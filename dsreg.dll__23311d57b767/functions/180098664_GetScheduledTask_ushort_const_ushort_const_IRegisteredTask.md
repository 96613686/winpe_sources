# GetScheduledTask(ushort const *,ushort const *,IRegisteredTask * *)

- ea: `0x180098664`
- end: `0x180098939`
- name: `?GetScheduledTask@@YAJPEBG0PEAPEAUIRegisteredTask@@@Z`
- size: `725`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033984`
- `0x180098b54`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x1800307c4`
- `0x18003334c`
- `0x180098664`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180098753`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180098753`
- `OLEAUT32!__imp_SysAllocString` at `0x1800987f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18009884a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800987f3`
- `OLEAUT32!__imp_SysAllocString` at `0x18009884a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800988bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800988c4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800988bb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800988c4`
- `OLEAUT32!__imp_VariantInit` at `0x180098730`
- `OLEAUT32!__imp_VariantInit` at `0x180098730`

## string_xrefs

- `0x1800986a6`: `GetScheduledTask`
- `0x180098705`: `registeredTask`
- `0x180098720`: `registeredTask`
- `0x1800986d1`: `taskName`
- `0x1800986ec`: `taskName`
- `0x1800987ce`: `ITaskService::Connect`
- `0x180098762`: `%s: CoCreateInstance failed with error 0x%08x. Failed to create an instance of the TaskService class.`
- `0x180098878`: `%s: ITaskFolder::GetTask("%s") failed with error 0x%08x.`
- `0x18009883e`: `%s: ITaskService::GetFolder("%s") failed with error 0x%08x.`
- `0x18009889a`: `%s: Task "%s\%s" not found. ITaskFolder::GetTask returns NULL pointer.`

## pseudocode

```c
__int64 __fastcall GetScheduledTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IRegisteredTask **a3)
{
  OLECHAR *v5; // rsi
  OLECHAR *v6; // r14
  unsigned int v7; // ebx
  const unsigned __int16 *v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rax
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  int v12; // eax
  BSTR v13; // rax
  int v14; // eax
  BSTR v15; // rax
  int v16; // eax
  __int64 v18; // [rsp+38h] [rbp-69h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-61h] BYREF
  __int128 v20; // [rsp+58h] [rbp-49h] BYREF
  IRecordInfo *pRecInfo; // [rsp+68h] [rbp-39h]
  VARIANTARG v22; // [rsp+78h] [rbp-29h] BYREF
  VARIANTARG v23; // [rsp+98h] [rbp-9h] BYREF
  VARIANTARG v24; // [rsp+B8h] [rbp+17h] BYREF
  struct IRegisteredTask *v25; // [rsp+108h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+120h] [rbp+7Fh] BYREF

  ppv = 0;
  v18 = 0;
  v25 = 0;
  v5 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"GetScheduledTask");
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetScheduledTask", L"taskName");
    v8 = L"taskName";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetScheduledTask", v8);
    goto LABEL_21;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetScheduledTask", L"registeredTask");
    v8 = L"registeredTask";
    goto LABEL_3;
  }
  *a3 = 0;
  VariantInit(&pvarg);
  v9 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v7 = v9;
  if ( v9 < 0 )
  {
    Logger::TraceError(
      L"%s: CoCreateInstance failed with error 0x%08x. Failed to create an instance of the TaskService class.",
      L"GetScheduledTask",
      (unsigned int)v9);
    goto LABEL_21;
  }
  v20 = *(_OWORD *)&pvarg.vt;
  v10 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v22 = pvarg;
  v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v10 + 80);
  v23 = pvarg;
  v24 = pvarg;
  v12 = v11(ppv, &v24, &v23, &v22, &v20);
  v7 = v12;
  if ( v12 >= 0 )
  {
    v13 = SysAllocString(L"\\Microsoft\\Windows\\Workplace Join");
    v5 = v13;
    if ( !v13 )
      goto LABEL_12;
    v14 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v13, &v18);
    v7 = v14;
    if ( v14 < 0 )
    {
      Logger::TraceError(
        L"%s: ITaskService::GetFolder(\"%s\") failed with error 0x%08x.",
        L"GetScheduledTask",
        L"\\Microsoft\\Windows\\Workplace Join",
        (unsigned int)v14);
      goto LABEL_21;
    }
    v15 = SysAllocString(a2);
    v6 = v15;
    if ( !v15 )
    {
LABEL_12:
      v7 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"GetScheduledTask");
      goto LABEL_21;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, BSTR, struct IRegisteredTask **))(*(_QWORD *)v18 + 104LL))(v18, v15, &v25);
    v7 = v16;
    if ( v16 >= 0 )
    {
      if ( v25 )
      {
        *a3 = v25;
        v25 = 0;
      }
      else
      {
        Logger::TraceError(
          L"%s: Task \"%s\\%s\" not found. ITaskFolder::GetTask returns NULL pointer.",
          L"GetScheduledTask",
          L"\\Microsoft\\Windows\\Workplace Join",
          a2);
        v7 = -2147024894;
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: ITaskFolder::GetTask(\"%s\") failed with error 0x%08x.",
        L"GetScheduledTask",
        a2,
        (unsigned int)v16);
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"GetScheduledTask",
      L"ITaskService::Connect",
      (unsigned int)v12);
  }
LABEL_21:
  SysFreeString(v5);
  SysFreeString(v6);
  if ( v25 )
    ((void (__fastcall *)(struct IRegisteredTask *))v25->lpVtbl->Release)(v25);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetScheduledTask", v7);
  return v7;
}

```

## disassembly

```asm
0x180098664  mov     rax, rsp
0x180098667  mov     [rax+10h], rbx
0x18009866b  mov     [rax+18h], rsi
0x18009866f  mov     [rax+8], rcx
0x180098673  push    rbp
0x180098674  push    rdi
0x180098675  push    r13
0x180098677  push    r14
0x180098679  push    r15
0x18009867b  lea     rbp, [rax-5Fh]
0x18009867f  sub     rsp, 0D0h
0x180098686  mov     rdi, rdx
0x180098689  mov     [rbp+57h+arg_18], 0
0x180098691  xorps   xmm0, xmm0
0x180098694  mov     [rbp+57h+var_C0], 0
0x18009869c  xor     eax, eax
0x18009869e  mov     [rbp+57h+arg_0], 0
0x1800986a6  lea     r13, aGetscheduledta; "GetScheduledTask"
0x1800986ad  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800986b1  mov     rdx, r13
0x1800986b4  lea     rcx, aSStarted; "%s started"
0x1800986bb  mov     r15, r8
0x1800986be  xor     esi, esi
0x1800986c0  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800986c4  xor     r14d, r14d
0x1800986c7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800986cc  test    rdi, rdi
0x1800986cf  jnz     short loc_180098700
0x1800986d1  lea     r8, aTaskname; "taskName"
0x1800986d8  mov     rdx, r13
0x1800986db  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800986e2  mov     ebx, 80070057h
0x1800986e7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800986ec  lea     rdx, aTaskname; "taskName"
0x1800986f3  mov     rcx, r13; unsigned __int16 *
0x1800986f6  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800986fb  jmp     loc_1800988B8
0x180098700  test    r15, r15
0x180098703  jnz     short loc_180098729
0x180098705  lea     r8, aRegisteredtask; "registeredTask"
0x18009870c  mov     rdx, r13
0x18009870f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180098716  mov     ebx, 80070057h
0x18009871b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098720  lea     rdx, aRegisteredtask; "registeredTask"
0x180098727  jmp     short loc_1800986F3
0x180098729  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18009872d  mov     [r15], rsi
0x180098730  call    cs:__imp_VariantInit
0x180098736  xor     edx, edx; pUnkOuter
0x180098738  lea     rax, [rbp+57h+arg_18]
0x18009873c  lea     r9, IID_ITaskService; riid
0x180098743  mov     [rsp+0F0h+ppv], rax; ppv
0x180098748  lea     rcx, CLSID_TaskScheduler; rclsid
0x18009874f  lea     r8d, [rdx+1]; dwClsContext
0x180098753  call    cs:__imp_CoCreateInstance
0x180098759  mov     ebx, eax
0x18009875b  test    eax, eax
0x18009875d  jns     short loc_180098776
0x18009875f  mov     r8d, eax
0x180098762  lea     rcx, aSCocreateinsta_0; "%s: CoCreateInstance failed with error "...
0x180098769  mov     rdx, r13
0x18009876c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180098771  jmp     loc_1800988B8
0x180098776  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x18009877a  lea     rdx, [rbp+57h+var_A0]
0x18009877e  mov     rcx, [rbp+57h+arg_18]
0x180098782  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180098787  lea     r9, [rbp+57h+var_80]
0x18009878b  mov     [rsp+0F0h+ppv], rdx
0x180098790  lea     r8, [rbp+57h+var_60]
0x180098794  lea     rdx, [rbp+57h+var_40]
0x180098798  movaps  [rbp+57h+var_A0], xmm1
0x18009879c  mov     rax, [rcx]
0x18009879f  movsd   [rbp+57h+var_90], xmm0
0x1800987a4  movaps  [rbp+57h+var_80], xmm1
0x1800987a8  movsd   [rbp+57h+var_70], xmm0
0x1800987ad  mov     rax, [rax+50h]
0x1800987b1  movaps  [rbp+57h+var_60], xmm1
0x1800987b5  movsd   [rbp+57h+var_50], xmm0
0x1800987ba  movaps  [rbp+57h+var_40], xmm1
0x1800987be  movsd   [rbp+57h+var_30], xmm0
0x1800987c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987c8  mov     ebx, eax
0x1800987ca  test    eax, eax
0x1800987cc  jns     short loc_1800987EC
0x1800987ce  lea     r8, aItaskserviceCo; "ITaskService::Connect"
0x1800987d5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800987dc  mov     r9d, eax
0x1800987df  mov     rdx, r13
0x1800987e2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800987e7  jmp     loc_1800988B8
0x1800987ec  lea     rcx, psz; "\\Microsoft\\Windows\\Workplace Join"
0x1800987f3  call    cs:__imp_SysAllocString
0x1800987f9  mov     rsi, rax
0x1800987fc  test    rax, rax
0x1800987ff  jnz     short loc_18009881A
0x180098801  mov     rdx, r13
0x180098804  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18009880b  mov     ebx, 8007000Eh
0x180098810  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180098815  jmp     loc_1800988B8
0x18009881a  mov     rcx, [rbp+57h+arg_18]
0x18009881e  lea     r8, [rbp+57h+var_C0]
0x180098822  mov     rdx, rsi
0x180098825  mov     rax, [rcx]
0x180098828  mov     rax, [rax+38h]
0x18009882c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098831  mov     ebx, eax
0x180098833  test    eax, eax
0x180098835  jns     short loc_180098847
0x180098837  lea     r8, psz; "\\Microsoft\\Windows\\Workplace Join"
0x18009883e  lea     rcx, aSItaskserviceG; "%s: ITaskService::GetFolder(\"%s\") fai"...
0x180098845  jmp     short loc_1800987DC
0x180098847  mov     rcx, rdi; psz
0x18009884a  call    cs:__imp_SysAllocString
0x180098850  mov     r14, rax
0x180098853  test    rax, rax
0x180098856  jz      short loc_180098801
0x180098858  mov     rcx, [rbp+57h+var_C0]
0x18009885c  lea     r8, [rbp+57h+arg_0]
0x180098860  mov     rdx, r14
0x180098863  mov     rax, [rcx]
0x180098866  mov     rax, [rax+68h]
0x18009886a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009886f  mov     ebx, eax
0x180098871  test    eax, eax
0x180098873  jns     short loc_180098884
0x180098875  mov     r8, rdi
0x180098878  lea     rcx, aSItaskfolderGe; "%s: ITaskFolder::GetTask(\"%s\") failed"...
0x18009887f  jmp     loc_1800987DC
0x180098884  mov     rax, [rbp+57h+arg_0]
0x180098888  test    rax, rax
0x18009888b  jnz     short loc_1800988AD
0x18009888d  mov     r9, rdi
0x180098890  lea     r8, psz; "\\Microsoft\\Windows\\Workplace Join"
0x180098897  mov     rdx, r13
0x18009889a  lea     rcx, aSTaskSSNotFoun; "%s: Task \"%s\\%s\" not found. ITaskFol"...
0x1800988a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800988a6  mov     ebx, 80070002h
0x1800988ab  jmp     short loc_1800988B8
0x1800988ad  mov     [r15], rax
0x1800988b0  mov     [rbp+57h+arg_0], 0
0x1800988b8  mov     rcx, rsi; bstrString
0x1800988bb  call    cs:__imp_SysFreeString
0x1800988c1  mov     rcx, r14; bstrString
0x1800988c4  call    cs:__imp_SysFreeString
0x1800988ca  mov     rcx, [rbp+57h+arg_0]
0x1800988ce  test    rcx, rcx
0x1800988d1  jz      short loc_1800988DF
0x1800988d3  mov     rax, [rcx]
0x1800988d6  mov     rax, [rax+10h]
0x1800988da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988df  mov     rcx, [rbp+57h+var_C0]
0x1800988e3  test    rcx, rcx
0x1800988e6  jz      short loc_1800988F4
0x1800988e8  mov     rax, [rcx]
0x1800988eb  mov     rax, [rax+10h]
0x1800988ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800988f4  mov     rcx, [rbp+57h+arg_18]
0x1800988f8  test    rcx, rcx
0x1800988fb  jz      short loc_180098909
0x1800988fd  mov     rax, [rcx]
0x180098900  mov     rax, [rax+10h]
0x180098904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098909  mov     r8d, ebx
0x18009890c  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180098913  mov     rdx, r13
0x180098916  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009891b  lea     r11, [rsp+0F0h+var_20]
0x180098923  mov     eax, ebx
0x180098925  mov     rbx, [r11+38h]
0x180098929  mov     rsi, [r11+40h]
0x18009892d  mov     rsp, r11
0x180098930  pop     r15
0x180098932  pop     r14
0x180098934  pop     r13
0x180098936  pop     rdi
0x180098937  pop     rbp
0x180098938  retn
```
