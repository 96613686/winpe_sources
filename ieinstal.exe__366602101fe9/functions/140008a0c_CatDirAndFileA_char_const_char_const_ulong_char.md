# CatDirAndFileA(char const *,char const *,ulong,char *)

- ea: `0x140008a0c`
- end: `0x140008b3c`
- name: `?CatDirAndFileA@@YAHPEBD0KPEAD@Z`
- size: `304`
- prototype: `__int64 __fastcall(const char *, const char *, unsigned int, char *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140008684`
- `0x140008b44`
- `0x140009824`
- `0x140009cc4`

## callees

- `0x140008908`
- `0x140008a0c`
- `0x14000b654`

## pseudocode

```c
__int64 __fastcall CatDirAndFileA(const char *a1, const char *a2, unsigned int a3, char *a4)
{
  unsigned __int64 v4; // rdi
  char *v5; // rbx
  const char *v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rbp
  unsigned __int64 v10; // r9
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  char *v14; // rdx
  char *v15; // rax
  char v16; // al

  v4 = a3;
  v5 = a4;
  v7 = a1;
  if ( !a3 )
    return 0;
  LODWORD(v8) = 0;
  v9 = -1;
  *a4 = 0;
  if ( a1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
  }
  if ( (int)AxiPreScanPathA(a2) < 0 || (int)AxiPreScanPathA(v7) < 0 )
    return 0;
  if ( (_DWORD)v8 )
  {
    if ( (int)v4 - (int)v8 <= 1 )
      return 0;
    v10 = v4;
    if ( (unsigned int)v4 > 0x7FFFFFFF )
    {
      *v5 = 0;
      return 0;
    }
    LODWORD(v4) = v4 - v8;
    v12 = v10;
    v13 = 2147483646;
    v14 = v5;
    do
    {
      if ( !v13 )
        break;
      if ( !*v7 )
        break;
      *v14++ = *v7++;
      --v13;
      --v12;
    }
    while ( v12 );
    v15 = v14 - 1;
    if ( v12 )
      v15 = v14;
    *v15 = 0;
    if ( !v12 )
      return 0;
    v16 = v5[(int)v8 - 1];
    if ( v16 && v16 != 92 && v16 != 58 )
    {
      *(_WORD *)&v5[(int)v8] = 92;
      LODWORD(v4) = v4 - 1;
    }
    if ( (int)v4 <= 0 )
      return 0;
  }
  else
  {
    v10 = v4;
  }
  if ( !*a2 )
    return 0;
  do
    ++v9;
  while ( a2[v9] );
  if ( (int)v4 - (int)v9 <= 0 || (int)StringCchCatA(v5, v10, a2) < 0 )
    return 0;
  while ( *v5 )
  {
    if ( *v5 == 47 )
      *v5 = 92;
    ++v5;
  }
  return 1;
}

```

## disassembly

```asm
0x140008a0c  push    rbx
0x140008a0e  push    rbp
0x140008a0f  push    rsi
0x140008a10  push    rdi
0x140008a11  push    r14
0x140008a13  push    r15
0x140008a15  sub     rsp, 28h
0x140008a19  mov     edi, r8d
0x140008a1c  mov     rbx, r9
0x140008a1f  mov     r15, rdx
0x140008a22  mov     r14, rcx
0x140008a25  test    r8d, r8d
0x140008a28  jz      short loc_140008A7F
0x140008a2a  xor     esi, esi
0x140008a2c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008a30  mov     [r9], sil
0x140008a33  test    rcx, rcx
0x140008a36  jz      short loc_140008A44
0x140008a38  mov     rsi, rbp
0x140008a3b  inc     rsi
0x140008a3e  cmp     byte ptr [rcx+rsi], 0
0x140008a42  jnz     short loc_140008A3B
0x140008a44  mov     rcx, r15; char *
0x140008a47  call    ?AxiPreScanPathA@@YAJPEBD@Z; AxiPreScanPathA(char const *)
0x140008a4c  test    eax, eax
0x140008a4e  js      short loc_140008A7F
0x140008a50  mov     rcx, r14; char *
0x140008a53  call    ?AxiPreScanPathA@@YAJPEBD@Z; AxiPreScanPathA(char const *)
0x140008a58  test    eax, eax
0x140008a5a  js      short loc_140008A7F
0x140008a5c  test    esi, esi
0x140008a5e  jz      loc_140008AEC
0x140008a64  mov     eax, edi
0x140008a66  sub     eax, esi
0x140008a68  cmp     eax, 1
0x140008a6b  jle     short loc_140008A7F
0x140008a6d  mov     r9, rdi
0x140008a70  cmp     edi, 7FFFFFFFh
0x140008a76  jbe     short loc_140008A8F
0x140008a78  test    edi, edi
0x140008a7a  jz      short loc_140008A7F
0x140008a7c  mov     byte ptr [rbx], 0
0x140008a7f  xor     eax, eax
0x140008a81  add     rsp, 28h
0x140008a85  pop     r15
0x140008a87  pop     r14
0x140008a89  pop     rdi
0x140008a8a  pop     rsi
0x140008a8b  pop     rbp
0x140008a8c  pop     rbx
0x140008a8d  retn
0x140008a8f  mov     edi, eax
0x140008a91  mov     rcx, r9
0x140008a94  mov     eax, 7FFFFFFEh
0x140008a99  mov     rdx, rbx
0x140008a9c  test    rax, rax
0x140008a9f  jz      short loc_140008ABB
0x140008aa1  mov     r8b, [r14]
0x140008aa4  test    r8b, r8b
0x140008aa7  jz      short loc_140008ABB
0x140008aa9  mov     [rdx], r8b
0x140008aac  inc     r14
0x140008aaf  inc     rdx
0x140008ab2  dec     rax
0x140008ab5  sub     rcx, 1
0x140008ab9  jnz     short loc_140008A9C
0x140008abb  test    rcx, rcx
0x140008abe  lea     rax, [rdx-1]
0x140008ac2  cmovnz  rax, rdx
0x140008ac6  mov     byte ptr [rax], 0
0x140008ac9  jz      short loc_140008A7F
0x140008acb  movsxd  rcx, esi
0x140008ace  mov     al, [rcx+rbx-1]
0x140008ad2  test    al, al
0x140008ad4  jz      short loc_140008AE6
0x140008ad6  cmp     al, 5Ch ; '\'
0x140008ad8  jz      short loc_140008AE6
0x140008ada  cmp     al, 3Ah ; ':'
0x140008adc  jz      short loc_140008AE6
0x140008ade  mov     word ptr [rcx+rbx], 5Ch ; '\'
0x140008ae4  dec     edi
0x140008ae6  test    edi, edi
0x140008ae8  jle     short loc_140008A7F
0x140008aea  jmp     short loc_140008AEF
0x140008aec  mov     r9, rdi
0x140008aef  cmp     byte ptr [r15], 0
0x140008af3  jz      short loc_140008A7F
0x140008af5  inc     rbp
0x140008af8  cmp     byte ptr [r15+rbp], 0
0x140008afd  jnz     short loc_140008AF5
0x140008aff  sub     edi, ebp
0x140008b01  test    edi, edi
0x140008b03  jle     loc_140008A7F
0x140008b09  mov     r8, r15; char *
0x140008b0c  mov     rdx, r9; unsigned __int64
0x140008b0f  mov     rcx, rbx; char *
0x140008b12  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x140008b17  test    eax, eax
0x140008b19  js      loc_140008A7F
0x140008b1f  jmp     short loc_140008B2C
0x140008b21  cmp     cl, 2Fh ; '/'
0x140008b24  jnz     short loc_140008B29
0x140008b26  mov     byte ptr [rbx], 5Ch ; '\'
0x140008b29  inc     rbx
0x140008b2c  mov     cl, [rbx]
0x140008b2e  test    cl, cl
0x140008b30  jnz     short loc_140008B21
0x140008b32  mov     eax, 1
0x140008b37  jmp     loc_140008A81
```
