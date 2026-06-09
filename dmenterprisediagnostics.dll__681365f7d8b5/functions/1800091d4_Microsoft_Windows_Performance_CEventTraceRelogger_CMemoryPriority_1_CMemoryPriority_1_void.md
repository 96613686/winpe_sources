# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::CMemoryPriority<1>(void)

- ea: `0x1800091d4`
- end: `0x1800092f4`
- name: `??0?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c2e0`

## callees

- `0x1800091d4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009248`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009261`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009248`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009261`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800091e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009203`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000921e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800091e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009203`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000921e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800092c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800092c1`

## string_xrefs

- `0x180009217`: `kernelbase.dll`
- `0x1800091e1`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1800091fc`: `kernel32.dll`
- `0x18000923e`: `SetThreadInformation`
- `0x180009254`: `GetThreadInformation`

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
0x1800091d4  mov     [rsp+arg_8], rbx
0x1800091d9  push    rdi
0x1800091da  sub     rsp, 30h
0x1800091de  mov     rdi, rcx
0x1800091e1  lea     rcx, aApiMsWinCorePr_2; "api-ms-win-core-processthreads-l1-1-3.d"...
0x1800091e8  call    cs:__imp_GetModuleHandleW
0x1800091ef  nop     dword ptr [rax+rax+00h]
0x1800091f4  mov     rbx, rax
0x1800091f7  test    rax, rax
0x1800091fa  jnz     short loc_18000922D
0x1800091fc  lea     rcx, aKernel32Dll; "kernel32.dll"
0x180009203  call    cs:__imp_GetModuleHandleW
0x18000920a  nop     dword ptr [rax+rax+00h]
0x18000920f  mov     rbx, rax
0x180009212  test    rax, rax
0x180009215  jnz     short loc_18000922D
0x180009217  lea     rcx, ModuleName; "kernelbase.dll"
0x18000921e  call    cs:__imp_GetModuleHandleW
0x180009225  nop     dword ptr [rax+rax+00h]
0x18000922a  mov     rbx, rax
0x18000922d  test    rbx, rbx
0x180009230  jnz     short loc_18000923E
0x180009232  mov     [rdi], rbx
0x180009235  mov     [rdi+8], rbx
0x180009239  jmp     loc_1800092E5
0x18000923e  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180009245  mov     rcx, rbx; hModule
0x180009248  call    cs:__imp_GetProcAddress
0x18000924f  nop     dword ptr [rax+rax+00h]
0x180009254  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x18000925b  mov     rcx, rbx; hModule
0x18000925e  mov     [rdi], rax
0x180009261  call    cs:__imp_GetProcAddress
0x180009268  nop     dword ptr [rax+rax+00h]
0x18000926d  cmp     qword ptr [rdi], 0
0x180009271  mov     rbx, rax
0x180009274  mov     [rdi+8], rax
0x180009278  jz      short loc_1800092E5
0x18000927a  test    rax, rax
0x18000927d  jz      short loc_1800092E5
0x18000927f  mov     [rsp+38h+arg_0], 0
0x180009287  call    cs:__imp_GetCurrentThread
0x18000928e  nop     dword ptr [rax+rax+00h]
0x180009293  mov     r9d, 4
0x180009299  lea     r8, [rsp+38h+arg_0]
0x18000929e  mov     rcx, rax
0x1800092a1  xor     edx, edx
0x1800092a3  mov     rax, rbx
0x1800092a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ab  test    eax, eax
0x1800092ad  jz      short loc_1800092E5
0x1800092af  mov     eax, [rsp+38h+arg_0]
0x1800092b3  mov     rbx, [rdi]
0x1800092b6  mov     [rdi+10h], eax
0x1800092b9  mov     [rsp+38h+arg_0], 1
0x1800092c1  call    cs:__imp_GetCurrentThread
0x1800092c8  nop     dword ptr [rax+rax+00h]
0x1800092cd  mov     r9d, 4
0x1800092d3  lea     r8, [rsp+38h+arg_0]
0x1800092d8  mov     rcx, rax
0x1800092db  xor     edx, edx
0x1800092dd  mov     rax, rbx
0x1800092e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092e5  mov     rbx, [rsp+38h+arg_8]
0x1800092ea  mov     rax, rdi
0x1800092ed  add     rsp, 30h
0x1800092f1  pop     rdi
0x1800092f2  retn
```
