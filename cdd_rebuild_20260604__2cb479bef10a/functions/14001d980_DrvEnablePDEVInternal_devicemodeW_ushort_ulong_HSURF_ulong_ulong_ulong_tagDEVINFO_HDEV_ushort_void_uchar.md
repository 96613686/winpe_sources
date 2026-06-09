# DrvEnablePDEVInternal(_devicemodeW *,ushort *,ulong,HSURF__ * *,ulong,ulong *,ulong,tagDEVINFO *,HDEV__ *,ushort *,void *,uchar)

- ea: `0x14001d980`
- end: `0x14001eda0`
- name: `?DrvEnablePDEVInternal@@YAPEAUDHPDEV__@@PEAU_devicemodeW@@PEAGKPEAPEAUHSURF__@@KPEAKKPEAUtagDEVINFO@@PEAUHDEV__@@1PEAXE@Z`
- size: `5152`
- prototype: `struct DHPDEV__ *__fastcall(struct _devicemodeW *, unsigned __int16 *, unsigned int, HSURF *, size_t, unsigned int *, size_t, struct tagDEVINFO *, HDEV, unsigned __int16 *, void *, char)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001d910`
- `0x140035240`

## callees

- `0x140015ce0`
- `0x140018c68`
- `0x14001bff8`
- `0x14001d6b0`
- `0x14001d980`
- `0x14002849c`
- `0x140028a40`
- `0x14002bcfc`
- `0x14002c204`
- `0x14002ece0`
- `0x14002fa88`
- `0x14003020c`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037340`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001e192`
- `ntoskrnl!KeInitializeEvent` at `0x14001e1c4`
- `ntoskrnl!KeInitializeEvent` at `0x14001e1f6`
- `ntoskrnl!KeInitializeEvent` at `0x14001e228`
- `ntoskrnl!KeInitializeEvent` at `0x14001e25a`
- `ntoskrnl!KeInitializeEvent` at `0x14001e28c`
- `ntoskrnl!KeInitializeEvent` at `0x14001e2be`
- `ntoskrnl!KeInitializeEvent` at `0x14001e2f0`
- `ntoskrnl!KeInitializeEvent` at `0x14001e419`
- `ntoskrnl!KeInitializeEvent` at `0x14001e192`
- `ntoskrnl!KeInitializeEvent` at `0x14001e1c4`
- `ntoskrnl!KeInitializeEvent` at `0x14001e1f6`
- `ntoskrnl!KeInitializeEvent` at `0x14001e228`
- `ntoskrnl!KeInitializeEvent` at `0x14001e25a`
- `ntoskrnl!KeInitializeEvent` at `0x14001e28c`
- `ntoskrnl!KeInitializeEvent` at `0x14001e2be`
- `ntoskrnl!KeInitializeEvent` at `0x14001e2f0`
- `ntoskrnl!KeInitializeEvent` at `0x14001e419`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd86`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd86`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001dd1a`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x14001dd1a`
- `ntoskrnl!ExAllocatePool2` at `0x14001dcda`
- `ntoskrnl!ExAllocatePool2` at `0x14001df2e`
- `ntoskrnl!ExAllocatePool2` at `0x14001df4f`
- `ntoskrnl!ExAllocatePool2` at `0x14001df70`
- `ntoskrnl!ExAllocatePool2` at `0x14001df91`
- `ntoskrnl!ExAllocatePool2` at `0x14001dfb2`
- `ntoskrnl!ExAllocatePool2` at `0x14001dfd3`
- `ntoskrnl!ExAllocatePool2` at `0x14001dff4`
- `ntoskrnl!ExAllocatePool2` at `0x14001e015`
- `ntoskrnl!ExAllocatePool2` at `0x14001e11c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e3f6`
- `ntoskrnl!ExAllocatePool2` at `0x14001dcda`
- `ntoskrnl!ExAllocatePool2` at `0x14001df2e`
- `ntoskrnl!ExAllocatePool2` at `0x14001df4f`
- `ntoskrnl!ExAllocatePool2` at `0x14001df70`
- `ntoskrnl!ExAllocatePool2` at `0x14001df91`
- `ntoskrnl!ExAllocatePool2` at `0x14001dfb2`
- `ntoskrnl!ExAllocatePool2` at `0x14001dfd3`
- `ntoskrnl!ExAllocatePool2` at `0x14001dff4`
- `ntoskrnl!ExAllocatePool2` at `0x14001e015`
- `ntoskrnl!ExAllocatePool2` at `0x14001e11c`
- `ntoskrnl!ExAllocatePool2` at `0x14001e3f6`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001e15f`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001e15f`
- `ntoskrnl!DbgPrint` at `0x14001da81`
- `ntoskrnl!DbgPrint` at `0x14001da81`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001da64`
- `watchdog!WdLogSingleEntry4` at `0x14001e33f`
- `watchdog!WdLogSingleEntry4` at `0x14001e3b2`
- `watchdog!WdLogSingleEntry4` at `0x14001e33f`
- `watchdog!WdLogSingleEntry4` at `0x14001e3b2`
- `watchdog!WdLogSingleEntry5` at `0x14001dc9d`
- `watchdog!WdLogSingleEntry5` at `0x14001e492`
- `watchdog!WdLogSingleEntry5` at `0x14001e648`
- `watchdog!WdLogSingleEntry5` at `0x14001e73e`
- `watchdog!WdLogSingleEntry5` at `0x14001eb5e`
- `watchdog!WdLogSingleEntry5` at `0x14001ebbb`
- `watchdog!WdLogSingleEntry5` at `0x14001ed25`
- `watchdog!WdLogSingleEntry5` at `0x14001dc9d`
- `watchdog!WdLogSingleEntry5` at `0x14001e492`
- `watchdog!WdLogSingleEntry5` at `0x14001e648`
- `watchdog!WdLogSingleEntry5` at `0x14001e73e`
- `watchdog!WdLogSingleEntry5` at `0x14001eb5e`
- `watchdog!WdLogSingleEntry5` at `0x14001ebbb`
- `watchdog!WdLogSingleEntry5` at `0x14001ed25`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001db17`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ed3c`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001db17`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x14001ed3c`
- `watchdog!WdLogSingleEntry2` at `0x14001da23`
- `watchdog!WdLogSingleEntry2` at `0x14001e435`
- `watchdog!WdLogSingleEntry2` at `0x14001da23`
- `watchdog!WdLogSingleEntry2` at `0x14001e435`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001eb75`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001ec76`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001eb75`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001ec76`
- `watchdog!WdLogSingleEntry1` at `0x14001dd36`
- `watchdog!WdLogSingleEntry1` at `0x14001e510`
- `watchdog!WdLogSingleEntry1` at `0x14001e89a`
- `watchdog!WdLogSingleEntry1` at `0x14001e8bf`
- `watchdog!WdLogSingleEntry1` at `0x14001ea54`
- `watchdog!WdLogSingleEntry1` at `0x14001ea7e`
- `watchdog!WdLogSingleEntry1` at `0x14001eae1`
- `watchdog!WdLogSingleEntry1` at `0x14001eb0b`
- `watchdog!WdLogSingleEntry1` at `0x14001ec5d`
- `watchdog!WdLogSingleEntry1` at `0x14001ecec`
- `watchdog!WdLogSingleEntry1` at `0x14001dd36`
- `watchdog!WdLogSingleEntry1` at `0x14001e510`
- `watchdog!WdLogSingleEntry1` at `0x14001e89a`
- `watchdog!WdLogSingleEntry1` at `0x14001e8bf`
- `watchdog!WdLogSingleEntry1` at `0x14001ea54`
- `watchdog!WdLogSingleEntry1` at `0x14001ea7e`
- `watchdog!WdLogSingleEntry1` at `0x14001eae1`
- `watchdog!WdLogSingleEntry1` at `0x14001eb0b`
- `watchdog!WdLogSingleEntry1` at `0x14001ec5d`
- `watchdog!WdLogSingleEntry1` at `0x14001ecec`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001da3a`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001daa4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001dcb4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001dd4d`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001e356`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001da3a`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001daa4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001dcb4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001dd4d`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001e356`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001ddcf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001ddcf`
- `watchdog!WdLogSingleEntry0` at `0x14001da8f`
- `watchdog!WdLogSingleEntry0` at `0x14001db00`
- `watchdog!WdLogSingleEntry0` at `0x14001ddb9`
- `watchdog!WdLogSingleEntry0` at `0x14001e13c`
- `watchdog!WdLogSingleEntry0` at `0x14001e953`
- `watchdog!WdLogSingleEntry0` at `0x14001e990`
- `watchdog!WdLogSingleEntry0` at `0x14001e9f4`
- `watchdog!WdLogSingleEntry0` at `0x14001da8f`
- `watchdog!WdLogSingleEntry0` at `0x14001db00`
- `watchdog!WdLogSingleEntry0` at `0x14001ddb9`
- `watchdog!WdLogSingleEntry0` at `0x14001e13c`
- `watchdog!WdLogSingleEntry0` at `0x14001e953`
- `watchdog!WdLogSingleEntry0` at `0x14001e990`
- `watchdog!WdLogSingleEntry0` at `0x14001e9f4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001ebd4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001ebd4`
- `WIN32K!EngQueryW32kCddInterface` at `0x14001dc71`
- `WIN32K!EngQueryW32kCddInterface` at `0x14001dc71`
- `WIN32K!W32GetSessionState` at `0x14001dbf1`
- `WIN32K!W32GetSessionState` at `0x14001e5eb`
- `WIN32K!W32GetSessionState` at `0x14001e754`
- `WIN32K!W32GetSessionState` at `0x14001e853`
- `WIN32K!W32GetSessionState` at `0x14001e86c`
- `WIN32K!W32GetSessionState` at `0x14001e903`
- `WIN32K!W32GetSessionState` at `0x14001dbf1`
- `WIN32K!W32GetSessionState` at `0x14001e5eb`
- `WIN32K!W32GetSessionState` at `0x14001e754`
- `WIN32K!W32GetSessionState` at `0x14001e853`
- `WIN32K!W32GetSessionState` at `0x14001e86c`
- `WIN32K!W32GetSessionState` at `0x14001e903`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de08`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de25`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de42`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de5f`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de7c`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de99`
- `WIN32K!CddEngCreateRectRgn` at `0x14001deb6`
- `WIN32K!CddEngCreateRectRgn` at `0x14001ded3`
- `WIN32K!CddEngCreateRectRgn` at `0x14001def0`
- `WIN32K!CddEngCreateRectRgn` at `0x14001df0d`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de08`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de25`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de42`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de5f`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de7c`
- `WIN32K!CddEngCreateRectRgn` at `0x14001de99`
- `WIN32K!CddEngCreateRectRgn` at `0x14001deb6`
- `WIN32K!CddEngCreateRectRgn` at `0x14001ded3`
- `WIN32K!CddEngCreateRectRgn` at `0x14001def0`
- `WIN32K!CddEngCreateRectRgn` at `0x14001df0d`
- `WIN32K!EngAllocMem` at `0x14001dae9`
- `WIN32K!EngAllocMem` at `0x14001dae9`

## pseudocode

```c
DHPDEV __fastcall DrvEnablePDEVInternal(
        struct _devicemodeW *a1,
        unsigned __int16 *a2,
        __int64 a3,
        HSURF *a4,
        size_t a5,
        unsigned int *a6,
        size_t a7,
        struct tagDEVINFO *a8,
        HDEV a9,
        unsigned __int16 *a10,
        void *a11,
        char a12)
{
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _DWORD *v15; // rax
  DHPDEV v16; // rdi
  _QWORD *v17; // rax
  unsigned int v18; // eax
  unsigned int *v19; // r13
  _QWORD *v20; // r14
  _QWORD *v21; // r12
  int W32kCddInterface; // eax
  int v23; // ebx
  _QWORD *v24; // rax
  struct _LOOKASIDE_LIST_EX *Pool2; // rax
  NTSTATUS v26; // eax
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rax
  struct _KSEMAPHORE *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  unsigned int v40; // edx
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // ecx
  __int64 v44; // rbx
  struct _KEVENT *v45; // rax
  struct _CDD_DEVMODE *v46; // rbx
  struct _CDD_DEVMODE *v47; // rdx
  int inited; // eax
  int v49; // eax
  int v50; // ebx
  __int64 v51; // rax
  bool v52; // al
  unsigned __int16 v53; // cx
  int v54; // eax
  __int64 v55; // rcx
  int v56; // eax
  unsigned int v57; // edx
  __int64 v58; // rcx
  size_t v59; // r8
  size_t v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rcx
  int v63; // eax
  __int16 v64; // dx
  int v65; // edx
  bool v66; // cc
  _QWORD *v67; // rax
  int v68; // eax
  unsigned int v69; // r9d
  __int64 v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // rcx
  int v73; // eax
  CddBitmapBase *v74; // rcx
  _QWORD *v75; // rcx
  __int64 v76; // r9
  __int64 v77; // r8
  bool v78; // zf
  HDEV v79; // rdx
  _QWORD *v80; // rax
  void (__fastcall *v81)(_QWORD, DHPDEV); // rax
  __int64 v82; // rdx
  __int64 v83; // rax
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  unsigned int Size; // [rsp+28h] [rbp-D8h]
  int v89; // [rsp+40h] [rbp-C0h] BYREF
  struct _KSEMAPHORE *v90; // [rsp+48h] [rbp-B8h]
  __int64 v91; // [rsp+50h] [rbp-B0h] BYREF
  struct _CDD_DEVMODE *v92; // [rsp+58h] [rbp-A8h]
  void *v93; // [rsp+60h] [rbp-A0h]
  void *v94; // [rsp+68h] [rbp-98h] BYREF
  _DWORD Src[80]; // [rsp+70h] [rbp-90h] BYREF
  _GDIINFO v96; // [rsp+1B0h] [rbp+B0h] BYREF

  v94 = a6;
  v92 = (struct _CDD_DEVMODE *)a1;
  v93 = a8;
  memset(&v96, 0, sizeof(v96));
  memset(Src, 0, 0x138u);
  v91 = 0;
  v89 = 0;
  if ( !a11 )
  {
    WdLogSingleEntry2(2, a9, a1);
    WdLogGlobalForLineNumber = 710;
    v13 = (_QWORD *)WdLogNewEntry5_WdError();
    v13[3] = gCddImageInfo;
    v13[4] = (unsigned int)dword_14003E570;
    v13[5] = 215857758;
    WdLogGlobalForLineNumber = 710;
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("DrvEnablePDEV is called with hDriver equal to NULL");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 712;
      v14 = (_QWORD *)WdLogNewEntry5_WdError();
      v14[3] = gCddImageInfo;
      v14[4] = (unsigned int)dword_14003E570;
      v14[5] = 215857758;
      WdLogGlobalForLineNumber = 712;
      __debugbreak();
    }
    return 0;
  }
  v15 = EngAllocMem(1u, 0x3208u, 0x64646344u);
  v16 = (DHPDEV)v15;
  if ( v15 )
  {
    v15[667] = 1;
    v15[670] = 0;
    v18 = v15[686] & 0xFFFFFFF7;
    *((_DWORD *)v16 + 672) = 3;
    *((_DWORD *)v16 + 674) = 63;
    *((_DWORD *)v16 + 686) = v18 | 0x22;
    *((_QWORD *)v16 + 85) = CddAddD3DDirtyRgn;
    *((_QWORD *)v16 + 87) = CddW32kCloseProcess;
    *((_QWORD *)v16 + 88) = CddDriverSupportsLiteModeChange;
    *((_QWORD *)v16 + 89) = CddUpdateDevMode;
    *((_DWORD *)v16 + 676) = 127;
    *((_DWORD *)v16 + 142) = 160;
    *((_DWORD *)v16 + 143) = 4;
    *((_QWORD *)v16 + 341) = 0;
    *((_BYTE *)v16 + 2736) = 0;
    *((_DWORD *)v16 + 3178) = 6291456;
    v19 = (unsigned int *)(v16 + 196);
    v20 = v16 + 622;
    *(_DWORD *)(*(_QWORD *)(((__int64 (*)(void))W32GetSessionState)() + 72) + 3384LL) = 1;
    v21 = v16 + 188;
    *((_QWORD *)v16 + 906) = v16 + 1810;
    *((_QWORD *)v16 + 905) = v16 + 1810;
    if ( a12 )
    {
      *((_QWORD *)v16 + 87) = RmtW32kCloseProcess;
      *((_QWORD *)v16 + 85) = guard_check_icall_nop;
      *((_QWORD *)v16 + 90) = RmtDeleteDeviceBitmapExSurf;
    }
    W32kCddInterface = EngQueryW32kCddInterface(a11, a9, v16 + 142, v16 + 622, v16 + 196, v16 + 188);
    if ( W32kCddInterface < 0 )
    {
      WdLogSingleEntry5(2, W32kCddInterface, a11, v16, a9, 160);
      v23 = 763;
      WdLogGlobalForLineNumber = 763;
      v24 = (_QWORD *)WdLogNewEntry5_WdError();
LABEL_123:
      v24[3] = gCddImageInfo;
      v24[4] = (unsigned int)dword_14003E570;
      v24[5] = 215857758;
      WdLogGlobalForLineNumber = v23;
      goto LABEL_124;
    }
    Pool2 = (struct _LOOKASIDE_LIST_EX *)ExAllocatePool2(64, 96, 1684300612);
    *((_QWORD *)v16 + 97) = Pool2;
    if ( !Pool2 )
    {
LABEL_124:
      *((_QWORD *)v16 + 43) = 0;
      DrvDisablePDEV(v16);
      return 0;
    }
    v26 = ExInitializeLookasideListEx(Pool2, 0, 0, PagedPool, 0, 0x438u, 0x64646344u, 0);
    LODWORD(v90) = v26;
    if ( v26 < 0 )
    {
      WdLogSingleEntry1(2, v26);
      WdLogGlobalForLineNumber = 777;
      v27 = (_QWORD *)WdLogNewEntry5_WdError();
      v27[3] = gCddImageInfo;
      v27[4] = (unsigned int)dword_14003E570;
      v27[5] = 215857758;
      WdLogGlobalForLineNumber = 777;
      ExFreePoolWithTag(*((PVOID *)v16 + 97), 0);
      *((_QWORD *)v16 + 97) = 0;
      goto LABEL_124;
    }
    if ( !*v20 || !*v21 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 783;
      v28 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v28[3] = gCddImageInfo;
      v28[4] = (unsigned int)dword_14003E570;
      v28[5] = 215857758;
      WdLogGlobalForLineNumber = 783;
    }
    *((_QWORD *)v16 + 350) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 351) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 352) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 353) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 354) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 355) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 356) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 357) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 358) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 359) = CddEngCreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)v16 + 360) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 361) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 362) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 900) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 907) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 686) = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 363) = ExAllocatePool2(64, 56, 1684300612);
    v29 = ExAllocatePool2(64, 56, 1684300612);
    *((_QWORD *)v16 + 364) = v29;
    if ( !*((_QWORD *)v16 + 350)
      || !*((_QWORD *)v16 + 351)
      || !*((_QWORD *)v16 + 352)
      || !*((_QWORD *)v16 + 353)
      || !*((_QWORD *)v16 + 354)
      || !*((_QWORD *)v16 + 355)
      || !*((_QWORD *)v16 + 356)
      || !*((_QWORD *)v16 + 357)
      || !*((_QWORD *)v16 + 358)
      || !*((_QWORD *)v16 + 359)
      || !*((_QWORD *)v16 + 360)
      || !*((_QWORD *)v16 + 361)
      || !*((_QWORD *)v16 + 362)
      || !*((_QWORD *)v16 + 900)
      || !*((_QWORD *)v16 + 686)
      || !*((_QWORD *)v16 + 363)
      || !v29
      || !*((_QWORD *)v16 + 907) )
    {
      WdLogSingleEntry5(6, (int)v90, a11, v16, a9, 160);
      v23 = 833;
      goto LABEL_122;
    }
    v30 = (struct _KSEMAPHORE *)ExAllocatePool2(64, 40, 1684300612);
    v90 = v30;
    *((_QWORD *)v16 + 895) = v30;
    if ( !v30 )
    {
      WdLogSingleEntry0(6);
      v23 = 840;
LABEL_122:
      WdLogGlobalForLineNumber = v23;
      v24 = (_QWORD *)WdLogNewEntry5_WdLowResource();
      goto LABEL_123;
    }
    KeInitializeSemaphore(v30, 1, 1);
    *(_QWORD *)&v90[1].Header.Lock = 0;
    v31 = *((_QWORD *)v16 + 360);
    *(_QWORD *)(v31 + 8) = 0;
    *(_DWORD *)(v31 + 16) = 0;
    *(_DWORD *)v31 = 1;
    KeInitializeEvent((PRKEVENT)(v31 + 24), SynchronizationEvent, 0);
    v32 = *((_QWORD *)v16 + 361);
    *(_DWORD *)v32 = 1;
    *(_QWORD *)(v32 + 8) = 0;
    *(_DWORD *)(v32 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v32 + 24), SynchronizationEvent, 0);
    v33 = *((_QWORD *)v16 + 362);
    *(_DWORD *)v33 = 1;
    *(_QWORD *)(v33 + 8) = 0;
    *(_DWORD *)(v33 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v33 + 24), SynchronizationEvent, 0);
    v34 = *((_QWORD *)v16 + 363);
    *(_DWORD *)v34 = 1;
    *(_QWORD *)(v34 + 8) = 0;
    *(_DWORD *)(v34 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v34 + 24), SynchronizationEvent, 0);
    v35 = *((_QWORD *)v16 + 364);
    *(_DWORD *)v35 = 1;
    *(_QWORD *)(v35 + 8) = 0;
    *(_DWORD *)(v35 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v35 + 24), SynchronizationEvent, 0);
    v36 = *((_QWORD *)v16 + 907);
    *(_DWORD *)v36 = 1;
    *(_QWORD *)(v36 + 8) = 0;
    *(_DWORD *)(v36 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v36 + 24), SynchronizationEvent, 0);
    v37 = *((_QWORD *)v16 + 900);
    *(_DWORD *)v37 = 1;
    *(_QWORD *)(v37 + 8) = 0;
    *(_DWORD *)(v37 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v37 + 24), SynchronizationEvent, 0);
    v38 = *((_QWORD *)v16 + 686);
    *(_DWORD *)v38 = 1;
    *(_QWORD *)(v38 + 8) = 0;
    *(_DWORD *)(v38 + 16) = 0;
    KeInitializeEvent((PRKEVENT)(v38 + 24), SynchronizationEvent, 0);
    v39 = (*((__int64 (__fastcall **)(HDEV, void *, int *, __int64 *))v16 + 75))(a9, a11, &v89, &v91);
    v40 = *v19;
    if ( v39 >= 0 )
    {
      v41 = *v20;
      *((_DWORD *)v16 + 14) = v40;
      *((_WORD *)v16 + 20) = 528;
      *((_QWORD *)v16 + 6) = v41;
      *((_WORD *)v16 + 21) = 9;
      v42 = OpenDxgkrnl(v16 + 10, (PFILE_OBJECT *)v16 + 92, (PDEVICE_OBJECT *)v16 + 93);
      v43 = *v19;
      if ( v42 >= 0 )
      {
        v44 = 0;
        *((_BYTE *)v16 + 1120) = a12;
        *((_DWORD *)v16 + 288) = v43;
        *((_DWORD *)v16 + 1370) = 0;
        while ( (unsigned int)v44 < 5 )
        {
          v45 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1684300612);
          *((_QWORD *)v16 + v44 + 326) = v45;
          if ( !v45 )
          {
            WdLogSingleEntry2(6, v16, *v19);
            v23 = 899;
            goto LABEL_122;
          }
          KeInitializeEvent(v45, SynchronizationEvent, 0);
          v44 = (unsigned int)(v44 + 1);
        }
        v46 = v92;
        v47 = v92;
        *(_QWORD *)v16 = a11;
        inited = InitPDEV(
                   (struct CDDPDEV *)v16,
                   v47,
                   &v96,
                   (struct tagDEVINFO *)Src,
                   (struct _CDD_DEVMODE *)(v16 + 182),
                   Size);
        if ( inited >= 0 )
        {
          v49 = Src[76];
          if ( ((_DWORD)v16[686] & 0x10) != 0 )
            v49 = Src[76] | 0x80;
          Src[0] |= 0x1001113u;
          v50 = 0x4000;
          Src[76] = v49 | 0x4000;
          if ( (*((int (__fastcall **)(_QWORD, DHPDEV, DHPDEV, DHPDEV, DHPDEV))v16 + 39))(
                 *v20,
                 v16 + 308,
                 v16 + 626,
                 v16 + 628,
                 v16 + 462) >= 0 )
          {
            v16[301] = v16[315];
            v16[300] = v16[314];
            v16[302] = v16[316];
            *((_QWORD *)v16 + 152) = v16 + 10;
            v51 = *v20;
            *((_QWORD *)v16 + 153) = *v20;
            v52 = v51 == *((_QWORD *)v16 + 313) && ((_DWORD)v16[321] & 4) != 0 || *((int *)v16 + 392) >= 4608;
            v53 = 16 * *((_DWORD *)v16 + 479);
            *((_BYTE *)v16 + 1196) = v52;
            v54 = *((_DWORD *)v16 + 475);
            *((_DWORD *)v16 + 686) ^= ((unsigned __int16)*((_DWORD *)v16 + 686) ^ v53) & 0x1000;
            if ( (v54 & 4) == 0 )
              Src[0] |= 0xCu;
            v55 = Src[76] | 0x20u;
            Src[76] |= 0x20u;
            if ( *((int *)v16 + 392) < 4608 || ((_DWORD)v16[320] & 1) != 0 )
            {
              v55 = (unsigned int)v55 | 0x10;
              Src[76] = v55;
            }
            if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v55, 4608) + 72) + 3416LL) )
              Src[76] |= 0x10000u;
            v56 = bInitDefaultPalette((struct CDDPDEV *)v16, (struct tagDEVINFO *)Src);
            v57 = *((_DWORD *)v16 + 199);
            v58 = *((unsigned int *)v16 + 200);
            if ( v56 )
            {
              v59 = 312;
              *((_DWORD *)v16 + 1822) = v57;
              *((_DWORD *)v16 + 1823) = 64;
              *((_DWORD *)v16 + 1824) = v57;
              *((_DWORD *)v16 + 1825) = v58;
              if ( (unsigned int)a7 <= 0x138 )
                v59 = (unsigned int)a7;
              memmove(v93, Src, v59);
              v60 = 320;
              if ( (unsigned int)a5 < 0x140 )
                v60 = (unsigned int)a5;
              memmove(v94, &v96, v60);
              *((_QWORD *)v16 + 897) = v16 + 1792;
              *((_QWORD *)v16 + 896) = v16 + 1792;
              *((_QWORD *)v16 + 899) = v16 + 1796;
              *((_QWORD *)v16 + 898) = v16 + 1796;
              *((_QWORD *)v16 + 901) = v16 + 1796;
              *((_QWORD *)v16 + 902) = v16 + 1792;
              *((_QWORD *)v16 + 894) = v16 + 1786;
              *((_QWORD *)v16 + 893) = v16 + 1786;
              *((_QWORD *)v16 + 913) = 600000000;
              if ( (unsigned int)bCreateSemaphores((struct CDDPDEV *)v16) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v62, v61) + 72) + 3400LL) )
                  *((_DWORD *)v16 + 686) ^= ((unsigned __int8)*((_DWORD *)v16 + 686)
                                           ^ (unsigned __int8)(16 * *((_DWORD *)v16 + 475)))
                                          & 0x40;
                v63 = *((_DWORD *)v16 + 686);
                v64 = v63 ^ (*((_DWORD *)v16 + 475) >> 17);
                *((_BYTE *)v16 + 12716) = 0;
                *((_QWORD *)v16 + 1600) = 0;
                v65 = v63 ^ v64 & 0x800;
                v66 = *((_DWORD *)v16 + 546) < 0x2000;
                *((_DWORD *)v16 + 686) = v65;
                if ( !v66 && (v65 & 0x40) != 0 )
                {
                  *((_BYTE *)v16 + 12716) = 1;
                  v67 = operator new(0x10u);
                  if ( !v67 )
                  {
                    *((_QWORD *)v16 + 1600) = 0;
                    WdLogSingleEntry1(6, v16);
                    v23 = 1097;
                    goto LABEL_122;
                  }
                  v67[1] = 0;
                  *v67 = 0;
                  *((_QWORD *)v16 + 1600) = v67;
                }
                *((_QWORD *)v16 + 1599) = v16 + 3196;
                *((_QWORD *)v16 + 1598) = v16 + 3196;
                v68 = 0x4000;
                v69 = *((_DWORD *)v16 + 475);
                v70 = ((v69 >> 17) & 7) + 11;
                v71 = (unsigned int)(1 << (((v69 >> 17) & 7) + 11));
                if ( (unsigned int)(1 << (((v69 >> 14) & 7) + 11)) < 0x4000 )
                  v68 = 1 << (((*((_DWORD *)v16 + 475) >> 14) & 7) + 11);
                *((_DWORD *)v16 + 618) = v68;
                if ( (unsigned int)v71 < 0x4000 )
                  v50 = 1 << (((v69 >> 17) & 7) + 11);
                *((_DWORD *)v16 + 619) = v50;
                if ( (v69 & 0x40000000) != 0
                  && (v70 = *(_QWORD *)(W32GetSessionState(v70, v71) + 72), *(_DWORD *)(v70 + 3388))
                  || (v72 = *(_QWORD *)(W32GetSessionState(v70, v71) + 72), *(_DWORD *)(v72 + 3388) == 2) )
                {
                  if ( ((_DWORD)v16[475] & 0x3C00u) < 0x800 )
                  {
                    WdLogSingleEntry1(2, 0);
                    v23 = 1117;
                    goto LABEL_38;
                  }
                  *((_BYTE *)v16 + 2751) = 1;
                  v72 = (*((_DWORD *)v16 + 475) >> 10) & 0xF;
                  v73 = (1 << ((*((_DWORD *)v16 + 475) >> 10) & 0xF)) - 1;
                  *((_QWORD *)v16 + 909) = v73;
                  *((_QWORD *)v16 + 910) = ~(__int64)v73;
                }
                if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v72, v71) + 72) + 3392LL) )
                  *((_DWORD *)v16 + 475) |= 0x20000000u;
                if ( ((_DWORD)v16[686] & 0x40) != 0 )
                {
                  if ( (int)CHwCommandBuffer::CreateCommandBuffer(
                              (CHwCommandBuffer *)(v16 + 2098),
                              (struct CDDPDEV *)v16,
                              0,
                              0x10000u) < 0 )
                  {
                    WdLogSingleEntry0(6);
                    v23 = 1138;
                    goto LABEL_122;
                  }
                  if ( (int)CHwCommandBuffer::CreateCommandBuffer(
                              (CHwCommandBuffer *)(v16 + 2636),
                              (struct CDDPDEV *)v16,
                              1u,
                              0x10000u) < 0 )
                  {
                    WdLogSingleEntry0(6);
                    v23 = 1143;
                    goto LABEL_122;
                  }
                  *((_QWORD *)v16 + 1588) = v16 + 2636;
                  *((_QWORD *)v16 + 1587) = v16 + 2098;
                  v74 = (CddBitmapBase *)operator new(0x80u);
                  if ( v74 )
                  {
                    CddBitmapBase::CddBitmapBase(v74, (struct CDDPDEV *)v16);
                    *v75 = &CddBitmapStagingApertureMem::`vftable';
                  }
                  else
                  {
                    v75 = 0;
                  }
                  *((_QWORD *)v16 + 687) = v75;
                  if ( !v75 )
                  {
                    WdLogSingleEntry0(6);
                    v23 = 1152;
                    goto LABEL_122;
                  }
                }
                v76 = *((unsigned int *)v16 + 200);
                v77 = *((unsigned int *)v16 + 199);
                v78 = ((_DWORD)v16[475] & 0x20000000) == 0;
                *((_QWORD *)v16 + 892) = v16 + 1376;
                if ( (int)CStagingPoolBase::CreateStagingPool(v16 + 1376, v16, v77, v76, 2, !v78) >= 0 )
                {
                  if ( (int)CStagingPool::InitGdiSurfaces((CStagingPool *)(v16 + 1376), (struct CDDPDEV *)v16) >= 0 )
                  {
                    if ( ((_DWORD)v16[475] & 0x20000000) != 0 )
                    {
                      if ( (int)CStagingPoolBase::CreateStagingPool(
                                  v16 + 1580,
                                  v16,
                                  *((_DWORD *)v16 + 199) >> 2,
                                  *((_DWORD *)v16 + 200) >> 2,
                                  1,
                                  2) < 0 )
                      {
                        WdLogSingleEntry1(2, v16);
                        v23 = 1207;
                        goto LABEL_38;
                      }
                      if ( (int)CStagingPool::InitGdiSurfaces((CStagingPool *)(v16 + 1580), (struct CDDPDEV *)v16) < 0 )
                      {
                        WdLogSingleEntry1(2, v16);
                        v23 = 1212;
                        goto LABEL_38;
                      }
                      *((_QWORD *)v16 + 892) = v16 + 1580;
                    }
                    if ( !(unsigned int)WorkerThreadStartup(v16, v79) )
                    {
                      WdLogSingleEntry5(
                        3,
                        v16,
                        *v19,
                        *((unsigned int *)v16 + 199),
                        *((unsigned int *)v16 + 200),
                        *((int *)v16 + 258));
                      v23 = 1224;
                      WdLogGlobalForLineNumber = 1224;
                      v24 = (_QWORD *)WdLogNewEntry5_WdWarning();
                      goto LABEL_123;
                    }
                    *((_BYTE *)v16 + 2748) = 1;
                    WdLogSingleEntry5(
                      4,
                      v16,
                      *((_QWORD *)v16 + 1),
                      *((unsigned int *)v16 + 199),
                      *((unsigned int *)v16 + 200),
                      *((unsigned int *)v16 + 279));
                    WdLogGlobalForLineNumber = 1232;
                    v80 = (_QWORD *)WdLogNewEntry5_WdEvent();
                    v80[3] = gCddImageInfo;
                    v80[4] = (unsigned int)dword_14003E570;
                    v80[5] = 215857758;
                    WdLogGlobalForLineNumber = 1232;
                    v81 = (void (__fastcall *)(_QWORD, DHPDEV))*((_QWORD *)v16 + 42);
                    if ( v81 )
                      v81(*v20, v16 + 624);
                    v82 = *v21;
                    v94 = (void *)WNF_SEB_SYSTEM_LPE;
                    v83 = (*((__int64 (__fastcall **)(__int64 (__fastcall *)(struct _EX_WNF_SUBSCRIPTION *, const struct _WNF_STATE_NAME *, unsigned int, unsigned int, const struct _WNF_TYPE_ID *, void *), __int64, void **, __int64, DHPDEV))v16
                           + 52))(
                            CddWnfStateChangeCallback,
                            v82,
                            &v94,
                            1,
                            v16);
                    *((_QWORD *)v16 + 95) = v83;
                    if ( !v83 )
                    {
                      WdLogSingleEntry1(3, v16);
                      WdLogGlobalForLineNumber = 1256;
                      v84 = (_QWORD *)WdLogNewEntry5_WdWarning();
                      v84[3] = gCddImageInfo;
                      v84[4] = (unsigned int)dword_14003E570;
                      v84[5] = 215857758;
                      WdLogGlobalForLineNumber = 1256;
                    }
                    if ( !*((_BYTE *)v16 + 12716) )
                      return v16;
                    v85 = *v21;
                    v94 = (void *)WNF_DX_VIDMM_TRIM_NOTIFICATION;
                    v86 = (*((__int64 (__fastcall **)(__int64 (__fastcall *)(struct _EX_WNF_SUBSCRIPTION *, const struct _WNF_STATE_NAME *, unsigned int, unsigned int, const struct _WNF_TYPE_ID *, void *), __int64, void **, __int64, DHPDEV))v16
                           + 52))(
                            CddWnfTrimCallback,
                            v85,
                            &v94,
                            1,
                            v16);
                    *((_QWORD *)v16 + 96) = v86;
                    if ( v86 )
                      return v16;
                    WdLogSingleEntry1(2, v16);
                    v23 = 1283;
                    goto LABEL_38;
                  }
                  WdLogSingleEntry1(2, v16);
                  v23 = 1192;
                }
                else
                {
                  WdLogSingleEntry1(2, v16);
                  v23 = 1187;
                }
              }
              else
              {
                WdLogSingleEntry5(
                  2,
                  v16,
                  *((_QWORD *)v16 + 1),
                  *((unsigned int *)v16 + 199),
                  *((unsigned int *)v16 + 200),
                  *((unsigned int *)v16 + 279));
                v23 = 1067;
              }
            }
            else
            {
              WdLogSingleEntry5(2, v16, *((_QWORD *)v16 + 1), v57, v58, *((unsigned int *)v16 + 279));
              v23 = 1004;
            }
          }
          else
          {
            WdLogSingleEntry1(2, v16);
            v23 = 954;
          }
        }
        else
        {
          WdLogSingleEntry5(2, inited, v16, v46, &v96, Src);
          v23 = 920;
        }
      }
      else
      {
        WdLogSingleEntry4(2, *(_QWORD *)v16, *v20, v43, *v21);
        v23 = 878;
      }
    }
    else
    {
      WdLogSingleEntry4(2, v39, v16, v40, a9);
      v23 = 862;
    }
LABEL_38:
    WdLogGlobalForLineNumber = v23;
    v24 = (_QWORD *)WdLogNewEntry5_WdError();
    goto LABEL_123;
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 723;
  v17 = (_QWORD *)WdLogNewEntry5_WdLowResource();
  v17[3] = gCddImageInfo;
  v17[4] = (unsigned int)dword_14003E570;
  v17[5] = 215857758;
  WdLogGlobalForLineNumber = 723;
  return 0;
}

```

## disassembly

```asm
0x14001d980  push    rbp
0x14001d982  push    rbx
0x14001d983  push    rsi
0x14001d984  push    rdi
0x14001d985  push    r12
0x14001d987  push    r13
0x14001d989  push    r14
0x14001d98b  push    r15
0x14001d98d  lea     rbp, [rsp-208h]
0x14001d995  sub     rsp, 308h
0x14001d99c  mov     rax, cs:__security_cookie
0x14001d9a3  xor     rax, rsp
0x14001d9a6  mov     [rbp+240h+var_50], rax
0x14001d9ad  mov     rax, [rbp+240h+arg_28]
0x14001d9b4  mov     rdi, rcx
0x14001d9b7  mov     rbx, [rbp+240h+arg_40]
0x14001d9be  xor     edx, edx; Val
0x14001d9c0  mov     r15, [rbp+240h+arg_50]
0x14001d9c7  mov     r8d, 140h; Size
0x14001d9cd  mov     [rsp+340h+var_2D8], rax
0x14001d9d2  mov     rax, [rbp+240h+arg_38]
0x14001d9d9  mov     [rsp+340h+var_2E8], rcx
0x14001d9de  lea     rcx, [rbp+240h+var_190]; void *
0x14001d9e5  mov     [rsp+340h+var_2E0], rax
0x14001d9ea  call    memset
0x14001d9ef  xor     edx, edx; Val
0x14001d9f1  lea     rcx, [rsp+340h+Src]; void *
0x14001d9f6  mov     r8d, 138h; Size
0x14001d9fc  call    memset
0x14001da01  xor     r14d, r14d
0x14001da04  mov     [rsp+340h+var_2F0], r14
0x14001da09  mov     [rsp+340h+var_300], r14d
0x14001da0e  test    r15, r15
0x14001da11  jnz     loc_14001DAD5
0x14001da17  mov     rdx, rbx
0x14001da1a  mov     r8, rdi
0x14001da1d  lea     ebx, [r15+2]
0x14001da21  mov     ecx, ebx
0x14001da23  call    cs:__imp_WdLogSingleEntry2
0x14001da2a  nop     dword ptr [rax+rax+00h]
0x14001da2f  mov     edi, 2C6h
0x14001da34  mov     cs:WdLogGlobalForLineNumber, edi
0x14001da3a  call    cs:__imp_WdLogNewEntry5_WdError
0x14001da41  nop     dword ptr [rax+rax+00h]
0x14001da46  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001da4d  mov     esi, 0CDDBA5Eh
0x14001da52  mov     [rax+18h], rcx
0x14001da56  mov     ecx, cs:dword_14003E570
0x14001da5c  mov     [rax+20h], rcx
0x14001da60  mov     [rax+28h], rsi
0x14001da64  mov     rax, cs:KdDebuggerEnabled
0x14001da6b  mov     cs:WdLogGlobalForLineNumber, edi
0x14001da71  cmp     [rax], r14b
0x14001da74  jz      loc_14001ED7A
0x14001da7a  lea     rcx, aDrvenablepdevI; "DrvEnablePDEV is called with hDriver eq"...
0x14001da81  call    cs:__imp_DbgPrint
0x14001da88  nop     dword ptr [rax+rax+00h]
0x14001da8d  mov     ecx, ebx
0x14001da8f  call    cs:__imp_WdLogSingleEntry0
0x14001da96  nop     dword ptr [rax+rax+00h]
0x14001da9b  lea     ebx, [rdi+2]
0x14001da9e  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001daa4  call    cs:__imp_WdLogNewEntry5_WdError
0x14001daab  nop     dword ptr [rax+rax+00h]
0x14001dab0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001dab7  mov     [rax+18h], rcx
0x14001dabb  mov     ecx, cs:dword_14003E570
0x14001dac1  mov     [rax+20h], rcx
0x14001dac5  mov     [rax+28h], rsi
0x14001dac9  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001dacf  int     3; Trap to Debugger
0x14001dad0  jmp     loc_14001ED7A
0x14001dad5  mov     r12d, 1
0x14001dadb  mov     edx, 3208h; cjMemSize
0x14001dae0  mov     ecx, r12d; fl
0x14001dae3  mov     r8d, 64646344h; ulTag
0x14001dae9  call    cs:__imp_EngAllocMem
0x14001daf0  nop     dword ptr [rax+rax+00h]
0x14001daf5  mov     rdi, rax
0x14001daf8  test    rax, rax
0x14001dafb  jnz     short loc_14001DB4C
0x14001dafd  lea     ecx, [rax+6]
0x14001db00  call    cs:__imp_WdLogSingleEntry0
0x14001db07  nop     dword ptr [rax+rax+00h]
0x14001db0c  mov     ebx, 2D3h
0x14001db11  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001db17  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x14001db1e  nop     dword ptr [rax+rax+00h]
0x14001db23  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001db2a  mov     esi, 0CDDBA5Eh
0x14001db2f  mov     [rax+18h], rcx
0x14001db33  mov     ecx, cs:dword_14003E570
0x14001db39  mov     [rax+20h], rcx
0x14001db3d  mov     [rax+28h], rsi
0x14001db41  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001db47  jmp     loc_14001ED7A
0x14001db4c  mov     [rax+0A6Ch], r12d
0x14001db53  lea     rsi, [rdi+238h]
0x14001db5a  mov     [rax+0A78h], r14d
0x14001db61  mov     eax, [rax+0AB8h]
0x14001db67  and     eax, 0FFFFFFF7h
0x14001db6a  mov     dword ptr [rdi+0A80h], 3
0x14001db74  or      eax, 22h
0x14001db77  mov     dword ptr [rdi+0A88h], 3Fh ; '?'
0x14001db81  mov     [rdi+0AB8h], eax
0x14001db87  lea     rax, ?CddAddD3DDirtyRgn@@YAXQEAXQEBUtagRECT@@@Z; CddAddD3DDirtyRgn(void * const,tagRECT const * const)
0x14001db8e  mov     [rdi+2A8h], rax
0x14001db95  lea     rax, ?CddW32kCloseProcess@@YAXQEAXPEAU_EPROCESS@@@Z; CddW32kCloseProcess(void * const,_EPROCESS *)
0x14001db9c  mov     [rdi+2B8h], rax
0x14001dba3  lea     rax, ?CddDriverSupportsLiteModeChange@@YAHPEAX@Z; CddDriverSupportsLiteModeChange(void *)
0x14001dbaa  mov     [rdi+2C0h], rax
0x14001dbb1  lea     rax, ?CddUpdateDevMode@@YAHPEAXPEAU_devicemodeW@@1PEAU_GDIINFO@@2PEAPEAUHSURF__@@@Z; CddUpdateDevMode(void *,_devicemodeW *,_devicemodeW *,_GDIINFO *,_GDIINFO *,HSURF__ * *)
0x14001dbb8  mov     [rdi+2C8h], rax
0x14001dbbf  mov     dword ptr [rdi+0A90h], 7Fh
0x14001dbc9  mov     dword ptr [rsi], 0A0h
0x14001dbcf  mov     dword ptr [rdi+23Ch], 4
0x14001dbd9  mov     [rdi+0AA8h], r14
0x14001dbe0  mov     [rdi+0AB0h], r14b
0x14001dbe7  mov     dword ptr [rdi+31A8h], 600000h
0x14001dbf1  call    cs:__imp_W32GetSessionState
0x14001dbf8  nop     dword ptr [rax+rax+00h]
0x14001dbfd  cmp     [rbp+240h+arg_58], 0
0x14001dc04  lea     r13, [rdi+310h]
0x14001dc0b  lea     r14, [rdi+9B8h]
0x14001dc12  mov     r8, rsi
0x14001dc15  mov     r9, r14
0x14001dc18  mov     rdx, rbx
0x14001dc1b  mov     rcx, [rax+48h]
0x14001dc1f  lea     rax, [rdi+1C48h]
0x14001dc26  mov     [rcx+0D38h], r12d
0x14001dc2d  lea     r12, [rdi+2F0h]
0x14001dc34  mov     [rsp+340h+Size], r12
0x14001dc39  mov     rcx, r15
0x14001dc3c  mov     qword ptr [rsp+340h+Flags], r13
0x14001dc41  mov     [rax+8], rax
0x14001dc45  mov     [rax], rax
0x14001dc48  jz      short loc_14001DC71
0x14001dc4a  lea     rax, ?RmtW32kCloseProcess@@YAXQEAXPEAU_EPROCESS@@@Z; RmtW32kCloseProcess(void * const,_EPROCESS *)
0x14001dc51  mov     [rsi+80h], rax
0x14001dc58  lea     rax, _guard_check_icall_nop
0x14001dc5f  mov     [rsi+70h], rax
0x14001dc63  lea     rax, ?RmtDeleteDeviceBitmapExSurf@@YAXPEAU_SURFOBJ@@@Z; RmtDeleteDeviceBitmapExSurf(_SURFOBJ *)
0x14001dc6a  mov     [rsi+98h], rax
0x14001dc71  call    cs:__imp_EngQueryW32kCddInterface
0x14001dc78  nop     dword ptr [rax+rax+00h]
0x14001dc7d  test    eax, eax
0x14001dc7f  jns     short loc_14001DCCA
0x14001dc81  movsxd  rdx, eax
0x14001dc84  mov     r9, rdi
0x14001dc87  mov     [rsp+340h+Size], 0A0h
0x14001dc90  mov     r8, r15
0x14001dc93  mov     ecx, 2
0x14001dc98  mov     qword ptr [rsp+340h+Flags], rbx
0x14001dc9d  call    cs:__imp_WdLogSingleEntry5
0x14001dca4  nop     dword ptr [rax+rax+00h]
0x14001dca9  mov     ebx, 2FBh
0x14001dcae  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001dcb4  call    cs:__imp_WdLogNewEntry5_WdError
0x14001dcbb  nop     dword ptr [rax+rax+00h]
0x14001dcc0  mov     esi, 0CDDBA5Eh
0x14001dcc5  jmp     loc_14001ED48
0x14001dcca  mov     edx, 60h ; '`'
0x14001dccf  mov     esi, 64646344h
0x14001dcd4  mov     r8d, esi
0x14001dcd7  lea     ecx, [rdx-20h]
0x14001dcda  call    cs:__imp_ExAllocatePool2
0x14001dce1  nop     dword ptr [rax+rax+00h]
0x14001dce6  mov     [rdi+308h], rax
0x14001dced  test    rax, rax
0x14001dcf0  jz      loc_14001ED67
0x14001dcf6  xor     ecx, ecx
0x14001dcf8  xor     r8d, r8d; Free
0x14001dcfb  mov     [rsp+340h+Depth], cx; Depth
0x14001dd00  xor     edx, edx; Allocate
0x14001dd02  mov     [rsp+340h+Tag], esi; Tag
0x14001dd06  mov     [rsp+340h+Size], 438h; unsigned int
0x14001dd0f  mov     [rsp+340h+Flags], ecx; Flags
0x14001dd13  lea     r9d, [rcx+1]; PoolType
0x14001dd17  mov     rcx, rax; Lookaside
0x14001dd1a  call    cs:__imp_ExInitializeLookasideListEx
0x14001dd21  nop     dword ptr [rax+rax+00h]
0x14001dd26  mov     dword ptr [rsp+340h+var_2F8], eax
0x14001dd2a  test    eax, eax
0x14001dd2c  jns     short loc_14001DDA2
0x14001dd2e  movsxd  rdx, eax
0x14001dd31  mov     ecx, 2
0x14001dd36  call    cs:__imp_WdLogSingleEntry1
0x14001dd3d  nop     dword ptr [rax+rax+00h]
0x14001dd42  mov     ebx, 309h
0x14001dd47  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001dd4d  call    cs:__imp_WdLogNewEntry5_WdError
0x14001dd54  nop     dword ptr [rax+rax+00h]
0x14001dd59  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001dd60  mov     esi, 0CDDBA5Eh
0x14001dd65  xor     edx, edx; Tag
0x14001dd67  mov     [rax+18h], rcx
0x14001dd6b  mov     ecx, cs:dword_14003E570
0x14001dd71  mov     [rax+20h], rcx
0x14001dd75  mov     [rax+28h], rsi
0x14001dd79  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001dd7f  mov     rcx, [rdi+308h]; P
0x14001dd86  call    cs:__imp_ExFreePoolWithTag
0x14001dd8d  nop     dword ptr [rax+rax+00h]
0x14001dd92  mov     qword ptr [rdi+308h], 0
0x14001dd9d  jmp     loc_14001ED67
0x14001dda2  cmp     qword ptr [r14], 0
0x14001dda6  mov     esi, 0CDDBA5Eh
0x14001ddab  jz      short loc_14001DDB4
0x14001ddad  cmp     qword ptr [r12], 0
0x14001ddb2  jnz     short loc_14001DDFE
0x14001ddb4  mov     ecx, 1
0x14001ddb9  call    cs:__imp_WdLogSingleEntry0
0x14001ddc0  nop     dword ptr [rax+rax+00h]
0x14001ddc5  mov     cs:WdLogGlobalForLineNumber, 30Fh
0x14001ddcf  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001ddd6  nop     dword ptr [rax+rax+00h]
0x14001dddb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001dde2  mov     [rax+18h], rcx
0x14001dde6  mov     ecx, cs:dword_14003E570
0x14001ddec  mov     [rax+20h], rcx
0x14001ddf0  mov     [rax+28h], rsi
0x14001ddf4  mov     cs:WdLogGlobalForLineNumber, 30Fh
0x14001ddfe  xor     r9d, r9d
0x14001de01  xor     r8d, r8d
0x14001de04  xor     edx, edx
0x14001de06  xor     ecx, ecx
0x14001de08  call    cs:__imp_CddEngCreateRectRgn
0x14001de0f  nop     dword ptr [rax+rax+00h]
0x14001de14  xor     r9d, r9d
0x14001de17  xor     r8d, r8d
0x14001de1a  xor     edx, edx
0x14001de1c  mov     [rdi+0AF0h], rax
0x14001de23  xor     ecx, ecx
0x14001de25  call    cs:__imp_CddEngCreateRectRgn
0x14001de2c  nop     dword ptr [rax+rax+00h]
0x14001de31  xor     r9d, r9d
0x14001de34  xor     r8d, r8d
0x14001de37  xor     edx, edx
0x14001de39  mov     [rdi+0AF8h], rax
0x14001de40  xor     ecx, ecx
0x14001de42  call    cs:__imp_CddEngCreateRectRgn
0x14001de49  nop     dword ptr [rax+rax+00h]
0x14001de4e  xor     r9d, r9d
0x14001de51  xor     r8d, r8d
0x14001de54  xor     edx, edx
0x14001de56  mov     [rdi+0B00h], rax
0x14001de5d  xor     ecx, ecx
0x14001de5f  call    cs:__imp_CddEngCreateRectRgn
0x14001de66  nop     dword ptr [rax+rax+00h]
0x14001de6b  xor     r9d, r9d
0x14001de6e  xor     r8d, r8d
0x14001de71  xor     edx, edx
0x14001de73  mov     [rdi+0B08h], rax
0x14001de7a  xor     ecx, ecx
0x14001de7c  call    cs:__imp_CddEngCreateRectRgn
0x14001de83  nop     dword ptr [rax+rax+00h]
0x14001de88  xor     r9d, r9d
0x14001de8b  xor     r8d, r8d
0x14001de8e  xor     edx, edx
0x14001de90  mov     [rdi+0B10h], rax
0x14001de97  xor     ecx, ecx
0x14001de99  call    cs:__imp_CddEngCreateRectRgn
0x14001dea0  nop     dword ptr [rax+rax+00h]
0x14001dea5  xor     r9d, r9d
0x14001dea8  xor     r8d, r8d
0x14001deab  xor     edx, edx
0x14001dead  mov     [rdi+0B18h], rax
0x14001deb4  xor     ecx, ecx
0x14001deb6  call    cs:__imp_CddEngCreateRectRgn
0x14001debd  nop     dword ptr [rax+rax+00h]
0x14001dec2  xor     r9d, r9d
0x14001dec5  xor     r8d, r8d
0x14001dec8  xor     edx, edx
0x14001deca  mov     [rdi+0B20h], rax
0x14001ded1  xor     ecx, ecx
0x14001ded3  call    cs:__imp_CddEngCreateRectRgn
0x14001deda  nop     dword ptr [rax+rax+00h]
0x14001dedf  xor     r9d, r9d
0x14001dee2  xor     r8d, r8d
0x14001dee5  xor     edx, edx
0x14001dee7  mov     [rdi+0B28h], rax
0x14001deee  xor     ecx, ecx
0x14001def0  call    cs:__imp_CddEngCreateRectRgn
0x14001def7  nop     dword ptr [rax+rax+00h]
0x14001defc  xor     r9d, r9d
0x14001deff  xor     r8d, r8d
0x14001df02  xor     edx, edx
0x14001df04  mov     [rdi+0B30h], rax
0x14001df0b  xor     ecx, ecx
0x14001df0d  call    cs:__imp_CddEngCreateRectRgn
0x14001df14  nop     dword ptr [rax+rax+00h]
0x14001df19  mov     edx, 38h ; '8'
0x14001df1e  mov     r8d, 64646344h
0x14001df24  mov     [rdi+0B38h], rax
0x14001df2b  lea     ecx, [rdx+8]
0x14001df2e  call    cs:__imp_ExAllocatePool2
0x14001df35  nop     dword ptr [rax+rax+00h]
0x14001df3a  mov     edx, 38h ; '8'
0x14001df3f  mov     r8d, 64646344h
0x14001df45  mov     [rdi+0B40h], rax
  ... truncated ...
```
