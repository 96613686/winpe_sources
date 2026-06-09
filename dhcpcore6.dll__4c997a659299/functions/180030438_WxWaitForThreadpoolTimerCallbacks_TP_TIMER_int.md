# WxWaitForThreadpoolTimerCallbacks(_TP_TIMER *,int)

- ea: `0x180030438`
- end: `0x180030467`
- name: `?WxWaitForThreadpoolTimerCallbacks@@YAXPEAU_TP_TIMER@@H@Z`
- size: `47`
- prototype: `void __fastcall(struct _TP_TIMER *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff14`

## callees

- `0x180030438`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180030453`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180030453`

## pseudocode

```c
void __fastcall WxWaitForThreadpoolTimerCallbacks(struct _TP_TIMER *a1)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800426A0 + 72) )
      WaitForThreadpoolTimerCallbacks(a1, 1);
  }
}

```

## disassembly

```asm
0x180030438  sub     rsp, 28h
0x18003043c  test    rcx, rcx
0x18003043f  jz      short loc_180030461
0x180030441  mov     rax, cs:qword_1800426A0
0x180030448  cmp     byte ptr [rax+48h], 0
0x18003044c  jnz     short loc_180030461
0x18003044e  mov     edx, 1; fCancelPendingCallbacks
0x180030453  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003045a  nop     dword ptr [rax+rax+00h]
0x18003045f  jmp     short $+2
0x180030461  add     rsp, 28h
0x180030465  retn
0x180030a36  push    rbp
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbp, rdx
0x180030a3f  mov     rax, [rcx]
0x180030a42  xor     ecx, ecx
0x180030a44  cmp     dword ptr [rax], 0C000000Dh
0x180030a4a  setz    cl
0x180030a4d  mov     eax, ecx
0x180030a4f  add     rsp, 20h
0x180030a53  pop     rbp
0x180030a54  retn
```
