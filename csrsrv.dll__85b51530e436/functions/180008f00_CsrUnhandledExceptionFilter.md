# CsrUnhandledExceptionFilter

- ea: `0x180008f00`
- end: `0x180009096`
- name: `CsrUnhandledExceptionFilter`
- size: `406`
- prototype: `__int64 __fastcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180001540`
- `0x180002460`
- `0x180004a20`
- `0x1800097f0`

## callees

- `0x180008c50`
- `0x180008e2c`
- `0x180008f00`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180008f4c`
- `ntdll!NtQuerySystemInformation` at `0x180008f4c`
- `ntdll!RtlInitUnicodeString` at `0x180008fee`
- `ntdll!RtlInitUnicodeString` at `0x180008fee`
- `ntdll!NtRaiseHardError` at `0x180009044`
- `ntdll!NtRaiseHardError` at `0x180009044`
- `ntdll!RtlAdjustPrivilege` at `0x180008faf`
- `ntdll!RtlAdjustPrivilege` at `0x180008fcf`
- `ntdll!RtlAdjustPrivilege` at `0x180008faf`
- `ntdll!RtlAdjustPrivilege` at `0x180008fcf`
- `ntdll!RtlUnhandledExceptionFilter` at `0x180008f89`
- `ntdll!RtlUnhandledExceptionFilter` at `0x180008f89`
- `ntdll!NtTerminateProcess` at `0x180009066`
- `ntdll!NtTerminateProcess` at `0x180009066`

## pseudocode

```c
__int64 __fastcall CsrUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  PEXCEPTION_RECORD ExceptionRecord; // rcx
  unsigned __int8 OldValue[4]; // [rsp+30h] [rbp-50h] BYREF
  __int16 SystemInformation; // [rsp+34h] [rbp-4Ch] BYREF
  ULONG Response; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 Parameters[4]; // [rsp+50h] [rbp-30h] BYREF

  Response = 0;
  OldValue[0] = 0;
  SystemInformation = 0;
  DestinationString = 0;
  v2 = NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
  if ( *(_DWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 704LL) != ServiceSessionId )
  {
    v3 = 1;
    if ( v2 < 0 || !(_BYTE)SystemInformation )
    {
LABEL_8:
      CsrReportToWerSvc(ExceptionInfo);
      CsrFlushToBlackBoxRecorder();
      NtTerminateProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ExceptionInfo->ExceptionRecord->ExceptionCode);
      return v3;
    }
  }
  v3 = RtlUnhandledExceptionFilter(ExceptionInfo);
  if ( v3 != -1 )
  {
    if ( RtlAdjustPrivilege(0x13u, 1u, 1u, OldValue) == -1073741700 )
      RtlAdjustPrivilege(0x13u, 1u, 0, OldValue);
    CsrReportToWerSvc(ExceptionInfo);
    RtlInitUnicodeString(&DestinationString, L"Windows SubSystem");
    ExceptionRecord = ExceptionInfo->ExceptionRecord;
    Parameters[0] = (unsigned __int64)&DestinationString;
    Parameters[1] = (int)ExceptionRecord->ExceptionCode;
    Parameters[2] = (unsigned __int64)ExceptionRecord->ExceptionAddress;
    Parameters[3] = (unsigned __int64)ExceptionInfo->ContextRecord;
    CsrFlushToBlackBoxRecorder();
    NtRaiseHardError(-1073741286, 4u, 1u, Parameters, 6u, &Response);
    goto LABEL_8;
  }
  return v3;
}

```

## disassembly

```asm
0x180008f00  mov     [rsp-8+arg_8], rbx
0x180008f05  mov     [rsp-8+arg_10], rdi
0x180008f0a  push    rbp
0x180008f0b  mov     rbp, rsp
0x180008f0e  sub     rsp, 80h
0x180008f15  mov     rax, cs:__security_cookie
0x180008f1c  xor     rax, rsp
0x180008f1f  mov     [rbp+var_10], rax
0x180008f23  xor     eax, eax
0x180008f25  mov     [rbp+var_48], 0
0x180008f2c  mov     rdi, rcx
0x180008f2f  mov     [rbp+OldValue], 0
0x180008f33  xorps   xmm0, xmm0
0x180008f36  mov     [rbp+SystemInformation], ax
0x180008f3a  xor     r9d, r9d; ReturnLength
0x180008f3d  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180008f41  lea     r8d, [rax+2]; SystemInformationLength
0x180008f45  lea     ecx, [rax+23h]; SystemInformationClass
0x180008f48  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180008f4c  call    cs:__imp_NtQuerySystemInformation
0x180008f53  nop     dword ptr [rax+rax+00h]
0x180008f58  mov     rdx, gs:60h
0x180008f61  mov     ecx, cs:ServiceSessionId
0x180008f67  cmp     [rdx+2C0h], ecx
0x180008f6d  jz      short loc_180008F86
0x180008f6f  mov     ebx, 1
0x180008f74  test    eax, eax
0x180008f76  js      loc_180009050
0x180008f7c  cmp     byte ptr [rbp+SystemInformation], 0
0x180008f80  jz      loc_180009050
0x180008f86  mov     rcx, rdi; ExceptionInfo
0x180008f89  call    cs:__imp_RtlUnhandledExceptionFilter
0x180008f90  nop     dword ptr [rax+rax+00h]
0x180008f95  mov     ebx, eax
0x180008f97  cmp     eax, 0FFFFFFFFh
0x180008f9a  jz      loc_180009072
0x180008fa0  mov     r8b, 1; ForThread
0x180008fa3  lea     r9, [rbp+OldValue]; OldValue
0x180008fa7  mov     dl, r8b; NewValue
0x180008faa  mov     ecx, 13h; Privilege
0x180008faf  call    cs:__imp_RtlAdjustPrivilege
0x180008fb6  nop     dword ptr [rax+rax+00h]
0x180008fbb  cmp     eax, 0C000007Ch
0x180008fc0  jnz     short loc_180008FDB
0x180008fc2  xor     r8d, r8d; ForThread
0x180008fc5  lea     r9, [rbp+OldValue]; OldValue
0x180008fc9  mov     dl, 1; NewValue
0x180008fcb  lea     ecx, [r8+13h]; Privilege
0x180008fcf  call    cs:__imp_RtlAdjustPrivilege
0x180008fd6  nop     dword ptr [rax+rax+00h]
0x180008fdb  mov     rcx, rdi; Reserved6
0x180008fde  call    CsrReportToWerSvc
0x180008fe3  lea     rdx, aWindowsSubsyst; "Windows SubSystem"
0x180008fea  lea     rcx, [rbp+DestinationString]; DestinationString
0x180008fee  call    cs:__imp_RtlInitUnicodeString
0x180008ff5  nop     dword ptr [rax+rax+00h]
0x180008ffa  mov     rcx, [rdi]
0x180008ffd  lea     rax, [rbp+DestinationString]
0x180009001  mov     [rbp+Parameters], rax
0x180009005  movsxd  rax, dword ptr [rcx]
0x180009008  mov     [rbp+var_28], rax
0x18000900c  mov     rax, [rcx+10h]
0x180009010  mov     [rbp+var_20], rax
0x180009014  mov     rax, [rdi+8]
0x180009018  mov     [rbp+var_18], rax
0x18000901c  call    CsrFlushToBlackBoxRecorder
0x180009021  mov     edx, 4; NumberOfParameters
0x180009026  lea     rax, [rbp+var_48]
0x18000902a  mov     [rsp+80h+Response], rax; Response
0x18000902f  lea     r9, [rbp+Parameters]; Parameters
0x180009033  mov     ecx, 0C000021Ah; ErrorStatus
0x180009038  mov     [rsp+80h+ValidResponseOptions], 6; ValidResponseOptions
0x180009040  lea     r8d, [rdx-3]; UnicodeStringParameterMask
0x180009044  call    cs:__imp_NtRaiseHardError
0x18000904b  nop     dword ptr [rax+rax+00h]
0x180009050  mov     rcx, rdi; Reserved6
0x180009053  call    CsrReportToWerSvc
0x180009058  call    CsrFlushToBlackBoxRecorder
0x18000905d  mov     rdx, [rdi]
0x180009060  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180009064  mov     edx, [rdx]; ExitStatus
0x180009066  call    cs:__imp_NtTerminateProcess
0x18000906d  nop     dword ptr [rax+rax+00h]
0x180009072  mov     eax, ebx
0x180009074  mov     rcx, [rbp+var_10]
0x180009078  xor     rcx, rsp; StackCookie
0x18000907b  call    __security_check_cookie
0x180009080  lea     r11, [rsp+80h+var_s0]
0x180009088  mov     rbx, [r11+18h]
0x18000908c  mov     rdi, [r11+20h]
0x180009090  mov     rsp, r11
0x180009093  pop     rbp
0x180009094  retn
```
