# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180002fc0`
- end: `0x1800038bc`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `2300`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `15`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180002fb0`
- `0x180009690`
- `0x1800096a0`
- `0x1800096b0`
- `0x1800096c0`
- `0x1800096d0`
- `0x1800096e0`
- `0x1800096f0`
- `0x180009700`
- `0x180009710`
- `0x180009720`
- `0x180009730`
- `0x180009740`
- `0x180009750`
- `0x180009760`

## callees

- `0x180002fc0`
- `0x1800038d0`
- `0x180003a20`
- `0x180006aa0`
- `0x180007490`
- `0x1800082a0`
- `0x1800088bc`
- `0x1800091e8`
- `0x18000b230`
- `0x18000c91e`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003035`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003476`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003035`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003476`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033a9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003415`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003658`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800036db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800036f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800033a9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003415`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003658`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800036db`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800036f1`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003549`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180003549`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800034ed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800034ed`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180003164`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180003171`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180003164`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180003171`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800034af`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800034af`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800034d7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800034d7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003198`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800031a5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003198`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800031a5`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000317e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000318b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000317e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x18000318b`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000343f`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000343f`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, __int64 a2)
{
  int v2; // r12d
  struct IHttpContext *v5; // rdi
  __int64 v6; // rbx
  __int64 (__fastcall ***v7)(_QWORD, void *); // rax
  FILTER_LIST *v8; // rsi
  _DWORD *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  BOOL v12; // r15d
  __int64 v13; // rbx
  __int64 v14; // r14
  W3_FILTER_CONTEXT *v15; // rax
  __int64 v16; // rax
  int v17; // r15d
  _DWORD *v18; // rax
  int v19; // eax
  int v20; // eax
  _DWORD *v21; // rsi
  _DWORD *v22; // r14
  _DWORD *v23; // rax
  int v24; // eax
  int v25; // eax
  W3_FILTER_CONTEXT *v27; // rax
  FILTER_LIST *v28; // rax
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *Str; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 (__fastcall ***v35)(_QWORD, void *); // rax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  unsigned int v39; // eax
  unsigned int v40; // eax
  bool v41; // zf
  __int64 (*v42)(void); // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  unsigned int v46; // [rsp+40h] [rbp-C0h] BYREF
  int v47; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeSectionException *v49; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v50[7]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v51[64]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v52[8]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v53[64]; // [rsp+150h] [rbp+50h] BYREF

  v2 = 0;
  v49 = 0;
  v48 = 0;
  v47 = 0;
  memset(v52, 0, sizeof(v52));
  STRU::STRU((STRU *)v51, (unsigned __int16 *)v52, 0x40u);
  v46 = 0;
  if ( a1 != 256 )
    goto LABEL_36;
  v5 = (struct IHttpContext *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 232LL))(v5) )
    goto LABEL_36;
  v6 = (**(__int64 (__fastcall ***)(struct IHttpContext *))v5)(v5);
  v7 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v8 = (FILTER_LIST *)(**v7)(v7, g_pFilterModuleContext);
  if ( !v8 )
  {
    memset_0(v53, 0, sizeof(v53));
    STRU::STRU((STRU *)v50, v53, 0x40u);
    v28 = (FILTER_LIST *)operator new(0xC0u);
    if ( v28 && (v8 = FILTER_LIST::FILTER_LIST(v28)) != 0 )
    {
      v17 = STRU::Copy((STRU *)v50, L"MACHINE/WEBROOT/APPHOST/");
      if ( v17 < 0
        || (v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6),
            v17 = STRU::Append((STRU *)v50, v29),
            v17 < 0) )
      {
LABEL_56:
        (**(void (__fastcall ***)(FILTER_LIST *))v8)(v8);
        STRU::~STRU((STRU *)v50);
        goto LABEL_38;
      }
      Str = STRU::QueryStr((STRU *)v50);
      v17 = FILTER_LIST::LoadFilters(v8, Str, (struct STRU *)v51, (enum FILTER_FAILURE_POINT *)&v46, &v49);
      if ( v17 < 0 )
      {
        v31 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 32LL))(v5);
        *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31) + 536) = 0;
        if ( STRU::QueryCCH((STRU *)v51) )
        {
          UpdateErrorDescription(v5, v46, v51);
          v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 32LL))(v5);
          (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v32 + 24LL))(
            v32,
            500,
            "Internal Server Error",
            0,
            v17,
            0,
            0);
        }
        else
        {
          if ( v49 )
            (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v49)(
              v49,
              &IID_IAppHostConfigException,
              &v48);
          v33 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 32LL))(v5);
          (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v33 + 24LL))(
            v33,
            500,
            "Internal Server Error",
            19,
            v17,
            v48,
            0);
          if ( v48 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            v48 = 0;
          }
        }
        if ( v49 )
        {
          (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v49 + 16LL))(v49);
          v49 = 0;
        }
        goto LABEL_56;
      }
      v34 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      v17 = (*(__int64 (__fastcall **)(__int64, FILTER_LIST *, void *))(*(_QWORD *)v34 + 8LL))(
              v34,
              v8,
              g_pFilterModuleContext);
      if ( v17 >= 0 )
      {
LABEL_60:
        STRU::~STRU((STRU *)v50);
        goto LABEL_4;
      }
      (**(void (__fastcall ***)(FILTER_LIST *))v8)(v8);
      if ( v17 == -2147024811 )
      {
        v35 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        v8 = (FILTER_LIST *)(**v35)(v35, g_pFilterModuleContext);
        goto LABEL_60;
      }
    }
    else
    {
      v17 = -2147024888;
    }
    STRU::~STRU((STRU *)v50);
    goto LABEL_38;
  }
LABEL_4:
  v9 = (_DWORD *)((char *)v8 + 72);
  if ( !*((_DWORD *)v8 + 32) && !*v9 )
    goto LABEL_36;
  if ( !*((_DWORD *)v8 + 46) )
  {
    v36 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 32LL))(v5);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 112LL))(v36, 10);
  }
  v10 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 24LL))(v5);
  v11 = *(_QWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) + 840);
  v12 = v11 != 0;
  if ( !*((_DWORD *)v8 + 4) )
    goto LABEL_11;
  if ( v11 )
    v9 = (_DWORD *)((char *)v8 + 128);
  if ( (*v9 & 0x100) != 0 )
  {
    v27 = (W3_FILTER_CONTEXT *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)W3_FILTER_CONTEXT::sm_pachFilterContexts);
    if ( !v27 )
      goto LABEL_42;
    v15 = W3_FILTER_CONTEXT::W3_FILTER_CONTEXT(v27, v5, v12, 0);
    v14 = (__int64)v15;
    if ( !v15 )
      goto LABEL_42;
    v13 = (__int64)v15;
  }
  else
  {
LABEL_11:
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64))(*(_QWORD *)v5 + 144LL))(v5, 520);
    if ( !v13 )
      goto LABEL_42;
    v2 = 1;
    *(_QWORD *)v13 = &W3_FILTER_CONTEXT::`vftable';
    BUFFER::BUFFER((BUFFER *)(v13 + 160));
    BUFFER::BUFFER((BUFFER *)(v13 + 208));
    STRA::STRA((STRA *)(v13 + 288));
    STRA::STRA((STRA *)(v13 + 344));
    STRU::STRU((STRU *)(v13 + 408));
    STRU::STRU((STRU *)(v13 + 464));
    *(_DWORD *)(v13 + 12) = 1;
    *(_QWORD *)(v13 + 32) = 0;
    *(_QWORD *)(v13 + 112) = 0;
    v14 = v13;
    *(_QWORD *)(v13 + 264) = 0;
    *(_QWORD *)(v13 + 272) = 0;
    *(_DWORD *)(v13 + 256) = 0;
    *(_QWORD *)(v13 + 148) = 0;
    *(_QWORD *)(v13 + 136) = 0;
    *(_DWORD *)(v13 + 144) = 0;
    *(_DWORD *)(v13 + 400) = 0;
    *(_QWORD *)(v13 + 24) = v5;
    *(_DWORD *)(v13 + 280) = -1;
    *(_DWORD *)(v13 + 16) = 1;
    *(_QWORD *)(v13 + 128) = v13 + 120;
    *(_QWORD *)(v13 + 120) = v13 + 120;
    *(_QWORD *)(v13 + 104) = W3_FILTER_CONTEXT::ServerSupportFunction;
    *(_QWORD *)(v13 + 72) = W3_FILTER_CONTEXT::GetServerVariable;
    *(_QWORD *)(v13 + 80) = W3_FILTER_CONTEXT::AddResponseHeaders;
    *(_QWORD *)(v13 + 88) = W3_FILTER_CONTEXT::WriteClient;
    *(_QWORD *)(v13 + 96) = W3_FILTER_CONTEXT::AllocateMemory;
    *(_DWORD *)(v13 + 40) = 72;
    *(_DWORD *)(v13 + 44) = 655360;
    *(_QWORD *)(v13 + 48) = v13;
    *(_DWORD *)(v13 + 56) = 0;
    *(_QWORD *)(v13 + 64) = 0;
    *(_DWORD *)(v13 + 60) = v12;
    *(_DWORD *)(v13 + 8) = 1128674135;
  }
  _InterlockedIncrement((volatile signed __int32 *)v8 + 3);
  *(_QWORD *)(v13 + 112) = v8;
  v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)v5 + 56LL))(v5);
  v17 = (*(__int64 (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v16 + 8LL))(v16, v13, g_pFilterModuleContext);
  if ( v17 < 0 )
  {
    (**(void (__fastcall ***)(__int64))v13)(v13);
    goto LABEL_38;
  }
  if ( *(_DWORD *)(v13 + 256) || (v18 = *(_DWORD **)(v13 + 112)) == 0 )
  {
    v21 = (_DWORD *)(v13 + 60);
    if ( *(_DWORD *)(v13 + 60) )
      v37 = *(_DWORD *)(v13 + 148);
    else
      v37 = *(_DWORD *)(v13 + 152);
    v20 = v37 & 0x400;
  }
  else
  {
    if ( v18[4] )
    {
      if ( *(_DWORD *)(v13 + 60) )
        v19 = v18[32];
      else
        v19 = v18[18];
      v20 = v19 & 0x400;
    }
    else
    {
      v20 = 0;
    }
    v21 = (_DWORD *)(v13 + 60);
  }
  if ( v20 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const wchar_t *))(*(_QWORD *)v5 + 136LL))(
            v5,
            "EDITING_RESPONSE_ENTITY",
            L"1");
    if ( v17 < 0 )
      goto LABEL_38;
    v22 = (_DWORD *)(v14 + 60);
  }
  else
  {
    v22 = v21;
  }
  if ( v2 )
  {
    v22 = v21;
    goto LABEL_27;
  }
  if ( !W3_FILTER_CONTEXT::QueryConnectionContext((W3_FILTER_CONTEXT *)v13) )
  {
LABEL_42:
    v17 = -2147024888;
    goto LABEL_38;
  }
LABEL_27:
  if ( *(_DWORD *)(v13 + 256) )
  {
    v21 = v22;
LABEL_76:
    if ( *v21 )
      v24 = *(_DWORD *)(v13 + 148);
    else
      v24 = *(_DWORD *)(v13 + 152);
    goto LABEL_32;
  }
  v23 = *(_DWORD **)(v13 + 112);
  if ( !v23 )
    goto LABEL_76;
  if ( !v23[4] )
  {
    v25 = 0;
    goto LABEL_33;
  }
  if ( *(_DWORD *)(v13 + 60) )
    v24 = v23[32];
  else
    v24 = v23[18];
LABEL_32:
  v25 = v24 & 0x4000;
LABEL_33:
  if ( !v25 )
  {
LABEL_36:
    STRU::~STRU((STRU *)v51);
    return 0;
  }
  v50[3] = 0;
  v50[0] = W3_FILTER_CONTEXT::GetFilterHeader;
  v50[1] = W3_FILTER_CONTEXT::SetFilterHeader;
  v50[2] = W3_FILTER_CONTEXT::AddFilterHeader;
  v17 = W3_FILTER_CONTEXT::NotifyFilters((W3_FILTER_CONTEXT *)v13, 0x4000u, v50, &v47);
  if ( v17 < 0 )
  {
    v38 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 24) + 32LL))(*(_QWORD *)(v13 + 24));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 96LL))(v38);
    v39 = WIN32_FROM_HRESULT(v17) - 2;
    if ( v39 && (v40 = v39 - 1) != 0 )
    {
      v41 = v40 == 2;
      v42 = *(__int64 (**)(void))(**(_QWORD **)(v13 + 24) + 32LL);
      if ( v41 )
      {
        v44 = v42();
        (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, _QWORD, _DWORD))(*(_QWORD *)v44 + 24LL))(
          v44,
          401,
          "Unauthorized",
          4,
          v17,
          0,
          0);
      }
      else
      {
        v43 = v42();
        (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v43 + 24LL))(
          v43,
          500,
          "Internal Server Error",
          0,
          v17,
          0,
          0);
      }
    }
    else
    {
      v45 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v13 + 24) + 32LL))(*(_QWORD *)(v13 + 24));
      (*(void (__fastcall **)(__int64, __int64, const char *, _QWORD, int, _QWORD, _DWORD))(*(_QWORD *)v45 + 24LL))(
        v45,
        404,
        "Not Found",
        0,
        v17,
        0,
        0);
    }
  }
  else if ( !v47 )
  {
    goto LABEL_36;
  }
LABEL_38:
  (**(void (__fastcall ***)(__int64, _QWORD))a2)(a2, (unsigned int)v17);
  STRU::~STRU((STRU *)v51);
  return 1;
}

```

## disassembly

```asm
0x180002fc0  push    rbp
0x180002fc2  push    rbx
0x180002fc3  push    rsi
0x180002fc4  push    rdi
0x180002fc5  push    r12
0x180002fc7  push    r13
0x180002fc9  push    r14
0x180002fcb  push    r15
0x180002fcd  lea     rbp, [rsp-0E8h]
0x180002fd5  sub     rsp, 1E8h
0x180002fdc  mov     rax, cs:__security_cookie
0x180002fe3  xor     rax, rsp
0x180002fe6  mov     [rbp+120h+var_50], rax
0x180002fed  xorps   xmm0, xmm0
0x180002ff0  xor     r12d, r12d
0x180002ff3  mov     r13, rdx
0x180002ff6  mov     [rsp+220h+var_1D0], r12
0x180002ffb  mov     ebx, ecx
0x180002ffd  mov     [rsp+220h+var_1D8], r12
0x180003002  lea     rdx, [rbp+120h+var_150]
0x180003006  mov     [rsp+220h+var_1DC], r12d
0x18000300b  lea     rcx, [rbp+120h+var_190]
0x18000300f  mov     r8d, 40h ; '@'
0x180003015  movups  [rbp+120h+var_150], xmm0
0x180003019  movups  [rbp+120h+var_140], xmm0
0x18000301d  movups  [rbp+120h+var_130], xmm0
0x180003021  movups  [rbp+120h+var_120], xmm0
0x180003025  movups  [rbp+120h+var_110], xmm0
0x180003029  movups  [rbp+120h+var_100], xmm0
0x18000302d  movups  [rbp+120h+var_F0], xmm0
0x180003031  movups  [rbp+120h+var_E0], xmm0
0x180003035  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000303b  mov     [rsp+220h+var_1E0], r12d
0x180003040  cmp     ebx, 100h
0x180003046  jnz     loc_1800033A5
0x18000304c  mov     rax, [r13+0]
0x180003050  mov     rcx, r13
0x180003053  mov     rax, [rax+8]
0x180003057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305c  mov     rdi, rax
0x18000305f  mov     rcx, [rax]
0x180003062  mov     rax, [rcx+0E8h]
0x180003069  mov     rcx, rdi
0x18000306c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003071  test    rax, rax
0x180003074  jnz     loc_1800033A5
0x18000307a  mov     rcx, [rdi]
0x18000307d  mov     rax, [rcx]
0x180003080  mov     rcx, rdi
0x180003083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003088  mov     rbx, rax
0x18000308b  mov     rcx, [rax]
0x18000308e  mov     rax, [rcx+10h]
0x180003092  mov     rcx, rbx
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  mov     rdx, cs:?g_pFilterModuleContext@@3PEAXEA; void * g_pFilterModuleContext
0x1800030a1  mov     r9, rax
0x1800030a4  mov     rcx, [rax]
0x1800030a7  mov     rax, [rcx]
0x1800030aa  mov     rcx, r9
0x1800030ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b2  mov     rsi, rax
0x1800030b5  test    rax, rax
0x1800030b8  jz      loc_180003456
0x1800030be  lea     r14, [rsi+80h]
0x1800030c5  lea     rbx, [rsi+48h]
0x1800030c9  cmp     [r14], r12d
0x1800030cc  jz      loc_1800036FC
0x1800030d2  cmp     [rsi+0B8h], r12d
0x1800030d9  jz      loc_18000370A
0x1800030df  mov     rax, [rdi]
0x1800030e2  mov     rcx, rdi
0x1800030e5  mov     rax, [rax+18h]
0x1800030e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ee  mov     rdx, rax
0x1800030f1  mov     rcx, [rax]
0x1800030f4  mov     rax, [rcx+8]
0x1800030f8  mov     rcx, rdx
0x1800030fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003100  mov     r15d, r12d
0x180003103  mov     rcx, [rax+348h]
0x18000310a  test    rcx, rcx
0x18000310d  setnz   r15b
0x180003111  cmp     [rsi+10h], r12d
0x180003115  jz      short loc_18000312A
0x180003117  test    rcx, rcx
0x18000311a  cmovnz  rbx, r14
0x18000311e  test    dword ptr [rbx], 100h
0x180003124  jnz     loc_180003438
0x18000312a  mov     rax, [rdi]
0x18000312d  mov     edx, 208h
0x180003132  mov     rcx, rdi
0x180003135  mov     rax, [rax+90h]
0x18000313c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003141  mov     rbx, rax
0x180003144  test    rax, rax
0x180003147  jz      loc_18000344E
0x18000314d  lea     rax, ??_7W3_FILTER_CONTEXT@@6B@; const W3_FILTER_CONTEXT::`vftable'
0x180003154  mov     r12d, 1
0x18000315a  lea     rcx, [rbx+0A0h]
0x180003161  mov     [rbx], rax
0x180003164  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000316a  lea     rcx, [rbx+0D0h]
0x180003171  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180003177  lea     rcx, [rbx+120h]
0x18000317e  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003184  lea     rcx, [rbx+158h]
0x18000318b  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180003191  lea     rcx, [rbx+198h]
0x180003198  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000319e  lea     rcx, [rbx+1D0h]
0x1800031a5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800031ab  xor     ecx, ecx
0x1800031ad  mov     [rbx+0Ch], r12d
0x1800031b1  lea     rax, [rbx+78h]
0x1800031b5  mov     [rbx+20h], rcx
0x1800031b9  mov     [rbx+70h], rcx
0x1800031bd  mov     r14, rbx
0x1800031c0  mov     [rbx+108h], rcx
0x1800031c7  mov     [rbx+110h], rcx
0x1800031ce  mov     [rbx+100h], ecx
0x1800031d4  mov     [rbx+94h], rcx
0x1800031db  mov     [rbx+88h], rcx
0x1800031e2  mov     [rbx+90h], ecx
0x1800031e8  mov     [rbx+190h], ecx
0x1800031ee  mov     [rbx+18h], rdi
0x1800031f2  mov     dword ptr [rbx+118h], 0FFFFFFFFh
0x1800031fc  mov     [rbx+10h], r12d
0x180003200  mov     [rax+8], rax
0x180003204  mov     [rax], rax
0x180003207  lea     rax, ?ServerSupportFunction@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@W4SF_REQ_TYPE@@PEAX_K3@Z; W3_FILTER_CONTEXT::ServerSupportFunction(_HTTP_FILTER_CONTEXT *,SF_REQ_TYPE,void *,unsigned __int64,unsigned __int64)
0x18000320e  mov     [rbx+68h], rax
0x180003212  lea     rax, ?GetServerVariable@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADPEAXPEAK@Z; W3_FILTER_CONTEXT::GetServerVariable(_HTTP_FILTER_CONTEXT *,char *,void *,ulong *)
0x180003219  mov     [rbx+48h], rax
0x18000321d  lea     rax, ?AddResponseHeaders@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADK@Z; W3_FILTER_CONTEXT::AddResponseHeaders(_HTTP_FILTER_CONTEXT *,char *,ulong)
0x180003224  mov     [rbx+50h], rax
0x180003228  lea     rax, ?WriteClient@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAXPEAKK@Z; W3_FILTER_CONTEXT::WriteClient(_HTTP_FILTER_CONTEXT *,void *,ulong *,ulong)
0x18000322f  mov     [rbx+58h], rax
0x180003233  lea     rax, ?AllocateMemory@W3_FILTER_CONTEXT@@SAPEAXPEAU_HTTP_FILTER_CONTEXT@@KK@Z; W3_FILTER_CONTEXT::AllocateMemory(_HTTP_FILTER_CONTEXT *,ulong,ulong)
0x18000323a  mov     [rbx+60h], rax
0x18000323e  mov     dword ptr [rbx+28h], 48h ; 'H'
0x180003245  mov     dword ptr [rbx+2Ch], 0A0000h
0x18000324c  mov     [rbx+30h], rbx
0x180003250  mov     [rbx+38h], ecx
0x180003253  mov     [rbx+40h], rcx
0x180003257  mov     [rbx+3Ch], r15d
0x18000325b  mov     dword ptr [rbx+8], 43463357h
0x180003262  jmp     short loc_180003284
0x180003264  xor     r9d, r9d; int
0x180003267  mov     r8d, r15d; int
0x18000326a  mov     rdx, rdi; struct IHttpContext *
0x18000326d  mov     rcx, rax; this
0x180003270  call    ??0W3_FILTER_CONTEXT@@QEAA@PEAVIHttpContext@@HH@Z; W3_FILTER_CONTEXT::W3_FILTER_CONTEXT(IHttpContext *,int,int)
0x180003275  mov     r14, rax
0x180003278  test    rax, rax
0x18000327b  jz      loc_18000344E
0x180003281  mov     rbx, rax
0x180003284  lock inc dword ptr [rsi+0Ch]
0x180003288  mov     [rbx+70h], rsi
0x18000328c  mov     rcx, rdi
0x18000328f  mov     rax, [rdi]
0x180003292  mov     rax, [rax+38h]
0x180003296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329b  mov     r8, cs:?g_pFilterModuleContext@@3PEAXEA; void * g_pFilterModuleContext
0x1800032a2  mov     r9, rax
0x1800032a5  mov     rdx, rbx
0x1800032a8  mov     rcx, [rax]
0x1800032ab  mov     rax, [rcx+8]
0x1800032af  mov     rcx, r9
0x1800032b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b7  mov     r15d, eax
0x1800032ba  test    eax, eax
0x1800032bc  js      loc_180003735
0x1800032c2  cmp     dword ptr [rbx+100h], 0
0x1800032c9  jnz     loc_18000374F
0x1800032cf  mov     rax, [rbx+70h]
0x1800032d3  test    rax, rax
0x1800032d6  jz      loc_18000374F
0x1800032dc  cmp     dword ptr [rax+10h], 0
0x1800032e0  jz      loc_180003748
0x1800032e6  cmp     dword ptr [rbx+3Ch], 0
0x1800032ea  jnz     loc_180003422
0x1800032f0  mov     eax, [rax+48h]
0x1800032f3  and     eax, 400h
0x1800032f8  lea     rsi, [rbx+3Ch]
0x1800032fc  test    eax, eax
0x1800032fe  jnz     loc_1800033D4
0x180003304  mov     r14, rsi
0x180003307  test    r12d, r12d
0x18000330a  jz      loc_18000377A
0x180003310  mov     r14, rsi
0x180003313  cmp     dword ptr [rbx+100h], 0
0x18000331a  jnz     loc_180003799
0x180003320  mov     rax, [rbx+70h]
0x180003324  test    rax, rax
0x180003327  jz      loc_18000379C
0x18000332d  cmp     dword ptr [rax+10h], 0
0x180003331  jz      loc_180003790
0x180003337  cmp     dword ptr [rbx+3Ch], 0
0x18000333b  jnz     loc_18000342D
0x180003341  mov     eax, [rax+48h]
0x180003344  and     eax, 4000h
0x180003349  xor     edi, edi
0x18000334b  test    eax, eax
0x18000334d  jz      short loc_1800033A5
0x18000334f  lea     rax, ?GetFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADPEAXPEAK@Z; W3_FILTER_CONTEXT::GetFilterHeader(_HTTP_FILTER_CONTEXT *,char *,void *,ulong *)
0x180003356  mov     [rsp+220h+var_1B0], 0
0x18000335f  mov     [rsp+220h+var_1C8], rax
0x180003364  lea     r9, [rsp+220h+var_1DC]; int *
0x180003369  lea     rax, ?SetFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z; W3_FILTER_CONTEXT::SetFilterHeader(_HTTP_FILTER_CONTEXT *,char *,char *)
0x180003370  mov     edx, 4000h; unsigned int
0x180003375  mov     [rsp+220h+var_1C0], rax
0x18000337a  lea     r8, [rsp+220h+var_1C8]; void *
0x18000337f  lea     rax, ?AddFilterHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEAD1@Z; W3_FILTER_CONTEXT::AddFilterHeader(_HTTP_FILTER_CONTEXT *,char *,char *)
0x180003386  mov     rcx, rbx; this
0x180003389  mov     [rsp+220h+var_1B8], rax
0x18000338e  call    ?NotifyFilters@W3_FILTER_CONTEXT@@QEAAJKPEAXPEAH@Z; W3_FILTER_CONTEXT::NotifyFilters(ulong,void *,int *)
0x180003393  mov     r15d, eax
0x180003396  test    eax, eax
0x180003398  js      loc_1800037B7
0x18000339e  cmp     [rsp+220h+var_1DC], 0
0x1800033a3  jnz     short loc_1800033FF
0x1800033a5  lea     rcx, [rbp+120h+var_190]
0x1800033a9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800033af  xor     eax, eax
0x1800033b1  mov     rcx, [rbp+120h+var_50]
0x1800033b8  xor     rcx, rsp; StackCookie
0x1800033bb  call    __security_check_cookie
0x1800033c0  add     rsp, 1E8h
0x1800033c7  pop     r15
0x1800033c9  pop     r14
0x1800033cb  pop     r13
0x1800033cd  pop     r12
0x1800033cf  pop     rdi
0x1800033d0  pop     rsi
0x1800033d1  pop     rbx
0x1800033d2  pop     rbp
0x1800033d3  retn
0x1800033d4  mov     rax, [rdi]
0x1800033d7  lea     r8, a1; "1"
0x1800033de  lea     rdx, aEditingRespons; "EDITING_RESPONSE_ENTITY"
0x1800033e5  mov     rcx, rdi
0x1800033e8  mov     rax, [rax+88h]
0x1800033ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f4  mov     r15d, eax
0x1800033f7  test    eax, eax
0x1800033f9  jns     loc_180003771
0x1800033ff  mov     rdx, [r13+0]
0x180003403  mov     rcx, r13
0x180003406  mov     rax, [rdx]
0x180003409  mov     edx, r15d
0x18000340c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003411  lea     rcx, [rbp+120h+var_190]
0x180003415  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000341b  mov     eax, 1
0x180003420  jmp     short loc_1800033B1
0x180003422  mov     eax, [rax+80h]
0x180003428  jmp     loc_1800032F3
0x18000342d  mov     eax, [rax+80h]
0x180003433  jmp     loc_180003344
0x180003438  mov     rcx, cs:?sm_pachFilterContexts@W3_FILTER_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * W3_FILTER_CONTEXT::sm_pachFilterContexts
0x18000343f  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180003445  test    rax, rax
0x180003448  jnz     loc_180003264
0x18000344e  mov     r15d, 80070008h
0x180003454  jmp     short loc_1800033FF
0x180003456  xor     edx, edx; Val
0x180003458  lea     rcx, [rbp+120h+var_D0]; void *
0x18000345c  mov     r8d, 80h; Size
0x180003462  call    memset_0
0x180003467  mov     r8d, 40h ; '@'
0x18000346d  lea     rdx, [rbp+120h+var_D0]
0x180003471  lea     rcx, [rsp+220h+var_1C8]
0x180003476  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000347c  mov     ecx, 0C0h; Size
0x180003481  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003486  test    rax, rax
0x180003489  jz      loc_1800036E6
0x18000348f  mov     rcx, rax; this
0x180003492  call    ??0FILTER_LIST@@QEAA@XZ; FILTER_LIST::FILTER_LIST(void)
0x180003497  mov     rsi, rax
0x18000349a  test    rax, rax
0x18000349d  jz      loc_1800036E6
0x1800034a3  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x1800034aa  lea     rcx, [rsp+220h+var_1C8]
0x1800034af  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800034b5  mov     r15d, eax
0x1800034b8  test    eax, eax
0x1800034ba  js      loc_180003645
0x1800034c0  mov     rax, [rbx]
0x1800034c3  mov     rcx, rbx
0x1800034c6  mov     rax, [rax+8]
0x1800034ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034cf  mov     rdx, rax
0x1800034d2  lea     rcx, [rsp+220h+var_1C8]
0x1800034d7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800034dd  mov     r15d, eax
0x1800034e0  test    eax, eax
0x1800034e2  js      loc_180003645
0x1800034e8  lea     rcx, [rsp+220h+var_1C8]
  ... truncated ...
```
