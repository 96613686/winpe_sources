# CWinHttpRequest::QueryHeader(ulong,ushort const *,void *,ulong *,ulong *)

- ea: `0x1800110a0`
- end: `0x1800113b1`
- name: `?QueryHeader@CWinHttpRequest@@UEAAHKPEBGPEAXPEAK2@Z`
- size: `785`
- prototype: `__int64 __fastcall(CWinHttpRequest *this, signed int, const unsigned __int16 *, void *, unsigned int *lpdwBufferLength, unsigned int *lpdwIndex)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800110a0`
- `0x180011400`
- `0x1800114c0`
- `0x180011760`
- `0x180073b34`
- `0x180086674`
- `0x1800959c0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800df1a4`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001120a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001120a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800110e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800110fa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001111d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001111d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011104`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011233`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011376`
- `WINHTTP!WinHttpQueryHeaders` at `0x180011376`

## string_xrefs

- `0x18001112c`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWinHttpRequest::QueryHeader(
        CWinHttpRequest *this,
        signed int a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned int *lpdwBufferLength,
        unsigned int *lpdwIndex)
{
  __int64 v10; // r13
  __int64 v11; // rbx
  void *v12; // rdi
  HANDLE CurrentThread; // rax
  const char *v14; // r9
  __int64 v15; // rdx
  int LastError; // edi
  const wchar_t *v17; // rsi
  _QWORD *i; // rdi
  const unsigned __int16 *v19; // r8
  DWORD v20; // ecx
  EVENT_LOG *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // eax
  int v25; // eax
  _DWORD *v26; // r11
  __int64 v27; // rdi
  void *v28; // rdx
  unsigned int Headers; // ebp
  void *TokenHandle[2]; // [rsp+30h] [rbp-B8h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-A8h] BYREF
  __int128 v32; // [rsp+48h] [rbp-A0h]
  int v33; // [rsp+58h] [rbp-90h]
  int v34; // [rsp+5Ch] [rbp-8Ch]
  int v35; // [rsp+60h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  __int64 v37; // [rsp+F0h] [rbp+8h] BYREF

  v10 = -1;
  v11 = -1;
  v37 = -1;
  v12 = (void *)**((_QWORD **)this + 1);
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, v12) )
    {
      v11 = (__int64)TokenHandle[0];
      v37 = (__int64)TokenHandle[0];
      goto LABEL_9;
    }
    v15 = 454;
  }
  else
  {
    v15 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v15,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v14);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  if ( LastError < 0 )
  {
    v32 = 0;
    pExceptionObject = &ComError::`vftable';
    v33 = LastError;
    v34 = 525;
    v35 = 1;
    throw (ComError *)&pExceptionObject;
  }
LABEL_9:
  if ( a2 < 0 )
  {
LABEL_44:
    v27 = *((_QWORD *)this + 4);
    if ( v27 )
      ThreadMarker::MarkThread(*(ThreadMarker **)(v27 + 8));
    Headers = WinHttpQueryHeaders(*((HINTERNET *)this + 2), a2, a3, a4, lpdwBufferLength, lpdwIndex);
    if ( v27 )
      ThreadMarker::ClearThreadMarking(*(ThreadMarker **)(v27 + 8));
    if ( v11 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v11, v28);
    return Headers;
  }
  else
  {
    if ( a2 == 0xFFFF )
    {
      v17 = a3;
    }
    else if ( (unsigned __int16)a2 == 5 )
    {
      v17 = L"Content-Length";
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_655a24a015db31ef984e42af7ef631c4_Traceguids,
          (unsigned __int16)a2);
      v17 = &qword_18011AC70;
    }
    for ( i = (_QWORD *)*((_QWORD *)this + 3); ; i = (_QWORD *)i[2] )
    {
      if ( !i )
        goto LABEL_44;
      if ( !(unsigned int)_o__wcsicmp(v17, *i) )
        break;
    }
    v19 = (const unsigned __int16 *)i[1];
    do
      ++v10;
    while ( v19[v10] );
    if ( !v10 )
    {
      v20 = 12150;
LABEL_26:
      SetLastError(v20);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v37);
      return 0;
    }
    if ( (a2 & 0x40000000) != 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_42;
      v23 = 29;
LABEL_35:
      WPP_SF_(*((_QWORD *)v22 + 2), v23, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids);
LABEL_42:
      v20 = 1359;
      goto LABEL_26;
    }
    if ( (a2 & 0x20000000) != 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_42;
      v23 = 30;
      goto LABEL_35;
    }
    v24 = 2 * v10 + 2;
    if ( *lpdwBufferLength < v24 )
    {
      *lpdwBufferLength = v24;
      v20 = 122;
      goto LABEL_26;
    }
    v25 = StringCbCopyW((unsigned __int16 *)a4, *lpdwBufferLength, v19);
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_655a24a015db31ef984e42af7ef631c4_Traceguids,
          (unsigned int)v25);
      goto LABEL_42;
    }
    *v26 = 2 * v10;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v37);
    return 1;
  }
}

```

## disassembly

```asm
0x1800110a0  push    rbx
0x1800110a2  push    rbp
0x1800110a3  push    rsi
0x1800110a4  push    rdi
0x1800110a5  push    r12
0x1800110a7  push    r13
0x1800110a9  push    r14
0x1800110ab  push    r15
0x1800110ad  sub     rsp, 0A8h
0x1800110b4  mov     r12, r9
0x1800110b7  mov     r15, r8
0x1800110ba  mov     ebp, edx
0x1800110bc  mov     r14, rcx
0x1800110bf  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800110c6  mov     rbx, r13
0x1800110c9  mov     [rsp+0E8h+arg_0], rbx
0x1800110d1  mov     rax, [rcx+8]
0x1800110d5  mov     rdi, [rax]
0x1800110d8  mov     [rsp+0E8h+TokenHandle], 0
0x1800110e1  call    cs:__imp_GetCurrentThread
0x1800110e7  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800110ec  mov     edx, 0F01FFh; DesiredAccess
0x1800110f1  mov     r8d, 1; OpenAsSelf
0x1800110f7  mov     rcx, rax; ThreadHandle
0x1800110fa  call    cs:__imp_OpenThreadToken
0x180011100  test    eax, eax
0x180011102  jnz     short loc_180011118
0x180011104  call    cs:__imp_GetLastError
0x18001110a  cmp     eax, 3F0h
0x18001110f  jz      short loc_180011118
0x180011111  mov     edx, 1C2h
0x180011116  jmp     short loc_18001112C
0x180011118  mov     rdx, rdi; Token
0x18001111b  xor     ecx, ecx; Thread
0x18001111d  call    cs:__imp_SetThreadToken
0x180011123  test    eax, eax
0x180011125  jnz     short loc_18001118D
0x180011127  mov     edx, 1C6h; void *
0x18001112c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011133  mov     rcx, [rsp+0E8h]; this
0x18001113b  lea     rsi, [rsp+0E8h+TokenHandle]
0x180011140  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011145  mov     edi, eax
0x180011147  mov     rcx, rsi
0x18001114a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001114f  test    edi, edi
0x180011151  jns     short loc_18001119A
0x180011153  xorps   xmm0, xmm0
0x180011156  movups  [rsp+0E8h+var_A0], xmm0
0x18001115b  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180011162  mov     [rsp+0E8h+pExceptionObject], rax
0x180011167  mov     [rsp+0E8h+var_90], edi
0x18001116b  mov     [rsp+0E8h+var_8C], 20Dh
0x180011173  mov     [rsp+0E8h+var_88], 1
0x18001117b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011182  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180011187  call    _CxxThrowException_0
0x18001118d  mov     rbx, [rsp+0E8h+TokenHandle]
0x180011192  mov     [rsp+0E8h+arg_0], rbx
0x18001119a  test    ebp, ebp
0x18001119c  js      loc_18001133E
0x1800111a2  lea     rax, WPP_GLOBAL_Control
0x1800111a9  cmp     ebp, 0FFFFh
0x1800111af  jz      short loc_1800111F4
0x1800111b1  movzx   r9d, bp
0x1800111b5  cmp     r9d, 5
0x1800111b9  jz      short loc_1800111EB
0x1800111bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111c2  cmp     rcx, rax
0x1800111c5  jz      short loc_1800111E2
0x1800111c7  test    byte ptr [rcx+1Ch], 1
0x1800111cb  jz      short loc_1800111E2
0x1800111cd  mov     edx, 1Ch
0x1800111d2  lea     r8, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x1800111d9  mov     rcx, [rcx+10h]
0x1800111dd  call    WPP_SF_d
0x1800111e2  lea     rsi, qword_18011AC70
0x1800111e9  jmp     short loc_1800111F7
0x1800111eb  lea     rsi, aContentLength; "Content-Length"
0x1800111f2  jmp     short loc_1800111F7
0x1800111f4  mov     rsi, r15
0x1800111f7  mov     rdi, [r14+18h]
0x1800111fb  test    rdi, rdi
0x1800111fe  jz      loc_18001133E
0x180011204  mov     rdx, [rdi]
0x180011207  mov     rcx, rsi
0x18001120a  call    cs:__imp__o__wcsicmp
0x180011210  test    eax, eax
0x180011212  jz      short loc_18001121A
0x180011214  mov     rdi, [rdi+10h]
0x180011218  jmp     short loc_1800111FB
0x18001121a  mov     r8, [rdi+8]; unsigned __int16 *
0x18001121e  inc     r13
0x180011221  cmp     word ptr [r8+r13*2], 0
0x180011227  jnz     short loc_18001121E
0x180011229  test    r13, r13
0x18001122c  jnz     short loc_18001124E
0x18001122e  mov     ecx, 2F76h; dwErrCode
0x180011233  call    cs:__imp_SetLastError
0x180011239  nop
0x18001123a  lea     rcx, [rsp+0E8h+arg_0]
0x180011242  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180011247  xor     eax, eax
0x180011249  jmp     loc_18001139D
0x18001124e  bt      ebp, 1Eh
0x180011252  jnb     short loc_18001127C
0x180011254  mov     rcx, cs:WPP_GLOBAL_Control
0x18001125b  lea     rdx, WPP_GLOBAL_Control
0x180011262  cmp     rcx, rdx
0x180011265  jz      loc_18001131D
0x18001126b  test    byte ptr [rcx+1Ch], 4
0x18001126f  jz      loc_18001131D
0x180011275  mov     edx, 1Dh
0x18001127a  jmp     short loc_1800112A4
0x18001127c  bt      ebp, 1Dh
0x180011280  jnb     short loc_1800112B6
0x180011282  mov     rcx, cs:WPP_GLOBAL_Control
0x180011289  lea     rdx, WPP_GLOBAL_Control
0x180011290  cmp     rcx, rdx
0x180011293  jz      loc_18001131D
0x180011299  test    byte ptr [rcx+1Ch], 4
0x18001129d  jz      short loc_18001131D
0x18001129f  mov     edx, 1Eh
0x1800112a4  lea     r8, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x1800112ab  mov     rcx, [rcx+10h]
0x1800112af  call    WPP_SF_
0x1800112b4  jmp     short loc_18001131D
0x1800112b6  lea     ebx, ds:0[r13*2]
0x1800112be  lea     eax, [rbx+2]
0x1800112c1  mov     r11, [rsp+0E8h+arg_20]
0x1800112c9  mov     ecx, [r11]
0x1800112cc  cmp     ecx, eax
0x1800112ce  jnb     short loc_1800112DD
0x1800112d0  mov     [r11], eax
0x1800112d3  mov     ecx, 7Ah ; 'z'
0x1800112d8  jmp     loc_180011233
0x1800112dd  mov     rdx, rcx; unsigned __int64
0x1800112e0  mov     rcx, r12; unsigned __int16 *
0x1800112e3  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800112e8  test    eax, eax
0x1800112ea  jns     short loc_180011327
0x1800112ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112f3  lea     rdx, WPP_GLOBAL_Control
0x1800112fa  cmp     rcx, rdx
0x1800112fd  jz      short loc_18001131D
0x1800112ff  test    byte ptr [rcx+1Ch], 4
0x180011303  jz      short loc_18001131D
0x180011305  mov     edx, 1Fh
0x18001130a  mov     r9d, eax
0x18001130d  lea     r8, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x180011314  mov     rcx, [rcx+10h]
0x180011318  call    WPP_SF_d
0x18001131d  mov     ecx, 54Fh
0x180011322  jmp     loc_180011233
0x180011327  mov     [r11], ebx
0x18001132a  lea     rcx, [rsp+0E8h+arg_0]
0x180011332  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180011337  mov     eax, 1
0x18001133c  jmp     short loc_18001139D
0x18001133e  mov     rdi, [r14+20h]
0x180011342  test    rdi, rdi
0x180011345  jz      short loc_180011350
0x180011347  mov     rcx, [rdi+8]; this
0x18001134b  call    ?MarkThread@ThreadMarker@@QEAAXXZ; ThreadMarker::MarkThread(void)
0x180011350  mov     rax, [rsp+0E8h+arg_28]
0x180011358  mov     [rsp+0E8h+lpdwIndex], rax; lpdwIndex
0x18001135d  mov     rax, [rsp+0E8h+arg_20]
0x180011365  mov     [rsp+0E8h+lpdwBufferLength], rax; lpdwBufferLength
0x18001136a  mov     r9, r12; lpBuffer
0x18001136d  mov     r8, r15; pwszName
0x180011370  mov     edx, ebp; dwInfoLevel
0x180011372  mov     rcx, [r14+10h]; hRequest
0x180011376  call    cs:__imp_WinHttpQueryHeaders
0x18001137c  mov     ebp, eax
0x18001137e  test    rdi, rdi
0x180011381  jz      short loc_18001138D
0x180011383  mov     rcx, [rdi+8]; this
0x180011387  call    ?ClearThreadMarking@ThreadMarker@@QEAAXXZ; ThreadMarker::ClearThreadMarking(void)
0x18001138c  nop
0x18001138d  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011391  jz      short loc_18001139B
0x180011393  mov     rcx, rbx; Token
0x180011396  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18001139b  mov     eax, ebp
0x18001139d  add     rsp, 0A8h
0x1800113a4  pop     r15
0x1800113a6  pop     r14
0x1800113a8  pop     r13
0x1800113aa  pop     r12
0x1800113ac  pop     rdi
0x1800113ad  pop     rsi
0x1800113ae  pop     rbp
0x1800113af  pop     rbx
0x1800113b0  retn
```
