# DxgkCreateSwapChain

- ea: `0x1401c2980`
- end: `0x1401c32e2`
- name: `DxgkCreateSwapChain`
- size: `2402`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012b14`
- `0x140013860`
- `0x140015970`
- `0x140015d70`
- `0x14001667c`
- `0x140017fb8`
- `0x14001b890`
- `0x14001cec0`
- `0x14001d0e4`
- `0x14001f120`
- `0x14002e110`
- `0x140030820`
- `0x140047b74`
- `0x1400670a4`
- `0x14007b5f8`
- `0x14007b790`
- `0x1400a0100`
- `0x1400a0540`
- `0x1401b85a4`
- `0x1401c2980`
- `0x1401e5360`
- `0x14026602c`
- `0x140266e00`
- `0x1402677d4`
- `0x140323854`
- `0x140323bc0`
- `0x1403a17a4`
- `0x1403a1c8c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1401c314e`
- `ntoskrnl!ObCloseHandle` at `0x1401c314e`
- `ntoskrnl!ObCreateObject` at `0x1401c3011`
- `ntoskrnl!ObCreateObject` at `0x1401c3011`
- `ntoskrnl!ObInsertObject` at `0x1401c30ac`
- `ntoskrnl!ObInsertObject` at `0x1401c30ac`
- `watchdog!WdLogSingleEntry2` at `0x1401c2d02`
- `watchdog!WdLogSingleEntry2` at `0x1401c3171`
- `watchdog!WdLogSingleEntry2` at `0x1401c2d02`
- `watchdog!WdLogSingleEntry2` at `0x1401c3171`
- `watchdog!WdLogSingleEntry0` at `0x1401c2a4b`
- `watchdog!WdLogSingleEntry0` at `0x1401c2a94`
- `watchdog!WdLogSingleEntry0` at `0x1401c2ac1`
- `watchdog!WdLogSingleEntry0` at `0x1401c2b1d`
- `watchdog!WdLogSingleEntry0` at `0x1401c2bf1`
- `watchdog!WdLogSingleEntry0` at `0x1401c2c99`
- `watchdog!WdLogSingleEntry0` at `0x1401c2ded`
- `watchdog!WdLogSingleEntry0` at `0x1401c2a4b`
- `watchdog!WdLogSingleEntry0` at `0x1401c2a94`
- `watchdog!WdLogSingleEntry0` at `0x1401c2ac1`
- `watchdog!WdLogSingleEntry0` at `0x1401c2b1d`
- `watchdog!WdLogSingleEntry0` at `0x1401c2bf1`
- `watchdog!WdLogSingleEntry0` at `0x1401c2c99`
- `watchdog!WdLogSingleEntry0` at `0x1401c2ded`
- `watchdog!WdLogSingleEntry1` at `0x1401c2aec`
- `watchdog!WdLogSingleEntry1` at `0x1401c2f2c`
- `watchdog!WdLogSingleEntry1` at `0x1401c302a`
- `watchdog!WdLogSingleEntry1` at `0x1401c30c5`
- `watchdog!WdLogSingleEntry1` at `0x1401c310d`
- `watchdog!WdLogSingleEntry1` at `0x1401c326e`
- `watchdog!WdLogSingleEntry1` at `0x1401c2aec`
- `watchdog!WdLogSingleEntry1` at `0x1401c2f2c`
- `watchdog!WdLogSingleEntry1` at `0x1401c302a`
- `watchdog!WdLogSingleEntry1` at `0x1401c30c5`
- `watchdog!WdLogSingleEntry1` at `0x1401c310d`
- `watchdog!WdLogSingleEntry1` at `0x1401c326e`

## string_xrefs

- `0x1401c2b2e`: `Cannot create swapchain with zero buffers`
- `0x1401c2aa5`: `In non-sequence mode create cannot have any surfaces, add surface should be used to add them`
- `0x1401c2ad2`: `In non-sequence mode create has to be the producer`
- `0x1401c30db`: `Failed to create Nt handle for swapchain (0x%I64x)`
- `0x1401c3040`: `Failed to create Nt swapchain object (0x%I64x)`

## pseudocode

```c
__int64 __fastcall DxgkCreateSwapChain(char *Src, __int64 a2, __int64 a3)
{
  struct DXGPROCESS *Current; // rbx
  __int64 v5; // rax
  const wchar_t *v6; // r9
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r8
  DXGSWAPCHAIN *v11; // r14
  void *v12; // r15
  __int64 v13; // rax
  unsigned __int64 v14; // kr00_8
  void *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  struct ADAPTER_RENDER **v18; // rbx
  __int64 v19; // rsi
  unsigned int v20; // edx
  int v21; // ecx
  int v22; // r8d
  DXGSWAPCHAIN *v23; // rax
  bool v24; // r9
  int v25; // eax
  unsigned int i; // ebx
  __int64 v27; // r9
  __int64 v28; // rcx
  int v29; // eax
  const wchar_t *v30; // r9
  NTSTATUS inserted; // eax
  NTSTATUS v32; // eax
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // r8
  char v36; // [rsp+50h] [rbp-208h]
  unsigned int v37; // [rsp+58h] [rbp-200h] BYREF
  __int64 v38; // [rsp+60h] [rbp-1F8h]
  char v39; // [rsp+68h] [rbp-1F0h]
  unsigned int v40; // [rsp+70h] [rbp-1E8h] BYREF
  struct DXGDEVICE *v41; // [rsp+78h] [rbp-1E0h] BYREF
  HANDLE Srca; // [rsp+80h] [rbp-1D8h] BYREF
  struct DXGDEVICE *v43[2]; // [rsp+88h] [rbp-1D0h] BYREF
  PVOID Object; // [rsp+98h] [rbp-1C0h] BYREF
  void *v45; // [rsp+A0h] [rbp-1B8h]
  _BYTE v46[64]; // [rsp+B0h] [rbp-1A8h] BYREF
  char *v47; // [rsp+F0h] [rbp-168h]
  _BYTE v48[160]; // [rsp+100h] [rbp-158h] BYREF
  _BYTE v49[128]; // [rsp+1A0h] [rbp-B8h] BYREF

  v47 = Src;
  v37 = -1;
  v38 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v39 = 1;
    v37 = 2108;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2108);
  }
  else
  {
    v39 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v37, 2108);
  Object = 0;
  Srca = 0;
  memset(v46, 0, sizeof(v46));
  Current = DXGPROCESS::GetCurrent();
  if ( !Current )
  {
    WdLogSingleEntry0(2);
    v5 = 426;
    v6 = L"Invalid process context";
LABEL_16:
    WdLogGlobalForLineNumber = v5;
    goto LABEL_17;
  }
  RtlCopyFromUser(v46, Src, 0x40u);
  if ( (v46[32] & 2) != 0 )
  {
    v7 = *(_DWORD *)&v46[20];
    if ( *(_DWORD *)&v46[20] )
    {
      WdLogSingleEntry0(2);
      v5 = 449;
      v6 = L"In non-sequence mode create cannot have any surfaces, add surface should be used to add them";
      goto LABEL_16;
    }
    if ( !*(_DWORD *)v46 )
    {
      WdLogSingleEntry0(2);
      v5 = 456;
      v6 = L"In non-sequence mode create has to be the producer";
      goto LABEL_16;
    }
  }
  else
  {
    v7 = *(_DWORD *)&v46[20];
    if ( *(_DWORD *)&v46[20] > 0x32u )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 465;
      v5 = *(unsigned int *)&v46[20];
      v6 = L"Caller requested 0x%I64x buffers, this is over the maximum";
LABEL_17:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v6, v5, 0, 0, 0, 0);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v37);
      if ( v39 )
      {
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v8, EventProfilerExit, v9, v37);
      }
      return -1073741811;
    }
    if ( !*(_DWORD *)&v46[20] )
    {
      WdLogSingleEntry0(2);
      v5 = 470;
      v6 = L"Cannot create swapchain with zero buffers";
      goto LABEL_16;
    }
  }
  v11 = 0;
  v36 = 0;
  v12 = 0;
  v45 = 0;
  if ( v7 )
  {
    v14 = v7;
    v13 = 8LL * v7;
    if ( !is_mul_ok(v14, 8u) )
      v13 = -1;
    v15 = (void *)operator new[](v13, 1265072196, 256);
    v12 = v15;
    v45 = v15;
    if ( !v15 )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 482;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Out of memory allocating memory for handles array",
        482,
        0,
        0,
        0,
        0);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v37);
      if ( v39 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v16, EventProfilerExit, v17, v37);
      return 3221225495LL;
    }
    RtlCopyFromUser(v15, *(void **)&v46[24], 8LL * *(unsigned int *)&v46[20]);
    *(_QWORD *)&v46[24] = v12;
  }
  v41 = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v40, *(unsigned int *)&v46[4], Current, &v41);
  v18 = (struct ADAPTER_RENDER **)v41;
  if ( !v41 )
  {
    LODWORD(v19) = -1073741811;
    WdLogSingleEntry2(2, *(unsigned int *)&v46[4]);
    WdLogGlobalForLineNumber = 504;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      *(unsigned int *)&v46[4],
      -1073741811,
      0,
      0,
      0);
LABEL_32:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v40);
    goto LABEL_58;
  }
  DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v43, v41);
  COREDEVICEACCESS::COREDEVICEACCESS(v48, v18, 2);
  LODWORD(v19) = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v48, 0);
  if ( (int)v19 < 0 )
  {
LABEL_34:
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v48);
    DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v43);
    goto LABEL_32;
  }
  v23 = (DXGSWAPCHAIN *)operator new(240, 1265072196, 256);
  if ( v23 )
    v11 = DXGSWAPCHAIN::DXGSWAPCHAIN(v23);
  else
    v11 = 0;
  v41 = v11;
  if ( !v11 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 521;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Out of memory allocating DXGSWAPCHAIN class",
      521,
      0,
      0,
      0,
      0);
    LODWORD(v19) = -1073741801;
    goto LABEL_34;
  }
  LODWORD(v19) = DXGSWAPCHAIN::InitializeSwapchainGlobalState(v11, v18[2], (struct _D3DKMT_CREATESWAPCHAIN *)v46);
  if ( (int)v19 < 0 )
    goto LABEL_34;
  LODWORD(v19) = DXGSWAPCHAIN::OpenSwapchainLocal(
                   v11,
                   *(unsigned int *)&v46[4],
                   (struct DXGDEVICE *)v18,
                   *(void **)&v46[40],
                   v46[32] & 1,
                   *(int *)v46,
                   *(int *)&v46[56]);
  if ( (int)v19 < 0 )
    goto LABEL_34;
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v48);
  DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v43);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v40);
  v43[0] = 0;
  DXGSWAPCHAINLOCKWITHDEVICE::DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v49, v11, *(_DWORD *)v46 != 0, 1);
  if ( (unsigned int)Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline() )
    v24 = *((_DWORD *)v11 + 59) != 0;
  else
    v24 = 0;
  v25 = DXGSWAPCHAINLOCKWITHDEVICE::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)v49, v43, 1, v24);
  v19 = v25;
  if ( v25 < 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 571;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to acquire swapchain and device lock (0x%I64x)",
      v19,
      0,
      0,
      0,
      0);
LABEL_47:
    DXGSWAPCHAINLOCKWITHDEVICE::~DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v49);
    goto LABEL_58;
  }
  for ( i = 0; i < *(_DWORD *)&v46[20]; ++i )
  {
    LODWORD(v19) = DXGSWAPCHAIN::AddSurface(v11, v43[0], *(int *)v46, *(void **)(*(_QWORD *)&v46[24] + 8LL * i), &v40);
    if ( (int)v19 < 0 )
      goto LABEL_47;
  }
  DXGSWAPCHAINLOCKWITHDEVICE::~DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v49);
  LOBYTE(v27) = 1;
  LOBYTE(v28) = 1;
  v29 = ObCreateObject(v28, g_pDxgkSharedSwapChainObjectType, *(_QWORD *)&v46[8], v27, 0, 8, 248, 0, &Object);
  v19 = v29;
  if ( v29 >= 0 )
  {
    *(_QWORD *)Object = v11;
    v36 = 1;
    inserted = ObInsertObject(Object, 0, *(ACCESS_MASK *)&v46[16], 0, 0, &Srca);
    v19 = inserted;
    if ( inserted >= 0 )
    {
      RtlCopyToUser(Src + 48, &Srca, 8u);
      goto LABEL_58;
    }
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 619;
    v30 = L"Failed to create Nt handle for swapchain (0x%I64x)";
  }
  else
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 600;
    v30 = L"Failed to create Nt swapchain object (0x%I64x)";
  }
  DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v30, v19, 0, 0, 0, 0);
LABEL_58:
  if ( (int)v19 < 0 )
  {
    v21 = (int)Srca;
    if ( Srca )
    {
      v32 = ObCloseHandle(Srca, 1);
      if ( v32 < 0 )
      {
        v33 = v32;
        WdLogSingleEntry2(1, Srca);
        WdLogGlobalForLineNumber = 644;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"Failed to close swap chain handle 0x%I64x: Status = 0x%I64x",
          (__int64)Srca,
          v33,
          0,
          0,
          0);
      }
    }
    if ( v11 && !v36 )
    {
      DXGSWAPCHAIN::`scalar deleting destructor'(v11, v20);
      LODWORD(v11) = 0;
    }
  }
  if ( v12 )
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v12);
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40000000000LL) != 0 )
    McTemplateK0pqdqqpp_EtwWriteTransfer(v21, v20, v22, (_DWORD)v11, v19, v46[0], v46[4], v46[20], v46[40], (char)Srca);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v37);
  if ( v39 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v34, EventProfilerExit, v35, v37);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1401c2980  mov     [rsp+arg_8], rbx
0x1401c2985  mov     [rsp+arg_10], rsi
0x1401c298a  push    rdi
0x1401c298b  push    r12
0x1401c298d  push    r13
0x1401c298f  push    r14
0x1401c2991  push    r15
0x1401c2993  sub     rsp, 230h
0x1401c299a  mov     rax, cs:__security_cookie
0x1401c29a1  xor     rax, rsp
0x1401c29a4  mov     [rsp+258h+var_38], rax
0x1401c29ac  mov     r13, rcx
0x1401c29af  mov     [rsp+258h+var_168], rcx
0x1401c29b7  mov     [rsp+258h+var_200], 0FFFFFFFFh
0x1401c29bf  xor     edi, edi
0x1401c29c1  mov     [rsp+258h+var_1F8], rdi
0x1401c29c6  mov     rax, cs:qword_14015C500
0x1401c29cd  lea     r12d, [rdi+2]
0x1401c29d1  test    r12b, al
0x1401c29d4  jz      short loc_1401C2A00
0x1401c29d6  mov     [rsp+258h+var_1F0], 1
0x1401c29db  mov     [rsp+258h+var_200], 83Ch
0x1401c29e3  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c29ea  jz      short loc_1401C2A05
0x1401c29ec  mov     r9d, 83Ch
0x1401c29f2  lea     rdx, EventProfilerEnter
0x1401c29f9  call    McTemplateK0q_EtwWriteTransfer
0x1401c29fe  jmp     short loc_1401C2A05
0x1401c2a00  mov     [rsp+258h+var_1F0], dil
0x1401c2a05  mov     edx, 83Ch
0x1401c2a0a  lea     rcx, [rsp+258h+var_200]
0x1401c2a0f  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1401c2a14  mov     [rsp+258h+Object], rdi
0x1401c2a1c  mov     [rsp+258h+Src], rdi
0x1401c2a24  mov     esi, 40h ; '@'
0x1401c2a29  mov     r8d, esi; Size
0x1401c2a2c  xor     edx, edx; Val
0x1401c2a2e  lea     rcx, [rsp+258h+var_1A8]; void *
0x1401c2a36  call    memset
0x1401c2a3b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401c2a40  mov     rbx, rax
0x1401c2a43  test    rax, rax
0x1401c2a46  jnz     short loc_1401C2A68
0x1401c2a48  mov     ecx, r12d
0x1401c2a4b  call    cs:__imp_WdLogSingleEntry0
0x1401c2a52  nop     dword ptr [rax+rax+00h]
0x1401c2a57  mov     eax, 1AAh
0x1401c2a5c  lea     r9, aInvalidProcess_3; "Invalid process context"
0x1401c2a63  jmp     loc_1401C2B35
0x1401c2a68  mov     r8, rsi; Size
0x1401c2a6b  mov     rdx, r13; Src
0x1401c2a6e  lea     rcx, [rsp+258h+var_1A8]; void *
0x1401c2a76  call    RtlCopyFromUser
0x1401c2a7b  nop
0x1401c2a7c  test    byte ptr [rsp+258h+var_1A8.Flags], r12b
0x1401c2a84  jz      short loc_1401C2ADB
0x1401c2a86  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c2a8d  test    eax, eax
0x1401c2a8f  jz      short loc_1401C2AB1
0x1401c2a91  mov     ecx, r12d
0x1401c2a94  call    cs:__imp_WdLogSingleEntry0
0x1401c2a9b  nop     dword ptr [rax+rax+00h]
0x1401c2aa0  mov     eax, 1C1h
0x1401c2aa5  lea     r9, aInNonSequenceM_0; "In non-sequence mode create cannot have"...
0x1401c2aac  jmp     loc_1401C2B35
0x1401c2ab1  cmp     [rsp+258h+var_1A8.bProducer], edi
0x1401c2ab8  jnz     loc_1401C2B9B
0x1401c2abe  mov     ecx, r12d
0x1401c2ac1  call    cs:__imp_WdLogSingleEntry0
0x1401c2ac8  nop     dword ptr [rax+rax+00h]
0x1401c2acd  mov     eax, 1C8h
0x1401c2ad2  lea     r9, aInNonSequenceM; "In non-sequence mode create has to be t"...
0x1401c2ad9  jmp     short loc_1401C2B35
0x1401c2adb  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c2ae2  cmp     eax, 32h ; '2'
0x1401c2ae5  jbe     short loc_1401C2B12
0x1401c2ae7  mov     edx, eax
0x1401c2ae9  mov     ecx, r12d
0x1401c2aec  call    cs:__imp_WdLogSingleEntry1
0x1401c2af3  nop     dword ptr [rax+rax+00h]
0x1401c2af8  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x1401c2b02  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c2b09  lea     r9, aCallerRequeste; "Caller requested 0x%I64x buffers, this "...
0x1401c2b10  jmp     short loc_1401C2B3B
0x1401c2b12  test    eax, eax
0x1401c2b14  jnz     loc_1401C2B9B
0x1401c2b1a  mov     ecx, r12d
0x1401c2b1d  call    cs:__imp_WdLogSingleEntry0
0x1401c2b24  nop     dword ptr [rax+rax+00h]
0x1401c2b29  mov     eax, 1D6h
0x1401c2b2e  lea     r9, aCannotCreateSw; "Cannot create swapchain with zero buffe"...
0x1401c2b35  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c2b3b  mov     [rsp+258h+var_218], rdi
0x1401c2b40  mov     [rsp+258h+var_220], rdi
0x1401c2b45  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c2b4a  mov     [rsp+258h+Handle], rdi
0x1401c2b4f  mov     [rsp+258h+NewObject], rax
0x1401c2b54  or      r8d, 0FFFFFFFFh
0x1401c2b58  mov     edx, 40000h
0x1401c2b5d  xor     ecx, ecx
0x1401c2b5f  call    DxgkLogInternalTriageEvent
0x1401c2b64  lea     rcx, [rsp+258h+var_200]; this
0x1401c2b69  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401c2b6e  cmp     [rsp+258h+var_1F0], dil
0x1401c2b73  jz      short loc_1401C2B8F
0x1401c2b75  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c2b7c  jz      short loc_1401C2B8F
0x1401c2b7e  mov     r9d, [rsp+258h+var_200]
0x1401c2b83  lea     rdx, EventProfilerExit
0x1401c2b8a  call    McTemplateK0q_EtwWriteTransfer
0x1401c2b8f  mov     rax, 0FFFFFFFFC000000Dh
0x1401c2b96  jmp     loc_1401C32B4
0x1401c2b9b  mov     r14, rdi
0x1401c2b9e  mov     [rsp+258h+var_208], dil
0x1401c2ba3  mov     r15, rdi
0x1401c2ba6  mov     [rsp+258h+var_1B8], rdi
0x1401c2bae  test    eax, eax
0x1401c2bb0  jz      loc_1401C2CC6
0x1401c2bb6  mov     ecx, eax
0x1401c2bb8  mov     eax, 8
0x1401c2bbd  mul     rcx
0x1401c2bc0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401c2bc7  cmovb   rax, rcx
0x1401c2bcb  mov     edx, 4B677844h
0x1401c2bd0  mov     r8d, 100h
0x1401c2bd6  mov     rcx, rax
0x1401c2bd9  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c2bde  mov     r15, rax
0x1401c2be1  mov     [rsp+258h+var_1B8], rax
0x1401c2be9  test    rax, rax
0x1401c2bec  jnz     short loc_1401C2C6D
0x1401c2bee  lea     ecx, [rax+6]
0x1401c2bf1  call    cs:__imp_WdLogSingleEntry0
0x1401c2bf8  nop     dword ptr [rax+rax+00h]
0x1401c2bfd  mov     eax, 1E2h
0x1401c2c02  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c2c08  mov     [rsp+258h+var_218], rdi
0x1401c2c0d  mov     [rsp+258h+var_220], rdi
0x1401c2c12  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c2c17  mov     [rsp+258h+Handle], rdi
0x1401c2c1c  mov     [rsp+258h+NewObject], rax
0x1401c2c21  lea     r9, aOutOfMemoryAll_22; "Out of memory allocating memory for han"...
0x1401c2c28  or      r8d, 0FFFFFFFFh
0x1401c2c2c  mov     edx, 40001h
0x1401c2c31  xor     ecx, ecx
0x1401c2c33  call    DxgkLogInternalTriageEvent
0x1401c2c38  lea     rcx, [rsp+258h+var_200]; this
0x1401c2c3d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401c2c42  cmp     [rsp+258h+var_1F0], dil
0x1401c2c47  jz      short loc_1401C2C63
0x1401c2c49  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c2c50  jz      short loc_1401C2C63
0x1401c2c52  mov     r9d, [rsp+258h+var_200]
0x1401c2c57  lea     rdx, EventProfilerExit
0x1401c2c5e  call    McTemplateK0q_EtwWriteTransfer
0x1401c2c63  mov     eax, 0C0000017h
0x1401c2c68  jmp     loc_1401C32B4
0x1401c2c6d  mov     r8d, [rsp+258h+var_1A8.SurfaceCount]
0x1401c2c75  shl     r8, 3; Size
0x1401c2c79  mov     rdx, [rsp+258h+var_1A8.pNtSurfaceHandles]; Src
0x1401c2c81  mov     rcx, r15; void *
0x1401c2c84  call    RtlCopyFromUser
0x1401c2c89  nop
0x1401c2c8a  mov     [rsp+258h+var_1A8.pNtSurfaceHandles], r15
0x1401c2c92  jmp     short loc_1401C2CC6
0x1401c2c94  mov     ecx, 3
0x1401c2c99  call    cs:__imp_WdLogSingleEntry0
0x1401c2ca0  nop     dword ptr [rax+rax+00h]
0x1401c2ca5  mov     cs:WdLogGlobalForLineNumber, 1EBh
0x1401c2caf  mov     esi, 0C000000Dh
0x1401c2cb4  xor     edi, edi
0x1401c2cb6  mov     r14d, edi
0x1401c2cb9  mov     r15, [rsp+258h+var_1B8]
0x1401c2cc1  jmp     loc_1401C3137
0x1401c2cc6  mov     [rsp+258h+var_1E0], rdi
0x1401c2ccb  lea     r9, [rsp+258h+var_1E0]; struct DXGDEVICE **
0x1401c2cd0  mov     r8, rbx; struct DXGPROCESS *
0x1401c2cd3  mov     edx, [rsp+258h+var_1A8.hDevice]; unsigned int
0x1401c2cda  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c2cdf  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x1401c2ce4  mov     rbx, [rsp+258h+var_1E0]
0x1401c2ce9  test    rbx, rbx
0x1401c2cec  jnz     short loc_1401C2D5E
0x1401c2cee  mov     edx, [rsp+258h+var_1A8.hDevice]
0x1401c2cf5  mov     rsi, 0FFFFFFFFC000000Dh
0x1401c2cfc  mov     r8, rsi
0x1401c2cff  mov     ecx, r12d
0x1401c2d02  call    cs:__imp_WdLogSingleEntry2
0x1401c2d09  nop     dword ptr [rax+rax+00h]
0x1401c2d0e  mov     cs:WdLogGlobalForLineNumber, 1F8h
0x1401c2d18  mov     eax, [rsp+258h+var_1A8.hDevice]
0x1401c2d1f  mov     [rsp+258h+var_218], rdi
0x1401c2d24  mov     [rsp+258h+var_220], rdi
0x1401c2d29  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c2d2e  mov     [rsp+258h+Handle], rsi
0x1401c2d33  mov     [rsp+258h+NewObject], rax
0x1401c2d38  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x1401c2d3f  or      r8d, 0FFFFFFFFh
0x1401c2d43  mov     edx, 40000h
0x1401c2d48  xor     ecx, ecx
0x1401c2d4a  call    DxgkLogInternalTriageEvent
0x1401c2d4f  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c2d54  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1401c2d59  jmp     loc_1401C3137
0x1401c2d5e  mov     rdx, rbx; struct DXGDEVICE *
0x1401c2d61  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c2d69  call    ??0DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE(DXGDEVICE *)
0x1401c2d6e  mov     byte ptr [rsp+258h+NewObject], dil
0x1401c2d73  mov     r8d, r12d
0x1401c2d76  mov     rdx, rbx
0x1401c2d79  lea     rcx, [rsp+258h+var_158]
0x1401c2d81  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1401c2d86  xor     edx, edx; char *
0x1401c2d88  lea     rcx, [rsp+258h+var_158]; this
0x1401c2d90  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x1401c2d95  mov     esi, eax
0x1401c2d97  test    eax, eax
0x1401c2d99  jns     short loc_1401C2DB7
0x1401c2d9b  lea     rcx, [rsp+258h+var_158]; this
0x1401c2da3  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1401c2da8  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c2db0  call    ??1DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@XZ; DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE(void)
0x1401c2db5  jmp     short loc_1401C2D4F
0x1401c2db7  mov     edx, 4B677844h
0x1401c2dbc  mov     ecx, 0F0h
0x1401c2dc1  lea     r8d, [rcx+10h]
0x1401c2dc5  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c2dca  test    rax, rax
0x1401c2dcd  jz      short loc_1401C2DDC
0x1401c2dcf  mov     rcx, rax; this
0x1401c2dd2  call    ??0DXGSWAPCHAIN@@QEAA@XZ; DXGSWAPCHAIN::DXGSWAPCHAIN(void)
0x1401c2dd7  mov     r14, rax
0x1401c2dda  jmp     short loc_1401C2DDF
0x1401c2ddc  mov     r14, rdi
0x1401c2ddf  mov     [rsp+258h+var_1E0], r14
0x1401c2de4  test    r14, r14
0x1401c2de7  jnz     short loc_1401C2E3E
0x1401c2de9  lea     ecx, [r14+6]
0x1401c2ded  call    cs:__imp_WdLogSingleEntry0
0x1401c2df4  nop     dword ptr [rax+rax+00h]
0x1401c2df9  mov     eax, 209h
0x1401c2dfe  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c2e04  mov     [rsp+258h+var_218], rdi
0x1401c2e09  mov     [rsp+258h+var_220], rdi
0x1401c2e0e  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c2e13  mov     [rsp+258h+Handle], rdi
0x1401c2e18  mov     [rsp+258h+NewObject], rax
0x1401c2e1d  lea     r9, aOutOfMemoryAll_16; "Out of memory allocating DXGSWAPCHAIN c"...
0x1401c2e24  or      r8d, 0FFFFFFFFh
0x1401c2e28  mov     edx, 40001h
0x1401c2e2d  xor     ecx, ecx
0x1401c2e2f  call    DxgkLogInternalTriageEvent
0x1401c2e34  mov     esi, 0C0000017h
0x1401c2e39  jmp     loc_1401C2D9B
0x1401c2e3e  lea     r8, [rsp+258h+var_1A8]; struct _D3DKMT_CREATESWAPCHAIN *
0x1401c2e46  mov     rdx, [rbx+10h]; struct ADAPTER_RENDER *
0x1401c2e4a  mov     rcx, r14; this
0x1401c2e4d  call    ?InitializeSwapchainGlobalState@DXGSWAPCHAIN@@QEAAJPEAVADAPTER_RENDER@@PEAU_D3DKMT_CREATESWAPCHAIN@@@Z; DXGSWAPCHAIN::InitializeSwapchainGlobalState(ADAPTER_RENDER *,_D3DKMT_CREATESWAPCHAIN *)
0x1401c2e52  mov     esi, eax
0x1401c2e54  test    eax, eax
0x1401c2e56  js      loc_1401C2D9B
0x1401c2e5c  mov     ecx, dword ptr [rsp+258h+var_1A8.Flags]
0x1401c2e63  and     ecx, 1
0x1401c2e66  mov     eax, [rsp+258h+var_170]
0x1401c2e6d  mov     [rsp+258h+var_228], eax; int
0x1401c2e71  mov     eax, [rsp+258h+var_1A8.bProducer]
0x1401c2e78  mov     dword ptr [rsp+258h+Handle], eax; int
0x1401c2e7c  mov     dword ptr [rsp+258h+NewObject], ecx; int
0x1401c2e80  mov     r9, [rsp+258h+var_1A8.BufferAvailableEvent]; void *
0x1401c2e88  mov     r8, rbx; struct DXGDEVICE *
0x1401c2e8b  mov     edx, [rsp+258h+var_1A8.hDevice]; unsigned int
0x1401c2e92  mov     rcx, r14; this
0x1401c2e95  call    ?OpenSwapchainLocal@DXGSWAPCHAIN@@QEAAJIPEAVDXGDEVICE@@PEAXHHH@Z; DXGSWAPCHAIN::OpenSwapchainLocal(uint,DXGDEVICE *,void *,int,int,int)
0x1401c2e9a  mov     esi, eax
0x1401c2e9c  lea     rcx, [rsp+258h+var_158]; this
0x1401c2ea4  test    eax, eax
0x1401c2ea6  js      loc_1401C2DA3
0x1401c2eac  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1401c2eb1  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c2eb9  call    ??1DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@XZ; DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE(void)
0x1401c2ebe  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c2ec3  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1401c2ec8  mov     [rsp+258h+var_1D0], rdi
0x1401c2ed0  cmp     [rsp+258h+var_1A8.bProducer], edi
0x1401c2ed7  setnz   r8b; bool
0x1401c2edb  mov     r9b, 1; char
0x1401c2ede  mov     rdx, r14; struct DXGSWAPCHAIN *
0x1401c2ee1  lea     rcx, [rsp+258h+var_B8]; this
0x1401c2ee9  call    ??0DXGSWAPCHAINLOCKWITHDEVICE@@QEAA@PEAVDXGSWAPCHAIN@@_ND@Z; DXGSWAPCHAINLOCKWITHDEVICE::DXGSWAPCHAINLOCKWITHDEVICE(DXGSWAPCHAIN *,bool,char)
0x1401c2eee  call    Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline
0x1401c2ef3  test    eax, eax
0x1401c2ef5  jnz     short loc_1401C2EFC
0x1401c2ef7  mov     r9b, dil
0x1401c2efa  jmp     short loc_1401C2F07
0x1401c2efc  cmp     [r14+0ECh], edi
0x1401c2f03  setnz   r9b; bool
0x1401c2f07  mov     r8b, 1; bool
0x1401c2f0a  lea     rdx, [rsp+258h+var_1D0]; struct DXGDEVICE **
0x1401c2f12  lea     rcx, [rsp+258h+var_B8]; this
0x1401c2f1a  call    ?Acquire@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAJPEAPEAVDXGDEVICE@@_N1@Z; DXGSWAPCHAINLOCKWITHDEVICE::Acquire(DXGDEVICE * *,bool,bool)
  ... truncated ...
```
