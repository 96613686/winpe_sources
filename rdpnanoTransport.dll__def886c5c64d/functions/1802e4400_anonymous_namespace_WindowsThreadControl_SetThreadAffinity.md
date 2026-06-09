# _anonymous_namespace_::WindowsThreadControl::SetThreadAffinity

- ea: `0x1802e4400`
- end: `0x1802e45fc`
- name: `_anonymous_namespace_::WindowsThreadControl::SetThreadAffinity`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18004569c`
- `0x1802e4400`
- `0x1802e4a40`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802e4526`
- `KERNEL32!GetLastError` at `0x1802e4526`
- `KERNEL32!GetCurrentProcess` at `0x1802e443f`
- `KERNEL32!GetCurrentProcess` at `0x1802e443f`
- `KERNEL32!GetCurrentThread` at `0x1802e44e8`
- `KERNEL32!GetCurrentThread` at `0x1802e44e8`
- `KERNEL32!GetProcessAffinityMask` at `0x1802e4450`
- `KERNEL32!GetProcessAffinityMask` at `0x1802e4450`
- `KERNEL32!SetThreadAffinityMask` at `0x1802e44f4`
- `KERNEL32!SetThreadAffinityMask` at `0x1802e44f4`

## string_xrefs

- `0x1802e44a5`: ``anonymous-namespace'::WindowsThreadControl::SetThreadAffinity`
- `0x1802e4554`: ``anonymous-namespace'::WindowsThreadControl::SetThreadAffinity`
- `0x1802e44b9`: `C:\__w\1\s\src\libbasix\pattern\windowsthreadcontrol.cpp`
- `0x1802e4568`: `C:\__w\1\s\src\libbasix\pattern\windowsthreadcontrol.cpp`
- `0x1802e4494`: `Failed to set thread to default affinity: Failed to get process affinity mask\n    %s(%d): %s()`
- `0x1802e4543`: `Failed to set thread affinity to %zx: %d \n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
DWORD_PTR __fastcall anonymous_namespace_::WindowsThreadControl::SetThreadAffinity(__int64 a1, DWORD_PTR a2)
{
  DWORD_PTR v2; // rdi
  HANDLE CurrentProcess; // rax
  int v4; // r9d
  DWORD_PTR result; // rax
  HANDLE CurrentThread; // rax
  char LastError; // bl
  int v8; // r9d
  volatile signed __int32 *v9; // rdi
  signed __int32 v10; // eax
  bool v11; // zf
  const char *v12; // [rsp+20h] [rbp-19h]
  int v13; // [rsp+28h] [rbp-11h]
  const char *v14; // [rsp+30h] [rbp-9h]
  __int128 v15; // [rsp+40h] [rbp+7h] BYREF
  __int128 v16; // [rsp+50h] [rbp+17h]
  __int128 v17; // [rsp+60h] [rbp+27h] BYREF
  ULONG_PTR ProcessAffinityMask; // [rsp+70h] [rbp+37h] BYREF
  ULONG_PTR SystemAffinityMask; // [rsp+78h] [rbp+3Fh] BYREF

  v2 = a2;
  if ( !a2 )
  {
    ProcessAffinityMask = 0;
    SystemAffinityMask = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask) )
    {
      v17 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v17);
      result = v17;
      if ( (_QWORD)v17 && *(_BYTE *)(v17 + 128) )
      {
        v15 = 0;
        v16 = 0;
        std::string::_Construct<1,char const *>(
          &v15,
          "Failed to set thread to default affinity: Failed to get process affinity mask\n    %s(%d): %s()",
          (const char *)0x5E,
          v4,
          v12);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v17,
          (unsigned int)"BASIX_PATTERN",
          (unsigned int)&v15,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix\\pattern\\windowsthreadcontrol.cpp",
          35,
          (__int64)"`anonymous-namespace'::WindowsThreadControl::SetThreadAffinity");
        result = std::string::_Tidy_deallocate(&v15);
      }
      goto LABEL_12;
    }
    v2 = ProcessAffinityMask;
  }
  CurrentThread = GetCurrentThread();
  result = SetThreadAffinityMask(CurrentThread, v2);
  if ( result )
    return result;
  v17 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v17);
  result = v17;
  if ( (_QWORD)v17 && *(_BYTE *)(v17 + 128) )
  {
    LastError = GetLastError();
    v15 = 0;
    v16 = 0;
    std::string::_Construct<1,char const *>(
      &v15,
      "Failed to set thread affinity to %zx: %d \n    %s(%d): %s()",
      0x3Au,
      v8,
      v12,
      v13,
      v14);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,unsigned __int64,unsigned long,char const *,int,char const *>(
      (unsigned int)&v17,
      (unsigned int)"BASIX_PATTERN",
      (unsigned int)&v15,
      v2,
      LastError,
      (__int64)"C:\\__w\\1\\s\\src\\libbasix\\pattern\\windowsthreadcontrol.cpp",
      45,
      (__int64)"`anonymous-namespace'::WindowsThreadControl::SetThreadAffinity");
    result = std::string::_Tidy_deallocate(&v15);
  }
LABEL_12:
  v9 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
  if ( *((_QWORD *)&v17 + 1) )
  {
    v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF);
    v11 = v10 == 1;
    result = (unsigned int)(v10 - 1);
    if ( v11 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      result = (unsigned int)_InterlockedDecrement(v9 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1802e4400  mov     [rsp-8+arg_0], rbx
0x1802e4405  mov     [rsp-8+arg_10], rdi
0x1802e440a  push    rbp
0x1802e440b  lea     rbp, [rsp-57h]
0x1802e4410  mov     eax, 90h
0x1802e4415  call    _alloca_probe
0x1802e441a  sub     rsp, rax
0x1802e441d  mov     rax, cs:__security_cookie
0x1802e4424  xor     rax, rsp
0x1802e4427  mov     [rbp+57h+var_10], rax
0x1802e442b  mov     rdi, rdx
0x1802e442e  test    rdx, rdx
0x1802e4431  jnz     loc_1802E44E8
0x1802e4437  mov     [rbp+57h+ProcessAffinityMask], rdx
0x1802e443b  mov     [rbp+57h+SystemAffinityMask], rdx
0x1802e443f  call    cs:__imp_GetCurrentProcess
0x1802e4445  mov     rcx, rax; hProcess
0x1802e4448  lea     r8, [rbp+57h+SystemAffinityMask]; lpSystemAffinityMask
0x1802e444c  lea     rdx, [rbp+57h+ProcessAffinityMask]; lpProcessAffinityMask
0x1802e4450  call    cs:__imp_GetProcessAffinityMask
0x1802e4456  test    eax, eax
0x1802e4458  jnz     loc_1802E44E4
0x1802e445e  xorps   xmm0, xmm0
0x1802e4461  movups  [rbp+57h+var_30], xmm0
0x1802e4465  lea     rcx, [rbp+57h+var_30]
0x1802e4469  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1802e446e  nop
0x1802e446f  mov     rax, qword ptr [rbp+57h+var_30]
0x1802e4473  test    rax, rax
0x1802e4476  jz      short loc_1802E44DF
0x1802e4478  cmp     [rax+80h], dil
0x1802e447f  jz      short loc_1802E44DF
0x1802e4481  xorps   xmm0, xmm0
0x1802e4484  movups  [rbp+57h+var_50], xmm0
0x1802e4488  xorps   xmm1, xmm1
0x1802e448b  movdqu  [rbp+57h+var_40], xmm1
0x1802e4490  lea     r8d, [rdi+5Eh]
0x1802e4494  lea     rdx, aFailedToSetThr_1; "Failed to set thread to default affinit"...
0x1802e449b  lea     rcx, [rbp+57h+var_50]
0x1802e449f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802e44a4  nop
0x1802e44a5  lea     rax, aAnonymousNames; "`anonymous-namespace'::WindowsThreadCon"...
0x1802e44ac  mov     [rsp+90h+var_68], rax
0x1802e44b1  mov     dword ptr [rsp+90h+var_70], 23h ; '#'
0x1802e44b9  lea     r9, aCW1SSrcLibbasi_48; "C:\\__w\\1\\s\\src\\libbasix\\pattern\\"...
0x1802e44c0  lea     r8, [rbp+57h+var_50]
0x1802e44c4  lea     rdx, aBasixPattern; "BASIX_PATTERN"
0x1802e44cb  lea     rcx, [rbp+57h+var_30]
0x1802e44cf  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1802e44d4  nop
0x1802e44d5  lea     rcx, [rbp+57h+var_50]
0x1802e44d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802e44de  nop
0x1802e44df  jmp     loc_1802E459A
0x1802e44e4  mov     rdi, [rbp+57h+ProcessAffinityMask]
0x1802e44e8  call    cs:__imp_GetCurrentThread
0x1802e44ee  mov     rcx, rax; hThread
0x1802e44f1  mov     rdx, rdi; dwThreadAffinityMask
0x1802e44f4  call    cs:__imp_SetThreadAffinityMask
0x1802e44fa  test    rax, rax
0x1802e44fd  jnz     loc_1802E45DB
0x1802e4503  xorps   xmm0, xmm0
0x1802e4506  movups  [rbp+57h+var_30], xmm0
0x1802e450a  lea     rcx, [rbp+57h+var_30]
0x1802e450e  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1802e4513  nop
0x1802e4514  mov     rax, qword ptr [rbp+57h+var_30]
0x1802e4518  test    rax, rax
0x1802e451b  jz      short loc_1802E459A
0x1802e451d  cmp     byte ptr [rax+80h], 0
0x1802e4524  jz      short loc_1802E459A
0x1802e4526  call    cs:__imp_GetLastError
0x1802e452c  mov     ebx, eax
0x1802e452e  xorps   xmm0, xmm0
0x1802e4531  movups  [rbp+57h+var_50], xmm0
0x1802e4535  xorps   xmm1, xmm1
0x1802e4538  movdqu  [rbp+57h+var_40], xmm1
0x1802e453d  mov     r8d, 3Ah ; ':'
0x1802e4543  lea     rdx, aFailedToSetThr; "Failed to set thread affinity to %zx: %"...
0x1802e454a  lea     rcx, [rbp+57h+var_50]
0x1802e454e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1802e4553  nop
0x1802e4554  lea     rax, aAnonymousNames; "`anonymous-namespace'::WindowsThreadCon"...
0x1802e455b  mov     [rsp+90h+var_58], rax
0x1802e4560  mov     dword ptr [rsp+90h+var_60], 2Dh ; '-'
0x1802e4568  lea     rax, aCW1SSrcLibbasi_48; "C:\\__w\\1\\s\\src\\libbasix\\pattern\\"...
0x1802e456f  mov     [rsp+90h+var_68], rax
0x1802e4574  mov     dword ptr [rsp+90h+var_70], ebx
0x1802e4578  mov     r9, rdi
0x1802e457b  lea     r8, [rbp+57h+var_50]
0x1802e457f  lea     rdx, aBasixPattern; "BASIX_PATTERN"
0x1802e4586  lea     rcx, [rbp+57h+var_30]
0x1802e458a  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@_KKPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_KK1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,unsigned __int64,ulong,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,unsigned __int64,ulong,char const *,int,char const *)
0x1802e458f  nop
0x1802e4590  lea     rcx, [rbp+57h+var_50]
0x1802e4594  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1802e4599  nop
0x1802e459a  mov     rdi, qword ptr [rbp+57h+var_30+8]
0x1802e459e  test    rdi, rdi
0x1802e45a1  jz      short loc_1802E45DB
0x1802e45a3  or      ebx, 0FFFFFFFFh
0x1802e45a6  mov     eax, ebx
0x1802e45a8  lock xadd [rdi+8], eax
0x1802e45ad  add     eax, ebx
0x1802e45af  jnz     short loc_1802E45DB
0x1802e45b1  mov     rax, [rdi]
0x1802e45b4  mov     rcx, rdi
0x1802e45b7  mov     rax, [rax]
0x1802e45ba  call    cs:__guard_dispatch_icall_fptr
0x1802e45c0  mov     eax, ebx
0x1802e45c2  lock xadd [rdi+0Ch], eax
0x1802e45c7  add     eax, ebx
0x1802e45c9  jnz     short loc_1802E45DB
0x1802e45cb  mov     rax, [rdi]
0x1802e45ce  mov     rcx, rdi
0x1802e45d1  mov     rax, [rax+8]
0x1802e45d5  call    cs:__guard_dispatch_icall_fptr
0x1802e45db  mov     rcx, [rbp+57h+var_10]
0x1802e45df  xor     rcx, rsp; StackCookie
0x1802e45e2  call    __security_check_cookie
0x1802e45e7  lea     r11, [rsp+90h+var_s0]
0x1802e45ef  mov     rbx, [r11+10h]
0x1802e45f3  mov     rdi, [r11+20h]
0x1802e45f7  mov     rsp, r11
0x1802e45fa  pop     rbp
0x1802e45fb  retn
```
