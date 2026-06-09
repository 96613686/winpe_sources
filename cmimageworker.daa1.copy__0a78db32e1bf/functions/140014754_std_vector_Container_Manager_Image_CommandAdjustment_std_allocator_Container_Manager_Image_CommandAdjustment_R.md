# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x140014754`
- end: `0x1400148c4`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140010274`

## callees

- `0x140002bd4`
- `0x140014754`
- `0x140014d84`
- `0x1400161c8`
- `0x14001f404`
- `0x14001ffcc`

## pseudocode

```c
__int64 __fastcall std::vector<Container::Manager::Image::CommandAdjustment>::_Resize_reallocate<std::_Value_init_tag>(
        _QWORD *a1)
{
  __int64 v1; // rbp
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  unsigned __int64 v6; // rbx
  size_t v7; // rcx
  _QWORD *v8; // rdi
  unsigned __int64 v9; // r14
  char *v10; // rdx
  unsigned __int64 v11; // r10
  _QWORD *v12; // r9
  _WORD *v13; // rcx
  __int64 v14; // rcx
  void *v16; // rax
  _QWORD *v17; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v18; // [rsp+30h] [rbp-58h]
  char *v19; // [rsp+38h] [rbp-50h]
  char *v20; // [rsp+40h] [rbp-48h]

  v1 = *a1;
  v3 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[2] - *a1) >> 3);
  v4 = v3 >> 1;
  if ( v3 > 0x666666666666666LL - (v3 >> 1) )
    goto LABEL_17;
  v5 = a1[1];
  v6 = v3 + v4;
  if ( !(v3 + v4) )
  {
    v6 = 1;
    v7 = 40;
LABEL_4:
    v8 = operator new(v7);
    goto LABEL_5;
  }
  if ( v6 > 0x666666666666666LL )
    goto LABEL_17;
  v7 = 40 * v6;
  if ( !(40 * v6) )
  {
    v8 = 0;
    goto LABEL_5;
  }
  if ( v7 < 0x1000 )
    goto LABEL_4;
  if ( v7 + 39 < v7 )
LABEL_17:
    __scrt_throw_std_bad_array_new_length();
  v16 = operator new(v7 + 39);
  if ( !v16 )
    __fastfail(5u);
  v8 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v8 - 1) = v16;
LABEL_5:
  v17 = a1;
  v9 = 0xCCCCCCCCCCCCCCCDuLL * ((v5 - v1) >> 3);
  v18 = v6;
  v10 = (char *)&v8[5 * v9];
  v19 = v10;
  v11 = 1 - v9;
  if ( v9 != 1 )
  {
    v12 = v10 + 8;
    do
    {
      v13 = v12 + 2;
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 4) = 0;
      v10 += 40;
      *v12 = v12 + 2;
      v12[1] = v12 + 2;
      v12 += 5;
      *v13 = 0;
      --v11;
    }
    while ( v11 );
  }
  v14 = *a1;
  v20 = v10;
  std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(v14, a1[1], v8);
  std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(a1, v8, 1, v6, v17, 0, v18, v19, v20);
  return std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(&v17);
}

```

## disassembly

```asm
0x140014754  push    rbx
0x140014756  push    rbp
0x140014757  push    rsi
0x140014758  push    rdi
0x140014759  push    r12
0x14001475b  push    r14
0x14001475d  push    r15
0x14001475f  sub     rsp, 50h
0x140014763  mov     rbp, [rcx]
0x140014766  mov     rsi, rcx
0x140014769  mov     rdx, [rcx+10h]
0x14001476d  mov     r12, 0CCCCCCCCCCCCCCCDh
0x140014777  sub     rdx, rbp
0x14001477a  mov     r8, 666666666666666h
0x140014784  sar     rdx, 3
0x140014788  mov     rax, r8
0x14001478b  imul    rdx, r12
0x14001478f  mov     rcx, rdx
0x140014792  shr     rcx, 1
0x140014795  sub     rax, rcx
0x140014798  cmp     rdx, rax
0x14001479b  ja      loc_1400148BE
0x1400147a1  mov     r14, [rsi+8]
0x1400147a5  lea     rbx, [rdx+rcx]
0x1400147a9  mov     r15d, 1
0x1400147af  cmp     rbx, r15
0x1400147b2  jnb     loc_140014868
0x1400147b8  mov     ebx, r15d
0x1400147bb  lea     ecx, [r15+27h]; Size
0x1400147bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400147c4  mov     rdi, rax
0x1400147c7  sub     r14, rbp
0x1400147ca  mov     [rsp+88h+var_68], rsi
0x1400147cf  sar     r14, 3
0x1400147d3  mov     r10, r15
0x1400147d6  imul    r14, r12
0x1400147da  mov     [rsp+88h+var_58], rbx
0x1400147df  lea     rcx, [r14+r14*4]
0x1400147e3  lea     rdx, [rdi+rcx*8]
0x1400147e7  mov     [rsp+88h+var_50], rdx
0x1400147ec  sub     r10, r14
0x1400147ef  jz      short loc_140014820
0x1400147f1  lea     r9, [rdx+8]
0x1400147f5  lea     rcx, [r9+10h]
0x1400147f9  xor     eax, eax
0x1400147fb  xorps   xmm0, xmm0
0x1400147fe  movups  xmmword ptr [rdx], xmm0
0x140014801  movups  xmmword ptr [rdx+10h], xmm0
0x140014805  mov     [rdx+20h], rax
0x140014809  add     rdx, 28h ; '('
0x14001480d  mov     [r9], rcx
0x140014810  mov     [r9+8], rcx
0x140014814  lea     r9, [r9+28h]
0x140014818  mov     [rcx], ax
0x14001481b  sub     r10, r15
0x14001481e  jnz     short loc_1400147F5
0x140014820  mov     rcx, [rsi]
0x140014823  mov     r8, rdi
0x140014826  mov     [rsp+88h+var_48], rdx
0x14001482b  mov     rdx, [rsi+8]
0x14001482f  call    ??$_Uninitialized_move@PEAUCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@YAPEAUCommandAdjustment@Image@Manager@Container@@QEAU1234@0PEAU1234@AEAV?$allocator@UCommandAdjustment@Image@Manager@Container@@@0@@Z; std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment *,std::allocator<Container::Manager::Image::CommandAdjustment> &)
0x140014834  mov     r9, rbx
0x140014837  mov     [rsp+88h+var_60], 0
0x140014840  mov     r8, r15
0x140014843  mov     rdx, rdi
0x140014846  mov     rcx, rsi
0x140014849  call    ?_Change_array@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAUCommandAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(Container::Manager::Image::CommandAdjustment * const,unsigned __int64,unsigned __int64)
0x14001484e  lea     rcx, [rsp+88h+var_68]
0x140014853  call    ??1_Reallocation_guard@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(void)
0x140014858  add     rsp, 50h
0x14001485c  pop     r15
0x14001485e  pop     r14
0x140014860  pop     r12
0x140014862  pop     rdi
0x140014863  pop     rsi
0x140014864  pop     rbp
0x140014865  pop     rbx
0x140014866  retn
0x140014868  cmp     rbx, r8
0x14001486b  ja      short loc_1400148BE
0x14001486d  lea     rax, [rbx+rbx*4]
0x140014871  lea     rcx, ds:0[rax*8]
0x140014879  test    rcx, rcx
0x14001487c  jnz     short loc_140014885
0x14001487e  xor     edi, edi
0x140014880  jmp     loc_1400147C7
0x140014885  cmp     rcx, 1000h
0x14001488c  jb      loc_1400147BF
0x140014892  lea     rax, [rcx+27h]
0x140014896  cmp     rax, rcx
0x140014899  jbe     short loc_1400148BE
0x14001489b  mov     rcx, rax; Size
0x14001489e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400148a3  test    rax, rax
0x1400148a6  jnz     short loc_1400148AD
0x1400148a8  lea     ecx, [rax+5]
0x1400148ab  int     29h; Win8: RtlFailFast(ecx)
0x1400148ad  lea     rdi, [rax+27h]
0x1400148b1  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1400148b5  mov     [rdi-8], rax
0x1400148b9  jmp     loc_1400147C7
0x1400148be  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
