# DxgkCreateSwapChain

- ea: `0x1401c5580`
- end: `0x1401c5ee2`
- name: `DxgkCreateSwapChain`
- size: `2402`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012cd4`
- `0x140013a20`
- `0x140015b30`
- `0x140015f30`
- `0x14001683c`
- `0x140018054`
- `0x14001b9c0`
- `0x14001cff0`
- `0x14001d214`
- `0x14001f2f0`
- `0x14002e2e0`
- `0x1400309f0`
- `0x140047d74`
- `0x1400674c4`
- `0x14007be90`
- `0x14007c028`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x1401bb1a4`
- `0x1401c5580`
- `0x1401e76e0`
- `0x14026b5ec`
- `0x14026c3c0`
- `0x14026cd94`
- `0x14032a5c4`
- `0x14032a930`
- `0x1403a2584`
- `0x1403a2a6c`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x1401c5d4e`
- `ntoskrnl!ObCloseHandle` at `0x1401c5d4e`
- `ntoskrnl!ObCreateObject` at `0x1401c5c11`
- `ntoskrnl!ObCreateObject` at `0x1401c5c11`
- `ntoskrnl!ObInsertObject` at `0x1401c5cac`
- `ntoskrnl!ObInsertObject` at `0x1401c5cac`
- `watchdog!WdLogSingleEntry2` at `0x1401c5902`
- `watchdog!WdLogSingleEntry2` at `0x1401c5d71`
- `watchdog!WdLogSingleEntry2` at `0x1401c5902`
- `watchdog!WdLogSingleEntry2` at `0x1401c5d71`
- `watchdog!WdLogSingleEntry0` at `0x1401c564b`
- `watchdog!WdLogSingleEntry0` at `0x1401c5694`
- `watchdog!WdLogSingleEntry0` at `0x1401c56c1`
- `watchdog!WdLogSingleEntry0` at `0x1401c571d`
- `watchdog!WdLogSingleEntry0` at `0x1401c57f1`
- `watchdog!WdLogSingleEntry0` at `0x1401c5899`
- `watchdog!WdLogSingleEntry0` at `0x1401c59ed`
- `watchdog!WdLogSingleEntry0` at `0x1401c564b`
- `watchdog!WdLogSingleEntry0` at `0x1401c5694`
- `watchdog!WdLogSingleEntry0` at `0x1401c56c1`
- `watchdog!WdLogSingleEntry0` at `0x1401c571d`
- `watchdog!WdLogSingleEntry0` at `0x1401c57f1`
- `watchdog!WdLogSingleEntry0` at `0x1401c5899`
- `watchdog!WdLogSingleEntry0` at `0x1401c59ed`
- `watchdog!WdLogSingleEntry1` at `0x1401c56ec`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b2c`
- `watchdog!WdLogSingleEntry1` at `0x1401c5c2a`
- `watchdog!WdLogSingleEntry1` at `0x1401c5cc5`
- `watchdog!WdLogSingleEntry1` at `0x1401c5d0d`
- `watchdog!WdLogSingleEntry1` at `0x1401c5e6e`
- `watchdog!WdLogSingleEntry1` at `0x1401c56ec`
- `watchdog!WdLogSingleEntry1` at `0x1401c5b2c`
- `watchdog!WdLogSingleEntry1` at `0x1401c5c2a`
- `watchdog!WdLogSingleEntry1` at `0x1401c5cc5`
- `watchdog!WdLogSingleEntry1` at `0x1401c5d0d`
- `watchdog!WdLogSingleEntry1` at `0x1401c5e6e`

## string_xrefs

- `0x1401c572e`: `Cannot create swapchain with zero buffers`
- `0x1401c56a5`: `In non-sequence mode create cannot have any surfaces, add surface should be used to add them`
- `0x1401c56d2`: `In non-sequence mode create has to be the producer`
- `0x1401c5cdb`: `Failed to create Nt handle for swapchain (0x%I64x)`
- `0x1401c5c40`: `Failed to create Nt swapchain object (0x%I64x)`

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
  int v36[2]; // [rsp+30h] [rbp-228h]
  char v37; // [rsp+50h] [rbp-208h]
  unsigned int v38; // [rsp+58h] [rbp-200h] BYREF
  __int64 v39; // [rsp+60h] [rbp-1F8h]
  char v40; // [rsp+68h] [rbp-1F0h]
  unsigned int v41; // [rsp+70h] [rbp-1E8h] BYREF
  struct DXGDEVICE *v42; // [rsp+78h] [rbp-1E0h] BYREF
  HANDLE Srca; // [rsp+80h] [rbp-1D8h] BYREF
  struct DXGDEVICE *v44[2]; // [rsp+88h] [rbp-1D0h] BYREF
  PVOID Object; // [rsp+98h] [rbp-1C0h] BYREF
  void *v46; // [rsp+A0h] [rbp-1B8h]
  _BYTE v47[64]; // [rsp+B0h] [rbp-1A8h] BYREF
  char *v48; // [rsp+F0h] [rbp-168h]
  _BYTE v49[160]; // [rsp+100h] [rbp-158h] BYREF
  _BYTE v50[128]; // [rsp+1A0h] [rbp-B8h] BYREF

  v48 = Src;
  v38 = -1;
  v39 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v40 = 1;
    v38 = 2108;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2108);
  }
  else
  {
    v40 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v38, 2108);
  Object = 0;
  Srca = 0;
  memset(v47, 0, sizeof(v47));
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
  RtlCopyFromUser(v47, Src, 0x40u);
  if ( (v47[32] & 2) != 0 )
  {
    v7 = *(_DWORD *)&v47[20];
    if ( *(_DWORD *)&v47[20] )
    {
      WdLogSingleEntry0(2);
      v5 = 449;
      v6 = L"In non-sequence mode create cannot have any surfaces, add surface should be used to add them";
      goto LABEL_16;
    }
    if ( !*(_DWORD *)v47 )
    {
      WdLogSingleEntry0(2);
      v5 = 456;
      v6 = L"In non-sequence mode create has to be the producer";
      goto LABEL_16;
    }
  }
  else
  {
    v7 = *(_DWORD *)&v47[20];
    if ( *(_DWORD *)&v47[20] > 0x32u )
    {
      WdLogSingleEntry1(2, *(unsigned int *)&v47[20]);
      WdLogGlobalForLineNumber = 465;
      v5 = *(unsigned int *)&v47[20];
      v6 = L"Caller requested 0x%I64x buffers, this is over the maximum";
LABEL_17:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v6, v5, 0, 0, 0, 0);
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
      if ( v40 )
      {
        if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v8, EventProfilerExit, v9, v38);
      }
      return -1073741811;
    }
    if ( !*(_DWORD *)&v47[20] )
    {
      WdLogSingleEntry0(2);
      v5 = 470;
      v6 = L"Cannot create swapchain with zero buffers";
      goto LABEL_16;
    }
  }
  v11 = 0;
  v37 = 0;
  v12 = 0;
  v46 = 0;
  if ( v7 )
  {
    v14 = v7;
    v13 = 8LL * v7;
    if ( !is_mul_ok(v14, 8u) )
      v13 = -1;
    v15 = (void *)operator new[](v13, 1265072196, 256);
    v12 = v15;
    v46 = v15;
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
      DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
      if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v16, EventProfilerExit, v17, v38);
      return 3221225495LL;
    }
    RtlCopyFromUser(v15, *(void **)&v47[24], 8LL * *(unsigned int *)&v47[20]);
    *(_QWORD *)&v47[24] = v12;
  }
  v42 = 0;
  DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE((DXGDEVICEBYHANDLE *)&v41, *(unsigned int *)&v47[4], Current, &v42);
  v18 = (struct ADAPTER_RENDER **)v42;
  if ( !v42 )
  {
    LODWORD(v19) = -1073741811;
    WdLogSingleEntry2(2, *(unsigned int *)&v47[4], -1073741811);
    WdLogGlobalForLineNumber = 504;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid hDevice (0x%I64x) specified, returning 0x%I64x",
      *(unsigned int *)&v47[4],
      -1073741811,
      0,
      0,
      0);
LABEL_32:
    ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v41);
    goto LABEL_58;
  }
  DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v44, v42);
  COREDEVICEACCESS::COREDEVICEACCESS(v49, v18, 2);
  LODWORD(v19) = COREDEVICEACCESS::AcquireShared((COREDEVICEACCESS *)v49, 0);
  if ( (int)v19 < 0 )
  {
LABEL_34:
    COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v49);
    DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v44);
    goto LABEL_32;
  }
  v23 = (DXGSWAPCHAIN *)operator new(240, 1265072196, 256);
  if ( v23 )
    v11 = DXGSWAPCHAIN::DXGSWAPCHAIN(v23);
  else
    v11 = 0;
  v42 = v11;
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
  LODWORD(v19) = DXGSWAPCHAIN::InitializeSwapchainGlobalState(v11, v18[2], (struct _D3DKMT_CREATESWAPCHAIN *)v47);
  if ( (int)v19 < 0 )
    goto LABEL_34;
  LODWORD(v19) = DXGSWAPCHAIN::OpenSwapchainLocal(
                   v11,
                   *(unsigned int *)&v47[4],
                   (struct DXGDEVICE *)v18,
                   *(void **)&v47[40],
                   v47[32] & 1,
                   *(int *)v47,
                   *(int *)&v47[56]);
  if ( (int)v19 < 0 )
    goto LABEL_34;
  COREDEVICEACCESS::~COREDEVICEACCESS((COREDEVICEACCESS *)v49);
  DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE((DXGDEVICEACCESSLOCKEXCLUSIVE *)v44);
  ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS((ENSURE_DEVICE_DEREFERENCE_NOLOCKS *)&v41);
  v44[0] = 0;
  DXGSWAPCHAINLOCKWITHDEVICE::DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v50, v11, *(_DWORD *)v47 != 0, 1);
  if ( (unsigned int)Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline() )
    v24 = *((_DWORD *)v11 + 59) != 0;
  else
    v24 = 0;
  v25 = DXGSWAPCHAINLOCKWITHDEVICE::Acquire((DXGSWAPCHAINLOCKWITHDEVICE *)v50, v44, 1, v24);
  v19 = v25;
  if ( v25 < 0 )
  {
    WdLogSingleEntry1(2, v25);
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
    DXGSWAPCHAINLOCKWITHDEVICE::~DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v50);
    goto LABEL_58;
  }
  for ( i = 0; i < *(_DWORD *)&v47[20]; ++i )
  {
    LODWORD(v19) = DXGSWAPCHAIN::AddSurface(v11, v44[0], *(int *)v47, *(void **)(*(_QWORD *)&v47[24] + 8LL * i), &v41);
    if ( (int)v19 < 0 )
      goto LABEL_47;
  }
  DXGSWAPCHAINLOCKWITHDEVICE::~DXGSWAPCHAINLOCKWITHDEVICE((DXGSWAPCHAINLOCKWITHDEVICE *)v50);
  v36[0] = 248;
  LOBYTE(v27) = 1;
  LOBYTE(v28) = 1;
  v29 = ObCreateObject(v28, g_pDxgkSharedSwapChainObjectType, *(_QWORD *)&v47[8], v27, 0, 8, *(_QWORD *)v36, 0, &Object);
  v19 = v29;
  if ( v29 >= 0 )
  {
    *(_QWORD *)Object = v11;
    v37 = 1;
    inserted = ObInsertObject(Object, 0, *(ACCESS_MASK *)&v47[16], 0, 0, &Srca);
    v19 = inserted;
    if ( inserted >= 0 )
    {
      RtlCopyToUser(Src + 48, &Srca, 8u);
      goto LABEL_58;
    }
    WdLogSingleEntry1(2, inserted);
    WdLogGlobalForLineNumber = 619;
    v30 = L"Failed to create Nt handle for swapchain (0x%I64x)";
  }
  else
  {
    WdLogSingleEntry1(2, v29);
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
        WdLogSingleEntry2(1, Srca, v32);
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
    if ( v11 && !v37 )
    {
      DXGSWAPCHAIN::`scalar deleting destructor'(v11, v20);
      LODWORD(v11) = 0;
    }
  }
  if ( v12 )
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v12);
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40000000000LL) != 0 )
    McTemplateK0pqdqqpp_EtwWriteTransfer(v21, v20, v22, (_DWORD)v11, v19, v47[0], v47[4], v47[20], v47[40], (char)Srca);
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
  if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v34, EventProfilerExit, v35, v38);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1401c5580  mov     [rsp+arg_8], rbx
0x1401c5585  mov     [rsp+arg_10], rsi
0x1401c558a  push    rdi
0x1401c558b  push    r12
0x1401c558d  push    r13
0x1401c558f  push    r14
0x1401c5591  push    r15
0x1401c5593  sub     rsp, 230h
0x1401c559a  mov     rax, cs:__security_cookie
0x1401c55a1  xor     rax, rsp
0x1401c55a4  mov     [rsp+258h+var_38], rax
0x1401c55ac  mov     r13, rcx
0x1401c55af  mov     [rsp+258h+var_168], rcx
0x1401c55b7  mov     [rsp+258h+var_200], 0FFFFFFFFh
0x1401c55bf  xor     edi, edi
0x1401c55c1  mov     [rsp+258h+var_1F8], rdi
0x1401c55c6  mov     rax, cs:qword_1401604F0
0x1401c55cd  lea     r12d, [rdi+2]
0x1401c55d1  test    r12b, al
0x1401c55d4  jz      short loc_1401C5600
0x1401c55d6  mov     [rsp+258h+var_1F0], 1
0x1401c55db  mov     [rsp+258h+var_200], 83Ch
0x1401c55e3  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c55ea  jz      short loc_1401C5605
0x1401c55ec  mov     r9d, 83Ch
0x1401c55f2  lea     rdx, EventProfilerEnter
0x1401c55f9  call    McTemplateK0q_EtwWriteTransfer
0x1401c55fe  jmp     short loc_1401C5605
0x1401c5600  mov     [rsp+258h+var_1F0], dil
0x1401c5605  mov     edx, 83Ch
0x1401c560a  lea     rcx, [rsp+258h+var_200]
0x1401c560f  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1401c5614  mov     [rsp+258h+Object], rdi
0x1401c561c  mov     [rsp+258h+Src], rdi
0x1401c5624  mov     esi, 40h ; '@'
0x1401c5629  mov     r8d, esi; Size
0x1401c562c  xor     edx, edx; Val
0x1401c562e  lea     rcx, [rsp+258h+var_1A8]; void *
0x1401c5636  call    memset
0x1401c563b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x1401c5640  mov     rbx, rax
0x1401c5643  test    rax, rax
0x1401c5646  jnz     short loc_1401C5668
0x1401c5648  mov     ecx, r12d
0x1401c564b  call    cs:__imp_WdLogSingleEntry0
0x1401c5652  nop     dword ptr [rax+rax+00h]
0x1401c5657  mov     eax, 1AAh
0x1401c565c  lea     r9, aInvalidProcess_3; "Invalid process context"
0x1401c5663  jmp     loc_1401C5735
0x1401c5668  mov     r8, rsi; Size
0x1401c566b  mov     rdx, r13; Src
0x1401c566e  lea     rcx, [rsp+258h+var_1A8]; void *
0x1401c5676  call    RtlCopyFromUser
0x1401c567b  nop
0x1401c567c  test    byte ptr [rsp+258h+var_1A8.Flags], r12b
0x1401c5684  jz      short loc_1401C56DB
0x1401c5686  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c568d  test    eax, eax
0x1401c568f  jz      short loc_1401C56B1
0x1401c5691  mov     ecx, r12d
0x1401c5694  call    cs:__imp_WdLogSingleEntry0
0x1401c569b  nop     dword ptr [rax+rax+00h]
0x1401c56a0  mov     eax, 1C1h
0x1401c56a5  lea     r9, aInNonSequenceM_0; "In non-sequence mode create cannot have"...
0x1401c56ac  jmp     loc_1401C5735
0x1401c56b1  cmp     [rsp+258h+var_1A8.bProducer], edi
0x1401c56b8  jnz     loc_1401C579B
0x1401c56be  mov     ecx, r12d
0x1401c56c1  call    cs:__imp_WdLogSingleEntry0
0x1401c56c8  nop     dword ptr [rax+rax+00h]
0x1401c56cd  mov     eax, 1C8h
0x1401c56d2  lea     r9, aInNonSequenceM; "In non-sequence mode create has to be t"...
0x1401c56d9  jmp     short loc_1401C5735
0x1401c56db  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c56e2  cmp     eax, 32h ; '2'
0x1401c56e5  jbe     short loc_1401C5712
0x1401c56e7  mov     edx, eax
0x1401c56e9  mov     ecx, r12d
0x1401c56ec  call    cs:__imp_WdLogSingleEntry1
0x1401c56f3  nop     dword ptr [rax+rax+00h]
0x1401c56f8  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x1401c5702  mov     eax, [rsp+258h+var_1A8.SurfaceCount]
0x1401c5709  lea     r9, aCallerRequeste; "Caller requested 0x%I64x buffers, this "...
0x1401c5710  jmp     short loc_1401C573B
0x1401c5712  test    eax, eax
0x1401c5714  jnz     loc_1401C579B
0x1401c571a  mov     ecx, r12d
0x1401c571d  call    cs:__imp_WdLogSingleEntry0
0x1401c5724  nop     dword ptr [rax+rax+00h]
0x1401c5729  mov     eax, 1D6h
0x1401c572e  lea     r9, aCannotCreateSw; "Cannot create swapchain with zero buffe"...
0x1401c5735  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c573b  mov     [rsp+258h+var_218], rdi
0x1401c5740  mov     [rsp+258h+var_220], rdi
0x1401c5745  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c574a  mov     [rsp+258h+Handle], rdi
0x1401c574f  mov     [rsp+258h+NewObject], rax
0x1401c5754  or      r8d, 0FFFFFFFFh
0x1401c5758  mov     edx, 40000h
0x1401c575d  xor     ecx, ecx
0x1401c575f  call    DxgkLogInternalTriageEvent
0x1401c5764  lea     rcx, [rsp+258h+var_200]; this
0x1401c5769  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401c576e  cmp     [rsp+258h+var_1F0], dil
0x1401c5773  jz      short loc_1401C578F
0x1401c5775  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c577c  jz      short loc_1401C578F
0x1401c577e  mov     r9d, [rsp+258h+var_200]
0x1401c5783  lea     rdx, EventProfilerExit
0x1401c578a  call    McTemplateK0q_EtwWriteTransfer
0x1401c578f  mov     rax, 0FFFFFFFFC000000Dh
0x1401c5796  jmp     loc_1401C5EB4
0x1401c579b  mov     r14, rdi
0x1401c579e  mov     [rsp+258h+var_208], dil
0x1401c57a3  mov     r15, rdi
0x1401c57a6  mov     [rsp+258h+var_1B8], rdi
0x1401c57ae  test    eax, eax
0x1401c57b0  jz      loc_1401C58C6
0x1401c57b6  mov     ecx, eax
0x1401c57b8  mov     eax, 8
0x1401c57bd  mul     rcx
0x1401c57c0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401c57c7  cmovb   rax, rcx
0x1401c57cb  mov     edx, 4B677844h
0x1401c57d0  mov     r8d, 100h
0x1401c57d6  mov     rcx, rax
0x1401c57d9  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c57de  mov     r15, rax
0x1401c57e1  mov     [rsp+258h+var_1B8], rax
0x1401c57e9  test    rax, rax
0x1401c57ec  jnz     short loc_1401C586D
0x1401c57ee  lea     ecx, [rax+6]
0x1401c57f1  call    cs:__imp_WdLogSingleEntry0
0x1401c57f8  nop     dword ptr [rax+rax+00h]
0x1401c57fd  mov     eax, 1E2h
0x1401c5802  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c5808  mov     [rsp+258h+var_218], rdi
0x1401c580d  mov     [rsp+258h+var_220], rdi
0x1401c5812  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c5817  mov     [rsp+258h+Handle], rdi
0x1401c581c  mov     [rsp+258h+NewObject], rax
0x1401c5821  lea     r9, aOutOfMemoryAll_22; "Out of memory allocating memory for han"...
0x1401c5828  or      r8d, 0FFFFFFFFh
0x1401c582c  mov     edx, 40001h
0x1401c5831  xor     ecx, ecx
0x1401c5833  call    DxgkLogInternalTriageEvent
0x1401c5838  lea     rcx, [rsp+258h+var_200]; this
0x1401c583d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1401c5842  cmp     [rsp+258h+var_1F0], dil
0x1401c5847  jz      short loc_1401C5863
0x1401c5849  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1401c5850  jz      short loc_1401C5863
0x1401c5852  mov     r9d, [rsp+258h+var_200]
0x1401c5857  lea     rdx, EventProfilerExit
0x1401c585e  call    McTemplateK0q_EtwWriteTransfer
0x1401c5863  mov     eax, 0C0000017h
0x1401c5868  jmp     loc_1401C5EB4
0x1401c586d  mov     r8d, [rsp+258h+var_1A8.SurfaceCount]
0x1401c5875  shl     r8, 3; Size
0x1401c5879  mov     rdx, [rsp+258h+var_1A8.pNtSurfaceHandles]; Src
0x1401c5881  mov     rcx, r15; void *
0x1401c5884  call    RtlCopyFromUser
0x1401c5889  nop
0x1401c588a  mov     [rsp+258h+var_1A8.pNtSurfaceHandles], r15
0x1401c5892  jmp     short loc_1401C58C6
0x1401c5894  mov     ecx, 3
0x1401c5899  call    cs:__imp_WdLogSingleEntry0
0x1401c58a0  nop     dword ptr [rax+rax+00h]
0x1401c58a5  mov     cs:WdLogGlobalForLineNumber, 1EBh
0x1401c58af  mov     esi, 0C000000Dh
0x1401c58b4  xor     edi, edi
0x1401c58b6  mov     r14d, edi
0x1401c58b9  mov     r15, [rsp+258h+var_1B8]
0x1401c58c1  jmp     loc_1401C5D37
0x1401c58c6  mov     [rsp+258h+var_1E0], rdi
0x1401c58cb  lea     r9, [rsp+258h+var_1E0]; struct DXGDEVICE **
0x1401c58d0  mov     r8, rbx; struct DXGPROCESS *
0x1401c58d3  mov     edx, [rsp+258h+var_1A8.hDevice]; unsigned int
0x1401c58da  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c58df  call    ??0DXGDEVICEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGDEVICE@@@Z; DXGDEVICEBYHANDLE::DXGDEVICEBYHANDLE(uint,DXGPROCESS *,DXGDEVICE * *)
0x1401c58e4  mov     rbx, [rsp+258h+var_1E0]
0x1401c58e9  test    rbx, rbx
0x1401c58ec  jnz     short loc_1401C595E
0x1401c58ee  mov     edx, [rsp+258h+var_1A8.hDevice]
0x1401c58f5  mov     rsi, 0FFFFFFFFC000000Dh
0x1401c58fc  mov     r8, rsi
0x1401c58ff  mov     ecx, r12d
0x1401c5902  call    cs:__imp_WdLogSingleEntry2
0x1401c5909  nop     dword ptr [rax+rax+00h]
0x1401c590e  mov     cs:WdLogGlobalForLineNumber, 1F8h
0x1401c5918  mov     eax, [rsp+258h+var_1A8.hDevice]
0x1401c591f  mov     [rsp+258h+var_218], rdi
0x1401c5924  mov     [rsp+258h+var_220], rdi
0x1401c5929  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c592e  mov     [rsp+258h+Handle], rsi
0x1401c5933  mov     [rsp+258h+NewObject], rax
0x1401c5938  lea     r9, aInvalidHdevice_2; "Invalid hDevice (0x%I64x) specified, re"...
0x1401c593f  or      r8d, 0FFFFFFFFh
0x1401c5943  mov     edx, 40000h
0x1401c5948  xor     ecx, ecx
0x1401c594a  call    DxgkLogInternalTriageEvent
0x1401c594f  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c5954  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1401c5959  jmp     loc_1401C5D37
0x1401c595e  mov     rdx, rbx; struct DXGDEVICE *
0x1401c5961  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c5969  call    ??0DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@PEAVDXGDEVICE@@@Z; DXGDEVICEACCESSLOCKEXCLUSIVE::DXGDEVICEACCESSLOCKEXCLUSIVE(DXGDEVICE *)
0x1401c596e  mov     byte ptr [rsp+258h+NewObject], dil
0x1401c5973  mov     r8d, r12d
0x1401c5976  mov     rdx, rbx
0x1401c5979  lea     rcx, [rsp+258h+var_158]
0x1401c5981  call    ??0COREDEVICEACCESS@@QEAA@QEAVDXGDEVICE@@W4_DXGDEVICEACCESS_TYPE@@I_N@Z; COREDEVICEACCESS::COREDEVICEACCESS(DXGDEVICE * const,_DXGDEVICEACCESS_TYPE,uint,bool)
0x1401c5986  xor     edx, edx; char *
0x1401c5988  lea     rcx, [rsp+258h+var_158]; this
0x1401c5990  call    ?AcquireShared@COREDEVICEACCESS@@QEAAJPEBD@Z; COREDEVICEACCESS::AcquireShared(char const *)
0x1401c5995  mov     esi, eax
0x1401c5997  test    eax, eax
0x1401c5999  jns     short loc_1401C59B7
0x1401c599b  lea     rcx, [rsp+258h+var_158]; this
0x1401c59a3  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1401c59a8  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c59b0  call    ??1DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@XZ; DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE(void)
0x1401c59b5  jmp     short loc_1401C594F
0x1401c59b7  mov     edx, 4B677844h
0x1401c59bc  mov     ecx, 0F0h
0x1401c59c1  lea     r8d, [rcx+10h]
0x1401c59c5  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401c59ca  test    rax, rax
0x1401c59cd  jz      short loc_1401C59DC
0x1401c59cf  mov     rcx, rax; this
0x1401c59d2  call    ??0DXGSWAPCHAIN@@QEAA@XZ; DXGSWAPCHAIN::DXGSWAPCHAIN(void)
0x1401c59d7  mov     r14, rax
0x1401c59da  jmp     short loc_1401C59DF
0x1401c59dc  mov     r14, rdi
0x1401c59df  mov     [rsp+258h+var_1E0], r14
0x1401c59e4  test    r14, r14
0x1401c59e7  jnz     short loc_1401C5A3E
0x1401c59e9  lea     ecx, [r14+6]
0x1401c59ed  call    cs:__imp_WdLogSingleEntry0
0x1401c59f4  nop     dword ptr [rax+rax+00h]
0x1401c59f9  mov     eax, 209h
0x1401c59fe  mov     cs:WdLogGlobalForLineNumber, eax
0x1401c5a04  mov     [rsp+258h+var_218], rdi
0x1401c5a09  mov     [rsp+258h+var_220], rdi
0x1401c5a0e  mov     qword ptr [rsp+258h+var_228], rdi
0x1401c5a13  mov     [rsp+258h+Handle], rdi
0x1401c5a18  mov     [rsp+258h+NewObject], rax
0x1401c5a1d  lea     r9, aOutOfMemoryAll_16; "Out of memory allocating DXGSWAPCHAIN c"...
0x1401c5a24  or      r8d, 0FFFFFFFFh
0x1401c5a28  mov     edx, 40001h
0x1401c5a2d  xor     ecx, ecx
0x1401c5a2f  call    DxgkLogInternalTriageEvent
0x1401c5a34  mov     esi, 0C0000017h
0x1401c5a39  jmp     loc_1401C599B
0x1401c5a3e  lea     r8, [rsp+258h+var_1A8]; struct _D3DKMT_CREATESWAPCHAIN *
0x1401c5a46  mov     rdx, [rbx+10h]; struct ADAPTER_RENDER *
0x1401c5a4a  mov     rcx, r14; this
0x1401c5a4d  call    ?InitializeSwapchainGlobalState@DXGSWAPCHAIN@@QEAAJPEAVADAPTER_RENDER@@PEAU_D3DKMT_CREATESWAPCHAIN@@@Z; DXGSWAPCHAIN::InitializeSwapchainGlobalState(ADAPTER_RENDER *,_D3DKMT_CREATESWAPCHAIN *)
0x1401c5a52  mov     esi, eax
0x1401c5a54  test    eax, eax
0x1401c5a56  js      loc_1401C599B
0x1401c5a5c  mov     ecx, dword ptr [rsp+258h+var_1A8.Flags]
0x1401c5a63  and     ecx, 1
0x1401c5a66  mov     eax, [rsp+258h+var_170]
0x1401c5a6d  mov     [rsp+258h+var_228], eax; int
0x1401c5a71  mov     eax, [rsp+258h+var_1A8.bProducer]
0x1401c5a78  mov     dword ptr [rsp+258h+Handle], eax; int
0x1401c5a7c  mov     dword ptr [rsp+258h+NewObject], ecx; int
0x1401c5a80  mov     r9, [rsp+258h+var_1A8.BufferAvailableEvent]; void *
0x1401c5a88  mov     r8, rbx; struct DXGDEVICE *
0x1401c5a8b  mov     edx, [rsp+258h+var_1A8.hDevice]; unsigned int
0x1401c5a92  mov     rcx, r14; this
0x1401c5a95  call    ?OpenSwapchainLocal@DXGSWAPCHAIN@@QEAAJIPEAVDXGDEVICE@@PEAXHHH@Z; DXGSWAPCHAIN::OpenSwapchainLocal(uint,DXGDEVICE *,void *,int,int,int)
0x1401c5a9a  mov     esi, eax
0x1401c5a9c  lea     rcx, [rsp+258h+var_158]; this
0x1401c5aa4  test    eax, eax
0x1401c5aa6  js      loc_1401C59A3
0x1401c5aac  call    ??1COREDEVICEACCESS@@QEAA@XZ; COREDEVICEACCESS::~COREDEVICEACCESS(void)
0x1401c5ab1  lea     rcx, [rsp+258h+var_1D0]; this
0x1401c5ab9  call    ??1DXGDEVICEACCESSLOCKEXCLUSIVE@@QEAA@XZ; DXGDEVICEACCESSLOCKEXCLUSIVE::~DXGDEVICEACCESSLOCKEXCLUSIVE(void)
0x1401c5abe  lea     rcx, [rsp+258h+var_1E8]; this
0x1401c5ac3  call    ??1ENSURE_DEVICE_DEREFERENCE_NOLOCKS@@QEAA@XZ; ENSURE_DEVICE_DEREFERENCE_NOLOCKS::~ENSURE_DEVICE_DEREFERENCE_NOLOCKS(void)
0x1401c5ac8  mov     [rsp+258h+var_1D0], rdi
0x1401c5ad0  cmp     [rsp+258h+var_1A8.bProducer], edi
0x1401c5ad7  setnz   r8b; bool
0x1401c5adb  mov     r9b, 1; char
0x1401c5ade  mov     rdx, r14; struct DXGSWAPCHAIN *
0x1401c5ae1  lea     rcx, [rsp+258h+var_B8]; this
0x1401c5ae9  call    ??0DXGSWAPCHAINLOCKWITHDEVICE@@QEAA@PEAVDXGSWAPCHAIN@@_ND@Z; DXGSWAPCHAINLOCKWITHDEVICE::DXGSWAPCHAINLOCKWITHDEVICE(DXGSWAPCHAIN *,bool,char)
0x1401c5aee  call    Feature_IdSwapChainUserModeSync__private_IsEnabledDeviceUsageNoInline
0x1401c5af3  test    eax, eax
0x1401c5af5  jnz     short loc_1401C5AFC
0x1401c5af7  mov     r9b, dil
0x1401c5afa  jmp     short loc_1401C5B07
0x1401c5afc  cmp     [r14+0ECh], edi
0x1401c5b03  setnz   r9b; bool
0x1401c5b07  mov     r8b, 1; bool
0x1401c5b0a  lea     rdx, [rsp+258h+var_1D0]; struct DXGDEVICE **
0x1401c5b12  lea     rcx, [rsp+258h+var_B8]; this
0x1401c5b1a  call    ?Acquire@DXGSWAPCHAINLOCKWITHDEVICE@@QEAAJPEAPEAVDXGDEVICE@@_N1@Z; DXGSWAPCHAINLOCKWITHDEVICE::Acquire(DXGDEVICE * *,bool,bool)
  ... truncated ...
```
