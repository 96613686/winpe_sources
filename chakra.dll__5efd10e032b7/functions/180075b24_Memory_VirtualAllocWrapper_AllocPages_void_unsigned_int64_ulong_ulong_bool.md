# Memory::VirtualAllocWrapper::AllocPages(void *,unsigned __int64,ulong,ulong,bool)

- ea: `0x180075b24`
- end: `0x180075e18`
- name: `?AllocPages@VirtualAllocWrapper@Memory@@QEAAPEAXPEAX_KKK_N@Z`
- size: `756`
- prototype: `void *__fastcall(Memory::VirtualAllocWrapper *__hidden this, void *, unsigned __int64, unsigned int, DWORD flProtect, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073a58`
- `0x180074070`
- `0x180074a88`
- `0x1801b4f58`
- `0x1801b543c`
- `0x1803a6e20`

## callees

- `0x180075b24`
- `0x1801b5cc8`
- `0x180408f60`
- `0x18048e5d8`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075dbe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075ceb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075ceb`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180075d0d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180075d0d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d2f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d48`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d65`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d2f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d48`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180075d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180075d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180075d7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075ded`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075ded`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180075b98`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180075c8c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180075b98`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180075c8c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180075cbb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180075cbb`

## string_xrefs

- `0x180075d06`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180075d5b`: `GetThreadInformation`
- `0x180075d3e`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::VirtualAllocWrapper::AllocPages(
        Memory::VirtualAllocWrapper *this,
        void *a2,
        unsigned __int64 a3,
        DWORD a4,
        DWORD flProtect,
        bool a6)
{
  SIZE_T v6; // rdi
  char v7; // bl
  LPVOID v8; // rsi
  int (*v10)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rsi
  HANDLE CurrentThread; // rax
  int (*v12)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v13; // rax
  void *v14; // rax
  HMODULE ModuleHandleW; // rax
  HMODULE v16; // rsi
  FARPROC ProcAddress; // r12
  HANDLE CurrentProcess; // rax
  int (*v19)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v20; // rax
  char v21[4]; // [rsp+30h] [rbp-20h] BYREF
  int v22; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD flOldProtect; // [rsp+38h] [rbp-18h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h]
  struct _RTL_CRITICAL_SECTION *v25; // [rsp+48h] [rbp-8h]

  v24 = -2;
  if ( a3 > 0xFFFFFFFFFFFFFLL )
    return 0;
  v6 = a3 << 12;
  if ( !a6 && (flProtect & 0x70) == 0 )
  {
    v7 = 0;
LABEL_5:
    v21[0] = v7;
    goto LABEL_6;
  }
  v7 = 0;
  v21[0] = 0;
  if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
  {
    v25 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
    EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
    if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
    {
      ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
      v16 = ModuleHandleW;
      if ( !ModuleHandleW
        || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
            Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v16, "SetThreadInformation"),
            Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v16, "GetThreadInformation"),
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
      v10 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
      if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
      {
        v22 = 0;
        CurrentThread = GetCurrentThread();
        if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v10)(CurrentThread, 2, &v22) || v22 != 1 )
        {
          v22 = 1;
          v12 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
          v13 = GetCurrentThread();
          ((void (__fastcall *)(HANDLE, __int64, int *))v12)(v13, 2, &v22);
          v7 = 1;
          goto LABEL_5;
        }
      }
    }
  }
LABEL_6:
  flOldProtect = 0;
  if ( a6 )
  {
    v14 = VirtualAlloc(a2, v6, a4, 0x40000040u);
    v8 = v14;
    if ( v14 )
    {
      if ( (a4 & 0x1000) != 0 && !VirtualProtect(v14, v6, flProtect, &flOldProtect) )
        CustomHeap_BadPageState_unrecoverable_error((unsigned __int64)this);
      goto LABEL_8;
    }
    goto LABEL_18;
  }
  v8 = VirtualAlloc(a2, v6, a4, flProtect);
  if ( !v8 )
  {
LABEL_18:
    Memory::MemoryOperationLastError::RecordLastError();
    Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v21);
    return 0;
  }
LABEL_8:
  if ( v7 )
  {
    v22 = 0;
    v19 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
    v20 = GetCurrentThread();
    ((void (__fastcall *)(HANDLE, __int64, int *))v19)(v20, 2, &v22);
  }
  return v8;
}

```

## disassembly

```asm
0x180075b24  mov     rax, rsp
0x180075b27  mov     [rax+20h], r9d
0x180075b2b  mov     [rax+18h], r8
0x180075b2f  mov     [rax+10h], rdx
0x180075b33  mov     [rax+8], rcx
0x180075b37  push    rbp
0x180075b38  push    rbx
0x180075b39  push    rsi
0x180075b3a  push    rdi
0x180075b3b  push    r12
0x180075b3d  mov     rbp, rsp
0x180075b40  sub     rsp, 50h
0x180075b44  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180075b4c  mov     rax, 0FFFFFFFFFFFFFh
0x180075b56  mov     rdi, [rbp+arg_10]
0x180075b5a  cmp     rdi, rax
0x180075b5d  ja      loc_180075C7F
0x180075b63  shl     rdi, 0Ch
0x180075b67  cmp     [rbp+arg_28], 0
0x180075b6b  jnz     short loc_180075BC7
0x180075b6d  test    byte ptr [rbp+flProtect], 70h
0x180075b71  jnz     short loc_180075BC7
0x180075b73  xor     bl, bl
0x180075b75  mov     [rbp+var_20], bl
0x180075b78  mov     [rbp+flOldProtect], 0
0x180075b7f  mov     r8d, [rbp+flAllocationType]; flAllocationType
0x180075b83  mov     rdx, rdi; dwSize
0x180075b86  mov     rcx, [rbp+lpAddress]; lpAddress
0x180075b8a  cmp     [rbp+arg_28], 0
0x180075b8e  jnz     loc_180075C86
0x180075b94  mov     r9d, [rbp+flProtect]; flProtect
0x180075b98  call    cs:__imp_VirtualAlloc
0x180075b9f  nop     dword ptr [rax+rax+00h]
0x180075ba4  mov     rsi, rax
0x180075ba7  test    rax, rax
0x180075baa  jz      loc_180075C70
0x180075bb0  test    bl, bl
0x180075bb2  jnz     loc_180075DDF
0x180075bb8  mov     rax, rsi
0x180075bbb  add     rsp, 50h
0x180075bbf  pop     r12
0x180075bc1  pop     rdi
0x180075bc2  pop     rsi
0x180075bc3  pop     rbx
0x180075bc4  pop     rbp
0x180075bc5  retn
0x180075bc7  xor     bl, bl
0x180075bc9  mov     [rbp+var_20], bl
0x180075bcc  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180075bd2  test    al, al
0x180075bd4  jz      loc_180075CDD
0x180075bda  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180075be0  test    al, 1
0x180075be2  jz      short loc_180075B78
0x180075be4  test    al, 2
0x180075be6  jz      short loc_180075B78
0x180075be8  cmp     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, 0; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075bf0  jz      short loc_180075B78
0x180075bf2  mov     rsi, cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075bf9  test    rsi, rsi
0x180075bfc  jz      loc_180075B78
0x180075c02  mov     [rbp+var_1C], 0
0x180075c09  call    cs:__imp_GetCurrentThread
0x180075c10  nop     dword ptr [rax+rax+00h]
0x180075c15  mov     rcx, rax
0x180075c18  mov     r9d, 4
0x180075c1e  lea     r8, [rbp+var_1C]
0x180075c22  lea     edx, [r9-2]
0x180075c26  mov     rax, rsi
0x180075c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c2e  test    eax, eax
0x180075c30  jnz     loc_180075DD0
0x180075c36  mov     [rbp+var_1C], 1
0x180075c3d  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075c44  call    cs:__imp_GetCurrentThread
0x180075c4b  nop     dword ptr [rax+rax+00h]
0x180075c50  mov     rcx, rax
0x180075c53  mov     r9d, 4
0x180075c59  lea     r8, [rbp+var_1C]
0x180075c5d  lea     edx, [r9-2]
0x180075c61  mov     rax, rbx
0x180075c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c69  mov     bl, 1
0x180075c6b  jmp     loc_180075B75
0x180075c70  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x180075c75  nop
0x180075c76  lea     rcx, [rbp+var_20]; this
0x180075c7a  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x180075c7f  xor     eax, eax
0x180075c81  jmp     loc_180075BBB
0x180075c86  mov     r9d, 40000040h; flProtect
0x180075c8c  call    cs:__imp_VirtualAlloc
0x180075c93  nop     dword ptr [rax+rax+00h]
0x180075c98  mov     rsi, rax
0x180075c9b  test    rax, rax
0x180075c9e  jz      short loc_180075C70
0x180075ca0  test    [rbp+flAllocationType], 1000h
0x180075ca7  jz      loc_180075BB0
0x180075cad  lea     r9, [rbp+flOldProtect]; lpflOldProtect
0x180075cb1  mov     r8d, [rbp+flProtect]; flNewProtect
0x180075cb5  mov     rdx, rdi; dwSize
0x180075cb8  mov     rcx, rax; lpAddress
0x180075cbb  call    cs:__imp_VirtualProtect
0x180075cc2  nop     dword ptr [rax+rax+00h]
0x180075cc7  test    eax, eax
0x180075cc9  jnz     loc_180075BB0
0x180075ccf  mov     rcx, [rbp+arg_0]; unsigned __int64
0x180075cd3  call    ?CustomHeap_BadPageState_unrecoverable_error@@YAX_K@Z; CustomHeap_BadPageState_unrecoverable_error(unsigned __int64)
0x180075cd8  jmp     loc_180075BB0
0x180075cdd  lea     rax, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x180075ce4  mov     [rbp+var_8], rax
0x180075ce8  mov     rcx, rax; lpCriticalSection
0x180075ceb  call    cs:__imp_EnterCriticalSection
0x180075cf2  nop     dword ptr [rax+rax+00h]
0x180075cf7  nop
0x180075cf8  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180075cfe  test    al, al
0x180075d00  jnz     loc_180075DB7
0x180075d06  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-3.d"...
0x180075d0d  call    cs:__imp_GetModuleHandleW
0x180075d14  nop     dword ptr [rax+rax+00h]
0x180075d19  mov     rsi, rax
0x180075d1c  test    rax, rax
0x180075d1f  jz      loc_180075DA9
0x180075d25  lea     rdx, ProcName; "GetProcessMitigationPolicy"
0x180075d2c  mov     rcx, rax; hModule
0x180075d2f  call    cs:__imp_GetProcAddress
0x180075d36  nop     dword ptr [rax+rax+00h]
0x180075d3b  mov     r12, rax
0x180075d3e  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x180075d45  mov     rcx, rsi; hModule
0x180075d48  call    cs:__imp_GetProcAddress
0x180075d4f  nop     dword ptr [rax+rax+00h]
0x180075d54  mov     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075d5b  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x180075d62  mov     rcx, rsi; hModule
0x180075d65  call    cs:__imp_GetProcAddress
0x180075d6c  nop     dword ptr [rax+rax+00h]
0x180075d71  mov     cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, rax; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075d78  test    r12, r12
0x180075d7b  jz      short loc_180075DA9
0x180075d7d  call    cs:__imp_GetCurrentProcess
0x180075d84  nop     dword ptr [rax+rax+00h]
0x180075d89  mov     rcx, rax
0x180075d8c  mov     r9d, 4
0x180075d92  lea     r8, ?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180075d99  lea     edx, [r9-2]
0x180075d9d  mov     rax, r12
0x180075da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075da5  test    eax, eax
0x180075da7  jnz     short loc_180075DB0
0x180075da9  and     cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A, 0FFFFFFFEh; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180075db0  mov     cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC, 1; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x180075db7  lea     rcx, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; lpCriticalSection
0x180075dbe  call    cs:__imp_LeaveCriticalSection
0x180075dc5  nop     dword ptr [rax+rax+00h]
0x180075dca  nop
0x180075dcb  jmp     loc_180075BDA
0x180075dd0  cmp     [rbp+var_1C], 1
0x180075dd4  jz      loc_180075B78
0x180075dda  jmp     loc_180075C36
0x180075ddf  mov     [rbp+var_1C], 0
0x180075de6  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180075ded  call    cs:__imp_GetCurrentThread
0x180075df4  nop     dword ptr [rax+rax+00h]
0x180075df9  mov     rcx, rax
0x180075dfc  mov     r9d, 4
0x180075e02  lea     r8, [rbp+var_1C]
0x180075e06  lea     edx, [r9-2]
0x180075e0a  mov     rax, rbx
0x180075e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e12  jmp     loc_180075BB8
```
