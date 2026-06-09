# DfscPolicyReadRegistryParameters

- ea: `0x1400286dc`
- end: `0x140028caf`
- name: `DfscPolicyReadRegistryParameters`
- size: `1491`
- prototype: `int()`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002a488`

## callees

- `0x140005f70`
- `0x140011760`
- `0x1400286dc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140028c56`
- `ntoskrnl!ZwClose` at `0x140028c6c`
- `ntoskrnl!ZwClose` at `0x140028c82`
- `ntoskrnl!ZwClose` at `0x140028c56`
- `ntoskrnl!ZwClose` at `0x140028c6c`
- `ntoskrnl!ZwClose` at `0x140028c82`
- `ntoskrnl!ZwQueryValueKey` at `0x140028886`
- `ntoskrnl!ZwQueryValueKey` at `0x1400288e5`
- `ntoskrnl!ZwQueryValueKey` at `0x140028940`
- `ntoskrnl!ZwQueryValueKey` at `0x1400289b9`
- `ntoskrnl!ZwQueryValueKey` at `0x140028a2c`
- `ntoskrnl!ZwQueryValueKey` at `0x140028aa5`
- `ntoskrnl!ZwQueryValueKey` at `0x140028b18`
- `ntoskrnl!ZwQueryValueKey` at `0x140028b84`
- `ntoskrnl!ZwQueryValueKey` at `0x140028886`
- `ntoskrnl!ZwQueryValueKey` at `0x1400288e5`
- `ntoskrnl!ZwQueryValueKey` at `0x140028940`
- `ntoskrnl!ZwQueryValueKey` at `0x1400289b9`
- `ntoskrnl!ZwQueryValueKey` at `0x140028a2c`
- `ntoskrnl!ZwQueryValueKey` at `0x140028aa5`
- `ntoskrnl!ZwQueryValueKey` at `0x140028b18`
- `ntoskrnl!ZwQueryValueKey` at `0x140028b84`
- `ntoskrnl!RtlGetVersion` at `0x140028742`
- `ntoskrnl!RtlGetVersion` at `0x140028742`
- `ntoskrnl!ZwOpenKey` at `0x1400287b7`
- `ntoskrnl!ZwOpenKey` at `0x140028834`
- `ntoskrnl!ZwOpenKey` at `0x140028c01`
- `ntoskrnl!ZwOpenKey` at `0x1400287b7`
- `ntoskrnl!ZwOpenKey` at `0x140028834`
- `ntoskrnl!ZwOpenKey` at `0x140028c01`

## string_xrefs

- `0x1400289f9`: `MaxReferralCacheKBytes`
- `0x140028a72`: `MaxDomainCacheKBytes`
- `0x140028b51`: `MaxEntriesDeletedPerInterval`
- `0x140028ae5`: `ScavengerThreadIntervalSeconds`
- `0x14002879c`: `\Registry\Machine\System\CurrentControlSet\Services\Mup`

## pseudocode

```c
int DfscPolicyReadRegistryParameters()
{
  int v0; // eax
  int result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  int v3; // [rsp+34h] [rbp-CCh] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v7; // [rsp+58h] [rbp-A8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+90h] [rbp-70h] BYREF
  int v10; // [rsp+94h] [rbp-6Ch]
  __int64 v11; // [rsp+9Ch] [rbp-64h]

  g_OsVersionInfo.dwOSVersionInfoSize = 284;
  Handle = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  KeyHandle = 0;
  v7 = 0;
  v3 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(_DWORD *)(&ValueName.MaximumLength + 1) = 0;
  RtlGetVersion(&g_OsVersionInfo);
  *(_DWORD *)&ValueName.Length = 7209070;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  DWORD1(xmmword_14000C740) = (unsigned __int8)(byte_14000C53A - 2) <= 1u;
  ValueName.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Mup";
  ObjectAttributes.ObjectName = &ValueName;
  if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    ValueName.Buffer = L"DisableDfs";
    *(_DWORD *)&ValueName.Length = 1310740;
    if ( DfscGetUlongRegistryParameter(KeyHandle, &ValueName, &v3) >= 0 )
    {
      if ( v3 )
        LODWORD(xmmword_14000C740) = 1;
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    ValueName.Buffer = L"MaxReferralTTLInSeconds";
    *(_DWORD *)&ValueName.Length = 3014702;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      DWORD2(xmmword_14000C740) = v11;
    }
    ValueName.Buffer = L"MaxDomainTTLInSeconds";
    *(_DWORD *)&ValueName.Length = 2752554;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      HIDWORD(xmmword_14000C740) = v11;
    }
    ValueName.Buffer = L"ReferralTTLMultiplier";
    *(_DWORD *)&ValueName.Length = 2752554;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      HIDWORD(xmmword_14000C750) = v11;
      if ( (_DWORD)v11 )
      {
        if ( (unsigned int)v11 > 0x400 )
          HIDWORD(xmmword_14000C750) = 1024;
      }
      else
      {
        HIDWORD(xmmword_14000C750) = 1;
      }
    }
    ValueName.Buffer = L"DomainTTLMultiplier";
    *(_DWORD *)&ValueName.Length = 2490406;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      LODWORD(xmmword_14000C750) = v11;
      if ( (_DWORD)v11 )
      {
        if ( (unsigned int)v11 > 0x400 )
          LODWORD(xmmword_14000C750) = 1024;
      }
      else
      {
        LODWORD(xmmword_14000C750) = 1;
      }
    }
    ValueName.Buffer = L"MaxReferralCacheKBytes";
    *(_DWORD *)&ValueName.Length = 2883628;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      if ( (_DWORD)v11 << 10 >= (unsigned int)v11 )
      {
        dword_14000C760 = v11;
        if ( (unsigned int)(v11 - 1) <= 0xE )
          dword_14000C760 = 16;
      }
    }
    ValueName.Buffer = L"MaxDomainCacheKBytes";
    *(_DWORD *)&ValueName.Length = 2621480;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      if ( (_DWORD)v11 << 10 >= (unsigned int)v11 )
      {
        dword_14000C764 = v11;
        if ( (unsigned int)(v11 - 1) <= 0xE )
          dword_14000C764 = 16;
      }
    }
    ValueName.Buffer = L"ScavengerThreadIntervalSeconds";
    *(_DWORD *)&ValueName.Length = 3932220;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v3 = v11;
      DWORD1(xmmword_14000C750) = v11;
      if ( (unsigned int)(v11 - 1) <= 0x1C )
        DWORD1(xmmword_14000C750) = 30;
    }
    ValueName.Buffer = L"MaxEntriesDeletedPerInterval";
    *(_DWORD *)&ValueName.Length = 3670072;
    ResultLength = 0;
    if ( ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x60u, &ResultLength) >= 0
      && v10 == 4 )
    {
      v0 = v11;
      if ( !(_DWORD)v11 )
        v0 = 1;
      v3 = v0;
      DWORD2(xmmword_14000C750) = v0;
    }
  }
  result = (int)KeyHandle;
  if ( KeyHandle )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    ValueName.Buffer = L"Parameters";
    *(_DWORD *)&ValueName.Length = 1310740;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &ValueName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = ZwOpenKey(&v7, 0x20019u, &ObjectAttributes);
    if ( result >= 0 )
    {
      ValueName.Buffer = L"EnableDfsLoopbackTargets";
      *(_DWORD *)&ValueName.Length = 3145776;
      result = DfscGetUlongRegistryParameter(v7, &ValueName, &v3);
      if ( result >= 0 )
      {
        result = v3 != 0;
        DWORD1(xmmword_14000C740) = result;
      }
    }
    if ( KeyHandle )
      result = ZwClose(KeyHandle);
  }
  if ( Handle )
    result = ZwClose(Handle);
  if ( v7 )
    return ZwClose(v7);
  return result;
}

```

## disassembly

```asm
0x1400286dc  push    rbp
0x1400286de  push    rbx
0x1400286df  push    rsi
0x1400286e0  push    rdi
0x1400286e1  push    r12
0x1400286e3  push    r13
0x1400286e5  push    r14
0x1400286e7  push    r15
0x1400286e9  lea     rbp, [rsp-8]
0x1400286ee  sub     rsp, 108h
0x1400286f5  mov     rax, cs:__security_cookie
0x1400286fc  xor     rax, rsp
0x1400286ff  mov     [rbp+40h+var_50], rax
0x140028703  xorps   xmm0, xmm0
0x140028706  mov     cs:g_OsVersionInfo.dwOSVersionInfoSize, 11Ch
0x140028710  xor     ebx, ebx
0x140028712  lea     rcx, g_OsVersionInfo; lpVersionInformation
0x140028719  movups  xmmword ptr [rsp+140h+ObjectAttributes.ObjectName], xmm0
0x14002871e  xor     eax, eax
0x140028720  mov     [rsp+140h+Handle], rbx
0x140028725  movups  xmmword ptr [rsp+140h+ObjectAttributes+1Ch], xmm0
0x14002872a  mov     [rsp+140h+KeyHandle], rbx
0x14002872f  mov     [rsp+140h+var_E8], rbx
0x140028734  mov     [rsp+140h+var_10C], ebx
0x140028738  movups  xmmword ptr [rsp+140h+ObjectAttributes.Length], xmm0
0x14002873d  movups  xmmword ptr [rsp+140h+ValueName.Length], xmm0
0x140028742  call    cs:__imp_RtlGetVersion
0x140028749  nop     dword ptr [rax+rax+00h]
0x14002874e  mov     cl, cs:byte_14000C53A
0x140028754  lea     r12d, [rbx+2]
0x140028758  sub     cl, r12b
0x14002875b  mov     dword ptr [rsp+140h+ValueName.Length], 6E006Eh
0x140028763  mov     eax, ebx
0x140028765  mov     [rsp+140h+ObjectAttributes.RootDirectory], rbx
0x14002876a  xorps   xmm0, xmm0
0x14002876d  mov     [rsp+140h+ObjectAttributes.Attributes], 240h
0x140028775  lea     esi, [rbx+1]
0x140028778  mov     edx, 20019h; DesiredAccess
0x14002877d  cmp     cl, sil
0x140028780  lea     r13d, [rbx+30h]
0x140028784  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140028789  mov     [rsp+140h+ObjectAttributes.Length], r13d
0x14002878e  setbe   al
0x140028791  lea     rcx, [rsp+140h+KeyHandle]; KeyHandle
0x140028796  mov     dword ptr cs:xmmword_14000C740+4, eax
0x14002879c  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400287a3  mov     [rsp+140h+ValueName.Buffer], rax
0x1400287a8  lea     rax, [rsp+140h+ValueName]
0x1400287ad  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x1400287b2  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400287b7  call    cs:__imp_ZwOpenKey
0x1400287be  nop     dword ptr [rax+rax+00h]
0x1400287c3  test    eax, eax
0x1400287c5  js      short loc_1400287FF
0x1400287c7  mov     rcx, [rsp+140h+KeyHandle]
0x1400287cc  lea     rax, aDisabledfs; "DisableDfs"
0x1400287d3  lea     r8, [rsp+140h+var_10C]
0x1400287d8  mov     [rsp+140h+ValueName.Buffer], rax
0x1400287dd  lea     rdx, [rsp+140h+ValueName]
0x1400287e2  mov     dword ptr [rsp+140h+ValueName.Length], 140014h
0x1400287ea  call    DfscGetUlongRegistryParameter
0x1400287ef  test    eax, eax
0x1400287f1  js      short loc_1400287FF
0x1400287f3  cmp     [rsp+140h+var_10C], ebx
0x1400287f7  jz      short loc_1400287FF
0x1400287f9  mov     dword ptr cs:xmmword_14000C740, esi
0x1400287ff  lea     rax, Destination
0x140028806  mov     [rsp+140h+ObjectAttributes.Length], r13d
0x14002880b  xorps   xmm0, xmm0
0x14002880e  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x140028813  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140028818  mov     [rsp+140h+ObjectAttributes.RootDirectory], rbx
0x14002881d  mov     edx, 20019h; DesiredAccess
0x140028822  mov     [rsp+140h+ObjectAttributes.Attributes], 240h
0x14002882a  lea     rcx, [rsp+140h+Handle]; KeyHandle
0x14002882f  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028834  call    cs:__imp_ZwOpenKey
0x14002883b  nop     dword ptr [rax+rax+00h]
0x140028840  test    eax, eax
0x140028842  js      loc_140028BAC
0x140028848  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x14002884d  lea     rax, aMaxreferralttl; "MaxReferralTTLInSeconds"
0x140028854  mov     [rsp+140h+ValueName.Buffer], rax
0x140028859  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x14002885d  lea     rax, [rsp+140h+var_110]
0x140028862  mov     dword ptr [rsp+140h+ValueName.Length], 2E002Eh
0x14002886a  mov     [rsp+140h+ResultLength], rax; ResultLength
0x14002886f  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028874  mov     r15d, 60h ; '`'
0x14002887a  mov     [rsp+140h+var_110], ebx
0x14002887e  mov     r8d, r12d; KeyValueInformationClass
0x140028881  mov     [rsp+140h+Length], r15d; Length
0x140028886  call    cs:__imp_ZwQueryValueKey
0x14002888d  nop     dword ptr [rax+rax+00h]
0x140028892  lea     edi, [r15-5Ch]
0x140028896  test    eax, eax
0x140028898  js      short loc_1400288AD
0x14002889a  cmp     [rbp+40h+var_AC], edi
0x14002889d  jnz     short loc_1400288AD
0x14002889f  mov     rax, [rbp+40h+var_A4]
0x1400288a3  mov     [rsp+140h+var_10C], eax
0x1400288a7  mov     dword ptr cs:xmmword_14000C740+8, eax
0x1400288ad  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1400288b2  lea     rax, aMaxdomainttlin; "MaxDomainTTLInSeconds"
0x1400288b9  mov     [rsp+140h+ValueName.Buffer], rax
0x1400288be  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x1400288c2  lea     rax, [rsp+140h+var_110]
0x1400288c7  mov     dword ptr [rsp+140h+ValueName.Length], 2A002Ah
0x1400288cf  mov     [rsp+140h+ResultLength], rax; ResultLength
0x1400288d4  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1400288d9  mov     r8d, r12d; KeyValueInformationClass
0x1400288dc  mov     [rsp+140h+Length], r15d; Length
0x1400288e1  mov     [rsp+140h+var_110], ebx
0x1400288e5  call    cs:__imp_ZwQueryValueKey
0x1400288ec  nop     dword ptr [rax+rax+00h]
0x1400288f1  test    eax, eax
0x1400288f3  js      short loc_140028908
0x1400288f5  cmp     [rbp+40h+var_AC], edi
0x1400288f8  jnz     short loc_140028908
0x1400288fa  mov     rax, [rbp+40h+var_A4]
0x1400288fe  mov     [rsp+140h+var_10C], eax
0x140028902  mov     dword ptr cs:xmmword_14000C740+0Ch, eax
0x140028908  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x14002890d  lea     rax, aReferralttlmul; "ReferralTTLMultiplier"
0x140028914  mov     [rsp+140h+ValueName.Buffer], rax
0x140028919  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x14002891d  lea     rax, [rsp+140h+var_110]
0x140028922  mov     dword ptr [rsp+140h+ValueName.Length], 2A002Ah
0x14002892a  mov     [rsp+140h+ResultLength], rax; ResultLength
0x14002892f  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028934  mov     r8d, r12d; KeyValueInformationClass
0x140028937  mov     [rsp+140h+Length], r15d; Length
0x14002893c  mov     [rsp+140h+var_110], ebx
0x140028940  call    cs:__imp_ZwQueryValueKey
0x140028947  nop     dword ptr [rax+rax+00h]
0x14002894c  mov     r14d, 400h
0x140028952  test    eax, eax
0x140028954  js      short loc_140028981
0x140028956  cmp     [rbp+40h+var_AC], edi
0x140028959  jnz     short loc_140028981
0x14002895b  mov     rax, [rbp+40h+var_A4]
0x14002895f  mov     [rsp+140h+var_10C], eax
0x140028963  mov     dword ptr cs:xmmword_14000C750+0Ch, eax
0x140028969  cmp     eax, esi
0x14002896b  jnb     short loc_140028975
0x14002896d  mov     dword ptr cs:xmmword_14000C750+0Ch, esi
0x140028973  jmp     short loc_140028981
0x140028975  cmp     eax, r14d
0x140028978  jbe     short loc_140028981
0x14002897a  mov     dword ptr cs:xmmword_14000C750+0Ch, r14d
0x140028981  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x140028986  lea     rax, aDomainttlmulti; "DomainTTLMultiplier"
0x14002898d  mov     [rsp+140h+ValueName.Buffer], rax
0x140028992  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x140028996  lea     rax, [rsp+140h+var_110]
0x14002899b  mov     dword ptr [rsp+140h+ValueName.Length], 260026h
0x1400289a3  mov     [rsp+140h+ResultLength], rax; ResultLength
0x1400289a8  lea     rdx, [rsp+140h+ValueName]; ValueName
0x1400289ad  mov     r8d, r12d; KeyValueInformationClass
0x1400289b0  mov     [rsp+140h+Length], r15d; Length
0x1400289b5  mov     [rsp+140h+var_110], ebx
0x1400289b9  call    cs:__imp_ZwQueryValueKey
0x1400289c0  nop     dword ptr [rax+rax+00h]
0x1400289c5  test    eax, eax
0x1400289c7  js      short loc_1400289F4
0x1400289c9  cmp     [rbp+40h+var_AC], edi
0x1400289cc  jnz     short loc_1400289F4
0x1400289ce  mov     rax, [rbp+40h+var_A4]
0x1400289d2  mov     [rsp+140h+var_10C], eax
0x1400289d6  mov     dword ptr cs:xmmword_14000C750, eax
0x1400289dc  cmp     eax, esi
0x1400289de  jnb     short loc_1400289E8
0x1400289e0  mov     dword ptr cs:xmmword_14000C750, esi
0x1400289e6  jmp     short loc_1400289F4
0x1400289e8  cmp     eax, r14d
0x1400289eb  jbe     short loc_1400289F4
0x1400289ed  mov     dword ptr cs:xmmword_14000C750, r14d
0x1400289f4  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x1400289f9  lea     rax, aMaxreferralcac; "MaxReferralCacheKBytes"
0x140028a00  mov     [rsp+140h+ValueName.Buffer], rax
0x140028a05  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x140028a09  lea     rax, [rsp+140h+var_110]
0x140028a0e  mov     dword ptr [rsp+140h+ValueName.Length], 2C002Ch
0x140028a16  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140028a1b  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028a20  mov     r8d, r12d; KeyValueInformationClass
0x140028a23  mov     [rsp+140h+Length], r15d; Length
0x140028a28  mov     [rsp+140h+var_110], ebx
0x140028a2c  call    cs:__imp_ZwQueryValueKey
0x140028a33  nop     dword ptr [rax+rax+00h]
0x140028a38  mov     r14d, 10h
0x140028a3e  test    eax, eax
0x140028a40  js      short loc_140028A6D
0x140028a42  cmp     [rbp+40h+var_AC], edi
0x140028a45  jnz     short loc_140028A6D
0x140028a47  mov     rcx, [rbp+40h+var_A4]
0x140028a4b  mov     eax, ecx
0x140028a4d  mov     [rsp+140h+var_10C], ecx
0x140028a51  shl     eax, 0Ah
0x140028a54  cmp     eax, ecx
0x140028a56  jb      short loc_140028A6D
0x140028a58  lea     eax, [rcx-1]
0x140028a5b  mov     cs:dword_14000C760, ecx
0x140028a61  cmp     eax, 0Eh
0x140028a64  ja      short loc_140028A6D
0x140028a66  mov     cs:dword_14000C760, r14d
0x140028a6d  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x140028a72  lea     rax, aMaxdomaincache; "MaxDomainCacheKBytes"
0x140028a79  mov     [rsp+140h+ValueName.Buffer], rax
0x140028a7e  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x140028a82  lea     rax, [rsp+140h+var_110]
0x140028a87  mov     dword ptr [rsp+140h+ValueName.Length], 280028h
0x140028a8f  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140028a94  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028a99  mov     r8d, r12d; KeyValueInformationClass
0x140028a9c  mov     [rsp+140h+Length], r15d; Length
0x140028aa1  mov     [rsp+140h+var_110], ebx
0x140028aa5  call    cs:__imp_ZwQueryValueKey
0x140028aac  nop     dword ptr [rax+rax+00h]
0x140028ab1  test    eax, eax
0x140028ab3  js      short loc_140028AE0
0x140028ab5  cmp     [rbp+40h+var_AC], edi
0x140028ab8  jnz     short loc_140028AE0
0x140028aba  mov     rcx, [rbp+40h+var_A4]
0x140028abe  mov     eax, ecx
0x140028ac0  mov     [rsp+140h+var_10C], ecx
0x140028ac4  shl     eax, 0Ah
0x140028ac7  cmp     eax, ecx
0x140028ac9  jb      short loc_140028AE0
0x140028acb  lea     eax, [rcx-1]
0x140028ace  mov     cs:dword_14000C764, ecx
0x140028ad4  cmp     eax, 0Eh
0x140028ad7  ja      short loc_140028AE0
0x140028ad9  mov     cs:dword_14000C764, r14d
0x140028ae0  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x140028ae5  lea     rax, aScavengerthrea; "ScavengerThreadIntervalSeconds"
0x140028aec  mov     [rsp+140h+ValueName.Buffer], rax
0x140028af1  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x140028af5  lea     rax, [rsp+140h+var_110]
0x140028afa  mov     dword ptr [rsp+140h+ValueName.Length], 3C003Ch
0x140028b02  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140028b07  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028b0c  mov     r8d, r12d; KeyValueInformationClass
0x140028b0f  mov     [rsp+140h+Length], r15d; Length
0x140028b14  mov     [rsp+140h+var_110], ebx
0x140028b18  call    cs:__imp_ZwQueryValueKey
0x140028b1f  nop     dword ptr [rax+rax+00h]
0x140028b24  test    eax, eax
0x140028b26  js      short loc_140028B4C
0x140028b28  cmp     [rbp+40h+var_AC], edi
0x140028b2b  jnz     short loc_140028B4C
0x140028b2d  mov     rax, [rbp+40h+var_A4]
0x140028b31  mov     [rsp+140h+var_10C], eax
0x140028b35  mov     dword ptr cs:xmmword_14000C750+4, eax
0x140028b3b  dec     eax
0x140028b3d  cmp     eax, 1Ch
0x140028b40  ja      short loc_140028B4C
0x140028b42  mov     dword ptr cs:xmmword_14000C750+4, 1Eh
0x140028b4c  mov     rcx, [rsp+140h+Handle]; KeyHandle
0x140028b51  lea     rax, aMaxentriesdele; "MaxEntriesDeletedPerInterval"
0x140028b58  mov     [rsp+140h+ValueName.Buffer], rax
0x140028b5d  lea     r9, [rbp+40h+KeyValueInformation]; KeyValueInformation
0x140028b61  lea     rax, [rsp+140h+var_110]
0x140028b66  mov     dword ptr [rsp+140h+ValueName.Length], 380038h
0x140028b6e  mov     [rsp+140h+ResultLength], rax; ResultLength
0x140028b73  lea     rdx, [rsp+140h+ValueName]; ValueName
0x140028b78  mov     r8d, r12d; KeyValueInformationClass
0x140028b7b  mov     [rsp+140h+Length], r15d; Length
0x140028b80  mov     [rsp+140h+var_110], ebx
0x140028b84  call    cs:__imp_ZwQueryValueKey
0x140028b8b  nop     dword ptr [rax+rax+00h]
0x140028b90  test    eax, eax
0x140028b92  js      short loc_140028BAC
0x140028b94  cmp     [rbp+40h+var_AC], edi
0x140028b97  jnz     short loc_140028BAC
0x140028b99  mov     rax, [rbp+40h+var_A4]
0x140028b9d  cmp     eax, esi
0x140028b9f  cmovb   eax, esi
0x140028ba2  mov     [rsp+140h+var_10C], eax
0x140028ba6  mov     dword ptr cs:xmmword_14000C750+8, eax
0x140028bac  mov     rax, [rsp+140h+KeyHandle]
0x140028bb1  test    rax, rax
0x140028bb4  jz      loc_140028C62
0x140028bba  lea     rcx, aParameters; "Parameters"
0x140028bc1  mov     [rsp+140h+ObjectAttributes.RootDirectory], rax
0x140028bc6  mov     [rsp+140h+ValueName.Buffer], rcx
0x140028bcb  lea     rax, [rsp+140h+ValueName]
0x140028bd0  xorps   xmm0, xmm0
0x140028bd3  mov     dword ptr [rsp+140h+ValueName.Length], 140014h
0x140028bdb  lea     rcx, [rsp+140h+var_E8]; KeyHandle
0x140028be0  mov     [rsp+140h+ObjectAttributes.Length], r13d
0x140028be5  lea     r8, [rsp+140h+ObjectAttributes]; ObjectAttributes
0x140028bea  mov     [rsp+140h+ObjectAttributes.Attributes], 240h
0x140028bf2  mov     edx, 20019h; DesiredAccess
0x140028bf7  mov     [rsp+140h+ObjectAttributes.ObjectName], rax
0x140028bfc  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028c01  call    cs:__imp_ZwOpenKey
0x140028c08  nop     dword ptr [rax+rax+00h]
0x140028c0d  test    eax, eax
0x140028c0f  js      short loc_140028C4C
  ... truncated ...
```
