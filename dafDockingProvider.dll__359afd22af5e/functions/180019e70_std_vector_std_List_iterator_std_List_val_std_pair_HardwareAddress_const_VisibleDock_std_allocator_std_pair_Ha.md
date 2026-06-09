# std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>>>>,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>> const &)

- ea: `0x180019e70`
- end: `0x18001a096`
- name: `?_Insert_n@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@@2@_KAEBV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z`
- size: `550`
- prototype: `void __fastcall(__int64, char *, unsigned __int64, __int64 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800180ec`
- `0x18001884c`
- `0x180019be0`

## callees

- `0x180001484`
- `0x1800014d0`
- `0x1800020bd`
- `0x18001117c`
- `0x1800131f4`
- `0x1800180a0`
- `0x1800180c4`
- `0x180019e70`

## pseudocode

```c
void __fastcall std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Insert_n(
        __int64 a1,
        char *a2,
        unsigned __int64 a3,
        __int64 *a4)
{
  char *v8; // r15
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r12
  _QWORD *v13; // rbx
  __int64 v14; // r15
  __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  unsigned __int64 v17; // rbx
  __int64 v18; // r12
  char *v19; // rdx
  unsigned __int64 v20; // rcx
  char *v21; // r14
  unsigned __int64 v22; // rcx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v24; // [rsp+90h] [rbp+18h] BYREF

  if ( a3 )
  {
    v8 = *(char **)(a1 + 8);
    v9 = (__int64)&v8[-*(_QWORD *)a1] >> 3;
    if ( 0x1FFFFFFFFFFFFFFFLL - v9 < a3 )
      std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Xlen();
    v10 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
    v11 = v9 + a3;
    if ( v10 >= v11 )
    {
      v17 = *a4;
      v18 = 8 * a3;
      if ( (v8 - a2) >> 3 >= a3 )
      {
        v21 = &v8[-v18];
        *(_QWORD *)(a1 + 8) = std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
                                &v8[-v18],
                                v8,
                                v8);
        while ( v21 != a2 )
        {
          v21 -= 8;
          v8 -= 8;
          *(_QWORD *)v8 = *(_QWORD *)v21;
        }
        v19 = &a2[v18];
        v20 = v18 + 7;
      }
      else
      {
        v24 = (_QWORD *)*a4;
        std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
          a2,
          v8,
          &a2[v18]);
        try
        {
          std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
            *(__int64 **)(a1 + 8),
            a3 - ((__int64)(*(_QWORD *)(a1 + 8) - (_QWORD)a2) >> 3),
            (__int64 *)&v24);
        }
        catch ( ... )
        {
          throw;
        }
        v19 = *(char **)(a1 + 8);
        *(_QWORD *)(a1 + 8) = &v19[v18];
        v20 = v19 - a2 + 7;
      }
      v22 = v20 >> 3;
      if ( a2 > v19 )
        v22 = 0;
      if ( v22 )
        memset64(a2, v17, v22);
    }
    else
    {
      v12 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) >= v10 )
        v12 = v10 + (v10 >> 1);
      if ( v12 < v11 )
        v12 = v11;
      v13 = 0;
      v24 = 0;
      if ( v12 )
      {
        if ( v12 > 0x1FFFFFFFFFFFFFFFLL || (v13 = operator new(8 * v12), (v24 = v13) == 0) )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const char *)v10);
          throw (std::bad_alloc *)pExceptionObject;
        }
      }
      v14 = (__int64)&a2[-*(_QWORD *)a1] >> 3;
      try
      {
        std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
          &v13[v14],
          a3,
          a4);
        std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
          *(_QWORD **)a1,
          a2,
          v13);
        std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(
          a2,
          *(_QWORD **)(a1 + 8),
          &v13[v14 + a3]);
      }
      catch ( ... )
      {
        std::allocator<Dock>::deallocate(v15, v24);
        throw;
      }
      v16 = a3 + ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
      if ( *(_QWORD *)a1 )
        operator delete(*(void **)a1);
      *(_QWORD *)(a1 + 16) = &v13[v12];
      *(_QWORD *)(a1 + 8) = &v13[v16];
      *(_QWORD *)a1 = v13;
    }
  }
}

```

## disassembly

```asm
0x180019e70  test    r8, r8
0x180019e73  jz      locret_18001A073
0x180019e79  mov     [rsp+arg_0], rbx
0x180019e7e  mov     [rsp+arg_8], rsi
0x180019e83  push    rdi
0x180019e84  push    r12
0x180019e86  push    r13
0x180019e88  push    r14
0x180019e8a  push    r15
0x180019e8c  sub     rsp, 50h
0x180019e90  mov     r13, r9
0x180019e93  mov     r14, r8
0x180019e96  mov     rdi, rdx
0x180019e99  mov     rsi, rcx
0x180019e9c  mov     r15, [rcx+8]
0x180019ea0  mov     rcx, r15
0x180019ea3  sub     rcx, [rsi]
0x180019ea6  sar     rcx, 3
0x180019eaa  mov     r9, 1FFFFFFFFFFFFFFFh
0x180019eb4  mov     rax, r9
0x180019eb7  sub     rax, rcx
0x180019eba  cmp     rax, r8
0x180019ebd  jb      loc_18001A074
0x180019ec3  mov     rdx, [rsi+10h]
0x180019ec7  sub     rdx, [rsi]
0x180019eca  sar     rdx, 3; char *
0x180019ece  add     r8, rcx
0x180019ed1  cmp     rdx, r8
0x180019ed4  jnb     loc_180019FA2
0x180019eda  mov     rax, rdx
0x180019edd  shr     rax, 1
0x180019ee0  mov     rcx, r9
0x180019ee3  sub     rcx, rax
0x180019ee6  add     rax, rdx
0x180019ee9  xor     r12d, r12d
0x180019eec  cmp     rcx, rdx
0x180019eef  cmovnb  r12, rax
0x180019ef3  cmp     r12, r8
0x180019ef6  cmovb   r12, r8
0x180019efa  xor     ebx, ebx
0x180019efc  mov     [rsp+78h+arg_10], rbx
0x180019f04  test    r12, r12
0x180019f07  jz      short loc_180019F33
0x180019f09  cmp     r12, r9
0x180019f0c  ja      loc_18001A07A
0x180019f12  lea     rcx, ds:0[r12*8]; Size
0x180019f1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019f1f  mov     rbx, rax
0x180019f22  mov     [rsp+78h+arg_10], rax
0x180019f2a  test    rax, rax
0x180019f2d  jz      loc_18001A07A
0x180019f33  mov     r15, rdi
0x180019f36  sub     r15, [rsi]
0x180019f39  sar     r15, 3
0x180019f3d  lea     rcx, [rbx+r15*8]
0x180019f41  mov     r8, r13
0x180019f44  mov     rdx, r14
0x180019f47  call    ??$_Uninit_fill_n@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_KV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAXPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@_KPEBV10@AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> const *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x180019f4c  mov     r8, rbx
0x180019f4f  mov     rdx, rdi
0x180019f52  mov     rcx, [rsi]
0x180019f55  call    ??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x180019f5a  lea     rax, [r15+r14]
0x180019f5e  lea     r8, [rbx+rax*8]
0x180019f62  mov     rdx, [rsi+8]
0x180019f66  mov     rcx, rdi
0x180019f69  call    ??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x180019f6e  nop
0x180019f6f  mov     rcx, [rsi]; Block
0x180019f72  mov     rdi, [rsi+8]
0x180019f76  sub     rdi, rcx
0x180019f79  sar     rdi, 3
0x180019f7d  add     rdi, r14
0x180019f80  test    rcx, rcx
0x180019f83  jz      short loc_180019F8A
0x180019f85  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019f8a  lea     rax, [rbx+r12*8]
0x180019f8e  mov     [rsi+10h], rax
0x180019f92  lea     rax, [rbx+rdi*8]
0x180019f96  mov     [rsi+8], rax
0x180019f9a  mov     [rsi], rbx
0x180019f9d  jmp     loc_18001A05A
0x180019fa2  mov     rbx, [r13+0]
0x180019fa6  lea     r12, ds:0[r14*8]
0x180019fae  mov     rax, r15
0x180019fb1  sub     rax, rdi
0x180019fb4  sar     rax, 3
0x180019fb8  mov     rdx, r15
0x180019fbb  cmp     rax, r14
0x180019fbe  jnb     short loc_18001A00F
0x180019fc0  mov     [rsp+78h+arg_10], rbx
0x180019fc8  lea     r8, [r12+rdi]
0x180019fcc  mov     rcx, rdi
0x180019fcf  call    ??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x180019fd4  nop
0x180019fd5  mov     rcx, [rsi+8]
0x180019fd9  mov     rax, rcx
0x180019fdc  sub     rax, rdi
0x180019fdf  sar     rax, 3
0x180019fe3  sub     r14, rax
0x180019fe6  lea     r8, [rsp+78h+arg_10]
0x180019fee  mov     rdx, r14
0x180019ff1  call    ??$_Uninit_fill_n@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_KV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAXPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@_KPEBV10@AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_fill_n<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> const *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x180019ff6  nop
0x180019ff7  mov     rdx, [rsi+8]
0x180019ffb  lea     rax, [r12+rdx]
0x180019fff  mov     [rsi+8], rax
0x18001a003  mov     rcx, rdx
0x18001a006  sub     rcx, rdi
0x18001a009  add     rcx, 7
0x18001a00d  jmp     short loc_18001A042
0x18001a00f  mov     r14, r15
0x18001a012  sub     r14, r12
0x18001a015  mov     r8, r15
0x18001a018  mov     rcx, r14
0x18001a01b  call    ??$_Uninit_move@PEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@PEAV12@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@0@PEAV10@00AEAV?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>(std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::allocator<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>> &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> *,std::_Nonscalar_ptr_iterator_tag)
0x18001a020  mov     [rsi+8], rax
0x18001a024  jmp     short loc_18001A034
0x18001a026  sub     r14, 8
0x18001a02a  lea     r15, [r15-8]
0x18001a02e  mov     rax, [r14]
0x18001a031  mov     [r15], rax
0x18001a034  cmp     r14, rdi
0x18001a037  jnz     short loc_18001A026
0x18001a039  lea     rdx, [r12+rdi]
0x18001a03d  lea     rcx, [r12+7]
0x18001a042  shr     rcx, 3
0x18001a046  xor     eax, eax
0x18001a048  cmp     rdi, rdx
0x18001a04b  cmova   rcx, rax
0x18001a04f  test    rcx, rcx
0x18001a052  jz      short loc_18001A05A
0x18001a054  mov     rax, rbx
0x18001a057  rep stosq
0x18001a05a  lea     r11, [rsp+78h+var_28]
0x18001a05f  mov     rbx, [r11+30h]
0x18001a063  mov     rsi, [r11+38h]
0x18001a067  mov     rsp, r11
0x18001a06a  pop     r15
0x18001a06c  pop     r14
0x18001a06e  pop     r13
0x18001a070  pop     r12
0x18001a072  pop     rdi
0x18001a073  retn
0x18001a074  call    ?_Xlen@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEBAXXZ; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Xlen(void)
0x18001a07a  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18001a07f  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18001a084  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001a08b  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001a090  call    _CxxThrowException_0
```
