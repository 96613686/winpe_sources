# std::vector<ATL::CComPtr<IDomNode>,std::allocator<ATL::CComPtr<IDomNode>>>::_Emplace_reallocate<ATL::CComPtr<IDomNode>>(ATL::CComPtr<IDomNode> * const,ATL::CComPtr<IDomNode> &&)

- ea: `0x180023c20`
- end: `0x180023d58`
- name: `??$_Emplace_reallocate@V?$CComPtr@UIDomNode@@@ATL@@@?$vector@V?$CComPtr@UIDomNode@@@ATL@@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@AEAAPEAV?$CComPtr@UIDomNode@@@ATL@@QEAV23@$$QEAV23@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002559c`

## callees

- `0x180011ec4`
- `0x180011f48`
- `0x1800128a0`
- `0x1800128c0`
- `0x180023be8`
- `0x180023c20`
- `0x180023fcc`
- `0x180024028`
- `0x1800241e0`

## pseudocode

```c
__int64 __fastcall std::vector<ATL::CComPtr<IDomNode>>::_Emplace_reallocate<ATL::CComPtr<IDomNode>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  __int64 size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rsi
  __int64 v17; // r15
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v24; // [rsp+38h] [rbp-60h]
  __int64 v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<CSyncMLCmd *>::_Xlength();
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  v23[0] = a1;
  v23[2] = v3;
  v17 = v14 + 8 * v11;
  v25 = v17 + 8;
  ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v17, v15);
  v18 = a1[1];
  v19 = v16;
  v20 = *a1;
  v24 = v17;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move<ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>>>(v20, a2, v16);
    v18 = a1[1];
    v19 = v17 + 8;
    v20 = a2;
    v24 = v16;
  }
  std::_Uninitialized_move<ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>>>(v20, v18, v19);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<ATL::CComPtr<IDomNode>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<ATL::CComPtr<IDomNode>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v17;
}

```

## disassembly

```asm
0x180023c20  push    rbx
0x180023c22  push    rbp
0x180023c23  push    rsi
0x180023c24  push    rdi
0x180023c25  push    r12
0x180023c27  push    r13
0x180023c29  push    r14
0x180023c2b  push    r15
0x180023c2d  sub     rsp, 58h
0x180023c31  mov     rax, [rcx+8]
0x180023c35  mov     rdi, 1FFFFFFFFFFFFFFFh
0x180023c3f  sub     rax, [rcx]
0x180023c42  mov     r13, r8
0x180023c45  sar     rax, 3
0x180023c49  mov     rbp, rdx
0x180023c4c  mov     rbx, rcx
0x180023c4f  cmp     rax, rdi
0x180023c52  jz      loc_180023D52
0x180023c58  mov     r15, rdx
0x180023c5b  lea     r14, [rax+1]
0x180023c5f  sub     r15, [rcx]
0x180023c62  mov     rax, rdi
0x180023c65  mov     rcx, [rcx+10h]
0x180023c69  sub     rcx, [rbx]
0x180023c6c  sar     rcx, 3
0x180023c70  mov     rdx, rcx
0x180023c73  sar     r15, 3
0x180023c77  shr     rdx, 1
0x180023c7a  sub     rax, rdx
0x180023c7d  cmp     rcx, rax
0x180023c80  ja      short loc_180023C8D
0x180023c82  lea     rdi, [rdx+rcx]
0x180023c86  cmp     rdi, r14
0x180023c89  cmovb   rdi, r14
0x180023c8d  mov     rcx, rdi
0x180023c90  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180023c95  mov     rcx, rax
0x180023c98  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180023c9d  mov     rdx, [r13+0]
0x180023ca1  mov     rsi, rax
0x180023ca4  mov     [rsp+98h+var_78], rbx
0x180023ca9  mov     [rsp+98h+var_68], rdi
0x180023cae  lea     r15, [rax+r15*8]
0x180023cb2  lea     r12, [r15+8]
0x180023cb6  mov     rcx, r15
0x180023cb9  mov     [rsp+98h+var_58], r12
0x180023cbe  call    ??0?$CComPtrBase@UIDomNode@@@ATL@@IEAA@PEAUIDomNode@@@Z; ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(IDomNode *)
0x180023cc3  mov     rdx, [rbx+8]
0x180023cc7  mov     r8, rsi
0x180023cca  mov     rcx, [rbx]
0x180023ccd  mov     [rsp+98h+var_60], r15
0x180023cd2  cmp     rbp, rdx
0x180023cd5  jz      short loc_180023CEE
0x180023cd7  mov     rdx, rbp
0x180023cda  call    ??$_Uninitialized_move@PEAV?$CComPtr@UIDomNode@@@ATL@@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDomNode@@@ATL@@QEAV12@0PEAV12@AEAV?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@0@@Z; std::_Uninitialized_move<ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>>>(ATL::CComPtr<IDomNode> * const,ATL::CComPtr<IDomNode> * const,ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>> &)
0x180023cdf  mov     rdx, [rbx+8]
0x180023ce3  mov     r8, r12
0x180023ce6  mov     rcx, rbp
0x180023ce9  mov     [rsp+98h+var_60], rsi
0x180023cee  call    ??$_Uninitialized_move@PEAV?$CComPtr@UIDomNode@@@ATL@@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@YAPEAV?$CComPtr@UIDomNode@@@ATL@@QEAV12@0PEAV12@AEAV?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@0@@Z; std::_Uninitialized_move<ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>>>(ATL::CComPtr<IDomNode> * const,ATL::CComPtr<IDomNode> * const,ATL::CComPtr<IDomNode> *,std::allocator<ATL::CComPtr<IDomNode>> &)
0x180023cf3  mov     rcx, [rbx]
0x180023cf6  mov     [rsp+98h+var_70], 0
0x180023cff  test    rcx, rcx
0x180023d02  jz      short loc_180023D20
0x180023d04  mov     rdx, [rbx+8]
0x180023d08  call    ??$_Destroy_range@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@YAXPEAV?$CComPtr@UIDomNode@@@ATL@@QEAV12@AEAV?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@0@@Z; std::_Destroy_range<std::allocator<ATL::CComPtr<IDomNode>>>(ATL::CComPtr<IDomNode> *,ATL::CComPtr<IDomNode> * const,std::allocator<ATL::CComPtr<IDomNode>> &)
0x180023d0d  mov     rdx, [rbx+10h]
0x180023d11  sub     rdx, [rbx]
0x180023d14  mov     rcx, [rbx]
0x180023d17  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180023d1b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180023d20  mov     [rbx], rsi
0x180023d23  lea     rcx, [rsi+r14*8]
0x180023d27  mov     [rbx+8], rcx
0x180023d2b  lea     rcx, [rsi+rdi*8]
0x180023d2f  mov     [rbx+10h], rcx
0x180023d33  lea     rcx, [rsp+98h+var_78]
0x180023d38  call    ??1_Reallocation_guard@?$vector@V?$CComPtr@UIDomNode@@@ATL@@V?$allocator@V?$CComPtr@UIDomNode@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComPtr<IDomNode>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180023d3d  mov     rax, r15
0x180023d40  add     rsp, 58h
0x180023d44  pop     r15
0x180023d46  pop     r14
0x180023d48  pop     r13
0x180023d4a  pop     r12
0x180023d4c  pop     rdi
0x180023d4d  pop     rsi
0x180023d4e  pop     rbp
0x180023d4f  pop     rbx
0x180023d50  retn
0x180023d52  call    ?_Xlength@?$vector@PEAVCSyncMLCmd@@V?$allocator@PEAVCSyncMLCmd@@@std@@@std@@CAXXZ; std::vector<CSyncMLCmd *>::_Xlength(void)
```
