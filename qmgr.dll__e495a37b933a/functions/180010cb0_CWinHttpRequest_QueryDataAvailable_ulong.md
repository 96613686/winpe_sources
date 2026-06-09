# CWinHttpRequest::QueryDataAvailable(ulong *)

- ea: `0x180010cb0`
- end: `0x180010de1`
- name: `?QueryDataAvailable@CWinHttpRequest@@UEAAHPEAK@Z`
- size: `305`
- prototype: `int(CWinHttpRequest *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180010cb0`
- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010ce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010ce3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010cfb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180010cfb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010d39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d05`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180010da1`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180010da1`

## string_xrefs

- `0x180010d17`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWinHttpRequest::QueryDataAvailable(CWinHttpRequest *this, unsigned int *a2)
{
  __int64 v4; // rbx
  void *v5; // rdi
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  int LastError; // edi
  __int64 v10; // rsi
  void *v11; // rdx
  unsigned int DataAvailable; // r14d
  void **pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  __int128 v15; // [rsp+28h] [rbp-58h]
  int v16; // [rsp+38h] [rbp-48h]
  int v17; // [rsp+3Ch] [rbp-44h]
  int v18; // [rsp+40h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  void *TokenHandle; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+40h]

  v4 = -1;
  v21 = -1;
  v5 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v8 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v5) )
  {
    v8 = 454;
    goto LABEL_4;
  }
  v4 = (__int64)TokenHandle;
  v21 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v15 = 0;
    pExceptionObject = &ComError::`vftable';
    v16 = LastError;
    v17 = 2145;
    v18 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v10 = *((_QWORD *)this + 4);
  if ( v10 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v10 + 8));
  DataAvailable = WinHttpQueryDataAvailable(*((HINTERNET *)this + 2), a2);
  if ( v10 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v10 + 8));
  if ( v4 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v4, v11);
  return DataAvailable;
}

```

## disassembly

```asm
0x180010cb0  mov     [rsp-28h+arg_8], rbx
0x180010cb5  push    rbp
0x180010cb6  push    rsi
0x180010cb7  push    rdi
0x180010cb8  push    r14
0x180010cba  push    r15
0x180010cbc  mov     rbp, rsp
0x180010cbf  sub     rsp, 80h
0x180010cc6  mov     r15, rdx
0x180010cc9  mov     r14, rcx
0x180010ccc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010cd0  mov     [rbp+arg_10], rbx
0x180010cd4  mov     rax, [rcx+8]
0x180010cd8  mov     rdi, [rax]
0x180010cdb  mov     [rbp+TokenHandle], 0
0x180010ce3  call    cs:__imp_GetCurrentThread
0x180010ce9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180010ced  lea     esi, [rbx+2]
0x180010cf0  mov     r8d, esi; OpenAsSelf
0x180010cf3  mov     edx, 0F01FFh; DesiredAccess
0x180010cf8  mov     rcx, rax; ThreadHandle
0x180010cfb  call    cs:__imp_OpenThreadToken
0x180010d01  test    eax, eax
0x180010d03  jnz     short loc_180010D34
0x180010d05  call    cs:__imp_GetLastError
0x180010d0b  cmp     eax, 3F0h
0x180010d10  jz      short loc_180010D34
0x180010d12  mov     edx, 1C2h; void *
0x180010d17  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010d1e  mov     rcx, [rbp+28h]; this
0x180010d22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010d27  mov     edi, eax
0x180010d29  lea     rcx, [rbp+TokenHandle]
0x180010d2d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180010d32  jmp     short loc_180010D54
0x180010d34  mov     rdx, rdi; Token
0x180010d37  xor     ecx, ecx; Thread
0x180010d39  call    cs:__imp_SetThreadToken
0x180010d3f  test    eax, eax
0x180010d41  jnz     short loc_180010D4A
0x180010d43  mov     edx, 1C6h
0x180010d48  jmp     short loc_180010D17
0x180010d4a  mov     rbx, [rbp+TokenHandle]
0x180010d4e  mov     [rbp+arg_10], rbx
0x180010d52  xor     edi, edi
0x180010d54  test    edi, edi
0x180010d56  jns     short loc_180010D88
0x180010d58  xorps   xmm0, xmm0
0x180010d5b  movups  [rbp+var_58], xmm0
0x180010d5f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180010d66  mov     [rbp+pExceptionObject], rax
0x180010d6a  mov     [rbp+var_48], edi
0x180010d6d  mov     [rbp+var_44], 861h
0x180010d74  mov     [rbp+var_40], esi
0x180010d77  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180010d7e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180010d82  call    _CxxThrowException_0
0x180010d88  mov     rsi, [r14+20h]
0x180010d8c  test    rsi, rsi
0x180010d8f  jz      short loc_180010D9A
0x180010d91  mov     rcx, [rsi+8]; this
0x180010d95  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180010d9a  mov     rdx, r15; lpdwNumberOfBytesAvailable
0x180010d9d  mov     rcx, [r14+10h]; hRequest
0x180010da1  call    cs:__imp_WinHttpQueryDataAvailable
0x180010da7  mov     r14d, eax
0x180010daa  test    rsi, rsi
0x180010dad  jz      short loc_180010DB9
0x180010daf  mov     rcx, [rsi+8]; this
0x180010db3  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180010db8  nop
0x180010db9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010dbd  jz      short loc_180010DC7
0x180010dbf  mov     rcx, rbx; Token
0x180010dc2  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180010dc7  mov     eax, r14d
0x180010dca  mov     rbx, [rsp+80h+arg_8]
0x180010dd2  add     rsp, 80h
0x180010dd9  pop     r15
0x180010ddb  pop     r14
0x180010ddd  pop     rdi
0x180010dde  pop     rsi
0x180010ddf  pop     rbp
0x180010de0  retn
```
