# std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *> *,std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>,void *> * const)

- ea: `0x18001f1ac`
- end: `0x18001f2db`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f2e4`
- `0x180020b28`

## callees

- `0x18001efd0`
- `0x18001effc`
- `0x18001f1ac`

## pseudocode

```c
unsigned __int64 __fastcall std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        unsigned __int64 a3)
{
  _QWORD *v5; // r12
  _QWORD *v6; // r15
  __int64 v7; // rsi
  unsigned __int64 appended; // rax
  __int64 v9; // r10
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  _QWORD *v17; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // r12
  bool v21; // bl
  _QWORD *v22; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v23; // [rsp+28h] [rbp-50h]
  __int64 v24; // [rsp+30h] [rbp-48h]
  __int64 v26; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v5 = *(_QWORD **)(a2 + 8);
    v6 = (_QWORD *)a1[1];
    v7 = a1[3];
    v24 = a2;
    v22 = a1 + 1;
    v23 = v5;
    appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, (const unsigned __int8 *const)(a2 + 16), a3);
    v11 = 2 * (*(_QWORD *)(v10 + 48) & appended);
    v12 = *(_QWORD *)(v7 + 16 * (*(_QWORD *)(v10 + 48) & appended) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v26 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v9 == v12;
      std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Range_eraser::_Bump_erased(&v22);
      if ( v14 )
        break;
      v9 = v24;
      v12 = v26;
      if ( v24 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v7 + 8 * v11) = v9;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v6;
      v5 = v6;
    }
    for ( *(_QWORD *)(v7 + 8 * v11 + 8) = v5; ; *(_QWORD *)(v7 + 8 * v11 + 8) = v6 )
    {
      v9 = v24;
      if ( v24 == a3 )
        break;
      v19 = std::_Fnv1a_append_bytes(v15, (const unsigned __int8 *const)(v24 + 16), v16);
      v11 = 2 * (a1[6] & v19);
      v20 = *(_QWORD *)(v7 + 16 * (a1[6] & v19) + 8);
      while ( 1 )
      {
        v21 = v9 == v20;
        std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Range_eraser::_Bump_erased(&v22);
        if ( v21 )
          break;
        v9 = v24;
        if ( v24 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v7 + 8 * v11) = v6;
    }
LABEL_7:
    v17 = v23;
    *v23 = v9;
    *(_QWORD *)(v9 + 8) = v17;
  }
  return a3;
}

```

## disassembly

```asm
0x18001f1ac  mov     [rsp+arg_10], rbx
0x18001f1b1  mov     [rsp+arg_0], rcx
0x18001f1b6  push    rbp
0x18001f1b7  push    rsi
0x18001f1b8  push    rdi
0x18001f1b9  push    r12
0x18001f1bb  push    r13
0x18001f1bd  push    r14
0x18001f1bf  push    r15
0x18001f1c1  sub     rsp, 40h
0x18001f1c5  mov     rdi, r8
0x18001f1c8  mov     rbp, rdx
0x18001f1cb  mov     r11, rcx
0x18001f1ce  cmp     rdx, r8
0x18001f1d1  jz      loc_18001F257
0x18001f1d7  mov     r12, [rdx+8]
0x18001f1db  lea     rax, [rcx+8]
0x18001f1df  mov     r15, [rax]
0x18001f1e2  mov     r10, rdx
0x18001f1e5  mov     rsi, [rcx+18h]
0x18001f1e9  mov     [rsp+78h+var_48], rdx
0x18001f1ee  add     rdx, 10h; unsigned __int8 *
0x18001f1f2  mov     [rsp+78h+var_58], rax
0x18001f1f7  mov     [rsp+78h+var_50], r12
0x18001f1fc  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001f201  mov     r14, rax
0x18001f204  and     r14, [r11+30h]
0x18001f208  add     r14, r14
0x18001f20b  mov     rax, [rsi+r14*8+8]
0x18001f210  mov     r13, [rsi+r14*8]
0x18001f214  mov     [rsp+78h+arg_8], rax
0x18001f21c  cmp     r10, rax
0x18001f21f  lea     rcx, [rsp+78h+var_58]
0x18001f224  setz    bl
0x18001f227  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001f22c  test    bl, bl
0x18001f22e  jnz     short loc_18001F272
0x18001f230  mov     r10, [rsp+78h+var_48]
0x18001f235  mov     rax, [rsp+78h+arg_8]
0x18001f23d  cmp     r10, rdi
0x18001f240  jnz     short loc_18001F21C
0x18001f242  cmp     r13, rbp
0x18001f245  jnz     short loc_18001F24B
0x18001f247  mov     [rsi+r14*8], r10
0x18001f24b  mov     rax, [rsp+78h+var_50]
0x18001f250  mov     [rax], r10
0x18001f253  mov     [r10+8], rax
0x18001f257  mov     rbx, [rsp+78h+arg_10]
0x18001f25f  mov     rax, rdi
0x18001f262  add     rsp, 40h
0x18001f266  pop     r15
0x18001f268  pop     r14
0x18001f26a  pop     r13
0x18001f26c  pop     r12
0x18001f26e  pop     rdi
0x18001f26f  pop     rsi
0x18001f270  pop     rbp
0x18001f271  retn
0x18001f272  cmp     r13, rbp
0x18001f275  jnz     short loc_18001F27E
0x18001f277  mov     [rsi+r14*8], r15
0x18001f27b  mov     r12, r15
0x18001f27e  mov     [rsi+r14*8+8], r12
0x18001f283  mov     rbp, [rsp+78h+arg_0]
0x18001f28b  mov     r10, [rsp+78h+var_48]
0x18001f290  cmp     r10, rdi
0x18001f293  jz      short loc_18001F24B
0x18001f295  lea     rdx, [r10+10h]; unsigned __int8 *
0x18001f299  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18001f29e  mov     r14, rax
0x18001f2a1  and     r14, [rbp+30h]
0x18001f2a5  add     r14, r14
0x18001f2a8  mov     r12, [rsi+r14*8+8]
0x18001f2ad  cmp     r10, r12
0x18001f2b0  lea     rcx, [rsp+78h+var_58]
0x18001f2b5  setz    bl
0x18001f2b8  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@PEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$allocator@U?$pair@QEAXV?$com_ptr_t@UID3D11Texture2D@@Uerr_exception_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<void *,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,wil::com_ptr_t<ID3D11Texture2D,wil::err_exception_policy>>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001f2bd  test    bl, bl
0x18001f2bf  jnz     short loc_18001F2D0
0x18001f2c1  mov     r10, [rsp+78h+var_48]
0x18001f2c6  cmp     r10, rdi
0x18001f2c9  jnz     short loc_18001F2AD
0x18001f2cb  jmp     loc_18001F247
0x18001f2d0  mov     [rsi+r14*8], r15
0x18001f2d4  mov     [rsi+r14*8+8], r15
0x18001f2d9  jmp     short loc_18001F28B
```
