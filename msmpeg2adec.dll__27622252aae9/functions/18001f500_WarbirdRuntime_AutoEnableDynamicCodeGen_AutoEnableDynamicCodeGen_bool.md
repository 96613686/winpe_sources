# WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(bool)

- ea: `0x18001f500`
- end: `0x18001f7cd`
- name: `??0AutoEnableDynamicCodeGen@WarbirdRuntime@@QEAA@_N@Z`
- size: `717`
- prototype: `__int64 __fastcall(WarbirdRuntime::AutoEnableDynamicCodeGen *__hidden this, bool)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022470`
- `0x180022820`
- `0x180022bd0`
- `0x180022f00`
- `0x1800232d0`
- `0x1800236a0`

## callees

- `0x18001f500`
- `0x1800221c0`
- `0x180022330`
- `0x180025060`
- `0x180025190`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f542`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f643`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f542`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001f643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f57d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f59a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f686`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f560`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f57d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f59a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f686`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f66b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f66b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f5b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f5b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f72c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f76b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f72c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f76b`

## string_xrefs

- `0x18001f53b`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x18001f56c`: `SetThreadInformation`
- `0x18001f589`: `GetThreadInformation`
- `0x18001f63c`: `api-ms-win-core-localregistry-l1-1-0.dll`
- `0x18001f65e`: `api-ms-win-core-localregistry-l1-1-0.dll`

## pseudocode

```c
WarbirdRuntime::AutoEnableDynamicCodeGen *__fastcall WarbirdRuntime::AutoEnableDynamicCodeGen::AutoEnableDynamicCodeGen(
        WarbirdRuntime::AutoEnableDynamicCodeGen *this,
        char a2)
{
  volatile bool v2; // al
  HMODULE ModuleHandleW; // rax
  HMODULE v5; // rdi
  HANDLE CurrentProcess; // rax
  char Flags; // al
  HMODULE Library; // rax
  WarbirdRuntime::AutoEnableDynamicCodeGen *v9; // rcx
  FARPROC ProcAddress; // rax
  int v11; // edi
  int v12; // edi
  int v13; // edx
  int v14; // edx
  bool v15; // al
  HANDLE CurrentThread; // rax
  HANDLE v17; // rax
  int v19; // edx
  WarbirdRuntime::AutoEnableDynamicCodeGen *v20; // rcx
  int v21; // [rsp+60h] [rbp+8h] BYREF
  int v22; // [rsp+68h] [rbp+10h] BYREF
  int v23; // [rsp+70h] [rbp+18h] BYREF

  LOBYTE(v22) = a2;
  v2 = WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained;
  *(_DWORD *)this = 24604147;
  *((_DWORD *)this + 1) = 1313913263;
  *((_DWORD *)this + 2) = -380232549;
  *((_DWORD *)this + 3) = 81204785;
  *((_BYTE *)this + 16) = 0;
  if ( v2 )
  {
    Flags = WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy.Flags;
  }
  else
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
    v5 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc = (int (*)(void *, enum _PROCESS_MITIGATION_POLICY, void *, unsigned __int64))GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy");
      WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v5, "SetThreadInformation");
      WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v5, "GetThreadInformation");
    }
    if ( WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc
      && (CurrentProcess = GetCurrentProcess(),
          (unsigned int)((__int64 (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc)(
                          CurrentProcess,
                          2,
                          &WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy,
                          4)) )
    {
      Flags = WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy.Flags;
      WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
    }
    else
    {
      Flags = WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy.Flags & 0xFE;
      WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy.Flags &= ~1u;
      WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
    }
  }
  if ( (Flags & 1) == 0 )
    return this;
  if ( (Flags & 2) == 0 && !WarbirdRuntime::AutoEnableDynamicCodeGen::disableACGCalled )
  {
    Library = GetModuleHandleW(L"api-ms-win-core-localregistry-l1-1-0.dll");
    v23 = 0;
    v21 = 0;
    if ( !Library )
    {
      Library = LoadLibraryExW(L"api-ms-win-core-localregistry-l1-1-0.dll", 0, 0x800u);
      if ( !Library )
        goto LABEL_19;
    }
    ProcAddress = GetProcAddress(Library, "RegGetValueW");
    if ( !ProcAddress )
      goto LABEL_19;
    v11 = 0;
    if ( !((unsigned int (__fastcall *)(__int64, const wchar_t *, const wchar_t *, __int64, _QWORD, int *, int *))ProcAddress)(
            -2147483646,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SoftwareProtectionPlatform",
            L"AcgApi",
            16,
            0,
            &v21,
            &v23) )
      v11 = v21;
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 == 1 )
      {
LABEL_21:
        if ( !WarbirdRuntime::AutoEnableDynamicCodeGen::LoadLicensingBrokerApis(v9) )
          goto LABEL_25;
        v15 = WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaLicensingBroker(this, v14);
LABEL_23:
        if ( !v15 )
          goto LABEL_25;
        goto LABEL_24;
      }
LABEL_19:
      if ( WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(v9)
        && WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(v9, v13) )
      {
LABEL_24:
        WarbirdRuntime::AutoEnableDynamicCodeGen::disableACGCalled = 1;
        goto LABEL_25;
      }
      goto LABEL_21;
    }
    if ( WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(v9) )
    {
      v15 = WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(v20, v19);
      goto LABEL_23;
    }
  }
LABEL_25:
  if ( WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc )
  {
    if ( WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc )
    {
      v22 = 0;
      CurrentThread = GetCurrentThread();
      if ( !(unsigned int)((__int64 (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc)(
                            CurrentThread,
                            2,
                            &v22,
                            4)
        || v22 != 1 )
      {
        v22 = 1;
        v17 = GetCurrentThread();
        ((void (__fastcall *)(HANDLE, __int64, int *, __int64))WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(
          v17,
          2,
          &v22,
          4);
        *((_BYTE *)this + 16) = 1;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001f500  mov     byte ptr [rsp+arg_8], dl
0x18001f504  push    rbx
0x18001f505  push    rdi
0x18001f506  sub     rsp, 48h
0x18001f50a  movzx   eax, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@WarbirdRuntime@@0_NC; bool volatile WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained
0x18001f511  mov     rbx, rcx
0x18001f514  mov     dword ptr [rcx], 1776DF3h
0x18001f51a  mov     dword ptr [rcx+4], 4E50B9AFh
0x18001f521  mov     dword ptr [rcx+8], 0E9561C9Bh
0x18001f528  mov     dword ptr [rcx+0Ch], 4D71631h
0x18001f52f  mov     byte ptr [rcx+10h], 0
0x18001f533  test    al, al
0x18001f535  jnz     loc_18001F610
0x18001f53b  lea     rcx, aApiMsWinCorePr_3; "api-ms-win-core-processthreads-l1-1-3.d"...
0x18001f542  call    cs:__imp_GetModuleHandleW
0x18001f549  nop     dword ptr [rax+rax+00h]
0x18001f54e  mov     rdi, rax
0x18001f551  test    rax, rax
0x18001f554  jz      short loc_18001F5AD
0x18001f556  lea     rdx, aGetprocessmiti; "GetProcessMitigationPolicy"
0x18001f55d  mov     rcx, rax; hModule
0x18001f560  call    cs:__imp_GetProcAddress
0x18001f567  nop     dword ptr [rax+rax+00h]
0x18001f56c  lea     rdx, aSetthreadinfor; "SetThreadInformation"
0x18001f573  mov     rcx, rdi; hModule
0x18001f576  mov     cs:?GetProcessMitigationPolicyProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@ZEA, rax; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc)(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x18001f57d  call    cs:__imp_GetProcAddress
0x18001f584  nop     dword ptr [rax+rax+00h]
0x18001f589  lea     rdx, aGetthreadinfor; "GetThreadInformation"
0x18001f590  mov     rcx, rdi; hModule
0x18001f593  mov     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA, rax; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f59a  call    cs:__imp_GetProcAddress
0x18001f5a1  nop     dword ptr [rax+rax+00h]
0x18001f5a6  mov     cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA, rax; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f5ad  cmp     cs:?GetProcessMitigationPolicyProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@ZEA, 0; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc)(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x18001f5b5  jz      short loc_18001F5F8
0x18001f5b7  call    cs:__imp_GetCurrentProcess
0x18001f5be  nop     dword ptr [rax+rax+00h]
0x18001f5c3  mov     r9d, 4
0x18001f5c9  lea     r8, ?processPolicy@AutoEnableDynamicCodeGen@WarbirdRuntime@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@12@A; WarbirdRuntime::AutoEnableDynamicCodeGen::_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy
0x18001f5d0  mov     rcx, rax
0x18001f5d3  mov     edx, 2
0x18001f5d8  mov     rax, cs:?GetProcessMitigationPolicyProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_PROCESS_MITIGATION_POLICY@@0_K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetProcessMitigationPolicyProc)(void *,_PROCESS_MITIGATION_POLICY,void *,unsigned __int64)
0x18001f5df  call    cs:__guard_dispatch_icall_fptr
0x18001f5e5  test    eax, eax
0x18001f5e7  jz      short loc_18001F5F8
0x18001f5e9  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@WarbirdRuntime@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@12@A; WarbirdRuntime::AutoEnableDynamicCodeGen::_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy
0x18001f5ef  mov     cs:?processPolicyObtained@AutoEnableDynamicCodeGen@WarbirdRuntime@@0_NC, 1; bool volatile WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained
0x18001f5f6  jmp     short loc_18001F616
0x18001f5f8  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@WarbirdRuntime@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@12@A; WarbirdRuntime::AutoEnableDynamicCodeGen::_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy
0x18001f5fe  and     eax, 0FFFFFFFEh
0x18001f601  mov     cs:?processPolicy@AutoEnableDynamicCodeGen@WarbirdRuntime@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@12@A, eax; WarbirdRuntime::AutoEnableDynamicCodeGen::_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy
0x18001f607  mov     cs:?processPolicyObtained@AutoEnableDynamicCodeGen@WarbirdRuntime@@0_NC, 1; bool volatile WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicyObtained
0x18001f60e  jmp     short loc_18001F616
0x18001f610  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@WarbirdRuntime@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@12@A; WarbirdRuntime::AutoEnableDynamicCodeGen::_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY WarbirdRuntime::AutoEnableDynamicCodeGen::processPolicy
0x18001f616  test    al, 1
0x18001f618  jz      loc_18001F7C2
0x18001f61e  mov     [rsp+58h+var_18], rsi
0x18001f623  xor     esi, esi
0x18001f625  test    al, 2
0x18001f627  jnz     loc_18001F716
0x18001f62d  movzx   eax, cs:?disableACGCalled@AutoEnableDynamicCodeGen@WarbirdRuntime@@0_NC; bool volatile WarbirdRuntime::AutoEnableDynamicCodeGen::disableACGCalled
0x18001f634  test    al, al
0x18001f636  jnz     loc_18001F716
0x18001f63c  lea     rcx, aApiMsWinCoreLo_0; "api-ms-win-core-localregistry-l1-1-0.dl"...
0x18001f643  call    cs:__imp_GetModuleHandleW
0x18001f64a  nop     dword ptr [rax+rax+00h]
0x18001f64f  mov     [rsp+58h+arg_10], esi
0x18001f653  mov     [rsp+58h+arg_0], esi
0x18001f657  test    rax, rax
0x18001f65a  jnz     short loc_18001F67C
0x18001f65c  xor     edx, edx; hFile
0x18001f65e  lea     rcx, aApiMsWinCoreLo_0; "api-ms-win-core-localregistry-l1-1-0.dl"...
0x18001f665  mov     r8d, 800h; dwFlags
0x18001f66b  call    cs:__imp_LoadLibraryExW
0x18001f672  nop     dword ptr [rax+rax+00h]
0x18001f677  test    rax, rax
0x18001f67a  jz      short loc_18001F6E8
0x18001f67c  lea     rdx, aReggetvaluew; "RegGetValueW"
0x18001f683  mov     rcx, rax; hModule
0x18001f686  call    cs:__imp_GetProcAddress
0x18001f68d  nop     dword ptr [rax+rax+00h]
0x18001f692  test    rax, rax
0x18001f695  jz      short loc_18001F6E8
0x18001f697  lea     rcx, [rsp+58h+arg_10]
0x18001f69c  mov     r9d, 10h
0x18001f6a2  mov     [rsp+58h+var_28], rcx
0x18001f6a7  lea     r8, aAcgapi; "AcgApi"
0x18001f6ae  lea     rcx, [rsp+58h+arg_0]
0x18001f6b3  mov     edi, esi
0x18001f6b5  mov     [rsp+58h+var_30], rcx
0x18001f6ba  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f6c1  mov     rcx, 0FFFFFFFF80000002h
0x18001f6c8  mov     [rsp+58h+var_38], rsi
0x18001f6cd  call    cs:__guard_dispatch_icall_fptr
0x18001f6d3  test    eax, eax
0x18001f6d5  cmovz   edi, [rsp+58h+arg_0]
0x18001f6da  sub     edi, 1
0x18001f6dd  jz      loc_18001F7AB
0x18001f6e3  cmp     edi, 1
0x18001f6e6  jz      short loc_18001F6FA
0x18001f6e8  call    ?LoadEdgeBrokerApis@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NXZ; WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(void)
0x18001f6ed  test    al, al
0x18001f6ef  jz      short loc_18001F6FA
0x18001f6f1  call    ?DisableAcgViaEdgeBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(int)
0x18001f6f6  test    al, al
0x18001f6f8  jnz     short loc_18001F70F
0x18001f6fa  call    ?LoadLicensingBrokerApis@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NXZ; WarbirdRuntime::AutoEnableDynamicCodeGen::LoadLicensingBrokerApis(void)
0x18001f6ff  test    al, al
0x18001f701  jz      short loc_18001F716
0x18001f703  mov     rcx, rbx; this
0x18001f706  call    ?DisableAcgViaLicensingBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaLicensingBroker(int)
0x18001f70b  test    al, al
0x18001f70d  jz      short loc_18001F716
0x18001f70f  mov     cs:?disableACGCalled@AutoEnableDynamicCodeGen@WarbirdRuntime@@0_NC, 1; bool volatile WarbirdRuntime::AutoEnableDynamicCodeGen::disableACGCalled
0x18001f716  cmp     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA, rsi; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f71d  jz      short loc_18001F79B
0x18001f71f  cmp     cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA, rsi; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f726  jz      short loc_18001F79B
0x18001f728  mov     [rsp+58h+arg_8], esi
0x18001f72c  call    cs:__imp_GetCurrentThread
0x18001f733  nop     dword ptr [rax+rax+00h]
0x18001f738  mov     r9d, 4
0x18001f73e  lea     r8, [rsp+58h+arg_8]
0x18001f743  mov     rcx, rax
0x18001f746  mov     edx, 2
0x18001f74b  mov     rax, cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f752  call    cs:__guard_dispatch_icall_fptr
0x18001f758  test    eax, eax
0x18001f75a  jz      short loc_18001F763
0x18001f75c  cmp     [rsp+58h+arg_8], 1
0x18001f761  jz      short loc_18001F79B
0x18001f763  mov     [rsp+58h+arg_8], 1
0x18001f76b  call    cs:__imp_GetCurrentThread
0x18001f772  nop     dword ptr [rax+rax+00h]
0x18001f777  mov     r9d, 4
0x18001f77d  lea     r8, [rsp+58h+arg_8]
0x18001f782  mov     rcx, rax
0x18001f785  mov     edx, 2
0x18001f78a  mov     rax, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@WarbirdRuntime@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@12@0K@ZEA; int (*WarbirdRuntime::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,WarbirdRuntime::AutoEnableDynamicCodeGen::_THREAD_INFORMATION_CLASS,void *,ulong)
0x18001f791  call    cs:__guard_dispatch_icall_fptr
0x18001f797  mov     byte ptr [rbx+10h], 1
0x18001f79b  mov     rsi, [rsp+58h+var_18]
0x18001f7a0  mov     rax, rbx
0x18001f7a3  add     rsp, 48h
0x18001f7a7  pop     rdi
0x18001f7a8  pop     rbx
0x18001f7a9  retn
0x18001f7ab  call    ?LoadEdgeBrokerApis@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NXZ; WarbirdRuntime::AutoEnableDynamicCodeGen::LoadEdgeBrokerApis(void)
0x18001f7b0  test    al, al
0x18001f7b2  jz      loc_18001F716
0x18001f7b8  call    ?DisableAcgViaEdgeBroker@AutoEnableDynamicCodeGen@WarbirdRuntime@@AEAA_NH@Z; WarbirdRuntime::AutoEnableDynamicCodeGen::DisableAcgViaEdgeBroker(int)
0x18001f7bd  jmp     loc_18001F70B
0x18001f7c2  mov     rax, rbx
0x18001f7c5  add     rsp, 48h
0x18001f7c9  pop     rdi
0x18001f7ca  pop     rbx
0x18001f7cb  retn
```
