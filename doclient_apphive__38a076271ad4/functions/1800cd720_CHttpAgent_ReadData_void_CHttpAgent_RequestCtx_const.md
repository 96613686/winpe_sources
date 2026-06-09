# CHttpAgent::_ReadData(void *,CHttpAgent::RequestCtx const &)

- ea: `0x1800cd720`
- end: `0x1800cd86a`
- name: `?_ReadData@CHttpAgent@@AEAAXPEAXAEBURequestCtx@1@@Z`
- size: `330`
- prototype: `void(CHttpAgent *__hidden this, void *, const struct CHttpAgent::RequestCtx *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800cdfe8`
- `0x1800ce36c`

## callees

- `0x180009ab4`
- `0x1800a1f08`
- `0x1800cd720`
- `0x1800ce610`
- `0x1800cf144`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd7c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd80a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd7c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cd80a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd7aa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd7f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd7aa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cd7f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd77e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd7ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd813`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cd813`
- `WINHTTP!WinHttpReadData` at `0x1800cd774`
- `WINHTTP!WinHttpReadData` at `0x1800cd774`

## string_xrefs

- `0x1800cd83c`: `CHttpAgent::_ReadData`
- `0x1800cd827`: `WinHttpReadData failed for request = 0x%p`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CHttpAgent::_ReadData(CHttpAgent *this, void *a2, const struct CHttpAgent::RequestCtx *a3)
{
  unsigned __int64 v6; // r8
  signed int LastError; // eax
  unsigned int v8; // edi
  __int64 v9; // rbx
  wil::details::in1diag3 *v10; // rcx
  HANDLE v11; // rbx
  DWORD v12; // r14d
  wil::details::in1diag3 *v13; // rcx
  HANDLE Token[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( !*((_BYTE *)a3 + 106) )
  {
    Token[0] = (HANDLE)-1LL;
    CHttpAgent::_ImpersonateUserToken(this, Token);
    v6 = *((_QWORD *)a3 + 11) - *((_QWORD *)a3 + 12);
    if ( v6 > 0x40000 )
      LODWORD(v6) = 0x40000;
    if ( WinHttpReadData(a2, (LPVOID)(*((_QWORD *)a3 + 12) + *((_QWORD *)a3 + 10)), v6, 0) )
      goto LABEL_9;
    LastError = GetLastError();
    if ( LastError )
    {
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v8 = LastError;
    }
    else
    {
      v8 = -2147467259;
    }
    if ( *((_BYTE *)this + 387) )
    {
LABEL_9:
      v9 = (__int64)Token[0];
    }
    else
    {
      v11 = Token[0];
      if ( Token[0] != (HANDLE)-1LL )
      {
        v12 = GetLastError();
        if ( !SetThreadToken(0, v11) )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
        if ( v11 )
          CloseHandle(v11);
        SetLastError(v12);
      }
      v9 = -1;
      Token[0] = (HANDLE)-1LL;
      LogResult(2u, "CHttpAgent::_ReadData", 0x34Cu, v8, "WinHttpReadData failed for request = 0x%p", a2);
      CHttpAgent::_OnError(this, a2, v8);
    }
    if ( v9 != -1 )
    {
      if ( !SetThreadToken(0, (HANDLE)v9) )
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v10);
      if ( v9 )
        CloseHandle((HANDLE)v9);
    }
  }
}

```

## disassembly

```asm
0x1800cd720  push    rbx
0x1800cd722  push    rbp
0x1800cd723  push    rsi
0x1800cd724  push    rdi
0x1800cd725  push    r14
0x1800cd727  sub     rsp, 40h
0x1800cd72b  mov     rbx, r8
0x1800cd72e  mov     rbp, rdx
0x1800cd731  mov     rsi, rcx
0x1800cd734  cmp     byte ptr [r8+6Ah], 0
0x1800cd739  jnz     loc_1800CD7C6
0x1800cd73f  mov     [rsp+68h+Token], 0FFFFFFFFFFFFFFFFh
0x1800cd748  lea     rdx, [rsp+68h+Token]
0x1800cd74d  call    ?_ImpersonateUserToken@CHttpAgent@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@@Z; CHttpAgent::_ImpersonateUserToken(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cd752  mov     r8, [rbx+58h]
0x1800cd756  sub     r8, [rbx+60h]
0x1800cd75a  mov     eax, 40000h
0x1800cd75f  cmp     r8, rax
0x1800cd762  cmova   r8d, eax; dwNumberOfBytesToRead
0x1800cd766  mov     rdx, [rbx+50h]
0x1800cd76a  add     rdx, [rbx+60h]; lpBuffer
0x1800cd76e  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800cd771  mov     rcx, rbp; hRequest
0x1800cd774  call    cs:__imp_WinHttpReadData
0x1800cd77a  test    eax, eax
0x1800cd77c  jnz     short loc_1800CD79A
0x1800cd77e  call    cs:__imp_GetLastError
0x1800cd784  test    eax, eax
0x1800cd786  jz      short loc_1800CD7D1
0x1800cd788  movzx   edi, ax
0x1800cd78b  or      edi, 80070000h
0x1800cd791  test    eax, eax
0x1800cd793  cmovle  edi, eax
0x1800cd796  test    edi, edi
0x1800cd798  js      short loc_1800CD7D6
0x1800cd79a  mov     rbx, [rsp+68h+Token]
0x1800cd79f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd7a3  jz      short loc_1800CD7C6
0x1800cd7a5  mov     rdx, rbx; Token
0x1800cd7a8  xor     ecx, ecx; Thread
0x1800cd7aa  call    cs:__imp_SetThreadToken
0x1800cd7b0  test    eax, eax
0x1800cd7b2  jz      loc_1800CD864
0x1800cd7b8  test    rbx, rbx
0x1800cd7bb  jz      short loc_1800CD7C6
0x1800cd7bd  mov     rcx, rbx; hObject
0x1800cd7c0  call    cs:__imp_CloseHandle
0x1800cd7c6  add     rsp, 40h
0x1800cd7ca  pop     r14
0x1800cd7cc  pop     rdi
0x1800cd7cd  pop     rsi
0x1800cd7ce  pop     rbp
0x1800cd7cf  pop     rbx
0x1800cd7d0  retn
0x1800cd7d1  mov     edi, 80004005h
0x1800cd7d6  cmp     byte ptr [rsi+183h], 0
0x1800cd7dd  jnz     short loc_1800CD79A
0x1800cd7df  mov     rbx, [rsp+68h+Token]
0x1800cd7e4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd7e8  jz      short loc_1800CD819
0x1800cd7ea  call    cs:__imp_GetLastError
0x1800cd7f0  mov     r14d, eax
0x1800cd7f3  mov     rdx, rbx; Token
0x1800cd7f6  xor     ecx, ecx; Thread
0x1800cd7f8  call    cs:__imp_SetThreadToken
0x1800cd7fe  test    eax, eax
0x1800cd800  jz      short loc_1800CD85E
0x1800cd802  test    rbx, rbx
0x1800cd805  jz      short loc_1800CD810
0x1800cd807  mov     rcx, rbx; hObject
0x1800cd80a  call    cs:__imp_CloseHandle
0x1800cd810  mov     ecx, r14d; dwErrCode
0x1800cd813  call    cs:__imp_SetLastError
0x1800cd819  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd81d  mov     [rsp+68h+Token], rbx
0x1800cd822  mov     [rsp+68h+var_40], rbp
0x1800cd827  lea     rax, aWinhttpreaddat_0; "WinHttpReadData failed for request = 0x"...
0x1800cd82e  mov     [rsp+68h+var_48], rax; char *
0x1800cd833  mov     r9d, edi; int
0x1800cd836  mov     r8d, 34Ch; unsigned int
0x1800cd83c  lea     rdx, aChttpagentRead; "CHttpAgent::_ReadData"
0x1800cd843  lea     ecx, [rbx+3]; unsigned __int8
0x1800cd846  call    ?LogResult@@YAXEPEBDIJ0ZZ; LogResult(uchar,char const *,uint,long,char const *,...)
0x1800cd84b  mov     r8d, edi; int
0x1800cd84e  mov     rdx, rbp; void *
0x1800cd851  mov     rcx, rsi; this
0x1800cd854  call    ?_OnError@CHttpAgent@@AEAAXPEAXJ@Z; CHttpAgent::_OnError(void *,long)
0x1800cd859  jmp     loc_1800CD79F
0x1800cd85e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800cd864  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
