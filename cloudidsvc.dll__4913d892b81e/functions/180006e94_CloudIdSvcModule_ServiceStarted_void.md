# CloudIdSvcModule::ServiceStarted(void)

- ea: `0x180006e94`
- end: `0x180006f73`
- name: `?ServiceStarted@CloudIdSvcModule@@QEAAJXZ`
- size: `223`
- prototype: `__int64 __fastcall(CloudIdSvcModule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004820`

## callees

- `0x180001a50`
- `0x180003e84`
- `0x180004518`
- `0x180006d14`
- `0x180006e94`
- `0x180008570`
- `0x18000b080`

## string_xrefs

- `0x180006eb9`: `ServiceStart`
- `0x180006eec`: `onecoreuap\ds\ext\common\ntservice\svc\cloudidsvc.cpp`

## pseudocode

```c
__int64 __fastcall CloudIdSvcModule::ServiceStarted(CloudIdSvcModule *this)
{
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // ebx
  _BYTE v7[244]; // [rsp+40h] [rbp-138h] BYREF
  int v8; // [rsp+134h] [rbp-44h]
  _BYTE v9[16]; // [rsp+150h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  wil::g_fResultFailFastUnknownExceptions = 0;
  TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(
    (TenantRestrictionsLoggers::AutoMeasureLogger *)v7,
    "ServiceStart");
  g_SvcStatusHandle = (struct SERVICE_STATUS_HANDLE__ *)*((_QWORD *)this + 1);
  v2 = InitializeTenantRestrictionsUpdates();
  v5 = v2;
  if ( v2 >= 0 )
  {
    if ( (Microsoft_Windows_TenantRestrictionsEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v3, ServiceStartSuccess, v4, 1, v9);
    v7[240] = 1;
    v8 = 0;
    TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (int)"onecoreuap\\ds\\ext\\common\\ntservice\\svc\\cloudidsvc.cpp",
      (const char *)(unsigned int)v2);
    TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger((TenantRestrictionsLoggers::AutoMeasureLogger *)v7);
    return v5;
  }
}

```

## disassembly

```asm
0x180006e94  push    rbx
0x180006e96  sub     rsp, 170h
0x180006e9d  mov     rax, cs:__security_cookie
0x180006ea4  xor     rax, rsp
0x180006ea7  mov     [rsp+178h+var_18], rax
0x180006eaf  mov     rbx, rcx
0x180006eb2  mov     cs:?g_fResultFailFastUnknownExceptions@wil@@3_NA, 0; bool wil::g_fResultFailFastUnknownExceptions
0x180006eb9  lea     rdx, aServicestart; "ServiceStart"
0x180006ec0  lea     rcx, [rsp+178h+var_138]; this
0x180006ec5  call    ??0AutoMeasureLogger@TenantRestrictionsLoggers@@QEAA@PEBD@Z; TenantRestrictionsLoggers::AutoMeasureLogger::AutoMeasureLogger(char const *)
0x180006eca  nop
0x180006ecb  mov     rax, [rbx+8]
0x180006ecf  mov     cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x180006ed6  call    ?InitializeTenantRestrictionsUpdates@@YAJXZ; InitializeTenantRestrictionsUpdates(void)
0x180006edb  mov     ebx, eax
0x180006edd  test    eax, eax
0x180006edf  jns     short loc_180006F0C
0x180006ee1  mov     rcx, [rsp+178h]; this
0x180006ee9  mov     r9d, eax; char *
0x180006eec  lea     r8, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x180006ef3  mov     edx, 32h ; '2'; void *
0x180006ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006efd  nop
0x180006efe  lea     rcx, [rsp+178h+var_138]; this
0x180006f03  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x180006f08  mov     eax, ebx
0x180006f0a  jmp     short loc_180006F59
0x180006f0c  test    cs:Microsoft_Windows_TenantRestrictionsEnableBits, 4
0x180006f13  jz      short loc_180006F34
0x180006f15  lea     rax, [rsp+178h+var_28]
0x180006f1d  mov     [rsp+178h+var_158], rax
0x180006f22  mov     r9d, 1
0x180006f28  lea     rdx, ServiceStartSuccess
0x180006f2f  call    McGenEventWrite_EventWriteTransfer
0x180006f34  mov     [rsp+178h+var_48], 1
0x180006f3c  mov     [rsp+178h+var_44], 0
0x180006f47  lea     rcx, [rsp+178h+var_138]; this
0x180006f4c  call    ??1AutoMeasureLogger@TenantRestrictionsLoggers@@UEAA@XZ; TenantRestrictionsLoggers::AutoMeasureLogger::~AutoMeasureLogger(void)
0x180006f51  xor     eax, eax
0x180006f53  jmp     short loc_180006F59
0x180006f55  mov     eax, [rsp+178h+var_148]
0x180006f59  mov     rcx, [rsp+178h+var_18]
0x180006f61  xor     rcx, rsp; StackCookie
0x180006f64  call    __security_check_cookie
0x180006f69  add     rsp, 170h
0x180006f70  pop     rbx
0x180006f71  retn
```
