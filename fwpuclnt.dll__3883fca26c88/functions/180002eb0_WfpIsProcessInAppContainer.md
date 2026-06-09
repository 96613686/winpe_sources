# WfpIsProcessInAppContainer

- ea: `0x180002eb0`
- end: `0x180003001`
- name: `WfpIsProcessInAppContainer`
- size: `337`
- prototype: `__int64 __fastcall(PVOID TokenInformation)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009340`

## callees

- `0x180002eb0`
- `0x1800034e0`
- `0x18000e898`
- `0x180011500`
- `0x180012bd0`
- `0x18003b2c8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180002f21`
- `ntdll!NtQueryInformationToken` at `0x180002f21`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002ef0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002ef0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002ed7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f3f`

## string_xrefs

- `0x180002fba`: `OpenProcessToken`
- `0x180002fd1`: `NtQueryInformationToken`

## pseudocode

```c
__int64 __fastcall WfpIsProcessInAppContainer(PVOID TokenInformation)
{
  __int64 v1; // rbx
  HANDLE CurrentProcess; // rax
  NTSTATUS v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // r8d
  void *v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // [rsp+28h] [rbp-30h]
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v4 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, TokenInformation, 4u, &ReturnLength);
    if ( v4 >= 0 )
      goto LABEL_3;
    v12 = WfpReportSysErrorAsNtStatus(v6, "NtQueryInformationToken", (unsigned int)v4);
  }
  else
  {
    LastError = GetLastError();
    v12 = WfpReportSysErrorAsWinError(v11, "OpenProcessToken", LastError);
  }
  v1 = v12;
LABEL_3:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = v1;
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v7, 0, (__int64)"WfpIsProcessInAppContainer", v13);
    }
    if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v9, v5, "WfpIsProcessInAppContainer", (unsigned int)v1);
  }
  return v1;
}

```

## disassembly

```asm
0x180002eb0  mov     [rsp+arg_8], rbx
0x180002eb5  push    rdi
0x180002eb6  sub     rsp, 50h
0x180002eba  mov     rax, cs:__security_cookie
0x180002ec1  xor     rax, rsp
0x180002ec4  mov     [rsp+58h+var_18], rax
0x180002ec9  xor     ebx, ebx
0x180002ecb  mov     rdi, rcx
0x180002ece  mov     [rsp+58h+TokenHandle], rbx
0x180002ed3  mov     [rsp+58h+var_20], ebx
0x180002ed7  call    cs:__imp_GetCurrentProcess
0x180002ede  nop     dword ptr [rax+rax+00h]
0x180002ee3  lea     r8, [rsp+58h+TokenHandle]; TokenHandle
0x180002ee8  mov     edx, 8; DesiredAccess
0x180002eed  mov     rcx, rax; ProcessHandle
0x180002ef0  call    cs:__imp_OpenProcessToken
0x180002ef7  nop     dword ptr [rax+rax+00h]
0x180002efc  test    eax, eax
0x180002efe  jz      loc_180002FAB
0x180002f04  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x180002f09  lea     rax, [rsp+58h+var_20]
0x180002f0e  mov     r9d, 4; TokenInformationLength
0x180002f14  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180002f19  mov     r8, rdi; TokenInformation
0x180002f1c  mov     edx, 1Dh; TokenInformationClass
0x180002f21  call    cs:__imp_NtQueryInformationToken
0x180002f28  nop     dword ptr [rax+rax+00h]
0x180002f2d  test    eax, eax
0x180002f2f  js      loc_180002FCE
0x180002f35  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180002f3a  test    rcx, rcx
0x180002f3d  jz      short loc_180002F4B
0x180002f3f  call    cs:__imp_CloseHandle
0x180002f46  nop     dword ptr [rax+rax+00h]
0x180002f4b  test    rbx, rbx
0x180002f4e  jnz     short loc_180002F6C
0x180002f50  mov     rax, rbx
0x180002f53  mov     rcx, [rsp+58h+var_18]
0x180002f58  xor     rcx, rsp; StackCookie
0x180002f5b  call    __security_check_cookie
0x180002f60  mov     rbx, [rsp+58h+arg_8]
0x180002f65  add     rsp, 50h
0x180002f69  pop     rdi
0x180002f6a  retn
0x180002f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f73  lea     rax, WPP_GLOBAL_Control
0x180002f7a  lea     rdi, aWfpisprocessin; "WfpIsProcessInAppContainer"
0x180002f81  cmp     rcx, rax
0x180002f84  jz      short loc_180002F8C
0x180002f86  cmp     byte ptr [rcx+19h], 2
0x180002f8a  jnb     short loc_180002FDF
0x180002f8c  cmp     cs:gWfpLogUserModeErrors, 0
0x180002f93  jz      short loc_180002F50
0x180002f95  test    cs:byte_18007C665, 1
0x180002f9c  jz      short loc_180002F50
0x180002f9e  mov     r9d, ebx
0x180002fa1  mov     r8, rdi
0x180002fa4  call    McTemplateU0sq_EtwEventWriteTransfer
0x180002fa9  jmp     short loc_180002F50
0x180002fab  call    cs:__imp_GetLastError
0x180002fb2  nop     dword ptr [rax+rax+00h]
0x180002fb7  mov     r8d, eax
0x180002fba  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x180002fc1  call    WfpReportSysErrorAsWinError
0x180002fc6  mov     rbx, rax
0x180002fc9  jmp     loc_180002F35
0x180002fce  mov     r8d, eax
0x180002fd1  lea     rdx, aNtqueryinforma; "NtQueryInformationToken"
0x180002fd8  call    WfpReportSysErrorAsNtStatus
0x180002fdd  jmp     short loc_180002FC6
0x180002fdf  test    byte ptr [rcx+1Ch], 1
0x180002fe3  jz      short loc_180002F8C
0x180002fe5  mov     rcx, [rcx+10h]
0x180002fe9  mov     edx, 1Ah
0x180002fee  mov     [rsp+58h+var_30], ebx
0x180002ff2  xor     r9d, r9d
0x180002ff5  mov     [rsp+58h+ReturnLength], rdi
0x180002ffa  call    WPP_SF_Ssd
0x180002fff  jmp     short loc_180002F8C
```
