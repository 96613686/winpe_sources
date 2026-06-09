# LdrpSnapModule

- ea: `0x1800b6f08`
- end: `0x1800b74c4`
- name: `LdrpSnapModule`
- size: `1468`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025688`
- `0x18011ae8c`

## callees

- `0x18001eb80`
- `0x180025ec0`
- `0x180025efc`
- `0x180025f40`
- `0x180029010`
- `0x180029a60`
- `0x1800376a0`
- `0x18004f1dc`
- `0x18006cc40`
- `0x18006d8b0`
- `0x180082a00`
- `0x180083c30`
- `0x1800b6f08`
- `0x1800b74cc`
- `0x1800b7570`
- `0x1800b7654`
- `0x1800d9fa0`
- `0x18015b7c8`
- `0x18015f020`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x1800b7399`: `Import '%s' of DLL '%wZ' is redirected to 0x%p`
- `0x1800b7337`: `DLL "%wZ" does not contain an export table\n`

## pseudocode

```c
__int64 __fastcall LdrpSnapModule(__int64 a1)
{
  __int64 v2; // r13
  __int64 v3; // r12
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 *v10; // r14
  __int64 v11; // r12
  _DWORD *v12; // rdx
  __int64 v13; // rcx
  char *v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int *v17; // r14
  int v18; // ebx
  __int64 v19; // r12
  unsigned __int64 v20; // r14
  int v21; // ecx
  int v22; // eax
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // eax
  __int64 v29; // r14
  __int64 v30; // rax
  int v31; // [rsp+44h] [rbp-114h]
  unsigned int v32; // [rsp+48h] [rbp-110h] BYREF
  unsigned int v33; // [rsp+4Ch] [rbp-10Ch]
  __int64 *v34; // [rsp+50h] [rbp-108h]
  char ArgList[8]; // [rsp+58h] [rbp-100h]
  int v36; // [rsp+60h] [rbp-F8h]
  unsigned int *v37; // [rsp+68h] [rbp-F0h]
  _DWORD *v38; // [rsp+70h] [rbp-E8h]
  __int64 v39; // [rsp+78h] [rbp-E0h]
  unsigned __int64 v40; // [rsp+80h] [rbp-D8h]
  char *v41; // [rsp+88h] [rbp-D0h]
  __int64 v42; // [rsp+90h] [rbp-C8h]
  __int64 v43; // [rsp+98h] [rbp-C0h]
  __int64 v44; // [rsp+A0h] [rbp-B8h]
  __int64 v45; // [rsp+A8h] [rbp-B0h]
  __int64 v46; // [rsp+B0h] [rbp-A8h]
  __int64 v47; // [rsp+B8h] [rbp-A0h]
  __int64 v48; // [rsp+C0h] [rbp-98h]
  __int64 v49; // [rsp+C8h] [rbp-90h]
  _QWORD v50[8]; // [rsp+D0h] [rbp-88h] BYREF

  v48 = a1;
  v32 = 0;
  v40 = 0;
  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(v2 + 48);
  v49 = v3;
  v47 = v2 + 72;
  LdrpLogDllState(v3, v2 + 72, 5286);
  LdrpHandlePendingModuleReplaced(a1);
  memset_thunk_772440563353939046(v50, 0, 0x40u);
  v31 = 0;
  v33 = 0;
  while ( 1 )
  {
    v4 = *(unsigned int *)(a1 + 128);
    if ( (unsigned int)v4 >= *(_DWORD *)(a1 + 104) )
    {
      v18 = LdrpDoPostSnapWork(a1);
      if ( v18 >= 0 )
      {
        LdrpLogDllState(*(_QWORD *)(v2 + 48), v2 + 72, 5287);
        *(_DWORD *)(*(_QWORD *)(v2 + 152) + 56LL) = 5;
      }
      goto LABEL_36;
    }
    _mm_lfence();
    v5 = (unsigned int)v4;
    v6 = LdrpHandleReplacedModule(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v4));
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v5) != v6 )
    {
      LdrpFreeReplacedModule();
      *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v5) = v6;
    }
    v7 = *(_QWORD *)(a1 + 136);
    v8 = *(unsigned int *)(v7 + 20 * v5);
    v9 = (__int64 *)(v3 + *(unsigned int *)(v7 + 20 * v5 + 16));
    v34 = v9;
    if ( !(_DWORD)v8 || (v10 = (__int64 *)(v3 + v8), (unsigned int)v8 > *(_DWORD *)(v2 + 64)) )
      v10 = v9;
    if ( v6 )
      break;
LABEL_27:
    ++*(_DWORD *)(a1 + 128);
  }
  v11 = *(_QWORD *)(v6 + 48);
  v39 = v11;
  LOBYTE(v8) = 1;
  v12 = (_DWORD *)RtlImageDirectoryEntryToData(v11, v8, 0, &v32);
  v38 = v12;
  if ( v12 )
  {
    v13 = 0;
    do
    {
      if ( !v50[v13] )
        break;
      if ( v11 == v50[v13] )
        break;
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < 8 );
    if ( (_DWORD)v13 == 8 || !v50[v13] )
    {
      RtlGuardCheckImageBase(v11, 0);
      v50[v31] = v11;
      v31 = ((_BYTE)v31 + 1) & 7;
      v12 = v38;
    }
    v14 = (char *)v12 + v32;
    v41 = v14;
    v15 = v11 + (unsigned int)v12[7];
    v42 = v15;
    v36 = v12[6];
    v46 = v11 + (unsigned int)v12[8];
    v45 = v11 + (unsigned int)v12[9];
    v16 = *(unsigned int *)(a1 + 132);
    v17 = (unsigned int *)&v10[v16];
    v34 = (__int64 *)((char *)v34 + v16 * 8);
    while ( 1 )
    {
      v37 = v17;
      if ( !*(_QWORD *)v17 )
      {
        *(_DWORD *)(a1 + 132) = 0;
        v3 = v49;
        goto LABEL_27;
      }
      v18 = -1073741702;
      v19 = *(_QWORD *)v17 >> 63;
      v20 = -4530927;
      v21 = *v37;
      if ( (_BYTE)v19 )
        break;
      v25 = *v37;
      v43 = v25;
      v44 = *(_QWORD *)(v2 + 48);
      v26 = v44 + v25 + 2;
      *(_QWORD *)ArgList = v26;
      if ( (*(_DWORD *)(a1 + 32) & 0x2000000) != 0 )
      {
        v20 = LdrpCheckRedirection(v2, v6, v26);
        if ( v20 != -4530927 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrsnap.c",
            3511,
            (int)"LdrpSnapModule",
            2,
            "Import '%s' of DLL '%wZ' is redirected to 0x%p",
            ArgList[0]);
          goto LABEL_22;
        }
        LOBYTE(v26) = ArgList[0];
      }
      v22 = LdrpNameToOrdinal(v26, v46, v45);
      if ( v22 >= 0 )
      {
        v12 = v38;
        v14 = v41;
        v15 = v42;
        goto LABEL_19;
      }
LABEL_21:
      if ( v18 < 0 )
      {
        if ( v18 == -1073741702 || v18 == -1073741515 )
        {
          if ( (unsigned int)CompatCachepLookupCdb(*(wchar_t **)(v2 + 80))
            || (unsigned int)CompatCachepLookupCdb(*(wchar_t **)(v6 + 80)) )
          {
            v29 = v2 + 72;
            LdrpLogLoadFailureEtwEvent(v2 + 72, v6 + 72, 1, (unsigned int)LoadFailure, 0);
            LdrpLogLoadFailureEtwEvent(v2 + 72, v6 + 72, 1, (unsigned int)LoadFailureOperational, 1);
          }
          else
          {
            v29 = v47;
          }
          if ( (_BYTE)v19 )
          {
            v18 = -1073741512;
            v30 = v33;
          }
          else
          {
            v18 = -1073741511;
            v30 = *(_QWORD *)ArgList;
          }
          LdrpReportError(v29, v30, ((unsigned __int8)v19 ^ 1u) - 1073741512);
        }
        goto LABEL_36;
      }
LABEL_22:
      v23 = RtlpHpRedirectHeapExport(v20);
      v24 = v34;
      *v34 = v23;
      v17 = v37 + 2;
      v34 = v24 + 1;
      ++*(_DWORD *)(a1 + 132);
      v12 = v38;
      v14 = v41;
      v15 = v42;
    }
    *(_QWORD *)ArgList = 0;
    v33 = (unsigned __int16)v21;
    v22 = (unsigned __int16)v21 - v12[4];
LABEL_19:
    if ( (unsigned int)v22 < v12[5] )
    {
      if ( *(_DWORD *)(v15 + 4LL * v22) )
      {
        v20 = v39 + *(unsigned int *)(v15 + 4LL * v22);
        v18 = 0;
        if ( v20 < (unsigned __int64)v14 && v20 > (unsigned __int64)v12 )
        {
          v27 = LdrpResolveForwarder((char *)v20);
          v18 = v27;
          if ( v27 == 259 )
            return 0;
          if ( v27 >= 0 )
            v20 = v40;
        }
      }
    }
    goto LABEL_21;
  }
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrsnap.c",
    3413,
    (int)"LdrpSnapModule",
    0,
    "DLL \"%wZ\" does not contain an export table\n",
    v6 + 72);
  v18 = -1073741701;
LABEL_36:
  if ( *(_QWORD *)(a1 + 192) )
  {
    NtUnmapViewOfSection(-1);
    *(_QWORD *)(a1 + 192) = 0;
  }
  if ( v18 < 0 )
    LdrpLogError((unsigned int)v18, 25, 0, a1);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800b6f08  push    rbx
0x1800b6f0a  push    rsi
0x1800b6f0b  push    r12
0x1800b6f0d  push    r13
0x1800b6f0f  push    r14
0x1800b6f11  push    r15
0x1800b6f13  sub     rsp, 128h
0x1800b6f1a  mov     rax, cs:__security_cookie
0x1800b6f21  xor     rax, rsp
0x1800b6f24  mov     [rsp+158h+var_48], rax
0x1800b6f2c  mov     rsi, rcx
0x1800b6f2f  mov     [rsp+158h+var_98], rcx
0x1800b6f37  mov     [rsp+158h+var_110], 0
0x1800b6f3f  mov     [rsp+158h+var_D8], 0
0x1800b6f4b  mov     r13, [rcx+38h]
0x1800b6f4f  mov     r12, [r13+30h]
0x1800b6f53  mov     [rsp+158h+var_90], r12
0x1800b6f5b  lea     r14, [r13+48h]
0x1800b6f5f  mov     [rsp+158h+var_A0], r14
0x1800b6f67  mov     r8d, 14A6h
0x1800b6f6d  mov     rdx, r14
0x1800b6f70  mov     rcx, r12
0x1800b6f73  call    LdrpLogDllState
0x1800b6f78  mov     rcx, rsi
0x1800b6f7b  call    LdrpHandlePendingModuleReplaced
0x1800b6f80  xor     edx, edx; Val
0x1800b6f82  lea     r8d, [rdx+40h]; Size
0x1800b6f86  lea     rcx, [rsp+158h+var_88]; void *
0x1800b6f8e  call    memset$thunk$772440563353939046
0x1800b6f93  mov     [rsp+158h+var_114], 0
0x1800b6f9b  xor     ebx, ebx
0x1800b6f9d  xor     eax, eax
0x1800b6f9f  mov     [rsp+158h+var_10C], eax
0x1800b6fa3  mov     eax, [rsi+80h]
0x1800b6fa9  cmp     eax, [rsi+68h]
0x1800b6fac  jnb     loc_1800B726D
0x1800b6fb2  lfence
0x1800b6fb5  mov     r14d, eax
0x1800b6fb8  mov     rcx, [rsi+58h]
0x1800b6fbc  mov     rcx, [rcx+rax*8]
0x1800b6fc0  call    LdrpHandleReplacedModule
0x1800b6fc5  mov     r15, rax
0x1800b6fc8  mov     rax, [rsi+58h]
0x1800b6fcc  mov     rcx, [rax+r14*8]
0x1800b6fd0  cmp     rcx, r15
0x1800b6fd3  jnz     loc_1800B7314
0x1800b6fd9  lea     rcx, [r14+r14*4]
0x1800b6fdd  mov     rax, [rsi+88h]
0x1800b6fe4  mov     edx, [rax+rcx*4]
0x1800b6fe7  mov     eax, [rax+rcx*4+10h]
0x1800b6feb  add     rax, r12
0x1800b6fee  mov     [rsp+158h+var_108], rax
0x1800b6ff3  test    edx, edx
0x1800b6ff5  jz      loc_1800B7326
0x1800b6ffb  cmp     edx, [r13+40h]
0x1800b6fff  lea     r14, [r12+rdx]
0x1800b7003  ja      loc_1800B7326
0x1800b7009  test    r15, r15
0x1800b700c  jz      loc_1800B720A
0x1800b7012  mov     r12, [r15+30h]
0x1800b7016  mov     [rsp+158h+var_E0], r12
0x1800b701b  xor     r8d, r8d
0x1800b701e  lea     r9, [rsp+158h+var_110]
0x1800b7023  mov     dl, 1
0x1800b7025  mov     rcx, r12
0x1800b7028  call    RtlImageDirectoryEntryToData
0x1800b702d  mov     rdx, rax
0x1800b7030  mov     [rsp+158h+var_E8], rax
0x1800b7035  test    rax, rax
0x1800b7038  jz      loc_1800B732E
0x1800b703e  xor     ecx, ecx
0x1800b7040  cmp     [rsp+rcx*8+158h+var_88], 0
0x1800b7049  jz      short loc_1800B705C
0x1800b704b  cmp     r12, [rsp+rcx*8+158h+var_88]
0x1800b7053  jz      short loc_1800B705C
0x1800b7055  inc     ecx
0x1800b7057  cmp     ecx, 8
0x1800b705a  jb      short loc_1800B7040
0x1800b705c  cmp     ecx, 8
0x1800b705f  jz      loc_1800B72EB
0x1800b7065  cmp     [rsp+rcx*8+158h+var_88], 0
0x1800b706e  jz      loc_1800B72EB
0x1800b7074  mov     r8d, [rsp+158h+var_110]
0x1800b7079  add     r8, rdx
0x1800b707c  mov     [rsp+158h+var_D0], r8
0x1800b7084  mov     r9d, [rdx+1Ch]
0x1800b7088  add     r9, r12
0x1800b708b  mov     [rsp+158h+var_C8], r9
0x1800b7093  mov     eax, [rdx+18h]
0x1800b7096  mov     [rsp+158h+var_F8], eax
0x1800b709a  mov     eax, [rdx+20h]
0x1800b709d  add     rax, r12
0x1800b70a0  mov     [rsp+158h+var_A8], rax
0x1800b70a8  mov     eax, [rdx+24h]
0x1800b70ab  add     rax, r12
0x1800b70ae  mov     [rsp+158h+var_B0], rax
0x1800b70b6  mov     eax, [rsi+84h]
0x1800b70bc  shl     rax, 3
0x1800b70c0  add     r14, rax
0x1800b70c3  add     [rsp+158h+var_108], rax
0x1800b70c8  mov     [rsp+158h+var_F0], r14
0x1800b70cd  mov     r12, [r14]
0x1800b70d0  test    r12, r12
0x1800b70d3  jz      loc_1800B71F8
0x1800b70d9  mov     ebx, 0C000007Ah
0x1800b70de  mov     [rsp+158h+var_118], ebx
0x1800b70e2  shr     r12, 3Fh
0x1800b70e6  mov     r14, 0FFFFFFFFFFBADD11h
0x1800b70ed  mov     rax, [rsp+158h+var_F0]
0x1800b70f2  mov     ecx, [rax]
0x1800b70f4  test    r12b, r12b
0x1800b70f7  jz      short loc_1800B7166
0x1800b70f9  xor     eax, eax
0x1800b70fb  mov     qword ptr [rsp+158h+var_100], rax
0x1800b7100  movzx   eax, cx
0x1800b7103  mov     [rsp+158h+var_10C], eax
0x1800b7107  sub     eax, [rdx+10h]
0x1800b710a  cmp     eax, [rdx+14h]
0x1800b710d  jnb     short loc_1800B711C
0x1800b710f  cdqe
0x1800b7111  cmp     dword ptr [r9+rax*4], 0
0x1800b7116  jnz     loc_1800B7215
0x1800b711c  test    ebx, ebx
0x1800b711e  js      loc_1800B73DB
0x1800b7124  mov     rcx, r14
0x1800b7127  call    RtlpHpRedirectHeapExport
0x1800b712c  mov     rcx, [rsp+158h+var_108]
0x1800b7131  mov     [rcx], rax
0x1800b7134  mov     r14, [rsp+158h+var_F0]
0x1800b7139  add     r14, 8
0x1800b713d  add     rcx, 8
0x1800b7141  mov     [rsp+158h+var_108], rcx
0x1800b7146  inc     dword ptr [rsi+84h]
0x1800b714c  mov     rdx, [rsp+158h+var_E8]
0x1800b7151  mov     r8, [rsp+158h+var_D0]
0x1800b7159  mov     r9, [rsp+158h+var_C8]
0x1800b7161  jmp     loc_1800B70C8
0x1800b7166  mov     rax, rcx
0x1800b7169  mov     [rsp+158h+var_C0], rcx
0x1800b7171  mov     rcx, [r13+30h]
0x1800b7175  mov     [rsp+158h+var_B8], rcx
0x1800b717d  add     rax, 2
0x1800b7181  add     rax, rcx
0x1800b7184  mov     qword ptr [rsp+158h+var_100], rax
0x1800b7189  test    dword ptr [rsi+20h], 2000000h
0x1800b7190  jnz     loc_1800B7368
0x1800b7196  mov     rcx, [rsp+158h+var_C0]
0x1800b719e  mov     rdx, [rsp+158h+var_B8]
0x1800b71a6  movzx   edx, word ptr [rcx+rdx]
0x1800b71aa  mov     rcx, [rsp+158h+var_B0]
0x1800b71b2  mov     qword ptr [rsp+158h+ArgList], rcx; __int64
0x1800b71b7  mov     rcx, [rsp+158h+var_A8]
0x1800b71bf  mov     [rsp+158h+Format], rcx; __int64
0x1800b71c4  mov     r9d, [rsp+158h+var_F8]
0x1800b71c9  mov     r8, [rsp+158h+var_E0]
0x1800b71ce  mov     rcx, rax; ArgList
0x1800b71d1  call    LdrpNameToOrdinal
0x1800b71d6  test    eax, eax
0x1800b71d8  js      loc_1800B711C
0x1800b71de  mov     rdx, [rsp+158h+var_E8]
0x1800b71e3  mov     r8, [rsp+158h+var_D0]
0x1800b71eb  mov     r9, [rsp+158h+var_C8]
0x1800b71f3  jmp     loc_1800B710A
0x1800b71f8  mov     dword ptr [rsi+84h], 0
0x1800b7202  mov     r12, [rsp+158h+var_90]
0x1800b720a  inc     dword ptr [rsi+80h]
0x1800b7210  jmp     loc_1800B6FA3
0x1800b7215  mov     r14d, [r9+rax*4]
0x1800b7219  add     r14, [rsp+158h+var_E0]
0x1800b721e  xor     ebx, ebx
0x1800b7220  mov     [rsp+158h+var_118], ebx
0x1800b7224  cmp     r14, r8
0x1800b7227  jnb     loc_1800B711C
0x1800b722d  cmp     r14, rdx
0x1800b7230  jbe     loc_1800B711C
0x1800b7236  lea     r9, [rsp+158h+var_D8]
0x1800b723e  mov     r8, r13
0x1800b7241  mov     rdx, r15
0x1800b7244  mov     rcx, r14; Str
0x1800b7247  call    LdrpResolveForwarder
0x1800b724c  mov     ebx, eax
0x1800b724e  mov     [rsp+158h+var_118], eax
0x1800b7252  cmp     eax, 103h
0x1800b7257  jz      loc_1800B73D4
0x1800b725d  test    eax, eax
0x1800b725f  cmovns  r14, [rsp+158h+var_D8]
0x1800b7268  jmp     loc_1800B711C
0x1800b726d  test    ebx, ebx
0x1800b726f  js      short loc_1800B72A0
0x1800b7271  mov     rcx, rsi
0x1800b7274  call    LdrpDoPostSnapWork
0x1800b7279  mov     ebx, eax
0x1800b727b  test    eax, eax
0x1800b727d  js      short loc_1800B72A0
0x1800b727f  mov     r8d, 14A7h
0x1800b7285  lea     rdx, [r13+48h]
0x1800b7289  mov     rcx, [r13+30h]
0x1800b728d  call    LdrpLogDllState
0x1800b7292  mov     rax, [r13+98h]
0x1800b7299  mov     dword ptr [rax+38h], 5
0x1800b72a0  mov     rdx, [rsi+0C0h]
0x1800b72a7  test    rdx, rdx
0x1800b72aa  jnz     loc_1800B74AB
0x1800b72b0  test    ebx, ebx
0x1800b72b2  jns     short loc_1800B72C6
0x1800b72b4  mov     edx, 19h
0x1800b72b9  mov     r9, rsi
0x1800b72bc  xor     r8d, r8d
0x1800b72bf  mov     ecx, ebx
0x1800b72c1  call    LdrpLogError
0x1800b72c6  mov     eax, ebx
0x1800b72c8  mov     rcx, [rsp+158h+var_48]
0x1800b72d0  xor     rcx, rsp; StackCookie
0x1800b72d3  call    __security_check_cookie
0x1800b72d8  add     rsp, 128h
0x1800b72df  pop     r15
0x1800b72e1  pop     r14
0x1800b72e3  pop     r13
0x1800b72e5  pop     r12
0x1800b72e7  pop     rsi
0x1800b72e8  pop     rbx
0x1800b72e9  retn
0x1800b72eb  xor     edx, edx
0x1800b72ed  mov     rcx, r12
0x1800b72f0  call    RtlGuardCheckImageBase
0x1800b72f5  mov     ecx, [rsp+158h+var_114]
0x1800b72f9  mov     [rsp+rcx*8+158h+var_88], r12
0x1800b7301  inc     ecx
0x1800b7303  and     ecx, 7
0x1800b7306  mov     [rsp+158h+var_114], ecx
0x1800b730a  mov     rdx, [rsp+158h+var_E8]
0x1800b730f  jmp     loc_1800B7074
0x1800b7314  call    LdrpFreeReplacedModule
0x1800b7319  mov     rax, [rsi+58h]
0x1800b731d  mov     [rax+r14*8], r15
0x1800b7321  jmp     loc_1800B6FD9
0x1800b7326  mov     r14, rax
0x1800b7329  jmp     loc_1800B7009
0x1800b732e  lea     rax, [r15+48h]
0x1800b7332  mov     qword ptr [rsp+158h+ArgList], rax; ArgList
0x1800b7337  lea     rax, aDllWzDoesNotCo; "DLL \"%wZ\" does not contain an export "...
0x1800b733e  mov     [rsp+158h+Format], rax; Format
0x1800b7343  xor     r9d, r9d; int
0x1800b7346  lea     r8, aLdrpsnapmodule; "LdrpSnapModule"
0x1800b734d  mov     edx, 0D55h; int
0x1800b7352  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800b7359  call    LdrpLogInternal
0x1800b735e  mov     ebx, 0C000007Bh
0x1800b7363  jmp     loc_1800B72A0
0x1800b7368  mov     r8, rax
0x1800b736b  mov     rdx, r15
0x1800b736e  mov     rcx, r13
0x1800b7371  call    LdrpCheckRedirection
0x1800b7376  mov     r14, rax
0x1800b7379  cmp     rax, 0FFFFFFFFFFBADD11h
0x1800b737f  jz      short loc_1800B73CA
0x1800b7381  mov     [rsp+158h+var_120], rax
0x1800b7386  lea     rax, [r13+48h]
0x1800b738a  mov     [rsp+158h+var_128], rax
0x1800b738f  mov     rax, qword ptr [rsp+158h+var_100]
0x1800b7394  mov     qword ptr [rsp+158h+ArgList], rax; ArgList
0x1800b7399  lea     rax, aImportSOfDllWz; "Import '%s' of DLL '%wZ' is redirected "...
0x1800b73a0  mov     [rsp+158h+Format], rax; Format
0x1800b73a5  mov     r9d, 2; int
0x1800b73ab  lea     r8, aLdrpsnapmodule; "LdrpSnapModule"
0x1800b73b2  mov     edx, 0DB7h; int
0x1800b73b7  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800b73be  call    LdrpLogInternal
0x1800b73c3  xor     ebx, ebx
0x1800b73c5  jmp     loc_1800B7124
0x1800b73ca  mov     rax, qword ptr [rsp+158h+var_100]
0x1800b73cf  jmp     loc_1800B7196
0x1800b73d4  xor     eax, eax
0x1800b73d6  jmp     loc_1800B72C8
0x1800b73db  cmp     ebx, 0C000007Ah
0x1800b73e1  jz      short loc_1800B73EF
0x1800b73e3  cmp     ebx, 0C0000135h
0x1800b73e9  jnz     loc_1800B72A0
0x1800b73ef  mov     ebx, 80h
0x1800b73f4  mov     edx, ebx
0x1800b73f6  mov     rcx, [r13+50h]; Str
0x1800b73fa  call    CompatCachepLookupCdb
0x1800b73ff  test    eax, eax
0x1800b7401  jnz     short loc_1800B741C
0x1800b7403  mov     edx, ebx
0x1800b7405  mov     rcx, [r15+50h]; Str
0x1800b7409  call    CompatCachepLookupCdb
0x1800b740e  test    eax, eax
0x1800b7410  jnz     short loc_1800B741C
0x1800b7412  mov     r14, [rsp+158h+var_A0]
0x1800b741a  jmp     short loc_1800B745D
0x1800b741c  mov     byte ptr [rsp+158h+Format], 0
0x1800b7421  lea     r9, LoadFailure
0x1800b7428  mov     r8d, 1
0x1800b742e  lea     rdx, [r15+48h]
0x1800b7432  lea     r14, [r13+48h]
0x1800b7436  mov     rcx, r14
0x1800b7439  call    LdrpLogLoadFailureEtwEvent
0x1800b743e  mov     byte ptr [rsp+158h+Format], 1
0x1800b7443  lea     r9, LoadFailureOperational
  ... truncated ...
```
