# CWinHttpRequest::SetStatusCallback(void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)

- ea: `0x180012030`
- end: `0x18001216d`
- name: `?SetStatusCallback@CWinHttpRequest@@UEAAP6AXPEAX_KK0K@ZP6AX01K0K@ZK1@Z`
- size: `317`
- prototype: `void (*(CWinHttpRequest *__hidden this, void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int), unsigned int, unsigned __int64))(void *, unsigned __int64, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180012030`
- `0x180086674`
- `0x1800959c0`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001206c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001206c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012084`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180012084`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800120c2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800120c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001208e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001208e`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012130`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180012130`

## string_xrefs

- `0x1800120a0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
WINHTTP_STATUS_CALLBACK __fastcall CWinHttpRequest::SetStatusCallback(CWinHttpRequest *this, void (*a2)(void *, unsigned __int64, unsigned int, void *, unsigned int), DWORD a3, DWORD_PTR a4)
{
  __int64 v8; // rbx
  void *v9; // rdi
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  int LastError; // edi
  __int64 v14; // rsi
  void *v15; // rdx
  WINHTTP_STATUS_CALLBACK v16; // r14
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
    v21 = 2087;
    v22 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v14 = *((_QWORD *)this + 4);
  if ( v14 )
    ThreadMarker::MarkThread(*(ThreadMarker **)(v14 + 8));
  v16 = WinHttpSetStatusCallback(*((HINTERNET *)this + 2), a2, a3, a4);
  if ( v14 )
    ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v14 + 8));
  if ( v8 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v8, v15);
  return v16;
}

```

## disassembly

```asm
0x180012030  push    rbp
0x180012032  push    rbx
0x180012033  push    rsi
0x180012034  push    rdi
0x180012035  push    r12
0x180012037  push    r13
0x180012039  push    r14
0x18001203b  push    r15
0x18001203d  lea     rbp, [rsp-1Fh]
0x180012042  sub     rsp, 98h
0x180012049  mov     r15, r9
0x18001204c  mov     r12d, r8d
0x18001204f  mov     r13, rdx
0x180012052  mov     r14, rcx
0x180012055  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180012059  mov     [rbp+57h+var_B0], rbx
0x18001205d  mov     rax, [rcx+8]
0x180012061  mov     rdi, [rax]
0x180012064  mov     [rbp+57h+TokenHandle], 0
0x18001206c  call    cs:__imp_GetCurrentThread
0x180012072  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180012076  lea     esi, [rbx+2]
0x180012079  mov     r8d, esi; OpenAsSelf
0x18001207c  mov     edx, 0F01FFh; DesiredAccess
0x180012081  mov     rcx, rax; ThreadHandle
0x180012084  call    cs:__imp_OpenThreadToken
0x18001208a  test    eax, eax
0x18001208c  jnz     short loc_1800120BD
0x18001208e  call    cs:__imp_GetLastError
0x180012094  cmp     eax, 3F0h
0x180012099  jz      short loc_1800120BD
0x18001209b  mov     edx, 1C2h; void *
0x1800120a0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800120a7  mov     rcx, [rbp+5Fh]; this
0x1800120ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800120b0  mov     edi, eax
0x1800120b2  lea     rcx, [rbp+57h+TokenHandle]
0x1800120b6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800120bb  jmp     short loc_1800120DD
0x1800120bd  mov     rdx, rdi; Token
0x1800120c0  xor     ecx, ecx; Thread
0x1800120c2  call    cs:__imp_SetThreadToken
0x1800120c8  test    eax, eax
0x1800120ca  jnz     short loc_1800120D3
0x1800120cc  mov     edx, 1C6h
0x1800120d1  jmp     short loc_1800120A0
0x1800120d3  mov     rbx, [rbp+57h+TokenHandle]
0x1800120d7  mov     [rbp+57h+var_B0], rbx
0x1800120db  xor     edi, edi
0x1800120dd  test    edi, edi
0x1800120df  jns     short loc_180012111
0x1800120e1  xorps   xmm0, xmm0
0x1800120e4  movups  [rbp+57h+var_98], xmm0
0x1800120e8  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800120ef  mov     [rbp+57h+pExceptionObject], rax
0x1800120f3  mov     [rbp+57h+var_88], edi
0x1800120f6  mov     [rbp+57h+var_84], 827h
0x1800120fd  mov     [rbp+57h+var_80], esi
0x180012100  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012107  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001210b  call    _CxxThrowException_0
0x180012111  mov     rsi, [r14+20h]
0x180012115  test    rsi, rsi
0x180012118  jz      short loc_180012123
0x18001211a  mov     rcx, [rsi+8]; this
0x18001211e  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180012123  mov     r9, r15; dwReserved
0x180012126  mov     r8d, r12d; dwNotificationFlags
0x180012129  mov     rdx, r13; lpfnInternetCallback
0x18001212c  mov     rcx, [r14+10h]; hInternet
0x180012130  call    cs:__imp_WinHttpSetStatusCallback
0x180012136  mov     r14, rax
0x180012139  test    rsi, rsi
0x18001213c  jz      short loc_180012148
0x18001213e  mov     rcx, [rsi+8]; this
0x180012142  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x180012147  nop
0x180012148  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001214c  jz      short loc_180012156
0x18001214e  mov     rcx, rbx; Token
0x180012151  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180012156  mov     rax, r14
0x180012159  add     rsp, 98h
0x180012160  pop     r15
0x180012162  pop     r14
0x180012164  pop     r13
0x180012166  pop     r12
0x180012168  pop     rdi
0x180012169  pop     rsi
0x18001216a  pop     rbx
0x18001216b  pop     rbp
0x18001216c  retn
```
