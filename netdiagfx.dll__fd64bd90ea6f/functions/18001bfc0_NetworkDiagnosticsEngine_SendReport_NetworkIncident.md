# NetworkDiagnosticsEngine::SendReport(NetworkIncident *)

- ea: `0x18001bfc0`
- end: `0x18001c715`
- name: `?SendReport@NetworkDiagnosticsEngine@@QEAAXPEAVNetworkIncident@@@Z`
- size: `1877`
- prototype: `void __fastcall(NetworkDiagnosticsEngine *__hidden this, struct NetworkIncident *)`
- caller_count: `4`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180004940`
- `0x180018ae4`
- `0x18001bb00`
- `0x18001cc54`

## callees

- `0x180001ff4`
- `0x1800035a8`
- `0x18000579c`
- `0x180006d58`
- `0x180006f04`
- `0x180007f1c`
- `0x18000844c`
- `0x180008db8`
- `0x180010214`
- `0x1800137f0`
- `0x18001bfc0`
- `0x18001ec48`
- `0x1800237a4`
- `0x180023880`
- `0x180026a6c`
- `0x18002762c`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c67c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c67c`
- `KERNEL32!DeleteFileW` at `0x18001c65d`
- `KERNEL32!DeleteFileW` at `0x18001c65d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c66b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c2f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c5c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c66b`

## pseudocode

```c
void __fastcall NetworkDiagnosticsEngine::SendReport(NetworkDiagnosticsEngine *this, struct NetworkIncident *a2)
{
  struct NetworkIncident *v2; // r12
  NetworkDiagnosticsEngine *v3; // rbx
  struct NetworkIncident *v4; // r13
  WERReport *v5; // rax
  WERReport *v6; // r14
  int TraceFilePath; // r15d
  __int64 v8; // rcx
  const WCHAR *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  void *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  ProblemInstance **v15; // r12
  ProblemInstance *v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // ebx
  int v19; // eax
  unsigned __int64 v20; // rdx
  unsigned int **v21; // r12
  unsigned int *v22; // rbx
  __int64 v23; // r12
  struct NetworkIncident *v24; // rcx
  _QWORD *v25; // rbx
  int v26; // edi
  __int64 v27; // rcx
  __int64 v28; // rdx
  unsigned int *v29; // r12
  __int64 v30; // rcx
  void *v31; // rbx
  __int64 v32; // rcx
  NetworkDiagnosticsEngine *v33; // rbx
  unsigned int v34; // [rsp+30h] [rbp-128h] BYREF
  unsigned int v35[2]; // [rsp+38h] [rbp-120h] BYREF
  __int64 v36; // [rsp+40h] [rbp-118h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-110h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-108h] BYREF
  NetworkDiagnosticsEngine *v39; // [rsp+58h] [rbp-100h]
  struct NetworkIncident *v40; // [rsp+60h] [rbp-F8h]
  unsigned int **v41; // [rsp+68h] [rbp-F0h] BYREF
  int v42; // [rsp+70h] [rbp-E8h]
  NetworkDiagnosticsEngine *v43; // [rsp+78h] [rbp-E0h]
  NetworkDiagnosticsEngine *v44; // [rsp+80h] [rbp-D8h]
  unsigned int v45; // [rsp+88h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+90h] [rbp-C8h] BYREF
  unsigned __int16 v47[64]; // [rsp+A0h] [rbp-B8h] BYREF

  v2 = a2;
  v3 = this;
  v43 = this;
  v39 = this;
  v44 = this;
  v4 = a2;
  v40 = a2;
  if ( !a2 )
    return;
  if ( !*((_DWORD *)a2 + 6) )
    return;
  v5 = (WERReport *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  v41 = (unsigned int **)v5;
  if ( !v5 )
    return;
  *(_QWORD *)v5 = &WERReport::`vftable';
  *((_QWORD *)v5 + 1) = 0;
  v41 = (unsigned int **)v5;
  *(_QWORD *)v35 = 0;
  pv = 0;
  TraceFilePath = -2147467259;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v42 = 0;
    v46 = 0;
    v8 = *((_QWORD *)v4 + 10);
    if ( v8 )
      TraceFilePath = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 72LL))(v8, &v46);
    if ( TraceFilePath < 0 )
    {
      v9 = lpFileName;
    }
    else
    {
      TraceFilePath = CTraceController::GenerateTraceFilePath((_DWORD *)v2 + 32, (__int64)L"WER", (__int64)&lpFileName);
      v9 = lpFileName;
      if ( TraceFilePath >= 0 )
      {
        TraceFilePath = CTraceController::CopyTraceFile((struct NetworkIncident *)((char *)v2 + 128), lpFileName);
        if ( TraceFilePath >= 0 )
        {
          v42 = 1;
          goto LABEL_90;
        }
      }
      v3 = v43;
    }
    if ( *(_QWORD *)v3 )
    {
      memset_0(v47, 0, sizeof(v47));
      StringCchPrintfW(
        v47,
        0x40u,
        L"Failed to get session trace file, will attach global etl file to WER. HRESULT=0x%x",
        (unsigned int)TraceFilePath);
      (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)v3 + 96LL))(*(_QWORD *)v3, 6, v47);
      TraceFilePath = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 24LL))(*(_QWORD *)v3);
      if ( TraceFilePath >= 0 )
      {
        v10 = *(_QWORD *)v3 + 16LL;
        if ( *(_QWORD *)v3 == -16 )
        {
          v11 = 0;
        }
        else
        {
          v11 = -1;
          do
            ++v11;
          while ( *(_WORD *)(v10 + 2 * v11) );
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpFileName, v10, v11);
        v9 = lpFileName;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v45) )
    {
      v34 = v45;
      TraceFilePath = v45;
      v6 = (WERReport *)v41;
      v12 = pv;
      *(_QWORD *)v35 = pv;
      v9 = lpFileName;
      v4 = v40;
      v43 = v39;
      v2 = v40;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001C19C);
      goto LABEL_21;
    }
  }
LABEL_90:
  v12 = 0;
LABEL_21:
  if ( TraceFilePath < 0 )
    goto LABEL_76;
  v13 = *((_QWORD *)v4 + 4);
  v14 = *((_QWORD *)v4 + 5) - v13;
  if ( v14 )
  {
    if ( !(v14 >> 3) )
      goto LABEL_76;
    v19 = 0;
    LODWORD(v39) = 0;
    v20 = 0;
    while ( 1 )
    {
      v21 = *(unsigned int ***)(v13 + 8 * v20);
      v41 = v21;
      if ( v21 )
      {
        v22 = *v21;
        if ( *v21 )
        {
          v40 = 0;
          if ( *((_WORD *)v4 + 46) )
          {
            v34 = 0;
            std::list<ProblemNode *>::list<ProblemNode *>(&v46);
            std::list<ProblemNode *>::_Insert<ProblemNode * const &>(&v46, v46, &v41);
            while ( *((_QWORD *)&v46 + 1) )
            {
              v23 = *(_QWORD *)(*(_QWORD *)v46 + 16LL);
              std::list<ProblemNode *>::pop_front(&v46);
              if ( v23 )
              {
                v22 = *(unsigned int **)v23;
                v24 = v40;
                if ( *(_QWORD *)(*(_QWORD *)v23 + 248LL) )
                  v24 = *(struct NetworkIncident **)(*(_QWORD *)v23 + 248LL);
                v40 = v24;
                if ( v22[61] )
                {
                  v34 = v22[61];
                  if ( v22 )
                  {
                    v21 = v41;
                    goto LABEL_56;
                  }
                  break;
                }
                v25 = **(_QWORD ***)(v23 + 64);
                v26 = (int)v39;
                while ( v25 != *(_QWORD **)(v23 + 64) )
                {
                  v27 = v25[2];
                  v25 = (_QWORD *)*v25;
                  v36 = v27;
                  if ( v27 && (*(_DWORD *)(v27 + 96) != 7 || *(_DWORD *)(v27 + 36) != v26) )
                    std::list<ProblemNode *>::_Insert<ProblemNode * const &>(&v46, v46, &v36);
                }
                *(_DWORD *)(v23 + 96) = 7;
                *(_DWORD *)(v23 + 36) = v26;
                v9 = lpFileName;
              }
            }
            v21 = v41;
            v22 = *v41;
LABEL_56:
            std::list<ProblemNode *>::~list<ProblemNode *>((void **)&v46);
            if ( v40 && (*((_DWORD *)v40 + 10) & 0x200000) != 0 )
              goto LABEL_75;
          }
          else
          {
            v34 = v22[60];
          }
          TraceFilePath = (**(__int64 (__fastcall ***)(WERReport *, const wchar_t *, _QWORD))v6)(
                            v6,
                            L"NetworkDiagnosticsFrameworkV3",
                            0);
          if ( TraceFilePath < 0 )
            goto LABEL_75;
          v36 = *((_QWORD *)v44 + 5) + 8LL;
          v28 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                             v36,
                             v22);
          if ( !v28 )
            v28 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                               v36 + 16,
                               v22);
          if ( !v28 )
            goto LABEL_75;
          TraceFilePath = (*(__int64 (__fastcall **)(WERReport *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( TraceFilePath < 0 )
            goto LABEL_75;
          ProblemInstance::GetWerAttributes((ProblemInstance *)v22, v35, (unsigned __int16 **)&pv);
          v29 = *v21;
          v36 = *((_QWORD *)v44 + 5) + 8LL;
          v30 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                             v36,
                             v29);
          if ( !v30 )
            v30 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                               v36 + 16,
                               v29);
          if ( !v30
            || (TraceFilePath = (*(__int64 (__fastcall **)(WERReport *, _QWORD, _QWORD, struct NetworkIncident *, unsigned int *))(*(_QWORD *)v6 + 16LL))(
                                  v6,
                                  *((unsigned __int16 *)v4 + 46),
                                  v34,
                                  v40,
                                  v22),
                TraceFilePath < 0) )
          {
            v12 = pv;
            goto LABEL_76;
          }
          v31 = pv;
          if ( pv )
            (*(void (__fastcall **)(WERReport *, LPVOID, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, pv, 0);
          CoTaskMemFree(v31);
          v12 = 0;
          *(_QWORD *)v35 = 0;
          pv = 0;
          (*(void (__fastcall **)(WERReport *, const WCHAR *, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, v9, 0);
          TraceFilePath = WERReport::Submit(v6);
          if ( TraceFilePath < 0 )
            goto LABEL_76;
          v19 = (int)v39;
        }
        else
        {
          v12 = *(void **)v35;
        }
      }
      LODWORD(v39) = v19 + 1;
      v13 = *((_QWORD *)v4 + 4);
      v20 = (unsigned int)(v19 + 1);
      if ( v20 >= (*((_QWORD *)v4 + 5) - v13) >> 3 )
        goto LABEL_76;
      v19 = (int)v39;
    }
  }
  v15 = *(ProblemInstance ***)v2;
  if ( v15 )
  {
    if ( *v15 )
    {
      TraceFilePath = (**(__int64 (__fastcall ***)(WERReport *, const wchar_t *, _QWORD))v6)(
                        v6,
                        L"NetworkDiagnosticsFrameworkV3",
                        0);
      if ( TraceFilePath >= 0 )
      {
        v16 = *v15;
        v36 = *((_QWORD *)v44 + 5) + 8LL;
        v17 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                           v36,
                           v16);
        if ( !v17 )
          v17 = *(_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperInfo *>::operator[](
                             v36 + 16,
                             v16);
        if ( v17
          && (TraceFilePath = (*(__int64 (__fastcall **)(WERReport *))(*(_QWORD *)v6 + 8LL))(v6), TraceFilePath >= 0) )
        {
          v18 = *(_DWORD *)((char *)*v15 + (*((_WORD *)v4 + 46) != 0 ? 4 : 0) + 240);
          ProblemInstance::GetWerAttributes(*v15, &v34, (unsigned __int16 **)&pv);
          TraceFilePath = (*(__int64 (__fastcall **)(WERReport *, _QWORD, _QWORD, _QWORD, ProblemInstance *))(*(_QWORD *)v6 + 16LL))(
                            v6,
                            *((unsigned __int16 *)v4 + 46),
                            v18,
                            0,
                            *v15);
          v12 = pv;
          if ( TraceFilePath >= 0 )
          {
            if ( pv )
              (*(void (__fastcall **)(WERReport *, LPVOID, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, pv, 0);
            CoTaskMemFree(v12);
            v12 = 0;
            (*(void (__fastcall **)(WERReport *, const WCHAR *, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, v9, 0);
            TraceFilePath = WERReport::Submit(v6);
          }
        }
        else
        {
LABEL_75:
          v12 = *(void **)v35;
        }
      }
    }
  }
LABEL_76:
  v32 = *((_QWORD *)v4 + 15);
  if ( v32 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 128LL))(v32, 1);
  if ( v42 )
    DeleteFileW(v9);
  if ( v12 )
    CoTaskMemFree(v12);
  WERReport::~WERReport(v6);
  operator delete(v6);
  if ( TraceFilePath < 0 )
  {
    v33 = v43;
    if ( *(_QWORD *)v43 )
    {
      memset_0(v47, 0, sizeof(v47));
      StringCchPrintfW(v47, 0x40u, L"Could not submit WER report. HRESULT=0x%x", (unsigned int)TraceFilePath);
      (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 *))(**(_QWORD **)v33 + 96LL))(*(_QWORD *)v33, 6, v47);
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
}

```

## disassembly

```asm
0x18001bfc0  mov     [rsp+arg_10], rbx
0x18001bfc5  mov     [rsp+arg_18], rsi
0x18001bfca  push    rdi
0x18001bfcb  push    r12
0x18001bfcd  push    r13
0x18001bfcf  push    r14
0x18001bfd1  push    r15
0x18001bfd3  sub     rsp, 130h
0x18001bfda  mov     rax, cs:__security_cookie
0x18001bfe1  xor     rax, rsp
0x18001bfe4  mov     [rsp+158h+var_38], rax
0x18001bfec  mov     r12, rdx
0x18001bfef  mov     rbx, rcx
0x18001bff2  mov     [rsp+158h+var_E0], rcx
0x18001bff7  mov     [rsp+158h+var_100], rcx
0x18001bffc  mov     [rsp+158h+var_D8], rcx
0x18001c004  mov     r13, rdx
0x18001c007  mov     [rsp+158h+var_F8], rdx
0x18001c00c  xor     esi, esi
0x18001c00e  test    rdx, rdx
0x18001c011  jz      loc_18001C6E8
0x18001c017  cmp     [rdx+18h], esi
0x18001c01a  jz      loc_18001C6E8
0x18001c020  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c027  lea     ecx, [rsi+10h]; unsigned __int64
0x18001c02a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c02f  mov     r14, rax
0x18001c032  mov     [rsp+158h+var_F0], rax
0x18001c037  test    rax, rax
0x18001c03a  jz      loc_18001C6E8
0x18001c040  lea     rax, ??_7WERReport@@6B@; const WERReport::`vftable'
0x18001c047  mov     [r14], rax
0x18001c04a  mov     [r14+8], rsi
0x18001c04e  mov     [rsp+158h+var_F0], r14
0x18001c053  mov     eax, esi
0x18001c055  mov     qword ptr [rsp+158h+var_120], rax
0x18001c05a  mov     [rsp+158h+pv], rax
0x18001c05f  test    r14, r14
0x18001c062  jz      loc_18001C6E8
0x18001c068  mov     r15d, 80004005h
0x18001c06e  lea     rcx, [rsp+158h+lpFileName]
0x18001c073  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001c078  nop
0x18001c079  mov     [rsp+158h+var_E8], esi
0x18001c07d  xorps   xmm0, xmm0
0x18001c080  movups  [rsp+158h+var_C8], xmm0
0x18001c088  mov     rcx, [r13+50h]
0x18001c08c  test    rcx, rcx
0x18001c08f  jz      short loc_18001C0A8
0x18001c091  mov     rax, [rcx]
0x18001c094  lea     rdx, [rsp+158h+var_C8]
0x18001c09c  mov     rax, [rax+48h]
0x18001c0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c0a5  mov     r15d, eax
0x18001c0a8  test    r15d, r15d
0x18001c0ab  js      short loc_18001C0F4
0x18001c0ad  lea     rbx, [r12+80h]
0x18001c0b5  lea     r8, [rsp+158h+lpFileName]
0x18001c0ba  lea     rdx, aWer; "WER"
0x18001c0c1  mov     rcx, rbx
0x18001c0c4  call    ?GenerateTraceFilePath@CTraceController@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CTraceController::GenerateTraceFilePath(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001c0c9  mov     r15d, eax
0x18001c0cc  mov     rdi, [rsp+158h+lpFileName]
0x18001c0d1  test    eax, eax
0x18001c0d3  js      short loc_18001C0FB
0x18001c0d5  mov     rdx, rdi; lpNewFileName
0x18001c0d8  mov     rcx, rbx; this
0x18001c0db  call    ?CopyTraceFile@CTraceController@@QEAAJPEBG@Z; CTraceController::CopyTraceFile(ushort const *)
0x18001c0e0  mov     r15d, eax
0x18001c0e3  test    eax, eax
0x18001c0e5  js      short loc_18001C0FB
0x18001c0e7  mov     [rsp+158h+var_E8], 1
0x18001c0ef  jmp     loc_18001C197
0x18001c0f4  mov     rdi, [rsp+158h+lpFileName]
0x18001c0f9  jmp     short loc_18001C100
0x18001c0fb  mov     rbx, [rsp+158h+var_E0]
0x18001c100  cmp     [rbx], rsi
0x18001c103  jz      loc_18001C197
0x18001c109  xor     edx, edx; Val
0x18001c10b  mov     r8d, 80h; Size
0x18001c111  lea     rcx, [rsp+158h+var_B8]; void *
0x18001c119  call    memset_0
0x18001c11e  mov     r9d, r15d
0x18001c121  lea     r8, aFailedToGetSes; "Failed to get session trace file, will "...
0x18001c128  mov     edx, 40h ; '@'; unsigned __int64
0x18001c12d  lea     rcx, [rsp+158h+var_B8]; unsigned __int16 *
0x18001c135  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c13a  mov     rcx, [rbx]
0x18001c13d  mov     rax, [rcx]
0x18001c140  lea     r8, [rsp+158h+var_B8]
0x18001c148  mov     edx, 6
0x18001c14d  mov     rax, [rax+60h]
0x18001c151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c156  mov     rcx, [rbx]
0x18001c159  mov     rax, [rcx]
0x18001c15c  mov     rax, [rax+18h]
0x18001c160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c165  mov     r15d, eax
0x18001c168  test    eax, eax
0x18001c16a  js      short loc_18001C197
0x18001c16c  mov     rdx, [rbx]
0x18001c16f  add     rdx, 10h
0x18001c173  jnz     short loc_18001C17A
0x18001c175  mov     r8d, esi
0x18001c178  jmp     short loc_18001C188
0x18001c17a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c17e  inc     r8
0x18001c181  cmp     [rdx+r8*2], si
0x18001c186  jnz     short loc_18001C17E
0x18001c188  lea     rcx, [rsp+158h+lpFileName]
0x18001c18d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001c192  mov     rdi, [rsp+158h+lpFileName]
0x18001c197  mov     rbx, rsi
0x18001c19a  jmp     short loc_18001C1C9
0x18001c19c  xor     esi, esi
0x18001c19e  mov     r15d, [rsp+158h+var_128]
0x18001c1a3  mov     r14, [rsp+158h+var_F0]
0x18001c1a8  mov     rbx, [rsp+158h+pv]
0x18001c1ad  mov     qword ptr [rsp+158h+var_120], rbx
0x18001c1b2  mov     rdi, [rsp+158h+lpFileName]
0x18001c1b7  mov     r13, [rsp+158h+var_F8]
0x18001c1bc  mov     rax, [rsp+158h+var_100]
0x18001c1c1  mov     [rsp+158h+var_E0], rax
0x18001c1c6  mov     r12, r13
0x18001c1c9  test    r15d, r15d
0x18001c1cc  js      loc_18001C637
0x18001c1d2  mov     rcx, [r13+20h]
0x18001c1d6  mov     rax, [r13+28h]
0x18001c1da  sub     rax, rcx
0x18001c1dd  jnz     loc_18001C326
0x18001c1e3  mov     r12, [r12]
0x18001c1e7  test    r12, r12
0x18001c1ea  jz      loc_18001C637
0x18001c1f0  cmp     [r12], rsi
0x18001c1f4  jz      loc_18001C637
0x18001c1fa  mov     rax, [r14]
0x18001c1fd  xor     r8d, r8d
0x18001c200  lea     rdx, aNetworkdiagnos_0; "NetworkDiagnosticsFrameworkV3"
0x18001c207  mov     rcx, r14
0x18001c20a  mov     rax, [rax]
0x18001c20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c212  mov     r15d, eax
0x18001c215  test    eax, eax
0x18001c217  js      loc_18001C637
0x18001c21d  mov     rbx, [r12]
0x18001c221  mov     rax, [rsp+158h+var_D8]
0x18001c229  mov     rax, [rax+28h]
0x18001c22d  add     rax, 8
0x18001c231  mov     [rsp+158h+var_118], rax
0x18001c236  mov     rdx, rbx
0x18001c239  mov     rcx, rax
0x18001c23c  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@QEAAAEAPEAVCHelperInfo@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001c241  mov     rdx, [rax]
0x18001c244  test    rdx, rdx
0x18001c247  jnz     short loc_18001C25D
0x18001c249  mov     rcx, [rsp+158h+var_118]
0x18001c24e  add     rcx, 10h
0x18001c252  mov     rdx, rbx
0x18001c255  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperInfo@@@std@@@5@@std@@QEAAAEAPEAVCHelperInfo@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperInfo *>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001c25a  mov     rdx, [rax]
0x18001c25d  test    rdx, rdx
0x18001c260  jz      loc_18001C632
0x18001c266  mov     rax, [r14]
0x18001c269  mov     rcx, r14
0x18001c26c  mov     rax, [rax+8]
0x18001c270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c275  mov     r15d, eax
0x18001c278  test    eax, eax
0x18001c27a  js      loc_18001C632
0x18001c280  mov     rcx, [r12]; this
0x18001c284  movzx   eax, word ptr [r13+5Ch]
0x18001c289  neg     ax
0x18001c28c  sbb     rdx, rdx
0x18001c28f  and     edx, 4
0x18001c292  mov     ebx, [rdx+rcx+0F0h]
0x18001c299  lea     r8, [rsp+158h+pv]; unsigned __int16 **
0x18001c29e  lea     rdx, [rsp+158h+var_128]; unsigned int *
0x18001c2a3  call    ?GetWerAttributes@ProblemInstance@@QEAAJPEAIPEAPEAG@Z; ProblemInstance::GetWerAttributes(uint *,ushort * *)
0x18001c2a8  mov     rax, [r14]
0x18001c2ab  movzx   edx, word ptr [r13+5Ch]
0x18001c2b0  mov     rcx, [r12]
0x18001c2b4  mov     [rsp+158h+var_138], rcx
0x18001c2b9  xor     r9d, r9d
0x18001c2bc  mov     r8d, ebx
0x18001c2bf  mov     rcx, r14
0x18001c2c2  mov     rax, [rax+10h]
0x18001c2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2cb  mov     r15d, eax
0x18001c2ce  mov     rbx, [rsp+158h+pv]
0x18001c2d3  test    eax, eax
0x18001c2d5  js      loc_18001C637
0x18001c2db  test    rbx, rbx
0x18001c2de  jz      short loc_18001C2F5
0x18001c2e0  mov     rax, [r14]
0x18001c2e3  xor     r8d, r8d
0x18001c2e6  mov     rdx, rbx
0x18001c2e9  mov     rcx, r14
0x18001c2ec  mov     rax, [rax+18h]
0x18001c2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2f5  mov     rcx, rbx; pv
0x18001c2f8  call    cs:__imp_CoTaskMemFree
0x18001c2fe  mov     rbx, rsi
0x18001c301  mov     rax, [r14]
0x18001c304  xor     r8d, r8d
0x18001c307  mov     rdx, rdi
0x18001c30a  mov     rcx, r14
0x18001c30d  mov     rax, [rax+18h]
0x18001c311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c316  mov     rcx, r14; this
0x18001c319  call    ?Submit@WERReport@@QEAAJXZ; WERReport::Submit(void)
0x18001c31e  mov     r15d, eax
0x18001c321  jmp     loc_18001C637
0x18001c326  sar     rax, 3
0x18001c32a  test    rax, rax
0x18001c32d  jz      loc_18001C637
0x18001c333  mov     eax, esi
0x18001c335  mov     dword ptr [rsp+158h+var_100], eax
0x18001c339  mov     rdx, rsi
0x18001c33c  mov     r12, [rcx+rdx*8]
0x18001c340  mov     [rsp+158h+var_F0], r12
0x18001c345  test    r12, r12
0x18001c348  jz      loc_18001C5FF
0x18001c34e  mov     rbx, [r12]
0x18001c352  test    rbx, rbx
0x18001c355  jz      loc_18001C624
0x18001c35b  mov     [rsp+158h+var_F8], rsi
0x18001c360  cmp     [r13+5Ch], si
0x18001c365  jnz     short loc_18001C376
0x18001c367  mov     eax, [rbx+0F0h]
0x18001c36d  mov     [rsp+158h+var_128], eax
0x18001c371  jmp     loc_18001C497
0x18001c376  mov     [rsp+158h+var_128], esi
0x18001c37a  lea     rcx, [rsp+158h+var_C8]
0x18001c382  call    ??0?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::list<ProblemNode *>(void)
0x18001c387  nop
0x18001c388  lea     r8, [rsp+158h+var_F0]
0x18001c38d  mov     rdx, qword ptr [rsp+158h+var_C8]
0x18001c395  lea     rcx, [rsp+158h+var_C8]
0x18001c39d  call    ??$_Insert@AEBQEAVProblemNode@@@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVProblemNode@@@std@@@std@@U_Iterator_base0@2@@1@AEBQEAVProblemNode@@@Z; std::list<ProblemNode *>::_Insert<ProblemNode * const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProblemNode *>>,std::_Iterator_base0>,ProblemNode * const &)
0x18001c3a2  cmp     qword ptr [rsp+158h+var_C8+8], rsi
0x18001c3aa  jz      loc_18001C46A
0x18001c3b0  mov     rax, qword ptr [rsp+158h+var_C8]
0x18001c3b8  mov     rcx, [rax]
0x18001c3bb  mov     r12, [rcx+10h]
0x18001c3bf  lea     rcx, [rsp+158h+var_C8]
0x18001c3c7  call    ?pop_front@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::pop_front(void)
0x18001c3cc  test    r12, r12
0x18001c3cf  jz      short loc_18001C3A2
0x18001c3d1  mov     rbx, [r12]
0x18001c3d5  mov     rax, [rbx+0F8h]
0x18001c3dc  mov     rcx, [rsp+158h+var_F8]
0x18001c3e1  test    rax, rax
0x18001c3e4  cmovnz  rcx, rax
0x18001c3e8  mov     [rsp+158h+var_F8], rcx
0x18001c3ed  mov     eax, [rbx+0F4h]
0x18001c3f3  test    eax, eax
0x18001c3f5  jnz     short loc_18001C45A
0x18001c3f7  mov     rbx, [r12+40h]
0x18001c3fc  mov     rbx, [rbx]
0x18001c3ff  mov     edi, dword ptr [rsp+158h+var_100]
0x18001c403  cmp     rbx, [r12+40h]
0x18001c408  jz      short loc_18001C442
0x18001c40a  mov     rcx, [rbx+10h]
0x18001c40e  mov     rbx, [rbx]
0x18001c411  mov     [rsp+158h+var_118], rcx
0x18001c416  test    rcx, rcx
0x18001c419  jz      short loc_18001C403
0x18001c41b  cmp     dword ptr [rcx+60h], 7
0x18001c41f  jnz     short loc_18001C426
0x18001c421  cmp     [rcx+24h], edi
0x18001c424  jz      short loc_18001C403
0x18001c426  lea     r8, [rsp+158h+var_118]
0x18001c42b  mov     rdx, qword ptr [rsp+158h+var_C8]
0x18001c433  lea     rcx, [rsp+158h+var_C8]
0x18001c43b  call    ??$_Insert@AEBQEAVProblemNode@@@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVProblemNode@@@std@@@std@@U_Iterator_base0@2@@1@AEBQEAVProblemNode@@@Z; std::list<ProblemNode *>::_Insert<ProblemNode * const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProblemNode *>>,std::_Iterator_base0>,ProblemNode * const &)
0x18001c440  jmp     short loc_18001C403
0x18001c442  mov     dword ptr [r12+60h], 7
0x18001c44b  mov     [r12+24h], edi
0x18001c450  mov     rdi, [rsp+158h+lpFileName]
0x18001c455  jmp     loc_18001C3A2
0x18001c45a  mov     [rsp+158h+var_128], eax
0x18001c45e  test    rbx, rbx
0x18001c461  jz      short loc_18001C46A
0x18001c463  mov     r12, [rsp+158h+var_F0]
0x18001c468  jmp     short loc_18001C473
0x18001c46a  mov     r12, [rsp+158h+var_F0]
0x18001c46f  mov     rbx, [r12]
0x18001c473  lea     rcx, [rsp+158h+var_C8]
0x18001c47b  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x18001c480  mov     rax, [rsp+158h+var_F8]
0x18001c485  test    rax, rax
0x18001c488  jz      short loc_18001C497
0x18001c48a  test    dword ptr [rax+28h], 200000h
0x18001c491  jnz     loc_18001C632
0x18001c497  mov     rax, [r14]
0x18001c49a  xor     r8d, r8d
0x18001c49d  lea     rdx, aNetworkdiagnos_0; "NetworkDiagnosticsFrameworkV3"
0x18001c4a4  mov     rcx, r14
0x18001c4a7  mov     rax, [rax]
0x18001c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
