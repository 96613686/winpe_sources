# Memory::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)

- ea: `0x1801b5d34`
- end: `0x1801b5f16`
- name: `??0AutoEnableDynamicCodeGen@Memory@@QEAA@_N@Z`
- size: `482`
- prototype: `__int64 __fastcall(Memory::AutoEnableDynamicCodeGen *__hidden this, bool)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801b48e4`
- `0x1801b529c`
- `0x1801b53b4`
- `0x1801b5930`
- `0x1801b5ad4`
- `0x180385460`
- `0x180416cd0`
- `0x180491f24`

## callees

- `0x1801b5d34`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5ef4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b5ef4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b5e25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b5e25`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1801b5e47`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1801b5e47`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e69`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e82`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e9f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e69`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e82`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801b5e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b5eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b5eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5de8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b5de8`

## string_xrefs

- `0x1801b5e40`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1801b5e95`: `GetThreadInformation`
- `0x1801b5e78`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Memory::AutoEnableDynamicCodeGen *__fastcall Memory::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        Memory::AutoEnableDynamicCodeGen *this,
        char a2)
{
  int (*v4)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE CurrentThread; // rax
  int (*v6)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v7; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v9; // rbx
  FARPROC ProcAddress; // rsi
  HANDLE CurrentProcess; // rax
  int v12; // [rsp+30h] [rbp-38h] BYREF
  __int64 v13; // [rsp+38h] [rbp-30h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+40h] [rbp-28h]

  v13 = -2;
  *(_BYTE *)this = 0;
  if ( a2 )
  {
    if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
    {
      v14 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
      EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
      if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
      {
        ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
        v9 = ModuleHandleW;
        if ( !ModuleHandleW
          || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
              Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v9, "SetThreadInformation"),
              Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v9, "GetThreadInformation"),
              !ProcAddress)
          || (CurrentProcess = GetCurrentProcess(),
              !((unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *))ProcAddress)(
                 CurrentProcess,
                 2,
                 &Memory::AutoEnableDynamicCodeGen::processPolicy)) )
        {
          Memory::AutoEnableDynamicCodeGen::processPolicy.Flags &= ~1u;
        }
        Memory::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
      }
      LeaveCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
    }
    if ( (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 1) != 0
      && (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 2) != 0 )
    {
      if ( Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc )
      {
        v4 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
        if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
        {
          v12 = 0;
          CurrentThread = GetCurrentThread();
          if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v4)(CurrentThread, 2, &v12) || v12 != 1 )
          {
            v12 = 1;
            v6 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
            v7 = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *))v6)(v7, 2, &v12);
            *(_BYTE *)this = 1;
          }
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801b5d34  mov     rax, rsp
0x1801b5d37  mov     [rax+10h], dl
0x1801b5d3a  mov     [rax+8], rcx
0x1801b5d3e  push    rsi
0x1801b5d3f  push    rdi
0x1801b5d40  push    r14
0x1801b5d42  sub     rsp, 50h
0x1801b5d46  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x1801b5d4e  mov     [rax+18h], rbx
0x1801b5d52  mov     rdi, rcx
0x1801b5d55  mov     byte ptr [rcx], 0
0x1801b5d58  test    dl, dl
0x1801b5d5a  jnz     short loc_1801B5D71
0x1801b5d5c  mov     rax, rdi
0x1801b5d5f  mov     rbx, [rsp+68h+arg_10]
0x1801b5d67  add     rsp, 50h
0x1801b5d6b  pop     r14
0x1801b5d6d  pop     rdi
0x1801b5d6e  pop     rsi
0x1801b5d6f  retn
0x1801b5d71  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x1801b5d77  test    al, al
0x1801b5d79  jz      loc_1801B5E16
0x1801b5d7f  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x1801b5d85  test    al, 1
0x1801b5d87  jz      short loc_1801B5D5C
0x1801b5d89  test    al, 2
0x1801b5d8b  jz      short loc_1801B5D5C
0x1801b5d8d  cmp     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, 0; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x1801b5d95  jz      short loc_1801B5D5C
0x1801b5d97  mov     rbx, cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x1801b5d9e  test    rbx, rbx
0x1801b5da1  jz      short loc_1801B5D5C
0x1801b5da3  mov     [rsp+68h+var_38], 0
0x1801b5dab  call    cs:__imp_GetCurrentThread
0x1801b5db2  nop     dword ptr [rax+rax+00h]
0x1801b5db7  mov     rcx, rax
0x1801b5dba  mov     r9d, 4
0x1801b5dc0  lea     r8, [rsp+68h+var_38]
0x1801b5dc5  lea     edx, [r9-2]
0x1801b5dc9  mov     rax, rbx
0x1801b5dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5dd1  test    eax, eax
0x1801b5dd3  jnz     loc_1801B5F06
0x1801b5dd9  mov     [rsp+68h+var_38], 1
0x1801b5de1  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x1801b5de8  call    cs:__imp_GetCurrentThread
0x1801b5def  nop     dword ptr [rax+rax+00h]
0x1801b5df4  mov     rcx, rax
0x1801b5df7  mov     r9d, 4
0x1801b5dfd  lea     r8, [rsp+68h+var_38]
0x1801b5e02  lea     edx, [r9-2]
0x1801b5e06  mov     rax, rbx
0x1801b5e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5e0e  mov     byte ptr [rdi], 1
0x1801b5e11  jmp     loc_1801B5D5C
0x1801b5e16  lea     r14, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x1801b5e1d  mov     [rsp+68h+var_28], r14
0x1801b5e22  mov     rcx, r14; lpCriticalSection
0x1801b5e25  call    cs:__imp_EnterCriticalSection
0x1801b5e2c  nop     dword ptr [rax+rax+00h]
0x1801b5e31  nop
0x1801b5e32  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x1801b5e38  test    al, al
0x1801b5e3a  jnz     loc_1801B5EF1
0x1801b5e40  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-3.d"...
0x1801b5e47  call    cs:__imp_GetModuleHandleW
0x1801b5e4e  nop     dword ptr [rax+rax+00h]
0x1801b5e53  mov     rbx, rax
0x1801b5e56  test    rax, rax
0x1801b5e59  jz      loc_1801B5EE3
0x1801b5e5f  lea     rdx, ProcName; "GetProcessMitigationPolicy"
0x1801b5e66  mov     rcx, rax; hModule
0x1801b5e69  call    cs:__imp_GetProcAddress
0x1801b5e70  nop     dword ptr [rax+rax+00h]
0x1801b5e75  mov     rsi, rax
0x1801b5e78  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x1801b5e7f  mov     rcx, rbx; hModule
0x1801b5e82  call    cs:__imp_GetProcAddress
0x1801b5e89  nop     dword ptr [rax+rax+00h]
0x1801b5e8e  mov     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x1801b5e95  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x1801b5e9c  mov     rcx, rbx; hModule
0x1801b5e9f  call    cs:__imp_GetProcAddress
0x1801b5ea6  nop     dword ptr [rax+rax+00h]
0x1801b5eab  mov     cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x1801b5eb2  test    rsi, rsi
0x1801b5eb5  jz      short loc_1801B5EE3
0x1801b5eb7  call    cs:__imp_GetCurrentProcess
0x1801b5ebe  nop     dword ptr [rax+rax+00h]
0x1801b5ec3  mov     rcx, rax
0x1801b5ec6  mov     r9d, 4
0x1801b5ecc  lea     r8, ?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x1801b5ed3  lea     edx, [r9-2]
0x1801b5ed7  mov     rax, rsi
0x1801b5eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5edf  test    eax, eax
0x1801b5ee1  jnz     short loc_1801B5EEA
0x1801b5ee3  and     cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A, 0FFFFFFFEh; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x1801b5eea  mov     cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC, 1; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x1801b5ef1  mov     rcx, r14; lpCriticalSection
0x1801b5ef4  call    cs:__imp_LeaveCriticalSection
0x1801b5efb  nop     dword ptr [rax+rax+00h]
0x1801b5f00  nop
0x1801b5f01  jmp     loc_1801B5D7F
0x1801b5f06  cmp     [rsp+68h+var_38], 1
0x1801b5f0b  jz      loc_1801B5D5C
0x1801b5f11  jmp     loc_1801B5DD9
```
