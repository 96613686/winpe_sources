# CXMLTag::ParseDateISO8601ToSystemTime(wchar_t *,_SYSTEMTIME *)

- ea: `0x180021a2c`
- end: `0x180021bc1`
- name: `?ParseDateISO8601ToSystemTime@CXMLTag@@AEAA_NPEA_WPEAU_SYSTEMTIME@@@Z`
- size: `405`
- prototype: `bool(CXMLTag *__hidden this, wchar_t *, struct _SYSTEMTIME *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000fb70`
- `0x180021bc8`

## callees

- `0x180021a2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ab9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ad1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ae4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b81`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b8f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b9e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ab9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ad1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021ae4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b81`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b8f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180021b9e`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021a9a`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021b3b`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021a9a`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180021b3b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021a5c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180021a5c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021a4d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021b50`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021a4d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180021b50`

## pseudocode

```c
char __fastcall CXMLTag::ParseDateISO8601ToSystemTime(CXMLTag *this, wchar_t *a2, struct _SYSTEMTIME *a3)
{
  wchar_t *v5; // r14
  wchar_t *v6; // rax
  wchar_t *v7; // rbx
  __int64 v8; // rax
  int j; // ebx
  wchar_t v10; // bx
  wchar_t v11; // bx
  __int64 v13; // rax
  int i; // esi
  wchar_t *v15; // rcx

  v5 = wcschr(a2, 0x2Du);
  v6 = wcsrchr(a2, 0x2Du);
  v7 = v6;
  if ( v5 )
  {
    if ( v6 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a2[v13] );
      if ( v13 != 10 )
        return 0;
      for ( i = 0; i < 10; ++i )
      {
        v15 = &a2[i];
        if ( v15 != v5 && v15 != v7 && !(unsigned int)_o_iswdigit(*v15) )
          return 0;
      }
      if ( wcschr(v5 + 1, 0x2Du) != v7 || (unsigned int)(v5 - a2) != 4 || (unsigned int)(v7 - a2) != 7 )
        return 0;
      *v5 = 0;
      *v7 = 0;
      a3->wYear = _o__wtoi(a2);
      a3->wMonth = _o__wtoi(a2 + 5);
      a3->wDay = _o__wtoi(a2 + 8);
      *(_QWORD *)&a3->wHour = 0;
      *v5 = 45;
      *v7 = 45;
    }
    return 1;
  }
  if ( v6 )
    return 1;
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  if ( v8 == 8 )
  {
    for ( j = 0; j < 8; ++j )
    {
      if ( !(unsigned int)_o_iswdigit(a2[j]) )
        return 0;
    }
    v10 = a2[4];
    a2[4] = 0;
    a3->wYear = _o__wtoi(a2);
    a2[4] = v10;
    v11 = a2[6];
    a2[6] = 0;
    a3->wMonth = _o__wtoi(a2 + 4);
    a2[6] = v11;
    a3->wDay = _o__wtoi(a2 + 6);
    *(_QWORD *)&a3->wHour = 0;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180021a2c  push    rbx
0x180021a2e  push    rbp
0x180021a2f  push    rsi
0x180021a30  push    rdi
0x180021a31  push    r12
0x180021a33  push    r14
0x180021a35  push    r15
0x180021a37  sub     rsp, 20h
0x180021a3b  mov     rdi, rdx
0x180021a3e  mov     r12d, 2Dh ; '-'
0x180021a44  mov     edx, r12d; Ch
0x180021a47  mov     rcx, rdi; Str
0x180021a4a  mov     r15, r8
0x180021a4d  call    cs:__imp_wcschr
0x180021a53  mov     edx, r12d; Ch
0x180021a56  mov     rcx, rdi; Str
0x180021a59  mov     r14, rax
0x180021a5c  call    cs:__imp_wcsrchr
0x180021a62  xor     ebp, ebp
0x180021a64  mov     rbx, rax
0x180021a67  test    r14, r14
0x180021a6a  jnz     loc_180021B04
0x180021a70  test    rax, rax
0x180021a73  jnz     short loc_180021AF3
0x180021a75  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021a79  inc     rax
0x180021a7c  cmp     [rdi+rax*2], bp
0x180021a80  jnz     short loc_180021A79
0x180021a82  cmp     rax, 8
0x180021a86  jnz     loc_180021BBA
0x180021a8c  mov     ebx, ebp
0x180021a8e  cmp     ebx, 8
0x180021a91  jge     short loc_180021AAC
0x180021a93  movsxd  rcx, ebx
0x180021a96  movzx   ecx, word ptr [rdi+rcx*2]
0x180021a9a  call    cs:__imp__o_iswdigit
0x180021aa0  test    eax, eax
0x180021aa2  jz      loc_180021BBA
0x180021aa8  inc     ebx
0x180021aaa  jmp     short loc_180021A8E
0x180021aac  lea     rsi, [rdi+8]
0x180021ab0  mov     rcx, rdi
0x180021ab3  movzx   ebx, word ptr [rsi]
0x180021ab6  mov     [rsi], bp
0x180021ab9  call    cs:__imp__o__wtoi
0x180021abf  mov     [r15], ax
0x180021ac3  mov     rcx, rsi
0x180021ac6  mov     [rsi], bx
0x180021ac9  movzx   ebx, word ptr [rdi+0Ch]
0x180021acd  mov     [rdi+0Ch], bp
0x180021ad1  call    cs:__imp__o__wtoi
0x180021ad7  mov     [r15+2], ax
0x180021adc  lea     rcx, [rdi+0Ch]
0x180021ae0  mov     [rdi+0Ch], bx
0x180021ae4  call    cs:__imp__o__wtoi
0x180021aea  mov     [r15+6], ax
0x180021aef  mov     [r15+8], rbp
0x180021af3  mov     al, 1
0x180021af5  add     rsp, 20h
0x180021af9  pop     r15
0x180021afb  pop     r14
0x180021afd  pop     r12
0x180021aff  pop     rdi
0x180021b00  pop     rsi
0x180021b01  pop     rbp
0x180021b02  pop     rbx
0x180021b03  retn
0x180021b04  test    rbx, rbx
0x180021b07  jz      short loc_180021AF3
0x180021b09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021b0d  inc     rax
0x180021b10  cmp     [rdi+rax*2], bp
0x180021b14  jnz     short loc_180021B0D
0x180021b16  cmp     rax, 0Ah
0x180021b1a  jnz     loc_180021BBA
0x180021b20  mov     esi, ebp
0x180021b22  cmp     esi, 0Ah
0x180021b25  jge     short loc_180021B49
0x180021b27  movsxd  rax, esi
0x180021b2a  lea     rcx, [rdi+rax*2]
0x180021b2e  cmp     rcx, r14
0x180021b31  jz      short loc_180021B45
0x180021b33  cmp     rcx, rbx
0x180021b36  jz      short loc_180021B45
0x180021b38  movzx   ecx, word ptr [rcx]
0x180021b3b  call    cs:__imp__o_iswdigit
0x180021b41  test    eax, eax
0x180021b43  jz      short loc_180021BBA
0x180021b45  inc     esi
0x180021b47  jmp     short loc_180021B22
0x180021b49  mov     edx, r12d; Ch
0x180021b4c  lea     rcx, [r14+2]; Str
0x180021b50  call    cs:__imp_wcschr
0x180021b56  cmp     rax, rbx
0x180021b59  jnz     short loc_180021BBA
0x180021b5b  mov     rax, r14
0x180021b5e  sub     rax, rdi
0x180021b61  sar     rax, 1
0x180021b64  cmp     eax, 4
0x180021b67  jnz     short loc_180021BBA
0x180021b69  mov     rax, rbx
0x180021b6c  sub     rax, rdi
0x180021b6f  sar     rax, 1
0x180021b72  cmp     eax, 7
0x180021b75  jnz     short loc_180021BBA
0x180021b77  mov     [r14], bp
0x180021b7b  mov     rcx, rdi
0x180021b7e  mov     [rbx], bp
0x180021b81  call    cs:__imp__o__wtoi
0x180021b87  lea     rcx, [rdi+0Ah]
0x180021b8b  mov     [r15], ax
0x180021b8f  call    cs:__imp__o__wtoi
0x180021b95  lea     rcx, [rdi+10h]
0x180021b99  mov     [r15+2], ax
0x180021b9e  call    cs:__imp__o__wtoi
0x180021ba4  mov     [r15+6], ax
0x180021ba9  mov     [r15+8], rbp
0x180021bad  mov     [r14], r12w
0x180021bb1  mov     [rbx], r12w
0x180021bb5  jmp     loc_180021AF3
0x180021bba  xor     al, al
0x180021bbc  jmp     loc_180021AF5
```
