# RfcommSendSABM

- ea: `0x14001552c`
- end: `0x140015680`
- name: `RfcommSendSABM`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001190c`
- `0x1400174a8`

## callees

- `0x140003818`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x14001552c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400155ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400155ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001561f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001561f`

## pseudocode

```c
__int64 __fastcall RfcommSendSABM(__int64 a1, __int64 a2)
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
      57,
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
  v7 = RfcommFrameAllocLockedEx(a1, (__int64 *)a2, 47, 0, v6, 0, &v12, v5, 0) == 0 ? 0xC000009A : 0;
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
      58,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v11);
  }
  return v7;
}

```

## disassembly

```asm
0x14001552c  mov     rax, rsp
0x14001552f  push    rbx
0x140015530  push    rbp
0x140015531  push    rsi
0x140015532  push    rdi
0x140015533  push    r13
0x140015535  push    r15
0x140015537  sub     rsp, 58h
0x14001553b  mov     rbx, rdx
0x14001553e  mov     dword ptr [rax+8], 0
0x140015545  mov     rdi, rcx
0x140015548  lea     r15, WPP_RECORDER_INITIALIZED
0x14001554f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140015556  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001555d  jz      short loc_140015592
0x14001555f  test    rdx, rdx
0x140015562  jz      short loc_14001556D
0x140015564  movzx   eax, byte ptr [rdx+0B8h]
0x14001556b  jmp     short loc_14001556F
0x14001556d  xor     eax, eax
0x14001556f  mov     rcx, cs:WPP_GLOBAL_Control
0x140015576  mov     r9d, 39h ; '9'
0x14001557c  mov     dword ptr [rsp+88h+var_60], eax
0x140015580  mov     [rsp+88h+var_68], r13
0x140015585  mov     rcx, [rcx+40h]
0x140015589  lea     r8d, [r9-36h]
0x14001558d  call    WPP_RECORDER_SF_d
0x140015592  lea     rax, [rdi+0C0h]
0x140015599  test    rbx, rbx
0x14001559c  lea     rsi, [rbx+98h]
0x1400155a3  lea     rcx, [rdi+38h]; SpinLock
0x1400155a7  cmovz   rsi, rax
0x1400155ab  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400155b2  nop     dword ptr [rax+rax+00h]
0x1400155b7  mov     [rdi+40h], al
0x1400155ba  test    rbx, rbx
0x1400155bd  jz      short loc_1400155C7
0x1400155bf  mov     al, [rbx+0B8h]
0x1400155c5  jmp     short loc_1400155C9
0x1400155c7  xor     al, al
0x1400155c9  mov     [rsp+88h+var_48], 0
0x1400155ce  lea     rcx, [rsp+88h+arg_0]
0x1400155d6  mov     [rsp+88h+var_50], rsi
0x1400155db  xor     r9d, r9d
0x1400155de  mov     [rsp+88h+var_58], rcx
0x1400155e3  mov     r8b, 2Fh ; '/'
0x1400155e6  mov     dword ptr [rsp+88h+var_60], 0
0x1400155ee  mov     rcx, rdi
0x1400155f1  mov     rdx, rbx
0x1400155f4  mov     byte ptr [rsp+88h+var_68], al
0x1400155f8  call    RfcommFrameAllocLockedEx
0x1400155fd  neg     rax
0x140015600  mov     rdx, rbx
0x140015603  mov     rcx, rdi
0x140015606  sbb     esi, esi
0x140015608  not     esi
0x14001560a  and     esi, 0C000009Ah
0x140015610  call    RfcommGetNextCmdLocked
0x140015615  mov     dl, [rdi+40h]; NewIrql
0x140015618  lea     rcx, [rdi+38h]; SpinLock
0x14001561c  mov     rbx, rax
0x14001561f  call    cs:__imp_KeReleaseSpinLock
0x140015626  nop     dword ptr [rax+rax+00h]
0x14001562b  test    rbx, rbx
0x14001562e  jz      short loc_140015644
0x140015630  mov     rcx, [rdi+48h]
0x140015634  call    RfcommStartTimer
0x140015639  mov     rdx, rbx
0x14001563c  mov     rcx, rdi
0x14001563f  call    RfcommFrameWrite
0x140015644  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001564b  jz      short loc_140015670
0x14001564d  mov     rcx, cs:WPP_GLOBAL_Control
0x140015654  mov     r9d, 3Ah ; ':'
0x14001565a  mov     dword ptr [rsp+88h+var_60], esi
0x14001565e  mov     [rsp+88h+var_68], r13
0x140015663  mov     rcx, [rcx+40h]
0x140015667  lea     r8d, [r9-37h]
0x14001566b  call    WPP_RECORDER_SF_d
0x140015670  mov     eax, esi
0x140015672  add     rsp, 58h
0x140015676  pop     r15
0x140015678  pop     r13
0x14001567a  pop     rdi
0x14001567b  pop     rsi
0x14001567c  pop     rbp
0x14001567d  pop     rbx
0x14001567e  retn
```
