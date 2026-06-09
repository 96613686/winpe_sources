# KmWlanStateSeparation_GetMutableRegistryKey

- ea: `0x140055e6c`
- end: `0x1400560d7`
- name: `KmWlanStateSeparation_GetMutableRegistryKey`
- size: `619`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036c48`

## callees

- `0x140055e6c`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005609b`
- `ntoskrnl!ZwClose` at `0x14005609b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055f5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055fce`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055f5e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140055fce`
- `ntoskrnl!wcscpy_s` at `0x140055f1d`
- `ntoskrnl!wcscpy_s` at `0x140056018`
- `ntoskrnl!wcscpy_s` at `0x140056037`
- `ntoskrnl!wcscpy_s` at `0x140055f1d`
- `ntoskrnl!wcscpy_s` at `0x140056018`
- `ntoskrnl!wcscpy_s` at `0x140056037`
- `ntoskrnl!wcscat_s` at `0x140055f40`
- `ntoskrnl!wcscat_s` at `0x14005606e`
- `ntoskrnl!wcscat_s` at `0x140056083`
- `ntoskrnl!wcscat_s` at `0x140055f40`
- `ntoskrnl!wcscat_s` at `0x14005606e`
- `ntoskrnl!wcscat_s` at `0x140056083`
- `ntoskrnl!ZwQueryValueKey` at `0x140055ffe`
- `ntoskrnl!ZwQueryValueKey` at `0x140055ffe`
- `ntoskrnl!ZwOpenKey` at `0x140055fa4`
- `ntoskrnl!ZwOpenKey` at `0x140055fa4`

## string_xrefs

- `0x140055e98`: `\REGISTRY\MACHINE\`
- `0x140055fba`: `RedirectedRegistryRoot`

## pseudocode

```c
__int64 __fastcall KmWlanStateSeparation_GetMutableRegistryKey(
        wchar_t *SourceString,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  errno_t v6; // ebx
  wchar_t *v7; // rdi
  __int64 v8; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-B0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t KeyValueInformation[272]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Src[20]; // [rsp+2B0h] [rbp+1B0h] BYREF

  wcscpy(Src, L"\\REGISTRY\\MACHNE\\");
  KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ValueName = 0;
  memset(KeyValueInformation, 0, 0x218u);
  if ( !SourceString )
    return 87;
  v6 = wcscpy_s(SourceString, 0x104u, Src);
  if ( !v6 )
  {
    v6 = wcscat_s(SourceString, 0x104u, L"Software\\Microsoft\\Wlansvc");
    if ( !v6 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      v7 = SourceString + 18;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        ResultLength = 484;
        RtlInitUnicodeString(&ValueName, L"RedirectedRegistryRoot");
        if ( ZwQueryValueKey(
               KeyHandle,
               &ValueName,
               KeyValuePartialInformation,
               KeyValueInformation,
               0x218u,
               &ResultLength) >= 0 )
        {
          v6 = wcscpy_s(v7, 0xF2u, &KeyValueInformation[6]);
          if ( v6 >= 0 )
            goto LABEL_11;
        }
      }
      v6 = wcscpy_s(v7, 0xF2u, L"Software\\Microsoft\\Wlansvc");
      if ( v6 >= 0 )
      {
LABEL_11:
        if ( a4 )
        {
          v8 = -1;
          do
            ++v8;
          while ( a4[v8] );
          if ( v8 )
          {
            wcscat_s(v7, 0xF2u, L"\\");
            v6 = wcscat_s(v7, 0xF2u, a4);
          }
        }
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140055e6c  mov     [rsp-8+arg_8], rbx
0x140055e71  push    rbp
0x140055e72  push    rsi
0x140055e73  push    rdi
0x140055e74  push    r14
0x140055e76  push    r15
0x140055e78  lea     rbp, [rsp-1E0h]
0x140055e80  sub     rsp, 2E0h
0x140055e87  mov     rax, cs:__security_cookie
0x140055e8e  xor     rax, rsp
0x140055e91  mov     [rbp+200h+var_28], rax
0x140055e98  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\REGISTRY\\MACHINE\\"
0x140055e9f  mov     rdi, rcx
0x140055ea2  xor     r14d, r14d
0x140055ea5  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "Y\\MACHINE\\"
0x140055eac  xor     edx, edx; Val
0x140055eae  mov     r8d, 218h; Size
0x140055eb4  movups  xmmword ptr [rbp+200h+Src], xmm0
0x140055ebb  lea     rcx, [rbp+200h+KeyValueInformation]; void *
0x140055ebf  mov     rsi, r9
0x140055ec2  movsd   xmm0, qword ptr cs:aRegistryMachin+1Eh; "NE\\"
0x140055eca  movups  [rbp+200h+var_40], xmm1
0x140055ed1  mov     [rsp+300h+KeyHandle], r14
0x140055ed6  xorps   xmm1, xmm1
0x140055ed9  movsd   qword ptr [rbp+200h+var_40+0Eh], xmm0
0x140055ee1  xorps   xmm0, xmm0
0x140055ee4  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x140055ee9  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm1
0x140055eee  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm1
0x140055ef3  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm1
0x140055ef7  movups  xmmword ptr [rsp+300h+ValueName.Length], xmm1
0x140055efc  call    memset
0x140055f01  test    rdi, rdi
0x140055f04  jz      loc_1400560AB
0x140055f0a  mov     r15d, 104h
0x140055f10  lea     r8, [rbp+200h+Src]; Src
0x140055f17  mov     edx, r15d; SizeInWords
0x140055f1a  mov     rcx, rdi; Dst
0x140055f1d  call    cs:__imp_wcscpy_s
0x140055f24  nop     dword ptr [rax+rax+00h]
0x140055f29  mov     ebx, eax
0x140055f2b  test    eax, eax
0x140055f2d  jnz     loc_140056091
0x140055f33  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x140055f3a  mov     edx, r15d; SizeInWords
0x140055f3d  mov     rcx, rdi; Dst
0x140055f40  call    cs:__imp_wcscat_s
0x140055f47  nop     dword ptr [rax+rax+00h]
0x140055f4c  mov     ebx, eax
0x140055f4e  test    eax, eax
0x140055f50  jnz     loc_140056091
0x140055f56  mov     rdx, rdi; SourceString
0x140055f59  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x140055f5e  call    cs:__imp_RtlInitUnicodeString
0x140055f65  nop     dword ptr [rax+rax+00h]
0x140055f6a  lea     rax, [rsp+300h+DestinationString]
0x140055f6f  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x140055f77  xorps   xmm0, xmm0
0x140055f7a  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x140055f7f  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x140055f84  mov     [rsp+300h+ObjectAttributes.RootDirectory], r14
0x140055f89  mov     edx, 20019h; DesiredAccess
0x140055f8e  mov     [rsp+300h+ObjectAttributes.Attributes], 240h
0x140055f96  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140055f9b  add     rdi, 24h ; '$'
0x140055f9f  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x140055fa4  call    cs:__imp_ZwOpenKey
0x140055fab  nop     dword ptr [rax+rax+00h]
0x140055fb0  mov     r15d, 0F2h
0x140055fb6  test    eax, eax
0x140055fb8  js      short loc_14005602A
0x140055fba  lea     rdx, aRedirectedregi; "RedirectedRegistryRoot"
0x140055fc1  mov     [rsp+300h+var_2D0], 1E4h
0x140055fc9  lea     rcx, [rsp+300h+ValueName]; DestinationString
0x140055fce  call    cs:__imp_RtlInitUnicodeString
0x140055fd5  nop     dword ptr [rax+rax+00h]
0x140055fda  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x140055fdf  lea     rax, [rsp+300h+var_2D0]
0x140055fe4  mov     [rsp+300h+ResultLength], rax; ResultLength
0x140055fe9  lea     r9, [rbp+200h+KeyValueInformation]; KeyValueInformation
0x140055fed  lea     r8d, [r14+2]; KeyValueInformationClass
0x140055ff1  mov     [rsp+300h+Length], 218h; Length
0x140055ff9  lea     rdx, [rsp+300h+ValueName]; ValueName
0x140055ffe  call    cs:__imp_ZwQueryValueKey
0x140056005  nop     dword ptr [rax+rax+00h]
0x14005600a  test    eax, eax
0x14005600c  js      short loc_14005602A
0x14005600e  lea     r8, [rbp+200h+var_264]; Src
0x140056012  mov     edx, r15d; SizeInWords
0x140056015  mov     rcx, rdi; Dst
0x140056018  call    cs:__imp_wcscpy_s
0x14005601f  nop     dword ptr [rax+rax+00h]
0x140056024  mov     ebx, eax
0x140056026  test    eax, eax
0x140056028  jns     short loc_140056049
0x14005602a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x140056031  mov     rdx, r15; SizeInWords
0x140056034  mov     rcx, rdi; Dst
0x140056037  call    cs:__imp_wcscpy_s
0x14005603e  nop     dword ptr [rax+rax+00h]
0x140056043  mov     ebx, eax
0x140056045  test    eax, eax
0x140056047  js      short loc_140056091
0x140056049  test    rsi, rsi
0x14005604c  jz      short loc_140056091
0x14005604e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140056052  inc     rax
0x140056055  cmp     [rsi+rax*2], r14w
0x14005605a  jnz     short loc_140056052
0x14005605c  test    rax, rax
0x14005605f  jz      short loc_140056091
0x140056061  lea     r8, asc_14009FDE0; "\\"
0x140056068  mov     rdx, r15; SizeInWords
0x14005606b  mov     rcx, rdi; Dst
0x14005606e  call    cs:__imp_wcscat_s
0x140056075  nop     dword ptr [rax+rax+00h]
0x14005607a  mov     r8, rsi; Src
0x14005607d  mov     rdx, r15; SizeInWords
0x140056080  mov     rcx, rdi; Dst
0x140056083  call    cs:__imp_wcscat_s
0x14005608a  nop     dword ptr [rax+rax+00h]
0x14005608f  mov     ebx, eax
0x140056091  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x140056096  test    rcx, rcx
0x140056099  jz      short loc_1400560A7
0x14005609b  call    cs:__imp_ZwClose
0x1400560a2  nop     dword ptr [rax+rax+00h]
0x1400560a7  mov     eax, ebx
0x1400560a9  jmp     short loc_1400560B0
0x1400560ab  mov     eax, 57h ; 'W'
0x1400560b0  mov     rcx, [rbp+200h+var_28]
0x1400560b7  xor     rcx, rsp; StackCookie
0x1400560ba  call    __security_check_cookie
0x1400560bf  mov     rbx, [rsp+300h+arg_8]
0x1400560c7  add     rsp, 2E0h
0x1400560ce  pop     r15
0x1400560d0  pop     r14
0x1400560d2  pop     rdi
0x1400560d3  pop     rsi
0x1400560d4  pop     rbp
0x1400560d5  retn
```
