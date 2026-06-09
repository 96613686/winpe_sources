# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)

- ea: `0x18000fbc0`
- end: `0x18000fd04`
- name: `??$_Emplace_reallocate@AEBUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `324`
- prototype: `char *__fastcall(__int64 *, Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013844`

## callees

- `0x180003430`
- `0x1800035c4`
- `0x180008c48`
- `0x18000fa0c`
- `0x18000fbc0`
- `0x18001000c`
- `0x18001070c`
- `0x1800107a4`
- `0x180011a58`

## pseudocode

```c
char *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
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
  size_t size_of; // rax
  char *v13; // rbp
  char *v14; // r14
  __int64 v15; // rcx
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v16; // rdx
  char *v17; // r8
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *v18; // rcx
  __int64 *v20; // [rsp+20h] [rbp-78h] BYREF
  char *v21; // [rsp+28h] [rbp-70h]
  __int64 v22; // [rsp+30h] [rbp-68h]
  char *v23; // [rsp+38h] [rbp-60h]
  char *v24; // [rsp+40h] [rbp-58h]

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
  v13 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = &v13[v8 & 0xFFFFFFFFFFFFFFC0uLL];
  v20 = a1;
  v21 = v13;
  v22 = v7;
  v24 = v14 + 64;
  std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(
    v15,
    v14,
    a3);
  v23 = v14;
  v16 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)a1[1];
  v17 = v13;
  v18 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*a1;
  if ( a2 != v16 )
  {
    std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v18, a2, v13);
    v23 = v13;
    v17 = v14 + 64;
    v16 = (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)a1[1];
    v18 = a2;
  }
  std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(v18, v16, v17);
  v21 = 0;
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(
      (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)*a1,
      (Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *)a1[1]);
    std::_Deallocate<16>((void *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFC0uLL);
  }
  *a1 = (__int64)v13;
  a1[1] = (__int64)&v13[64 * v9];
  a1[2] = (__int64)&v13[64 * v7];
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return v14;
}

```

## disassembly

```asm
0x18000fbc0  push    rbx
0x18000fbc2  push    rbp
0x18000fbc3  push    rsi
0x18000fbc4  push    rdi
0x18000fbc5  push    r12
0x18000fbc7  push    r13
0x18000fbc9  push    r14
0x18000fbcb  push    r15
0x18000fbcd  sub     rsp, 58h
0x18000fbd1  mov     r13, r8
0x18000fbd4  mov     r15, rdx
0x18000fbd7  mov     rdi, rcx
0x18000fbda  mov     rsi, [rcx+8]
0x18000fbde  sub     rsi, [rcx]
0x18000fbe1  sar     rsi, 6
0x18000fbe5  mov     rbx, 3FFFFFFFFFFFFFFh
0x18000fbef  cmp     rsi, rbx
0x18000fbf2  jz      loc_18000FCFE
0x18000fbf8  mov     r14, rdx
0x18000fbfb  sub     r14, [rcx]
0x18000fbfe  inc     rsi
0x18000fc01  mov     rcx, [rcx+10h]
0x18000fc05  sub     rcx, [rdi]
0x18000fc08  sar     rcx, 6
0x18000fc0c  mov     rdx, rcx
0x18000fc0f  shr     rdx, 1
0x18000fc12  mov     rax, rbx
0x18000fc15  sub     rax, rdx
0x18000fc18  cmp     rcx, rax
0x18000fc1b  ja      short loc_18000FC28
0x18000fc1d  lea     rbx, [rdx+rcx]
0x18000fc21  cmp     rbx, rsi
0x18000fc24  cmovb   rbx, rsi
0x18000fc28  mov     rcx, rbx
0x18000fc2b  call    ??$_Get_size_of_n@$0EA@@std@@YA_K_K@Z; std::_Get_size_of_n<64>(unsigned __int64)
0x18000fc30  mov     rcx, rax
0x18000fc33  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000fc38  mov     rbp, rax
0x18000fc3b  and     r14, 0FFFFFFFFFFFFFFC0h
0x18000fc3f  add     r14, rax
0x18000fc42  lea     r12, [r14+40h]
0x18000fc46  mov     [rsp+98h+var_78], rdi
0x18000fc4b  mov     [rsp+98h+var_70], rax
0x18000fc50  mov     [rsp+98h+var_68], rbx
0x18000fc55  mov     [rsp+98h+var_60], r12
0x18000fc5a  mov     [rsp+98h+var_58], r12
0x18000fc5f  mov     r8, r13
0x18000fc62  mov     rdx, r14
0x18000fc65  call    ??$construct@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU1234@@?$_Default_allocator_traits@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@SAXAEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@1@QEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@AEBU3456@@Z; std::_Default_allocator_traits<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>::construct<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &>(std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping const &)
0x18000fc6a  mov     [rsp+98h+var_60], r14
0x18000fc6f  mov     rdx, [rdi+8]
0x18000fc73  mov     r8, rbp
0x18000fc76  mov     rcx, [rdi]
0x18000fc79  cmp     r15, rdx
0x18000fc7c  jz      short loc_18000FC95
0x18000fc7e  mov     rdx, r15
0x18000fc81  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18000fc86  mov     [rsp+98h+var_60], rbp
0x18000fc8b  mov     r8, r12
0x18000fc8e  mov     rdx, [rdi+8]
0x18000fc92  mov     rcx, r15
0x18000fc95  call    ??$_Uninitialized_move@PEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18000fc9a  mov     [rsp+98h+var_70], 0
0x18000fca3  mov     rcx, [rdi]; this
0x18000fca6  test    rcx, rcx
0x18000fca9  jz      short loc_18000FCC7
0x18000fcab  mov     rdx, [rdi+8]
0x18000fcaf  call    ??$_Destroy_range@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping> &)
0x18000fcb4  mov     rdx, [rdi+10h]
0x18000fcb8  sub     rdx, [rdi]
0x18000fcbb  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18000fcbf  mov     rcx, [rdi]
0x18000fcc2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fcc7  mov     [rdi], rbp
0x18000fcca  shl     rsi, 6
0x18000fcce  add     rsi, rbp
0x18000fcd1  mov     [rdi+8], rsi
0x18000fcd5  shl     rbx, 6
0x18000fcd9  add     rbx, rbp
0x18000fcdc  mov     [rdi+10h], rbx
0x18000fce0  lea     rcx, [rsp+98h+var_78]
0x18000fce5  call    ??1_Reallocation_guard@?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000fcea  mov     rax, r14
0x18000fced  add     rsp, 58h
0x18000fcf1  pop     r15
0x18000fcf3  pop     r14
0x18000fcf5  pop     r13
0x18000fcf7  pop     r12
0x18000fcf9  pop     rdi
0x18000fcfa  pop     rsi
0x18000fcfb  pop     rbp
0x18000fcfc  pop     rbx
0x18000fcfd  retn
0x18000fcfe  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
```
