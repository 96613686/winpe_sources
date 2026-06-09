# EnableFlushTimer

- ea: `0x18001e040`
- end: `0x18001e091`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800184c8`
- `0x180018870`

## callees

- `0x18001e040`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e079`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e079`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18002AFD8 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18001e040  sub     rsp, 28h
0x18001e044  test    rcx, rcx
0x18001e047  jz      short loc_18001E08C
0x18001e049  mov     eax, cs:dword_18002AFD8
0x18001e04f  test    eax, eax
0x18001e051  jnz     short loc_18001E08C
0x18001e053  mov     eax, edx
0x18001e055  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18001e05c  mov     rdx, rax
0x18001e05f  shr     rdx, 20h
0x18001e063  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18001e067  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001e06b  mov     r9d, 1388h; msWindowLength
0x18001e071  xor     r8d, r8d; msPeriod
0x18001e074  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001e079  call    cs:__imp_SetThreadpoolTimer
0x18001e07f  jmp     short loc_18001E08C
0x18001e081  mov     eax, 1
0x18001e086  xchg    eax, cs:dword_18002AFD8
0x18001e08c  add     rsp, 28h
0x18001e090  retn
0x18001f282  push    rbp
0x18001f284  sub     rsp, 20h
0x18001f288  mov     rbp, rdx
0x18001f28b  mov     rax, [rcx]
0x18001f28e  xor     ecx, ecx
0x18001f290  cmp     dword ptr [rax], 0C000000Dh
0x18001f296  setz    cl
0x18001f299  mov     eax, ecx
0x18001f29b  add     rsp, 20h
0x18001f29f  pop     rbp
0x18001f2a0  retn
```
