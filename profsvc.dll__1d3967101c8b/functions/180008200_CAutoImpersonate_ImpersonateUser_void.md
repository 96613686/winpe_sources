# CAutoImpersonate::ImpersonateUser(void *)

- ea: `0x180008200`
- end: `0x180008358`
- name: `?ImpersonateUser@CAutoImpersonate@@QEAAJPEAX@Z`
- size: `344`
- prototype: `__int64 __fastcall(CAutoImpersonate *this, void *)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004768`
- `0x18000659c`
- `0x1800080c8`
- `0x180011200`
- `0x1800123cc`
- `0x180013048`
- `0x180017364`
- `0x1800190f4`
- `0x18002cf64`
- `0x180036eec`
- `0x1800384b8`
- `0x180039d6c`
- `0x1800436b0`
- `0x18004cc94`
- `0x18004debc`

## callees

- `0x180008200`
- `0x18000a9b8`
- `0x18002d2d8`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000827b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008271`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008271`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000822e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000822e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008258`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008244`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008292`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008292`

## string_xrefs

- `0x1800082e3`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18000830e`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180008336`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::ImpersonateUser(CAutoImpersonate *this, void *a2)
{
  const char *v4; // r9
  void *v5; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v8; // edi
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500037LL;
  if ( *((_BYTE *)this + 8) )
  {
    if ( SetThreadToken(0, *(HANDLE *)this) )
    {
      v5 = *(void **)this;
      if ( !*(_QWORD *)this )
      {
LABEL_6:
        *((_BYTE *)this + 8) = 0;
        goto LABEL_7;
      }
    }
    else
    {
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v4);
      v5 = *(void **)this;
      if ( !*(_QWORD *)this )
        goto LABEL_6;
    }
    CloseHandle(v5);
    goto LABEL_6;
  }
LABEL_7:
  *(_QWORD *)this = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    goto LABEL_22;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 == -2147023888 || v8 >= 0 )
  {
LABEL_22:
    if ( ImpersonateLoggedOnUser(a2) )
    {
      v8 = 0;
      *(_QWORD *)this = TokenHandle;
    }
    else
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2D,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             v9);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v8,
      v11);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  result = (unsigned int)v8;
  *((_BYTE *)this + 8) = v8 >= 0;
  return result;
}

```

## disassembly

```asm
0x180008200  mov     [rsp+arg_18], rbx
0x180008205  push    rsi; int
0x180008206  sub     rsp, 20h
0x18000820a  mov     rsi, rdx
0x18000820d  mov     rbx, rcx
0x180008210  test    rdx, rdx
0x180008213  jz      loc_1800082D7
0x180008219  cmp     byte ptr [rcx+8], 0
0x18000821d  mov     [rsp+28h+arg_0], rbp
0x180008222  mov     [rsp+28h+arg_10], rdi
0x180008227  jz      short loc_18000824E
0x180008229  mov     rdx, [rcx]; Token
0x18000822c  xor     ecx, ecx; Thread
0x18000822e  call    cs:__imp_SetThreadToken
0x180008234  test    eax, eax
0x180008236  jz      loc_1800082DE
0x18000823c  mov     rcx, [rbx]; hObject
0x18000823f  test    rcx, rcx
0x180008242  jz      short loc_18000824A
0x180008244  call    cs:__imp_CloseHandle
0x18000824a  mov     byte ptr [rbx+8], 0
0x18000824e  xor     ebp, ebp
0x180008250  mov     [rbx], rbp
0x180008253  mov     [rsp+28h+TokenHandle], rbp
0x180008258  call    cs:__imp_GetCurrentThread
0x18000825e  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180008263  mov     edx, 2000Ch; DesiredAccess
0x180008268  mov     rcx, rax; ThreadHandle
0x18000826b  mov     r8d, 1; OpenAsSelf
0x180008271  call    cs:__imp_OpenThreadToken
0x180008277  test    eax, eax
0x180008279  jnz     short loc_18000828F
0x18000827b  call    cs:__imp_GetLastError
0x180008281  mov     edi, eax
0x180008283  test    eax, eax
0x180008285  jg      short loc_1800082CC
0x180008287  cmp     edi, 800703F0h
0x18000828d  jnz     short loc_180008305
0x18000828f  mov     rcx, rsi; hToken
0x180008292  call    cs:__imp_ImpersonateLoggedOnUser
0x180008298  test    eax, eax
0x18000829a  jz      loc_180008331
0x1800082a0  mov     rax, [rsp+28h+TokenHandle]
0x1800082a5  mov     edi, ebp
0x1800082a7  mov     [rbx], rax
0x1800082aa  mov     rbp, [rsp+28h+arg_0]
0x1800082af  mov     ecx, edi
0x1800082b1  shr     ecx, 1Fh
0x1800082b4  mov     eax, edi
0x1800082b6  mov     rdi, [rsp+28h+arg_10]
0x1800082bb  xor     cl, 1
0x1800082be  mov     [rbx+8], cl
0x1800082c1  mov     rbx, [rsp+28h+arg_18]
0x1800082c6  add     rsp, 20h
0x1800082ca  pop     rsi
0x1800082cb  retn
0x1800082cc  movzx   edi, ax
0x1800082cf  or      edi, 80070000h
0x1800082d5  jmp     short loc_180008287
0x1800082d7  mov     eax, 80004005h
0x1800082dc  jmp     short loc_1800082C1
0x1800082de  mov     rcx, [rsp+28h]; this
0x1800082e3  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800082ea  mov     edx, 4Fh ; 'O'; void *
0x1800082ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800082f4  mov     rcx, [rbx]
0x1800082f7  test    rcx, rcx
0x1800082fa  jz      loc_18000824A
0x180008300  jmp     loc_180008244
0x180008305  test    edi, edi
0x180008307  jns     short loc_18000828F
0x180008309  mov     rcx, [rsp+28h]; this
0x18000830e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180008315  mov     r9d, edi; char *
0x180008318  mov     edx, 2Ah ; '*'; void *
0x18000831d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008322  lea     rcx, [rsp+28h+TokenHandle]
0x180008327  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000832c  jmp     loc_1800082AA
0x180008331  mov     rcx, [rsp+28h]; this
0x180008336  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000833d  mov     edx, 2Dh ; '-'; void *
0x180008342  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008347  lea     rcx, [rsp+28h+TokenHandle]
0x18000834c  mov     edi, eax
0x18000834e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008353  jmp     loc_1800082AA
```
