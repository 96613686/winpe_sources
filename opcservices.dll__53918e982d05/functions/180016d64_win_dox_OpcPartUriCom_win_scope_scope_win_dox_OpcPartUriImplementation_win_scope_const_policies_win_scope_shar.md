# win_dox::OpcPartUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>>::ComparePartUri_Safe(IOpcPartUri *,int *)

- ea: `0x180016d64`
- end: `0x180017310`
- name: `?ComparePartUri_Safe@?$OpcPartUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$OpcUriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$UriCom@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@V?$ScopeInnerStore@V?$scope@PEAVOpcPartUriImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@UIOpcPartUri@@Ureport_policy_throw@2@@win_dox@@@win_dox@@@win_dox@@@win_dox@@AEAAXPEAUIOpcPartUri@@PEAH@Z`
- size: `1452`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800162e4`

## callees

- `0x180016bf0`
- `0x180016d00`
- `0x180016d64`
- `0x180017410`
- `0x1800175b0`
- `0x1800190e0`
- `0x1800195ac`
- `0x180058f20`
- `0x1800cd1c4`
- `0x1800cded0`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180016ec9`
- `msvcrt!memcpy_s` at `0x18001711c`
- `msvcrt!memcpy_s` at `0x180016ec9`
- `msvcrt!memcpy_s` at `0x18001711c`

## string_xrefs

- `0x180017246`: `partUri`
- `0x180017252`: `ComparePartUri`
- `0x18001728e`: `ComparePartUri`
- `0x180017282`: `comparison`
- `0x18001725e`: `OpcPartUriCom`
- `0x18001729a`: `OpcPartUriCom`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall win_dox::OpcPartUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::OpcUriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::UriCom<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_dox::ScopeInnerStore<win_scope::scope<win_dox::OpcPartUriImplementation *,win_scope::const_policies<win_scope::shared_policies>>,IOpcPartUri,win_scope::report_policy_throw>>>>::ComparePartUri_Safe(
        __int64 a1,
        __int64 a2,
        int *a3)
{
  _QWORD *v5; // r12
  int v6; // r14d
  __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  _QWORD *v9; // r8
  void **v10; // rcx
  void **v11; // rcx
  void **v12; // rcx
  void **v13; // rcx
  void **v14; // rax
  __int16 v15; // r8
  unsigned __int64 v16; // r8
  void **v17; // rdx
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 Path; // rdx
  __int64 NormalizedPartNameInternal; // rax
  __int64 v25; // rsi
  unsigned __int64 v26; // rdi
  _QWORD *v27; // r8
  unsigned __int64 v28; // rdx
  void **v29; // rsi
  void *v30; // rcx
  _QWORD *v31; // rcx
  __int64 v32; // [rsp+48h] [rbp-99h] BYREF
  __int64 v33; // [rsp+50h] [rbp-91h] BYREF
  __int64 v34; // [rsp+58h] [rbp-89h] BYREF
  __int64 v35; // [rsp+60h] [rbp-81h] BYREF
  _QWORD v36[3]; // [rsp+68h] [rbp-79h] BYREF
  char v37[8]; // [rsp+80h] [rbp-61h] BYREF
  void *Destination[2]; // [rsp+88h] [rbp-59h] BYREF
  unsigned __int64 v39; // [rsp+98h] [rbp-49h]
  unsigned __int64 v40; // [rsp+A0h] [rbp-41h]
  char v41[8]; // [rsp+A8h] [rbp-39h] BYREF
  void *v42; // [rsp+B0h] [rbp-31h]
  __int64 v43; // [rsp+C0h] [rbp-21h]
  unsigned __int64 v44; // [rsp+C8h] [rbp-19h]
  char v45[8]; // [rsp+D0h] [rbp-11h] BYREF
  void *Block; // [rsp+D8h] [rbp-9h]
  unsigned __int64 v47; // [rsp+F0h] [rbp+Fh]

  v36[1] = -2;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 180, L"OpcPartUriCom", L"ComparePartUri", L"partUri", 0);
  if ( !a3 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", 0, 181, L"OpcPartUriCom", L"ComparePartUri", L"comparison", 0);
  win_dox::to_interface<IReceiver>::resolve(&v33);
  win_dox::to_interface<IReceiver>::resolve(&v32);
  win_dox::to_interface<IReceiver>::resolve(&v34);
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  win_dox::to_interface<IReceiver>::resolve(&v35);
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  win_dox::to_interface<IReceiver>::resolve(v36);
  v5 = *(_QWORD **)(a1 + 16);
  v6 = -1;
  if ( !v5[5] )
  {
    v21 = 0;
    v32 = 0;
    v22 = *v5;
    if ( *v5 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22 + 8LL))(*v5);
      v21 = v32;
    }
    else
    {
      v22 = 0;
    }
    v32 = v22;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v36[2] = &v32;
    win_dox::to_interface<IByteReceiver>::resolve(&v33);
    if ( v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v32 = 0;
    }
    Path = win_dox::Uri::GetPath(&v33, v45);
    NormalizedPartNameInternal = win_dox::GetNormalizedPartNameInternal(v41, Path);
    v25 = NormalizedPartNameInternal;
    v26 = *(_QWORD *)(NormalizedPartNameInternal + 24);
    if ( v5 + 2 == (_QWORD *)NormalizedPartNameInternal )
    {
      std::wstring::erase(v5 + 2, *(_QWORD *)(NormalizedPartNameInternal + 24), -1);
      std::wstring::erase(v5 + 2, 0, 0);
    }
    else
    {
      if ( v26 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v5[6] >= v26 )
      {
        if ( !v26 )
        {
          v31 = v5 + 3;
          if ( v5[6] >= 8u )
            v31 = (_QWORD *)*v31;
          v5[5] = 0;
          *(_WORD *)v31 = 0;
          goto LABEL_67;
        }
        goto LABEL_60;
      }
      std::wstring::_Copy(v5 + 2, v26, v5[5]);
      if ( v26 )
      {
LABEL_60:
        v27 = (_QWORD *)(v25 + 8);
        if ( *(_QWORD *)(v25 + 32) >= 8u )
          v27 = (_QWORD *)*v27;
        v28 = v5[6];
        v29 = (void **)(v5 + 3);
        if ( v28 < 8 )
          v30 = v5 + 3;
        else
          v30 = *v29;
        memcpy_s(v30, 2 * v28, v27, 2 * v26);
        if ( v5[6] >= 8u )
          v29 = (void **)*v29;
        v5[5] = v26;
        *((_WORD *)v29 + v26) = 0;
      }
    }
LABEL_67:
    if ( v44 >= 8 )
      operator delete(v42);
    v44 = 7;
    v43 = 0;
    LOWORD(v42) = 0;
    if ( v47 >= 8 )
      operator delete(Block);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v7 = win_dox::Uri::GetPath(&v34, v45);
  v40 = 7;
  v39 = 0;
  LOWORD(Destination[0]) = 0;
  v8 = *(_QWORD *)(v7 + 24);
  if ( v37 == (char *)v7 )
  {
    std::wstring::erase(v37, v8, -1);
    std::wstring::erase(v37, 0, 0);
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( v40 < v8 )
    {
      std::wstring::_Copy(v37, v8, v39);
      if ( v8 )
        goto LABEL_12;
    }
    else
    {
      if ( v8 )
      {
LABEL_12:
        v9 = (_QWORD *)(v7 + 8);
        if ( *(_QWORD *)(v7 + 32) >= 8u )
          v9 = (_QWORD *)*v9;
        v10 = Destination;
        if ( v40 >= 8 )
          v10 = (void **)Destination[0];
        memcpy_s(v10, 2 * v40, v9, 2 * v8);
        v11 = Destination;
        if ( v40 >= 8 )
          v11 = (void **)Destination[0];
        v39 = v8;
        *((_WORD *)v11 + v8) = 0;
        goto LABEL_19;
      }
      v39 = 0;
      LOWORD(Destination[0]) = 0;
    }
  }
LABEL_19:
  v12 = Destination;
  if ( v40 >= 8 )
    v12 = (void **)Destination[0];
  v13 = (void **)((char *)v12 + 2 * v39);
  v14 = Destination;
  if ( v40 >= 8 )
    v14 = (void **)Destination[0];
  while ( v14 != v13 )
  {
    v15 = *(_WORD *)v14;
    if ( (unsigned __int16)(*(_WORD *)v14 - 97) <= 0x19u )
      v15 -= 32;
    *(_WORD *)v14 = v15;
    v14 = (void **)((char *)v14 + 2);
  }
  if ( v47 >= 8 )
    operator delete(Block);
  v16 = v39;
  v17 = Destination;
  if ( v40 >= 8 )
    v17 = (void **)Destination[0];
  v18 = v5[5];
  v19 = v39;
  if ( v18 < v39 )
    v19 = v5[5];
  v20 = v5 + 3;
  if ( v5[6] >= 8u )
    v20 = (_QWORD *)*v20;
  while ( v19 )
  {
    if ( *(_WORD *)v20 != *(_WORD *)v17 )
    {
      v6 = *(_WORD *)v20 < *(_WORD *)v17 ? -1 : 1;
      goto LABEL_39;
    }
    v20 = (_QWORD *)((char *)v20 + 2);
    v17 = (void **)((char *)v17 + 2);
    --v19;
  }
  if ( v18 >= v39 )
    v6 = v18 != v39;
LABEL_39:
  if ( v40 >= 8 )
    operator delete(Destination[0]);
  *a3 = v6;
  if ( v36[0] )
    (*(void (__fastcall **)(_QWORD, void **, unsigned __int64))(*(_QWORD *)v36[0] + 16LL))(v36[0], v17, v16);
  if ( v35 )
    (*(void (__fastcall **)(__int64, void **, unsigned __int64))(*(_QWORD *)v35 + 16LL))(v35, v17, v16);
  if ( v34 )
    (*(void (__fastcall **)(__int64, void **, unsigned __int64))(*(_QWORD *)v34 + 16LL))(v34, v17, v16);
}

```

## disassembly

```asm
0x180016d64  mov     rax, rsp
0x180016d67  push    rbp
0x180016d68  push    rsi
0x180016d69  push    rdi
0x180016d6a  push    r12
0x180016d6c  push    r13
0x180016d6e  push    r14
0x180016d70  push    r15
0x180016d72  lea     rbp, [rax-5Fh]
0x180016d76  sub     rsp, 100h
0x180016d7d  mov     [rbp+57h+var_C8], 0FFFFFFFFFFFFFFFEh
0x180016d85  mov     [rax+20h], rbx
0x180016d89  mov     rax, cs:__security_cookie
0x180016d90  xor     rax, rsp
0x180016d93  mov     [rbp+57h+var_40], rax
0x180016d97  mov     r13, r8
0x180016d9a  mov     rbx, rdx
0x180016d9d  mov     rsi, rcx
0x180016da0  xor     r15d, r15d
0x180016da3  test    rdx, rdx
0x180016da6  jz      loc_180017241
0x180016dac  test    r8, r8
0x180016daf  jz      loc_18001727D
0x180016db5  lea     rcx, [rsp+130h+var_E8]
0x180016dba  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180016dbf  nop
0x180016dc0  mov     rdi, [rax]
0x180016dc3  mov     rdx, rdi
0x180016dc6  lea     rcx, [rsp+130h+var_F0]
0x180016dcb  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180016dd0  nop
0x180016dd1  mov     rdx, [rax]
0x180016dd4  lea     rcx, [rsp+130h+var_E0]
0x180016dd9  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180016dde  nop
0x180016ddf  mov     rcx, [rsp+130h+var_F0]
0x180016de4  test    rcx, rcx
0x180016de7  jz      short loc_180016DFA
0x180016de9  mov     rax, [rcx]
0x180016dec  mov     rax, [rax+10h]
0x180016df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df5  mov     [rsp+130h+var_F0], r15
0x180016dfa  mov     rdx, rdi
0x180016dfd  lea     rcx, [rsp+130h+var_D8]
0x180016e02  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180016e07  nop
0x180016e08  mov     rcx, [rsp+130h+var_E8]
0x180016e0d  test    rcx, rcx
0x180016e10  jz      short loc_180016E23
0x180016e12  mov     rax, [rcx]
0x180016e15  mov     rax, [rax+10h]
0x180016e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e1e  mov     [rsp+130h+var_E8], r15
0x180016e23  mov     rdx, rbx
0x180016e26  lea     rcx, [rbp+57h+var_D0]
0x180016e2a  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x180016e2f  nop
0x180016e30  mov     r12, [rsi+10h]
0x180016e34  lea     rbx, [r12+10h]
0x180016e39  or      r14, 0FFFFFFFFFFFFFFFFh
0x180016e3d  mov     rsi, 7FFFFFFFFFFFFFFEh
0x180016e47  cmp     [rbx+18h], r15
0x180016e4b  jz      loc_18001703F
0x180016e51  lea     rdx, [rbp+57h+var_68]
0x180016e55  lea     rcx, [rsp+130h+var_E0]
0x180016e5a  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x180016e5f  mov     rbx, rax
0x180016e62  mov     [rbp+57h+var_98], 7
0x180016e6a  mov     [rbp+57h+var_A0], r15
0x180016e6e  mov     word ptr [rbp+57h+Destination], r15w
0x180016e73  mov     rdi, [rax+18h]
0x180016e77  lea     rax, [rbp+57h+var_B8]
0x180016e7b  cmp     rax, rbx
0x180016e7e  jz      loc_1800172E3
0x180016e84  cmp     rdi, rsi
0x180016e87  ja      loc_180017305
0x180016e8d  cmp     [rbp+57h+var_98], rdi
0x180016e91  jb      loc_180017021
0x180016e97  test    rdi, rdi
0x180016e9a  jz      loc_180017183
0x180016ea0  lea     r8, [rbx+8]
0x180016ea4  cmp     qword ptr [rbx+20h], 8
0x180016ea9  jb      short loc_180016EAE
0x180016eab  mov     r8, [r8]; Source
0x180016eae  mov     rdx, [rbp+57h+var_98]
0x180016eb2  lea     rcx, [rbp+57h+Destination]
0x180016eb6  cmp     rdx, 8
0x180016eba  cmovnb  rcx, [rbp+57h+Destination]; Destination
0x180016ebf  lea     rbx, [rdi+rdi]
0x180016ec3  add     rdx, rdx; DestinationSize
0x180016ec6  mov     r9, rbx; SourceSize
0x180016ec9  call    cs:__imp_memcpy_s
0x180016ecf  lea     rcx, [rbp+57h+Destination]
0x180016ed3  cmp     [rbp+57h+var_98], 8
0x180016ed8  cmovnb  rcx, [rbp+57h+Destination]
0x180016edd  mov     [rbp+57h+var_A0], rdi
0x180016ee1  mov     [rbx+rcx], r15w
0x180016ee6  lea     rcx, [rbp+57h+Destination]
0x180016eea  cmp     [rbp+57h+var_98], 8
0x180016eef  cmovnb  rcx, [rbp+57h+Destination]
0x180016ef4  mov     rax, [rbp+57h+var_A0]
0x180016ef8  lea     rcx, [rcx+rax*2]
0x180016efc  lea     rax, [rbp+57h+Destination]
0x180016f00  cmovnb  rax, [rbp+57h+Destination]
0x180016f05  cmp     rax, rcx
0x180016f08  jz      short loc_180016F22
0x180016f0a  movzx   r8d, word ptr [rax]
0x180016f0e  lea     edx, [r8-61h]
0x180016f12  cmp     dx, 19h
0x180016f16  jbe     short loc_180016F7E
0x180016f18  mov     [rax], r8w
0x180016f1c  add     rax, 2
0x180016f20  jmp     short loc_180016F05
0x180016f22  cmp     [rbp+57h+var_48], 8
0x180016f27  jnb     loc_180017005
0x180016f2d  mov     r8, [rbp+57h+var_A0]
0x180016f31  lea     rdx, [rbp+57h+Destination]
0x180016f35  cmp     [rbp+57h+var_98], 8
0x180016f3a  cmovnb  rdx, [rbp+57h+Destination]
0x180016f3f  mov     r9, [r12+28h]
0x180016f44  mov     rcx, r8
0x180016f47  cmp     r9, r8
0x180016f4a  cmovb   rcx, r9
0x180016f4e  lea     rax, [r12+18h]
0x180016f53  cmp     qword ptr [r12+30h], 8
0x180016f59  jb      short loc_180016F5E
0x180016f5b  mov     rax, [rax]
0x180016f5e  test    rcx, rcx
0x180016f61  jz      loc_18001722A
0x180016f67  movzx   r10d, word ptr [rax]
0x180016f6b  cmp     r10w, [rdx]
0x180016f6f  jnz     short loc_180016F85
0x180016f71  add     rax, 2
0x180016f75  add     rdx, 2
0x180016f79  dec     rcx
0x180016f7c  jmp     short loc_180016F5E
0x180016f7e  sub     r8w, 20h ; ' '
0x180016f83  jmp     short loc_180016F18
0x180016f85  sbb     r14d, r14d
0x180016f88  and     r14d, 0FFFFFFFEh
0x180016f8c  inc     r14d
0x180016f8f  cmp     [rbp+57h+var_98], 8
0x180016f94  jnb     short loc_180017013
0x180016f96  mov     [r13+0], r14d
0x180016f9a  mov     rcx, [rbp+57h+var_D0]
0x180016f9e  test    rcx, rcx
0x180016fa1  jz      short loc_180016FB0
0x180016fa3  mov     rax, [rcx]
0x180016fa6  mov     rax, [rax+10h]
0x180016faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016faf  nop
0x180016fb0  mov     rcx, [rsp+130h+var_D8]
0x180016fb5  test    rcx, rcx
0x180016fb8  jz      short loc_180016FC7
0x180016fba  mov     rax, [rcx]
0x180016fbd  mov     rax, [rax+10h]
0x180016fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc6  nop
0x180016fc7  mov     rcx, [rsp+130h+var_E0]
0x180016fcc  test    rcx, rcx
0x180016fcf  jz      short loc_180016FDE
0x180016fd1  mov     rax, [rcx]
0x180016fd4  mov     rax, [rax+10h]
0x180016fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fdd  nop
0x180016fde  mov     rcx, [rbp+57h+var_40]
0x180016fe2  xor     rcx, rsp; StackCookie
0x180016fe5  call    __security_check_cookie
0x180016fea  mov     rbx, [rsp+130h+arg_18]
0x180016ff2  add     rsp, 100h
0x180016ff9  pop     r15
0x180016ffb  pop     r14
0x180016ffd  pop     r13
0x180016fff  pop     r12
0x180017001  pop     rdi
0x180017002  pop     rsi
0x180017003  pop     rbp
0x180017004  retn
0x180017005  mov     rcx, [rbp+57h+Block]; Block
0x180017009  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001700e  jmp     loc_180016F2D
0x180017013  mov     rcx, [rbp+57h+Destination]; Block
0x180017017  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001701c  jmp     loc_180016F96
0x180017021  mov     r8, [rbp+57h+var_A0]
0x180017025  mov     rdx, rdi
0x180017028  lea     rcx, [rbp+57h+var_B8]
0x18001702c  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180017031  test    rdi, rdi
0x180017034  jz      loc_180016EE6
0x18001703a  jmp     loc_180016EA0
0x18001703f  mov     rcx, r15
0x180017042  mov     [rsp+130h+var_F0], rcx
0x180017047  mov     rdi, [r12]
0x18001704b  test    rdi, rdi
0x18001704e  jz      loc_1800171B4
0x180017054  mov     rax, [rdi]
0x180017057  mov     rcx, rdi
0x18001705a  mov     rax, [rax+8]
0x18001705e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017063  mov     rcx, [rsp+130h+var_F0]
0x180017068  mov     [rsp+130h+var_F0], rdi
0x18001706d  test    rcx, rcx
0x180017070  jnz     loc_1800171BC
0x180017076  lea     rax, [rsp+130h+var_F0]
0x18001707b  mov     [rbp+57h+var_C0], rax
0x18001707f  lea     rdx, [rsp+130h+var_F0]
0x180017084  lea     rcx, [rsp+130h+var_E8]
0x180017089  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18001708e  nop
0x18001708f  mov     rcx, [rsp+130h+var_F0]
0x180017094  test    rcx, rcx
0x180017097  jnz     loc_18001719E
0x18001709d  lea     rdx, [rbp+57h+var_68]
0x1800170a1  lea     rcx, [rsp+130h+var_E8]
0x1800170a6  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x1800170ab  nop
0x1800170ac  mov     rdx, rax
0x1800170af  lea     rcx, [rbp+57h+var_90]
0x1800170b3  call    ?GetNormalizedPartNameInternal@win_dox@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV23@@Z; win_dox::GetNormalizedPartNameInternal(std::wstring const &)
0x1800170b8  mov     rsi, rax
0x1800170bb  mov     rdi, [rax+18h]
0x1800170bf  cmp     rbx, rax
0x1800170c2  jz      loc_1800172B9
0x1800170c8  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800170d2  cmp     rdi, rax
0x1800170d5  ja      loc_1800172D9
0x1800170db  cmp     [rbx+20h], rdi
0x1800170df  jb      loc_1800171E9
0x1800170e5  test    rdi, rdi
0x1800170e8  jz      loc_18001720E
0x1800170ee  lea     r8, [rsi+8]
0x1800170f2  cmp     qword ptr [rsi+20h], 8
0x1800170f7  jb      short loc_1800170FC
0x1800170f9  mov     r8, [r8]; Source
0x1800170fc  mov     rdx, [rbx+20h]
0x180017100  lea     rsi, [r12+18h]
0x180017105  cmp     rdx, 8
0x180017109  jb      loc_180017206
0x18001710f  mov     rcx, [rsi]; Destination
0x180017112  lea     r15, [rdi+rdi]
0x180017116  add     rdx, rdx; DestinationSize
0x180017119  mov     r9, r15; SourceSize
0x18001711c  call    cs:__imp_memcpy_s
0x180017122  cmp     qword ptr [rbx+20h], 8
0x180017127  jb      short loc_18001712C
0x180017129  mov     rsi, [rsi]
0x18001712c  mov     [rbx+18h], rdi
0x180017130  xor     eax, eax
0x180017132  mov     [r15+rsi], ax
0x180017137  xor     r15d, r15d
0x18001713a  cmp     [rbp+57h+var_70], 8
0x18001713f  jnb     loc_1800171CD
0x180017145  mov     [rbp+57h+var_70], 7
0x18001714d  mov     [rbp+57h+var_78], r15
0x180017151  mov     word ptr [rbp+57h+var_88], r15w
0x180017156  cmp     [rbp+57h+var_48], 8
0x18001715b  jnb     short loc_1800171DB
0x18001715d  mov     rcx, [rsp+130h+var_E8]
0x180017162  test    rcx, rcx
0x180017165  jz      short loc_180017174
0x180017167  mov     rax, [rcx]
0x18001716a  mov     rax, [rax+10h]
0x18001716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017173  nop
0x180017174  mov     rsi, 7FFFFFFFFFFFFFFEh
0x18001717e  jmp     loc_180016E51
0x180017183  lea     rcx, [rbp+57h+Destination]
0x180017187  cmp     [rbp+57h+var_98], 8
0x18001718c  cmovnb  rcx, [rbp+57h+Destination]
0x180017191  mov     [rbp+57h+var_A0], r15
0x180017195  mov     [rcx], r15w
0x180017199  jmp     loc_180016EE6
0x18001719e  mov     rax, [rcx]
0x1800171a1  mov     rax, [rax+10h]
0x1800171a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171aa  mov     [rsp+130h+var_F0], r15
0x1800171af  jmp     loc_18001709D
0x1800171b4  mov     rdi, r15
0x1800171b7  jmp     loc_180017068
0x1800171bc  mov     rax, [rcx]
0x1800171bf  mov     rax, [rax+10h]
0x1800171c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c8  jmp     loc_180017076
0x1800171cd  mov     rcx, [rbp+57h+var_88]; Block
0x1800171d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800171d6  jmp     loc_180017145
0x1800171db  mov     rcx, [rbp+57h+Block]; Block
0x1800171df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800171e4  jmp     loc_18001715D
0x1800171e9  mov     r8, [rbx+18h]
0x1800171ed  mov     rdx, rdi
0x1800171f0  mov     rcx, rbx
0x1800171f3  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800171f8  test    rdi, rdi
0x1800171fb  jz      loc_18001713A
0x180017201  jmp     loc_1800170EE
0x180017206  mov     rcx, rsi
0x180017209  jmp     loc_180017112
0x18001720e  lea     rcx, [r12+18h]
  ... truncated ...
```
