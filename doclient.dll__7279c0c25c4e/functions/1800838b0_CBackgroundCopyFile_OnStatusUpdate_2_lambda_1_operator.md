# _CBackgroundCopyFile::_OnStatusUpdate_::_2_::_lambda_1_::operator()

- ea: `0x1800838b0`
- end: `0x180083e92`
- name: `_CBackgroundCopyFile::_OnStatusUpdate_::_2_::_lambda_1_::operator()`
- size: `1506`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180087b90`

## callees

- `0x1800095a0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001dfc4`
- `0x180036ea8`
- `0x18007ca54`
- `0x1800813e0`
- `0x180081ab0`
- `0x1800838b0`
- `0x180093f74`
- `0x1800946c4`
- `0x180096130`
- `0x180096fc0`
- `0x1800970d4`
- `0x18009aa8c`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800a1f08`
- `0x1800b0e1c`
- `0x1800b2cb4`
- `0x1800be90c`
- `0x1800beccc`
- `0x1800bf914`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083a1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ad7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083c5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083cdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083d83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083e30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083a1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083ad7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083c5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083cdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083d83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180083e30`

## string_xrefs

- `0x180083dcd`: `File %s: Status update from swarm, code: %d`
- `0x1800839e6`: `CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()`
- `0x180083d46`: `CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()`
- `0x180083de2`: `CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CBackgroundCopyFile::_OnStatusUpdate_::_2_::_lambda_1_::operator()(unsigned int *a1)
{
  __int64 v2; // r15
  char v3; // bl
  __int64 v4; // rdx
  int v5; // r8d
  unsigned int v6; // r9d
  unsigned int v7; // ecx
  const char *v8; // rdx
  bool v9; // zf
  void *v10; // rbx
  struct CGlobalObjects *v11; // rax
  bool v12; // cl
  unsigned int CostPolicy; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdi
  __int64 v16; // rsi
  _BYTE *v17; // r14
  void *v18; // rbx
  CBackgroundCopyFile *v19; // rbx
  int v20; // edi
  __int64 v21; // rdx
  unsigned int v22; // esi
  const char *v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h]
  char v29[24]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33[24]; // [rsp+D0h] [rbp-30h] BYREF

  v28 = 0;
  v2 = *(_QWORD *)a1 + 264LL;
  *(_QWORD *)&v28 = v2;
  BYTE8(v28) = 0;
  if ( (unsigned int)mtx_do_lock(v2) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v2 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v3 = 1;
  BYTE8(v28) = 1;
  if ( !*(_BYTE *)(*(_QWORD *)a1 + 492LL) )
    goto LABEL_17;
  v4 = *(_QWORD *)a1;
  v5 = *(_DWORD *)(*(_QWORD *)a1 + 488LL);
  if ( (v5 & 5) != 0 )
    goto LABEL_17;
  v6 = a1[2];
  if ( v6 < 2 )
  {
    if ( *((_BYTE *)a1 + 64) != 1 )
      goto LABEL_66;
    v22 = a1[4];
    v23 = (const char *)(v4 + 144);
    if ( *((_QWORD *)v23 + 3) > 0xFu )
      v23 = *(const char **)v23;
    LogResult(
      5u,
      "CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()",
      0x4D4u,
      v22,
      "File %s: Status update from swarm, code: %d",
      v23,
      v6);
    v24 = *((_QWORD *)CGlobalObjects::Instance() + 4);
    v25 = *(_QWORD *)a1;
    v26 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 16LL))(*(_QWORD *)a1);
    CTelemetryLogger::GetLastHttpResponseHeaders(v24, v26, v25 + 176);
    v9 = (*(_DWORD *)(v2 + 76))-- == 1;
    if ( v9 )
    {
      *(_DWORD *)(v2 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
    }
    v3 = 0;
    BYTE8(v28) = 0;
    if ( !*(_BYTE *)(*(_QWORD *)a1 + 492LL) )
      goto LABEL_17;
    v21 = v22;
    goto LABEL_64;
  }
  switch ( v6 )
  {
    case 2u:
      if ( (v5 & 0x10) != 0 )
        break;
      if ( (v5 & 8) == 0 )
      {
        LogMessage(
          2u,
          "CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()",
          0x4E5u,
          "TelemetryAssert (%s): %s (0x%x, 0x%x)",
          "(static_cast<decltype((_fileState) & (static_cast<decltype(FileState_Starting)>(::wil::details::verify_single_"
          "flag_helper<static_cast<unsigned long long>(static_cast<::wil::integral_from_enum<decltype(FileState_Starting)"
          ">>(FileState_Starting))>::value)))>(static_cast<::wil::integral_from_enum<decltype(_fileState)>>(_fileState) &"
          " static_cast<::wil::integral_from_enum<decltype(static_cast<decltype(FileState_Starting)>(::wil::details::veri"
          "fy_single_flag_helper<static_cast<unsigned long long>(static_cast<::wil::integral_from_enum<decltype(FileState"
          "_Starting)>>(FileState_Starting))>::value))>>(static_cast<decltype(FileState_Starting)>(::wil::details::verify"
          "_single_flag_helper<static_cast<unsigned long long>(static_cast<::wil::integral_from_enum<decltype(FileState_S"
          "tarting)>>(FileState_Starting))>::value))) != static_cast<decltype((_fileState) & (static_cast<decltype(FileSt"
          "ate_Starting)>(::wil::details::verify_single_flag_helper<static_cast<unsigned long long>(static_cast<::wil::in"
          "tegral_from_enum<decltype(FileState_Starting)>>(FileState_Starting))>::value)))>(0))",
          "Failed",
          v5,
          0);
        DOTelemetryAssertTriggered(*(_DWORD *)(*(_QWORD *)a1 + 488LL), 0);
      }
      if ( *((_BYTE *)a1 + 64) != 2 )
        goto LABEL_66;
      v9 = (*(_DWORD *)(v2 + 76))-- == 1;
      if ( v9 )
      {
        *(_DWORD *)(v2 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
      }
      v3 = 0;
      BYTE8(v28) = 0;
      CBackgroundCopyFile::_ContinueStart(*(CBackgroundCopyFile **)a1, (const struct DownloadStatusStartData *)(a1 + 4));
      break;
    case 3u:
      if ( (*(_BYTE *)(v4 + 495) & 1) == 0 && (v5 & 0x40) == 0 )
        break;
      CBackgroundCopyFile::_EndProgressMonitoring(*(CBackgroundCopyFile **)a1);
      if ( *((_BYTE *)a1 + 64) != 1 )
        goto LABEL_66;
      v20 = a1[4];
      if ( v20 >= 0 )
        break;
      v9 = (*(_DWORD *)(v2 + 76))-- == 1;
      if ( v9 )
      {
        *(_DWORD *)(v2 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
      }
      v3 = 0;
      BYTE8(v28) = 0;
      if ( !*(_BYTE *)(*(_QWORD *)a1 + 492LL) )
        break;
      v21 = (unsigned int)v20;
LABEL_64:
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(***(_QWORD ***)(*(_QWORD *)a1 + 32LL) + 8LL))(
        **(_QWORD **)(*(_QWORD *)a1 + 32LL),
        v21,
        0);
      break;
    case 4u:
      if ( (v5 & 0x40) != 0 )
      {
        v12 = (*(_BYTE *)(v4 + 495) & 2) != 0 && !CJobSharedData::IsXVCJob(*(CJobSharedData **)(v4 + 32));
        *(_DWORD *)(*(_QWORD *)a1 + 488LL) &= ~0x40u;
        *(_BYTE *)(*(_QWORD *)a1 + 495LL) |= 1u;
        *(_BYTE *)(*(_QWORD *)a1 + 495LL) &= ~2u;
        if ( v12 )
        {
          CostPolicy = CJobSharedData::GetCostPolicy(*(_QWORD *)(*(_QWORD *)a1 + 32LL));
          v14 = CostPolicyToBitsTransferPolicy(CostPolicy);
          v15 = *(_QWORD *)a1 + 112LL;
          v16 = *(_QWORD *)(*(_QWORD *)a1 + 208LL);
          v17 = operator new(0x248u);
          Block = v17;
          EventDataDownloadResumed::EventDataDownloadResumed((_DWORD)v17, *(_QWORD *)a1, v16, v15, 0, v14);
          v17[576] = 3;
          Block = v17;
          CDownloadManager::FireTelemetry(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 8LL), *(_QWORD *)a1, &Block);
          v18 = Block;
          if ( Block )
          {
            std::_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>::~_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>((char *)Block);
            operator delete(v18);
          }
        }
        v19 = *(CBackgroundCopyFile **)a1;
        *((_QWORD *)v19 + 27) = *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)(*(_QWORD *)a1 + 344LL)
                                                                                      + 104LL))(
                                              *(_QWORD *)(*(_QWORD *)a1 + 344LL),
                                              v29)
                                          + 8);
        *((_QWORD *)v19 + 28) = *(_QWORD *)GetUnbiasedSystemTimestamp(&Block);
        CProgressMonitor::Register(
          *(CProgressMonitor **)(*(_QWORD *)(*((_QWORD *)v19 + 4) + 8LL) + 24LL),
          (CBackgroundCopyFile *)((char *)v19 + 8));
      }
      v9 = (*(_DWORD *)(v2 + 76))-- == 1;
      if ( v9 )
      {
        *(_DWORD *)(v2 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
      }
      v3 = 0;
      BYTE8(v28) = 0;
      if ( *(_BYTE *)(*(_QWORD *)a1 + 492LL) )
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(***(_QWORD ***)(*(_QWORD *)a1 + 32LL) + 16LL))(
          **(_QWORD **)(*(_QWORD *)a1 + 32LL),
          *(_QWORD *)a1,
          32);
      break;
    case 5u:
      if ( *((_BYTE *)a1 + 64) != 3 )
        goto LABEL_66;
      v10 = (void *)*((_QWORD *)a1 + 2);
      Block = v10;
      if ( !CJobSharedData::IsXVCJob(*(CJobSharedData **)(v4 + 32)) && BYTE4(Block) )
      {
        TelDataDownloadIdentifiers::TelDataDownloadIdentifiers(
          (TelDataDownloadIdentifiers *)v30,
          *(struct IDownloadRequest **)a1,
          *(struct TraceLoggingCorrelationVector **)(*(_QWORD *)a1 + 208LL));
        v11 = CGlobalObjects::Instance();
        CTelemetryLogger::TraceDownloadProgress(
          *((CTelemetryLogger **)v11 + 4),
          (const struct TelDataDownloadIdentifiers *)v30,
          (unsigned int)v10);
        std::string::~string(v33);
        std::string::~string(v32);
        std::string::~string(v31);
        std::string::~string(v30);
      }
      v9 = (*(_DWORD *)(v2 + 76))-- == 1;
      if ( v9 )
      {
        *(_DWORD *)(v2 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
      }
      v3 = 0;
      BYTE8(v28) = 0;
      if ( *(_BYTE *)(*(_QWORD *)a1 + 492LL) )
        (*(void (__fastcall **)(_QWORD))(***(_QWORD ***)(*(_QWORD *)a1 + 32LL) + 24LL))(**(_QWORD **)(*(_QWORD *)a1 + 32LL));
      break;
    case 6u:
      if ( *((_BYTE *)a1 + 64) == 4 )
      {
        v7 = a1[4];
        if ( v7 || *((_QWORD *)a1 + 3) >= 0x1400000u )
        {
          v8 = (const char *)(v4 + 144);
          if ( *((_QWORD *)v8 + 3) > 0xFu )
            v8 = *(const char **)v8;
          LogMessage(
            5u,
            "CBackgroundCopyFile::_OnStatusUpdate::<lambda_1>::operator ()",
            0x52Du,
            "File %s: pending output %llu bytes, output rate %u Bps",
            v8,
            *((_QWORD *)a1 + 3),
            v7);
          CDownloadManager::SetOutputRateLimit(
            *(CDownloadManager **)(*(_QWORD *)(*(_QWORD *)a1 + 32LL) + 8LL),
            *(const struct IDownloadRequest **)a1);
        }
        break;
      }
LABEL_66:
      std::_Throw_bad_variant_access();
    default:
      break;
  }
LABEL_17:
  if ( v3 )
  {
    v9 = (*(_DWORD *)(v2 + 76))-- == 1;
    if ( v9 )
    {
      *(_DWORD *)(v2 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v2 + 16));
    }
  }
}

```

## disassembly

```asm
0x1800838b0  mov     [rsp-8+arg_8], rbx
0x1800838b5  mov     [rsp-8+arg_10], rsi
0x1800838ba  push    rbp
0x1800838bb  push    rdi
0x1800838bc  push    r12
0x1800838be  push    r14
0x1800838c0  push    r15
0x1800838c2  lea     rbp, [rsp-0A0h]
0x1800838ca  sub     rsp, 1A0h
0x1800838d1  mov     rax, cs:__security_cookie
0x1800838d8  xor     rax, rsp
0x1800838db  mov     [rbp+0C0h+var_30], rax
0x1800838e2  mov     r12, rcx
0x1800838e5  xorps   xmm0, xmm0
0x1800838e8  movups  [rsp+1C0h+var_178], xmm0
0x1800838ed  mov     r15, [rcx]
0x1800838f0  add     r15, 108h
0x1800838f7  mov     qword ptr [rsp+1C0h+var_178], r15
0x1800838fc  mov     byte ptr [rsp+1C0h+var_178+8], 0
0x180083901  mov     rcx, r15
0x180083904  call    mtx_do_lock
0x180083909  test    eax, eax
0x18008390b  jnz     loc_180083E87
0x180083911  mov     eax, [r15+4Ch]
0x180083915  cmp     eax, 7FFFFFFFh
0x18008391a  jz      loc_180083E70
0x180083920  mov     bl, 1
0x180083922  mov     byte ptr [rsp+1C0h+var_178+8], bl
0x180083926  mov     rax, [r12]
0x18008392a  mov     cl, [rax+1ECh]
0x180083930  nop
0x180083931  or      r14d, 0FFFFFFFFh
0x180083935  test    cl, cl
0x180083937  jz      loc_180083A09
0x18008393d  mov     rdx, [r12]
0x180083941  mov     r8d, [rdx+1E8h]
0x180083948  test    r8b, 5
0x18008394c  jnz     loc_180083A09
0x180083952  mov     r9d, [r12+8]
0x180083957  mov     ecx, r9d
0x18008395a  test    r9d, r9d
0x18008395d  jz      loc_180083DA2
0x180083963  sub     ecx, 1
0x180083966  jz      loc_180083DA2
0x18008396c  sub     ecx, 1
0x18008396f  jz      loc_180083D03
0x180083975  sub     ecx, 1
0x180083978  jz      loc_180083C9C
0x18008397e  sub     ecx, 1
0x180083981  jz      loc_180083B12
0x180083987  sub     ecx, 1
0x18008398a  jz      loc_180083A4D
0x180083990  cmp     ecx, 1
0x180083993  jnz     short loc_180083A09
0x180083995  cmp     byte ptr [r12+40h], 4
0x18008399b  jnz     loc_180083E81
0x1800839a1  mov     ecx, [r12+10h]
0x1800839a6  test    ecx, ecx
0x1800839a8  jnz     short loc_1800839B5
0x1800839aa  cmp     qword ptr [r12+18h], 1400000h
0x1800839b3  jb      short loc_180083A09
0x1800839b5  mov     r8, [r12+18h]
0x1800839ba  add     rdx, 90h
0x1800839c1  cmp     qword ptr [rdx+18h], 0Fh
0x1800839c6  jbe     short loc_1800839CB
0x1800839c8  mov     rdx, [rdx]
0x1800839cb  mov     [rsp+1C0h+var_190], ecx
0x1800839cf  mov     [rsp+1C0h+var_198], r8
0x1800839d4  mov     [rsp+1C0h+var_1A0], rdx
0x1800839d9  lea     r9, aFileSPendingOu; "File %s: pending output %llu bytes, out"...
0x1800839e0  mov     r8d, 52Dh; unsigned int
0x1800839e6  lea     rdx, aCbackgroundcop_14; "CBackgroundCopyFile::_OnStatusUpdate::<"...
0x1800839ed  mov     ecx, 5; unsigned __int8
0x1800839f2  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800839f7  mov     rdx, [r12]; struct IDownloadRequest *
0x1800839fb  mov     rcx, [rdx+20h]
0x1800839ff  mov     rcx, [rcx+8]; this
0x180083a03  call    ?SetOutputRateLimit@CDownloadManager@@QEAAXAEBVIDownloadRequest@@@Z; CDownloadManager::SetOutputRateLimit(IDownloadRequest const &)
0x180083a08  nop
0x180083a09  test    bl, bl
0x180083a0b  jz      short loc_180083A22
0x180083a0d  sub     dword ptr [r15+4Ch], 1
0x180083a12  jnz     short loc_180083A22
0x180083a14  mov     [r15+48h], r14d
0x180083a18  lea     rcx, [r15+10h]; SRWLock
0x180083a1c  call    cs:__imp_ReleaseSRWLockExclusive
0x180083a22  mov     rcx, [rbp+0C0h+var_30]
0x180083a29  xor     rcx, rsp; StackCookie
0x180083a2c  call    __security_check_cookie
0x180083a31  lea     r11, [rsp+1C0h+var_20]
0x180083a39  mov     rbx, [r11+38h]
0x180083a3d  mov     rsi, [r11+40h]
0x180083a41  mov     rsp, r11
0x180083a44  pop     r15
0x180083a46  pop     r14
0x180083a48  pop     r12
0x180083a4a  pop     rdi
0x180083a4b  pop     rbp
0x180083a4c  retn
0x180083a4d  cmp     byte ptr [r12+40h], 3
0x180083a53  jnz     loc_180083E81
0x180083a59  mov     rbx, [r12+10h]
0x180083a5e  mov     [rsp+1C0h+Block], rbx
0x180083a63  mov     rcx, [rdx+20h]; this
0x180083a67  call    ?IsXVCJob@CJobSharedData@@QEBA_NXZ; CJobSharedData::IsXVCJob(void)
0x180083a6c  test    al, al
0x180083a6e  jnz     short loc_180083AC8
0x180083a70  cmp     byte ptr [rsp+1C0h+Block+4], al
0x180083a74  jz      short loc_180083AC8
0x180083a76  mov     rdx, [r12]; struct IDownloadRequest *
0x180083a7a  mov     r8, [rdx+0D0h]; struct TraceLoggingCorrelationVector *
0x180083a81  lea     rcx, [rsp+1C0h+var_150]; this
0x180083a86  call    ??0TelDataDownloadIdentifiers@@QEAA@PEAVIDownloadRequest@@PEAVTraceLoggingCorrelationVector@@@Z; TelDataDownloadIdentifiers::TelDataDownloadIdentifiers(IDownloadRequest *,TraceLoggingCorrelationVector *)
0x180083a8b  nop
0x180083a8c  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x180083a91  mov     r8d, ebx; unsigned int
0x180083a94  lea     rdx, [rsp+1C0h+var_150]; struct TelDataDownloadIdentifiers *
0x180083a99  mov     rcx, [rax+20h]; this
0x180083a9d  call    ?TraceDownloadProgress@CTelemetryLogger@@QEAAXAEBUTelDataDownloadIdentifiers@@I@Z; CTelemetryLogger::TraceDownloadProgress(TelDataDownloadIdentifiers const &,uint)
0x180083aa2  nop
0x180083aa3  lea     rcx, [rbp+0C0h+var_F0]; void *
0x180083aa7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180083aac  lea     rcx, [rbp+0C0h+var_110]; void *
0x180083ab0  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180083ab5  lea     rcx, [rbp+0C0h+var_130]; void *
0x180083ab9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180083abe  lea     rcx, [rsp+1C0h+var_150]; void *
0x180083ac3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180083ac8  sub     dword ptr [r15+4Ch], 1
0x180083acd  jnz     short loc_180083ADD
0x180083acf  mov     [r15+48h], r14d
0x180083ad3  lea     rcx, [r15+10h]; SRWLock
0x180083ad7  call    cs:__imp_ReleaseSRWLockExclusive
0x180083add  xor     bl, bl
0x180083adf  mov     byte ptr [rsp+1C0h+var_178+8], bl
0x180083ae3  mov     rax, [r12]
0x180083ae7  mov     cl, [rax+1ECh]
0x180083aed  nop
0x180083aee  test    cl, cl
0x180083af0  jz      loc_180083A09
0x180083af6  mov     rax, [r12]
0x180083afa  mov     rcx, [rax+20h]
0x180083afe  mov     rcx, [rcx]
0x180083b01  mov     rax, [rcx]
0x180083b04  mov     rax, [rax+18h]
0x180083b08  call    _guard_dispatch_icall
0x180083b0d  jmp     loc_180083A09
0x180083b12  test    r8b, 40h
0x180083b16  jz      loc_180083C4C
0x180083b1c  test    byte ptr [rdx+1EFh], 2
0x180083b23  jz      short loc_180083B36
0x180083b25  mov     rcx, [rdx+20h]; this
0x180083b29  call    ?IsXVCJob@CJobSharedData@@QEBA_NXZ; CJobSharedData::IsXVCJob(void)
0x180083b2e  test    al, al
0x180083b30  jnz     short loc_180083B36
0x180083b32  mov     cl, bl
0x180083b34  jmp     short loc_180083B38
0x180083b36  xor     cl, cl
0x180083b38  mov     rax, [r12]
0x180083b3c  and     dword ptr [rax+1E8h], 0FFFFFFBFh
0x180083b43  mov     rax, [r12]
0x180083b47  or      [rax+1EFh], bl
0x180083b4d  mov     rax, [r12]
0x180083b51  and     byte ptr [rax+1EFh], 0FDh
0x180083b58  test    cl, cl
0x180083b5a  jz      loc_180083BFC
0x180083b60  mov     rcx, [r12]
0x180083b64  mov     rcx, [rcx+20h]
0x180083b68  call    ?GetCostPolicy@CJobSharedData@@QEBA?AW4DownloadCostPolicy@@XZ; CJobSharedData::GetCostPolicy(void)
0x180083b6d  mov     ecx, eax; unsigned int
0x180083b6f  call    ?CostPolicyToBitsTransferPolicy@@YAII@Z; CostPolicyToBitsTransferPolicy(uint)
0x180083b74  mov     ebx, eax
0x180083b76  mov     rcx, [r12]
0x180083b7a  lea     rdi, [rcx+70h]
0x180083b7e  mov     rsi, [rcx+0D0h]
0x180083b85  mov     ecx, 248h; Size
0x180083b8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083b8f  mov     r14, rax
0x180083b92  mov     [rsp+1C0h+Block], rax
0x180083b97  mov     dword ptr [rsp+1C0h+var_198], ebx
0x180083b9b  mov     dword ptr [rsp+1C0h+var_1A0], 0
0x180083ba3  mov     r9, rdi
0x180083ba6  mov     r8, rsi
0x180083ba9  mov     rdx, [r12]
0x180083bad  mov     rcx, rax
0x180083bb0  call    ??0EventDataDownloadResumed@@QEAA@PEAVIDownloadRequest@@PEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JI@Z; EventDataDownloadResumed::EventDataDownloadResumed(IDownloadRequest *,TraceLoggingCorrelationVector *,std::string const &,long,uint)
0x180083bb5  mov     byte ptr [r14+240h], 3
0x180083bbd  mov     [rsp+1C0h+Block], r14
0x180083bc2  mov     rdx, [r12]
0x180083bc6  mov     rcx, [rdx+20h]
0x180083bca  lea     r8, [rsp+1C0h+Block]
0x180083bcf  mov     rcx, [rcx+8]
0x180083bd3  call    ?FireTelemetry@CDownloadManager@@QEAAXAEBVIDownloadRequest@@$$QEAV?$unique_ptr@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@U?$default_delete@V?$variant@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@@2@@std@@@Z; CDownloadManager::FireTelemetry(IDownloadRequest const &,std::unique_ptr<std::variant<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>> &&)
0x180083bd8  nop
0x180083bd9  mov     rbx, [rsp+1C0h+Block]
0x180083bde  test    rbx, rbx
0x180083be1  jz      short loc_180083BF8
0x180083be3  mov     rcx, rbx
0x180083be6  call    ??1?$_Variant_destroy_layer_@UEventDataDownloadCanceled@@UEventDataDownloadCompleted@@UEventDataDownloadPaused@@UEventDataDownloadResumed@@UEventDataDownloadStarted@@UEventDataDownloadStuck@@@std@@QEAA@XZ; std::_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>::~_Variant_destroy_layer_<EventDataDownloadCanceled,EventDataDownloadCompleted,EventDataDownloadPaused,EventDataDownloadResumed,EventDataDownloadStarted,EventDataDownloadStuck>(void)
0x180083beb  mov     edx, 248h
0x180083bf0  mov     rcx, rbx; Block
0x180083bf3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180083bf8  or      r14d, 0FFFFFFFFh
0x180083bfc  mov     rbx, [r12]
0x180083c00  mov     rcx, [rbx+158h]
0x180083c07  mov     rax, [rcx]
0x180083c0a  lea     rdx, [rsp+1C0h+var_168]
0x180083c0f  mov     rax, [rax+68h]
0x180083c13  call    _guard_dispatch_icall
0x180083c18  mov     rcx, [rax+8]
0x180083c1c  mov     [rbx+0D8h], rcx
0x180083c23  lea     rcx, [rsp+1C0h+Block]
0x180083c28  call    ?GetUnbiasedSystemTimestamp@@YA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@std@@XZ; GetUnbiasedSystemTimestamp(void)
0x180083c2d  mov     rcx, [rax]
0x180083c30  mov     [rbx+0E0h], rcx
0x180083c37  lea     rdx, [rbx+8]; struct IProgressMonitorCallback *
0x180083c3b  mov     rax, [rbx+20h]
0x180083c3f  mov     rcx, [rax+8]
0x180083c43  mov     rcx, [rcx+18h]; this
0x180083c47  call    ?Register@CProgressMonitor@@QEAAXPEAVIProgressMonitorCallback@@@Z; CProgressMonitor::Register(IProgressMonitorCallback *)
0x180083c4c  sub     dword ptr [r15+4Ch], 1
0x180083c51  jnz     short loc_180083C61
0x180083c53  mov     [r15+48h], r14d
0x180083c57  lea     rcx, [r15+10h]; SRWLock
0x180083c5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180083c61  xor     bl, bl
0x180083c63  mov     byte ptr [rsp+1C0h+var_178+8], bl
0x180083c67  mov     rax, [r12]
0x180083c6b  mov     cl, [rax+1ECh]
0x180083c71  nop
0x180083c72  test    cl, cl
0x180083c74  jz      loc_180083A09
0x180083c7a  mov     rdx, [r12]
0x180083c7e  mov     rax, [rdx+20h]
0x180083c82  mov     rcx, [rax]
0x180083c85  mov     rax, [rcx]
0x180083c88  mov     r8d, 20h ; ' '
0x180083c8e  mov     rax, [rax+10h]
0x180083c92  call    _guard_dispatch_icall
0x180083c97  jmp     loc_180083A09
0x180083c9c  test    [rdx+1EFh], bl
0x180083ca2  jnz     short loc_180083CAE
0x180083ca4  test    r8b, 40h
0x180083ca8  jz      loc_180083A09
0x180083cae  mov     rcx, rdx; this
0x180083cb1  call    ?_EndProgressMonitoring@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_EndProgressMonitoring(void)
0x180083cb6  cmp     [r12+40h], bl
0x180083cbb  jnz     loc_180083E81
0x180083cc1  mov     edi, [r12+10h]
0x180083cc6  test    edi, edi
0x180083cc8  jns     loc_180083A09
0x180083cce  sub     dword ptr [r15+4Ch], 1
0x180083cd3  jnz     short loc_180083CE3
0x180083cd5  mov     [r15+48h], r14d
0x180083cd9  lea     rcx, [r15+10h]; SRWLock
0x180083cdd  call    cs:__imp_ReleaseSRWLockExclusive
0x180083ce3  xor     bl, bl
0x180083ce5  mov     byte ptr [rsp+1C0h+var_178+8], bl
0x180083ce9  mov     rax, [r12]
0x180083ced  mov     cl, [rax+1ECh]
0x180083cf3  nop
0x180083cf4  test    cl, cl
0x180083cf6  jz      loc_180083A09
0x180083cfc  mov     edx, edi
0x180083cfe  jmp     loc_180083E51
0x180083d03  test    r8b, 10h
0x180083d07  jnz     loc_180083A09
0x180083d0d  test    r8b, 8
0x180083d11  jnz     short loc_180083D68
0x180083d13  mov     [rsp+1C0h+var_188], 0
0x180083d1c  mov     [rsp+1C0h+var_190], r8d
0x180083d21  lea     rax, aFailed; "Failed"
0x180083d28  mov     [rsp+1C0h+var_198], rax
0x180083d2d  lea     rax, aStaticCastDecl_1; "(static_cast<decltype((_fileState) & (s"...
0x180083d34  mov     [rsp+1C0h+var_1A0], rax
0x180083d39  lea     r9, aTelemetryasser_0; "TelemetryAssert (%s): %s (0x%x, 0x%x)"
0x180083d40  mov     r8d, 4E5h; unsigned int
0x180083d46  lea     rdx, aCbackgroundcop_14; "CBackgroundCopyFile::_OnStatusUpdate::<"...
0x180083d4d  mov     ecx, 2; unsigned __int8
0x180083d52  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180083d57  mov     rcx, [r12]
0x180083d5b  xor     edx, edx; unsigned int
0x180083d5d  mov     ecx, [rcx+1E8h]; unsigned int
0x180083d63  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x180083d68  cmp     byte ptr [r12+40h], 2
0x180083d6e  jnz     loc_180083E81
0x180083d74  sub     dword ptr [r15+4Ch], 1
0x180083d79  jnz     short loc_180083D89
0x180083d7b  mov     [r15+48h], r14d
0x180083d7f  lea     rcx, [r15+10h]; SRWLock
0x180083d83  call    cs:__imp_ReleaseSRWLockExclusive
0x180083d89  xor     bl, bl
0x180083d8b  mov     byte ptr [rsp+1C0h+var_178+8], bl
0x180083d8f  lea     rdx, [r12+10h]; struct DownloadStatusStartData *
0x180083d94  mov     rcx, [r12]; this
0x180083d98  call    ?_ContinueStart@CBackgroundCopyFile@@AEAAXAEBUDownloadStatusStartData@@@Z; CBackgroundCopyFile::_ContinueStart(DownloadStatusStartData const &)
0x180083d9d  jmp     loc_180083A09
0x180083da2  cmp     [r12+40h], bl
0x180083da7  jnz     loc_180083E81
0x180083dad  mov     esi, [r12+10h]
  ... truncated ...
```
