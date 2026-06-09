# DXG_HOST_GLOBAL_VMBUS::VmBusCreateProcess(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x1401ac240`
- end: `0x1401ac839`
- name: `?VmBusCreateProcess@DXG_HOST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1529`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140012540`
- `0x140015448`
- `0x140015618`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001bea0`
- `0x1400493a8`
- `0x14004ea88`
- `0x14007a6f8`
- `0x14007e044`
- `0x1400a0bd0`
- `0x1401ac240`
- `0x14025ad38`
- `0x14035327c`
- `0x1403a4b30`
- `0x1403b6104`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac773`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401ac773`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac767`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401ac767`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac584`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac7dd`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac584`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401ac7dd`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac47a`
- `ntoskrnl!KeStackAttachProcess` at `0x1401ac47a`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1401ac2ed`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1401ac2ed`
- `watchdog!WdLogSingleEntry0` at `0x1401ac296`
- `watchdog!WdLogSingleEntry0` at `0x1401ac328`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3c6`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3fa`
- `watchdog!WdLogSingleEntry0` at `0x1401ac446`
- `watchdog!WdLogSingleEntry0` at `0x1401ac531`
- `watchdog!WdLogSingleEntry0` at `0x1401ac70a`
- `watchdog!WdLogSingleEntry0` at `0x1401ac296`
- `watchdog!WdLogSingleEntry0` at `0x1401ac328`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3c6`
- `watchdog!WdLogSingleEntry0` at `0x1401ac3fa`
- `watchdog!WdLogSingleEntry0` at `0x1401ac446`
- `watchdog!WdLogSingleEntry0` at `0x1401ac531`
- `watchdog!WdLogSingleEntry0` at `0x1401ac70a`
- `watchdog!WdLogSingleEntry1` at `0x1401ac793`
- `watchdog!WdLogSingleEntry1` at `0x1401ac793`

## string_xrefs

- `0x1401ac40b`: `Too many VM processes created`
- `0x1401ac457`: `To  many VM processes created`
- `0x1401ac7a4`: `Failed to create VM process: 0x%I64x`

## pseudocode

```c
unsigned __int8 __fastcall DXG_HOST_GLOBAL_VMBUS::VmBusCreateProcess(struct DXGADAPTER_VMBUS_PACKET *a1)
{
  struct DXGADAPTER_VMBUS_PACKET *v1; // r13
  __int64 v2; // rax
  __int64 v3; // r14
  char v4; // dl
  unsigned __int8 v5; // r8
  __int64 v6; // rax
  const wchar_t *v7; // r9
  __int64 v8; // r15
  __int64 v9; // r9
  unsigned int v10; // eax
  bool v11; // di
  bool v12; // si
  int v13; // eax
  DXGFASTMUTEX *v14; // rbx
  DXGPROCESSVM *v15; // rbx
  __int64 v16; // rax
  _QWORD *v17; // r12
  unsigned int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // eax
  __int64 v21; // rdi
  unsigned int v22; // r13d
  int v23; // edx
  char v24; // al
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rbx
  struct VMBPACKETCOMPLETION__ *v29; // rcx
  int v31; // [rsp+60h] [rbp-59h] BYREF
  DXGPROCESSVM *v32; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v33[24]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v34; // [rsp+88h] [rbp-31h] BYREF
  int v35; // [rsp+90h] [rbp-29h]
  struct _KAPC_STATE ApcState; // [rsp+98h] [rbp-21h] BYREF

  v1 = a1;
  v34 = (__int64)a1;
  v2 = CastToVmBusCommand<DXGKVMB_COMMAND_CREATEPROCESS>();
  v3 = v2;
  if ( !v2 )
    return 0;
  v4 = *(_BYTE *)(v2 + 562);
  v32 = 0;
  if ( (v4 & 0x10) != 0 )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 7327;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process flag, bWslProcess is not supported",
      7327,
      0,
      0,
      0,
      0);
    v34 = 58001484;
    v35 = 0;
    RtlLogUnexpectedCodepath(&v34);
    return 0;
  }
  v5 = v4 & 1;
  if ( (v4 & 1) != 0 && (v4 & 2) != 0 || ((v4 & 2) != 0) | v5 && (v4 & 4) != 0 )
  {
    WdLogSingleEntry0(2);
    v6 = 7336;
    v7 = L"Invalid process flags";
LABEL_9:
    WdLogGlobalForLineNumber = v6;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v7, v6, 0, 0, 0, 0);
    return 0;
  }
  v8 = *((_QWORD *)v1 + 12);
  v9 = *(_QWORD *)(v8 + 600);
  v10 = *(_DWORD *)(v9 + 392);
  if ( v10 < 0x1F )
  {
    v12 = 0;
    v11 = 0;
    if ( v10 < 0x1B )
      goto LABEL_19;
  }
  else
  {
    v11 = (v4 & 0x10) != 0;
  }
  v12 = (v4 & 8) != 0;
  if ( ((v4 & 8) != 0 || v11) && ((v4 & 2) != 0 || v5 || (v4 & 4) != 0) )
  {
    WdLogSingleEntry0(2);
    v6 = 7355;
    v7 = L"Invalid process Linux/WSL flags";
    goto LABEL_9;
  }
LABEL_19:
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)v9) > 0xFFFF )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 6619;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Too many VM processes created", 6619, 0, 0, 0, 0);
    WdLogSingleEntry0(2);
    v6 = 7363;
    v7 = L"To  many VM processes created";
    goto LABEL_9;
  }
  memset(&ApcState, 0, sizeof(ApcState));
  KeStackAttachProcess(*(PRKPROCESS *)(v8 + 56), &ApcState);
  v13 = DXGPROCESS::CreateDxgProcess(&v32, (struct DXGPROCESS *)v8, *(struct DXGPROCESS **)(v3 + 24), 0, 0);
  v31 = v13;
  if ( v13 < 0 )
  {
    v28 = v13;
    v19 = 0;
    WdLogSingleEntry1(2, v13);
    WdLogGlobalForLineNumber = 7447;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Failed to create VM process: 0x%I64x", v28, 0, 0, 0, 0);
  }
  else
  {
    v14 = (struct DXGGLOBAL *)((char *)DXGGLOBAL::GetGlobal() + 376);
    DXGFASTMUTEX::Acquire(v14);
    DXGPROCESS::AcquireReference((DXGPROCESS *)v8);
    DXGFASTMUTEX::Release(v14);
    v15 = v32;
    if ( v12 )
      *((_DWORD *)v32 + 102) |= 0x20u;
    if ( v11 )
    {
      v16 = *((_QWORD *)v15 + 8);
      *((_DWORD *)v15 + 102) |= 0x10u;
      *(_BYTE *)(v16 + 136) = 1;
    }
    DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(
      (DXGHANDLETABLELOCKEXCLUSIVE *)v33,
      (struct DXGPROCESS *)v8);
    v17 = (_QWORD *)(v8 + 280);
    v18 = HMGRTABLE::AllocHandle(v8 + 280, v15, 12, 0, 0);
    v19 = v18;
    if ( !v18 )
    {
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 7401;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to allocate process handle: 0x%I64x",
        7401,
        0,
        0,
        0,
        0);
      DXGPROCESS::DestroyDxgProcess(v15);
      KeUnstackDetachProcess(&ApcState);
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
      return 0;
    }
    v20 = (v18 >> 6) & 0xFFFFFF;
    v21 = 2LL * v20;
    v22 = v20;
    if ( v20 < *(_DWORD *)(v8 + 296) )
    {
      v23 = *(_DWORD *)(*v17 + 16LL * v20 + 8);
      if ( ((v19 >> 25) & 0x60) == (*(_BYTE *)(*v17 + 16LL * v20 + 8) & 0x60)
        && (v23 & 0x2000) == 0
        && (v23 & 0x1F) != 0 )
      {
        *(_DWORD *)(*v17 + 16LL * v20 + 8) = v23 | 0x2000;
      }
    }
    DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
    *((_DWORD *)v15 + 161) = v19;
    DXGPROCESSVM::SetVmProcessName(v15, (unsigned __int16 *)(v3 + 40));
    *(_QWORD *)(*((_QWORD *)v15 + 8) + 88LL) = *(_QWORD *)(v3 + 32);
    v24 = *(_BYTE *)(v3 + 562);
    if ( (v24 & 2) != 0 )
    {
      *((_DWORD *)v15 + 102) |= 4u;
    }
    else if ( (v24 & 1) != 0 )
    {
      *((_DWORD *)v15 + 102) |= 1u;
    }
    else if ( (v24 & 4) != 0 )
    {
      *((_DWORD *)v15 + 102) |= 8u;
    }
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x100) != 0 )
    {
      v25 = *((_QWORD *)v15 + 8);
      if ( v25 )
        v26 = *(_QWORD *)(v25 + 80);
      else
        LODWORD(v26) = 0;
      McTemplateK0ppqqpppz_EtwWriteTransfer(
        v26,
        (unsigned int)EventCreateDxgProcessVm,
        *((_QWORD *)v15 + 76),
        (_DWORD)v15,
        v26,
        *((_DWORD *)v15 + 122),
        *((_DWORD *)v15 + 102),
        *(_QWORD *)(v25 + 88),
        *((_QWORD *)v15 + 76),
        *(_QWORD *)(*((_QWORD *)v15 + 75) + 600LL),
        v3 + 40);
    }
    DXGPUSHLOCK::AcquireExclusive((DXGPUSHLOCK *)(v8 + 248));
    if ( v22 < *(_DWORD *)(v8 + 296)
      && ((v19 >> 25) & 0x60) == (*(_BYTE *)(*v17 + 8 * v21 + 8) & 0x60)
      && (*(_DWORD *)(*v17 + 8 * v21 + 8) & 0x1F) != 0 )
    {
      v27 = 16LL * ((v19 >> 6) & 0xFFFFFF);
      if ( (*(_DWORD *)(*v17 + v27 + 8) & 0x2000) == 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 224;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"m_pEntryTable[GetIndex(hObject)].Destroyed",
          224,
          0,
          0,
          0,
          0);
      }
      *(_DWORD *)(*v17 + v27 + 8) &= ~0x2000u;
    }
    *(_QWORD *)(v8 + 256) = 0;
    ExReleasePushLockExclusiveEx(v8 + 248, 0);
    KeLeaveCriticalRegion();
    v1 = (struct DXGADAPTER_VMBUS_PACKET *)v34;
  }
  KeUnstackDetachProcess(&ApcState);
  if ( v31 >= 0 )
  {
    v29 = (struct VMBPACKETCOMPLETION__ *)*((_QWORD *)v1 + 16);
    v31 = v19;
    VmBusCompletePacket(v29, &v31, 4u);
    return 1;
  }
  _InterlockedDecrement(*(volatile signed __int32 **)(v8 + 600));
  return 0;
}

```

## disassembly

```asm
0x1401ac240  push    rbp
0x1401ac242  push    rbx
0x1401ac243  push    rsi
0x1401ac244  push    rdi
0x1401ac245  push    r12
0x1401ac247  push    r13
0x1401ac249  push    r14
0x1401ac24b  push    r15
0x1401ac24d  lea     rbp, [rsp-1Fh]
0x1401ac252  sub     rsp, 0D8h
0x1401ac259  mov     rax, cs:__security_cookie
0x1401ac260  xor     rax, rsp
0x1401ac263  mov     [rbp+57h+var_48], rax
0x1401ac267  mov     r13, rcx
0x1401ac26a  mov     [rbp+57h+var_88], rcx
0x1401ac26e  call    ??$CastToVmBusCommand@UDXGKVMB_COMMAND_CREATEPROCESS@@@@YAPEAUDXGKVMB_COMMAND_CREATEPROCESS@@PEAUDXGADAPTER_VMBUS_PACKET@@@Z; CastToVmBusCommand<DXGKVMB_COMMAND_CREATEPROCESS>(DXGADAPTER_VMBUS_PACKET *)
0x1401ac273  xor     r12d, r12d
0x1401ac276  mov     r14, rax
0x1401ac279  test    rax, rax
0x1401ac27c  jz      loc_1401AC816
0x1401ac282  mov     dl, [rax+232h]
0x1401ac288  mov     [rbp+57h+var_A8], r12
0x1401ac28c  test    dl, 10h
0x1401ac28f  jz      short loc_1401AC2FE
0x1401ac291  lea     ecx, [r12+2]
0x1401ac296  call    cs:__imp_WdLogSingleEntry0
0x1401ac29d  nop     dword ptr [rax+rax+00h]
0x1401ac2a2  mov     [rsp+110h+var_D0], r12
0x1401ac2a7  lea     r9, aInvalidProcess_0; "Invalid process flag, bWslProcess is no"...
0x1401ac2ae  mov     [rsp+110h+var_D8], r12
0x1401ac2b3  mov     eax, 1C9Fh
0x1401ac2b8  mov     [rsp+110h+var_E0], r12
0x1401ac2bd  or      r8d, 0FFFFFFFFh
0x1401ac2c1  mov     [rsp+110h+var_E8], r12
0x1401ac2c6  mov     edx, 40000h
0x1401ac2cb  xor     ecx, ecx
0x1401ac2cd  mov     [rsp+110h+var_F0], rax
0x1401ac2d2  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ac2d8  call    DxgkLogInternalTriageEvent
0x1401ac2dd  lea     rcx, [rbp+57h+var_88]
0x1401ac2e1  mov     [rbp+57h+var_88], 375084Ch
0x1401ac2e9  mov     [rbp+57h+var_80], r12d
0x1401ac2ed  call    cs:__imp_RtlLogUnexpectedCodepath
0x1401ac2f4  nop     dword ptr [rax+rax+00h]
0x1401ac2f9  jmp     loc_1401AC816
0x1401ac2fe  mov     r10d, 1
0x1401ac304  mov     cl, dl
0x1401ac306  shr     cl, 1
0x1401ac308  mov     r8b, dl
0x1401ac30b  and     cl, r10b
0x1401ac30e  and     r8b, r10b
0x1401ac311  jz      short loc_1401AC317
0x1401ac313  test    cl, cl
0x1401ac315  jnz     short loc_1401AC323
0x1401ac317  mov     al, r8b
0x1401ac31a  or      al, cl
0x1401ac31c  jz      short loc_1401AC374
0x1401ac31e  test    dl, 4
0x1401ac321  jz      short loc_1401AC374
0x1401ac323  mov     ecx, 2
0x1401ac328  call    cs:__imp_WdLogSingleEntry0
0x1401ac32f  nop     dword ptr [rax+rax+00h]
0x1401ac334  mov     eax, 1CA8h
0x1401ac339  lea     r9, aInvalidProcess_2; "Invalid process flags"
0x1401ac340  mov     [rsp+110h+var_D0], r12
0x1401ac345  or      r8d, 0FFFFFFFFh
0x1401ac349  mov     [rsp+110h+var_D8], r12
0x1401ac34e  mov     edx, 40000h
0x1401ac353  mov     [rsp+110h+var_E0], r12
0x1401ac358  xor     ecx, ecx
0x1401ac35a  mov     [rsp+110h+var_E8], r12
0x1401ac35f  mov     [rsp+110h+var_F0], rax
0x1401ac364  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ac36a  call    DxgkLogInternalTriageEvent
0x1401ac36f  jmp     loc_1401AC816
0x1401ac374  mov     r15, [r13+60h]
0x1401ac378  mov     r9, [r15+258h]
0x1401ac37f  mov     eax, [r9+188h]
0x1401ac386  cmp     eax, 1Fh
0x1401ac389  jb      short loc_1401AC397
0x1401ac38b  mov     dil, dl
0x1401ac38e  shr     dil, 4
0x1401ac392  and     dil, r10b
0x1401ac395  jmp     short loc_1401AC3A2
0x1401ac397  mov     sil, r12b
0x1401ac39a  mov     dil, r12b
0x1401ac39d  cmp     eax, 1Bh
0x1401ac3a0  jb      short loc_1401AC3E3
0x1401ac3a2  mov     sil, dl
0x1401ac3a5  shr     sil, 3
0x1401ac3a9  and     sil, r10b
0x1401ac3ac  jnz     short loc_1401AC3B3
0x1401ac3ae  test    dil, dil
0x1401ac3b1  jz      short loc_1401AC3E3
0x1401ac3b3  test    cl, cl
0x1401ac3b5  jnz     short loc_1401AC3C1
0x1401ac3b7  test    r8b, r8b
0x1401ac3ba  jnz     short loc_1401AC3C1
0x1401ac3bc  test    dl, 4
0x1401ac3bf  jz      short loc_1401AC3E3
0x1401ac3c1  mov     ecx, 2
0x1401ac3c6  call    cs:__imp_WdLogSingleEntry0
0x1401ac3cd  nop     dword ptr [rax+rax+00h]
0x1401ac3d2  mov     eax, 1CBBh
0x1401ac3d7  lea     r9, aInvalidProcess_5; "Invalid process Linux/WSL flags"
0x1401ac3de  jmp     loc_1401AC340
0x1401ac3e3  mov     eax, r10d
0x1401ac3e6  lock xadd [r9], eax
0x1401ac3eb  add     eax, r10d
0x1401ac3ee  cmp     eax, 0FFFFh
0x1401ac3f3  jbe     short loc_1401AC463
0x1401ac3f5  mov     ecx, 2
0x1401ac3fa  call    cs:__imp_WdLogSingleEntry0
0x1401ac401  nop     dword ptr [rax+rax+00h]
0x1401ac406  mov     [rsp+110h+var_D0], r12
0x1401ac40b  lea     r9, aTooManyVmProce; "Too many VM processes created"
0x1401ac412  mov     [rsp+110h+var_D8], r12
0x1401ac417  mov     eax, 19DBh
0x1401ac41c  mov     [rsp+110h+var_E0], r12
0x1401ac421  or      r8d, 0FFFFFFFFh
0x1401ac425  mov     [rsp+110h+var_E8], r12
0x1401ac42a  mov     edx, 40000h
0x1401ac42f  xor     ecx, ecx
0x1401ac431  mov     [rsp+110h+var_F0], rax
0x1401ac436  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ac43c  call    DxgkLogInternalTriageEvent
0x1401ac441  mov     ecx, 2
0x1401ac446  call    cs:__imp_WdLogSingleEntry0
0x1401ac44d  nop     dword ptr [rax+rax+00h]
0x1401ac452  mov     eax, 1CC3h
0x1401ac457  lea     r9, aToManyVmProces; "To  many VM processes created"
0x1401ac45e  jmp     loc_1401AC340
0x1401ac463  xorps   xmm0, xmm0
0x1401ac466  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1401ac46a  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1401ac46e  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1401ac472  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1401ac476  mov     rcx, [r15+38h]; PROCESS
0x1401ac47a  call    cs:__imp_KeStackAttachProcess
0x1401ac481  nop     dword ptr [rax+rax+00h]
0x1401ac486  mov     r8, [r14+18h]; struct DXGPROCESS *
0x1401ac48a  lea     rcx, [rbp+57h+var_A8]; struct DXGPROCESS **
0x1401ac48e  xor     r9d, r9d; unsigned __int8
0x1401ac491  mov     [rsp+110h+var_F0], r12; struct _EPROCESS *
0x1401ac496  mov     rdx, r15; struct DXGPROCESS *
0x1401ac499  call    ?CreateDxgProcess@DXGPROCESS@@SAJPEAPEAV1@PEAV1@1EPEAU_EPROCESS@@@Z; DXGPROCESS::CreateDxgProcess(DXGPROCESS * *,DXGPROCESS *,DXGPROCESS *,uchar,_EPROCESS *)
0x1401ac49e  mov     [rbp+57h+var_B0], eax
0x1401ac4a1  test    eax, eax
0x1401ac4a3  js      loc_1401AC785
0x1401ac4a9  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401ac4ae  lea     rbx, [rax+178h]
0x1401ac4b5  mov     rcx, rbx; this
0x1401ac4b8  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1401ac4bd  mov     rcx, r15; this
0x1401ac4c0  call    ?AcquireReference@DXGPROCESS@@QEAAXXZ; DXGPROCESS::AcquireReference(void)
0x1401ac4c5  mov     rcx, rbx; this
0x1401ac4c8  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1401ac4cd  mov     rbx, [rbp+57h+var_A8]
0x1401ac4d1  test    sil, sil
0x1401ac4d4  jz      short loc_1401AC4DD
0x1401ac4d6  or      dword ptr [rbx+198h], 20h
0x1401ac4dd  test    dil, dil
0x1401ac4e0  jz      short loc_1401AC4F4
0x1401ac4e2  mov     rax, [rbx+40h]
0x1401ac4e6  or      dword ptr [rbx+198h], 10h
0x1401ac4ed  mov     byte ptr [rax+88h], 1
0x1401ac4f4  mov     rdx, r15; struct DXGPROCESS *
0x1401ac4f7  lea     rcx, [rbp+57h+var_A0]; this
0x1401ac4fb  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x1401ac500  xor     edi, edi
0x1401ac502  lea     r12, [r15+118h]
0x1401ac509  xor     r9d, r9d
0x1401ac50c  mov     dword ptr [rsp+110h+var_F0], edi
0x1401ac510  mov     rdx, rbx
0x1401ac513  mov     rcx, r12
0x1401ac516  lea     r8d, [rdi+0Ch]
0x1401ac51a  call    ?AllocHandle@HMGRTABLE@@QEAAIPEAXW4_HMGRENTRY_TYPE@@IH@Z; HMGRTABLE::AllocHandle(void *,_HMGRENTRY_TYPE,uint,int)
0x1401ac51f  mov     esi, eax
0x1401ac521  test    eax, eax
0x1401ac523  jnz     short loc_1401AC59E
0x1401ac525  lea     rcx, [rbp+57h+var_A0]; this
0x1401ac529  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401ac52e  lea     ecx, [rdi+2]
0x1401ac531  call    cs:__imp_WdLogSingleEntry0
0x1401ac538  nop     dword ptr [rax+rax+00h]
0x1401ac53d  mov     [rsp+110h+var_D0], rdi
0x1401ac542  lea     r9, aFailedToAlloca_50; "Failed to allocate process handle: 0x%I"...
0x1401ac549  mov     [rsp+110h+var_D8], rdi
0x1401ac54e  mov     eax, 1CE9h
0x1401ac553  mov     [rsp+110h+var_E0], rdi
0x1401ac558  or      r8d, 0FFFFFFFFh
0x1401ac55c  mov     [rsp+110h+var_E8], rdi
0x1401ac561  mov     edx, 40000h
0x1401ac566  xor     ecx, ecx
0x1401ac568  mov     [rsp+110h+var_F0], rax
0x1401ac56d  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ac573  call    DxgkLogInternalTriageEvent
0x1401ac578  mov     rcx, rbx; this
0x1401ac57b  call    ?DestroyDxgProcess@DXGPROCESS@@SAXPEAV1@@Z; DXGPROCESS::DestroyDxgProcess(DXGPROCESS *)
0x1401ac580  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1401ac584  call    cs:__imp_KeUnstackDetachProcess
0x1401ac58b  nop     dword ptr [rax+rax+00h]
0x1401ac590  lea     rcx, [rbp+57h+var_A0]; this
0x1401ac594  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401ac599  jmp     loc_1401AC816
0x1401ac59e  shr     eax, 6
0x1401ac5a1  mov     r9d, 2000h
0x1401ac5a7  and     eax, 0FFFFFFh
0x1401ac5ac  mov     edi, eax
0x1401ac5ae  add     rdi, rdi
0x1401ac5b1  mov     r13d, eax
0x1401ac5b4  cmp     eax, [r12+10h]
0x1401ac5b9  jnb     short loc_1401AC5E7
0x1401ac5bb  mov     r8, [r12]
0x1401ac5bf  mov     ecx, esi
0x1401ac5c1  shr     ecx, 19h
0x1401ac5c4  and     ecx, 60h
0x1401ac5c7  mov     edx, [r8+rdi*8+8]
0x1401ac5cc  mov     eax, edx
0x1401ac5ce  and     eax, 60h
0x1401ac5d1  cmp     cl, al
0x1401ac5d3  jnz     short loc_1401AC5E7
0x1401ac5d5  test    r9d, edx
0x1401ac5d8  jnz     short loc_1401AC5E7
0x1401ac5da  test    dl, 1Fh
0x1401ac5dd  jz      short loc_1401AC5E7
0x1401ac5df  or      edx, r9d
0x1401ac5e2  mov     [r8+rdi*8+8], edx
0x1401ac5e7  lea     rcx, [rbp+57h+var_A0]; this
0x1401ac5eb  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401ac5f0  lea     rdx, [r14+28h]; unsigned __int16 *
0x1401ac5f4  mov     [rbx+284h], esi
0x1401ac5fa  mov     rcx, rbx; this
0x1401ac5fd  call    ?SetVmProcessName@DXGPROCESSVM@@QEAAXPEAG@Z; DXGPROCESSVM::SetVmProcessName(ushort *)
0x1401ac602  mov     rax, [r14+20h]
0x1401ac606  mov     rcx, [rbx+40h]
0x1401ac60a  mov     [rcx+58h], rax
0x1401ac60e  mov     al, [r14+232h]
0x1401ac615  test    al, 2
0x1401ac617  jz      short loc_1401AC622
0x1401ac619  or      dword ptr [rbx+198h], 4
0x1401ac620  jmp     short loc_1401AC63A
0x1401ac622  test    al, 1
0x1401ac624  jz      short loc_1401AC62F
0x1401ac626  or      dword ptr [rbx+198h], 1
0x1401ac62d  jmp     short loc_1401AC63A
0x1401ac62f  test    al, 4
0x1401ac631  jz      short loc_1401AC63A
0x1401ac633  or      dword ptr [rbx+198h], 8
0x1401ac63a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1401ac641  jz      short loc_1401AC6B1
0x1401ac643  mov     rax, [rbx+258h]
0x1401ac64a  mov     r8, [rbx+260h]
0x1401ac651  mov     r10d, [rbx+198h]
0x1401ac658  mov     r11d, [rbx+1E8h]
0x1401ac65f  mov     rdx, [rax+258h]
0x1401ac666  mov     rax, [rbx+40h]
0x1401ac66a  mov     r9, [rax+58h]
0x1401ac66e  test    rax, rax
0x1401ac671  jz      short loc_1401AC679
0x1401ac673  mov     rcx, [rax+50h]
0x1401ac677  jmp     short loc_1401AC67B
0x1401ac679  xor     ecx, ecx
0x1401ac67b  lea     rax, [r14+28h]
0x1401ac67f  mov     [rsp+110h+var_C0], rax
0x1401ac684  mov     [rsp+110h+var_C8], rdx
0x1401ac689  lea     rdx, EventCreateDxgProcessVm
0x1401ac690  mov     [rsp+110h+var_D0], r8
0x1401ac695  mov     [rsp+110h+var_D8], r9
0x1401ac69a  mov     r9, rbx
0x1401ac69d  mov     dword ptr [rsp+110h+var_E0], r10d
0x1401ac6a2  mov     dword ptr [rsp+110h+var_E8], r11d
0x1401ac6a7  mov     [rsp+110h+var_F0], rcx
0x1401ac6ac  call    McTemplateK0ppqqpppz_EtwWriteTransfer
0x1401ac6b1  lea     r14, [r15+0F8h]
0x1401ac6b8  mov     rcx, r14; this
0x1401ac6bb  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1401ac6c0  cmp     r13d, [r12+10h]
0x1401ac6c5  jnb     loc_1401AC75B
0x1401ac6cb  mov     r8, [r12]
0x1401ac6cf  mov     ecx, esi
0x1401ac6d1  shr     ecx, 19h
0x1401ac6d4  and     ecx, 60h
0x1401ac6d7  mov     edx, [r8+rdi*8+8]
0x1401ac6dc  mov     eax, edx
0x1401ac6de  and     eax, 60h
0x1401ac6e1  cmp     cl, al
0x1401ac6e3  jnz     short loc_1401AC75B
0x1401ac6e5  test    dl, 1Fh
0x1401ac6e8  jz      short loc_1401AC75B
0x1401ac6ea  mov     ebx, esi
0x1401ac6ec  shr     rbx, 6
0x1401ac6f0  and     ebx, 0FFFFFFh
0x1401ac6f6  shl     rbx, 4
0x1401ac6fa  test    dword ptr [r8+rbx+8], 2000h
0x1401ac703  jnz     short loc_1401AC751
0x1401ac705  mov     ecx, 1
0x1401ac70a  call    cs:__imp_WdLogSingleEntry0
0x1401ac711  nop     dword ptr [rax+rax+00h]
0x1401ac716  xor     ecx, ecx
  ... truncated ...
```
