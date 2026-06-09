# DfscCreateSymbolicLink

- ea: `0x140013908`
- end: `0x1400139f9`
- name: `DfscCreateSymbolicLink`
- size: `241`
- prototype: `__int64 __fastcall(WCHAR, struct _UNICODE_STRING *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001338c`

## callees

- `0x140003ec0`
- `0x140005f70`
- `0x140013908`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013961`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013961`
- `ntoskrnl!ZwClose` at `0x1400139c9`
- `ntoskrnl!ZwClose` at `0x1400139c9`
- `ntoskrnl!ZwCreateSymbolicLinkObject` at `0x1400139b3`
- `ntoskrnl!ZwCreateSymbolicLinkObject` at `0x1400139b3`

## pseudocode

```c
__int64 __fastcall DfscCreateSymbolicLink(WCHAR a1, struct _UNICODE_STRING *a2, const wchar_t *a3)
{
  NTSTATUS v5; // ebx
  void *SymbolicLinkHandle; // [rsp+20h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  wchar_t pszDest[28]; // [rsp+68h] [rbp+Fh] BYREF

  SymbolicLinkHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlStringCbCopyW(pszDest, (size_t)a2, a3);
  RtlInitUnicodeStringEx(&DestinationString, pszDest);
  DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 2] = a1;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1616;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, a2);
  if ( v5 >= 0 )
    ZwClose(SymbolicLinkHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140013908  mov     [rsp-8+arg_0], rbx
0x14001390d  mov     [rsp-8+arg_10], rdi
0x140013912  push    rbp
0x140013913  lea     rbp, [rsp-57h]
0x140013918  sub     rsp, 0B0h
0x14001391f  mov     rax, cs:__security_cookie
0x140013926  xor     rax, rsp
0x140013929  mov     [rbp+57h+var_10], rax
0x14001392d  xorps   xmm0, xmm0
0x140013930  mov     [rbp+57h+SymbolicLinkHandle], 0
0x140013938  movzx   ebx, cx
0x14001393b  xor     eax, eax
0x14001393d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140013941  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140013945  mov     rdi, rdx
0x140013948  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001394c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140013950  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140013954  call    RtlStringCbCopyW
0x140013959  lea     rdx, [rbp+57h+pszDest]; SourceString
0x14001395d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140013961  call    cs:__imp_RtlInitUnicodeStringEx
0x140013968  nop     dword ptr [rax+rax+00h]
0x14001396d  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140013971  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140013975  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140013979  xorps   xmm0, xmm0
0x14001397c  shr     rcx, 1
0x14001397f  mov     r9, rdi; Name
0x140013982  mov     edx, 0F0001h; DesiredAccess
0x140013987  mov     [rax+rcx*2-4], bx
0x14001398c  lea     rax, [rbp+57h+DestinationString]
0x140013990  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x140013994  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140013998  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001399f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400139a7  mov     [rbp+57h+ObjectAttributes.Attributes], 650h
0x1400139ae  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400139b3  call    cs:__imp_ZwCreateSymbolicLinkObject
0x1400139ba  nop     dword ptr [rax+rax+00h]
0x1400139bf  mov     ebx, eax
0x1400139c1  test    eax, eax
0x1400139c3  js      short loc_1400139D5
0x1400139c5  mov     rcx, [rbp+57h+SymbolicLinkHandle]; Handle
0x1400139c9  call    cs:__imp_ZwClose
0x1400139d0  nop     dword ptr [rax+rax+00h]
0x1400139d5  mov     eax, ebx
0x1400139d7  mov     rcx, [rbp+57h+var_10]
0x1400139db  xor     rcx, rsp; StackCookie
0x1400139de  call    __security_check_cookie
0x1400139e3  lea     r11, [rsp+0B0h+var_s0]
0x1400139eb  mov     rbx, [r11+10h]
0x1400139ef  mov     rdi, [r11+20h]
0x1400139f3  mov     rsp, r11
0x1400139f6  pop     rbp
0x1400139f7  retn
```
