# CSpellerGlobalState::~CSpellerGlobalState(void)

- ea: `0x180273b34`
- end: `0x180273cda`
- name: `??1CSpellerGlobalState@@AEAA@XZ`
- size: `422`
- prototype: `void __fastcall(CSpellerGlobalState *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802754d0`

## callees

- `0x18006ad18`
- `0x1800d29c4`
- `0x1800d2a50`
- `0x18013dac8`
- `0x180273b34`
- `0x180275530`
- `0x180275c90`
- `0x18027733c`
- `0x180278634`
- `0x18027f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273ba9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273bca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273beb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273cbb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273ba9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273bca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273beb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180273cbb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180273c4f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180273c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180273c6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180273c6f`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x180273b88`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreeServices` at `0x180273b88`

## pseudocode

```c
void __fastcall CSpellerGlobalState::~CSpellerGlobalState(CSpellerGlobalState *this)
{
  bool v1; // zf
  struct _MAPPING_SERVICE_INFO *v3; // rcx
  void **v4; // rdi
  void **v5; // rdi
  void **v6; // rdi
  __int64 v7; // rcx
  void *v8; // rdi
  HMODULE v9; // rcx
  void *v10; // rcx
  void **v11; // rdi

  v1 = *((_BYTE *)this + 66) == 0;
  *(_QWORD *)this = &CSpellerGlobalState::`vftable'{for `ISpellEngineTSF'};
  *((_QWORD *)this + 1) = &CSpellerGlobalState::`vftable'{for `ISpellEngineGlobalState'};
  *((_QWORD *)this + 2) = &CSpellerGlobalState::`vftable'{for `IMultilingualSpellEngine'};
  if ( !v1 )
  {
    _InterlockedCompareExchange((volatile signed __int32 *)this + 26, 2, 1);
    CSpellerGlobalState::FinishInitialization(this);
  }
  v3 = (struct _MAPPING_SERVICE_INFO *)*((_QWORD *)this + 31);
  if ( v3 )
    MappingFreeServices(v3);
  CSpellerGlobalState::RemoveSpellCheckingResources(this);
  v4 = (void **)*((_QWORD *)this + 5);
  if ( v4 )
  {
    free(v4[2]);
    operator delete(v4);
  }
  v5 = (void **)*((_QWORD *)this + 3);
  if ( v5 )
  {
    free(v5[2]);
    operator delete(v5);
  }
  v6 = (void **)*((_QWORD *)this + 4);
  if ( v6 )
  {
    free(v6[2]);
    operator delete(v6);
  }
  v7 = *((_QWORD *)this + 16);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 16LL))(*((_QWORD *)this + 16));
  }
  v8 = (void *)*((_QWORD *)this + 7);
  if ( v8 )
  {
    CSpellContextHandler::~CSpellContextHandler(*((CSpellContextHandler **)this + 7));
    operator delete(v8);
  }
  v9 = (HMODULE)*((_QWORD *)this + 17);
  if ( v9 )
    FreeLibrary(v9);
  CSpellerGlobalState::FreeSpellCheckErrors(this);
  v10 = (void *)*((_QWORD *)this + 40);
  if ( v10 )
    CoTaskMemFree(v10);
  v11 = (void **)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    CSpellCheckerTelemetry::LogSpellerStatistics<CSpellCheckerTelemetryStatistics * &>((char *)this + 80);
    operator delete(*v11);
    *v11 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 296);
  CMultilingualSpeller::~CMultilingualSpeller((CSpellerGlobalState *)((char *)this + 256));
  free(*((void **)this + 30));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 48);
}

```

## disassembly

```asm
0x180273b34  mov     [rsp+arg_0], rbx
0x180273b39  push    rdi
0x180273b3a  sub     rsp, 20h
0x180273b3e  cmp     byte ptr [rcx+42h], 0
0x180273b42  lea     rax, ??_7CSpellerGlobalState@@6BISpellEngineTSF@@@; const CSpellerGlobalState::`vftable'{for `ISpellEngineTSF'}
0x180273b49  mov     [rcx], rax
0x180273b4c  mov     rbx, rcx
0x180273b4f  lea     rax, ??_7CSpellerGlobalState@@6BISpellEngineGlobalState@@@; const CSpellerGlobalState::`vftable'{for `ISpellEngineGlobalState'}
0x180273b56  mov     [rcx+8], rax
0x180273b5a  lea     rax, ??_7CSpellerGlobalState@@6BIMultilingualSpellEngine@@@; const CSpellerGlobalState::`vftable'{for `IMultilingualSpellEngine'}
0x180273b61  mov     [rcx+10h], rax
0x180273b65  jz      short loc_180273B7C
0x180273b67  mov     ecx, 2
0x180273b6c  lea     eax, [rcx-1]
0x180273b6f  lock cmpxchg [rbx+68h], ecx
0x180273b74  mov     rcx, rbx; this
0x180273b77  call    ?FinishInitialization@CSpellerGlobalState@@QEAAJXZ; CSpellerGlobalState::FinishInitialization(void)
0x180273b7c  mov     rcx, [rbx+0F8h]; pServiceInfo
0x180273b83  test    rcx, rcx
0x180273b86  jz      short loc_180273B94
0x180273b88  call    cs:__imp_MappingFreeServices
0x180273b8f  nop     dword ptr [rax+rax+00h]
0x180273b94  mov     rcx, rbx; this
0x180273b97  call    ?RemoveSpellCheckingResources@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::RemoveSpellCheckingResources(void)
0x180273b9c  mov     rdi, [rbx+28h]
0x180273ba0  test    rdi, rdi
0x180273ba3  jz      short loc_180273BBD
0x180273ba5  mov     rcx, [rdi+10h]; Block
0x180273ba9  call    cs:__imp_free
0x180273bb0  nop     dword ptr [rax+rax+00h]
0x180273bb5  mov     rcx, rdi; Block
0x180273bb8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180273bbd  mov     rdi, [rbx+18h]
0x180273bc1  test    rdi, rdi
0x180273bc4  jz      short loc_180273BDE
0x180273bc6  mov     rcx, [rdi+10h]; Block
0x180273bca  call    cs:__imp_free
0x180273bd1  nop     dword ptr [rax+rax+00h]
0x180273bd6  mov     rcx, rdi; Block
0x180273bd9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180273bde  mov     rdi, [rbx+20h]
0x180273be2  test    rdi, rdi
0x180273be5  jz      short loc_180273BFF
0x180273be7  mov     rcx, [rdi+10h]; Block
0x180273beb  call    cs:__imp_free
0x180273bf2  nop     dword ptr [rax+rax+00h]
0x180273bf7  mov     rcx, rdi; Block
0x180273bfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180273bff  mov     rcx, [rbx+80h]
0x180273c06  test    rcx, rcx
0x180273c09  jz      short loc_180273C2A
0x180273c0b  mov     rax, [rcx]
0x180273c0e  mov     rax, [rax+20h]
0x180273c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273c17  mov     rcx, [rbx+80h]
0x180273c1e  mov     rax, [rcx]
0x180273c21  mov     rax, [rax+10h]
0x180273c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273c2a  mov     rdi, [rbx+38h]
0x180273c2e  test    rdi, rdi
0x180273c31  jz      short loc_180273C43
0x180273c33  mov     rcx, rdi; this
0x180273c36  call    ??1CSpellContextHandler@@QEAA@XZ; CSpellContextHandler::~CSpellContextHandler(void)
0x180273c3b  mov     rcx, rdi; Block
0x180273c3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180273c43  mov     rcx, [rbx+88h]; hLibModule
0x180273c4a  test    rcx, rcx
0x180273c4d  jz      short loc_180273C5B
0x180273c4f  call    cs:__imp_FreeLibrary
0x180273c56  nop     dword ptr [rax+rax+00h]
0x180273c5b  mov     rcx, rbx; this
0x180273c5e  call    ?FreeSpellCheckErrors@CSpellerGlobalState@@AEAAXXZ; CSpellerGlobalState::FreeSpellCheckErrors(void)
0x180273c63  mov     rcx, [rbx+140h]; pv
0x180273c6a  test    rcx, rcx
0x180273c6d  jz      short loc_180273C7B
0x180273c6f  call    cs:__imp_CoTaskMemFree
0x180273c76  nop     dword ptr [rax+rax+00h]
0x180273c7b  lea     rdi, [rbx+50h]
0x180273c7f  cmp     qword ptr [rdi], 0
0x180273c83  jz      short loc_180273C9C
0x180273c85  mov     rcx, rdi
0x180273c88  call    ??$LogSpellerStatistics@AEAPEAVCSpellCheckerTelemetryStatistics@@@CSpellCheckerTelemetry@@SAXAEAPEAVCSpellCheckerTelemetryStatistics@@@Z; CSpellCheckerTelemetry::LogSpellerStatistics<CSpellCheckerTelemetryStatistics * &>(CSpellCheckerTelemetryStatistics * &)
0x180273c8d  mov     rcx, [rdi]; Block
0x180273c90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180273c95  mov     qword ptr [rdi], 0
0x180273c9c  lea     rcx, [rbx+128h]
0x180273ca3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273ca8  lea     rcx, [rbx+100h]; this
0x180273caf  call    ??1CMultilingualSpeller@@QEAA@XZ; CMultilingualSpeller::~CMultilingualSpeller(void)
0x180273cb4  mov     rcx, [rbx+0F0h]; Block
0x180273cbb  call    cs:__imp_free
0x180273cc2  nop     dword ptr [rax+rax+00h]
0x180273cc7  lea     rcx, [rbx+30h]
0x180273ccb  mov     rbx, [rsp+28h+arg_0]
0x180273cd0  add     rsp, 20h
0x180273cd4  pop     rdi
0x180273cd5  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
