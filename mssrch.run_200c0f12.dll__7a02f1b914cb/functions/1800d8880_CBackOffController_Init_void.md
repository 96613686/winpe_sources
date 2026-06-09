# CBackOffController::Init(void)

- ea: `0x1800d8880`
- end: `0x1800d8b94`
- name: `?Init@CBackOffController@@UEAAJXZ`
- size: `788`
- prototype: `__int64 __fastcall(CBackOffController *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000bf8c`
- `0x18000f880`
- `0x180012318`
- `0x180026b58`
- `0x18002bf00`
- `0x1800548a4`
- `0x180054cb8`
- `0x1800555f0`
- `0x1800c2734`
- `0x1800d8880`
- `0x1800d8b9c`
- `0x1800d9830`
- `0x1800f8f24`
- `0x1800fe1a0`
- `0x180103bb0`
- `0x18010ad2c`
- `0x1801244c0`
- `0x1801244f0`
- `0x18015f04c`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d88f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d894e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d88f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d894e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d88b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d88b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d896d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d896d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d8af0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d8af0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1800d8aa5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GlobalMemoryStatus` at `0x1800d8aa5`

## string_xrefs

- `0x1800d89e3`: `DataDirectory`

## pseudocode

```c
__int64 __fastcall CBackOffController::Init(CBackOffController *this)
{
  HANDLE v2; // rax
  __int64 v3; // rcx
  signed int LastError; // eax
  unsigned int v5; // ebx
  HANDLE EventW; // rax
  signed int v7; // eax
  int v8; // ecx
  _DWORD *v9; // rdi
  std::_Ref_count_base *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  int v15; // edx
  int v16; // ecx
  SIZE_T v17; // r9
  SIZE_T v18; // r8
  BOOL v19; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v21; // r9
  __int64 v22; // rcx
  int v24; // [rsp+20h] [rbp-E0h]
  _BYTE v25[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh]
  char *v27; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+40h] [rbp-C0h] BYREF
  struct _MEMORYSTATUS Buffer; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v30[192]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v27 = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 1;
  EventAttributes.lpSecurityDescriptor = 0;
  v2 = CreateEventW(&EventAttributes, 1, 1, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 760,
    v2);
  v3 = *((_QWORD *)this + 95);
  if ( ((v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  *((_QWORD *)this + 93) = v3;
  *((_BYTE *)this + 752) = 1;
  EventW = CreateEventW(0, 1, 1, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 128,
    EventW);
  if ( ((*((_QWORD *)this + 16) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v5 = v7;
    goto LABEL_26;
  }
  if ( *((_DWORD *)System::SystemInfo() + 1) )
  {
    *((_DWORD *)this + 46) = 0x100000u / *((_DWORD *)System::SystemInfo() + 1);
    v8 = *((_DWORD *)System::SystemInfo() + 1);
  }
  else
  {
    *((_DWORD *)this + 46) = 256;
    v8 = 4096;
  }
  *((_DWORD *)this + 45) = v8;
  CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v30, 0, 0xF003Fu);
  CRegistry::GetValue((CRegistry *)v30, L"DataDirectory", (CBackOffController *)((char *)this + 256));
  CLMString::ExpandEnvironmentStringsW((CBackOffController *)((char *)this + 256));
  v9 = operator new(0x120u);
  v9[2] = 1;
  v9[3] = 1;
  *(_QWORD *)v9 = &std::_Ref_count_obj2<CBackoffStateManager>::`vftable';
  CBackoffStateManager::CBackoffStateManager((CBackoffStateManager *)(v9 + 4));
  *((_QWORD *)this + 56) = v9 + 4;
  v10 = (std::_Ref_count_base *)*((_QWORD *)this + 57);
  *((_QWORD *)this + 57) = v9;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  v11 = *((_QWORD *)this + 56);
  if ( !v11 )
  {
    v5 = -2147024882;
    v12 = 194;
    v13 = 2147942414LL;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\backoffctrl.cxx",
      (const char *)v13,
      v24);
LABEL_16:
    CRegistry::~CRegistry((CRegistry *)v30);
    goto LABEL_26;
  }
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  v5 = v14;
  if ( v14 < 0 )
  {
    v13 = (unsigned int)v14;
    v12 = 196;
    goto LABEL_15;
  }
  Buffer.dwLength = 56;
  GlobalMemoryStatus(&Buffer);
  v17 = *((unsigned int *)this + 50);
  v18 = Buffer.dwAvailPageFile >> 10;
  v19 = Buffer.dwAvailPageFile >> 10 < v17;
  *((_DWORD *)this + 41) = v19;
  if ( (byte_1802DA181 & 4) != 0 )
    McTemplateU0qqt_EventWriteTransfer(v16, v15, v18, v17, v19);
  ThreadpoolTimer = CreateThreadpoolTimer(CBackOffController::ForceTimerCallback, (char *)this - 8, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (char *)this + 768,
    ThreadpoolTimer);
  if ( !*((_QWORD *)this + 96) )
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xCD,
           (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\backoffctrl.cxx",
           v21);
    goto LABEL_16;
  }
  ETWLog::Log(L"OverrideFullBackOffItemsCountThreshold : %d", *((unsigned int *)this + 53));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFix56414827>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827>::GetCachedVariantState(v22, v25);
    *((_DWORD *)this + 109) = v26;
  }
  CRegistry::~CRegistry((CRegistry *)v30);
  v5 = 0;
LABEL_26:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v27);
  return v5;
}

```

## disassembly

```asm
0x1800d8880  mov     [rsp-8+arg_8], rbx
0x1800d8885  mov     [rsp-8+arg_10], rsi
0x1800d888a  push    rbp
0x1800d888b  push    rdi
0x1800d888c  push    r15
0x1800d888e  lea     rbp, [rsp-60h]
0x1800d8893  sub     rsp, 160h
0x1800d889a  mov     rax, cs:__security_cookie
0x1800d88a1  xor     rax, rsp
0x1800d88a4  mov     [rbp+70h+var_20], rax
0x1800d88a8  mov     rsi, rcx
0x1800d88ab  add     rcx, 20h ; ' '; lpCriticalSection
0x1800d88af  mov     [rsp+170h+var_138], rcx
0x1800d88b4  call    cs:__imp_EnterCriticalSection
0x1800d88ba  mov     r15d, 1
0x1800d88c0  mov     qword ptr [rsp+170h+EventAttributes.nLength], 18h
0x1800d88c9  mov     r8d, r15d; bInitialState
0x1800d88cc  mov     qword ptr [rsp+170h+EventAttributes.bInheritHandle], 1
0x1800d88d5  mov     edx, r15d; bManualReset
0x1800d88d8  mov     [rsp+170h+EventAttributes.lpSecurityDescriptor], 0
0x1800d88e1  xor     r9d, r9d; lpName
0x1800d88e4  lea     rcx, [rsp+170h+EventAttributes]; lpEventAttributes
0x1800d88e9  lea     rbx, [rsi+2F8h]
0x1800d88f0  call    cs:__imp_CreateEventW
0x1800d88f6  mov     rdx, rax
0x1800d88f9  mov     rcx, rbx
0x1800d88fc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d8901  mov     rcx, [rbx]
0x1800d8904  lea     rax, [rcx+1]
0x1800d8908  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800d890e  jnz     short loc_1800D892E
0x1800d8910  call    cs:__imp_GetLastError
0x1800d8916  mov     ebx, eax
0x1800d8918  test    eax, eax
0x1800d891a  jle     loc_1800D8B64
0x1800d8920  movzx   ebx, ax
0x1800d8923  or      ebx, 80070000h
0x1800d8929  jmp     loc_1800D8B64
0x1800d892e  mov     [rsi+2E8h], rcx
0x1800d8935  lea     rbx, [rsi+80h]
0x1800d893c  xor     ecx, ecx; lpEventAttributes
0x1800d893e  mov     [rsi+2F0h], r15b
0x1800d8945  xor     r9d, r9d; lpName
0x1800d8948  mov     r8d, r15d; bInitialState
0x1800d894b  mov     edx, r15d; bManualReset
0x1800d894e  call    cs:__imp_CreateEventW
0x1800d8954  mov     rdx, rax
0x1800d8957  mov     rcx, rbx
0x1800d895a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d895f  mov     rax, [rbx]
0x1800d8962  add     rax, r15
0x1800d8965  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800d896b  jnz     short loc_1800D8986
0x1800d896d  call    cs:__imp_GetLastError
0x1800d8973  test    eax, eax
0x1800d8975  jle     short loc_1800D897F
0x1800d8977  movzx   eax, ax
0x1800d897a  or      eax, 80070000h
0x1800d897f  mov     ebx, eax
0x1800d8981  jmp     loc_1800D8B64
0x1800d8986  call    ?SystemInfo@System@@YAAEBVCSystemInfo@1@XZ; System::SystemInfo(void)
0x1800d898b  cmp     dword ptr [rax+4], 0
0x1800d898f  jbe     short loc_1800D89B3
0x1800d8991  call    ?SystemInfo@System@@YAAEBVCSystemInfo@1@XZ; System::SystemInfo(void)
0x1800d8996  mov     rcx, rax
0x1800d8999  xor     edx, edx
0x1800d899b  mov     eax, 100000h
0x1800d89a0  div     dword ptr [rcx+4]
0x1800d89a3  mov     [rsi+0B8h], eax
0x1800d89a9  call    ?SystemInfo@System@@YAAEBVCSystemInfo@1@XZ; System::SystemInfo(void)
0x1800d89ae  mov     ecx, [rax+4]
0x1800d89b1  jmp     short loc_1800D89C2
0x1800d89b3  mov     dword ptr [rsi+0B8h], 100h
0x1800d89bd  mov     ecx, 1000h
0x1800d89c2  mov     [rsi+0B4h], ecx
0x1800d89c8  xor     edx, edx; wchar_t *
0x1800d89ca  lea     rcx, [rbp+70h+var_E0]; this
0x1800d89ce  mov     r8d, 0F003Fh; unsigned int
0x1800d89d4  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x1800d89d9  lea     rbx, [rsi+100h]
0x1800d89e0  mov     r8, rbx; struct CLMString *
0x1800d89e3  lea     rdx, aDatadirectory; "DataDirectory"
0x1800d89ea  lea     rcx, [rbp+70h+var_E0]; this
0x1800d89ee  call    ?GetValue@CRegistry@@QEAAHPEB_WAEAVCLMString@@@Z; CRegistry::GetValue(wchar_t const *,CLMString &)
0x1800d89f3  mov     rcx, rbx; this
0x1800d89f6  call    ?ExpandEnvironmentStringsW@CLMString@@QEAAXXZ; CLMString::ExpandEnvironmentStringsW(void)
0x1800d89fb  mov     ecx, 120h; Size
0x1800d8a00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8a05  mov     rdi, rax
0x1800d8a08  mov     [rax+8], r15d
0x1800d8a0c  mov     [rax+0Ch], r15d
0x1800d8a10  lea     rbx, [rdi+10h]
0x1800d8a14  lea     rax, ??_7?$_Ref_count_obj2@VCBackoffStateManager@@@std@@6B@; const std::_Ref_count_obj2<CBackoffStateManager>::`vftable'
0x1800d8a1b  mov     rcx, rbx; this
0x1800d8a1e  mov     [rdi], rax
0x1800d8a21  call    ??0CBackoffStateManager@@QEAA@XZ; CBackoffStateManager::CBackoffStateManager(void)
0x1800d8a26  mov     [rsi+1C0h], rbx
0x1800d8a2d  mov     rcx, [rsi+1C8h]; this
0x1800d8a34  mov     [rsi+1C8h], rdi
0x1800d8a3b  test    rcx, rcx
0x1800d8a3e  jz      short loc_1800D8A45
0x1800d8a40  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800d8a45  mov     rcx, [rsi+1C0h]
0x1800d8a4c  test    rcx, rcx
0x1800d8a4f  jnz     short loc_1800D8A7C
0x1800d8a51  mov     ebx, 8007000Eh
0x1800d8a56  mov     edx, 0C2h; void *
0x1800d8a5b  mov     r9d, ebx; char *
0x1800d8a5e  mov     rcx, [rbp+78h]; this
0x1800d8a62  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800d8a69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8a6e  lea     rcx, [rbp+70h+var_E0]; this
0x1800d8a72  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800d8a77  jmp     loc_1800D8B64
0x1800d8a7c  mov     rax, [rcx]
0x1800d8a7f  mov     rax, [rax+8]
0x1800d8a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8a88  mov     ebx, eax
0x1800d8a8a  test    eax, eax
0x1800d8a8c  jns     short loc_1800D8A98
0x1800d8a8e  mov     r9d, eax
0x1800d8a91  mov     edx, 0C4h
0x1800d8a96  jmp     short loc_1800D8A5E
0x1800d8a98  lea     rcx, [rsp+170h+Buffer]; lpBuffer
0x1800d8a9d  mov     [rsp+170h+Buffer.dwLength], 38h ; '8'
0x1800d8aa5  call    cs:__imp_GlobalMemoryStatus
0x1800d8aab  mov     r8, [rsp+170h+Buffer.dwAvailPageFile]
0x1800d8ab0  xor     eax, eax
0x1800d8ab2  mov     r9d, [rsi+0C8h]
0x1800d8ab9  shr     r8, 0Ah
0x1800d8abd  cmp     r8, r9
0x1800d8ac0  setb    al
0x1800d8ac3  mov     [rsi+0A4h], eax
0x1800d8ac9  test    cs:byte_1802DA181, 4
0x1800d8ad0  jz      short loc_1800D8ADB
0x1800d8ad2  mov     [rsp+170h+var_150], eax
0x1800d8ad6  call    McTemplateU0qqt_EventWriteTransfer
0x1800d8adb  lea     rdx, [rsi-8]; pv
0x1800d8adf  xor     r8d, r8d; pcbe
0x1800d8ae2  lea     rcx, ?ForceTimerCallback@CBackOffController@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d8ae9  lea     rbx, [rsi+300h]
0x1800d8af0  call    cs:__imp_CreateThreadpoolTimer
0x1800d8af6  mov     rdx, rax
0x1800d8af9  mov     rcx, rbx
0x1800d8afc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800d8b01  cmp     qword ptr [rbx], 0
0x1800d8b05  jnz     short loc_1800D8B23
0x1800d8b07  mov     rcx, [rbp+78h]; this
0x1800d8b0b  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800d8b12  mov     edx, 0CDh; void *
0x1800d8b17  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d8b1c  mov     ebx, eax
0x1800d8b1e  jmp     loc_1800D8A6E
0x1800d8b23  mov     edx, [rsi+0D4h]
0x1800d8b29  lea     rcx, aOverridefullba; "OverrideFullBackOffItemsCountThreshold "...
0x1800d8b30  call    ?Log@ETWLog@@SAXPEB_WZZ; ETWLog::Log(wchar_t const *,...)
0x1800d8b35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix56414827@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix56414827@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827> `wil::Feature<__WilFeatureTraits_Feature_BugFix56414827>::GetImpl(void)'::`2'::impl
0x1800d8b3c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix56414827@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827>::__private_IsEnabled(void)
0x1800d8b41  test    al, al
0x1800d8b43  jz      short loc_1800D8B59
0x1800d8b45  lea     rdx, [rsp+170h+var_140]
0x1800d8b4a  call    ?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix56414827@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix56414827>::GetCachedVariantState(void)
0x1800d8b4f  mov     eax, [rsp+170h+var_13C]
0x1800d8b53  mov     [rsi+1B4h], eax
0x1800d8b59  lea     rcx, [rbp+70h+var_E0]; this
0x1800d8b5d  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x1800d8b62  xor     ebx, ebx
0x1800d8b64  lea     rcx, [rsp+170h+var_138]
0x1800d8b69  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800d8b6e  mov     eax, ebx
0x1800d8b70  mov     rcx, [rbp+70h+var_20]
0x1800d8b74  xor     rcx, rsp; StackCookie
0x1800d8b77  call    __security_check_cookie
0x1800d8b7c  lea     r11, [rsp+170h+var_10]
0x1800d8b84  mov     rbx, [r11+28h]
0x1800d8b88  mov     rsi, [r11+30h]
0x1800d8b8c  mov     rsp, r11
0x1800d8b8f  pop     r15
0x1800d8b91  pop     rdi
0x1800d8b92  pop     rbp
0x1800d8b93  retn
```
