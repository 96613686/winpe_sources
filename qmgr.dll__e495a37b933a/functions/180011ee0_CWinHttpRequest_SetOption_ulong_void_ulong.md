# CWinHttpRequest::SetOption(ulong,void *,ulong)

- ea: `0x180011ee0`
- end: `0x18001201d`
- name: `?SetOption@CWinHttpRequest@@UEAAHKPEAXK@Z`
- size: `317`
- prototype: `int(CWinHttpRequest *__hidden this, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180011ee0`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011f1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011f1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011f34`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011f34`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011f72`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011f72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f3e`
- `WINHTTP!WinHttpSetOption` at `0x180011fe0`
- `WINHTTP!WinHttpSetOption` at `0x180011fe0`

## string_xrefs

- `0x180011f50`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall CWinHttpRequest::SetOption(CWinHttpRequest *this, DWORD a2, void *a3, DWORD a4)
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
    v21 = 2056;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v14 + 8));
  v16 = WinHttpSetOption(*((HINTERNET *)this + 2), a2, a3, a4);
  if ( v14 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v14 + 8));
  if ( v8 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v8, v15);
  return v16;
}

```

## disassembly

```asm
0x180011ee0  push    rbp
0x180011ee2  push    rbx
0x180011ee3  push    rsi
0x180011ee4  push    rdi
0x180011ee5  push    r12
0x180011ee7  push    r13
0x180011ee9  push    r14
0x180011eeb  push    r15
0x180011eed  lea     rbp, [rsp-1Fh]
0x180011ef2  sub     rsp, 98h
0x180011ef9  mov     r15d, r9d
0x180011efc  mov     r12, r8
0x180011eff  mov     r13d, edx
0x180011f02  mov     r14, rcx
0x180011f05  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180011f09  mov     [rbp+57h+var_B0], rbx
0x180011f0d  mov     rax, [rcx+8]
0x180011f11  mov     rdi, [rax]
0x180011f14  mov     [rbp+57h+TokenHandle], 0
0x180011f1c  call    cs:__imp_GetCurrentThread
0x180011f22  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180011f26  lea     esi, [rbx+2]
0x180011f29  mov     r8d, esi; OpenAsSelf
0x180011f2c  mov     edx, 0F01FFh; DesiredAccess
0x180011f31  mov     rcx, rax; ThreadHandle
0x180011f34  call    cs:__imp_OpenThreadToken
0x180011f3a  test    eax, eax
0x180011f3c  jnz     short loc_180011F6D
0x180011f3e  call    cs:__imp_GetLastError
0x180011f44  cmp     eax, 3F0h
0x180011f49  jz      short loc_180011F6D
0x180011f4b  mov     edx, 1C2h; void *
0x180011f50  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011f57  mov     rcx, [rbp+5Fh]; this
0x180011f5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011f60  mov     edi, eax
0x180011f62  lea     rcx, [rbp+57h+TokenHandle]
0x180011f66  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180011f6b  jmp     short loc_180011F8D
0x180011f6d  mov     rdx, rdi; Token
0x180011f70  xor     ecx, ecx; Thread
0x180011f72  call    cs:__imp_SetThreadToken
0x180011f78  test    eax, eax
0x180011f7a  jnz     short loc_180011F83
0x180011f7c  mov     edx, 1C6h
0x180011f81  jmp     short loc_180011F50
0x180011f83  mov     rbx, [rbp+57h+TokenHandle]
0x180011f87  mov     [rbp+57h+var_B0], rbx
0x180011f8b  xor     edi, edi
0x180011f8d  test    edi, edi
0x180011f8f  jns     short loc_180011FC1
0x180011f91  xorps   xmm0, xmm0
0x180011f94  movups  [rbp+57h+var_98], xmm0
0x180011f98  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180011f9f  mov     [rbp+57h+pExceptionObject], rax
0x180011fa3  mov     [rbp+57h+var_88], edi
0x180011fa6  mov     [rbp+57h+var_84], 808h
0x180011fad  mov     [rbp+57h+var_80], esi
0x180011fb0  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011fb7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180011fbb  call    _CxxThrowException_0
0x180011fc1  mov     rsi, [r14+20h]
0x180011fc5  test    rsi, rsi
0x180011fc8  jz      short loc_180011FD3
0x180011fca  mov     rcx, [rsi+8]; this
0x180011fce  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180011fd3  mov     r9d, r15d; dwBufferLength
0x180011fd6  mov     r8, r12; lpBuffer
0x180011fd9  mov     edx, r13d; dwOption
0x180011fdc  mov     rcx, [r14+10h]; hInternet
0x180011fe0  call    cs:__imp_WinHttpSetOption
0x180011fe6  mov     r14d, eax
0x180011fe9  test    rsi, rsi
0x180011fec  jz      short loc_180011FF8
0x180011fee  mov     rcx, [rsi+8]; this
0x180011ff2  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180011ff7  nop
0x180011ff8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011ffc  jz      short loc_180012006
0x180011ffe  mov     rcx, rbx; Token
0x180012001  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180012006  mov     eax, r14d
0x180012009  add     rsp, 98h
0x180012010  pop     r15
0x180012012  pop     r14
0x180012014  pop     r13
0x180012016  pop     r12
0x180012018  pop     rdi
0x180012019  pop     rsi
0x18001201a  pop     rbx
0x18001201b  pop     rbp
0x18001201c  retn
```
