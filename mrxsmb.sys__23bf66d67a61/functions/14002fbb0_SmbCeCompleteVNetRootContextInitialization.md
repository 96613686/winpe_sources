# SmbCeCompleteVNetRootContextInitialization

- ea: `0x14002fbb0`
- end: `0x1400302dd`
- name: `SmbCeCompleteVNetRootContextInitialization`
- size: `1837`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140005320`
- `0x1400093a0`
- `0x14002fbb0`
- `0x14003e14c`
- `0x1400472c4`
- `0x140047878`
- `0x140047cbc`
- `0x140047d78`
- `0x140047e34`
- `0x140059ea0`
- `0x140084a28`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14002fde9`
- `ntoskrnl!KeBugCheckEx` at `0x14002fde9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140030052`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140030052`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002fc2c`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002fc2c`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002fc3e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002fc3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400302a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400302a4`
- `rdbss!RxNameCacheExpireEntriesWithPrefix` at `0x140030275`
- `rdbss!RxNameCacheExpireEntriesWithPrefix` at `0x140030275`

## pseudocode

```c
void __fastcall SmbCeCompleteVNetRootContextInitialization(_QWORD *P)
{
  __int64 v1; // r13
  _DWORD *v2; // r14
  int v3; // edi
  int v4; // esi
  int *v5; // rbx
  __int128 v6; // xmm7
  __int64 v7; // r12
  __int128 v8; // xmm8
  __int128 v9; // xmm9
  __int64 v10; // rax
  int **v11; // rdx
  int v12; // r8d
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 v15; // r8
  int *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // r14
  int v19; // edi
  __int64 v20; // rax
  int v21; // r12d
  char v22; // al
  int v23; // r8d
  int v24; // ecx
  char v25; // r10
  __int64 v26; // r11
  __int64 *v27; // rdx
  int v28; // edi
  __int64 v29; // rax
  int v30; // r12d
  char IsTrafficCompressionRequestedVNetRootContext; // al
  char v32; // r10
  __int64 v33; // r11
  __int64 v34; // rax
  __int64 v35; // xmm6_8
  __int64 v36; // rdx
  __int64 v37; // r12
  __int64 v38; // rdx
  __int64 v39; // r8
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  int v42; // r15d
  __int64 v43; // rax
  const char *v44; // rsi
  const char *v45; // rdi
  const char *v46; // rbx
  const char *v47; // r11
  const char *v48; // rdx
  __int64 v49; // r14
  char *v50; // rax
  __int64 v51; // rcx
  int v52; // eax
  char BugCheckParameter4; // [rsp+20h] [rbp-E0h]
  __int16 v54; // [rsp+30h] [rbp-D0h]
  __int64 v55; // [rsp+38h] [rbp-C8h]
  int v56; // [rsp+40h] [rbp-C0h]
  __int64 v57; // [rsp+48h] [rbp-B8h]
  char v58; // [rsp+50h] [rbp-B0h]
  char v59; // [rsp+58h] [rbp-A8h]
  char v60; // [rsp+60h] [rbp-A0h]
  char v61; // [rsp+68h] [rbp-98h]
  char v62; // [rsp+70h] [rbp-90h]
  __int128 v63; // [rsp+80h] [rbp-80h] BYREF
  __int64 v64; // [rsp+90h] [rbp-70h]
  PVOID pContext[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-50h]
  _OWORD v67[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v68; // [rsp+F0h] [rbp-10h]
  KIRQL v70; // [rsp+198h] [rbp+98h]
  int v71; // [rsp+1A0h] [rbp+A0h]
  __int64 v72; // [rsp+1A8h] [rbp+A8h]

  v1 = P[3];
  v2 = P;
  v3 = *((_DWORD *)P + 2);
  v4 = 0;
  LOBYTE(v5) = 0;
  v6 = 0;
  v7 = *(_QWORD *)(v1 + 24);
  v8 = 0;
  v68 = 0;
  v9 = 0;
  v10 = P[2];
  v64 = 0;
  pContext[0] = 0;
  v71 = v3;
  v66 = v10;
  v72 = v7;
  v70 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v7 + 1920));
  *(_DWORD *)(v7 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( v3 < 0 )
    goto LABEL_46;
  v13 = *(_QWORD *)(v1 + 416);
  if ( (unsigned int)(*(_DWORD *)(v13 + 12) - 1) <= 2 )
  {
    v3 = -1073741309;
    v71 = -1073741309;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_50;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
        v13,
        -1073741309);
LABEL_46:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qLZ(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v11, v12, v1, v3, *(_QWORD *)(v1 + 424) + 96LL);
    }
    goto LABEL_50;
  }
  v14 = *(unsigned __int16 *)(v13 + 2);
  if ( (_WORD)v14 )
  {
    v15 = v13 + v14 + 8;
    if ( !v15 )
      goto LABEL_41;
  }
  else
  {
    v15 = 8;
  }
  v16 = *(int **)v15;
  if ( !*(_QWORD *)v15 || (v17 = *(_QWORD **)(v15 + 8)) == 0 || *((_QWORD *)v16 + 1) != v15 || *v17 != v15 )
LABEL_41:
    __fastfail(3u);
  v5 = 0;
  if ( v16 != (int *)v15 )
  {
    while ( v16 )
    {
      if ( !*(_QWORD *)v16 )
        break;
      v11 = (int **)*((_QWORD *)v16 + 1);
      if ( !v11 || *(int **)(*(_QWORD *)v16 + 8LL) != v16 || *v11 != v16 )
        break;
      v5 = v16 - 100;
      if ( *(v16 - 98) < 0 )
        KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v16 - 100), *(v16 - 98), 0);
      if ( *(_WORD *)v5 == 0xE2FF )
      {
        v16 = *(int **)v16;
        v5 = 0;
        if ( v16 != (int *)v15 )
          continue;
      }
      goto LABEL_19;
    }
    goto LABEL_41;
  }
LABEL_19:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qDZ(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v11, v15, v1, v3, *(_QWORD *)(v1 + 424) + 96LL);
  }
  if ( v5 )
  {
    v4 = 16;
    if ( *(_BYTE *)(*((_QWORD *)v5 + 49) + 325LL) )
      v4 = 28;
  }
  if ( *(_DWORD *)(v1 + 264) <= 1u )
  {
    if ( (byte_1400712C2 & 2) == 0 )
      goto LABEL_39;
    v18 = *(_QWORD *)(v1 + 416);
    v28 = (*(_DWORD *)(v18 + 4) >> 2) & 1;
    if ( v5 )
    {
      v29 = *((_QWORD *)v5 + 49);
      v30 = *(_DWORD *)(v29 + 320);
      *(_QWORD *)&v63 = v29 + 428;
    }
    else
    {
      LOBYTE(v30) = 0;
      *(_QWORD *)&v63 = 0;
    }
    IsTrafficCompressionRequestedVNetRootContext = Smb2IsTrafficCompressionRequestedVNetRootContext(
                                                     v1,
                                                     *(unsigned __int8 *)(v72 + 1312));
    v24 = *(unsigned __int8 *)(v18 + 464);
    v62 = v32;
    v61 = IsTrafficCompressionRequestedVNetRootContext;
    v60 = v28;
    v59 = *(_BYTE *)(v18 + 464);
    v58 = v30;
    v57 = v63;
    v56 = v4;
    v55 = *(_QWORD *)(v33 + 104);
    v54 = *(_WORD *)(v33 + 96) >> 1;
    v27 = ShareInitialConnectionEstablished;
  }
  else
  {
    if ( (byte_1400712C2 & 2) == 0 )
      goto LABEL_39;
    v18 = *(_QWORD *)(v1 + 416);
    v19 = (*(_DWORD *)(v18 + 4) >> 2) & 1;
    if ( v5 )
    {
      v20 = *((_QWORD *)v5 + 49);
      v21 = *(_DWORD *)(v20 + 320);
      *(_QWORD *)&v63 = v20 + 428;
    }
    else
    {
      LOBYTE(v21) = 0;
      *(_QWORD *)&v63 = 0;
    }
    v22 = Smb2IsTrafficCompressionRequestedVNetRootContext(v1, *(unsigned __int8 *)(v72 + 1312));
    v24 = *(unsigned __int8 *)(v18 + 464);
    v62 = v25;
    v61 = v22;
    v60 = v19;
    v59 = *(_BYTE *)(v18 + 464);
    v58 = v21;
    v57 = v63;
    v56 = v4;
    v55 = *(_QWORD *)(v26 + 104);
    v54 = *(_WORD *)(v26 + 96) >> 1;
    v27 = ShareConnectionEstablishedV4;
  }
  v3 = v71;
  McTemplateK0qxqhzr3qbr5qtttt_EtwWriteTransfer(
    v24,
    (_DWORD)v27,
    v23,
    v71,
    *(_QWORD *)(v18 + 440),
    *(_DWORD *)(v1 + 436),
    v54,
    v55,
    v56,
    v57,
    v58,
    v59,
    v60,
    v61,
    v62);
  v7 = v72;
  v2 = P;
LABEL_39:
  if ( v5 )
  {
    v34 = *((_QWORD *)v5 + 49);
    LOBYTE(v5) = 1;
    v6 = *(_OWORD *)(v34 + 400);
    v8 = *(_OWORD *)(v34 + 416);
    v9 = *(_OWORD *)(v34 + 432);
    v35 = *(_QWORD *)(v34 + 448);
    goto LABEL_51;
  }
LABEL_50:
  v35 = v68;
LABEL_51:
  HIDWORD(v64) = v2[3];
  LODWORD(v64) = v3;
  v36 = v64;
  *(_QWORD *)(v1 + 336) = SmbCePrepareNonMitigatedExchangeForRestart;
  SmbCeCompleteObjectConstructionLite(v1, v36, pContext);
  *(_DWORD *)(v7 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v7 + 1920), v70);
  if ( pContext[0] )
    SmbCeDereferenceExchange(pContext[0]);
  if ( v3 >= 0 )
  {
    v37 = *(_QWORD *)(v1 + 424);
    if ( (*(_DWORD *)(v37 + 176) & 0x40) != 0 )
    {
      v38 = *(_QWORD *)(v37 + 88);
      if ( !*(_WORD *)(v38 + 740) )
        *(_WORD *)(v38 + 740) = *(_WORD *)(*(_QWORD *)(v38 + 64) + 8LL);
    }
    if ( !WitnessUpcallInitialized
      || !(_BYTE)v5
      || (*(_BYTE *)(v37 + 176) & 0xC0) != 0xC0
      || *(PRDBSS_DEVICE_OBJECT *)(v1 + 24) != MRxSmbDeviceObject )
    {
      goto LABEL_66;
    }
    v39 = *(_QWORD *)(v37 + 88);
    if ( (*(_BYTE *)(v39 + 737) & 0x20) != 0 )
    {
      BugCheckParameter4 = 1;
    }
    else
    {
      if ( (*(_DWORD *)(v37 + 176) & 0x200) != 0 )
      {
LABEL_66:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v42 = *(_DWORD *)(v37 + 176);
          v43 = *(_QWORD *)(v37 + 88);
          v44 = "SyncRedirect";
          v45 = "Asymmetric";
          v46 = "Scaleout";
          v47 = "Cluster";
          v48 = "CA";
          v49 = *(_BYTE *)(v43 + 737) & 3;
          if ( !*(_BYTE *)(v37 + 189) )
            v44 = "-";
          v50 = off_140061BC8[((unsigned __int64)*(unsigned __int8 *)(v43 + 737) >> 2) & 3];
          if ( (v42 & 0x200) == 0 )
            v45 = "-";
          if ( (v42 & 0x100) == 0 )
            v46 = "-";
          if ( (v42 & 0x40) == 0 )
            v47 = "-";
          if ( (v42 & 0x80u) == 0 )
            v48 = "-";
          WPP_SF_qZDDDsssssss(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v48,
            *(unsigned __int8 *)(v37 + 188),
            v37,
            v37 + 96,
            *(_BYTE *)(v37 + 188),
            *(_DWORD *)(v37 + 180),
            v42,
            (__int64)v48,
            (__int64)v47,
            (__int64)v46,
            (__int64)v45,
            (__int64)v44,
            (__int64)off_140061BC8[v49],
            (__int64)v50);
          v3 = v71;
          v2 = P;
        }
        goto LABEL_80;
      }
      BugCheckParameter4 = 0;
    }
    v40 = *(_OWORD *)(v37 + 96);
    v67[0] = v6;
    *(_OWORD *)pContext = v40;
    v41 = *(_OWORD *)(v39 + 80);
    v67[1] = v8;
    v63 = v41;
    v67[2] = v9;
    v68 = v35;
    WitnessInitiateClusterConnect(
      (unsigned int)&v63,
      (unsigned int)pContext,
      v39 + 656,
      (unsigned int)v67,
      BugCheckParameter4);
    goto LABEL_66;
  }
LABEL_80:
  _InterlockedIncrement64((volatile signed __int64 *)(v1 + 576));
  RxNameCacheExpireEntriesWithPrefix(*(_QWORD *)(v1 + 424) + 1112LL, &qword_140070108);
  v51 = v66;
  if ( v66 )
  {
    v52 = v2[3];
    *(_DWORD *)(v66 + 8) = v3;
    *(_DWORD *)(v51 + 12) = v52;
    (*(void (**)(void))v51)();
  }
  ExFreePoolWithTag(v2, 0x6D536243u);
}

```

## disassembly

```asm
0x14002fbb0  mov     rax, rsp
0x14002fbb3  mov     [rax+8], rcx
0x14002fbb7  push    rbp
0x14002fbb8  push    rbx
0x14002fbb9  push    rsi
0x14002fbba  push    rdi
0x14002fbbb  push    r12
0x14002fbbd  push    r13
0x14002fbbf  push    r14
0x14002fbc1  push    r15
0x14002fbc3  lea     rbp, [rsp-48h]
0x14002fbc8  sub     rsp, 148h
0x14002fbcf  mov     r13, [rcx+18h]
0x14002fbd3  mov     r14, rcx
0x14002fbd6  mov     edi, [rcx+8]
0x14002fbd9  xor     esi, esi
0x14002fbdb  movaps  xmmword ptr [rax-58h], xmm6
0x14002fbdf  xor     bl, bl
0x14002fbe1  movaps  xmmword ptr [rax-68h], xmm7
0x14002fbe5  xorps   xmm7, xmm7
0x14002fbe8  mov     r12, [r13+18h]
0x14002fbec  movaps  xmmword ptr [rax-78h], xmm8
0x14002fbf1  xorps   xmm8, xmm8
0x14002fbf5  movaps  xmmword ptr [rax-88h], xmm9
0x14002fbfd  xor     eax, eax
0x14002fbff  mov     [rbp+80h+var_90], rax
0x14002fc03  xorps   xmm9, xmm9
0x14002fc07  mov     rax, [rcx+10h]
0x14002fc0b  lea     rcx, [r12+780h]; SpinLock
0x14002fc13  mov     [rbp+80h+var_F0], rsi
0x14002fc17  mov     [rbp+80h+pContext], rsi
0x14002fc1b  mov     [rbp+80h+arg_10], edi
0x14002fc21  mov     [rbp+80h+var_D0], rax
0x14002fc25  mov     [rbp+80h+arg_18], r12
0x14002fc2c  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002fc33  nop     dword ptr [rax+rax+00h]
0x14002fc38  mov     byte ptr [rbp+80h+arg_8], al
0x14002fc3e  call    cs:__imp_PsGetCurrentThreadId
0x14002fc45  nop     dword ptr [rax+rax+00h]
0x14002fc4a  mov     [r12+930h], eax
0x14002fc52  lea     r15, WPP_GLOBAL_Control
0x14002fc59  test    edi, edi
0x14002fc5b  js      loc_14002FFD1
0x14002fc61  mov     r9, [r13+1A0h]
0x14002fc68  mov     ecx, [r9+0Ch]
0x14002fc6c  dec     ecx
0x14002fc6e  cmp     ecx, 2
0x14002fc71  jbe     loc_14002FF90
0x14002fc77  movzx   eax, word ptr [r9+2]
0x14002fc7c  test    ax, ax
0x14002fc7f  jnz     short loc_14002FC89
0x14002fc81  mov     r8d, 8
0x14002fc87  jmp     short loc_14002FC96
0x14002fc89  lea     r8, [rax+8]
0x14002fc8d  add     r8, r9
0x14002fc90  jz      loc_14002FF89
0x14002fc96  mov     rax, [r8]
0x14002fc99  test    rax, rax
0x14002fc9c  jz      loc_14002FF89
0x14002fca2  mov     rcx, [r8+8]
0x14002fca6  test    rcx, rcx
0x14002fca9  jz      loc_14002FF89
0x14002fcaf  cmp     [rax+8], r8
0x14002fcb3  jnz     loc_14002FF89
0x14002fcb9  cmp     [rcx], r8
0x14002fcbc  jnz     loc_14002FF89
0x14002fcc2  mov     rbx, rsi
0x14002fcc5  cmp     rax, r8
0x14002fcc8  jz      short loc_14002FD29
0x14002fcca  mov     r9d, 0E2FFh
0x14002fcd0  test    rax, rax
0x14002fcd3  jz      loc_14002FF89
0x14002fcd9  mov     rcx, [rax]
0x14002fcdc  test    rcx, rcx
0x14002fcdf  jz      loc_14002FF89
0x14002fce5  mov     rdx, [rax+8]
0x14002fce9  test    rdx, rdx
0x14002fcec  jz      loc_14002FF89
0x14002fcf2  cmp     [rcx+8], rax
0x14002fcf6  jnz     loc_14002FF89
0x14002fcfc  cmp     [rdx], rax
0x14002fcff  jnz     loc_14002FF89
0x14002fd05  lea     rbx, [rax-190h]
0x14002fd0c  movsxd  rcx, dword ptr [rbx+8]
0x14002fd10  test    ecx, ecx
0x14002fd12  js      loc_14002FDD4
0x14002fd18  cmp     [rbx], r9w
0x14002fd1c  jnz     short loc_14002FD29
0x14002fd1e  mov     rax, [rax]
0x14002fd21  mov     rbx, rsi
0x14002fd24  cmp     rax, r8
0x14002fd27  jnz     short loc_14002FCD0
0x14002fd29  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fd30  lea     r15, WPP_GLOBAL_Control
0x14002fd37  cmp     rcx, r15
0x14002fd3a  jz      short loc_14002FD69
0x14002fd3c  mov     eax, [rcx+2Ch]
0x14002fd3f  test    al, 40h
0x14002fd41  jz      short loc_14002FD69
0x14002fd43  cmp     byte ptr [rcx+29h], 2
0x14002fd47  jb      short loc_14002FD69
0x14002fd49  mov     rax, [r13+1A8h]
0x14002fd50  mov     r9, r13
0x14002fd53  mov     rcx, [rcx+18h]
0x14002fd57  add     rax, 60h ; '`'
0x14002fd5b  mov     [rsp+180h+var_158], rax
0x14002fd60  mov     dword ptr [rsp+180h+BugCheckParameter4], edi
0x14002fd64  call    WPP_SF_qDZ
0x14002fd69  test    rbx, rbx
0x14002fd6c  jz      short loc_14002FD89
0x14002fd6e  mov     rax, [rbx+188h]
0x14002fd75  mov     esi, 10h
0x14002fd7a  mov     ecx, 1Ch
0x14002fd7f  cmp     byte ptr [rax+145h], 0
0x14002fd86  cmovnz  esi, ecx
0x14002fd89  cmp     dword ptr [r13+108h], 1
0x14002fd91  jbe     loc_14002FE6F
0x14002fd97  test    cs:byte_1400712C2, 2
0x14002fd9e  jz      loc_14002FF53
0x14002fda4  mov     r14, [r13+1A0h]
0x14002fdab  mov     edi, [r14+4]
0x14002fdaf  shr     edi, 2
0x14002fdb2  and     edi, 1
0x14002fdb5  test    rbx, rbx
0x14002fdb8  jz      short loc_14002FDF6
0x14002fdba  mov     rax, [rbx+188h]
0x14002fdc1  mov     r12d, [rax+140h]
0x14002fdc8  add     rax, 1ACh
0x14002fdce  mov     qword ptr [rbp+80h+var_100], rax
0x14002fdd2  jmp     short loc_14002FDFD
0x14002fdd4  mov     r9, rcx; BugCheckParameter3
0x14002fdd7  mov     [rsp+180h+BugCheckParameter4], rsi; BugCheckParameter4
0x14002fddc  mov     ecx, 27h ; '''; BugCheckCode
0x14002fde1  mov     r8, rbx; BugCheckParameter2
0x14002fde4  mov     edx, 0A0001h; BugCheckParameter1
0x14002fde9  call    cs:__imp_KeBugCheckEx
0x14002fdf6  xor     r12d, r12d
0x14002fdf9  mov     qword ptr [rbp+80h+var_100], r12
0x14002fdfd  mov     rdx, [rbp+80h+arg_18]
0x14002fe04  mov     rcx, r13
0x14002fe07  mov     r11, [r13+1A8h]
0x14002fe0e  movzx   r10d, byte ptr [r14+290h]
0x14002fe16  movzx   edx, byte ptr [rdx+520h]
0x14002fe1d  call    Smb2IsTrafficCompressionRequestedVNetRootContext
0x14002fe22  movzx   edx, word ptr [r11+60h]
0x14002fe27  movzx   ecx, byte ptr [r14+1D0h]
0x14002fe2f  mov     dword ptr [rsp+180h+var_110], r10d
0x14002fe34  mov     dword ptr [rsp+180h+var_118], eax
0x14002fe38  mov     rax, qword ptr [rbp+80h+var_100]
0x14002fe3c  mov     dword ptr [rsp+180h+var_120], edi
0x14002fe40  mov     dword ptr [rsp+180h+var_128], ecx
0x14002fe44  mov     dword ptr [rsp+180h+var_130], r12d
0x14002fe49  mov     [rsp+180h+var_138], rax
0x14002fe4e  mov     rax, [r11+68h]
0x14002fe52  shr     dx, 1
0x14002fe55  mov     dword ptr [rsp+180h+var_140], esi
0x14002fe59  mov     [rsp+180h+var_148], rax
0x14002fe5e  mov     [rsp+180h+var_150], dx
0x14002fe63  lea     rdx, ShareConnectionEstablishedV4
0x14002fe6a  jmp     loc_14002FF20
0x14002fe6f  test    cs:byte_1400712C2, 2
0x14002fe76  jz      loc_14002FF53
0x14002fe7c  mov     r14, [r13+1A0h]
0x14002fe83  mov     edi, [r14+4]
0x14002fe87  shr     edi, 2
0x14002fe8a  and     edi, 1
0x14002fe8d  test    rbx, rbx
0x14002fe90  jz      short loc_14002FEAC
0x14002fe92  mov     rax, [rbx+188h]
0x14002fe99  mov     r12d, [rax+140h]
0x14002fea0  add     rax, 1ACh
0x14002fea6  mov     qword ptr [rbp+80h+var_100], rax
0x14002feaa  jmp     short loc_14002FEB3
0x14002feac  xor     r12d, r12d
0x14002feaf  mov     qword ptr [rbp+80h+var_100], r12
0x14002feb3  mov     rdx, [rbp+80h+arg_18]
0x14002feba  mov     rcx, r13
0x14002febd  mov     r11, [r13+1A8h]
0x14002fec4  movzx   r10d, byte ptr [r14+290h]
0x14002fecc  movzx   edx, byte ptr [rdx+520h]
0x14002fed3  call    Smb2IsTrafficCompressionRequestedVNetRootContext
0x14002fed8  movzx   edx, word ptr [r11+60h]
0x14002fedd  movzx   ecx, byte ptr [r14+1D0h]
0x14002fee5  mov     dword ptr [rsp+180h+var_110], r10d
0x14002feea  mov     dword ptr [rsp+180h+var_118], eax
0x14002feee  mov     rax, qword ptr [rbp+80h+var_100]
0x14002fef2  mov     dword ptr [rsp+180h+var_120], edi
0x14002fef6  mov     dword ptr [rsp+180h+var_128], ecx
0x14002fefa  mov     dword ptr [rsp+180h+var_130], r12d
0x14002feff  mov     [rsp+180h+var_138], rax
0x14002ff04  mov     rax, [r11+68h]
0x14002ff08  shr     dx, 1
0x14002ff0b  mov     dword ptr [rsp+180h+var_140], esi
0x14002ff0f  mov     [rsp+180h+var_148], rax
0x14002ff14  mov     [rsp+180h+var_150], dx
0x14002ff19  lea     rdx, ShareInitialConnectionEstablished
0x14002ff20  mov     eax, [r13+1B4h]
0x14002ff27  mov     edi, [rbp+80h+arg_10]
0x14002ff2d  mov     r9d, edi
0x14002ff30  mov     dword ptr [rsp+180h+var_158], eax
0x14002ff34  mov     rax, [r14+1B8h]
0x14002ff3b  mov     [rsp+180h+BugCheckParameter4], rax
0x14002ff40  call    McTemplateK0qxqhzr3qbr5qtttt_EtwWriteTransfer
0x14002ff45  mov     r12, [rbp+80h+arg_18]
0x14002ff4c  mov     r14, [rbp+80h+arg_0]
0x14002ff53  test    rbx, rbx
0x14002ff56  jz      loc_14003000A
0x14002ff5c  mov     rax, [rbx+188h]
0x14002ff63  mov     bl, 1
0x14002ff65  movups  xmm7, xmmword ptr [rax+190h]
0x14002ff6c  movups  xmm8, xmmword ptr [rax+1A0h]
0x14002ff74  movups  xmm9, xmmword ptr [rax+1B0h]
0x14002ff7c  movsd   xmm6, qword ptr [rax+1C0h]
0x14002ff84  jmp     loc_14003000F
0x14002ff89  mov     ecx, 3
0x14002ff8e  int     29h; Win8: RtlFailFast(ecx)
0x14002ff90  mov     edi, 0C0000203h
0x14002ff95  mov     [rbp+80h+arg_10], edi
0x14002ff9b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ffa2  cmp     rcx, r15
0x14002ffa5  jz      short loc_14003000A
0x14002ffa7  mov     eax, [rcx+2Ch]
0x14002ffaa  test    al, 1
0x14002ffac  jz      short loc_14002FFD1
0x14002ffae  cmp     byte ptr [rcx+29h], 1
0x14002ffb2  jb      short loc_14002FFD1
0x14002ffb4  mov     rcx, [rcx+18h]
0x14002ffb8  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14002ffbf  mov     edx, 25h ; '%'
0x14002ffc4  mov     dword ptr [rsp+180h+BugCheckParameter4], 0C0000203h
0x14002ffcc  call    WPP_SF_qD
0x14002ffd1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ffd8  cmp     rcx, r15
0x14002ffdb  jz      short loc_14003000A
0x14002ffdd  mov     eax, [rcx+2Ch]
0x14002ffe0  test    al, 1
0x14002ffe2  jz      short loc_14003000A
0x14002ffe4  cmp     byte ptr [rcx+29h], 1
0x14002ffe8  jb      short loc_14003000A
0x14002ffea  mov     rax, [r13+1A8h]
0x14002fff1  mov     r9, r13
0x14002fff4  mov     rcx, [rcx+18h]
0x14002fff8  add     rax, 60h ; '`'
0x14002fffc  mov     [rsp+180h+var_158], rax
0x140030001  mov     dword ptr [rsp+180h+BugCheckParameter4], edi
0x140030005  call    WPP_SF_qLZ
0x14003000a  movsd   xmm6, [rbp+80h+var_90]
0x14003000f  mov     eax, [r14+0Ch]
0x140030013  lea     r8, [rbp+80h+pContext]
0x140030017  mov     dword ptr [rbp+80h+var_F0+4], eax
0x14003001a  mov     rcx, r13
0x14003001d  lea     rax, SmbCePrepareNonMitigatedExchangeForRestart
0x140030024  mov     dword ptr [rbp+80h+var_F0], edi
0x140030027  mov     rdx, [rbp+80h+var_F0]
0x14003002b  mov     [r13+150h], rax
0x140030032  call    SmbCeCompleteObjectConstructionLite
0x140030037  movzx   edx, byte ptr [rbp+80h+arg_8]; OldIrql
0x14003003e  lea     rcx, [r12+780h]; SpinLock
0x140030046  mov     dword ptr [r12+930h], 0FFFFFFFFh
0x140030052  call    cs:__imp_ExReleaseSpinLockExclusive
0x140030059  nop     dword ptr [rax+rax+00h]
0x14003005e  mov     rcx, [rbp+80h+pContext]; pContext
0x140030062  test    rcx, rcx
0x140030065  jz      short loc_14003006C
0x140030067  call    SmbCeDereferenceExchange
0x14003006c  test    edi, edi
0x14003006e  js      loc_140030258
0x140030074  mov     r12, [r13+1A8h]
0x14003007b  mov     eax, [r12+0B0h]
0x140030083  test    al, 40h
0x140030085  jz      short loc_1400300A5
0x140030087  mov     rdx, [r12+58h]
0x14003008c  cmp     word ptr [rdx+2E4h], 0
0x140030094  jnz     short loc_1400300A5
0x140030096  mov     rax, [rdx+40h]
0x14003009a  movzx   ecx, word ptr [rax+8]
0x14003009e  mov     [rdx+2E4h], cx
0x1400300a5  cmp     cs:WitnessUpcallInitialized, 0
0x1400300ac  jz      loc_140030135
0x1400300b2  test    bl, bl
0x1400300b4  jz      short loc_140030135
0x1400300b6  mov     ecx, [r12+0B0h]
0x1400300be  mov     eax, ecx
0x1400300c0  and     eax, 0C0h
0x1400300c5  cmp     al, 0C0h
0x1400300c7  jnz     short loc_140030135
0x1400300c9  mov     rax, cs:MRxSmbDeviceObject
0x1400300d0  cmp     [r13+18h], rax
0x1400300d4  jnz     short loc_140030135
0x1400300d6  mov     r8, [r12+58h]
0x1400300db  test    byte ptr [r8+2E1h], 20h
0x1400300e3  jz      short loc_1400300EC
0x1400300e5  mov     byte ptr [rsp+180h+BugCheckParameter4], 1
0x1400300ea  jmp     short loc_1400300F7
0x1400300ec  bt      ecx, 9
0x1400300f0  jb      short loc_140030135
0x1400300f2  mov     byte ptr [rsp+180h+BugCheckParameter4], 0
0x1400300f7  movups  xmm0, xmmword ptr [r12+60h]
0x1400300fd  lea     r9, [rbp+80h+var_C0]
0x140030101  lea     rdx, [rbp+80h+pContext]
  ... truncated ...
```
