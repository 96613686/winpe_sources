# EnableFlushTimer

- ea: `0x180017a18`
- end: `0x180017a69`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017c60`
- `0x180017cb0`

## callees

- `0x180017a18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a51`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180025CF0 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180017a18  sub     rsp, 28h
0x180017a1c  test    rcx, rcx
0x180017a1f  jz      short loc_180017A64
0x180017a21  mov     eax, cs:dword_180025CF0
0x180017a27  test    eax, eax
0x180017a29  jnz     short loc_180017A64
0x180017a2b  mov     eax, edx
0x180017a2d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180017a34  mov     rdx, rax
0x180017a37  shr     rdx, 20h
0x180017a3b  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180017a3f  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180017a43  mov     r9d, 1388h; msWindowLength
0x180017a49  xor     r8d, r8d; msPeriod
0x180017a4c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180017a51  call    cs:__imp_SetThreadpoolTimer
0x180017a57  jmp     short loc_180017A64
0x180017a59  mov     eax, 1
0x180017a5e  xchg    eax, cs:dword_180025CF0
0x180017a64  add     rsp, 28h
0x180017a68  retn
0x180018b65  push    rbp
0x180018b67  sub     rsp, 20h
0x180018b6b  mov     rbp, rdx
0x180018b6e  mov     rax, [rcx]
0x180018b71  xor     ecx, ecx
0x180018b73  cmp     dword ptr [rax], 0C000000Dh
0x180018b79  setz    cl
0x180018b7c  mov     eax, ecx
0x180018b7e  add     rsp, 20h
0x180018b82  pop     rbp
0x180018b83  retn
```
