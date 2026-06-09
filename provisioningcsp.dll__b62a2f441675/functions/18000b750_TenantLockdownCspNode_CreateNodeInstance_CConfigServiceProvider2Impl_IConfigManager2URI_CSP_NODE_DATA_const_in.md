# TenantLockdownCspNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x18000b750`
- end: `0x18000ba5a`
- name: `?CreateNodeInstance@TenantLockdownCspNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `778`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000b750`
- `0x18001279c`
- `0x1800128d0`
- `0x180012be0`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TenantLockdownCspNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  unsigned int v9; // ebx
  struct ICSPNode **v11; // rsi
  unsigned int *v12; // rax
  int v13; // eax
  struct ICSPNode *v14; // rax
  struct ICSPNode *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  int v18; // eax
  int v19; // [rsp+20h] [rbp-38h]
  int v20; // [rsp+20h] [rbp-38h]
  unsigned int v21[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v23; // [rsp+60h] [rbp+8h] BYREF

  v23 = 0;
  *(_QWORD *)v21 = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x80070057LL,
      v19);
    return v9;
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x80070057LL,
      v19);
    return v9;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x80070057LL,
      v19);
    return v9;
  }
  v11 = a5;
  if ( !a5 )
  {
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x80004003LL,
      v19);
    return v9;
  }
  v12 = a6;
  if ( !a6 )
  {
    v9 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x80004003LL,
      v19);
    return v9;
  }
  *a5 = 0;
  *v12 = 0;
  if ( a4 && (*((_BYTE *)a3 + 20) & 4) == 0 )
  {
    v9 = -2046820335;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x86000011LL,
      v19);
    return v9;
  }
  v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v23);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)(unsigned int)v13,
      v19);
    return v9;
  }
  if ( *((_DWORD *)a3 + 2) + 1 != v23 )
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x8000FFFFLL,
      v19);
    return v9;
  }
  v14 = (struct ICSPNode *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v15 = v14;
  *(_QWORD *)v21 = v14;
  if ( v14 )
  {
    *((_QWORD *)v14 + 2) = 0;
    *((_QWORD *)v14 + 3) = 0;
    *((_DWORD *)v14 + 16) = 1;
    *((_OWORD *)v14 + 2) = 0;
    *((_OWORD *)v14 + 3) = 0;
    *(_QWORD *)v14 = &TenantLockdownCspNode::`vftable'{for `ICSPNode'};
    *((_QWORD *)v14 + 1) = &CAccountsNode::`vftable'{for `ICSPNodeTransactioning'};
    _InterlockedIncrement(&dword_18004A0B4);
  }
  else
  {
    v15 = 0;
  }
  *(_QWORD *)v21 = v15;
  if ( !v15 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)0x8007000ELL,
      v19);
    return v9;
  }
  v16 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v15 + 136LL))(
          v15,
          a1,
          a2,
          a3);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
      (const char *)(unsigned int)v16,
      v19);
    (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v15 + 16LL))(v15);
    return v17;
  }
  v21[0] = 0;
  if ( Microsoft::Windows::Autopilot::ForcedEnrollment::DoesSupportUefiVariable() )
  {
    if ( (unsigned int)Microsoft::Windows::Autopilot::ForcedEnrollment::GetOobeForcedNetworkValue(v21) == -2147024693 )
    {
      v18 = Microsoft::Windows::Autopilot::ForcedEnrollment::SetOobeForcedNetworkValue(0);
      v17 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
          (const char *)(unsigned int)v18,
          v19);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x42,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\tenantlockdowncspnode.cpp",
          (const char *)v17,
          v20);
        (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v15 + 16LL))(v15);
        return v17;
      }
    }
  }
  *v11 = v15;
  return 0;
}

```

## disassembly

```asm
0x18000b750  mov     rax, rsp
0x18000b753  mov     [rax+10h], rbx
0x18000b757  mov     [rax+18h], rbp
0x18000b75b  push    rsi
0x18000b75c  push    rdi
0x18000b75d  push    r14
0x18000b75f  sub     rsp, 40h
0x18000b763  mov     rdi, r8
0x18000b766  mov     r14, rdx
0x18000b769  mov     rbp, rcx
0x18000b76c  mov     dword ptr [rax+8], 0
0x18000b773  mov     qword ptr [rax-28h], 0
0x18000b77b  test    rcx, rcx
0x18000b77e  jnz     short loc_18000B7A4
0x18000b780  mov     rcx, [rsp+58h]; this
0x18000b785  mov     ebx, 80070057h
0x18000b78a  mov     r9d, ebx; char *
0x18000b78d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b794  lea     edx, [rbp+2Bh]; void *
0x18000b797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b79c  nop
0x18000b79d  mov     eax, ebx
0x18000b79f  jmp     loc_18000BA46
0x18000b7a4  test    r14, r14
0x18000b7a7  jnz     short loc_18000B7C9
0x18000b7a9  mov     rcx, [rsp+58h]; this
0x18000b7ae  mov     ebx, 80070057h
0x18000b7b3  mov     r9d, ebx; char *
0x18000b7b6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b7bd  lea     edx, [r14+2Ch]; void *
0x18000b7c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7c6  nop
0x18000b7c7  jmp     short loc_18000B79D
0x18000b7c9  test    rdi, rdi
0x18000b7cc  jnz     short loc_18000B7ED
0x18000b7ce  mov     rcx, [rsp+58h]; this
0x18000b7d3  mov     ebx, 80070057h
0x18000b7d8  mov     r9d, ebx; char *
0x18000b7db  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b7e2  lea     edx, [rdi+2Dh]; void *
0x18000b7e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b7ea  nop
0x18000b7eb  jmp     short loc_18000B79D
0x18000b7ed  mov     rsi, [rsp+58h+arg_20]
0x18000b7f5  test    rsi, rsi
0x18000b7f8  jnz     short loc_18000B819
0x18000b7fa  mov     rcx, [rsp+58h]; this
0x18000b7ff  mov     ebx, 80004003h
0x18000b804  mov     r9d, ebx; char *
0x18000b807  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b80e  lea     edx, [rsi+2Eh]; void *
0x18000b811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b816  nop
0x18000b817  jmp     short loc_18000B79D
0x18000b819  mov     rax, [rsp+58h+arg_28]
0x18000b821  test    rax, rax
0x18000b824  jnz     short loc_18000B848
0x18000b826  mov     rcx, [rsp+58h]; this
0x18000b82b  mov     ebx, 80004003h
0x18000b830  mov     r9d, ebx; char *
0x18000b833  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b83a  lea     edx, [rax+2Fh]; void *
0x18000b83d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b842  nop
0x18000b843  jmp     loc_18000B79D
0x18000b848  mov     qword ptr [rsi], 0
0x18000b84f  mov     dword ptr [rax], 0
0x18000b855  test    r9d, r9d
0x18000b858  jz      short loc_18000B885
0x18000b85a  test    byte ptr [r8+14h], 4
0x18000b85f  jnz     short loc_18000B885
0x18000b861  mov     rcx, [rsp+58h]; this
0x18000b866  mov     ebx, 86000011h
0x18000b86b  mov     r9d, ebx; char *
0x18000b86e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b875  mov     edx, 35h ; '5'; void *
0x18000b87a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b87f  nop
0x18000b880  jmp     loc_18000B79D
0x18000b885  mov     rax, [rdx]
0x18000b888  lea     rdx, [rsp+58h+arg_0]
0x18000b88d  mov     rcx, r14
0x18000b890  mov     rax, [rax+88h]
0x18000b897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b89c  mov     ebx, eax
0x18000b89e  test    eax, eax
0x18000b8a0  jns     short loc_18000B8C1
0x18000b8a2  mov     rcx, [rsp+58h]; this
0x18000b8a7  mov     r9d, eax; char *
0x18000b8aa  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b8b1  mov     edx, 38h ; '8'; void *
0x18000b8b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8bb  nop
0x18000b8bc  jmp     loc_18000B79D
0x18000b8c1  mov     eax, [rdi+8]
0x18000b8c4  inc     eax
0x18000b8c6  cmp     eax, [rsp+58h+arg_0]
0x18000b8ca  jz      short loc_18000B8F0
0x18000b8cc  mov     rcx, [rsp+58h]; this
0x18000b8d1  mov     ebx, 8000FFFFh
0x18000b8d6  mov     r9d, ebx; char *
0x18000b8d9  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b8e0  mov     edx, 3Bh ; ';'; void *
0x18000b8e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8ea  nop
0x18000b8eb  jmp     loc_18000B79D
0x18000b8f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b8f7  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000b8fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b901  mov     rbx, rax
0x18000b904  mov     qword ptr [rsp+58h+var_28], rax
0x18000b909  test    rax, rax
0x18000b90c  jz      short loc_18000B94E
0x18000b90e  mov     qword ptr [rax+10h], 0
0x18000b916  mov     qword ptr [rax+18h], 0
0x18000b91e  mov     dword ptr [rax+40h], 1
0x18000b925  xorps   xmm0, xmm0
0x18000b928  movups  xmmword ptr [rax+20h], xmm0
0x18000b92c  movups  xmmword ptr [rax+30h], xmm0
0x18000b930  lea     rax, ??_7TenantLockdownCspNode@@6BICSPNode@@@; const TenantLockdownCspNode::`vftable'{for `ICSPNode'}
0x18000b937  mov     [rbx], rax
0x18000b93a  lea     rax, ??_7CAccountsNode@@6BICSPNodeTransactioning@@@; const CAccountsNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000b941  mov     [rbx+8], rax
0x18000b945  lock inc cs:dword_18004A0B4
0x18000b94c  jmp     short loc_18000B950
0x18000b94e  xor     ebx, ebx
0x18000b950  mov     qword ptr [rsp+58h+var_28], rbx
0x18000b955  test    rbx, rbx
0x18000b958  jnz     short loc_18000B97E
0x18000b95a  mov     rcx, [rsp+58h]; this
0x18000b95f  mov     ebx, 8007000Eh
0x18000b964  mov     r9d, ebx; char *
0x18000b967  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b96e  mov     edx, 3Eh ; '>'; void *
0x18000b973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b978  nop
0x18000b979  jmp     loc_18000B79D
0x18000b97e  mov     rax, [rbx]
0x18000b981  mov     r9, rdi
0x18000b984  mov     r8, r14
0x18000b987  mov     rdx, rbp
0x18000b98a  mov     rcx, rbx
0x18000b98d  mov     rax, [rax+88h]
0x18000b994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b999  mov     edi, eax
0x18000b99b  test    eax, eax
0x18000b99d  jns     short loc_18000B9CD
0x18000b99f  mov     rcx, [rsp+58h]; this
0x18000b9a4  mov     r9d, eax; char *
0x18000b9a7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000b9ae  mov     edx, 40h ; '@'; void *
0x18000b9b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9b8  nop
0x18000b9b9  mov     rdx, [rbx]
0x18000b9bc  mov     rcx, rbx
0x18000b9bf  mov     rax, [rdx+10h]
0x18000b9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9c8  nop
0x18000b9c9  mov     eax, edi
0x18000b9cb  jmp     short loc_18000BA46
0x18000b9cd  mov     [rsp+58h+var_28], 0
0x18000b9d5  call    ?DoesSupportUefiVariable@ForcedEnrollment@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::ForcedEnrollment::DoesSupportUefiVariable(void)
0x18000b9da  test    al, al
0x18000b9dc  jz      short loc_18000BA41
0x18000b9de  lea     rcx, [rsp+58h+var_28]; unsigned int *
0x18000b9e3  call    ?GetOobeForcedNetworkValue@ForcedEnrollment@Autopilot@Windows@Microsoft@@SAJPEAK@Z; Microsoft::Windows::Autopilot::ForcedEnrollment::GetOobeForcedNetworkValue(ulong *)
0x18000b9e8  cmp     eax, 800700CBh
0x18000b9ed  jnz     short loc_18000BA41
0x18000b9ef  xor     ecx, ecx; unsigned int
0x18000b9f1  call    ?SetOobeForcedNetworkValue@ForcedEnrollment@Autopilot@Windows@Microsoft@@SAJK@Z; Microsoft::Windows::Autopilot::ForcedEnrollment::SetOobeForcedNetworkValue(ulong)
0x18000b9f6  mov     edi, eax
0x18000b9f8  test    eax, eax
0x18000b9fa  jns     short loc_18000BA41
0x18000b9fc  mov     rcx, [rsp+58h]; this
0x18000ba01  mov     r9d, eax; char *
0x18000ba04  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000ba0b  mov     edx, 0D3h; void *
0x18000ba10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba15  mov     rcx, [rsp+58h]; this
0x18000ba1a  mov     r9d, edi; char *
0x18000ba1d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\provcsp\\tenan"...
0x18000ba24  mov     edx, 42h ; 'B'; void *
0x18000ba29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba2e  nop
0x18000ba2f  mov     rax, [rbx]
0x18000ba32  mov     rcx, rbx
0x18000ba35  mov     rax, [rax+10h]
0x18000ba39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3e  nop
0x18000ba3f  jmp     short loc_18000B9C9
0x18000ba41  mov     [rsi], rbx
0x18000ba44  xor     eax, eax
0x18000ba46  mov     rbx, [rsp+58h+arg_8]
0x18000ba4b  mov     rbp, [rsp+58h+arg_10]
0x18000ba50  add     rsp, 40h
0x18000ba54  pop     r14
0x18000ba56  pop     rdi
0x18000ba57  pop     rsi
0x18000ba58  retn
```
