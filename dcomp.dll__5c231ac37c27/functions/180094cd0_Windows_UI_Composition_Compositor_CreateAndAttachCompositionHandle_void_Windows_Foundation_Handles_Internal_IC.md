# Windows::UI::Composition::Compositor::CreateAndAttachCompositionHandle(void * *,Windows::Foundation::Handles::Internal::ICompositionHandle * *)

- ea: `0x180094cd0`
- end: `0x180094e75`
- name: `?CreateAndAttachCompositionHandle@Compositor@Composition@UI@Windows@@QEAAJPEAPEAXPEAPEAUICompositionHandle@Internal@Handles@Foundation@4@@Z`
- size: `421`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Compositor *__hidden this, void **, struct Windows::Foundation::Handles::Internal::ICompositionHandle **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180094960`

## callees

- `0x1800093f4`
- `0x18001358c`
- `0x180094cd0`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180094d42`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180094d42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180094d2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180094d2c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180094d58`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180094d58`

## string_xrefs

- `0x180094de5`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositorg.cpp`
- `0x180094e4c`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositorg.cpp`
- `0x180094d25`: `Windows.Foundation.Handles.Internal.CompositionHandle`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Compositor::CreateAndAttachCompositionHandle(
        Windows::UI::Composition::Compositor *this,
        void **a2,
        struct Windows::Foundation::Handles::Internal::ICompositionHandle **a3)
{
  __int64 *v3; // rsi
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v11; // rcx
  int v12; // eax
  struct Windows::Foundation::Handles::Internal::ICompositionHandle *v13; // rcx
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-50h]
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Foundation::Handles::Internal::ICompositionHandle *v18; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v3 = (__int64 *)((char *)this + 1192);
  if ( !*((_QWORD *)this + 149) )
  {
    v17 = 0;
    string = 0;
    v6 = WindowsCreateStringReference(
           L"Windows.Foundation.Handles.Internal.CompositionHandle",
           0x35u,
           &hstringHeader,
           &string);
    if ( v6 < 0 )
    {
      RaiseException(v6, 1u, 0, 0);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_011681b7_9ece_462e_89f5_be2215219abb, &v17);
    if ( ActivationFactory < 0 )
    {
      v15 = 586;
    }
    else
    {
      v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
      v9 = **v17;
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v3);
      ActivationFactory = v9(v8, &GUID_1f5cee95_a9e9_464e_be2f_57bbb131e7ec, v3);
      if ( ActivationFactory >= 0 )
      {
        v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
        if ( v17 )
        {
          v17 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
        }
        goto LABEL_8;
      }
      v15 = 588;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositorg.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v16);
    v13 = (struct Windows::Foundation::Handles::Internal::ICompositionHandle *)v17;
    if ( !v17 )
      return (unsigned int)ActivationFactory;
    v17 = 0;
    goto LABEL_11;
  }
LABEL_8:
  v11 = *v3;
  v18 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, void **, GUID *, struct Windows::Foundation::Handles::Internal::ICompositionHandle **))(*(_QWORD *)v11 + 48LL))(
          v11,
          a2,
          &GUID_cfde6f9a_4afe_45b3_81b5_20d13cd8a81a,
          &v18);
  ActivationFactory = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositorg.cpp",
      (const char *)(unsigned int)v12,
      v16);
    v13 = v18;
    if ( !v18 )
      return (unsigned int)ActivationFactory;
    v18 = 0;
LABEL_11:
    (*(void (__fastcall **)(struct Windows::Foundation::Handles::Internal::ICompositionHandle *))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)ActivationFactory;
  }
  *a3 = v18;
  return 0;
}

```

## disassembly

```asm
0x180094cd0  mov     [rsp-28h+arg_18], rbx
0x180094cd5  push    rbp
0x180094cd6  push    rsi
0x180094cd7  push    rdi
0x180094cd8  push    r14
0x180094cda  push    r15
0x180094cdc  mov     rbp, rsp
0x180094cdf  sub     rsp, 70h
0x180094ce3  mov     rax, cs:__security_cookie
0x180094cea  xor     rax, rsp
0x180094ced  mov     [rbp+var_10], rax
0x180094cf1  lea     rsi, [rcx+4A8h]
0x180094cf8  mov     r14, r8
0x180094cfb  cmp     qword ptr [rsi], 0
0x180094cff  mov     r15, rdx
0x180094d02  jnz     loc_180094DB6
0x180094d08  lea     r9, [rbp+string]; string
0x180094d0c  mov     [rbp+var_40], 0
0x180094d14  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180094d18  mov     [rbp+string], 0
0x180094d20  mov     edx, 35h ; '5'; length
0x180094d25  lea     rcx, ?RuntimeClass_Windows_Foundation_Handles_Internal_CompositionHandle@@3QBGB; "Windows.Foundation.Handles.Internal.Com"...
0x180094d2c  call    cs:__imp_WindowsCreateStringReference
0x180094d32  test    eax, eax
0x180094d34  jns     short loc_180094D49
0x180094d36  xor     r9d, r9d; lpArguments
0x180094d39  xor     r8d, r8d; nNumberOfArguments
0x180094d3c  mov     ecx, eax; dwExceptionCode
0x180094d3e  lea     edx, [r9+1]; dwExceptionFlags
0x180094d42  call    cs:__imp_RaiseException
0x180094d48  int     3; Trap to Debugger
0x180094d49  mov     rcx, [rbp+string]
0x180094d4d  lea     r8, [rbp+var_40]
0x180094d51  lea     rdx, _GUID_011681b7_9ece_462e_89f5_be2215219abb
0x180094d58  call    cs:__imp_RoGetActivationFactory
0x180094d5e  mov     ebx, eax
0x180094d60  test    eax, eax
0x180094d62  js      loc_180094E43
0x180094d68  mov     rbx, [rbp+var_40]
0x180094d6c  mov     rcx, rsi
0x180094d6f  mov     rax, [rbx]
0x180094d72  mov     rdi, [rax]
0x180094d75  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x180094d7a  mov     r8, rsi
0x180094d7d  lea     rdx, _GUID_1f5cee95_a9e9_464e_be2f_57bbb131e7ec
0x180094d84  mov     rcx, rbx
0x180094d87  mov     rax, rdi
0x180094d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094d8f  mov     ebx, eax
0x180094d91  test    eax, eax
0x180094d93  js      loc_180094E6E
0x180094d99  mov     rcx, [rbp+var_40]
0x180094d9d  test    rcx, rcx
0x180094da0  jz      short loc_180094DB6
0x180094da2  mov     [rbp+var_40], 0
0x180094daa  mov     rax, [rcx]
0x180094dad  mov     rax, [rax+10h]
0x180094db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094db6  mov     rcx, [rsi]
0x180094db9  lea     r9, [rbp+var_38]
0x180094dbd  mov     [rbp+var_38], 0
0x180094dc5  lea     r8, _GUID_cfde6f9a_4afe_45b3_81b5_20d13cd8a81a
0x180094dcc  mov     rdx, r15
0x180094dcf  mov     rax, [rcx]
0x180094dd2  mov     rax, [rax+30h]
0x180094dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094ddb  mov     ebx, eax
0x180094ddd  test    eax, eax
0x180094ddf  jns     short loc_180094E38
0x180094de1  mov     rcx, [rbp+28h]; this
0x180094de5  lea     r8, aOnecoreuapWind_243; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180094dec  mov     r9d, eax; char *
0x180094def  mov     edx, 252h; void *
0x180094df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094df9  mov     rcx, [rbp+var_38]
0x180094dfd  test    rcx, rcx
0x180094e00  jz      short loc_180094E16
0x180094e02  mov     [rbp+var_38], 0
0x180094e0a  mov     rax, [rcx]
0x180094e0d  mov     rax, [rax+10h]
0x180094e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e16  mov     eax, ebx
0x180094e18  mov     rcx, [rbp+var_10]
0x180094e1c  xor     rcx, rsp; StackCookie
0x180094e1f  call    __security_check_cookie
0x180094e24  mov     rbx, [rsp+70h+arg_18]
0x180094e2c  add     rsp, 70h
0x180094e30  pop     r15
0x180094e32  pop     r14
0x180094e34  pop     rdi
0x180094e35  pop     rsi
0x180094e36  pop     rbp
0x180094e37  retn
0x180094e38  mov     rax, [rbp+var_38]
0x180094e3c  mov     [r14], rax
0x180094e3f  xor     eax, eax
0x180094e41  jmp     short loc_180094E18
0x180094e43  mov     edx, 24Ah; void *
0x180094e48  mov     rcx, [rbp+28h]; this
0x180094e4c  lea     r8, aOnecoreuapWind_243; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180094e53  mov     r9d, ebx; char *
0x180094e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094e5b  mov     rcx, [rbp+var_40]
0x180094e5f  test    rcx, rcx
0x180094e62  jz      short loc_180094E16
0x180094e64  mov     [rbp+var_40], 0
0x180094e6c  jmp     short loc_180094E0A
0x180094e6e  mov     edx, 24Ch
0x180094e73  jmp     short loc_180094E48
```
