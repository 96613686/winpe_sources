# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x1800587d4`
- end: `0x180058a29`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `597`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800599a0`

## callees

- `0x1800053a0`
- `0x180009338`
- `0x180057e94`
- `0x180057ff0`
- `0x1800587d4`
- `0x180058e30`
- `0x1800cc010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180058926`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180058926`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180058999`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800589ba`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180058999`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800589ba`
- `msvcp_win!_Mtx_lock` at `0x180058984`
- `msvcp_win!_Mtx_lock` at `0x180058984`
- `msvcp_win!_Mtx_unlock` at `0x1800589d2`
- `msvcp_win!_Mtx_unlock` at `0x1800589e7`
- `msvcp_win!_Mtx_unlock` at `0x1800589d2`
- `msvcp_win!_Mtx_unlock` at `0x1800589e7`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058910`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058910`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058945`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x180058945`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_ae79b6a25084f623882ea33371aa944e__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rsi
  _BYTE *v4; // rcx
  _BYTE *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  _BYTE *v8; // rcx
  char v9; // si
  _BYTE *v10; // rdx
  struct _Mtx_internal_imp_t *v11; // rcx
  _QWORD v12[7]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v13; // [rsp+70h] [rbp-90h]
  _BYTE *v14; // [rsp+78h] [rbp-88h]
  _BYTE v15[56]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE *v16; // [rsp+B8h] [rbp-48h]
  _BYTE v17[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE *v18; // [rsp+F8h] [rbp-8h]

  v2 = *(_QWORD *)(a1 + 8);
  v14 = v15;
  v12[0] = off_1800CE7A8;
  v12[1] = *(_QWORD *)(a1 + 24);
  v13 = v12;
  v18 = 0;
  v18 = (_BYTE *)std::_Func_impl_no_alloc__lambda_ae79b6a25084f623882ea33371aa944e__void_::_Move(v12, v17);
  v16 = 0;
  v3 = operator new(0x48u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v3[8] = 0;
  v4 = v18;
  if ( v18 )
  {
    v3[8] = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v18)(v18, v3 + 1);
    v4 = v18;
  }
  v16 = v3;
  if ( v4 )
  {
    v5 = v17;
    LOBYTE(v5) = v4 != v17;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v4 + 32LL))(v4, v5);
    v18 = 0;
  }
  if ( v13 )
  {
    v6 = v12;
    LOBYTE(v6) = v13 != v12;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v13 + 32LL))(v13, v6);
    v13 = 0;
  }
  v7 = (Concurrency::details::_TaskEventLogger *)(*(_QWORD *)(a1 + 8) + 256LL);
  Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(v7);
  v8 = v16;
  if ( !v16 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 16LL))(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v16 )
  {
    v10 = v15;
    LOBYTE(v10) = v16 != v15;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v16 + 32LL))(v16, v10);
    v16 = 0;
  }
  *(_BYTE *)(v2 + 272) = v9;
  if ( _Mtx_lock((_Mtx_t)(v2 + 32)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *(_DWORD *)(v2 + 60) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v2 + 60) = 2147483646;
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
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((_Cnd_t)(v2 + 88));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x1800587d4  mov     [rsp-8+arg_8], rbx
0x1800587d9  mov     [rsp-8+arg_10], rsi
0x1800587de  push    rbp
0x1800587df  push    rdi
0x1800587e0  push    r14
0x1800587e2  lea     rbp, [rsp-10h]
0x1800587e7  sub     rsp, 110h
0x1800587ee  mov     rax, cs:__security_cookie
0x1800587f5  xor     rax, rsp
0x1800587f8  mov     [rbp+20h+var_20], rax
0x1800587fc  mov     r14, rcx
0x1800587ff  mov     rdi, [rcx+8]
0x180058803  lea     rax, [rbp+20h+var_A0]
0x180058807  mov     [rsp+120h+var_A8], rax
0x18005880c  lea     rax, off_1800CE7A8
0x180058813  mov     [rsp+120h+var_E8], rax
0x180058818  mov     rax, [rcx+18h]
0x18005881c  mov     [rsp+120h+var_E0], rax
0x180058821  lea     rax, [rsp+120h+var_E8]
0x180058826  mov     [rsp+120h+var_B0], rax
0x18005882b  lea     rax, [rsp+120h+var_E8]
0x180058830  mov     [rsp+120h+var_F8], rax
0x180058835  lea     rax, [rbp+20h+var_60]
0x180058839  mov     [rsp+120h+var_100], rax
0x18005883e  and     [rbp+20h+var_28], 0
0x180058843  lea     rdx, [rbp+20h+var_60]
0x180058847  lea     rcx, [rsp+120h+var_E8]
0x18005884c  call    std___Func_impl_no_alloc__lambda_ae79b6a25084f623882ea33371aa944e__void____Move
0x180058851  mov     [rbp+20h+var_28], rax
0x180058855  and     [rbp+20h+var_68], 0
0x18005885a  mov     ecx, 48h ; 'H'; Size
0x18005885f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058864  mov     rsi, rax
0x180058867  mov     [rsp+120h+var_100], rax
0x18005886c  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x180058873  mov     [rsi], rax
0x180058876  lea     rbx, [rsi+8]
0x18005887a  mov     [rsp+120h+var_F0], rbx
0x18005887f  and     qword ptr [rbx+38h], 0
0x180058884  mov     rcx, [rbp+20h+var_28]
0x180058888  test    rcx, rcx
0x18005888b  jz      short loc_1800588A3
0x18005888d  mov     rax, [rcx]
0x180058890  mov     rdx, rbx
0x180058893  mov     rax, [rax]
0x180058896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005889b  mov     [rbx+38h], rax
0x18005889f  mov     rcx, [rbp+20h+var_28]
0x1800588a3  and     [rsp+120h+var_100], 0
0x1800588a9  mov     [rbp+20h+var_68], rsi
0x1800588ad  test    rcx, rcx
0x1800588b0  jz      short loc_1800588CD
0x1800588b2  mov     rax, [rcx]
0x1800588b5  lea     rdx, [rbp+20h+var_60]
0x1800588b9  cmp     rcx, rdx
0x1800588bc  setnz   dl
0x1800588bf  mov     rax, [rax+20h]
0x1800588c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588c8  and     [rbp+20h+var_28], 0
0x1800588cd  mov     rcx, [rsp+120h+var_B0]
0x1800588d2  test    rcx, rcx
0x1800588d5  jz      short loc_1800588F4
0x1800588d7  mov     rax, [rcx]
0x1800588da  lea     rdx, [rsp+120h+var_E8]
0x1800588df  cmp     rcx, rdx
0x1800588e2  setnz   dl
0x1800588e5  mov     rax, [rax+20h]
0x1800588e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588ee  and     [rsp+120h+var_B0], 0
0x1800588f4  lea     rax, [rbp+20h+var_A0]
0x1800588f8  mov     [rsp+120h+var_F0], rax
0x1800588fd  mov     rbx, [r14+8]
0x180058901  add     rbx, 100h
0x180058908  mov     [rsp+120h+var_F8], rbx
0x18005890d  mov     rcx, rbx
0x180058910  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x180058917  nop     dword ptr [rax+rax+00h]
0x18005891c  nop
0x18005891d  mov     rcx, [rbp+20h+var_68]
0x180058921  test    rcx, rcx
0x180058924  jnz     short loc_180058933
0x180058926  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005892d  nop     dword ptr [rax+rax+00h]
0x180058932  int     3; Trap to Debugger
0x180058933  mov     rax, [rcx]
0x180058936  mov     rax, [rax+10h]
0x18005893a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005893f  mov     sil, al
0x180058942  mov     rcx, rbx
0x180058945  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x18005894c  nop     dword ptr [rax+rax+00h]
0x180058951  nop
0x180058952  mov     rcx, [rbp+20h+var_68]
0x180058956  test    rcx, rcx
0x180058959  jz      short loc_180058976
0x18005895b  mov     rdx, [rcx]
0x18005895e  mov     rax, [rdx+20h]
0x180058962  lea     rdx, [rbp+20h+var_A0]
0x180058966  cmp     rcx, rdx
0x180058969  setnz   dl
0x18005896c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058971  and     [rbp+20h+var_68], 0
0x180058976  mov     [rdi+110h], sil
0x18005897d  lea     rbx, [rdi+20h]
0x180058981  mov     rcx, rbx; _Mtx_t
0x180058984  call    cs:__imp__Mtx_lock
0x18005898b  nop     dword ptr [rax+rax+00h]
0x180058990  test    eax, eax
0x180058992  jz      short loc_1800589A6
0x180058994  mov     ecx, 5
0x180058999  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800589a0  nop     dword ptr [rax+rax+00h]
0x1800589a5  int     3; Trap to Debugger
0x1800589a6  mov     eax, [rbx+1Ch]
0x1800589a9  cmp     eax, 7FFFFFFFh
0x1800589ae  jnz     short loc_1800589C7
0x1800589b0  dec     eax
0x1800589b2  mov     [rbx+1Ch], eax
0x1800589b5  mov     ecx, 6
0x1800589ba  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800589c1  nop     dword ptr [rax+rax+00h]
0x1800589c6  int     3; Trap to Debugger
0x1800589c7  mov     eax, [rdi+8]
0x1800589ca  mov     rcx, rbx; _Mtx_t
0x1800589cd  cmp     eax, 4
0x1800589d0  jnz     short loc_1800589E0
0x1800589d2  call    cs:__imp__Mtx_unlock
0x1800589d9  nop     dword ptr [rax+rax+00h]
0x1800589de  jmp     short loc_180058A04
0x1800589e0  mov     dword ptr [rdi+8], 3
0x1800589e7  call    cs:__imp__Mtx_unlock
0x1800589ee  nop     dword ptr [rax+rax+00h]
0x1800589f3  lea     rcx, [rdi+58h]; this
0x1800589f7  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x1800589fc  mov     rcx, rdi; this
0x1800589ff  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x180058a04  mov     rcx, [rbp+20h+var_20]
0x180058a08  xor     rcx, rsp; StackCookie
0x180058a0b  call    __security_check_cookie
0x180058a10  lea     r11, [rsp+120h+var_10]
0x180058a18  mov     rbx, [r11+28h]
0x180058a1c  mov     rsi, [r11+30h]
0x180058a20  mov     rsp, r11
0x180058a23  pop     r14
0x180058a25  pop     rdi
0x180058a26  pop     rbp
0x180058a27  retn
```
