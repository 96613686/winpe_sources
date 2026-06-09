# DfscDeleteSymbolicLink

- ea: `0x140013cbc`
- end: `0x140013db0`
- name: `DfscDeleteSymbolicLink`
- size: `244`
- prototype: `__int64 __fastcall(WCHAR, size_t, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001338c`
- `0x14002545c`

## callees

- `0x140003ec0`
- `0x140005f70`
- `0x140013cbc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013d0d`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013d0d`
- `ntoskrnl!ZwClose` at `0x140013d84`
- `ntoskrnl!ZwClose` at `0x140013d84`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140013d5c`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140013d5c`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x140013d72`
- `ntoskrnl!ZwMakeTemporaryObject` at `0x140013d72`

## pseudocode

```c
__int64 __fastcall DfscDeleteSymbolicLink(WCHAR a1, size_t a2, const wchar_t *a3)
{
  NTSTATUS TemporaryObject; // ebx
  void *LinkHandle; // [rsp+20h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-21h] BYREF
  wchar_t pszDest[28]; // [rsp+68h] [rbp+Fh] BYREF

  LinkHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlStringCbCopyW(pszDest, a2, a3);
  RtlInitUnicodeStringEx(&DestinationString, pszDest);
  DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) - 2] = a1;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 1616;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  TemporaryObject = ZwOpenSymbolicLinkObject(&LinkHandle, 0x10001u, &ObjectAttributes);
  if ( TemporaryObject >= 0 )
  {
    TemporaryObject = ZwMakeTemporaryObject(LinkHandle);
    ZwClose(LinkHandle);
  }
  return (unsigned int)TemporaryObject;
}

```

## disassembly

```asm
0x140013cbc  mov     [rsp-8+arg_0], rbx
0x140013cc1  push    rbp
0x140013cc2  lea     rbp, [rsp-57h]
0x140013cc7  sub     rsp, 0B0h
0x140013cce  mov     rax, cs:__security_cookie
0x140013cd5  xor     rax, rsp
0x140013cd8  mov     [rbp+57h+var_10], rax
0x140013cdc  xorps   xmm0, xmm0
0x140013cdf  mov     [rbp+57h+LinkHandle], 0
0x140013ce7  movzx   ebx, cx
0x140013cea  xor     eax, eax
0x140013cec  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140013cf0  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140013cf4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140013cf8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140013cfc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140013d00  call    RtlStringCbCopyW
0x140013d05  lea     rdx, [rbp+57h+pszDest]; SourceString
0x140013d09  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140013d0d  call    cs:__imp_RtlInitUnicodeStringEx
0x140013d14  nop     dword ptr [rax+rax+00h]
0x140013d19  movzx   ecx, [rbp+57h+DestinationString.Length]
0x140013d1d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140013d21  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140013d25  xorps   xmm0, xmm0
0x140013d28  shr     rcx, 1
0x140013d2b  mov     edx, 10001h; DesiredAccess
0x140013d30  mov     [rax+rcx*2-4], bx
0x140013d35  lea     rax, [rbp+57h+DestinationString]
0x140013d39  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140013d3d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140013d41  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140013d48  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140013d50  mov     [rbp+57h+ObjectAttributes.Attributes], 650h
0x140013d57  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140013d5c  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140013d63  nop     dword ptr [rax+rax+00h]
0x140013d68  mov     ebx, eax
0x140013d6a  test    eax, eax
0x140013d6c  js      short loc_140013D90
0x140013d6e  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x140013d72  call    cs:__imp_ZwMakeTemporaryObject
0x140013d79  nop     dword ptr [rax+rax+00h]
0x140013d7e  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x140013d82  mov     ebx, eax
0x140013d84  call    cs:__imp_ZwClose
0x140013d8b  nop     dword ptr [rax+rax+00h]
0x140013d90  mov     eax, ebx
0x140013d92  mov     rcx, [rbp+57h+var_10]
0x140013d96  xor     rcx, rsp; StackCookie
0x140013d99  call    __security_check_cookie
0x140013d9e  mov     rbx, [rsp+0B0h+arg_0]
0x140013da6  add     rsp, 0B0h
0x140013dad  pop     rbp
0x140013dae  retn
```
