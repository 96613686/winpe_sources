# CManipulationManager::ProcessManipulationThreadCallbackInput(tagMANIPULATION_INPUT_INFO *,void *)

- ea: `0x1801354e4`
- end: `0x180135759`
- name: `?ProcessManipulationThreadCallbackInput@CManipulationManager@@KAHPEAUtagMANIPULATION_INPUT_INFO@@PEAX@Z`
- size: `629`
- prototype: `static int(struct tagMANIPULATION_INPUT_INFO *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180135260`

## callees

- `0x18004a5a8`
- `0x18004a92c`
- `0x180050270`
- `0x180131e14`
- `0x18013508c`
- `0x1801354e4`
- `0x180135d98`
- `0x180135e5c`
- `0x1801360e0`
- `0x1801361c0`
- `0x180136224`
- `0x180136328`
- `0x18016da58`
- `0x1801b3560`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801355e5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801355e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801355cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801355cc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180135571`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180135571`
- `ext-ms-win-compositor-hosting-l1-3-0!SetManipulationInputTarget` at `0x180135691`
- `ext-ms-win-compositor-hosting-l1-3-0!SetManipulationInputTarget` at `0x180135691`

## pseudocode

```c
__int64 __fastcall CManipulationManager::ProcessManipulationThreadCallbackInput(
        struct tagMANIPULATION_INPUT_INFO *a1,
        CManipulationManager *a2)
{
  struct CManipulationFrame *v2; // r15
  unsigned int *v5; // r14
  unsigned __int64 v6; // rbx
  unsigned int v7; // r12d
  int v8; // eax
  LARGE_INTEGER v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  unsigned int *v14; // rbx
  __int64 v15; // r8
  unsigned int near **v16; // r9
  __int64 i; // rdx
  struct CManipulationFrame *v18; // [rsp+70h] [rbp+40h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+50h] BYREF
  struct CManipulationFrame *v20; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  v18 = 0;
  if ( !a1 )
    goto LABEL_10;
  v5 = (unsigned int *)((char *)a1 + 148);
  v6 = *((_QWORD *)a1 + 30);
  v7 = *((_DWORD *)a1 + 42);
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McTemplateU0qq_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      MANIPULATION_FRAME_RECEIVED,
      v7,
      *v5);
  InputTraceLogging::GestureTargeting::QueueFrame(v6, *(_QWORD *)a1, v7, *v5);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v18);
  v8 = CManipulationFrame::Create(a1, &v18);
  v2 = v18;
  if ( v8 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x15Du, 0);
LABEL_19:
    v14 = v5;
    goto LABEL_14;
  }
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v9 = PerformanceCount;
  *(LARGE_INTEGER *)((char *)v2 + (IsVailContainer() ? 0x48 : 0) + 72) = v9;
  InputTraceLogging::TelemetryDebug::GestureTargeting::QueueFrame((struct CManipulationFrame *)((char *)v2 + 32));
  v20 = v2;
  Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(&v20);
  v18 = v2;
  Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(&v18);
  v12 = CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Insert(v11, v10, &v18);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v20);
  if ( v12 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v12, 0x165u, 0);
    goto LABEL_19;
  }
  if ( GetCurrentThreadId() == CManipulationManager::s_dwManipulationThreadId && a2 )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        MANIPULATION_FRAME_QUEUED,
        v7,
        *v5);
    CManipulationManager::OnInput(a2);
    goto LABEL_10;
  }
  if ( SetEvent(hEvent) )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
      McTemplateU0qq_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        MANIPULATION_FRAME_QUEUED,
        v7,
        *((unsigned int *)a1 + 37));
    goto LABEL_10;
  }
  v14 = (unsigned int *)((char *)a1 + 148);
  CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Remove(&CManipulationManager::s_InputQueue, &v18, 0, 0);
  Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(&v18);
  v5 = (unsigned int *)((char *)a1 + 148);
LABEL_14:
  v18 = (struct CManipulationFrame *)CManipulationManager::s_rwPointerBufferLock;
  CReadWriteLock::AcquireExclusive((CReadWriteLock *)CManipulationManager::s_rwPointerBufferLock);
  v15 = *v14;
  v16 = &CManipulationManager::s_rgPointerIds;
  for ( i = 0; (unsigned int)i < (unsigned int)v15; v15 = *v5 )
  {
    *((_DWORD *)&CManipulationManager::s_rgPointerIds + i) = *((_DWORD *)a1 + 60 * (unsigned int)i + 41);
    i = (unsigned int)(i + 1);
  }
  if ( (*((_DWORD *)a1 + 43) & 0x180000) == 0 )
    SetManipulationInputTarget(*((unsigned int *)a1 + 42), 0, v15, &CManipulationManager::s_rgPointerIds, a1);
  CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(&v18, i, v15, v16);
LABEL_10:
  if ( v2 )
    (*(void (__fastcall **)(struct CManipulationFrame *))(*(_QWORD *)v2 + 8LL))(v2);
  return 1;
}

```

## disassembly

```asm
0x1801354e4  mov     [rsp-38h+arg_8], rbx
0x1801354e9  push    rbp
0x1801354ea  push    rsi
0x1801354eb  push    rdi
0x1801354ec  push    r12
0x1801354ee  push    r13
0x1801354f0  push    r14
0x1801354f2  push    r15
0x1801354f4  mov     rbp, rsp
0x1801354f7  sub     rsp, 30h
0x1801354fb  xor     r15d, r15d
0x1801354fe  mov     r13, rdx
0x180135501  mov     [rbp+arg_0], r15
0x180135505  mov     rsi, rcx
0x180135508  test    rcx, rcx
0x18013550b  jz      loc_1801355FC
0x180135511  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180135518  lea     r14, [rcx+94h]
0x18013551f  mov     rbx, [rcx+0F0h]
0x180135526  mov     r12d, [rcx+0A8h]
0x18013552d  jnz     loc_1801356CB
0x180135533  mov     r9d, [r14]; unsigned int
0x180135536  mov     r8d, r12d; unsigned int
0x180135539  mov     rdx, [rsi]; unsigned __int64
0x18013553c  mov     rcx, rbx; unsigned __int64
0x18013553f  call    ?QueueFrame@GestureTargeting@InputTraceLogging@@SAX_K0KK@Z; InputTraceLogging::GestureTargeting::QueueFrame(unsigned __int64,unsigned __int64,ulong,ulong)
0x180135544  lea     rcx, [rbp+arg_0]
0x180135548  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x18013554d  lea     rdx, [rbp+arg_0]; struct CManipulationFrame **
0x180135551  mov     rcx, rsi; struct tagMANIPULATION_INPUT_INFO *
0x180135554  call    ?Create@CManipulationFrame@@SAJPEBUtagMANIPULATION_INPUT_INFO@@PEAPEAV1@@Z; CManipulationFrame::Create(tagMANIPULATION_INPUT_INFO const *,CManipulationFrame * *)
0x180135559  mov     r15, [rbp+arg_0]
0x18013555d  test    eax, eax
0x18013555f  js      loc_1801356A5
0x180135565  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180135569  mov     qword ptr [rbp+PerformanceCount], 0
0x180135571  call    cs:__imp_QueryPerformanceCounter
0x180135577  mov     rbx, qword ptr [rbp+PerformanceCount]
0x18013557b  call    ?IsVailContainer@@YA_NXZ; IsVailContainer(void)
0x180135580  neg     al
0x180135582  lea     rcx, [r15+20h]; struct tagTELEMETRY_POINTER_FRAME_TIMES *
0x180135586  sbb     rdx, rdx
0x180135589  and     edx, 48h
0x18013558c  mov     [rdx+r15+48h], rbx
0x180135591  call    ?QueueFrame@GestureTargeting@TelemetryDebug@InputTraceLogging@@SAXAEBUtagTELEMETRY_POINTER_FRAME_TIMES@@@Z; InputTraceLogging::TelemetryDebug::GestureTargeting::QueueFrame(tagTELEMETRY_POINTER_FRAME_TIMES const &)
0x180135596  lea     rcx, [rbp+arg_18]
0x18013559a  mov     [rbp+arg_18], r15
0x18013559e  call    ?InternalAddRef@?$ComPtr@UIInteractionContextWrapper@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(void)
0x1801355a3  lea     rcx, [rbp+arg_0]
0x1801355a7  mov     [rbp+arg_0], r15
0x1801355ab  call    ?InternalAddRef@?$ComPtr@UIInteractionContextWrapper@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInteractionContextWrapper>::InternalAddRef(void)
0x1801355b0  lea     r8, [rbp+arg_0]
0x1801355b4  call    ?Insert@?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@AEAAJ_NV?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@Z; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Insert(bool,Microsoft::WRL::ComPtr<CManipulationFrame>)
0x1801355b9  lea     rcx, [rbp+arg_18]
0x1801355bd  mov     ebx, eax
0x1801355bf  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x1801355c4  test    ebx, ebx
0x1801355c6  js      loc_180135740
0x1801355cc  call    cs:__imp_GetCurrentThreadId
0x1801355d2  cmp     eax, cs:?s_dwManipulationThreadId@CManipulationManager@@1KA; ulong CManipulationManager::s_dwManipulationThreadId
0x1801355d8  jz      loc_18013570B
0x1801355de  mov     rcx, cs:hEvent; hEvent
0x1801355e5  call    cs:__imp_SetEvent
0x1801355eb  test    eax, eax
0x1801355ed  jz      short loc_18013562A
0x1801355ef  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x1801355f6  jnz     loc_1801356E9
0x1801355fc  test    r15, r15
0x1801355ff  jz      short loc_180135610
0x180135601  mov     rdx, [r15]
0x180135604  mov     rcx, r15
0x180135607  mov     rax, [rdx+8]
0x18013560b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135610  mov     rbx, [rsp+30h+arg_8]
0x180135615  mov     eax, 1
0x18013561a  add     rsp, 30h
0x18013561e  pop     r15
0x180135620  pop     r14
0x180135622  pop     r13
0x180135624  pop     r12
0x180135626  pop     rdi
0x180135627  pop     rsi
0x180135628  pop     rbp
0x180135629  retn
0x18013562a  xor     r9d, r9d
0x18013562d  lea     rdx, [rbp+arg_0]
0x180135631  xor     r8d, r8d
0x180135634  lea     rcx, ?s_InputQueue@CManipulationManager@@1V?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@A; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>> CManipulationManager::s_InputQueue
0x18013563b  lea     rbx, [rsi+94h]
0x180135642  call    ?Remove@?$CQueue@V?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@@@AEAA?AV?$ComPtr@VCManipulationFrame@@@WRL@Microsoft@@_NPEAI@Z; CQueue<Microsoft::WRL::ComPtr<CManipulationFrame>>::Remove(bool,uint *)
0x180135647  lea     rcx, [rbp+arg_0]
0x18013564b  call    ?InternalRelease@?$ComPtr@VCBrushRenderingGraph@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CBrushRenderingGraph>::InternalRelease(void)
0x180135650  mov     r14, rbx
0x180135653  lea     rcx, ?s_rwPointerBufferLock@CManipulationManager@@1VCReadWriteLock@@A; this
0x18013565a  mov     [rbp+arg_0], rcx
0x18013565e  call    ?AcquireExclusive@CReadWriteLock@@QEAAXXZ; CReadWriteLock::AcquireExclusive(void)
0x180135663  mov     r8d, [rbx]
0x180135666  lea     r9, ?s_rgPointerIds@CManipulationManager@@1PAIA; uint near * CManipulationManager::s_rgPointerIds
0x18013566d  xor     edx, edx
0x18013566f  test    r8d, r8d
0x180135672  jnz     loc_1802A6DE6
0x180135678  test    dword ptr [rsi+0ACh], 180000h
0x180135682  jnz     short loc_180135697
0x180135684  mov     ecx, [rsi+0A8h]
0x18013568a  xor     edx, edx
0x18013568c  mov     qword ptr [rsp+30h+var_10], rsi
0x180135691  call    cs:__imp_SetManipulationInputTarget
0x180135697  lea     rcx, [rbp+arg_0]
0x18013569b  call    ??1?$CWriteGuard@VCReadWriteLock@@@@QEAA@XZ; CWriteGuard<CReadWriteLock>::~CWriteGuard<CReadWriteLock>(void)
0x1801356a0  jmp     loc_1801355FC
0x1801356a5  mov     [rsp+30h+var_8], 0; void *
0x1801356ae  mov     r9d, eax; int
0x1801356b1  mov     [rsp+30h+var_10], 15Dh; unsigned int
0x1801356b9  xor     edx, edx; int *
0x1801356bb  xor     r8d, r8d; unsigned int
0x1801356be  lea     ecx, [rdx+14h]; unsigned int
0x1801356c1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801356c6  mov     rbx, r14
0x1801356c9  jmp     short loc_180135653
0x1801356cb  mov     r9d, [r14]
0x1801356ce  lea     rdx, MANIPULATION_FRAME_RECEIVED
0x1801356d5  mov     r8d, r12d
0x1801356d8  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801356df  call    McTemplateU0qq_EventWriteTransfer
0x1801356e4  jmp     loc_180135533
0x1801356e9  mov     r9d, [rsi+94h]
0x1801356f0  lea     rdx, MANIPULATION_FRAME_QUEUED
0x1801356f7  mov     r8d, r12d
0x1801356fa  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180135701  call    McTemplateU0qq_EventWriteTransfer
0x180135706  jmp     loc_1801355FC
0x18013570b  test    r13, r13
0x18013570e  jz      loc_1801355DE
0x180135714  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x18013571b  jz      loc_1802A6DD8
0x180135721  mov     r9d, [r14]
0x180135724  lea     rdx, MANIPULATION_FRAME_QUEUED
0x18013572b  mov     r8d, r12d
0x18013572e  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180135735  call    McTemplateU0qq_EventWriteTransfer
0x18013573a  nop
0x18013573b  jmp     loc_1802A6DD8
0x180135740  mov     [rsp+30h+var_8], 0
0x180135749  mov     r9d, ebx
0x18013574c  mov     [rsp+30h+var_10], 165h
0x180135754  jmp     loc_1801356B9
0x1802a6dd8  mov     rcx, r13; this
0x1802a6ddb  call    ?OnInput@CManipulationManager@@IEAAXXZ; CManipulationManager::OnInput(void)
0x1802a6de0  nop
0x1802a6de1  jmp     loc_1801355FC
0x1802a6de6  mov     ecx, edx
0x1802a6de8  imul    rax, rcx, 0F0h
0x1802a6def  mov     eax, [rax+rsi+0A4h]
0x1802a6df6  mov     [r9+rdx*4], eax
0x1802a6dfa  inc     edx
0x1802a6dfc  mov     r8d, [r14]
0x1802a6dff  cmp     edx, r8d
0x1802a6e02  jb      short loc_1802A6DE6
0x1802a6e04  jmp     loc_180135678
```
