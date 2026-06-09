# VctDereferenceEndpoint

- ea: `0x140013470`
- end: `0x14001352b`
- name: `VctDereferenceEndpoint`
- size: `187`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `18`
- callee_count: `2`
- tags: ``

## callers

- `0x1400125e0`
- `0x140012650`
- `0x140012840`
- `0x140012d10`
- `0x14001a950`
- `0x14002c7f0`
- `0x140031500`
- `0x140031940`
- `0x140035f90`
- `0x140038158`
- `0x140038770`
- `0x14003fbb0`
- `0x140044ae0`
- `0x1400461fc`
- `0x140050fe0`
- `0x140051b60`
- `0x14008d030`
- `0x1400956a0`

## callees

- `0x140013470`
- `0x140037fa4`

## import_xrefs

- `rdbss!RxDiagnosticTrace` at `0x140013499`
- `rdbss!RxDiagnosticTrace` at `0x140013499`
- `rdbss!RxPostToWorkerThread` at `0x140013511`
- `rdbss!RxPostToWorkerThread` at `0x140013511`

## pseudocode

```c
__int64 __fastcall VctDereferenceEndpoint(PVOID pContext)
{
  unsigned __int32 v2; // ebx

  RxDiagnosticTrace(
    *((_QWORD *)pContext + 2),
    16,
    "Deref %d->%d",
    *((_DWORD *)pContext + 2),
    *((_DWORD *)pContext + 2) - 1);
  v2 = _InterlockedDecrement((volatile signed __int32 *)pContext + 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_39c16dc859303064795977fd63584161_Traceguids,
      pContext,
      v2 + 1,
      v2);
  }
  if ( !v2 )
    RxPostToWorkerThread(
      *((PRDBSS_DEVICE_OBJECT *)pContext + 3),
      BackgroundWorkQueue,
      (PRX_WORK_QUEUE_ITEM)pContext + 1,
      (PRX_WORKERTHREAD_ROUTINE)VctpTearDownEndpoint,
      pContext);
  return v2;
}

```

## disassembly

```asm
0x140013470  mov     [rsp+arg_0], rbx
0x140013475  push    rdi
0x140013476  sub     rsp, 30h
0x14001347a  mov     r9d, [rcx+8]
0x14001347e  lea     r8, aDerefDD; "Deref %d->%d"
0x140013485  mov     rdi, rcx
0x140013488  mov     edx, 10h
0x14001348d  mov     rcx, [rcx+10h]
0x140013491  lea     eax, [r9-1]
0x140013495  mov     dword ptr [rsp+38h+pContext], eax
0x140013499  call    cs:__imp_RxDiagnosticTrace
0x1400134a0  nop     dword ptr [rax+rax+00h]
0x1400134a5  mov     ebx, 0FFFFFFFFh
0x1400134aa  lock xadd [rdi+8], ebx
0x1400134af  dec     ebx
0x1400134b1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400134b8  lea     rax, WPP_GLOBAL_Control
0x1400134bf  cmp     rcx, rax
0x1400134c2  jz      short loc_1400134F4
0x1400134c4  mov     eax, [rcx+2Ch]
0x1400134c7  test    al, 4
0x1400134c9  jz      short loc_1400134F4
0x1400134cb  cmp     byte ptr [rcx+29h], 4
0x1400134cf  jb      short loc_1400134F4
0x1400134d1  mov     rcx, [rcx+18h]
0x1400134d5  lea     eax, [rbx+1]
0x1400134d8  mov     edx, 1Bh
0x1400134dd  mov     [rsp+38h+var_10], ebx
0x1400134e1  mov     r9, rdi
0x1400134e4  mov     dword ptr [rsp+38h+pContext], eax
0x1400134e8  lea     r8, WPP_39c16dc859303064795977fd63584161_Traceguids
0x1400134ef  call    WPP_SF_qDD
0x1400134f4  test    ebx, ebx
0x1400134f6  jnz     short loc_14001351D
0x1400134f8  mov     rcx, [rdi+18h]; pMRxDeviceObject
0x1400134fc  lea     r8, [rdi+28h]; pWorkQueueItem
0x140013500  lea     r9, VctpTearDownEndpoint; Routine
0x140013507  mov     [rsp+38h+pContext], rdi; pContext
0x14001350c  mov     edx, 4; WorkQueueType
0x140013511  call    cs:__imp_RxPostToWorkerThread
0x140013518  nop     dword ptr [rax+rax+00h]
0x14001351d  mov     eax, ebx
0x14001351f  mov     rbx, [rsp+38h+arg_0]
0x140013524  add     rsp, 30h
0x140013528  pop     rdi
0x140013529  retn
```
