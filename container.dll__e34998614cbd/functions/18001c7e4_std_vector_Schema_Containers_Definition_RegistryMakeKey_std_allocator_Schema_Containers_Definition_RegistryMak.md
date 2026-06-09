# std::vector<Schema::Containers::Definition::RegistryMakeKey,std::allocator<Schema::Containers::Definition::RegistryMakeKey>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryMakeKey * const)

- ea: `0x18001c7e4`
- end: `0x18001ca58`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryMakeKey@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180016110`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001c7e4`
- `0x18001e19c`
- `0x18001efa8`
- `0x180021d98`
- `0x180021e68`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Emplace_reallocate<>(
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
  char **v19; // rsi
  char **v20; // rbp
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
  *(_DWORD *)(v14 + 113) = 0;
  v15 = v14 + 120;
  *(_WORD *)(v14 + 117) = 0;
  v14[119] = 0;
  *(_OWORD *)v14 = 0;
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 7;
  *(_WORD *)v14 = 0;
  *((_OWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 7) = 7;
  *((_WORD *)v14 + 16) = 0;
  *((_QWORD *)v14 + 8) = 0;
  *((_QWORD *)v14 + 9) = 0;
  *((_QWORD *)v14 + 10) = 0;
  *((_QWORD *)v14 + 11) = 0;
  *((_QWORD *)v14 + 12) = 0;
  *((_QWORD *)v14 + 13) = 0;
  v14[112] = 0;
  v16 = v11;
  v17 = a1[1];
  v18 = *a1;
  v26 = v15;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeKey *>(v18, a2, v11);
    v17 = a1[1];
    v16 = v15;
    v18 = a2;
    v25 = v11;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeKey *>(v18, v17, v16);
  v19 = (char **)*a1;
  v24[1] = 0;
  if ( v19 )
  {
    v20 = (char **)a1[1];
    while ( v19 != v20 )
    {
      std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Tidy(v19 + 11);
      std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(v19 + 8);
      std::wstring::~wstring(v19 + 4);
      std::wstring::~wstring(v19);
      v19 += 15;
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
  std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Reallocation_guard::~_Reallocation_guard(v24);
  return &v11[120 * v13];
}

```

## disassembly

```asm
0x18001c7e4  push    rbx
0x18001c7e6  push    rbp
0x18001c7e7  push    rsi
0x18001c7e8  push    rdi
0x18001c7e9  push    r12
0x18001c7eb  push    r13
0x18001c7ed  push    r14
0x18001c7ef  push    r15
0x18001c7f1  sub     rsp, 58h
0x18001c7f5  mov     rbp, [rcx]
0x18001c7f8  mov     rax, 0EEEEEEEEEEEEEEEFh
0x18001c802  mov     r8, [rcx+8]
0x18001c806  mov     r9, 222222222222222h
0x18001c810  sub     r8, rbp
0x18001c813  mov     r12, rdx
0x18001c816  sar     r8, 3
0x18001c81a  mov     rdi, rcx
0x18001c81d  imul    r8, rax
0x18001c821  cmp     r8, r9
0x18001c824  jz      loc_18001CA4C
0x18001c82a  mov     rcx, [rcx+10h]
0x18001c82e  sub     rcx, rbp
0x18001c831  sar     rcx, 3
0x18001c835  imul    rcx, rax
0x18001c839  mov     rax, r9
0x18001c83c  mov     rdx, rcx
0x18001c83f  shr     rdx, 1
0x18001c842  sub     rax, rdx
0x18001c845  cmp     rcx, rax
0x18001c848  ja      loc_18001CA52
0x18001c84e  lea     r15, [r8+1]
0x18001c852  lea     rax, [rcx+rdx]
0x18001c856  mov     rsi, r15
0x18001c859  cmp     rax, r15
0x18001c85c  cmovnb  rsi, rax
0x18001c860  cmp     rsi, r9
0x18001c863  ja      loc_18001CA52
0x18001c869  imul    r14, rsi, 78h ; 'x'
0x18001c86d  xor     r8d, r8d
0x18001c870  test    r14, r14
0x18001c873  jnz     short loc_18001C87A
0x18001c875  mov     ebx, r8d
0x18001c878  jmp     short loc_18001C8BD
0x18001c87a  cmp     r14, 1000h
0x18001c881  jb      short loc_18001C8AF
0x18001c883  lea     rcx, [r14+27h]; Size
0x18001c887  cmp     rcx, r14
0x18001c88a  jbe     loc_18001CA52
0x18001c890  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c895  xor     r8d, r8d
0x18001c898  test    rax, rax
0x18001c89b  jz      loc_18001CA01
0x18001c8a1  lea     rbx, [rax+27h]
0x18001c8a5  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001c8a9  mov     [rbx-8], rax
0x18001c8ad  jmp     short loc_18001C8BD
0x18001c8af  mov     rcx, r14; Size
0x18001c8b2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c8b7  mov     rbx, rax
0x18001c8ba  xor     r8d, r8d
0x18001c8bd  mov     rcx, r12
0x18001c8c0  mov     [rsp+98h+var_78], rdi
0x18001c8c5  sub     rcx, rbp
0x18001c8c8  mov     [rsp+98h+var_68], rsi
0x18001c8cd  mov     rax, 8888888888888889h
0x18001c8d7  xorps   xmm0, xmm0
0x18001c8da  imul    rcx
0x18001c8dd  xor     eax, eax
0x18001c8df  lea     r13, [rcx+rdx]
0x18001c8e3  sar     r13, 6
0x18001c8e7  lea     edx, [rax+7]
0x18001c8ea  mov     rcx, r13
0x18001c8ed  shr     rcx, 3Fh
0x18001c8f1  add     r13, rcx
0x18001c8f4  imul    rcx, r13, 78h ; 'x'
0x18001c8f8  add     rcx, rbx
0x18001c8fb  mov     [rsp+98h+var_60], rcx
0x18001c900  mov     [rcx+71h], eax
0x18001c903  lea     rbp, [rcx+78h]
0x18001c907  mov     [rcx+75h], ax
0x18001c90b  mov     [rcx+77h], al
0x18001c90e  movups  xmmword ptr [rcx], xmm0
0x18001c911  mov     [rcx+10h], r8
0x18001c915  mov     [rcx+18h], rdx
0x18001c919  mov     [rcx], r8w
0x18001c91d  movups  xmmword ptr [rcx+20h], xmm0
0x18001c921  mov     [rcx+30h], r8
0x18001c925  mov     [rcx+38h], rdx
0x18001c929  mov     [rcx+20h], r8w
0x18001c92e  mov     [rcx+40h], r8
0x18001c932  mov     [rcx+48h], r8
0x18001c936  mov     [rcx+50h], r8
0x18001c93a  mov     [rcx+58h], r8
0x18001c93e  mov     [rcx+60h], r8
0x18001c942  mov     [rcx+68h], r8
0x18001c946  mov     [rcx+70h], r8b
0x18001c94a  mov     r8, rbx
0x18001c94d  mov     rdx, [rdi+8]
0x18001c951  mov     rcx, [rdi]
0x18001c954  mov     [rsp+98h+var_58], rbp
0x18001c959  cmp     r12, rdx
0x18001c95c  jz      short loc_18001C975
0x18001c95e  mov     rdx, r12
0x18001c961  call    ??$_Uninitialized_move@PEAURegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeKey@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeKey *>(Schema::Containers::Definition::RegistryMakeKey * const,Schema::Containers::Definition::RegistryMakeKey * const,Schema::Containers::Definition::RegistryMakeKey *,std::allocator<Schema::Containers::Definition::RegistryMakeKey> &)
0x18001c966  mov     rdx, [rdi+8]
0x18001c96a  mov     r8, rbp
0x18001c96d  mov     rcx, r12
0x18001c970  mov     [rsp+98h+var_60], rbx
0x18001c975  call    ??$_Uninitialized_move@PEAURegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeKey@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeKey *>(Schema::Containers::Definition::RegistryMakeKey * const,Schema::Containers::Definition::RegistryMakeKey * const,Schema::Containers::Definition::RegistryMakeKey *,std::allocator<Schema::Containers::Definition::RegistryMakeKey> &)
0x18001c97a  mov     rsi, [rdi]
0x18001c97d  mov     [rsp+98h+var_70], 0
0x18001c986  test    rsi, rsi
0x18001c989  jz      loc_18001CA13
0x18001c98f  mov     rbp, [rdi+8]
0x18001c993  jmp     short loc_18001C9BC
0x18001c995  lea     rcx, [rsi+58h]
0x18001c999  call    ?_Tidy@?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Tidy(void)
0x18001c99e  lea     rcx, [rsi+40h]
0x18001c9a2  call    ?_Tidy@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Tidy(void)
0x18001c9a7  lea     rcx, [rsi+20h]
0x18001c9ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c9b0  mov     rcx, rsi
0x18001c9b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c9b8  add     rsi, 78h ; 'x'
0x18001c9bc  cmp     rsi, rbp
0x18001c9bf  jnz     short loc_18001C995
0x18001c9c1  mov     rcx, [rdi]
0x18001c9c4  mov     rdx, 0EEEEEEEEEEEEEEEFh
0x18001c9ce  mov     rax, [rdi+10h]
0x18001c9d2  sub     rax, rcx
0x18001c9d5  sar     rax, 3
0x18001c9d9  imul    rax, rdx
0x18001c9dd  imul    rdx, rax, 78h ; 'x'; unsigned __int64
0x18001c9e1  cmp     rdx, 1000h
0x18001c9e8  jb      short loc_18001CA08
0x18001c9ea  mov     rax, [rcx-8]
0x18001c9ee  sub     rcx, rax
0x18001c9f1  sub     rcx, 8
0x18001c9f5  cmp     rcx, 1Fh
0x18001c9f9  ja      short loc_18001CA01
0x18001c9fb  add     rdx, 27h ; '''
0x18001c9ff  jmp     short loc_18001CA0B
0x18001ca01  mov     ecx, 5
0x18001ca06  int     29h; Win8: RtlFailFast(ecx)
0x18001ca08  mov     rax, rcx
0x18001ca0b  mov     rcx, rax; void *
0x18001ca0e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca13  mov     [rdi], rbx
0x18001ca16  lea     rcx, [rsp+98h+var_78]
0x18001ca1b  imul    rax, r15, 78h ; 'x'
0x18001ca1f  add     rax, rbx
0x18001ca22  mov     [rdi+8], rax
0x18001ca26  lea     rax, [r14+rbx]
0x18001ca2a  mov     [rdi+10h], rax
0x18001ca2e  call    ??1_Reallocation_guard@?$vector@URegistryMakeKey@Definition@Containers@Schema@@V?$allocator@URegistryMakeKey@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::RegistryMakeKey>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001ca33  imul    rax, r13, 78h ; 'x'
0x18001ca37  add     rax, rbx
0x18001ca3a  add     rsp, 58h
0x18001ca3e  pop     r15
0x18001ca40  pop     r14
0x18001ca42  pop     r13
0x18001ca44  pop     r12
0x18001ca46  pop     rdi
0x18001ca47  pop     rsi
0x18001ca48  pop     rbp
0x18001ca49  pop     rbx
0x18001ca4a  retn
0x18001ca4c  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001ca52  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
