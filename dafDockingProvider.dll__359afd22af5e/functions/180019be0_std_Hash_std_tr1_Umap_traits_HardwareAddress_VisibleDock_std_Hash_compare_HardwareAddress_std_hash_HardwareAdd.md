# std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(std::pair<HardwareAddress const,VisibleDock> const &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>>>)

- ea: `0x180019be0`
- end: `0x180019e68`
- name: `?_Insert@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_N@2@AEBU?$pair@$$CBVHardwareAddress@@VVisibleDock@@@2@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z`
- size: `648`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018540`
- `0x180019be0`

## callees

- `0x1800014d0`
- `0x1800184f8`
- `0x180019be0`
- `0x180019e70`
- `0x18001a24c`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD **a4)
{
  int v8; // ecx
  unsigned __int64 v9; // rdx
  int v10; // eax
  unsigned __int64 v11; // r8
  __int64 *v12; // r14
  __int64 v13; // r8
  __int64 v14; // rdi
  _QWORD *v15; // rdx
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  _QWORD **v24; // rcx
  __int64 v25; // rdi
  __int64 v26; // rcx
  float v27; // xmm0_4
  __int64 v28; // rax
  float v29; // xmm1_4
  __int64 v30; // rcx
  int i; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // r14
  __int64 v36; // rdi
  _QWORD *iter; // rax
  _BYTE v38[56]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v40; // [rsp+70h] [rbp+18h] BYREF
  _QWORD **v41; // [rsp+78h] [rbp+20h]

  v41 = a4;
  v8 = 16807 * *(_DWORD *)a3 - 0x7FFFFFFF * (*(_DWORD *)a3 / 127773);
  v9 = *(_QWORD *)(a1 + 64);
  v10 = v8 + 0x7FFFFFFF;
  if ( v8 >= 0 )
    v10 = 16807 * *(_DWORD *)a3 - 0x7FFFFFFF * (*(_DWORD *)a3 / 127773);
  v11 = v9 & v10;
  if ( *(_QWORD *)(a1 + 72) <= v11 )
    v11 = v11 - (v9 >> 1) - 1;
  v12 = (__int64 *)(a1 + 32);
  v13 = 2 * v11;
  v14 = *(_QWORD *)(a1 + 32);
  v15 = *(_QWORD **)(v14 + 8 * v13);
  if ( v15 == *(_QWORD **)(a1 + 8) )
    v16 = *(_QWORD **)(a1 + 8);
  else
    v16 = **(_QWORD ***)(v14 + 8 * v13 + 8);
  while ( v16 != v15 )
  {
    v17 = v16[1];
    v16 = (_QWORD *)v17;
    if ( *(_DWORD *)(a3 + 8) == *(_DWORD *)(v17 + 24) && *(_WORD *)(a3 + 12) == *(_WORD *)(v17 + 28) )
    {
      if ( *(_DWORD *)(v17 + 24) == *(_DWORD *)(a3 + 8) && *(_WORD *)(v17 + 28) == *(_WORD *)(a3 + 12) )
      {
        if ( a4 != *(_QWORD ***)(a1 + 8) )
        {
          *a4[1] = *a4;
          (*a4)[1] = a4[1];
          VisibleDock::~VisibleDock((VisibleDock *)(a4 + 4));
          operator delete(a4);
          --*(_QWORD *)(a1 + 16);
        }
        *(_QWORD *)a2 = v16;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v16 = *(_QWORD **)v17;
      break;
    }
  }
  v19 = *a4;
  if ( v16 != *a4 )
  {
    *a4[1] = v19;
    *(_QWORD *)v19[1] = v16;
    *(_QWORD *)v16[1] = a4;
    v20 = (_QWORD *)v16[1];
    v16[1] = v19[1];
    v19[1] = a4[1];
    a4[1] = v20;
  }
  v21 = *v12;
  v22 = *(_QWORD **)(*v12 + 8 * v13);
  if ( v22 == *(_QWORD **)(a1 + 8) )
  {
    *(_QWORD *)(v21 + 8 * v13) = a4;
    *(_QWORD *)(*v12 + 8 * v13 + 8) = a4;
  }
  else if ( v22 == v16 )
  {
    *(_QWORD *)(v21 + 8 * v13) = a4;
  }
  else
  {
    v23 = *(_QWORD **)(v21 + 8 * v13 + 8);
    v24 = (_QWORD **)*v23;
    *(_QWORD *)(v21 + 8 * v13 + 8) = *v23;
    if ( v24 != a4 )
      *(_QWORD *)(*v12 + 8 * v13 + 8) = *(_QWORD *)(*(_QWORD *)(*v12 + 8 * v13 + 8) + 8LL);
  }
  v25 = *(_QWORD *)(a1 + 72);
  v26 = *(_QWORD *)(a1 + 16);
  if ( v26 < 0 )
  {
    v28 = *(_QWORD *)(a1 + 16) & 1LL | ((unsigned __int64)v26 >> 1);
    v27 = (float)(int)v28 + (float)(int)v28;
  }
  else
  {
    v27 = (float)(int)v26;
  }
  if ( v25 < 0 )
  {
    v30 = *(_QWORD *)(a1 + 72) & 1LL | ((unsigned __int64)v25 >> 1);
    v29 = (float)(int)v30 + (float)(int)v30;
  }
  else
  {
    v29 = (float)(int)v25;
  }
  if ( (float)(v27 / v29) > *(float *)(a1 + 80) )
  {
    for ( i = 0; i < 3; ++i )
    {
      if ( (unsigned __int64)v25 >= 0xFFFFFFFFFFFFFFFLL )
        break;
      v25 *= 2;
    }
    try
    {
      std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::reserve(
        a1 + 32,
        2 * v25);
      v40 = *(_QWORD *)(a1 + 8);
      v32 = *v12;
      if ( *(_QWORD *)(a1 + 32) != *(_QWORD *)(a1 + 40) )
        *(_QWORD *)(a1 + 40) = v32;
      std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Insert_n(
        a1 + 32,
        v32,
        2 * v25,
        &v40);
      *(_QWORD *)(a1 + 64) = v25 - 1;
      *(_QWORD *)(a1 + 72) = v25;
      v34 = *(_QWORD **)(a1 + 8);
      if ( (_QWORD *)*v34 != v34 )
      {
        v35 = v34[1];
        do
        {
          v36 = **(_QWORD **)(a1 + 8);
          std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(
            a1,
            v38,
            v36 + 16);
        }
        while ( v36 != v35 );
      }
    }
    catch ( ... )
    {
      iter = (_QWORD *)std::list<std::pair<HardwareAddress const,VisibleDock>>::_Make_iter(v33, &v40, v41);
      std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::erase(
        a1,
        v38,
        *iter);
      throw;
    }
  }
  *(_QWORD *)a2 = a4;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180019be0  mov     [rsp+arg_8], rbx
0x180019be5  mov     [rsp+arg_18], r9
0x180019bea  mov     [rsp+arg_0], rcx
0x180019bef  push    rsi
0x180019bf0  push    rdi
0x180019bf1  push    r12
0x180019bf3  push    r14
0x180019bf5  push    r15
0x180019bf7  sub     rsp, 30h
0x180019bfb  mov     rbx, r9
0x180019bfe  mov     r9, r8
0x180019c01  mov     r15, rdx
0x180019c04  mov     rsi, rcx
0x180019c07  mov     eax, 834E0B5Fh
0x180019c0c  imul    dword ptr [r8]
0x180019c0f  add     edx, [r8]
0x180019c12  sar     edx, 10h
0x180019c15  mov     eax, edx
0x180019c17  shr     eax, 1Fh
0x180019c1a  add     edx, eax
0x180019c1c  imul    ecx, [r8], 41A7h
0x180019c23  imul    eax, edx, 7FFFFFFFh
0x180019c29  sub     ecx, eax
0x180019c2b  mov     rdx, [rsi+40h]
0x180019c2f  lea     eax, [rcx+7FFFFFFFh]
0x180019c35  cmovns  eax, ecx
0x180019c38  movsxd  r8, eax
0x180019c3b  and     r8, rdx
0x180019c3e  cmp     [rsi+48h], r8
0x180019c42  ja      short loc_180019C4D
0x180019c44  shr     rdx, 1
0x180019c47  sub     r8, rdx
0x180019c4a  dec     r8
0x180019c4d  lea     r14, [rsi+20h]
0x180019c51  add     r8, r8
0x180019c54  mov     rdi, [r14]
0x180019c57  mov     rdx, [rdi+r8*8]
0x180019c5b  cmp     rdx, [rsi+8]
0x180019c5f  jnz     short loc_180019C67
0x180019c61  mov     rdi, [rsi+8]
0x180019c65  jmp     short loc_180019C6F
0x180019c67  mov     rdi, [rdi+r8*8+8]
0x180019c6c  mov     rdi, [rdi]
0x180019c6f  cmp     rdi, rdx
0x180019c72  jz      short loc_180019CF3
0x180019c74  mov     rcx, [rdi+8]
0x180019c78  mov     rdi, rcx
0x180019c7b  mov     eax, [r9+8]
0x180019c7f  cmp     eax, [rcx+18h]
0x180019c82  jnz     short loc_180019C6F
0x180019c84  movzx   eax, word ptr [r9+0Ch]
0x180019c89  cmp     ax, [rcx+1Ch]
0x180019c8d  jnz     short loc_180019C6F
0x180019c8f  mov     eax, [rcx+18h]
0x180019c92  cmp     eax, [r9+8]
0x180019c96  jnz     short loc_180019CF0
0x180019c98  movzx   eax, word ptr [rcx+1Ch]
0x180019c9c  cmp     ax, [r9+0Ch]
0x180019ca1  jnz     short loc_180019CF0
0x180019ca3  cmp     rbx, [rsi+8]
0x180019ca7  jz      short loc_180019CD3
0x180019ca9  mov     rcx, [rbx+8]
0x180019cad  mov     rax, [rbx]
0x180019cb0  mov     [rcx], rax
0x180019cb3  mov     rcx, [rbx]
0x180019cb6  mov     rax, [rbx+8]
0x180019cba  mov     [rcx+8], rax
0x180019cbe  lea     rcx, [rbx+20h]; this
0x180019cc2  call    ??1VisibleDock@@QEAA@XZ; VisibleDock::~VisibleDock(void)
0x180019cc7  mov     rcx, rbx; Block
0x180019cca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019ccf  dec     qword ptr [rsi+10h]
0x180019cd3  mov     [r15], rdi
0x180019cd6  mov     byte ptr [r15+8], 0
0x180019cdb  mov     rax, r15
0x180019cde  mov     rbx, [rsp+58h+arg_8]
0x180019ce3  add     rsp, 30h
0x180019ce7  pop     r15
0x180019ce9  pop     r14
0x180019ceb  pop     r12
0x180019ced  pop     rdi
0x180019cee  pop     rsi
0x180019cef  retn
0x180019cf0  mov     rdi, [rcx]
0x180019cf3  mov     rdx, [rbx]
0x180019cf6  cmp     rdi, rdx
0x180019cf9  jz      short loc_180019D28
0x180019cfb  mov     rax, [rbx+8]
0x180019cff  mov     [rax], rdx
0x180019d02  mov     rax, [rdx+8]
0x180019d06  mov     [rax], rdi
0x180019d09  mov     rax, [rdi+8]
0x180019d0d  mov     [rax], rbx
0x180019d10  mov     rcx, [rdi+8]
0x180019d14  mov     rax, [rdx+8]
0x180019d18  mov     [rdi+8], rax
0x180019d1c  mov     rax, [rbx+8]
0x180019d20  mov     [rdx+8], rax
0x180019d24  mov     [rbx+8], rcx
0x180019d28  mov     rdx, [r14]
0x180019d2b  mov     rax, [rdx+r8*8]
0x180019d2f  cmp     rax, [rsi+8]
0x180019d33  jnz     short loc_180019D43
0x180019d35  mov     [rdx+r8*8], rbx
0x180019d39  mov     rax, [r14]
0x180019d3c  mov     [rax+r8*8+8], rbx
0x180019d41  jmp     short loc_180019D71
0x180019d43  cmp     rax, rdi
0x180019d46  jnz     short loc_180019D4E
0x180019d48  mov     [rdx+r8*8], rbx
0x180019d4c  jmp     short loc_180019D71
0x180019d4e  mov     rax, [rdx+r8*8+8]
0x180019d53  mov     rcx, [rax]
0x180019d56  mov     [rdx+r8*8+8], rcx
0x180019d5b  cmp     rcx, rbx
0x180019d5e  jz      short loc_180019D71
0x180019d60  mov     rdx, [r14]
0x180019d63  mov     rax, [rdx+r8*8+8]
0x180019d68  mov     rcx, [rax+8]
0x180019d6c  mov     [rdx+r8*8+8], rcx
0x180019d71  mov     rdi, [rsi+48h]
0x180019d75  mov     rcx, [rsi+10h]
0x180019d79  xorps   xmm0, xmm0
0x180019d7c  test    rcx, rcx
0x180019d7f  js      short loc_180019D88
0x180019d81  cvtsi2ss xmm0, rcx
0x180019d86  jmp     short loc_180019D9D
0x180019d88  mov     rax, rcx
0x180019d8b  shr     rax, 1
0x180019d8e  and     ecx, 1
0x180019d91  or      rax, rcx
0x180019d94  cvtsi2ss xmm0, rax
0x180019d99  addss   xmm0, xmm0
0x180019d9d  xorps   xmm1, xmm1
0x180019da0  test    rdi, rdi
0x180019da3  js      short loc_180019DAC
0x180019da5  cvtsi2ss xmm1, rdi
0x180019daa  jmp     short loc_180019DC4
0x180019dac  mov     rcx, rdi
0x180019daf  shr     rcx, 1
0x180019db2  mov     rax, rdi
0x180019db5  and     eax, 1
0x180019db8  or      rcx, rax
0x180019dbb  cvtsi2ss xmm1, rcx
0x180019dc0  addss   xmm1, xmm1
0x180019dc4  divss   xmm0, xmm1
0x180019dc8  comiss  xmm0, dword ptr [rsi+50h]
0x180019dcc  jbe     loc_180019E5B
0x180019dd2  xor     eax, eax
0x180019dd4  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180019dde  cmp     rdi, rcx
0x180019de1  jnb     short loc_180019DED
0x180019de3  add     rdi, rdi
0x180019de6  inc     eax
0x180019de8  cmp     eax, 3
0x180019deb  jl      short loc_180019DD4
0x180019ded  lea     r12, [rdi+rdi]
0x180019df1  mov     rdx, r12
0x180019df4  mov     rcx, r14
0x180019df7  call    ?reserve@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::reserve(unsigned __int64)
0x180019dfc  mov     rax, [rsi+8]
0x180019e00  mov     [rsp+58h+arg_10], rax
0x180019e05  mov     rdx, [r14]
0x180019e08  cmp     rdx, [r14+8]
0x180019e0c  jz      short loc_180019E12
0x180019e0e  mov     [r14+8], rdx
0x180019e12  lea     r9, [rsp+58h+arg_10]
0x180019e17  mov     r8, r12
0x180019e1a  mov     rcx, r14
0x180019e1d  call    ?_Insert_n@?$vector@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@IEAAXV?$_Vector_const_iterator@V?$_Vector_val@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@@2@@std@@@2@_KAEBV?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::vector<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>>>,unsigned __int64,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>> const &)
0x180019e22  lea     rax, [rdi-1]
0x180019e26  mov     [rsi+40h], rax
0x180019e2a  mov     [rsi+48h], rdi
0x180019e2e  mov     rax, [rsi+8]
0x180019e32  cmp     [rax], rax
0x180019e35  jz      short loc_180019E5B
0x180019e37  mov     r14, [rax+8]
0x180019e3b  mov     rdi, [rsi+8]
0x180019e3f  mov     rdi, [rdi]
0x180019e42  lea     r8, [rdi+10h]
0x180019e46  mov     r9, rdi
0x180019e49  lea     rdx, [rsp+58h+var_38]
0x180019e4e  mov     rcx, rsi
0x180019e51  call    ?_Insert@?$_Hash@V?$_Umap_traits@VHardwareAddress@@VVisibleDock@@V?$_Hash_compare@VHardwareAddress@@V?$hash@VHardwareAddress@@@std@@U?$equal_to@VHardwareAddress@@@3@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@4@$0A@@tr1@std@@@std@@IEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@std@@_N@2@AEBU?$pair@$$CBVHardwareAddress@@VVisibleDock@@@2@V?$_List_iterator@V?$_List_val@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@V?$allocator@U?$pair@$$CBVHardwareAddress@@VVisibleDock@@@std@@@2@@std@@@2@@Z; std::_Hash<std::tr1::_Umap_traits<HardwareAddress,VisibleDock,std::_Hash_compare<HardwareAddress,std::hash<HardwareAddress>,std::equal_to<HardwareAddress>>,std::allocator<std::pair<HardwareAddress const,VisibleDock>>,0>>::_Insert(std::pair<HardwareAddress const,VisibleDock> const &,std::_List_iterator<std::_List_val<std::pair<HardwareAddress const,VisibleDock>>>)
0x180019e56  cmp     rdi, r14
0x180019e59  jnz     short loc_180019E3B
0x180019e5b  mov     [r15], rbx
0x180019e5e  mov     byte ptr [r15+8], 1
0x180019e63  jmp     loc_180019CDB
```
