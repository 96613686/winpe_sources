# std::vector<Schema::Containers::Definition::RegistryLayer,std::allocator<Schema::Containers::Definition::RegistryLayer>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryLayer * const)

- ea: `0x18001c574`
- end: `0x18001c7de`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryLayer@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180016050`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001c574`
- `0x18001e0b8`
- `0x18001ef10`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistryLayer>::_Emplace_reallocate<>(
        void **a1,
        _BYTE *a2)
{
  _BYTE *v2; // r15
  __int64 v4; // rbp
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  size_t v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  char *v13; // rbx
  void *v14; // rax
  __int64 v15; // r12
  char *v16; // rcx
  char *v17; // r15
  char *v18; // r8
  _BYTE *v19; // rdx
  void *v20; // rcx
  char *v21; // rbp
  char *v22; // r15
  char *v23; // rcx
  _BYTE *v24; // rax
  _QWORD v26[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v27; // [rsp+38h] [rbp-60h]
  char *v28; // [rsp+40h] [rbp-58h]

  v2 = *a1;
  v4 = 0x2AAAAAAAAAAAAAALL;
  v6 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 5);
  if ( v6 == 0x2AAAAAAAAAAAAAALL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v7 = v6 + 1;
  v8 = 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)a1[2] - v2) >> 5);
  if ( v8 <= 0x2AAAAAAAAAAAAAALL - (v8 >> 1) )
  {
    v11 = v8 + (v8 >> 1);
    v12 = v7;
    if ( v11 >= v7 )
      v12 = v11;
    if ( v12 > 0x2AAAAAAAAAAAAAALL )
      goto LABEL_27;
    v4 = v12;
    v9 = 96 * v12;
    if ( !(96 * v12) )
    {
      v13 = 0;
      goto LABEL_14;
    }
    if ( v9 < 0x1000 )
    {
      v13 = (char *)operator new(96 * v12);
      goto LABEL_14;
    }
    v10 = v9 + 39;
    if ( v9 + 39 < v9 )
LABEL_27:
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v9 = -64;
    v10 = -25;
  }
  v14 = operator new(v10);
  if ( !v14 )
    goto LABEL_22;
  v13 = (char *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *((_QWORD *)v13 - 1) = v14;
LABEL_14:
  v26[0] = a1;
  v26[2] = v4;
  v15 = (a2 - v2) / 96;
  v16 = &v13[96 * v15];
  v27 = v16;
  *(_WORD *)(v16 + 85) = 0;
  v17 = v16 + 96;
  v16[87] = 0;
  *(_OWORD *)v16 = 0;
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 7;
  *(_WORD *)v16 = 0;
  *((_OWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 7;
  *((_WORD *)v16 + 16) = 0;
  *((_OWORD *)v16 + 4) = 0;
  v16[84] = 0;
  *((_QWORD *)v16 + 11) = 0;
  v18 = v13;
  *((_DWORD *)v16 + 20) = 0;
  v19 = a1[1];
  v20 = *a1;
  v28 = v17;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryLayer *>(v20, a2, v13);
    v19 = a1[1];
    v18 = v17;
    v20 = a2;
    v27 = v13;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::RegistryLayer *>(v20, v19, v18);
  v21 = (char *)*a1;
  v26[1] = 0;
  if ( v21 )
  {
    v22 = (char *)a1[1];
    while ( v21 != v22 )
    {
      std::wstring::~wstring(v21 + 32);
      std::wstring::~wstring(v21);
      v21 += 96;
    }
    v23 = (char *)*a1;
    if ( (unsigned __int64)(32 * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 5)) < 0x1000 )
    {
      v24 = *a1;
    }
    else
    {
      v24 = (_BYTE *)*((_QWORD *)v23 - 1);
      if ( (unsigned __int64)(v23 - v24 - 8) > 0x1F )
LABEL_22:
        __fastfail(5u);
    }
    operator delete(v24);
  }
  *a1 = v13;
  a1[1] = &v13[96 * v7];
  a1[2] = &v13[v9];
  std::vector<Schema::Containers::Definition::RegistryLayer>::_Reallocation_guard::~_Reallocation_guard(v26);
  return &v13[96 * v15];
}

```

## disassembly

```asm
0x18001c574  push    rbx
0x18001c576  push    rbp
0x18001c577  push    rsi
0x18001c578  push    rdi
0x18001c579  push    r12
0x18001c57b  push    r13
0x18001c57d  push    r14
0x18001c57f  push    r15
0x18001c581  sub     rsp, 58h
0x18001c585  mov     r15, [rcx]
0x18001c588  mov     r13, rdx
0x18001c58b  mov     rax, [rcx+8]
0x18001c58f  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001c599  sub     rax, r15
0x18001c59c  mov     rbp, 2AAAAAAAAAAAAAAh
0x18001c5a6  sar     rax, 5
0x18001c5aa  mov     rdi, rcx
0x18001c5ad  imul    rax, rdx
0x18001c5b1  cmp     rax, rbp
0x18001c5b4  jz      loc_18001C7D2
0x18001c5ba  mov     rcx, [rcx+10h]
0x18001c5be  lea     r14, [rax+1]
0x18001c5c2  sub     rcx, r15
0x18001c5c5  mov     rax, rbp
0x18001c5c8  sar     rcx, 5
0x18001c5cc  xor     r8d, r8d
0x18001c5cf  imul    rcx, rdx
0x18001c5d3  mov     rdx, rcx
0x18001c5d6  shr     rdx, 1
0x18001c5d9  sub     rax, rdx
0x18001c5dc  cmp     rcx, rax
0x18001c5df  jbe     short loc_18001C5EB
0x18001c5e1  lea     rsi, [r8-40h]
0x18001c5e5  lea     rcx, [rsi+27h]
0x18001c5e9  jmp     short loc_18001C62D
0x18001c5eb  lea     rax, [rcx+rdx]
0x18001c5ef  mov     rcx, r14
0x18001c5f2  cmp     rax, r14
0x18001c5f5  cmovnb  rcx, rax
0x18001c5f9  cmp     rcx, rbp
0x18001c5fc  ja      loc_18001C7D8
0x18001c602  lea     rsi, [rcx+rcx*2]
0x18001c606  mov     rbp, rcx
0x18001c609  shl     rsi, 5
0x18001c60d  test    rsi, rsi
0x18001c610  jnz     short loc_18001C617
0x18001c612  mov     rbx, r8
0x18001c615  jmp     short loc_18001C65A
0x18001c617  cmp     rsi, 1000h
0x18001c61e  jb      short loc_18001C64C
0x18001c620  lea     rcx, [rsi+27h]; Size
0x18001c624  cmp     rcx, rsi
0x18001c627  jbe     loc_18001C7D8
0x18001c62d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c632  xor     r8d, r8d
0x18001c635  test    rax, rax
0x18001c638  jz      loc_18001C77F
0x18001c63e  lea     rbx, [rax+27h]
0x18001c642  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001c646  mov     [rbx-8], rax
0x18001c64a  jmp     short loc_18001C65A
0x18001c64c  mov     rcx, rsi; Size
0x18001c64f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c654  mov     rbx, rax
0x18001c657  xor     r8d, r8d
0x18001c65a  xorps   xmm0, xmm0
0x18001c65d  mov     [rsp+98h+var_78], rdi
0x18001c662  mov     rcx, r13
0x18001c665  mov     [rsp+98h+var_68], rbp
0x18001c66a  sub     rcx, r15
0x18001c66d  mov     rax, 2AAAAAAAAAAAAAABh
0x18001c677  imul    rcx
0x18001c67a  xor     eax, eax
0x18001c67c  mov     r12, rdx
0x18001c67f  sar     r12, 4
0x18001c683  mov     rcx, r12
0x18001c686  shr     rcx, 3Fh
0x18001c68a  lea     edx, [rax+7]
0x18001c68d  add     r12, rcx
0x18001c690  lea     rcx, [r12+r12*2]
0x18001c694  shl     rcx, 5
0x18001c698  add     rcx, rbx
0x18001c69b  mov     [rsp+98h+var_60], rcx
0x18001c6a0  mov     [rcx+55h], ax
0x18001c6a4  lea     r15, [rcx+60h]
0x18001c6a8  mov     [rcx+57h], al
0x18001c6ab  movups  xmmword ptr [rcx], xmm0
0x18001c6ae  mov     [rcx+10h], r8
0x18001c6b2  mov     [rcx+18h], rdx
0x18001c6b6  mov     [rcx], r8w
0x18001c6ba  movups  xmmword ptr [rcx+20h], xmm0
0x18001c6be  mov     [rcx+30h], r8
0x18001c6c2  mov     [rcx+38h], rdx
0x18001c6c6  mov     [rcx+20h], r8w
0x18001c6cb  movups  xmmword ptr [rcx+40h], xmm0
0x18001c6cf  mov     [rcx+54h], r8b
0x18001c6d3  mov     [rcx+58h], r8
0x18001c6d7  mov     r8, rbx
0x18001c6da  mov     [rcx+50h], eax
0x18001c6dd  mov     rdx, [rdi+8]
0x18001c6e1  mov     rcx, [rdi]
0x18001c6e4  mov     [rsp+98h+var_58], r15
0x18001c6e9  cmp     r13, rdx
0x18001c6ec  jz      short loc_18001C705
0x18001c6ee  mov     rdx, r13
0x18001c6f1  call    ??$_Uninitialized_move@PEAURegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryLayer@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryLayer@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryLayer *>(Schema::Containers::Definition::RegistryLayer * const,Schema::Containers::Definition::RegistryLayer * const,Schema::Containers::Definition::RegistryLayer *,std::allocator<Schema::Containers::Definition::RegistryLayer> &)
0x18001c6f6  mov     rdx, [rdi+8]
0x18001c6fa  mov     r8, r15
0x18001c6fd  mov     rcx, r13
0x18001c700  mov     [rsp+98h+var_60], rbx
0x18001c705  call    ??$_Uninitialized_move@PEAURegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryLayer@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryLayer@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryLayer *>(Schema::Containers::Definition::RegistryLayer * const,Schema::Containers::Definition::RegistryLayer * const,Schema::Containers::Definition::RegistryLayer *,std::allocator<Schema::Containers::Definition::RegistryLayer> &)
0x18001c70a  mov     rbp, [rdi]
0x18001c70d  mov     [rsp+98h+var_70], 0
0x18001c716  test    rbp, rbp
0x18001c719  jz      short loc_18001C791
0x18001c71b  mov     r15, [rdi+8]
0x18001c71f  jmp     short loc_18001C736
0x18001c721  lea     rcx, [rbp+20h]
0x18001c725  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c72a  mov     rcx, rbp
0x18001c72d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c732  add     rbp, 60h ; '`'
0x18001c736  cmp     rbp, r15
0x18001c739  jnz     short loc_18001C721
0x18001c73b  mov     rcx, [rdi]
0x18001c73e  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18001c748  mov     rax, [rdi+10h]
0x18001c74c  sub     rax, rcx
0x18001c74f  sar     rax, 5
0x18001c753  imul    rax, rdx
0x18001c757  lea     rdx, [rax+rax*2]
0x18001c75b  shl     rdx, 5; unsigned __int64
0x18001c75f  cmp     rdx, 1000h
0x18001c766  jb      short loc_18001C786
0x18001c768  mov     rax, [rcx-8]
0x18001c76c  sub     rcx, rax
0x18001c76f  sub     rcx, 8
0x18001c773  cmp     rcx, 1Fh
0x18001c777  ja      short loc_18001C77F
0x18001c779  add     rdx, 27h ; '''
0x18001c77d  jmp     short loc_18001C789
0x18001c77f  mov     ecx, 5
0x18001c784  int     29h; Win8: RtlFailFast(ecx)
0x18001c786  mov     rax, rcx
0x18001c789  mov     rcx, rax; void *
0x18001c78c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c791  mov     [rdi], rbx
0x18001c794  lea     rax, [r14+r14*2]
0x18001c798  shl     rax, 5
0x18001c79c  lea     rcx, [rsp+98h+var_78]
0x18001c7a1  add     rax, rbx
0x18001c7a4  mov     [rdi+8], rax
0x18001c7a8  lea     rax, [rsi+rbx]
0x18001c7ac  mov     [rdi+10h], rax
0x18001c7b0  call    ??1_Reallocation_guard@?$vector@URegistryLayer@Definition@Containers@Schema@@V?$allocator@URegistryLayer@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::RegistryLayer>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001c7b5  lea     rax, [r12+r12*2]
0x18001c7b9  shl     rax, 5
0x18001c7bd  add     rax, rbx
0x18001c7c0  add     rsp, 58h
0x18001c7c4  pop     r15
0x18001c7c6  pop     r14
0x18001c7c8  pop     r13
0x18001c7ca  pop     r12
0x18001c7cc  pop     rdi
0x18001c7cd  pop     rsi
0x18001c7ce  pop     rbp
0x18001c7cf  pop     rbx
0x18001c7d0  retn
0x18001c7d2  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001c7d8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
