# ATL::CRegParser::NextToken(ushort *)

- ea: `0x18000cf14`
- end: `0x18000d06b`
- name: `?NextToken@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `343`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c0c8`
- `0x18000d45c`
- `0x18000d764`
- `0x18000ddbc`

## callees

- `0x18000cf14`
- `0x18000de50`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf4d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf7e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf8d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cfe5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d014`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf4d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf66`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf7e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cf8d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000cfe5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d014`

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
0x18000cf14  push    rbx
0x18000cf16  push    rbp
0x18000cf17  push    rsi
0x18000cf18  push    rdi
0x18000cf19  push    r14
0x18000cf1b  sub     rsp, 20h
0x18000cf1f  mov     rbx, rdx
0x18000cf22  mov     rdi, rcx
0x18000cf25  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000cf2a  mov     rcx, [rdi]; lpsz
0x18000cf2d  xor     eax, eax
0x18000cf2f  cmp     ax, [rcx]
0x18000cf32  jz      loc_18000D05B
0x18000cf38  lea     r14d, [rax+27h]
0x18000cf3c  lea     rbp, [rbx+2000h]
0x18000cf43  cmp     r14w, [rcx]
0x18000cf47  jnz     loc_18000CFF0
0x18000cf4d  call    cs:__imp_CharNextW
0x18000cf53  mov     [rdi], rax
0x18000cf56  mov     rcx, [rdi]; lpsz
0x18000cf59  xor     eax, eax
0x18000cf5b  cmp     ax, [rcx]
0x18000cf5e  jz      short loc_18000CFCC
0x18000cf60  cmp     r14w, [rcx]
0x18000cf64  jnz     short loc_18000CF72
0x18000cf66  call    cs:__imp_CharNextW
0x18000cf6c  cmp     r14w, [rax]
0x18000cf70  jnz     short loc_18000CFCC
0x18000cf72  mov     rsi, [rdi]
0x18000cf75  cmp     r14w, [rsi]
0x18000cf79  jnz     short loc_18000CF8A
0x18000cf7b  mov     rcx, rsi; lpsz
0x18000cf7e  call    cs:__imp_CharNextW
0x18000cf84  mov     rsi, rax
0x18000cf87  mov     [rdi], rax
0x18000cf8a  mov     rcx, rsi; lpsz
0x18000cf8d  call    cs:__imp_CharNextW
0x18000cf93  mov     rdx, rax
0x18000cf96  mov     [rdi], rax
0x18000cf99  sub     rdx, rsi
0x18000cf9c  sar     rdx, 1
0x18000cf9f  lea     rcx, [rdx+1]
0x18000cfa3  lea     rcx, [rbx+rcx*2]
0x18000cfa7  cmp     rcx, rbp
0x18000cfaa  jnb     loc_18000D05B
0x18000cfb0  xor     ecx, ecx
0x18000cfb2  test    edx, edx
0x18000cfb4  jle     short loc_18000CF56
0x18000cfb6  movzx   eax, word ptr [rsi]
0x18000cfb9  inc     ecx
0x18000cfbb  mov     [rbx], ax
0x18000cfbe  lea     rsi, [rsi+2]
0x18000cfc2  add     rbx, 2
0x18000cfc6  cmp     ecx, edx
0x18000cfc8  jl      short loc_18000CFB6
0x18000cfca  jmp     short loc_18000CF56
0x18000cfcc  mov     rcx, [rdi]
0x18000cfcf  xor     eax, eax
0x18000cfd1  cmp     ax, [rcx]
0x18000cfd4  jz      loc_18000D05B
0x18000cfda  cmp     rbx, rbp
0x18000cfdd  jnb     short loc_18000D05B
0x18000cfdf  mov     [rbx], ax
0x18000cfe2  mov     rcx, [rdi]; lpsz
0x18000cfe5  call    cs:__imp_CharNextW
0x18000cfeb  mov     [rdi], rax
0x18000cfee  jmp     short loc_18000D057
0x18000cff0  mov     rsi, [rdi]
0x18000cff3  xor     eax, eax
0x18000cff5  cmp     ax, [rsi]
0x18000cff8  jz      short loc_18000D04F
0x18000cffa  movzx   ecx, word ptr [rsi]
0x18000cffd  sub     ecx, 9
0x18000d000  jz      short loc_18000D04F
0x18000d002  sub     ecx, 1
0x18000d005  jz      short loc_18000D04F
0x18000d007  sub     ecx, 3
0x18000d00a  jz      short loc_18000D04F
0x18000d00c  cmp     ecx, 13h
0x18000d00f  jz      short loc_18000D04F
0x18000d011  mov     rcx, rsi; lpsz
0x18000d014  call    cs:__imp_CharNextW
0x18000d01a  mov     rdx, rax
0x18000d01d  mov     [rdi], rax
0x18000d020  sub     rdx, rsi
0x18000d023  sar     rdx, 1
0x18000d026  lea     rcx, [rdx+1]
0x18000d02a  lea     rcx, [rbx+rcx*2]
0x18000d02e  cmp     rcx, rbp
0x18000d031  jnb     short loc_18000D05B
0x18000d033  xor     ecx, ecx
0x18000d035  test    edx, edx
0x18000d037  jle     short loc_18000CFF0
0x18000d039  movzx   eax, word ptr [rsi]
0x18000d03c  inc     ecx
0x18000d03e  mov     [rbx], ax
0x18000d041  lea     rsi, [rsi+2]
0x18000d045  add     rbx, 2
0x18000d049  cmp     ecx, edx
0x18000d04b  jl      short loc_18000D039
0x18000d04d  jmp     short loc_18000CFF0
0x18000d04f  cmp     rbx, rbp
0x18000d052  jnb     short loc_18000D05B
0x18000d054  mov     [rbx], ax
0x18000d057  xor     eax, eax
0x18000d059  jmp     short loc_18000D060
0x18000d05b  mov     eax, 80020009h
0x18000d060  add     rsp, 20h
0x18000d064  pop     r14
0x18000d066  pop     rdi
0x18000d067  pop     rsi
0x18000d068  pop     rbp
0x18000d069  pop     rbx
0x18000d06a  retn
```
