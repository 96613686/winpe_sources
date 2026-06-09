# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)

- ea: `0x14000452c`
- end: `0x140004664`
- name: `??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140005f00`
- `0x140007acc`
- `0x14000afac`
- `0x14000b4a0`
- `0x14000c88c`
- `0x14000d2a4`
- `0x14000e150`
- `0x14000f930`
- `0x14000fa88`

## callees

- `0x140002624`
- `0x140002630`
- `0x140003150`
- `0x14000452c`
- `0x14000b940`
- `0x14000ba04`

## pseudocode

```c
char **__fastcall std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4)
{
  __int64 v4; // rbx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  size_t v11; // rcx
  void *v12; // rax
  _QWORD *v13; // rsi
  char *v14; // rax
  char *v15; // rcx
  char **result; // rax

  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v8 = (unsigned __int64)a1[3];
  v9 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v10 = v8 >> 1, v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1)) )
  {
    v4 = v10 + v8;
    if ( v9 >= v10 + v8 )
      v4 = v9;
    if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_23;
    v11 = 2 * (v4 + 1);
    if ( !v11 )
    {
      v13 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v11 = -2;
  }
  if ( v11 < 0x1000 )
  {
    v13 = operator new(v11);
    goto LABEL_15;
  }
  if ( v11 + 39 < v11 )
LABEL_23:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_18;
  v13 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v12;
LABEL_15:
  a1[3] = (char *)v4;
  a1[2] = (char *)a2;
  memcpy_0(v13, a4, 2 * a2);
  *((_WORD *)v13 + a2) = 0;
  if ( v8 > 7 )
  {
    v14 = *a1;
    if ( 2 * v8 + 2 < 0x1000 )
    {
      v15 = *a1;
    }
    else
    {
      v15 = (char *)*((_QWORD *)v14 - 1);
      if ( (unsigned __int64)(v14 - v15 - 8) > 0x1F )
LABEL_18:
        __fastfail(5u);
    }
    operator delete(v15);
  }
  result = a1;
  *a1 = (char *)v13;
  return result;
}

```

## disassembly

```asm
0x14000452c  push    rbx
0x14000452e  push    rbp
0x14000452f  push    rsi
0x140004530  push    rdi
0x140004531  push    r14
0x140004533  push    r15
0x140004535  sub     rsp, 28h
0x140004539  mov     rbx, 7FFFFFFFFFFFFFFEh
0x140004543  mov     r15, r9
0x140004546  mov     r14, rdx
0x140004549  mov     rdi, rcx
0x14000454c  cmp     rdx, rbx
0x14000454f  ja      loc_140004658
0x140004555  mov     rbp, [rcx+18h]
0x140004559  mov     rcx, rdx
0x14000455c  or      rcx, 7
0x140004560  cmp     rcx, rbx
0x140004563  ja      short loc_140004576
0x140004565  mov     rdx, rbp
0x140004568  mov     rax, rbx
0x14000456b  shr     rdx, 1
0x14000456e  sub     rax, rdx
0x140004571  cmp     rbp, rax
0x140004574  jbe     short loc_1400045B2
0x140004576  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000457d  cmp     rcx, 1000h
0x140004584  jb      short loc_1400045DD
0x140004586  lea     rax, [rcx+27h]
0x14000458a  cmp     rax, rcx
0x14000458d  jbe     loc_14000465E
0x140004593  mov     rcx, rax; Size
0x140004596  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000459b  test    rax, rax
0x14000459e  jz      loc_140004636
0x1400045a4  lea     rsi, [rax+27h]
0x1400045a8  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1400045ac  mov     [rsi-8], rax
0x1400045b0  jmp     short loc_1400045E5
0x1400045b2  lea     rbx, [rdx+rbp]
0x1400045b6  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400045c0  cmp     rcx, rbx
0x1400045c3  cmovnb  rbx, rcx
0x1400045c7  lea     rcx, [rbx+1]
0x1400045cb  cmp     rcx, rax
0x1400045ce  ja      loc_14000465E
0x1400045d4  add     rcx, rcx
0x1400045d7  jnz     short loc_14000457D
0x1400045d9  xor     esi, esi
0x1400045db  jmp     short loc_1400045E5
0x1400045dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400045e2  mov     rsi, rax
0x1400045e5  mov     [rdi+18h], rbx
0x1400045e9  mov     rdx, r15; Src
0x1400045ec  lea     rbx, [r14+r14]
0x1400045f0  mov     [rdi+10h], r14
0x1400045f4  mov     r8, rbx; Size
0x1400045f7  mov     rcx, rsi; void *
0x1400045fa  call    memcpy_0
0x1400045ff  xor     ecx, ecx
0x140004601  mov     [rbx+rsi], cx
0x140004605  cmp     rbp, 7
0x140004609  jbe     short loc_140004645
0x14000460b  mov     rax, [rdi]
0x14000460e  lea     rdx, ds:2[rbp*2]; unsigned __int64
0x140004616  cmp     rdx, 1000h
0x14000461d  jb      short loc_14000463D
0x14000461f  mov     rcx, [rax-8]
0x140004623  sub     rax, rcx
0x140004626  sub     rax, 8
0x14000462a  cmp     rax, 1Fh
0x14000462e  ja      short loc_140004636
0x140004630  add     rdx, 27h ; '''
0x140004634  jmp     short loc_140004640
0x140004636  mov     ecx, 5
0x14000463b  int     29h; Win8: RtlFailFast(ecx)
0x14000463d  mov     rcx, rax; void *
0x140004640  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004645  mov     rax, rdi
0x140004648  mov     [rax], rsi
0x14000464b  add     rsp, 28h
0x14000464f  pop     r15
0x140004651  pop     r14
0x140004653  pop     rdi
0x140004654  pop     rsi
0x140004655  pop     rbp
0x140004656  pop     rbx
0x140004657  retn
0x140004658  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000465e  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
