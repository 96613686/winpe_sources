# PmapQueryAndProbe

- ea: `0x14000adb0`
- end: `0x14000b66d`
- name: `PmapQueryAndProbe`
- size: `2237`
- prototype: `__int64 __fastcall(__int64, __int64, __int16 *, unsigned int, unsigned int *, __int64, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140001760`
- `0x140009f60`
- `0x14001dce8`
- `0x140020c90`
- `0x1400235c0`

## callees

- `0x14000adb0`
- `0x14000b900`
- `0x14000bab0`
- `0x140011f84`
- `0x140014c30`
- `0x140014c64`
- `0x1400159cc`
- `0x1400159fc`
- `0x14002d1e4`
- `0x140033ee0`
- `0x140034248`
- `0x1400343b8`
- `0x140034534`
- `0x140038708`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x14000af84`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000b545`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000af84`
- `ntoskrnl!ExInitializeResourceLite` at `0x14000b545`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b068`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b5fa`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b068`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000b5fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b07a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b60c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b07a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b60c`
- `ntoskrnl!ExAllocatePool2` at `0x14000af2d`
- `ntoskrnl!ExAllocatePool2` at `0x14000b108`
- `ntoskrnl!ExAllocatePool2` at `0x14000af2d`
- `ntoskrnl!ExAllocatePool2` at `0x14000b108`
- `rpcxdr!OncRpcBuildCall` at `0x14000b1b5`
- `rpcxdr!OncRpcBuildCall` at `0x14000b1b5`
- `rpcxdr!OncRpcDestroy` at `0x14000b480`
- `rpcxdr!OncRpcDestroy` at `0x14000b496`
- `rpcxdr!OncRpcDestroy` at `0x14000b480`
- `rpcxdr!OncRpcDestroy` at `0x14000b496`

## pseudocode

```c
__int64 __fastcall PmapQueryAndProbe(
        __int64 a1,
        __int64 a2,
        __int16 *a3,
        unsigned int a4,
        unsigned int *a5,
        __int64 a6,
        _QWORD *a7,
        _QWORD *a8)
{
  unsigned int v9; // r12d
  __int16 v10; // di
  unsigned int v11; // r15d
  __int16 v12; // dx
  __int16 v13; // ax
  unsigned int v14; // r13d
  unsigned int v15; // ecx
  __int16 v16; // cx
  struct _ERESOURCE *v17; // xmm1_8
  struct _ERESOURCE *v18; // xmm0_8
  int v19; // ebx
  __int64 v20; // rcx
  bool v21; // zf
  __int64 v22; // r8
  char v23; // r12
  __int16 v24; // ax
  struct _ERESOURCE *Pool2; // rax
  unsigned int v26; // r15d
  char v27; // r12
  int v28; // r11d
  int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r8
  const char *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  _BYTE *v45; // r10
  __int64 v46; // r8
  __int64 v47; // r9
  _BYTE *v48; // r8
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rbx
  __int64 v54; // rdx
  __int16 v55; // r15
  unsigned int v56; // edx
  __int64 v57; // rdi
  __int64 v58; // r8
  PDEVICE_OBJECT v59; // rcx
  __int64 v60; // rdx
  _DWORD *v61; // rcx
  unsigned int v63; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v64; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v65; // [rsp+48h] [rbp-B8h]
  __int64 v66; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v67; // [rsp+58h] [rbp-A8h]
  __int64 v68; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v69; // [rsp+68h] [rbp-98h]
  int v70; // [rsp+70h] [rbp-90h] BYREF
  __int128 v71; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+88h] [rbp-78h]
  __int128 v73; // [rsp+90h] [rbp-70h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h]
  _QWORD *v75; // [rsp+A8h] [rbp-58h]
  _QWORD *v76; // [rsp+B0h] [rbp-50h]
  PERESOURCE Resource[10]; // [rsp+C0h] [rbp-40h] BYREF
  PERESOURCE v78; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v79; // [rsp+118h] [rbp+18h]
  unsigned int v80; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v81; // [rsp+120h] [rbp+20h]
  int v82; // [rsp+124h] [rbp+24h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  __int64 v84; // [rsp+130h] [rbp+30h]
  __int64 v85; // [rsp+138h] [rbp+38h] BYREF
  __int128 v86; // [rsp+140h] [rbp+40h]
  __int64 v87; // [rsp+150h] [rbp+50h]

  v74 = a6;
  v9 = a4;
  v75 = a7;
  v72 = a2;
  v69 = a1;
  v76 = a8;
  v67 = a4;
  memset(Resource, 0, 0x48u);
  v10 = *a3;
  v63 = 0;
  v71 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
  {
    v13 = v10;
    v12 = v10;
  }
  else
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_775836655b5d3951eb084104865a818b_Traceguids);
    v12 = *a3;
    v13 = *a3;
  }
  v14 = *a5;
  Resource[0] = 0;
  v15 = 4;
  LODWORD(Resource[1]) = 0;
  if ( v10 == 2 )
    v15 = 2;
  Resource[2] = (PERESOURCE)v15;
  memset(&Resource[5], 0, 32);
  HIDWORD(Resource[1]) = 100000;
  if ( v12 == 2 )
  {
    v18 = *(struct _ERESOURCE **)(a3 + 2);
    HIWORD(Resource[5]) = a3[1];
    LODWORD(Resource[7]) = *((_DWORD *)a3 + 3);
    Resource[6] = v18;
  }
  else
  {
    if ( v12 != 23 )
    {
      *(_OWORD *)((char *)&Resource[5] + 4) = 0;
      *(_OWORD *)&Resource[7] = 0;
      goto LABEL_15;
    }
    v16 = a3[1];
    v17 = *(struct _ERESOURCE **)(a3 + 10);
    *(_OWORD *)&Resource[6] = *(_OWORD *)(a3 + 2);
    HIWORD(Resource[5]) = v16;
    Resource[8] = v17;
  }
  WORD2(Resource[5]) = v13;
  if ( v13 == 23 || v13 == 2 )
    HIWORD(Resource[5]) = 28416;
LABEL_15:
  Resource[3] = 0;
  Resource[4] = 0;
  Resource[0] = (PERESOURCE)ExAllocatePool2(66, 104, 1783785038);
  if ( Resource[0] )
  {
    v19 = -1073741811;
    ExInitializeResourceLite(Resource[0]);
    v20 = v69;
    *(_QWORD *)&v71 = __PAIR64__(v14, v9);
    HIDWORD(v71) = 0;
    if ( (*(_BYTE *)(v69 + 1416) & 1) != 0
      || (v21 = (*(_BYTE *)(v69 + 1417) & 0x40) == 0, LODWORD(Resource[1]) = 17, !v21) )
    {
      LODWORD(Resource[1]) = 6;
    }
    while ( 1 )
    {
      if ( v11 >= 2 )
      {
LABEL_33:
        v9 = v67;
        LOWORD(v11) = 0;
        goto LABEL_34;
      }
      v19 = NfsConnect(v20, Resource);
      if ( v19 >= 0 )
        break;
      v23 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 23, v22, LODWORD(Resource[1]), v19);
      v20 = v69;
      if ( LODWORD(Resource[1]) == 6 && ((*(_BYTE *)(v69 + 1416) & 2) != 0 || *(char *)(v69 + 1417) < 0) )
      {
        LODWORD(Resource[1]) = 17;
        v23 = 1;
        Resource[3] = 0;
      }
      ++v11;
      if ( !v23 )
        goto LABEL_33;
    }
    v66 = 0;
    v26 = 0;
    v68 = 0;
    v27 = 1;
    while ( 1 )
    {
      v65 = v26;
      if ( v26 >= 2 || !v27 )
      {
LABEL_109:
        NfsForceDisconnect(Resource, 0);
        LOWORD(v11) = v63;
        v9 = v67;
        goto LABEL_34;
      }
      if ( !(unsigned __int8)NfsRdrpSetProtocol(v69, &v71, v26) )
      {
        v19 = -1073741823;
        goto LABEL_109;
      }
      v29 = 16;
      if ( v10 != 2 )
        v29 = v28;
      if ( (int)OncRpcBuildCall(
                  &v66,
                  (char *)&Resource[5] + 4,
                  LODWORD(Resource[1]),
                  HIDWORD(Resource[1]),
                  Resource[2],
                  3,
                  v29,
                  0) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_775836655b5d3951eb084104865a818b_Traceguids);
        v19 = -1073741670;
        goto LABEL_109;
      }
      v31 = v66;
      v32 = *(_QWORD *)(v66 + 72);
      if ( v32 )
        v32 = *(_QWORD *)(v32 + 64);
      *(_DWORD *)v32 = _byteswap_ulong(v71);
      v33 = DWORD1(v71);
      *(_QWORD *)(*(_QWORD *)(v31 + 72) + 64LL) += 4LL;
      v34 = v66;
      v35 = *(_QWORD *)(v66 + 72);
      if ( v35 )
        v35 = *(_QWORD *)(v35 + 64);
      *(_DWORD *)v35 = _byteswap_ulong(v33);
      *(_QWORD *)(*(_QWORD *)(v34 + 72) + 64LL) += 4LL;
      if ( v10 == 2 )
      {
        v36 = v66;
        v37 = *(_QWORD *)(v66 + 72);
        if ( v37 )
          v37 = *(_QWORD *)(v37 + 64);
        *(_DWORD *)v37 = _byteswap_ulong(DWORD2(v71));
        *(_QWORD *)(*(_QWORD *)(v36 + 72) + 64LL) += 4LL;
        v38 = v66;
        v39 = *(_QWORD *)(v66 + 72);
        if ( v39 )
          **(_DWORD **)(v39 + 64) = _byteswap_ulong(HIDWORD(v71));
        else
          MEMORY[0] = _byteswap_ulong(HIDWORD(v71));
        v40 = *(_QWORD *)(v38 + 72);
      }
      else
      {
        v41 = v66;
        v42 = "tcp6";
        if ( DWORD2(v71) != 6 )
          v42 = "udp6";
        v43 = *(_QWORD *)(v66 + 72);
        if ( v43 )
          v43 = *(_QWORD *)(v43 + 64);
        *(_DWORD *)v43 = 0x4000000;
        *(_QWORD *)(*(_QWORD *)(v41 + 72) + 64LL) += 4LL;
        v44 = *(_QWORD *)(v41 + 72);
        if ( v44 )
          v44 = *(_QWORD *)(v44 + 64);
        *(_DWORD *)v44 = *(_DWORD *)v42;
        *(_QWORD *)(*(_QWORD *)(v41 + 72) + 64LL) += 4LL;
        XdrNextMod4Boundary(v41, v44, v41, v30);
        v47 = *(_QWORD *)(v46 + 72);
        if ( v47 )
          v48 = *(_BYTE **)(v47 + 64);
        else
          v48 = 0;
        if ( v45 != v48 )
          memset(v45, 0, v48 - v45);
        v49 = v66;
        v50 = *(_QWORD *)(v66 + 72);
        if ( v50 )
          v50 = *(_QWORD *)(v50 + 64);
        *(_DWORD *)v50 = 0;
        *(_QWORD *)(*(_QWORD *)(v49 + 72) + 64LL) += 4LL;
        v51 = v66;
        v52 = *(_QWORD *)(v66 + 72);
        if ( v52 )
          v52 = *(_QWORD *)(v52 + 64);
        *(_DWORD *)v52 = 0;
        v40 = *(_QWORD *)(v51 + 72);
      }
      *(_QWORD *)(v40 + 64) += 4LL;
      v53 = v66;
      if ( *(int *)(v66 + 264) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_775836655b5d3951eb084104865a818b_Traceguids);
          v53 = v66;
        }
        v19 = *(_DWORD *)(v53 + 264);
        goto LABEL_109;
      }
      v27 = 0;
      v19 = NfsRdrpSunRpcSendWaitReply(v69, v72, (unsigned int)Resource, v66, (__int64)&v68);
      if ( v19 >= 0 )
        break;
LABEL_95:
      if ( v66 )
        OncRpcDestroy(v66);
      if ( v68 )
        OncRpcDestroy(v68);
      ++v26;
    }
    v55 = 0;
    v70 = 0;
    v64 = 0;
    v73 = 0;
    if ( v10 == 2 )
    {
      v63 = XdrDecodeInt(v68);
      v56 = v63;
      if ( v63 > 0xFFFF )
      {
        v19 = -1073741811;
        goto LABEL_81;
      }
    }
    else
    {
      XdrDecodeStringAndLength(v68, v54, &v70, &v78);
      v56 = v63;
      v55 = v70;
    }
    if ( *(int *)(v68 + 264) >= 0 )
    {
      if ( v10 != 2 )
      {
        LOWORD(v73) = v55;
        *((_QWORD *)&v73 + 1) = &v78;
        WORD1(v73) = 96;
        v19 = NfsIpv6UniversalAddressToPort(&v73, &v64);
        if ( v19 < 0 )
          goto LABEL_94;
        v56 = v64;
        v63 = v64;
      }
      goto LABEL_87;
    }
LABEL_81:
    v63 = v56;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_775836655b5d3951eb084104865a818b_Traceguids);
      v56 = v63;
    }
    if ( v19 >= 0 )
      v19 = *(_DWORD *)(v68 + 264);
    v27 = 1;
    if ( v19 < 0 )
    {
LABEL_94:
      v26 = v65;
      goto LABEL_95;
    }
LABEL_87:
    v26 = v65;
    if ( !v56 )
    {
      v19 = -1073741823;
      v27 = 1;
    }
    goto LABEL_95;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_775836655b5d3951eb084104865a818b_Traceguids);
  v19 = -1073741670;
LABEL_34:
  if ( Resource[0] )
  {
    ExDeleteResourceLite(Resource[0]);
    ExFreePoolWithTag(Resource[0], 0);
  }
  if ( v19 >= 0 )
  {
    v79 = DWORD2(v71);
    v24 = *a3;
    v78 = 0;
    v82 = 0;
    v85 = 0;
    v86 = 0;
    v87 = 0;
    v83 = 0;
    v84 = 0;
    v80 = v9;
    v81 = v14;
    if ( v24 == 23 || v24 == 2 )
      a3[1] = __ROR2__(v11, 8);
    OncRpcCopyAddress((char *)&v85 + 4, a3);
    Pool2 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 1783785038);
    v78 = Pool2;
    if ( !Pool2 )
    {
      v19 = -1073741670;
      goto LABEL_121;
    }
    ExInitializeResourceLite(Pool2);
    v57 = v69;
    v19 = NfsConnect(v69, &v78);
    if ( v19 >= 0 )
    {
      v19 = NfsRdrpPingNullProc(v57, &v78, v72);
      if ( v19 >= 0 )
      {
        v61 = (_DWORD *)v74;
        *a5 = v81;
        *v61 = v79;
        *v75 = v83;
        *v76 = v84;
        goto LABEL_120;
      }
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_120;
      v60 = 28;
    }
    else
    {
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_120;
      v60 = 27;
    }
    WPP_SF_dD(v59->AttachedDevice, v60, v58, v79, v19);
LABEL_120:
    ExDeleteResourceLite(v78);
    ExFreePoolWithTag(v78, 0);
  }
LABEL_121:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_775836655b5d3951eb084104865a818b_Traceguids);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14000adb0  push    rbp
0x14000adb2  push    rbx
0x14000adb3  push    rsi
0x14000adb4  push    rdi
0x14000adb5  push    r12
0x14000adb7  push    r13
0x14000adb9  push    r14
0x14000adbb  push    r15
0x14000adbd  lea     rbp, [rsp-88h]
0x14000adc5  sub     rsp, 188h
0x14000adcc  mov     rax, cs:__security_cookie
0x14000add3  xor     rax, rsp
0x14000add6  mov     [rbp+0C0h+var_50], rax
0x14000adda  mov     rax, [rbp+0C0h+arg_28]
0x14000ade1  mov     rsi, r8
0x14000ade4  mov     r14, [rbp+0C0h+arg_20]
0x14000adeb  mov     r8d, 48h ; 'H'; Size
0x14000adf1  mov     [rbp+0C0h+var_120], rax
0x14000adf5  mov     r12d, r9d
0x14000adf8  mov     rax, [rbp+0C0h+arg_30]
0x14000adff  mov     [rbp+0C0h+var_118], rax
0x14000ae03  mov     rax, [rbp+0C0h+arg_38]
0x14000ae0a  mov     [rbp+0C0h+var_138], rdx
0x14000ae0e  xor     edx, edx; Val
0x14000ae10  mov     [rsp+1C0h+var_158], rcx
0x14000ae15  lea     rcx, [rbp+0C0h+Resource]; void *
0x14000ae19  mov     [rbp+0C0h+var_110], rax
0x14000ae1d  mov     [rsp+1C0h+var_168], r9d
0x14000ae22  call    memset
0x14000ae27  movzx   edi, word ptr [rsi]
0x14000ae2a  xor     ebx, ebx
0x14000ae2c  xorps   xmm0, xmm0
0x14000ae2f  mov     [rsp+1C0h+var_180], ebx
0x14000ae33  movups  [rsp+1C0h+var_148], xmm0
0x14000ae38  mov     r15d, ebx
0x14000ae3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae42  lea     rax, WPP_GLOBAL_Control
0x14000ae49  cmp     rcx, rax
0x14000ae4c  jz      short loc_14000AE72
0x14000ae4e  mov     eax, [rcx+2Ch]
0x14000ae51  test    al, 10h
0x14000ae53  jz      short loc_14000AE72
0x14000ae55  mov     rcx, [rcx+18h]
0x14000ae59  lea     r8, WPP_775836655b5d3951eb084104865a818b_Traceguids
0x14000ae60  mov     edx, 15h
0x14000ae65  call    WPP_SF_
0x14000ae6a  movzx   edx, word ptr [rsi]
0x14000ae6d  movzx   eax, dx
0x14000ae70  jmp     short loc_14000AE78
0x14000ae72  movzx   eax, di
0x14000ae75  movzx   edx, di
0x14000ae78  mov     r13d, [r14]
0x14000ae7b  mov     r8d, 2
0x14000ae81  cmp     di, r8w
0x14000ae85  mov     [rbp+0C0h+Resource], rbx
0x14000ae89  mov     ecx, 4
0x14000ae8e  mov     [rbp+0C0h+var_F8], ebx
0x14000ae91  cmovz   ecx, r8d
0x14000ae95  mov     [rbp+0C0h+var_EC], ebx
0x14000ae98  mov     [rbp+0C0h+var_F0], ecx
0x14000ae9b  xorps   xmm0, xmm0
0x14000ae9e  mov     qword ptr [rbp+0C0h+var_D8], rbx
0x14000aea2  movdqa  [rbp+0C0h+var_D8+8], xmm0
0x14000aea7  mov     [rbp+0C0h+var_C0], rbx
0x14000aeab  mov     [rbp+0C0h+var_F4], 186A0h
0x14000aeb2  cmp     dx, r8w
0x14000aeb6  jz      short loc_14000AEE4
0x14000aeb8  cmp     dx, 17h
0x14000aebc  jz      short loc_14000AEC8
0x14000aebe  movups  [rbp+0C0h+var_D8+4], xmm0
0x14000aec2  movups  xmmword ptr [rbp-8], xmm0
0x14000aec6  jmp     short loc_14000AF15
0x14000aec8  movups  xmm0, xmmword ptr [rsi+4]
0x14000aecc  movzx   ecx, word ptr [rsi+2]
0x14000aed0  movsd   xmm1, qword ptr [rsi+14h]
0x14000aed5  movaps  [rbp+0C0h+var_D8+8], xmm0
0x14000aed9  mov     word ptr [rbp+0C0h+var_D8+6], cx
0x14000aedd  movsd   [rbp+0C0h+var_C0], xmm1
0x14000aee2  jmp     short loc_14000AEFC
0x14000aee4  movzx   ecx, word ptr [rsi+2]
0x14000aee8  movsd   xmm0, qword ptr [rsi+4]
0x14000aeed  mov     word ptr [rbp+0C0h+var_D8+6], cx
0x14000aef1  mov     ecx, [rsi+0Ch]
0x14000aef4  mov     [rbp+0C0h+var_C8], ecx
0x14000aef7  movsd   qword ptr [rbp+0C0h+var_D8+8], xmm0
0x14000aefc  mov     word ptr [rbp+0C0h+var_D8+4], ax
0x14000af00  cmp     ax, 17h
0x14000af04  jz      short loc_14000AF0C
0x14000af06  cmp     ax, r8w
0x14000af0a  jnz     short loc_14000AF15
0x14000af0c  mov     eax, 6F00h
0x14000af11  mov     word ptr [rbp+0C0h+var_D8+6], ax
0x14000af15  mov     edx, 68h ; 'h'
0x14000af1a  mov     [rbp+0C0h+var_E8], rbx
0x14000af1e  mov     ecx, 42h ; 'B'
0x14000af23  mov     [rbp+0C0h+var_E0], rbx
0x14000af27  mov     r8d, 6A52664Eh
0x14000af2d  call    cs:__imp_ExAllocatePool2
0x14000af34  nop     dword ptr [rax+rax+00h]
0x14000af39  mov     [rbp+0C0h+Resource], rax
0x14000af3d  test    rax, rax
0x14000af40  jnz     short loc_14000AF7B
0x14000af42  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af49  lea     rbx, WPP_GLOBAL_Control
0x14000af50  cmp     rcx, rbx
0x14000af53  jz      short loc_14000AF71
0x14000af55  mov     eax, [rcx+2Ch]
0x14000af58  test    al, 1
0x14000af5a  jz      short loc_14000AF71
0x14000af5c  mov     rcx, [rcx+18h]
0x14000af60  lea     r8, WPP_775836655b5d3951eb084104865a818b_Traceguids
0x14000af67  mov     edx, 16h
0x14000af6c  call    WPP_SF_
0x14000af71  mov     ebx, 0C000009Ah
0x14000af76  jmp     loc_14000B058
0x14000af7b  mov     rcx, [rbp+0C0h+Resource]; Resource
0x14000af7f  mov     ebx, 0C000000Dh
0x14000af84  call    cs:__imp_ExInitializeResourceLite
0x14000af8b  nop     dword ptr [rax+rax+00h]
0x14000af90  mov     rcx, [rsp+1C0h+var_158]
0x14000af95  mov     dword ptr [rsp+1C0h+var_148], r12d
0x14000af9a  mov     dword ptr [rsp+1C0h+var_148+4], r13d
0x14000af9f  mov     dword ptr [rbp+0C0h+var_148+0Ch], r15d
0x14000afa3  test    byte ptr [rcx+588h], 1
0x14000afaa  jnz     short loc_14000AFBC
0x14000afac  test    byte ptr [rcx+589h], 40h
0x14000afb3  mov     [rbp+0C0h+var_F8], 11h
0x14000afba  jz      short loc_14000AFC3
0x14000afbc  mov     [rbp+0C0h+var_F8], 6
0x14000afc3  cmp     r15d, 2
0x14000afc7  jnb     loc_14000B04E
0x14000afcd  lea     rdx, [rbp+0C0h+Resource]
0x14000afd1  call    NfsConnect
0x14000afd6  mov     ebx, eax
0x14000afd8  test    eax, eax
0x14000afda  jns     loc_14000B12B
0x14000afe0  xor     r12b, r12b
0x14000afe3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afea  lea     rax, WPP_GLOBAL_Control
0x14000aff1  cmp     rcx, rax
0x14000aff4  jz      short loc_14000B013
0x14000aff6  mov     eax, [rcx+2Ch]
0x14000aff9  test    al, 1
0x14000affb  jz      short loc_14000B013
0x14000affd  mov     r9d, [rbp+0C0h+var_F8]
0x14000b001  mov     edx, 17h
0x14000b006  mov     rcx, [rcx+18h]
0x14000b00a  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x14000b00e  call    WPP_SF_dD
0x14000b013  cmp     [rbp+0C0h+var_F8], 6
0x14000b017  mov     rcx, [rsp+1C0h+var_158]
0x14000b01c  jnz     short loc_14000B042
0x14000b01e  test    byte ptr [rcx+588h], 2
0x14000b025  jnz     short loc_14000B030
0x14000b027  cmp     [rcx+589h], r12b
0x14000b02e  jge     short loc_14000B042
0x14000b030  mov     [rbp+0C0h+var_F8], 11h
0x14000b037  mov     r12b, 1
0x14000b03a  mov     [rbp+0C0h+var_E8], 0
0x14000b042  inc     r15d
0x14000b045  test    r12b, r12b
0x14000b048  jnz     loc_14000AFC3
0x14000b04e  mov     r12d, [rsp+1C0h+var_168]
0x14000b053  mov     r15d, [rsp+1C0h+var_180]
0x14000b058  lea     rdi, WPP_GLOBAL_Control
0x14000b05f  mov     rcx, [rbp+0C0h+Resource]; Resource
0x14000b063  test    rcx, rcx
0x14000b066  jz      short loc_14000B086
0x14000b068  call    cs:__imp_ExDeleteResourceLite
0x14000b06f  nop     dword ptr [rax+rax+00h]
0x14000b074  mov     rcx, [rbp+0C0h+Resource]; P
0x14000b078  xor     edx, edx; Tag
0x14000b07a  call    cs:__imp_ExFreePoolWithTag
0x14000b081  nop     dword ptr [rax+rax+00h]
0x14000b086  test    ebx, ebx
0x14000b088  js      loc_14000B61F
0x14000b08e  mov     eax, dword ptr [rbp+0C0h+var_148+8]
0x14000b091  xorps   xmm0, xmm0
0x14000b094  mov     [rbp+0C0h+var_A8], eax
0x14000b097  movzx   eax, word ptr [rsi]
0x14000b09a  mov     [rbp+0C0h+var_B0], 0
0x14000b0a2  mov     [rbp+0C0h+var_9C], 0
0x14000b0a9  mov     [rbp+0C0h+var_88], 0
0x14000b0b1  movdqa  [rbp+0C0h+var_80], xmm0
0x14000b0b6  mov     [rbp+0C0h+var_70], 0
0x14000b0be  mov     [rbp+0C0h+var_98], 0
0x14000b0c6  mov     [rbp+0C0h+var_90], 0
0x14000b0ce  mov     [rbp+0C0h+var_A4], r12d
0x14000b0d2  mov     [rbp+0C0h+var_A0], r13d
0x14000b0d6  cmp     ax, 17h
0x14000b0da  jz      short loc_14000B0E2
0x14000b0dc  cmp     ax, 2
0x14000b0e0  jnz     short loc_14000B0EC
0x14000b0e2  ror     r15w, 8
0x14000b0e7  mov     [rsi+2], r15w
0x14000b0ec  mov     rdx, rsi
0x14000b0ef  lea     rcx, [rbp+0C0h+var_88+4]
0x14000b0f3  call    OncRpcCopyAddress
0x14000b0f8  mov     edx, 68h ; 'h'
0x14000b0fd  mov     ecx, 42h ; 'B'
0x14000b102  mov     r8d, 6A52664Eh
0x14000b108  call    cs:__imp_ExAllocatePool2
0x14000b10f  nop     dword ptr [rax+rax+00h]
0x14000b114  mov     [rbp+0C0h+var_B0], rax
0x14000b118  test    rax, rax
0x14000b11b  jnz     loc_14000B542
0x14000b121  mov     ebx, 0C000009Ah
0x14000b126  jmp     loc_14000B61F
0x14000b12b  mov     [rsp+1C0h+var_170], 0
0x14000b134  xor     r15d, r15d
0x14000b137  mov     [rsp+1C0h+var_160], 0
0x14000b140  mov     r12b, 1
0x14000b143  mov     [rsp+1C0h+var_178], r15d
0x14000b148  mov     r11d, 18h
0x14000b14e  cmp     r15d, 2
0x14000b152  jnb     loc_14000B521
0x14000b158  test    r12b, r12b
0x14000b15b  jz      loc_14000B521
0x14000b161  mov     rcx, [rsp+1C0h+var_158]
0x14000b166  lea     rdx, [rsp+1C0h+var_148]
0x14000b16b  mov     r8d, r15d
0x14000b16e  call    NfsRdrpSetProtocol
0x14000b173  test    al, al
0x14000b175  jz      loc_14000B51C
0x14000b17b  mov     r9d, [rbp+0C0h+var_F4]
0x14000b17f  lea     rdx, [rbp+0C0h+var_D8+4]
0x14000b183  mov     r8d, [rbp+0C0h+var_F8]
0x14000b187  lea     rcx, [rsp+1C0h+var_170]
0x14000b18c  mov     [rsp+1C0h+var_188], 0
0x14000b195  mov     eax, 10h
0x14000b19a  cmp     di, 2
0x14000b19e  cmovnz  eax, r11d
0x14000b1a2  mov     [rsp+1C0h+var_190], eax
0x14000b1a6  mov     eax, [rbp+0C0h+var_F0]
0x14000b1a9  mov     [rsp+1C0h+var_198], 3
0x14000b1b1  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x14000b1b5  call    cs:__imp_OncRpcBuildCall
0x14000b1bc  nop     dword ptr [rax+rax+00h]
0x14000b1c1  test    eax, eax
0x14000b1c3  js      loc_14000B4E6
0x14000b1c9  mov     rcx, [rsp+1C0h+var_170]
0x14000b1ce  mov     edx, dword ptr [rsp+1C0h+var_148]
0x14000b1d2  mov     rax, [rcx+48h]
0x14000b1d6  test    rax, rax
0x14000b1d9  jz      short loc_14000B1DF
0x14000b1db  mov     rax, [rax+40h]
0x14000b1df  bswap   edx
0x14000b1e1  mov     [rax], edx
0x14000b1e3  mov     rax, [rcx+48h]
0x14000b1e7  mov     edx, dword ptr [rsp+1C0h+var_148+4]
0x14000b1eb  add     qword ptr [rax+40h], 4
0x14000b1f0  mov     rcx, [rsp+1C0h+var_170]
0x14000b1f5  mov     rax, [rcx+48h]
0x14000b1f9  test    rax, rax
0x14000b1fc  jz      short loc_14000B202
0x14000b1fe  mov     rax, [rax+40h]
0x14000b202  bswap   edx
0x14000b204  mov     [rax], edx
0x14000b206  mov     rax, [rcx+48h]
0x14000b20a  add     qword ptr [rax+40h], 4
0x14000b20f  cmp     di, 2
0x14000b213  jnz     short loc_14000B266
0x14000b215  mov     rcx, [rsp+1C0h+var_170]
0x14000b21a  mov     edx, dword ptr [rbp+0C0h+var_148+8]
0x14000b21d  mov     rax, [rcx+48h]
0x14000b221  test    rax, rax
0x14000b224  jz      short loc_14000B22A
0x14000b226  mov     rax, [rax+40h]
0x14000b22a  bswap   edx
0x14000b22c  mov     [rax], edx
0x14000b22e  mov     rax, [rcx+48h]
0x14000b232  add     qword ptr [rax+40h], 4
0x14000b237  mov     rdx, [rsp+1C0h+var_170]
0x14000b23c  mov     eax, dword ptr [rbp+0C0h+var_148+0Ch]
0x14000b23f  mov     rcx, [rdx+48h]
0x14000b243  test    rcx, rcx
0x14000b246  jnz     short loc_14000B255
0x14000b248  bswap   eax
0x14000b24a  mov     [rcx], eax
0x14000b24c  mov     rax, [rdx+48h]
0x14000b250  jmp     loc_14000B332
0x14000b255  mov     rcx, [rcx+40h]
0x14000b259  bswap   eax
0x14000b25b  mov     [rcx], eax
0x14000b25d  mov     rax, [rdx+48h]
0x14000b261  jmp     loc_14000B332
0x14000b266  cmp     dword ptr [rbp+0C0h+var_148+8], 6
0x14000b26a  lea     rax, aUdp6; "udp6"
0x14000b271  mov     r8, [rsp+1C0h+var_170]
0x14000b276  lea     rcx, aTcp6; "tcp6"
0x14000b27d  cmovnz  rcx, rax
0x14000b281  mov     rax, [r8+48h]
0x14000b285  test    rax, rax
0x14000b288  jz      short loc_14000B28E
0x14000b28a  mov     rax, [rax+40h]
0x14000b28e  mov     dword ptr [rax], 4000000h
0x14000b294  mov     rax, [r8+48h]
0x14000b298  add     qword ptr [rax+40h], 4
0x14000b29d  mov     rdx, [r8+48h]
0x14000b2a1  test    rdx, rdx
  ... truncated ...
```
