# CSimpleRegWrapper::CSimpleRegWrapper(ushort const *,int,ulong,int)

- ea: `0x180019444`
- end: `0x180019725`
- name: `??0CSimpleRegWrapper@@QEAA@PEBGHKH@Z`
- size: `737`
- prototype: `CSimpleRegWrapper *__fastcall(CSimpleRegWrapper *this, const unsigned __int16 *, int, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001360`
- `0x1800198dc`
- `0x1800199ec`

## callees

- `0x180005df0`
- `0x180013cd0`
- `0x180019444`
- `0x1800304ec`
- `0x180034fd4`
- `0x1800366a8`
- `0x180037964`
- `0x18003f280`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18001950a`
- `KERNEL32!DebugBreak` at `0x18001950a`
- `KERNEL32!TerminateProcess` at `0x18001951e`
- `KERNEL32!TerminateProcess` at `0x18001951e`
- `KERNEL32!GetCurrentProcess` at `0x180019510`
- `KERNEL32!GetCurrentProcess` at `0x180019510`

## string_xrefs

- `0x1800195e3`: `ngenserviceclientlock.dat`

## pseudocode

```c
CSimpleRegWrapper *__fastcall CSimpleRegWrapper::CSimpleRegWrapper(
        CSimpleRegWrapper *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        int a5)
{
  char *v9; // rsi
  void (__fastcall ***v10)(MachineWideMutexHolder *__hidden, const unsigned __int16 *, void *, int *); // rbx
  int v11; // eax
  HANDLE CurrentProcess; // rax
  REGSAM v13; // r14d
  _QWORD *v14; // rax
  unsigned int v15; // r8d
  unsigned __int16 *v16; // r9
  _QWORD *v17; // rbx
  void (__fastcall *v18)(MachineWideMutexHolder *__hidden, const unsigned __int16 *, void *, int *); // rax
  void (__fastcall *v19)(VersionedMutexHolder *__hidden, const unsigned __int16 *, void *, int *); // rax
  VersionedMutexHolder *v20; // rcx
  _QWORD *v21; // rax
  int v22; // edi
  __int64 v23; // rax
  unsigned int v25; // ecx
  struct _SECURITY_ATTRIBUTES *v26; // [rsp+30h] [rbp-50h]
  unsigned int *v27; // [rsp+40h] [rbp-40h]
  HKEY v28; // [rsp+C8h] [rbp+48h] BYREF
  bool v29; // [rsp+D0h] [rbp+50h] BYREF

  *(_QWORD *)this = &IRegWrapper::`vftable';
  v9 = (char *)this + 8;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  v10 = (void (__fastcall ***)(MachineWideMutexHolder *__hidden, const unsigned __int16 *, void *, int *))((char *)this + 24);
  *((_QWORD *)this + 3) = &FileLockHolder::`vftable';
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 3) = &MachineWideMutexHolder::`vftable';
  *((_QWORD *)this + 5) = &FileLockHolder::`vftable';
  *((_QWORD *)this + 6) = -1;
  *((_QWORD *)this + 5) = &VersionedMutexHolder::`vftable';
  *(_QWORD *)this = &CSimpleRegWrapper::`vftable';
  v11 = g_registryCounter;
  if ( g_registryCounter != -1 )
  {
    --g_registryCounter;
    if ( v11 == 1 )
    {
      if ( CLRConfig::GetConfigValue(
             (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_BreakOnNGenRegistryAccessCount,
             1,
             &v29) == 1 )
        DebugBreak();
      CurrentProcess = GetCurrentProcess();
      TerminateProcess(CurrentProcess, 1u);
    }
  }
  v13 = (a3 != 0 ? 9 : 65551) | a4;
  if ( a3 )
  {
    v14 = operator new(0x18u);
    v17 = v14;
    if ( v14 )
    {
      *v14 = &IRegWrapper::Key::`vftable';
      *v14 = &CSimpleRegWrapper::RegistryKey::`vftable';
      v14[2] = 0;
      *((_DWORD *)v14 + 2) = v13;
      *v14 = &CSimpleRegWrapper::ReadOnlyRegKey::`vftable';
    }
    else
    {
      v17 = 0;
    }
  }
  else
  {
    if ( a5 )
    {
      if ( !NGENService::g_bProcessNGENService && !NgenTask::g_LegacyServiceBehavior )
      {
        v18 = **v10;
        if ( v18 == MachineWideMutexHolder::Acquire )
          MachineWideMutexHolder::Acquire((MachineWideMutexHolder *)v10, L"ngenserviceclientlock.dat", 0, 0);
        else
          v18((MachineWideMutexHolder *)v10, L"ngenserviceclientlock.dat", 0, 0);
      }
      v19 = *v10[2];
      v20 = (VersionedMutexHolder *)(v10 + 2);
      if ( v19 == VersionedMutexHolder::Acquire )
        VersionedMutexHolder::Acquire(v20, L"ngenrootstorelock.dat", 0, 0);
      else
        v19(v20, L"ngenrootstorelock.dat", 0, 0);
    }
    v21 = operator new(0x18u);
    v17 = v21;
    if ( v21 )
    {
      *v21 = &IRegWrapper::Key::`vftable';
      *v21 = &CSimpleRegWrapper::RegistryKey::`vftable';
      v21[2] = 0;
      *((_DWORD *)v21 + 2) = v13;
    }
    else
    {
      v17 = 0;
    }
  }
  if ( *a2 )
  {
    v22 = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, a2, v15, v16, 0, v13, v26, &v28, v27);
    if ( v22 )
    {
      if ( v17 )
        (*(void (__fastcall **)(_QWORD *, __int64))*v17)(v17, 1);
      v25 = (unsigned __int16)v22 | 0x80070000;
      if ( v22 <= 0 )
        v25 = v22;
      ThrowHR(v25);
    }
    v23 = (__int64)v28;
  }
  else
  {
    v23 = -2147483646;
    v28 = HKEY_LOCAL_MACHINE;
  }
  v17[2] = v23;
  if ( *((_DWORD *)v9 + 2) && *(_QWORD *)v9 )
    (***(void (__fastcall ****)(_QWORD, __int64))v9)(*(_QWORD *)v9, 1);
  *(_QWORD *)v9 = v17;
  *((_DWORD *)v9 + 2) = 1;
  return this;
}

```

## disassembly

```asm
0x180019444  mov     [rsp-38h+arg_18], rbx
0x180019449  mov     [rsp-38h+arg_0], rcx
0x18001944e  push    rbp
0x18001944f  push    rsi
0x180019450  push    rdi
0x180019451  push    r12
0x180019453  push    r13
0x180019455  push    r14
0x180019457  push    r15
0x180019459  mov     rbp, rsp
0x18001945c  sub     rsp, 80h
0x180019463  mov     r14d, r9d
0x180019466  mov     edi, r8d
0x180019469  mov     r15, rdx
0x18001946c  mov     r12, rcx
0x18001946f  lea     rax, ??_7IRegWrapper@@6B@; const IRegWrapper::`vftable'
0x180019476  mov     [rcx], rax
0x180019479  lea     rsi, [rcx+8]
0x18001947d  mov     [rbp+var_30], rsi
0x180019481  xor     r13d, r13d
0x180019484  mov     [rsi], r13
0x180019487  mov     [rsi+8], r13d
0x18001948b  lea     rbx, [rcx+18h]
0x18001948f  mov     [rbp+var_28], rbx
0x180019493  mov     [rbp+var_20], rbx
0x180019497  lea     rdx, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001949e  mov     [rbx], rdx
0x1800194a1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800194a5  mov     [rbx+8], rcx
0x1800194a9  lea     rax, ??_7MachineWideMutexHolder@@6B@; const MachineWideMutexHolder::`vftable'
0x1800194b0  mov     [rbx], rax
0x1800194b3  lea     rax, [rbx+10h]
0x1800194b7  mov     [rbp+var_10], rax
0x1800194bb  mov     [rax], rdx
0x1800194be  mov     [rax+8], rcx
0x1800194c2  lea     rcx, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x1800194c9  mov     [rax], rcx
0x1800194cc  lea     rax, ??_7CSimpleRegWrapper@@6B@; const CSimpleRegWrapper::`vftable'
0x1800194d3  mov     [r12], rax
0x1800194d7  lea     edx, [r13+1]; bool
0x1800194db  mov     eax, cs:?g_registryCounter@@3VRegistryCounter@@A; RegistryCounter g_registryCounter
0x1800194e1  or      ecx, 0FFFFFFFFh
0x1800194e4  cmp     eax, ecx
0x1800194e6  jz      short loc_180019529
0x1800194e8  add     eax, ecx
0x1800194ea  mov     cs:?g_registryCounter@@3VRegistryCounter@@A, eax; RegistryCounter g_registryCounter
0x1800194f0  jnz     short loc_180019529
0x1800194f2  lea     r8, [rbp+arg_10]; bool *
0x1800194f6  lea     rcx, ?UNSUPPORTED_BreakOnNGenRegistryAccessCount@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800194fd  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180019502  lea     edx, [r13+1]
0x180019506  cmp     eax, edx
0x180019508  jnz     short loc_180019510
0x18001950a  call    cs:__imp_DebugBreak
0x180019510  call    cs:__imp_GetCurrentProcess
0x180019516  mov     rcx, rax; hProcess
0x180019519  mov     edx, 1; uExitCode
0x18001951e  call    cs:__imp_TerminateProcess
0x180019524  mov     edx, 1
0x180019529  mov     eax, edi
0x18001952b  neg     eax
0x18001952d  sbb     ecx, ecx
0x18001952f  and     ecx, 0FFFEFFFAh
0x180019535  add     ecx, 1000Fh
0x18001953b  or      r14d, ecx
0x18001953e  test    edi, edi
0x180019540  jz      short loc_180019588
0x180019542  mov     ecx, 18h; dwBytes
0x180019547  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001954c  mov     rbx, rax
0x18001954f  mov     [rbp+var_10], rax
0x180019553  test    rax, rax
0x180019556  jz      short loc_180019580
0x180019558  lea     rax, ??_7Key@IRegWrapper@@6B@; const IRegWrapper::Key::`vftable'
0x18001955f  mov     [rbx], rax
0x180019562  lea     rax, ??_7RegistryKey@CSimpleRegWrapper@@6B@; const CSimpleRegWrapper::RegistryKey::`vftable'
0x180019569  mov     [rbx], rax
0x18001956c  mov     [rbx+10h], r13
0x180019570  mov     [rbx+8], r14d
0x180019574  lea     rax, ??_7ReadOnlyRegKey@CSimpleRegWrapper@@6B@; const CSimpleRegWrapper::ReadOnlyRegKey::`vftable'
0x18001957b  mov     [rbx], rax
0x18001957e  jmp     short loc_180019583
0x180019580  mov     rbx, r13
0x180019583  jmp     loc_18001966D
0x180019588  cmp     [rbp+arg_20], r13d
0x18001958c  jz      loc_180019636
0x180019592  lea     rdi, [rbx+10h]
0x180019596  mov     [rbp+var_10], rdi
0x18001959a  mov     [rbp+var_8], r13d
0x18001959e  mov     eax, r13d
0x1800195a1  test    rdi, rdi
0x1800195a4  cmovnz  eax, edx
0x1800195a7  mov     [rbp+var_8], eax
0x1800195aa  mov     [rbp+var_20], rbx
0x1800195ae  mov     [rbp+var_18], r13d
0x1800195b2  mov     eax, r13d
0x1800195b5  test    rbx, rbx
0x1800195b8  cmovnz  eax, edx
0x1800195bb  mov     [rbp+var_18], eax
0x1800195be  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, r13b; bool NGENService::g_bProcessNGENService
0x1800195c5  jnz     short loc_1800195FF
0x1800195c7  cmp     cs:?g_LegacyServiceBehavior@NgenTask@@3_NA, r13b; bool NgenTask::g_LegacyServiceBehavior
0x1800195ce  jnz     short loc_1800195FF
0x1800195d0  mov     rax, [rbx]
0x1800195d3  mov     rax, [rax]
0x1800195d6  lea     rcx, ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x1800195dd  xor     r9d, r9d; int *
0x1800195e0  xor     r8d, r8d; void *
0x1800195e3  lea     rdx, aNgenservicecli; "ngenserviceclientlock.dat"
0x1800195ea  cmp     rax, rcx
0x1800195ed  mov     rcx, rbx; this
0x1800195f0  jnz     short loc_1800195F9
0x1800195f2  call    ?Acquire@MachineWideMutexHolder@@UEAAXPEBGPEAXPEAH@Z; MachineWideMutexHolder::Acquire(ushort const *,void *,int *)
0x1800195f7  jmp     short loc_1800195FF
0x1800195f9  call    cs:__guard_dispatch_icall_fptr
0x1800195ff  mov     rax, [rdi]
0x180019602  mov     rax, [rax]
0x180019605  lea     rcx, ?Acquire@VersionedMutexHolder@@UEAAXPEBGPEAXPEAH@Z; VersionedMutexHolder::Acquire(ushort const *,void *,int *)
0x18001960c  xor     r9d, r9d; int *
0x18001960f  xor     r8d, r8d; void *
0x180019612  lea     rdx, aNgenrootstorel; "ngenrootstorelock.dat"
0x180019619  cmp     rax, rcx
0x18001961c  mov     rcx, rdi; this
0x18001961f  jnz     short loc_180019628
0x180019621  call    ?Acquire@VersionedMutexHolder@@UEAAXPEBGPEAXPEAH@Z; VersionedMutexHolder::Acquire(ushort const *,void *,int *)
0x180019626  jmp     short loc_18001962E
0x180019628  call    cs:__guard_dispatch_icall_fptr
0x18001962e  mov     [rbp+var_8], r13d
0x180019632  mov     [rbp+var_18], r13d
0x180019636  mov     ecx, 18h; dwBytes
0x18001963b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019640  mov     rbx, rax
0x180019643  mov     [rbp+var_10], rax
0x180019647  test    rax, rax
0x18001964a  jz      short loc_18001966A
0x18001964c  lea     rax, ??_7Key@IRegWrapper@@6B@; const IRegWrapper::Key::`vftable'
0x180019653  mov     [rbx], rax
0x180019656  lea     rax, ??_7RegistryKey@CSimpleRegWrapper@@6B@; const CSimpleRegWrapper::RegistryKey::`vftable'
0x18001965d  mov     [rbx], rax
0x180019660  mov     [rbx+10h], r13
0x180019664  mov     [rbx+8], r14d
0x180019668  jmp     short loc_18001966D
0x18001966a  mov     rbx, r13
0x18001966d  cmp     [r15], r13w
0x180019671  jz      short loc_1800196A1
0x180019673  lea     rax, [rbp+arg_8]
0x180019677  mov     [rsp+80h+var_48], rax; HKEY *
0x18001967c  mov     [rsp+80h+var_58], r14d; REGSAM
0x180019681  mov     [rsp+80h+var_60], r13d; DWORD
0x180019686  mov     rdx, r15; unsigned __int16 *
0x180019689  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180019690  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180019695  mov     edi, eax
0x180019697  test    eax, eax
0x180019699  jnz     short loc_1800196F8
0x18001969b  mov     rax, [rbp+arg_8]
0x18001969f  jmp     short loc_1800196AC
0x1800196a1  mov     rax, 0FFFFFFFF80000002h
0x1800196a8  mov     [rbp+arg_8], rax
0x1800196ac  mov     [rbx+10h], rax
0x1800196b0  cmp     [rsi+8], r13d
0x1800196b4  jz      short loc_1800196CF
0x1800196b6  mov     rcx, [rsi]
0x1800196b9  test    rcx, rcx
0x1800196bc  jz      short loc_1800196CF
0x1800196be  mov     rax, [rcx]
0x1800196c1  mov     edx, 1
0x1800196c6  mov     rax, [rax]
0x1800196c9  call    cs:__guard_dispatch_icall_fptr
0x1800196cf  mov     [rsi], rbx
0x1800196d2  mov     eax, 1
0x1800196d7  mov     [rsi+8], eax
0x1800196da  mov     rax, r12
0x1800196dd  mov     rbx, [rsp+80h+arg_18]
0x1800196e5  add     rsp, 80h
0x1800196ec  pop     r15
0x1800196ee  pop     r14
0x1800196f0  pop     r13
0x1800196f2  pop     r12
0x1800196f4  pop     rdi
0x1800196f5  pop     rsi
0x1800196f6  pop     rbp
0x1800196f7  retn
0x1800196f8  test    rbx, rbx
0x1800196fb  jz      short loc_180019711
0x1800196fd  mov     r8, [rbx]
0x180019700  mov     edx, 1
0x180019705  mov     rcx, rbx
0x180019708  mov     rax, [r8]
0x18001970b  call    cs:__guard_dispatch_icall_fptr
0x180019711  movzx   ecx, di
0x180019714  or      ecx, 80070000h
0x18001971a  test    edi, edi
0x18001971c  cmovle  ecx, edi; int
0x18001971f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
