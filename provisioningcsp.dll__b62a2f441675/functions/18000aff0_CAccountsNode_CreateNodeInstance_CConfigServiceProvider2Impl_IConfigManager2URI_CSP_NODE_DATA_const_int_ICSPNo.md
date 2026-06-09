# CAccountsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000aff0`
- end: `0x18000b1d7`
- name: `?CreateNodeInstance@CAccountsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000aff0`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAccountsNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v9; // rsi
  unsigned int *v10; // rax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  struct ICSPNode *v14; // rax
  struct ICSPNode *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v9 = a5;
  if ( !a5 )
    return 2147942487LL;
  v10 = a6;
  if ( !a6 )
    return 2147942487LL;
  *a5 = 0;
  *v10 = 0;
  if ( a4 )
  {
    if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
      return 2248146961LL;
  }
  else if ( !*((_DWORD *)a3 + 6) )
  {
    v12 = -2046820350;
    v13 = 46;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
      (const char *)v12,
      v18);
    return v12;
  }
  v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v20);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = 50;
    goto LABEL_11;
  }
  if ( *((_DWORD *)a3 + 2) + 1 != v20 )
  {
    v12 = -2147418113;
    v13 = 53;
    goto LABEL_11;
  }
  v14 = (struct ICSPNode *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    *((_QWORD *)v14 + 2) = 0;
    *((_QWORD *)v14 + 3) = 0;
    *((_DWORD *)v14 + 16) = 1;
    *((_OWORD *)v14 + 2) = 0;
    *((_OWORD *)v14 + 3) = 0;
    *(_QWORD *)v14 = &CAccountsNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v14 + 1) = &CAccountsNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_18004A0B4);
  }
  else
  {
    v15 = 0;
  }
  if ( !v15 )
  {
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
      (const char *)0x8007000ELL,
      v18);
    return v12;
  }
  v16 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v15 + 136LL))(
          v15,
          a1,
          a2,
          a3);
  v17 = v16;
  if ( v16 >= 0 )
  {
    *v9 = v15;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
      (const char *)(unsigned int)v16,
      v18);
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v15 + 16LL))(v15);
    return v17;
  }
}

```

## disassembly

```asm
0x18000aff0  mov     [rsp+arg_8], rbx
0x18000aff5  mov     [rsp+arg_10], rbp
0x18000affa  push    rsi
0x18000affb  push    rdi
0x18000affc  push    r14
0x18000affe  sub     rsp, 40h
0x18000b002  mov     rdi, r8
0x18000b005  mov     r14, rdx
0x18000b008  mov     rbp, rcx
0x18000b00b  mov     [rsp+58h+arg_0], 0
0x18000b013  test    rcx, rcx
0x18000b016  jz      loc_18000B1BE
0x18000b01c  test    rdx, rdx
0x18000b01f  jz      loc_18000B1BE
0x18000b025  test    r8, r8
0x18000b028  jz      loc_18000B1BE
0x18000b02e  mov     rsi, [rsp+58h+arg_20]
0x18000b036  test    rsi, rsi
0x18000b039  jz      loc_18000B1BE
0x18000b03f  mov     rax, [rsp+58h+arg_28]
0x18000b047  test    rax, rax
0x18000b04a  jz      loc_18000B1BE
0x18000b050  mov     qword ptr [rsi], 0
0x18000b057  mov     dword ptr [rax], 0
0x18000b05d  test    r9d, r9d
0x18000b060  jz      short loc_18000B073
0x18000b062  test    byte ptr [r8+14h], 4
0x18000b067  jnz     short loc_18000B09F
0x18000b069  mov     eax, 86000011h
0x18000b06e  jmp     loc_18000B1C3
0x18000b073  cmp     dword ptr [r8+18h], 0
0x18000b078  jnz     short loc_18000B09F
0x18000b07a  mov     ebx, 86000002h
0x18000b07f  mov     edx, 2Eh ; '.'; void *
0x18000b084  mov     rcx, [rsp+58h]; this
0x18000b089  mov     r9d, ebx; char *
0x18000b08c  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000b093  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b098  mov     eax, ebx
0x18000b09a  jmp     loc_18000B1C3
0x18000b09f  mov     rax, [rdx]
0x18000b0a2  lea     rdx, [rsp+58h+arg_0]
0x18000b0a7  mov     rcx, r14
0x18000b0aa  mov     rax, [rax+88h]
0x18000b0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0b6  mov     ebx, eax
0x18000b0b8  test    eax, eax
0x18000b0ba  jns     short loc_18000B0C3
0x18000b0bc  mov     edx, 32h ; '2'
0x18000b0c1  jmp     short loc_18000B084
0x18000b0c3  mov     eax, [rdi+8]
0x18000b0c6  inc     eax
0x18000b0c8  cmp     eax, [rsp+58h+arg_0]
0x18000b0cc  jz      short loc_18000B0DA
0x18000b0ce  mov     ebx, 8000FFFFh
0x18000b0d3  mov     edx, 35h ; '5'
0x18000b0d8  jmp     short loc_18000B084
0x18000b0da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b0e1  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000b0e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b0eb  mov     rbx, rax
0x18000b0ee  mov     [rsp+58h+var_28], rax
0x18000b0f3  test    rax, rax
0x18000b0f6  jz      short loc_18000B138
0x18000b0f8  mov     qword ptr [rax+10h], 0
0x18000b100  mov     qword ptr [rax+18h], 0
0x18000b108  mov     dword ptr [rax+40h], 1
0x18000b10f  xorps   xmm0, xmm0
0x18000b112  movups  xmmword ptr [rax+20h], xmm0
0x18000b116  movups  xmmword ptr [rax+30h], xmm0
0x18000b11a  lea     rax, ??_7CAccountsNode@@6BICSPNode@@@; const CAccountsNode::`vftable'{for `ICSPNode'}
0x18000b121  mov     [rbx], rax
0x18000b124  lea     rax, ??_7CAccountsNode@@6BICSPNodeTransactioning@@@; const CAccountsNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000b12b  mov     [rbx+8], rax
0x18000b12f  lock inc cs:dword_18004A0B4
0x18000b136  jmp     short loc_18000B13A
0x18000b138  xor     ebx, ebx
0x18000b13a  mov     [rsp+58h+var_28], rbx
0x18000b13f  test    rbx, rbx
0x18000b142  jnz     short loc_18000B168
0x18000b144  mov     rcx, [rsp+58h]; this
0x18000b149  mov     ebx, 8007000Eh
0x18000b14e  mov     r9d, ebx; char *
0x18000b151  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000b158  mov     edx, 39h ; '9'; void *
0x18000b15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b162  nop
0x18000b163  jmp     loc_18000B098
0x18000b168  mov     rax, [rbx]
0x18000b16b  mov     r9, rdi
0x18000b16e  mov     r8, r14
0x18000b171  mov     rdx, rbp
0x18000b174  mov     rcx, rbx
0x18000b177  mov     rax, [rax+88h]
0x18000b17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b183  mov     edi, eax
0x18000b185  test    eax, eax
0x18000b187  jns     short loc_18000B1B7
0x18000b189  mov     rcx, [rsp+58h]; this
0x18000b18e  mov     r9d, eax; char *
0x18000b191  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000b198  mov     edx, 3Ah ; ':'; void *
0x18000b19d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1a2  nop
0x18000b1a3  mov     rdx, [rbx]
0x18000b1a6  mov     rcx, rbx
0x18000b1a9  mov     rax, [rdx+10h]
0x18000b1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b2  nop
0x18000b1b3  mov     eax, edi
0x18000b1b5  jmp     short loc_18000B1C3
0x18000b1b7  mov     [rsi], rbx
0x18000b1ba  xor     eax, eax
0x18000b1bc  jmp     short loc_18000B1C3
0x18000b1be  mov     eax, 80070057h
0x18000b1c3  mov     rbx, [rsp+58h+arg_8]
0x18000b1c8  mov     rbp, [rsp+58h+arg_10]
0x18000b1cd  add     rsp, 40h
0x18000b1d1  pop     r14
0x18000b1d3  pop     rdi
0x18000b1d4  pop     rsi
0x18000b1d5  retn
```
