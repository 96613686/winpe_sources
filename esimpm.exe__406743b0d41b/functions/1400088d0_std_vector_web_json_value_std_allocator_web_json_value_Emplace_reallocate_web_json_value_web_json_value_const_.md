# std::vector<web::json::value,std::allocator<web::json::value>>::_Emplace_reallocate<web::json::value>(web::json::value * const,web::json::value &&)

- ea: `0x1400088d0`
- end: `0x140008ae8`
- name: `??$_Emplace_reallocate@Vvalue@json@web@@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAPEAVvalue@json@web@@QEAV234@$$QEAV234@@Z`
- size: `536`
- prototype: `char *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140009db0`

## callees

- `0x140002f84`
- `0x1400064b0`
- `0x1400066e0`
- `0x140006db0`
- `0x140007030`
- `0x1400088d0`
- `0x140013dd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall std::vector<web::json::value>::_Emplace_reallocate<web::json::value>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r15
  size_t v11; // rcx
  _QWORD *v12; // r14
  void *v13; // rax
  __int64 v14; // r13
  __int64 v15; // rsi
  __int64 v16; // rbx
  _QWORD *i; // rdi
  __int64 v18; // rsi
  _QWORD *j; // rsi
  __int64 v20; // rbp
  char *k; // rbx
  _QWORD *v23; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v24; // [rsp+30h] [rbp-48h]
  char *v25; // [rsp+38h] [rbp-40h]
  __int64 v26; // [rsp+40h] [rbp-38h]
  __int64 v27; // [rsp+80h] [rbp+8h]

  v3 = *a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
  v8 = (a1[2] - v3) >> 3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_24;
  v27 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v10 = v8 + v9;
  if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_24;
  v11 = 8 * v10;
  if ( !(8 * v10) )
  {
    v12 = 0;
    goto LABEL_14;
  }
  if ( v11 < 0x1000 )
  {
    v12 = operator new(v11);
    goto LABEL_14;
  }
  if ( v11 + 39 < v11 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    __fastfail(5u);
  v12 = (_QWORD *)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_14:
  v23 = a1;
  v24 = v10;
  v14 = (a2 - v3) >> 3;
  v26 = (__int64)&v12[v14 + 1];
  web::json::value::value(&v12[v14], a3);
  v15 = a1[1];
  v25 = (char *)&v12[v14];
  v16 = *a1;
  if ( a2 == v15 )
  {
    for ( i = v12; v16 != v15; v16 += 8 )
      web::json::value::value(i++, v16);
    v18 = v14;
  }
  else
  {
    for ( j = v12; v16 != a2; v16 += 8 )
      web::json::value::value(j++, v16);
    v20 = a1[1];
    v18 = v14;
    v25 = (char *)v12;
    for ( k = (char *)&v12[v14 + 1]; a2 != v20; a2 += 8 )
    {
      web::json::value::value(k, a2);
      k += 8;
    }
  }
  std::vector<web::json::value>::_Change_array(a1, v12, v27, v10, v23, 0, v24, v25, v26);
  std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(&v23);
  return (char *)&v12[v18];
}

```

## disassembly

```asm
0x1400088d0  push    rbx
0x1400088d2  push    rsi
0x1400088d3  push    rdi
0x1400088d4  push    r12
0x1400088d6  sub     rsp, 58h
0x1400088da  mov     rbx, [rcx]
0x1400088dd  mov     rdi, rdx
0x1400088e0  mov     rdx, [rcx+8]
0x1400088e4  mov     r9, 1FFFFFFFFFFFFFFFh
0x1400088ee  sub     rdx, rbx
0x1400088f1  mov     rsi, r8
0x1400088f4  sar     rdx, 3
0x1400088f8  mov     r12, rcx
0x1400088fb  cmp     rdx, r9
0x1400088fe  jz      loc_140008ADC
0x140008904  mov     rcx, [rcx+10h]
0x140008908  mov     rax, r9
0x14000890b  sub     rcx, rbx
0x14000890e  mov     [rsp+78h+arg_18], r14
0x140008916  sar     rcx, 3
0x14000891a  mov     r8, rcx
0x14000891d  mov     [rsp+78h+var_28], r15
0x140008922  shr     r8, 1
0x140008925  sub     rax, r8
0x140008928  cmp     rcx, rax
0x14000892b  ja      loc_140008AE2
0x140008931  inc     rdx
0x140008934  lea     rax, [rcx+r8]
0x140008938  cmp     rax, rdx
0x14000893b  mov     [rsp+78h+arg_0], rdx
0x140008943  mov     r15, rdx
0x140008946  cmovnb  r15, rax
0x14000894a  cmp     r15, r9
0x14000894d  ja      loc_140008AE2
0x140008953  lea     rcx, ds:0[r15*8]; Size
0x14000895b  test    rcx, rcx
0x14000895e  jnz     short loc_140008965
0x140008960  xor     r14d, r14d
0x140008963  jmp     short loc_1400089A5
0x140008965  cmp     rcx, 1000h
0x14000896c  jb      short loc_14000899D
0x14000896e  lea     rax, [rcx+27h]
0x140008972  cmp     rax, rcx
0x140008975  jbe     loc_140008AE2
0x14000897b  mov     rcx, rax; Size
0x14000897e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008983  test    rax, rax
0x140008986  jnz     short loc_14000898F
0x140008988  mov     ecx, 5
0x14000898d  int     29h; Win8: RtlFailFast(ecx)
0x14000898f  lea     r14, [rax+27h]
0x140008993  and     r14, 0FFFFFFFFFFFFFFE0h
0x140008997  mov     [r14-8], rax
0x14000899b  jmp     short loc_1400089A5
0x14000899d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400089a2  mov     r14, rax
0x1400089a5  mov     [rsp+78h+arg_10], r13
0x1400089ad  mov     rdx, rsi
0x1400089b0  mov     r13, rdi
0x1400089b3  mov     [rsp+78h+var_58], r12
0x1400089b8  sub     r13, rbx
0x1400089bb  mov     [rsp+78h+var_48], r15
0x1400089c0  sar     r13, 3
0x1400089c4  lea     rbx, [r14+r13*8]
0x1400089c8  lea     rcx, [rbx+8]
0x1400089cc  mov     [rsp+78h+var_38], rcx
0x1400089d1  mov     rcx, rbx
0x1400089d4  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x1400089d9  mov     rsi, [r12+8]
0x1400089de  mov     [rsp+78h+var_40], rbx
0x1400089e3  mov     rbx, [r12]
0x1400089e7  cmp     rdi, rsi
0x1400089ea  jnz     short loc_140008A16
0x1400089ec  mov     rdi, r14
0x1400089ef  cmp     rbx, rsi
0x1400089f2  jz      short loc_140008A0C
0x1400089f4  mov     rdx, rbx
0x1400089f7  mov     rcx, rdi
0x1400089fa  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x1400089ff  add     rdi, 8
0x140008a03  add     rbx, 8
0x140008a07  cmp     rbx, rsi
0x140008a0a  jnz     short loc_1400089F4
0x140008a0c  lea     rsi, ds:0[r13*8]
0x140008a14  jmp     short loc_140008A90
0x140008a16  mov     [rsp+78h+arg_8], rbp
0x140008a1e  mov     rsi, r14
0x140008a21  cmp     rbx, rdi
0x140008a24  jz      short loc_140008A48
0x140008a26  nop     word ptr [rax+rax+00000000h]
0x140008a30  mov     rdx, rbx
0x140008a33  mov     rcx, rsi
0x140008a36  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x140008a3b  add     rsi, 8
0x140008a3f  add     rbx, 8
0x140008a43  cmp     rbx, rdi
0x140008a46  jnz     short loc_140008A30
0x140008a48  mov     rbp, [r12+8]
0x140008a4d  lea     rsi, ds:0[r13*8]
0x140008a55  lea     rbx, [rsi+8]
0x140008a59  mov     [rsp+78h+var_40], r14
0x140008a5e  add     rbx, r14
0x140008a61  cmp     rdi, rbp
0x140008a64  jz      short loc_140008A88
0x140008a66  nop     word ptr [rax+rax+00000000h]
0x140008a70  mov     rdx, rdi
0x140008a73  mov     rcx, rbx
0x140008a76  call    ??0value@json@web@@QEAA@$$QEAV012@@Z; web::json::value::value(web::json::value &&)
0x140008a7b  add     rbx, 8
0x140008a7f  add     rdi, 8
0x140008a83  cmp     rdi, rbp
0x140008a86  jnz     short loc_140008A70
0x140008a88  mov     rbp, [rsp+78h+arg_8]
0x140008a90  mov     r8, [rsp+78h+arg_0]
0x140008a98  mov     r9, r15
0x140008a9b  mov     rdx, r14
0x140008a9e  mov     [rsp+78h+var_50], 0
0x140008aa7  mov     rcx, r12
0x140008aaa  call    ?_Change_array@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXQEAVvalue@json@web@@_K1@Z; std::vector<web::json::value>::_Change_array(web::json::value * const,unsigned __int64,unsigned __int64)
0x140008aaf  lea     rcx, [rsp+78h+var_58]
0x140008ab4  call    ??1_Reallocation_guard@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@XZ; std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(void)
0x140008ab9  mov     r13, [rsp+78h+arg_10]
0x140008ac1  lea     rax, [rsi+r14]
0x140008ac5  mov     r14, [rsp+78h+arg_18]
0x140008acd  mov     r15, [rsp+78h+var_28]
0x140008ad2  add     rsp, 58h
0x140008ad6  pop     r12
0x140008ad8  pop     rdi
0x140008ad9  pop     rsi
0x140008ada  pop     rbx
0x140008adb  retn
0x140008adc  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
0x140008ae2  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
