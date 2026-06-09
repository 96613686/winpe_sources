# ComputeService::Vmwp::LookupWorkerProcess(_GUID const &)

- ea: `0x18004ed1c`
- end: `0x18004eeb0`
- name: `?LookupWorkerProcess@Vmwp@ComputeService@@YA?AUWorkerProcessContext@12@AEBU_GUID@@@Z`
- size: `404`
- prototype: `struct ComputeService::Vmwp::WorkerProcessContext __high(const struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180045980`
- `0x180046700`

## callees

- `0x1800067c0`
- `0x18001017c`
- `0x18001587c`
- `0x180027380`
- `0x18004df3c`
- `0x18004ed1c`
- `0x18004eeb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004edd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004edd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ee20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004edcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004edcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ee18`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004edaa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004edf6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004edaa`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004edf6`

## string_xrefs

- `0x18004ee68`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x18004ee85`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`
- `0x18004ee9e`: `onecore\vm\compute\shared\vmwp\lib\workerprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComputeService::Vmwp::LookupWorkerProcess(
        __int64 a1,
        ComputeService::Vmwp::Details *a2,
        struct IUnknown **a3)
{
  _QWORD *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // eax
  HANDLE v9; // rsi
  char *v10; // rbp
  DWORD LastError; // ebx
  HANDLE v12; // rsi
  const char *v13; // r9
  char *v14; // rbp
  DWORD v15; // ebx
  _QWORD v17[2]; // [rsp+28h] [rbp-40h] BYREF
  DWORD dwProcessId; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v17[1] = a1;
  v5 = (_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = -1;
  dwProcessId = 0;
  if ( !ComputeService::Vmwp::Details::LookupWorkerProcessInterface(a2, (const struct _GUID *)(a1 + 16), a3) )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4AA,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)0x490,
      1u);
  v17[0] = &dwProcessId;
  v8 = ___InvokeWorkerProcessMethod_UIVmVirtualMachine__PEAK__ZPEAK_Vmwp_ComputeService__YAJAEBUWorkerProcessContext_01_PEAUIUnknown__P8IVmVirtualMachine__EAAJPEAK_Z__QEAPEAK_Z(
         v6,
         *v5,
         v7,
         v17);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B0,
      (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
      (const char *)(unsigned int)v8,
      1);
  v9 = OpenProcess(0x100001u, 0, dwProcessId);
  v10 = *(char **)(a1 + 24);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v10);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 24) = v9;
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v12 = OpenProcess(0x100000u, 0, dwProcessId);
    v14 = *(char **)(a1 + 24);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v15 = GetLastError();
      CloseHandle(v14);
      SetLastError(v15);
    }
    *(_QWORD *)(a1 + 24) = v12;
    if ( (((unsigned __int64)v12 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4C3,
        (unsigned int)"onecore\\vm\\compute\\shared\\vmwp\\lib\\workerprocess.cpp",
        v13);
  }
  *(_OWORD *)a1 = *(_OWORD *)a2;
  return a1;
}

```

## disassembly

```asm
0x18004ed1c  mov     [rsp+arg_10], rbx
0x18004ed21  mov     [rsp+arg_18], rbp
0x18004ed26  push    rsi
0x18004ed27  push    rdi
0x18004ed28  push    r14
0x18004ed2a  sub     rsp, 50h
0x18004ed2e  mov     rax, cs:__security_cookie
0x18004ed35  xor     rax, rsp
0x18004ed38  mov     [rsp+68h+var_28], rax
0x18004ed3d  mov     r14, rdx
0x18004ed40  mov     rdi, rcx
0x18004ed43  mov     [rsp+68h+var_38], rcx
0x18004ed48  xor     esi, esi
0x18004ed4a  mov     [rsp+68h+var_48], esi
0x18004ed4e  lea     rbx, [rcx+10h]
0x18004ed52  mov     [rbx], rsi
0x18004ed55  mov     [rcx+18h], rsi
0x18004ed59  mov     dword ptr [rcx+20h], 0FFFFFFFFh
0x18004ed60  mov     [rsp+68h+var_48], 1; int
0x18004ed68  mov     [rsp+68h+dwProcessId], esi
0x18004ed6c  mov     rdx, rbx; struct _GUID *
0x18004ed6f  mov     rcx, r14; this
0x18004ed72  call    ?LookupWorkerProcessInterface@Details@Vmwp@ComputeService@@YA_NAEBU_GUID@@PEAPEAUIUnknown@@@Z; ComputeService::Vmwp::Details::LookupWorkerProcessInterface(_GUID const &,IUnknown * *)
0x18004ed77  test    al, al
0x18004ed79  jz      loc_18004EE7A
0x18004ed7f  lea     rax, [rsp+68h+dwProcessId]
0x18004ed84  mov     [rsp+68h+var_40], rax
0x18004ed89  lea     r9, [rsp+68h+var_40]
0x18004ed8e  mov     rdx, [rbx]
0x18004ed91  call    ??$InvokeWorkerProcessMethod@UIVmVirtualMachine@@PEAK$$ZPEAK@Vmwp@ComputeService@@YAJAEBUWorkerProcessContext@01@PEAUIUnknown@@P8IVmVirtualMachine@@EAAJPEAK@Z$$QEAPEAK@Z
0x18004ed96  test    eax, eax
0x18004ed98  js      loc_18004EE96
0x18004ed9e  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x18004eda3  xor     edx, edx; bInheritHandle
0x18004eda5  mov     ecx, 100001h; dwDesiredAccess
0x18004edaa  call    cs:__imp_OpenProcess
0x18004edb0  mov     rsi, rax
0x18004edb3  mov     rbp, [rdi+18h]
0x18004edb7  lea     rdx, [rbp-1]
0x18004edbb  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004edbf  ja      short loc_18004EDDA
0x18004edc1  call    cs:__imp_GetLastError
0x18004edc7  mov     ebx, eax
0x18004edc9  mov     rcx, rbp; hObject
0x18004edcc  call    cs:__imp_CloseHandle
0x18004edd2  mov     ecx, ebx; dwErrCode
0x18004edd4  call    cs:__imp_SetLastError
0x18004edda  mov     [rdi+18h], rsi
0x18004edde  lea     rax, [rsi+1]
0x18004ede2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004ede8  jnz     short loc_18004EE36
0x18004edea  mov     r8d, [rsp+68h+dwProcessId]; dwProcessId
0x18004edef  xor     edx, edx; bInheritHandle
0x18004edf1  mov     ecx, 100000h; dwDesiredAccess
0x18004edf6  call    cs:__imp_OpenProcess
0x18004edfc  mov     rsi, rax
0x18004edff  mov     rbp, [rdi+18h]
0x18004ee03  lea     rdx, [rbp-1]
0x18004ee07  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004ee0b  ja      short loc_18004EE26
0x18004ee0d  call    cs:__imp_GetLastError
0x18004ee13  mov     ebx, eax
0x18004ee15  mov     rcx, rbp; hObject
0x18004ee18  call    cs:__imp_CloseHandle
0x18004ee1e  mov     ecx, ebx; dwErrCode
0x18004ee20  call    cs:__imp_SetLastError
0x18004ee26  mov     [rdi+18h], rsi
0x18004ee2a  lea     rax, [rsi+1]
0x18004ee2e  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004ee34  jz      short loc_18004EE63
0x18004ee36  movups  xmm0, xmmword ptr [r14]
0x18004ee3a  movdqu  xmmword ptr [rdi], xmm0
0x18004ee3e  mov     rax, rdi
0x18004ee41  mov     rcx, [rsp+68h+var_28]
0x18004ee46  xor     rcx, rsp; StackCookie
0x18004ee49  call    __security_check_cookie
0x18004ee4e  lea     r11, [rsp+68h+var_18]
0x18004ee53  mov     rbx, [r11+30h]
0x18004ee57  mov     rbp, [r11+38h]
0x18004ee5b  mov     rsp, r11
0x18004ee5e  pop     r14
0x18004ee60  pop     rdi
0x18004ee61  pop     rsi
0x18004ee62  retn
0x18004ee63  mov     rcx, [rsp+68h]; this
0x18004ee68  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004ee6f  mov     edx, 4C3h; void *
0x18004ee74  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004ee7a  mov     rcx, [rsp+68h]; this
0x18004ee7f  mov     r9d, 490h; char *
0x18004ee85  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004ee8c  lea     edx, [r9+1Ah]; void *
0x18004ee90  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004ee96  mov     rcx, [rsp+68h]; this
0x18004ee9b  mov     r9d, eax; char *
0x18004ee9e  lea     r8, aOnecoreVmCompu_9; "onecore\\vm\\compute\\shared\\vmwp\\lib"...
0x18004eea5  mov     edx, 4B0h; void *
0x18004eeaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
