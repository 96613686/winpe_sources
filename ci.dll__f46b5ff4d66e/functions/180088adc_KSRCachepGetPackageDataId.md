# KSRCachepGetPackageDataId

- ea: `0x180088adc`
- end: `0x180088c62`
- name: `KSRCachepGetPackageDataId`
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
- `0x180088adc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180088c1f`
- `ntoskrnl!ZwClose` at `0x180088c34`
- `ntoskrnl!ZwClose` at `0x180088c1f`
- `ntoskrnl!ZwClose` at `0x180088c34`
- `ntoskrnl!ZwOpenKey` at `0x180088b61`
- `ntoskrnl!ZwOpenKey` at `0x180088ba6`
- `ntoskrnl!ZwOpenKey` at `0x180088b61`
- `ntoskrnl!ZwOpenKey` at `0x180088ba6`
- `ntoskrnl!ZwEnumerateKey` at `0x180088bd6`
- `ntoskrnl!ZwEnumerateKey` at `0x180088bd6`

## string_xrefs

- `0x180088b10`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Index\PackageFullName`

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
0x180088adc  mov     [rsp-8+arg_10], rbx
0x180088ae1  push    rbp
0x180088ae2  push    rsi
0x180088ae3  push    rdi
0x180088ae4  lea     rbp, [rsp-47h]
0x180088ae9  sub     rsp, 0D0h
0x180088af0  mov     rax, cs:__security_cookie
0x180088af7  xor     rax, rsp
0x180088afa  mov     [rbp+57h+var_18], rax
0x180088afe  xor     eax, eax
0x180088b00  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180088b08  mov     [rbp+57h+KeyHandle], rax
0x180088b0c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180088b10  lea     rax, aRegistryMachin_22; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180088b17  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088b1f  mov     [rbp+57h+var_90], rax
0x180088b23  mov     rdi, rdx
0x180088b26  lea     rax, [rbp+57h+var_98]
0x180088b2a  mov     [rbp+57h+var_98], 0F200F0h
0x180088b32  mov     rsi, rcx
0x180088b35  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180088b39  xorps   xmm0, xmm0
0x180088b3c  mov     [rbp+57h+Handle], 0
0x180088b44  mov     edx, 20019h; DesiredAccess
0x180088b49  mov     [rbp+57h+var_B0], 0
0x180088b50  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180088b54  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180088b5c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088b61  call    cs:__imp_ZwOpenKey
0x180088b68  nop     dword ptr [rax+rax+00h]
0x180088b6d  mov     ebx, eax
0x180088b6f  test    eax, eax
0x180088b71  js      loc_180088C16
0x180088b77  mov     rax, [rbp+57h+KeyHandle]
0x180088b7b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180088b7f  xorps   xmm0, xmm0
0x180088b82  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180088b86  mov     edx, 20019h; DesiredAccess
0x180088b8b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180088b92  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x180088b96  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180088b9d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088ba2  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180088ba6  call    cs:__imp_ZwOpenKey
0x180088bad  nop     dword ptr [rax+rax+00h]
0x180088bb2  mov     ebx, eax
0x180088bb4  test    eax, eax
0x180088bb6  js      short loc_180088C16
0x180088bb8  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x180088bbc  lea     rax, [rbp+57h+var_B0]
0x180088bc0  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x180088bc5  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x180088bc9  xor     r8d, r8d; KeyInformationClass
0x180088bcc  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x180088bd4  xor     edx, edx; Index
0x180088bd6  call    cs:__imp_ZwEnumerateKey
0x180088bdd  nop     dword ptr [rax+rax+00h]
0x180088be2  mov     ebx, eax
0x180088be4  test    eax, eax
0x180088be6  js      short loc_180088C16
0x180088be8  mov     ecx, dword ptr [rbp+57h+Size]
0x180088beb  cmp     ecx, 24h ; '$'
0x180088bee  jbe     short loc_180088BF7
0x180088bf0  mov     ebx, 0C0000023h
0x180088bf5  jmp     short loc_180088C16
0x180088bf7  movzx   eax, word ptr [rdi+2]
0x180088bfb  cmp     eax, ecx
0x180088bfd  jb      short loc_180088BF0
0x180088bff  mov     r8, rcx; Size
0x180088c02  lea     rdx, [rbp+57h+Size+4]; Src
0x180088c06  mov     rcx, [rdi+8]; void *
0x180088c0a  call    memmove
0x180088c0f  movzx   eax, word ptr [rbp+57h+Size]
0x180088c13  mov     [rdi], ax
0x180088c16  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180088c1a  test    rcx, rcx
0x180088c1d  jz      short loc_180088C2B
0x180088c1f  call    cs:__imp_ZwClose
0x180088c26  nop     dword ptr [rax+rax+00h]
0x180088c2b  mov     rcx, [rbp+57h+Handle]; Handle
0x180088c2f  test    rcx, rcx
0x180088c32  jz      short loc_180088C40
0x180088c34  call    cs:__imp_ZwClose
0x180088c3b  nop     dword ptr [rax+rax+00h]
0x180088c40  mov     eax, ebx
0x180088c42  mov     rcx, [rbp+57h+var_18]
0x180088c46  xor     rcx, rsp; StackCookie
0x180088c49  call    __security_check_cookie
0x180088c4e  mov     rbx, [rsp+0E0h+arg_10]
0x180088c56  add     rsp, 0D0h
0x180088c5d  pop     rdi
0x180088c5e  pop     rsi
0x180088c5f  pop     rbp
0x180088c60  retn
```
