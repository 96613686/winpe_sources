# CWinHttpConnection::OpenRequest(ushort const *,ushort const *,ushort const *,ushort const *,ushort const * *,ulong)

- ea: `0x1800118f0`
- end: `0x180011bda`
- name: `?OpenRequest@CWinHttpConnection@@UEAAPEAVIHttpRequest@@PEBG000PEAPEBGK@Z`
- size: `746`
- prototype: `struct IHttpRequest *(CWinHttpConnection *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006640`
- `0x18000e370`
- `0x180011760`
- `0x1800118f0`
- `0x180014310`
- `0x180086674`
- `0x1800959c0`
- `0x18009e9c8`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011a79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011931`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011931`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011947`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011947`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011985`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b8f`
- `WINHTTP!WinHttpOpenRequest` at `0x1800119fe`
- `WINHTTP!WinHttpOpenRequest` at `0x1800119fe`

## string_xrefs

- `0x180011963`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IHttpRequest *__fastcall CWinHttpConnection::OpenRequest(
        CWinHttpConnection *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *pwszReferrer,
        const unsigned __int16 **ppwszAcceptTypes,
        DWORD dwFlags)
{
  __int64 v11; // rbx
  void *v12; // rdi
  HANDLE CurrentThread; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  int LastError; // edi
  HINTERNET v17; // r14
  unsigned int v18; // ecx
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  volatile signed __int32 **v21; // rsi
  _DWORD *v22; // rax
  volatile signed __int32 **v23; // r14
  _QWORD *v24; // rdx
  volatile signed __int32 *v25; // rax
  void *v26; // rcx
  void **pExceptionObject; // [rsp+50h] [rbp-51h] BYREF
  __int128 v29; // [rsp+58h] [rbp-49h]
  int v30; // [rsp+68h] [rbp-39h]
  int v31; // [rsp+6Ch] [rbp-35h]
  int v32; // [rsp+70h] [rbp-31h]
  _QWORD *v33; // [rsp+B0h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+47h]
  void *TokenHandle; // [rsp+F0h] [rbp+4Fh] BYREF

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
    v29 = 0;
    pExceptionObject = &ComError::`vftable';
    v30 = LastError;
    v31 = 2295;
    v32 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v17 = WinHttpOpenRequest(*((HINTERNET *)this + 2), a2, a3, a4, pwszReferrer, ppwszAcceptTypes, dwFlags);
  if ( !v17 )
  {
    if ( (int)GetLastError() > 0 )
      v18 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v18 = GetLastError();
    v29 = 0;
    pExceptionObject = &ComError::`vftable';
    v30 = v18;
    v31 = 2307;
    v32 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v19 = HeapAlloc(hBitsHeap, 8u, 0x28u);
  v20 = v19;
  if ( !v19 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 40);
    v29 = 0;
    pExceptionObject = &ComError::`vftable';
    v30 = -2147024882;
    v31 = 0;
    v32 = 1;
    throw (ComError *)&pExceptionObject;
  }
  v33 = v19;
  *v19 = &CWinHttpRequest::`vftable';
  v21 = (volatile signed __int32 **)(v19 + 1);
  v22 = operator new(0x10u);
  v20[1] = v22;
  v22[2] = 1;
  *(_QWORD *)v20[1] = 0;
  v20[2] = v17;
  v20[3] = 0;
  v20[4] = 0;
  v23 = (volatile signed __int32 **)CopyThreadToken(&TokenHandle);
  v24 = (_QWORD *)v20[1];
  if ( *v24 != *(_QWORD *)*v23 )
  {
    TokenHandle::Decrement((TokenHandle *)(v20 + 1));
    v25 = *v23;
    *v21 = *v23;
    _InterlockedIncrement(v25 + 2);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)TokenHandle + 2, 0xFFFFFFFF) == 1 )
  {
    v26 = TokenHandle;
    if ( (unsigned __int64)(*(_QWORD *)TokenHandle - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)TokenHandle);
      *(_QWORD *)TokenHandle = 0;
      v26 = TokenHandle;
    }
    operator delete(v26, 0x10u);
  }
  if ( v11 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v11, v24);
  return (struct IHttpRequest *)v20;
}

```

## disassembly

```asm
0x1800118f0  mov     [rsp-8+arg_8], rbx
0x1800118f5  mov     [rsp-8+arg_10], rsi
0x1800118fa  push    rbp
0x1800118fb  push    rdi
0x1800118fc  push    r12
0x1800118fe  push    r14
0x180011900  push    r15
0x180011902  lea     rbp, [rsp-1Fh]
0x180011907  sub     rsp, 0C0h
0x18001190e  mov     r14, r9
0x180011911  mov     r15, r8
0x180011914  mov     r12, rdx
0x180011917  mov     rsi, rcx
0x18001191a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001191e  mov     [rbp+3Fh+var_A0], rbx
0x180011922  mov     rax, [rcx+8]
0x180011926  mov     rdi, [rax]
0x180011929  mov     [rbp+3Fh+TokenHandle], 0
0x180011931  call    cs:__imp_GetCurrentThread
0x180011937  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x18001193b  mov     edx, 0F01FFh; DesiredAccess
0x180011940  lea     r8d, [rbx+2]; OpenAsSelf
0x180011944  mov     rcx, rax; ThreadHandle
0x180011947  call    cs:__imp_OpenThreadToken
0x18001194d  test    eax, eax
0x18001194f  jnz     short loc_180011980
0x180011951  call    cs:__imp_GetLastError
0x180011957  cmp     eax, 3F0h
0x18001195c  jz      short loc_180011980
0x18001195e  mov     edx, 1C2h; void *
0x180011963  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001196a  mov     rcx, [rbp+47h]; this
0x18001196e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011973  mov     edi, eax
0x180011975  lea     rcx, [rbp+3Fh+TokenHandle]
0x180011979  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001197e  jmp     short loc_1800119A0
0x180011980  mov     rdx, rdi; Token
0x180011983  xor     ecx, ecx; Thread
0x180011985  call    cs:__imp_SetThreadToken
0x18001198b  test    eax, eax
0x18001198d  jnz     short loc_180011996
0x18001198f  mov     edx, 1C6h
0x180011994  jmp     short loc_180011963
0x180011996  mov     rbx, [rbp+3Fh+TokenHandle]
0x18001199a  mov     [rbp+3Fh+var_A0], rbx
0x18001199e  xor     edi, edi
0x1800119a0  test    edi, edi
0x1800119a2  jns     short loc_1800119D8
0x1800119a4  xorps   xmm0, xmm0
0x1800119a7  movups  [rbp+3Fh+var_88], xmm0
0x1800119ab  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800119b2  mov     [rbp+3Fh+pExceptionObject], rax
0x1800119b6  mov     [rbp+3Fh+var_78], edi
0x1800119b9  mov     [rbp+3Fh+var_74], 8F7h
0x1800119c0  mov     [rbp+3Fh+var_70], 1
0x1800119c7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800119ce  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x1800119d2  call    _CxxThrowException_0
0x1800119d8  mov     eax, [rbp+3Fh+arg_30]
0x1800119db  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x1800119df  mov     rax, [rbp+3Fh+arg_28]
0x1800119e3  mov     [rsp+0E0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1800119e8  mov     rax, [rbp+3Fh+arg_20]
0x1800119ec  mov     [rsp+0E0h+pwszReferrer], rax; pwszReferrer
0x1800119f1  mov     r9, r14; pwszVersion
0x1800119f4  mov     r8, r15; pwszObjectName
0x1800119f7  mov     rdx, r12; pwszVerb
0x1800119fa  mov     rcx, [rsi+10h]; hConnect
0x1800119fe  call    cs:__imp_WinHttpOpenRequest
0x180011a04  mov     r14, rax
0x180011a07  mov     [rbp+3Fh+var_98], rax
0x180011a0b  test    rax, rax
0x180011a0e  jnz     short loc_180011A67
0x180011a10  call    cs:__imp_GetLastError
0x180011a16  test    eax, eax
0x180011a18  jg      short loc_180011A24
0x180011a1a  call    cs:__imp_GetLastError
0x180011a20  mov     ecx, eax
0x180011a22  jmp     short loc_180011A33
0x180011a24  call    cs:__imp_GetLastError
0x180011a2a  movzx   ecx, ax
0x180011a2d  or      ecx, 80070000h
0x180011a33  xorps   xmm0, xmm0
0x180011a36  movups  [rbp+3Fh+var_88], xmm0
0x180011a3a  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180011a41  mov     [rbp+3Fh+pExceptionObject], rax
0x180011a45  mov     [rbp+3Fh+var_78], ecx
0x180011a48  mov     [rbp+3Fh+var_74], 903h
0x180011a4f  mov     [rbp+3Fh+var_70], 1
0x180011a56  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011a5d  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180011a61  call    _CxxThrowException_0
0x180011a67  mov     esi, 28h ; '('
0x180011a6c  mov     r8d, esi; dwBytes
0x180011a6f  lea     edx, [rsi-20h]; dwFlags
0x180011a72  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180011a79  call    cs:__imp_HeapAlloc
0x180011a7f  mov     rdi, rax
0x180011a82  test    rax, rax
0x180011a85  jnz     short loc_180011AEE
0x180011a87  lea     rax, WPP_GLOBAL_Control
0x180011a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a95  cmp     rcx, rax
0x180011a98  jz      short loc_180011AB6
0x180011a9a  test    byte ptr [rcx+1Ch], 4
0x180011a9e  jz      short loc_180011AB6
0x180011aa0  lea     edx, [rsi-1Eh]
0x180011aa3  mov     r9d, esi
0x180011aa6  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180011aad  mov     rcx, [rcx+10h]
0x180011ab1  call    WPP_SF_d
0x180011ab6  xorps   xmm0, xmm0
0x180011ab9  movups  [rbp+3Fh+var_88], xmm0
0x180011abd  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180011ac4  mov     [rbp+3Fh+pExceptionObject], rax
0x180011ac8  mov     [rbp+3Fh+var_78], 8007000Eh
0x180011acf  mov     [rbp+3Fh+var_74], 0
0x180011ad6  mov     [rbp+3Fh+var_70], 1
0x180011add  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011ae4  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180011ae8  call    _CxxThrowException_0
0x180011aee  mov     [rbp+3Fh+var_30], rdi
0x180011af2  lea     rax, ??_7CWinHttpRequest@@6B@; const CWinHttpRequest::`vftable'
0x180011af9  mov     [rdi], rax
0x180011afc  lea     rsi, [rdi+8]
0x180011b00  mov     r15d, 10h
0x180011b06  mov     ecx, r15d; dwBytes
0x180011b09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b0e  mov     [rsi], rax
0x180011b11  mov     dword ptr [rax+8], 1
0x180011b18  mov     rax, [rsi]
0x180011b1b  mov     qword ptr [rax], 0
0x180011b22  mov     [rbp+3Fh+var_98], 0
0x180011b2a  mov     [rdi+10h], r14
0x180011b2e  mov     qword ptr [rdi+18h], 0
0x180011b36  mov     qword ptr [rdi+20h], 0
0x180011b3e  lea     rcx, [rbp+3Fh+TokenHandle]
0x180011b42  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x180011b47  mov     r14, rax
0x180011b4a  mov     rcx, [rax]
0x180011b4d  mov     rdx, [rsi]
0x180011b50  mov     rcx, [rcx]
0x180011b53  cmp     [rdx], rcx
0x180011b56  jz      short loc_180011B6A
0x180011b58  mov     rcx, rsi; this
0x180011b5b  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x180011b60  mov     rax, [r14]
0x180011b63  mov     [rsi], rax
0x180011b66  lock inc dword ptr [rax+8]
0x180011b6a  mov     rcx, [rbp+3Fh+TokenHandle]
0x180011b6e  or      eax, 0FFFFFFFFh
0x180011b71  lock xadd [rcx+8], eax
0x180011b76  cmp     eax, 1
0x180011b79  jnz     short loc_180011BAD
0x180011b7b  mov     rcx, [rbp+3Fh+TokenHandle]
0x180011b7f  mov     r8, [rcx]
0x180011b82  lea     rax, [r8-1]
0x180011b86  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180011b8a  ja      short loc_180011BA4
0x180011b8c  mov     rcx, r8; hObject
0x180011b8f  call    cs:__imp_CloseHandle
0x180011b95  mov     rax, [rbp+3Fh+TokenHandle]
0x180011b99  mov     qword ptr [rax], 0
0x180011ba0  mov     rcx, [rbp+3Fh+TokenHandle]; void *
0x180011ba4  mov     rdx, r15; unsigned __int64
0x180011ba7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011bac  nop
0x180011bad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011bb1  jz      short loc_180011BBB
0x180011bb3  mov     rcx, rbx; Token
0x180011bb6  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180011bbb  mov     rax, rdi
0x180011bbe  lea     r11, [rsp+0E0h+var_20]
0x180011bc6  mov     rbx, [r11+38h]
0x180011bca  mov     rsi, [r11+40h]
0x180011bce  mov     rsp, r11
0x180011bd1  pop     r15
0x180011bd3  pop     r14
0x180011bd5  pop     r12
0x180011bd7  pop     rdi
0x180011bd8  pop     rbp
0x180011bd9  retn
```
