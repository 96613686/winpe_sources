# RfcommSendDMEx

- ea: `0x140014b10`
- end: `0x140014c5e`
- name: `RfcommSendDMEx`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001127c`
- `0x14001190c`
- `0x1400121d4`
- `0x140012590`
- `0x140012c60`
- `0x140018d08`

## callees

- `0x140003cb4`
- `0x140004b4c`
- `0x1400135cc`
- `0x140013abc`
- `0x140014b10`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b77`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014b77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014bfa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014bfa`

## string_xrefs

- `0x140014bd9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommSendDMEx(__int64 a1, char a2, char a3)
{
  __int64 v6; // rax
  __int64 v7; // rbp
  char v8; // si
  unsigned int v9; // edi
  int v10; // edx
  unsigned int v12; // [rsp+80h] [rbp+8h] BYREF

  v12 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      61,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      a2);
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v6 = RfcommFrameAllocLockedEx(a1, 0, 15, 0, a2, 0, &v12, a1 + 208, a3);
  v7 = v6;
  if ( v6 )
  {
    v9 = 0;
    v8 = 1;
    RefObj_AddRefEx(v6 + 24, 1346917442, 2882, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    v8 = 0;
    v9 = -1073741670;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v8 )
    RfcommFrameWrite(a1, v7);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      62,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v9);
  return v9;
}

```

## disassembly

```asm
0x140014b10  mov     rax, rsp
0x140014b13  mov     [rax+10h], rbx
0x140014b17  mov     [rax+18h], rbp
0x140014b1b  push    rsi
0x140014b1c  push    rdi
0x140014b1d  push    r13
0x140014b1f  push    r14
0x140014b21  push    r15
0x140014b23  sub     rsp, 50h
0x140014b27  mov     sil, r8b
0x140014b2a  movzx   edi, dl
0x140014b2d  mov     rbx, rcx
0x140014b30  mov     dword ptr [rax+8], 0
0x140014b37  lea     r15, WPP_RECORDER_INITIALIZED
0x140014b3e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140014b45  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014b4c  jz      short loc_140014B73
0x140014b4e  mov     [rax-48h], edi
0x140014b51  mov     r9d, 3Dh ; '='
0x140014b57  mov     [rax-50h], rcx
0x140014b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140014b62  mov     [rax-58h], r13
0x140014b66  lea     r8d, [r9-3Ah]
0x140014b6a  mov     rcx, [rcx+40h]
0x140014b6e  call    WPP_RECORDER_SF_qD
0x140014b73  lea     rcx, [rbx+38h]; SpinLock
0x140014b77  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014b7e  nop     dword ptr [rax+rax+00h]
0x140014b83  mov     [rsp+78h+var_38], sil
0x140014b88  xor     r9d, r9d
0x140014b8b  mov     [rbx+40h], al
0x140014b8e  mov     r8b, 0Fh
0x140014b91  lea     rax, [rbx+0D0h]
0x140014b98  xor     edx, edx
0x140014b9a  mov     [rsp+78h+var_40], rax
0x140014b9f  mov     rcx, rbx
0x140014ba2  lea     rax, [rsp+78h+arg_0]
0x140014baa  mov     [rsp+78h+var_48], rax
0x140014baf  mov     [rsp+78h+var_50], 0
0x140014bb7  mov     byte ptr [rsp+78h+var_58], dil
0x140014bbc  call    RfcommFrameAllocLockedEx
0x140014bc1  mov     rbp, rax
0x140014bc4  test    rax, rax
0x140014bc7  jnz     short loc_140014BD3
0x140014bc9  xor     sil, sil
0x140014bcc  mov     edi, 0C000009Ah
0x140014bd1  jmp     short loc_140014BF3
0x140014bd3  xor     edi, edi
0x140014bd5  lea     rcx, [rax+18h]
0x140014bd9  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140014be0  mov     edx, 50485442h
0x140014be5  mov     r8d, 0B42h
0x140014beb  mov     sil, 1
0x140014bee  call    RefObj_AddRefEx
0x140014bf3  mov     dl, [rbx+40h]; NewIrql
0x140014bf6  lea     rcx, [rbx+38h]; SpinLock
0x140014bfa  call    cs:__imp_KeReleaseSpinLock
0x140014c01  nop     dword ptr [rax+rax+00h]
0x140014c06  test    sil, sil
0x140014c09  jz      short loc_140014C16
0x140014c0b  mov     rdx, rbp
0x140014c0e  mov     rcx, rbx
0x140014c11  call    RfcommFrameWrite
0x140014c16  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140014c1d  jz      short loc_140014C42
0x140014c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c26  mov     r9d, 3Eh ; '>'
0x140014c2c  mov     [rsp+78h+var_50], edi
0x140014c30  mov     [rsp+78h+var_58], r13
0x140014c35  mov     rcx, [rcx+40h]
0x140014c39  lea     r8d, [r9-3Bh]
0x140014c3d  call    WPP_RECORDER_SF_d
0x140014c42  lea     r11, [rsp+78h+var_28]
0x140014c47  mov     eax, edi
0x140014c49  mov     rbx, [r11+38h]
0x140014c4d  mov     rbp, [r11+40h]
0x140014c51  mov     rsp, r11
0x140014c54  pop     r15
0x140014c56  pop     r14
0x140014c58  pop     r13
0x140014c5a  pop     rdi
0x140014c5b  pop     rsi
0x140014c5c  retn
```
