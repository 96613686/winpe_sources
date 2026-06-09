# DXG_HOST_GLOBAL_VMBUS::VmBusCreateProcess(DXGADAPTER_VMBUS_PACKET *)

- ea: `0x1401a7f80`
- end: `0x1401a8579`
- name: `?VmBusCreateProcess@DXG_HOST_GLOBAL_VMBUS@@SAEPEAUDXGADAPTER_VMBUS_PACKET@@@Z`
- size: `1529`
- prototype: `unsigned __int8 __fastcall(struct DXGADAPTER_VMBUS_PACKET *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140012380`
- `0x140015288`
- `0x140015458`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001bd70`
- `0x1400491a8`
- `0x14004e888`
- `0x140079fe8`
- `0x14007d744`
- `0x1400a0100`
- `0x1401a7f80`
- `0x1402566e8`
- `0x140352dcc`
- `0x1403a3d50`
- `0x1403b5c74`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a84b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a84b3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a84a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1401a84a7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401a82c4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401a851d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401a82c4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1401a851d`
- `ntoskrnl!KeStackAttachProcess` at `0x1401a81ba`
- `ntoskrnl!KeStackAttachProcess` at `0x1401a81ba`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1401a802d`
- `ntoskrnl!RtlLogUnexpectedCodepath` at `0x1401a802d`
- `watchdog!WdLogSingleEntry0` at `0x1401a7fd6`
- `watchdog!WdLogSingleEntry0` at `0x1401a8068`
- `watchdog!WdLogSingleEntry0` at `0x1401a8106`
- `watchdog!WdLogSingleEntry0` at `0x1401a813a`
- `watchdog!WdLogSingleEntry0` at `0x1401a8186`
- `watchdog!WdLogSingleEntry0` at `0x1401a8271`
- `watchdog!WdLogSingleEntry0` at `0x1401a844a`
- `watchdog!WdLogSingleEntry0` at `0x1401a7fd6`
- `watchdog!WdLogSingleEntry0` at `0x1401a8068`
- `watchdog!WdLogSingleEntry0` at `0x1401a8106`
- `watchdog!WdLogSingleEntry0` at `0x1401a813a`
- `watchdog!WdLogSingleEntry0` at `0x1401a8186`
- `watchdog!WdLogSingleEntry0` at `0x1401a8271`
- `watchdog!WdLogSingleEntry0` at `0x1401a844a`
- `watchdog!WdLogSingleEntry1` at `0x1401a84d3`
- `watchdog!WdLogSingleEntry1` at `0x1401a84d3`

## string_xrefs

- `0x1401a814b`: `Too many VM processes created`
- `0x1401a8197`: `To  many VM processes created`
- `0x1401a84e4`: `Failed to create VM process: 0x%I64x`

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
    WdLogGlobalForLineNumber = 7329;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process flag, bWslProcess is not supported",
      7329,
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
    v6 = 7338;
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
    v6 = 7357;
    v7 = L"Invalid process Linux/WSL flags";
    goto LABEL_9;
  }
LABEL_19:
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)v9) > 0xFFFF )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 6599;
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Too many VM processes created", 6599, 0, 0, 0, 0);
    WdLogSingleEntry0(2);
    v6 = 7365;
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
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 7449;
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
    v18 = HMGRTABLE::AllocHandle(v8 + 280, v15, 12);
    v19 = v18;
    if ( !v18 )
    {
      DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v33);
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 7403;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to allocate process handle: 0x%I64x",
        7403,
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
0x1401a7f80  push    rbp
0x1401a7f82  push    rbx
0x1401a7f83  push    rsi
0x1401a7f84  push    rdi
0x1401a7f85  push    r12
0x1401a7f87  push    r13
0x1401a7f89  push    r14
0x1401a7f8b  push    r15
0x1401a7f8d  lea     rbp, [rsp-1Fh]
0x1401a7f92  sub     rsp, 0D8h
0x1401a7f99  mov     rax, cs:__security_cookie
0x1401a7fa0  xor     rax, rsp
0x1401a7fa3  mov     [rbp+57h+var_48], rax
0x1401a7fa7  mov     r13, rcx
0x1401a7faa  mov     [rbp+57h+var_88], rcx
0x1401a7fae  call    ??$CastToVmBusCommand@UDXGKVMB_COMMAND_CREATEPROCESS@@@@YAPEAUDXGKVMB_COMMAND_CREATEPROCESS@@PEAUDXGADAPTER_VMBUS_PACKET@@@Z; CastToVmBusCommand<DXGKVMB_COMMAND_CREATEPROCESS>(DXGADAPTER_VMBUS_PACKET *)
0x1401a7fb3  xor     r12d, r12d
0x1401a7fb6  mov     r14, rax
0x1401a7fb9  test    rax, rax
0x1401a7fbc  jz      loc_1401A8556
0x1401a7fc2  mov     dl, [rax+232h]
0x1401a7fc8  mov     [rbp+57h+var_A8], r12
0x1401a7fcc  test    dl, 10h
0x1401a7fcf  jz      short loc_1401A803E
0x1401a7fd1  lea     ecx, [r12+2]
0x1401a7fd6  call    cs:__imp_WdLogSingleEntry0
0x1401a7fdd  nop     dword ptr [rax+rax+00h]
0x1401a7fe2  mov     [rsp+110h+var_D0], r12
0x1401a7fe7  lea     r9, aInvalidProcess_0; "Invalid process flag, bWslProcess is no"...
0x1401a7fee  mov     [rsp+110h+var_D8], r12
0x1401a7ff3  mov     eax, 1CA1h
0x1401a7ff8  mov     [rsp+110h+var_E0], r12
0x1401a7ffd  or      r8d, 0FFFFFFFFh
0x1401a8001  mov     [rsp+110h+var_E8], r12
0x1401a8006  mov     edx, 40000h
0x1401a800b  xor     ecx, ecx
0x1401a800d  mov     [rsp+110h+var_F0], rax
0x1401a8012  mov     cs:WdLogGlobalForLineNumber, eax
0x1401a8018  call    DxgkLogInternalTriageEvent
0x1401a801d  lea     rcx, [rbp+57h+var_88]
0x1401a8021  mov     [rbp+57h+var_88], 375084Ch
0x1401a8029  mov     [rbp+57h+var_80], r12d
0x1401a802d  call    cs:__imp_RtlLogUnexpectedCodepath
0x1401a8034  nop     dword ptr [rax+rax+00h]
0x1401a8039  jmp     loc_1401A8556
0x1401a803e  mov     r10d, 1
0x1401a8044  mov     cl, dl
0x1401a8046  shr     cl, 1
0x1401a8048  mov     r8b, dl
0x1401a804b  and     cl, r10b
0x1401a804e  and     r8b, r10b
0x1401a8051  jz      short loc_1401A8057
0x1401a8053  test    cl, cl
0x1401a8055  jnz     short loc_1401A8063
0x1401a8057  mov     al, r8b
0x1401a805a  or      al, cl
0x1401a805c  jz      short loc_1401A80B4
0x1401a805e  test    dl, 4
0x1401a8061  jz      short loc_1401A80B4
0x1401a8063  mov     ecx, 2
0x1401a8068  call    cs:__imp_WdLogSingleEntry0
0x1401a806f  nop     dword ptr [rax+rax+00h]
0x1401a8074  mov     eax, 1CAAh
0x1401a8079  lea     r9, aInvalidProcess_2; "Invalid process flags"
0x1401a8080  mov     [rsp+110h+var_D0], r12
0x1401a8085  or      r8d, 0FFFFFFFFh
0x1401a8089  mov     [rsp+110h+var_D8], r12
0x1401a808e  mov     edx, 40000h
0x1401a8093  mov     [rsp+110h+var_E0], r12
0x1401a8098  xor     ecx, ecx
0x1401a809a  mov     [rsp+110h+var_E8], r12
0x1401a809f  mov     [rsp+110h+var_F0], rax
0x1401a80a4  mov     cs:WdLogGlobalForLineNumber, eax
0x1401a80aa  call    DxgkLogInternalTriageEvent
0x1401a80af  jmp     loc_1401A8556
0x1401a80b4  mov     r15, [r13+60h]
0x1401a80b8  mov     r9, [r15+258h]
0x1401a80bf  mov     eax, [r9+188h]
0x1401a80c6  cmp     eax, 1Fh
0x1401a80c9  jb      short loc_1401A80D7
0x1401a80cb  mov     dil, dl
0x1401a80ce  shr     dil, 4
0x1401a80d2  and     dil, r10b
0x1401a80d5  jmp     short loc_1401A80E2
0x1401a80d7  mov     sil, r12b
0x1401a80da  mov     dil, r12b
0x1401a80dd  cmp     eax, 1Bh
0x1401a80e0  jb      short loc_1401A8123
0x1401a80e2  mov     sil, dl
0x1401a80e5  shr     sil, 3
0x1401a80e9  and     sil, r10b
0x1401a80ec  jnz     short loc_1401A80F3
0x1401a80ee  test    dil, dil
0x1401a80f1  jz      short loc_1401A8123
0x1401a80f3  test    cl, cl
0x1401a80f5  jnz     short loc_1401A8101
0x1401a80f7  test    r8b, r8b
0x1401a80fa  jnz     short loc_1401A8101
0x1401a80fc  test    dl, 4
0x1401a80ff  jz      short loc_1401A8123
0x1401a8101  mov     ecx, 2
0x1401a8106  call    cs:__imp_WdLogSingleEntry0
0x1401a810d  nop     dword ptr [rax+rax+00h]
0x1401a8112  mov     eax, 1CBDh
0x1401a8117  lea     r9, aInvalidProcess_5; "Invalid process Linux/WSL flags"
0x1401a811e  jmp     loc_1401A8080
0x1401a8123  mov     eax, r10d
0x1401a8126  lock xadd [r9], eax
0x1401a812b  add     eax, r10d
0x1401a812e  cmp     eax, 0FFFFh
0x1401a8133  jbe     short loc_1401A81A3
0x1401a8135  mov     ecx, 2
0x1401a813a  call    cs:__imp_WdLogSingleEntry0
0x1401a8141  nop     dword ptr [rax+rax+00h]
0x1401a8146  mov     [rsp+110h+var_D0], r12
0x1401a814b  lea     r9, aTooManyVmProce; "Too many VM processes created"
0x1401a8152  mov     [rsp+110h+var_D8], r12
0x1401a8157  mov     eax, 19C7h
0x1401a815c  mov     [rsp+110h+var_E0], r12
0x1401a8161  or      r8d, 0FFFFFFFFh
0x1401a8165  mov     [rsp+110h+var_E8], r12
0x1401a816a  mov     edx, 40000h
0x1401a816f  xor     ecx, ecx
0x1401a8171  mov     [rsp+110h+var_F0], rax
0x1401a8176  mov     cs:WdLogGlobalForLineNumber, eax
0x1401a817c  call    DxgkLogInternalTriageEvent
0x1401a8181  mov     ecx, 2
0x1401a8186  call    cs:__imp_WdLogSingleEntry0
0x1401a818d  nop     dword ptr [rax+rax+00h]
0x1401a8192  mov     eax, 1CC5h
0x1401a8197  lea     r9, aToManyVmProces; "To  many VM processes created"
0x1401a819e  jmp     loc_1401A8080
0x1401a81a3  xorps   xmm0, xmm0
0x1401a81a6  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1401a81aa  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1401a81ae  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1401a81b2  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1401a81b6  mov     rcx, [r15+38h]; PROCESS
0x1401a81ba  call    cs:__imp_KeStackAttachProcess
0x1401a81c1  nop     dword ptr [rax+rax+00h]
0x1401a81c6  mov     r8, [r14+18h]; struct DXGPROCESS *
0x1401a81ca  lea     rcx, [rbp+57h+var_A8]; struct DXGPROCESS **
0x1401a81ce  xor     r9d, r9d; unsigned __int8
0x1401a81d1  mov     [rsp+110h+var_F0], r12; struct _EPROCESS *
0x1401a81d6  mov     rdx, r15; struct DXGPROCESS *
0x1401a81d9  call    ?CreateDxgProcess@DXGPROCESS@@SAJPEAPEAV1@PEAV1@1EPEAU_EPROCESS@@@Z; DXGPROCESS::CreateDxgProcess(DXGPROCESS * *,DXGPROCESS *,DXGPROCESS *,uchar,_EPROCESS *)
0x1401a81de  mov     [rbp+57h+var_B0], eax
0x1401a81e1  test    eax, eax
0x1401a81e3  js      loc_1401A84C5
0x1401a81e9  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401a81ee  lea     rbx, [rax+178h]
0x1401a81f5  mov     rcx, rbx; this
0x1401a81f8  call    ?Acquire@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Acquire(void)
0x1401a81fd  mov     rcx, r15; this
0x1401a8200  call    ?AcquireReference@DXGPROCESS@@QEAAXXZ; DXGPROCESS::AcquireReference(void)
0x1401a8205  mov     rcx, rbx; this
0x1401a8208  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1401a820d  mov     rbx, [rbp+57h+var_A8]
0x1401a8211  test    sil, sil
0x1401a8214  jz      short loc_1401A821D
0x1401a8216  or      dword ptr [rbx+198h], 20h
0x1401a821d  test    dil, dil
0x1401a8220  jz      short loc_1401A8234
0x1401a8222  mov     rax, [rbx+40h]
0x1401a8226  or      dword ptr [rbx+198h], 10h
0x1401a822d  mov     byte ptr [rax+88h], 1
0x1401a8234  mov     rdx, r15; struct DXGPROCESS *
0x1401a8237  lea     rcx, [rbp+57h+var_A0]; this
0x1401a823b  call    ??0DXGHANDLETABLELOCKEXCLUSIVE@@QEAA@PEAVDXGPROCESS@@@Z; DXGHANDLETABLELOCKEXCLUSIVE::DXGHANDLETABLELOCKEXCLUSIVE(DXGPROCESS *)
0x1401a8240  xor     edi, edi
0x1401a8242  lea     r12, [r15+118h]
0x1401a8249  xor     r9d, r9d
0x1401a824c  mov     dword ptr [rsp+110h+var_F0], edi
0x1401a8250  mov     rdx, rbx
0x1401a8253  mov     rcx, r12
0x1401a8256  lea     r8d, [rdi+0Ch]
0x1401a825a  call    ?AllocHandle@HMGRTABLE@@QEAAIPEAXW4_HMGRENTRY_TYPE@@IH@Z; HMGRTABLE::AllocHandle(void *,_HMGRENTRY_TYPE,uint,int)
0x1401a825f  mov     esi, eax
0x1401a8261  test    eax, eax
0x1401a8263  jnz     short loc_1401A82DE
0x1401a8265  lea     rcx, [rbp+57h+var_A0]; this
0x1401a8269  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401a826e  lea     ecx, [rdi+2]
0x1401a8271  call    cs:__imp_WdLogSingleEntry0
0x1401a8278  nop     dword ptr [rax+rax+00h]
0x1401a827d  mov     [rsp+110h+var_D0], rdi
0x1401a8282  lea     r9, aFailedToAlloca_50; "Failed to allocate process handle: 0x%I"...
0x1401a8289  mov     [rsp+110h+var_D8], rdi
0x1401a828e  mov     eax, 1CEBh
0x1401a8293  mov     [rsp+110h+var_E0], rdi
0x1401a8298  or      r8d, 0FFFFFFFFh
0x1401a829c  mov     [rsp+110h+var_E8], rdi
0x1401a82a1  mov     edx, 40000h
0x1401a82a6  xor     ecx, ecx
0x1401a82a8  mov     [rsp+110h+var_F0], rax
0x1401a82ad  mov     cs:WdLogGlobalForLineNumber, eax
0x1401a82b3  call    DxgkLogInternalTriageEvent
0x1401a82b8  mov     rcx, rbx; this
0x1401a82bb  call    ?DestroyDxgProcess@DXGPROCESS@@SAXPEAV1@@Z; DXGPROCESS::DestroyDxgProcess(DXGPROCESS *)
0x1401a82c0  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1401a82c4  call    cs:__imp_KeUnstackDetachProcess
0x1401a82cb  nop     dword ptr [rax+rax+00h]
0x1401a82d0  lea     rcx, [rbp+57h+var_A0]; this
0x1401a82d4  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401a82d9  jmp     loc_1401A8556
0x1401a82de  shr     eax, 6
0x1401a82e1  mov     r9d, 2000h
0x1401a82e7  and     eax, 0FFFFFFh
0x1401a82ec  mov     edi, eax
0x1401a82ee  add     rdi, rdi
0x1401a82f1  mov     r13d, eax
0x1401a82f4  cmp     eax, [r12+10h]
0x1401a82f9  jnb     short loc_1401A8327
0x1401a82fb  mov     r8, [r12]
0x1401a82ff  mov     ecx, esi
0x1401a8301  shr     ecx, 19h
0x1401a8304  and     ecx, 60h
0x1401a8307  mov     edx, [r8+rdi*8+8]
0x1401a830c  mov     eax, edx
0x1401a830e  and     eax, 60h
0x1401a8311  cmp     cl, al
0x1401a8313  jnz     short loc_1401A8327
0x1401a8315  test    r9d, edx
0x1401a8318  jnz     short loc_1401A8327
0x1401a831a  test    dl, 1Fh
0x1401a831d  jz      short loc_1401A8327
0x1401a831f  or      edx, r9d
0x1401a8322  mov     [r8+rdi*8+8], edx
0x1401a8327  lea     rcx, [rbp+57h+var_A0]; this
0x1401a832b  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401a8330  lea     rdx, [r14+28h]; unsigned __int16 *
0x1401a8334  mov     [rbx+284h], esi
0x1401a833a  mov     rcx, rbx; this
0x1401a833d  call    ?SetVmProcessName@DXGPROCESSVM@@QEAAXPEAG@Z; DXGPROCESSVM::SetVmProcessName(ushort *)
0x1401a8342  mov     rax, [r14+20h]
0x1401a8346  mov     rcx, [rbx+40h]
0x1401a834a  mov     [rcx+58h], rax
0x1401a834e  mov     al, [r14+232h]
0x1401a8355  test    al, 2
0x1401a8357  jz      short loc_1401A8362
0x1401a8359  or      dword ptr [rbx+198h], 4
0x1401a8360  jmp     short loc_1401A837A
0x1401a8362  test    al, 1
0x1401a8364  jz      short loc_1401A836F
0x1401a8366  or      dword ptr [rbx+198h], 1
0x1401a836d  jmp     short loc_1401A837A
0x1401a836f  test    al, 4
0x1401a8371  jz      short loc_1401A837A
0x1401a8373  or      dword ptr [rbx+198h], 8
0x1401a837a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+1, 1
0x1401a8381  jz      short loc_1401A83F1
0x1401a8383  mov     rax, [rbx+258h]
0x1401a838a  mov     r8, [rbx+260h]
0x1401a8391  mov     r10d, [rbx+198h]
0x1401a8398  mov     r11d, [rbx+1E8h]
0x1401a839f  mov     rdx, [rax+258h]
0x1401a83a6  mov     rax, [rbx+40h]
0x1401a83aa  mov     r9, [rax+58h]
0x1401a83ae  test    rax, rax
0x1401a83b1  jz      short loc_1401A83B9
0x1401a83b3  mov     rcx, [rax+50h]
0x1401a83b7  jmp     short loc_1401A83BB
0x1401a83b9  xor     ecx, ecx
0x1401a83bb  lea     rax, [r14+28h]
0x1401a83bf  mov     [rsp+110h+var_C0], rax
0x1401a83c4  mov     [rsp+110h+var_C8], rdx
0x1401a83c9  lea     rdx, EventCreateDxgProcessVm
0x1401a83d0  mov     [rsp+110h+var_D0], r8
0x1401a83d5  mov     [rsp+110h+var_D8], r9
0x1401a83da  mov     r9, rbx
0x1401a83dd  mov     dword ptr [rsp+110h+var_E0], r10d
0x1401a83e2  mov     dword ptr [rsp+110h+var_E8], r11d
0x1401a83e7  mov     [rsp+110h+var_F0], rcx
0x1401a83ec  call    McTemplateK0ppqqpppz_EtwWriteTransfer
0x1401a83f1  lea     r14, [r15+0F8h]
0x1401a83f8  mov     rcx, r14; this
0x1401a83fb  call    ?AcquireExclusive@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireExclusive(void)
0x1401a8400  cmp     r13d, [r12+10h]
0x1401a8405  jnb     loc_1401A849B
0x1401a840b  mov     r8, [r12]
0x1401a840f  mov     ecx, esi
0x1401a8411  shr     ecx, 19h
0x1401a8414  and     ecx, 60h
0x1401a8417  mov     edx, [r8+rdi*8+8]
0x1401a841c  mov     eax, edx
0x1401a841e  and     eax, 60h
0x1401a8421  cmp     cl, al
0x1401a8423  jnz     short loc_1401A849B
0x1401a8425  test    dl, 1Fh
0x1401a8428  jz      short loc_1401A849B
0x1401a842a  mov     ebx, esi
0x1401a842c  shr     rbx, 6
0x1401a8430  and     ebx, 0FFFFFFh
0x1401a8436  shl     rbx, 4
0x1401a843a  test    dword ptr [r8+rbx+8], 2000h
0x1401a8443  jnz     short loc_1401A8491
0x1401a8445  mov     ecx, 1
0x1401a844a  call    cs:__imp_WdLogSingleEntry0
0x1401a8451  nop     dword ptr [rax+rax+00h]
0x1401a8456  xor     ecx, ecx
  ... truncated ...
```
