# PackagedCreateProcess::CheckIfValidCall(void *,ushort const *,bool &)

- ea: `0x1800287a4`
- end: `0x180028b7d`
- name: `?CheckIfValidCall@PackagedCreateProcess@@CAJPEAXPEBGAEA_N@Z`
- size: `985`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, wchar_t *String1, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028ee0`

## callees

- `0x180028368`
- `0x1800284a0`
- `0x1800286d4`
- `0x1800287a4`
- `0x18002fd98`
- `0x180032f18`
- `0x180032fd0`
- `0x180033800`
- `0x180034118`
- `0x180048f30`
- `0x180058768`
- `0x180107b98`
- `0x180123770`
- `0x180125f74`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800288a4`
- `ntdll!_wcsicmp` at `0x1800288a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180028951`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180028951`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028975`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800289c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028abd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028af8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028975`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800289c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028abd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180028af8`

## string_xrefs

- `0x18002882a`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x1800289a9`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180028a5a`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180028a8b`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180028b0c`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180028986`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`

## pseudocode

```c
__int64 __fastcall PackagedCreateProcess::CheckIfValidCall(HANDLE TokenHandle, wchar_t *String1, bool *a3)
{
  HANDLE v5; // rdi
  unsigned int v6; // ebx
  HANDLE v7; // rcx
  bool v8; // cc
  LONG PackageFamilyNameFromToken; // eax
  unsigned int AppUserModelId; // ebx
  __int64 v12; // rcx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  bool *v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  ARI::ProcessToken::SysAppId *v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  int v26[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  __int128 v29; // [rsp+90h] [rbp-70h]
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  WCHAR packageFamilyName[72]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v34[68]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a3 = 0;
  hObject = 0;
  v5 = TokenHandle;
  if ( !TokenHandle )
  {
    v23[1] = 0;
    v23[0] = (ARI::ProcessToken::SysAppId *)&hObject;
    v24 = 1;
    v6 = wil::open_current_access_token_nothrow(&v23[1]);
    if ( v24 )
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(v23[0]);
    if ( (v6 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F8,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)v6,
        (int)v19);
      v7 = hObject;
      v8 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_6:
      if ( v8 )
        CloseHandle(v7);
      return v6;
    }
    v5 = hObject;
  }
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  PackageFamilyNameFromToken = GetPackageFamilyNameFromToken(v5, &packageFamilyNameLength, packageFamilyName);
  v6 = PackageFamilyNameFromToken;
  if ( PackageFamilyNameFromToken != 15700 )
  {
    if ( PackageFamilyNameFromToken )
    {
      if ( PackageFamilyNameFromToken > 0 )
        v6 = (unsigned __int16)PackageFamilyNameFromToken | 0x80070000;
      goto LABEL_36;
    }
    if ( _wcsicmp(String1, packageFamilyName) )
    {
      memset_0(v34, 0, 0x104u);
      if ( v5 )
      {
        *(_OWORD *)v23 = 0;
        AppUserModelId = ARI::ProcessToken::SysAppId::Open(v5, v23, &v23[1], 0, v19);
        if ( AppUserModelId )
        {
          if ( AppUserModelId == 1168 )
            AppUserModelId = 15703;
        }
        else
        {
          packageFamilyNameLength = 0;
          AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                             v23[1],
                             (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)0x82,
                             (unsigned int)&packageFamilyNameLength,
                             v34,
                             (unsigned __int16 *)v19);
        }
        ARI::ProcessToken::AutoSysAppId::~AutoSysAppId((ARI::ProcessToken::AutoSysAppId *)v23);
        if ( !AppUserModelId )
        {
          v20 = 0;
          v23[0] = (ARI::ProcessToken::SysAppId *)&v20;
          v23[1] = 0;
          v24 = 1;
          v6 = SRCacheManager_Open(0, &v23[1]);
          if ( v24 )
          {
            v12 = *(_QWORD *)v23[0];
            *(_QWORD *)v23[0] = v23[1];
            if ( v12 )
              SRCacheManager_Close(v12);
          }
          if ( (v6 & 0x80000000) == 0 )
          {
            v25 = 0;
            v16 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
                    (struct StateRepository::Cache::Manager_NoThrow *)&v20,
                    0,
                    &v25);
            v6 = v16;
            if ( v16 >= 0 )
            {
              *(_OWORD *)v26 = 0;
              v27 = 0;
              v28 = 0;
              v29 = 0;
              v30 = 0;
              v31 = 0;
              v32 = 0;
              v17 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
                      (struct StateRepository::Cache::Manager_NoThrow *)&v20,
                      v25,
                      (const unsigned __int16 *)v34);
              v6 = v17;
              if ( v17 >= 0 )
              {
                v6 = -2147023728;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x316,
                  (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                  (const char *)0x80070490LL,
                  (int)v26);
                StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v26);
                v18 = v20;
                v20 = 0;
                if ( v18 )
                  SRCacheManager_Close(v18);
                v7 = hObject;
                v8 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
                goto LABEL_6;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x315,
                (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                (const char *)(unsigned int)v17,
                (int)v26);
              StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v26);
              goto LABEL_25;
            }
            v13 = (unsigned int)v16;
            v14 = 786;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA5,
              (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
              (const char *)v6,
              (int)v19);
            v13 = v6;
            v14 = 784;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
            (const char *)v13,
            (int)v19);
LABEL_25:
          v15 = v20;
          v20 = 0;
          if ( v15 )
            SRCacheManager_Close(v15);
          goto LABEL_36;
        }
      }
      else
      {
        AppUserModelId = 87;
      }
      v6 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x30E,
             (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
             (const char *)AppUserModelId,
             (unsigned int)v19);
LABEL_36:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return v6;
    }
  }
  *a3 = 1;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x1800287a4  mov     [rsp-8+arg_18], rbx
0x1800287a9  push    rbp
0x1800287aa  push    rsi
0x1800287ab  push    rdi
0x1800287ac  push    r14
0x1800287ae  push    r15
0x1800287b0  lea     rbp, [rsp-180h]
0x1800287b8  sub     rsp, 280h
0x1800287bf  mov     rax, cs:__security_cookie
0x1800287c6  xor     rax, rsp
0x1800287c9  mov     [rbp+1A0h+var_30], rax
0x1800287d0  xor     r15d, r15d
0x1800287d3  mov     rsi, r8
0x1800287d6  mov     [r8], r15b
0x1800287d9  mov     r14, rdx
0x1800287dc  mov     [rsp+2A0h+hObject], r15
0x1800287e1  mov     rdi, rcx
0x1800287e4  test    rcx, rcx
0x1800287e7  jnz     short loc_18002885E
0x1800287e9  lea     rax, [rsp+2A0h+hObject]
0x1800287ee  mov     [rsp+2A0h+var_250+8], r15
0x1800287f3  lea     rcx, [rsp+2A0h+var_250+8]
0x1800287f8  mov     [rsp+2A0h+var_250], rax
0x1800287fd  mov     [rsp+2A0h+var_240], 1
0x180028802  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x180028807  mov     ebx, eax
0x180028809  cmp     [rsp+2A0h+var_240], r15b
0x18002880e  jz      short loc_18002881F
0x180028810  mov     rdx, [rsp+2A0h+var_250+8]
0x180028815  mov     rcx, [rsp+2A0h+var_250]
0x18002881a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002881f  test    ebx, ebx
0x180028821  jns     short loc_180028859
0x180028823  mov     rcx, [rbp+1A8h]; this
0x18002882a  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180028831  mov     r9d, ebx; char *
0x180028834  mov     edx, 2F8h; void *
0x180028839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002883e  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180028843  lea     rax, [rcx-1]
0x180028847  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002884b  ja      short loc_180028852
0x18002884d  call    CloseHandle
0x180028852  mov     eax, ebx
0x180028854  jmp     loc_180028B57
0x180028859  mov     rdi, [rsp+2A0h+hObject]
0x18002885e  xor     edx, edx; Val
0x180028860  lea     rcx, [rbp+1A0h+packageFamilyName]; void *
0x180028864  mov     r8d, 82h; Size
0x18002886a  call    memset_0
0x18002886f  lea     r8, [rbp+1A0h+packageFamilyName]; packageFamilyName
0x180028873  mov     [rsp+2A0h+packageFamilyNameLength], 41h ; 'A'
0x18002887b  lea     rdx, [rsp+2A0h+packageFamilyNameLength]; packageFamilyNameLength
0x180028880  mov     rcx, rdi; token
0x180028883  call    GetPackageFamilyNameFromToken
0x180028888  mov     ebx, eax
0x18002888a  cmp     eax, 3D54h
0x18002888f  jz      loc_180028B3E
0x180028895  test    eax, eax
0x180028897  jnz     loc_180028B31
0x18002889d  lea     rdx, [rbp+1A0h+packageFamilyName]; String2
0x1800288a1  mov     rcx, r14; String1
0x1800288a4  call    cs:__imp__wcsicmp
0x1800288aa  test    eax, eax
0x1800288ac  jz      loc_180028B3E
0x1800288b2  xor     edx, edx; Val
0x1800288b4  lea     rcx, [rbp+1A0h+var_140]; void *
0x1800288b8  mov     r8d, 104h; Size
0x1800288be  call    memset_0
0x1800288c3  test    rdi, rdi
0x1800288c6  jz      loc_180028B00
0x1800288cc  xorps   xmm0, xmm0
0x1800288cf  lea     r8, [rsp+2A0h+var_250+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x1800288d4  xor     r9d, r9d; struct _TOKEN_SECURITY_ATTRIBUTE_V1 **
0x1800288d7  lea     rdx, [rsp+2A0h+var_250]; void *
0x1800288dc  mov     rcx, rdi; TokenHandle
0x1800288df  movdqu  xmmword ptr [rsp+2A0h+var_250], xmm0
0x1800288e5  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x1800288ea  mov     ebx, eax
0x1800288ec  test    eax, eax
0x1800288ee  jnz     short loc_180028911
0x1800288f0  mov     rcx, [rsp+2A0h+var_250+8]; this
0x1800288f5  lea     r9, [rbp+1A0h+var_140]; unsigned int *
0x1800288f9  lea     r8, [rsp+2A0h+packageFamilyNameLength]; unsigned int
0x1800288fe  mov     [rsp+2A0h+packageFamilyNameLength], r15d
0x180028903  mov     edx, 82h; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x180028908  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x18002890d  mov     ebx, eax
0x18002890f  jmp     short loc_18002891F
0x180028911  cmp     ebx, 490h
0x180028917  mov     eax, 3D57h
0x18002891c  cmovz   ebx, eax
0x18002891f  lea     rcx, [rsp+2A0h+var_250]; this
0x180028924  call    ??1AutoSysAppId@ProcessToken@ARI@@QEAA@XZ; ARI::ProcessToken::AutoSysAppId::~AutoSysAppId(void)
0x180028929  test    ebx, ebx
0x18002892b  jnz     loc_180028B05
0x180028931  lea     rax, [rsp+2A0h+var_268]
0x180028936  mov     [rsp+2A0h+var_268], r15
0x18002893b  lea     rdx, [rsp+2A0h+var_250+8]
0x180028940  mov     [rsp+2A0h+var_250], rax
0x180028945  xor     ecx, ecx
0x180028947  mov     [rsp+2A0h+var_250+8], r15
0x18002894c  mov     [rsp+2A0h+var_240], 1
0x180028951  call    cs:__imp_SRCacheManager_Open
0x180028957  mov     ebx, eax
0x180028959  cmp     [rsp+2A0h+var_240], r15b
0x18002895e  jz      short loc_18002897B
0x180028960  mov     r8, [rsp+2A0h+var_250]
0x180028965  mov     rdx, [rsp+2A0h+var_250+8]
0x18002896a  mov     rcx, [r8]
0x18002896d  mov     [r8], rdx
0x180028970  test    rcx, rcx
0x180028973  jz      short loc_18002897B
0x180028975  call    cs:__imp_SRCacheManager_Close
0x18002897b  test    ebx, ebx
0x18002897d  jns     short loc_1800289D3
0x18002897f  mov     rcx, [rbp+1A8h]; this
0x180028986  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002898d  mov     r9d, ebx; char *
0x180028990  mov     edx, 0A5h; void *
0x180028995  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002899a  mov     r9d, ebx; char *
0x18002899d  mov     edx, 310h; void *
0x1800289a2  mov     rcx, [rbp+1A8h]; this
0x1800289a9  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x1800289b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800289b5  mov     rcx, [rsp+2A0h+var_268]
0x1800289ba  mov     [rsp+2A0h+var_268], r15
0x1800289bf  test    rcx, rcx
0x1800289c2  jz      loc_180028B22
0x1800289c8  call    cs:__imp_SRCacheManager_Close
0x1800289ce  jmp     loc_180028B22
0x1800289d3  lea     r8, [rsp+2A0h+var_238]; __int64 *
0x1800289d8  mov     [rsp+2A0h+var_238], r15
0x1800289dd  xor     edx, edx; void *
0x1800289df  lea     rcx, [rsp+2A0h+var_268]; struct StateRepository::Cache::Manager_NoThrow *
0x1800289e4  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x1800289e9  mov     ebx, eax
0x1800289eb  test    eax, eax
0x1800289ed  jns     short loc_1800289F9
0x1800289ef  mov     r9d, eax
0x1800289f2  mov     edx, 312h
0x1800289f7  jmp     short loc_1800289A2
0x1800289f9  mov     rdx, [rsp+2A0h+var_238]
0x1800289fe  lea     rax, [rsp+2A0h+var_270]
0x180028a03  xorps   xmm0, xmm0
0x180028a06  mov     [rsp+2A0h+var_278], rax
0x180028a0b  xorps   xmm1, xmm1
0x180028a0e  movdqa  xmmword ptr [rsp+2A0h+var_230], xmm0
0x180028a14  lea     rax, [rsp+2A0h+var_230]
0x180028a19  mov     [rbp+1A0h+var_220], r15
0x180028a1d  lea     r8, [rbp+1A0h+var_140]
0x180028a21  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180028a26  lea     rcx, [rsp+2A0h+var_268]
0x180028a2b  mov     [rbp+1A0h+var_218], r15
0x180028a2f  movdqa  [rbp+1A0h+var_210], xmm0
0x180028a34  movdqa  [rbp+1A0h+var_200], xmm1
0x180028a39  movdqa  [rbp+1A0h+var_1F0], xmm0
0x180028a3e  movdqa  [rbp+1A0h+var_1E0], xmm1
0x180028a43  mov     [rsp+2A0h+var_270], r15b
0x180028a48  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180028a4d  mov     ebx, eax
0x180028a4f  test    eax, eax
0x180028a51  jns     short loc_180028A7D
0x180028a53  mov     rcx, [rbp+1A8h]; this
0x180028a5a  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180028a61  mov     r9d, eax; char *
0x180028a64  mov     edx, 315h; void *
0x180028a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a6e  lea     rcx, [rsp+2A0h+var_230]; this
0x180028a73  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180028a78  jmp     loc_1800289B5
0x180028a7d  cmp     [rsp+2A0h+var_270], r15b
0x180028a82  jnz     short loc_180028AD5
0x180028a84  mov     rcx, [rbp+1A8h]; this
0x180028a8b  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180028a92  mov     ebx, 80070490h
0x180028a97  mov     edx, 316h; void *
0x180028a9c  mov     r9d, ebx; char *
0x180028a9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028aa4  lea     rcx, [rsp+2A0h+var_230]; this
0x180028aa9  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180028aae  mov     rcx, [rsp+2A0h+var_268]
0x180028ab3  mov     [rsp+2A0h+var_268], r15
0x180028ab8  test    rcx, rcx
0x180028abb  jz      short loc_180028AC3
0x180028abd  call    cs:__imp_SRCacheManager_Close
0x180028ac3  mov     rcx, [rsp+2A0h+hObject]
0x180028ac8  lea     rdx, [rcx-1]
0x180028acc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180028ad0  jmp     loc_18002884B
0x180028ad5  mov     eax, dword ptr [rbp+1A0h+var_220+4]
0x180028ad8  lea     rcx, [rsp+2A0h+var_230]; this
0x180028add  shr     eax, 2
0x180028ae0  and     al, 1
0x180028ae2  mov     [rsi], al
0x180028ae4  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180028ae9  mov     rcx, [rsp+2A0h+var_268]
0x180028aee  mov     [rsp+2A0h+var_268], r15
0x180028af3  test    rcx, rcx
0x180028af6  jz      short loc_180028B41
0x180028af8  call    cs:__imp_SRCacheManager_Close
0x180028afe  jmp     short loc_180028B41
0x180028b00  mov     ebx, 57h ; 'W'
0x180028b05  mov     rcx, [rbp+1A8h]; this
0x180028b0c  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x180028b13  mov     r9d, ebx; char *
0x180028b16  mov     edx, 30Eh; void *
0x180028b1b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180028b20  mov     ebx, eax
0x180028b22  lea     rcx, [rsp+2A0h+hObject]
0x180028b27  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028b2c  jmp     loc_180028852
0x180028b31  jle     short loc_180028B22
0x180028b33  movzx   ebx, ax
0x180028b36  or      ebx, 80070000h
0x180028b3c  jmp     short loc_180028B22
0x180028b3e  mov     byte ptr [rsi], 1
0x180028b41  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180028b46  lea     rax, [rcx-1]
0x180028b4a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028b4e  ja      short loc_180028B55
0x180028b50  call    CloseHandle
0x180028b55  xor     eax, eax
0x180028b57  mov     rcx, [rbp+1A0h+var_30]
0x180028b5e  xor     rcx, rsp; StackCookie
0x180028b61  call    __security_check_cookie
0x180028b66  mov     rbx, [rsp+2A0h+arg_18]
0x180028b6e  add     rsp, 280h
0x180028b75  pop     r15
0x180028b77  pop     r14
0x180028b79  pop     rdi
0x180028b7a  pop     rsi
0x180028b7b  pop     rbp
0x180028b7c  retn
```
