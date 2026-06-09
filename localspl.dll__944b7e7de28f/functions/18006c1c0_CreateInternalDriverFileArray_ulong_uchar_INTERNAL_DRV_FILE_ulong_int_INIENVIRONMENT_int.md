# CreateInternalDriverFileArray(ulong,uchar *,_INTERNAL_DRV_FILE * *,ulong *,int,_INIENVIRONMENT *,int)

- ea: `0x18006c1c0`
- end: `0x18006c869`
- name: `?CreateInternalDriverFileArray@@YAHKPEAEPEAPEAU_INTERNAL_DRV_FILE@@PEAKHPEAU_INIENVIRONMENT@@H@Z`
- size: `1705`
- prototype: `__int64 __fastcall(int, unsigned __int8 *, struct _INTERNAL_DRV_FILE **, unsigned int *, int, struct _INIENVIRONMENT *, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x180028360`
- `0x180069484`
- `0x1800705a0`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000c5fc`
- `0x18000c71c`
- `0x18000d540`
- `0x18002dc20`
- `0x180041028`
- `0x180054638`
- `0x18006c1c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c284`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c707`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c2cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c7fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c82f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c2cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c318`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c7fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c82f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c6ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006c6ee`
- `SPOOLSS!DllFreeSplMem` at `0x18006c81f`
- `SPOOLSS!DllFreeSplMem` at `0x18006c81f`
- `SPOOLSS!DllAllocSplMem` at `0x18006c387`
- `SPOOLSS!DllAllocSplMem` at `0x18006c387`
- `SPOOLSS!AllocSplStr` at `0x18006c461`
- `SPOOLSS!AllocSplStr` at `0x18006c4ed`
- `SPOOLSS!AllocSplStr` at `0x18006c4fd`
- `SPOOLSS!AllocSplStr` at `0x18006c50e`
- `SPOOLSS!AllocSplStr` at `0x18006c52d`
- `SPOOLSS!AllocSplStr` at `0x18006c580`
- `SPOOLSS!AllocSplStr` at `0x18006c5fe`
- `SPOOLSS!AllocSplStr` at `0x18006c60e`
- `SPOOLSS!AllocSplStr` at `0x18006c61f`
- `SPOOLSS!AllocSplStr` at `0x18006c461`
- `SPOOLSS!AllocSplStr` at `0x18006c4ed`
- `SPOOLSS!AllocSplStr` at `0x18006c4fd`
- `SPOOLSS!AllocSplStr` at `0x18006c50e`
- `SPOOLSS!AllocSplStr` at `0x18006c52d`
- `SPOOLSS!AllocSplStr` at `0x18006c580`
- `SPOOLSS!AllocSplStr` at `0x18006c5fe`
- `SPOOLSS!AllocSplStr` at `0x18006c60e`
- `SPOOLSS!AllocSplStr` at `0x18006c61f`
- `SPOOLSS!MakePTR` at `0x18006c43d`
- `SPOOLSS!MakePTR` at `0x18006c43d`

## string_xrefs

- `0x18006c66d`: `CreateInternalDriverFileArray`
- `0x18006c71e`: `CreateInternalDriverFileArray`
- `0x18006c717`: `Failed to open file %ws, error %d`

## pseudocode

```c
__int64 __fastcall CreateInternalDriverFileArray(
        int a1,
        unsigned __int8 *a2,
        struct _INTERNAL_DRV_FILE **a3,
        unsigned int *a4,
        int a5,
        struct _INIENVIRONMENT *a6,
        int a7)
{
  unsigned int v10; // ebx
  unsigned __int16 *v11; // r14
  int v12; // r15d
  unsigned __int8 *v13; // r13
  unsigned int v14; // ecx
  struct _INIENVIRONMENT *v15; // r15
  int v16; // eax
  unsigned __int16 *v17; // rax
  _WORD *v18; // rdx
  unsigned __int64 v19; // rcx
  int v20; // edx
  bool v21; // zf
  unsigned __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  struct _INTERNAL_DRV_FILE *v24; // rax
  __int64 v25; // r8
  unsigned int i; // edx
  __int64 v27; // rcx
  unsigned int j; // r14d
  unsigned __int16 *PTR; // rcx
  unsigned __int16 *FileNameInScratchDir; // rax
  unsigned __int16 *v31; // rcx
  unsigned __int16 *v32; // rcx
  unsigned __int16 *v33; // rax
  _WORD *v34; // rcx
  unsigned int v35; // eax
  __int64 v36; // r13
  unsigned __int16 *v37; // rax
  __int64 v38; // rax
  unsigned __int8 *v39; // r15
  unsigned __int16 *v40; // rcx
  struct _INIENVIRONMENT *v41; // r14
  unsigned int v42; // edx
  __int64 v43; // rcx
  __int64 v44; // rcx
  unsigned int v45; // r8d
  unsigned int k; // r14d
  unsigned int v47; // r13d
  _QWORD *v48; // r15
  __int64 v49; // r13
  DWORD LastError; // eax
  unsigned int m; // r14d
  __int64 v52; // r12
  int v54; // [rsp+48h] [rbp-80h]
  int v55; // [rsp+54h] [rbp-74h]
  unsigned __int8 *v56; // [rsp+58h] [rbp-70h]
  unsigned __int16 *v57; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int8 *v58; // [rsp+68h] [rbp-60h]
  unsigned __int8 *v59; // [rsp+70h] [rbp-58h]
  unsigned __int16 *v60; // [rsp+78h] [rbp-50h]
  int v61; // [rsp+80h] [rbp-48h]

  v10 = 1;
  v55 = 1;
  v11 = 0;
  v57 = 0;
  if ( !a3 || !a4 )
  {
LABEL_97:
    v10 = 0;
    SetLastError(0xDu);
    goto LABEL_98;
  }
  v54 = 0;
  v12 = 0;
  v59 = 0;
  v13 = 0;
  v56 = 0;
  v58 = 0;
  v60 = 0;
  *a4 = 0;
  *a3 = 0;
  if ( a1 == 2 )
  {
    *a4 = 3;
    v59 = a2;
    v14 = 3;
    goto LABEL_30;
  }
  if ( a1 != 3 && a1 != 4 && a1 != 6 && a1 != 8 )
  {
    if ( a1 == 101 )
    {
      v58 = a2;
      v14 = *((_DWORD *)a2 + 8);
      *a4 = v14;
      goto LABEL_30;
    }
    goto LABEL_97;
  }
  *a4 = 3;
  v15 = a6;
  v16 = _o__wcsicmp(*((_QWORD *)a6 + 3), L"Windows 4.0");
  v11 = (unsigned __int16 *)*((_QWORD *)a2 + 7);
  if ( v16 )
  {
    if ( !(unsigned int)BuildTrueDependentFileField(
                          *((_QWORD *)a2 + 3),
                          *((_QWORD *)a2 + 4),
                          *((_QWORD *)a2 + 5),
                          *((_QWORD *)a2 + 6),
                          (__int64)v11,
                          (__int64)&v57) )
    {
      v10 = 0;
      SetLastError(0xDu);
      goto LABEL_99;
    }
    v11 = v57;
    v60 = v57;
  }
  v17 = v11;
  v12 = 3;
  v18 = (_WORD *)*((_QWORD *)a2 + 6);
  if ( !v18 || !*v18 )
  {
LABEL_21:
    v20 = 0;
    v21 = v11 == 0;
    while ( 1 )
    {
      v54 = v20;
      if ( v21 || !*v17 )
        break;
      v22 = -1;
      do
        ++v22;
      while ( v17[v22] );
      if ( v22 >= 0x104 )
        goto LABEL_19;
      ++v20;
      v23 = &v17[v22];
      v21 = v23 + 1 == 0;
      v17 = v23 + 1;
    }
    v13 = a2;
    v56 = a2;
    *a4 += v20;
    v14 = *a4;
LABEL_30:
    v24 = (struct _INTERNAL_DRV_FILE *)DllAllocSplMem(32 * v14);
    *a3 = v24;
    v25 = 0;
    if ( !v24 )
    {
LABEL_91:
      v10 = 0;
      goto LABEL_94;
    }
    for ( i = 0; i < *a4; ++i )
    {
      v27 = 32LL * i;
      *(_QWORD *)((char *)*a3 + v27) = 0;
      *(_QWORD *)((char *)*a3 + v27 + 16) = -1;
      *(_DWORD *)((char *)*a3 + v27 + 8) = 0;
      *(_DWORD *)((char *)*a3 + v27 + 24) = 0;
    }
    if ( a1 == 2 )
    {
      v39 = v59;
      v40 = (unsigned __int16 *)*((_QWORD *)v59 + 3);
      if ( a5 )
      {
        v41 = a6;
        *(_QWORD *)*a3 = GetFileNameInScratchDir(v40, a6);
        *((_QWORD *)*a3 + 4) = GetFileNameInScratchDir(*((unsigned __int16 **)v39 + 5), a6);
        *((_QWORD *)*a3 + 8) = GetFileNameInScratchDir(*((unsigned __int16 **)v39 + 4), a6);
      }
      else
      {
        *(_QWORD *)*a3 = AllocSplStr(v40);
        *((_QWORD *)*a3 + 4) = AllocSplStr(*((_QWORD *)v39 + 5));
        *((_QWORD *)*a3 + 8) = AllocSplStr(*((_QWORD *)v39 + 4));
        v41 = a6;
      }
      goto LABEL_68;
    }
    if ( a1 != 3 && a1 != 4 && a1 != 5 && a1 != 6 && a1 != 8 )
    {
      if ( a1 == 101 )
      {
        for ( j = 0; j < *a4; ++j )
        {
          PTR = (unsigned __int16 *)MakePTR(v58, *(unsigned int *)(*((_QWORD *)v58 + 3) + 12LL * j), v25);
          if ( a5 )
            FileNameInScratchDir = GetFileNameInScratchDir(PTR, a6);
          else
            FileNameInScratchDir = (unsigned __int16 *)AllocSplStr(PTR);
          *((_QWORD *)*a3 + 4 * j) = FileNameInScratchDir;
        }
        v41 = a6;
LABEL_68:
        v42 = 0;
        while ( v42 < *a4 )
        {
          v43 = 32LL * v42++;
          if ( !*(_QWORD *)((char *)*a3 + v43) )
          {
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "CreateInternalDriverFileArray",
              L"Failed to allocate memory for driver file array",
              0);
            goto LABEL_91;
          }
        }
        if ( a7 )
          goto LABEL_94;
        SafeIncrementReference((unsigned int *)v41 + 4);
        LeaveSplSem(v44);
        v45 = 0;
        v55 = 0;
        v61 = 0;
        for ( k = 0; ; ++k )
        {
          v47 = *a4;
          v48 = *a3;
          if ( k >= *a4 )
            break;
          v49 = 32LL * k;
          *(_QWORD *)((char *)*a3 + v49 + 16) = CreateFileW(
                                                  (LPCWSTR)v48[(unsigned __int64)v49 / 8],
                                                  0x80000000,
                                                  1u,
                                                  0,
                                                  3u,
                                                  0x8000000u,
                                                  0);
          if ( *(_QWORD *)((char *)*a3 + v49 + 16) == -1 )
          {
            LastError = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "CreateInternalDriverFileArray",
              L"Failed to open file %ws, error %d",
              *((_QWORD *)*a3 + 4 * k),
              LastError);
            goto LABEL_91;
          }
          v45 = 0;
        }
        if ( a1 == 101 )
        {
          if ( a2 && *((_QWORD *)a2 + 3) && *((_DWORD *)a2 + 8) == v47 )
          {
            while ( v45 < *((_DWORD *)a2 + 8) )
            {
              LODWORD(v48[4 * v45 + 1]) = *(_DWORD *)(*((_QWORD *)a2 + 3) + 12LL * v45 + 8);
              ++v45;
            }
            goto LABEL_94;
          }
        }
        else if ( v48 && v47 )
        {
          for ( m = 0; m < v47; ++m )
          {
            v52 = 4LL * m;
            if ( (unsigned int)IsEXEFile(v48[v52]) && !(unsigned int)GetPrintDriverVersion((LPCWSTR)v48[v52]) )
              goto LABEL_91;
          }
          goto LABEL_94;
        }
        v10 = 0;
        SetLastError(0xDu);
LABEL_94:
        if ( !v10 )
        {
          CleanupInternalDriverInfo(*a3);
          *a4 = 0;
          *a3 = 0;
        }
        DllFreeSplMem(v60);
        goto LABEL_98;
      }
LABEL_66:
      v41 = a6;
      goto LABEL_68;
    }
    v31 = (unsigned __int16 *)*((_QWORD *)v13 + 3);
    if ( a5 )
    {
      *(_QWORD *)*a3 = GetFileNameInScratchDir(v31, a6);
      *((_QWORD *)*a3 + 4) = GetFileNameInScratchDir(*((unsigned __int16 **)v56 + 5), a6);
      *((_QWORD *)*a3 + 8) = GetFileNameInScratchDir(*((unsigned __int16 **)v56 + 4), a6);
      v32 = (unsigned __int16 *)*((_QWORD *)v56 + 6);
      if ( v32 && *v32 )
      {
        v33 = GetFileNameInScratchDir(v32, a6);
LABEL_54:
        *((_QWORD *)*a3 + 12) = v33;
      }
    }
    else
    {
      *(_QWORD *)*a3 = AllocSplStr(v31);
      *((_QWORD *)*a3 + 4) = AllocSplStr(*((_QWORD *)v13 + 5));
      *((_QWORD *)*a3 + 8) = AllocSplStr(*((_QWORD *)v13 + 4));
      v34 = (_WORD *)*((_QWORD *)v13 + 6);
      if ( v34 && *v34 )
      {
        v33 = (unsigned __int16 *)AllocSplStr(v34);
        goto LABEL_54;
      }
    }
    if ( v54 )
    {
      while ( 1 )
      {
        v35 = v12;
        if ( !*v11 )
          break;
        ++v12;
        v36 = 32LL * v35;
        if ( a5 )
          v37 = GetFileNameInScratchDir(v11, a6);
        else
          v37 = (unsigned __int16 *)AllocSplStr(v11);
        *(_QWORD *)((char *)*a3 + v36) = v37;
        v38 = -1;
        do
          ++v38;
        while ( v11[v38] );
        v11 += v38 + 1;
      }
    }
    goto LABEL_66;
  }
  v19 = -1;
  do
    ++v19;
  while ( v18[v19] );
  if ( v19 < 0x104 )
  {
    ++*a4;
    v12 = 4;
    goto LABEL_21;
  }
LABEL_19:
  v10 = 0;
  SetLastError(0xDu);
  *a4 = 0;
LABEL_98:
  v15 = a6;
LABEL_99:
  if ( !v55 )
  {
    EnterSplSem(0);
    SafeDecrementReference((unsigned int *)v15 + 4);
  }
  return v10;
}

```

## disassembly

```asm
0x18006c1c0  mov     rax, rsp
0x18006c1c3  mov     [rax+20h], r9
0x18006c1c7  mov     [rax+18h], r8
0x18006c1cb  mov     [rax+8], ecx
0x18006c1ce  push    rbx
0x18006c1cf  push    rsi
0x18006c1d0  push    rdi
0x18006c1d1  push    r12
0x18006c1d3  push    r13
0x18006c1d5  push    r14
0x18006c1d7  push    r15
0x18006c1d9  sub     rsp, 90h
0x18006c1e0  mov     rsi, r9
0x18006c1e3  mov     rdi, r8
0x18006c1e6  mov     r12, rdx
0x18006c1e9  mov     ebx, 1
0x18006c1ee  mov     [rax-74h], ebx
0x18006c1f1  xor     r9d, r9d
0x18006c1f4  mov     r14d, r9d
0x18006c1f7  mov     [rax-68h], r9
0x18006c1fb  test    r8, r8
0x18006c1fe  jz      loc_18006C827
0x18006c204  test    rsi, rsi
0x18006c207  jz      loc_18006C827
0x18006c20d  mov     [rsp+0C8h+var_80], r9d
0x18006c212  mov     r15d, r9d
0x18006c215  mov     [rsp+0C8h+var_84], ebx
0x18006c219  mov     [rsp+0C8h+var_58], r9
0x18006c21e  mov     r13d, r9d
0x18006c221  mov     [rsp+0C8h+var_70], r9
0x18006c226  mov     [rsp+0C8h+var_60], r9
0x18006c22b  mov     [rsp+0C8h+var_50], r9
0x18006c230  mov     [rsi], r9d
0x18006c233  mov     [r8], r9
0x18006c236  mov     eax, ecx
0x18006c238  sub     eax, 2
0x18006c23b  jz      loc_18006C371
0x18006c241  sub     eax, ebx
0x18006c243  jz      short loc_18006C26B
0x18006c245  sub     eax, ebx
0x18006c247  jz      short loc_18006C26B
0x18006c249  sub     eax, 2
0x18006c24c  jz      short loc_18006C26B
0x18006c24e  sub     eax, 2
0x18006c251  jz      short loc_18006C26B
0x18006c253  sub     eax, 5Dh ; ']'
0x18006c256  jnz     loc_18006C827
0x18006c25c  mov     [rsp+0C8h+var_60], rdx
0x18006c261  mov     ecx, [rdx+20h]
0x18006c264  mov     [rsi], ecx
0x18006c266  jmp     loc_18006C384
0x18006c26b  mov     dword ptr [rsi], 3
0x18006c271  lea     rdx, szWin95Environment; "Windows 4.0"
0x18006c278  mov     r15, [rsp+0C8h+arg_28]
0x18006c280  mov     rcx, [r15+18h]
0x18006c284  call    cs:__imp__o__wcsicmp
0x18006c28a  mov     r14, [r12+38h]
0x18006c28f  xor     r9d, r9d
0x18006c292  test    eax, eax
0x18006c294  jz      short loc_18006C2E0
0x18006c296  lea     rax, [rsp+0C8h+var_68]
0x18006c29b  mov     qword ptr [rsp+0C8h+dwFlagsAndAttributes], rax
0x18006c2a0  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r14
0x18006c2a5  mov     r9, [r12+30h]
0x18006c2aa  mov     r8, [r12+28h]
0x18006c2af  mov     rdx, [r12+20h]
0x18006c2b4  mov     rcx, [r12+18h]
0x18006c2b9  call    BuildTrueDependentFileField
0x18006c2be  xor     r9d, r9d
0x18006c2c1  test    eax, eax
0x18006c2c3  jnz     short loc_18006C2D6
0x18006c2c5  mov     ebx, r9d
0x18006c2c8  lea     ecx, [rax+0Dh]; dwErrCode
0x18006c2cb  call    cs:__imp_SetLastError
0x18006c2d1  jmp     loc_18006C83D
0x18006c2d6  mov     r14, [rsp+0C8h+var_68]
0x18006c2db  mov     [rsp+0C8h+var_50], r14
0x18006c2e0  mov     rax, r14
0x18006c2e3  mov     r15d, 3
0x18006c2e9  mov     rdx, [r12+30h]
0x18006c2ee  test    rdx, rdx
0x18006c2f1  jz      short loc_18006C32E
0x18006c2f3  cmp     [rdx], r9w
0x18006c2f7  jz      short loc_18006C32E
0x18006c2f9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006c2fd  inc     rcx
0x18006c300  cmp     [rdx+rcx*2], r9w
0x18006c305  jnz     short loc_18006C2FD
0x18006c307  cmp     rcx, 104h
0x18006c30e  jb      short loc_18006C326
0x18006c310  mov     ebx, r9d
0x18006c313  mov     ecx, 0Dh; dwErrCode
0x18006c318  call    cs:__imp_SetLastError
0x18006c31e  mov     [rsi], r13d
0x18006c321  jmp     loc_18006C835
0x18006c326  add     [rsi], ebx
0x18006c328  mov     r15d, 4
0x18006c32e  mov     edx, r9d
0x18006c331  test    rax, rax
0x18006c334  jmp     short loc_18006C35D
0x18006c336  cmp     [rax], r9w
0x18006c33a  jz      short loc_18006C363
0x18006c33c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006c340  inc     rcx
0x18006c343  cmp     [rax+rcx*2], r9w
0x18006c348  jnz     short loc_18006C340
0x18006c34a  cmp     rcx, 104h
0x18006c351  jnb     short loc_18006C310
0x18006c353  add     edx, ebx
0x18006c355  lea     rax, [rax+rcx*2]
0x18006c359  add     rax, 2
0x18006c35d  mov     [rsp+0C8h+var_80], edx
0x18006c361  jnz     short loc_18006C336
0x18006c363  mov     r13, r12
0x18006c366  mov     [rsp+0C8h+var_70], r12
0x18006c36b  add     [rsi], edx
0x18006c36d  mov     ecx, [rsi]
0x18006c36f  jmp     short loc_18006C384
0x18006c371  mov     dword ptr [rsi], 3
0x18006c377  mov     rax, r12
0x18006c37a  mov     [rsp+0C8h+var_58], rax
0x18006c37f  mov     ecx, 3
0x18006c384  shl     ecx, 5
0x18006c387  call    cs:__imp_DllAllocSplMem
0x18006c38d  mov     [rdi], rax
0x18006c390  xor     r8d, r8d
0x18006c393  test    rax, rax
0x18006c396  jz      loc_18006C7E4
0x18006c39c  mov     edx, r8d
0x18006c39f  mov     [rsp+0C8h+var_88], edx
0x18006c3a3  cmp     edx, [rsi]
0x18006c3a5  jnb     short loc_18006C3D4
0x18006c3a7  mov     ecx, edx
0x18006c3a9  shl     rcx, 5
0x18006c3ad  mov     rax, [rdi]
0x18006c3b0  mov     [rcx+rax], r8
0x18006c3b4  mov     rax, [rdi]
0x18006c3b7  mov     qword ptr [rcx+rax+10h], 0FFFFFFFFFFFFFFFFh
0x18006c3c0  mov     rax, [rdi]
0x18006c3c3  mov     [rcx+rax+8], r8d
0x18006c3c8  mov     rax, [rdi]
0x18006c3cb  mov     [rcx+rax+18h], r8d
0x18006c3d0  add     edx, ebx
0x18006c3d2  jmp     short loc_18006C39F
0x18006c3d4  mov     eax, [rsp+0C8h+arg_0]
0x18006c3db  sub     eax, 2
0x18006c3de  jz      loc_18006C5AD
0x18006c3e4  sub     eax, 1
0x18006c3e7  jz      loc_18006C478
0x18006c3ed  sub     eax, 1
0x18006c3f0  jz      loc_18006C478
0x18006c3f6  sub     eax, 1
0x18006c3f9  jz      short loc_18006C478
0x18006c3fb  sub     eax, 1
0x18006c3fe  jz      short loc_18006C478
0x18006c400  sub     eax, 2
0x18006c403  jz      short loc_18006C478
0x18006c405  sub     eax, 5Dh ; ']'
0x18006c408  jnz     loc_18006C636
0x18006c40e  mov     r14d, r8d
0x18006c411  mov     [rsp+0C8h+var_88], r8d
0x18006c416  mov     r15, [rsp+0C8h+arg_28]
0x18006c41e  cmp     r14d, [rsi]
0x18006c421  jnb     loc_18006C640
0x18006c427  mov     eax, r14d
0x18006c42a  lea     rcx, [rax+rax*2]
0x18006c42e  mov     rax, [rsp+0C8h+var_60]
0x18006c433  mov     rdx, [rax+18h]
0x18006c437  mov     edx, [rdx+rcx*4]
0x18006c43a  mov     rcx, rax
0x18006c43d  call    cs:__imp_MakePTR
0x18006c443  mov     r13d, r14d
0x18006c446  shl     r13, 5
0x18006c44a  mov     rcx, rax; unsigned __int16 *
0x18006c44d  cmp     [rsp+0C8h+arg_20], 0
0x18006c455  jz      short loc_18006C461
0x18006c457  mov     rdx, r15; struct _INIENVIRONMENT *
0x18006c45a  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c45f  jmp     short loc_18006C467
0x18006c461  call    cs:__imp_AllocSplStr
0x18006c467  mov     rcx, [rdi]
0x18006c46a  mov     [rcx+r13], rax
0x18006c46e  add     r14d, ebx
0x18006c471  mov     [rsp+0C8h+var_88], r14d
0x18006c476  jmp     short loc_18006C41E
0x18006c478  mov     rcx, [r13+18h]; unsigned __int16 *
0x18006c47c  cmp     [rsp+0C8h+arg_20], r8d
0x18006c484  jz      short loc_18006C4ED
0x18006c486  mov     r13, [rsp+0C8h+arg_28]
0x18006c48e  mov     rdx, r13; struct _INIENVIRONMENT *
0x18006c491  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c496  mov     rcx, [rdi]
0x18006c499  mov     [rcx], rax
0x18006c49c  mov     rdx, r13; struct _INIENVIRONMENT *
0x18006c49f  mov     rcx, [rsp+0C8h+var_70]
0x18006c4a4  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18006c4a8  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c4ad  mov     rcx, [rdi]
0x18006c4b0  mov     [rcx+20h], rax
0x18006c4b4  mov     rdx, r13; struct _INIENVIRONMENT *
0x18006c4b7  mov     rax, [rsp+0C8h+var_70]
0x18006c4bc  mov     rcx, [rax+20h]; unsigned __int16 *
0x18006c4c0  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c4c5  mov     rcx, [rdi]
0x18006c4c8  mov     [rcx+40h], rax
0x18006c4cc  mov     rax, [rsp+0C8h+var_70]
0x18006c4d1  mov     rcx, [rax+30h]; unsigned __int16 *
0x18006c4d5  xor     r8d, r8d
0x18006c4d8  test    rcx, rcx
0x18006c4db  jz      short loc_18006C53D
0x18006c4dd  cmp     [rcx], r8w
0x18006c4e1  jz      short loc_18006C53D
0x18006c4e3  mov     rdx, r13; struct _INIENVIRONMENT *
0x18006c4e6  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c4eb  jmp     short loc_18006C533
0x18006c4ed  call    cs:__imp_AllocSplStr
0x18006c4f3  mov     rcx, [rdi]
0x18006c4f6  mov     [rcx], rax
0x18006c4f9  mov     rcx, [r13+28h]
0x18006c4fd  call    cs:__imp_AllocSplStr
0x18006c503  mov     rcx, [rdi]
0x18006c506  mov     [rcx+20h], rax
0x18006c50a  mov     rcx, [r13+20h]
0x18006c50e  call    cs:__imp_AllocSplStr
0x18006c514  mov     rcx, [rdi]
0x18006c517  mov     [rcx+40h], rax
0x18006c51b  mov     rcx, [r13+30h]
0x18006c51f  xor     r8d, r8d
0x18006c522  test    rcx, rcx
0x18006c525  jz      short loc_18006C53D
0x18006c527  cmp     [rcx], r8w
0x18006c52b  jz      short loc_18006C53D
0x18006c52d  call    cs:__imp_AllocSplStr
0x18006c533  mov     rcx, [rdi]
0x18006c536  xor     r8d, r8d
0x18006c539  mov     [rcx+60h], rax
0x18006c53d  cmp     [rsp+0C8h+var_80], r8d
0x18006c542  jz      loc_18006C636
0x18006c548  mov     [rsp+0C8h+var_88], r15d
0x18006c54d  mov     eax, r15d
0x18006c550  cmp     [r14], r8w
0x18006c554  jz      loc_18006C636
0x18006c55a  inc     r15d
0x18006c55d  mov     r13d, eax
0x18006c560  shl     r13, 5
0x18006c564  mov     rcx, r14; unsigned __int16 *
0x18006c567  cmp     [rsp+0C8h+arg_20], r8d
0x18006c56f  jz      short loc_18006C580
0x18006c571  mov     rdx, [rsp+0C8h+arg_28]; struct _INIENVIRONMENT *
0x18006c579  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c57e  jmp     short loc_18006C586
0x18006c580  call    cs:__imp_AllocSplStr
0x18006c586  mov     rcx, [rdi]
0x18006c589  mov     [rcx+r13], rax
0x18006c58d  mov     [rsp+0C8h+var_88], r15d
0x18006c592  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006c596  xor     r8d, r8d
0x18006c599  inc     rax
0x18006c59c  cmp     [r14+rax*2], r8w
0x18006c5a1  jnz     short loc_18006C599
0x18006c5a3  lea     r14, [r14+rax*2]
0x18006c5a7  add     r14, 2
0x18006c5ab  jmp     short loc_18006C54D
0x18006c5ad  mov     r15, [rsp+0C8h+var_58]
0x18006c5b2  mov     rcx, [r15+18h]; unsigned __int16 *
0x18006c5b6  cmp     [rsp+0C8h+arg_20], r8d
0x18006c5be  jz      short loc_18006C5FE
0x18006c5c0  mov     r14, [rsp+0C8h+arg_28]
0x18006c5c8  mov     rdx, r14; struct _INIENVIRONMENT *
0x18006c5cb  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c5d0  mov     rcx, [rdi]
0x18006c5d3  mov     [rcx], rax
0x18006c5d6  mov     rdx, r14; struct _INIENVIRONMENT *
0x18006c5d9  mov     rcx, [r15+28h]; unsigned __int16 *
0x18006c5dd  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c5e2  mov     rcx, [rdi]
0x18006c5e5  mov     [rcx+20h], rax
0x18006c5e9  mov     rdx, r14; struct _INIENVIRONMENT *
0x18006c5ec  mov     rcx, [r15+20h]; unsigned __int16 *
0x18006c5f0  call    ?GetFileNameInScratchDir@@YAPEAGPEAGPEAU_INIENVIRONMENT@@@Z; GetFileNameInScratchDir(ushort *,_INIENVIRONMENT *)
0x18006c5f5  mov     rcx, [rdi]
0x18006c5f8  mov     [rcx+40h], rax
0x18006c5fc  jmp     short loc_18006C643
0x18006c5fe  call    cs:__imp_AllocSplStr
0x18006c604  mov     rcx, [rdi]
0x18006c607  mov     [rcx], rax
0x18006c60a  mov     rcx, [r15+28h]
0x18006c60e  call    cs:__imp_AllocSplStr
0x18006c614  mov     rcx, [rdi]
0x18006c617  mov     [rcx+20h], rax
0x18006c61b  mov     rcx, [r15+20h]
0x18006c61f  call    cs:__imp_AllocSplStr
0x18006c625  mov     rcx, [rdi]
0x18006c628  mov     [rcx+40h], rax
0x18006c62c  mov     r14, [rsp+0C8h+arg_28]
0x18006c634  jmp     short loc_18006C643
0x18006c636  mov     r14, [rsp+0C8h+arg_28]
0x18006c63e  jmp     short loc_18006C646
0x18006c640  mov     r14, r15
0x18006c643  xor     r8d, r8d
  ... truncated ...
```
