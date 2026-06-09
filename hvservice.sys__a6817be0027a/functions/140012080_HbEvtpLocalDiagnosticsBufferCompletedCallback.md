# HbEvtpLocalDiagnosticsBufferCompletedCallback

- ea: `0x140012080`
- end: `0x140012167`
- name: `HbEvtpLocalDiagnosticsBufferCompletedCallback`
- size: `231`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001600`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140012122`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140012122`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x1400120d2`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x1400120d2`

## string_xrefs

- `0x1400120a9`: `HbEvtpLocalDiagnosticsBufferCompletedCallback`
- `0x1400120fb`: `HbEvtpLocalDiagnosticsBufferCompletedCallback`
- `0x140012139`: `HbEvtpLocalDiagnosticsBufferCompletedCallback`

## pseudocode

```c
__int64 __fastcall HbEvtpLocalDiagnosticsBufferCompletedCallback(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v6; // rbx
  int v7; // eax

  v3 = qword_140009380;
  v4 = a3;
  v5 = 112LL * a3;
  v6 = *(_QWORD *)(v5 + qword_140009380);
  HbpTraceEvent(
    3,
    "HbEvtpLocalDiagnosticsBufferCompletedCallback",
    3653,
    "Finishing processing buffer %d (state %d); releasing it",
    a3,
    *(_DWORD *)(v6 + 44));
  *(_DWORD *)(v6 + 44) = 4;
  v7 = WinHvReleaseEventLogBuffer(1, (unsigned int)v4);
  HbpTraceEvent(
    3,
    "HbEvtpLocalDiagnosticsBufferCompletedCallback",
    3667,
    "Released buffer %d (status 0x%x), new state %d",
    v4,
    v7,
    *(_DWORD *)(*(_QWORD *)(v5 + v3) + 44LL));
  *(_DWORD *)(v5 + v3 + 88) = 0;
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)(qword_140009388 + 8 * v4));
  return HbpTraceEvent(
           3,
           "HbEvtpLocalDiagnosticsBufferCompletedCallback",
           3673,
           "Buffer %d released (state %d)",
           v4,
           *(_DWORD *)(*(_QWORD *)(v5 + v3) + 44LL));
}

```

## disassembly

```asm
0x140012080  push    rbx
0x140012082  push    rbp
0x140012083  push    rsi
0x140012084  push    rdi
0x140012085  sub     rsp, 48h
0x140012089  mov     rdi, cs:qword_140009380
0x140012090  mov     ebp, r8d
0x140012093  imul    rsi, rbp, 70h ; 'p'
0x140012097  mov     rbx, [rsi+rdi]
0x14001209b  mov     eax, [rbx+2Ch]
0x14001209e  lea     r9, aFinishingProce; "Finishing processing buffer %d (state %"...
0x1400120a5  mov     [rsp+68h+var_40], eax
0x1400120a9  lea     rdx, aHbevtplocaldia_1; "HbEvtpLocalDiagnosticsBufferCompletedCa"...
0x1400120b0  mov     r8d, 0E45h
0x1400120b6  mov     [rsp+68h+var_48], ebp
0x1400120ba  mov     ecx, 3
0x1400120bf  call    HbpTraceEvent
0x1400120c4  mov     edx, ebp
0x1400120c6  mov     dword ptr [rbx+2Ch], 4
0x1400120cd  mov     ecx, 1
0x1400120d2  call    cs:__imp_WinHvReleaseEventLogBuffer
0x1400120d9  nop     dword ptr [rax+rax+00h]
0x1400120de  mov     rcx, [rsi+rdi]
0x1400120e2  lea     r9, aReleasedBuffer; "Released buffer %d (status 0x%x), new s"...
0x1400120e9  mov     r8d, 0E53h
0x1400120ef  mov     edx, [rcx+2Ch]
0x1400120f2  mov     ecx, 3
0x1400120f7  mov     [rsp+68h+var_38], edx
0x1400120fb  lea     rdx, aHbevtplocaldia_1; "HbEvtpLocalDiagnosticsBufferCompletedCa"...
0x140012102  mov     [rsp+68h+var_40], eax
0x140012106  mov     [rsp+68h+var_48], ebp
0x14001210a  call    HbpTraceEvent
0x14001210f  mov     dword ptr [rsi+rdi+58h], 0
0x140012117  mov     rax, cs:qword_140009388
0x14001211e  lea     rcx, [rax+rbp*8]; RunRef
0x140012122  call    cs:__imp_ExReleaseRundownProtection
0x140012129  nop     dword ptr [rax+rax+00h]
0x14001212e  mov     rax, [rsi+rdi]
0x140012132  lea     r9, aBufferDRelease; "Buffer %d released (state %d)"
0x140012139  lea     rdx, aHbevtplocaldia_1; "HbEvtpLocalDiagnosticsBufferCompletedCa"...
0x140012140  mov     ecx, 3
0x140012145  mov     r8d, [rax+2Ch]
0x140012149  mov     [rsp+68h+var_40], r8d
0x14001214e  mov     r8d, 0E59h
0x140012154  mov     [rsp+68h+var_48], ebp
0x140012158  call    HbpTraceEvent
0x14001215d  add     rsp, 48h
0x140012161  pop     rdi
0x140012162  pop     rsi
0x140012163  pop     rbp
0x140012164  pop     rbx
0x140012165  retn
```
