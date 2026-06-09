# EnableFlushTimer

- ea: `0x18003ef58`
- end: `0x18003efa9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003f100`
- `0x18003f150`

## callees

- `0x18003ef58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ef91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ef91`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180060180 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18003ef58  sub     rsp, 28h
0x18003ef5c  test    rcx, rcx
0x18003ef5f  jz      short loc_18003EFA4
0x18003ef61  mov     eax, cs:dword_180060180
0x18003ef67  test    eax, eax
0x18003ef69  jnz     short loc_18003EFA4
0x18003ef6b  mov     eax, edx
0x18003ef6d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18003ef74  mov     rdx, rax
0x18003ef77  shr     rdx, 20h
0x18003ef7b  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18003ef7f  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18003ef83  mov     r9d, 1388h; msWindowLength
0x18003ef89  xor     r8d, r8d; msPeriod
0x18003ef8c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18003ef91  call    cs:__imp_SetThreadpoolTimer
0x18003ef97  jmp     short loc_18003EFA4
0x18003ef99  mov     eax, 1
0x18003ef9e  xchg    eax, cs:dword_180060180
0x18003efa4  add     rsp, 28h
0x18003efa8  retn
0x180041f48  push    rbp
0x180041f4a  sub     rsp, 20h
0x180041f4e  mov     rbp, rdx
0x180041f51  mov     rax, [rcx]
0x180041f54  xor     ecx, ecx
0x180041f56  cmp     dword ptr [rax], 0C000000Dh
0x180041f5c  setz    cl
0x180041f5f  mov     eax, ecx
0x180041f61  add     rsp, 20h
0x180041f65  pop     rbp
0x180041f66  retn
```
