# StartW32Time(void)

- ea: `0x18001762c`
- end: `0x1800177cb`
- name: `?StartW32Time@@YAJXZ`
- size: `415`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800174e4`

## callees

- `0x180014660`
- `0x18001762c`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x1800176a4`
- `ADVAPI32!StartServiceW` at `0x1800176a4`
- `ADVAPI32!CloseServiceHandle` at `0x18001774a`
- `ADVAPI32!CloseServiceHandle` at `0x180017780`
- `ADVAPI32!CloseServiceHandle` at `0x18001774a`
- `ADVAPI32!CloseServiceHandle` at `0x180017780`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800176e9`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800176e9`
- `ADVAPI32!OpenServiceW` at `0x18001768a`
- `ADVAPI32!OpenServiceW` at `0x18001768a`
- `ADVAPI32!OpenSCManagerW` at `0x180017668`
- `ADVAPI32!OpenSCManagerW` at `0x180017668`
- `KERNEL32!Sleep` at `0x180017706`
- `KERNEL32!Sleep` at `0x180017706`
- `KERNEL32!GetLastError` at `0x1800176ae`
- `KERNEL32!GetLastError` at `0x1800176ae`

## string_xrefs

- `0x180017736`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x18001776c`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x1800177a2`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180017646`: `ServicesActive`

## pseudocode

```c
__int64 StartW32Time(void)
{
  SC_HANDLE v0; // rax
  const struct _EVENT_DESCRIPTOR *v1; // rdx
  CEventLogger *v2; // rcx
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  SC_HANDLE v7; // rsi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // r9d
  int v13; // edi
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-68h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-60h] BYREF
  __int128 v17; // [rsp+48h] [rbp-50h]
  int v18; // [rsp+58h] [rbp-40h]

  v18 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v17 = 0;
  v0 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v0;
  if ( v0 )
  {
    v4 = OpenServiceW(v0, L"w32time", 0x14u);
    v7 = v4;
    if ( v4 )
    {
      if ( StartServiceW(v4, 0, 0) )
      {
        v11 = 0;
        v13 = 0;
        while ( QueryServiceStatusEx(v7, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        {
          if ( *(_DWORD *)&Buffer[4] == 4 )
            goto LABEL_16;
          if ( *(_DWORD *)&Buffer[4] != 2 )
          {
            v11 = -2147467259;
            goto LABEL_16;
          }
          Sleep(0x1F4u);
          if ( (unsigned int)++v13 >= 0x3C )
            goto LABEL_16;
        }
        v11 = -2147467259;
        v12 = 641;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v12 = 623;
      }
      CEventLogger::LogError(v10, v9, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", v12, L"StartW32Time", 0);
LABEL_16:
      CloseServiceHandle(v7);
    }
    else
    {
      CEventLogger::LogError(v6, v5, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x26Au, L"StartW32Time", 0);
      v11 = -2147467259;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    CEventLogger::LogError(v2, v1, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x265u, L"StartW32Time", 0);
    return (unsigned int)-2147467259;
  }
  return v11;
}

```

## disassembly

```asm
0x18001762c  push    rbx
0x18001762e  push    rbp
0x18001762f  push    rsi
0x180017630  push    rdi
0x180017631  sub     rsp, 78h
0x180017635  mov     rax, cs:__security_cookie
0x18001763c  xor     rax, rsp
0x18001763f  mov     [rsp+98h+var_38], rax
0x180017644  xor     eax, eax
0x180017646  lea     rdx, DatabaseName; "ServicesActive"
0x18001764d  xorps   xmm0, xmm0
0x180017650  mov     [rsp+98h+var_40], eax
0x180017654  xor     ecx, ecx; lpMachineName
0x180017656  mov     [rsp+98h+var_68], eax
0x18001765a  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001765f  lea     r8d, [rax+1]; dwDesiredAccess
0x180017663  movups  [rsp+98h+var_50], xmm0
0x180017668  call    cs:__imp_OpenSCManagerW
0x18001766e  mov     rbp, rax
0x180017671  test    rax, rax
0x180017674  jz      loc_180017788
0x18001767a  mov     r8d, 14h; dwDesiredAccess
0x180017680  lea     rdx, ServiceName; "w32time"
0x180017687  mov     rcx, rax; hSCManager
0x18001768a  call    cs:__imp_OpenServiceW
0x180017690  mov     rsi, rax
0x180017693  test    rax, rax
0x180017696  jz      loc_180017752
0x18001769c  xor     r8d, r8d; lpServiceArgVectors
0x18001769f  xor     edx, edx; dwNumServiceArgs
0x1800176a1  mov     rcx, rax; hService
0x1800176a4  call    cs:__imp_StartServiceW
0x1800176aa  test    eax, eax
0x1800176ac  jnz     short loc_1800176CB
0x1800176ae  call    cs:__imp_GetLastError
0x1800176b4  mov     ebx, eax
0x1800176b6  test    eax, eax
0x1800176b8  jle     short loc_1800176C3
0x1800176ba  movzx   ebx, ax
0x1800176bd  or      ebx, 80070000h
0x1800176c3  mov     r9d, 26Fh
0x1800176c9  jmp     short loc_180017727
0x1800176cb  xor     ebx, ebx
0x1800176cd  xor     edi, edi
0x1800176cf  lea     rax, [rsp+98h+var_68]
0x1800176d4  mov     r9d, 24h ; '$'; cbBufSize
0x1800176da  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x1800176df  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800176e4  xor     edx, edx; InfoLevel
0x1800176e6  mov     rcx, rsi; hService
0x1800176e9  call    cs:__imp_QueryServiceStatusEx
0x1800176ef  test    eax, eax
0x1800176f1  jz      short loc_18001771C
0x1800176f3  cmp     dword ptr [rsp+98h+Buffer+4], 4
0x1800176f8  jz      short loc_180017747
0x1800176fa  cmp     dword ptr [rsp+98h+Buffer+4], 2
0x1800176ff  jnz     short loc_180017715
0x180017701  mov     ecx, 1F4h; dwMilliseconds
0x180017706  call    cs:__imp_Sleep
0x18001770c  inc     edi
0x18001770e  cmp     edi, 3Ch ; '<'
0x180017711  jb      short loc_1800176CF
0x180017713  jmp     short loc_180017747
0x180017715  mov     ebx, 80004005h
0x18001771a  jmp     short loc_180017747
0x18001771c  mov     ebx, 80004005h
0x180017721  mov     r9d, 281h; unsigned int
0x180017727  lea     rax, aStartw32time; "StartW32Time"
0x18001772e  mov     [rsp+98h+var_70], 0; unsigned int
0x180017736  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x18001773d  mov     [rsp+98h+pcbBytesNeeded], rax; unsigned __int16 *
0x180017742  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017747  mov     rcx, rsi; hSCObject
0x18001774a  call    cs:__imp_CloseServiceHandle
0x180017750  jmp     short loc_18001777D
0x180017752  lea     rax, aStartw32time; "StartW32Time"
0x180017759  mov     [rsp+98h+var_70], 0; unsigned int
0x180017761  mov     r9d, 26Ah; unsigned int
0x180017767  mov     [rsp+98h+pcbBytesNeeded], rax; unsigned __int16 *
0x18001776c  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180017773  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180017778  mov     ebx, 80004005h
0x18001777d  mov     rcx, rbp; hSCObject
0x180017780  call    cs:__imp_CloseServiceHandle
0x180017786  jmp     short loc_1800177B3
0x180017788  lea     rax, aStartw32time; "StartW32Time"
0x18001778f  mov     [rsp+98h+var_70], 0; unsigned int
0x180017797  mov     r9d, 265h; unsigned int
0x18001779d  mov     [rsp+98h+pcbBytesNeeded], rax; unsigned __int16 *
0x1800177a2  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800177a9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800177ae  mov     ebx, 80004005h
0x1800177b3  mov     eax, ebx
0x1800177b5  mov     rcx, [rsp+98h+var_38]
0x1800177ba  xor     rcx, rsp; StackCookie
0x1800177bd  call    __security_check_cookie
0x1800177c2  add     rsp, 78h
0x1800177c6  pop     rdi
0x1800177c7  pop     rsi
0x1800177c8  pop     rbp
0x1800177c9  pop     rbx
0x1800177ca  retn
```
