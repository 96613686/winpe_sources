# KmWlanStateSeparation_GetMutableRegistryKey

- ea: `0x14005768c`
- end: `0x1400578f7`
- name: `KmWlanStateSeparation_GetMutableRegistryKey`
- size: `619`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036e68`

## callees

- `0x14005768c`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400578bb`
- `ntoskrnl!ZwClose` at `0x1400578bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005777e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400577ee`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005777e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400577ee`
- `ntoskrnl!wcscpy_s` at `0x14005773d`
- `ntoskrnl!wcscpy_s` at `0x140057838`
- `ntoskrnl!wcscpy_s` at `0x140057857`
- `ntoskrnl!wcscpy_s` at `0x14005773d`
- `ntoskrnl!wcscpy_s` at `0x140057838`
- `ntoskrnl!wcscpy_s` at `0x140057857`
- `ntoskrnl!wcscat_s` at `0x140057760`
- `ntoskrnl!wcscat_s` at `0x14005788e`
- `ntoskrnl!wcscat_s` at `0x1400578a3`
- `ntoskrnl!wcscat_s` at `0x140057760`
- `ntoskrnl!wcscat_s` at `0x14005788e`
- `ntoskrnl!wcscat_s` at `0x1400578a3`
- `ntoskrnl!ZwQueryValueKey` at `0x14005781e`
- `ntoskrnl!ZwQueryValueKey` at `0x14005781e`
- `ntoskrnl!ZwOpenKey` at `0x1400577c4`
- `ntoskrnl!ZwOpenKey` at `0x1400577c4`

## string_xrefs

- `0x1400576b8`: `\REGISTRY\MACHINE\`
- `0x1400577da`: `RedirectedRegistryRoot`

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
0x14005768c  mov     [rsp-8+arg_8], rbx
0x140057691  push    rbp
0x140057692  push    rsi
0x140057693  push    rdi
0x140057694  push    r14
0x140057696  push    r15
0x140057698  lea     rbp, [rsp-1E0h]
0x1400576a0  sub     rsp, 2E0h
0x1400576a7  mov     rax, cs:__security_cookie
0x1400576ae  xor     rax, rsp
0x1400576b1  mov     [rbp+200h+var_28], rax
0x1400576b8  movups  xmm0, xmmword ptr cs:aRegistryMachin; "\\REGISTRY\\MACHINE\\"
0x1400576bf  mov     rdi, rcx
0x1400576c2  xor     r14d, r14d
0x1400576c5  movups  xmm1, xmmword ptr cs:aRegistryMachin+10h; "Y\\MACHINE\\"
0x1400576cc  xor     edx, edx; Val
0x1400576ce  mov     r8d, 218h; Size
0x1400576d4  movups  xmmword ptr [rbp+200h+Src], xmm0
0x1400576db  lea     rcx, [rbp+200h+KeyValueInformation]; void *
0x1400576df  mov     rsi, r9
0x1400576e2  movsd   xmm0, qword ptr cs:aRegistryMachin+1Eh; "NE\\"
0x1400576ea  movups  [rbp+200h+var_40], xmm1
0x1400576f1  mov     [rsp+300h+KeyHandle], r14
0x1400576f6  xorps   xmm1, xmm1
0x1400576f9  movsd   qword ptr [rbp+200h+var_40+0Eh], xmm0
0x140057701  xorps   xmm0, xmm0
0x140057704  movups  xmmword ptr [rsp+300h+DestinationString.Length], xmm0
0x140057709  movups  xmmword ptr [rsp+300h+ObjectAttributes.Length], xmm1
0x14005770e  movups  xmmword ptr [rsp+300h+ObjectAttributes.ObjectName], xmm1
0x140057713  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm1
0x140057717  movups  xmmword ptr [rsp+300h+ValueName.Length], xmm1
0x14005771c  call    memset
0x140057721  test    rdi, rdi
0x140057724  jz      loc_1400578CB
0x14005772a  mov     r15d, 104h
0x140057730  lea     r8, [rbp+200h+Src]; Src
0x140057737  mov     edx, r15d; SizeInWords
0x14005773a  mov     rcx, rdi; Dst
0x14005773d  call    cs:__imp_wcscpy_s
0x140057744  nop     dword ptr [rax+rax+00h]
0x140057749  mov     ebx, eax
0x14005774b  test    eax, eax
0x14005774d  jnz     loc_1400578B1
0x140057753  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x14005775a  mov     edx, r15d; SizeInWords
0x14005775d  mov     rcx, rdi; Dst
0x140057760  call    cs:__imp_wcscat_s
0x140057767  nop     dword ptr [rax+rax+00h]
0x14005776c  mov     ebx, eax
0x14005776e  test    eax, eax
0x140057770  jnz     loc_1400578B1
0x140057776  mov     rdx, rdi; SourceString
0x140057779  lea     rcx, [rsp+300h+DestinationString]; DestinationString
0x14005777e  call    cs:__imp_RtlInitUnicodeString
0x140057785  nop     dword ptr [rax+rax+00h]
0x14005778a  lea     rax, [rsp+300h+DestinationString]
0x14005778f  mov     [rsp+300h+ObjectAttributes.Length], 30h ; '0'
0x140057797  xorps   xmm0, xmm0
0x14005779a  mov     [rsp+300h+ObjectAttributes.ObjectName], rax
0x14005779f  lea     r8, [rsp+300h+ObjectAttributes]; ObjectAttributes
0x1400577a4  mov     [rsp+300h+ObjectAttributes.RootDirectory], r14
0x1400577a9  mov     edx, 20019h; DesiredAccess
0x1400577ae  mov     [rsp+300h+ObjectAttributes.Attributes], 240h
0x1400577b6  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400577bb  add     rdi, 24h ; '$'
0x1400577bf  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400577c4  call    cs:__imp_ZwOpenKey
0x1400577cb  nop     dword ptr [rax+rax+00h]
0x1400577d0  mov     r15d, 0F2h
0x1400577d6  test    eax, eax
0x1400577d8  js      short loc_14005784A
0x1400577da  lea     rdx, aRedirectedregi; "RedirectedRegistryRoot"
0x1400577e1  mov     [rsp+300h+var_2D0], 1E4h
0x1400577e9  lea     rcx, [rsp+300h+ValueName]; DestinationString
0x1400577ee  call    cs:__imp_RtlInitUnicodeString
0x1400577f5  nop     dword ptr [rax+rax+00h]
0x1400577fa  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1400577ff  lea     rax, [rsp+300h+var_2D0]
0x140057804  mov     [rsp+300h+ResultLength], rax; ResultLength
0x140057809  lea     r9, [rbp+200h+KeyValueInformation]; KeyValueInformation
0x14005780d  lea     r8d, [r14+2]; KeyValueInformationClass
0x140057811  mov     [rsp+300h+Length], 218h; Length
0x140057819  lea     rdx, [rsp+300h+ValueName]; ValueName
0x14005781e  call    cs:__imp_ZwQueryValueKey
0x140057825  nop     dword ptr [rax+rax+00h]
0x14005782a  test    eax, eax
0x14005782c  js      short loc_14005784A
0x14005782e  lea     r8, [rbp+200h+var_264]; Src
0x140057832  mov     edx, r15d; SizeInWords
0x140057835  mov     rcx, rdi; Dst
0x140057838  call    cs:__imp_wcscpy_s
0x14005783f  nop     dword ptr [rax+rax+00h]
0x140057844  mov     ebx, eax
0x140057846  test    eax, eax
0x140057848  jns     short loc_140057869
0x14005784a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Wlansvc"
0x140057851  mov     rdx, r15; SizeInWords
0x140057854  mov     rcx, rdi; Dst
0x140057857  call    cs:__imp_wcscpy_s
0x14005785e  nop     dword ptr [rax+rax+00h]
0x140057863  mov     ebx, eax
0x140057865  test    eax, eax
0x140057867  js      short loc_1400578B1
0x140057869  test    rsi, rsi
0x14005786c  jz      short loc_1400578B1
0x14005786e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140057872  inc     rax
0x140057875  cmp     [rsi+rax*2], r14w
0x14005787a  jnz     short loc_140057872
0x14005787c  test    rax, rax
0x14005787f  jz      short loc_1400578B1
0x140057881  lea     r8, asc_1400A1EE0; "\\"
0x140057888  mov     rdx, r15; SizeInWords
0x14005788b  mov     rcx, rdi; Dst
0x14005788e  call    cs:__imp_wcscat_s
0x140057895  nop     dword ptr [rax+rax+00h]
0x14005789a  mov     r8, rsi; Src
0x14005789d  mov     rdx, r15; SizeInWords
0x1400578a0  mov     rcx, rdi; Dst
0x1400578a3  call    cs:__imp_wcscat_s
0x1400578aa  nop     dword ptr [rax+rax+00h]
0x1400578af  mov     ebx, eax
0x1400578b1  mov     rcx, [rsp+300h+KeyHandle]; Handle
0x1400578b6  test    rcx, rcx
0x1400578b9  jz      short loc_1400578C7
0x1400578bb  call    cs:__imp_ZwClose
0x1400578c2  nop     dword ptr [rax+rax+00h]
0x1400578c7  mov     eax, ebx
0x1400578c9  jmp     short loc_1400578D0
0x1400578cb  mov     eax, 57h ; 'W'
0x1400578d0  mov     rcx, [rbp+200h+var_28]
0x1400578d7  xor     rcx, rsp; StackCookie
0x1400578da  call    __security_check_cookie
0x1400578df  mov     rbx, [rsp+300h+arg_8]
0x1400578e7  add     rsp, 2E0h
0x1400578ee  pop     r15
0x1400578f0  pop     r14
0x1400578f2  pop     rdi
0x1400578f3  pop     rsi
0x1400578f4  pop     rbp
0x1400578f5  retn
```
