# CProvisioningNode::QueryRebootRequesterByUri(IConfigManager2URI *)

- ea: `0x180009c80`
- end: `0x180009d6f`
- name: `?QueryRebootRequesterByUri@CProvisioningNode@@CAJPEAUIConfigManager2URI@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180009890`

## callees

- `0x180006974`
- `0x180009c80`
- `0x180009fac`
- `0x18000a578`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009d26`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009d26`

## pseudocode

```c
__int64 __fastcall CProvisioningNode::QueryRebootRequesterByUri(struct IConfigManager2URI *a1)
{
  __int64 v1; // rax
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  void *Src; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  void *v9[3]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v10; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v1 = *(_QWORD *)a1;
  Src = 0;
  v2 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, void **))(v1 + 88))(a1, 2, &Src);
  if ( v2 < 0 )
  {
    v3 = 72;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\provisioningnode.cpp",
      (const char *)(unsigned int)v2,
      (int)Src);
    return (unsigned int)v2;
  }
  v10 = 7;
  v9[2] = 0;
  LOWORD(v9[0]) = 0;
  if ( *(_WORD *)Src )
  {
    v5 = -1;
    do
      ++v5;
    while ( *((_WORD *)Src + v5) );
  }
  std::wstring::assign(v9, Src);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(v6, &v8, v9);
  if ( v10 >= 8 )
    operator delete(v9[0]);
  if ( v8 == CProvisioningNode::m_rebootRequests )
  {
    v2 = -2046820350;
    v3 = 75;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009c80  mov     [rsp-8+arg_8], rbx
0x180009c85  mov     [rsp-8+arg_10], rdi
0x180009c8a  push    rbp
0x180009c8b  mov     rbp, rsp
0x180009c8e  sub     rsp, 60h
0x180009c92  mov     rax, cs:__security_cookie
0x180009c99  xor     rax, rsp
0x180009c9c  mov     [rbp+var_10], rax
0x180009ca0  mov     rax, [rcx]
0x180009ca3  lea     r8, [rbp+Src]
0x180009ca7  xor     edi, edi
0x180009ca9  mov     [rbp+Src], rdi
0x180009cad  mov     rax, [rax+58h]
0x180009cb1  lea     edx, [rdi+2]
0x180009cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb9  mov     ebx, eax
0x180009cbb  test    eax, eax
0x180009cbd  jns     short loc_180009CD9
0x180009cbf  lea     edx, [rdi+48h]; void *
0x180009cc2  mov     rcx, [rbp+8]; this
0x180009cc6  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\provcsp\\provi"...
0x180009ccd  mov     r9d, ebx; char *
0x180009cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cd5  mov     eax, ebx
0x180009cd7  jmp     short loc_180009D50
0x180009cd9  mov     rdx, [rbp+Src]; Src
0x180009cdd  mov     [rbp+var_18], 7
0x180009ce5  mov     [rbp+var_20], rdi
0x180009ce9  mov     word ptr [rbp+var_30], di
0x180009ced  cmp     [rdx], di
0x180009cf0  jnz     short loc_180009CF7
0x180009cf2  mov     r8, rdi
0x180009cf5  jmp     short loc_180009D05
0x180009cf7  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009cfb  inc     r8
0x180009cfe  cmp     [rdx+r8*2], di
0x180009d03  jnz     short loc_180009CFB
0x180009d05  lea     rcx, [rbp+var_30]; void *
0x180009d09  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180009d0e  lea     r8, [rbp+var_30]
0x180009d12  lea     rdx, [rbp+var_38]
0x180009d16  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180009d1b  cmp     [rbp+var_18], 8
0x180009d20  jb      short loc_180009D32
0x180009d22  mov     rcx, [rbp+var_30]
0x180009d26  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009d2d  nop     dword ptr [rax+rax+00h]
0x180009d32  mov     rax, cs:?m_rebootRequests@CProvisioningNode@@0V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@A; std::set<std::wstring> CProvisioningNode::m_rebootRequests
0x180009d39  cmp     [rbp+var_38], rax
0x180009d3d  jnz     short loc_180009D4E
0x180009d3f  mov     ebx, 86000002h
0x180009d44  mov     edx, 4Bh ; 'K'
0x180009d49  jmp     loc_180009CC2
0x180009d4e  xor     eax, eax
0x180009d50  mov     rcx, [rbp+var_10]
0x180009d54  xor     rcx, rsp; StackCookie
0x180009d57  call    __security_check_cookie
0x180009d5c  lea     r11, [rsp+60h+var_s0]
0x180009d61  mov     rbx, [r11+18h]
0x180009d65  mov     rdi, [r11+20h]
0x180009d69  mov     rsp, r11
0x180009d6c  pop     rbp
0x180009d6d  retn
```
