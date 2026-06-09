# DpspInitializeTask

- ea: `0x180016f70`
- end: `0x180017037`
- name: `DpspInitializeTask`
- size: `199`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e4c8`

## callees

- `0x180009090`
- `0x180016f70`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016fb0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016fb0`

## string_xrefs

- `0x180016fd7`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180016ffb`: `clientcore\base\diagnosis\pdi\wdi\framework\dps\dpstask.cpp`
- `0x180016fd0`: `DpspVerifyTaskService`
- `0x180016ff4`: `DpspInitializeTask`

## pseudocode

```c
__int64 DpspInitializeTask()
{
  HRESULT Instance; // eax
  unsigned int v1; // edi

  g_pTaskService = 0;
  g_pTaskFolder = 0;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &g_pTaskService);
  v1 = Instance;
  if ( Instance < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (int)L"DpspVerifyTaskService",
      135,
      (int)L"Error = %d",
      Instance);
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpstask.cpp",
      (int)L"DpspInitializeTask",
      167,
      (int)L"Error = %d",
      v1);
    if ( g_pTaskService )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)g_pTaskService + 16LL))(g_pTaskService);
      g_pTaskService = 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180016f70  mov     [rsp+arg_0], rbx
0x180016f75  push    rdi
0x180016f76  sub     rsp, 30h
0x180016f7a  xor     edx, edx; pUnkOuter
0x180016f7c  mov     cs:g_pTaskService, 0
0x180016f87  lea     rax, g_pTaskService
0x180016f8e  mov     cs:g_pTaskFolder, 0
0x180016f99  lea     r9, IID_ITaskService; riid
0x180016fa0  mov     [rsp+38h+ppv], rax; ppv
0x180016fa5  lea     rcx, CLSID_TaskScheduler; rclsid
0x180016fac  lea     r8d, [rdx+1]; dwClsContext
0x180016fb0  call    cs:__imp_CoCreateInstance
0x180016fb6  mov     edi, eax
0x180016fb8  test    eax, eax
0x180016fba  jns     short loc_18001702A
0x180016fbc  movzx   ebx, di
0x180016fbf  lea     r9, aErrorD; "Error = %d"
0x180016fc6  mov     r8d, 87h; int
0x180016fcc  mov     dword ptr [rsp+38h+ppv], ebx; Args
0x180016fd0  lea     rdx, aDpspverifytask; "DpspVerifyTaskService"
0x180016fd7  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180016fde  call    WdipTraceError
0x180016fe3  lea     r9, aErrorD; "Error = %d"
0x180016fea  mov     dword ptr [rsp+38h+ppv], ebx; Args
0x180016fee  mov     r8d, 0A7h; int
0x180016ff4  lea     rdx, aDpspinitialize_1; "DpspInitializeTask"
0x180016ffb  lea     rcx, aClientcoreBase_4; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180017002  call    WdipTraceError
0x180017007  mov     rcx, cs:g_pTaskService
0x18001700e  test    rcx, rcx
0x180017011  jz      short loc_18001702A
0x180017013  mov     rax, [rcx]
0x180017016  mov     rax, [rax+10h]
0x18001701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001701f  mov     cs:g_pTaskService, 0
0x18001702a  mov     rbx, [rsp+38h+arg_0]
0x18001702f  mov     eax, edi
0x180017031  add     rsp, 30h
0x180017035  pop     rdi
0x180017036  retn
```
