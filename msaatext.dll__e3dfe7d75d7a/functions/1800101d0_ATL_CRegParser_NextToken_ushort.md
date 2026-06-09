# ATL::CRegParser::NextToken(ushort *)

- ea: `0x1800101d0`
- end: `0x180010358`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e3f4`
- `0x180010c3c`
- `0x180011038`
- `0x180012064`

## callees

- `0x1800101d0`

## import_xrefs

- `USER32!CharNextW` at `0x180010205`
- `USER32!CharNextW` at `0x18001022b`
- `USER32!CharNextW` at `0x180010245`
- `USER32!CharNextW` at `0x18001025d`
- `USER32!CharNextW` at `0x18001026c`
- `USER32!CharNextW` at `0x1800102d2`
- `USER32!CharNextW` at `0x1800102f7`
- `USER32!CharNextW` at `0x180010205`
- `USER32!CharNextW` at `0x18001022b`
- `USER32!CharNextW` at `0x180010245`
- `USER32!CharNextW` at `0x18001025d`
- `USER32!CharNextW` at `0x18001026c`
- `USER32!CharNextW` at `0x1800102d2`
- `USER32!CharNextW` at `0x1800102f7`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(LPCWSTR *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rbx
  WCHAR v5; // cx
  unsigned __int16 *v6; // rbp
  LPWSTR v7; // rax
  LPWSTR v8; // rdx
  WCHAR i; // cx
  const WCHAR *v10; // rbx
  unsigned __int16 v12; // ax
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  LPWSTR v16; // rax
  const WCHAR *v17; // rcx
  unsigned __int16 v18; // ax

  while ( 1 )
  {
    v4 = *this;
    v5 = **this;
    if ( v5 != 9 && **this != 10 && **this != 13 && **this != 32 )
      break;
    *this = CharNextW(*this);
  }
  if ( !v5 )
    return 2147614729LL;
  v6 = a2;
  if ( v5 != 39 )
  {
    while ( 1 )
    {
      v13 = v5 - 9;
      if ( !v13 )
        break;
      v14 = v13 - 1;
      if ( !v14 )
        break;
      v15 = v14 - 3;
      if ( !v15 || v15 == 19 )
        break;
      v16 = CharNextW(v4);
      *this = v16;
      if ( &a2[v16 - v4] >= v6 + 4096 )
        return 2147614729LL;
      v17 = v4;
      if ( v4 >= v16 )
      {
        v4 = v16;
      }
      else
      {
        do
        {
          v18 = *v17++;
          *a2++ = v18;
          v4 = *this;
        }
        while ( v17 < *this );
      }
      if ( !*v4 )
        break;
      v5 = *v4;
    }
    *a2 = 0;
    return 0;
  }
  v7 = CharNextW(*this);
  *this = v7;
  v8 = v7;
  for ( i = *v7; i && (i != 39 || *CharNextW(v8) == 39); i = *v8 )
  {
    v10 = *this;
    if ( **this == 39 )
    {
      v10 = CharNextW(*this);
      *this = v10;
    }
    v8 = CharNextW(v10);
    *this = v8;
    if ( &a2[v8 - v10] >= v6 + 4096 )
      return 2147614729LL;
    while ( v10 < v8 )
    {
      v12 = *v10++;
      *a2++ = v12;
      v8 = (LPWSTR)*this;
    }
  }
  if ( !**this )
    return 2147614729LL;
  *a2 = 0;
  *this = CharNextW(*this);
  return 0;
}

```

## disassembly

```asm
0x1800101d0  push    rbx
0x1800101d2  push    rbp
0x1800101d3  push    rsi
0x1800101d4  push    rdi
0x1800101d5  push    r14
0x1800101d7  sub     rsp, 20h
0x1800101db  mov     rsi, rdx
0x1800101de  mov     rdi, rcx
0x1800101e1  mov     rbx, [rdi]
0x1800101e4  movzx   ecx, word ptr [rbx]
0x1800101e7  mov     r8d, ecx
0x1800101ea  sub     r8d, 9
0x1800101ee  jz      short loc_180010202
0x1800101f0  sub     r8d, 1
0x1800101f4  jz      short loc_180010202
0x1800101f6  sub     r8d, 3
0x1800101fa  jz      short loc_180010202
0x1800101fc  cmp     r8d, 13h
0x180010200  jnz     short loc_180010210
0x180010202  mov     rcx, rbx; lpsz
0x180010205  call    cs:__imp_CharNextW
0x18001020b  mov     [rdi], rax
0x18001020e  jmp     short loc_1800101E1
0x180010210  xor     eax, eax
0x180010212  cmp     ax, cx
0x180010215  jz      short loc_18001028E
0x180010217  lea     r14d, [rax+27h]
0x18001021b  mov     rbp, rsi
0x18001021e  cmp     r14w, cx
0x180010222  jnz     loc_1800102DD
0x180010228  mov     rcx, rbx; lpsz
0x18001022b  call    cs:__imp_CharNextW
0x180010231  mov     [rdi], rax
0x180010234  mov     rdx, rax
0x180010237  movzx   ecx, word ptr [rax]
0x18001023a  jmp     short loc_1800102B7
0x18001023c  cmp     r14w, cx
0x180010240  jnz     short loc_180010251
0x180010242  mov     rcx, rdx; lpsz
0x180010245  call    cs:__imp_CharNextW
0x18001024b  cmp     r14w, [rax]
0x18001024f  jnz     short loc_1800102C2
0x180010251  mov     rbx, [rdi]
0x180010254  cmp     r14w, [rbx]
0x180010258  jnz     short loc_180010269
0x18001025a  mov     rcx, rbx; lpsz
0x18001025d  call    cs:__imp_CharNextW
0x180010263  mov     rbx, rax
0x180010266  mov     [rdi], rax
0x180010269  mov     rcx, rbx; lpsz
0x18001026c  call    cs:__imp_CharNextW
0x180010272  mov     rdx, rax
0x180010275  mov     [rdi], rax
0x180010278  sub     rax, rbx
0x18001027b  sar     rax, 1
0x18001027e  lea     rcx, [rsi+rax*2]
0x180010282  lea     rax, [rbp+2000h]
0x180010289  cmp     rcx, rax
0x18001028c  jb      short loc_1800102AF
0x18001028e  mov     eax, 80020009h
0x180010293  add     rsp, 20h
0x180010297  pop     r14
0x180010299  pop     rdi
0x18001029a  pop     rsi
0x18001029b  pop     rbp
0x18001029c  pop     rbx
0x18001029d  retn
0x18001029e  movzx   eax, word ptr [rbx]
0x1800102a1  add     rbx, 2
0x1800102a5  mov     [rsi], ax
0x1800102a8  add     rsi, 2
0x1800102ac  mov     rdx, [rdi]
0x1800102af  cmp     rbx, rdx
0x1800102b2  jb      short loc_18001029E
0x1800102b4  movzx   ecx, word ptr [rdx]
0x1800102b7  xor     eax, eax
0x1800102b9  cmp     ax, cx
0x1800102bc  jnz     loc_18001023C
0x1800102c2  mov     rcx, [rdi]
0x1800102c5  xor     eax, eax
0x1800102c7  cmp     ax, [rcx]
0x1800102ca  jz      short loc_18001028E
0x1800102cc  mov     [rsi], ax
0x1800102cf  mov     rcx, [rdi]; lpsz
0x1800102d2  call    cs:__imp_CharNextW
0x1800102d8  mov     [rdi], rax
0x1800102db  jmp     short loc_180010351
0x1800102dd  movzx   ecx, cx
0x1800102e0  sub     ecx, 9
0x1800102e3  jz      short loc_18001034C
0x1800102e5  sub     ecx, 1
0x1800102e8  jz      short loc_18001034C
0x1800102ea  sub     ecx, 3
0x1800102ed  jz      short loc_18001034C
0x1800102ef  cmp     ecx, 13h
0x1800102f2  jz      short loc_18001034C
0x1800102f4  mov     rcx, rbx; lpsz
0x1800102f7  call    cs:__imp_CharNextW
0x1800102fd  mov     rcx, rax
0x180010300  mov     [rdi], rax
0x180010303  sub     rcx, rbx
0x180010306  sar     rcx, 1
0x180010309  lea     rdx, [rsi+rcx*2]
0x18001030d  lea     rcx, [rbp+2000h]
0x180010314  cmp     rdx, rcx
0x180010317  jnb     loc_18001028E
0x18001031d  mov     rcx, rbx
0x180010320  cmp     rbx, rax
0x180010323  jnb     short loc_18001033D
0x180010325  movzx   eax, word ptr [rcx]
0x180010328  add     rcx, 2
0x18001032c  mov     [rsi], ax
0x18001032f  add     rsi, 2
0x180010333  mov     rbx, [rdi]
0x180010336  cmp     rcx, rbx
0x180010339  jb      short loc_180010325
0x18001033b  jmp     short loc_180010340
0x18001033d  mov     rbx, rax
0x180010340  xor     eax, eax
0x180010342  cmp     ax, [rbx]
0x180010345  jz      short loc_18001034C
0x180010347  movzx   ecx, word ptr [rbx]
0x18001034a  jmp     short loc_1800102DD
0x18001034c  xor     eax, eax
0x18001034e  mov     [rsi], ax
0x180010351  xor     eax, eax
0x180010353  jmp     loc_180010293
```
