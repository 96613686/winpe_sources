# EnableFlushTimer

- ea: `0x18000aac0`
- end: `0x18000ab11`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac70`
- `0x18000acc0`

## callees

- `0x18000aac0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aaf9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aaf9`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180012668 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18000aac0  sub     rsp, 28h
0x18000aac4  test    rcx, rcx
0x18000aac7  jz      short loc_18000AB0C
0x18000aac9  mov     eax, cs:dword_180012668
0x18000aacf  test    eax, eax
0x18000aad1  jnz     short loc_18000AB0C
0x18000aad3  mov     eax, edx
0x18000aad5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000aadc  mov     rdx, rax
0x18000aadf  shr     rdx, 20h
0x18000aae3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18000aae7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000aaeb  mov     r9d, 1388h; msWindowLength
0x18000aaf1  xor     r8d, r8d; msPeriod
0x18000aaf4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000aaf9  call    cs:__imp_SetThreadpoolTimer
0x18000aaff  jmp     short loc_18000AB0C
0x18000ab01  mov     eax, 1
0x18000ab06  xchg    eax, cs:dword_180012668
0x18000ab0c  add     rsp, 28h
0x18000ab10  retn
0x18000b57a  push    rbp
0x18000b57c  sub     rsp, 20h
0x18000b580  mov     rbp, rdx
0x18000b583  mov     rax, [rcx]
0x18000b586  xor     ecx, ecx
0x18000b588  cmp     dword ptr [rax], 0C000000Dh
0x18000b58e  setz    cl
0x18000b591  mov     eax, ecx
0x18000b593  add     rsp, 20h
0x18000b597  pop     rbp
0x18000b598  retn
```
