# VidSchDestroyPeriodicFrameNotification

- ea: `0x1400526f0`
- end: `0x1400529a5`
- name: `VidSchDestroyPeriodicFrameNotification`
- size: `693`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14003d398`
- `0x140052240`

## callees

- `0x140004268`
- `0x140017750`
- `0x14001b910`
- `0x14001f640`
- `0x140027b90`
- `0x1400336d8`
- `0x140051d4c`
- `0x1400526f0`
- `0x140059030`
- `0x1401185a0`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140052768`
- `ntoskrnl!ExDeleteTimer` at `0x140052768`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052986`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052986`
- `watchdog!WdLogSingleEntry0` at `0x14005293b`
- `watchdog!WdLogSingleEntry0` at `0x14005293b`
- `watchdog!WdLogSingleEntry1` at `0x1400527c1`
- `watchdog!WdLogSingleEntry1` at `0x140052843`
- `watchdog!WdLogSingleEntry1` at `0x1400527c1`
- `watchdog!WdLogSingleEntry1` at `0x140052843`
- `dxgkrnl!DxgCoreInterface` at `0x140052794`

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
  if ( (byte_140087201 & 4) != 0 )
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
               *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 16LL) + 3248LL),
               &v21),
        v7 < 0) )
  {
    v8 = v7;
    WdLogSingleEntry1(1, v7);
    WdLogGlobalForLineNumber = 14748;
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
    WdLogGlobalForLineNumber = 14759;
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
    WdLogGlobalForLineNumber = 566;
    DxgkLogInternalTriageEvent(
      v19,
      262146,
      v20,
      (unsigned int)L"GetSyncObjectType() == D3DDDI_PERIODIC_MONITORED_FENCE",
      566,
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
0x1400526f0  push    rbp
0x1400526f2  push    rbx
0x1400526f3  push    rsi
0x1400526f4  push    rdi
0x1400526f5  push    r12
0x1400526f7  push    r14
0x1400526f9  push    r15
0x1400526fb  lea     rbp, [rsp-27h]
0x140052700  sub     rsp, 0A0h
0x140052707  xor     r12d, r12d
0x14005270a  lea     rsi, [rcx+8]
0x14005270e  test    cs:byte_140087201, 4
0x140052715  mov     rdi, rcx
0x140052718  jz      short loc_140052756
0x14005271a  mov     rax, [rcx+28h]
0x14005271e  lea     rdx, EventDestroyPeriodicFrameNotification
0x140052725  mov     r9, [rcx]
0x140052728  mov     [rsp+0D0h+var_88], rax
0x14005272d  mov     rax, [rcx+20h]
0x140052731  mov     [rsp+0D0h+var_90], rax
0x140052736  mov     eax, [rcx+18h]
0x140052739  mov     dword ptr [rsp+0D0h+var_98], eax
0x14005273d  mov     rax, [rcx+10h]
0x140052741  mov     [rsp+0D0h+var_A0], r12
0x140052746  mov     [rsp+0D0h+var_A8], rax
0x14005274b  mov     eax, [rsi]
0x14005274d  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140052751  call    McTemplateK0pqxxqpp_EtwWriteTransfer
0x140052756  mov     rcx, [rdi+28h]
0x14005275a  test    rcx, rcx
0x14005275d  jz      short loc_140052774
0x14005275f  mov     r8b, 1
0x140052762  xor     r9d, r9d
0x140052765  mov     dl, r8b
0x140052768  call    cs:__imp_ExDeleteTimer
0x14005276f  nop     dword ptr [rax+rax+00h]
0x140052774  mov     rax, [rdi+20h]
0x140052778  test    rax, rax
0x14005277b  jz      loc_140052802
0x140052781  mov     [rbp+57h+var_80], rax
0x140052785  lea     rdx, [rbp+57h+var_80]
0x140052789  mov     rax, [rdi]
0x14005278c  mov     qword ptr [rbp+57h+var_78], r12
0x140052790  mov     rcx, [rax+8]
0x140052794  mov     rax, cs:DxgCoreInterface
0x14005279b  mov     rcx, [rcx+10h]
0x14005279f  mov     rax, [rax+258h]
0x1400527a6  mov     rcx, [rcx+0CB0h]
0x1400527ad  call    _guard_dispatch_icall
0x1400527b2  test    eax, eax
0x1400527b4  jns     short loc_140052802
0x1400527b6  movsxd  rbx, eax
0x1400527b9  mov     ecx, 1
0x1400527be  mov     rdx, rbx
0x1400527c1  call    cs:__imp_WdLogSingleEntry1
0x1400527c8  nop     dword ptr [rax+rax+00h]
0x1400527cd  mov     [rsp+0D0h+var_98], r12
0x1400527d2  lea     r9, aPeriodicMonito; "Periodic monitored fence failed to dest"...
0x1400527d9  mov     [rsp+0D0h+var_A0], r12
0x1400527de  mov     edx, 40000h
0x1400527e3  mov     [rsp+0D0h+var_A8], r12
0x1400527e8  mov     [rsp+0D0h+var_B0], rbx
0x1400527ed  mov     cs:WdLogGlobalForLineNumber, 399Ch
0x1400527f7  call    DxgkLogInternalTriageEvent
0x1400527fc  lea     rbx, [rdi+8]
0x140052800  jmp     short loc_140052805
0x140052802  mov     rbx, rsi
0x140052805  mov     rcx, [rdi]
0x140052808  xor     r8d, r8d
0x14005280b  mov     r9d, [rsi]
0x14005280e  mov     rcx, [rcx+8]; struct _VIDSCH_GLOBAL *
0x140052812  lea     edx, [r8+3]
0x140052816  call    VidSchControlVSyncAdapter
0x14005281b  test    eax, eax
0x14005281d  jns     short loc_140052894
0x14005281f  mov     rax, [rdi]
0x140052822  mov     r14d, 0FFFFFFFDh
0x140052828  mov     rcx, [rax+8]
0x14005282c  cmp     [rcx+0A14h], r12b
0x140052833  jz      short loc_140052839
0x140052835  mov     eax, [rbx]
0x140052837  jmp     short loc_14005283C
0x140052839  mov     eax, r14d
0x14005283c  mov     edx, eax
0x14005283e  mov     ecx, 1
0x140052843  call    cs:__imp_WdLogSingleEntry1
0x14005284a  nop     dword ptr [rax+rax+00h]
0x14005284f  mov     cs:WdLogGlobalForLineNumber, 39A7h
0x140052859  mov     rax, [rdi]
0x14005285c  mov     rcx, [rax+8]
0x140052860  cmp     [rcx+0A14h], r12b
0x140052867  jz      short loc_14005286C
0x140052869  mov     r14d, [rbx]
0x14005286c  mov     [rsp+0D0h+var_98], r12
0x140052871  lea     r9, aPeriodicMonito_0; "Periodic monitored fence failed to rele"...
0x140052878  mov     [rsp+0D0h+var_A0], r12
0x14005287d  mov     edx, 40000h
0x140052882  mov     eax, r14d
0x140052885  mov     [rsp+0D0h+var_A8], r12
0x14005288a  mov     [rsp+0D0h+var_B0], rax
0x14005288f  call    DxgkLogInternalTriageEvent
0x140052894  mov     rax, [rdi]
0x140052897  lea     rcx, [rbp+57h+var_60]; this
0x14005289b  xor     r9d, r9d; bool
0x14005289e  mov     r8b, 1; bool
0x1400528a1  mov     rdx, [rax+8]
0x1400528a5  add     rdx, 830h; unsigned __int64 *
0x1400528ac  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x1400528b1  mov     rdx, [rdi]
0x1400528b4  xorps   xmm0, xmm0
0x1400528b7  mov     ecx, [rsi]
0x1400528b9  mov     r8b, 1; bool
0x1400528bc  mov     rax, [rdx+8]
0x1400528c0  mov     [rbp+57h+var_80], rax
0x1400528c4  lea     rax, [rbp+57h+var_78]
0x1400528c8  movups  [rbp+57h+var_78], xmm0
0x1400528cc  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400528d0  lea     rax, [rbp+57h+var_78]
0x1400528d4  mov     qword ptr [rbp+57h+var_78], rax
0x1400528d8  mov     [rbp+57h+var_68], r12b
0x1400528dc  mov     [rbp+57h+var_64], 2
0x1400528e3  mov     rax, [rdx+8]
0x1400528e7  mov     rdx, [rax+rcx*8+0DC8h]
0x1400528ef  mov     eax, [rdi+18h]
0x1400528f2  movzx   ecx, al
0x1400528f5  mov     rax, [rdx+13478h]
0x1400528fc  lea     rdx, [rbp+57h+var_80]; struct HwQueueStagingList *
0x140052900  mov     [rax+rcx*8], r12
0x140052904  mov     rcx, [rdi]; this
0x140052907  call    ?SetToAlwaysSignaled@_VIDSCH_SYNC_OBJECT@@QEAAXPEAVHwQueueStagingList@@_N@Z; _VIDSCH_SYNC_OBJECT::SetToAlwaysSignaled(HwQueueStagingList *,bool)
0x14005290c  lea     rcx, [rbp+57h+var_80]; this
0x140052910  call    ??1HwQueueStagingList@@QEAA@XZ; HwQueueStagingList::~HwQueueStagingList(void)
0x140052915  lea     rcx, [rbp+57h+var_60]; this
0x140052919  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14005291e  mov     rcx, [rdi]; P
0x140052921  call    VidSchiReleaseSyncObjectReference
0x140052926  mov     rax, [rdi]
0x140052929  mov     rbx, [rax+10h]
0x14005292d  cmp     dword ptr [rbx+1A4h], 6
0x140052934  jz      short loc_140052977
0x140052936  mov     ecx, 1
0x14005293b  call    cs:__imp_WdLogSingleEntry0
0x140052942  nop     dword ptr [rax+rax+00h]
0x140052947  mov     [rsp+0D0h+var_98], r12
0x14005294c  lea     r9, aGetsyncobjectt; "GetSyncObjectType() == D3DDDI_PERIODIC_"...
0x140052953  mov     eax, 236h
0x140052958  mov     [rsp+0D0h+var_A0], r12
0x14005295d  mov     [rsp+0D0h+var_A8], r12
0x140052962  mov     edx, 40002h
0x140052967  mov     cs:WdLogGlobalForLineNumber, eax
0x14005296d  mov     [rsp+0D0h+var_B0], rax
0x140052972  call    DxgkLogInternalTriageEvent
0x140052977  mov     edx, 62616956h; Tag
0x14005297c  mov     [rbx+0C0h], r12
0x140052983  mov     rcx, rdi; P
0x140052986  call    cs:__imp_ExFreePoolWithTag
0x14005298d  nop     dword ptr [rax+rax+00h]
0x140052992  add     rsp, 0A0h
0x140052999  pop     r15
0x14005299b  pop     r14
0x14005299d  pop     r12
0x14005299f  pop     rdi
0x1400529a0  pop     rsi
0x1400529a1  pop     rbx
0x1400529a2  pop     rbp
0x1400529a3  retn
```
