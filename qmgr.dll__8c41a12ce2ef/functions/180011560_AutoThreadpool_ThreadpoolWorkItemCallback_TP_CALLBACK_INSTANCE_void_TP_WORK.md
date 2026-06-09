# AutoThreadpool::ThreadpoolWorkItemCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180011560`
- end: `0x180011755`
- name: `?ThreadpoolWorkItemCallback@AutoThreadpool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `501`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180011560`
- `0x180011760`
- `0x180086674`
- `0x1800959c0`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800115c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800115c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800115e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800115e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800115f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800115f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001166f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001166f`

## string_xrefs

- `0x1800116d0`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall AutoThreadpool::ThreadpoolWorkItemCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WORK Work)
{
  __int64 v4; // rbx
  void **v5; // r14
  void *v6; // r15
  HANDLE CurrentThread; // rax
  const char *v8; // r9
  void *v9; // rdx
  char *v10; // rcx
  __int64 v11; // rdx
  int LastError; // r15d
  void **pExceptionObject; // [rsp+50h] [rbp-88h] BYREF
  __int128 v14; // [rsp+58h] [rbp-80h]
  int v15; // [rsp+68h] [rbp-70h]
  int v16; // [rsp+6Ch] [rbp-6Ch]
  int v17; // [rsp+70h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  void *TokenHandle; // [rsp+F8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_7a43e90641713c5942580354798d2ea8_Traceguids, Work);
  v4 = -1;
  v5 = (void **)(Context + 16);
  v6 = (void *)**((_QWORD **)Context + 2);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) || GetLastError() == 1008 )
  {
    if ( SetThreadToken(0, v6) )
    {
      v4 = (__int64)TokenHandle;
      goto LABEL_7;
    }
    v11 = 454;
  }
  else
  {
    v11 = 450;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v11,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                v8);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  if ( LastError < 0 )
  {
    v14 = 0;
    pExceptionObject = &ComError::`vftable';
    v15 = LastError;
    v16 = 185;
    v17 = 1;
    throw (ComError *)&pExceptionObject;
  }
LABEL_7:
  (*(void (__fastcall **)(_QWORD))Context)(*((_QWORD *)Context + 1));
  if ( v4 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v4, v9);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v5 + 2, 0xFFFFFFFF) == 1 )
  {
    v10 = *(char **)*v5;
    if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v10);
      *(_QWORD *)*v5 = 0;
    }
    operator delete(*v5, 0x10u);
    *v5 = 0;
  }
  operator delete(Context, 0x18u);
}

```

## disassembly

```asm
0x180011560  mov     [rsp+arg_0], rbx
0x180011565  mov     [rsp+arg_8], rdx
0x18001156a  push    rsi
0x18001156b  push    rdi
0x18001156c  push    r12
0x18001156e  push    r14
0x180011570  push    r15
0x180011572  sub     rsp, 0B0h
0x180011579  mov     rdi, rdx
0x18001157c  lea     rax, WPP_GLOBAL_Control
0x180011583  mov     rcx, cs:WPP_GLOBAL_Control
0x18001158a  cmp     rcx, rax
0x18001158d  jz      short loc_180011599
0x18001158f  test    byte ptr [rcx+1Ch], 1
0x180011593  jnz     loc_1800116AE
0x180011599  mov     [rsp+0D8h+var_98], rdi
0x18001159e  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800115a5  mov     rbx, rsi
0x1800115a8  mov     [rsp+0D8h+var_A8], rbx
0x1800115ad  lea     r14, [rdi+10h]
0x1800115b1  mov     [rsp+0D8h+var_A0], r14
0x1800115b6  mov     rax, [r14]
0x1800115b9  mov     r15, [rax]
0x1800115bc  mov     [rsp+0D8h+TokenHandle], 0
0x1800115c8  call    cs:__imp_GetCurrentThread
0x1800115ce  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x1800115d6  mov     edx, 0F01FFh; DesiredAccess
0x1800115db  mov     r8d, 1; OpenAsSelf
0x1800115e1  mov     rcx, rax; ThreadHandle
0x1800115e4  call    cs:__imp_OpenThreadToken
0x1800115ea  test    eax, eax
0x1800115ec  jz      loc_180011695
0x1800115f2  mov     rdx, r15; Token
0x1800115f5  xor     ecx, ecx; Thread
0x1800115f7  call    cs:__imp_SetThreadToken
0x1800115fd  test    eax, eax
0x1800115ff  jz      loc_1800116CB
0x180011605  mov     rbx, [rsp+0D8h+TokenHandle]
0x18001160d  mov     [rsp+0D8h+var_A8], rbx
0x180011612  mov     rcx, [rdi+8]
0x180011616  mov     rax, [rdi]
0x180011619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001161e  nop
0x18001161f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011623  jz      short loc_18001162E
0x180011625  mov     rcx, rbx; Token
0x180011628  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18001162d  nop
0x18001162e  mov     rax, [r14]
0x180011631  lock xadd [rax+8], esi
0x180011636  cmp     esi, 1
0x180011639  jz      short loc_18001165F
0x18001163b  mov     edx, 18h; unsigned __int64
0x180011640  mov     rcx, rdi; void *
0x180011643  mov     rbx, [rsp+0D8h+arg_0]
0x18001164b  add     rsp, 0B0h
0x180011652  pop     r15
0x180011654  pop     r14
0x180011656  pop     r12
0x180011658  pop     rdi
0x180011659  pop     rsi
0x18001165a  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001165f  mov     rax, [r14]
0x180011662  mov     rcx, [rax]; hObject
0x180011665  lea     rax, [rcx-1]
0x180011669  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001166d  ja      short loc_18001167F
0x18001166f  call    cs:__imp_CloseHandle
0x180011675  mov     rax, [r14]
0x180011678  mov     qword ptr [rax], 0
0x18001167f  mov     edx, 10h; unsigned __int64
0x180011684  mov     rcx, [r14]; void *
0x180011687  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001168c  mov     qword ptr [r14], 0
0x180011693  jmp     short loc_18001163B
0x180011695  call    cs:__imp_GetLastError
0x18001169b  nop
0x18001169c  cmp     eax, 3F0h
0x1800116a1  jz      loc_1800115F2
0x1800116a7  mov     edx, 1C2h
0x1800116ac  jmp     short loc_1800116D0
0x1800116ae  mov     edx, 10h
0x1800116b3  mov     r9, r8
0x1800116b6  lea     r8, WPP_7a43e90641713c5942580354798d2ea8_Traceguids
0x1800116bd  mov     rcx, [rcx+10h]
0x1800116c1  call    WPP_SF_q
0x1800116c6  jmp     loc_180011599
0x1800116cb  mov     edx, 1C6h; void *
0x1800116d0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800116d7  mov     rcx, [rsp+0D8h]; this
0x1800116df  lea     r12, [rsp+0D8h+TokenHandle]
0x1800116e7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800116ec  mov     r15d, eax
0x1800116ef  mov     rcx, r12
0x1800116f2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800116f7  test    r15d, r15d
0x1800116fa  jns     loc_180011612
0x180011700  xorps   xmm0, xmm0
0x180011703  movups  [rsp+0D8h+var_80], xmm0
0x180011708  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18001170f  mov     [rsp+0D8h+pExceptionObject], rax
0x180011714  mov     [rsp+0D8h+var_70], r15d
0x180011719  mov     [rsp+0D8h+var_6C], 0B9h
0x180011721  mov     [rsp+0D8h+var_68], 1
0x180011729  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180011730  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180011735  call    _CxxThrowException_0
0x18001173b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180011742  mov     rdi, [rsp+0D8h+arg_8]
0x18001174a  mov     r14, [rsp+0D8h+var_A0]
0x18001174f  jmp     loc_18001162E
```
