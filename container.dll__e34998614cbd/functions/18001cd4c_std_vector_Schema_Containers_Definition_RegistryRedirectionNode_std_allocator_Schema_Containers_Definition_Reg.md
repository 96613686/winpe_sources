# std::vector<Schema::Containers::Definition::RegistryRedirectionNode,std::allocator<Schema::Containers::Definition::RegistryRedirectionNode>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryRedirectionNode * const)

- ea: `0x18001cd4c`
- end: `0x18001cf8d`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryRedirectionNode@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180016310`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001cd4c`
- `0x18001e3f0`
- `0x18001f0ec`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Emplace_reallocate<>(
        void **a1,
        _BYTE *a2)
{
  _BYTE *v2; // rbp
  __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  __int64 v8; // r15
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r14
  char *v11; // rbx
  void *v12; // rax
  char *v13; // r8
  __int64 v14; // r13
  char *v15; // rcx
  char *v16; // rbp
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
  v13 = v11;
  v14 = (a2 - v2) / 104;
  v15 = &v11[104 * v14];
  v25 = v15;
  *((_QWORD *)v15 + 12) = 0;
  v16 = v15 + 104;
  *(_OWORD *)v15 = 0;
  *((_QWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 3) = 7;
  *(_WORD *)v15 = 0;
  *((_OWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 7) = 7;
  *((_WORD *)v15 + 16) = 0;
  *((_OWORD *)v15 + 4) = 0;
  *((_QWORD *)v15 + 10) = 0;
  *((_QWORD *)v15 + 11) = 7;
  *((_WORD *)v15 + 32) = 0;
  v17 = a1[1];
  v18 = *a1;
  v26 = v16;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryRedirectionNode *>(v18, a2, v11);
    v17 = a1[1];
    v13 = v16;
    v18 = a2;
    v25 = v11;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::RegistryRedirectionNode *>(v18, v17, v13);
  v19 = (char *)*a1;
  v24[1] = 0;
  if ( v19 )
  {
    v20 = (char *)a1[1];
    while ( v19 != v20 )
    {
      std::wstring::~wstring(v19 + 64);
      std::wstring::~wstring(v19 + 32);
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
  std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Reallocation_guard::~_Reallocation_guard(v24);
  return &v11[104 * v14];
}

```

## disassembly

```asm
0x18001cd4c  push    rbx
0x18001cd4e  push    rbp
0x18001cd4f  push    rsi
0x18001cd50  push    rdi
0x18001cd51  push    r12
0x18001cd53  push    r13
0x18001cd55  push    r14
0x18001cd57  push    r15
0x18001cd59  sub     rsp, 58h
0x18001cd5d  mov     rbp, [rcx]
0x18001cd60  mov     r13, 4EC4EC4EC4EC4EC5h
0x18001cd6a  mov     r8, [rcx+8]
0x18001cd6e  mov     r9, 276276276276276h
0x18001cd78  sub     r8, rbp
0x18001cd7b  mov     r12, rdx
0x18001cd7e  sar     r8, 3
0x18001cd82  mov     rdi, rcx
0x18001cd85  imul    r8, r13
0x18001cd89  cmp     r8, r9
0x18001cd8c  jz      loc_18001CF81
0x18001cd92  mov     rcx, [rcx+10h]
0x18001cd96  mov     rax, r9
0x18001cd99  sub     rcx, rbp
0x18001cd9c  sar     rcx, 3
0x18001cda0  imul    rcx, r13
0x18001cda4  mov     rdx, rcx
0x18001cda7  shr     rdx, 1
0x18001cdaa  sub     rax, rdx
0x18001cdad  cmp     rcx, rax
0x18001cdb0  ja      loc_18001CF87
0x18001cdb6  lea     r15, [r8+1]
0x18001cdba  lea     rax, [rcx+rdx]
0x18001cdbe  mov     rsi, r15
0x18001cdc1  cmp     rax, r15
0x18001cdc4  cmovnb  rsi, rax
0x18001cdc8  cmp     rsi, r9
0x18001cdcb  ja      loc_18001CF87
0x18001cdd1  imul    r14, rsi, 68h ; 'h'
0x18001cdd5  test    r14, r14
0x18001cdd8  jnz     short loc_18001CDDE
0x18001cdda  xor     ebx, ebx
0x18001cddc  jmp     short loc_18001CE1B
0x18001cdde  cmp     r14, 1000h
0x18001cde5  jb      short loc_18001CE10
0x18001cde7  lea     rcx, [r14+27h]; Size
0x18001cdeb  cmp     rcx, r14
0x18001cdee  jbe     loc_18001CF87
0x18001cdf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cdf9  test    rax, rax
0x18001cdfc  jz      loc_18001CF36
0x18001ce02  lea     rbx, [rax+27h]
0x18001ce06  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001ce0a  mov     [rbx-8], rax
0x18001ce0e  jmp     short loc_18001CE1B
0x18001ce10  mov     rcx, r14; Size
0x18001ce13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ce18  mov     rbx, rax
0x18001ce1b  mov     rax, r13
0x18001ce1e  mov     [rsp+98h+var_78], rdi
0x18001ce23  xorps   xmm0, xmm0
0x18001ce26  mov     [rsp+98h+var_68], rsi
0x18001ce2b  mov     rcx, r12
0x18001ce2e  mov     r8, rbx
0x18001ce31  sub     rcx, rbp
0x18001ce34  imul    rcx
0x18001ce37  xor     eax, eax
0x18001ce39  mov     r13, rdx
0x18001ce3c  sar     r13, 5
0x18001ce40  mov     rcx, r13
0x18001ce43  shr     rcx, 3Fh
0x18001ce47  lea     edx, [rax+7]
0x18001ce4a  add     r13, rcx
0x18001ce4d  imul    rcx, r13, 68h ; 'h'
0x18001ce51  add     rcx, rbx
0x18001ce54  mov     [rsp+98h+var_60], rcx
0x18001ce59  mov     [rcx+60h], rax
0x18001ce5d  lea     rbp, [rcx+68h]
0x18001ce61  movups  xmmword ptr [rcx], xmm0
0x18001ce64  mov     [rcx+10h], rax
0x18001ce68  mov     [rcx+18h], rdx
0x18001ce6c  mov     [rcx], ax
0x18001ce6f  movups  xmmword ptr [rcx+20h], xmm0
0x18001ce73  mov     [rcx+30h], rax
0x18001ce77  mov     [rcx+38h], rdx
0x18001ce7b  mov     [rcx+20h], ax
0x18001ce7f  movups  xmmword ptr [rcx+40h], xmm0
0x18001ce83  mov     [rcx+50h], rax
0x18001ce87  mov     [rcx+58h], rdx
0x18001ce8b  mov     [rcx+40h], ax
0x18001ce8f  mov     rdx, [rdi+8]
0x18001ce93  mov     rcx, [rdi]
0x18001ce96  mov     [rsp+98h+var_58], rbp
0x18001ce9b  cmp     r12, rdx
0x18001ce9e  jz      short loc_18001CEB7
0x18001cea0  mov     rdx, r12
0x18001cea3  call    ??$_Uninitialized_move@PEAURegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryRedirectionNode@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryRedirectionNode *>(Schema::Containers::Definition::RegistryRedirectionNode * const,Schema::Containers::Definition::RegistryRedirectionNode * const,Schema::Containers::Definition::RegistryRedirectionNode *,std::allocator<Schema::Containers::Definition::RegistryRedirectionNode> &)
0x18001cea8  mov     rdx, [rdi+8]
0x18001ceac  mov     r8, rbp
0x18001ceaf  mov     rcx, r12
0x18001ceb2  mov     [rsp+98h+var_60], rbx
0x18001ceb7  call    ??$_Uninitialized_move@PEAURegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryRedirectionNode@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryRedirectionNode *>(Schema::Containers::Definition::RegistryRedirectionNode * const,Schema::Containers::Definition::RegistryRedirectionNode * const,Schema::Containers::Definition::RegistryRedirectionNode *,std::allocator<Schema::Containers::Definition::RegistryRedirectionNode> &)
0x18001cebc  mov     rsi, [rdi]
0x18001cebf  mov     [rsp+98h+var_70], 0
0x18001cec8  test    rsi, rsi
0x18001cecb  jz      short loc_18001CF48
0x18001cecd  mov     rbp, [rdi+8]
0x18001ced1  jmp     short loc_18001CEF1
0x18001ced3  lea     rcx, [rsi+40h]
0x18001ced7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cedc  lea     rcx, [rsi+20h]
0x18001cee0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cee5  mov     rcx, rsi
0x18001cee8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ceed  add     rsi, 68h ; 'h'
0x18001cef1  cmp     rsi, rbp
0x18001cef4  jnz     short loc_18001CED3
0x18001cef6  mov     rcx, [rdi]
0x18001cef9  mov     rdx, 4EC4EC4EC4EC4EC5h
0x18001cf03  mov     rax, [rdi+10h]
0x18001cf07  sub     rax, rcx
0x18001cf0a  sar     rax, 3
0x18001cf0e  imul    rax, rdx
0x18001cf12  imul    rdx, rax, 68h ; 'h'; unsigned __int64
0x18001cf16  cmp     rdx, 1000h
0x18001cf1d  jb      short loc_18001CF3D
0x18001cf1f  mov     rax, [rcx-8]
0x18001cf23  sub     rcx, rax
0x18001cf26  sub     rcx, 8
0x18001cf2a  cmp     rcx, 1Fh
0x18001cf2e  ja      short loc_18001CF36
0x18001cf30  add     rdx, 27h ; '''
0x18001cf34  jmp     short loc_18001CF40
0x18001cf36  mov     ecx, 5
0x18001cf3b  int     29h; Win8: RtlFailFast(ecx)
0x18001cf3d  mov     rax, rcx
0x18001cf40  mov     rcx, rax; void *
0x18001cf43  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001cf48  mov     [rdi], rbx
0x18001cf4b  lea     rcx, [rsp+98h+var_78]
0x18001cf50  imul    rax, r15, 68h ; 'h'
0x18001cf54  add     rax, rbx
0x18001cf57  mov     [rdi+8], rax
0x18001cf5b  lea     rax, [r14+rbx]
0x18001cf5f  mov     [rdi+10h], rax
0x18001cf63  call    ??1_Reallocation_guard@?$vector@URegistryRedirectionNode@Definition@Containers@Schema@@V?$allocator@URegistryRedirectionNode@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::RegistryRedirectionNode>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001cf68  imul    rax, r13, 68h ; 'h'
0x18001cf6c  add     rax, rbx
0x18001cf6f  add     rsp, 58h
0x18001cf73  pop     r15
0x18001cf75  pop     r14
0x18001cf77  pop     r13
0x18001cf79  pop     r12
0x18001cf7b  pop     rdi
0x18001cf7c  pop     rsi
0x18001cf7d  pop     rbp
0x18001cf7e  pop     rbx
0x18001cf7f  retn
0x18001cf81  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001cf87  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
