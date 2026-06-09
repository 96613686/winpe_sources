# ExpeditedUpdateUSOTask::_FilterUpdates(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,std::vector<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>,std::allocator<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>> &)

- ea: `0x18007c614`
- end: `0x18007c880`
- name: `?_FilterUpdates@ExpeditedUpdateUSOTask@@AEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@AEAV?$vector@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180079120`

## callees

- `0x180008544`
- `0x18001ad08`
- `0x18002f39c`
- `0x1800418d8`
- `0x180043c58`
- `0x180078124`
- `0x18007c614`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c726`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007c726`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c716`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c716`

## string_xrefs

- `0x18007c669`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007c818`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007c83c`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007c860`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007c7f0`: `ExpeditedUpdateUSOTask updates count after filtering %d`
- `0x18007c630`: `ExpeditedUpdateUSOTask Filtering Expedited Update collection`
- `0x18007c685`: `ExpeditedUpdateUSOTask updates count %ld`
- `0x18007c75f`: `ExpeditedUpdateUSOTask Update added: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ExpeditedUpdateUSOTask::_FilterUpdates(__int64 a1, __int64 a2, __int64 *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v9; // esi
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  UINT v15; // eax
  HRESULT v16; // eax
  __int64 v17; // rdi
  __int64 *v18; // rdx
  BSTR pbstr; // [rsp+20h] [rbp-20h] BYREF
  __int64 v20; // [rsp+28h] [rbp-18h] BYREF
  HSTRING string; // [rsp+30h] [rbp-10h] BYREF
  __int64 v22; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char v24; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v25; // [rsp+88h] [rbp+48h] BYREF

  UnattendLogW(0, L"ExpeditedUpdateUSOTask Filtering Expedited Update collection");
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 672) + 32LL))(*(_QWORD *)(a1 + 672), &v25);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v6,
      (int)pbstr);
    return v7;
  }
  UnattendLogW(0, L"ExpeditedUpdateUSOTask updates count %ld", v25);
  v9 = 0;
  if ( v25 )
  {
    while ( 1 )
    {
      v20 = 0;
      v10 = *(__int64 **)(a1 + 672);
      v11 = *v10;
      v20 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v11 + 24))(v10, v9, &v20);
      v7 = v12;
      if ( v12 < 0 )
        break;
      pbstr = 0;
      v13 = *(_QWORD *)v20;
      pbstr = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(v13 + 112))(v20, &pbstr);
      v7 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B7,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v14,
          (int)pbstr);
        goto LABEL_20;
      }
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v15 = SysStringLen(pbstr);
      v16 = WindowsCreateString(pbstr, v15, &string);
      v7 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
          (const char *)(unsigned int)v16,
          (int)pbstr);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_20:
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
        goto LABEL_22;
      }
      v24 = 0;
      if ( (*(int (__fastcall **)(__int64, HSTRING, char *))(*(_QWORD *)a2 + 64LL))(a2, string, &v24) >= 0 && v24 )
      {
        UnattendLogW(0, L"ExpeditedUpdateUSOTask Update added: %s", pbstr);
        v17 = v20;
        v22 = v20;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        v18 = (__int64 *)a3[1];
        if ( v18 == (__int64 *)a3[2] )
        {
          std::vector<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>(
            a3,
            (__int64)v18,
            &v22);
        }
        else
        {
          v22 = 0;
          *v18 = v17;
          a3[1] += 8;
        }
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v22);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pbstr);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
      if ( ++v9 >= v25 )
        goto LABEL_17;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B5,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)(unsigned int)v12,
      (int)pbstr);
LABEL_22:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
    return v7;
  }
LABEL_17:
  UnattendLogW(0, L"ExpeditedUpdateUSOTask updates count after filtering %d", (a3[1] - *a3) >> 3);
  return 0;
}

```

## disassembly

```asm
0x18007c614  mov     [rsp-28h+arg_8], rbx
0x18007c619  push    rbp
0x18007c61a  push    rsi
0x18007c61b  push    rdi
0x18007c61c  push    r14
0x18007c61e  push    r15
0x18007c620  mov     rbp, rsp
0x18007c623  sub     rsp, 40h
0x18007c627  mov     rbx, r8
0x18007c62a  mov     r14, rdx
0x18007c62d  mov     r15, rcx
0x18007c630  lea     rdx, aExpeditedupdat_4; "ExpeditedUpdateUSOTask Filtering Expedi"...
0x18007c637  xor     ecx, ecx
0x18007c639  call    UnattendLogW
0x18007c63e  mov     [rbp+arg_18], 0
0x18007c645  mov     rcx, [r15+2A0h]
0x18007c64c  mov     rax, [rcx]
0x18007c64f  lea     rdx, [rbp+arg_18]
0x18007c653  mov     rax, [rax+20h]
0x18007c657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c65c  mov     edi, eax
0x18007c65e  test    eax, eax
0x18007c660  jns     short loc_18007C681
0x18007c662  mov     rcx, [rbp+28h]; this
0x18007c666  mov     r9d, eax; char *
0x18007c669  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007c670  mov     edx, 1B0h; void *
0x18007c675  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c67a  mov     eax, edi
0x18007c67c  jmp     loc_18007C800
0x18007c681  mov     r8d, [rbp+arg_18]
0x18007c685  lea     rdx, aExpeditedupdat_37; "ExpeditedUpdateUSOTask updates count %l"...
0x18007c68c  xor     ecx, ecx
0x18007c68e  call    UnattendLogW
0x18007c693  xor     esi, esi
0x18007c695  cmp     [rbp+arg_18], esi
0x18007c698  jbe     loc_18007C7E5
0x18007c69e  mov     [rbp+var_18], 0
0x18007c6a6  mov     rcx, [r15+2A0h]
0x18007c6ad  mov     rax, [rcx]
0x18007c6b0  mov     [rbp+var_18], 0
0x18007c6b8  lea     r8, [rbp+var_18]
0x18007c6bc  mov     edx, esi
0x18007c6be  mov     rax, [rax+18h]
0x18007c6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6c7  mov     edi, eax
0x18007c6c9  test    eax, eax
0x18007c6cb  js      loc_18007C859
0x18007c6d1  mov     [rbp+pbstr], 0
0x18007c6d9  mov     rcx, [rbp+var_18]
0x18007c6dd  mov     rax, [rcx]
0x18007c6e0  mov     [rbp+pbstr], 0
0x18007c6e8  lea     rdx, [rbp+pbstr]
0x18007c6ec  mov     rax, [rax+70h]
0x18007c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6f5  mov     edi, eax
0x18007c6f7  test    eax, eax
0x18007c6f9  js      loc_18007C835
0x18007c6ff  mov     [rbp+string], 0
0x18007c707  xor     edx, edx
0x18007c709  lea     rcx, [rbp+string]
0x18007c70d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007c712  mov     rcx, [rbp+pbstr]; pbstr
0x18007c716  call    cs:__imp_SysStringLen
0x18007c71c  lea     r8, [rbp+string]; string
0x18007c720  mov     edx, eax; length
0x18007c722  mov     rcx, [rbp+pbstr]; sourceString
0x18007c726  call    cs:__imp_WindowsCreateString
0x18007c72c  mov     edi, eax
0x18007c72e  test    eax, eax
0x18007c730  js      loc_18007C811
0x18007c736  mov     [rbp+arg_0], 0
0x18007c73a  mov     rax, [r14]
0x18007c73d  lea     r8, [rbp+arg_0]
0x18007c741  mov     rdx, [rbp+string]
0x18007c745  mov     rcx, r14
0x18007c748  mov     rax, [rax+40h]
0x18007c74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c751  test    eax, eax
0x18007c753  js      short loc_18007C7BD
0x18007c755  cmp     [rbp+arg_0], 0
0x18007c759  jz      short loc_18007C7BD
0x18007c75b  mov     r8, [rbp+pbstr]
0x18007c75f  lea     rdx, aExpeditedupdat_11; "ExpeditedUpdateUSOTask Update added: %s"
0x18007c766  xor     ecx, ecx
0x18007c768  call    UnattendLogW
0x18007c76d  mov     rdi, [rbp+var_18]
0x18007c771  mov     [rbp+var_8], rdi
0x18007c775  test    rdi, rdi
0x18007c778  jz      short loc_18007C78A
0x18007c77a  mov     rax, [rdi]
0x18007c77d  mov     rcx, rdi
0x18007c780  mov     rax, [rax+8]
0x18007c784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c789  nop
0x18007c78a  mov     rdx, [rbx+8]
0x18007c78e  cmp     rdx, [rbx+10h]
0x18007c792  jz      short loc_18007C7A6
0x18007c794  mov     [rbp+var_8], 0
0x18007c79c  mov     [rdx], rdi
0x18007c79f  add     qword ptr [rbx+8], 8
0x18007c7a4  jmp     short loc_18007C7B3
0x18007c7a6  lea     r8, [rbp+var_8]
0x18007c7aa  mov     rcx, rbx
0x18007c7ad  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIMoUsoUpdate@@Uerr_returncode_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy>>(wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> * const,wil::com_ptr_t<IMoUsoUpdate,wil::err_returncode_policy> &&)
0x18007c7b2  nop
0x18007c7b3  lea     rcx, [rbp+var_8]
0x18007c7b7  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007c7bc  nop
0x18007c7bd  lea     rcx, [rbp+string]; this
0x18007c7c1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007c7c6  nop
0x18007c7c7  lea     rcx, [rbp+pbstr]
0x18007c7cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007c7d0  nop
0x18007c7d1  lea     rcx, [rbp+var_18]
0x18007c7d5  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007c7da  inc     esi
0x18007c7dc  cmp     esi, [rbp+arg_18]
0x18007c7df  jb      loc_18007C69E
0x18007c7e5  mov     r8, [rbx+8]
0x18007c7e9  sub     r8, [rbx]
0x18007c7ec  sar     r8, 3
0x18007c7f0  lea     rdx, aExpeditedupdat_40; "ExpeditedUpdateUSOTask updates count af"...
0x18007c7f7  xor     ecx, ecx
0x18007c7f9  call    UnattendLogW
0x18007c7fe  xor     eax, eax
0x18007c800  mov     rbx, [rsp+40h+arg_8]
0x18007c805  add     rsp, 40h
0x18007c809  pop     r15
0x18007c80b  pop     r14
0x18007c80d  pop     rdi
0x18007c80e  pop     rsi
0x18007c80f  pop     rbp
0x18007c810  retn
0x18007c811  mov     rcx, [rbp+28h]; this
0x18007c815  mov     r9d, eax; char *
0x18007c818  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007c81f  mov     edx, 1B9h; void *
0x18007c824  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c829  nop
0x18007c82a  lea     rcx, [rbp+string]; this
0x18007c82e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007c833  jmp     short loc_18007C84E
0x18007c835  mov     rcx, [rbp+28h]; this
0x18007c839  mov     r9d, eax; char *
0x18007c83c  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007c843  mov     edx, 1B7h; void *
0x18007c848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c84d  nop
0x18007c84e  lea     rcx, [rbp+pbstr]
0x18007c852  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007c857  jmp     short loc_18007C872
0x18007c859  mov     rcx, [rbp+28h]; this
0x18007c85d  mov     r9d, eax; char *
0x18007c860  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007c867  mov     edx, 1B5h; void *
0x18007c86c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c871  nop
0x18007c872  lea     rcx, [rbp+var_18]
0x18007c876  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007c87b  jmp     loc_18007C67A
```
