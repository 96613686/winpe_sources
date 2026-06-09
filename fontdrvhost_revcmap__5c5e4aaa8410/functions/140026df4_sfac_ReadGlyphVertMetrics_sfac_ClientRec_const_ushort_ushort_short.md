# sfac_ReadGlyphVertMetrics(sfac_ClientRec const *,ushort,ushort *,short *)

- ea: `0x140026df4`
- end: `0x14002713a`
- name: `?sfac_ReadGlyphVertMetrics@@YAHPEBUsfac_ClientRec@@GPEAGPEAF@Z`
- size: `838`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, unsigned __int16, unsigned __int16 *, __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140026d60`

## callees

- `0x14001a950`
- `0x140026df4`
- `0x140072578`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sfac_ReadGlyphVertMetrics(
        const struct sfac_ClientRec *a1,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        __int16 *a4)
{
  __int64 v6; // r15
  __int64 v8; // r10
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdx
  __int16 v13; // r8
  __int16 v14; // ax
  __int16 v15; // r8
  __int64 v17; // rcx
  unsigned int GlyphLocation; // edi
  __int64 v19; // r8
  unsigned __int16 *v20; // r9
  unsigned int v21; // r10d
  signed __int16 v22; // di
  __int64 v23; // rdx
  __int16 v24; // cx
  __int64 v25; // rdx
  unsigned int v26; // [rsp+30h] [rbp-40h] BYREF
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v28[6]; // [rsp+40h] [rbp-30h] BYREF
  int v29; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+B8h] [rbp+48h] BYREF

  v6 = a2;
  v8 = 0;
  v27 = 0;
  v9 = 0;
  v28[0] = 0;
  v10 = *((unsigned __int16 *)a1 + 109);
  if ( a2 < (unsigned __int16)v10 )
    v11 = 4 * (unsigned int)a2 + 4;
  else
    v11 = 2 * (a2 + (unsigned int)v10) + 2;
  if ( *((_BYTE *)a1 + 220) && *((_DWORD *)a1 + 49) )
  {
    v12 = *((unsigned int *)a1 + 48);
    if ( (unsigned int)v12 > 0x7FFFFFFF )
    {
LABEL_43:
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, v12);
      goto LABEL_44;
    }
    v8 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD *))a1 + 1))(*(_QWORD *)a1, v12, v11, v28);
    v9 = v28[0];
  }
  v28[1] = a1;
  v28[2] = v9;
  if ( *((_BYTE *)a1 + 220) && v8 )
  {
    if ( (unsigned __int16)v6 < (unsigned __int16)v10 )
    {
      v25 = (unsigned int)(4 * v6);
      *a3 = _byteswap_ushort(*(_WORD *)(v25 + v8));
      v13 = *(unsigned __int8 *)(v25 + v8 + 3);
      v14 = *(unsigned __int8 *)(v25 + v8 + 2);
    }
    else
    {
      *a3 = _byteswap_ushort(*(_WORD *)((unsigned int)(4 * v10) + v8 - 4));
      v13 = *(unsigned __int8 *)(v8 + 2 * (v6 + v10) + 1);
      v14 = *(unsigned __int8 *)(v8 + 2 * (v6 + v10));
    }
    v15 = (v14 << 8) | v13;
    goto LABEL_12;
  }
  v30 = 0;
  v26 = 0;
  v29 = 0;
  GlyphLocation = sfac_GetGlyphLocation(
                    (_DWORD)a1,
                    *((unsigned __int16 *)a1 + 116),
                    (unsigned int)&v26,
                    (unsigned int)&v30,
                    (__int64)&v29);
  if ( GlyphLocation )
    goto LABEL_33;
  if ( !v30 )
  {
    v22 = HIWORD(v27);
LABEL_40:
    *a3 = *((_WORD *)a1 + 120) - *((_WORD *)a1 + 121);
    v15 = *((_WORD *)a1 + 120) - v22;
LABEL_12:
    *a4 = v15;
    if ( v9 )
      (*((void (__fastcall **)(__int64))a1 + 2))(v9);
    return 0;
  }
  if ( v30 < 0xA )
  {
    GlyphLocation = 5133;
    goto LABEL_33;
  }
  v19 = 0;
  v27 = 0;
  if ( !*((_DWORD *)a1 + 2 * v29 + 9) )
  {
    v20 = 0;
    GlyphLocation = 5129;
    goto LABEL_25;
  }
  if ( v30 > 0x7FFFFFFF || (v21 = v26 + *((_DWORD *)a1 + 2 * v29 + 8), v21 > 0x7FFFFFFF) || v21 < v26 )
  {
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v17, v30);
    goto LABEL_43;
  }
  v20 = (unsigned __int16 *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))a1 + 1))(
                              *(_QWORD *)a1,
                              v21,
                              v30,
                              &v27);
  v19 = v27;
  if ( v20 )
  {
    GlyphLocation = 0;
    goto LABEL_25;
  }
LABEL_44:
  GlyphLocation = 5128;
LABEL_25:
  v28[3] = a1;
  v28[4] = v19;
  if ( GlyphLocation )
  {
    if ( v19 )
      (*((void (__fastcall **)(__int64))a1 + 2))(v19);
  }
  else
  {
    v22 = _byteswap_ushort(v20[4]);
    v23 = *((unsigned __int8 *)v20 + 6);
    LOWORD(v23) = _byteswap_ushort(v20[3]);
    v24 = _byteswap_ushort(v20[1]);
    if ( (__int16)_byteswap_ushort(v20[2]) <= v22 && v24 <= (__int16)v23 )
    {
      if ( v19 )
        (*((void (__fastcall **)(__int64))a1 + 2))(v19);
      goto LABEL_40;
    }
    if ( v19 )
      (*((void (__fastcall **)(__int64, __int64))a1 + 2))(v19, v23);
    GlyphLocation = 5120;
  }
LABEL_33:
  if ( v9 )
    (*((void (__fastcall **)(__int64))a1 + 2))(v9);
  return GlyphLocation;
}

```

## disassembly

```asm
0x140026df4  mov     [rsp-38h+arg_10], rbx
0x140026df9  push    rbp
0x140026dfa  push    rsi
0x140026dfb  push    rdi
0x140026dfc  push    r12
0x140026dfe  push    r13
0x140026e00  push    r14
0x140026e02  push    r15
0x140026e04  mov     rbp, rsp
0x140026e07  sub     rsp, 70h
0x140026e0b  mov     r13, r9
0x140026e0e  mov     r12, r8
0x140026e11  movzx   r15d, dx
0x140026e15  mov     rbx, rcx
0x140026e18  xor     r10d, r10d
0x140026e1b  mov     [rbp+var_38], r10
0x140026e1f  xor     esi, esi
0x140026e21  mov     [rbp+var_30], rsi
0x140026e25  movzx   edi, word ptr [rcx+0DAh]
0x140026e2c  cmp     r15w, di
0x140026e30  jb      loc_14002707F
0x140026e36  lea     eax, [r15+rdi]
0x140026e3a  lea     r8d, ds:2[rax*2]
0x140026e42  cmp     [rcx+0DCh], sil
0x140026e49  jz      short loc_140026E7C
0x140026e4b  cmp     [rcx+0C4h], esi
0x140026e51  jbe     short loc_140026E7C
0x140026e53  mov     edx, [rcx+0C0h]
0x140026e59  cmp     edx, 7FFFFFFFh
0x140026e5f  ja      loc_1400270CA
0x140026e65  lea     r9, [rbp+var_30]
0x140026e69  mov     rcx, [rcx]
0x140026e6c  mov     rax, [rbx+8]
0x140026e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026e75  mov     r10, rax
0x140026e78  mov     rsi, [rbp+var_30]
0x140026e7c  mov     [rbp+var_28], rbx
0x140026e80  mov     [rbp+var_20], rsi
0x140026e84  cmp     byte ptr [rbx+0DCh], 0
0x140026e8b  jz      short loc_140026F02
0x140026e8d  test    r10, r10
0x140026e90  jz      short loc_140026F02
0x140026e92  cmp     r15w, di
0x140026e96  jb      loc_140027034
0x140026e9c  lea     eax, ds:0[rdi*4]
0x140026ea3  movzx   edx, byte ptr [rax+r10-4]
0x140026ea9  shl     dx, 8
0x140026ead  movzx   eax, byte ptr [rax+r10-3]
0x140026eb3  or      dx, ax
0x140026eb6  mov     [r12], dx
0x140026ebb  mov     rcx, rdi
0x140026ebe  add     rcx, rcx
0x140026ec1  sub     rcx, rdi
0x140026ec4  add     rcx, r15
0x140026ec7  movzx   r8d, byte ptr [r10+rcx*2+1]
0x140026ecd  movzx   eax, byte ptr [r10+rcx*2]
0x140026ed2  shl     ax, 8
0x140026ed6  or      r8w, ax
0x140026eda  mov     [r13+0], r8w
0x140026edf  test    rsi, rsi
0x140026ee2  jnz     loc_1400270DA
0x140026ee8  xor     eax, eax
0x140026eea  mov     rbx, [rsp+70h+arg_10]
0x140026ef2  add     rsp, 70h
0x140026ef6  pop     r15
0x140026ef8  pop     r14
0x140026efa  pop     r13
0x140026efc  pop     r12
0x140026efe  pop     rdi
0x140026eff  pop     rsi
0x140026f00  pop     rbp
0x140026f01  retn
0x140026f02  mov     [rbp+arg_8], 0
0x140026f09  mov     [rbp+var_40], 0
0x140026f10  mov     [rbp+arg_0], 0
0x140026f17  lea     rax, [rbp+arg_0]
0x140026f1b  mov     [rsp+70h+var_50], rax
0x140026f20  lea     r9, [rbp+arg_8]
0x140026f24  lea     r8, [rbp+var_40]
0x140026f28  movzx   edx, word ptr [rbx+0E8h]
0x140026f2f  mov     rcx, rbx
0x140026f32  call    sfac_GetGlyphLocation
0x140026f37  mov     edi, eax
0x140026f39  test    eax, eax
0x140026f3b  jnz     loc_14002706F
0x140026f41  mov     edx, [rbp+arg_8]
0x140026f44  test    edx, edx
0x140026f46  jz      loc_1400270BE
0x140026f4c  cmp     edx, 0Ah
0x140026f4f  jb      loc_1400270EB
0x140026f55  xor     r8d, r8d
0x140026f58  mov     [rbp+var_38], r8
0x140026f5c  test    edx, edx
0x140026f5e  jz      short loc_140026F6B
0x140026f60  movsxd  rax, [rbp+arg_0]
0x140026f64  cmp     [rbx+rax*8+24h], r8d
0x140026f69  ja      short loc_140026F75
0x140026f6b  xor     r9d, r9d
0x140026f6e  mov     edi, 1409h
0x140026f73  jmp     short loc_140026FC8
0x140026f75  mov     r8d, 7FFFFFFFh
0x140026f7b  cmp     edx, r8d
0x140026f7e  ja      loc_1400270C4
0x140026f84  mov     r10d, [rbx+rax*8+20h]
0x140026f89  add     r10d, [rbp+var_40]
0x140026f8d  cmp     r10d, r8d
0x140026f90  ja      loc_1400270C4
0x140026f96  cmp     r10d, [rbp+var_40]
0x140026f9a  jb      loc_1400270C4
0x140026fa0  lea     r9, [rbp+var_38]
0x140026fa4  mov     r8d, edx
0x140026fa7  mov     edx, r10d
0x140026faa  mov     rcx, [rbx]
0x140026fad  mov     rax, [rbx+8]
0x140026fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026fb6  mov     r9, rax
0x140026fb9  mov     r8, [rbp+var_38]
0x140026fbd  test    rax, rax
0x140026fc0  jz      loc_1400270D0
0x140026fc6  xor     edi, edi
0x140026fc8  mov     [rbp+var_18], rbx
0x140026fcc  mov     [rbp+var_10], r8
0x140026fd0  test    edi, edi
0x140026fd2  jnz     loc_140027066
0x140026fd8  movzx   r10d, byte ptr [r9+4]
0x140026fdd  shl     r10w, 8
0x140026fe2  movzx   eax, byte ptr [r9+5]
0x140026fe7  or      r10w, ax
0x140026feb  movzx   edi, byte ptr [r9+8]
0x140026ff0  shl     di, 8
0x140026ff4  movzx   eax, byte ptr [r9+9]
0x140026ff9  or      di, ax
0x140026ffc  movzx   edx, byte ptr [r9+6]
0x140027001  shl     dx, 8
0x140027005  movzx   eax, byte ptr [r9+7]
0x14002700a  or      dx, ax
0x14002700d  movzx   ecx, byte ptr [r9+2]
0x140027012  shl     cx, 8
0x140027016  movzx   eax, byte ptr [r9+3]
0x14002701b  or      cx, ax
0x14002701e  cmp     r10w, di
0x140027022  jle     short loc_14002708C
0x140027024  test    r8, r8
0x140027027  jnz     loc_1400270F5
0x14002702d  mov     edi, 1400h
0x140027032  jmp     short loc_14002706F
0x140027034  lea     eax, ds:0[r15*4]
0x14002703c  mov     edx, eax
0x14002703e  movzx   ecx, byte ptr [rax+r10+1]
0x140027044  movzx   eax, byte ptr [rax+r10]
0x140027049  shl     ax, 8
0x14002704d  or      cx, ax
0x140027050  mov     [r12], cx
0x140027055  movzx   r8d, byte ptr [rdx+r10+3]
0x14002705b  movzx   eax, byte ptr [rdx+r10+2]
0x140027061  jmp     loc_140026ED2
0x140027066  test    r8, r8
0x140027069  jnz     loc_140027106
0x14002706f  test    rsi, rsi
0x140027072  jnz     loc_140027117
0x140027078  mov     eax, edi
0x14002707a  jmp     loc_140026EEA
0x14002707f  lea     r8d, ds:4[r15*4]
0x140027087  jmp     loc_140026E42
0x14002708c  cmp     cx, dx
0x14002708f  jg      short loc_140027024
0x140027091  test    r8, r8
0x140027094  jnz     loc_140027128
0x14002709a  movzx   eax, word ptr [rbx+0F0h]
0x1400270a1  sub     ax, [rbx+0F2h]
0x1400270a8  mov     [r12], ax
0x1400270ad  movzx   r8d, word ptr [rbx+0F0h]
0x1400270b5  sub     r8w, di
0x1400270b9  jmp     loc_140026EDA
0x1400270be  movzx   edi, word ptr [rbp+var_38+6]
0x1400270c2  jmp     short loc_14002709A
0x1400270c4  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x1400270c9  nop
0x1400270ca  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x1400270cf  nop
0x1400270d0  mov     edi, 1408h
0x1400270d5  jmp     loc_140026FC8
0x1400270da  mov     rcx, rsi
0x1400270dd  mov     rax, [rbx+10h]
0x1400270e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400270e6  jmp     loc_140026EE8
0x1400270eb  mov     edi, 140Dh
0x1400270f0  jmp     loc_14002706F
0x1400270f5  mov     rcx, r8
0x1400270f8  mov     rax, [rbx+10h]
0x1400270fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027101  jmp     loc_14002702D
0x140027106  mov     rcx, r8
0x140027109  mov     rax, [rbx+10h]
0x14002710d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027112  jmp     loc_14002706F
0x140027117  mov     rcx, rsi
0x14002711a  mov     rax, [rbx+10h]
0x14002711e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027123  jmp     loc_140027078
0x140027128  mov     rcx, r8
0x14002712b  mov     rax, [rbx+10h]
0x14002712f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027134  jmp     loc_14002709A
```
