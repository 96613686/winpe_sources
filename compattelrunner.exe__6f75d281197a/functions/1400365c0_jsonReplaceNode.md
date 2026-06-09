# jsonReplaceNode

- ea: `0x1400365c0`
- end: `0x1400367d5`
- name: `jsonReplaceNode`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1400364c0`
- `0x140036f00`

## callees

- `0x140034cc8`
- `0x140034d34`
- `0x140034d70`
- `0x140034e80`
- `0x140034ef4`
- `0x1400365c0`
- `0x140054178`
- `0x140073758`
- `0x14007b4d0`
- `0x14007c6ac`
- `0x14007d3c4`
- `0x14008b8d0`
- `0x14008c3e0`
- `0x14008f900`

## string_xrefs

- `0x140036631`: `JSON cannot hold BLOB values`

## pseudocode

```c
unsigned int *__fastcall jsonReplaceNode(__int64 *a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int *result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rbp
  unsigned int v12; // r14d
  unsigned int *v13; // rdi
  __int64 (__fastcall *v14)(); // rdx
  __int64 v15; // rax
  __int64 v16; // rbp
  __int64 v17; // rcx
  double v18; // xmm0_8
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rax

  result = (unsigned int *)jsonParseAddSubstNode(a2, a3);
  if ( (int)result <= 0 )
    return result;
  if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) == 1 )
  {
    v21 = sqlite3VdbeIntValue(
            a4,
            (unsigned int)*((unsigned __int8 *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) - 1);
    result = (unsigned int *)sqlite3_mprintf("%lld", v21);
    v13 = result;
    if ( !result )
      goto LABEL_23;
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)result + v19) );
    v20 = 4;
    goto LABEL_27;
  }
  if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) == 2 )
  {
    v18 = sqlite3VdbeRealValue(a4);
    result = (unsigned int *)sqlite3_mprintf("%!0.15g", v18);
    v13 = result;
    if ( !result )
      goto LABEL_23;
    v19 = -1;
    do
      ++v19;
    while ( *((_BYTE *)result + v19) );
    v20 = 5;
LABEL_27:
    jsonParseAddNode(a2, v20, v19 & 0x3FFFFFFF, v13);
    v14 = (__int64 (__fastcall *)())sqlite3_free;
    return (unsigned int *)jsonParseAddCleanup(a2, v14, v13);
  }
  v8 = (unsigned int)*((unsigned __int8 *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) - 3;
  if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
  {
    if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) == 5 )
      return (unsigned int *)jsonParseAddNode(a2, 1, 0, 0);
    jsonParseAddNode(a2, 1, 0, 0);
    v9 = *a1;
    *((_DWORD *)a1 + 9) = 1;
    LOBYTE(v10) = 1;
    result = (unsigned int *)sqlite3VdbeMemSetStr(v9, "JSON cannot hold BLOB values", -1, v10, -1);
    ++*(_BYTE *)(a2 + 50);
    return result;
  }
  LODWORD(v8) = 1;
  v11 = sqlite3ValueText(a4, v8);
  result = (unsigned int *)sqlite3_value_bytes(a4);
  v12 = (unsigned int)result;
  if ( !v11 )
    goto LABEL_23;
  if ( (*(_WORD *)(a4 + 20) & 0x800) != 0 && *(_BYTE *)(a4 + 23) == 74 )
  {
    result = (unsigned int *)jsonParseCached(a1, a4, a1, 1);
    v13 = result;
    if ( result )
    {
      jsonParseAddNodeArray(a2, *((_QWORD *)result + 1), *result);
      ++v13[14];
      v14 = jsonParseFree;
      return (unsigned int *)jsonParseAddCleanup(a2, v14, v13);
    }
LABEL_23:
    *(_BYTE *)(a2 + 51) = 1;
    return result;
  }
  v15 = sqlite3DbStrDup(0, v11);
  v16 = v15;
  if ( v15 )
  {
    jsonParseAddCleanup(a2, sqlite3_free, v15);
  }
  else
  {
    *(_BYTE *)(a2 + 51) = 1;
    sqlite3_result_error_nomem(a1);
  }
  result = (unsigned int *)jsonParseAddNode(a2, 6, v12, v16);
  if ( !*(_BYTE *)(a2 + 51) )
  {
    v17 = (int)result;
    result = *(unsigned int **)(a2 + 8);
    BYTE1(result[4 * v17]) |= 1u;
  }
  return result;
}

```

## disassembly

```asm
0x1400365c0  push    rbx
0x1400365c2  push    rbp
0x1400365c3  push    rsi
0x1400365c4  push    rdi
0x1400365c5  push    r14
0x1400365c7  push    r15
0x1400365c9  sub     rsp, 38h
0x1400365cd  mov     rbx, rdx
0x1400365d0  mov     rsi, rcx
0x1400365d3  mov     rcx, rbx
0x1400365d6  mov     edx, r8d
0x1400365d9  mov     rdi, r9
0x1400365dc  call    jsonParseAddSubstNode
0x1400365e1  test    eax, eax
0x1400365e3  jle     loc_1400367C8
0x1400365e9  movzx   eax, word ptr [rdi+14h]
0x1400365ed  lea     rcx, qword_1400B5170
0x1400365f4  and     eax, 3Fh
0x1400365f7  mov     r15d, 1
0x1400365fd  movzx   edx, byte ptr [rax+rcx]
0x140036601  sub     edx, r15d
0x140036604  jz      loc_14003676C
0x14003660a  sub     edx, r15d
0x14003660d  jz      loc_140036733
0x140036613  sub     edx, r15d
0x140036616  jz      short loc_140036660
0x140036618  xor     r9d, r9d
0x14003661b  xor     r8d, r8d
0x14003661e  cmp     edx, 2
0x140036621  mov     rcx, rbx
0x140036624  mov     edx, r15d
0x140036627  jz      short loc_140036656
0x140036629  call    jsonParseAddNode
0x14003662e  mov     rcx, [rsi]
0x140036631  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x140036638  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003663c  mov     [rsi+24h], r15d
0x140036640  mov     r9b, r15b
0x140036643  mov     [rsp+68h+var_48], r8
0x140036648  call    sqlite3VdbeMemSetStr
0x14003664d  add     [rbx+32h], r15b
0x140036651  jmp     loc_1400367C8
0x140036656  call    jsonParseAddNode
0x14003665b  jmp     loc_1400367C8
0x140036660  mov     dl, r15b
0x140036663  mov     rcx, rdi
0x140036666  call    sqlite3ValueText
0x14003666b  mov     rcx, rdi
0x14003666e  mov     rbp, rax
0x140036671  call    sqlite3_value_bytes
0x140036676  mov     r14d, eax
0x140036679  test    rbp, rbp
0x14003667c  jz      loc_14003678B
0x140036682  mov     eax, 800h
0x140036687  test    [rdi+14h], ax
0x14003668b  jz      short loc_1400366CF
0x14003668d  cmp     byte ptr [rdi+17h], 4Ah ; 'J'
0x140036691  jnz     short loc_1400366CF
0x140036693  mov     r9d, r15d
0x140036696  mov     r8, rsi
0x140036699  mov     rdx, rdi
0x14003669c  mov     rcx, rsi
0x14003669f  call    jsonParseCached
0x1400366a4  mov     rdi, rax
0x1400366a7  test    rax, rax
0x1400366aa  jz      loc_14003678B
0x1400366b0  mov     r8d, [rax]
0x1400366b3  mov     rcx, rbx
0x1400366b6  mov     rdx, [rax+8]
0x1400366ba  call    jsonParseAddNodeArray
0x1400366bf  add     [rdi+38h], r15d
0x1400366c3  lea     rdx, jsonParseFree
0x1400366ca  jmp     loc_1400367BD
0x1400366cf  mov     rdx, rbp
0x1400366d2  xor     ecx, ecx
0x1400366d4  call    sqlite3DbStrDup
0x1400366d9  mov     rbp, rax
0x1400366dc  test    rax, rax
0x1400366df  jz      short loc_1400366F5
0x1400366e1  mov     r8, rax
0x1400366e4  lea     rdx, sqlite3_free
0x1400366eb  mov     rcx, rbx
0x1400366ee  call    jsonParseAddCleanup
0x1400366f3  jmp     short loc_140036701
0x1400366f5  mov     rcx, rsi
0x1400366f8  mov     [rbx+33h], r15b
0x1400366fc  call    sqlite3_result_error_nomem
0x140036701  mov     r9, rbp
0x140036704  mov     r8d, r14d
0x140036707  mov     edx, 6
0x14003670c  mov     rcx, rbx
0x14003670f  call    jsonParseAddNode
0x140036714  cmp     byte ptr [rbx+33h], 0
0x140036718  jnz     loc_1400367C8
0x14003671e  movsxd  rcx, eax
0x140036721  mov     rax, [rbx+8]
0x140036725  shl     rcx, 4
0x140036729  or      [rcx+rax+1], r15b
0x14003672e  jmp     loc_1400367C8
0x140036733  mov     rcx, rdi
0x140036736  call    sqlite3VdbeRealValue
0x14003673b  movaps  xmm1, xmm0
0x14003673e  lea     rcx, a015g; "%!0.15g"
0x140036745  movq    rdx, xmm0
0x14003674a  call    sqlite3_mprintf
0x14003674f  mov     rdi, rax
0x140036752  test    rax, rax
0x140036755  jz      short loc_14003678B
0x140036757  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003675b  inc     r8
0x14003675e  cmp     byte ptr [rax+r8], 0
0x140036763  jnz     short loc_14003675B
0x140036765  mov     edx, 5
0x14003676a  jmp     short loc_1400367A4
0x14003676c  mov     rcx, rdi
0x14003676f  call    sqlite3VdbeIntValue
0x140036774  mov     rdx, rax
0x140036777  lea     rcx, aLld; "%lld"
0x14003677e  call    sqlite3_mprintf
0x140036783  mov     rdi, rax
0x140036786  test    rax, rax
0x140036789  jnz     short loc_140036791
0x14003678b  mov     [rbx+33h], r15b
0x14003678f  jmp     short loc_1400367C8
0x140036791  or      r8, 0FFFFFFFFFFFFFFFFh
0x140036795  inc     r8
0x140036798  cmp     byte ptr [rax+r8], 0
0x14003679d  jnz     short loc_140036795
0x14003679f  mov     edx, 4
0x1400367a4  mov     r9, rdi
0x1400367a7  and     r8d, 3FFFFFFFh
0x1400367ae  mov     rcx, rbx
0x1400367b1  call    jsonParseAddNode
0x1400367b6  lea     rdx, sqlite3_free
0x1400367bd  mov     r8, rdi
0x1400367c0  mov     rcx, rbx
0x1400367c3  call    jsonParseAddCleanup
0x1400367c8  add     rsp, 38h
0x1400367cc  pop     r15
0x1400367ce  pop     r14
0x1400367d0  pop     rdi
0x1400367d1  pop     rsi
0x1400367d2  pop     rbp
0x1400367d3  pop     rbx
0x1400367d4  retn
```
