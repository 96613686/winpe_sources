# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)

- ea: `0x180025ee8`
- end: `0x18002605c`
- name: `??$_Insert_nohint@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, const wchar_t **, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800256c0`
- `0x18002eb90`

## callees

- `0x180025c68`
- `0x180025ee8`
- `0x18003f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025f17`
- `msvcrt!_wcsicmp` at `0x180025fdb`
- `msvcrt!_wcsicmp` at `0x180025f17`
- `msvcrt!_wcsicmp` at `0x180025fdb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002603d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002603d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        const wchar_t **a4,
        _QWORD *a5)
{
  __int64 *v8; // rbx
  __int64 *v9; // rsi
  int v10; // eax
  unsigned int v11; // r14d
  __int64 *v12; // rsi
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 *i; // rax
  void *v17; // rsi
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-48h]
  __int64 v20; // [rsp+70h] [rbp+8h] BYREF

  try
  {
    v8 = *a1;
    v9 = (__int64 *)(*a1)[1];
    if ( *((_BYTE *)v9 + 25) )
    {
      LOBYTE(v11) = 1;
      v12 = *a1;
    }
    else
    {
      do
      {
        v8 = v9;
        v10 = _wcsicmp(*a4, (const wchar_t *)v9[4]);
        v11 = (unsigned int)v10 >> 31;
        if ( v10 >= 0 )
          v9 = (__int64 *)v9[2];
        else
          v9 = (__int64 *)*v9;
      }
      while ( !*((_BYTE *)v9 + 25) );
      v12 = v8;
      if ( v10 >= 0 )
      {
LABEL_25:
        if ( _wcsicmp((const wchar_t *)v8[4], *a4) >= 0 )
        {
          v17 = a5;
          v18 = a5[5];
          if ( v18 )
          {
            a5[5] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          }
          operator delete(v17);
          *(_QWORD *)a2 = v8;
          *(_BYTE *)(a2 + 8) = 0;
          return a2;
        }
        else
        {
          *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
                             a1,
                             &v20,
                             v11,
                             v12,
                             v19,
                             (__int64)a5);
          *(_BYTE *)(a2 + 8) = 1;
          return a2;
        }
      }
    }
    if ( v12 == (__int64 *)**a1 )
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
                         a1,
                         &v20,
                         1,
                         v12,
                         v19,
                         (__int64)a5);
      *(_BYTE *)(a2 + 8) = 1;
      return a2;
    }
    if ( *((_BYTE *)v12 + 25) )
    {
      v8 = (__int64 *)v12[2];
    }
    else if ( *(_BYTE *)(*v12 + 25) )
    {
      for ( i = (__int64 *)v12[1]; !*((_BYTE *)i + 25) && v8 == (__int64 *)*i; i = (__int64 *)i[1] )
        v8 = i;
      if ( !*((_BYTE *)v8 + 25) )
        v8 = i;
    }
    else
    {
      v8 = (__int64 *)*v12;
      for ( j = *(_QWORD *)(*v12 + 16); !*(_BYTE *)(j + 25); j = v8[2] )
        v8 = (__int64 *)v8[2];
    }
    goto LABEL_25;
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Destroy_if_not_nil(
      v13,
      a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180025ee8  push    rbx
0x180025eea  push    rsi
0x180025eeb  push    rdi
0x180025eec  push    r12
0x180025eee  push    r14
0x180025ef0  push    r15
0x180025ef2  sub     rsp, 38h
0x180025ef6  mov     r12, r9
0x180025ef9  mov     rdi, rdx
0x180025efc  mov     r15, rcx
0x180025eff  mov     rbx, [rcx]
0x180025f02  mov     rsi, [rbx+8]
0x180025f06  cmp     byte ptr [rsi+19h], 0
0x180025f0a  jnz     short loc_180025F45
0x180025f0c  mov     rbx, rsi
0x180025f0f  mov     rdx, [rsi+20h]; String2
0x180025f13  mov     rcx, [r12]; String1
0x180025f17  call    cs:__imp__wcsicmp
0x180025f1d  mov     r14d, eax
0x180025f20  shr     r14d, 1Fh
0x180025f24  test    r14b, r14b
0x180025f27  jz      short loc_180025F2E
0x180025f29  mov     rsi, [rsi]
0x180025f2c  jmp     short loc_180025F32
0x180025f2e  mov     rsi, [rsi+10h]
0x180025f32  cmp     byte ptr [rsi+19h], 0
0x180025f36  jz      short loc_180025F0C
0x180025f38  mov     rsi, rbx
0x180025f3b  test    r14b, r14b
0x180025f3e  jnz     short loc_180025F4B
0x180025f40  jmp     loc_180025FD3
0x180025f45  mov     r14b, 1
0x180025f48  mov     rsi, rbx
0x180025f4b  mov     rax, [r15]
0x180025f4e  cmp     rsi, [rax]
0x180025f51  jnz     short loc_180025F85
0x180025f53  mov     rax, [rsp+68h+arg_20]
0x180025f5b  mov     [rsp+68h+var_40], rax
0x180025f60  mov     r9, rsi
0x180025f63  mov     r8b, 1
0x180025f66  lea     rdx, [rsp+68h+arg_0]
0x180025f6b  mov     rcx, r15
0x180025f6e  call    ??$_Insert_at@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x180025f73  mov     rax, [rax]
0x180025f76  mov     [rdi], rax
0x180025f79  mov     byte ptr [rdi+8], 1
0x180025f7d  mov     rax, rdi
0x180025f80  jmp     loc_18002604D
0x180025f85  cmp     byte ptr [rsi+19h], 0
0x180025f89  jz      short loc_180025F91
0x180025f8b  mov     rbx, [rsi+10h]
0x180025f8f  jmp     short loc_180025FD3
0x180025f91  mov     rax, [rsi]
0x180025f94  cmp     byte ptr [rax+19h], 0
0x180025f98  jnz     short loc_180025FB3
0x180025f9a  mov     rbx, rax
0x180025f9d  mov     rax, [rax+10h]
0x180025fa1  jmp     short loc_180025FAB
0x180025fa3  mov     rbx, [rbx+10h]
0x180025fa7  mov     rax, [rbx+10h]
0x180025fab  cmp     byte ptr [rax+19h], 0
0x180025faf  jz      short loc_180025FA3
0x180025fb1  jmp     short loc_180025FD3
0x180025fb3  mov     rax, [rsi+8]
0x180025fb7  jmp     short loc_180025FC5
0x180025fb9  cmp     rbx, [rax]
0x180025fbc  jnz     short loc_180025FCB
0x180025fbe  mov     rbx, rax
0x180025fc1  mov     rax, [rax+8]
0x180025fc5  cmp     byte ptr [rax+19h], 0
0x180025fc9  jz      short loc_180025FB9
0x180025fcb  cmp     byte ptr [rbx+19h], 0
0x180025fcf  cmovz   rbx, rax
0x180025fd3  mov     rdx, [r12]; String2
0x180025fd7  mov     rcx, [rbx+20h]; String1
0x180025fdb  call    cs:__imp__wcsicmp
0x180025fe1  test    eax, eax
0x180025fe3  jns     short loc_180026014
0x180025fe5  mov     rax, [rsp+68h+arg_20]
0x180025fed  mov     [rsp+68h+var_40], rax
0x180025ff2  mov     r9, rsi
0x180025ff5  mov     r8b, r14b
0x180025ff8  lea     rdx, [rsp+68h+arg_0]
0x180025ffd  mov     rcx, r15
0x180026000  call    ??$_Insert_at@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_at<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x180026005  mov     rax, [rax]
0x180026008  mov     [rdi], rax
0x18002600b  mov     byte ptr [rdi+8], 1
0x18002600f  mov     rax, rdi
0x180026012  jmp     short loc_18002604D
0x180026014  mov     rsi, [rsp+68h+arg_20]
0x18002601c  mov     rcx, [rsi+28h]
0x180026020  test    rcx, rcx
0x180026023  jz      short loc_18002603A
0x180026025  mov     qword ptr [rsi+28h], 0
0x18002602d  mov     rax, [rcx]
0x180026030  mov     rax, [rax+10h]
0x180026034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026039  nop
0x18002603a  mov     rcx, rsi
0x18002603d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026043  mov     [rdi], rbx
0x180026046  mov     byte ptr [rdi+8], 0
0x18002604a  mov     rax, rdi
0x18002604d  add     rsp, 38h
0x180026051  pop     r15
0x180026053  pop     r14
0x180026055  pop     r12
0x180026057  pop     rdi
0x180026058  pop     rsi
0x180026059  pop     rbx
0x18002605a  retn
```
