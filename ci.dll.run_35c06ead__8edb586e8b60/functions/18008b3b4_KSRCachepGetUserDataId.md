# KSRCachepGetUserDataId

- ea: `0x18008b3b4`
- end: `0x18008b53a`
- name: `KSRCachepGetUserDataId`
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
- `0x18008b3b4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18008b4f7`
- `ntoskrnl!ZwClose` at `0x18008b50c`
- `ntoskrnl!ZwClose` at `0x18008b4f7`
- `ntoskrnl!ZwClose` at `0x18008b50c`
- `ntoskrnl!ZwOpenKey` at `0x18008b439`
- `ntoskrnl!ZwOpenKey` at `0x18008b47e`
- `ntoskrnl!ZwOpenKey` at `0x18008b439`
- `ntoskrnl!ZwOpenKey` at `0x18008b47e`
- `ntoskrnl!ZwEnumerateKey` at `0x18008b4ae`
- `ntoskrnl!ZwEnumerateKey` at `0x18008b4ae`

## string_xrefs

- `0x18008b3e8`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\User\Index\UserSid`

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
0x18008b3b4  mov     [rsp-8+arg_10], rbx
0x18008b3b9  push    rbp
0x18008b3ba  push    rsi
0x18008b3bb  push    rdi
0x18008b3bc  lea     rbp, [rsp-47h]
0x18008b3c1  sub     rsp, 0D0h
0x18008b3c8  mov     rax, cs:__security_cookie
0x18008b3cf  xor     rax, rsp
0x18008b3d2  mov     [rbp+57h+var_18], rax
0x18008b3d6  xor     eax, eax
0x18008b3d8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008b3e0  mov     [rbp+57h+KeyHandle], rax
0x18008b3e4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008b3e8  lea     rax, aRegistryMachin_3; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008b3ef  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008b3f7  mov     [rbp+57h+var_90], rax
0x18008b3fb  mov     rdi, rdx
0x18008b3fe  lea     rax, [rbp+57h+var_98]
0x18008b402  mov     [rbp+57h+var_98], 0DC00DAh
0x18008b40a  mov     rsi, rcx
0x18008b40d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18008b411  xorps   xmm0, xmm0
0x18008b414  mov     [rbp+57h+Handle], 0
0x18008b41c  mov     edx, 20019h; DesiredAccess
0x18008b421  mov     [rbp+57h+var_B0], 0
0x18008b428  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18008b42c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18008b434  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008b439  call    cs:__imp_ZwOpenKey
0x18008b440  nop     dword ptr [rax+rax+00h]
0x18008b445  mov     ebx, eax
0x18008b447  test    eax, eax
0x18008b449  js      loc_18008B4EE
0x18008b44f  mov     rax, [rbp+57h+KeyHandle]
0x18008b453  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18008b457  xorps   xmm0, xmm0
0x18008b45a  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18008b45e  mov     edx, 20019h; DesiredAccess
0x18008b463  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18008b46a  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x18008b46e  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18008b475  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008b47a  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18008b47e  call    cs:__imp_ZwOpenKey
0x18008b485  nop     dword ptr [rax+rax+00h]
0x18008b48a  mov     ebx, eax
0x18008b48c  test    eax, eax
0x18008b48e  js      short loc_18008B4EE
0x18008b490  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x18008b494  lea     rax, [rbp+57h+var_B0]
0x18008b498  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x18008b49d  lea     r9, [rbp+57h+KeyInformation]; KeyInformation
0x18008b4a1  xor     r8d, r8d; KeyInformationClass
0x18008b4a4  mov     [rsp+0E0h+Length], 3Ah ; ':'; Length
0x18008b4ac  xor     edx, edx; Index
0x18008b4ae  call    cs:__imp_ZwEnumerateKey
0x18008b4b5  nop     dword ptr [rax+rax+00h]
0x18008b4ba  mov     ebx, eax
0x18008b4bc  test    eax, eax
0x18008b4be  js      short loc_18008B4EE
0x18008b4c0  mov     ecx, dword ptr [rbp+57h+Size]
0x18008b4c3  cmp     ecx, 24h ; '$'
0x18008b4c6  jbe     short loc_18008B4CF
0x18008b4c8  mov     ebx, 0C0000023h
0x18008b4cd  jmp     short loc_18008B4EE
0x18008b4cf  movzx   eax, word ptr [rdi+2]
0x18008b4d3  cmp     eax, ecx
0x18008b4d5  jb      short loc_18008B4C8
0x18008b4d7  mov     r8, rcx; Size
0x18008b4da  lea     rdx, [rbp+57h+Size+4]; Src
0x18008b4de  mov     rcx, [rdi+8]; void *
0x18008b4e2  call    memmove
0x18008b4e7  movzx   eax, word ptr [rbp+57h+Size]
0x18008b4eb  mov     [rdi], ax
0x18008b4ee  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18008b4f2  test    rcx, rcx
0x18008b4f5  jz      short loc_18008B503
0x18008b4f7  call    cs:__imp_ZwClose
0x18008b4fe  nop     dword ptr [rax+rax+00h]
0x18008b503  mov     rcx, [rbp+57h+Handle]; Handle
0x18008b507  test    rcx, rcx
0x18008b50a  jz      short loc_18008B518
0x18008b50c  call    cs:__imp_ZwClose
0x18008b513  nop     dword ptr [rax+rax+00h]
0x18008b518  mov     eax, ebx
0x18008b51a  mov     rcx, [rbp+57h+var_18]
0x18008b51e  xor     rcx, rsp; StackCookie
0x18008b521  call    __security_check_cookie
0x18008b526  mov     rbx, [rsp+0E0h+arg_10]
0x18008b52e  add     rsp, 0D0h
0x18008b535  pop     rdi
0x18008b536  pop     rsi
0x18008b537  pop     rbp
0x18008b538  retn
```
