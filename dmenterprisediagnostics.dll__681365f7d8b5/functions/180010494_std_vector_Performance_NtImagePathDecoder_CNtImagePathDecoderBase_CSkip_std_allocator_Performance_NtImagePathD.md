# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x180010494`
- end: `0x1800105f4`
- name: `??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014168`

## callees

- `0x180003480`
- `0x180003618`
- `0x1800074b8`
- `0x18000908c`
- `0x180010134`
- `0x180010494`
- `0x180010ee8`
- `0x180011118`
- `0x180012264`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v5; // r14
  __int64 v6; // rdi
  __int64 v7; // rbp
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rsi
  unsigned __int64 v13; // r14
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 *v18; // [rsp+20h] [rbp-78h] BYREF
  __int64 v19; // [rsp+28h] [rbp-70h]
  __int64 v20; // [rsp+30h] [rbp-68h]
  __int64 v21; // [rsp+38h] [rbp-60h]
  unsigned __int64 v22; // [rsp+40h] [rbp-58h]

  v5 = *a1;
  v6 = (a1[1] - *a1) >> 5;
  v7 = 0x7FFFFFFFFFFFFFFLL;
  if ( v6 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<unsigned int>::_Xlength();
  v8 = v6 + 1;
  v9 = (a1[2] - v5) >> 5;
  if ( v9 <= 0x7FFFFFFFFFFFFFFLL - (v9 >> 1) )
  {
    v10 = (v9 >> 1) + v9;
    v11 = v8;
    if ( v10 >= v8 )
      v11 = v10;
    if ( v11 > 0x7FFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    v7 = v11;
  }
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(32 * v7);
  v13 = ((a2 - v5) & 0xFFFFFFFFFFFFFFE0uLL) + v12;
  v18 = a1;
  v19 = v12;
  v20 = v7;
  v22 = v13 + 32;
  std::wstring::wstring(v13, a3);
  v21 = v13;
  v14 = a1[1];
  v15 = v12;
  v16 = *a1;
  if ( a2 != v14 )
  {
    std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(v16, a2, v12);
    v21 = v12;
    v15 = v13 + 32;
    v14 = a1[1];
    v16 = a2;
  }
  std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(v16, v14, v15);
  v19 = 0;
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(*a1, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  *a1 = v12;
  a1[1] = v12 + 32 * v8;
  a1[2] = 32 * v7 + v12;
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(&v18);
  return v13;
}

```

## disassembly

```asm
0x180010494  mov     [rsp+arg_10], r8
0x180010499  push    rbx
0x18001049a  push    rbp
0x18001049b  push    rsi
0x18001049c  push    rdi
0x18001049d  push    r12
0x18001049f  push    r13
0x1800104a1  push    r14
0x1800104a3  push    r15
0x1800104a5  sub     rsp, 58h
0x1800104a9  mov     r15, rdx
0x1800104ac  mov     rbx, rcx
0x1800104af  mov     r14, [rcx]
0x1800104b2  mov     rdi, [rcx+8]
0x1800104b6  sub     rdi, r14
0x1800104b9  sar     rdi, 5
0x1800104bd  mov     rbp, 7FFFFFFFFFFFFFFh
0x1800104c7  cmp     rdi, rbp
0x1800104ca  jz      loc_1800105EE
0x1800104d0  inc     rdi
0x1800104d3  mov     rcx, [rcx+10h]
0x1800104d7  sub     rcx, r14
0x1800104da  sar     rcx, 5
0x1800104de  mov     rdx, rcx
0x1800104e1  shr     rdx, 1
0x1800104e4  mov     rax, rbp
0x1800104e7  sub     rax, rdx
0x1800104ea  cmp     rcx, rax
0x1800104ed  ja      short loc_180010509
0x1800104ef  lea     rax, [rdx+rcx]
0x1800104f3  mov     rcx, rdi
0x1800104f6  cmp     rax, rdi
0x1800104f9  cmovnb  rcx, rax
0x1800104fd  cmp     rcx, rbp
0x180010500  ja      loc_1800105E8
0x180010506  mov     rbp, rcx
0x180010509  mov     r12, rbp
0x18001050c  shl     r12, 5
0x180010510  mov     rcx, r12
0x180010513  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180010518  mov     rsi, rax
0x18001051b  mov     rcx, r15
0x18001051e  sub     rcx, r14
0x180010521  and     rcx, 0FFFFFFFFFFFFFFE0h
0x180010525  lea     r14, [rcx+rax]
0x180010529  lea     r13, [r14+20h]
0x18001052d  mov     [rsp+98h+var_78], rbx
0x180010532  mov     [rsp+98h+var_70], rax
0x180010537  mov     [rsp+98h+var_68], rbp
0x18001053c  mov     [rsp+98h+var_60], r13
0x180010541  mov     [rsp+98h+var_58], r13
0x180010546  mov     rdx, [rsp+98h+arg_10]
0x18001054e  mov     rcx, r14
0x180010551  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010556  mov     [rsp+98h+var_60], r14
0x18001055b  mov     rdx, [rbx+8]
0x18001055f  mov     r8, rsi
0x180010562  mov     rcx, [rbx]
0x180010565  cmp     r15, rdx
0x180010568  jz      short loc_180010581
0x18001056a  mov     rdx, r15
0x18001056d  call    ??$_Uninitialized_move@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x180010572  mov     [rsp+98h+var_60], rsi
0x180010577  mov     r8, r13
0x18001057a  mov     rdx, [rbx+8]
0x18001057e  mov     rcx, r15
0x180010581  call    ??$_Uninitialized_move@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x180010586  mov     [rsp+98h+var_70], 0
0x18001058f  mov     rcx, [rbx]
0x180010592  test    rcx, rcx
0x180010595  jz      short loc_1800105B3
0x180010597  mov     rdx, [rbx+8]
0x18001059b  call    ??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x1800105a0  mov     rdx, [rbx+10h]
0x1800105a4  sub     rdx, [rbx]
0x1800105a7  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800105ab  mov     rcx, [rbx]
0x1800105ae  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800105b3  mov     [rbx], rsi
0x1800105b6  shl     rdi, 5
0x1800105ba  add     rdi, rsi
0x1800105bd  mov     [rbx+8], rdi
0x1800105c1  lea     rcx, [r12+rsi]
0x1800105c5  mov     [rbx+10h], rcx
0x1800105c9  lea     rcx, [rsp+98h+var_78]
0x1800105ce  call    ??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800105d3  mov     rax, r14
0x1800105d6  add     rsp, 58h
0x1800105da  pop     r15
0x1800105dc  pop     r14
0x1800105de  pop     r13
0x1800105e0  pop     r12
0x1800105e2  pop     rdi
0x1800105e3  pop     rsi
0x1800105e4  pop     rbp
0x1800105e5  pop     rbx
0x1800105e6  retn
0x1800105e8  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x1800105ee  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
```
