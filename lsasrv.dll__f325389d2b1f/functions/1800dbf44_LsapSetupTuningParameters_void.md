# LsapSetupTuningParameters(void)

- ea: `0x1800dbf44`
- end: `0x1800dc24a`
- name: `?LsapSetupTuningParameters@@YAXXZ`
- size: `774`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1800d20d8`

## callees

- `0x180011278`
- `0x1800ada18`
- `0x1800dbf44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dc02f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dc02f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc17d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc17d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dc061`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800dc061`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dc01b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800dc01b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc094`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc0d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc114`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc157`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc094`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc0d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc114`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800dc157`
- `ntdll!RtlGetNtProductType` at `0x1800dbfb4`
- `ntdll!RtlGetNtProductType` at `0x1800dbfb4`

## string_xrefs

- `0x1800dc08d`: `GeneralThreadLifespan`
- `0x1800dc0cd`: `DedicatedThreadLifespan`

## pseudocode

```c
void LsapSetupTuningParameters(void)
{
  struct _PEB *v0; // rax
  unsigned int v1; // ecx
  ULONG v2; // eax
  LsaHandleCache *v3; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD v6; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+78h] [rbp+38h] BYREF

  LsaTuningParameters = 60;
  ProductType = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  v6 = 0;
  v0 = NtCurrentPeb();
  qword_18019E1CC = 0x20000001ELL;
  v1 = 1000 * v0->NumberOfProcessors;
  v2 = 32000;
  SpinCount = v1;
  if ( v1 > 0x7D00 || (v2 = 1000, v1 < 0x3E8) )
    SpinCount = v2;
  if ( RtlGetNtProductType(&ProductType) )
  {
    if ( ProductType != NtProductWinNt )
    {
      LsaTuningParameters = 900;
      qword_18019E1CC = 300;
    }
    GetDsaThreadState = LsaDbExtPushCallContext;
    RestoreDsaThreadState = (void (*)(void *))LsaDbExtRestoreCallContext;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 0x2001Fu, &hKey) )
  {
    Data = GetCurrentProcessId();
    RegSetValueExW(hKey, L"LsaPid", 0, 4u, (const BYTE *)&Data, 4u);
    v6 = 4;
    if ( !RegQueryValueExW(hKey, L"GeneralThreadLifespan", 0, &Type, (LPBYTE)&Data, &v6) )
      LsaTuningParameters = Data;
    v6 = 4;
    if ( !RegQueryValueExW(hKey, L"DedicatedThreadLifespan", 0, &Type, (LPBYTE)&Data, &v6) )
      LODWORD(qword_18019E1CC) = Data;
    v6 = 4;
    if ( !RegQueryValueExW(hKey, L"HighPriority", 0, &Type, (LPBYTE)&Data, &v6) && Data )
      HIDWORD(qword_18019E1CC) |= 1u;
    v6 = 4;
    if ( !RegQueryValueExW(hKey, L"CritSecSpinCount", 0, &Type, (LPBYTE)&Data, &v6) && Data && Type == 4 )
      SpinCount = Data;
    RegCloseKey(hKey);
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != (LsaHandleCache *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v3 + 28) & 0x80) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v3 + 2), 17, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids, LsaTuningParameters);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != (LsaHandleCache *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v3 + 28) & 0x80) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)v3 + 2),
            18,
            WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids,
            (unsigned int)qword_18019E1CC);
          v3 = WPP_GLOBAL_Control;
        }
        if ( v3 != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x80) != 0 )
          WPP_SF_(*((_QWORD *)v3 + 2), 19, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids);
      }
    }
  }
}

```

## disassembly

```asm
0x1800dbf44  push    rbp
0x1800dbf46  push    rbx
0x1800dbf47  push    rdi
0x1800dbf48  mov     rbp, rsp
0x1800dbf4b  sub     rsp, 40h
0x1800dbf4f  xor     ebx, ebx
0x1800dbf51  mov     cs:?LsaTuningParameters@@3U_LSA_TUNING_PARAMETERS@@A, 3Ch ; '<'; _LSA_TUNING_PARAMETERS LsaTuningParameters
0x1800dbf5b  mov     [rbp+ProductType], ebx
0x1800dbf5e  mov     [rbp+hKey], rbx
0x1800dbf62  mov     [rbp+Data], ebx
0x1800dbf65  mov     [rbp+Type], ebx
0x1800dbf68  mov     [rbp+arg_8], ebx
0x1800dbf6b  mov     rax, gs:60h
0x1800dbf74  mov     dword ptr cs:qword_18019E1CC, 1Eh
0x1800dbf7e  mov     dword ptr cs:qword_18019E1CC+4, 2
0x1800dbf88  imul    ecx, [rax+0B8h], 3E8h
0x1800dbf92  mov     eax, 7D00h
0x1800dbf97  mov     cs:SpinCount, ecx
0x1800dbf9d  cmp     ecx, eax
0x1800dbf9f  ja      short loc_1800DBFAA
0x1800dbfa1  mov     eax, 3E8h
0x1800dbfa6  cmp     ecx, eax
0x1800dbfa8  jnb     short loc_1800DBFB0
0x1800dbfaa  mov     cs:SpinCount, eax
0x1800dbfb0  lea     rcx, [rbp+ProductType]; ProductType
0x1800dbfb4  call    cs:__imp_RtlGetNtProductType
0x1800dbfbb  nop     dword ptr [rax+rax+00h]
0x1800dbfc0  test    al, al
0x1800dbfc2  jz      short loc_1800DBFFB
0x1800dbfc4  cmp     [rbp+ProductType], 1
0x1800dbfc8  jz      short loc_1800DBFDF
0x1800dbfca  mov     cs:?LsaTuningParameters@@3U_LSA_TUNING_PARAMETERS@@A, 384h; _LSA_TUNING_PARAMETERS LsaTuningParameters
0x1800dbfd4  mov     cs:qword_18019E1CC, 12Ch
0x1800dbfdf  lea     rax, ?LsaDbExtPushCallContext@@YAPEAXXZ; LsaDbExtPushCallContext(void)
0x1800dbfe6  mov     cs:?GetDsaThreadState@@3P6APEAXXZEA, rax; void * (*GetDsaThreadState)(void)
0x1800dbfed  lea     rax, ?LsaDbExtRestoreCallContext@@YAXPEAX@Z; LsaDbExtRestoreCallContext(void *)
0x1800dbff4  mov     cs:?RestoreDsaThreadState@@3P6AXPEAX@ZEA, rax; void (*RestoreDsaThreadState)(void *)
0x1800dbffb  lea     rax, [rbp+hKey]
0x1800dbfff  mov     r9d, 2001Fh; samDesired
0x1800dc005  xor     r8d, r8d; ulOptions
0x1800dc008  mov     [rsp+40h+phkResult], rax; phkResult
0x1800dc00d  lea     rdx, aSystemCurrentc_14; "System\\CurrentControlSet\\Control\\Lsa"
0x1800dc014  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800dc01b  call    cs:__imp_RegOpenKeyExW
0x1800dc022  nop     dword ptr [rax+rax+00h]
0x1800dc027  test    eax, eax
0x1800dc029  jnz     loc_1800DC189
0x1800dc02f  call    cs:__imp_GetCurrentProcessId
0x1800dc036  nop     dword ptr [rax+rax+00h]
0x1800dc03b  mov     rcx, [rbp+hKey]; hKey
0x1800dc03f  lea     rdx, aLsapid; "LsaPid"
0x1800dc046  mov     [rbp+Data], eax
0x1800dc049  mov     edi, 4
0x1800dc04e  lea     rax, [rbp+Data]
0x1800dc052  mov     [rsp+40h+cbData], edi; cbData
0x1800dc056  mov     r9d, edi; dwType
0x1800dc059  mov     [rsp+40h+phkResult], rax; lpData
0x1800dc05e  xor     r8d, r8d; Reserved
0x1800dc061  call    cs:__imp_RegSetValueExW
0x1800dc068  nop     dword ptr [rax+rax+00h]
0x1800dc06d  mov     rcx, [rbp+hKey]; hKey
0x1800dc071  lea     rax, [rbp+arg_8]
0x1800dc075  mov     qword ptr [rsp+40h+cbData], rax; lpcbData
0x1800dc07a  lea     r9, [rbp+Type]; lpType
0x1800dc07e  lea     rax, [rbp+Data]
0x1800dc082  mov     [rbp+arg_8], edi
0x1800dc085  xor     r8d, r8d; lpReserved
0x1800dc088  mov     [rsp+40h+phkResult], rax; lpData
0x1800dc08d  lea     rdx, aGeneralthreadl; "GeneralThreadLifespan"
0x1800dc094  call    cs:__imp_RegQueryValueExW
0x1800dc09b  nop     dword ptr [rax+rax+00h]
0x1800dc0a0  test    eax, eax
0x1800dc0a2  jnz     short loc_1800DC0AD
0x1800dc0a4  mov     eax, [rbp+Data]
0x1800dc0a7  mov     cs:?LsaTuningParameters@@3U_LSA_TUNING_PARAMETERS@@A, eax; _LSA_TUNING_PARAMETERS LsaTuningParameters
0x1800dc0ad  mov     rcx, [rbp+hKey]; hKey
0x1800dc0b1  lea     rax, [rbp+arg_8]
0x1800dc0b5  mov     qword ptr [rsp+40h+cbData], rax; lpcbData
0x1800dc0ba  lea     r9, [rbp+Type]; lpType
0x1800dc0be  lea     rax, [rbp+Data]
0x1800dc0c2  mov     [rbp+arg_8], edi
0x1800dc0c5  xor     r8d, r8d; lpReserved
0x1800dc0c8  mov     [rsp+40h+phkResult], rax; lpData
0x1800dc0cd  lea     rdx, aDedicatedthrea; "DedicatedThreadLifespan"
0x1800dc0d4  call    cs:__imp_RegQueryValueExW
0x1800dc0db  nop     dword ptr [rax+rax+00h]
0x1800dc0e0  test    eax, eax
0x1800dc0e2  jnz     short loc_1800DC0ED
0x1800dc0e4  mov     eax, [rbp+Data]
0x1800dc0e7  mov     dword ptr cs:qword_18019E1CC, eax
0x1800dc0ed  mov     rcx, [rbp+hKey]; hKey
0x1800dc0f1  lea     rax, [rbp+arg_8]
0x1800dc0f5  mov     qword ptr [rsp+40h+cbData], rax; lpcbData
0x1800dc0fa  lea     r9, [rbp+Type]; lpType
0x1800dc0fe  lea     rax, [rbp+Data]
0x1800dc102  mov     [rbp+arg_8], edi
0x1800dc105  xor     r8d, r8d; lpReserved
0x1800dc108  mov     [rsp+40h+phkResult], rax; lpData
0x1800dc10d  lea     rdx, aHighpriority; "HighPriority"
0x1800dc114  call    cs:__imp_RegQueryValueExW
0x1800dc11b  nop     dword ptr [rax+rax+00h]
0x1800dc120  test    eax, eax
0x1800dc122  jnz     short loc_1800DC130
0x1800dc124  cmp     [rbp+Data], ebx
0x1800dc127  jz      short loc_1800DC130
0x1800dc129  or      dword ptr cs:qword_18019E1CC+4, 1
0x1800dc130  mov     rcx, [rbp+hKey]; hKey
0x1800dc134  lea     rax, [rbp+arg_8]
0x1800dc138  mov     qword ptr [rsp+40h+cbData], rax; lpcbData
0x1800dc13d  lea     r9, [rbp+Type]; lpType
0x1800dc141  lea     rax, [rbp+Data]
0x1800dc145  mov     [rbp+arg_8], edi
0x1800dc148  xor     r8d, r8d; lpReserved
0x1800dc14b  mov     [rsp+40h+phkResult], rax; lpData
0x1800dc150  lea     rdx, aCritsecspincou; "CritSecSpinCount"
0x1800dc157  call    cs:__imp_RegQueryValueExW
0x1800dc15e  nop     dword ptr [rax+rax+00h]
0x1800dc163  test    eax, eax
0x1800dc165  jnz     short loc_1800DC179
0x1800dc167  mov     eax, [rbp+Data]
0x1800dc16a  test    eax, eax
0x1800dc16c  jz      short loc_1800DC179
0x1800dc16e  cmp     [rbp+Type], edi
0x1800dc171  jnz     short loc_1800DC179
0x1800dc173  mov     cs:SpinCount, eax
0x1800dc179  mov     rcx, [rbp+hKey]; hKey
0x1800dc17d  call    cs:__imp_RegCloseKey
0x1800dc184  nop     dword ptr [rax+rax+00h]
0x1800dc189  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc190  lea     rbx, WPP_GLOBAL_Control
0x1800dc197  cmp     rcx, rbx
0x1800dc19a  jz      loc_1800DC241
0x1800dc1a0  mov     dil, 80h
0x1800dc1a3  test    [rcx+1Ch], dil
0x1800dc1a7  jz      short loc_1800DC1C5
0x1800dc1a9  mov     rcx, [rcx+10h]
0x1800dc1ad  lea     r8, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids
0x1800dc1b4  mov     edx, 10h
0x1800dc1b9  call    WPP_SF_
0x1800dc1be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc1c5  cmp     rcx, rbx
0x1800dc1c8  jz      short loc_1800DC241
0x1800dc1ca  test    [rcx+1Ch], dil
0x1800dc1ce  jz      short loc_1800DC1F3
0x1800dc1d0  mov     r9d, cs:?LsaTuningParameters@@3U_LSA_TUNING_PARAMETERS@@A; _LSA_TUNING_PARAMETERS LsaTuningParameters
0x1800dc1d7  lea     r8, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids
0x1800dc1de  mov     rcx, [rcx+10h]
0x1800dc1e2  mov     edx, 11h
0x1800dc1e7  call    WPP_SF_d
0x1800dc1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc1f3  cmp     rcx, rbx
0x1800dc1f6  jz      short loc_1800DC241
0x1800dc1f8  test    [rcx+1Ch], dil
0x1800dc1fc  jz      short loc_1800DC221
0x1800dc1fe  mov     r9d, dword ptr cs:qword_18019E1CC
0x1800dc205  lea     r8, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids
0x1800dc20c  mov     rcx, [rcx+10h]
0x1800dc210  mov     edx, 12h
0x1800dc215  call    WPP_SF_d
0x1800dc21a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc221  cmp     rcx, rbx
0x1800dc224  jz      short loc_1800DC241
0x1800dc226  test    [rcx+1Ch], dil
0x1800dc22a  jz      short loc_1800DC241
0x1800dc22c  mov     rcx, [rcx+10h]
0x1800dc230  lea     r8, WPP_6da7ad4de1d53458cd6e48998fc9fcf1_Traceguids
0x1800dc237  mov     edx, 13h
0x1800dc23c  call    WPP_SF_
0x1800dc241  add     rsp, 40h
0x1800dc245  pop     rdi
0x1800dc246  pop     rbx
0x1800dc247  pop     rbp
0x1800dc248  retn
```
