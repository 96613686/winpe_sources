# CubicCongestionControlUpdateBlockedState

- ea: `0x140031d60`
- end: `0x140031ddc`
- name: `CubicCongestionControlUpdateBlockedState`
- size: `124`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140031440`
- `0x140031960`
- `0x1400319a0`
- `0x140031a40`
- `0x140031ae0`
- `0x140031b70`

## callees

- `0x140007ac0`
- `0x140010820`
- `0x1400216cc`
- `0x1400217f0`
- `0x140030f10`
- `0x140031d60`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x140031dbd`
- `HAL!KeQueryPerformanceCounter` at `0x140031dbd`

## pseudocode

```c
char __fastcall CubicCongestionControlUpdateBlockedState(__int64 a1, char a2)
{
  __int64 v2; // rdi
  LARGE_INTEGER PerformanceCounter; // rax

  v2 = a1 - 2168;
  QuicConnLogOutFlowStats(a1 - 2168);
  if ( a2 == (unsigned __int8)CubicCongestionControlCanSend(a1) )
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
0x140031d60  mov     [rsp+arg_0], rbx
0x140031d65  mov     [rsp+arg_8], rsi
0x140031d6a  push    rdi
0x140031d6b  sub     rsp, 20h
0x140031d6f  lea     rdi, [rcx-878h]
0x140031d76  mov     rbx, rcx
0x140031d79  mov     rcx, rdi
0x140031d7c  mov     sil, dl
0x140031d7f  call    QuicConnLogOutFlowStats
0x140031d84  mov     rcx, rbx
0x140031d87  call    CubicCongestionControlCanSend
0x140031d8c  cmp     sil, al
0x140031d8f  jz      short loc_140031DA3
0x140031d91  mov     edx, 8
0x140031d96  mov     rcx, rdi
0x140031d99  test    sil, sil
0x140031d9c  jz      short loc_140031DB6
0x140031d9e  call    QuicConnAddOutFlowBlockedReason
0x140031da3  xor     al, al
0x140031da5  mov     rbx, [rsp+28h+arg_0]
0x140031daa  mov     rsi, [rsp+28h+arg_8]
0x140031daf  add     rsp, 20h
0x140031db3  pop     rdi
0x140031db4  retn
0x140031db6  call    QuicConnRemoveOutFlowBlockedReason
0x140031dbb  xor     ecx, ecx; PerformanceFrequency
0x140031dbd  call    cs:__imp_KeQueryPerformanceCounter
0x140031dc4  nop     dword ptr [rax+rax+00h]
0x140031dc9  mov     rcx, rax
0x140031dcc  call    QuicTimePlatToUs64
0x140031dd1  mov     [rdi+0D68h], rax
0x140031dd8  mov     al, 1
0x140031dda  jmp     short loc_140031DA5
```
