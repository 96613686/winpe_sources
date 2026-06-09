# Microsoft::Resources::StateRepositoryHelper::IsPackageMetadataUnderSystemMetadata(ushort const *)

- ea: `0x1800a6818`
- end: `0x1800a6934`
- name: `?IsPackageMetadataUnderSystemMetadata@StateRepositoryHelper@Resources@Microsoft@@SA_NPEBG@Z`
- size: `284`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800564e0`

## callees

- `0x1800194e8`
- `0x180019588`
- `0x18002c8d0`
- `0x180070f4c`
- `0x1800a6818`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a68e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a6919`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a68e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a6919`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800a687b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800a687b`

## string_xrefs

- `0x1800a6894`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
bool __fastcall Microsoft::Resources::StateRepositoryHelper::IsPackageMetadataUnderSystemMetadata(
        const unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rcx
  bool v5; // bl
  __int64 v6; // rcx
  int v7; // [rsp+20h] [rbp-59h]
  __int64 *v8; // [rsp+30h] [rbp-49h] BYREF
  __int64 v9; // [rsp+38h] [rbp-41h] BYREF
  char v10; // [rsp+40h] [rbp-39h]
  __int128 v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 v12; // [rsp+60h] [rbp-19h]
  __int64 v13; // [rsp+68h] [rbp-11h]
  __int64 v14; // [rsp+70h] [rbp-9h]
  __int64 v15; // [rsp+78h] [rbp-1h]
  __int64 v16; // [rsp+80h] [rbp+7h]
  __int64 v17; // [rsp+88h] [rbp+Fh]
  __int128 v18; // [rsp+90h] [rbp+17h]
  int v19; // [rsp+A0h] [rbp+27h]
  __int64 v20; // [rsp+A8h] [rbp+2Fh]
  __int64 v21; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  char v23; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+F0h] [rbp+77h] BYREF

  v10 = 1;
  v24 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v8 = &v24;
  v9 = 0;
  v2 = SRCacheManager_Open(0, &v9);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v8);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v2,
      v7);
LABEL_4:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v11);
    v3 = v24;
    v24 = 0;
    if ( v3 )
      SRCacheManager_Close();
    return 0;
  }
  v23 = 0;
  if ( (int)StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(&v24, a1, 8, &v11, &v23) < 0 )
    goto LABEL_4;
  v5 = 0;
  if ( v23 )
    v5 = (v13 & 0x2000000000LL) != 0;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v11);
  v6 = v24;
  v24 = 0;
  if ( v6 )
    SRCacheManager_Close();
  return v5;
}

```

## disassembly

```asm
0x1800a6818  mov     [rsp-8+arg_0], rbx
0x1800a681d  push    rbp
0x1800a681e  push    rsi
0x1800a681f  push    rdi
0x1800a6820  lea     rbp, [rsp-47h]
0x1800a6825  sub     rsp, 0C0h
0x1800a682c  xor     esi, esi
0x1800a682e  mov     [rbp+57h+var_90], 1
0x1800a6832  xorps   xmm0, xmm0
0x1800a6835  mov     [rbp+57h+arg_10], rsi
0x1800a6839  mov     rdi, rcx
0x1800a683c  movdqa  [rbp+57h+var_80], xmm0
0x1800a6841  lea     rax, [rbp+57h+arg_10]
0x1800a6845  mov     [rbp+57h+var_70], rsi
0x1800a6849  xor     ecx, ecx
0x1800a684b  mov     [rbp+57h+var_68], rsi
0x1800a684f  lea     rdx, [rbp+57h+var_98]
0x1800a6853  mov     [rbp+57h+var_60], rsi
0x1800a6857  mov     [rbp+57h+var_58], rsi
0x1800a685b  mov     [rbp+57h+var_50], rsi
0x1800a685f  mov     [rbp+57h+var_48], rsi
0x1800a6863  movdqa  [rbp+57h+var_40], xmm0
0x1800a6868  mov     [rbp+57h+var_30], esi
0x1800a686b  mov     [rbp+57h+var_28], rsi
0x1800a686f  mov     [rbp+57h+var_20], rsi
0x1800a6873  mov     [rbp+57h+var_A0], rax
0x1800a6877  mov     [rbp+57h+var_98], rsi
0x1800a687b  call    cs:__imp_SRCacheManager_Open
0x1800a6881  lea     rcx, [rbp+57h+var_A0]
0x1800a6885  mov     ebx, eax
0x1800a6887  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x1800a688c  test    ebx, ebx
0x1800a688e  jns     short loc_1800A68AA
0x1800a6890  mov     rcx, [rbp+5Fh]; this
0x1800a6894  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a689b  mov     r9d, ebx; char *
0x1800a689e  mov     edx, 0A5h; void *
0x1800a68a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a68a8  jmp     short loc_1800A68D1
0x1800a68aa  lea     rax, [rbp+57h+arg_8]
0x1800a68ae  mov     [rbp+57h+arg_8], sil
0x1800a68b2  lea     r9, [rbp+57h+var_80]
0x1800a68b6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x1800a68bb  mov     r8d, 8
0x1800a68c1  lea     rcx, [rbp+57h+arg_10]
0x1800a68c5  mov     rdx, rdi
0x1800a68c8  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800a68cd  test    eax, eax
0x1800a68cf  jns     short loc_1800A68F1
0x1800a68d1  lea     rcx, [rbp+57h+var_80]; this
0x1800a68d5  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800a68da  mov     rcx, [rbp+57h+arg_10]
0x1800a68de  mov     [rbp+57h+arg_10], rsi
0x1800a68e2  test    rcx, rcx
0x1800a68e5  jz      short loc_1800A68ED
0x1800a68e7  call    cs:__imp_SRCacheManager_Close
0x1800a68ed  xor     al, al
0x1800a68ef  jmp     short loc_1800A6921
0x1800a68f1  mov     bl, sil
0x1800a68f4  cmp     [rbp+57h+arg_8], sil
0x1800a68f8  jz      short loc_1800A6903
0x1800a68fa  mov     ebx, dword ptr [rbp+57h+var_68+4]
0x1800a68fd  shr     ebx, 5
0x1800a6900  and     bl, 1
0x1800a6903  lea     rcx, [rbp+57h+var_80]; this
0x1800a6907  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800a690c  mov     rcx, [rbp+57h+arg_10]
0x1800a6910  mov     [rbp+57h+arg_10], rsi
0x1800a6914  test    rcx, rcx
0x1800a6917  jz      short loc_1800A691F
0x1800a6919  call    cs:__imp_SRCacheManager_Close
0x1800a691f  mov     al, bl
0x1800a6921  mov     rbx, [rsp+0D0h+arg_0]
0x1800a6929  add     rsp, 0C0h
0x1800a6930  pop     rdi
0x1800a6931  pop     rsi
0x1800a6932  pop     rbp
0x1800a6933  retn
```
