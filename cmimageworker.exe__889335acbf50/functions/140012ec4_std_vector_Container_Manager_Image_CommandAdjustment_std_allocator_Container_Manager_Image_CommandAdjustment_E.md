# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::_Emplace_reallocate<>(Container::Manager::Image::CommandAdjustment * const)

- ea: `0x140012ec4`
- end: `0x140013076`
- name: `??$_Emplace_reallocate@$$V@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUCommandAdjustment@Image@Manager@Container@@QEAU2345@@Z`
- size: `434`
- prototype: `char *__fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010274`

## callees

- `0x140002bd4`
- `0x140012ec4`
- `0x140014d84`
- `0x1400161c8`
- `0x14001f404`
- `0x14001ffcc`
- `0x140020224`

## pseudocode

```c
char *__fastcall std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v2; // r14
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rdi
  size_t v10; // rcx
  _QWORD *v11; // rbx
  void *v12; // rax
  _QWORD *v13; // r8
  char *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v18; // [rsp+20h] [rbp-68h] BYREF
  unsigned __int64 v19; // [rsp+30h] [rbp-58h]
  _QWORD *v20; // [rsp+38h] [rbp-50h]
  char *v21; // [rsp+40h] [rbp-48h]

  v2 = *a1;
  v5 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v5 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
  v6 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[2] - v2) >> 3);
  v7 = v6 >> 1;
  if ( v6 > 0x666666666666666LL - (v6 >> 1) )
    goto LABEL_18;
  v8 = v5 + 1;
  v9 = v5 + 1;
  if ( v6 + v7 >= v5 + 1 )
    v9 = v6 + v7;
  if ( v9 > 0x666666666666666LL )
    goto LABEL_18;
  v10 = 40 * v9;
  if ( !(40 * v9) )
  {
    v11 = 0;
    goto LABEL_14;
  }
  if ( v10 < 0x1000 )
  {
    v11 = operator new(v10);
    goto LABEL_14;
  }
  if ( v10 + 39 < v10 )
LABEL_18:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v10 + 39);
  if ( !v12 )
    __fastfail(5u);
  v11 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v11 - 1) = v12;
LABEL_14:
  v18 = a1;
  v19 = v9;
  v13 = v11;
  v14 = (char *)&v11[5 * ((a2 - v2) / 40)];
  *(_QWORD *)v14 = 0;
  v21 = v14 + 40;
  *(_QWORD *)(v14 + 26) = 0;
  *(_DWORD *)(v14 + 34) = 0;
  *((_WORD *)v14 + 19) = 0;
  *((_QWORD *)v14 + 1) = v14 + 24;
  *((_QWORD *)v14 + 2) = v14 + 24;
  *((_WORD *)v14 + 12) = 0;
  v15 = a1[1];
  v16 = *a1;
  v20 = v14;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(v16, a2, v11);
    v15 = a1[1];
    v13 = v14 + 40;
    v16 = a2;
    v20 = v11;
  }
  std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(v16, v15, v13);
  std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(a1, v11, v8, v9, v18, 0, v19, v20, v21);
  std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(&v18);
  return v14;
}

```

## disassembly

```asm
0x140012ec4  push    rbx
0x140012ec6  push    rbp
0x140012ec7  push    rsi
0x140012ec8  push    rdi
0x140012ec9  push    r12
0x140012ecb  push    r14
0x140012ecd  push    r15
0x140012ecf  sub     rsp, 50h
0x140012ed3  mov     r14, [rcx]
0x140012ed6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140012ee0  mov     r8, [rcx+8]
0x140012ee4  mov     r9, 666666666666666h
0x140012eee  sub     r8, r14
0x140012ef1  mov     r15, rdx
0x140012ef4  sar     r8, 3
0x140012ef8  mov     rsi, rcx
0x140012efb  imul    r8, rax
0x140012eff  cmp     r8, r9
0x140012f02  jz      loc_14001306A
0x140012f08  mov     rcx, [rcx+10h]
0x140012f0c  sub     rcx, r14
0x140012f0f  sar     rcx, 3
0x140012f13  imul    rcx, rax
0x140012f17  mov     rax, r9
0x140012f1a  mov     rdx, rcx
0x140012f1d  shr     rdx, 1
0x140012f20  sub     rax, rdx
0x140012f23  cmp     rcx, rax
0x140012f26  ja      loc_140013070
0x140012f2c  lea     rbp, [r8+1]
0x140012f30  lea     rax, [rcx+rdx]
0x140012f34  mov     rdi, rbp
0x140012f37  cmp     rax, rbp
0x140012f3a  cmovnb  rdi, rax
0x140012f3e  cmp     rdi, r9
0x140012f41  ja      loc_140013070
0x140012f47  lea     rax, [rdi+rdi*4]
0x140012f4b  lea     rcx, ds:0[rax*8]; Size
0x140012f53  test    rcx, rcx
0x140012f56  jnz     short loc_140012F5C
0x140012f58  xor     ebx, ebx
0x140012f5a  jmp     short loc_140012F9A
0x140012f5c  cmp     rcx, 1000h
0x140012f63  jb      short loc_140012F92
0x140012f65  lea     rax, [rcx+27h]
0x140012f69  cmp     rax, rcx
0x140012f6c  jbe     loc_140013070
0x140012f72  mov     rcx, rax; Size
0x140012f75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012f7a  test    rax, rax
0x140012f7d  jnz     short loc_140012F84
0x140012f7f  lea     ecx, [rax+5]
0x140012f82  int     29h; Win8: RtlFailFast(ecx)
0x140012f84  lea     rbx, [rax+27h]
0x140012f88  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140012f8c  mov     [rbx-8], rax
0x140012f90  jmp     short loc_140012F9A
0x140012f92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012f97  mov     rbx, rax
0x140012f9a  mov     [rsp+88h+var_68], rsi
0x140012f9f  mov     rcx, r15
0x140012fa2  sub     rcx, r14
0x140012fa5  mov     [rsp+88h+var_58], rdi
0x140012faa  mov     rax, 6666666666666667h
0x140012fb4  mov     r8, rbx
0x140012fb7  imul    rcx
0x140012fba  sar     rdx, 4
0x140012fbe  mov     rcx, rdx
0x140012fc1  shr     rcx, 3Fh
0x140012fc5  add     rdx, rcx
0x140012fc8  lea     rax, [rdx+rdx*4]
0x140012fcc  lea     r14, [rbx+rax*8]
0x140012fd0  xor     eax, eax
0x140012fd2  mov     qword ptr [r14], 0
0x140012fd9  lea     rcx, [r14+18h]
0x140012fdd  lea     r12, [r14+28h]
0x140012fe1  mov     [rsp+88h+var_48], r12
0x140012fe6  mov     qword ptr [r14+1Ah], 0
0x140012fee  mov     dword ptr [r14+22h], 0
0x140012ff6  mov     [r14+26h], ax
0x140012ffb  mov     [r14+8], rcx
0x140012fff  mov     [r14+10h], rcx
0x140013003  mov     [rcx], ax
0x140013006  mov     rdx, [rsi+8]
0x14001300a  mov     rcx, [rsi]
0x14001300d  mov     [rsp+88h+var_50], r14
0x140013012  cmp     r15, rdx
0x140013015  jz      short loc_14001302E
0x140013017  mov     rdx, r15
0x14001301a  call    ??$_Uninitialized_move@PEAUCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@YAPEAUCommandAdjustment@Image@Manager@Container@@QEAU1234@0PEAU1234@AEAV?$allocator@UCommandAdjustment@Image@Manager@Container@@@0@@Z; std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment *,std::allocator<Container::Manager::Image::CommandAdjustment> &)
0x14001301f  mov     rdx, [rsi+8]
0x140013023  mov     r8, r12
0x140013026  mov     rcx, r15
0x140013029  mov     [rsp+88h+var_50], rbx
0x14001302e  call    ??$_Uninitialized_move@PEAUCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@YAPEAUCommandAdjustment@Image@Manager@Container@@QEAU1234@0PEAU1234@AEAV?$allocator@UCommandAdjustment@Image@Manager@Container@@@0@@Z; std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment *,std::allocator<Container::Manager::Image::CommandAdjustment> &)
0x140013033  mov     r9, rdi
0x140013036  mov     [rsp+88h+var_60], 0
0x14001303f  mov     r8, rbp
0x140013042  mov     rdx, rbx
0x140013045  mov     rcx, rsi
0x140013048  call    ?_Change_array@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAUCommandAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(Container::Manager::Image::CommandAdjustment * const,unsigned __int64,unsigned __int64)
0x14001304d  lea     rcx, [rsp+88h+var_68]
0x140013052  call    ??1_Reallocation_guard@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(void)
0x140013057  mov     rax, r14
0x14001305a  add     rsp, 50h
0x14001305e  pop     r15
0x140013060  pop     r14
0x140013062  pop     r12
0x140013064  pop     rdi
0x140013065  pop     rsi
0x140013066  pop     rbp
0x140013067  pop     rbx
0x140013068  retn
0x14001306a  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Xlength(void)
0x140013070  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
