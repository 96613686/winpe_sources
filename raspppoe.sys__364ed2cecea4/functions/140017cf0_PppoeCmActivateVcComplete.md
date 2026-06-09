# PppoeCmActivateVcComplete

- ea: `0x140017cf0`
- end: `0x14001804b`
- name: `PppoeCmActivateVcComplete`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140002b4c`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400024dc`
- `0x140002e0c`
- `0x140017cf0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140017e33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f20`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001802f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017e33`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f20`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001802f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017f78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017f78`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017d88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017eca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fe1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017d88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017eca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fe1`
- `NDIS!NdisCmDispatchCallConnected` at `0x140017fd2`
- `NDIS!NdisCmDispatchCallConnected` at `0x140017fd2`
- `NDIS!NdisCmMakeCallComplete` at `0x140017ebb`
- `NDIS!NdisCmMakeCallComplete` at `0x140017ebb`

## pseudocode

```c
void __fastcall PppoeCmActivateVcComplete(unsigned int a1, __int64 a2)
{
  __int64 v4; // r14
  unsigned int v5; // ebx
  KIRQL v6; // dl
  int v7; // edi
  KIRQL v8; // dl
  KIRQL v9; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
  }
  if ( (a1 & 0x80000000) == 0 )
  {
    *(_BYTE *)(a2 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
    }
    *(_DWORD *)(a2 + 88) = *(_DWORD *)(a2 + 88) & 0xFFFFEFFB | 4;
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 24));
    *(_DWORD *)(a2 + 88) |= 0x6000u;
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 40));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
    }
    v4 = *(_QWORD *)(a2 + 176);
    if ( *(_BYTE *)(a2 + 76) )
    {
      if ( v4 )
        ExFreePoolWithTag(*(PVOID *)(a2 + 176), 0);
      v8 = *(_BYTE *)(a2 + 64);
      *(_QWORD *)(a2 + 176) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v8);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
      }
      NdisCmDispatchCallConnected(*(NDIS_HANDLE *)(a2 + 168));
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
      *(_DWORD *)(a2 + 88) |= 8u;
      *(_BYTE *)(a2 + 64) = v9;
      *(_DWORD *)(a2 + 72) = 8;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
      }
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 24));
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), *(_BYTE *)(a2 + 64));
    }
    else
    {
      *(_DWORD *)v4 |= 2u;
      v5 = 100 * *(_DWORD *)(a2 + 120);
      v6 = *(_BYTE *)(a2 + 64);
      v7 = *(_DWORD *)(a2 + 124);
      *(_DWORD *)(a2 + 72) = 8;
      v5 >>= 3;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v6);
      *(_DWORD *)(*(_QWORD *)(v4 + 8) + 32LL) = v5;
      *(_DWORD *)(*(_QWORD *)(v4 + 8) + 40LL) = v5;
      **(_DWORD **)(v4 + 8) = v5;
      *(_DWORD *)(*(_QWORD *)(v4 + 8) + 8LL) = v5;
      *(_DWORD *)(*(_QWORD *)(v4 + 8) + 24LL) = v7;
      *(_DWORD *)(*(_QWORD *)(v4 + 8) + 56LL) = v7;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
      }
      NdisCmMakeCallComplete(0, *(NDIS_HANDLE *)(a2 + 168), 0, 0, *(PCO_CALL_PARAMETERS *)(a2 + 176));
      *(_BYTE *)(a2 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
      *(_QWORD *)(a2 + 176) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
      }
      *(_DWORD *)(a2 + 88) |= 8u;
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 24));
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), *(_BYTE *)(a2 + 64));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a2);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu) )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
    }
    TpCmCallCleanup(a2, 0);
  }
}

```

## disassembly

```asm
0x140017cf0  push    rbx
0x140017cf2  push    rbp
0x140017cf3  push    rsi
0x140017cf4  push    rdi
0x140017cf5  push    r12
0x140017cf7  push    r14
0x140017cf9  push    r15
0x140017cfb  sub     rsp, 30h
0x140017cff  mov     rsi, rdx
0x140017d02  mov     r15d, ecx
0x140017d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d0c  lea     rdi, WPP_GLOBAL_Control
0x140017d13  lea     rbx, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140017d1a  cmp     rcx, rdi
0x140017d1d  jz      short loc_140017D40
0x140017d1f  bt      dword ptr [rcx+2Ch], 0Fh
0x140017d24  jnb     short loc_140017D40
0x140017d26  cmp     byte ptr [rcx+29h], 2
0x140017d2a  jb      short loc_140017D40
0x140017d2c  mov     rcx, [rcx+18h]
0x140017d30  mov     edx, 25h ; '%'
0x140017d35  mov     r9d, r15d
0x140017d38  mov     r8, rbx
0x140017d3b  call    WPP_SF_d
0x140017d40  test    r15d, r15d
0x140017d43  jns     short loc_140017D81
0x140017d45  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d4c  cmp     rcx, rdi
0x140017d4f  jz      short loc_140017D72
0x140017d51  bt      dword ptr [rcx+2Ch], 0Fh
0x140017d56  jnb     short loc_140017D72
0x140017d58  cmp     byte ptr [rcx+29h], 1
0x140017d5c  jb      short loc_140017D72
0x140017d5e  mov     rcx, [rcx+18h]
0x140017d62  mov     edx, 26h ; '&'
0x140017d67  mov     r9d, r15d
0x140017d6a  mov     r8, rbx
0x140017d6d  call    WPP_SF_d
0x140017d72  xor     edx, edx
0x140017d74  mov     rcx, rsi
0x140017d77  call    TpCmCallCleanup
0x140017d7c  jmp     loc_14001803B
0x140017d81  lea     rbp, [rsi+38h]
0x140017d85  mov     rcx, rbp; SpinLock
0x140017d88  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017d8f  nop     dword ptr [rax+rax+00h]
0x140017d94  mov     [rsi+40h], al
0x140017d97  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d9e  cmp     rcx, rdi
0x140017da1  jz      short loc_140017DC1
0x140017da3  bt      dword ptr [rcx+2Ch], 0Fh
0x140017da8  jnb     short loc_140017DC1
0x140017daa  cmp     byte ptr [rcx+29h], 2
0x140017dae  jb      short loc_140017DC1
0x140017db0  mov     rcx, [rcx+18h]
0x140017db4  mov     edx, 27h ; '''
0x140017db9  mov     r8, rbx
0x140017dbc  call    WPP_SF_
0x140017dc1  mov     eax, [rsi+58h]
0x140017dc4  btr     eax, 0Ch
0x140017dc8  or      eax, 4
0x140017dcb  mov     [rsi+58h], eax
0x140017dce  lock inc dword ptr [rsi+18h]
0x140017dd2  or      dword ptr [rsi+58h], 6000h
0x140017dd9  lock inc dword ptr [rsi+28h]
0x140017ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x140017de4  cmp     rcx, rdi
0x140017de7  jz      short loc_140017E07
0x140017de9  bt      dword ptr [rcx+2Ch], 0Fh
0x140017dee  jnb     short loc_140017E07
0x140017df0  cmp     byte ptr [rcx+29h], 2
0x140017df4  jb      short loc_140017E07
0x140017df6  mov     rcx, [rcx+18h]
0x140017dfa  mov     edx, 28h ; '('
0x140017dff  mov     r8, rbx
0x140017e02  call    WPP_SF_
0x140017e07  cmp     byte ptr [rsi+4Ch], 0
0x140017e0b  mov     r14, [rsi+0B0h]
0x140017e12  jnz     loc_140017F6E
0x140017e18  or      dword ptr [r14], 2
0x140017e1c  mov     rcx, rbp; SpinLock
0x140017e1f  imul    ebx, [rsi+78h], 64h ; 'd'
0x140017e23  mov     dl, [rsi+40h]; NewIrql
0x140017e26  mov     edi, [rsi+7Ch]
0x140017e29  mov     dword ptr [rsi+48h], 8
0x140017e30  shr     ebx, 3
0x140017e33  call    cs:__imp_KeReleaseSpinLock
0x140017e3a  nop     dword ptr [rax+rax+00h]
0x140017e3f  mov     rax, [r14+8]
0x140017e43  mov     [rax+20h], ebx
0x140017e46  mov     rax, [r14+8]
0x140017e4a  mov     [rax+28h], ebx
0x140017e4d  mov     rax, [r14+8]
0x140017e51  mov     [rax], ebx
0x140017e53  mov     rax, [r14+8]
0x140017e57  mov     [rax+8], ebx
0x140017e5a  mov     rax, [r14+8]
0x140017e5e  mov     [rax+18h], edi
0x140017e61  mov     rax, [r14+8]
0x140017e65  mov     [rax+38h], edi
0x140017e68  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e6f  lea     rbx, WPP_GLOBAL_Control
0x140017e76  cmp     rcx, rbx
0x140017e79  jz      short loc_140017EA0
0x140017e7b  bt      dword ptr [rcx+2Ch], 0Fh
0x140017e80  jnb     short loc_140017EA0
0x140017e82  cmp     byte ptr [rcx+29h], 2
0x140017e86  jb      short loc_140017EA0
0x140017e88  mov     rcx, [rcx+18h]
0x140017e8c  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140017e93  mov     edx, 29h ; ')'
0x140017e98  mov     r9d, r15d
0x140017e9b  call    WPP_SF_d
0x140017ea0  mov     rax, [rsi+0B0h]
0x140017ea7  xor     r9d, r9d; CallMgrPartyContext
0x140017eaa  mov     rdx, [rsi+0A8h]; NdisVcHandle
0x140017eb1  xor     r8d, r8d; NdisPartyHandle
0x140017eb4  xor     ecx, ecx; Status
0x140017eb6  mov     [rsp+68h+CallParameters], rax; CallParameters
0x140017ebb  call    cs:__imp_NdisCmMakeCallComplete
0x140017ec2  nop     dword ptr [rax+rax+00h]
0x140017ec7  mov     rcx, rbp; SpinLock
0x140017eca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017ed1  nop     dword ptr [rax+rax+00h]
0x140017ed6  mov     [rsi+40h], al
0x140017ed9  mov     qword ptr [rsi+0B0h], 0
0x140017ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140017eeb  cmp     rcx, rbx
0x140017eee  jz      short loc_140017F12
0x140017ef0  bt      dword ptr [rcx+2Ch], 0Fh
0x140017ef5  jnb     short loc_140017F12
0x140017ef7  cmp     byte ptr [rcx+29h], 2
0x140017efb  jb      short loc_140017F12
0x140017efd  mov     rcx, [rcx+18h]
0x140017f01  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140017f08  mov     edx, 2Ah ; '*'
0x140017f0d  call    WPP_SF_
0x140017f12  or      dword ptr [rsi+58h], 8
0x140017f16  lock inc dword ptr [rsi+18h]
0x140017f1a  mov     dl, [rsi+40h]; NewIrql
0x140017f1d  mov     rcx, rbp; SpinLock
0x140017f20  call    cs:__imp_KeReleaseSpinLock
0x140017f27  nop     dword ptr [rax+rax+00h]
0x140017f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f33  cmp     rcx, rbx
0x140017f36  jz      loc_14001803B
0x140017f3c  bt      dword ptr [rcx+2Ch], 0Fh
0x140017f41  jnb     loc_14001803B
0x140017f47  cmp     byte ptr [rcx+29h], 2
0x140017f4b  jb      loc_14001803B
0x140017f51  mov     rcx, [rcx+18h]
0x140017f55  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140017f5c  mov     edx, 2Bh ; '+'
0x140017f61  mov     r9, rsi
0x140017f64  call    WPP_SF_q
0x140017f69  jmp     loc_14001803B
0x140017f6e  test    r14, r14
0x140017f71  jz      short loc_140017F84
0x140017f73  xor     edx, edx; Tag
0x140017f75  mov     rcx, r14; P
0x140017f78  call    cs:__imp_ExFreePoolWithTag
0x140017f7f  nop     dword ptr [rax+rax+00h]
0x140017f84  mov     dl, [rsi+40h]; NewIrql
0x140017f87  mov     rcx, rbp; SpinLock
0x140017f8a  mov     qword ptr [rsi+0B0h], 0
0x140017f95  call    cs:__imp_KeReleaseSpinLock
0x140017f9c  nop     dword ptr [rax+rax+00h]
0x140017fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fa8  cmp     rcx, rdi
0x140017fab  jz      short loc_140017FCB
0x140017fad  bt      dword ptr [rcx+2Ch], 0Fh
0x140017fb2  jnb     short loc_140017FCB
0x140017fb4  cmp     byte ptr [rcx+29h], 2
0x140017fb8  jb      short loc_140017FCB
0x140017fba  mov     rcx, [rcx+18h]
0x140017fbe  mov     edx, 2Ch ; ','
0x140017fc3  mov     r8, rbx
0x140017fc6  call    WPP_SF_
0x140017fcb  mov     rcx, [rsi+0A8h]; NdisVcHandle
0x140017fd2  call    cs:__imp_NdisCmDispatchCallConnected
0x140017fd9  nop     dword ptr [rax+rax+00h]
0x140017fde  mov     rcx, rbp; SpinLock
0x140017fe1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017fe8  nop     dword ptr [rax+rax+00h]
0x140017fed  or      dword ptr [rsi+58h], 8
0x140017ff1  mov     [rsi+40h], al
0x140017ff4  mov     dword ptr [rsi+48h], 8
0x140017ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140018002  cmp     rcx, rdi
0x140018005  jz      short loc_140018025
0x140018007  bt      dword ptr [rcx+2Ch], 0Fh
0x14001800c  jnb     short loc_140018025
0x14001800e  cmp     byte ptr [rcx+29h], 2
0x140018012  jb      short loc_140018025
0x140018014  mov     rcx, [rcx+18h]
0x140018018  mov     edx, 2Dh ; '-'
0x14001801d  mov     r8, rbx
0x140018020  call    WPP_SF_
0x140018025  lock inc dword ptr [rsi+18h]
0x140018029  mov     dl, [rsi+40h]; NewIrql
0x14001802c  mov     rcx, rbp; SpinLock
0x14001802f  call    cs:__imp_KeReleaseSpinLock
0x140018036  nop     dword ptr [rax+rax+00h]
0x14001803b  add     rsp, 30h
0x14001803f  pop     r15
0x140018041  pop     r14
0x140018043  pop     r12
0x140018045  pop     rdi
0x140018046  pop     rsi
0x140018047  pop     rbp
0x140018048  pop     rbx
0x140018049  retn
```
