# StartTimerToDrainIgnoreList

- ea: `0x180012eac`
- end: `0x180012eeb`
- name: `StartTimerToDrainIgnoreList`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d60`
- `0x1800130a0`

## callees

- `0x18000be40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ed3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012ed3`

## pseudocode

```c
void __fastcall StartTimerToDrainIgnoreList(struct _TP_TIMER *a1)
{
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  pftDueTime = (struct _FILETIME)-600000000LL;
  SetThreadpoolTimer(a1, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x180012eac  sub     rsp, 38h
0x180012eb0  mov     rax, cs:__security_cookie
0x180012eb7  xor     rax, rsp
0x180012eba  mov     [rsp+38h+var_10], rax
0x180012ebf  xor     r9d, r9d; msWindowLength
0x180012ec2  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x180012ecb  xor     r8d, r8d; msPeriod
0x180012ece  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012ed3  call    cs:__imp_SetThreadpoolTimer
0x180012ed9  mov     rcx, [rsp+38h+var_10]
0x180012ede  xor     rcx, rsp; StackCookie
0x180012ee1  call    __security_check_cookie
0x180012ee6  add     rsp, 38h
0x180012eea  retn
```
