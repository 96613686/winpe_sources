# CscDclMRxSetItemInformation

- ea: `0x14004d450`
- end: `0x14004da45`
- name: `CscDclMRxSetItemInformation`
- size: `1525`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x14007ae70`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x14000dfc0`
- `0x14000e030`
- `0x14000e100`
- `0x14000f8b0`
- `0x1400169d4`
- `0x140016a04`
- `0x1400190ec`
- `0x140019204`
- `0x14001a494`
- `0x14001b374`
- `0x14001d200`
- `0x14002f010`
- `0x14002f440`
- `0x14004d450`
- `0x140075f70`
- `0x1400761e0`
- `0x140088580`

## import_xrefs

- `rdbss!RxReleaseFcbPagingInMRx` at `0x14004d9c3`
- `rdbss!RxReleaseFcbPagingInMRx` at `0x14004d9c3`
- `rdbss!RxPurgeFcbInSystemCache` at `0x14004d759`
- `rdbss!RxPurgeFcbInSystemCache` at `0x14004d759`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x14004d6f2`
- `rdbss!RxAcquireExclusiveFcbPagingInMRx` at `0x14004d6f2`

## pseudocode

```c
__int64 __fastcall CscDclMRxSetItemInformation(__int64 a1, _DWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v7; // rdi
  __int64 v8; // r12
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // r8
  char v16; // r15
  unsigned int v17; // ebx
  int InformationEntry; // edi
  int v19; // esi
  int v20; // r9d
  int v21; // edi
  int v22; // esi
  __int64 v23; // r8
  char v24; // r12
  __int64 v25; // rdx
  char v26; // si
  int v27; // eax
  __int64 v28; // r12
  int v29; // edx
  __int64 v30; // r14
  __int64 v31; // r14
  __int64 v32; // rbx
  int FlushFile; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-D8h]
  char v36; // [rsp+40h] [rbp-C0h]
  char v37; // [rsp+41h] [rbp-BFh]
  char v38; // [rsp+42h] [rbp-BEh]
  char v39[5]; // [rsp+43h] [rbp-BDh] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  __int128 v43; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v44; // [rsp+70h] [rbp-90h]
  __int128 v45; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v46[3]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h]
  _DWORD v48[20]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_QWORD *)(a1 + 56);
  v40 = a3;
  v7 = a3;
  v42 = a1;
  v8 = *(_QWORD *)(v4 + 32);
  v41 = a4;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  memset(v48, 0, sizeof(v48));
  memset(v46, 0, sizeof(v46));
  v47 = 0;
  v39[0] = 0;
  CscGetContexts(a1, &v43, v11, v12);
  LOBYTE(v13) = 1;
  CscUpdateAndCaptureConnectionStateEx(v5, v8, a1, v13, (__int64)&v45, 1);
  if ( (v45 & 0x20) == 0 )
  {
    if ( (BYTE1(v45) & 0x40) == 0 )
    {
      InformationEntry = -1073741275;
      goto LABEL_81;
    }
LABEL_79:
    InformationEntry = CscDetermineAbortStatus(&v45);
LABEL_81:
    v19 = 1265;
    goto LABEL_82;
  }
  if ( (BYTE1(v45) & 0x40) != 0 )
    goto LABEL_79;
  v38 = 0;
  v16 = 1;
  v37 = 0;
  v17 = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LOBYTE(v15) = a4 != 0 ? 89 : 78;
    LOBYTE(v14) = v7 != 0 ? 89 : 78;
    LOBYTE(v35) = v14;
    LOBYTE(FlushFile) = a2 != 0 ? 89 : 78;
    WPP_SF_qccc(WPP_GLOBAL_Control->AttachedDevice, v14, v15, v5, FlushFile, v35, (_BYTE)v15);
  }
  if ( !a2 )
    goto LABEL_49;
  InformationEntry = CscStoreQueryInformationEntryEx(
                       *(_QWORD *)(*((_QWORD *)&v43 + 1) + 56LL),
                       0,
                       (unsigned int)v48,
                       (unsigned int)v46,
                       (__int64)v39,
                       0,
                       0);
  if ( InformationEntry < 0 )
  {
    v19 = 1288;
    goto LABEL_82;
  }
  v20 = v48[0];
  v21 = *a2 & v48[0];
  v17 = a2[1] & ~v48[0] | 0x20;
  if ( (a2[1] & 0x20) == 0 )
    v17 = a2[1] & ~v48[0];
  v22 = v21 | v17;
  if ( !(v21 | v17) )
  {
    v7 = v40;
    v19 = 0;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      27,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      v17,
      v21,
      v48[0]);
    v20 = v48[0];
  }
  if ( (v22 & 0x14840) != 0 )
  {
    InformationEntry = -1073741811;
    v19 = 1330;
    goto LABEL_82;
  }
  if ( (v22 & 0x21) != 0 && (*(_BYTE *)(v5 + 232) & 0x10) != 0 )
  {
    InformationEntry = -1073741811;
    v19 = 1344;
    goto LABEL_82;
  }
  v23 = *(unsigned int *)(v8 + 152);
  if ( (v23 & 2) == 0 && (*(_DWORD *)(v44 + 24) & 0x800) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, 2, v23);
    InformationEntry = -1073741790;
    v19 = 1371;
    goto LABEL_82;
  }
  v24 = 0;
  v16 = 0;
  if ( (v22 & 0x20) != 0 )
  {
    LOBYTE(v23) = 1;
    RxAcquireExclusiveFcbPagingInMRx(0, v5, v23);
    v20 = v48[0];
    v38 = 1;
  }
  v25 = 525335;
  if ( (v17 & 0x20) != 0 )
  {
    if ( (v45 & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids, v5);
      RxPurgeFcbInSystemCache((PFCB)v5, 0, 0, 0, 0);
      v20 = v48[0];
      v25 = 525335;
    }
    *a2 |= 0x80417u;
    v17 &= 0xFFF7FBE8;
    v21 |= 0x80417u;
    a2[1] &= 0xFFF7FBE8;
    v26 = 1;
    v36 = 1;
  }
  else
  {
    v26 = 0;
  }
  if ( ((v17 | v20 & ~v21) & 0x80417) == 0 && (v21 & 0x80417) != 0 )
  {
    v37 = 1;
    if ( !v40 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
      v24 = 1;
    }
  }
  if ( (v27 = v21 | v17, v7 = v40, v27 == 0x100000) && !v40 && !v41
    || v24 && !v26
    || (LOBYTE(v25) = 1, (unsigned __int8)_CscObtainFcbMostlyExclusive(v42, v25)) )
  {
LABEL_49:
    v19 = 0;
    if ( !v16 )
    {
      v28 = v41;
      goto LABEL_57;
    }
LABEL_50:
    v28 = v41;
    if ( !v7 && !v41 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids);
      InformationEntry = 0;
      goto LABEL_76;
    }
LABEL_57:
    LODWORD(v40) = 0;
    if ( !v16
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        32,
        WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
        (unsigned int)a2[1],
        *a2);
    }
    v29 = 0;
    if ( !v16 )
      v29 = (int)a2;
    v30 = *((_QWORD *)&v43 + 1);
    InformationEntry = CscStoreSetInformationEntry(
                         *(_QWORD *)(*((_QWORD *)&v43 + 1) + 56LL),
                         v29,
                         v7,
                         0,
                         v28,
                         0,
                         (__int64)&v40);
    if ( InformationEntry >= 0 )
    {
      if ( (v45 & 1) == 0 && !v16 && (v37 || v36) )
      {
        *(_DWORD *)(v30 + 40) = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
            0,
            DWORD2(v45));
        }
      }
      if ( (v17 & 0x100000) != 0 )
      {
        v31 = *(_QWORD *)(v5 + 128);
        if ( v31 )
        {
          v32 = *(_QWORD *)(v31 + 48);
          CscAcquireLViewLock(*(_QWORD *)(v5 + 128));
          *(_DWORD *)(v32 + 4) &= 0xFFFFFCFF;
          CscReleaseLViewLock(v31);
          CscLoadLViewWasPreviouslyOffline(v31);
          CscFlushLViewWasPreviouslyOffline(v31);
        }
      }
    }
    if ( (_DWORD)v40 )
      CscNotifyReportChange(v42, (unsigned int)v40, 3);
    goto LABEL_76;
  }
  InformationEntry = -1073741757;
  v19 = 1458;
LABEL_76:
  if ( v38 )
    RxReleaseFcbPagingInMRx(0, v5);
LABEL_82:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids,
      (unsigned int)InformationEntry,
      v19);
  return (unsigned int)InformationEntry;
}

```

## disassembly

```asm
0x14004d450  push    rbp
0x14004d452  push    rbx
0x14004d453  push    rsi
0x14004d454  push    rdi
0x14004d455  push    r12
0x14004d457  push    r13
0x14004d459  push    r14
0x14004d45b  push    r15
0x14004d45d  lea     rbp, [rsp-38h]
0x14004d462  sub     rsp, 138h
0x14004d469  mov     rax, cs:__security_cookie
0x14004d470  xor     rax, rsp
0x14004d473  mov     [rbp+70h+var_50], rax
0x14004d477  mov     rax, [rcx+40h]
0x14004d47b  xorps   xmm0, xmm0
0x14004d47e  mov     r13, [rcx+38h]
0x14004d482  mov     r14, rdx
0x14004d485  xor     edx, edx; Val
0x14004d487  mov     [rsp+170h+var_128], r8
0x14004d48c  mov     rdi, r8
0x14004d48f  mov     [rsp+170h+var_118], rcx
0x14004d494  mov     r12, [rax+20h]
0x14004d498  mov     rbx, rcx
0x14004d49b  lea     rcx, [rbp+70h+var_A0]; void *
0x14004d49f  mov     [rsp+170h+var_120], r9
0x14004d4a4  lea     r8d, [rdx+50h]; Size
0x14004d4a8  mov     rsi, r9
0x14004d4ab  movups  [rsp+170h+var_110], xmm0
0x14004d4b0  movups  [rsp+170h+var_100], xmm0
0x14004d4b5  movups  [rbp+70h+var_E8], xmm0
0x14004d4b9  call    memset
0x14004d4be  xorps   xmm0, xmm0
0x14004d4c1  lea     rdx, [rsp+170h+var_110]
0x14004d4c6  xor     eax, eax
0x14004d4c8  mov     rcx, rbx
0x14004d4cb  movups  [rbp+70h+var_D8], xmm0
0x14004d4cf  mov     [rbp+70h+var_A8], rax
0x14004d4d3  movups  [rbp+70h+var_C8], xmm0
0x14004d4d7  mov     [rsp+170h+var_12D], al
0x14004d4db  movups  [rbp+70h+var_B8], xmm0
0x14004d4df  call    CscGetContexts
0x14004d4e4  lea     rax, [rbp+70h+var_E8]
0x14004d4e8  mov     byte ptr [rsp+170h+var_148], 1
0x14004d4ed  mov     r9b, 1
0x14004d4f0  mov     qword ptr [rsp+170h+FlushFile], rax
0x14004d4f5  mov     r8, rbx
0x14004d4f8  mov     rdx, r12
0x14004d4fb  mov     rcx, r13
0x14004d4fe  call    CscUpdateAndCaptureConnectionStateEx
0x14004d503  test    byte ptr [rbp+70h+var_E8], 20h
0x14004d507  lea     rcx, WPP_GLOBAL_Control
0x14004d50e  mov     al, byte ptr [rbp+70h+var_E8+1]
0x14004d511  jz      loc_14004D9D1
0x14004d517  test    al, 40h
0x14004d519  jnz     loc_14004D9D5
0x14004d51f  mov     [rsp+170h+var_12E], 0
0x14004d524  mov     r15b, 1
0x14004d527  mov     [rsp+170h+var_12F], 0
0x14004d52c  xor     ebx, ebx
0x14004d52e  mov     [rsp+170h+var_130], 0
0x14004d533  mov     r10, cs:WPP_GLOBAL_Control
0x14004d53a  cmp     r10, rcx
0x14004d53d  jz      short loc_14004D591
0x14004d53f  mov     eax, [r10+2Ch]
0x14004d543  test    al, 20h
0x14004d545  jz      short loc_14004D591
0x14004d547  mov     r11b, 0Bh
0x14004d54a  mov     r9b, 4Eh ; 'N'
0x14004d54d  mov     rax, rsi
0x14004d550  neg     rax
0x14004d553  mov     rax, rdi
0x14004d556  sbb     r8b, r8b
0x14004d559  and     r8b, r11b
0x14004d55c  add     r8b, r9b
0x14004d55f  neg     rax
0x14004d562  mov     byte ptr [rsp+170h+var_140], r8b
0x14004d567  mov     rax, r14
0x14004d56a  sbb     dl, dl
0x14004d56c  and     dl, r11b
0x14004d56f  add     dl, r9b
0x14004d572  neg     rax
0x14004d575  mov     byte ptr [rsp+170h+var_148], dl
0x14004d579  sbb     cl, cl
0x14004d57b  and     cl, r11b
0x14004d57e  add     cl, r9b
0x14004d581  mov     r9, r13
0x14004d584  mov     [rsp+170h+FlushFile], cl
0x14004d588  mov     rcx, [r10+18h]
0x14004d58c  call    WPP_SF_qccc
0x14004d591  test    r14, r14
0x14004d594  jz      loc_14004D833
0x14004d59a  mov     rcx, qword ptr [rsp+170h+var_110+8]
0x14004d59f  lea     rax, [rsp+170h+var_12D]
0x14004d5a4  mov     [rsp+170h+var_140], rbx
0x14004d5a9  lea     r9, [rbp+70h+var_D8]
0x14004d5ad  mov     [rsp+170h+var_148], rbx
0x14004d5b2  lea     r8, [rbp+70h+var_A0]
0x14004d5b6  xor     edx, edx
0x14004d5b8  mov     qword ptr [rsp+170h+FlushFile], rax
0x14004d5bd  mov     rcx, [rcx+38h]
0x14004d5c1  call    CscStoreQueryInformationEntryEx
0x14004d5c6  mov     edi, eax
0x14004d5c8  test    eax, eax
0x14004d5ca  jns     short loc_14004D5D6
0x14004d5cc  mov     esi, 508h
0x14004d5d1  jmp     loc_14004D9EC
0x14004d5d6  mov     r9d, [rbp+70h+var_A0]
0x14004d5da  mov     ecx, r9d
0x14004d5dd  not     ecx
0x14004d5df  mov     edi, r9d
0x14004d5e2  and     ecx, [r14+4]
0x14004d5e6  and     edi, [r14]
0x14004d5e9  mov     ebx, ecx
0x14004d5eb  or      ebx, 20h
0x14004d5ee  test    byte ptr [r14+4], 20h
0x14004d5f3  cmovz   ebx, ecx
0x14004d5f6  mov     esi, ebx
0x14004d5f8  or      esi, edi
0x14004d5fa  jz      loc_14004D82A
0x14004d600  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d607  lea     rdx, WPP_GLOBAL_Control
0x14004d60e  cmp     rcx, rdx
0x14004d611  jz      short loc_14004D646
0x14004d613  mov     eax, [rcx+2Ch]
0x14004d616  test    al, 40h
0x14004d618  jz      short loc_14004D646
0x14004d61a  mov     rcx, [rcx+18h]
0x14004d61e  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004d625  mov     dword ptr [rsp+170h+var_148], r9d
0x14004d62a  mov     edx, 1Bh
0x14004d62f  mov     r9d, ebx
0x14004d632  mov     dword ptr [rsp+170h+FlushFile], edi
0x14004d636  call    WPP_SF_DDd
0x14004d63b  mov     r9d, [rbp+70h+var_A0]
0x14004d63f  lea     rdx, WPP_GLOBAL_Control
0x14004d646  test    esi, 14840h
0x14004d64c  jz      short loc_14004D65D
0x14004d64e  mov     edi, 0C000000Dh
0x14004d653  mov     esi, 532h
0x14004d658  jmp     loc_14004D9EC
0x14004d65d  test    sil, 21h
0x14004d661  setnz   cl
0x14004d664  test    byte ptr [r13+0E8h], 10h
0x14004d66c  setnz   al
0x14004d66f  test    al, cl
0x14004d671  jz      short loc_14004D682
0x14004d673  mov     edi, 0C000000Dh
0x14004d678  mov     esi, 540h
0x14004d67d  jmp     loc_14004D9EC
0x14004d682  mov     r8d, [r12+98h]
0x14004d68a  test    r8b, 2
0x14004d68e  jnz     short loc_14004D6DE
0x14004d690  mov     rax, qword ptr [rsp+170h+var_100]
0x14004d695  test    dword ptr [rax+18h], 800h
0x14004d69c  jnz     short loc_14004D6DE
0x14004d69e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d6a5  cmp     rcx, rdx
0x14004d6a8  jz      short loc_14004D6CF
0x14004d6aa  mov     eax, [rcx+2Ch]
0x14004d6ad  test    al, 40h
0x14004d6af  jz      short loc_14004D6CF
0x14004d6b1  mov     rcx, [rcx+18h]
0x14004d6b5  mov     edx, 1Ch
0x14004d6ba  mov     dword ptr [rsp+170h+FlushFile], r8d
0x14004d6bf  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004d6c6  lea     r9d, [rdx-1Ah]
0x14004d6ca  call    WPP_SF_Dd
0x14004d6cf  mov     edi, 0C0000022h
0x14004d6d4  mov     esi, 55Bh
0x14004d6d9  jmp     loc_14004D9EC
0x14004d6de  xor     r12b, r12b
0x14004d6e1  xor     r15b, r15b
0x14004d6e4  test    sil, 20h
0x14004d6e8  jz      short loc_14004D707
0x14004d6ea  mov     r8b, 1
0x14004d6ed  mov     rdx, r13
0x14004d6f0  xor     ecx, ecx
0x14004d6f2  call    cs:__imp_RxAcquireExclusiveFcbPagingInMRx
0x14004d6f9  nop     dword ptr [rax+rax+00h]
0x14004d6fe  mov     r9d, [rbp+70h+var_A0]
0x14004d702  mov     [rsp+170h+var_12E], 1
0x14004d707  mov     edx, 80417h
0x14004d70c  test    bl, 20h
0x14004d70f  jz      short loc_14004D788
0x14004d711  test    byte ptr [rbp+70h+var_E8], 10h
0x14004d715  jz      short loc_14004D76E
0x14004d717  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d71e  lea     rax, WPP_GLOBAL_Control
0x14004d725  cmp     rcx, rax
0x14004d728  jz      short loc_14004D749
0x14004d72a  mov     eax, [rcx+2Ch]
0x14004d72d  test    al, 40h
0x14004d72f  jz      short loc_14004D749
0x14004d731  mov     rcx, [rcx+18h]
0x14004d735  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004d73c  mov     edx, 1Dh
0x14004d741  mov     r9, r13
0x14004d744  call    WPP_SF_q
0x14004d749  xor     r9d, r9d; UninitializeCacheMaps
0x14004d74c  mov     [rsp+170h+FlushFile], r12b; FlushFile
0x14004d751  xor     r8d, r8d; Length
0x14004d754  xor     edx, edx; FileOffset
0x14004d756  mov     rcx, r13; Fcb
0x14004d759  call    cs:__imp_RxPurgeFcbInSystemCache
0x14004d760  nop     dword ptr [rax+rax+00h]
0x14004d765  mov     r9d, [rbp+70h+var_A0]
0x14004d769  mov     edx, 80417h
0x14004d76e  or      [r14], edx
0x14004d771  mov     eax, 0FFF7FBE8h
0x14004d776  and     ebx, eax
0x14004d778  or      edi, edx
0x14004d77a  and     [r14+4], eax
0x14004d77e  mov     sil, 1
0x14004d781  mov     [rsp+170h+var_130], sil
0x14004d786  jmp     short loc_14004D78B
0x14004d788  mov     sil, r12b
0x14004d78b  mov     eax, edi
0x14004d78d  not     eax
0x14004d78f  and     eax, r9d
0x14004d792  or      eax, ebx
0x14004d794  test    edx, eax
0x14004d796  setz    cl
0x14004d799  test    edx, edi
0x14004d79b  setnz   al
0x14004d79e  test    al, cl
0x14004d7a0  jz      short loc_14004D7E1
0x14004d7a2  cmp     [rsp+170h+var_128], 0
0x14004d7a8  mov     [rsp+170h+var_12F], 1
0x14004d7ad  jnz     short loc_14004D7E1
0x14004d7af  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d7b6  lea     rax, WPP_GLOBAL_Control
0x14004d7bd  cmp     rcx, rax
0x14004d7c0  jz      short loc_14004D7DE
0x14004d7c2  mov     eax, [rcx+2Ch]
0x14004d7c5  test    al, 40h
0x14004d7c7  jz      short loc_14004D7DE
0x14004d7c9  mov     rcx, [rcx+18h]
0x14004d7cd  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004d7d4  mov     edx, 1Eh
0x14004d7d9  call    WPP_SF_
0x14004d7de  mov     r12b, 1
0x14004d7e1  mov     eax, ebx
0x14004d7e3  or      eax, edi
0x14004d7e5  mov     rdi, [rsp+170h+var_128]
0x14004d7ea  cmp     eax, 100000h
0x14004d7ef  jnz     short loc_14004D7FD
0x14004d7f1  test    rdi, rdi
0x14004d7f4  jnz     short loc_14004D7FD
0x14004d7f6  cmp     [rsp+170h+var_120], rdi
0x14004d7fb  jz      short loc_14004D833
0x14004d7fd  test    r12b, r12b
0x14004d800  jz      short loc_14004D807
0x14004d802  test    sil, sil
0x14004d805  jz      short loc_14004D833
0x14004d807  mov     rcx, [rsp+170h+var_118]
0x14004d80c  mov     r8b, 1
0x14004d80f  mov     dl, r8b
0x14004d812  call    __CscObtainFcbMostlyExclusive
0x14004d817  test    al, al
0x14004d819  jnz     short loc_14004D833
0x14004d81b  mov     edi, 0C0000043h
0x14004d820  mov     esi, 5B2h
0x14004d825  jmp     loc_14004D9B7
0x14004d82a  mov     rdi, [rsp+170h+var_128]
0x14004d82f  xor     esi, esi
0x14004d831  jmp     short loc_14004D83A
0x14004d833  xor     esi, esi
0x14004d835  test    r15b, r15b
0x14004d838  jz      short loc_14004D87D
0x14004d83a  mov     r12, [rsp+170h+var_120]
0x14004d83f  test    rdi, rdi
0x14004d842  jnz     short loc_14004D882
0x14004d844  test    r12, r12
0x14004d847  jnz     short loc_14004D882
0x14004d849  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d850  lea     rax, WPP_GLOBAL_Control
0x14004d857  cmp     rcx, rax
0x14004d85a  jz      short loc_14004D876
0x14004d85c  mov     eax, [rcx+2Ch]
0x14004d85f  test    al, 40h
0x14004d861  jz      short loc_14004D876
0x14004d863  mov     rcx, [rcx+18h]
0x14004d867  lea     edx, [rdi+1Fh]
0x14004d86a  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
0x14004d871  call    WPP_SF_
0x14004d876  xor     edi, edi
0x14004d878  jmp     loc_14004D9B7
0x14004d87d  mov     r12, [rsp+170h+var_120]
0x14004d882  mov     dword ptr [rsp+170h+var_128], 0
0x14004d88a  test    r15b, r15b
0x14004d88d  jnz     short loc_14004D8C9
0x14004d88f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d896  lea     rax, WPP_GLOBAL_Control
0x14004d89d  cmp     rcx, rax
0x14004d8a0  jz      short loc_14004D8C9
0x14004d8a2  mov     eax, [rcx+2Ch]
0x14004d8a5  test    al, 40h
0x14004d8a7  jz      short loc_14004D8C9
0x14004d8a9  mov     eax, [r14]
0x14004d8ac  lea     r8, WPP_9fe6cec971b631e5a08288fb958a861f_Traceguids
  ... truncated ...
```
