# win_musl::consumption::AppxXmlPreprocessor::FatalError(win_musl::consumption::SaxLocator &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,long)

- ea: `0x1800c1cec`
- end: `0x1800c1db5`
- name: `?FatalError@AppxXmlPreprocessor@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z`
- size: `201`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e2d0`
- `0x180042c88`
- `0x1800c1c40`

## callees

- `0x180006f30`
- `0x1800afe88`
- `0x1800bdff4`
- `0x1800c1cec`
- `0x1800ccb58`
- `0x1800ccc30`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c1d71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::AppxXmlPreprocessor::FatalError(
        __int64 a1,
        win_musl::consumption::SaxLocator *a2,
        __int64 a3,
        unsigned int a4)
{
  int v8; // ebx
  _DWORD *v9; // rbx
  _DWORD *v10; // rbx
  void *v11; // rcx
  void **v12; // rbx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v8 = -1;
  if ( *(_QWORD *)win_dox::OpcPartContent::GetInterface(a2, &v14) )
    v8 = dword_1801C4E80;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v8 != -1 )
  {
    v9 = *(_DWORD **)(a1 + 80);
    *v9 = win_musl::consumption::SaxLocator::getLineNumber(a2);
    v10 = *(_DWORD **)(a1 + 88);
    *v10 = win_musl::consumption::SaxLocator::getColumnNumber(a2);
  }
  v11 = **(void ***)(a1 + 72);
  if ( v11 )
  {
    CoTaskMemFree(v11);
    **(_QWORD **)(a1 + 72) = 0;
  }
  v12 = *(void ***)(a1 + 72);
  *v12 = win_dox::AllocAndCopyString(a3);
  return win_musl::consumption::SaxErrorHandler::FatalError(a1 + 64, a2, a3, a4);
}

```

## disassembly

```asm
0x1800c1cec  mov     rax, rsp
0x1800c1cef  push    rsi
0x1800c1cf0  push    rdi
0x1800c1cf1  push    r14
0x1800c1cf3  sub     rsp, 30h
0x1800c1cf7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800c1cff  mov     [rax+10h], rbx
0x1800c1d03  mov     [rax+18h], rbp
0x1800c1d07  mov     r14d, r9d
0x1800c1d0a  mov     rbp, r8
0x1800c1d0d  mov     rsi, rdx
0x1800c1d10  mov     rdi, rcx
0x1800c1d13  lea     rdx, [rax+8]
0x1800c1d17  mov     rcx, rsi
0x1800c1d1a  call    ?GetInterface@OpcPartContent@win_dox@@QEBA?AV?$scope@PEAUIOpcPartContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartContent::GetInterface(void)
0x1800c1d1f  or      ebx, 0FFFFFFFFh
0x1800c1d22  cmp     qword ptr [rax], 0
0x1800c1d26  cmovnz  ebx, cs:dword_1801C4E80
0x1800c1d2d  mov     rcx, [rsp+48h+arg_0]
0x1800c1d32  test    rcx, rcx
0x1800c1d35  jz      short loc_1800C1D44
0x1800c1d37  mov     rax, [rcx]
0x1800c1d3a  mov     rax, [rax+10h]
0x1800c1d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1d43  nop
0x1800c1d44  cmp     ebx, 0FFFFFFFFh
0x1800c1d47  jz      short loc_1800C1D65
0x1800c1d49  mov     rbx, [rdi+50h]
0x1800c1d4d  mov     rcx, rsi; this
0x1800c1d50  call    ?getLineNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getLineNumber(void)
0x1800c1d55  mov     [rbx], eax
0x1800c1d57  mov     rbx, [rdi+58h]
0x1800c1d5b  mov     rcx, rsi; this
0x1800c1d5e  call    ?getColumnNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getColumnNumber(void)
0x1800c1d63  mov     [rbx], eax
0x1800c1d65  mov     rax, [rdi+48h]
0x1800c1d69  mov     rcx, [rax]; pv
0x1800c1d6c  test    rcx, rcx
0x1800c1d6f  jz      short loc_1800C1D82
0x1800c1d71  call    cs:__imp_CoTaskMemFree
0x1800c1d77  mov     rax, [rdi+48h]
0x1800c1d7b  mov     qword ptr [rax], 0
0x1800c1d82  mov     rbx, [rdi+48h]
0x1800c1d86  mov     rcx, rbp
0x1800c1d89  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800c1d8e  mov     [rbx], rax
0x1800c1d91  lea     rcx, [rdi+40h]
0x1800c1d95  mov     r9d, r14d
0x1800c1d98  mov     r8, rbp
0x1800c1d9b  mov     rdx, rsi
0x1800c1d9e  mov     rbx, [rsp+48h+arg_8]
0x1800c1da3  mov     rbp, [rsp+48h+arg_10]
0x1800c1da8  add     rsp, 30h
0x1800c1dac  pop     r14
0x1800c1dae  pop     rdi
0x1800c1daf  pop     rsi
0x1800c1db0  jmp     ?FatalError@SaxErrorHandler@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::FatalError(win_musl::consumption::SaxLocator &,std::wstring const &,long)
```
