# std::vector<winrt::com_ptr<ID3D11Texture2D>,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>::_Emplace_reallocate<winrt::com_ptr<ID3D11Texture2D> const &>(winrt::com_ptr<ID3D11Texture2D> * const,winrt::com_ptr<ID3D11Texture2D> const &)

- ea: `0x18000d974`
- end: `0x18000dab9`
- name: `??$_Emplace_reallocate@AEBU?$com_ptr@UID3D11Texture2D@@@winrt@@@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@AEAAPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU23@AEBU23@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180011128`

## callees

- `0x180002720`
- `0x180002794`
- `0x18000d8c0`
- `0x18000d974`
- `0x18000dd5c`
- `0x18000dd88`
- `0x18000eddc`
- `0x180012328`
- `0x180012564`

## pseudocode

```c
_QWORD *__fastcall std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Emplace_reallocate<winrt::com_ptr<ID3D11Texture2D> const &>(
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
  __int64 v15; // rcx
  __int64 v16; // rsi
  _QWORD *v17; // r15
  _QWORD *v18; // r12
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD v23[3]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-60h]
  _QWORD *v25; // [rsp+40h] [rbp-58h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Xlength();
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
  v17 = (_QWORD *)(v14 + 8 * v11);
  *v17 = v15;
  v18 = v17 + 1;
  v25 = v17 + 1;
  winrt::com_ptr<IDCompositionVisual>::add_ref(v17);
  v19 = a1[1];
  v20 = *a1;
  v24 = v17;
  if ( a2 == v19 )
  {
    v18 = (_QWORD *)v16;
  }
  else
  {
    std::_Uninitialized_move<winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(
      v20,
      a2,
      v16,
      a1,
      v23[0]);
    v19 = a1[1];
    v20 = a2;
    v24 = (_QWORD *)v16;
  }
  std::_Uninitialized_move<winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(
    v20,
    v19,
    v18,
    a1,
    v23[0]);
  v21 = *a1;
  v23[1] = 0;
  if ( v21 )
  {
    std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(v21, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  *a1 = v16;
  a1[1] = v16 + 8 * v8;
  a1[2] = v16 + 8 * v3;
  std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Reallocation_guard::~_Reallocation_guard(v23);
  return v17;
}

```

## disassembly

```asm
0x18000d974  push    rbx
0x18000d976  push    rbp
0x18000d977  push    rsi
0x18000d978  push    rdi
0x18000d979  push    r12
0x18000d97b  push    r13
0x18000d97d  push    r14
0x18000d97f  push    r15
0x18000d981  sub     rsp, 58h
0x18000d985  mov     rax, [rcx+8]
0x18000d989  mov     rdi, 1FFFFFFFFFFFFFFFh
0x18000d993  sub     rax, [rcx]
0x18000d996  mov     r13, r8
0x18000d999  sar     rax, 3
0x18000d99d  mov     rbp, rdx
0x18000d9a0  mov     rbx, rcx
0x18000d9a3  cmp     rax, rdi
0x18000d9a6  jz      loc_18000DAB3
0x18000d9ac  mov     r15, rdx
0x18000d9af  lea     r14, [rax+1]
0x18000d9b3  sub     r15, [rcx]
0x18000d9b6  mov     rax, rdi
0x18000d9b9  mov     rcx, [rcx+10h]
0x18000d9bd  sub     rcx, [rbx]
0x18000d9c0  sar     rcx, 3
0x18000d9c4  mov     rdx, rcx
0x18000d9c7  sar     r15, 3
0x18000d9cb  shr     rdx, 1
0x18000d9ce  sub     rax, rdx
0x18000d9d1  cmp     rcx, rax
0x18000d9d4  ja      short loc_18000D9E1
0x18000d9d6  lea     rdi, [rdx+rcx]
0x18000d9da  cmp     rdi, r14
0x18000d9dd  cmovb   rdi, r14
0x18000d9e1  mov     rcx, rdi
0x18000d9e4  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000d9e9  mov     rcx, rax
0x18000d9ec  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000d9f1  mov     rcx, [r13+0]
0x18000d9f5  mov     rsi, rax
0x18000d9f8  mov     [rsp+98h+var_78], rbx
0x18000d9fd  mov     [rsp+98h+var_68], rdi
0x18000da02  lea     r15, [rax+r15*8]
0x18000da06  mov     [r15], rcx
0x18000da09  lea     r12, [r15+8]
0x18000da0d  mov     rcx, r15
0x18000da10  mov     [rsp+98h+var_58], r12
0x18000da15  call    ?add_ref@?$com_ptr@UIDCompositionVisual@@@winrt@@AEBAXXZ; winrt::com_ptr<IDCompositionVisual>::add_ref(void)
0x18000da1a  mov     rdx, [rbx+8]
0x18000da1e  mov     rcx, [rbx]
0x18000da21  mov     [rsp+98h+var_60], r15
0x18000da26  cmp     rbp, rdx
0x18000da29  jnz     short loc_18000DA30
0x18000da2b  mov     r12, rsi
0x18000da2e  jmp     short loc_18000DA4A
0x18000da30  mov     r9, rbx
0x18000da33  mov     r8, rsi
0x18000da36  mov     rdx, rbp
0x18000da39  call    ??$_Uninitialized_move@PEAU?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@YAPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU12@0PEAU12@AEAV?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@0@@Z; std::_Uninitialized_move<winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(winrt::com_ptr<ID3D11Texture2D> * const,winrt::com_ptr<ID3D11Texture2D> * const,winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>> &)
0x18000da3e  mov     rdx, [rbx+8]
0x18000da42  mov     rcx, rbp
0x18000da45  mov     [rsp+98h+var_60], rsi
0x18000da4a  mov     r9, rbx
0x18000da4d  mov     r8, r12
0x18000da50  call    ??$_Uninitialized_move@PEAU?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@YAPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU12@0PEAU12@AEAV?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@0@@Z; std::_Uninitialized_move<winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(winrt::com_ptr<ID3D11Texture2D> * const,winrt::com_ptr<ID3D11Texture2D> * const,winrt::com_ptr<ID3D11Texture2D> *,std::allocator<winrt::com_ptr<ID3D11Texture2D>> &)
0x18000da55  mov     rcx, [rbx]
0x18000da58  mov     [rsp+98h+var_70], 0
0x18000da61  test    rcx, rcx
0x18000da64  jz      short loc_18000DA82
0x18000da66  mov     rdx, [rbx+8]
0x18000da6a  call    ??$_Destroy_range@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@YAXPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU12@AEAV?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@0@@Z; std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(winrt::com_ptr<ID3D11Texture2D> *,winrt::com_ptr<ID3D11Texture2D> * const,std::allocator<winrt::com_ptr<ID3D11Texture2D>> &)
0x18000da6f  mov     rdx, [rbx+10h]
0x18000da73  sub     rdx, [rbx]
0x18000da76  mov     rcx, [rbx]
0x18000da79  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000da7d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000da82  mov     [rbx], rsi
0x18000da85  lea     rcx, [rsi+r14*8]
0x18000da89  mov     [rbx+8], rcx
0x18000da8d  lea     rcx, [rsi+rdi*8]
0x18000da91  mov     [rbx+10h], rcx
0x18000da95  lea     rcx, [rsp+98h+var_78]
0x18000da9a  call    ??1_Reallocation_guard@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000da9f  mov     rax, r15
0x18000daa2  add     rsp, 58h
0x18000daa6  pop     r15
0x18000daa8  pop     r14
0x18000daaa  pop     r13
0x18000daac  pop     r12
0x18000daae  pop     rdi
0x18000daaf  pop     rsi
0x18000dab0  pop     rbp
0x18000dab1  pop     rbx
0x18000dab2  retn
0x18000dab3  call    ?_Xlength@?$vector@U?$com_ptr@UID3D11Texture2D@@@winrt@@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::com_ptr<ID3D11Texture2D>>::_Xlength(void)
```
