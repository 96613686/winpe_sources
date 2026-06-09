# std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>>(std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,web::json::value>>> const &)

- ea: `0x1400061a0`
- end: `0x140006319`
- name: `??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@QEAA@AEBV01@@Z`
- size: `377`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140007280`

## callees

- `0x140002f84`
- `0x1400061a0`
- `0x140007030`
- `0x140013dd0`
- `0x1400147cc`
- `0x14003e010`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::pair<std::wstring,web::json::value>>::vector<std::pair<std::wstring,web::json::value>>(
        _QWORD *a1,
        __int64 *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdi
  _QWORD *v6; // rbx
  void *v7; // rax
  __int64 v8; // rbp
  __int64 i; // rsi
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v14; // [rsp+88h] [rbp+10h]
  _QWORD *v15; // [rsp+90h] [rbp+18h]

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v4 = (a2[1] - *a2) / 40;
  if ( v4 )
  {
    if ( v4 > 0x666666666666666LL )
      std::vector<std::pair<std::wstring,web::json::value>>::_Xlength();
    v5 = 40 * v4;
    if ( 40 * v4 )
    {
      if ( v5 < 0x1000 )
      {
        v6 = operator new(40 * v4);
      }
      else
      {
        if ( v5 + 39 < v5 )
          __scrt_throw_std_bad_array_new_length();
        v7 = operator new(v5 + 39);
        if ( !v7 )
          __fastfail(5u);
        v6 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v6 - 1) = v7;
      }
    }
    else
    {
      v6 = 0;
    }
    *a1 = v6;
    a1[1] = v6;
    a1[2] = &v6[v5 / 8];
    v14 = a1;
    v8 = a2[1];
    for ( i = *a2; i != v8; i += 40 )
    {
      v15 = v6;
      std::wstring::wstring(v6, i);
      v10 = (__int64 *)(***(__int64 (__fastcall ****)(_QWORD, __int64 *))(i + 32))(*(_QWORD *)(i + 32), &v13);
      v11 = *v10;
      *v10 = 0;
      v6[4] = v11;
      if ( v13 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 192LL))(v13, 1);
      v6 += 5;
    }
    a1[1] = v6;
  }
  return a1;
}

```

## disassembly

```asm
0x1400061a0  push    rbx
0x1400061a2  push    rbp
0x1400061a3  push    rsi
0x1400061a4  push    rdi
0x1400061a5  push    r14
0x1400061a7  push    r15
0x1400061a9  sub     rsp, 48h
0x1400061ad  mov     rsi, rdx
0x1400061b0  mov     r14, rcx
0x1400061b3  xor     r15d, r15d
0x1400061b6  mov     [rcx], r15
0x1400061b9  mov     [rcx+8], r15
0x1400061bd  mov     [rcx+10h], r15
0x1400061c1  mov     r8, [rdx+8]
0x1400061c5  sub     r8, [rdx]
0x1400061c8  mov     rax, 6666666666666667h
0x1400061d2  imul    r8
0x1400061d5  sar     rdx, 4
0x1400061d9  mov     rax, rdx
0x1400061dc  shr     rax, 3Fh
0x1400061e0  add     rdx, rax
0x1400061e3  jz      loc_1400062FD
0x1400061e9  mov     rax, 666666666666666h
0x1400061f3  cmp     rdx, rax
0x1400061f6  ja      loc_140006313
0x1400061fc  lea     rax, [rdx+rdx*4]
0x140006200  lea     rdi, ds:0[rax*8]
0x140006208  test    rdi, rdi
0x14000620b  jnz     short loc_140006212
0x14000620d  mov     ebx, r15d
0x140006210  jmp     short loc_140006252
0x140006212  cmp     rdi, 1000h
0x140006219  jb      short loc_140006247
0x14000621b  lea     rcx, [rdi+27h]; Size
0x14000621f  cmp     rcx, rdi
0x140006222  jbe     loc_14000630D
0x140006228  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000622d  test    rax, rax
0x140006230  jnz     short loc_140006239
0x140006232  mov     ecx, 5
0x140006237  int     29h; Win8: RtlFailFast(ecx)
0x140006239  lea     rbx, [rax+27h]
0x14000623d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x140006241  mov     [rbx-8], rax
0x140006245  jmp     short loc_140006252
0x140006247  mov     rcx, rdi; Size
0x14000624a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000624f  mov     rbx, rax
0x140006252  mov     [r14], rbx
0x140006255  mov     [r14+8], rbx
0x140006259  lea     rax, [rdi+rbx]
0x14000625d  mov     [r14+10h], rax
0x140006261  mov     [rsp+78h+arg_8], r14
0x140006269  mov     rbp, [rsi+8]
0x14000626d  mov     rsi, [rsi]
0x140006270  mov     [rsp+78h+var_58], rbx
0x140006275  mov     [rsp+78h+var_50], rbx
0x14000627a  mov     [rsp+78h+var_48], r14
0x14000627f  cmp     rsi, rbp
0x140006282  jz      short loc_1400062F9
0x140006284  nop     dword ptr [rax+00h]
0x140006288  nop     dword ptr [rax+rax+00000000h]
0x140006290  mov     [rsp+78h+arg_10], rbx
0x140006298  mov     rdx, rsi
0x14000629b  mov     rcx, rbx
0x14000629e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400062a3  nop
0x1400062a4  mov     rcx, [rsi+20h]
0x1400062a8  mov     rax, [rcx]
0x1400062ab  lea     rdx, [rsp+78h+arg_0]
0x1400062b3  mov     rax, [rax]
0x1400062b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062bb  mov     rcx, [rax]
0x1400062be  mov     [rax], r15
0x1400062c1  mov     [rbx+20h], rcx
0x1400062c5  mov     rcx, [rsp+78h+arg_0]
0x1400062cd  test    rcx, rcx
0x1400062d0  jz      short loc_1400062E7
0x1400062d2  mov     rax, [rcx]
0x1400062d5  mov     edx, 1
0x1400062da  mov     rax, [rax+0C0h]
0x1400062e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062e6  nop
0x1400062e7  add     rbx, 28h ; '('
0x1400062eb  mov     [rsp+78h+var_50], rbx
0x1400062f0  add     rsi, 28h ; '('
0x1400062f4  cmp     rsi, rbp
0x1400062f7  jnz     short loc_140006290
0x1400062f9  mov     [r14+8], rbx
0x1400062fd  mov     rax, r14
0x140006300  add     rsp, 48h
0x140006304  pop     r15
0x140006306  pop     r14
0x140006308  pop     rdi
0x140006309  pop     rsi
0x14000630a  pop     rbp
0x14000630b  pop     rbx
0x14000630c  retn
0x14000630d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x140006313  call    ?_Xlength@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Vvalue@json@web@@@std@@@2@@std@@CAXXZ; std::vector<std::pair<std::wstring,web::json::value>>::_Xlength(void)
```
