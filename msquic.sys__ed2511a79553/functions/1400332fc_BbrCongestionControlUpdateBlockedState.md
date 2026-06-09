# BbrCongestionControlUpdateBlockedState

- ea: `0x1400332fc`
- end: `0x140033378`
- name: `BbrCongestionControlUpdateBlockedState`
- size: `124`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140032950`
- `0x140032ce0`
- `0x140032d20`
- `0x140032e80`

## callees

- `0x140007ac0`
- `0x140010820`
- `0x1400216cc`
- `0x1400217f0`
- `0x140032170`
- `0x1400332fc`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140033359`
- `HAL!KeQueryPerformanceCounter` at `0x140033359`

## pseudocode

```c
char __fastcall BbrCongestionControlUpdateBlockedState(__int64 a1, char a2)
{
  __int64 v2; // rdi
  LARGE_INTEGER PerformanceCounter; // rax

  v2 = a1 - 2168;
  QuicConnLogOutFlowStats(a1 - 2168);
  if ( a2 == (unsigned __int8)BbrCongestionControlCanSend(a1) )
    return 0;
  if ( a2 )
  {
    QuicConnAddOutFlowBlockedReason(v2, 8);
    return 0;
  }
  QuicConnRemoveOutFlowBlockedReason(v2, 8);
  PerformanceCounter = KeQueryPerformanceCounter(0);
  *(_QWORD *)(v2 + 3432) = ((__int64 (__fastcall *)(_QWORD))QuicTimePlatToUs64)((LARGE_INTEGER)PerformanceCounter.QuadPart);
  return 1;
}

```

## disassembly

```asm
0x1400332fc  mov     [rsp+arg_0], rbx
0x140033301  mov     [rsp+arg_8], rsi
0x140033306  push    rdi
0x140033307  sub     rsp, 20h
0x14003330b  lea     rdi, [rcx-878h]
0x140033312  mov     rbx, rcx
0x140033315  mov     rcx, rdi
0x140033318  mov     sil, dl
0x14003331b  call    QuicConnLogOutFlowStats
0x140033320  mov     rcx, rbx
0x140033323  call    BbrCongestionControlCanSend
0x140033328  cmp     sil, al
0x14003332b  jz      short loc_14003333F
0x14003332d  mov     edx, 8
0x140033332  mov     rcx, rdi
0x140033335  test    sil, sil
0x140033338  jz      short loc_140033352
0x14003333a  call    QuicConnAddOutFlowBlockedReason
0x14003333f  xor     al, al
0x140033341  mov     rbx, [rsp+28h+arg_0]
0x140033346  mov     rsi, [rsp+28h+arg_8]
0x14003334b  add     rsp, 20h
0x14003334f  pop     rdi
0x140033350  retn
0x140033352  call    QuicConnRemoveOutFlowBlockedReason
0x140033357  xor     ecx, ecx; PerformanceFrequency
0x140033359  call    cs:__imp_KeQueryPerformanceCounter
0x140033360  nop     dword ptr [rax+rax+00h]
0x140033365  mov     rcx, rax
0x140033368  call    QuicTimePlatToUs64
0x14003336d  mov     [rdi+0D68h], rax
0x140033374  mov     al, 1
0x140033376  jmp     short loc_140033341
```
