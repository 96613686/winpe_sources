# JsonUtil::GetJsonEncodedQuotedString(ushort const *,ushort * *)

- ea: `0x14001d06c`
- end: `0x14001d2ce`
- name: `?GetJsonEncodedQuotedString@JsonUtil@@SAKPEBGPEAPEAG@Z`
- size: `610`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001d6d0`
- `0x14001daa0`

## callees

- `0x140001b60`
- `0x140002a30`
- `0x14001d06c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d2c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d2c1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d12a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d12a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d0ab`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d0ab`

## pseudocode

```c
__int64 __fastcall JsonUtil::GetJsonEncodedQuotedString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rdx
  size_t v6; // rax
  __int64 result; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  _WORD *v10; // rax
  unsigned __int16 *v11; // rsi
  __int64 v12; // rbp
  _DWORD *v13; // rbx
  unsigned int v14; // edx
  wchar_t v15; // ax
  wchar_t *v16; // rbx
  wchar_t Buffer[8]; // [rsp+20h] [rbp-58h] BYREF

  if ( a1 )
  {
    v6 = wcsnlen(a1, 0x7FFFFFFFu);
    v4 = v6;
    if ( v6 >= 0x15555552 )
      return 3399876612LL;
    v5 = 0;
    v8 = 0;
    if ( v6 )
    {
      do
      {
        if ( a1[v8] == 8
          || a1[v8] == 9
          || a1[v8] == 10
          || a1[v8] == 12
          || a1[v8] == 13
          || a1[v8] == 34
          || a1[v8] == 47
          || a1[v8] == 92 )
        {
          v9 = 2;
        }
        else
        {
          v9 = 1;
          if ( a1[v8] <= 0x1Fu )
            v9 = 6;
        }
        v8 = (unsigned int)(v8 + 1);
        v5 += v9;
      }
      while ( (unsigned int)v8 < v4 );
    }
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  v10 = malloc(2 * v5 + 6);
  v11 = v10;
  if ( !v10 )
    return 3399876610LL;
  v12 = 0;
  v13 = v10 + 1;
  *v10 = 34;
  if ( !v4 )
  {
LABEL_43:
    *v13 = 34;
    result = 0;
    *a2 = v11;
    return result;
  }
  while ( 1 )
  {
    v14 = a1[v12];
    if ( v14 == 8 )
    {
      *(_WORD *)v13 = 92;
      v13 = (_DWORD *)((char *)v13 + 2);
      *(_WORD *)v13 = 98;
      goto LABEL_42;
    }
    switch ( a1[v12] )
    {
      case 9u:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 116;
        goto LABEL_42;
      case 0xAu:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 110;
        goto LABEL_42;
      case 0xCu:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 102;
        goto LABEL_42;
      case 0xDu:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 114;
        goto LABEL_42;
      case 0x22u:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 34;
        goto LABEL_42;
      case 0x2Fu:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 47;
        goto LABEL_42;
      case 0x5Cu:
        *(_WORD *)v13 = 92;
        v13 = (_DWORD *)((char *)v13 + 2);
        *(_WORD *)v13 = 92;
        goto LABEL_42;
    }
    if ( v14 > 0x1F )
    {
      *(_WORD *)v13 = v14;
      goto LABEL_42;
    }
    if ( swprintf_s(Buffer, 5u, L"%04x", a1[v12]) == -1 )
      break;
    v15 = Buffer[0];
    *(_WORD *)v13 = 92;
    v16 = (wchar_t *)v13 + 1;
    *v16++ = 117;
    *v16++ = v15;
    *v16++ = Buffer[1];
    *v16 = Buffer[2];
    v13 = v16 + 1;
    *(_WORD *)v13 = Buffer[3];
LABEL_42:
    v12 = (unsigned int)(v12 + 1);
    v13 = (_DWORD *)((char *)v13 + 2);
    if ( (unsigned int)v12 >= v4 )
      goto LABEL_43;
  }
  free(v11);
  return 3399876614LL;
}

```

## disassembly

```asm
0x14001d06c  mov     [rsp+arg_10], rbx
0x14001d071  push    rbp
0x14001d072  push    rsi
0x14001d073  push    rdi
0x14001d074  push    r12
0x14001d076  push    r13
0x14001d078  push    r14
0x14001d07a  push    r15
0x14001d07c  sub     rsp, 40h
0x14001d080  mov     rax, cs:__security_cookie
0x14001d087  xor     rax, rsp
0x14001d08a  mov     [rsp+78h+var_48], rax
0x14001d08f  mov     r15, rdx
0x14001d092  mov     r14, rcx
0x14001d095  mov     r12d, 2
0x14001d09b  test    rcx, rcx
0x14001d09e  jnz     short loc_14001D0A6
0x14001d0a0  xor     edi, edi
0x14001d0a2  xor     edx, edx
0x14001d0a4  jmp     short loc_14001D122
0x14001d0a6  mov     edx, 7FFFFFFFh; MaxCount
0x14001d0ab  call    cs:__imp_wcsnlen
0x14001d0b1  mov     rdi, rax
0x14001d0b4  cmp     rax, 15555552h
0x14001d0ba  jb      short loc_14001D0C6
0x14001d0bc  mov     eax, 0CAA60004h
0x14001d0c1  jmp     loc_14001D299
0x14001d0c6  xor     edx, edx
0x14001d0c8  xor     r8d, r8d
0x14001d0cb  test    rdi, rdi
0x14001d0ce  jz      short loc_14001D122
0x14001d0d0  movzx   r9d, word ptr [r14+r8*2]
0x14001d0d5  mov     ecx, r9d
0x14001d0d8  sub     ecx, 8
0x14001d0db  jz      short loc_14001D111
0x14001d0dd  sub     ecx, 1
0x14001d0e0  jz      short loc_14001D111
0x14001d0e2  sub     ecx, 1
0x14001d0e5  jz      short loc_14001D111
0x14001d0e7  sub     ecx, r12d
0x14001d0ea  jz      short loc_14001D111
0x14001d0ec  sub     ecx, 1
0x14001d0ef  jz      short loc_14001D111
0x14001d0f1  sub     ecx, 15h
0x14001d0f4  jz      short loc_14001D111
0x14001d0f6  sub     ecx, 0Dh
0x14001d0f9  jz      short loc_14001D111
0x14001d0fb  cmp     ecx, 2Dh ; '-'
0x14001d0fe  jz      short loc_14001D111
0x14001d100  mov     eax, 1
0x14001d105  cmp     r9d, 1Fh
0x14001d109  lea     ecx, [rax+5]
0x14001d10c  cmovbe  eax, ecx
0x14001d10f  jmp     short loc_14001D114
0x14001d111  mov     rax, r12
0x14001d114  inc     r8d
0x14001d117  add     rdx, rax
0x14001d11a  mov     eax, r8d
0x14001d11d  cmp     rax, rdi
0x14001d120  jb      short loc_14001D0D0
0x14001d122  lea     rcx, ds:6[rdx*2]; Size
0x14001d12a  call    cs:__imp_malloc
0x14001d130  mov     rsi, rax
0x14001d133  test    rax, rax
0x14001d136  jnz     short loc_14001D142
0x14001d138  mov     eax, 0CAA60002h
0x14001d13d  jmp     loc_14001D299
0x14001d142  xor     ebp, ebp
0x14001d144  lea     rbx, [rax+2]
0x14001d148  mov     r8d, 22h ; '"'
0x14001d14e  mov     [rax], r8w
0x14001d152  test    rdi, rdi
0x14001d155  jz      loc_14001D28E
0x14001d15b  lea     r13d, [r8+3Ah]
0x14001d15f  movzx   edx, word ptr [r14+rbp*2]
0x14001d164  mov     ecx, edx
0x14001d166  sub     ecx, 8
0x14001d169  jz      loc_14001D272
0x14001d16f  sub     ecx, 1
0x14001d172  jz      loc_14001D264
0x14001d178  sub     ecx, 1
0x14001d17b  jz      loc_14001D256
0x14001d181  sub     ecx, r12d
0x14001d184  jz      loc_14001D248
0x14001d18a  sub     ecx, 1
0x14001d18d  jz      loc_14001D23A
0x14001d193  sub     ecx, 15h
0x14001d196  jz      loc_14001D22D
0x14001d19c  sub     ecx, 0Dh
0x14001d19f  jz      short loc_14001D21F
0x14001d1a1  cmp     ecx, 2Dh ; '-'
0x14001d1a4  jz      short loc_14001D212
0x14001d1a6  cmp     edx, 1Fh
0x14001d1a9  ja      short loc_14001D20D
0x14001d1ab  mov     r9d, edx
0x14001d1ae  lea     r8, a04x; "%04x"
0x14001d1b5  mov     edx, 5; BufferCount
0x14001d1ba  lea     rcx, [rsp+78h+Buffer]; Buffer
0x14001d1bf  call    swprintf_s
0x14001d1c4  cmp     eax, 0FFFFFFFFh
0x14001d1c7  jz      loc_14001D2BE
0x14001d1cd  movzx   eax, [rsp+78h+Buffer]
0x14001d1d2  mov     r8d, 22h ; '"'
0x14001d1d8  mov     [rbx], r13w
0x14001d1dc  add     rbx, r12
0x14001d1df  mov     word ptr [rbx], 75h ; 'u'
0x14001d1e4  add     rbx, r12
0x14001d1e7  mov     [rbx], ax
0x14001d1ea  add     rbx, r12
0x14001d1ed  movzx   eax, [rsp+78h+var_56]
0x14001d1f2  mov     [rbx], ax
0x14001d1f5  add     rbx, r12
0x14001d1f8  movzx   eax, [rsp+78h+var_54]
0x14001d1fd  mov     [rbx], ax
0x14001d200  add     rbx, r12
0x14001d203  movzx   eax, [rsp+78h+var_52]
0x14001d208  mov     [rbx], ax
0x14001d20b  jmp     short loc_14001D27E
0x14001d20d  mov     [rbx], dx
0x14001d210  jmp     short loc_14001D27E
0x14001d212  mov     [rbx], r13w
0x14001d216  add     rbx, r12
0x14001d219  mov     [rbx], r13w
0x14001d21d  jmp     short loc_14001D27E
0x14001d21f  mov     [rbx], r13w
0x14001d223  add     rbx, r12
0x14001d226  mov     word ptr [rbx], 2Fh ; '/'
0x14001d22b  jmp     short loc_14001D27E
0x14001d22d  mov     [rbx], r13w
0x14001d231  add     rbx, r12
0x14001d234  mov     [rbx], r8w
0x14001d238  jmp     short loc_14001D27E
0x14001d23a  mov     [rbx], r13w
0x14001d23e  add     rbx, r12
0x14001d241  mov     word ptr [rbx], 72h ; 'r'
0x14001d246  jmp     short loc_14001D27E
0x14001d248  mov     [rbx], r13w
0x14001d24c  add     rbx, r12
0x14001d24f  mov     word ptr [rbx], 66h ; 'f'
0x14001d254  jmp     short loc_14001D27E
0x14001d256  mov     [rbx], r13w
0x14001d25a  add     rbx, r12
0x14001d25d  mov     word ptr [rbx], 6Eh ; 'n'
0x14001d262  jmp     short loc_14001D27E
0x14001d264  mov     [rbx], r13w
0x14001d268  add     rbx, r12
0x14001d26b  mov     word ptr [rbx], 74h ; 't'
0x14001d270  jmp     short loc_14001D27E
0x14001d272  mov     [rbx], r13w
0x14001d276  add     rbx, r12
0x14001d279  mov     word ptr [rbx], 62h ; 'b'
0x14001d27e  inc     ebp
0x14001d280  add     rbx, r12
0x14001d283  mov     eax, ebp
0x14001d285  cmp     rax, rdi
0x14001d288  jb      loc_14001D15F
0x14001d28e  mov     dword ptr [rbx], 22h ; '"'
0x14001d294  xor     eax, eax
0x14001d296  mov     [r15], rsi
0x14001d299  mov     rcx, [rsp+78h+var_48]
0x14001d29e  xor     rcx, rsp; StackCookie
0x14001d2a1  call    __security_check_cookie
0x14001d2a6  mov     rbx, [rsp+78h+arg_10]
0x14001d2ae  add     rsp, 40h
0x14001d2b2  pop     r15
0x14001d2b4  pop     r14
0x14001d2b6  pop     r13
0x14001d2b8  pop     r12
0x14001d2ba  pop     rdi
0x14001d2bb  pop     rsi
0x14001d2bc  pop     rbp
0x14001d2bd  retn
0x14001d2be  mov     rcx, rsi; Block
0x14001d2c1  call    cs:__imp_free
0x14001d2c7  mov     eax, 0CAA60006h
0x14001d2cc  jmp     short loc_14001D299
```
