# std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment &&)

- ea: `0x140013914`
- end: `0x140013b01`
- name: `??$_Emplace_reallocate@UCommandAdjustment@Image@Manager@Container@@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUCommandAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z`
- size: `493`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010448`

## callees

- `0x140002bd4`
- `0x140013914`
- `0x140014d84`
- `0x1400161c8`
- `0x14001f404`
- `0x14001ffcc`
- `0x140020224`

## pseudocode

```c
char *__fastcall std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // r14
  unsigned __int64 v6; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rdi
  size_t v12; // rcx
  _QWORD *v13; // rbx
  void *v14; // rax
  char *v15; // r14
  __int64 v16; // rax
  _OWORD *v17; // rcx
  _OWORD *v18; // r8
  _QWORD *v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *v23; // [rsp+20h] [rbp-78h] BYREF
  unsigned __int64 v24; // [rsp+30h] [rbp-68h]
  _QWORD *v25; // [rsp+38h] [rbp-60h]
  char *v26; // [rsp+40h] [rbp-58h]

  v3 = *a1;
  v6 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v6 == 0x666666666666666LL )
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Xlength();
  v8 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[2] - v3) >> 3);
  v9 = v8 >> 1;
  if ( v8 > 0x666666666666666LL - (v8 >> 1) )
    goto LABEL_21;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x666666666666666LL )
    goto LABEL_21;
  v12 = 40 * v11;
  if ( !(40 * v11) )
  {
    v13 = 0;
    goto LABEL_14;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_14;
  }
  if ( v12 + 39 < v12 )
LABEL_21:
    __scrt_throw_std_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    __fastfail(5u);
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_14:
  v23 = a1;
  v24 = v11;
  v15 = (char *)&v13[5 * ((a2 - v3) / 40)];
  *(_DWORD *)v15 = *(_DWORD *)a3;
  v16 = *(_QWORD *)(a3 + 8);
  v17 = (_OWORD *)(a3 + 24);
  v26 = v15 + 40;
  v18 = v15 + 24;
  if ( v16 == a3 + 24 )
  {
    *((_QWORD *)v15 + 1) = v18;
    *((_QWORD *)v15 + 2) = &v15[2 * ((*(_QWORD *)(a3 + 16) - (a3 + 8) - 16) >> 1) + 24];
    *v18 = *v17;
  }
  else
  {
    *((_QWORD *)v15 + 1) = v16;
    *((_QWORD *)v15 + 2) = *(_QWORD *)(a3 + 16);
    *(_QWORD *)v18 = *(_QWORD *)v17;
  }
  *(_QWORD *)(a3 + 8) = v17;
  *(_WORD *)v17 = 0;
  v19 = v13;
  *(_QWORD *)(a3 + 16) = v17;
  v20 = a1[1];
  v21 = *a1;
  v25 = v15;
  if ( a2 != v20 )
  {
    std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(v21, a2, v13);
    v20 = a1[1];
    v19 = v15 + 40;
    v21 = a2;
    v25 = v13;
  }
  std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(v21, v20, v19);
  std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(a1, v13, v10, v11, v23, 0, v24, v25, v26);
  std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(&v23);
  return v15;
}

```

## disassembly

```asm
0x140013914  push    rbx
0x140013916  push    rbp
0x140013917  push    rsi
0x140013918  push    rdi
0x140013919  push    r12
0x14001391b  push    r13
0x14001391d  push    r14
0x14001391f  push    r15
0x140013921  sub     rsp, 58h
0x140013925  mov     r14, [rcx]
0x140013928  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140013932  mov     r9, [rcx+8]
0x140013936  mov     r13, r8
0x140013939  sub     r9, r14
0x14001393c  mov     r8, 666666666666666h
0x140013946  sar     r9, 3
0x14001394a  mov     rbp, rdx
0x14001394d  imul    r9, rax
0x140013951  mov     rsi, rcx
0x140013954  cmp     r9, r8
0x140013957  jz      loc_140013AF5
0x14001395d  mov     rcx, [rcx+10h]
0x140013961  sub     rcx, r14
0x140013964  sar     rcx, 3
0x140013968  imul    rcx, rax
0x14001396c  mov     rax, r8
0x14001396f  mov     rdx, rcx
0x140013972  shr     rdx, 1
0x140013975  sub     rax, rdx
0x140013978  cmp     rcx, rax
0x14001397b  ja      loc_140013AFB
0x140013981  lea     r15, [r9+1]
0x140013985  lea     rax, [rcx+rdx]
0x140013989  mov     rdi, r15
0x14001398c  cmp     rax, r15
0x14001398f  cmovnb  rdi, rax
0x140013993  cmp     rdi, r8
0x140013996  ja      loc_140013AFB
0x14001399c  lea     rax, [rdi+rdi*4]
0x1400139a0  lea     rcx, ds:0[rax*8]; Size
0x1400139a8  test    rcx, rcx
0x1400139ab  jnz     short loc_1400139B1
0x1400139ad  xor     ebx, ebx
0x1400139af  jmp     short loc_1400139EF
0x1400139b1  cmp     rcx, 1000h
0x1400139b8  jb      short loc_1400139E7
0x1400139ba  lea     rax, [rcx+27h]
0x1400139be  cmp     rax, rcx
0x1400139c1  jbe     loc_140013AFB
0x1400139c7  mov     rcx, rax; Size
0x1400139ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400139cf  test    rax, rax
0x1400139d2  jnz     short loc_1400139D9
0x1400139d4  lea     ecx, [rax+5]
0x1400139d7  int     29h; Win8: RtlFailFast(ecx)
0x1400139d9  lea     rbx, [rax+27h]
0x1400139dd  and     rbx, 0FFFFFFFFFFFFFFE0h
0x1400139e1  mov     [rbx-8], rax
0x1400139e5  jmp     short loc_1400139EF
0x1400139e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400139ec  mov     rbx, rax
0x1400139ef  mov     rcx, rbp
0x1400139f2  mov     [rsp+98h+var_78], rsi
0x1400139f7  sub     rcx, r14
0x1400139fa  mov     [rsp+98h+var_68], rdi
0x1400139ff  mov     rax, 6666666666666667h
0x140013a09  imul    rcx
0x140013a0c  sar     rdx, 4
0x140013a10  mov     rcx, rdx
0x140013a13  shr     rcx, 3Fh
0x140013a17  add     rdx, rcx
0x140013a1a  lea     rax, [rdx+rdx*4]
0x140013a1e  lea     r14, [rbx+rax*8]
0x140013a22  mov     eax, [r13+0]
0x140013a26  lea     rdx, [r13+8]
0x140013a2a  mov     [r14], eax
0x140013a2d  mov     rax, [rdx]
0x140013a30  lea     rcx, [rdx+10h]
0x140013a34  lea     r12, [r14+28h]
0x140013a38  mov     [rsp+98h+var_58], r12
0x140013a3d  lea     r8, [r14+18h]
0x140013a41  cmp     rax, rcx
0x140013a44  jnz     short loc_140013A6E
0x140013a46  mov     [r14+8], r8
0x140013a4a  mov     rax, [rdx+8]
0x140013a4e  sub     rax, rdx
0x140013a51  sub     rax, 10h
0x140013a55  sar     rax, 1
0x140013a58  add     rax, 0Ch
0x140013a5c  lea     rax, [r14+rax*2]
0x140013a60  mov     [r14+10h], rax
0x140013a64  movups  xmm0, xmmword ptr [rcx]
0x140013a67  movdqu  xmmword ptr [r8], xmm0
0x140013a6c  jmp     short loc_140013A80
0x140013a6e  mov     [r14+8], rax
0x140013a72  mov     rax, [rdx+8]
0x140013a76  mov     [r14+10h], rax
0x140013a7a  mov     rax, [rcx]
0x140013a7d  mov     [r8], rax
0x140013a80  xor     eax, eax
0x140013a82  mov     [rdx], rcx
0x140013a85  mov     [rcx], ax
0x140013a88  mov     r8, rbx
0x140013a8b  mov     [rdx+8], rcx
0x140013a8f  mov     rdx, [rsi+8]
0x140013a93  mov     rcx, [rsi]
0x140013a96  mov     [rsp+98h+var_60], r14
0x140013a9b  cmp     rbp, rdx
0x140013a9e  jz      short loc_140013AB7
0x140013aa0  mov     rdx, rbp
0x140013aa3  call    ??$_Uninitialized_move@PEAUCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@YAPEAUCommandAdjustment@Image@Manager@Container@@QEAU1234@0PEAU1234@AEAV?$allocator@UCommandAdjustment@Image@Manager@Container@@@0@@Z; std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment *,std::allocator<Container::Manager::Image::CommandAdjustment> &)
0x140013aa8  mov     rdx, [rsi+8]
0x140013aac  mov     r8, r12
0x140013aaf  mov     rcx, rbp
0x140013ab2  mov     [rsp+98h+var_60], rbx
0x140013ab7  call    ??$_Uninitialized_move@PEAUCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@YAPEAUCommandAdjustment@Image@Manager@Container@@QEAU1234@0PEAU1234@AEAV?$allocator@UCommandAdjustment@Image@Manager@Container@@@0@@Z; std::_Uninitialized_move<Container::Manager::Image::CommandAdjustment *>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment *,std::allocator<Container::Manager::Image::CommandAdjustment> &)
0x140013abc  mov     r9, rdi
0x140013abf  mov     [rsp+98h+var_70], 0
0x140013ac8  mov     r8, r15
0x140013acb  mov     rdx, rbx
0x140013ace  mov     rcx, rsi
0x140013ad1  call    ?_Change_array@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAXQEAUCommandAdjustment@Image@Manager@Container@@_K1@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Change_array(Container::Manager::Image::CommandAdjustment * const,unsigned __int64,unsigned __int64)
0x140013ad6  lea     rcx, [rsp+98h+var_78]
0x140013adb  call    ??1_Reallocation_guard@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::CommandAdjustment>::_Reallocation_guard::~_Reallocation_guard(void)
0x140013ae0  mov     rax, r14
0x140013ae3  add     rsp, 58h
0x140013ae7  pop     r15
0x140013ae9  pop     r14
0x140013aeb  pop     r13
0x140013aed  pop     r12
0x140013aef  pop     rdi
0x140013af0  pop     rsi
0x140013af1  pop     rbp
0x140013af2  pop     rbx
0x140013af3  retn
0x140013af5  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Xlength(void)
0x140013afb  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
