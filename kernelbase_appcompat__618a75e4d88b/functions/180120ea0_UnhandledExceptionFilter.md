# UnhandledExceptionFilter

- ea: `0x180120ea0`
- end: `0x18012149c`
- name: `UnhandledExceptionFilter`
- size: `1532`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x180107470`

## callees

- `0x18004cc30`
- `0x18004ce20`
- `0x18008c7f0`
- `0x18008c8cc`
- `0x18008d33c`
- `0x1800b8f50`
- `0x1800c1a90`
- `0x1800eddc8`
- `0x180103bb0`
- `0x18010d820`
- `0x180120ea0`
- `0x180130800`
- `0x180136930`
- `0x1801369c9`
- `0x180139760`
- `0x18018e670`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18012108e`
- `ntdll!RtlEqualUnicodeString` at `0x18012108e`
- `ntdll!NtSetInformationProcess` at `0x180120fd0`
- `ntdll!NtSetInformationProcess` at `0x180121147`
- `ntdll!NtSetInformationProcess` at `0x180120fd0`
- `ntdll!NtSetInformationProcess` at `0x180121147`
- `ntdll!NtTerminateProcess` at `0x180121468`
- `ntdll!NtTerminateProcess` at `0x180121468`
- `ntdll!RtlDecodePointer` at `0x180121005`
- `ntdll!RtlDecodePointer` at `0x180121005`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180120fe6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180120fe6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1801210a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180121108`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1801210a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180121108`
- `ntdll!RtlGetThreadErrorMode` at `0x18012116c`
- `ntdll!RtlGetThreadErrorMode` at `0x18012116c`
- `ntdll!NtRaiseHardError` at `0x1801213d9`
- `ntdll!NtRaiseHardError` at `0x1801213d9`
- `ntdll!RtlKnownExceptionFilter` at `0x180120fa2`
- `ntdll!RtlKnownExceptionFilter` at `0x180121117`
- `ntdll!RtlKnownExceptionFilter` at `0x180120fa2`
- `ntdll!RtlKnownExceptionFilter` at `0x180121117`
- `ntdll!NtQueryInformationJobObject` at `0x180121196`
- `ntdll!NtQueryInformationJobObject` at `0x180121196`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!BasepReportFault` at `0x18012120e`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!BasepReportFault` at `0x18012120e`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!CheckForReadOnlyResourceFilter` at `0x180120f75`
- `ext-ms-win-kernel32-errorhandling-l1-1-0!CheckForReadOnlyResourceFilter` at `0x180120f75`

## string_xrefs

- `0x1801211d5`: `ext-ms-win-kernel32-errorhandling-l1-1-0.dll`

## pseudocode

```c
LONG __stdcall UnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  struct _EXCEPTION_POINTERS *v3; // r12
  int v4; // eax
  __int64 (__fastcall *v5)(struct _EXCEPTION_POINTERS *); // rax
  __int64 (__fastcall *v6)(struct _EXCEPTION_POINTERS *); // rdi
  int v7; // eax
  LONG v8; // esi
  LONG result; // eax
  int v10; // r14d
  int v11; // edi
  HMODULE Library; // r12
  ULONG LastErrorValue; // ecx
  _WORD *v14; // rdi
  _DWORD *v15; // rax
  __int64 v16; // rcx
  NTSTATUS *ExceptionRecord; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rax
  ULONG v20; // eax
  int v21; // r14d
  ULONG Response; // [rsp+38h] [rbp-D0h] BYREF
  __int64 ProcessInformation; // [rsp+40h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-C0h]
  int v26; // [rsp+4Ch] [rbp-BCh]
  struct _EXCEPTION_POINTERS *v27; // [rsp+50h] [rbp-B8h]
  ULONG v28; // [rsp+60h] [rbp-A8h]
  ULONG v29; // [rsp+64h] [rbp-A4h]
  HMODULE v30; // [rsp+68h] [rbp-A0h]
  _BYTE JobInformation[16]; // [rsp+70h] [rbp-98h] BYREF
  int v32; // [rsp+80h] [rbp-88h]
  unsigned __int64 Parameters[4]; // [rsp+B0h] [rbp-58h] BYREF

  v27 = ExceptionInfo;
  v26 = 4;
  Response = 6;
  memset_0(JobInformation, 0, 0x40u);
  ProcessInformation = 0;
  if ( (ExceptionInfo->ExceptionRecord->ExceptionFlags & 0x10) != 0 )
    return 0;
  if ( ExceptionInfo->ExceptionRecord->ExceptionCode == -1073740791
    && ((unsigned int)BasepIsKernelDebuggerPresent() || (unsigned int)BasepIsDebugPortPresent()) )
  {
    DbgPrint_0("\r\nSTATUS_STACK_BUFFER_OVERRUN encountered\r\n");
    __debugbreak();
  }
  v3 = ExceptionInfo;
  if ( !(unsigned __int8)IsBasepReportFaultPresent() || BasepIsSecureProcess )
    v4 = 0;
  else
    v4 = CheckForReadOnlyResourceFilter(ExceptionInfo);
  if ( v4 == -1 )
    return -1;
  if ( (unsigned int)BasepIsDebugPortPresent() )
    return 0;
  if ( (unsigned int)RtlKnownExceptionFilter(ExceptionInfo) != -1 )
  {
    ProcessInformation = 8;
    NtSetInformationProcess(
      (HANDLE)0xFFFFFFFFFFFFFFFFLL,
      MaxProcessInfoClass|ProcessUserModeIOPL,
      &ProcessInformation,
      8u);
  }
  RtlAcquireSRWLockExclusive(&BasepUEFLock);
  if ( BasepIsSecureProcess
    || (v5 = (__int64 (__fastcall *)(struct _EXCEPTION_POINTERS *))RtlDecodePointer(BasepCurrentTopLevelFilter),
        (v6 = v5) == 0)
    || !(unsigned int)BasepFillUEFInfo(v5)
    || *(_QWORD *)BasepFilterInfo != *((_QWORD *)BasepFilterInfo + 71)
    || *((_QWORD *)BasepFilterInfo + 1) != *((_QWORD *)BasepFilterInfo + 72)
    || (v7 = *((_DWORD *)BasepFilterInfo + 4), v7 != *((_DWORD *)BasepFilterInfo + 146)) )
  {
    v8 = 1;
LABEL_28:
    RtlReleaseSRWLockExclusive(&BasepUEFLock);
    goto LABEL_29;
  }
  v8 = 1;
  if ( (v7 & 0x1040000) != 0
    && !RtlEqualUnicodeString(
          (PCUNICODE_STRING)((char *)BasepFilterInfo + 24),
          (PCUNICODE_STRING)BasepFilterInfo + 37,
          1u) )
  {
    goto LABEL_28;
  }
  RtlReleaseSRWLockExclusive(&BasepUEFLock);
  result = v6(ExceptionInfo);
  if ( ((result + 1) & 0xFFFFFFFD) == 0 )
    return result;
  if ( result || !(unsigned int)BasepIsDebugPortPresent() )
  {
LABEL_29:
    if ( (unsigned int)RtlKnownExceptionFilter(ExceptionInfo) != -1 )
    {
      ProcessInformation = 1;
      NtSetInformationProcess(
        (HANDLE)0xFFFFFFFFFFFFFFFFLL,
        MaxProcessInfoClass|ProcessUserModeIOPL,
        &ProcessInformation,
        8u);
      if ( BasepIsSecureProcess )
        return 0;
      if ( (GetErrorMode() & 2) != 0
        || (RtlGetThreadErrorMode() & 0x20) != 0
        || NtQueryInformationJobObject(0, JobObjectBasicLimitInformation, JobInformation, 0x40u, 0) >= 0
        && (v32 & 0x400) != 0 )
      {
        return v8;
      }
      v10 = 4;
      if ( (unsigned __int8)IsBasepReportFaultPresent() )
      {
        v11 = 0;
        v25 = 0;
        Library = LoadLibraryExW(L"ext-ms-win-kernel32-errorhandling-l1-1-0.dll", 0, 0);
        v30 = Library;
        LastErrorValue = 0;
        if ( !Library )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          v28 = LastErrorValue;
          v29 = LastErrorValue;
        }
        if ( !LastErrorValue || LastErrorValue == 126 )
        {
          v10 = BasepReportFault(ExceptionInfo, 1);
          v26 = v10;
          v11 = 1;
          v25 = 1;
        }
        if ( Library )
          FreeLibrary(Library);
        if ( (unsigned int)(v10 - 9) <= 1 || v10 == 3 || !v11 )
          RaiseFailFastException(ExceptionInfo->ExceptionRecord, ExceptionInfo->ContextRecord, 0);
        v3 = ExceptionInfo;
      }
      if ( v10 == 8 || v10 == 6 && (unsigned int)BasepIsDebugPortPresent() )
        return 0;
      v14 = 0;
      if ( v10 != 4 )
        goto LABEL_84;
      v15 = VirtualAllocExNuma((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x250u, 0x1000u, 4u, 0xFFFFFFFF);
      v14 = v15;
      if ( !v15 )
        return 0;
      *v15 &= ~1u;
      if ( (unsigned __int8)IsBasepReportFaultPresent() && ((int)WerpGetDebugger(v16, v14) < 0 || !v14[2]) )
        *(_DWORD *)v14 &= ~1u;
      if ( (*(_BYTE *)v14 & 2) != 0 )
      {
LABEL_74:
        if ( (*(_BYTE *)v14 & 1) != 0 && (Response == 3 || (*(_BYTE *)v14 & 2) != 0) )
        {
          if ( BasepAlreadyHadHardError )
          {
LABEL_85:
            NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3->ExceptionRecord->ExceptionCode);
LABEL_86:
            if ( v14 )
              VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v14, 0, 0x8000u);
            return v8;
          }
          if ( !byte_1803AAD44 )
          {
            v21 = -2147467259;
            if ( (unsigned __int8)IsBasepReportFaultPresent() )
              v21 = WerpLaunchAeDebug(
                      -1,
                      -2,
                      (__int64)v3->ExceptionRecord,
                      &ExceptionInfo->ContextRecord->P1Home,
                      (ULONG_PTR)v14);
            if ( v21 < 0 )
              BasepAlreadyHadHardError = 1;
            v8 = 0;
            goto LABEL_86;
          }
        }
LABEL_84:
        if ( !BasepAlreadyHadHardError )
          goto LABEL_86;
        goto LABEL_85;
      }
      ExceptionRecord = (NTSTATUS *)v3->ExceptionRecord;
      Parameters[0] = v3->ExceptionRecord->ExceptionCode;
      Parameters[1] = *((_QWORD *)ExceptionRecord + 2);
      if ( *ExceptionRecord == -1073741818 )
      {
        if ( (unsigned int)ExceptionRecord[6] >= 3 )
        {
          v18 = *((_QWORD *)ExceptionRecord + 6);
LABEL_64:
          Parameters[2] = v18;
          if ( (unsigned int)ExceptionRecord[6] < 2 )
            v19 = 0;
          else
            v19 = *((_QWORD *)ExceptionRecord + 5);
          Parameters[3] = v19;
          if ( (NtCurrentPeb()->NtGlobalFlag & 0x20000000) != 0 )
          {
            DbgPrint_0("\r\nUnhandled exception encountered\r\n");
            __debugbreak();
          }
          if ( (*(_BYTE *)v14 & 1) == 0 || (v20 = 2, BasepAlreadyHadHardError) )
            v20 = 1;
          if ( (NtRaiseHardError(-805306044, 4u, 0, Parameters, v20, &Response) & 0xC0000000) == 0xC0000000 )
            Response = 6;
          goto LABEL_74;
        }
      }
      else if ( ExceptionRecord[6] )
      {
        v18 = *((_QWORD *)ExceptionRecord + 4);
        goto LABEL_64;
      }
      v18 = 0;
      goto LABEL_64;
    }
    return -1;
  }
  return 0;
}

```

## disassembly

```asm
0x180120ea0  mov     [rsp+arg_8], rbx
0x180120ea5  mov     [rsp+arg_10], rsi
0x180120eaa  push    rdi
0x180120eab  push    r12
0x180120ead  push    r13
0x180120eaf  push    r14
0x180120eb1  push    r15
0x180120eb3  sub     rsp, 0E0h
0x180120eba  mov     rax, cs:__security_cookie
0x180120ec1  xor     rax, rsp
0x180120ec4  mov     [rsp+108h+var_38], rax
0x180120ecc  mov     rdi, rcx
0x180120ecf  mov     [rsp+108h+var_D8], rcx
0x180120ed4  mov     r13, rcx
0x180120ed7  mov     [rsp+108h+var_B8], rcx
0x180120edc  mov     [rsp+108h+var_BC], 4
0x180120ee4  mov     [rsp+108h+Response], 6
0x180120eec  xor     edx, edx; Val
0x180120eee  lea     r8d, [rdx+40h]; Size
0x180120ef2  lea     rcx, [rsp+108h+JobInformation]; void *
0x180120ef7  call    memset_0
0x180120efc  xor     ebx, ebx
0x180120efe  mov     [rsp+108h+ProcessInformation], rbx
0x180120f03  mov     rax, [r13+0]
0x180120f07  test    byte ptr [rax+4], 10h
0x180120f0b  jnz     loc_1801210D0
0x180120f11  cmp     dword ptr [rax], 0C0000409h
0x180120f17  jnz     short loc_180120F5E
0x180120f19  call    BasepIsKernelDebuggerPresent
0x180120f1e  test    eax, eax
0x180120f20  jnz     short loc_180120F2B
0x180120f22  call    BasepIsDebugPortPresent
0x180120f27  test    eax, eax
0x180120f29  jz      short loc_180120F5E
0x180120f2b  lea     rcx, aStatusStackBuf; "\r\nSTATUS_STACK_BUFFER_OVERRUN encount"...
0x180120f32  call    DbgPrint_0
0x180120f37  int     3; Trap to Debugger
0x180120f38  mov     r12, [rsp+108h+var_D8]
0x180120f3d  jmp     short loc_180120F61
0x180120f3f  mov     edx, 0C0000409h; uExitCode
0x180120f44  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x180120f48  call    TerminateProcess
0x180120f4d  xor     ebx, ebx
0x180120f4f  mov     r13, [rsp+108h+var_B8]
0x180120f54  mov     r12, r13
0x180120f57  mov     [rsp+108h+var_D8], r13
0x180120f5c  jmp     short loc_180120F61
0x180120f5e  mov     r12, rdi
0x180120f61  call    IsBasepReportFaultPresent
0x180120f66  test    al, al
0x180120f68  jz      short loc_180120F83
0x180120f6a  cmp     cs:BasepIsSecureProcess, bl
0x180120f70  jnz     short loc_180120F83
0x180120f72  mov     rcx, r13
0x180120f75  call    cs:__imp_CheckForReadOnlyResourceFilter
0x180120f7c  nop     dword ptr [rax+rax+00h]
0x180120f81  jmp     short loc_180120F85
0x180120f83  mov     eax, ebx
0x180120f85  or      r15, 0FFFFFFFFFFFFFFFFh
0x180120f89  cmp     eax, r15d
0x180120f8c  jz      loc_180121494
0x180120f92  call    BasepIsDebugPortPresent
0x180120f97  test    eax, eax
0x180120f99  jnz     loc_1801210D0
0x180120f9f  mov     rcx, r13
0x180120fa2  call    cs:__imp_RtlKnownExceptionFilter
0x180120fa9  nop     dword ptr [rax+rax+00h]
0x180120fae  cmp     eax, r15d
0x180120fb1  jz      short loc_180120FDC
0x180120fb3  mov     [rsp+108h+ProcessInformation], rbx
0x180120fb8  mov     dword ptr [rsp+108h+ProcessInformation], 8
0x180120fc0  lea     r9d, [r15+9]; ProcessInformationLength
0x180120fc4  lea     r8, [rsp+108h+ProcessInformation]; ProcessInformation
0x180120fc9  lea     edx, [r15+40h]; ProcessInformationClass
0x180120fcd  mov     rcx, r15; ProcessHandle
0x180120fd0  call    cs:__imp_NtSetInformationProcess
0x180120fd7  nop     dword ptr [rax+rax+00h]
0x180120fdc  lea     r14, BasepUEFLock
0x180120fe3  mov     rcx, r14
0x180120fe6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180120fed  nop     dword ptr [rax+rax+00h]
0x180120ff2  cmp     cs:BasepIsSecureProcess, bl
0x180120ff8  jnz     loc_180121100
0x180120ffe  mov     rcx, cs:BasepCurrentTopLevelFilter; Pointer
0x180121005  call    cs:__imp_RtlDecodePointer
0x18012100c  nop     dword ptr [rax+rax+00h]
0x180121011  mov     rdi, rax
0x180121014  test    rax, rax
0x180121017  jz      loc_180121100
0x18012101d  mov     rdx, cs:BasepFilterInfo
0x180121024  add     rdx, 238h
0x18012102b  mov     rcx, rax; Address
0x18012102e  call    BasepFillUEFInfo
0x180121033  test    eax, eax
0x180121035  jz      loc_180121100
0x18012103b  mov     r8, cs:BasepFilterInfo
0x180121042  mov     rcx, [r8+238h]
0x180121049  cmp     [r8], rcx
0x18012104c  jnz     loc_180121100
0x180121052  mov     rax, [r8+240h]
0x180121059  cmp     [r8+8], rax
0x18012105d  jnz     loc_180121100
0x180121063  mov     eax, [r8+10h]
0x180121067  cmp     eax, [r8+248h]
0x18012106e  jnz     loc_180121100
0x180121074  mov     esi, 1
0x180121079  test    eax, 1040000h
0x18012107e  jz      short loc_18012109E
0x180121080  lea     rdx, [r8+250h]; String2
0x180121087  lea     rcx, [r8+18h]; String1
0x18012108b  mov     r8b, sil; CaseInsensitive
0x18012108e  call    cs:__imp_RtlEqualUnicodeString
0x180121095  nop     dword ptr [rax+rax+00h]
0x18012109a  test    al, al
0x18012109c  jz      short loc_180121105
0x18012109e  mov     rcx, r14
0x1801210a1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1801210a8  nop     dword ptr [rax+rax+00h]
0x1801210ad  mov     rcx, r13
0x1801210b0  mov     rax, rdi
0x1801210b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801210b8  lea     ecx, [rax+1]
0x1801210bb  test    ecx, 0FFFFFFFDh
0x1801210c1  jz      short loc_1801210D2
0x1801210c3  test    eax, eax
0x1801210c5  jnz     short loc_180121114
0x1801210c7  call    BasepIsDebugPortPresent
0x1801210cc  test    eax, eax
0x1801210ce  jz      short loc_180121114
0x1801210d0  xor     eax, eax
0x1801210d2  mov     rcx, [rsp+108h+var_38]
0x1801210da  xor     rcx, rsp; StackCookie
0x1801210dd  call    __security_check_cookie
0x1801210e2  lea     r11, [rsp+108h+var_28]
0x1801210ea  mov     rbx, [r11+38h]
0x1801210ee  mov     rsi, [r11+40h]
0x1801210f2  mov     rsp, r11
0x1801210f5  pop     r15
0x1801210f7  pop     r14
0x1801210f9  pop     r13
0x1801210fb  pop     r12
0x1801210fd  pop     rdi
0x1801210fe  retn
0x180121100  mov     esi, 1
0x180121105  mov     rcx, r14
0x180121108  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18012110f  nop     dword ptr [rax+rax+00h]
0x180121114  mov     rcx, r13
0x180121117  call    cs:__imp_RtlKnownExceptionFilter
0x18012111e  nop     dword ptr [rax+rax+00h]
0x180121123  cmp     eax, r15d
0x180121126  jz      loc_180121494
0x18012112c  mov     [rsp+108h+ProcessInformation], rbx
0x180121131  mov     dword ptr [rsp+108h+ProcessInformation], esi
0x180121135  mov     r9d, 8; ProcessInformationLength
0x18012113b  lea     r8, [rsp+108h+ProcessInformation]; ProcessInformation
0x180121140  lea     edx, [r9+37h]; ProcessInformationClass
0x180121144  mov     rcx, r15; ProcessHandle
0x180121147  call    cs:__imp_NtSetInformationProcess
0x18012114e  nop     dword ptr [rax+rax+00h]
0x180121153  cmp     cs:BasepIsSecureProcess, bl
0x180121159  jnz     loc_1801210D0
0x18012115f  call    GetErrorMode
0x180121164  test    al, 2
0x180121166  jnz     loc_18012148D
0x18012116c  call    cs:__imp_RtlGetThreadErrorMode
0x180121173  nop     dword ptr [rax+rax+00h]
0x180121178  test    al, 20h
0x18012117a  jnz     loc_18012148D
0x180121180  mov     [rsp+108h+ReturnLength], rbx; ReturnLength
0x180121185  mov     r9d, 40h ; '@'; JobInformationLength
0x18012118b  lea     r8, [rsp+108h+JobInformation]; JobInformation
0x180121190  lea     edx, [r9-3Eh]; JobInformationClass
0x180121194  xor     ecx, ecx; JobHandle
0x180121196  call    cs:__imp_NtQueryInformationJobObject
0x18012119d  nop     dword ptr [rax+rax+00h]
0x1801211a2  test    eax, eax
0x1801211a4  js      short loc_1801211B7
0x1801211a6  test    [rsp+108h+var_88], 400h
0x1801211b1  jnz     loc_18012148D
0x1801211b7  mov     r14d, 4
0x1801211bd  call    IsBasepReportFaultPresent
0x1801211c2  test    al, al
0x1801211c4  jz      loc_18012127F
0x1801211ca  mov     edi, ebx
0x1801211cc  mov     [rsp+108h+var_C0], ebx
0x1801211d0  xor     r8d, r8d; dwFlags
0x1801211d3  xor     edx, edx; hFile
0x1801211d5  lea     rcx, aExtMsWinKernel_21; "ext-ms-win-kernel32-errorhandling-l1-1-"...
0x1801211dc  call    LoadLibraryExW
0x1801211e1  mov     r12, rax
0x1801211e4  mov     [rsp+108h+var_A0], rax
0x1801211e9  mov     ecx, ebx
0x1801211eb  test    rax, rax
0x1801211ee  jnz     short loc_180121200
0x1801211f0  mov     ecx, gs:68h
0x1801211f8  mov     [rsp+108h+var_A8], ecx
0x1801211fc  mov     [rsp+108h+var_A4], ecx
0x180121200  test    ecx, ecx
0x180121202  jz      short loc_180121209
0x180121204  cmp     ecx, 7Eh ; '~'
0x180121207  jnz     short loc_180121227
0x180121209  mov     edx, esi
0x18012120b  mov     rcx, r13
0x18012120e  call    cs:__imp_BasepReportFault
0x180121215  nop     dword ptr [rax+rax+00h]
0x18012121a  mov     r14d, eax
0x18012121d  mov     [rsp+108h+var_BC], eax
0x180121221  mov     edi, esi
0x180121223  mov     [rsp+108h+var_C0], esi
0x180121227  test    r12, r12
0x18012122a  jz      short loc_180121234
0x18012122c  mov     rcx, r12; hLibModule
0x18012122f  call    FreeLibrary
0x180121234  mov     rcx, [rsp+108h+var_D8]
0x180121239  jmp     short loc_180121259
0x18012123b  xor     ebx, ebx
0x18012123d  lea     r14d, [rbx+0Ah]
0x180121241  or      r15, 0FFFFFFFFFFFFFFFFh
0x180121245  lea     esi, [rbx+1]
0x180121248  mov     edi, [rsp+108h+var_C0]
0x18012124c  mov     r13, [rsp+108h+var_B8]
0x180121251  mov     rcx, r13
0x180121254  mov     [rsp+108h+var_D8], rcx
0x180121259  lea     eax, [r14-9]
0x18012125d  cmp     eax, esi
0x18012125f  jbe     short loc_18012126B
0x180121261  cmp     r14d, 3
0x180121265  jz      short loc_18012126B
0x180121267  test    edi, edi
0x180121269  jnz     short loc_18012127A
0x18012126b  xor     r8d, r8d; dwFlags
0x18012126e  mov     rdx, [r13+8]; pContextRecord
0x180121272  mov     rcx, [rcx]; pExceptionRecord
0x180121275  call    RaiseFailFastException
0x18012127a  mov     r12, [rsp+108h+var_D8]
0x18012127f  cmp     r14d, 8
0x180121283  jz      loc_1801210D0
0x180121289  cmp     r14d, 6
0x18012128d  jnz     short loc_18012129C
0x18012128f  call    BasepIsDebugPortPresent
0x180121294  test    eax, eax
0x180121296  jnz     loc_1801210D0
0x18012129c  mov     rdi, rbx
0x18012129f  cmp     r14d, 4
0x1801212a3  jnz     loc_180121457
0x1801212a9  mov     [rsp+108h+nndPreferred], 0FFFFFFFFh; nndPreferred
0x1801212b1  mov     dword ptr [rsp+108h+ReturnLength], r14d; flProtect
0x1801212b6  xor     edx, edx; lpAddress
0x1801212b8  mov     r9d, 1000h; flAllocationType
0x1801212be  mov     r8d, 250h; dwSize
0x1801212c4  mov     rcx, r15; hProcess
0x1801212c7  call    VirtualAllocExNuma
0x1801212cc  mov     rdi, rax
0x1801212cf  mov     [rsp+108h+var_D8], rax
0x1801212d4  test    rax, rax
0x1801212d7  jz      loc_1801210D0
0x1801212dd  mov     r14d, 0FFFFFFFEh
0x1801212e3  and     [rax], r14d
0x1801212e6  call    IsBasepReportFaultPresent
0x1801212eb  test    al, al
0x1801212ed  jz      short loc_180121304
0x1801212ef  mov     rdx, rdi
0x1801212f2  call    WerpGetDebugger
0x1801212f7  test    eax, eax
0x1801212f9  js      short loc_180121301
0x1801212fb  cmp     [rdi+4], bx
0x1801212ff  jnz     short loc_180121304
0x180121301  and     [rdi], r14d
0x180121304  test    byte ptr [rdi], 2
0x180121307  jnz     loc_1801213F8
0x18012130d  mov     rcx, [r12]
0x180121311  movsxd  rax, dword ptr [rcx]
0x180121314  mov     [rsp+108h+Parameters], rax
0x18012131c  mov     rax, [rcx+10h]
0x180121320  mov     [rsp+108h+var_50], rax
0x180121328  cmp     dword ptr [rcx], 0C0000006h
0x18012132e  jnz     short loc_18012133C
0x180121330  cmp     dword ptr [rcx+18h], 3
0x180121334  jb      short loc_180121347
0x180121336  mov     rax, [rcx+30h]
0x18012133a  jmp     short loc_18012134A
0x18012133c  cmp     [rcx+18h], esi
0x18012133f  jb      short loc_180121347
0x180121341  mov     rax, [rcx+20h]
0x180121345  jmp     short loc_18012134A
0x180121347  mov     rax, rbx
0x18012134a  mov     [rsp+108h+var_48], rax
0x180121352  cmp     dword ptr [rcx+18h], 2
0x180121356  jb      short loc_18012135E
0x180121358  mov     rax, [rcx+28h]
0x18012135c  jmp     short loc_180121361
0x18012135e  mov     rax, rbx
0x180121361  mov     [rsp+108h+var_40], rax
0x180121369  mov     rax, gs:60h
0x180121372  test    dword ptr [rax+0BCh], 20000000h
0x18012137c  jz      short loc_1801213A3
0x18012137e  lea     rcx, aUnhandledExcep; "\r\nUnhandled exception encountered\r\n"
0x180121385  call    DbgPrint_0
0x18012138a  int     3; Trap to Debugger
  ... truncated ...
```
