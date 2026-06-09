# AppXGetPackageSid

- ea: `0x18002c020`
- end: `0x18002c4cf`
- name: `AppXGetPackageSid`
- size: `1199`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002bfb0`
- `0x18002c020`
- `0x18002ddc0`
- `0x18002f738`
- `0x18002f994`
- `0x18002fba0`
- `0x180049460`
- `0x18004c240`
- `0x18004cb90`
- `0x180057f40`
- `0x180058768`
- `0x1800fe940`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002c292`
- `ntdll!RtlAllocateHeap` at `0x18002c292`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002c0bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002c0bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c26a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c440`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c490`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c26a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c440`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002c490`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c12c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c302`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c369`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c12c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c302`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002c369`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c2d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c2e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c34a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c3bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c3ce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c2d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c2e3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c337`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c34a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c3bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18002c3ce`

## string_xrefs

- `0x18002c37d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c41e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002c3ec`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18002c0ed`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`

## pseudocode

```c
__int64 __fastcall AppXGetPackageSid(unsigned __int16 *a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v8; // di
  __int64 v9; // rsi
  int v10; // eax
  bool v11; // di
  __int64 v12; // rcx
  PSID v13; // rbx
  ReservedForLocalUse *v14; // rcx
  void *Heap; // rax
  SIZE_T v16; // r8
  PVOID v17; // rdi
  DWORD LengthSid; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  bool v35; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-B8h]
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  char v40; // [rsp+58h] [rbp-A8h]
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h]
  __int128 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+88h] [rbp-78h]
  __int64 v45; // [rsp+90h] [rbp-70h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  __int128 v47; // [rsp+A0h] [rbp-60h]
  int v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  __int64 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v52[72]; // [rsp+E0h] [rbp-20h] BYREF
  PSID pSid; // [rsp+128h] [rbp+28h]
  __int64 v54; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( !a2 || !a1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
      (const char *)0x80070057LL,
      v31);
    return v4;
  }
  v36 = 0;
  v38 = &v36;
  v39 = 0;
  v40 = 1;
  v4 = SRCacheManager_Open(0, &v39);
  if ( v40 )
  {
    v6 = *v38;
    *v38 = v39;
    if ( v6 )
      SRCacheManager_Close(v6);
  }
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)v4,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
      (const char *)v4,
      v32);
    goto LABEL_10;
  }
  v42 = 0;
  v41 = 0;
  v47 = 0;
  v44 = 0;
  v45 = 0;
  v43 = 0;
  v46 = 0;
  v8 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v35 = 0;
  v37 = 0;
  v4 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v36,
         a1,
         &v37);
  if ( (v4 & 0x80000000) != 0 )
  {
    v27 = 1165;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)v4,
      v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
      (const char *)v4,
      v34);
    goto LABEL_44;
  }
  if ( !v37 )
    goto LABEL_16;
  v4 = StateRepository::Cache::Entity::Package_NoThrow::Get(&v36, v37, 2, (__int64 *)&v41, &v35);
  if ( (v4 & 0x80000000) != 0 )
  {
    v27 = 1168;
    goto LABEL_46;
  }
  v8 = v35;
LABEL_16:
  if ( v8 )
  {
    v51 = 0;
    memset_0(v52, 0, 0x44u);
    v9 = v42;
    pSid = 0;
    v54 = 0;
    v35 = 0;
    if ( v42 )
    {
      v37 = 0;
      v10 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v36,
              v42,
              (struct StateRepository::Cache::Context_NoThrow *)&v37,
              &v35);
      v4 = v10;
      if ( v10 < 0 )
      {
        v28 = 175;
      }
      else
      {
        v11 = v35;
        if ( !v35 )
        {
          v30 = v37;
          v37 = 0;
          if ( v30 )
            SRCacheContext_Close(v30);
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xDC,
            (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
            (const char *)0x80070002LL,
            v31);
          v22 = v54;
          v54 = 0;
          if ( v22 )
            SRCache_Free(v22);
          v23 = *((_QWORD *)&v51 + 1);
          *((_QWORD *)&v51 + 1) = 0;
          if ( v23 )
            SRCache_Free(v23);
          goto LABEL_36;
        }
        v10 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(&v37, &v51, 2, v9);
        v4 = v10;
        if ( v10 >= 0 )
        {
          v12 = v37;
          v37 = 0;
          if ( v12 )
            SRCacheContext_Close(v12);
          if ( v11 )
          {
            v13 = pSid;
            GetLengthSid(pSid);
            Heap = ReservedForLocalUse::GetHeap(v14);
            v17 = RtlAllocateHeap(Heap, 0, v16);
            if ( v17 )
            {
              LengthSid = GetLengthSid(v13);
              CopySid(LengthSid, v17, v13);
              *a2 = v17;
              Common::GlobalHeap::Free(0);
              v19 = v54;
              v54 = 0;
              if ( v19 )
                SRCache_Free(v19);
              v20 = *((_QWORD *)&v51 + 1);
              *((_QWORD *)&v51 + 1) = 0;
              if ( v20 )
                SRCache_Free(v20);
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
              v21 = v36;
              v36 = 0;
              if ( v21 )
                SRCacheManager_Close(v21);
              return 0;
            }
            v4 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE0,
              (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
              (const char *)0x8007000ELL,
              v31);
            Common::GlobalHeap::Free(0);
            StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v51);
LABEL_44:
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
LABEL_10:
            v7 = v36;
            v36 = 0;
            if ( v7 )
              SRCacheManager_Close(v7);
            return v4;
          }
          goto LABEL_32;
        }
        v28 = 180;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)v10,
        v31);
      v29 = v37;
      v37 = 0;
      if ( v29 )
        SRCacheContext_Close(v29);
    }
    else
    {
      v4 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)0x80070057LL,
        v31);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDB,
      (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
      (const char *)v4,
      v33);
    v25 = v54;
    v54 = 0;
    if ( v25 )
      SRCache_Free(v25);
    v26 = *((_QWORD *)&v51 + 1);
    *((_QWORD *)&v51 + 1) = 0;
    if ( v26 )
      SRCache_Free(v26);
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD2,
    (unsigned int)"onecore\\base\\appmodel\\identity\\lib\\packageidentity.cpp",
    (const char *)0x80070002LL,
    v31);
LABEL_36:
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v41);
  v24 = v36;
  v36 = 0;
  if ( v24 )
    SRCacheManager_Close(v24);
  return 2147942402LL;
}

```

## disassembly

```asm
0x18002c020  mov     [rsp-8+arg_10], rbx
0x18002c025  push    rbp
0x18002c026  push    rsi
0x18002c027  push    rdi
0x18002c028  push    r14
0x18002c02a  push    r15
0x18002c02c  lea     rbp, [rsp-50h]
0x18002c031  sub     rsp, 150h
0x18002c038  mov     rax, cs:__security_cookie
0x18002c03f  xor     rax, rsp
0x18002c042  mov     [rbp+70h+var_30], rax
0x18002c046  xor     r15d, r15d
0x18002c049  mov     r14, rdx
0x18002c04c  mov     rsi, rcx
0x18002c04f  test    rdx, rdx
0x18002c052  jnz     short loc_18002C096
0x18002c054  mov     rcx, [rbp+78h]; this
0x18002c058  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c05f  mov     ebx, 80070057h
0x18002c064  mov     edx, 0C5h; void *
0x18002c069  mov     r9d, ebx; char *
0x18002c06c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c071  mov     eax, ebx
0x18002c073  mov     rcx, [rbp+70h+var_30]
0x18002c077  xor     rcx, rsp; StackCookie
0x18002c07a  call    __security_check_cookie
0x18002c07f  mov     rbx, [rsp+170h+arg_10]
0x18002c087  add     rsp, 150h
0x18002c08e  pop     r15
0x18002c090  pop     r14
0x18002c092  pop     rdi
0x18002c093  pop     rsi
0x18002c094  pop     rbp
0x18002c095  retn
0x18002c096  test    rsi, rsi
0x18002c099  jz      short loc_18002C054
0x18002c09b  lea     rax, [rsp+170h+var_138]
0x18002c0a0  mov     [rsp+170h+var_138], r15
0x18002c0a5  lea     rdx, [rsp+170h+var_120]
0x18002c0aa  mov     [rsp+170h+var_128], rax
0x18002c0af  xor     ecx, ecx
0x18002c0b1  mov     [rsp+170h+var_120], r15
0x18002c0b6  mov     [rsp+170h+var_118], 1
0x18002c0bb  call    cs:__imp_SRCacheManager_Open
0x18002c0c1  mov     ebx, eax
0x18002c0c3  cmp     [rsp+170h+var_118], r15b
0x18002c0c8  jz      short loc_18002C0E5
0x18002c0ca  mov     r8, [rsp+170h+var_128]
0x18002c0cf  mov     rdx, [rsp+170h+var_120]
0x18002c0d4  mov     rcx, [r8]
0x18002c0d7  mov     [r8], rdx
0x18002c0da  test    rcx, rcx
0x18002c0dd  jz      short loc_18002C0E5
0x18002c0df  call    cs:__imp_SRCacheManager_Close
0x18002c0e5  test    ebx, ebx
0x18002c0e7  jns     short loc_18002C137
0x18002c0e9  mov     rcx, [rbp+78h]; this
0x18002c0ed  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c0f4  mov     r9d, ebx; char *
0x18002c0f7  mov     edx, 0A5h; void *
0x18002c0fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c101  mov     rcx, [rbp+78h]; this
0x18002c105  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c10c  mov     r9d, ebx; char *
0x18002c10f  mov     edx, 0C8h; void *
0x18002c114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c119  mov     rcx, [rsp+170h+var_138]
0x18002c11e  mov     [rsp+170h+var_138], r15
0x18002c123  test    rcx, rcx
0x18002c126  jz      loc_18002C071
0x18002c12c  call    cs:__imp_SRCacheManager_Close
0x18002c132  jmp     loc_18002C071
0x18002c137  xorps   xmm0, xmm0
0x18002c13a  mov     [rsp+170h+var_100], r15
0x18002c13f  xorps   xmm1, xmm1
0x18002c142  movdqa  [rsp+170h+var_110], xmm0
0x18002c148  lea     r8, [rsp+170h+var_130]; __int64 *
0x18002c14d  movdqa  [rbp+70h+var_D0], xmm0
0x18002c152  mov     rdx, rsi; unsigned __int16 *
0x18002c155  mov     [rbp+70h+var_E8], r15
0x18002c159  lea     rcx, [rsp+170h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x18002c15e  mov     [rbp+70h+var_E0], r15
0x18002c162  movups  [rsp+170h+var_F8], xmm1
0x18002c167  mov     [rbp+70h+var_D8], r15
0x18002c16b  mov     dil, r15b
0x18002c16e  mov     [rbp+70h+var_C0], r15d
0x18002c172  mov     [rbp+70h+var_B8], r15
0x18002c176  mov     [rbp+70h+var_B0], r15
0x18002c17a  mov     [rsp+170h+var_140], r15b
0x18002c17f  mov     [rsp+170h+var_130], r15
0x18002c184  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18002c189  mov     ebx, eax
0x18002c18b  test    eax, eax
0x18002c18d  js      loc_18002C3E3
0x18002c193  mov     rdx, [rsp+170h+var_130]
0x18002c198  test    rdx, rdx
0x18002c19b  jz      short loc_18002C1CB
0x18002c19d  lea     rax, [rsp+170h+var_140]
0x18002c1a2  mov     r8d, 2
0x18002c1a8  lea     r9, [rsp+170h+var_110]
0x18002c1ad  mov     qword ptr [rsp+170h+var_150], rax; int
0x18002c1b2  lea     rcx, [rsp+170h+var_138]
0x18002c1b7  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18002c1bc  mov     ebx, eax
0x18002c1be  test    eax, eax
0x18002c1c0  js      loc_18002C49B
0x18002c1c6  mov     dil, [rsp+170h+var_140]
0x18002c1cb  test    dil, dil
0x18002c1ce  jz      loc_18002C4A5
0x18002c1d4  xor     edx, edx; Val
0x18002c1d6  lea     rcx, [rbp+70h+var_90]; void *
0x18002c1da  xorps   xmm0, xmm0
0x18002c1dd  movdqa  [rbp+70h+var_A0], xmm0
0x18002c1e2  lea     r8d, [rdx+44h]; Size
0x18002c1e6  call    memset_0
0x18002c1eb  mov     rsi, [rsp+170h+var_100]
0x18002c1f0  mov     [rbp+70h+pSid], r15
0x18002c1f4  mov     [rbp+70h+var_40], r15
0x18002c1f8  mov     [rsp+170h+var_140], r15b
0x18002c1fd  test    rsi, rsi
0x18002c200  jz      loc_18002C379
0x18002c206  lea     r9, [rsp+170h+var_140]; bool *
0x18002c20b  mov     [rsp+170h+var_130], r15
0x18002c210  lea     r8, [rsp+170h+var_130]; struct StateRepository::Cache::Context_NoThrow *
0x18002c215  mov     rdx, rsi; __int64
0x18002c218  lea     rcx, [rsp+170h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x18002c21d  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002c222  mov     ebx, eax
0x18002c224  test    eax, eax
0x18002c226  js      loc_18002C415
0x18002c22c  mov     dil, [rsp+170h+var_140]
0x18002c231  test    dil, dil
0x18002c234  jz      loc_18002C47D
0x18002c23a  mov     r9, rsi
0x18002c23d  lea     rdx, [rbp+70h+var_A0]
0x18002c241  mov     r8d, 2
0x18002c247  lea     rcx, [rsp+170h+var_130]
0x18002c24c  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x18002c251  mov     ebx, eax
0x18002c253  test    eax, eax
0x18002c255  js      loc_18002C4C5
0x18002c25b  mov     rcx, [rsp+170h+var_130]
0x18002c260  mov     [rsp+170h+var_130], r15
0x18002c265  test    rcx, rcx
0x18002c268  jz      short loc_18002C270
0x18002c26a  call    cs:__imp_SRCacheContext_Close
0x18002c270  test    dil, dil
0x18002c273  jz      loc_18002C30F
0x18002c279  mov     rbx, [rbp+70h+pSid]
0x18002c27d  mov     rcx, rbx; pSid
0x18002c280  call    GetLengthSid
0x18002c285  mov     r8d, eax
0x18002c288  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x18002c28d  mov     rcx, rax; HeapHandle
0x18002c290  xor     edx, edx; Flags
0x18002c292  call    cs:__imp_RtlAllocateHeap
0x18002c298  mov     rdi, rax
0x18002c29b  test    rax, rax
0x18002c29e  jz      loc_18002C44B
0x18002c2a4  mov     rcx, rbx; pSid
0x18002c2a7  call    GetLengthSid
0x18002c2ac  mov     r8, rbx; pSourceSid
0x18002c2af  mov     rdx, rdi; pDestinationSid
0x18002c2b2  mov     ecx, eax; nDestinationSidLength
0x18002c2b4  call    CopySid
0x18002c2b9  xor     ecx, ecx; void *
0x18002c2bb  mov     [r14], rdi
0x18002c2be  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18002c2c3  mov     rcx, [rbp+70h+var_40]
0x18002c2c7  mov     [rbp+70h+var_40], r15
0x18002c2cb  test    rcx, rcx
0x18002c2ce  jz      short loc_18002C2D6
0x18002c2d0  call    cs:__imp_SRCache_Free
0x18002c2d6  mov     rcx, qword ptr [rbp+70h+var_A0+8]
0x18002c2da  mov     qword ptr [rbp+70h+var_A0+8], r15
0x18002c2de  test    rcx, rcx
0x18002c2e1  jz      short loc_18002C2E9
0x18002c2e3  call    cs:__imp_SRCache_Free
0x18002c2e9  lea     rcx, [rsp+170h+var_110]; this
0x18002c2ee  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002c2f3  mov     rcx, [rsp+170h+var_138]
0x18002c2f8  mov     [rsp+170h+var_138], r15
0x18002c2fd  test    rcx, rcx
0x18002c300  jz      short loc_18002C308
0x18002c302  call    cs:__imp_SRCacheManager_Close
0x18002c308  xor     eax, eax
0x18002c30a  jmp     loc_18002C073
0x18002c30f  mov     rcx, [rbp+78h]; this
0x18002c313  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c31a  mov     r9d, 80070002h; char *
0x18002c320  mov     edx, 0DCh; void *
0x18002c325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c32a  mov     rcx, [rbp+70h+var_40]
0x18002c32e  mov     [rbp+70h+var_40], r15
0x18002c332  test    rcx, rcx
0x18002c335  jz      short loc_18002C33D
0x18002c337  call    cs:__imp_SRCache_Free
0x18002c33d  mov     rcx, qword ptr [rbp+70h+var_A0+8]
0x18002c341  mov     qword ptr [rbp+70h+var_A0+8], r15
0x18002c345  test    rcx, rcx
0x18002c348  jz      short loc_18002C350
0x18002c34a  call    cs:__imp_SRCache_Free
0x18002c350  lea     rcx, [rsp+170h+var_110]; this
0x18002c355  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002c35a  mov     rcx, [rsp+170h+var_138]
0x18002c35f  mov     [rsp+170h+var_138], r15
0x18002c364  test    rcx, rcx
0x18002c367  jz      short loc_18002C36F
0x18002c369  call    cs:__imp_SRCacheManager_Close
0x18002c36f  mov     eax, 80070002h
0x18002c374  jmp     loc_18002C073
0x18002c379  mov     rcx, [rbp+78h]; this
0x18002c37d  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c384  mov     ebx, 80070057h
0x18002c389  mov     edx, 0ACh; void *
0x18002c38e  mov     r9d, ebx; char *
0x18002c391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c396  mov     rcx, [rbp+78h]; this
0x18002c39a  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c3a1  mov     r9d, ebx; char *
0x18002c3a4  mov     edx, 0DBh; void *
0x18002c3a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3ae  mov     rcx, [rbp+70h+var_40]
0x18002c3b2  mov     [rbp+70h+var_40], r15
0x18002c3b6  test    rcx, rcx
0x18002c3b9  jz      short loc_18002C3C1
0x18002c3bb  call    cs:__imp_SRCache_Free
0x18002c3c1  mov     rcx, qword ptr [rbp+70h+var_A0+8]
0x18002c3c5  mov     qword ptr [rbp+70h+var_A0+8], r15
0x18002c3c9  test    rcx, rcx
0x18002c3cc  jz      short loc_18002C3D4
0x18002c3ce  call    cs:__imp_SRCache_Free
0x18002c3d4  lea     rcx, [rsp+170h+var_110]; this
0x18002c3d9  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002c3de  jmp     loc_18002C119
0x18002c3e3  mov     edx, 48Dh; void *
0x18002c3e8  mov     rcx, [rbp+78h]; this
0x18002c3ec  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c3f3  mov     r9d, ebx; char *
0x18002c3f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c3fb  mov     rcx, [rbp+78h]; this
0x18002c3ff  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c406  mov     r9d, ebx; char *
0x18002c409  mov     edx, 0D1h; void *
0x18002c40e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c413  jmp     short loc_18002C3D4
0x18002c415  mov     edx, 0AFh; void *
0x18002c41a  mov     rcx, [rbp+78h]; this
0x18002c41e  lea     r8, aOnecorePrivate_6; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002c425  mov     r9d, eax; char *
0x18002c428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c42d  mov     rcx, [rsp+170h+var_130]
0x18002c432  mov     [rsp+170h+var_130], r15
0x18002c437  test    rcx, rcx
0x18002c43a  jz      loc_18002C396
0x18002c440  call    cs:__imp_SRCacheContext_Close
0x18002c446  jmp     loc_18002C396
0x18002c44b  mov     rcx, [rbp+78h]; this
0x18002c44f  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c456  mov     ebx, 8007000Eh
0x18002c45b  mov     edx, 0E0h; void *
0x18002c460  mov     r9d, ebx; char *
0x18002c463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c468  xor     ecx, ecx; void *
0x18002c46a  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18002c46f  lea     rcx, [rbp+70h+var_A0]; this
0x18002c473  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x18002c478  jmp     loc_18002C3D4
0x18002c47d  mov     rcx, [rsp+170h+var_130]
0x18002c482  mov     [rsp+170h+var_130], r15
0x18002c487  test    rcx, rcx
0x18002c48a  jz      loc_18002C30F
0x18002c490  call    cs:__imp_SRCacheContext_Close
0x18002c496  jmp     loc_18002C30F
0x18002c49b  mov     edx, 490h
0x18002c4a0  jmp     loc_18002C3E8
0x18002c4a5  mov     rcx, [rbp+78h]; this
0x18002c4a9  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\identity\\lib"...
0x18002c4b0  mov     r9d, 80070002h; char *
0x18002c4b6  mov     edx, 0D2h; void *
0x18002c4bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c4c0  jmp     loc_18002C350
0x18002c4c5  mov     edx, 0B4h
0x18002c4ca  jmp     loc_18002C41A
```
