# TestCommandHost::CreateEndpointToReceiveMessages(void)

- ea: `0x1800a1d90`
- end: `0x1800a1f42`
- name: `?CreateEndpointToReceiveMessages@TestCommandHost@@AEAAXXZ`
- size: `434`
- prototype: `void __fastcall(TestCommandHost *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bfa0`

## callees

- `0x180012b74`
- `0x18003afb0`
- `0x1800a1d90`
- `0x18010afb4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a1f29`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800a1f21`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800a1f21`

## string_xrefs

- `0x1800a1dfa`: `System\Input\TestCommandsPort`
- `0x1800a1ec7`: `System\Input\TestCommandsEndpoint`
- `0x1800a1dcf`: `onecoreuap\windows\moderncore\inputv2\utilities\testcommandhost\lib\testcommandhost.cpp`
- `0x1800a1e1b`: `onecoreuap\windows\moderncore\inputv2\utilities\testcommandhost\lib\testcommandhost.cpp`
- `0x1800a1e5d`: `onecoreuap\windows\moderncore\inputv2\utilities\testcommandhost\lib\testcommandhost.cpp`
- `0x1800a1ea4`: `onecoreuap\windows\moderncore\inputv2\utilities\testcommandhost\lib\testcommandhost.cpp`
- `0x1800a1ee2`: `onecoreuap\windows\moderncore\inputv2\utilities\testcommandhost\lib\testcommandhost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TestCommandHost::CreateEndpointToReceiveMessages(
        TestCommandHost *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Descriptor; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HLOCAL, const wchar_t *, char *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+20h] [rbp-20h]
  int v17; // [rsp+20h] [rbp-20h]
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  char v19; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v21; // [rsp+68h] [rbp+28h] BYREF

  hMem = 0;
  v19 = 0;
  Descriptor = InputSecurityDescriptor::QueryDescriptor((__int64)&hMem, a2, (__int64)c_wszMessagePortNames, a4, v15);
  if ( Descriptor < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\testcommandhost\\lib\\testcommandhost.cpp",
      (const char *)(unsigned int)Descriptor,
      v16);
  v6 = *(_QWORD *)this;
  v7 = *(__int64 (__fastcall **)(__int64, HLOCAL, const wchar_t *, char *))(**(_QWORD **)this + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 16);
  v8 = v7(v6, hMem, L"System\\Input\\TestCommandsPort", (char *)this + 16);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\testcommandhost\\lib\\testcommandhost.cpp",
      (const char *)(unsigned int)v8,
      v16);
  v17 = (_DWORD)this + 24;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int (*)(void *, const void *, int), TestCommandHost *, _QWORD))(**(_QWORD **)this + 104LL))(
         *(_QWORD *)this,
         TestCommandHost::OnCoreMessageStatic,
         this,
         *((_QWORD *)this + 2));
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\testcommandhost\\lib\\testcommandhost.cpp",
      (const char *)(unsigned int)v9,
      v17);
  v21 = 0;
  v10 = *(_QWORD *)this;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)this + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v12 = v11(v10, &v21);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\testcommandhost\\lib\\testcommandhost.cpp",
      (const char *)(unsigned int)v12,
      v17);
  v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64))(*(_QWORD *)v21 + 40LL))(
          v21,
          L"System\\Input\\TestCommandsEndpoint",
          *((_QWORD *)this + 3),
          1);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\testcommandhost\\lib\\testcommandhost.cpp",
      (const char *)(unsigned int)v13,
      v17);
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( hMem )
  {
    if ( v19 )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(hMem);
  }
}

```

## disassembly

```asm
0x1800a1d90  mov     [rsp-18h+arg_0], rbx
0x1800a1d95  mov     [rsp-18h+arg_10], rsi
0x1800a1d9a  push    rbp
0x1800a1d9b  push    rdi
0x1800a1d9c  push    r14
0x1800a1d9e  mov     rbp, rsp
0x1800a1da1  sub     rsp, 40h
0x1800a1da5  mov     rsi, rcx
0x1800a1da8  mov     [rbp+hMem], 0
0x1800a1db0  mov     [rbp+var_8], 0
0x1800a1db4  mov     r8, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x1800a1dbb  lea     rcx, [rbp+hMem]
0x1800a1dbf  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x1800a1dc4  mov     rcx, [rbp+18h]; this
0x1800a1dc8  test    eax, eax
0x1800a1dca  jns     short loc_1800A1DE1
0x1800a1dcc  mov     r9d, eax; char *
0x1800a1dcf  lea     r8, aOnecoreuapWind_185; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800a1dd6  mov     edx, 68h ; 'h'; void *
0x1800a1ddb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1de1  mov     rdi, [rsi]
0x1800a1de4  mov     rax, [rdi]
0x1800a1de7  mov     rbx, [rax+38h]
0x1800a1deb  lea     r14, [rsi+10h]
0x1800a1def  mov     rcx, r14
0x1800a1df2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a1df7  mov     r9, r14
0x1800a1dfa  lea     r8, aSystemInputTes; "System\\Input\\TestCommandsPort"
0x1800a1e01  mov     rdx, [rbp+hMem]
0x1800a1e05  mov     rcx, rdi
0x1800a1e08  mov     rax, rbx
0x1800a1e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e10  mov     rcx, [rbp+18h]; this
0x1800a1e14  test    eax, eax
0x1800a1e16  jns     short loc_1800A1E2D
0x1800a1e18  mov     r9d, eax; char *
0x1800a1e1b  lea     r8, aOnecoreuapWind_185; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800a1e22  mov     edx, 6Dh ; 'm'; void *
0x1800a1e27  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1e2d  mov     rcx, [rsi]
0x1800a1e30  mov     rax, [rcx]
0x1800a1e33  lea     rdx, [r14+8]
0x1800a1e37  mov     qword ptr [rsp+40h+var_20], rdx; int
0x1800a1e3c  mov     r9, [r14]
0x1800a1e3f  mov     r8, rsi
0x1800a1e42  lea     rdx, ?OnCoreMessageStatic@TestCommandHost@@CAJPEAXPEBXH@Z; TestCommandHost::OnCoreMessageStatic(void *,void const *,int)
0x1800a1e49  mov     rax, [rax+68h]
0x1800a1e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e52  mov     rcx, [rbp+18h]; this
0x1800a1e56  test    eax, eax
0x1800a1e58  jns     short loc_1800A1E6F
0x1800a1e5a  mov     r9d, eax; char *
0x1800a1e5d  lea     r8, aOnecoreuapWind_185; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800a1e64  mov     edx, 73h ; 's'; void *
0x1800a1e69  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1e6f  mov     [rbp+arg_8], 0
0x1800a1e77  mov     rdi, [rsi]
0x1800a1e7a  mov     rax, [rdi]
0x1800a1e7d  mov     rbx, [rax+18h]
0x1800a1e81  lea     rcx, [rbp+arg_8]
0x1800a1e85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a1e8a  lea     rdx, [rbp+arg_8]
0x1800a1e8e  mov     rcx, rdi
0x1800a1e91  mov     rax, rbx
0x1800a1e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e99  mov     rcx, [rbp+18h]; this
0x1800a1e9d  test    eax, eax
0x1800a1e9f  jns     short loc_1800A1EB6
0x1800a1ea1  mov     r9d, eax; char *
0x1800a1ea4  lea     r8, aOnecoreuapWind_185; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800a1eab  mov     edx, 77h ; 'w'; void *
0x1800a1eb0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1eb6  mov     rcx, [rbp+arg_8]
0x1800a1eba  mov     rax, [rcx]
0x1800a1ebd  mov     r9d, 1
0x1800a1ec3  mov     r8, [rsi+18h]
0x1800a1ec7  lea     rdx, aSystemInputTes_0; "System\\Input\\TestCommandsEndpoint"
0x1800a1ece  mov     rax, [rax+28h]
0x1800a1ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1ed7  mov     rcx, [rbp+18h]; this
0x1800a1edb  test    eax, eax
0x1800a1edd  jns     short loc_1800A1EF4
0x1800a1edf  mov     r9d, eax; char *
0x1800a1ee2  lea     r8, aOnecoreuapWind_185; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800a1ee9  mov     edx, 7Ch ; '|'; void *
0x1800a1eee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800a1ef4  mov     rcx, [rbp+arg_8]
0x1800a1ef8  test    rcx, rcx
0x1800a1efb  jz      short loc_1800A1F12
0x1800a1efd  mov     [rbp+arg_8], 0
0x1800a1f05  mov     rax, [rcx]
0x1800a1f08  mov     rax, [rax+10h]
0x1800a1f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f11  nop
0x1800a1f12  mov     rcx, [rbp+hMem]; hMem
0x1800a1f16  test    rcx, rcx
0x1800a1f19  jz      short loc_1800A1F2F
0x1800a1f1b  cmp     [rbp+var_8], 0
0x1800a1f1f  jz      short loc_1800A1F29
0x1800a1f21  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800a1f27  jmp     short loc_1800A1F2F
0x1800a1f29  call    cs:__imp_LocalFree
0x1800a1f2f  mov     rbx, [rsp+40h+arg_0]
0x1800a1f34  mov     rsi, [rsp+40h+arg_10]
0x1800a1f39  add     rsp, 40h
0x1800a1f3d  pop     r14
0x1800a1f3f  pop     rdi
0x1800a1f40  pop     rbp
0x1800a1f41  retn
```
