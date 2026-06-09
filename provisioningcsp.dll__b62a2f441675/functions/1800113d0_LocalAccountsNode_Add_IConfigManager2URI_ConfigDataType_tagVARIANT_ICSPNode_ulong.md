# LocalAccountsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800113d0`
- end: `0x180011629`
- name: `?Add@LocalAccountsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `601`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000fffc`
- `0x1800113d0`
- `0x180025e18`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LocalAccountsNode::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  int v7; // ebx
  __int64 v8; // rdx
  GenericBStrNode *v10; // rax
  GenericBStrNode *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // rax
  GenericBStrNode *v14; // rcx
  int v15; // eax
  int v16; // [rsp+20h] [rbp-20h]
  __int64 v17; // [rsp+20h] [rbp-20h]
  GenericBStrNode *v18; // [rsp+20h] [rbp-20h]
  __int64 v19; // [rsp+20h] [rbp-20h]
  __int64 v20; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v21[3]; // [rsp+28h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int v23; // [rsp+58h] [rbp+18h] BYREF

  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v23);
  if ( v7 < 0 )
  {
    v8 = 62;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\localaccountsnode.cpp",
      (const char *)(unsigned int)v7,
      v16);
    return (unsigned int)v7;
  }
  if ( v23 != 1 )
  {
    v7 = -2147024809;
    v8 = 63;
    goto LABEL_3;
  }
  v21[0] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(a2, 0, v21);
  if ( v7 < 0 )
  {
    v8 = 66;
    goto LABEL_3;
  }
  v10 = (GenericBStrNode *)operator new(0x58u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    v12 = -2147024882;
    goto LABEL_13;
  }
  GenericBStrNode::GenericBStrNode(v10);
  *(_QWORD *)v11 = &UserAccountNode::`vftable'{for `ICSPNode'};
  *((_QWORD *)v11 + 1) = &UserAccountNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'};
  *((_QWORD *)v11 + 8) = 0;
  *((_QWORD *)v11 + 9) = 0;
  *((_QWORD *)v11 + 10) = 0;
  v21[1] = (unsigned __int16 *)v11;
  v21[2] = 0;
  v12 = UserAccountNode::RuntimeClassInitialize(v11, v21[0]);
  v13 = *(_QWORD *)v11;
  if ( (v12 & 0x80000000) != 0 )
  {
    (*(void (__fastcall **)(GenericBStrNode *))(v13 + 16))(v11);
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\localaccountsnode.cpp",
      (const char *)v12,
      0);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    return v12;
  }
  (*(void (__fastcall **)(GenericBStrNode *))(v13 + 8))(v11);
  v18 = v11;
  (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)v11 + 16LL))(v11);
  v14 = v11;
  if ( !v11 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\localaccountsnode.cpp",
      (const char *)0x8007000ELL,
      0);
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    return v12;
  }
  if ( a5 )
  {
    v15 = (**(__int64 (__fastcall ***)(GenericBStrNode *, GUID *))v11)(v11, &GUID_8a13633c_797d_46e9_b602_d982b8ec9847);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\localaccountsnode.cpp",
        (const char *)(unsigned int)v15,
        (int)v18);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      return (unsigned int)v7;
    }
    v14 = v18;
  }
  *a6 |= 2u;
  if ( v14 )
    (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)v14 + 16LL))(v14);
  return 0;
}

```

## disassembly

```asm
0x1800113d0  mov     [rsp-8+arg_0], rbx
0x1800113d5  mov     [rsp-8+arg_10], rdi
0x1800113da  push    rbp
0x1800113db  mov     rbp, rsp
0x1800113de  sub     rsp, 40h
0x1800113e2  mov     rdi, rdx
0x1800113e5  mov     [rbp+arg_8], 0
0x1800113ec  mov     rax, [rdx]
0x1800113ef  lea     rdx, [rbp+arg_8]
0x1800113f3  mov     rcx, rdi
0x1800113f6  mov     rax, [rax+88h]
0x1800113fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011402  mov     ebx, eax
0x180011404  test    eax, eax
0x180011406  jns     short loc_180011427
0x180011408  mov     edx, 3Eh ; '>'; void *
0x18001140d  mov     rcx, [rbp+8]; this
0x180011411  mov     r9d, ebx; char *
0x180011414  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\provcsp\\local"...
0x18001141b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011420  mov     eax, ebx
0x180011422  jmp     loc_180011618
0x180011427  cmp     [rbp+arg_8], 1
0x18001142b  jz      short loc_180011439
0x18001142d  mov     ebx, 80070057h
0x180011432  mov     edx, 3Fh ; '?'
0x180011437  jmp     short loc_18001140D
0x180011439  mov     [rbp+var_18], 0
0x180011441  mov     rax, [rdi]
0x180011444  lea     r8, [rbp+var_18]
0x180011448  xor     edx, edx
0x18001144a  mov     rcx, rdi
0x18001144d  mov     rax, [rax+58h]
0x180011451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011456  mov     ebx, eax
0x180011458  test    eax, eax
0x18001145a  jns     short loc_180011463
0x18001145c  mov     edx, 42h ; 'B'
0x180011461  jmp     short loc_18001140D
0x180011463  mov     [rbp+var_20], 0
0x18001146b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011472  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011477  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001147c  mov     rbx, rax
0x18001147f  test    rax, rax
0x180011482  jnz     short loc_18001148B
0x180011484  mov     edi, 8007000Eh
0x180011489  jmp     short loc_1800114EE
0x18001148b  mov     rcx, rbx; this
0x18001148e  call    ??0GenericBStrNode@@QEAA@XZ; GenericBStrNode::GenericBStrNode(void)
0x180011493  lea     rax, ??_7UserAccountNode@@6BICSPNode@@@; const UserAccountNode::`vftable'{for `ICSPNode'}
0x18001149a  mov     [rbx], rax
0x18001149d  lea     rax, ??_7UserAccountNode@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UICSPNodeTransactioning@@@Details@WRL@Microsoft@@@; const UserAccountNode::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,ICSPNodeTransactioning>'}
0x1800114a4  mov     [rbx+8], rax
0x1800114a8  mov     qword ptr [rbx+40h], 0
0x1800114b0  mov     qword ptr [rbx+48h], 0
0x1800114b8  mov     qword ptr [rbx+50h], 0
0x1800114c0  mov     [rbp+var_10], rbx
0x1800114c4  mov     [rbp+var_8], 0
0x1800114cc  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800114d0  mov     rcx, rbx; this
0x1800114d3  call    ?RuntimeClassInitialize@UserAccountNode@@QEAAJPEBG@Z; UserAccountNode::RuntimeClassInitialize(ushort const *)
0x1800114d8  mov     edi, eax
0x1800114da  mov     rax, [rbx]
0x1800114dd  test    edi, edi
0x1800114df  jns     short loc_18001152C
0x1800114e1  mov     rcx, rbx
0x1800114e4  mov     rax, [rax+10h]
0x1800114e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114ed  nop
0x1800114ee  mov     rcx, [rbp+8]; this
0x1800114f2  mov     r9d, edi; char *
0x1800114f5  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\provcsp\\local"...
0x1800114fc  mov     edx, 46h ; 'F'; void *
0x180011501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011506  nop
0x180011507  mov     rcx, [rbp+var_20]
0x18001150b  test    rcx, rcx
0x18001150e  jz      short loc_180011525
0x180011510  mov     [rbp+var_20], 0
0x180011518  mov     rdx, [rcx]
0x18001151b  mov     rax, [rdx+10h]
0x18001151f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011524  nop
0x180011525  mov     eax, edi
0x180011527  jmp     loc_180011618
0x18001152c  mov     rcx, rbx
0x18001152f  mov     rax, [rax+8]
0x180011533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011538  nop
0x180011539  mov     [rbp+var_20], rbx
0x18001153d  mov     rax, [rbx]
0x180011540  mov     rcx, rbx
0x180011543  mov     rax, [rax+10h]
0x180011547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154c  nop
0x18001154d  mov     rcx, [rbp+var_20]
0x180011551  test    rcx, rcx
0x180011554  jnz     short loc_180011594
0x180011556  mov     rcx, [rbp+8]; this
0x18001155a  mov     edi, 8007000Eh
0x18001155f  mov     r9d, edi; char *
0x180011562  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\provcsp\\local"...
0x180011569  mov     edx, 47h ; 'G'; void *
0x18001156e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011573  nop
0x180011574  mov     rcx, [rbp+var_20]
0x180011578  test    rcx, rcx
0x18001157b  jz      short loc_180011592
0x18001157d  mov     [rbp+var_20], 0
0x180011585  mov     rax, [rcx]
0x180011588  mov     rax, [rax+10h]
0x18001158c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011591  nop
0x180011592  jmp     short loc_180011525
0x180011594  mov     r8, [rbp+arg_20]
0x180011598  test    r8, r8
0x18001159b  jz      short loc_1800115F5
0x18001159d  mov     rax, [rcx]
0x1800115a0  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x1800115a7  mov     rax, [rax]
0x1800115aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115af  mov     ebx, eax
0x1800115b1  test    eax, eax
0x1800115b3  jns     short loc_1800115F1
0x1800115b5  mov     rcx, [rbp+8]; this
0x1800115b9  mov     r9d, eax; char *
0x1800115bc  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\provcsp\\local"...
0x1800115c3  mov     edx, 4Ah ; 'J'; void *
0x1800115c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115cd  nop
0x1800115ce  mov     rcx, [rbp+var_20]
0x1800115d2  test    rcx, rcx
0x1800115d5  jz      short loc_1800115EC
0x1800115d7  mov     [rbp+var_20], 0
0x1800115df  mov     rax, [rcx]
0x1800115e2  mov     rax, [rax+10h]
0x1800115e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115eb  nop
0x1800115ec  jmp     loc_180011420
0x1800115f1  mov     rcx, [rbp+var_20]
0x1800115f5  mov     rax, [rbp+arg_28]
0x1800115f9  or      dword ptr [rax], 2
0x1800115fc  test    rcx, rcx
0x1800115ff  jz      short loc_180011616
0x180011601  mov     [rbp+var_20], 0
0x180011609  mov     rax, [rcx]
0x18001160c  mov     rax, [rax+10h]
0x180011610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011615  nop
0x180011616  xor     eax, eax
0x180011618  mov     rbx, [rsp+40h+arg_0]
0x18001161d  mov     rdi, [rsp+40h+arg_10]
0x180011622  add     rsp, 40h
0x180011626  pop     rbp
0x180011627  retn
```
