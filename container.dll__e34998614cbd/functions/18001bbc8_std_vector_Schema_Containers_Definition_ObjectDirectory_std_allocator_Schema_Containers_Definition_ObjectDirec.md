# std::vector<Schema::Containers::Definition::ObjectDirectory,std::allocator<Schema::Containers::Definition::ObjectDirectory>>::_Emplace_reallocate<>(Schema::Containers::Definition::ObjectDirectory * const)

- ea: `0x18001bbc8`
- end: `0x18001be32`
- name: `??$_Emplace_reallocate@$$V@?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@AEAAPEAUObjectDirectory@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x180015d20`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001bbc8`
- `0x18001ddc4`
- `0x18001ecb0`
- `0x1800219d0`
- `0x180021aa0`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::ObjectDirectory>::_Emplace_reallocate<>(
        void **a1,
        _BYTE *a2)
{
  _BYTE *v2; // rbp
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // r15
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
  v5 = 0xEEEEEEEEEEEEEEEFuLL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 3);
  if ( v5 == 0x222222222222222LL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v6 = 0xEEEEEEEEEEEEEEEFuLL * (((_BYTE *)a1[2] - v2) >> 3);
  v7 = v6 >> 1;
  if ( v6 > 0x222222222222222LL - (v6 >> 1) )
    goto LABEL_26;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x222222222222222LL )
    goto LABEL_26;
  v10 = 120 * v9;
  if ( !(120 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = (char *)operator new(120 * v9);
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
  v13 = (a2 - v2) / 120;
  v14 = &v11[120 * v13];
  v25 = v14;
  *((_QWORD *)v14 + 8) = 0;
  v15 = v14 + 120;
  *(_OWORD *)v14 = 0;
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 7;
  *(_WORD *)v14 = 0;
  *((_OWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 7) = 7;
  *((_WORD *)v14 + 16) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 12) = 0;
  *((_QWORD *)v14 + 13) = 0;
  *((_QWORD *)v14 + 14) = 0;
  v16 = v11;
  v17 = a1[1];
  v18 = *a1;
  v26 = v15;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::ObjectDirectory *>(v18, a2, v11);
    v17 = a1[1];
    v16 = v15;
    v18 = a2;
    v25 = v11;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::ObjectDirectory *>(v18, v17, v16);
  v19 = (char *)*a1;
  v24[1] = 0;
  if ( v19 )
  {
    v20 = (char *)a1[1];
    while ( v19 != v20 )
    {
      std::vector<Schema::Containers::Definition::ObjectDirectory>::_Tidy(v19 + 96);
      std::vector<Schema::Containers::Definition::ObjectSymlink>::_Tidy(v19 + 72);
      std::wstring::~wstring(v19 + 32);
      std::wstring::~wstring(v19);
      v19 += 120;
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
  a1[1] = &v11[120 * v8];
  a1[2] = &v11[v10];
  std::vector<Schema::Containers::Definition::ObjectDirectory>::_Reallocation_guard::~_Reallocation_guard(v24);
  return &v11[120 * v13];
}

```

## disassembly

```asm
0x18001bbc8  push    rbx
0x18001bbca  push    rbp
0x18001bbcb  push    rsi
0x18001bbcc  push    rdi
0x18001bbcd  push    r12
0x18001bbcf  push    r13
0x18001bbd1  push    r14
0x18001bbd3  push    r15
0x18001bbd5  sub     rsp, 58h
0x18001bbd9  mov     rbp, [rcx]
0x18001bbdc  mov     rax, 0EEEEEEEEEEEEEEEFh
0x18001bbe6  mov     r8, [rcx+8]
0x18001bbea  mov     r9, 222222222222222h
0x18001bbf4  sub     r8, rbp
0x18001bbf7  mov     r12, rdx
0x18001bbfa  sar     r8, 3
0x18001bbfe  mov     rdi, rcx
0x18001bc01  imul    r8, rax
0x18001bc05  cmp     r8, r9
0x18001bc08  jz      loc_18001BE26
0x18001bc0e  mov     rcx, [rcx+10h]
0x18001bc12  sub     rcx, rbp
0x18001bc15  sar     rcx, 3
0x18001bc19  imul    rcx, rax
0x18001bc1d  mov     rax, r9
0x18001bc20  mov     rdx, rcx
0x18001bc23  shr     rdx, 1
0x18001bc26  sub     rax, rdx
0x18001bc29  cmp     rcx, rax
0x18001bc2c  ja      loc_18001BE2C
0x18001bc32  lea     r15, [r8+1]
0x18001bc36  lea     rax, [rcx+rdx]
0x18001bc3a  mov     rsi, r15
0x18001bc3d  cmp     rax, r15
0x18001bc40  cmovnb  rsi, rax
0x18001bc44  cmp     rsi, r9
0x18001bc47  ja      loc_18001BE2C
0x18001bc4d  imul    r14, rsi, 78h ; 'x'
0x18001bc51  xor     r8d, r8d
0x18001bc54  test    r14, r14
0x18001bc57  jnz     short loc_18001BC5E
0x18001bc59  mov     ebx, r8d
0x18001bc5c  jmp     short loc_18001BCA1
0x18001bc5e  cmp     r14, 1000h
0x18001bc65  jb      short loc_18001BC93
0x18001bc67  lea     rcx, [r14+27h]; Size
0x18001bc6b  cmp     rcx, r14
0x18001bc6e  jbe     loc_18001BE2C
0x18001bc74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bc79  xor     r8d, r8d
0x18001bc7c  test    rax, rax
0x18001bc7f  jz      loc_18001BDDB
0x18001bc85  lea     rbx, [rax+27h]
0x18001bc89  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001bc8d  mov     [rbx-8], rax
0x18001bc91  jmp     short loc_18001BCA1
0x18001bc93  mov     rcx, r14; Size
0x18001bc96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bc9b  mov     rbx, rax
0x18001bc9e  xor     r8d, r8d
0x18001bca1  mov     rcx, r12
0x18001bca4  mov     [rsp+98h+var_78], rdi
0x18001bca9  sub     rcx, rbp
0x18001bcac  mov     [rsp+98h+var_68], rsi
0x18001bcb1  mov     rax, 8888888888888889h
0x18001bcbb  xorps   xmm0, xmm0
0x18001bcbe  imul    rcx
0x18001bcc1  xor     eax, eax
0x18001bcc3  lea     r13, [rcx+rdx]
0x18001bcc7  sar     r13, 6
0x18001bccb  lea     edx, [rax+7]
0x18001bcce  mov     rcx, r13
0x18001bcd1  shr     rcx, 3Fh
0x18001bcd5  add     r13, rcx
0x18001bcd8  imul    rcx, r13, 78h ; 'x'
0x18001bcdc  add     rcx, rbx
0x18001bcdf  mov     [rsp+98h+var_60], rcx
0x18001bce4  mov     [rcx+40h], rax
0x18001bce8  lea     rbp, [rcx+78h]
0x18001bcec  movups  xmmword ptr [rcx], xmm0
0x18001bcef  mov     [rcx+10h], r8
0x18001bcf3  mov     [rcx+18h], rdx
0x18001bcf7  mov     [rcx], r8w
0x18001bcfb  movups  xmmword ptr [rcx+20h], xmm0
0x18001bcff  mov     [rcx+30h], r8
0x18001bd03  mov     [rcx+38h], rdx
0x18001bd07  mov     [rcx+20h], r8w
0x18001bd0c  mov     [rcx+48h], r8
0x18001bd10  mov     [rcx+50h], r8
0x18001bd14  mov     [rcx+58h], r8
0x18001bd18  mov     [rcx+60h], r8
0x18001bd1c  mov     [rcx+68h], r8
0x18001bd20  mov     [rcx+70h], r8
0x18001bd24  mov     r8, rbx
0x18001bd27  mov     rdx, [rdi+8]
0x18001bd2b  mov     rcx, [rdi]
0x18001bd2e  mov     [rsp+98h+var_58], rbp
0x18001bd33  cmp     r12, rdx
0x18001bd36  jz      short loc_18001BD4F
0x18001bd38  mov     rdx, r12
0x18001bd3b  call    ??$_Uninitialized_move@PEAUObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@YAPEAUObjectDirectory@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@UObjectDirectory@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::ObjectDirectory *>(Schema::Containers::Definition::ObjectDirectory * const,Schema::Containers::Definition::ObjectDirectory * const,Schema::Containers::Definition::ObjectDirectory *,std::allocator<Schema::Containers::Definition::ObjectDirectory> &)
0x18001bd40  mov     rdx, [rdi+8]
0x18001bd44  mov     r8, rbp
0x18001bd47  mov     rcx, r12
0x18001bd4a  mov     [rsp+98h+var_60], rbx
0x18001bd4f  call    ??$_Uninitialized_move@PEAUObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@YAPEAUObjectDirectory@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@UObjectDirectory@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::ObjectDirectory *>(Schema::Containers::Definition::ObjectDirectory * const,Schema::Containers::Definition::ObjectDirectory * const,Schema::Containers::Definition::ObjectDirectory *,std::allocator<Schema::Containers::Definition::ObjectDirectory> &)
0x18001bd54  mov     rsi, [rdi]
0x18001bd57  mov     [rsp+98h+var_70], 0
0x18001bd60  test    rsi, rsi
0x18001bd63  jz      loc_18001BDED
0x18001bd69  mov     rbp, [rdi+8]
0x18001bd6d  jmp     short loc_18001BD96
0x18001bd6f  lea     rcx, [rsi+60h]
0x18001bd73  call    ?_Tidy@?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::ObjectDirectory>::_Tidy(void)
0x18001bd78  lea     rcx, [rsi+48h]
0x18001bd7c  call    ?_Tidy@?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::ObjectSymlink>::_Tidy(void)
0x18001bd81  lea     rcx, [rsi+20h]
0x18001bd85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bd8a  mov     rcx, rsi
0x18001bd8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bd92  add     rsi, 78h ; 'x'
0x18001bd96  cmp     rsi, rbp
0x18001bd99  jnz     short loc_18001BD6F
0x18001bd9b  mov     rcx, [rdi]
0x18001bd9e  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x18001bda8  mov     rax, [rdi+10h]
0x18001bdac  sub     rax, rcx
0x18001bdaf  sar     rax, 3
0x18001bdb3  imul    rax, rdx
0x18001bdb7  imul    rdx, rax, 78h ; 'x'; unsigned __int64
0x18001bdbb  cmp     rdx, 1000h
0x18001bdc2  jb      short loc_18001BDE2
0x18001bdc4  mov     rax, [rcx-8]
0x18001bdc8  sub     rcx, rax
0x18001bdcb  sub     rcx, 8
0x18001bdcf  cmp     rcx, 1Fh
0x18001bdd3  ja      short loc_18001BDDB
0x18001bdd5  add     rdx, 27h ; '''
0x18001bdd9  jmp     short loc_18001BDE5
0x18001bddb  mov     ecx, 5
0x18001bde0  int     29h; Win8: RtlFailFast(ecx)
0x18001bde2  mov     rax, rcx
0x18001bde5  mov     rcx, rax; void *
0x18001bde8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bded  mov     [rdi], rbx
0x18001bdf0  lea     rcx, [rsp+98h+var_78]
0x18001bdf5  imul    rax, r15, 78h ; 'x'
0x18001bdf9  add     rax, rbx
0x18001bdfc  mov     [rdi+8], rax
0x18001be00  lea     rax, [r14+rbx]
0x18001be04  mov     [rdi+10h], rax
0x18001be08  call    ??1_Reallocation_guard@?$vector@UObjectDirectory@Definition@Containers@Schema@@V?$allocator@UObjectDirectory@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::ObjectDirectory>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001be0d  imul    rax, r13, 78h ; 'x'
0x18001be11  add     rax, rbx
0x18001be14  add     rsp, 58h
0x18001be18  pop     r15
0x18001be1a  pop     r14
0x18001be1c  pop     r13
0x18001be1e  pop     r12
0x18001be20  pop     rdi
0x18001be21  pop     rsi
0x18001be22  pop     rbp
0x18001be23  pop     rbx
0x18001be24  retn
0x18001be26  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001be2c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
