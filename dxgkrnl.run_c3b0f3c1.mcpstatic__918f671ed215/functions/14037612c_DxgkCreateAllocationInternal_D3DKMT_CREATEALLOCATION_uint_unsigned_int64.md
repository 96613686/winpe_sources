# DxgkCreateAllocationInternal(_D3DKMT_CREATEALLOCATION *,uint *,unsigned __int64 *)

- ea: `0x14037612c`
- end: `0x140377079`
- name: `?DxgkCreateAllocationInternal@@YAJPEAU_D3DKMT_CREATEALLOCATION@@PEAIPEA_K@Z`
- size: `3917`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEALLOCATION *Src, unsigned int *, struct DXGRESOURCE *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1403760e0`
- `0x14040e140`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012cd4`
- `0x140013a20`
- `0x140015a70`
- `0x140015b30`
- `0x1400169f0`
- `0x140018054`
- `0x14001a874`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001c790`
- `0x14001cff0`
- `0x14001d214`
- `0x14001f2f0`
- `0x14002ef40`
- `0x1400309f0`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401e784c`
- `0x14020fd60`
- `0x14021057c`
- `0x140324bfc`
- `0x14032a5c4`
- `0x14032aaa8`
- `0x140374d98`
- `0x14037612c`
- `0x140377080`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403761d9`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x1403761d9`
- `watchdog!WdLogSingleEntry2` at `0x1403765a3`
- `watchdog!WdLogSingleEntry2` at `0x14037660a`
- `watchdog!WdLogSingleEntry2` at `0x140376672`
- `watchdog!WdLogSingleEntry2` at `0x1403766a5`
- `watchdog!WdLogSingleEntry2` at `0x140376c8b`
- `watchdog!WdLogSingleEntry2` at `0x140376db8`
- `watchdog!WdLogSingleEntry2` at `0x140376de7`
- `watchdog!WdLogSingleEntry2` at `0x140376e43`
- `watchdog!WdLogSingleEntry2` at `0x140376ed2`
- `watchdog!WdLogSingleEntry2` at `0x1403765a3`
- `watchdog!WdLogSingleEntry2` at `0x14037660a`
- `watchdog!WdLogSingleEntry2` at `0x140376672`
- `watchdog!WdLogSingleEntry2` at `0x1403766a5`
- `watchdog!WdLogSingleEntry2` at `0x140376c8b`
- `watchdog!WdLogSingleEntry2` at `0x140376db8`
- `watchdog!WdLogSingleEntry2` at `0x140376de7`
- `watchdog!WdLogSingleEntry2` at `0x140376e43`
- `watchdog!WdLogSingleEntry2` at `0x140376ed2`
- `watchdog!WdLogSingleEntry3` at `0x140376707`
- `watchdog!WdLogSingleEntry3` at `0x140376d7d`
- `watchdog!WdLogSingleEntry3` at `0x140376707`
- `watchdog!WdLogSingleEntry3` at `0x140376d7d`
- `watchdog!WdLogSingleEntry0` at `0x140376833`
- `watchdog!WdLogSingleEntry0` at `0x140376990`
- `watchdog!WdLogSingleEntry0` at `0x1403769e5`
- `watchdog!WdLogSingleEntry0` at `0x140376ccc`
- `watchdog!WdLogSingleEntry0` at `0x140376d20`
- `watchdog!WdLogSingleEntry0` at `0x140376833`
- `watchdog!WdLogSingleEntry0` at `0x140376990`
- `watchdog!WdLogSingleEntry0` at `0x1403769e5`
- `watchdog!WdLogSingleEntry0` at `0x140376ccc`
- `watchdog!WdLogSingleEntry0` at `0x140376d20`
- `watchdog!WdLogSingleEntry1` at `0x140376bb3`
- `watchdog!WdLogSingleEntry1` at `0x140376c26`
- `watchdog!WdLogSingleEntry1` at `0x140376bb3`
- `watchdog!WdLogSingleEntry1` at `0x140376c26`

## string_xrefs

- `0x140376d4b`: `NoKmdAccess cannot be used with StandardAllocation`
- `0x140376cf7`: `NoKmdAccess can be used only with testsigning`

## pseudocode

```c
__int64 __fastcall DxgkCreateAllocationInternal(
        struct _D3DKMT_CREATEALLOCATION *Src,
        unsigned int *a2,
        struct DXGRESOURCE *a3)
{
  struct DXGPROCESS *Current; // r13
  char CurrentThreadPreviousMode; // si
  struct DXGDEVICE *v6; // rsi
  char Flags; // cl
  int v8; // eax
  int v9; // r12d
  __int64 v10; // rax
  enum _D3DKMDT_STANDARDALLOCATION_TYPE v11; // edx
  ADAPTER_RENDER **v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // r8
  int StandardAllocationDriverData; // r15d
  bool v23; // [rsp+80h] [rbp-1F8h]
  unsigned int v24; // [rsp+88h] [rbp-1F0h] BYREF
  __int64 v25; // [rsp+90h] [rbp-1E8h]
  char v26; // [rsp+98h] [rbp-1E0h]
  char v27; // [rsp+A0h] [rbp-1D8h]
  struct DXGDEVICE *v28; // [rsp+A8h] [rbp-1D0h] BYREF
  unsigned int v29; // [rsp+B0h] [rbp-1C8h] BYREF
  struct DXGRESOURCE *v30; // [rsp+B8h] [rbp-1C0h]
  void *v31; // [rsp+C0h] [rbp-1B8h] BYREF
  struct DXGDEVICE *v32[2]; // [rsp+C8h] [rbp-1B0h] BYREF
  void *v33; // [rsp+D8h] [rbp-1A0h]
  _D3DKMT_CREATEALLOCATION v34; // [rsp+E0h] [rbp-198h] BYREF
  _BYTE v35[16]; // [rsp+130h] [rbp-148h] BYREF
  _BYTE v36[8]; // [rsp+140h] [rbp-138h] BYREF
  __int64 v37; // [rsp+148h] [rbp-130h]
  char v38; // [rsp+150h] [rbp-128h]
  int Size; // [rsp+158h] [rbp-120h] BYREF
  __int64 v40; // [rsp+15Ch] [rbp-11Ch]
  int v41; // [rsp+164h] [rbp-114h]
  __int64 v42; // [rsp+168h] [rbp-110h]
  struct _D3DKMT_CREATESTANDARDALLOCATION v43; // [rsp+170h] [rbp-108h] BYREF
  _BYTE v44[160]; // [rsp+190h] [rbp-E8h] BYREF

  v30 = a3;
  v31 = a2;
  *a2 = 0;
  v24 = -1;
  v25 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v26 = 1;
    v24 = 2003;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2003);
  }
  else
  {
    v26 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v24, 2003);
  Current = DXGPROCESS::GetCurrent();
  v32[1] = Current;
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v27 = CurrentThreadPreviousMode;
  v23 = CurrentThreadPreviousMode == 1;
  if ( !Current )
  {
    WdLogSingleEntry1(2, -1073741811);
    WdLogGlobalForLineNumber = 9099;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid process context, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0,
      0);
    goto LABEL_41;
  }
  memset(&v34, 0, sizeof(v34));
  memset(&v43, 0, sizeof(v43));
  if ( CurrentThreadPreviousMode == 1 )
    RtlCopyFromUser(&v34, Src, 0x48u);
  else
    v34 = *Src;
  v32[0] = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v28, v34.hDevice, Current, v32);
  v6 = v32[0];
  if ( !v32[0] )
  {
    WdLogSingleEntry2(2, v34.hDevice, -1073741811);
    WdLogGlobalForLineNumber = 9141;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      v34.hDevice,
      -1073741811,
      0,
      0,
      0);
    goto LABEL_72;
  }
  Flags = (char)v34.Flags;
  if ( (*(_DWORD *)&v34.Flags & 0x100000) != 0 )
  {
    if ( (*(_DWORD *)&v34.Flags & 0x10000) != 0 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 9150;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NoKmdAccess cannot be used with StandardAllocation",
        9150,
        0,
        0,
        0,
        0);
      goto LABEL_72;
    }
    if ( !g_OSTestSigningEnabled )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 9155;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NoKmdAccess can be used only with testsigning",
        9155,
        0,
        0,
        0,
        0);
      goto LABEL_72;
    }
  }
  if ( v34.NumAllocations > 0x682AA )
  {
    WdLogSingleEntry3(3, v32[0], v34.NumAllocations, -1073741811);
    WdLogGlobalForLineNumber = 9168;
    goto LABEL_72;
  }
  if ( (*((_DWORD *)Current + 102) & 0x100) == 0
    && ((*(_BYTE *)&v34.Flags & 8) != 0
     || (*(_WORD *)&v34.Flags & 0x100) != 0
     || (*(_WORD *)&v34.Flags & 0x1000) != 0
     || (*(_WORD *)&v34.Flags & 0x200) != 0) )
  {
    WdLogSingleEntry2(3, v32[0], -1073741811);
    WdLogGlobalForLineNumber = 9182;
    goto LABEL_72;
  }
  if ( (*(_BYTE *)&v34.Flags & 0x20) != 0
    && (*(_DWORD *)&v34.Flags & 0x10000) == 0
    && (*((_DWORD *)Current + 102) & 0x100) == 0 )
  {
    WdLogSingleEntry2(3, v32[0], -1073741811);
    WdLogGlobalForLineNumber = 9196;
    goto LABEL_72;
  }
  if ( (*(_DWORD *)&v34.Flags & 0x20000) != 0 )
  {
    if ( (*(_DWORD *)&v34.Flags & 0x10000) == 0 )
    {
      WdLogSingleEntry2(3, v32[0], -1073741811);
      WdLogGlobalForLineNumber = 9208;
      goto LABEL_72;
    }
  }
  else if ( (*(_DWORD *)&v34.Flags & 0x10000) == 0 )
  {
    goto LABEL_15;
  }
  v9 = ValidateStandardAllocationParams(&v34, &v43, v23);
  if ( v9 < 0 )
  {
LABEL_69:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v28);
    goto LABEL_27;
  }
  Flags = (char)v34.Flags;
LABEL_15:
  if ( (Flags & 2) != 0 && (Flags & 1) == 0 )
  {
    WdLogSingleEntry2(3, v6, -1073741811);
    WdLogGlobalForLineNumber = 9230;
    goto LABEL_72;
  }
  if ( !v34.hResource && !v34.NumAllocations )
  {
    WdLogSingleEntry2(3, v6, -1073741811);
    WdLogGlobalForLineNumber = 9241;
LABEL_72:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v28);
LABEL_41:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
    if ( v26 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v16, EventProfilerExit, v17, v24);
    return 3221225485LL;
  }
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35,
    v6);
  v37 = *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL);
  v38 = 0;
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
  COREDEVICEACCESS::COREDEVICEACCESS(v44, v6, 2);
  v8 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v44, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    WdLogSingleEntry2(3, v6, v8);
    WdLogGlobalForLineNumber = 9260;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v44);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35);
    goto LABEL_69;
  }
  *(_DWORD *)v31 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL) + 420LL);
  v10 = 8LL * v34.NumAllocations;
  if ( !is_mul_ok(v34.NumAllocations, 8u) )
    v10 = -1;
  v33 = (void *)operator new[](v10, 1265072196, 256);
  if ( v33 )
  {
    OutputDuplCleanUpPendingList(v6);
    v34.hGlobalShare = 0;
    v34.hDevice = 0;
    v31 = 0;
    v29 = 0;
    if ( (*(_DWORD *)&v34.Flags & 0x10000) != 0 )
    {
      if ( *(int *)(*(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL) + 3132LL) < 2000 )
      {
        WdLogSingleEntry2(2, v6, -1073741811);
        WdLogGlobalForLineNumber = 9299;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Device 0x%I64x: Creating StandardAllocation only supported on WDDM2.0+, returning 0x%I64x",
          (__int64)v6,
          -1073741811,
          0,
          0,
          0);
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v44);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35);
        goto LABEL_72;
      }
      v42 = 0;
      Size = v43.ExistingHeapData.Size;
      v40 = 1;
      v41 = 7;
      StandardAllocationDriverData = DXGDEVICE::GetStandardAllocationDriverData(v6, v11, &Size, &v29, &v31);
      if ( StandardAllocationDriverData < 0 )
      {
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v44);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35);
        ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v28);
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
        if ( v26 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v20, EventProfilerExit, v21, v24);
        return (unsigned int)StandardAllocationDriverData;
      }
    }
    LODWORD(v30) = DXGDEVICE::CreateAllocation(
                     v6,
                     &v34,
                     v23,
                     0,
                     0,
                     0,
                     (struct COREDEVICEACCESS *)v44,
                     0,
                     0,
                     0,
                     0,
                     (unsigned __int64 *)v30,
                     &v43,
                     v31,
                     v29);
    v9 = (int)v30;
    v29 = (unsigned int)v30;
    if ( v27 == 1 )
    {
      RtlWriteULongToUser(&Src->hResource, v34.hResource);
      RtlWriteULongToUser(&Src->hGlobalShare, v34.hGlobalShare);
      RtlWriteULongToUser(&Src->Flags, *(_DWORD *)&v34.Flags);
    }
    else
    {
      Src->hResource = v34.hResource;
      Src->hGlobalShare = v34.hGlobalShare;
      Src->Flags = v34.Flags;
    }
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v33);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v31);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v44);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35);
    v12 = (ADAPTER_RENDER **)v28;
    if ( v28 && _InterlockedExchangeAdd64((volatile signed __int64 *)v28 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v12[2], (struct DXGDEVICE *)v12);
LABEL_27:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
    if ( v26 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v13, EventProfilerExit, v14, v24);
    }
    return (unsigned int)v9;
  }
  WdLogSingleEntry3(6, v6, v34.NumAllocations, -1073741801);
  WdLogGlobalForLineNumber = 9275;
  DxgkLogInternalTriageEvent(
    0,
    262145,
    -1,
    (unsigned int)L"Device 0x%I64x: Out of memory allocating destroy handle table with 0x%I64x elements, returning 0x%I64x",
    (__int64)v6,
    v34.NumAllocations,
    -1073741801,
    0,
    0);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v44);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v36);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v35);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v28);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v24);
  if ( v26 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v18, EventProfilerExit, v19, v24);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14037612c  push    rbx
0x14037612e  push    rsi
0x14037612f  push    rdi
0x140376130  push    r12
0x140376132  push    r13
0x140376134  push    r14
0x140376136  push    r15
0x140376138  sub     rsp, 240h
0x14037613f  mov     rax, cs:__security_cookie
0x140376146  xor     rax, rsp
0x140376149  mov     [rsp+278h+var_48], rax
0x140376151  mov     [rsp+278h+var_1C0], r8
0x140376159  mov     [rsp+278h+var_1B8], rdx
0x140376161  mov     r14, rcx
0x140376164  xor     ebx, ebx
0x140376166  mov     [rdx], ebx
0x140376168  mov     [rsp+278h+var_1F0], 0FFFFFFFFh
0x140376173  mov     [rsp+278h+var_1E8], rbx
0x14037617b  mov     rax, cs:qword_1401604F0
0x140376182  lea     r12d, [rbx+2]
0x140376186  lea     edi, [rbx+1]
0x140376189  test    r12b, al
0x14037618c  jnz     short loc_140376197
0x14037618e  mov     [rsp+278h+var_1E0], bl
0x140376195  jmp     short loc_1403761B7
0x140376197  mov     [rsp+278h+var_1E0], dil
0x14037619f  mov     [rsp+278h+var_1F0], 7D3h
0x1403761aa  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x1403761b1  jnz     loc_140376B92
0x1403761b7  mov     edx, 7D3h
0x1403761bc  lea     rcx, [rsp+278h+var_1F0]
0x1403761c4  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1403761c9  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1403761ce  mov     r13, rax
0x1403761d1  mov     [rsp+278h+var_1A8], rax
0x1403761d9  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x1403761e0  nop     dword ptr [rax+rax+00h]
0x1403761e5  mov     sil, al
0x1403761e8  mov     [rsp+278h+var_1D8], al
0x1403761ef  cmp     al, dil
0x1403761f2  setz    [rsp+278h+var_1F8]
0x1403761fa  test    r13, r13
0x1403761fd  jz      loc_140376BA9
0x140376203  mov     r15d, 48h ; 'H'
0x140376209  mov     r8d, r15d; Size
0x14037620c  xor     edx, edx; Val
0x14037620e  lea     rcx, [rsp+278h+var_198]; void *
0x140376216  call    memset
0x14037621b  xorps   xmm0, xmm0
0x14037621e  xor     eax, eax
0x140376220  movups  xmmword ptr [rsp+278h+var_108.Type], xmm0
0x140376228  mov     qword ptr [rsp+278h+var_108.Flags], rax
0x140376230  cmp     sil, dil
0x140376233  jz      loc_140376C02
0x140376239  movups  xmm0, xmmword ptr [r14]
0x14037623d  movaps  xmmword ptr [rsp+278h+var_198.hDevice], xmm0
0x140376245  movups  xmm1, xmmword ptr [r14+10h]
0x14037624a  movaps  xmmword ptr [rsp+278h+var_198.pPrivateRuntimeData], xmm1
0x140376252  movups  xmm0, xmmword ptr [r14+20h]
0x140376257  movaps  xmmword ptr [rsp+278h+var_198.20h], xmm0
0x14037625f  movups  xmm1, xmmword ptr [r14+30h]
0x140376264  movaps  xmmword ptr [rsp+278h+var_198.30h], xmm1
0x14037626c  movsd   xmm0, qword ptr [r14+40h]
0x140376272  movsd   [rsp+278h+var_198.hPrivateRuntimeResourceHandle], xmm0
0x14037627b  mov     [rsp+278h+var_1B0], rbx
0x140376283  lea     r9, [rsp+278h+var_1B0]; struct DXGDEVICE **
0x14037628b  mov     r8, r13; struct DXGPROCESS *
0x14037628e  mov     edx, [rsp+278h+var_198.hDevice]; unsigned int
0x140376295  lea     rcx, [rsp+278h+var_1D0]; this
0x14037629d  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x1403762a2  mov     rsi, [rsp+278h+var_1B0]
0x1403762aa  test    rsi, rsi
0x1403762ad  jz      loc_140376C7A
0x1403762b3  mov     ecx, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x1403762ba  mov     r15d, 10000h
0x1403762c0  bt      ecx, 14h
0x1403762c4  jb      loc_140376D18
0x1403762ca  cmp     [rsp+278h+var_198.NumAllocations], 682AAh
0x1403762d5  ja      loc_140376D66
0x1403762db  mov     eax, [r13+198h]
0x1403762e2  shr     eax, 8
0x1403762e5  and     al, dil
0x1403762e8  jz      loc_140376648
0x1403762ee  test    cl, 20h
0x1403762f1  jnz     loc_140376D98
0x1403762f7  bt      ecx, 11h
0x1403762fb  jb      loc_140376DD3
0x140376301  test    r15d, ecx
0x140376304  jnz     loc_140376E02
0x14037630a  test    r12b, cl
0x14037630d  jnz     loc_14037668D
0x140376313  cmp     [rsp+278h+var_198.hResource], ebx
0x14037631a  jz      loc_140376587
0x140376320  mov     rdx, rsi; struct DXGDEVICE *
0x140376323  lea     rcx, [rsp+278h+var_148]; this
0x14037632b  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x140376330  mov     rax, [rsi+10h]
0x140376334  mov     rcx, [rax+10h]
0x140376338  mov     [rsp+278h+var_130], rcx
0x140376340  mov     [rsp+278h+var_128], bl
0x140376347  lea     rcx, [rsp+278h+var_138]; this
0x14037634f  call    ?Acquire@DXGADAPTERSTOPRESETLOCKSHARED@@QEAAXXZ; DXGADAPTERSTOPRESETLOCKSHARED::Acquire(void)
0x140376354  mov     byte ptr [rsp+278h+var_258], bl
0x140376358  mov     r8d, r12d
0x14037635b  mov     rdx, rsi
0x14037635e  lea     rcx, [rsp+278h+var_E8]
0x140376366  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x14037636b  xor     edx, edx; char *
0x14037636d  lea     rcx, [rsp+278h+var_E8]; this
0x140376375  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x14037637a  movsxd  r12, eax
0x14037637d  test    eax, eax
0x14037637f  js      loc_140376E38
0x140376385  mov     rcx, [rsi+10h]
0x140376389  mov     rdx, [rcx+10h]
0x14037638d  mov     ecx, [rdx+1A4h]
0x140376393  mov     rax, [rsp+278h+var_1B8]
0x14037639b  mov     [rax], ecx
0x14037639d  mov     ecx, [rsp+278h+var_198.NumAllocations]
0x1403763a4  mov     eax, 8
0x1403763a9  mul     rcx
0x1403763ac  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1403763b3  cmovb   rax, rcx
0x1403763b7  mov     edx, 4B677844h
0x1403763bc  mov     r8d, 100h
0x1403763c2  mov     rcx, rax
0x1403763c5  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1403763ca  mov     [rsp+278h+var_1A0], rax
0x1403763d2  test    rax, rax
0x1403763d5  jz      loc_1403766ED
0x1403763db  mov     rcx, rsi; struct DXGDEVICE *
0x1403763de  call    OutputDuplCleanUpPendingList
0x1403763e3  mov     [rsp+278h+var_198.hGlobalShare], ebx
0x1403763ea  mov     [rsp+278h+var_198.hDevice], ebx
0x1403763f1  mov     [rsp+278h+var_1B8], rbx
0x1403763f9  mov     [rsp+278h+var_1C8], ebx
0x140376400  test    dword ptr [rsp+278h+var_198.Flags.CreateResource], r15d
0x140376408  jnz     loc_140376EAB
0x14037640e  mov     eax, [rsp+278h+var_1C8]
0x140376415  mov     [rsp+278h+var_208], eax; unsigned int
0x140376419  mov     rax, [rsp+278h+var_1B8]
0x140376421  mov     [rsp+278h+var_210], rax; void *
0x140376426  lea     rax, [rsp+278h+var_108]
0x14037642e  mov     [rsp+278h+var_218], rax; struct _D3DKMT_CREATESTANDARDALLOCATION *
0x140376433  mov     rax, [rsp+278h+var_1C0]
0x14037643b  mov     [rsp+278h+var_220], rax; unsigned __int64 *
0x140376440  mov     [rsp+278h+var_228], rbx; unsigned __int64 *
0x140376445  mov     [rsp+278h+var_230], rbx; unsigned int *
0x14037644a  mov     [rsp+278h+var_238], rbx; struct _EPROCESS *
0x14037644f  mov     [rsp+278h+var_240], ebx; unsigned int
0x140376453  lea     rax, [rsp+278h+var_E8]
0x14037645b  mov     [rsp+278h+var_248], rax; struct COREDEVICEACCESS *
0x140376460  mov     qword ptr [rsp+278h+var_250], rbx; struct _D3DKM_CREATESTANDARDALLOCATION *
0x140376465  mov     [rsp+278h+var_258], rbx; struct _DXGSHAREDALLOCOBJECT *
0x14037646a  xor     r9d, r9d; unsigned __int8
0x14037646d  mov     r8b, [rsp+278h+var_1F8]; unsigned __int8
0x140376475  lea     rdx, [rsp+278h+var_198]; struct _D3DKMT_CREATEALLOCATION *
0x14037647d  mov     rcx, rsi; this
0x140376480  call    ?CreateAllocation@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@EEPEAU_DXGSHAREDALLOCOBJECT@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@IPEAU_EPROCESS@@PEAIPEA_K6PEAU_D3DKMT_CREATESTANDARDALLOCATION@@PEAXI@Z; DXGDEVICE::CreateAllocation(_D3DKMT_CREATEALLOCATION *,uchar,uchar,_DXGSHAREDALLOCOBJECT *,_D3DKM_CREATESTANDARDALLOCATION const *,COREDEVICEACCESS *,uint,_EPROCESS *,uint *,unsigned __int64 *,unsigned __int64 *,_D3DKMT_CREATESTANDARDALLOCATION *,void *,uint)
0x140376485  mov     r15d, eax
0x140376488  mov     dword ptr [rsp+278h+var_1C0], eax
0x14037648f  mov     r12d, eax
0x140376492  mov     [rsp+278h+var_1C8], eax
0x140376499  cmp     [rsp+278h+var_1D8], dil
0x1403764a1  jz      loc_1403765BE
0x1403764a7  mov     eax, [rsp+278h+var_198.hResource]
0x1403764ae  mov     [r14+4], eax
0x1403764b2  mov     eax, [rsp+278h+var_198.hGlobalShare]
0x1403764b9  mov     [r14+8], eax
0x1403764bd  mov     eax, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x1403764c4  mov     [r14+38h], eax
0x1403764c8  test    r12d, r12d
0x1403764cb  js      loc_140376FEA
0x1403764d1  mov     rcx, [rsp+278h+var_1A0]; void *
0x1403764d9  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403764de  mov     rcx, [rsp+278h+var_1B8]; void *
0x1403764e6  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403764eb  lea     rcx, [rsp+278h+var_E8]; this
0x1403764f3  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403764f8  lea     rcx, [rsp+278h+var_138]; this
0x140376500  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x140376505  lea     rcx, [rsp+278h+var_148]; this
0x14037650d  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x140376512  mov     rcx, [rsp+278h+var_1D0]
0x14037651a  test    rcx, rcx
0x14037651d  jz      short loc_14037653D
0x14037651f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140376523  mov     rax, rdx
0x140376526  lock xadd [rcx+40h], rax
0x14037652c  add     rax, rdx
0x14037652f  jnz     short loc_14037653D
0x140376531  mov     rdx, rcx; struct DXGDEVICE *
0x140376534  mov     rcx, [rcx+10h]; this
0x140376538  call    ?DestroyDeviceNoLocks@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@@Z; ADAPTER_RENDER::DestroyDeviceNoLocks(DXGDEVICE *)
0x14037653d  lea     rcx, [rsp+278h+var_1F0]; this
0x140376545  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14037654a  cmp     [rsp+278h+var_1E0], bl
0x140376551  jz      short loc_140376560
0x140376553  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x14037655a  jnz     loc_140377060
0x140376560  mov     eax, r12d
0x140376563  mov     rcx, [rsp+278h+var_48]
0x14037656b  xor     rcx, rsp; StackCookie
0x14037656e  call    __security_check_cookie
0x140376573  add     rsp, 240h
0x14037657a  pop     r15
0x14037657c  pop     r14
0x14037657e  pop     r13
0x140376580  pop     r12
0x140376582  pop     rdi
0x140376583  pop     rsi
0x140376584  pop     rbx
0x140376585  retn
0x140376587  cmp     [rsp+278h+var_198.NumAllocations], ebx
0x14037658e  jnz     loc_140376320
0x140376594  mov     r8, 0FFFFFFFFC000000Dh
0x14037659b  mov     rdx, rsi
0x14037659e  mov     ecx, 3
0x1403765a3  call    cs:__imp_WdLogSingleEntry2
0x1403765aa  nop     dword ptr [rax+rax+00h]
0x1403765af  mov     cs:WdLogGlobalForLineNumber, 2419h
0x1403765b9  jmp     loc_140376F43
0x1403765be  lea     rcx, [r14+4]
0x1403765c2  mov     edx, [rsp+278h+var_198.hResource]
0x1403765c9  call    RtlWriteULongToUser
0x1403765ce  lea     rcx, [r14+8]
0x1403765d2  mov     edx, [rsp+278h+var_198.hGlobalShare]
0x1403765d9  call    RtlWriteULongToUser
0x1403765de  lea     rcx, [r14+38h]
0x1403765e2  mov     edx, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x1403765e9  call    RtlWriteULongToUser
0x1403765ee  jmp     loc_1403764C8
0x1403765f3  mov     r8, 0FFFFFFFFC000000Dh
0x1403765fa  mov     rsi, [rsp+278h+var_1B0]
0x140376602  mov     rdx, rsi
0x140376605  mov     ecx, 3
0x14037660a  call    cs:__imp_WdLogSingleEntry2
0x140376611  nop     dword ptr [rax+rax+00h]
0x140376616  mov     cs:WdLogGlobalForLineNumber, 249Ah
0x140376620  mov     r12d, 0C000000Dh
0x140376626  mov     [rsp+278h+var_1C8], r12d
0x14037662e  xor     ebx, ebx
0x140376630  lea     edi, [rbx+1]
0x140376633  mov     r13, [rsp+278h+var_1A8]
0x14037663b  mov     r15d, dword ptr [rsp+278h+var_1C0]
0x140376643  jmp     loc_1403764C8
0x140376648  test    cl, 8
0x14037664b  jnz     short loc_140376663
0x14037664d  bt      ecx, 8
0x140376651  jb      short loc_140376663
0x140376653  bt      ecx, 0Ch
0x140376657  jb      short loc_140376663
0x140376659  bt      ecx, 9
0x14037665d  jnb     loc_1403762EE
0x140376663  mov     r8, 0FFFFFFFFC000000Dh
0x14037666a  mov     rdx, rsi
0x14037666d  mov     ecx, 3
0x140376672  call    cs:__imp_WdLogSingleEntry2
0x140376679  nop     dword ptr [rax+rax+00h]
0x14037667e  mov     cs:WdLogGlobalForLineNumber, 23DEh
0x140376688  jmp     loc_140376F43
0x14037668d  test    dil, cl
0x140376690  jnz     loc_140376313
0x140376696  mov     r8, 0FFFFFFFFC000000Dh
0x14037669d  mov     rdx, rsi
0x1403766a0  mov     ecx, 3
0x1403766a5  call    cs:__imp_WdLogSingleEntry2
0x1403766ac  nop     dword ptr [rax+rax+00h]
0x1403766b1  mov     cs:WdLogGlobalForLineNumber, 240Eh
0x1403766bb  jmp     loc_140376F43
0x1403766c0  lea     rcx, [rsp+278h+var_1F0]; this
0x1403766c8  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403766cd  cmp     [rsp+278h+var_1E0], bl
0x1403766d4  jz      short loc_1403766E3
0x1403766d6  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x1403766dd  jnz     loc_140376F55
0x1403766e3  mov     eax, 0C000000Dh
0x1403766e8  jmp     loc_140376563
0x1403766ed  mov     r8d, [rsp+278h+var_198.NumAllocations]
0x1403766f5  mov     r14, 0FFFFFFFFC0000017h
0x1403766fc  mov     r9, r14
0x1403766ff  mov     rdx, rsi
0x140376702  mov     ecx, 6
0x140376707  call    cs:__imp_WdLogSingleEntry3
0x14037670e  nop     dword ptr [rax+rax+00h]
0x140376713  mov     cs:WdLogGlobalForLineNumber, 243Bh
0x14037671d  mov     eax, [rsp+278h+var_198.NumAllocations]
0x140376724  mov     [rsp+278h+var_238], rbx
0x140376729  mov     qword ptr [rsp+278h+var_240], rbx
0x14037672e  mov     [rsp+278h+var_248], r14
0x140376733  mov     qword ptr [rsp+278h+var_250], rax
0x140376738  mov     [rsp+278h+var_258], rsi
0x14037673d  lea     r9, aDevice0xI64xOu; "Device 0x%I64x: Out of memory allocatin"...
0x140376744  or      r8d, 0FFFFFFFFh
0x140376748  mov     edx, 40001h
0x14037674d  xor     ecx, ecx
0x14037674f  call    DxgkLogInternalTriageEvent
0x140376754  lea     rcx, [rsp+278h+var_E8]; this
0x14037675c  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x140376761  lea     rcx, [rsp+278h+var_138]; this
  ... truncated ...
```
