# sqlite3InitOne

- ea: `0x140060050`
- end: `0x1400603f9`
- name: `sqlite3InitOne`
- size: `937`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14005fd9c`
- `0x140074448`

## callees

- `0x140001ba0`
- `0x14001f914`
- `0x140020730`
- `0x14004b2f4`
- `0x14004d36c`
- `0x14004de74`
- `0x14004fb1c`
- `0x140053e3c`
- `0x140056018`
- `0x14005fe30`
- `0x140060050`
- `0x140062bfc`
- `0x1400636dc`
- `0x14006b6ec`
- `0x14006b778`
- `0x14006f26c`
- `0x14006f2b8`
- `0x14008a490`
- `0x140092d90`

## string_xrefs

- `0x140060098`: `sqlite_temp_master`
- `0x1400600ef`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

## pseudocode

```c
__int64 __fastcall sqlite3InitOne(__int64 a1, int a2, __int64 a3, int a4)
{
  int v4; // ebx
  __int64 v5; // r13
  const char *v8; // rax
  unsigned int v9; // ebx
  unsigned int v10; // esi
  __int64 v11; // rax
  __int64 v12; // r15
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // ebx
  int v20; // edx
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  bool v24; // zf
  const char *v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // r12
  unsigned int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v35; // [rsp+30h] [rbp-79h]
  __int128 v36; // [rsp+38h] [rbp-71h] BYREF
  int v37; // [rsp+48h] [rbp-61h]
  _QWORD v38[2]; // [rsp+50h] [rbp-59h] BYREF
  int v39; // [rsp+60h] [rbp-49h]
  unsigned int v40; // [rsp+64h] [rbp-45h]
  int v41; // [rsp+68h] [rbp-41h]
  int v42; // [rsp+6Ch] [rbp-3Dh]
  __int64 v43; // [rsp+70h] [rbp-39h]
  const char *v44; // [rsp+78h] [rbp-31h]
  _QWORD v45[6]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_DWORD *)(a1 + 44);
  v5 = a2;
  v45[0] = "table";
  v41 = a4;
  v43 = 0;
  v8 = "sqlite_temp_master";
  v45[5] = 0;
  v9 = v4 | 0xFFFFFFBF;
  v40 = 0;
  *(_BYTE *)(a1 + 197) = 1;
  v42 = 0;
  if ( a2 != 1 )
    v8 = "sqlite_master";
  v38[0] = a1;
  v44 = v8;
  v45[1] = v8;
  v45[2] = v8;
  v39 = a2;
  v45[3] = "1";
  v45[4] = "CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)";
  v38[1] = a3;
  sqlite3InitCallback(v38, 5, v45);
  *(_DWORD *)(a1 + 44) &= v9;
  v10 = v40;
  if ( v40 )
    goto LABEL_68;
  v11 = *(_QWORD *)(a1 + 32);
  v12 = 32 * v5;
  v13 = 32 * v5 + v11;
  v14 = *(_QWORD *)(v13 + 8);
  if ( !v14 )
  {
    v10 = 0;
    *(_WORD *)(*(_QWORD *)(v11 + 56) + 114LL) |= 1u;
    goto LABEL_72;
  }
  v10 = 1;
  if ( *(_BYTE *)(v14 + 17) )
  {
    ++*(_DWORD *)(v14 + 20);
    if ( !*(_BYTE *)(v14 + 18) )
      btreeLockCarefully(v14);
  }
  v15 = *(_QWORD *)(v13 + 8);
  if ( !v15 || (v35 = 0, !*(_BYTE *)(v15 + 16)) )
  {
    if ( *(_BYTE *)(v15 + 17) || !*(_BYTE *)(v15 + 16) )
    {
      v16 = btreeBeginTrans(v15, 0, 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = sqlite3ErrStr(v16);
        sqlite3SetString(a3, a1, v17);
        goto LABEL_64;
      }
      v10 = 1;
    }
    v35 = 1;
  }
  v18 = 0;
  do
  {
    v19 = v18 + 1;
    sqlite3BtreeGetMeta(*(_QWORD *)(v13 + 8), (unsigned int)(v18 + 1), (char *)&v36 + 4 * v18);
    v18 = (unsigned int)v19;
  }
  while ( v19 < 5 );
  if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
  {
    v20 = 0;
    v36 = 0;
  }
  else
  {
    v20 = v37;
  }
  **(_DWORD **)(v13 + 24) = v36;
  if ( !v20 )
    goto LABEL_32;
  if ( !(_DWORD)v5 && (*(_BYTE *)(a1 + 44) & 0x40) == 0 )
  {
    v21 = v20 & 3;
    if ( !(_BYTE)v21 )
      v21 = 1;
    if ( *(int *)(a1 + 216) > 0 && (_BYTE)v21 != *(_BYTE *)(a1 + 100) && (*(_BYTE *)(a1 + 44) & 4) == 0 )
    {
      v10 = 6;
      goto LABEL_62;
    }
    sqlite3SetTextEncoding(a1, v21);
LABEL_32:
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 113LL) = *(_BYTE *)(a1 + 100);
    v22 = *(_QWORD *)(v13 + 24);
    if ( *(_DWORD *)(v22 + 116) )
    {
LABEL_43:
      *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) = BYTE4(v36);
      v26 = *(_QWORD *)(v13 + 24);
      if ( !*(_BYTE *)(v26 + 112) )
        *(_BYTE *)(v26 + 112) = 1;
      if ( *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) <= 4u )
      {
        if ( !(_DWORD)v5 && SDWORD1(v36) >= 4 )
          *(_QWORD *)(a1 + 48) &= ~2uLL;
        v27 = *(_QWORD *)(a1 + 32);
        LODWORD(v43) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 64LL);
        v28 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v12 + v27), v44);
        v29 = *(_QWORD *)(a1 + 512);
        *(_QWORD *)(a1 + 512) = 0;
        v30 = v28;
        v31 = sqlite3_exec(a1, v28, (unsigned int)sqlite3InitCallback, (unsigned int)v38, 0);
        *(_QWORD *)(a1 + 512) = v29;
        v10 = v31;
        if ( !v31 )
          v10 = v40;
        if ( v30 )
          sqlite3DbFreeNN(a1);
        if ( !v10 )
          sqlite3AnalysisLoad(a1, (unsigned int)v5);
        if ( *(_BYTE *)(a1 + 103) )
        {
          v10 = 7;
          sqlite3ResetAllSchemasOfConnection(a1);
          v13 = v12 + *(_QWORD *)(a1 + 32);
        }
        else if ( !v10 || (*(_DWORD *)(a1 + 48) & 0x8000000) != 0 && v10 != 7 )
        {
          v10 = 0;
          v32 = *(_QWORD *)(v12 + *(_QWORD *)(a1 + 32) + 24);
          *(_WORD *)(v32 + 114) |= 1u;
        }
        goto LABEL_62;
      }
      v25 = "unsupported file format";
      goto LABEL_38;
    }
    v23 = DWORD2(v36);
    v24 = DWORD2(v36) == 0;
    if ( SDWORD2(v36) < 0 )
    {
      if ( DWORD2(v36) == 0x80000000 )
      {
        v23 = 0x7FFFFFFF;
LABEL_42:
        *(_DWORD *)(v22 + 116) = v23;
        sqlite3BtreeSetCacheSize(*(_QWORD *)(v13 + 8), *(unsigned int *)(*(_QWORD *)(v13 + 24) + 116LL));
        goto LABEL_43;
      }
      v23 = -DWORD2(v36);
      v24 = DWORD2(v36) == 0;
    }
    if ( v24 )
      v23 = -2000;
    goto LABEL_42;
  }
  if ( (v20 & 3) == *(_BYTE *)(a1 + 100) )
    goto LABEL_32;
  v25 = "attached databases must use the same text encoding as main database";
LABEL_38:
  sqlite3SetString(a3, a1, v25);
LABEL_62:
  if ( v35 )
    sqlite3BtreeCommit(*(_QWORD *)(v13 + 8));
LABEL_64:
  v33 = *(_QWORD *)(v13 + 8);
  if ( *(_BYTE *)(v33 + 17) )
  {
    v24 = (*(_DWORD *)(v33 + 20))-- == 1;
    if ( v24 )
      unlockBtreeMutex();
  }
  if ( v10 )
  {
LABEL_68:
    if ( v10 == 7 || v10 == 3082 )
      sqlite3OomFault(a1);
    sqlite3ResetOneSchema(a1);
  }
LABEL_72:
  *(_BYTE *)(a1 + 197) = 0;
  return v10;
}

```

## disassembly

```asm
0x140060050  push    rbp
0x140060052  push    rbx
0x140060053  push    rsi
0x140060054  push    rdi
0x140060055  push    r12
0x140060057  push    r13
0x140060059  push    r14
0x14006005b  push    r15
0x14006005d  lea     rbp, [rsp-1Fh]
0x140060062  sub     rsp, 0C8h
0x140060069  mov     rax, cs:__security_cookie
0x140060070  xor     rax, rsp
0x140060073  mov     [rbp+57h+var_50], rax
0x140060077  mov     ebx, [rcx+2Ch]
0x14006007a  lea     rax, aTable; "table"
0x140060081  movsxd  r13, edx
0x140060084  mov     r12, r8
0x140060087  xor     edx, edx
0x140060089  mov     [rbp+57h+var_80], rax
0x14006008d  mov     rdi, rcx
0x140060090  mov     [rbp+57h+var_98], r9d
0x140060094  mov     [rbp+57h+var_90], rdx
0x140060098  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x14006009f  mov     [rbp+57h+var_58], rdx
0x1400600a3  or      ebx, 0FFFFFFBFh
0x1400600a6  lea     r8d, [rdx+1]
0x1400600aa  mov     [rbp+57h+var_9C], edx
0x1400600ad  mov     [rcx+0C5h], r8b
0x1400600b4  cmp     r13d, r8d
0x1400600b7  lea     rcx, aSqliteMaster; "sqlite_master"
0x1400600be  mov     [rbp+57h+var_94], edx
0x1400600c1  cmovnz  rax, rcx
0x1400600c5  mov     [rbp+57h+var_B0], rdi
0x1400600c9  mov     [rbp+57h+var_88], rax
0x1400600cd  lea     r8, [rbp+57h+var_80]
0x1400600d1  mov     [rbp+57h+var_78], rax
0x1400600d5  lea     rcx, [rbp+57h+var_B0]
0x1400600d9  mov     [rbp+57h+var_70], rax
0x1400600dd  xor     r9d, r9d
0x1400600e0  lea     rax, a1; "1"
0x1400600e7  mov     [rbp+57h+var_A0], r13d
0x1400600eb  mov     [rbp+57h+var_68], rax
0x1400600ef  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x1400600f6  mov     [rbp+57h+var_60], rax
0x1400600fa  lea     edx, [r9+5]
0x1400600fe  mov     [rbp+57h+var_A8], r12
0x140060102  call    sqlite3InitCallback
0x140060107  and     [rdi+2Ch], ebx
0x14006010a  xor     ebx, ebx
0x14006010c  mov     esi, [rbp+57h+var_9C]
0x14006010f  test    esi, esi
0x140060111  jnz     loc_1400603B1
0x140060117  mov     rax, [rdi+20h]
0x14006011b  mov     r15, r13
0x14006011e  shl     r15, 5
0x140060122  lea     r14, [r15+rax]
0x140060126  mov     rcx, [r14+8]
0x14006012a  test    rcx, rcx
0x14006012d  jnz     short loc_140060141
0x14006012f  mov     rax, [rax+38h]
0x140060133  lea     edx, [rsi+1]
0x140060136  mov     esi, ebx
0x140060138  or      [rax+72h], dx
0x14006013c  jmp     loc_1400603D1
0x140060141  mov     esi, 1
0x140060146  cmp     [rcx+11h], bl
0x140060149  jz      short loc_140060158
0x14006014b  add     [rcx+14h], esi
0x14006014e  cmp     [rcx+12h], bl
0x140060151  jnz     short loc_140060158
0x140060153  call    btreeLockCarefully
0x140060158  mov     rcx, [r14+8]
0x14006015c  test    rcx, rcx
0x14006015f  jz      short loc_140060169
0x140060161  mov     [rbp+57h+var_D0], ebx
0x140060164  cmp     [rcx+10h], bl
0x140060167  jnz     short loc_1400601A5
0x140060169  cmp     [rcx+11h], bl
0x14006016c  jnz     short loc_140060173
0x14006016e  cmp     [rcx+10h], bl
0x140060171  jnz     short loc_1400601A2
0x140060173  xor     r8d, r8d
0x140060176  xor     edx, edx
0x140060178  call    btreeBeginTrans
0x14006017d  mov     esi, eax
0x14006017f  test    eax, eax
0x140060181  jz      short loc_14006019D
0x140060183  mov     ecx, eax
0x140060185  call    sqlite3ErrStr
0x14006018a  mov     r8, rax
0x14006018d  mov     rdx, rdi
0x140060190  mov     rcx, r12
0x140060193  call    sqlite3SetString
0x140060198  jmp     loc_140060399
0x14006019d  mov     esi, 1
0x1400601a2  mov     [rbp+57h+var_D0], esi
0x1400601a5  mov     eax, ebx
0x1400601a7  mov     rcx, [r14+8]
0x1400601ab  lea     ebx, [rax+1]
0x1400601ae  lea     r8, [rbp+57h+var_C8]
0x1400601b2  mov     edx, ebx
0x1400601b4  lea     r8, [r8+rax*4]
0x1400601b8  call    sqlite3BtreeGetMeta
0x1400601bd  mov     eax, ebx
0x1400601bf  cmp     ebx, 5
0x1400601c2  jl      short loc_1400601A7
0x1400601c4  mov     eax, [rdi+30h]
0x1400601c7  bt      rax, 19h
0x1400601cc  jnb     short loc_1400601D9
0x1400601ce  xorps   xmm0, xmm0
0x1400601d1  xor     edx, edx
0x1400601d3  movups  [rbp+57h+var_C8], xmm0
0x1400601d7  jmp     short loc_1400601DC
0x1400601d9  mov     edx, [rbp+57h+var_B8]
0x1400601dc  mov     rcx, [r14+18h]
0x1400601e0  xor     ebx, ebx
0x1400601e2  mov     eax, dword ptr [rbp+57h+var_C8]
0x1400601e5  mov     [rcx], eax
0x1400601e7  test    edx, edx
0x1400601e9  jz      short loc_140060223
0x1400601eb  test    r13d, r13d
0x1400601ee  jnz     short loc_14006024B
0x1400601f0  test    byte ptr [rdi+2Ch], 40h
0x1400601f4  jnz     short loc_14006024B
0x1400601f6  mov     al, dl
0x1400601f8  and     al, 3
0x1400601fa  movzx   edx, al
0x1400601fd  cmovz   edx, esi
0x140060200  cmp     [rdi+0D8h], ebx
0x140060206  jle     short loc_14006021B
0x140060208  cmp     dl, [rdi+64h]
0x14006020b  jz      short loc_14006021B
0x14006020d  test    byte ptr [rdi+2Ch], 4
0x140060211  jnz     short loc_14006021B
0x140060213  lea     esi, [rbx+6]
0x140060216  jmp     loc_14006038B
0x14006021b  mov     rcx, rdi
0x14006021e  call    sqlite3SetTextEncoding
0x140060223  mov     rcx, [r14+18h]
0x140060227  mov     al, [rdi+64h]
0x14006022a  mov     [rcx+71h], al
0x14006022d  mov     rcx, [r14+18h]
0x140060231  cmp     [rcx+74h], ebx
0x140060234  jnz     short loc_140060288
0x140060236  mov     eax, dword ptr [rbp+57h+var_C8+8]
0x140060239  test    eax, eax
0x14006023b  jns     short loc_14006026E
0x14006023d  cmp     eax, 80000000h
0x140060242  jnz     short loc_14006026A
0x140060244  mov     eax, 7FFFFFFFh
0x140060249  jmp     short loc_140060275
0x14006024b  and     edx, 3
0x14006024e  cmp     dl, [rdi+64h]
0x140060251  jz      short loc_140060223
0x140060253  lea     r8, aAttachedDataba; "attached databases must use the same te"...
0x14006025a  mov     rdx, rdi
0x14006025d  mov     rcx, r12
0x140060260  call    sqlite3SetString
0x140060265  jmp     loc_14006038B
0x14006026a  neg     eax
0x14006026c  test    eax, eax
0x14006026e  jnz     short loc_140060275
0x140060270  mov     eax, 0FFFFF830h
0x140060275  mov     [rcx+74h], eax
0x140060278  mov     rdx, [r14+18h]
0x14006027c  mov     rcx, [r14+8]
0x140060280  mov     edx, [rdx+74h]
0x140060283  call    sqlite3BtreeSetCacheSize
0x140060288  mov     al, byte ptr [rbp+57h+var_C8+4]
0x14006028b  mov     rcx, [r14+18h]
0x14006028f  mov     [rcx+70h], al
0x140060292  mov     rax, [r14+18h]
0x140060296  cmp     [rax+70h], bl
0x140060299  jnz     short loc_14006029F
0x14006029b  mov     [rax+70h], sil
0x14006029f  mov     rax, [r14+18h]
0x1400602a3  cmp     byte ptr [rax+70h], 4
0x1400602a7  jbe     short loc_1400602B2
0x1400602a9  lea     r8, aUnsupportedFil; "unsupported file format"
0x1400602b0  jmp     short loc_14006025A
0x1400602b2  test    r13d, r13d
0x1400602b5  jnz     short loc_1400602C2
0x1400602b7  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x1400602bb  jl      short loc_1400602C2
0x1400602bd  and     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFDh
0x1400602c2  mov     rax, [r14+8]
0x1400602c6  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x1400602cd  mov     r8, [rdi+20h]
0x1400602d1  mov     r9, [rbp+57h+var_88]
0x1400602d5  mov     rcx, [rax+8]
0x1400602d9  mov     eax, [rcx+40h]
0x1400602dc  mov     rcx, rdi
0x1400602df  mov     dword ptr [rbp+57h+var_90], eax
0x1400602e2  mov     r8, [r15+r8]
0x1400602e6  call    sqlite3MPrintf
0x1400602eb  mov     rbx, [rdi+200h]
0x1400602f2  lea     r9, [rbp+57h+var_B0]
0x1400602f6  xor     edx, edx
0x1400602f8  lea     r8, sqlite3InitCallback
0x1400602ff  mov     [rdi+200h], rdx
0x140060306  mov     rcx, rdi
0x140060309  mov     [rsp+100h+var_E0], rdx
0x14006030e  mov     r12, rax
0x140060311  mov     rdx, rax
0x140060314  call    sqlite3_exec
0x140060319  mov     [rdi+200h], rbx
0x140060320  mov     esi, eax
0x140060322  xor     ebx, ebx
0x140060324  test    eax, eax
0x140060326  cmovz   esi, [rbp+57h+var_9C]
0x14006032a  test    r12, r12
0x14006032d  jz      short loc_14006033A
0x14006032f  mov     rdx, r12
0x140060332  mov     rcx, rdi
0x140060335  call    sqlite3DbFreeNN
0x14006033a  test    esi, esi
0x14006033c  jnz     short loc_140060349
0x14006033e  mov     edx, r13d
0x140060341  mov     rcx, rdi
0x140060344  call    sqlite3AnalysisLoad
0x140060349  cmp     [rdi+67h], bl
0x14006034c  jz      short loc_140060364
0x14006034e  mov     rcx, rdi
0x140060351  mov     esi, 7
0x140060356  call    sqlite3ResetAllSchemasOfConnection
0x14006035b  mov     r14, [rdi+20h]
0x14006035f  add     r14, r15
0x140060362  jmp     short loc_14006038B
0x140060364  test    esi, esi
0x140060366  jz      short loc_140060377
0x140060368  mov     eax, [rdi+30h]
0x14006036b  bt      rax, 1Bh
0x140060370  jnb     short loc_14006038B
0x140060372  cmp     esi, 7
0x140060375  jz      short loc_14006038B
0x140060377  mov     rax, [rdi+20h]
0x14006037b  mov     edx, 1
0x140060380  mov     esi, ebx
0x140060382  mov     rcx, [r15+rax+18h]
0x140060387  or      [rcx+72h], dx
0x14006038b  cmp     [rbp+57h+var_D0], ebx
0x14006038e  jz      short loc_140060399
0x140060390  mov     rcx, [r14+8]
0x140060394  call    sqlite3BtreeCommit
0x140060399  mov     rcx, [r14+8]
0x14006039d  cmp     [rcx+11h], bl
0x1400603a0  jz      short loc_1400603AD
0x1400603a2  sub     dword ptr [rcx+14h], 1
0x1400603a6  jnz     short loc_1400603AD
0x1400603a8  call    unlockBtreeMutex
0x1400603ad  test    esi, esi
0x1400603af  jz      short loc_1400603D1
0x1400603b1  cmp     esi, 7
0x1400603b4  jz      short loc_1400603BE
0x1400603b6  cmp     esi, 0C0Ah
0x1400603bc  jnz     short loc_1400603C6
0x1400603be  mov     rcx, rdi
0x1400603c1  call    sqlite3OomFault
0x1400603c6  mov     edx, r13d
0x1400603c9  mov     rcx, rdi
0x1400603cc  call    sqlite3ResetOneSchema
0x1400603d1  mov     [rdi+0C5h], bl
0x1400603d7  mov     eax, esi
0x1400603d9  mov     rcx, [rbp+57h+var_50]
0x1400603dd  xor     rcx, rsp; StackCookie
0x1400603e0  call    __security_check_cookie
0x1400603e5  add     rsp, 0C8h
0x1400603ec  pop     r15
0x1400603ee  pop     r14
0x1400603f0  pop     r13
0x1400603f2  pop     r12
0x1400603f4  pop     rdi
0x1400603f5  pop     rsi
0x1400603f6  pop     rbx
0x1400603f7  pop     rbp
0x1400603f8  retn
```
