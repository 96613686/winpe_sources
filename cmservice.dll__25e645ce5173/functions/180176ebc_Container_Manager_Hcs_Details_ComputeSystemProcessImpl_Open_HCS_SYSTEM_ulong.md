# Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Open(HCS_SYSTEM__ *,ulong)

- ea: `0x180176ebc`
- end: `0x180177161`
- name: `?Open@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@QEAAXPEAUHCS_SYSTEM__@@K@Z`
- size: `677`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemProcessImpl *__hidden this, HCS_SYSTEM computeSystem, DWORD processId)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180181e78`

## callees

- `0x18002e2b4`
- `0x1800491e8`
- `0x1801260f0`
- `0x180176ebc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180176f9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180176f9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017705e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017705e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180176fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017700b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017700b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177094`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801770af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177079`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180177094`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801770af`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetProcessInfo` at `0x180176f38`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsGetProcessInfo` at `0x180176f38`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180176f11`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCreateOperation` at `0x180176f11`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x1801770bf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x1801770bf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176ffd`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x1801770d5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x180176ffd`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseProcess` at `0x1801770d5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenProcess` at `0x180176ef5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsOpenProcess` at `0x180176ef5`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176fbf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsSetProcessCallback` at `0x180176fbf`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x180176f68`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsWaitForOperationResultAndProcessInfo` at `0x180176f68`

## string_xrefs

- `0x1801770fe`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180177113`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x180177125`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x18017713a`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`
- `0x18017714f`: `onecore\base\gendrv\silos\clem\compute\lib\computesystemprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Container::Manager::Hcs::Details::ComputeSystemProcessImpl::Open(
        RTL_SRWLOCK *this,
        HCS_SYSTEM computeSystem,
        DWORD processId)
{
  HRESULT v4; // eax
  HCS_OPERATION Operation; // rax
  const char *v6; // r9
  HCS_OPERATION v7; // rbx
  HRESULT ProcessInfo; // eax
  HRESULT v9; // eax
  HRESULT v10; // eax
  HCS_PROCESS v11; // r12
  HCS_PROCESS Ptr; // r14
  DWORD LastError; // edi
  HCS_PROCESS process; // [rsp+20h] [rbp-50h] BYREF
  HANDLE StdOutput; // [rsp+28h] [rbp-48h] BYREF
  HANDLE v16[3]; // [rsp+30h] [rbp-40h] BYREF
  HCS_PROCESS_INFORMATION processInformation; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  HANDLE hObject; // [rsp+B8h] [rbp+48h] BYREF

  process = 0;
  v4 = HcsOpenProcess(computeSystem, processId, 0x10000000u, &process);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v4,
      (int)process);
  Operation = HcsCreateOperation(0, 0);
  v7 = Operation;
  v16[1] = Operation;
  if ( !Operation )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      v6);
  ProcessInfo = HcsGetProcessInfo(process, Operation);
  if ( ProcessInfo < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)ProcessInfo,
      (int)process);
  memset(&processInformation, 0, sizeof(processInformation));
  v9 = HcsWaitForOperationResultAndProcessInfo(v7, 0xFFFFFFFF, &processInformation, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v9,
      (int)process);
  v16[0] = processInformation.StdInput;
  StdOutput = processInformation.StdOutput;
  hObject = processInformation.StdError;
  AcquireSRWLockExclusive(this + 5);
  v16[2] = &this[5];
  v10 = HcsSetProcessCallback(
          process,
          HcsEventOptionNone,
          this,
          Container::Manager::Hcs::Details::ComputeSystemProcessImpl::OnProcessEvent);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\compute\\lib\\computesystemprocess.cpp",
      (const char *)(unsigned int)v10,
      (int)process);
  if ( this != (RTL_SRWLOCK *)&process )
  {
    v11 = process;
    Ptr = (HCS_PROCESS)this->Ptr;
    if ( this->Ptr )
    {
      LastError = GetLastError();
      HcsCloseProcess(Ptr);
      SetLastError(LastError);
    }
    this->Ptr = v11;
    process = 0;
  }
  LODWORD(this[1].Ptr) = processInformation.ProcessId;
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[2],
    v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[3],
    &StdOutput);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this[4],
    &hObject);
  LODWORD(this[6].Ptr) = 1;
  if ( this != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(this + 5);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)StdOutput - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(StdOutput);
  if ( (unsigned __int64)v16[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v16[0]);
  HcsCloseOperation(v7);
  if ( process )
    HcsCloseProcess(process);
}

```

## disassembly

```asm
0x180176ebc  mov     [rsp-28h+arg_0], rbx
0x180176ec1  mov     [rsp-28h+arg_8], rsi
0x180176ec6  push    rbp
0x180176ec7  push    rdi
0x180176ec8  push    r12
0x180176eca  push    r14
0x180176ecc  push    r15
0x180176ece  mov     rbp, rsp
0x180176ed1  sub     rsp, 70h
0x180176ed5  mov     eax, r8d
0x180176ed8  mov     r10, rdx
0x180176edb  mov     rsi, rcx
0x180176ede  mov     [rbp+process], 0
0x180176ee6  lea     r9, [rbp+process]; process
0x180176eea  mov     r8d, 10000000h; requestedAccess
0x180176ef0  mov     edx, eax; processId
0x180176ef2  mov     rcx, r10; computeSystem
0x180176ef5  call    cs:__imp_HcsOpenProcess
0x180176efc  nop     dword ptr [rax+rax+00h]
0x180176f01  mov     rcx, [rbp+28h]; this
0x180176f05  test    eax, eax
0x180176f07  js      loc_180177110
0x180176f0d  xor     edx, edx; callback
0x180176f0f  xor     ecx, ecx; context
0x180176f11  call    cs:__imp_HcsCreateOperation
0x180176f18  nop     dword ptr [rax+rax+00h]
0x180176f1d  mov     rbx, rax
0x180176f20  mov     [rbp+var_38], rax
0x180176f24  mov     rcx, [rbp+28h]; this
0x180176f28  test    rax, rax
0x180176f2b  jz      loc_180177125
0x180176f31  mov     rdx, rax; operation
0x180176f34  mov     rcx, [rbp+process]; process
0x180176f38  call    cs:__imp_HcsGetProcessInfo
0x180176f3f  nop     dword ptr [rax+rax+00h]
0x180176f44  mov     rcx, [rbp+28h]; this
0x180176f48  test    eax, eax
0x180176f4a  js      loc_180177137
0x180176f50  xorps   xmm0, xmm0
0x180176f53  movups  xmmword ptr [rbp+processInformation.ProcessId], xmm0
0x180176f57  movups  xmmword ptr [rbp+processInformation.StdOutput], xmm0
0x180176f5b  xor     r9d, r9d; resultDocument
0x180176f5e  lea     r8, [rbp+processInformation]; processInformation
0x180176f62  or      edx, 0FFFFFFFFh; timeoutMs
0x180176f65  mov     rcx, rbx; operation
0x180176f68  call    cs:__imp_HcsWaitForOperationResultAndProcessInfo
0x180176f6f  nop     dword ptr [rax+rax+00h]
0x180176f74  mov     rcx, [rbp+28h]; this
0x180176f78  test    eax, eax
0x180176f7a  js      loc_18017714C
0x180176f80  mov     rax, [rbp+processInformation.StdInput]
0x180176f84  mov     [rbp+var_40], rax
0x180176f88  mov     rax, [rbp+processInformation.StdOutput]
0x180176f8c  mov     [rbp+var_48], rax
0x180176f90  mov     rax, [rbp+processInformation.StdError]
0x180176f94  mov     [rbp+hObject], rax
0x180176f98  lea     r15, [rsi+28h]
0x180176f9c  mov     rcx, r15; SRWLock
0x180176f9f  call    cs:__imp_AcquireSRWLockExclusive
0x180176fa6  nop     dword ptr [rax+rax+00h]
0x180176fab  mov     [rbp+var_30], r15
0x180176faf  lea     r9, ?OnProcessEvent@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@CAXPEAUHCS_EVENT@@PEAX@Z; callback
0x180176fb6  mov     r8, rsi; context
0x180176fb9  xor     edx, edx; callbackOptions
0x180176fbb  mov     rcx, [rbp+process]; process
0x180176fbf  call    cs:__imp_HcsSetProcessCallback
0x180176fc6  nop     dword ptr [rax+rax+00h]
0x180176fcb  mov     rcx, [rbp+28h]; this
0x180176fcf  test    eax, eax
0x180176fd1  js      loc_1801770FB
0x180176fd7  lea     rax, [rbp+process]
0x180176fdb  cmp     rsi, rax
0x180176fde  jz      short loc_180177022
0x180176fe0  mov     r12, [rbp+process]
0x180176fe4  mov     r14, [rsi]
0x180176fe7  test    r14, r14
0x180176fea  jz      short loc_180177017
0x180176fec  call    cs:__imp_GetLastError
0x180176ff3  nop     dword ptr [rax+rax+00h]
0x180176ff8  mov     edi, eax
0x180176ffa  mov     rcx, r14; process
0x180176ffd  call    cs:__imp_HcsCloseProcess
0x180177004  nop     dword ptr [rax+rax+00h]
0x180177009  mov     ecx, edi; dwErrCode
0x18017700b  call    cs:__imp_SetLastError
0x180177012  nop     dword ptr [rax+rax+00h]
0x180177017  mov     [rsi], r12
0x18017701a  mov     [rbp+process], 0
0x180177022  mov     eax, [rbp+processInformation.ProcessId]
0x180177025  mov     [rsi+8], eax
0x180177028  lea     rcx, [rsi+10h]
0x18017702c  lea     rdx, [rbp+var_40]
0x180177030  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180177035  lea     rcx, [rsi+18h]
0x180177039  lea     rdx, [rbp+var_48]
0x18017703d  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180177042  lea     rcx, [rsi+20h]
0x180177046  lea     rdx, [rbp+hObject]
0x18017704a  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18017704f  mov     dword ptr [rsi+30h], 1
0x180177056  test    r15, r15
0x180177059  jz      short loc_18017706B
0x18017705b  mov     rcx, r15; SRWLock
0x18017705e  call    cs:__imp_ReleaseSRWLockExclusive
0x180177065  nop     dword ptr [rax+rax+00h]
0x18017706a  nop
0x18017706b  mov     rcx, [rbp+hObject]; hObject
0x18017706f  lea     rax, [rcx-1]
0x180177073  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180177077  ja      short loc_180177086
0x180177079  call    cs:__imp_CloseHandle
0x180177080  nop     dword ptr [rax+rax+00h]
0x180177085  nop
0x180177086  mov     rcx, [rbp+var_48]; hObject
0x18017708a  lea     rax, [rcx-1]
0x18017708e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180177092  ja      short loc_1801770A1
0x180177094  call    cs:__imp_CloseHandle
0x18017709b  nop     dword ptr [rax+rax+00h]
0x1801770a0  nop
0x1801770a1  mov     rcx, [rbp+var_40]; hObject
0x1801770a5  lea     rax, [rcx-1]
0x1801770a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801770ad  ja      short loc_1801770BC
0x1801770af  call    cs:__imp_CloseHandle
0x1801770b6  nop     dword ptr [rax+rax+00h]
0x1801770bb  nop
0x1801770bc  mov     rcx, rbx; operation
0x1801770bf  call    cs:__imp_HcsCloseOperation
0x1801770c6  nop     dword ptr [rax+rax+00h]
0x1801770cb  nop
0x1801770cc  mov     rcx, [rbp+process]; process
0x1801770d0  test    rcx, rcx
0x1801770d3  jz      short loc_1801770E1
0x1801770d5  call    cs:__imp_HcsCloseProcess
0x1801770dc  nop     dword ptr [rax+rax+00h]
0x1801770e1  lea     r11, [rsp+70h+var_s0]
0x1801770e6  mov     rbx, [r11+30h]
0x1801770ea  mov     rsi, [r11+38h]
0x1801770ee  mov     rsp, r11
0x1801770f1  pop     r15
0x1801770f3  pop     r14
0x1801770f5  pop     r12
0x1801770f7  pop     rdi
0x1801770f8  pop     rbp
0x1801770f9  retn
0x1801770fb  mov     r9d, eax; char *
0x1801770fe  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180177105  mov     edx, 0D4h; void *
0x18017710a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180177110  mov     r9d, eax; char *
0x180177113  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017711a  mov     edx, 0B3h; void *
0x18017711f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180177125  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x18017712c  mov     edx, 0B7h; void *
0x180177131  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180177137  mov     r9d, eax; char *
0x18017713a  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180177141  mov     edx, 0BAh; void *
0x180177146  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017714c  mov     r9d, eax; char *
0x18017714f  lea     r8, aOnecoreBaseGen_69; "onecore\\base\\gendrv\\silos\\clem\\com"...
0x180177156  mov     edx, 0C1h; void *
0x18017715b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
