# SessionDisconnect

- ea: `0x140017ab8`
- end: `0x140017dac`
- name: `SessionDisconnect`
- size: `756`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d370`
- `0x14000da70`
- `0x14000e840`
- `0x14001737c`
- `0x140017db4`

## callees

- `0x140003bf4`
- `0x140005050`
- `0x1400133b0`
- `0x1400157dc`
- `0x140015bdc`
- `0x140017ab8`
- `0x140018e9c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017afc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017ae6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017afc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b75`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c39`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017c4b`

## string_xrefs

- `0x140017c57`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
void __fastcall SessionDisconnect(__int64 a1)
{
  __int64 v1; // rsi
  const char *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  unsigned int v7; // r12d
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rax
  unsigned int v13; // esi
  __int64 v14; // rbx
  int v15; // edx
  __int128 v16; // [rsp+40h] [rbp-20h] BYREF
  __int128 v17; // [rsp+50h] [rbp-10h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v16 = 0;
  v17 = 0;
  *(_BYTE *)(v1 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 24));
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v3 = RfcommStateTxt(*(_DWORD *)(a1 + 48));
    WPP_RECORDER_SF_qs(WPP_GLOBAL_Control->DeviceExtension, v4, 3, 33, v4, a1, (__int64)v3);
  }
  if ( *(_DWORD *)(a1 + 48) == 6 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), *(_BYTE *)(v1 + 32));
  }
  else
  {
    RfcommSetState(a1, 6);
    *((_QWORD *)&v16 + 1) = &v16;
    *(_QWORD *)&v16 = &v16;
    ListDrainLocked(&v16, a1 + 208);
    ListDrainLocked(&v16, a1 + 192);
    v5 = *(_QWORD **)(a1 + 176);
    *(_QWORD *)(a1 + 176) = 0;
    if ( v5 )
    {
      v6 = (_QWORD *)*((_QWORD *)&v16 + 1);
      if ( **((__int128 ***)&v16 + 1) != &v16 )
LABEL_17:
        __fastfail(3u);
      v5[1] = *((_QWORD *)&v16 + 1);
      *v5 = &v16;
      *v6 = v5;
      *((_QWORD *)&v16 + 1) = v5;
      _InterlockedExchange((volatile __int32 *)(a1 + 184), 0);
    }
    v7 = ListDrainLocked(a1 + 160, a1 + 224);
    *((_QWORD *)&v17 + 1) = &v17;
    *(_QWORD *)&v17 = &v17;
    ListDrainLocked(&v17, a1 + 96);
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 24), *(_BYTE *)(v1 + 32));
    while ( 1 )
    {
      v9 = v16;
      if ( (__int128 *)v16 == &v16 )
        break;
      if ( *(__int128 **)(v16 + 8) != &v16 )
        goto LABEL_17;
      v10 = *(_QWORD *)v16;
      if ( *(_QWORD *)(*(_QWORD *)v16 + 8LL) != (_QWORD)v16 )
        goto LABEL_17;
      *(_QWORD *)&v16 = *(_QWORD *)v16;
      *(_QWORD *)(v10 + 8) = &v16;
      *(_QWORD *)(v9 + 8) = v9;
      *(_QWORD *)v9 = v9;
      *(_DWORD *)(v9 + 104) = -1073741299;
      *(_DWORD *)(v9 + 60) = 0;
      RefObj_ReleaseEx(v9 + 24, 541803329, 1046, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    }
    while ( 1 )
    {
      v11 = (_QWORD *)v17;
      if ( (__int128 *)v17 == &v17 )
        break;
      if ( *(__int128 **)(v17 + 8) != &v17 )
        goto LABEL_17;
      v12 = *(_QWORD *)v17;
      if ( *(_QWORD *)(*(_QWORD *)v17 + 8LL) != (_QWORD)v17 )
        goto LABEL_17;
      *(_QWORD *)&v17 = *(_QWORD *)v17;
      *(_QWORD *)(v12 + 8) = &v17;
      v11[1] = v11;
      *v11 = v11;
      ChannelConnect((__int64)(v11 - 35), v8);
      RefObj_ReleaseEx(v11 - 32, 1313754947, 1071, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    }
    v13 = 0;
    if ( v7 )
    {
      do
      {
        v14 = a1 + 24;
        RefObj_ReleaseEx(a1 + 24, 1145128274, 1076, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
        ++v13;
      }
      while ( v13 < v7 );
    }
    else
    {
      v14 = a1 + 24;
    }
    RefObj_ReleaseEx(v14, 1414090313, 1079, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        3,
        34,
        (__int64)WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids);
  }
}

```

## disassembly

```asm
0x140017ab8  push    rbp
0x140017aba  push    rbx
0x140017abb  push    rsi
0x140017abc  push    rdi
0x140017abd  push    r12
0x140017abf  push    r14
0x140017ac1  push    r15
0x140017ac3  mov     rbp, rsp
0x140017ac6  sub     rsp, 60h
0x140017aca  mov     rsi, [rcx+48h]
0x140017ace  mov     rdi, rcx
0x140017ad1  xorps   xmm0, xmm0
0x140017ad4  xorps   xmm1, xmm1
0x140017ad7  movups  [rbp+var_20], xmm0
0x140017adb  lea     r14, [rsi+18h]
0x140017adf  mov     rcx, r14; SpinLock
0x140017ae2  movups  [rbp+var_10], xmm1
0x140017ae6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017aed  nop     dword ptr [rax+rax+00h]
0x140017af2  lea     r15, [rdi+38h]
0x140017af6  mov     [rsi+20h], al
0x140017af9  mov     rcx, r15; SpinLock
0x140017afc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017b03  nop     dword ptr [rax+rax+00h]
0x140017b08  mov     [rdi+40h], al
0x140017b0b  lea     rax, WPP_RECORDER_INITIALIZED
0x140017b12  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017b19  lea     rdx, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017b20  jz      short loc_140017B53
0x140017b22  mov     ecx, [rdi+30h]
0x140017b25  call    RfcommStateTxt
0x140017b2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b31  mov     r9d, 21h ; '!'
0x140017b37  mov     [rsp+60h+var_30], rax
0x140017b3c  mov     [rsp+60h+var_38], rdi
0x140017b41  mov     [rsp+60h+var_40], rdx
0x140017b46  mov     rcx, [rcx+40h]
0x140017b4a  lea     r8d, [r9-1Eh]
0x140017b4e  call    WPP_RECORDER_SF_qs
0x140017b53  mov     edx, 6
0x140017b58  cmp     [rdi+30h], edx
0x140017b5b  jnz     short loc_140017B86
0x140017b5d  mov     dl, [rdi+40h]; NewIrql
0x140017b60  mov     rcx, r15; SpinLock
0x140017b63  call    cs:__imp_KeReleaseSpinLock
0x140017b6a  nop     dword ptr [rax+rax+00h]
0x140017b6f  mov     dl, [rsi+20h]; NewIrql
0x140017b72  mov     rcx, r14; SpinLock
0x140017b75  call    cs:__imp_KeReleaseSpinLock
0x140017b7c  nop     dword ptr [rax+rax+00h]
0x140017b81  jmp     loc_140017D9C
0x140017b86  mov     rcx, rdi
0x140017b89  call    RfcommSetState
0x140017b8e  lea     rax, [rbp+var_20]
0x140017b92  mov     qword ptr [rbp+var_20+8], rax
0x140017b96  lea     rdx, [rdi+0D0h]
0x140017b9d  lea     rax, [rbp+var_20]
0x140017ba1  lea     rcx, [rbp+var_20]
0x140017ba5  mov     qword ptr [rbp+var_20], rax
0x140017ba9  call    ListDrainLocked
0x140017bae  lea     rcx, [rbp+var_20]
0x140017bb2  lea     rdx, [rdi+0C0h]
0x140017bb9  call    ListDrainLocked
0x140017bbe  mov     rax, [rdi+0B0h]
0x140017bc5  mov     qword ptr [rdi+0B0h], 0
0x140017bd0  test    rax, rax
0x140017bd3  jz      short loc_140017C00
0x140017bd5  mov     rcx, qword ptr [rbp+var_20+8]
0x140017bd9  lea     rdx, [rbp+var_20]
0x140017bdd  cmp     [rcx], rdx
0x140017be0  jnz     loc_140017D1B
0x140017be6  mov     [rax+8], rcx
0x140017bea  lea     rdx, [rbp+var_20]
0x140017bee  mov     [rax], rdx
0x140017bf1  mov     [rcx], rax
0x140017bf4  mov     qword ptr [rbp+var_20+8], rax
0x140017bf8  xor     eax, eax
0x140017bfa  xchg    eax, [rdi+0B8h]
0x140017c00  lea     rdx, [rdi+0E0h]
0x140017c07  lea     rcx, [rdi+0A0h]
0x140017c0e  call    ListDrainLocked
0x140017c13  mov     r12d, eax
0x140017c16  lea     rdx, [rdi+60h]
0x140017c1a  lea     rax, [rbp+var_10]
0x140017c1e  mov     qword ptr [rbp+var_10+8], rax
0x140017c22  lea     rcx, [rbp+var_10]
0x140017c26  lea     rax, [rbp+var_10]
0x140017c2a  mov     qword ptr [rbp+var_10], rax
0x140017c2e  call    ListDrainLocked
0x140017c33  mov     dl, [rdi+40h]; NewIrql
0x140017c36  mov     rcx, r15; SpinLock
0x140017c39  call    cs:__imp_KeReleaseSpinLock
0x140017c40  nop     dword ptr [rax+rax+00h]
0x140017c45  mov     dl, [rsi+20h]; NewIrql
0x140017c48  mov     rcx, r14; SpinLock
0x140017c4b  call    cs:__imp_KeReleaseSpinLock
0x140017c52  nop     dword ptr [rax+rax+00h]
0x140017c57  lea     r14, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140017c5e  mov     rcx, qword ptr [rbp+var_20]
0x140017c62  lea     rax, [rbp+var_20]
0x140017c66  cmp     rcx, rax
0x140017c69  jz      short loc_140017CC0
0x140017c6b  lea     rax, [rbp+var_20]
0x140017c6f  cmp     [rcx+8], rax
0x140017c73  jnz     loc_140017D1B
0x140017c79  mov     rax, [rcx]
0x140017c7c  cmp     [rax+8], rcx
0x140017c80  jnz     loc_140017D1B
0x140017c86  mov     qword ptr [rbp+var_20], rax
0x140017c8a  lea     rdx, [rbp+var_20]
0x140017c8e  mov     [rax+8], rdx
0x140017c92  mov     r9, r14
0x140017c95  mov     [rcx+8], rcx
0x140017c99  mov     edx, 204B4341h
0x140017c9e  mov     [rcx], rcx
0x140017ca1  mov     r8d, 416h
0x140017ca7  mov     dword ptr [rcx+68h], 0C000020Dh
0x140017cae  mov     dword ptr [rcx+3Ch], 0
0x140017cb5  add     rcx, 18h
0x140017cb9  call    RefObj_ReleaseEx
0x140017cbe  jmp     short loc_140017C5E
0x140017cc0  mov     rbx, qword ptr [rbp+var_10]
0x140017cc4  lea     rax, [rbp+var_10]
0x140017cc8  cmp     rbx, rax
0x140017ccb  jz      short loc_140017D22
0x140017ccd  lea     rax, [rbp+var_10]
0x140017cd1  cmp     [rbx+8], rax
0x140017cd5  jnz     short loc_140017D1B
0x140017cd7  mov     rax, [rbx]
0x140017cda  cmp     [rax+8], rbx
0x140017cde  jnz     short loc_140017D1B
0x140017ce0  mov     qword ptr [rbp+var_10], rax
0x140017ce4  lea     rcx, [rbp+var_10]
0x140017ce8  mov     [rax+8], rcx
0x140017cec  lea     rcx, [rbx-118h]
0x140017cf3  mov     [rbx+8], rbx
0x140017cf7  mov     [rbx], rbx
0x140017cfa  call    ChannelConnect
0x140017cff  lea     rcx, [rbx-100h]
0x140017d06  mov     r9, r14
0x140017d09  mov     edx, 4E4E4F43h
0x140017d0e  mov     r8d, 42Fh
0x140017d14  call    RefObj_ReleaseEx
0x140017d19  jmp     short loc_140017CC0
0x140017d1b  mov     ecx, 3
0x140017d20  int     29h; Win8: RtlFailFast(ecx)
0x140017d22  xor     esi, esi
0x140017d24  test    r12d, r12d
0x140017d27  jz      short loc_140017D4C
0x140017d29  lea     rbx, [rdi+18h]
0x140017d2d  mov     r9, r14
0x140017d30  mov     rcx, rbx
0x140017d33  mov     edx, 44414552h
0x140017d38  mov     r8d, 434h
0x140017d3e  call    RefObj_ReleaseEx
0x140017d43  inc     esi
0x140017d45  cmp     esi, r12d
0x140017d48  jb      short loc_140017D29
0x140017d4a  jmp     short loc_140017D50
0x140017d4c  lea     rbx, [rdi+18h]
0x140017d50  mov     r9, r14
0x140017d53  mov     edx, 54494E49h
0x140017d58  mov     r8d, 437h
0x140017d5e  mov     rcx, rbx
0x140017d61  call    RefObj_ReleaseEx
0x140017d66  lea     rax, WPP_RECORDER_INITIALIZED
0x140017d6d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017d74  jz      short loc_140017D9C
0x140017d76  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d7d  lea     rax, WPP_e8acc0105d9833ef8123c1144c916ba5_Traceguids
0x140017d84  mov     r9d, 22h ; '"'
0x140017d8a  mov     [rsp+60h+var_40], rax
0x140017d8f  mov     rcx, [rcx+40h]
0x140017d93  lea     r8d, [r9-1Fh]
0x140017d97  call    WPP_RECORDER_SF_
0x140017d9c  add     rsp, 60h
0x140017da0  pop     r15
0x140017da2  pop     r14
0x140017da4  pop     r12
0x140017da6  pop     rdi
0x140017da7  pop     rsi
0x140017da8  pop     rbx
0x140017da9  pop     rbp
0x140017daa  retn
```
