# CscUpdateAndCaptureConnectionStateEx

- ea: `0x140003a00`
- end: `0x1400043ae`
- name: `CscUpdateAndCaptureConnectionStateEx`
- size: `2478`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64, char)`
- caller_count: `43`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140001980`
- `0x140001b14`
- `0x140001cd0`
- `0x140001ed0`
- `0x140002680`
- `0x140003550`
- `0x140003690`
- `0x1400038e0`
- `0x140004a30`
- `0x140008350`
- `0x14000fd40`
- `0x140017ac0`
- `0x140019bbc`
- `0x14001b960`
- `0x14001e178`
- `0x14001ea30`
- `0x14004b610`
- `0x14004cd10`
- `0x14004cf58`
- `0x14004d450`
- `0x1400504b0`
- `0x1400518a0`
- `0x140051a50`
- `0x140062b70`
- `0x14006e380`
- `0x14006e884`
- `0x140070040`
- `0x140070c70`
- `0x140074330`
- `0x1400770e0`
- `0x14007a9d0`
- `0x14007e150`
- `0x14007f960`
- `0x14007fc40`
- `0x140081120`
- `0x140083570`
- `0x1400837e0`
- `0x140085c80`
- `0x1400869e0`
- `0x1400874b0`
- `0x14008bb70`
- `0x14008caec`
- `0x14008ee80`

## callees

- `0x140003a00`
- `0x1400169d4`
- `0x140017cfc`
- `0x1400184ac`
- `0x140020744`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003e45`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140003e45`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004185`
- `ntoskrnl!ExAcquireFastMutex` at `0x140004185`
- `ntoskrnl!KeAreApcsDisabled` at `0x140003b79`
- `ntoskrnl!KeAreApcsDisabled` at `0x140003b79`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400041b6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400041b6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003b91`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140003b91`
- `rdbss!RxQueryNetRootCachingMode` at `0x140003bb4`
- `rdbss!RxQueryNetRootCachingMode` at `0x140003bb4`

## pseudocode

```c
__int64 __fastcall CscUpdateAndCaptureConnectionStateEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 a4,
        __int64 a5,
        char a6)
{
  int v6; // r13d
  int v7; // r9d
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  char v13; // al
  char v14; // dl
  char v15; // al
  char v16; // dl
  char v17; // dl
  char v18; // cl
  __int64 v19; // r15
  __int64 v20; // r15
  BOOLEAN v21; // al
  struct _FAST_MUTEX *v22; // rcx
  char v23; // al
  unsigned int NetRootCachingMode; // eax
  int v25; // edx
  char v26; // cl
  char v27; // r8
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  bool v31; // zf
  char v32; // al
  char v33; // dl
  __int64 v34; // rax
  __int64 v35; // r9
  int v36; // r9d
  bool v37; // cl
  __int64 v38; // rax
  bool v39; // al
  int v40; // eax
  char v41; // al
  char v42; // r8
  int v43; // ecx
  int v44; // edx
  int v45; // edx
  char v46; // al
  char v47; // dl
  bool v48; // cl
  char v49; // cl
  int v50; // eax
  int v51; // ecx
  char v52; // cl
  int v53; // eax
  char v54; // al
  char v55; // dl
  __int64 v56; // r15
  int v57; // eax
  char v58; // dl
  char v59; // al
  char v60; // dl
  char v61; // al
  __int64 v62; // rax
  __int64 v63; // rax
  struct _FAST_MUTEX *v64; // rcx
  __int64 v65; // r13
  char v66; // cl
  __int64 result; // rax
  int v68; // r11d
  int v69; // r10d
  int v70; // eax
  __int64 v71; // r8
  int v72; // edx
  char v73; // r13
  char v74; // r9
  char v75; // al
  char v76; // r15
  int v77; // r8d
  char v78; // cl
  char v79; // al
  char v80; // r14
  char v81; // bp
  char v82; // si
  char v83; // r10
  char v84; // di
  char v85; // r11
  int v86; // edx
  int v87; // r13d
  __int64 v88; // [rsp+B0h] [rbp-78h]
  int v89; // [rsp+B0h] [rbp-78h]
  int v90; // [rsp+B8h] [rbp-70h]
  __int64 v91; // [rsp+C0h] [rbp-68h]
  char v92; // [rsp+C0h] [rbp-68h]
  __int64 v93; // [rsp+C8h] [rbp-60h]
  int v94; // [rsp+C8h] [rbp-60h]
  bool v95; // [rsp+130h] [rbp+8h]

  v6 = a4;
  v95 = 0;
  v7 = -1;
  *(_OWORD *)a5 = 0;
  LOBYTE(v90) = -1;
  if ( *(_WORD *)a1 != 0xEC23 )
  {
    if ( a3 )
      v93 = *(_QWORD *)(a3 + 64);
    else
      v93 = 0;
    v10 = *(_QWORD *)(a1 + 144);
    if ( v10 && *(_WORD *)v10 != 0xEAA1 )
      v10 = 0;
    if ( a2 )
      v88 = *(_QWORD *)(a2 + 56);
    else
      v88 = 0;
    v11 = *(_QWORD *)(a1 + 128);
    if ( v11 )
      v12 = *(_QWORD *)(v11 + 48);
    else
      v12 = 0;
    v91 = v12;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    {
      if ( v10 )
        v68 = *(_DWORD *)(v10 + 76);
      else
        v68 = -1;
      if ( v12 )
        v69 = *(_DWORD *)(v12 + 8);
      else
        v69 = -1;
      if ( v10 )
      {
        v70 = *(_DWORD *)(v10 + 36);
        v71 = *(unsigned int *)(v10 + 20);
        v7 = *(_DWORD *)(v10 + 8);
      }
      else
      {
        v70 = -1;
        v71 = 0xFFFFFFFFLL;
      }
      WPP_SF_qddddddddd(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v71,
        a1,
        v6,
        *(_DWORD *)(a1 + 192),
        *(_DWORD *)(a1 + 184),
        *(_DWORD *)(a1 + 196),
        v7,
        v71,
        v70,
        v69,
        v68);
    }
    *(_DWORD *)(a5 + 12) = 0;
    if ( *(_QWORD *)(a1 + 192) )
      v13 = 0;
    else
      v13 = 64;
    v14 = v13 | *(_BYTE *)a5 & 0xBF;
    *(_BYTE *)a5 = v14;
    if ( a2
      && ((*(_DWORD *)(a2 + 72) & 0x400) != 0 || *(_DWORD *)(*(_QWORD *)(a1 + 304) + 296LL))
      && (*(_DWORD *)(a1 + 156) & 0x1000000) == 0
      && *(_DWORD *)(a1 + 184)
      || *(_DWORD *)(a1 + 192)
      || *(_DWORD *)(a1 + 196) )
    {
      v15 = 0;
    }
    else
    {
      v15 = 0x80;
    }
    v16 = v15 | v14 & 0x7F;
    *(_BYTE *)a5 = v16;
    if ( v10 && *(_QWORD *)(v10 + 56) )
    {
      v17 = v16 | 0x20;
      *(_BYTE *)a5 = v17;
    }
    else
    {
      v17 = v16 & 0xDF;
      *(_BYTE *)a5 = v17;
      if ( !v10 )
        goto LABEL_26;
    }
    v18 = 0;
    if ( *(_DWORD *)(v10 + 76) )
      v18 = 16;
    *(_BYTE *)(a5 + 1) = *(_BYTE *)(a5 + 1) & 0xEF | v18;
LABEL_26:
    v19 = *(_QWORD *)(a1 + 128);
    if ( !v19 )
    {
      v49 = v17;
LABEL_62:
      if ( v10 )
      {
        v50 = *(_DWORD *)(v10 + 4);
        v51 = 71279;
        if ( (v50 & 0x8000) != 0 )
          v51 = 70767;
        v52 = v17 & 0xFD | ((v51 & v50) != 0 ? 2 : 0);
        *(_BYTE *)a5 = v52;
        v53 = *(_DWORD *)(v10 + 4);
        if ( (v53 & 0x1166F) == 0 || (v53 & 0x166E) != 0 )
          v54 = 0;
        else
          v54 = 8;
        v55 = v54 | *(_BYTE *)(a5 + 1) & 0xF7;
        *(_BYTE *)(a5 + 1) = v55;
        if ( (*(_DWORD *)(v10 + 4) & 0x1000) != 0 )
          *(_BYTE *)(a5 + 1) = v55 | 0x20;
      }
      else
      {
        v52 = v49 & 0xFD;
        *(_BYTE *)a5 = v52;
      }
      v56 = v88;
      if ( v88 )
      {
        v57 = *(_DWORD *)(v88 + 24);
        if ( (v57 & 0x801) != 0 || (v57 & 2) == 0 )
        {
          v52 |= 2u;
          *(_BYTE *)a5 = v52;
        }
      }
      v58 = *(_BYTE *)(a5 + 1) & 0xFE | (*(_DWORD *)(a5 + 12) == 0);
      *(_BYTE *)(a5 + 1) = v58;
      if ( v10 && (*(_DWORD *)(v10 + 4) & 0x1000000) != 0 )
        v59 = 2;
      else
        v59 = 0;
      v60 = v59 | v58 & 0xFD;
      *(_BYTE *)(a5 + 1) = v60;
      if ( (v52 & 2) != 0 || (v52 & 1) != 0 && (v60 & 0x14) != 0x14 )
        v61 = 16;
      else
        v61 = 0;
      *(_BYTE *)a5 = v61 | v52 & 0xEF;
      v62 = *(_QWORD *)(a1 + 128);
      if ( v62 )
      {
        v63 = *(_QWORD *)(v62 + 48);
        v64 = (struct _FAST_MUTEX *)(v63 + 56);
        *(_QWORD *)(v63 + 112) = 0;
        if ( *(_BYTE *)(v63 + 120) )
          ExReleaseFastMutexUnsafe(v64);
        else
          ExReleaseFastMutex(v64);
      }
      v65 = v93;
      goto LABEL_83;
    }
    v20 = *(_QWORD *)(v19 + 48);
    v21 = KeAreApcsDisabled();
    v22 = (struct _FAST_MUTEX *)(v20 + 56);
    if ( v21 )
    {
      ExAcquireFastMutexUnsafe(v22);
      v23 = 1;
    }
    else
    {
      ExAcquireFastMutex(v22);
      v23 = 0;
    }
    *(_BYTE *)(v20 + 120) = v23;
    *(_QWORD *)(v20 + 112) = KeGetCurrentThread();
    NetRootCachingMode = RxQueryNetRootCachingMode(*(_QWORD *)(a1 + 120));
    *(_DWORD *)(a5 + 12) = NetRootCachingMode;
    v25 = NetRootCachingMode & 0x20000;
    if ( (NetRootCachingMode & 0x1FFFF) == 0x10000 || v25 )
    {
      v26 = 0x80;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v27 = v26 | *(_BYTE *)(a5 + 1) & 0x7F;
    v28 = HIWORD(NetRootCachingMode) & 1;
    *(_BYTE *)(a5 + 1) = v27;
    v29 = v28 | 2;
    if ( !v25 )
      v29 = v28;
    *(_DWORD *)(a5 + 4) = *(_DWORD *)(a5 + 4) & 0xFFFFFFFC | v29;
    v30 = *(_DWORD *)(v91 + 8);
    *(_WORD *)(a5 + 14) = 0;
    v31 = *(_DWORD *)(a5 + 12) == 12;
    *(_DWORD *)(a5 + 8) = v30;
    if ( !v31 || v10 )
      v32 = 4;
    else
      v32 = 0;
    v33 = v32 | *(_BYTE *)a5 & 0xFB;
    *(_BYTE *)a5 = v33;
    v34 = *(_QWORD *)(a1 + 128);
    v35 = *(_QWORD *)(v34 + 48);
    if ( v35 )
    {
      v36 = *(_DWORD *)(v35 + 4) & 0x23;
      v95 = v36 != 0;
      v37 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v34 + 32) + 32LL) + 48LL) == (_QWORD)CscDeviceObject;
      v39 = 0;
      if ( a2 )
      {
        v38 = *(_QWORD *)(a2 + 40);
        if ( v38 )
        {
          if ( (*(_DWORD *)(v38 + 56) & 0x10) != 0 )
            v39 = 1;
        }
      }
      if ( v36 || v37 || v39 )
        v39 = 1;
    }
    else
    {
      v39 = 0;
    }
    *(_BYTE *)a5 = v39 | v33 & 0xFE;
    v40 = *(_DWORD *)(v91 + 4);
    if ( (v40 & 0x23) == 0 || (v40 & 2) != 0 )
      v41 = 0;
    else
      v41 = 4;
    v42 = v41 | v27 & 0xFB;
    *(_BYTE *)(a5 + 1) = v42;
    if ( !(_BYTE)v6 || !v10 )
    {
LABEL_57:
      if ( ((*(_DWORD *)(a5 + 12) - 4) & 0xFFFFFFFB) != 0 )
        v46 = 0;
      else
        v46 = 8;
      v47 = v46 | *(_BYTE *)a5 & 0xF7;
      *(_BYTE *)a5 = v47;
      if ( v10 )
        v48 = (*(_DWORD *)(v10 + 4) & 0x1040080) != 0;
      else
        v48 = 0;
      v49 = v47 & 0xF7 ^ (v47 | (8 * v48)) & 8;
      *(_BYTE *)a5 = v49;
      v17 = v49;
      goto LABEL_62;
    }
    v43 = *(_DWORD *)(v10 + 4);
    if ( (v43 & 0x10003) == 0 )
    {
      v44 = *(_DWORD *)(v91 + 4);
      if ( (v44 & 0x23) == 0x20 && (v42 & 0x10) == 0 )
      {
        v45 = v43 | 0x10000;
        *(_DWORD *)(v10 + 4) = v43 | 0x10000;
        goto LABEL_56;
      }
      if ( (v44 & 1) != 0 && (v42 & 0x10) == 0 )
      {
        v45 = v43 | 1;
        *(_DWORD *)(v10 + 4) = v43 | 1;
LABEL_56:
        if ( (~v43 & v45) != 0 )
        {
          *(_DWORD *)(v10 + 4) = v45 & 0xFFFFFFF3;
          if ( a6 && (*(_BYTE *)a5 & 0x20) == 0 )
            _InterlockedOr8((volatile signed __int8 *)(a1 + 256), 2u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_ccDDdDd(WPP_GLOBAL_Control->AttachedDevice);
          }
        }
        goto LABEL_57;
      }
      if ( (v44 & 2) != 0 || (v43 & 0x8000) == 0 && *(_DWORD *)(v10 + 36) != *(_DWORD *)(v91 + 8) )
      {
        v45 = v43 | 2;
        *(_DWORD *)(v10 + 4) = v43 | 2;
        goto LABEL_56;
      }
    }
    v45 = *(_DWORD *)(v10 + 4);
    goto LABEL_56;
  }
  v65 = 0;
  v10 = 0;
  v56 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_61114c5048fe38b79d273cf1da5b551c_Traceguids);
  if ( *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 40) + 32LL) + 32LL) + 48LL) == CscDeviceObject )
    *(_BYTE *)a5 |= 0x10u;
LABEL_83:
  if ( (*(_BYTE *)(a1 + 256) & 2) != 0
    || (*(_DWORD *)(a1 + 156) & 0x80u) != 0
    || a2 && (*(_DWORD *)(a2 + 72) & 0x400) != 0
    || v65 && (*(_DWORD *)(v65 + 72) & 2) != 0 )
  {
    *(_BYTE *)(a5 + 2) |= 1u;
  }
  v66 = *(_BYTE *)(a5 + 2) & 1;
  if ( v66 || (*(_BYTE *)a5 & 0x30) == 0x10 )
    *(_BYTE *)(a5 + 1) |= 0x40u;
  result = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x20) != 0 )
    {
      v72 = *(char *)(a5 + 1);
      v94 = ((v72 >> 7) & 0xB) + 78;
      if ( v56 )
        v89 = *(_DWORD *)(v56 + 24);
      else
        LOBYTE(v89) = -1;
      if ( v10 )
        v90 = *(_DWORD *)(v10 + 4);
      v73 = *(_BYTE *)a5;
      v74 = 89;
      v75 = 89;
      v76 = 89;
      if ( !v66 )
        v75 = 78;
      v92 = v75;
      v77 = 89;
      if ( (*(_BYTE *)(a5 + 1) & 2) == 0 )
        v76 = 78;
      v78 = 89;
      v79 = 89;
      v80 = 89;
      v81 = 89;
      if ( (*(_BYTE *)(a5 + 1) & 0x10) == 0 )
        v74 = 78;
      v82 = 89;
      v83 = 89;
      if ( (*(_BYTE *)(a5 + 1) & 4) == 0 )
        v78 = 78;
      if ( !v95 )
        v79 = 78;
      if ( (v72 & 0x40) == 0 )
        v80 = 78;
      if ( (v73 & 4) == 0 )
        v81 = 78;
      if ( (v73 & 8) == 0 )
        v82 = 78;
      v84 = 89;
      if ( (v73 & 0x20) == 0 )
        v84 = 78;
      v85 = ((v73 >> 7) & 0xB) + 78;
      if ( (v73 & 0x40) == 0 )
        v83 = 78;
      if ( (v73 & 0x10) == 0 )
        v77 = 78;
      v86 = 89;
      if ( (v73 & 1) == 0 )
        v86 = 78;
      v31 = (v73 & 2) == 0;
      v87 = 89;
      if ( v31 )
        v87 = 78;
      return WPP_SF_cccccccccDDDcccccDc(
               WPP_GLOBAL_Control->AttachedDevice,
               v86,
               v77,
               v87,
               v86,
               v77,
               v83,
               v85,
               v84,
               v82,
               v81,
               v80,
               *(_DWORD *)(a5 + 12),
               v90,
               v89,
               v79,
               v78,
               v74,
               v76,
               v94,
               *(_DWORD *)(a5 + 4) & 3,
               v92);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003a00  push    rbx
0x140003a02  push    rbp
0x140003a03  push    rsi
0x140003a04  push    rdi
0x140003a05  push    r12
0x140003a07  push    r13
0x140003a09  push    r14
0x140003a0b  push    r15
0x140003a0d  sub     rsp, 0E8h
0x140003a14  mov     rbx, [rsp+128h+arg_20]
0x140003a1c  xorps   xmm0, xmm0
0x140003a1f  movzx   r13d, r9b
0x140003a23  mov     eax, 0EC23h
0x140003a28  xor     r14d, r14d
0x140003a2b  mov     [rsp+128h+arg_0], 0
0x140003a33  mov     r9d, 0FFFFFFFFh
0x140003a39  mov     dword ptr [rsp+128h+arg_20], 4Eh ; 'N'
0x140003a44  movups  xmmword ptr [rbx], xmm0
0x140003a47  mov     rbp, rdx
0x140003a4a  mov     rdi, rcx
0x140003a4d  mov     [rsp+128h+var_70], r9d
0x140003a55  cmp     [rcx], ax
0x140003a58  jz      loc_140003EF8
0x140003a5e  test    r8, r8
0x140003a61  jz      loc_140003F45
0x140003a67  mov     rax, [r8+40h]
0x140003a6b  mov     [rsp+128h+var_60], rax
0x140003a73  mov     rsi, [rcx+90h]
0x140003a7a  test    rsi, rsi
0x140003a7d  jz      short loc_140003A8B
0x140003a7f  mov     eax, 0EAA1h
0x140003a84  cmp     ax, [rsi]
0x140003a87  cmovnz  rsi, r14
0x140003a8b  test    rbp, rbp
0x140003a8e  jz      loc_140003F81
0x140003a94  mov     rax, [rdx+38h]
0x140003a98  mov     [rsp+128h+var_78], rax
0x140003aa0  mov     rax, [rcx+80h]
0x140003aa7  test    rax, rax
0x140003aaa  jz      loc_140003FBB
0x140003ab0  mov     rdx, [rax+30h]
0x140003ab4  mov     [rsp+128h+var_68], rdx
0x140003abc  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ac3  lea     r12, WPP_GLOBAL_Control
0x140003aca  cmp     rcx, r12
0x140003acd  jz      short loc_140003ADA
0x140003acf  mov     eax, [rcx+2Ch]
0x140003ad2  test    al, 20h
0x140003ad4  jnz     loc_1400040B3
0x140003ada  mov     [rbx+0Ch], r14d
0x140003ade  cmp     [rdi+0C0h], r14d
0x140003ae5  jz      loc_140003F59
0x140003aeb  xor     al, al
0x140003aed  movzx   edx, byte ptr [rbx]
0x140003af0  and     dl, 0BFh
0x140003af3  or      dl, al
0x140003af5  mov     [rbx], dl
0x140003af7  test    rbp, rbp
0x140003afa  jz      short loc_140003B1D
0x140003afc  test    dword ptr [rbp+48h], 400h
0x140003b03  jnz     loc_140004091
0x140003b09  mov     rax, [rdi+130h]
0x140003b10  cmp     [rax+128h], r14d
0x140003b17  ja      loc_140004091
0x140003b1d  cmp     [rdi+0C0h], r14d
0x140003b24  jz      loc_140003F6D
0x140003b2a  xor     al, al
0x140003b2c  and     dl, 7Fh
0x140003b2f  or      dl, al
0x140003b31  mov     [rbx], dl
0x140003b33  test    rsi, rsi
0x140003b36  jz      short loc_140003B42
0x140003b38  cmp     [rsi+38h], r14
0x140003b3c  jnz     loc_140003F9F
0x140003b42  and     dl, 0DFh
0x140003b45  mov     [rbx], dl
0x140003b47  test    rsi, rsi
0x140003b4a  jz      short loc_140003B65
0x140003b4c  mov     ecx, r14d
0x140003b4f  mov     eax, 10h
0x140003b54  cmp     [rsi+4Ch], ecx
0x140003b57  cmovnz  ecx, eax
0x140003b5a  movzx   eax, byte ptr [rbx+1]
0x140003b5e  and     al, 0EFh
0x140003b60  or      cl, al
0x140003b62  mov     [rbx+1], cl
0x140003b65  mov     r15, [rdi+80h]
0x140003b6c  test    r15, r15
0x140003b6f  jz      loc_140003F3D
0x140003b75  mov     r15, [r15+30h]
0x140003b79  call    cs:__imp_KeAreApcsDisabled
0x140003b80  nop     dword ptr [rax+rax+00h]
0x140003b85  lea     rcx, [r15+38h]; FastMutex
0x140003b89  test    al, al
0x140003b8b  jz      loc_140004185
0x140003b91  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140003b98  nop     dword ptr [rax+rax+00h]
0x140003b9d  mov     al, 1
0x140003b9f  mov     [r15+78h], al
0x140003ba3  mov     rax, gs:188h
0x140003bac  mov     [r15+70h], rax
0x140003bb0  mov     rcx, [rdi+78h]
0x140003bb4  call    cs:__imp_RxQueryNetRootCachingMode
0x140003bbb  nop     dword ptr [rax+rax+00h]
0x140003bc0  mov     edx, eax
0x140003bc2  mov     [rbx+0Ch], eax
0x140003bc5  mov     ecx, eax
0x140003bc7  and     edx, 20000h
0x140003bcd  and     ecx, 1FFFFh
0x140003bd3  cmp     ecx, 10000h
0x140003bd9  jnz     short loc_140003BDF
0x140003bdb  mov     cl, 80h
0x140003bdd  jmp     short loc_140003BE8
0x140003bdf  test    edx, edx
0x140003be1  jnz     short loc_140003BDB
0x140003be3  mov     edx, r14d
0x140003be6  xor     cl, cl
0x140003be8  movzx   r8d, byte ptr [rbx+1]
0x140003bed  mov     r10, [rsp+128h+var_68]
0x140003bf5  and     r8b, 7Fh
0x140003bf9  or      r8b, cl
0x140003bfc  shr     eax, 10h
0x140003bff  and     eax, 1
0x140003c02  mov     [rbx+1], r8b
0x140003c06  mov     ecx, eax
0x140003c08  or      ecx, 2
0x140003c0b  test    edx, edx
0x140003c0d  cmovz   ecx, eax
0x140003c10  mov     eax, [rbx+4]
0x140003c13  and     eax, 0FFFFFFFCh
0x140003c16  or      ecx, eax
0x140003c18  mov     [rbx+4], ecx
0x140003c1b  mov     eax, [r10+8]
0x140003c1f  mov     [rbx+0Eh], r14w
0x140003c24  cmp     dword ptr [rbx+0Ch], 0Ch
0x140003c28  mov     [rbx+8], eax
0x140003c2b  jz      loc_140004081
0x140003c31  mov     al, 4
0x140003c33  movzx   edx, byte ptr [rbx]
0x140003c36  and     dl, 0FBh
0x140003c39  or      dl, al
0x140003c3b  mov     [rbx], dl
0x140003c3d  mov     rax, [rdi+80h]
0x140003c44  mov     r9, [rax+30h]
0x140003c48  test    r9, r9
0x140003c4b  jz      loc_1400041C7
0x140003c51  mov     rax, [rax+20h]
0x140003c55  mov     r9d, [r9+4]
0x140003c59  and     r9d, 23h
0x140003c5d  mov     rcx, [rax+20h]
0x140003c61  setnz   [rsp+128h+arg_0]
0x140003c69  mov     rax, cs:CscDeviceObject
0x140003c70  cmp     [rcx+30h], rax
0x140003c74  setz    cl
0x140003c77  test    rbp, rbp
0x140003c7a  jz      short loc_140003C90
0x140003c7c  mov     rax, [rbp+28h]
0x140003c80  test    rax, rax
0x140003c83  jz      short loc_140003C90
0x140003c85  mov     eax, [rax+38h]
0x140003c88  test    al, 10h
0x140003c8a  jnz     loc_14000406B
0x140003c90  xor     al, al
0x140003c92  test    r9d, r9d
0x140003c95  jnz     loc_140003F52
0x140003c9b  test    cl, cl
0x140003c9d  jnz     loc_140003F52
0x140003ca3  test    al, al
0x140003ca5  jnz     loc_140003F52
0x140003cab  and     dl, 0FEh
0x140003cae  or      dl, al
0x140003cb0  mov     [rbx], dl
0x140003cb2  mov     eax, [r10+4]
0x140003cb6  test    al, 23h
0x140003cb8  jnz     loc_140004072
0x140003cbe  xor     al, al
0x140003cc0  and     r8b, 0FBh
0x140003cc4  or      r8b, al
0x140003cc7  mov     [rbx+1], r8b
0x140003ccb  test    r13b, r13b
0x140003cce  jz      short loc_140003D23
0x140003cd0  test    rsi, rsi
0x140003cd3  jz      short loc_140003D23
0x140003cd5  mov     ecx, [rsi+4]
0x140003cd8  test    ecx, 10003h
0x140003cde  jnz     short loc_140003D15
0x140003ce0  mov     edx, [r10+4]
0x140003ce4  mov     eax, edx
0x140003ce6  and     al, 23h
0x140003ce8  cmp     al, 20h ; ' '
0x140003cea  jz      loc_14000416D
0x140003cf0  test    dl, 1
0x140003cf3  jnz     loc_140004198
0x140003cf9  test    dl, 2
0x140003cfc  jnz     loc_140003FC3
0x140003d02  bt      ecx, 0Fh
0x140003d06  jb      short loc_140003D15
0x140003d08  mov     eax, [r10+8]
0x140003d0c  cmp     [rsi+24h], eax
0x140003d0f  jnz     loc_140003FC3
0x140003d15  mov     edx, ecx
0x140003d17  mov     eax, ecx
0x140003d19  not     eax
0x140003d1b  test    edx, eax
0x140003d1d  jnz     loc_140003FD0
0x140003d23  mov     eax, [rbx+0Ch]
0x140003d26  sub     eax, 4
0x140003d29  test    eax, 0FFFFFFFBh
0x140003d2e  jnz     loc_140004064
0x140003d34  mov     al, 8
0x140003d36  movzx   edx, byte ptr [rbx]
0x140003d39  and     dl, 0F7h
0x140003d3c  or      dl, al
0x140003d3e  mov     [rbx], dl
0x140003d40  test    rsi, rsi
0x140003d43  jz      loc_140003F97
0x140003d49  test    dword ptr [rsi+4], 1040080h
0x140003d50  setnz   cl
0x140003d53  shl     cl, 3
0x140003d56  or      cl, dl
0x140003d58  and     dl, 0F7h
0x140003d5b  and     cl, 8
0x140003d5e  xor     cl, dl
0x140003d60  mov     [rbx], cl
0x140003d62  movzx   edx, cl
0x140003d65  test    rsi, rsi
0x140003d68  jz      loc_140003EEE
0x140003d6e  mov     eax, [rsi+4]
0x140003d71  mov     ecx, 1166Fh
0x140003d76  bt      eax, 0Fh
0x140003d7a  jb      loc_1400041CE
0x140003d80  and     eax, ecx
0x140003d82  neg     eax
0x140003d84  sbb     cl, cl
0x140003d86  and     dl, 0FDh
0x140003d89  and     cl, 2
0x140003d8c  or      cl, dl
0x140003d8e  mov     [rbx], cl
0x140003d90  mov     eax, [rsi+4]
0x140003d93  test    eax, 1166Fh
0x140003d98  jnz     loc_140003FA9
0x140003d9e  xor     al, al
0x140003da0  movzx   edx, byte ptr [rbx+1]
0x140003da4  and     dl, 0F7h
0x140003da7  or      dl, al
0x140003da9  mov     [rbx+1], dl
0x140003dac  test    dword ptr [rsi+4], 1000h
0x140003db3  jnz     loc_1400041D8
0x140003db9  mov     r15, [rsp+128h+var_78]
0x140003dc1  test    r15, r15
0x140003dc4  jz      short loc_140003DDA
0x140003dc6  mov     eax, [r15+18h]
0x140003dca  test    eax, 801h
0x140003dcf  jnz     short loc_140003DD5
0x140003dd1  test    al, 2
0x140003dd3  jnz     short loc_140003DDA
0x140003dd5  or      cl, 2
0x140003dd8  mov     [rbx], cl
0x140003dda  cmp     [rbx+0Ch], r14d
0x140003dde  movzx   eax, byte ptr [rbx+1]
0x140003de2  setz    dl
0x140003de5  and     al, 0FEh
0x140003de7  or      dl, al
0x140003de9  mov     [rbx+1], dl
0x140003dec  test    rsi, rsi
0x140003def  jz      short loc_140003DFE
0x140003df1  test    dword ptr [rsi+4], 1000000h
0x140003df8  jnz     loc_1400041AF
0x140003dfe  xor     al, al
0x140003e00  and     dl, 0FDh
0x140003e03  or      dl, al
0x140003e05  mov     [rbx+1], dl
0x140003e08  test    cl, 2
0x140003e0b  jnz     loc_140003EE7
0x140003e11  test    cl, 1
0x140003e14  jnz     loc_140003EDB
0x140003e1a  xor     al, al
0x140003e1c  and     cl, 0EFh
0x140003e1f  or      cl, al
0x140003e21  mov     [rbx], cl
0x140003e23  mov     rax, [rdi+80h]
0x140003e2a  test    rax, rax
0x140003e2d  jz      short loc_140003E51
0x140003e2f  mov     rax, [rax+30h]
0x140003e33  lea     rcx, [rax+38h]; FastMutex
0x140003e37  mov     [rax+70h], r14
0x140003e3b  cmp     [rax+78h], r14b
0x140003e3f  jz      loc_1400041B6
0x140003e45  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140003e4c  nop     dword ptr [rax+rax+00h]
0x140003e51  mov     r13, [rsp+128h+var_60]
0x140003e59  test    byte ptr [rdi+100h], 2
0x140003e60  jz      short loc_140003EB4
0x140003e62  or      byte ptr [rbx+2], 1
0x140003e66  movzx   ecx, byte ptr [rbx+2]
0x140003e6a  and     cl, 1
0x140003e6d  jnz     loc_140003F8E
0x140003e73  movzx   eax, byte ptr [rbx]
0x140003e76  and     al, 30h
0x140003e78  cmp     al, 10h
  ... truncated ...
```
