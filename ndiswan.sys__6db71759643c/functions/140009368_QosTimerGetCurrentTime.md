# QosTimerGetCurrentTime

- ea: `0x140009368`
- end: `0x1400093f4`
- name: `QosTimerGetCurrentTime`
- size: `140`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002974`
- `0x1400091d0`
- `0x1400093fc`
- `0x1400097f8`
- `0x140012480`
- `0x140012570`
- `0x140013080`
- `0x140013570`
- `0x140013ea0`
- `0x140013f48`
- `0x140014050`
- `0x1400143d0`
- `0x140014434`
- `0x140014568`
- `0x1400154bc`
- `0x14001554c`

## callees

- `0x140009368`
- `0x1400146b8`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140009383`
- `ntoskrnl!KfRaiseIrql` at `0x140009383`
- `ntoskrnl!KeLowerIrql` at `0x1400093db`
- `ntoskrnl!KeLowerIrql` at `0x1400093db`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009394`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140009394`

## pseudocode

```c
__int64 __fastcall QosTimerGetCurrentTime(ULONG CurrentProcessorNumber, char a2, char a3)
{
  KIRQL v3; // di
  __int64 *v7; // rbx
  __int64 v8; // rbx

  v3 = 0;
  if ( !a3 )
  {
    v3 = KfRaiseIrql(2u);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  }
  v7 = (__int64 *)(*(_QWORD *)QosgTimerTable + ((unsigned __int64)CurrentProcessorNumber << 7));
  if ( a2 || MEMORY[0xFFFFF78000000008] != v7[1] )
    QosTimerConvertPerformanceCounterToMicroseconds(
      *(_QWORD *)QosgTimerTable + ((unsigned __int64)CurrentProcessorNumber << 7),
      MEMORY[0xFFFFF78000000008]);
  v8 = *v7;
  if ( !a3 )
    KeLowerIrql(v3);
  return v8;
}

```

## disassembly

```asm
0x140009368  push    rbx
0x14000936a  push    rbp
0x14000936b  push    rsi
0x14000936c  push    rdi
0x14000936d  sub     rsp, 28h
0x140009371  xor     dil, dil
0x140009374  mov     sil, r8b
0x140009377  mov     bpl, dl
0x14000937a  mov     eax, ecx
0x14000937c  test    r8b, r8b
0x14000937f  jnz     short loc_1400093A0
0x140009381  mov     cl, 2; NewIrql
0x140009383  call    cs:__imp_KfRaiseIrql
0x14000938a  nop     dword ptr [rax+rax+00h]
0x14000938f  xor     ecx, ecx; ProcNumber
0x140009391  mov     dil, al
0x140009394  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000939b  nop     dword ptr [rax+rax+00h]
0x1400093a0  mov     rcx, cs:QosgTimerTable
0x1400093a7  mov     rdx, 0FFFFF78000000008h
0x1400093b1  mov     ebx, eax
0x1400093b3  shl     rbx, 7
0x1400093b7  add     rbx, [rcx]
0x1400093ba  mov     rdx, [rdx]
0x1400093bd  test    bpl, bpl
0x1400093c0  jnz     short loc_1400093C8
0x1400093c2  cmp     rdx, [rbx+8]
0x1400093c6  jz      short loc_1400093D0
0x1400093c8  mov     rcx, rbx
0x1400093cb  call    QosTimerConvertPerformanceCounterToMicroseconds
0x1400093d0  mov     rbx, [rbx]
0x1400093d3  test    sil, sil
0x1400093d6  jnz     short loc_1400093E7
0x1400093d8  mov     cl, dil; NewIrql
0x1400093db  call    cs:__imp_KeLowerIrql
0x1400093e2  nop     dword ptr [rax+rax+00h]
0x1400093e7  mov     rax, rbx
0x1400093ea  add     rsp, 28h
0x1400093ee  pop     rdi
0x1400093ef  pop     rsi
0x1400093f0  pop     rbp
0x1400093f1  pop     rbx
0x1400093f2  retn
```
