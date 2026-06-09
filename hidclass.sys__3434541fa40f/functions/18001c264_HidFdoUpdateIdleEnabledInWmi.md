# HidFdoUpdateIdleEnabledInWmi

- ea: `0x18001c264`
- end: `0x18001c347`
- name: `HidFdoUpdateIdleEnabledInWmi`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18001c1e4`

## callees

- `0x18000ce08`
- `0x18001c264`
- `0x180025524`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18001c32f`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001c32f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001c2dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001c2dd`

## pseudocode

```c
bool __fastcall HidFdoUpdateIdleEnabledInWmi(__int64 a1, char a2)
{
  bool v4; // dl
  KIRQL v5; // al
  int v6; // r8d
  char v7; // bl
  KIRQL NewIrql; // [rsp+88h] [rbp+10h] BYREF

  v4 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qc(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *(_QWORD *)(a1 + 672));
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1792));
  v6 = *(_DWORD *)(a1 + 1756);
  v7 = v6;
  NewIrql = v5;
  *(_DWORD *)(a1 + 1756) = v6 & 0xFFFFFFF7 | (a2 != 0 ? 8 : 0);
  HidFdoRunTimePolicyEngine(a1, &NewIrql);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1792), NewIrql);
  return (v7 & 8) != 0;
}

```

## disassembly

```asm
0x18001c264  push    rbx
0x18001c266  push    rbp
0x18001c267  push    rsi
0x18001c268  push    rdi
0x18001c269  sub     rsp, 58h
0x18001c26d  mov     bpl, dl
0x18001c270  mov     rsi, rcx
0x18001c273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c27a  lea     rax, WPP_GLOBAL_Control
0x18001c281  cmp     rcx, rax
0x18001c284  jz      short loc_18001C299
0x18001c286  test    dword ptr [rcx+2Ch], 100h
0x18001c28d  jz      short loc_18001C299
0x18001c28f  cmp     byte ptr [rcx+29h], 4
0x18001c293  jb      short loc_18001C299
0x18001c295  mov     dl, 1
0x18001c297  jmp     short loc_18001C29B
0x18001c299  xor     dl, dl
0x18001c29b  lea     rax, WPP_RECORDER_INITIALIZED
0x18001c2a2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001c2a9  setnz   r8b
0x18001c2ad  test    dl, dl
0x18001c2af  jnz     short loc_18001C2B6
0x18001c2b1  test    r8b, r8b
0x18001c2b4  jz      short loc_18001C2D3
0x18001c2b6  mov     rax, [rsi]
0x18001c2b9  mov     r9, [rsi+2A0h]
0x18001c2c0  mov     rcx, [rcx+18h]
0x18001c2c4  mov     [rsp+78h+var_30], bpl
0x18001c2c9  mov     [rsp+78h+var_38], rax
0x18001c2ce  call    WPP_RECORDER_AND_TRACE_SF_qc
0x18001c2d3  lea     rdi, [rsi+700h]
0x18001c2da  mov     rcx, rdi; SpinLock
0x18001c2dd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001c2e4  nop     dword ptr [rax+rax+00h]
0x18001c2e9  mov     r8d, [rsi+6DCh]
0x18001c2f0  mov     rcx, rsi
0x18001c2f3  mov     ebx, r8d
0x18001c2f6  mov     [rsp+78h+NewIrql], al
0x18001c2fd  shr     ebx, 3
0x18001c300  and     bl, 1
0x18001c303  neg     bpl
0x18001c306  sbb     edx, edx
0x18001c308  and     r8d, 0FFFFFFF7h
0x18001c30c  and     edx, 8
0x18001c30f  or      edx, r8d
0x18001c312  mov     [rsi+6DCh], edx
0x18001c318  lea     rdx, [rsp+78h+NewIrql]
0x18001c320  call    HidFdoRunTimePolicyEngine
0x18001c325  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x18001c32c  mov     rcx, rdi; SpinLock
0x18001c32f  call    cs:__imp_KeReleaseSpinLock
0x18001c336  nop     dword ptr [rax+rax+00h]
0x18001c33b  mov     al, bl
0x18001c33d  add     rsp, 58h
0x18001c341  pop     rdi
0x18001c342  pop     rsi
0x18001c343  pop     rbp
0x18001c344  pop     rbx
0x18001c345  retn
```
