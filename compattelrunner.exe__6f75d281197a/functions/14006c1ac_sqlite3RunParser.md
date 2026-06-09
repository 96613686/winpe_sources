# sqlite3RunParser

- ea: `0x14006c1ac`
- end: `0x14006c51e`
- name: `sqlite3RunParser`
- size: `882`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: ``

## callers

- `0x140043994`
- `0x14006348c`
- `0x140069cec`
- `0x140089cf0`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140027ba8`
- `0x14002fccc`
- `0x140054038`
- `0x140054f4c`
- `0x140056018`
- `0x1400560c4`
- `0x14005ec2c`
- `0x140062bfc`
- `0x140065c88`
- `0x14006c1ac`
- `0x14008ac90`
- `0x14008b740`
- `0x1400a3e24`

## string_xrefs

- `0x14006c3cf`: `unrecognized token: "%T"`

## pseudocode

```c
__int64 __fastcall sqlite3RunParser(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // rdi
  int v5; // esi
  int v6; // r12d
  __int64 v7; // r13
  __int64 v8; // rdx
  unsigned int v9; // r15d
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int Token; // eax
  __int64 v14; // rcx
  const char *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // esi
  const char *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  bool v22; // zf
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v26[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v27; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v29[594]; // [rsp+50h] [rbp-B0h] BYREF
  char v30; // [rsp+998h] [rbp+898h] BYREF
  char *v31; // [rsp+9B0h] [rbp+8B0h]

  v2 = *a1;
  v26[0] = 0;
  v5 = -1;
  memset_0(v28, 0, 0x978u);
  v6 = *(_DWORD *)(v2 + 140);
  if ( !*(_DWORD *)(v2 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v28[0] = v29;
  v31 = &v30;
  a1[42] = (__int64)a2;
  v28[1] = a1;
  v29[0] = 0;
  v7 = *(_QWORD *)(v2 + 352);
  *(_QWORD *)(v2 + 352) = a1;
  while ( 1 )
  {
    while ( 1 )
    {
      Token = sqlite3GetToken(a2, v26);
      v6 -= Token;
      v9 = Token;
      if ( v6 < 0 )
      {
        *((_DWORD *)a1 + 6) = 18;
LABEL_35:
        ++*((_DWORD *)a1 + 12);
        goto LABEL_39;
      }
      v8 = (unsigned int)v26[0];
      if ( v26[0] >= 164 )
        break;
LABEL_31:
      a1[35] = (__int64)a2;
      *((_DWORD *)a1 + 72) = v9;
      v27 = *(_OWORD *)(a1 + 35);
      sqlite3Parser(v28, v8, &v27);
      a2 += (int)v9;
      if ( *((_DWORD *)a1 + 6) )
        goto LABEL_39;
      v5 = v26[0];
    }
    if ( *(_DWORD *)(v2 + 408) )
    {
      *((_DWORD *)a1 + 6) = 9;
      goto LABEL_35;
    }
    if ( v26[0] != 183 )
      break;
    a2 += (int)Token;
  }
  if ( !*a2 )
  {
    if ( v5 == 1 )
    {
      v8 = 0;
    }
    else
    {
      if ( !v5 )
        goto LABEL_39;
      v8 = 1;
    }
    v9 = 0;
    goto LABEL_30;
  }
  switch ( v26[0] )
  {
    case 164:
      *(_QWORD *)&v27 = a2 + 6;
      if ( (unsigned int)getToken(&v27) == 59 )
      {
        v10 = getToken(&v27);
        v8 = 164;
        if ( v10 != 24 )
          v8 = 59;
        goto LABEL_30;
      }
      goto LABEL_16;
    case 165:
      *(_QWORD *)&v27 = a2 + 4;
      if ( v5 == 23 )
      {
        v11 = getToken(&v27);
        if ( v11 == 22 || v11 == 59 )
        {
          v8 = 165;
          goto LABEL_30;
        }
      }
LABEL_16:
      v8 = 59;
LABEL_30:
      v26[0] = v8;
      goto LABEL_31;
    case 166:
      *(_QWORD *)&v27 = a2 + 6;
      if ( v5 != 23 || (v12 = getToken(&v27), v8 = 166, v12 != 22) )
        v8 = 59;
      goto LABEL_30;
  }
  *(_QWORD *)&v27 = a2;
  *((_QWORD *)&v27 + 1) = Token;
  sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v27);
LABEL_39:
  while ( 1 )
  {
    v14 = v28[0];
    if ( v28[0] <= (unsigned __int64)v29 )
      break;
    v28[0] -= 24LL;
    yy_destructor(v28, *(unsigned __int16 *)(v14 + 2), v14 + 8);
  }
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v15 = (const char *)a1[1];
  if ( v15 )
  {
LABEL_46:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v15, (const char *)a1[42]);
    v17 = 1;
  }
  else
  {
    v16 = *((unsigned int *)a1 + 6);
    v17 = 0;
    if ( (_DWORD)v16 && (_DWORD)v16 != 101 )
    {
      v18 = (const char *)sqlite3ErrStr(v16);
      v15 = (const char *)sqlite3MPrintf(v2, "%s", v18);
      a1[1] = (__int64)v15;
      goto LABEL_46;
    }
  }
  v19 = a1[49];
  a1[42] = (__int64)a2;
  sqlite3_free(v19);
  v21 = a1[43];
  if ( v21 )
  {
    if ( !*((_BYTE *)a1 + 300) )
    {
      if ( *(_QWORD *)(v2 + 776) || (v22 = *(_DWORD *)(v21 + 44) == 1, --*(_DWORD *)(v21 + 44), v22) )
        deleteTable(v2, v21, v20);
    }
  }
  v23 = a1[45];
  if ( v23 && *((_BYTE *)a1 + 300) < 2u )
    sqlite3DeleteTrigger(v2, v23);
  v24 = a1[40];
  if ( v24 )
    sqlite3DbNNFreeNN(v2, v24);
  *(_QWORD *)(v2 + 352) = v7;
  return v17;
}

```

## disassembly

```asm
0x14006c1ac  mov     [rsp-8+arg_10], rbx
0x14006c1b1  push    rbp
0x14006c1b2  push    rsi
0x14006c1b3  push    rdi
0x14006c1b4  push    r12
0x14006c1b6  push    r13
0x14006c1b8  push    r14
0x14006c1ba  push    r15
0x14006c1bc  lea     rbp, [rsp-8D0h]
0x14006c1c4  sub     rsp, 9D0h
0x14006c1cb  mov     rax, cs:__security_cookie
0x14006c1d2  xor     rax, rsp
0x14006c1d5  mov     [rbp+900h+var_40], rax
0x14006c1dc  mov     rdi, [rcx]
0x14006c1df  mov     r14, rdx
0x14006c1e2  mov     rbx, rcx
0x14006c1e5  xor     r15d, r15d
0x14006c1e8  xor     edx, edx; Val
0x14006c1ea  mov     [rsp+0A00h+var_9E0], r15d
0x14006c1ef  lea     rcx, [rsp+0A00h+var_9C0]; void *
0x14006c1f4  mov     r8d, 978h; Size
0x14006c1fa  or      esi, 0FFFFFFFFh
0x14006c1fd  call    memset_0
0x14006c202  mov     r12d, [rdi+8Ch]
0x14006c209  cmp     [rdi+0D8h], r15d
0x14006c210  jnz     short loc_14006C219
0x14006c212  mov     [rdi+198h], r15d
0x14006c219  lea     rax, [rsp+0A00h+var_9B0]
0x14006c21e  mov     [rbx+18h], r15d
0x14006c222  mov     [rsp+0A00h+var_9C0], rax
0x14006c227  lea     rax, [rbp+900h+var_68]
0x14006c22e  mov     [rbp+900h+var_50], rax
0x14006c235  mov     [rbx+150h], r14
0x14006c23c  mov     [rsp+0A00h+var_9B8], rbx
0x14006c241  mov     [rsp+0A00h+var_9B0], r15d
0x14006c246  mov     r13, [rdi+160h]
0x14006c24d  mov     [rdi+160h], rbx
0x14006c254  jmp     loc_14006C39D
0x14006c259  mov     edx, [rsp+0A00h+var_9E0]
0x14006c25d  cmp     edx, 0A4h
0x14006c263  jl      loc_14006C363
0x14006c269  mov     eax, [rdi+198h]
0x14006c26f  test    eax, eax
0x14006c271  jnz     loc_14006C3EA
0x14006c277  mov     eax, [rsp+0A00h+var_9E0]
0x14006c27b  cmp     eax, 0B7h
0x14006c280  jnz     short loc_14006C28D
0x14006c282  movsxd  rax, r15d
0x14006c285  add     r14, rax
0x14006c288  jmp     loc_14006C39D
0x14006c28d  cmp     byte ptr [r14], 0
0x14006c291  jnz     short loc_14006C2B1
0x14006c293  cmp     esi, 1
0x14006c296  jnz     short loc_14006C29C
0x14006c298  xor     edx, edx
0x14006c29a  jmp     short loc_14006C2A9
0x14006c29c  test    esi, esi
0x14006c29e  jz      loc_14006C40E
0x14006c2a4  mov     edx, 1
0x14006c2a9  xor     r15d, r15d
0x14006c2ac  jmp     loc_14006C35F
0x14006c2b1  cmp     eax, 0A4h
0x14006c2b6  jnz     short loc_14006C2F2
0x14006c2b8  lea     rax, [r14+6]
0x14006c2bc  lea     rcx, [rsp+0A00h+var_9D0]
0x14006c2c1  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x14006c2c6  call    getToken
0x14006c2cb  mov     esi, 3Bh ; ';'
0x14006c2d0  cmp     eax, esi
0x14006c2d2  jz      short loc_14006C2DB
0x14006c2d4  mov     edx, esi
0x14006c2d6  jmp     loc_14006C35F
0x14006c2db  lea     rcx, [rsp+0A00h+var_9D0]
0x14006c2e0  call    getToken
0x14006c2e5  cmp     eax, 18h
0x14006c2e8  mov     edx, 0A4h
0x14006c2ed  cmovnz  edx, esi
0x14006c2f0  jmp     short loc_14006C35F
0x14006c2f2  cmp     eax, 0A5h
0x14006c2f7  jnz     short loc_14006C32D
0x14006c2f9  lea     rax, [r14+4]
0x14006c2fd  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x14006c302  cmp     esi, 17h
0x14006c305  jnz     short loc_14006C326
0x14006c307  lea     rcx, [rsp+0A00h+var_9D0]
0x14006c30c  call    getToken
0x14006c311  cmp     eax, 16h
0x14006c314  jz      short loc_14006C31F
0x14006c316  mov     esi, 3Bh ; ';'
0x14006c31b  cmp     eax, esi
0x14006c31d  jnz     short loc_14006C2D4
0x14006c31f  mov     edx, 0A5h
0x14006c324  jmp     short loc_14006C35F
0x14006c326  mov     esi, 3Bh ; ';'
0x14006c32b  jmp     short loc_14006C2D4
0x14006c32d  cmp     eax, 0A6h
0x14006c332  jnz     loc_14006C3C2
0x14006c338  lea     rax, [r14+6]
0x14006c33c  mov     qword ptr [rsp+0A00h+var_9D0], rax
0x14006c341  cmp     esi, 17h
0x14006c344  jnz     short loc_14006C35A
0x14006c346  lea     rcx, [rsp+0A00h+var_9D0]
0x14006c34b  call    getToken
0x14006c350  mov     edx, 0A6h
0x14006c355  cmp     eax, 16h
0x14006c358  jz      short loc_14006C35F
0x14006c35a  mov     edx, 3Bh ; ';'
0x14006c35f  mov     [rsp+0A00h+var_9E0], edx
0x14006c363  mov     [rbx+118h], r14
0x14006c36a  lea     r8, [rsp+0A00h+var_9D0]
0x14006c36f  mov     [rbx+120h], r15d
0x14006c376  lea     rcx, [rsp+0A00h+var_9C0]
0x14006c37b  movups  xmm0, xmmword ptr [rbx+118h]
0x14006c382  movdqu  [rsp+0A00h+var_9D0], xmm0
0x14006c388  call    sqlite3Parser
0x14006c38d  movsxd  rax, r15d
0x14006c390  add     r14, rax
0x14006c393  cmp     dword ptr [rbx+18h], 0
0x14006c397  jnz     short loc_14006C40E
0x14006c399  mov     esi, [rsp+0A00h+var_9E0]
0x14006c39d  lea     rdx, [rsp+0A00h+var_9E0]
0x14006c3a2  mov     rcx, r14
0x14006c3a5  call    sqlite3GetToken
0x14006c3aa  sub     r12d, eax
0x14006c3ad  mov     r15d, eax
0x14006c3b0  jns     loc_14006C259
0x14006c3b6  mov     dword ptr [rbx+18h], 12h
0x14006c3bd  inc     dword ptr [rbx+30h]
0x14006c3c0  jmp     short loc_14006C40E
0x14006c3c2  lea     r8, [rsp+0A00h+var_9D0]
0x14006c3c7  mov     dword ptr [rsp+0A00h+var_9D0+0Ch], 0
0x14006c3cf  lea     rdx, aUnrecognizedTo; "unrecognized token: \"%T\""
0x14006c3d6  mov     qword ptr [rsp+0A00h+var_9D0], r14
0x14006c3db  mov     rcx, rbx
0x14006c3de  mov     dword ptr [rsp+0A00h+var_9D0+8], r15d
0x14006c3e3  call    sqlite3ErrorMsg
0x14006c3e8  jmp     short loc_14006C40E
0x14006c3ea  mov     dword ptr [rbx+18h], 9
0x14006c3f1  jmp     short loc_14006C3BD
0x14006c3f3  lea     rax, [rcx-18h]
0x14006c3f7  mov     [rsp+0A00h+var_9C0], rax
0x14006c3fc  lea     r8, [rcx+8]
0x14006c400  movzx   edx, word ptr [rcx+2]
0x14006c404  lea     rcx, [rsp+0A00h+var_9C0]
0x14006c409  call    yy_destructor
0x14006c40e  mov     rcx, [rsp+0A00h+var_9C0]
0x14006c413  lea     rax, [rsp+0A00h+var_9B0]
0x14006c418  cmp     rcx, rax
0x14006c41b  ja      short loc_14006C3F3
0x14006c41d  cmp     byte ptr [rdi+67h], 0
0x14006c421  jz      short loc_14006C42A
0x14006c423  mov     dword ptr [rbx+18h], 7
0x14006c42a  mov     rax, [rbx+8]
0x14006c42e  test    rax, rax
0x14006c431  jnz     short loc_14006C45C
0x14006c433  mov     ecx, [rbx+18h]
0x14006c436  xor     esi, esi
0x14006c438  test    ecx, ecx
0x14006c43a  jz      short loc_14006C47A
0x14006c43c  cmp     ecx, 65h ; 'e'
0x14006c43f  jz      short loc_14006C47A
0x14006c441  call    sqlite3ErrStr
0x14006c446  mov     r8, rax
0x14006c449  lea     rdx, aS_6; "%s"
0x14006c450  mov     rcx, rdi
0x14006c453  call    sqlite3MPrintf
0x14006c458  mov     [rbx+8], rax
0x14006c45c  mov     r9, [rbx+150h]
0x14006c463  lea     rdx, aSInS; "%s in \"%s\""
0x14006c46a  mov     ecx, [rbx+18h]
0x14006c46d  mov     r8, rax
0x14006c470  call    sqlite3_log
0x14006c475  mov     esi, 1
0x14006c47a  mov     rcx, [rbx+188h]
0x14006c481  mov     [rbx+150h], r14
0x14006c488  call    sqlite3_free
0x14006c48d  mov     rdx, [rbx+158h]
0x14006c494  test    rdx, rdx
0x14006c497  jz      short loc_14006C4BA
0x14006c499  cmp     byte ptr [rbx+12Ch], 0
0x14006c4a0  jnz     short loc_14006C4BA
0x14006c4a2  cmp     qword ptr [rdi+308h], 0
0x14006c4aa  jnz     short loc_14006C4B2
0x14006c4ac  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x14006c4b0  jnz     short loc_14006C4BA
0x14006c4b2  mov     rcx, rdi
0x14006c4b5  call    deleteTable
0x14006c4ba  mov     rdx, [rbx+168h]
0x14006c4c1  test    rdx, rdx
0x14006c4c4  jz      short loc_14006C4D7
0x14006c4c6  cmp     byte ptr [rbx+12Ch], 2
0x14006c4cd  jnb     short loc_14006C4D7
0x14006c4cf  mov     rcx, rdi
0x14006c4d2  call    sqlite3DeleteTrigger
0x14006c4d7  mov     rdx, [rbx+140h]
0x14006c4de  test    rdx, rdx
0x14006c4e1  jz      short loc_14006C4EB
0x14006c4e3  mov     rcx, rdi
0x14006c4e6  call    sqlite3DbNNFreeNN
0x14006c4eb  mov     [rdi+160h], r13
0x14006c4f2  mov     eax, esi
0x14006c4f4  mov     rcx, [rbp+900h+var_40]
0x14006c4fb  xor     rcx, rsp; StackCookie
0x14006c4fe  call    __security_check_cookie
0x14006c503  mov     rbx, [rsp+0A00h+arg_10]
0x14006c50b  add     rsp, 9D0h
0x14006c512  pop     r15
0x14006c514  pop     r14
0x14006c516  pop     r13
0x14006c518  pop     r12
0x14006c51a  pop     rdi
0x14006c51b  pop     rsi
0x14006c51c  pop     rbp
0x14006c51d  retn
```
