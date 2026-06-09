# KSRCachepGetUserDataId

- ea: `0x180089368`
- end: `0x1800894ee`
- name: `KSRCachepGetUserDataId`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180088558`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x180089368`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800894ab`
- `ntoskrnl!ZwClose` at `0x1800894c0`
- `ntoskrnl!ZwClose` at `0x1800894ab`
- `ntoskrnl!ZwClose` at `0x1800894c0`
- `ntoskrnl!ZwOpenKey` at `0x1800893ed`
- `ntoskrnl!ZwOpenKey` at `0x180089432`
- `ntoskrnl!ZwOpenKey` at `0x1800893ed`
- `ntoskrnl!ZwOpenKey` at `0x180089432`
- `ntoskrnl!ZwEnumerateKey` at `0x180089462`
- `ntoskrnl!ZwEnumerateKey` at `0x180089462`

## string_xrefs

- `0x18008939c`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\User\Index\UserSid`

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
0x180089368  mov     [rsp-8+arg_10], rbx
0x18008936d  push    rbp
0x18008936e  push    rsi
0x18008936f  push    rdi
0x180089370  lea     rbp, [rsp-47h]
0x180089375  sub     rsp, 0D0h
0x18008937c  mov     rax, cs:__security_cookie
0x180089383  xor     rax, rsp
0x180089386  mov     [rbp+57h+var_18], rax
0x18008938a  xor     eax, eax
0x18008938c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180089394  mov     [rbp+57h+KeyHandle], rax
0x180089398  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008939c  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x1800893a3  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800893ab  mov     [rbp+57h+var_90], rax
0x1800893af  mov     rdi, rdx
0x1800893b2  lea     rax, [rbp+57h+var_98]
0x1800893b6  mov     [rbp+57h+var_98], 0DC00DAh
0x1800893be  mov     rsi, rcx
0x1800893c1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800893c5  xorps   xmm0, xmm0
0x1800893c8  mov     [rbp+57h+Handle], 0
0x1800893d0  mov     edx, 20019h; DesiredAccess
0x1800893d5  mov     [rbp+57h+var_B0], 0
0x1800893dc  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800893e0  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800893e8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800893ed  call    cs:__imp_ZwOpenKey
0x1800893f4  nop     dword ptr [rax+rax+00h]
0x1800893f9  mov     ebx, eax
0x1800893fb  test    eax, eax
0x1800893fd  js      loc_1800894A2
0x180089403  mov     rax, [rbp+57h+KeyHandle]
0x180089407  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008940b  xorps   xmm0, xmm0
0x18008940e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180089412  mov     edx, 20019h; DesiredAccess
0x180089417  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008941e  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180089422  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180089429  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008942e  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180089432  call    cs:__imp_ZwOpenKey
0x180089439  nop     dword ptr [rax+rax+00h]
0x18008943e  mov     ebx, eax
0x180089440  test    eax, eax
0x180089442  js      short loc_1800894A2
0x180089444  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180089448  lea     rax, [rbp+57h+var_B0]
0x18008944c  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180089451  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x180089455  xor     r8d, r8d; KeyInformationClass
0x180089458  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x180089460  xor     edx, edx; Index
0x180089462  call    cs:__imp_ZwEnumerateKey
0x180089469  nop     dword ptr [rax+rax+00h]
0x18008946e  mov     ebx, eax
0x180089470  test    eax, eax
0x180089472  js      short loc_1800894A2
0x180089474  mov     ecx, dword ptr [rbp+57h+Size]
0x180089477  cmp     ecx, 24h ; '$'
0x18008947a  jbe     short loc_180089483
0x18008947c  mov     ebx, 0C0000023h
0x180089481  jmp     short loc_1800894A2
0x180089483  movzx   eax, word ptr [rdi+2]
0x180089487  cmp     eax, ecx
0x180089489  jb      short loc_18008947C
0x18008948b  mov     r8, rcx; Size
0x18008948e  lea     rdx, [rbp+57h+Size+4]; Src
0x180089492  mov     rcx, [rdi+8]; void *
0x180089496  call    memmove
0x18008949b  movzx   eax, word ptr [rbp+57h+Size]
0x18008949f  mov     [rdi], ax
0x1800894a2  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800894a6  test    rcx, rcx
0x1800894a9  jz      short loc_1800894B7
0x1800894ab  call    cs:__imp_ZwClose
0x1800894b2  nop     dword ptr [rax+rax+00h]
0x1800894b7  mov     rcx, [rbp+57h+Handle]; Handle
0x1800894bb  test    rcx, rcx
0x1800894be  jz      short loc_1800894CC
0x1800894c0  call    cs:__imp_ZwClose
0x1800894c7  nop     dword ptr [rax+rax+00h]
0x1800894cc  mov     eax, ebx
0x1800894ce  mov     rcx, [rbp+57h+var_18]
0x1800894d2  xor     rcx, rsp; StackCookie
0x1800894d5  call    __security_check_cookie
0x1800894da  mov     rbx, [rsp+0E0h+arg_10]
0x1800894e2  add     rsp, 0D0h
0x1800894e9  pop     rdi
0x1800894ea  pop     rsi
0x1800894eb  pop     rbp
0x1800894ec  retn
```
