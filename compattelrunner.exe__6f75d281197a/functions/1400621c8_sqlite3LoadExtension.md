# sqlite3LoadExtension

- ea: `0x1400621c8`
- end: `0x140062654`
- name: `sqlite3LoadExtension`
- size: `1164`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14008b6c0`

## callees

- `0x140053e3c`
- `0x140053fec`
- `0x1400621c8`
- `0x14008ac90`
- `0x14008b820`
- `0x14008b8d0`
- `0x14008ccd0`
- `0x14008eb20`
- `0x1400a7308`
- `0x1400a8010`

## string_xrefs

- `0x14006223b`: `sqlite3_extension_init`
- `0x140062543`: `error during initialization: %s`
- `0x140062617`: `unable to open shared library [%.*s]`

## pseudocode

```c
__int64 __fastcall sqlite3LoadExtension(__int64 *a1, const char *a2, const char *a3, const char **a4)
{
  __int64 v4; // rdi
  __int64 v8; // r15
  const char *v9; // r14
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  _QWORD *v15; // r15
  int v16; // r14d
  __int64 v17; // r14
  int v19; // eax
  int v20; // r8d
  int v21; // edx
  unsigned int i; // ecx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // ebx
  const char *v27; // rax
  int v28; // eax
  void *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // rax
  __int64 v33; // [rsp+30h] [rbp-58h]
  __int64 v34; // [rsp+38h] [rbp-50h]
  __int64 v35; // [rsp+40h] [rbp-48h]
  int v36; // [rsp+90h] [rbp+8h]
  __int64 (__fastcall *v37)(__int64 *, const char **, __int64 (__fastcall **)()); // [rsp+90h] [rbp+8h]
  const char *v39; // [rsp+A8h] [rbp+20h] BYREF

  v4 = *a1;
  v39 = 0;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v35 = v8;
  if ( a4 )
    *a4 = 0;
  if ( (a1[6] & 0x10000) != 0 )
  {
    v9 = a3;
    if ( !a3 )
      v9 = "sqlite3_extension_init";
    if ( (unsigned __int64)(v8 - 1) > 0x103 )
    {
LABEL_59:
      if ( a4 )
      {
        v32 = (const char *)sqlite3_malloc64(v8 + 300);
        v39 = v32;
        *a4 = v32;
        if ( v32 )
        {
          sqlite3_snprintf((unsigned int)(v8 + 300), v32, "unable to open shared library [%.*s]", 260, a2);
          (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v8 + 299), v39);
        }
      }
      return 1;
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(v4 + 72))(v4);
    v11 = 0;
    v36 = 0;
    while ( !v10 )
    {
      v33 = v11;
      v34 = sqlite3_mprintf("%s.%s", a2, off_1400AA308[v11]);
      v12 = v34;
      if ( !v34 )
        return 7;
      v13 = -1;
      do
        ++v13;
      while ( off_1400AA308[v33][v13] );
      if ( (unsigned __int64)(v13 + v8 + 1) <= 0x104 )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 72))(v4, v34);
        v12 = v34;
        v10 = v14;
      }
      sqlite3_free(v12);
      v11 = (unsigned int)(v36 + 1);
      v36 = v11;
      if ( (int)v11 >= 1 )
      {
        if ( !v10 )
          goto LABEL_59;
        break;
      }
    }
    v15 = 0;
    v37 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, const char *))(v4 + 88))(
                                                                                         v4,
                                                                                         v10,
                                                                                         v9);
    if ( !v37 )
    {
      if ( a3 )
        goto LABEL_41;
      if ( a2 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v16 = v17 & 0x3FFFFFFF;
      }
      else
      {
        v16 = 0;
      }
      v15 = (_QWORD *)sqlite3_malloc64((unsigned int)(v16 + 30));
      if ( !v15 )
      {
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 7;
      }
      *v15 = 0x5F336574696C7173LL;
      do
        --v16;
      while ( v16 >= 0 && a2[v16] != 47 && a2[v16] != 92 );
      v19 = sqlite3_strnicmp(&a2[v16 + 1], "lib", 3);
      v20 = 8;
      v21 = v16 + (v19 != 0 ? 1 : 4);
      for ( i = a2[v21]; a2[v21]; i = a2[++v21] )
      {
        if ( i == 46 )
          break;
        if ( (byte_1400B2300[(unsigned __int8)i] & 2) != 0 )
        {
          v23 = i;
          v24 = v20++;
          *((_BYTE *)v15 + v24) = *((_BYTE *)qword_1400B2890 + v23);
        }
      }
      strcpy((char *)v15 + v20, "_init");
      v37 = (__int64 (__fastcall *)(__int64 *, const char **, __int64 (__fastcall **)()))(*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(v4 + 88))(
                                                                                           v4,
                                                                                           v10,
                                                                                           v15);
      if ( !v37 )
      {
        v9 = (const char *)v15;
LABEL_41:
        if ( a4 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v9[v25] );
          v26 = v25 + v35;
          v27 = (const char *)sqlite3_malloc64(v25 + v35 + 300);
          v39 = v27;
          *a4 = v27;
          if ( v27 )
          {
            sqlite3_snprintf((unsigned int)(v26 + 300), v27, "no entry point [%s] in shared library [%s]", v9, a2);
            (*(void (__fastcall **)(__int64, _QWORD, const char *))(v4 + 80))(v4, (unsigned int)(v26 + 299), v39);
          }
        }
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        sqlite3_free(v15);
        return 1;
      }
    }
    sqlite3_free(v15);
    v28 = v37(a1, &v39, off_1400A9650);
    if ( v28 )
    {
      if ( v28 != 256 )
      {
        if ( a4 )
          *a4 = (const char *)sqlite3_mprintf("error during initialization: %s", v39);
        sqlite3_free(v39);
        (*(void (__fastcall **)(__int64, __int64))(v4 + 96))(v4, v10);
        return 1;
      }
    }
    else
    {
      v29 = (void *)sqlite3DbMallocZero(a1, 8LL * *((int *)a1 + 59) + 8);
      if ( !v29 )
        return 7;
      v30 = *((int *)a1 + 59);
      if ( (int)v30 > 0 )
        memcpy_0(v29, (const void *)a1[30], 8 * v30);
      if ( a1[30] )
        sqlite3DbFreeNN(a1);
      v31 = *((int *)a1 + 59);
      a1[30] = (__int64)v29;
      *((_QWORD *)v29 + v31) = v10;
      ++*((_DWORD *)a1 + 59);
    }
    return 0;
  }
  if ( a4 )
    *a4 = (const char *)sqlite3_mprintf("not authorized");
  return 1;
}

```

## disassembly

```asm
0x1400621c8  mov     rax, rsp
0x1400621cb  mov     [rax+18h], r8
0x1400621cf  push    rbx
0x1400621d0  push    rsi
0x1400621d1  push    rdi
0x1400621d2  push    r12
0x1400621d4  push    r13
0x1400621d6  push    r14
0x1400621d8  push    r15
0x1400621da  sub     rsp, 50h
0x1400621de  mov     rdi, [rcx]
0x1400621e1  mov     rsi, r9
0x1400621e4  mov     r12, rdx
0x1400621e7  mov     qword ptr [rax+20h], 0
0x1400621ef  mov     rbx, rcx
0x1400621f2  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400621f6  inc     r15
0x1400621f9  cmp     byte ptr [rdx+r15], 0
0x1400621fe  jnz     short loc_1400621F6
0x140062200  mov     [rsp+88h+var_48], r15
0x140062205  test    rsi, rsi
0x140062208  jz      short loc_140062211
0x14006220a  mov     qword ptr [r9], 0
0x140062211  mov     eax, [rcx+30h]
0x140062214  bt      rax, 10h
0x140062219  jb      short loc_140062238
0x14006221b  test    rsi, rsi
0x14006221e  jz      loc_14006263F
0x140062224  lea     rcx, aNotAuthorized; "not authorized"
0x14006222b  call    sqlite3_mprintf
0x140062230  mov     [rsi], rax
0x140062233  jmp     loc_14006263F
0x140062238  test    r8, r8
0x14006223b  lea     rax, aSqlite3Extensi; "sqlite3_extension_init"
0x140062242  mov     r14, r8
0x140062245  cmovz   r14, rax
0x140062249  lea     rax, [r15-1]
0x14006224d  cmp     rax, 103h
0x140062253  ja      loc_1400625E8
0x140062259  mov     rax, [rdi+48h]
0x14006225d  mov     rcx, rdi
0x140062260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062265  mov     r13, rax
0x140062268  xor     eax, eax
0x14006226a  mov     dword ptr [rsp+88h+arg_0], eax
0x140062271  lea     rcx, __ImageBase
0x140062278  test    r13, r13
0x14006227b  jnz     loc_14006231D
0x140062281  mov     r8, ds:rva off_1400AA308[rcx+rax*8]; "dll" ...
0x140062289  mov     rdx, r12
0x14006228c  lea     rcx, aSS_4; "%s.%s"
0x140062293  mov     [rsp+88h+var_58], rax
0x140062298  call    sqlite3_mprintf
0x14006229d  mov     [rsp+88h+var_50], rax
0x1400622a2  mov     rdx, rax
0x1400622a5  test    rax, rax
0x1400622a8  jz      loc_14006238F
0x1400622ae  mov     rax, [rsp+88h+var_58]
0x1400622b3  lea     r8, __ImageBase
0x1400622ba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400622be  mov     r8, ds:rva off_1400AA308[r8+rax*8]; "dll" ...
0x1400622c6  inc     rcx
0x1400622c9  cmp     byte ptr [r8+rcx], 0
0x1400622ce  jnz     short loc_1400622C6
0x1400622d0  lea     rax, [r15+1]
0x1400622d4  add     rax, rcx
0x1400622d7  cmp     rax, 104h
0x1400622dd  ja      short loc_1400622F3
0x1400622df  mov     rax, [rdi+48h]
0x1400622e3  mov     rcx, rdi
0x1400622e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400622eb  mov     rdx, [rsp+88h+var_50]
0x1400622f0  mov     r13, rax
0x1400622f3  mov     rcx, rdx
0x1400622f6  call    sqlite3_free
0x1400622fb  mov     eax, dword ptr [rsp+88h+arg_0]
0x140062302  inc     eax
0x140062304  mov     dword ptr [rsp+88h+arg_0], eax
0x14006230b  cmp     eax, 1
0x14006230e  jl      loc_140062271
0x140062314  test    r13, r13
0x140062317  jz      loc_1400625E8
0x14006231d  mov     rax, [rdi+58h]
0x140062321  mov     r8, r14
0x140062324  mov     rdx, r13
0x140062327  mov     rcx, rdi
0x14006232a  xor     r15d, r15d
0x14006232d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062332  mov     [rsp+88h+arg_0], rax
0x14006233a  test    rax, rax
0x14006233d  jnz     loc_1400624FD
0x140062343  cmp     [rsp+88h+arg_10], r15
0x14006234b  jnz     loc_140062473
0x140062351  test    r12, r12
0x140062354  jnz     short loc_14006235B
0x140062356  xor     r14d, r14d
0x140062359  jmp     short loc_14006236F
0x14006235b  or      r14, 0FFFFFFFFFFFFFFFFh
0x14006235f  inc     r14
0x140062362  cmp     [r12+r14], r15b
0x140062366  jnz     short loc_14006235F
0x140062368  and     r14d, 3FFFFFFFh
0x14006236f  lea     ecx, [r14+1Eh]
0x140062373  call    sqlite3_malloc64
0x140062378  mov     r15, rax
0x14006237b  test    rax, rax
0x14006237e  jnz     short loc_140062399
0x140062380  mov     rax, [rdi+60h]
0x140062384  mov     rdx, r13
0x140062387  mov     rcx, rdi
0x14006238a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006238f  mov     eax, 7
0x140062394  jmp     loc_140062644
0x140062399  mov     rax, 5F336574696C7173h
0x1400623a3  mov     [r15], rax
0x1400623a6  jmp     short loc_1400623B6
0x1400623a8  cmp     byte ptr [r14+r12], 2Fh ; '/'
0x1400623ad  jz      short loc_1400623BC
0x1400623af  cmp     byte ptr [r14+r12], 5Ch ; '\'
0x1400623b4  jz      short loc_1400623BC
0x1400623b6  sub     r14d, 1
0x1400623ba  jns     short loc_1400623A8
0x1400623bc  lea     eax, [r14+1]
0x1400623c0  mov     r8d, 3
0x1400623c6  movsxd  rcx, eax
0x1400623c9  lea     rdx, aLib; "lib"
0x1400623d0  add     rcx, r12
0x1400623d3  call    sqlite3_strnicmp
0x1400623d8  neg     eax
0x1400623da  mov     r8d, 8
0x1400623e0  sbb     ecx, ecx
0x1400623e2  and     ecx, 0FFFFFFFDh
0x1400623e5  lea     edx, [rcx+4]
0x1400623e8  add     edx, r14d
0x1400623eb  movsxd  rax, edx
0x1400623ee  movsx   ecx, byte ptr [rax+r12]
0x1400623f3  test    ecx, ecx
0x1400623f5  jz      short loc_140062433
0x1400623f7  lea     r9, __ImageBase
0x1400623fe  cmp     ecx, 2Eh ; '.'
0x140062401  jz      short loc_140062433
0x140062403  movzx   eax, cl
0x140062406  test    byte ptr [rax+r9+0B2300h], 2
0x14006240f  jz      short loc_140062425
0x140062411  mov     eax, ecx
0x140062413  movsxd  rcx, r8d
0x140062416  inc     r8d
0x140062419  mov     al, [rax+r9+0B2890h]
0x140062421  mov     [rcx+r15], al
0x140062425  inc     edx
0x140062427  movsxd  rax, edx
0x14006242a  movsx   ecx, byte ptr [rax+r12]
0x14006242f  test    ecx, ecx
0x140062431  jnz     short loc_1400623FE
0x140062433  mov     eax, dword ptr cs:aInit; "_init"
0x140062439  mov     rdx, r13
0x14006243c  movsxd  rcx, r8d
0x14006243f  mov     r8, r15
0x140062442  mov     [rcx+r15], eax
0x140062446  movzx   eax, word ptr cs:aInit+4; "t"
0x14006244d  mov     [rcx+r15+4], ax
0x140062453  mov     rcx, rdi
0x140062456  mov     rax, [rdi+58h]
0x14006245a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006245f  mov     [rsp+88h+arg_0], rax
0x140062467  test    rax, rax
0x14006246a  jnz     loc_1400624FD
0x140062470  mov     r14, r15
0x140062473  test    rsi, rsi
0x140062476  jz      short loc_1400624E1
0x140062478  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14006247c  inc     rcx
0x14006247f  cmp     byte ptr [r14+rcx], 0
0x140062484  jnz     short loc_14006247C
0x140062486  mov     rbx, [rsp+88h+var_48]
0x14006248b  add     rbx, rcx
0x14006248e  lea     rcx, [rbx+12Ch]
0x140062495  call    sqlite3_malloc64
0x14006249a  mov     [rsp+88h+arg_18], rax
0x1400624a2  mov     [rsi], rax
0x1400624a5  test    rax, rax
0x1400624a8  jz      short loc_1400624E1
0x1400624aa  mov     r9, r14
0x1400624ad  mov     [rsp+88h+var_68], r12
0x1400624b2  lea     r8, aNoEntryPointSI; "no entry point [%s] in shared library ["...
0x1400624b9  mov     rdx, rax
0x1400624bc  lea     ecx, [rbx+12Ch]
0x1400624c2  call    sqlite3_snprintf
0x1400624c7  mov     r8, [rsp+88h+arg_18]
0x1400624cf  lea     edx, [rbx+12Bh]
0x1400624d5  mov     rax, [rdi+50h]
0x1400624d9  mov     rcx, rdi
0x1400624dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400624e1  mov     rax, [rdi+60h]
0x1400624e5  mov     rdx, r13
0x1400624e8  mov     rcx, rdi
0x1400624eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400624f0  mov     rcx, r15
0x1400624f3  call    sqlite3_free
0x1400624f8  jmp     loc_14006263F
0x1400624fd  mov     rcx, r15
0x140062500  call    sqlite3_free
0x140062505  mov     rax, [rsp+88h+arg_0]
0x14006250d  lea     r8, off_1400A9650
0x140062514  lea     rdx, [rsp+88h+arg_18]
0x14006251c  mov     rcx, rbx
0x14006251f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140062524  test    eax, eax
0x140062526  jz      short loc_140062573
0x140062528  cmp     eax, 100h
0x14006252d  jnz     short loc_140062536
0x14006252f  xor     eax, eax
0x140062531  jmp     loc_140062644
0x140062536  test    rsi, rsi
0x140062539  jz      short loc_140062552
0x14006253b  mov     rdx, [rsp+88h+arg_18]
0x140062543  lea     rcx, aErrorDuringIni; "error during initialization: %s"
0x14006254a  call    sqlite3_mprintf
0x14006254f  mov     [rsi], rax
0x140062552  mov     rcx, [rsp+88h+arg_18]
0x14006255a  call    sqlite3_free
0x14006255f  mov     rax, [rdi+60h]
0x140062563  mov     rdx, r13
0x140062566  mov     rcx, rdi
0x140062569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006256e  jmp     loc_14006263F
0x140062573  movsxd  rdx, dword ptr [rbx+0ECh]
0x14006257a  mov     rcx, rbx
0x14006257d  lea     rdx, ds:8[rdx*8]
0x140062585  call    sqlite3DbMallocZero
0x14006258a  mov     rdi, rax
0x14006258d  test    rax, rax
0x140062590  jz      loc_14006238F
0x140062596  movsxd  rax, dword ptr [rbx+0ECh]
0x14006259d  test    eax, eax
0x14006259f  jle     short loc_1400625B7
0x1400625a1  mov     rdx, [rbx+0F0h]; Src
0x1400625a8  mov     r8, rax
0x1400625ab  shl     r8, 3; Size
0x1400625af  mov     rcx, rdi; void *
0x1400625b2  call    memcpy_0
0x1400625b7  mov     rdx, [rbx+0F0h]
0x1400625be  test    rdx, rdx
0x1400625c1  jz      short loc_1400625CB
0x1400625c3  mov     rcx, rbx
0x1400625c6  call    sqlite3DbFreeNN
0x1400625cb  movsxd  rax, dword ptr [rbx+0ECh]
0x1400625d2  mov     [rbx+0F0h], rdi
0x1400625d9  mov     [rdi+rax*8], r13
0x1400625dd  inc     dword ptr [rbx+0ECh]
0x1400625e3  jmp     loc_14006252F
0x1400625e8  test    rsi, rsi
0x1400625eb  jz      short loc_14006263F
0x1400625ed  lea     rbx, [r15+12Ch]
0x1400625f4  mov     rcx, rbx
0x1400625f7  call    sqlite3_malloc64
0x1400625fc  mov     [rsp+88h+arg_18], rax
0x140062604  mov     [rsi], rax
0x140062607  test    rax, rax
0x14006260a  jz      short loc_14006263F
0x14006260c  mov     r9d, 104h
0x140062612  mov     [rsp+88h+var_68], r12
0x140062617  lea     r8, aUnableToOpenSh; "unable to open shared library [%.*s]"
0x14006261e  mov     rdx, rax
0x140062621  mov     ecx, ebx
0x140062623  call    sqlite3_snprintf
0x140062628  mov     r8, [rsp+88h+arg_18]
0x140062630  lea     edx, [rbx-1]
0x140062633  mov     rax, [rdi+50h]
0x140062637  mov     rcx, rdi
0x14006263a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006263f  mov     eax, 1
0x140062644  add     rsp, 50h
0x140062648  pop     r15
0x14006264a  pop     r14
0x14006264c  pop     r13
0x14006264e  pop     r12
0x140062650  pop     rdi
0x140062651  pop     rsi
0x140062652  pop     rbx
0x140062653  retn
```
