# operator delete(void *)

- ea: `0x14000a10c`
- end: `0x14000a147`
- name: `??3@YAXPEAX@Z`
- size: `59`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `49`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400010c8`
- `0x1400010e8`
- `0x140001100`
- `0x1400012c0`
- `0x140001334`
- `0x140001354`
- `0x1400016f4`
- `0x140001950`
- `0x140001bac`
- `0x140001fc8`
- `0x14000202c`
- `0x140002168`
- `0x140004b08`
- `0x140006188`
- `0x140006a5c`
- `0x140006e3c`
- `0x140006e90`
- `0x140007338`
- `0x140007360`
- `0x140007504`
- `0x14000750c`
- `0x14000793c`
- `0x140008548`
- `0x140008ed0`
- `0x140009d24`
- `0x140009dc4`
- `0x14000a610`
- `0x14000a844`
- `0x14000a994`
- `0x14000bb50`
- `0x14000bd64`
- `0x14000cc64`
- `0x14000e748`
- `0x14000e930`
- `0x14000fc30`
- `0x1400102cc`
- `0x140010454`
- `0x140010690`
- `0x14001070c`
- `0x140010938`
- `0x140010b88`
- `0x14001209c`
- `0x1400121ec`
- `0x1400122e4`
- `0x140012e18`
- `0x140012e68`
- `0x140012eb8`
- `0x140012f08`
- `0x14001374c`

## callees

- `0x14000a10c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000a13a`
- `KERNEL32!HeapFree` at `0x14000a13a`
- `KERNEL32!GetProcessHeap` at `0x14000a125`
- `KERNEL32!GetProcessHeap` at `0x14000a125`

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
0x14000a10c  test    rcx, rcx
0x14000a10f  jz      short locret_14000A146
0x14000a111  push    rbx
0x14000a112  sub     rsp, 20h
0x14000a116  mov     rbx, rcx
0x14000a119  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000a120  test    rax, rax
0x14000a123  jnz     short loc_14000A132
0x14000a125  call    cs:__imp_GetProcessHeap
0x14000a12b  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000a132  mov     r8, rbx; lpMem
0x14000a135  xor     edx, edx; dwFlags
0x14000a137  mov     rcx, rax; hHeap
0x14000a13a  call    cs:__imp_HeapFree
0x14000a140  nop
0x14000a141  add     rsp, 20h
0x14000a145  pop     rbx
0x14000a146  retn
```
