# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x18005a314`
- end: `0x18005a578`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b560`

## callees

- `0x180004f70`
- `0x18000ae88`
- `0x1800599ac`
- `0x180059b10`
- `0x18005a314`
- `0x18005a9dc`
- `0x1800cd010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005a46f`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005a46f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a4e5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a506`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a4e5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18005a506`
- `msvcp_win!_Mtx_lock` at `0x18005a4d0`
- `msvcp_win!_Mtx_lock` at `0x18005a4d0`
- `msvcp_win!_Mtx_unlock` at `0x18005a51e`
- `msvcp_win!_Mtx_unlock` at `0x18005a533`
- `msvcp_win!_Mtx_unlock` at `0x18005a51e`
- `msvcp_win!_Mtx_unlock` at `0x18005a533`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a459`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a459`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a48e`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18005a48e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  _BYTE *v8; // rcx
  char v9; // si
  _BYTE *v10; // rdx
  struct _Mtx_internal_imp_t *v11; // rcx
  _QWORD v12[7]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp-88h]
  _BYTE v14[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v15; // [rsp+B8h] [rbp-48h]
  _BYTE v16[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v17; // [rsp+F8h] [rbp-8h]

  v2 = *(_QWORD *)(a1 + 8);
  v12[0] = off_1800CF7B0;
  v12[1] = *(_QWORD *)(a1 + 24);
  v13 = v12;
  v17 = 0;
  v17 = (_BYTE *)std::_Func_impl_no_alloc__lambda_ae79b6a25084f623882ea33371aa944e__void_::_Move(v12, v16);
  v15 = 0;
  v3 = operator new(0x48u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v3[8] = 0;
  v4 = v17;
  if ( v17 )
  {
    v3[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v17)(v17, v3 + 1);
    v4 = v17;
  }
  v15 = v3;
  if ( v4 )
  {
    v5 = v16;
    LOBYTE(v5) = v4 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 32LL))(v4, v5);
    v17 = 0;
  }
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v6);
    v13 = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 352LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v8 = v15;
  if ( !v15 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 16LL))(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v15 )
  {
    v10 = v14;
    LOBYTE(v10) = v15 != v14;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v15 + 32LL))(v15, v10);
    v15 = 0;
  }
  *(_BYTE *)(v2 + 368) = v9;
  if ( _Mtx_lock((_Mtx_t)(v2 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v2 + 108) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 108) = 2147483646;
    std::_Throw_Cpp_error(6);
    __debugbreak();
  }
  v11 = (struct _Mtx_internal_imp_t *)(v2 + 32);
  if ( *(_DWORD *)(v2 + 8) == 4 )
  {
    _Mtx_unlock(v11);
  }
  else
  {
    *(_DWORD *)(v2 + 8) = 3;
    _Mtx_unlock(v11);
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(v2 + 136));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x18005a314  mov     [rsp-8+arg_8], rbx
0x18005a319  mov     [rsp-8+arg_10], rsi
0x18005a31e  push    rbp
0x18005a31f  push    rdi
0x18005a320  push    r14
0x18005a322  lea     rbp, [rsp-10h]
0x18005a327  sub     rsp, 110h
0x18005a32e  mov     rax, cs:__security_cookie
0x18005a335  xor     rax, rsp
0x18005a338  mov     [rbp+20h+var_20], rax
0x18005a33c  mov     r14, rcx
0x18005a33f  mov     rdi, [rcx+8]
0x18005a343  lea     rax, [rbp+20h+var_A0]
0x18005a347  mov     [rsp+120h+var_F8], rax
0x18005a34c  lea     rax, off_1800CF7B0
0x18005a353  mov     [rsp+120h+var_E0], rax
0x18005a358  mov     rax, [rcx+18h]
0x18005a35c  mov     [rsp+120h+var_D8], rax
0x18005a361  lea     rax, [rsp+120h+var_E0]
0x18005a366  mov     [rsp+120h+var_A8], rax
0x18005a36b  lea     rax, [rsp+120h+var_E0]
0x18005a370  mov     [rsp+120h+var_F0], rax
0x18005a375  lea     rax, [rbp+20h+var_60]
0x18005a379  mov     [rsp+120h+var_100], rax
0x18005a37e  mov     [rbp+20h+var_28], 0
0x18005a386  lea     rdx, [rbp+20h+var_60]
0x18005a38a  lea     rcx, [rsp+120h+var_E0]
0x18005a38f  call    std___Func_impl_no_alloc__lambda_ae79b6a25084f623882ea33371aa944e__void____Move
0x18005a394  mov     [rbp+20h+var_28], rax
0x18005a398  mov     [rbp+20h+var_68], 0
0x18005a3a0  mov     ecx, 48h ; 'H'; Size
0x18005a3a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a3aa  mov     rbx, rax
0x18005a3ad  mov     [rsp+120h+var_100], rax
0x18005a3b2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x18005a3b9  mov     [rbx], rax
0x18005a3bc  lea     rsi, [rbx+8]
0x18005a3c0  mov     [rsp+120h+var_E8], rsi
0x18005a3c5  mov     qword ptr [rsi+38h], 0
0x18005a3cd  mov     rcx, [rbp+20h+var_28]
0x18005a3d1  test    rcx, rcx
0x18005a3d4  jz      short loc_18005A3EC
0x18005a3d6  mov     rax, [rcx]
0x18005a3d9  mov     rdx, rsi
0x18005a3dc  mov     rax, [rax]
0x18005a3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3e4  mov     [rsi+38h], rax
0x18005a3e8  mov     rcx, [rbp+20h+var_28]
0x18005a3ec  mov     [rbp+20h+var_68], rbx
0x18005a3f0  test    rcx, rcx
0x18005a3f3  jz      short loc_18005A413
0x18005a3f5  mov     rax, [rcx]
0x18005a3f8  lea     rdx, [rbp+20h+var_60]
0x18005a3fc  cmp     rcx, rdx
0x18005a3ff  setnz   dl
0x18005a402  mov     rax, [rax+20h]
0x18005a406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a40b  mov     [rbp+20h+var_28], 0
0x18005a413  mov     rcx, [rsp+120h+var_A8]
0x18005a418  test    rcx, rcx
0x18005a41b  jz      short loc_18005A43D
0x18005a41d  mov     rax, [rcx]
0x18005a420  lea     rdx, [rsp+120h+var_E0]
0x18005a425  cmp     rcx, rdx
0x18005a428  setnz   dl
0x18005a42b  mov     rax, [rax+20h]
0x18005a42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a434  mov     [rsp+120h+var_A8], 0
0x18005a43d  lea     rax, [rbp+20h+var_A0]
0x18005a441  mov     [rsp+120h+var_E8], rax
0x18005a446  mov     rbx, [r14+8]
0x18005a44a  add     rbx, 160h
0x18005a451  mov     [rsp+120h+var_100], rbx
0x18005a456  mov     rcx, rbx
0x18005a459  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x18005a460  nop     dword ptr [rax+rax+00h]
0x18005a465  nop
0x18005a466  mov     rcx, [rbp+20h+var_68]
0x18005a46a  test    rcx, rcx
0x18005a46d  jnz     short loc_18005A47C
0x18005a46f  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005a476  nop     dword ptr [rax+rax+00h]
0x18005a47b  int     3; Trap to Debugger
0x18005a47c  mov     rax, [rcx]
0x18005a47f  mov     rax, [rax+10h]
0x18005a483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a488  mov     sil, al
0x18005a48b  mov     rcx, rbx
0x18005a48e  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18005a495  nop     dword ptr [rax+rax+00h]
0x18005a49a  nop
0x18005a49b  mov     rcx, [rbp+20h+var_68]
0x18005a49f  test    rcx, rcx
0x18005a4a2  jz      short loc_18005A4C2
0x18005a4a4  mov     rdx, [rcx]
0x18005a4a7  mov     rax, [rdx+20h]
0x18005a4ab  lea     rdx, [rbp+20h+var_A0]
0x18005a4af  cmp     rcx, rdx
0x18005a4b2  setnz   dl
0x18005a4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4ba  mov     [rbp+20h+var_68], 0
0x18005a4c2  mov     [rdi+170h], sil
0x18005a4c9  lea     rbx, [rdi+20h]
0x18005a4cd  mov     rcx, rbx; _Mtx_t
0x18005a4d0  call    cs:__imp__Mtx_lock
0x18005a4d7  nop     dword ptr [rax+rax+00h]
0x18005a4dc  test    eax, eax
0x18005a4de  jz      short loc_18005A4F2
0x18005a4e0  mov     ecx, 5
0x18005a4e5  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005a4ec  nop     dword ptr [rax+rax+00h]
0x18005a4f1  int     3; Trap to Debugger
0x18005a4f2  mov     eax, [rbx+4Ch]
0x18005a4f5  cmp     eax, 7FFFFFFFh
0x18005a4fa  jnz     short loc_18005A513
0x18005a4fc  dec     eax
0x18005a4fe  mov     [rbx+4Ch], eax
0x18005a501  mov     ecx, 6
0x18005a506  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18005a50d  nop     dword ptr [rax+rax+00h]
0x18005a512  int     3; Trap to Debugger
0x18005a513  mov     eax, [rdi+8]
0x18005a516  mov     rcx, rbx; _Mtx_t
0x18005a519  cmp     eax, 4
0x18005a51c  jnz     short loc_18005A52C
0x18005a51e  call    cs:__imp__Mtx_unlock
0x18005a525  nop     dword ptr [rax+rax+00h]
0x18005a52a  jmp     short loc_18005A553
0x18005a52c  mov     dword ptr [rdi+8], 3
0x18005a533  call    cs:__imp__Mtx_unlock
0x18005a53a  nop     dword ptr [rax+rax+00h]
0x18005a53f  lea     rcx, [rdi+88h]; this
0x18005a546  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x18005a54b  mov     rcx, rdi; this
0x18005a54e  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x18005a553  mov     rcx, [rbp+20h+var_20]
0x18005a557  xor     rcx, rsp; StackCookie
0x18005a55a  call    __security_check_cookie
0x18005a55f  lea     r11, [rsp+120h+var_10]
0x18005a567  mov     rbx, [r11+28h]
0x18005a56b  mov     rsi, [r11+30h]
0x18005a56f  mov     rsp, r11
0x18005a572  pop     r14
0x18005a574  pop     rdi
0x18005a575  pop     rbp
0x18005a576  retn
```
