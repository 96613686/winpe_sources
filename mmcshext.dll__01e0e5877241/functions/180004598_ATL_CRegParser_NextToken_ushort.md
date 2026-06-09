# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180004598`
- end: `0x180004720`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `392`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fe8`
- `0x180004d3c`
- `0x180005130`
- `0x180006074`

## callees

- `0x180004598`

## import_xrefs

- `USER32!CharNextW` at `0x1800045cd`
- `USER32!CharNextW` at `0x1800045f3`
- `USER32!CharNextW` at `0x18000460d`
- `USER32!CharNextW` at `0x180004625`
- `USER32!CharNextW` at `0x180004634`
- `USER32!CharNextW` at `0x18000469a`
- `USER32!CharNextW` at `0x1800046bf`
- `USER32!CharNextW` at `0x1800045cd`
- `USER32!CharNextW` at `0x1800045f3`
- `USER32!CharNextW` at `0x18000460d`
- `USER32!CharNextW` at `0x180004625`
- `USER32!CharNextW` at `0x180004634`
- `USER32!CharNextW` at `0x18000469a`
- `USER32!CharNextW` at `0x1800046bf`

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
0x180004598  push    rbx
0x18000459a  push    rbp
0x18000459b  push    rsi
0x18000459c  push    rdi
0x18000459d  push    r14
0x18000459f  sub     rsp, 20h
0x1800045a3  mov     rsi, rdx
0x1800045a6  mov     rdi, rcx
0x1800045a9  mov     rbx, [rdi]
0x1800045ac  movzx   ecx, word ptr [rbx]
0x1800045af  mov     r8d, ecx
0x1800045b2  sub     r8d, 9
0x1800045b6  jz      short loc_1800045CA
0x1800045b8  sub     r8d, 1
0x1800045bc  jz      short loc_1800045CA
0x1800045be  sub     r8d, 3
0x1800045c2  jz      short loc_1800045CA
0x1800045c4  cmp     r8d, 13h
0x1800045c8  jnz     short loc_1800045D8
0x1800045ca  mov     rcx, rbx; lpsz
0x1800045cd  call    cs:__imp_CharNextW
0x1800045d3  mov     [rdi], rax
0x1800045d6  jmp     short loc_1800045A9
0x1800045d8  xor     eax, eax
0x1800045da  cmp     ax, cx
0x1800045dd  jz      short loc_180004656
0x1800045df  lea     r14d, [rax+27h]
0x1800045e3  mov     rbp, rsi
0x1800045e6  cmp     r14w, cx
0x1800045ea  jnz     loc_1800046A5
0x1800045f0  mov     rcx, rbx; lpsz
0x1800045f3  call    cs:__imp_CharNextW
0x1800045f9  mov     [rdi], rax
0x1800045fc  mov     rdx, rax
0x1800045ff  movzx   ecx, word ptr [rax]
0x180004602  jmp     short loc_18000467F
0x180004604  cmp     r14w, cx
0x180004608  jnz     short loc_180004619
0x18000460a  mov     rcx, rdx; lpsz
0x18000460d  call    cs:__imp_CharNextW
0x180004613  cmp     r14w, [rax]
0x180004617  jnz     short loc_18000468A
0x180004619  mov     rbx, [rdi]
0x18000461c  cmp     r14w, [rbx]
0x180004620  jnz     short loc_180004631
0x180004622  mov     rcx, rbx; lpsz
0x180004625  call    cs:__imp_CharNextW
0x18000462b  mov     rbx, rax
0x18000462e  mov     [rdi], rax
0x180004631  mov     rcx, rbx; lpsz
0x180004634  call    cs:__imp_CharNextW
0x18000463a  mov     rdx, rax
0x18000463d  mov     [rdi], rax
0x180004640  sub     rax, rbx
0x180004643  sar     rax, 1
0x180004646  lea     rcx, [rsi+rax*2]
0x18000464a  lea     rax, [rbp+2000h]
0x180004651  cmp     rcx, rax
0x180004654  jb      short loc_180004677
0x180004656  mov     eax, 80020009h
0x18000465b  add     rsp, 20h
0x18000465f  pop     r14
0x180004661  pop     rdi
0x180004662  pop     rsi
0x180004663  pop     rbp
0x180004664  pop     rbx
0x180004665  retn
0x180004666  movzx   eax, word ptr [rbx]
0x180004669  add     rbx, 2
0x18000466d  mov     [rsi], ax
0x180004670  add     rsi, 2
0x180004674  mov     rdx, [rdi]
0x180004677  cmp     rbx, rdx
0x18000467a  jb      short loc_180004666
0x18000467c  movzx   ecx, word ptr [rdx]
0x18000467f  xor     eax, eax
0x180004681  cmp     ax, cx
0x180004684  jnz     loc_180004604
0x18000468a  mov     rcx, [rdi]
0x18000468d  xor     eax, eax
0x18000468f  cmp     ax, [rcx]
0x180004692  jz      short loc_180004656
0x180004694  mov     [rsi], ax
0x180004697  mov     rcx, [rdi]; lpsz
0x18000469a  call    cs:__imp_CharNextW
0x1800046a0  mov     [rdi], rax
0x1800046a3  jmp     short loc_180004719
0x1800046a5  movzx   ecx, cx
0x1800046a8  sub     ecx, 9
0x1800046ab  jz      short loc_180004714
0x1800046ad  sub     ecx, 1
0x1800046b0  jz      short loc_180004714
0x1800046b2  sub     ecx, 3
0x1800046b5  jz      short loc_180004714
0x1800046b7  cmp     ecx, 13h
0x1800046ba  jz      short loc_180004714
0x1800046bc  mov     rcx, rbx; lpsz
0x1800046bf  call    cs:__imp_CharNextW
0x1800046c5  mov     rcx, rax
0x1800046c8  mov     [rdi], rax
0x1800046cb  sub     rcx, rbx
0x1800046ce  sar     rcx, 1
0x1800046d1  lea     rdx, [rsi+rcx*2]
0x1800046d5  lea     rcx, [rbp+2000h]
0x1800046dc  cmp     rdx, rcx
0x1800046df  jnb     loc_180004656
0x1800046e5  mov     rcx, rbx
0x1800046e8  cmp     rbx, rax
0x1800046eb  jnb     short loc_180004705
0x1800046ed  movzx   eax, word ptr [rcx]
0x1800046f0  add     rcx, 2
0x1800046f4  mov     [rsi], ax
0x1800046f7  add     rsi, 2
0x1800046fb  mov     rbx, [rdi]
0x1800046fe  cmp     rcx, rbx
0x180004701  jb      short loc_1800046ED
0x180004703  jmp     short loc_180004708
0x180004705  mov     rbx, rax
0x180004708  xor     eax, eax
0x18000470a  cmp     ax, [rbx]
0x18000470d  jz      short loc_180004714
0x18000470f  movzx   ecx, word ptr [rbx]
0x180004712  jmp     short loc_1800046A5
0x180004714  xor     eax, eax
0x180004716  mov     [rsi], ax
0x180004719  xor     eax, eax
0x18000471b  jmp     loc_18000465B
```
