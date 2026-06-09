# getQuotedString

- ea: `0x14000313c`
- end: `0x140003284`
- name: `getQuotedString`
- size: `328`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140003310`
- `0x1400034e4`
- `0x140003748`
- `0x140003934`

## callees

- `0x14000313c`
- `0x140008620`
- `0x14000e406`

## import_xrefs

- `msvcrt!strpbrk` at `0x140003189`
- `msvcrt!strpbrk` at `0x140003189`

## pseudocode

```c
const char *__fastcall getQuotedString(_BYTE *a1, int a2, const char *a3, __int64 a4, const char *a5, __int64 a6)
{
  __int64 v7; // rbx
  unsigned int v8; // r8d
  const char *result; // rax
  const char *v11; // rax
  char v12; // cl
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rbx
  _BYTE *v17; // rdi
  _BYTE *i; // rcx
  __int64 v19; // rdx
  bool v20; // cc

  v7 = a2;
  v8 = *a3;
  if ( !(_BYTE)v8 )
  {
    *a1 = 0;
    return a3;
  }
  v11 = "'\"";
  v12 = 39;
  do
  {
    if ( v12 == (_BYTE)v8 )
      break;
    v12 = *++v11;
  }
  while ( *v11 );
  if ( *v11 )
  {
    v17 = a3 + 1;
    for ( i = a1; *v17 && i - a1 < v7; ++i )
    {
      if ( *v17 == (_BYTE)v8 )
      {
        result = v17 + 1;
        if ( v17[1] != (_BYTE)v8 )
        {
          *i = 0;
          return result;
        }
        v19 = 2;
      }
      else
      {
        v19 = 1;
      }
      *i = *v17;
      v17 += v19;
    }
    v20 = i - a1 < v7;
    v15 = a6;
    if ( !v20 )
      goto LABEL_24;
    ErrSet(a6, (int)"Missing closing quote(%1) in %2", "%c%s", v8, a5);
  }
  else
  {
    v13 = (__int64)strpbrk(a3, " \t");
    v14 = v13;
    if ( v13 )
    {
      LODWORD(v13) = v13 - (_DWORD)a3;
    }
    else
    {
      v13 = -1;
      do
        ++v13;
      while ( a3[v13] );
      v14 = (__int64)&a3[(int)v13];
    }
    if ( (int)v13 < (int)v7 )
    {
      v16 = (int)v13;
      memcpy_0(a1, a3, (int)v13);
      result = (const char *)v14;
      a1[v16] = 0;
      return result;
    }
    v15 = a6;
LABEL_24:
    ErrSet(v15, (int)"%1 exceeded maximum length(%2)", "%s%d", a5, v7 - 1);
  }
  return 0;
}

```

## disassembly

```asm
0x14000313c  push    rbx
0x14000313e  push    rsi
0x14000313f  push    rdi
0x140003140  push    r14
0x140003142  sub     rsp, 38h
0x140003146  mov     rdi, r8
0x140003149  movsxd  rbx, edx
0x14000314c  movsx   r8d, byte ptr [r8]
0x140003150  mov     r14, rcx
0x140003153  test    r8b, r8b
0x140003156  jnz     short loc_140003163
0x140003158  mov     [rcx], r8b
0x14000315b  mov     rax, rdi
0x14000315e  jmp     loc_14000327A
0x140003163  lea     rax, asc_140011CEC; "'\""
0x14000316a  mov     cl, 27h ; '''
0x14000316c  cmp     cl, r8b
0x14000316f  jz      short loc_14000317A
0x140003171  inc     rax
0x140003174  mov     cl, [rax]
0x140003176  test    cl, cl
0x140003178  jnz     short loc_14000316C
0x14000317a  cmp     byte ptr [rax], 0
0x14000317d  jnz     short loc_1400031DA
0x14000317f  lea     rdx, Control; " \t"
0x140003186  mov     rcx, rdi; Str
0x140003189  call    cs:__imp_strpbrk
0x14000318f  mov     rsi, rax
0x140003192  test    rax, rax
0x140003195  jnz     short loc_1400031AC
0x140003197  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000319b  inc     rax
0x14000319e  cmp     byte ptr [rdi+rax], 0
0x1400031a2  jnz     short loc_14000319B
0x1400031a4  movsxd  rsi, eax
0x1400031a7  add     rsi, rdi
0x1400031aa  jmp     short loc_1400031AE
0x1400031ac  sub     eax, edi
0x1400031ae  cmp     eax, ebx
0x1400031b0  jl      short loc_1400031BC
0x1400031b2  mov     rcx, [rsp+58h+arg_28]
0x1400031ba  jmp     short loc_14000322C
0x1400031bc  movsxd  rbx, eax
0x1400031bf  mov     rdx, rdi; Src
0x1400031c2  mov     r8, rbx; Size
0x1400031c5  mov     rcx, r14; void *
0x1400031c8  call    memcpy_0
0x1400031cd  mov     rax, rsi
0x1400031d0  mov     byte ptr [rbx+r14], 0
0x1400031d5  jmp     loc_14000327A
0x1400031da  inc     rdi
0x1400031dd  mov     rcx, r14
0x1400031e0  jmp     short loc_140003217
0x1400031e2  mov     rax, rcx
0x1400031e5  sub     rax, r14
0x1400031e8  cmp     rax, rbx
0x1400031eb  jge     short loc_14000321C
0x1400031ed  mov     r9b, [rdi]
0x1400031f0  cmp     r9b, r8b
0x1400031f3  jnz     short loc_140003205
0x1400031f5  lea     rax, [rdi+1]
0x1400031f9  cmp     [rax], r8b
0x1400031fc  jnz     short loc_140003250
0x1400031fe  mov     edx, 2
0x140003203  jmp     short loc_14000320A
0x140003205  mov     edx, 1
0x14000320a  lea     rax, [rcx+1]
0x14000320e  mov     [rcx], r9b
0x140003211  mov     rcx, rax
0x140003214  add     rdi, rdx
0x140003217  cmp     byte ptr [rdi], 0
0x14000321a  jnz     short loc_1400031E2
0x14000321c  sub     rcx, r14
0x14000321f  cmp     rcx, rbx
0x140003222  mov     rcx, [rsp+58h+arg_28]
0x14000322a  jl      short loc_140003255
0x14000322c  mov     r9, [rsp+58h+arg_20]
0x140003234  lea     eax, [rbx-1]
0x140003237  lea     rdx, a1ExceededMaxim; "%1 exceeded maximum length(%2)"
0x14000323e  mov     dword ptr [rsp+58h+var_38], eax
0x140003242  lea     r8, aSD; "%s%d"
0x140003249  call    ErrSet
0x14000324e  jmp     short loc_140003278
0x140003250  mov     byte ptr [rcx], 0
0x140003253  jmp     short loc_14000327A
0x140003255  mov     rax, [rsp+58h+arg_20]
0x14000325d  lea     rdx, aMissingClosing; "Missing closing quote(%1) in %2"
0x140003264  mov     r9d, r8d
0x140003267  mov     [rsp+58h+var_38], rax
0x14000326c  lea     r8, aCS; "%c%s"
0x140003273  call    ErrSet
0x140003278  xor     eax, eax
0x14000327a  add     rsp, 38h
0x14000327e  pop     r14
0x140003280  pop     rdi
0x140003281  pop     rsi
0x140003282  pop     rbx
0x140003283  retn
```
