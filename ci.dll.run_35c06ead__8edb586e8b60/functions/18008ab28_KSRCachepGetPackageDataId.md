# KSRCachepGetPackageDataId

- ea: `0x18008ab28`
- end: `0x18008acae`
- name: `KSRCachepGetPackageDataId`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008a5a4`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18008ab28`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008ac6b`
- `ntoskrnl!ZwClose` at `0x18008ac80`
- `ntoskrnl!ZwClose` at `0x18008ac6b`
- `ntoskrnl!ZwClose` at `0x18008ac80`
- `ntoskrnl!ZwOpenKey` at `0x18008abad`
- `ntoskrnl!ZwOpenKey` at `0x18008abf2`
- `ntoskrnl!ZwOpenKey` at `0x18008abad`
- `ntoskrnl!ZwOpenKey` at `0x18008abf2`
- `ntoskrnl!ZwEnumerateKey` at `0x18008ac22`
- `ntoskrnl!ZwEnumerateKey` at `0x18008ac22`

## string_xrefs

- `0x18008ab5c`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`

## pseudocode

```c
__int64 __fastcall KSRCachepGetPackageDataId(struct _UNICODE_STRING *a1, __int64 a2)
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
  v9[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\"
           "Index\\PackageFullName";
  v9[0] = 15859952;
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
0x18008ab28  mov     [rsp-8+arg_10], rbx
0x18008ab2d  push    rbp
0x18008ab2e  push    rsi
0x18008ab2f  push    rdi
0x18008ab30  lea     rbp, [rsp-47h]
0x18008ab35  sub     rsp, 0D0h
0x18008ab3c  mov     rax, cs:__security_cookie
0x18008ab43  xor     rax, rsp
0x18008ab46  mov     [rbp+57h+var_18], rax
0x18008ab4a  xor     eax, eax
0x18008ab4c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008ab54  mov     [rbp+57h+KeyHandle], rax
0x18008ab58  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008ab5c  lea     rax, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008ab63  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008ab6b  mov     [rbp+57h+var_90], rax
0x18008ab6f  mov     rdi, rdx
0x18008ab72  lea     rax, [rbp+57h+var_98]
0x18008ab76  mov     [rbp+57h+var_98], 0F200F0h
0x18008ab7e  mov     rsi, rcx
0x18008ab81  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008ab85  xorps   xmm0, xmm0
0x18008ab88  mov     [rbp+57h+Handle], 0
0x18008ab90  mov     edx, 20019h; DesiredAccess
0x18008ab95  mov     [rbp+57h+var_B0], 0
0x18008ab9c  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008aba0  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008aba8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008abad  call    cs:__imp_ZwOpenKey
0x18008abb4  nop     dword ptr [rax+rax+00h]
0x18008abb9  mov     ebx, eax
0x18008abbb  test    eax, eax
0x18008abbd  js      loc_18008AC62
0x18008abc3  mov     rax, [rbp+57h+KeyHandle]
0x18008abc7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008abcb  xorps   xmm0, xmm0
0x18008abce  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008abd2  mov     edx, 20019h; DesiredAccess
0x18008abd7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008abde  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008abe2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008abe9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008abee  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008abf2  call    cs:__imp_ZwOpenKey
0x18008abf9  nop     dword ptr [rax+rax+00h]
0x18008abfe  mov     ebx, eax
0x18008ac00  test    eax, eax
0x18008ac02  js      short loc_18008AC62
0x18008ac04  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008ac08  lea     rax, [rbp+57h+var_B0]
0x18008ac0c  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18008ac11  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008ac15  xor     r8d, r8d; KeyInformationClass
0x18008ac18  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x18008ac20  xor     edx, edx; Index
0x18008ac22  call    cs:__imp_ZwEnumerateKey
0x18008ac29  nop     dword ptr [rax+rax+00h]
0x18008ac2e  mov     ebx, eax
0x18008ac30  test    eax, eax
0x18008ac32  js      short loc_18008AC62
0x18008ac34  mov     ecx, dword ptr [rbp+57h+Size]
0x18008ac37  cmp     ecx, 24h ; '$'
0x18008ac3a  jbe     short loc_18008AC43
0x18008ac3c  mov     ebx, 0C0000023h
0x18008ac41  jmp     short loc_18008AC62
0x18008ac43  movzx   eax, word ptr [rdi+2]
0x18008ac47  cmp     eax, ecx
0x18008ac49  jb      short loc_18008AC3C
0x18008ac4b  mov     r8, rcx; Size
0x18008ac4e  lea     rdx, [rbp+57h+Size+4]; Src
0x18008ac52  mov     rcx, [rdi+8]; void *
0x18008ac56  call    memmove
0x18008ac5b  movzx   eax, word ptr [rbp+57h+Size]
0x18008ac5f  mov     [rdi], ax
0x18008ac62  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008ac66  test    rcx, rcx
0x18008ac69  jz      short loc_18008AC77
0x18008ac6b  call    cs:__imp_ZwClose
0x18008ac72  nop     dword ptr [rax+rax+00h]
0x18008ac77  mov     rcx, [rbp+57h+Handle]; Handle
0x18008ac7b  test    rcx, rcx
0x18008ac7e  jz      short loc_18008AC8C
0x18008ac80  call    cs:__imp_ZwClose
0x18008ac87  nop     dword ptr [rax+rax+00h]
0x18008ac8c  mov     eax, ebx
0x18008ac8e  mov     rcx, [rbp+57h+var_18]
0x18008ac92  xor     rcx, rsp; StackCookie
0x18008ac95  call    __security_check_cookie
0x18008ac9a  mov     rbx, [rsp+0E0h+arg_10]
0x18008aca2  add     rsp, 0D0h
0x18008aca9  pop     rdi
0x18008acaa  pop     rsi
0x18008acab  pop     rbp
0x18008acac  retn
```
