# PptpCmActivateVcComplete

- ea: `0x140015a40`
- end: `0x140015d9f`
- name: `PptpCmActivateVcComplete`
- size: `863`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f3fc`
- `0x14000f8d8`
- `0x1400162f0`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x1400039f8`
- `0x140003e08`
- `0x140003e38`
- `0x140004204`
- `0x140015a40`
- `0x1400162cc`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015b9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015cac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d7b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015b9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015cac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015d7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015af8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015c58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015af8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015c58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015d63`
- `NDIS!NdisCmDispatchCallConnected` at `0x140015d54`
- `NDIS!NdisCmDispatchCallConnected` at `0x140015d54`
- `NDIS!NdisCmMakeCallComplete` at `0x140015c49`
- `NDIS!NdisCmMakeCallComplete` at `0x140015c49`

## pseudocode

```c
__int64 __fastcall PptpCmActivateVcComplete(unsigned int a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v5; // rbp
  KIRQL *v6; // r14
  _DWORD *v7; // rsi
  __int64 v8; // r13
  int v9; // ebx
  KIRQL v10; // al
  KIRQL v11; // dl
  KIRQL v12; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, a1);
  }
  if ( (a1 & 0x80000000) == 0 )
  {
    v5 = (KSPIN_LOCK *)(a2 + 96);
    v6 = (KIRQL *)(a2 + 104);
    v7 = (_DWORD *)(a2 + 424);
    *(_BYTE *)(a2 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
    *(_DWORD *)(a2 + 424) &= ~0x1000u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    _InterlockedIncrement((volatile signed __int32 *)a2);
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 32));
    *v7 |= 0x10004u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    v8 = *(_QWORD *)(a2 + 232);
    if ( *(_BYTE *)(a2 + 192) )
    {
      PptpCmFreeCallParams(*(_QWORD *)(a2 + 232));
      v11 = *v6;
      *(_QWORD *)(a2 + 232) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), v11);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
      NdisCmDispatchCallConnected(*(NDIS_HANDLE *)(a2 + 224));
    }
    else
    {
      *(_DWORD *)v8 |= 2u;
      v9 = *(_DWORD *)(a2 + 432) >> 3;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *v6);
      *(_DWORD *)(*(_QWORD *)(v8 + 8) + 32LL) = v9;
      *(_DWORD *)(*(_QWORD *)(v8 + 8) + 40LL) = v9;
      **(_DWORD **)(v8 + 8) = v9;
      *(_DWORD *)(*(_QWORD *)(v8 + 8) + 8LL) = v9;
      *(_DWORD *)(*(_QWORD *)(v8 + 8) + 24LL) = 1464;
      *(_DWORD *)(*(_QWORD *)(v8 + 8) + 56LL) = 1464;
      **(_DWORD **)(a2 + 440) = 1396789842;
      *(_DWORD *)(*(_QWORD *)(a2 + 440) + 4LL) = *(_DWORD *)(*(_QWORD *)(a2 + 80) + 660LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, a1);
      }
      NdisCmMakeCallComplete(0, *(NDIS_HANDLE *)(a2 + 224), 0, 0, *(PCO_CALL_PARAMETERS *)(a2 + 232));
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
      *v7 |= 8u;
      *v6 = v10;
      *(_QWORD *)(a2 + 232) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
      _InterlockedIncrement((volatile signed __int32 *)a2);
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), *v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, a2);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, a1);
    }
    CallSetState(a2, 11, a3, 0);
    CallCleanup(a2);
    v5 = (KSPIN_LOCK *)(a2 + 96);
    v6 = (KIRQL *)(a2 + 104);
    v7 = (_DWORD *)(a2 + 424);
  }
  v12 = KeAcquireSpinLockRaiseToDpc(v5);
  *v7 &= ~0x20000u;
  *v6 = v12;
  KeReleaseSpinLock(v5, v12);
  return DereferenceRefCount(a2);
}

```

## disassembly

```asm
0x140015a40  push    rbx
0x140015a42  push    rbp
0x140015a43  push    rsi
0x140015a44  push    rdi
0x140015a45  push    r13
0x140015a47  push    r14
0x140015a49  push    r15
0x140015a4b  sub     rsp, 30h
0x140015a4f  mov     rdi, rdx
0x140015a52  mov     r15d, ecx
0x140015a55  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a5c  lea     r13, WPP_GLOBAL_Control
0x140015a63  lea     rbx, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140015a6a  cmp     rcx, r13
0x140015a6d  jz      short loc_140015A90
0x140015a6f  mov     eax, [rcx+2Ch]
0x140015a72  test    al, 4
0x140015a74  jz      short loc_140015A90
0x140015a76  cmp     byte ptr [rcx+29h], 2
0x140015a7a  jb      short loc_140015A90
0x140015a7c  mov     rcx, [rcx+18h]
0x140015a80  mov     edx, 5Dh ; ']'
0x140015a85  mov     r9d, r15d
0x140015a88  mov     r8, rbx
0x140015a8b  call    WPP_SF_d
0x140015a90  test    r15d, r15d
0x140015a93  jns     short loc_140015AED
0x140015a95  mov     rcx, cs:WPP_GLOBAL_Control
0x140015a9c  cmp     rcx, r13
0x140015a9f  jz      short loc_140015AC2
0x140015aa1  mov     eax, [rcx+2Ch]
0x140015aa4  test    al, 4
0x140015aa6  jz      short loc_140015AC2
0x140015aa8  cmp     byte ptr [rcx+29h], 1
0x140015aac  jb      short loc_140015AC2
0x140015aae  mov     rcx, [rcx+18h]
0x140015ab2  mov     edx, 5Eh ; '^'
0x140015ab7  mov     r9d, r15d
0x140015aba  mov     r8, rbx
0x140015abd  call    WPP_SF_d
0x140015ac2  xor     r9d, r9d
0x140015ac5  mov     rcx, rdi
0x140015ac8  lea     edx, [r9+0Bh]
0x140015acc  call    CallSetState
0x140015ad1  mov     rcx, rdi
0x140015ad4  call    CallCleanup
0x140015ad9  lea     rbp, [rdi+60h]
0x140015add  lea     r14, [rdi+68h]
0x140015ae1  lea     rsi, [rdi+1A8h]
0x140015ae8  jmp     loc_140015D60
0x140015aed  lea     rbp, [rdi+60h]
0x140015af1  mov     rcx, rbp; SpinLock
0x140015af4  lea     r14, [rdi+68h]
0x140015af8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015aff  nop     dword ptr [rax+rax+00h]
0x140015b04  lea     rsi, [rdi+1A8h]
0x140015b0b  mov     [r14], al
0x140015b0e  btr     dword ptr [rsi], 0Ch
0x140015b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b19  cmp     rcx, r13
0x140015b1c  jz      short loc_140015B3C
0x140015b1e  mov     eax, [rcx+2Ch]
0x140015b21  test    al, 4
0x140015b23  jz      short loc_140015B3C
0x140015b25  cmp     byte ptr [rcx+29h], 2
0x140015b29  jb      short loc_140015B3C
0x140015b2b  mov     rcx, [rcx+18h]
0x140015b2f  mov     edx, 5Fh ; '_'
0x140015b34  mov     r8, rbx
0x140015b37  call    WPP_SF_
0x140015b3c  lock inc dword ptr [rdi]
0x140015b3f  lock inc dword ptr [rdi+20h]
0x140015b43  or      dword ptr [rsi], 10004h
0x140015b49  mov     rcx, cs:WPP_GLOBAL_Control
0x140015b50  cmp     rcx, r13
0x140015b53  jz      short loc_140015B73
0x140015b55  mov     eax, [rcx+2Ch]
0x140015b58  test    al, 4
0x140015b5a  jz      short loc_140015B73
0x140015b5c  cmp     byte ptr [rcx+29h], 2
0x140015b60  jb      short loc_140015B73
0x140015b62  mov     rcx, [rcx+18h]
0x140015b66  mov     edx, 60h ; '`'
0x140015b6b  mov     r8, rbx
0x140015b6e  call    WPP_SF_
0x140015b73  cmp     byte ptr [rdi+0C0h], 0
0x140015b7a  mov     r13, [rdi+0E8h]
0x140015b81  jnz     loc_140015CF7
0x140015b87  or      dword ptr [r13+0], 2
0x140015b8c  mov     rcx, rbp; SpinLock
0x140015b8f  mov     ebx, [rdi+1B0h]
0x140015b95  mov     dl, [r14]; NewIrql
0x140015b98  shr     ebx, 3
0x140015b9b  call    cs:__imp_KeReleaseSpinLock
0x140015ba2  nop     dword ptr [rax+rax+00h]
0x140015ba7  mov     rax, [r13+8]
0x140015bab  mov     ecx, 5B8h
0x140015bb0  mov     [rax+20h], ebx
0x140015bb3  mov     rax, [r13+8]
0x140015bb7  mov     [rax+28h], ebx
0x140015bba  mov     rax, [r13+8]
0x140015bbe  mov     [rax], ebx
0x140015bc0  mov     rax, [r13+8]
0x140015bc4  mov     [rax+8], ebx
0x140015bc7  mov     rax, [r13+8]
0x140015bcb  mov     [rax+18h], ecx
0x140015bce  mov     rax, [r13+8]
0x140015bd2  mov     [rax+38h], ecx
0x140015bd5  mov     rax, [rdi+1B8h]
0x140015bdc  mov     dword ptr [rax], 53415252h
0x140015be2  mov     rax, [rdi+50h]
0x140015be6  mov     rcx, [rdi+1B8h]
0x140015bed  mov     eax, [rax+294h]
0x140015bf3  mov     [rcx+4], eax
0x140015bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140015bfd  lea     r13, WPP_GLOBAL_Control
0x140015c04  cmp     rcx, r13
0x140015c07  jz      short loc_140015C2E
0x140015c09  mov     eax, [rcx+2Ch]
0x140015c0c  test    al, 4
0x140015c0e  jz      short loc_140015C2E
0x140015c10  cmp     byte ptr [rcx+29h], 1
0x140015c14  jb      short loc_140015C2E
0x140015c16  mov     rcx, [rcx+18h]
0x140015c1a  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140015c21  mov     edx, 61h ; 'a'
0x140015c26  mov     r9d, r15d
0x140015c29  call    WPP_SF_d
0x140015c2e  mov     rax, [rdi+0E8h]
0x140015c35  xor     r9d, r9d; CallMgrPartyContext
0x140015c38  mov     rdx, [rdi+0E0h]; NdisVcHandle
0x140015c3f  xor     r8d, r8d; NdisPartyHandle
0x140015c42  xor     ecx, ecx; Status
0x140015c44  mov     [rsp+68h+CallParameters], rax; CallParameters
0x140015c49  call    cs:__imp_NdisCmMakeCallComplete
0x140015c50  nop     dword ptr [rax+rax+00h]
0x140015c55  mov     rcx, rbp; SpinLock
0x140015c58  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015c5f  nop     dword ptr [rax+rax+00h]
0x140015c64  or      dword ptr [rsi], 8
0x140015c67  mov     [r14], al
0x140015c6a  mov     qword ptr [rdi+0E8h], 0
0x140015c75  mov     rcx, cs:WPP_GLOBAL_Control
0x140015c7c  cmp     rcx, r13
0x140015c7f  jz      short loc_140015CA3
0x140015c81  mov     eax, [rcx+2Ch]
0x140015c84  test    al, 4
0x140015c86  jz      short loc_140015CA3
0x140015c88  cmp     byte ptr [rcx+29h], 2
0x140015c8c  jb      short loc_140015CA3
0x140015c8e  mov     rcx, [rcx+18h]
0x140015c92  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140015c99  mov     edx, 62h ; 'b'
0x140015c9e  call    WPP_SF_
0x140015ca3  lock inc dword ptr [rdi]
0x140015ca6  mov     dl, [r14]; NewIrql
0x140015ca9  mov     rcx, rbp; SpinLock
0x140015cac  call    cs:__imp_KeReleaseSpinLock
0x140015cb3  nop     dword ptr [rax+rax+00h]
0x140015cb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140015cbf  cmp     rcx, r13
0x140015cc2  jz      loc_140015D60
0x140015cc8  mov     eax, [rcx+2Ch]
0x140015ccb  test    al, 4
0x140015ccd  jz      loc_140015D60
0x140015cd3  cmp     byte ptr [rcx+29h], 1
0x140015cd7  jb      loc_140015D60
0x140015cdd  mov     rcx, [rcx+18h]
0x140015ce1  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140015ce8  mov     edx, 63h ; 'c'
0x140015ced  mov     r9, rdi
0x140015cf0  call    WPP_SF_q
0x140015cf5  jmp     short loc_140015D60
0x140015cf7  mov     rcx, r13
0x140015cfa  call    PptpCmFreeCallParams
0x140015cff  mov     dl, [r14]; NewIrql
0x140015d02  mov     rcx, rbp; SpinLock
0x140015d05  mov     qword ptr [rdi+0E8h], 0
0x140015d10  call    cs:__imp_KeReleaseSpinLock
0x140015d17  nop     dword ptr [rax+rax+00h]
0x140015d1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015d23  lea     r13, WPP_GLOBAL_Control
0x140015d2a  cmp     rcx, r13
0x140015d2d  jz      short loc_140015D4D
0x140015d2f  mov     eax, [rcx+2Ch]
0x140015d32  test    al, 4
0x140015d34  jz      short loc_140015D4D
0x140015d36  cmp     byte ptr [rcx+29h], 2
0x140015d3a  jb      short loc_140015D4D
0x140015d3c  mov     rcx, [rcx+18h]
0x140015d40  mov     edx, 64h ; 'd'
0x140015d45  mov     r8, rbx
0x140015d48  call    WPP_SF_
0x140015d4d  mov     rcx, [rdi+0E0h]; NdisVcHandle
0x140015d54  call    cs:__imp_NdisCmDispatchCallConnected
0x140015d5b  nop     dword ptr [rax+rax+00h]
0x140015d60  mov     rcx, rbp; SpinLock
0x140015d63  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015d6a  nop     dword ptr [rax+rax+00h]
0x140015d6f  btr     dword ptr [rsi], 11h
0x140015d73  mov     rcx, rbp; SpinLock
0x140015d76  mov     dl, al; NewIrql
0x140015d78  mov     [r14], al
0x140015d7b  call    cs:__imp_KeReleaseSpinLock
0x140015d82  nop     dword ptr [rax+rax+00h]
0x140015d87  mov     rcx, rdi
0x140015d8a  call    DereferenceRefCount
0x140015d8f  add     rsp, 30h
0x140015d93  pop     r15
0x140015d95  pop     r14
0x140015d97  pop     r13
0x140015d99  pop     rdi
0x140015d9a  pop     rsi
0x140015d9b  pop     rbp
0x140015d9c  pop     rbx
0x140015d9d  retn
```
