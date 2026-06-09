# HidpFdoPoFxUpdateIdleTimeout

- ea: `0x18000d628`
- end: `0x18000d6dc`
- name: `HidpFdoPoFxUpdateIdleTimeout`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000ce08`

## callees

- `0x18000d628`
- `0x18000ddc8`

## import_xrefs

- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x18000d6c4`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x18000d6c4`

## pseudocode

```c
__int64 __fastcall HidpFdoPoFxUpdateIdleTimeout(_QWORD *a1, unsigned int a2, __int64 a3)
{
  __int64 v3; // rdi

  v3 = a2;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      a1[84],
      4,
      9,
      34,
      (__int64)WPP_5a2771af4cec3e744979769e1f191181_Traceguids,
      *a1,
      v3);
  return PoFxSetDeviceIdleTimeout(a1[87], 10000 * v3, a3);
}

```

## disassembly

```asm
0x18000d628  mov     [rsp+arg_0], rbx
0x18000d62d  push    rdi
0x18000d62e  sub     rsp, 50h
0x18000d632  mov     edi, edx
0x18000d634  mov     rbx, rcx
0x18000d637  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d63e  lea     rax, WPP_GLOBAL_Control
0x18000d645  cmp     rcx, rax
0x18000d648  jz      short loc_18000D65D
0x18000d64a  test    dword ptr [rcx+2Ch], 100h
0x18000d651  jz      short loc_18000D65D
0x18000d653  cmp     byte ptr [rcx+29h], 4
0x18000d657  jb      short loc_18000D65D
0x18000d659  mov     dl, 1
0x18000d65b  jmp     short loc_18000D65F
0x18000d65d  xor     dl, dl
0x18000d65f  lea     rax, WPP_RECORDER_INITIALIZED
0x18000d666  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000d66d  setnz   r8b
0x18000d671  test    dl, dl
0x18000d673  jnz     short loc_18000D67A
0x18000d675  test    r8b, r8b
0x18000d678  jz      short loc_18000D6B6
0x18000d67a  mov     rax, [rbx]
0x18000d67d  mov     r9, [rbx+2A0h]
0x18000d684  mov     rcx, [rcx+18h]
0x18000d688  mov     [rsp+58h+var_10], edi
0x18000d68c  mov     [rsp+58h+var_18], rax
0x18000d691  lea     rax, WPP_5a2771af4cec3e744979769e1f191181_Traceguids
0x18000d698  mov     [rsp+58h+var_20], rax
0x18000d69d  mov     [rsp+58h+var_28], 22h ; '"'
0x18000d6a4  mov     [rsp+58h+var_30], 9
0x18000d6ac  mov     [rsp+58h+var_38], 4
0x18000d6b1  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18000d6b6  mov     rcx, [rbx+2B8h]
0x18000d6bd  imul    rdx, rdi, 2710h
0x18000d6c4  call    cs:__imp_PoFxSetDeviceIdleTimeout
0x18000d6cb  nop     dword ptr [rax+rax+00h]
0x18000d6d0  mov     rbx, [rsp+58h+arg_0]
0x18000d6d5  add     rsp, 50h
0x18000d6d9  pop     rdi
0x18000d6da  retn
```
