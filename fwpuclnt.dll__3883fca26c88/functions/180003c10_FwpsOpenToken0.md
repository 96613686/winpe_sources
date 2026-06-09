# FwpsOpenToken0

- ea: `0x180003c10`
- end: `0x180003e60`
- name: `FwpsOpenToken0`
- size: `592`
- prototype: `DWORD __stdcall(HANDLE engineHandle, LUID modifiedId, DWORD desiredAccess, HANDLE *accessToken)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1800034e0`
- `0x180003c10`
- `0x180004540`
- `0x18000e898`
- `0x180012bd0`
- `0x18003b2c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180003d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e3d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003d56`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180003d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180003d97`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180003d97`
- `RPCRT4!NdrClientCall3` at `0x180003cc4`
- `RPCRT4!NdrClientCall3` at `0x180003d38`
- `RPCRT4!NdrClientCall3` at `0x180003cc4`
- `RPCRT4!NdrClientCall3` at `0x180003d38`

## string_xrefs

- `0x180003c64`: `FwpsOpenToken0`
- `0x180003e05`: `FwpsOpenToken0`
- `0x180003e34`: `FwppProxyOpenToken`
- `0x180003e1d`: `OpenProcess`

## pseudocode

```c
DWORD __stdcall FwpsOpenToken0(HANDLE engineHandle, LUID modifiedId, DWORD desiredAccess, HANDLE *accessToken)
{
  void *v7; // rcx
  __int64 v8; // rbx
  unsigned int Pointer; // eax
  HANDLE v11; // rdi
  HANDLE CurrentProcess; // rax
  __int64 LastError; // r8
  const char *v14; // rdx
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD dwProcessId; // [rsp+50h] [rbp-48h] BYREF
  __int64 v18; // [rsp+58h] [rbp-40h] BYREF
  HANDLE hSourceHandle; // [rsp+60h] [rbp-38h] BYREF

  dwProcessId = 0;
  hSourceHandle = 0;
  v18 = 0;
  if ( !engineHandle )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, desiredAccess, 0, (__int64)"FwpsOpenToken0", -2144206820);
    }
    if ( gWfpLogUserModeErrors && (byte_18007C665 & 1) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0sq_EtwEventWriteTransfer)(
        v7,
        modifiedId,
        "FwpsOpenToken0",
        2150760476LL);
    v8 = -2144206820;
    goto LABEL_8;
  }
  if ( !accessToken )
  {
    LastError = 2150760476LL;
    v14 = "FwpsOpenToken0";
LABEL_21:
    v8 = WfpReportSysErrorAsWinError(engineHandle, v14, LastError);
    goto LABEL_8;
  }
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                            0x97u,
                            0,
                            *(_QWORD *)engineHandle,
                            *((_QWORD *)engineHandle + 1),
                            modifiedId,
                            &dwProcessId,
                            &hSourceHandle,
                            &v18).Pointer;
  if ( Pointer )
  {
    LastError = Pointer;
    v14 = "FwppProxyOpenToken";
    goto LABEL_21;
  }
  v11 = OpenProcess(0x40u, 0, dwProcessId);
  if ( !v11 )
  {
    LastError = GetLastError();
    v14 = "OpenProcess";
    goto LABEL_21;
  }
  v8 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v11, hSourceHandle, CurrentProcess, accessToken, desiredAccess, 0, 0) )
  {
    v15 = GetLastError();
    v8 = WfpReportSysErrorAsWinError(v16, "DuplicateHandle", v15);
  }
  CloseHandle(v11);
LABEL_8:
  if ( v18 )
    NdrClientCall3(
      (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
      0x98u,
      0,
      *(_QWORD *)engineHandle,
      *((_QWORD *)engineHandle + 1),
      &v18);
  return WfpErrorToFwpErr(v8);
}

```

## disassembly

```asm
0x180003c10  push    rbx
0x180003c12  push    rbp
0x180003c13  push    rsi
0x180003c14  push    rdi
0x180003c15  push    r14
0x180003c17  sub     rsp, 70h
0x180003c1b  mov     rax, cs:__security_cookie
0x180003c22  xor     rax, rsp
0x180003c25  mov     [rsp+98h+var_30], rax
0x180003c2a  mov     [rsp+98h+dwProcessId], 0
0x180003c32  mov     rbp, r9
0x180003c35  mov     [rsp+98h+hSourceHandle], 0
0x180003c3e  mov     r14d, r8d
0x180003c41  mov     [rsp+98h+var_40], 0
0x180003c4a  mov     rsi, rcx
0x180003c4d  test    rcx, rcx
0x180003c50  jnz     loc_180003CF1
0x180003c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c5d  lea     rax, WPP_GLOBAL_Control
0x180003c64  lea     rbx, aFwpsopentoken0_0; "FwpsOpenToken0"
0x180003c6b  cmp     rcx, rax
0x180003c6e  jz      short loc_180003C7A
0x180003c70  cmp     byte ptr [rcx+19h], 2
0x180003c74  jnb     loc_180003DBF
0x180003c7a  cmp     cs:gWfpLogUserModeErrors, 0
0x180003c81  jz      short loc_180003C90
0x180003c83  test    cs:byte_18007C665, 1
0x180003c8a  jnz     loc_180003DEC
0x180003c90  mov     rbx, 0FFFFFFFF8032001Ch
0x180003c97  cmp     [rsp+98h+var_40], 0
0x180003c9d  jz      short loc_180003CD0
0x180003c9f  mov     r9, [rsi]
0x180003ca2  lea     rax, [rsp+98h+var_40]
0x180003ca7  mov     qword ptr [rsp+98h+bInheritHandle], rax
0x180003cac  lea     rcx, pProxyInfo; pProxyInfo
0x180003cb3  mov     rax, [rsi+8]
0x180003cb7  xor     r8d, r8d; pReturnValue
0x180003cba  mov     edx, 98h; nProcNum
0x180003cbf  mov     qword ptr [rsp+98h+dwDesiredAccess], rax
0x180003cc4  call    cs:__imp_NdrClientCall3
0x180003ccb  nop     dword ptr [rax+rax+00h]
0x180003cd0  mov     rcx, rbx
0x180003cd3  call    WfpErrorToFwpErr
0x180003cd8  mov     rcx, [rsp+98h+var_30]
0x180003cdd  xor     rcx, rsp; StackCookie
0x180003ce0  call    __security_check_cookie
0x180003ce5  add     rsp, 70h
0x180003ce9  pop     r14
0x180003ceb  pop     rdi
0x180003cec  pop     rsi
0x180003ced  pop     rbp
0x180003cee  pop     rbx
0x180003cef  retn
0x180003cf1  test    rbp, rbp
0x180003cf4  jz      loc_180003DFF
0x180003cfa  mov     r9, [rcx]
0x180003cfd  lea     rax, [rsp+98h+var_40]
0x180003d02  mov     [rsp+98h+var_58], rax
0x180003d07  xor     r8d, r8d; pReturnValue
0x180003d0a  lea     rax, [rsp+98h+hSourceHandle]
0x180003d0f  mov     [rsp+98h+var_60], rax
0x180003d14  lea     rax, [rsp+98h+dwProcessId]
0x180003d19  mov     qword ptr [rsp+98h+dwOptions], rax
0x180003d1e  mov     rax, [rcx+8]
0x180003d22  lea     rcx, pProxyInfo; pProxyInfo
0x180003d29  mov     qword ptr [rsp+98h+bInheritHandle], rdx
0x180003d2e  mov     edx, 97h; nProcNum
0x180003d33  mov     qword ptr [rsp+98h+dwDesiredAccess], rax
0x180003d38  call    cs:__imp_NdrClientCall3
0x180003d3f  nop     dword ptr [rax+rax+00h]
0x180003d44  test    eax, eax
0x180003d46  jnz     loc_180003E31
0x180003d4c  mov     r8d, [rsp+98h+dwProcessId]; dwProcessId
0x180003d51  lea     ecx, [rax+40h]; dwDesiredAccess
0x180003d54  xor     edx, edx; bInheritHandle
0x180003d56  call    cs:__imp_OpenProcess
0x180003d5d  nop     dword ptr [rax+rax+00h]
0x180003d62  mov     rdi, rax
0x180003d65  test    rax, rax
0x180003d68  jz      loc_180003E0E
0x180003d6e  xor     ebx, ebx
0x180003d70  call    cs:__imp_GetCurrentProcess
0x180003d77  nop     dword ptr [rax+rax+00h]
0x180003d7c  mov     rdx, [rsp+98h+hSourceHandle]; hSourceHandle
0x180003d81  mov     r9, rbp; lpTargetHandle
0x180003d84  mov     [rsp+98h+dwOptions], ebx; dwOptions
0x180003d88  mov     r8, rax; hTargetProcessHandle
0x180003d8b  mov     [rsp+98h+bInheritHandle], ebx; bInheritHandle
0x180003d8f  mov     rcx, rdi; hSourceProcessHandle
0x180003d92  mov     [rsp+98h+dwDesiredAccess], r14d; dwDesiredAccess
0x180003d97  call    cs:__imp_DuplicateHandle
0x180003d9e  nop     dword ptr [rax+rax+00h]
0x180003da3  test    eax, eax
0x180003da5  jz      loc_180003E3D
0x180003dab  mov     rcx, rdi; hObject
0x180003dae  call    cs:__imp_CloseHandle
0x180003db5  nop     dword ptr [rax+rax+00h]
0x180003dba  jmp     loc_180003C97
0x180003dbf  test    byte ptr [rcx+1Ch], 1
0x180003dc3  jz      loc_180003C7A
0x180003dc9  mov     rcx, [rcx+10h]
0x180003dcd  mov     edx, 17h
0x180003dd2  mov     [rsp+98h+bInheritHandle], 8032001Ch
0x180003dda  xor     r9d, r9d
0x180003ddd  mov     qword ptr [rsp+98h+dwDesiredAccess], rbx
0x180003de2  call    WPP_SF_Ssd
0x180003de7  jmp     loc_180003C7A
0x180003dec  mov     r9d, 8032001Ch
0x180003df2  mov     r8, rbx
0x180003df5  call    McTemplateU0sq_EtwEventWriteTransfer
0x180003dfa  jmp     loc_180003C90
0x180003dff  mov     r8d, 8032001Ch
0x180003e05  lea     rdx, aFwpsopentoken0_0; "FwpsOpenToken0"
0x180003e0c  jmp     short loc_180003E24
0x180003e0e  call    cs:__imp_GetLastError
0x180003e15  nop     dword ptr [rax+rax+00h]
0x180003e1a  mov     r8d, eax
0x180003e1d  lea     rdx, aOpenprocess; "OpenProcess"
0x180003e24  call    WfpReportSysErrorAsWinError
0x180003e29  mov     rbx, rax
0x180003e2c  jmp     loc_180003C97
0x180003e31  mov     r8d, eax
0x180003e34  lea     rdx, aFwppproxyopent; "FwppProxyOpenToken"
0x180003e3b  jmp     short loc_180003E24
0x180003e3d  call    cs:__imp_GetLastError
0x180003e44  nop     dword ptr [rax+rax+00h]
0x180003e49  mov     r8d, eax
0x180003e4c  lea     rdx, aDuplicatehandl; "DuplicateHandle"
0x180003e53  call    WfpReportSysErrorAsWinError
0x180003e58  mov     rbx, rax
0x180003e5b  jmp     loc_180003DAB
```
