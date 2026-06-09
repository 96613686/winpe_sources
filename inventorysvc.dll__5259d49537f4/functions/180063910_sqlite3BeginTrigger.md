# sqlite3BeginTrigger

- ea: `0x180063910`
- end: `0x180063e3c`
- name: `sqlite3BeginTrigger`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x1800bb79c`

## callees

- `0x1800038b8`
- `0x180042198`
- `0x1800438b8`
- `0x1800634ac`
- `0x180063910`
- `0x180067c64`
- `0x180068dbc`
- `0x18006b52c`
- `0x18006b6dc`
- `0x18006b868`
- `0x18006c63c`
- `0x18006d7b4`
- `0x18007073c`
- `0x180072e18`
- `0x180072e9c`
- `0x180077130`
- `0x18007ab4c`
- `0x180086da0`
- `0x180087204`
- `0x1800886c0`
- `0x1800a6210`

## string_xrefs

- `0x180063ca4`: `sqlite_temp_master`
- `0x180063974`: `temporary trigger may not have qualified name`
- `0x180063b3c`: `trigger %T already exists`
- `0x180063a95`: `cannot create triggers on virtual tables`
- `0x180063b94`: `cannot create trigger on system table`
- `0x180063bd5`: `cannot create %s trigger on view: %S`
- `0x180063bf7`: `cannot create INSTEAD OF trigger on table: %S`

## pseudocode

```c
__int64 __fastcall sqlite3BeginTrigger(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 v10; // rbx
  __int64 *v11; // r14
  __int64 v15; // rsi
  __int64 v16; // rbp
  unsigned int v17; // r14d
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rax
  const char *v22; // r8
  __int64 v23; // rcx
  int v24; // r12d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // edx
  const char *v29; // r8
  int v30; // eax
  __int64 *v31; // rax
  __int64 *v32; // r12
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 *i; // rax
  __int64 result; // rax
  __int64 v38; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-A0h]
  _BYTE v40[152]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v42; // [rsp+118h] [rbp+40h]
  int v43; // [rsp+120h] [rbp+48h]

  v10 = *a1;
  v11 = 0;
  v38 = 0;
  memset_0(v40, 0, 0x60u);
  if ( a9 )
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      v15 = a8;
      v16 = a6;
      goto LABEL_78;
    }
    v17 = 1;
  }
  else
  {
    v17 = sqlite3TwoPartName(a1, a2, a3, &v38);
    if ( (v17 & 0x80000000) != 0 )
    {
LABEL_76:
      v15 = a8;
      v16 = a6;
      goto LABEL_77;
    }
    a2 = v38;
  }
  if ( !a7 || *(_BYTE *)(v10 + 103) )
    goto LABEL_76;
  if ( *(_BYTE *)(v10 + 197) && v17 != 1 )
  {
    if ( *(_QWORD *)(a7 + 16) )
      sqlite3DbFreeNN(v10);
    *(_QWORD *)(a7 + 16) = 0;
  }
  v18 = sqlite3SrcListLookup(a1, a7);
  if ( !*(_BYTE *)(v10 + 197)
    && !*(_DWORD *)(a3 + 8)
    && v18
    && *(_QWORD *)(v18 + 96) == *(_QWORD *)(*(_QWORD *)(v10 + 32) + 56LL) )
  {
    v17 = 1;
  }
  if ( *(_BYTE *)(v10 + 103) )
    goto LABEL_76;
  sqlite3FixInit((unsigned int)v40, (_DWORD)a1, v17, (unsigned int)"trigger", a2);
  if ( (unsigned int)sqlite3FixSrcList(v40, a7) )
    goto LABEL_76;
  v16 = a6;
  v15 = a8;
  v19 = 0;
  v20 = sqlite3SrcListLookup(a1, a7);
  v42 = v20;
  if ( !v20 )
    goto LABEL_24;
  if ( *(_BYTE *)(v20 + 63) == 1 )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
    goto LABEL_24;
  }
  v21 = sqlite3NameFromToken(v10, a2);
  v19 = v21;
  if ( !v21 )
  {
LABEL_77:
    v11 = 0;
    goto LABEL_78;
  }
  if ( (unsigned int)sqlite3CheckObjectName(a1, v21, "trigger", *(_QWORD *)v42) )
    goto LABEL_34;
  if ( *((_BYTE *)a1 + 300) < 2u
    && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v17 + *(_QWORD *)(v10 + 32) + 24) + 56LL, v19, 0) + 16) )
  {
    if ( a10 )
      sqlite3CodeVerifySchema(a1, v17);
    else
      sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
    goto LABEL_34;
  }
  v38 = *(_QWORD *)v42;
  if ( !(unsigned int)sqlite3_strnicmp(v38, "sqlite_", 7) )
  {
    sqlite3ErrorMsg(a1, "cannot create trigger on system table");
    goto LABEL_34;
  }
  if ( *(_BYTE *)(v42 + 63) != 2 )
  {
    if ( a4 == 65 )
    {
      sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
      goto LABEL_24;
    }
    goto LABEL_46;
  }
  if ( a4 == 65 )
  {
LABEL_46:
    if ( *((_BYTE *)a1 + 300) >= 2u )
      goto LABEL_60;
    v23 = *(_QWORD *)(v42 + 96);
    v24 = -32768;
    if ( v23 )
    {
      v25 = *(_QWORD *)(v10 + 32);
      v24 = 0;
      if ( *(_QWORD *)(v25 + 24) != v23 )
      {
        do
          ++v24;
        while ( *(_QWORD *)(32LL * v24 + v25 + 24) != v23 );
      }
    }
    v26 = *(_QWORD *)(v10 + 32);
    v27 = *(_QWORD *)(32LL * v24 + v26);
    v39 = v27;
    if ( a9 )
      v27 = *(_QWORD *)(v26 + 32);
    v28 = v24 == 1 || a9 ? 5 : 7;
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v28, v19, v38, v27) )
    {
      v29 = "sqlite_temp_master";
      if ( v24 != 1 )
        v29 = "sqlite_master";
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v29, 0, v39) )
      {
LABEL_60:
        v30 = 33;
        if ( a4 != 65 )
          v30 = a4;
        v43 = v30;
        v31 = (__int64 *)sqlite3DbMallocZero(v10, 72);
        v32 = v31;
        if ( v31 )
        {
          *v31 = v19;
          v33 = sqlite3DbStrDup(v10, *(_QWORD *)(a7 + 24));
          v32[1] = v33;
          v34 = v33;
          v32[5] = *(_QWORD *)(32LL * v17 + *(_QWORD *)(v10 + 32) + 24);
          v32[6] = *(_QWORD *)(v42 + 96);
          *((_BYTE *)v32 + 16) = a5;
          *((_BYTE *)v32 + 17) = (v43 != 33) + 1;
          if ( *((_BYTE *)a1 + 300) < 2u )
          {
            if ( v15 )
              v35 = exprDup(v10, v15, 1);
            else
              v35 = 0;
          }
          else
          {
            v35 = v15;
            for ( i = (__int64 *)a1[51]; i; i = (__int64 *)i[3] )
            {
              if ( *i == *(_QWORD *)(a7 + 24) )
              {
                *i = v34;
                break;
              }
            }
            v15 = 0;
          }
          v32[3] = v35;
          v11 = v32;
          v32[4] = a6;
          v16 = 0;
          a1[45] = (__int64)v32;
          goto LABEL_78;
        }
        v11 = 0;
LABEL_35:
        sqlite3DbFreeNN(v10);
        goto LABEL_78;
      }
    }
LABEL_34:
    v11 = 0;
    goto LABEL_35;
  }
  v22 = "BEFORE";
  if ( a4 != 33 )
    v22 = "AFTER";
  sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v22, (const wchar_t *)(a7 + 8));
LABEL_24:
  if ( *(_BYTE *)(v10 + 196) == 1 )
    *(_DWORD *)(v10 + 200) |= 1u;
  v11 = 0;
  if ( v19 )
    goto LABEL_35;
LABEL_78:
  sqlite3SrcListDelete(v10, a7);
  result = sqlite3IdListDelete(v10, v16);
  if ( v15 )
    result = sqlite3ExprDeleteNN(v10, v15);
  if ( !a1[45] )
    return sqlite3DeleteTrigger(v10, v11);
  return result;
}

```

## disassembly

```asm
0x180063910  mov     [rsp+arg_8], rbx
0x180063915  mov     [rsp+arg_18], r9d
0x18006391a  push    rbp
0x18006391b  push    rsi
0x18006391c  push    rdi
0x18006391d  push    r12
0x18006391f  push    r13
0x180063921  push    r14
0x180063923  push    r15
0x180063925  sub     rsp, 0A0h
0x18006392c  mov     rbx, [rcx]
0x18006392f  xor     r14d, r14d
0x180063932  mov     rsi, r8
0x180063935  mov     [rsp+0D8h+arg_0], r14
0x18006393d  mov     r12, rdx
0x180063940  mov     [rsp+0D8h+var_A8], r14
0x180063945  mov     rdi, rcx
0x180063948  xor     edx, edx; Val
0x18006394a  lea     r8d, [r14+60h]; Size
0x18006394e  lea     rcx, [rsp+0D8h+var_98]; void *
0x180063953  call    memset_0
0x180063958  lea     ebp, [r14+1]
0x18006395c  mov     r13, [rsp+0D8h+arg_30]
0x180063964  cmp     [rsp+0D8h+arg_40], r14d
0x18006396c  jz      short loc_18006399D
0x18006396e  cmp     [rsi+8], r14d
0x180063972  jbe     short loc_180063998
0x180063974  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18006397b  mov     rcx, rdi
0x18006397e  call    sqlite3ErrorMsg
0x180063983  mov     rsi, [rsp+0D8h+arg_38]
0x18006398b  mov     rbp, [rsp+0D8h+arg_28]
0x180063993  jmp     loc_180063DE6
0x180063998  mov     r14d, ebp
0x18006399b  jmp     short loc_1800639C0
0x18006399d  lea     r9, [rsp+0D8h+var_A8]
0x1800639a2  mov     r8, rsi
0x1800639a5  mov     rdx, r12
0x1800639a8  mov     rcx, rdi
0x1800639ab  call    sqlite3TwoPartName
0x1800639b0  mov     r14d, eax
0x1800639b3  test    eax, eax
0x1800639b5  js      loc_180063DCE
0x1800639bb  mov     r12, [rsp+0D8h+var_A8]
0x1800639c0  test    r13, r13
0x1800639c3  jz      loc_180063DCE
0x1800639c9  cmp     byte ptr [rbx+67h], 0
0x1800639cd  jnz     loc_180063DCE
0x1800639d3  cmp     byte ptr [rbx+0C5h], 0
0x1800639da  jz      short loc_1800639FA
0x1800639dc  cmp     r14d, ebp
0x1800639df  jz      short loc_1800639FA
0x1800639e1  mov     rdx, [r13+10h]
0x1800639e5  test    rdx, rdx
0x1800639e8  jz      short loc_1800639F2
0x1800639ea  mov     rcx, rbx
0x1800639ed  call    sqlite3DbFreeNN
0x1800639f2  mov     qword ptr [r13+10h], 0
0x1800639fa  mov     rdx, r13
0x1800639fd  mov     rcx, rdi
0x180063a00  call    sqlite3SrcListLookup
0x180063a05  cmp     byte ptr [rbx+0C5h], 0
0x180063a0c  jnz     short loc_180063A29
0x180063a0e  cmp     dword ptr [rsi+8], 0
0x180063a12  jnz     short loc_180063A29
0x180063a14  test    rax, rax
0x180063a17  jz      short loc_180063A29
0x180063a19  mov     rcx, [rbx+20h]
0x180063a1d  mov     rcx, [rcx+38h]
0x180063a21  cmp     [rax+60h], rcx
0x180063a25  cmovz   r14d, ebp
0x180063a29  cmp     byte ptr [rbx+67h], 0
0x180063a2d  jnz     loc_180063DCE
0x180063a33  lea     r9, aTrigger; "trigger"
0x180063a3a  mov     [rsp+0D8h+var_B8], r12
0x180063a3f  mov     r8d, r14d
0x180063a42  lea     rcx, [rsp+0D8h+var_98]
0x180063a47  mov     rdx, rdi
0x180063a4a  call    sqlite3FixInit
0x180063a4f  mov     rdx, r13
0x180063a52  lea     rcx, [rsp+0D8h+var_98]
0x180063a57  call    sqlite3FixSrcList
0x180063a5c  test    eax, eax
0x180063a5e  jnz     loc_180063DCE
0x180063a64  mov     rbp, [rsp+0D8h+arg_28]
0x180063a6c  mov     rdx, r13
0x180063a6f  mov     rsi, [rsp+0D8h+arg_38]
0x180063a77  mov     rcx, rdi
0x180063a7a  xor     r15d, r15d
0x180063a7d  call    sqlite3SrcListLookup
0x180063a82  mov     [rsp+0D8h+arg_38], rax
0x180063a8a  test    rax, rax
0x180063a8d  jz      short loc_180063AA4
0x180063a8f  cmp     byte ptr [rax+3Fh], 1
0x180063a93  jnz     short loc_180063AC5
0x180063a95  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x180063a9c  mov     rcx, rdi
0x180063a9f  call    sqlite3ErrorMsg
0x180063aa4  cmp     byte ptr [rbx+0C4h], 1
0x180063aab  jnz     short loc_180063AB4
0x180063aad  or      dword ptr [rbx+0C8h], 1
0x180063ab4  xor     r14d, r14d
0x180063ab7  test    r15, r15
0x180063aba  jz      loc_180063DE6
0x180063ac0  jmp     loc_180063B50
0x180063ac5  mov     rdx, r12
0x180063ac8  mov     rcx, rbx
0x180063acb  call    sqlite3NameFromToken
0x180063ad0  mov     r15, rax
0x180063ad3  test    rax, rax
0x180063ad6  jz      loc_180063DDE
0x180063adc  mov     rcx, [rsp+0D8h+arg_38]
0x180063ae4  lea     r8, aTrigger; "trigger"
0x180063aeb  mov     rdx, rax
0x180063aee  mov     r9, [rcx]
0x180063af1  mov     rcx, rdi
0x180063af4  call    sqlite3CheckObjectName
0x180063af9  test    eax, eax
0x180063afb  jnz     short loc_180063B48
0x180063afd  cmp     byte ptr [rdi+12Ch], 2
0x180063b04  jnb     short loc_180063B6A
0x180063b06  mov     rax, [rbx+20h]
0x180063b0a  xor     r8d, r8d
0x180063b0d  mov     ecx, r14d
0x180063b10  mov     rdx, r15
0x180063b13  shl     rcx, 5
0x180063b17  mov     rcx, [rcx+rax+18h]
0x180063b1c  add     rcx, 38h ; '8'
0x180063b20  call    findElementWithHash
0x180063b25  cmp     qword ptr [rax+10h], 0
0x180063b2a  jz      short loc_180063B6A
0x180063b2c  cmp     [rsp+0D8h+arg_48], 0
0x180063b34  mov     rcx, rdi
0x180063b37  jnz     short loc_180063B60
0x180063b39  mov     r8, r12
0x180063b3c  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x180063b43  call    sqlite3ErrorMsg
0x180063b48  mov     r14, [rsp+0D8h+arg_0]
0x180063b50  mov     rdx, r15
0x180063b53  mov     rcx, rbx
0x180063b56  call    sqlite3DbFreeNN
0x180063b5b  jmp     loc_180063DE6
0x180063b60  mov     edx, r14d
0x180063b63  call    sqlite3CodeVerifySchema
0x180063b68  jmp     short loc_180063B48
0x180063b6a  mov     r12, [rsp+0D8h+arg_38]
0x180063b72  lea     rdx, aSqlite_0; "sqlite_"
0x180063b79  mov     r8d, 7
0x180063b7f  mov     rax, [r12]
0x180063b83  mov     rcx, rax
0x180063b86  mov     [rsp+0D8h+var_A8], rax
0x180063b8b  call    sqlite3_strnicmp
0x180063b90  test    eax, eax
0x180063b92  jnz     short loc_180063BA5
0x180063b94  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x180063b9b  mov     rcx, rdi
0x180063b9e  call    sqlite3ErrorMsg
0x180063ba3  jmp     short loc_180063B48
0x180063ba5  cmp     byte ptr [r12+3Fh], 2
0x180063bab  jnz     short loc_180063BE6
0x180063bad  mov     eax, [rsp+0D8h+arg_18]
0x180063bb4  cmp     eax, 41h ; 'A'
0x180063bb7  jz      short loc_180063C08
0x180063bb9  cmp     eax, 21h ; '!'
0x180063bbc  lea     rcx, aAfter; "AFTER"
0x180063bc3  lea     r8, aBefore; "BEFORE"
0x180063bca  cmovnz  r8, rcx
0x180063bce  lea     r9, [r13+8]
0x180063bd2  mov     rcx, rdi
0x180063bd5  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x180063bdc  call    sqlite3ErrorMsg
0x180063be1  jmp     loc_180063AA4
0x180063be6  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180063bee  jnz     short loc_180063C08
0x180063bf0  lea     r8, [r13+8]
0x180063bf4  mov     rcx, rdi
0x180063bf7  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x180063bfe  call    sqlite3ErrorMsg
0x180063c03  jmp     loc_180063AA4
0x180063c08  cmp     byte ptr [rdi+12Ch], 2
0x180063c0f  jnb     loc_180063CD0
0x180063c15  mov     rcx, [r12+60h]
0x180063c1a  mov     r12d, 0FFFF8000h
0x180063c20  test    rcx, rcx
0x180063c23  jz      short loc_180063C43
0x180063c25  mov     rdx, [rbx+20h]
0x180063c29  xor     r12d, r12d
0x180063c2c  cmp     [rdx+18h], rcx
0x180063c30  jz      short loc_180063C43
0x180063c32  inc     r12d
0x180063c35  movsxd  rax, r12d
0x180063c38  shl     rax, 5
0x180063c3c  cmp     [rax+rdx+18h], rcx
0x180063c41  jnz     short loc_180063C32
0x180063c43  mov     rcx, [rbx+20h]
0x180063c47  mov     edx, [rsp+0D8h+arg_40]
0x180063c4e  movsxd  rax, r12d
0x180063c51  shl     rax, 5
0x180063c55  mov     rax, [rax+rcx]
0x180063c59  mov     [rsp+0D8h+var_A0], rax
0x180063c5e  test    edx, edx
0x180063c60  jz      short loc_180063C66
0x180063c62  mov     rax, [rcx+20h]
0x180063c66  cmp     r12d, 1
0x180063c6a  jz      short loc_180063C70
0x180063c6c  test    edx, edx
0x180063c6e  jz      short loc_180063C77
0x180063c70  mov     edx, 5
0x180063c75  jmp     short loc_180063C7C
0x180063c77  mov     edx, 7
0x180063c7c  mov     r9, [rsp+0D8h+var_A8]
0x180063c81  mov     r8, r15
0x180063c84  mov     rcx, rdi
0x180063c87  mov     [rsp+0D8h+var_B8], rax
0x180063c8c  call    sqlite3AuthCheck
0x180063c91  test    eax, eax
0x180063c93  jnz     loc_180063B48
0x180063c99  lea     rax, aSqliteMaster; "sqlite_master"
0x180063ca0  cmp     r12d, 1
0x180063ca4  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180063cab  mov     rcx, rdi
0x180063cae  cmovnz  r8, rax
0x180063cb2  mov     rax, [rsp+0D8h+var_A0]
0x180063cb7  xor     r9d, r9d
0x180063cba  mov     [rsp+0D8h+var_B8], rax
0x180063cbf  lea     edx, [r9+12h]
0x180063cc3  call    sqlite3AuthCheck
0x180063cc8  test    eax, eax
0x180063cca  jnz     loc_180063B48
0x180063cd0  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180063cd8  mov     eax, 21h ; '!'
0x180063cdd  mov     edx, 48h ; 'H'
0x180063ce2  mov     rcx, rbx
0x180063ce5  cmovnz  eax, [rsp+0D8h+arg_18]
0x180063ced  mov     [rsp+0D8h+arg_40], eax
0x180063cf4  call    sqlite3DbMallocZero
0x180063cf9  mov     r12, rax
0x180063cfc  test    rax, rax
0x180063cff  jz      loc_180063DC6
0x180063d05  mov     [rax], r15
0x180063d08  mov     rcx, rbx
0x180063d0b  mov     rdx, [r13+18h]
0x180063d0f  call    sqlite3DbStrDup
0x180063d14  mov     [r12+8], rax
0x180063d19  mov     r8, rax
0x180063d1c  mov     rcx, [rbx+20h]
0x180063d20  mov     edx, r14d
0x180063d23  shl     rdx, 5
0x180063d27  cmp     [rsp+0D8h+arg_40], 21h ; '!'
0x180063d2f  mov     rdx, [rdx+rcx+18h]
0x180063d34  mov     rcx, [rsp+0D8h+arg_38]
0x180063d3c  mov     [r12+28h], rdx
0x180063d41  mov     rcx, [rcx+60h]
0x180063d45  mov     [r12+30h], rcx
0x180063d4a  mov     cl, [rsp+0D8h+arg_20]
0x180063d51  mov     [r12+10h], cl
0x180063d56  setnz   cl
0x180063d59  inc     cl
0x180063d5b  mov     [r12+11h], cl
0x180063d60  cmp     byte ptr [rdi+12Ch], 2
0x180063d67  jb      short loc_180063D90
0x180063d69  mov     rdx, [r13+18h]
0x180063d6d  mov     rcx, rsi
0x180063d70  mov     rax, [rdi+198h]
0x180063d77  jmp     short loc_180063D82
0x180063d79  cmp     [rax], rdx
0x180063d7c  jz      short loc_180063D89
0x180063d7e  mov     rax, [rax+18h]
0x180063d82  test    rax, rax
0x180063d85  jnz     short loc_180063D79
0x180063d87  jmp     short loc_180063D8C
0x180063d89  mov     [rax], r8
0x180063d8c  xor     esi, esi
0x180063d8e  jmp     short loc_180063DAE
0x180063d90  test    rsi, rsi
0x180063d93  jz      short loc_180063DAC
0x180063d95  xor     r9d, r9d
0x180063d98  mov     rdx, rsi
0x180063d9b  mov     rcx, rbx
0x180063d9e  lea     r8d, [r9+1]
0x180063da2  call    exprDup
0x180063da7  mov     rcx, rax
0x180063daa  jmp     short loc_180063DAE
0x180063dac  xor     ecx, ecx
0x180063dae  mov     [r12+18h], rcx
0x180063db3  mov     r14, r12
0x180063db6  mov     [r12+20h], rbp
0x180063dbb  xor     ebp, ebp
0x180063dbd  mov     [rdi+168h], r12
0x180063dc4  jmp     short loc_180063DE6
0x180063dc6  mov     r14, rax
0x180063dc9  jmp     loc_180063B50
0x180063dce  mov     rsi, [rsp+0D8h+arg_38]
0x180063dd6  mov     rbp, [rsp+0D8h+arg_28]
0x180063dde  mov     r14, [rsp+0D8h+arg_0]
0x180063de6  mov     rdx, r13
0x180063de9  mov     rcx, rbx
0x180063dec  call    sqlite3SrcListDelete
0x180063df1  mov     rdx, rbp
0x180063df4  mov     rcx, rbx
  ... truncated ...
```
