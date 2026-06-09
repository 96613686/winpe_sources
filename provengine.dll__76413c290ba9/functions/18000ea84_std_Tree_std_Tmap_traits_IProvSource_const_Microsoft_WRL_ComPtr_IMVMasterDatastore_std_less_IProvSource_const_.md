# std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_nohint<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(bool,std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)

- ea: `0x18000ea84`
- end: `0x18000ebd2`
- name: `??$_Insert_nohint@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, unsigned __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e04c`

## callees

- `0x18000d20c`
- `0x18000ea84`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ebb1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ebb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_nohint<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 *a4,
        _QWORD *a5)
{
  _QWORD *v8; // rdx
  __int64 *v9; // rax
  unsigned __int64 v10; // r8
  _QWORD *v11; // r9
  char v12; // cl
  _QWORD *v13; // rbx
  __int64 v14; // rcx
  __int64 result; // rax
  __int64 j; // rax
  __int64 i; // rax
  void *v18; // rsi
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-18h]
  __int64 v21; // [rsp+40h] [rbp+8h] BYREF

  v8 = (_QWORD *)*a1;
  v9 = *(__int64 **)(*a1 + 8LL);
  if ( *((_BYTE *)v9 + 25) )
  {
    v12 = 1;
    v11 = v8;
  }
  else
  {
    v10 = *a4;
    do
    {
      v11 = v9;
      v12 = v10 < v9[4];
      if ( v10 >= v9[4] )
        v9 = (__int64 *)v9[2];
      else
        v9 = (__int64 *)*v9;
    }
    while ( !*((_BYTE *)v9 + 25) );
  }
  try
  {
    v13 = v11;
    if ( v12 )
    {
      if ( v11 == (_QWORD *)*v8 )
      {
        *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(
                           a1,
                           &v21,
                           1,
                           v11,
                           v20,
                           (__int64)a5);
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
      if ( *((_BYTE *)v11 + 25) )
      {
        v13 = (_QWORD *)v11[2];
      }
      else if ( *(_BYTE *)(*v11 + 25LL) )
      {
        for ( i = v11[1]; !*(_BYTE *)(i + 25) && v13 == *(_QWORD **)i; i = *(_QWORD *)(i + 8) )
          v13 = (_QWORD *)i;
        if ( !*((_BYTE *)v13 + 25) )
          v13 = (_QWORD *)i;
      }
      else
      {
        v13 = (_QWORD *)*v11;
        for ( j = *(_QWORD *)(*v11 + 16LL); !*(_BYTE *)(j + 25); j = v13[2] )
          v13 = (_QWORD *)v13[2];
      }
    }
    if ( v13[4] >= *a4 )
    {
      v18 = a5;
      v19 = a5[5];
      if ( v19 )
      {
        a5[5] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      operator delete(v18);
      *(_QWORD *)a2 = v13;
      *(_BYTE *)(a2 + 8) = 0;
      result = a2;
    }
    else
    {
      *(_QWORD *)a2 = *std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(
                         a1,
                         &v21,
                         v12,
                         v11,
                         v20,
                         (__int64)a5);
      *(_BYTE *)(a2 + 8) = 1;
      result = a2;
    }
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Destroy_if_not_nil(
      v14,
      a5);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000ea84  mov     [rsp+arg_8], rbx
0x18000ea89  mov     [rsp+arg_10], rsi
0x18000ea8e  push    rdi
0x18000ea8f  sub     rsp, 30h
0x18000ea93  mov     r11, r9
0x18000ea96  mov     rdi, rdx
0x18000ea99  mov     r10, rcx
0x18000ea9c  mov     rdx, [rcx]
0x18000ea9f  mov     rax, [rdx+8]
0x18000eaa3  cmp     byte ptr [rax+19h], 0
0x18000eaa7  jnz     short loc_18000EAC9
0x18000eaa9  mov     r8, [r9]
0x18000eaac  mov     r9, rax
0x18000eaaf  cmp     r8, [rax+20h]
0x18000eab3  setb    cl
0x18000eab6  jnb     short loc_18000EABD
0x18000eab8  mov     rax, [rax]
0x18000eabb  jmp     short loc_18000EAC1
0x18000eabd  mov     rax, [rax+10h]
0x18000eac1  cmp     byte ptr [rax+19h], 0
0x18000eac5  jz      short loc_18000EAAC
0x18000eac7  jmp     short loc_18000EACE
0x18000eac9  mov     cl, 1
0x18000eacb  mov     r9, rdx
0x18000eace  mov     rbx, r9
0x18000ead1  test    cl, cl
0x18000ead3  jz      loc_18000EB59
0x18000ead9  cmp     r9, [rdx]
0x18000eadc  jnz     short loc_18000EB0A
0x18000eade  mov     rax, [rsp+38h+arg_20]
0x18000eae3  mov     [rsp+38h+var_10], rax
0x18000eae8  mov     r8b, 1
0x18000eaeb  lea     rdx, [rsp+38h+arg_0]
0x18000eaf0  mov     rcx, r10
0x18000eaf3  call    ??$_Insert_at@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(bool,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *,std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)
0x18000eaf8  mov     rax, [rax]
0x18000eafb  mov     [rdi], rax
0x18000eafe  mov     byte ptr [rdi+8], 1
0x18000eb02  mov     rax, rdi
0x18000eb05  jmp     loc_18000EBC1
0x18000eb0a  cmp     byte ptr [r9+19h], 0
0x18000eb0f  jz      short loc_18000EB17
0x18000eb11  mov     rbx, [r9+10h]
0x18000eb15  jmp     short loc_18000EB59
0x18000eb17  mov     rax, [r9]
0x18000eb1a  cmp     byte ptr [rax+19h], 0
0x18000eb1e  jnz     short loc_18000EB39
0x18000eb20  mov     rbx, rax
0x18000eb23  mov     rax, [rax+10h]
0x18000eb27  jmp     short loc_18000EB31
0x18000eb29  mov     rbx, [rbx+10h]
0x18000eb2d  mov     rax, [rbx+10h]
0x18000eb31  cmp     byte ptr [rax+19h], 0
0x18000eb35  jz      short loc_18000EB29
0x18000eb37  jmp     short loc_18000EB59
0x18000eb39  mov     rax, [r9+8]
0x18000eb3d  jmp     short loc_18000EB4B
0x18000eb3f  cmp     rbx, [rax]
0x18000eb42  jnz     short loc_18000EB51
0x18000eb44  mov     rbx, rax
0x18000eb47  mov     rax, [rax+8]
0x18000eb4b  cmp     byte ptr [rax+19h], 0
0x18000eb4f  jz      short loc_18000EB3F
0x18000eb51  cmp     byte ptr [rbx+19h], 0
0x18000eb55  cmovz   rbx, rax
0x18000eb59  mov     rax, [r11]
0x18000eb5c  cmp     [rbx+20h], rax
0x18000eb60  jnb     short loc_18000EB8B
0x18000eb62  mov     rax, [rsp+38h+arg_20]
0x18000eb67  mov     [rsp+38h+var_10], rax
0x18000eb6c  mov     r8b, cl
0x18000eb6f  lea     rdx, [rsp+38h+arg_0]
0x18000eb74  mov     rcx, r10
0x18000eb77  call    ??$_Insert_at@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@U?$less@PEBUIProvSource@@@std@@V?$allocator@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@std@@PEAX@1@AEAU?$pair@QEBUIProvSource@@V?$ComPtr@UIMVMasterDatastore@@@WRL@Microsoft@@@1@1@Z; std::_Tree<std::_Tmap_traits<IProvSource const *,Microsoft::WRL::ComPtr<IMVMasterDatastore>,std::less<IProvSource const *>,std::allocator<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>>,0>>::_Insert_at<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *>(bool,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *,std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>> &,std::_Tree_node<std::pair<IProvSource const * const,Microsoft::WRL::ComPtr<IMVMasterDatastore>>,void *> *)
0x18000eb7c  mov     rax, [rax]
0x18000eb7f  mov     [rdi], rax
0x18000eb82  mov     byte ptr [rdi+8], 1
0x18000eb86  mov     rax, rdi
0x18000eb89  jmp     short loc_18000EBC1
0x18000eb8b  mov     rsi, [rsp+38h+arg_20]
0x18000eb90  mov     rcx, [rsi+28h]
0x18000eb94  test    rcx, rcx
0x18000eb97  jz      short loc_18000EBAE
0x18000eb99  mov     qword ptr [rsi+28h], 0
0x18000eba1  mov     rax, [rcx]
0x18000eba4  mov     rax, [rax+10h]
0x18000eba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebad  nop
0x18000ebae  mov     rcx, rsi
0x18000ebb1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ebb7  mov     [rdi], rbx
0x18000ebba  mov     byte ptr [rdi+8], 0
0x18000ebbe  mov     rax, rdi
0x18000ebc1  mov     rbx, [rsp+38h+arg_8]
0x18000ebc6  mov     rsi, [rsp+38h+arg_10]
0x18000ebcb  add     rsp, 30h
0x18000ebcf  pop     rdi
0x18000ebd0  retn
```
