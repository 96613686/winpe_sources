# GetLinkInfo

- ea: `0x1400288a0`
- end: `0x140028daf`
- name: `GetLinkInfo`
- size: `1295`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x140003060`
- `0x1400048c0`
- `0x14000550c`
- `0x1400084d8`
- `0x1400087f0`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a648`
- `0x140010640`
- `0x1400161f0`
- `0x140016700`
- `0x1400288a0`
- `0x140035960`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140028aac`
- `ntoskrnl!KeInitializeEvent` at `0x140028b82`
- `ntoskrnl!KeInitializeEvent` at `0x140028aac`
- `ntoskrnl!KeInitializeEvent` at `0x140028b82`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028bc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028c30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028cf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028d7a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028bc0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028c30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028cf3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140028d7a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028b9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028c0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028d53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028b9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028c0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140028d53`

## pseudocode

```c
__int64 __fastcall GetLinkInfo(__int64 *a1, __int64 a2, __int64 a3, unsigned int a4, _DWORD *a5)
{
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  char *v11; // rdi
  char v12; // si
  _DWORD *v13; // rbx
  int v14; // eax
  KIRQL v15; // al
  KSPIN_LOCK *v16; // rcx
  int v17; // ebx
  KIRQL v18; // al
  PVOID Entry; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v23; // [rsp+48h] [rbp-B8h]
  __int128 v24; // [rsp+58h] [rbp-A8h]
  struct _KEVENT v25[14]; // [rsp+70h] [rbp-90h] BYREF

  v22 = 0;
  v23 = 0;
  Entry = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  *a5 = 56;
  if ( a4 < 0x38 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a4, 56);
    }
    return (unsigned int)-1073741820;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v10 = *a1;
  if ( v9 )
  {
    v8 = ValidateLink(v10, 1, &Entry);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, *a1);
      }
      goto LABEL_26;
    }
  }
  else if ( !(unsigned __int8)IsLinkValid(v10, 1, &Entry) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, *a1);
    }
    v8 = 601;
LABEL_26:
    v11 = (char *)Entry;
    goto LABEL_51;
  }
  v11 = (char *)Entry;
  v12 = 0;
  v13 = (_DWORD *)*((_QWORD *)Entry + 9);
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( v13[30] == 12 && v13[31] == 12 )
  {
    v12 = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
    }
  }
  if ( (v13[5] & 1) != 0 )
  {
    memset(v25, 0, 0x108u);
    v25[0].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)1;
    KeInitializeEvent(&v25[10], NotificationEvent, 0);
    *(_QWORD *)&v25[1].Header.Lock = v13;
    *(_QWORD *)&v22 = *((_QWORD *)v11 + 7);
    *(_QWORD *)&v25[4].Header.Lock = &v22;
    LODWORD(v25[3].Header.WaitListHead.Flink) = 0;
    LODWORD(v25[3].Header.WaitListHead.Blink) = 67174665;
    LODWORD(v25[4].Header.WaitListHead.Flink) = 48;
    if ( !(unsigned int)NdisWanSubmitNdisRequestLegacy(v13, v25) )
    {
      *((_QWORD *)v11 + 34) = *((_QWORD *)&v22 + 1);
      if ( v12 )
        *((_QWORD *)v11 + 36) |= *((_QWORD *)&v23 + 1);
      else
        *((_QWORD *)v11 + 36) = *((_QWORD *)&v23 + 1);
      *((_QWORD *)v11 + 37) = v24;
      *((_DWORD *)v11 + 76) = DWORD2(v24);
      v14 = HIDWORD(v24);
LABEL_48:
      *((_DWORD *)v11 + 77) = v14;
    }
  }
  else
  {
    memset(v25, 0, 0x148u);
    v25[0].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)1;
    KeInitializeEvent((PRKEVENT)&v25[12].Header.WaitListHead.Blink, NotificationEvent, 0);
    *(_QWORD *)&v25[1].Header.Lock = v13;
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
    v11[744] = v15;
    v16 = (KSPIN_LOCK *)(v11 + 736);
    if ( *((_DWORD *)v11 + 6) != 2 )
    {
      KeReleaseSpinLock(v16, v15);
      goto LABEL_50;
    }
    ++*((_DWORD *)v11 + 8);
    KeReleaseSpinLock(v16, v15);
    *(_QWORD *)&v25[2].Header.Lock = 15466902;
    v25[3].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)&v22;
    LODWORD(v25[3].Header.WaitListHead.Flink) = 67174786;
    v25[4].Header.LockNV = 32;
    v25[1].Header.WaitListHead.Flink = 0;
    v25[1].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)*((_QWORD *)v11 + 7);
    v17 = NdisWanSubmitNdisRequest(v13, v25);
    v11[744] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
    DerefVc(v11);
    KeReleaseSpinLock((PKSPIN_LOCK)v11 + 92, v11[744]);
    if ( !v17 )
    {
      *((_QWORD *)v11 + 34) = v22;
      if ( v12 )
      {
        *((_QWORD *)v11 + 36) |= *((_QWORD *)&v22 + 1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            76,
            WPP_5659416b879e33cc7e241cd80588418e_Traceguids,
            *((unsigned int *)v11 + 72),
            *((_DWORD *)v11 + 73));
        }
      }
      else
      {
        *((_QWORD *)v11 + 36) = *((_QWORD *)&v22 + 1);
      }
      *((_QWORD *)v11 + 37) = v23;
      *((_DWORD *)v11 + 76) = DWORD2(v23);
      v14 = HIDWORD(v23);
      goto LABEL_48;
    }
  }
LABEL_50:
  v8 = 0;
  *((_DWORD *)v11 + 78) = glMaxMTU;
  *((_DWORD *)v11 + 79) = glMRRU;
  *(_OWORD *)(a3 + 8) = *((_OWORD *)v11 + 17);
  *(_OWORD *)(a3 + 24) = *((_OWORD *)v11 + 18);
  *(_OWORD *)(a3 + 40) = *((_OWORD *)v11 + 19);
  *(_QWORD *)a3 = *((_QWORD *)v11 + 5);
LABEL_51:
  if ( v11 )
  {
    v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 92);
    v11[744] = v18;
    if ( (*((_DWORD *)v11 + 7))-- == 1 )
      DoDerefLinkCBWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 92, v18);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400288a0  mov     [rsp-8+arg_8], rbx
0x1400288a5  push    rbp
0x1400288a6  push    rsi
0x1400288a7  push    rdi
0x1400288a8  push    r14
0x1400288aa  push    r15
0x1400288ac  lea     rbp, [rsp-0D0h]
0x1400288b4  sub     rsp, 1D0h
0x1400288bb  mov     rax, cs:__security_cookie
0x1400288c2  xor     rax, rsp
0x1400288c5  mov     [rbp+0F0h+var_30], rax
0x1400288cc  mov     rsi, [rbp+0F0h+arg_20]
0x1400288d3  xorps   xmm0, xmm0
0x1400288d6  movups  [rsp+1F0h+var_1B8], xmm0
0x1400288db  mov     ebx, r9d
0x1400288de  mov     r15, r8
0x1400288e1  movups  [rsp+1F0h+var_1A8], xmm0
0x1400288e6  mov     rdi, rcx
0x1400288e9  mov     [rsp+1F0h+Entry], 0
0x1400288f2  movups  [rsp+1F0h+var_198], xmm0
0x1400288f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400288fe  lea     r14, WPP_GLOBAL_Control
0x140028905  cmp     rcx, r14
0x140028908  jz      short loc_14002892C
0x14002890a  mov     eax, [rcx+2Ch]
0x14002890d  test    al, 20h
0x14002890f  jz      short loc_14002892C
0x140028911  cmp     byte ptr [rcx+29h], 5
0x140028915  jb      short loc_14002892C
0x140028917  mov     rcx, [rcx+18h]
0x14002891b  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028922  mov     edx, 47h ; 'G'
0x140028927  call    WPP_SF_
0x14002892c  mov     r8d, 38h ; '8'
0x140028932  mov     [rsi], r8d
0x140028935  cmp     ebx, r8d
0x140028938  jnb     short loc_140028979
0x14002893a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028941  cmp     rcx, r14
0x140028944  jz      short loc_14002896F
0x140028946  mov     eax, [rcx+2Ch]
0x140028949  test    al, 20h
0x14002894b  jz      short loc_14002896F
0x14002894d  cmp     byte ptr [rcx+29h], 3
0x140028951  jb      short loc_14002896F
0x140028953  mov     rcx, [rcx+18h]
0x140028957  lea     edx, [r8+10h]
0x14002895b  mov     [rsp+1F0h+var_1D0], r8d
0x140028960  mov     r9d, ebx
0x140028963  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x14002896a  call    WPP_SF_dd
0x14002896f  mov     ebx, 0C0000004h
0x140028974  jmp     loc_140028D86
0x140028979  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x14002897f  test    al, 10h
0x140028981  jz      short loc_140028988
0x140028983  and     eax, 1
0x140028986  jmp     short loc_14002898D
0x140028988  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x14002898d  mov     rcx, [rdi]
0x140028990  lea     r8, [rsp+1F0h+Entry]
0x140028995  mov     dl, 1
0x140028997  test    eax, eax
0x140028999  jnz     short loc_1400289DC
0x14002899b  call    IsLinkValid
0x1400289a0  test    al, al
0x1400289a2  jnz     short loc_140028A23
0x1400289a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289ab  cmp     rcx, r14
0x1400289ae  jz      short loc_1400289D5
0x1400289b0  mov     eax, [rcx+2Ch]
0x1400289b3  test    al, 20h
0x1400289b5  jz      short loc_1400289D5
0x1400289b7  cmp     byte ptr [rcx+29h], 3
0x1400289bb  jb      short loc_1400289D5
0x1400289bd  mov     r9, [rdi]
0x1400289c0  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x1400289c7  mov     rcx, [rcx+18h]
0x1400289cb  mov     edx, 4Ah ; 'J'
0x1400289d0  call    WPP_SF_q
0x1400289d5  mov     ebx, 259h
0x1400289da  jmp     short loc_140028A19
0x1400289dc  call    ValidateLink
0x1400289e1  mov     ebx, eax
0x1400289e3  test    eax, eax
0x1400289e5  jns     short loc_140028A23
0x1400289e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400289ee  cmp     rcx, r14
0x1400289f1  jz      short loc_140028A19
0x1400289f3  mov     edx, [rcx+2Ch]
0x1400289f6  test    dl, 20h
0x1400289f9  jz      short loc_140028A19
0x1400289fb  cmp     byte ptr [rcx+29h], 3
0x1400289ff  jb      short loc_140028A19
0x140028a01  mov     r9, [rdi]
0x140028a04  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028a0b  mov     rcx, [rcx+18h]
0x140028a0f  mov     edx, 49h ; 'I'
0x140028a14  call    WPP_SF_q
0x140028a19  mov     rdi, [rsp+1F0h+Entry]
0x140028a1e  jmp     loc_140028D44
0x140028a23  mov     rdi, [rsp+1F0h+Entry]
0x140028a28  xorps   xmm0, xmm0
0x140028a2b  xor     sil, sil
0x140028a2e  mov     rbx, [rdi+48h]
0x140028a32  movups  [rsp+1F0h+var_1B8], xmm0
0x140028a37  movups  [rsp+1F0h+var_1A8], xmm0
0x140028a3c  movups  [rsp+1F0h+var_198], xmm0
0x140028a41  cmp     dword ptr [rbx+78h], 0Ch
0x140028a45  jnz     short loc_140028A7E
0x140028a47  cmp     dword ptr [rbx+7Ch], 0Ch
0x140028a4b  jnz     short loc_140028A7E
0x140028a4d  mov     sil, 1
0x140028a50  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a57  cmp     rcx, r14
0x140028a5a  jz      short loc_140028A7E
0x140028a5c  mov     eax, [rcx+2Ch]
0x140028a5f  test    al, 20h
0x140028a61  jz      short loc_140028A7E
0x140028a63  cmp     byte ptr [rcx+29h], 5
0x140028a67  jb      short loc_140028A7E
0x140028a69  mov     rcx, [rcx+18h]
0x140028a6d  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028a74  mov     edx, 4Bh ; 'K'
0x140028a79  call    WPP_SF_
0x140028a7e  mov     eax, [rbx+14h]
0x140028a81  xor     edx, edx; Val
0x140028a83  test    al, 1
0x140028a85  jz      loc_140028B5E
0x140028a8b  mov     r8d, 108h; Size
0x140028a91  lea     rcx, [rsp+1F0h+var_180]; void *
0x140028a96  call    memset
0x140028a9b  xor     r8d, r8d; State
0x140028a9e  mov     [rbp+0F0h+var_170], 1
0x140028aa6  xor     edx, edx; Type
0x140028aa8  lea     rcx, [rbp+0F0h+Event]; Event
0x140028aac  call    cs:__imp_KeInitializeEvent
0x140028ab3  nop     dword ptr [rax+rax+00h]
0x140028ab8  mov     [rbp+0F0h+var_168], rbx
0x140028abc  lea     rdx, [rsp+1F0h+var_180]
0x140028ac1  mov     rax, [rdi+38h]
0x140028ac5  mov     rcx, rbx
0x140028ac8  mov     qword ptr [rsp+1F0h+var_1B8], rax
0x140028acd  lea     rax, [rsp+1F0h+var_1B8]
0x140028ad2  mov     [rbp+0F0h+var_120], rax
0x140028ad6  mov     [rbp+0F0h+var_130], 0
0x140028add  mov     dword ptr [rbp+0F0h+var_128], 4010109h
0x140028ae4  mov     [rbp+0F0h+var_118], 30h ; '0'
0x140028aeb  call    NdisWanSubmitNdisRequestLegacy
0x140028af0  test    eax, eax
0x140028af2  jnz     loc_140028CFF
0x140028af8  mov     eax, dword ptr [rsp+1F0h+var_1B8+8]
0x140028afc  mov     [rdi+110h], eax
0x140028b02  mov     eax, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x140028b06  mov     [rdi+114h], eax
0x140028b0c  mov     eax, dword ptr [rsp+1F0h+var_1A8+8]
0x140028b10  test    sil, sil
0x140028b13  jz      short loc_140028B27
0x140028b15  or      [rdi+120h], eax
0x140028b1b  mov     eax, dword ptr [rsp+1F0h+var_1A8+0Ch]
0x140028b1f  or      [rdi+124h], eax
0x140028b25  jmp     short loc_140028B37
0x140028b27  mov     [rdi+120h], eax
0x140028b2d  mov     eax, dword ptr [rsp+1F0h+var_1A8+0Ch]
0x140028b31  mov     [rdi+124h], eax
0x140028b37  mov     eax, dword ptr [rsp+1F0h+var_198]
0x140028b3b  mov     [rdi+128h], eax
0x140028b41  mov     eax, dword ptr [rsp+1F0h+var_198+4]
0x140028b45  mov     [rdi+12Ch], eax
0x140028b4b  mov     eax, dword ptr [rsp+1F0h+var_198+8]
0x140028b4f  mov     [rdi+130h], eax
0x140028b55  mov     eax, dword ptr [rsp+1F0h+var_198+0Ch]
0x140028b59  jmp     loc_140028CEB
0x140028b5e  mov     r8d, 148h; Size
0x140028b64  lea     rcx, [rsp+1F0h+var_180]; void *
0x140028b69  call    memset
0x140028b6e  xor     r8d, r8d; State
0x140028b71  mov     [rbp+0F0h+var_170], 1
0x140028b79  xor     edx, edx; Type
0x140028b7b  lea     rcx, [rbp+0F0h+var_50]; Event
0x140028b82  call    cs:__imp_KeInitializeEvent
0x140028b89  nop     dword ptr [rax+rax+00h]
0x140028b8e  lea     r14, [rdi+2E0h]
0x140028b95  mov     [rbp+0F0h+var_168], rbx
0x140028b99  mov     rcx, r14; SpinLock
0x140028b9c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028ba3  nop     dword ptr [rax+rax+00h]
0x140028ba8  mov     [rdi+2E8h], al
0x140028bae  mov     dl, al; NewIrql
0x140028bb0  cmp     dword ptr [rdi+18h], 2
0x140028bb4  mov     rcx, r14; SpinLock
0x140028bb7  jnz     loc_140028CF3
0x140028bbd  inc     dword ptr [rdi+20h]
0x140028bc0  call    cs:__imp_KeReleaseSpinLock
0x140028bc7  nop     dword ptr [rax+rax+00h]
0x140028bcc  lea     rax, [rsp+1F0h+var_1B8]
0x140028bd1  mov     [rbp+0F0h+var_150], 0EC0196h
0x140028bd9  mov     [rbp+0F0h+var_128], rax
0x140028bdd  lea     rdx, [rsp+1F0h+var_180]
0x140028be2  mov     [rbp+0F0h+var_130], 4010182h
0x140028be9  mov     rcx, rbx
0x140028bec  mov     dword ptr [rbp+0F0h+var_120], 20h ; ' '
0x140028bf3  mov     [rbp+0F0h+var_160], 0
0x140028bfb  mov     rax, [rdi+38h]
0x140028bff  mov     [rbp+0F0h+var_158], rax
0x140028c03  call    NdisWanSubmitNdisRequest
0x140028c08  mov     rcx, r14; SpinLock
0x140028c0b  mov     ebx, eax
0x140028c0d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028c14  nop     dword ptr [rax+rax+00h]
0x140028c19  mov     rcx, rdi
0x140028c1c  mov     [rdi+2E8h], al
0x140028c22  call    DerefVc
0x140028c27  mov     dl, [rdi+2E8h]; NewIrql
0x140028c2d  mov     rcx, r14; SpinLock
0x140028c30  call    cs:__imp_KeReleaseSpinLock
0x140028c37  nop     dword ptr [rax+rax+00h]
0x140028c3c  test    ebx, ebx
0x140028c3e  jnz     loc_140028CFF
0x140028c44  mov     eax, dword ptr [rsp+1F0h+var_1B8]
0x140028c48  mov     [rdi+110h], eax
0x140028c4e  mov     eax, dword ptr [rsp+1F0h+var_1B8+4]
0x140028c52  mov     [rdi+114h], eax
0x140028c58  mov     eax, dword ptr [rsp+1F0h+var_1B8+8]
0x140028c5c  test    sil, sil
0x140028c5f  jz      short loc_140028CB9
0x140028c61  or      [rdi+120h], eax
0x140028c67  mov     eax, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x140028c6b  or      [rdi+124h], eax
0x140028c71  mov     r8d, [rdi+124h]
0x140028c78  mov     r9d, [rdi+120h]
0x140028c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140028c86  lea     rax, WPP_GLOBAL_Control
0x140028c8d  cmp     rcx, rax
0x140028c90  jz      short loc_140028CC9
0x140028c92  mov     eax, [rcx+2Ch]
0x140028c95  test    al, 20h
0x140028c97  jz      short loc_140028CC9
0x140028c99  cmp     byte ptr [rcx+29h], 5
0x140028c9d  jb      short loc_140028CC9
0x140028c9f  mov     rcx, [rcx+18h]
0x140028ca3  lea     edx, [rbx+4Ch]
0x140028ca6  mov     [rsp+1F0h+var_1D0], r8d
0x140028cab  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140028cb2  call    WPP_SF_dd
0x140028cb7  jmp     short loc_140028CC9
0x140028cb9  mov     [rdi+120h], eax
0x140028cbf  mov     eax, dword ptr [rsp+1F0h+var_1B8+0Ch]
0x140028cc3  mov     [rdi+124h], eax
0x140028cc9  mov     eax, dword ptr [rsp+1F0h+var_1A8]
0x140028ccd  mov     [rdi+128h], eax
0x140028cd3  mov     eax, dword ptr [rsp+1F0h+var_1A8+4]
0x140028cd7  mov     [rdi+12Ch], eax
0x140028cdd  mov     eax, dword ptr [rsp+1F0h+var_1A8+8]
0x140028ce1  mov     [rdi+130h], eax
0x140028ce7  mov     eax, dword ptr [rsp+1F0h+var_1A8+0Ch]
0x140028ceb  mov     [rdi+134h], eax
0x140028cf1  jmp     short loc_140028CFF
0x140028cf3  call    cs:__imp_KeReleaseSpinLock
0x140028cfa  nop     dword ptr [rax+rax+00h]
0x140028cff  mov     eax, cs:glMaxMTU
0x140028d05  xor     ebx, ebx
0x140028d07  mov     [rdi+138h], eax
0x140028d0d  mov     eax, cs:glMRRU
0x140028d13  mov     [rdi+13Ch], eax
0x140028d19  movups  xmm0, xmmword ptr [rdi+110h]
0x140028d20  movups  xmmword ptr [r15+8], xmm0
0x140028d25  movups  xmm1, xmmword ptr [rdi+120h]
0x140028d2c  movups  xmmword ptr [r15+18h], xmm1
0x140028d31  movups  xmm0, xmmword ptr [rdi+130h]
0x140028d38  movups  xmmword ptr [r15+28h], xmm0
0x140028d3d  mov     rax, [rdi+28h]
0x140028d41  mov     [r15], rax
0x140028d44  test    rdi, rdi
0x140028d47  jz      short loc_140028D86
0x140028d49  lea     rsi, [rdi+2E0h]
0x140028d50  mov     rcx, rsi; SpinLock
0x140028d53  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140028d5a  nop     dword ptr [rax+rax+00h]
0x140028d5f  mov     [rdi+2E8h], al
0x140028d65  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x140028d69  jnz     short loc_140028D75
0x140028d6b  mov     rcx, rdi; Entry
0x140028d6e  call    DoDerefLinkCBWork
0x140028d73  jmp     short loc_140028D86
0x140028d75  mov     dl, al; NewIrql
0x140028d77  mov     rcx, rsi; SpinLock
0x140028d7a  call    cs:__imp_KeReleaseSpinLock
0x140028d81  nop     dword ptr [rax+rax+00h]
0x140028d86  mov     eax, ebx
0x140028d88  mov     rcx, [rbp+0F0h+var_30]
0x140028d8f  xor     rcx, rsp; StackCookie
0x140028d92  call    __security_check_cookie
0x140028d97  mov     rbx, [rsp+1F0h+arg_8]
0x140028d9f  add     rsp, 1D0h
0x140028da6  pop     r15
0x140028da8  pop     r14
0x140028daa  pop     rdi
0x140028dab  pop     rsi
0x140028dac  pop     rbp
  ... truncated ...
```
