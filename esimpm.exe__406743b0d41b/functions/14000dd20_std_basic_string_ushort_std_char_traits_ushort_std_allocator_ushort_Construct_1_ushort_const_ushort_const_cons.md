# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x14000dd20`
- end: `0x14000de01`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `225`
- prototype: `void *__fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `31`
- callee_count: `6`
- tags: ``

## callers

- `0x1400025b0`
- `0x1400025f0`
- `0x1400028c0`
- `0x140002900`
- `0x14000a940`
- `0x14000de08`
- `0x14001f988`
- `0x140022150`
- `0x140022200`
- `0x14002595c`
- `0x14002dfac`
- `0x14002e734`
- `0x14002f654`
- `0x14002f9e0`
- `0x1400312d4`
- `0x14003154c`
- `0x140031c00`
- `0x140031e98`
- `0x140032218`
- `0x140032434`
- `0x140038e24`
- `0x1400393ec`
- `0x14003a898`
- `0x14003a9d8`
- `0x14003aba0`
- `0x14003adc4`
- `0x14003b25c`
- `0x14003b424`
- `0x14003b63c`
- `0x14003b8bc`
- `0x14003ba84`

## callees

- `0x140002f84`
- `0x140003b10`
- `0x14000dce0`
- `0x14000dd20`
- `0x140013dd0`
- `0x140013e64`

## pseudocode

```c
void *__fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbp
  __int64 v7; // rbx
  void *result; // rax
  size_t v9; // rcx
  char *v10; // rax
  char *v11; // rdi
  size_t v12; // rbx

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 <= 7 )
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    result = memcpy_0(a1, a2, 2 * a3);
    *(_WORD *)((char *)a1 + v7) = 0;
    return result;
  }
  if ( (a3 | 7) > 0x7FFFFFFFFFFFFFFELL )
  {
    v9 = -2;
LABEL_6:
    if ( v9 < 0x1000 )
      v10 = (char *)operator new(v9);
    else
      v10 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v9);
    v11 = v10;
    goto LABEL_15;
  }
  v3 = a3 | 7;
  if ( (a3 | 7) < 0xA )
    v3 = 10;
  if ( (unsigned __int64)(v3 + 1) > 0x7FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  v9 = 2 * (v3 + 1);
  if ( v9 )
    goto LABEL_6;
  v11 = 0;
LABEL_15:
  a1[2] = a3;
  v12 = 2 * a3;
  *a1 = v11;
  a1[3] = v3;
  result = memcpy_0(v11, a2, v12);
  *(_WORD *)&v11[v12] = 0;
  return result;
}

```

## disassembly

```asm
0x14000dd20  push    rbx
0x14000dd22  push    rbp
0x14000dd23  push    rsi
0x14000dd24  push    rdi
0x14000dd25  push    r14
0x14000dd27  push    r15
0x14000dd29  sub     rsp, 28h
0x14000dd2d  mov     rbp, 7FFFFFFFFFFFFFFEh
0x14000dd37  mov     rbx, r8
0x14000dd3a  mov     r15, rdx
0x14000dd3d  mov     rsi, rcx
0x14000dd40  cmp     r8, rbp
0x14000dd43  ja      loc_14000DDFB
0x14000dd49  cmp     rbx, 7
0x14000dd4d  ja      short loc_14000DD70
0x14000dd4f  mov     [rcx+10h], rbx
0x14000dd53  add     rbx, rbx
0x14000dd56  mov     r8, rbx; Size
0x14000dd59  mov     qword ptr [rcx+18h], 7
0x14000dd61  call    memcpy_0
0x14000dd66  xor     r14d, r14d
0x14000dd69  mov     [rbx+rsi], r14w
0x14000dd6e  jmp     short loc_14000DDE8
0x14000dd70  mov     rax, rbx
0x14000dd73  xor     r14d, r14d
0x14000dd76  or      rax, 7
0x14000dd7a  cmp     rax, rbp
0x14000dd7d  jbe     short loc_14000DD93
0x14000dd7f  lea     rcx, [r14-2]; Size
0x14000dd83  cmp     rcx, 1000h
0x14000dd8a  jb      short loc_14000DDBF
0x14000dd8c  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x14000dd91  jmp     short loc_14000DDC4
0x14000dd93  mov     ecx, 0Ah
0x14000dd98  mov     rbp, rax
0x14000dd9b  cmp     rax, rcx
0x14000dd9e  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000dda8  cmovb   rbp, rcx
0x14000ddac  lea     rcx, [rbp+1]
0x14000ddb0  cmp     rcx, rax
0x14000ddb3  ja      short loc_14000DDF5
0x14000ddb5  add     rcx, rcx
0x14000ddb8  jnz     short loc_14000DD83
0x14000ddba  mov     rdi, r14
0x14000ddbd  jmp     short loc_14000DDC7
0x14000ddbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ddc4  mov     rdi, rax
0x14000ddc7  mov     [rsi+10h], rbx
0x14000ddcb  mov     rdx, r15; Src
0x14000ddce  add     rbx, rbx
0x14000ddd1  mov     [rsi], rdi
0x14000ddd4  mov     r8, rbx; Size
0x14000ddd7  mov     [rsi+18h], rbp
0x14000dddb  mov     rcx, rdi; void *
0x14000ddde  call    memcpy_0
0x14000dde3  mov     [rbx+rdi], r14w
0x14000dde8  add     rsp, 28h
0x14000ddec  pop     r15
0x14000ddee  pop     r14
0x14000ddf0  pop     rdi
0x14000ddf1  pop     rsi
0x14000ddf2  pop     rbp
0x14000ddf3  pop     rbx
0x14000ddf4  retn
0x14000ddf5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x14000ddfb  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
