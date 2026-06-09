# BCParsePath

- ea: `0x140069f40`
- end: `0x14006a3cb`
- name: `BCParsePath`
- size: `1163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400675a0`
- `0x140069f40`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall BCParsePath(
        _QWORD *a1,
        __int64 a2,
        void (__fastcall **a3)(_QWORD, _QWORD, _QWORD, _QWORD),
        _DWORD *a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  unsigned int v7; // r9d
  void (__fastcall **v8)(_QWORD, _QWORD, _QWORD, _QWORD); // r10
  __int64 v9; // rbx
  int v10; // r15d
  void (__fastcall *v11)(__int64, __int64, _QWORD, _QWORD); // rax
  int v12; // r13d
  int v13; // r12d
  __int64 v14; // r8
  int i; // r11d
  int v16; // edi
  int v17; // esi
  int v18; // r14d
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  void (__fastcall *v26)(__int64 *, __int64, __int64); // rax
  int v27; // r11d
  void (__fastcall *v28)(__int64); // rax
  int v29; // r8d
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  void (__fastcall *v35)(__int64 *, __int64 *, __int64 *, __int64 *, __int64); // rax
  int v36; // ecx
  void (__fastcall *v37)(__int64 *, __int64, __int64); // rax
  _QWORD *v38; // rbx
  void (__fastcall *v39)(__int64); // rax
  unsigned int v41; // [rsp+30h] [rbp-50h]
  int v42; // [rsp+34h] [rbp-4Ch]
  __int64 v43; // [rsp+38h] [rbp-48h] BYREF
  int v44; // [rsp+40h] [rbp-40h]
  __int64 v45; // [rsp+48h] [rbp-38h] BYREF
  int v46; // [rsp+50h] [rbp-30h]
  __int64 v47; // [rsp+58h] [rbp-28h] BYREF
  __int64 v48; // [rsp+60h] [rbp-20h] BYREF
  __int64 v49; // [rsp+68h] [rbp-18h] BYREF
  int v50; // [rsp+70h] [rbp-10h]
  _QWORD *v51; // [rsp+C0h] [rbp+40h]

  v51 = a1;
  v7 = a5;
  v8 = a3;
  v42 = 1;
  v9 = (__int64)(a1 + 1);
  v43 = 0;
  v10 = 0;
  v11 = *a3;
  v12 = 0;
  v47 = 0;
  v13 = 0;
  v48 = 0;
  v14 = 0;
  v49 = 0;
  i = 0;
  v41 = 0;
  v16 = 0;
  v46 = 0;
  v17 = 0;
  v50 = 0;
  v18 = 0;
  v44 = 0;
  v45 = 0;
  if ( !v11 )
    goto LABEL_4;
  v11(a7, a2, 0, a5);
  v14 = 0;
  for ( i = 0; ; i = v44 )
  {
    v7 = a5;
    v8 = a3;
LABEL_4:
    v19 = *(_DWORD *)(v9 + 4LL * v16);
    if ( v19 > 1548 )
      return 4294967294LL;
    if ( v19 == 1548 )
    {
      if ( i )
      {
        v18 = 0;
        v44 = 0;
        v17 = 0;
      }
      else
      {
        v44 = 1;
        v18 = *(_DWORD *)(v9 + 4 * (v16 + (v7 != 0) + 3LL));
        v17 = *(_DWORD *)(v9 + 4 * (v16 + 4LL - (v7 != 0)));
      }
      goto LABEL_95;
    }
    if ( v19 > 14 )
    {
      v30 = v19 - 15;
      if ( v30 )
      {
        v31 = v30 - 1;
        if ( v31 )
        {
          v32 = v31 - 5;
          if ( !v32 || (v33 = v32 - 1) == 0 )
          {
LABEL_82:
            if ( v7 )
            {
              LODWORD(v45) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 16);
              v36 = *(_DWORD *)(v9 + 4LL * v16 + 12);
            }
            else
            {
              LODWORD(v45) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 12);
              v36 = *(_DWORD *)(v9 + 4LL * v16 + 16);
            }
            v37 = (void (__fastcall *)(__int64 *, __int64, __int64))v8[1];
            HIDWORD(v45) = v17 + v36;
            v37(&v45, a7, v14);
            v14 = v41;
LABEL_95:
            v16 += 5;
LABEL_96:
            v27 = v42;
            goto LABEL_97;
          }
          if ( (unsigned int)(v33 - 8) > 1 )
            return 4294967294LL;
LABEL_43:
          if ( v7 )
          {
            LODWORD(v43) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 8);
            HIDWORD(v43) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 4);
            LODWORD(v47) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 16);
            HIDWORD(v47) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 12);
            LODWORD(v48) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 24);
            HIDWORD(v48) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 20);
            LODWORD(v49) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 32);
            v34 = *(_DWORD *)(v9 + 4LL * v16 + 28);
          }
          else
          {
            LODWORD(v43) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 4);
            HIDWORD(v43) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 8);
            LODWORD(v47) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 12);
            HIDWORD(v47) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 16);
            LODWORD(v48) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 20);
            HIDWORD(v48) = v17 + *(_DWORD *)(v9 + 4LL * v16 + 24);
            LODWORD(v49) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 28);
            v34 = *(_DWORD *)(v9 + 4LL * v16 + 32);
          }
          v35 = (void (__fastcall *)(__int64 *, __int64 *, __int64 *, __int64 *, __int64))v8[3];
          HIDWORD(v49) = v17 + v34;
          v35(&v43, &v47, &v48, &v49, a7);
          if ( v42 )
          {
            v12 = v45;
            v14 = (unsigned int)v45;
            v10 = HIDWORD(v45);
            v13 = HIDWORD(v45);
          }
          else
          {
            v14 = v41;
          }
          v27 = 0;
          v42 = 0;
          if ( (int)v43 > v12 )
            v12 = v43;
          if ( (int)v43 < (int)v14 )
            v14 = (unsigned int)v43;
          if ( SHIDWORD(v43) > v10 )
            v10 = HIDWORD(v43);
          if ( SHIDWORD(v43) < v13 )
            v13 = HIDWORD(v43);
          if ( (int)v47 > v12 )
            v12 = v47;
          if ( (int)v47 < (int)v14 )
            v14 = (unsigned int)v47;
          if ( SHIDWORD(v47) > v10 )
            v10 = HIDWORD(v47);
          if ( SHIDWORD(v47) < v13 )
            v13 = HIDWORD(v47);
          if ( (int)v48 > v12 )
            v12 = v48;
          if ( (int)v48 < (int)v14 )
            v14 = (unsigned int)v48;
          if ( SHIDWORD(v48) > v10 )
            v10 = HIDWORD(v48);
          if ( SHIDWORD(v48) < v13 )
            v13 = HIDWORD(v48);
          if ( (int)v49 > v12 )
            v12 = v49;
          if ( (int)v49 < (int)v14 )
            v14 = (unsigned int)v49;
          v41 = v14;
          if ( SHIDWORD(v49) > v10 )
            v10 = HIDWORD(v49);
          if ( SHIDWORD(v49) < v13 )
            v13 = HIDWORD(v49);
          v16 += 9;
          goto LABEL_97;
        }
        v38 = v51;
        v16 = 0;
        if ( !*v51 )
          os_raise(0xFFFFFFFFLL, 0);
        v51 = (_QWORD *)*v51;
        v9 = *v38 + 8LL;
LABEL_15:
        v14 = v41;
        goto LABEL_96;
      }
      v39 = (void (__fastcall *)(__int64))v8[5];
      if ( v39 )
        v39(a7);
      v50 = 1;
LABEL_37:
      ++v16;
      goto LABEL_15;
    }
    if ( v19 == 14 )
    {
      if ( !v50 )
      {
        v28 = (void (__fastcall *)(__int64))v8[5];
        if ( v28 )
          v28(a7);
      }
      v29 = v46;
      if ( !v44 )
        v29 = 1;
      v46 = v29;
      goto LABEL_37;
    }
    v20 = v19 - 4;
    if ( !v20 )
      goto LABEL_82;
    v21 = v20 - 1;
    if ( v21 )
    {
      v22 = v21 - 1;
      if ( v22 )
      {
        v23 = v22 - 1;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            if ( v24 != 1 )
              return 4294967294LL;
            ((void (__fastcall *)(__int64))v8[4])(a7);
            v16 += 3;
            goto LABEL_15;
          }
          goto LABEL_43;
        }
      }
    }
    if ( v7 )
    {
      LODWORD(v43) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 16);
      v25 = *(_DWORD *)(v9 + 4LL * v16 + 12);
    }
    else
    {
      LODWORD(v43) = v18 + *(_DWORD *)(v9 + 4LL * v16 + 12);
      v25 = *(_DWORD *)(v9 + 4LL * v16 + 16);
    }
    v26 = (void (__fastcall *)(__int64 *, __int64, __int64))v8[2];
    HIDWORD(v43) = v17 + v25;
    v26(&v43, a7, v14);
    if ( v42 )
    {
      v12 = v45;
      v14 = (unsigned int)v45;
      v10 = HIDWORD(v45);
      v13 = HIDWORD(v45);
    }
    else
    {
      v14 = v41;
    }
    v27 = 0;
    v42 = 0;
    if ( (int)v43 > v12 )
      v12 = v43;
    if ( (int)v43 < (int)v14 )
      v14 = (unsigned int)v43;
    v41 = v14;
    if ( SHIDWORD(v43) > v10 )
      v10 = HIDWORD(v43);
    if ( SHIDWORD(v43) < v13 )
      v13 = HIDWORD(v43);
    v16 += 5;
LABEL_97:
    if ( v46 )
      break;
  }
  a4[2] = v12 + 1;
  a4[3] = v10 + 1;
  *a4 = v14;
  a4[1] = v13;
  if ( v27 )
    *((_QWORD *)a4 + 1) = 0;
  return 0;
}

```

## disassembly

```asm
0x140069f40  mov     rax, rsp
0x140069f43  mov     [rax+10h], rbx
0x140069f47  mov     [rax+20h], r9
0x140069f4b  mov     [rax+18h], r8
0x140069f4f  mov     [rax+8], rcx
0x140069f53  push    rbp
0x140069f54  push    rsi
0x140069f55  push    rdi
0x140069f56  push    r12
0x140069f58  push    r13
0x140069f5a  push    r14
0x140069f5c  push    r15
0x140069f5e  mov     rbp, rsp
0x140069f61  sub     rsp, 80h
0x140069f68  mov     r9d, [rbp+arg_20]
0x140069f6c  mov     r10, r8
0x140069f6f  mov     rbx, rcx
0x140069f72  mov     [rbp+var_4C], 1
0x140069f79  xor     ecx, ecx
0x140069f7b  add     rbx, 8
0x140069f7f  mov     [rbp+var_48], rcx
0x140069f83  mov     r15d, ecx
0x140069f86  mov     rax, [r10]
0x140069f89  mov     r13d, ecx
0x140069f8c  mov     [rbp+var_28], rcx
0x140069f90  mov     r12d, ecx
0x140069f93  mov     [rbp+var_20], rcx
0x140069f97  mov     r8d, ecx
0x140069f9a  mov     [rbp+var_18], rcx
0x140069f9e  mov     r11d, ecx
0x140069fa1  mov     [rbp+var_50], ecx
0x140069fa4  mov     edi, ecx
0x140069fa6  mov     [rbp+var_30], ecx
0x140069fa9  mov     esi, ecx
0x140069fab  mov     [rbp+var_10], ecx
0x140069fae  mov     r14d, ecx
0x140069fb1  mov     [rbp+var_40], ecx
0x140069fb4  mov     [rbp+var_38], rcx
0x140069fb8  test    rax, rax
0x140069fbb  jz      short loc_140069FD4
0x140069fbd  mov     rcx, [rbp+arg_30]
0x140069fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069fc6  mov     r8d, r14d
0x140069fc9  mov     r11d, r14d
0x140069fcc  mov     r9d, [rbp+arg_20]
0x140069fd0  mov     r10, [rbp+arg_10]
0x140069fd4  movsxd  rdx, edi
0x140069fd7  mov     ecx, [rbx+rdx*4]
0x140069fda  cmp     ecx, 60Ch
0x140069fe0  jg      loc_14006A3AB
0x140069fe6  jz      loc_14006A323
0x140069fec  cmp     ecx, 0Eh
0x140069fef  jg      loc_14006A0FA
0x140069ff5  jz      loc_14006A0C6
0x140069ffb  sub     ecx, 4
0x140069ffe  jz      loc_14006A29D
0x14006a004  sub     ecx, 1
0x14006a007  jz      short loc_14006A03E
0x14006a009  sub     ecx, 1
0x14006a00c  jz      short loc_14006A03E
0x14006a00e  sub     ecx, 1
0x14006a011  jz      short loc_14006A03E
0x14006a013  sub     ecx, 1
0x14006a016  jz      loc_14006A12C
0x14006a01c  cmp     ecx, 1
0x14006a01f  jnz     loc_14006A3AB
0x14006a025  mov     rcx, [rbp+arg_30]
0x14006a029  mov     rax, [r10+20h]
0x14006a02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a032  add     edi, 3
0x14006a035  mov     r8d, [rbp+var_50]
0x14006a039  jmp     loc_14006A36E
0x14006a03e  test    r9d, r9d
0x14006a041  jz      short loc_14006A053
0x14006a043  mov     ecx, [rbx+rdx*4+10h]
0x14006a047  add     ecx, r14d
0x14006a04a  mov     dword ptr [rbp+var_48], ecx
0x14006a04d  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a051  jmp     short loc_14006A061
0x14006a053  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a057  add     ecx, r14d
0x14006a05a  mov     dword ptr [rbp+var_48], ecx
0x14006a05d  mov     ecx, [rbx+rdx*4+10h]
0x14006a061  mov     rdx, [rbp+arg_30]
0x14006a065  add     ecx, esi
0x14006a067  mov     rax, [r10+10h]
0x14006a06b  mov     dword ptr [rbp+var_48+4], ecx
0x14006a06e  lea     rcx, [rbp+var_48]
0x14006a072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a077  cmp     [rbp+var_4C], 0
0x14006a07b  jz      short loc_14006A08D
0x14006a07d  mov     r13d, dword ptr [rbp+var_38]
0x14006a081  mov     r8d, r13d
0x14006a084  mov     r15d, dword ptr [rbp+var_38+4]
0x14006a088  mov     r12d, r15d
0x14006a08b  jmp     short loc_14006A091
0x14006a08d  mov     r8d, [rbp+var_50]
0x14006a091  mov     eax, dword ptr [rbp+var_48]
0x14006a094  xor     r11d, r11d
0x14006a097  cmp     eax, r13d
0x14006a09a  mov     [rbp+var_4C], r11d
0x14006a09e  cmovg   r13d, eax
0x14006a0a2  cmp     eax, r8d
0x14006a0a5  cmovl   r8d, eax
0x14006a0a9  mov     eax, dword ptr [rbp+var_48+4]
0x14006a0ac  cmp     eax, r15d
0x14006a0af  mov     [rbp+var_50], r8d
0x14006a0b3  cmovg   r15d, eax
0x14006a0b7  cmp     eax, r12d
0x14006a0ba  cmovl   r12d, eax
0x14006a0be  add     edi, 5
0x14006a0c1  jmp     loc_14006A372
0x14006a0c6  cmp     [rbp+var_10], 0
0x14006a0ca  jnz     short loc_14006A0DE
0x14006a0cc  mov     rax, [r10+28h]
0x14006a0d0  test    rax, rax
0x14006a0d3  jz      short loc_14006A0DE
0x14006a0d5  mov     rcx, [rbp+arg_30]
0x14006a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a0de  mov     r8d, [rbp+var_30]
0x14006a0e2  mov     eax, 1
0x14006a0e7  cmp     [rbp+var_40], 0
0x14006a0eb  cmovz   r8d, eax
0x14006a0ef  mov     [rbp+var_30], r8d
0x14006a0f3  add     edi, eax
0x14006a0f5  jmp     loc_14006A035
0x14006a0fa  sub     ecx, 0Fh
0x14006a0fd  jz      loc_14006A304
0x14006a103  sub     ecx, 1
0x14006a106  jz      loc_14006A2DF
0x14006a10c  sub     ecx, 5
0x14006a10f  jz      loc_14006A29D
0x14006a115  sub     ecx, 1
0x14006a118  jz      loc_14006A29D
0x14006a11e  sub     ecx, 8
0x14006a121  jz      short loc_14006A12C
0x14006a123  cmp     ecx, 1
0x14006a126  jnz     loc_14006A3AB
0x14006a12c  test    r9d, r9d
0x14006a12f  jz      short loc_14006A17A
0x14006a131  mov     ecx, [rbx+rdx*4+8]
0x14006a135  add     ecx, r14d
0x14006a138  mov     dword ptr [rbp+var_48], ecx
0x14006a13b  mov     ecx, [rbx+rdx*4+4]
0x14006a13f  add     ecx, esi
0x14006a141  mov     dword ptr [rbp+var_48+4], ecx
0x14006a144  mov     ecx, [rbx+rdx*4+10h]
0x14006a148  add     ecx, r14d
0x14006a14b  mov     dword ptr [rbp+var_28], ecx
0x14006a14e  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a152  add     ecx, esi
0x14006a154  mov     dword ptr [rbp+var_28+4], ecx
0x14006a157  mov     ecx, [rbx+rdx*4+18h]
0x14006a15b  add     ecx, r14d
0x14006a15e  mov     dword ptr [rbp+var_20], ecx
0x14006a161  mov     ecx, [rbx+rdx*4+14h]
0x14006a165  add     ecx, esi
0x14006a167  mov     dword ptr [rbp+var_20+4], ecx
0x14006a16a  mov     ecx, [rbx+rdx*4+20h]
0x14006a16e  add     ecx, r14d
0x14006a171  mov     dword ptr [rbp+var_18], ecx
0x14006a174  mov     ecx, [rbx+rdx*4+1Ch]
0x14006a178  jmp     short loc_14006A1C1
0x14006a17a  mov     ecx, [rbx+rdx*4+4]
0x14006a17e  add     ecx, r14d
0x14006a181  mov     dword ptr [rbp+var_48], ecx
0x14006a184  mov     ecx, [rbx+rdx*4+8]
0x14006a188  add     ecx, esi
0x14006a18a  mov     dword ptr [rbp+var_48+4], ecx
0x14006a18d  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a191  add     ecx, r14d
0x14006a194  mov     dword ptr [rbp+var_28], ecx
0x14006a197  mov     ecx, [rbx+rdx*4+10h]
0x14006a19b  add     ecx, esi
0x14006a19d  mov     dword ptr [rbp+var_28+4], ecx
0x14006a1a0  mov     ecx, [rbx+rdx*4+14h]
0x14006a1a4  add     ecx, r14d
0x14006a1a7  mov     dword ptr [rbp+var_20], ecx
0x14006a1aa  mov     ecx, [rbx+rdx*4+18h]
0x14006a1ae  add     ecx, esi
0x14006a1b0  mov     dword ptr [rbp+var_20+4], ecx
0x14006a1b3  mov     ecx, [rbx+rdx*4+1Ch]
0x14006a1b7  add     ecx, r14d
0x14006a1ba  mov     dword ptr [rbp+var_18], ecx
0x14006a1bd  mov     ecx, [rbx+rdx*4+20h]
0x14006a1c1  mov     rax, [rbp+arg_30]
0x14006a1c5  lea     r9, [rbp+var_18]
0x14006a1c9  add     ecx, esi
0x14006a1cb  mov     [rsp+80h+var_60], rax
0x14006a1d0  mov     rax, [r10+18h]
0x14006a1d4  lea     r8, [rbp+var_20]
0x14006a1d8  mov     dword ptr [rbp+var_18+4], ecx
0x14006a1db  lea     rdx, [rbp+var_28]
0x14006a1df  lea     rcx, [rbp+var_48]
0x14006a1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a1e8  cmp     [rbp+var_4C], 0
0x14006a1ec  jz      short loc_14006A1FE
0x14006a1ee  mov     r13d, dword ptr [rbp+var_38]
0x14006a1f2  mov     r8d, r13d
0x14006a1f5  mov     r15d, dword ptr [rbp+var_38+4]
0x14006a1f9  mov     r12d, r15d
0x14006a1fc  jmp     short loc_14006A202
0x14006a1fe  mov     r8d, [rbp+var_50]
0x14006a202  mov     eax, dword ptr [rbp+var_48]
0x14006a205  xor     r11d, r11d
0x14006a208  cmp     eax, r13d
0x14006a20b  mov     [rbp+var_4C], r11d
0x14006a20f  cmovg   r13d, eax
0x14006a213  cmp     eax, r8d
0x14006a216  cmovl   r8d, eax
0x14006a21a  mov     eax, dword ptr [rbp+var_48+4]
0x14006a21d  cmp     eax, r15d
0x14006a220  cmovg   r15d, eax
0x14006a224  cmp     eax, r12d
0x14006a227  cmovl   r12d, eax
0x14006a22b  mov     eax, dword ptr [rbp+var_28]
0x14006a22e  cmp     eax, r13d
0x14006a231  cmovg   r13d, eax
0x14006a235  cmp     eax, r8d
0x14006a238  cmovl   r8d, eax
0x14006a23c  mov     eax, dword ptr [rbp+var_28+4]
0x14006a23f  cmp     eax, r15d
0x14006a242  cmovg   r15d, eax
0x14006a246  cmp     eax, r12d
0x14006a249  cmovl   r12d, eax
0x14006a24d  mov     eax, dword ptr [rbp+var_20]
0x14006a250  cmp     eax, r13d
0x14006a253  cmovg   r13d, eax
0x14006a257  cmp     eax, r8d
0x14006a25a  cmovl   r8d, eax
0x14006a25e  mov     eax, dword ptr [rbp+var_20+4]
0x14006a261  cmp     eax, r15d
0x14006a264  cmovg   r15d, eax
0x14006a268  cmp     eax, r12d
0x14006a26b  cmovl   r12d, eax
0x14006a26f  mov     eax, dword ptr [rbp+var_18]
0x14006a272  cmp     eax, r13d
0x14006a275  cmovg   r13d, eax
0x14006a279  cmp     eax, r8d
0x14006a27c  cmovl   r8d, eax
0x14006a280  mov     eax, dword ptr [rbp+var_18+4]
0x14006a283  cmp     eax, r15d
0x14006a286  mov     [rbp+var_50], r8d
0x14006a28a  cmovg   r15d, eax
0x14006a28e  cmp     eax, r12d
0x14006a291  cmovl   r12d, eax
0x14006a295  add     edi, 9
0x14006a298  jmp     loc_14006A372
0x14006a29d  test    r9d, r9d
0x14006a2a0  jz      short loc_14006A2B2
0x14006a2a2  mov     ecx, [rbx+rdx*4+10h]
0x14006a2a6  add     ecx, r14d
0x14006a2a9  mov     dword ptr [rbp+var_38], ecx
0x14006a2ac  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a2b0  jmp     short loc_14006A2C0
0x14006a2b2  mov     ecx, [rbx+rdx*4+0Ch]
0x14006a2b6  add     ecx, r14d
0x14006a2b9  mov     dword ptr [rbp+var_38], ecx
0x14006a2bc  mov     ecx, [rbx+rdx*4+10h]
0x14006a2c0  mov     rdx, [rbp+arg_30]
0x14006a2c4  add     ecx, esi
0x14006a2c6  mov     rax, [r10+8]
0x14006a2ca  mov     dword ptr [rbp+var_38+4], ecx
0x14006a2cd  lea     rcx, [rbp+var_38]
0x14006a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a2d6  mov     r8d, [rbp+var_50]
0x14006a2da  jmp     loc_14006A36B
0x14006a2df  mov     rbx, [rbp+arg_0]
0x14006a2e3  xor     edi, edi
0x14006a2e5  cmp     [rbx], rdi
0x14006a2e8  jnz     short loc_14006A2F4
0x14006a2ea  xor     edx, edx
0x14006a2ec  or      ecx, 0FFFFFFFFh
0x14006a2ef  call    os_raise
0x14006a2f4  mov     rax, [rbx]
0x14006a2f7  mov     [rbp+arg_0], rax
0x14006a2fb  lea     rbx, [rax+8]
0x14006a2ff  jmp     loc_14006A035
0x14006a304  mov     rax, [r10+28h]
0x14006a308  test    rax, rax
0x14006a30b  jz      short loc_14006A316
0x14006a30d  mov     rcx, [rbp+arg_30]
0x14006a311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a316  mov     eax, 1
0x14006a31b  mov     [rbp+var_10], eax
0x14006a31e  jmp     loc_14006A0F3
0x14006a323  test    r11d, r11d
0x14006a326  jz      short loc_14006A336
0x14006a328  xor     r14d, r14d
0x14006a32b  mov     [rbp+var_40], 0
0x14006a332  xor     esi, esi
0x14006a334  jmp     short loc_14006A36B
0x14006a336  mov     eax, r9d
0x14006a339  mov     [rbp+var_40], 1
0x14006a340  neg     eax
0x14006a342  movsxd  rax, edi
0x14006a345  sbb     rcx, rcx
0x14006a348  neg     rcx
0x14006a34b  add     rcx, 3
0x14006a34f  add     rcx, rax
  ... truncated ...
```
