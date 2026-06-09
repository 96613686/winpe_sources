# Dither16InitScale

- ea: `0x18000707c`
- end: `0x18000723c`
- name: `Dither16InitScale`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006c1c`

## callees

- `0x18000707c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800070c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800070c6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800070bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800070bd`

## pseudocode

```c
char *Dither16InitScale()
{
  HGLOBAL v0; // rax
  unsigned int i; // [rsp+20h] [rbp-38h]
  unsigned int m; // [rsp+20h] [rbp-38h]
  unsigned int j; // [rsp+24h] [rbp-34h]
  unsigned int n; // [rsp+24h] [rbp-34h]
  unsigned int k; // [rsp+28h] [rbp-30h]
  unsigned int ii; // [rsp+28h] [rbp-30h]
  char *v8; // [rsp+30h] [rbp-28h]
  _WORD *v9; // [rsp+38h] [rbp-20h]
  _BYTE *v10; // [rsp+40h] [rbp-18h]

  v0 = GlobalAlloc(0x2002u, 0x1FA00u);
  v8 = (char *)GlobalLock(v0);
  if ( !v8 )
    return 0;
  v9 = v8;
  for ( i = 0; i < 0x20; ++i )
  {
    for ( j = 0; j < 0x20; ++j )
    {
      for ( k = 0; k < 0x20; ++k )
        *v9++ = 1600 * i + k + 40 * j;
    }
  }
  v10 = v8 + 0x10000;
  for ( m = 0; m < 0x28; ++m )
  {
    for ( n = 0; n < 0x28; ++n )
    {
      for ( ii = 0; ii < 0x28; ++ii )
      {
        _mm_lfence();
        *v10++ = *((_BYTE *)lookup775
                 + 35 * *((_DWORD *)rlevel + m)
                 + 5 * *((_DWORD *)glevel + n)
                 + *((_DWORD *)blevel + ii));
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000707c  sub     rsp, 58h
0x180007080  mov     [rsp+58h+var_28], 0
0x180007089  mov     [rsp+58h+var_18], 0
0x180007092  mov     [rsp+58h+var_20], 0
0x18000709b  mov     [rsp+58h+var_38], 0
0x1800070a3  mov     [rsp+58h+var_34], 0
0x1800070ab  mov     [rsp+58h+var_30], 0
0x1800070b3  mov     edx, 1FA00h; dwBytes
0x1800070b8  mov     ecx, 2002h; uFlags
0x1800070bd  call    cs:__imp_GlobalAlloc
0x1800070c3  mov     rcx, rax; hMem
0x1800070c6  call    cs:__imp_GlobalLock
0x1800070cc  mov     [rsp+58h+var_28], rax
0x1800070d1  cmp     [rsp+58h+var_28], 0
0x1800070d7  jnz     short loc_1800070E0
0x1800070d9  xor     eax, eax
0x1800070db  jmp     loc_180007237
0x1800070e0  mov     rax, [rsp+58h+var_28]
0x1800070e5  mov     [rsp+58h+var_20], rax
0x1800070ea  mov     [rsp+58h+var_38], 0
0x1800070f2  jmp     short loc_1800070FE
0x1800070f4  mov     eax, [rsp+58h+var_38]
0x1800070f8  inc     eax
0x1800070fa  mov     [rsp+58h+var_38], eax
0x1800070fe  cmp     [rsp+58h+var_38], 20h ; ' '
0x180007103  jnb     short loc_180007170
0x180007105  mov     [rsp+58h+var_34], 0
0x18000710d  jmp     short loc_180007119
0x18000710f  mov     eax, [rsp+58h+var_34]
0x180007113  inc     eax
0x180007115  mov     [rsp+58h+var_34], eax
0x180007119  cmp     [rsp+58h+var_34], 20h ; ' '
0x18000711e  jnb     short loc_18000716E
0x180007120  mov     [rsp+58h+var_30], 0
0x180007128  jmp     short loc_180007134
0x18000712a  mov     eax, [rsp+58h+var_30]
0x18000712e  inc     eax
0x180007130  mov     [rsp+58h+var_30], eax
0x180007134  cmp     [rsp+58h+var_30], 20h ; ' '
0x180007139  jnb     short loc_18000716C
0x18000713b  imul    eax, [rsp+58h+var_38], 640h
0x180007143  imul    ecx, [rsp+58h+var_34], 28h ; '('
0x180007148  mov     edx, [rsp+58h+var_30]
0x18000714c  add     edx, eax
0x18000714e  mov     eax, edx
0x180007150  add     ecx, eax
0x180007152  mov     eax, ecx
0x180007154  mov     rcx, [rsp+58h+var_20]
0x180007159  mov     [rcx], ax
0x18000715c  mov     rax, [rsp+58h+var_20]
0x180007161  add     rax, 2
0x180007165  mov     [rsp+58h+var_20], rax
0x18000716a  jmp     short loc_18000712A
0x18000716c  jmp     short loc_18000710F
0x18000716e  jmp     short loc_1800070F4
0x180007170  mov     rax, [rsp+58h+var_28]
0x180007175  add     rax, 10000h
0x18000717b  mov     [rsp+58h+var_18], rax
0x180007180  mov     [rsp+58h+var_38], 0
0x180007188  jmp     short loc_180007194
0x18000718a  mov     eax, [rsp+58h+var_38]
0x18000718e  inc     eax
0x180007190  mov     [rsp+58h+var_38], eax
0x180007194  cmp     [rsp+58h+var_38], 28h ; '('
0x180007199  jnb     loc_180007232
0x18000719f  mov     [rsp+58h+var_34], 0
0x1800071a7  jmp     short loc_1800071B3
0x1800071a9  mov     eax, [rsp+58h+var_34]
0x1800071ad  inc     eax
0x1800071af  mov     [rsp+58h+var_34], eax
0x1800071b3  cmp     [rsp+58h+var_34], 28h ; '('
0x1800071b8  jnb     short loc_18000722D
0x1800071ba  mov     [rsp+58h+var_30], 0
0x1800071c2  jmp     short loc_1800071CE
0x1800071c4  mov     eax, [rsp+58h+var_30]
0x1800071c8  inc     eax
0x1800071ca  mov     [rsp+58h+var_30], eax
0x1800071ce  cmp     [rsp+58h+var_30], 28h ; '('
0x1800071d3  jnb     short loc_180007228
0x1800071d5  lfence
0x1800071d8  mov     eax, [rsp+58h+var_38]
0x1800071dc  lea     rcx, rlevel
0x1800071e3  imul    eax, [rcx+rax*4], 23h ; '#'
0x1800071e7  mov     ecx, [rsp+58h+var_34]
0x1800071eb  lea     rdx, glevel
0x1800071f2  imul    ecx, [rdx+rcx*4], 5
0x1800071f6  add     eax, ecx
0x1800071f8  mov     ecx, [rsp+58h+var_30]
0x1800071fc  lea     rdx, blevel
0x180007203  add     eax, [rdx+rcx*4]
0x180007206  cdqe
0x180007208  lea     rcx, lookup775
0x18000720f  mov     rdx, [rsp+58h+var_18]
0x180007214  mov     al, [rcx+rax]
0x180007217  mov     [rdx], al
0x180007219  mov     rax, [rsp+58h+var_18]
0x18000721e  inc     rax
0x180007221  mov     [rsp+58h+var_18], rax
0x180007226  jmp     short loc_1800071C4
0x180007228  jmp     loc_1800071A9
0x18000722d  jmp     loc_18000718A
0x180007232  mov     rax, [rsp+58h+var_28]
0x180007237  add     rsp, 58h
0x18000723b  retn
```
