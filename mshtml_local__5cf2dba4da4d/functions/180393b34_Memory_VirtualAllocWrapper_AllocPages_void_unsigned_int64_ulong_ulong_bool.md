# Memory::VirtualAllocWrapper::AllocPages(void *,unsigned __int64,ulong,ulong,bool)

- ea: `0x180393b34`
- end: `0x180393e1e`
- name: `?AllocPages@VirtualAllocWrapper@Memory@@QEAAPEAXPEAX_KKK_N@Z`
- size: `746`
- prototype: `void *__fastcall(Memory::VirtualAllocWrapper *__hidden this, void *, unsigned __int64, unsigned int, unsigned int, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180392744`
- `0x180393f48`

## callees

- `0x180393b34`
- `0x180393e24`
- `0x1810bc928`
- `0x1810c0bf4`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180393d11`
- `KERNEL32!GetCurrentThread` at `0x180393d50`
- `KERNEL32!GetCurrentThread` at `0x180393df5`
- `KERNEL32!GetCurrentThread` at `0x180393d11`
- `KERNEL32!GetCurrentThread` at `0x180393d50`
- `KERNEL32!GetCurrentThread` at `0x180393df5`
- `KERNEL32!GetProcAddress` at `0x180393c3c`
- `KERNEL32!GetProcAddress` at `0x180393c55`
- `KERNEL32!GetProcAddress` at `0x180393c72`
- `KERNEL32!GetProcAddress` at `0x180393c3c`
- `KERNEL32!GetProcAddress` at `0x180393c55`
- `KERNEL32!GetProcAddress` at `0x180393c72`
- `KERNEL32!GetModuleHandleW` at `0x180393c1a`
- `KERNEL32!GetModuleHandleW` at `0x180393c1a`
- `KERNEL32!LeaveCriticalSection` at `0x180393cc9`
- `KERNEL32!LeaveCriticalSection` at `0x180393cc9`
- `KERNEL32!EnterCriticalSection` at `0x180393bf8`
- `KERNEL32!EnterCriticalSection` at `0x180393bf8`
- `KERNEL32!GetCurrentProcess` at `0x180393c8a`
- `KERNEL32!GetCurrentProcess` at `0x180393c8a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180393b9c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180393d83`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180393b9c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180393d83`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180393dc5`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180393dc5`

## string_xrefs

- `0x180393c68`: `GetThreadInformation`
- `0x180393c13`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180393c4b`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::VirtualAllocWrapper::AllocPages(
        Memory::VirtualAllocWrapper *this,
        void *a2,
        unsigned __int64 a3,
        DWORD a4,
        unsigned int a5,
        bool a6)
{
  SIZE_T v6; // rdi
  char v7; // bl
  LPVOID v8; // rsi
  HMODULE ModuleHandleW; // rax
  HMODULE v11; // rsi
  FARPROC ProcAddress; // r15
  HANDLE CurrentProcess; // rax
  int (*v14)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rsi
  HANDLE CurrentThread; // rax
  int (*v16)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v17; // rax
  void *v18; // rax
  int (*v19)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v20; // rax
  _BYTE v21[4]; // [rsp+30h] [rbp-28h] BYREF
  int v22; // [rsp+34h] [rbp-24h] BYREF
  DWORD flOldProtect; // [rsp+38h] [rbp-20h] BYREF
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+40h] [rbp-18h]

  if ( a3 > 0xFFFFFFFFFFFFFLL )
    return 0;
  v6 = a3 << 12;
  v7 = 0;
  v21[0] = 0;
  if ( a6 )
  {
    if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
    {
      v24 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
      EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
      if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
      {
        ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
        v11 = ModuleHandleW;
        if ( !ModuleHandleW
          || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
              Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v11, "SetThreadInformation"),
              Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v11, "GetThreadInformation"),
              !ProcAddress)
          || (CurrentProcess = GetCurrentProcess(),
              !((unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *, __int64))ProcAddress)(
                 CurrentProcess,
                 2,
                 &Memory::AutoEnableDynamicCodeGen::processPolicy,
                 4)) )
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
        v14 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
        if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
        {
          v22 = 0;
          CurrentThread = GetCurrentThread();
          if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *, __int64))v14)(CurrentThread, 2, &v22, 4)
            || v22 != 1 )
          {
            v22 = 1;
            v16 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
            v17 = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *, __int64))v16)(v17, 2, &v22, 4);
            v7 = 1;
            v21[0] = 1;
          }
        }
      }
    }
  }
  flOldProtect = 0;
  if ( a6 )
  {
    v18 = VirtualAlloc(a2, v6, a4, 0x40000040u);
    v8 = v18;
    if ( !v18 )
    {
      Memory::MemoryOperationLastError::RecordLastError();
      Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v21);
      return 0;
    }
    if ( (a4 & 0x1000) != 0 && !VirtualProtect(v18, v6, 4u, &flOldProtect) )
      CustomHeap_BadPageState_fatal_error((unsigned __int64)this);
  }
  else
  {
    v8 = VirtualAlloc(a2, v6, a4, 4u);
    if ( !v8 )
    {
      Memory::MemoryOperationLastError::RecordLastError();
      if ( v7 )
      {
        v22 = 0;
        v19 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
        v20 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))v19)(v20, 2, &v22, 4);
      }
      return 0;
    }
  }
  Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v21);
  return v8;
}

```

## disassembly

```asm
0x180393b34  mov     rax, rsp
0x180393b37  mov     [rax+20h], r9d
0x180393b3b  mov     [rax+18h], r8
0x180393b3f  mov     [rax+10h], rdx
0x180393b43  mov     [rax+8], rcx
0x180393b47  push    rbp
0x180393b48  push    rbx
0x180393b49  push    rsi
0x180393b4a  push    rdi
0x180393b4b  push    r13
0x180393b4d  push    r15
0x180393b4f  mov     rbp, rsp
0x180393b52  sub     rsp, 58h
0x180393b56  mov     rax, 0FFFFFFFFFFFFFh
0x180393b60  mov     rdi, [rbp+arg_10]
0x180393b64  cmp     rdi, rax
0x180393b67  ja      short loc_180393BBE
0x180393b69  shl     rdi, 0Ch
0x180393b6d  mov     r13d, 4
0x180393b73  xor     bl, bl
0x180393b75  mov     [rbp+var_28], bl
0x180393b78  cmp     [rbp+arg_28], bl
0x180393b7b  jnz     short loc_180393BDC
0x180393b7d  mov     [rbp+flOldProtect], 0
0x180393b84  mov     r8d, [rbp+flAllocationType]; flAllocationType
0x180393b88  mov     rdx, rdi; dwSize
0x180393b8b  mov     rcx, [rbp+lpAddress]; lpAddress
0x180393b8f  cmp     [rbp+arg_28], 0
0x180393b93  jnz     loc_180393D7D
0x180393b99  mov     r9d, r13d; flProtect
0x180393b9c  call    cs:__imp_VirtualAlloc
0x180393ba3  nop     dword ptr [rax+rax+00h]
0x180393ba8  mov     rsi, rax
0x180393bab  test    rax, rax
0x180393bae  jnz     short loc_180393BCE
0x180393bb0  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x180393bb5  nop
0x180393bb6  test    bl, bl
0x180393bb8  jnz     loc_180393DE7
0x180393bbe  xor     eax, eax
0x180393bc0  add     rsp, 58h
0x180393bc4  pop     r15
0x180393bc6  pop     r13
0x180393bc8  pop     rdi
0x180393bc9  pop     rsi
0x180393bca  pop     rbx
0x180393bcb  pop     rbp
0x180393bcc  retn
0x180393bce  lea     rcx, [rbp+var_28]; this
0x180393bd2  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x180393bd7  mov     rax, rsi
0x180393bda  jmp     short loc_180393BC0
0x180393bdc  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180393be2  test    al, al
0x180393be4  jnz     loc_180393CD6
0x180393bea  lea     rax, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x180393bf1  mov     [rbp+var_18], rax
0x180393bf5  mov     rcx, rax; lpCriticalSection
0x180393bf8  call    cs:__imp_EnterCriticalSection
0x180393bff  nop     dword ptr [rax+rax+00h]
0x180393c04  nop
0x180393c05  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180393c0b  test    al, al
0x180393c0d  jnz     loc_180393CC2
0x180393c13  lea     rcx, aApiMsWinCorePr_4; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180393c1a  call    cs:__imp_GetModuleHandleW
0x180393c21  nop     dword ptr [rax+rax+00h]
0x180393c26  mov     rsi, rax
0x180393c29  test    rax, rax
0x180393c2c  jz      loc_180393CB4
0x180393c32  lea     rdx, aGetprocessmiti; "GetProcessMitigationPolicy"
0x180393c39  mov     rcx, rax; hModule
0x180393c3c  call    cs:__imp_GetProcAddress
0x180393c43  nop     dword ptr [rax+rax+00h]
0x180393c48  mov     r15, rax
0x180393c4b  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180393c52  mov     rcx, rsi; hModule
0x180393c55  call    cs:__imp_GetProcAddress
0x180393c5c  nop     dword ptr [rax+rax+00h]
0x180393c61  mov     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393c68  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180393c6f  mov     rcx, rsi; hModule
0x180393c72  call    cs:__imp_GetProcAddress
0x180393c79  nop     dword ptr [rax+rax+00h]
0x180393c7e  mov     cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393c85  test    r15, r15
0x180393c88  jz      short loc_180393CB4
0x180393c8a  call    cs:__imp_GetCurrentProcess
0x180393c91  nop     dword ptr [rax+rax+00h]
0x180393c96  mov     rcx, rax
0x180393c99  mov     r9, r13
0x180393c9c  lea     r8, ?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180393ca3  mov     edx, 2
0x180393ca8  mov     rax, r15
0x180393cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393cb0  test    eax, eax
0x180393cb2  jnz     short loc_180393CBB
0x180393cb4  and     cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A, 0FFFFFFFEh; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180393cbb  mov     cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC, 1; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180393cc2  lea     rcx, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; lpCriticalSection
0x180393cc9  call    cs:__imp_LeaveCriticalSection
0x180393cd0  nop     dword ptr [rax+rax+00h]
0x180393cd5  nop
0x180393cd6  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180393cdc  test    al, 1
0x180393cde  jz      loc_180393B7D
0x180393ce4  test    al, 2
0x180393ce6  jz      loc_180393B7D
0x180393cec  cmp     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, 0; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393cf4  jz      loc_180393B7D
0x180393cfa  mov     rsi, cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393d01  test    rsi, rsi
0x180393d04  jz      loc_180393B7D
0x180393d0a  mov     [rbp+var_24], 0
0x180393d11  call    cs:__imp_GetCurrentThread
0x180393d18  nop     dword ptr [rax+rax+00h]
0x180393d1d  mov     rcx, rax
0x180393d20  mov     r9d, r13d
0x180393d23  lea     r8, [rbp+var_24]
0x180393d27  mov     edx, 2
0x180393d2c  mov     rax, rsi
0x180393d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393d34  test    eax, eax
0x180393d36  jz      short loc_180393D42
0x180393d38  cmp     [rbp+var_24], 1
0x180393d3c  jz      loc_180393B7D
0x180393d42  mov     [rbp+var_24], 1
0x180393d49  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393d50  call    cs:__imp_GetCurrentThread
0x180393d57  nop     dword ptr [rax+rax+00h]
0x180393d5c  mov     rcx, rax
0x180393d5f  mov     r9d, r13d
0x180393d62  lea     r8, [rbp+var_24]
0x180393d66  mov     edx, 2
0x180393d6b  mov     rax, rbx
0x180393d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393d73  mov     bl, 1
0x180393d75  mov     [rbp+var_28], bl
0x180393d78  jmp     loc_180393B7D
0x180393d7d  mov     r9d, 40000040h; flProtect
0x180393d83  call    cs:__imp_VirtualAlloc
0x180393d8a  nop     dword ptr [rax+rax+00h]
0x180393d8f  mov     rsi, rax
0x180393d92  test    rax, rax
0x180393d95  jnz     short loc_180393DAB
0x180393d97  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x180393d9c  nop
0x180393d9d  lea     rcx, [rbp+var_28]; this
0x180393da1  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x180393da6  jmp     loc_180393BBE
0x180393dab  test    [rbp+flAllocationType], 1000h
0x180393db2  jz      loc_180393BCE
0x180393db8  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x180393dbc  mov     r8d, r13d; flNewProtect
0x180393dbf  mov     rdx, rdi; dwSize
0x180393dc2  mov     rcx, rax; lpAddress
0x180393dc5  call    cs:__imp_VirtualProtect
0x180393dcc  nop     dword ptr [rax+rax+00h]
0x180393dd1  test    eax, eax
0x180393dd3  jnz     loc_180393BCE
0x180393dd9  mov     rcx, [rbp+arg_0]; unsigned __int64
0x180393ddd  call    ?CustomHeap_BadPageState_fatal_error@@YAX_K@Z; CustomHeap_BadPageState_fatal_error(unsigned __int64)
0x180393de2  jmp     loc_180393BCE
0x180393de7  mov     [rbp+var_24], 0
0x180393dee  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180393df5  call    cs:__imp_GetCurrentThread
0x180393dfc  nop     dword ptr [rax+rax+00h]
0x180393e01  mov     rcx, rax
0x180393e04  mov     r9d, r13d
0x180393e07  lea     r8, [rbp+var_24]
0x180393e0b  mov     edx, 2
0x180393e10  mov     rax, rbx
0x180393e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180393e18  jmp     loc_180393BBE
```
