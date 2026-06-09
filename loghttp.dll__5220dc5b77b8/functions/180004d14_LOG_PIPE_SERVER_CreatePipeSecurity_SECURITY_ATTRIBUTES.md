# LOG_PIPE_SERVER::CreatePipeSecurity(_SECURITY_ATTRIBUTES * *)

- ea: `0x180004d14`
- end: `0x180004f3a`
- name: `?CreatePipeSecurity@LOG_PIPE_SERVER@@AEAAJPEAPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(LOG_PIPE_SERVER *__hidden this, struct _SECURITY_ATTRIBUTES **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800051c8`

## callees

- `0x180004d14`
- `0x1800056f2`
- `0x180005720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004da9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004d9f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180004d9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004d8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004d8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004dea`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180004dea`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180004e58`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180004e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004eac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004efa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004e6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ec5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ec5`
- `iisutil!FreeTokenUserSID` at `0x180004ee1`
- `iisutil!FreeTokenUserSID` at `0x180004ee1`
- `iisutil!GetTokenUserSID` at `0x180004dd1`
- `iisutil!GetTokenUserSID` at `0x180004dd1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e1a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e32`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e1a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e32`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004e00`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004e00`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f0e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004f0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e43`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e43`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004d86`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004d86`

## pseudocode

```c
__int64 __fastcall LOG_PIPE_SERVER::CreatePipeSecurity(LOG_PIPE_SERVER *this, struct _SECURITY_ATTRIBUTES **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v5; // ebx
  bool v6; // cc
  const WCHAR *Str; // rax
  struct _SECURITY_ATTRIBUTES *v8; // rax
  struct _TOKEN_USER *v10; // [rsp+20h] [rbp-E0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-D8h] BYREF
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[256]; // [rsp+80h] [rbp-80h] BYREF

  SecurityDescriptor = 0;
  StringSid = 0;
  TokenHandle = 0;
  v10 = 0;
  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v14, v15, 0x100u);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x80000000, &TokenHandle) )
  {
LABEL_2:
    LastError = GetLastError();
    v5 = LastError;
    v6 = LastError <= 0;
    goto LABEL_3;
  }
  LastError = GetTokenUserSID(TokenHandle, &v10);
  v5 = LastError;
  v6 = LastError <= 0;
  if ( !LastError )
  {
    if ( ConvertSidToStringSidW(v10->User.Sid, &StringSid) )
    {
      v5 = STRU::Copy((STRU *)v14, L"D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;");
      if ( v5 < 0 )
        goto LABEL_13;
      v5 = STRU::Append((STRU *)v14, StringSid);
      if ( v5 < 0 )
        goto LABEL_13;
      v5 = STRU::Append((STRU *)v14, L")");
      if ( v5 < 0 )
        goto LABEL_13;
      Str = STRU::QueryStr((STRU *)v14);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(Str, 1u, &SecurityDescriptor, 0) )
      {
        v8 = (struct _SECURITY_ATTRIBUTES *)LocalAlloc(0x40u, 0x18u);
        if ( v8 )
        {
          v8->nLength = 24;
          v8->lpSecurityDescriptor = SecurityDescriptor;
          v8->bInheritHandle = 0;
          *a2 = v8;
          SecurityDescriptor = 0;
          goto LABEL_13;
        }
      }
    }
    goto LABEL_2;
  }
LABEL_3:
  if ( !v6 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v10 )
  {
    FreeTokenUserSID(&v10);
    v10 = 0;
  }
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  STRU::~STRU((STRU *)v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004d14  mov     [rsp-8+arg_0], rbx
0x180004d19  mov     [rsp-8+arg_10], rdi
0x180004d1e  push    rbp
0x180004d1f  lea     rbp, [rsp-190h]
0x180004d27  sub     rsp, 290h
0x180004d2e  mov     rax, cs:__security_cookie
0x180004d35  xor     rax, rsp
0x180004d38  mov     [rbp+190h+var_10], rax
0x180004d3f  mov     rdi, rdx
0x180004d42  mov     [rsp+290h+SecurityDescriptor], 0
0x180004d4b  xor     edx, edx; Val
0x180004d4d  mov     [rsp+290h+StringSid], 0
0x180004d56  mov     r8d, 200h; Size
0x180004d5c  mov     [rsp+290h+TokenHandle], 0
0x180004d65  lea     rcx, [rbp+190h+var_210]; void *
0x180004d69  mov     [rsp+290h+var_270], 0
0x180004d72  call    memset_0
0x180004d77  mov     r8d, 100h
0x180004d7d  lea     rdx, [rbp+190h+var_210]
0x180004d81  lea     rcx, [rsp+290h+var_250]
0x180004d86  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004d8c  call    cs:__imp_GetCurrentProcess
0x180004d92  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180004d97  mov     edx, 80000000h; DesiredAccess
0x180004d9c  mov     rcx, rax; ProcessHandle
0x180004d9f  call    cs:__imp_OpenProcessToken
0x180004da5  test    eax, eax
0x180004da7  jnz     short loc_180004DC7
0x180004da9  call    cs:__imp_GetLastError
0x180004daf  mov     ebx, eax
0x180004db1  test    eax, eax
0x180004db3  jle     loc_180004EA2
0x180004db9  movzx   ebx, ax
0x180004dbc  or      ebx, 80070000h
0x180004dc2  jmp     loc_180004EA2
0x180004dc7  mov     rcx, [rsp+290h+TokenHandle]
0x180004dcc  lea     rdx, [rsp+290h+var_270]
0x180004dd1  call    cs:__imp_?GetTokenUserSID@@YAKPEAXPEAPEAU_TOKEN_USER@@@Z; GetTokenUserSID(void *,_TOKEN_USER * *)
0x180004dd7  mov     ebx, eax
0x180004dd9  test    eax, eax
0x180004ddb  jnz     short loc_180004DB3
0x180004ddd  mov     rcx, [rsp+290h+var_270]
0x180004de2  lea     rdx, [rsp+290h+StringSid]; StringSid
0x180004de7  mov     rcx, [rcx]; Sid
0x180004dea  call    cs:__imp_ConvertSidToStringSidW
0x180004df0  test    eax, eax
0x180004df2  jz      short loc_180004DA9
0x180004df4  lea     rdx, aDPAOiciGaSyAOi; "D:P(A;OICI;GA;;;SY)(A;OICI;GA;;;"
0x180004dfb  lea     rcx, [rsp+290h+var_250]
0x180004e00  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004e06  mov     ebx, eax
0x180004e08  test    eax, eax
0x180004e0a  js      loc_180004EA2
0x180004e10  mov     rdx, [rsp+290h+StringSid]
0x180004e15  lea     rcx, [rsp+290h+var_250]
0x180004e1a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004e20  mov     ebx, eax
0x180004e22  test    eax, eax
0x180004e24  js      short loc_180004EA2
0x180004e26  lea     rdx, asc_1800084A4; ")"
0x180004e2d  lea     rcx, [rsp+290h+var_250]
0x180004e32  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004e38  mov     ebx, eax
0x180004e3a  test    eax, eax
0x180004e3c  js      short loc_180004EA2
0x180004e3e  lea     rcx, [rsp+290h+var_250]
0x180004e43  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004e49  xor     r9d, r9d; SecurityDescriptorSize
0x180004e4c  lea     r8, [rsp+290h+SecurityDescriptor]; SecurityDescriptor
0x180004e51  mov     rcx, rax; StringSecurityDescriptor
0x180004e54  lea     edx, [r9+1]; StringSDRevision
0x180004e58  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180004e5e  test    eax, eax
0x180004e60  jz      loc_180004DA9
0x180004e66  mov     edx, 18h; uBytes
0x180004e6b  lea     ecx, [rdx+28h]; uFlags
0x180004e6e  call    cs:__imp_LocalAlloc
0x180004e74  mov     rcx, rax
0x180004e77  test    rax, rax
0x180004e7a  jz      loc_180004DA9
0x180004e80  mov     dword ptr [rax], 18h
0x180004e86  mov     rax, [rsp+290h+SecurityDescriptor]
0x180004e8b  mov     [rcx+8], rax
0x180004e8f  mov     dword ptr [rcx+10h], 0
0x180004e96  mov     [rdi], rcx
0x180004e99  mov     [rsp+290h+SecurityDescriptor], 0
0x180004ea2  mov     rcx, [rsp+290h+StringSid]; hMem
0x180004ea7  test    rcx, rcx
0x180004eaa  jz      short loc_180004EBB
0x180004eac  call    cs:__imp_LocalFree
0x180004eb2  mov     [rsp+290h+StringSid], 0
0x180004ebb  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x180004ec0  test    rcx, rcx
0x180004ec3  jz      short loc_180004ED4
0x180004ec5  call    cs:__imp_CloseHandle
0x180004ecb  mov     [rsp+290h+TokenHandle], 0
0x180004ed4  cmp     [rsp+290h+var_270], 0
0x180004eda  jz      short loc_180004EF0
0x180004edc  lea     rcx, [rsp+290h+var_270]
0x180004ee1  call    cs:__imp_?FreeTokenUserSID@@YAXPEAPEAU_TOKEN_USER@@@Z; FreeTokenUserSID(_TOKEN_USER * *)
0x180004ee7  mov     [rsp+290h+var_270], 0
0x180004ef0  mov     rcx, [rsp+290h+SecurityDescriptor]; hMem
0x180004ef5  test    rcx, rcx
0x180004ef8  jz      short loc_180004F09
0x180004efa  call    cs:__imp_LocalFree
0x180004f00  mov     [rsp+290h+SecurityDescriptor], 0
0x180004f09  lea     rcx, [rsp+290h+var_250]
0x180004f0e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004f14  mov     eax, ebx
0x180004f16  mov     rcx, [rbp+190h+var_10]
0x180004f1d  xor     rcx, rsp; StackCookie
0x180004f20  call    __security_check_cookie
0x180004f25  lea     r11, [rsp+290h+var_s0]
0x180004f2d  mov     rbx, [r11+10h]
0x180004f31  mov     rdi, [r11+20h]
0x180004f35  mov     rsp, r11
0x180004f38  pop     rbp
0x180004f39  retn
```
