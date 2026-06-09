# CsrApiRequestThread

- ea: `0x1800097f0`
- end: `0x180009fbc`
- name: `CsrApiRequestThread`
- size: `1996`
- prototype: `void __fastcall __noreturn(__int64)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001140`
- `0x180001200`
- `0x1800019b0`
- `0x180001aa0`
- `0x180001c50`
- `0x180002040`
- `0x1800021f0`
- `0x180002850`
- `0x180002880`
- `0x180003670`
- `0x180003830`
- `0x1800038c0`
- `0x180003970`
- `0x180003a20`
- `0x180003bb0`
- `0x180006270`
- `0x1800062e0`
- `0x180008f00`
- `0x1800097f0`
- `0x18000ab61`
- `0x18000ab80`
- `0x18000b010`

## import_xrefs

- `ntdll!NtSetEvent` at `0x1800098cd`
- `ntdll!NtSetEvent` at `0x1800098cd`
- `ntdll!NtDelayExecution` at `0x180009868`
- `ntdll!NtDelayExecution` at `0x180009868`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000996b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009ebb`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000996b`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180009ebb`
- `ntdll!RtlEnterCriticalSection` at `0x180009a4a`
- `ntdll!RtlEnterCriticalSection` at `0x180009a4a`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ad8`
- `ntdll!RtlLeaveCriticalSection` at `0x180009b1f`
- `ntdll!RtlLeaveCriticalSection` at `0x180009b79`
- `ntdll!RtlLeaveCriticalSection` at `0x180009bae`
- `ntdll!RtlLeaveCriticalSection` at `0x180009c22`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d22`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d55`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ad8`
- `ntdll!RtlLeaveCriticalSection` at `0x180009b1f`
- `ntdll!RtlLeaveCriticalSection` at `0x180009b79`
- `ntdll!RtlLeaveCriticalSection` at `0x180009bae`
- `ntdll!RtlLeaveCriticalSection` at `0x180009c22`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d22`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d55`
- `ntdll!NtSetDefaultHardErrorPort` at `0x1800098b7`
- `ntdll!NtSetDefaultHardErrorPort` at `0x1800098b7`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800098ff`
- `ntdll!AlpcInitializeMessageAttribute` at `0x1800098ff`
- `ntdll!AlpcGetMessageAttribute` at `0x1800099ee`
- `ntdll!AlpcGetMessageAttribute` at `0x180009a21`
- `ntdll!AlpcGetMessageAttribute` at `0x1800099ee`
- `ntdll!AlpcGetMessageAttribute` at `0x180009a21`

## string_xrefs

- `0x180009cea`: `CsrApiRequestThread`
- `0x180009f45`: `CsrApiRequestThread`
- `0x180009f90`: `CsrApiRequestThread`

## pseudocode

```c
void __fastcall __noreturn CsrApiRequestThread(__int64 a1)
{
  _BYTE *v2; // rsi
  struct _NT_TIB *Self; // r14
  NTSTATUS v4; // ecx
  int v5; // r13d
  __int16 v6; // r15
  __int64 MessageAttribute; // rax
  __int64 v8; // rax
  unsigned int v9; // r14d
  volatile signed __int32 *v10; // rdi
  __int64 v11; // r9
  __int64 ProcessByClientId; // rax
  __int64 v13; // rdi
  PVOID v14; // rcx
  __int64 v15; // r15
  bool v16; // zf
  __int64 v17; // r9
  __int64 v18; // rdi
  __int64 v19; // r14
  int v20; // r14d
  int v21; // ecx
  __int64 v22; // r14
  __int64 v23; // rdi
  __int64 v24; // rcx
  __int64 v25; // r14
  int v26; // eax
  __int64 v27; // [rsp+40h] [rbp-498h]
  int v28; // [rsp+48h] [rbp-490h] BYREF
  PVOID BaseAddress; // [rsp+50h] [rbp-488h] BYREF
  LARGE_INTEGER Interval; // [rsp+58h] [rbp-480h] BYREF
  __int64 v31; // [rsp+60h] [rbp-478h] BYREF
  _BYTE *v32; // [rsp+68h] [rbp-470h]
  __int64 v33; // [rsp+70h] [rbp-468h]
  struct _NT_TIB *v34; // [rsp+78h] [rbp-460h]
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // [rsp+80h] [rbp-458h]
  _BYTE v36[2]; // [rsp+90h] [rbp-448h] BYREF
  __int16 v37; // [rsp+92h] [rbp-446h]
  __int16 v38; // [rsp+94h] [rbp-444h]
  _OWORD v39[2]; // [rsp+98h] [rbp-440h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-420h]
  unsigned int v41; // [rsp+C0h] [rbp-418h]
  int v42; // [rsp+C4h] [rbp-414h]
  _BYTE v43[4]; // [rsp+450h] [rbp-88h] BYREF
  int v44; // [rsp+454h] [rbp-84h]

  memset_0(v36, 0, 0x3B8u);
  v2 = 0;
  v28 = 0;
  v31 = 0;
  Self = KeGetPcr()->NtTib.Self;
  v34 = Self;
  while ( !CsrConnectToUser() )
  {
    Self[36].FiberData = 0;
    Interval.QuadPart = -300000000;
    NtDelayExecution(0, &Interval);
  }
  Interval.QuadPart = (LONGLONG)&Self[2];
  ExceptionList = Self[2].ExceptionList;
  if ( a1 )
  {
    v4 = 0;
    if ( *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL) == ServiceSessionId )
      v4 = NtSetDefaultHardErrorPort(CsrApiPort);
    *(_DWORD *)a1 = v4;
    NtSetEvent(*(HANDLE *)(a1 + 8), 0);
    _InterlockedIncrement(&CsrpStaticThreadCount);
    _InterlockedIncrement(&CsrpDynamicThreadTotal);
  }
  AlpcInitializeMessageAttribute(1610612736, v43, 72, &v31);
  while ( 1 )
  {
    do
    {
      while ( 1 )
      {
        do
        {
          *(_OWORD *)&Self[35].Self = *(_OWORD *)&Self[1].StackBase;
          v31 = 952;
          v44 = 0;
          v5 = NtAlpcSendWaitReceivePort(CsrApiPort, 0x10000, v2, 0, v36, &v31, v43, 0);
          v2 = 0;
        }
        while ( v5 < 0 );
        v32 = 0;
        memset_0(&v36[v37], 0, 952LL - v37);
        *(_OWORD *)&Self[35].Self = v39[0];
        v6 = (unsigned __int8)v38;
        if ( (unsigned __int8)v38 != 10 )
          break;
        if ( (v44 & 0x40000000) != 0 )
          MessageAttribute = AlpcGetMessageAttribute(v43, 0x40000000);
        else
          MessageAttribute = 0;
        CsrApiHandleConnectionRequest(v36, MessageAttribute);
      }
      v8 = AlpcGetMessageAttribute(v43, 0x20000000);
    }
    while ( !v8 );
    v33 = *(_QWORD *)v8;
    v27 = v33;
    v9 = *(_DWORD *)(v8 + 16);
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    v10 = (volatile signed __int32 *)CsrLocateThreadByClientId(&BaseAddress, v39);
    BaseAddress = (PVOID)v10;
    v11 = v27;
    if ( v27 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 100));
      CsrFinalizeContext(v27, 0, v9);
      v11 = v27;
    }
    if ( v6 == 1 )
      break;
    if ( v6 != 3 )
    {
      switch ( v6 )
      {
        case 5:
          CsrFinalizeContext(v11, 1, v9);
          goto LABEL_26;
        case 6:
          if ( v10 && v40 == *(_QWORD *)v10 )
          {
            _InterlockedIncrement(v10 + 19);
            CsrDestroyThread(v39);
            CsrLockedDereferenceThread((PVOID)v10);
          }
          goto LABEL_26;
        case 7:
          RtlLeaveCriticalSection(&CsrProcessStructureLock);
          v2 = v36;
          HIDWORD(v40) = -2147418111;
          goto LABEL_74;
      }
      if ( v6 != 9 )
      {
        if ( v6 == 12 )
        {
          RtlLeaveCriticalSection(&CsrProcessStructureLock);
          v2 = (_BYTE *)((unsigned __int64)v36 & -(__int64)((v38 & 0x2000) != 0));
          goto LABEL_74;
        }
        if ( v6 == 13 )
        {
          ProcessByClientId = CsrLocateProcessByClientId(v40);
          v13 = ProcessByClientId;
          if ( ProcessByClientId )
          {
            _InterlockedIncrement((volatile signed __int32 *)(ProcessByClientId + 100));
            *(_DWORD *)(ProcessByClientId + 92) |= 0x1000u;
            CsrDestroyProcessByPtr(ProcessByClientId);
            CsrUnlockProcess(v13);
            goto LABEL_74;
          }
        }
LABEL_26:
        RtlLeaveCriticalSection(&CsrProcessStructureLock);
LABEL_74:
        v15 = v27;
LABEL_75:
        v16 = v15 == 0;
        goto LABEL_76;
      }
      if ( v10 || (CsrThreadLazyRegister(&BaseAddress, v36), (v10 = (volatile signed __int32 *)BaseAddress) != 0) )
        _InterlockedIncrement(v10 + 19);
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
      QueueHardError((PVOID)v10);
      if ( !v10 )
        goto LABEL_74;
      v14 = (PVOID)v10;
LABEL_35:
      CsrDereferenceThread(v14);
      goto LABEL_74;
    }
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    v15 = v27;
    v16 = v27 == 0;
    if ( !v27 )
    {
      if ( !v10 )
      {
        v40 = 0;
        v17 = HIWORD(v41);
        if ( (unsigned int)v17 < 6
          && (_mm_lfence(), (v18 = CsrLoadedServerDll[v17]) != 0)
          && (v19 = (unsigned int)(unsigned __int16)v41 - *(_DWORD *)(v18 + 32),
              (unsigned int)v19 < *(_DWORD *)(v18 + 36) - *(_DWORD *)(v18 + 32)) )
        {
          v42 = 0;
          CsrpCheckRequestThreads();
          (*(void (__fastcall **)(_BYTE *, int *))(*(_QWORD *)(v18 + 40) + 8 * v19))(v36, &v28);
          _InterlockedIncrement(&CsrpStaticThreadCount);
        }
        else
        {
          CsrpLogModuleFailureInt("CsrApiRequestThread", v5);
        }
      }
      goto LABEL_75;
    }
LABEL_76:
    Self = v34;
    if ( !v16 )
      CsrDereferenceProcess(v15);
  }
  if ( !v10 )
  {
    v20 = CsrThreadLazyRegister(&BaseAddress, v36);
    v10 = (volatile signed __int32 *)BaseAddress;
    if ( !BaseAddress )
    {
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
      v2 = v36;
      v21 = -1073741649;
      if ( v20 < 0 )
        v21 = v20;
      v42 = v21;
      goto LABEL_74;
    }
  }
  _InterlockedIncrement(v10 + 19);
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  v22 = HIWORD(v41);
  if ( (unsigned int)v22 < 6 )
  {
    _mm_lfence();
    v23 = CsrLoadedServerDll[v22];
    if ( v23 )
    {
      v24 = (unsigned int)(unsigned __int16)v41 - *(_DWORD *)(v23 + 32);
      if ( (unsigned int)v24 < *(_DWORD *)(v23 + 36) - *(_DWORD *)(v23 + 32)
        && (v25 = (unsigned int)v24, *(_QWORD *)(*(_QWORD *)(v23 + 40) + 8 * v24)) )
      {
        v2 = v36;
        v32 = v36;
        v42 = 0;
        if ( !v40 || CsrCaptureArguments((__int64)BaseAddress, (__int64)v36) )
        {
          *(_QWORD *)Interval.QuadPart = BaseAddress;
          v28 = 0;
          CsrpCheckRequestThreads();
          v42 = (*(__int64 (__fastcall **)(_BYTE *, int *))(*(_QWORD *)(v23 + 40) + 8 * v25))(v36, &v28);
          v15 = v27;
          _InterlockedIncrement(&CsrpStaticThreadCount);
          *(_QWORD *)Interval.QuadPart = ExceptionList;
          v26 = v28;
          if ( v28 >= 4 )
          {
            v26 = 0;
            v28 = 0;
          }
          if ( v26 != 1 && v40 )
          {
            CsrReleaseCapturedArguments((__int64)v36);
            v26 = v28;
          }
          if ( v26 == 2 )
          {
            NtAlpcSendWaitReceivePort(CsrApiPort, 0x10000, v36, 0, 0, 0, 0, 0);
            v26 = v28;
          }
          if ( v26 )
            v2 = 0;
          if ( v26 != 1 )
            CsrDereferenceThread(BaseAddress);
          goto LABEL_75;
        }
      }
      else
      {
        v2 = v36;
        v42 = -1073741649;
        CsrpLogModuleFailureInt("CsrApiRequestThread", -1073741649);
      }
      v14 = BaseAddress;
      goto LABEL_35;
    }
    v10 = (volatile signed __int32 *)BaseAddress;
  }
  v2 = v36;
  v42 = -1073741649;
  CsrDereferenceThread((PVOID)v10);
  CsrpLogModuleFailureInt("CsrApiRequestThread", v42);
  goto LABEL_74;
}

```

## disassembly

```asm
0x1800097f0  mov     [rsp+arg_8], rbx
0x1800097f5  mov     [rsp+arg_10], rsi
0x1800097fa  push    rdi
0x1800097fb  push    r12
0x1800097fd  push    r13
0x1800097ff  push    r14
0x180009801  push    r15
0x180009803  sub     rsp, 4B0h
0x18000980a  mov     rax, cs:__security_cookie
0x180009811  xor     rax, rsp
0x180009814  mov     [rsp+4D8h+var_38], rax
0x18000981c  mov     rdi, rcx
0x18000981f  xor     edx, edx; Val
0x180009821  mov     r8d, 3B8h; Size
0x180009827  lea     rcx, [rsp+4D8h+var_448]; void *
0x18000982f  call    memset_0
0x180009834  xor     ebx, ebx
0x180009836  mov     esi, ebx
0x180009838  mov     [rsp+4D8h+var_490], ebx
0x18000983c  mov     [rsp+4D8h+var_478], rbx
0x180009841  mov     r14, gs:30h
0x18000984a  mov     [rsp+4D8h+var_460], r14
0x18000984f  jmp     short loc_180009874
0x180009851  mov     [r14+800h], rbx
0x180009858  mov     qword ptr [rsp+4D8h+Interval], 0FFFFFFFFEE1E5D00h
0x180009861  lea     rdx, [rsp+4D8h+Interval]; Interval
0x180009866  xor     ecx, ecx; Alertable
0x180009868  call    cs:__imp_NtDelayExecution
0x18000986f  nop     dword ptr [rax+rax+00h]
0x180009874  call    CsrConnectToUser
0x180009879  test    rax, rax
0x18000987c  jz      short loc_180009851
0x18000987e  lea     rax, [r14+70h]
0x180009882  mov     qword ptr [rsp+4D8h+Interval], rax
0x180009887  mov     rax, [rax]
0x18000988a  mov     [rsp+4D8h+var_458], rax
0x180009892  test    rdi, rdi
0x180009895  jz      short loc_1800098E7
0x180009897  mov     ecx, ebx
0x180009899  mov     rdx, gs:60h
0x1800098a2  mov     eax, cs:ServiceSessionId
0x1800098a8  cmp     [rdx+2C0h], eax
0x1800098ae  jnz     short loc_1800098C5
0x1800098b0  mov     rcx, cs:CsrApiPort; PortHandle
0x1800098b7  call    cs:__imp_NtSetDefaultHardErrorPort
0x1800098be  nop     dword ptr [rax+rax+00h]
0x1800098c3  mov     ecx, eax
0x1800098c5  mov     [rdi], ecx
0x1800098c7  xor     edx, edx; PreviousState
0x1800098c9  mov     rcx, [rdi+8]; EventHandle
0x1800098cd  call    cs:__imp_NtSetEvent
0x1800098d4  nop     dword ptr [rax+rax+00h]
0x1800098d9  lock inc cs:CsrpStaticThreadCount
0x1800098e0  lock inc cs:CsrpDynamicThreadTotal
0x1800098e7  lea     r9, [rsp+4D8h+var_478]
0x1800098ec  mov     r8d, 48h ; 'H'
0x1800098f2  lea     rdx, [rsp+4D8h+var_88]
0x1800098fa  mov     ecx, 60000000h
0x1800098ff  call    cs:__imp_AlpcInitializeMessageAttribute
0x180009906  nop     dword ptr [rax+rax+00h]
0x18000990b  lea     r12, CsrProcessStructureLock
0x180009912  movups  xmm0, xmmword ptr [r14+40h]
0x180009917  movdqu  xmmword ptr [r14+7D8h], xmm0
0x180009920  mov     [rsp+4D8h+var_478], 3B8h
0x180009929  mov     [rsp+4D8h+var_84], ebx
0x180009930  mov     [rsp+4D8h+var_4A0], rbx
0x180009935  lea     rax, [rsp+4D8h+var_88]
0x18000993d  mov     [rsp+4D8h+var_4A8], rax
0x180009942  lea     rax, [rsp+4D8h+var_478]
0x180009947  mov     [rsp+4D8h+var_4B0], rax
0x18000994c  lea     rax, [rsp+4D8h+var_448]
0x180009954  mov     qword ptr [rsp+4D8h+var_4B8], rax
0x180009959  xor     r9d, r9d
0x18000995c  mov     r8, rsi
0x18000995f  mov     edx, 10000h
0x180009964  mov     rcx, cs:CsrApiPort
0x18000996b  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180009972  nop     dword ptr [rax+rax+00h]
0x180009977  mov     r13d, eax
0x18000997a  mov     rsi, rbx
0x18000997d  test    eax, eax
0x18000997f  js      short loc_180009912
0x180009981  mov     [rsp+4D8h+var_470], rbx
0x180009986  movsx   rax, [rsp+4D8h+var_446]
0x18000998f  mov     r8d, 3B8h
0x180009995  sub     r8, rax; Size
0x180009998  lea     rcx, [rsp+4D8h+var_448]
0x1800099a0  add     rcx, rax; void *
0x1800099a3  xor     edx, edx; Val
0x1800099a5  call    memset_0
0x1800099aa  movups  xmm0, [rsp+4D8h+var_440]
0x1800099b2  movdqu  xmmword ptr [r14+7D8h], xmm0
0x1800099bb  mov     eax, 0FFh
0x1800099c0  movzx   r15d, [rsp+4D8h+var_444]
0x1800099c9  and     r15w, ax
0x1800099cd  cmp     r15w, 0Ah
0x1800099d2  jnz     short loc_180009A14
0x1800099d4  test    [rsp+4D8h+var_84], 40000000h
0x1800099df  jz      short loc_1800099FC
0x1800099e1  mov     edx, 40000000h
0x1800099e6  lea     rcx, [rsp+4D8h+var_88]
0x1800099ee  call    cs:__imp_AlpcGetMessageAttribute
0x1800099f5  nop     dword ptr [rax+rax+00h]
0x1800099fa  jmp     short loc_1800099FF
0x1800099fc  mov     rax, rbx
0x1800099ff  mov     rdx, rax
0x180009a02  lea     rcx, [rsp+4D8h+var_448]
0x180009a0a  call    CsrApiHandleConnectionRequest
0x180009a0f  jmp     loc_180009912
0x180009a14  mov     edx, 20000000h
0x180009a19  lea     rcx, [rsp+4D8h+var_88]
0x180009a21  call    cs:__imp_AlpcGetMessageAttribute
0x180009a28  nop     dword ptr [rax+rax+00h]
0x180009a2d  test    rax, rax
0x180009a30  jz      loc_180009912
0x180009a36  mov     rcx, [rax]
0x180009a39  mov     [rsp+4D8h+var_498], rcx
0x180009a3e  mov     [rsp+4D8h+var_468], rcx
0x180009a43  mov     r14d, [rax+10h]
0x180009a47  mov     rcx, r12; CriticalSection
0x180009a4a  call    cs:__imp_RtlEnterCriticalSection
0x180009a51  nop     dword ptr [rax+rax+00h]
0x180009a56  lea     rdx, [rsp+4D8h+var_440]
0x180009a5e  lea     rcx, [rsp+4D8h+BaseAddress]
0x180009a63  call    CsrLocateThreadByClientId
0x180009a68  mov     rdi, rax
0x180009a6b  mov     [rsp+4D8h+BaseAddress], rax
0x180009a70  mov     r9, [rsp+4D8h+var_498]
0x180009a75  test    r9, r9
0x180009a78  jz      short loc_180009A91
0x180009a7a  lock inc dword ptr [r9+64h]
0x180009a7f  mov     r8d, r14d
0x180009a82  xor     edx, edx
0x180009a84  mov     rcx, r9
0x180009a87  call    CsrFinalizeContext
0x180009a8c  mov     r9, [rsp+4D8h+var_498]
0x180009a91  movzx   ecx, r15w
0x180009a95  sub     ecx, 1
0x180009a98  jz      loc_180009CFB
0x180009a9e  sub     ecx, 2
0x180009aa1  jz      loc_180009C1F
0x180009aa7  sub     ecx, 2
0x180009aaa  jz      loc_180009C0A
0x180009ab0  sub     ecx, 1
0x180009ab3  jz      loc_180009BD2
0x180009ab9  sub     ecx, 1
0x180009abc  jz      loc_180009BAB
0x180009ac2  sub     ecx, 2
0x180009ac5  jz      loc_180009B51
0x180009acb  sub     ecx, 3
0x180009ace  jz      short loc_180009B1C
0x180009ad0  cmp     ecx, 1
0x180009ad3  jz      short loc_180009AE9
0x180009ad5  mov     rcx, r12; CriticalSection
0x180009ad8  call    cs:__imp_RtlLeaveCriticalSection
0x180009adf  nop     dword ptr [rax+rax+00h]
0x180009ae4  jmp     loc_180009F9C
0x180009ae9  mov     rcx, [rsp+4D8h+var_420]
0x180009af1  call    CsrLocateProcessByClientId
0x180009af6  mov     rdi, rax
0x180009af9  test    rax, rax
0x180009afc  jz      short loc_180009AD5
0x180009afe  lock inc dword ptr [rax+64h]
0x180009b02  bts     dword ptr [rax+5Ch], 0Ch
0x180009b07  mov     rcx, rax
0x180009b0a  call    CsrDestroyProcessByPtr
0x180009b0f  mov     rcx, rdi
0x180009b12  call    CsrUnlockProcess
0x180009b17  jmp     loc_180009F9C
0x180009b1c  mov     rcx, r12; CriticalSection
0x180009b1f  call    cs:__imp_RtlLeaveCriticalSection
0x180009b26  nop     dword ptr [rax+rax+00h]
0x180009b2b  movzx   eax, [rsp+4D8h+var_444]
0x180009b33  mov     ecx, 2000h
0x180009b38  and     ax, cx
0x180009b3b  neg     ax
0x180009b3e  sbb     rsi, rsi
0x180009b41  lea     rax, [rsp+4D8h+var_448]
0x180009b49  and     rsi, rax
0x180009b4c  jmp     loc_180009F9C
0x180009b51  test    rdi, rdi
0x180009b54  jnz     short loc_180009B72
0x180009b56  lea     rdx, [rsp+4D8h+var_448]
0x180009b5e  lea     rcx, [rsp+4D8h+BaseAddress]
0x180009b63  call    CsrThreadLazyRegister
0x180009b68  mov     rdi, [rsp+4D8h+BaseAddress]
0x180009b6d  test    rdi, rdi
0x180009b70  jz      short loc_180009B76
0x180009b72  lock inc dword ptr [rdi+4Ch]
0x180009b76  mov     rcx, r12; CriticalSection
0x180009b79  call    cs:__imp_RtlLeaveCriticalSection
0x180009b80  nop     dword ptr [rax+rax+00h]
0x180009b85  lea     rdx, [rsp+4D8h+var_448]
0x180009b8d  mov     rcx, rdi; BaseAddress
0x180009b90  call    QueueHardError
0x180009b95  test    rdi, rdi
0x180009b98  jz      loc_180009F9C
0x180009b9e  mov     rcx, rdi; BaseAddress
0x180009ba1  call    CsrDereferenceThread
0x180009ba6  jmp     loc_180009F9C
0x180009bab  mov     rcx, r12; CriticalSection
0x180009bae  call    cs:__imp_RtlLeaveCriticalSection
0x180009bb5  nop     dword ptr [rax+rax+00h]
0x180009bba  lea     rsi, [rsp+4D8h+var_448]
0x180009bc2  mov     dword ptr [rsp+4D8h+var_420+4], 80010001h
0x180009bcd  jmp     loc_180009F9C
0x180009bd2  test    rdi, rdi
0x180009bd5  jz      loc_180009AD5
0x180009bdb  mov     rax, [rsp+4D8h+var_420]
0x180009be3  cmp     rax, [rdi]
0x180009be6  jnz     loc_180009AD5
0x180009bec  lock inc dword ptr [rdi+4Ch]
0x180009bf0  lea     rcx, [rsp+4D8h+var_440]
0x180009bf8  call    CsrDestroyThread
0x180009bfd  mov     rcx, rdi; BaseAddress
0x180009c00  call    CsrLockedDereferenceThread
0x180009c05  jmp     loc_180009AD5
0x180009c0a  mov     r8d, r14d
0x180009c0d  mov     edx, 1
0x180009c12  mov     rcx, r9
0x180009c15  call    CsrFinalizeContext
0x180009c1a  jmp     loc_180009AD5
0x180009c1f  mov     rcx, r12; CriticalSection
0x180009c22  call    cs:__imp_RtlLeaveCriticalSection
0x180009c29  nop     dword ptr [rax+rax+00h]
0x180009c2e  mov     r15, [rsp+4D8h+var_498]
0x180009c33  test    r15, r15
0x180009c36  jnz     loc_180009FA4
0x180009c3c  test    rdi, rdi
0x180009c3f  jnz     loc_180009FA1
0x180009c45  mov     [rsp+4D8h+var_420], rbx
0x180009c4d  mov     ecx, [rsp+4D8h+var_418]
0x180009c54  mov     r9d, ecx
0x180009c57  shr     r9d, 10h
0x180009c5b  cmp     r9d, 6
0x180009c5f  jnb     short loc_180009CD9
0x180009c61  lfence
0x180009c64  lea     rdx, CsrLoadedServerDll
0x180009c6b  mov     rdi, [rdx+r9*8]
0x180009c6f  test    rdi, rdi
0x180009c72  jz      short loc_180009CD9
0x180009c74  movzx   r9d, cx
0x180009c78  mov     r14d, r9d
0x180009c7b  sub     r14d, [rdi+20h]
0x180009c7f  mov     eax, [rdi+24h]
0x180009c82  sub     eax, [rdi+20h]
0x180009c85  cmp     r14d, eax
0x180009c88  jb      short loc_180009C91
0x180009c8a  mov     edx, 480h
0x180009c8f  jmp     short loc_180009CDE
0x180009c91  mov     [rsp+4D8h+var_414], ebx
0x180009c98  call    CsrpCheckRequestThreads
0x180009c9d  nop
0x180009c9e  mov     rax, [rdi+28h]
0x180009ca2  mov     rax, [rax+r14*8]
0x180009ca6  lea     rdx, [rsp+4D8h+var_490]
0x180009cab  lea     rcx, [rsp+4D8h+var_448]
0x180009cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb8  jmp     short loc_180009CCD
0x180009cba  xor     ebx, ebx
0x180009cbc  lea     r12, CsrProcessStructureLock
0x180009cc3  mov     rsi, [rsp+4D8h+var_470]
0x180009cc8  mov     r15, [rsp+4D8h+var_468]
0x180009ccd  lock inc cs:CsrpStaticThreadCount
0x180009cd4  jmp     loc_180009FA1
0x180009cd9  mov     edx, 470h
0x180009cde  lea     r8, qword_18000C660
0x180009ce5  mov     [rsp+4D8h+var_4B8], r13d; int
0x180009cea  lea     rcx, aCsrapirequestt; "CsrApiRequestThread"
0x180009cf1  call    CsrpLogModuleFailureInt
0x180009cf6  jmp     loc_180009FA1
0x180009cfb  test    rdi, rdi
0x180009cfe  jnz     short loc_180009D4E
0x180009d00  lea     rdx, [rsp+4D8h+var_448]
0x180009d08  lea     rcx, [rsp+4D8h+BaseAddress]
0x180009d0d  call    CsrThreadLazyRegister
0x180009d12  mov     r14d, eax
0x180009d15  mov     rdi, [rsp+4D8h+BaseAddress]
0x180009d1a  test    rdi, rdi
0x180009d1d  jnz     short loc_180009D4E
0x180009d1f  mov     rcx, r12; CriticalSection
0x180009d22  call    cs:__imp_RtlLeaveCriticalSection
0x180009d29  nop     dword ptr [rax+rax+00h]
0x180009d2e  lea     rsi, [rsp+4D8h+var_448]
0x180009d36  mov     ecx, 0C00000AFh
0x180009d3b  test    r14d, r14d
0x180009d3e  cmovs   ecx, r14d
0x180009d42  mov     [rsp+4D8h+var_414], ecx
0x180009d49  jmp     loc_180009F9C
0x180009d4e  lock inc dword ptr [rdi+4Ch]
0x180009d52  mov     rcx, r12; CriticalSection
0x180009d55  call    cs:__imp_RtlLeaveCriticalSection
0x180009d5c  nop     dword ptr [rax+rax+00h]
0x180009d61  mov     ecx, [rsp+4D8h+var_418]
0x180009d68  mov     r14d, ecx
0x180009d6b  shr     r14d, 10h
0x180009d6f  cmp     r14d, 6
0x180009d73  jnb     loc_180009F5B
0x180009d79  lfence
0x180009d7c  lea     rdx, CsrLoadedServerDll
  ... truncated ...
```
