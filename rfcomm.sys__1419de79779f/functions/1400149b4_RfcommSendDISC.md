# RfcommSendDISC

- ea: `0x1400149b4`
- end: `0x140014b08`
- name: `RfcommSendDISC`
- size: `340`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018040`
- `0x140019cd0`

## callees

- `0x140003818`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x1400149b4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a33`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014aa7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014aa7`

## pseudocode

```c
__int64 __fastcall RfcommSendDISC(__int64 a1, __int64 a2)
{
  int v4; // eax
  __int64 v5; // rsi
  char v6; // al
  unsigned int v7; // esi
  _QWORD *NextCmdLocked; // rbx
  int v9; // edx
  __int64 v11; // [rsp+28h] [rbp-60h]
  unsigned int v12; // [rsp+90h] [rbp+8h] BYREF

  v12 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( a2 )
      v4 = *(unsigned __int8 *)(a2 + 184);
    else
      v4 = 0;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      59,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v4);
  }
  v5 = a2 + 152;
  if ( !a2 )
    v5 = a1 + 192;
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( a2 )
    v6 = *(_BYTE *)(a2 + 184);
  else
    v6 = 0;
  v7 = RfcommFrameAllocLockedEx(a1, (__int64 *)a2, 67, 0, v6, 0, &v12, v5, 0) == 0 ? 0xC000009A : 0;
  NextCmdLocked = RfcommGetNextCmdLocked(a1, a2);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( NextCmdLocked )
  {
    RfcommStartTimer(*(_QWORD *)(a1 + 72));
    RfcommFrameWrite((_QWORD *)a1, (__int64)NextCmdLocked);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v11) = v7;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      3,
      60,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v11);
  }
  return v7;
}

```

## disassembly

```asm
0x1400149b4  mov     rax, rsp
0x1400149b7  push    rbx
0x1400149b8  push    rbp
0x1400149b9  push    rsi
0x1400149ba  push    rdi
0x1400149bb  push    r13
0x1400149bd  push    r15
0x1400149bf  sub     rsp, 58h
0x1400149c3  mov     rbx, rdx
0x1400149c6  mov     dword ptr [rax+8], 0
0x1400149cd  mov     rdi, rcx
0x1400149d0  lea     r15, WPP_RECORDER_INITIALIZED
0x1400149d7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400149de  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400149e5  jz      short loc_140014A1A
0x1400149e7  test    rdx, rdx
0x1400149ea  jz      short loc_1400149F5
0x1400149ec  movzx   eax, byte ptr [rdx+0B8h]
0x1400149f3  jmp     short loc_1400149F7
0x1400149f5  xor     eax, eax
0x1400149f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400149fe  mov     r9d, 3Bh ; ';'
0x140014a04  mov     dword ptr [rsp+88h+var_60], eax
0x140014a08  mov     [rsp+88h+var_68], r13
0x140014a0d  mov     rcx, [rcx+40h]
0x140014a11  lea     r8d, [r9-38h]
0x140014a15  call    WPP_RECORDER_SF_d
0x140014a1a  lea     rax, [rdi+0C0h]
0x140014a21  test    rbx, rbx
0x140014a24  lea     rsi, [rbx+98h]
0x140014a2b  lea     rcx, [rdi+38h]; SpinLock
0x140014a2f  cmovz   rsi, rax
0x140014a33  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014a3a  nop     dword ptr [rax+rax+00h]
0x140014a3f  mov     [rdi+40h], al
0x140014a42  test    rbx, rbx
0x140014a45  jz      short loc_140014A4F
0x140014a47  mov     al, [rbx+0B8h]
0x140014a4d  jmp     short loc_140014A51
0x140014a4f  xor     al, al
0x140014a51  mov     [rsp+88h+var_48], 0
0x140014a56  lea     rcx, [rsp+88h+arg_0]
0x140014a5e  mov     [rsp+88h+var_50], rsi
0x140014a63  xor     r9d, r9d
0x140014a66  mov     [rsp+88h+var_58], rcx
0x140014a6b  mov     r8b, 43h ; 'C'
0x140014a6e  mov     dword ptr [rsp+88h+var_60], 0
0x140014a76  mov     rcx, rdi
0x140014a79  mov     rdx, rbx
0x140014a7c  mov     byte ptr [rsp+88h+var_68], al
0x140014a80  call    RfcommFrameAllocLockedEx
0x140014a85  neg     rax
0x140014a88  mov     rdx, rbx
0x140014a8b  mov     rcx, rdi
0x140014a8e  sbb     esi, esi
0x140014a90  not     esi
0x140014a92  and     esi, 0C000009Ah
0x140014a98  call    RfcommGetNextCmdLocked
0x140014a9d  mov     dl, [rdi+40h]; NewIrql
0x140014aa0  lea     rcx, [rdi+38h]; SpinLock
0x140014aa4  mov     rbx, rax
0x140014aa7  call    cs:__imp_KeReleaseSpinLock
0x140014aae  nop     dword ptr [rax+rax+00h]
0x140014ab3  test    rbx, rbx
0x140014ab6  jz      short loc_140014ACC
0x140014ab8  mov     rcx, [rdi+48h]
0x140014abc  call    RfcommStartTimer
0x140014ac1  mov     rdx, rbx
0x140014ac4  mov     rcx, rdi
0x140014ac7  call    RfcommFrameWrite
0x140014acc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140014ad3  jz      short loc_140014AF8
0x140014ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140014adc  mov     r9d, 3Ch ; '<'
0x140014ae2  mov     dword ptr [rsp+88h+var_60], esi
0x140014ae6  mov     [rsp+88h+var_68], r13
0x140014aeb  mov     rcx, [rcx+40h]
0x140014aef  lea     r8d, [r9-39h]
0x140014af3  call    WPP_RECORDER_SF_d
0x140014af8  mov     eax, esi
0x140014afa  add     rsp, 58h
0x140014afe  pop     r15
0x140014b00  pop     r13
0x140014b02  pop     rdi
0x140014b03  pop     rsi
0x140014b04  pop     rbp
0x140014b05  pop     rbx
0x140014b06  retn
```
