# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x180008d84`
- end: `0x180008e79`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `245`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bd60`

## callees

- `0x180008d84`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008de6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008df9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008de6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008df9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dc2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e4d`

## string_xrefs

- `0x180008dbb`: `kernelbase.dll`
- `0x180008d91`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180008da6`: `kernel32.dll`
- `0x180008ddc`: `SetThreadInformation`
- `0x180008dec`: `GetThreadInformation`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(
        __int64 a1)
{
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rax
  bool v4; // zf
  unsigned int (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD); // rbx
  HANDLE CurrentThread; // rax
  void (__fastcall *v7)(HANDLE, _QWORD, int *, __int64); // rbx
  HANDLE v8; // rax
  int v10; // [rsp+40h] [rbp+8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
  if ( !ModuleHandleW )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( !ModuleHandleW )
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  }
  if ( ModuleHandleW )
  {
    *(_QWORD *)a1 = GetProcAddress(ModuleHandleW, "SetThreadInformation");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetThreadInformation");
    v4 = *(_QWORD *)a1 == 0;
    v5 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    *(_QWORD *)(a1 + 8) = ProcAddress;
    if ( !v4 )
    {
      if ( ProcAddress )
      {
        v10 = 0;
        CurrentThread = GetCurrentThread();
        if ( v5(CurrentThread, 0, &v10, 4) )
        {
          v7 = *(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1;
          *(_DWORD *)(a1 + 16) = v10;
          v10 = 1;
          v8 = GetCurrentThread();
          v7(v8, 0, &v10, 4);
        }
      }
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180008d84  mov     [rsp+arg_8], rbx
0x180008d89  push    rdi
0x180008d8a  sub     rsp, 30h
0x180008d8e  mov     rdi, rcx
0x180008d91  lea     rcx, aApiMsWinCorePr_2; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180008d98  call    cs:__imp_GetModuleHandleW
0x180008d9e  mov     rbx, rax
0x180008da1  test    rax, rax
0x180008da4  jnz     short loc_180008DCB
0x180008da6  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180008dad  call    cs:__imp_GetModuleHandleW
0x180008db3  mov     rbx, rax
0x180008db6  test    rax, rax
0x180008db9  jnz     short loc_180008DCB
0x180008dbb  lea     rcx, ModuleName; "kernelbase.dll"
0x180008dc2  call    cs:__imp_GetModuleHandleW
0x180008dc8  mov     rbx, rax
0x180008dcb  test    rbx, rbx
0x180008dce  jnz     short loc_180008DDC
0x180008dd0  mov     [rdi], rbx
0x180008dd3  mov     [rdi+8], rbx
0x180008dd7  jmp     loc_180008E6B
0x180008ddc  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180008de3  mov     rcx, rbx; hModule
0x180008de6  call    cs:__imp_GetProcAddress
0x180008dec  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180008df3  mov     rcx, rbx; hModule
0x180008df6  mov     [rdi], rax
0x180008df9  call    cs:__imp_GetProcAddress
0x180008dff  cmp     qword ptr [rdi], 0
0x180008e03  mov     rbx, rax
0x180008e06  mov     [rdi+8], rax
0x180008e0a  jz      short loc_180008E6B
0x180008e0c  test    rax, rax
0x180008e0f  jz      short loc_180008E6B
0x180008e11  mov     [rsp+38h+arg_0], 0
0x180008e19  call    cs:__imp_GetCurrentThread
0x180008e1f  mov     r9d, 4
0x180008e25  lea     r8, [rsp+38h+arg_0]
0x180008e2a  mov     rcx, rax
0x180008e2d  xor     edx, edx
0x180008e2f  mov     rax, rbx
0x180008e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e37  test    eax, eax
0x180008e39  jz      short loc_180008E6B
0x180008e3b  mov     eax, [rsp+38h+arg_0]
0x180008e3f  mov     rbx, [rdi]
0x180008e42  mov     [rdi+10h], eax
0x180008e45  mov     [rsp+38h+arg_0], 1
0x180008e4d  call    cs:__imp_GetCurrentThread
0x180008e53  mov     r9d, 4
0x180008e59  lea     r8, [rsp+38h+arg_0]
0x180008e5e  mov     rcx, rax
0x180008e61  xor     edx, edx
0x180008e63  mov     rax, rbx
0x180008e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e6b  mov     rbx, [rsp+38h+arg_8]
0x180008e70  mov     rax, rdi
0x180008e73  add     rsp, 30h
0x180008e77  pop     rdi
0x180008e78  retn
```
