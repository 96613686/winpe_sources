# CFilterGraph::CFilterGraph(ushort const *,IUnknown *,bool,long *)

- ea: `0x180029690`
- end: `0x180029d84`
- name: `??0CFilterGraph@@AEAA@PEBGPEAUIUnknown@@_NPEAJ@Z`
- size: `1780`
- prototype: `CFilterGraph *__usercall@<rax>(CFilterGraph *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, bool@<r9b>, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180060e60`

## callees

- `0x1800049c0`
- `0x180023b40`
- `0x180029690`
- `0x180038458`
- `0x18015e010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800298d8`
- `KERNEL32!CreateEventW` at `0x1800298d8`
- `KERNEL32!InitializeCriticalSection` at `0x1800296c9`
- `KERNEL32!InitializeCriticalSection` at `0x180029921`
- `KERNEL32!InitializeCriticalSection` at `0x180029b5a`
- `KERNEL32!InitializeCriticalSection` at `0x1800296c9`
- `KERNEL32!InitializeCriticalSection` at `0x180029921`
- `KERNEL32!InitializeCriticalSection` at `0x180029b5a`
- `KERNEL32!LeaveCriticalSection` at `0x180029b46`
- `KERNEL32!LeaveCriticalSection` at `0x180029b46`
- `KERNEL32!EnterCriticalSection` at `0x180029b2d`
- `KERNEL32!EnterCriticalSection` at `0x180029b2d`
- `KERNEL32!GetCurrentThreadId` at `0x180029a87`
- `KERNEL32!GetCurrentThreadId` at `0x180029a87`
- `KERNEL32!CreateMutexW` at `0x1800297c8`
- `KERNEL32!CreateMutexW` at `0x1800297c8`
- `ADVAPI32!RegQueryValueExW` at `0x180029c56`
- `ADVAPI32!RegQueryValueExW` at `0x180029cb8`
- `ADVAPI32!RegQueryValueExW` at `0x180029c56`
- `ADVAPI32!RegQueryValueExW` at `0x180029cb8`
- `ADVAPI32!RegOpenKeyExW` at `0x180029bf5`
- `ADVAPI32!RegOpenKeyExW` at `0x180029bf5`
- `ADVAPI32!RegCloseKey` at `0x180029ce5`
- `ADVAPI32!RegCloseKey` at `0x180029ce5`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180029ae8`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x180029ae8`
- `ole32!CreateBindCtx` at `0x180029d40`
- `ole32!CreateBindCtx` at `0x180029d40`
- `ole32!CoCreateInstance` at `0x180029bb7`
- `ole32!CoCreateInstance` at `0x180029bb7`

## pseudocode

```c
CFilterGraph *__fastcall CFilterGraph::CFilterGraph(
        CFilterGraph *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        char a4,
        int *a5)
{
  struct IUnknown *v8; // rax
  HANDLE MutexW; // rax
  int *v10; // rsi
  HANDLE EventW; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rbp
  _QWORD *v14; // rax
  unsigned int v15; // edx
  _QWORD *v16; // rax
  IUnknown *v17; // rcx
  HRESULT FreeThreadedMarshaler; // eax
  struct _RTL_CRITICAL_SECTION *v19; // rax
  struct _RTL_CRITICAL_SECTION *v20; // r14
  ULONG_PTR v21; // rbx
  HRESULT Instance; // eax
  CFGControl *v23; // rax
  CFGControl *v24; // rax
  DWORD Type; // [rsp+80h] [rbp+8h] BYREF
  const unsigned __int16 *cbData; // [rsp+88h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+20h] BYREF

  cbData = a2;
  *((_QWORD *)this + 8) = &CServiceProvider::`vftable'{for `IServiceProvider'};
  *((_QWORD *)this + 9) = &CServiceProvider::`vftable'{for `IRegisterServiceProvider'};
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 2);
  *((_QWORD *)this + 15) = 0;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 23) = 0;
  v8 = (struct IUnknown *)((char *)this + 128);
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 22) = 0;
  if ( a3 )
    v8 = a3;
  *((_QWORD *)this + 17) = v8;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 26) = this;
  *((_QWORD *)this + 27) = 0;
  *((GUID *)this + 12) = CLSID_FilterGraph;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 60) = 1;
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
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 20) = &CFilterGraph::`vftable'{for `IAMovieSetup'};
  MutexW = CreateMutexW(0, 0, 0);
  v10 = a5;
  *((_QWORD *)this + 32) = MutexW;
  *((_DWORD *)this + 66) = 0;
  *((_DWORD *)this + 67) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  if ( !*((_QWORD *)this + 32) )
    *v10 = -2147024882;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = 10;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = this;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_QWORD *)this + 46) = 10;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 72) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_DWORD *)this + 102) = 0;
  *((_DWORD *)this + 110) = 0;
  *((_QWORD *)this + 56) = 5000000;
  *((_DWORD *)this + 114) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = -1;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 63) = EventW;
  if ( !EventW && v10 && *v10 >= 0 )
    *v10 = -2147024882;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_DWORD *)this + 134) = 0;
  *((_QWORD *)this + 68) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_DWORD *)this + 152) = 0;
  *((_QWORD *)this + 77) = 10;
  *((_QWORD *)this + 78) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_WORD *)this + 320) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_DWORD *)this + 166) = 0;
  *((_QWORD *)this + 84) = 0;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  *((_QWORD *)this + 87) = this;
  *((_DWORD *)this + 176) = 0;
  *((_QWORD *)this + 85) = &CGraphConfig::`vftable'{for `IGraphConfig'};
  *((_QWORD *)this + 86) = &CGraphConfig::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 89) = this;
  *((_QWORD *)this + 90) = 0;
  v12 = operator new(0x18u);
  if ( v12 )
  {
    v13 = *((_QWORD *)this + 89);
    *v12 = 0;
    v12[1] = 0;
    *((_DWORD *)v12 + 4) = 0;
    v14 = operator new(0x28u);
    if ( v14 )
    {
      v14[3] = 10;
      *v14 = 0;
      v14[1] = 0;
      *((_DWORD *)v14 + 4) = 0;
      v14[4] = 0;
      *v12 = v14;
      v12[1] = v13 + 256;
    }
    else
    {
      *v12 = 0;
      *v10 = -2147024882;
    }
    *((_QWORD *)this + 90) = v12;
    if ( *v10 < 0 )
    {
      CFilterCache::`scalar deleting destructor'((CFilterCache *)v12, v15);
      *((_QWORD *)this + 90) = 0;
    }
  }
  else
  {
    *((_QWORD *)this + 90) = 0;
    *v10 = -2147024882;
  }
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_BYTE *)this + 736) = a4;
  *(_WORD *)((char *)this + 737) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 0;
  *((_BYTE *)this + 776) = 1;
  *((_DWORD *)this + 121) = GetCurrentThreadId();
  v16 = operator new(0x28u);
  if ( !v16 )
  {
    *((_QWORD *)this + 91) = 0;
    goto LABEL_38;
  }
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  v16[2] = this;
  *((_DWORD *)v16 + 6) = 0;
  *v16 = &CFilterChain::`vftable'{for `IFilterChain'};
  v16[1] = &CFilterChain::`vftable'{for `CUnknown'};
  v16[4] = this;
  v17 = (IUnknown *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 91) = v16;
  FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v17, (LPUNKNOWN *)this + 84);
  if ( FreeThreadedMarshaler < 0 )
  {
LABEL_34:
    *v10 = FreeThreadedMarshaler;
    return this;
  }
  v19 = (struct _RTL_CRITICAL_SECTION *)operator new(0x50u);
  v20 = v19;
  if ( !v19 )
  {
    *((_QWORD *)this + 66) = 0;
    goto LABEL_38;
  }
  v21 = *((_QWORD *)this + 17);
  v19->LockCount = 0;
  v19->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CStatContainer>::`vftable';
  EnterCriticalSection(&stru_18019E7F8);
  ++dword_18019A950;
  LeaveCriticalSection(&stru_18019E7F8);
  LODWORD(v20->SpinCount) = 0;
  InitializeCriticalSection(v20 + 1);
  v20->SpinCount = v21;
  v20->LockSemaphore = &ATL::CComContainedObject<CStatContainer>::`vftable';
  _InterlockedIncrement(&dword_18019E7E8);
  *((_QWORD *)this + 66) = v20;
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v20->DebugInfo->CriticalSection)(v20);
  if ( *v10 >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_FilterMapper2, *((LPUNKNOWN *)this + 17), 3u, &IID_IUnknown, (LPVOID *)this + 54);
    if ( Instance < 0 )
      *v10 = Instance;
  }
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\DirectShow\\PushClock", 0, 0x20019u, &phkResult) )
  {
    Type = 0;
    Data = 0;
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(phkResult, L"SyncUsingOffset", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      *((_DWORD *)this + 110) = Data != 0;
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(phkResult, L"MaxGraphLatencyMS", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
      *((_QWORD *)this + 56) = 10000LL * Data;
    RegCloseKey(phkResult);
  }
  if ( *v10 < 0 )
    return this;
  v23 = (CFGControl *)operator new(0x6E0u);
  if ( !v23 )
  {
    *((_QWORD *)this + 31) = 0;
    goto LABEL_38;
  }
  v24 = CFGControl::CFGControl(v23, this, v10);
  *((_QWORD *)this + 31) = v24;
  if ( !v24 )
  {
LABEL_38:
    *v10 = -2147024882;
    return this;
  }
  if ( *v10 >= 0 )
  {
    *((_QWORD *)this + 61) = *((_QWORD *)v24 + 63);
    if ( *v10 >= 0 )
    {
      FreeThreadedMarshaler = CreateBindCtx(0, (LPBC *)this + 79);
      goto LABEL_34;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180029690  mov     [rsp+cbData], rdx
0x180029695  push    rbx
0x180029696  push    rbp
0x180029697  push    rsi
0x180029698  push    rdi
0x180029699  push    r12
0x18002969b  push    r13
0x18002969d  push    r14
0x18002969f  push    r15
0x1800296a1  sub     rsp, 38h
0x1800296a5  lea     rax, ??_7CServiceProvider@@6BIServiceProvider@@@; const CServiceProvider::`vftable'{for `IServiceProvider'}
0x1800296ac  mov     rdi, rcx
0x1800296af  mov     [rcx+40h], rax
0x1800296b3  movzx   r13d, r9b
0x1800296b7  lea     rax, ??_7CServiceProvider@@6BIRegisterServiceProvider@@@; const CServiceProvider::`vftable'{for `IRegisterServiceProvider'}
0x1800296be  mov     rbx, r8
0x1800296c1  mov     [rcx+48h], rax
0x1800296c5  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800296c9  call    cs:__imp_InitializeCriticalSection
0x1800296d0  nop     dword ptr [rax+rax+00h]
0x1800296d5  xor     ebp, ebp
0x1800296d7  lea     rdx, [rdi+80h]
0x1800296de  mov     [rdi+78h], rbp
0x1800296e2  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x1800296e9  mov     [rdx+38h], rbp
0x1800296ed  mov     rax, rdx
0x1800296f0  mov     [rdx+28h], ebp
0x1800296f3  test    rbx, rbx
0x1800296f6  mov     [rdx+30h], rbp
0x1800296fa  cmovnz  rax, rbx
0x1800296fe  xor     r8d, r8d; lpName
0x180029701  mov     [rdx+8], rax
0x180029705  xor     ecx, ecx; lpMutexAttributes
0x180029707  mov     [rdx+10h], ebp
0x18002970a  lea     rax, ??_7CFilterGraph@@6BIFilterGraph3@@@; const CFilterGraph::`vftable'{for `IFilterGraph3'}
0x180029711  movups  xmm0, xmmword ptr cs:CLSID_FilterGraph.Data1
0x180029718  mov     [rdx+50h], rdi
0x18002971c  mov     [rdx+58h], rbp
0x180029720  movups  xmmword ptr [rdx+40h], xmm0
0x180029724  mov     [rdx+60h], rbp
0x180029728  mov     [rdx+68h], rbp
0x18002972c  mov     dword ptr [rdx+70h], 1
0x180029733  mov     [rdi], rax
0x180029736  lea     rax, ??_7CFilterGraph@@6BIGraphVersion@@@; const CFilterGraph::`vftable'{for `IGraphVersion'}
0x18002973d  mov     [rdi+8], rax
0x180029741  lea     rax, ??_7CFilterGraph@@6BIPersistStream@@@; const CFilterGraph::`vftable'{for `IPersistStream'}
0x180029748  mov     [rdi+10h], rax
0x18002974c  lea     rax, ??_7CFilterGraph@@6BIObjectWithSite@@@; const CFilterGraph::`vftable'{for `IObjectWithSite'}
0x180029753  mov     [rdi+18h], rax
0x180029757  lea     rax, ??_7CFilterGraph@@6BIAMMainThread@@@; const CFilterGraph::`vftable'{for `IAMMainThread'}
0x18002975e  mov     [rdi+20h], rax
0x180029762  lea     rax, ??_7CFilterGraph@@6BIAMOpenProgress@@@; const CFilterGraph::`vftable'{for `IAMOpenProgress'}
0x180029769  mov     [rdi+28h], rax
0x18002976d  lea     rax, ??_7CFilterGraph@@6BIAMGraphStreams@@@; const CFilterGraph::`vftable'{for `IAMGraphStreams'}
0x180029774  mov     [rdi+30h], rax
0x180029778  lea     rax, ??_7CFilterGraph@@6BIVideoFrameStep@@@; const CFilterGraph::`vftable'{for `IVideoFrameStep'}
0x18002977f  mov     [rdi+38h], rax
0x180029783  lea     rax, ??_7CFilterGraph@@6BIServiceProvider@@@; const CFilterGraph::`vftable'{for `IServiceProvider'}
0x18002978a  mov     [rdi+40h], rax
0x18002978e  lea     rax, ??_7CFilterGraph@@6BIRegisterServiceProvider@@@; const CFilterGraph::`vftable'{for `IRegisterServiceProvider'}
0x180029795  mov     [rdi+48h], rax
0x180029799  lea     rax, ??_7CFilterGraph@@6BCUnknown@@@; const CFilterGraph::`vftable'{for `CUnknown'}
0x1800297a0  mov     [rdx], rax
0x1800297a3  lea     rax, ??_7CFilterGraph@@6BIBaseFilter@@@; const CFilterGraph::`vftable'{for `IBaseFilter'}
0x1800297aa  mov     [rdi+98h], rax
0x1800297b1  xor     edx, edx; bInitialOwner
0x1800297b3  lea     rax, ??_7CFilterGraph@@6BIAMovieSetup@@@; const CFilterGraph::`vftable'{for `IAMovieSetup'}
0x1800297ba  mov     [rdi+0F8h], rbp
0x1800297c1  mov     [rdi+0A0h], rax
0x1800297c8  call    cs:__imp_CreateMutexW
0x1800297cf  nop     dword ptr [rax+rax+00h]
0x1800297d4  mov     rsi, [rsp+78h+arg_20]
0x1800297dc  mov     [rdi+100h], rax
0x1800297e3  mov     [rdi+108h], ebp
0x1800297e9  mov     [rdi+10Ch], ebp
0x1800297ef  mov     [rdi+110h], rbp
0x1800297f6  mov     [rdi+118h], rbp
0x1800297fd  cmp     [rdi+100h], rbp
0x180029804  jnz     short loc_18002980C
0x180029806  mov     dword ptr [rsi], 8007000Eh
0x18002980c  mov     [rdi+128h], rbp
0x180029813  lea     r15, [rdi+1B0h]
0x18002981a  mov     [rdi+130h], rbp
0x180029821  xor     r9d, r9d; lpName
0x180029824  mov     [rdi+138h], ebp
0x18002982a  xor     r8d, r8d; bInitialState
0x18002982d  mov     qword ptr [rdi+140h], 0Ah
0x180029838  xor     edx, edx; bManualReset
0x18002983a  mov     [rdi+148h], rbp
0x180029841  xor     ecx, ecx; lpEventAttributes
0x180029843  mov     [rdi+150h], rdi
0x18002984a  mov     [rdi+158h], rbp
0x180029851  mov     [rdi+160h], rbp
0x180029858  mov     [rdi+168h], ebp
0x18002985e  mov     qword ptr [rdi+170h], 0Ah
0x180029869  mov     [rdi+178h], rbp
0x180029870  mov     [rdi+180h], ebp
0x180029876  mov     [rdi+188h], rbp
0x18002987d  mov     [rdi+1A0h], rbp
0x180029884  mov     [rdi+1A8h], rbp
0x18002988b  mov     [r15], rbp
0x18002988e  mov     [rdi+120h], ebp
0x180029894  mov     [rdi+190h], rbp
0x18002989b  mov     [rdi+198h], ebp
0x1800298a1  mov     [rdi+1B8h], ebp
0x1800298a7  mov     qword ptr [rdi+1C0h], 4C4B40h
0x1800298b2  mov     [rdi+1C8h], ebp
0x1800298b8  mov     [rdi+1D0h], rbp
0x1800298bf  mov     qword ptr [rdi+1D8h], 0FFFFFFFFFFFFFFFFh
0x1800298ca  mov     [rdi+1E0h], rbp
0x1800298d1  mov     [rdi+1E8h], rbp
0x1800298d8  call    cs:__imp_CreateEventW
0x1800298df  nop     dword ptr [rax+rax+00h]
0x1800298e4  mov     [rdi+1F8h], rax
0x1800298eb  test    rax, rax
0x1800298ee  jnz     short loc_1800298FF
0x1800298f0  test    rsi, rsi
0x1800298f3  jz      short loc_1800298FF
0x1800298f5  cmp     [rsi], ebp
0x1800298f7  jl      short loc_1800298FF
0x1800298f9  mov     dword ptr [rsi], 8007000Eh
0x1800298ff  lea     rcx, [rdi+228h]; lpCriticalSection
0x180029906  mov     [rdi+200h], rbp
0x18002990d  mov     [rdi+210h], rbp
0x180029914  mov     [rdi+218h], ebp
0x18002991a  mov     [rdi+220h], rbp
0x180029921  call    cs:__imp_InitializeCriticalSection
0x180029928  nop     dword ptr [rax+rax+00h]
0x18002992d  mov     [rdi+250h], rbp
0x180029934  mov     [rdi+258h], rbp
0x18002993b  mov     [rdi+260h], ebp
0x180029941  mov     qword ptr [rdi+268h], 0Ah
0x18002994c  mov     [rdi+270h], rbp
0x180029953  mov     [rdi+278h], rbp
0x18002995a  mov     [rdi+280h], bp
0x180029961  mov     [rdi+288h], rbp
0x180029968  mov     [rdi+290h], rbp
0x18002996f  mov     [rdi+298h], ebp
0x180029975  mov     [rdi+2A0h], rbp
0x18002997c  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180029983  mov     [rdi+2B8h], rdi
0x18002998a  lea     rax, ??_7CGraphConfig@@6BIGraphConfig@@@; const CGraphConfig::`vftable'{for `IGraphConfig'}
0x180029991  mov     [rdi+2C0h], ebp
0x180029997  mov     ecx, 18h; Size
0x18002999c  mov     [rdi+2A8h], rax
0x1800299a3  lea     rax, ??_7CGraphConfig@@6BCUnknown@@@; const CGraphConfig::`vftable'{for `CUnknown'}
0x1800299aa  mov     [rdi+2B0h], rax
0x1800299b1  mov     [rdi+2C8h], rdi
0x1800299b8  mov     [rdi+2D0h], rbp
0x1800299bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800299c4  mov     rbx, rax
0x1800299c7  test    rax, rax
0x1800299ca  jz      short loc_180029A40
0x1800299cc  mov     rbp, [rdi+2C8h]
0x1800299d3  xor     eax, eax
0x1800299d5  mov     ecx, 28h ; '('; Size
0x1800299da  mov     [rbx], rax
0x1800299dd  mov     [rbx+8], rax
0x1800299e1  mov     [rbx+10h], eax
0x1800299e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800299e9  test    rax, rax
0x1800299ec  jz      short loc_180029A18
0x1800299ee  xor     ecx, ecx
0x1800299f0  mov     qword ptr [rax+18h], 0Ah
0x1800299f8  mov     [rax], rcx
0x1800299fb  mov     [rax+8], rcx
0x1800299ff  mov     [rax+10h], ecx
0x180029a02  mov     [rax+20h], rcx
0x180029a06  mov     [rbx], rax
0x180029a09  lea     rax, [rbp+100h]
0x180029a10  mov     [rbx+8], rax
0x180029a14  xor     ebp, ebp
0x180029a16  jmp     short loc_180029A23
0x180029a18  xor     ebp, ebp
0x180029a1a  mov     [rbx], rbp
0x180029a1d  mov     dword ptr [rsi], 8007000Eh
0x180029a23  mov     [rdi+2D0h], rbx
0x180029a2a  cmp     dword ptr [rsi], 0
0x180029a2d  jge     short loc_180029A4D
0x180029a2f  mov     rcx, rbx; this
0x180029a32  call    ??_GCFilterCache@@QEAAPEAXI@Z; CFilterCache::`scalar deleting destructor'(uint)
0x180029a37  mov     [rdi+2D0h], rbp
0x180029a3e  jmp     short loc_180029A4D
0x180029a40  mov     [rdi+2D0h], rbp
0x180029a47  mov     dword ptr [rsi], 8007000Eh
0x180029a4d  mov     [rdi+2D8h], rbp
0x180029a54  mov     [rdi+2E8h], rbp
0x180029a5b  mov     [rdi+2F0h], rbp
0x180029a62  mov     [rdi+2E0h], r13b
0x180029a69  mov     word ptr [rdi+2E1h], 0
0x180029a72  mov     [rdi+2F8h], rbp
0x180029a79  mov     [rdi+300h], rbp
0x180029a80  mov     byte ptr [rdi+308h], 1
0x180029a87  call    cs:__imp_GetCurrentThreadId
0x180029a8e  nop     dword ptr [rax+rax+00h]
0x180029a93  mov     ecx, 28h ; '('; Size
0x180029a98  mov     [rdi+1E4h], eax
0x180029a9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029aa3  test    rax, rax
0x180029aa6  jz      loc_180029D62
0x180029aac  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180029ab3  mov     [rax+10h], rdi
0x180029ab7  lea     rcx, ??_7CFilterChain@@6BIFilterChain@@@; const CFilterChain::`vftable'{for `IFilterChain'}
0x180029abe  mov     [rax+18h], ebp
0x180029ac1  lea     rdx, [rdi+2A0h]; ppunkMarshal
0x180029ac8  mov     [rax], rcx
0x180029acb  lea     rcx, ??_7CFilterChain@@6BCUnknown@@@; const CFilterChain::`vftable'{for `CUnknown'}
0x180029ad2  mov     [rax+8], rcx
0x180029ad6  mov     [rax+20h], rdi
0x180029ada  mov     rcx, [rdi+88h]; punkOuter
0x180029ae1  mov     [rdi+2D8h], rax
0x180029ae8  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180029aef  nop     dword ptr [rax+rax+00h]
0x180029af4  test    eax, eax
0x180029af6  js      loc_180029D4C
0x180029afc  mov     ecx, 50h ; 'P'; Size
0x180029b01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029b06  mov     r14, rax
0x180029b09  test    rax, rax
0x180029b0c  jz      loc_180029D59
0x180029b12  mov     rbx, [rdi+88h]
0x180029b19  lea     rcx, stru_18019E7F8; lpCriticalSection
0x180029b20  mov     [rax+8], ebp
0x180029b23  lea     rax, ??_7?$CComAggObject@VCStatContainer@@@ATL@@6B@; const ATL::CComAggObject<CStatContainer>::`vftable'
0x180029b2a  mov     [r14], rax
0x180029b2d  call    cs:__imp_EnterCriticalSection
0x180029b34  nop     dword ptr [rax+rax+00h]
0x180029b39  inc     cs:dword_18019A950
0x180029b3f  lea     rcx, stru_18019E7F8; lpCriticalSection
0x180029b46  call    cs:__imp_LeaveCriticalSection
0x180029b4d  nop     dword ptr [rax+rax+00h]
0x180029b52  lea     rcx, [r14+28h]; lpCriticalSection
0x180029b56  mov     [r14+20h], ebp
0x180029b5a  call    cs:__imp_InitializeCriticalSection
0x180029b61  nop     dword ptr [rax+rax+00h]
0x180029b66  lea     rax, ??_7?$CComContainedObject@VCStatContainer@@@ATL@@6B@; const ATL::CComContainedObject<CStatContainer>::`vftable'
0x180029b6d  mov     [r14+20h], rbx
0x180029b71  mov     [r14+18h], rax
0x180029b75  lock inc cs:dword_18019E7E8
0x180029b7c  mov     [rdi+210h], r14
0x180029b83  mov     rcx, r14
0x180029b86  mov     rax, [r14]
0x180029b89  mov     rax, [rax+8]
0x180029b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b92  cmp     dword ptr [rsi], 0
0x180029b95  jl      short loc_180029BC9
0x180029b97  mov     rdx, [rdi+88h]; pUnkOuter
0x180029b9e  lea     r9, IID_IUnknown; riid
0x180029ba5  mov     r8d, 3; dwClsContext
0x180029bab  mov     [rsp+78h+ppv], r15; ppv
0x180029bb0  lea     rcx, CLSID_FilterMapper2; rclsid
0x180029bb7  call    cs:__imp_CoCreateInstance
0x180029bbe  nop     dword ptr [rax+rax+00h]
0x180029bc3  test    eax, eax
0x180029bc5  jns     short loc_180029BC9
0x180029bc7  mov     [rsi], eax
0x180029bc9  lea     rax, [rsp+78h+phkResult]
0x180029bd1  mov     [rsp+78h+phkResult], rbp
0x180029bd9  mov     r9d, 20019h; samDesired
0x180029bdf  mov     [rsp+78h+ppv], rax; phkResult
0x180029be4  xor     r8d, r8d; ulOptions
0x180029be7  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\DirectShow\\PushCl"...
0x180029bee  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180029bf5  call    cs:__imp_RegOpenKeyExW
0x180029bfc  nop     dword ptr [rax+rax+00h]
0x180029c01  test    eax, eax
0x180029c03  jnz     loc_180029CF1
0x180029c09  mov     rcx, [rsp+78h+phkResult]; hKey
0x180029c11  lea     rax, [rsp+78h+cbData]
0x180029c19  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180029c1e  lea     r9, [rsp+78h+Type]; lpType
0x180029c26  lea     rax, [rsp+78h+Data]
0x180029c2e  mov     [rsp+78h+Type], ebp
0x180029c35  xor     r8d, r8d; lpReserved
0x180029c38  mov     [rsp+78h+ppv], rax; lpData
0x180029c3d  lea     rdx, aSyncusingoffse; "SyncUsingOffset"
0x180029c44  mov     [rsp+78h+Data], ebp
0x180029c4b  mov     dword ptr [rsp+78h+cbData], 4
0x180029c56  call    cs:__imp_RegQueryValueExW
0x180029c5d  nop     dword ptr [rax+rax+00h]
0x180029c62  test    eax, eax
0x180029c64  jnz     short loc_180029C79
0x180029c66  cmp     [rsp+78h+Data], 0
0x180029c6e  mov     eax, ebp
0x180029c70  setnz   al
0x180029c73  mov     [rdi+1B8h], eax
0x180029c79  mov     rcx, [rsp+78h+phkResult]; hKey
0x180029c81  lea     rax, [rsp+78h+cbData]
0x180029c89  mov     [rsp+78h+lpcbData], rax; lpcbData
0x180029c8e  lea     r9, [rsp+78h+Type]; lpType
0x180029c96  lea     rax, [rsp+78h+Data]
0x180029c9e  mov     dword ptr [rsp+78h+cbData], 4
0x180029ca9  xor     r8d, r8d; lpReserved
0x180029cac  mov     [rsp+78h+ppv], rax; lpData
0x180029cb1  lea     rdx, aMaxgraphlatenc; "MaxGraphLatencyMS"
0x180029cb8  call    cs:__imp_RegQueryValueExW
0x180029cbf  nop     dword ptr [rax+rax+00h]
0x180029cc4  test    eax, eax
0x180029cc6  jnz     short loc_180029CDD
0x180029cc8  mov     eax, [rsp+78h+Data]
  ... truncated ...
```
