# DxgkCreateAllocationInternal(_D3DKMT_CREATEALLOCATION *,uint *,unsigned __int64 *)

- ea: `0x1403760ec`
- end: `0x140377039`
- name: `?DxgkCreateAllocationInternal@@YAJPEAU_D3DKMT_CREATEALLOCATION@@PEAIPEA_K@Z`
- size: `3917`
- prototype: `__int64 __fastcall(struct _D3DKMT_CREATEALLOCATION *Src, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1403760a0`
- `0x1403f80d0`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012b14`
- `0x140013860`
- `0x1400158b0`
- `0x140015970`
- `0x140016830`
- `0x140017fb8`
- `0x14001a7d4`
- `0x14001ab20`
- `0x14001b890`
- `0x14001c660`
- `0x14001cec0`
- `0x14001d0e4`
- `0x14001f120`
- `0x14002ed70`
- `0x140030820`
- `0x1400670a4`
- `0x1400a0100`
- `0x1400a0540`
- `0x1401e54cc`
- `0x14020d710`
- `0x14020df2c`
- `0x14031de8c`
- `0x140323854`
- `0x140323d38`
- `0x140374d58`
- `0x1403760ec`
- `0x140377040`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140376199`
- `ntoskrnl!PsGetCurrentThreadPreviousMode` at `0x140376199`
- `watchdog!WdLogSingleEntry2` at `0x140376563`
- `watchdog!WdLogSingleEntry2` at `0x1403765ca`
- `watchdog!WdLogSingleEntry2` at `0x140376632`
- `watchdog!WdLogSingleEntry2` at `0x140376665`
- `watchdog!WdLogSingleEntry2` at `0x140376c4b`
- `watchdog!WdLogSingleEntry2` at `0x140376d78`
- `watchdog!WdLogSingleEntry2` at `0x140376da7`
- `watchdog!WdLogSingleEntry2` at `0x140376e03`
- `watchdog!WdLogSingleEntry2` at `0x140376e92`
- `watchdog!WdLogSingleEntry2` at `0x140376563`
- `watchdog!WdLogSingleEntry2` at `0x1403765ca`
- `watchdog!WdLogSingleEntry2` at `0x140376632`
- `watchdog!WdLogSingleEntry2` at `0x140376665`
- `watchdog!WdLogSingleEntry2` at `0x140376c4b`
- `watchdog!WdLogSingleEntry2` at `0x140376d78`
- `watchdog!WdLogSingleEntry2` at `0x140376da7`
- `watchdog!WdLogSingleEntry2` at `0x140376e03`
- `watchdog!WdLogSingleEntry2` at `0x140376e92`
- `watchdog!WdLogSingleEntry3` at `0x1403766c7`
- `watchdog!WdLogSingleEntry3` at `0x140376d3d`
- `watchdog!WdLogSingleEntry3` at `0x1403766c7`
- `watchdog!WdLogSingleEntry3` at `0x140376d3d`
- `watchdog!WdLogSingleEntry0` at `0x1403767f3`
- `watchdog!WdLogSingleEntry0` at `0x140376950`
- `watchdog!WdLogSingleEntry0` at `0x1403769a5`
- `watchdog!WdLogSingleEntry0` at `0x140376c8c`
- `watchdog!WdLogSingleEntry0` at `0x140376ce0`
- `watchdog!WdLogSingleEntry0` at `0x1403767f3`
- `watchdog!WdLogSingleEntry0` at `0x140376950`
- `watchdog!WdLogSingleEntry0` at `0x1403769a5`
- `watchdog!WdLogSingleEntry0` at `0x140376c8c`
- `watchdog!WdLogSingleEntry0` at `0x140376ce0`
- `watchdog!WdLogSingleEntry1` at `0x140376b73`
- `watchdog!WdLogSingleEntry1` at `0x140376be6`
- `watchdog!WdLogSingleEntry1` at `0x140376b73`
- `watchdog!WdLogSingleEntry1` at `0x140376be6`

## string_xrefs

- `0x140376d0b`: `NoKmdAccess cannot be used with StandardAllocation`
- `0x140376cb7`: `NoKmdAccess can be used only with testsigning`

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
  int v8; // r12d
  __int64 v9; // rax
  enum _D3DKMDT_STANDARDALLOCATION_TYPE v10; // edx
  ADAPTER_RENDER **v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r8
  int StandardAllocationDriverData; // r15d
  bool v22; // [rsp+80h] [rbp-1F8h]
  unsigned int v23; // [rsp+88h] [rbp-1F0h] BYREF
  __int64 v24; // [rsp+90h] [rbp-1E8h]
  char v25; // [rsp+98h] [rbp-1E0h]
  char v26; // [rsp+A0h] [rbp-1D8h]
  struct DXGDEVICE *v27; // [rsp+A8h] [rbp-1D0h] BYREF
  unsigned int v28; // [rsp+B0h] [rbp-1C8h] BYREF
  struct DXGRESOURCE *v29; // [rsp+B8h] [rbp-1C0h]
  void *v30; // [rsp+C0h] [rbp-1B8h] BYREF
  struct DXGDEVICE *v31[2]; // [rsp+C8h] [rbp-1B0h] BYREF
  void *v32; // [rsp+D8h] [rbp-1A0h]
  _D3DKMT_CREATEALLOCATION v33; // [rsp+E0h] [rbp-198h] BYREF
  _BYTE v34[16]; // [rsp+130h] [rbp-148h] BYREF
  _BYTE v35[8]; // [rsp+140h] [rbp-138h] BYREF
  __int64 v36; // [rsp+148h] [rbp-130h]
  char v37; // [rsp+150h] [rbp-128h]
  int Size; // [rsp+158h] [rbp-120h] BYREF
  __int64 v39; // [rsp+15Ch] [rbp-11Ch]
  int v40; // [rsp+164h] [rbp-114h]
  __int64 v41; // [rsp+168h] [rbp-110h]
  struct _D3DKMT_CREATESTANDARDALLOCATION v42; // [rsp+170h] [rbp-108h] BYREF
  _BYTE v43[160]; // [rsp+190h] [rbp-E8h] BYREF

  v29 = a3;
  v30 = a2;
  *a2 = 0;
  v23 = -1;
  v24 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v25 = 1;
    v23 = 2003;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2003);
  }
  else
  {
    v25 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v23, 2003);
  Current = DXGPROCESS::GetCurrent();
  v31[1] = Current;
  CurrentThreadPreviousMode = PsGetCurrentThreadPreviousMode();
  v26 = CurrentThreadPreviousMode;
  v22 = CurrentThreadPreviousMode == 1;
  if ( !Current )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 9073;
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
  memset(&v33, 0, sizeof(v33));
  memset(&v42, 0, sizeof(v42));
  if ( CurrentThreadPreviousMode == 1 )
    RtlCopyFromUser(&v33, Src, 0x48u);
  else
    v33 = *Src;
  v31[0] = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v27, v33.hDevice, Current, v31);
  v6 = v31[0];
  if ( !v31[0] )
  {
    WdLogSingleEntry2(2, v33.hDevice);
    WdLogGlobalForLineNumber = 9115;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      v33.hDevice,
      -1073741811,
      0,
      0,
      0);
    goto LABEL_72;
  }
  Flags = (char)v33.Flags;
  if ( (*(_DWORD *)&v33.Flags & 0x100000) != 0 )
  {
    if ( (*(_DWORD *)&v33.Flags & 0x10000) != 0 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 9124;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NoKmdAccess cannot be used with StandardAllocation",
        9124,
        0,
        0,
        0,
        0);
      goto LABEL_72;
    }
    if ( !g_OSTestSigningEnabled )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 9129;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"NoKmdAccess can be used only with testsigning",
        9129,
        0,
        0,
        0,
        0);
      goto LABEL_72;
    }
  }
  if ( v33.NumAllocations > 0x682AA )
  {
    WdLogSingleEntry3(3, v31[0], v33.NumAllocations, -1073741811);
    WdLogGlobalForLineNumber = 9142;
    goto LABEL_72;
  }
  if ( (*((_DWORD *)Current + 102) & 0x100) == 0
    && ((*(_BYTE *)&v33.Flags & 8) != 0
     || (*(_WORD *)&v33.Flags & 0x100) != 0
     || (*(_WORD *)&v33.Flags & 0x1000) != 0
     || (*(_WORD *)&v33.Flags & 0x200) != 0) )
  {
    WdLogSingleEntry2(3, v31[0]);
    WdLogGlobalForLineNumber = 9156;
    goto LABEL_72;
  }
  if ( (*(_BYTE *)&v33.Flags & 0x20) != 0
    && (*(_DWORD *)&v33.Flags & 0x10000) == 0
    && (*((_DWORD *)Current + 102) & 0x100) == 0 )
  {
    WdLogSingleEntry2(3, v31[0]);
    WdLogGlobalForLineNumber = 9170;
    goto LABEL_72;
  }
  if ( (*(_DWORD *)&v33.Flags & 0x20000) != 0 )
  {
    if ( (*(_DWORD *)&v33.Flags & 0x10000) == 0 )
    {
      WdLogSingleEntry2(3, v31[0]);
      WdLogGlobalForLineNumber = 9182;
      goto LABEL_72;
    }
  }
  else if ( (*(_DWORD *)&v33.Flags & 0x10000) == 0 )
  {
    goto LABEL_15;
  }
  v8 = ValidateStandardAllocationParams(&v33, &v42, v22);
  if ( v8 < 0 )
  {
LABEL_69:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v27);
    goto LABEL_27;
  }
  Flags = (char)v33.Flags;
LABEL_15:
  if ( (Flags & 2) != 0 && (Flags & 1) == 0 )
  {
    WdLogSingleEntry2(3, v6);
    WdLogGlobalForLineNumber = 9204;
    goto LABEL_72;
  }
  if ( !v33.hResource && !v33.NumAllocations )
  {
    WdLogSingleEntry2(3, v6);
    WdLogGlobalForLineNumber = 9215;
LABEL_72:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v27);
LABEL_41:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v23);
    if ( v25 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v15, EventProfilerExit, v16, v23);
    return 3221225485LL;
  }
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(
    (DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34,
    v6);
  v36 = *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL);
  v37 = 0;
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
  COREDEVICEACCESS::COREDEVICEACCESS(v43, v6, 2);
  v8 = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v43, 0);
  if ( v8 < 0 )
  {
    WdLogSingleEntry2(3, v6);
    WdLogGlobalForLineNumber = 9234;
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v43);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34);
    goto LABEL_69;
  }
  *(_DWORD *)v30 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL) + 420LL);
  v9 = 8LL * v33.NumAllocations;
  if ( !is_mul_ok(v33.NumAllocations, 8u) )
    v9 = -1;
  v32 = (void *)operator new[](v9, 1265072196, 256);
  if ( v32 )
  {
    OutputDuplCleanUpPendingList(v6);
    v33.hGlobalShare = 0;
    v33.hDevice = 0;
    v30 = 0;
    v28 = 0;
    if ( (*(_DWORD *)&v33.Flags & 0x10000) != 0 )
    {
      if ( *(int *)(*(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL) + 3116LL) < 2000 )
      {
        WdLogSingleEntry2(2, v6);
        WdLogGlobalForLineNumber = 9273;
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
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v43);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34);
        goto LABEL_72;
      }
      v41 = 0;
      Size = v42.ExistingHeapData.Size;
      v39 = 1;
      v40 = 7;
      StandardAllocationDriverData = DXGDEVICE::GetStandardAllocationDriverData(v6, v10, &Size, &v28, &v30);
      if ( StandardAllocationDriverData < 0 )
      {
        COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v43);
        DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
        DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34);
        ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v27);
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v23);
        if ( v25 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v19, EventProfilerExit, v20, v23);
        return (unsigned int)StandardAllocationDriverData;
      }
    }
    LODWORD(v29) = DXGDEVICE::CreateAllocation(
                     v6,
                     &v33,
                     v22,
                     0,
                     0,
                     0,
                     (struct COREDEVICEACCESS *)v43,
                     0,
                     0,
                     0,
                     0,
                     (unsigned __int64 *)v29,
                     &v42,
                     v30,
                     v28);
    v8 = (int)v29;
    v28 = (unsigned int)v29;
    if ( v26 == 1 )
    {
      RtlWriteULongToUser(&Src->hResource, v33.hResource);
      RtlWriteULongToUser(&Src->hGlobalShare, v33.hGlobalShare);
      RtlWriteULongToUser(&Src->Flags, *(_DWORD *)&v33.Flags);
    }
    else
    {
      Src->hResource = v33.hResource;
      Src->hGlobalShare = v33.hGlobalShare;
      Src->Flags = v33.Flags;
    }
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v32);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v30);
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v43);
    DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
    DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34);
    v11 = (ADAPTER_RENDER **)v27;
    if ( v27 && _InterlockedExchangeAdd64((volatile signed __int64 *)v27 + 8, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
      ADAPTER_RENDER::DestroyDeviceNoLocks(v11[2], (struct DXGDEVICE *)v11);
LABEL_27:
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v23);
    if ( v25 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v12, EventProfilerExit, v13, v23);
    }
    return (unsigned int)v8;
  }
  WdLogSingleEntry3(6, v6, v33.NumAllocations, -1073741801);
  WdLogGlobalForLineNumber = 9249;
  DxgkLogInternalTriageEvent(
    0,
    262145,
    -1,
    (unsigned int)L"Device 0x%I64x: Out of memory allocating destroy handle table with 0x%I64x elements, returning 0x%I64x",
    (__int64)v6,
    v33.NumAllocations,
    -1073741801,
    0,
    0);
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v43);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v35);
  DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL((DXGDEVICELOCKONAPPROPRIATETHREADMODEL *)v34);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v27);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v23);
  if ( v25 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v17, EventProfilerExit, v18, v23);
  return 3221225495LL;
}

```

## disassembly

```asm
0x1403760ec  push    rbx
0x1403760ee  push    rsi
0x1403760ef  push    rdi
0x1403760f0  push    r12
0x1403760f2  push    r13
0x1403760f4  push    r14
0x1403760f6  push    r15
0x1403760f8  sub     rsp, 240h
0x1403760ff  mov     rax, cs:__security_cookie
0x140376106  xor     rax, rsp
0x140376109  mov     [rsp+278h+var_48], rax
0x140376111  mov     [rsp+278h+var_1C0], r8
0x140376119  mov     [rsp+278h+var_1B8], rdx
0x140376121  mov     r14, rcx
0x140376124  xor     ebx, ebx
0x140376126  mov     [rdx], ebx
0x140376128  mov     [rsp+278h+var_1F0], 0FFFFFFFFh
0x140376133  mov     [rsp+278h+var_1E8], rbx
0x14037613b  mov     rax, cs:qword_14015C500
0x140376142  lea     r12d, [rbx+2]
0x140376146  lea     edi, [rbx+1]
0x140376149  test    r12b, al
0x14037614c  jnz     short loc_140376157
0x14037614e  mov     [rsp+278h+var_1E0], bl
0x140376155  jmp     short loc_140376177
0x140376157  mov     [rsp+278h+var_1E0], dil
0x14037615f  mov     [rsp+278h+var_1F0], 7D3h
0x14037616a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x140376171  jnz     loc_140376B52
0x140376177  mov     edx, 7D3h
0x14037617c  lea     rcx, [rsp+278h+var_1F0]
0x140376184  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x140376189  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14037618e  mov     r13, rax
0x140376191  mov     [rsp+278h+var_1A8], rax
0x140376199  call    cs:__imp_PsGetCurrentThreadPreviousMode
0x1403761a0  nop     dword ptr [rax+rax+00h]
0x1403761a5  mov     sil, al
0x1403761a8  mov     [rsp+278h+var_1D8], al
0x1403761af  cmp     al, dil
0x1403761b2  setz    [rsp+278h+var_1F8]
0x1403761ba  test    r13, r13
0x1403761bd  jz      loc_140376B69
0x1403761c3  mov     r15d, 48h ; 'H'
0x1403761c9  mov     r8d, r15d; Size
0x1403761cc  xor     edx, edx; Val
0x1403761ce  lea     rcx, [rsp+278h+var_198]; void *
0x1403761d6  call    memset
0x1403761db  xorps   xmm0, xmm0
0x1403761de  xor     eax, eax
0x1403761e0  movups  xmmword ptr [rsp+278h+var_108.Type], xmm0
0x1403761e8  mov     qword ptr [rsp+278h+var_108.Flags], rax
0x1403761f0  cmp     sil, dil
0x1403761f3  jz      loc_140376BC2
0x1403761f9  movups  xmm0, xmmword ptr [r14]
0x1403761fd  movaps  xmmword ptr [rsp+278h+var_198.hDevice], xmm0
0x140376205  movups  xmm1, xmmword ptr [r14+10h]
0x14037620a  movaps  xmmword ptr [rsp+278h+var_198.pPrivateRuntimeData], xmm1
0x140376212  movups  xmm0, xmmword ptr [r14+20h]
0x140376217  movaps  xmmword ptr [rsp+278h+var_198.20h], xmm0
0x14037621f  movups  xmm1, xmmword ptr [r14+30h]
0x140376224  movaps  xmmword ptr [rsp+278h+var_198.30h], xmm1
0x14037622c  movsd   xmm0, qword ptr [r14+40h]
0x140376232  movsd   [rsp+278h+var_198.hPrivateRuntimeResourceHandle], xmm0
0x14037623b  mov     [rsp+278h+var_1B0], rbx
0x140376243  lea     r9, [rsp+278h+var_1B0]; struct DXGDEVICE **
0x14037624b  mov     r8, r13; struct DXGPROCESS *
0x14037624e  mov     edx, [rsp+278h+var_198.hDevice]; unsigned int
0x140376255  lea     rcx, [rsp+278h+var_1D0]; this
0x14037625d  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x140376262  mov     rsi, [rsp+278h+var_1B0]
0x14037626a  test    rsi, rsi
0x14037626d  jz      loc_140376C3A
0x140376273  mov     ecx, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x14037627a  mov     r15d, 10000h
0x140376280  bt      ecx, 14h
0x140376284  jb      loc_140376CD8
0x14037628a  cmp     [rsp+278h+var_198.NumAllocations], 682AAh
0x140376295  ja      loc_140376D26
0x14037629b  mov     eax, [r13+198h]
0x1403762a2  shr     eax, 8
0x1403762a5  and     al, dil
0x1403762a8  jz      loc_140376608
0x1403762ae  test    cl, 20h
0x1403762b1  jnz     loc_140376D58
0x1403762b7  bt      ecx, 11h
0x1403762bb  jb      loc_140376D93
0x1403762c1  test    r15d, ecx
0x1403762c4  jnz     loc_140376DC2
0x1403762ca  test    r12b, cl
0x1403762cd  jnz     loc_14037664D
0x1403762d3  cmp     [rsp+278h+var_198.hResource], ebx
0x1403762da  jz      loc_140376547
0x1403762e0  mov     rdx, rsi; struct DXGDEVICE *
0x1403762e3  lea     rcx, [rsp+278h+var_148]; this
0x1403762eb  call    ??0DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::DXGDEVICELOCKONAPPROPRIATETHREADMODEL(DXGDEVICE *)
0x1403762f0  mov     rax, [rsi+10h]
0x1403762f4  mov     rcx, [rax+10h]
0x1403762f8  mov     [rsp+278h+var_130], rcx
0x140376300  mov     [rsp+278h+var_128], bl
0x140376307  lea     rcx, [rsp+278h+var_138]; this
0x14037630f  call    ?Acquire@DXGADAPTERSTOPRESETLOCKSHARED@@QEAAXXZ; DXGADAPTERSTOPRESETLOCKSHARED::Acquire(void)
0x140376314  mov     byte ptr [rsp+278h+var_258], bl
0x140376318  mov     r8d, r12d
0x14037631b  mov     rdx, rsi
0x14037631e  lea     rcx, [rsp+278h+var_E8]
0x140376326  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x14037632b  xor     edx, edx; char *
0x14037632d  lea     rcx, [rsp+278h+var_E8]; this
0x140376335  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x14037633a  movsxd  r12, eax
0x14037633d  test    eax, eax
0x14037633f  js      loc_140376DF8
0x140376345  mov     rcx, [rsi+10h]
0x140376349  mov     rdx, [rcx+10h]
0x14037634d  mov     ecx, [rdx+1A4h]
0x140376353  mov     rax, [rsp+278h+var_1B8]
0x14037635b  mov     [rax], ecx
0x14037635d  mov     ecx, [rsp+278h+var_198.NumAllocations]
0x140376364  mov     eax, 8
0x140376369  mul     rcx
0x14037636c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140376373  cmovb   rax, rcx
0x140376377  mov     edx, 4B677844h
0x14037637c  mov     r8d, 100h
0x140376382  mov     rcx, rax
0x140376385  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14037638a  mov     [rsp+278h+var_1A0], rax
0x140376392  test    rax, rax
0x140376395  jz      loc_1403766AD
0x14037639b  mov     rcx, rsi; struct DXGDEVICE *
0x14037639e  call    OutputDuplCleanUpPendingList
0x1403763a3  mov     [rsp+278h+var_198.hGlobalShare], ebx
0x1403763aa  mov     [rsp+278h+var_198.hDevice], ebx
0x1403763b1  mov     [rsp+278h+var_1B8], rbx
0x1403763b9  mov     [rsp+278h+var_1C8], ebx
0x1403763c0  test    dword ptr [rsp+278h+var_198.Flags.CreateResource], r15d
0x1403763c8  jnz     loc_140376E6B
0x1403763ce  mov     eax, [rsp+278h+var_1C8]
0x1403763d5  mov     [rsp+278h+var_208], eax; unsigned int
0x1403763d9  mov     rax, [rsp+278h+var_1B8]
0x1403763e1  mov     [rsp+278h+var_210], rax; void *
0x1403763e6  lea     rax, [rsp+278h+var_108]
0x1403763ee  mov     [rsp+278h+var_218], rax; struct _D3DKMT_CREATESTANDARDALLOCATION *
0x1403763f3  mov     rax, [rsp+278h+var_1C0]
0x1403763fb  mov     [rsp+278h+var_220], rax; unsigned __int64 *
0x140376400  mov     [rsp+278h+var_228], rbx; unsigned __int64 *
0x140376405  mov     [rsp+278h+var_230], rbx; unsigned int *
0x14037640a  mov     [rsp+278h+var_238], rbx; struct _EPROCESS *
0x14037640f  mov     [rsp+278h+var_240], ebx; unsigned int
0x140376413  lea     rax, [rsp+278h+var_E8]
0x14037641b  mov     [rsp+278h+var_248], rax; struct COREDEVICEACCESS *
0x140376420  mov     qword ptr [rsp+278h+var_250], rbx; struct _D3DKM_CREATESTANDARDALLOCATION *
0x140376425  mov     [rsp+278h+var_258], rbx; struct _DXGSHAREDALLOCOBJECT *
0x14037642a  xor     r9d, r9d; unsigned __int8
0x14037642d  mov     r8b, [rsp+278h+var_1F8]; unsigned __int8
0x140376435  lea     rdx, [rsp+278h+var_198]; struct _D3DKMT_CREATEALLOCATION *
0x14037643d  mov     rcx, rsi; this
0x140376440  call    ?CreateAllocation@DXGDEVICE@@QEAAJPEAU_D3DKMT_CREATEALLOCATION@@EEPEAU_DXGSHAREDALLOCOBJECT@@PEBU_D3DKM_CREATESTANDARDALLOCATION@@PEAVCOREDEVICEACCESS@@IPEAU_EPROCESS@@PEAIPEA_K6PEAU_D3DKMT_CREATESTANDARDALLOCATION@@PEAXI@Z; DXGDEVICE::CreateAllocation(_D3DKMT_CREATEALLOCATION *,uchar,uchar,_DXGSHAREDALLOCOBJECT *,_D3DKM_CREATESTANDARDALLOCATION const *,COREDEVICEACCESS *,uint,_EPROCESS *,uint *,unsigned __int64 *,unsigned __int64 *,_D3DKMT_CREATESTANDARDALLOCATION *,void *,uint)
0x140376445  mov     r15d, eax
0x140376448  mov     dword ptr [rsp+278h+var_1C0], eax
0x14037644f  mov     r12d, eax
0x140376452  mov     [rsp+278h+var_1C8], eax
0x140376459  cmp     [rsp+278h+var_1D8], dil
0x140376461  jz      loc_14037657E
0x140376467  mov     eax, [rsp+278h+var_198.hResource]
0x14037646e  mov     [r14+4], eax
0x140376472  mov     eax, [rsp+278h+var_198.hGlobalShare]
0x140376479  mov     [r14+8], eax
0x14037647d  mov     eax, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x140376484  mov     [r14+38h], eax
0x140376488  test    r12d, r12d
0x14037648b  js      loc_140376FAA
0x140376491  mov     rcx, [rsp+278h+var_1A0]; void *
0x140376499  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x14037649e  mov     rcx, [rsp+278h+var_1B8]; void *
0x1403764a6  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1403764ab  lea     rcx, [rsp+278h+var_E8]; this
0x1403764b3  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1403764b8  lea     rcx, [rsp+278h+var_138]; this
0x1403764c0  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403764c5  lea     rcx, [rsp+278h+var_148]; this
0x1403764cd  call    ??1DXGDEVICELOCKONAPPROPRIATETHREADMODEL@@QEAA@XZ; DXGDEVICELOCKONAPPROPRIATETHREADMODEL::~DXGDEVICELOCKONAPPROPRIATETHREADMODEL(void)
0x1403764d2  mov     rcx, [rsp+278h+var_1D0]
0x1403764da  test    rcx, rcx
0x1403764dd  jz      short loc_1403764FD
0x1403764df  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1403764e3  mov     rax, rdx
0x1403764e6  lock xadd [rcx+40h], rax
0x1403764ec  add     rax, rdx
0x1403764ef  jnz     short loc_1403764FD
0x1403764f1  mov     rdx, rcx; struct DXGDEVICE *
0x1403764f4  mov     rcx, [rcx+10h]; this
0x1403764f8  call    ?DestroyDeviceNoLocks@ADAPTER_RENDER@@QEAAXPEAVDXGDEVICE@@@Z; ADAPTER_RENDER::DestroyDeviceNoLocks(DXGDEVICE *)
0x1403764fd  lea     rcx, [rsp+278h+var_1F0]; this
0x140376505  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14037650a  cmp     [rsp+278h+var_1E0], bl
0x140376511  jz      short loc_140376520
0x140376513  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x14037651a  jnz     loc_140377020
0x140376520  mov     eax, r12d
0x140376523  mov     rcx, [rsp+278h+var_48]
0x14037652b  xor     rcx, rsp; StackCookie
0x14037652e  call    __security_check_cookie
0x140376533  add     rsp, 240h
0x14037653a  pop     r15
0x14037653c  pop     r14
0x14037653e  pop     r13
0x140376540  pop     r12
0x140376542  pop     rdi
0x140376543  pop     rsi
0x140376544  pop     rbx
0x140376545  retn
0x140376547  cmp     [rsp+278h+var_198.NumAllocations], ebx
0x14037654e  jnz     loc_1403762E0
0x140376554  mov     r8, 0FFFFFFFFC000000Dh
0x14037655b  mov     rdx, rsi
0x14037655e  mov     ecx, 3
0x140376563  call    cs:__imp_WdLogSingleEntry2
0x14037656a  nop     dword ptr [rax+rax+00h]
0x14037656f  mov     cs:WdLogGlobalForLineNumber, 23FFh
0x140376579  jmp     loc_140376F03
0x14037657e  lea     rcx, [r14+4]
0x140376582  mov     edx, [rsp+278h+var_198.hResource]
0x140376589  call    RtlWriteULongToUser
0x14037658e  lea     rcx, [r14+8]
0x140376592  mov     edx, [rsp+278h+var_198.hGlobalShare]
0x140376599  call    RtlWriteULongToUser
0x14037659e  lea     rcx, [r14+38h]
0x1403765a2  mov     edx, dword ptr [rsp+278h+var_198.Flags.CreateResource]
0x1403765a9  call    RtlWriteULongToUser
0x1403765ae  jmp     loc_140376488
0x1403765b3  mov     r8, 0FFFFFFFFC000000Dh
0x1403765ba  mov     rsi, [rsp+278h+var_1B0]
0x1403765c2  mov     rdx, rsi
0x1403765c5  mov     ecx, 3
0x1403765ca  call    cs:__imp_WdLogSingleEntry2
0x1403765d1  nop     dword ptr [rax+rax+00h]
0x1403765d6  mov     cs:WdLogGlobalForLineNumber, 2480h
0x1403765e0  mov     r12d, 0C000000Dh
0x1403765e6  mov     [rsp+278h+var_1C8], r12d
0x1403765ee  xor     ebx, ebx
0x1403765f0  lea     edi, [rbx+1]
0x1403765f3  mov     r13, [rsp+278h+var_1A8]
0x1403765fb  mov     r15d, dword ptr [rsp+278h+var_1C0]
0x140376603  jmp     loc_140376488
0x140376608  test    cl, 8
0x14037660b  jnz     short loc_140376623
0x14037660d  bt      ecx, 8
0x140376611  jb      short loc_140376623
0x140376613  bt      ecx, 0Ch
0x140376617  jb      short loc_140376623
0x140376619  bt      ecx, 9
0x14037661d  jnb     loc_1403762AE
0x140376623  mov     r8, 0FFFFFFFFC000000Dh
0x14037662a  mov     rdx, rsi
0x14037662d  mov     ecx, 3
0x140376632  call    cs:__imp_WdLogSingleEntry2
0x140376639  nop     dword ptr [rax+rax+00h]
0x14037663e  mov     cs:WdLogGlobalForLineNumber, 23C4h
0x140376648  jmp     loc_140376F03
0x14037664d  test    dil, cl
0x140376650  jnz     loc_1403762D3
0x140376656  mov     r8, 0FFFFFFFFC000000Dh
0x14037665d  mov     rdx, rsi
0x140376660  mov     ecx, 3
0x140376665  call    cs:__imp_WdLogSingleEntry2
0x14037666c  nop     dword ptr [rax+rax+00h]
0x140376671  mov     cs:WdLogGlobalForLineNumber, 23F4h
0x14037667b  jmp     loc_140376F03
0x140376680  lea     rcx, [rsp+278h+var_1F0]; this
0x140376688  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x14037668d  cmp     [rsp+278h+var_1E0], bl
0x140376694  jz      short loc_1403766A3
0x140376696  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, dil
0x14037669d  jnz     loc_140376F15
0x1403766a3  mov     eax, 0C000000Dh
0x1403766a8  jmp     loc_140376523
0x1403766ad  mov     r8d, [rsp+278h+var_198.NumAllocations]
0x1403766b5  mov     r14, 0FFFFFFFFC0000017h
0x1403766bc  mov     r9, r14
0x1403766bf  mov     rdx, rsi
0x1403766c2  mov     ecx, 6
0x1403766c7  call    cs:__imp_WdLogSingleEntry3
0x1403766ce  nop     dword ptr [rax+rax+00h]
0x1403766d3  mov     cs:WdLogGlobalForLineNumber, 2421h
0x1403766dd  mov     eax, [rsp+278h+var_198.NumAllocations]
0x1403766e4  mov     [rsp+278h+var_238], rbx
0x1403766e9  mov     qword ptr [rsp+278h+var_240], rbx
0x1403766ee  mov     [rsp+278h+var_248], r14
0x1403766f3  mov     qword ptr [rsp+278h+var_250], rax
0x1403766f8  mov     [rsp+278h+var_258], rsi
0x1403766fd  lea     r9, aDevice0xI64xOu; "Device 0x%I64x: Out of memory allocatin"...
0x140376704  or      r8d, 0FFFFFFFFh
0x140376708  mov     edx, 40001h
0x14037670d  xor     ecx, ecx
0x14037670f  call    DxgkLogInternalTriageEvent
0x140376714  lea     rcx, [rsp+278h+var_E8]; this
0x14037671c  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x140376721  lea     rcx, [rsp+278h+var_138]; this
  ... truncated ...
```
