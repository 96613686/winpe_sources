# Smb2CancelSuspendedExchangeOnSrvOpen

- ea: `0x140033a30`
- end: `0x140033d3b`
- name: `Smb2CancelSuspendedExchangeOnSrvOpen`
- size: `779`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001c040`
- `0x14001ff50`
- `0x140020040`
- `0x140028ae0`
- `0x140028b20`
- `0x1400297fc`
- `0x14002a1dc`
- `0x140033a30`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140033b78`
- `ntoskrnl!KeLowerIrql` at `0x140033b78`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b26`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b3a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b5a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b26`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b3a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140033b5a`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140033a9f`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140033acb`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140033a9f`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140033acb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033ae1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033ccd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033ae1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033ccd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033a70`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033c46`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033cdf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033c46`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140033cdf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140033a5a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140033a5a`
- `mrxsmb!SmbCeReferenceExchange` at `0x140033af5`
- `mrxsmb!SmbCeReferenceExchange` at `0x140033af5`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140033ab2`
- `mrxsmb!SmbCseReferenceCompoundingKey` at `0x140033ab2`
- `mrxsmb!SmbCeDereferenceExchange` at `0x140033b69`
- `mrxsmb!SmbCeDereferenceExchange` at `0x140033b69`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140033b49`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x140033b49`
- `mrxsmb!SmbCepCompleteExchangeLite` at `0x140033ca2`
- `mrxsmb!SmbCepCompleteExchangeLite` at `0x140033ca2`

## pseudocode

```c
__int64 __fastcall Smb2CancelSuspendedExchangeOnSrvOpen(_QWORD *a1)
{
  __int64 v2; // rsi
  KIRQL v3; // al
  __int64 v4; // rbx
  KIRQL v5; // r15
  __int64 v6; // rdi
  __int64 v7; // r13
  __int64 v8; // rdx
  __int64 v9; // r8
  KSPIN_LOCK *v10; // r12
  char v11; // si
  _QWORD *i; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rdx
  __int64 v17; // [rsp+80h] [rbp+8h]

  v2 = *(_QWORD *)(a1[9] + 48LL);
  v17 = v2;
  ExAcquirePushLockExclusiveEx(v2 + 16, 0);
  while ( 1 )
  {
    v3 = KeAcquireSpinLockRaiseToDpc(a1 + 28);
    v4 = a1[26];
    v5 = v3;
    if ( !v4 )
    {
      KeReleaseSpinLock(a1 + 28, v3);
      ExReleasePushLockExclusiveEx(v2 + 16, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_6016506345153a43e23e2141f162fbeb_Traceguids, a1);
      }
      return 0;
    }
    v6 = *(_QWORD *)(v4 + 56);
    if ( !v6 )
      break;
    v7 = v6 + 8;
    if ( KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v6 + 8)) )
    {
      SmbCseReferenceCompoundingKey(v6, v8, v9);
      v10 = (KSPIN_LOCK *)(v4 + 24);
      goto LABEL_9;
    }
LABEL_7:
    KeReleaseSpinLock(a1 + 28, v5);
  }
  v10 = (KSPIN_LOCK *)(v4 + 24);
  if ( !KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 24)) )
    goto LABEL_7;
  SmbCeReferenceExchange(v4);
  v7 = 8;
LABEL_9:
  v11 = 0;
  a1[26] = 0;
  _InterlockedOr((volatile signed __int32 *)(v4 + 68), 0x100u);
  _InterlockedAnd((volatile signed __int32 *)(v4 + 68), 0xFFFFFDFF);
  KeReleaseSpinLockFromDpcLevel(a1 + 28);
  if ( v6 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v7);
    SmbCseDereferenceCompoundingKey(v6);
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel(v10);
    SmbCeDereferenceExchange(v4);
  }
  KeLowerIrql(v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6016506345153a43e23e2141f162fbeb_Traceguids, v4, a1);
  }
  for ( i = *(_QWORD **)(v17 + 56); i != (_QWORD *)(v17 + 56); i = (_QWORD *)*i )
  {
    if ( i - 16 == (_QWORD *)v4 )
    {
      if ( v6 )
        SmbCeAcquireCompoundingKeyLock(v6);
      else
        SmbCeAcquireExchangeLock(v4);
      _InterlockedAnd((volatile signed __int32 *)(v4 + 68), 0xFFFFFFF7);
      if ( v6 )
        SmbCeReleaseCompoundingKeyLock(v6);
      else
        SmbCeReleaseExchangeLock(v4);
      v13 = (_QWORD *)(v4 + 128);
      v14 = *(_QWORD *)(v4 + 128);
      if ( *(_QWORD *)(v14 + 8) != v4 + 128 || (v15 = *(_QWORD **)(v4 + 136), (_QWORD *)*v15 != v13) )
        __fastfail(3u);
      *v15 = v14;
      v11 = 1;
      *(_QWORD *)(v14 + 8) = v15;
      *(_QWORD *)(v4 + 136) = v4 + 128;
      *v13 = v13;
      break;
    }
  }
  ExReleasePushLockExclusiveEx(v17 + 16, 0);
  if ( v11 )
  {
    if ( v6 )
      SmbCeAcquireCompoundingKeyLock(v6);
    else
      SmbCeAcquireExchangeLock(v4);
    SmbCeUpdateExchangeStatus(v4, 0x10C0000120LL);
    SmbCepCompleteExchangeLite(v4);
    if ( v6 )
      SmbCeReleaseCompoundingKeyLock(v6);
    else
      SmbCeReleaseExchangeLock(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x140033a30  push    rbx
0x140033a32  push    rbp
0x140033a33  push    rsi
0x140033a34  push    rdi
0x140033a35  push    r12
0x140033a37  push    r13
0x140033a39  push    r14
0x140033a3b  push    r15
0x140033a3d  sub     rsp, 38h
0x140033a41  mov     rax, [rcx+48h]
0x140033a45  mov     rbp, rcx
0x140033a48  xor     edx, edx
0x140033a4a  mov     rsi, [rax+30h]
0x140033a4e  mov     [rsp+78h+arg_0], rsi
0x140033a56  lea     rcx, [rsi+10h]
0x140033a5a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140033a61  nop     dword ptr [rax+rax+00h]
0x140033a66  lea     r14, [rbp+0E0h]
0x140033a6d  mov     rcx, r14; SpinLock
0x140033a70  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140033a77  nop     dword ptr [rax+rax+00h]
0x140033a7c  mov     rbx, [rbp+0D0h]
0x140033a83  mov     r15b, al
0x140033a86  test    rbx, rbx
0x140033a89  jz      loc_140033CC7
0x140033a8f  mov     rdi, [rbx+38h]
0x140033a93  test    rdi, rdi
0x140033a96  jz      short loc_140033AC4
0x140033a98  lea     r13, [rdi+8]
0x140033a9c  mov     rcx, r13; SpinLock
0x140033a9f  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x140033aa6  nop     dword ptr [rax+rax+00h]
0x140033aab  test    al, al
0x140033aad  jz      short loc_140033ADB
0x140033aaf  mov     rcx, rdi
0x140033ab2  call    cs:__imp_SmbCseReferenceCompoundingKey
0x140033ab9  nop     dword ptr [rax+rax+00h]
0x140033abe  lea     r12, [rbx+18h]
0x140033ac2  jmp     short loc_140033B05
0x140033ac4  lea     r12, [rbx+18h]
0x140033ac8  mov     rcx, r12; SpinLock
0x140033acb  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x140033ad2  nop     dword ptr [rax+rax+00h]
0x140033ad7  test    al, al
0x140033ad9  jnz     short loc_140033AF2
0x140033adb  mov     dl, r15b; NewIrql
0x140033ade  mov     rcx, r14; SpinLock
0x140033ae1  call    cs:__imp_KeReleaseSpinLock
0x140033ae8  nop     dword ptr [rax+rax+00h]
0x140033aed  jmp     loc_140033A6D
0x140033af2  mov     rcx, rbx
0x140033af5  call    cs:__imp_SmbCeReferenceExchange
0x140033afc  nop     dword ptr [rax+rax+00h]
0x140033b01  lea     r13, [rdi+8]
0x140033b05  xor     sil, sil
0x140033b08  mov     qword ptr [rbp+0D0h], 0
0x140033b13  lock or dword ptr [rbx+44h], 100h
0x140033b1b  lock and dword ptr [rbx+44h], 0FFFFFDFFh
0x140033b23  mov     rcx, r14; SpinLock
0x140033b26  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140033b2d  nop     dword ptr [rax+rax+00h]
0x140033b32  test    rdi, rdi
0x140033b35  jz      short loc_140033B57
0x140033b37  mov     rcx, r13; SpinLock
0x140033b3a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140033b41  nop     dword ptr [rax+rax+00h]
0x140033b46  mov     rcx, rdi
0x140033b49  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x140033b50  nop     dword ptr [rax+rax+00h]
0x140033b55  jmp     short loc_140033B75
0x140033b57  mov     rcx, r12; SpinLock
0x140033b5a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140033b61  nop     dword ptr [rax+rax+00h]
0x140033b66  mov     rcx, rbx
0x140033b69  call    cs:__imp_SmbCeDereferenceExchange
0x140033b70  nop     dword ptr [rax+rax+00h]
0x140033b75  mov     cl, r15b; NewIrql
0x140033b78  call    cs:__imp_KeLowerIrql
0x140033b7f  nop     dword ptr [rax+rax+00h]
0x140033b84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033b8b  lea     rax, WPP_GLOBAL_Control
0x140033b92  cmp     rcx, rax
0x140033b95  jz      short loc_140033BC1
0x140033b97  mov     eax, [rcx+2Ch]
0x140033b9a  test    al, 10h
0x140033b9c  jz      short loc_140033BC1
0x140033b9e  cmp     byte ptr [rcx+29h], 2
0x140033ba2  jb      short loc_140033BC1
0x140033ba4  mov     rcx, [rcx+18h]
0x140033ba8  lea     r8, WPP_6016506345153a43e23e2141f162fbeb_Traceguids
0x140033baf  mov     edx, 0Bh
0x140033bb4  mov     [rsp+78h+var_58], rbp
0x140033bb9  mov     r9, rbx
0x140033bbc  call    WPP_SF_qq
0x140033bc1  mov     rbp, [rsp+78h+arg_0]
0x140033bc9  lea     rdx, [rbp+38h]
0x140033bcd  mov     rcx, [rdx]
0x140033bd0  cmp     rcx, rdx
0x140033bd3  jz      short loc_140033C40
0x140033bd5  lea     rax, [rcx-80h]
0x140033bd9  cmp     rax, rbx
0x140033bdc  jz      short loc_140033BE3
0x140033bde  mov     rcx, [rcx]
0x140033be1  jmp     short loc_140033BD0
0x140033be3  test    rdi, rdi
0x140033be6  jz      short loc_140033BF2
0x140033be8  mov     rcx, rdi
0x140033beb  call    SmbCeAcquireCompoundingKeyLock
0x140033bf0  jmp     short loc_140033BFA
0x140033bf2  mov     rcx, rbx
0x140033bf5  call    SmbCeAcquireExchangeLock
0x140033bfa  lock and dword ptr [rbx+44h], 0FFFFFFF7h
0x140033bff  test    rdi, rdi
0x140033c02  jz      short loc_140033C0E
0x140033c04  mov     rcx, rdi
0x140033c07  call    SmbCeReleaseCompoundingKeyLock
0x140033c0c  jmp     short loc_140033C16
0x140033c0e  mov     rcx, rbx
0x140033c11  call    SmbCeReleaseExchangeLock
0x140033c16  lea     rax, [rbx+80h]
0x140033c1d  mov     rcx, [rax]
0x140033c20  cmp     [rcx+8], rax
0x140033c24  jnz     short loc_140033C6A
0x140033c26  mov     rdx, [rax+8]
0x140033c2a  cmp     [rdx], rax
0x140033c2d  jnz     short loc_140033C6A
0x140033c2f  mov     [rdx], rcx
0x140033c32  mov     sil, 1
0x140033c35  mov     [rcx+8], rdx
0x140033c39  mov     [rax+8], rax
0x140033c3d  mov     [rax], rax
0x140033c40  xor     edx, edx
0x140033c42  lea     rcx, [rbp+10h]
0x140033c46  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140033c4d  nop     dword ptr [rax+rax+00h]
0x140033c52  test    sil, sil
0x140033c55  jz      loc_140033D27
0x140033c5b  test    rdi, rdi
0x140033c5e  jz      short loc_140033C71
0x140033c60  mov     rcx, rdi
0x140033c63  call    SmbCeAcquireCompoundingKeyLock
0x140033c68  jmp     short loc_140033C79
0x140033c6a  mov     ecx, 3
0x140033c6f  int     29h; Win8: RtlFailFast(ecx)
0x140033c71  mov     rcx, rbx
0x140033c74  call    SmbCeAcquireExchangeLock
0x140033c79  mov     dword ptr [rsp+78h+arg_0], 0C0000120h
0x140033c84  mov     rcx, rbx
0x140033c87  mov     dword ptr [rsp+78h+arg_0+4], 10h
0x140033c92  mov     rdx, [rsp+78h+arg_0]
0x140033c9a  call    SmbCeUpdateExchangeStatus
0x140033c9f  mov     rcx, rbx
0x140033ca2  call    cs:__imp_SmbCepCompleteExchangeLite
0x140033ca9  nop     dword ptr [rax+rax+00h]
0x140033cae  test    rdi, rdi
0x140033cb1  jz      short loc_140033CBD
0x140033cb3  mov     rcx, rdi
0x140033cb6  call    SmbCeReleaseCompoundingKeyLock
0x140033cbb  jmp     short loc_140033D27
0x140033cbd  mov     rcx, rbx
0x140033cc0  call    SmbCeReleaseExchangeLock
0x140033cc5  jmp     short loc_140033D27
0x140033cc7  mov     dl, r15b; NewIrql
0x140033cca  mov     rcx, r14; SpinLock
0x140033ccd  call    cs:__imp_KeReleaseSpinLock
0x140033cd4  nop     dword ptr [rax+rax+00h]
0x140033cd9  xor     edx, edx
0x140033cdb  lea     rcx, [rsi+10h]
0x140033cdf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140033ce6  nop     dword ptr [rax+rax+00h]
0x140033ceb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140033cf2  lea     rax, WPP_GLOBAL_Control
0x140033cf9  cmp     rcx, rax
0x140033cfc  jz      short loc_140033D27
0x140033cfe  mov     eax, [rcx+2Ch]
0x140033d01  mov     sil, 1
0x140033d04  test    sil, al
0x140033d07  jz      short loc_140033D27
0x140033d09  cmp     [rcx+29h], sil
0x140033d0d  jb      short loc_140033D27
0x140033d0f  mov     rcx, [rcx+18h]
0x140033d13  lea     r8, WPP_6016506345153a43e23e2141f162fbeb_Traceguids
0x140033d1a  mov     edx, 0Ah
0x140033d1f  mov     r9, rbp
0x140033d22  call    WPP_SF_q
0x140033d27  xor     eax, eax
0x140033d29  add     rsp, 38h
0x140033d2d  pop     r15
0x140033d2f  pop     r14
0x140033d31  pop     r13
0x140033d33  pop     r12
0x140033d35  pop     rdi
0x140033d36  pop     rsi
0x140033d37  pop     rbp
0x140033d38  pop     rbx
0x140033d39  retn
```
