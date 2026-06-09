# CWinHttpRequest::SendRequest(ushort const *,ulong,void *,ulong,ulong,unsigned __int64)

- ea: `0x180011d80`
- end: `0x180011ed4`
- name: `?SendRequest@CWinHttpRequest@@UEAAHPEBGKPEAXKK_K@Z`
- size: `340`
- prototype: `int(CWinHttpRequest *__hidden this, const unsigned __int16 *, unsigned int, void *, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180011d80`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011dbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011dbc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011dd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011dd4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011e12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dde`
- `WINHTTP!WinHttpSendRequest` at `0x180011e97`
- `WINHTTP!WinHttpSendRequest` at `0x180011e97`

## string_xrefs

- `0x180011df0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinHttpRequest::SendRequest(
        CWinHttpRequest *this,
        const unsigned __int16 *a2,
        DWORD a3,
        void *a4,
        DWORD dwOptionalLength,
        DWORD dwTotalLength,
        DWORD_PTR dwContext)
{
  __int64 v11; // rbx
  void *v12; // rdi
  HANDLE CurrentThread; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  int LastError; // edi
  __int64 v17; // rsi
  void *v18; // rdx
  unsigned int v19; // r14d
  void **pExceptionObject; // [rsp+50h] [rbp-61h] BYREF
  __int128 v22; // [rsp+58h] [rbp-59h]
  int v23; // [rsp+68h] [rbp-49h]
  int v24; // [rsp+6Ch] [rbp-45h]
  int v25; // [rsp+70h] [rbp-41h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+47h]
  void *TokenHandle; // [rsp+100h] [rbp+4Fh] BYREF

  v11 = -1;
  v12 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v15 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v15,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v14);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v12) )
  {
    v15 = 454;
    goto LABEL_4;
  }
  v11 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v22 = 0;
    pExceptionObject = &ComError::`vftable';
    v23 = LastError;
    v24 = 2105;
    v25 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v17 = *((_QWORD *)this + 4);
  if ( v17 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v17 + 8));
  v19 = WinHttpSendRequest(*((HINTERNET *)this + 2), a2, a3, a4, dwOptionalLength, dwTotalLength, dwContext);
  if ( v17 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v17 + 8));
  if ( v11 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v11, v18);
  return v19;
}

```

## disassembly

```asm
0x180011d80  push    rbp
0x180011d82  push    rbx
0x180011d83  push    rsi
0x180011d84  push    rdi
0x180011d85  push    r12
0x180011d87  push    r13
0x180011d89  push    r14
0x180011d8b  push    r15
0x180011d8d  lea     rbp, [rsp-7]
0x180011d92  sub     rsp, 0B8h
0x180011d99  mov     r15, r9
0x180011d9c  mov     r12d, r8d
0x180011d9f  mov     r13, rdx
0x180011da2  mov     r14, rcx
0x180011da5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011da9  mov     [rbp+3Fh+var_B0], rbx
0x180011dad  mov     rax, [rcx+8]
0x180011db1  mov     rdi, [rax]
0x180011db4  mov     [rbp+3Fh+TokenHandle], 0
0x180011dbc  call    cs:__imp_GetCurrentThread
0x180011dc2  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180011dc6  lea     esi, [rbx+2]
0x180011dc9  mov     r8d, esi; OpenAsSelf
0x180011dcc  mov     edx, 0F01FFh; DesiredAccess
0x180011dd1  mov     rcx, rax; ThreadHandle
0x180011dd4  call    cs:__imp_OpenThreadToken
0x180011dda  test    eax, eax
0x180011ddc  jnz     short loc_180011E0D
0x180011dde  call    cs:__imp_GetLastError
0x180011de4  cmp     eax, 3F0h
0x180011de9  jz      short loc_180011E0D
0x180011deb  mov     edx, 1C2h; void *
0x180011df0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011df7  mov     rcx, [rbp+47h]; this
0x180011dfb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011e00  mov     edi, eax
0x180011e02  lea     rcx, [rbp+3Fh+TokenHandle]
0x180011e06  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011e0b  jmp     short loc_180011E2D
0x180011e0d  mov     rdx, rdi; Token
0x180011e10  xor     ecx, ecx; Thread
0x180011e12  call    cs:__imp_SetThreadToken
0x180011e18  test    eax, eax
0x180011e1a  jnz     short loc_180011E23
0x180011e1c  mov     edx, 1C6h
0x180011e21  jmp     short loc_180011DF0
0x180011e23  mov     rbx, [rbp+3Fh+TokenHandle]
0x180011e27  mov     [rbp+3Fh+var_B0], rbx
0x180011e2b  xor     edi, edi
0x180011e2d  test    edi, edi
0x180011e2f  jns     short loc_180011E61
0x180011e31  xorps   xmm0, xmm0
0x180011e34  movups  [rbp+3Fh+var_98], xmm0
0x180011e38  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180011e3f  mov     [rbp+3Fh+pExceptionObject], rax
0x180011e43  mov     [rbp+3Fh+var_88], edi
0x180011e46  mov     [rbp+3Fh+var_84], 839h
0x180011e4d  mov     [rbp+3Fh+var_80], esi
0x180011e50  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011e57  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180011e5b  call    _CxxThrowException_0
0x180011e61  mov     rsi, [r14+20h]
0x180011e65  test    rsi, rsi
0x180011e68  jz      short loc_180011E73
0x180011e6a  mov     rcx, [rsi+8]; this
0x180011e6e  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180011e73  mov     rax, [rbp+3Fh+arg_30]
0x180011e77  mov     [rsp+0F0h+dwContext], rax; dwContext
0x180011e7c  mov     eax, [rbp+3Fh+arg_28]
0x180011e7f  mov     [rsp+0F0h+dwTotalLength], eax; dwTotalLength
0x180011e83  mov     eax, [rbp+3Fh+arg_20]
0x180011e86  mov     [rsp+0F0h+dwOptionalLength], eax; dwOptionalLength
0x180011e8a  mov     r9, r15; lpOptional
0x180011e8d  mov     r8d, r12d; dwHeadersLength
0x180011e90  mov     rdx, r13; lpszHeaders
0x180011e93  mov     rcx, [r14+10h]; hRequest
0x180011e97  call    cs:__imp_WinHttpSendRequest
0x180011e9d  mov     r14d, eax
0x180011ea0  test    rsi, rsi
0x180011ea3  jz      short loc_180011EAF
0x180011ea5  mov     rcx, [rsi+8]; this
0x180011ea9  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180011eae  nop
0x180011eaf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011eb3  jz      short loc_180011EBD
0x180011eb5  mov     rcx, rbx; Token
0x180011eb8  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180011ebd  mov     eax, r14d
0x180011ec0  add     rsp, 0B8h
0x180011ec7  pop     r15
0x180011ec9  pop     r14
0x180011ecb  pop     r13
0x180011ecd  pop     r12
0x180011ecf  pop     rdi
0x180011ed0  pop     rsi
0x180011ed1  pop     rbx
0x180011ed2  pop     rbp
0x180011ed3  retn
```
