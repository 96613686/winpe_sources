# EnableFlushTimer

- ea: `0x180007498`
- end: `0x1800074e9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007620`
- `0x180007670`

## callees

- `0x180007498`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800074d1`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18000D730 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180007498  sub     rsp, 28h
0x18000749c  test    rcx, rcx
0x18000749f  jz      short loc_1800074E4
0x1800074a1  mov     eax, cs:dword_18000D730
0x1800074a7  test    eax, eax
0x1800074a9  jnz     short loc_1800074E4
0x1800074ab  mov     eax, edx
0x1800074ad  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800074b4  mov     rdx, rax
0x1800074b7  shr     rdx, 20h
0x1800074bb  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800074bf  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800074c3  mov     r9d, 1388h; msWindowLength
0x1800074c9  xor     r8d, r8d; msPeriod
0x1800074cc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800074d1  call    cs:__imp_SetThreadpoolTimer
0x1800074d7  jmp     short loc_1800074E4
0x1800074d9  mov     eax, 1
0x1800074de  xchg    eax, cs:dword_18000D730
0x1800074e4  add     rsp, 28h
0x1800074e8  retn
0x1800087b6  push    rbp
0x1800087b8  sub     rsp, 20h
0x1800087bc  mov     rbp, rdx
0x1800087bf  mov     rax, [rcx]
0x1800087c2  xor     ecx, ecx
0x1800087c4  cmp     dword ptr [rax], 0C000000Dh
0x1800087ca  setz    cl
0x1800087cd  mov     eax, ecx
0x1800087cf  add     rsp, 20h
0x1800087d3  pop     rbp
0x1800087d4  retn
```
