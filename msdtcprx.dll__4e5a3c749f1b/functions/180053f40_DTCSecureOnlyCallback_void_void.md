# DTCSecureOnlyCallback(void *,void *)

- ea: `0x180053f40`
- end: `0x1800540ea`
- name: `?DTCSecureOnlyCallback@@YAJPEAX0@Z`
- size: `426`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x180053f40`
- `0x180054968`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientExA` at `0x180053f86`
- `RPCRT4!RpcBindingInqAuthClientExA` at `0x180053f86`
- `RPCRT4!RpcRevertToSelf` at `0x1800540c1`
- `RPCRT4!RpcRevertToSelf` at `0x1800540c1`
- `RPCRT4!RpcImpersonateClient` at `0x180053fe5`
- `RPCRT4!RpcImpersonateClient` at `0x180053fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054045`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180053ffb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054011`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180054011`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054081`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054031`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180054031`

## string_xrefs

- `0x180053fa8`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005405d`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x1800540a1`: `com\complus\dtc\dtc\cm\src\iomgrrpc.cpp`
- `0x18005404b`: `CheckTokenMembership failed`
- `0x18005408f`: `OpenThreadToken failed`
- `0x1800540cb`: `Failed to revert to self in security callback`

## pseudocode

```c
__int64 __fastcall DTCSecureOnlyCallback(void *a1, void *a2)
{
  RPC_STATUS v2; // eax
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  __int64 v6; // [rsp+28h] [rbp-28h]
  void *TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+48h] [rbp-8h] BYREF
  unsigned int AuthnLevel; // [rsp+70h] [rbp+20h] BYREF
  WINBOOL IsMember; // [rsp+78h] [rbp+28h] BYREF

  Privs = 0;
  AuthnLevel = 0;
  v2 = RpcBindingInqAuthClientExA(0, &Privs, 0, &AuthnLevel, 0, 0, 0);
  if ( v2 )
  {
    LODWORD(v6) = RpcStatusToHresult(v2);
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
      626,
      L"DTCSecureOnlyCallback",
      v6,
      L"Failed to determine client's authentication level");
    return 5;
  }
  if ( AuthnLevel != 6 )
    return 5;
  v4 = 5;
  if ( !RpcImpersonateClient(0) )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      IsMember = 0;
      if ( CheckTokenMembership(TokenHandle, &AuthenticatedUsersSid, &IsMember) )
      {
        if ( IsMember )
          v4 = 0;
      }
      else
      {
        LODWORD(v6) = GetLastError();
        TraceStringInline(
          1,
          1,
          L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
          657,
          L"DTCSecureOnlyCallback",
          v6,
          L"CheckTokenMembership failed");
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      LODWORD(v6) = GetLastError();
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrrpc.cpp",
        664,
        L"DTCSecureOnlyCallback",
        v6,
        L"OpenThreadToken failed");
    }
    if ( RpcRevertToSelf() )
      DtcInternalErrorW(L"Failed to revert to self in security callback");
  }
  return v4;
}

```

## disassembly

```asm
0x180053f40  mov     rax, rsp
0x180053f43  mov     [rax+8], rbx
0x180053f47  mov     [rax+10h], rdi
0x180053f4b  push    rbp
0x180053f4c  mov     rbp, rsp
0x180053f4f  sub     rsp, 50h
0x180053f53  mov     dword ptr [rax-28h], 0
0x180053f5a  lea     r9, [rbp+AuthnLevel]; AuthnLevel
0x180053f5e  mov     qword ptr [rax-30h], 0
0x180053f66  lea     rdx, [rbp+Privs]; Privs
0x180053f6a  xor     r8d, r8d; ServerPrincName
0x180053f6d  mov     qword ptr [rax-38h], 0
0x180053f75  xor     ecx, ecx; ClientBinding
0x180053f77  mov     [rbp+Privs], 0
0x180053f7f  mov     [rbp+AuthnLevel], 0
0x180053f86  call    cs:__imp_RpcBindingInqAuthClientExA
0x180053f8c  test    eax, eax
0x180053f8e  jz      short loc_180053FD8
0x180053f90  mov     ecx, eax; int
0x180053f92  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180053f97  lea     rcx, aFailedToDeterm; "Failed to determine client's authentica"...
0x180053f9e  mov     edi, 1
0x180053fa3  mov     [rsp+50h+var_20], rcx
0x180053fa8  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180053faf  mov     dword ptr [rsp+50h+var_28], eax
0x180053fb3  mov     r9d, 272h
0x180053fb9  lea     rax, aDtcsecureonlyc; "DTCSecureOnlyCallback"
0x180053fc0  mov     edx, edi
0x180053fc2  mov     ecx, edi
0x180053fc4  mov     [rsp+50h+var_30], rax
0x180053fc9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180053fce  mov     eax, 5
0x180053fd3  jmp     loc_1800540DA
0x180053fd8  cmp     [rbp+AuthnLevel], 6
0x180053fdc  jnz     short loc_180053FCE
0x180053fde  xor     ecx, ecx; BindingHandle
0x180053fe0  mov     ebx, 5
0x180053fe5  call    cs:__imp_RpcImpersonateClient
0x180053feb  test    eax, eax
0x180053fed  jnz     loc_1800540D8
0x180053ff3  mov     [rbp+TokenHandle], 0
0x180053ffb  call    cs:__imp_GetCurrentThread
0x180054001  lea     edi, [rbx-4]
0x180054004  mov     rcx, rax; ThreadHandle
0x180054007  mov     r8d, edi; OpenAsSelf
0x18005400a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005400e  lea     edx, [rbx+3]; DesiredAccess
0x180054011  call    cs:__imp_OpenThreadToken
0x180054017  test    eax, eax
0x180054019  jz      short loc_180054089
0x18005401b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005401f  lea     r8, [rbp+IsMember]; IsMember
0x180054023  lea     rdx, ?AuthenticatedUsersSid@@3U_SID1@@A; SidToCheck
0x18005402a  mov     [rbp+IsMember], 0
0x180054031  call    cs:__imp_CheckTokenMembership
0x180054037  test    eax, eax
0x180054039  jz      short loc_180054045
0x18005403b  cmp     [rbp+IsMember], 0
0x18005403f  jz      short loc_18005407D
0x180054041  xor     ebx, ebx
0x180054043  jmp     short loc_18005407D
0x180054045  call    cs:__imp_GetLastError
0x18005404b  lea     rcx, aChecktokenmemb; "CheckTokenMembership failed"
0x180054052  mov     r9d, 291h
0x180054058  mov     [rsp+50h+var_20], rcx
0x18005405d  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x180054064  mov     dword ptr [rsp+50h+var_28], eax
0x180054068  mov     edx, edi
0x18005406a  lea     rax, aDtcsecureonlyc; "DTCSecureOnlyCallback"
0x180054071  mov     ecx, edi
0x180054073  mov     [rsp+50h+var_30], rax
0x180054078  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18005407d  mov     rcx, [rbp+TokenHandle]; hObject
0x180054081  call    cs:__imp_CloseHandle
0x180054087  jmp     short loc_1800540C1
0x180054089  call    cs:__imp_GetLastError
0x18005408f  lea     rcx, aOpenthreadtoke; "OpenThreadToken failed"
0x180054096  mov     r9d, 298h
0x18005409c  mov     [rsp+50h+var_20], rcx
0x1800540a1  lea     r8, aComComplusDtcD_14; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrr"...
0x1800540a8  mov     dword ptr [rsp+50h+var_28], eax
0x1800540ac  mov     edx, edi
0x1800540ae  lea     rax, aDtcsecureonlyc; "DTCSecureOnlyCallback"
0x1800540b5  mov     ecx, edi
0x1800540b7  mov     [rsp+50h+var_30], rax
0x1800540bc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800540c1  call    cs:__imp_RpcRevertToSelf
0x1800540c7  test    eax, eax
0x1800540c9  jz      short loc_1800540D8
0x1800540cb  lea     rcx, aFailedToRevert; "Failed to revert to self in security ca"...
0x1800540d2  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x1800540d8  mov     eax, ebx
0x1800540da  mov     rbx, [rsp+50h+arg_0]
0x1800540df  mov     rdi, [rsp+50h+arg_8]
0x1800540e4  add     rsp, 50h
0x1800540e8  pop     rbp
0x1800540e9  retn
```
