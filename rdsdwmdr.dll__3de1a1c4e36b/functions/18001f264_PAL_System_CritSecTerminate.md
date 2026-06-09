# PAL_System_CritSecTerminate

- ea: `0x18001f264`
- end: `0x18001f290`
- name: `PAL_System_CritSecTerminate`
- size: `44`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800171ec`
- `0x18002ad68`

## callees

- `0x18001f264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f279`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f279`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f282`

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
0x18001f264  push    rbx
0x18001f266  sub     rsp, 20h
0x18001f26a  mov     rbx, rcx
0x18001f26d  test    rcx, rcx
0x18001f270  jnz     short loc_18001F279
0x18001f272  mov     eax, 80070057h
0x18001f277  jmp     short loc_18001F28A
0x18001f279  call    cs:__imp_DeleteCriticalSection
0x18001f27f  mov     rcx, rbx; hMem
0x18001f282  call    cs:__imp_LocalFree
0x18001f288  xor     eax, eax
0x18001f28a  add     rsp, 20h
0x18001f28e  pop     rbx
0x18001f28f  retn
```
