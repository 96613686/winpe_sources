# CProvisioningNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180009890`
- end: `0x180009b65`
- name: `?CreateNodeInstance@CProvisioningNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `725`
- prototype: `static int(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ebc0`

## callees

- `0x1800030e8`
- `0x180006974`
- `0x18000937c`
- `0x180009460`
- `0x180009890`
- `0x180009c80`
- `0x180009d78`
- `0x18000fd74`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProvisioningNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v10; // rsi
  unsigned int *v11; // r15
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int RegStoreForCertificateByUri; // eax
  struct ICSPNode *v16; // rax
  struct ICSPNode *v17; // rbx
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-28h]
  _QWORD v25[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  int v27; // [rsp+90h] [rbp+48h] BYREF

  v27 = 0;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147942487LL;
  if ( !a3 )
    return 2147942487LL;
  v10 = a5;
  if ( !a5 )
    return 2147942487LL;
  v11 = a6;
  if ( !a6 )
    return 2147942487LL;
  v12 = ProvUtil::CheckAllowedConfigSource(a1, a2);
  if ( (v12 & 0x80000000) != 0 )
  {
    v13 = 99;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
      (const char *)v12,
      v24);
    return v12;
  }
  *v10 = 0;
  *v11 = 0;
  if ( a4 )
  {
    if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
      return 2248146961LL;
    goto LABEL_21;
  }
  if ( !*((_DWORD *)a3 + 6) )
  {
    if ( *((_DWORD *)a3 + 3) == 2 )
    {
      RegStoreForCertificateByUri = CProvisioningNode::QueryRegStoreForCertificateByUri(a2);
    }
    else
    {
      if ( *((_DWORD *)a3 + 3) != 8 )
      {
        v12 = -2046820350;
LABEL_20:
        v13 = 126;
        goto LABEL_8;
      }
      RegStoreForCertificateByUri = CProvisioningNode::QueryRebootRequesterByUri(a2);
    }
    v12 = RegStoreForCertificateByUri;
    if ( RegStoreForCertificateByUri < 0 )
      goto LABEL_20;
  }
LABEL_21:
  if ( *((_DWORD *)a3 + 3) == 4 )
  {
    v25[0] = 0;
    v22 = Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(v25);
    v12 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
        (const char *)(unsigned int)v22,
        v24);
      v23 = v25[0];
      if ( v25[0] )
      {
        v25[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      return v12;
    }
    *v10 = (struct ICSPNode *)v25[0];
  }
  else if ( *((_DWORD *)a3 + 3) == 9 )
  {
    v25[0] = 0;
    v20 = Microsoft::WRL::Details::MakeAndInitialize<EnrollmentsNode,EnrollmentsNode,IConfigManager2URI * &>(v25);
    v12 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
        (const char *)(unsigned int)v20,
        v24);
      v21 = v25[0];
      if ( v25[0] )
      {
        v25[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      return v12;
    }
    *v10 = (struct ICSPNode *)v25[0];
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v27);
    if ( (v12 & 0x80000000) != 0 )
    {
      v13 = 150;
      goto LABEL_8;
    }
    if ( *((_DWORD *)a3 + 2) + 1 != v27 )
    {
      v12 = -2147418113;
      v13 = 153;
      goto LABEL_8;
    }
    v16 = (struct ICSPNode *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
    v17 = v16;
    v25[0] = v16;
    if ( v16 )
    {
      *((_QWORD *)v16 + 2) = 0;
      *((_QWORD *)v16 + 3) = 0;
      *((_DWORD *)v16 + 16) = 1;
      *((_OWORD *)v16 + 2) = 0;
      *((_OWORD *)v16 + 3) = 0;
      *(_QWORD *)v16 = &CProvisioningNode::`vftable'{for `ICSPNode'};
      *((_QWORD *)v16 + 1) = &CAccountsNode::`vftable'{for `ICSPNodeTransactioning'};
      _InterlockedIncrement(&dword_18004A0B4);
    }
    else
    {
      v17 = 0;
    }
    v25[0] = v17;
    if ( !v17 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
        (const char *)0x8007000ELL,
        v24);
      return v12;
    }
    v18 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v17 + 136LL))(
            v17,
            a1,
            a2,
            a3);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
        (const char *)(unsigned int)v18,
        v24);
      (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v17 + 16LL))(v17);
      return v19;
    }
    *v10 = v17;
  }
  return 0;
}

```

## disassembly

```asm
0x180009890  push    rbp
0x180009892  push    rbx
0x180009893  push    rsi
0x180009894  push    rdi
0x180009895  push    r12
0x180009897  push    r13
0x180009899  push    r14
0x18000989b  push    r15
0x18000989d  mov     rbp, rsp
0x1800098a0  sub     rsp, 48h
0x1800098a4  mov     r12d, r9d
0x1800098a7  mov     rdi, r8
0x1800098aa  mov     r14, rdx
0x1800098ad  mov     r13, rcx
0x1800098b0  mov     [rbp+arg_0], 0
0x1800098b7  test    rcx, rcx
0x1800098ba  jz      loc_180009B4E
0x1800098c0  test    rdx, rdx
0x1800098c3  jz      loc_180009B4E
0x1800098c9  test    r8, r8
0x1800098cc  jz      loc_180009B4E
0x1800098d2  mov     rsi, [rbp+arg_20]
0x1800098d6  test    rsi, rsi
0x1800098d9  jz      loc_180009B4E
0x1800098df  mov     r15, [rbp+arg_28]
0x1800098e3  test    r15, r15
0x1800098e6  jz      loc_180009B4E
0x1800098ec  call    ?CheckAllowedConfigSource@ProvUtil@@YAJPEAVCConfigServiceProvider2Impl@@@Z; ProvUtil::CheckAllowedConfigSource(CConfigServiceProvider2Impl *)
0x1800098f1  mov     ebx, eax
0x1800098f3  test    eax, eax
0x1800098f5  jns     short loc_180009916
0x1800098f7  mov     edx, 63h ; 'c'; void *
0x1800098fc  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009903  mov     r9d, ebx; char *
0x180009906  mov     rcx, [rbp+40h]; this
0x18000990a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000990f  mov     eax, ebx
0x180009911  jmp     loc_180009B53
0x180009916  mov     qword ptr [rsi], 0
0x18000991d  mov     dword ptr [r15], 0
0x180009924  xor     r15d, r15d
0x180009927  test    r12d, r12d
0x18000992a  jz      short loc_18000993C
0x18000992c  test    byte ptr [rdi+14h], 4
0x180009930  jnz     short loc_180009974
0x180009932  mov     eax, 86000011h
0x180009937  jmp     loc_180009B53
0x18000993c  cmp     [rdi+18h], r15d
0x180009940  jnz     short loc_180009974
0x180009942  cmp     dword ptr [rdi+0Ch], 2
0x180009946  jz      short loc_18000995F
0x180009948  cmp     dword ptr [rdi+0Ch], 8
0x18000994c  jz      short loc_180009955
0x18000994e  mov     ebx, 86000002h
0x180009953  jmp     short loc_18000996D
0x180009955  mov     rcx, r14; struct IConfigManager2URI *
0x180009958  call    ?QueryRebootRequesterByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@@Z; CProvisioningNode::QueryRebootRequesterByUri(IConfigManager2URI *)
0x18000995d  jmp     short loc_180009967
0x18000995f  mov     rcx, r14; struct IConfigManager2URI *
0x180009962  call    ?QueryRegStoreForCertificateByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@@Z; CProvisioningNode::QueryRegStoreForCertificateByUri(IConfigManager2URI *)
0x180009967  mov     ebx, eax
0x180009969  test    eax, eax
0x18000996b  jns     short loc_180009974
0x18000996d  mov     edx, 7Eh ; '~'
0x180009972  jmp     short loc_1800098FC
0x180009974  cmp     dword ptr [rdi+0Ch], 4
0x180009978  jz      loc_180009AF8
0x18000997e  cmp     dword ptr [rdi+0Ch], 9
0x180009982  jz      loc_180009AA4
0x180009988  mov     rax, [r14]
0x18000998b  lea     rdx, [rbp+arg_0]
0x18000998f  mov     rcx, r14
0x180009992  mov     rax, [rax+88h]
0x180009999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999e  mov     ebx, eax
0x1800099a0  test    eax, eax
0x1800099a2  jns     short loc_1800099AE
0x1800099a4  mov     edx, 96h
0x1800099a9  jmp     loc_1800098FC
0x1800099ae  mov     eax, [rdi+8]
0x1800099b1  inc     eax
0x1800099b3  cmp     eax, [rbp+arg_0]
0x1800099b6  jz      short loc_1800099C7
0x1800099b8  mov     ebx, 8000FFFFh
0x1800099bd  mov     edx, 99h
0x1800099c2  jmp     loc_1800098FC
0x1800099c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800099ce  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800099d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800099d8  mov     rbx, rax
0x1800099db  mov     [rbp+var_18], rax
0x1800099df  test    rax, rax
0x1800099e2  jz      short loc_180009A1C
0x1800099e4  mov     [rax+10h], r15
0x1800099e8  mov     [rax+18h], r15
0x1800099ec  mov     dword ptr [rax+40h], 1
0x1800099f3  xorps   xmm0, xmm0
0x1800099f6  movups  xmmword ptr [rax+20h], xmm0
0x1800099fa  movups  xmmword ptr [rax+30h], xmm0
0x1800099fe  lea     rax, ??_7CProvisioningNode@@6BICSPNode@@@; const CProvisioningNode::`vftable'{for `ICSPNode'}
0x180009a05  mov     [rbx], rax
0x180009a08  lea     rax, ??_7CAccountsNode@@6BICSPNodeTransactioning@@@; const CAccountsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180009a0f  mov     [rbx+8], rax
0x180009a13  lock inc cs:dword_18004A0B4
0x180009a1a  jmp     short loc_180009A1F
0x180009a1c  mov     rbx, r15
0x180009a1f  mov     [rbp+var_18], rbx
0x180009a23  test    rbx, rbx
0x180009a26  jnz     short loc_180009A4B
0x180009a28  mov     rcx, [rbp+40h]; this
0x180009a2c  mov     ebx, 8007000Eh
0x180009a31  mov     r9d, ebx; char *
0x180009a34  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009a3b  mov     edx, 9Dh; void *
0x180009a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a45  nop
0x180009a46  jmp     loc_18000990F
0x180009a4b  mov     rax, [rbx]
0x180009a4e  mov     r9, rdi
0x180009a51  mov     r8, r14
0x180009a54  mov     rdx, r13
0x180009a57  mov     rcx, rbx
0x180009a5a  mov     rax, [rax+88h]
0x180009a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a66  mov     edi, eax
0x180009a68  test    eax, eax
0x180009a6a  jns     short loc_180009A9C
0x180009a6c  mov     rcx, [rbp+40h]; this
0x180009a70  mov     r9d, eax; char *
0x180009a73  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009a7a  mov     edx, 9Eh; void *
0x180009a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a84  nop
0x180009a85  mov     rdx, [rbx]
0x180009a88  mov     rcx, rbx
0x180009a8b  mov     rax, [rdx+10h]
0x180009a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a94  nop
0x180009a95  mov     eax, edi
0x180009a97  jmp     loc_180009B53
0x180009a9c  mov     [rsi], rbx
0x180009a9f  jmp     loc_180009B4A
0x180009aa4  mov     [rbp+var_18], r15
0x180009aa8  lea     rcx, [rbp+var_18]
0x180009aac  call    ??$MakeAndInitialize@VEnrollmentsNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VEnrollmentsNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<EnrollmentsNode,EnrollmentsNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<EnrollmentsNode>>,IConfigManager2URI * &)
0x180009ab1  mov     ebx, eax
0x180009ab3  test    eax, eax
0x180009ab5  jns     short loc_180009AEF
0x180009ab7  mov     rcx, [rbp+40h]; this
0x180009abb  mov     r9d, eax; char *
0x180009abe  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009ac5  mov     edx, 8Fh; void *
0x180009aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009acf  nop
0x180009ad0  mov     rcx, [rbp+var_18]
0x180009ad4  test    rcx, rcx
0x180009ad7  jz      short loc_180009AEA
0x180009ad9  mov     [rbp+var_18], r15
0x180009add  mov     rax, [rcx]
0x180009ae0  mov     rax, [rax+10h]
0x180009ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae9  nop
0x180009aea  jmp     loc_18000990F
0x180009aef  mov     rax, [rbp+var_18]
0x180009af3  mov     [rsi], rax
0x180009af6  jmp     short loc_180009B4A
0x180009af8  mov     [rbp+var_18], r15
0x180009afc  lea     rcx, [rbp+var_18]
0x180009b00  call    ??$MakeAndInitialize@VAddPackageNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAddPackageNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AddPackageNode>>,IConfigManager2URI * &)
0x180009b05  mov     ebx, eax
0x180009b07  test    eax, eax
0x180009b09  jns     short loc_180009B43
0x180009b0b  mov     rcx, [rbp+40h]; this
0x180009b0f  mov     r9d, eax; char *
0x180009b12  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009b19  mov     edx, 87h; void *
0x180009b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b23  nop
0x180009b24  mov     rcx, [rbp+var_18]
0x180009b28  test    rcx, rcx
0x180009b2b  jz      short loc_180009B3E
0x180009b2d  mov     [rbp+var_18], r15
0x180009b31  mov     rax, [rcx]
0x180009b34  mov     rax, [rax+10h]
0x180009b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3d  nop
0x180009b3e  jmp     loc_18000990F
0x180009b43  mov     rax, [rbp+var_18]
0x180009b47  mov     [rsi], rax
0x180009b4a  xor     eax, eax
0x180009b4c  jmp     short loc_180009B53
0x180009b4e  mov     eax, 80070057h
0x180009b53  add     rsp, 48h
0x180009b57  pop     r15
0x180009b59  pop     r14
0x180009b5b  pop     r13
0x180009b5d  pop     r12
0x180009b5f  pop     rdi
0x180009b60  pop     rsi
0x180009b61  pop     rbx
0x180009b62  pop     rbp
0x180009b63  retn
```
