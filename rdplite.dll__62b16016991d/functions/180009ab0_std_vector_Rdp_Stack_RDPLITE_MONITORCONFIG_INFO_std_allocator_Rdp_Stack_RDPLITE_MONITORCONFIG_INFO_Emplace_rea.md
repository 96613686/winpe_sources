# std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO,std::allocator<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(Rdp::Stack::RDPLITE_MONITORCONFIG_INFO * const,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO &&)

- ea: `0x180009ab0`
- end: `0x180009bb7`
- name: `??$_Emplace_reallocate@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEAAPEAURDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@QEAU234@$$QEAU234@@Z`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c0f0`
- `0x180016304`

## callees

- `0x180004958`
- `0x180008be0`
- `0x180009ab0`
- `0x180009d98`
- `0x18000aa30`
- `0x18000d1e0`
- `0x18000d250`
- `0x18002834c`

## pseudocode

```c
char *__fastcall std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Emplace_reallocate<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>(
        _QWORD *a1,
        _BYTE *a2,
        __int128 *a3)
{
  _BYTE *v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  __int64 size_of; // rax
  char *v11; // rax
  __int128 v12; // xmm0
  char *v13; // rdi
  char *v14; // rbp
  void *v15; // rcx
  _BYTE *v16; // r8
  _BYTE *v17; // rdx
  size_t v18; // r8
  _QWORD *v20; // [rsp+20h] [rbp-78h] BYREF
  __int64 v21; // [rsp+30h] [rbp-68h]
  char *v22; // [rsp+38h] [rbp-60h]
  _OWORD *v23; // [rsp+40h] [rbp-58h]

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 4;
  if ( v6 == 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<16>(v9);
  v11 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = *a3;
  v20 = a1;
  v21 = v9;
  v13 = v11;
  v14 = &v11[(a2 - v3) & 0xFFFFFFFFFFFFFFF0uLL];
  v15 = v11;
  *(_OWORD *)v14 = v12;
  v16 = (_BYTE *)a1[1];
  v17 = (_BYTE *)*a1;
  v23 = v14 + 16;
  v22 = v14;
  if ( a2 == v16 )
  {
    v18 = v16 - v17;
  }
  else
  {
    memmove_0(v11, v17, (size_t)&a2[-*a1]);
    v17 = a2;
    v18 = a1[1] - (_QWORD)a2;
    v22 = v13;
    v15 = v14 + 16;
  }
  memmove_0(v15, v17, v18);
  std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Change_array(a1, v13, v8, v9, v20, 0, v21, v22, v23);
  std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Reallocation_guard::~_Reallocation_guard(&v20);
  return v14;
}

```

## disassembly

```asm
0x180009ab0  push    rbx
0x180009ab2  push    rbp
0x180009ab3  push    rsi
0x180009ab4  push    rdi
0x180009ab5  push    r12
0x180009ab7  push    r13
0x180009ab9  push    r14
0x180009abb  push    r15
0x180009abd  sub     rsp, 58h
0x180009ac1  mov     rbp, [rcx]
0x180009ac4  mov     rbx, rcx
0x180009ac7  mov     rax, [rcx+8]
0x180009acb  mov     r12, r8
0x180009ace  sub     rax, rbp
0x180009ad1  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180009adb  sar     rax, 4
0x180009adf  mov     rsi, rdx
0x180009ae2  cmp     rax, rcx
0x180009ae5  jnz     short loc_180009AF4
0x180009ae7  lea     rcx, aVectorTooLong; "vector too long"
0x180009aee  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180009af4  lea     r15, [rax+1]
0x180009af8  mov     rcx, rbx
0x180009afb  mov     rdx, r15
0x180009afe  call    ?_Calculate_growth@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEBA_K_K@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Calculate_growth(unsigned __int64)
0x180009b03  mov     rcx, rax
0x180009b06  mov     r14, rax
0x180009b09  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x180009b0e  mov     rcx, rax
0x180009b11  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009b16  movups  xmm0, xmmword ptr [r12]
0x180009b1b  mov     rcx, rsi
0x180009b1e  mov     [rsp+98h+var_78], rbx
0x180009b23  sub     rcx, rbp
0x180009b26  mov     [rsp+98h+var_68], r14
0x180009b2b  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180009b2f  mov     rdi, rax
0x180009b32  lea     rbp, [rcx+rax]
0x180009b36  mov     rcx, rax; void *
0x180009b39  movdqu  xmmword ptr [rbp+0], xmm0
0x180009b3e  mov     r8, [rbx+8]
0x180009b42  lea     r13, [rbp+10h]
0x180009b46  mov     rdx, [rbx]; Src
0x180009b49  mov     [rsp+98h+var_58], r13
0x180009b4e  mov     [rsp+98h+var_60], rbp
0x180009b53  cmp     rsi, r8
0x180009b56  jnz     short loc_180009B5D
0x180009b58  sub     r8, rdx
0x180009b5b  jmp     short loc_180009B7A
0x180009b5d  mov     r8, rsi
0x180009b60  sub     r8, [rbx]; Size
0x180009b63  call    memmove_0
0x180009b68  mov     r8, [rbx+8]
0x180009b6c  mov     rdx, rsi; Src
0x180009b6f  sub     r8, rsi; Size
0x180009b72  mov     [rsp+98h+var_60], rdi
0x180009b77  mov     rcx, r13; void *
0x180009b7a  call    memmove_0
0x180009b7f  mov     r9, r14
0x180009b82  mov     [rsp+98h+var_70], 0
0x180009b8b  mov     r8, r15
0x180009b8e  mov     rdx, rdi
0x180009b91  mov     rcx, rbx
0x180009b94  call    ?_Change_array@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@AEAAXQEAURDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@_K1@Z; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Change_array(Rdp::Stack::RDPLITE_MONITORCONFIG_INFO * const,unsigned __int64,unsigned __int64)
0x180009b99  lea     rcx, [rsp+98h+var_78]
0x180009b9e  call    ??1_Reallocation_guard@?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@QEAA@XZ; std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>::_Reallocation_guard::~_Reallocation_guard(void)
0x180009ba3  mov     rax, rbp
0x180009ba6  add     rsp, 58h
0x180009baa  pop     r15
0x180009bac  pop     r14
0x180009bae  pop     r13
0x180009bb0  pop     r12
0x180009bb2  pop     rdi
0x180009bb3  pop     rsi
0x180009bb4  pop     rbp
0x180009bb5  pop     rbx
0x180009bb6  retn
```
