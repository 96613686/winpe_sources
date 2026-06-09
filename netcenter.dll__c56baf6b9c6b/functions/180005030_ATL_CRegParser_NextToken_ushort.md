# ATL::CRegParser::NextToken(ushort *)

- ea: `0x180005030`
- end: `0x180005187`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000441c`
- `0x1800055ec`
- `0x180005910`
- `0x180005f70`

## callees

- `0x180005030`
- `0x180006004`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005069`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005082`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000509a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800050a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005101`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005130`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005069`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005082`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000509a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800050a9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005101`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005130`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::NextToken(ATL::CRegParser *this, unsigned __int16 *a2)
{
  const WCHAR *v4; // rcx
  unsigned __int16 *v5; // rbp
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rsi
  LPWSTR v8; // rax
  __int64 v9; // rdx
  int i; // ecx
  unsigned __int16 *v11; // rsi
  LPWSTR v12; // rax
  __int64 v13; // rdx
  int j; // ecx

  ATL::CRegParser::SkipWhiteSpace(this);
  v4 = *(const WCHAR **)this;
  if ( **(_WORD **)this )
  {
    v5 = a2 + 4096;
    if ( *v4 == 39 )
    {
      *(_QWORD *)this = CharNextW(v4);
      while ( 1 )
      {
        v6 = *(const WCHAR **)this;
        if ( !**(_WORD **)this || *v6 == 39 && *CharNextW(v6) != 39 )
          break;
        v7 = *(const WCHAR **)this;
        if ( **(_WORD **)this == 39 )
        {
          v7 = CharNextW(*(LPCWSTR *)this);
          *(_QWORD *)this = v7;
        }
        v8 = CharNextW(v7);
        *(_QWORD *)this = v8;
        v9 = v8 - v7;
        if ( &a2[v9 + 1] >= v5 )
          return 2147614729LL;
        for ( i = 0; i < (int)v9; ++a2 )
        {
          ++i;
          *a2 = *v7++;
        }
      }
      if ( **(_WORD **)this && a2 < v5 )
      {
        *a2 = 0;
        *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
        return 0;
      }
    }
    else
    {
      while ( 1 )
      {
        v11 = *(unsigned __int16 **)this;
        if ( !**(_WORD **)this || *v11 == 9 || *v11 == 10 || *v11 == 13 || *v11 == 32 )
          break;
        v12 = CharNextW(*(LPCWSTR *)this);
        *(_QWORD *)this = v12;
        v13 = v12 - v11;
        if ( &a2[v13 + 1] >= v5 )
          return 2147614729LL;
        for ( j = 0; j < (int)v13; ++a2 )
        {
          ++j;
          *a2 = *v11++;
        }
      }
      if ( a2 < v5 )
      {
        *a2 = 0;
        return 0;
      }
    }
  }
  return 2147614729LL;
}

```

## disassembly

```asm
0x180005030  push    rbx
0x180005032  push    rbp
0x180005033  push    rsi
0x180005034  push    rdi
0x180005035  push    r14
0x180005037  sub     rsp, 20h
0x18000503b  mov     rbx, rdx
0x18000503e  mov     rdi, rcx
0x180005041  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180005046  mov     rcx, [rdi]; lpsz
0x180005049  xor     eax, eax
0x18000504b  cmp     ax, [rcx]
0x18000504e  jz      loc_180005177
0x180005054  lea     r14d, [rax+27h]
0x180005058  lea     rbp, [rbx+2000h]
0x18000505f  cmp     r14w, [rcx]
0x180005063  jnz     loc_18000510C
0x180005069  call    cs:__imp_CharNextW
0x18000506f  mov     [rdi], rax
0x180005072  mov     rcx, [rdi]; lpsz
0x180005075  xor     eax, eax
0x180005077  cmp     ax, [rcx]
0x18000507a  jz      short loc_1800050E8
0x18000507c  cmp     r14w, [rcx]
0x180005080  jnz     short loc_18000508E
0x180005082  call    cs:__imp_CharNextW
0x180005088  cmp     r14w, [rax]
0x18000508c  jnz     short loc_1800050E8
0x18000508e  mov     rsi, [rdi]
0x180005091  cmp     r14w, [rsi]
0x180005095  jnz     short loc_1800050A6
0x180005097  mov     rcx, rsi; lpsz
0x18000509a  call    cs:__imp_CharNextW
0x1800050a0  mov     rsi, rax
0x1800050a3  mov     [rdi], rax
0x1800050a6  mov     rcx, rsi; lpsz
0x1800050a9  call    cs:__imp_CharNextW
0x1800050af  mov     rdx, rax
0x1800050b2  mov     [rdi], rax
0x1800050b5  sub     rdx, rsi
0x1800050b8  sar     rdx, 1
0x1800050bb  lea     rcx, [rdx+1]
0x1800050bf  lea     rcx, [rbx+rcx*2]
0x1800050c3  cmp     rcx, rbp
0x1800050c6  jnb     loc_180005177
0x1800050cc  xor     ecx, ecx
0x1800050ce  test    edx, edx
0x1800050d0  jle     short loc_180005072
0x1800050d2  movzx   eax, word ptr [rsi]
0x1800050d5  inc     ecx
0x1800050d7  mov     [rbx], ax
0x1800050da  lea     rsi, [rsi+2]
0x1800050de  add     rbx, 2
0x1800050e2  cmp     ecx, edx
0x1800050e4  jl      short loc_1800050D2
0x1800050e6  jmp     short loc_180005072
0x1800050e8  mov     rcx, [rdi]
0x1800050eb  xor     eax, eax
0x1800050ed  cmp     ax, [rcx]
0x1800050f0  jz      loc_180005177
0x1800050f6  cmp     rbx, rbp
0x1800050f9  jnb     short loc_180005177
0x1800050fb  mov     [rbx], ax
0x1800050fe  mov     rcx, [rdi]; lpsz
0x180005101  call    cs:__imp_CharNextW
0x180005107  mov     [rdi], rax
0x18000510a  jmp     short loc_180005173
0x18000510c  mov     rsi, [rdi]
0x18000510f  xor     eax, eax
0x180005111  cmp     ax, [rsi]
0x180005114  jz      short loc_18000516B
0x180005116  movzx   ecx, word ptr [rsi]
0x180005119  sub     ecx, 9
0x18000511c  jz      short loc_18000516B
0x18000511e  sub     ecx, 1
0x180005121  jz      short loc_18000516B
0x180005123  sub     ecx, 3
0x180005126  jz      short loc_18000516B
0x180005128  cmp     ecx, 13h
0x18000512b  jz      short loc_18000516B
0x18000512d  mov     rcx, rsi; lpsz
0x180005130  call    cs:__imp_CharNextW
0x180005136  mov     rdx, rax
0x180005139  mov     [rdi], rax
0x18000513c  sub     rdx, rsi
0x18000513f  sar     rdx, 1
0x180005142  lea     rcx, [rdx+1]
0x180005146  lea     rcx, [rbx+rcx*2]
0x18000514a  cmp     rcx, rbp
0x18000514d  jnb     short loc_180005177
0x18000514f  xor     ecx, ecx
0x180005151  test    edx, edx
0x180005153  jle     short loc_18000510C
0x180005155  movzx   eax, word ptr [rsi]
0x180005158  inc     ecx
0x18000515a  mov     [rbx], ax
0x18000515d  lea     rsi, [rsi+2]
0x180005161  add     rbx, 2
0x180005165  cmp     ecx, edx
0x180005167  jl      short loc_180005155
0x180005169  jmp     short loc_18000510C
0x18000516b  cmp     rbx, rbp
0x18000516e  jnb     short loc_180005177
0x180005170  mov     [rbx], ax
0x180005173  xor     eax, eax
0x180005175  jmp     short loc_18000517C
0x180005177  mov     eax, 80020009h
0x18000517c  add     rsp, 20h
0x180005180  pop     r14
0x180005182  pop     rdi
0x180005183  pop     rsi
0x180005184  pop     rbp
0x180005185  pop     rbx
0x180005186  retn
```
