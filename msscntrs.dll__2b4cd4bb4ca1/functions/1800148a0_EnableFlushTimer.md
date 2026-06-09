# EnableFlushTimer

- ea: `0x1800148a0`
- end: `0x1800148f1`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180014a20`
- `0x180014a70`

## callees

- `0x1800148a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800148d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800148d9`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_1800222F0 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x1800148a0  sub     rsp, 28h
0x1800148a4  test    rcx, rcx
0x1800148a7  jz      short loc_1800148EC
0x1800148a9  mov     eax, cs:dword_1800222F0
0x1800148af  test    eax, eax
0x1800148b1  jnz     short loc_1800148EC
0x1800148b3  mov     eax, edx
0x1800148b5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800148bc  mov     rdx, rax
0x1800148bf  shr     rdx, 20h
0x1800148c3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800148c7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800148cb  mov     r9d, 1388h; msWindowLength
0x1800148d1  xor     r8d, r8d; msPeriod
0x1800148d4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800148d9  call    cs:__imp_SetThreadpoolTimer
0x1800148df  jmp     short loc_1800148EC
0x1800148e1  mov     eax, 1
0x1800148e6  xchg    eax, cs:dword_1800222F0
0x1800148ec  add     rsp, 28h
0x1800148f0  retn
0x180016e95  push    rbp
0x180016e97  sub     rsp, 20h
0x180016e9b  mov     rbp, rdx
0x180016e9e  mov     rax, [rcx]
0x180016ea1  xor     ecx, ecx
0x180016ea3  cmp     dword ptr [rax], 0C000000Dh
0x180016ea9  setz    cl
0x180016eac  mov     eax, ecx
0x180016eae  add     rsp, 20h
0x180016eb2  pop     rbp
0x180016eb3  retn
```
