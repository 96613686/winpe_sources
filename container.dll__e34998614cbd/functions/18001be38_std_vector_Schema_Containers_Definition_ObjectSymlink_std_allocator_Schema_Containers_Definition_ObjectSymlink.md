# std::vector<Schema::Containers::Definition::ObjectSymlink,std::allocator<Schema::Containers::Definition::ObjectSymlink>>::_Emplace_reallocate<>(Schema::Containers::Definition::ObjectSymlink * const)

- ea: `0x18001be38`
- end: `0x18001c084`
- name: `??$_Emplace_reallocate@$$V@?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAPEAUObjectSymlink@Definition@Containers@Schema@@QEAU2345@@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x180015e00`

## callees

- `0x180002af4`
- `0x180002ee4`
- `0x1800051b0`
- `0x18000be08`
- `0x1800120b0`
- `0x18001be38`
- `0x18001decc`
- `0x18001ed50`

## pseudocode

```c
char *__fastcall std::vector<Schema::Containers::Definition::ObjectSymlink>::_Emplace_reallocate<>(
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
  v5 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 4);
  if ( v5 == 0x249249249249249LL )
    std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength();
  v6 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[2] - v2) >> 4);
  v7 = v6 >> 1;
  if ( v6 > 0x249249249249249LL - (v6 >> 1) )
    goto LABEL_26;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x249249249249249LL )
    goto LABEL_26;
  v10 = 112 * v9;
  if ( !(112 * v9) )
  {
    v11 = 0;
    goto LABEL_13;
  }
  if ( v10 < 0x1000 )
  {
    v11 = (char *)operator new(112 * v9);
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
  v14 = (a2 - v2) / 112;
  v15 = &v11[112 * v14];
  v25 = v15;
  *((_QWORD *)v15 + 8) = 0;
  v16 = v15 + 112;
  *((_QWORD *)v15 + 13) = 0;
  *(_OWORD *)v15 = 0;
  *((_QWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 3) = 7;
  *(_WORD *)v15 = 0;
  *((_OWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 7) = 7;
  *((_WORD *)v15 + 16) = 0;
  *(_OWORD *)(v15 + 72) = 0;
  *((_QWORD *)v15 + 11) = 0;
  *((_QWORD *)v15 + 12) = 7;
  *((_WORD *)v15 + 36) = 0;
  v17 = a1[1];
  v18 = *a1;
  v26 = v16;
  if ( a2 != v17 )
  {
    std::_Uninitialized_move<Schema::Containers::Definition::ObjectSymlink *>(v18, a2, v11);
    v17 = a1[1];
    v13 = v16;
    v18 = a2;
    v25 = v11;
  }
  std::_Uninitialized_move<Schema::Containers::Definition::ObjectSymlink *>(v18, v17, v13);
  v19 = (char *)*a1;
  v24[1] = 0;
  if ( v19 )
  {
    v20 = (char *)a1[1];
    while ( v19 != v20 )
    {
      std::wstring::~wstring(v19 + 72);
      std::wstring::~wstring(v19 + 32);
      std::wstring::~wstring(v19);
      v19 += 112;
    }
    v21 = (char *)*a1;
    if ( (unsigned __int64)(16 * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 4)) < 0x1000 )
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
  a1[1] = &v11[112 * v8];
  a1[2] = &v11[v10];
  std::vector<Schema::Containers::Definition::ObjectSymlink>::_Reallocation_guard::~_Reallocation_guard(v24);
  return &v11[112 * v14];
}

```

## disassembly

```asm
0x18001be38  push    rbx
0x18001be3a  push    rbp
0x18001be3b  push    rsi
0x18001be3c  push    rdi
0x18001be3d  push    r12
0x18001be3f  push    r13
0x18001be41  push    r14
0x18001be43  push    r15
0x18001be45  sub     rsp, 58h
0x18001be49  mov     rbp, [rcx]
0x18001be4c  mov     rax, 6DB6DB6DB6DB6DB7h
0x18001be56  mov     r8, [rcx+8]
0x18001be5a  mov     r9, 249249249249249h
0x18001be64  sub     r8, rbp
0x18001be67  mov     r12, rdx
0x18001be6a  sar     r8, 4
0x18001be6e  mov     rdi, rcx
0x18001be71  imul    r8, rax
0x18001be75  cmp     r8, r9
0x18001be78  jz      loc_18001C078
0x18001be7e  mov     rcx, [rcx+10h]
0x18001be82  sub     rcx, rbp
0x18001be85  sar     rcx, 4
0x18001be89  imul    rcx, rax
0x18001be8d  mov     rax, r9
0x18001be90  mov     rdx, rcx
0x18001be93  shr     rdx, 1
0x18001be96  sub     rax, rdx
0x18001be99  cmp     rcx, rax
0x18001be9c  ja      loc_18001C07E
0x18001bea2  lea     r15, [r8+1]
0x18001bea6  lea     rax, [rcx+rdx]
0x18001beaa  mov     rsi, r15
0x18001bead  cmp     rax, r15
0x18001beb0  cmovnb  rsi, rax
0x18001beb4  cmp     rsi, r9
0x18001beb7  ja      loc_18001C07E
0x18001bebd  imul    r14, rsi, 70h ; 'p'
0x18001bec1  test    r14, r14
0x18001bec4  jnz     short loc_18001BECA
0x18001bec6  xor     ebx, ebx
0x18001bec8  jmp     short loc_18001BF07
0x18001beca  cmp     r14, 1000h
0x18001bed1  jb      short loc_18001BEFC
0x18001bed3  lea     rcx, [r14+27h]; Size
0x18001bed7  cmp     rcx, r14
0x18001beda  jbe     loc_18001C07E
0x18001bee0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bee5  test    rax, rax
0x18001bee8  jz      loc_18001C02D
0x18001beee  lea     rbx, [rax+27h]
0x18001bef2  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001bef6  mov     [rbx-8], rax
0x18001befa  jmp     short loc_18001BF07
0x18001befc  mov     rcx, r14; Size
0x18001beff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bf04  mov     rbx, rax
0x18001bf07  xorps   xmm0, xmm0
0x18001bf0a  mov     [rsp+98h+var_78], rdi
0x18001bf0f  mov     rcx, r12
0x18001bf12  mov     [rsp+98h+var_68], rsi
0x18001bf17  sub     rcx, rbp
0x18001bf1a  mov     rax, 4924924924924925h
0x18001bf24  imul    rcx
0x18001bf27  xor     eax, eax
0x18001bf29  mov     r8, rbx
0x18001bf2c  mov     r13, rdx
0x18001bf2f  sar     r13, 5
0x18001bf33  mov     rcx, r13
0x18001bf36  shr     rcx, 3Fh
0x18001bf3a  lea     edx, [rax+7]
0x18001bf3d  add     r13, rcx
0x18001bf40  imul    rcx, r13, 70h ; 'p'
0x18001bf44  add     rcx, rbx
0x18001bf47  mov     [rsp+98h+var_60], rcx
0x18001bf4c  mov     [rcx+40h], rax
0x18001bf50  lea     rbp, [rcx+70h]
0x18001bf54  mov     [rcx+68h], rax
0x18001bf58  movups  xmmword ptr [rcx], xmm0
0x18001bf5b  mov     [rcx+10h], rax
0x18001bf5f  mov     [rcx+18h], rdx
0x18001bf63  mov     [rcx], ax
0x18001bf66  movups  xmmword ptr [rcx+20h], xmm0
0x18001bf6a  mov     [rcx+30h], rax
0x18001bf6e  mov     [rcx+38h], rdx
0x18001bf72  mov     [rcx+20h], ax
0x18001bf76  movups  xmmword ptr [rcx+48h], xmm0
0x18001bf7a  mov     [rcx+58h], rax
0x18001bf7e  mov     [rcx+60h], rdx
0x18001bf82  mov     [rcx+48h], ax
0x18001bf86  mov     rdx, [rdi+8]
0x18001bf8a  mov     rcx, [rdi]
0x18001bf8d  mov     [rsp+98h+var_58], rbp
0x18001bf92  cmp     r12, rdx
0x18001bf95  jz      short loc_18001BFAE
0x18001bf97  mov     rdx, r12
0x18001bf9a  call    ??$_Uninitialized_move@PEAUObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@YAPEAUObjectSymlink@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@UObjectSymlink@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::ObjectSymlink *>(Schema::Containers::Definition::ObjectSymlink * const,Schema::Containers::Definition::ObjectSymlink * const,Schema::Containers::Definition::ObjectSymlink *,std::allocator<Schema::Containers::Definition::ObjectSymlink> &)
0x18001bf9f  mov     rdx, [rdi+8]
0x18001bfa3  mov     r8, rbp
0x18001bfa6  mov     rcx, r12
0x18001bfa9  mov     [rsp+98h+var_60], rbx
0x18001bfae  call    ??$_Uninitialized_move@PEAUObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@YAPEAUObjectSymlink@Definition@Containers@Schema@@QEAU1234@0PEAU1234@AEAV?$allocator@UObjectSymlink@Definition@Containers@Schema@@@0@@Z; std::_Uninitialized_move<Schema::Containers::Definition::ObjectSymlink *>(Schema::Containers::Definition::ObjectSymlink * const,Schema::Containers::Definition::ObjectSymlink * const,Schema::Containers::Definition::ObjectSymlink *,std::allocator<Schema::Containers::Definition::ObjectSymlink> &)
0x18001bfb3  mov     rsi, [rdi]
0x18001bfb6  mov     [rsp+98h+var_70], 0
0x18001bfbf  test    rsi, rsi
0x18001bfc2  jz      short loc_18001C03F
0x18001bfc4  mov     rbp, [rdi+8]
0x18001bfc8  jmp     short loc_18001BFE8
0x18001bfca  lea     rcx, [rsi+48h]
0x18001bfce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfd3  lea     rcx, [rsi+20h]
0x18001bfd7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfdc  mov     rcx, rsi
0x18001bfdf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bfe4  add     rsi, 70h ; 'p'
0x18001bfe8  cmp     rsi, rbp
0x18001bfeb  jnz     short loc_18001BFCA
0x18001bfed  mov     rcx, [rdi]
0x18001bff0  mov     rdx, 6DB6DB6DB6DB6DB7h
0x18001bffa  mov     rax, [rdi+10h]
0x18001bffe  sub     rax, rcx
0x18001c001  sar     rax, 4
0x18001c005  imul    rax, rdx
0x18001c009  imul    rdx, rax, 70h ; 'p'; unsigned __int64
0x18001c00d  cmp     rdx, 1000h
0x18001c014  jb      short loc_18001C034
0x18001c016  mov     rax, [rcx-8]
0x18001c01a  sub     rcx, rax
0x18001c01d  sub     rcx, 8
0x18001c021  cmp     rcx, 1Fh
0x18001c025  ja      short loc_18001C02D
0x18001c027  add     rdx, 27h ; '''
0x18001c02b  jmp     short loc_18001C037
0x18001c02d  mov     ecx, 5
0x18001c032  int     29h; Win8: RtlFailFast(ecx)
0x18001c034  mov     rax, rcx
0x18001c037  mov     rcx, rax; void *
0x18001c03a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c03f  mov     [rdi], rbx
0x18001c042  lea     rcx, [rsp+98h+var_78]
0x18001c047  imul    rax, r15, 70h ; 'p'
0x18001c04b  add     rax, rbx
0x18001c04e  mov     [rdi+8], rax
0x18001c052  lea     rax, [r14+rbx]
0x18001c056  mov     [rdi+10h], rax
0x18001c05a  call    ??1_Reallocation_guard@?$vector@UObjectSymlink@Definition@Containers@Schema@@V?$allocator@UObjectSymlink@Definition@Containers@Schema@@@std@@@std@@QEAA@XZ; std::vector<Schema::Containers::Definition::ObjectSymlink>::_Reallocation_guard::~_Reallocation_guard(void)
0x18001c05f  imul    rax, r13, 70h ; 'p'
0x18001c063  add     rax, rbx
0x18001c066  add     rsp, 58h
0x18001c06a  pop     r15
0x18001c06c  pop     r14
0x18001c06e  pop     r13
0x18001c070  pop     r12
0x18001c072  pop     rdi
0x18001c073  pop     rsi
0x18001c074  pop     rbp
0x18001c075  pop     rbx
0x18001c076  retn
0x18001c078  call    ?_Xlength@?$vector@UMountManagerMountPoint@Definition@Containers@Schema@@V?$allocator@UMountManagerMountPoint@Definition@Containers@Schema@@@std@@@std@@CAXXZ; std::vector<Schema::Containers::Definition::MountManagerMountPoint>::_Xlength(void)
0x18001c07e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
