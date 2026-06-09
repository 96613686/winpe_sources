# std::vector<Schema::Containers::Definition::RegistryDeleteKey,std::allocator<Schema::Containers::Definition::RegistryDeleteKey>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryDeleteKey * const)

- ea: `0x18001c08c`
- end: `0x18001c30e`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryDeleteKey@Definition@Containers@Schema@@V?$allocator@URegistryDeleteKey@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryDeleteKey@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180015ed0`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001c08c`
- `0x18001ede8`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistryDeleteKey>::_Emplace_reallocate<>(
        void **a1,
        char *a2)
{
  _BYTE *v2; // r13
  __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // r12
  unsigned __int64 v9; // rbp
  __int64 v10; // r9
  unsigned __int64 v11; // r14
  char *v12; // rbx
  void *v13; // rax
  __int64 v14; // rsi
  char *v15; // rdx
  char *v16; // rax
  char *v17; // rdx
  char *v18; // r8
  char *v19; // rcx
  __int64 v20; // rsi
  char *v21; // rcx
  char *v22; // rbp
  char *v23; // r15
  char *v24; // rax
  _BYTE *v25; // rcx
  _QWORD v27[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v28; // [rsp+38h] [rbp-60h]
  char *v29; // [rsp+40h] [rbp-58h]

  v2 = *a1;
  v5 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 5;
  if ( v5 == 0x7FFFFFFFFFFFFFFLL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v6 = ((_BYTE *)a1[2] - v2) >> 5;
  v7 = v6 >> 1;
  if ( v6 > 0x7FFFFFFFFFFFFFFLL - (v6 >> 1) )
    goto LABEL_34;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x7FFFFFFFFFFFFFFLL )
    goto LABEL_34;
  v10 = 0;
  v11 = 32 * v9;
  if ( !(32 * v9) )
  {
    v12 = 0;
    goto LABEL_13;
  }
  if ( v11 < 0x1000 )
  {
    v12 = (char *)operator new(32 * v9);
    v10 = 0;
    goto LABEL_13;
  }
  if ( v11 + 39 < v11 )
LABEL_34:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  v10 = 0;
  if ( !v13 )
    goto LABEL_29;
  v12 = (char *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v12 - 1) = v13;
LABEL_13:
  v27[0] = a1;
  v27[2] = v9;
  v14 = (a2 - v2) >> 5;
  v15 = &v12[32 * v14];
  v28 = v15;
  *(_OWORD *)v15 = 0;
  *((_QWORD *)v15 + 2) = 0;
  v16 = v15 + 32;
  *((_QWORD *)v15 + 3) = 7;
  *(_WORD *)v15 = 0;
  v17 = v12;
  v18 = (char *)a1[1];
  v19 = (char *)*a1;
  v29 = v16;
  if ( a2 == v18 )
  {
    while ( v19 != v18 )
    {
      *(_OWORD *)v17 = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *(_OWORD *)v17 = *(_OWORD *)v19;
      v17 += 32;
      *((_OWORD *)v17 - 1) = *((_OWORD *)v19 + 1);
      *((_QWORD *)v19 + 2) = 0;
      *((_QWORD *)v19 + 3) = 7;
      *(_WORD *)v19 = 0;
      v19 += 32;
    }
    v20 = 32 * v14;
  }
  else
  {
    while ( v19 != a2 )
    {
      *(_OWORD *)v17 = 0;
      *((_QWORD *)v17 + 2) = 0;
      *((_QWORD *)v17 + 3) = 0;
      *(_OWORD *)v17 = *(_OWORD *)v19;
      v17 += 32;
      *((_OWORD *)v17 - 1) = *((_OWORD *)v19 + 1);
      *((_QWORD *)v19 + 2) = 0;
      *((_QWORD *)v19 + 3) = 7;
      *(_WORD *)v19 = 0;
      v19 += 32;
    }
    v17 = (char *)a1[1];
    v20 = 32 * v14;
    v28 = v12;
    v21 = &v12[v20 + 32];
    while ( a2 != v17 )
    {
      *(_OWORD *)v21 = 0;
      *((_QWORD *)v21 + 2) = 0;
      *((_QWORD *)v21 + 3) = 0;
      *(_OWORD *)v21 = *(_OWORD *)a2;
      v21 += 32;
      *((_OWORD *)v21 - 1) = *((_OWORD *)a2 + 1);
      *((_QWORD *)a2 + 2) = 0;
      *((_QWORD *)a2 + 3) = 7;
      *(_WORD *)a2 = 0;
      a2 += 32;
    }
  }
  v22 = (char *)*a1;
  v27[1] = 0;
  if ( v22 )
  {
    v23 = (char *)a1[1];
    while ( v22 != v23 )
    {
      std::wstring::~wstring(v22);
      v22 += 32;
    }
    v24 = (char *)*a1;
    if ( (((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFE0uLL) < 0x1000 )
    {
      v25 = *a1;
    }
    else
    {
      v25 = (_BYTE *)*((_QWORD *)v24 - 1);
      if ( (unsigned __int64)(v24 - v25 - 8) > 0x1F )
LABEL_29:
        __fastfail(5u);
    }
    operator delete(v25);
  }
  *a1 = v12;
  a1[1] = &v12[32 * v8];
  a1[2] = &v12[v11];
  ((void (__fastcall *)(_QWORD *, char *, char *, __int64))std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard)(
    v27,
    v17,
    v18,
    v10);
  return &v12[v20];
}

```

## disassembly

```asm
0x18001c08c  push    rbx
0x18001c08e  push    rbp
0x18001c08f  push    rsi
0x18001c090  push    rdi
0x18001c091  push    r12
0x18001c093  push    r13
0x18001c095  push    r14
0x18001c097  push    r15
0x18001c099  sub     rsp, 58h
0x18001c09d  mov     r13, [rcx]
0x18001c0a0  mov     r9, 7FFFFFFFFFFFFFFh
0x18001c0aa  mov     r8, [rcx+8]
0x18001c0ae  mov     r15, rdx
0x18001c0b1  sub     r8, r13
0x18001c0b4  mov     rdi, rcx
0x18001c0b7  sar     r8, 5
0x18001c0bb  cmp     r8, r9
0x18001c0be  jz      loc_18001C302
0x18001c0c4  mov     rcx, [rcx+10h]
0x18001c0c8  mov     rax, r9
0x18001c0cb  sub     rcx, r13
0x18001c0ce  sar     rcx, 5
0x18001c0d2  mov     rdx, rcx
0x18001c0d5  shr     rdx, 1
0x18001c0d8  sub     rax, rdx
0x18001c0db  cmp     rcx, rax
0x18001c0de  ja      loc_18001C308
0x18001c0e4  lea     r12, [r8+1]
0x18001c0e8  lea     rax, [rcx+rdx]
0x18001c0ec  mov     rbp, r12
0x18001c0ef  cmp     rax, r12
0x18001c0f2  cmovnb  rbp, rax
0x18001c0f6  cmp     rbp, r9
0x18001c0f9  ja      loc_18001C308
0x18001c0ff  mov     r14, rbp
0x18001c102  xor     r9d, r9d
0x18001c105  shl     r14, 5
0x18001c109  test    r14, r14
0x18001c10c  jnz     short loc_18001C113
0x18001c10e  mov     ebx, r9d
0x18001c111  jmp     short loc_18001C156
0x18001c113  cmp     r14, 1000h
0x18001c11a  jb      short loc_18001C148
0x18001c11c  lea     rcx, [r14+27h]; Size
0x18001c120  cmp     rcx, r14
0x18001c123  jbe     loc_18001C308
0x18001c129  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c12e  xor     r9d, r9d
0x18001c131  test    rax, rax
0x18001c134  jz      loc_18001C2BD
0x18001c13a  lea     rbx, [rax+27h]
0x18001c13e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001c142  mov     [rbx-8], rax
0x18001c146  jmp     short loc_18001C156
0x18001c148  mov     rcx, r14; Size
0x18001c14b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c150  mov     rbx, rax
0x18001c153  xor     r9d, r9d
0x18001c156  mov     rsi, r15
0x18001c159  mov     [rsp+98h+var_78], rdi
0x18001c15e  sub     rsi, r13
0x18001c161  mov     [rsp+98h+var_68], rbp
0x18001c166  sar     rsi, 5
0x18001c16a  xorps   xmm0, xmm0
0x18001c16d  mov     rdx, rsi
0x18001c170  mov     r10d, 7
0x18001c176  shl     rdx, 5
0x18001c17a  add     rdx, rbx
0x18001c17d  mov     [rsp+98h+var_60], rdx
0x18001c182  movups  xmmword ptr [rdx], xmm0
0x18001c185  mov     [rdx+10h], r9
0x18001c189  lea     rax, [rdx+20h]
0x18001c18d  mov     [rdx+18h], r10
0x18001c191  mov     [rdx], r9w
0x18001c195  mov     rdx, rbx
0x18001c198  mov     r8, [rdi+8]
0x18001c19c  mov     rcx, [rdi]
0x18001c19f  mov     [rsp+98h+var_58], rax
0x18001c1a4  cmp     r15, r8
0x18001c1a7  jnz     short loc_18001C219
0x18001c1a9  jmp     short loc_18001C1DB
0x18001c1ab  xorps   xmm0, xmm0
0x18001c1ae  movups  xmmword ptr [rdx], xmm0
0x18001c1b1  mov     [rdx+10h], r9
0x18001c1b5  mov     [rdx+18h], r9
0x18001c1b9  movups  xmm0, xmmword ptr [rcx]
0x18001c1bc  movups  xmmword ptr [rdx], xmm0
0x18001c1bf  lea     rdx, [rdx+20h]
0x18001c1c3  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c1c7  movups  xmmword ptr [rdx-10h], xmm1
0x18001c1cb  mov     [rcx+10h], r9
0x18001c1cf  mov     [rcx+18h], r10
0x18001c1d3  mov     [rcx], r9w
0x18001c1d7  add     rcx, 20h ; ' '
0x18001c1db  cmp     rcx, r8
0x18001c1de  jnz     short loc_18001C1AB
0x18001c1e0  shl     rsi, 5
0x18001c1e4  jmp     loc_18001C26B
0x18001c1e9  xorps   xmm0, xmm0
0x18001c1ec  movups  xmmword ptr [rdx], xmm0
0x18001c1ef  mov     [rdx+10h], r9
0x18001c1f3  mov     [rdx+18h], r9
0x18001c1f7  movups  xmm0, xmmword ptr [rcx]
0x18001c1fa  movups  xmmword ptr [rdx], xmm0
0x18001c1fd  lea     rdx, [rdx+20h]
0x18001c201  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c205  movups  xmmword ptr [rdx-10h], xmm1
0x18001c209  mov     [rcx+10h], r9
0x18001c20d  mov     [rcx+18h], r10
0x18001c211  mov     [rcx], r9w
0x18001c215  add     rcx, 20h ; ' '
0x18001c219  cmp     rcx, r15
0x18001c21c  jnz     short loc_18001C1E9
0x18001c21e  mov     rdx, [rdi+8]
0x18001c222  shl     rsi, 5
0x18001c226  mov     [rsp+98h+var_60], rbx
0x18001c22b  lea     rcx, [rsi+20h]
0x18001c22f  add     rcx, rbx
0x18001c232  jmp     short loc_18001C266
0x18001c234  xorps   xmm0, xmm0
0x18001c237  movups  xmmword ptr [rcx], xmm0
0x18001c23a  mov     [rcx+10h], r9
0x18001c23e  mov     [rcx+18h], r9
0x18001c242  movups  xmm0, xmmword ptr [r15]
0x18001c246  movups  xmmword ptr [rcx], xmm0
0x18001c249  lea     rcx, [rcx+20h]
0x18001c24d  movups  xmm1, xmmword ptr [r15+10h]
0x18001c252  movups  xmmword ptr [rcx-10h], xmm1
0x18001c256  mov     [r15+10h], r9
0x18001c25a  mov     [r15+18h], r10
0x18001c25e  mov     [r15], r9w
0x18001c262  add     r15, 20h ; ' '
0x18001c266  cmp     r15, rdx
0x18001c269  jnz     short loc_18001C234
0x18001c26b  mov     rbp, [rdi]
0x18001c26e  mov     [rsp+98h+var_70], r9
0x18001c273  test    rbp, rbp
0x18001c276  jz      short loc_18001C2CC
0x18001c278  mov     r15, [rdi+8]
0x18001c27c  jmp     short loc_18001C28A
0x18001c27e  mov     rcx, rbp
0x18001c281  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c286  add     rbp, 20h ; ' '
0x18001c28a  cmp     rbp, r15
0x18001c28d  jnz     short loc_18001C27E
0x18001c28f  mov     rax, [rdi]
0x18001c292  mov     rdx, [rdi+10h]
0x18001c296  sub     rdx, rax
0x18001c299  and     rdx, 0FFFFFFFFFFFFFFE0h; unsigned __int64
0x18001c29d  cmp     rdx, 1000h
0x18001c2a4  jb      short loc_18001C2C4
0x18001c2a6  mov     rcx, [rax-8]
0x18001c2aa  sub     rax, rcx
0x18001c2ad  sub     rax, 8
0x18001c2b1  cmp     rax, 1Fh
0x18001c2b5  ja      short loc_18001C2BD
0x18001c2b7  add     rdx, 27h ; '''
0x18001c2bb  jmp     short loc_18001C2C7
0x18001c2bd  mov     ecx, 5
0x18001c2c2  int     29h; Win8: RtlFailFast(ecx)
0x18001c2c4  mov     rcx, rax; void *
0x18001c2c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c2cc  mov     [rdi], rbx
0x18001c2cf  lea     rax, [r14+rbx]
0x18001c2d3  shl     r12, 5
0x18001c2d7  lea     rcx, [rsp+98h+var_78]
0x18001c2dc  add     r12, rbx
0x18001c2df  mov     [rdi+8], r12
0x18001c2e3  mov     [rdi+10h], rax
0x18001c2e7  call    ??1_Reallocation_guard@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001c2ec  lea     rax, [rsi+rbx]
0x18001c2f0  add     rsp, 58h
0x18001c2f4  pop     r15
0x18001c2f6  pop     r14
0x18001c2f8  pop     r13
0x18001c2fa  pop     r12
0x18001c2fc  pop     rdi
0x18001c2fd  pop     rsi
0x18001c2fe  pop     rbp
0x18001c2ff  pop     rbx
0x18001c300  retn
0x18001c302  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001c308  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
