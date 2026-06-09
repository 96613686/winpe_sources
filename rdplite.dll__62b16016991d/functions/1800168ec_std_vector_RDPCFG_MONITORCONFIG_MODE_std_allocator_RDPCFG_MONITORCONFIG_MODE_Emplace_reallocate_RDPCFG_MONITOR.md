# std::vector<_RDPCFG_MONITORCONFIG_MODE,std::allocator<_RDPCFG_MONITORCONFIG_MODE>>::_Emplace_reallocate<_RDPCFG_MONITORCONFIG_MODE const &>(_RDPCFG_MONITORCONFIG_MODE * const,_RDPCFG_MONITORCONFIG_MODE const &)

- ea: `0x1800168ec`
- end: `0x180016a88`
- name: `??$_Emplace_reallocate@AEBU_RDPCFG_MONITORCONFIG_MODE@@@?$vector@U_RDPCFG_MONITORCONFIG_MODE@@V?$allocator@U_RDPCFG_MONITORCONFIG_MODE@@@std@@@std@@AEAAPEAU_RDPCFG_MONITORCONFIG_MODE@@QEAU2@AEBU2@@Z`
- size: `412`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001766c`

## callees

- `0x180004958`
- `0x1800049b8`
- `0x180007584`
- `0x180008be0`
- `0x1800168ec`
- `0x180017314`
- `0x18002834c`

## pseudocode

```c
char *__fastcall std::vector<_RDPCFG_MONITORCONFIG_MODE>::_Emplace_reallocate<_RDPCFG_MONITORCONFIG_MODE const &>(
        _QWORD *a1,
        _BYTE *a2,
        __int128 *a3)
{
  _BYTE *v3; // r15
  __int64 v5; // rsi
  __int64 v7; // rax
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rcx
  char *v13; // rax
  __int128 v14; // xmm0
  char *v15; // rdi
  void *v16; // rcx
  char *v17; // r15
  __int128 v18; // xmm1
  _BYTE *v19; // r8
  _BYTE *v20; // rdx
  size_t v21; // r8
  _BYTE *v22; // rcx
  _QWORD v24[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v25; // [rsp+38h] [rbp-60h]
  char *v26; // [rsp+40h] [rbp-58h]

  v3 = (_BYTE *)*a1;
  v5 = 0x5D1745D1745D174LL;
  v7 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[1] - *a1) >> 2);
  if ( v7 == 0x5D1745D1745D174LL )
    std::_Xlength_error("vector too long");
  v9 = v7 + 1;
  v10 = 0x2E8BA2E8BA2E8BA3LL * ((__int64)(a1[2] - (_QWORD)v3) >> 2);
  if ( v10 <= 0x5D1745D1745D174LL - (v10 >> 1) )
  {
    v11 = (v10 >> 1) + v10;
    v12 = v9;
    if ( v11 >= v9 )
      v12 = v11;
    if ( v12 > 0x5D1745D1745D174LL )
      std::_Throw_bad_array_new_length();
    v5 = v12;
  }
  v13 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(44 * v5);
  v14 = *a3;
  v15 = v13;
  v24[0] = a1;
  v24[2] = v5;
  v16 = v13;
  v17 = &v13[44 * ((a2 - v3) / 44)];
  v25 = v17;
  *(_OWORD *)v17 = v14;
  v18 = a3[1];
  v26 = v17 + 44;
  *((_OWORD *)v17 + 1) = v18;
  *(_OWORD *)(v17 + 28) = *(__int128 *)((char *)a3 + 28);
  v19 = (_BYTE *)a1[1];
  v20 = (_BYTE *)*a1;
  if ( a2 == v19 )
  {
    v21 = v19 - v20;
  }
  else
  {
    memmove_0(v13, v20, (size_t)&a2[-*a1]);
    v16 = v17 + 44;
    v21 = a1[1] - (_QWORD)a2;
    v25 = v15;
    v20 = a2;
  }
  memmove_0(v16, v20, v21);
  v22 = (_BYTE *)*a1;
  v24[1] = 0;
  if ( v22 )
    std::_Deallocate<16>(v22, 4 * ((__int64)(a1[2] - (_QWORD)v22) >> 2));
  *a1 = v15;
  a1[1] = &v15[44 * v9];
  a1[2] = &v15[44 * v5];
  std::vector<_RDPCFG_MONITORCONFIG_MODE>::_Reallocation_guard::~_Reallocation_guard(v24);
  return v17;
}

```

## disassembly

```asm
0x1800168ec  push    rbx
0x1800168ee  push    rbp
0x1800168ef  push    rsi
0x1800168f0  push    rdi
0x1800168f1  push    r12
0x1800168f3  push    r13
0x1800168f5  push    r14
0x1800168f7  push    r15
0x1800168f9  sub     rsp, 58h
0x1800168fd  mov     r15, [rcx]
0x180016900  mov     rbp, rdx
0x180016903  mov     rax, [rcx+8]
0x180016907  mov     rdx, 2E8BA2E8BA2E8BA3h
0x180016911  sub     rax, r15
0x180016914  mov     rsi, 5D1745D1745D174h
0x18001691e  sar     rax, 2
0x180016922  mov     r13, r8
0x180016925  imul    rax, rdx
0x180016929  mov     rbx, rcx
0x18001692c  cmp     rax, rsi
0x18001692f  jnz     short loc_18001693E
0x180016931  lea     rcx, aVectorTooLong; "vector too long"
0x180016938  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001693e  mov     rcx, [rcx+10h]
0x180016942  lea     r14, [rax+1]
0x180016946  sub     rcx, r15
0x180016949  mov     rax, rsi
0x18001694c  sar     rcx, 2
0x180016950  imul    rcx, rdx
0x180016954  mov     rdx, rcx
0x180016957  shr     rdx, 1
0x18001695a  sub     rax, rdx
0x18001695d  cmp     rcx, rax
0x180016960  ja      short loc_18001697E
0x180016962  lea     rax, [rdx+rcx]
0x180016966  mov     rcx, r14
0x180016969  cmp     rax, r14
0x18001696c  cmovnb  rcx, rax
0x180016970  cmp     rcx, rsi
0x180016973  jbe     short loc_18001697B
0x180016975  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18001697b  mov     rsi, rcx
0x18001697e  imul    r12, rsi, 2Ch ; ','
0x180016982  mov     rcx, r12
0x180016985  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001698a  movups  xmm0, xmmword ptr [r13+0]
0x18001698f  mov     rdi, rax
0x180016992  mov     [rsp+98h+var_78], rbx
0x180016997  mov     rcx, rbp
0x18001699a  mov     [rsp+98h+var_68], rsi
0x18001699f  sub     rcx, r15
0x1800169a2  mov     rax, 2E8BA2E8BA2E8BA3h
0x1800169ac  imul    rcx
0x1800169af  sar     rdx, 3
0x1800169b3  mov     rcx, rdx
0x1800169b6  shr     rcx, 3Fh
0x1800169ba  add     rdx, rcx
0x1800169bd  mov     rcx, rdi; void *
0x1800169c0  imul    r15, rdx, 2Ch ; ','
0x1800169c4  add     r15, rdi
0x1800169c7  mov     [rsp+98h+var_60], r15
0x1800169cc  movups  xmmword ptr [r15], xmm0
0x1800169d0  lea     rax, [r15+2Ch]
0x1800169d4  movups  xmm1, xmmword ptr [r13+10h]
0x1800169d9  mov     [rsp+98h+var_58], rax
0x1800169de  movups  xmmword ptr [r15+10h], xmm1
0x1800169e3  movups  xmm0, xmmword ptr [r13+1Ch]
0x1800169e8  movups  xmmword ptr [r15+1Ch], xmm0
0x1800169ed  mov     r8, [rbx+8]
0x1800169f1  mov     rdx, [rbx]; Src
0x1800169f4  cmp     rbp, r8
0x1800169f7  jnz     short loc_1800169FE
0x1800169f9  sub     r8, rdx
0x1800169fc  jmp     short loc_180016A1C
0x1800169fe  mov     r8, rbp
0x180016a01  sub     r8, [rbx]; Size
0x180016a04  call    memmove_0
0x180016a09  mov     r8, [rbx+8]
0x180016a0d  lea     rcx, [r15+2Ch]; void *
0x180016a11  sub     r8, rbp; Size
0x180016a14  mov     [rsp+98h+var_60], rdi
0x180016a19  mov     rdx, rbp; Src
0x180016a1c  call    memmove_0
0x180016a21  mov     rcx, [rbx]
0x180016a24  mov     [rsp+98h+var_70], 0
0x180016a2d  test    rcx, rcx
0x180016a30  jz      short loc_180016A54
0x180016a32  mov     rdx, [rbx+10h]
0x180016a36  mov     rax, 2E8BA2E8BA2E8BA3h
0x180016a40  sub     rdx, rcx
0x180016a43  sar     rdx, 2
0x180016a47  imul    rdx, rax
0x180016a4b  imul    rdx, 2Ch ; ','
0x180016a4f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180016a54  mov     [rbx], rdi
0x180016a57  imul    rcx, r14, 2Ch ; ','
0x180016a5b  add     rcx, rdi
0x180016a5e  mov     [rbx+8], rcx
0x180016a62  lea     rcx, [r12+rdi]
0x180016a66  mov     [rbx+10h], rcx
0x180016a6a  lea     rcx, [rsp+98h+var_78]
0x180016a6f  call    ??1_Reallocation_guard@?$vector@U_RDPCFG_MONITORCONFIG_MODE@@V?$allocator@U_RDPCFG_MONITORCONFIG_MODE@@@std@@@std@@QEAA@XZ; std::vector<_RDPCFG_MONITORCONFIG_MODE>::_Reallocation_guard::~_Reallocation_guard(void)
0x180016a74  mov     rax, r15
0x180016a77  add     rsp, 58h
0x180016a7b  pop     r15
0x180016a7d  pop     r14
0x180016a7f  pop     r13
0x180016a81  pop     r12
0x180016a83  pop     rdi
0x180016a84  pop     rsi
0x180016a85  pop     rbp
0x180016a86  pop     rbx
0x180016a87  retn
```
