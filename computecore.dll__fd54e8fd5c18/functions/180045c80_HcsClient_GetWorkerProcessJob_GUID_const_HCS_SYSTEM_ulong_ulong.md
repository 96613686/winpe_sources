# HcsClient::GetWorkerProcessJob(_GUID const &,HCS_SYSTEM__ *,ulong,ulong)

- ea: `0x180045c80`
- end: `0x180046136`
- name: `?GetWorkerProcessJob@HcsClient@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBU_GUID@@PEAUHCS_SYSTEM__@@KK@Z`
- size: `1206`
- prototype: `__int64 __usercall@<rax>(PHANDLE JobHandle@<rcx>, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180029a50`

## callees

- `0x1800067c0`
- `0x180009e8c`
- `0x18001017c`
- `0x1800115c4`
- `0x18001587c`
- `0x180020c90`
- `0x180035638`
- `0x180035e7c`
- `0x180037a04`
- `0x1800453bc`
- `0x180045c80`
- `0x180046c50`
- `0x180046dbc`
- `0x18004b114`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045e86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180045e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045f82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045e21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045e65`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045e21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045e65`
- `ntdll!RtlInitUnicodeString` at `0x180045fb5`
- `ntdll!RtlInitUnicodeString` at `0x180045fb5`
- `ntdll!NtOpenJobObject` at `0x180046006`
- `ntdll!NtOpenJobObject` at `0x180046006`

## string_xrefs

- `0x1800460af`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180046018`: `Failed to open job object '%ls'`
- `0x180046027`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x1800460c7`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x1800460e2`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x1800460f4`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x180046106`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`
- `0x180046121`: `onecore\vm\compute\dll\lib\core\vmworkerprocessinternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
PHANDLE __fastcall HcsClient::GetWorkerProcessJob(
        PHANDLE JobHandle,
        __int64 a2,
        __int64 *a3,
        ACCESS_MASK a4,
        unsigned int a5)
{
  ACCESS_MASK v5; // r14d
  __int64 v8; // rax
  __int64 v9; // rbx
  volatile signed __int32 *v10; // rsi
  char v11; // cl
  _QWORD *v12; // r8
  const struct _GUID *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r15
  volatile signed __int32 *v16; // rdi
  ULONGLONG TickCount64; // r13
  DWORD v18; // eax
  HcsClient *v20; // rcx
  struct HCS_SYSTEM__ *v21; // r8
  const char *v22; // r9
  const WCHAR *v23; // rdx
  PCWSTR *v24; // rbx
  unsigned int v25; // eax
  int v27; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v30; // [rsp+40h] [rbp-C0h]
  __int128 v31; // [rsp+50h] [rbp-B0h]
  PHANDLE v32; // [rsp+60h] [rbp-A0h]
  const struct _GUID *v33; // [rsp+68h] [rbp-98h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  HANDLE hHandle; // [rsp+C0h] [rbp-40h] BYREF
  char *v38; // [rsp+C8h] [rbp-38h]
  __int128 v39; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v43[29]; // [rsp+100h] [rbp+0h] BYREF
  int v44; // [rsp+1E8h] [rbp+E8h]
  char v45; // [rsp+458h] [rbp+358h]
  _BYTE v46[16]; // [rsp+460h] [rbp+360h] BYREF
  __int64 v47; // [rsp+470h] [rbp+370h]
  __int64 v48; // [rsp+480h] [rbp+380h]
  _BYTE v49[864]; // [rsp+550h] [rbp+450h] BYREF
  _BYTE v50[16]; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int64 v51; // [rsp+8C0h] [rbp+7C0h]
  char v52; // [rsp+8D0h] [rbp+7D0h]
  wil::details::in1diag3 *retaddr; // [rsp+9F8h] [rbp+8F8h]

  v5 = a4;
  v32 = JobHandle;
  v30 = 0;
  v8 = a3[1];
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
  v9 = *a3;
  *(_QWORD *)&v30 = v9;
  v10 = (volatile signed __int32 *)a3[1];
  *((_QWORD *)&v30 + 1) = v10;
  *(_OWORD *)SourceString = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(SourceString[0]) = 0;
  v29 = a2;
  lambda_80fb9797dfb51f618d68e1d22ff94370_::operator()(&v29, v43, v9);
  if ( !(_BYTE)v48 || (v11 = 0, !v45) )
    v11 = 1;
  if ( v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
      (const char *)0x80070057LL,
      v27);
  if ( !(_BYTE)v48 )
    __fastfail(5u);
  if ( v47 )
  {
    std::wstring::operator=(SourceString, v46);
  }
  else
  {
    if ( v44 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
        (const char *)0x8000FFFFLL,
        v27);
    hHandle = 0;
    LODWORD(v38) = -2147418113;
    v39 = 0;
    v40 = 0;
    v41 = 7;
    LOWORD(v39) = 0;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &hHandle,
      0);
    v12 = v43;
    if ( v43[3] > 7u )
      v12 = (_QWORD *)v43[0];
    v13 = (const struct _GUID *)HcsClient::OpenComputeSystem(a2, v9 + 24, v12, 0x10000000);
    v33 = v13;
    v31 = 0;
    v14 = *(_QWORD *)v13->Data4;
    if ( v14 )
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
    v15 = *(_QWORD *)&v13->Data1;
    *(_QWORD *)&v31 = v15;
    v16 = *(volatile signed __int32 **)v13->Data4;
    *((_QWORD *)&v31 + 1) = v16;
    HcsClient::OperationTracker::SetClientCallback(
      *(HcsClient::OperationTracker **)(v15 + 112),
      HcsEventOptionNone,
      &hHandle,
      lambda_a2d8e03cc03dc09e021f93ab7c667289_::_lambda_invoker_cdecl_);
    TickCount64 = GetTickCount64();
    while ( 1 )
    {
      lambda_80fb9797dfb51f618d68e1d22ff94370_::operator()(&v29, v49, v15);
      if ( !v52 )
        __fastfail(5u);
      if ( v51 )
        break;
      if ( GetTickCount64() - TickCount64 > a5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
          (const char *)0x80070102LL,
          v27);
      v18 = WaitForSingleObject(hHandle, 0xFAu);
      if ( v18 && v18 != 258 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x16D,
          (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
          (const char *)retaddr);
      if ( !v18 )
      {
        if ( (int)v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x173,
            (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
            (const char *)(unsigned int)v38,
            v27);
        if ( v40 )
        {
          std::wstring::operator=(SourceString, &v39);
          Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v49);
          goto LABEL_32;
        }
      }
      Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v49);
    }
    std::wstring::operator=(SourceString, v50);
    Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v49);
LABEL_32:
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    HcsClient::CloseComputeSystem(v20, v13, v21);
    std::wstring::~wstring(&v39);
    if ( hHandle && !CloseHandle(hHandle) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    v5 = a4;
  }
  DestinationString = 0;
  v23 = (const WCHAR *)SourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v23 = SourceString[0];
  RtlInitUnicodeString(&DestinationString, v23);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  v24 = SourceString;
  if ( si128.m128i_i64[1] > 7uLL )
    v24 = (PCWSTR *)SourceString[0];
  *JobHandle = 0;
  v25 = NtOpenJobObject(JobHandle, v5, &ObjectAttributes);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x187,
    (unsigned int)"onecore\\vm\\compute\\dll\\lib\\core\\vmworkerprocessinternal.cpp",
    (const char *)v25,
    (int)"Failed to open job object '%ls'",
    (const char *)v24);
  Schema::Responses::System::Properties::~Properties((Schema::Responses::System::Properties *)v43);
  std::wstring::~wstring(SourceString);
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  return JobHandle;
}

```

## disassembly

```asm
0x180045c80  push    rbp
0x180045c82  push    rbx
0x180045c83  push    rsi
0x180045c84  push    rdi
0x180045c85  push    r12
0x180045c87  push    r13
0x180045c89  push    r14
0x180045c8b  push    r15
0x180045c8d  lea     rbp, [rsp-8B8h]
0x180045c95  sub     rsp, 9B8h
0x180045c9c  mov     rax, cs:__security_cookie
0x180045ca3  xor     rax, rsp
0x180045ca6  mov     [rbp+8F0h+var_50], rax
0x180045cad  mov     r14d, r9d
0x180045cb0  mov     [rsp+9F0h+var_9C0], r9d
0x180045cb5  mov     rdi, rdx
0x180045cb8  mov     r12, rcx
0x180045cbb  mov     [rsp+9F0h+var_990], rcx
0x180045cc0  xor     r15d, r15d
0x180045cc3  mov     [rsp+9F0h+var_9BC], r15d
0x180045cc8  xorps   xmm0, xmm0
0x180045ccb  movups  [rsp+9F0h+var_9B0], xmm0
0x180045cd0  mov     rax, [r8+8]
0x180045cd4  test    rax, rax
0x180045cd7  jz      short loc_180045CDD
0x180045cd9  lock inc dword ptr [rax+8]
0x180045cdd  mov     rbx, [r8]
0x180045ce0  mov     qword ptr [rsp+9F0h+var_9B0], rbx
0x180045ce5  mov     rsi, [r8+8]
0x180045ce9  mov     qword ptr [rsp+9F0h+var_9B0+8], rsi
0x180045cee  movups  xmmword ptr [rbp+8F0h+SourceString], xmm0
0x180045cf2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180045cfa  movdqu  [rbp+8F0h+var_940], xmm1
0x180045cff  mov     word ptr [rbp+8F0h+SourceString], r15w
0x180045d04  mov     [rsp+9F0h+var_9B8], rdi
0x180045d09  mov     r8, rbx
0x180045d0c  lea     rdx, [rbp+8F0h+var_8F0]
0x180045d10  lea     rcx, [rsp+9F0h+var_9B8]
0x180045d15  call    _lambda_80fb9797dfb51f618d68e1d22ff94370___operator__
0x180045d1a  nop
0x180045d1b  mov     rax, [rbp+8F0h+var_570]
0x180045d22  test    al, al
0x180045d24  jz      short loc_180045D32
0x180045d26  cmp     [rbp+8F0h+var_598], r15b
0x180045d2d  mov     cl, r15b
0x180045d30  jnz     short loc_180045D34
0x180045d32  mov     cl, 1
0x180045d34  mov     r10, [rbp+8F8h]
0x180045d3b  test    cl, cl
0x180045d3d  jnz     loc_1800460C1
0x180045d43  mov     ecx, 5
0x180045d48  test    al, al
0x180045d4a  jnz     short loc_180045D4E
0x180045d4c  int     29h; Win8: RtlFailFast(ecx)
0x180045d4e  or      r13d, 0FFFFFFFFh
0x180045d52  cmp     [rbp+8F0h+var_580], r15
0x180045d59  jz      short loc_180045D76
0x180045d5b  test    al, al
0x180045d5d  jnz     short loc_180045D61
0x180045d5f  int     29h; Win8: RtlFailFast(ecx)
0x180045d61  lea     rdx, [rbp+8F0h+var_590]
0x180045d68  lea     rcx, [rbp+8F0h+SourceString]
0x180045d6c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180045d71  jmp     loc_180045F9C
0x180045d76  cmp     [rbp+8F0h+var_808], r15d
0x180045d7d  setnz   al
0x180045d80  mov     rcx, [rbp+8F8h]; this
0x180045d87  test    al, al
0x180045d89  jnz     loc_1800460DC
0x180045d8f  mov     [rbp+8F0h+hHandle], r15
0x180045d93  mov     dword ptr [rbp+8F0h+var_928], 8000FFFFh
0x180045d9a  xorps   xmm0, xmm0
0x180045d9d  movups  [rbp+8F0h+var_920], xmm0
0x180045da1  mov     [rbp+8F0h+var_910], r15
0x180045da5  mov     [rbp+8F0h+var_908], 7
0x180045dad  mov     word ptr [rbp+8F0h+var_920], r15w
0x180045db2  xor     edx, edx
0x180045db4  lea     rcx, [rbp+8F0h+hHandle]
0x180045db8  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180045dbd  lea     r8, [rbp+8F0h+var_8F0]
0x180045dc1  cmp     [rbp+8F0h+var_8D8], 7
0x180045dc6  cmova   r8, [rbp+8F0h+var_8F0]
0x180045dcb  lea     rdx, [rbx+18h]
0x180045dcf  mov     r9d, 10000000h
0x180045dd5  mov     rcx, rdi
0x180045dd8  call    ?OpenComputeSystem@HcsClient@@YAPEAUHCS_SYSTEM__@@AEBU_GUID@@AEBV?$shared_ptr@VHcsServer@@@std@@PEBGK@Z; HcsClient::OpenComputeSystem(_GUID const &,std::shared_ptr<HcsServer> const &,ushort const *,ulong)
0x180045ddd  mov     rbx, rax
0x180045de0  mov     [rsp+9F0h+var_988], rax
0x180045de5  xorps   xmm0, xmm0
0x180045de8  movups  [rsp+9F0h+var_9A0], xmm0
0x180045ded  mov     rax, [rax+8]
0x180045df1  test    rax, rax
0x180045df4  jz      short loc_180045DFA
0x180045df6  lock inc dword ptr [rax+8]
0x180045dfa  mov     r15, [rbx]
0x180045dfd  mov     qword ptr [rsp+9F0h+var_9A0], r15
0x180045e02  mov     rdi, [rbx+8]
0x180045e06  mov     qword ptr [rsp+9F0h+var_9A0+8], rdi
0x180045e0b  lea     r9, _lambda_a2d8e03cc03dc09e021f93ab7c667289____lambda_invoker_cdecl_; void (*)(struct HCS_EVENT *, void *)
0x180045e12  lea     r8, [rbp+8F0h+hHandle]; void *
0x180045e16  xor     edx, edx; enum HCS_EVENT_OPTIONS
0x180045e18  mov     rcx, [r15+70h]; this
0x180045e1c  call    ?SetClientCallback@OperationTracker@HcsClient@@QEAAXW4HCS_EVENT_OPTIONS@@PEBXP6AXPEAUHCS_EVENT@@PEAX@Z@Z; HcsClient::OperationTracker::SetClientCallback(HCS_EVENT_OPTIONS,void const *,void (*)(HCS_EVENT *,void *))
0x180045e21  call    cs:__imp_GetTickCount64
0x180045e27  mov     r13, rax
0x180045e2a  mov     r8, r15
0x180045e2d  lea     rdx, [rbp+8F0h+var_4A0]
0x180045e34  lea     rcx, [rsp+9F0h+var_9B8]
0x180045e39  call    _lambda_80fb9797dfb51f618d68e1d22ff94370___operator__
0x180045e3e  nop
0x180045e3f  mov     dl, [rbp+8F0h+var_120]
0x180045e45  test    dl, dl
0x180045e47  jnz     short loc_180045E50
0x180045e49  mov     ecx, 5
0x180045e4e  int     29h; Win8: RtlFailFast(ecx)
0x180045e50  cmp     [rbp+8F0h+var_130], 0
0x180045e58  jnz     loc_180045EFB
0x180045e5e  mov     r14, [rbp+8F8h]
0x180045e65  call    cs:__imp_GetTickCount64
0x180045e6b  sub     rax, r13
0x180045e6e  mov     ecx, [rbp+8F0h+arg_20]
0x180045e74  cmp     rax, rcx
0x180045e77  ja      loc_18004611B
0x180045e7d  mov     edx, 0FAh; dwMilliseconds
0x180045e82  mov     rcx, [rbp+8F0h+hHandle]; hHandle
0x180045e86  call    cs:__imp_WaitForSingleObject
0x180045e8c  test    eax, eax
0x180045e8e  jz      short loc_180045E9B
0x180045e90  cmp     eax, 102h
0x180045e95  jz      short loc_180045E9B
0x180045e97  mov     cl, 1
0x180045e99  jmp     short loc_180045E9D
0x180045e9b  xor     cl, cl
0x180045e9d  mov     r9, [rbp+8F8h]; char *
0x180045ea4  test    cl, cl
0x180045ea6  jnz     loc_180046106
0x180045eac  test    eax, eax
0x180045eae  jnz     short loc_180045ECB
0x180045eb0  mov     r9d, dword ptr [rbp+8F0h+var_928]; char *
0x180045eb4  mov     rcx, [rbp+8F8h]; this
0x180045ebb  test    r9d, r9d
0x180045ebe  js      loc_1800460F4
0x180045ec4  cmp     [rbp+8F0h+var_910], 0
0x180045ec9  jnz     short loc_180045EDC
0x180045ecb  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180045ed2  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180045ed7  jmp     loc_180045E2A
0x180045edc  lea     rdx, [rbp+8F0h+var_920]
0x180045ee0  lea     rcx, [rbp+8F0h+SourceString]
0x180045ee4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180045ee9  nop
0x180045eea  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180045ef1  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180045ef6  xor     r15d, r15d
0x180045ef9  jmp     short loc_180045F26
0x180045efb  xor     r15d, r15d
0x180045efe  test    dl, dl
0x180045f00  jnz     short loc_180045F08
0x180045f02  lea     ecx, [r15+5]
0x180045f06  int     29h; Win8: RtlFailFast(ecx)
0x180045f08  lea     rdx, [rbp+8F0h+var_140]
0x180045f0f  lea     rcx, [rbp+8F0h+SourceString]
0x180045f13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180045f18  nop
0x180045f19  lea     rcx, [rbp+8F0h+var_4A0]; this
0x180045f20  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180045f25  nop
0x180045f26  or      r13d, 0FFFFFFFFh
0x180045f2a  test    rdi, rdi
0x180045f2d  jz      short loc_180045F67
0x180045f2f  mov     eax, r13d
0x180045f32  lock xadd [rdi+8], eax
0x180045f37  add     eax, r13d
0x180045f3a  jnz     short loc_180045F67
0x180045f3c  mov     rax, [rdi]
0x180045f3f  mov     rcx, rdi
0x180045f42  mov     rax, [rax]
0x180045f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f4a  mov     eax, r13d
0x180045f4d  lock xadd [rdi+0Ch], eax
0x180045f52  add     eax, r13d
0x180045f55  jnz     short loc_180045F67
0x180045f57  mov     rax, [rdi]
0x180045f5a  mov     rcx, rdi
0x180045f5d  mov     rax, [rax+8]
0x180045f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045f66  nop
0x180045f67  mov     rdx, rbx; struct _GUID *
0x180045f6a  call    ?CloseComputeSystem@HcsClient@@YAXAEBU_GUID@@PEAUHCS_SYSTEM__@@@Z; HcsClient::CloseComputeSystem(_GUID const &,HCS_SYSTEM__ *)
0x180045f6f  nop
0x180045f70  lea     rcx, [rbp+8F0h+var_920]
0x180045f74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045f79  mov     rcx, [rbp+8F0h+hHandle]; hObject
0x180045f7d  test    rcx, rcx
0x180045f80  jz      short loc_180045F97
0x180045f82  call    cs:__imp_CloseHandle
0x180045f88  mov     rcx, [rbp+8F8h]; this
0x180045f8f  test    eax, eax
0x180045f91  jz      loc_1800460AF
0x180045f97  mov     r14d, [rsp+9F0h+var_9C0]
0x180045f9c  xorps   xmm0, xmm0
0x180045f9f  movups  xmmword ptr [rbp+8F0h+DestinationString.Length], xmm0
0x180045fa3  lea     rdx, [rbp+8F0h+SourceString]
0x180045fa7  cmp     qword ptr [rbp+8F0h+var_940+8], 7
0x180045fac  cmova   rdx, [rbp+8F0h+SourceString]; SourceString
0x180045fb1  lea     rcx, [rbp+8F0h+DestinationString]; DestinationString
0x180045fb5  call    cs:__imp_RtlInitUnicodeString
0x180045fbb  mov     qword ptr [rsp+9F0h+ObjectAttributes.Length], 30h ; '0'
0x180045fc4  mov     qword ptr [rbp+8F0h+ObjectAttributes.Attributes], 0
0x180045fcc  mov     [rsp+9F0h+ObjectAttributes.RootDirectory], r15
0x180045fd1  lea     rax, [rbp+8F0h+DestinationString]
0x180045fd5  mov     [rbp+8F0h+ObjectAttributes.ObjectName], rax
0x180045fd9  xorps   xmm0, xmm0
0x180045fdc  movdqu  xmmword ptr [rbp+8F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180045fe1  mov     [rsp+9F0h+var_9BC], 1
0x180045fe9  lea     rbx, [rbp+8F0h+SourceString]
0x180045fed  cmp     qword ptr [rbp+8F0h+var_940+8], 7
0x180045ff2  cmova   rbx, [rbp+8F0h+SourceString]
0x180045ff7  mov     [r12], r15
0x180045ffb  lea     r8, [rsp+9F0h+ObjectAttributes]; ObjectAttributes
0x180046000  mov     edx, r14d; DesiredAccess
0x180046003  mov     rcx, r12; JobHandle
0x180046006  call    cs:__imp_NtOpenJobObject
0x18004600c  mov     rcx, [rbp+8F8h]; this
0x180046013  mov     [rsp+9F0h+var_9C8], rbx; char *
0x180046018  lea     rdx, aFailedToOpenJo; "Failed to open job object '%ls'"
0x18004601f  mov     qword ptr [rsp+9F0h+var_9D0], rdx; int
0x180046024  mov     r9d, eax; char *
0x180046027  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18004602e  mov     edx, 187h; void *
0x180046033  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180046038  nop
0x180046039  lea     rcx, [rbp+8F0h+var_8F0]; this
0x18004603d  call    ??1Properties@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::Properties::~Properties(void)
0x180046042  nop
0x180046043  lea     rcx, [rbp+8F0h+SourceString]
0x180046047  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004604c  nop
0x18004604d  test    rsi, rsi
0x180046050  jz      short loc_180046089
0x180046052  mov     eax, r13d
0x180046055  lock xadd [rsi+8], eax
0x18004605a  add     eax, r13d
0x18004605d  jnz     short loc_180046089
0x18004605f  mov     rax, [rsi]
0x180046062  mov     rcx, rsi
0x180046065  mov     rax, [rax]
0x180046068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004606d  mov     edx, r13d
0x180046070  lock xadd [rsi+0Ch], edx
0x180046075  add     edx, r13d
0x180046078  jnz     short loc_180046089
0x18004607a  mov     rdx, [rsi]
0x18004607d  mov     rcx, rsi
0x180046080  mov     rax, [rdx+8]
0x180046084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046089  mov     rax, r12
0x18004608c  mov     rcx, [rbp+8F0h+var_50]
0x180046093  xor     rcx, rsp; StackCookie
0x180046096  call    __security_check_cookie
0x18004609b  add     rsp, 9B8h
0x1800460a2  pop     r15
0x1800460a4  pop     r14
0x1800460a6  pop     r13
0x1800460a8  pop     r12
0x1800460aa  pop     rdi
0x1800460ab  pop     rsi
0x1800460ac  pop     rbx
0x1800460ad  pop     rbp
0x1800460ae  retn
0x1800460af  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800460b6  mov     edx, 0A0Bh; void *
0x1800460bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800460c1  mov     r9d, 80070057h; char *
0x1800460c7  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x1800460ce  mov     edx, 118h; void *
0x1800460d3  mov     rcx, r10; this
0x1800460d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800460dc  mov     r9d, 8000FFFFh; char *
0x1800460e2  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x1800460e9  mov     edx, 126h; void *
0x1800460ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800460f4  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x1800460fb  mov     edx, 173h; void *
0x180046100  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180046106  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x18004610d  mov     edx, 16Dh; void *
0x180046112  mov     rcx, r9; this
0x180046115  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004611b  mov     r9d, 80070102h; char *
0x180046121  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\dll\\lib\\core\\v"...
0x180046128  mov     edx, 16Ah; void *
0x18004612d  mov     rcx, r14; this
0x180046130  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
