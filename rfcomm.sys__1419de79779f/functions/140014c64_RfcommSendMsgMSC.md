# RfcommSendMsgMSC

- ea: `0x140014c64`
- end: `0x140014eae`
- name: `RfcommSendMsgMSC`
- size: `586`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001eec`
- `0x14000fc00`
- `0x14001291c`

## callees

- `0x140003818`
- `0x140003cb4`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x140014c64`
- `0x1400171e0`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014cfe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014cfe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014e36`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014e36`

## string_xrefs

- `0x140014dc9`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140014e1d`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`
- `0x140014cb2`: `command`

## pseudocode

```c
__int64 __fastcall RfcommSendMsgMSC(__int64 a1, __int64 a2, __int64 a3, char *a4, int a5)
{
  __int64 v5; // rdi
  char v9; // r12
  char v10; // bp
  _BYTE *v11; // rax
  __int64 NextCmdLocked; // rbx
  unsigned int v13; // esi
  char v14; // al
  int v15; // edx

  v5 = *(_QWORD *)(a1 + 56);
  v9 = 0;
  v10 = a5;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ss(WPP_GLOBAL_Control->DeviceExtension, (unsigned int)"generated", 3, 67);
  a5 = 4;
  *(_BYTE *)(v5 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 56));
  v11 = (_BYTE *)RfcommFrameAllocLockedEx(
                   v5,
                   (__int64 *)a1,
                   239,
                   56,
                   0,
                   v10 == 0,
                   (unsigned int *)&a5,
                   a1 + (-(__int64)(v10 != 0) & 0xFFFFFFFFFFFFFFF0uLL) + 168,
                   0);
  NextCmdLocked = (__int64)v11;
  if ( v11 )
  {
    v11[156] = 5;
    v13 = 259;
    v11[155] = v10 != 0 ? -29 : -31;
    v11[157] = (4 * *(_BYTE *)(a1 + 184)) | 3;
    if ( a4 )
      v14 = *a4;
    else
      v14 = -116;
    *(_BYTE *)(NextCmdLocked + 158) = v14 | 1;
    if ( a3 )
    {
      RefObj_AddRefEx(a2 + 24, 1296126534, 3181, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      *(_QWORD *)(NextCmdLocked + 80) = a2;
      *(_QWORD *)(NextCmdLocked + 96) = a2 + 680;
      *(_QWORD *)(NextCmdLocked + 88) = a3;
      *(_DWORD *)(NextCmdLocked + 104) = 0;
      *(_DWORD *)(NextCmdLocked + 60) = 0;
    }
    if ( v10 )
    {
      NextCmdLocked = RfcommGetNextCmdLocked(v5, a1);
      v9 = 1;
    }
    else
    {
      RefObj_AddRefEx(
        NextCmdLocked + 24,
        1346917442,
        3205,
        "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    }
  }
  else
  {
    v13 = -1073741670;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 56), *(_BYTE *)(v5 + 64));
  if ( NextCmdLocked )
  {
    if ( v9 )
      RfcommStartTimer(*(_QWORD *)(v5 + 72));
    RfcommFrameWrite(v5, NextCmdLocked);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      3,
      68,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      v13);
  return v13;
}

```

## disassembly

```asm
0x140014c64  mov     [rsp+arg_10], r8
0x140014c69  push    rbx
0x140014c6a  push    rbp
0x140014c6b  push    rsi
0x140014c6c  push    rdi
0x140014c6d  push    r12
0x140014c6f  push    r13
0x140014c71  push    r14
0x140014c73  push    r15
0x140014c75  sub     rsp, 58h
0x140014c79  mov     rdi, [rcx+38h]
0x140014c7d  mov     r15, r9
0x140014c80  mov     r13, rdx
0x140014c83  mov     r14, rcx
0x140014c86  xor     r12b, r12b
0x140014c89  mov     bpl, byte ptr [rsp+98h+arg_20]
0x140014c91  lea     rax, WPP_RECORDER_INITIALIZED
0x140014c98  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014c9f  jz      short loc_140014CEF
0x140014ca1  test    bpl, bpl
0x140014ca4  lea     rax, aResponse_0; "response"
0x140014cab  lea     rdx, aGenerated; "generated"
0x140014cb2  lea     rcx, aCommand; "command"
0x140014cb9  cmovz   rcx, rax
0x140014cbd  test    r9, r9
0x140014cc0  mov     [rsp+98h+var_68], rcx
0x140014cc5  lea     rax, aProvided; "provided"
0x140014ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cd3  mov     r9d, 43h ; 'C'
0x140014cd9  cmovz   rax, rdx
0x140014cdd  mov     [rsp+98h+var_70], rax
0x140014ce2  mov     rcx, [rcx+40h]
0x140014ce6  lea     r8d, [r9-40h]
0x140014cea  call    WPP_RECORDER_SF_ss
0x140014cef  lea     rcx, [rdi+38h]; SpinLock
0x140014cf3  mov     [rsp+98h+arg_20], 4
0x140014cfe  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014d05  nop     dword ptr [rax+rax+00h]
0x140014d0a  mov     [rsp+98h+var_58], r12b
0x140014d0f  mov     r9b, 38h ; '8'
0x140014d12  mov     [rdi+40h], al
0x140014d15  mov     r8b, 0EFh
0x140014d18  mov     al, bpl
0x140014d1b  mov     rdx, r14
0x140014d1e  neg     al
0x140014d20  sbb     rcx, rcx
0x140014d23  xor     eax, eax
0x140014d25  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140014d29  add     rcx, 0A8h
0x140014d30  add     rcx, r14
0x140014d33  mov     [rsp+98h+var_60], rcx
0x140014d38  test    bpl, bpl
0x140014d3b  lea     rcx, [rsp+98h+arg_20]
0x140014d43  mov     [rsp+98h+var_68], rcx
0x140014d48  setz    al
0x140014d4b  mov     dword ptr [rsp+98h+var_70], eax
0x140014d4f  mov     rcx, rdi
0x140014d52  mov     byte ptr [rsp+98h+var_78], r12b
0x140014d57  call    RfcommFrameAllocLockedEx
0x140014d5c  mov     rbx, rax
0x140014d5f  test    rax, rax
0x140014d62  jnz     short loc_140014D6E
0x140014d64  mov     esi, 0C000009Ah
0x140014d69  jmp     loc_140014E2F
0x140014d6e  mov     al, bpl
0x140014d71  mov     byte ptr [rbx+9Ch], 5
0x140014d78  neg     al
0x140014d7a  mov     esi, 103h
0x140014d7f  sbb     cl, cl
0x140014d81  and     cl, 2
0x140014d84  add     cl, 0E1h
0x140014d87  mov     [rbx+9Bh], cl
0x140014d8d  mov     al, [r14+0B8h]
0x140014d94  shl     al, 2
0x140014d97  or      al, 3
0x140014d99  mov     [rbx+9Dh], al
0x140014d9f  test    r15, r15
0x140014da2  jz      short loc_140014DA9
0x140014da4  mov     al, [r15]
0x140014da7  jmp     short loc_140014DAB
0x140014da9  mov     al, 8Ch
0x140014dab  mov     r15, [rsp+98h+arg_10]
0x140014db3  or      al, 1
0x140014db5  mov     [rbx+9Eh], al
0x140014dbb  test    r15, r15
0x140014dbe  jz      short loc_140014DFC
0x140014dc0  lea     rcx, [r13+18h]
0x140014dc4  mov     edx, 4D415246h
0x140014dc9  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140014dd0  mov     r8d, 0C6Dh
0x140014dd6  call    RefObj_AddRefEx
0x140014ddb  lea     rax, [r13+2A8h]
0x140014de2  mov     [rbx+50h], r13
0x140014de6  mov     [rbx+60h], rax
0x140014dea  mov     [rbx+58h], r15
0x140014dee  mov     dword ptr [rbx+68h], 0
0x140014df5  mov     dword ptr [rbx+3Ch], 0
0x140014dfc  test    bpl, bpl
0x140014dff  jz      short loc_140014E14
0x140014e01  mov     rdx, r14
0x140014e04  mov     rcx, rdi
0x140014e07  call    RfcommGetNextCmdLocked
0x140014e0c  mov     rbx, rax
0x140014e0f  mov     r12b, 1
0x140014e12  jmp     short loc_140014E2F
0x140014e14  lea     rcx, [rbx+18h]
0x140014e18  mov     edx, 50485442h
0x140014e1d  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140014e24  mov     r8d, 0C85h
0x140014e2a  call    RefObj_AddRefEx
0x140014e2f  mov     dl, [rdi+40h]; NewIrql
0x140014e32  lea     rcx, [rdi+38h]; SpinLock
0x140014e36  call    cs:__imp_KeReleaseSpinLock
0x140014e3d  nop     dword ptr [rax+rax+00h]
0x140014e42  test    rbx, rbx
0x140014e45  jz      short loc_140014E60
0x140014e47  test    r12b, r12b
0x140014e4a  jz      short loc_140014E55
0x140014e4c  mov     rcx, [rdi+48h]
0x140014e50  call    RfcommStartTimer
0x140014e55  mov     rdx, rbx
0x140014e58  mov     rcx, rdi
0x140014e5b  call    RfcommFrameWrite
0x140014e60  lea     rax, WPP_RECORDER_INITIALIZED
0x140014e67  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014e6e  jz      short loc_140014E9A
0x140014e70  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e77  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140014e7e  mov     r9d, 44h ; 'D'
0x140014e84  mov     dword ptr [rsp+98h+var_70], esi
0x140014e88  mov     [rsp+98h+var_78], rax
0x140014e8d  mov     rcx, [rcx+40h]
0x140014e91  lea     r8d, [r9-41h]
0x140014e95  call    WPP_RECORDER_SF_d
0x140014e9a  mov     eax, esi
0x140014e9c  add     rsp, 58h
0x140014ea0  pop     r15
0x140014ea2  pop     r14
0x140014ea4  pop     r13
0x140014ea6  pop     r12
0x140014ea8  pop     rdi
0x140014ea9  pop     rsi
0x140014eaa  pop     rbp
0x140014eab  pop     rbx
0x140014eac  retn
```
