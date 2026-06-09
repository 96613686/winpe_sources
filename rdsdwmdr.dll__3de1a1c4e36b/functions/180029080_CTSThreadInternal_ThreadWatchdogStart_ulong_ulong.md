# CTSThreadInternal::ThreadWatchdogStart(ulong,ulong)

- ea: `0x180029080`
- end: `0x1800290c1`
- name: `?ThreadWatchdogStart@CTSThreadInternal@@UEAAJKK@Z`
- size: `65`
- prototype: `__int64 __fastcall(CTSThreadInternal *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180029080`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800290b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800290b4`

## pseudocode

```c
__int64 __fastcall CTSThreadInternal::ThreadWatchdogStart(CTSThreadInternal *this, unsigned int a2, DWORD a3)
{
  struct _TP_TIMER *v3; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( !v3 )
    return 2147549183LL;
  pftDueTime = (struct _FILETIME)(-10000LL * a2);
  SetThreadpoolTimer(v3, &pftDueTime, a3, 0);
  return 0;
}

```

## disassembly

```asm
0x180029080  sub     rsp, 28h
0x180029084  mov     rcx, [rcx+38h]; pti
0x180029088  test    rcx, rcx
0x18002908b  jnz     short loc_180029094
0x18002908d  mov     eax, 8000FFFFh
0x180029092  jmp     short loc_1800290BC
0x180029094  mov     eax, edx
0x180029096  xor     r9d, r9d; msWindowLength
0x180029099  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800290a0  mov     rdx, rax
0x1800290a3  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800290a7  shr     rdx, 20h
0x1800290ab  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800290af  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800290b4  call    cs:__imp_SetThreadpoolTimer
0x1800290ba  xor     eax, eax
0x1800290bc  add     rsp, 28h
0x1800290c0  retn
```
