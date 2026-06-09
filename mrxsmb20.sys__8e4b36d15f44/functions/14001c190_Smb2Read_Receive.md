# Smb2Read_Receive

- ea: `0x14001c190`
- end: `0x14001c723`
- name: `Smb2Read_Receive`
- size: `1427`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000fa00`
- `0x140015570`
- `0x14001c010`
- `0x14001c190`
- `0x14001cf70`
- `0x140027fc0`
- `0x1400297fc`
- `0x140029840`
- `0x14002a9ac`
- `0x14002da60`
- `0x140036950`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14003bd96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003bd96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bd16`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003bd16`
- `mrxsmb!RDR_PERF_FREE` at `0x14001c279`
- `mrxsmb!RDR_PERF_FREE` at `0x14001c41c`
- `mrxsmb!RDR_PERF_FREE` at `0x14001c279`
- `mrxsmb!RDR_PERF_FREE` at `0x14001c41c`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x14001c26a`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x14001c40d`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x14001c26a`
- `mrxsmb!RDR_PERF_OUTPUT_ETW` at `0x14001c40d`
- `mrxsmb!RDR_PERF_EXIT` at `0x14001c25b`
- `mrxsmb!RDR_PERF_EXIT` at `0x14001c3fe`
- `mrxsmb!RDR_PERF_EXIT` at `0x14001c25b`
- `mrxsmb!RDR_PERF_EXIT` at `0x14001c3fe`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001c1fc`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001c1fc`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001c371`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14001c371`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001c458`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001c458`
- `mrxsmb!SmbCeContinueExchange` at `0x14001c712`
- `mrxsmb!SmbCeContinueExchange` at `0x14001c712`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14001c30a`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x14001c30a`

## pseudocode

```c
__int64 __fastcall Smb2Read_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7,
        _DWORD *a8)
{
  __int64 v8; // rbx
  int HandleRdmaDdpReceive; // edi
  __int64 v10; // rbp
  __int64 v11; // r12
  __int64 v13; // r8
  __int64 v15; // rax
  unsigned int v16; // r15d
  __int64 v17; // r13
  unsigned int v18; // ecx
  unsigned int v19; // r8d
  __int64 v20; // rcx
  _DWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  unsigned int v24; // ecx
  unsigned int v26; // r15d
  unsigned int v27; // r8d
  unsigned int *v28; // r8
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  PDEVICE_OBJECT v31; // rcx
  __int64 v32; // rdx
  unsigned __int64 v33; // rcx
  KIRQL v34; // al
  __int64 v35; // r8
  KIRQL v36; // r11
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // r10
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // [rsp+80h] [rbp+8h] BYREF
  __int64 v43; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int64 v44; // [rsp+90h] [rbp+18h]
  unsigned int v45; // [rsp+98h] [rbp+20h]

  v45 = a4;
  v8 = a2 + 880;
  HandleRdmaDdpReceive = *(_DWORD *)(a3 + 16);
  v10 = a2;
  v11 = *(_QWORD *)(a2 + 760);
  LOBYTE(a2) = 35;
  v13 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL);
  LODWORD(v42) = HIDWORD(KeGetPcr()[1].LockArray);
  LODWORD(v43) = *(_DWORD *)(v13 + 1488);
  v44 = *(_QWORD *)(v13 + 1480);
  RDR_PERF_ENTER(v8, a2);
  if ( (int)(HandleRdmaDdpReceive + 0x80000000) >= 0 && HandleRdmaDdpReceive != -2147483643 )
  {
    v15 = *(_QWORD *)(a1 + 72);
    v43 = 0;
    LODWORD(v42) = 0;
    if ( *(_BYTE *)(*(_QWORD *)(v15 + 24) + 1313LL) )
    {
      v26 = a5;
      if ( a4 != a5 )
      {
        v16 = Smb2BufferErrorResponse(v10, a7, a4, a5, a6);
        goto LABEL_6;
      }
      if ( *(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL)
        && (int)Smb2QueryErrorDataFromResponse(a7 + 64, a4 - 64, 1164730963, &v43, (unsigned int *)&v42) >= 0
        && v43
        && (unsigned int)v42 >= 8 )
      {
        StRtlIoStorInfoSetSenseCode(
          *(_QWORD *)(*(_QWORD *)(a1 + 48) + 40LL),
          *(unsigned __int8 *)(v43 + 4),
          *(unsigned __int8 *)(v43 + 5),
          *(unsigned __int8 *)(v43 + 6));
      }
      *a6 = v26;
    }
    else
    {
      *a6 = a5;
    }
    v16 = 0;
LABEL_6:
    RDR_PERF_EXIT(v8);
    RDR_PERF_OUTPUT_ETW(v8);
    RDR_PERF_FREE(v8);
    goto LABEL_32;
  }
  v16 = 0;
  if ( a4 < 0x50 )
  {
    HandleRdmaDdpReceive = -1073741629;
    *a6 = a5;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 11);
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_6;
    }
    v32 = 37;
LABEL_79:
    WPP_SF_q(v31->AttachedDevice, v32, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1);
    goto LABEL_6;
  }
  v17 = a7 + 64;
  if ( *(_WORD *)(a7 + 64) != 17 )
  {
    *a6 = a5;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 12);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids);
    }
    goto LABEL_90;
  }
  v18 = *(unsigned __int8 *)(a7 + 66);
  if ( v18 > a5 || (v19 = *(_DWORD *)(a7 + 68), v19 + v18 > a5) )
  {
    *a6 = a5;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 13);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_90;
    }
    v30 = 39;
    goto LABEL_89;
  }
  if ( (unsigned __int8)v18 < 0x50u && v19 )
  {
    *a6 = a5;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 14);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_90;
    }
    v30 = 40;
LABEL_89:
    WPP_SF_q(v29->AttachedDevice, v30, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1);
LABEL_90:
    HandleRdmaDdpReceive = -1073741629;
    goto LABEL_6;
  }
  if ( !v11 )
  {
    if ( v19 <= *(_DWORD *)(v10 + 744) )
      goto LABEL_14;
    goto LABEL_91;
  }
  if ( *(_DWORD *)(a7 + 72) > *(_DWORD *)(v10 + 776) )
  {
LABEL_91:
    HandleRdmaDdpReceive = -1073741629;
    *a6 = a5;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 15);
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_6;
    }
    v32 = 41;
    goto LABEL_79;
  }
LABEL_14:
  if ( (unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(a1 + 72), 3, 1, 1) )
  {
    v27 = *(_DWORD *)(v17 + 12);
    if ( v27 >= 2 )
    {
      HandleRdmaDdpReceive = -1073741629;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1, v27);
      }
      goto LABEL_6;
    }
  }
  if ( v11 && *(_DWORD *)(v17 + 8) )
  {
    HandleRdmaDdpReceive = Smb2Read_HandleRdmaDdpReceive(a1, v10, v45, a7, (__int64)a8, v17);
    if ( HandleRdmaDdpReceive < 0 )
      goto LABEL_30;
    v42 = v44 + 192LL * ((unsigned int)v42 % (unsigned int)v43);
    goto LABEL_19;
  }
  if ( (*(_BYTE *)(v17 + 12) & 1) != 0 )
  {
    HandleRdmaDdpReceive = -1073741629;
    Smb2LkmdTelCollectParsingFailureReadHelper(v10, a1, 16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
        a1,
        *(_DWORD *)(a1 + 68));
    }
    goto LABEL_6;
  }
  v42 = v44 + 192LL * ((unsigned int)v42 % (unsigned int)v43);
  if ( v11 )
  {
LABEL_19:
    v21 = (_DWORD *)(v17 + 8);
    goto LABEL_20;
  }
  v21 = (_DWORD *)(v17 + 4);
LABEL_20:
  *(_DWORD *)(v10 + 748) = *v21;
  if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v20) + 64) & 1) != 0 && *(_QWORD *)(v10 + 848) )
    Smb2Read_UpdatePerfCounters(v42, v10);
  if ( a8 )
  {
    v28 = a8 + 1;
    if ( (*a8 & 0x20000000) == 0 )
      v28 = (unsigned int *)(v10 + 748);
    Smb2UpdateCompressibilitySamplingState(a1, *(unsigned int *)(v10 + 748), *v28);
  }
  else
  {
    v22 = *(_QWORD *)(a1 + 504);
    v43 = v22;
    if ( v22 )
    {
      v33 = *(unsigned int *)(v10 + 748);
      v44 = v33;
      _InterlockedAdd64((volatile signed __int64 *)(v22 + 48), v33);
      _InterlockedAdd64((volatile signed __int64 *)(v22 + 56), v33);
      if ( *(_DWORD *)(v22 + 40) == 1 )
      {
        v34 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v22 + 32));
        v35 = v43;
        v36 = v34;
        if ( *(_DWORD *)(v43 + 40) == 1 )
        {
          v37 = *(_QWORD *)(v43 + 8);
          v38 = -1;
          v39 = v44;
          if ( v37 + v44 >= v37 )
            v38 = v37 + v44;
          *(_QWORD *)(v43 + 8) = v38;
          v40 = *(_QWORD *)(v35 + 16);
          v41 = v40 + v39;
          if ( v40 + v39 < v40 )
          {
            *(_QWORD *)(v35 + 16) = -1;
            v41 = -1;
          }
          else
          {
            *(_QWORD *)(v35 + 16) = v41;
          }
          if ( v38 >= *(_QWORD *)v35 )
            *(_DWORD *)(v35 + 40) = v38 - *(_QWORD *)(v35 + 24) < v41 ? 2 : 0;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(v35 + 32), v36);
      }
    }
  }
  if ( *(_BYTE *)(v10 + 856) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v42 + 88));
    *(_BYTE *)(v10 + 856) = 0;
  }
  if ( !v11 )
  {
    v23 = *(unsigned __int8 *)(v17 + 2);
    if ( *(_DWORD *)(v17 + 4) + (int)v23 <= v45 )
    {
      memmove(*(void **)(v10 + 712), (const void *)(a7 + v23), *(unsigned int *)(v17 + 4));
    }
    else if ( !dbgNoOpReadAndTestPaddingMdl )
    {
      v24 = *(unsigned __int8 *)(v17 + 2);
      v16 = -1073741802;
      goto LABEL_29;
    }
  }
  v24 = a5;
LABEL_29:
  *a6 = v24;
LABEL_30:
  RDR_PERF_EXIT(v8);
  RDR_PERF_OUTPUT_ETW(v8);
  RDR_PERF_FREE(v8);
  if ( !HandleRdmaDdpReceive
    && !v16
    && *(_DWORD *)(a1 + 1044) == 1
    && *(_BYTE *)(a1 + 1052)
    && (*(_DWORD *)(a1 + 68) & 0x1000800) == 0
    && (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 632LL) <= 1u || *(_QWORD *)(a1 + 200) % 0x23C34600uLL >= 0x4C4B40) )
  {
    _InterlockedOr((volatile signed __int32 *)(a1 + 68), 0x100000u);
  }
LABEL_32:
  if ( *(_BYTE *)(a1 + 1040) == 1 && HandleRdmaDdpReceive == -2147483643 )
    SmbCeContinueExchange(a1);
  v42 = (unsigned int)HandleRdmaDdpReceive;
  SmbCseUpdateBufferContextStatus(v10, (unsigned int)HandleRdmaDdpReceive);
  return v16;
}

```

## disassembly

```asm
0x14001c190  mov     [rsp+arg_18], r9d
0x14001c195  push    rbx
0x14001c196  push    rbp
0x14001c197  push    rsi
0x14001c198  push    rdi
0x14001c199  push    r12
0x14001c19b  push    r13
0x14001c19d  push    r14
0x14001c19f  push    r15
0x14001c1a1  sub     rsp, 38h
0x14001c1a5  mov     rax, [rcx+58h]
0x14001c1a9  lea     rbx, [rdx+370h]
0x14001c1b0  mov     edi, [r8+10h]
0x14001c1b4  mov     rbp, rdx
0x14001c1b7  mov     r12, [rdx+2F8h]
0x14001c1be  mov     rsi, rcx
0x14001c1c1  mov     dl, 23h ; '#'
0x14001c1c3  mov     rcx, rbx
0x14001c1c6  mov     r8, [rax+1A8h]
0x14001c1cd  mov     r13d, r9d
0x14001c1d0  mov     eax, gs:1A4h
0x14001c1d8  mov     dword ptr [rsp+78h+arg_0], eax
0x14001c1df  mov     eax, [r8+5D0h]
0x14001c1e6  mov     dword ptr [rsp+78h+arg_8], eax
0x14001c1ed  mov     rax, [r8+5C8h]
0x14001c1f4  mov     [rsp+78h+arg_10], rax
0x14001c1fc  call    cs:__imp_RDR_PERF_ENTER
0x14001c203  nop     dword ptr [rax+rax+00h]
0x14001c208  mov     ecx, 80000000h
0x14001c20d  lea     eax, [rdi+rcx]
0x14001c210  test    ecx, eax
0x14001c212  jnz     short loc_14001C28A
0x14001c214  cmp     edi, 80000005h
0x14001c21a  jz      short loc_14001C28A
0x14001c21c  mov     rax, [rsi+48h]
0x14001c220  xor     r14d, r14d
0x14001c223  mov     [rsp+78h+arg_8], r14
0x14001c22b  mov     dword ptr [rsp+78h+arg_0], r14d
0x14001c233  mov     rcx, [rax+18h]
0x14001c237  cmp     [rcx+521h], r14b
0x14001c23e  jnz     loc_14001C4DC
0x14001c244  mov     rax, [rsp+78h+arg_28]
0x14001c24c  mov     ecx, [rsp+78h+arg_20]
0x14001c253  mov     [rax], ecx
0x14001c255  mov     r15d, r14d
0x14001c258  mov     rcx, rbx
0x14001c25b  call    cs:__imp_RDR_PERF_EXIT
0x14001c262  nop     dword ptr [rax+rax+00h]
0x14001c267  mov     rcx, rbx
0x14001c26a  call    cs:__imp_RDR_PERF_OUTPUT_ETW
0x14001c271  nop     dword ptr [rax+rax+00h]
0x14001c276  mov     rcx, rbx
0x14001c279  call    cs:__imp_RDR_PERF_FREE
0x14001c280  nop     dword ptr [rax+rax+00h]
0x14001c285  jmp     loc_14001C431
0x14001c28a  xor     r14d, r14d
0x14001c28d  mov     r15d, r14d
0x14001c290  cmp     r13d, 50h ; 'P'
0x14001c294  jb      loc_14003BB2C
0x14001c29a  mov     r13, [rsp+78h+arg_30]
0x14001c2a2  add     r13, 40h ; '@'
0x14001c2a6  cmp     word ptr [r13+0], 11h
0x14001c2ac  jnz     loc_14003BBA4
0x14001c2b2  movzx   ecx, byte ptr [r13+2]
0x14001c2b7  mov     edx, [rsp+78h+arg_20]
0x14001c2be  cmp     ecx, edx
0x14001c2c0  ja      loc_14001C6B2
0x14001c2c6  mov     r8d, [r13+4]
0x14001c2ca  lea     eax, [r8+rcx]
0x14001c2ce  cmp     eax, edx
0x14001c2d0  ja      loc_14001C6B2
0x14001c2d6  cmp     cl, 50h ; 'P'
0x14001c2d9  jb      loc_14003BC01
0x14001c2df  test    r12, r12
0x14001c2e2  jz      loc_14001C518
0x14001c2e8  mov     eax, [rbp+308h]
0x14001c2ee  cmp     [r13+8], eax
0x14001c2f2  ja      loc_14003BC67
0x14001c2f8  mov     rcx, [rsi+48h]
0x14001c2fc  mov     r9d, 1
0x14001c302  mov     r8d, r9d
0x14001c305  mov     edx, 3
0x14001c30a  call    cs:__imp_SmbCeCheckServerEntryDialect
0x14001c311  nop     dword ptr [rax+rax+00h]
0x14001c316  test    al, al
0x14001c318  jnz     loc_14001C52A
0x14001c31e  test    r12, r12
0x14001c321  jnz     loc_14001C578
0x14001c327  test    byte ptr [r13+0Ch], 1
0x14001c32c  jnz     loc_14001C5E6
0x14001c332  mov     eax, dword ptr [rsp+78h+arg_0]
0x14001c339  xor     edx, edx
0x14001c33b  div     dword ptr [rsp+78h+arg_8]
0x14001c342  lea     rax, [rdx+rdx*2]
0x14001c346  shl     rax, 6
0x14001c34a  add     rax, [rsp+78h+arg_10]
0x14001c352  mov     [rsp+78h+arg_0], rax
0x14001c35a  test    r12, r12
0x14001c35d  jnz     short loc_14001C365
0x14001c35f  lea     rax, [r13+4]
0x14001c363  jmp     short loc_14001C369
0x14001c365  lea     rax, [r13+8]
0x14001c369  mov     eax, [rax]
0x14001c36b  mov     [rbp+2ECh], eax
0x14001c371  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14001c378  nop     dword ptr [rax+rax+00h]
0x14001c37d  test    byte ptr [rax+40h], 1
0x14001c381  jnz     loc_14001C62D
0x14001c387  mov     rcx, [rsp+78h+arg_38]
0x14001c38f  test    rcx, rcx
0x14001c392  jnz     loc_14001C64F
0x14001c398  mov     rax, [rsi+1F8h]
0x14001c39f  mov     [rsp+78h+arg_8], rax
0x14001c3a7  test    rax, rax
0x14001c3aa  jnz     loc_14003BCF0
0x14001c3b0  cmp     [rbp+358h], r14b
0x14001c3b7  jnz     loc_14001C66E
0x14001c3bd  test    r12, r12
0x14001c3c0  jnz     short loc_14001C3EA
0x14001c3c2  mov     ecx, [r13+4]
0x14001c3c6  movzx   edx, byte ptr [r13+2]
0x14001c3cb  lea     eax, [rcx+rdx]
0x14001c3ce  cmp     eax, [rsp+78h+arg_18]
0x14001c3d5  jbe     loc_14001C696
0x14001c3db  movzx   eax, cs:dbgNoOpReadAndTestPaddingMdl
0x14001c3e2  test    al, al
0x14001c3e4  jz      loc_14001C686
0x14001c3ea  mov     ecx, [rsp+78h+arg_20]
0x14001c3f1  mov     rax, [rsp+78h+arg_28]
0x14001c3f9  mov     [rax], ecx
0x14001c3fb  mov     rcx, rbx
0x14001c3fe  call    cs:__imp_RDR_PERF_EXIT
0x14001c405  nop     dword ptr [rax+rax+00h]
0x14001c40a  mov     rcx, rbx
0x14001c40d  call    cs:__imp_RDR_PERF_OUTPUT_ETW
0x14001c414  nop     dword ptr [rax+rax+00h]
0x14001c419  mov     rcx, rbx
0x14001c41c  call    cs:__imp_RDR_PERF_FREE
0x14001c423  nop     dword ptr [rax+rax+00h]
0x14001c428  test    edi, edi
0x14001c42a  jnz     short loc_14001C431
0x14001c42c  test    r15d, r15d
0x14001c42f  jz      short loc_14001C479
0x14001c431  cmp     byte ptr [rsi+410h], 1
0x14001c438  jz      loc_14001C703
0x14001c43e  mov     dword ptr [rsp+78h+arg_0], edi
0x14001c445  mov     rcx, rbp
0x14001c448  mov     dword ptr [rsp+78h+arg_0+4], r14d
0x14001c450  mov     rdx, [rsp+78h+arg_0]
0x14001c458  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14001c45f  nop     dword ptr [rax+rax+00h]
0x14001c464  mov     eax, r15d
0x14001c467  add     rsp, 38h
0x14001c46b  pop     r15
0x14001c46d  pop     r14
0x14001c46f  pop     r13
0x14001c471  pop     r12
0x14001c473  pop     rdi
0x14001c474  pop     rsi
0x14001c475  pop     rbp
0x14001c476  pop     rbx
0x14001c477  retn
0x14001c479  cmp     dword ptr [rsi+414h], 1
0x14001c480  jnz     short loc_14001C431
0x14001c482  cmp     [rsi+41Ch], r14b
0x14001c489  jz      short loc_14001C431
0x14001c48b  mov     eax, [rsi+44h]
0x14001c48e  test    eax, 1000800h
0x14001c493  jnz     short loc_14001C431
0x14001c495  mov     rax, [rsi+48h]
0x14001c499  cmp     dword ptr [rax+278h], 1
0x14001c4a0  ja      short loc_14001C4AC
0x14001c4a2  lock or dword ptr [rsi+44h], 100000h
0x14001c4aa  jmp     short loc_14001C431
0x14001c4ac  mov     rcx, [rsi+0C8h]
0x14001c4b3  mov     rax, 0E5109EC205D7BEA7h
0x14001c4bd  mul     rcx
0x14001c4c0  shr     rdx, 1Dh
0x14001c4c4  imul    rax, rdx, 23C34600h
0x14001c4cb  sub     rcx, rax
0x14001c4ce  cmp     rcx, 4C4B40h
0x14001c4d5  jnb     short loc_14001C4A2
0x14001c4d7  jmp     loc_14001C431
0x14001c4dc  mov     r15d, [rsp+78h+arg_20]
0x14001c4e4  cmp     r13d, r15d
0x14001c4e7  jz      loc_14003BAAC
0x14001c4ed  mov     rax, [rsp+78h+arg_28]
0x14001c4f5  mov     r9d, r15d
0x14001c4f8  mov     rdx, [rsp+78h+arg_30]
0x14001c500  mov     r8d, r13d
0x14001c503  mov     rcx, rbp
0x14001c506  mov     [rsp+78h+var_58], rax
0x14001c50b  call    Smb2BufferErrorResponse
0x14001c510  mov     r15d, eax
0x14001c513  jmp     loc_14001C258
0x14001c518  cmp     r8d, [rbp+2E8h]
0x14001c51f  ja      loc_14003BC67
0x14001c525  jmp     loc_14001C2F8
0x14001c52a  mov     r8d, [r13+0Ch]
0x14001c52e  cmp     r8d, 2
0x14001c532  jb      loc_14001C31E
0x14001c538  mov     edi, 0C00000C3h
0x14001c53d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c544  lea     rax, WPP_GLOBAL_Control
0x14001c54b  cmp     rcx, rax
0x14001c54e  jz      loc_14001C258
0x14001c554  mov     eax, [rcx+2Ch]
0x14001c557  test    al, 1
0x14001c559  jz      loc_14001C258
0x14001c55f  cmp     byte ptr [rcx+29h], 1
0x14001c563  jb      loc_14001C258
0x14001c569  mov     edx, 2Ah ; '*'
0x14001c56e  mov     dword ptr [rsp+78h+var_58], r8d
0x14001c573  jmp     loc_14003BCC4
0x14001c578  cmp     [r13+8], r14d
0x14001c57c  jbe     loc_14001C327
0x14001c582  mov     rax, [rsp+78h+arg_38]
0x14001c58a  mov     rdx, rbp
0x14001c58d  mov     r9, [rsp+78h+arg_30]
0x14001c595  mov     rcx, rsi
0x14001c598  mov     r8d, [rsp+78h+arg_18]
0x14001c5a0  mov     [rsp+78h+var_50], r13
0x14001c5a5  mov     [rsp+78h+var_58], rax
0x14001c5aa  call    Smb2Read_HandleRdmaDdpReceive
0x14001c5af  mov     edi, eax
0x14001c5b1  test    eax, eax
0x14001c5b3  js      loc_14001C3FB
0x14001c5b9  mov     eax, dword ptr [rsp+78h+arg_0]
0x14001c5c0  xor     edx, edx
0x14001c5c2  div     dword ptr [rsp+78h+arg_8]
0x14001c5c9  lea     rax, [rdx+rdx*2]
0x14001c5cd  shl     rax, 6
0x14001c5d1  add     rax, [rsp+78h+arg_10]
0x14001c5d9  mov     [rsp+78h+arg_0], rax
0x14001c5e1  jmp     loc_14001C365
0x14001c5e6  mov     r8d, 10h
0x14001c5ec  mov     rdx, rsi
0x14001c5ef  mov     rcx, rbp
0x14001c5f2  mov     edi, 0C00000C3h
0x14001c5f7  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x14001c5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c603  lea     rax, WPP_GLOBAL_Control
0x14001c60a  cmp     rcx, rax
0x14001c60d  jz      loc_14001C258
0x14001c613  mov     eax, [rcx+2Ch]
0x14001c616  test    al, 1
0x14001c618  jz      loc_14001C258
0x14001c61e  cmp     byte ptr [rcx+29h], 1
0x14001c622  jb      loc_14001C258
0x14001c628  jmp     loc_14003BCB8
0x14001c62d  cmp     [rbp+350h], r14
0x14001c634  jz      loc_14001C387
0x14001c63a  mov     rcx, [rsp+78h+arg_0]
0x14001c642  mov     rdx, rbp
0x14001c645  call    Smb2Read_UpdatePerfCounters
0x14001c64a  jmp     loc_14001C387
0x14001c64f  test    dword ptr [rcx], 20000000h
0x14001c655  lea     rax, [rbp+2ECh]
0x14001c65c  lea     r8, [rcx+4]
0x14001c660  jnz     loc_14003BCDD
0x14001c666  mov     r8, rax
0x14001c669  jmp     loc_14003BCDD
0x14001c66e  mov     rax, [rsp+78h+arg_0]
0x14001c676  lock dec dword ptr [rax+58h]
0x14001c67a  mov     [rbp+358h], r14b
0x14001c681  jmp     loc_14001C3BD
0x14001c686  movzx   ecx, byte ptr [r13+2]
0x14001c68b  mov     r15d, 0C0000016h
0x14001c691  jmp     loc_14001C3F1
0x14001c696  add     rdx, [rsp+78h+arg_30]; Src
0x14001c69e  mov     r8, rcx; Size
0x14001c6a1  mov     rcx, [rbp+2C8h]; void *
0x14001c6a8  call    memmove
0x14001c6ad  jmp     loc_14001C3EA
0x14001c6b2  mov     rax, [rsp+78h+arg_28]
0x14001c6ba  mov     r8d, 0Dh
0x14001c6c0  mov     rcx, rbp
0x14001c6c3  mov     [rax], edx
0x14001c6c5  mov     rdx, rsi
0x14001c6c8  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x14001c6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c6d4  lea     rax, WPP_GLOBAL_Control
0x14001c6db  cmp     rcx, rax
0x14001c6de  jz      loc_14003BC5D
0x14001c6e4  mov     eax, [rcx+2Ch]
0x14001c6e7  test    al, 1
0x14001c6e9  jz      loc_14003BC5D
0x14001c6ef  cmp     byte ptr [rcx+29h], 1
0x14001c6f3  jb      loc_14003BC5D
0x14001c6f9  mov     edx, 27h ; '''
0x14001c6fe  jmp     loc_14003BC4A
0x14001c703  cmp     edi, 80000005h
0x14001c709  jnz     loc_14001C43E
0x14001c70f  mov     rcx, rsi
0x14001c712  call    cs:__imp_SmbCeContinueExchange
0x14001c719  nop     dword ptr [rax+rax+00h]
0x14001c71e  jmp     loc_14001C43E
0x14003baac  mov     rax, [rsi+30h]
0x14003bab0  cmp     [rax+28h], r14
0x14003bab4  jz      short loc_14003BB1C
  ... truncated ...
```
