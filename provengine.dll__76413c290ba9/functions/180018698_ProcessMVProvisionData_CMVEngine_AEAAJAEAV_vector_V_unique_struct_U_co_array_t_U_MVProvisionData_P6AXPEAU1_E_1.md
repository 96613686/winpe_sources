# ?ProcessMVProvisionData@CMVEngine@@AEAAJAEAV?$vector@V?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@@std@@@std@@PEAPEAU_MVProvisionData@@PEAK@Z

- ea: `0x180018698`
- end: `0x180018e1a`
- name: `?ProcessMVProvisionData@CMVEngine@@AEAAJAEAV?$vector@V?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@V?$allocator@V?$unique_struct@U?$co_array_t@U_MVProvisionData@@@@P6AXPEAU1@@_E$1?FreeProvisionDataArray@@YAX0@Z$$T$0A@@wil@@@std@@@std@@PEAPEAU_MVProvisionData@@PEAK@Z`
- size: `1922`
- prototype: `__int64 __fastcall(CMVEngine *this, __int64 *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015740`

## callees

- `0x1800098dc`
- `0x18000aef0`
- `0x18000b030`
- `0x18000efa4`
- `0x18000f56c`
- `0x180010ad8`
- `0x180012eb4`
- `0x1800139a0`
- `0x180013e50`
- `0x180016570`
- `0x180018698`
- `0x18001b068`
- `0x18001c7fc`
- `0x18001e83c`
- `0x18001fab8`
- `0x180021860`
- `0x180021c5c`
- `0x180021cf4`
- `0x180021d14`
- `0x180030f6c`
- `0x180033ecc`
- `0x1800346d8`
- `0x180036338`
- `0x18004371a`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018874`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800189bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018b25`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018c87`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018ce4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018874`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800189bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018a3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018b25`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018c87`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018ce4`
- `OLEAUT32!__imp_VariantInit` at `0x180018728`
- `OLEAUT32!__imp_VariantInit` at `0x180018728`
- `OLEAUT32!__imp_VariantClear` at `0x18001875e`
- `OLEAUT32!__imp_VariantClear` at `0x18001875e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800188bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800188bb`

## string_xrefs

- `0x180018de2`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180018df3`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x180018e02`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CMVEngine::ProcessMVProvisionData(CMVEngine *this, __int64 *a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v6; // rcx
  bool v7; // dl
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  __int64 v12; // r15
  __int64 v13; // rdi
  unsigned __int64 v14; // r14
  char *pcVal; // rbx
  char *v16; // r14
  __int64 v17; // r8
  unsigned __int64 v18; // rdi
  SIZE_T v19; // rax
  __int64 v20; // r9
  char *v21; // rax
  const char *v22; // r9
  char *v23; // r15
  unsigned int v24; // r13d
  char *i; // rdi
  _OWORD *v26; // rcx
  __int128 v27; // xmm1
  __int128 v28; // xmm2
  __int128 v29; // xmm3
  __int128 v30; // xmm4
  __int128 v31; // xmm5
  __int64 v32; // xmm6_8
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 j; // rax
  __int64 v36; // r13
  int v37; // eax
  char HasMatchingSettingsGroup; // al
  CMVEngine *v39; // rcx
  int ProvisionDataContents; // eax
  const struct _MVProvisionData *v41; // rdx
  _WORD *v42; // rdx
  __int64 v43; // r8
  unsigned __int64 v44; // r13
  int SettingProperties; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rcx
  __int64 v49; // rbx
  unsigned __int64 v50; // rdx
  unsigned __int64 v51; // r9
  unsigned __int64 v52; // r8
  int v53; // [rsp+20h] [rbp-118h]
  bool v54; // [rsp+30h] [rbp-108h]
  char v55; // [rsp+31h] [rbp-107h]
  bool v56; // [rsp+31h] [rbp-107h]
  bool v57; // [rsp+32h] [rbp-106h]
  bool v58; // [rsp+33h] [rbp-105h]
  unsigned int v59; // [rsp+34h] [rbp-104h]
  __int128 v60; // [rsp+38h] [rbp-100h] BYREF
  __int64 v61; // [rsp+48h] [rbp-F0h]
  int v62; // [rsp+50h] [rbp-E8h]
  __int64 v63; // [rsp+58h] [rbp-E0h] BYREF
  int v64; // [rsp+60h] [rbp-D8h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-D0h] BYREF
  struct PackageContext *ContextFromProvXmlId; // [rsp+80h] [rbp-B8h]
  IRecordInfo *pRecInfo; // [rsp+88h] [rbp-B0h]
  _QWORD *v68; // [rsp+90h] [rbp-A8h]
  _DWORD *v69; // [rsp+98h] [rbp-A0h]
  __int128 v70; // [rsp+A0h] [rbp-98h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-88h]
  __int64 v72; // [rsp+B8h] [rbp-80h]
  __int128 *v73; // [rsp+C0h] [rbp-78h]
  void *v74[3]; // [rsp+C8h] [rbp-70h] BYREF
  unsigned __int64 v75; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v69 = a4;
  v68 = a3;
  v6 = *(unsigned int *)(*((_QWORD *)this + 26) + 24LL);
  v7 = (((_DWORD)v6 - 6) & 0xFFFFFFFD) == 0;
  v54 = v7;
  v57 = (_DWORD)v6 == 11 || (_DWORD)v6 == 18;
  try
  {
    v60 = 0;
    v61 = 0;
    v58 = 0;
    if ( (((_DWORD)v6 - 6) & 0xFFFFFFFD) != 0 )
    {
      VariantInit(&pvarg);
      if ( (*(int (__fastcall **)(CMVEngine *, const unsigned __int16 *, VARIANTARG *))(*(_QWORD *)this + 56LL))(
             this,
             L"slotstatus",
             &pvarg) >= 0 )
        v58 = pvarg.lVal == 2;
      VariantClear(&pvarg);
    }
    else
    {
      if ( !*((_DWORD *)this + 28) )
        goto LABEL_13;
      v8 = CMVEngine::RetrieveSettingsGroupsToUpdateFromRegistry(v6, &v60);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37E,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
          (const char *)(unsigned int)v8,
          v53);
        std::vector<std::wstring>::_Tidy(&v60);
        return v9;
      }
    }
    v7 = v54;
LABEL_13:
    memset(&pvarg, 0, sizeof(pvarg));
    pRecInfo = 0;
    v12 = *a2;
    v13 = a2[1];
    v14 = *((_QWORD *)&v60 + 1);
    pcVal = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
LABEL_14:
    if ( v12 == v13 )
    {
      if ( *((_DWORD *)this + 29) || !v7 )
      {
        v16 = *(char **)&pvarg.vt;
      }
      else
      {
        v16 = *(char **)&pvarg.vt;
        if ( *(char **)&pvarg.vt == pcVal )
        {
LABEL_23:
          v18 = (pcVal - v16) >> 3;
          v63 = 0;
          v19 = 104 * v18;
          if ( is_mul_ok(v18, 0x68u) )
          {
            v20 = 0;
          }
          else
          {
            v19 = -1;
            v20 = 2147942934LL;
          }
          if ( (int)v20 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3B,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
              (const char *)v20,
              v53);
          v21 = (char *)CoTaskMemRealloc(0, v19);
          v23 = v21;
          if ( v18 && !v21 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x3F,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
              v22);
          if ( v18 > 0xFFFFFFFF )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x41,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
              v18 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
              v53);
          v63 = (__int64)v21;
          v64 = (pcVal - v16) >> 3;
          v24 = 0;
          for ( i = v16; i != pcVal; i += 8 )
          {
            v26 = *(_OWORD **)i;
            v27 = *(_OWORD *)(*(_QWORD *)i + 16LL);
            v28 = *(_OWORD *)(*(_QWORD *)i + 32LL);
            v29 = *(_OWORD *)(*(_QWORD *)i + 48LL);
            v30 = *(_OWORD *)(*(_QWORD *)i + 64LL);
            v31 = *(_OWORD *)(*(_QWORD *)i + 80LL);
            v32 = *(_QWORD *)(*(_QWORD *)i + 96LL);
            v33 = v24++;
            v34 = 104 * v33;
            *(_OWORD *)&v23[v34] = *(_OWORD *)*(_QWORD *)i;
            *(_OWORD *)&v23[v34 + 16] = v27;
            *(_OWORD *)&v23[v34 + 32] = v28;
            *(_OWORD *)&v23[v34 + 48] = v29;
            *(_OWORD *)&v23[v34 + 64] = v30;
            *(_OWORD *)&v23[v34 + 80] = v31;
            *(_QWORD *)&v23[v34 + 96] = v32;
            memset_0(v26, 0, 0x68u);
          }
          *v68 = v23;
          *v69 = (pcVal - v16) >> 3;
          v63 = 0;
          v64 = 0;
          FreeProvisionDataArray(&v63);
          if ( v16 )
            operator delete(v16);
          std::vector<std::wstring>::_Tidy(&v60);
          return 0;
        }
        *((_DWORD *)this + 29) = 1;
      }
      if ( v16 != pcVal )
      {
        v17 = (pcVal - v16) >> 3;
        v70 = 0;
        v71 = 0;
        v72 = (v17 + 1) / 2;
        v73 = &v70;
        ____Stable_sort_PEAPEAU_MVProvisionData___JPEAU1_P6AHPEAU1_0__E_std__YAXPEAPEAU_MVProvisionData__0_JAEAV___Temp_iterator_PEAU_MVProvisionData___0_P6AHPEAU1_3__E_Z(
          v16,
          pcVal,
          v17,
          &v70);
        if ( (_QWORD)v70 )
          operator delete((void *)v70);
      }
      goto LABEL_23;
    }
    for ( j = 0; ; j = (unsigned int)(v62 + 1) )
    {
      v62 = j;
      if ( (unsigned int)j >= *(_DWORD *)(v12 + 8) )
      {
        v12 += 16;
        v7 = v54;
        goto LABEL_14;
      }
      v36 = 104 * j;
      v63 = 104 * j;
      if ( *(_DWORD *)(104 * j + *(_QWORD *)v12 + 4) != 1 )
      {
        v37 = ProfileFilter::Filter((char *)this + 248);
        if ( v37 )
        {
          if ( v37 != 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x397,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              (const char *)0x8000FFFFLL,
              v53);
            if ( *(_QWORD *)&pvarg.vt )
              operator delete(*(void **)&pvarg.vt);
            std::vector<std::wstring>::_Tidy(&v60);
            return 2147549183LL;
          }
        }
        else
        {
          if ( !v57 )
          {
            if ( v54 )
            {
              if ( *((_DWORD *)this + 28) )
              {
                HasMatchingSettingsGroup = CMVEngine::HasMatchingSettingsGroup(v36 + *(_QWORD *)v12, &v60);
                v14 = *((_QWORD *)&v60 + 1);
                if ( !HasMatchingSettingsGroup )
                  continue;
              }
            }
            else
            {
              ContextFromProvXmlId = ProvStateContext::GetContextFromProvXmlId(
                                       *((ProvStateContext **)this + 26),
                                       *(const unsigned __int16 **)(*(_QWORD *)v12 + v36 + 48));
              if ( (_QWORD)v60 == v14
                || (v55 = CMVEngine::HasMatchingSettingsGroup(v36 + *(_QWORD *)v12, &v60),
                    v14 = *((_QWORD *)&v60 + 1),
                    !v55) )
              {
                ProvisionDataContents = CMVEngine::GetProvisionDataContents(
                                          v39,
                                          *(const struct ProvSource **)ContextFromProvXmlId,
                                          (struct _MVProvisionData *)(v36 + *(_QWORD *)v12));
                v59 = ProvisionDataContents;
                if ( ProvisionDataContents < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3C0,
                    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                    (const char *)(unsigned int)ProvisionDataContents,
                    v53);
                  if ( *(_QWORD *)&pvarg.vt )
                    operator delete(*(void **)&pvarg.vt);
                  goto LABEL_55;
                }
                v56 = HasProvisionDataChanged(
                        ContextFromProvXmlId,
                        (struct _MVProvisionData *)(v36 + *(_QWORD *)v12),
                        *(const unsigned __int16 **)(v36 + *(_QWORD *)v12 + 16));
                v41 = (const struct _MVProvisionData *)(v36 + *(_QWORD *)v12);
                if ( v56 )
                {
                  CMVEngine::RemoveResultsForProvisionData(this, v41);
                }
                else if ( !CMVEngine::ShouldRetryProvisionData(this, v41) )
                {
                  continue;
                }
              }
              CMVEngine::CacheProvisioningResults(this, (const struct _MVProvisionData *)(v36 + *(_QWORD *)v12));
              v42 = *(_WORD **)(*(_QWORD *)v12 + v36 + 40);
              if ( v42 )
              {
                v75 = 7;
                v74[2] = 0;
                LOWORD(v74[0]) = 0;
                if ( *v42 )
                {
                  v43 = -1;
                  do
                    ++v43;
                  while ( v42[v43] );
                }
                std::wstring::assign(v74, v42);
                if ( (unsigned __int64)v74 >= v14 || (unsigned __int64)v60 > (unsigned __int64)v74 )
                {
                  if ( v14 == v61 )
                  {
                    std::vector<std::wstring>::_Reserve(&v60);
                    v14 = *((_QWORD *)&v60 + 1);
                  }
                  std::wstring::wstring(v14, v74);
                }
                else
                {
                  v44 = (unsigned __int64)v74 - v60;
                  if ( v14 == v61 )
                  {
                    std::vector<std::wstring>::_Reserve(&v60);
                    v14 = *((_QWORD *)&v60 + 1);
                  }
                  std::wstring::wstring(v14, v60 + (v44 & 0xFFFFFFFFFFFFFFE0uLL));
                  v36 = v63;
                }
                v14 += 32LL;
                *((_QWORD *)&v60 + 1) = v14;
                if ( v75 >= 8 )
                  operator delete(v74[0]);
                if ( v58 )
                  DeleteCrcsForSettingsGroup(ContextFromProvXmlId, (struct _MVProvisionData *)(v36 + *(_QWORD *)v12));
              }
            }
          }
          SettingProperties = CMVEngine::QuerySettingProperties(this, (struct _MVProvisionData *)(v36 + *(_QWORD *)v12));
          v59 = SettingProperties;
          if ( SettingProperties < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E8,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              (const char *)(unsigned int)SettingProperties,
              v53);
            if ( *(_QWORD *)&pvarg.vt )
              operator delete(*(void **)&pvarg.vt);
LABEL_55:
            std::vector<std::wstring>::_Tidy(&v60);
            return v59;
          }
          v48 = *(_QWORD *)v12;
          v63 = *(_QWORD *)v12;
          if ( pcVal == (char *)pRecInfo && !(((char *)pRecInfo - pcVal) >> 3) )
          {
            v49 = (__int64)&pcVal[-*(_QWORD *)&pvarg.vt] >> 3;
            if ( v49 == 0x1FFFFFFFFFFFFFFFLL )
              std::vector<ProvSource *>::_Xlen(0x1FFFFFFFFFFFFFFFLL, v46, v47);
            v50 = v49 + 1;
            v51 = ((__int64)pRecInfo - *(_QWORD *)&pvarg.vt) >> 3;
            v52 = 0;
            if ( 0x1FFFFFFFFFFFFFFFLL - (v51 >> 1) >= v51 )
              v52 = v51 + (v51 >> 1);
            if ( v52 >= v50 )
              v50 = v52;
            std::vector<_MVProvisionData *>::_Reallocate(&pvarg, v50);
            pRecInfo = pvarg.pRecInfo;
            pcVal = pvarg.pcVal;
            v48 = v63;
          }
          *(_QWORD *)pcVal = v48 + v36;
          pcVal += 8;
          pvarg.llVal = (LONGLONG)pcVal;
        }
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x406,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180018698  mov     rax, rsp
0x18001869b  push    rbx
0x18001869c  push    rsi
0x18001869d  push    rdi
0x18001869e  push    r12
0x1800186a0  push    r13
0x1800186a2  push    r14
0x1800186a4  push    r15
0x1800186a6  sub     rsp, 100h
0x1800186ad  movaps  xmmword ptr [rax-48h], xmm6
0x1800186b1  mov     rax, cs:__security_cookie
0x1800186b8  xor     rax, rsp
0x1800186bb  mov     [rsp+138h+var_50], rax
0x1800186c3  mov     [rsp+138h+var_A0], r9
0x1800186cb  mov     [rsp+138h+var_A8], r8
0x1800186d3  mov     rdi, rdx
0x1800186d6  mov     r12, rcx
0x1800186d9  mov     rax, [rcx+0D0h]
0x1800186e0  mov     ecx, [rax+18h]
0x1800186e3  lea     eax, [rcx-6]
0x1800186e6  test    eax, 0FFFFFFFDh
0x1800186eb  setz    dl
0x1800186ee  mov     [rsp+138h+var_108], dl
0x1800186f2  cmp     ecx, 0Bh
0x1800186f5  jz      short loc_180018705
0x1800186f7  cmp     ecx, 12h
0x1800186fa  jz      short loc_180018705
0x1800186fc  xor     esi, esi
0x1800186fe  mov     [rsp+138h+var_106], sil
0x180018703  jmp     short loc_18001870C
0x180018705  mov     [rsp+138h+var_106], 1
0x18001870a  xor     esi, esi
0x18001870c  xorps   xmm0, xmm0
0x18001870f  movdqu  [rsp+138h+var_100], xmm0
0x180018715  mov     [rsp+138h+var_F0], rsi
0x18001871a  mov     [rsp+138h+var_105], sil
0x18001871f  test    dl, dl
0x180018721  jnz     short loc_180018766
0x180018723  lea     rcx, [rsp+138h+pvarg]; pvarg
0x180018728  call    cs:__imp_VariantInit
0x18001872e  nop
0x18001872f  mov     rax, [r12]
0x180018733  lea     r8, [rsp+138h+pvarg]
0x180018738  lea     rdx, ?gc_wszSlotStatusContext@@3QBGB; "slotstatus"
0x18001873f  mov     rcx, r12
0x180018742  mov     rax, [rax+38h]
0x180018746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001874b  test    eax, eax
0x18001874d  js      short loc_180018759
0x18001874f  cmp     dword ptr [rsp+138h+pvarg+8], 2
0x180018754  setz    [rsp+138h+var_105]
0x180018759  lea     rcx, [rsp+138h+pvarg]; pvarg
0x18001875e  call    cs:__imp_VariantClear
0x180018764  jmp     short loc_1800187AB
0x180018766  cmp     [r12+70h], esi
0x18001876b  jz      short loc_1800187AF
0x18001876d  lea     rdx, [rsp+138h+var_100]
0x180018772  call    ?RetrieveSettingsGroupsToUpdateFromRegistry@CMVEngine@@CAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CMVEngine::RetrieveSettingsGroupsToUpdateFromRegistry(__MIDL___MIDL_itf_mvengine_0000_0000_0001,std::vector<std::wstring> &)
0x180018777  mov     ebx, eax
0x180018779  test    eax, eax
0x18001877b  jns     short loc_1800187AB
0x18001877d  mov     rcx, [rsp+138h]; this
0x180018785  mov     r9d, eax; char *
0x180018788  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001878f  mov     edx, 37Eh; void *
0x180018794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018799  nop
0x18001879a  lea     rcx, [rsp+138h+var_100]
0x18001879f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800187a4  mov     eax, ebx
0x1800187a6  jmp     loc_180018DAA
0x1800187ab  mov     dl, [rsp+138h+var_108]
0x1800187af  xorps   xmm0, xmm0
0x1800187b2  movdqu  xmmword ptr [rsp+138h+pvarg], xmm0
0x1800187b8  mov     rax, rsi
0x1800187bb  mov     [rsp+138h+var_B0], rax
0x1800187c3  mov     qword ptr [rsp+138h+pvarg+10h], rax
0x1800187c8  mov     r15, [rdi]
0x1800187cb  mov     rdi, [rdi+8]
0x1800187cf  mov     r14, qword ptr [rsp+138h+var_100+8]
0x1800187d4  psrldq  xmm0, 8
0x1800187d9  movq    rbx, xmm0
0x1800187de  cmp     r15, rdi
0x1800187e1  jnz     loc_1800189D3
0x1800187e7  cmp     [r12+74h], esi
0x1800187ec  jnz     short loc_180018807
0x1800187ee  test    dl, dl
0x1800187f0  jz      short loc_180018807
0x1800187f2  mov     r14, qword ptr [rsp+138h+pvarg]
0x1800187f7  cmp     r14, rbx
0x1800187fa  jz      short loc_18001887A
0x1800187fc  mov     dword ptr [r12+74h], 1
0x180018805  jmp     short loc_18001880C
0x180018807  mov     r14, qword ptr [rsp+138h+pvarg]
0x18001880c  cmp     r14, rbx
0x18001880f  jz      short loc_18001887A
0x180018811  mov     r8, rbx
0x180018814  sub     r8, r14
0x180018817  sar     r8, 3
0x18001881b  xorps   xmm0, xmm0
0x18001881e  movdqu  [rsp+138h+var_98], xmm0
0x180018827  mov     [rsp+138h+var_88], rsi
0x18001882f  lea     rax, [r8+1]
0x180018833  cqo
0x180018835  sub     rax, rdx
0x180018838  sar     rax, 1
0x18001883b  mov     [rsp+138h+var_80], rax
0x180018843  lea     rax, [rsp+138h+var_98]
0x18001884b  mov     [rsp+138h+var_78], rax
0x180018853  lea     r9, [rsp+138h+var_98]
0x18001885b  mov     rdx, rbx
0x18001885e  mov     rcx, r14
0x180018861  call    ??$_Stable_sort@PEAPEAU_MVProvisionData@@_JPEAU1@P6AHPEAU1@0@_E@std@@YAXPEAPEAU_MVProvisionData@@0_JAEAV?$_Temp_iterator@PEAU_MVProvisionData@@@0@P6AHPEAU1@3@_E@Z
0x180018866  nop
0x180018867  mov     rcx, qword ptr [rsp+138h+var_98]
0x18001886f  test    rcx, rcx
0x180018872  jz      short loc_18001887A
0x180018874  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001887a  mov     rdi, rbx
0x18001887d  sub     rdi, r14
0x180018880  sar     rdi, 3
0x180018884  mov     [rsp+138h+var_E0], rsi
0x180018889  mov     eax, 68h ; 'h'
0x18001888e  mul     rdi
0x180018891  test    rdx, rdx
0x180018894  jnz     short loc_18001889B
0x180018896  mov     r9d, esi
0x180018899  jmp     short loc_1800188A5
0x18001889b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001889f  mov     r9d, 80070216h; char *
0x1800188a5  mov     rcx, [rsp+138h]; this
0x1800188ad  test    r9d, r9d
0x1800188b0  js      loc_180018DE2
0x1800188b6  mov     rdx, rax; cb
0x1800188b9  xor     ecx, ecx; pv
0x1800188bb  call    cs:__imp_CoTaskMemRealloc
0x1800188c1  mov     r15, rax
0x1800188c4  test    rdi, rdi
0x1800188c7  jz      short loc_1800188DA
0x1800188c9  mov     rcx, [rsp+138h]; this
0x1800188d1  test    rax, rax
0x1800188d4  jz      loc_180018DF3
0x1800188da  mov     eax, 0FFFFFFFFh
0x1800188df  cmp     rdi, rax
0x1800188e2  mov     r12d, edi
0x1800188e5  jbe     short loc_1800188EA
0x1800188e7  mov     r12d, eax
0x1800188ea  cmp     rax, rdi
0x1800188ed  sbb     r9d, r9d
0x1800188f0  and     r9d, 80070216h; char *
0x1800188f7  mov     rcx, [rsp+138h]; this
0x1800188ff  cmp     rdi, rax
0x180018902  ja      loc_180018E02
0x180018908  mov     [rsp+138h+var_E0], r15
0x18001890d  mov     [rsp+138h+var_D8], r12d
0x180018912  mov     eax, [rsp+138h+var_D4]
0x180018916  mov     [rsp+138h+var_D4], eax
0x18001891a  mov     r13d, esi
0x18001891d  mov     rdi, r14
0x180018920  cmp     rdi, rbx
0x180018923  jz      short loc_180018989
0x180018925  mov     rcx, [rdi]; void *
0x180018928  movups  xmm0, xmmword ptr [rcx]
0x18001892b  movups  xmm1, xmmword ptr [rcx+10h]
0x18001892f  movups  xmm2, xmmword ptr [rcx+20h]
0x180018933  movups  xmm3, xmmword ptr [rcx+30h]
0x180018937  movups  xmm4, xmmword ptr [rcx+40h]
0x18001893b  movups  xmm5, xmmword ptr [rcx+50h]
0x18001893f  movsd   xmm6, qword ptr [rcx+60h]
0x180018944  mov     eax, r13d
0x180018947  inc     r13d
0x18001894a  imul    rdx, rax, 68h ; 'h'
0x18001894e  movups  xmmword ptr [rdx+r15], xmm0
0x180018953  movups  xmmword ptr [rdx+r15+10h], xmm1
0x180018959  movups  xmmword ptr [rdx+r15+20h], xmm2
0x18001895f  movups  xmmword ptr [rdx+r15+30h], xmm3
0x180018965  movups  xmmword ptr [rdx+r15+40h], xmm4
0x18001896b  movups  xmmword ptr [rdx+r15+50h], xmm5
0x180018971  movsd   qword ptr [rdx+r15+60h], xmm6
0x180018978  xor     edx, edx; Val
0x18001897a  lea     r8d, [rdx+68h]; Size
0x18001897e  call    memset_0
0x180018983  add     rdi, 8
0x180018987  jmp     short loc_180018920
0x180018989  mov     rax, [rsp+138h+var_A8]
0x180018991  mov     [rax], r15
0x180018994  mov     rax, [rsp+138h+var_A0]
0x18001899c  mov     [rax], r12d
0x18001899f  mov     [rsp+138h+var_E0], rsi
0x1800189a4  mov     [rsp+138h+var_D8], esi
0x1800189a8  lea     rcx, [rsp+138h+var_E0]
0x1800189ad  call    ?FreeProvisionDataArray@@YAXPEAU?$co_array_t@U_MVProvisionData@@@@@Z; FreeProvisionDataArray(co_array_t<_MVProvisionData> *)
0x1800189b2  nop
0x1800189b3  test    r14, r14
0x1800189b6  jz      short loc_1800189C2
0x1800189b8  mov     rcx, r14
0x1800189bb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800189c1  nop
0x1800189c2  lea     rcx, [rsp+138h+var_100]
0x1800189c7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800189cc  xor     eax, eax
0x1800189ce  jmp     loc_180018DAA
0x1800189d3  mov     eax, esi
0x1800189d5  mov     [rsp+138h+var_E8], eax
0x1800189d9  cmp     eax, [r15+8]
0x1800189dd  jnb     loc_180018DD5
0x1800189e3  imul    r13, rax, 68h ; 'h'
0x1800189e7  mov     [rsp+138h+var_E0], r13
0x1800189ec  mov     rdx, [r15]
0x1800189ef  add     rdx, r13
0x1800189f2  cmp     dword ptr [rdx+4], 1
0x1800189f6  jz      loc_180018A90
0x1800189fc  lea     rcx, [r12+0F8h]
0x180018a04  call    ?Filter@ProfileFilter@@QEAA?AW4FilterResult@@AEAU_MVProvisionData@@@Z; ProfileFilter::Filter(_MVProvisionData &)
0x180018a09  test    eax, eax
0x180018a0b  jz      short loc_180018A56
0x180018a0d  cmp     eax, 1
0x180018a10  jz      short loc_180018A90
0x180018a12  mov     rcx, [rsp+138h]; this
0x180018a1a  mov     ebx, 8000FFFFh
0x180018a1f  mov     r9d, ebx; char *
0x180018a22  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180018a29  mov     edx, 397h; void *
0x180018a2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a33  nop
0x180018a34  mov     rcx, qword ptr [rsp+138h+pvarg]
0x180018a39  test    rcx, rcx
0x180018a3c  jz      short loc_180018A45
0x180018a3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018a44  nop
0x180018a45  lea     rcx, [rsp+138h+var_100]
0x180018a4a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180018a4f  mov     eax, ebx
0x180018a51  jmp     loc_180018DAA
0x180018a56  cmp     [rsp+138h+var_106], sil
0x180018a5b  jnz     loc_180018CA7
0x180018a61  cmp     [rsp+138h+var_108], sil
0x180018a66  jz      short loc_180018A9B
0x180018a68  cmp     [r12+70h], esi
0x180018a6d  jz      loc_180018CA7
0x180018a73  mov     rcx, [r15]
0x180018a76  add     rcx, r13
0x180018a79  lea     rdx, [rsp+138h+var_100]
0x180018a7e  call    ?HasMatchingSettingsGroup@CMVEngine@@CA_NAEBU_MVProvisionData@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CMVEngine::HasMatchingSettingsGroup(_MVProvisionData const &,std::vector<std::wstring> const &)
0x180018a83  mov     r14, qword ptr [rsp+138h+var_100+8]
0x180018a88  test    al, al
0x180018a8a  jnz     loc_180018CA7
0x180018a90  mov     eax, [rsp+138h+var_E8]
0x180018a94  inc     eax
0x180018a96  jmp     loc_1800189D5
0x180018a9b  mov     rdx, [r15]
0x180018a9e  mov     rdx, [rdx+r13+30h]; unsigned __int16 *
0x180018aa3  mov     rcx, [r12+0D0h]; this
0x180018aab  call    ?GetContextFromProvXmlId@ProvStateContext@@QEAAAEAUPackageContext@@PEBG@Z; ProvStateContext::GetContextFromProvXmlId(ushort const *)
0x180018ab0  mov     [rsp+138h+var_B8], rax
0x180018ab8  cmp     qword ptr [rsp+138h+var_100], r14
0x180018abd  jz      short loc_180018AE0
0x180018abf  mov     rcx, [r15]
0x180018ac2  add     rcx, r13
0x180018ac5  lea     rdx, [rsp+138h+var_100]
0x180018aca  call    ?HasMatchingSettingsGroup@CMVEngine@@CA_NAEBU_MVProvisionData@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CMVEngine::HasMatchingSettingsGroup(_MVProvisionData const &,std::vector<std::wstring> const &)
0x180018acf  mov     [rsp+138h+var_107], al
0x180018ad3  mov     r14, qword ptr [rsp+138h+var_100+8]
0x180018ad8  test    al, al
0x180018ada  jnz     loc_180018B7F
0x180018ae0  mov     r8, [r15]
0x180018ae3  add     r8, r13; struct _MVProvisionData *
0x180018ae6  mov     rdx, [rsp+138h+var_B8]
0x180018aee  mov     rdx, [rdx]; struct ProvSource *
0x180018af1  call    ?GetProvisionDataContents@CMVEngine@@AEAAJPEBVProvSource@@AEAU_MVProvisionData@@@Z; CMVEngine::GetProvisionDataContents(ProvSource const *,_MVProvisionData &)
0x180018af6  mov     [rsp+138h+var_104], eax
0x180018afa  test    eax, eax
0x180018afc  jns     short loc_180018B3F
0x180018afe  mov     rcx, [rsp+138h]; this
0x180018b06  mov     r9d, eax; char *
0x180018b09  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180018b10  mov     edx, 3C0h; void *
0x180018b15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b1a  nop
0x180018b1b  mov     rcx, qword ptr [rsp+138h+pvarg]
0x180018b20  test    rcx, rcx
0x180018b23  jz      short loc_180018B2C
0x180018b25  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018b2b  nop
0x180018b2c  lea     rcx, [rsp+138h+var_100]
0x180018b31  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180018b36  mov     eax, [rsp+138h+var_104]
0x180018b3a  jmp     loc_180018DAA
0x180018b3f  mov     rdx, [r15]
0x180018b42  add     rdx, r13; struct _MVProvisionData *
0x180018b45  mov     r8, [rdx+10h]; unsigned __int16 *
0x180018b49  mov     rcx, [rsp+138h+var_B8]; struct PackageContext *
0x180018b51  call    ?HasProvisionDataChanged@@YA_NPEAUPackageContext@@PEAU_MVProvisionData@@PEBG@Z; HasProvisionDataChanged(PackageContext *,_MVProvisionData *,ushort const *)
0x180018b56  mov     [rsp+138h+var_107], al
0x180018b5a  mov     rdx, [r15]
0x180018b5d  mov     rcx, r12; this
0x180018b60  add     rdx, r13; struct _MVProvisionData *
0x180018b63  test    al, al
0x180018b65  jz      short loc_180018B6E
0x180018b67  call    ?RemoveResultsForProvisionData@CMVEngine@@AEAAXAEBU_MVProvisionData@@@Z; CMVEngine::RemoveResultsForProvisionData(_MVProvisionData const &)
  ... truncated ...
```
