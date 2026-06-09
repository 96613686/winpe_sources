# MapsBackgroundTransferJob::Initialize(std::weak_ptr<MapsBackgroundTransferJob> const &,MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *)

- ea: `0x18000cfec`
- end: `0x18000d3d6`
- name: `?Initialize@MapsBackgroundTransferJob@@AEAAJAEBV?$weak_ptr@VMapsBackgroundTransferJob@@@std@@W4MAPSBTSVC_JOB_TYPE@@PEBG2@Z`
- size: `1002`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *this, __int64, int, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c834`

## callees

- `0x180002900`
- `0x1800033d4`
- `0x1800039d8`
- `0x1800041d4`
- `0x1800046ac`
- `0x180009834`
- `0x180009948`
- `0x18000cfec`
- `0x18000d694`
- `0x18000dd10`
- `0x18001110c`
- `0x180012ca0`
- `0x180012f78`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d2db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d361`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000d215`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000d215`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d2c2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d34d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d2c2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000d34d`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000d3b0`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000d3b0`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000d32f`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18000d32f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000d180`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000d180`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d043`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d157`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d265`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d043`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d157`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d265`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d11b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d304`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d11b`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000d304`

## string_xrefs

- `0x18000d202`: `BitsTemp`
- `0x18000d323`: `MapsCacheBitsTemp`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::Initialize(
        MapsBackgroundTransferJob *this,
        __int64 a2,
        int a3,
        const WCHAR *a4,
        __int64 a5)
{
  char *v8; // rdi
  int PersistedRegistryLocation; // eax
  int v10; // r8d
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // ecx
  const wchar_t *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  _DWORD *v18; // rdi
  BackgroundCopyJobNotify *v19; // rcx
  unsigned int v20; // eax
  _QWORD *v21; // rsi
  HRESULT v22; // eax
  int v23; // r8d
  int active; // eax
  int v25; // eax
  int v26; // r8d
  int LastError; // eax
  int v28; // r8d
  int TransientObjectSecurityDescriptor; // eax
  _QWORD v31[2]; // [rsp+20h] [rbp-40h] BYREF
  GUID v32; // [rsp+30h] [rbp-30h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-20h] BYREF
  _DWORD *v34; // [rsp+90h] [rbp+30h] BYREF
  char v35; // [rsp+A0h] [rbp+40h] BYREF

  v31[0] = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  *((_DWORD *)this + 10) = a3;
  v8 = (char *)this + 48;
  PersistedRegistryLocation = RegUtils::GetPersistedRegistryLocation(this, (char *)this + 48);
  if ( PersistedRegistryLocation >= 0 )
  {
    v12 = std::_WChar_traits<unsigned short>::length(L"\\");
    std::wstring::_Append<unsigned short>(v8, v13, v12);
    v14 = *((_DWORD *)this + 10);
    if ( v14 )
    {
      if ( v14 == 1 )
        v15 = L"MicrosoftMapsBingGeoStore";
      else
        v15 = 0;
    }
    else
    {
      v15 = L"MicrosoftMapsMosGeoStore";
    }
    v16 = std::_WChar_traits<unsigned short>::length(v15);
    std::wstring::_Append<unsigned short>(v8, v17, v16);
    _InterlockedExchange((volatile __int32 *)this + 20, 0);
    CallingStateTracker::CallingStateTracker(&v35, 1);
    v18 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v34 = v18;
    if ( v18 )
    {
      *(_QWORD *)v18 = &BackgroundCopyJobNotify::`vftable';
      std::weak_ptr<MapsBackgroundTransferJob>::weak_ptr<MapsBackgroundTransferJob>(v18 + 2, a2);
      v18[6] = 1;
    }
    else
    {
      v18 = 0;
    }
    v19 = (BackgroundCopyJobNotify *)*((_QWORD *)this + 4);
    if ( v19 )
      BackgroundCopyJobNotify::Release(v19);
    *((_QWORD *)this + 4) = v18;
    if ( !v18 )
    {
      v20 = ZTraceReportOrigination(-2147024882, "MapsBackgroundTransferJob::Initialize", 237, this);
LABEL_16:
      v11 = v20;
      goto LABEL_17;
    }
    v21 = (_QWORD *)((char *)this + 24);
    v22 = ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>((char *)this + 24, v31);
    if ( v22 < 0 )
    {
      v23 = 239;
LABEL_20:
      v20 = ZTraceReportPropagation(v22, "MapsBackgroundTransferJob::Initialize", v23, this);
      goto LABEL_16;
    }
    active = MapsBackgroundTransferJob::RestorePreviouslyActiveRequests(this);
    if ( active < 0 )
      ZTraceReportIgnore(active, "MapsBackgroundTransferJob::Initialize", 244, this);
    v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v21 + 200LL))(*v21, *((_QWORD *)this + 4));
    if ( v22 < 0 )
    {
      v23 = 246;
      goto LABEL_20;
    }
    v32 = GUID_NULL;
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *))(*(_QWORD *)v31[0] + 424LL))(v31[0], 2, &v32);
    if ( v22 < 0 )
    {
      v23 = 250;
      goto LABEL_20;
    }
    v22 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v21 + 184LL))(*v21, 26);
    if ( v22 < 0 )
    {
      v23 = 254;
      goto LABEL_20;
    }
    v22 = PathCchCombine((PWSTR)this + 42, 0x104u, a4, L"BitsTemp");
    if ( v22 < 0 )
    {
      v23 = 257;
      goto LABEL_20;
    }
    if ( a5 )
    {
      v34 = 0;
      v25 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _DWORD **))*v21)(
              *v21,
              &GUID_f1bd1079_9f01_4bdc_8036_f09b70095066,
              &v34);
      if ( v25 < 0 )
      {
        v26 = 263;
LABEL_34:
        v11 = ZTraceReportPropagation(v25, "MapsBackgroundTransferJob::Initialize", v26, this);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
        goto LABEL_17;
      }
      v25 = (*(__int64 (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v34 + 56LL))(v34, a5);
      if ( v25 < 0 )
      {
        v26 = 266;
        goto LABEL_34;
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    }
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v35);
    CallingStateTracker::CallingStateTracker(&v35, 3);
    if ( CreateDirectoryW(a4, 0) || GetLastError() == 183 )
    {
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      TransientObjectSecurityDescriptor = QueryTransientObjectSecurityDescriptor(
                                            12,
                                            L"MapsCacheBitsTemp",
                                            &SecurityAttributes.lpSecurityDescriptor);
      if ( TransientObjectSecurityDescriptor >= 0 )
      {
        if ( CreateDirectoryW((LPCWSTR)this + 42, &SecurityAttributes) || GetLastError() == 183 )
        {
          CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v35);
          PersistedRegistryLocation = MapsBackgroundTransferJob::NotifyOnTransientErrorState(this);
          if ( PersistedRegistryLocation >= 0 )
          {
            v11 = 0;
            goto LABEL_58;
          }
          v10 = 295;
          goto LABEL_3;
        }
        LastError = GetLastError();
        if ( LastError )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          LastError = -2143748092;
        }
        v28 = 291;
      }
      else
      {
        LastError = TransientObjectSecurityDescriptor | 0x10000000;
        v28 = 287;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v28 = 277;
    }
    v11 = ZTraceReportOrigination(LastError, "MapsBackgroundTransferJob::Initialize", v28, this);
LABEL_17:
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)&v35);
    goto LABEL_58;
  }
  v10 = 226;
LABEL_3:
  v11 = ZTraceReportPropagation(PersistedRegistryLocation, "MapsBackgroundTransferJob::Initialize", v10, this);
LABEL_58:
  FreeTransientObjectSecurityDescriptor(SecurityAttributes.lpSecurityDescriptor);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v31);
  return v11;
}

```

## disassembly

```asm
0x18000cfec  mov     [rsp-28h+arg_8], rbx
0x18000cff1  push    rbp
0x18000cff2  push    rsi
0x18000cff3  push    rdi
0x18000cff4  push    r12
0x18000cff6  push    r15
0x18000cff8  mov     rbp, rsp
0x18000cffb  sub     rsp, 60h
0x18000cfff  mov     r12, r9
0x18000d002  mov     rsi, rdx
0x18000d005  mov     rbx, rcx
0x18000d008  mov     [rbp+var_40], 0
0x18000d010  xorps   xmm0, xmm0
0x18000d013  xor     eax, eax
0x18000d015  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18000d019  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x18000d01d  mov     [rcx+28h], r8d
0x18000d021  lea     rdi, [rcx+30h]
0x18000d025  mov     rdx, rdi
0x18000d028  call    ?GetPersistedRegistryLocation@RegUtils@@SAJW4MapsRegKeys@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetPersistedRegistryLocation(MapsRegKeys,std::wstring *)
0x18000d02d  test    eax, eax
0x18000d02f  jns     short loc_18000D050
0x18000d031  mov     r8d, 0E2h
0x18000d037  lea     rdx, aMapsbackground_35; "MapsBackgroundTransferJob::Initialize"
0x18000d03e  mov     r9, rbx
0x18000d041  mov     ecx, eax
0x18000d043  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d049  mov     ebx, eax
0x18000d04b  jmp     loc_18000D3AC
0x18000d050  lea     rcx, asc_180017400; "\\"
0x18000d057  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000d05c  mov     r8, rax
0x18000d05f  mov     rdx, rcx
0x18000d062  mov     rcx, rdi
0x18000d065  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000d06a  mov     ecx, [rbx+28h]
0x18000d06d  test    ecx, ecx
0x18000d06f  jz      short loc_18000D083
0x18000d071  cmp     ecx, 1
0x18000d074  jz      short loc_18000D07A
0x18000d076  xor     ecx, ecx
0x18000d078  jmp     short loc_18000D08A
0x18000d07a  lea     rcx, aMicrosoftmapsb; "MicrosoftMapsBingGeoStore"
0x18000d081  jmp     short loc_18000D08A
0x18000d083  lea     rcx, aMicrosoftmapsm; "MicrosoftMapsMosGeoStore"
0x18000d08a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000d08f  mov     r8, rax
0x18000d092  mov     rdx, rcx
0x18000d095  mov     rcx, rdi
0x18000d098  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000d09d  xor     eax, eax
0x18000d09f  xchg    eax, [rbx+50h]
0x18000d0a2  mov     edx, 1
0x18000d0a7  lea     rcx, [rbp+arg_10]
0x18000d0ab  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18000d0b0  nop
0x18000d0b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d0b8  mov     ecx, 20h ; ' '; unsigned __int64
0x18000d0bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d0c2  mov     rdi, rax
0x18000d0c5  mov     [rbp+arg_0], rax
0x18000d0c9  test    rax, rax
0x18000d0cc  jz      short loc_18000D0ED
0x18000d0ce  lea     rax, ??_7BackgroundCopyJobNotify@@6B@; const BackgroundCopyJobNotify::`vftable'
0x18000d0d5  mov     [rdi], rax
0x18000d0d8  lea     rcx, [rdi+8]
0x18000d0dc  mov     rdx, rsi
0x18000d0df  call    ??0?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<MapsBackgroundTransferJob>::weak_ptr<MapsBackgroundTransferJob>(std::weak_ptr<MapsBackgroundTransferJob> const &)
0x18000d0e4  mov     dword ptr [rdi+18h], 1
0x18000d0eb  jmp     short loc_18000D0EF
0x18000d0ed  xor     edi, edi
0x18000d0ef  mov     rcx, [rbx+20h]; this
0x18000d0f3  test    rcx, rcx
0x18000d0f6  jz      short loc_18000D0FD
0x18000d0f8  call    ?Release@BackgroundCopyJobNotify@@UEAAKXZ; BackgroundCopyJobNotify::Release(void)
0x18000d0fd  mov     [rbx+20h], rdi
0x18000d101  test    rdi, rdi
0x18000d104  jnz     short loc_18000D131
0x18000d106  mov     r9, rbx
0x18000d109  mov     r8d, 0EDh
0x18000d10f  lea     rdx, aMapsbackground_35; "MapsBackgroundTransferJob::Initialize"
0x18000d116  mov     ecx, 8007000Eh
0x18000d11b  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000d121  mov     ebx, eax
0x18000d123  lea     rcx, [rbp+arg_10]; this
0x18000d127  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18000d12c  jmp     loc_18000D3AC
0x18000d131  lea     rsi, [rbx+18h]
0x18000d135  lea     rdx, [rbp+var_40]
0x18000d139  mov     rcx, rsi
0x18000d13c  call    ??$QueryInterface@UIBackgroundCopyJob5@@@?$CComPtrBase@UIBackgroundCopyJob@@@ATL@@QEBAJPEAPEAUIBackgroundCopyJob5@@@Z; ATL::CComPtrBase<IBackgroundCopyJob>::QueryInterface<IBackgroundCopyJob5>(IBackgroundCopyJob5 * *)
0x18000d141  test    eax, eax
0x18000d143  jns     short loc_18000D15F
0x18000d145  mov     r8d, 0EFh
0x18000d14b  lea     rdx, aMapsbackground_35; "MapsBackgroundTransferJob::Initialize"
0x18000d152  mov     r9, rbx
0x18000d155  mov     ecx, eax
0x18000d157  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d15d  jmp     short loc_18000D121
0x18000d15f  mov     rcx, rbx; this
0x18000d162  call    ?RestorePreviouslyActiveRequests@MapsBackgroundTransferJob@@AEAAJXZ; MapsBackgroundTransferJob::RestorePreviouslyActiveRequests(void)
0x18000d167  lea     rdi, aMapsbackground_35; "MapsBackgroundTransferJob::Initialize"
0x18000d16e  test    eax, eax
0x18000d170  jns     short loc_18000D186
0x18000d172  mov     r9, rbx
0x18000d175  mov     r8d, 0F4h
0x18000d17b  mov     rdx, rdi
0x18000d17e  mov     ecx, eax
0x18000d180  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000d186  mov     rcx, [rsi]
0x18000d189  mov     rax, [rcx]
0x18000d18c  mov     rdx, [rbx+20h]
0x18000d190  mov     rax, [rax+0C8h]
0x18000d197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d19c  test    eax, eax
0x18000d19e  jns     short loc_18000D1AB
0x18000d1a0  mov     r8d, 0F6h
0x18000d1a6  mov     rdx, rdi
0x18000d1a9  jmp     short loc_18000D152
0x18000d1ab  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000d1b2  mov     rcx, [rbp+var_40]
0x18000d1b6  movdqa  [rbp+var_30], xmm0
0x18000d1bb  mov     rax, [rcx]
0x18000d1be  lea     r8, [rbp+var_30]
0x18000d1c2  mov     edx, 2
0x18000d1c7  mov     rax, [rax+1A8h]
0x18000d1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d3  test    eax, eax
0x18000d1d5  jns     short loc_18000D1DF
0x18000d1d7  mov     r8d, 0FAh
0x18000d1dd  jmp     short loc_18000D1A6
0x18000d1df  mov     rcx, [rsi]
0x18000d1e2  mov     rax, [rcx]
0x18000d1e5  mov     edx, 1Ah
0x18000d1ea  mov     rax, [rax+0B8h]
0x18000d1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f6  test    eax, eax
0x18000d1f8  jns     short loc_18000D202
0x18000d1fa  mov     r8d, 0FEh
0x18000d200  jmp     short loc_18000D1A6
0x18000d202  lea     r9, pszMore; "BitsTemp"
0x18000d209  mov     r8, r12; pszPathIn
0x18000d20c  mov     edx, 104h; cchPathOut
0x18000d211  lea     rcx, [rbx+54h]; pszPathOut
0x18000d215  call    cs:__imp_PathCchCombine
0x18000d21b  test    eax, eax
0x18000d21d  jns     short loc_18000D22A
0x18000d21f  mov     r8d, 101h
0x18000d225  jmp     loc_18000D1A6
0x18000d22a  cmp     [rbp+arg_20], 0
0x18000d22f  jz      short loc_18000D2A5
0x18000d231  mov     [rbp+arg_0], 0
0x18000d239  mov     rcx, [rsi]
0x18000d23c  mov     rax, [rcx]
0x18000d23f  lea     r8, [rbp+arg_0]
0x18000d243  lea     rdx, _GUID_f1bd1079_9f01_4bdc_8036_f09b70095066
0x18000d24a  mov     rax, [rax]
0x18000d24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d252  nop
0x18000d253  test    eax, eax
0x18000d255  jns     short loc_18000D27B
0x18000d257  mov     r8d, 107h
0x18000d25d  mov     r9, rbx
0x18000d260  mov     rdx, rdi
0x18000d263  mov     ecx, eax
0x18000d265  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d26b  mov     ebx, eax
0x18000d26d  lea     rcx, [rbp+arg_0]
0x18000d271  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d276  jmp     loc_18000D123
0x18000d27b  mov     rcx, [rbp+arg_0]
0x18000d27f  mov     rax, [rcx]
0x18000d282  mov     rdx, [rbp+arg_20]
0x18000d286  mov     rax, [rax+38h]
0x18000d28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d28f  test    eax, eax
0x18000d291  jns     short loc_18000D29B
0x18000d293  mov     r8d, 10Ah
0x18000d299  jmp     short loc_18000D25D
0x18000d29b  lea     rcx, [rbp+arg_0]
0x18000d29f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d2a4  nop
0x18000d2a5  lea     rcx, [rbp+arg_10]; this
0x18000d2a9  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18000d2ae  mov     edx, 3
0x18000d2b3  lea     rcx, [rbp+arg_10]
0x18000d2b7  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18000d2bc  nop
0x18000d2bd  xor     edx, edx; lpSecurityAttributes
0x18000d2bf  mov     rcx, r12; lpPathName
0x18000d2c2  call    cs:__imp_CreateDirectoryW
0x18000d2c8  mov     esi, 0B7h
0x18000d2cd  test    eax, eax
0x18000d2cf  jnz     short loc_18000D311
0x18000d2d1  call    cs:__imp_GetLastError
0x18000d2d7  cmp     eax, esi
0x18000d2d9  jz      short loc_18000D311
0x18000d2db  call    cs:__imp_GetLastError
0x18000d2e1  test    eax, eax
0x18000d2e3  jz      short loc_18000D2F1
0x18000d2e5  jle     short loc_18000D2F6
0x18000d2e7  movzx   eax, ax
0x18000d2ea  or      eax, 80070000h
0x18000d2ef  jmp     short loc_18000D2F6
0x18000d2f1  mov     eax, 80390004h
0x18000d2f6  mov     r8d, 115h
0x18000d2fc  mov     r9, rbx
0x18000d2ff  mov     rdx, rdi
0x18000d302  mov     ecx, eax
0x18000d304  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000d30a  mov     ebx, eax
0x18000d30c  jmp     loc_18000D123
0x18000d311  mov     [rbp+SecurityAttributes.nLength], 18h
0x18000d318  mov     [rbp+SecurityAttributes.bInheritHandle], 0
0x18000d31f  lea     r8, [rbp+SecurityAttributes.lpSecurityDescriptor]
0x18000d323  lea     rdx, aMapscachebitst; "MapsCacheBitsTemp"
0x18000d32a  mov     ecx, 0Ch
0x18000d32f  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18000d335  test    eax, eax
0x18000d337  jns     short loc_18000D345
0x18000d339  bts     eax, 1Ch
0x18000d33d  mov     r8d, 11Fh
0x18000d343  jmp     short loc_18000D2FC
0x18000d345  lea     rdx, [rbp+SecurityAttributes]; lpSecurityAttributes
0x18000d349  lea     rcx, [rbx+54h]; lpPathName
0x18000d34d  call    cs:__imp_CreateDirectoryW
0x18000d353  test    eax, eax
0x18000d355  jnz     short loc_18000D387
0x18000d357  call    cs:__imp_GetLastError
0x18000d35d  cmp     eax, esi
0x18000d35f  jz      short loc_18000D387
0x18000d361  call    cs:__imp_GetLastError
0x18000d367  test    eax, eax
0x18000d369  jz      short loc_18000D377
0x18000d36b  jle     short loc_18000D37C
0x18000d36d  movzx   eax, ax
0x18000d370  or      eax, 80070000h
0x18000d375  jmp     short loc_18000D37C
0x18000d377  mov     eax, 80390004h
0x18000d37c  mov     r8d, 123h
0x18000d382  jmp     loc_18000D2FC
0x18000d387  lea     rcx, [rbp+arg_10]; this
0x18000d38b  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x18000d390  mov     rcx, rbx; this
0x18000d393  call    ?NotifyOnTransientErrorState@MapsBackgroundTransferJob@@AEAAJXZ; MapsBackgroundTransferJob::NotifyOnTransientErrorState(void)
0x18000d398  test    eax, eax
0x18000d39a  jns     short loc_18000D3AA
0x18000d39c  mov     r8d, 127h
0x18000d3a2  mov     rdx, rdi
0x18000d3a5  jmp     loc_18000D03E
0x18000d3aa  xor     ebx, ebx
0x18000d3ac  mov     rcx, [rbp+SecurityAttributes.lpSecurityDescriptor]
0x18000d3b0  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000d3b6  nop
0x18000d3b7  lea     rcx, [rbp+var_40]
0x18000d3bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d3c0  mov     eax, ebx
0x18000d3c2  mov     rbx, [rsp+60h+arg_8]
0x18000d3ca  add     rsp, 60h
0x18000d3ce  pop     r15
0x18000d3d0  pop     r12
0x18000d3d2  pop     rdi
0x18000d3d3  pop     rsi
0x18000d3d4  pop     rbp
0x18000d3d5  retn
```
