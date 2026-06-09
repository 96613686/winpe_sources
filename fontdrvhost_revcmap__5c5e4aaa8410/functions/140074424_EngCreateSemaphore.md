# EngCreateSemaphore

- ea: `0x140074424`
- end: `0x14007445d`
- name: `EngCreateSemaphore`
- size: `57`
- prototype: `HSEMAPHORE __stdcall()`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400743ac`
- `0x14007c0f0`
- `0x14007cef0`
- `0x14007dc20`
- `0x140091200`

## callees

- `0x140074424`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14007444e`
- `KERNEL32!InitializeCriticalSection` at `0x14007444e`
- `ntdll!RtlAllocateHeap` at `0x14007443d`
- `ntdll!RtlAllocateHeap` at `0x14007443d`

## pseudocode

```c
HSEMAPHORE __stdcall EngCreateSemaphore()
{
  struct _RTL_CRITICAL_SECTION *Heap; // rax
  HSEMAPHORE v1; // rbx

  Heap = (struct _RTL_CRITICAL_SECTION *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x28u);
  v1 = (HSEMAPHORE)Heap;
  if ( Heap )
    InitializeCriticalSection(Heap);
  return v1;
}

```

## disassembly

```asm
0x140074424  push    rbx
0x140074426  sub     rsp, 20h
0x14007442a  mov     rcx, gs:60h
0x140074433  xor     edx, edx; Flags
0x140074435  mov     rcx, [rcx+30h]; HeapHandle
0x140074439  lea     r8d, [rdx+28h]; Size
0x14007443d  call    cs:__imp_RtlAllocateHeap
0x140074443  mov     rbx, rax
0x140074446  test    rax, rax
0x140074449  jz      short loc_140074454
0x14007444b  mov     rcx, rax; lpCriticalSection
0x14007444e  call    cs:__imp_InitializeCriticalSection
0x140074454  mov     rax, rbx
0x140074457  add     rsp, 20h
0x14007445b  pop     rbx
0x14007445c  retn
```
