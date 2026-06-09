# IsPlainUrl(wchar_t const *)

- ea: `0x18002c954`
- end: `0x18002cb7e`
- name: `?IsPlainUrl@@YA_NPEB_W@Z`
- size: `554`
- prototype: `bool __fastcall(LPCWCH lpString2)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000afec`
- `0x18002a7d0`
- `0x18003cfd0`
- `0x18003d1a8`
- `0x1800b1e50`
- `0x180113e30`
- `0x180120a1c`
- `0x1801c00c0`
- `0x1801c8c20`
- `0x1801c9240`
- `0x1801d8200`
- `0x1801e4354`

## callees

- `0x18002c954`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x18002cb02`
- `api-ms-win-crt-private-l1-1-0!_o_iswxdigit` at `0x18002cb02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c9c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c9ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cb27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cb56`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c9c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002c9ef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cb27`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cb56`

## pseudocode

```c
char __fastcall IsPlainUrl(LPCWCH lpString2)
{
  unsigned __int64 v1; // r14
  LPCWCH v2; // rbx
  __int64 v3; // rdi
  char v4; // bp
  _WORD *v5; // rsi
  unsigned __int64 v6; // rax
  __int64 v8; // rdi
  LPCWCH v9; // rdi
  _WORD *v10; // rax
  __int64 v11; // rcx
  unsigned int i; // ebx

  v1 = -1;
  v2 = lpString2;
  v3 = -1;
  do
    ++v3;
  while ( lpString2[v3] );
  v4 = 1;
  if ( (unsigned int)v3 >= 8 && CompareStringOrdinal(L"file:///", 8, lpString2, 8, 1) == 2 )
  {
    v5 = v2 + 8;
  }
  else
  {
    v5 = v2;
    if ( (unsigned int)v3 >= 5 && CompareStringOrdinal(L"file:", 5, v2, 5, 1) == 2 )
      v5 = v2 + 5;
  }
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 < 3
    || (unsigned __int16)(*v5 - 97) > 0x19u && (unsigned __int16)(*v5 - 65) > 0x19u
    || v5[1] != 58
    || v5[2] != 47 && v5[2] != 92 )
  {
    return 0;
  }
  v8 = -1;
  do
    ++v8;
  while ( v2[v8] );
  if ( (unsigned int)v8 >= 8 && CompareStringOrdinal(L"file:///", 8, v2, 8, 1) == 2 )
  {
    v2 += 8;
  }
  else if ( (unsigned int)v8 >= 5 && CompareStringOrdinal(L"file:", 5, v2, 5, 1) == 2 )
  {
    v2 += 5;
  }
  do
    ++v1;
  while ( v2[v1] );
  if ( v1 >= 3
    && ((unsigned __int16)(*v2 - 97) <= 0x19u || (unsigned __int16)(*v2 - 65) <= 0x19u)
    && v2[1] == 58
    && (v2[2] == 47 || v2[2] == 92) )
  {
    v9 = v2 + 3;
    if ( v2 != (LPCWCH)-6LL )
    {
      v10 = v2 + 3;
      v11 = 0x7FFF;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v11;
      }
      while ( v11 );
      if ( v11 && ((0x7FFF - v11) & (unsigned __int64)-(__int64)(v11 != 0)) >= 0x26 )
      {
        for ( i = 0; i < 0x26; ++i )
        {
          if ( (aXxxxxxxxXxxxXx[i] != 88 || !(unsigned int)_o_iswxdigit(v9[i])) && v9[i] != aXxxxxxxxXxxxXx[i] )
            return v4;
        }
        return 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18002c954  push    rbx
0x18002c956  push    rbp
0x18002c957  push    rsi
0x18002c958  push    rdi
0x18002c959  push    r14
0x18002c95b  push    r15
0x18002c95d  sub     rsp, 38h
0x18002c961  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002c965  mov     rbx, rcx
0x18002c968  mov     rdi, r14
0x18002c96b  xor     r15d, r15d
0x18002c96e  inc     rdi
0x18002c971  cmp     [rcx+rdi*2], r15w
0x18002c976  jnz     short loc_18002C96E
0x18002c978  mov     ebp, 1
0x18002c97d  cmp     edi, 8
0x18002c980  jnb     short loc_18002C9B0
0x18002c982  mov     rsi, rbx
0x18002c985  cmp     edi, 5
0x18002c988  jnb     short loc_18002C9D8
0x18002c98a  mov     rax, r14
0x18002c98d  inc     rax
0x18002c990  cmp     [rsi+rax*2], r15w
0x18002c995  jnz     short loc_18002C98D
0x18002c997  cmp     rax, 3
0x18002c99b  jnb     short loc_18002CA00
0x18002c99d  mov     bpl, r15b
0x18002c9a0  mov     al, bpl
0x18002c9a3  add     rsp, 38h
0x18002c9a7  pop     r15
0x18002c9a9  pop     r14
0x18002c9ab  pop     rdi
0x18002c9ac  pop     rsi
0x18002c9ad  pop     rbp
0x18002c9ae  pop     rbx
0x18002c9af  retn
0x18002c9b0  mov     r9d, 8; cchCount2
0x18002c9b6  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x18002c9ba  mov     edx, r9d; cchCount1
0x18002c9bd  lea     rcx, String1; "file:///"
0x18002c9c4  mov     r8, rbx; lpString2
0x18002c9c7  call    cs:__imp_CompareStringOrdinal
0x18002c9cd  cmp     eax, 2
0x18002c9d0  jnz     short loc_18002C982
0x18002c9d2  lea     rsi, [rbx+10h]
0x18002c9d6  jmp     short loc_18002C98A
0x18002c9d8  mov     r9d, 5; cchCount2
0x18002c9de  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x18002c9e2  mov     edx, r9d; cchCount1
0x18002c9e5  lea     rcx, aFile_8; "file:"
0x18002c9ec  mov     r8, rbx; lpString2
0x18002c9ef  call    cs:__imp_CompareStringOrdinal
0x18002c9f5  cmp     eax, 2
0x18002c9f8  jnz     short loc_18002C98A
0x18002c9fa  lea     rsi, [rbx+0Ah]
0x18002c9fe  jmp     short loc_18002C98A
0x18002ca00  movzx   ecx, word ptr [rsi]
0x18002ca03  lea     eax, [rcx-61h]
0x18002ca06  cmp     ax, 19h
0x18002ca0a  jbe     short loc_18002CA16
0x18002ca0c  sub     cx, 41h ; 'A'
0x18002ca10  cmp     cx, 19h
0x18002ca14  ja      short loc_18002C99D
0x18002ca16  cmp     word ptr [rsi+2], 3Ah ; ':'
0x18002ca1b  jnz     short loc_18002C99D
0x18002ca1d  cmp     word ptr [rsi+4], 2Fh ; '/'
0x18002ca22  jz      short loc_18002CA2F
0x18002ca24  cmp     word ptr [rsi+4], 5Ch ; '\'
0x18002ca29  jnz     loc_18002C99D
0x18002ca2f  mov     rdi, r14
0x18002ca32  inc     rdi
0x18002ca35  cmp     [rbx+rdi*2], r15w
0x18002ca3a  jnz     short loc_18002CA32
0x18002ca3c  cmp     edi, 8
0x18002ca3f  jnb     loc_18002CB10
0x18002ca45  cmp     edi, 5
0x18002ca48  jnb     loc_18002CB3F
0x18002ca4e  inc     r14
0x18002ca51  cmp     [rbx+r14*2], r15w
0x18002ca56  jnz     short loc_18002CA4E
0x18002ca58  cmp     r14, 3
0x18002ca5c  jb      loc_18002C9A0
0x18002ca62  movzx   ecx, word ptr [rbx]
0x18002ca65  lea     eax, [rcx-61h]
0x18002ca68  cmp     ax, 19h
0x18002ca6c  jbe     short loc_18002CA7C
0x18002ca6e  sub     cx, 41h ; 'A'
0x18002ca72  cmp     cx, 19h
0x18002ca76  ja      loc_18002C9A0
0x18002ca7c  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18002ca81  jnz     loc_18002C9A0
0x18002ca87  cmp     word ptr [rbx+4], 2Fh ; '/'
0x18002ca8c  jz      short loc_18002CA99
0x18002ca8e  cmp     word ptr [rbx+4], 5Ch ; '\'
0x18002ca93  jnz     loc_18002C9A0
0x18002ca99  lea     rdi, [rbx+6]
0x18002ca9d  test    rdi, rdi
0x18002caa0  jz      loc_18002C9A0
0x18002caa6  mov     edx, 7FFFh
0x18002caab  mov     rax, rdi
0x18002caae  mov     ecx, edx
0x18002cab0  cmp     [rax], r15w
0x18002cab4  jz      short loc_18002CABF
0x18002cab6  add     rax, 2
0x18002caba  sub     rcx, rbp
0x18002cabd  jnz     short loc_18002CAB0
0x18002cabf  sub     rdx, rcx
0x18002cac2  mov     rax, rcx
0x18002cac5  neg     rax
0x18002cac8  sbb     r8, r8
0x18002cacb  and     r8, rdx
0x18002cace  test    rcx, rcx
0x18002cad1  jz      loc_18002C9A0
0x18002cad7  cmp     r8, 26h ; '&'
0x18002cadb  jb      loc_18002C9A0
0x18002cae1  mov     ebx, r15d
0x18002cae4  cmp     ebx, 26h ; '&'
0x18002cae7  jnb     loc_18002C99D
0x18002caed  mov     esi, ebx
0x18002caef  lea     r14, aXxxxxxxxXxxxXx; "[XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX]"
0x18002caf6  cmp     word ptr [r14+rsi*2], 58h ; 'X'
0x18002cafc  jnz     short loc_18002CB6E
0x18002cafe  movzx   ecx, word ptr [rdi+rsi*2]
0x18002cb02  call    cs:__imp__o_iswxdigit
0x18002cb08  test    eax, eax
0x18002cb0a  jz      short loc_18002CB6E
0x18002cb0c  add     ebx, ebp
0x18002cb0e  jmp     short loc_18002CAE4
0x18002cb10  mov     r9d, 8; cchCount2
0x18002cb16  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x18002cb1a  mov     edx, r9d; cchCount1
0x18002cb1d  lea     rcx, String1; "file:///"
0x18002cb24  mov     r8, rbx; lpString2
0x18002cb27  call    cs:__imp_CompareStringOrdinal
0x18002cb2d  cmp     eax, 2
0x18002cb30  jnz     loc_18002CA45
0x18002cb36  add     rbx, 10h
0x18002cb3a  jmp     loc_18002CA4E
0x18002cb3f  mov     r9d, 5; cchCount2
0x18002cb45  mov     [rsp+68h+bIgnoreCase], ebp; bIgnoreCase
0x18002cb49  mov     edx, r9d; cchCount1
0x18002cb4c  lea     rcx, aFile_8; "file:"
0x18002cb53  mov     r8, rbx; lpString2
0x18002cb56  call    cs:__imp_CompareStringOrdinal
0x18002cb5c  cmp     eax, 2
0x18002cb5f  jnz     loc_18002CA4E
0x18002cb65  add     rbx, 0Ah
0x18002cb69  jmp     loc_18002CA4E
0x18002cb6e  movzx   eax, word ptr [r14+rsi*2]
0x18002cb73  cmp     [rdi+rsi*2], ax
0x18002cb77  jz      short loc_18002CB0C
0x18002cb79  jmp     loc_18002C9A0
```
