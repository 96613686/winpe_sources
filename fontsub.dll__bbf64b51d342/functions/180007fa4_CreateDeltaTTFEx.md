# CreateDeltaTTFEx

- ea: `0x180007fa4`
- end: `0x18000870e`
- name: `CreateDeltaTTFEx`
- size: `1898`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007cd4`

## callees

- `0x18000740c`
- `0x1800075f4`
- `0x180007800`
- `0x1800079b8`
- `0x180007fa4`
- `0x1800087e8`
- `0x18000d45c`
- `0x18000fd08`
- `0x180010088`
- `0x180010284`
- `0x180010454`
- `0x1800105d0`
- `0x18001077c`
- `0x1800108e4`
- `0x1800109fc`
- `0x180010fd4`
- `0x180011538`
- `0x180011574`
- `0x1800118bc`
- `0x180013364`
- `0x180013ee0`
- `0x1800143f0`
- `0x1800198f8`
- `0x180019ac4`
- `0x180019c00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CreateDeltaTTFEx(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4,
        unsigned int *a5,
        unsigned __int16 a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        unsigned __int16 a9,
        unsigned __int16 a10,
        __int64 a11,
        __int16 a12,
        __int64 (__fastcall *a13)(_QWORD, _QWORD),
        void (__fastcall *a14)(_QWORD),
        int a15,
        __int16 a16)
{
  _DWORD *v16; // r12
  unsigned __int16 v20; // r14
  unsigned __int16 NumGlyphs; // ax
  unsigned __int16 v22; // si
  __int64 v23; // rax
  __int64 v24; // rdi
  unsigned __int16 KeepGlyphList; // bx
  __int64 v26; // rax
  __int64 (__fastcall *v27)(_QWORD, _QWORD); // rbx
  unsigned __int16 v28; // r15
  int v29; // r12d
  unsigned __int16 v30; // ax
  __int64 v31; // rax
  __int64 v32; // r12
  unsigned __int16 v33; // dx
  unsigned __int16 i; // cx
  unsigned int v35; // ecx
  unsigned int v36; // [rsp+68h] [rbp-49h] BYREF
  __int128 v37; // [rsp+70h] [rbp-41h] BYREF
  __int64 (__fastcall *v38)(_QWORD, _QWORD); // [rsp+80h] [rbp-31h]
  _WORD v39[2]; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 v40; // [rsp+8Ch] [rbp-25h] BYREF
  __int64 v41; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v42; // [rsp+98h] [rbp-19h]
  int v43; // [rsp+9Ch] [rbp-15h]
  __int64 v44; // [rsp+A0h] [rbp-11h]
  int v45; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-1h]
  unsigned __int16 v47; // [rsp+F8h] [rbp+47h] BYREF
  unsigned int v48; // [rsp+100h] [rbp+4Fh]
  _DWORD *v49; // [rsp+110h] [rbp+5Fh]

  v49 = a4;
  v48 = a2;
  v40 = -1;
  v47 = 0;
  a16 = 0;
  v16 = a4;
  v39[0] = 0;
  v45 = 0;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  if ( !a1 )
    return 1100;
  if ( !a2 )
    return 1101;
  if ( !a3 )
    return 1102;
  if ( !a4 )
    return 1103;
  if ( !a5 )
    return 1104;
  v20 = a6;
  if ( a6 > 2u )
    return 1105;
  v41 = a1;
  v42 = a2;
  v43 = a15;
  v44 = 0;
  *a5 = 0;
  NumGlyphs = GetNumGlyphs(&v41);
  v22 = NumGlyphs;
  if ( !NumGlyphs )
    return 1009;
  v23 = Mem_Alloc(NumGlyphs);
  v24 = v23;
  if ( !v23 )
    return 1005;
  KeepGlyphList = MakeKeepGlyphList(
                    (unsigned int)&v41,
                    a10,
                    a8,
                    a9,
                    a11,
                    a12,
                    v23,
                    v22,
                    (__int64)&a16,
                    (__int64)&v47,
                    1);
  if ( !KeepGlyphList )
  {
    v26 = *a3;
    v27 = a13;
    v46 = v26;
    if ( !v26 || !*v16 )
    {
      CalcOutputBufferSize((unsigned int)&v41, v22, v47, v20, a2, (__int64)v16);
      v26 = v27(0, (unsigned int)*v16);
      *a3 = v26;
      if ( !v26 )
      {
        Mem_Free(v24);
        return 1005;
      }
    }
    *(_QWORD *)&v37 = v26;
    *((_QWORD *)&v37 + 1) = (unsigned int)*v16;
    v38 = v27;
    if ( v20 == 1 || (v28 = 0, v20 == 2) )
      v28 = v47;
    KeepGlyphList = CopyOffsetDirectoryTables(&v41, &v37, v20, &v36);
    if ( KeepGlyphList
      || (KeepGlyphList = CopyTableOver(&v37, &v41, "head", &v36)) != 0
      || (KeepGlyphList = CopyTableOver(&v37, &v41, "hhea", &v36)) != 0
      || (KeepGlyphList = CopyTableOver(&v37, &v41, "maxp", &v36)) != 0 )
    {
LABEL_68:
      Mem_Free(v24);
      if ( !KeepGlyphList )
      {
        v35 = v36;
        if ( v36 <= v48 )
        {
          *a3 = v37;
          *v16 = DWORD2(v37);
          *a5 = v35;
          return KeepGlyphList;
        }
        KeepGlyphList = 1007;
      }
      if ( v46 || !a14 )
      {
        *a3 = v37;
      }
      else
      {
        a14(v37);
        *a3 = 0;
      }
      return KeepGlyphList;
    }
    v29 = 1;
    if ( v20 != 2 )
      CopyTableOver(&v37, &v41, "OS/2", &v36);
    KeepGlyphList = ModXmtxXhea((unsigned int)&v41, (unsigned int)&v37, v24, v22, v28, a16, 1, (__int64)&v36);
    if ( KeepGlyphList )
    {
      if ( KeepGlyphList != 1007 )
        goto LABEL_67;
      v29 = 0;
    }
    KeepGlyphList = ModLTSH((unsigned int)&v41, (unsigned int)&v37, v24, v22, v28, (__int64)&v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModVDMX(&v41, &v37, v20, &v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    if ( v29 == 1 )
    {
      KeepGlyphList = ModHdmx((unsigned int)&v41, (unsigned int)&v37, v24, v22, v28, (__int64)&v36);
      if ( KeepGlyphList )
        goto LABEL_67;
    }
    else
    {
      CopyTableOver(&v37, &v41, "hdmx", &v36);
    }
    KeepGlyphList = ModCmap(
                      (unsigned int)&v41,
                      (unsigned int)&v37,
                      v24,
                      v22,
                      (__int64)&v40,
                      (__int64)v39,
                      (__int64)&v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    if ( v20 != 2 )
    {
      CopyTableOver(&v37, &v41, "fpgm", &v36);
      CopyTableOver(&v37, &v41, "prep", &v36);
      CopyTableOver(&v37, &v41, "cvt ", &v36);
    }
    KeepGlyphList = ModGlyfLocaAndHead(&v41, &v37, v24, v22, &v45, &v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModMaxP(&v41, &v37, &v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModOS2((unsigned int)&v41, (unsigned int)&v37, v40, v39[0], v20, (__int64)&v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModKern((unsigned int)&v41, (unsigned int)&v37, v24, v22, v20, (__int64)&v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModName((unsigned int)&v41, (unsigned int)&v37, a7, v20, (__int64)&v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    KeepGlyphList = ModPost(&v41, &v37, v20, &v36);
    if ( KeepGlyphList )
      goto LABEL_67;
    CopyTableOver(&v37, &v41, "gasp", &v36);
    CopyTableOver(&v37, &v41, "PCLT", &v36);
    CopyTableOver(&v37, &v41, "vhea", &v36);
    KeepGlyphList = ModXmtxXhea((unsigned int)&v41, (unsigned int)&v37, v24, v22, v28, a16, 0, (__int64)&v36);
    if ( KeepGlyphList )
    {
      if ( KeepGlyphList != 1007 )
        goto LABEL_67;
    }
    v30 = ModSbit((unsigned int)&v41, (unsigned int)&v37, v24, v22, (__int64)&v36);
    if ( v30 )
    {
      KeepGlyphList = v30;
      goto LABEL_67;
    }
    if ( !v28 )
      goto LABEL_63;
    KeepGlyphList = CompactMaxpLocaTable(&v37, v24, v22, v28);
    if ( !KeepGlyphList )
    {
      v31 = Mem_Alloc(2LL * v28);
      v32 = v31;
      if ( !v31 )
      {
        KeepGlyphList = 1005;
        goto LABEL_67;
      }
      v33 = 0;
      for ( i = 0; i < v22; ++i )
      {
        if ( v33 >= v28 )
          break;
        if ( *(_BYTE *)(i + v24) )
          *(_WORD *)(v31 + 2LL * v33++) = i;
      }
      KeepGlyphList = UpdatePrivateTable((unsigned int)&v37, (unsigned int)&v36, v31, v28, v22, v20, v45);
      Mem_Free(v32);
      if ( KeepGlyphList )
        goto LABEL_67;
LABEL_63:
      KeepGlyphList = CopyForgottenTables(&v41, &v37, &v36);
      if ( !KeepGlyphList )
      {
        KeepGlyphList = CompressTables(&v37, &v36);
        if ( !KeepGlyphList )
          SetFileChecksum(&v37, v36);
      }
    }
LABEL_67:
    v16 = v49;
    goto LABEL_68;
  }
  Mem_Free(v24);
  return KeepGlyphList;
}

```

## disassembly

```asm
0x180007fa4  mov     rax, rsp
0x180007fa7  mov     [rax+18h], rbx
0x180007fab  mov     [rax+20h], r9
0x180007faf  mov     [rax+10h], edx
0x180007fb2  push    rbp
0x180007fb3  push    rsi
0x180007fb4  push    rdi
0x180007fb5  push    r12
0x180007fb7  push    r13
0x180007fb9  push    r14
0x180007fbb  push    r15
0x180007fbd  lea     rbp, [rax-3Fh]
0x180007fc1  sub     rsp, 0B0h
0x180007fc8  xor     ebx, ebx
0x180007fca  mov     eax, 0FFFFh
0x180007fcf  mov     [rbp+37h+var_5C], ax
0x180007fd3  xorps   xmm0, xmm0
0x180007fd6  xor     eax, eax
0x180007fd8  mov     [rbp+37h+arg_0], bx
0x180007fdc  mov     [rbp+37h+arg_78], bx
0x180007fe3  mov     r12, r9
0x180007fe6  mov     [rbp+37h+var_60], bx
0x180007fea  mov     r13, r8
0x180007fed  mov     [rbp+37h+var_40], ebx
0x180007ff0  mov     r15d, edx
0x180007ff3  mov     [rbp+37h+var_80], ebx
0x180007ff6  mov     [rbp+37h+var_68], rax
0x180007ffa  movups  [rbp+37h+var_78], xmm0
0x180007ffe  test    rcx, rcx
0x180008001  jnz     short loc_18000800D
0x180008003  mov     eax, 44Ch
0x180008008  jmp     loc_1800086F3
0x18000800d  test    r15d, r15d
0x180008010  jnz     short loc_18000801C
0x180008012  mov     eax, 44Dh
0x180008017  jmp     loc_1800086F3
0x18000801c  test    r13, r13
0x18000801f  jnz     short loc_18000802B
0x180008021  mov     eax, 44Eh
0x180008026  jmp     loc_1800086F3
0x18000802b  test    r12, r12
0x18000802e  jnz     short loc_18000803A
0x180008030  mov     eax, 44Fh
0x180008035  jmp     loc_1800086F3
0x18000803a  mov     rdx, [rbp+37h+arg_20]
0x18000803e  test    rdx, rdx
0x180008041  jnz     short loc_18000804D
0x180008043  mov     eax, 450h
0x180008048  jmp     loc_1800086F3
0x18000804d  movzx   r14d, [rbp+37h+arg_28]
0x180008052  cmp     r14w, 2
0x180008057  jbe     short loc_180008063
0x180008059  mov     eax, 451h
0x18000805e  jmp     loc_1800086F3
0x180008063  mov     eax, [rbp+37h+arg_70]
0x180008069  mov     [rbp+37h+var_58], rcx
0x18000806d  lea     rcx, [rbp+37h+var_58]
0x180008071  mov     [rbp+37h+var_50], r15d
0x180008075  mov     [rbp+37h+var_4C], eax
0x180008078  mov     [rbp+37h+var_48], rbx
0x18000807c  mov     [rdx], ebx
0x18000807e  call    GetNumGlyphs
0x180008083  movzx   esi, ax
0x180008086  test    si, si
0x180008089  jnz     short loc_180008095
0x18000808b  mov     eax, 3F1h
0x180008090  jmp     loc_1800086F3
0x180008095  mov     rcx, rsi; Size
0x180008098  call    Mem_Alloc
0x18000809d  mov     rdi, rax
0x1800080a0  test    rax, rax
0x1800080a3  jnz     short loc_1800080AF
0x1800080a5  mov     eax, 3EDh
0x1800080aa  jmp     loc_1800086F3
0x1800080af  movzx   r9d, [rbp+37h+arg_40]
0x1800080b7  lea     rax, [rbp+37h+arg_0]
0x1800080bb  movzx   r8d, [rbp+37h+arg_38]
0x1800080c0  lea     rcx, [rbp+37h+var_58]
0x1800080c4  movzx   edx, [rbp+37h+arg_48]
0x1800080cb  mov     dword ptr [rsp+50h], 1
0x1800080d3  mov     qword ptr [rsp+0E0h+var_98], rax
0x1800080d8  lea     rax, [rbp+37h+arg_78]
0x1800080df  mov     [rsp+0E0h+var_A0], rax
0x1800080e4  movzx   eax, [rbp+37h+arg_58]
0x1800080eb  mov     word ptr [rsp+0E0h+var_A8], si
0x1800080f0  mov     [rsp+0E0h+var_B0], rdi
0x1800080f5  mov     word ptr [rsp+0E0h+var_B8], ax
0x1800080fa  mov     rax, [rbp+37h+arg_50]
0x180008101  mov     [rsp+0E0h+var_C0], rax
0x180008106  call    MakeKeepGlyphList
0x18000810b  xor     ecx, ecx
0x18000810d  movzx   ebx, ax
0x180008110  test    ax, ax
0x180008113  jz      short loc_180008122
0x180008115  mov     rcx, rdi
0x180008118  call    Mem_Free
0x18000811d  jmp     loc_1800086F0
0x180008122  mov     rax, [r13+0]
0x180008126  mov     rbx, [rbp+37h+arg_60]
0x18000812d  mov     [rbp+37h+var_38], rax
0x180008131  test    rax, rax
0x180008134  jz      short loc_18000813C
0x180008136  cmp     [r12], ecx
0x18000813a  jnz     short loc_180008181
0x18000813c  movzx   r8d, [rbp+37h+arg_0]
0x180008141  lea     rcx, [rbp+37h+var_58]
0x180008145  mov     [rsp+0E0h+var_B8], r12
0x18000814a  movzx   r9d, r14w
0x18000814e  movzx   edx, si
0x180008151  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x180008156  call    CalcOutputBufferSize
0x18000815b  mov     edx, [r12]
0x18000815f  xor     ecx, ecx
0x180008161  mov     rax, rbx
0x180008164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008169  xor     ecx, ecx
0x18000816b  mov     [r13+0], rax
0x18000816f  test    rax, rax
0x180008172  jnz     short loc_180008181
0x180008174  mov     rcx, rdi
0x180008177  call    Mem_Free
0x18000817c  jmp     loc_1800080A5
0x180008181  mov     qword ptr [rbp+37h+var_78], rax
0x180008185  mov     eax, [r12]
0x180008189  mov     dword ptr [rbp+37h+var_78+8], eax
0x18000818c  mov     eax, 1
0x180008191  mov     dword ptr [rbp+37h+var_78+0Ch], ecx
0x180008194  mov     [rbp+37h+var_68], rbx
0x180008198  cmp     r14w, ax
0x18000819c  jz      short loc_1800081A8
0x18000819e  mov     r15d, ecx
0x1800081a1  cmp     r14w, 2
0x1800081a6  jnz     short loc_1800081AD
0x1800081a8  movzx   r15d, [rbp+37h+arg_0]
0x1800081ad  lea     r9, [rbp+37h+var_80]
0x1800081b1  movzx   r8d, r14w
0x1800081b5  lea     rdx, [rbp+37h+var_78]
0x1800081b9  lea     rcx, [rbp+37h+var_58]
0x1800081bd  call    CopyOffsetDirectoryTables
0x1800081c2  movzx   ebx, ax
0x1800081c5  test    ax, ax
0x1800081c8  jnz     loc_180008694
0x1800081ce  lea     r9, [rbp+37h+var_80]
0x1800081d2  lea     r8, aHead; "head"
0x1800081d9  lea     rdx, [rbp+37h+var_58]
0x1800081dd  lea     rcx, [rbp+37h+var_78]
0x1800081e1  call    CopyTableOver
0x1800081e6  movzx   ebx, ax
0x1800081e9  test    ax, ax
0x1800081ec  jnz     loc_180008694
0x1800081f2  lea     r9, [rbp+37h+var_80]
0x1800081f6  lea     r8, aHhea; "hhea"
0x1800081fd  lea     rdx, [rbp+37h+var_58]
0x180008201  lea     rcx, [rbp+37h+var_78]
0x180008205  call    CopyTableOver
0x18000820a  movzx   ebx, ax
0x18000820d  test    ax, ax
0x180008210  jnz     loc_180008694
0x180008216  lea     r9, [rbp+37h+var_80]
0x18000821a  lea     r8, aMaxp; "maxp"
0x180008221  lea     rdx, [rbp+37h+var_58]
0x180008225  lea     rcx, [rbp+37h+var_78]
0x180008229  call    CopyTableOver
0x18000822e  movzx   ebx, ax
0x180008231  test    ax, ax
0x180008234  jnz     loc_180008694
0x18000823a  mov     ebx, 1
0x18000823f  mov     r12d, ebx
0x180008242  cmp     r14w, 2
0x180008247  jz      short loc_180008261
0x180008249  lea     r9, [rbp+37h+var_80]
0x18000824d  lea     r8, aOs2; "OS/2"
0x180008254  lea     rdx, [rbp+37h+var_58]
0x180008258  lea     rcx, [rbp+37h+var_78]
0x18000825c  call    CopyTableOver
0x180008261  lea     rax, [rbp+37h+var_80]
0x180008265  movzx   r9d, si
0x180008269  mov     [rsp+0E0h+var_A8], rax
0x18000826e  lea     rdx, [rbp+37h+var_78]
0x180008272  movzx   eax, [rbp+37h+arg_78]
0x180008279  lea     rcx, [rbp+37h+var_58]
0x18000827d  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x180008281  mov     r8, rdi
0x180008284  mov     word ptr [rsp+0E0h+var_B8], ax
0x180008289  mov     word ptr [rsp+0E0h+var_C0], r15w
0x18000828f  call    ModXmtxXhea
0x180008294  movzx   ebx, ax
0x180008297  xor     eax, eax
0x180008299  test    bx, bx
0x18000829c  jz      short loc_1800082AF
0x18000829e  mov     ecx, 3EFh
0x1800082a3  cmp     bx, cx
0x1800082a6  jnz     loc_180008690
0x1800082ac  mov     r12d, eax
0x1800082af  lea     rax, [rbp+37h+var_80]
0x1800082b3  movzx   r9d, si
0x1800082b7  mov     [rsp+0E0h+var_B8], rax
0x1800082bc  lea     rdx, [rbp+37h+var_78]
0x1800082c0  mov     r8, rdi
0x1800082c3  mov     word ptr [rsp+0E0h+var_C0], r15w
0x1800082c9  lea     rcx, [rbp+37h+var_58]
0x1800082cd  call    ModLTSH
0x1800082d2  movzx   ebx, ax
0x1800082d5  test    ax, ax
0x1800082d8  jnz     loc_180008690
0x1800082de  lea     r9, [rbp+37h+var_80]
0x1800082e2  movzx   r8d, r14w
0x1800082e6  lea     rdx, [rbp+37h+var_78]
0x1800082ea  lea     rcx, [rbp+37h+var_58]
0x1800082ee  call    ModVDMX
0x1800082f3  movzx   ebx, ax
0x1800082f6  test    ax, ax
0x1800082f9  jnz     loc_180008690
0x1800082ff  mov     eax, 1
0x180008304  cmp     r12d, eax
0x180008307  jnz     short loc_18000833D
0x180008309  lea     rax, [rbp+37h+var_80]
0x18000830d  movzx   r9d, si
0x180008311  mov     [rsp+0E0h+var_B8], rax
0x180008316  lea     rdx, [rbp+37h+var_78]
0x18000831a  mov     r8, rdi
0x18000831d  mov     word ptr [rsp+0E0h+var_C0], r15w
0x180008323  lea     rcx, [rbp+37h+var_58]
0x180008327  call    ModHdmx
0x18000832c  xor     r12d, r12d
0x18000832f  movzx   ebx, ax
0x180008332  test    ax, ax
0x180008335  jnz     loc_180008690
0x18000833b  jmp     short loc_180008358
0x18000833d  lea     r9, [rbp+37h+var_80]
0x180008341  lea     r8, aHdmx; "hdmx"
0x180008348  lea     rdx, [rbp+37h+var_58]
0x18000834c  lea     rcx, [rbp+37h+var_78]
0x180008350  call    CopyTableOver
0x180008355  xor     r12d, r12d
0x180008358  lea     rax, [rbp+37h+var_80]
0x18000835c  movzx   r9d, si
0x180008360  mov     [rsp+0E0h+var_B0], rax
0x180008365  lea     rdx, [rbp+37h+var_78]
0x180008369  lea     rax, [rbp+37h+var_60]
0x18000836d  mov     r8, rdi
0x180008370  mov     [rsp+0E0h+var_B8], rax
0x180008375  lea     rcx, [rbp+37h+var_58]
0x180008379  lea     rax, [rbp+37h+var_5C]
0x18000837d  mov     [rsp+0E0h+var_C0], rax
0x180008382  call    ModCmap
0x180008387  movzx   ebx, ax
0x18000838a  test    ax, ax
0x18000838d  jnz     loc_180008690
0x180008393  cmp     r14w, 2
0x180008398  jz      short loc_1800083E2
0x18000839a  lea     r9, [rbp+37h+var_80]
0x18000839e  lea     r8, aFpgm; "fpgm"
0x1800083a5  lea     rdx, [rbp+37h+var_58]
0x1800083a9  lea     rcx, [rbp+37h+var_78]
0x1800083ad  call    CopyTableOver
0x1800083b2  lea     r9, [rbp+37h+var_80]
0x1800083b6  lea     r8, aPrep; "prep"
0x1800083bd  lea     rdx, [rbp+37h+var_58]
0x1800083c1  lea     rcx, [rbp+37h+var_78]
0x1800083c5  call    CopyTableOver
0x1800083ca  lea     r9, [rbp+37h+var_80]
0x1800083ce  lea     r8, aCvt; "cvt "
0x1800083d5  lea     rdx, [rbp+37h+var_58]
0x1800083d9  lea     rcx, [rbp+37h+var_78]
0x1800083dd  call    CopyTableOver
0x1800083e2  lea     rax, [rbp+37h+var_80]
0x1800083e6  movzx   r9d, si
0x1800083ea  mov     [rsp+0E0h+var_B8], rax
0x1800083ef  lea     rdx, [rbp+37h+var_78]
0x1800083f3  lea     rax, [rbp+37h+var_40]
0x1800083f7  mov     r8, rdi
0x1800083fa  lea     rcx, [rbp+37h+var_58]
0x1800083fe  mov     [rsp+0E0h+var_C0], rax
0x180008403  call    ModGlyfLocaAndHead
0x180008408  movzx   ebx, ax
0x18000840b  test    ax, ax
0x18000840e  jnz     loc_180008690
0x180008414  lea     r8, [rbp+37h+var_80]
0x180008418  lea     rdx, [rbp+37h+var_78]
0x18000841c  lea     rcx, [rbp+37h+var_58]
0x180008420  call    ModMaxP
0x180008425  movzx   ebx, ax
0x180008428  test    ax, ax
0x18000842b  jnz     loc_180008690
0x180008431  movzx   r9d, [rbp+37h+var_60]
0x180008436  lea     rax, [rbp+37h+var_80]
0x18000843a  movzx   r8d, [rbp+37h+var_5C]
0x18000843f  lea     rdx, [rbp+37h+var_78]
0x180008443  mov     [rsp+0E0h+var_B8], rax
0x180008448  lea     rcx, [rbp+37h+var_58]
0x18000844c  mov     word ptr [rsp+0E0h+var_C0], r14w
0x180008452  call    ModOS2
0x180008457  movzx   ebx, ax
0x18000845a  test    ax, ax
0x18000845d  jnz     loc_180008690
0x180008463  lea     rax, [rbp+37h+var_80]
0x180008467  movzx   r9d, si
0x18000846b  mov     [rsp+0E0h+var_B8], rax
0x180008470  lea     rdx, [rbp+37h+var_78]
  ... truncated ...
```
