# RefsTransformStreamRange(_IRP_CONTEXT *,_IRP *,_SCB *,_RANGE,void *,_MDL *,SCB_STATE)

- ea: `0x14029f98c`
- end: `0x1402a03af`
- name: `?RefsTransformStreamRange@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_SCB@@U_RANGE@@PEAXPEAU_MDL@@W4SCB_STATE@@@Z`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, loader_planting`

## callers

- `0x14029c098`

## callees

- `0x14002a0f0`
- `0x14002b180`
- `0x140043510`
- `0x140080b90`
- `0x140081670`
- `0x14008dbd0`
- `0x14008f8b0`
- `0x14009b060`
- `0x1400ac034`
- `0x1400aec80`
- `0x1400ca788`
- `0x1400cf4bc`
- `0x1400ef978`
- `0x140115adc`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x14029f98c`
- `0x14032b500`
- `0x14032ead0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1402a00c6`
- `ntoskrnl!IoBuildPartialMdl` at `0x1402a00c6`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402a008a`
- `ntoskrnl!MmUnmapLockedPages` at `0x1402a008a`
- `ntoskrnl!IoAllocateMdl` at `0x14029fff0`
- `ntoskrnl!IoAllocateMdl` at `0x14029fff0`
- `ntoskrnl!IoFreeMdl` at `0x1402a033d`
- `ntoskrnl!IoFreeMdl` at `0x1403441e4`
- `ntoskrnl!IoFreeMdl` at `0x1402a033d`
- `ntoskrnl!IoFreeMdl` at `0x1403441e4`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14029fc3b`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14029fd81`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a0178`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a034c`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1403441fb`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14029fc3b`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x14029fd81`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a0178`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1402a034c`
- `ntoskrnl!IoIrpHasFsTrackOffsetExtensionType` at `0x1403441fb`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14029fc51`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14029fd96`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a018b`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a035f`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14034420e`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14029fc51`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14029fd96`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a018b`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1402a035f`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x14034420e`

## pseudocode

```c
void __fastcall RefsTransformStreamRange(
        struct _IRP_CONTEXT *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        void *a5,
        struct _MDL *a6,
        int a7)
{
  unsigned __int64 v11; // r14
  CmsStream *v12; // rdx
  struct CmsTransactionContext *v13; // rcx
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // r14
  unsigned __int8 v17; // r8
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // r8d
  NTSTATUS v23; // r14d
  __int64 *v24; // [rsp+28h] [rbp-520h]
  int v25; // [rsp+38h] [rbp-510h]
  int v26; // [rsp+40h] [rbp-508h]
  __int64 v27; // [rsp+88h] [rbp-4C0h] BYREF
  PMDL SourceMdl; // [rsp+90h] [rbp-4B8h]
  unsigned __int64 v29; // [rsp+98h] [rbp-4B0h]
  __int64 v30; // [rsp+A0h] [rbp-4A8h]
  __int64 v31; // [rsp+A8h] [rbp-4A0h]
  __int64 v32; // [rsp+B0h] [rbp-498h]
  __int64 v33; // [rsp+B8h] [rbp-490h]
  __int64 v34; // [rsp+D0h] [rbp-478h]
  __int64 v35; // [rsp+E8h] [rbp-460h]
  __int64 v36; // [rsp+F0h] [rbp-458h]
  __int64 v37; // [rsp+F8h] [rbp-450h]
  struct _IRP_CONTEXT *v38; // [rsp+100h] [rbp-448h]
  __int128 v39; // [rsp+140h] [rbp-408h]
  __int128 v40; // [rsp+160h] [rbp-3E8h]
  _OWORD v41[2]; // [rsp+170h] [rbp-3D8h] BYREF
  __int128 v42; // [rsp+190h] [rbp-3B8h] BYREF
  _DWORD v43[32]; // [rsp+1A0h] [rbp-3A8h] BYREF
  __int64 v44; // [rsp+220h] [rbp-328h]
  __int64 v45; // [rsp+228h] [rbp-320h]
  __int128 v46; // [rsp+230h] [rbp-318h]
  _DWORD v47[176]; // [rsp+240h] [rbp-308h] BYREF

  v38 = a1;
  v36 = a2;
  SourceMdl = a6;
  v27 = 0;
  v35 = *(_QWORD *)(a2 + 8);
  v37 = v35;
  v33 = 0;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  v45 = 0;
  v46 = 0;
  memset(v47, 0, sizeof(v47));
  RefsInitializeIoContext(a1, (struct REFS_IO_CONTEXT *)v43, a3, 0);
  while ( a4[1] )
  {
    v41[0] = *(_OWORD *)a4;
    v24 = &v27;
    if ( (unsigned __int8)RefsLookupAllocation(a1, a3, v41, 1) || BYTE1(v27) )
    {
      v11 = *a4;
      v29 = *a4;
      if ( !(_BYTE)v27 )
      {
        v39 = v11;
        v12 = *(CmsStream **)(a3 + 432);
        v13 = (struct CmsTransactionContext *)*((_QWORD *)a1 + 3);
        v41[1] = v11;
        v14 = MsSetRangeEncryptedState(v13, v12);
        v11 = (unsigned int)v14;
        if ( v14 >= 0 )
          goto LABEL_32;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            102,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            (unsigned int)v14);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v11, a1, "Efssup.c", 0x1554u);
        RefsRaiseStatusInternal(a1, v11, v15);
      }
      v16 = v11 << *(_BYTE *)(*(_QWORD *)(a3 + 144) + 552LL);
      if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
        IoClearFsTrackOffsetState(a2);
      *(_QWORD *)(a2 + 8) = SourceMdl;
      LOBYTE(v26) = 0;
      LOBYTE(v25) = 3;
      LODWORD(v24) = 0;
      RefsSingleAsync(a1, v43, *(_QWORD *)(*(_QWORD *)(a3 + 144) + 192LL), v16, 0, v24, a2, v25, v26, a3, 0);
      RefsWaitOnIo((struct REFS_IO_CONTEXT *)v43);
      *(_QWORD *)(a2 + 56) = 0;
      RefsNormalizeAndCleanupTransaction(a1, (int *)(a2 + 48), v17, v18);
      if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
        IoClearFsTrackOffsetState(a2);
      if ( _bittest16((const signed __int16 *)(a3 + 256), 0xEu) && *(_QWORD *)(a3 + 288) && *(int *)(a3 + 152) >= 0 )
      {
        if ( (a7 & 0x4000000) != 0 )
          RefsDecryptBuffer((struct _SCB *)a3, v16, 0, a5);
        else
          RefsEncryptBuffer((struct _SCB *)a3, v16, 0, a5, a5);
      }
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v34 = 0;
      v29 = 0;
      v40 = *a4;
      v19 = *((_QWORD *)a1 + 3);
      v20 = *(_QWORD *)(a3 + 432);
      v42 = v40;
      v25 = 0;
      v21 = MsPersistReserveAllocationAndGenerateChecksum(v20, v19, &v42);
      v23 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            (unsigned int)v21);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v23, a1, "Efssup.c", 0x166Au);
        RefsRaiseStatusInternal(a1, v23, v22);
      }
    }
LABEL_32:
    *a4 = *a4;
    a4[1] = a4[1];
  }
  if ( (unsigned __int8)IoIrpHasFsTrackOffsetExtensionType(a2) )
    IoClearFsTrackOffsetState(a2);
  *(_QWORD *)(a2 + 8) = v35;
  RefsCleanupIoContext(a1, (struct REFS_IO_CONTEXT *)v43, *(_DWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x14029f98c  mov     r11, rsp
0x14029f98f  push    rbx
0x14029f990  push    rsi
0x14029f991  push    rdi
0x14029f992  push    r12
0x14029f994  push    r13
0x14029f996  push    r14
0x14029f998  push    r15
0x14029f99a  sub     rsp, 510h
0x14029f9a1  mov     rax, cs:__security_cookie
0x14029f9a8  xor     rax, rsp
0x14029f9ab  mov     [rsp+548h+var_48], rax
0x14029f9b3  mov     r13, r9
0x14029f9b6  mov     rdi, r8
0x14029f9b9  mov     rsi, rdx
0x14029f9bc  mov     rbx, rcx
0x14029f9bf  mov     [rsp+548h+var_448], rcx
0x14029f9c7  mov     [rsp+548h+var_458], rdx
0x14029f9cf  mov     rax, [rsp+548h+arg_20]
0x14029f9d7  mov     [rsp+548h+VirtualAddress], rax
0x14029f9dc  mov     rax, [rsp+548h+arg_28]
0x14029f9e4  mov     [rsp+548h+SourceMdl], rax
0x14029f9ec  xor     r12d, r12d
0x14029f9ef  mov     [r11-4C0h], r12
0x14029f9f6  mov     [rsp+548h+var_4D0], r12
0x14029f9fb  mov     [r11-4C8h], r12
0x14029fa02  mov     r14, [rdx+8]
0x14029fa06  mov     [rsp+548h+var_460], r14
0x14029fa0e  mov     [rsp+548h+var_450], r14
0x14029fa16  mov     r15d, r12d
0x14029fa19  mov     [r11-490h], r12
0x14029fa20  xor     eax, eax
0x14029fa22  mov     [rsp+548h+var_3A4], eax
0x14029fa29  mov     [rsp+548h+var_36F], eax
0x14029fa30  mov     [rsp+548h+var_36B], ax
0x14029fa38  mov     [rsp+548h+var_369], al
0x14029fa3f  lea     r14d, [r12+40h]
0x14029fa44  mov     r8d, r14d; Size
0x14029fa47  xor     edx, edx; Val
0x14029fa49  lea     rcx, [r11-3A8h]; void *
0x14029fa50  call    memset
0x14029fa55  xor     eax, eax
0x14029fa57  mov     [rsp+548h+var_34C], eax
0x14029fa5e  mov     [rsp+548h+var_33C], eax
0x14029fa65  mov     r8d, r14d; Size
0x14029fa68  xor     edx, edx; Val
0x14029fa6a  lea     rcx, [rsp+548h+var_368]; void *
0x14029fa72  call    memset
0x14029fa77  mov     [rsp+548h+var_328], r12
0x14029fa7f  mov     [rsp+548h+var_320], r12
0x14029fa87  xorps   xmm0, xmm0
0x14029fa8a  movups  [rsp+548h+var_318], xmm0
0x14029fa92  xor     edx, edx; Val
0x14029fa94  mov     r8d, 1C0h; Size
0x14029fa9a  lea     rcx, [rsp+548h+var_308]; void *
0x14029faa2  call    memset
0x14029faa7  xor     eax, eax
0x14029faa9  mov     [rsp+548h+var_144], eax
0x14029fab0  xor     edx, edx; Val
0x14029fab2  mov     r8d, 100h; Size
0x14029fab8  lea     rcx, [rsp+548h+var_148]; void *
0x14029fac0  call    memset
0x14029fac5  xor     r9d, r9d; bool
0x14029fac8  lea     rdx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x14029fad0  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14029fad3  call    ?RefsInitializeIoContext@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@_N2@Z; RefsInitializeIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,bool,bool)
0x14029fad8  nop
0x14029fad9  cmp     [r13+8], r12
0x14029fadd  jz      loc_1402A0335
0x14029fae3  movaps  xmm0, xmmword ptr [r13+0]
0x14029fae8  movdqa  [rsp+548h+var_3D8], xmm0
0x14029faf1  mov     dword ptr [rsp+548h+var_518], r12d
0x14029faf6  lea     rax, [rsp+548h+var_4C0]
0x14029fafe  mov     [rsp+548h+var_520], rax
0x14029fb03  lea     rax, [rsp+548h+var_4D0]
0x14029fb08  mov     [rsp+548h+Irp], rax
0x14029fb0d  mov     r9d, 1
0x14029fb13  lea     r8, [rsp+548h+var_3D8]
0x14029fb1b  mov     rdx, rdi
0x14029fb1e  mov     rcx, rbx
0x14029fb21  call    ?RefsLookupAllocation@@YAEPEAU_IRP_CONTEXT@@PEAU_SCB@@U_RANGE@@W4RefsLookupAllocationFlags@@PEAU3@PEAU_MS_STREAM_RUN_PROPERTIES@@K@Z; RefsLookupAllocation(_IRP_CONTEXT *,_SCB *,_RANGE,RefsLookupAllocationFlags,_RANGE *,_MS_STREAM_RUN_PROPERTIES *,ulong)
0x14029fb26  test    al, al
0x14029fb28  jnz     short loc_14029FB38
0x14029fb2a  cmp     [rsp+548h+var_4BF], r12b
0x14029fb32  jz      loc_1402A0320
0x14029fb38  mov     r14, [r13+0]
0x14029fb3c  mov     [rsp+548h+var_4B0], r14
0x14029fb44  cmp     [rsp+548h+var_4C0], r12b
0x14029fb4c  jnz     loc_14029FC17
0x14029fb52  mov     eax, [rsp+548h+arg_30]
0x14029fb59  and     eax, 2000000h
0x14029fb5e  setnz   r9b
0x14029fb62  mov     qword ptr [rsp+548h+var_408], r14
0x14029fb6a  mov     rax, [rsp+548h+var_4C8]
0x14029fb72  mov     qword ptr [rsp+548h+var_408+8], rax
0x14029fb7a  mov     rdx, [rdi+1B0h]
0x14029fb81  mov     rcx, [rbx+18h]
0x14029fb85  movaps  xmm0, [rsp+548h+var_408]
0x14029fb8d  movdqa  [rsp+548h+var_3C8], xmm0
0x14029fb96  lea     r8, [rsp+548h+var_3C8]
0x14029fb9e  call    MsSetRangeEncryptedState
0x14029fba3  mov     r14d, eax
0x14029fba6  test    eax, eax
0x14029fba8  jns     loc_1402A0320
0x14029fbae  lea     rdx, WPP_GLOBAL_Control
0x14029fbb5  mov     r10, cs:WPP_GLOBAL_Control
0x14029fbbc  cmp     r10, rdx
0x14029fbbf  jz      short loc_14029FBEA
0x14029fbc1  test    dword ptr [r10+2Ch], 100h
0x14029fbc9  jz      short loc_14029FBEA
0x14029fbcb  cmp     byte ptr [r10+29h], 4
0x14029fbd0  jb      short loc_14029FBEA
0x14029fbd2  mov     edx, 66h ; 'f'
0x14029fbd7  mov     r9d, eax
0x14029fbda  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x14029fbe1  mov     rcx, [r10+18h]
0x14029fbe5  call    WPP_SF_d
0x14029fbea  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14029fbf0  test    al, al
0x14029fbf2  jz      short loc_14029FC0C
0x14029fbf4  mov     r9d, 1554h; unsigned int
0x14029fbfa  lea     r8, aEfssupC; "Efssup.c"
0x14029fc01  mov     rdx, rbx; struct _IRP_CONTEXT *
0x14029fc04  mov     ecx, r14d; Status
0x14029fc07  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14029fc0c  mov     edx, r14d; int
0x14029fc0f  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14029fc12  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x14029fc17  mov     rax, [rdi+90h]
0x14029fc1e  mov     cl, [rax+228h]
0x14029fc24  shl     r14, cl
0x14029fc27  mov     ecx, [rax+228h]
0x14029fc2d  mov     r12, [rsp+548h+var_4C8]
0x14029fc35  shl     r12d, cl
0x14029fc38  mov     rcx, rsi
0x14029fc3b  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x14029fc42  nop     dword ptr [rax+rax+00h]
0x14029fc47  xor     r9d, r9d
0x14029fc4a  test    al, al
0x14029fc4c  jz      short loc_14029FC60
0x14029fc4e  mov     rcx, rsi
0x14029fc51  call    cs:__imp_IoClearFsTrackOffsetState
0x14029fc58  nop     dword ptr [rax+rax+00h]
0x14029fc5d  xor     r9d, r9d
0x14029fc60  mov     rax, [rsp+548h+SourceMdl]
0x14029fc68  mov     [rsi+8], rax
0x14029fc6c  mov     rdx, [rsp+548h+var_4D0]
0x14029fc71  bt      rdx, 3Fh ; '?'
0x14029fc76  jnb     loc_14029FD0F
0x14029fc7c  xorps   xmm0, xmm0
0x14029fc7f  xor     eax, eax
0x14029fc81  movups  [rsp+548h+Context], xmm0
0x14029fc89  movups  [rsp+548h+var_430], xmm0
0x14029fc91  movups  [rsp+548h+var_420], xmm0
0x14029fc99  mov     [rsp+548h+var_410], rax
0x14029fca1  mov     rax, [rbx+18h]
0x14029fca5  mov     qword ptr [rsp+548h+Context], rax
0x14029fcad  mov     qword ptr [rsp+548h+var_430], rsi
0x14029fcb5  mov     dword ptr [rsp+548h+var_430+8], r12d
0x14029fcbd  mov     rcx, [rdi+90h]
0x14029fcc4  mov     cl, [rcx+228h]
0x14029fcca  shl     rdx, cl
0x14029fccd  mov     qword ptr [rsp+548h+var_420], rdx
0x14029fcd5  mov     qword ptr [rsp+548h+var_420+8], r14
0x14029fcdd  mov     qword ptr [rsp+548h+Context+8], rdi
0x14029fce5  xor     r9d, r9d; unsigned int
0x14029fce8  mov     r8, rsi; struct _IRP *
0x14029fceb  lea     rdx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x14029fcf3  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14029fcf6  call    ?RefsPreProcessIo@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@K@Z; RefsPreProcessIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,ulong)
0x14029fcfb  xor     r8d, r8d; IoWorkItem
0x14029fcfe  lea     rdx, [rsp+548h+Context]; Context
0x14029fd06  xor     ecx, ecx; IoObject
0x14029fd08  call    ?RefsDecompressWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; RefsDecompressWorker(void *,void *,_IO_WORKITEM *)
0x14029fd0d  jmp     short loc_14029FD5D
0x14029fd0f  mov     r8, [rdi+90h]
0x14029fd16  mov     cl, [r8+228h]
0x14029fd1d  shl     rdx, cl
0x14029fd20  mov     [rsp+548h+var_4F8], r9d
0x14029fd25  mov     [rsp+548h+var_500], rdi
0x14029fd2a  mov     [rsp+548h+var_508], r9b
0x14029fd2f  mov     byte ptr [rsp+548h+var_510], 3
0x14029fd34  mov     [rsp+548h+var_518], rsi
0x14029fd39  mov     dword ptr [rsp+548h+var_520], r12d
0x14029fd3e  mov     [rsp+548h+Irp], rdx
0x14029fd43  mov     r9, r14
0x14029fd46  mov     r8, [r8+0C0h]
0x14029fd4d  lea     rdx, [rsp+548h+var_3A8]
0x14029fd55  mov     rcx, rbx
0x14029fd58  call    ?RefsSingleAsync@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_DEVICE_OBJECT@@_J3KPEAU_IRP@@EEPEAU_SCB@@W4RefsIoStreamFlags@@@Z; RefsSingleAsync(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_DEVICE_OBJECT *,__int64,__int64,ulong,_IRP *,uchar,uchar,_SCB *,RefsIoStreamFlags)
0x14029fd5d  lea     rcx, [rsp+548h+var_3A8]; struct REFS_IO_CONTEXT *
0x14029fd65  call    ?RefsWaitOnIo@@YAXPEAUREFS_IO_CONTEXT@@@Z; RefsWaitOnIo(REFS_IO_CONTEXT *)
0x14029fd6a  lea     rdx, [rsi+30h]; int *
0x14029fd6e  mov     qword ptr [rsi+38h], 0
0x14029fd76  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14029fd79  call    ?RefsNormalizeAndCleanupTransaction@@YAXPEAU_IRP_CONTEXT@@PEAJEJ@Z; RefsNormalizeAndCleanupTransaction(_IRP_CONTEXT *,long *,uchar,long)
0x14029fd7e  mov     rcx, rsi
0x14029fd81  call    cs:__imp_IoIrpHasFsTrackOffsetExtensionType
0x14029fd88  nop     dword ptr [rax+rax+00h]
0x14029fd8d  xor     edx, edx
0x14029fd8f  test    al, al
0x14029fd91  jz      short loc_14029FDA4
0x14029fd93  mov     rcx, rsi
0x14029fd96  call    cs:__imp_IoClearFsTrackOffsetState
0x14029fd9d  nop     dword ptr [rax+rax+00h]
0x14029fda2  xor     edx, edx
0x14029fda4  bt      word ptr [rdi+100h], 0Eh
0x14029fdad  jnb     short loc_14029FDF5
0x14029fdaf  cmp     [rdi+120h], rdx
0x14029fdb6  jz      short loc_14029FDF5
0x14029fdb8  cmp     [rdi+98h], edx
0x14029fdbe  jl      short loc_14029FDF5
0x14029fdc0  mov     eax, [rsp+548h+arg_30]
0x14029fdc7  and     eax, 4000000h
0x14029fdcc  mov     r8d, r12d; unsigned int
0x14029fdcf  mov     rdx, r14; __int64
0x14029fdd2  mov     rcx, rdi; struct _SCB *
0x14029fdd5  jz      short loc_14029FDE3
0x14029fdd7  mov     r9, [rsp+548h+VirtualAddress]; void *
0x14029fddc  call    ?RefsDecryptBuffer@@YAXPEAU_SCB@@_JKPEAX@Z; RefsDecryptBuffer(_SCB *,__int64,ulong,void *)
0x14029fde1  jmp     short loc_14029FDF5
0x14029fde3  mov     rax, [rsp+548h+VirtualAddress]
0x14029fde8  mov     [rsp+548h+Irp], rax; void *
0x14029fded  mov     r9, rax; void *
0x14029fdf0  call    ?RefsEncryptBuffer@@YAXPEAU_SCB@@_JKPEAX2@Z; RefsEncryptBuffer(_SCB *,__int64,ulong,void *,void *)
0x14029fdf5  mov     r12, [rsp+548h+var_4B0]
0x14029fdfd  mov     [rsp+548h+var_4B0], r12
0x14029fe05  mov     rdx, [rsp+548h+var_4C8]
0x14029fe0d  mov     [rsp+548h+var_4A8], rdx
0x14029fe15  mov     [rsp+548h+var_4D8], rdx
0x14029fe1a  mov     [rsp+548h+var_4E8], 0
0x14029fe22  mov     rax, rdx
0x14029fe25  mov     r10, rdx
0x14029fe28  mov     [rsp+548h+var_4A0], rdx
0x14029fe30  mov     r11, rdx
0x14029fe33  mov     [rsp+548h+var_498], rdx
0x14029fe3b  mov     r8, rdx
0x14029fe3e  mov     [rsp+548h+var_478], rdx
0x14029fe46  mov     r14, rdx
0x14029fe49  mov     [rsp+548h+var_4B0], rdx
0x14029fe51  test    rax, rax
0x14029fe54  jz      loc_1402A0209
0x14029fe5a  xor     edx, edx
0x14029fe5c  mov     [rsp+548h+var_488], rdx
0x14029fe64  mov     [rsp+548h+var_480], rdx
0x14029fe6c  mov     [rsp+548h+var_468], rdx
0x14029fe74  mov     ecx, [rsp+548h+arg_30]
0x14029fe7b  and     ecx, 2000000h
0x14029fe81  mov     eax, ecx
0x14029fe83  neg     eax
0x14029fe85  sbb     r9d, r9d
0x14029fe88  and     r9d, 400000h
0x14029fe8f  add     r9d, 10h
0x14029fe93  mov     [rsp+548h+var_4E4], r9d
0x14029fe98  test    ecx, ecx
0x14029fe9a  cmovz   r10, [rsp+548h+var_4A0]
0x14029fea3  cmovz   r11, [rsp+548h+var_498]
0x14029feac  cmovz   r8, [rsp+548h+var_478]
0x14029feb5  cmovz   r14, [rsp+548h+var_4B0]
0x14029febe  movzx   eax, word ptr [rdi+100h]
0x14029fec5  test    ax, ax
0x14029fec8  js      short loc_14029FED0
0x14029feca  mov     r10, r11
0x14029fecd  mov     r8, r14
0x14029fed0  shr     ax, 0Fh
0x14029fed4  test    al, al
0x14029fed6  jz      short loc_14029FEE1
0x14029fed8  or      r9d, 2
0x14029fedc  mov     [rsp+548h+var_4E4], r9d
0x14029fee1  mov     [rsp+548h+var_3F8], r12
0x14029fee9  test    al, al
0x14029feeb  cmovz   r8, r10
0x14029feef  mov     [rsp+548h+var_3F0], r8
0x14029fef7  mov     [rsp+548h+var_510], rdx
0x14029fefc  mov     [rsp+548h+var_518], rdx
0x14029ff01  lea     rax, [rsp+548h+var_468]
0x14029ff09  mov     [rsp+548h+var_520], rax
0x14029ff0e  lea     rax, [rsp+548h+var_488]
0x14029ff16  mov     [rsp+548h+Irp], rax
0x14029ff1b  lea     r8, [rsp+548h+var_3F8]
0x14029ff23  mov     rdx, [rdi+1B0h]
0x14029ff2a  mov     rcx, [rbx+18h]
0x14029ff2e  call    MsPrepareVRangeForWrite
0x14029ff33  mov     r14d, eax
0x14029ff36  test    eax, eax
0x14029ff38  jns     short loc_14029FFA1
0x14029ff3a  lea     rdx, WPP_GLOBAL_Control
0x14029ff41  mov     rcx, cs:WPP_GLOBAL_Control
0x14029ff48  cmp     rcx, rdx
0x14029ff4b  jz      short loc_14029FF74
0x14029ff4d  test    dword ptr [rcx+2Ch], 100h
0x14029ff54  jz      short loc_14029FF74
0x14029ff56  cmp     byte ptr [rcx+29h], 4
0x14029ff5a  jb      short loc_14029FF74
0x14029ff5c  mov     edx, 67h ; 'g'
0x14029ff61  mov     r9d, eax
0x14029ff64  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x14029ff6b  mov     rcx, [rcx+18h]
0x14029ff6f  call    WPP_SF_d
0x14029ff74  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
  ... truncated ...
```
