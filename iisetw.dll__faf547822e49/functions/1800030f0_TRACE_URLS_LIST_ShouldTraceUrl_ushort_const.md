# TRACE_URLS_LIST::ShouldTraceUrl(ushort const *)

- ea: `0x1800030f0`
- end: `0x1800031d4`
- name: `?ShouldTraceUrl@TRACE_URLS_LIST@@QEAAHPEBG@Z`
- size: `228`
- prototype: `__int64 __fastcall(TRACE_URLS_LIST *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019a4`

## callees

- `0x1800030f0`

## import_xrefs

- `msvcrt!towupper` at `0x180003127`
- `msvcrt!towupper` at `0x180003133`
- `msvcrt!towupper` at `0x180003171`
- `msvcrt!towupper` at `0x18000317d`
- `msvcrt!towupper` at `0x180003127`
- `msvcrt!towupper` at `0x180003133`
- `msvcrt!towupper` at `0x180003171`
- `msvcrt!towupper` at `0x18000317d`

## pseudocode

```c
__int64 __fastcall TRACE_URLS_LIST::ShouldTraceUrl(TRACE_URLS_LIST *this, const unsigned __int16 *a2)
{
  TRACE_URLS_LIST *v2; // r15
  const unsigned __int16 *v3; // rax
  wint_t *v5; // rsi
  wint_t *i; // r14
  wint_t v7; // bx
  wint_t v8; // di
  wint_t *v9; // r12
  wint_t *v10; // r13
  wint_t v11; // bx
  wint_t v12; // di

  v2 = *(TRACE_URLS_LIST **)this;
  v3 = a2;
  if ( *(TRACE_URLS_LIST **)this == this )
    return 0;
LABEL_2:
  v5 = (wint_t *)*((_QWORD *)v2 + 6);
  for ( i = (wint_t *)v3; ; ++i )
  {
    if ( *v5 == 42 )
    {
LABEL_9:
      v9 = v5;
      while ( 2 )
      {
        v10 = i;
        while ( 1 )
        {
          if ( *v5 == 42 )
          {
            if ( !*++v5 )
              return 1;
            goto LABEL_9;
          }
          v11 = *v5;
          v12 = towupper(*i);
          if ( v12 != towupper(v11) )
            break;
          if ( !*v5 )
            return 1;
          ++i;
          ++v5;
        }
        i = v10 + 1;
        if ( v10[1] )
        {
          v5 = v9;
          continue;
        }
        break;
      }
LABEL_17:
      v2 = *(TRACE_URLS_LIST **)v2;
      if ( v2 == this )
        return 0;
      v3 = a2;
      goto LABEL_2;
    }
    v7 = *v5;
    v8 = towupper(*i);
    if ( v8 != towupper(v7) )
      goto LABEL_17;
    if ( !*v5 )
      break;
    ++v5;
  }
  return 1;
}

```

## disassembly

```asm
0x1800030f0  mov     [rsp+arg_8], rdx
0x1800030f5  push    rbx
0x1800030f6  push    rbp
0x1800030f7  push    rsi
0x1800030f8  push    rdi
0x1800030f9  push    r12
0x1800030fb  push    r13
0x1800030fd  push    r14
0x1800030ff  push    r15
0x180003101  sub     rsp, 28h
0x180003105  mov     r15, [rcx]
0x180003108  mov     rax, rdx
0x18000310b  mov     rbp, rcx
0x18000310e  cmp     r15, rcx
0x180003111  jz      loc_1800031C1
0x180003117  mov     rsi, [r15+30h]
0x18000311b  mov     r14, rax
0x18000311e  jmp     short loc_18000314C
0x180003120  movzx   ecx, word ptr [r14]; C
0x180003124  movzx   ebx, word ptr [rsi]
0x180003127  call    cs:__imp_towupper
0x18000312d  movzx   ecx, bx; C
0x180003130  movzx   edi, ax
0x180003133  call    cs:__imp_towupper
0x180003139  cmp     di, ax
0x18000313c  jnz     short loc_1800031A8
0x18000313e  cmp     word ptr [rsi], 0
0x180003142  jz      short loc_1800031BA
0x180003144  add     r14, 2
0x180003148  add     rsi, 2
0x18000314c  cmp     word ptr [rsi], 2Ah ; '*'
0x180003150  jnz     short loc_180003120
0x180003152  jmp     short loc_18000315E
0x180003154  add     rsi, 2
0x180003158  cmp     word ptr [rsi], 0
0x18000315c  jz      short loc_1800031BA
0x18000315e  mov     r12, rsi
0x180003161  mov     r13, r14
0x180003164  cmp     word ptr [rsi], 2Ah ; '*'
0x180003168  jz      short loc_180003154
0x18000316a  movzx   ecx, word ptr [r14]; C
0x18000316e  movzx   ebx, word ptr [rsi]
0x180003171  call    cs:__imp_towupper
0x180003177  movzx   ecx, bx; C
0x18000317a  movzx   edi, ax
0x18000317d  call    cs:__imp_towupper
0x180003183  cmp     di, ax
0x180003186  jz      short loc_180003198
0x180003188  lea     r14, [r13+2]
0x18000318c  cmp     word ptr [r14], 0
0x180003191  jz      short loc_1800031A8
0x180003193  mov     rsi, r12
0x180003196  jmp     short loc_180003161
0x180003198  cmp     word ptr [rsi], 0
0x18000319c  jz      short loc_1800031BA
0x18000319e  add     r14, 2
0x1800031a2  add     rsi, 2
0x1800031a6  jmp     short loc_180003164
0x1800031a8  mov     r15, [r15]
0x1800031ab  cmp     r15, rbp
0x1800031ae  jz      short loc_1800031C1
0x1800031b0  mov     rax, [rsp+68h+arg_8]
0x1800031b5  jmp     loc_180003117
0x1800031ba  mov     eax, 1
0x1800031bf  jmp     short loc_1800031C3
0x1800031c1  xor     eax, eax
0x1800031c3  add     rsp, 28h
0x1800031c7  pop     r15
0x1800031c9  pop     r14
0x1800031cb  pop     r13
0x1800031cd  pop     r12
0x1800031cf  pop     rdi
0x1800031d0  pop     rsi
0x1800031d1  pop     rbp
0x1800031d2  pop     rbx
0x1800031d3  retn
```
