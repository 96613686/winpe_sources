# CJob::SetWorkingDirectory(ushort const *)

- ea: `0x18000df10`
- end: `0x18000e004`
- name: `?SetWorkingDirectory@CJob@@UEAAJPEBG@Z`
- size: `244`
- prototype: `int(CJob *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001840`
- `0x1800090e0`
- `0x180009ef8`
- `0x180009f38`
- `0x18000df10`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CJob::SetWorkingDirectory(CJob *this, unsigned __int16 *a2)
{
  void *v4; // rcx
  __int64 v5; // rdi
  __int64 v6; // rcx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r14
  void *v10; // rcx
  _WORD *v11; // rdx

  if ( *a2 )
  {
    v5 = -1;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = (unsigned __int16 *)operator new(saturated_mul(v6 + 1, 2u));
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    *v7 = 0;
    do
      ++v5;
    while ( a2[v5] );
    StringCchCopyW(v7, v5 + 1, a2);
    v10 = (void *)*((_QWORD *)this + 16);
    if ( *((_QWORD *)this + 28) > (unsigned __int64)v10 || (unsigned __int64)v10 >= *((_QWORD *)this + 29) )
      operator delete(v10);
    *((_QWORD *)this + 16) = v8;
    DeleteQuotes(v8);
  }
  else
  {
    v4 = (void *)*((_QWORD *)this + 16);
    if ( *((_QWORD *)this + 28) > (unsigned __int64)v4 || (unsigned __int64)v4 >= *((_QWORD *)this + 29) )
      operator delete(v4);
    *((_QWORD *)this + 16) = 0;
  }
  *((_DWORD *)this + 22) |= 0x40000000u;
  v11 = (_WORD *)*((_QWORD *)this + 32);
  if ( v11 && *v11 )
    return (*(__int64 (__fastcall **)(CJob *))(*(_QWORD *)this + 256LL))(this);
  else
    return 0;
}

```

## disassembly

```asm
0x18000df10  push    rbx
0x18000df12  push    rbp
0x18000df13  push    rsi
0x18000df14  push    rdi
0x18000df15  push    r14
0x18000df17  sub     rsp, 20h
0x18000df1b  xor     ebp, ebp
0x18000df1d  mov     rsi, rdx
0x18000df20  mov     rbx, rcx
0x18000df23  cmp     [rdx], bp
0x18000df26  jnz     short loc_18000DF4F
0x18000df28  mov     rcx, [rcx+80h]; Block
0x18000df2f  cmp     [rbx+0E0h], rcx
0x18000df36  ja      short loc_18000DF41
0x18000df38  cmp     rcx, [rbx+0E8h]
0x18000df3f  jb      short loc_18000DF46
0x18000df41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000df46  mov     [rbx+80h], rbp
0x18000df4d  jmp     short loc_18000DFCD
0x18000df4f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000df53  mov     rcx, rdi
0x18000df56  inc     rcx
0x18000df59  cmp     [rdx+rcx*2], bp
0x18000df5d  jnz     short loc_18000DF56
0x18000df5f  inc     rcx
0x18000df62  mov     eax, 2
0x18000df67  mul     rcx
0x18000df6a  cmovb   rax, rdi
0x18000df6e  mov     rcx, rax; Size
0x18000df71  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000df76  mov     r14, rax
0x18000df79  test    rax, rax
0x18000df7c  jnz     short loc_18000DF85
0x18000df7e  mov     eax, 8007000Eh
0x18000df83  jmp     short loc_18000DFF9
0x18000df85  mov     [rax], bp
0x18000df88  inc     rdi
0x18000df8b  cmp     [rsi+rdi*2], bp
0x18000df8f  jnz     short loc_18000DF88
0x18000df91  lea     rdx, [rdi+1]; unsigned __int64
0x18000df95  mov     r8, rsi; unsigned __int16 *
0x18000df98  mov     rcx, r14; unsigned __int16 *
0x18000df9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000dfa0  mov     rcx, [rbx+80h]; Block
0x18000dfa7  cmp     [rbx+0E0h], rcx
0x18000dfae  ja      short loc_18000DFB9
0x18000dfb0  cmp     rcx, [rbx+0E8h]
0x18000dfb7  jb      short loc_18000DFBE
0x18000dfb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dfbe  mov     rcx, r14; unsigned __int16 *
0x18000dfc1  mov     [rbx+80h], r14
0x18000dfc8  call    ?DeleteQuotes@@YAXPEAG@Z; DeleteQuotes(ushort *)
0x18000dfcd  bts     dword ptr [rbx+58h], 1Eh
0x18000dfd2  mov     rdx, [rbx+100h]
0x18000dfd9  test    rdx, rdx
0x18000dfdc  jz      short loc_18000DFF7
0x18000dfde  cmp     [rdx], bp
0x18000dfe1  jz      short loc_18000DFF7
0x18000dfe3  mov     rax, [rbx]
0x18000dfe6  mov     rcx, rbx
0x18000dfe9  mov     rax, [rax+100h]
0x18000dff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff5  jmp     short loc_18000DFF9
0x18000dff7  mov     eax, ebp
0x18000dff9  add     rsp, 20h
0x18000dffd  pop     r14
0x18000dfff  pop     rdi
0x18000e000  pop     rsi
0x18000e001  pop     rbp
0x18000e002  pop     rbx
0x18000e003  retn
```
