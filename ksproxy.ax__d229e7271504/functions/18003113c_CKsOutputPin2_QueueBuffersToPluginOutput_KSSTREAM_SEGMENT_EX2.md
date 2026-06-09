# CKsOutputPin2::QueueBuffersToPluginOutput(_KSSTREAM_SEGMENT_EX2 *)

- ea: `0x18003113c`
- end: `0x180031351`
- name: `?QueueBuffersToPluginOutput@CKsOutputPin2@@QEAAJPEAU_KSSTREAM_SEGMENT_EX2@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(CBaseList *this, CBaseList *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800306f0`

## callees

- `0x180003d60`
- `0x18000df50`
- `0x18000e400`
- `0x18000ef30`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18003113c`
- `0x180031d5c`
- `0x180031e14`
- `0x180045010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18003123e`
- `KERNEL32!SetEvent` at `0x18003123e`
- `KERNEL32!CreateEventW` at `0x180031196`
- `KERNEL32!CreateEventW` at `0x180031196`
- `KERNEL32!CloseHandle` at `0x18003130b`
- `KERNEL32!CloseHandle` at `0x18003130b`
- `KERNEL32!LeaveCriticalSection` at `0x1800312b8`
- `KERNEL32!LeaveCriticalSection` at `0x1800312b8`
- `KERNEL32!EnterCriticalSection` at `0x1800312d9`
- `KERNEL32!EnterCriticalSection` at `0x1800312d9`

## string_xrefs

- `0x180031179`: `CKsOutputPin2::QueueBuffersToPluginOutput`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::QueueBuffersToPluginOutput(CBaseList *this, CBaseList *a2)
{
  CBaseList::CNode *m_pFirst; // r13
  CBaseList **v5; // r14
  CBaseList *EventW; // rbp
  _QWORD *v7; // rsi
  int v8; // edi
  CBaseList **v9; // rax
  int v10; // eax
  CBaseList::CNode *v11; // rdx
  CBaseList *v12; // rcx
  struct _ASYNC_ITEM *v13; // r15

  m_pFirst = this[2].m_pFirst;
  v5 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
      "CKsOutputPin2::QueueBuffersToPluginOutput");
  EventW = (CBaseList *)CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v7 = 0;
    v8 = -2147467259;
    goto LABEL_17;
  }
  v7 = operator new(0x30u);
  if ( !v7 )
    goto LABEL_7;
  v9 = (CBaseList **)operator new(0x28u);
  v5 = v9;
  if ( !v9 )
    goto LABEL_7;
  v9[3] = EventW;
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 2) != 0 )
    McTemplateU0pi_EventWriteTransfer(
      &Microsoft_Windows_DirectShow_KernelSupport_Context,
      ProcessOutput_Start,
      a2[13].m_Cache.m_pHead[1].m_pObject,
      a2[13].m_Cache.m_pHead->m_pNext);
  v10 = ((__int64 (__fastcall *)(CBaseList::CNode *, CBaseList::CNode *, CBaseList **))this[28].m_pLast->m_pPrev[4].m_pObject)(
          this[28].m_pLast,
          a2[13].m_Cache.m_pHead,
          v5 + 3);
  v8 = v10;
  if ( v10 )
  {
    if ( v10 == -2147483638 )
    {
      v8 = 0;
    }
    else if ( v10 < 0 )
    {
      ((void (__fastcall *)(CBaseList::CNode *))a2->m_Cache.m_pHead->m_pPrev->m_pObject)(a2->m_Cache.m_pHead);
LABEL_17:
      operator delete(v7);
      operator delete(v5);
      if ( EventW )
        CloseHandle(EventW);
      return (unsigned int)v8;
    }
  }
  else
  {
    SetEvent(EventW);
  }
  *v5 = this;
  v5[1] = a2;
  v7[4] = CKsOutputPin2::AppQueueItem;
  v7[1] = 0;
  *v7 = 0;
  *((_BYTE *)v7 + 16) = 1;
  v7[3] = EventW;
  v7[5] = v5;
  if ( !CBaseList::AddTailI(this + 18, v7) )
  {
LABEL_7:
    v8 = -2147024882;
    goto LABEL_17;
  }
  v13 = (struct _ASYNC_ITEM *)CBaseList::GetI(*v5 + 18, (struct __POSITION *)(*v5)[18].m_pFirst);
  if ( v13 )
  {
    CBaseList::RemoveI(v12, v11);
    LeaveCriticalSection((LPCRITICAL_SECTION)&m_pFirst[17]);
    CAsyncItemHandler::QueueAsyncItem(*(CAsyncItemHandler **)&(*v5)[24].m_Cache.m_iCacheSize, v13);
    EnterCriticalSection((LPCRITICAL_SECTION)&m_pFirst[17]);
  }
  if ( v8 < 0 )
    goto LABEL_17;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003113c  push    rbx
0x18003113e  push    rbp
0x18003113f  push    rsi
0x180031140  push    rdi
0x180031141  push    r13
0x180031143  push    r14
0x180031145  push    r15
0x180031147  sub     rsp, 20h
0x18003114b  mov     r13, [rcx+50h]
0x18003114f  mov     r15, rdx
0x180031152  mov     rbx, rcx
0x180031155  xor     r14d, r14d
0x180031158  mov     rcx, cs:WPP_GLOBAL_Control
0x18003115f  lea     rax, WPP_GLOBAL_Control
0x180031166  cmp     rcx, rax
0x180031169  jz      short loc_18003118C
0x18003116b  cmp     byte ptr [rcx+19h], 2
0x18003116f  jb      short loc_18003118C
0x180031171  mov     rcx, [rcx+10h]
0x180031175  lea     edx, [r14+27h]
0x180031179  lea     r9, aCksoutputpin2Q; "CKsOutputPin2::QueueBuffersToPluginOutp"...
0x180031180  lea     r8, WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids
0x180031187  call    WPP_SF_s
0x18003118c  xor     r9d, r9d; lpName
0x18003118f  xor     r8d, r8d; bInitialState
0x180031192  xor     edx, edx; bManualReset
0x180031194  xor     ecx, ecx; lpEventAttributes
0x180031196  call    cs:__imp_CreateEventW
0x18003119d  nop     dword ptr [rax+rax+00h]
0x1800311a2  mov     rbp, rax
0x1800311a5  test    rax, rax
0x1800311a8  jnz     short loc_1800311B6
0x1800311aa  xor     esi, esi
0x1800311ac  mov     edi, 80004005h
0x1800311b1  jmp     loc_1800312E9
0x1800311b6  mov     ecx, 30h ; '0'; Size
0x1800311bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800311c0  mov     rsi, rax
0x1800311c3  test    rax, rax
0x1800311c6  jnz     short loc_1800311D2
0x1800311c8  mov     edi, 8007000Eh
0x1800311cd  jmp     loc_1800312E9
0x1800311d2  mov     ecx, 28h ; '('; Size
0x1800311d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800311dc  mov     r14, rax
0x1800311df  test    rax, rax
0x1800311e2  jz      short loc_1800311C8
0x1800311e4  mov     [rax+18h], rbp
0x1800311e8  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 2
0x1800311ef  jz      short loc_180031213
0x1800311f1  mov     r8, [r15+228h]
0x1800311f8  lea     rdx, ProcessOutput_Start
0x1800311ff  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x180031206  mov     r9, [r8+8]
0x18003120a  mov     r8, [r8+28h]
0x18003120e  call    McTemplateU0pi_EventWriteTransfer
0x180031213  mov     rcx, [rbx+468h]
0x18003121a  lea     r8, [r14+18h]
0x18003121e  mov     rdx, [r15+228h]
0x180031225  mov     rax, [rcx]
0x180031228  mov     rax, [rax+70h]
0x18003122c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031231  mov     edi, eax
0x180031233  test    eax, eax
0x180031235  jnz     loc_180031329
0x18003123b  mov     rcx, rbp; hEvent
0x18003123e  call    cs:__imp_SetEvent
0x180031245  nop     dword ptr [rax+rax+00h]
0x18003124a  mov     [r14], rbx
0x18003124d  lea     rax, ?AppQueueItem@CKsOutputPin2@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin2::AppQueueItem(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x180031254  mov     [r14+8], r15
0x180031258  lea     rcx, [rbx+2D0h]; this
0x18003125f  mov     rdx, rsi; void *
0x180031262  mov     [rsi+20h], rax
0x180031266  mov     qword ptr [rsi+8], 0
0x18003126e  mov     qword ptr [rsi], 0
0x180031275  mov     byte ptr [rsi+10h], 1
0x180031279  mov     [rsi+18h], rbp
0x18003127d  mov     [rsi+28h], r14
0x180031281  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x180031286  test    rax, rax
0x180031289  jz      loc_1800311C8
0x18003128f  mov     rcx, [r14]
0x180031292  add     rcx, 2D0h; this
0x180031299  mov     rdx, [rcx]; struct __POSITION *
0x18003129c  call    ?GetI@CBaseList@@IEBAPEAXPEAU__POSITION@@@Z; CBaseList::GetI(__POSITION *)
0x1800312a1  mov     r15, rax
0x1800312a4  test    rax, rax
0x1800312a7  jz      short loc_1800312E5
0x1800312a9  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x1800312ae  lea     rbx, [r13+198h]
0x1800312b5  mov     rcx, rbx; lpCriticalSection
0x1800312b8  call    cs:__imp_LeaveCriticalSection
0x1800312bf  nop     dword ptr [rax+rax+00h]
0x1800312c4  mov     rcx, [r14]
0x1800312c7  mov     rdx, r15; struct _ASYNC_ITEM *
0x1800312ca  mov     rcx, [rcx+3D8h]; this
0x1800312d1  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x1800312d6  mov     rcx, rbx; lpCriticalSection
0x1800312d9  call    cs:__imp_EnterCriticalSection
0x1800312e0  nop     dword ptr [rax+rax+00h]
0x1800312e5  test    edi, edi
0x1800312e7  jns     short loc_180031317
0x1800312e9  mov     edx, 30h ; '0'; unsigned __int64
0x1800312ee  mov     rcx, rsi; void *
0x1800312f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800312f6  mov     edx, 28h ; '('; unsigned __int64
0x1800312fb  mov     rcx, r14; void *
0x1800312fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180031303  test    rbp, rbp
0x180031306  jz      short loc_180031317
0x180031308  mov     rcx, rbp; hObject
0x18003130b  call    cs:__imp_CloseHandle
0x180031312  nop     dword ptr [rax+rax+00h]
0x180031317  mov     eax, edi
0x180031319  add     rsp, 20h
0x18003131d  pop     r15
0x18003131f  pop     r14
0x180031321  pop     r13
0x180031323  pop     rdi
0x180031324  pop     rsi
0x180031325  pop     rbp
0x180031326  pop     rbx
0x180031327  retn
0x180031329  cmp     eax, 8000000Ah
0x18003132e  jnz     short loc_180031337
0x180031330  xor     edi, edi
0x180031332  jmp     loc_18003124A
0x180031337  test    eax, eax
0x180031339  jns     loc_18003124A
0x18003133f  mov     rcx, [r15+20h]
0x180031343  mov     rax, [rcx]
0x180031346  mov     rax, [rax+10h]
0x18003134a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003134f  jmp     short loc_1800312E9
```
