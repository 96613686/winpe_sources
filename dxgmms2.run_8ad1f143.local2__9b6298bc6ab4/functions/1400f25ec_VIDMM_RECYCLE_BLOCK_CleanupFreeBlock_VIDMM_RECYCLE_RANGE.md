# VIDMM_RECYCLE_BLOCK::CleanupFreeBlock(VIDMM_RECYCLE_RANGE *)

- ea: `0x1400f25ec`
- end: `0x1400f26b2`
- name: `?CleanupFreeBlock@VIDMM_RECYCLE_BLOCK@@QEAA_NPEAVVIDMM_RECYCLE_RANGE@@@Z`
- size: `198`
- prototype: `bool(VIDMM_RECYCLE_BLOCK *__hidden this, struct VIDMM_RECYCLE_RANGE *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400f210c`
- `0x1400f26b8`
- `0x1400f5dd8`
- `0x1401167b8`

## callees

- `0x1400f0670`
- `0x1400f1ffc`
- `0x1400f25ec`

## import_xrefs

- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f264b`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f269d`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f264b`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f269d`
- `watchdog!WdLogSingleEntry2` at `0x1400f262f`
- `watchdog!WdLogSingleEntry2` at `0x1400f2681`
- `watchdog!WdLogSingleEntry2` at `0x1400f262f`
- `watchdog!WdLogSingleEntry2` at `0x1400f2681`

## pseudocode

```c
char __fastcall VIDMM_RECYCLE_BLOCK::CleanupFreeBlock(VIDMM_RECYCLE_BLOCK *this, struct VIDMM_RECYCLE_RANGE *a2)
{
  __int64 v4; // rax
  struct VIDMM_RECYCLE_MULTIRANGE *v5; // rdi
  VIDMM_RECYCLE_HEAP_MGR *v6; // rsi
  __int64 v7; // rbp

  if ( *(_QWORD *)this != 1 )
    return 0;
  v4 = *((_QWORD *)this + 4);
  v5 = (struct VIDMM_RECYCLE_MULTIRANGE *)*((_QWORD *)a2 + 17);
  v6 = *(VIDMM_RECYCLE_HEAP_MGR **)(v4 + 8);
  v7 = v4 + 64;
  if ( v5 )
  {
    WdLogSingleEntry2(4, v5, 2);
    WdLogGlobalForLineNumber = 8471;
    RtlAvlRemoveNode(v7, v5);
    *((_DWORD *)v5 + 22) = 3;
    VIDMM_RECYCLE_HEAP_MGR::DestroyMultirange(v6, v5);
  }
  else
  {
    WdLogSingleEntry2(3, a2, 2);
    WdLogGlobalForLineNumber = 8359;
    RtlAvlRemoveNode(v7, a2);
    *((_DWORD *)a2 + 22) = 3;
  }
  VIDMM_RECYCLE_HEAP_MGR::DestroyRange(v6, a2);
  return 1;
}

```

## disassembly

```asm
0x1400f25ec  push    rbx
0x1400f25ee  push    rbp
0x1400f25ef  push    rsi
0x1400f25f0  push    rdi
0x1400f25f1  sub     rsp, 28h
0x1400f25f5  cmp     qword ptr [rcx], 1
0x1400f25f9  mov     rbx, rdx
0x1400f25fc  jz      short loc_1400F260A
0x1400f25fe  xor     al, al
0x1400f2600  add     rsp, 28h
0x1400f2604  pop     rdi
0x1400f2605  pop     rsi
0x1400f2606  pop     rbp
0x1400f2607  pop     rbx
0x1400f2608  retn
0x1400f260a  mov     rax, [rcx+20h]
0x1400f260e  mov     rdi, [rdx+88h]
0x1400f2615  mov     rsi, [rax+8]
0x1400f2619  lea     rbp, [rax+40h]
0x1400f261d  test    rdi, rdi
0x1400f2620  jz      short loc_1400F2678
0x1400f2622  mov     r8d, 2
0x1400f2628  mov     rdx, rdi
0x1400f262b  lea     ecx, [r8+2]
0x1400f262f  call    cs:__imp_WdLogSingleEntry2
0x1400f2636  nop     dword ptr [rax+rax+00h]
0x1400f263b  mov     rdx, rdi
0x1400f263e  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f2648  mov     rcx, rbp
0x1400f264b  call    cs:__imp_RtlAvlRemoveNode
0x1400f2652  nop     dword ptr [rax+rax+00h]
0x1400f2657  mov     rdx, rdi; struct VIDMM_RECYCLE_MULTIRANGE *
0x1400f265a  mov     dword ptr [rdi+58h], 3
0x1400f2661  mov     rcx, rsi; this
0x1400f2664  call    ?DestroyMultirange@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::DestroyMultirange(VIDMM_RECYCLE_MULTIRANGE *)
0x1400f2669  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x1400f266c  mov     rcx, rsi; this
0x1400f266f  call    ?DestroyRange@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::DestroyRange(VIDMM_RECYCLE_RANGE *)
0x1400f2674  mov     al, 1
0x1400f2676  jmp     short loc_1400F2600
0x1400f2678  mov     ecx, 3
0x1400f267d  lea     r8d, [rcx-1]
0x1400f2681  call    cs:__imp_WdLogSingleEntry2
0x1400f2688  nop     dword ptr [rax+rax+00h]
0x1400f268d  mov     rdx, rbx
0x1400f2690  mov     cs:WdLogGlobalForLineNumber, 20A7h
0x1400f269a  mov     rcx, rbp
0x1400f269d  call    cs:__imp_RtlAvlRemoveNode
0x1400f26a4  nop     dword ptr [rax+rax+00h]
0x1400f26a9  mov     dword ptr [rbx+58h], 3
0x1400f26b0  jmp     short loc_1400F2669
```
