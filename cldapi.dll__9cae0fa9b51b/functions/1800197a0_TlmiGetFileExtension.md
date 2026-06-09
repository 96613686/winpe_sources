# TlmiGetFileExtension

- ea: `0x1800197a0`
- end: `0x180019858`
- name: `TlmiGetFileExtension`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018564`

## callees

- `0x1800197a0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800197ca`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800197ca`

## pseudocode

```c
__int64 __fastcall TlmiGetFileExtension(__int64 a1, const wchar_t *a2)
{
  unsigned __int16 v4; // si
  size_t v5; // rax
  const wchar_t *v6; // rcx
  const wchar_t *v7; // rax
  __int128 v8; // xmm0
  __int16 v9; // cx

  *(_OWORD *)a1 = 0;
  if ( !a2 )
    goto LABEL_15;
  v4 = 0;
  v5 = wcsnlen(a2, 0x8000u);
  if ( a2[v5] )
    goto LABEL_15;
  v6 = &a2[v5 - 1];
  v7 = v6;
  if ( v6 >= a2 )
  {
    while ( 1 )
    {
      if ( *v7 == 92 )
      {
LABEL_8:
        if ( v4 <= 0xFu )
          goto LABEL_11;
LABEL_9:
        v8 = *(_OWORD *)L"\"$";
        goto LABEL_16;
      }
      if ( v4 > 0xFu )
        goto LABEL_9;
      if ( *v7 == 46 )
        break;
      ++v4;
      if ( --v7 < a2 )
        goto LABEL_8;
    }
    ++v7;
  }
LABEL_11:
  if ( v7 > v6 || v7 < a2 || *v7 == 92 )
  {
LABEL_15:
    v8 = *(_OWORD *)&TlmNoFileExtension;
LABEL_16:
    *(_OWORD *)a1 = v8;
  }
  else
  {
    *(_QWORD *)(a1 + 8) = v7;
    v9 = (_WORD)v6 - (_WORD)v7 + 2;
    *(_WORD *)a1 = v9;
    *(_WORD *)(a1 + 2) = v9;
  }
  return a1;
}

```

## disassembly

```asm
0x1800197a0  push    rbx
0x1800197a2  push    rbp
0x1800197a3  push    rsi
0x1800197a4  push    rdi
0x1800197a5  sub     rsp, 28h
0x1800197a9  xor     ebp, ebp
0x1800197ab  xorps   xmm0, xmm0
0x1800197ae  mov     rdi, rdx
0x1800197b1  mov     rbx, rcx
0x1800197b4  movups  xmmword ptr [rcx], xmm0
0x1800197b7  test    rdx, rdx
0x1800197ba  jz      loc_180019840
0x1800197c0  mov     edx, 8000h; MaxCount
0x1800197c5  mov     rcx, rdi; Source
0x1800197c8  mov     esi, ebp
0x1800197ca  call    cs:__imp_wcsnlen
0x1800197d1  nop     dword ptr [rax+rax+00h]
0x1800197d6  cmp     [rdi+rax*2], bp
0x1800197da  jnz     short loc_180019840
0x1800197dc  dec     rax
0x1800197df  lea     edx, [rbp+2]
0x1800197e2  lea     rcx, [rdi+rax*2]
0x1800197e6  mov     rax, rcx
0x1800197e9  cmp     rcx, rdi
0x1800197ec  jb      short loc_18001981D
0x1800197ee  cmp     word ptr [rax], 5Ch ; '\'
0x1800197f2  jz      short loc_18001980B
0x1800197f4  cmp     si, 0Fh
0x1800197f8  ja      short loc_180019811
0x1800197fa  cmp     word ptr [rax], 2Eh ; '.'
0x1800197fe  jz      short loc_18001981A
0x180019800  inc     si
0x180019803  sub     rax, rdx
0x180019806  cmp     rax, rdi
0x180019809  jnb     short loc_1800197EE
0x18001980b  cmp     si, 0Fh
0x18001980f  jbe     short loc_18001981D
0x180019811  movups  xmm0, xmmword ptr cs:TlmLongFileExtension; "\"$"
0x180019818  jmp     short loc_180019847
0x18001981a  add     rax, rdx
0x18001981d  cmp     rax, rcx
0x180019820  ja      short loc_180019840
0x180019822  cmp     rax, rdi
0x180019825  jb      short loc_180019840
0x180019827  cmp     word ptr [rax], 5Ch ; '\'
0x18001982b  jz      short loc_180019840
0x18001982d  sub     cx, ax
0x180019830  mov     [rbx+8], rax
0x180019834  add     cx, dx
0x180019837  mov     [rbx], cx
0x18001983a  mov     [rbx+2], cx
0x18001983e  jmp     short loc_18001984B
0x180019840  movups  xmm0, xmmword ptr cs:TlmNoFileExtension
0x180019847  movdqu  xmmword ptr [rbx], xmm0
0x18001984b  mov     rax, rbx
0x18001984e  add     rsp, 28h
0x180019852  pop     rdi
0x180019853  pop     rsi
0x180019854  pop     rbp
0x180019855  pop     rbx
0x180019856  retn
```
