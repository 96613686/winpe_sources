# CProvisioningNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000e6e0`
- end: `0x18000ebb9`
- name: `?Add@CProvisioningNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `1241`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006974`
- `0x18000937c`
- `0x18000d9a8`
- `0x18000e004`
- `0x18000e458`
- `0x18000e6e0`
- `0x18000ebc0`
- `0x18000ed40`
- `0x18000ee24`
- `0x180010590`
- `0x180012cd0`
- `0x180038010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000eb15`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000eb15`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000eaea`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000eaea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e87c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e8c0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e9ff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea4a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea9f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e87c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e8c0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000e9ff`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea4a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000ea9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CProvisioningNode::Add(
        CProvisioningNode *a1,
        struct IConfigManager2URI *a2,
        __int64 a3,
        SAFEARRAY **a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  int v7; // r12d
  struct ICSPNode **v10; // rsi
  unsigned int *v11; // r13
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int ChildNodeFromUri; // esi
  __int64 v16; // rdx
  int v17; // eax
  HRESULT UBound; // r14d
  struct ICSPNode *v19; // rcx
  int v20; // eax
  int v21; // ecx
  int v22; // r8d
  const char *v23; // r9
  struct ICSPNode *v25; // rcx
  int v26; // eax
  struct ICSPNode *v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  struct ICSPNode *v30; // rcx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-98h]
  LONG plUbound; // [rsp+30h] [rbp-88h] BYREF
  void *ppvData; // [rsp+38h] [rbp-80h] BYREF
  struct ICSPNode *v35; // [rsp+40h] [rbp-78h] BYREF
  char v36; // [rsp+48h] [rbp-70h] BYREF
  __int128 v37; // [rsp+60h] [rbp-58h] BYREF
  SAFEARRAY *v38; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  struct IConfigManager2URI *v41; // [rsp+C8h] [rbp+10h] BYREF
  SAFEARRAY **v42; // [rsp+D8h] [rbp+20h]

  v42 = a4;
  v41 = a2;
  v7 = a3;
  if ( !a2 )
    return 2147500035LL;
  v10 = a5;
  if ( !a5 )
    return 2147500035LL;
  v11 = a6;
  if ( !a6 )
    return 2147500035LL;
  *a5 = 0;
  *v11 = 0;
  plUbound = 0;
  ppvData = 0;
  *(_QWORD *)&v37 = &ppvData;
  *((_QWORD *)&v37 + 1) = a4;
  LOBYTE(v38) = 1;
  v12 = *((_DWORD *)a1 + 11) - 1;
  if ( !v12 )
  {
    LODWORD(v41) = 0;
    UBound = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, struct IConfigManager2URI **))(*(_QWORD *)a2 + 136LL))(
               a2,
               &v41);
    if ( UBound >= 0 )
    {
      if ( (_DWORD)v41 != 1 )
      {
        ChildNodeFromUri = -2147024809;
        v16 = 105;
        goto LABEL_44;
      }
      if ( v7 != 6 )
      {
        v28 = 106;
        goto LABEL_51;
      }
      if ( *(_WORD *)a4 != 8209 )
      {
        v28 = 107;
        goto LABEL_51;
      }
      v35 = 0;
      UBound = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, struct ICSPNode **))(*(_QWORD *)a2 + 88LL))(
                 a2,
                 0,
                 &v35);
      if ( UBound >= 0 )
      {
        UBound = SafeArrayAccessData(a4[1], &ppvData);
        if ( UBound >= 0 )
        {
          UBound = SafeArrayGetUBound(a4[1], 1u, &plUbound);
          if ( UBound >= 0 )
          {
            UBound = ValidateCertificate((BYTE *)ppvData, ++plUbound);
            if ( UBound >= 0 )
            {
              UBound = CProvisioningNode::StoreCertificateInRegStore((BYTE *)ppvData, plUbound);
              if ( UBound >= 0 )
              {
                ChildNodeFromUri = CProvisioningNode::CreateChildNodeFromUri(a1, a2, v10, v11);
                if ( ChildNodeFromUri < 0 )
                {
                  v16 = 122;
                  goto LABEL_44;
                }
                goto LABEL_16;
              }
              v31 = 119;
            }
            else
            {
              v31 = 118;
            }
          }
          else
          {
            v31 = 114;
          }
        }
        else
        {
          v31 = 113;
        }
      }
      else
      {
        v31 = 112;
      }
    }
    else
    {
      v31 = 104;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
      (const char *)(unsigned int)UBound,
      v32);
LABEL_39:
    if ( ppvData )
      SafeArrayUnaccessData(a4[1]);
    return (unsigned int)UBound;
  }
  v13 = v12 - 2;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 != 3 )
      {
        v37 = *(_OWORD *)a4;
        v38 = a4[2];
        v32 = (int)v10;
        ChildNodeFromUri = CCSPNodeImpl::Add(a1, a2, a3, &v37);
        if ( ChildNodeFromUri < 0 )
        {
          v16 = 162;
LABEL_44:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
            (const char *)(unsigned int)ChildNodeFromUri,
            v32);
          if ( ppvData )
            SafeArrayUnaccessData(a4[1]);
          return (unsigned int)ChildNodeFromUri;
        }
        goto LABEL_16;
      }
      v35 = 0;
      v17 = Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(&v35, &v41);
      UBound = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x96,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
          (const char *)(unsigned int)v17,
          v32);
        v19 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v19 + 16LL))(v19);
        }
        goto LABEL_39;
      }
      v20 = ChangeCount(1, (char *)v35 + 56);
      if ( v20 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
          (const char *)(unsigned int)v20,
          v32);
      try
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring const &,std::_Nil>(
          v21,
          (unsigned int)&v36,
          v22,
          (_DWORD)v35 + 24,
          byte_18004A3D0);
        *v10 = v35;
      }
      catch ( ... )
      {
        LODWORD(v41) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x9C,
                         (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
                         v23);
        v25 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        if ( ppvData )
          SafeArrayUnaccessData(v42[1]);
        return (unsigned int)v41;
      }
    }
    else
    {
      v35 = 0;
      v26 = Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(&v35);
      UBound = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
          (const char *)(unsigned int)v26,
          v32);
        v27 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v27 + 16LL))(v27);
        }
        goto LABEL_39;
      }
      *v10 = v35;
    }
LABEL_16:
    if ( ppvData )
      SafeArrayUnaccessData(a4[1]);
    return 0;
  }
  if ( (_DWORD)a3 == 8 )
  {
    v35 = 0;
    v29 = Microsoft::WRL::Details::MakeAndInitialize<PackageNode,PackageNode,IConfigManager2URI * &>(&v35, &v41);
    UBound = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
        (const char *)(unsigned int)v29,
        v32);
      v30 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v30 + 16LL))(v30);
      }
      goto LABEL_39;
    }
    *v10 = v35;
    goto LABEL_16;
  }
  v28 = 129;
LABEL_51:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v28,
    (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\add.cpp",
    (const char *)0x86000011LL,
    v32);
  if ( ppvData )
    SafeArrayUnaccessData(a4[1]);
  return 2248146961LL;
}

```

## disassembly

```asm
0x18000e6e0  mov     r11, rsp
0x18000e6e3  mov     [r11+20h], r9
0x18000e6e7  mov     [r11+10h], rdx
0x18000e6eb  mov     [r11+8], rcx
0x18000e6ef  push    rbx
0x18000e6f0  push    rsi
0x18000e6f1  push    rdi
0x18000e6f2  push    r12
0x18000e6f4  push    r13
0x18000e6f6  push    r14
0x18000e6f8  push    r15
0x18000e6fa  sub     rsp, 80h
0x18000e701  mov     rdi, r9
0x18000e704  mov     r12d, r8d
0x18000e707  mov     r15, rdx
0x18000e70a  mov     r10, rcx
0x18000e70d  xor     ebx, ebx
0x18000e70f  test    rdx, rdx
0x18000e712  jz      loc_18000EBA0
0x18000e718  mov     rsi, [rsp+0B8h+arg_20]
0x18000e720  test    rsi, rsi
0x18000e723  jz      loc_18000EBA0
0x18000e729  mov     r13, [rsp+0B8h+arg_28]
0x18000e731  test    r13, r13
0x18000e734  jz      loc_18000EBA0
0x18000e73a  mov     [rsi], rbx
0x18000e73d  mov     [r13+0], ebx
0x18000e741  mov     [rsp+0B8h+plUbound], ebx
0x18000e745  mov     [r11-80h], rbx
0x18000e749  lea     rax, [r11-80h]
0x18000e74d  mov     [r11-58h], rax
0x18000e751  mov     [r11-50h], r9
0x18000e755  mov     byte ptr [rsp+0B8h+var_48], 1
0x18000e75a  mov     ecx, [rcx+2Ch]
0x18000e75d  sub     ecx, 1
0x18000e760  jz      loc_18000E9AF
0x18000e766  sub     ecx, 2
0x18000e769  jz      loc_18000E939
0x18000e76f  sub     ecx, 1
0x18000e772  jz      loc_18000E8D8
0x18000e778  cmp     ecx, 3
0x18000e77b  jz      short loc_18000E7BC
0x18000e77d  movups  xmm0, xmmword ptr [r9]
0x18000e781  movaps  [rsp+0B8h+var_58], xmm0
0x18000e786  movsd   xmm1, qword ptr [r9+10h]
0x18000e78c  movsd   [rsp+0B8h+var_48], xmm1
0x18000e792  mov     [rsp+0B8h+var_90], r13
0x18000e797  mov     [rsp+0B8h+var_98], rsi
0x18000e79c  lea     r9, [r11-58h]
0x18000e7a0  mov     rcx, r10
0x18000e7a3  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000e7a8  mov     esi, eax
0x18000e7aa  test    eax, eax
0x18000e7ac  jns     loc_18000E871
0x18000e7b2  mov     edx, 0A2h
0x18000e7b7  jmp     loc_18000EA27
0x18000e7bc  mov     [rsp+0B8h+var_78], rbx
0x18000e7c1  lea     rdx, [rsp+0B8h+arg_8]
0x18000e7c9  lea     rcx, [rsp+0B8h+var_78]
0x18000e7ce  call    ??$MakeAndInitialize@VRebootRequest@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VRebootRequest@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<RebootRequest>>,IConfigManager2URI * &)
0x18000e7d3  mov     r14d, eax
0x18000e7d6  test    eax, eax
0x18000e7d8  jns     short loc_18000E818
0x18000e7da  mov     rcx, [rsp+0B8h]; this
0x18000e7e2  mov     r9d, eax; char *
0x18000e7e5  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000e7ec  mov     edx, 96h; void *
0x18000e7f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e7f6  nop
0x18000e7f7  mov     rcx, [rsp+0B8h+var_78]
0x18000e7fc  test    rcx, rcx
0x18000e7ff  jz      short loc_18000E813
0x18000e801  mov     [rsp+0B8h+var_78], rbx
0x18000e806  mov     rax, [rcx]
0x18000e809  mov     rax, [rax+10h]
0x18000e80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e812  nop
0x18000e813  jmp     loc_18000E9F4
0x18000e818  mov     rdx, [rsp+0B8h+var_78]
0x18000e81d  add     rdx, 38h ; '8'
0x18000e821  mov     ecx, 1
0x18000e826  call    ChangeCount
0x18000e82b  test    eax, eax
0x18000e82d  jns     short loc_18000E84B
0x18000e82f  mov     rcx, [rsp+0B8h]; this
0x18000e837  mov     r9d, eax; char *
0x18000e83a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\provcsp\\reboo"...
0x18000e841  mov     edx, 5Bh ; '['; void *
0x18000e846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e84b  mov     r9, [rsp+0B8h+var_78]
0x18000e850  add     r9, 18h
0x18000e854  mov     al, cs:byte_18004A3D0
0x18000e85a  mov     byte ptr [rsp+0B8h+var_98], al
0x18000e85e  lea     rdx, [rsp+0B8h+var_70]
0x18000e863  call    ??$_Insert_nohint@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring const &,std::_Nil>(bool,std::wstring const &,std::_Nil)
0x18000e868  nop
0x18000e869  mov     rax, [rsp+0B8h+var_78]
0x18000e86e  mov     [rsi], rax
0x18000e871  cmp     [rsp+0B8h+ppvData], rbx
0x18000e876  jz      short loc_18000E888
0x18000e878  mov     rcx, [rdi+8]; psa
0x18000e87c  call    cs:__imp_SafeArrayUnaccessData
0x18000e883  nop     dword ptr [rax+rax+00h]
0x18000e888  xor     eax, eax
0x18000e88a  jmp     loc_18000EBA5
0x18000e88f  mov     rcx, [rsp+0B8h+var_78]
0x18000e894  xor     ebx, ebx
0x18000e896  test    rcx, rcx
0x18000e899  jz      short loc_18000E8AD
0x18000e89b  mov     [rsp+0B8h+var_78], rbx
0x18000e8a0  mov     rax, [rcx]
0x18000e8a3  mov     rax, [rax+10h]
0x18000e8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ac  nop
0x18000e8ad  cmp     [rsp+0B8h+ppvData], rbx
0x18000e8b2  jz      short loc_18000E8CC
0x18000e8b4  mov     rcx, [rsp+0B8h+arg_18]
0x18000e8bc  mov     rcx, [rcx+8]; psa
0x18000e8c0  call    cs:__imp_SafeArrayUnaccessData
0x18000e8c7  nop     dword ptr [rax+rax+00h]
0x18000e8cc  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18000e8d3  jmp     loc_18000EBA5
0x18000e8d8  mov     [rsp+0B8h+var_78], rbx
0x18000e8dd  lea     rcx, [rsp+0B8h+var_78]
0x18000e8e2  call    ??$MakeAndInitialize@VAddPackageNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAddPackageNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<AddPackageNode,AddPackageNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AddPackageNode>>,IConfigManager2URI * &)
0x18000e8e7  mov     r14d, eax
0x18000e8ea  test    eax, eax
0x18000e8ec  jns     short loc_18000E92C
0x18000e8ee  mov     rcx, [rsp+0B8h]; this
0x18000e8f6  mov     r9d, eax; char *
0x18000e8f9  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000e900  mov     edx, 8Eh; void *
0x18000e905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e90a  nop
0x18000e90b  mov     rcx, [rsp+0B8h+var_78]
0x18000e910  test    rcx, rcx
0x18000e913  jz      short loc_18000E927
0x18000e915  mov     [rsp+0B8h+var_78], rbx
0x18000e91a  mov     rax, [rcx]
0x18000e91d  mov     rax, [rax+10h]
0x18000e921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e926  nop
0x18000e927  jmp     loc_18000E9F4
0x18000e92c  mov     rax, [rsp+0B8h+var_78]
0x18000e931  mov     [rsi], rax
0x18000e934  jmp     loc_18000E871
0x18000e939  cmp     r12d, 8
0x18000e93d  jz      short loc_18000E949
0x18000e93f  mov     edx, 81h
0x18000e944  jmp     loc_18000EA79
0x18000e949  mov     [rsp+0B8h+var_78], rbx
0x18000e94e  lea     rdx, [rsp+0B8h+arg_8]
0x18000e956  lea     rcx, [rsp+0B8h+var_78]
0x18000e95b  call    ??$MakeAndInitialize@VPackageNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VPackageNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PackageNode,PackageNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<PackageNode>>,IConfigManager2URI * &)
0x18000e960  mov     r14d, eax
0x18000e963  test    eax, eax
0x18000e965  jns     short loc_18000E9A2
0x18000e967  mov     rcx, [rsp+0B8h]; this
0x18000e96f  mov     r9d, eax; char *
0x18000e972  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000e979  mov     edx, 85h; void *
0x18000e97e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e983  nop
0x18000e984  mov     rcx, [rsp+0B8h+var_78]
0x18000e989  test    rcx, rcx
0x18000e98c  jz      short loc_18000E9A0
0x18000e98e  mov     [rsp+0B8h+var_78], rbx
0x18000e993  mov     rax, [rcx]
0x18000e996  mov     rax, [rax+10h]
0x18000e99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e99f  nop
0x18000e9a0  jmp     short loc_18000E9F4
0x18000e9a2  mov     rax, [rsp+0B8h+var_78]
0x18000e9a7  mov     [rsi], rax
0x18000e9aa  jmp     loc_18000E871
0x18000e9af  mov     dword ptr [rsp+0B8h+arg_8], ebx
0x18000e9b6  mov     rax, [rdx]
0x18000e9b9  lea     rdx, [rsp+0B8h+arg_8]
0x18000e9c1  mov     rcx, r15
0x18000e9c4  mov     rax, [rax+88h]
0x18000e9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d0  mov     r14d, eax
0x18000e9d3  test    eax, eax
0x18000e9d5  jns     short loc_18000EA13
0x18000e9d7  mov     edx, 68h ; 'h'; void *
0x18000e9dc  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000e9e3  mov     r9d, r14d; char *
0x18000e9e6  mov     rcx, [rsp+0B8h]; this
0x18000e9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9f3  nop
0x18000e9f4  cmp     [rsp+0B8h+ppvData], rbx
0x18000e9f9  jz      short loc_18000EA0B
0x18000e9fb  mov     rcx, [rdi+8]; psa
0x18000e9ff  call    cs:__imp_SafeArrayUnaccessData
0x18000ea06  nop     dword ptr [rax+rax+00h]
0x18000ea0b  mov     eax, r14d
0x18000ea0e  jmp     loc_18000EBA5
0x18000ea13  cmp     dword ptr [rsp+0B8h+arg_8], 1
0x18000ea1b  jz      short loc_18000EA5D
0x18000ea1d  mov     esi, 80070057h
0x18000ea22  mov     edx, 69h ; 'i'; void *
0x18000ea27  mov     rcx, [rsp+0B8h]; this
0x18000ea2f  mov     r9d, esi; char *
0x18000ea32  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ea39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea3e  nop
0x18000ea3f  cmp     [rsp+0B8h+ppvData], rbx
0x18000ea44  jz      short loc_18000EA56
0x18000ea46  mov     rcx, [rdi+8]; psa
0x18000ea4a  call    cs:__imp_SafeArrayUnaccessData
0x18000ea51  nop     dword ptr [rax+rax+00h]
0x18000ea56  mov     eax, esi
0x18000ea58  jmp     loc_18000EBA5
0x18000ea5d  cmp     r12d, 6
0x18000ea61  jz      short loc_18000EA6A
0x18000ea63  mov     edx, 6Ah ; 'j'
0x18000ea68  jmp     short loc_18000EA79
0x18000ea6a  mov     eax, 2011h
0x18000ea6f  cmp     [rdi], ax
0x18000ea72  jz      short loc_18000EAB5
0x18000ea74  mov     edx, 6Bh ; 'k'; void *
0x18000ea79  mov     r9d, 86000011h; char *
0x18000ea7f  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\provcsp\\add.c"...
0x18000ea86  mov     rcx, [rsp+0B8h]; this
0x18000ea8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea93  nop
0x18000ea94  cmp     [rsp+0B8h+ppvData], rbx
0x18000ea99  jz      short loc_18000EAAB
0x18000ea9b  mov     rcx, [rdi+8]; psa
0x18000ea9f  call    cs:__imp_SafeArrayUnaccessData
0x18000eaa6  nop     dword ptr [rax+rax+00h]
0x18000eaab  mov     eax, 86000011h
0x18000eab0  jmp     loc_18000EBA5
0x18000eab5  mov     [rsp+0B8h+var_78], rbx
0x18000eaba  mov     rax, [r15]
0x18000eabd  lea     r8, [rsp+0B8h+var_78]
0x18000eac2  xor     edx, edx
0x18000eac4  mov     rcx, r15
0x18000eac7  mov     rax, [rax+58h]
0x18000eacb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ead0  mov     r14d, eax
0x18000ead3  test    eax, eax
0x18000ead5  jns     short loc_18000EAE1
0x18000ead7  mov     edx, 70h ; 'p'
0x18000eadc  jmp     loc_18000E9DC
0x18000eae1  lea     rdx, [rsp+0B8h+ppvData]; ppvData
0x18000eae6  mov     rcx, [rdi+8]; psa
0x18000eaea  call    cs:__imp_SafeArrayAccessData
0x18000eaf1  nop     dword ptr [rax+rax+00h]
0x18000eaf6  mov     r14d, eax
0x18000eaf9  test    eax, eax
0x18000eafb  jns     short loc_18000EB07
0x18000eafd  mov     edx, 71h ; 'q'
0x18000eb02  jmp     loc_18000E9DC
0x18000eb07  lea     r8, [rsp+0B8h+plUbound]; plUbound
0x18000eb0c  mov     edx, 1; nDim
0x18000eb11  mov     rcx, [rdi+8]; psa
0x18000eb15  call    cs:__imp_SafeArrayGetUBound
0x18000eb1c  nop     dword ptr [rax+rax+00h]
0x18000eb21  mov     r14d, eax
0x18000eb24  test    eax, eax
0x18000eb26  jns     short loc_18000EB32
0x18000eb28  mov     edx, 72h ; 'r'
0x18000eb2d  jmp     loc_18000E9DC
0x18000eb32  mov     edx, [rsp+0B8h+plUbound]
0x18000eb36  inc     edx; cbCertEncoded
0x18000eb38  mov     [rsp+0B8h+plUbound], edx
0x18000eb3c  mov     rcx, [rsp+0B8h+ppvData]; pbCertEncoded
0x18000eb41  call    ?ValidateCertificate@@YAJQEAEK@Z; ValidateCertificate(uchar * const,ulong)
0x18000eb46  mov     r14d, eax
0x18000eb49  test    eax, eax
0x18000eb4b  jns     short loc_18000EB57
0x18000eb4d  mov     edx, 76h ; 'v'
0x18000eb52  jmp     loc_18000E9DC
0x18000eb57  mov     edx, [rsp+0B8h+plUbound]; cbCertEncoded
0x18000eb5b  mov     rcx, [rsp+0B8h+ppvData]; pbCertEncoded
0x18000eb60  call    ?StoreCertificateInRegStore@CProvisioningNode@@CAJQEAEK@Z; CProvisioningNode::StoreCertificateInRegStore(uchar * const,ulong)
0x18000eb65  mov     r14d, eax
0x18000eb68  test    eax, eax
0x18000eb6a  jns     short loc_18000EB76
0x18000eb6c  mov     edx, 77h ; 'w'
0x18000eb71  jmp     loc_18000E9DC
0x18000eb76  mov     r9, r13; unsigned int *
0x18000eb79  mov     r8, rsi; struct ICSPNode **
0x18000eb7c  mov     rdx, r15; struct IConfigManager2URI *
0x18000eb7f  mov     rcx, [rsp+0B8h+arg_0]; this
0x18000eb87  call    ?CreateChildNodeFromUri@CProvisioningNode@@AEAAJPEAUIConfigManager2URI@@PEAPEAUICSPNode@@PEAK@Z; CProvisioningNode::CreateChildNodeFromUri(IConfigManager2URI *,ICSPNode * *,ulong *)
0x18000eb8c  mov     esi, eax
0x18000eb8e  test    eax, eax
0x18000eb90  jns     loc_18000E871
0x18000eb96  mov     edx, 7Ah ; 'z'
0x18000eb9b  jmp     loc_18000EA27
0x18000eba0  mov     eax, 80004003h
0x18000eba5  add     rsp, 80h
0x18000ebac  pop     r15
0x18000ebae  pop     r14
0x18000ebb0  pop     r13
0x18000ebb2  pop     r12
0x18000ebb4  pop     rdi
0x18000ebb5  pop     rsi
  ... truncated ...
```
