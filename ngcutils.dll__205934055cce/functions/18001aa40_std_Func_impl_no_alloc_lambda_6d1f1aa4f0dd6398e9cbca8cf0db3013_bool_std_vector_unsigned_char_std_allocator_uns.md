# std::_Func_impl_no_alloc__lambda_6d1f1aa4f0dd6398e9cbca8cf0db3013__bool_std::vector_unsigned_char_std::allocator_unsigned_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____bool_::_Do_call

- ea: `0x18001aa40`
- end: `0x18001ab8f`
- name: `std::_Func_impl_no_alloc__lambda_6d1f1aa4f0dd6398e9cbca8cf0db3013__bool_std::vector_unsigned_char_std::allocator_unsigned_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____bool_::_Do_call`
- size: `335`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005250`
- `0x18000ce74`
- `0x18000cfcc`
- `0x180013834`
- `0x18001aa40`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001aae4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001aae4`

## pseudocode

```c
char __fastcall std::_Func_impl_no_alloc__lambda_6d1f1aa4f0dd6398e9cbca8cf0db3013__bool_std::vector_unsigned_char_std::allocator_unsigned_char____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____bool_::_Do_call(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        char *a5)
{
  __int128 v6; // xmm1
  char v7; // r10
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int64 v10; // rcx
  void *v11; // r8
  _QWORD *v12; // rdi
  __int64 v13; // rax
  char *v14; // rbx
  __int64 trivial_2; // rax
  char v16; // bl
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  _QWORD v22[3]; // [rsp+20h] [rbp-60h] BYREF
  _OWORD v23[2]; // [rsp+38h] [rbp-48h] BYREF
  _OWORD v24[2]; // [rsp+58h] [rbp-28h] BYREF

  v6 = *(_OWORD *)(a4 + 16);
  v24[0] = *(_OWORD *)a4;
  v7 = *a5;
  *(_WORD *)a4 = 0;
  *(_QWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 24) = 7;
  v8 = *a3;
  v24[1] = v6;
  v9 = a3[1];
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 3) = 7;
  *(_WORD *)a3 = 0;
  v10 = *(_QWORD *)(a2 + 16);
  v11 = *(void **)a2;
  *(_QWORD *)(a2 + 16) = 0;
  v22[1] = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)a2 = 0;
  v22[0] = v11;
  v22[2] = v10;
  v23[0] = v8;
  v23[1] = v9;
  if ( v7 || !EqualSid(**(PSID **)(a1 + 8), v11) )
    goto LABEL_10;
  std::wstring::operator=(**(_QWORD **)(a1 + 16), v23);
  std::wstring::operator=(**(_QWORD **)(a1 + 24), v24);
  if ( !**(_BYTE **)(a1 + 32) )
    goto LABEL_9;
  v12 = **(_QWORD ***)(a1 + 16);
  v13 = v12[2];
  if ( v12[3] > 7u )
    v12 = (_QWORD *)*v12;
  if ( !v13
    || (v14 = (char *)v12 + 2 * v13, trivial_2 = _std_find_trivial_2(v12, v14, 64), (char *)trivial_2 == v14)
    || (trivial_2 - (__int64)v12) >> 1 == -1 )
  {
LABEL_10:
    v16 = 0;
  }
  else
  {
LABEL_9:
    v16 = 1;
  }
  std::vector<unsigned char>::~vector<unsigned char>(v22);
  std::wstring::~wstring(v23, v17, v18);
  std::wstring::~wstring(v24, v19, v20);
  return v16;
}

```

## disassembly

```asm
0x18001aa40  mov     [rsp-8+arg_0], rbx
0x18001aa45  mov     [rsp-8+arg_8], rdi
0x18001aa4a  push    rbp
0x18001aa4b  mov     rbp, rsp
0x18001aa4e  sub     rsp, 80h
0x18001aa55  movups  xmm0, xmmword ptr [r9]
0x18001aa59  mov     rax, [rbp+arg_20]
0x18001aa5d  mov     rbx, rcx
0x18001aa60  movups  xmm1, xmmword ptr [r9+10h]
0x18001aa65  movups  [rbp+var_28], xmm0
0x18001aa69  mov     r10b, [rax]
0x18001aa6c  xor     eax, eax
0x18001aa6e  mov     [r9], ax
0x18001aa72  mov     qword ptr [r9+10h], 0
0x18001aa7a  mov     qword ptr [r9+18h], 7
0x18001aa82  movups  xmm0, xmmword ptr [r8]
0x18001aa86  movups  [rbp+var_18], xmm1
0x18001aa8a  movups  xmm1, xmmword ptr [r8+10h]
0x18001aa8f  mov     [r8+10h], rax
0x18001aa93  mov     qword ptr [r8+18h], 7
0x18001aa9b  mov     [r8], ax
0x18001aa9f  mov     rcx, [rdx+10h]
0x18001aaa3  mov     r8, [rdx]
0x18001aaa6  mov     [rdx+10h], rax
0x18001aaaa  mov     rax, [rdx+8]
0x18001aaae  mov     [rbp+var_58], rax
0x18001aab2  mov     qword ptr [rdx+8], 0
0x18001aaba  mov     qword ptr [rdx], 0
0x18001aac1  mov     [rbp+var_60], r8
0x18001aac5  mov     [rbp+var_50], rcx
0x18001aac9  movups  [rbp+var_48], xmm0
0x18001aacd  movups  [rbp+var_38], xmm1
0x18001aad1  test    r10b, r10b
0x18001aad4  jnz     loc_18001AB5B
0x18001aada  mov     rcx, [rbx+8]
0x18001aade  mov     rdx, r8; pSid2
0x18001aae1  mov     rcx, [rcx]; pSid1
0x18001aae4  call    cs:__imp_EqualSid
0x18001aaea  test    eax, eax
0x18001aaec  jz      short loc_18001AB5B
0x18001aaee  mov     rcx, [rbx+10h]
0x18001aaf2  lea     rdx, [rbp+var_48]
0x18001aaf6  mov     rcx, [rcx]
0x18001aaf9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001aafe  mov     rcx, [rbx+18h]
0x18001ab02  lea     rdx, [rbp+var_28]
0x18001ab06  mov     rcx, [rcx]
0x18001ab09  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ab0e  mov     rax, [rbx+20h]
0x18001ab12  cmp     byte ptr [rax], 0
0x18001ab15  jz      short loc_18001AB57
0x18001ab17  mov     rax, [rbx+10h]
0x18001ab1b  mov     rdi, [rax]
0x18001ab1e  cmp     qword ptr [rdi+18h], 7
0x18001ab23  mov     rax, [rdi+10h]
0x18001ab27  jbe     short loc_18001AB2C
0x18001ab29  mov     rdi, [rdi]
0x18001ab2c  test    rax, rax
0x18001ab2f  jz      short loc_18001AB5B
0x18001ab31  lea     rbx, [rdi+rax*2]
0x18001ab35  mov     r8d, 40h ; '@'
0x18001ab3b  mov     rdx, rbx
0x18001ab3e  mov     rcx, rdi
0x18001ab41  call    __std_find_trivial_2
0x18001ab46  cmp     rax, rbx
0x18001ab49  jz      short loc_18001AB5B
0x18001ab4b  sub     rax, rdi
0x18001ab4e  sar     rax, 1
0x18001ab51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ab55  jz      short loc_18001AB5B
0x18001ab57  mov     bl, 1
0x18001ab59  jmp     short loc_18001AB5D
0x18001ab5b  xor     bl, bl
0x18001ab5d  lea     rcx, [rbp+var_60]
0x18001ab61  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001ab66  lea     rcx, [rbp+var_48]
0x18001ab6a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ab6f  lea     rcx, [rbp+var_28]
0x18001ab73  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ab78  lea     r11, [rsp+80h+var_s0]
0x18001ab80  mov     al, bl
0x18001ab82  mov     rbx, [r11+10h]
0x18001ab86  mov     rdi, [r11+18h]
0x18001ab8a  mov     rsp, r11
0x18001ab8d  pop     rbp
0x18001ab8e  retn
```
