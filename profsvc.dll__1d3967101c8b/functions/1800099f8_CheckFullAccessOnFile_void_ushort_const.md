# CheckFullAccessOnFile(void *,ushort const *)

- ea: `0x1800099f8`
- end: `0x180009b65`
- name: `?CheckFullAccessOnFile@@YAHPEAXPEBG@Z`
- size: `365`
- prototype: `__int64 __fastcall(HANDLE hToken, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800085cc`
- `0x180011200`
- `0x180039d6c`

## callees

- `0x1800099f8`
- `0x180009b70`
- `0x18000a9b8`
- `0x18002d2d8`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009a43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180009a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009a2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ab9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ab9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009a69`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009a69`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009aa6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180009aa6`

## string_xrefs

- `0x180009aff`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180009b31`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

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
0x1800099f8  mov     [rsp-18h+arg_8], rbx
0x1800099fd  mov     [rsp-18h+arg_10], rsi
0x180009a02  push    rbp
0x180009a03  push    rdi
0x180009a04  push    r15
0x180009a06  mov     rbp, rsp
0x180009a09  sub     rsp, 50h
0x180009a0d  xor     edi, edi
0x180009a0f  mov     rsi, rdx
0x180009a12  mov     [rbp+var_8], dil
0x180009a16  mov     rbx, rcx
0x180009a19  test    rcx, rcx
0x180009a1c  jz      loc_180009AD7
0x180009a22  mov     [rbp+var_10], rdi
0x180009a26  mov     [rbp+TokenHandle], rdi
0x180009a2a  call    cs:__imp_GetCurrentThread
0x180009a30  lea     r15d, [rdi+1]
0x180009a34  mov     edx, 2000Ch; DesiredAccess
0x180009a39  mov     r8d, r15d; OpenAsSelf
0x180009a3c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180009a40  mov     rcx, rax; ThreadHandle
0x180009a43  call    cs:__imp_OpenThreadToken
0x180009a49  test    eax, eax
0x180009a4b  jnz     short loc_180009A66
0x180009a4d  call    cs:__imp_GetLastError
0x180009a53  test    eax, eax
0x180009a55  jg      loc_180009AEE
0x180009a5b  cmp     eax, 800703F0h
0x180009a60  jnz     loc_180009B25
0x180009a66  mov     rcx, rbx; hToken
0x180009a69  call    cs:__imp_ImpersonateLoggedOnUser
0x180009a6f  test    eax, eax
0x180009a71  jz      loc_180009AFB
0x180009a77  mov     rax, [rbp+TokenHandle]
0x180009a7b  mov     [rbp+var_10], rax
0x180009a7f  mov     [rsp+50h+hTemplateFile], rdi; hTemplateFile
0x180009a84  mov     r8d, 3; dwShareMode
0x180009a8a  mov     [rsp+50h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x180009a92  xor     r9d, r9d; lpSecurityAttributes
0x180009a95  mov     edx, 0C0000000h; dwDesiredAccess
0x180009a9a  mov     [rsp+50h+dwCreationDisposition], r8d; dwCreationDisposition
0x180009a9f  mov     rcx, rsi; lpFileName
0x180009aa2  mov     [rbp+var_8], r15b
0x180009aa6  call    cs:__imp_CreateFileW
0x180009aac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009ab0  jz      loc_180009B53
0x180009ab6  mov     rcx, rax; hObject
0x180009ab9  call    cs:__imp_CloseHandle
0x180009abf  mov     edi, r15d
0x180009ac2  jmp     short loc_180009AC8
0x180009ac4  mov     [rbp+var_8], dil
0x180009ac8  cmp     [rbp+var_8], 0
0x180009acc  jz      short loc_180009AD7
0x180009ace  lea     rcx, [rbp+var_10]; void **
0x180009ad2  call    ?RevertToUser@@YAJPEAPEAX@Z; RevertToUser(void * *)
0x180009ad7  lea     r11, [rsp+50h+var_s0]
0x180009adc  mov     eax, edi
0x180009ade  mov     rbx, [r11+28h]
0x180009ae2  mov     rsi, [r11+30h]
0x180009ae6  mov     rsp, r11
0x180009ae9  pop     r15
0x180009aeb  pop     rdi
0x180009aec  pop     rbp
0x180009aed  retn
0x180009aee  movzx   eax, ax
0x180009af1  or      eax, 80070000h
0x180009af6  jmp     loc_180009A5B
0x180009afb  mov     rcx, [rbp+18h]; this
0x180009aff  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009b06  mov     edx, 2Dh ; '-'; void *
0x180009b0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009b10  lea     rcx, [rbp+TokenHandle]
0x180009b14  mov     ebx, eax
0x180009b16  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009b1b  test    ebx, ebx
0x180009b1d  jns     loc_180009A7F
0x180009b23  jmp     short loc_180009AC4
0x180009b25  test    eax, eax
0x180009b27  jns     loc_180009A66
0x180009b2d  mov     rcx, [rbp+18h]; this
0x180009b31  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180009b38  mov     r9d, eax; char *
0x180009b3b  mov     edx, 2Ah ; '*'; void *
0x180009b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b45  lea     rcx, [rbp+TokenHandle]
0x180009b49  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180009b4e  jmp     loc_180009AC4
0x180009b53  call    cs:__imp_GetLastError
0x180009b59  cmp     eax, 5
0x180009b5c  cmovnz  edi, r15d
0x180009b60  jmp     loc_180009AC8
```
