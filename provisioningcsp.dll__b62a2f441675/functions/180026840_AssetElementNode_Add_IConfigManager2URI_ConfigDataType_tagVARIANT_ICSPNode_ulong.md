# AssetElementNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180026840`
- end: `0x180026b64`
- name: `?Add@AssetElementNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000918c`
- `0x180009fac`
- `0x180026840`
- `0x1800277c4`
- `0x1800287dc`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002693b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026aac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026b2b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002693b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026aac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026b2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall AssetElementNode::Add(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 *a5, _DWORD *a6)
{
  _WORD *v9; // rdx
  __int64 v10; // r8
  _DWORD *v11; // rax
  __int64 v12; // rbx
  int v13; // edi
  int v14; // esi
  unsigned int v15; // r14d
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  int lpFileName; // [rsp+20h] [rbp-C8h]
  WCHAR FileName[4]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v21; // [rsp+70h] [rbp-78h]
  unsigned __int64 v22; // [rsp+78h] [rbp-70h]
  void *v23; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int64 v24; // [rsp+98h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( a3 != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)0x86000011LL,
      lpFileName);
    return 2248146961LL;
  }
  if ( *(_WORD *)a4 != 8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)0x80070057LL,
      lpFileName);
    return 2147942487LL;
  }
  v9 = *(_WORD **)(a4 + 8);
  v22 = 7;
  v21 = 0;
  FileName[0] = 0;
  if ( *v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
  }
  std::wstring::assign(FileName, v9);
  AssetElementNode::_GetFullDestination(a1, &v23, (__int64)FileName);
  if ( v22 >= 8 )
    operator delete(*(void **)FileName);
  v22 = 7;
  v21 = 0;
  FileName[0] = 0;
  v11 = operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  v12 = (__int64)v11;
  if ( !v11 )
  {
    v13 = -2147024882;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v13,
      lpFileName);
    if ( v24 >= 8 )
      operator delete(v23);
    return (unsigned int)v13;
  }
  v11[5] = 1;
  *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
  *((_QWORD *)v11 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v12 = &AssetNode::`vftable'{for `ICSPNode'};
  *(_QWORD *)(v12 + 8) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  *(_QWORD *)(v12 + 48) = 7;
  *(_QWORD *)(v12 + 40) = 0;
  *(_WORD *)(v12 + 24) = 0;
  v14 = *(_DWORD *)(a1 + 172);
  v15 = *(_DWORD *)(a1 + 168);
  v22 = 7;
  v21 = 0;
  FileName[0] = 0;
  std::wstring::assign(FileName);
  v13 = AssetNode::RuntimeClassInitialize(v12, a2, v16, (_QWORD *)(a1 + 32), FileName, v15, v14);
  v17 = *(_QWORD *)v12;
  if ( v13 < 0 )
  {
    (*(void (__fastcall **)(__int64))(v17 + 16))(v12);
    goto LABEL_16;
  }
  (*(void (__fastcall **)(__int64))(v17 + 8))(v12);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  *a6 = 0;
  if ( a5 )
  {
    v18 = 0;
    *a5 = v12;
  }
  else
  {
    v18 = v12;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v24 >= 8 )
    operator delete(v23);
  return 0;
}

```

## disassembly

```asm
0x180026840  push    rbx
0x180026842  push    rsi
0x180026843  push    rdi
0x180026844  push    r12
0x180026846  push    r13
0x180026848  push    r14
0x18002684a  push    r15
0x18002684c  sub     rsp, 0B0h
0x180026853  mov     rax, cs:__security_cookie
0x18002685a  xor     rax, rsp
0x18002685d  mov     [rsp+0E8h+var_48], rax
0x180026865  mov     r12, rdx
0x180026868  mov     rdi, rcx
0x18002686b  mov     r15, [rsp+0E8h+arg_20]
0x180026873  mov     r13, [rsp+0E8h+arg_28]
0x18002687b  cmp     r8d, 1
0x18002687f  jz      short loc_1800268A9
0x180026881  mov     rcx, [rsp+0E8h]; this
0x180026889  mov     ebx, 86000011h
0x18002688e  mov     r9d, ebx; char *
0x180026891  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026898  mov     edx, 42h ; 'B'; void *
0x18002689d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268a2  mov     eax, ebx
0x1800268a4  jmp     loc_180026B40
0x1800268a9  mov     r14d, 8
0x1800268af  cmp     [r9], r14w
0x1800268b3  jz      short loc_1800268DC
0x1800268b5  mov     rcx, [rsp+0E8h]; this
0x1800268bd  mov     ebx, 80070057h
0x1800268c2  mov     r9d, ebx; char *
0x1800268c5  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800268cc  lea     edx, [r14+3Bh]; void *
0x1800268d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800268d5  mov     eax, ebx
0x1800268d7  jmp     loc_180026B40
0x1800268dc  mov     rdx, [r9+8]; Src
0x1800268e0  mov     ebx, 7
0x1800268e5  mov     [rsp+0E8h+var_70], rbx
0x1800268ea  xor     esi, esi
0x1800268ec  mov     [rsp+0E8h+var_78], rsi
0x1800268f1  mov     [rsp+0E8h+FileName], si
0x1800268f6  cmp     [rdx], si
0x1800268f9  jnz     short loc_180026900
0x1800268fb  mov     r8d, esi
0x1800268fe  jmp     short loc_18002690E
0x180026900  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026904  inc     r8
0x180026907  cmp     [rdx+r8*2], si
0x18002690c  jnz     short loc_180026904
0x18002690e  lea     rcx, [rsp+0E8h+FileName]; void *
0x180026913  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180026918  nop
0x180026919  lea     r8, [rsp+0E8h+FileName]
0x18002691e  lea     rdx, [rsp+0E8h+var_68]
0x180026926  mov     rcx, rdi
0x180026929  call    ?_GetFullDestination@AssetElementNode@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; AssetElementNode::_GetFullDestination(std::wstring const &)
0x18002692e  nop
0x18002692f  cmp     [rsp+0E8h+var_70], r14
0x180026934  jb      short loc_180026947
0x180026936  mov     rcx, qword ptr [rsp+0E8h+FileName]
0x18002693b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026942  nop     dword ptr [rax+rax+00h]
0x180026947  mov     [rsp+0E8h+var_70], rbx
0x18002694c  mov     [rsp+0E8h+var_78], rsi
0x180026951  mov     [rsp+0E8h+FileName], si
0x180026956  mov     [rsp+0E8h+var_A8], rsi
0x18002695b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026962  mov     ecx, 38h ; '8'; unsigned __int64
0x180026967  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002696c  mov     rbx, rax
0x18002696f  mov     [rsp+0E8h+var_98], rax
0x180026974  test    rax, rax
0x180026977  jnz     short loc_180026983
0x180026979  mov     edi, 8007000Eh
0x18002697e  jmp     loc_180026A61
0x180026983  mov     dword ptr [rax+14h], 1
0x18002698a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x180026991  mov     [rbx], rax
0x180026994  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x18002699b  mov     [rbx+8], rax
0x18002699f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800269a6  test    rcx, rcx
0x1800269a9  jz      short loc_1800269B8
0x1800269ab  mov     rax, [rcx]
0x1800269ae  mov     rax, [rax+8]
0x1800269b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269b7  nop
0x1800269b8  lea     rax, ??_7AssetNode@@6BICSPNode@@@; const AssetNode::`vftable'{for `ICSPNode'}
0x1800269bf  mov     [rbx], rax
0x1800269c2  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800269c9  mov     [rbx+8], rax
0x1800269cd  mov     ecx, 7
0x1800269d2  mov     [rbx+30h], rcx
0x1800269d6  mov     [rbx+28h], rsi
0x1800269da  mov     [rbx+18h], si
0x1800269de  mov     [rsp+0E8h+var_A0], rbx
0x1800269e3  mov     [rsp+0E8h+var_98], rsi
0x1800269e8  mov     esi, [rdi+0ACh]
0x1800269ee  mov     r14d, [rdi+0A8h]
0x1800269f5  mov     [rsp+0E8h+var_70], rcx
0x1800269fa  mov     [rsp+0E8h+var_78], 0
0x180026a03  xor     eax, eax
0x180026a05  mov     [rsp+0E8h+FileName], ax
0x180026a0a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180026a0e  xor     r8d, r8d
0x180026a11  lea     rdx, [rsp+0E8h+var_68]
0x180026a19  lea     rcx, [rsp+0E8h+FileName]; void *
0x180026a1e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180026a23  lea     r9, [rdi+20h]; int
0x180026a27  mov     [rsp+0E8h+var_B8], esi; int
0x180026a2b  mov     [rsp+0E8h+var_C0], r14d; int
0x180026a30  lea     rax, [rsp+0E8h+FileName]
0x180026a35  mov     [rsp+0E8h+lpFileName], rax; int
0x180026a3a  mov     rdx, r12; int
0x180026a3d  mov     rcx, rbx; int
0x180026a40  call    ?RuntimeClassInitialize@AssetNode@@QEAAJPEAUIConfigManager2URI@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_ptr@UIElement@@U?$ProvReleaser@UIElement@@@@@4@V34@HH@Z; AssetNode::RuntimeClassInitialize(IConfigManager2URI *,std::wstring const &,std::unique_ptr<IElement,ProvReleaser<IElement>> const &,std::wstring,int,int)
0x180026a45  mov     edi, eax
0x180026a47  mov     rax, [rbx]
0x180026a4a  xor     esi, esi
0x180026a4c  test    edi, edi
0x180026a4e  jns     short loc_180026ABF
0x180026a50  mov     rcx, rbx
0x180026a53  mov     rax, [rax+10h]
0x180026a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a5c  nop
0x180026a5d  lea     r14d, [rsi+8]
0x180026a61  mov     rcx, [rsp+0E8h]; this
0x180026a69  mov     r9d, edi; char *
0x180026a6c  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026a73  mov     edx, 48h ; 'H'; void *
0x180026a78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a7d  nop
0x180026a7e  mov     rcx, [rsp+0E8h+var_A8]
0x180026a83  test    rcx, rcx
0x180026a86  jz      short loc_180026A9A
0x180026a88  mov     [rsp+0E8h+var_A8], rsi
0x180026a8d  mov     rax, [rcx]
0x180026a90  mov     rax, [rax+10h]
0x180026a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a99  nop
0x180026a9a  cmp     [rsp+0E8h+var_50], r14
0x180026aa2  jb      short loc_180026AB8
0x180026aa4  mov     rcx, [rsp+0E8h+var_68]
0x180026aac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026ab3  nop     dword ptr [rax+rax+00h]
0x180026ab8  mov     eax, edi
0x180026aba  jmp     loc_180026B40
0x180026abf  mov     rcx, rbx
0x180026ac2  mov     rax, [rax+8]
0x180026ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026acb  nop
0x180026acc  mov     [rsp+0E8h+var_A8], rbx
0x180026ad1  mov     rax, [rbx]
0x180026ad4  mov     rcx, rbx
0x180026ad7  mov     rax, [rax+10h]
0x180026adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ae0  nop
0x180026ae1  mov     [r13+0], esi
0x180026ae5  test    r15, r15
0x180026ae8  jz      short loc_180026AFC
0x180026aea  mov     rax, [rsp+0E8h+var_A8]
0x180026aef  mov     rcx, rsi
0x180026af2  mov     [rsp+0E8h+var_A8], rcx
0x180026af7  mov     [r15], rax
0x180026afa  jmp     short loc_180026B01
0x180026afc  mov     rcx, [rsp+0E8h+var_A8]
0x180026b01  test    rcx, rcx
0x180026b04  jz      short loc_180026B18
0x180026b06  mov     [rsp+0E8h+var_A8], rsi
0x180026b0b  mov     rax, [rcx]
0x180026b0e  mov     rax, [rax+10h]
0x180026b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b17  nop
0x180026b18  cmp     [rsp+0E8h+var_50], 8
0x180026b21  jb      short loc_180026B38
0x180026b23  mov     rcx, [rsp+0E8h+var_68]
0x180026b2b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026b32  nop     dword ptr [rax+rax+00h]
0x180026b37  nop
0x180026b38  xor     eax, eax
0x180026b3a  jmp     short loc_180026B40
0x180026b3c  mov     eax, dword ptr [rsp+0E8h+var_A8]
0x180026b40  mov     rcx, [rsp+0E8h+var_48]
0x180026b48  xor     rcx, rsp; StackCookie
0x180026b4b  call    __security_check_cookie
0x180026b50  add     rsp, 0B0h
0x180026b57  pop     r15
0x180026b59  pop     r14
0x180026b5b  pop     r13
0x180026b5d  pop     r12
0x180026b5f  pop     rdi
0x180026b60  pop     rsi
0x180026b61  pop     rbx
0x180026b62  retn
```
