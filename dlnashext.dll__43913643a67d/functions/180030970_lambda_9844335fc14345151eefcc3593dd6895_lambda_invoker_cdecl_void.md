# _lambda_9844335fc14345151eefcc3593dd6895_::_lambda_invoker_cdecl_(void *)

- ea: `0x180030970`
- end: `0x18003098f`
- name: `?_lambda_invoker_cdecl_@_lambda_9844335fc14345151eefcc3593dd6895_@@CAKPEAX@Z`
- size: `31`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000a694`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180030988`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180030988`

## pseudocode

```c
void __fastcall __noreturn _lambda_9844335fc14345151eefcc3593dd6895_::_lambda_invoker_cdecl_(LPVOID lpThreadParameter)
{
  HMODULE hLibModule; // [rsp+38h] [rbp+10h] BYREF

  WorkThreadManager::CThread::s_ExecuteThreadProc(&hLibModule, lpThreadParameter);
  FreeLibraryAndExitThread(hLibModule, 0);
}

```

## disassembly

```asm
0x180030970  sub     rsp, 28h
0x180030974  mov     rdx, rcx
0x180030977  lea     rcx, [rsp+28h+hLibModule]
0x18003097c  call    ?s_ExecuteThreadProc@CThread@WorkThreadManager@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAX@Z; WorkThreadManager::CThread::s_ExecuteThreadProc(void *)
0x180030981  mov     rcx, [rsp+28h+hLibModule]; hLibModule
0x180030986  xor     edx, edx; dwExitCode
0x180030988  call    cs:__imp_FreeLibraryAndExitThread
```
