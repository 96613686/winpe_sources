# SPSslFreeObject

- ea: `0x180046720`
- end: `0x1800469be`
- name: `SPSslFreeObject`
- size: `670`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006470`
- `0x1800082b0`
- `0x180036040`
- `0x180046720`
- `0x180083314`
- `0x180084f84`
- `0x180085164`
- `0x180085568`
- `0x1800859f8`
- `0x180085e34`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180046813`
- `ntoskrnl!RtlInitUnicodeString` at `0x180046813`
- `ntoskrnl!ZwQueryValueKey` at `0x180046844`
- `ntoskrnl!ZwQueryValueKey` at `0x180046844`
- `ntoskrnl!ZwClose` at `0x180046876`
- `ntoskrnl!ZwClose` at `0x180046876`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180046748`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180046748`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18004675d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18004675d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800468d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800468d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800468dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800468dc`
- `ntoskrnl!SkIsSecureKernel` at `0x180046788`
- `ntoskrnl!SkIsSecureKernel` at `0x180046788`

## string_xrefs

- `0x180046929`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x1800467cc`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider`

## pseudocode

```c
__int64 __fastcall SPSslFreeObject(unsigned int *P, int a2, int a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r9
  int v7; // eax
  BOOL v8; // esi
  HANDLE v9; // rbx
  void *v11; // rcx
  __int64 v12; // rcx
  _BYTE *v13; // rax
  __int64 v14; // rdx
  _BYTE *v15; // rax
  HANDLE KeyHandle; // [rsp+40h] [rbp-58h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-48h] BYREF
  int KeyValueInformation; // [rsp+60h] [rbp-38h] BYREF
  __int128 v20; // [rsp+64h] [rbp-34h]

  if ( !dword_1800CE0E4 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    if ( !dword_1800CE0E4 )
    {
      LOBYTE(v7) = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
      {
        v7 = ((int)SkIsSecureKernel(v5, v4) >> 31) + 2;
        g_TrustedEnvironment = v7;
      }
      if ( (v7 & 2) == 0 )
      {
        KeyHandle = 0;
        v8 = 0;
        if ( (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol Provider",
                    0,
                    &KeyHandle,
                    v6) >= 0 )
        {
          v9 = KeyHandle;
          ResultLength = 0;
          KeyValueInformation = 0;
          DestinationString = 0;
          v20 = 0;
          RtlInitUnicodeString(
            &DestinationString,
            (PCWSTR)"E\x00n\x00a\x00b\x00l\x00e\x00T\x00l\x00s\x00E\x00x\x00t\x00e\x00r\x00n\x00a\x00l\x00A\x00l\x00g\x00o\x00r\x00i\x00t\x00h\x00m\x00s");
          if ( ZwQueryValueKey(
                 v9,
                 &DestinationString,
                 KeyValuePartialInformation,
                 &KeyValueInformation,
                 0x14u,
                 &ResultLength) >= 0
            && (_DWORD)v20 == 4 )
          {
            v8 = DWORD2(v20) == 1;
          }
        }
        if ( KeyHandle )
        {
          ZwClose(KeyHandle);
          KeyHandle = 0;
        }
        dword_1800CD804 = v8;
        if ( v8 )
        {
          GetExternalHashAlgorithms();
          GetExternalSignatureAlgorithms();
          GetExternalKeyExchangeAlgorithms();
          GetExternalCipherAlgorithms();
          GetExternalCipherSuites();
        }
      }
      dword_1800CE0E4 = 1;
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
  }
  if ( !P )
    return 2148073511LL;
  if ( P[1] == 1936944177 )
  {
    v14 = 912;
    v15 = P;
    do
    {
      *v15++ = 0;
      --v14;
    }
    while ( v14 );
LABEL_31:
    MSCryptFree(P);
    return 0;
  }
  if ( P[1] == 1936944179 )
  {
    v11 = (void *)*((_QWORD *)P + 4);
    if ( v11 )
      BCryptDestroyKey(v11);
    v12 = *P;
    v13 = P;
    if ( *P )
    {
      do
      {
        *v13++ = 0;
        --v12;
      }
      while ( v12 );
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      a3,
      (unsigned int)"Status",
      2,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      44);
  return 3221225474LL;
}

```

## disassembly

```asm
0x180046720  push    rdi
0x180046722  sub     rsp, 90h
0x180046729  mov     rax, cs:__security_cookie
0x180046730  xor     rax, rsp
0x180046733  mov     [rsp+98h+var_20], rax
0x180046738  cmp     cs:dword_1800CE0E4, 0
0x18004673f  mov     rdi, rcx
0x180046742  jnz     loc_1800468E8
0x180046748  call    cs:__imp_KeEnterCriticalRegion
0x18004674f  nop     dword ptr [rax+rax+00h]
0x180046754  mov     dl, 1; Wait
0x180046756  lea     rcx, Resource; Resource
0x18004675d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180046764  nop     dword ptr [rax+rax+00h]
0x180046769  cmp     cs:dword_1800CE0E4, 0
0x180046770  jnz     loc_1800468C9
0x180046776  mov     eax, cs:g_TrustedEnvironment
0x18004677c  mov     [rsp+98h+var_18], r14
0x180046784  test    eax, eax
0x180046786  jnz     short loc_1800467A0
0x180046788  call    cs:__imp_SkIsSecureKernel
0x18004678f  nop     dword ptr [rax+rax+00h]
0x180046794  sar     eax, 1Fh
0x180046797  add     eax, 2
0x18004679a  mov     cs:g_TrustedEnvironment, eax
0x1800467a0  mov     r14d, 1
0x1800467a6  test    al, 2
0x1800467a8  jnz     loc_1800468BA
0x1800467ae  mov     [rsp+98h+arg_10], rbp
0x1800467b6  lea     r8, [rsp+98h+KeyHandle]; KeyHandle
0x1800467bb  xor     ebp, ebp
0x1800467bd  mov     [rsp+98h+var_10], rsi
0x1800467c5  xor     edx, edx; PCWSTR
0x1800467c7  mov     [rsp+98h+KeyHandle], rbp
0x1800467cc  lea     rcx, aRegistryMachin_14; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x1800467d3  mov     esi, ebp
0x1800467d5  call    TlsOpenRegKey
0x1800467da  test    eax, eax
0x1800467dc  js      loc_18004686C
0x1800467e2  xorps   xmm0, xmm0
0x1800467e5  mov     [rsp+98h+arg_8], rbx
0x1800467ed  mov     rbx, [rsp+98h+KeyHandle]
0x1800467f2  lea     rdx, g_rgbPad1+30h; SourceString
0x1800467f9  xorps   xmm1, xmm1
0x1800467fc  mov     [rsp+98h+var_50], ebp
0x180046800  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180046805  mov     [rsp+98h+KeyValueInformation], ebp
0x180046809  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x18004680e  movups  [rsp+98h+var_34], xmm1
0x180046813  call    cs:__imp_RtlInitUnicodeString
0x18004681a  nop     dword ptr [rax+rax+00h]
0x18004681f  lea     rax, [rsp+98h+var_50]
0x180046824  mov     r8d, 2; KeyValueInformationClass
0x18004682a  mov     [rsp+98h+ResultLength], rax; ResultLength
0x18004682f  lea     r9, [rsp+98h+KeyValueInformation]; KeyValueInformation
0x180046834  lea     rdx, [rsp+98h+DestinationString]; ValueName
0x180046839  mov     [rsp+98h+Length], 14h; Length
0x180046841  mov     rcx, rbx; KeyHandle
0x180046844  call    cs:__imp_ZwQueryValueKey
0x18004684b  nop     dword ptr [rax+rax+00h]
0x180046850  mov     rbx, [rsp+98h+arg_8]
0x180046858  test    eax, eax
0x18004685a  js      short loc_18004686C
0x18004685c  cmp     dword ptr [rsp+98h+var_34], 4
0x180046861  jnz     short loc_18004686C
0x180046863  cmp     dword ptr [rsp+98h+var_34+8], r14d
0x180046868  cmovz   esi, r14d
0x18004686c  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x180046871  test    rcx, rcx
0x180046874  jz      short loc_180046887
0x180046876  call    cs:__imp_ZwClose
0x18004687d  nop     dword ptr [rax+rax+00h]
0x180046882  mov     [rsp+98h+KeyHandle], rbp
0x180046887  mov     rbp, [rsp+98h+arg_10]
0x18004688f  test    esi, esi
0x180046891  mov     cs:dword_1800CD804, esi
0x180046897  mov     rsi, [rsp+98h+var_10]
0x18004689f  jz      short loc_1800468BA
0x1800468a1  call    GetExternalHashAlgorithms
0x1800468a6  call    GetExternalSignatureAlgorithms
0x1800468ab  call    GetExternalKeyExchangeAlgorithms
0x1800468b0  call    GetExternalCipherAlgorithms
0x1800468b5  call    GetExternalCipherSuites
0x1800468ba  mov     cs:dword_1800CE0E4, r14d
0x1800468c1  mov     r14, [rsp+98h+var_18]
0x1800468c9  lea     rcx, Resource; Resource
0x1800468d0  call    cs:__imp_ExReleaseResourceLite
0x1800468d7  nop     dword ptr [rax+rax+00h]
0x1800468dc  call    cs:__imp_KeLeaveCriticalRegion
0x1800468e3  nop     dword ptr [rax+rax+00h]
0x1800468e8  test    rdi, rdi
0x1800468eb  jnz     short loc_1800468F7
0x1800468ed  mov     eax, 80090027h
0x1800468f2  jmp     loc_1800469A7
0x1800468f7  mov     ecx, [rdi+4]
0x1800468fa  sub     ecx, 73736C31h
0x180046900  jz      loc_18004697F
0x180046906  cmp     ecx, 2
0x180046909  jz      short loc_180046958
0x18004690b  mov     rcx, cs:WPP_GLOBAL_Control
0x180046912  lea     rax, WPP_GLOBAL_Control
0x180046919  cmp     rcx, rax
0x18004691c  jz      short loc_180046951
0x18004691e  mov     eax, [rcx+2Ch]
0x180046921  test    al, 1
0x180046923  jz      short loc_180046951
0x180046925  mov     rcx, [rcx+18h]
0x180046929  lea     rax, aOnecoreDsSecur_28; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046930  mov     [rsp+98h+var_68], 0A2Ch
0x180046938  lea     r9, aStatus; "Status"
0x18004693f  mov     [rsp+98h+ResultLength], rax
0x180046944  mov     [rsp+98h+Length], 0C0000002h
0x18004694c  call    WPP_SF_sDsd
0x180046951  mov     eax, 0C0000002h
0x180046956  jmp     short loc_1800469A7
0x180046958  mov     rcx, [rdi+20h]; hKey
0x18004695c  test    rcx, rcx
0x18004695f  jz      short loc_180046966
0x180046961  call    BCryptDestroyKey
0x180046966  mov     ecx, [rdi]
0x180046968  mov     rax, rdi
0x18004696b  test    rcx, rcx
0x18004696e  jz      short loc_18004699D
0x180046970  mov     byte ptr [rax], 0
0x180046973  lea     rax, [rax+1]
0x180046977  sub     rcx, 1
0x18004697b  jnz     short loc_180046970
0x18004697d  jmp     short loc_18004699D
0x18004697f  mov     edx, 390h
0x180046984  mov     rax, rdi
0x180046987  nop     word ptr [rax+rax+00000000h]
0x180046990  mov     byte ptr [rax], 0
0x180046993  lea     rax, [rax+1]
0x180046997  sub     rdx, 1
0x18004699b  jnz     short loc_180046990
0x18004699d  mov     rcx, rdi; P
0x1800469a0  call    MSCryptFree
0x1800469a5  xor     eax, eax
0x1800469a7  mov     rcx, [rsp+98h+var_20]
0x1800469ac  xor     rcx, rsp; StackCookie
0x1800469af  call    __security_check_cookie
0x1800469b4  add     rsp, 90h
0x1800469bb  pop     rdi
0x1800469bc  retn
```
