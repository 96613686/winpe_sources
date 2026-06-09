# GetProcessExecutableHeap(void)

- ea: `0x180030528`
- end: `0x18003056f`
- name: `?GetProcessExecutableHeap@@YAPEAXXZ`
- size: `71`
- prototype: `void *(void)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006900`
- `0x180029b70`
- `0x1800405b0`

## callees

- `0x180030528`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x180030540`
- `KERNEL32!HeapCreate` at `0x180030540`
- `KERNEL32!HeapDestroy` at `0x18003055b`
- `KERNEL32!HeapDestroy` at `0x18003055b`

## pseudocode

```c
HANDLE GetProcessExecutableHeap(void)
{
  HANDLE result; // rax

  if ( !hHeap )
  {
    result = HeapCreate(0x40000u, 0, 0);
    if ( !result )
      return result;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hHeap, (signed __int64)result, 0) )
      HeapDestroy(result);
  }
  return hHeap;
}

```

## disassembly

```asm
0x180030528  sub     rsp, 28h
0x18003052c  cmp     cs:hHeap, 0
0x180030534  jnz     short loc_180030561
0x180030536  xor     r8d, r8d; dwMaximumSize
0x180030539  xor     edx, edx; dwInitialSize
0x18003053b  mov     ecx, 40000h; flOptions
0x180030540  call    cs:__imp_HeapCreate
0x180030546  mov     rcx, rax; hHeap
0x180030549  test    rax, rax
0x18003054c  jz      short loc_18003056D
0x18003054e  xor     eax, eax
0x180030550  lock cmpxchg cs:hHeap, rcx
0x180030559  jz      short loc_180030561
0x18003055b  call    cs:__imp_HeapDestroy
0x180030561  mov     rax, cs:hHeap
0x180030568  add     rsp, 28h
0x18003056c  retn
0x18003056d  jmp     short loc_180030568
```
