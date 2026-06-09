# Concurrency::task<uchar>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x1800263bc`
- end: `0x1800265fd`
- name: `?_Init@?$_InitialTaskHandle@XV_lambda_92025865ef304844afd880c1a9e1f846_@@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU_TypeSelectorNoAsync@details@3@@Z`
- size: `577`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027390`

## callees

- `0x1800026b4`
- `0x1800258a8`
- `0x180025a10`
- `0x1800263bc`
- `0x180026a5c`
- `0x180049010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026576`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026597`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026576`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026597`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180026500`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180026500`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002651f`
- `msvcp_win!?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18002651f`
- `msvcp_win!_Mtx_lock` at `0x180026561`
- `msvcp_win!_Mtx_lock` at `0x180026561`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800264ea`
- `msvcp_win!?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x1800264ea`
- `msvcp_win!_Mtx_unlock` at `0x1800265af`
- `msvcp_win!_Mtx_unlock` at `0x1800265c4`
- `msvcp_win!_Mtx_unlock` at `0x1800265af`
- `msvcp_win!_Mtx_unlock` at `0x1800265c4`

## pseudocode

```c
void __fastcall Concurrency::task<unsigned char>::_InitialTaskHandle<void,_lambda_92025865ef304844afd880c1a9e1f846_,Concurrency::details::_TypeSelectorNoAsync>::_Init(
        __int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rdx
  Concurrency::details::_TaskEventLogger *v7; // rbx
  _BYTE *v8; // rcx
  char v9; // si
  _BYTE *v10; // rdx
  struct _Mtx_internal_imp_t *v11; // rcx
  _QWORD v12[7]; // [rsp+40h] [rbp-79h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp-41h]
  _QWORD v14[7]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD *v15; // [rsp+B8h] [rbp-1h]
  _BYTE v16[56]; // [rsp+C0h] [rbp+7h] BYREF
  _BYTE *v17; // [rsp+F8h] [rbp+3Fh]

  v2 = *(_QWORD *)(a1 + 8);
  v12[0] = &std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::`vftable';
  v12[1] = *(_QWORD *)(a1 + 24);
  v13 = v12;
  v15 = 0;
  v15 = std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::_Copy((__int64)v12, v14);
  v17 = 0;
  v3 = operator new(0x48u);
  *v3 = &std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,unsigned char,>::`vftable';
  v3[8] = 0;
  v4 = v15;
  if ( v15 )
  {
    v3[8] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))*v15)(v15, v3 + 1);
    v4 = v15;
  }
  v17 = v3;
  if ( v4 )
  {
    v5 = v14;
    LOBYTE(v5) = v4 != v14;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v4 + 32LL))(v4, v5);
    v15 = 0;
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
  v8 = v17;
  if ( !v17 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v9 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v8 + 16LL))(v8);
  Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(v7);
  if ( v17 )
  {
    v10 = v16;
    LOBYTE(v10) = v17 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v10);
    v17 = 0;
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
    Concurrency::details::_TaskCollectionBaseImpl::_Complete((char *)(v2 + 136));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
}

```

## disassembly

```asm
0x1800263bc  mov     [rsp-8+arg_8], rbx
0x1800263c1  mov     [rsp-8+arg_10], rsi
0x1800263c6  push    rbp
0x1800263c7  push    rdi
0x1800263c8  push    r14
0x1800263ca  lea     rbp, [rsp-47h]
0x1800263cf  sub     rsp, 100h
0x1800263d6  mov     r14, rcx
0x1800263d9  mov     rdi, [rcx+8]
0x1800263dd  lea     rax, [rbp+57h+var_50]
0x1800263e1  mov     [rsp+110h+var_E8], rax
0x1800263e6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_92025865ef304844afd880c1a9e1f846_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::`vftable'
0x1800263ed  mov     [rbp+57h+var_D0], rax
0x1800263f1  mov     rax, [rcx+18h]
0x1800263f5  mov     [rbp+57h+var_C8], rax
0x1800263f9  lea     rax, [rbp+57h+var_D0]
0x1800263fd  mov     [rbp+57h+var_98], rax
0x180026401  lea     rax, [rbp+57h+var_D0]
0x180026405  mov     [rsp+110h+var_E0], rax
0x18002640a  lea     rax, [rbp+57h+var_90]
0x18002640e  mov     [rsp+110h+var_F0], rax
0x180026413  mov     [rbp+57h+var_58], 0
0x18002641b  lea     rdx, [rbp+57h+var_90]
0x18002641f  lea     rcx, [rbp+57h+var_D0]
0x180026423  call    ?_Copy@?$_Func_impl_no_alloc@V_lambda_92025865ef304844afd880c1a9e1f846_@@X$$V@std@@EEBAPEAV?$_Func_base@X$$V@2@PEAX@Z; std::_Func_impl_no_alloc<_lambda_92025865ef304844afd880c1a9e1f846_,void,>::_Copy(void *)
0x180026428  mov     [rbp+57h+var_58], rax
0x18002642c  mov     [rbp+57h+var_18], 0
0x180026434  mov     ecx, 48h ; 'H'; Size
0x180026439  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002643e  mov     rbx, rax
0x180026441  mov     [rsp+110h+var_F0], rax
0x180026446  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@E$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_052e919cc0e5399df76dff3972c0cac1_,uchar,>::`vftable'
0x18002644d  mov     [rbx], rax
0x180026450  lea     rsi, [rbx+8]
0x180026454  mov     [rsp+110h+var_D8], rsi
0x180026459  mov     qword ptr [rsi+38h], 0
0x180026461  mov     rcx, [rbp+57h+var_58]
0x180026465  test    rcx, rcx
0x180026468  jz      short loc_180026480
0x18002646a  mov     rax, [rcx]
0x18002646d  mov     rdx, rsi
0x180026470  mov     rax, [rax]
0x180026473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026478  mov     [rsi+38h], rax
0x18002647c  mov     rcx, [rbp+57h+var_58]
0x180026480  mov     [rbp+57h+var_18], rbx
0x180026484  test    rcx, rcx
0x180026487  jz      short loc_1800264A7
0x180026489  mov     rax, [rcx]
0x18002648c  lea     rdx, [rbp+57h+var_90]
0x180026490  cmp     rcx, rdx
0x180026493  setnz   dl
0x180026496  mov     rax, [rax+20h]
0x18002649a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002649f  mov     [rbp+57h+var_58], 0
0x1800264a7  mov     rcx, [rbp+57h+var_98]
0x1800264ab  test    rcx, rcx
0x1800264ae  jz      short loc_1800264CE
0x1800264b0  mov     rax, [rcx]
0x1800264b3  lea     rdx, [rbp+57h+var_D0]
0x1800264b7  cmp     rcx, rdx
0x1800264ba  setnz   dl
0x1800264bd  mov     rax, [rax+20h]
0x1800264c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c6  mov     [rbp+57h+var_98], 0
0x1800264ce  lea     rax, [rbp+57h+var_50]
0x1800264d2  mov     [rsp+110h+var_D8], rax
0x1800264d7  mov     rbx, [r14+8]
0x1800264db  add     rbx, 160h
0x1800264e2  mov     [rsp+110h+var_F0], rbx
0x1800264e7  mov     rcx, rbx
0x1800264ea  call    cs:__imp_?_LogWorkItemStarted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemStarted(void)
0x1800264f1  nop     dword ptr [rax+rax+00h]
0x1800264f6  nop
0x1800264f7  mov     rcx, [rbp+57h+var_18]
0x1800264fb  test    rcx, rcx
0x1800264fe  jnz     short loc_18002650D
0x180026500  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180026507  nop     dword ptr [rax+rax+00h]
0x18002650c  int     3; Trap to Debugger
0x18002650d  mov     rax, [rcx]
0x180026510  mov     rax, [rax+10h]
0x180026514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026519  mov     sil, al
0x18002651c  mov     rcx, rbx
0x18002651f  call    cs:__imp_?_LogWorkItemCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogWorkItemCompleted(void)
0x180026526  nop     dword ptr [rax+rax+00h]
0x18002652b  nop
0x18002652c  mov     rcx, [rbp+57h+var_18]
0x180026530  test    rcx, rcx
0x180026533  jz      short loc_180026553
0x180026535  mov     rdx, [rcx]
0x180026538  mov     rax, [rdx+20h]
0x18002653c  lea     rdx, [rbp+57h+var_50]
0x180026540  cmp     rcx, rdx
0x180026543  setnz   dl
0x180026546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002654b  mov     [rbp+57h+var_18], 0
0x180026553  mov     [rdi+170h], sil
0x18002655a  lea     rbx, [rdi+20h]
0x18002655e  mov     rcx, rbx; _Mtx_t
0x180026561  call    cs:__imp__Mtx_lock
0x180026568  nop     dword ptr [rax+rax+00h]
0x18002656d  test    eax, eax
0x18002656f  jz      short loc_180026583
0x180026571  mov     ecx, 5
0x180026576  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002657d  nop     dword ptr [rax+rax+00h]
0x180026582  int     3; Trap to Debugger
0x180026583  mov     eax, [rbx+4Ch]
0x180026586  cmp     eax, 7FFFFFFFh
0x18002658b  jnz     short loc_1800265A4
0x18002658d  dec     eax
0x18002658f  mov     [rbx+4Ch], eax
0x180026592  mov     ecx, 6
0x180026597  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002659e  nop     dword ptr [rax+rax+00h]
0x1800265a3  int     3; Trap to Debugger
0x1800265a4  mov     eax, [rdi+8]
0x1800265a7  mov     rcx, rbx; _Mtx_t
0x1800265aa  cmp     eax, 4
0x1800265ad  jnz     short loc_1800265BD
0x1800265af  call    cs:__imp__Mtx_unlock
0x1800265b6  nop     dword ptr [rax+rax+00h]
0x1800265bb  jmp     short loc_1800265E4
0x1800265bd  mov     dword ptr [rdi+8], 3
0x1800265c4  call    cs:__imp__Mtx_unlock
0x1800265cb  nop     dword ptr [rax+rax+00h]
0x1800265d0  lea     rcx, [rdi+88h]; this
0x1800265d7  call    ?_Complete@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskCollectionBaseImpl::_Complete(void)
0x1800265dc  mov     rcx, rdi; this
0x1800265df  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x1800265e4  lea     r11, [rsp+110h+var_10]
0x1800265ec  mov     rbx, [r11+28h]
0x1800265f0  mov     rsi, [r11+30h]
0x1800265f4  mov     rsp, r11
0x1800265f7  pop     r14
0x1800265f9  pop     rdi
0x1800265fa  pop     rbp
0x1800265fb  retn
```
