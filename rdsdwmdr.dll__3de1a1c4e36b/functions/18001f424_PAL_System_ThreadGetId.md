# PAL_System_ThreadGetId

- ea: `0x18001f424`
- end: `0x18001f449`
- name: `PAL_System_ThreadGetId`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180022b94`
- `0x1800234e0`
- `0x180025820`
- `0x180026720`
- `0x180027150`
- `0x180027bf4`
- `0x180027d30`

## callees

- `0x18001f424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f439`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadGetId(DWORD *a1)
{
  if ( !a1 )
    return 2147942487LL;
  *a1 = GetCurrentThreadId();
  return 0;
}

```

## disassembly

```asm
0x18001f424  push    rbx
0x18001f426  sub     rsp, 20h
0x18001f42a  mov     rbx, rcx
0x18001f42d  test    rcx, rcx
0x18001f430  jnz     short loc_18001F439
0x18001f432  mov     eax, 80070057h
0x18001f437  jmp     short loc_18001F443
0x18001f439  call    cs:__imp_GetCurrentThreadId
0x18001f43f  mov     [rbx], eax
0x18001f441  xor     eax, eax
0x18001f443  add     rsp, 20h
0x18001f447  pop     rbx
0x18001f448  retn
```
