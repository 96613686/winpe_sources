# CHttpAgent::_HandleStatusCallback(void *,uint,void *,uint)

- ea: `0x1800cd870`
- end: `0x1800cda48`
- name: `?_HandleStatusCallback@CHttpAgent@@AEAAXPEAXI0I@Z`
- size: `472`
- prototype: `void __usercall(CHttpAgent *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800cacc0`

## callees

- `0x180009ab4`
- `0x1800a1ea4`
- `0x1800ae518`
- `0x1800bd69c`
- `0x1800cd870`
- `0x1800cda50`
- `0x1800cdcb4`
- `0x1800cdfe8`
- `0x1800ce36c`
- `0x1800ce610`
- `0x1800ced5c`
- `0x1800cee88`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cda17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cda17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cd898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cda23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cd898`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cda23`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800cd8a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800cda31`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800cd8a6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800cda31`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cda05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cda05`

## string_xrefs

- `0x1800cd99b`: `CHttpAgent::_HandleStatusCallback`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CHttpAgent::_HandleStatusCallback(
        CHttpAgent *this,
        void *a2,
        int a3,
        const wchar_t *a4,
        unsigned int a5)
{
  char v9; // di
  HANDLE CurrentThread; // rax
  unsigned __int8 *v11; // r8
  int v12; // eax
  unsigned int v13; // r8d
  HANDLE v14; // rax

  v9 = *((_BYTE *)this + 388);
  if ( v9 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadPriority(CurrentThread, 0x10000);
  }
  wil::impersonate_token_nothrow(0);
  switch ( a3 )
  {
    case 0x10:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl'::`2'::impl) )
        CHttpAgent::_OnSendingRequest(this, a2);
      break;
    case 0x20:
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl'::`2'::impl);
      break;
    case 0x800:
      CHttpAgent::_OnRequestClosed(this, a2);
      break;
    case 0x4000:
      CHttpAgent::_OnRedirect(this, a2, a4);
      break;
    case 0x10000:
      LogMessage(
        3u,
        "CHttpAgent::_HandleStatusCallback",
        0x393u,
        "Failed to retrieve the SSL certificate from the server. SSL error flags = %x, request = 0x%p",
        *(_DWORD *)a4,
        a2);
      break;
    case 0x20000:
      CHttpAgent::_OnHeadersAvailable(this, a2);
      break;
    case 0x80000:
      CHttpAgent::_OnReadComplete(this, a2, v11, a5);
      break;
    case 0x200000:
      v12 = *((_DWORD *)a4 + 2);
      if ( v12 )
      {
        v13 = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          v13 = *((_DWORD *)a4 + 2);
      }
      else
      {
        v13 = -2147467259;
      }
      CHttpAgent::_OnError(this, a2, v13);
      break;
    case 0x400000:
      CHttpAgent::_OnSendRequestComplete(this, a2);
      break;
  }
  if ( v9 )
  {
    v14 = GetCurrentThread();
    SetThreadPriority(v14, 0x20000);
  }
}

```

## disassembly

```asm
0x1800cd870  push    rbx
0x1800cd872  push    rbp
0x1800cd873  push    rsi
0x1800cd874  push    rdi
0x1800cd875  push    r14
0x1800cd877  sub     rsp, 40h
0x1800cd87b  mov     r14, r9
0x1800cd87e  mov     ebx, r8d
0x1800cd881  mov     rsi, rdx
0x1800cd884  mov     rbp, rcx
0x1800cd887  mov     dil, [rcx+184h]
0x1800cd88e  mov     [rsp+68h+var_38], dil
0x1800cd893  test    dil, dil
0x1800cd896  jz      short loc_1800CD8AD
0x1800cd898  call    cs:__imp_GetCurrentThread
0x1800cd89e  mov     rcx, rax; hThread
0x1800cd8a1  mov     edx, 10000h; nPriority
0x1800cd8a6  call    cs:__imp_SetThreadPriority
0x1800cd8ac  nop
0x1800cd8ad  mov     [rsp+68h+Token], 0FFFFFFFFFFFFFFFFh
0x1800cd8b6  lea     rdx, [rsp+68h+Token]
0x1800cd8bb  xor     ecx, ecx; Token
0x1800cd8bd  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800cd8c2  cmp     ebx, 10h
0x1800cd8c5  jz      loc_1800CD9D9
0x1800cd8cb  cmp     ebx, 20h ; ' '
0x1800cd8ce  jz      loc_1800CD9CB
0x1800cd8d4  cmp     ebx, 800h
0x1800cd8da  jz      loc_1800CD9BE
0x1800cd8e0  cmp     ebx, 4000h
0x1800cd8e6  jz      loc_1800CD9AE
0x1800cd8ec  cmp     ebx, 10000h
0x1800cd8f2  jz      loc_1800CD982
0x1800cd8f8  cmp     ebx, 20000h
0x1800cd8fe  jz      short loc_1800CD975
0x1800cd900  cmp     ebx, 80000h
0x1800cd906  jz      short loc_1800CD95D
0x1800cd908  cmp     ebx, 200000h
0x1800cd90e  jz      short loc_1800CD92C
0x1800cd910  cmp     ebx, 400000h
0x1800cd916  jnz     loc_1800CD9F5
0x1800cd91c  mov     rdx, rsi; void *
0x1800cd91f  mov     rcx, rbp; this
0x1800cd922  call    ?_OnSendRequestComplete@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_OnSendRequestComplete(void *)
0x1800cd927  jmp     loc_1800CD9F5
0x1800cd92c  mov     eax, [r14+8]
0x1800cd930  test    eax, eax
0x1800cd932  jz      short loc_1800CD947
0x1800cd934  movzx   r8d, ax
0x1800cd938  or      r8d, 80070000h
0x1800cd93f  test    eax, eax
0x1800cd941  cmovle  r8d, eax
0x1800cd945  jmp     short loc_1800CD94D
0x1800cd947  mov     r8d, 80004005h; int
0x1800cd94d  mov     rdx, rsi; void *
0x1800cd950  mov     rcx, rbp; this
0x1800cd953  call    ?_OnError@CHttpAgent@@AEAAXPEAXJ@Z; CHttpAgent::_OnError(void *,long)
0x1800cd958  jmp     loc_1800CD9F5
0x1800cd95d  mov     r9d, [rsp+68h+arg_20]; unsigned int
0x1800cd965  mov     rdx, rsi; void *
0x1800cd968  mov     rcx, rbp; this
0x1800cd96b  call    ?_OnReadComplete@CHttpAgent@@AEAAXPEAXPEAEI@Z; CHttpAgent::_OnReadComplete(void *,uchar *,uint)
0x1800cd970  jmp     loc_1800CD9F5
0x1800cd975  mov     rdx, rsi; void *
0x1800cd978  mov     rcx, rbp; this
0x1800cd97b  call    ?_OnHeadersAvailable@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_OnHeadersAvailable(void *)
0x1800cd980  jmp     short loc_1800CD9F5
0x1800cd982  mov     [rsp+68h+var_40], rsi
0x1800cd987  mov     eax, [r14]
0x1800cd98a  mov     [rsp+68h+var_48], eax
0x1800cd98e  lea     r9, aFailedToRetrie; "Failed to retrieve the SSL certificate "...
0x1800cd995  mov     r8d, 393h; unsigned int
0x1800cd99b  lea     rdx, aChttpagentHand; "CHttpAgent::_HandleStatusCallback"
0x1800cd9a2  mov     ecx, 3; unsigned __int8
0x1800cd9a7  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800cd9ac  jmp     short loc_1800CD9F5
0x1800cd9ae  mov     r8, r14; wchar_t *
0x1800cd9b1  mov     rdx, rsi; void *
0x1800cd9b4  mov     rcx, rbp; this
0x1800cd9b7  call    ?_OnRedirect@CHttpAgent@@AEAAXPEAXPEB_W@Z; CHttpAgent::_OnRedirect(void *,wchar_t const *)
0x1800cd9bc  jmp     short loc_1800CD9F5
0x1800cd9be  mov     rdx, rsi; void *
0x1800cd9c1  mov     rcx, rbp; this
0x1800cd9c4  call    ?_OnRequestClosed@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_OnRequestClosed(void *)
0x1800cd9c9  jmp     short loc_1800CD9F5
0x1800cd9cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CertPinningCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck> `wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl(void)'::`2'::impl
0x1800cd9d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(void)
0x1800cd9d7  jmp     short loc_1800CD9F5
0x1800cd9d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CertPinningCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck> `wil::Feature<__WilFeatureTraits_Feature_CertPinningCheck>::GetImpl(void)'::`2'::impl
0x1800cd9e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CertPinningCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CertPinningCheck>::__private_IsEnabled(void)
0x1800cd9e5  test    al, al
0x1800cd9e7  jz      short loc_1800CD9F5
0x1800cd9e9  mov     rdx, rsi; void *
0x1800cd9ec  mov     rcx, rbp; this
0x1800cd9ef  call    ?_OnSendingRequest@CHttpAgent@@AEAAXPEAX@Z; CHttpAgent::_OnSendingRequest(void *)
0x1800cd9f4  nop
0x1800cd9f5  mov     rbx, [rsp+68h+Token]
0x1800cd9fa  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800cd9fe  jz      short loc_1800CDA1E
0x1800cda00  mov     rdx, rbx; Token
0x1800cda03  xor     ecx, ecx; Thread
0x1800cda05  call    cs:__imp_SetThreadToken
0x1800cda0b  test    eax, eax
0x1800cda0d  jz      short loc_1800CDA42
0x1800cda0f  test    rbx, rbx
0x1800cda12  jz      short loc_1800CDA1E
0x1800cda14  mov     rcx, rbx; hObject
0x1800cda17  call    cs:__imp_CloseHandle
0x1800cda1d  nop
0x1800cda1e  test    dil, dil
0x1800cda21  jz      short loc_1800CDA37
0x1800cda23  call    cs:__imp_GetCurrentThread
0x1800cda29  mov     rcx, rax; hThread
0x1800cda2c  mov     edx, 20000h; nPriority
0x1800cda31  call    cs:__imp_SetThreadPriority
0x1800cda37  add     rsp, 40h
0x1800cda3b  pop     r14
0x1800cda3d  pop     rdi
0x1800cda3e  pop     rsi
0x1800cda3f  pop     rbp
0x1800cda40  pop     rbx
0x1800cda41  retn
0x1800cda42  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
