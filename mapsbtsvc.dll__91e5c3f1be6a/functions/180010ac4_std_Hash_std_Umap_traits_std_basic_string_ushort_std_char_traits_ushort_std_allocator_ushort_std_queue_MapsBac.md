# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<MapsBackgroundTransferJob::RequestContext,std::deque<MapsBackgroundTransferJob::RequestContext,std::allocator<MapsBackgroundTransferJob::RequestContext>>>>,void *> * const)

- ea: `0x180010ac4`
- end: `0x180010bee`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010de4`

## callees

- `0x18000b880`
- `0x18000fbd8`
- `0x180010ac4`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rsi
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  _QWORD *v15; // rax
  unsigned __int64 v17; // rax
  __int64 v18; // r12
  bool v19; // bl
  _QWORD *v20; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = a1[3];
    v8 = (_QWORD *)a1[1];
    v20 = a1 + 1;
    v21 = v6;
    v22 = a2;
    v9 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2 + 16);
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v7 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v24 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Range_eraser::_Bump_erased(&v20);
      if ( v14 )
        break;
      v10 = v22;
      v12 = v24;
      if ( v22 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v7 + 8 * v11) = v10;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v8;
      v6 = v8;
    }
    for ( *(_QWORD *)(v7 + 8 * v11 + 8) = v6; ; *(_QWORD *)(v7 + 8 * v11 + 8) = v8 )
    {
      v10 = v22;
      if ( v22 == a3 )
        break;
      v17 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(v22 + 16);
      v11 = 2 * (a1[6] & v17);
      v18 = *(_QWORD *)(v7 + 16 * (a1[6] & v17) + 8);
      while ( 1 )
      {
        v19 = v10 == v18;
        std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Range_eraser::_Bump_erased(&v20);
        if ( v19 )
          break;
        v10 = v22;
        if ( v22 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v7 + 8 * v11) = v8;
    }
LABEL_7:
    v15 = v21;
    *v21 = v10;
    *(_QWORD *)(v10 + 8) = v15;
  }
  return a3;
}

```

## disassembly

```asm
0x180010ac4  mov     r11, rsp
0x180010ac7  mov     [r11+18h], rbx
0x180010acb  mov     [r11+8], rcx
0x180010acf  push    rbp
0x180010ad0  push    rsi
0x180010ad1  push    rdi
0x180010ad2  push    r12
0x180010ad4  push    r13
0x180010ad6  push    r14
0x180010ad8  push    r15
0x180010ada  sub     rsp, 40h
0x180010ade  mov     rdi, r8
0x180010ae1  mov     rbp, rdx
0x180010ae4  mov     rbx, rcx
0x180010ae7  cmp     rdx, r8
0x180010aea  jz      short loc_180010B6A
0x180010aec  mov     r12, [rdx+8]
0x180010af0  lea     rax, [rcx+8]
0x180010af4  mov     rsi, [rcx+18h]
0x180010af8  lea     rcx, [rdx+10h]
0x180010afc  mov     r15, [rax]
0x180010aff  mov     [r11-58h], rax
0x180010b03  mov     [r11-50h], r12
0x180010b07  mov     r11, rdx
0x180010b0a  mov     [rsp+78h+var_48], rdx
0x180010b0f  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180010b14  mov     r14, rax
0x180010b17  and     r14, [rbx+30h]
0x180010b1b  add     r14, r14
0x180010b1e  mov     rax, [rsi+r14*8+8]
0x180010b23  mov     r13, [rsi+r14*8]
0x180010b27  mov     [rsp+78h+arg_8], rax
0x180010b2f  cmp     r11, rax
0x180010b32  lea     rcx, [rsp+78h+var_58]
0x180010b37  setz    bl
0x180010b3a  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Range_eraser::_Bump_erased(void)
0x180010b3f  test    bl, bl
0x180010b41  jnz     short loc_180010B85
0x180010b43  mov     r11, [rsp+78h+var_48]
0x180010b48  mov     rax, [rsp+78h+arg_8]
0x180010b50  cmp     r11, rdi
0x180010b53  jnz     short loc_180010B2F
0x180010b55  cmp     r13, rbp
0x180010b58  jnz     short loc_180010B5E
0x180010b5a  mov     [rsi+r14*8], r11
0x180010b5e  mov     rax, [rsp+78h+var_50]
0x180010b63  mov     [rax], r11
0x180010b66  mov     [r11+8], rax
0x180010b6a  mov     rbx, [rsp+78h+arg_10]
0x180010b72  mov     rax, rdi
0x180010b75  add     rsp, 40h
0x180010b79  pop     r15
0x180010b7b  pop     r14
0x180010b7d  pop     r13
0x180010b7f  pop     r12
0x180010b81  pop     rdi
0x180010b82  pop     rsi
0x180010b83  pop     rbp
0x180010b84  retn
0x180010b85  cmp     r13, rbp
0x180010b88  jnz     short loc_180010B91
0x180010b8a  mov     [rsi+r14*8], r15
0x180010b8e  mov     r12, r15
0x180010b91  mov     [rsi+r14*8+8], r12
0x180010b96  mov     rbp, [rsp+78h+arg_0]
0x180010b9e  mov     r11, [rsp+78h+var_48]
0x180010ba3  cmp     r11, rdi
0x180010ba6  jz      short loc_180010B5E
0x180010ba8  lea     rcx, [r11+10h]
0x180010bac  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180010bb1  mov     r14, rax
0x180010bb4  and     r14, [rbp+30h]
0x180010bb8  add     r14, r14
0x180010bbb  mov     r12, [rsi+r14*8+8]
0x180010bc0  cmp     r11, r12
0x180010bc3  lea     rcx, [rsp+78h+var_58]
0x180010bc8  setz    bl
0x180010bcb  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<MapsBackgroundTransferJob::RequestContext>>>,0>>::_Range_eraser::_Bump_erased(void)
0x180010bd0  test    bl, bl
0x180010bd2  jnz     short loc_180010BE3
0x180010bd4  mov     r11, [rsp+78h+var_48]
0x180010bd9  cmp     r11, rdi
0x180010bdc  jnz     short loc_180010BC0
0x180010bde  jmp     loc_180010B5A
0x180010be3  mov     [rsi+r14*8], r15
0x180010be7  mov     [rsi+r14*8+8], r15
0x180010bec  jmp     short loc_180010B9E
```
