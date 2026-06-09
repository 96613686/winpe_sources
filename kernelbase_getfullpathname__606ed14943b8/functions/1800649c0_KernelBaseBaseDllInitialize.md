# _KernelBaseBaseDllInitialize

- ea: `0x1800649c0`
- end: `0x180064f44`
- name: `_KernelBaseBaseDllInitialize`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006493c`

## callees

- `0x1800649c0`
- `0x180064f90`
- `0x180065484`
- `0x180065520`
- `0x1800655c8`
- `0x180065c00`
- `0x180066708`
- `0x180066be4`
- `0x180098538`
- `0x1800ed4cc`
- `0x180110fb8`
- `0x18011b768`
- `0x180120e70`
- `0x18012aa08`
- `0x18018e8c0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18019b586`
- `ntdll!RtlFreeAnsiString` at `0x18019b586`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180064ca6`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180064ca6`
- `ntdll!RtlDeleteCriticalSection` at `0x180064f2c`
- `ntdll!RtlDeleteCriticalSection` at `0x180064f2c`
- `ntdll!RtlInitializeCriticalSection` at `0x180064d1a`
- `ntdll!RtlInitializeCriticalSection` at `0x180064d1a`
- `ntdll!NtQuerySystemInformation` at `0x180064b28`
- `ntdll!NtQuerySystemInformation` at `0x180064b28`
- `ntdll!RtlEncodePointer` at `0x180064ccf`
- `ntdll!RtlEncodePointer` at `0x180064ccf`
- `ntdll!RtlRandomEx` at `0x180064b41`
- `ntdll!RtlRandomEx` at `0x180064b5f`
- `ntdll!RtlRandomEx` at `0x180064b41`
- `ntdll!RtlRandomEx` at `0x180064b5f`
- `ntdll!RtlFreeHeap` at `0x180064ea2`
- `ntdll!RtlFreeHeap` at `0x18019b5b1`
- `ntdll!RtlFreeHeap` at `0x180064ea2`
- `ntdll!RtlFreeHeap` at `0x18019b5b1`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180064ad7`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180064ad7`
- `ntdll!RtlCreateTagHeap` at `0x180064abf`
- `ntdll!RtlCreateTagHeap` at `0x180064abf`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x180064cc1`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x180064cc1`
- `ntdll!RtlCleanUpTEBLangLists` at `0x180064a5f`
- `ntdll!RtlCleanUpTEBLangLists` at `0x180064a5f`
- `ntdll!CsrClientConnectToServer` at `0x180064bc1`
- `ntdll!CsrClientConnectToServer` at `0x180064bc1`

## string_xrefs

- `0x180064ab2`: `BASEDLL!`

## pseudocode

```c
char __fastcall KernelBaseBaseDllInitialize(__int64 a1, unsigned int a2, __int64 a3)
{
  struct _PEB *v5; // rbx
  char result; // al
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rax
  ULONG SessionId; // edi
  char *v9; // r9
  __int16 v10; // ax
  WCHAR *v11; // r10
  WCHAR *v12; // rcx
  WCHAR *v13; // r10
  WCHAR *v14; // rcx
  PVOID v15; // rax
  __int16 v16; // ax
  unsigned __int8 ServerToServerCall[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Seed; // [rsp+34h] [rbp-CCh] BYREF
  HMODULE (__stdcall *ConnectionInfo)(LPCWSTR, HANDLE, DWORD); // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[256]; // [rsp+40h] [rbp-C0h] BYREF

  Seed = 0;
  ServerToServerCall[0] = 0;
  v5 = NtCurrentPeb();
  Seed = (ULONG)NtCurrentTeb()->ClientId.UniqueProcess;
  if ( !a2 )
  {
    TraceLoggingUnregister_EtwEventUnregister();
    if ( !a3 )
    {
      v16 = BasepInitializationStage;
      if ( (unsigned __int16)BasepInitializationStage > 0x258u )
      {
        ConsoleCleanupConnectionState(&ConsoleConnectionState);
        RtlDeleteCriticalSection(&ConsoleStateLock);
        v16 = BasepInitializationStage;
      }
      if ( (unsigned __int16)v16 > 0x1F4u )
      {
        BasepUnInitComputerNameCache();
        v16 = BasepInitializationStage;
      }
      a1 = 400;
      if ( (unsigned __int16)v16 > 0x190u )
        BaseNlsDllInitialize(400, 0, 0);
      if ( BaseAnsiCommandLine.Buffer )
        RtlFreeAnsiString(&BaseAnsiCommandLine);
    }
    if ( BasepFilterInfo )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, BasepFilterInfo);
    ConnectionInfo = LoadLibraryExW;
    return RegKrnInitialize(a1, a2, a3);
  }
  if ( a2 != 1 )
  {
    if ( a2 == 2 )
    {
      if ( ConsoleIsConsoleApplication )
        SetTEBLangID();
    }
    else if ( a2 == 3 )
    {
      RtlCleanUpTEBLangLists();
      if ( NtCurrentTeb()->SavedPriorityState )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtCurrentTeb()->SavedPriorityState);
      BaseNlsThreadCleanup();
    }
    return RegKrnInitialize(a1, a2, a3);
  }
  ProcessParameters = v5->ProcessParameters;
  BaseDllHandle = a1;
  if ( (ProcessParameters->Flags & 0x80000000) != 0 )
    BasepIsSecureProcess = 1;
  KernelBaseDllInitializeMemoryManager();
  KernelBaseGlobalData = RtlCreateTagHeap(NtCurrentPeb()->ProcessHeap, 0, (PWSTR)L"BASEDLL!", (PWSTR)L"TMP");
  SessionId = v5->SessionId;
  if ( SessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
    StringCbCopyW(pszDest, 0x200u, L"\\Windows");
  else
    StringCbPrintfW(pszDest, 0x200u, L"%ws\\%ld%ws", L"\\Sessions", SessionId, L"\\Windows");
  if ( NtQuerySystemInformation(SystemBasicInformation, &SysInfo, 0x40u, 0) < 0 )
    return 0;
  BasepFiberCookie = (unsigned __int64)RtlRandomEx(&Seed) << 32;
  BasepFiberCookie = RtlRandomEx(&Seed) | (unsigned __int64)BasepFiberCookie;
  BasepInitializationStage = 100;
  ConnectionInfo = (HMODULE (__stdcall *)(LPCWSTR, HANDLE, DWORD))CtrlRoutine;
  if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) == 0 )
  {
    if ( CsrClientConnectToServer(pszDest, 1u, &ConnectionInfo, (PULONG)8, ServerToServerCall) >= 0 )
      goto LABEL_17;
    return 0;
  }
  if ( (int)CsrpLocalSetupForSecureProcess() < 0 )
    return 0;
  ServerToServerCall[0] = 0;
LABEL_17:
  BasepInitializationStage = 200;
  v9 = (char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
     - (unsigned __int64)NtCurrentPeb()[1].Ldr;
  BaseStaticServerData = (__int64)v9;
  v10 = *((_WORD *)v9 + 28);
  byte_1803AAD44 = ServerToServerCall[0] != 0;
  BaseRCNumber = v10;
  qword_1803AAD48 = *(_QWORD *)v9;
  v11 = (WCHAR *)*((_QWORD *)v9 + 1);
  UnicodeString = v11;
  if ( v11 )
    v12 = (WCHAR *)((char *)v11
                  + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                  + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                  - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                              + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                              - (unsigned __int64)NtCurrentPeb()[1].Ldr
                              + 2536)
                  - (unsigned __int64)NtCurrentPeb()[1].Ldr);
  else
    v12 = 0;
  UnicodeString = v12;
  qword_1803AAD58 = *((_QWORD *)v9 + 2);
  v13 = (WCHAR *)*((_QWORD *)v9 + 3);
  Src = v13;
  if ( v13 )
    v14 = (WCHAR *)((char *)v13
                  + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                  + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                  - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                              + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                              - (unsigned __int64)NtCurrentPeb()[1].Ldr
                              + 2536)
                  - (unsigned __int64)NtCurrentPeb()[1].Ldr);
  else
    v14 = 0;
  Src = v14;
  BaseUnicodeCommandLine = v5->ProcessParameters->CommandLine;
  if ( RtlUnicodeStringToAnsiString(&BaseAnsiCommandLine, &BaseUnicodeCommandLine, 1u) < 0 )
  {
    BaseAnsiCommandLine.Buffer = 0;
    *(_DWORD *)&BaseAnsiCommandLine.Length = 0;
  }
  RtlSetUnhandledExceptionFilter((PRTLP_UNHANDLED_EXCEPTION_FILTER)UnhandledExceptionFilter);
  v15 = RtlEncodePointer(0);
  BasepInitializationStage = 400;
  BasepCurrentTopLevelFilter = v15;
  if ( !(unsigned __int8)BaseNlsDllInitialize(400, 1, BaseStaticServerData) )
    return 0;
  BasepInitializationStage = 500;
  if ( RtlInitializeCriticalSection(&stru_1803AADF0) < 0 )
    return 0;
  BasepInitializationStage = 600;
  result = ConsoleInitialize();
  if ( result )
  {
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    BasepDiscountProcessFreezeTimeFromUnbiasedTime = (unsigned int)Feature_DiscountProcessFreezeTimeFromUnbiasedInterruptTimePrecise__private_IsEnabledDeviceUsageNoInline() != 0;
    BasepInitializationStage = 700;
    return RegKrnInitialize(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800649c0  push    rbp
0x1800649c2  push    rbx
0x1800649c3  push    rsi
0x1800649c4  push    rdi
0x1800649c5  push    r14
0x1800649c7  push    r15
0x1800649c9  lea     rbp, [rsp-158h]
0x1800649d1  sub     rsp, 258h
0x1800649d8  mov     rax, cs:__security_cookie
0x1800649df  xor     rax, rsp
0x1800649e2  mov     [rbp+180h+var_40], rax
0x1800649e9  xor     r15d, r15d
0x1800649ec  mov     rsi, r8
0x1800649ef  mov     [rsp+280h+Seed], r15d
0x1800649f4  mov     r14d, edx
0x1800649f7  mov     [rsp+280h+var_250], r15b
0x1800649fc  mov     rbx, gs:60h
0x180064a05  mov     rax, gs:30h
0x180064a0e  mov     r9d, [rax+40h]
0x180064a12  mov     eax, edx
0x180064a14  mov     [rsp+280h+Seed], r9d
0x180064a19  test    edx, edx
0x180064a1b  jz      loc_180064EF6
0x180064a21  sub     eax, 1
0x180064a24  jz      short loc_180064A88
0x180064a26  sub     eax, 1
0x180064a29  jz      loc_180064D74
0x180064a2f  cmp     eax, 1
0x180064a32  jz      short loc_180064A5F
0x180064a34  mov     r8, rsi
0x180064a37  mov     edx, r14d
0x180064a3a  call    RegKrnInitialize
0x180064a3f  mov     rcx, [rbp+180h+var_40]
0x180064a46  xor     rcx, rsp; StackCookie
0x180064a49  call    __security_check_cookie
0x180064a4e  add     rsp, 258h
0x180064a55  pop     r15
0x180064a57  pop     r14
0x180064a59  pop     rdi
0x180064a5a  pop     rsi
0x180064a5b  pop     rbx
0x180064a5c  pop     rbp
0x180064a5d  retn
0x180064a5f  call    cs:__imp_RtlCleanUpTEBLangLists
0x180064a66  nop     dword ptr [rax+rax+00h]
0x180064a6b  mov     rax, gs:30h
0x180064a74  cmp     [rax+1768h], r15
0x180064a7b  jnz     loc_180064E83
0x180064a81  call    BaseNlsThreadCleanup
0x180064a86  jmp     short loc_180064A34
0x180064a88  mov     rax, [rbx+20h]
0x180064a8c  mov     cs:BaseDllHandle, rcx
0x180064a93  cmp     [rax+8], r15d
0x180064a97  jl      loc_180064EB3
0x180064a9d  call    KernelBaseDllInitializeMemoryManager
0x180064aa2  mov     rcx, gs:60h
0x180064aab  lea     r9, TagSubName; "TMP"
0x180064ab2  lea     r8, TagName; "BASEDLL!"
0x180064ab9  xor     edx, edx; Flags
0x180064abb  mov     rcx, [rcx+30h]; HeapHandle
0x180064abf  call    cs:__imp_RtlCreateTagHeap
0x180064ac6  nop     dword ptr [rax+rax+00h]
0x180064acb  mov     cs:KernelBaseGlobalData, eax
0x180064ad1  mov     edi, [rbx+2C0h]
0x180064ad7  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180064ade  nop     dword ptr [rax+rax+00h]
0x180064ae3  mov     edx, 200h; cbDest
0x180064ae8  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180064aed  cmp     edi, eax
0x180064aef  jz      loc_180064EBF
0x180064af5  lea     rax, aWindows; "\\Windows"
0x180064afc  mov     [rsp+280h+var_258], rax
0x180064b01  lea     r9, aSessions; "\\Sessions"
0x180064b08  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x180064b0f  mov     dword ptr [rsp+280h+ServerToServerCall], edi
0x180064b13  call    StringCbPrintfW
0x180064b18  xor     r9d, r9d; ReturnLength
0x180064b1b  lea     rdx, SysInfo; SystemInformation
0x180064b22  xor     ecx, ecx; SystemInformationClass
0x180064b24  lea     r8d, [r9+40h]; SystemInformationLength
0x180064b28  call    cs:__imp_NtQuerySystemInformation
0x180064b2f  nop     dword ptr [rax+rax+00h]
0x180064b34  test    eax, eax
0x180064b36  js      loc_180064E7B
0x180064b3c  lea     rcx, [rsp+280h+Seed]; Seed
0x180064b41  call    cs:__imp_RtlRandomEx
0x180064b48  nop     dword ptr [rax+rax+00h]
0x180064b4d  mov     eax, eax
0x180064b4f  lea     rcx, [rsp+280h+Seed]; Seed
0x180064b54  shl     rax, 20h
0x180064b58  mov     cs:BasepFiberCookie, rax
0x180064b5f  call    cs:__imp_RtlRandomEx
0x180064b66  nop     dword ptr [rax+rax+00h]
0x180064b6b  mov     eax, eax
0x180064b6d  or      cs:BasepFiberCookie, rax
0x180064b74  mov     eax, 64h ; 'd'
0x180064b79  mov     cs:BasepInitializationStage, ax
0x180064b80  lea     rax, CtrlRoutine
0x180064b87  mov     [rsp+280h+ConnectionInfo], rax
0x180064b8c  mov     rax, gs:60h
0x180064b95  mov     rcx, [rax+20h]
0x180064b99  cmp     [rcx+8], r15d
0x180064b9d  jl      loc_180064ED0
0x180064ba3  mov     r9d, 8; ConnectionInfoSize
0x180064ba9  lea     rax, [rsp+280h+var_250]
0x180064bae  lea     r8, [rsp+280h+ConnectionInfo]; ConnectionInfo
0x180064bb3  mov     [rsp+280h+ServerToServerCall], rax; ServerToServerCall
0x180064bb8  lea     rcx, [rsp+280h+pszDest]; ObjectDirectory
0x180064bbd  lea     edx, [r9-7]; ServerId
0x180064bc1  call    cs:__imp_CsrClientConnectToServer
0x180064bc8  nop     dword ptr [rax+rax+00h]
0x180064bcd  test    eax, eax
0x180064bcf  js      loc_180064E7B
0x180064bd5  mov     eax, 0C8h
0x180064bda  mov     cs:BasepInitializationStage, ax
0x180064be1  mov     rax, gs:60h
0x180064bea  mov     rcx, [rax+98h]
0x180064bf1  mov     rax, gs:60h
0x180064bfa  mov     r9, [rcx+8]
0x180064bfe  sub     r9, [rax+380h]
0x180064c05  mov     rax, gs:60h
0x180064c0e  add     r9, [rax+88h]
0x180064c15  cmp     [rsp+280h+var_250], r15b
0x180064c1a  mov     cs:BaseStaticServerData, r9
0x180064c21  movzx   eax, word ptr [r9+38h]
0x180064c26  setnz   cs:byte_1803AAD44
0x180064c2d  mov     cs:BaseRCNumber, ax
0x180064c34  mov     rax, [r9]
0x180064c37  mov     cs:qword_1803AAD48, rax
0x180064c3e  mov     r10, [r9+8]
0x180064c42  mov     cs:UnicodeString, r10
0x180064c49  test    r10, r10
0x180064c4c  jnz     loc_180064D8B
0x180064c52  mov     rcx, r15
0x180064c55  mov     cs:UnicodeString, rcx
0x180064c5c  mov     rax, [r9+10h]
0x180064c60  mov     cs:qword_1803AAD58, rax
0x180064c67  mov     r10, [r9+18h]
0x180064c6b  mov     cs:Src, r10
0x180064c72  test    r10, r10
0x180064c75  jnz     loc_180064E03
0x180064c7b  mov     rcx, r15
0x180064c7e  mov     cs:Src, rcx
0x180064c85  lea     rdx, BaseUnicodeCommandLine; SourceString
0x180064c8c  mov     rax, [rbx+20h]
0x180064c90  lea     rcx, BaseAnsiCommandLine; DestinationString
0x180064c97  mov     r8b, 1; AllocateDestinationString
0x180064c9a  movups  xmm0, xmmword ptr [rax+70h]
0x180064c9e  movdqu  xmmword ptr cs:BaseUnicodeCommandLine.Length, xmm0
0x180064ca6  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180064cad  nop     dword ptr [rax+rax+00h]
0x180064cb2  test    eax, eax
0x180064cb4  js      loc_180064EE3
0x180064cba  lea     rcx, UnhandledExceptionFilter; TopLevelExceptionFilter
0x180064cc1  call    cs:__imp_RtlSetUnhandledExceptionFilter
0x180064cc8  nop     dword ptr [rax+rax+00h]
0x180064ccd  xor     ecx, ecx; Pointer
0x180064ccf  call    cs:__imp_RtlEncodePointer
0x180064cd6  nop     dword ptr [rax+rax+00h]
0x180064cdb  mov     r8, cs:BaseStaticServerData
0x180064ce2  mov     ecx, 190h
0x180064ce7  mov     edx, 1
0x180064cec  mov     cs:BasepInitializationStage, cx
0x180064cf3  mov     cs:BasepCurrentTopLevelFilter, rax
0x180064cfa  call    BaseNlsDllInitialize
0x180064cff  test    al, al
0x180064d01  jz      loc_180064E7B
0x180064d07  mov     ecx, 1F4h
0x180064d0c  mov     cs:BasepInitializationStage, cx
0x180064d13  lea     rcx, stru_1803AADF0; CriticalSection
0x180064d1a  call    cs:__imp_RtlInitializeCriticalSection
0x180064d21  nop     dword ptr [rax+rax+00h]
0x180064d26  test    eax, eax
0x180064d28  js      loc_180064E7B
0x180064d2e  mov     ecx, 258h
0x180064d33  mov     cs:BasepInitializationStage, cx
0x180064d3a  call    ConsoleInitialize
0x180064d3f  test    al, al
0x180064d41  jz      loc_180064A3F
0x180064d47  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180064d4c  mov     cs:BasepDiscountProcessFreezeTimeFromUnbiasedTime, r15b
0x180064d53  call    Feature_DiscountProcessFreezeTimeFromUnbiasedInterruptTimePrecise__private_IsEnabledDeviceUsageNoInline
0x180064d58  test    eax, eax
0x180064d5a  jz      short loc_180064D63
0x180064d5c  mov     cs:BasepDiscountProcessFreezeTimeFromUnbiasedTime, 1
0x180064d63  mov     eax, 2BCh
0x180064d68  mov     cs:BasepInitializationStage, ax
0x180064d6f  jmp     loc_180064A34
0x180064d74  cmp     cs:ConsoleIsConsoleApplication, r15b
0x180064d7b  jz      loc_180064A34
0x180064d81  call    SetTEBLangID
0x180064d86  jmp     loc_180064A34
0x180064d8b  mov     rax, gs:60h
0x180064d94  mov     rcx, [rax+98h]
0x180064d9b  mov     rax, gs:60h
0x180064da4  mov     r8, [rcx+8]
0x180064da8  sub     r8, [rax+380h]
0x180064daf  mov     rax, gs:60h
0x180064db8  mov     rdx, [rax+88h]
0x180064dbf  mov     rax, gs:60h
0x180064dc8  mov     rcx, [rax+98h]
0x180064dcf  mov     rax, gs:60h
0x180064dd8  mov     rcx, [rcx+8]
0x180064ddc  sub     rcx, [r8+rdx+9E8h]
0x180064de4  sub     rcx, [rax+380h]
0x180064deb  mov     rax, gs:60h
0x180064df4  add     rcx, [rax+88h]
0x180064dfb  add     rcx, r10
0x180064dfe  jmp     loc_180064C55
0x180064e03  mov     rax, gs:60h
0x180064e0c  mov     rcx, [rax+98h]
0x180064e13  mov     rax, gs:60h
0x180064e1c  mov     r8, [rcx+8]
0x180064e20  sub     r8, [rax+380h]
0x180064e27  mov     rax, gs:60h
0x180064e30  mov     rdx, [rax+88h]
0x180064e37  mov     rax, gs:60h
0x180064e40  mov     rcx, [rax+98h]
0x180064e47  mov     rax, gs:60h
0x180064e50  mov     rcx, [rcx+8]
0x180064e54  sub     rcx, [r8+rdx+9E8h]
0x180064e5c  sub     rcx, [rax+380h]
0x180064e63  mov     rax, gs:60h
0x180064e6c  add     rcx, [rax+88h]
0x180064e73  add     rcx, r10
0x180064e76  jmp     loc_180064C7E
0x180064e7b  mov     al, r15b
0x180064e7e  jmp     loc_180064A3F
0x180064e83  mov     r8, gs:30h
0x180064e8c  xor     edx, edx; Flags
0x180064e8e  mov     rcx, gs:60h
0x180064e97  mov     r8, [r8+1768h]; P
0x180064e9e  mov     rcx, [rcx+30h]; HeapHandle
0x180064ea2  call    cs:__imp_RtlFreeHeap
0x180064ea9  nop     dword ptr [rax+rax+00h]
0x180064eae  jmp     loc_180064A81
0x180064eb3  mov     cs:BasepIsSecureProcess, 1
0x180064eba  jmp     loc_180064A9D
0x180064ebf  lea     r8, aWindows; "\\Windows"
0x180064ec6  call    StringCbCopyW
0x180064ecb  jmp     loc_180064B18
0x180064ed0  call    CsrpLocalSetupForSecureProcess
0x180064ed5  test    eax, eax
0x180064ed7  js      short loc_180064E7B
0x180064ed9  mov     [rsp+280h+var_250], r15b
0x180064ede  jmp     loc_180064BD5
0x180064ee3  mov     cs:BaseAnsiCommandLine.Buffer, r15
0x180064eea  mov     dword ptr cs:BaseAnsiCommandLine.Length, r15d
0x180064ef1  jmp     loc_180064CBA
0x180064ef6  call    TraceLoggingUnregister_EtwEventUnregister
0x180064efb  test    rsi, rsi
0x180064efe  jnz     loc_18019B592
0x180064f04  movzx   eax, cs:BasepInitializationStage
0x180064f0b  mov     ecx, 258h
0x180064f10  cmp     ax, cx
0x180064f13  jbe     loc_18019B54C
0x180064f19  lea     rcx, ConsoleConnectionState
0x180064f20  call    ConsoleCleanupConnectionState
0x180064f25  lea     rcx, ConsoleStateLock; CriticalSection
0x180064f2c  call    cs:__imp_RtlDeleteCriticalSection
0x180064f33  nop     dword ptr [rax+rax+00h]
0x180064f38  movzx   eax, cs:BasepInitializationStage
0x180064f3f  jmp     loc_18019B54C
0x18019b54c  mov     ecx, 1F4h
0x18019b551  cmp     ax, cx
0x18019b554  jbe     short loc_18019B562
0x18019b556  call    BasepUnInitComputerNameCache
0x18019b55b  movzx   eax, cs:BasepInitializationStage
0x18019b562  mov     ecx, 190h
0x18019b567  cmp     ax, cx
0x18019b56a  jbe     short loc_18019B576
0x18019b56c  xor     r8d, r8d
0x18019b56f  xor     edx, edx
0x18019b571  call    BaseNlsDllInitialize
0x18019b576  cmp     cs:BaseAnsiCommandLine.Buffer, r15
0x18019b57d  jz      short loc_18019B592
0x18019b57f  lea     rcx, BaseAnsiCommandLine; AnsiString
0x18019b586  call    cs:__imp_RtlFreeAnsiString
0x18019b58d  nop     dword ptr [rax+rax+00h]
0x18019b592  cmp     cs:BasepFilterInfo, r15
0x18019b599  jz      short loc_18019B5BD
0x18019b59b  mov     rcx, gs:60h
0x18019b5a4  xor     edx, edx; Flags
0x18019b5a6  mov     r8, cs:BasepFilterInfo; P
0x18019b5ad  mov     rcx, [rcx+30h]; HeapHandle
0x18019b5b1  call    cs:__imp_RtlFreeHeap
0x18019b5b8  nop     dword ptr [rax+rax+00h]
0x18019b5bd  lea     rax, LoadLibraryA
0x18019b5c4  mov     [rsp+280h+ConnectionInfo], rax
0x18019b5c9  lea     rax, LoadLibraryW
0x18019b5d0  mov     [rsp+280h+ConnectionInfo], rax
0x18019b5d5  lea     rax, LoadLibraryExA
0x18019b5dc  mov     [rsp+280h+ConnectionInfo], rax
0x18019b5e1  lea     rax, LoadLibraryExW
0x18019b5e8  mov     [rsp+280h+ConnectionInfo], rax
0x18019b5ed  jmp     loc_180064A34
```
