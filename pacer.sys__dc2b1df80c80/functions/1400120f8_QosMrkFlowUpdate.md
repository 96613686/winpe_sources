# QosMrkFlowUpdate

- ea: `0x1400120f8`
- end: `0x140012146`
- name: `QosMrkFlowUpdate`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003ab0`

## callees

- `0x140004fe0`
- `0x14000516c`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140012123`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140012123`

## pseudocode

```c
__int64 __fastcall QosMrkFlowUpdate(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  ULONG CurrentProcessorNumber; // eax
  __int64 v6; // r8
  __int64 result; // rax

  *(_DWORD *)(a1 + 40) = *(_DWORD *)(a2 + 36);
  *(_QWORD *)(a1 + 80) = *(_QWORD *)(a2 + 48);
  v4 = a1 + 56;
  LOBYTE(a3) = *(_QWORD *)(v4 + 8) == 0;
  QosUtilSetTokenSpec(v4, a2, a3);
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  LOBYTE(v6) = 1;
  result = QosTimerGetCurrentTime(CurrentProcessorNumber, 0, v6);
  *(_QWORD *)(a1 + 48) = result;
  return result;
}

```

## disassembly

```asm
0x1400120f8  push    rbx
0x1400120fa  sub     rsp, 20h
0x1400120fe  mov     eax, [rdx+24h]
0x140012101  mov     rbx, rcx
0x140012104  mov     [rcx+28h], eax
0x140012107  mov     rax, [rdx+30h]
0x14001210b  mov     [rcx+50h], rax
0x14001210f  add     rcx, 38h ; '8'
0x140012113  cmp     qword ptr [rcx+8], 0
0x140012118  setz    r8b
0x14001211c  call    QosUtilSetTokenSpec
0x140012121  xor     ecx, ecx; ProcNumber
0x140012123  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001212a  nop     dword ptr [rax+rax+00h]
0x14001212f  mov     r8b, 1
0x140012132  xor     edx, edx
0x140012134  mov     ecx, eax
0x140012136  call    QosTimerGetCurrentTime
0x14001213b  mov     [rbx+30h], rax
0x14001213f  add     rsp, 20h
0x140012143  pop     rbx
0x140012144  retn
```
