# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x180010348`
- end: `0x18001048d`
- name: `??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014030`

## callees

- `0x180003480`
- `0x180003618`
- `0x18000908c`
- `0x1800100fc`
- `0x180010348`
- `0x1800107a0`
- `0x180010e94`
- `0x180010f2c`
- `0x180012228`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
        __int64 *a1,
        Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *a2,
        __int64 a3)
{
  __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // r14
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 size_of; // rax
  __int64 v13; // rbp
  unsigned __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v18; // rcx
  __int64 *v20; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+28h] [rbp-70h]
  __int64 v22; // [rsp+30h] [rbp-68h]
  __int64 v23; // [rsp+38h] [rbp-60h]
  unsigned __int64 v24; // [rsp+40h] [rbp-58h]

  v6 = (a1[1] - *a1) >> 6;
  v7 = 0x3FFFFFFFFFFFFFFLL;
  if ( v6 == 0x3FFFFFFFFFFFFFFLL )
    std::vector<unsigned int>::_Xlength();
  v8 = (__int64)a2 - *a1;
  v9 = v6 + 1;
  v10 = (a1[2] - *a1) >> 6;
  v11 = v10 >> 1;
  if ( v10 <= 0x3FFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v7 = v11 + v10;
    if ( v11 + v10 < v9 )
      v7 = v9;
  }
  size_of = std::_Get_size_of_n<64>(v7);
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = v13 + (v8 & 0xFFFFFFFFFFFFFFC0uLL);
  v20 = a1;
  v21 = v13;
  v22 = v7;
  v24 = v14 + 64;
  std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
    v15,
    v14,
    a3);
  v23 = v14;
  v16 = a1[1];
  v17 = v13;
  v18 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*a1;
  if ( a2 != (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)v16 )
  {
    std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v18, a2, v13);
    v23 = v13;
    v17 = v14 + 64;
    v16 = a1[1];
    v18 = a2;
  }
  std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v18, v16, v17);
  v21 = 0;
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>((Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*a1);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL);
  }
  *a1 = v13;
  a1[1] = v13 + (v9 << 6);
  a1[2] = v13 + (v7 << 6);
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return v14;
}

```

## disassembly

```asm
0x180010348  push    rbx
0x18001034a  push    rbp
0x18001034b  push    rsi
0x18001034c  push    rdi
0x18001034d  push    r12
0x18001034f  push    r13
0x180010351  push    r14
0x180010353  push    r15
0x180010355  sub     rsp, 58h
0x180010359  mov     r13, r8
0x18001035c  mov     r15, rdx
0x18001035f  mov     rdi, rcx
0x180010362  mov     rsi, [rcx+8]
0x180010366  sub     rsi, [rcx]
0x180010369  sar     rsi, 6
0x18001036d  mov     rbx, 3FFFFFFFFFFFFFFh
0x180010377  cmp     rsi, rbx
0x18001037a  jz      loc_180010487
0x180010380  mov     r14, rdx
0x180010383  sub     r14, [rcx]
0x180010386  inc     rsi
0x180010389  mov     rcx, [rcx+10h]
0x18001038d  sub     rcx, [rdi]
0x180010390  sar     rcx, 6
0x180010394  mov     rdx, rcx
0x180010397  shr     rdx, 1
0x18001039a  mov     rax, rbx
0x18001039d  sub     rax, rdx
0x1800103a0  cmp     rcx, rax
0x1800103a3  ja      short loc_1800103B0
0x1800103a5  lea     rbx, [rdx+rcx]
0x1800103a9  cmp     rbx, rsi
0x1800103ac  cmovb   rbx, rsi
0x1800103b0  mov     rcx, rbx
0x1800103b3  call    ??$_Get_size_of_n@$0EA@@std@@YA_K_K@Z; std::_Get_size_of_n<64>(unsigned __int64)
0x1800103b8  mov     rcx, rax
0x1800103bb  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800103c0  mov     rbp, rax
0x1800103c3  and     r14, 0FFFFFFFFFFFFFFC0h
0x1800103c7  add     r14, rax
0x1800103ca  lea     r12, [r14+40h]
0x1800103ce  mov     [rsp+98h+var_78], rdi
0x1800103d3  mov     [rsp+98h+var_70], rax
0x1800103d8  mov     [rsp+98h+var_68], rbx
0x1800103dd  mov     [rsp+98h+var_60], r12
0x1800103e2  mov     [rsp+98h+var_58], r12
0x1800103e7  mov     r8, r13
0x1800103ea  mov     rdx, r14
0x1800103ed  call    ??$construct@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@SAXAEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@1@QEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x1800103f2  mov     [rsp+98h+var_60], r14
0x1800103f7  mov     rdx, [rdi+8]
0x1800103fb  mov     r8, rbp
0x1800103fe  mov     rcx, [rdi]
0x180010401  cmp     r15, rdx
0x180010404  jz      short loc_18001041D
0x180010406  mov     rdx, r15
0x180010409  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001040e  mov     [rsp+98h+var_60], rbp
0x180010413  mov     r8, r12
0x180010416  mov     rdx, [rdi+8]
0x18001041a  mov     rcx, r15
0x18001041d  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x180010422  mov     [rsp+98h+var_70], 0
0x18001042b  mov     rcx, [rdi]; this
0x18001042e  test    rcx, rcx
0x180010431  jz      short loc_18001044F
0x180010433  mov     rdx, [rdi+8]
0x180010437  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18001043c  mov     rdx, [rdi+10h]
0x180010440  sub     rdx, [rdi]
0x180010443  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180010447  mov     rcx, [rdi]
0x18001044a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001044f  mov     [rdi], rbp
0x180010452  shl     rsi, 6
0x180010456  add     rsi, rbp
0x180010459  mov     [rdi+8], rsi
0x18001045d  shl     rbx, 6
0x180010461  add     rbx, rbp
0x180010464  mov     [rdi+10h], rbx
0x180010468  lea     rcx, [rsp+98h+var_78]
0x18001046d  call    ??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(void)
0x180010472  mov     rax, r14
0x180010475  add     rsp, 58h
0x180010479  pop     r15
0x18001047b  pop     r14
0x18001047d  pop     r13
0x18001047f  pop     r12
0x180010481  pop     rdi
0x180010482  pop     rsi
0x180010483  pop     rbp
0x180010484  pop     rbx
0x180010485  retn
0x180010487  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
```
