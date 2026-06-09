# sqlite3_get_table_cb

- ea: `0x14008aff0`
- end: `0x14008b139`
- name: `sqlite3_get_table_cb`
- size: `329`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14006ab04`
- `0x14008ac90`
- `0x14008aff0`
- `0x14008b820`
- `0x14008b8d0`
- `0x1400a7308`

## string_xrefs

- `0x14008b0b2`: `sqlite3_get_table() called with two or more incompatible queries`

## pseudocode

```c
__int64 __fastcall sqlite3_get_table_cb(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  int v6; // edi
  unsigned int v8; // r8d
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdx
  __int64 i; // rsi
  __int64 v14; // rcx
  void *v15; // rbp
  __int64 v17; // rax
  __int64 v18; // r12
  void *v19; // rax

  v6 = a2;
  if ( !*((_DWORD *)a1 + 5) && a3 )
    a2 *= 2;
  v8 = *((_DWORD *)a1 + 4);
  if ( a2 + *((_DWORD *)a1 + 7) > v8 )
  {
    v9 = *a1;
    *((_DWORD *)a1 + 4) = a2 + 2 * v8;
    v10 = sqlite3Realloc(v9, 8LL * (a2 + 2 * v8));
    if ( !v10 )
    {
LABEL_25:
      *((_DWORD *)a1 + 8) = 7;
      return 1;
    }
    *a1 = v10;
  }
  if ( *((_DWORD *)a1 + 5) )
  {
    if ( *((_DWORD *)a1 + 6) != v6 )
    {
      sqlite3_free(a1[1]);
      a1[1] = sqlite3_mprintf("sqlite3_get_table() called with two or more incompatible queries");
      *((_DWORD *)a1 + 8) = 1;
      return 1;
    }
  }
  else
  {
    v11 = 0;
    for ( *((_DWORD *)a1 + 6) = v6; (int)v11 < v6; *(_QWORD *)(*a1 + 8LL * (unsigned int)(*((_DWORD *)a1 + 7))++) = v12 )
    {
      v12 = sqlite3_mprintf("%s", *(const char **)(a4 + 8 * v11));
      if ( !v12 )
        goto LABEL_25;
      v11 = (unsigned int)(v11 + 1);
    }
  }
  if ( a3 )
  {
    for ( i = 0; (int)i < v6; *(_QWORD *)(*a1 + 8LL * (unsigned int)(*((_DWORD *)a1 + 7))++) = v15 )
    {
      v14 = *(_QWORD *)(a3 + 8 * i);
      if ( v14 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v14 + v17) );
        v18 = ((unsigned int)v17 & 0x3FFFFFFF) + 1;
        v19 = (void *)sqlite3_malloc64(v18);
        v15 = v19;
        if ( !v19 )
          goto LABEL_25;
        memcpy_0(v19, *(const void **)(a3 + 8 * i), (unsigned int)v18);
      }
      else
      {
        v15 = 0;
      }
      i = (unsigned int)(i + 1);
    }
    ++*((_DWORD *)a1 + 5);
  }
  return 0;
}

```

## disassembly

```asm
0x14008aff0  push    rbx
0x14008aff2  push    rbp
0x14008aff3  push    rsi
0x14008aff4  push    rdi
0x14008aff5  push    r12
0x14008aff7  push    r14
0x14008aff9  push    r15
0x14008affb  sub     rsp, 20h
0x14008afff  cmp     dword ptr [rcx+14h], 0
0x14008b003  mov     r15, r9
0x14008b006  mov     r14, r8
0x14008b009  mov     edi, edx
0x14008b00b  mov     rbx, rcx
0x14008b00e  jnz     short loc_14008B017
0x14008b010  test    r8, r8
0x14008b013  jz      short loc_14008B017
0x14008b015  add     edx, edx
0x14008b017  mov     r8d, [rcx+10h]
0x14008b01b  mov     ecx, [rcx+1Ch]
0x14008b01e  add     ecx, edx
0x14008b020  cmp     ecx, r8d
0x14008b023  jbe     short loc_14008B046
0x14008b025  mov     rcx, [rbx]
0x14008b028  lea     eax, [rdx+r8*2]
0x14008b02c  mov     edx, eax
0x14008b02e  shl     rdx, 3
0x14008b032  mov     [rbx+10h], eax
0x14008b035  call    sqlite3Realloc
0x14008b03a  test    rax, rax
0x14008b03d  jz      loc_14008B130
0x14008b043  mov     [rbx], rax
0x14008b046  cmp     dword ptr [rbx+14h], 0
0x14008b04a  jnz     short loc_14008B0A4
0x14008b04c  xor     esi, esi
0x14008b04e  mov     [rbx+18h], edi
0x14008b051  test    edi, edi
0x14008b053  jle     short loc_14008B084
0x14008b055  mov     rdx, [r15+rsi*8]
0x14008b059  lea     rcx, aS_6; "%s"
0x14008b060  call    sqlite3_mprintf
0x14008b065  mov     rdx, rax
0x14008b068  test    rax, rax
0x14008b06b  jz      loc_14008B130
0x14008b071  mov     ecx, [rbx+1Ch]
0x14008b074  inc     esi
0x14008b076  mov     rax, [rbx]
0x14008b079  mov     [rax+rcx*8], rdx
0x14008b07d  inc     dword ptr [rbx+1Ch]
0x14008b080  cmp     esi, edi
0x14008b082  jl      short loc_14008B055
0x14008b084  test    r14, r14
0x14008b087  jz      loc_14008B11F
0x14008b08d  xor     esi, esi
0x14008b08f  test    edi, edi
0x14008b091  jle     loc_14008B11C
0x14008b097  mov     rcx, [r14+rsi*8]
0x14008b09b  test    rcx, rcx
0x14008b09e  jnz     short loc_14008B0D0
0x14008b0a0  xor     ebp, ebp
0x14008b0a2  jmp     short loc_14008B105
0x14008b0a4  cmp     [rbx+18h], edi
0x14008b0a7  jz      short loc_14008B084
0x14008b0a9  mov     rcx, [rbx+8]
0x14008b0ad  call    sqlite3_free
0x14008b0b2  lea     rcx, aSqlite3GetTabl; "sqlite3_get_table() called with two or "...
0x14008b0b9  call    sqlite3_mprintf
0x14008b0be  mov     [rbx+8], rax
0x14008b0c2  mov     dword ptr [rbx+20h], 1
0x14008b0c9  mov     eax, 1
0x14008b0ce  jmp     short loc_14008B121
0x14008b0d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14008b0d4  inc     rax
0x14008b0d7  cmp     byte ptr [rcx+rax], 0
0x14008b0db  jnz     short loc_14008B0D4
0x14008b0dd  and     eax, 3FFFFFFFh
0x14008b0e2  inc     eax
0x14008b0e4  mov     ecx, eax
0x14008b0e6  mov     r12d, eax
0x14008b0e9  call    sqlite3_malloc64
0x14008b0ee  mov     rbp, rax
0x14008b0f1  test    rax, rax
0x14008b0f4  jz      short loc_14008B130
0x14008b0f6  mov     rdx, [r14+rsi*8]; Src
0x14008b0fa  mov     r8d, r12d; Size
0x14008b0fd  mov     rcx, rax; void *
0x14008b100  call    memcpy_0
0x14008b105  mov     edx, [rbx+1Ch]
0x14008b108  inc     esi
0x14008b10a  mov     rcx, [rbx]
0x14008b10d  mov     [rcx+rdx*8], rbp
0x14008b111  inc     dword ptr [rbx+1Ch]
0x14008b114  cmp     esi, edi
0x14008b116  jl      loc_14008B097
0x14008b11c  inc     dword ptr [rbx+14h]
0x14008b11f  xor     eax, eax
0x14008b121  add     rsp, 20h
0x14008b125  pop     r15
0x14008b127  pop     r14
0x14008b129  pop     r12
0x14008b12b  pop     rdi
0x14008b12c  pop     rsi
0x14008b12d  pop     rbp
0x14008b12e  pop     rbx
0x14008b12f  retn
0x14008b130  mov     dword ptr [rbx+20h], 7
0x14008b137  jmp     short loc_14008B0C9
```
