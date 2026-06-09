# SmbPseFinalizeOrdinaryExchange

- ea: `0x140046120`
- end: `0x140046377`
- name: `SmbPseFinalizeOrdinaryExchange`
- size: `599`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x140029ff0`
- `0x14002cc54`
- `0x14002ff70`
- `0x140034700`
- `0x140034920`
- `0x140034ae0`
- `0x140034bf0`
- `0x1400367d0`
- `0x140036d40`
- `0x140039420`
- `0x14003bbd0`
- `0x14003bd40`
- `0x14003c3f8`
- `0x140044790`
- `0x140044c70`
- `0x140045d50`
- `0x14004cfa0`
- `0x14004d7f0`
- `0x1400508a0`

## callees

- `0x140009340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x140046120`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x140046260`
- `ntoskrnl!MmUnmapLockedPages` at `0x140046289`
- `ntoskrnl!MmUnmapLockedPages` at `0x140046260`
- `ntoskrnl!MmUnmapLockedPages` at `0x140046289`
- `ntoskrnl!DbgPrint` at `0x1400462d8`
- `ntoskrnl!DbgPrint` at `0x1400462d8`
- `ntoskrnl!IoFreeMdl` at `0x140046316`
- `ntoskrnl!IoFreeMdl` at `0x140046316`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046339`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046339`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140046355`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140046355`
- `rdbss!RxPostToWorkerThread` at `0x140046216`
- `rdbss!RxPostToWorkerThread` at `0x140046216`
- `rdbss!RxUnlockHeaderPages` at `0x140046230`
- `rdbss!RxUnlockHeaderPages` at `0x140046230`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400461f4`

## pseudocode

```c
char __fastcall SmbPseFinalizeOrdinaryExchange(unsigned __int8 *pContext)
{
  __int16 v1; // si
  unsigned __int32 v3; // edi
  struct _MDL *v5; // rcx
  struct _RX_CONTEXT *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx

  v1 = *((_WORD *)pContext + 192);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids);
  v3 = _InterlockedDecrement((volatile signed __int32 *)pContext + 1);
  if ( SmbCeTraceExchangeReferenceCount )
    DbgPrint(
      "Dereference Exchange %p Type(%ld) %s %ld %ld\n",
      pContext,
      *pContext,
      "SmbPseFinalizeOrdinaryExchange",
      1230,
      *((_DWORD *)pContext + 1));
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids, v3);
    return 0;
  }
  else
  {
    if ( *((_DWORD *)pContext + 27) || *((_DWORD *)pContext + 26) )
      __debugbreak();
    v5 = (struct _MDL *)*((_QWORD *)pContext + 47);
    if ( v5 && (v1 & 0x200) == 0 )
      IoFreeMdl(v5);
    if ( (pContext[384] & 0x20) != 0 )
    {
      RxUnlockHeaderPages(*((_QWORD *)pContext + 112));
      *((_WORD *)pContext + 192) &= ~0x20u;
      v7 = *((_QWORD *)pContext + 112);
      if ( (*(_BYTE *)(v7 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v7 + 24), *((PMDL *)pContext + 112));
    }
    if ( (pContext[384] & 8) != 0 )
    {
      v8 = *((_QWORD *)pContext + 113);
      if ( (*(_BYTE *)(v8 + 10) & 0x20) != 0 )
        MmUnmapLockedPages(*(PVOID *)(v8 + 24), *((PMDL *)pContext + 113));
    }
    if ( (v1 & 0x200) == 0 )
    {
      v9 = (void *)*((_QWORD *)pContext + 114);
      if ( v9 )
      {
        ExFreePoolWithTag(v9, 0);
        *((_QWORD *)pContext + 114) = 0;
      }
    }
    v6 = (struct _RX_CONTEXT *)*((_QWORD *)pContext + 117);
    if ( v6 )
      RxDereferenceAndDeleteRxContext_Real(v6);
    if ( (*((_DWORD *)pContext + 18) & 1) != 0 )
      SmbCeDissociateMidFromExchange(*((_QWORD *)pContext + 10), pContext);
    RxPostToWorkerThread(
      MRxSmbDeviceObject,
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 176),
      SmbCeDiscardExchangeWorkerThreadRoutine,
      pContext);
    return 1;
  }
}

```

## disassembly

```asm
0x140046120  push    rbx
0x140046122  push    rbp
0x140046123  push    rsi
0x140046124  push    rdi
0x140046125  sub     rsp, 38h
0x140046129  movzx   esi, word ptr [rcx+180h]
0x140046130  mov     rbx, rcx
0x140046133  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004613a  lea     rbp, WPP_GLOBAL_Control
0x140046141  cmp     rcx, rbp
0x140046144  jz      short loc_140046153
0x140046146  test    dword ptr [rcx+2Ch], 400h
0x14004614d  jnz     loc_14004629A
0x140046153  mov     edi, 0FFFFFFFFh
0x140046158  lock xadd [rbx+4], edi
0x14004615d  dec     edi
0x14004615f  cmp     cs:SmbCeTraceExchangeReferenceCount, 0
0x140046166  jnz     loc_1400462B4
0x14004616c  test    edi, edi
0x14004616e  jz      short loc_140046195
0x140046170  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140046177  cmp     rcx, rbp
0x14004617a  jz      short loc_140046189
0x14004617c  test    dword ptr [rcx+2Ch], 400h
0x140046183  jnz     loc_1400462E9
0x140046189  xor     al, al
0x14004618b  add     rsp, 38h
0x14004618f  pop     rdi
0x140046190  pop     rsi
0x140046191  pop     rbp
0x140046192  pop     rbx
0x140046193  retn
0x140046195  cmp     dword ptr [rbx+6Ch], 0
0x140046199  jnz     loc_140046306
0x14004619f  cmp     dword ptr [rbx+68h], 0
0x1400461a3  jnz     loc_140046306
0x1400461a9  mov     rcx, [rbx+178h]; Mdl
0x1400461b0  test    rcx, rcx
0x1400461b3  jnz     loc_14004630C
0x1400461b9  test    byte ptr [rbx+180h], 20h
0x1400461c0  jnz     short loc_140046229
0x1400461c2  test    byte ptr [rbx+180h], 8
0x1400461c9  jnz     loc_140046271
0x1400461cf  bt      esi, 9
0x1400461d3  jnb     loc_140046327
0x1400461d9  mov     rcx, [rbx+3A8h]; RxContext
0x1400461e0  test    rcx, rcx
0x1400461e3  jnz     loc_140046355
0x1400461e9  mov     eax, [rbx+48h]
0x1400461ec  test    al, 1
0x1400461ee  jnz     loc_140046366
0x1400461f4  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400461fb  lea     r8, [rbx+0B0h]; pWorkQueueItem
0x140046202  lea     r9, SmbCeDiscardExchangeWorkerThreadRoutine; Routine
0x140046209  mov     [rsp+58h+pContext], rbx; pContext
0x14004620e  mov     edx, 3; WorkQueueType
0x140046213  mov     rcx, [rcx]; pMRxDeviceObject
0x140046216  call    cs:__imp_RxPostToWorkerThread
0x14004621d  nop     dword ptr [rax+rax+00h]
0x140046222  mov     al, 1
0x140046224  jmp     loc_14004618B
0x140046229  mov     rcx, [rbx+380h]
0x140046230  call    cs:__imp_RxUnlockHeaderPages
0x140046237  nop     dword ptr [rax+rax+00h]
0x14004623c  mov     eax, 0FFDFh
0x140046241  and     [rbx+180h], ax
0x140046248  mov     rcx, [rbx+380h]
0x14004624f  test    byte ptr [rcx+0Ah], 20h
0x140046253  jz      loc_1400461C2
0x140046259  mov     rdx, rcx; MemoryDescriptorList
0x14004625c  mov     rcx, [rcx+18h]; BaseAddress
0x140046260  call    cs:__imp_MmUnmapLockedPages
0x140046267  nop     dword ptr [rax+rax+00h]
0x14004626c  jmp     loc_1400461C2
0x140046271  mov     rcx, [rbx+388h]
0x140046278  test    byte ptr [rcx+0Ah], 20h
0x14004627c  jz      loc_1400461CF
0x140046282  mov     rdx, rcx; MemoryDescriptorList
0x140046285  mov     rcx, [rcx+18h]; BaseAddress
0x140046289  call    cs:__imp_MmUnmapLockedPages
0x140046290  nop     dword ptr [rax+rax+00h]
0x140046295  jmp     loc_1400461CF
0x14004629a  mov     rcx, [rcx+18h]
0x14004629e  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x1400462a5  mov     edx, 1Eh
0x1400462aa  call    WPP_SF_
0x1400462af  jmp     loc_140046153
0x1400462b4  mov     eax, [rbx+4]
0x1400462b7  lea     r9, aSmbpsefinalize; "SmbPseFinalizeOrdinaryExchange"
0x1400462be  movzx   r8d, byte ptr [rbx]
0x1400462c2  lea     rcx, aDereferenceExc; "Dereference Exchange %p Type(%ld) %s %l"...
0x1400462c9  mov     [rsp+58h+var_30], eax
0x1400462cd  mov     rdx, rbx
0x1400462d0  mov     dword ptr [rsp+58h+pContext], 4CEh
0x1400462d8  call    cs:__imp_DbgPrint
0x1400462df  nop     dword ptr [rax+rax+00h]
0x1400462e4  jmp     loc_14004616C
0x1400462e9  mov     rcx, [rcx+18h]
0x1400462ed  lea     r8, WPP_33911492055d3ff4d7be76dabaca3f1d_Traceguids
0x1400462f4  mov     edx, 1Fh
0x1400462f9  mov     r9d, edi
0x1400462fc  call    WPP_SF_d
0x140046301  jmp     loc_140046189
0x140046306  int     3; Trap to Debugger
0x140046307  jmp     loc_1400461A9
0x14004630c  bt      esi, 9
0x140046310  jb      loc_1400461B9
0x140046316  call    cs:__imp_IoFreeMdl
0x14004631d  nop     dword ptr [rax+rax+00h]
0x140046322  jmp     loc_1400461B9
0x140046327  mov     rcx, [rbx+390h]; P
0x14004632e  test    rcx, rcx
0x140046331  jz      loc_1400461D9
0x140046337  xor     edx, edx; Tag
0x140046339  call    cs:__imp_ExFreePoolWithTag
0x140046340  nop     dword ptr [rax+rax+00h]
0x140046345  mov     qword ptr [rbx+390h], 0
0x140046350  jmp     loc_1400461D9
0x140046355  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x14004635c  nop     dword ptr [rax+rax+00h]
0x140046361  jmp     loc_1400461E9
0x140046366  mov     rcx, [rbx+50h]
0x14004636a  mov     rdx, rbx
0x14004636d  call    SmbCeDissociateMidFromExchange
0x140046372  jmp     loc_1400461F4
```
