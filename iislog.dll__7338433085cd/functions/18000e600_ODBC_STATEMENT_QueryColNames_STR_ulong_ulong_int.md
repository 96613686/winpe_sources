# ODBC_STATEMENT::QueryColNames(STR * *,ulong *,ulong,int *)

- ea: `0x18000e600`
- end: `0x18000e8f0`
- name: `?QueryColNames@ODBC_STATEMENT@@QEAAHPEAPEAVSTR@@PEAKKPEAH@Z`
- size: `752`
- prototype: `__int64 __fastcall(ODBC_STATEMENT *__hidden this, struct STR **, unsigned int *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000e930`

## callees

- `0x180001008`
- `0x18000dbc0`
- `0x18000e600`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `IisRTL!??0STR@@QEAA@XZ` at `0x18000e6ee`
- `IisRTL!??0STR@@QEAA@XZ` at `0x18000e74d`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e85b`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000e85b`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000e845`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x18000e845`
- `ODBC32!__imp_SQLBindCol` at `0x18000e894`
- `ODBC32!__imp_SQLBindCol` at `0x18000e894`
- `ODBC32!__imp_SQLDescribeCol` at `0x18000e805`
- `ODBC32!__imp_SQLDescribeCol` at `0x18000e805`
- `ODBC32!__imp_SQLNumResultCols` at `0x18000e68b`
- `ODBC32!__imp_SQLNumResultCols` at `0x18000e68b`

## pseudocode

```c
__int64 __fastcall ODBC_STATEMENT::QueryColNames(
        ODBC_STATEMENT *this,
        struct STR **a2,
        unsigned int *a3,
        unsigned int a4,
        int *a5)
{
  struct STR *v8; // rcx
  unsigned int v10; // r13d
  SQLRETURN v11; // ax
  unsigned int v12; // eax
  unsigned __int64 v13; // rdi
  __int64 v14; // rax
  bool v15; // cf
  size_t v16; // rax
  unsigned __int64 *v17; // rax
  _QWORD *v18; // r14
  _QWORD *i; // rsi
  unsigned __int64 v20; // rdi
  __int64 v21; // rax
  size_t v22; // rax
  unsigned __int64 *v23; // rax
  _QWORD *v24; // r14
  _QWORD *j; // rsi
  unsigned __int64 v26; // kr00_8
  void *v27; // rax
  signed __int16 v28; // di
  signed __int16 v29; // si
  SQLRETURN v30; // ax
  SQLULEN v31; // rdx
  SQLULEN v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r14
  __int64 v35; // rdi
  SQLRETURN v36; // ax
  SQLSMALLINT ColumnCount[2]; // [rsp+50h] [rbp-61h] BYREF
  SQLSMALLINT DataType; // [rsp+54h] [rbp-5Dh] BYREF
  SQLSMALLINT Nullable[2]; // [rsp+58h] [rbp-59h] BYREF
  SQLSMALLINT DecimalDigits; // [rsp+5Ch] [rbp-55h] BYREF
  SQLSMALLINT NameLength; // [rsp+60h] [rbp-51h] BYREF
  SQLULEN ColumnSize; // [rsp+68h] [rbp-49h] BYREF
  SQLCHAR ColumnName[64]; // [rsp+70h] [rbp-41h] BYREF

  *a2 = 0;
  *a3 = 0;
  ColumnCount[0] = 0;
  NameLength = 0;
  *a5 = 1;
  v8 = (struct STR *)*((_QWORD *)this + 4);
  DataType = 0;
  ColumnSize = 0;
  DecimalDigits = 0;
  Nullable[0] = 0;
  if ( v8 )
  {
    *a2 = v8;
    *a3 = *((unsigned __int16 *)this + 13);
    return 1;
  }
  v10 = 0x2000;
  if ( a4 )
    v10 = a4;
  v11 = SQLNumResultCols(*((SQLHSTMT *)this + 2), ColumnCount);
  *((_WORD *)this + 12) = v11;
  if ( (unsigned __int16)v11 <= 1u )
  {
    v12 = (unsigned __int16)ColumnCount[0];
    if ( ColumnCount[0] <= 0 )
    {
      *a5 = 0;
      return 1;
    }
    *((_WORD *)this + 13) = ColumnCount[0];
    *a3 = v12;
    v13 = *((unsigned __int16 *)this + 13);
    v14 = 56 * v13;
    if ( !is_mul_ok(v13, 0x38u) )
      v14 = -1;
    v15 = __CFADD__(v14, 8);
    v16 = v14 + 8;
    if ( v15 )
      v16 = -1;
    v17 = (unsigned __int64 *)operator new(v16);
    if ( v17 )
    {
      *v17 = v13;
      v18 = v17 + 1;
      for ( i = v17 + 1; v13; --v13 )
      {
        ((void (__fastcall *)(_QWORD *))STR::STR)(i);
        i += 7;
      }
    }
    else
    {
      v18 = 0;
    }
    v20 = *((unsigned __int16 *)this + 13);
    *((_QWORD *)this + 4) = v18;
    v21 = 56 * v20;
    if ( !is_mul_ok(v20, 0x38u) )
      v21 = -1;
    v15 = __CFADD__(v21, 8);
    v22 = v21 + 8;
    if ( v15 )
      v22 = -1;
    v23 = (unsigned __int64 *)operator new(v22);
    if ( v23 )
    {
      *v23 = v20;
      v24 = v23 + 1;
      for ( j = v23 + 1; v20; --v20 )
      {
        ((void (__fastcall *)(_QWORD *))STR::STR)(j);
        j += 7;
      }
    }
    else
    {
      v24 = 0;
    }
    v26 = *((unsigned __int16 *)this + 13);
    *((_QWORD *)this + 5) = v24;
    v27 = operator new(saturated_mul(v26, 8u));
    *((_QWORD *)this + 6) = v27;
    if ( *((_QWORD *)this + 4) )
    {
      if ( *((_QWORD *)this + 5) && v27 )
      {
        v28 = 0;
        if ( !*((_WORD *)this + 13) )
        {
LABEL_37:
          *a2 = (struct STR *)*((_QWORD *)this + 4);
          *a3 = *((unsigned __int16 *)this + 13);
          return 1;
        }
        while ( 1 )
        {
          v29 = v28 + 1;
          v30 = SQLDescribeCol(
                  *((SQLHSTMT *)this + 2),
                  v28 + 1,
                  ColumnName,
                  64,
                  &NameLength,
                  &DataType,
                  &ColumnSize,
                  &DecimalDigits,
                  Nullable);
          *((_WORD *)this + 12) = v30;
          if ( (unsigned __int16)v30 > 1u )
            break;
          v31 = v10;
          if ( ColumnSize < v10 )
            v31 = ColumnSize;
          v32 = ODBC_CONNECTION::DisplaySize(DataType, v31);
          v33 = *((_QWORD *)this + 4);
          v34 = v28;
          v35 = 56LL * v28;
          ColumnSize = v32;
          if ( !STR::Copy((STR *)(v35 + v33), (const char *)ColumnName) )
            break;
          if ( !BUFFER::Resize((BUFFER *)(v35 + *((_QWORD *)this + 5)), ColumnSize + 1) )
            break;
          v36 = SQLBindCol(
                  *((SQLHSTMT *)this + 2),
                  v29,
                  1,
                  *(SQLPOINTER *)(*((_QWORD *)this + 5) + v35 + 32),
                  ColumnSize,
                  (SQLLEN *)(*((_QWORD *)this + 6) + 8 * v34));
          *((_WORD *)this + 12) = v36;
          if ( (unsigned __int16)v36 > 1u )
            break;
          v28 = v29;
          if ( v29 >= (int)*((unsigned __int16 *)this + 13) )
            goto LABEL_37;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e600  push    rbp
0x18000e602  push    rbx
0x18000e603  push    rsi
0x18000e604  push    rdi
0x18000e605  push    r12
0x18000e607  push    r13
0x18000e609  push    r14
0x18000e60b  push    r15
0x18000e60d  lea     rbp, [rsp-17h]
0x18000e612  sub     rsp, 0C8h
0x18000e619  mov     rax, cs:__security_cookie
0x18000e620  xor     rax, rsp
0x18000e623  mov     [rbp+4Fh+var_50], rax
0x18000e627  mov     rdi, [rbp+4Fh+arg_20]
0x18000e62b  xor     esi, esi
0x18000e62d  mov     [rdx], rsi
0x18000e630  mov     rbx, rcx
0x18000e633  mov     [r8], esi
0x18000e636  mov     r15, r8
0x18000e639  mov     r12, rdx
0x18000e63c  mov     [rbp+4Fh+ColumnCount], si
0x18000e640  lea     r14d, [rsi+1]
0x18000e644  mov     [rbp+4Fh+var_A0], si
0x18000e648  mov     [rdi], r14d
0x18000e64b  mov     rcx, [rcx+20h]
0x18000e64f  mov     [rbp+4Fh+var_AC], si
0x18000e653  mov     [rbp+4Fh+var_98], rsi
0x18000e657  mov     [rbp+4Fh+var_A4], si
0x18000e65b  mov     [rbp+4Fh+var_A8], si
0x18000e65f  test    rcx, rcx
0x18000e662  jz      short loc_18000E676
0x18000e664  mov     [rdx], rcx
0x18000e667  movzx   ecx, word ptr [rbx+1Ah]
0x18000e66b  mov     [r8], ecx
0x18000e66e  mov     eax, r14d
0x18000e671  jmp     loc_18000E8D0
0x18000e676  mov     rcx, [rbx+10h]; StatementHandle
0x18000e67a  lea     rdx, [rbp+4Fh+ColumnCount]; ColumnCount
0x18000e67e  test    r9d, r9d
0x18000e681  mov     r13d, 2000h
0x18000e687  cmovnz  r13d, r9d
0x18000e68b  call    cs:__imp_SQLNumResultCols
0x18000e691  mov     [rbx+18h], ax
0x18000e695  cmp     ax, r14w
0x18000e699  ja      loc_18000E8CE
0x18000e69f  movzx   eax, [rbp+4Fh+ColumnCount]
0x18000e6a3  test    ax, ax
0x18000e6a6  jle     loc_18000E8C7
0x18000e6ac  mov     [rbx+1Ah], ax
0x18000e6b0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e6b7  mov     [r15], eax
0x18000e6ba  mov     eax, 38h ; '8'
0x18000e6bf  movzx   edi, word ptr [rbx+1Ah]
0x18000e6c3  mul     rdi
0x18000e6c6  cmovb   rax, rcx
0x18000e6ca  add     rax, 8
0x18000e6ce  cmovb   rax, rcx
0x18000e6d2  mov     rcx, rax; Size
0x18000e6d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e6da  test    rax, rax
0x18000e6dd  jz      short loc_18000E70B
0x18000e6df  mov     [rax], rdi
0x18000e6e2  lea     r14, [rax+8]
0x18000e6e6  mov     rsi, r14
0x18000e6e9  test    rdi, rdi
0x18000e6ec  jz      short loc_18000E707
0x18000e6ee  mov     rax, cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x18000e6f5  mov     rcx, rsi
0x18000e6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6fd  add     rsi, 38h ; '8'
0x18000e701  sub     rdi, 1
0x18000e705  jnz     short loc_18000E6EE
0x18000e707  xor     esi, esi
0x18000e709  jmp     short loc_18000E70E
0x18000e70b  mov     r14, rsi
0x18000e70e  movzx   edi, word ptr [rbx+1Ah]
0x18000e712  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e719  mov     eax, 38h ; '8'
0x18000e71e  mov     [rbx+20h], r14
0x18000e722  mul     rdi
0x18000e725  cmovb   rax, rcx
0x18000e729  add     rax, 8
0x18000e72d  cmovb   rax, rcx
0x18000e731  mov     rcx, rax; Size
0x18000e734  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e739  test    rax, rax
0x18000e73c  jz      short loc_18000E76A
0x18000e73e  mov     [rax], rdi
0x18000e741  lea     r14, [rax+8]
0x18000e745  mov     rsi, r14
0x18000e748  test    rdi, rdi
0x18000e74b  jz      short loc_18000E766
0x18000e74d  mov     rax, cs:__imp_??0STR@@QEAA@XZ; STR::STR(void)
0x18000e754  mov     rcx, rsi
0x18000e757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e75c  add     rsi, 38h ; '8'
0x18000e760  sub     rdi, 1
0x18000e764  jnz     short loc_18000E74D
0x18000e766  xor     esi, esi
0x18000e768  jmp     short loc_18000E76D
0x18000e76a  mov     r14, rsi
0x18000e76d  movzx   ecx, word ptr [rbx+1Ah]
0x18000e771  mov     eax, 8
0x18000e776  mul     rcx
0x18000e779  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e780  mov     [rbx+28h], r14
0x18000e784  cmovb   rax, rcx
0x18000e788  mov     rcx, rax; Size
0x18000e78b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e790  mov     [rbx+30h], rax
0x18000e794  cmp     [rbx+20h], rsi
0x18000e798  jz      loc_18000E8CE
0x18000e79e  cmp     [rbx+28h], rsi
0x18000e7a2  jz      loc_18000E8CE
0x18000e7a8  test    rax, rax
0x18000e7ab  jz      loc_18000E8CE
0x18000e7b1  mov     edi, esi
0x18000e7b3  mov     r14d, 1
0x18000e7b9  cmp     si, [rbx+1Ah]
0x18000e7bd  jnb     loc_18000E8B3
0x18000e7c3  mov     rcx, [rbx+10h]; StatementHandle
0x18000e7c7  lea     rax, [rbp+4Fh+var_A8]
0x18000e7cb  mov     [rsp+100h+Nullable], rax; Nullable
0x18000e7d0  lea     esi, [r14+rdi]
0x18000e7d4  lea     rax, [rbp+4Fh+var_A4]
0x18000e7d8  mov     r9d, 40h ; '@'; BufferLength
0x18000e7de  mov     [rsp+100h+DecimalDigits], rax; DecimalDigits
0x18000e7e3  lea     r8, [rbp+4Fh+ColumnName]; ColumnName
0x18000e7e7  lea     rax, [rbp+4Fh+var_98]
0x18000e7eb  movzx   edx, si; ColumnNumber
0x18000e7ee  mov     [rsp+100h+ColumnSize], rax; ColumnSize
0x18000e7f3  lea     rax, [rbp+4Fh+var_AC]
0x18000e7f7  mov     [rsp+100h+DataType], rax; DataType
0x18000e7fc  lea     rax, [rbp+4Fh+var_A0]
0x18000e800  mov     [rsp+100h+NameLength], rax; NameLength
0x18000e805  call    cs:__imp_SQLDescribeCol
0x18000e80b  mov     [rbx+18h], ax
0x18000e80f  cmp     ax, r14w
0x18000e813  ja      loc_18000E8CE
0x18000e819  movzx   ecx, [rbp+4Fh+var_AC]; __int16
0x18000e81d  mov     edx, r13d
0x18000e820  cmp     [rbp+4Fh+var_98], rdx
0x18000e824  cmovb   rdx, [rbp+4Fh+var_98]; unsigned __int64
0x18000e829  call    ?DisplaySize@ODBC_CONNECTION@@SA_KF_K@Z; ODBC_CONNECTION::DisplaySize(short,unsigned __int64)
0x18000e82e  mov     rcx, [rbx+20h]
0x18000e832  lea     rdx, [rbp+4Fh+ColumnName]
0x18000e836  movsx   r14, di
0x18000e83a  imul    rdi, r14, 38h ; '8'
0x18000e83e  mov     [rbp+4Fh+var_98], rax
0x18000e842  add     rcx, rdi
0x18000e845  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x18000e84b  test    eax, eax
0x18000e84d  jz      short loc_18000E8CE
0x18000e84f  mov     edx, dword ptr [rbp+4Fh+var_98]
0x18000e852  mov     rcx, [rbx+28h]
0x18000e856  inc     edx
0x18000e858  add     rcx, rdi
0x18000e85b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000e861  test    al, al
0x18000e863  jz      short loc_18000E8CE
0x18000e865  mov     rax, [rbx+30h]
0x18000e869  movzx   edx, si; ColumnNumber
0x18000e86c  mov     r9, [rbx+28h]
0x18000e870  lea     rcx, [rax+r14*8]
0x18000e874  mov     r14d, 1
0x18000e87a  mov     rax, [rbp+4Fh+var_98]
0x18000e87e  mov     r8d, r14d; TargetType
0x18000e881  mov     r9, [r9+rdi+20h]; TargetValue
0x18000e886  mov     [rsp+100h+DataType], rcx; StrLen_or_Ind
0x18000e88b  mov     rcx, [rbx+10h]; StatementHandle
0x18000e88f  mov     [rsp+100h+NameLength], rax; BufferLength
0x18000e894  call    cs:__imp_SQLBindCol
0x18000e89a  mov     [rbx+18h], ax
0x18000e89e  cmp     ax, r14w
0x18000e8a2  ja      short loc_18000E8CE
0x18000e8a4  movzx   eax, word ptr [rbx+1Ah]
0x18000e8a8  movsx   edi, si
0x18000e8ab  cmp     edi, eax
0x18000e8ad  jl      loc_18000E7C3
0x18000e8b3  mov     rax, [rbx+20h]
0x18000e8b7  mov     [r12], rax
0x18000e8bb  movzx   eax, word ptr [rbx+1Ah]
0x18000e8bf  mov     [r15], eax
0x18000e8c2  jmp     loc_18000E66E
0x18000e8c7  mov     [rdi], esi
0x18000e8c9  jmp     loc_18000E66E
0x18000e8ce  xor     eax, eax
0x18000e8d0  mov     rcx, [rbp+4Fh+var_50]
0x18000e8d4  xor     rcx, rsp; StackCookie
0x18000e8d7  call    __security_check_cookie
0x18000e8dc  add     rsp, 0C8h
0x18000e8e3  pop     r15
0x18000e8e5  pop     r14
0x18000e8e7  pop     r13
0x18000e8e9  pop     r12
0x18000e8eb  pop     rdi
0x18000e8ec  pop     rsi
0x18000e8ed  pop     rbx
0x18000e8ee  pop     rbp
0x18000e8ef  retn
```
