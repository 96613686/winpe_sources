# AsyncWinRTCompletionHandlerPriorityWrapper::Initialize(IUnknown *,_GUID,Windows::UI::Core::ICoreDispatcher *,IWebPlatformPriorityContext *,MSAppPriority,IGlobalInterfaceTable *)

- ea: `0x18059d3b8`
- end: `0x18059d52f`
- name: `?Initialize@AsyncWinRTCompletionHandlerPriorityWrapper@@QEAAJPEAUIUnknown@@U_GUID@@PEAUICoreDispatcher@Core@UI@Windows@@PEAUIWebPlatformPriorityContext@@W4MSAppPriority@@PEAUIGlobalInterfaceTable@@@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18059dbf0`

## callees

- `0x1803e5a74`
- `0x180401df0`
- `0x18046dad0`
- `0x18046f3fc`
- `0x18059c3c8`
- `0x18059d3b8`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18059d434`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18059d434`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentLogicalThreadId` at `0x18059d418`
- `api-ms-win-core-com-l1-1-0!CoGetCurrentLogicalThreadId` at `0x18059d418`

## pseudocode

```c
__int64 __fastcall AsyncWinRTCompletionHandlerPriorityWrapper::Initialize(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64, __int64 *),
        _OWORD *a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  __int64 v8; // r14
  HRESULT CurrentLogicalThreadId; // ebx
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(_QWORD, __int64, __int64 *); // rbx
  int v13; // [rsp+20h] [rbp-20h]
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  v14 = 0;
  v8 = a1 + 120;
  *(_OWORD *)(a1 + 120) = *a3;
  Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::operator=(a1 + 72, a4);
  Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::operator=(a1 + 104, a5);
  *(_DWORD *)(a1 + 100) = a6;
  CurrentLogicalThreadId = CoGetCurrentLogicalThreadId((GUID *)(a1 + 84));
  if ( CurrentLogicalThreadId < 0 )
  {
    v10 = 605;
LABEL_13:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
      (const char *)(unsigned int)CurrentLogicalThreadId,
      v13);
    goto LABEL_14;
  }
  *(_DWORD *)(a1 + 80) = GetCurrentThreadId();
  if ( *(__int64 (__fastcall ****)(_QWORD, __int64, __int64 *))(a1 + 112) != a2 )
  {
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalAddRef(&v15);
    v15 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))(a1 + 112);
    *(_QWORD *)(a1 + 112) = a2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  }
  v11 = **a2;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  CurrentLogicalThreadId = v11(a2, v8, &v14);
  if ( CurrentLogicalThreadId < 0 )
  {
    v10 = 611;
    goto LABEL_13;
  }
  if ( *(_QWORD *)(a1 + 144) != a7 )
  {
    if ( a7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a7 + 8LL))(a7);
    v15 = *(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))(a1 + 144);
    *(_QWORD *)(a1 + 144) = a7;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(&v15);
  }
  CurrentLogicalThreadId = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 144) + 24LL))(
                             *(_QWORD *)(a1 + 144),
                             v14,
                             v8,
                             a1 + 136);
  if ( CurrentLogicalThreadId < 0 )
  {
    v10 = 617;
    goto LABEL_13;
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return (unsigned int)CurrentLogicalThreadId;
}

```

## disassembly

```asm
0x18059d3b8  mov     rax, rsp
0x18059d3bb  mov     [rax+20h], r9
0x18059d3bf  mov     [rax+18h], r8
0x18059d3c3  mov     [rax+10h], rdx
0x18059d3c7  mov     [rax+8], rcx
0x18059d3cb  push    rbp
0x18059d3cc  push    rbx
0x18059d3cd  push    rsi
0x18059d3ce  push    rdi
0x18059d3cf  push    r14
0x18059d3d1  mov     rbp, rsp
0x18059d3d4  sub     rsp, 40h
0x18059d3d8  mov     rdi, [rbp+arg_0]
0x18059d3dc  mov     rax, [rbp+arg_10]
0x18059d3e0  mov     rdx, [rbp+arg_18]
0x18059d3e4  mov     [rbp+var_10], 0
0x18059d3ec  lea     r14, [rdi+78h]
0x18059d3f0  movaps  xmm0, xmmword ptr [rax]
0x18059d3f3  lea     rcx, [rdi+48h]
0x18059d3f7  movdqu  xmmword ptr [r14], xmm0
0x18059d3fc  call    ??4?$ComPtr@UICoreDispatcher@Core@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUICoreDispatcher@Core@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::operator=(Windows::UI::Core::ICoreDispatcher *)
0x18059d401  mov     rdx, [rbp+arg_20]
0x18059d405  lea     rcx, [rdi+68h]
0x18059d409  call    ??4?$ComPtr@UICoreDispatcher@Core@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUICoreDispatcher@Core@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreDispatcher>::operator=(Windows::UI::Core::ICoreDispatcher *)
0x18059d40e  mov     eax, [rbp+arg_28]
0x18059d411  lea     rcx, [rdi+54h]; pguid
0x18059d415  mov     [rdi+64h], eax
0x18059d418  call    cs:__imp_CoGetCurrentLogicalThreadId
0x18059d41f  nop     dword ptr [rax+rax+00h]
0x18059d424  mov     ebx, eax
0x18059d426  test    eax, eax
0x18059d428  jns     short loc_18059D434
0x18059d42a  mov     edx, 25Dh
0x18059d42f  jmp     loc_18059D505
0x18059d434  call    cs:__imp_GetCurrentThreadId
0x18059d43b  nop     dword ptr [rax+rax+00h]
0x18059d440  mov     rsi, [rbp+arg_8]
0x18059d444  mov     [rdi+50h], eax
0x18059d447  cmp     [rdi+70h], rsi
0x18059d44b  jz      short loc_18059D46F
0x18059d44d  lea     rcx, [rbp+var_8]
0x18059d451  mov     [rbp+var_8], rsi
0x18059d455  call    ?InternalAddRef@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalAddRef(void)
0x18059d45a  mov     rax, [rdi+70h]
0x18059d45e  lea     rcx, [rbp+var_8]
0x18059d462  mov     [rbp+var_8], rax
0x18059d466  mov     [rdi+70h], rsi
0x18059d46a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18059d46f  mov     rax, [rsi]
0x18059d472  lea     rcx, [rbp+var_10]
0x18059d476  mov     rbx, [rax]
0x18059d479  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18059d47e  lea     r8, [rbp+var_10]
0x18059d482  mov     rdx, r14
0x18059d485  mov     rcx, rsi
0x18059d488  mov     rax, rbx
0x18059d48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059d490  mov     ebx, eax
0x18059d492  test    eax, eax
0x18059d494  jns     short loc_18059D49D
0x18059d496  mov     edx, 263h
0x18059d49b  jmp     short loc_18059D505
0x18059d49d  mov     rbx, [rbp+arg_30]
0x18059d4a1  cmp     [rdi+90h], rbx
0x18059d4a8  jz      short loc_18059D4D9
0x18059d4aa  test    rbx, rbx
0x18059d4ad  jz      short loc_18059D4BE
0x18059d4af  mov     rax, [rbx]
0x18059d4b2  mov     rcx, rbx
0x18059d4b5  mov     rax, [rax+8]
0x18059d4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059d4be  mov     rax, [rdi+90h]
0x18059d4c5  lea     rcx, [rbp+var_8]
0x18059d4c9  mov     [rbp+var_8], rax
0x18059d4cd  mov     [rdi+90h], rbx
0x18059d4d4  call    ?InternalRelease@?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::InternalRelease(void)
0x18059d4d9  mov     rcx, [rdi+90h]
0x18059d4e0  lea     r9, [rdi+88h]
0x18059d4e7  mov     rdx, [rbp+var_10]
0x18059d4eb  mov     r8, r14
0x18059d4ee  mov     rax, [rcx]
0x18059d4f1  mov     rax, [rax+18h]
0x18059d4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18059d4fa  mov     ebx, eax
0x18059d4fc  test    eax, eax
0x18059d4fe  jns     short loc_18059D518
0x18059d500  mov     edx, 269h; void *
0x18059d505  mov     rcx, [rbp+28h]; this
0x18059d509  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059d510  mov     r9d, ebx; char *
0x18059d513  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059d518  lea     rcx, [rbp+var_10]
0x18059d51c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18059d521  mov     eax, ebx
0x18059d523  add     rsp, 40h
0x18059d527  pop     r14
0x18059d529  pop     rdi
0x18059d52a  pop     rsi
0x18059d52b  pop     rbx
0x18059d52c  pop     rbp
0x18059d52d  retn
```
