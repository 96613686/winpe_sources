# sqlite3FinishTrigger

- ea: `0x14005b440`
- end: `0x14005b722`
- name: `sqlite3FinishTrigger`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x1400a40bc`

## callees

- `0x1400026c0`
- `0x14002c1b8`
- `0x14004c754`
- `0x140050530`
- `0x140053e3c`
- `0x1400541ec`
- `0x140054f4c`
- `0x140054fcc`
- `0x1400560c4`
- `0x14005b440`
- `0x14005b728`
- `0x14005b824`
- `0x14005f5fc`
- `0x14005f79c`
- `0x140062bfc`
- `0x14006348c`
- `0x1400636dc`
- `0x14006a9c0`
- `0x14006f318`
- `0x140073b00`
- `0x14007ff8c`

## string_xrefs

- `0x14005b6ba`: `trigger "%s" may not write to shadow table "%s"`
- `0x14005b622`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  __int64 v8; // rcx
  int v9; // r15d
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  _BYTE *v17; // r14
  __int64 i; // rbp
  __int64 v19; // rdx
  __int64 Vdbe; // rbp
  __int64 v21; // r12
  __int64 v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int128 v27; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v28[8]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v29[160]; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+F0h] [rbp+8h]

  v3 = a1[45];
  v5 = *a1;
  memset_0(v28, 0, 0x60u);
  v27 = 0;
  a1[45] = 0;
  if ( !*((_DWORD *)a1 + 12) && v3 )
  {
    v8 = *(_QWORD *)(v3 + 40);
    v9 = -32768;
    v10 = *(_QWORD *)v3;
    v30 = *(_QWORD *)v3;
    if ( v8 )
    {
      v11 = *(_QWORD *)(v5 + 32);
      v9 = 0;
      if ( *(_QWORD *)(v11 + 24) != v8 )
      {
        do
          ++v9;
        while ( *(_QWORD *)(32LL * v9 + v11 + 24) != v8 );
      }
    }
    *(_QWORD *)(v3 + 56) = a2;
    while ( a2 )
    {
      *(_QWORD *)(a2 + 8) = v3;
      a2 = *(_QWORD *)(a2 + 80);
    }
    v12 = *(_QWORD *)v3;
    *(_QWORD *)&v27 = v12;
    if ( v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_BYTE *)(v12 + v14) );
      v13 = v14 & 0x3FFFFFFF;
    }
    else
    {
      v13 = 0;
    }
    DWORD2(v27) = v13;
    sqlite3FixInit((unsigned int)v28, (_DWORD)a1, v9, (unsigned int)"trigger", (__int64)&v27);
    if ( !(unsigned int)sqlite3FixTriggerStep(v28, *(_QWORD *)(v3 + 56)) )
    {
      v16 = *(_QWORD *)(v3 + 24);
      if ( !v16 || !(unsigned int)sqlite3WalkExprNN(v29, v16, v15) )
      {
        if ( *((_BYTE *)a1 + 300) >= 2u )
        {
          a1[45] = v3;
          v3 = 0;
          v17 = (_BYTE *)(v5 + 197);
          goto LABEL_30;
        }
        v17 = (_BYTE *)(v5 + 197);
        if ( *(_BYTE *)(v5 + 197) )
        {
LABEL_31:
          v23 = (_QWORD *)v3;
          v3 = sqlite3HashInsert(*(_QWORD *)(32LL * v9 + *(_QWORD *)(v5 + 32) + 24) + 56LL, v10, v3);
          if ( v3 )
          {
            sqlite3OomFault(v5);
          }
          else
          {
            v24 = v23[6];
            if ( v23[5] == v24 )
            {
              v25 = *(_QWORD *)(findElementWithHash(v24 + 8, v23[1], 0) + 16);
              v23[8] = *(_QWORD *)(v25 + 88);
              *(_QWORD *)(v25 + 88) = v23;
            }
          }
          goto LABEL_36;
        }
        if ( (unsigned int)sqlite3ReadOnlyShadowTables(v5) )
        {
          for ( i = *(_QWORD *)(v3 + 56); i; i = *(_QWORD *)(i + 80) )
          {
            v19 = *(_QWORD *)(i + 24);
            if ( v19 && (unsigned int)sqlite3ShadowTableName(v5, v19) )
            {
              sqlite3ErrorMsg(
                a1,
                "trigger \"%s\" may not write to shadow table \"%s\"",
                *(const char **)v3,
                *(const char **)(i + 24));
              goto LABEL_36;
            }
          }
        }
        Vdbe = sqlite3GetVdbe(a1);
        if ( Vdbe )
        {
          sqlite3BeginWriteOperation(a1, 0, (unsigned int)v9);
          v21 = sqlite3DbStrNDup(v5, *(_QWORD *)a3, *(unsigned int *)(a3 + 8));
          sqlite3NestedParse(
            a1,
            "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
            *(_QWORD *)(32LL * v9 + *(_QWORD *)(v5 + 32)),
            v30,
            *(_QWORD *)(v3 + 8),
            v21,
            (_QWORD)v27);
          if ( v21 )
            sqlite3DbFreeNN(v5);
          sqlite3ChangeCookie(a1, (unsigned int)v9);
          v22 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v30);
          sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v9, v22, 0);
          v10 = v30;
LABEL_30:
          if ( !*v17 )
            goto LABEL_36;
          goto LABEL_31;
        }
      }
    }
  }
LABEL_36:
  sqlite3DeleteTrigger(v5, v3);
  return sqlite3DeleteTriggerStep(v5, a2);
}

```

## disassembly

```asm
0x14005b440  push    rbx
0x14005b442  push    rbp
0x14005b443  push    rsi
0x14005b444  push    rdi
0x14005b445  push    r12
0x14005b447  push    r13
0x14005b449  push    r14
0x14005b44b  push    r15
0x14005b44d  sub     rsp, 0A8h
0x14005b454  mov     rdi, [rcx+168h]
0x14005b45b  mov     r13, rdx
0x14005b45e  mov     rsi, [rcx]
0x14005b461  xor     edx, edx; Val
0x14005b463  mov     r12, r8
0x14005b466  mov     rbx, rcx
0x14005b469  lea     rcx, [rsp+0E8h+var_A8]; void *
0x14005b46e  lea     r8d, [rdx+60h]; Size
0x14005b472  call    memset_0
0x14005b477  xor     r14d, r14d
0x14005b47a  xorps   xmm0, xmm0
0x14005b47d  movups  [rsp+0E8h+var_B8], xmm0
0x14005b482  mov     [rbx+168h], r14
0x14005b489  cmp     [rbx+30h], r14d
0x14005b48d  jnz     loc_14005B6F8
0x14005b493  test    rdi, rdi
0x14005b496  jz      loc_14005B6F8
0x14005b49c  mov     rcx, [rdi+28h]
0x14005b4a0  mov     r15d, 0FFFF8000h
0x14005b4a6  mov     rbp, [rdi]
0x14005b4a9  mov     [rsp+0E8h+arg_0], rbp
0x14005b4b1  test    rcx, rcx
0x14005b4b4  jz      short loc_14005B4D4
0x14005b4b6  mov     rdx, [rsi+20h]
0x14005b4ba  mov     r15d, r14d
0x14005b4bd  cmp     [rdx+18h], rcx
0x14005b4c1  jz      short loc_14005B4D4
0x14005b4c3  inc     r15d
0x14005b4c6  movsxd  rax, r15d
0x14005b4c9  shl     rax, 5
0x14005b4cd  cmp     [rax+rdx+18h], rcx
0x14005b4d2  jnz     short loc_14005B4C3
0x14005b4d4  mov     [rdi+38h], r13
0x14005b4d8  jmp     short loc_14005B4E2
0x14005b4da  mov     [r13+8], rdi
0x14005b4de  mov     r13, [r13+50h]
0x14005b4e2  test    r13, r13
0x14005b4e5  jnz     short loc_14005B4DA
0x14005b4e7  mov     rcx, [rdi]
0x14005b4ea  mov     qword ptr [rsp+0E8h+var_B8], rcx
0x14005b4ef  test    rcx, rcx
0x14005b4f2  jnz     short loc_14005B4F9
0x14005b4f4  mov     eax, r14d
0x14005b4f7  jmp     short loc_14005B50B
0x14005b4f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14005b4fd  inc     rax
0x14005b500  cmp     [rcx+rax], r14b
0x14005b504  jnz     short loc_14005B4FD
0x14005b506  and     eax, 3FFFFFFFh
0x14005b50b  mov     dword ptr [rsp+0E8h+var_B8+8], eax
0x14005b50f  lea     r9, aTrigger; "trigger"
0x14005b516  lea     rax, [rsp+0E8h+var_B8]
0x14005b51b  mov     r8d, r15d
0x14005b51e  mov     rdx, rbx
0x14005b521  mov     [rsp+0E8h+var_C8], rax
0x14005b526  lea     rcx, [rsp+0E8h+var_A8]
0x14005b52b  call    sqlite3FixInit
0x14005b530  mov     rdx, [rdi+38h]
0x14005b534  lea     rcx, [rsp+0E8h+var_A8]
0x14005b539  call    sqlite3FixTriggerStep
0x14005b53e  test    eax, eax
0x14005b540  jnz     loc_14005B6F8
0x14005b546  mov     rdx, [rdi+18h]
0x14005b54a  test    rdx, rdx
0x14005b54d  jz      short loc_14005B561
0x14005b54f  lea     rcx, [rsp+0E8h+var_A0]
0x14005b554  call    sqlite3WalkExprNN
0x14005b559  test    eax, eax
0x14005b55b  jnz     loc_14005B6F8
0x14005b561  cmp     byte ptr [rbx+12Ch], 2
0x14005b568  jb      short loc_14005B580
0x14005b56a  mov     [rbx+168h], rdi
0x14005b571  mov     rdi, r14
0x14005b574  lea     r14, [rsi+0C5h]
0x14005b57b  jmp     loc_14005B67C
0x14005b580  lea     r14, [rsi+0C5h]
0x14005b587  cmp     byte ptr [r14], 0
0x14005b58b  jnz     loc_14005B682
0x14005b591  mov     rcx, rsi
0x14005b594  call    sqlite3ReadOnlyShadowTables
0x14005b599  test    eax, eax
0x14005b59b  jz      short loc_14005B5C5
0x14005b59d  mov     rbp, [rdi+38h]
0x14005b5a1  jmp     short loc_14005B5C0
0x14005b5a3  mov     rdx, [rbp+18h]
0x14005b5a7  test    rdx, rdx
0x14005b5aa  jz      short loc_14005B5BC
0x14005b5ac  mov     rcx, rsi
0x14005b5af  call    sqlite3ShadowTableName
0x14005b5b4  test    eax, eax
0x14005b5b6  jnz     loc_14005B6B6
0x14005b5bc  mov     rbp, [rbp+50h]
0x14005b5c0  test    rbp, rbp
0x14005b5c3  jnz     short loc_14005B5A3
0x14005b5c5  mov     rcx, rbx
0x14005b5c8  call    sqlite3GetVdbe
0x14005b5cd  mov     rbp, rax
0x14005b5d0  test    rax, rax
0x14005b5d3  jz      loc_14005B6F8
0x14005b5d9  mov     r8d, r15d
0x14005b5dc  xor     edx, edx
0x14005b5de  mov     rcx, rbx
0x14005b5e1  call    sqlite3BeginWriteOperation
0x14005b5e6  mov     r8d, [r12+8]
0x14005b5eb  mov     rcx, rsi
0x14005b5ee  mov     rdx, [r12]
0x14005b5f2  call    sqlite3DbStrNDup
0x14005b5f7  mov     rcx, [rdi+8]
0x14005b5fb  mov     r12, rax
0x14005b5fe  mov     r8, [rsi+20h]
0x14005b602  mov     r9, [rsp+0E8h+arg_0]
0x14005b60a  mov     [rsp+0E8h+var_C0], rax
0x14005b60f  mov     [rsp+0E8h+var_C8], rcx
0x14005b614  mov     rcx, rbx
0x14005b617  movsxd  rdx, r15d
0x14005b61a  shl     rdx, 5
0x14005b61e  mov     r8, [rdx+r8]
0x14005b622  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x14005b629  call    sqlite3NestedParse
0x14005b62e  test    r12, r12
0x14005b631  jz      short loc_14005B63E
0x14005b633  mov     rdx, r12
0x14005b636  mov     rcx, rsi
0x14005b639  call    sqlite3DbFreeNN
0x14005b63e  mov     edx, r15d
0x14005b641  mov     rcx, rbx
0x14005b644  call    sqlite3ChangeCookie
0x14005b649  mov     r8, [rsp+0E8h+arg_0]
0x14005b651  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x14005b658  mov     rcx, rsi
0x14005b65b  xor     ebx, ebx
0x14005b65d  call    sqlite3MPrintf
0x14005b662  mov     r8, rax
0x14005b665  movzx   r9d, bx
0x14005b669  mov     edx, r15d
0x14005b66c  mov     rcx, rbp
0x14005b66f  call    sqlite3VdbeAddParseSchemaOp
0x14005b674  mov     rbp, [rsp+0E8h+arg_0]
0x14005b67c  cmp     byte ptr [r14], 0
0x14005b680  jz      short loc_14005B6F8
0x14005b682  mov     rax, [rsi+20h]
0x14005b686  mov     r8, rdi
0x14005b689  movsxd  rcx, r15d
0x14005b68c  mov     rdx, rbp
0x14005b68f  shl     rcx, 5
0x14005b693  mov     rbx, rdi
0x14005b696  mov     rcx, [rcx+rax+18h]
0x14005b69b  add     rcx, 38h ; '8'
0x14005b69f  call    sqlite3HashInsert
0x14005b6a4  mov     rdi, rax
0x14005b6a7  test    rax, rax
0x14005b6aa  jz      short loc_14005B6CE
0x14005b6ac  mov     rcx, rsi
0x14005b6af  call    sqlite3OomFault
0x14005b6b4  jmp     short loc_14005B6F8
0x14005b6b6  mov     r9, [rbp+18h]
0x14005b6ba  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x14005b6c1  mov     r8, [rdi]
0x14005b6c4  mov     rcx, rbx
0x14005b6c7  call    sqlite3ErrorMsg
0x14005b6cc  jmp     short loc_14005B6F8
0x14005b6ce  mov     rcx, [rbx+30h]
0x14005b6d2  cmp     [rbx+28h], rcx
0x14005b6d6  jnz     short loc_14005B6F8
0x14005b6d8  mov     rdx, [rbx+8]
0x14005b6dc  add     rcx, 8
0x14005b6e0  xor     r8d, r8d
0x14005b6e3  call    findElementWithHash
0x14005b6e8  mov     rdx, [rax+10h]
0x14005b6ec  mov     rax, [rdx+58h]
0x14005b6f0  mov     [rbx+40h], rax
0x14005b6f4  mov     [rdx+58h], rbx
0x14005b6f8  mov     rdx, rdi
0x14005b6fb  mov     rcx, rsi
0x14005b6fe  call    sqlite3DeleteTrigger
0x14005b703  mov     rdx, r13
0x14005b706  mov     rcx, rsi
0x14005b709  call    sqlite3DeleteTriggerStep
0x14005b70e  add     rsp, 0A8h
0x14005b715  pop     r15
0x14005b717  pop     r14
0x14005b719  pop     r13
0x14005b71b  pop     r12
0x14005b71d  pop     rdi
0x14005b71e  pop     rsi
0x14005b71f  pop     rbp
0x14005b720  pop     rbx
0x14005b721  retn
```
