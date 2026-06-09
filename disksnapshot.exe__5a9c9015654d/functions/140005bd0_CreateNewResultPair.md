# CreateNewResultPair

- ea: `0x140005bd0`
- end: `0x140005e08`
- name: `CreateNewResultPair`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140008a38`

## callees

- `0x140001c74`
- `0x140001cb8`
- `0x140001d20`
- `0x140004f34`
- `0x14000549c`
- `0x140005bd0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140005d32`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140005d32`

## pseudocode

```c
__int64 __fastcall CreateNewResultPair(__int64 *a1, __int64 a2)
{
  _OWORD *v4; // rax
  void *v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  unsigned int v9; // r14d
  _QWORD **v10; // rbx
  _QWORD *v11; // rbx
  __int64 **v12; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  void **v18; // rbx
  _QWORD *v19; // r15
  void *v20; // rcx
  _QWORD v22[5]; // [rsp+20h] [rbp-28h] BYREF

  v4 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v6 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    v7 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v8 = operator new(0x28u);
      *v8 = v8;
      v8[1] = v8;
      v8[2] = v8;
      *((_WORD *)v8 + 12) = 257;
      *v7 = v8;
    }
    else
    {
      v7 = 0;
    }
    *((_QWORD *)v5 + 1) = v7;
    if ( v7 )
    {
      v9 = 0;
      v10 = *(_QWORD ***)(a2 + 40);
      if ( v10 )
      {
        v11 = (_QWORD *)**v10;
        while ( v11 != **(_QWORD ***)(a2 + 40) )
        {
          std::_Tree<std::_Tset_traits<std::wstring *,std::less<std::wstring *>,std::allocator<std::wstring *>,0>>::emplace<std::wstring * const &>(
            *((__int64 **)v5 + 1),
            (__int64)v22,
            v11 + 4);
          v12 = (__int64 **)v11[2];
          if ( *((_BYTE *)v12 + 25) )
          {
            for ( i = v11[1]; !*(_BYTE *)(i + 25) && v11 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
              v11 = (_QWORD *)i;
            v11 = (_QWORD *)i;
          }
          else
          {
            v11 = (_QWORD *)v11[2];
            for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v11 = j;
          }
        }
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        *(_QWORD *)v5 = *(_QWORD *)(a2 + 32);
        *((_QWORD *)v5 + 2) = *(_QWORD *)a2;
        *((_DWORD *)v5 + 6) = *(_DWORD *)(a2 + 8);
        *((_QWORD *)v5 + 4) = *(_QWORD *)(a2 + 16);
        *((_DWORD *)v5 + 10) = *(_DWORD *)(a2 + 24);
        *((_DWORD *)v5 + 11) = *(_DWORD *)(a2 + 72);
        if ( a1[1] == 0xAAAAAAAAAAAAAAALL )
          std::_Xlength_error("list too long");
        v15 = *a1;
        v22[0] = a1;
        v22[1] = 0;
        v16 = operator new(0x18u);
        v16[2] = v5;
        ++a1[1];
        v17 = *(_QWORD **)(v15 + 8);
        *v16 = v15;
        v16[1] = v17;
        *(_QWORD *)(v15 + 8) = v16;
        *v17 = v16;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v9 = -2147024882;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140005D7A);
        }
      }
    }
    else
    {
      v9 = -2147024882;
      v18 = (void **)*((_QWORD *)v5 + 1);
      if ( v18 )
      {
        v19 = (_QWORD *)*((_QWORD *)*v18 + 1);
        while ( !*((_BYTE *)v19 + 25) )
        {
          std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(
            (__int64)v18,
            (__int64)v18,
            v19[2]);
          v20 = v19;
          v19 = (_QWORD *)*v19;
          operator delete(v20, (const struct std::nothrow_t *)0x28);
        }
        operator delete(*v18, (const struct std::nothrow_t *)0x28);
        operator delete(v18, (const struct std::nothrow_t *)0x10);
      }
      operator delete(v5, (const struct std::nothrow_t *)0x30);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x140005bd0  mov     [rsp+arg_0], rbx
0x140005bd5  mov     [rsp+arg_8], rsi
0x140005bda  push    r12
0x140005bdc  push    r14
0x140005bde  push    r15
0x140005be0  sub     rsp, 30h
0x140005be4  mov     r15, rdx
0x140005be7  mov     r12, rcx
0x140005bea  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005bf1  mov     ecx, 30h ; '0'; unsigned __int64
0x140005bf6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005bfb  mov     rsi, rax
0x140005bfe  test    rax, rax
0x140005c01  jz      loc_140005DEA
0x140005c07  xorps   xmm0, xmm0
0x140005c0a  movups  xmmword ptr [rax], xmm0
0x140005c0d  movups  xmmword ptr [rax+10h], xmm0
0x140005c11  movups  xmmword ptr [rax+20h], xmm0
0x140005c15  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140005c1c  mov     ecx, 10h; unsigned __int64
0x140005c21  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140005c26  mov     rbx, rax
0x140005c29  mov     [rsp+48h+arg_10], rax
0x140005c2e  test    rax, rax
0x140005c31  jz      short loc_140005C62
0x140005c33  mov     qword ptr [rax], 0
0x140005c3a  mov     qword ptr [rax+8], 0
0x140005c42  mov     ecx, 28h ; '('; Size
0x140005c47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005c4c  mov     [rax], rax
0x140005c4f  mov     [rax+8], rax
0x140005c53  mov     [rax+10h], rax
0x140005c57  mov     word ptr [rax+18h], 101h
0x140005c5d  mov     [rbx], rax
0x140005c60  jmp     short loc_140005C64
0x140005c62  xor     ebx, ebx
0x140005c64  mov     [rsi+8], rbx
0x140005c68  test    rbx, rbx
0x140005c6b  jnz     short loc_140005C78
0x140005c6d  mov     r14d, 8007000Eh
0x140005c73  jmp     loc_140005D89
0x140005c78  xor     r14d, r14d
0x140005c7b  mov     rbx, [r15+28h]
0x140005c7f  mov     [rsp+48h+arg_18], rsi
0x140005c84  test    rbx, rbx
0x140005c87  jz      short loc_140005CEF
0x140005c89  mov     rbx, [rbx]
0x140005c8c  mov     rbx, [rbx]
0x140005c8f  mov     rax, [r15+28h]
0x140005c93  cmp     rbx, [rax]
0x140005c96  jz      short loc_140005CEF
0x140005c98  lea     r8, [rbx+20h]
0x140005c9c  lea     rdx, [rsp+48h+var_28]
0x140005ca1  mov     rcx, [rsi+8]
0x140005ca5  call    ??$emplace@AEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBQEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring *,std::less<std::wstring *>,std::allocator<std::wstring *>,0>>::emplace<std::wstring * const &>(std::wstring * const &)
0x140005caa  mov     rcx, [rbx+10h]
0x140005cae  cmp     [rcx+19h], r14b
0x140005cb2  jz      short loc_140005CD2
0x140005cb4  mov     rax, [rbx+8]
0x140005cb8  jmp     short loc_140005CC7
0x140005cba  cmp     rbx, [rax+10h]
0x140005cbe  jnz     short loc_140005CCD
0x140005cc0  mov     rbx, rax
0x140005cc3  mov     rax, [rax+8]
0x140005cc7  cmp     [rax+19h], r14b
0x140005ccb  jz      short loc_140005CBA
0x140005ccd  mov     rbx, rax
0x140005cd0  jmp     short loc_140005C8F
0x140005cd2  mov     rbx, rcx
0x140005cd5  mov     rcx, [rcx]
0x140005cd8  cmp     [rcx+19h], r14b
0x140005cdc  jnz     short loc_140005C8F
0x140005cde  mov     rbx, rcx
0x140005ce1  mov     rax, [rcx]
0x140005ce4  mov     rcx, rax
0x140005ce7  cmp     [rax+19h], r14b
0x140005ceb  jz      short loc_140005CDE
0x140005ced  jmp     short loc_140005C8F
0x140005cef  mov     rax, [r15+20h]
0x140005cf3  mov     [rsi], rax
0x140005cf6  mov     rax, [r15]
0x140005cf9  mov     [rsi+10h], rax
0x140005cfd  mov     eax, [r15+8]
0x140005d01  mov     [rsi+18h], eax
0x140005d04  mov     rax, [r15+10h]
0x140005d08  mov     [rsi+20h], rax
0x140005d0c  mov     eax, [r15+18h]
0x140005d10  mov     [rsi+28h], eax
0x140005d13  mov     eax, [r15+48h]
0x140005d17  mov     [rsi+2Ch], eax
0x140005d1a  mov     rax, 0AAAAAAAAAAAAAAAh
0x140005d24  cmp     [r12+8], rax
0x140005d29  jnz     short loc_140005D38
0x140005d2b  lea     rcx, aListTooLong; "list too long"
0x140005d32  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140005d38  mov     rbx, [r12]
0x140005d3c  mov     [rsp+48h+var_28], r12
0x140005d41  mov     [rsp+48h+var_20], 0
0x140005d4a  mov     ecx, 18h; Size
0x140005d4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005d54  mov     [rax+10h], rsi
0x140005d58  inc     qword ptr [r12+8]
0x140005d5d  mov     rcx, [rbx+8]
0x140005d61  mov     [rax], rbx
0x140005d64  mov     [rax+8], rcx
0x140005d68  mov     [rbx+8], rax
0x140005d6c  mov     [rcx], rax
0x140005d6f  mov     [rsp+48h+arg_18], 0
0x140005d78  jmp     short loc_140005DF0
0x140005d7a  mov     rsi, [rsp+48h+arg_18]
0x140005d7f  mov     r14d, dword ptr [rsp+48h+arg_10]
0x140005d84  test    rsi, rsi
0x140005d87  jz      short loc_140005DF0
0x140005d89  mov     rbx, [rsi+8]
0x140005d8d  test    rbx, rbx
0x140005d90  jz      short loc_140005DDB
0x140005d92  mov     rax, [rbx]
0x140005d95  mov     r15, [rax+8]
0x140005d99  jmp     short loc_140005DBA
0x140005d9b  mov     r8, [r15+10h]
0x140005d9f  mov     rdx, rbx
0x140005da2  mov     rcx, rbx
0x140005da5  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring *,void *>>>(std::allocator<std::_Tree_node<std::wstring *,void *>> &,std::_Tree_node<std::wstring *,void *> *)
0x140005daa  mov     rcx, r15; void *
0x140005dad  mov     r15, [r15]
0x140005db0  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140005db5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005dba  cmp     byte ptr [r15+19h], 0
0x140005dbf  jz      short loc_140005D9B
0x140005dc1  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140005dc6  mov     rcx, [rbx]; void *
0x140005dc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005dce  mov     edx, 10h; struct std::nothrow_t *
0x140005dd3  mov     rcx, rbx; void *
0x140005dd6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005ddb  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x140005de0  mov     rcx, rsi; void *
0x140005de3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140005de8  jmp     short loc_140005DF0
0x140005dea  mov     r14d, 8007000Eh
0x140005df0  mov     eax, r14d
0x140005df3  mov     rbx, [rsp+48h+arg_0]
0x140005df8  mov     rsi, [rsp+48h+arg_8]
0x140005dfd  add     rsp, 30h
0x140005e01  pop     r15
0x140005e03  pop     r14
0x140005e05  pop     r12
0x140005e07  retn
```
