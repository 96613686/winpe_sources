# PAL_System_CritSecTerminate

- ea: `0x140018690`
- end: `0x1400186bc`
- name: `PAL_System_CritSecTerminate`
- size: `44`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400107ac`
- `0x140042828`

## callees

- `0x140018690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400186a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400186a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400186ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400186ae`

## pseudocode

```c
__int64 __fastcall PAL_System_CritSecTerminate(struct _RTL_CRITICAL_SECTION *hMem)
{
  if ( !hMem )
    return 2147942487LL;
  DeleteCriticalSection(hMem);
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x140018690  push    rbx
0x140018692  sub     rsp, 20h
0x140018696  mov     rbx, rcx
0x140018699  test    rcx, rcx
0x14001869c  jnz     short loc_1400186A5
0x14001869e  mov     eax, 80070057h
0x1400186a3  jmp     short loc_1400186B6
0x1400186a5  call    cs:__imp_DeleteCriticalSection
0x1400186ab  mov     rcx, rbx; hMem
0x1400186ae  call    cs:__imp_LocalFree
0x1400186b4  xor     eax, eax
0x1400186b6  add     rsp, 20h
0x1400186ba  pop     rbx
0x1400186bb  retn
```
