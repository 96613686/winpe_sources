# operator delete(void *)

- ea: `0x180072664`
- end: `0x18007269f`
- name: `??3@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `139`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001288`
- `0x180001ed4`
- `0x1800032fc`
- `0x18000b158`
- `0x18000b928`
- `0x18000b940`
- `0x18000b960`
- `0x18000ccbc`
- `0x18000dd30`
- `0x18000e1c0`
- `0x18000e698`
- `0x18000fda0`
- `0x18000ffd0`
- `0x180011430`
- `0x180011eb0`
- `0x180012300`
- `0x180012840`
- `0x180012b20`
- `0x180012d20`
- `0x180012f00`
- `0x180013da0`
- `0x180018ab0`
- `0x180018ac8`
- `0x180018bc0`
- `0x180019ba0`
- `0x18001bfc8`
- `0x18001c0f4`
- `0x18001c1d8`
- `0x18001c2b4`
- `0x18001d308`
- `0x18001ee60`
- `0x1800224d4`
- `0x1800225b0`
- `0x180022718`
- `0x180022dc4`
- `0x180024120`
- `0x18002413c`
- `0x18002415c`
- `0x1800242a8`
- `0x1800248c4`
- `0x180024914`
- `0x180024954`
- `0x180024c88`
- `0x180035184`
- `0x180040f74`
- `0x180042ea4`
- `0x180043098`
- `0x180049300`
- `0x18004bd30`
- `0x180051944`

## callees

- `0x180072664`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180072692`
- `KERNEL32!HeapFree` at `0x180072692`
- `KERNEL32!GetProcessHeap` at `0x18007267d`
- `KERNEL32!GetProcessHeap` at `0x18007267d`

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
0x180072664  test    rcx, rcx
0x180072667  jz      short locret_18007269E
0x180072669  push    rbx
0x18007266a  sub     rsp, 20h
0x18007266e  mov     rbx, rcx
0x180072671  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180072678  test    rax, rax
0x18007267b  jnz     short loc_18007268A
0x18007267d  call    cs:__imp_GetProcessHeap
0x180072683  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18007268a  mov     r8, rbx; lpMem
0x18007268d  xor     edx, edx; dwFlags
0x18007268f  mov     rcx, rax; hHeap
0x180072692  call    cs:__imp_HeapFree
0x180072698  nop
0x180072699  add     rsp, 20h
0x18007269d  pop     rbx
0x18007269e  retn
```
