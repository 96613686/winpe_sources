# AdjustShutdownPrivilege

- ea: `0x180012300`
- end: `0x180012404`
- name: `AdjustShutdownPrivilege`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b700`

## callees

- `0x1800098bc`
- `0x180012300`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001233f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001233f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001232d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001232d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001236e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800123e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001236e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800123e5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800123c3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800123c3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180012385`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180012385`

## string_xrefs

- `0x18001237e`: `SeShutdownPrivilege`

## pseudocode

```c
__int64 __fastcall AdjustShutdownPrivilege(unsigned __int8 a1)
{
  int v1; // ebx
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  unsigned int LastError; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-20h] BYREF
  _LUID Luid[2]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v1 = a1;
  *(_OWORD *)&Luid[0].LowPart = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v4 = 3262;
LABEL_3:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v4,
                  (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                  v3);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return LastError;
  }
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
  {
    v4 = 3263;
    goto LABEL_3;
  }
  Luid[0].LowPart = 1;
  Luid[1].HighPart = 2 * v1;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
  {
    v4 = 3268;
    goto LABEL_3;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x180012300  mov     [rsp-8+arg_0], rbx
0x180012305  push    rbp
0x180012306  mov     rbp, rsp
0x180012309  sub     rsp, 50h
0x18001230d  mov     rax, cs:__security_cookie
0x180012314  xor     rax, rsp
0x180012317  mov     [rbp+var_8], rax
0x18001231b  xorps   xmm0, xmm0
0x18001231e  movzx   ebx, cl
0x180012321  movups  xmmword ptr [rbp+Luid.LowPart], xmm0
0x180012325  mov     [rbp+TokenHandle], 0
0x18001232d  call    cs:__imp_GetCurrentProcess
0x180012333  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180012337  mov     edx, 28h ; '('; DesiredAccess
0x18001233c  mov     rcx, rax; ProcessHandle
0x18001233f  call    cs:__imp_OpenProcessToken
0x180012345  test    eax, eax
0x180012347  jnz     short loc_180012378
0x180012349  mov     edx, 0CBEh; void *
0x18001234e  mov     rcx, [rbp+8]; this
0x180012352  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180012359  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001235e  mov     rcx, [rbp+TokenHandle]; hObject
0x180012362  mov     ebx, eax
0x180012364  lea     rdx, [rcx-1]
0x180012368  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001236c  ja      short loc_180012374
0x18001236e  call    cs:__imp_CloseHandle
0x180012374  mov     eax, ebx
0x180012376  jmp     short loc_1800123ED
0x180012378  lea     r8, [rbp+Luid.HighPart]; lpLuid
0x18001237c  xor     ecx, ecx; lpSystemName
0x18001237e  lea     rdx, Name; "SeShutdownPrivilege"
0x180012385  call    cs:__imp_LookupPrivilegeValueW
0x18001238b  test    eax, eax
0x18001238d  jnz     short loc_180012396
0x18001238f  mov     edx, 0CBFh
0x180012394  jmp     short loc_18001234E
0x180012396  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001239a  lea     r8, [rbp+Luid]; NewState
0x18001239e  mov     eax, ebx
0x1800123a0  mov     [rsp+50h+ReturnLength], 0; ReturnLength
0x1800123a9  add     eax, eax
0x1800123ab  mov     [rbp+Luid.LowPart], 1
0x1800123b2  xor     r9d, r9d; BufferLength
0x1800123b5  mov     [rbp+Luid.HighPart+8], eax
0x1800123b8  xor     edx, edx; DisableAllPrivileges
0x1800123ba  mov     [rsp+50h+PreviousState], 0; PreviousState
0x1800123c3  call    cs:__imp_AdjustTokenPrivileges
0x1800123c9  test    eax, eax
0x1800123cb  jnz     short loc_1800123D7
0x1800123cd  mov     edx, 0CC4h
0x1800123d2  jmp     loc_18001234E
0x1800123d7  mov     rcx, [rbp+TokenHandle]; hObject
0x1800123db  lea     rax, [rcx-1]
0x1800123df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800123e3  ja      short loc_1800123EB
0x1800123e5  call    cs:__imp_CloseHandle
0x1800123eb  xor     eax, eax
0x1800123ed  mov     rcx, [rbp+var_8]
0x1800123f1  xor     rcx, rsp; StackCookie
0x1800123f4  call    __security_check_cookie
0x1800123f9  mov     rbx, [rsp+50h+arg_0]
0x1800123fe  add     rsp, 50h
0x180012402  pop     rbp
0x180012403  retn
```
