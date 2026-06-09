# VidSchDestroyPeriodicFrameNotification

- ea: `0x140051fe0`
- end: `0x140052295`
- name: `VidSchDestroyPeriodicFrameNotification`
- size: `693`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14003e9d8`
- `0x140051b30`

## callees

- `0x1400045ec`
- `0x14001bff0`
- `0x14001ca80`
- `0x140021c90`
- `0x14002a250`
- `0x140034de8`
- `0x14005163c`
- `0x140051fe0`
- `0x140058760`
- `0x1401149e0`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140052058`
- `ntoskrnl!ExDeleteTimer` at `0x140052058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052276`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052276`
- `watchdog!WdLogSingleEntry0` at `0x14005222b`
- `watchdog!WdLogSingleEntry0` at `0x14005222b`
- `watchdog!WdLogSingleEntry1` at `0x1400520b1`
- `watchdog!WdLogSingleEntry1` at `0x140052133`
- `watchdog!WdLogSingleEntry1` at `0x1400520b1`
- `watchdog!WdLogSingleEntry1` at `0x140052133`
- `dxgkrnl!DxgCoreInterface` at `0x140052084`

## pseudocode

```c
void __fastcall VidSchDestroyPeriodicFrameNotification(_QWORD *P, __int64 a2, __int64 a3)
{
  unsigned int *v3; // rsi
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rbx
  int v9; // ecx
  int v10; // r8d
  unsigned int *v11; // rbx
  unsigned int v12; // r14d
  unsigned int v13; // eax
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rbx
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v22[2]; // [rsp+58h] [rbp-21h] BYREF
  char v23; // [rsp+68h] [rbp-11h]
  int v24; // [rsp+6Ch] [rbp-Dh]
  _BYTE v25[96]; // [rsp+70h] [rbp-9h] BYREF

  v3 = (unsigned int *)(P + 1);
  if ( (byte_140086201 & 4) != 0 )
    McTemplateK0pqxxqpp_EtwWriteTransfer(
      (_DWORD)P,
      (unsigned int)EventDestroyPeriodicFrameNotification,
      a3,
      *P,
      *v3,
      P[2],
      0,
      *((_DWORD *)P + 6),
      P[4],
      P[5]);
  v5 = P[5];
  if ( v5 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(a2) = 1;
    ExDeleteTimer(v5, a2, a3, 0);
  }
  if ( P[4]
    && (v21 = P[4],
        v6 = *P,
        v22[0] = 0,
        v7 = ((__int64 (__fastcall *)(_QWORD, __int64 *))DxgCoreInterface[75])(
               *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 16LL) + 3232LL),
               &v21),
        v7 < 0) )
  {
    v8 = v7;
    WdLogSingleEntry1(1, v7);
    WdLogGlobalForLineNumber = 14719;
    DxgkLogInternalTriageEvent(
      v9,
      0x40000,
      v10,
      (unsigned int)L"Periodic monitored fence failed to destroy KMD notification, Status: 0x%I64x",
      v8,
      0,
      0,
      0);
    v11 = (unsigned int *)(P + 1);
  }
  else
  {
    v11 = v3;
  }
  if ( (int)VidSchControlVSyncAdapter(*(struct _VIDSCH_GLOBAL **)(*P + 8LL)) < 0 )
  {
    v12 = -3;
    if ( *(_BYTE *)(*(_QWORD *)(*P + 8LL) + 2580LL) )
      v13 = *v11;
    else
      v13 = -3;
    WdLogSingleEntry1(1, v13);
    WdLogGlobalForLineNumber = 14730;
    v15 = *(_QWORD *)(*P + 8LL);
    if ( *(_BYTE *)(v15 + 2580) )
      v12 = *v11;
    DxgkLogInternalTriageEvent(
      v15,
      0x40000,
      v14,
      (unsigned int)L"Periodic monitored fence failed to release VSync for VidPnSourceID:0x%I64x.",
      v12,
      0,
      0,
      0);
  }
  AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v25, (unsigned __int64 *)(*(_QWORD *)(*P + 8LL) + 2096LL), 1, 0);
  v16 = *P;
  v17 = *v3;
  v21 = *(_QWORD *)(*P + 8LL);
  v22[1] = v22;
  v22[0] = v22;
  v23 = 0;
  v24 = 2;
  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v17 + 3528) + 78968LL)
            + 8LL * (unsigned __int8)*((_DWORD *)P + 6)) = 0;
  _VIDSCH_SYNC_OBJECT::SetToAlwaysSignaled((_VIDSCH_SYNC_OBJECT *)*P, (struct HwQueueStagingList *)&v21, 1);
  HwQueueStagingList::~HwQueueStagingList((HwQueueStagingList *)&v21);
  AcquireSpinLock::Release((AcquireSpinLock *)v25);
  VidSchiReleaseSyncObjectReference((PVOID)*P);
  v18 = *(_QWORD *)(*P + 16LL);
  if ( *(_DWORD *)(v18 + 420) != 6 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    DxgkLogInternalTriageEvent(
      v19,
      262146,
      v20,
      (unsigned int)L"GetSyncObjectType() == D3DDDI_PERIODIC_MONITORED_FENCE",
      561,
      0,
      0,
      0);
  }
  *(_QWORD *)(v18 + 192) = 0;
  ExFreePoolWithTag(P, 0x62616956u);
}

```

## disassembly

```asm
0x140051fe0  push    rbp
0x140051fe2  push    rbx
0x140051fe3  push    rsi
0x140051fe4  push    rdi
0x140051fe5  push    r12
0x140051fe7  push    r14
0x140051fe9  push    r15
0x140051feb  lea     rbp, [rsp-27h]
0x140051ff0  sub     rsp, 0A0h
0x140051ff7  xor     r12d, r12d
0x140051ffa  lea     rsi, [rcx+8]
0x140051ffe  test    cs:byte_140086201, 4
0x140052005  mov     rdi, rcx
0x140052008  jz      short loc_140052046
0x14005200a  mov     rax, [rcx+28h]
0x14005200e  lea     rdx, EventDestroyPeriodicFrameNotification
0x140052015  mov     r9, [rcx]
0x140052018  mov     [rsp+0D0h+var_88], rax
0x14005201d  mov     rax, [rcx+20h]
0x140052021  mov     [rsp+0D0h+var_90], rax
0x140052026  mov     eax, [rcx+18h]
0x140052029  mov     dword ptr [rsp+0D0h+var_98], eax
0x14005202d  mov     rax, [rcx+10h]
0x140052031  mov     [rsp+0D0h+var_A0], r12
0x140052036  mov     [rsp+0D0h+var_A8], rax
0x14005203b  mov     eax, [rsi]
0x14005203d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140052041  call    McTemplateK0pqxxqpp_EtwWriteTransfer
0x140052046  mov     rcx, [rdi+28h]
0x14005204a  test    rcx, rcx
0x14005204d  jz      short loc_140052064
0x14005204f  mov     r8b, 1
0x140052052  xor     r9d, r9d
0x140052055  mov     dl, r8b
0x140052058  call    cs:__imp_ExDeleteTimer
0x14005205f  nop     dword ptr [rax+rax+00h]
0x140052064  mov     rax, [rdi+20h]
0x140052068  test    rax, rax
0x14005206b  jz      loc_1400520F2
0x140052071  mov     [rbp+57h+var_80], rax
0x140052075  lea     rdx, [rbp+57h+var_80]
0x140052079  mov     rax, [rdi]
0x14005207c  mov     qword ptr [rbp+57h+var_78], r12
0x140052080  mov     rcx, [rax+8]
0x140052084  mov     rax, cs:DxgCoreInterface
0x14005208b  mov     rcx, [rcx+10h]
0x14005208f  mov     rax, [rax+258h]
0x140052096  mov     rcx, [rcx+0CA0h]
0x14005209d  call    _guard_dispatch_icall
0x1400520a2  test    eax, eax
0x1400520a4  jns     short loc_1400520F2
0x1400520a6  movsxd  rbx, eax
0x1400520a9  mov     ecx, 1
0x1400520ae  mov     rdx, rbx
0x1400520b1  call    cs:__imp_WdLogSingleEntry1
0x1400520b8  nop     dword ptr [rax+rax+00h]
0x1400520bd  mov     [rsp+0D0h+var_98], r12
0x1400520c2  lea     r9, aPeriodicMonito; "Periodic monitored fence failed to dest"...
0x1400520c9  mov     [rsp+0D0h+var_A0], r12
0x1400520ce  mov     edx, 40000h
0x1400520d3  mov     [rsp+0D0h+var_A8], r12
0x1400520d8  mov     [rsp+0D0h+var_B0], rbx
0x1400520dd  mov     cs:WdLogGlobalForLineNumber, 397Fh
0x1400520e7  call    DxgkLogInternalTriageEvent
0x1400520ec  lea     rbx, [rdi+8]
0x1400520f0  jmp     short loc_1400520F5
0x1400520f2  mov     rbx, rsi
0x1400520f5  mov     rcx, [rdi]
0x1400520f8  xor     r8d, r8d
0x1400520fb  mov     r9d, [rsi]
0x1400520fe  mov     rcx, [rcx+8]; struct _VIDSCH_GLOBAL *
0x140052102  lea     edx, [r8+3]
0x140052106  call    VidSchControlVSyncAdapter
0x14005210b  test    eax, eax
0x14005210d  jns     short loc_140052184
0x14005210f  mov     rax, [rdi]
0x140052112  mov     r14d, 0FFFFFFFDh
0x140052118  mov     rcx, [rax+8]
0x14005211c  cmp     [rcx+0A14h], r12b
0x140052123  jz      short loc_140052129
0x140052125  mov     eax, [rbx]
0x140052127  jmp     short loc_14005212C
0x140052129  mov     eax, r14d
0x14005212c  mov     edx, eax
0x14005212e  mov     ecx, 1
0x140052133  call    cs:__imp_WdLogSingleEntry1
0x14005213a  nop     dword ptr [rax+rax+00h]
0x14005213f  mov     cs:WdLogGlobalForLineNumber, 398Ah
0x140052149  mov     rax, [rdi]
0x14005214c  mov     rcx, [rax+8]
0x140052150  cmp     [rcx+0A14h], r12b
0x140052157  jz      short loc_14005215C
0x140052159  mov     r14d, [rbx]
0x14005215c  mov     [rsp+0D0h+var_98], r12
0x140052161  lea     r9, aPeriodicMonito_0; "Periodic monitored fence failed to rele"...
0x140052168  mov     [rsp+0D0h+var_A0], r12
0x14005216d  mov     edx, 40000h
0x140052172  mov     eax, r14d
0x140052175  mov     [rsp+0D0h+var_A8], r12
0x14005217a  mov     [rsp+0D0h+var_B0], rax
0x14005217f  call    DxgkLogInternalTriageEvent
0x140052184  mov     rax, [rdi]
0x140052187  lea     rcx, [rbp+57h+var_60]; this
0x14005218b  xor     r9d, r9d; bool
0x14005218e  mov     r8b, 1; bool
0x140052191  mov     rdx, [rax+8]
0x140052195  add     rdx, 830h; unsigned __int64 *
0x14005219c  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x1400521a1  mov     rdx, [rdi]
0x1400521a4  xorps   xmm0, xmm0
0x1400521a7  mov     ecx, [rsi]
0x1400521a9  mov     r8b, 1; bool
0x1400521ac  mov     rax, [rdx+8]
0x1400521b0  mov     [rbp+57h+var_80], rax
0x1400521b4  lea     rax, [rbp+57h+var_78]
0x1400521b8  movups  [rbp+57h+var_78], xmm0
0x1400521bc  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400521c0  lea     rax, [rbp+57h+var_78]
0x1400521c4  mov     qword ptr [rbp+57h+var_78], rax
0x1400521c8  mov     [rbp+57h+var_68], r12b
0x1400521cc  mov     [rbp+57h+var_64], 2
0x1400521d3  mov     rax, [rdx+8]
0x1400521d7  mov     rdx, [rax+rcx*8+0DC8h]
0x1400521df  mov     eax, [rdi+18h]
0x1400521e2  movzx   ecx, al
0x1400521e5  mov     rax, [rdx+13478h]
0x1400521ec  lea     rdx, [rbp+57h+var_80]; struct HwQueueStagingList *
0x1400521f0  mov     [rax+rcx*8], r12
0x1400521f4  mov     rcx, [rdi]; this
0x1400521f7  call    ?SetToAlwaysSignaled@_VIDSCH_SYNC_OBJECT@@QEAAXPEAVHwQueueStagingList@@_N@Z; _VIDSCH_SYNC_OBJECT::SetToAlwaysSignaled(HwQueueStagingList *,bool)
0x1400521fc  lea     rcx, [rbp+57h+var_80]; this
0x140052200  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x140052205  lea     rcx, [rbp+57h+var_60]; this
0x140052209  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14005220e  mov     rcx, [rdi]; P
0x140052211  call    VidSchiReleaseSyncObjectReference
0x140052216  mov     rax, [rdi]
0x140052219  mov     rbx, [rax+10h]
0x14005221d  cmp     dword ptr [rbx+1A4h], 6
0x140052224  jz      short loc_140052267
0x140052226  mov     ecx, 1
0x14005222b  call    cs:__imp_WdLogSingleEntry0
0x140052232  nop     dword ptr [rax+rax+00h]
0x140052237  mov     [rsp+0D0h+var_98], r12
0x14005223c  lea     r9, aGetsyncobjectt; "GetSyncObjectType() == D3DDDI_PERIODIC_"...
0x140052243  mov     eax, 231h
0x140052248  mov     [rsp+0D0h+var_A0], r12
0x14005224d  mov     [rsp+0D0h+var_A8], r12
0x140052252  mov     edx, 40002h
0x140052257  mov     cs:WdLogGlobalForLineNumber, eax
0x14005225d  mov     [rsp+0D0h+var_B0], rax
0x140052262  call    DxgkLogInternalTriageEvent
0x140052267  mov     edx, 62616956h; Tag
0x14005226c  mov     [rbx+0C0h], r12
0x140052273  mov     rcx, rdi; P
0x140052276  call    cs:__imp_ExFreePoolWithTag
0x14005227d  nop     dword ptr [rax+rax+00h]
0x140052282  add     rsp, 0A0h
0x140052289  pop     r15
0x14005228b  pop     r14
0x14005228d  pop     r12
0x14005228f  pop     rdi
0x140052290  pop     rsi
0x140052291  pop     rbx
0x140052292  pop     rbp
0x140052293  retn
```
