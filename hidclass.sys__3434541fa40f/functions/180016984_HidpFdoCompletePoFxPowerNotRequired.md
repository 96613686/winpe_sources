# HidpFdoCompletePoFxPowerNotRequired

- ea: `0x180016984`
- end: `0x180016a36`
- name: `HidpFdoCompletePoFxPowerNotRequired`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016960`

## callees

- `0x18000ff44`
- `0x180016984`

## import_xrefs

- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x180016a23`
- `ntoskrnl!PoFxCompleteDevicePowerNotRequired` at `0x180016a23`

## pseudocode

```c
__int64 __fastcall HidpFdoCompletePoFxPowerNotRequired(__int64 a1, __int64 a2, __int64 a3)
{
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      *(_QWORD *)(a1 + 672),
      4,
      9,
      55,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *(_QWORD *)a1);
  _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 2184), 0, 1);
  *(_DWORD *)(a1 + 1768) |= 1u;
  return PoFxCompleteDevicePowerNotRequired(*(_QWORD *)(a1 + 696), a2, a3);
}

```

## disassembly

```asm
0x180016984  push    rbx
0x180016986  sub     rsp, 50h
0x18001698a  mov     rbx, rcx
0x18001698d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016994  lea     rax, WPP_GLOBAL_Control
0x18001699b  cmp     rcx, rax
0x18001699e  jz      short loc_1800169B3
0x1800169a0  test    dword ptr [rcx+2Ch], 100h
0x1800169a7  jz      short loc_1800169B3
0x1800169a9  cmp     byte ptr [rcx+29h], 4
0x1800169ad  jb      short loc_1800169B3
0x1800169af  mov     dl, 1
0x1800169b1  jmp     short loc_1800169B5
0x1800169b3  xor     dl, dl
0x1800169b5  lea     rax, WPP_RECORDER_INITIALIZED
0x1800169bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800169c3  setnz   r8b
0x1800169c7  test    dl, dl
0x1800169c9  jnz     short loc_1800169D0
0x1800169cb  test    r8b, r8b
0x1800169ce  jz      short loc_180016A08
0x1800169d0  mov     rax, [rbx]
0x1800169d3  mov     r9, [rbx+2A0h]
0x1800169da  mov     rcx, [rcx+18h]
0x1800169de  mov     [rsp+58h+var_18], rax
0x1800169e3  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x1800169ea  mov     [rsp+58h+var_20], rax
0x1800169ef  mov     [rsp+58h+var_28], 37h ; '7'
0x1800169f6  mov     [rsp+58h+var_30], 9
0x1800169fe  mov     [rsp+58h+var_38], 4
0x180016a03  call    WPP_RECORDER_AND_TRACE_SF_q
0x180016a08  xor     ecx, ecx
0x180016a0a  lea     eax, [rcx+1]
0x180016a0d  lock cmpxchg [rbx+888h], ecx
0x180016a15  or      dword ptr [rbx+6E8h], 1
0x180016a1c  mov     rcx, [rbx+2B8h]
0x180016a23  call    cs:__imp_PoFxCompleteDevicePowerNotRequired
0x180016a2a  nop     dword ptr [rax+rax+00h]
0x180016a2f  add     rsp, 50h
0x180016a33  pop     rbx
0x180016a34  retn
```
