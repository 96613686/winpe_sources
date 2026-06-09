# MRxSmb2AssembleSmb

- ea: `0x14000ae40`
- end: `0x14000b404`
- name: `MRxSmb2AssembleSmb`
- size: `1476`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ae40`
- `0x14000b410`
- `0x14000bb90`
- `0x1400297fc`
- `0x140029840`
- `0x14002a6a8`
- `0x14002fc28`
- `0x14002fea0`
- `0x1400303ec`
- `0x140030470`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b174`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000b174`
- `rdbss!RxDiagnosticTrace` at `0x14000b092`
- `rdbss!RxDiagnosticTrace` at `0x14000b092`
- `mrxsmb!SmbCseGetMemoryDescriptors` at `0x14000b392`
- `mrxsmb!SmbCseGetMemoryDescriptors` at `0x14003918d`
- `mrxsmb!SmbCseGetMemoryDescriptors` at `0x14000b392`
- `mrxsmb!SmbCseGetMemoryDescriptors` at `0x14003918d`
- `mrxsmb!Smb2CommandToString` at `0x14000b062`
- `mrxsmb!Smb2CommandToString` at `0x14000b293`
- `mrxsmb!Smb2CommandToString` at `0x140039394`
- `mrxsmb!Smb2CommandToString` at `0x1400395ab`
- `mrxsmb!Smb2CommandToString` at `0x14000b062`
- `mrxsmb!Smb2CommandToString` at `0x14000b293`
- `mrxsmb!Smb2CommandToString` at `0x140039394`
- `mrxsmb!Smb2CommandToString` at `0x1400395ab`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000af96`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14000af96`

## pseudocode

```c
__int64 __fastcall MRxSmb2AssembleSmb(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebp
  bool v4; // r10
  int v5; // r9d
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v11; // rcx
  _QWORD *v12; // r15
  unsigned __int16 *v13; // r13
  __int64 v14; // r8
  int v15; // eax
  unsigned __int64 v16; // rcx
  __int64 v17; // rsi
  __int16 v18; // ax
  int v19; // ecx
  int v20; // eax
  unsigned int v21; // r15d
  __int64 v22; // r14
  unsigned __int16 *v23; // rax
  int v24; // ecx
  int v25; // ecx
  int v26; // ebx
  unsigned __int16 v27; // si
  unsigned __int16 v28; // bp
  int v29; // r14d
  __int64 v30; // r15
  __int64 v31; // rdi
  __int64 v32; // r12
  __int64 v33; // rax
  int v34; // edx
  int v35; // ecx
  _WORD *v36; // r14
  unsigned __int16 *v37; // r12
  int v38; // eax
  char *v39; // rdx
  char *v40; // rdx
  int v41; // ebp
  int v42; // eax
  int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // rcx
  unsigned __int16 v46; // dx
  __int64 v47; // rax
  __int64 v48; // r8
  __int128 *v49; // rax
  __int64 v50; // r13
  __int64 v51; // rsi
  __int64 v52; // r14
  int v53; // ebp
  __int64 v54; // r15
  __int64 v55; // r8
  __int64 v56; // r12
  __int64 v57; // rdi
  __int64 v58; // rax
  int v59; // r8d
  int v60; // edx
  char v61; // cl
  __int64 v62; // r8
  __int64 v63; // r8
  __int128 *v64; // rax
  __int64 v65; // r13
  __int64 v66; // rsi
  __int64 v67; // r14
  int v68; // ebp
  __int64 v69; // r15
  __int64 v70; // rdi
  __int64 v71; // r8
  __int64 v72; // r12
  __int64 v73; // rax
  int v74; // r8d
  int v75; // edx
  char v76; // cl
  int v77; // [rsp+30h] [rbp-1C8h]
  int v78; // [rsp+38h] [rbp-1C0h]
  char v79; // [rsp+A0h] [rbp-158h]
  char v80; // [rsp+A0h] [rbp-158h]
  bool v81; // [rsp+D0h] [rbp-128h]
  int MemoryDescriptors; // [rsp+D4h] [rbp-124h]
  __int16 v83; // [rsp+D8h] [rbp-120h]
  int v84; // [rsp+D8h] [rbp-120h]
  __int16 v85; // [rsp+DCh] [rbp-11Ch]
  __int16 v86; // [rsp+DCh] [rbp-11Ch]
  int v87; // [rsp+E0h] [rbp-118h]
  __int16 v88; // [rsp+E0h] [rbp-118h]
  _QWORD *v89; // [rsp+E8h] [rbp-110h]
  _DWORD *v90; // [rsp+F0h] [rbp-108h]
  int v91; // [rsp+F8h] [rbp-100h]
  __int64 v92; // [rsp+100h] [rbp-F8h]
  __int64 v93; // [rsp+100h] [rbp-F8h]
  __int64 v94; // [rsp+108h] [rbp-F0h]
  __int64 v95; // [rsp+108h] [rbp-F0h]
  __int64 v96; // [rsp+110h] [rbp-E8h]
  char v97; // [rsp+110h] [rbp-E8h]
  __int64 v98; // [rsp+118h] [rbp-E0h]
  __int64 v99; // [rsp+120h] [rbp-D8h]
  __int128 v100; // [rsp+130h] [rbp-C8h] BYREF
  __int128 v101; // [rsp+140h] [rbp-B8h] BYREF
  __int128 v102; // [rsp+150h] [rbp-A8h] BYREF
  __int128 v103; // [rsp+160h] [rbp-98h] BYREF
  char v104[16]; // [rsp+170h] [rbp-88h] BYREF
  char v105[16]; // [rsp+180h] [rbp-78h] BYREF
  char v106[16]; // [rsp+190h] [rbp-68h] BYREF
  char v107[24]; // [rsp+1A0h] [rbp-58h] BYREF
  unsigned int v109; // [rsp+208h] [rbp+10h]
  int v110; // [rsp+210h] [rbp+18h] BYREF
  int v111; // [rsp+218h] [rbp+20h]

  v3 = 0;
  v4 = 0;
  MemoryDescriptors = 0;
  v5 = 0;
  v109 = 0;
  v6 = a1;
  v81 = 0;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 56LL);
  v8 = 1;
  v111 = 0;
  v99 = v7;
  if ( v7 )
  {
    v4 = (*(_BYTE *)(v7 + 68) & 0x20) != 0;
    v81 = v4;
  }
  v9 = a1;
  while ( 1 )
  {
    if ( !v9 )
      return v3;
    v11 = *(_QWORD *)(v9 + 96);
    v12 = *(_QWORD **)(v9 + 56);
    v89 = v12;
    if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    {
      v13 = *(unsigned __int16 **)(v11 + 24);
      v90 = v13;
    }
    else
    {
      v23 = (unsigned __int16 *)MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000010u);
      v5 = v111;
      v13 = v23;
      v4 = v81;
      v90 = v23;
    }
    if ( !v13 )
    {
      MemoryDescriptors = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qqqL(WPP_GLOBAL_Control->AttachedDevice, v8, a3, v12[6], v12, v9, v77, v78);
        v5 = v111;
        v4 = v81;
      }
      __debugbreak();
    }
    *(_WORD *)(v9 + 2) = v13[6];
    if ( (*(_DWORD *)(v9 + 4) & 0x10) == 0 )
      *((_QWORD *)v13 + 3) = *(_QWORD *)(v9 + 40);
    if ( *(_QWORD *)(v9 + 760) )
      break;
LABEL_12:
    v14 = 0;
    if ( v7 )
    {
      v8 = *(_QWORD *)(v9 + 64);
      if ( v8 != v7 + 48 )
        v14 = v8 - 64;
      v98 = v14;
      if ( v14 )
      {
        v15 = *(_DWORD *)(v9 + 728);
        goto LABEL_15;
      }
    }
    else
    {
      v98 = 0;
    }
    v15 = 0;
LABEL_15:
    *((_DWORD *)v13 + 5) = v15;
    if ( v9 != v6 && v4 )
      *((_DWORD *)v13 + 4) |= 4u;
    v13[3] = *(_WORD *)(v9 + 80);
    v111 = *(_DWORD *)(v9 + 732) + v5;
    v16 = (unsigned __int16)v111;
    if ( v14 )
      LOWORD(v16) = 0;
    v13[7] = v16;
    if ( (*(_DWORD *)(v6 + 4) & 0x1000) != 0 )
    {
      MemoryDescriptors = Smb2ComputeOutgoingSignature(v9, v8);
      if ( MemoryDescriptors < 0 )
      {
        v16 = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids,
            v12,
            v9,
            MemoryDescriptors);
        }
        MemoryDescriptors = 0;
      }
    }
    v17 = v12[10];
    if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v16) + 64) & 8) != 0 && v17 )
    {
      v45 = v13[6];
      if ( (unsigned int)v45 > 0x14 )
        v45 = 20;
      _InterlockedAdd64((volatile signed __int64 *)(v17 + 720), *(unsigned int *)(v6 + 728));
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 4 * v45 + 736));
    }
    v18 = *(_WORD *)(v9 + 2);
    switch ( v18 )
    {
      case 17:
        goto LABEL_28;
      case 14:
        v20 = *(unsigned __int16 *)(v9 + 864);
        goto LABEL_30;
      case 11:
        v20 = *(_DWORD *)(v9 + 864);
LABEL_30:
        v110 = v20;
        if ( v20 == -1 )
          goto LABEL_24;
        goto LABEL_31;
    }
    if ( v18 != 16 )
      goto LABEL_24;
LABEL_28:
    v19 = *(_DWORD *)(v9 + 864);
    switch ( HIWORD(v19) )
    {
      case 1:
        v20 = (unsigned __int16)v19;
        goto LABEL_30;
      case 3:
        v110 = 0;
        break;
      case 4:
        v110 = 32;
        break;
      default:
LABEL_24:
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_33;
        }
        v62 = v12[12];
        v110 = *(_DWORD *)(v6 + 4);
        v97 = v62;
        v102 = *(_OWORD *)WppSockAddr(v106, *(_QWORD *)(v62 + 392) + 428LL);
        v64 = (__int128 *)WppSockAddr(v107, *(_QWORD *)(v63 + 392) + 400LL);
        v65 = v12[9];
        v66 = v12[11];
        v67 = v12[10];
        v68 = v90[9];
        v69 = *((_QWORD *)v90 + 5);
        v103 = *v64;
        v70 = *(_QWORD *)(v65 + 24);
        v72 = *(_QWORD *)(v71 + 392);
        v95 = v89[6];
        v88 = *((_WORD *)v90 + 7);
        v86 = *((_WORD *)v90 + 3);
        v93 = *((_QWORD *)v90 + 3);
        v84 = *(_DWORD *)(v9 + 728);
        v73 = Smb2CommandToString(*((unsigned __int16 *)v90 + 6));
        v74 = 67;
        v75 = 69;
        v80 = v69;
        if ( (v110 & 0x10000) == 0 )
          v74 = 32;
        v21 = v109;
        v76 = 83;
        if ( (v110 & 0x8000) == 0 )
          v75 = 32;
        if ( (v110 & 0x1000) == 0 )
          v76 = 32;
        WPP_SF_dd_SOCKADDR__SOCKADDR_cccsDiDDqqqqqiqLqq(
          WPP_GLOBAL_Control->AttachedDevice,
          v75,
          v74,
          *(unsigned __int8 *)(v70 + 1312),
          v109,
          (__int64)&v103,
          (__int64)&v102,
          v76,
          v75,
          v74,
          v73,
          v84,
          v93,
          v86,
          v88,
          (char)v89,
          v9,
          v95,
          v72,
          v97,
          v80,
          v67,
          v68,
          v66,
          v65);
        v13 = (unsigned __int16 *)v90;
        goto LABEL_34;
    }
LABEL_31:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
LABEL_33:
      v21 = v109;
      goto LABEL_34;
    }
    v91 = *(_DWORD *)(v6 + 4);
    v92 = v12[12];
    v100 = *(_OWORD *)WppSockAddr(v104, *(_QWORD *)(v92 + 392) + 428LL);
    v49 = (__int128 *)WppSockAddr(v105, *(_QWORD *)(v48 + 392) + 400LL);
    v50 = v12[9];
    v51 = v12[11];
    v52 = v12[10];
    v53 = v90[9];
    v54 = *((_QWORD *)v90 + 5);
    v101 = *v49;
    v56 = *(_QWORD *)(v55 + 392);
    v57 = *(_QWORD *)(v50 + 24);
    v94 = v89[6];
    v83 = *((_WORD *)v90 + 7);
    v85 = *((_WORD *)v90 + 3);
    v96 = *((_QWORD *)v90 + 3);
    v87 = *(_DWORD *)(v9 + 728);
    v58 = Smb2CommandToString(*((unsigned __int16 *)v90 + 6));
    v59 = 67;
    v60 = 69;
    v61 = 83;
    if ( (v91 & 0x10000) == 0 )
      v59 = 32;
    if ( (v91 & 0x8000) == 0 )
      v60 = 32;
    if ( (v91 & 0x1000) == 0 )
      v61 = 32;
    v79 = v54;
    v21 = v109;
    WPP_SF_dd_SOCKADDR__SOCKADDR_cccsDiDDqqqqqiqLqql(
      WPP_GLOBAL_Control->AttachedDevice,
      v60,
      v59,
      *(unsigned __int8 *)(v57 + 1312),
      v109,
      (__int64)&v101,
      (__int64)&v100,
      v61,
      v60,
      v59,
      v58,
      v87,
      v96,
      v85,
      v83,
      (char)v89,
      v9,
      v94,
      v56,
      v92,
      v79,
      v52,
      v53,
      v51,
      v50,
      v110);
    v13 = (unsigned __int16 *)v90;
LABEL_34:
    v22 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v89[12] + 392LL) + 512LL) + 16LL);
    v78 = v13[7];
    v77 = v13[3];
    Smb2CommandToString(v13[6]);
    RxDiagnosticTrace(v22, 1, "SEND[%02x]: [%s] Mid (%I64x) MidCharge %lx Creds %lx", v21);
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100) != 0 )
    {
      v26 = *(_DWORD *)(v9 + 728);
      v27 = v13[7];
      v28 = v13[3];
      v29 = *((_DWORD *)v13 + 9);
      v30 = *((_QWORD *)v13 + 5);
      v31 = *(_QWORD *)(v89[12] + 392LL);
      v32 = *((_QWORD *)v13 + 3);
      v33 = Smb2CommandToString(v13[6]);
      McTemplateK0qsxxqhhqp_EtwWriteTransfer(v35, v34, (_DWORD)v89 + 312, v109, v33, v32, v30, v29, v28, v27, v26, v31);
    }
    v9 = v98;
    v8 = 1;
    ++v109;
    v6 = a1;
    v7 = v99;
    v5 = v111;
    v3 = MemoryDescriptors;
    v4 = v81;
  }
  v24 = v13[6];
  v110 = 0;
  v25 = v24 - 8;
  if ( v25 )
  {
    if ( v25 != 1 )
      return 3221225701LL;
    v36 = v13 + 53;
    if ( *((_DWORD *)v13 + 24) == 3 )
    {
      v37 = (unsigned __int16 *)((char *)v13 + v13[52]);
      v38 = v37[1];
      v39 = (char *)v37 + *v37;
    }
    else
    {
      v37 = 0;
      v38 = (unsigned __int16)*v36;
      v39 = (char *)v13 + v13[52];
    }
    v110 = v38;
    MemoryDescriptors = SmbCseGetMemoryDescriptors(v6, v39, &v110);
    v41 = MemoryDescriptors;
    if ( MemoryDescriptors >= 0 )
    {
      if ( *((_DWORD *)v13 + 24) == 3 )
      {
        v46 = v110;
        *v36 += v110 - v37[1];
        v37[1] = v46;
      }
      else
      {
        *v36 = v110;
      }
      v8 = (unsigned __int16)*v36 + (unsigned int)v13[52];
      v47 = *(_QWORD *)(v9 + 96);
      if ( *(_DWORD *)(v47 + 40) < (unsigned int)v8 )
        __int2c();
      if ( *(_DWORD *)(v9 + 728) < (unsigned int)v8 )
        __int2c();
      *(_DWORD *)(v9 + 728) = v8;
      *(_DWORD *)(v47 + 40) = v8;
      goto LABEL_81;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids,
        v12,
        MemoryDescriptors);
    }
  }
  else
  {
    v40 = (char *)v13 + v13[54];
    v110 = v13[55];
    MemoryDescriptors = SmbCseGetMemoryDescriptors(v6, v40, &v110);
    v41 = MemoryDescriptors;
    if ( MemoryDescriptors >= 0 )
    {
      v42 = v110;
      v13[55] = v110;
      v43 = v42 + 112;
      v44 = *(_QWORD *)(v9 + 96);
      *(_DWORD *)(v9 + 728) = v43;
      *(_DWORD *)(v44 + 40) = v43;
LABEL_81:
      v5 = v111;
      v4 = v81;
      goto LABEL_12;
    }
  }
  if ( v41 != -2147483643 )
    goto LABEL_81;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids, v12);
  }
  return 3221225701LL;
}

```

## disassembly

```asm
0x14000ae40  mov     [rsp+arg_0], rcx
0x14000ae45  push    rbx
0x14000ae46  push    rbp
0x14000ae47  push    rsi
0x14000ae48  push    rdi
0x14000ae49  push    r12
0x14000ae4b  push    r14
0x14000ae4d  sub     rsp, 1C8h
0x14000ae54  mov     rax, [rcx+38h]
0x14000ae58  xor     ebp, ebp
0x14000ae5a  xor     r10b, r10b
0x14000ae5d  mov     [rsp+1F8h+var_124], ebp
0x14000ae64  xor     r9d, r9d
0x14000ae67  mov     [rsp+1F8h+arg_8], ebp
0x14000ae6e  mov     rdi, rcx
0x14000ae71  mov     [rsp+1F8h+var_128], r10d
0x14000ae79  mov     rsi, [rax+38h]
0x14000ae7d  mov     edx, 1
0x14000ae82  mov     [rsp+1F8h+arg_18], r9d
0x14000ae8a  mov     [rsp+1F8h+var_D8], rsi
0x14000ae92  test    rsi, rsi
0x14000ae95  jnz     loc_14000B21C
0x14000ae9b  mov     [rsp+1F8h+var_38], r13
0x14000aea3  mov     rbx, rcx
0x14000aea6  mov     [rsp+1F8h+var_40], r15
0x14000aeae  mov     r12d, 20h ; ' '
0x14000aeb4  lea     r14, WPP_GLOBAL_Control
0x14000aebb  test    rbx, rbx
0x14000aebe  jnz     short loc_14000AEE3
0x14000aec0  mov     eax, ebp
0x14000aec2  mov     r15, [rsp+1F8h+var_40]
0x14000aeca  mov     r13, [rsp+1F8h+var_38]
0x14000aed2  add     rsp, 1C8h
0x14000aed9  pop     r14
0x14000aedb  pop     r12
0x14000aedd  pop     rdi
0x14000aede  pop     rsi
0x14000aedf  pop     rbp
0x14000aee0  pop     rbx
0x14000aee1  retn
0x14000aee3  mov     rcx, [rbx+60h]; MemoryDescriptorList
0x14000aee7  mov     r15, [rbx+38h]
0x14000aeeb  mov     [rsp+1F8h+var_110], r15
0x14000aef3  test    byte ptr [rcx+0Ah], 5
0x14000aef7  jz      loc_14000B15C
0x14000aefd  mov     r13, [rcx+18h]
0x14000af01  mov     [rsp+1F8h+var_108], r13
0x14000af09  test    r13, r13
0x14000af0c  jz      loc_14000B2ED
0x14000af12  movzx   eax, word ptr [r13+0Ch]
0x14000af17  mov     [rbx+2], ax
0x14000af1b  mov     eax, [rbx+4]
0x14000af1e  test    al, 10h
0x14000af20  jnz     short loc_14000AF2A
0x14000af22  mov     rax, [rbx+28h]
0x14000af26  mov     [r13+18h], rax
0x14000af2a  cmp     qword ptr [rbx+2F8h], 0
0x14000af32  jnz     loc_14000B1F0
0x14000af38  xor     r8d, r8d
0x14000af3b  test    rsi, rsi
0x14000af3e  jnz     loc_14000B1A0
0x14000af44  mov     [rsp+1F8h+var_E0], r8
0x14000af4c  xor     eax, eax
0x14000af4e  mov     [r13+14h], eax
0x14000af52  cmp     rbx, rdi
0x14000af55  jnz     loc_14000B235
0x14000af5b  movzx   eax, word ptr [rbx+50h]
0x14000af5f  mov     [r13+6], ax
0x14000af64  xor     eax, eax
0x14000af66  add     r9d, [rbx+2DCh]
0x14000af6d  test    r8, r8
0x14000af70  mov     [rsp+1F8h+arg_18], r9d
0x14000af78  movzx   ecx, r9w
0x14000af7c  cmovnz  cx, ax
0x14000af80  mov     [r13+0Eh], cx
0x14000af85  test    dword ptr [rdi+4], 1000h
0x14000af8c  jnz     loc_14000B0EB
0x14000af92  mov     rsi, [r15+50h]
0x14000af96  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14000af9d  nop     dword ptr [rax+rax+00h]
0x14000afa2  test    byte ptr [rax+40h], 8
0x14000afa6  jnz     loc_14000B3D0
0x14000afac  movzx   eax, word ptr [rbx+2]
0x14000afb0  cmp     ax, 11h
0x14000afb4  jz      short loc_14000AFEE
0x14000afb6  cmp     ax, 0Eh
0x14000afba  jz      loc_14000B150
0x14000afc0  cmp     ax, 0Bh
0x14000afc4  jz      loc_14000B1CF
0x14000afca  cmp     ax, 10h
0x14000afce  jz      short loc_14000AFEE
0x14000afd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afd7  cmp     rcx, r14
0x14000afda  jz      short loc_14000B029
0x14000afdc  mov     eax, [rcx+2Ch]
0x14000afdf  test    al, 4
0x14000afe1  jz      short loc_14000B029
0x14000afe3  cmp     byte ptr [rcx+29h], 2
0x14000afe7  jb      short loc_14000B029
0x14000afe9  jmp     loc_1400394DC
0x14000afee  mov     ecx, [rbx+360h]
0x14000aff4  mov     eax, ecx
0x14000aff6  shr     eax, 10h
0x14000aff9  cmp     ax, 1
0x14000affd  jnz     loc_14000B1DA
0x14000b003  movzx   eax, cx
0x14000b006  mov     [rsp+1F8h+arg_10], eax
0x14000b00d  cmp     eax, 0FFFFFFFFh
0x14000b010  jz      short loc_14000AFD0
0x14000b012  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b019  cmp     rcx, r14
0x14000b01c  jz      short loc_14000B029
0x14000b01e  mov     eax, [rcx+2Ch]
0x14000b021  test    al, 4
0x14000b023  jnz     loc_1400392BB
0x14000b029  mov     r15d, [rsp+1F8h+arg_8]
0x14000b031  mov     rax, [rsp+1F8h+var_110]
0x14000b039  movzx   esi, word ptr [r13+0Eh]
0x14000b03e  movzx   ebp, word ptr [r13+6]
0x14000b043  mov     rdi, [r13+18h]
0x14000b047  mov     rax, [rax+60h]
0x14000b04b  mov     rax, [rax+188h]
0x14000b052  mov     rcx, [rax+200h]
0x14000b059  mov     r14, [rcx+10h]
0x14000b05d  movzx   ecx, word ptr [r13+0Ch]
0x14000b062  call    cs:__imp_Smb2CommandToString
0x14000b069  nop     dword ptr [rax+rax+00h]
0x14000b06e  mov     [rsp+1F8h+var_1C0], esi
0x14000b072  lea     r8, aSend02xSMidI64; "SEND[%02x]: [%s] Mid (%I64x) MidCharge "...
0x14000b079  mov     dword ptr [rsp+1F8h+var_1C8], ebp
0x14000b07d  mov     r9d, r15d
0x14000b080  mov     qword ptr [rsp+1F8h+Priority], rdi
0x14000b085  mov     edx, 1
0x14000b08a  mov     rcx, r14
0x14000b08d  mov     qword ptr [rsp+1F8h+BugCheckOnFailure], rax
0x14000b092  call    cs:__imp_RxDiagnosticTrace
0x14000b099  nop     dword ptr [rax+rax+00h]
0x14000b09e  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 1
0x14000b0a5  jnz     loc_14000B25F
0x14000b0ab  mov     rbx, [rsp+1F8h+var_E0]
0x14000b0b3  mov     edx, 1
0x14000b0b8  inc     [rsp+1F8h+arg_8]
0x14000b0bf  mov     rdi, [rsp+1F8h+arg_0]
0x14000b0c7  mov     rsi, [rsp+1F8h+var_D8]
0x14000b0cf  mov     r9d, [rsp+1F8h+arg_18]
0x14000b0d7  mov     ebp, [rsp+1F8h+var_124]
0x14000b0de  mov     r10d, [rsp+1F8h+var_128]
0x14000b0e6  jmp     loc_14000AEB4
0x14000b0eb  mov     rcx, rbx
0x14000b0ee  call    Smb2ComputeOutgoingSignature
0x14000b0f3  mov     [rsp+1F8h+var_124], eax
0x14000b0fa  mov     ebp, eax
0x14000b0fc  test    eax, eax
0x14000b0fe  jns     loc_14000AF92
0x14000b104  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b10b  cmp     rcx, r14
0x14000b10e  jz      loc_1400392AD
0x14000b114  mov     eax, [rcx+2Ch]
0x14000b117  test    al, 1
0x14000b119  jz      loc_1400392AD
0x14000b11f  cmp     byte ptr [rcx+29h], 1
0x14000b123  jb      loc_1400392AD
0x14000b129  mov     rcx, [rcx+18h]
0x14000b12d  lea     r8, WPP_05786ea0ac0c32530d7d4a16350fe9c7_Traceguids
0x14000b134  mov     edx, 23h ; '#'
0x14000b139  mov     [rsp+1F8h+Priority], ebp
0x14000b13d  mov     r9, r15
0x14000b140  mov     qword ptr [rsp+1F8h+BugCheckOnFailure], rbx
0x14000b145  call    WPP_SF_qqD
0x14000b14a  nop
0x14000b14b  jmp     loc_1400392AD
0x14000b150  movzx   eax, word ptr [rbx+360h]
0x14000b157  jmp     loc_14000B006
0x14000b15c  mov     r8d, edx; CacheType
0x14000b15f  mov     [rsp+1F8h+Priority], 40000010h; Priority
0x14000b167  xor     edx, edx; AccessMode
0x14000b169  mov     [rsp+1F8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000b171  xor     r9d, r9d; RequestedAddress
0x14000b174  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000b17b  nop     dword ptr [rax+rax+00h]
0x14000b180  mov     r9d, [rsp+1F8h+arg_18]
0x14000b188  mov     r13, rax
0x14000b18b  mov     r10d, [rsp+1F8h+var_128]
0x14000b193  mov     [rsp+1F8h+var_108], rax
0x14000b19b  jmp     loc_14000AF09
0x14000b1a0  mov     rdx, [rbx+40h]
0x14000b1a4  lea     rcx, [rsi+30h]
0x14000b1a8  cmp     rdx, rcx
0x14000b1ab  lea     rax, [rdx-40h]
0x14000b1af  cmovnz  r8, rax
0x14000b1b3  mov     [rsp+1F8h+var_E0], r8
0x14000b1bb  test    r8, r8
0x14000b1be  jz      loc_14000AF4C
0x14000b1c4  mov     eax, [rbx+2D8h]
0x14000b1ca  jmp     loc_14000AF4E
0x14000b1cf  mov     eax, [rbx+360h]
0x14000b1d5  jmp     loc_14000B006
0x14000b1da  cmp     ax, 3
0x14000b1de  jnz     short loc_14000B248
0x14000b1e0  mov     [rsp+1F8h+arg_10], 0
0x14000b1eb  jmp     loc_14000B012
0x14000b1f0  movzx   ecx, word ptr [r13+0Ch]
0x14000b1f5  mov     [rsp+1F8h+arg_10], 0
0x14000b200  sub     ecx, 8
0x14000b203  jz      loc_14000B373
0x14000b209  cmp     ecx, 1
0x14000b20c  jz      loc_14000B349
0x14000b212  mov     eax, 0C00000E5h
0x14000b217  jmp     loc_14000AEC2
0x14000b21c  test    byte ptr [rsi+44h], 20h
0x14000b220  movzx   r10d, r10b
0x14000b224  cmovnz  r10d, edx
0x14000b228  mov     [rsp+1F8h+var_128], r10d
0x14000b230  jmp     loc_14000AE9B
0x14000b235  test    r10b, r10b
0x14000b238  jz      loc_14000AF5B
0x14000b23e  or      dword ptr [r13+10h], 4
0x14000b243  jmp     loc_14000AF5B
0x14000b248  cmp     ax, 4
0x14000b24c  jnz     loc_14000AFD0
0x14000b252  mov     [rsp+1F8h+arg_10], r12d
0x14000b25a  jmp     loc_14000B012
0x14000b25f  mov     rax, [rsp+1F8h+var_110]
0x14000b267  movzx   ecx, word ptr [r13+0Ch]
0x14000b26c  mov     ebx, [rbx+2D8h]
0x14000b272  movzx   esi, word ptr [r13+0Eh]
0x14000b277  mov     rax, [rax+60h]
0x14000b27b  movzx   ebp, word ptr [r13+6]
0x14000b280  mov     r14d, [r13+24h]
0x14000b284  mov     r15, [r13+28h]
0x14000b288  mov     rdi, [rax+188h]
0x14000b28f  mov     r12, [r13+18h]
0x14000b293  call    cs:__imp_Smb2CommandToString
0x14000b29a  nop     dword ptr [rax+rax+00h]
0x14000b29f  mov     r8, [rsp+1F8h+var_110]
0x14000b2a7  mov     r9d, [rsp+1F8h+arg_8]
0x14000b2af  add     r8, 138h
0x14000b2b6  mov     [rsp+1F8h+var_1A0], rdi
0x14000b2bb  mov     dword ptr [rsp+1F8h+var_1A8], ebx
0x14000b2bf  mov     [rsp+1F8h+var_1B0], si
0x14000b2c4  mov     [rsp+1F8h+var_1B8], bp
0x14000b2c9  mov     [rsp+1F8h+var_1C0], r14d
0x14000b2ce  mov     [rsp+1F8h+var_1C8], r15
0x14000b2d3  mov     qword ptr [rsp+1F8h+Priority], r12
0x14000b2d8  mov     qword ptr [rsp+1F8h+BugCheckOnFailure], rax
0x14000b2dd  call    McTemplateK0qsxxqhhqp_EtwWriteTransfer
0x14000b2e2  mov     r12d, 20h ; ' '
0x14000b2e8  jmp     loc_14000B0AB
0x14000b2ed  mov     [rsp+1F8h+var_124], 0C000009Ah
0x14000b2f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b2ff  cmp     rcx, r14
0x14000b302  jz      loc_140039166
0x14000b308  mov     eax, [rcx+2Ch]
0x14000b30b  test    al, 1
0x14000b30d  jz      loc_140039166
0x14000b313  cmp     byte ptr [rcx+29h], 1
0x14000b317  jb      loc_140039166
0x14000b31d  mov     r9, [r15+30h]
0x14000b321  mov     rcx, [rcx+18h]
0x14000b325  mov     qword ptr [rsp+1F8h+Priority], rbx
0x14000b32a  mov     qword ptr [rsp+1F8h+BugCheckOnFailure], r15
0x14000b32f  call    WPP_SF_qqqL
0x14000b334  mov     r9d, [rsp+1F8h+arg_18]
0x14000b33c  mov     r10d, [rsp+1F8h+var_128]
0x14000b344  jmp     loc_140039166
0x14000b349  cmp     dword ptr [r13+60h], 3
0x14000b34e  lea     r14, [r13+6Ah]
0x14000b352  jnz     loc_14003916C
0x14000b358  movzx   r12d, word ptr [r13+68h]
0x14000b35d  add     r12, r13
0x14000b360  movzx   edx, word ptr [r12]
0x14000b365  movzx   eax, word ptr [r12+2]
0x14000b36b  add     rdx, r12
0x14000b36e  jmp     loc_14003917B
0x14000b373  movzx   edx, word ptr [r13+6Ch]
0x14000b378  lea     r8, [rsp+1F8h+arg_10]
0x14000b380  movzx   eax, word ptr [r13+6Eh]
0x14000b385  add     rdx, r13
0x14000b388  mov     rcx, rdi
0x14000b38b  mov     [rsp+1F8h+arg_10], eax
0x14000b392  call    cs:__imp_SmbCseGetMemoryDescriptors
0x14000b399  nop     dword ptr [rax+rax+00h]
0x14000b39e  mov     [rsp+1F8h+var_124], eax
0x14000b3a5  mov     ebp, eax
0x14000b3a7  test    eax, eax
0x14000b3a9  js      loc_140039262
0x14000b3af  mov     eax, [rsp+1F8h+arg_10]
0x14000b3b6  mov     [r13+6Eh], ax
0x14000b3bb  lea     ecx, [rax+70h]
0x14000b3be  mov     rax, [rbx+60h]
0x14000b3c2  mov     [rbx+2D8h], ecx
0x14000b3c8  mov     [rax+28h], ecx
0x14000b3cb  jmp     loc_14003920B
0x14000b3d0  test    rsi, rsi
0x14000b3d3  jz      loc_14000AFAC
0x14000b3d9  movzx   ecx, word ptr [r13+0Ch]
0x14000b3de  mov     eax, 14h
0x14000b3e3  cmp     ecx, 14h
0x14000b3e6  cmova   ecx, eax
0x14000b3e9  mov     eax, [rdi+2D8h]
  ... truncated ...
```
