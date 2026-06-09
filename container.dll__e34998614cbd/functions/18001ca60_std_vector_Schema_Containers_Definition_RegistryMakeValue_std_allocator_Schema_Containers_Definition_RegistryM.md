# std::vector<Schema::Containers::Definition::RegistryMakeValue,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>::_Emplace_reallocate<>(Schema::Containers::Definition::RegistryMakeValue * const)

- ea: `0x18001ca60`
- end: `0x18001cd46`
- name: `??$_Emplace_reallocate@$$V@?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@AEAAPEAURegistryMakeValue@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x1800161f0`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001ca60`
- `0x18001d9d0`
- `0x18001e2a0`
- `0x18001e6dc`
- `0x18001f048`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Emplace_reallocate<>(
        _QWORD *a1,
        __int64 a2)
{
  void *v4; // rbp
  unsigned __int64 v5; // rax
  __int64 v6; // rsi
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // rcx
  size_t v9; // rcx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  __int64 v15; // r13
  char *v16; // rcx
  char *v17; // rbp
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rbp
  __int64 v22; // rcx
  void *v23; // rax
  _QWORD *v25; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v26; // [rsp+28h] [rbp-70h]
  __int64 v27; // [rsp+30h] [rbp-68h]
  _QWORD *v28; // [rsp+38h] [rbp-60h]
  char *v29; // [rsp+40h] [rbp-58h]

  v4 = (void *)*a1;
  v5 = 0x86BCA1AF286BCA1BuLL * ((__int64)(a1[1] - *a1) >> 3);
  v6 = 0x1AF286BCA1AF286LL;
  if ( v5 == 0x1AF286BCA1AF286LL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v7 = v5 + 1;
  v8 = 0x86BCA1AF286BCA1BuLL * ((__int64)(a1[2] - (_QWORD)v4) >> 3);
  if ( v8 <= 0x1AF286BCA1AF286LL - (v8 >> 1) )
  {
    v11 = v8 + (v8 >> 1);
    v12 = v7;
    if ( v11 >= v7 )
      v12 = v11;
    if ( v12 > 0x1AF286BCA1AF286LL )
      goto LABEL_29;
    v10 = 152 * v12;
    v6 = v12;
    if ( !(152 * v12) )
    {
      v13 = 0;
      goto LABEL_15;
    }
    if ( v10 < 0x1000 )
    {
      v13 = operator new(152 * v12);
      goto LABEL_15;
    }
    v9 = v10 + 39;
    if ( v10 + 39 < v10 )
LABEL_29:
      __scrt_throw_std_bad_array_new_length();
  }
  else
  {
    v9 = -73;
    v10 = -112;
  }
  v14 = operator new(v9);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_15:
  v15 = (a2 - (__int64)v4) / 152;
  v16 = (char *)&v13[19 * v15];
  v17 = v16 + 152;
  v25 = a1;
  v26 = v13;
  v27 = v6;
  v29 = v16 + 152;
  *(_OWORD *)v16 = 0;
  *((_QWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 3) = 7;
  *(_WORD *)v16 = 0;
  *(_DWORD *)(v16 + 65) = 0;
  *(_WORD *)(v16 + 69) = 0;
  v16[71] = 0;
  *((_OWORD *)v16 + 2) = 0;
  *((_QWORD *)v16 + 6) = 0;
  *((_QWORD *)v16 + 7) = 7;
  *((_WORD *)v16 + 16) = 0;
  v16[64] = 0;
  *((_QWORD *)v16 + 9) = 0;
  *(_DWORD *)(v16 + 113) = 0;
  *(_WORD *)(v16 + 117) = 0;
  v16[119] = 0;
  *((_OWORD *)v16 + 5) = 0;
  *((_QWORD *)v16 + 12) = 0;
  *((_QWORD *)v16 + 13) = 7;
  *((_WORD *)v16 + 40) = 0;
  v16[112] = 0;
  *(_DWORD *)(v16 + 145) = 0;
  *(_WORD *)(v16 + 149) = 0;
  v16[151] = 0;
  *((_QWORD *)v16 + 15) = 0;
  *((_QWORD *)v16 + 16) = 0;
  *((_QWORD *)v16 + 17) = 0;
  v16[144] = 0;
  v28 = v16;
  v18 = a1[1];
  v19 = *a1;
  if ( a2 == v18 )
  {
    std::_Uninitialized_copy<Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>(
      v19,
      v18,
      v13,
      a1,
      v25,
      v26,
      v27,
      v28,
      v29);
  }
  else
  {
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeValue *>(v19, a2, v13);
    v28 = v13;
    std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeValue *>(a2, a1[1], v17);
  }
  v26 = 0;
  v20 = *a1;
  if ( *a1 )
  {
    v21 = a1[1];
    while ( v20 != v21 )
    {
      std::vector<unsigned char>::~vector<unsigned char>(v20 + 120);
      std::wstring::~wstring(v20 + 80);
      std::wstring::~wstring(v20 + 32);
      std::wstring::~wstring(v20);
      v20 += 152;
    }
    v22 = *a1;
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - *a1) >> 3)) < 0x1000 )
    {
      v23 = (void *)*a1;
    }
    else
    {
      v23 = *(void **)(v22 - 8);
      if ( (unsigned __int64)(v22 - (_QWORD)v23 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v23);
  }
  *a1 = v13;
  a1[1] = &v13[19 * v7];
  a1[2] = &v13[v10 / 8];
  std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Reallocation_guard::~_Reallocation_guard(&v25);
  return (char *)&v13[19 * v15];
}

```

## disassembly

```asm
0x18001ca60  push    rbx
0x18001ca62  push    rbp
0x18001ca63  push    rsi
0x18001ca64  push    rdi
0x18001ca65  push    r12
0x18001ca67  push    r13
0x18001ca69  push    r14
0x18001ca6b  push    r15
0x18001ca6d  sub     rsp, 58h
0x18001ca71  mov     r12, rdx
0x18001ca74  mov     rdi, rcx
0x18001ca77  mov     rbp, [rcx]
0x18001ca7a  mov     rax, [rcx+8]
0x18001ca7e  sub     rax, rbp
0x18001ca81  sar     rax, 3
0x18001ca85  mov     rdx, 86BCA1AF286BCA1Bh
0x18001ca8f  imul    rax, rdx
0x18001ca93  mov     rsi, 1AF286BCA1AF286h
0x18001ca9d  cmp     rax, rsi
0x18001caa0  jz      loc_18001CD3A
0x18001caa6  lea     r15, [rax+1]
0x18001caaa  mov     rcx, [rcx+10h]
0x18001caae  sub     rcx, rbp
0x18001cab1  sar     rcx, 3
0x18001cab5  imul    rcx, rdx
0x18001cab9  mov     rdx, rcx
0x18001cabc  shr     rdx, 1
0x18001cabf  mov     rax, rsi
0x18001cac2  sub     rax, rdx
0x18001cac5  xor     r8d, r8d
0x18001cac8  cmp     rcx, rax
0x18001cacb  jbe     short loc_18001CAD7
0x18001cacd  lea     rcx, [r8-49h]
0x18001cad1  lea     r14, [r8-70h]
0x18001cad5  jmp     short loc_18001CB18
0x18001cad7  lea     rax, [rcx+rdx]
0x18001cadb  mov     rcx, r15
0x18001cade  cmp     rax, r15
0x18001cae1  cmovnb  rcx, rax
0x18001cae5  cmp     rcx, rsi
0x18001cae8  ja      loc_18001CD40
0x18001caee  imul    r14, rcx, 98h
0x18001caf5  mov     rsi, rcx
0x18001caf8  test    r14, r14
0x18001cafb  jnz     short loc_18001CB02
0x18001cafd  mov     rbx, r8
0x18001cb00  jmp     short loc_18001CB46
0x18001cb02  cmp     r14, 1000h
0x18001cb09  jb      short loc_18001CB38
0x18001cb0b  lea     rcx, [r14+27h]; Size
0x18001cb0f  cmp     rcx, r14
0x18001cb12  jbe     loc_18001CD40
0x18001cb18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cb1d  xor     r8d, r8d
0x18001cb20  test    rax, rax
0x18001cb23  jnz     short loc_18001CB2A
0x18001cb25  lea     ecx, [rax+5]
0x18001cb28  int     29h; Win8: RtlFailFast(ecx)
0x18001cb2a  lea     rbx, [rax+27h]
0x18001cb2e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001cb32  mov     [rbx-8], rax
0x18001cb36  jmp     short loc_18001CB46
0x18001cb38  mov     rcx, r14; Size
0x18001cb3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cb40  mov     rbx, rax
0x18001cb43  xor     r8d, r8d
0x18001cb46  mov     rcx, r12
0x18001cb49  sub     rcx, rbp
0x18001cb4c  mov     rax, 6BCA1AF286BCA1Bh
0x18001cb56  imul    rcx
0x18001cb59  mov     r13, rdx
0x18001cb5c  sar     r13, 2
0x18001cb60  mov     rcx, r13
0x18001cb63  shr     rcx, 3Fh
0x18001cb67  add     r13, rcx
0x18001cb6a  imul    rcx, r13, 98h
0x18001cb71  add     rcx, rbx
0x18001cb74  lea     rbp, [rcx+98h]
0x18001cb7b  mov     [rsp+98h+var_78], rdi
0x18001cb80  mov     [rsp+98h+var_70], rbx
0x18001cb85  mov     [rsp+98h+var_68], rsi
0x18001cb8a  mov     [rsp+98h+var_58], rbp
0x18001cb8f  xorps   xmm0, xmm0
0x18001cb92  movups  xmmword ptr [rcx], xmm0
0x18001cb95  mov     [rcx+10h], r8
0x18001cb99  mov     edx, 7
0x18001cb9e  mov     [rcx+18h], rdx
0x18001cba2  mov     [rcx], r8w
0x18001cba6  mov     [rcx+41h], r8d
0x18001cbaa  mov     [rcx+45h], r8w
0x18001cbaf  mov     [rcx+47h], r8b
0x18001cbb3  movups  xmmword ptr [rcx+20h], xmm0
0x18001cbb7  mov     [rcx+30h], r8
0x18001cbbb  mov     [rcx+38h], rdx
0x18001cbbf  mov     [rcx+20h], r8w
0x18001cbc4  mov     [rcx+40h], r8b
0x18001cbc8  xor     eax, eax
0x18001cbca  mov     [rcx+48h], rax
0x18001cbce  mov     [rcx+71h], r8d
0x18001cbd2  mov     [rcx+75h], r8w
0x18001cbd7  mov     [rcx+77h], r8b
0x18001cbdb  movups  xmmword ptr [rcx+50h], xmm0
0x18001cbdf  mov     [rcx+60h], r8
0x18001cbe3  mov     [rcx+68h], rdx
0x18001cbe7  mov     [rcx+50h], r8w
0x18001cbec  mov     [rcx+70h], r8b
0x18001cbf0  mov     [rcx+91h], r8d
0x18001cbf7  mov     [rcx+95h], r8w
0x18001cbff  mov     [rcx+97h], r8b
0x18001cc06  mov     [rcx+78h], r8
0x18001cc0a  mov     [rcx+80h], r8
0x18001cc11  mov     [rcx+88h], r8
0x18001cc18  mov     [rcx+90h], r8b
0x18001cc1f  mov     [rsp+98h+var_60], rcx
0x18001cc24  mov     rdx, [rdi+8]
0x18001cc28  mov     r8, rbx
0x18001cc2b  mov     rcx, [rdi]
0x18001cc2e  cmp     r12, rdx
0x18001cc31  jnz     short loc_18001CC3D
0x18001cc33  mov     r9, rdi
0x18001cc36  call    ??$_Uninitialized_copy@PEAURegistryMakeValue@Definition@Containers@Schema@@PEAU1234@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeValue@Definition@Containers@Schema@@PEAU1234@00AEAV?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_copy<Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue>>(Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue> &)
0x18001cc3b  jmp     short loc_18001CC59
0x18001cc3d  mov     rdx, r12
0x18001cc40  call    ??$_Uninitialized_move@PEAURegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeValue@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeValue *>(Schema::Containers::Definition::RegistryMakeValue * const,Schema::Containers::Definition::RegistryMakeValue * const,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue> &)
0x18001cc45  mov     [rsp+98h+var_60], rbx
0x18001cc4a  mov     r8, rbp
0x18001cc4d  mov     rdx, [rdi+8]
0x18001cc51  mov     rcx, r12
0x18001cc54  call    ??$_Uninitialized_move@PEAURegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@YAPEAURegistryMakeValue@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::RegistryMakeValue *>(Schema::Containers::Definition::RegistryMakeValue * const,Schema::Containers::Definition::RegistryMakeValue * const,Schema::Containers::Definition::RegistryMakeValue *,std::allocator<Schema::Containers::Definition::RegistryMakeValue> &)
0x18001cc59  mov     [rsp+98h+var_70], 0
0x18001cc62  mov     rsi, [rdi]
0x18001cc65  test    rsi, rsi
0x18001cc68  jz      loc_18001CCF8
0x18001cc6e  mov     rbp, [rdi+8]
0x18001cc72  jmp     short loc_18001CC9E
0x18001cc74  lea     rcx, [rsi+78h]
0x18001cc78  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001cc7d  lea     rcx, [rsi+50h]
0x18001cc81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cc86  lea     rcx, [rsi+20h]
0x18001cc8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cc8f  mov     rcx, rsi
0x18001cc92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cc97  add     rsi, 98h
0x18001cc9e  cmp     rsi, rbp
0x18001cca1  jnz     short loc_18001CC74
0x18001cca3  mov     rcx, [rdi]
0x18001cca6  mov     rax, [rdi+10h]
0x18001ccaa  sub     rax, rcx
0x18001ccad  sar     rax, 3
0x18001ccb1  mov     rdx, 86BCA1AF286BCA1Bh
0x18001ccbb  imul    rax, rdx
0x18001ccbf  imul    rdx, rax, 98h; unsigned __int64
0x18001ccc6  cmp     rdx, 1000h
0x18001cccd  jb      short loc_18001CCED
0x18001cccf  mov     rax, [rcx-8]
0x18001ccd3  sub     rcx, rax
0x18001ccd6  sub     rcx, 8
0x18001ccda  cmp     rcx, 1Fh
0x18001ccde  ja      short loc_18001CCE6
0x18001cce0  add     rdx, 27h ; '''
0x18001cce4  jmp     short loc_18001CCF0
0x18001cce6  mov     ecx, 5
0x18001cceb  int     29h; Win8: RtlFailFast(ecx)
0x18001cced  mov     rax, rcx
0x18001ccf0  mov     rcx, rax; void *
0x18001ccf3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ccf8  mov     [rdi], rbx
0x18001ccfb  imul    rax, r15, 98h
0x18001cd02  add     rax, rbx
0x18001cd05  mov     [rdi+8], rax
0x18001cd09  lea     rax, [r14+rbx]
0x18001cd0d  mov     [rdi+10h], rax
0x18001cd11  imul    rax, r13, 98h
0x18001cd18  add     rbx, rax
0x18001cd1b  lea     rcx, [rsp+98h+var_78]
0x18001cd20  call    ??1_Reallocation_guard@?$vector@URegistryMakeValue@Definition@Containers@Schema@@V?$allocator@URegistryMakeValue@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::RegistryMakeValue>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001cd25  mov     rax, rbx
0x18001cd28  add     rsp, 58h
0x18001cd2c  pop     r15
0x18001cd2e  pop     r14
0x18001cd30  pop     r13
0x18001cd32  pop     r12
0x18001cd34  pop     rdi
0x18001cd35  pop     rsi
0x18001cd36  pop     rbp
0x18001cd37  pop     rbx
0x18001cd38  retn
0x18001cd3a  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001cd40  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
