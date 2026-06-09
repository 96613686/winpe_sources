# UlExtractAndAppendAuthenticationResponseInfo

- ea: `0x1400a7b50`
- end: `0x1400a84d4`
- name: `UlExtractAndAppendAuthenticationResponseInfo`
- size: `2436`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x14001aba0`
- `0x14001d270`
- `0x1400474d0`

## callees

- `0x140049bc0`
- `0x140074400`
- `0x1400a7b50`
- `0x1400b1acc`
- `0x1400b45cc`
- `0x1400b573c`
- `0x1400caf44`
- `0x1400fb400`
- `0x140142df4`
- `0x140145fb4`
- `0x140146204`
- `0x140146744`
- `0x140146b88`
- `0x140146c38`
- `0x140167840`
- `0x140167c40`
- `0x1401c49c4`
- `0x1401d7ea8`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400a7c5b`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7cd8`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7d77`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7e7d`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7fc5`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7c5b`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7cd8`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7d77`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7e7d`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7fc5`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8248`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a83f5`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8248`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a83f5`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a816b`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a8327`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a816b`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a8327`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a81f0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a839e`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a81f0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a839e`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a81a1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a8352`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a81a1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a8352`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a81ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8254`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a835e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8401`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a81ad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8254`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a835e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8401`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8156`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a81dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8312`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a838b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8156`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a81dd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8312`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a838b`

## pseudocode

```c
__int64 __fastcall UlExtractAndAppendAuthenticationResponseInfo(
        __int64 a1,
        __int64 a2,
        IRP *a3,
        char a4,
        unsigned __int8 a5,
        char *a6)
{
  char v7; // bl
  int v10; // edx
  int v11; // r8d
  char v12; // di
  int AuthInfoFromMode; // esi
  __int64 v14; // r13
  char v15; // bl
  _OWORD *v16; // r15
  int v17; // r8d
  SIZE_T v18; // rdx
  unsigned __int16 v19; // r9
  unsigned int v20; // ecx
  SIZE_T v21; // rdx
  ULONG v22; // r8d
  _QWORD *v23; // rbx
  BOOLEAN v24; // al
  ULONG v25; // r8d
  __int64 v26; // r15
  __int64 v27; // r15
  __int64 v28; // rbx
  int v29; // r9d
  int v30; // ecx
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r15
  __int64 v35; // r15
  const char *v36; // r12
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  _QWORD *v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // rcx
  char v44; // [rsp+50h] [rbp-F8h]
  char v45; // [rsp+51h] [rbp-F7h] BYREF
  char v46; // [rsp+52h] [rbp-F6h]
  unsigned __int16 v47; // [rsp+54h] [rbp-F4h]
  int v48; // [rsp+58h] [rbp-F0h]
  volatile void *Address[2]; // [rsp+60h] [rbp-E8h] BYREF
  int v50; // [rsp+70h] [rbp-D8h]
  _OWORD v51[5]; // [rsp+80h] [rbp-C8h] BYREF
  int v52[2]; // [rsp+D0h] [rbp-78h]
  int v53[4]; // [rsp+D8h] [rbp-70h] BYREF
  __int64 v54; // [rsp+E8h] [rbp-60h]
  _OWORD *v55; // [rsp+F0h] [rbp-58h]
  __int64 v56; // [rsp+F8h] [rbp-50h]
  _QWORD *v57; // [rsp+100h] [rbp-48h]
  char v58; // [rsp+150h] [rbp+8h]
  char v59; // [rsp+150h] [rbp+8h]
  char v60; // [rsp+158h] [rbp+10h] BYREF
  PIRP Irp; // [rsp+160h] [rbp+18h]
  char v62; // [rsp+168h] [rbp+20h]

  v62 = a4;
  Irp = a3;
  v7 = (char)a3;
  *(_OWORD *)Address = 0;
  memset(v51, 0, sizeof(v51));
  v12 = 0;
  v60 = 0;
  v45 = 0;
  AuthInfoFromMode = 0;
  v57 = (_QWORD *)(a1 + 24);
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 1096LL);
  v56 = v14;
  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qiqqllq(a5, v10, v11, a1, *(_QWORD *)(a1 + 64), a2, v7, a4, a5, a6);
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
    goto LABEL_114;
  v15 = 0;
  v46 = 0;
  v44 = 0;
  *(_QWORD *)v52 = 0;
  v47 = *(_WORD *)(a2 + 552);
  if ( !v47 )
    goto LABEL_114;
  v16 = *(_OWORD **)(a2 + 560);
  if ( !IoIs32bitProcess(Irp) )
  {
    v18 = 16LL * v47;
    if ( UxKirNewUma )
    {
      AuthInfoFromMode = UxProbeAlignment(v16, v18, 8);
      v48 = AuthInfoFromMode;
      if ( AuthInfoFromMode < 0 )
        goto LABEL_114;
      goto LABEL_13;
    }
    UlProbeForRead(v16, v18, 8u);
  }
  v19 = v47;
LABEL_13:
  v20 = 0;
  v50 = 0;
  v55 = v16;
  while ( v20 < v19 )
  {
    if ( UxKirNewUma && !IoIs32bitProcess(Irp) )
    {
      if ( a4 )
        RtlCopyFromUser(Address, v16, 0x10u);
      else
        RtlCopyVolatileMemory(Address, v16, 0x10u);
    }
    else
    {
      *(_OWORD *)Address = *v16;
    }
    if ( SLODWORD(Address[0]) >= 4 )
    {
      AuthInfoFromMode = -1073741811;
      v48 = -1073741811;
      if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
        WPP_SF_d(774, 130, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 3221225485LL);
      goto LABEL_114;
    }
    if ( ((LODWORD(Address[0]) - 1) & 0xFFFFFFFD) == 0 )
    {
      if ( LODWORD(Address[0]) == 1 && !v15 )
      {
        if ( IoIs32bitProcess(Irp) )
        {
          if ( HIDWORD(Address[0]) < 0x24 )
          {
            AuthInfoFromMode = -1073741811;
            v48 = -1073741811;
            if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
              WPP_SF_d(774, 131, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 3221225485LL);
            goto LABEL_114;
          }
          v21 = HIDWORD(Address[0]);
          v22 = 4;
          if ( UxKirNewUma )
          {
            v23 = Address[1];
            AuthInfoFromMode = UxProbeAlignment(Address[1], HIDWORD(Address[0]), 4);
            v48 = AuthInfoFromMode;
            if ( AuthInfoFromMode < 0 )
              goto LABEL_114;
            goto LABEL_43;
          }
        }
        else
        {
          if ( HIDWORD(Address[0]) < 0x40 )
          {
            AuthInfoFromMode = -1073741811;
            v48 = -1073741811;
            if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
              WPP_SF_d(774, 132, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 3221225485LL);
            goto LABEL_114;
          }
          v21 = HIDWORD(Address[0]);
          v22 = 8;
          if ( UxKirNewUma )
          {
            v23 = Address[1];
            AuthInfoFromMode = UxProbeAlignment(Address[1], HIDWORD(Address[0]), 8);
            v48 = AuthInfoFromMode;
            if ( AuthInfoFromMode < 0 )
              goto LABEL_114;
            goto LABEL_43;
          }
        }
        UlProbeForRead(Address[1], v21, v22);
        v23 = Address[1];
LABEL_43:
        if ( UxKirNewUma )
        {
          AuthInfoFromMode = UlGetAuthInfoFromMode(v23, Irp, v51);
          v48 = AuthInfoFromMode;
          if ( AuthInfoFromMode < 0 )
            goto LABEL_114;
        }
        else
        {
          v24 = IoIs32bitProcess(Irp);
          *(_QWORD *)&v51[0] = *v23;
          DWORD2(v51[0]) = *((_DWORD *)v23 + 2);
          if ( v24 )
          {
            *((_QWORD *)&v51[2] + 1) = *((unsigned int *)v23 + 6);
            LOWORD(v51[2]) = *((_WORD *)v23 + 10);
            *((_QWORD *)&v51[1] + 1) = *((unsigned int *)v23 + 4);
            LOWORD(v51[1]) = *((_WORD *)v23 + 6);
            *((_QWORD *)&v51[3] + 1) = *((unsigned int *)v23 + 8);
            LOWORD(v51[3]) = *((_WORD *)v23 + 14);
          }
          else
          {
            *((_QWORD *)&v51[2] + 1) = v23[5];
            LOWORD(v51[2]) = *((_WORD *)v23 + 16);
            *((_QWORD *)&v51[1] + 1) = v23[3];
            LOWORD(v51[1]) = *((_WORD *)v23 + 8);
            *((_QWORD *)&v51[3] + 1) = v23[7];
            LOWORD(v51[3]) = *((_WORD *)v23 + 24);
            v51[4] = 0;
          }
          v51[4] = 0;
        }
        v15 = 1;
        v46 = 1;
        goto LABEL_65;
      }
      if ( LODWORD(Address[0]) == 3 && !v44 )
      {
        if ( IoIs32bitProcess(Irp) )
        {
          if ( HIDWORD(Address[0]) < 0x10 )
          {
            AuthInfoFromMode = -1073741811;
            v48 = -1073741811;
            if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
              WPP_SF_d(774, 133, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 3221225485LL);
            goto LABEL_114;
          }
          v25 = 4;
        }
        else
        {
          if ( HIDWORD(Address[0]) < 0x18 )
          {
            AuthInfoFromMode = -1073741811;
            v48 = -1073741811;
            if ( (BYTE8(xmmword_1401A2C90) & 0x40) != 0 )
              WPP_SF_d(774, 134, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, 3221225485LL);
            goto LABEL_114;
          }
          v25 = 8;
        }
        UlProbeForRead(Address[1], HIDWORD(Address[0]), v25);
        v44 = 1;
        *(volatile void **)v52 = Address[1];
      }
    }
LABEL_65:
    v20 = ++v50;
    v55 = ++v16;
    v19 = v47;
  }
  if ( !v15 )
  {
    if ( !v44 )
      goto LABEL_114;
    goto LABEL_86;
  }
  AuthInfoFromMode = UlVerifyAuthConfig(v14, v51);
  if ( AuthInfoFromMode < 0 )
    goto LABEL_114;
  v26 = *(_QWORD *)(a1 + 1544);
  if ( v26 )
  {
    v58 = 1;
    goto LABEL_75;
  }
  v58 = 0;
  if ( *(_BYTE *)(a1 + 1537) )
  {
    v27 = *(_QWORD *)(a1 + 1320) + 296LL;
  }
  else
  {
    v26 = *(_QWORD *)(a1 + 1328);
LABEL_75:
    v27 = v26 + 304;
  }
  KeEnterCriticalRegion();
  v28 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v14 + 1368), 0);
  LOBYTE(v29) = a4;
  AuthInfoFromMode = UlIsAuthChangeNeededOld(v30, v27, (unsigned int)v51, v29, (__int64)&v60);
  ExReleaseCacheAwarePushLockSharedEx(v28, 0);
  KeLeaveCriticalRegion();
  if ( AuthInfoFromMode < 0 )
    goto LABEL_114;
  if ( v60 && a5 )
  {
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v14 + 1368));
    if ( !v58 || (v32 = *(_QWORD *)(a1 + 1328), *(_QWORD *)(a1 + 1544) == v32) )
    {
      v33 = v27;
LABEL_84:
      LOBYTE(v31) = a4;
      AuthInfoFromMode = UlUpdateAuthConfig(v14, v33, v51, v31);
    }
    else if ( (v51[0] & 1) != 0 )
    {
      v33 = v32 + 304;
      goto LABEL_84;
    }
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v14 + 1368));
    KeLeaveCriticalRegion();
    if ( AuthInfoFromMode < 0 )
      goto LABEL_114;
  }
LABEL_86:
  if ( v44 )
  {
    *(_OWORD *)v53 = 0;
    v54 = 0;
    LOBYTE(v17) = a4;
    AuthInfoFromMode = UlCaptureChannelBindConfig(v14, v52[0], v17, (int)v53, Irp, a4);
    if ( AuthInfoFromMode < 0 )
      goto LABEL_114;
    v34 = *(_QWORD *)(a1 + 1584);
    if ( v34 )
    {
      v59 = 1;
      goto LABEL_93;
    }
    v59 = 0;
    if ( *(_BYTE *)(a1 + 1577) )
    {
      v35 = *(_QWORD *)(a1 + 1320) + 376LL;
      v36 = "SERVER_SESSION";
    }
    else
    {
      v34 = *(_QWORD *)(a1 + 1328);
LABEL_93:
      v36 = "DEFAULT_GROUP";
      v35 = v34 + 384;
    }
    KeEnterCriticalRegion();
    v37 = ExAcquireCacheAwarePushLockSharedEx(*(_QWORD *)(v14 + 1368), 0);
    AuthInfoFromMode = UlIsChannelBindChangeNeeded(v35, v53, &v45);
    ExReleaseCacheAwarePushLockSharedEx(v37, 0);
    KeLeaveCriticalRegion();
    if ( AuthInfoFromMode >= 0 && v45 && a5 )
    {
      KeEnterCriticalRegion();
      ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v14 + 1368));
      if ( !v59 || (v38 = *(_QWORD *)(a1 + 1328), *(_QWORD *)(a1 + 1584) == v38) )
      {
        v39 = v35;
LABEL_102:
        UlUpdateChannelBindConfig(v39, v53);
      }
      else
      {
        v36 = "OWNER_GROUP";
        if ( (v53[0] & 1) != 0 )
        {
          v39 = v38 + 384;
          goto LABEL_102;
        }
      }
      ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v14 + 1368));
      KeLeaveCriticalRegion();
      v40 = v57;
      v41 = *v57;
      if ( *v57 )
      {
        v42 = *(_QWORD *)(v41 + 1096);
        if ( (*(_BYTE *)(v42 + 1762) & 0x20) != 0
          && (!*(_QWORD *)(v42 + 1776) || (unsigned __int8)UlEtwEvaluateFilterForRequestConnection(a1, v41, 0)) )
        {
          McTemplateK0s_EtwWriteTransfer(*(_QWORD *)(*v40 + 1096LL) + 1688LL, v41, a1 + 72, v36);
        }
      }
    }
    UlCleanupChannelBindConfig(v53);
    if ( AuthInfoFromMode < 0 )
      goto LABEL_114;
  }
  if ( a6 )
  {
    if ( v60 || v45 )
      v12 = 1;
    *a6 = v12;
  }
LABEL_114:
  if ( (BYTE1(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_d(1038, 136, WPP_3bc569ebedc33674d1577199996181a5_Traceguids, (unsigned int)AuthInfoFromMode);
  return (unsigned int)AuthInfoFromMode;
}

```

## disassembly

```asm
0x1400a7b50  mov     rax, rsp
0x1400a7b53  mov     [rax+20h], r9b
0x1400a7b57  mov     [rax+18h], r8
0x1400a7b5b  mov     [rax+8], rcx
0x1400a7b5f  push    rbx
0x1400a7b60  push    rsi
0x1400a7b61  push    rdi
0x1400a7b62  push    r12
0x1400a7b64  push    r13
0x1400a7b66  push    r14
0x1400a7b68  push    r15
0x1400a7b6a  sub     rsp, 110h
0x1400a7b71  movsx   r12d, r9b
0x1400a7b75  mov     rbx, r8
0x1400a7b78  mov     r15, rdx
0x1400a7b7b  mov     r14, rcx
0x1400a7b7e  xorps   xmm0, xmm0
0x1400a7b81  movups  xmmword ptr [rsp+148h+Address], xmm0
0x1400a7b86  xor     edx, edx; Val
0x1400a7b88  lea     r8d, [rdx+50h]; Size
0x1400a7b8c  lea     rcx, [rax-0C8h]; void *
0x1400a7b93  call    memset
0x1400a7b98  xor     edi, edi
0x1400a7b9a  mov     [rsp+148h+arg_8], dil
0x1400a7ba2  mov     [rsp+148h+var_F7], dil
0x1400a7ba7  mov     esi, edi
0x1400a7ba9  lea     rax, [r14+18h]
0x1400a7bad  mov     [rsp+148h+var_48], rax
0x1400a7bb5  mov     rax, [rax]
0x1400a7bb8  mov     r13, [rax+448h]
0x1400a7bbf  mov     [rsp+148h+var_50], r13
0x1400a7bc7  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400a7bce  jz      short loc_1400A7C09
0x1400a7bd0  movzx   ecx, [rsp+148h+arg_20]
0x1400a7bd8  mov     rax, [rsp+148h+arg_28]
0x1400a7be0  mov     [rsp+148h+var_100], rax
0x1400a7be5  mov     [rsp+148h+var_108], ecx
0x1400a7be9  mov     [rsp+148h+var_110], r12d
0x1400a7bee  mov     [rsp+148h+var_118], rbx
0x1400a7bf3  mov     qword ptr [rsp+148h+var_120], r15
0x1400a7bf8  mov     rax, [r14+40h]
0x1400a7bfc  mov     [rsp+148h+var_128], rax
0x1400a7c01  mov     r9, r14
0x1400a7c04  call    WPP_SF_qiqqllq
0x1400a7c09  mov     rax, [rsp+148h+arg_28]
0x1400a7c11  test    rax, rax
0x1400a7c14  jz      short loc_1400A7C19
0x1400a7c16  mov     [rax], dil
0x1400a7c19  test    r15, r15
0x1400a7c1c  jz      loc_1400A849C
0x1400a7c22  mov     bl, dil
0x1400a7c25  mov     [rsp+148h+var_F6], bl
0x1400a7c29  mov     [rsp+148h+var_F8], dil
0x1400a7c2e  mov     qword ptr [rsp+148h+var_78], rdi
0x1400a7c36  movzx   eax, word ptr [r15+228h]
0x1400a7c3e  mov     [rsp+148h+var_F4], ax
0x1400a7c43  test    ax, ax
0x1400a7c46  jz      loc_1400A849C
0x1400a7c4c  mov     r15, [r15+230h]
0x1400a7c53  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7c5b  call    cs:__imp_IoIs32bitProcess
0x1400a7c62  nop     dword ptr [rax+rax+00h]
0x1400a7c67  test    al, al
0x1400a7c69  jnz     short loc_1400A7CA7
0x1400a7c6b  movzx   r9d, [rsp+148h+var_F4]
0x1400a7c71  mov     edx, r9d
0x1400a7c74  shl     rdx, 4; Length
0x1400a7c78  mov     r8d, 8; Alignment
0x1400a7c7e  mov     rcx, r15; Address
0x1400a7c81  cmp     cs:UxKirNewUma, al
0x1400a7c87  jnz     short loc_1400A7C93
0x1400a7c89  mov     r9b, r12b
0x1400a7c8c  call    UlProbeForRead
0x1400a7c91  jmp     short loc_1400A7CA7
0x1400a7c93  call    UxProbeAlignment
0x1400a7c98  mov     esi, eax
0x1400a7c9a  mov     [rsp+148h+var_F0], eax
0x1400a7c9e  test    eax, eax
0x1400a7ca0  jns     short loc_1400A7CAD
0x1400a7ca2  jmp     loc_1400A849C
0x1400a7ca7  movzx   r9d, [rsp+148h+var_F4]
0x1400a7cad  mov     ecx, edi
0x1400a7caf  mov     [rsp+148h+var_D8], ecx
0x1400a7cb3  mov     [rsp+148h+var_58], r15
0x1400a7cbb  movzx   eax, r9w
0x1400a7cbf  cmp     ecx, eax
0x1400a7cc1  jnb     loc_1400A8099
0x1400a7cc7  cmp     cs:UxKirNewUma, 0
0x1400a7cce  jz      short loc_1400A7CE8
0x1400a7cd0  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7cd8  call    cs:__imp_IoIs32bitProcess
0x1400a7cdf  nop     dword ptr [rax+rax+00h]
0x1400a7ce4  test    al, al
0x1400a7ce6  jz      short loc_1400A7CF4
0x1400a7ce8  movups  xmm0, xmmword ptr [r15]
0x1400a7cec  movdqu  xmmword ptr [rsp+148h+Address], xmm0
0x1400a7cf2  jmp     short loc_1400A7D13
0x1400a7cf4  mov     r8d, 10h; Size
0x1400a7cfa  mov     rdx, r15; Src
0x1400a7cfd  lea     rcx, [rsp+148h+Address]; void *
0x1400a7d02  test    r12b, r12b
0x1400a7d05  jz      short loc_1400A7D0E
0x1400a7d07  call    RtlCopyFromUser
0x1400a7d0c  jmp     short loc_1400A7D13
0x1400a7d0e  call    RtlCopyVolatileMemory
0x1400a7d13  mov     rcx, [rsp+148h+Address]
0x1400a7d18  cmp     ecx, 4
0x1400a7d1b  jl      short loc_1400A7D4F
0x1400a7d1d  mov     r9d, 0C000000Dh
0x1400a7d23  mov     esi, r9d
0x1400a7d26  mov     [rsp+148h+var_F0], r9d
0x1400a7d2b  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7d32  jz      short loc_1400A7D4A
0x1400a7d34  mov     edx, 82h
0x1400a7d39  mov     ecx, 306h
0x1400a7d3e  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7d45  call    WPP_SF_d
0x1400a7d4a  jmp     loc_1400A849C
0x1400a7d4f  lea     eax, [rcx-1]
0x1400a7d52  test    eax, 0FFFFFFFDh
0x1400a7d57  jz      short loc_1400A7D5E
0x1400a7d59  jmp     loc_1400A8078
0x1400a7d5e  cmp     ecx, 1
0x1400a7d61  jnz     loc_1400A7FA9
0x1400a7d67  test    bl, bl
0x1400a7d69  jnz     loc_1400A7FA9
0x1400a7d6f  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7d77  call    cs:__imp_IoIs32bitProcess
0x1400a7d7e  nop     dword ptr [rax+rax+00h]
0x1400a7d83  mov     ecx, dword ptr [rsp+148h+Address+4]
0x1400a7d87  test    al, al
0x1400a7d89  jz      short loc_1400A7DF0
0x1400a7d8b  cmp     ecx, 24h ; '$'
0x1400a7d8e  jnb     short loc_1400A7DC2
0x1400a7d90  mov     r9d, 0C000000Dh
0x1400a7d96  mov     esi, r9d
0x1400a7d99  mov     [rsp+148h+var_F0], r9d
0x1400a7d9e  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7da5  jz      short loc_1400A7DBD
0x1400a7da7  mov     edx, 83h
0x1400a7dac  mov     ecx, 306h
0x1400a7db1  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7db8  call    WPP_SF_d
0x1400a7dbd  jmp     loc_1400A849C
0x1400a7dc2  mov     rdx, rcx
0x1400a7dc5  mov     r8d, 4
0x1400a7dcb  cmp     cs:UxKirNewUma, 0
0x1400a7dd2  jz      short loc_1400A7E39
0x1400a7dd4  mov     rbx, [rsp+148h+Address+8]
0x1400a7dd9  mov     rcx, rbx
0x1400a7ddc  call    UxProbeAlignment
0x1400a7de1  mov     esi, eax
0x1400a7de3  mov     [rsp+148h+var_F0], eax
0x1400a7de7  test    eax, eax
0x1400a7de9  jns     short loc_1400A7E68
0x1400a7deb  jmp     loc_1400A849C
0x1400a7df0  cmp     ecx, 40h ; '@'
0x1400a7df3  jnb     short loc_1400A7E27
0x1400a7df5  mov     r9d, 0C000000Dh
0x1400a7dfb  mov     esi, r9d
0x1400a7dfe  mov     [rsp+148h+var_F0], r9d
0x1400a7e03  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7e0a  jz      short loc_1400A7E22
0x1400a7e0c  mov     edx, 84h
0x1400a7e11  mov     ecx, 306h
0x1400a7e16  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7e1d  call    WPP_SF_d
0x1400a7e22  jmp     loc_1400A849C
0x1400a7e27  mov     rdx, rcx; Length
0x1400a7e2a  mov     r8d, 8; Alignment
0x1400a7e30  cmp     cs:UxKirNewUma, 0
0x1400a7e37  jnz     short loc_1400A7E4D
0x1400a7e39  mov     r9b, r12b
0x1400a7e3c  mov     rcx, [rsp+148h+Address+8]; Address
0x1400a7e41  call    UlProbeForRead
0x1400a7e46  mov     rbx, [rsp+148h+Address+8]
0x1400a7e4b  jmp     short loc_1400A7E68
0x1400a7e4d  mov     rbx, [rsp+148h+Address+8]
0x1400a7e52  mov     rcx, rbx
0x1400a7e55  call    UxProbeAlignment
0x1400a7e5a  mov     esi, eax
0x1400a7e5c  mov     [rsp+148h+var_F0], eax
0x1400a7e60  test    eax, eax
0x1400a7e62  js      loc_1400A849C
0x1400a7e68  cmp     cs:UxKirNewUma, 0
0x1400a7e6f  jnz     loc_1400A7F7A
0x1400a7e75  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7e7d  call    cs:__imp_IoIs32bitProcess
0x1400a7e84  nop     dword ptr [rax+rax+00h]
0x1400a7e89  mov     ecx, [rbx]
0x1400a7e8b  mov     [rsp+148h+var_C8], ecx
0x1400a7e92  test    al, al
0x1400a7e94  mov     eax, [rbx+4]
0x1400a7e97  mov     [rsp+148h+var_C4], eax
0x1400a7e9e  mov     al, [rbx+8]
0x1400a7ea1  mov     [rsp+148h+var_C0], al
0x1400a7ea8  mov     al, [rbx+9]
0x1400a7eab  mov     [rsp+148h+var_BF], al
0x1400a7eb2  mov     al, [rbx+0Ah]
0x1400a7eb5  mov     [rsp+148h+var_BE], al
0x1400a7ebc  mov     al, [rbx+0Bh]
0x1400a7ebf  mov     [rsp+148h+var_BD], al
0x1400a7ec6  jz      short loc_1400A7F0F
0x1400a7ec8  mov     eax, [rbx+18h]
0x1400a7ecb  mov     [rsp+148h+var_A0], rax
0x1400a7ed3  movzx   eax, word ptr [rbx+14h]
0x1400a7ed7  mov     [rsp+148h+var_A8], ax
0x1400a7edf  mov     eax, [rbx+10h]
0x1400a7ee2  mov     [rsp+148h+var_B0], rax
0x1400a7eea  movzx   eax, word ptr [rbx+0Ch]
0x1400a7eee  mov     [rsp+148h+var_B8], ax
0x1400a7ef6  mov     eax, [rbx+20h]
0x1400a7ef9  mov     [rsp+148h+var_90], rax
0x1400a7f01  movzx   eax, word ptr [rbx+1Ch]
0x1400a7f05  mov     [rsp+148h+var_98], ax
0x1400a7f0d  jmp     short loc_1400A7F63
0x1400a7f0f  mov     rax, [rbx+28h]
0x1400a7f13  mov     [rsp+148h+var_A0], rax
0x1400a7f1b  movzx   eax, word ptr [rbx+20h]
0x1400a7f1f  mov     [rsp+148h+var_A8], ax
0x1400a7f27  mov     rax, [rbx+18h]
0x1400a7f2b  mov     [rsp+148h+var_B0], rax
0x1400a7f33  movzx   eax, word ptr [rbx+10h]
0x1400a7f37  mov     [rsp+148h+var_B8], ax
0x1400a7f3f  mov     rax, [rbx+38h]
0x1400a7f43  mov     [rsp+148h+var_90], rax
0x1400a7f4b  movzx   eax, word ptr [rbx+30h]
0x1400a7f4f  mov     [rsp+148h+var_98], ax
0x1400a7f57  xorps   xmm0, xmm0
0x1400a7f5a  movdqa  [rsp+148h+var_88], xmm0
0x1400a7f63  xorps   xmm0, xmm0
0x1400a7f66  movdqa  [rsp+148h+var_88], xmm0
0x1400a7f6f  mov     bl, 1
0x1400a7f71  mov     [rsp+148h+var_F6], bl
0x1400a7f75  jmp     loc_1400A8078
0x1400a7f7a  lea     rax, [rsp+148h+var_C8]
0x1400a7f82  mov     [rsp+148h+var_128], rax; void *
0x1400a7f87  mov     r8b, r12b
0x1400a7f8a  mov     rdx, [rsp+148h+Irp]; Irp
0x1400a7f92  mov     rcx, rbx; Src
0x1400a7f95  call    UlGetAuthInfoFromMode
0x1400a7f9a  mov     esi, eax
0x1400a7f9c  mov     [rsp+148h+var_F0], eax
0x1400a7fa0  test    eax, eax
0x1400a7fa2  jns     short loc_1400A7F6F
0x1400a7fa4  jmp     loc_1400A849C
0x1400a7fa9  cmp     ecx, 3
0x1400a7fac  jnz     loc_1400A8078
0x1400a7fb2  cmp     [rsp+148h+var_F8], dil
0x1400a7fb7  jnz     loc_1400A8078
0x1400a7fbd  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7fc5  call    cs:__imp_IoIs32bitProcess
0x1400a7fcc  nop     dword ptr [rax+rax+00h]
0x1400a7fd1  test    al, al
0x1400a7fd3  jz      short loc_1400A8016
0x1400a7fd5  cmp     dword ptr [rsp+148h+Address+4], 10h
0x1400a7fda  jnb     short loc_1400A800E
0x1400a7fdc  mov     r9d, 0C000000Dh
0x1400a7fe2  mov     esi, r9d
0x1400a7fe5  mov     [rsp+148h+var_F0], r9d
0x1400a7fea  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7ff1  jz      short loc_1400A8009
0x1400a7ff3  mov     edx, 85h
0x1400a7ff8  mov     ecx, 306h
0x1400a7ffd  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a8004  call    WPP_SF_d
0x1400a8009  jmp     loc_1400A849C
0x1400a800e  mov     r8d, 4
0x1400a8014  jmp     short loc_1400A8055
0x1400a8016  cmp     dword ptr [rsp+148h+Address+4], 18h
0x1400a801b  jnb     short loc_1400A804F
0x1400a801d  mov     r9d, 0C000000Dh
0x1400a8023  mov     esi, r9d
0x1400a8026  mov     [rsp+148h+var_F0], r9d
0x1400a802b  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a8032  jz      short loc_1400A804A
0x1400a8034  mov     edx, 86h
0x1400a8039  mov     ecx, 306h
0x1400a803e  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a8045  call    WPP_SF_d
0x1400a804a  jmp     loc_1400A849C
0x1400a804f  mov     r8d, 8; Alignment
0x1400a8055  mov     r9b, r12b
0x1400a8058  mov     edx, dword ptr [rsp+148h+Address+4]; Length
0x1400a805c  mov     rcx, [rsp+148h+Address+8]; Address
0x1400a8061  call    UlProbeForRead
0x1400a8066  mov     [rsp+148h+var_F8], 1
0x1400a806b  mov     rax, [rsp+148h+Address+8]
0x1400a8070  mov     qword ptr [rsp+148h+var_78], rax
0x1400a8078  mov     ecx, [rsp+148h+var_D8]
0x1400a807c  inc     ecx
0x1400a807e  mov     [rsp+148h+var_D8], ecx
0x1400a8082  add     r15, 10h
0x1400a8086  mov     [rsp+148h+var_58], r15
0x1400a808e  movzx   r9d, [rsp+148h+var_F4]
0x1400a8094  jmp     loc_1400A7CBB
0x1400a8099  jmp     short loc_1400A80E0
0x1400a809b  mov     esi, eax
0x1400a809d  and     eax, 0C0000000h
0x1400a80a2  cmp     eax, 80000000h
  ... truncated ...
```
