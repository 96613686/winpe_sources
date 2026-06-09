# CProvisioningNode::RemoveRequestByName(IConfigManager2URI *)

- ea: `0x18000de00`
- end: `0x18000dffc`
- name: `?RemoveRequestByName@CProvisioningNode@@AEAAJPEAUIConfigManager2URI@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(CProvisioningNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000db50`

## callees

- `0x180006974`
- `0x180009fac`
- `0x18000a0bc`
- `0x18000a578`
- `0x18000d9a8`
- `0x18000de00`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000def7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000def7`

## string_xrefs

- `0x18000de4b`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`
- `0x18000df42`: `onecoreuap\admin\prov\provcsp\deletechild.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProvisioningNode::RemoveRequestByName(CProvisioningNode *this, struct IConfigManager2URI *a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rbx
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // rcx
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15[2]; // [rsp+20h] [rbp-58h] BYREF
  int v16; // [rsp+28h] [rbp-50h] BYREF
  __int64 v17; // [rsp+30h] [rbp-48h] BYREF
  void *Src; // [rsp+38h] [rbp-40h] BYREF
  struct IConfigManager2URI *v19; // [rsp+40h] [rbp-38h] BYREF
  void *v20[3]; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v19 = a2;
  v16 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v16);
  if ( v3 < 0 )
  {
    v4 = 64;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
      (const char *)(unsigned int)v3,
      v15[0]);
    return (unsigned int)v3;
  }
  if ( v16 != 1 )
  {
    v3 = -2147024809;
    v4 = 65;
    goto LABEL_3;
  }
  Src = 0;
  v3 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, void **))(*(_QWORD *)a2 + 88LL))(a2, 0, &Src);
  if ( v3 < 0 )
  {
    v4 = 68;
    goto LABEL_3;
  }
  v21 = 7;
  v20[2] = 0;
  LOWORD(v20[0]) = 0;
  if ( *(_WORD *)Src )
  {
    v6 = -1;
    do
      ++v6;
    while ( *((_WORD *)Src + v6) );
  }
  std::wstring::assign(v20, Src);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(
    v7,
    &v17,
    v20);
  if ( v21 >= 8 )
    operator delete(v20[0]);
  v8 = v17;
  if ( v17 == CProvisioningNode::m_rebootRequests )
  {
    v3 = -2046820350;
    v4 = 70;
    goto LABEL_3;
  }
  *(_QWORD *)v15 = 0;
  v9 = Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(v15, &v19);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
      (const char *)(unsigned int)v9,
      v15[0]);
    v11 = *(_QWORD *)v15;
    if ( *(_QWORD *)v15 )
    {
      *(_QWORD *)v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v10;
  }
  try
  {
    (*(void (**)(void))(**(_QWORD **)v15 + 56LL))();
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(
      &CProvisioningNode::m_rebootRequests,
      &v19,
      v8);
  }
  catch ( ... )
  {
    LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x4F,
                     (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\deletechild.cpp",
                     v12);
    v14 = *(_QWORD *)v15;
    if ( *(_QWORD *)v15 )
    {
      *(_QWORD *)v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)v17;
  }
  v13 = *(_QWORD *)v15;
  if ( *(_QWORD *)v15 )
  {
    *(_QWORD *)v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18000de00  mov     r11, rsp
0x18000de03  mov     [r11+8], rbx
0x18000de07  mov     [r11+18h], rsi
0x18000de0b  push    rdi
0x18000de0c  sub     rsp, 70h
0x18000de10  mov     rax, cs:__security_cookie
0x18000de17  xor     rax, rsp
0x18000de1a  mov     [rsp+78h+var_10], rax
0x18000de1f  mov     rsi, rdx
0x18000de22  mov     [r11-38h], rdx
0x18000de26  xor     edi, edi
0x18000de28  mov     [rsp+78h+var_50], edi
0x18000de2c  mov     rax, [rdx]
0x18000de2f  lea     rdx, [r11-50h]
0x18000de33  mov     rcx, rsi
0x18000de36  mov     rax, [rax+88h]
0x18000de3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de42  mov     ebx, eax
0x18000de44  test    eax, eax
0x18000de46  jns     short loc_18000DE66
0x18000de48  lea     edx, [rdi+40h]; void *
0x18000de4b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000de52  mov     r9d, ebx; char *
0x18000de55  mov     rcx, [rsp+78h]; this
0x18000de5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de5f  mov     eax, ebx
0x18000de61  jmp     loc_18000DFDC
0x18000de66  cmp     [rsp+78h+var_50], 1
0x18000de6b  jz      short loc_18000DE79
0x18000de6d  mov     ebx, 80070057h
0x18000de72  mov     edx, 41h ; 'A'
0x18000de77  jmp     short loc_18000DE4B
0x18000de79  mov     [rsp+78h+Src], rdi
0x18000de7e  mov     rax, [rsi]
0x18000de81  lea     r8, [rsp+78h+Src]
0x18000de86  xor     edx, edx
0x18000de88  mov     rcx, rsi
0x18000de8b  mov     rax, [rax+58h]
0x18000de8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de94  mov     ebx, eax
0x18000de96  test    eax, eax
0x18000de98  jns     short loc_18000DEA1
0x18000de9a  mov     edx, 44h ; 'D'
0x18000de9f  jmp     short loc_18000DE4B
0x18000dea1  mov     rdx, [rsp+78h+Src]; Src
0x18000dea6  mov     [rsp+78h+var_18], 7
0x18000deaf  mov     [rsp+78h+var_20], rdi
0x18000deb4  mov     word ptr [rsp+78h+var_30], di
0x18000deb9  cmp     [rdx], di
0x18000debc  jnz     short loc_18000DEC3
0x18000debe  mov     r8, rdi
0x18000dec1  jmp     short loc_18000DED1
0x18000dec3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000dec7  inc     r8
0x18000deca  cmp     [rdx+r8*2], di
0x18000decf  jnz     short loc_18000DEC7
0x18000ded1  lea     rcx, [rsp+78h+var_30]; void *
0x18000ded6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000dedb  lea     r8, [rsp+78h+var_30]
0x18000dee0  lea     rdx, [rsp+78h+var_48]
0x18000dee5  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18000deea  cmp     [rsp+78h+var_18], 8
0x18000def0  jb      short loc_18000DF03
0x18000def2  mov     rcx, [rsp+78h+var_30]
0x18000def7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000defe  nop     dword ptr [rax+rax+00h]
0x18000df03  mov     rbx, [rsp+78h+var_48]
0x18000df08  cmp     rbx, cs:?m_rebootRequests@CProvisioningNode@@0V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::set<std::wstring> CProvisioningNode::m_rebootRequests
0x18000df0f  jnz     short loc_18000DF20
0x18000df11  mov     ebx, 86000002h
0x18000df16  mov     edx, 46h ; 'F'
0x18000df1b  jmp     loc_18000DE4B
0x18000df20  mov     qword ptr [rsp+78h+var_58], rdi; int
0x18000df25  lea     rdx, [rsp+78h+var_38]
0x18000df2a  lea     rcx, [rsp+78h+var_58]
0x18000df2f  call    ??$MakeAndInitialize@VRebootRequest@@V1@AEAPEAUIConfigManager2URI@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VRebootRequest@@@WRL@Microsoft@@@012@AEAPEAUIConfigManager2URI@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RebootRequest,RebootRequest,IConfigManager2URI * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<RebootRequest>>,IConfigManager2URI * &)
0x18000df34  mov     esi, eax
0x18000df36  test    eax, eax
0x18000df38  jns     short loc_18000DF74
0x18000df3a  mov     rcx, [rsp+78h]; this
0x18000df3f  mov     r9d, eax; char *
0x18000df42  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\provcsp\\delet"...
0x18000df49  mov     edx, 49h ; 'I'; void *
0x18000df4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df53  nop
0x18000df54  mov     rcx, qword ptr [rsp+78h+var_58]
0x18000df59  test    rcx, rcx
0x18000df5c  jz      short loc_18000DF70
0x18000df5e  mov     qword ptr [rsp+78h+var_58], rdi
0x18000df63  mov     rax, [rcx]
0x18000df66  mov     rax, [rax+10h]
0x18000df6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df6f  nop
0x18000df70  mov     eax, esi
0x18000df72  jmp     short loc_18000DFDC
0x18000df74  mov     rcx, qword ptr [rsp+78h+var_58]
0x18000df79  mov     rax, [rcx]
0x18000df7c  mov     rax, [rax+38h]
0x18000df80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df85  mov     r8, rbx
0x18000df88  lea     rdx, [rsp+78h+var_38]
0x18000df8d  lea     rcx, ?m_rebootRequests@CProvisioningNode@@0V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::set<std::wstring> CProvisioningNode::m_rebootRequests
0x18000df94  call    ?erase@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@V32@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>)
0x18000df99  nop
0x18000df9a  mov     rcx, qword ptr [rsp+78h+var_58]
0x18000df9f  test    rcx, rcx
0x18000dfa2  jz      short loc_18000DFB6
0x18000dfa4  mov     qword ptr [rsp+78h+var_58], rdi
0x18000dfa9  mov     rax, [rcx]
0x18000dfac  mov     rax, [rax+10h]
0x18000dfb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfb5  nop
0x18000dfb6  xor     eax, eax
0x18000dfb8  jmp     short loc_18000DFDC
0x18000dfba  mov     rcx, qword ptr [rsp+78h+var_58]
0x18000dfbf  xor     edi, edi
0x18000dfc1  test    rcx, rcx
0x18000dfc4  jz      short loc_18000DFD8
0x18000dfc6  mov     qword ptr [rsp+78h+var_58], rdi
0x18000dfcb  mov     rax, [rcx]
0x18000dfce  mov     rax, [rax+10h]
0x18000dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd7  nop
0x18000dfd8  mov     eax, dword ptr [rsp+78h+var_48]
0x18000dfdc  mov     rcx, [rsp+78h+var_10]
0x18000dfe1  xor     rcx, rsp; StackCookie
0x18000dfe4  call    __security_check_cookie
0x18000dfe9  lea     r11, [rsp+78h+var_8]
0x18000dfee  mov     rbx, [r11+10h]
0x18000dff2  mov     rsi, [r11+20h]
0x18000dff6  mov     rsp, r11
0x18000dff9  pop     rdi
0x18000dffa  retn
```
