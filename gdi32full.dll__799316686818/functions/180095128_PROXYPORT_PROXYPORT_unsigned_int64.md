# PROXYPORT::PROXYPORT(unsigned __int64)

- ea: `0x180095128`
- end: `0x180095490`
- name: `??0PROXYPORT@@QEAA@_K@Z`
- size: `872`
- prototype: `PROXYPORT *__fastcall(PROXYPORT *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045d0c`

## callees

- `0x18005bf98`
- `0x180069474`
- `0x18006b28c`
- `0x18007ac50`
- `0x18007ba24`
- `0x180095128`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009519d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009519d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180095190`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180095190`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009540a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009540a`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180095401`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180095401`
- `ntdll!RtlFreeHeap` at `0x180095465`
- `ntdll!RtlFreeHeap` at `0x180095465`
- `ntdll!RtlInitUnicodeString` at `0x180095372`
- `ntdll!RtlInitUnicodeString` at `0x180095372`
- `ntdll!NtClose` at `0x18009542d`
- `ntdll!NtClose` at `0x18009542d`
- `ntdll!RtlInitializeCriticalSection` at `0x1800951dd`
- `ntdll!RtlInitializeCriticalSection` at `0x1800951dd`
- `ntdll!RtlDeleteCriticalSection` at `0x18009543a`
- `ntdll!RtlDeleteCriticalSection` at `0x18009543a`
- `ntdll!NtCreateSection` at `0x180095267`
- `ntdll!NtCreateSection` at `0x180095267`
- `ntdll!RtlAllocateHeap` at `0x1800951c7`
- `ntdll!RtlAllocateHeap` at `0x1800951c7`
- `ntdll!RtlEnterCriticalSection` at `0x18009541b`
- `ntdll!RtlEnterCriticalSection` at `0x18009541b`
- `ntdll!RtlDecodePointer` at `0x1800952ab`
- `ntdll!RtlDecodePointer` at `0x1800952ab`
- `ntdll!NtQueryInformationProcess` at `0x1800952e9`
- `ntdll!NtQueryInformationProcess` at `0x1800952e9`
- `ntdll!NtSecureConnectPort` at `0x1800953a5`
- `ntdll!NtSecureConnectPort` at `0x1800953a5`

## pseudocode

```c
PROXYPORT *__fastcall PROXYPORT::PROXYPORT(PROXYPORT *this)
{
  DWORD CurrentProcessId; // eax
  char *Heap; // rax
  unsigned int (__fastcall *v4)(HANDLE *); // rax
  void *UserSidAndAuthenticationIdAndIntegrityLevel; // rdi
  unsigned int v6; // ecx
  NTSTATUS v7; // esi
  struct _PEB *v8; // rcx
  void *v9; // r8
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-E0h]
  ULONG AllocationAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE FileHandle; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId; // [rsp+54h] [rbp-ACh] BYREF
  _LUID v16; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+60h] [rbp-A0h] BYREF
  struct _PORT_VIEW SectionHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v21; // [rsp+C8h] [rbp-38h]
  _SECURITY_QUALITY_OF_SERVICE SecurityQos; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR SourceString[264]; // [rsp+F0h] [rbp-10h] BYREF

  *(_QWORD *)&SecurityQos.Length = 0;
  *(_DWORD *)&SecurityQos.ContextTrackingMode = 0;
  MaximumSize.QuadPart = 0;
  memset(&SectionHandle, 0, sizeof(SectionHandle));
  DestinationString = 0;
  memset_0(SourceString, 0, 0x208u);
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  SecurityQos.Length = 0;
  SecurityQos.ImpersonationLevel = SecurityImpersonation;
  *(_WORD *)&SecurityQos.ContextTrackingMode = 257;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x70u);
  *(_QWORD *)this = Heap;
  if ( !Heap || RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 16)) < 0 )
  {
    v9 = *(void **)this;
    if ( !*(_QWORD *)this )
      return this;
    v8 = NtCurrentPeb();
LABEL_20:
    RtlFreeHeap(v8->ProcessHeap, 0, v9);
    *(_QWORD *)this = 0;
    return this;
  }
  *(_QWORD *)(*(_QWORD *)this + 56LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 64LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  **(_QWORD **)this = 0;
  *(_QWORD *)(*(_QWORD *)this + 8LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 72LL) = 0;
  *(_QWORD *)(*(_QWORD *)this + 80LL) = 0;
  *(_DWORD *)(*(_QWORD *)this + 108LL) &= ~1u;
  *(_DWORD *)(*(_QWORD *)this + 108LL) &= ~2u;
  *(_DWORD *)(*(_QWORD *)this + 108LL) &= ~4u;
  MaximumSize.QuadPart = 0x200000;
  SectionHandle.SectionHandle = 0;
  if ( NtCreateSection(&SectionHandle.SectionHandle, 6u, 0, &MaximumSize, 4u, 0x8000000u, 0) < 0 )
    goto LABEL_15;
  SectionHandle.Length = 48;
  *(_OWORD *)&SectionHandle.ViewBase = 0;
  SectionHandle.SectionOffset = 0;
  SectionHandle.ViewSize = 0x200000;
  if ( !ghSpooler && !(unsigned int)bLoadSpooler() )
    goto LABEL_15;
  v4 = (unsigned int (__fastcall *)(HANDLE *))RtlDecodePointer(fpLoadSplWow64);
  if ( v4(&ghWow64ServerProcess) )
    goto LABEL_15;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v21 = 0;
  if ( NtQueryInformationProcess(ghWow64ServerProcess, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
    goto LABEL_15;
  v16 = 0;
  v14 = 0;
  UserSidAndAuthenticationIdAndIntegrityLevel = OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(&v16, &v14);
  if ( UserSidAndAuthenticationIdAndIntegrityLevel )
  {
    v6 = v14;
    if ( v14 < 0x2000 )
    {
      *(_DWORD *)(*(_QWORD *)this + 108LL) |= 4u;
      v6 = 0x2000;
    }
    LODWORD(FileHandle) = v16.HighPart;
    AllocationAttributes[0] = v16.LowPart;
    SectionPageProtection[0] = pSessionId;
    StringCchPrintfW(
      SourceString,
      0x104u,
      L"%s_%x_%x_%x_%x",
      L"\\RPC Control\\UmpdProxy",
      *(_QWORD *)SectionPageProtection,
      *(_QWORD *)AllocationAttributes,
      FileHandle,
      v6);
    RtlInitUnicodeString(&DestinationString, SourceString);
    v7 = NtSecureConnectPort(
           *(PHANDLE *)this,
           &DestinationString,
           &SecurityQos,
           &SectionHandle,
           UserSidAndAuthenticationIdAndIntegrityLevel,
           0,
           (PULONG)(*(_QWORD *)this + 104LL),
           0,
           0);
    if ( v7 >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)this + 8LL) = SectionHandle.SectionHandle;
      *(_QWORD *)(*(_QWORD *)this + 56LL) = SectionHandle.ViewBase;
      *(_QWORD *)(*(_QWORD *)this + 64LL) = 0x200000;
      *(_QWORD *)(*(_QWORD *)this + 72LL) = SectionHandle.ViewRemoteBase;
      *(_QWORD *)(*(_QWORD *)this + 80LL) = *(_QWORD *)(*(_QWORD *)this + 72LL) - *(_QWORD *)(*(_QWORD *)this + 56LL);
      *(_QWORD *)(*(_QWORD *)this + 96LL) = v21;
      *(_DWORD *)(*(_QWORD *)this + 108LL) |= 1u;
      NtRegisterThreadTerminatePort(**(HANDLE **)this);
    }
    LocalFree(UserSidAndAuthenticationIdAndIntegrityLevel);
    if ( v7 < 0 )
    {
LABEL_15:
      if ( SectionHandle.SectionHandle )
        NtClose(SectionHandle.SectionHandle);
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)this + 16LL));
      v8 = NtCurrentPeb();
      v9 = *(void **)this;
      goto LABEL_20;
    }
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)this + 16LL));
  return this;
}

```

## disassembly

```asm
0x180095128  push    rbp
0x18009512a  push    rbx
0x18009512b  push    rsi
0x18009512c  push    rdi
0x18009512d  push    r14
0x18009512f  push    r15
0x180095131  lea     rbp, [rsp-218h]
0x180095139  sub     rsp, 318h
0x180095140  mov     rax, cs:__security_cookie
0x180095147  xor     rax, rsp
0x18009514a  mov     [rbp+240h+var_40], rax
0x180095151  xorps   xmm0, xmm0
0x180095154  xor     eax, eax
0x180095156  mov     rbx, rcx
0x180095159  mov     qword ptr [rbp+240h+SecurityQos.Length], rax
0x18009515d  xor     r14d, r14d
0x180095160  mov     dword ptr [rbp+240h+SecurityQos.ContextTrackingMode], eax
0x180095163  lea     rcx, [rbp+240h+SourceString]; void *
0x180095167  mov     qword ptr [rsp+340h+MaximumSize], r14
0x18009516c  xor     edx, edx; Val
0x18009516e  mov     r8d, 208h; Size
0x180095174  movups  xmmword ptr [rsp+340h+SectionHandle], xmm0
0x180095179  movups  [rsp+340h+var_2C8], xmm0
0x18009517e  movups  [rbp+240h+var_2B8], xmm0
0x180095182  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x180095186  call    memset_0
0x18009518b  mov     [rsp+340h+pSessionId], r14d
0x180095190  call    cs:__imp_GetCurrentProcessId
0x180095196  mov     ecx, eax; dwProcessId
0x180095198  lea     rdx, [rsp+340h+pSessionId]; pSessionId
0x18009519d  call    cs:__imp_ProcessIdToSessionId
0x1800951a3  mov     [rbp+240h+SecurityQos.Length], r14d
0x1800951a7  lea     r8d, [r14+70h]; Size
0x1800951ab  mov     [rbp+240h+SecurityQos.ImpersonationLevel], 2
0x1800951b2  xor     edx, edx; Flags
0x1800951b4  mov     word ptr [rbp+240h+SecurityQos.ContextTrackingMode], 101h
0x1800951ba  mov     rcx, gs:60h
0x1800951c3  mov     rcx, [rcx+30h]; HeapHandle
0x1800951c7  call    cs:__imp_RtlAllocateHeap
0x1800951cd  mov     [rbx], rax
0x1800951d0  test    rax, rax
0x1800951d3  jz      loc_18009544E
0x1800951d9  lea     rcx, [rax+10h]; CriticalSection
0x1800951dd  call    cs:__imp_RtlInitializeCriticalSection
0x1800951e3  test    eax, eax
0x1800951e5  js      loc_18009544E
0x1800951eb  mov     rax, [rbx]
0x1800951ee  lea     r9, [rsp+340h+MaximumSize]; MaximumSize
0x1800951f3  mov     [rsp+340h+FileHandle], r14; FileHandle
0x1800951f8  lea     rcx, [rsp+340h+SectionHandle+8]; SectionHandle
0x1800951fd  mov     r15d, 200000h
0x180095203  mov     [rsp+340h+AllocationAttributes], 8000000h; AllocationAttributes
0x18009520b  xor     r8d, r8d; ObjectAttributes
0x18009520e  mov     [rsp+340h+SectionPageProtection], 4; SectionPageProtection
0x180095216  mov     [rax+38h], r14
0x18009521a  mov     rax, [rbx]
0x18009521d  mov     [rax+40h], r14
0x180095221  mov     rax, [rbx]
0x180095224  mov     [rax+58h], r14d
0x180095228  mov     rax, [rbx]
0x18009522b  mov     [rax], r14
0x18009522e  mov     rax, [rbx]
0x180095231  mov     [rax+8], r14
0x180095235  mov     rax, [rbx]
0x180095238  mov     [rax+48h], r14
0x18009523c  mov     rax, [rbx]
0x18009523f  mov     [rax+50h], r14
0x180095243  mov     rax, [rbx]
0x180095246  and     dword ptr [rax+6Ch], 0FFFFFFFEh
0x18009524a  mov     rax, [rbx]
0x18009524d  and     dword ptr [rax+6Ch], 0FFFFFFFDh
0x180095251  mov     rax, [rbx]
0x180095254  and     dword ptr [rax+6Ch], 0FFFFFFFBh
0x180095258  xor     eax, eax
0x18009525a  mov     qword ptr [rsp+340h+MaximumSize], r15
0x18009525f  mov     [rsp+340h+SectionHandle+8], rax
0x180095264  lea     edx, [rax+6]; DesiredAccess
0x180095267  call    cs:__imp_NtCreateSection
0x18009526d  test    eax, eax
0x18009526f  js      loc_180095423
0x180095275  cmp     cs:ghSpooler, r14
0x18009527c  lea     edi, [r14+30h]
0x180095280  xorps   xmm0, xmm0
0x180095283  mov     dword ptr [rsp+340h+SectionHandle], edi
0x180095287  movdqu  [rbp+240h+var_2B8], xmm0
0x18009528c  mov     dword ptr [rsp+340h+var_2C8], r14d
0x180095291  mov     qword ptr [rbp+240h+var_2C8+8], r15
0x180095295  jnz     short loc_1800952A4
0x180095297  call    bLoadSpooler
0x18009529c  test    eax, eax
0x18009529e  jz      loc_180095423
0x1800952a4  mov     rcx, cs:fpLoadSplWow64; Pointer
0x1800952ab  call    cs:__imp_RtlDecodePointer
0x1800952b1  lea     rcx, ?ghWow64ServerProcess@@3PEAXEA; void * ghWow64ServerProcess
0x1800952b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800952bd  test    eax, eax
0x1800952bf  jnz     loc_180095423
0x1800952c5  mov     rcx, cs:?ghWow64ServerProcess@@3PEAXEA; ProcessHandle
0x1800952cc  lea     r8, [rbp+240h+ProcessInformation]; ProcessInformation
0x1800952d0  xorps   xmm0, xmm0
0x1800952d3  mov     qword ptr [rsp+340h+SectionPageProtection], r14; ReturnLength
0x1800952d8  mov     r9d, edi; ProcessInformationLength
0x1800952db  xor     edx, edx; ProcessInformationClass
0x1800952dd  movups  [rbp+240h+ProcessInformation], xmm0
0x1800952e1  movups  [rbp+240h+var_288], xmm0
0x1800952e5  movups  [rbp+240h+var_278], xmm0
0x1800952e9  call    cs:__imp_NtQueryInformationProcess
0x1800952ef  test    eax, eax
0x1800952f1  js      loc_180095423
0x1800952f7  lea     rdx, [rsp+340h+var_2F0]; unsigned int *
0x1800952fc  mov     qword ptr [rsp+340h+var_2E8.LowPart], r14
0x180095301  lea     rcx, [rsp+340h+var_2E8]; struct _LUID *
0x180095306  mov     [rsp+340h+var_2F0], r14d
0x18009530b  call    ?OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel@@YAPEAXPEAU_LUID@@PEAK@Z; OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(_LUID *,ulong *)
0x180095310  mov     rdi, rax
0x180095313  test    rax, rax
0x180095316  jz      loc_180095414
0x18009531c  mov     ecx, [rsp+340h+var_2F0]
0x180095320  mov     eax, 2000h
0x180095325  cmp     ecx, eax
0x180095327  jnb     short loc_180095332
0x180095329  mov     rcx, [rbx]
0x18009532c  or      dword ptr [rcx+6Ch], 4
0x180095330  mov     ecx, eax
0x180095332  mov     eax, [rsp+340h+var_2E8.HighPart]
0x180095336  lea     r9, aRpcControlUmpd; "\\RPC Control\\UmpdProxy"
0x18009533d  mov     dword ptr [rsp+340h+ConnectionInformation], ecx
0x180095341  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x180095348  mov     dword ptr [rsp+340h+FileHandle], eax
0x18009534c  lea     rcx, [rbp+240h+SourceString]; unsigned __int16 *
0x180095350  mov     eax, [rsp+340h+var_2E8.LowPart]
0x180095354  mov     edx, 104h; unsigned __int64
0x180095359  mov     [rsp+340h+AllocationAttributes], eax
0x18009535d  mov     eax, [rsp+340h+pSessionId]
0x180095361  mov     [rsp+340h+SectionPageProtection], eax
0x180095365  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009536a  lea     rdx, [rbp+240h+SourceString]; SourceString
0x18009536e  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x180095372  call    cs:__imp_RtlInitUnicodeString
0x180095378  mov     rcx, [rbx]; PortHandle
0x18009537b  lea     r9, [rsp+340h+SectionHandle]; ClientView
0x180095380  mov     [rsp+340h+ConnectionInformationLength], r14; ConnectionInformationLength
0x180095385  lea     r8, [rbp+240h+SecurityQos]; SecurityQos
0x180095389  mov     [rsp+340h+ConnectionInformation], r14; ConnectionInformation
0x18009538e  lea     rdx, [rbp+240h+DestinationString]; PortName
0x180095392  lea     rax, [rcx+68h]
0x180095396  mov     [rsp+340h+FileHandle], rax; MaxMessageLength
0x18009539b  mov     qword ptr [rsp+340h+AllocationAttributes], r14; ServerView
0x1800953a0  mov     qword ptr [rsp+340h+SectionPageProtection], rdi; ServerSid
0x1800953a5  call    cs:__imp_NtSecureConnectPort
0x1800953ab  mov     esi, eax
0x1800953ad  test    eax, eax
0x1800953af  js      short loc_180095407
0x1800953b1  mov     rcx, [rbx]
0x1800953b4  mov     rax, [rsp+340h+SectionHandle+8]
0x1800953b9  mov     [rcx+8], rax
0x1800953bd  mov     rcx, [rbx]
0x1800953c0  mov     rax, qword ptr [rbp+240h+var_2B8]
0x1800953c4  mov     [rcx+38h], rax
0x1800953c8  mov     rax, [rbx]
0x1800953cb  mov     [rax+40h], r15
0x1800953cf  mov     rcx, [rbx]
0x1800953d2  mov     rax, qword ptr [rbp+240h+var_2B8+8]
0x1800953d6  mov     [rcx+48h], rax
0x1800953da  mov     rcx, [rbx]
0x1800953dd  mov     rax, [rcx+48h]
0x1800953e1  sub     rax, [rcx+38h]
0x1800953e5  mov     [rcx+50h], rax
0x1800953e9  mov     rcx, [rbx]
0x1800953ec  mov     rax, qword ptr [rbp+240h+var_278]
0x1800953f0  mov     [rcx+60h], rax
0x1800953f4  mov     rax, [rbx]
0x1800953f7  or      dword ptr [rax+6Ch], 1
0x1800953fb  mov     rcx, [rbx]
0x1800953fe  mov     rcx, [rcx]; TerminationPort
0x180095401  call    cs:__imp_NtRegisterThreadTerminatePort
0x180095407  mov     rcx, rdi; hMem
0x18009540a  call    cs:__imp_LocalFree
0x180095410  test    esi, esi
0x180095412  js      short loc_180095423
0x180095414  mov     rcx, [rbx]
0x180095417  add     rcx, 10h; CriticalSection
0x18009541b  call    cs:__imp_RtlEnterCriticalSection
0x180095421  jmp     short loc_18009546E
0x180095423  mov     rcx, [rsp+340h+SectionHandle+8]; Handle
0x180095428  test    rcx, rcx
0x18009542b  jz      short loc_180095433
0x18009542d  call    cs:__imp_NtClose
0x180095433  mov     rcx, [rbx]
0x180095436  add     rcx, 10h; CriticalSection
0x18009543a  call    cs:__imp_RtlDeleteCriticalSection
0x180095440  mov     rcx, gs:60h
0x180095449  mov     r8, [rbx]
0x18009544c  jmp     short loc_18009545F
0x18009544e  mov     r8, [rbx]; P
0x180095451  test    r8, r8
0x180095454  jz      short loc_18009546E
0x180095456  mov     rcx, gs:60h
0x18009545f  mov     rcx, [rcx+30h]; HeapHandle
0x180095463  xor     edx, edx; Flags
0x180095465  call    cs:__imp_RtlFreeHeap
0x18009546b  mov     [rbx], r14
0x18009546e  mov     rax, rbx
0x180095471  mov     rcx, [rbp+240h+var_40]
0x180095478  xor     rcx, rsp; StackCookie
0x18009547b  call    __security_check_cookie
0x180095480  add     rsp, 318h
0x180095487  pop     r15
0x180095489  pop     r14
0x18009548b  pop     rdi
0x18009548c  pop     rsi
0x18009548d  pop     rbx
0x18009548e  pop     rbp
0x18009548f  retn
```
