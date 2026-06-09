# processLineWithQuotes

- ea: `0x140003934`
- end: `0x140003a27`
- name: `processLineWithQuotes`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400021cc`
- `0x140002c80`

## callees

- `0x14000313c`
- `0x140003934`
- `0x140008620`

## import_xrefs

- `msvcrt!strspn` at `0x1400039b1`
- `msvcrt!strspn` at `0x1400039b1`

## string_xrefs

- `0x14000395e`: `InfWrite string`

## pseudocode

```c
__int64 __fastcall processLineWithQuotes(_BYTE *a1, int a2, _BYTE *a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v8; // rax
  const char *QuotedString; // rax
  const char *v10; // rdi
  __int64 v11; // rbx
  size_t v12; // rax
  size_t v13; // rdx
  _BYTE *v14; // rcx

  *a1 = 0;
  if ( !*a3 )
    return 1;
  while ( 1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    QuotedString = (const char *)getQuotedString(&a1[(int)v8], (__int64)"InfWrite string", a6);
    v10 = QuotedString;
    if ( !QuotedString )
      return 0;
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    v12 = strspn(QuotedString, " \t");
    v13 = v12;
    if ( !v10[v12] )
      return 1;
    v14 = &a1[(int)v11];
    if ( v12 )
    {
      while ( (int)v11 < a2 )
      {
        LODWORD(v11) = v11 + 1;
        *v14++ = *v10++;
        if ( !--v13 )
          goto LABEL_11;
      }
LABEL_14:
      ErrSet(a6, "%1 exceeded maximum length(%2)", "%s%d", "InfWrite string", a2 - 1);
      return 0;
    }
LABEL_11:
    if ( (int)v11 >= a2 )
      goto LABEL_14;
    *v14 = 0;
    if ( !*v10 )
      return 1;
  }
}

```

## disassembly

```asm
0x140003934  push    rbx
0x140003936  push    rbp
0x140003937  push    rsi
0x140003938  push    rdi
0x140003939  push    r13
0x14000393b  push    r14
0x14000393d  sub     rsp, 38h
0x140003941  mov     byte ptr [rcx], 0
0x140003944  mov     rdi, r8
0x140003947  cmp     byte ptr [r8], 0
0x14000394b  mov     ebp, edx
0x14000394d  mov     rsi, rcx
0x140003950  jz      loc_1400039F1
0x140003956  mov     r14, [rsp+68h+arg_28]
0x14000395e  lea     r13, aInfwriteString; "InfWrite string"
0x140003965  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003969  inc     rax
0x14000396c  cmp     byte ptr [rsi+rax], 0
0x140003970  jnz     short loc_140003969
0x140003972  mov     edx, ebp
0x140003974  movsxd  rcx, eax
0x140003977  sub     edx, eax
0x140003979  mov     [rsp+68h+var_40], r14; __int64
0x14000397e  add     rcx, rsi; void *
0x140003981  mov     [rsp+68h+var_48], r13; __int64
0x140003986  mov     r8, rdi
0x140003989  call    getQuotedString
0x14000398e  mov     rdi, rax
0x140003991  test    rax, rax
0x140003994  jz      loc_140003A23
0x14000399a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000399e  inc     rbx
0x1400039a1  cmp     byte ptr [rsi+rbx], 0
0x1400039a5  jnz     short loc_14000399E
0x1400039a7  lea     rdx, Control; " \t"
0x1400039ae  mov     rcx, rdi; Str
0x1400039b1  call    cs:__imp_strspn
0x1400039b7  mov     rdx, rax
0x1400039ba  cmp     byte ptr [rdi+rax], 0
0x1400039be  jz      short loc_1400039F1
0x1400039c0  movsxd  rcx, ebx
0x1400039c3  add     rcx, rsi
0x1400039c6  test    rax, rax
0x1400039c9  jz      short loc_1400039E1
0x1400039cb  cmp     ebx, ebp
0x1400039cd  jge     short loc_140003A03
0x1400039cf  mov     al, [rdi]
0x1400039d1  inc     ebx
0x1400039d3  mov     [rcx], al
0x1400039d5  inc     rdi
0x1400039d8  inc     rcx
0x1400039db  sub     rdx, 1
0x1400039df  jnz     short loc_1400039CB
0x1400039e1  cmp     ebx, ebp
0x1400039e3  jge     short loc_140003A03
0x1400039e5  mov     byte ptr [rcx], 0
0x1400039e8  cmp     byte ptr [rdi], 0
0x1400039eb  jnz     loc_140003965
0x1400039f1  mov     eax, 1
0x1400039f6  add     rsp, 38h
0x1400039fa  pop     r14
0x1400039fc  pop     r13
0x1400039fe  pop     rdi
0x1400039ff  pop     rsi
0x140003a00  pop     rbp
0x140003a01  pop     rbx
0x140003a02  retn
0x140003a03  lea     eax, [rbp-1]
0x140003a06  mov     r9, r13
0x140003a09  lea     r8, aSD; "%s%d"
0x140003a10  mov     dword ptr [rsp+68h+var_48], eax
0x140003a14  lea     rdx, a1ExceededMaxim; "%1 exceeded maximum length(%2)"
0x140003a1b  mov     rcx, r14
0x140003a1e  call    ErrSet
0x140003a23  xor     eax, eax
0x140003a25  jmp     short loc_1400039F6
```
