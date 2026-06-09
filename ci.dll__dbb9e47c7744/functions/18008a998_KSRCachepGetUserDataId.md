# KSRCachepGetUserDataId

- ea: `0x18008a998`
- end: `0x18008ab1e`
- name: `KSRCachepGetUserDataId`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089b88`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18008a998`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008aadb`
- `ntoskrnl!ZwClose` at `0x18008aaf0`
- `ntoskrnl!ZwClose` at `0x18008aadb`
- `ntoskrnl!ZwClose` at `0x18008aaf0`
- `ntoskrnl!ZwOpenKey` at `0x18008aa1d`
- `ntoskrnl!ZwOpenKey` at `0x18008aa62`
- `ntoskrnl!ZwOpenKey` at `0x18008aa1d`
- `ntoskrnl!ZwOpenKey` at `0x18008aa62`
- `ntoskrnl!ZwEnumerateKey` at `0x18008aa92`
- `ntoskrnl!ZwEnumerateKey` at `0x18008aa92`

## string_xrefs

- `0x18008a9cc`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall KSRCachepGetUserDataId(struct _UNICODE_STRING *a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG ResultLength; // [rsp+30h] [rbp-59h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-31h] BYREF
  _BYTE KeyInformation[12]; // [rsp+88h] [rbp-1h] BYREF
  unsigned int Size; // [rsp+94h] [rbp+Bh]
  size_t Size_4; // [rsp+98h] [rbp+Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\User\\Index\\UserSid";
  v9[0] = 14418138;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  Handle = 0;
  ResultLength = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v4 >= 0 )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.ObjectName = a1;
    v4 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    if ( v4 >= 0 )
    {
      v4 = ZwEnumerateKey(Handle, 0, KeyBasicInformation, KeyInformation, 0x3Au, &ResultLength);
      if ( v4 >= 0 )
      {
        if ( Size > 0x24 || *(unsigned __int16 *)(a2 + 2) < Size )
        {
          v4 = -1073741789;
        }
        else
        {
          memmove(*(void **)(a2 + 8), &Size_4, Size);
          *(_WORD *)a2 = Size;
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008a998  mov     [rsp-8+arg_10], rbx
0x18008a99d  push    rbp
0x18008a99e  push    rsi
0x18008a99f  push    rdi
0x18008a9a0  lea     rbp, [rsp-47h]
0x18008a9a5  sub     rsp, 0D0h
0x18008a9ac  mov     rax, cs:__security_cookie
0x18008a9b3  xor     rax, rsp
0x18008a9b6  mov     [rbp+57h+var_18], rax
0x18008a9ba  xor     eax, eax
0x18008a9bc  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008a9c4  mov     [rbp+57h+KeyHandle], rax
0x18008a9c8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008a9cc  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008a9d3  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008a9db  mov     [rbp+57h+var_90], rax
0x18008a9df  mov     rdi, rdx
0x18008a9e2  lea     rax, [rbp+57h+var_98]
0x18008a9e6  mov     [rbp+57h+var_98], 0DC00DAh
0x18008a9ee  mov     rsi, rcx
0x18008a9f1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008a9f5  xorps   xmm0, xmm0
0x18008a9f8  mov     [rbp+57h+Handle], 0
0x18008aa00  mov     edx, 20019h; DesiredAccess
0x18008aa05  mov     [rbp+57h+var_B0], 0
0x18008aa0c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008aa10  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008aa18  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008aa1d  call    cs:__imp_ZwOpenKey
0x18008aa24  nop     dword ptr [rax+rax+00h]
0x18008aa29  mov     ebx, eax
0x18008aa2b  test    eax, eax
0x18008aa2d  js      loc_18008AAD2
0x18008aa33  mov     rax, [rbp+57h+KeyHandle]
0x18008aa37  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008aa3b  xorps   xmm0, xmm0
0x18008aa3e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008aa42  mov     edx, 20019h; DesiredAccess
0x18008aa47  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008aa4e  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008aa52  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008aa59  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008aa5e  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008aa62  call    cs:__imp_ZwOpenKey
0x18008aa69  nop     dword ptr [rax+rax+00h]
0x18008aa6e  mov     ebx, eax
0x18008aa70  test    eax, eax
0x18008aa72  js      short loc_18008AAD2
0x18008aa74  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008aa78  lea     rax, [rbp+57h+var_B0]
0x18008aa7c  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18008aa81  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008aa85  xor     r8d, r8d; KeyInformationClass
0x18008aa88  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x18008aa90  xor     edx, edx; Index
0x18008aa92  call    cs:__imp_ZwEnumerateKey
0x18008aa99  nop     dword ptr [rax+rax+00h]
0x18008aa9e  mov     ebx, eax
0x18008aaa0  test    eax, eax
0x18008aaa2  js      short loc_18008AAD2
0x18008aaa4  mov     ecx, dword ptr [rbp+57h+Size]
0x18008aaa7  cmp     ecx, 24h ; '$'
0x18008aaaa  jbe     short loc_18008AAB3
0x18008aaac  mov     ebx, 0C0000023h
0x18008aab1  jmp     short loc_18008AAD2
0x18008aab3  movzx   eax, word ptr [rdi+2]
0x18008aab7  cmp     eax, ecx
0x18008aab9  jb      short loc_18008AAAC
0x18008aabb  mov     r8, rcx; Size
0x18008aabe  lea     rdx, [rbp+57h+Size+4]; Src
0x18008aac2  mov     rcx, [rdi+8]; void *
0x18008aac6  call    memmove
0x18008aacb  movzx   eax, word ptr [rbp+57h+Size]
0x18008aacf  mov     [rdi], ax
0x18008aad2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008aad6  test    rcx, rcx
0x18008aad9  jz      short loc_18008AAE7
0x18008aadb  call    cs:__imp_ZwClose
0x18008aae2  nop     dword ptr [rax+rax+00h]
0x18008aae7  mov     rcx, [rbp+57h+Handle]; Handle
0x18008aaeb  test    rcx, rcx
0x18008aaee  jz      short loc_18008AAFC
0x18008aaf0  call    cs:__imp_ZwClose
0x18008aaf7  nop     dword ptr [rax+rax+00h]
0x18008aafc  mov     eax, ebx
0x18008aafe  mov     rcx, [rbp+57h+var_18]
0x18008ab02  xor     rcx, rsp; StackCookie
0x18008ab05  call    __security_check_cookie
0x18008ab0a  mov     rbx, [rsp+0E0h+arg_10]
0x18008ab12  add     rsp, 0D0h
0x18008ab19  pop     rdi
0x18008ab1a  pop     rsi
0x18008ab1b  pop     rbp
0x18008ab1c  retn
```
