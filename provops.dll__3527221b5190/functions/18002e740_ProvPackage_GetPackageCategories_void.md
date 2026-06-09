# ProvPackage::GetPackageCategories(void)

- ea: `0x18002e740`
- end: `0x18002e966`
- name: `?GetPackageCategories@ProvPackage@@QEBAAEBV?$set@IU?$less@I@std@@V?$allocator@I@2@@std@@XZ`
- size: `550`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180023d4c`
- `0x180023f14`

## callees

- `0x180002f44`
- `0x18000de00`
- `0x18001b388`
- `0x180028d48`
- `0x18002defc`
- `0x18002e288`
- `0x18002e740`
- `0x180031354`
- `0x180032f1c`
- `0x180033520`
- `0x180033724`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002e914`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e936`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e914`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002e936`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002e7b1`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002e7b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall ProvPackage::GetPackageCategories(_QWORD *a1)
{
  _QWORD *v2; // r14
  const struct ICategoryIndex *Instance; // r12
  const struct ICategoryIndex **v4; // r15
  __int64 v5; // rsi
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  int v8; // eax
  struct IStream *i; // rcx
  ProvXmlEnumerator *v10; // rbx
  struct IStream *v11; // rax
  bool v12; // dl
  struct IStream *v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdi
  int v16; // r8d
  ProvXmlEnumerator *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v22; // [rsp+20h] [rbp-60h]
  char v23; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v24[3]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v25[24]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v27; // [rsp+C0h] [rbp+40h] BYREF
  struct IStream *v28; // [rsp+C8h] [rbp+48h]
  __int64 v29; // [rsp+D0h] [rbp+50h] BYREF
  ProvXmlEnumerator *v30; // [rsp+D8h] [rbp+58h] BYREF

  v2 = a1 + 19;
  if ( !a1[20] )
  {
    Instance = CategoryIndex::GetInstance();
    v4 = (const struct ICategoryIndex **)operator new(8u);
    *v4 = Instance;
    v5 = 0;
    v29 = 0;
    v6 = a1[13];
    if ( v6 )
    {
      v29 = a1[13];
    }
    else
    {
      v7 = a1 + 1;
      if ( a1[4] >= 8u )
        v7 = (_QWORD *)*v7;
      v8 = OpenProvisioningPackageForRead(v7, &v29);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
          (const char *)(unsigned int)v8,
          v22);
      v6 = v29;
      if ( v29 )
        v5 = v29;
    }
    ProvXmlEnumerator::CreateInstance((__int64 *)&v30, v6);
    for ( i = 0; ; i = v28 )
    {
      v10 = v30;
      if ( i )
      {
        v28 = 0;
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)i + 16LL))(i);
      }
      v11 = 0;
      v28 = 0;
      if ( *((_QWORD *)v10 + 1) && *((_QWORD *)v10 + 2) && *((_QWORD *)v10 + 3) )
      {
        v11 = ProvXmlEnumerator::CheckElements(v10);
        v28 = v11;
        v12 = v11 != 0;
        v13 = v11;
      }
      else
      {
        v12 = 0;
        v13 = 0;
      }
      if ( !v12 )
        break;
      CategoryResolver::GetPaths(v13, v24, v11);
      v14 = v24[0];
      v15 = v24[1];
      while ( v14 != v15 )
      {
        std::vector<std::wstring>::vector<std::wstring>(v25, v14);
        v27 = (**(__int64 (__fastcall ***)(const struct ICategoryIndex *, _BYTE *))Instance)(Instance, v25);
        std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Insert_nohint<unsigned int,std::_Nil>(
          (_DWORD)v2,
          (unsigned int)&v23,
          v16,
          (unsigned int)&v27,
          byte_18004AED0);
        std::vector<std::wstring>::_Tidy((__int64)v25);
        v14 += 24;
      }
      std::vector<std::vector<std::wstring>>::~vector<std::vector<std::wstring>>(v24);
    }
    if ( v13 )
    {
      v28 = 0;
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v17 = v30;
    if ( v30 )
    {
      v18 = *((_QWORD *)v30 + 3);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = *((_QWORD *)v17 + 2);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v20 = *((_QWORD *)v17 + 1);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
      operator delete(v17);
    }
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 128LL))(v5);
    operator delete(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e740  push    rbp
0x18002e742  push    rbx
0x18002e743  push    rsi
0x18002e744  push    rdi
0x18002e745  push    r12
0x18002e747  push    r14
0x18002e749  push    r15
0x18002e74b  mov     rbp, rsp
0x18002e74e  sub     rsp, 80h
0x18002e755  mov     rbx, rcx
0x18002e758  lea     r14, [rcx+98h]
0x18002e75f  cmp     qword ptr [r14+8], 0
0x18002e764  jnz     loc_18002E93C
0x18002e76a  call    ?GetInstance@CategoryIndex@@SAPEBUICategoryIndex@@XZ; CategoryIndex::GetInstance(void)
0x18002e76f  mov     r12, rax
0x18002e772  mov     ecx, 8; Size
0x18002e777  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e77c  mov     r15, rax
0x18002e77f  mov     [rbp+var_48], rax
0x18002e783  mov     [rax], r12
0x18002e786  xor     esi, esi
0x18002e788  mov     [rbp+var_50], rsi
0x18002e78c  mov     [rbp+arg_10], rsi
0x18002e790  mov     rdx, [rbx+68h]
0x18002e794  test    rdx, rdx
0x18002e797  jz      short loc_18002E79F
0x18002e799  mov     [rbp+arg_10], rdx
0x18002e79d  jmp     short loc_18002E7D2
0x18002e79f  lea     rcx, [rbx+8]
0x18002e7a3  cmp     qword ptr [rcx+18h], 8
0x18002e7a8  jb      short loc_18002E7AD
0x18002e7aa  mov     rcx, [rcx]
0x18002e7ad  lea     rdx, [rbp+arg_10]
0x18002e7b1  call    cs:__imp_OpenProvisioningPackageForRead
0x18002e7b7  mov     rcx, [rbp+38h]; this
0x18002e7bb  test    eax, eax
0x18002e7bd  js      loc_18002E951
0x18002e7c3  mov     rdx, [rbp+arg_10]
0x18002e7c7  test    rdx, rdx
0x18002e7ca  cmovnz  rsi, rdx
0x18002e7ce  mov     [rbp+var_50], rsi
0x18002e7d2  lea     rcx, [rbp+arg_18]
0x18002e7d6  call    ?CreateInstance@ProvXmlEnumerator@@SA?AV?$unique_ptr@VProvXmlEnumerator@@U?$default_delete@VProvXmlEnumerator@@@std@@@std@@PEAUIProvisioningPackage@@@Z; ProvXmlEnumerator::CreateInstance(IProvisioningPackage *)
0x18002e7db  nop
0x18002e7dc  xor     ecx, ecx
0x18002e7de  mov     rbx, [rbp+arg_18]
0x18002e7e2  test    rcx, rcx
0x18002e7e5  jz      short loc_18002E7FC
0x18002e7e7  mov     [rbp+arg_8], 0
0x18002e7ef  mov     rax, [rcx]
0x18002e7f2  mov     rax, [rax+10h]
0x18002e7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7fb  nop
0x18002e7fc  xor     eax, eax
0x18002e7fe  mov     [rbp+arg_8], rax
0x18002e802  cmp     [rbx+8], rax
0x18002e806  jz      short loc_18002E82B
0x18002e808  cmp     [rbx+10h], rax
0x18002e80c  jz      short loc_18002E82B
0x18002e80e  cmp     [rbx+18h], rax
0x18002e812  jz      short loc_18002E82B
0x18002e814  mov     rcx, rbx; this
0x18002e817  call    ?CheckElements@ProvXmlEnumerator@@AEAAPEAUIStream@@XZ; ProvXmlEnumerator::CheckElements(void)
0x18002e81c  mov     [rbp+arg_8], rax
0x18002e820  test    rax, rax
0x18002e823  setnz   dl
0x18002e826  mov     rcx, rax
0x18002e829  jmp     short loc_18002E82F
0x18002e82b  xor     dl, dl
0x18002e82d  xor     ecx, ecx
0x18002e82f  test    dl, dl
0x18002e831  jz      short loc_18002E8AC
0x18002e833  mov     r8, rax
0x18002e836  lea     rdx, [rbp+var_30]
0x18002e83a  call    ?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAUIStream@@@Z; CategoryResolver::GetPaths(IStream *)
0x18002e83f  nop
0x18002e840  mov     rbx, [rbp+var_30]
0x18002e844  mov     rdi, [rbp+var_28]
0x18002e848  cmp     rbx, rdi
0x18002e84b  jz      short loc_18002E89A
0x18002e84d  mov     rdx, rbx
0x18002e850  lea     rcx, [rbp+var_18]
0x18002e854  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18002e859  nop
0x18002e85a  mov     rax, [r12]
0x18002e85e  lea     rdx, [rbp+var_18]
0x18002e862  mov     rcx, r12
0x18002e865  mov     rax, [rax]
0x18002e868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e86d  mov     [rbp+arg_0], eax
0x18002e870  mov     al, cs:byte_18004AED0
0x18002e876  mov     byte ptr [rsp+80h+var_60], al
0x18002e87a  lea     r9, [rbp+arg_0]
0x18002e87e  lea     rdx, [rbp+var_40]
0x18002e882  mov     rcx, r14
0x18002e885  call    ??$_Insert_nohint@IU_Nil@std@@@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@@std@@_N@1@_N$$QEAIU_Nil@1@@Z; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Insert_nohint<uint,std::_Nil>(bool,uint &&,std::_Nil)
0x18002e88a  nop
0x18002e88b  lea     rcx, [rbp+var_18]
0x18002e88f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002e894  add     rbx, 18h
0x18002e898  jmp     short loc_18002E848
0x18002e89a  lea     rcx, [rbp+var_30]
0x18002e89e  call    ??1?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::~vector<std::vector<std::wstring>>(void)
0x18002e8a3  mov     rcx, [rbp+arg_8]
0x18002e8a7  jmp     loc_18002E7DE
0x18002e8ac  test    rcx, rcx
0x18002e8af  jz      short loc_18002E8C6
0x18002e8b1  mov     [rbp+arg_8], 0
0x18002e8b9  mov     rax, [rcx]
0x18002e8bc  mov     rax, [rax+10h]
0x18002e8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c5  nop
0x18002e8c6  mov     rbx, [rbp+arg_18]
0x18002e8ca  test    rbx, rbx
0x18002e8cd  jz      short loc_18002E91B
0x18002e8cf  mov     rcx, [rbx+18h]
0x18002e8d3  test    rcx, rcx
0x18002e8d6  jz      short loc_18002E8E5
0x18002e8d8  mov     rax, [rcx]
0x18002e8db  mov     rax, [rax+10h]
0x18002e8df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8e4  nop
0x18002e8e5  mov     rcx, [rbx+10h]
0x18002e8e9  test    rcx, rcx
0x18002e8ec  jz      short loc_18002E8FB
0x18002e8ee  mov     rax, [rcx]
0x18002e8f1  mov     rax, [rax+50h]
0x18002e8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8fa  nop
0x18002e8fb  mov     rcx, [rbx+8]
0x18002e8ff  test    rcx, rcx
0x18002e902  jz      short loc_18002E911
0x18002e904  mov     rax, [rcx]
0x18002e907  mov     rax, [rax+8]
0x18002e90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e910  nop
0x18002e911  mov     rcx, rbx
0x18002e914  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002e91a  nop
0x18002e91b  test    rsi, rsi
0x18002e91e  jz      short loc_18002E933
0x18002e920  mov     rdx, [rsi]
0x18002e923  mov     rcx, rsi
0x18002e926  mov     rax, [rdx+80h]
0x18002e92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e932  nop
0x18002e933  mov     rcx, r15
0x18002e936  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002e93c  mov     rax, r14
0x18002e93f  add     rsp, 80h
0x18002e946  pop     r15
0x18002e948  pop     r14
0x18002e94a  pop     r12
0x18002e94c  pop     rdi
0x18002e94d  pop     rsi
0x18002e94e  pop     rbx
0x18002e94f  pop     rbp
0x18002e950  retn
0x18002e951  mov     r9d, eax; char *
0x18002e954  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002e95b  mov     edx, 17Eh; void *
0x18002e960  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
