# SkipNonSecureCore(int *)

- ea: `0x180033720`
- end: `0x180033919`
- name: `?SkipNonSecureCore@@YAJPEAH@Z`
- size: `505`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000dcc0`
- `0x180011690`
- `0x18002feec`

## callees

- `0x1800039f0`
- `0x18000bab4`
- `0x180011424`
- `0x180031ec0`
- `0x180033720`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033800`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180033800`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033810`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180033810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800338cc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180033827`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180033827`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003385a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003385a`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x1800338c0`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x1800338c0`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18003388c`
- `api-ms-win-core-firmware-l1-1-0!SetFirmwareEnvironmentVariableW` at `0x18003388c`

## string_xrefs

- `0x18003381e`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SkipNonSecureCore(wil::details *a1)
{
  unsigned int v3; // r8d
  int v4; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  bool v7; // sf
  DWORD FirmwareEnvironmentVariableW; // edi
  signed int v9; // eax
  bool v10; // sf
  int v11; // eax
  int v12; // [rsp+30h] [rbp-40h]
  _BYTE pBuffer[8]; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  void **v15; // [rsp+50h] [rbp-20h] BYREF
  _LUID Luid[2]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47E,
      (int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
  v3 = *(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor;
  if ( (*(_DWORD *)Feature_ConfigLock_DMClientCSP__descriptor & 4) == 0 )
  {
    v15 = (void **)*wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(
                      a1,
                      &v15);
    v3 = (unsigned int)v15;
  }
  LODWORD(TokenHandle) = 0;
  WORD2(TokenHandle) = 3;
  v4 = 1;
  wil::details::ReportUsageToService(
    (__int64)&qword_180051238,
    0x16B4257u,
    (v3 >> 10) & 1,
    (v3 >> 11) & 1,
    (__int64)&TokenHandle,
    1u,
    v12);
  pBuffer[0] = 0;
  v15 = &NvRam::`vftable';
  if ( !`NvRam::Initialize'::`2'::s_fIsInitialized )
  {
    TokenHandle = 0;
    *(_OWORD *)&Luid[0].LowPart = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
      || !LookupPrivilegeValueW(0, L"SeSystemEnvironmentPrivilege", (PLUID)&Luid[0].HighPart)
      || (Luid[0].LowPart = 1,
          Luid[1].HighPart = 2,
          !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0)) )
    {
      LastError = GetLastError();
      v7 = LastError < 0;
      if ( LastError > 0 )
        v7 = 1;
      if ( v7 )
        goto LABEL_24;
    }
    if ( SetFirmwareEnvironmentVariableW(&word_1800401D0, L"{00000000-0000-0000-0000-000000000000}", 0, 0)
      || GetLastError() == 1 )
    {
      goto LABEL_24;
    }
    `NvRam::Initialize'::`2'::s_fIsInitialized = 1;
  }
  pBuffer[0] = 0;
  FirmwareEnvironmentVariableW = GetFirmwareEnvironmentVariableW(
                                   L"BuiltAsSecuredCorePC",
                                   L"{77FA9ABD-0359-4D32-BD60-28F4E78F784B}",
                                   pBuffer,
                                   1u);
  if ( FirmwareEnvironmentVariableW )
    goto LABEL_20;
  v9 = GetLastError();
  v10 = v9 < 0;
  if ( v9 > 0 )
    v10 = 1;
  if ( !v10 )
  {
LABEL_20:
    v11 = 0;
    if ( FirmwareEnvironmentVariableW )
      LOBYTE(v11) = pBuffer[0] != 0;
    if ( v11 )
      v4 = 0;
  }
LABEL_24:
  *(_DWORD *)a1 = v4;
  return 0;
}

```

## disassembly

```asm
0x180033720  mov     [rsp-18h+arg_8], rbx
0x180033725  mov     [rsp-18h+arg_10], rsi
0x18003372a  push    rbp
0x18003372b  push    rdi
0x18003372c  push    r15
0x18003372e  mov     rbp, rsp
0x180033731  sub     rsp, 70h
0x180033735  mov     rax, cs:__security_cookie
0x18003373c  xor     rax, rsp
0x18003373f  mov     [rbp+var_8], rax
0x180033743  mov     rsi, rcx
0x180033746  test    rcx, rcx
0x180033749  jnz     short loc_18003376F
0x18003374b  mov     rcx, [rbp+18h]; this
0x18003374f  mov     ebx, 80070057h
0x180033754  mov     r9d, ebx; char *
0x180033757  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x18003375e  mov     edx, 47Eh; void *
0x180033763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033768  mov     eax, ebx
0x18003376a  jmp     loc_1800338F8
0x18003376f  mov     rax, cs:Feature_ConfigLock_DMClientCSP__descriptor
0x180033776  mov     r8d, [rax]
0x180033779  test    r8b, 4
0x18003377d  jnz     short loc_180033792
0x18003377f  lea     rdx, [rbp+var_20]
0x180033783  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ConfigLock_DMClientCSP@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ConfigLock_DMClientCSP>::GetCachedFeatureEnabledState(void)
0x180033788  mov     rcx, [rax]
0x18003378b  mov     [rbp+var_20], rcx
0x18003378f  mov     r8d, ecx
0x180033792  xor     eax, eax
0x180033794  mov     dword ptr [rbp+TokenHandle], eax
0x180033797  mov     word ptr [rbp+TokenHandle+4], 3
0x18003379d  mov     r9d, r8d
0x1800337a0  shr     r9d, 0Bh
0x1800337a4  lea     ebx, [rax+1]
0x1800337a7  and     r9d, ebx
0x1800337aa  shr     r8d, 0Ah
0x1800337ae  and     r8d, ebx
0x1800337b1  mov     dword ptr [rsp+70h+ReturnLength], ebx
0x1800337b5  lea     rax, [rbp+TokenHandle]
0x1800337b9  mov     [rsp+70h+PreviousState], rax
0x1800337be  mov     edx, 16B4257h
0x1800337c3  lea     rcx, qword_180051238
0x1800337ca  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800337cf  mov     [rbp+pBuffer], 0
0x1800337d3  lea     rax, ??_7NvRam@@6B@; const NvRam::`vftable'
0x1800337da  mov     [rbp+var_20], rax
0x1800337de  mov     r15d, 80070000h
0x1800337e4  cmp     cs:?s_fIsInitialized@?1??Initialize@NvRam@@AEAAJXZ@4HA, 0; int `NvRam::Initialize(void)'::`2'::s_fIsInitialized
0x1800337eb  jnz     loc_1800338A6
0x1800337f1  mov     [rbp+TokenHandle], 0
0x1800337f9  xorps   xmm0, xmm0
0x1800337fc  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x180033800  call    cs:__imp_GetCurrentProcess
0x180033806  mov     rcx, rax; ProcessHandle
0x180033809  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18003380d  lea     edx, [rbx+27h]; DesiredAccess
0x180033810  call    cs:__imp_OpenProcessToken
0x180033816  test    eax, eax
0x180033818  jz      short loc_180033864
0x18003381a  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x18003381e  lea     rdx, aSesystemenviro; "SeSystemEnvironmentPrivilege"
0x180033825  xor     ecx, ecx; lpSystemName
0x180033827  call    cs:__imp_LookupPrivilegeValueW
0x18003382d  test    eax, eax
0x18003382f  jz      short loc_180033864
0x180033831  mov     [rbp+Luid.LowPart], ebx
0x180033834  mov     [rbp+Luid.HighPart+8], 2
0x18003383b  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x180033844  mov     [rsp+70h+PreviousState], 0; PreviousState
0x18003384d  xor     r9d, r9d; BufferLength
0x180033850  lea     r8, [rbp+Luid]; NewState
0x180033854  xor     edx, edx; DisableAllPrivileges
0x180033856  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003385a  call    cs:__imp_AdjustTokenPrivileges
0x180033860  test    eax, eax
0x180033862  jnz     short loc_180033878
0x180033864  call    cs:__imp_GetLastError
0x18003386a  test    eax, eax
0x18003386c  jle     short loc_180033876
0x18003386e  movzx   eax, ax
0x180033871  or      eax, r15d
0x180033874  test    eax, eax
0x180033876  js      short loc_1800338E0
0x180033878  xor     r9d, r9d; nSize
0x18003387b  xor     r8d, r8d; pValue
0x18003387e  lea     rdx, Guid; "{00000000-0000-0000-0000-000000000000}"
0x180033885  lea     rcx, word_1800401D0; lpName
0x18003388c  call    cs:__imp_SetFirmwareEnvironmentVariableW
0x180033892  test    eax, eax
0x180033894  jnz     short loc_1800338E0
0x180033896  call    cs:__imp_GetLastError
0x18003389c  cmp     eax, ebx
0x18003389e  jz      short loc_1800338E0
0x1800338a0  mov     cs:?s_fIsInitialized@?1??Initialize@NvRam@@AEAAJXZ@4HA, ebx; int `NvRam::Initialize(void)'::`2'::s_fIsInitialized
0x1800338a6  xor     eax, eax
0x1800338a8  mov     [rbp+pBuffer], al
0x1800338ab  mov     r9d, ebx; nSize
0x1800338ae  lea     r8, [rbp+pBuffer]; pBuffer
0x1800338b2  lea     rdx, a77fa9abd03594d; "{77FA9ABD-0359-4D32-BD60-28F4E78F784B}"
0x1800338b9  lea     rcx, aBuiltassecured; "BuiltAsSecuredCorePC"
0x1800338c0  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x1800338c6  mov     edi, eax
0x1800338c8  test    eax, eax
0x1800338ca  jnz     short loc_1800338E2
0x1800338cc  call    cs:__imp_GetLastError
0x1800338d2  test    eax, eax
0x1800338d4  jle     short loc_1800338DE
0x1800338d6  movzx   eax, ax
0x1800338d9  or      eax, r15d
0x1800338dc  test    eax, eax
0x1800338de  jns     short loc_1800338E2
0x1800338e0  jmp     short loc_1800338F4
0x1800338e2  xor     eax, eax
0x1800338e4  test    edi, edi; __annotation("Debug", "TelemetryAssert", "dwSizeData <=1")
0x1800338e6  jz      short loc_1800338EE
0x1800338e8  cmp     [rbp+pBuffer], al
0x1800338eb  setnz   al
0x1800338ee  test    eax, eax
0x1800338f0  jz      short loc_1800338F4
0x1800338f2  xor     ebx, ebx
0x1800338f4  mov     [rsi], ebx
0x1800338f6  xor     eax, eax
0x1800338f8  mov     rcx, [rbp+var_8]
0x1800338fc  xor     rcx, rsp; StackCookie
0x1800338ff  call    __security_check_cookie
0x180033904  lea     r11, [rsp+70h+var_s0]
0x180033909  mov     rbx, [r11+28h]
0x18003390d  mov     rsi, [r11+30h]
0x180033911  mov     rsp, r11
0x180033914  pop     r15
0x180033916  pop     rdi
0x180033917  pop     rbp
0x180033918  retn
```
