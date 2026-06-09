# CscBackPatchFobxCallback

- ea: `0x14004f0a0`
- end: `0x14004f87e`
- name: `CscBackPatchFobxCallback`
- size: `2014`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400084f0`
- `0x14000e100`
- `0x140012118`
- `0x14001404c`
- `0x1400169d4`
- `0x140016a04`
- `0x140018930`
- `0x140018b50`
- `0x14001bd48`
- `0x14001be94`
- `0x14001c114`
- `0x14001d06c`
- `0x14002f0f0`
- `0x14004f0a0`
- `0x140074330`
- `0x14007f870`
- `0x140080800`

## import_xrefs

- `rdbss!RxNotifyBufferingManagerOfCompletedOpen` at `0x14004f3c7`
- `rdbss!RxNotifyBufferingManagerOfCompletedOpen` at `0x14004f3c7`
- `rdbss!RxDeregisterSrvOpenWithBufferingManager` at `0x14004f267`
- `rdbss!RxDeregisterSrvOpenWithBufferingManager` at `0x14004f267`
- `rdbss!RxNotifyBufferingManagerOfPendingOpen` at `0x14004f2b7`
- `rdbss!RxNotifyBufferingManagerOfPendingOpen` at `0x14004f2b7`
- `rdbss!RxpTrackDereference` at `0x14004f80d`
- `rdbss!RxpTrackDereference` at `0x14004f80d`
- `rdbss!RxDereference` at `0x14004f7e8`
- `rdbss!RxDereference` at `0x14004f7e8`
- `rdbss!RxReference` at `0x14004f282`
- `rdbss!RxReference` at `0x14004f282`
- `rdbss!RxpTrackReference` at `0x14004f2a7`
- `rdbss!RxpTrackReference` at `0x14004f2a7`

## pseudocode

```c
__int64 __fastcall CscBackPatchFobxCallback(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int16 *v3; // rax
  __int16 v7; // r9
  __int64 v8; // rax
  __int64 v9; // rbp
  __int64 v10; // r8
  __int16 v11; // r9
  __int16 v12; // r10
  char v13; // al
  __int64 v14; // r12
  int NetInfoToRdr; // esi
  int v16; // ebp
  __int64 v17; // r13
  __int64 v18; // r9
  int v19; // ebp
  void (__fastcall *v20)(__int64); // rax
  int v21; // eax
  void (__fastcall *v22)(__int64); // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r9
  __int128 v27; // [rsp+50h] [rbp-68h] BYREF
  __int128 v28; // [rsp+60h] [rbp-58h]
  char v29; // [rsp+C0h] [rbp+8h]
  bool v30; // [rsp+C8h] [rbp+10h]
  __int16 v31; // [rsp+D0h] [rbp+18h]
  unsigned int v32; // [rsp+D8h] [rbp+20h]

  v3 = (__int16 *)a3[2];
  v27 = 0;
  v7 = *v3;
  v8 = a2[4];
  v28 = 0;
  v31 = v7;
  v30 = v7 == -5087;
  v9 = *(_QWORD *)(v8 + 40);
  *(_QWORD *)(a1 + 64) = a2;
  *(_QWORD *)(a1 + 72) = a2[4];
  CscGetContexts((_QWORD *)a1, &v27);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v13 = 89;
    if ( v11 != v12 )
      v13 = 78;
    WPP_SF_qqqDDDc(
      WPP_GLOBAL_Control->AttachedDevice,
      a2[4],
      78,
      a2,
      a2[4],
      v9,
      *(_DWORD *)(v9 + 56),
      *(_DWORD *)(a2[4] + 124LL),
      *(_DWORD *)(a2[4] + 120LL),
      v13);
  }
  v14 = v28;
  if ( (*(_DWORD *)(v28 + 24) & 0x809) != 0 )
  {
    NetInfoToRdr = 0;
    v16 = 2146;
    goto LABEL_95;
  }
  v17 = v27;
  NetInfoToRdr = -1073741811;
  if ( !(_QWORD)v27 )
  {
    NetInfoToRdr = CscCreateAndInitializeFobxContext(a2, &v27, 0, 0);
    if ( NetInfoToRdr )
    {
      v16 = 2162;
      goto LABEL_95;
    }
    v14 = v28;
    v17 = v27;
  }
  if ( !*(_DWORD *)(a2[4] + 88LL) && (*(_DWORD *)(v14 + 24) & 4) != 0 )
  {
    NetInfoToRdr = 0;
    v16 = 2178;
    goto LABEL_95;
  }
  if ( (*(_DWORD *)(v9 + 56) & 0x10) != 0 )
  {
    NetInfoToRdr = -1073741584;
    v16 = 2195;
    goto LABEL_95;
  }
  CscNotifyCleanup(a3[2], a2);
  CscPopulateRxCreateInfoFromContexts(a1);
  *(_QWORD *)(a1 + 560) = 0;
  if ( (*(_DWORD *)(v14 + 24) & 2) != 0 )
  {
    v29 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL) + 48LL) + 352LL) + 80LL) )
    {
      if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
      {
        v19 = -1073741536;
      }
      else
      {
        *(_OWORD *)(a1 + 208) = 0;
        *(_OWORD *)(a1 + 224) = 0;
        *(_QWORD *)(a1 + 240) = 0;
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL)
                                                                         + 48LL)
                                                             + 352LL)
                                                 + 80LL))(a1);
      }
    }
    else
    {
      v19 = -1073741822;
    }
  }
  else
  {
    v32 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    v29 = 1;
    RxDeregisterSrvOpenWithBufferingManager(a2[4]);
    *(_DWORD *)(a3[2] + 156LL) |= 0x800000u;
    RxReference(a2);
    RxpTrackReference(8u, "CscBackPatchFobxCallback", 0x8D4u, a2);
    RxNotifyBufferingManagerOfPendingOpen(a2[4]);
    *(_DWORD *)(a1 + 120) |= 0x20000000u;
    *(_DWORD *)(v17 + 4) |= 0x10u;
    *(_DWORD *)(a2[4] + 72LL) &= ~0x200u;
    while ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL) + 48LL) + 352LL) + 56LL) )
    {
      if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
      {
        v19 = -1073741536;
        goto LABEL_32;
      }
      *(_OWORD *)(a1 + 208) = 0;
      *(_OWORD *)(a1 + 224) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL)
                                                                       + 48LL)
                                                           + 352LL)
                                               + 56LL))(a1);
      if ( v19 == -1069481983 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v32);
        }
        if ( ++v32 < 0x3E8 )
          continue;
      }
      goto LABEL_32;
    }
    v19 = -1073741822;
LABEL_32:
    *(_DWORD *)(v17 + 4) &= ~0x10u;
    if ( v19 == -1069481983 )
      v19 = -1073741595;
    RxNotifyBufferingManagerOfCompletedOpen(a2[4]);
    if ( v19 >= 0 && (*(_DWORD *)(v14 + 24) & 0x10000) == 0 )
      *((_DWORD *)a3 + 24) = *(_DWORD *)(a1 + 736);
    *(_DWORD *)(a3[2] + 156LL) &= ~0x800000u;
  }
  v10 = *((_QWORD *)&v27 + 1);
  *(_DWORD *)(*((_QWORD *)&v27 + 1) + 4LL) |= 0x10u;
  *(_QWORD *)(v10 + 88) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL) + 48LL)
                                                + 352LL)
                                    + 128LL);
  *(_DWORD *)(v14 + 24) |= 4u;
  *(_QWORD *)(v14 + 40) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL) + 48LL)
                                                + 352LL)
                                    + 136LL);
  *(_DWORD *)(v17 + 4) |= 2u;
  *(_QWORD *)(v17 + 64) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL) + 48LL)
                                                + 352LL)
                                    + 144LL);
  if ( v19 >= 0 )
  {
    *(_DWORD *)(v14 + 24) |= 2u;
    if ( *(_DWORD *)(a2[4] + 88LL) )
    {
      *(_DWORD *)(v17 + 4) |= 1u;
      CscUpdateRdrOpenCount(*(_QWORD *)(a3[1] + 8LL), a2[4], 1, v18);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      v20 = *(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL)
                                                                   + 48LL)
                                                       + 352LL)
                                           + 104LL);
      if ( v20 )
        v20(a1);
    }
    if ( !v29 )
    {
      NetInfoToRdr = 0;
      v16 = 2434;
      goto LABEL_95;
    }
    v21 = *(_DWORD *)(v17 + 4);
    if ( (v21 & 0x20) != 0 )
    {
      if ( (v21 & 1) != 0 )
      {
        v22 = *(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3[2] + 120LL) + 32LL)
                                                                     + 48LL)
                                                         + 352LL)
                                             + 104LL);
        if ( v22 )
          v22(a1);
        *(_DWORD *)(v17 + 4) &= ~1u;
        CscUpdateRdrOpenCount(*(_QWORD *)(a3[1] + 8LL), a2[4], 0xFFFFFFFFLL, v18);
      }
      CscCloseSrvOpen(a1);
      v16 = 2479;
      goto LABEL_94;
    }
    NetInfoToRdr = CscIssueQueryNetInfoToRdr(a1, *a3, a3 + 5);
    if ( NetInfoToRdr < 0 )
    {
      v16 = 2495;
LABEL_94:
      RxDereference(a2, LHS_SharedLockHeld);
      RxpTrackDereference(8u, "CscBackPatchFobxCallback", 0xA50u, a2);
      goto LABEL_95;
    }
    if ( ((a3[11] & 0x10) != 0) != v30 )
    {
      NetInfoToRdr = -1073741565;
      v16 = 2507;
      if ( v31 != -5087 )
        NetInfoToRdr = -1073741638;
      goto LABEL_94;
    }
    if ( v31 != -5087 )
    {
      v23 = a3[3];
      if ( *(_QWORD *)(v23 + 32) != a3[7] || *(_QWORD *)(v23 + 56) != a3[10] )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
        v24 = a2[4];
        if ( (*(_DWORD *)(v24 + 124) & 2) == 0 && *(_DWORD *)(v24 + 88) )
        {
          NetInfoToRdr = -1073741585;
          v16 = 2564;
          goto LABEL_94;
        }
        *((_BYTE *)a3 + 144) |= 1u;
      }
    }
    v16 = 0;
    v25 = a3[8];
    if ( *(_QWORD *)(a3[3] + 40LL) != v25 || (a3[18] & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v25);
      *((_BYTE *)a3 + 144) |= 2u;
      CscStoreSetExplicitAccessEntry(
        *(_QWORD *)(*(_QWORD *)(a3[1] + 8LL) + 56LL),
        0,
        *(_QWORD *)(a2[4] + 40LL) + 112,
        *(_DWORD *)(a2[4] + 152LL),
        3);
    }
    if ( v31 == -5087 || (*(_DWORD *)(v14 + 24) & 0x10000) != 0 )
    {
      if ( a3[17] )
      {
LABEL_93:
        NetInfoToRdr = 0;
        goto LABEL_94;
      }
    }
    else
    {
      a3[16] = a2;
    }
    a3[17] = a2;
    goto LABEL_93;
  }
  if ( !(unsigned __int8)CscCheckRdrStatusTransitionIfNetErr((unsigned int)v19, *a3, a3[2]) )
    CscTransitionFcbOffline(a3[2], 0, 1024, 0);
  NetInfoToRdr = v19;
  v16 = 2382;
  if ( v29 )
    goto LABEL_94;
LABEL_95:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_DdDdd(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned int *)(*((_QWORD *)&v27 + 1) + 4LL),
      v10,
      (unsigned int)NetInfoToRdr,
      v16,
      *(_DWORD *)(*((_QWORD *)&v27 + 1) + 4LL),
      a3[18] & 1,
      (*((unsigned __int8 *)a3 + 144) >> 1) & 1);
  return (unsigned int)NetInfoToRdr;
}

```

## disassembly

```asm
0x14004f0a0  push    rbx
0x14004f0a2  push    rbp
0x14004f0a3  push    rsi
0x14004f0a4  push    r12
0x14004f0a6  push    r13
0x14004f0a8  push    r14
0x14004f0aa  push    r15
0x14004f0ac  sub     rsp, 80h
0x14004f0b3  mov     rax, [r8+10h]
0x14004f0b7  xorps   xmm0, xmm0
0x14004f0ba  mov     r10d, 0EC21h
0x14004f0c0  mov     r14, rdx
0x14004f0c3  mov     rbx, r8
0x14004f0c6  mov     r15, rcx
0x14004f0c9  movups  [rsp+0B8h+var_68], xmm0
0x14004f0ce  movzx   r9d, word ptr [rax]
0x14004f0d2  mov     rax, [rdx+20h]
0x14004f0d6  cmp     r9w, r10w
0x14004f0da  movups  [rsp+0B8h+var_58], xmm0
0x14004f0df  mov     [rsp+0B8h+arg_10], r9w
0x14004f0e8  setz    [rsp+0B8h+arg_8]
0x14004f0f0  mov     rbp, [rax+28h]
0x14004f0f4  mov     [rcx+40h], rdx
0x14004f0f8  mov     rax, [rdx+20h]
0x14004f0fc  lea     rdx, [rsp+0B8h+var_68]
0x14004f101  mov     [rcx+48h], rax
0x14004f105  call    CscGetContexts
0x14004f10a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f111  lea     rax, WPP_GLOBAL_Control
0x14004f118  cmp     rcx, rax
0x14004f11b  jz      short loc_14004F168
0x14004f11d  mov     eax, [rcx+2Ch]
0x14004f120  test    al, 20h
0x14004f122  jz      short loc_14004F168
0x14004f124  mov     rdx, [r14+20h]
0x14004f128  mov     eax, 59h ; 'Y'
0x14004f12d  mov     rcx, [rcx+18h]
0x14004f131  cmp     r9w, r10w
0x14004f135  mov     r9, r14
0x14004f138  lea     r8d, [rax-0Bh]
0x14004f13c  cmovnz  eax, r8d
0x14004f140  mov     [rsp+0B8h+var_70], al
0x14004f144  mov     eax, [rdx+78h]
0x14004f147  mov     [rsp+0B8h+var_78], eax
0x14004f14b  mov     eax, [rdx+7Ch]
0x14004f14e  mov     [rsp+0B8h+var_80], eax
0x14004f152  mov     eax, [rbp+38h]
0x14004f155  mov     [rsp+0B8h+var_88], eax
0x14004f159  mov     [rsp+0B8h+var_90], rbp
0x14004f15e  mov     [rsp+0B8h+var_98], rdx
0x14004f163  call    WPP_SF_qqqDDDc
0x14004f168  mov     r12, qword ptr [rsp+0B8h+var_58]
0x14004f16d  test    dword ptr [r12+18h], 809h
0x14004f176  jz      short loc_14004F184
0x14004f178  xor     esi, esi
0x14004f17a  mov     ebp, 862h
0x14004f17f  jmp     loc_14004F819
0x14004f184  mov     r13, qword ptr [rsp+0B8h+var_68]
0x14004f189  mov     esi, 0C000000Dh
0x14004f18e  test    r13, r13
0x14004f191  jnz     short loc_14004F1C0
0x14004f193  xor     r9d, r9d
0x14004f196  lea     rdx, [rsp+0B8h+var_68]
0x14004f19b  xor     r8d, r8d
0x14004f19e  mov     rcx, r14
0x14004f1a1  call    CscCreateAndInitializeFobxContext
0x14004f1a6  mov     esi, eax
0x14004f1a8  test    eax, eax
0x14004f1aa  jz      short loc_14004F1B6
0x14004f1ac  mov     ebp, 872h
0x14004f1b1  jmp     loc_14004F819
0x14004f1b6  mov     r12, qword ptr [rsp+0B8h+var_58]
0x14004f1bb  mov     r13, qword ptr [rsp+0B8h+var_68]
0x14004f1c0  mov     rax, [r14+20h]
0x14004f1c4  cmp     dword ptr [rax+58h], 0
0x14004f1c8  jnz     short loc_14004F1DF
0x14004f1ca  mov     eax, [r12+18h]
0x14004f1cf  test    al, 4
0x14004f1d1  jz      short loc_14004F1DF
0x14004f1d3  xor     esi, esi
0x14004f1d5  mov     ebp, 882h
0x14004f1da  jmp     loc_14004F819
0x14004f1df  mov     eax, [rbp+38h]
0x14004f1e2  test    al, 10h
0x14004f1e4  jz      short loc_14004F1F5
0x14004f1e6  mov     esi, 0C00000F0h
0x14004f1eb  mov     ebp, 893h
0x14004f1f0  jmp     loc_14004F819
0x14004f1f5  mov     rcx, [rbx+10h]
0x14004f1f9  mov     rdx, r14
0x14004f1fc  call    CscNotifyCleanup
0x14004f201  mov     rcx, r15
0x14004f204  call    CscPopulateRxCreateInfoFromContexts
0x14004f209  mov     qword ptr [r15+230h], 0
0x14004f214  mov     eax, [r12+18h]
0x14004f219  test    al, 2
0x14004f21b  jnz     loc_14004F3FD
0x14004f221  mov     [rsp+0B8h+arg_18], 0
0x14004f22c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f233  lea     rax, WPP_GLOBAL_Control
0x14004f23a  cmp     rcx, rax
0x14004f23d  jz      short loc_14004F25B
0x14004f23f  mov     eax, [rcx+2Ch]
0x14004f242  test    al, 20h
0x14004f244  jz      short loc_14004F25B
0x14004f246  mov     rcx, [rcx+18h]
0x14004f24a  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004f251  mov     edx, 25h ; '%'
0x14004f256  call    WPP_SF_
0x14004f25b  mov     rcx, [r14+20h]
0x14004f25f  mov     [rsp+0B8h+arg_0], 1
0x14004f267  call    cs:__imp_RxDeregisterSrvOpenWithBufferingManager
0x14004f26e  nop     dword ptr [rax+rax+00h]
0x14004f273  mov     rax, [rbx+10h]
0x14004f277  mov     rcx, r14; Instance
0x14004f27a  bts     dword ptr [rax+9Ch], 17h
0x14004f282  call    cs:__imp_RxReference
0x14004f289  nop     dword ptr [rax+rax+00h]
0x14004f28e  mov     r9, r14; Instance
0x14004f291  lea     rdx, aCscbackpatchfo; "CscBackPatchFobxCallback"
0x14004f298  mov     r8d, 8D4h; Line
0x14004f29e  mov     dword ptr [rsp+0B8h+var_98], eax
0x14004f2a2  mov     ecx, 8; TraceType
0x14004f2a7  call    cs:__imp_RxpTrackReference
0x14004f2ae  nop     dword ptr [rax+rax+00h]
0x14004f2b3  mov     rcx, [r14+20h]
0x14004f2b7  call    cs:__imp_RxNotifyBufferingManagerOfPendingOpen
0x14004f2be  nop     dword ptr [rax+rax+00h]
0x14004f2c3  bts     dword ptr [r15+78h], 1Dh
0x14004f2c9  or      dword ptr [r13+4], 10h
0x14004f2ce  mov     rax, [r14+20h]
0x14004f2d2  btr     dword ptr [rax+48h], 9
0x14004f2d7  mov     rax, [rbx+10h]
0x14004f2db  mov     rcx, [rax+78h]
0x14004f2df  mov     rax, [rcx+20h]
0x14004f2e3  mov     rcx, [rax+30h]
0x14004f2e7  mov     rax, [rcx+160h]
0x14004f2ee  cmp     qword ptr [rax+38h], 0
0x14004f2f3  jz      loc_14004F3AB
0x14004f2f9  mov     eax, [r15+80h]
0x14004f300  test    al, 2
0x14004f302  jnz     loc_14004F3A4
0x14004f308  xor     eax, eax
0x14004f30a  xorps   xmm0, xmm0
0x14004f30d  movups  xmmword ptr [r15+0D0h], xmm0
0x14004f315  movups  xmmword ptr [r15+0E0h], xmm0
0x14004f31d  mov     [r15+0F0h], rax
0x14004f324  mov     rax, [rbx+10h]
0x14004f328  mov     rcx, [rax+78h]
0x14004f32c  mov     rax, [rcx+20h]
0x14004f330  mov     rcx, [rax+30h]
0x14004f334  mov     rax, [rcx+160h]
0x14004f33b  mov     rcx, r15
0x14004f33e  mov     rax, [rax+38h]
0x14004f342  call    _guard_dispatch_icall
0x14004f347  mov     ebp, eax
0x14004f349  cmp     eax, 0C0410001h
0x14004f34e  jnz     short loc_14004F3B0
0x14004f350  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f357  lea     rax, WPP_GLOBAL_Control
0x14004f35e  cmp     rcx, rax
0x14004f361  jz      short loc_14004F387
0x14004f363  mov     eax, [rcx+2Ch]
0x14004f366  test    al, 20h
0x14004f368  jz      short loc_14004F387
0x14004f36a  mov     r9d, [rsp+0B8h+arg_18]
0x14004f372  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004f379  mov     rcx, [rcx+18h]
0x14004f37d  mov     edx, 26h ; '&'
0x14004f382  call    WPP_SF_d
0x14004f387  mov     eax, [rsp+0B8h+arg_18]
0x14004f38e  inc     eax
0x14004f390  mov     [rsp+0B8h+arg_18], eax
0x14004f397  cmp     eax, 3E8h
0x14004f39c  jb      loc_14004F2D7
0x14004f3a2  jmp     short loc_14004F3B0
0x14004f3a4  mov     ebp, 0C0000120h
0x14004f3a9  jmp     short loc_14004F3B0
0x14004f3ab  mov     ebp, 0C0000002h
0x14004f3b0  and     dword ptr [r13+4], 0FFFFFFEFh
0x14004f3b5  mov     eax, 0C00000E5h
0x14004f3ba  mov     rcx, [r14+20h]
0x14004f3be  cmp     ebp, 0C0410001h
0x14004f3c4  cmovz   ebp, eax
0x14004f3c7  call    cs:__imp_RxNotifyBufferingManagerOfCompletedOpen
0x14004f3ce  nop     dword ptr [rax+rax+00h]
0x14004f3d3  test    ebp, ebp
0x14004f3d5  js      short loc_14004F3EC
0x14004f3d7  test    dword ptr [r12+18h], 10000h
0x14004f3e0  jnz     short loc_14004F3EC
0x14004f3e2  mov     eax, [r15+2E0h]
0x14004f3e9  mov     [rbx+60h], eax
0x14004f3ec  mov     rax, [rbx+10h]
0x14004f3f0  btr     dword ptr [rax+9Ch], 17h
0x14004f3f8  jmp     loc_14004F4AC
0x14004f3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f404  lea     rax, WPP_GLOBAL_Control
0x14004f40b  mov     [rsp+0B8h+arg_0], 0
0x14004f413  cmp     rcx, rax
0x14004f416  jz      short loc_14004F434
0x14004f418  mov     eax, [rcx+2Ch]
0x14004f41b  test    al, 20h
0x14004f41d  jz      short loc_14004F434
0x14004f41f  mov     rcx, [rcx+18h]
0x14004f423  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004f42a  mov     edx, 27h ; '''
0x14004f42f  call    WPP_SF_
0x14004f434  mov     rax, [rbx+10h]
0x14004f438  mov     rcx, [rax+78h]
0x14004f43c  mov     rax, [rcx+20h]
0x14004f440  mov     rcx, [rax+30h]
0x14004f444  mov     rax, [rcx+160h]
0x14004f44b  cmp     qword ptr [rax+50h], 0
0x14004f450  jnz     short loc_14004F459
0x14004f452  mov     ebp, 0C0000002h
0x14004f457  jmp     short loc_14004F4AC
0x14004f459  mov     eax, [r15+80h]
0x14004f460  test    al, 2
0x14004f462  jz      short loc_14004F46B
0x14004f464  mov     ebp, 0C0000120h
0x14004f469  jmp     short loc_14004F4AC
0x14004f46b  xor     eax, eax
0x14004f46d  xorps   xmm0, xmm0
0x14004f470  movups  xmmword ptr [r15+0D0h], xmm0
0x14004f478  movups  xmmword ptr [r15+0E0h], xmm0
0x14004f480  mov     [r15+0F0h], rax
0x14004f487  mov     rax, [rbx+10h]
0x14004f48b  mov     rcx, [rax+78h]
0x14004f48f  mov     rax, [rcx+20h]
0x14004f493  mov     rcx, [rax+30h]
0x14004f497  mov     rax, [rcx+160h]
0x14004f49e  mov     rcx, r15
0x14004f4a1  mov     rax, [rax+50h]
0x14004f4a5  call    _guard_dispatch_icall
0x14004f4aa  mov     ebp, eax
0x14004f4ac  mov     r8, qword ptr [rsp+0B8h+var_68+8]
0x14004f4b1  or      dword ptr [r8+4], 10h
0x14004f4b6  mov     rcx, [rbx+10h]
0x14004f4ba  mov     rdx, [rcx+78h]
0x14004f4be  mov     rcx, [rdx+20h]
0x14004f4c2  mov     rdx, [rcx+30h]
0x14004f4c6  mov     rcx, [rdx+160h]
0x14004f4cd  mov     rdx, [rcx+80h]
0x14004f4d4  mov     [r8+58h], rdx
0x14004f4d8  or      dword ptr [r12+18h], 4
0x14004f4de  mov     rcx, [rbx+10h]
0x14004f4e2  mov     rax, [rcx+78h]
0x14004f4e6  mov     rcx, [rax+20h]
0x14004f4ea  mov     rax, [rcx+30h]
0x14004f4ee  mov     rcx, [rax+160h]
0x14004f4f5  mov     rax, [rcx+88h]
0x14004f4fc  mov     [r12+28h], rax
0x14004f501  or      dword ptr [r13+4], 2
0x14004f506  mov     rax, [rbx+10h]
0x14004f50a  mov     rcx, [rax+78h]
0x14004f50e  mov     rax, [rcx+20h]
0x14004f512  mov     rcx, [rax+30h]
0x14004f516  mov     rax, [rcx+160h]
0x14004f51d  mov     rcx, [rax+90h]
0x14004f524  mov     [r13+40h], rcx
0x14004f528  test    ebp, ebp
0x14004f52a  jns     short loc_14004F56C
0x14004f52c  mov     r8, [rbx+10h]
0x14004f530  mov     ecx, ebp
0x14004f532  mov     rdx, [rbx]
0x14004f535  call    CscCheckRdrStatusTransitionIfNetErr
0x14004f53a  test    al, al
0x14004f53c  jnz     short loc_14004F552
0x14004f53e  mov     rcx, [rbx+10h]
0x14004f542  xor     r9d, r9d
0x14004f545  xor     edx, edx
0x14004f547  mov     r8d, 400h
0x14004f54d  call    CscTransitionFcbOffline
0x14004f552  cmp     [rsp+0B8h+arg_0], 0
0x14004f55a  mov     esi, ebp
0x14004f55c  mov     ebp, 94Eh
0x14004f561  jz      loc_14004F819
0x14004f567  jmp     loc_14004F7E0
0x14004f56c  or      dword ptr [r12+18h], 2
0x14004f572  mov     rax, [r14+20h]
0x14004f576  cmp     dword ptr [rax+58h], 0
0x14004f57a  jnz     short loc_14004F5D5
0x14004f57c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f583  lea     rax, WPP_GLOBAL_Control
0x14004f58a  cmp     rcx, rax
0x14004f58d  jz      short loc_14004F5AB
0x14004f58f  mov     eax, [rcx+2Ch]
0x14004f592  test    al, 40h
0x14004f594  jz      short loc_14004F5AB
0x14004f596  mov     rcx, [rcx+18h]
0x14004f59a  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004f5a1  mov     edx, 28h ; '('
0x14004f5a6  call    WPP_SF_
0x14004f5ab  mov     rax, [rbx+10h]
0x14004f5af  mov     rcx, [rax+78h]
0x14004f5b3  mov     rax, [rcx+20h]
0x14004f5b7  mov     rcx, [rax+30h]
0x14004f5bb  mov     rax, [rcx+160h]
0x14004f5c2  mov     rax, [rax+68h]
0x14004f5c6  test    rax, rax
  ... truncated ...
```
