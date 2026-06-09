# CCrashReport::EnableShutdownPrivilege(void)

- ea: `0x18000fdec`
- end: `0x18000ff84`
- name: `?EnableShutdownPrivilege@CCrashReport@@CAJXZ`
- size: `408`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ff8c`

## callees

- `0x180002890`
- `0x180007704`
- `0x180009f00`
- `0x18000fdec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fe1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fe1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fe30`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fe30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ff69`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ff00`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000ff00`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000fe88`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18000fe88`

## string_xrefs

- `0x18000fe81`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 CCrashReport::EnableShutdownPrivilege(void)
{
  void **v0; // rbx
  HANDLE CurrentProcess; // rax
  signed int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  signed int v6; // eax
  BOOL v7; // ebx
  signed int LastError; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  struct _LUID Luid[2]; // [rsp+38h] [rbp-20h] BYREF

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  v0 = tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, v0) )
  {
    if ( LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
    {
      Luid[0].LowPart = 1;
      Luid[1].HighPart = 2;
      v7 = AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
      LastError = GetLastError();
      if ( v7 )
      {
        v3 = 0;
        if ( !LastError )
          goto LABEL_22;
      }
      v3 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v5 = 38;
      goto LABEL_21;
    }
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 37;
      goto LABEL_21;
    }
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 36;
LABEL_21:
      WPP_SF_d(v4[2], v5, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, v3);
    }
  }
LABEL_22:
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18000fdec  push    rbx
0x18000fdee  sub     rsp, 50h
0x18000fdf2  mov     rax, cs:__security_cookie
0x18000fdf9  xor     rax, rsp
0x18000fdfc  mov     [rsp+58h+var_10], rax
0x18000fe01  xorps   xmm0, xmm0
0x18000fe04  mov     [rsp+58h+TokenHandle], 0
0x18000fe0d  lea     rcx, [rsp+58h+TokenHandle]
0x18000fe12  movups  xmmword ptr [rsp+58h+Luid.LowPart], xmm0
0x18000fe17  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000fe1c  mov     rbx, rax
0x18000fe1f  call    cs:__imp_GetCurrentProcess
0x18000fe25  mov     r8, rbx; TokenHandle
0x18000fe28  mov     edx, 28h ; '('; DesiredAccess
0x18000fe2d  mov     rcx, rax; ProcessHandle
0x18000fe30  call    cs:__imp_OpenProcessToken
0x18000fe36  test    eax, eax
0x18000fe38  jnz     short loc_18000FE7A
0x18000fe3a  call    cs:__imp_GetLastError
0x18000fe40  mov     ebx, eax
0x18000fe42  test    eax, eax
0x18000fe44  jle     short loc_18000FE4F
0x18000fe46  movzx   ebx, ax
0x18000fe49  or      ebx, 80070000h
0x18000fe4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe56  lea     rax, WPP_GLOBAL_Control
0x18000fe5d  cmp     rcx, rax
0x18000fe60  jz      loc_18000FF5A
0x18000fe66  test    byte ptr [rcx+1Ch], 1
0x18000fe6a  jz      loc_18000FF5A
0x18000fe70  mov     edx, 24h ; '$'
0x18000fe75  jmp     loc_18000FF47
0x18000fe7a  lea     r8, [rsp+58h+Luid.HighPart]; lpLuid
0x18000fe7f  xor     ecx, ecx; lpSystemName
0x18000fe81  lea     rdx, aSeshutdownpriv; "SeShutdownPrivilege"
0x18000fe88  call    cs:__imp_LookupPrivilegeValueW
0x18000fe8e  test    eax, eax
0x18000fe90  jnz     short loc_18000FECF
0x18000fe92  call    cs:__imp_GetLastError
0x18000fe98  mov     ebx, eax
0x18000fe9a  test    eax, eax
0x18000fe9c  jle     short loc_18000FEA7
0x18000fe9e  movzx   ebx, ax
0x18000fea1  or      ebx, 80070000h
0x18000fea7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feae  lea     rax, WPP_GLOBAL_Control
0x18000feb5  cmp     rcx, rax
0x18000feb8  jz      loc_18000FF5A
0x18000febe  test    byte ptr [rcx+1Ch], 1
0x18000fec2  jz      loc_18000FF5A
0x18000fec8  mov     edx, 25h ; '%'
0x18000fecd  jmp     short loc_18000FF47
0x18000fecf  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18000fed4  lea     r8, [rsp+58h+Luid]; NewState
0x18000fed9  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x18000fee2  xor     r9d, r9d; BufferLength
0x18000fee5  xor     edx, edx; DisableAllPrivileges
0x18000fee7  mov     [rsp+58h+PreviousState], 0; PreviousState
0x18000fef0  mov     [rsp+58h+Luid.LowPart], 1
0x18000fef8  mov     [rsp+58h+Luid.HighPart+8], 2
0x18000ff00  call    cs:__imp_AdjustTokenPrivileges
0x18000ff06  mov     ebx, eax
0x18000ff08  call    cs:__imp_GetLastError
0x18000ff0e  test    ebx, ebx
0x18000ff10  jz      short loc_18000FF18
0x18000ff12  xor     ebx, ebx
0x18000ff14  test    eax, eax
0x18000ff16  jz      short loc_18000FF5A
0x18000ff18  test    eax, eax
0x18000ff1a  jg      short loc_18000FF20
0x18000ff1c  mov     ebx, eax
0x18000ff1e  jmp     short loc_18000FF29
0x18000ff20  movzx   ebx, ax
0x18000ff23  or      ebx, 80070000h
0x18000ff29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff30  lea     rax, WPP_GLOBAL_Control
0x18000ff37  cmp     rcx, rax
0x18000ff3a  jz      short loc_18000FF5A
0x18000ff3c  test    byte ptr [rcx+1Ch], 1
0x18000ff40  jz      short loc_18000FF5A
0x18000ff42  mov     edx, 26h ; '&'
0x18000ff47  mov     rcx, [rcx+10h]
0x18000ff4b  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18000ff52  mov     r9d, ebx
0x18000ff55  call    WPP_SF_d
0x18000ff5a  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18000ff5f  lea     rdx, [rcx+1]
0x18000ff63  cmp     rdx, 1
0x18000ff67  jbe     short loc_18000FF6F
0x18000ff69  call    cs:__imp_CloseHandle
0x18000ff6f  mov     eax, ebx
0x18000ff71  mov     rcx, [rsp+58h+var_10]
0x18000ff76  xor     rcx, rsp; StackCookie
0x18000ff79  call    __security_check_cookie
0x18000ff7e  add     rsp, 50h
0x18000ff82  pop     rbx
0x18000ff83  retn
```
