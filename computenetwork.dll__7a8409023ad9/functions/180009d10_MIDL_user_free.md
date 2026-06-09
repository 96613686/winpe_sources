# MIDL_user_free

- ea: `0x180009d10`
- end: `0x180009d37`
- name: `MIDL_user_free`
- size: `39`
- prototype: `void __stdcall(void *)`
- caller_count: `45`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041d4`
- `0x180005650`
- `0x180005720`
- `0x1800057b0`
- `0x180005870`
- `0x180005930`
- `0x1800059f0`
- `0x180005ab0`
- `0x180005b70`
- `0x180005c70`
- `0x180005d30`
- `0x180007d00`
- `0x180007e90`
- `0x180007f60`
- `0x180008030`
- `0x180008100`
- `0x1800081d0`
- `0x180008260`
- `0x1800082f0`
- `0x180008380`
- `0x180008410`
- `0x1800084a0`
- `0x180008670`
- `0x180008730`
- `0x1800087f0`
- `0x1800088b0`
- `0x1800088d0`
- `0x180008990`
- `0x180008a50`
- `0x180008b10`
- `0x180008bd0`
- `0x180008c90`
- `0x180008d50`
- `0x180008e10`
- `0x180008ed0`
- `0x180008f90`
- `0x180009090`
- `0x180009190`
- `0x180009290`
- `0x180009390`
- `0x180009490`
- `0x180009590`
- `0x180009730`
- `0x18000a40c`
- `0x18000e1b9`

## callees

- `0x180009d10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d1d`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x180009d10  test    rcx, rcx
0x180009d13  jz      short locret_180009D36
0x180009d15  push    rbx
0x180009d16  sub     rsp, 20h
0x180009d1a  mov     rbx, rcx
0x180009d1d  call    cs:__imp_GetProcessHeap
0x180009d23  mov     r8, rbx; lpMem
0x180009d26  xor     edx, edx; dwFlags
0x180009d28  mov     rcx, rax; hHeap
0x180009d2b  call    cs:__imp_HeapFree
0x180009d31  add     rsp, 20h
0x180009d35  pop     rbx
0x180009d36  retn
```
