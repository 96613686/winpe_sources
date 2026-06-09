# KappxGetPackageSidFromPackageFamilyNameInRegistry

- ea: `0x1400113e0`
- end: `0x1400117ff`
- name: `KappxGetPackageSidFromPackageFamilyNameInRegistry`
- size: `1055`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140011350`

## callees

- `0x140001010`
- `0x140003640`
- `0x1400113e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140011510`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011510`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400115ac`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400115ac`
- `ntoskrnl!ZwQueryValueKey` at `0x140011622`
- `ntoskrnl!ZwQueryValueKey` at `0x140011721`
- `ntoskrnl!ZwQueryValueKey` at `0x140011622`
- `ntoskrnl!ZwQueryValueKey` at `0x140011721`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011683`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400116ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400117ee`
- `ntoskrnl!ExAllocatePool2` at `0x140011462`
- `ntoskrnl!ExAllocatePool2` at `0x140011537`
- `ntoskrnl!ExAllocatePool2` at `0x140011645`
- `ntoskrnl!ExAllocatePool2` at `0x140011777`
- `ntoskrnl!ExAllocatePool2` at `0x140011462`
- `ntoskrnl!ExAllocatePool2` at `0x140011537`
- `ntoskrnl!ExAllocatePool2` at `0x140011645`
- `ntoskrnl!ExAllocatePool2` at `0x140011777`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400114a8`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400114a8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001156e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001158b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001156e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001158b`
- `ntoskrnl!ZwOpenKey` at `0x1400115f1`
- `ntoskrnl!ZwOpenKey` at `0x1400115f1`
- `ntoskrnl!ZwClose` at `0x1400117c2`
- `ntoskrnl!ZwClose` at `0x1400117c2`

## string_xrefs

- `0x1400113fd`: `PackageSid`
- `0x140011495`: `TargetNtPath`
- `0x14001149c`: `AppxPackageSidRef`
- `0x140011486`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Appx\PackageSidRef`

## pseudocode

```c
__int64 __fastcall KappxGetPackageSidFromPackageFamilyNameInRegistry(PCUNICODE_STRING Source, wchar_t **a2)
{
  _DWORD *v4; // r14
  wchar_t *v5; // r15
  WCHAR *Pool2; // rdi
  NTSTATUS PersistedStateLocation; // ebx
  __int64 v8; // rcx
  WCHAR *v9; // rax
  unsigned int v10; // ebx
  WCHAR *v11; // rax
  unsigned int v13; // ecx
  wchar_t *v14; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-39h] BYREF
  UNICODE_STRING Sourcea; // [rsp+58h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-9h] BYREF
  ULONG ResultLength; // [rsp+E8h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+F8h] [rbp+77h] BYREF

  ValueName.Buffer = L"PackageSid";
  *(_QWORD *)&ValueName.Length = 1441812;
  v4 = 0;
  KeyHandle = 0;
  v5 = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  Sourcea = 0;
  if ( Source->Length )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(256, 522, 1483763777);
    if ( Pool2 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"AppxPackageSidRef",
                                 L"TargetNtPath",
                                 L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Appx\\PackageSidRef",
                                 0,
                                 Pool2,
                                 522,
                                 &ResultLength);
      if ( PersistedStateLocation >= 0 )
      {
        v8 = 0x7FFF;
        Sourcea = 0;
        v9 = Pool2;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v8;
        }
        while ( v8 );
        PersistedStateLocation = -1073741811;
        if ( v8 )
        {
          Sourcea.Buffer = Pool2;
          Sourcea.Length = -2 - 2 * v8;
          Sourcea.MaximumLength = -2 * v8;
          RtlInitUnicodeString(&DestinationString, 0);
          v10 = (unsigned __int16)(Source->Length + Sourcea.Length + 2);
          v11 = (WCHAR *)ExAllocatePool2(256, (unsigned __int16)(Source->Length + Sourcea.Length + 2), 1483763777);
          DestinationString.Buffer = v11;
          if ( v11 )
          {
            memset(v11, 0, v10);
            DestinationString.Length = 0;
            DestinationString.MaximumLength = v10;
            PersistedStateLocation = RtlAppendUnicodeStringToString(&DestinationString, &Sourcea);
            if ( PersistedStateLocation >= 0 )
            {
              PersistedStateLocation = RtlAppendUnicodeStringToString(&DestinationString, Source);
              if ( PersistedStateLocation >= 0 )
              {
                PersistedStateLocation = RtlAppendUnicodeToString(&DestinationString, &::Source);
                if ( PersistedStateLocation >= 0 )
                {
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.ObjectName = &DestinationString;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 576;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  PersistedStateLocation = ZwOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes);
                  if ( PersistedStateLocation >= 0 )
                  {
                    PersistedStateLocation = ZwQueryValueKey(
                                               KeyHandle,
                                               &ValueName,
                                               KeyValueFullInformation,
                                               0,
                                               0,
                                               &ResultLength);
                    if ( PersistedStateLocation == -1073741789 )
                    {
                      v4 = (_DWORD *)ExAllocatePool2(256, ResultLength, 1483763777);
                      if ( v4 )
                      {
                        PersistedStateLocation = ZwQueryValueKey(
                                                   KeyHandle,
                                                   &ValueName,
                                                   KeyValueFullInformation,
                                                   v4,
                                                   ResultLength,
                                                   &ResultLength);
                        if ( PersistedStateLocation >= 0 )
                        {
                          if ( v4[1] == 1 && (v13 = v4[3], v13 >= 4)
                            || (v13 = v4[3], *(_WORD *)((char *)v4 + v4[2] + v13 - 2)) )
                          {
                            v14 = (wchar_t *)ExAllocatePool2(256, v13 + 2LL, 1483763777);
                            v5 = v14;
                            if ( v14 )
                            {
                              PersistedStateLocation = RtlStringCbCopyNW(
                                                         v14,
                                                         (unsigned int)v4[3] + 2LL,
                                                         (STRSAFE_PCNZWCH)((char *)v4 + (unsigned int)v4[2]),
                                                         (unsigned int)v4[3]);
                              if ( PersistedStateLocation >= 0 )
                              {
                                *a2 = v5;
                                v5 = 0;
                              }
                            }
                            else
                            {
                              PersistedStateLocation = -1073741801;
                            }
                          }
                          else
                          {
                            PersistedStateLocation = -1073739509;
                          }
                        }
                      }
                      else
                      {
                        PersistedStateLocation = -1073741801;
                      }
                    }
                  }
                }
              }
            }
          }
          else
          {
            PersistedStateLocation = -1073741801;
          }
        }
      }
    }
    else
    {
      PersistedStateLocation = -1073741801;
    }
    if ( KeyHandle )
      ZwClose(KeyHandle);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x58707041u);
  }
  else
  {
    PersistedStateLocation = -1073741772;
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x1400113e0  mov     r11, rsp
0x1400113e3  push    rbp
0x1400113e4  push    rbx
0x1400113e5  push    r14
0x1400113e7  lea     rbp, [r11-5Fh]
0x1400113eb  sub     rsp, 0C0h
0x1400113f2  xorps   xmm0, xmm0
0x1400113f5  mov     [r11+10h], rsi
0x1400113f9  mov     [r11-28h], r12
0x1400113fd  lea     rax, aPackagesid; "PackageSid"
0x140011404  mov     [r11-30h], r13
0x140011408  mov     r12, rdx
0x14001140b  xor     r13d, r13d
0x14001140e  mov     [rbp+57h+ValueName.Buffer], rax
0x140011412  xor     eax, eax
0x140011414  mov     [r11-38h], r15
0x140011418  mov     rsi, rcx
0x14001141b  mov     qword ptr [rbp+57h+ValueName.Length], 160014h
0x140011423  mov     r14d, r13d
0x140011426  mov     [rbp+57h+KeyHandle], r13
0x14001142a  mov     r15d, r13d
0x14001142d  mov     [rbp+57h+arg_0], r13d
0x140011431  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140011435  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140011439  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14001143d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140011441  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140011445  cmp     [rcx], ax
0x140011448  jz      loc_1400116EF
0x14001144e  mov     edx, 20Ah
0x140011453  mov     [r11-20h], rdi
0x140011457  mov     ecx, 100h
0x14001145c  mov     r8d, 58707041h
0x140011462  call    cs:__imp_ExAllocatePool2
0x140011469  nop     dword ptr [rax+rax+00h]
0x14001146e  mov     rdi, rax
0x140011471  test    rax, rax
0x140011474  jz      loc_1400116F6
0x14001147a  lea     rax, [rbp+57h+arg_0]
0x14001147e  xor     r9d, r9d
0x140011481  mov     [rsp+30h], rax
0x140011486  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\Software\\Microsof"...
0x14001148d  mov     dword ptr [rsp+0D0h+ResultLength], 20Ah
0x140011495  lea     rdx, aTargetntpath; "TargetNtPath"
0x14001149c  lea     rcx, aAppxpackagesid; "AppxPackageSidRef"
0x1400114a3  mov     qword ptr [rsp+0D0h+Length], rdi
0x1400114a8  call    cs:__imp_RtlGetPersistedStateLocation
0x1400114af  nop     dword ptr [rax+rax+00h]
0x1400114b4  mov     ebx, eax
0x1400114b6  test    eax, eax
0x1400114b8  js      loc_140011669
0x1400114be  xorps   xmm0, xmm0
0x1400114c1  mov     ecx, 7FFFh
0x1400114c6  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x1400114ca  mov     rax, rdi
0x1400114cd  cmp     [rax], r13w
0x1400114d1  jz      short loc_1400114DD
0x1400114d3  add     rax, 2
0x1400114d7  sub     rcx, 1
0x1400114db  jnz     short loc_1400114CD
0x1400114dd  test    rcx, rcx
0x1400114e0  mov     ebx, 0C000000Dh
0x1400114e5  cmovnz  ebx, r13d
0x1400114e9  jz      loc_140011669
0x1400114ef  add     cx, cx
0x1400114f2  mov     [rbp+57h+Source.Buffer], rdi
0x1400114f6  mov     eax, 0FFFEh
0x1400114fb  xor     edx, edx; SourceString
0x1400114fd  sub     ax, cx
0x140011500  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140011504  mov     [rbp+57h+Source.Length], ax
0x140011508  add     ax, 2
0x14001150c  mov     [rbp+57h+Source.MaximumLength], ax
0x140011510  call    cs:__imp_RtlInitUnicodeString
0x140011517  nop     dword ptr [rax+rax+00h]
0x14001151c  movzx   eax, [rbp+57h+Source.Length]
0x140011520  mov     r8d, 58707041h
0x140011526  add     ax, 2
0x14001152a  mov     ecx, 100h
0x14001152f  add     ax, [rsi]
0x140011532  movzx   ebx, ax
0x140011535  mov     edx, ebx
0x140011537  call    cs:__imp_ExAllocatePool2
0x14001153e  nop     dword ptr [rax+rax+00h]
0x140011543  mov     [rbp+57h+DestinationString.Buffer], rax
0x140011547  test    rax, rax
0x14001154a  jz      loc_140011664
0x140011550  mov     r8d, ebx; Size
0x140011553  xor     edx, edx; Val
0x140011555  mov     rcx, rax; void *
0x140011558  call    memset
0x14001155d  lea     rdx, [rbp+57h+Source]; Source
0x140011561  mov     [rbp+57h+DestinationString.Length], r13w
0x140011566  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14001156a  mov     [rbp+57h+DestinationString.MaximumLength], bx
0x14001156e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140011575  nop     dword ptr [rax+rax+00h]
0x14001157a  mov     ebx, eax
0x14001157c  test    eax, eax
0x14001157e  js      loc_140011669
0x140011584  mov     rdx, rsi; Source
0x140011587  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14001158b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140011592  nop     dword ptr [rax+rax+00h]
0x140011597  mov     ebx, eax
0x140011599  test    eax, eax
0x14001159b  js      loc_140011669
0x1400115a1  lea     rdx, Source; Source
0x1400115a8  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400115ac  call    cs:__imp_RtlAppendUnicodeToString
0x1400115b3  nop     dword ptr [rax+rax+00h]
0x1400115b8  mov     ebx, eax
0x1400115ba  test    eax, eax
0x1400115bc  js      loc_140011669
0x1400115c2  lea     rax, [rbp+57h+DestinationString]
0x1400115c6  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400115cd  xorps   xmm0, xmm0
0x1400115d0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400115d4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400115d8  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x1400115dc  mov     edx, 2000000h; DesiredAccess
0x1400115e1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400115e8  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400115ec  movdqu  xmmword ptr [rbp+17h], xmm0
0x1400115f1  call    cs:__imp_ZwOpenKey
0x1400115f8  nop     dword ptr [rax+rax+00h]
0x1400115fd  mov     ebx, eax
0x1400115ff  test    eax, eax
0x140011601  js      short loc_140011669
0x140011603  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011607  lea     rax, [rbp+57h+arg_0]
0x14001160b  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x140011610  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140011614  xor     r9d, r9d; KeyValueInformation
0x140011617  mov     [rsp+0D0h+Length], r13d; Length
0x14001161c  mov     r8d, 1; KeyValueInformationClass
0x140011622  call    cs:__imp_ZwQueryValueKey
0x140011629  nop     dword ptr [rax+rax+00h]
0x14001162e  mov     ebx, eax
0x140011630  cmp     eax, 0C0000023h
0x140011635  jnz     short loc_140011669
0x140011637  mov     edx, [rbp+57h+arg_0]
0x14001163a  mov     ecx, 100h
0x14001163f  mov     r8d, 58707041h
0x140011645  call    cs:__imp_ExAllocatePool2
0x14001164c  nop     dword ptr [rax+rax+00h]
0x140011651  mov     r14, rax
0x140011654  test    rax, rax
0x140011657  jnz     loc_140011700
0x14001165d  mov     ebx, 0C0000017h
0x140011662  jmp     short loc_140011669
0x140011664  mov     ebx, 0C0000017h
0x140011669  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14001166d  test    rcx, rcx
0x140011670  jnz     loc_1400117C2
0x140011676  test    rdi, rdi
0x140011679  jz      short loc_14001168F
0x14001167b  mov     edx, 58707041h; Tag
0x140011680  mov     rcx, rdi; P
0x140011683  call    cs:__imp_ExFreePoolWithTag
0x14001168a  nop     dword ptr [rax+rax+00h]
0x14001168f  mov     rdi, [rsp+0B8h]
0x140011697  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14001169b  mov     r13, [rsp+0D0h+var_28]
0x1400116a3  mov     r12, [rsp+0D0h+var_20]
0x1400116ab  mov     rsi, [rsp+0D0h+arg_8]
0x1400116b3  test    rcx, rcx
0x1400116b6  jz      short loc_1400116C6
0x1400116b8  xor     edx, edx; Tag
0x1400116ba  call    cs:__imp_ExFreePoolWithTag
0x1400116c1  nop     dword ptr [rax+rax+00h]
0x1400116c6  test    r15, r15
0x1400116c9  jnz     loc_1400117D3
0x1400116cf  mov     r15, [rsp+0D0h+var_30]
0x1400116d7  test    r14, r14
0x1400116da  jnz     loc_1400117E9
0x1400116e0  mov     eax, ebx
0x1400116e2  add     rsp, 0C0h
0x1400116e9  pop     r14
0x1400116eb  pop     rbx
0x1400116ec  pop     rbp
0x1400116ed  retn
0x1400116ef  mov     ebx, 0C0000034h
0x1400116f4  jmp     short loc_140011697
0x1400116f6  mov     ebx, 0C0000017h
0x1400116fb  jmp     loc_140011669
0x140011700  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140011704  lea     rax, [rbp+57h+arg_0]
0x140011708  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x14001170d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140011711  mov     eax, [rbp+57h+arg_0]
0x140011714  mov     r9, r14; KeyValueInformation
0x140011717  mov     r8d, 1; KeyValueInformationClass
0x14001171d  mov     [rsp+0D0h+Length], eax; Length
0x140011721  call    cs:__imp_ZwQueryValueKey
0x140011728  nop     dword ptr [rax+rax+00h]
0x14001172d  mov     ebx, eax
0x14001172f  test    eax, eax
0x140011731  js      loc_140011669
0x140011737  cmp     dword ptr [r14+4], 1
0x14001173c  jnz     short loc_140011747
0x14001173e  mov     ecx, [r14+0Ch]
0x140011742  cmp     ecx, 4
0x140011745  jnb     short loc_140011766
0x140011747  mov     edx, [r14+0Ch]
0x14001174b  mov     eax, [r14+8]
0x14001174f  mov     ecx, edx
0x140011751  add     rax, r14
0x140011754  cmp     [rdx+rax-2], r13w
0x14001175a  jnz     short loc_140011766
0x14001175c  mov     ebx, 0C000090Bh
0x140011761  jmp     loc_140011669
0x140011766  mov     edx, ecx
0x140011768  mov     r8d, 58707041h
0x14001176e  add     rdx, 2
0x140011772  mov     ecx, 100h
0x140011777  call    cs:__imp_ExAllocatePool2
0x14001177e  nop     dword ptr [rax+rax+00h]
0x140011783  mov     r15, rax
0x140011786  test    rax, rax
0x140011789  jnz     short loc_140011795
0x14001178b  mov     ebx, 0C0000017h
0x140011790  jmp     loc_140011669
0x140011795  mov     r9d, [r14+0Ch]; cbToCopy
0x140011799  mov     rcx, r15; pszDest
0x14001179c  mov     r8d, [r14+8]
0x1400117a0  add     r8, r14; pszSrc
0x1400117a3  lea     rdx, [r9+2]; cbDest
0x1400117a7  call    RtlStringCbCopyNW
0x1400117ac  mov     ebx, eax
0x1400117ae  test    eax, eax
0x1400117b0  js      loc_140011669
0x1400117b6  mov     [r12], r15
0x1400117ba  mov     r15, r13
0x1400117bd  jmp     loc_140011669
0x1400117c2  call    cs:__imp_ZwClose
0x1400117c9  nop     dword ptr [rax+rax+00h]
0x1400117ce  jmp     loc_140011676
0x1400117d3  xor     edx, edx; Tag
0x1400117d5  mov     rcx, r15; P
0x1400117d8  call    cs:__imp_ExFreePoolWithTag
0x1400117df  nop     dword ptr [rax+rax+00h]
0x1400117e4  jmp     loc_1400116CF
0x1400117e9  xor     edx, edx; Tag
0x1400117eb  mov     rcx, r14; P
0x1400117ee  call    cs:__imp_ExFreePoolWithTag
0x1400117f5  nop     dword ptr [rax+rax+00h]
0x1400117fa  jmp     loc_1400116E0
```
