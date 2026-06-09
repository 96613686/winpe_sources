# CFilterGraph::~CFilterGraph(void)

- ea: `0x180002710`
- end: `0x180002c77`
- name: `??1CFilterGraph@@EEAA@XZ`
- size: `1383`
- prototype: `void __fastcall(CFilterGraph *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180060480`

## callees

- `0x180002710`
- `0x180002c80`
- `0x1800032f0`
- `0x180003808`
- `0x180003868`
- `0x180023b40`
- `0x18002e458`
- `0x180038498`
- `0x180060450`
- `0x1800604bc`
- `0x180060514`
- `0x180069b14`
- `0x180069fb4`
- `0x180070eec`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002b03`
- `KERNEL32!DeleteCriticalSection` at `0x180002b03`
- `KERNEL32!DeleteCriticalSection` at `0x180002c6b`
- `KERNEL32!LeaveCriticalSection` at `0x1800029c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800029c2`
- `KERNEL32!EnterCriticalSection` at `0x180002984`
- `KERNEL32!EnterCriticalSection` at `0x180002984`
- `KERNEL32!CloseHandle` at `0x180002b1b`
- `KERNEL32!CloseHandle` at `0x180002bdf`
- `KERNEL32!CloseHandle` at `0x180002b1b`
- `KERNEL32!CloseHandle` at `0x180002bdf`
- `USER32!PostThreadMessageW` at `0x1800029af`
- `USER32!PostThreadMessageW` at `0x1800029e5`
- `USER32!PostThreadMessageW` at `0x1800029af`
- `USER32!PostThreadMessageW` at `0x1800029e5`

## pseudocode

```c
void __fastcall CFilterGraph::~CFilterGraph(CFilterGraph *this)
{
  CWaveOutFilter::CDS3D *v2; // rcx
  CFGControl *v3; // rcx
  CDistributorManager *v4; // rcx
  __int64 v5; // rax
  struct IBaseFilter **v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rdx
  CFilterGraph::ConGen *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  void *v16; // rdi
  void *v17; // rdi
  unsigned int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  CFilterCache *v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rdi
  void *v26; // rcx
  _QWORD *v27; // rdi
  void *v28; // rcx
  void *v29; // rcx
  void *i; // rdi
  _QWORD *v31; // rdi
  void *v32; // rcx
  _QWORD *v33; // rdi
  void *v34; // rcx
  void *v35; // rcx
  unsigned int v36; // edx
  __int64 v37; // rcx
  CServiceProvider::ProviderEntry *v38; // rcx

  *(_QWORD *)this = &CFilterGraph::`vftable'{for `IFilterGraph3'};
  *((_QWORD *)this + 1) = &CFilterGraph::`vftable'{for `IGraphVersion'};
  *((_QWORD *)this + 2) = &CFilterGraph::`vftable'{for `IPersistStream'};
  *((_QWORD *)this + 3) = &CFilterGraph::`vftable'{for `IObjectWithSite'};
  *((_QWORD *)this + 4) = &CFilterGraph::`vftable'{for `IAMMainThread'};
  *((_QWORD *)this + 5) = &CFilterGraph::`vftable'{for `IAMOpenProgress'};
  *((_QWORD *)this + 6) = &CFilterGraph::`vftable'{for `IAMGraphStreams'};
  *((_QWORD *)this + 7) = &CFilterGraph::`vftable'{for `IVideoFrameStep'};
  *((_QWORD *)this + 8) = &CFilterGraph::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 9) = &CFilterGraph::`vftable'{for `IRegisterServiceProvider'};
  *((_QWORD *)this + 16) = &CFilterGraph::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 19) = &CFilterGraph::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 20) = &CFilterGraph::`vftable'{for `IAMovieSetup'};
  v2 = (CWaveOutFilter::CDS3D *)*((_QWORD *)this + 91);
  if ( v2 )
    CWaveOutFilter::CDS3D::`scalar deleting destructor'(v2, 1u);
  v3 = (CFGControl *)*((_QWORD *)this + 31);
  *((_QWORD *)this + 91) = 0;
  if ( v3 )
    CFGControl::Shutdown(v3);
  v4 = (CDistributorManager *)*((_QWORD *)this + 68);
  if ( v4 )
    CDistributorManager::Shutdown(v4);
  CFilterGraph::Stop((CFilterGraph *)((char *)this + 152));
  while ( *((int *)this + 78) > 0 )
  {
    v5 = *((_QWORD *)this + 37);
    if ( v5 )
      v6 = *(struct IBaseFilter ***)(v5 + 16);
    else
      v6 = 0;
    CFilterGraph::RemoveFilterInternal(this, *v6, 0);
  }
  while ( 1 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 43);
    if ( !v7 )
      break;
    v8 = v7[1];
    if ( *v7 )
      *(_QWORD *)(*v7 + 8LL) = v8;
    else
      *((_QWORD *)this + 43) = v8;
    v9 = (_QWORD *)v7[1];
    v10 = *v7;
    if ( v9 )
      *v9 = v10;
    else
      *((_QWORD *)this + 44) = v10;
    v11 = (CFilterGraph::ConGen *)v7[2];
    if ( *((_DWORD *)this + 93) >= *((_DWORD *)this + 92) )
    {
      operator delete(v7);
    }
    else
    {
      v7[1] = *((_QWORD *)this + 47);
      ++*((_DWORD *)this + 93);
      *((_QWORD *)this + 47) = v7;
    }
    --*((_DWORD *)this + 90);
    if ( !v11 )
      break;
    CFilterGraph::ConGen::`scalar deleting destructor'(v11, v10);
  }
  v12 = *((_QWORD *)this + 95);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 95) = 0;
  }
  v13 = *((_QWORD *)this + 96);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 96) = 0;
  }
  v14 = *((_QWORD *)this + 22);
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 22) = 0;
  }
  v15 = *((_QWORD *)this + 54);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = (void *)*((_QWORD *)this + 68);
  if ( v16 )
  {
    CDistributorManager::~CDistributorManager(*((CDistributorManager **)this + 68));
    operator delete(v16);
  }
  v17 = (void *)*((_QWORD *)this + 31);
  if ( v17 )
  {
    CFGControl::~CFGControl(*((CFGControl **)this + 31));
    operator delete(v17);
  }
  EnterCriticalSection(&g_csObjectThread);
  if ( *((_DWORD *)this + 121) == g_dwObjectThreadId && !--g_cFGObjects )
    PostThreadMessageW(g_dwObjectThreadId, 0, 0, 0);
  LeaveCriticalSection(&g_csObjectThread);
  if ( *((_BYTE *)this + 736) )
    PostThreadMessageW(*((_DWORD *)this + 121), 0, 0, 0);
  v19 = *((_QWORD *)this + 79);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = *((_QWORD *)this + 66);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  *((_QWORD *)this + 66) = 0;
  v21 = (CFilterCache *)*((_QWORD *)this + 90);
  *((_QWORD *)this + 85) = &CGraphConfig::`vftable'{for `IGraphConfig'};
  *((_QWORD *)this + 86) = &CGraphConfig::`vftable'{for `CUnknown'};
  if ( v21 )
    CFilterCache::`scalar deleting destructor'(v21, v18);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v22 = *((_QWORD *)this + 84);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = *((_QWORD *)this + 82);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = *((_QWORD *)this + 81);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = (_QWORD *)*((_QWORD *)this + 74);
  while ( v25 )
  {
    v26 = v25;
    v25 = (_QWORD *)v25[1];
    operator delete(v26);
  }
  v27 = (_QWORD *)*((_QWORD *)this + 78);
  *((_DWORD *)this + 152) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 74) = 0;
  while ( v27 )
  {
    v28 = v27;
    v27 = (_QWORD *)v27[1];
    operator delete(v28);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  v29 = (void *)*((_QWORD *)this + 63);
  if ( v29 )
    CloseHandle(v29);
  for ( i = (void *)*((_QWORD *)this + 49); i; i = (void *)*((_QWORD *)this + 49) )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)i + 1) + 16LL))(*((_QWORD *)i + 1));
    DeleteMediaType(*((struct _AMMediaType **)i + 2));
    *((_QWORD *)this + 49) = *(_QWORD *)i;
    operator delete(i);
  }
  v31 = (_QWORD *)*((_QWORD *)this + 43);
  while ( v31 )
  {
    v32 = v31;
    v31 = (_QWORD *)v31[1];
    operator delete(v32);
  }
  v33 = (_QWORD *)*((_QWORD *)this + 47);
  *((_DWORD *)this + 90) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 43) = 0;
  while ( v33 )
  {
    v34 = v33;
    v33 = (_QWORD *)v33[1];
    operator delete(v34);
  }
  CBaseList::~CBaseList((CFilterGraph *)((char *)this + 296));
  v35 = (void *)*((_QWORD *)this + 32);
  if ( v35 )
  {
    CloseHandle(v35);
    *((_QWORD *)this + 32) = 0;
  }
  operator delete(*((void **)this + 27));
  v37 = *((_QWORD *)this + 22);
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    *((_QWORD *)this + 22) = 0;
  }
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v38 = (CServiceProvider::ProviderEntry *)*((_QWORD *)this + 15);
  *((_QWORD *)this + 8) = &CServiceProvider::`vftable'{for `IServiceProvider'};
  for ( *((_QWORD *)this + 9) = &CServiceProvider::`vftable'{for `IRegisterServiceProvider'};
        v38;
        v38 = (CServiceProvider::ProviderEntry *)*((_QWORD *)this + 15) )
  {
    *((_QWORD *)this + 15) = *(_QWORD *)v38;
    CServiceProvider::ProviderEntry::`scalar deleting destructor'(v38, v36);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
}

```

## disassembly

```asm
0x180002710  mov     [rsp+arg_8], rbx
0x180002715  mov     [rsp+arg_10], rsi
0x18000271a  push    rdi
0x18000271b  sub     rsp, 20h
0x18000271f  lea     rax, ??_7CFilterGraph@@6BIFilterGraph3@@@; const CFilterGraph::`vftable'{for `IFilterGraph3'}
0x180002726  mov     rbx, rcx
0x180002729  mov     [rcx], rax
0x18000272c  lea     rax, ??_7CFilterGraph@@6BIGraphVersion@@@; const CFilterGraph::`vftable'{for `IGraphVersion'}
0x180002733  mov     [rcx+8], rax
0x180002737  lea     rax, ??_7CFilterGraph@@6BIPersistStream@@@; const CFilterGraph::`vftable'{for `IPersistStream'}
0x18000273e  mov     [rcx+10h], rax
0x180002742  lea     rax, ??_7CFilterGraph@@6BIObjectWithSite@@@; const CFilterGraph::`vftable'{for `IObjectWithSite'}
0x180002749  mov     [rcx+18h], rax
0x18000274d  lea     rax, ??_7CFilterGraph@@6BIAMMainThread@@@; const CFilterGraph::`vftable'{for `IAMMainThread'}
0x180002754  mov     [rcx+20h], rax
0x180002758  lea     rax, ??_7CFilterGraph@@6BIAMOpenProgress@@@; const CFilterGraph::`vftable'{for `IAMOpenProgress'}
0x18000275f  mov     [rcx+28h], rax
0x180002763  lea     rax, ??_7CFilterGraph@@6BIAMGraphStreams@@@; const CFilterGraph::`vftable'{for `IAMGraphStreams'}
0x18000276a  mov     [rcx+30h], rax
0x18000276e  lea     rax, ??_7CFilterGraph@@6BIVideoFrameStep@@@; const CFilterGraph::`vftable'{for `IVideoFrameStep'}
0x180002775  mov     [rcx+38h], rax
0x180002779  lea     rax, ??_7CFilterGraph@@6BIServiceProvider@@@; const CFilterGraph::`vftable'{for `IServiceProvider'}
0x180002780  mov     [rcx+40h], rax
0x180002784  lea     rax, ??_7CFilterGraph@@6BIRegisterServiceProvider@@@; const CFilterGraph::`vftable'{for `IRegisterServiceProvider'}
0x18000278b  mov     [rcx+48h], rax
0x18000278f  lea     rax, ??_7CFilterGraph@@6BCUnknown@@@; const CFilterGraph::`vftable'{for `CUnknown'}
0x180002796  mov     [rcx+80h], rax
0x18000279d  lea     rax, ??_7CFilterGraph@@6BIBaseFilter@@@; const CFilterGraph::`vftable'{for `IBaseFilter'}
0x1800027a4  mov     [rcx+98h], rax
0x1800027ab  lea     rax, ??_7CFilterGraph@@6BIAMovieSetup@@@; const CFilterGraph::`vftable'{for `IAMovieSetup'}
0x1800027b2  mov     [rcx+0A0h], rax
0x1800027b9  mov     rcx, [rcx+2D8h]; this
0x1800027c0  test    rcx, rcx
0x1800027c3  jz      short loc_1800027CF
0x1800027c5  mov     edx, 1; unsigned int
0x1800027ca  call    ??_GCDS3D@CWaveOutFilter@@UEAAPEAXI@Z; CWaveOutFilter::CDS3D::`scalar deleting destructor'(uint)
0x1800027cf  mov     rcx, [rbx+0F8h]; this
0x1800027d6  xor     esi, esi
0x1800027d8  mov     [rbx+2D8h], rsi
0x1800027df  test    rcx, rcx
0x1800027e2  jz      short loc_1800027E9
0x1800027e4  call    ?Shutdown@CFGControl@@QEAAJXZ; CFGControl::Shutdown(void)
0x1800027e9  mov     rcx, [rbx+220h]; this
0x1800027f0  test    rcx, rcx
0x1800027f3  jz      short loc_1800027FA
0x1800027f5  call    ?Shutdown@CDistributorManager@@QEAAJXZ; CDistributorManager::Shutdown(void)
0x1800027fa  lea     rcx, [rbx+98h]; this
0x180002801  call    ?Stop@CFilterGraph@@UEAAJXZ; CFilterGraph::Stop(void)
0x180002806  cmp     [rbx+138h], esi
0x18000280c  jle     short loc_18000283B
0x18000280e  xchg    ax, ax
0x180002810  mov     rax, [rbx+128h]
0x180002817  test    rax, rax
0x18000281a  jnz     short loc_180002821
0x18000281c  mov     rdx, rsi
0x18000281f  jmp     short loc_180002825
0x180002821  mov     rdx, [rax+10h]
0x180002825  mov     rdx, [rdx]; struct IBaseFilter *
0x180002828  xor     r8d, r8d; unsigned int
0x18000282b  mov     rcx, rbx; this
0x18000282e  call    ?RemoveFilterInternal@CFilterGraph@@AEAAJPEAUIBaseFilter@@K@Z; CFilterGraph::RemoveFilterInternal(IBaseFilter *,ulong)
0x180002833  cmp     [rbx+138h], esi
0x180002839  jg      short loc_180002810
0x18000283b  mov     rcx, [rbx+158h]; Block
0x180002842  test    rcx, rcx
0x180002845  jz      short loc_1800028C6
0x180002847  mov     rax, [rcx]
0x18000284a  mov     rdx, [rcx+8]
0x18000284e  test    rax, rax
0x180002851  jnz     short loc_18000285C
0x180002853  mov     [rbx+158h], rdx
0x18000285a  jmp     short loc_180002860
0x18000285c  mov     [rax+8], rdx
0x180002860  mov     rax, [rcx+8]
0x180002864  mov     rdx, [rcx]
0x180002867  test    rax, rax
0x18000286a  jnz     short loc_180002875
0x18000286c  mov     [rbx+160h], rdx
0x180002873  jmp     short loc_180002878
0x180002875  mov     [rax], rdx
0x180002878  mov     eax, [rbx+170h]
0x18000287e  mov     rdi, [rcx+10h]
0x180002882  cmp     [rbx+174h], eax
0x180002888  jge     short loc_1800028A4
0x18000288a  mov     rax, [rbx+178h]
0x180002891  mov     [rcx+8], rax
0x180002895  inc     dword ptr [rbx+174h]
0x18000289b  mov     [rbx+178h], rcx
0x1800028a2  jmp     short loc_1800028AE
0x1800028a4  mov     edx, 18h
0x1800028a9  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x1800028ae  dec     dword ptr [rbx+168h]
0x1800028b4  test    rdi, rdi
0x1800028b7  jz      short loc_1800028C6
0x1800028b9  mov     rcx, rdi; this
0x1800028bc  call    ??_GConGen@CFilterGraph@@QEAAPEAXI@Z; CFilterGraph::ConGen::`scalar deleting destructor'(uint)
0x1800028c1  jmp     loc_18000283B
0x1800028c6  mov     rcx, [rbx+2F8h]
0x1800028cd  test    rcx, rcx
0x1800028d0  jz      short loc_1800028E5
0x1800028d2  mov     rax, [rcx]
0x1800028d5  mov     rax, [rax+10h]
0x1800028d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028de  mov     [rbx+2F8h], rsi
0x1800028e5  mov     rcx, [rbx+300h]
0x1800028ec  test    rcx, rcx
0x1800028ef  jz      short loc_180002904
0x1800028f1  mov     rax, [rcx]
0x1800028f4  mov     rax, [rax+10h]
0x1800028f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fd  mov     [rbx+300h], rsi
0x180002904  mov     rcx, [rbx+0B0h]
0x18000290b  test    rcx, rcx
0x18000290e  jz      short loc_180002923
0x180002910  mov     rax, [rcx]
0x180002913  mov     rax, [rax+10h]
0x180002917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291c  mov     [rbx+0B0h], rsi
0x180002923  mov     rcx, [rbx+1B0h]
0x18000292a  test    rcx, rcx
0x18000292d  jz      short loc_18000293B
0x18000292f  mov     rax, [rcx]
0x180002932  mov     rax, [rax+10h]
0x180002936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000293b  mov     rdi, [rbx+220h]
0x180002942  test    rdi, rdi
0x180002945  jz      short loc_18000295C
0x180002947  mov     rcx, rdi; this
0x18000294a  call    ??1CDistributorManager@@QEAA@XZ; CDistributorManager::~CDistributorManager(void)
0x18000294f  mov     edx, 80h
0x180002954  mov     rcx, rdi; Block
0x180002957  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x18000295c  mov     rdi, [rbx+0F8h]
0x180002963  test    rdi, rdi
0x180002966  jz      short loc_18000297D
0x180002968  mov     rcx, rdi; this
0x18000296b  call    ??1CFGControl@@AEAA@XZ; CFGControl::~CFGControl(void)
0x180002970  mov     edx, 6E0h
0x180002975  mov     rcx, rdi; Block
0x180002978  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x18000297d  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002984  call    cs:__imp_EnterCriticalSection
0x18000298b  nop     dword ptr [rax+rax+00h]
0x180002990  mov     ecx, cs:?g_dwObjectThreadId@@3KA; idThread
0x180002996  cmp     [rbx+1E4h], ecx
0x18000299c  jnz     short loc_1800029BB
0x18000299e  add     cs:?g_cFGObjects@@3KA, 0FFFFFFFFh; ulong g_cFGObjects
0x1800029a5  jnz     short loc_1800029BB
0x1800029a7  xor     r9d, r9d; lParam
0x1800029aa  xor     r8d, r8d; wParam
0x1800029ad  xor     edx, edx; Msg
0x1800029af  call    cs:__imp_PostThreadMessageW
0x1800029b6  nop     dword ptr [rax+rax+00h]
0x1800029bb  lea     rcx, ?g_csObjectThread@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800029c2  call    cs:__imp_LeaveCriticalSection
0x1800029c9  nop     dword ptr [rax+rax+00h]
0x1800029ce  cmp     [rbx+2E0h], sil
0x1800029d5  jz      short loc_1800029F1
0x1800029d7  mov     ecx, [rbx+1E4h]; idThread
0x1800029dd  xor     r9d, r9d; lParam
0x1800029e0  xor     r8d, r8d; wParam
0x1800029e3  xor     edx, edx; Msg
0x1800029e5  call    cs:__imp_PostThreadMessageW
0x1800029ec  nop     dword ptr [rax+rax+00h]
0x1800029f1  mov     rcx, [rbx+278h]
0x1800029f8  test    rcx, rcx
0x1800029fb  jz      short loc_180002A09
0x1800029fd  mov     rax, [rcx]
0x180002a00  mov     rax, [rax+10h]
0x180002a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a09  mov     rcx, [rbx+210h]
0x180002a10  test    rcx, rcx
0x180002a13  jz      short loc_180002A21
0x180002a15  mov     rax, [rcx]
0x180002a18  mov     rax, [rax+10h]
0x180002a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a21  mov     [rbx+210h], rsi
0x180002a28  lea     rax, ??_7CGraphConfig@@6BIGraphConfig@@@; const CGraphConfig::`vftable'{for `IGraphConfig'}
0x180002a2f  mov     rcx, [rbx+2D0h]; this
0x180002a36  mov     [rbx+2A8h], rax
0x180002a3d  lea     rax, ??_7CGraphConfig@@6BCUnknown@@@; const CGraphConfig::`vftable'{for `CUnknown'}
0x180002a44  mov     [rbx+2B0h], rax
0x180002a4b  test    rcx, rcx
0x180002a4e  jz      short loc_180002A55
0x180002a50  call    ??_GCFilterCache@@QEAAPEAXI@Z; CFilterCache::`scalar deleting destructor'(uint)
0x180002a55  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180002a5c  mov     rcx, [rbx+2A0h]
0x180002a63  test    rcx, rcx
0x180002a66  jz      short loc_180002A74
0x180002a68  mov     rax, [rcx]
0x180002a6b  mov     rax, [rax+10h]
0x180002a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a74  mov     rcx, [rbx+290h]
0x180002a7b  test    rcx, rcx
0x180002a7e  jz      short loc_180002A8C
0x180002a80  mov     rax, [rcx]
0x180002a83  mov     rax, [rax+10h]
0x180002a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8c  mov     rcx, [rbx+288h]
0x180002a93  test    rcx, rcx
0x180002a96  jz      short loc_180002AA4
0x180002a98  mov     rax, [rcx]
0x180002a9b  mov     rax, [rax+10h]
0x180002a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa4  mov     rdi, [rbx+250h]
0x180002aab  test    rdi, rdi
0x180002aae  jz      short loc_180002AC6
0x180002ab0  mov     rcx, rdi; Block
0x180002ab3  mov     edx, 18h
0x180002ab8  mov     rdi, [rdi+8]
0x180002abc  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180002ac1  test    rdi, rdi
0x180002ac4  jnz     short loc_180002AB0
0x180002ac6  mov     rdi, [rbx+270h]
0x180002acd  mov     [rbx+260h], esi
0x180002ad3  mov     [rbx+258h], rsi
0x180002ada  mov     [rbx+250h], rsi
0x180002ae1  test    rdi, rdi
0x180002ae4  jz      short loc_180002AFC
0x180002ae6  mov     rcx, rdi; Block
0x180002ae9  mov     edx, 18h
0x180002aee  mov     rdi, [rdi+8]
0x180002af2  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180002af7  test    rdi, rdi
0x180002afa  jnz     short loc_180002AE6
0x180002afc  lea     rcx, [rbx+228h]; lpCriticalSection
0x180002b03  call    cs:__imp_DeleteCriticalSection
0x180002b0a  nop     dword ptr [rax+rax+00h]
0x180002b0f  mov     rcx, [rbx+1F8h]; hObject
0x180002b16  test    rcx, rcx
0x180002b19  jz      short loc_180002B27
0x180002b1b  call    cs:__imp_CloseHandle
0x180002b22  nop     dword ptr [rax+rax+00h]
0x180002b27  mov     rdi, [rbx+188h]
0x180002b2e  test    rdi, rdi
0x180002b31  jz      short loc_180002B6F
0x180002b33  mov     rcx, [rdi+8]
0x180002b37  mov     rax, [rcx]
0x180002b3a  mov     rax, [rax+10h]
0x180002b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b43  mov     rcx, [rdi+10h]; pv
0x180002b47  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180002b4c  mov     rax, [rdi]
0x180002b4f  mov     edx, 18h
0x180002b54  mov     rcx, rdi; Block
0x180002b57  mov     [rbx+188h], rax
0x180002b5e  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180002b63  mov     rdi, [rbx+188h]
0x180002b6a  test    rdi, rdi
0x180002b6d  jnz     short loc_180002B33
0x180002b6f  mov     rdi, [rbx+158h]
0x180002b76  test    rdi, rdi
0x180002b79  jz      short loc_180002B91
0x180002b7b  mov     rcx, rdi; Block
0x180002b7e  mov     edx, 18h
0x180002b83  mov     rdi, [rdi+8]
0x180002b87  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180002b8c  test    rdi, rdi
0x180002b8f  jnz     short loc_180002B7B
0x180002b91  mov     rdi, [rbx+178h]
0x180002b98  mov     [rbx+168h], esi
0x180002b9e  mov     [rbx+160h], rsi
0x180002ba5  mov     [rbx+158h], rsi
0x180002bac  test    rdi, rdi
0x180002baf  jz      short loc_180002BC7
0x180002bb1  mov     rcx, rdi; Block
0x180002bb4  mov     edx, 18h
0x180002bb9  mov     rdi, [rdi+8]
0x180002bbd  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180002bc2  test    rdi, rdi
0x180002bc5  jnz     short loc_180002BB1
0x180002bc7  lea     rcx, [rbx+128h]; this
0x180002bce  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x180002bd3  mov     rcx, [rbx+100h]; hObject
0x180002bda  test    rcx, rcx
0x180002bdd  jz      short loc_180002BF2
0x180002bdf  call    cs:__imp_CloseHandle
0x180002be6  nop     dword ptr [rax+rax+00h]
0x180002beb  mov     [rbx+100h], rsi
0x180002bf2  mov     rcx, [rbx+0D8h]; Block
0x180002bf9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002bfe  mov     rcx, [rbx+0B0h]
0x180002c05  test    rcx, rcx
0x180002c08  jz      short loc_180002C1D
0x180002c0a  mov     rax, [rcx]
0x180002c0d  mov     rax, [rax+10h]
0x180002c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c16  mov     [rbx+0B0h], rsi
0x180002c1d  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180002c24  lea     rax, ??_7CServiceProvider@@6BIServiceProvider@@@; const CServiceProvider::`vftable'{for `IServiceProvider'}
0x180002c2b  mov     rcx, [rbx+78h]; this
0x180002c2f  mov     [rbx+40h], rax
0x180002c33  lea     rax, ??_7CServiceProvider@@6BIRegisterServiceProvider@@@; const CServiceProvider::`vftable'{for `IRegisterServiceProvider'}
0x180002c3a  mov     [rbx+48h], rax
0x180002c3e  test    rcx, rcx
0x180002c41  jz      short loc_180002C58
0x180002c43  mov     rax, [rcx]
0x180002c46  mov     [rbx+78h], rax
0x180002c4a  call    ??_GProviderEntry@CServiceProvider@@QEAAPEAXI@Z; CServiceProvider::ProviderEntry::`scalar deleting destructor'(uint)
0x180002c4f  mov     rcx, [rbx+78h]
  ... truncated ...
```
