# PackagedCreateProcess::GetMatchingAppExtensionIfPresent(ushort const *,_FILE_ID_INFO const &,ushort const *,ushort const *,bool,ushort const *,ushort const *,StateRepository::Cache::Entity::Application_NoThrow const &,ushort const *,StateRepository::Cache::Manager_NoThrow &,ExtendedPackagedAppContext *,bool)

- ea: `0x180133c10`
- end: `0x18013401c`
- name: `?GetMatchingAppExtensionIfPresent@PackagedCreateProcess@@CAJPEBGAEBU_FILE_ID_INFO@@00_N00AEBVApplication_NoThrow@Entity@Cache@StateRepository@@0AEAVManager_NoThrow@56@PEAVExtendedPackagedAppContext@@2@Z`
- size: `1036`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _FILE_ID_INFO *, const unsigned __int16 *, const unsigned __int16 *, bool, const unsigned __int16 *, const unsigned __int16 *, const struct StateRepository::Cache::Entity::Application_NoThrow *, wchar_t *String2, struct StateRepository::Cache::Manager_NoThrow *, struct ExtendedPackagedAppContext *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180160dfc`
- `0x1801611cc`

## callees

- `0x1800162c0`
- `0x18005b2c4`
- `0x1800cfedc`
- `0x1800d02f0`
- `0x180111ef8`
- `0x18011387c`
- `0x180133c10`
- `0x180134024`
- `0x180161550`
- `0x180161f10`
- `0x180161f90`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180133d5f`
- `ntdll!_wcsicmp` at `0x180133d86`
- `ntdll!_wcsicmp` at `0x180133e0a`
- `ntdll!_wcsicmp` at `0x180133f5c`
- `ntdll!_wcsicmp` at `0x180133d5f`
- `ntdll!_wcsicmp` at `0x180133d86`
- `ntdll!_wcsicmp` at `0x180133e0a`
- `ntdll!_wcsicmp` at `0x180133f5c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180133cac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180133f95`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180133cac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180133f95`

## string_xrefs

- `0x180133c89`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180133d11`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180133fc1`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180133fff`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180133c71`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall PackagedCreateProcess::GetMatchingAppExtensionIfPresent(
        const unsigned __int16 *a1,
        const struct _FILE_ID_INFO *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const struct StateRepository::Cache::Entity::Application_NoThrow *a8,
        wchar_t *String2,
        struct StateRepository::Cache::Manager_NoThrow *a10,
        struct ExtendedPackagedAppContext *a11,
        bool a12)
{
  const struct StateRepository::Cache::Entity::Application_NoThrow *v12; // r15
  unsigned __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rdx
  int MatchingPackageLocation; // ebx
  __int64 v17; // rcx
  __int64 v19; // rdx
  struct ExtendedPackagedAppContext *v20; // rdi
  wchar_t *v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // r8
  const unsigned __int16 *v24; // r14
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  bool *pszPath; // [rsp+28h] [rbp-E0h]
  int pszPatha; // [rsp+28h] [rbp-E0h]
  bool v31[8]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  __m256i v34; // [rsp+70h] [rbp-98h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-78h]
  __int128 v36; // [rsp+98h] [rbp-70h]
  __int128 v37; // [rsp+A8h] [rbp-60h]
  __int64 v38; // [rsp+B8h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-48h]
  __int128 v40; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-30h]
  __int64 v42; // [rsp+E0h] [rbp-28h]
  wchar_t *v43[2]; // [rsp+E8h] [rbp-20h]
  __int128 v44; // [rsp+F8h] [rbp-10h]
  __int64 v45; // [rsp+108h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v12 = a8;
  v32 = 0;
  LODWORD(v33) = 0;
  v13 = *(_QWORD *)a8;
  v34.m256i_i64[0] = 0;
  v14 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(
          (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v32,
          a10,
          v13);
  MatchingPackageLocation = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v14,
      (int)pszPath);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      pszPatha);
LABEL_3:
    v17 = v32;
    v32 = 0;
LABEL_4:
    if ( v17 )
      SRCacheContext_Close(v17);
    return (unsigned int)MatchingPackageLocation;
  }
  v39 = 0;
  memset(&v34.m256i_u64[1], 0, 24);
  v36 = 0;
  v37 = 0;
  String1 = 0;
  v38 = 0;
  LOBYTE(a8) = 0;
  MatchingPackageLocation = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
                              &v32,
                              v15,
                              &v34.m256i_u64[1],
                              &a8);
  if ( MatchingPackageLocation < 0 )
  {
    v19 = 267;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
LABEL_10:
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
    goto LABEL_3;
  }
  v20 = a11;
  while ( 1 )
  {
    if ( !(_BYTE)a8 )
      goto LABEL_44;
    v21 = String1;
    if ( !_wcsicmp(String1, L"Windows.AppExecutionAlias") || !a12 && !_wcsicmp(v21, L"Windows.FullTrustProcess") )
    {
      v22 = v36;
      if ( (_QWORD)v36 )
        break;
    }
LABEL_23:
    LODWORD(v33) = v33 + 1;
    MatchingPackageLocation = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
                                &v32,
                                v22,
                                &v34.m256i_u64[1],
                                &a8);
    if ( MatchingPackageLocation < 0 )
    {
      v19 = 312;
      goto LABEL_9;
    }
  }
  pszPath = v31;
  v40 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v31[0] = 0;
  v41 = 0;
  v42 = 0;
  v45 = 0;
  MatchingPackageLocation = StateRepository::Cache::Entity::Activation_NoThrow::Get(a10, v36, v23, &v40);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 287;
    goto LABEL_50;
  }
  if ( !v31[0] )
    goto LABEL_22;
  v24 = v43[0];
  if ( !_wcsicmp(v43[0], String2) )
    goto LABEL_22;
  v31[0] = 0;
  MatchingPackageLocation = PackagedCreateProcess::GetMatchingPackageLocation(a1, a2, v24, a3, a4, a5, a6, a7, v20, v31);
  if ( MatchingPackageLocation < 0 )
  {
    v25 = 296;
    goto LABEL_48;
  }
  if ( !v31[0] )
  {
LABEL_22:
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    goto LABEL_23;
  }
  MatchingPackageLocation = StringCchCopyW((unsigned __int16 *)v20 + 1, 0x82u, *((const unsigned __int16 **)v12 + 4));
  if ( MatchingPackageLocation < 0 )
  {
    v25 = 300;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
    v17 = v32;
    v32 = 0;
    goto LABEL_4;
  }
  if ( (v41 & 0x40) != 0 && (v41 & 0x100) != 0 )
  {
    v26 = 3;
  }
  else if ( (v41 & 8) != 0 && (v41 & 0x100) != 0 )
  {
    v26 = 2;
  }
  else if ( (v41 & 0x10) != 0 || (v41 & 0x200) != 0 )
  {
    v26 = 4;
  }
  else if ( (v41 & 0x20) != 0 )
  {
    v26 = 5;
  }
  else
  {
    v26 = ((unsigned int)v41 >> 8) & 1;
  }
  *((_DWORD *)v20 + 137) = v26;
  MatchingPackageLocation = ExtendedPackagedAppContext::SetExeLocation(v20, v24);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 302;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)MatchingPackageLocation,
      (int)pszPath);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
    goto LABEL_10;
  }
  MatchingPackageLocation = ExtendedPackagedAppContext::SetCategory(v20, v21);
  if ( MatchingPackageLocation < 0 )
  {
    v27 = 303;
    goto LABEL_50;
  }
  *((_BYTE *)v20 + 544) = _wcsicmp(v21, L"Windows.AppExecutionAlias") == 0;
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v40);
LABEL_44:
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v34.m256i_u64[1]);
  v28 = v32;
  v32 = 0;
  if ( v28 )
    SRCacheContext_Close(v28);
  return 0;
}

```

## disassembly

```asm
0x180133c10  mov     rax, rsp
0x180133c13  mov     [rax+20h], r9
0x180133c17  mov     [rax+18h], r8
0x180133c1b  mov     [rax+10h], rdx
0x180133c1f  mov     [rax+8], rcx
0x180133c23  push    rbp
0x180133c24  push    rbx
0x180133c25  push    rsi
0x180133c26  push    rdi
0x180133c27  push    r12
0x180133c29  push    r13
0x180133c2b  push    r14
0x180133c2d  push    r15
0x180133c2f  lea     rbp, [rax-58h]
0x180133c33  sub     rsp, 118h
0x180133c3a  mov     r15, [rbp+50h+arg_38]
0x180133c41  lea     rcx, [rsp+150h+var_F8]; this
0x180133c46  mov     rdx, [rbp+50h+arg_48]; struct StateRepository::Cache::Manager_NoThrow *
0x180133c4d  xor     r14d, r14d
0x180133c50  mov     [rsp+150h+var_F8], r14
0x180133c55  mov     dword ptr [rsp+150h+var_F0], r14d
0x180133c5a  mov     r8, [r15]; __int64
0x180133c5d  mov     qword ptr [rsp+150h+var_E8], r14
0x180133c62  call    ?OpenByApplication@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplication(StateRepository::Cache::Manager_NoThrow &,__int64)
0x180133c67  mov     ebx, eax
0x180133c69  test    eax, eax
0x180133c6b  jns     short loc_180133CBF
0x180133c6d  mov     rcx, [rbp+58h]; this
0x180133c71  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180133c78  mov     r9d, eax; char *
0x180133c7b  mov     edx, 3AFh; void *
0x180133c80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133c85  mov     rcx, [rbp+58h]; this
0x180133c89  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180133c90  mov     r9d, ebx; char *
0x180133c93  mov     edx, 106h; void *
0x180133c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133c9d  mov     rcx, [rsp+150h+var_F8]
0x180133ca2  mov     [rsp+150h+var_F8], r14
0x180133ca7  test    rcx, rcx
0x180133caa  jz      short loc_180133CB8
0x180133cac  call    cs:__imp_SRCacheContext_Close
0x180133cb3  nop     dword ptr [rax+rax+00h]
0x180133cb8  mov     eax, ebx
0x180133cba  jmp     loc_180133FA3
0x180133cbf  xorps   xmm0, xmm0
0x180133cc2  mov     [rbp+50h+var_98], r14
0x180133cc6  xorps   xmm1, xmm1
0x180133cc9  movdqa  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x180133ccf  lea     r9, [rbp+50h+arg_38]
0x180133cd6  movdqa  [rbp+50h+var_C0], xmm0
0x180133cdb  lea     r8, [rsp+150h+var_E8+8]
0x180133ce0  movdqa  [rbp+50h+var_B0], xmm1
0x180133ce5  lea     rcx, [rsp+150h+var_F8]
0x180133cea  mov     [rbp+50h+var_D0], r14
0x180133cee  mov     [rbp+50h+String1], r14
0x180133cf2  mov     [rbp+50h+var_A0], r14
0x180133cf6  mov     byte ptr [rbp+50h+arg_38], r14b
0x180133cfd  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x180133d02  mov     ebx, eax
0x180133d04  test    eax, eax
0x180133d06  jns     short loc_180133D2F
0x180133d08  mov     edx, 10Bh; void *
0x180133d0d  mov     rcx, [rbp+58h]; this
0x180133d11  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180133d18  mov     r9d, ebx; char *
0x180133d1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133d20  lea     rcx, [rsp+150h+var_E8+8]; this
0x180133d25  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180133d2a  jmp     loc_180133C9D
0x180133d2f  mov     rdi, [rbp+50h+arg_50]
0x180133d36  mov     r12, [rbp+50h+arg_30]
0x180133d3d  mov     r13, [rbp+50h+arg_28]
0x180133d44  cmp     byte ptr [rbp+50h+arg_38], r14b
0x180133d4b  jz      loc_180133F7C
0x180133d51  mov     rsi, [rbp+50h+String1]
0x180133d55  lea     rdx, aWindowsAppexec; "Windows.AppExecutionAlias"
0x180133d5c  mov     rcx, rsi; String1
0x180133d5f  call    cs:__imp__wcsicmp
0x180133d66  nop     dword ptr [rax+rax+00h]
0x180133d6b  test    eax, eax
0x180133d6d  jz      short loc_180133D9A
0x180133d6f  cmp     [rbp+50h+arg_58], r14b
0x180133d76  jnz     loc_180133E7C
0x180133d7c  lea     rdx, aWindowsFulltru; "Windows.FullTrustProcess"
0x180133d83  mov     rcx, rsi; String1
0x180133d86  call    cs:__imp__wcsicmp
0x180133d8d  nop     dword ptr [rax+rax+00h]
0x180133d92  test    eax, eax
0x180133d94  jnz     loc_180133E7C
0x180133d9a  mov     rdx, qword ptr [rbp+50h+var_C0]
0x180133d9e  test    rdx, rdx
0x180133da1  jz      loc_180133E7C
0x180133da7  mov     rcx, [rbp+50h+arg_48]
0x180133dae  lea     rax, [rsp+150h+var_100]
0x180133db3  xorps   xmm0, xmm0
0x180133db6  mov     [rsp+150h+pszPath], rax; int
0x180133dbb  xorps   xmm1, xmm1
0x180133dbe  movdqa  [rbp+50h+var_90], xmm0
0x180133dc3  lea     r9, [rbp+50h+var_90]
0x180133dc7  movdqa  xmmword ptr [rbp+50h+var_70], xmm0
0x180133dcc  movdqa  [rbp+50h+var_60], xmm1
0x180133dd1  mov     [rsp+150h+var_100], r14b
0x180133dd6  mov     [rbp+50h+var_80], 0
0x180133dde  mov     [rbp+50h+var_78], r14
0x180133de2  mov     [rbp+50h+var_50], r14
0x180133de6  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180133deb  mov     ebx, eax
0x180133ded  test    eax, eax
0x180133def  js      loc_180133FF6
0x180133df5  cmp     [rsp+150h+var_100], r14b
0x180133dfa  jz      short loc_180133E73
0x180133dfc  mov     r14, [rbp+50h+var_70]
0x180133e00  mov     rdx, [rbp+50h+String2]; String2
0x180133e07  mov     rcx, r14; String1
0x180133e0a  call    cs:__imp__wcsicmp
0x180133e11  nop     dword ptr [rax+rax+00h]
0x180133e16  test    eax, eax
0x180133e18  jz      short loc_180133E70
0x180133e1a  mov     r9, [rbp+50h+arg_10]; unsigned __int16 *
0x180133e1e  lea     rax, [rsp+150h+var_100]
0x180133e23  mov     rdx, [rbp+50h+arg_8]; struct _FILE_ID_INFO *
0x180133e27  mov     r8, r14; unsigned __int16 *
0x180133e2a  mov     rcx, [rbp+50h+arg_0]; unsigned __int16 *
0x180133e2e  mov     [rsp+150h+var_108], rax; bool *
0x180133e33  mov     al, [rbp+50h+arg_20]
0x180133e39  mov     [rsp+150h+var_110], rdi; struct ExtendedPackagedAppContext *
0x180133e3e  mov     [rsp+150h+var_118], r12; unsigned __int16 *
0x180133e43  mov     [rsp+150h+var_120], r13; unsigned __int16 *
0x180133e48  mov     [rsp+150h+var_128], al; bool
0x180133e4c  mov     rax, [rbp+50h+arg_18]
0x180133e50  mov     [rsp+150h+pszPath], rax; int
0x180133e55  mov     [rsp+150h+var_100], 0
0x180133e5a  call    ?GetMatchingPackageLocation@PackagedCreateProcess@@CAJPEBGAEBU_FILE_ID_INFO@@000_N00PEAVExtendedPackagedAppContext@@AEA_N@Z; PackagedCreateProcess::GetMatchingPackageLocation(ushort const *,_FILE_ID_INFO const &,ushort const *,ushort const *,ushort const *,bool,ushort const *,ushort const *,ExtendedPackagedAppContext *,bool &)
0x180133e5f  mov     ebx, eax
0x180133e61  test    eax, eax
0x180133e63  js      loc_180133FB8
0x180133e69  cmp     [rsp+150h+var_100], 0
0x180133e6e  jnz     short loc_180133EAA
0x180133e70  xor     r14d, r14d
0x180133e73  lea     rcx, [rbp+50h+var_90]; this
0x180133e77  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180133e7c  inc     dword ptr [rsp+150h+var_F0]
0x180133e80  lea     r9, [rbp+50h+arg_38]
0x180133e87  lea     r8, [rsp+150h+var_E8+8]
0x180133e8c  lea     rcx, [rsp+150h+var_F8]
0x180133e91  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x180133e96  mov     ebx, eax
0x180133e98  test    eax, eax
0x180133e9a  jns     loc_180133D44
0x180133ea0  mov     edx, 138h
0x180133ea5  jmp     loc_180133D0D
0x180133eaa  mov     r8, [r15+20h]; unsigned __int16 *
0x180133eae  lea     rcx, [rdi+2]; unsigned __int16 *
0x180133eb2  mov     edx, 82h; unsigned __int64
0x180133eb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180133ebc  mov     ebx, eax
0x180133ebe  test    eax, eax
0x180133ec0  jns     short loc_180133ECC
0x180133ec2  mov     edx, 12Ch
0x180133ec7  jmp     loc_180133FBD
0x180133ecc  mov     eax, dword ptr [rbp+50h+var_80]
0x180133ecf  test    al, 40h
0x180133ed1  jz      short loc_180133EE0
0x180133ed3  bt      eax, 8
0x180133ed7  jnb     short loc_180133EE0
0x180133ed9  mov     eax, 3
0x180133ede  jmp     short loc_180133F13
0x180133ee0  test    al, 8
0x180133ee2  jz      short loc_180133EF1
0x180133ee4  bt      eax, 8
0x180133ee8  jnb     short loc_180133EF1
0x180133eea  mov     eax, 2
0x180133eef  jmp     short loc_180133F13
0x180133ef1  test    al, 10h
0x180133ef3  jnz     short loc_180133F0E
0x180133ef5  bt      eax, 9
0x180133ef9  jb      short loc_180133F0E
0x180133efb  test    al, 20h
0x180133efd  jz      short loc_180133F06
0x180133eff  mov     eax, 5
0x180133f04  jmp     short loc_180133F13
0x180133f06  shr     eax, 8
0x180133f09  and     eax, 1
0x180133f0c  jmp     short loc_180133F13
0x180133f0e  mov     eax, 4
0x180133f13  mov     rdx, r14; unsigned __int16 *
0x180133f16  mov     [rdi+224h], eax
0x180133f1c  mov     rcx, rdi; this
0x180133f1f  call    ?SetExeLocation@ExtendedPackagedAppContext@@QEAAJPEBG@Z; ExtendedPackagedAppContext::SetExeLocation(ushort const *)
0x180133f24  xor     r14d, r14d
0x180133f27  mov     ebx, eax
0x180133f29  test    eax, eax
0x180133f2b  jns     short loc_180133F37
0x180133f2d  mov     edx, 12Eh
0x180133f32  jmp     loc_180133FFB
0x180133f37  mov     rdx, rsi; unsigned __int16 *
0x180133f3a  mov     rcx, rdi; this
0x180133f3d  call    ?SetCategory@ExtendedPackagedAppContext@@QEAAJPEBG@Z; ExtendedPackagedAppContext::SetCategory(ushort const *)
0x180133f42  mov     ebx, eax
0x180133f44  test    eax, eax
0x180133f46  jns     short loc_180133F52
0x180133f48  mov     edx, 12Fh
0x180133f4d  jmp     loc_180133FFB
0x180133f52  lea     rdx, aWindowsAppexec; "Windows.AppExecutionAlias"
0x180133f59  mov     rcx, rsi; String1
0x180133f5c  call    cs:__imp__wcsicmp
0x180133f63  nop     dword ptr [rax+rax+00h]
0x180133f68  test    eax, eax
0x180133f6a  lea     rcx, [rbp+50h+var_90]; this
0x180133f6e  setz    al
0x180133f71  mov     [rdi+220h], al
0x180133f77  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180133f7c  lea     rcx, [rsp+150h+var_E8+8]; this
0x180133f81  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180133f86  mov     rcx, [rsp+150h+var_F8]
0x180133f8b  mov     [rsp+150h+var_F8], r14
0x180133f90  test    rcx, rcx
0x180133f93  jz      short loc_180133FA1
0x180133f95  call    cs:__imp_SRCacheContext_Close
0x180133f9c  nop     dword ptr [rax+rax+00h]
0x180133fa1  xor     eax, eax
0x180133fa3  add     rsp, 118h
0x180133faa  pop     r15
0x180133fac  pop     r14
0x180133fae  pop     r13
0x180133fb0  pop     r12
0x180133fb2  pop     rdi
0x180133fb3  pop     rsi
0x180133fb4  pop     rbx
0x180133fb5  pop     rbp
0x180133fb6  retn
0x180133fb8  mov     edx, 128h; void *
0x180133fbd  mov     rcx, [rbp+58h]; this
0x180133fc1  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180133fc8  mov     r9d, ebx; char *
0x180133fcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133fd0  lea     rcx, [rbp+50h+var_90]; this
0x180133fd4  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180133fd9  lea     rcx, [rsp+150h+var_E8+8]; this
0x180133fde  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180133fe3  mov     rcx, [rsp+150h+var_F8]
0x180133fe8  mov     [rsp+150h+var_F8], 0
0x180133ff1  jmp     loc_180133CA7
0x180133ff6  mov     edx, 11Fh; void *
0x180133ffb  mov     rcx, [rbp+58h]; this
0x180133fff  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180134006  mov     r9d, ebx; char *
0x180134009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013400e  lea     rcx, [rbp+50h+var_90]; this
0x180134012  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180134017  jmp     loc_180133D20
```
