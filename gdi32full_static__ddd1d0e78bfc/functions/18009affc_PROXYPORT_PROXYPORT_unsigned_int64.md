# PROXYPORT::PROXYPORT(unsigned __int64)

- ea: `0x18009affc`
- end: `0x18009b3bf`
- name: `??0PROXYPORT@@QEAA@_K@Z`
- size: `963`
- prototype: `PROXYPORT *__fastcall(PROXYPORT *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003fb74`

## callees

- `0x180060820`
- `0x18006d76c`
- `0x18006fb6c`
- `0x18007f800`
- `0x180080604`
- `0x18009affc`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009b077`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18009b077`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b064`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009b064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b31a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009b31a`
- `ntdll!NtRegisterThreadTerminatePort` at `0x18009b30b`
- `ntdll!NtRegisterThreadTerminatePort` at `0x18009b30b`
- `ntdll!RtlFreeHeap` at `0x18009b38d`
- `ntdll!RtlFreeHeap` at `0x18009b38d`
- `ntdll!RtlInitUnicodeString` at `0x18009b270`
- `ntdll!RtlInitUnicodeString` at `0x18009b270`
- `ntdll!NtClose` at `0x18009b349`
- `ntdll!NtClose` at `0x18009b349`
- `ntdll!RtlInitializeCriticalSection` at `0x18009b0c3`
- `ntdll!RtlInitializeCriticalSection` at `0x18009b0c3`
- `ntdll!RtlDeleteCriticalSection` at `0x18009b35c`
- `ntdll!RtlDeleteCriticalSection` at `0x18009b35c`
- `ntdll!NtCreateSection` at `0x18009b153`
- `ntdll!NtCreateSection` at `0x18009b153`
- `ntdll!RtlAllocateHeap` at `0x18009b0a7`
- `ntdll!RtlAllocateHeap` at `0x18009b0a7`
- `ntdll!RtlEnterCriticalSection` at `0x18009b331`
- `ntdll!RtlEnterCriticalSection` at `0x18009b331`
- `ntdll!RtlDecodePointer` at `0x18009b19d`
- `ntdll!RtlDecodePointer` at `0x18009b19d`
- `ntdll!NtQueryInformationProcess` at `0x18009b1e1`
- `ntdll!NtQueryInformationProcess` at `0x18009b1e1`
- `ntdll!NtSecureConnectPort` at `0x18009b2a9`
- `ntdll!NtSecureConnectPort` at `0x18009b2a9`

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
0x18009affc  push    rbp
0x18009affe  push    rbx
0x18009afff  push    rsi
0x18009b000  push    rdi
0x18009b001  push    r14
0x18009b003  push    r15
0x18009b005  lea     rbp, [rsp-218h]
0x18009b00d  sub     rsp, 318h
0x18009b014  mov     rax, cs:__security_cookie
0x18009b01b  xor     rax, rsp
0x18009b01e  mov     [rbp+240h+var_40], rax
0x18009b025  xorps   xmm0, xmm0
0x18009b028  xor     eax, eax
0x18009b02a  mov     rbx, rcx
0x18009b02d  mov     qword ptr [rbp+240h+SecurityQos.Length], rax
0x18009b031  xor     r14d, r14d
0x18009b034  mov     dword ptr [rbp+240h+SecurityQos.ContextTrackingMode], eax
0x18009b037  lea     rcx, [rbp+240h+SourceString]; void *
0x18009b03b  mov     qword ptr [rsp+340h+MaximumSize], r14
0x18009b040  xor     edx, edx; Val
0x18009b042  mov     r8d, 208h; Size
0x18009b048  movups  xmmword ptr [rsp+340h+SectionHandle], xmm0
0x18009b04d  movups  [rsp+340h+var_2C8], xmm0
0x18009b052  movups  [rbp+240h+var_2B8], xmm0
0x18009b056  movups  xmmword ptr [rbp+240h+DestinationString.Length], xmm0
0x18009b05a  call    memset_0
0x18009b05f  mov     [rsp+340h+pSessionId], r14d
0x18009b064  call    cs:__imp_GetCurrentProcessId
0x18009b06b  nop     dword ptr [rax+rax+00h]
0x18009b070  mov     ecx, eax; dwProcessId
0x18009b072  lea     rdx, [rsp+340h+pSessionId]; pSessionId
0x18009b077  call    cs:__imp_ProcessIdToSessionId
0x18009b07e  nop     dword ptr [rax+rax+00h]
0x18009b083  mov     [rbp+240h+SecurityQos.Length], r14d
0x18009b087  lea     r8d, [r14+70h]; Size
0x18009b08b  mov     [rbp+240h+SecurityQos.ImpersonationLevel], 2
0x18009b092  xor     edx, edx; Flags
0x18009b094  mov     word ptr [rbp+240h+SecurityQos.ContextTrackingMode], 101h
0x18009b09a  mov     rcx, gs:60h
0x18009b0a3  mov     rcx, [rcx+30h]; HeapHandle
0x18009b0a7  call    cs:__imp_RtlAllocateHeap
0x18009b0ae  nop     dword ptr [rax+rax+00h]
0x18009b0b3  mov     [rbx], rax
0x18009b0b6  test    rax, rax
0x18009b0b9  jz      loc_18009B376
0x18009b0bf  lea     rcx, [rax+10h]; CriticalSection
0x18009b0c3  call    cs:__imp_RtlInitializeCriticalSection
0x18009b0ca  nop     dword ptr [rax+rax+00h]
0x18009b0cf  test    eax, eax
0x18009b0d1  js      loc_18009B376
0x18009b0d7  mov     rax, [rbx]
0x18009b0da  lea     r9, [rsp+340h+MaximumSize]; MaximumSize
0x18009b0df  mov     [rsp+340h+FileHandle], r14; FileHandle
0x18009b0e4  lea     rcx, [rsp+340h+SectionHandle+8]; SectionHandle
0x18009b0e9  mov     r15d, 200000h
0x18009b0ef  mov     [rsp+340h+AllocationAttributes], 8000000h; AllocationAttributes
0x18009b0f7  xor     r8d, r8d; ObjectAttributes
0x18009b0fa  mov     [rsp+340h+SectionPageProtection], 4; SectionPageProtection
0x18009b102  mov     [rax+38h], r14
0x18009b106  mov     rax, [rbx]
0x18009b109  mov     [rax+40h], r14
0x18009b10d  mov     rax, [rbx]
0x18009b110  mov     [rax+58h], r14d
0x18009b114  mov     rax, [rbx]
0x18009b117  mov     [rax], r14
0x18009b11a  mov     rax, [rbx]
0x18009b11d  mov     [rax+8], r14
0x18009b121  mov     rax, [rbx]
0x18009b124  mov     [rax+48h], r14
0x18009b128  mov     rax, [rbx]
0x18009b12b  mov     [rax+50h], r14
0x18009b12f  mov     rax, [rbx]
0x18009b132  and     dword ptr [rax+6Ch], 0FFFFFFFEh
0x18009b136  mov     rax, [rbx]
0x18009b139  and     dword ptr [rax+6Ch], 0FFFFFFFDh
0x18009b13d  mov     rax, [rbx]
0x18009b140  and     dword ptr [rax+6Ch], 0FFFFFFFBh
0x18009b144  xor     eax, eax
0x18009b146  mov     qword ptr [rsp+340h+MaximumSize], r15
0x18009b14b  mov     [rsp+340h+SectionHandle+8], rax
0x18009b150  lea     edx, [rax+6]; DesiredAccess
0x18009b153  call    cs:__imp_NtCreateSection
0x18009b15a  nop     dword ptr [rax+rax+00h]
0x18009b15f  test    eax, eax
0x18009b161  js      loc_18009B33F
0x18009b167  cmp     cs:ghSpooler, r14
0x18009b16e  lea     edi, [r14+30h]
0x18009b172  xorps   xmm0, xmm0
0x18009b175  mov     dword ptr [rsp+340h+SectionHandle], edi
0x18009b179  movdqu  [rbp+240h+var_2B8], xmm0
0x18009b17e  mov     dword ptr [rsp+340h+var_2C8], r14d
0x18009b183  mov     qword ptr [rbp+240h+var_2C8+8], r15
0x18009b187  jnz     short loc_18009B196
0x18009b189  call    bLoadSpooler
0x18009b18e  test    eax, eax
0x18009b190  jz      loc_18009B33F
0x18009b196  mov     rcx, cs:fpLoadSplWow64; Pointer
0x18009b19d  call    cs:__imp_RtlDecodePointer
0x18009b1a4  nop     dword ptr [rax+rax+00h]
0x18009b1a9  lea     rcx, ?ghWow64ServerProcess@@3PEAXEA; void * ghWow64ServerProcess
0x18009b1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b1b5  test    eax, eax
0x18009b1b7  jnz     loc_18009B33F
0x18009b1bd  mov     rcx, cs:?ghWow64ServerProcess@@3PEAXEA; ProcessHandle
0x18009b1c4  lea     r8, [rbp+240h+ProcessInformation]; ProcessInformation
0x18009b1c8  xorps   xmm0, xmm0
0x18009b1cb  mov     qword ptr [rsp+340h+SectionPageProtection], r14; ReturnLength
0x18009b1d0  mov     r9d, edi; ProcessInformationLength
0x18009b1d3  xor     edx, edx; ProcessInformationClass
0x18009b1d5  movups  [rbp+240h+ProcessInformation], xmm0
0x18009b1d9  movups  [rbp+240h+var_288], xmm0
0x18009b1dd  movups  [rbp+240h+var_278], xmm0
0x18009b1e1  call    cs:__imp_NtQueryInformationProcess
0x18009b1e8  nop     dword ptr [rax+rax+00h]
0x18009b1ed  test    eax, eax
0x18009b1ef  js      loc_18009B33F
0x18009b1f5  lea     rdx, [rsp+340h+var_2F0]; unsigned int *
0x18009b1fa  mov     qword ptr [rsp+340h+var_2E8.LowPart], r14
0x18009b1ff  lea     rcx, [rsp+340h+var_2E8]; struct _LUID *
0x18009b204  mov     [rsp+340h+var_2F0], r14d
0x18009b209  call    ?OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel@@YAPEAXPEAU_LUID@@PEAK@Z; OpenTokenAndGetUserSidAndAuthenticationIdAndIntegrityLevel(_LUID *,ulong *)
0x18009b20e  mov     rdi, rax
0x18009b211  test    rax, rax
0x18009b214  jz      loc_18009B32A
0x18009b21a  mov     ecx, [rsp+340h+var_2F0]
0x18009b21e  mov     eax, 2000h
0x18009b223  cmp     ecx, eax
0x18009b225  jnb     short loc_18009B230
0x18009b227  mov     rcx, [rbx]
0x18009b22a  or      dword ptr [rcx+6Ch], 4
0x18009b22e  mov     ecx, eax
0x18009b230  mov     eax, [rsp+340h+var_2E8.HighPart]
0x18009b234  lea     r9, aRpcControlUmpd; "\\RPC Control\\UmpdProxy"
0x18009b23b  mov     dword ptr [rsp+340h+ConnectionInformation], ecx
0x18009b23f  lea     r8, aSXXXX; "%s_%x_%x_%x_%x"
0x18009b246  mov     dword ptr [rsp+340h+FileHandle], eax
0x18009b24a  lea     rcx, [rbp+240h+SourceString]; unsigned __int16 *
0x18009b24e  mov     eax, [rsp+340h+var_2E8.LowPart]
0x18009b252  mov     edx, 104h; unsigned __int64
0x18009b257  mov     [rsp+340h+AllocationAttributes], eax
0x18009b25b  mov     eax, [rsp+340h+pSessionId]
0x18009b25f  mov     [rsp+340h+SectionPageProtection], eax
0x18009b263  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009b268  lea     rdx, [rbp+240h+SourceString]; SourceString
0x18009b26c  lea     rcx, [rbp+240h+DestinationString]; DestinationString
0x18009b270  call    cs:__imp_RtlInitUnicodeString
0x18009b277  nop     dword ptr [rax+rax+00h]
0x18009b27c  mov     rcx, [rbx]; PortHandle
0x18009b27f  lea     r9, [rsp+340h+SectionHandle]; ClientView
0x18009b284  mov     [rsp+340h+ConnectionInformationLength], r14; ConnectionInformationLength
0x18009b289  lea     r8, [rbp+240h+SecurityQos]; SecurityQos
0x18009b28d  mov     [rsp+340h+ConnectionInformation], r14; ConnectionInformation
0x18009b292  lea     rdx, [rbp+240h+DestinationString]; PortName
0x18009b296  lea     rax, [rcx+68h]
0x18009b29a  mov     [rsp+340h+FileHandle], rax; MaxMessageLength
0x18009b29f  mov     qword ptr [rsp+340h+AllocationAttributes], r14; ServerView
0x18009b2a4  mov     qword ptr [rsp+340h+SectionPageProtection], rdi; ServerSid
0x18009b2a9  call    cs:__imp_NtSecureConnectPort
0x18009b2b0  nop     dword ptr [rax+rax+00h]
0x18009b2b5  mov     esi, eax
0x18009b2b7  test    eax, eax
0x18009b2b9  js      short loc_18009B317
0x18009b2bb  mov     rcx, [rbx]
0x18009b2be  mov     rax, [rsp+340h+SectionHandle+8]
0x18009b2c3  mov     [rcx+8], rax
0x18009b2c7  mov     rcx, [rbx]
0x18009b2ca  mov     rax, qword ptr [rbp+240h+var_2B8]
0x18009b2ce  mov     [rcx+38h], rax
0x18009b2d2  mov     rax, [rbx]
0x18009b2d5  mov     [rax+40h], r15
0x18009b2d9  mov     rcx, [rbx]
0x18009b2dc  mov     rax, qword ptr [rbp+240h+var_2B8+8]
0x18009b2e0  mov     [rcx+48h], rax
0x18009b2e4  mov     rcx, [rbx]
0x18009b2e7  mov     rax, [rcx+48h]
0x18009b2eb  sub     rax, [rcx+38h]
0x18009b2ef  mov     [rcx+50h], rax
0x18009b2f3  mov     rcx, [rbx]
0x18009b2f6  mov     rax, qword ptr [rbp+240h+var_278]
0x18009b2fa  mov     [rcx+60h], rax
0x18009b2fe  mov     rax, [rbx]
0x18009b301  or      dword ptr [rax+6Ch], 1
0x18009b305  mov     rcx, [rbx]
0x18009b308  mov     rcx, [rcx]; TerminationPort
0x18009b30b  call    cs:__imp_NtRegisterThreadTerminatePort
0x18009b312  nop     dword ptr [rax+rax+00h]
0x18009b317  mov     rcx, rdi; hMem
0x18009b31a  call    cs:__imp_LocalFree
0x18009b321  nop     dword ptr [rax+rax+00h]
0x18009b326  test    esi, esi
0x18009b328  js      short loc_18009B33F
0x18009b32a  mov     rcx, [rbx]
0x18009b32d  add     rcx, 10h; CriticalSection
0x18009b331  call    cs:__imp_RtlEnterCriticalSection
0x18009b338  nop     dword ptr [rax+rax+00h]
0x18009b33d  jmp     short loc_18009B39C
0x18009b33f  mov     rcx, [rsp+340h+SectionHandle+8]; Handle
0x18009b344  test    rcx, rcx
0x18009b347  jz      short loc_18009B355
0x18009b349  call    cs:__imp_NtClose
0x18009b350  nop     dword ptr [rax+rax+00h]
0x18009b355  mov     rcx, [rbx]
0x18009b358  add     rcx, 10h; CriticalSection
0x18009b35c  call    cs:__imp_RtlDeleteCriticalSection
0x18009b363  nop     dword ptr [rax+rax+00h]
0x18009b368  mov     rcx, gs:60h
0x18009b371  mov     r8, [rbx]
0x18009b374  jmp     short loc_18009B387
0x18009b376  mov     r8, [rbx]; P
0x18009b379  test    r8, r8
0x18009b37c  jz      short loc_18009B39C
0x18009b37e  mov     rcx, gs:60h
0x18009b387  mov     rcx, [rcx+30h]; HeapHandle
0x18009b38b  xor     edx, edx; Flags
0x18009b38d  call    cs:__imp_RtlFreeHeap
0x18009b394  nop     dword ptr [rax+rax+00h]
0x18009b399  mov     [rbx], r14
0x18009b39c  mov     rax, rbx
0x18009b39f  mov     rcx, [rbp+240h+var_40]
0x18009b3a6  xor     rcx, rsp; StackCookie
0x18009b3a9  call    __security_check_cookie
0x18009b3ae  add     rsp, 318h
0x18009b3b5  pop     r15
0x18009b3b7  pop     r14
0x18009b3b9  pop     rdi
0x18009b3ba  pop     rsi
0x18009b3bb  pop     rbx
0x18009b3bc  pop     rbp
0x18009b3bd  retn
```
