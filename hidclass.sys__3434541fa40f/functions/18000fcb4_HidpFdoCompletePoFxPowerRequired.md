# HidpFdoCompletePoFxPowerRequired

- ea: `0x18000fcb4`
- end: `0x18000fd52`
- name: `HidpFdoCompletePoFxPowerRequired`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fc90`

## callees

- `0x18000fcb4`
- `0x18000ff44`

## import_xrefs

- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x18000fd35`
- `ntoskrnl!PoFxReportDevicePoweredOn` at `0x18000fd35`

## pseudocode

```c
__int64 __fastcall HidpFdoCompletePoFxPowerRequired(_QWORD *a1, __int64 a2, __int64 a3)
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
      a1[84],
      4,
      9,
      54,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *a1);
  return PoFxReportDevicePoweredOn(a1[87], a2, a3);
}

```

## disassembly

```asm
0x18000fcb4  push    rbx
0x18000fcb6  sub     rsp, 50h
0x18000fcba  mov     rbx, rcx
0x18000fcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc4  lea     rax, WPP_GLOBAL_Control
0x18000fccb  cmp     rcx, rax
0x18000fcce  jz      short loc_18000FCD9
0x18000fcd0  test    dword ptr [rcx+2Ch], 100h
0x18000fcd7  jnz     short loc_18000FD48
0x18000fcd9  xor     dl, dl
0x18000fcdb  lea     rax, WPP_RECORDER_INITIALIZED
0x18000fce2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000fce9  setnz   r8b
0x18000fced  test    dl, dl
0x18000fcef  jnz     short loc_18000FCF6
0x18000fcf1  test    r8b, r8b
0x18000fcf4  jz      short loc_18000FD2E
0x18000fcf6  mov     rax, [rbx]
0x18000fcf9  mov     r9, [rbx+2A0h]
0x18000fd00  mov     rcx, [rcx+18h]
0x18000fd04  mov     [rsp+58h+var_18], rax
0x18000fd09  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000fd10  mov     [rsp+58h+var_20], rax
0x18000fd15  mov     [rsp+58h+var_28], 36h ; '6'
0x18000fd1c  mov     [rsp+58h+var_30], 9
0x18000fd24  mov     [rsp+58h+var_38], 4
0x18000fd29  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000fd2e  mov     rcx, [rbx+2B8h]
0x18000fd35  call    cs:__imp_PoFxReportDevicePoweredOn
0x18000fd3c  nop     dword ptr [rax+rax+00h]
0x18000fd41  add     rsp, 50h
0x18000fd45  pop     rbx
0x18000fd46  retn
0x18000fd48  cmp     byte ptr [rcx+29h], 4
0x18000fd4c  jb      short loc_18000FCD9
0x18000fd4e  mov     dl, 1
0x18000fd50  jmp     short loc_18000FCDB
```
