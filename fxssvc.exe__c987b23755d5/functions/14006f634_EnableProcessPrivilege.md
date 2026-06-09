# EnableProcessPrivilege

- ea: `0x14006f634`
- end: `0x14006f800`
- name: `EnableProcessPrivilege`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1400480f0`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14006f634`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14006f713`
- `ADVAPI32!OpenProcessToken` at `0x14006f713`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14006f6ab`
- `ADVAPI32!LookupPrivilegeValueW` at `0x14006f6ab`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14006f75d`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14006f75d`
- `KERNEL32!GetLastError` at `0x14006f6b5`
- `KERNEL32!GetLastError` at `0x14006f71d`
- `KERNEL32!GetLastError` at `0x14006f767`
- `KERNEL32!GetLastError` at `0x14006f7c6`
- `KERNEL32!GetLastError` at `0x14006f6b5`
- `KERNEL32!GetLastError` at `0x14006f71d`
- `KERNEL32!GetLastError` at `0x14006f767`
- `KERNEL32!GetLastError` at `0x14006f7c6`
- `KERNEL32!CloseHandle` at `0x14006f7a4`
- `KERNEL32!CloseHandle` at `0x14006f7a4`
- `KERNEL32!GetCurrentProcess` at `0x14006f701`
- `KERNEL32!GetCurrentProcess` at `0x14006f701`

## string_xrefs

- `0x14006f6a4`: `SeAuditPrivilege`

## pseudocode

```c
__int64 EnableProcessPrivilege()
{
  DWORD LastError; // eax
  DWORD v1; // ebx
  CMapDeviceId *v2; // rcx
  __int64 v3; // rdx
  HANDLE CurrentProcess; // rax
  DWORD v5; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState = 0;
  Luid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
  }
  if ( LookupPrivilegeValueW(0, L"SeAuditPrivilege", &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = 2;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
    {
      v1 = 0;
      if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        LastError = GetLastError();
        v1 = LastError;
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v3 = 18;
          goto LABEL_20;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v3 = 17;
        goto LABEL_20;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v3 = 16;
LABEL_20:
      WPP_SF_d(*((_QWORD *)v2 + 2), v3, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
  }
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v5 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v5);
  }
  return v1;
}

```

## disassembly

```asm
0x14006f634  push    rbp
0x14006f636  push    rbx
0x14006f637  push    r14
0x14006f639  push    r15
0x14006f63b  mov     rbp, rsp
0x14006f63e  sub     rsp, 68h
0x14006f642  mov     rax, cs:__security_cookie
0x14006f649  xor     rax, rsp
0x14006f64c  mov     [rbp+var_18], rax
0x14006f650  xorps   xmm0, xmm0
0x14006f653  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x14006f65b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x14006f65f  mov     qword ptr [rbp+Luid.LowPart], 0
0x14006f667  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f66e  lea     r14, WPP_GLOBAL_Control
0x14006f675  lea     r15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006f67c  cmp     rcx, r14
0x14006f67f  jz      short loc_14006F69E
0x14006f681  test    byte ptr [rcx+1Ch], 2
0x14006f685  jz      short loc_14006F69E
0x14006f687  cmp     byte ptr [rcx+19h], 5
0x14006f68b  jb      short loc_14006F69E
0x14006f68d  mov     rcx, [rcx+10h]
0x14006f691  mov     edx, 0Fh
0x14006f696  mov     r8, r15
0x14006f699  call    WPP_SF_
0x14006f69e  lea     r8, [rbp+Luid]; lpLuid
0x14006f6a2  xor     ecx, ecx; lpSystemName
0x14006f6a4  lea     rdx, Name; "SeAuditPrivilege"
0x14006f6ab  call    cs:__imp_LookupPrivilegeValueW
0x14006f6b1  test    eax, eax
0x14006f6b3  jnz     short loc_14006F6EB
0x14006f6b5  call    cs:__imp_GetLastError
0x14006f6bb  mov     ebx, eax
0x14006f6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f6c4  cmp     rcx, r14
0x14006f6c7  jz      loc_14006F79B
0x14006f6cd  test    byte ptr [rcx+1Ch], 2
0x14006f6d1  jz      loc_14006F79B
0x14006f6d7  cmp     byte ptr [rcx+19h], 2
0x14006f6db  jb      loc_14006F79B
0x14006f6e1  mov     edx, 10h
0x14006f6e6  jmp     loc_14006F78C
0x14006f6eb  mov     rax, qword ptr [rbp+Luid.LowPart]
0x14006f6ef  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x14006f6f3  mov     [rbp+NewState.PrivilegeCount], 1
0x14006f6fa  mov     [rbp+NewState.Privileges.Attributes], 2
0x14006f701  call    cs:__imp_GetCurrentProcess
0x14006f707  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14006f70b  mov     edx, 20h ; ' '; DesiredAccess
0x14006f710  mov     rcx, rax; ProcessHandle
0x14006f713  call    cs:__imp_OpenProcessToken
0x14006f719  test    eax, eax
0x14006f71b  jnz     short loc_14006F744
0x14006f71d  call    cs:__imp_GetLastError
0x14006f723  mov     ebx, eax
0x14006f725  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f72c  cmp     rcx, r14
0x14006f72f  jz      short loc_14006F79B
0x14006f731  test    byte ptr [rcx+1Ch], 2
0x14006f735  jz      short loc_14006F79B
0x14006f737  cmp     byte ptr [rcx+19h], 2
0x14006f73b  jb      short loc_14006F79B
0x14006f73d  mov     edx, 11h
0x14006f742  jmp     short loc_14006F78C
0x14006f744  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14006f748  lea     r8, [rbp+NewState]; NewState
0x14006f74c  xor     ebx, ebx
0x14006f74e  xor     r9d, r9d; BufferLength
0x14006f751  mov     [rsp+68h+ReturnLength], rbx; ReturnLength
0x14006f756  xor     edx, edx; DisableAllPrivileges
0x14006f758  mov     [rsp+68h+PreviousState], rbx; PreviousState
0x14006f75d  call    cs:__imp_AdjustTokenPrivileges
0x14006f763  test    eax, eax
0x14006f765  jnz     short loc_14006F79B
0x14006f767  call    cs:__imp_GetLastError
0x14006f76d  mov     ebx, eax
0x14006f76f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f776  cmp     rcx, r14
0x14006f779  jz      short loc_14006F79B
0x14006f77b  test    byte ptr [rcx+1Ch], 2
0x14006f77f  jz      short loc_14006F79B
0x14006f781  cmp     byte ptr [rcx+19h], 2
0x14006f785  jb      short loc_14006F79B
0x14006f787  mov     edx, 12h
0x14006f78c  mov     rcx, [rcx+10h]
0x14006f790  mov     r9d, eax
0x14006f793  mov     r8, r15
0x14006f796  call    WPP_SF_d
0x14006f79b  mov     rcx, [rbp+TokenHandle]; hObject
0x14006f79f  test    rcx, rcx
0x14006f7a2  jz      short loc_14006F7E7
0x14006f7a4  call    cs:__imp_CloseHandle
0x14006f7aa  test    eax, eax
0x14006f7ac  jnz     short loc_14006F7E7
0x14006f7ae  mov     rax, cs:WPP_GLOBAL_Control
0x14006f7b5  cmp     rax, r14
0x14006f7b8  jz      short loc_14006F7E7
0x14006f7ba  test    byte ptr [rax+1Ch], 2
0x14006f7be  jz      short loc_14006F7E7
0x14006f7c0  cmp     byte ptr [rax+19h], 2
0x14006f7c4  jb      short loc_14006F7E7
0x14006f7c6  call    cs:__imp_GetLastError
0x14006f7cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f7d3  mov     edx, 13h
0x14006f7d8  mov     r9d, eax
0x14006f7db  mov     r8, r15
0x14006f7de  mov     rcx, [rcx+10h]
0x14006f7e2  call    WPP_SF_d
0x14006f7e7  mov     eax, ebx
0x14006f7e9  mov     rcx, [rbp+var_18]
0x14006f7ed  xor     rcx, rsp; StackCookie
0x14006f7f0  call    __security_check_cookie
0x14006f7f5  add     rsp, 68h
0x14006f7f9  pop     r15
0x14006f7fb  pop     r14
0x14006f7fd  pop     rbx
0x14006f7fe  pop     rbp
0x14006f7ff  retn
```
