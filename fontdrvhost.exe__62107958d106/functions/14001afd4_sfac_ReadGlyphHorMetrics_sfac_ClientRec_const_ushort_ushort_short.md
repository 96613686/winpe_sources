# sfac_ReadGlyphHorMetrics(sfac_ClientRec const *,ushort,ushort *,short *)

- ea: `0x14001afd4`
- end: `0x14001b252`
- name: `?sfac_ReadGlyphHorMetrics@@YAHPEBUsfac_ClientRec@@GPEAGPEAF@Z`
- size: `638`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, unsigned __int16, unsigned __int16 *, __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400197e0`
- `0x14001ac14`
- `0x14002973c`
- `0x1400742bc`

## callees

- `0x140013240`
- `0x14001afd4`
- `0x14005589c`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sfac_ReadGlyphHorMetrics(
        const struct sfac_ClientRec *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        __int16 *a4)
{
  unsigned __int16 *v4; // r9
  unsigned int v5; // r13d
  const struct sfac_ClientRec *v6; // r14
  unsigned __int16 v7; // ax
  __int64 v8; // rbp
  __int64 v9; // rdi
  unsigned __int64 v10; // rsi
  unsigned int v11; // ebx
  __int64 v12; // r15
  unsigned __int64 v13; // r8
  __int16 v14; // cx
  __int16 v15; // ax
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // r12
  unsigned __int16 v21; // r13
  __int64 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+38h] [rbp-60h] BYREF
  char v24[8]; // [rsp+40h] [rbp-58h] BYREF
  const struct sfac_ClientRec *v25; // [rsp+48h] [rbp-50h]
  __int64 v26; // [rsp+50h] [rbp-48h]
  unsigned __int64 v27; // [rsp+A0h] [rbp+8h] BYREF
  unsigned __int16 *v28; // [rsp+B0h] [rbp+18h]
  __int16 *v29; // [rsp+B8h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v4 = a3;
  v5 = (unsigned __int16)a2;
  v6 = a1;
  v7 = *((_WORD *)a1 + 108);
  LOWORD(v27) = v7;
  v8 = *((unsigned int *)a1 + 23);
  v9 = 0;
  v22 = 0;
  if ( (_DWORD)v8 )
  {
    if ( (unsigned int)v8 > 0x7FFFFFFF || (a2 = *((unsigned int *)a1 + 22), (unsigned int)a2 > 0x7FFFFFFF) )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
      __debugbreak();
    }
    v10 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, __int64 *))a1 + 1))(
            *(_QWORD *)a1,
            a2,
            (unsigned int)v8,
            &v22);
    v9 = v22;
    v4 = v28;
    v7 = v27;
    if ( v10 )
      v11 = 0;
    else
      v11 = 5128;
  }
  else
  {
    v10 = 0;
    v11 = 5129;
  }
  v25 = v6;
  v26 = v9;
  if ( !v11 )
  {
    v12 = v7;
    if ( v7 > v5 )
    {
      a1 = (const struct sfac_ClientRec *)(v8 - 4);
      if ( (unsigned __int64)(v8 - 4) <= 0xFFFFFFFF )
      {
        v13 = v10 + (unsigned int)a1;
        if ( v13 >= v10 )
        {
          a2 = v10 + 4 * v5;
          if ( a2 <= v13 )
          {
            *v4 = _byteswap_ushort(*(_WORD *)a2);
            v14 = *(unsigned __int8 *)(a2 + 2) << 8;
            v15 = *(unsigned __int8 *)(a2 + 3);
            goto LABEL_12;
          }
          goto LABEL_27;
        }
      }
      goto LABEL_26;
    }
    if ( (unsigned int)v8 < 2 )
    {
LABEL_26:
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
      goto LABEL_27;
    }
    v23 = (unsigned int)(v8 - 2);
    v18 = *(_QWORD *)SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(
                       &v23,
                       v24,
                       1);
    if ( v18 < 0 )
    {
      v18 = -v18;
      if ( v18 <= v10 )
      {
        v19 = v10 - v18;
        goto LABEL_17;
      }
    }
    else
    {
      v19 = v18 + v10;
      if ( v18 + v10 >= v10 )
      {
LABEL_17:
        v20 = v10 + (unsigned int)(4 * v12);
        v21 = v5 - v27;
        v27 = v20;
        if ( *(_QWORD *)operator+=<short const,unsigned int,SafeIntExceptionHandler<SafeIntRasterizerException>>(
                          &v27,
                          v21) > v19 )
        {
LABEL_27:
          if ( v9 )
            (*((void (__fastcall **)(__int64, unsigned __int64, unsigned __int64, unsigned __int16 *))v6 + 2))(
              v9,
              a2,
              v13,
              v4);
          return 5135;
        }
        a1 = (const struct sfac_ClientRec *)(v12 - 1);
        if ( (unsigned __int64)(v12 - 1) <= 0xFFFFFFFF )
        {
          a1 = (const struct sfac_ClientRec *)(4LL * (unsigned int)a1);
          if ( (unsigned __int64)a1 <= 0xFFFFFFFF )
          {
            *v28 = _byteswap_ushort(*(_WORD *)((unsigned int)a1 + v10));
            v14 = *(unsigned __int8 *)(v20 + 2LL * v21 + 1);
            v15 = *(unsigned __int8 *)(v20 + 2LL * v21) << 8;
LABEL_12:
            *v29 = v15 | v14;
            if ( !v9 )
              return 0;
LABEL_33:
            (*((void (__fastcall **)(__int64))v6 + 2))(v9);
            return 0;
          }
        }
        goto LABEL_26;
      }
    }
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v18, v17);
    goto LABEL_33;
  }
  if ( v9 )
    (*((void (__fastcall **)(__int64, unsigned __int64, unsigned __int16 *, unsigned __int16 *))v6 + 2))(v9, a2, a3, v4);
  return v11;
}

```

## disassembly

```asm
0x14001afd4  mov     r11, rsp
0x14001afd7  mov     [r11+10h], rbx
0x14001afdb  mov     [r11+20h], r9
0x14001afdf  mov     [r11+18h], r8
0x14001afe3  push    rbp
0x14001afe4  push    rsi
0x14001afe5  push    rdi
0x14001afe6  push    r12
0x14001afe8  push    r13
0x14001afea  push    r14
0x14001afec  push    r15
0x14001afee  sub     rsp, 60h
0x14001aff2  mov     r9, r8
0x14001aff5  movzx   r13d, dx
0x14001aff9  mov     r14, rcx
0x14001affc  movzx   eax, word ptr [rcx+0D8h]
0x14001b003  mov     word ptr [rsp+98h+arg_0], ax
0x14001b00b  mov     ebp, [rcx+5Ch]
0x14001b00e  xor     edi, edi
0x14001b010  mov     [r11-68h], rdi
0x14001b014  test    ebp, ebp
0x14001b016  jz      loc_14001B1E1
0x14001b01c  mov     eax, 7FFFFFFFh
0x14001b021  cmp     ebp, eax
0x14001b023  ja      loc_14001B1DB
0x14001b029  mov     edx, [rcx+58h]
0x14001b02c  cmp     edx, eax
0x14001b02e  ja      loc_14001B1DB
0x14001b034  lea     r9, [r11-68h]
0x14001b038  mov     r8d, ebp
0x14001b03b  mov     rcx, [rcx]
0x14001b03e  mov     rax, [r14+8]
0x14001b042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b047  mov     rsi, rax
0x14001b04a  mov     rdi, [rsp+98h+var_68]
0x14001b04f  mov     r9, [rsp+98h+arg_10]
0x14001b057  test    rax, rax
0x14001b05a  movzx   eax, word ptr [rsp+98h+arg_0]
0x14001b062  jz      loc_14001B202
0x14001b068  xor     ebx, ebx
0x14001b06a  mov     [rsp+98h+var_50], r14
0x14001b06f  mov     [rsp+98h+var_48], rdi
0x14001b074  test    ebx, ebx
0x14001b076  jnz     loc_14001B1CF
0x14001b07c  movzx   r15d, ax
0x14001b080  cmp     r15d, r13d
0x14001b083  jbe     loc_14001B10D
0x14001b089  lea     rcx, [rbp-4]
0x14001b08d  mov     eax, 0FFFFFFFFh
0x14001b092  cmp     rcx, rax
0x14001b095  ja      loc_14001B1ED
0x14001b09b  mov     r8d, ecx
0x14001b09e  add     r8, rsi
0x14001b0a1  cmp     r8, rsi
0x14001b0a4  jb      loc_14001B1ED
0x14001b0aa  lea     edx, ds:0[r13*4]
0x14001b0b2  add     rdx, rsi
0x14001b0b5  cmp     rdx, r8
0x14001b0b8  ja      loc_14001B1F3
0x14001b0be  movzx   ecx, byte ptr [rdx+1]
0x14001b0c2  movzx   eax, byte ptr [rdx]
0x14001b0c5  shl     ax, 8
0x14001b0c9  or      cx, ax
0x14001b0cc  mov     [r9], cx
0x14001b0d0  movzx   ecx, byte ptr [rdx+2]
0x14001b0d4  shl     cx, 8
0x14001b0d8  movzx   eax, byte ptr [rdx+3]
0x14001b0dc  or      cx, ax
0x14001b0df  mov     rax, [rsp+98h+arg_18]
0x14001b0e7  mov     [rax], cx
0x14001b0ea  test    rdi, rdi
0x14001b0ed  jnz     loc_14001B21A
0x14001b0f3  xor     eax, eax
0x14001b0f5  mov     rbx, [rsp+98h+arg_8]
0x14001b0fd  add     rsp, 60h
0x14001b101  pop     r15
0x14001b103  pop     r14
0x14001b105  pop     r13
0x14001b107  pop     r12
0x14001b109  pop     rdi
0x14001b10a  pop     rsi
0x14001b10b  pop     rbp
0x14001b10c  retn
0x14001b10d  cmp     ebp, 2
0x14001b110  jb      loc_14001B1ED
0x14001b116  lea     ecx, [rbp-2]
0x14001b119  mov     [rsp+98h+var_60], rcx
0x14001b11e  mov     r8d, 1
0x14001b124  lea     rdx, [rsp+98h+var_58]
0x14001b129  lea     rcx, [rsp+98h+var_60]
0x14001b12e  call    ??$?D_K@?$SafeInt@_JV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@QEBA?AV0@_K@Z; SafeInt<__int64,SafeIntExceptionHandler<SafeIntRasterizerException>>::operator*<unsigned __int64>(unsigned __int64)
0x14001b133  mov     rcx, [rax]
0x14001b136  test    rcx, rcx
0x14001b139  js      loc_14001B20C
0x14001b13f  lea     rbp, [rcx+rsi]
0x14001b143  cmp     rbp, rsi
0x14001b146  jb      loc_14001B214
0x14001b14c  lea     r12d, ds:0[r15*4]
0x14001b154  add     r12, rsi
0x14001b157  sub     r13w, word ptr [rsp+98h+arg_0]
0x14001b160  movzx   ebx, r13w
0x14001b164  mov     [rsp+98h+arg_0], r12
0x14001b16c  mov     edx, ebx
0x14001b16e  lea     rcx, [rsp+98h+arg_0]
0x14001b176  call    ??$?Y$$CBFIV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@YAAEAPEBFAEAPEBFV?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@@@@Z; operator+=<short const,uint,SafeIntExceptionHandler<SafeIntRasterizerException>>(short const * &,SafeInt<uint,SafeIntExceptionHandler<SafeIntRasterizerException>>)
0x14001b17b  cmp     [rax], rbp
0x14001b17e  ja      short loc_14001B1F3
0x14001b180  lea     rcx, [r15-1]
0x14001b184  mov     eax, 0FFFFFFFFh
0x14001b189  cmp     rcx, rax
0x14001b18c  ja      short loc_14001B1ED
0x14001b18e  mov     ecx, ecx
0x14001b190  shl     rcx, 2
0x14001b194  cmp     rcx, rax
0x14001b197  ja      short loc_14001B1ED
0x14001b199  mov     edx, ecx
0x14001b19b  cmp     rdx, rax
0x14001b19e  ja      short loc_14001B1ED
0x14001b1a0  movzx   ecx, byte ptr [rdx+rsi+1]
0x14001b1a5  movzx   eax, byte ptr [rdx+rsi]
0x14001b1a9  shl     ax, 8
0x14001b1ad  or      cx, ax
0x14001b1b0  mov     rax, [rsp+98h+arg_10]
0x14001b1b8  mov     [rax], cx
0x14001b1bb  movzx   ecx, byte ptr [r12+rbx*2+1]
0x14001b1c1  movzx   eax, byte ptr [r12+rbx*2]
0x14001b1c6  shl     ax, 8
0x14001b1ca  jmp     loc_14001B0DC
0x14001b1cf  test    rdi, rdi
0x14001b1d2  jnz     short loc_14001B22B
0x14001b1d4  mov     eax, ebx
0x14001b1d6  jmp     loc_14001B0F5
0x14001b1db  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001b1e0  int     3; Trap to Debugger
0x14001b1e1  xor     esi, esi
0x14001b1e3  mov     ebx, 1409h
0x14001b1e8  jmp     loc_14001B06A
0x14001b1ed  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001b1f2  nop
0x14001b1f3  test    rdi, rdi
0x14001b1f6  jnz     short loc_14001B244
0x14001b1f8  mov     eax, 140Fh
0x14001b1fd  jmp     loc_14001B0F5
0x14001b202  mov     ebx, 1408h
0x14001b207  jmp     loc_14001B06A
0x14001b20c  neg     rcx
0x14001b20f  cmp     rcx, rsi
0x14001b212  jbe     short loc_14001B239
0x14001b214  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14001b219  nop
0x14001b21a  mov     rcx, rdi
0x14001b21d  mov     rax, [r14+10h]
0x14001b221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b226  jmp     loc_14001B0F3
0x14001b22b  mov     rcx, rdi
0x14001b22e  mov     rax, [r14+10h]
0x14001b232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b237  jmp     short loc_14001B1D4
0x14001b239  mov     rbp, rsi
0x14001b23c  sub     rbp, rcx
0x14001b23f  jmp     loc_14001B14C
0x14001b244  mov     rcx, rdi
0x14001b247  mov     rax, [r14+10h]
0x14001b24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b250  jmp     short loc_14001B1F8
```
