# operator delete(void *)

- ea: `0x180030568`
- end: `0x1800305a3`
- name: `??3@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `127`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800011d0`
- `0x180001360`
- `0x180001808`
- `0x180001d80`
- `0x180001e8c`
- `0x18000237c`
- `0x180002468`
- `0x180002694`
- `0x180002790`
- `0x180002930`
- `0x180002ae0`
- `0x180005688`
- `0x180005f50`
- `0x180005f74`
- `0x180005f9c`
- `0x180005fc4`
- `0x180006460`
- `0x1800064a8`
- `0x1800068a8`
- `0x180006b34`
- `0x180006d00`
- `0x1800087cc`
- `0x180008a04`
- `0x180008c90`
- `0x180008d84`
- `0x180009100`
- `0x1800099fc`
- `0x180009b34`
- `0x180009c6c`
- `0x180009df4`
- `0x180009ff4`
- `0x18000a384`
- `0x18000a3a4`
- `0x18000aacc`
- `0x18000ad6c`
- `0x18000af58`
- `0x18000b218`
- `0x18000b56c`
- `0x18000b5bc`
- `0x18000b610`
- `0x18000b664`
- `0x18000b794`
- `0x18000b8dc`
- `0x18000bc54`
- `0x18000c26c`
- `0x18000c588`
- `0x18000c80c`
- `0x18000c934`
- `0x18000d138`
- `0x18000d394`

## callees

- `0x180030568`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180030596`
- `KERNEL32!HeapFree` at `0x180030596`
- `KERNEL32!GetProcessHeap` at `0x180030581`
- `KERNEL32!GetProcessHeap` at `0x180030581`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
    if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
    }
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180030568  test    rcx, rcx
0x18003056b  jz      short locret_1800305A2
0x18003056d  push    rbx
0x18003056e  sub     rsp, 20h
0x180030572  mov     rbx, rcx
0x180030575  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003057c  test    rax, rax
0x18003057f  jnz     short loc_18003058E
0x180030581  call    cs:__imp_GetProcessHeap
0x180030587  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003058e  mov     r8, rbx; lpMem
0x180030591  xor     edx, edx; dwFlags
0x180030593  mov     rcx, rax; hHeap
0x180030596  call    cs:__imp_HeapFree
0x18003059c  nop
0x18003059d  add     rsp, 20h
0x1800305a1  pop     rbx
0x1800305a2  retn
```
