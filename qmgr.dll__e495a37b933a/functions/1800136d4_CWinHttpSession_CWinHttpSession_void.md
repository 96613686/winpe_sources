# CWinHttpSession::~CWinHttpSession(void)

- ea: `0x1800136d4`
- end: `0x1800138b3`
- name: `??1CWinHttpSession@@UEAA@XZ`
- size: `479`
- prototype: `void __fastcall(CWinHttpSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800de680`

## callees

- `0x180011760`
- `0x1800136d4`
- `0x180014310`
- `0x180086674`
- `0x1800959c0`
- `0x18009e9c8`
- `0x1800ab7fc`
- `0x1800b19d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180013708`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001371f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001371f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001375d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001375d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013881`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001379f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001379f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013823`
- `WINHTTP!WinHttpCloseHandle` at `0x180013785`
- `WINHTTP!WinHttpCloseHandle` at `0x180013832`
- `WINHTTP!WinHttpCloseHandle` at `0x180013785`
- `WINHTTP!WinHttpCloseHandle` at `0x180013832`

## string_xrefs

- `0x180013740`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
void __fastcall CWinHttpSession::~CWinHttpSession(CWinHttpSession *this)
{
  __int64 v2; // rbx
  void *v3; // rsi
  HANDLE CurrentThread; // rax
  const char *v5; // r9
  __int64 v6; // rdx
  void *v7; // rcx
  void *v8; // rdx
  DWORD v9; // esi
  DWORD LastError; // eax
  EVENT_LOG *v11; // rcx
  void *v12; // rcx
  DWORD v13; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF

  TokenHandle = 0;
  *(_QWORD *)this = &CWinHttpSession::`vftable';
  v2 = -1;
  v3 = (void *)**((_QWORD **)this + 1);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v6 = 450;
LABEL_4:
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      v5);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v3) )
  {
    v6 = 454;
    goto LABEL_4;
  }
  v2 = (__int64)TokenHandle;
  TokenHandle = 0;
LABEL_8:
  v7 = (void *)*((_QWORD *)this + 2);
  if ( v7 )
  {
    WinHttpCloseHandle(v7);
    *((_QWORD *)this + 2) = 0;
  }
  v9 = WaitForSingleObjectEx(*((HANDLE *)this + 3), 0x493E0u, 0);
  if ( v9 == -1 )
  {
    LastError = GetLastError();
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, LastError);
LABEL_14:
    v11 = WPP_GLOBAL_Control;
LABEL_15:
    if ( v11 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)v11 + 2), 19, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, this);
    goto LABEL_18;
  }
  if ( !v9 )
    goto LABEL_14;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = GetLastError();
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, this, v9, v13);
  }
LABEL_18:
  if ( v2 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v2, v8);
  CloseHandle(*((HANDLE *)this + 3));
  v12 = (void *)*((_QWORD *)this + 2);
  if ( v12 )
  {
    WinHttpCloseHandle(v12);
    *((_QWORD *)this + 2) = 0;
  }
  TokenHandle::Decrement((CWinHttpSession *)((char *)this + 8));
  *(_QWORD *)this = &IQmgrPersistenceReader::`vftable';
}

```

## disassembly

```asm
0x1800136d4  mov     [rsp+arg_8], rbx
0x1800136d9  mov     [rsp+arg_10], rsi
0x1800136de  push    rdi
0x1800136df  push    r14
0x1800136e1  push    r15
0x1800136e3  sub     rsp, 30h
0x1800136e7  lea     rax, ??_7CWinHttpSession@@6B@; const CWinHttpSession::`vftable'
0x1800136ee  mov     [rsp+48h+TokenHandle], 0
0x1800136f7  mov     [rcx], rax
0x1800136fa  mov     rdi, rcx
0x1800136fd  mov     rax, [rcx+8]
0x180013701  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180013705  mov     rsi, [rax]
0x180013708  call    cs:__imp_GetCurrentThread
0x18001370e  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180013713  mov     edx, 0F01FFh; DesiredAccess
0x180013718  mov     rcx, rax; ThreadHandle
0x18001371b  lea     r8d, [rbx+2]; OpenAsSelf
0x18001371f  call    cs:__imp_OpenThreadToken
0x180013725  test    eax, eax
0x180013727  jnz     short loc_180013758
0x180013729  call    cs:__imp_GetLastError
0x18001372f  cmp     eax, 3F0h
0x180013734  jz      short loc_180013758
0x180013736  mov     edx, 1C2h; void *
0x18001373b  mov     rcx, [rsp+48h]; this
0x180013740  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180013747  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001374c  lea     rcx, [rsp+48h+TokenHandle]
0x180013751  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180013756  jmp     short loc_18001377C
0x180013758  mov     rdx, rsi; Token
0x18001375b  xor     ecx, ecx; Thread
0x18001375d  call    cs:__imp_SetThreadToken
0x180013763  test    eax, eax
0x180013765  jnz     short loc_18001376E
0x180013767  mov     edx, 1C6h
0x18001376c  jmp     short loc_18001373B
0x18001376e  mov     rbx, [rsp+48h+TokenHandle]
0x180013773  mov     [rsp+48h+TokenHandle], 0
0x18001377c  mov     rcx, [rdi+10h]; hInternet
0x180013780  test    rcx, rcx
0x180013783  jz      short loc_180013793
0x180013785  call    cs:__imp_WinHttpCloseHandle
0x18001378b  mov     qword ptr [rdi+10h], 0
0x180013793  mov     rcx, [rdi+18h]; hHandle
0x180013797  xor     r8d, r8d; bAlertable
0x18001379a  mov     edx, 493E0h; dwMilliseconds
0x18001379f  call    cs:__imp_WaitForSingleObjectEx
0x1800137a5  lea     r15, WPP_GLOBAL_Control
0x1800137ac  mov     esi, eax
0x1800137ae  cmp     eax, 0FFFFFFFFh
0x1800137b1  jnz     loc_180013867
0x1800137b7  call    cs:__imp_GetLastError
0x1800137bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137c4  cmp     rcx, r15
0x1800137c7  jz      short loc_180013811
0x1800137c9  test    byte ptr [rcx+1Ch], 4
0x1800137cd  jz      short loc_1800137EE
0x1800137cf  mov     rcx, [rcx+10h]
0x1800137d3  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800137da  mov     edx, 0Ch
0x1800137df  mov     r9d, eax
0x1800137e2  call    WPP_SF_d
0x1800137e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137ee  cmp     rcx, r15
0x1800137f1  jz      short loc_180013811
0x1800137f3  test    byte ptr [rcx+1Ch], 1
0x1800137f7  jz      short loc_180013811
0x1800137f9  mov     rcx, [rcx+10h]
0x1800137fd  lea     r8, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x180013804  mov     edx, 13h
0x180013809  mov     r9, rdi
0x18001380c  call    WPP_SF_q
0x180013811  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180013815  jz      short loc_18001381F
0x180013817  mov     rcx, rbx; Token
0x18001381a  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18001381f  mov     rcx, [rdi+18h]; hObject
0x180013823  call    cs:__imp_CloseHandle
0x180013829  mov     rcx, [rdi+10h]; hInternet
0x18001382d  test    rcx, rcx
0x180013830  jz      short loc_180013840
0x180013832  call    cs:__imp_WinHttpCloseHandle
0x180013838  mov     qword ptr [rdi+10h], 0
0x180013840  lea     rcx, [rdi+8]; this
0x180013844  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180013849  mov     rbx, [rsp+48h+arg_8]
0x18001384e  lea     rax, ??_7IQmgrPersistenceReader@@6B@; const IQmgrPersistenceReader::`vftable'
0x180013855  mov     rsi, [rsp+48h+arg_10]
0x18001385a  mov     [rdi], rax
0x18001385d  add     rsp, 30h
0x180013861  pop     r15
0x180013863  pop     r14
0x180013865  pop     rdi
0x180013866  retn
0x180013867  test    esi, esi
0x180013869  jz      loc_1800137E7
0x18001386f  mov     rax, cs:WPP_GLOBAL_Control
0x180013876  cmp     rax, r15
0x180013879  jz      short loc_180013811
0x18001387b  test    byte ptr [rax+1Ch], 4
0x18001387f  jz      short loc_180013811
0x180013881  call    cs:__imp_GetLastError
0x180013887  mov     rcx, cs:WPP_GLOBAL_Control
0x18001388e  lea     r8, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x180013895  mov     [rsp+48h+var_20], eax
0x180013899  mov     edx, 14h
0x18001389e  mov     r9, rdi
0x1800138a1  mov     [rsp+48h+var_28], esi
0x1800138a5  mov     rcx, [rcx+10h]
0x1800138a9  call    WPP_SF_qDD
0x1800138ae  jmp     loc_180013811
```
