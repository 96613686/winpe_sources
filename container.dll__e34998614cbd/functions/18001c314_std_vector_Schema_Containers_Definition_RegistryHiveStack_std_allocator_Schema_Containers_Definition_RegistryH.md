# std::vector<Schema::Containers::Definition::RegistryHiveStack,std::allocator<Schema::Containers::Definition::RegistryHiveStack>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryHiveStack * const)

- ea: `0x18001c314`
- end: `0x18001c56c`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryHiveStack@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180015f70`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001c314`
- `0x18001dfd0`
- `0x18001ee70`
- `0x180021b68`
- `0x180021cd4`
- `0x180021d98`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Emplace_reallocate<>(
        void **a1,
        _BYTE *a2)
{
  _BYTE *v2; // rbp
  __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // r12
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r14
  char *v11; // rbx
  void *v12; // rax
  __int64 v13; // r13
  char *v14; // rcx
  char *v15; // rbp
  char *v16; // r8
  _BYTE *v17; // rdx
  void *v18; // rcx
  char *v19; // rsi
  char *v20; // rbp
  char *v21; // rcx
  _BYTE *v22; // rax
  _QWORD v24[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v25; // [rsp+38h] [rbp-60h]
  char *v26; // [rsp+40h] [rbp-58h]

  v2 = *a1;
  v5 = 0x4EC4EC4EC4EC4EC5LL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 3);
  if ( v5 == 0x276276276276276LL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v6 = 0x4EC4EC4EC4EC4EC5LL * (((_BYTE *)a1[2] - v2) >> 3);
  v7 = v6 >> 1;
  if ( v6 > 0x276276276276276LL - (v6 >> 1) )
    goto LABEL_26;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x276276276276276LL )
    goto LABEL_26;
  v10 = 104 * v9;
  if ( !(104 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = (char *)operator new(104 * v9);
    goto LABEL_13;
  }
  if ( v10 + 39 < v10 )
LABEL_26:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    goto LABEL_21;
  v11 = (char *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v11 - 1) = v12;
LABEL_13:
  v24[0] = a1;
  v24[2] = v9;
  v13 = (a2 - v2) / 104;
  v14 = &v11[104 * v13];
  v25 = v14;
  *(_OWORD *)v14 = 0;
  *((_QWORD *)v14 + 2) = 0;
  v15 = v14 + 104;
  *((_QWORD *)v14 + 3) = 7;
  *(_WORD *)v14 = 0;
  *((_QWORD *)v14 + 4) = 0;
  *((_QWORD *)v14 + 5) = 0;
  *((_QWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 7) = 0;
  *((_QWORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 12) = 0;
  v16 = v11;
  v17 = a1[1];
  v18 = *a1;
  v26 = v15;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryHiveStack *>(v18, a2, v11);
    v17 = a1[1];
    v16 = v15;
    v18 = a2;
    v25 = v11;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::RegistryHiveStack *>(v18, v17, v16);
  v19 = (char *)*a1;
  v24[1] = 0;
  if ( v19 )
  {
    v20 = (char *)a1[1];
    while ( v19 != v20 )
    {
      std::vector<std::wstring>::_Tidy(v19 + 80);
      std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(v19 + 56);
      std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(v19 + 32);
      std::wstring::~wstring(v19);
      v19 += 104;
    }
    v21 = (char *)*a1;
    if ( (unsigned __int64)(8 * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 3)) < 0x1000 )
    {
      v22 = *a1;
    }
    else
    {
      v22 = (_BYTE *)*((_QWORD *)v21 - 1);
      if ( (unsigned __int64)(v21 - v22 - 8) > 0x1F )
LABEL_21:
        __fastfail(5u);
    }
    operator delete(v22);
  }
  *a1 = v11;
  a1[1] = &v11[104 * v8];
  a1[2] = &v11[v10];
  std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Reallocation_guard::~_Reallocation_guard(v24);
  return &v11[104 * v13];
}

```

## disassembly

```asm
0x18001c314  push    rbx
0x18001c316  push    rbp
0x18001c317  push    rsi
0x18001c318  push    rdi
0x18001c319  push    r12
0x18001c31b  push    r13
0x18001c31d  push    r14
0x18001c31f  push    r15
0x18001c321  sub     rsp, 58h
0x18001c325  mov     rbp, [rcx]
0x18001c328  mov     r13, 4EC4EC4EC4EC4EC5h
0x18001c332  mov     r8, [rcx+8]
0x18001c336  mov     r9, 276276276276276h
0x18001c340  sub     r8, rbp
0x18001c343  mov     r15, rdx
0x18001c346  sar     r8, 3
0x18001c34a  mov     rdi, rcx
0x18001c34d  imul    r8, r13
0x18001c351  cmp     r8, r9
0x18001c354  jz      loc_18001C560
0x18001c35a  mov     rcx, [rcx+10h]
0x18001c35e  mov     rax, r9
0x18001c361  sub     rcx, rbp
0x18001c364  sar     rcx, 3
0x18001c368  imul    rcx, r13
0x18001c36c  mov     rdx, rcx
0x18001c36f  shr     rdx, 1
0x18001c372  sub     rax, rdx
0x18001c375  cmp     rcx, rax
0x18001c378  ja      loc_18001C566
0x18001c37e  lea     r12, [r8+1]
0x18001c382  lea     rax, [rcx+rdx]
0x18001c386  mov     rsi, r12
0x18001c389  cmp     rax, r12
0x18001c38c  cmovnb  rsi, rax
0x18001c390  cmp     rsi, r9
0x18001c393  ja      loc_18001C566
0x18001c399  imul    r14, rsi, 68h ; 'h'
0x18001c39d  xor     r8d, r8d
0x18001c3a0  test    r14, r14
0x18001c3a3  jnz     short loc_18001C3AA
0x18001c3a5  mov     ebx, r8d
0x18001c3a8  jmp     short loc_18001C3ED
0x18001c3aa  cmp     r14, 1000h
0x18001c3b1  jb      short loc_18001C3DF
0x18001c3b3  lea     rcx, [r14+27h]; Size
0x18001c3b7  cmp     rcx, r14
0x18001c3ba  jbe     loc_18001C566
0x18001c3c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c3c5  xor     r8d, r8d
0x18001c3c8  test    rax, rax
0x18001c3cb  jz      loc_18001C515
0x18001c3d1  lea     rbx, [rax+27h]
0x18001c3d5  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001c3d9  mov     [rbx-8], rax
0x18001c3dd  jmp     short loc_18001C3ED
0x18001c3df  mov     rcx, r14; Size
0x18001c3e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c3e7  mov     rbx, rax
0x18001c3ea  xor     r8d, r8d
0x18001c3ed  mov     rax, r13
0x18001c3f0  mov     [rsp+98h+var_78], rdi
0x18001c3f5  mov     rcx, r15
0x18001c3f8  mov     [rsp+98h+var_68], rsi
0x18001c3fd  sub     rcx, rbp
0x18001c400  xorps   xmm0, xmm0
0x18001c403  imul    rcx
0x18001c406  mov     r13, rdx
0x18001c409  sar     r13, 5
0x18001c40d  mov     rcx, r13
0x18001c410  shr     rcx, 3Fh
0x18001c414  add     r13, rcx
0x18001c417  imul    rcx, r13, 68h ; 'h'
0x18001c41b  add     rcx, rbx
0x18001c41e  mov     [rsp+98h+var_60], rcx
0x18001c423  movups  xmmword ptr [rcx], xmm0
0x18001c426  mov     [rcx+10h], r8
0x18001c42a  lea     rbp, [rcx+68h]
0x18001c42e  mov     qword ptr [rcx+18h], 7
0x18001c436  mov     [rcx], r8w
0x18001c43a  mov     [rcx+20h], r8
0x18001c43e  mov     [rcx+28h], r8
0x18001c442  mov     [rcx+30h], r8
0x18001c446  mov     [rcx+38h], r8
0x18001c44a  mov     [rcx+40h], r8
0x18001c44e  mov     [rcx+48h], r8
0x18001c452  mov     [rcx+50h], r8
0x18001c456  mov     [rcx+58h], r8
0x18001c45a  mov     [rcx+60h], r8
0x18001c45e  mov     r8, rbx
0x18001c461  mov     rdx, [rdi+8]
0x18001c465  mov     rcx, [rdi]
0x18001c468  mov     [rsp+98h+var_58], rbp
0x18001c46d  cmp     r15, rdx
0x18001c470  jz      short loc_18001C489
0x18001c472  mov     rdx, r15
0x18001c475  call    ??$_Uninitialized_move@PEAURegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryHiveStack@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryHiveStack *>(Schema::Containers::Definition::RegistryHiveStack * const,Schema::Containers::Definition::RegistryHiveStack * const,Schema::Containers::Definition::RegistryHiveStack *,std::allocator<Schema::Containers::Definition::RegistryHiveStack> &)
0x18001c47a  mov     rdx, [rdi+8]
0x18001c47e  mov     r8, rbp
0x18001c481  mov     rcx, r15
0x18001c484  mov     [rsp+98h+var_60], rbx
0x18001c489  call    ??$_Uninitialized_move@PEAURegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryHiveStack@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryHiveStack *>(Schema::Containers::Definition::RegistryHiveStack * const,Schema::Containers::Definition::RegistryHiveStack * const,Schema::Containers::Definition::RegistryHiveStack *,std::allocator<Schema::Containers::Definition::RegistryHiveStack> &)
0x18001c48e  mov     rsi, [rdi]
0x18001c491  mov     [rsp+98h+var_70], 0
0x18001c49a  test    rsi, rsi
0x18001c49d  jz      loc_18001C527
0x18001c4a3  mov     rbp, [rdi+8]
0x18001c4a7  jmp     short loc_18001C4D0
0x18001c4a9  lea     rcx, [rsi+50h]
0x18001c4ad  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001c4b2  lea     rcx, [rsi+38h]
0x18001c4b6  call    ?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(void)
0x18001c4bb  lea     rcx, [rsi+20h]
0x18001c4bf  call    ?_Tidy@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryLayer>::_Tidy(void)
0x18001c4c4  mov     rcx, rsi
0x18001c4c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c4cc  add     rsi, 68h ; 'h'
0x18001c4d0  cmp     rsi, rbp
0x18001c4d3  jnz     short loc_18001C4A9
0x18001c4d5  mov     rcx, [rdi]
0x18001c4d8  mov     rdx, 4EC4EC4EC4EC4EC5h
0x18001c4e2  mov     rax, [rdi+10h]
0x18001c4e6  sub     rax, rcx
0x18001c4e9  sar     rax, 3
0x18001c4ed  imul    rax, rdx
0x18001c4f1  imul    rdx, rax, 68h ; 'h'; unsigned __int64
0x18001c4f5  cmp     rdx, 1000h
0x18001c4fc  jb      short loc_18001C51C
0x18001c4fe  mov     rax, [rcx-8]
0x18001c502  sub     rcx, rax
0x18001c505  sub     rcx, 8
0x18001c509  cmp     rcx, 1Fh
0x18001c50d  ja      short loc_18001C515
0x18001c50f  add     rdx, 27h ; '''
0x18001c513  jmp     short loc_18001C51F
0x18001c515  mov     ecx, 5
0x18001c51a  int     29h; Win8: RtlFailFast(ecx)
0x18001c51c  mov     rax, rcx
0x18001c51f  mov     rcx, rax; void *
0x18001c522  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c527  mov     [rdi], rbx
0x18001c52a  lea     rcx, [rsp+98h+var_78]
0x18001c52f  imul    rax, r12, 68h ; 'h'
0x18001c533  add     rax, rbx
0x18001c536  mov     [rdi+8], rax
0x18001c53a  lea     rax, [r14+rbx]
0x18001c53e  mov     [rdi+10h], rax
0x18001c542  call    ??1_Reallocation_guard@?$vector@URegistryHiveStack@Definition@Containers@Schema@@V?$allocator@URegistryHiveStack@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::RegistryHiveStack>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001c547  imul    rax, r13, 68h ; 'h'
0x18001c54b  add     rax, rbx
0x18001c54e  add     rsp, 58h
0x18001c552  pop     r15
0x18001c554  pop     r14
0x18001c556  pop     r13
0x18001c558  pop     r12
0x18001c55a  pop     rdi
0x18001c55b  pop     rsi
0x18001c55c  pop     rbp
0x18001c55d  pop     rbx
0x18001c55e  retn
0x18001c560  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001c566  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
