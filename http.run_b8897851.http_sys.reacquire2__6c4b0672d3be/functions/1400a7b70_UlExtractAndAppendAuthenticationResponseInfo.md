# UlExtractAndAppendAuthenticationResponseInfo

- ea: `0x1400a7b70`
- end: `0x1400a84f4`
- name: `UlExtractAndAppendAuthenticationResponseInfo`
- size: `2436`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x14001aba0`
- `0x14001d270`
- `0x1400474f0`

## callees

- `0x140049be0`
- `0x140074420`
- `0x1400a7b70`
- `0x1400b1bac`
- `0x1400b46ac`
- `0x1400b581c`
- `0x1400cb024`
- `0x1400fb3d0`
- `0x140142d04`
- `0x140145ec4`
- `0x140146114`
- `0x140146654`
- `0x140146a98`
- `0x140146b48`
- `0x140167730`
- `0x140167b40`
- `0x1401c49c4`
- `0x1401d7ea8`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x1400a7c7b`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7cf8`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7d97`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7e9d`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7fe5`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7c7b`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7cf8`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7d97`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7e9d`
- `ntoskrnl!IoIs32bitProcess` at `0x1400a7fe5`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8268`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8415`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8268`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400a8415`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a818b`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a8347`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a818b`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1400a8347`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a8210`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a83be`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a8210`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400a83be`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a81c1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a8372`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a81c1`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1400a8372`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a81cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8274`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a837e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8421`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a81cd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8274`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a837e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400a8421`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8176`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a81fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8332`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a83ab`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8176`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a81fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a8332`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400a83ab`

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
0x1400a7b70  mov     rax, rsp
0x1400a7b73  mov     [rax+20h], r9b
0x1400a7b77  mov     [rax+18h], r8
0x1400a7b7b  mov     [rax+8], rcx
0x1400a7b7f  push    rbx
0x1400a7b80  push    rsi
0x1400a7b81  push    rdi
0x1400a7b82  push    r12
0x1400a7b84  push    r13
0x1400a7b86  push    r14
0x1400a7b88  push    r15
0x1400a7b8a  sub     rsp, 110h
0x1400a7b91  movsx   r12d, r9b
0x1400a7b95  mov     rbx, r8
0x1400a7b98  mov     r15, rdx
0x1400a7b9b  mov     r14, rcx
0x1400a7b9e  xorps   xmm0, xmm0
0x1400a7ba1  movups  xmmword ptr [rsp+148h+Address], xmm0
0x1400a7ba6  xor     edx, edx; Val
0x1400a7ba8  lea     r8d, [rdx+50h]; Size
0x1400a7bac  lea     rcx, [rax-0C8h]; void *
0x1400a7bb3  call    memset
0x1400a7bb8  xor     edi, edi
0x1400a7bba  mov     [rsp+148h+arg_8], dil
0x1400a7bc2  mov     [rsp+148h+var_F7], dil
0x1400a7bc7  mov     esi, edi
0x1400a7bc9  lea     rax, [r14+18h]
0x1400a7bcd  mov     [rsp+148h+var_48], rax
0x1400a7bd5  mov     rax, [rax]
0x1400a7bd8  mov     r13, [rax+448h]
0x1400a7bdf  mov     [rsp+148h+var_50], r13
0x1400a7be7  test    byte ptr cs:xmmword_1401A2CA0+1, 40h
0x1400a7bee  jz      short loc_1400A7C29
0x1400a7bf0  movzx   ecx, [rsp+148h+arg_20]
0x1400a7bf8  mov     rax, [rsp+148h+arg_28]
0x1400a7c00  mov     [rsp+148h+var_100], rax
0x1400a7c05  mov     [rsp+148h+var_108], ecx
0x1400a7c09  mov     [rsp+148h+var_110], r12d
0x1400a7c0e  mov     [rsp+148h+var_118], rbx
0x1400a7c13  mov     qword ptr [rsp+148h+var_120], r15
0x1400a7c18  mov     rax, [r14+40h]
0x1400a7c1c  mov     [rsp+148h+var_128], rax
0x1400a7c21  mov     r9, r14
0x1400a7c24  call    WPP_SF_qiqqllq
0x1400a7c29  mov     rax, [rsp+148h+arg_28]
0x1400a7c31  test    rax, rax
0x1400a7c34  jz      short loc_1400A7C39
0x1400a7c36  mov     [rax], dil
0x1400a7c39  test    r15, r15
0x1400a7c3c  jz      loc_1400A84BC
0x1400a7c42  mov     bl, dil
0x1400a7c45  mov     [rsp+148h+var_F6], bl
0x1400a7c49  mov     [rsp+148h+var_F8], dil
0x1400a7c4e  mov     qword ptr [rsp+148h+var_78], rdi
0x1400a7c56  movzx   eax, word ptr [r15+228h]
0x1400a7c5e  mov     [rsp+148h+var_F4], ax
0x1400a7c63  test    ax, ax
0x1400a7c66  jz      loc_1400A84BC
0x1400a7c6c  mov     r15, [r15+230h]
0x1400a7c73  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7c7b  call    cs:__imp_IoIs32bitProcess
0x1400a7c82  nop     dword ptr [rax+rax+00h]
0x1400a7c87  test    al, al
0x1400a7c89  jnz     short loc_1400A7CC7
0x1400a7c8b  movzx   r9d, [rsp+148h+var_F4]
0x1400a7c91  mov     edx, r9d
0x1400a7c94  shl     rdx, 4; Length
0x1400a7c98  mov     r8d, 8; Alignment
0x1400a7c9e  mov     rcx, r15; Address
0x1400a7ca1  cmp     cs:UxKirNewUma, al
0x1400a7ca7  jnz     short loc_1400A7CB3
0x1400a7ca9  mov     r9b, r12b
0x1400a7cac  call    UlProbeForRead
0x1400a7cb1  jmp     short loc_1400A7CC7
0x1400a7cb3  call    UxProbeAlignment
0x1400a7cb8  mov     esi, eax
0x1400a7cba  mov     [rsp+148h+var_F0], eax
0x1400a7cbe  test    eax, eax
0x1400a7cc0  jns     short loc_1400A7CCD
0x1400a7cc2  jmp     loc_1400A84BC
0x1400a7cc7  movzx   r9d, [rsp+148h+var_F4]
0x1400a7ccd  mov     ecx, edi
0x1400a7ccf  mov     [rsp+148h+var_D8], ecx
0x1400a7cd3  mov     [rsp+148h+var_58], r15
0x1400a7cdb  movzx   eax, r9w
0x1400a7cdf  cmp     ecx, eax
0x1400a7ce1  jnb     loc_1400A80B9
0x1400a7ce7  cmp     cs:UxKirNewUma, 0
0x1400a7cee  jz      short loc_1400A7D08
0x1400a7cf0  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7cf8  call    cs:__imp_IoIs32bitProcess
0x1400a7cff  nop     dword ptr [rax+rax+00h]
0x1400a7d04  test    al, al
0x1400a7d06  jz      short loc_1400A7D14
0x1400a7d08  movups  xmm0, xmmword ptr [r15]
0x1400a7d0c  movdqu  xmmword ptr [rsp+148h+Address], xmm0
0x1400a7d12  jmp     short loc_1400A7D33
0x1400a7d14  mov     r8d, 10h; Size
0x1400a7d1a  mov     rdx, r15; Src
0x1400a7d1d  lea     rcx, [rsp+148h+Address]; void *
0x1400a7d22  test    r12b, r12b
0x1400a7d25  jz      short loc_1400A7D2E
0x1400a7d27  call    RtlCopyFromUser
0x1400a7d2c  jmp     short loc_1400A7D33
0x1400a7d2e  call    RtlCopyVolatileMemory
0x1400a7d33  mov     rcx, [rsp+148h+Address]
0x1400a7d38  cmp     ecx, 4
0x1400a7d3b  jl      short loc_1400A7D6F
0x1400a7d3d  mov     r9d, 0C000000Dh
0x1400a7d43  mov     esi, r9d
0x1400a7d46  mov     [rsp+148h+var_F0], r9d
0x1400a7d4b  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7d52  jz      short loc_1400A7D6A
0x1400a7d54  mov     edx, 82h
0x1400a7d59  mov     ecx, 306h
0x1400a7d5e  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7d65  call    WPP_SF_d
0x1400a7d6a  jmp     loc_1400A84BC
0x1400a7d6f  lea     eax, [rcx-1]
0x1400a7d72  test    eax, 0FFFFFFFDh
0x1400a7d77  jz      short loc_1400A7D7E
0x1400a7d79  jmp     loc_1400A8098
0x1400a7d7e  cmp     ecx, 1
0x1400a7d81  jnz     loc_1400A7FC9
0x1400a7d87  test    bl, bl
0x1400a7d89  jnz     loc_1400A7FC9
0x1400a7d8f  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7d97  call    cs:__imp_IoIs32bitProcess
0x1400a7d9e  nop     dword ptr [rax+rax+00h]
0x1400a7da3  mov     ecx, dword ptr [rsp+148h+Address+4]
0x1400a7da7  test    al, al
0x1400a7da9  jz      short loc_1400A7E10
0x1400a7dab  cmp     ecx, 24h ; '$'
0x1400a7dae  jnb     short loc_1400A7DE2
0x1400a7db0  mov     r9d, 0C000000Dh
0x1400a7db6  mov     esi, r9d
0x1400a7db9  mov     [rsp+148h+var_F0], r9d
0x1400a7dbe  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7dc5  jz      short loc_1400A7DDD
0x1400a7dc7  mov     edx, 83h
0x1400a7dcc  mov     ecx, 306h
0x1400a7dd1  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7dd8  call    WPP_SF_d
0x1400a7ddd  jmp     loc_1400A84BC
0x1400a7de2  mov     rdx, rcx
0x1400a7de5  mov     r8d, 4
0x1400a7deb  cmp     cs:UxKirNewUma, 0
0x1400a7df2  jz      short loc_1400A7E59
0x1400a7df4  mov     rbx, [rsp+148h+Address+8]
0x1400a7df9  mov     rcx, rbx
0x1400a7dfc  call    UxProbeAlignment
0x1400a7e01  mov     esi, eax
0x1400a7e03  mov     [rsp+148h+var_F0], eax
0x1400a7e07  test    eax, eax
0x1400a7e09  jns     short loc_1400A7E88
0x1400a7e0b  jmp     loc_1400A84BC
0x1400a7e10  cmp     ecx, 40h ; '@'
0x1400a7e13  jnb     short loc_1400A7E47
0x1400a7e15  mov     r9d, 0C000000Dh
0x1400a7e1b  mov     esi, r9d
0x1400a7e1e  mov     [rsp+148h+var_F0], r9d
0x1400a7e23  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a7e2a  jz      short loc_1400A7E42
0x1400a7e2c  mov     edx, 84h
0x1400a7e31  mov     ecx, 306h
0x1400a7e36  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a7e3d  call    WPP_SF_d
0x1400a7e42  jmp     loc_1400A84BC
0x1400a7e47  mov     rdx, rcx; Length
0x1400a7e4a  mov     r8d, 8; Alignment
0x1400a7e50  cmp     cs:UxKirNewUma, 0
0x1400a7e57  jnz     short loc_1400A7E6D
0x1400a7e59  mov     r9b, r12b
0x1400a7e5c  mov     rcx, [rsp+148h+Address+8]; Address
0x1400a7e61  call    UlProbeForRead
0x1400a7e66  mov     rbx, [rsp+148h+Address+8]
0x1400a7e6b  jmp     short loc_1400A7E88
0x1400a7e6d  mov     rbx, [rsp+148h+Address+8]
0x1400a7e72  mov     rcx, rbx
0x1400a7e75  call    UxProbeAlignment
0x1400a7e7a  mov     esi, eax
0x1400a7e7c  mov     [rsp+148h+var_F0], eax
0x1400a7e80  test    eax, eax
0x1400a7e82  js      loc_1400A84BC
0x1400a7e88  cmp     cs:UxKirNewUma, 0
0x1400a7e8f  jnz     loc_1400A7F9A
0x1400a7e95  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7e9d  call    cs:__imp_IoIs32bitProcess
0x1400a7ea4  nop     dword ptr [rax+rax+00h]
0x1400a7ea9  mov     ecx, [rbx]
0x1400a7eab  mov     [rsp+148h+var_C8], ecx
0x1400a7eb2  test    al, al
0x1400a7eb4  mov     eax, [rbx+4]
0x1400a7eb7  mov     [rsp+148h+var_C4], eax
0x1400a7ebe  mov     al, [rbx+8]
0x1400a7ec1  mov     [rsp+148h+var_C0], al
0x1400a7ec8  mov     al, [rbx+9]
0x1400a7ecb  mov     [rsp+148h+var_BF], al
0x1400a7ed2  mov     al, [rbx+0Ah]
0x1400a7ed5  mov     [rsp+148h+var_BE], al
0x1400a7edc  mov     al, [rbx+0Bh]
0x1400a7edf  mov     [rsp+148h+var_BD], al
0x1400a7ee6  jz      short loc_1400A7F2F
0x1400a7ee8  mov     eax, [rbx+18h]
0x1400a7eeb  mov     [rsp+148h+var_A0], rax
0x1400a7ef3  movzx   eax, word ptr [rbx+14h]
0x1400a7ef7  mov     [rsp+148h+var_A8], ax
0x1400a7eff  mov     eax, [rbx+10h]
0x1400a7f02  mov     [rsp+148h+var_B0], rax
0x1400a7f0a  movzx   eax, word ptr [rbx+0Ch]
0x1400a7f0e  mov     [rsp+148h+var_B8], ax
0x1400a7f16  mov     eax, [rbx+20h]
0x1400a7f19  mov     [rsp+148h+var_90], rax
0x1400a7f21  movzx   eax, word ptr [rbx+1Ch]
0x1400a7f25  mov     [rsp+148h+var_98], ax
0x1400a7f2d  jmp     short loc_1400A7F83
0x1400a7f2f  mov     rax, [rbx+28h]
0x1400a7f33  mov     [rsp+148h+var_A0], rax
0x1400a7f3b  movzx   eax, word ptr [rbx+20h]
0x1400a7f3f  mov     [rsp+148h+var_A8], ax
0x1400a7f47  mov     rax, [rbx+18h]
0x1400a7f4b  mov     [rsp+148h+var_B0], rax
0x1400a7f53  movzx   eax, word ptr [rbx+10h]
0x1400a7f57  mov     [rsp+148h+var_B8], ax
0x1400a7f5f  mov     rax, [rbx+38h]
0x1400a7f63  mov     [rsp+148h+var_90], rax
0x1400a7f6b  movzx   eax, word ptr [rbx+30h]
0x1400a7f6f  mov     [rsp+148h+var_98], ax
0x1400a7f77  xorps   xmm0, xmm0
0x1400a7f7a  movdqa  [rsp+148h+var_88], xmm0
0x1400a7f83  xorps   xmm0, xmm0
0x1400a7f86  movdqa  [rsp+148h+var_88], xmm0
0x1400a7f8f  mov     bl, 1
0x1400a7f91  mov     [rsp+148h+var_F6], bl
0x1400a7f95  jmp     loc_1400A8098
0x1400a7f9a  lea     rax, [rsp+148h+var_C8]
0x1400a7fa2  mov     [rsp+148h+var_128], rax; void *
0x1400a7fa7  mov     r8b, r12b
0x1400a7faa  mov     rdx, [rsp+148h+Irp]; Irp
0x1400a7fb2  mov     rcx, rbx; Src
0x1400a7fb5  call    UlGetAuthInfoFromMode
0x1400a7fba  mov     esi, eax
0x1400a7fbc  mov     [rsp+148h+var_F0], eax
0x1400a7fc0  test    eax, eax
0x1400a7fc2  jns     short loc_1400A7F8F
0x1400a7fc4  jmp     loc_1400A84BC
0x1400a7fc9  cmp     ecx, 3
0x1400a7fcc  jnz     loc_1400A8098
0x1400a7fd2  cmp     [rsp+148h+var_F8], dil
0x1400a7fd7  jnz     loc_1400A8098
0x1400a7fdd  mov     rcx, [rsp+148h+Irp]; Irp
0x1400a7fe5  call    cs:__imp_IoIs32bitProcess
0x1400a7fec  nop     dword ptr [rax+rax+00h]
0x1400a7ff1  test    al, al
0x1400a7ff3  jz      short loc_1400A8036
0x1400a7ff5  cmp     dword ptr [rsp+148h+Address+4], 10h
0x1400a7ffa  jnb     short loc_1400A802E
0x1400a7ffc  mov     r9d, 0C000000Dh
0x1400a8002  mov     esi, r9d
0x1400a8005  mov     [rsp+148h+var_F0], r9d
0x1400a800a  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a8011  jz      short loc_1400A8029
0x1400a8013  mov     edx, 85h
0x1400a8018  mov     ecx, 306h
0x1400a801d  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a8024  call    WPP_SF_d
0x1400a8029  jmp     loc_1400A84BC
0x1400a802e  mov     r8d, 4
0x1400a8034  jmp     short loc_1400A8075
0x1400a8036  cmp     dword ptr [rsp+148h+Address+4], 18h
0x1400a803b  jnb     short loc_1400A806F
0x1400a803d  mov     r9d, 0C000000Dh
0x1400a8043  mov     esi, r9d
0x1400a8046  mov     [rsp+148h+var_F0], r9d
0x1400a804b  test    byte ptr cs:xmmword_1401A2C90+8, 40h
0x1400a8052  jz      short loc_1400A806A
0x1400a8054  mov     edx, 86h
0x1400a8059  mov     ecx, 306h
0x1400a805e  lea     r8, WPP_3bc569ebedc33674d1577199996181a5_Traceguids
0x1400a8065  call    WPP_SF_d
0x1400a806a  jmp     loc_1400A84BC
0x1400a806f  mov     r8d, 8; Alignment
0x1400a8075  mov     r9b, r12b
0x1400a8078  mov     edx, dword ptr [rsp+148h+Address+4]; Length
0x1400a807c  mov     rcx, [rsp+148h+Address+8]; Address
0x1400a8081  call    UlProbeForRead
0x1400a8086  mov     [rsp+148h+var_F8], 1
0x1400a808b  mov     rax, [rsp+148h+Address+8]
0x1400a8090  mov     qword ptr [rsp+148h+var_78], rax
0x1400a8098  mov     ecx, [rsp+148h+var_D8]
0x1400a809c  inc     ecx
0x1400a809e  mov     [rsp+148h+var_D8], ecx
0x1400a80a2  add     r15, 10h
0x1400a80a6  mov     [rsp+148h+var_58], r15
0x1400a80ae  movzx   r9d, [rsp+148h+var_F4]
0x1400a80b4  jmp     loc_1400A7CDB
0x1400a80b9  jmp     short loc_1400A8100
0x1400a80bb  mov     esi, eax
0x1400a80bd  and     eax, 0C0000000h
0x1400a80c2  cmp     eax, 80000000h
  ... truncated ...
```
