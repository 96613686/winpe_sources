# SmbConstructNetRootExchangeFinalize

- ea: `0x14000fee0`
- end: `0x1400101e3`
- name: `SmbConstructNetRootExchangeFinalize`
- size: `771`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001e40`
- `0x140002470`
- `0x1400099a0`
- `0x14000dfd8`
- `0x14000e694`
- `0x14000fee0`
- `0x140010358`
- `0x14003eb2c`
- `0x140042d00`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140010109`
- `ntoskrnl!MmUnlockPages` at `0x140010109`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff0c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff0c`
- `ntoskrnl!IoFreeMdl` at `0x14001011c`
- `ntoskrnl!IoFreeMdl` at `0x140010147`
- `ntoskrnl!IoFreeMdl` at `0x14001011c`
- `ntoskrnl!IoFreeMdl` at `0x140010147`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010161`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010161`
- `rdbss!RxDiagnosticTrace` at `0x14001019c`
- `rdbss!RxDiagnosticTrace` at `0x14001019c`
- `rdbss!RxPostToWorkerThread` at `0x1400101c3`
- `rdbss!RxPostToWorkerThread` at `0x1400101c3`
- `rdbss!RxUnlockHeaderPages` at `0x140010134`
- `rdbss!RxUnlockHeaderPages` at `0x140010134`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000ffdb`
- `mrxsmb!MRxSmbDeviceObject` at `0x1400101a8`

## string_xrefs

- `0x140010189`: `Callback rdbss for create VNetRootCtxt %p Status %x`

## pseudocode

```c
__int64 __fastcall SmbConstructNetRootExchangeFinalize(unsigned int *Context, _BYTE *a2)
{
  __int64 v2; // rax
  __int64 v5; // r15
  int v6; // esi
  __int64 v7; // r14
  __int64 pContext; // rdi
  void (__stdcall *v9)(PVOID); // r12
  __int64 v10; // r13
  __int64 v11; // rbp
  int v12; // ecx
  __int64 v13; // rax
  int v14; // r9d
  struct _MDL *v15; // rcx
  __int64 v16; // rcx
  void *v17; // rcx

  v2 = *((_QWORD *)Context + 11);
  if ( v2 )
    v5 = *(_QWORD *)(v2 + 104);
  else
    v5 = 0;
  v6 = Context[12];
  if ( KeGetCurrentIrql() < 2u )
  {
    *a2 = 0;
    v7 = *((_QWORD *)Context + 11);
    pContext = *((_QWORD *)Context + 51);
    v9 = (void (__stdcall *)(PVOID))*((_QWORD *)Context + 46);
    v10 = *(_QWORD *)(v7 + 96);
    v11 = *(_QWORD *)(pContext + 264);
    *(_QWORD *)(pContext + 280) = 0;
    v12 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids, Context[12]);
    if ( v6 >= 0 )
    {
      if ( v11 )
      {
        SmbCeUpdateNetRoot(v5, *(_QWORD *)(v11 + 32));
        if ( *(_DWORD *)(v11 + 184) == 4 )
          *(_DWORD *)(v11 + 184) = 2;
      }
    }
    else
    {
      if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(
          v12,
          (unsigned int)CreateVNetRootError,
          *(_QWORD *)(pContext + 32) + 412,
          v6,
          155,
          0);
      v13 = *(_QWORD *)(pContext + 32);
      if ( v13 && (*(_BYTE *)(v13 + 749) & 8) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                        + MRxSmbLegacyPerfCtrs
                                                        + 188));
      *(_DWORD *)(pContext + 280) = v6;
      if ( v11 )
        *(_DWORD *)(v11 + 180) = v6;
      if ( *(_DWORD *)(pContext + 280) == -1073741816 )
        *(_DWORD *)(pContext + 280) = -1073741628;
      if ( *((_BYTE *)Context + 365) )
      {
        *(_DWORD *)(pContext + 284) = v6;
        if ( v6 == -1073741816 )
          *(_DWORD *)(pContext + 284) = -1073741628;
      }
      _InterlockedExchange((volatile __int32 *)(v7 + 12), 9);
    }
    MRxSmbTrackRefCount(v7, "SmbConstructNetRootExchangeFinalize", 1227);
    SmbReferenceRecord(v7 + 136, "SmbConstructNetRootExchangeFinalize", 1227);
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    SmbCeCompleteVNetRootContextInitialization((PVOID)v7);
    Context[18] &= ~0x200u;
    v14 = *(_DWORD *)(pContext + 284);
    if ( (v14 == -1073741299 || v14 == -1073741643)
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids,
        v7,
        v14,
        *(_DWORD *)(pContext + 280));
    }
    v15 = (struct _MDL *)*((_QWORD *)Context + 48);
    if ( v15 )
    {
      MmUnlockPages(v15);
      IoFreeMdl(*((PMDL *)Context + 48));
    }
    v16 = *((_QWORD *)Context + 47);
    if ( v16 )
    {
      RxUnlockHeaderPages(v16);
      IoFreeMdl(*((PMDL *)Context + 47));
    }
    v17 = (void *)*((_QWORD *)Context + 49);
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      *((_QWORD *)Context + 49) = 0;
    }
    SmbCeDiscardExchangeWorkerThreadRoutine(Context);
    if ( v10 )
      RxDiagnosticTrace(
        *(_QWORD *)(v10 + 16),
        1,
        "Callback rdbss for create VNetRootCtxt %p Status %x",
        (const void *)v7,
        v6);
    RxPostToWorkerThread(
      MRxSmbDeviceObject,
      CriticalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 200),
      v9,
      (PVOID)pContext);
  }
  else
  {
    *a2 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000fee0  push    rbx
0x14000fee2  push    rbp
0x14000fee3  push    rsi
0x14000fee4  push    rdi
0x14000fee5  push    r12
0x14000fee7  push    r13
0x14000fee9  push    r14
0x14000feeb  push    r15
0x14000feed  sub     rsp, 38h
0x14000fef1  mov     rax, [rcx+58h]
0x14000fef5  mov     rdi, rdx
0x14000fef8  mov     rbx, rcx
0x14000fefb  test    rax, rax
0x14000fefe  jz      short loc_14000FF06
0x14000ff00  mov     r15, [rax+68h]
0x14000ff04  jmp     short loc_14000FF09
0x14000ff06  xor     r15d, r15d
0x14000ff09  mov     esi, [rcx+30h]
0x14000ff0c  call    cs:__imp_KeGetCurrentIrql
0x14000ff13  nop     dword ptr [rax+rax+00h]
0x14000ff18  cmp     al, 2
0x14000ff1a  jb      short loc_14000FF24
0x14000ff1c  mov     byte ptr [rdi], 1
0x14000ff1f  jmp     loc_1400101CF
0x14000ff24  mov     byte ptr [rdi], 0
0x14000ff27  mov     r14, [rbx+58h]
0x14000ff2b  mov     rdi, [rbx+198h]
0x14000ff32  mov     r12, [rbx+170h]
0x14000ff39  mov     r13, [r14+60h]
0x14000ff3d  mov     rbp, [rdi+108h]
0x14000ff44  mov     qword ptr [rdi+118h], 0
0x14000ff4f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000ff56  lea     rax, WPP_GLOBAL_Control
0x14000ff5d  cmp     rcx, rax
0x14000ff60  jz      short loc_14000FF84
0x14000ff62  test    dword ptr [rcx+2Ch], 400h
0x14000ff69  jz      short loc_14000FF84
0x14000ff6b  mov     r9d, [rbx+30h]
0x14000ff6f  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x14000ff76  mov     rcx, [rcx+18h]
0x14000ff7a  mov     edx, 1Ah
0x14000ff7f  call    WPP_SF_d
0x14000ff84  test    esi, esi
0x14000ff86  jns     loc_14001003E
0x14000ff8c  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14000ff93  jz      short loc_14000FFBF
0x14000ff95  mov     r8, [rdi+20h]
0x14000ff99  lea     rdx, CreateVNetRootError
0x14000ffa0  add     r8, 19Ch
0x14000ffa7  mov     [rsp+78h+var_50], 0
0x14000ffaf  mov     r9d, esi
0x14000ffb2  mov     dword ptr [rsp+78h+pContext], 1020049Bh
0x14000ffba  call    McTemplateK0qqq_EtwWriteTransfer
0x14000ffbf  mov     rax, [rdi+20h]
0x14000ffc3  test    rax, rax
0x14000ffc6  jz      short loc_14000FFF1
0x14000ffc8  test    byte ptr [rax+2EDh], 8
0x14000ffcf  jz      short loc_14000FFF1
0x14000ffd1  mov     eax, gs:1A4h
0x14000ffd9  mov     edx, eax
0x14000ffdb  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14000ffe2  shl     rdx, 8
0x14000ffe6  mov     rcx, [rax]
0x14000ffe9  lock inc dword ptr [rdx+rcx+0BCh]
0x14000fff1  mov     [rdi+118h], esi
0x14000fff7  test    rbp, rbp
0x14000fffa  jz      short loc_140010002
0x14000fffc  mov     [rbp+0B4h], esi
0x140010002  mov     ecx, 0C0000008h
0x140010007  mov     eax, 0C00000C4h
0x14001000c  cmp     [rdi+118h], ecx
0x140010012  jnz     short loc_14001001A
0x140010014  mov     [rdi+118h], eax
0x14001001a  cmp     byte ptr [rbx+16Dh], 0
0x140010021  jz      short loc_140010033
0x140010023  mov     [rdi+11Ch], esi
0x140010029  cmp     esi, ecx
0x14001002b  jnz     short loc_140010033
0x14001002d  mov     [rdi+11Ch], eax
0x140010033  mov     eax, 9
0x140010038  xchg    eax, [r14+0Ch]
0x14001003c  jmp     short loc_140010062
0x14001003e  test    rbp, rbp
0x140010041  jz      short loc_140010062
0x140010043  mov     rdx, [rbp+20h]
0x140010047  mov     rcx, r15
0x14001004a  call    SmbCeUpdateNetRoot
0x14001004f  cmp     dword ptr [rbp+0B8h], 4
0x140010056  jnz     short loc_140010062
0x140010058  mov     dword ptr [rbp+0B8h], 2
0x140010062  mov     ebp, 4CBh
0x140010067  lea     rdx, aSmbconstructne; "SmbConstructNetRootExchangeFinalize"
0x14001006e  mov     r8d, ebp
0x140010071  mov     rcx, r14
0x140010074  call    MRxSmbTrackRefCount
0x140010079  lea     rcx, [r14+88h]
0x140010080  mov     r8d, ebp
0x140010083  lea     rdx, aSmbconstructne; "SmbConstructNetRootExchangeFinalize"
0x14001008a  call    SmbReferenceRecord
0x14001008f  lock inc dword ptr [r14+8]
0x140010094  mov     rcx, r14; P
0x140010097  call    SmbCeCompleteVNetRootContextInitialization
0x14001009c  btr     dword ptr [rbx+48h], 9
0x1400100a1  mov     r9d, [rdi+11Ch]
0x1400100a8  cmp     r9d, 0C000020Dh
0x1400100af  jz      short loc_1400100BA
0x1400100b1  cmp     r9d, 0C00000B5h
0x1400100b8  jnz     short loc_1400100FD
0x1400100ba  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400100c1  lea     rax, WPP_GLOBAL_Control
0x1400100c8  cmp     rcx, rax
0x1400100cb  jz      short loc_1400100FD
0x1400100cd  test    dword ptr [rcx+2Ch], 100h
0x1400100d4  jz      short loc_1400100FD
0x1400100d6  mov     eax, [rdi+118h]
0x1400100dc  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x1400100e3  mov     rcx, [rcx+18h]
0x1400100e7  mov     edx, 1Bh
0x1400100ec  mov     [rsp+78h+var_50], eax
0x1400100f0  mov     dword ptr [rsp+78h+pContext], r9d
0x1400100f5  mov     r9, r14
0x1400100f8  call    WPP_SF_qDD
0x1400100fd  mov     rcx, [rbx+180h]; MemoryDescriptorList
0x140010104  test    rcx, rcx
0x140010107  jz      short loc_140010128
0x140010109  call    cs:__imp_MmUnlockPages
0x140010110  nop     dword ptr [rax+rax+00h]
0x140010115  mov     rcx, [rbx+180h]; Mdl
0x14001011c  call    cs:__imp_IoFreeMdl
0x140010123  nop     dword ptr [rax+rax+00h]
0x140010128  mov     rcx, [rbx+178h]
0x14001012f  test    rcx, rcx
0x140010132  jz      short loc_140010153
0x140010134  call    cs:__imp_RxUnlockHeaderPages
0x14001013b  nop     dword ptr [rax+rax+00h]
0x140010140  mov     rcx, [rbx+178h]; Mdl
0x140010147  call    cs:__imp_IoFreeMdl
0x14001014e  nop     dword ptr [rax+rax+00h]
0x140010153  mov     rcx, [rbx+188h]; P
0x14001015a  test    rcx, rcx
0x14001015d  jz      short loc_140010178
0x14001015f  xor     edx, edx; Tag
0x140010161  call    cs:__imp_ExFreePoolWithTag
0x140010168  nop     dword ptr [rax+rax+00h]
0x14001016d  mov     qword ptr [rbx+188h], 0
0x140010178  mov     rcx, rbx; Context
0x14001017b  call    SmbCeDiscardExchangeWorkerThreadRoutine
0x140010180  test    r13, r13
0x140010183  jz      short loc_1400101A8
0x140010185  mov     rcx, [r13+10h]
0x140010189  lea     r8, aCallbackRdbssF; "Callback rdbss for create VNetRootCtxt "...
0x140010190  mov     r9, r14
0x140010193  mov     dword ptr [rsp+78h+pContext], esi
0x140010197  mov     edx, 1
0x14001019c  call    cs:__imp_RxDiagnosticTrace
0x1400101a3  nop     dword ptr [rax+rax+00h]
0x1400101a8  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x1400101af  lea     r8, [rdi+0C8h]; pWorkQueueItem
0x1400101b6  mov     r9, r12; Routine
0x1400101b9  mov     [rsp+78h+pContext], rdi; pContext
0x1400101be  xor     edx, edx; WorkQueueType
0x1400101c0  mov     rcx, [rcx]; pMRxDeviceObject
0x1400101c3  call    cs:__imp_RxPostToWorkerThread
0x1400101ca  nop     dword ptr [rax+rax+00h]
0x1400101cf  xor     eax, eax
0x1400101d1  add     rsp, 38h
0x1400101d5  pop     r15
0x1400101d7  pop     r14
0x1400101d9  pop     r13
0x1400101db  pop     r12
0x1400101dd  pop     rdi
0x1400101de  pop     rsi
0x1400101df  pop     rbp
0x1400101e0  pop     rbx
0x1400101e1  retn
```
