# CscCloseSrvOpen

- ea: `0x140074330`
- end: `0x140074c6b`
- name: `CscCloseSrvOpen`
- size: `2363`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x14004f0a0`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x1400084f0`
- `0x14000a634`
- `0x14000e100`
- `0x1400109e0`
- `0x140010ae8`
- `0x140011634`
- `0x140018930`
- `0x140019034`
- `0x1400190ec`
- `0x14001ac1c`
- `0x14001bbc0`
- `0x14001c960`
- `0x14001c9e8`
- `0x14001d110`
- `0x1400235d4`
- `0x14002f010`
- `0x14002f0f0`
- `0x140046008`
- `0x140074330`
- `0x140074c74`
- `0x140074ff4`
- `0x1400750a4`
- `0x140088580`

## import_xrefs

- `rdbss!RxDoesOplockStateChangeOnSrvOpenClose` at `0x14007497c`
- `rdbss!RxDoesOplockStateChangeOnSrvOpenClose` at `0x14007497c`

## pseudocode

```c
__int64 __fastcall CscCloseSrvOpen(__int64 a1)
{
  _WORD *v1; // r10
  bool v2; // si
  __int64 v3; // r12
  int v5; // r15d
  int v6; // r9d
  int v7; // ecx
  int v8; // r10d
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rdi
  int v12; // r15d
  __int64 v13; // r13
  bool v14; // r11
  char v15; // bl
  char v16; // cl
  char v17; // bl
  __int64 v18; // rdx
  unsigned int v19; // esi
  char v20; // si
  int v21; // eax
  int v22; // r8d
  int v24; // eax
  _WORD *v25; // r12
  _WORD *v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // rdx
  int v29; // eax
  bool v30; // zf
  __int64 v31; // r8
  int v32; // eax
  char v33; // r10
  __int64 v34; // r8
  char v35; // cl
  char v36; // al
  char v37; // al
  int v38; // eax
  int v39; // [rsp+28h] [rbp-79h]
  int v40; // [rsp+30h] [rbp-71h]
  unsigned __int8 v41; // [rsp+68h] [rbp-39h]
  char v42; // [rsp+68h] [rbp-39h]
  bool v43; // [rsp+69h] [rbp-38h]
  unsigned __int8 v44; // [rsp+6Ah] [rbp-37h]
  _WORD *v45; // [rsp+70h] [rbp-31h] BYREF
  int v46; // [rsp+78h] [rbp-29h] BYREF
  unsigned int v47; // [rsp+80h] [rbp-21h] BYREF
  __int64 v48; // [rsp+88h] [rbp-19h] BYREF
  __int128 v49; // [rsp+90h] [rbp-11h] BYREF
  __int128 v50; // [rsp+A0h] [rbp-1h]
  __int64 v51; // [rsp+B0h] [rbp+Fh]
  __int128 v52; // [rsp+B8h] [rbp+17h] BYREF

  v1 = *(_WORD **)(a1 + 56);
  v2 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v3 = *(_QWORD *)(a1 + 72);
  LOWORD(v46) = *v1;
  v5 = *(_DWORD *)(a1 + 120);
  v51 = 0;
  v45 = v1;
  v47 = 0;
  v49 = 0;
  v50 = 0;
  v52 = 0;
  CscGetContexts((_QWORD *)a1, &v49);
  LOBYTE(v6) = 1;
  CscUpdateAndCaptureConnectionStateEx(v8, v3, v7, v6, (__int64)&v52, 1);
  v11 = v50;
  v12 = v5 & 0x100;
  if ( v12 && !(_QWORD)v50 )
  {
    v19 = 0;
    v22 = 11493;
    goto LABEL_40;
  }
  v13 = *((_QWORD *)&v49 + 1);
  LOBYTE(v9) = *((_QWORD *)&v49 + 1) && (*(_DWORD *)(*((_QWORD *)&v49 + 1) + 4LL) & 0x8000) != 0;
  v41 = v9;
  v14 = *((_QWORD *)&v49 + 1) && (*(_DWORD *)(*((_QWORD *)&v49 + 1) + 4LL) & 0x100000) != 0;
  v43 = v14;
  LOBYTE(v10) = (_QWORD)v50
             && (_m_prefetchw((const void *)(v50 + 28)),
                 (_InterlockedXor((volatile signed __int32 *)(v50 + 28), 0) & 0x8000) != 0);
  v44 = v10;
  v15 = 89;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      v33 = 89;
      if ( !(_BYTE)v10 )
        v33 = 78;
      if ( v11 )
      {
        v34 = 89;
        if ( (*(_DWORD *)(v11 + 24) & 2) == 0 )
          v34 = 78;
      }
      else
      {
        v34 = 63;
      }
      v35 = 89;
      v36 = 89;
      if ( !v14 )
        v35 = 78;
      if ( !v12 )
        v36 = 78;
      WPP_SF_dqqqcccc(
        WPP_GLOBAL_Control->AttachedDevice,
        WPP_GLOBAL_Control,
        v34,
        v2,
        v45,
        *((_QWORD *)v45 + 16),
        v3,
        (_BYTE)v34,
        v36,
        v35,
        v33);
      v9 = v41;
      v10 = v44;
      v14 = v43;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      WPP_SF_ddddd(
        WPP_GLOBAL_Control->AttachedDevice,
        v45,
        v9,
        *(unsigned int *)(v3 + 92),
        *((_DWORD *)v45 + 48),
        *((_DWORD *)v45 + 49),
        *((_DWORD *)v45 + 46),
        *(_DWORD *)(v13 + 8));
      v9 = v41;
      v10 = v44;
      v14 = v43;
    }
  }
  if ( v12 )
  {
    if ( !(_BYTE)v9 )
    {
      v9 = BYTE1(v52);
      if ( ((v52 & 0x20) == 0 || (BYTE1(v52) & 2) != 0) && !v14 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          v37 = 89;
          if ( (BYTE1(v52) & 2) == 0 )
            v37 = 78;
          LOBYTE(v40) = v37;
          if ( (v52 & 0x20) == 0 )
            v15 = 78;
          LOBYTE(v39) = v15;
          WPP_SF_qcc(
            WPP_GLOBAL_Control->AttachedDevice,
            217,
            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
            v45,
            v39,
            v40);
        }
        _InterlockedOr8((volatile signed __int8 *)v45 + 256, 2u);
        v19 = -1073741247;
        v22 = 11544;
        goto LABEL_40;
      }
    }
  }
  if ( (_QWORD)v49 )
  {
    v29 = *(_DWORD *)(v49 + 4);
    if ( (v29 & 0x10) != 0 )
    {
      v22 = 11563;
      *(_DWORD *)(v49 + 4) = v29 | 0x20;
      v19 = 0;
      goto LABEL_40;
    }
  }
  v16 = 0;
  v42 = 0;
  v17 = 0;
  v18 = 60449;
  if ( (v52 & 0x30) == 0x20 )
  {
    if ( v12 )
    {
      if ( !v14 )
        goto LABEL_12;
    }
    else if ( !v14 )
    {
LABEL_88:
      if ( (*(_DWORD *)(v3 + 72) & 0x810) == 0 && (_WORD)v46 != 0xEC21 && (!v11 || (*(_DWORD *)(v11 + 24) & 0x400) == 0) )
        goto LABEL_12;
LABEL_89:
      v16 = 1;
      v42 = 1;
      goto LABEL_12;
    }
    if ( (_BYTE)v10 )
      goto LABEL_89;
    goto LABEL_88;
  }
LABEL_12:
  if ( v2 && (!v11 || (*(_DWORD *)(v11 + 24) & 2) != 0) )
  {
    *(_BYTE *)(a1 + 504) = v16 & 0xFD | *(_BYTE *)(a1 + 504) & 0xFC;
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 112LL) )
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
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 112LL))(
                a1,
                60449);
      }
    }
    else
    {
      v19 = -1073741822;
    }
    if ( !v13 )
    {
      v22 = 11615;
      goto LABEL_40;
    }
    v17 = 1;
    if ( v11 )
      *(_DWORD *)(v11 + 24) &= ~2u;
    if ( (v52 & 0x20) != 0 && !v12 )
      CscCheckRdrStatusTransitionIfNetErr(v19, &v52, v45);
    if ( (*(_DWORD *)(v3 + 72) & 0x400) != 0 )
      CscDecrementRdrOpenCountForOrphanedSrvOpen(v3, v13);
  }
  if ( v11 )
  {
    if ( *(_DWORD *)(v3 + 92) )
      goto LABEL_138;
    if ( (*(_DWORD *)(v11 + 24) & 8) != 0 )
    {
      *(_DWORD *)(v13 + 4) &= ~0x20u;
      v38 = *(_DWORD *)(v13 + 4);
      if ( (v38 & 0x1000000) == 0 )
      {
        *(_DWORD *)(v13 + 4) = v38 | 0x200;
        *(_DWORD *)(v13 + 40) = 0;
        *(_DWORD *)(v3 + 72) |= 0x1080u;
      }
    }
    if ( (*(_DWORD *)(v11 + 24) & 1) != 0 )
      --*(_DWORD *)(v13 + 20);
  }
  if ( !*(_DWORD *)(v3 + 92) )
  {
LABEL_24:
    v20 = 1;
    goto LABEL_25;
  }
LABEL_138:
  if ( (*(_DWORD *)(v3 + 72) & 0x400) != 0 )
    goto LABEL_24;
  v20 = 0;
LABEL_25:
  if ( v12 && !v43 )
    goto LABEL_28;
  if ( v42 && (v52 & 0x10) == 0 && (v20 || v44 && v43) )
  {
    CscUpdateFileInfoOnClose(a1, &v49);
    v11 = v50;
    v13 = *((_QWORD *)&v49 + 1);
  }
  if ( v12 )
  {
LABEL_28:
    v21 = *(_DWORD *)(v13 + 4);
    if ( (v21 & 0x200) == 0 )
    {
      *(_DWORD *)(v13 + 4) = v21 | 0x200;
      v19 = 0;
LABEL_39:
      v22 = 0;
      goto LABEL_40;
    }
  }
  else
  {
    if ( v11 )
    {
      v24 = *(_DWORD *)(v11 + 24);
      if ( (v24 & 0x1000) != 0 )
      {
        *(_DWORD *)(v11 + 24) = v24 & 0xFFFFEFFF;
        v10 = (unsigned int)--*(_DWORD *)(v13 + 28);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 218, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v10);
        }
      }
    }
    if ( (v52 & 0x20) != 0 && v20 )
    {
      if ( v17 )
      {
        if ( (_WORD)v46 != 0xEC21 )
        {
          v46 = 0;
          if ( (unsigned __int8)RxDoesOplockStateChangeOnSrvOpenClose(v3, &v46) )
          {
            if ( (v46 & 1) == 0 && (unsigned __int8)CscCheckForNoOplockDataSrvOpen(v3) )
            {
              v48 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  219,
                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                  v45,
                  v46);
              }
              v48 = 0x2000000000LL;
              v32 = CscStoreSetInformationEntry(*(_QWORD *)(v13 + 56), (__int64)&v48, 0, 0, 0, 0, 0);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  220,
                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                  v45,
                  v32);
              }
            }
          }
        }
      }
      v27 = v3;
      v25 = v45;
      CscSrvOpenCloseStoreState(v45, v27, (v52 & 0x10) != 0, &v47);
      v28 = (unsigned __int8)v52;
      if ( (v52 & 0x80u) != 0LL && (*(_DWORD *)(v13 + 4) & 0x4000) == 0 )
      {
        LOBYTE(v28) = (v52 & 0x10) != 0;
        CscHandleDeleteOnClose(a1, v28);
      }
      v18 = v47;
      if ( v47 )
        CscNotifyReportChange(a1, v47, 3);
    }
    else
    {
      v25 = v45;
    }
    if ( (v52 & 0x80u) != 0LL && v13 )
    {
      CscCleanupFcbContextFlags(v25, v18, v9, v10);
      v26 = *(_WORD **)(v13 + 56);
      if ( v26 )
      {
        v30 = (*(_DWORD *)(v13 + 4) & 0x20000) == 0;
        v45 = *(_WORD **)(v13 + 56);
        if ( !v30 )
          CscStoreReferenceEntry(v26);
        CscClearFcbStoreEntry(v25);
        if ( (*(_DWORD *)(v13 + 4) & 0x20000) != 0 )
        {
          CscStoreRecreateAsGhost(&v45, 0);
          v26 = v45;
          if ( v45 )
          {
            CscStoreDereferenceEntry(&v45);
            v26 = v45;
          }
          *(_DWORD *)(v13 + 4) &= ~0x20000u;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_qqqd(WPP_GLOBAL_Control->AttachedDevice, 221, v31, v26, v25);
        }
        *(_DWORD *)(v13 + 4) &= ~0x20u;
      }
      goto LABEL_61;
    }
  }
  v19 = 0;
  if ( v12 )
    goto LABEL_39;
LABEL_61:
  v19 = 0;
  v22 = 0;
  if ( (_QWORD)v49 )
    *(_DWORD *)(v11 + 24) |= 0x200u;
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 222, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v19, v22);
  return v19;
}

```

## disassembly

```asm
0x140074330  mov     r11, rsp
0x140074333  push    rbp
0x140074334  push    rsi
0x140074335  lea     rbp, [r11-5Fh]
0x140074339  sub     rsp, 0E8h
0x140074340  mov     rax, cs:__security_cookie
0x140074347  xor     rax, rsp
0x14007434a  mov     [rbp+57h+var_30], rax
0x14007434e  mov     rax, cs:CscDeviceObject
0x140074355  lea     rdx, [rbp+57h+var_68]
0x140074359  cmp     [rcx+50h], rax
0x14007435d  xorps   xmm0, xmm0
0x140074360  mov     r10, [rcx+38h]
0x140074364  mov     [r11+18h], rdi
0x140074368  setnz   sil
0x14007436c  mov     [r11+20h], r12
0x140074370  mov     r12, [rcx+48h]
0x140074374  movzx   eax, word ptr [r10]
0x140074378  mov     word ptr [rbp+57h+var_80], ax
0x14007437c  xor     eax, eax
0x14007437e  mov     [r11-20h], r14
0x140074382  mov     r14, rcx
0x140074385  mov     [r11-28h], r15
0x140074389  mov     r15d, [rcx+78h]
0x14007438d  mov     [rbp+57h+var_48], rax
0x140074391  mov     [rbp+57h+var_88], r10
0x140074395  mov     [rbp+57h+var_78], 0
0x14007439c  movups  [rbp+57h+var_68], xmm0
0x1400743a0  movups  [rbp+57h+var_58], xmm0
0x1400743a4  movups  [rbp+57h+var_40], xmm0
0x1400743a8  call    CscGetContexts
0x1400743ad  lea     rax, [rbp+57h+var_40]
0x1400743b1  mov     byte ptr [rsp+0F0h+var_C8], 1
0x1400743b6  mov     r8, rcx
0x1400743b9  mov     [rsp+0F0h+var_D0], rax
0x1400743be  mov     rcx, r10
0x1400743c1  mov     r9b, 1
0x1400743c4  mov     rdx, r12
0x1400743c7  call    CscUpdateAndCaptureConnectionStateEx
0x1400743cc  mov     rdi, qword ptr [rbp+57h+var_58]
0x1400743d0  lea     r10, WPP_GLOBAL_Control
0x1400743d7  and     r15d, 100h
0x1400743de  jnz     loc_1400745A6
0x1400743e4  mov     [rsp+0F0h+arg_8], rbx
0x1400743ec  mov     [rsp+0E0h], r13
0x1400743f4  mov     r13, qword ptr [rbp+57h+var_68+8]
0x1400743f8  test    r13, r13
0x1400743fb  jnz     loc_140074627
0x140074401  xor     r8b, r8b
0x140074404  mov     [rbp+57h+var_90], r8b
0x140074408  test    r13, r13
0x14007440b  jnz     loc_14007463D
0x140074411  xor     r11b, r11b
0x140074414  mov     [rbp+57h+var_8F], r11b
0x140074418  test    rdi, rdi
0x14007441b  jnz     loc_140074653
0x140074421  xor     r9b, r9b
0x140074424  mov     [rbp+57h+var_8E], r9b
0x140074428  mov     rdx, cs:WPP_GLOBAL_Control
0x14007442f  mov     ebx, 59h ; 'Y'
0x140074434  mov     ecx, 4Eh ; 'N'
0x140074439  cmp     rdx, r10
0x14007443c  jnz     loc_140074678
0x140074442  test    r15d, r15d
0x140074445  jnz     loc_140074AF8
0x14007444b  mov     rcx, qword ptr [rbp+57h+var_68]
0x14007444f  test    rcx, rcx
0x140074452  jnz     loc_1400747F8
0x140074458  movzx   eax, byte ptr [rbp+57h+var_40]
0x14007445c  xor     cl, cl
0x14007445e  and     al, 30h
0x140074460  mov     [rbp+57h+var_90], cl
0x140074463  xor     bl, bl
0x140074465  mov     edx, 0EC21h
0x14007446a  cmp     al, 20h ; ' '
0x14007446c  jz      loc_140074868
0x140074472  test    sil, sil
0x140074475  jz      short loc_1400744DD
0x140074477  test    rdi, rdi
0x14007447a  jnz     loc_14007477D
0x140074480  movzx   eax, byte ptr [r14+1F8h]
0x140074488  and     al, 0FEh
0x14007448a  or      al, cl
0x14007448c  and     al, 0FDh
0x14007448e  mov     [r14+1F8h], al
0x140074495  mov     rax, [r14+50h]
0x140074499  mov     rcx, [rax+160h]
0x1400744a0  cmp     qword ptr [rcx+70h], 0
0x1400744a5  jnz     loc_140074532
0x1400744ab  mov     esi, 0C0000002h
0x1400744b0  test    r13, r13
0x1400744b3  jz      loc_14007492F
0x1400744b9  mov     bl, 1
0x1400744bb  test    rdi, rdi
0x1400744be  jz      short loc_1400744C4
0x1400744c0  and     dword ptr [rdi+18h], 0FFFFFFFDh
0x1400744c4  test    byte ptr [rbp+57h+var_40], 20h
0x1400744c8  jnz     loc_14007487D
0x1400744ce  test    dword ptr [r12+48h], 400h
0x1400744d7  jnz     loc_140074B95
0x1400744dd  test    rdi, rdi
0x1400744e0  jnz     loc_14007457B
0x1400744e6  cmp     dword ptr [r12+5Ch], 0
0x1400744ec  jnz     loc_140074BD6
0x1400744f2  mov     sil, 1
0x1400744f5  movzx   eax, [rbp+57h+var_8F]
0x1400744f9  test    r15d, r15d
0x1400744fc  jnz     loc_140074BED
0x140074502  cmp     [rbp+57h+var_90], 0
0x140074506  jnz     loc_1400748B8
0x14007450c  test    r15d, r15d
0x14007450f  jz      loc_14007471E
0x140074515  mov     eax, [r13+4]
0x140074519  bt      eax, 9
0x14007451d  jb      loc_1400745B9
0x140074523  bts     eax, 9
0x140074527  mov     [r13+4], eax
0x14007452b  xor     esi, esi
0x14007452d  jmp     loc_1400745C4
0x140074532  mov     eax, [r14+80h]
0x140074539  test    al, 2
0x14007453b  jnz     loc_140074B8B
0x140074541  xor     eax, eax
0x140074543  xorps   xmm0, xmm0
0x140074546  movups  xmmword ptr [r14+0D0h], xmm0
0x14007454e  movups  xmmword ptr [r14+0E0h], xmm0
0x140074556  mov     [r14+0F0h], rax
0x14007455d  mov     rax, [r14+50h]
0x140074561  mov     rcx, [rax+160h]
0x140074568  mov     rax, [rcx+70h]
0x14007456c  mov     rcx, r14
0x14007456f  call    _guard_dispatch_icall
0x140074574  mov     esi, eax
0x140074576  jmp     loc_1400744B0
0x14007457b  cmp     dword ptr [r12+5Ch], 0
0x140074581  jnz     loc_140074BD6
0x140074587  mov     eax, [rdi+18h]
0x14007458a  test    al, 8
0x14007458c  jnz     loc_140074BA5
0x140074592  mov     eax, [rdi+18h]
0x140074595  test    al, 1
0x140074597  jz      loc_1400744E6
0x14007459d  dec     dword ptr [r13+14h]
0x1400745a1  jmp     loc_1400744E6
0x1400745a6  test    rdi, rdi
0x1400745a9  jnz     loc_1400743E4
0x1400745af  xor     esi, esi
0x1400745b1  mov     r8d, 2CE5h
0x1400745b7  jmp     short loc_1400745D7
0x1400745b9  xor     esi, esi
0x1400745bb  test    r15d, r15d
0x1400745be  jz      loc_140074762
0x1400745c4  mov     r8d, esi
0x1400745c7  mov     rbx, [rsp+0F0h+arg_8]
0x1400745cf  mov     r13, [rsp+0E0h]
0x1400745d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400745de  lea     rax, WPP_GLOBAL_Control
0x1400745e5  mov     r15, [rsp+0F0h+var_20]
0x1400745ed  mov     r14, [rsp+0F0h+var_18]
0x1400745f5  mov     r12, [rsp+0F0h+arg_18]
0x1400745fd  mov     rdi, [rsp+0F0h+arg_10]
0x140074605  cmp     rcx, rax
0x140074608  jnz     loc_1400746F1
0x14007460e  mov     eax, esi
0x140074610  mov     rcx, [rbp+57h+var_30]
0x140074614  xor     rcx, rsp; StackCookie
0x140074617  call    __security_check_cookie
0x14007461c  add     rsp, 0E8h
0x140074623  pop     rsi
0x140074624  pop     rbp
0x140074625  retn
0x140074627  test    dword ptr [r13+4], 8000h
0x14007462f  jz      loc_140074401
0x140074635  mov     r8b, 1
0x140074638  jmp     loc_140074404
0x14007463d  test    dword ptr [r13+4], 100000h
0x140074645  jz      loc_140074411
0x14007464b  mov     r11b, 1
0x14007464e  jmp     loc_140074414
0x140074653  prefetchw byte ptr [rdi+1Ch]
0x140074657  mov     eax, [rdi+1Ch]
0x14007465a  mov     ecx, eax
0x14007465c  xor     ecx, 0
0x14007465f  lock cmpxchg [rdi+1Ch], ecx
0x140074664  jnz     short loc_14007465A
0x140074666  bt      eax, 0Fh
0x14007466a  jnb     loc_140074421
0x140074670  mov     r9b, 1
0x140074673  jmp     loc_140074424
0x140074678  mov     eax, [rdx+2Ch]
0x14007467b  test    al, 20h
0x14007467d  jnz     loc_140074A69
0x140074683  mov     rcx, cs:WPP_GLOBAL_Control
0x14007468a  cmp     rcx, r10
0x14007468d  jz      loc_140074442
0x140074693  mov     eax, [rcx+2Ch]
0x140074696  test    al, 20h
0x140074698  jz      loc_140074442
0x14007469e  mov     rdx, [rbp+57h+var_88]
0x1400746a2  mov     eax, [r13+8]
0x1400746a6  mov     r9d, [r12+5Ch]
0x1400746ab  mov     rcx, [rcx+18h]
0x1400746af  mov     dword ptr [rsp+0F0h+var_B8], eax
0x1400746b3  mov     eax, [rdx+0B8h]
0x1400746b9  mov     [rsp+0F0h+var_C0], eax
0x1400746bd  mov     eax, [rdx+0C4h]
0x1400746c3  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400746c7  mov     eax, [rdx+0C0h]
0x1400746cd  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400746d1  call    WPP_SF_ddddd
0x1400746d6  movzx   r8d, [rbp+57h+var_90]
0x1400746db  lea     r10, WPP_GLOBAL_Control
0x1400746e2  movzx   r9d, [rbp+57h+var_8E]
0x1400746e7  movzx   r11d, [rbp+57h+var_8F]
0x1400746ec  jmp     loc_140074442
0x1400746f1  mov     eax, [rcx+2Ch]
0x1400746f4  test    al, 20h
0x1400746f6  jz      loc_14007460E
0x1400746fc  mov     rcx, [rcx+18h]
0x140074700  mov     edx, 0DEh
0x140074705  mov     dword ptr [rsp+0F0h+var_D0], r8d
0x14007470a  mov     r9d, esi
0x14007470d  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140074714  call    WPP_SF_Dd
0x140074719  jmp     loc_14007460E
0x14007471e  test    rdi, rdi
0x140074721  jz      short loc_140074730
0x140074723  mov     eax, [rdi+18h]
0x140074726  bt      eax, 0Ch
0x14007472a  jb      loc_1400748E4
0x140074730  test    byte ptr [rbp+57h+var_40], 20h
0x140074734  jnz     short loc_14007478D
0x140074736  mov     r12, [rbp+57h+var_88]
0x14007473a  test    byte ptr [rbp+57h+var_40], 80h
0x14007473e  jz      loc_1400745B9
0x140074744  test    r13, r13
0x140074747  jz      loc_1400745B9
0x14007474d  mov     rcx, r12
0x140074750  call    CscCleanupFcbContextFlags
0x140074755  mov     rbx, [r13+38h]
0x140074759  test    rbx, rbx
0x14007475c  jnz     loc_140074816
0x140074762  xor     esi, esi
0x140074764  mov     r8d, esi
0x140074767  cmp     qword ptr [rbp+57h+var_68], rsi
0x14007476b  jz      loc_1400745C7
0x140074771  or      dword ptr [rdi+18h], 200h
0x140074778  jmp     loc_1400745C7
0x14007477d  mov     eax, [rdi+18h]
0x140074780  test    al, 2
0x140074782  jnz     loc_140074480
0x140074788  jmp     loc_1400744DD
0x14007478d  test    sil, sil
0x140074790  jz      short loc_140074736
0x140074792  test    bl, bl
0x140074794  jnz     loc_14007495F
0x14007479a  movzx   r8d, byte ptr [rbp+57h+var_40]
0x14007479f  lea     r9, [rbp+57h+var_78]
0x1400747a3  mov     rdx, r12
0x1400747a6  shr     r8b, 4
0x1400747aa  mov     r12, [rbp+57h+var_88]
0x1400747ae  and     r8b, 1
0x1400747b2  mov     rcx, r12
0x1400747b5  call    CscSrvOpenCloseStoreState
0x1400747ba  movzx   edx, byte ptr [rbp+57h+var_40]
0x1400747be  test    dl, dl
0x1400747c0  jns     short loc_1400747DA
0x1400747c2  test    dword ptr [r13+4], 4000h
0x1400747ca  jnz     short loc_1400747DA
0x1400747cc  shr     dl, 4
0x1400747cf  mov     rcx, r14
0x1400747d2  and     dl, 1
0x1400747d5  call    CscHandleDeleteOnClose
0x1400747da  mov     edx, [rbp+57h+var_78]
0x1400747dd  test    edx, edx
0x1400747df  jz      loc_14007473A
0x1400747e5  mov     r8d, 3
0x1400747eb  mov     rcx, r14
0x1400747ee  call    CscNotifyReportChange
0x1400747f3  jmp     loc_14007473A
0x1400747f8  mov     eax, [rcx+4]
0x1400747fb  test    al, 10h
0x1400747fd  jz      loc_140074458
0x140074803  or      eax, 20h
0x140074806  mov     r8d, 2D2Bh
0x14007480c  mov     [rcx+4], eax
0x14007480f  xor     esi, esi
0x140074811  jmp     loc_1400745C7
0x140074816  test    dword ptr [r13+4], 20000h
0x14007481e  mov     [rbp+57h+var_88], rbx
0x140074822  jnz     loc_140074C11
0x140074828  mov     rcx, r12
0x14007482b  call    CscClearFcbStoreEntry
0x140074830  test    dword ptr [r13+4], 20000h
0x140074838  mov     esi, eax
0x14007483a  jnz     loc_140074C1E
0x140074840  mov     rcx, cs:WPP_GLOBAL_Control
0x140074847  lea     rax, WPP_GLOBAL_Control
0x14007484e  cmp     rcx, rax
0x140074851  jz      short loc_14007485E
  ... truncated ...
```
