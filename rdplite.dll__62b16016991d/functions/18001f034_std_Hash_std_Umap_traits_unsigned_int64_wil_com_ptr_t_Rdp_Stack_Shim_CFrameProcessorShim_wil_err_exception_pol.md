# std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18001f034`
- end: `0x18001f1a6`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@IEAAX_K@Z`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c52c`

## callees

- `0x180008be0`
- `0x18000d118`
- `0x18001cd38`
- `0x18001effc`
- `0x18001f034`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 *v7; // rcx
  unsigned __int64 v8; // r8
  __int64 i; // r10
  unsigned __int64 appended; // rax
  unsigned __int64 **v11; // rdx
  unsigned __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // r9
  unsigned __int64 *v15; // rax
  unsigned __int64 v16; // rdi
  _QWORD *v17; // rdx
  unsigned __int64 *v18; // rax
  unsigned __int64 **v19; // rdi
  _QWORD *v20; // rdx
  unsigned __int64 *v21; // rax
  _QWORD *v22; // rdx
  unsigned __int64 *v23; // rax
  __int64 v25; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(v25) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v25) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(
    a1 + 3,
    2 * v6,
    v4);
  a1[7] = v6;
  a1[6] = v6 - 1;
  for ( i = *(_QWORD *)a1[1]; i != v4; i = v13 )
  {
    appended = std::_Fnv1a_append_bytes((unsigned __int64)v7, (const unsigned __int8 *const)(i + 16), v8);
    v14 = a1[3];
    v8 = 2 * (a1[6] & appended);
    if ( *(_QWORD *)(v14 + 16 * (a1[6] & appended)) == v4 )
    {
      *(_QWORD *)(v14 + 16 * (a1[6] & appended)) = v12;
LABEL_7:
      *(_QWORD *)(v14 + 8 * v8 + 8) = v12;
      continue;
    }
    v15 = *(unsigned __int64 **)(v14 + 16 * (a1[6] & appended) + 8);
    v7 = *v11;
    if ( *v11 == (unsigned __int64 *)v15[2] )
    {
      v16 = *v15;
      if ( *v15 != v12 )
      {
        v17 = *(_QWORD **)(v12 + 8);
        *v17 = v13;
        v7 = *(unsigned __int64 **)(v13 + 8);
        *v7 = v16;
        v18 = *(unsigned __int64 **)(v16 + 8);
        *v18 = v12;
        *(_QWORD *)(v16 + 8) = v7;
        *(_QWORD *)(v13 + 8) = v17;
        *(_QWORD *)(v12 + 8) = v18;
      }
      goto LABEL_7;
    }
    while ( 1 )
    {
      v19 = (unsigned __int64 **)(v15 + 1);
      if ( *(unsigned __int64 **)(v14 + 8 * v8) == v15 )
        break;
      v15 = *v19;
      if ( v7 == (unsigned __int64 *)(*v19)[2] )
      {
        v8 = *v15;
        v20 = *(_QWORD **)(v12 + 8);
        *v20 = v13;
        v7 = *(unsigned __int64 **)(v13 + 8);
        *v7 = v8;
        v21 = *(unsigned __int64 **)(v8 + 8);
        *v21 = v12;
        *(_QWORD *)(v8 + 8) = v7;
        *(_QWORD *)(v13 + 8) = v20;
        *(_QWORD *)(v12 + 8) = v21;
        goto LABEL_15;
      }
    }
    v22 = *(_QWORD **)(v12 + 8);
    *v22 = v13;
    v7 = *(unsigned __int64 **)(v13 + 8);
    *v7 = (unsigned __int64)v15;
    v23 = *v19;
    *v23 = v12;
    *v19 = v7;
    *(_QWORD *)(v13 + 8) = v22;
    *(_QWORD *)(v12 + 8) = v23;
    *(_QWORD *)(v14 + 8 * v8) = v12;
LABEL_15:
    ;
  }
  v25 = 0;
  return std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(&v25);
}

```

## disassembly

```asm
0x18001f034  push    rbx
0x18001f036  push    rsi
0x18001f037  push    rdi
0x18001f038  push    r14
0x18001f03a  sub     rsp, 28h
0x18001f03e  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001f048  mov     dword ptr [rsp+48h+arg_8], 0
0x18001f050  mov     rsi, rcx
0x18001f053  mov     edi, 1
0x18001f058  bsr     rcx, rax
0x18001f05c  mov     eax, edi
0x18001f05e  shl     rax, cl
0x18001f061  cmp     rdx, rax
0x18001f064  jbe     short loc_18001F073
0x18001f066  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001f06d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001f073  mov     rbx, [rsi+8]
0x18001f077  lea     rax, [rdx-1]
0x18001f07b  or      rax, rdi
0x18001f07e  mov     dword ptr [rsp+48h+arg_8], 0
0x18001f086  bsr     rcx, rax
0x18001f08a  mov     r8, rbx
0x18001f08d  inc     ecx
0x18001f08f  shl     rdi, cl
0x18001f092  lea     rcx, [rsi+18h]
0x18001f096  lea     rdx, [rdi+rdi]
0x18001f09a  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAUIUnknown@@U?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<IUnknown * const,std::pair<wil::com_ptr_t<IUnknown,wil::err_exception_policy>,void *>>>>>)
0x18001f09f  mov     [rsi+38h], rdi
0x18001f0a3  lea     rax, [rdi-1]
0x18001f0a7  mov     [rsi+30h], rax
0x18001f0ab  mov     r10, [rsi+8]
0x18001f0af  mov     r10, [r10]
0x18001f0b2  mov     r11, r10
0x18001f0b5  cmp     r10, rbx
0x18001f0b8  jz      loc_18001F189
0x18001f0be  mov     r11, [r11]
0x18001f0c1  lea     rdx, [r10+10h]; unsigned __int8 *
0x18001f0c5  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001f0ca  mov     r9, [rsi+18h]
0x18001f0ce  mov     r8, rax
0x18001f0d1  and     r8, [rsi+30h]
0x18001f0d5  add     r8, r8
0x18001f0d8  cmp     [r9+r8*8], rbx
0x18001f0dc  jnz     short loc_18001F0EC
0x18001f0de  mov     [r9+r8*8], r10
0x18001f0e2  mov     [r9+r8*8+8], r10
0x18001f0e7  jmp     loc_18001F181
0x18001f0ec  mov     rax, [r9+r8*8+8]
0x18001f0f1  mov     rcx, [rdx]
0x18001f0f4  cmp     rcx, [rax+10h]
0x18001f0f8  jnz     short loc_18001F125
0x18001f0fa  mov     rdi, [rax]
0x18001f0fd  cmp     rdi, r10
0x18001f100  jz      short loc_18001F0E2
0x18001f102  mov     rdx, [r10+8]
0x18001f106  mov     [rdx], r11
0x18001f109  mov     rcx, [r11+8]
0x18001f10d  mov     [rcx], rdi
0x18001f110  mov     rax, [rdi+8]
0x18001f114  mov     [rax], r10
0x18001f117  mov     [rdi+8], rcx
0x18001f11b  mov     [r11+8], rdx
0x18001f11f  mov     [r10+8], rax
0x18001f123  jmp     short loc_18001F0E2
0x18001f125  lea     rdi, [rax+8]
0x18001f129  cmp     [r9+r8*8], rax
0x18001f12d  jz      short loc_18001F15E
0x18001f12f  mov     rax, [rdi]
0x18001f132  cmp     rcx, [rax+10h]
0x18001f136  jnz     short loc_18001F125
0x18001f138  mov     r8, [rax]
0x18001f13b  mov     rdx, [r10+8]
0x18001f13f  mov     [rdx], r11
0x18001f142  mov     rcx, [r11+8]
0x18001f146  mov     [rcx], r8
0x18001f149  mov     rax, [r8+8]
0x18001f14d  mov     [rax], r10
0x18001f150  mov     [r8+8], rcx
0x18001f154  mov     [r11+8], rdx
0x18001f158  mov     [r10+8], rax
0x18001f15c  jmp     short loc_18001F181
0x18001f15e  mov     rdx, [r10+8]
0x18001f162  mov     [rdx], r11
0x18001f165  mov     rcx, [r11+8]
0x18001f169  mov     [rcx], rax
0x18001f16c  mov     rax, [rdi]
0x18001f16f  mov     [rax], r10
0x18001f172  mov     [rdi], rcx
0x18001f175  mov     [r11+8], rdx
0x18001f179  mov     [r10+8], rax
0x18001f17d  mov     [r9+r8*8], r10
0x18001f181  mov     r10, r11
0x18001f184  jmp     loc_18001F0B5
0x18001f189  lea     rcx, [rsp+48h+arg_8]
0x18001f18e  mov     [rsp+48h+arg_8], 0
0x18001f197  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<unsigned __int64,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18001f19c  add     rsp, 28h
0x18001f1a0  pop     r14
0x18001f1a2  pop     rdi
0x18001f1a3  pop     rsi
0x18001f1a4  pop     rbx
0x18001f1a5  retn
```
