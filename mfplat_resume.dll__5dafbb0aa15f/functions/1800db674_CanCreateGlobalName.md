# CanCreateGlobalName

- ea: `0x1800db674`
- end: `0x1800db916`
- name: `CanCreateGlobalName`
- size: `674`
- prototype: `__int64 __fastcall(LPBOOL pfResult)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a05fc`
- `0x1800e7960`

## callees

- `0x18002146c`
- `0x180024390`
- `0x1800db674`
- `0x1801200d0`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800db6c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800db6c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800db6d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800db6d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db789`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db8f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800db8f2`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800db834`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x1800db834`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800db77b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800db77b`

## string_xrefs

- `0x1800db8c5`: `CanCreateGlobalName`
- `0x1800db774`: `SeCreateGlobalPrivilege`

## pseudocode

```c
__int64 __fastcall CanCreateGlobalName(LPBOOL pfResult)
{
  signed int v1; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  CallStackTracing *v5; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  int v7; // r8d
  signed int v8; // eax
  CallStackTracing *v9; // rcx
  signed int v10; // eax
  CallStackTracing *v11; // rcx
  void *TokenHandle; // [rsp+20h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+28h] [rbp-28h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  v1 = 0;
  TokenHandle = 0;
  Luid = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( dword_1801FB630 != -1 )
  {
    *pfResult = dword_1801FB630;
    goto LABEL_40;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      v5 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v5 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v5 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( !v5->m_fEnabled )
        goto LABEL_37;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v5);
      if ( ThreadRelativeContext->m_result == v1 )
        goto LABEL_37;
      v7 = 43;
      goto LABEL_36;
    }
  }
  if ( !LookupPrivilegeValueW(0, L"SeCreateGlobalPrivilege", &Luid) )
  {
    v8 = GetLastError();
    v1 = v8;
    if ( v8 > 0 )
      v1 = (unsigned __int16)v8 | 0x80070000;
    if ( v1 < 0 )
    {
      v9 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v9 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( !v9->m_fEnabled )
        goto LABEL_37;
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v9);
      if ( ThreadRelativeContext->m_result == v1 )
        goto LABEL_37;
      v7 = 48;
      goto LABEL_36;
    }
  }
  RequiredPrivileges.Privilege[0].Luid = Luid;
  *(_QWORD *)&RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  if ( PrivilegeCheck(TokenHandle, &RequiredPrivileges, pfResult) )
    goto LABEL_39;
  v10 = GetLastError();
  v1 = v10;
  if ( v10 > 0 )
    v1 = (unsigned __int16)v10 | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_39:
    dword_1801FB630 = *pfResult;
    goto LABEL_40;
  }
  v11 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
    {
      v11 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &stru_1801F8A30;
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
  }
  if ( v11->m_fEnabled )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
    if ( ThreadRelativeContext->m_result != v1 )
    {
      v7 = 58;
LABEL_36:
      CallStackContext::TraceFailure(ThreadRelativeContext, "CanCreateGlobalName", v7, v1);
    }
  }
LABEL_37:
  if ( pfResult )
    *pfResult = 0;
LABEL_40:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800db674  mov     [rsp-8+arg_8], rbx
0x1800db679  mov     [rsp-8+arg_10], rdi
0x1800db67e  push    rbp
0x1800db67f  mov     rbp, rsp
0x1800db682  sub     rsp, 50h
0x1800db686  mov     rax, cs:__security_cookie
0x1800db68d  xor     rax, rsp
0x1800db690  mov     [rbp+var_8], rax
0x1800db694  xor     eax, eax
0x1800db696  xor     ebx, ebx
0x1800db698  mov     [rbp+RequiredPrivileges.Privilege.Attributes], eax
0x1800db69b  xorps   xmm0, xmm0
0x1800db69e  mov     eax, cs:dword_1801FB630
0x1800db6a4  mov     rdi, rcx
0x1800db6a7  mov     [rbp+TokenHandle], rbx
0x1800db6ab  mov     qword ptr [rbp+Luid.LowPart], rbx
0x1800db6af  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1800db6b3  cmp     eax, 0FFFFFFFFh
0x1800db6b6  jz      short loc_1800DB6C5
0x1800db6b8  mov     eax, cs:dword_1801FB630
0x1800db6be  mov     [rcx], eax
0x1800db6c0  jmp     loc_1800DB8E9
0x1800db6c5  call    cs:__imp_GetCurrentProcess
0x1800db6cb  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800db6cf  mov     edx, 8; DesiredAccess
0x1800db6d4  mov     rcx, rax; ProcessHandle
0x1800db6d7  call    cs:__imp_OpenProcessToken
0x1800db6dd  test    eax, eax
0x1800db6df  jnz     loc_1800DB76E
0x1800db6e5  call    cs:__imp_GetLastError
0x1800db6eb  mov     ebx, eax
0x1800db6ed  test    eax, eax
0x1800db6ef  jle     short loc_1800DB6FA
0x1800db6f1  movzx   ebx, ax
0x1800db6f4  or      ebx, 80070000h
0x1800db6fa  test    ebx, ebx
0x1800db6fc  jns     short loc_1800DB76E
0x1800db6fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db705  test    rcx, rcx
0x1800db708  jnz     short loc_1800DB748
0x1800db70a  mov     rax, cs:stru_1801FC290.__vftable
0x1800db711  lea     rcx, stru_1801FC290
0x1800db718  mov     edx, 7F0h
0x1800db71d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db724  mov     rax, [rax+8]
0x1800db728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db72d  test    eax, eax
0x1800db72f  jnz     short loc_1800DB741
0x1800db731  lea     rcx, stru_1801F8A30
0x1800db738  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db73f  jmp     short loc_1800DB748
0x1800db741  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800db748  cmp     byte ptr [rcx+8], 0
0x1800db74c  jz      loc_1800DB8D4
0x1800db752  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db757  cmp     [rax+7CCh], ebx
0x1800db75d  jz      loc_1800DB8D4
0x1800db763  mov     r8d, 2Bh ; '+'
0x1800db769  jmp     loc_1800DB8C2
0x1800db76e  lea     r8, [rbp+Luid]; lpLuid
0x1800db772  xor     ecx, ecx; lpSystemName
0x1800db774  lea     rdx, Name; "SeCreateGlobalPrivilege"
0x1800db77b  call    cs:__imp_LookupPrivilegeValueW
0x1800db781  test    eax, eax
0x1800db783  jnz     loc_1800DB812
0x1800db789  call    cs:__imp_GetLastError
0x1800db78f  mov     ebx, eax
0x1800db791  test    eax, eax
0x1800db793  jle     short loc_1800DB79E
0x1800db795  movzx   ebx, ax
0x1800db798  or      ebx, 80070000h
0x1800db79e  test    ebx, ebx
0x1800db7a0  jns     short loc_1800DB812
0x1800db7a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db7a9  test    rcx, rcx
0x1800db7ac  jnz     short loc_1800DB7EC
0x1800db7ae  mov     rax, cs:stru_1801FC290.__vftable
0x1800db7b5  lea     rcx, stru_1801FC290
0x1800db7bc  mov     edx, 7F0h
0x1800db7c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db7c8  mov     rax, [rax+8]
0x1800db7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db7d1  test    eax, eax
0x1800db7d3  jnz     short loc_1800DB7E5
0x1800db7d5  lea     rcx, stru_1801F8A30
0x1800db7dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db7e3  jmp     short loc_1800DB7EC
0x1800db7e5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800db7ec  cmp     byte ptr [rcx+8], 0
0x1800db7f0  jz      loc_1800DB8D4
0x1800db7f6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db7fb  cmp     [rax+7CCh], ebx
0x1800db801  jz      loc_1800DB8D4
0x1800db807  mov     r8d, 30h ; '0'
0x1800db80d  jmp     loc_1800DB8C2
0x1800db812  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800db816  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800db81a  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800db81e  mov     r8, rdi; pfResult
0x1800db821  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1800db825  mov     qword ptr [rbp+RequiredPrivileges.PrivilegeCount], 1
0x1800db82d  mov     [rbp+RequiredPrivileges.Privilege.Attributes], 0
0x1800db834  call    cs:__imp_PrivilegeCheck
0x1800db83a  test    eax, eax
0x1800db83c  jnz     loc_1800DB8E1
0x1800db842  call    cs:__imp_GetLastError
0x1800db848  mov     ebx, eax
0x1800db84a  test    eax, eax
0x1800db84c  jle     short loc_1800DB857
0x1800db84e  movzx   ebx, ax
0x1800db851  or      ebx, 80070000h
0x1800db857  test    ebx, ebx
0x1800db859  jns     loc_1800DB8E1
0x1800db85f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db866  test    rcx, rcx
0x1800db869  jnz     short loc_1800DB8A9
0x1800db86b  mov     rax, cs:stru_1801FC290.__vftable
0x1800db872  lea     rcx, stru_1801FC290
0x1800db879  mov     edx, 7F0h
0x1800db87e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db885  mov     rax, [rax+8]
0x1800db889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db88e  test    eax, eax
0x1800db890  jnz     short loc_1800DB8A2
0x1800db892  lea     rcx, stru_1801F8A30
0x1800db899  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800db8a0  jmp     short loc_1800DB8A9
0x1800db8a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800db8a9  cmp     byte ptr [rcx+8], 0
0x1800db8ad  jz      short loc_1800DB8D4
0x1800db8af  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800db8b4  cmp     [rax+7CCh], ebx
0x1800db8ba  jz      short loc_1800DB8D4
0x1800db8bc  mov     r8d, 3Ah ; ':'; int
0x1800db8c2  mov     r9d, ebx; int
0x1800db8c5  lea     rdx, aCancreategloba; "CanCreateGlobalName"
0x1800db8cc  mov     rcx, rax; this
0x1800db8cf  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800db8d4  test    rdi, rdi
0x1800db8d7  jz      short loc_1800DB8E9
0x1800db8d9  mov     dword ptr [rdi], 0
0x1800db8df  jmp     short loc_1800DB8E9
0x1800db8e1  mov     ecx, [rdi]
0x1800db8e3  mov     cs:dword_1801FB630, ecx
0x1800db8e9  mov     rcx, [rbp+TokenHandle]; hObject
0x1800db8ed  test    rcx, rcx
0x1800db8f0  jz      short loc_1800DB8F8
0x1800db8f2  call    cs:__imp_CloseHandle
0x1800db8f8  mov     eax, ebx
0x1800db8fa  mov     rcx, [rbp+var_8]
0x1800db8fe  xor     rcx, rsp; StackCookie
0x1800db901  call    __security_check_cookie
0x1800db906  mov     rbx, [rsp+50h+arg_8]
0x1800db90b  mov     rdi, [rsp+50h+arg_10]
0x1800db910  add     rsp, 50h
0x1800db914  pop     rbp
0x1800db915  retn
```
