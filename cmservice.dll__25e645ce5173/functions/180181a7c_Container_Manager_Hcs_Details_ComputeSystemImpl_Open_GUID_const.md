# Container::Manager::Hcs::Details::ComputeSystemImpl::Open(_GUID const &)

- ea: `0x180181a7c`
- end: `0x180181e6f`
- name: `?Open@ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAAXAEBU_GUID@@@Z`
- size: `1011`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemImpl *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180123b78`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b3c`
- `0x18002c5b4`
- `0x18003d4dc`
- `0x18003de70`
- `0x1800491e8`
- `0x180049230`
- `0x1801260f0`
- `0x180177958`
- `0x18017e544`
- `0x18017eeb0`
- `0x180181a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180181c2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180181c2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180181cd9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180181cd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180181c93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180181c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180181cb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180181cb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181cfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180181cfa`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenComputeSystem` at `0x180181aff`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenComputeSystem` at `0x180181aff`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetComputeSystemProperties` at `0x180181b52`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetComputeSystemProperties` at `0x180181b52`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x180181c51`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetComputeSystemCallback` at `0x180181c51`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181ca4`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181d21`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181ca4`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x180181d21`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180181b23`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180181b23`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180181d0a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x180181d0a`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResult` at `0x180181b7d`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResult` at `0x180181b7d`

## string_xrefs

- `0x180181d77`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181d9d`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181db2`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181dd5`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181de7`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181dfc`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181e11`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181e37`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`
- `0x180181e5d`: `onecore\base\gendrv\silos\clem\compute\lib\computesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::Open(RTL_SRWLOCK *this, const struct _GUID *a2)
{
  int v4; // eax
  HRESULT v5; // eax
  HCS_OPERATION Operation; // rax
  const char *v7; // r9
  HCS_OPERATION v8; // rbx
  HRESULT ComputeSystemProperties; // eax
  HRESULT v10; // eax
  __int64 v11; // rax
  bool v12; // di
  int v13; // edi
  HRESULT v14; // eax
  HCS_SYSTEM *v15; // rsi
  HCS_SYSTEM v16; // r13
  HCS_SYSTEM v17; // r12
  DWORD LastError; // edi
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  HCS_SYSTEM computeSystem; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR resultDocument; // [rsp+28h] [rbp-D8h] BYREF
  PCWSTR id[2]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v26[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[3]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[32]; // [rsp+F0h] [rbp-10h] BYREF
  int v34; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+488h]

  id[0] = v26;
  id[1] = v26;
  v26[0] = 0;
  v4 = Csl::GuidToString(a2, id);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v4,
      (int)computeSystem);
  computeSystem = 0;
  v5 = HcsOpenComputeSystem(id[0], 0x10000000u, &computeSystem);
  if ( v5 < 0 )
  {
    if ( v5 != -2143878896 )
    {
      v20 = wil::verify_hresult<long>((unsigned int)v5);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)v20,
        (int)computeSystem);
    }
    v19 = wil::verify_hresult<long>(2151088390LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)v19,
      (int)computeSystem);
  }
  Operation = HcsCreateOperation(0, 0);
  v8 = Operation;
  v27[2] = Operation;
  if ( !Operation )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      v7);
  ComputeSystemProperties = HcsGetComputeSystemProperties(computeSystem, Operation, 0);
  if ( ComputeSystemProperties < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)ComputeSystemProperties,
      (int)computeSystem);
  resultDocument = 0;
  v10 = HcsWaitForOperationResult(v8, 0xFFFFFFFF, &resultDocument);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v10,
      (int)computeSystem);
  Schema::Responses::System::Properties::Properties((Schema::Responses::System::Properties *)v33);
  v11 = -1;
  do
    ++v11;
  while ( resultDocument[v11] );
  v27[0] = resultDocument;
  v27[1] = v11;
  Marshal::JsonParser::JsonParser(v30, v27);
  Marshal::FromJson<Schema::Responses::System::Properties,>(v28, v30, v33);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v31);
  v12 = v28[0] == 0;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(v29);
  if ( v12 )
  {
    v21 = wil::verify_hresult<long>(2151088397LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)v21,
      (int)computeSystem);
  }
  if ( v34 )
  {
    if ( v34 != 1 )
    {
      v22 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
        (const char *)v22,
        (int)computeSystem);
    }
    v13 = 1;
  }
  else
  {
    v13 = 2;
  }
  AcquireSRWLockExclusive(this + 4);
  v27[0] = this + 4;
  v14 = HcsSetComputeSystemCallback(
          computeSystem,
          HcsEventOptionNone,
          this,
          Container::Manager::Hcs::Details::ComputeSystemImpl::OnComputeSystemEvent);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x175,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystem.cpp",
      (const char *)(unsigned int)v14,
      (int)computeSystem);
  *(struct _GUID *)&this->Ptr = *a2;
  LODWORD(this[2].Ptr) = v13;
  v15 = (HCS_SYSTEM *)&this[3];
  if ( &this[3] != (RTL_SRWLOCK *)&computeSystem )
  {
    v16 = computeSystem;
    v17 = *v15;
    if ( *v15 )
    {
      LastError = GetLastError();
      HcsCloseComputeSystem(v17);
      SetLastError(LastError);
    }
    *v15 = v16;
    computeSystem = 0;
  }
  LODWORD(this[5].Ptr) = 1;
  if ( this != (RTL_SRWLOCK *)-32LL )
    ReleaseSRWLockExclusive(this + 4);
  Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v33);
  if ( resultDocument )
    LocalFree(resultDocument);
  HcsCloseOperation(v8);
  if ( computeSystem )
    HcsCloseComputeSystem(computeSystem);
  if ( id[0] != v26 )
    operator delete((void *)id[0], (const struct std::nothrow_t *)&std::nothrow);
}

```

## disassembly

```asm
0x180181a7c  mov     [rsp-8+arg_10], rbx
0x180181a81  push    rbp
0x180181a82  push    rsi
0x180181a83  push    rdi
0x180181a84  push    r12
0x180181a86  push    r13
0x180181a88  push    r14
0x180181a8a  push    r15
0x180181a8c  lea     rbp, [rsp-450h]
0x180181a94  sub     rsp, 550h
0x180181a9b  mov     rax, cs:__security_cookie
0x180181aa2  xor     rax, rsp
0x180181aa5  mov     [rbp+480h+var_40], rax
0x180181aac  mov     rsi, rdx
0x180181aaf  mov     r14, rcx
0x180181ab2  xor     r12d, r12d
0x180181ab5  lea     rax, [rsp+580h+var_540]
0x180181aba  mov     [rsp+580h+id], rax
0x180181abf  lea     rax, [rsp+580h+var_540]
0x180181ac4  mov     [rsp+580h+var_548], rax
0x180181ac9  mov     [rsp+580h+var_540], r12w
0x180181acf  lea     rdx, [rsp+580h+id]
0x180181ad4  mov     rcx, rsi
0x180181ad7  call    ?GuidToString@Csl@@YAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::GuidToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180181adc  mov     rcx, [rbp+488h]; this
0x180181ae3  test    eax, eax
0x180181ae5  js      loc_180181DAF
0x180181aeb  mov     [rsp+580h+computeSystem], r12; int
0x180181af0  lea     r8, [rsp+580h+computeSystem]; computeSystem
0x180181af5  mov     edx, 10000000h; requestedAccess
0x180181afa  mov     rcx, [rsp+580h+id]; id
0x180181aff  call    cs:__imp_HcsOpenComputeSystem
0x180181b06  nop     dword ptr [rax+rax+00h]
0x180181b0b  test    eax, eax
0x180181b0d  jns     short loc_180181B1F
0x180181b0f  cmp     eax, 80370110h
0x180181b14  jz      loc_180181D89
0x180181b1a  jmp     loc_180181DC4
0x180181b1f  xor     edx, edx; callback
0x180181b21  xor     ecx, ecx; context
0x180181b23  call    cs:__imp_HcsCreateOperation
0x180181b2a  nop     dword ptr [rax+rax+00h]
0x180181b2f  mov     rbx, rax
0x180181b32  mov     [rsp+580h+var_520], rax
0x180181b37  mov     rcx, [rbp+488h]; this
0x180181b3e  test    rax, rax
0x180181b41  jz      loc_180181DE7
0x180181b47  xor     r8d, r8d; propertyQuery
0x180181b4a  mov     rdx, rax; operation
0x180181b4d  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181b52  call    cs:__imp_HcsGetComputeSystemProperties
0x180181b59  nop     dword ptr [rax+rax+00h]
0x180181b5e  mov     rcx, [rbp+488h]; this
0x180181b65  test    eax, eax
0x180181b67  js      loc_180181DF9
0x180181b6d  mov     [rsp+580h+resultDocument], r12
0x180181b72  lea     r8, [rsp+580h+resultDocument]; resultDocument
0x180181b77  or      edx, 0FFFFFFFFh; timeoutMs
0x180181b7a  mov     rcx, rbx; operation
0x180181b7d  call    cs:__imp_HcsWaitForOperationResult
0x180181b84  nop     dword ptr [rax+rax+00h]
0x180181b89  mov     rcx, [rbp+488h]; this
0x180181b90  test    eax, eax
0x180181b92  js      loc_180181E0E
0x180181b98  lea     rcx, [rbp+480h+var_490]; this
0x180181b9c  call    ??0Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::Properties(void)
0x180181ba1  nop
0x180181ba2  mov     rcx, [rsp+580h+resultDocument]
0x180181ba7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180181bab  inc     rax
0x180181bae  cmp     [rcx+rax*2], r12w
0x180181bb3  jnz     short loc_180181BAB
0x180181bb5  mov     [rsp+580h+var_530], rcx
0x180181bba  mov     [rsp+580h+var_528], rax
0x180181bbf  lea     rdx, [rsp+580h+var_530]
0x180181bc4  lea     rcx, [rbp+480h+var_4F0]
0x180181bc8  call    ??0JsonParser@Marshal@@QEAA@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; Marshal::JsonParser::JsonParser(std::basic_string_view<ushort>)
0x180181bcd  nop
0x180181bce  lea     r8, [rbp+480h+var_490]
0x180181bd2  lea     rdx, [rbp+480h+var_4F0]
0x180181bd6  lea     rcx, [rsp+580h+var_518]
0x180181bdb  call    ??$FromJson@UProperties@System@Responses@Schema@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEAVJsonParser@0@PEAUProperties@System@Responses@Schema@@W4UnmarshalFlags@0@@Z; Marshal::FromJson<Schema::Responses::System::Properties,>(Marshal::JsonParser &,Schema::Responses::System::Properties *,Marshal::UnmarshalFlags)
0x180181be0  nop
0x180181be1  lea     rcx, [rbp+480h+var_4B0]; void *
0x180181be5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181bea  lea     rcx, [rbp+480h+var_4D0]; void *
0x180181bee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181bf3  cmp     [rsp+580h+var_518], r12b
0x180181bf8  setz    dil
0x180181bfc  lea     rcx, [rsp+580h+var_510]
0x180181c01  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x180181c06  test    dil, dil
0x180181c09  jnz     loc_180181E23
0x180181c0f  mov     ecx, [rbp+480h+var_470]
0x180181c12  test    ecx, ecx
0x180181c14  jz      short loc_180181C23
0x180181c16  cmp     ecx, 1
0x180181c19  jnz     loc_180181E49
0x180181c1f  mov     edi, ecx
0x180181c21  jmp     short loc_180181C28
0x180181c23  mov     edi, 2
0x180181c28  lea     r15, [r14+20h]
0x180181c2c  mov     rcx, r15; SRWLock
0x180181c2f  call    cs:__imp_AcquireSRWLockExclusive
0x180181c36  nop     dword ptr [rax+rax+00h]
0x180181c3b  mov     [rsp+580h+var_530], r15
0x180181c40  lea     r9, ?OnComputeSystemEvent@ComputeSystemImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x180181c47  mov     r8, r14; context
0x180181c4a  xor     edx, edx; callbackOptions
0x180181c4c  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181c51  call    cs:__imp_HcsSetComputeSystemCallback
0x180181c58  nop     dword ptr [rax+rax+00h]
0x180181c5d  mov     rcx, [rbp+488h]; this
0x180181c64  test    eax, eax
0x180181c66  js      loc_180181D74
0x180181c6c  movups  xmm0, xmmword ptr [rsi]
0x180181c6f  movdqu  xmmword ptr [r14], xmm0
0x180181c74  mov     [r14+10h], edi
0x180181c78  lea     rsi, [r14+18h]
0x180181c7c  lea     rax, [rsp+580h+computeSystem]
0x180181c81  cmp     rsi, rax
0x180181c84  jz      short loc_180181CC9
0x180181c86  mov     r13, [rsp+580h+computeSystem]
0x180181c8b  mov     r12, [rsi]
0x180181c8e  test    r12, r12
0x180181c91  jz      short loc_180181CBE
0x180181c93  call    cs:__imp_GetLastError
0x180181c9a  nop     dword ptr [rax+rax+00h]
0x180181c9f  mov     edi, eax
0x180181ca1  mov     rcx, r12; computeSystem
0x180181ca4  call    cs:__imp_HcsCloseComputeSystem
0x180181cab  nop     dword ptr [rax+rax+00h]
0x180181cb0  mov     ecx, edi; dwErrCode
0x180181cb2  call    cs:__imp_SetLastError
0x180181cb9  nop     dword ptr [rax+rax+00h]
0x180181cbe  mov     [rsi], r13
0x180181cc1  xor     r12d, r12d
0x180181cc4  mov     [rsp+580h+computeSystem], r12
0x180181cc9  mov     dword ptr [r14+28h], 1
0x180181cd1  test    r15, r15
0x180181cd4  jz      short loc_180181CE6
0x180181cd6  mov     rcx, r15; SRWLock
0x180181cd9  call    cs:__imp_ReleaseSRWLockExclusive
0x180181ce0  nop     dword ptr [rax+rax+00h]
0x180181ce5  nop
0x180181ce6  lea     rcx, [rbp+480h+var_490]; this
0x180181cea  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180181cef  nop
0x180181cf0  mov     rcx, [rsp+580h+resultDocument]; hMem
0x180181cf5  test    rcx, rcx
0x180181cf8  jz      short loc_180181D07
0x180181cfa  call    cs:__imp_LocalFree
0x180181d01  nop     dword ptr [rax+rax+00h]
0x180181d06  nop
0x180181d07  mov     rcx, rbx; operation
0x180181d0a  call    cs:__imp_HcsCloseOperation
0x180181d11  nop     dword ptr [rax+rax+00h]
0x180181d16  nop
0x180181d17  mov     rcx, [rsp+580h+computeSystem]; computeSystem
0x180181d1c  test    rcx, rcx
0x180181d1f  jz      short loc_180181D2E
0x180181d21  call    cs:__imp_HcsCloseComputeSystem
0x180181d28  nop     dword ptr [rax+rax+00h]
0x180181d2d  nop
0x180181d2e  lea     rax, [rsp+580h+var_540]
0x180181d33  mov     rcx, [rsp+580h+id]; void *
0x180181d38  cmp     rcx, rax
0x180181d3b  jz      short loc_180181D49
0x180181d3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180181d44  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180181d49  mov     rcx, [rbp+480h+var_40]
0x180181d50  xor     rcx, rsp; StackCookie
0x180181d53  call    __security_check_cookie
0x180181d58  mov     rbx, [rsp+580h+arg_10]
0x180181d60  add     rsp, 550h
0x180181d67  pop     r15
0x180181d69  pop     r14
0x180181d6b  pop     r13
0x180181d6d  pop     r12
0x180181d6f  pop     rdi
0x180181d70  pop     rsi
0x180181d71  pop     rbp
0x180181d72  retn
0x180181d74  mov     r9d, eax; char *
0x180181d77  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181d7e  mov     edx, 175h; void *
0x180181d83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181d89  mov     ecx, 80370106h
0x180181d8e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181d93  mov     r9d, eax; char *
0x180181d96  mov     rcx, [rbp+488h]; this
0x180181d9d  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181da4  mov     edx, 13Ah; void *
0x180181da9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181daf  mov     r9d, eax; char *
0x180181db2  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181db9  mov     edx, 12Dh; void *
0x180181dbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181dc4  mov     ecx, eax
0x180181dc6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181dcb  mov     r9d, eax; char *
0x180181dce  mov     rcx, [rbp+488h]; this
0x180181dd5  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181ddc  mov     edx, 13Eh; void *
0x180181de1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181de7  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181dee  mov     edx, 144h; void *
0x180181df3  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180181df9  mov     r9d, eax; char *
0x180181dfc  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181e03  mov     edx, 148h; void *
0x180181e08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181e0e  mov     r9d, eax; char *
0x180181e11  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181e18  mov     edx, 14Bh; void *
0x180181e1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181e23  mov     ecx, 8037010Dh
0x180181e28  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181e2d  mov     r9d, eax; char *
0x180181e30  mov     rcx, [rbp+488h]; this
0x180181e37  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181e3e  mov     edx, 150h; void *
0x180181e43  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180181e49  mov     ecx, 8000FFFFh
0x180181e4e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180181e53  mov     r9d, eax; char *
0x180181e56  mov     rcx, [rbp+488h]; this
0x180181e5d  lea     r8, aOnecoreBaseGen_50; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180181e64  mov     edx, 168h; void *
0x180181e69  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
