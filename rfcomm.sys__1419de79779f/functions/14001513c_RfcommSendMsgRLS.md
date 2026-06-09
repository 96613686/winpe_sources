# RfcommSendMsgRLS

- ea: `0x14001513c`
- end: `0x1400152e5`
- name: `RfcommSendMsgRLS`
- size: `425`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001eec`

## callees

- `0x140003818`
- `0x140003bf4`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x14001513c`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400151a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015272`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015272`

## string_xrefs

- `0x14001520b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
__int64 __fastcall RfcommSendMsgRLS(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 v4; // rbx
  __int64 v9; // rax
  __int64 v10; // rbp
  unsigned int v11; // edi
  _QWORD *NextCmdLocked; // rsi
  int v13; // edx
  unsigned int v15; // [rsp+A0h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v15 = 4;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      69,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  *(_BYTE *)(v4 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 56));
  v9 = RfcommFrameAllocLockedEx(v4, (__int64 *)a1, 239, 20, 0, 0, &v15, a1 + 152, 0);
  v10 = v9;
  if ( v9 )
  {
    *(_WORD *)(v9 + 155) = 1363;
    *(_BYTE *)(v9 + 157) = (4 * *(_BYTE *)(a1 + 184)) | 3;
    v11 = 259;
    *(_BYTE *)(v9 + 158) = *a4;
    RefObj_AddRefEx(a2 + 24, 1296126534, 3279, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    *(_QWORD *)(v10 + 80) = a2;
    *(_QWORD *)(v10 + 96) = a2 + 680;
    *(_QWORD *)(v10 + 88) = a3;
    *(_DWORD *)(v10 + 104) = 0;
    *(_DWORD *)(v10 + 60) = 0;
  }
  else
  {
    v11 = -1073741670;
  }
  NextCmdLocked = RfcommGetNextCmdLocked(v4, a1);
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
  if ( NextCmdLocked )
  {
    RfcommStartTimer(*(_QWORD *)(v4 + 72));
    RfcommFrameWrite(v4, NextCmdLocked);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v13,
      3,
      70,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v11);
  return v11;
}

```

## disassembly

```asm
0x14001513c  mov     rax, rsp
0x14001513f  push    rbx
0x140015140  push    rbp
0x140015141  push    rsi
0x140015142  push    rdi
0x140015143  push    r12
0x140015145  push    r13
0x140015147  push    r14
0x140015149  push    r15
0x14001514b  sub     rsp, 58h
0x14001514f  mov     rbx, [rcx+38h]
0x140015153  mov     r12, r9
0x140015156  mov     r13, r8
0x140015159  mov     dword ptr [rax+8], 4
0x140015160  mov     r14, rdx
0x140015163  mov     rsi, rcx
0x140015166  lea     rax, WPP_RECORDER_INITIALIZED
0x14001516d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140015174  lea     rcx, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001517b  jz      short loc_14001519C
0x14001517d  mov     [rsp+98h+var_78], rcx
0x140015182  mov     r9d, 45h ; 'E'
0x140015188  mov     rcx, cs:WPP_GLOBAL_Control
0x14001518f  lea     r8d, [r9-42h]
0x140015193  mov     rcx, [rcx+40h]
0x140015197  call    WPP_RECORDER_SF_
0x14001519c  lea     rcx, [rbx+38h]; SpinLock
0x1400151a0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400151a7  nop     dword ptr [rax+rax+00h]
0x1400151ac  mov     [rbx+40h], al
0x1400151af  xor     edi, edi
0x1400151b1  mov     [rsp+98h+var_58], dil
0x1400151b6  mov     r9b, 14h
0x1400151b9  lea     rax, [rsi+98h]
0x1400151c0  mov     r8b, 0EFh
0x1400151c3  mov     [rsp+98h+var_60], rax
0x1400151c8  mov     rdx, rsi
0x1400151cb  lea     rax, [rsp+98h+arg_0]
0x1400151d3  mov     rcx, rbx
0x1400151d6  mov     [rsp+98h+var_68], rax
0x1400151db  mov     [rsp+98h+var_70], edi
0x1400151df  mov     byte ptr [rsp+98h+var_78], dil
0x1400151e4  call    RfcommFrameAllocLockedEx
0x1400151e9  mov     rbp, rax
0x1400151ec  test    rax, rax
0x1400151ef  jnz     short loc_1400151F8
0x1400151f1  mov     edi, 0C000009Ah
0x1400151f6  jmp     short loc_14001525D
0x1400151f8  mov     word ptr [rax+9Bh], 553h
0x140015201  lea     rcx, [r14+18h]
0x140015205  mov     al, [rsi+0B8h]
0x14001520b  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140015212  shl     al, 2
0x140015215  mov     edx, 4D415246h
0x14001521a  or      al, 3
0x14001521c  mov     r8d, 0CCFh
0x140015222  mov     [rbp+9Dh], al
0x140015228  mov     edi, 103h
0x14001522d  mov     al, [r12]
0x140015231  mov     [rbp+9Eh], al
0x140015237  call    RefObj_AddRefEx
0x14001523c  lea     rax, [r14+2A8h]
0x140015243  mov     [rbp+50h], r14
0x140015247  mov     [rbp+60h], rax
0x14001524b  mov     [rbp+58h], r13
0x14001524f  mov     dword ptr [rbp+68h], 0
0x140015256  mov     dword ptr [rbp+3Ch], 0
0x14001525d  mov     rdx, rsi
0x140015260  mov     rcx, rbx
0x140015263  call    RfcommGetNextCmdLocked
0x140015268  mov     dl, [rbx+40h]; NewIrql
0x14001526b  lea     rcx, [rbx+38h]; SpinLock
0x14001526f  mov     rsi, rax
0x140015272  call    cs:__imp_KeReleaseSpinLock
0x140015279  nop     dword ptr [rax+rax+00h]
0x14001527e  test    rsi, rsi
0x140015281  jz      short loc_140015297
0x140015283  mov     rcx, [rbx+48h]
0x140015287  call    RfcommStartTimer
0x14001528c  mov     rdx, rsi
0x14001528f  mov     rcx, rbx
0x140015292  call    RfcommFrameWrite
0x140015297  lea     rax, WPP_RECORDER_INITIALIZED
0x14001529e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400152a5  jz      short loc_1400152D1
0x1400152a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152ae  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x1400152b5  mov     r9d, 46h ; 'F'
0x1400152bb  mov     [rsp+98h+var_70], edi
0x1400152bf  mov     [rsp+98h+var_78], rax
0x1400152c4  mov     rcx, [rcx+40h]
0x1400152c8  lea     r8d, [r9-43h]
0x1400152cc  call    WPP_RECORDER_SF_d
0x1400152d1  mov     eax, edi
0x1400152d3  add     rsp, 58h
0x1400152d7  pop     r15
0x1400152d9  pop     r14
0x1400152db  pop     r13
0x1400152dd  pop     r12
0x1400152df  pop     rdi
0x1400152e0  pop     rsi
0x1400152e1  pop     rbp
0x1400152e2  pop     rbx
0x1400152e3  retn
```
