# PackageNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800131d0`
- end: `0x1800133cf`
- name: `?Add@PackageNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x1800131d0`
- `0x180026dbc`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall PackageNode::Add(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 *a5, _DWORD *a6)
{
  __int64 result; // rax
  _DWORD *v9; // rax
  __int64 v10; // rbx
  int v11; // edi
  __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  _QWORD *v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a3 != 8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
      (const char *)0x86000011LL,
      v15);
    return 2248146961LL;
  }
  v9 = operator new(0xB0u, (const struct std::nothrow_t *)std::nothrow);
  try
  {
    v10 = (__int64)v9;
    if ( v9 )
    {
      v9[5] = 1;
      *(_QWORD *)v9 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'};
      *((_QWORD *)v9 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v10 = &AssetElementNode::`vftable'{for `ICSPNode'};
      *(_QWORD *)(v10 + 8) = &GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
      *(_QWORD *)(v10 + 24) = 0;
      *(_QWORD *)(v10 + 32) = 0;
      *(_QWORD *)(v10 + 64) = 7;
      *(_QWORD *)(v10 + 56) = 0;
      *(_WORD *)(v10 + 40) = 0;
      *(_QWORD *)(v10 + 96) = 7;
      *(_QWORD *)(v10 + 88) = 0;
      *(_WORD *)(v10 + 72) = 0;
      *(_QWORD *)(v10 + 128) = 7;
      *(_QWORD *)(v10 + 120) = 0;
      *(_WORD *)(v10 + 104) = 0;
      *(_QWORD *)(v10 + 160) = 7;
      *(_QWORD *)(v10 + 152) = 0;
      *(_WORD *)(v10 + 136) = 0;
      v11 = AssetElementNode::RuntimeClassInitialize(v10, a2, (_QWORD *)(a1 + 24), a1 + 56);
      v12 = *(_QWORD *)v10;
      if ( v11 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(v12 + 8))(v10);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *a6 = 0;
        if ( a5 )
        {
          v14 = 0;
          *a5 = v10;
        }
        else
        {
          v14 = v10;
        }
        if ( v14 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        return 0;
      }
      (*(void (__fastcall **)(__int64))(v12 + 16))(v10);
    }
    else
    {
      v11 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
      (const char *)(unsigned int)v11,
      0);
    if ( v16 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v16 + 16LL))(v16, *v16);
    result = (unsigned int)v11;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x41,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\packagenode.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800131d0  mov     [rsp+arg_0], rbx
0x1800131d5  mov     [rsp+arg_8], rsi
0x1800131da  push    rdi
0x1800131db  sub     rsp, 40h
0x1800131df  mov     rsi, rdx
0x1800131e2  mov     rdi, rcx
0x1800131e5  cmp     r8d, 8
0x1800131e9  jz      short loc_180013210
0x1800131eb  mov     rcx, [rsp+48h]; this
0x1800131f0  mov     ebx, 86000011h
0x1800131f5  mov     r9d, ebx; char *
0x1800131f8  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x1800131ff  mov     edx, 37h ; '7'; void *
0x180013204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013209  mov     eax, ebx
0x18001320b  jmp     loc_1800133BE
0x180013210  mov     qword ptr [rsp+48h+var_28], 0; int
0x180013219  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013220  mov     ecx, 0B0h; unsigned __int64
0x180013225  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001322a  mov     rbx, rax
0x18001322d  mov     [rsp+48h+var_20], rax
0x180013232  test    rax, rax
0x180013235  jnz     short loc_180013241
0x180013237  mov     edi, 8007000Eh
0x18001323c  jmp     loc_180013315
0x180013241  mov     dword ptr [rax+14h], 1
0x180013248  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6BICSPNode@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `ICSPNode'}
0x18001324f  mov     [rbx], rax
0x180013252  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UICSPNode@@UICSPNodeTransactioning@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,ICSPNode,ICSPNodeTransactioning>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180013259  mov     [rbx+8], rax
0x18001325d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180013264  test    rcx, rcx
0x180013267  jz      short loc_180013276
0x180013269  mov     rax, [rcx]
0x18001326c  mov     rax, [rax+8]
0x180013270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013275  nop
0x180013276  lea     rax, ??_7AssetElementNode@@6BICSPNode@@@; const AssetElementNode::`vftable'{for `ICSPNode'}
0x18001327d  mov     [rbx], rax
0x180013280  lea     rax, ??_7GenericIntNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const GenericIntNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x180013287  mov     [rbx+8], rax
0x18001328b  mov     qword ptr [rbx+18h], 0
0x180013293  mov     qword ptr [rbx+20h], 0
0x18001329b  mov     ecx, 7
0x1800132a0  mov     [rbx+40h], rcx
0x1800132a4  mov     qword ptr [rbx+38h], 0
0x1800132ac  xor     eax, eax
0x1800132ae  mov     [rbx+28h], ax
0x1800132b2  mov     [rbx+60h], rcx
0x1800132b6  mov     [rbx+58h], rax
0x1800132ba  mov     [rbx+48h], ax
0x1800132be  mov     [rbx+80h], rcx
0x1800132c5  mov     [rbx+78h], rax
0x1800132c9  mov     [rbx+68h], ax
0x1800132cd  mov     [rbx+0A0h], rcx
0x1800132d4  mov     [rbx+98h], rax
0x1800132db  mov     [rbx+88h], ax
0x1800132e2  mov     [rsp+48h+var_18], rbx
0x1800132e7  mov     [rsp+48h+var_20], rax
0x1800132ec  lea     r9, [rdi+38h]
0x1800132f0  lea     r8, [rdi+18h]
0x1800132f4  mov     rdx, rsi
0x1800132f7  mov     rcx, rbx
0x1800132fa  call    ?RuntimeClassInitialize@AssetElementNode@@QEAAJPEAUIConfigManager2URI@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; AssetElementNode::RuntimeClassInitialize(IConfigManager2URI *,std::wstring const &,std::wstring const &)
0x1800132ff  mov     edi, eax
0x180013301  mov     rax, [rbx]
0x180013304  test    edi, edi
0x180013306  jns     short loc_180013353
0x180013308  mov     rcx, rbx
0x18001330b  mov     rax, [rax+10h]
0x18001330f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013314  nop
0x180013315  mov     rcx, [rsp+48h]; this
0x18001331a  mov     r9d, edi; char *
0x18001331d  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\provcsp\\packa"...
0x180013324  mov     edx, 3Ah ; ':'; void *
0x180013329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001332e  nop
0x18001332f  mov     rcx, qword ptr [rsp+48h+var_28]
0x180013334  test    rcx, rcx
0x180013337  jz      short loc_18001334F
0x180013339  mov     qword ptr [rsp+48h+var_28], 0
0x180013342  mov     rdx, [rcx]
0x180013345  mov     rax, [rdx+10h]
0x180013349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001334e  nop
0x18001334f  mov     eax, edi
0x180013351  jmp     short loc_1800133BE
0x180013353  mov     rcx, rbx
0x180013356  mov     rax, [rax+8]
0x18001335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001335f  nop
0x180013360  mov     qword ptr [rsp+48h+var_28], rbx
0x180013365  mov     rax, [rbx]
0x180013368  mov     rcx, rbx
0x18001336b  mov     rax, [rax+10h]
0x18001336f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013374  nop
0x180013375  mov     rax, [rsp+48h+arg_28]
0x18001337a  mov     dword ptr [rax], 0
0x180013380  mov     rdx, [rsp+48h+arg_20]
0x180013385  test    rdx, rdx
0x180013388  jz      short loc_180013396
0x18001338a  mov     rax, qword ptr [rsp+48h+var_28]
0x18001338f  xor     ecx, ecx
0x180013391  mov     [rdx], rax
0x180013394  jmp     short loc_18001339B
0x180013396  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001339b  test    rcx, rcx
0x18001339e  jz      short loc_1800133B6
0x1800133a0  mov     qword ptr [rsp+48h+var_28], 0
0x1800133a9  mov     rax, [rcx]
0x1800133ac  mov     rax, [rax+10h]
0x1800133b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133b5  nop
0x1800133b6  xor     eax, eax
0x1800133b8  jmp     short loc_1800133BE
0x1800133ba  mov     eax, [rsp+48h+arg_10]
0x1800133be  mov     rbx, [rsp+48h+arg_0]
0x1800133c3  mov     rsi, [rsp+48h+arg_8]
0x1800133c8  add     rsp, 40h
0x1800133cc  pop     rdi
0x1800133cd  retn
```
