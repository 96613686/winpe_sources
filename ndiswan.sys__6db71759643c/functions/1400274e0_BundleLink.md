# BundleLink

- ea: `0x1400274e0`
- end: `0x140027a40`
- name: `BundleLink`
- size: `1376`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003870`
- `0x140005494`
- `0x14000550c`
- `0x140005930`
- `0x1400084d8`
- `0x1400085b0`
- `0x14000899c`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a648`
- `0x14000a744`
- `0x14000b13c`
- `0x1400274e0`
- `0x14002a8e0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400277ce`
- `ntoskrnl!KeClearEvent` at `0x1400277ce`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027809`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027809`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400277e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027949`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027993`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400279d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027a17`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400277e7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027949`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027993`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400279d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140027a17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400277a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027818`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400278bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002796c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279f0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400277a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027818`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400278bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002796c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400279f0`

## pseudocode

```c
__int64 __fastcall BundleLink(__int64 *a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  void *v5; // rsi
  int v8; // r14d
  int v9; // eax
  __int64 v10; // rcx
  char *v11; // rdi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  _QWORD *v15; // r15
  _QWORD *v16; // r8
  _QWORD *v17; // r11
  _QWORD *v18; // r10
  KIRQL v19; // al
  PVOID v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r8
  _QWORD *v25; // rcx
  unsigned int v26; // eax
  _QWORD *v27; // rbx
  KIRQL v28; // al
  bool v29; // zf
  KIRQL v30; // al
  KIRQL v31; // al
  PVOID v33; // [rsp+30h] [rbp-40h] BYREF
  PVOID v34; // [rsp+38h] [rbp-38h] BYREF
  __int128 v35; // [rsp+40h] [rbp-30h]
  PVOID Entry; // [rsp+A0h] [rbp+30h] BYREF

  v5 = 0;
  v34 = 0;
  v33 = 0;
  Entry = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_5659416b879e33cc7e241cd80588418e_Traceguids);
  }
  *a5 = 0;
  if ( a2 < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 16);
    }
    return (unsigned int)-1073741820;
  }
  if ( (Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 0x10) != 0 )
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState & 1;
  else
    v9 = Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline();
  v10 = a1[1];
  if ( !v9 )
  {
    if ( !(unsigned __int8)AreLinkAndBundleValid(v10, 1, &v34, &Entry) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a1[1]);
      }
      v8 = 601;
      goto LABEL_20;
    }
    if ( (unsigned __int8)IsBundleValid(*a1, 1, &v33) )
    {
      v5 = v33;
      v8 = 0;
      v11 = (char *)Entry;
      if ( v33 != Entry )
        goto LABEL_51;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
LABEL_45:
        v8 = 601;
        goto LABEL_70;
      }
      v13 = 41;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      v11 = (char *)Entry;
      v5 = v33;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        goto LABEL_45;
      }
      v13 = 40;
    }
    WPP_SF_qq(v12->AttachedDevice, v13, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v5, v11);
    goto LABEL_45;
  }
  v8 = ValidateLinkAndBundle(v10, 1, &v34, &Entry);
  if ( v8 >= 0 )
  {
    v8 = ValidateBundle(*a1, 1, &v33);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v11 = (char *)Entry;
        v5 = v33;
      }
      else
      {
        v5 = v33;
        v11 = (char *)Entry;
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v33, Entry);
      }
      goto LABEL_70;
    }
    v5 = v33;
    v11 = (char *)Entry;
    if ( v33 == Entry )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, v33, Entry);
      }
      v8 = -1073741816;
      goto LABEL_70;
    }
LABEL_51:
    v11[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 221);
    *((_DWORD *)v11 + 5) = 1;
    if ( *((_DWORD *)v11 + 42) )
    {
      KeClearEvent((PRKEVENT)(v11 + 176));
      *((_DWORD *)v11 + 4) |= 0x20u;
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 221, v11[1776]);
      KeWaitForSingleObject(v11 + 176, UserRequest, 0, 0, 0);
      v11[1776] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 221);
    }
    v14 = *((_QWORD *)v11 + 38);
    v35 = 0;
    v15 = 0;
    v16 = *(_QWORD **)(v14 + 160);
    if ( v16 )
    {
      v17 = (_QWORD *)*((_QWORD *)&v35 + 1);
      do
      {
        v18 = (_QWORD *)*v16;
        if ( !*v16 )
          *(_QWORD *)(v14 + 168) = 0;
        *v16 = 0;
        *(_QWORD *)(v14 + 160) = v18;
        *(_DWORD *)(v14 + 176) -= *(_DWORD *)(*(unsigned __int16 *)(v16[2] + 10LL) + v16[2] + 116LL);
        --*(_DWORD *)(v14 + 184);
        if ( v15 )
        {
          *v17 = v16;
          v18 = *(_QWORD **)(v14 + 160);
        }
        else
        {
          v15 = v16;
        }
        v17 = v16;
        v16 = v18;
      }
      while ( v18 );
    }
    RemoveLinkFromBundle(v11);
    v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 221);
    v20 = v34;
    *((_BYTE *)v5 + 1776) = v19;
    AddLinkToBundle(v5, v20);
    SetBundleFlags(v5, v21, v22, v23);
    if ( v15 )
    {
      v24 = *((_QWORD *)v5 + 38) + 160LL;
      do
      {
        v25 = v15;
        v15 = (_QWORD *)*v15;
        *v25 = 0;
        if ( *(_QWORD *)v24 )
          **(_QWORD **)(v24 + 8) = v25;
        else
          *(_QWORD *)v24 = v25;
        *(_QWORD *)(v24 + 8) = v25;
        *(_DWORD *)(v24 + 16) += *(_DWORD *)(*(unsigned __int16 *)(v25[2] + 10LL) + v25[2] + 116LL);
        v26 = *(_DWORD *)(v24 + 24) + 1;
        *(_DWORD *)(v24 + 24) = v26;
        if ( v26 > *(_DWORD *)(v24 + 28) )
          *(_DWORD *)(v24 + 28) = v26;
      }
      while ( v15 );
    }
    KeReleaseSpinLock((PKSPIN_LOCK)v5 + 221, *((_BYTE *)v5 + 1776));
    goto LABEL_70;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a1[1]);
  }
LABEL_20:
  v11 = (char *)Entry;
LABEL_70:
  v27 = v34;
  if ( v34 )
  {
    v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v34 + 92);
    *((_BYTE *)v27 + 744) = v28;
    v29 = (*((_DWORD *)v27 + 7))-- == 1;
    if ( v29 )
      DoDerefLinkCBWork(v27);
    else
      KeReleaseSpinLock(v27 + 92, v28);
  }
  if ( v11 )
  {
    v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v11 + 221);
    v11[1776] = v30;
    v29 = (*((_DWORD *)v11 + 6))-- == 1;
    if ( v29 )
      DoDerefBundleCBWork(v11);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v11 + 221, v30);
  }
  if ( v5 )
  {
    v31 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v5 + 221);
    *((_BYTE *)v5 + 1776) = v31;
    v29 = (*((_DWORD *)v5 + 6))-- == 1;
    if ( v29 )
      DoDerefBundleCBWork(v5);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v5 + 221, v31);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400274e0  mov     [rsp-28h+arg_10], rbx
0x1400274e5  mov     [rsp-28h+arg_18], rsi
0x1400274ea  push    rbp
0x1400274eb  push    rdi
0x1400274ec  push    r12
0x1400274ee  push    r14
0x1400274f0  push    r15
0x1400274f2  mov     rbp, rsp
0x1400274f5  sub     rsp, 70h
0x1400274f9  xor     esi, esi
0x1400274fb  mov     [rbp+var_38], 0
0x140027503  mov     [rbp+var_40], rsi
0x140027507  mov     edi, edx
0x140027509  mov     rbx, rcx
0x14002750c  mov     [rbp+Entry], 0
0x140027514  mov     rcx, cs:WPP_GLOBAL_Control
0x14002751b  lea     r15, WPP_GLOBAL_Control
0x140027522  lea     r14, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140027529  lea     r12d, [rsi+20h]
0x14002752d  cmp     rcx, r15
0x140027530  jz      short loc_14002754F
0x140027532  mov     eax, [rcx+2Ch]
0x140027535  test    r12b, al
0x140027538  jz      short loc_14002754F
0x14002753a  cmp     byte ptr [rcx+29h], 5
0x14002753e  jb      short loc_14002754F
0x140027540  mov     rcx, [rcx+18h]
0x140027544  lea     edx, [rsi+22h]
0x140027547  mov     r8, r14
0x14002754a  call    WPP_SF_
0x14002754f  mov     rax, [rbp+arg_20]
0x140027553  mov     [rax], esi
0x140027555  cmp     edi, 10h
0x140027558  jnb     short loc_14002759B
0x14002755a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027561  cmp     rcx, r15
0x140027564  jz      short loc_140027590
0x140027566  mov     eax, [rcx+2Ch]
0x140027569  test    r12b, al
0x14002756c  jz      short loc_140027590
0x14002756e  cmp     byte ptr [rcx+29h], 3
0x140027572  jb      short loc_140027590
0x140027574  mov     rcx, [rcx+18h]
0x140027578  mov     edx, 23h ; '#'
0x14002757d  mov     r9d, edi
0x140027580  mov     dword ptr [rsp+70h+Timeout], 10h
0x140027588  mov     r8, r14
0x14002758b  call    WPP_SF_dd
0x140027590  mov     r14d, 0C0000004h
0x140027596  jmp     loc_140027A23
0x14002759b  mov     eax, cs:Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_featureState
0x1400275a1  test    al, 10h
0x1400275a3  jz      short loc_1400275AA
0x1400275a5  and     eax, 1
0x1400275a8  jmp     short loc_1400275AF
0x1400275aa  call    Feature_VPN_BugFixes_25C_NdisWan_HandleCheck__private_IsEnabledDeviceUsageNoInline
0x1400275af  mov     rcx, [rbx+8]
0x1400275b3  lea     r9, [rbp+Entry]
0x1400275b7  lea     r8, [rbp+var_38]
0x1400275bb  mov     dl, 1
0x1400275bd  test    eax, eax
0x1400275bf  jz      loc_1400276C6
0x1400275c5  call    ValidateLinkAndBundle
0x1400275ca  mov     r14d, eax
0x1400275cd  test    eax, eax
0x1400275cf  jns     short loc_14002760D
0x1400275d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400275d8  cmp     rcx, r15
0x1400275db  jz      short loc_140027604
0x1400275dd  mov     edx, [rcx+2Ch]
0x1400275e0  test    r12b, dl
0x1400275e3  jz      short loc_140027604
0x1400275e5  cmp     byte ptr [rcx+29h], 3
0x1400275e9  jb      short loc_140027604
0x1400275eb  mov     r9, [rbx+8]
0x1400275ef  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x1400275f6  mov     rcx, [rcx+18h]
0x1400275fa  mov     edx, 24h ; '$'
0x1400275ff  call    WPP_SF_q
0x140027604  mov     rdi, [rbp+Entry]
0x140027608  jmp     loc_140027955
0x14002760d  mov     rcx, [rbx]
0x140027610  lea     r8, [rbp+var_40]
0x140027614  mov     dl, 1
0x140027616  call    ValidateBundle
0x14002761b  mov     r14d, eax
0x14002761e  test    eax, eax
0x140027620  jns     short loc_140027673
0x140027622  mov     rcx, cs:WPP_GLOBAL_Control
0x140027629  cmp     rcx, r15
0x14002762c  jz      short loc_140027666
0x14002762e  mov     eax, [rcx+2Ch]
0x140027631  test    r12b, al
0x140027634  jz      short loc_140027666
0x140027636  cmp     byte ptr [rcx+29h], 3
0x14002763a  jb      short loc_140027666
0x14002763c  mov     rsi, [rbp+var_40]
0x140027640  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140027647  mov     rdi, [rbp+Entry]
0x14002764b  mov     r9, rsi
0x14002764e  mov     rcx, [rcx+18h]
0x140027652  mov     edx, 25h ; '%'
0x140027657  mov     [rsp+70h+Timeout], rdi
0x14002765c  call    WPP_SF_qq
0x140027661  jmp     loc_140027955
0x140027666  mov     rdi, [rbp+Entry]
0x14002766a  mov     rsi, [rbp+var_40]
0x14002766e  jmp     loc_140027955
0x140027673  mov     rsi, [rbp+var_40]
0x140027677  mov     rdi, [rbp+Entry]
0x14002767b  cmp     rsi, rdi
0x14002767e  jnz     loc_140027798
0x140027684  mov     rcx, cs:WPP_GLOBAL_Control
0x14002768b  cmp     rcx, r15
0x14002768e  jz      short loc_1400276BB
0x140027690  mov     eax, [rcx+2Ch]
0x140027693  test    r12b, al
0x140027696  jz      short loc_1400276BB
0x140027698  cmp     byte ptr [rcx+29h], 3
0x14002769c  jb      short loc_1400276BB
0x14002769e  mov     rcx, [rcx+18h]
0x1400276a2  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x1400276a9  mov     edx, 26h ; '&'
0x1400276ae  mov     [rsp+70h+Timeout], rdi
0x1400276b3  mov     r9, rsi
0x1400276b6  call    WPP_SF_qq
0x1400276bb  mov     r14d, 0C0000008h
0x1400276c1  jmp     loc_140027955
0x1400276c6  call    AreLinkAndBundleValid
0x1400276cb  test    al, al
0x1400276cd  jnz     short loc_140027709
0x1400276cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400276d6  cmp     rcx, r15
0x1400276d9  jz      short loc_1400276FE
0x1400276db  mov     eax, [rcx+2Ch]
0x1400276de  test    r12b, al
0x1400276e1  jz      short loc_1400276FE
0x1400276e3  cmp     byte ptr [rcx+29h], 3
0x1400276e7  jb      short loc_1400276FE
0x1400276e9  mov     r9, [rbx+8]
0x1400276ed  mov     edx, 27h ; '''
0x1400276f2  mov     rcx, [rcx+18h]
0x1400276f6  mov     r8, r14
0x1400276f9  call    WPP_SF_q
0x1400276fe  mov     r14d, 259h
0x140027704  jmp     loc_140027604
0x140027709  mov     rcx, [rbx]
0x14002770c  lea     r8, [rbp+var_40]
0x140027710  mov     dl, 1
0x140027712  call    IsBundleValid
0x140027717  test    al, al
0x140027719  jnz     short loc_140027761
0x14002771b  mov     rcx, cs:WPP_GLOBAL_Control
0x140027722  mov     rdi, [rbp+Entry]
0x140027726  mov     rsi, [rbp+var_40]
0x14002772a  cmp     rcx, r15
0x14002772d  jz      short loc_140027756
0x14002772f  mov     eax, [rcx+2Ch]
0x140027732  test    r12b, al
0x140027735  jz      short loc_140027756
0x140027737  cmp     byte ptr [rcx+29h], 3
0x14002773b  jb      short loc_140027756
0x14002773d  mov     edx, 28h ; '('
0x140027742  mov     r8, r14
0x140027745  mov     rcx, [rcx+18h]
0x140027749  mov     r9, rsi
0x14002774c  mov     [rsp+70h+Timeout], rdi
0x140027751  call    WPP_SF_qq
0x140027756  mov     r14d, 259h
0x14002775c  jmp     loc_140027955
0x140027761  mov     rsi, [rbp+var_40]
0x140027765  xor     r14d, r14d
0x140027768  mov     rdi, [rbp+Entry]
0x14002776c  cmp     rsi, rdi
0x14002776f  jnz     short loc_140027798
0x140027771  mov     rcx, cs:WPP_GLOBAL_Control
0x140027778  cmp     rcx, r15
0x14002777b  jz      short loc_140027756
0x14002777d  mov     eax, [rcx+2Ch]
0x140027780  test    r12b, al
0x140027783  jz      short loc_140027756
0x140027785  cmp     byte ptr [rcx+29h], 3
0x140027789  jb      short loc_140027756
0x14002778b  lea     edx, [r14+29h]
0x14002778f  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140027796  jmp     short loc_140027745
0x140027798  lea     r15, [rdi+6E8h]
0x14002779f  mov     rcx, r15; SpinLock
0x1400277a2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400277a9  nop     dword ptr [rax+rax+00h]
0x1400277ae  mov     [rdi+6F0h], al
0x1400277b4  mov     dword ptr [rdi+14h], 1
0x1400277bb  cmp     dword ptr [rdi+0A8h], 0
0x1400277c2  jz      short loc_14002782A
0x1400277c4  lea     rbx, [rdi+0B0h]
0x1400277cb  mov     rcx, rbx; Event
0x1400277ce  call    cs:__imp_KeClearEvent
0x1400277d5  nop     dword ptr [rax+rax+00h]
0x1400277da  or      [rdi+10h], r12d
0x1400277de  mov     rcx, r15; SpinLock
0x1400277e1  mov     dl, [rdi+6F0h]; NewIrql
0x1400277e7  call    cs:__imp_KeReleaseSpinLock
0x1400277ee  nop     dword ptr [rax+rax+00h]
0x1400277f3  xor     r9d, r9d; Alertable
0x1400277f6  mov     [rsp+70h+Timeout], 0; Timeout
0x1400277ff  xor     r8d, r8d; WaitMode
0x140027802  mov     rcx, rbx; Object
0x140027805  lea     edx, [r9+6]; WaitReason
0x140027809  call    cs:__imp_KeWaitForSingleObject
0x140027810  nop     dword ptr [rax+rax+00h]
0x140027815  mov     rcx, r15; SpinLock
0x140027818  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002781f  nop     dword ptr [rax+rax+00h]
0x140027824  mov     [rdi+6F0h], al
0x14002782a  mov     r9, [rdi+130h]
0x140027831  xorps   xmm0, xmm0
0x140027834  movups  [rbp+var_30], xmm0
0x140027838  mov     r15, qword ptr [rbp+var_30]
0x14002783c  mov     r8, [r9+0A0h]
0x140027843  test    r8, r8
0x140027846  jz      short loc_1400278A2
0x140027848  mov     r11, qword ptr [rbp+var_30+8]
0x14002784c  mov     r10, [r8]
0x14002784f  test    r10, r10
0x140027852  jnz     short loc_14002785B
0x140027854  mov     [r9+0A8h], r10
0x14002785b  mov     qword ptr [r8], 0
0x140027862  mov     [r9+0A0h], r10
0x140027869  mov     rcx, [r8+10h]
0x14002786d  movzx   eax, word ptr [rcx+0Ah]
0x140027871  mov     edx, [rax+rcx+74h]
0x140027875  sub     [r9+0B0h], edx
0x14002787c  dec     dword ptr [r9+0B8h]
0x140027883  test    r15, r15
0x140027886  jnz     short loc_14002788D
0x140027888  mov     r15, r8
0x14002788b  jmp     short loc_140027897
0x14002788d  mov     [r11], r8
0x140027890  mov     r10, [r9+0A0h]
0x140027897  mov     r11, r8
0x14002789a  mov     r8, r10
0x14002789d  test    r10, r10
0x1400278a0  jnz     short loc_14002784C
0x1400278a2  mov     rdx, [rbp+var_38]
0x1400278a6  mov     r8b, 1
0x1400278a9  mov     rcx, rdi; Entry
0x1400278ac  call    RemoveLinkFromBundle
0x1400278b1  lea     r12, [rsi+6E8h]
0x1400278b8  mov     rcx, r12; SpinLock
0x1400278bb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400278c2  nop     dword ptr [rax+rax+00h]
0x1400278c7  mov     rdx, [rbp+var_38]
0x1400278cb  mov     rcx, rsi
0x1400278ce  mov     [rsi+6F0h], al
0x1400278d4  call    AddLinkToBundle
0x1400278d9  mov     rcx, rsi
0x1400278dc  call    SetBundleFlags
0x1400278e1  test    r15, r15
0x1400278e4  jz      short loc_140027940
0x1400278e6  mov     r8, [rsi+130h]
0x1400278ed  add     r8, 0A0h
0x1400278f4  mov     rcx, r15
0x1400278f7  mov     r15, [r15]
0x1400278fa  mov     qword ptr [rcx], 0
0x140027901  cmp     qword ptr [r8], 0
0x140027905  jnz     short loc_14002790C
0x140027907  mov     [r8], rcx
0x14002790a  jmp     short loc_140027913
0x14002790c  mov     rax, [r8+8]
0x140027910  mov     [rax], rcx
0x140027913  mov     [r8+8], rcx
0x140027917  mov     rcx, [rcx+10h]
0x14002791b  movzx   eax, word ptr [rcx+0Ah]
0x14002791f  mov     edx, [rax+rcx+74h]
0x140027923  add     [r8+10h], edx
0x140027927  mov     eax, [r8+18h]
0x14002792b  inc     eax
0x14002792d  mov     [r8+18h], eax
0x140027931  cmp     eax, [r8+1Ch]
0x140027935  jbe     short loc_14002793B
0x140027937  mov     [r8+1Ch], eax
0x14002793b  test    r15, r15
0x14002793e  jnz     short loc_1400278F4
0x140027940  mov     dl, [rsi+6F0h]; NewIrql
0x140027946  mov     rcx, r12; SpinLock
0x140027949  call    cs:__imp_KeReleaseSpinLock
0x140027950  nop     dword ptr [rax+rax+00h]
0x140027955  mov     rbx, [rbp+var_38]
0x140027959  or      r12d, 0FFFFFFFFh
0x14002795d  test    rbx, rbx
0x140027960  jz      short loc_14002799F
0x140027962  lea     r15, [rbx+2E0h]
0x140027969  mov     rcx, r15; SpinLock
0x14002796c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140027973  nop     dword ptr [rax+rax+00h]
0x140027978  mov     [rbx+2E8h], al
0x14002797e  add     [rbx+1Ch], r12d
0x140027982  jnz     short loc_14002798E
0x140027984  mov     rcx, rbx; Entry
0x140027987  call    DoDerefLinkCBWork
  ... truncated ...
```
