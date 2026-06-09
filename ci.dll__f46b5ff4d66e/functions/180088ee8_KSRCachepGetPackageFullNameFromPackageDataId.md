# KSRCachepGetPackageFullNameFromPackageDataId

- ea: `0x180088ee8`
- end: `0x1800890b7`
- name: `KSRCachepGetPackageFullNameFromPackageDataId`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180088558`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x180088ee8`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180089014`
- `ntoskrnl!ZwQueryValueKey` at `0x180089014`
- `ntoskrnl!ZwClose` at `0x180089070`
- `ntoskrnl!ZwClose` at `0x180089086`
- `ntoskrnl!ZwClose` at `0x180089070`
- `ntoskrnl!ZwClose` at `0x180089086`
- `ntoskrnl!ZwOpenKey` at `0x180088f8f`
- `ntoskrnl!ZwOpenKey` at `0x180088fda`
- `ntoskrnl!ZwOpenKey` at `0x180088f8f`
- `ntoskrnl!ZwOpenKey` at `0x180088fda`

## string_xrefs

- `0x180088f2d`: `\Registry\Machine\SOFTWARE\Microsoft\Windows\CurrentVersion\AppModel\StateRepository\Cache\Package\Data`

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
0x180088ee8  mov     [rsp-8+arg_10], rbx
0x180088eed  push    rbp
0x180088eee  push    rsi
0x180088eef  push    rdi
0x180088ef0  lea     rbp, [rsp-0C0h]
0x180088ef8  sub     rsp, 1C0h
0x180088eff  mov     rax, cs:__security_cookie
0x180088f06  xor     rax, rsp
0x180088f09  mov     [rbp+0D0h+var_20], rax
0x180088f10  xor     eax, eax
0x180088f12  mov     qword ptr [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x180088f1b  mov     [rsp+1D0h+KeyHandle], rax
0x180088f20  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x180088f25  mov     [rsp+1D0h+Handle], rax
0x180088f2a  mov     rdi, rdx
0x180088f2d  lea     rax, aRegistryMachin_24; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180088f34  mov     qword ptr [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x180088f3c  mov     [rsp+1D0h+var_180], rax
0x180088f41  mov     rsi, rcx
0x180088f44  lea     rax, aPackagefullnam; "PackageFullName"
0x180088f4b  mov     [rsp+1D0h+var_188], 0D000CEh
0x180088f54  mov     [rsp+1D0h+ValueName.Buffer], rax
0x180088f59  lea     rcx, [rsp+1D0h+KeyHandle]; KeyHandle
0x180088f5e  lea     rax, [rsp+1D0h+var_188]
0x180088f63  mov     qword ptr [rsp+1D0h+ValueName.Length], 20001Eh
0x180088f6c  xorps   xmm0, xmm0
0x180088f6f  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rax
0x180088f74  mov     edx, 20019h; DesiredAccess
0x180088f79  mov     [rsp+1D0h+var_1A0], 110h
0x180088f81  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], 0
0x180088f8a  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088f8f  call    cs:__imp_ZwOpenKey
0x180088f96  nop     dword ptr [rax+rax+00h]
0x180088f9b  mov     ebx, eax
0x180088f9d  test    eax, eax
0x180088f9f  js      loc_180089066
0x180088fa5  mov     rax, [rsp+1D0h+KeyHandle]
0x180088faa  lea     r8, [rsp+1D0h+ObjectAttributes]; ObjectAttributes
0x180088faf  xorps   xmm0, xmm0
0x180088fb2  mov     [rsp+1D0h+ObjectAttributes.RootDirectory], rax
0x180088fb7  mov     edx, 20019h; DesiredAccess
0x180088fbc  mov     [rsp+1D0h+ObjectAttributes.Length], 30h ; '0'
0x180088fc4  lea     rcx, [rsp+1D0h+Handle]; KeyHandle
0x180088fc9  mov     [rbp+0D0h+ObjectAttributes.Attributes], 240h
0x180088fd0  movdqu  xmmword ptr [rbp+0D0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180088fd5  mov     [rsp+1D0h+ObjectAttributes.ObjectName], rsi
0x180088fda  call    cs:__imp_ZwOpenKey
0x180088fe1  nop     dword ptr [rax+rax+00h]
0x180088fe6  mov     ebx, eax
0x180088fe8  test    eax, eax
0x180088fea  js      short loc_180089066
0x180088fec  mov     rcx, [rsp+1D0h+Handle]; KeyHandle
0x180088ff1  lea     rax, [rsp+1D0h+var_1A0]
0x180088ff6  mov     [rsp+1D0h+ResultLength], rax; ResultLength
0x180088ffb  lea     r9, [rbp+0D0h+KeyValueInformation]; KeyValueInformation
0x180088fff  mov     eax, [rsp+1D0h+var_1A0]
0x180089003  lea     rdx, [rsp+1D0h+ValueName]; ValueName
0x180089008  mov     esi, 2
0x18008900d  mov     [rsp+1D0h+Length], eax; Length
0x180089011  mov     r8d, esi; KeyValueInformationClass
0x180089014  call    cs:__imp_ZwQueryValueKey
0x18008901b  nop     dword ptr [rax+rax+00h]
0x180089020  mov     ebx, eax
0x180089022  test    eax, eax
0x180089024  js      short loc_180089066
0x180089026  cmp     [rbp+0D0h+var_12C], 1
0x18008902a  jnz     short loc_180089061
0x18008902c  mov     ecx, [rbp+0D0h+var_128]
0x18008902f  cmp     ecx, esi
0x180089031  jb      short loc_180089061
0x180089033  movzx   eax, word ptr [rdi+2]
0x180089037  cmp     eax, ecx
0x180089039  jnb     short loc_180089042
0x18008903b  mov     ebx, 0C0000023h
0x180089040  jmp     short loc_180089066
0x180089042  mov     r8, rcx
0x180089045  lea     rdx, [rbp+0D0h+Src]; Src
0x180089049  mov     rcx, [rdi+8]; void *
0x18008904d  sub     r8, rsi; Size
0x180089050  call    memmove
0x180089055  movzx   eax, word ptr [rbp+0D0h+var_128]
0x180089059  sub     ax, si
0x18008905c  mov     [rdi], ax
0x18008905f  jmp     short loc_180089066
0x180089061  mov     ebx, 0C0000024h
0x180089066  mov     rcx, [rsp+1D0h+Handle]; Handle
0x18008906b  test    rcx, rcx
0x18008906e  jz      short loc_18008907C
0x180089070  call    cs:__imp_ZwClose
0x180089077  nop     dword ptr [rax+rax+00h]
0x18008907c  mov     rcx, [rsp+1D0h+KeyHandle]; Handle
0x180089081  test    rcx, rcx
0x180089084  jz      short loc_180089092
0x180089086  call    cs:__imp_ZwClose
0x18008908d  nop     dword ptr [rax+rax+00h]
0x180089092  mov     eax, ebx
0x180089094  mov     rcx, [rbp+0D0h+var_20]
0x18008909b  xor     rcx, rsp; StackCookie
0x18008909e  call    __security_check_cookie
0x1800890a3  mov     rbx, [rsp+1D0h+arg_10]
0x1800890ab  add     rsp, 1C0h
0x1800890b2  pop     rdi
0x1800890b3  pop     rsi
0x1800890b4  pop     rbp
0x1800890b5  retn
```
