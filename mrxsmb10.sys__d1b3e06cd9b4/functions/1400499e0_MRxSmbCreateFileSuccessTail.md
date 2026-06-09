# MRxSmbCreateFileSuccessTail

- ea: `0x1400499e0`
- end: `0x14004a2ea`
- name: `MRxSmbCreateFileSuccessTail`
- size: `2314`
- prototype: `__int64 __usercall@<rax>(PRX_CONTEXT RxContext@<rcx>, int, char, int, __int64)`
- caller_count: `8`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x140038760`
- `0x14003889c`
- `0x140038ad0`
- `0x140038d60`
- `0x140038f6c`
- `0x14003adf0`
- `0x14003b3a4`
- `0x140049870`

## callees

- `0x14000dc44`
- `0x14000dfa8`
- `0x14000e01c`
- `0x14000ee78`
- `0x14001051c`
- `0x140010660`
- `0x1400109ac`
- `0x140010a04`
- `0x140016560`
- `0x1400281f8`
- `0x1400499e0`
- `0x14004a2f0`
- `0x14004a7a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140049b76`
- `ntoskrnl!ExAllocatePool2` at `0x140049b76`
- `rdbss!RxIndicateChangeOfOplockState` at `0x140049f14`
- `rdbss!RxIndicateChangeOfOplockState` at `0x140049f14`
- `rdbss!RxFinishFcbInitialization` at `0x14004a12c`
- `rdbss!RxFinishFcbInitialization` at `0x14004a12c`
- `rdbss!RxCreateNetFobx` at `0x140049af1`
- `rdbss!RxCreateNetFobx` at `0x140049af1`
- `rdbss!RxRegisterSrvOpenWithBufferingManager` at `0x140049de0`
- `rdbss!RxRegisterSrvOpenWithBufferingManager` at `0x140049de0`

## pseudocode

```c
__int64 __fastcall MRxSmbCreateFileSuccessTail(
        PRX_CONTEXT RxContext,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        int a5,
        char a6,
        unsigned int a7,
        __int64 a8)
{
  PMRX_FCB pFcb; // r14
  unsigned int v9; // edi
  __int64 v11; // r15
  PMRX_SRV_OPEN pRelevantSrvOpen; // r13
  __int64 v13; // r12
  int v14; // ebp
  __int64 v15; // rdx
  PMRX_SHADOW_CALLDOWN DispatchRoutine; // rbx
  PMRX_FOBX pFobx; // rax
  PMRX_FCB v18; // rdi
  PDEVICE_OBJECT v19; // rcx
  PMRX_FOBX v21; // rbx
  PMRX_FOBX v22; // r9
  __int64 v23; // rdx
  int v24; // r11d
  __int64 v25; // r10
  char v26; // r9
  unsigned __int16 i; // ax
  __int64 *v28; // r15
  __int64 v29; // rcx
  __int64 v30; // rax
  PMRX_FCB v31; // rbp
  __int64 v32; // rdx
  char v33; // bl
  __int64 v34; // rcx
  unsigned int v35; // ebp
  unsigned __int64 v36; // rdx
  _DWORD *Context2; // r10
  ULONG v38; // edi
  __int64 v39; // rdx
  unsigned int v40; // ecx
  unsigned int v41; // ebx
  __int64 v42; // r9
  __int64 v43; // rcx
  unsigned __int64 v44; // rdx
  bool v45; // dl
  struct _FCB_INIT_PACKET *p_InitPacket; // r8
  __int64 v47; // rbx
  __int16 *v48; // rdx
  __int64 v49; // [rsp+28h] [rbp-100h]
  __int64 v50; // [rsp+30h] [rbp-F8h]
  __int64 v51; // [rsp+38h] [rbp-F0h]
  unsigned int v52; // [rsp+50h] [rbp-D8h]
  __int64 v54; // [rsp+60h] [rbp-C8h]
  unsigned int v55; // [rsp+68h] [rbp-C0h]
  ULONGLONG ActualAllocationLength; // [rsp+78h] [rbp-B0h]
  __int128 InitPacket; // [rsp+80h] [rbp-A8h] BYREF
  __int128 InitPacket_16; // [rsp+90h] [rbp-98h]
  __int128 InitPacket_32; // [rsp+A0h] [rbp-88h]
  __m256i InitPacket_48; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD v61[2]; // [rsp+D0h] [rbp-58h] BYREF

  pFcb = RxContext->pFcb;
  v9 = 0;
  v11 = a4;
  v52 = a3;
  v55 = 0;
  if ( pFcb )
    ActualAllocationLength = pFcb->ActualAllocationLength;
  else
    ActualAllocationLength = 0;
  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  if ( pRelevantSrvOpen )
    v13 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  else
    v13 = 0;
  v14 = *((_DWORD *)&RxContext->9 + 28);
  v15 = *(_QWORD *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease + 32LL);
  v54 = v15;
  DispatchRoutine = pRelevantSrvOpen->ShadowContext->DispatchRoutine;
  memset(&InitPacket_48, 0, 28);
  InitPacket = 0;
  InitPacket_16 = 0;
  InitPacket_32 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
    v15 = v54;
  }
  *(_DWORD *)(v13 + 4) = a5;
  *(_WORD *)(v13 + 8) = v11;
  if ( *(_DWORD *)(v13 + 128) )
  {
    if ( *(_BYTE *)(v13 + 10) != a6 && *(_QWORD *)(v15 + 48) )
    {
      if ( a6 && a6 == 1 )
        v42 = 3;
      else
        v42 = 0;
      v43 = *(_QWORD *)(v15 + 48);
      v44 = v11 | ((unsigned __int64)*((unsigned __int16 *)DispatchRoutine + 57) << 16);
      v61[1] = 0;
      v61[0] = v44;
      RxIndicateChangeOfOplockState(v43, v61, 0, v42);
    }
    goto LABEL_113;
  }
  pFobx = RxContext->pFobx;
  v18 = RxContext->pFcb;
  if ( !pFobx )
  {
    pFobx = RxCreateNetFobx(RxContext, pRelevantSrvOpen);
    RxContext->pFobx = pFobx;
    if ( !pFobx )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        return 3221225626LL;
      }
      v23 = 43;
      v22 = (PMRX_FOBX)pRelevantSrvOpen;
LABEL_17:
      WPP_SF_qD(v19->AttachedDevice, v23, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v22, -1073741670);
      return 3221225626LL;
    }
  }
  if ( !pFobx->UnicodeQueryTemplate.Buffer )
  {
    v21 = RxContext->pFobx;
    v21->UnicodeQueryTemplate.Buffer = (PWSTR)ExAllocatePool2(256, 72, 1766223187);
    v22 = RxContext->pFobx;
    if ( !v22->UnicodeQueryTemplate.Buffer )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        return 3221225626LL;
      }
      v23 = 44;
      goto LABEL_17;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LLL(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v52, v11, a7);
  v24 = 2;
  v25 = a8;
  v61[0] = pRelevantSrvOpen->ShadowContext->DispatchRoutine;
  if ( DisableByteRangeLockingOnReadOnlyFiles )
  {
    v26 = a6;
    if ( a6 == 3 && (*(_DWORD *)(a8 + 32) & 1) != 0 )
    {
      v45 = 0;
      if ( (v14 & 0x120089) == 0 )
        v45 = (v14 & 0xFFFDFF76) != 0 && (v14 & 0x120116) != 0;
      if ( !v45 )
        v26 = 2;
    }
  }
  else
  {
    v26 = a6;
  }
  for ( i = 0; i < (unsigned __int16)(LOWORD(v18[2].Header.Resource) >> 1); ++i )
  {
    if ( *((_WORD *)&v18[2].Header.PagingIoResource->SystemResourcesList.Flink + i) == 58 )
    {
      v26 = 0;
      break;
    }
  }
  *(_BYTE *)(v13 + 10) = v26;
  v28 = (__int64 *)(a8 + 40);
  *((_QWORD *)&RxContext->9 + 25) = a7;
  v29 = *(_QWORD *)(a8 + 40);
  if ( v29 < 0 )
    return 3221225667LL;
  v30 = *(_QWORD *)(a8 + 48);
  if ( v30 < 0 )
    return 3221225667LL;
  if ( v29 < v30 )
    *v28 = v30;
  *(_DWORD *)(ActualAllocationLength + 84) = *(_DWORD *)(a8 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      46,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      *(unsigned __int8 *)(v13 + 10),
      *(unsigned __int16 *)(ActualAllocationLength + 14));
    v25 = a8;
    v24 = 2;
  }
  if ( !*(_WORD *)(ActualAllocationLength + 14)
    || (*(_WORD *)(ActualAllocationLength + 14) == 1
     || (unsigned int)*(unsigned __int16 *)(ActualAllocationLength + 14) - 2 <= 1)
    && (unsigned __int8)(*(_BYTE *)(v13 + 10) - 1) <= 1u )
  {
    v31 = pFcb;
    HIDWORD(pFcb->SrvOpenList.Flink) &= ~0x40000u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
      v25 = a8;
      v24 = 2;
    }
  }
  else
  {
    v31 = pFcb;
  }
  v32 = v54;
  *(_WORD *)(ActualAllocationLength + 14) = *(unsigned __int8 *)(v13 + 10);
  if ( ((__int64)pRelevantSrvOpen->Key & 0x100000) != 0 )
  {
    v33 = 1;
  }
  else
  {
    v33 = 0;
    if ( !*(_BYTE *)(v54 + 505) )
    {
      MRxSmbCreateBasicFileInfoCache((__int64)RxContext, v25, v54, 0);
      MRxSmbCreateStandardFileInfoCache((__int64)RxContext, (__int64)v28, v54, 0);
      v25 = a8;
      v24 = 2;
      v32 = v54;
    }
    v34 = *(_QWORD *)&pRelevantSrvOpen->Flags;
    if ( (*(_DWORD *)(v34 + 72) & 0x10) == 0 )
    {
      *(_BYTE *)(v34 + 132) = 1;
      _InterlockedIncrement((volatile signed __int32 *)(v32 + 488));
    }
  }
  if ( LODWORD(v31[1].Header.PagingIoResource) )
  {
    if ( v33 )
    {
LABEL_46:
      v35 = v52;
      goto LABEL_96;
    }
  }
  else if ( v33 )
  {
    p_InitPacket = 0;
    goto LABEL_93;
  }
  if ( (*(_DWORD *)(a8 + 32) & 0x400) == 0 )
  {
    v24 = 1;
    if ( (*((_DWORD *)&RxContext->9 + 35) & 0x200000) != 0 )
      v24 = 4;
  }
  LODWORD(InitPacket) = v24;
  *(_QWORD *)&InitPacket_16 = v25 + 56;
  p_InitPacket = (struct _FCB_INIT_PACKET *)&InitPacket;
  *((_QWORD *)&InitPacket + 1) = a8 + 32;
  *(_QWORD *)&InitPacket_32 = v25 + 8;
  *((_QWORD *)&InitPacket_32 + 1) = v25 + 16;
  InitPacket_48.m256i_i64[0] = v25 + 24;
  *((_QWORD *)&InitPacket_16 + 1) = v25;
  InitPacket_48.m256i_i64[1] = a8 + 40;
  InitPacket_48.m256i_i64[2] = a8 + 48;
  InitPacket_48.m256i_i64[3] = a8 + 48;
LABEL_93:
  if ( (HIDWORD(pFcb->SrvOpenList.Blink) & 2) != 0 && (unsigned __int8)(*(_BYTE *)(v13 + 10) - 1) > 1u )
    goto LABEL_46;
  v35 = v52;
  RxFinishFcbInitialization(pFcb, (RX_FILE_TYPE)(v52 + 60448), p_InitPacket);
  v32 = v54;
LABEL_96:
  v47 = v61[0];
  if ( (*(_BYTE *)(*(_QWORD *)(v61[0] + 104LL) + 1232LL) || *(_BYTE *)(v32 + 640)) && !*(_QWORD *)(v13 + 16) )
  {
    v55 = MRxSmbConstructDeferredOpenContext(RxContext, v32);
    if ( !v55 )
    {
      *(_DWORD *)(*(_QWORD *)(v13 + 16) + 24LL) = 1;
      LODWORD(pRelevantSrvOpen->Key) &= ~0x100000u;
    }
  }
  v36 = a4 | ((unsigned __int64)*(unsigned __int16 *)(v47 + 114) << 16);
  pRelevantSrvOpen->SrvOpenQLinks.Blink = 0;
  pRelevantSrvOpen->SrvOpenQLinks.Flink = (struct _LIST_ENTRY *)v36;
  RxRegisterSrvOpenWithBufferingManager(pRelevantSrvOpen);
  Context2 = pRelevantSrvOpen->Context2;
  v38 = 0;
  v39 = 0;
  a3 = Context2[58] & 0x200;
  switch ( *(_BYTE *)(v13 + 10) )
  {
    case 1:
      goto LABEL_103;
    case 2:
      if ( v35 == 2 )
      {
        v38 = 16;
        LODWORD(v39) = 4196352;
      }
LABEL_103:
      v38 |= 0xEu;
      v39 = (unsigned int)v39 | 0x8300000;
      goto LABEL_104;
    case 3:
LABEL_104:
      v38 |= 1u;
      LODWORD(v39) = v39 | 0x2000000;
      break;
  }
  v40 = v39 & 0xF7FFFFFF;
  if ( !(_DWORD)a3 )
    v40 = v39;
  v41 = v40 & 0xF5FFFFFF;
  if ( !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)Context2 + 15) + 32LL) + 32LL) + 505LL) )
    v41 = v40;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    v48 = (__int16 *)"Sparse";
    if ( !(_DWORD)a3 )
      v48 = &word_14001A766;
    WPP_SF_DDqqsZ(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v48,
      a3,
      v38,
      v41,
      (char)pRelevantSrvOpen,
      (char)Context2,
      (__int64)v48,
      *(_QWORD *)&pRelevantSrvOpen->DesiredAccess);
  }
  if ( v35 == 1 )
    LODWORD(pRelevantSrvOpen->Key) |= 0x200u;
  LODWORD(pRelevantSrvOpen->Key) |= MRxSmbInitialSrvOpenFlags;
  *(_DWORD *)&RxContext->TrackerHistory[4].SavedTrackerValue = v41;
  RxContext->TrackerHistory[4].AcquireRelease = v38;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    LODWORD(v50) = v41;
    LODWORD(v49) = v38;
    WPP_SF_qqDD(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      pRelevantSrvOpen,
      pRelevantSrvOpen->Context2,
      v49,
      v50,
      v51);
  }
  v9 = v55;
  if ( !v55 )
    LODWORD(RxContext->pFobx[1].Context) = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v9;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_qi(WPP_GLOBAL_Control->AttachedDevice, v39, a3, pRelevantSrvOpen, pRelevantSrvOpen->SrvOpenQLinks.Flink);
LABEL_113:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_LDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      a3,
      v9,
      HIDWORD(pFcb->SrvOpenList.Flink),
      HIDWORD(pFcb->SrvOpenList.Blink),
      pFcb->SrvOpenList.Blink);
  return v9;
}

```

## disassembly

```asm
0x1400499e0  mov     [rsp+arg_8], rbx
0x1400499e5  push    rbp
0x1400499e6  push    rsi
0x1400499e7  push    rdi
0x1400499e8  push    r12
0x1400499ea  push    r13
0x1400499ec  push    r14
0x1400499ee  push    r15
0x1400499f0  sub     rsp, 0F0h
0x1400499f7  mov     rax, cs:__security_cookie
0x1400499fe  xor     rax, rsp
0x140049a01  mov     [rsp+128h+var_48], rax
0x140049a09  mov     r14, [rcx+38h]
0x140049a0d  xor     edi, edi
0x140049a0f  mov     rax, [rsp+128h+arg_38]
0x140049a17  mov     rsi, rcx
0x140049a1a  movzx   r15d, r9w
0x140049a1e  mov     [rsp+128h+var_D4], r15w
0x140049a24  mov     [rsp+128h+var_D8], r8d
0x140049a29  mov     [rsp+128h+var_D0], rax
0x140049a2e  mov     [rsp+128h+var_C0], edi
0x140049a32  mov     [rsp+128h+Fcb], r14
0x140049a37  test    r14, r14
0x140049a3a  jz      loc_140049D77
0x140049a40  mov     rax, [r14+88h]
0x140049a47  mov     [rsp+128h+var_B0], rax
0x140049a4c  mov     r13, [rcx+48h]
0x140049a50  test    r13, r13
0x140049a53  jnz     loc_140049B4E
0x140049a59  xor     r12d, r12d
0x140049a5c  mov     rax, [rcx+280h]
0x140049a63  xorps   xmm0, xmm0
0x140049a66  mov     ebp, [rcx+200h]
0x140049a6c  mov     rdx, [rax+20h]
0x140049a70  mov     rax, [r13+28h]
0x140049a74  mov     [rsp+128h+var_C8], rdx
0x140049a79  mov     rbx, [rax+28h]
0x140049a7d  xor     eax, eax
0x140049a7f  movups  xmmword ptr [rsp+128h+InitPacket.pAllocationSize], xmm0
0x140049a87  movups  xmmword ptr [rsp+128h+InitPacket.pFileSize+4], xmm0
0x140049a8f  movups  xmmword ptr [rsp+128h+InitPacket.pAttributes], xmm0
0x140049a97  movups  xmmword ptr [rsp+128h+InitPacket.pCreationTime], xmm0
0x140049a9f  movups  xmmword ptr [rsp+128h+InitPacket.pLastWriteTime], xmm0
0x140049aa7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049aae  lea     r9, WPP_GLOBAL_Control
0x140049ab5  cmp     rcx, r9
0x140049ab8  jnz     loc_140049BD7
0x140049abe  mov     eax, [rsp+128h+arg_20]
0x140049ac5  mov     [r12+4], eax
0x140049aca  mov     [r12+8], r15w
0x140049ad0  cmp     [r12+80h], edi
0x140049ad8  jnz     loc_140049EB7
0x140049ade  mov     rax, [rsi+40h]
0x140049ae2  mov     rdi, [rsi+38h]
0x140049ae6  test    rax, rax
0x140049ae9  jnz     short loc_140049B57
0x140049aeb  mov     rdx, r13; MrxSrvOpen
0x140049aee  mov     rcx, rsi; RxContext
0x140049af1  call    cs:__imp_RxCreateNetFobx
0x140049af8  nop     dword ptr [rax+rax+00h]
0x140049afd  mov     [rsi+40h], rax
0x140049b01  test    rax, rax
0x140049b04  jnz     short loc_140049B57
0x140049b06  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049b0d  lea     rax, WPP_GLOBAL_Control
0x140049b14  cmp     rcx, rax
0x140049b17  jnz     loc_140049F25
0x140049b1d  mov     eax, 0C000009Ah
0x140049b22  mov     rcx, [rsp+128h+var_48]
0x140049b2a  xor     rcx, rsp; StackCookie
0x140049b2d  call    __security_check_cookie
0x140049b32  mov     rbx, [rsp+128h+arg_8]
0x140049b3a  add     rsp, 0F0h
0x140049b41  pop     r15
0x140049b43  pop     r14
0x140049b45  pop     r13
0x140049b47  pop     r12
0x140049b49  pop     rdi
0x140049b4a  pop     rsi
0x140049b4b  pop     rbp
0x140049b4c  retn
0x140049b4e  mov     r12, [r13+30h]
0x140049b52  jmp     loc_140049A5C
0x140049b57  cmp     qword ptr [rax+38h], 0
0x140049b5c  jnz     loc_140049C0A
0x140049b62  mov     rbx, [rsi+40h]
0x140049b66  mov     edx, 48h ; 'H'
0x140049b6b  mov     ecx, 100h
0x140049b70  mov     r8d, 69466D53h
0x140049b76  call    cs:__imp_ExAllocatePool2
0x140049b7d  nop     dword ptr [rax+rax+00h]
0x140049b82  mov     [rbx+38h], rax
0x140049b86  mov     r9, [rsi+40h]
0x140049b8a  cmp     qword ptr [r9+38h], 0
0x140049b8f  jnz     short loc_140049C0A
0x140049b91  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049b98  lea     rax, WPP_GLOBAL_Control
0x140049b9f  cmp     rcx, rax
0x140049ba2  jz      loc_140049B1D
0x140049ba8  test    dword ptr [rcx+2Ch], 100h
0x140049baf  jz      loc_140049B1D
0x140049bb5  mov     edx, 2Ch ; ','
0x140049bba  mov     rcx, [rcx+18h]
0x140049bbe  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140049bc5  mov     dword ptr [rsp+128h+var_108], 0C000009Ah
0x140049bcd  call    WPP_SF_qD
0x140049bd2  jmp     loc_140049B1D
0x140049bd7  test    dword ptr [rcx+2Ch], 400h
0x140049bde  jz      loc_140049ABE
0x140049be4  mov     rcx, [rcx+18h]
0x140049be8  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140049bef  mov     edx, 2Ah ; '*'
0x140049bf4  call    WPP_SF_
0x140049bf9  mov     rdx, [rsp+128h+var_C8]
0x140049bfe  lea     r9, WPP_GLOBAL_Control
0x140049c05  jmp     loc_140049ABE
0x140049c0a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049c11  lea     rdx, WPP_GLOBAL_Control
0x140049c18  mov     ebx, [rsp+128h+arg_30]
0x140049c1f  cmp     rcx, rdx
0x140049c22  jnz     loc_140049F3F
0x140049c28  cmp     cs:DisableByteRangeLockingOnReadOnlyFiles, 0
0x140049c2f  mov     r11d, 2
0x140049c35  mov     rax, [r13+28h]
0x140049c39  mov     r10, [rsp+128h+var_D0]
0x140049c3e  mov     rax, [rax+28h]
0x140049c42  mov     [rsp+128h+var_58], rax
0x140049c4a  jnz     loc_140049F74
0x140049c50  movzx   r9d, [rsp+128h+arg_28]
0x140049c59  movzx   r8d, word ptr [rdi+168h]
0x140049c61  xor     eax, eax
0x140049c63  shr     r8w, 1
0x140049c67  cmp     ax, r8w
0x140049c6b  jnb     short loc_140049C86
0x140049c6d  mov     rcx, [rdi+170h]
0x140049c74  movzx   edx, ax
0x140049c77  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x140049c7c  jz      short loc_140049C83
0x140049c7e  inc     ax
0x140049c81  jmp     short loc_140049C67
0x140049c83  xor     r9b, r9b
0x140049c86  mov     [r12+0Ah], r9b
0x140049c8b  lea     r15, [r10+28h]
0x140049c8f  mov     [rsi+258h], rbx
0x140049c96  mov     rcx, [r15]
0x140049c99  test    rcx, rcx
0x140049c9c  js      loc_140049D81
0x140049ca2  mov     rax, [r10+30h]
0x140049ca6  lea     r14, [r10+30h]
0x140049caa  test    rax, rax
0x140049cad  js      loc_140049D81
0x140049cb3  cmp     rcx, rax
0x140049cb6  jl      loc_140049FC0
0x140049cbc  mov     rbx, [rsp+128h+var_B0]
0x140049cc1  lea     rdi, [r10+20h]
0x140049cc5  mov     eax, [rdi]
0x140049cc7  mov     [rbx+54h], eax
0x140049cca  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049cd1  lea     rdx, WPP_GLOBAL_Control
0x140049cd8  cmp     rcx, rdx
0x140049cdb  jz      short loc_140049CEA
0x140049cdd  test    dword ptr [rcx+2Ch], 200h
0x140049ce4  jnz     loc_140049FC8
0x140049cea  movzx   eax, word ptr [rbx+0Eh]
0x140049cee  test    eax, eax
0x140049cf0  jnz     loc_14004A002
0x140049cf6  mov     rbp, [rsp+128h+Fcb]
0x140049cfb  and     dword ptr [rbp+9Ch], 0FFFBFFFFh
0x140049d05  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049d0c  cmp     rcx, rdx
0x140049d0f  jz      short loc_140049D1E
0x140049d11  test    dword ptr [rcx+2Ch], 200h
0x140049d18  jnz     loc_14004A02B
0x140049d1e  movzx   eax, byte ptr [r12+0Ah]
0x140049d24  mov     rdx, [rsp+128h+var_C8]
0x140049d29  mov     [rbx+0Eh], ax
0x140049d2d  test    dword ptr [r13+48h], 100000h
0x140049d35  jnz     loc_14004A050
0x140049d3b  xor     bl, bl
0x140049d3d  cmp     [rdx+1F9h], bl
0x140049d43  jz      short loc_140049D8B
0x140049d45  mov     rcx, [r13+30h]
0x140049d49  mov     eax, [rcx+48h]
0x140049d4c  test    al, 10h
0x140049d4e  jz      loc_14004A057
0x140049d54  cmp     dword ptr [rbp+0C0h], 0
0x140049d5b  jz      loc_14004A06A
0x140049d61  test    bl, bl
0x140049d63  jz      loc_14004A076
0x140049d69  mov     r14, [rsp+128h+Fcb]
0x140049d6e  mov     ebp, [rsp+128h+var_D8]
0x140049d72  jmp     loc_14004A13D
0x140049d77  mov     [rsp+128h+var_B0], rdi
0x140049d7c  jmp     loc_140049A4C
0x140049d81  mov     eax, 0C00000C3h
0x140049d86  jmp     loc_140049B22
0x140049d8b  mov     r8, rdx
0x140049d8e  xor     r9d, r9d
0x140049d91  mov     rdx, r10
0x140049d94  mov     rcx, rsi
0x140049d97  call    MRxSmbCreateBasicFileInfoCache
0x140049d9c  mov     r8, [rsp+128h+var_C8]
0x140049da1  xor     r9d, r9d
0x140049da4  mov     rdx, r15
0x140049da7  mov     rcx, rsi
0x140049daa  call    MRxSmbCreateStandardFileInfoCache
0x140049daf  mov     r10, [rsp+128h+var_D0]
0x140049db4  mov     r11d, 2
0x140049dba  mov     rdx, [rsp+128h+var_C8]
0x140049dbf  jmp     short loc_140049D45
0x140049dc1  movzx   edx, word ptr [rbx+72h]
0x140049dc5  movzx   ecx, [rsp+128h+var_D4]
0x140049dca  shl     rdx, 10h
0x140049dce  or      rdx, rcx
0x140049dd1  mov     qword ptr [r13+70h], 0
0x140049dd9  mov     rcx, r13
0x140049ddc  mov     [r13+68h], rdx
0x140049de0  call    cs:__imp_RxRegisterSrvOpenWithBufferingManager
0x140049de7  nop     dword ptr [rax+rax+00h]
0x140049dec  mov     r10, [r13+20h]
0x140049df0  xor     edi, edi
0x140049df2  xor     edx, edx
0x140049df4  mov     rax, [r10+78h]
0x140049df8  mov     r8d, [r10+0E8h]
0x140049dff  and     r8d, 200h
0x140049e06  mov     rcx, [rax+20h]
0x140049e0a  mov     r9, [rcx+20h]
0x140049e0e  movzx   ecx, byte ptr [r12+0Ah]
0x140049e14  sub     ecx, 1
0x140049e17  jz      loc_14004A1A7
0x140049e1d  sub     ecx, 1
0x140049e20  jz      loc_14004A198
0x140049e26  cmp     ecx, 1
0x140049e29  jz      loc_14004A1B0
0x140049e2f  mov     ecx, edx
0x140049e31  btr     ecx, 1Bh
0x140049e35  test    r8d, r8d
0x140049e38  cmovz   ecx, edx
0x140049e3b  mov     ebx, ecx; __annotation("TMF:",
0x140049e3d  and     ebx, 0F5FFFFFFh
0x140049e43  cmp     byte ptr [r9+1F9h], 0
0x140049e4b  lea     r9, WPP_GLOBAL_Control
0x140049e52  cmovz   ebx, ecx
0x140049e55  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e5c  cmp     rcx, r9
0x140049e5f  jnz     loc_14004A1BC
0x140049e65  cmp     ebp, 1
0x140049e68  jz      loc_14004A212
0x140049e6e  mov     eax, cs:MRxSmbInitialSrvOpenFlags
0x140049e74  or      [r13+48h], eax
0x140049e78  mov     [rsi+2E4h], ebx
0x140049e7e  mov     [rsi+2E0h], edi
0x140049e84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049e8b  cmp     rcx, r9
0x140049e8e  jnz     loc_14004A21F
0x140049e94  mov     edi, [rsp+128h+var_C0]
0x140049e98  test    edi, edi
0x140049e9a  jz      loc_14004A261
0x140049ea0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140049ea7  cmp     rcx, r9
0x140049eaa  jnz     loc_14004A271
0x140049eb0  mov     eax, edi
0x140049eb2  jmp     loc_140049B22
0x140049eb7  movzx   eax, [rsp+128h+arg_28]
0x140049ebf  cmp     [r12+0Ah], al
0x140049ec4  jz      loc_14004A296
0x140049eca  mov     r10, [rdx+30h]
0x140049ece  test    r10, r10
0x140049ed1  jz      loc_14004A296
0x140049ed7  test    al, al
0x140049ed9  jz      short loc_140049EE8
0x140049edb  cmp     eax, 1
0x140049ede  jnz     short loc_140049EE8
0x140049ee0  mov     r9d, 3
0x140049ee6  jmp     short loc_140049EEB
0x140049ee8  xor     r9d, r9d
0x140049eeb  movzx   edx, word ptr [rbx+72h]
0x140049eef  xor     r8d, r8d
0x140049ef2  shl     rdx, 10h
0x140049ef6  mov     rcx, r10
0x140049ef9  or      rdx, r15
0x140049efc  mov     [rsp+128h+var_50], rdi
0x140049f04  mov     [rsp+128h+var_58], rdx
0x140049f0c  lea     rdx, [rsp+128h+var_58]
0x140049f14  call    cs:__imp_RxIndicateChangeOfOplockState
0x140049f1b  nop     dword ptr [rax+rax+00h]
0x140049f20  jmp     loc_14004A28F
0x140049f25  test    dword ptr [rcx+2Ch], 100h
0x140049f2c  jz      loc_140049B1D
0x140049f32  mov     edx, 2Bh ; '+'
0x140049f37  mov     r9, r13
0x140049f3a  jmp     loc_140049BBA
0x140049f3f  test    dword ptr [rcx+2Ch], 400h
0x140049f46  jz      loc_140049C28
0x140049f4c  mov     r9d, [rsp+128h+var_D8]
0x140049f51  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140049f58  mov     rcx, [rcx+18h]
0x140049f5c  mov     edx, 2Dh ; '-'
0x140049f61  mov     dword ptr [rsp+128h+var_100], ebx
0x140049f65  mov     dword ptr [rsp+128h+var_108], r15d
  ... truncated ...
```
