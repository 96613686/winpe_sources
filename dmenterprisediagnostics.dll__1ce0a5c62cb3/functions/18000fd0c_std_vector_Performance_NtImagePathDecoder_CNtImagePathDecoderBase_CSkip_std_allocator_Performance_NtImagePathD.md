# std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &)

- ea: `0x18000fd0c`
- end: `0x18000fe6b`
- name: `??$_Emplace_reallocate@AEBUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@AEAAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU2345@AEBU2345@@Z`
- size: `351`
- prototype: `char *__fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013974`

## callees

- `0x180003430`
- `0x1800035c4`
- `0x18000720c`
- `0x180008c48`
- `0x18000fa44`
- `0x18000fd0c`
- `0x180010760`
- `0x180010988`
- `0x180011a94`

## pseudocode

```c
char *__fastcall std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Emplace_reallocate<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip const &>(
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
  char *v12; // rsi
  char *v13; // r14
  __int64 v14; // rdx
  char *v15; // r8
  __int64 v16; // rcx
  __int64 *v18; // [rsp+20h] [rbp-78h] BYREF
  char *v19; // [rsp+28h] [rbp-70h]
  __int64 v20; // [rsp+30h] [rbp-68h]
  char *v21; // [rsp+38h] [rbp-60h]
  char *v22; // [rsp+40h] [rbp-58h]

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
  v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(32 * v7);
  v13 = &v12[(a2 - v5) & 0xFFFFFFFFFFFFFFE0uLL];
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
    std::_Deallocate<16>((void *)*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  *a1 = (__int64)v12;
  a1[1] = (__int64)&v12[32 * v8];
  a1[2] = (__int64)&v12[32 * v7];
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(&v18);
  return v13;
}

```

## disassembly

```asm
0x18000fd0c  mov     [rsp+arg_10], r8
0x18000fd11  push    rbx
0x18000fd12  push    rbp
0x18000fd13  push    rsi
0x18000fd14  push    rdi
0x18000fd15  push    r12
0x18000fd17  push    r13
0x18000fd19  push    r14
0x18000fd1b  push    r15
0x18000fd1d  sub     rsp, 58h
0x18000fd21  mov     r15, rdx
0x18000fd24  mov     rbx, rcx
0x18000fd27  mov     r14, [rcx]
0x18000fd2a  mov     rdi, [rcx+8]
0x18000fd2e  sub     rdi, r14
0x18000fd31  sar     rdi, 5
0x18000fd35  mov     rbp, 7FFFFFFFFFFFFFFh
0x18000fd3f  cmp     rdi, rbp
0x18000fd42  jz      loc_18000FE65
0x18000fd48  inc     rdi
0x18000fd4b  mov     rcx, [rcx+10h]
0x18000fd4f  sub     rcx, r14
0x18000fd52  sar     rcx, 5
0x18000fd56  mov     rdx, rcx
0x18000fd59  shr     rdx, 1
0x18000fd5c  mov     rax, rbp
0x18000fd5f  sub     rax, rdx
0x18000fd62  cmp     rcx, rax
0x18000fd65  ja      short loc_18000FD81
0x18000fd67  lea     rax, [rdx+rcx]
0x18000fd6b  mov     rcx, rdi
0x18000fd6e  cmp     rax, rdi
0x18000fd71  cmovnb  rcx, rax
0x18000fd75  cmp     rcx, rbp
0x18000fd78  ja      loc_18000FE5F
0x18000fd7e  mov     rbp, rcx
0x18000fd81  mov     r12, rbp
0x18000fd84  shl     r12, 5
0x18000fd88  mov     rcx, r12
0x18000fd8b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000fd90  mov     rsi, rax
0x18000fd93  mov     rcx, r15
0x18000fd96  sub     rcx, r14
0x18000fd99  and     rcx, 0FFFFFFFFFFFFFFE0h
0x18000fd9d  lea     r14, [rcx+rax]
0x18000fda1  lea     r13, [r14+20h]
0x18000fda5  mov     [rsp+98h+var_78], rbx
0x18000fdaa  mov     [rsp+98h+var_70], rax
0x18000fdaf  mov     [rsp+98h+var_68], rbp
0x18000fdb4  mov     [rsp+98h+var_60], r13
0x18000fdb9  mov     [rsp+98h+var_58], r13
0x18000fdbe  mov     rdx, [rsp+98h+arg_10]
0x18000fdc6  mov     rcx, r14
0x18000fdc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000fdce  mov     [rsp+98h+var_60], r14
0x18000fdd3  mov     rdx, [rbx+8]
0x18000fdd7  mov     r8, rsi
0x18000fdda  mov     rcx, [rbx]
0x18000fddd  cmp     r15, rdx
0x18000fde0  jz      short loc_18000FDF9
0x18000fde2  mov     rdx, r15
0x18000fde5  call    ??$_Uninitialized_move@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x18000fdea  mov     [rsp+98h+var_60], rsi
0x18000fdef  mov     r8, r13
0x18000fdf2  mov     rdx, [rbx+8]
0x18000fdf6  mov     rcx, r15
0x18000fdf9  call    ??$_Uninitialized_move@PEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@0PEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Uninitialized_move<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x18000fdfe  mov     [rsp+98h+var_70], 0
0x18000fe07  mov     rcx, [rbx]
0x18000fe0a  test    rcx, rcx
0x18000fe0d  jz      short loc_18000FE2B
0x18000fe0f  mov     rdx, [rbx+8]
0x18000fe13  call    ??$_Destroy_range@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@YAXPEAUCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAU1234@AEAV?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@0@@Z; std::_Destroy_range<std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>>(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip *,Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip * const,std::allocator<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip> &)
0x18000fe18  mov     rdx, [rbx+10h]
0x18000fe1c  sub     rdx, [rbx]
0x18000fe1f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18000fe23  mov     rcx, [rbx]
0x18000fe26  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000fe2b  mov     [rbx], rsi
0x18000fe2e  shl     rdi, 5
0x18000fe32  add     rdi, rsi
0x18000fe35  mov     [rbx+8], rdi
0x18000fe39  lea     rcx, [r12+rsi]
0x18000fe3d  mov     [rbx+10h], rcx
0x18000fe41  lea     rcx, [rsp+98h+var_78]
0x18000fe46  call    ??1_Reallocation_guard@?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000fe4b  mov     rax, r14
0x18000fe4e  add     rsp, 58h
0x18000fe52  pop     r15
0x18000fe54  pop     r14
0x18000fe56  pop     r13
0x18000fe58  pop     r12
0x18000fe5a  pop     rdi
0x18000fe5b  pop     rsi
0x18000fe5c  pop     rbp
0x18000fe5d  pop     rbx
0x18000fe5e  retn
0x18000fe5f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000fe65  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
```
