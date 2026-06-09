# win_musl::consumption::AppxXmlPreprocessor::Error(win_musl::consumption::SaxLocator &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,long)

- ea: `0x1800ee768`
- end: `0x1800ee831`
- name: `?Error@AppxXmlPreprocessor@consumption@win_musl@@QEAA?AW4type@SaxResponse@23@AEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ee150`

## callees

- `0x180006f30`
- `0x1800afe88`
- `0x1800ccb58`
- `0x1800ccc30`
- `0x1800ee768`
- `0x1800ee838`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee7ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ee7ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_musl::consumption::AppxXmlPreprocessor::Error(
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
  return win_musl::consumption::SaxErrorHandler::Error(a1 + 64, a2, a3, a4);
}

```

## disassembly

```asm
0x1800ee768  mov     rax, rsp
0x1800ee76b  push    rsi
0x1800ee76c  push    rdi
0x1800ee76d  push    r14
0x1800ee76f  sub     rsp, 30h
0x1800ee773  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800ee77b  mov     [rax+10h], rbx
0x1800ee77f  mov     [rax+18h], rbp
0x1800ee783  mov     r14d, r9d
0x1800ee786  mov     rbp, r8
0x1800ee789  mov     rsi, rdx
0x1800ee78c  mov     rdi, rcx
0x1800ee78f  lea     rdx, [rax+8]
0x1800ee793  mov     rcx, rsi
0x1800ee796  call    ?GetInterface@OpcPartContent@win_dox@@QEBA?AV?$scope@PEAUIOpcPartContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::OpcPartContent::GetInterface(void)
0x1800ee79b  or      ebx, 0FFFFFFFFh
0x1800ee79e  cmp     qword ptr [rax], 0
0x1800ee7a2  cmovnz  ebx, cs:dword_1801C4E80
0x1800ee7a9  mov     rcx, [rsp+48h+arg_0]
0x1800ee7ae  test    rcx, rcx
0x1800ee7b1  jz      short loc_1800EE7C0
0x1800ee7b3  mov     rax, [rcx]
0x1800ee7b6  mov     rax, [rax+10h]
0x1800ee7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ee7bf  nop
0x1800ee7c0  cmp     ebx, 0FFFFFFFFh
0x1800ee7c3  jz      short loc_1800EE7E1
0x1800ee7c5  mov     rbx, [rdi+50h]
0x1800ee7c9  mov     rcx, rsi; this
0x1800ee7cc  call    ?getLineNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getLineNumber(void)
0x1800ee7d1  mov     [rbx], eax
0x1800ee7d3  mov     rbx, [rdi+58h]
0x1800ee7d7  mov     rcx, rsi; this
0x1800ee7da  call    ?getColumnNumber@SaxLocator@consumption@win_musl@@QEAA_KXZ; win_musl::consumption::SaxLocator::getColumnNumber(void)
0x1800ee7df  mov     [rbx], eax
0x1800ee7e1  mov     rax, [rdi+48h]
0x1800ee7e5  mov     rcx, [rax]; pv
0x1800ee7e8  test    rcx, rcx
0x1800ee7eb  jz      short loc_1800EE7FE
0x1800ee7ed  call    cs:__imp_CoTaskMemFree
0x1800ee7f3  mov     rax, [rdi+48h]
0x1800ee7f7  mov     qword ptr [rax], 0
0x1800ee7fe  mov     rbx, [rdi+48h]
0x1800ee802  mov     rcx, rbp
0x1800ee805  call    ?AllocAndCopyString@win_dox@@YAPEA_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_dox::AllocAndCopyString(std::wstring const &)
0x1800ee80a  mov     [rbx], rax
0x1800ee80d  lea     rcx, [rdi+40h]
0x1800ee811  mov     r9d, r14d
0x1800ee814  mov     r8, rbp
0x1800ee817  mov     rdx, rsi
0x1800ee81a  mov     rbx, [rsp+48h+arg_8]
0x1800ee81f  mov     rbp, [rsp+48h+arg_10]
0x1800ee824  add     rsp, 30h
0x1800ee828  pop     r14
0x1800ee82a  pop     rdi
0x1800ee82b  pop     rsi
0x1800ee82c  jmp     ?Error@SaxErrorHandler@consumption@win_musl@@QEAA?AW4type@SaxResponse@23@AEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::Error(win_musl::consumption::SaxLocator &,std::wstring const &,long)
```
