# CDataCollection::ChangeDebugPrivilege(ulong,ulong *)

- ea: `0x180007bdc`
- end: `0x180007db2`
- name: `?ChangeDebugPrivilege@CDataCollection@@AEAAJKPEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(CDataCollection *this, DWORD, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008030`
- `0x180008490`
- `0x180008970`

## callees

- `0x180002890`
- `0x180007704`
- `0x180007bdc`
- `0x180009f00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180007c1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180007c2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180007c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d95`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180007d39`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180007d39`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180007caf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180007caf`

## string_xrefs

- `0x180007c95`: `SeDebugPrivilege`

## pseudocode

```c
__int64 __fastcall CDataCollection::ChangeDebugPrivilege(CDataCollection *this, DWORD a2, unsigned int *a3)
{
  void **v5; // rbx
  HANDLE CurrentProcess; // rax
  signed int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  signed int v11; // eax
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-48h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-40h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-28h] BYREF

  TokenHandle = 0;
  if ( a3 )
    *a3 = 0;
  v5 = tlx::replace<tlx::file_handle_traits>(&TokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, v5) )
  {
    NewState = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a2;
    PreviousState = 0;
    if ( LookupPrivilegeValueW(0, L"SeDebugPrivilege", &NewState.Privileges[0].Luid) )
    {
      PreviousState.Privileges[0].Attributes = 0;
      PreviousState.Privileges[0].Luid = NewState.Privileges[0].Luid;
      PreviousState.PrivilegeCount = 1;
      ReturnLength = 0;
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength) )
      {
        if ( a3 )
          *a3 = PreviousState.Privileges[0].Attributes;
        v8 = 0;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 25;
          goto LABEL_9;
        }
      }
    }
    else
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 24;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 23;
LABEL_9:
      WPP_SF_d(v9[2], v10, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, v8);
    }
  }
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return v8;
}

```

## disassembly

```asm
0x180007bdc  push    rbp
0x180007bde  push    rbx
0x180007bdf  push    rsi
0x180007be0  push    rdi
0x180007be1  mov     rbp, rsp
0x180007be4  sub     rsp, 78h
0x180007be8  mov     rax, cs:__security_cookie
0x180007bef  xor     rax, rsp
0x180007bf2  mov     [rbp+var_18], rax
0x180007bf6  mov     [rbp+TokenHandle], 0
0x180007bfe  mov     rdi, r8
0x180007c01  mov     esi, edx
0x180007c03  test    r8, r8
0x180007c06  jz      short loc_180007C0F
0x180007c08  mov     dword ptr [r8], 0
0x180007c0f  lea     rcx, [rbp+TokenHandle]
0x180007c13  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180007c18  mov     rbx, rax
0x180007c1b  call    cs:__imp_GetCurrentProcess
0x180007c21  mov     r8, rbx; TokenHandle
0x180007c24  mov     edx, 28h ; '('; DesiredAccess
0x180007c29  mov     rcx, rax; ProcessHandle
0x180007c2c  call    cs:__imp_OpenProcessToken
0x180007c32  test    eax, eax
0x180007c34  jnz     short loc_180007C89
0x180007c36  call    cs:__imp_GetLastError
0x180007c3c  mov     ebx, eax
0x180007c3e  test    eax, eax
0x180007c40  jle     short loc_180007C4B
0x180007c42  movzx   ebx, ax
0x180007c45  or      ebx, 80070000h
0x180007c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c52  lea     rax, WPP_GLOBAL_Control
0x180007c59  cmp     rcx, rax
0x180007c5c  jz      loc_180007D87
0x180007c62  test    byte ptr [rcx+1Ch], 1
0x180007c66  jz      loc_180007D87
0x180007c6c  mov     edx, 17h
0x180007c71  mov     rcx, [rcx+10h]
0x180007c75  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180007c7c  mov     r9d, ebx
0x180007c7f  call    WPP_SF_d
0x180007c84  jmp     loc_180007D87
0x180007c89  xorps   xmm1, xmm1
0x180007c8c  lea     r8, [rbp+NewState.Privileges]; lpLuid
0x180007c90  movdqa  xmmword ptr [rbp-38h], xmm1
0x180007c95  lea     rdx, Name; "SeDebugPrivilege"
0x180007c9c  xorps   xmm0, xmm0
0x180007c9f  mov     [rbp+NewState.PrivilegeCount], 1
0x180007ca6  xor     ecx, ecx; lpSystemName
0x180007ca8  mov     [rbp+NewState.Privileges.Attributes], esi
0x180007cab  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x180007caf  call    cs:__imp_LookupPrivilegeValueW
0x180007cb5  test    eax, eax
0x180007cb7  jnz     short loc_180007CF9
0x180007cb9  call    cs:__imp_GetLastError
0x180007cbf  mov     ebx, eax
0x180007cc1  test    eax, eax
0x180007cc3  jle     short loc_180007CCE
0x180007cc5  movzx   ebx, ax
0x180007cc8  or      ebx, 80070000h
0x180007cce  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cd5  lea     rax, WPP_GLOBAL_Control
0x180007cdc  cmp     rcx, rax
0x180007cdf  jz      loc_180007D87
0x180007ce5  test    byte ptr [rcx+1Ch], 1
0x180007ce9  jz      loc_180007D87
0x180007cef  mov     edx, 18h
0x180007cf4  jmp     loc_180007C71
0x180007cf9  mov     rax, qword ptr [rbp+NewState.Privileges.Luid.LowPart]
0x180007cfd  lea     r8, [rbp+NewState]; NewState
0x180007d01  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180007d05  xorps   xmm0, xmm0
0x180007d08  movdqa  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x180007d0d  mov     r9d, 10h; BufferLength
0x180007d13  mov     qword ptr [rbp+var_28.Privileges.Luid.LowPart], rax
0x180007d17  xor     edx, edx; DisableAllPrivileges
0x180007d19  lea     rax, [rbp+var_48]
0x180007d1d  mov     [rbp+var_28.PrivilegeCount], 1
0x180007d24  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180007d29  lea     rax, [rbp+var_28]
0x180007d2d  mov     [rsp+78h+PreviousState], rax; PreviousState
0x180007d32  mov     [rbp+var_48], 0
0x180007d39  call    cs:__imp_AdjustTokenPrivileges
0x180007d3f  test    eax, eax
0x180007d41  jnz     short loc_180007D7B
0x180007d43  call    cs:__imp_GetLastError
0x180007d49  mov     ebx, eax
0x180007d4b  test    eax, eax
0x180007d4d  jle     short loc_180007D58
0x180007d4f  movzx   ebx, ax
0x180007d52  or      ebx, 80070000h
0x180007d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d5f  lea     rax, WPP_GLOBAL_Control
0x180007d66  cmp     rcx, rax
0x180007d69  jz      short loc_180007D87
0x180007d6b  test    byte ptr [rcx+1Ch], 1
0x180007d6f  jz      short loc_180007D87
0x180007d71  mov     edx, 19h
0x180007d76  jmp     loc_180007C71
0x180007d7b  test    rdi, rdi
0x180007d7e  jz      short loc_180007D85
0x180007d80  mov     eax, [rbp+var_28.Privileges.Attributes]
0x180007d83  mov     [rdi], eax
0x180007d85  xor     ebx, ebx
0x180007d87  mov     rcx, [rbp+TokenHandle]; hObject
0x180007d8b  lea     rdx, [rcx+1]
0x180007d8f  cmp     rdx, 1
0x180007d93  jbe     short loc_180007D9B
0x180007d95  call    cs:__imp_CloseHandle
0x180007d9b  mov     eax, ebx
0x180007d9d  mov     rcx, [rbp+var_18]
0x180007da1  xor     rcx, rsp; StackCookie
0x180007da4  call    __security_check_cookie
0x180007da9  add     rsp, 78h
0x180007dad  pop     rdi
0x180007dae  pop     rsi
0x180007daf  pop     rbx
0x180007db0  pop     rbp
0x180007db1  retn
```
