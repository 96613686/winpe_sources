# CheckFullAccessOnFile(void *,ushort const *)

- ea: `0x18000721c`
- end: `0x1800073b4`
- name: `?CheckFullAccessOnFile@@YAHPEAXPEBG@Z`
- size: `408`
- prototype: `__int64 __fastcall(HANDLE hToken, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016150`
- `0x1800178bc`
- `0x18003b26c`

## callees

- `0x18000721c`
- `0x1800073c0`
- `0x1800084bc`
- `0x18002df48`
- `0x180030ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000727d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000739c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000727d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000739c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000726d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000726d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000724e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000724e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072fb`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000729f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000729f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800072e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800072e2`

## string_xrefs

- `0x180007348`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000737a`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckFullAccessOnFile(HANDLE hToken, LPCWSTR lpFileName)
{
  unsigned int v2; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v7; // r9
  HANDLE FileW; // rax
  int v10; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-30h]
  void *v12; // [rsp+40h] [rbp-10h] BYREF
  char v13; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  void *TokenHandle; // [rsp+70h] [rbp+20h] BYREF

  v2 = 0;
  v13 = 0;
  if ( !hToken )
    return v2;
  v12 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_23;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 || LastError >= 0 )
  {
LABEL_23:
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v12 = TokenHandle;
    }
    else
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2D,
              (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
              v7);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      if ( v10 < 0 )
        goto LABEL_10;
    }
    v13 = 1;
    FileW = CreateFileW(lpFileName, 0xC0000000, 3u, 0, 3u, 2u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( GetLastError() != 5 )
        v2 = 1;
    }
    else
    {
      CloseHandle(FileW);
      v2 = 1;
    }
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
    (const char *)(unsigned int)LastError,
    dwCreationDisposition);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_10:
  v13 = 0;
LABEL_11:
  if ( v13 )
    RevertToUser(&v12);
  return v2;
}

```

## disassembly

```asm
0x18000721c  mov     [rsp-18h+arg_8], rbx
0x180007221  mov     [rsp-18h+arg_10], rsi
0x180007226  push    rbp
0x180007227  push    rdi
0x180007228  push    r15
0x18000722a  mov     rbp, rsp
0x18000722d  sub     rsp, 50h
0x180007231  xor     edi, edi
0x180007233  mov     rsi, rdx
0x180007236  mov     [rbp+var_8], dil
0x18000723a  mov     rbx, rcx
0x18000723d  test    rcx, rcx
0x180007240  jz      loc_18000731F
0x180007246  mov     [rbp+var_10], rdi
0x18000724a  mov     [rbp+TokenHandle], rdi
0x18000724e  call    cs:__imp_GetCurrentThread
0x180007255  nop     dword ptr [rax+rax+00h]
0x18000725a  lea     r15d, [rdi+1]
0x18000725e  mov     edx, 2000Ch; DesiredAccess
0x180007263  mov     r8d, r15d; OpenAsSelf
0x180007266  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18000726a  mov     rcx, rax; ThreadHandle
0x18000726d  call    cs:__imp_OpenThreadToken
0x180007274  nop     dword ptr [rax+rax+00h]
0x180007279  test    eax, eax
0x18000727b  jnz     short loc_18000729C
0x18000727d  call    cs:__imp_GetLastError
0x180007284  nop     dword ptr [rax+rax+00h]
0x180007289  test    eax, eax
0x18000728b  jg      loc_180007337
0x180007291  cmp     eax, 800703F0h
0x180007296  jnz     loc_18000736E
0x18000729c  mov     rcx, rbx; hToken
0x18000729f  call    cs:__imp_ImpersonateLoggedOnUser
0x1800072a6  nop     dword ptr [rax+rax+00h]
0x1800072ab  test    eax, eax
0x1800072ad  jz      loc_180007344
0x1800072b3  mov     rax, [rbp+TokenHandle]
0x1800072b7  mov     [rbp+var_10], rax
0x1800072bb  mov     [rsp+50h+hTemplateFile], rdi; hTemplateFile
0x1800072c0  mov     r8d, 3; dwShareMode
0x1800072c6  mov     [rsp+50h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x1800072ce  xor     r9d, r9d; lpSecurityAttributes
0x1800072d1  mov     edx, 0C0000000h; dwDesiredAccess
0x1800072d6  mov     [rsp+50h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800072db  mov     rcx, rsi; lpFileName
0x1800072de  mov     [rbp+var_8], r15b
0x1800072e2  call    cs:__imp_CreateFileW
0x1800072e9  nop     dword ptr [rax+rax+00h]
0x1800072ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800072f2  jz      loc_18000739C
0x1800072f8  mov     rcx, rax; hObject
0x1800072fb  call    cs:__imp_CloseHandle
0x180007302  nop     dword ptr [rax+rax+00h]
0x180007307  mov     edi, r15d
0x18000730a  jmp     short loc_180007310
0x18000730c  mov     [rbp+var_8], dil
0x180007310  cmp     [rbp+var_8], 0
0x180007314  jz      short loc_18000731F
0x180007316  lea     rcx, [rbp+var_10]; void **
0x18000731a  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x18000731f  lea     r11, [rsp+50h+var_s0]
0x180007324  mov     eax, edi
0x180007326  mov     rbx, [r11+28h]
0x18000732a  mov     rsi, [r11+30h]
0x18000732e  mov     rsp, r11
0x180007331  pop     r15
0x180007333  pop     rdi
0x180007334  pop     rbp
0x180007335  retn
0x180007337  movzx   eax, ax
0x18000733a  or      eax, 80070000h
0x18000733f  jmp     loc_180007291
0x180007344  mov     rcx, [rbp+18h]; this
0x180007348  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000734f  mov     edx, 2Dh ; '-'; void *
0x180007354  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007359  lea     rcx, [rbp+TokenHandle]
0x18000735d  mov     ebx, eax
0x18000735f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007364  test    ebx, ebx
0x180007366  jns     loc_1800072BB
0x18000736c  jmp     short loc_18000730C
0x18000736e  test    eax, eax
0x180007370  jns     loc_18000729C
0x180007376  mov     rcx, [rbp+18h]; this
0x18000737a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180007381  mov     r9d, eax; char *
0x180007384  mov     edx, 2Ah ; '*'; void *
0x180007389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000738e  lea     rcx, [rbp+TokenHandle]
0x180007392  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180007397  jmp     loc_18000730C
0x18000739c  call    cs:__imp_GetLastError
0x1800073a3  nop     dword ptr [rax+rax+00h]
0x1800073a8  cmp     eax, 5
0x1800073ab  cmovnz  edi, r15d
0x1800073af  jmp     loc_180007310
```
