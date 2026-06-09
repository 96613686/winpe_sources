# CWinHttpRequest::AddRequestHeaders(ushort const *,ulong,ulong)

- ea: `0x1800117a0`
- end: `0x1800118dd`
- name: `?AddRequestHeaders@CWinHttpRequest@@UEAAHPEBGKK@Z`
- size: `317`
- prototype: `int(CWinHttpRequest *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x1800117a0`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800117dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800117dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800117f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800117f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011832`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800117fe`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800118a0`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1800118a0`

## string_xrefs

- `0x180011810`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinHttpRequest::AddRequestHeaders(
        CWinHttpRequest *this,
        const unsigned __int16 *a2,
        DWORD a3,
        DWORD a4)
{
  __int64 v8; // rbx
  void *v9; // rdi
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // edi
  __int64 v14; // rsi
  void *v15; // rdx
  unsigned int v16; // r14d
  void **pExceptionObject; // [rsp+30h] [rbp-49h] BYREF
  __int128 v19; // [rsp+38h] [rbp-41h]
  int v20; // [rsp+48h] [rbp-31h]
  int v21; // [rsp+4Ch] [rbp-2Dh]
  int v22; // [rsp+50h] [rbp-29h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  void *TokenHandle; // [rsp+E0h] [rbp+67h] BYREF

  v8 = -1;
  v9 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v12 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v11);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v9) )
  {
    v12 = 454;
    goto LABEL_4;
  }
  v8 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v19 = 0;
    pExceptionObject = &ComError::`vftable';
    v20 = LastError;
    v21 = 2033;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v14 + 8));
  v16 = WinHttpAddRequestHeaders(*((HINTERNET *)this + 2), a2, a3, a4);
  if ( v14 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v14 + 8));
  if ( v8 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v8, v15);
  return v16;
}

```

## disassembly

```asm
0x1800117a0  push    rbp
0x1800117a2  push    rbx
0x1800117a3  push    rsi
0x1800117a4  push    rdi
0x1800117a5  push    r12
0x1800117a7  push    r13
0x1800117a9  push    r14
0x1800117ab  push    r15
0x1800117ad  lea     rbp, [rsp-1Fh]
0x1800117b2  sub     rsp, 98h
0x1800117b9  mov     r15d, r9d
0x1800117bc  mov     r12d, r8d
0x1800117bf  mov     r13, rdx
0x1800117c2  mov     r14, rcx
0x1800117c5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800117c9  mov     [rbp+57h+var_B0], rbx
0x1800117cd  mov     rax, [rcx+8]
0x1800117d1  mov     rdi, [rax]
0x1800117d4  mov     [rbp+57h+TokenHandle], 0
0x1800117dc  call    cs:__imp_GetCurrentThread
0x1800117e2  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800117e6  lea     esi, [rbx+2]
0x1800117e9  mov     r8d, esi; OpenAsSelf
0x1800117ec  mov     edx, 0F01FFh; DesiredAccess
0x1800117f1  mov     rcx, rax; ThreadHandle
0x1800117f4  call    cs:__imp_OpenThreadToken
0x1800117fa  test    eax, eax
0x1800117fc  jnz     short loc_18001182D
0x1800117fe  call    cs:__imp_GetLastError
0x180011804  cmp     eax, 3F0h
0x180011809  jz      short loc_18001182D
0x18001180b  mov     edx, 1C2h; void *
0x180011810  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011817  mov     rcx, [rbp+5Fh]; this
0x18001181b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011820  mov     edi, eax
0x180011822  lea     rcx, [rbp+57h+TokenHandle]
0x180011826  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001182b  jmp     short loc_18001184D
0x18001182d  mov     rdx, rdi; Token
0x180011830  xor     ecx, ecx; Thread
0x180011832  call    cs:__imp_SetThreadToken
0x180011838  test    eax, eax
0x18001183a  jnz     short loc_180011843
0x18001183c  mov     edx, 1C6h
0x180011841  jmp     short loc_180011810
0x180011843  mov     rbx, [rbp+57h+TokenHandle]
0x180011847  mov     [rbp+57h+var_B0], rbx
0x18001184b  xor     edi, edi
0x18001184d  test    edi, edi
0x18001184f  jns     short loc_180011881
0x180011851  xorps   xmm0, xmm0
0x180011854  movups  [rbp+57h+var_98], xmm0
0x180011858  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001185f  mov     [rbp+57h+pExceptionObject], rax
0x180011863  mov     [rbp+57h+var_88], edi
0x180011866  mov     [rbp+57h+var_84], 7F1h
0x18001186d  mov     [rbp+57h+var_80], esi
0x180011870  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011877  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001187b  call    _CxxThrowException_0
0x180011881  mov     rsi, [r14+20h]
0x180011885  test    rsi, rsi
0x180011888  jz      short loc_180011893
0x18001188a  mov     rcx, [rsi+8]; this
0x18001188e  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180011893  mov     r9d, r15d; dwModifiers
0x180011896  mov     r8d, r12d; dwHeadersLength
0x180011899  mov     rdx, r13; lpszHeaders
0x18001189c  mov     rcx, [r14+10h]; hRequest
0x1800118a0  call    cs:__imp_WinHttpAddRequestHeaders
0x1800118a6  mov     r14d, eax
0x1800118a9  test    rsi, rsi
0x1800118ac  jz      short loc_1800118B8
0x1800118ae  mov     rcx, [rsi+8]; this
0x1800118b2  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x1800118b7  nop
0x1800118b8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800118bc  jz      short loc_1800118C6
0x1800118be  mov     rcx, rbx; Token
0x1800118c1  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x1800118c6  mov     eax, r14d
0x1800118c9  add     rsp, 98h
0x1800118d0  pop     r15
0x1800118d2  pop     r14
0x1800118d4  pop     r13
0x1800118d6  pop     r12
0x1800118d8  pop     rdi
0x1800118d9  pop     rsi
0x1800118da  pop     rbx
0x1800118db  pop     rbp
0x1800118dc  retn
```
