# KSRCachepGetPackageFullNameFromPackageDataId

- ea: `0x18008af34`
- end: `0x18008b103`
- name: `KSRCachepGetPackageFullNameFromPackageDataId`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008a5a4`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18008af34`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x18008b060`
- `ntoskrnl!ZwQueryValueKey` at `0x18008b060`
- `ntoskrnl!ZwClose` at `0x18008b0bc`
- `ntoskrnl!ZwClose` at `0x18008b0d2`
- `ntoskrnl!ZwClose` at `0x18008b0bc`
- `ntoskrnl!ZwClose` at `0x18008b0d2`
- `ntoskrnl!ZwOpenKey` at `0x18008afdb`
- `ntoskrnl!ZwOpenKey` at `0x18008b026`
- `ntoskrnl!ZwOpenKey` at `0x18008afdb`
- `ntoskrnl!ZwOpenKey` at `0x18008b026`

## string_xrefs

- `0x18008af79`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`

## pseudocode

```c
__int64 __fastcall KSRCachepGetPackageFullNameFromPackageDataId(struct _UNICODE_STRING *a1, __int64 a2)
{
  NTSTATUS v4; // ebx
  ULONG Length; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v13; // [rsp+A4h] [rbp-5Ch]
  unsigned int v14; // [rsp+A8h] [rbp-58h]
  _BYTE Src[260]; // [rsp+ACh] [rbp-54h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  Handle = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v9[1] = L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel\\StateRepository\\Cache\\Package\\Data";
  v9[0] = 13631694;
  ValueName.Buffer = L"PackageFullName";
  *(_QWORD *)&ValueName.Length = 2097182;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v9;
  Length = 272;
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
      v4 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, Length, &Length);
      if ( v4 >= 0 )
      {
        if ( v13 == 1 && v14 >= 2 )
        {
          if ( *(unsigned __int16 *)(a2 + 2) >= v14 )
          {
            memmove(*(void **)(a2 + 8), Src, v14 - 2LL);
            *(_WORD *)a2 = v14 - 2;
          }
          else
          {
            v4 = -1073741789;
          }
        }
        else
        {
          v4 = -1073741788;
        }
      }
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008af34  mov     [rsp-8+arg_10], rbx
0x18008af39  push    rbp
0x18008af3a  push    rsi
0x18008af3b  push    rdi
0x18008af3c  lea     rbp, [rsp-0C0h]
0x18008af44  sub     rsp, 1C0h
0x18008af4b  mov     rax, cs:__security_cookie
0x18008af52  xor     rax, rsp
0x18008af55  mov     [rbp+0D0h+var_20], rax
0x18008af5c  xor     eax, eax
0x18008af5e  mov     qword ptr [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x18008af67  mov     [rsp+1D0h+KeyHandle], rax
0x18008af6c  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x18008af71  mov     [rsp+1D0h+Handle], rax
0x18008af76  mov     rdi, rdx
0x18008af79  lea     rax, aRegistryMachin_23; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18008af80  mov     qword ptr [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x18008af88  mov     [rsp+1D0h+var_180], rax
0x18008af8d  mov     rsi, rcx
0x18008af90  lea     rax, aPackagefullnam; "PackageFullName"
0x18008af97  mov     [rsp+1D0h+var_188], 0D000CEh
0x18008afa0  mov     [rsp+1D0h+ValueName.Buffer], rax
0x18008afa5  lea     rcx, [rsp+1D0h+KeyHandle]; KeyHandle
0x18008afaa  lea     rax, [rsp+1D0h+var_188]
0x18008afaf  mov     qword ptr [rsp+1D0h+ValueName.Length], 20001Eh
0x18008afb8  xorps   xmm0, xmm0
0x18008afbb  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rax
0x18008afc0  mov     edx, 20019h; DesiredAccess
0x18008afc5  mov     [rsp+1D0h+var_1A0], 110h
0x18008afcd  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], 0
0x18008afd6  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008afdb  call    cs:__imp_ZwOpenKey
0x18008afe2  nop     dword ptr [rax+rax+00h]
0x18008afe7  mov     ebx, eax
0x18008afe9  test    eax, eax
0x18008afeb  js      loc_18008B0B2
0x18008aff1  mov     rax, [rsp+1D0h+KeyHandle]
0x18008aff6  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x18008affb  xorps   xmm0, xmm0
0x18008affe  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], rax
0x18008b003  mov     edx, 20019h; DesiredAccess
0x18008b008  mov     [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x18008b010  lea     rcx, [rsp+1D0h+Handle]; KeyHandle
0x18008b015  mov     [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x18008b01c  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008b021  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rsi
0x18008b026  call    cs:__imp_ZwOpenKey
0x18008b02d  nop     dword ptr [rax+rax+00h]
0x18008b032  mov     ebx, eax
0x18008b034  test    eax, eax
0x18008b036  js      short loc_18008B0B2
0x18008b038  mov     rcx, [rsp+1D0h+Handle]; KeyHandle
0x18008b03d  lea     rax, [rsp+1D0h+var_1A0]
0x18008b042  mov     [rsp+1D0h+ResultLength], rax; ResultLength
0x18008b047  lea     r9, [rbp+0D0h+KeyValueInformation]; KeyValueInformation
0x18008b04b  mov     eax, [rsp+1D0h+var_1A0]
0x18008b04f  lea     rdx, [rsp+1D0h+ValueName]; ValueName
0x18008b054  mov     esi, 2
0x18008b059  mov     [rsp+1D0h+Length], eax; Length
0x18008b05d  mov     r8d, esi; KeyValueInformationClass
0x18008b060  call    cs:__imp_ZwQueryValueKey
0x18008b067  nop     dword ptr [rax+rax+00h]
0x18008b06c  mov     ebx, eax
0x18008b06e  test    eax, eax
0x18008b070  js      short loc_18008B0B2
0x18008b072  cmp     [rbp+0D0h+var_12C], 1
0x18008b076  jnz     short loc_18008B0AD
0x18008b078  mov     ecx, [rbp+0D0h+var_128]
0x18008b07b  cmp     ecx, esi
0x18008b07d  jb      short loc_18008B0AD
0x18008b07f  movzx   eax, word ptr [rdi+2]
0x18008b083  cmp     eax, ecx
0x18008b085  jnb     short loc_18008B08E
0x18008b087  mov     ebx, 0C0000023h
0x18008b08c  jmp     short loc_18008B0B2
0x18008b08e  mov     r8, rcx
0x18008b091  lea     rdx, [rbp+0D0h+Src]; Src
0x18008b095  mov     rcx, [rdi+8]; void *
0x18008b099  sub     r8, rsi; Size
0x18008b09c  call    memmove
0x18008b0a1  movzx   eax, word ptr [rbp+0D0h+var_128]
0x18008b0a5  sub     ax, si
0x18008b0a8  mov     [rdi], ax
0x18008b0ab  jmp     short loc_18008B0B2
0x18008b0ad  mov     ebx, 0C0000024h
0x18008b0b2  mov     rcx, [rsp+1D0h+Handle]; Handle
0x18008b0b7  test    rcx, rcx
0x18008b0ba  jz      short loc_18008B0C8
0x18008b0bc  call    cs:__imp_ZwClose
0x18008b0c3  nop     dword ptr [rax+rax+00h]
0x18008b0c8  mov     rcx, [rsp+1D0h+KeyHandle]; Handle
0x18008b0cd  test    rcx, rcx
0x18008b0d0  jz      short loc_18008B0DE
0x18008b0d2  call    cs:__imp_ZwClose
0x18008b0d9  nop     dword ptr [rax+rax+00h]
0x18008b0de  mov     eax, ebx
0x18008b0e0  mov     rcx, [rbp+0D0h+var_20]
0x18008b0e7  xor     rcx, rsp; StackCookie
0x18008b0ea  call    __security_check_cookie
0x18008b0ef  mov     rbx, [rsp+1D0h+arg_10]
0x18008b0f7  add     rsp, 1C0h
0x18008b0fe  pop     rdi
0x18008b0ff  pop     rsi
0x18008b100  pop     rbp
0x18008b101  retn
```
