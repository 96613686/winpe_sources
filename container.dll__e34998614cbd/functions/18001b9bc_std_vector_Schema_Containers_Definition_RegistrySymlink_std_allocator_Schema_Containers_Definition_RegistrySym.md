# std::vector<Schema::Containers::Definition::RegistrySymlink,std::allocator<Schema::Containers::Definition::RegistrySymlink>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistrySymlink * const)

- ea: `0x18001b9bc`
- end: `0x18001bbbf`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistrySymlink@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `515`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180015bc0`
- `0x180015c70`
- `0x1800163e0`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001b9bc`
- `0x18001dd18`
- `0x18001ec20`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::RegistrySymlink>::_Emplace_reallocate<>(
        void **a1,
        _BYTE *a2)
{
  _BYTE *v2; // r12
  __int64 v3; // rbp
  __int64 v6; // rax
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rsi
  size_t v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  char *v13; // rbx
  void *v14; // rax
  char *v15; // r8
  __int64 v16; // r15
  char *v17; // rdx
  char *v18; // r12
  _BYTE *v19; // rdx
  void *v20; // rcx
  char *v21; // rbp
  char *v22; // r12
  char *v23; // rax
  _BYTE *v24; // rcx
  _QWORD v26[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v27; // [rsp+38h] [rbp-60h]
  char *v28; // [rsp+40h] [rbp-58h]

  v2 = *a1;
  v3 = 0x3FFFFFFFFFFFFFFLL;
  v6 = ((_BYTE *)a1[1] - (_BYTE *)*a1) >> 6;
  if ( v6 == 0x3FFFFFFFFFFFFFFLL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v7 = v6 + 1;
  v8 = ((_BYTE *)a1[2] - v2) >> 6;
  if ( v8 <= 0x3FFFFFFFFFFFFFFLL - (v8 >> 1) )
  {
    v11 = v8 + (v8 >> 1);
    v12 = v7;
    if ( v11 >= v7 )
      v12 = v11;
    if ( v12 > 0x3FFFFFFFFFFFFFFLL )
      goto LABEL_27;
    v3 = v12;
    v9 = v12 << 6;
    if ( !(v12 << 6) )
    {
      v13 = 0;
      goto LABEL_14;
    }
    if ( v9 < 0x1000 )
    {
      v13 = (char *)operator new(v12 << 6);
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
  v26[2] = v3;
  v15 = v13;
  v16 = (a2 - v2) >> 6;
  v17 = &v13[64 * v16];
  v27 = v17;
  *(_OWORD *)v17 = 0;
  *((_QWORD *)v17 + 2) = 0;
  v18 = v17 + 64;
  *((_QWORD *)v17 + 3) = 7;
  *(_WORD *)v17 = 0;
  *((_OWORD *)v17 + 2) = 0;
  *((_QWORD *)v17 + 6) = 0;
  *((_QWORD *)v17 + 7) = 7;
  *((_WORD *)v17 + 16) = 0;
  v19 = a1[1];
  v20 = *a1;
  v28 = v18;
  if ( a2 != v19 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistrySymlink *>(v20, a2, v13);
    v19 = a1[1];
    v15 = v18;
    v20 = a2;
    v27 = v13;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::RegistrySymlink *>(v20, v19, v15);
  v21 = (char *)*a1;
  v26[1] = 0;
  if ( v21 )
  {
    v22 = (char *)a1[1];
    while ( v21 != v22 )
    {
      std::wstring::~wstring(v21 + 32);
      std::wstring::~wstring(v21);
      v21 += 64;
    }
    v23 = (char *)*a1;
    if ( (((_BYTE *)a1[2] - (_BYTE *)*a1) & 0xFFFFFFFFFFFFFFC0uLL) < 0x1000 )
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
  a1[1] = &v13[64 * v7];
  a1[2] = &v13[v9];
  std::vector<container::DownlevelProvider::ContainerFixup>::_Reallocation_guard::~_Reallocation_guard(v26);
  return &v13[64 * v16];
}

```

## disassembly

```asm
0x18001b9bc  push    rbx
0x18001b9be  push    rbp
0x18001b9bf  push    rsi
0x18001b9c0  push    rdi
0x18001b9c1  push    r12
0x18001b9c3  push    r13
0x18001b9c5  push    r14
0x18001b9c7  push    r15
0x18001b9c9  sub     rsp, 58h
0x18001b9cd  mov     r12, [rcx]
0x18001b9d0  mov     rbp, 3FFFFFFFFFFFFFFh
0x18001b9da  mov     rax, [rcx+8]
0x18001b9de  mov     r13, rdx
0x18001b9e1  sub     rax, r12
0x18001b9e4  mov     rdi, rcx
0x18001b9e7  sar     rax, 6
0x18001b9eb  cmp     rax, rbp
0x18001b9ee  jz      loc_18001BBB3
0x18001b9f4  mov     rcx, [rcx+10h]
0x18001b9f8  lea     r14, [rax+1]
0x18001b9fc  sub     rcx, r12
0x18001b9ff  mov     rax, rbp
0x18001ba02  sar     rcx, 6
0x18001ba06  mov     rdx, rcx
0x18001ba09  shr     rdx, 1
0x18001ba0c  sub     rax, rdx
0x18001ba0f  cmp     rcx, rax
0x18001ba12  jbe     short loc_18001BA21
0x18001ba14  mov     rsi, 0FFFFFFFFFFFFFFC0h
0x18001ba1b  lea     rcx, [rsi+27h]
0x18001ba1f  jmp     short loc_18001BA61
0x18001ba21  lea     rax, [rcx+rdx]
0x18001ba25  mov     rcx, r14
0x18001ba28  cmp     rax, r14
0x18001ba2b  cmovnb  rcx, rax
0x18001ba2f  cmp     rcx, rbp
0x18001ba32  ja      loc_18001BBB9
0x18001ba38  mov     rsi, rcx
0x18001ba3b  mov     rbp, rcx
0x18001ba3e  shl     rsi, 6
0x18001ba42  test    rsi, rsi
0x18001ba45  jnz     short loc_18001BA4B
0x18001ba47  xor     ebx, ebx
0x18001ba49  jmp     short loc_18001BA88
0x18001ba4b  cmp     rsi, 1000h
0x18001ba52  jb      short loc_18001BA7D
0x18001ba54  lea     rcx, [rsi+27h]; Size
0x18001ba58  cmp     rcx, rsi
0x18001ba5b  jbe     loc_18001BBB9
0x18001ba61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba66  test    rax, rax
0x18001ba69  jz      loc_18001BB6A
0x18001ba6f  lea     rbx, [rax+27h]
0x18001ba73  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001ba77  mov     [rbx-8], rax
0x18001ba7b  jmp     short loc_18001BA88
0x18001ba7d  mov     rcx, rsi; Size
0x18001ba80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba85  mov     rbx, rax
0x18001ba88  xor     eax, eax
0x18001ba8a  mov     [rsp+98h+var_78], rdi
0x18001ba8f  mov     ecx, 7
0x18001ba94  mov     [rsp+98h+var_68], rbp
0x18001ba99  xorps   xmm0, xmm0
0x18001ba9c  mov     r15, r13
0x18001ba9f  sub     r15, r12
0x18001baa2  mov     r8, rbx
0x18001baa5  sar     r15, 6
0x18001baa9  mov     rdx, r15
0x18001baac  shl     rdx, 6
0x18001bab0  add     rdx, rbx
0x18001bab3  mov     [rsp+98h+var_60], rdx
0x18001bab8  movups  xmmword ptr [rdx], xmm0
0x18001babb  mov     qword ptr [rdx+10h], 0
0x18001bac3  lea     r12, [rdx+40h]
0x18001bac7  mov     [rdx+18h], rcx
0x18001bacb  mov     [rdx], ax
0x18001bace  movups  xmmword ptr [rdx+20h], xmm0
0x18001bad2  mov     [rdx+30h], rax
0x18001bad6  mov     [rdx+38h], rcx
0x18001bada  mov     [rdx+20h], ax
0x18001bade  mov     rdx, [rdi+8]
0x18001bae2  mov     rcx, [rdi]
0x18001bae5  mov     [rsp+98h+var_58], r12
0x18001baea  cmp     r13, rdx
0x18001baed  jz      short loc_18001BB06
0x18001baef  mov     rdx, r13
0x18001baf2  call    ??$_Uninitialized_move@PEAURegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistrySymlink@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistrySymlink@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistrySymlink *>(Schema::Containers::Definition::RegistrySymlink * const,Schema::Containers::Definition::RegistrySymlink * const,Schema::Containers::Definition::RegistrySymlink *,std::allocator<Schema::Containers::Definition::RegistrySymlink> &)
0x18001baf7  mov     rdx, [rdi+8]
0x18001bafb  mov     r8, r12
0x18001bafe  mov     rcx, r13
0x18001bb01  mov     [rsp+98h+var_60], rbx
0x18001bb06  call    ??$_Uninitialized_move@PEAURegistrySymlink@Definition@Containers@Schema@@V?$allocator@URegistrySymlink@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistrySymlink@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistrySymlink@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistrySymlink *>(Schema::Containers::Definition::RegistrySymlink * const,Schema::Containers::Definition::RegistrySymlink * const,Schema::Containers::Definition::RegistrySymlink *,std::allocator<Schema::Containers::Definition::RegistrySymlink> &)
0x18001bb0b  mov     rbp, [rdi]
0x18001bb0e  mov     [rsp+98h+var_70], 0
0x18001bb17  test    rbp, rbp
0x18001bb1a  jz      short loc_18001BB79
0x18001bb1c  mov     r12, [rdi+8]
0x18001bb20  jmp     short loc_18001BB37
0x18001bb22  lea     rcx, [rbp+20h]
0x18001bb26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bb2b  mov     rcx, rbp
0x18001bb2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bb33  add     rbp, 40h ; '@'
0x18001bb37  cmp     rbp, r12
0x18001bb3a  jnz     short loc_18001BB22
0x18001bb3c  mov     rax, [rdi]
0x18001bb3f  mov     rdx, [rdi+10h]
0x18001bb43  sub     rdx, rax
0x18001bb46  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x18001bb4a  cmp     rdx, 1000h
0x18001bb51  jb      short loc_18001BB71
0x18001bb53  mov     rcx, [rax-8]
0x18001bb57  sub     rax, rcx
0x18001bb5a  sub     rax, 8
0x18001bb5e  cmp     rax, 1Fh
0x18001bb62  ja      short loc_18001BB6A
0x18001bb64  add     rdx, 27h ; '''
0x18001bb68  jmp     short loc_18001BB74
0x18001bb6a  mov     ecx, 5
0x18001bb6f  int     29h; Win8: RtlFailFast(ecx)
0x18001bb71  mov     rcx, rax; void *
0x18001bb74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bb79  mov     [rdi], rbx
0x18001bb7c  lea     rax, [rsi+rbx]
0x18001bb80  shl     r14, 6
0x18001bb84  lea     rcx, [rsp+98h+var_78]
0x18001bb89  add     r14, rbx
0x18001bb8c  mov     [rdi+8], r14
0x18001bb90  mov     [rdi+10h], rax
0x18001bb94  call    ??1_Reallocation_guard@?$vector@UContainerFixup@DownlevelProvider@container@@V?$allocator@UContainerFixup@DownlevelProvider@container@@@std@@@std@@QEAA@XZ; std::vector<container::DownlevelProvider::ContainerFixup>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001bb99  shl     r15, 6
0x18001bb9d  lea     rax, [r15+rbx]
0x18001bba1  add     rsp, 58h
0x18001bba5  pop     r15
0x18001bba7  pop     r14
0x18001bba9  pop     r13
0x18001bbab  pop     r12
0x18001bbad  pop     rdi
0x18001bbae  pop     rsi
0x18001bbaf  pop     rbp
0x18001bbb0  pop     rbx
0x18001bbb1  retn
0x18001bbb3  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001bbb9  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
