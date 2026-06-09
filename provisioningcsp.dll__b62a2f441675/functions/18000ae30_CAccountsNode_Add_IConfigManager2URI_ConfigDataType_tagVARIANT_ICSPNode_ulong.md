# CAccountsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000ae30`
- end: `0x18000afe9`
- name: `?Add@CAccountsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `441`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006974`
- `0x18000aa98`
- `0x18000abb0`
- `0x18000ae30`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000aee4`
- `msvcrt!_wcsicmp` at `0x18000af62`
- `msvcrt!_wcsicmp` at `0x18000aee4`
- `msvcrt!_wcsicmp` at `0x18000af62`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccountsNode::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _DWORD *a6)
{
  _QWORD *v8; // rsi
  _DWORD *v9; // rdi
  int v10; // ebx
  __int64 v11; // rdx
  int v13; // eax
  _DWORD *v14; // rcx
  int v15; // eax
  _DWORD *v16; // rcx
  wchar_t *String1; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]

  v8 = a5;
  *a5 = 0;
  v9 = a6;
  *a6 = 0;
  LODWORD(a5) = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)a2 + 136LL))(a2, &a5);
  if ( v10 < 0 )
  {
    v11 = 95;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
      (const char *)(unsigned int)v10,
      (int)String1);
    return (unsigned int)v10;
  }
  if ( (_DWORD)a5 != 1 )
  {
    v10 = -2147024809;
    v11 = 96;
    goto LABEL_3;
  }
  String1 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
  if ( v10 < 0 )
  {
    v11 = 99;
    goto LABEL_3;
  }
  if ( !_wcsicmp(String1, L"Domain") )
  {
    a6 = 0;
    v13 = Microsoft::WRL::Details::MakeAndInitialize<DomainNode,DomainNode,CConfigServiceProvider2Impl * &,IConfigManager2URI * &>(
            &a6,
            a1 + 16);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
        (const char *)(unsigned int)v13,
        (int)String1);
      v14 = a6;
      if ( a6 )
      {
        a6 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return (unsigned int)v10;
    }
    *v8 = a6;
    *v9 |= 2u;
    return 0;
  }
  if ( !_wcsicmp(String1, L"Users") )
  {
    a6 = 0;
    v15 = Microsoft::WRL::Details::MakeAndInitialize<LocalAccountsNode,LocalAccountsNode,IConfigManager2URI * &>(&a6);
    v10 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\accountsnode.cpp",
        (const char *)(unsigned int)v15,
        (int)String1);
      v16 = a6;
      if ( a6 )
      {
        a6 = 0;
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
      }
      return (unsigned int)v10;
    }
    *v8 = a6;
    *v9 = 0;
    return 0;
  }
  return 2248146946LL;
}

```

## disassembly

```asm
0x18000ae30  push    rbp
0x18000ae32  push    rbx
0x18000ae33  push    rsi
0x18000ae34  push    rdi
0x18000ae35  push    r14
0x18000ae37  push    r15
0x18000ae39  mov     rbp, rsp
0x18000ae3c  sub     rsp, 38h
0x18000ae40  mov     r14, rdx
0x18000ae43  mov     r15, rcx
0x18000ae46  mov     rsi, [rbp+arg_20]
0x18000ae4a  mov     qword ptr [rsi], 0
0x18000ae51  mov     rdi, [rbp+arg_28]
0x18000ae55  mov     dword ptr [rdi], 0
0x18000ae5b  mov     dword ptr [rbp+arg_20], 0
0x18000ae62  mov     rax, [rdx]
0x18000ae65  lea     rdx, [rbp+arg_20]
0x18000ae69  mov     rcx, r14
0x18000ae6c  mov     rax, [rax+88h]
0x18000ae73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae78  mov     ebx, eax
0x18000ae7a  test    eax, eax
0x18000ae7c  jns     short loc_18000AE9D
0x18000ae7e  mov     edx, 5Fh ; '_'; void *
0x18000ae83  mov     rcx, [rbp+30h]; this
0x18000ae87  mov     r9d, ebx; char *
0x18000ae8a  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000ae91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae96  mov     eax, ebx
0x18000ae98  jmp     loc_18000AFDB
0x18000ae9d  cmp     dword ptr [rbp+arg_20], 1
0x18000aea1  jz      short loc_18000AEAF
0x18000aea3  mov     ebx, 80070057h
0x18000aea8  mov     edx, 60h ; '`'
0x18000aead  jmp     short loc_18000AE83
0x18000aeaf  mov     [rbp+String1], 0
0x18000aeb7  mov     rax, [r14]
0x18000aeba  lea     r8, [rbp+String1]
0x18000aebe  xor     edx, edx
0x18000aec0  mov     rcx, r14
0x18000aec3  mov     rax, [rax+58h]
0x18000aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecc  mov     ebx, eax
0x18000aece  test    eax, eax
0x18000aed0  jns     short loc_18000AED9
0x18000aed2  mov     edx, 63h ; 'c'
0x18000aed7  jmp     short loc_18000AE83
0x18000aed9  lea     rdx, ?gc_wszAccountsDomainNode@@3QBGB; "Domain"
0x18000aee0  mov     rcx, [rbp+String1]; String1
0x18000aee4  call    cs:__imp__wcsicmp
0x18000aeeb  nop     dword ptr [rax+rax+00h]
0x18000aef0  test    eax, eax
0x18000aef2  jnz     short loc_18000AF57
0x18000aef4  mov     [rbp+arg_28], 0
0x18000aefc  lea     rdx, [r15+10h]
0x18000af00  lea     rcx, [rbp+arg_28]
0x18000af04  call    ??$MakeAndInitialize@VDomainNode@@V1@AEAPEAVCConfigServiceProvider2Impl@@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VDomainNode@@@WRL@Microsoft@@@012@AEAPEAVCConfigServiceProvider2Impl@@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<DomainNode,DomainNode,CConfigServiceProvider2Impl * &,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DomainNode>>,CConfigServiceProvider2Impl * &,IConfigManager2URI * &)
0x18000af09  mov     ebx, eax
0x18000af0b  test    eax, eax
0x18000af0d  jns     short loc_18000AF4B
0x18000af0f  mov     rcx, [rbp+30h]; this
0x18000af13  mov     r9d, eax; char *
0x18000af16  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000af1d  mov     edx, 68h ; 'h'; void *
0x18000af22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af27  nop
0x18000af28  mov     rcx, [rbp+arg_28]
0x18000af2c  test    rcx, rcx
0x18000af2f  jz      short loc_18000AF46
0x18000af31  mov     [rbp+arg_28], 0
0x18000af39  mov     rax, [rcx]
0x18000af3c  mov     rax, [rax+10h]
0x18000af40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af45  nop
0x18000af46  jmp     loc_18000AE96
0x18000af4b  mov     rax, [rbp+arg_28]
0x18000af4f  mov     [rsi], rax
0x18000af52  or      dword ptr [rdi], 2
0x18000af55  jmp     short loc_18000AFD2
0x18000af57  lea     rdx, ?gc_wszAccountsLocalNode@@3QBGB; "Users"
0x18000af5e  mov     rcx, [rbp+String1]; String1
0x18000af62  call    cs:__imp__wcsicmp
0x18000af69  nop     dword ptr [rax+rax+00h]
0x18000af6e  test    eax, eax
0x18000af70  jnz     short loc_18000AFD6
0x18000af72  mov     [rbp+arg_28], 0
0x18000af7a  lea     rcx, [rbp+arg_28]
0x18000af7e  call    ??$MakeAndInitialize@VLocalAccountsNode@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VLocalAccountsNode@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<LocalAccountsNode,LocalAccountsNode,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<LocalAccountsNode>>,IConfigManager2URI * &)
0x18000af83  mov     ebx, eax
0x18000af85  test    eax, eax
0x18000af87  jns     short loc_18000AFC5
0x18000af89  mov     rcx, [rbp+30h]; this
0x18000af8d  mov     r9d, eax; char *
0x18000af90  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\provcsp\\accou"...
0x18000af97  mov     edx, 70h ; 'p'; void *
0x18000af9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afa1  nop
0x18000afa2  mov     rcx, [rbp+arg_28]
0x18000afa6  test    rcx, rcx
0x18000afa9  jz      short loc_18000AFC0
0x18000afab  mov     [rbp+arg_28], 0
0x18000afb3  mov     rax, [rcx]
0x18000afb6  mov     rax, [rax+10h]
0x18000afba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbf  nop
0x18000afc0  jmp     loc_18000AE96
0x18000afc5  mov     rax, [rbp+arg_28]
0x18000afc9  mov     [rsi], rax
0x18000afcc  mov     dword ptr [rdi], 0
0x18000afd2  xor     eax, eax
0x18000afd4  jmp     short loc_18000AFDB
0x18000afd6  mov     eax, 86000002h
0x18000afdb  add     rsp, 38h
0x18000afdf  pop     r15
0x18000afe1  pop     r14
0x18000afe3  pop     rdi
0x18000afe4  pop     rsi
0x18000afe5  pop     rbx
0x18000afe6  pop     rbp
0x18000afe7  retn
```
