# IsCallerWcmSvc(int *)

- ea: `0x1800133d0`
- end: `0x1800134e6`
- name: `?IsCallerWcmSvc@@YAKPEAH@Z`
- size: `278`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013240`
- `0x18001c5a0`
- `0x18001d2f0`
- `0x180029960`
- `0x180029a60`
- `0x180029b20`
- `0x180029bb0`
- `0x180029c40`

## callees

- `0x1800133d0`
- `0x180017b74`
- `0x18001b948`
- `0x18001c080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800134b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001341b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001341b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013433`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180013433`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001348a`
- `RPCRT4!RpcRevertToSelfEx` at `0x18001348a`
- `RPCRT4!RpcImpersonateClient` at `0x1800133e2`
- `RPCRT4!RpcImpersonateClient` at `0x1800133e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800134dc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013465`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180013465`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800134d3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180013450`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180013450`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
int __fastcall IsCallerWcmSvc(PBOOL IsMember)
{
  unsigned int v2; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  unsigned int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  void *TokenHandle; // [rsp+40h] [rbp+20h] BYREF
  PSID Sid; // [rsp+48h] [rbp+28h] BYREF

  v2 = RpcImpersonateClient(0);
  if ( v2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x94,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\sbrpc.cpp",
             (const char *)v2,
             savedregs);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(L"S-1-5-80-4155767994-3874329934-3800885181-2130851812-726865888", &Sid)
      && CheckTokenMembership(TokenHandle, Sid, IsMember) )
    {
      if ( Sid )
        LocalFree(Sid);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
  }
  RpcRevertToSelfEx(0);
  return LastError;
}

```

## disassembly

```asm
0x1800133d0  mov     [rsp-8+arg_0], rbx
0x1800133d5  push    rbp; unsigned int
0x1800133d6  mov     rbp, rsp
0x1800133d9  sub     rsp, 20h
0x1800133dd  mov     rbx, rcx
0x1800133e0  xor     ecx, ecx; BindingHandle
0x1800133e2  call    cs:__imp_RpcImpersonateClient
0x1800133e8  test    eax, eax
0x1800133ea  jz      short loc_18001340F
0x1800133ec  mov     rcx, [rbp+8]; this
0x1800133f0  mov     r9d, eax; char *
0x1800133f3  lea     r8, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x1800133fa  mov     edx, 94h; void *
0x1800133ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013404  mov     rbx, [rsp+20h+arg_0]
0x180013409  add     rsp, 20h
0x18001340d  pop     rbp
0x18001340e  retn
0x18001340f  mov     [rbp+arg_9], 1
0x180013413  mov     [rbp+TokenHandle], 0
0x18001341b  call    cs:__imp_GetCurrentThread
0x180013421  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180013425  mov     edx, 0F01FFh; DesiredAccess
0x18001342a  mov     r8d, 1; OpenAsSelf
0x180013430  mov     rcx, rax; ThreadHandle
0x180013433  call    cs:__imp_OpenThreadToken
0x180013439  test    eax, eax
0x18001343b  jz      short loc_180013497
0x18001343d  mov     [rbp+Sid], 0
0x180013445  lea     rdx, [rbp+Sid]; Sid
0x180013449  lea     rcx, StringSid; "S-1-5-80-4155767994-3874329934-38008851"...
0x180013450  call    cs:__imp_ConvertStringSidToSidW
0x180013456  test    eax, eax
0x180013458  jz      short loc_1800134B6
0x18001345a  mov     r8, rbx; IsMember
0x18001345d  mov     rdx, [rbp+Sid]; SidToCheck
0x180013461  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180013465  call    cs:__imp_CheckTokenMembership
0x18001346b  test    eax, eax
0x18001346d  jz      short loc_1800134B6
0x18001346f  mov     rcx, [rbp+Sid]; hMem
0x180013473  test    rcx, rcx
0x180013476  jnz     short loc_1800134D3
0x180013478  mov     rcx, [rbp+TokenHandle]; hObject
0x18001347c  lea     rax, [rcx-1]
0x180013480  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013484  jbe     short loc_1800134DC
0x180013486  xor     ebx, ebx
0x180013488  xor     ecx, ecx; BindingHandle
0x18001348a  call    cs:__imp_RpcRevertToSelfEx
0x180013490  mov     eax, ebx
0x180013492  jmp     loc_180013404
0x180013497  call    cs:__imp_GetLastError
0x18001349d  mov     ebx, eax
0x18001349f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800134a3  lea     rdx, [rcx-1]
0x1800134a7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800134ab  ja      short loc_180013488
0x1800134ad  call    cs:__imp_CloseHandle
0x1800134b3  nop
0x1800134b4  jmp     short loc_180013488
0x1800134b6  call    cs:__imp_GetLastError
0x1800134bc  mov     ebx, eax
0x1800134be  lea     rcx, [rbp+Sid]
0x1800134c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800134c7  nop
0x1800134c8  lea     rcx, [rbp+TokenHandle]
0x1800134cc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800134d1  jmp     short loc_180013488
0x1800134d3  call    cs:__imp_LocalFree
0x1800134d9  nop
0x1800134da  jmp     short loc_180013478
0x1800134dc  call    cs:__imp_CloseHandle
0x1800134e2  nop
0x1800134e3  jmp     short loc_180013486
```
