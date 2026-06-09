# WxWaitForThreadpoolTimerCallbacks(_TP_TIMER *,int)

- ea: `0x180047a18`
- end: `0x180047a40`
- name: `?WxWaitForThreadpoolTimerCallbacks@@YAXPEAU_TP_TIMER@@H@Z`
- size: `40`
- prototype: `void __fastcall(struct _TP_TIMER *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180043508`

## callees

- `0x180047a18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180047a33`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180047a33`

## pseudocode

```c
void __fastcall WxWaitForThreadpoolTimerCallbacks(struct _TP_TIMER *a1)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800618B0 + 72) )
      WaitForThreadpoolTimerCallbacks(a1, 1);
  }
}

```

## disassembly

```asm
0x180047a18  sub     rsp, 28h
0x180047a1c  test    rcx, rcx
0x180047a1f  jz      short loc_180047A3B
0x180047a21  mov     rax, cs:qword_1800618B0
0x180047a28  cmp     byte ptr [rax+48h], 0
0x180047a2c  jnz     short loc_180047A3B
0x180047a2e  mov     edx, 1; fCancelPendingCallbacks
0x180047a33  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180047a39  jmp     short $+2
0x180047a3b  add     rsp, 28h
0x180047a3f  retn
0x180048015  push    rbp
0x180048017  sub     rsp, 20h
0x18004801b  mov     rbp, rdx
0x18004801e  mov     rax, [rcx]
0x180048021  xor     ecx, ecx
0x180048023  cmp     dword ptr [rax], 0C000000Dh
0x180048029  setz    cl
0x18004802c  mov     eax, ecx
0x18004802e  add     rsp, 20h
0x180048032  pop     rbp
0x180048033  retn
```
