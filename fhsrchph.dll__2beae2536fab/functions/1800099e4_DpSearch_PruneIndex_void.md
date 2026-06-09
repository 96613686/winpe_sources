# DpSearch::PruneIndex(void)

- ea: `0x1800099e4`
- end: `0x18000a32a`
- name: `?PruneIndex@DpSearch@@QEAAXXZ`
- size: `2374`
- prototype: `void __fastcall(DpSearch *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180001d04`
- `0x1800020d8`
- `0x18000278c`
- `0x1800067b4`
- `0x180007b0c`
- `0x180008b10`
- `0x180008db4`
- `0x1800094a8`
- `0x180009604`
- `0x180009790`
- `0x18000985c`
- `0x1800098f8`
- `0x1800099e4`
- `0x18000a420`
- `0x18000a4bc`
- `0x18000a52c`
- `0x18000a62c`
- `0x18000a960`
- `0x18000a9cc`
- `0x18000aa14`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009f1e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a135`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009f1e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a135`
- `fhsvcctl!FhQueryConfiguredUsersCount` at `0x180009a25`
- `fhsvcctl!FhQueryConfiguredUsersCount` at `0x180009a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a11b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a10c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a11b`

## pseudocode

```c
void __fastcall DpSearch::PruneIndex(DpSearch *this)
{
  int v2; // eax
  int v3; // eax
  void **v4; // rdx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  bool v10; // r8
  void *v11; // rbx
  int v12; // eax
  struct tagDBPROPSET *v13; // r8
  unsigned int v14; // r9d
  int v15; // eax
  void *v16; // rdi
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // r15d
  int v21; // eax
  __int64 v22; // r8
  _QWORD *v23; // rcx
  __int64 v24; // r8
  unsigned int v25; // r12d
  int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // r15d
  unsigned int v29; // edx
  __int64 v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rdx
  _WORD *v33; // rdx
  __int64 v34; // r8
  signed __int64 v35; // rdx
  __int64 v36; // r8
  __int64 i; // rdx
  int v38; // edx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // [rsp+0h] [rbp-1F8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned int v46; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-1A8h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-1A0h]
  LPVOID pv; // [rsp+60h] [rbp-198h] BYREF
  __int64 v50; // [rsp+68h] [rbp-190h] BYREF
  _BYTE pExceptionObject[4]; // [rsp+70h] [rbp-188h] BYREF
  _BYTE v52[4]; // [rsp+74h] [rbp-184h] BYREF
  _BYTE v53[4]; // [rsp+78h] [rbp-180h] BYREF
  _BYTE v54[4]; // [rsp+7Ch] [rbp-17Ch] BYREF
  _BYTE v55[4]; // [rsp+80h] [rbp-178h] BYREF
  _BYTE v56[4]; // [rsp+84h] [rbp-174h] BYREF
  _BYTE v57[4]; // [rsp+88h] [rbp-170h] BYREF
  _BYTE v58[4]; // [rsp+8Ch] [rbp-16Ch] BYREF
  _BYTE v59[4]; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v60[4]; // [rsp+94h] [rbp-164h] BYREF
  _BYTE v61[4]; // [rsp+98h] [rbp-160h] BYREF
  _BYTE v62[4]; // [rsp+9Ch] [rbp-15Ch] BYREF
  LPVOID v63[2]; // [rsp+A0h] [rbp-158h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-148h] BYREF
  int v65; // [rsp+B8h] [rbp-140h]
  __int64 v66; // [rsp+C0h] [rbp-138h]
  unsigned __int64 v67; // [rsp+C8h] [rbp-130h]
  __int64 v68; // [rsp+D0h] [rbp-128h]
  __int64 v69; // [rsp+D8h] [rbp-120h]
  __int64 v70; // [rsp+E0h] [rbp-118h]
  char v71; // [rsp+E8h] [rbp-110h]
  int v72; // [rsp+ECh] [rbp-10Ch]
  __int64 v73; // [rsp+F0h] [rbp-108h]
  struct IRowset *v74[2]; // [rsp+F8h] [rbp-100h] BYREF
  ATL::CDynamicAccessor *v75; // [rsp+108h] [rbp-F0h]
  _QWORD v76[2]; // [rsp+110h] [rbp-E8h] BYREF
  __int128 v77; // [rsp+120h] [rbp-D8h] BYREF
  DpSearch *v78; // [rsp+130h] [rbp-C8h]
  LPVOID v79; // [rsp+138h] [rbp-C0h]
  DpSearch *v80; // [rsp+140h] [rbp-B8h]
  ATL::CAtlException *v81; // [rsp+150h] [rbp-A8h] BYREF
  ATL::CAtlException *v82; // [rsp+158h] [rbp-A0h] BYREF
  void *Src[2]; // [rsp+160h] [rbp-98h] BYREF
  __int64 v84; // [rsp+170h] [rbp-88h]
  unsigned __int64 v85; // [rsp+178h] [rbp-80h]
  void *v86[3]; // [rsp+188h] [rbp-70h] BYREF
  unsigned __int64 v87; // [rsp+1A0h] [rbp-58h]

  v78 = this;
  v80 = this;
  v46 = 0;
  v2 = FhQueryConfiguredUsersCount(&v46);
  if ( v2 < 0 )
  {
    ATL::CAtlException::CAtlException((ATL::CAtlException *)pExceptionObject, v2);
    throw (ATL::CAtlException *)pExceptionObject;
  }
  if ( v46 )
  {
    v45 = 0;
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 1) + 200LL))(*((_QWORD *)this + 1), &v45);
    if ( v3 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v52, v3);
      throw (ATL::CAtlException *)v52;
    }
    v85 = 7;
    v84 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src, L"AND SCOPE='DP://");
    std::wstring::append(Src, (char *)this + 32, 0, -1);
    std::wstring::append(Src, L"/'");
    v4 = Src;
    if ( v85 >= 8 )
      v4 = (void **)Src[0];
    v5 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v45 + 128LL))(v45, v4);
    if ( v5 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v53, v5);
      throw (ATL::CAtlException *)v53;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v45 + 144LL))(v45, L"System.ItemDate ASC");
    if ( v6 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v54, v6);
      throw (ATL::CAtlException *)v54;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v45 + 96LL))(v45, 0);
    if ( v7 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v55, v7);
      throw (ATL::CAtlException *)v55;
    }
    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 80LL))(v45, 1);
    if ( v8 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v56, v8);
      throw (ATL::CAtlException *)v56;
    }
    _GenerateSQLFromUserQuery(v63, &v45);
    pv = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v45 + 24LL))(v45, &pv);
    if ( v9 < 0 )
      ATL::AtlThrowImpl(v9);
    v11 = pv;
    v79 = pv;
    v50 = 0;
    v12 = ATL::CDataSource::OpenFromInitializationString((ATL::CDataSource *)&v50, (const unsigned __int16 *)pv, v10);
    if ( v12 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v57, v12);
      throw (ATL::CAtlException *)v57;
    }
    v47 = 0;
    v15 = ATL::CSession::Open((ATL::CSession *)&v47, (const struct ATL::CDataSource *)&v50, v13, v14);
    if ( v15 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v58, v15);
      throw (ATL::CAtlException *)v58;
    }
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v69 = 0;
    v70 = 0;
    v72 = 0;
    v73 = 8000;
    v68 = 0;
    v74[0] = 0;
    v74[1] = 0;
    v76[1] = 0;
    v76[0] = 0;
    v75 = (ATL::CDynamicAccessor *)&v64;
    v77 = 0;
    v16 = v63[0];
    v17 = ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::Open((ATL::CDynamicAccessor *)&v64);
    if ( v17 < 0 )
    {
      ATL::CAtlException::CAtlException((ATL::CAtlException *)v59, v17);
      throw (ATL::CAtlException *)v59;
    }
    ATL::CDynamicAccessor::FreeRecordMemory(v75, v74[0]);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( v76[0] )
      {
        ((void (__fastcall *)(struct IRowset *, __int64, _QWORD *, _QWORD, _QWORD, _QWORD))v74[0]->lpVtbl->ReleaseRows)(
          v74[0],
          1,
          v76,
          0,
          0,
          0);
        v76[0] = 0;
      }
      v18 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD))v74[0]->lpVtbl->RestartPosition)(v74[0], 0);
      v19 = (unsigned int)v18;
      if ( v18 >= 0 )
        v19 = (unsigned int)ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(v74, (unsigned int)v18);
      if ( (int)v19 < 0 )
      {
        ATL::CAtlException::CAtlException((ATL::CAtlException *)v60, v19);
        throw (ATL::CAtlException *)v60;
      }
      if ( (_DWORD)v19 != 265926 )
      {
        v20 = 0;
        do
        {
          ++v20;
          v21 = ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(v74, v19);
        }
        while ( v21 >= 0 && v21 != 265926 );
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v22, v20);
          v23 = WPP_GLOBAL_Control;
        }
        v24 = 0x4E20 / v46;
        if ( v20 > 0x4E20 / v46 )
        {
          v25 = (unsigned int)v24 / 5;
          LODWORD(pv) = (unsigned int)v24 / 5;
          if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
            WPP_SF_dd(v23[2], 0x4E20 % v46, v24, v25, v20);
          ATL::CDynamicAccessor::FreeRecordMemory(v75, v74[0]);
          if ( v76[0] )
          {
            ((void (__fastcall *)(struct IRowset *, __int64, _QWORD *, _QWORD, _QWORD, _QWORD))v74[0]->lpVtbl->ReleaseRows)(
              v74[0],
              1,
              v76,
              0,
              0,
              0);
            v76[0] = 0;
          }
          v26 = ((__int64 (__fastcall *)(struct IRowset *, _QWORD))v74[0]->lpVtbl->RestartPosition)(v74[0], 0);
          if ( v26 >= 0 )
            v26 = ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(v74, v27);
          if ( v26 < 0 )
          {
            ATL::CAtlException::CAtlException((ATL::CAtlException *)v61, v26);
            throw (ATL::CAtlException *)v61;
          }
          v28 = 0;
          v48 = 0;
          do
          {
            if ( v25 <= v28 )
              goto LABEL_121;
            if ( v71 )
            {
              v29 = 0;
              if ( v67 )
              {
                v30 = v69;
                do
                {
                  v31 = v29;
                  if ( *(_QWORD *)(v69 + 80LL * v29 + 16) == 1 )
                    goto LABEL_47;
                }
                while ( ++v29 < v67 );
              }
            }
            else
            {
              v30 = v69;
              v32 = *(_QWORD *)(v69 + 16);
              if ( v32 + v67 - 1 )
              {
                v31 = 1 - v32;
LABEL_47:
                v33 = (_WORD *)(*(_QWORD *)(80 * v31 + v30 + 8) + v66);
                goto LABEL_48;
              }
            }
            v33 = 0;
LABEL_48:
            v87 = 7;
            v86[2] = 0;
            LOWORD(v86[0]) = 0;
            v34 = -1;
            do
              ++v34;
            while ( v33[v34] );
            if ( __eh34_try(0, 1) )
            {
              __eh34_scope_strut(1);
              std::wstring::assign(v86, v33);
              DpSearch::NotifyDelete((__int64)v78, v86);
              if ( v87 >= 8 )
                operator delete(v86[0]);
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                if ( v71 )
                {
                  for ( i = 0; (unsigned int)i < v67; i = (unsigned int)(i + 1) )
                  {
                    if ( *(_QWORD *)(v69 + 80LL * (unsigned int)i + 16) == 1 )
                      break;
                  }
                }
                else
                {
                  i = *(_QWORD *)(v69 + 16);
                }
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), i);
              }
            }
            if ( __eh34_catch(1) )
            {
              if ( __eh34_catch_type(1, &ATL::CAtlException `RTTI Type Descriptor', &v81) )
              {
                v35 = (signed __int64)&v44;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                {
                  goto LABEL_114;
                }
                if ( v71 )
                {
                  v35 = 0;
                  if ( v67 )
                  {
                    v36 = v69;
                    while ( *(_QWORD *)(v69 + 80 * v35 + 16) != 1 )
                    {
                      v35 = (unsigned int)(v35 + 1);
                      if ( (unsigned int)v35 >= v67 )
                        goto LABEL_110;
                    }
                    v42 = (unsigned int)v35;
LABEL_112:
                    v35 = *(_QWORD *)(v36 + 80 * v42 + 8);
                    v43 = v35 + v66;
LABEL_113:
                    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, v36, *(_DWORD *)v81, v43);
LABEL_114:
                    v16 = v63[0];
                    v11 = v79;
                    v25 = (unsigned int)pv;
                    v28 = v48;
                    v78 = v80;
                    __eh34_try_continuation(1, &ATL::CAtlException `RTTI Type Descriptor', &loc_180009FD0);
                    goto LABEL_63;
                  }
                }
                else
                {
                  v36 = v69;
                  if ( v67 - 1 + *(_QWORD *)(v69 + 16) )
                  {
                    v42 = 1LL - *(_QWORD *)(v69 + 16);
                    goto LABEL_112;
                  }
                }
LABEL_110:
                v43 = 0;
                goto LABEL_113;
              }
            }
LABEL_63:
            v38 = ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(v74, v35);
            if ( v38 < 0 )
            {
              ATL::CAtlException::CAtlException((ATL::CAtlException *)v62, v38);
              throw (ATL::CAtlException *)v62;
            }
            v48 = ++v28;
          }
          while ( v38 != 265926 );
        }
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v82) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_2bfd5d99a55d3caeb8686f61088fb984_Traceguids,
            *(unsigned int *)v82);
        v16 = v63[0];
        v11 = v79;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000A02D);
      }
    }
LABEL_121:
    ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::Close(&v64);
    v39 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v40 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    ATL::CCommandBase::ReleaseCommand((ATL::CCommandBase *)&v77);
    if ( (_QWORD)v77 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v77 + 16LL))(v77);
    ATL::CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>::~CAccessorRowset<ATL::CDynamicAccessor,ATL::CRowset>(&v64);
    v41 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v41 = v47;
    }
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v50 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    if ( v11 )
      CoTaskMemFree(v11);
    if ( v16 )
      CoTaskMemFree(v16);
    if ( v85 >= 8 )
      operator delete(Src[0]);
    v85 = 7;
    v84 = 0;
    LOWORD(Src[0]) = 0;
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
}

```

## disassembly

```asm
0x1800099e4  push    rbx
0x1800099e6  push    rsi
0x1800099e7  push    rdi
0x1800099e8  push    r12
0x1800099ea  push    r14
0x1800099ec  push    r15
0x1800099ee  sub     rsp, 1C8h
0x1800099f5  mov     rax, cs:__security_cookie
0x1800099fc  xor     rax, rsp
0x1800099ff  mov     [rsp+1F8h+var_48], rax
0x180009a07  mov     rbx, rcx
0x180009a0a  mov     [rsp+1F8h+var_C8], rcx
0x180009a12  mov     [rsp+1F8h+var_B8], rcx
0x180009a1a  xor     esi, esi
0x180009a1c  mov     [rsp+1F8h+var_1B0], esi
0x180009a20  lea     rcx, [rsp+1F8h+var_1B0]
0x180009a25  call    cs:__imp_FhQueryConfiguredUsersCount
0x180009a2b  test    eax, eax
0x180009a2d  js      loc_18000A18F
0x180009a33  cmp     [rsp+1F8h+var_1B0], esi
0x180009a37  jz      loc_18000A16E
0x180009a3d  mov     [rsp+1F8h+var_1B8], rsi
0x180009a42  mov     rcx, [rbx+8]
0x180009a46  mov     rax, [rcx]
0x180009a49  lea     rdx, [rsp+1F8h+var_1B8]
0x180009a4e  mov     rax, [rax+0C8h]
0x180009a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5a  test    eax, eax
0x180009a5c  js      loc_18000A1AD
0x180009a62  mov     [rsp+1F8h+var_80], 7
0x180009a6e  mov     [rsp+1F8h+var_88], rsi
0x180009a76  mov     word ptr [rsp+1F8h+Src], si
0x180009a7e  mov     r8d, 10h
0x180009a84  lea     rdx, aAndScopeDp; "AND SCOPE='DP://"
0x180009a8b  lea     rcx, [rsp+1F8h+Src]; Src
0x180009a93  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180009a98  nop
0x180009a99  lea     rdx, [rbx+20h]
0x180009a9d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180009aa1  xor     r8d, r8d
0x180009aa4  lea     rcx, [rsp+1F8h+Src]
0x180009aac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180009ab1  lea     rdx, asc_18000E48C; "/'"
0x180009ab8  lea     rcx, [rsp+1F8h+Src]; Src
0x180009ac0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180009ac5  mov     rcx, [rsp+1F8h+var_1B8]
0x180009aca  mov     rax, [rcx]
0x180009acd  lea     rdx, [rsp+1F8h+Src]
0x180009ad5  cmp     [rsp+1F8h+var_80], 8
0x180009ade  cmovnb  rdx, [rsp+1F8h+Src]
0x180009ae7  mov     rax, [rax+80h]
0x180009aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009af3  test    eax, eax
0x180009af5  js      loc_18000A1CB
0x180009afb  mov     rcx, [rsp+1F8h+var_1B8]
0x180009b00  mov     rax, [rcx]
0x180009b03  lea     rdx, aSystemItemdate; "System.ItemDate ASC"
0x180009b0a  mov     rax, [rax+90h]
0x180009b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b16  test    eax, eax
0x180009b18  js      loc_18000A1E9
0x180009b1e  mov     rcx, [rsp+1F8h+var_1B8]
0x180009b23  mov     rax, [rcx]
0x180009b26  xor     edx, edx
0x180009b28  mov     rax, [rax+60h]
0x180009b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b31  test    eax, eax
0x180009b33  js      loc_18000A207
0x180009b39  mov     rcx, [rsp+1F8h+var_1B8]
0x180009b3e  mov     rax, [rcx]
0x180009b41  mov     r14d, 1
0x180009b47  mov     edx, r14d
0x180009b4a  mov     rax, [rax+50h]
0x180009b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b53  test    eax, eax
0x180009b55  js      loc_18000A22B
0x180009b5b  lea     rdx, [rsp+1F8h+var_1B8]
0x180009b60  lea     rcx, [rsp+1F8h+var_158]
0x180009b68  call    ?_GenerateSQLFromUserQuery@@YA?AV?$unique_ptr@GUCoTaskMemDeleter@@@std@@AEBV?$CComPtr@UISearchQueryHelper@@@ATL@@PEBG@Z; _GenerateSQLFromUserQuery(ATL::CComPtr<ISearchQueryHelper> const &,ushort const *)
0x180009b6d  nop
0x180009b6e  mov     [rsp+1F8h+pv], rsi
0x180009b73  mov     rcx, [rsp+1F8h+var_1B8]
0x180009b78  mov     rax, [rcx]
0x180009b7b  lea     rdx, [rsp+1F8h+pv]
0x180009b80  mov     rax, [rax+18h]
0x180009b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b89  test    eax, eax
0x180009b8b  js      loc_18000A24F
0x180009b91  mov     rbx, [rsp+1F8h+pv]
0x180009b96  mov     [rsp+1F8h+var_C0], rbx
0x180009b9e  mov     [rsp+1F8h+var_190], rsi
0x180009ba3  mov     rdx, rbx; unsigned __int16 *
0x180009ba6  lea     rcx, [rsp+1F8h+var_190]; this
0x180009bab  call    ?OpenFromInitializationString@CDataSource@ATL@@QEAAJPEBG_N@Z; ATL::CDataSource::OpenFromInitializationString(ushort const *,bool)
0x180009bb0  test    eax, eax
0x180009bb2  js      loc_18000A257
0x180009bb8  mov     [rsp+1F8h+var_1A8], rsi
0x180009bbd  lea     rdx, [rsp+1F8h+var_190]; struct ATL::CDataSource *
0x180009bc2  lea     rcx, [rsp+1F8h+var_1A8]; this
0x180009bc7  call    ?Open@CSession@ATL@@QEAAJAEBVCDataSource@2@PEAUtagDBPROPSET@@K@Z; ATL::CSession::Open(ATL::CDataSource const &,tagDBPROPSET *,ulong)
0x180009bcc  test    eax, eax
0x180009bce  js      loc_18000A27B
0x180009bd4  mov     [rsp+1F8h+var_148], rsi
0x180009bdc  mov     [rsp+1F8h+var_140], esi
0x180009be3  mov     [rsp+1F8h+var_138], rsi
0x180009beb  mov     [rsp+1F8h+var_130], rsi
0x180009bf3  mov     [rsp+1F8h+var_120], rsi
0x180009bfb  mov     [rsp+1F8h+var_118], rsi
0x180009c03  mov     [rsp+1F8h+var_10C], esi
0x180009c0a  mov     [rsp+1F8h+var_108], 1F40h
0x180009c16  mov     [rsp+1F8h+var_128], rsi
0x180009c1e  mov     [rsp+1F8h+var_100], rsi
0x180009c26  mov     [rsp+1F8h+var_F8], rsi
0x180009c2e  mov     [rsp+1F8h+var_E0], rsi
0x180009c36  mov     [rsp+1F8h+var_E8], rsi
0x180009c3e  lea     rax, [rsp+1F8h+var_148]
0x180009c46  mov     [rsp+1F8h+var_F0], rax
0x180009c4e  xorps   xmm0, xmm0
0x180009c51  movdqa  [rsp+1F8h+var_D8], xmm0
0x180009c5a  mov     rdi, [rsp+1F8h+var_158]
0x180009c62  mov     r8, rdi
0x180009c65  lea     rdx, [rsp+1F8h+var_1A8]
0x180009c6a  lea     rcx, [rsp+1F8h+var_148]; this
0x180009c72  call    ?Open@?$CCommand@VCDynamicAccessor@ATL@@VCRowset@2@VCNoMultipleResults@2@@ATL@@QEAAJAEBVCSession@2@PEBGPEAUtagDBPROPSET@@PEA_JAEBU_GUID@@_NK@Z; ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::Open(ATL::CSession const &,ushort const *,tagDBPROPSET *,__int64 *,_GUID const &,bool,ulong)
0x180009c77  test    eax, eax
0x180009c79  js      loc_18000A29F
0x180009c7f  mov     rdx, [rsp+1F8h+var_100]; struct IRowset *
0x180009c87  mov     rcx, [rsp+1F8h+var_F0]; this
0x180009c8f  call    ?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z; ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)
0x180009c94  nop
0x180009c95  cmp     [rsp+1F8h+var_E8], rsi
0x180009c9d  jz      short loc_180009CD3
0x180009c9f  mov     rcx, [rsp+1F8h+var_100]
0x180009ca7  mov     rax, [rcx]
0x180009caa  mov     [rsp+1F8h+var_1D0], rsi
0x180009caf  mov     [rsp+1F8h+var_1D8], rsi
0x180009cb4  xor     r9d, r9d
0x180009cb7  lea     r8, [rsp+1F8h+var_E8]
0x180009cbf  mov     rdx, r14
0x180009cc2  mov     rax, [rax+30h]
0x180009cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ccb  mov     [rsp+1F8h+var_E8], rsi
0x180009cd3  mov     rcx, [rsp+1F8h+var_100]
0x180009cdb  mov     rax, [rcx]
0x180009cde  xor     edx, edx
0x180009ce0  mov     rax, [rax+38h]
0x180009ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ce9  mov     edx, eax
0x180009ceb  test    eax, eax
0x180009ced  js      short loc_180009CFE
0x180009cef  lea     rcx, [rsp+1F8h+var_100]
0x180009cf7  call    ?MoveNext@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAJXZ; ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(void)
0x180009cfc  mov     edx, eax; int
0x180009cfe  test    edx, edx
0x180009d00  js      loc_18000A2C3
0x180009d06  cmp     edx, 40EC6h
0x180009d0c  jz      loc_18000A02B
0x180009d12  mov     r15d, esi
0x180009d15  add     r15d, r14d
0x180009d18  lea     rcx, [rsp+1F8h+var_100]
0x180009d20  call    ?MoveNext@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAJXZ; ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(void)
0x180009d25  test    eax, eax
0x180009d27  js      short loc_180009D30
0x180009d29  cmp     eax, 40EC6h
0x180009d2e  jnz     short loc_180009D15
0x180009d30  lea     r9, WPP_GLOBAL_Control
0x180009d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d3e  cmp     rcx, r9
0x180009d41  jz      short loc_180009D63
0x180009d43  test    byte ptr [rcx+1Ch], 8
0x180009d47  jz      short loc_180009D63
0x180009d49  mov     r9d, r15d
0x180009d4c  mov     rcx, [rcx+10h]
0x180009d50  call    WPP_SF_d
0x180009d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d5c  lea     r9, WPP_GLOBAL_Control
0x180009d63  xor     edx, edx
0x180009d65  mov     eax, 4E20h
0x180009d6a  div     [rsp+1F8h+var_1B0]
0x180009d6e  mov     r8d, eax
0x180009d71  cmp     r15d, eax
0x180009d74  jbe     loc_18000A02B
0x180009d7a  mov     eax, 0CCCCCCCDh
0x180009d7f  mul     r8d
0x180009d82  mov     r12d, edx
0x180009d85  shr     r12d, 2
0x180009d89  mov     dword ptr [rsp+1F8h+pv], r12d
0x180009d8e  cmp     rcx, r9
0x180009d91  jz      short loc_180009DAB
0x180009d93  test    byte ptr [rcx+1Ch], 8
0x180009d97  jz      short loc_180009DAB
0x180009d99  mov     dword ptr [rsp+1F8h+var_1D8], r15d
0x180009d9e  mov     r9d, r12d
0x180009da1  mov     rcx, [rcx+10h]
0x180009da5  call    WPP_SF_dd
0x180009daa  nop
0x180009dab  mov     rdx, [rsp+1F8h+var_100]; struct IRowset *
0x180009db3  mov     rcx, [rsp+1F8h+var_F0]; this
0x180009dbb  call    ?FreeRecordMemory@CDynamicAccessor@ATL@@QEAAXPEAUIRowset@@@Z; ATL::CDynamicAccessor::FreeRecordMemory(IRowset *)
0x180009dc0  nop
0x180009dc1  cmp     [rsp+1F8h+var_E8], rsi
0x180009dc9  jz      short loc_180009DFF
0x180009dcb  mov     rcx, [rsp+1F8h+var_100]
0x180009dd3  mov     rax, [rcx]
0x180009dd6  mov     [rsp+1F8h+var_1D0], rsi
0x180009ddb  mov     [rsp+1F8h+var_1D8], rsi
0x180009de0  xor     r9d, r9d
0x180009de3  lea     r8, [rsp+1F8h+var_E8]
0x180009deb  mov     rdx, r14
0x180009dee  mov     rax, [rax+30h]
0x180009df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df7  mov     [rsp+1F8h+var_E8], rsi
0x180009dff  mov     rcx, [rsp+1F8h+var_100]
0x180009e07  mov     rax, [rcx]
0x180009e0a  xor     edx, edx
0x180009e0c  mov     rax, [rax+38h]
0x180009e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e15  test    eax, eax
0x180009e17  js      short loc_180009E27
0x180009e19  lea     rcx, [rsp+1F8h+var_100]
0x180009e21  call    ?MoveNext@?$CRowset@VCDynamicAccessor@ATL@@@ATL@@QEAAJXZ; ATL::CRowset<ATL::CDynamicAccessor>::MoveNext(void)
0x180009e26  nop
0x180009e27  test    eax, eax
0x180009e29  js      loc_18000A2E4
0x180009e2f  mov     r15d, esi
0x180009e32  mov     [rsp+1F8h+var_1A0], esi
0x180009e36  cmp     r12d, r15d
0x180009e39  jbe     loc_18000A02B
0x180009e3f  cmp     [rsp+1F8h+var_110], sil
0x180009e47  jz      short loc_180009E7E
0x180009e49  mov     edx, esi
0x180009e4b  cmp     [rsp+1F8h+var_130], rsi
0x180009e53  jbe     short loc_180009E9D
0x180009e55  mov     r8, [rsp+1F8h+var_120]
0x180009e5d  mov     ecx, edx
0x180009e5f  lea     rax, [rcx+rcx*4]
0x180009e63  add     rax, rax
0x180009e66  cmp     [r8+rax*8+10h], r14
0x180009e6b  jz      short loc_180009EA8
0x180009e6d  add     edx, r14d
0x180009e70  mov     eax, edx
0x180009e72  cmp     rax, [rsp+1F8h+var_130]
0x180009e7a  jb      short loc_180009E5D
0x180009e7c  jmp     short loc_180009E9D
0x180009e7e  mov     r8, [rsp+1F8h+var_120]
0x180009e86  mov     rdx, [r8+10h]
0x180009e8a  mov     rcx, [rsp+1F8h+var_130]
0x180009e92  dec     rcx
0x180009e95  add     rcx, rdx
0x180009e98  cmp     rcx, r14
0x180009e9b  jnb     short loc_180009EA2
0x180009e9d  mov     rdx, rsi
0x180009ea0  jmp     short loc_180009EBD
0x180009ea2  mov     rcx, r14
0x180009ea5  sub     rcx, rdx
0x180009ea8  lea     rax, [rcx+rcx*4]
0x180009eac  shl     rax, 4
0x180009eb0  mov     rdx, [rsp+1F8h+var_138]
0x180009eb8  add     rdx, [rax+r8+8]; void *
0x180009ebd  mov     [rsp+1F8h+var_58], 7
0x180009ec9  mov     [rsp+1F8h+var_60], rsi
0x180009ed1  mov     word ptr [rsp+1F8h+var_70], si
0x180009ed9  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009edd  inc     r8
0x180009ee0  cmp     [rdx+r8*2], si
0x180009ee5  jnz     short loc_180009EDD
0x180009ee7  lea     rcx, [rsp+1F8h+var_70]; Src
0x180009eef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180009ef4  nop
0x180009ef5  lea     rdx, [rsp+1F8h+var_70]
0x180009efd  mov     rcx, [rsp+1F8h+var_C8]
0x180009f05  call    ?NotifyDelete@DpSearch@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DpSearch::NotifyDelete(std::wstring const &)
0x180009f0a  nop
0x180009f0b  cmp     [rsp+1F8h+var_58], 8
0x180009f14  jb      short loc_180009F24
0x180009f16  mov     rcx, [rsp+1F8h+var_70]
0x180009f1e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009f24  mov     r10, cs:WPP_GLOBAL_Control
0x180009f2b  lea     rax, WPP_GLOBAL_Control
0x180009f32  cmp     r10, rax
0x180009f35  jz      loc_180009FCE
0x180009f3b  test    byte ptr [r10+1Ch], 8
0x180009f40  jz      loc_180009FCE
0x180009f46  cmp     [rsp+1F8h+var_110], sil
0x180009f4e  jz      short loc_180009F85
0x180009f50  mov     edx, esi
0x180009f52  cmp     [rsp+1F8h+var_130], rsi
0x180009f5a  jbe     short loc_180009FA4
0x180009f5c  mov     r8, [rsp+1F8h+var_120]
0x180009f64  mov     ecx, edx
0x180009f66  lea     rax, [rcx+rcx*4]
0x180009f6a  add     rax, rax
0x180009f6d  cmp     [r8+rax*8+10h], r14
0x180009f72  jz      short loc_180009FAF
0x180009f74  add     edx, r14d
0x180009f77  mov     eax, edx
0x180009f79  cmp     rax, [rsp+1F8h+var_130]
0x180009f81  jb      short loc_180009F64
0x180009f83  jmp     short loc_180009FA4
0x180009f85  mov     r8, [rsp+1F8h+var_120]
  ... truncated ...
```
