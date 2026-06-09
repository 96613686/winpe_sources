# ParseProperty(ushort const * &,CTempBufferRef<ushort> &)

- ea: `0x1400066d8`
- end: `0x14000684a`
- name: `?ParseProperty@@YA?AW4Bool@@AEAPEBGAEAV?$CTempBufferRef@G@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(const unsigned __int16 **, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400011e4`

## callees

- `0x140003c48`
- `0x1400066d8`
- `0x140007110`
- `0x140008768`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140006811`
- `KERNEL32!GlobalAlloc` at `0x140006811`
- `USER32!IsCharAlphaNumericW` at `0x1400066f7`
- `USER32!IsCharAlphaNumericW` at `0x1400066f7`

## pseudocode

```c
__int64 __fastcall ParseProperty(const unsigned __int16 **a1, __int64 a2)
{
  WCHAR *v2; // rbx
  WCHAR v5; // ax
  unsigned __int16 *v6; // rbx
  __int16 v7; // r8
  unsigned __int16 v8; // dx
  int v9; // r9d
  unsigned __int16 *v10; // rdx
  signed int v11; // esi
  signed int v13; // ecx
  SIZE_T v14; // rax
  HGLOBAL v15; // rax

  v2 = (WCHAR *)*a1;
  if ( **a1 != 37 && !IsCharAlphaNumericW(*v2) )
    return 0;
  while ( 1 )
  {
    v5 = *v2;
    if ( !*v2 || v5 == 32 || v5 == 61 )
      break;
    ++v2;
  }
  if ( *v2 != 61 )
    return 0;
  v6 = v2 + 1;
  v7 = 34;
  v8 = *v6;
  if ( *v6 != 34 )
  {
    v7 = 32;
    v9 = 0;
    goto LABEL_19;
  }
  v9 = 1;
  ++v6;
  while ( 1 )
  {
    v8 = *v6;
LABEL_19:
    if ( !v8 )
      break;
    if ( v7 == v8 )
    {
      if ( !v9 )
        break;
      v10 = v6 + 1;
      if ( v7 != v6[1] )
        break;
      ++v6;
      v8 = *v10;
    }
    if ( v8 )
      ++v6;
  }
  if ( *v6 && v7 != *v6 )
    return 0;
  if ( v9 && *v6 )
    ++v6;
  v11 = v6 - *a1 + 1;
  if ( (unsigned int)v11 > 0x7FFFFFFF )
  {
    ReportErrorToDebugOutput((BYTE *)L"Property value is too long.\r\n", 0);
    return 0;
  }
  v13 = *(_DWORD *)(a2 + 8);
  if ( v13 < v11 )
  {
    if ( v13 > *(_DWORD *)(a2 + 12) )
      operator delete(*(void **)a2);
    *(_DWORD *)(a2 + 8) = v11;
    if ( v11 <= *(_DWORD *)(a2 + 12) )
    {
      v15 = (HGLOBAL)(a2 + 16);
    }
    else
    {
      v14 = 2LL * v11;
      if ( !is_mul_ok(v11, 2u) )
        v14 = -1;
      v15 = GlobalAlloc(0, v14);
    }
    *(_QWORD *)a2 = v15;
    if ( !v15 )
      return 0;
  }
  StringCchCopyNW(*(unsigned __int16 **)a2, *(int *)(a2 + 8), *a1, v11);
  if ( *v6 )
    ++v6;
  *a1 = v6;
  return 1;
}

```

## disassembly

```asm
0x1400066d8  push    rbx
0x1400066da  push    rbp
0x1400066db  push    rsi
0x1400066dc  push    rdi
0x1400066dd  push    r14
0x1400066df  sub     rsp, 20h
0x1400066e3  mov     rbx, [rcx]
0x1400066e6  xor     ebp, ebp
0x1400066e8  mov     rdi, rdx
0x1400066eb  mov     r14, rcx
0x1400066ee  cmp     word ptr [rbx], 25h ; '%'
0x1400066f2  jz      short loc_140006705
0x1400066f4  movzx   ecx, word ptr [rbx]; ch
0x1400066f7  call    cs:__imp_IsCharAlphaNumericW
0x1400066fd  test    eax, eax
0x1400066ff  jz      loc_1400067CD
0x140006705  mov     ecx, 3Dh ; '='
0x14000670a  lea     r9d, [rcx-1Dh]
0x14000670e  jmp     short loc_14000671F
0x140006710  cmp     r9w, ax
0x140006714  jz      short loc_140006727
0x140006716  cmp     cx, ax
0x140006719  jz      short loc_140006727
0x14000671b  add     rbx, 2
0x14000671f  movzx   eax, word ptr [rbx]
0x140006722  test    ax, ax
0x140006725  jnz     short loc_140006710
0x140006727  cmp     cx, [rbx]
0x14000672a  jnz     loc_1400067CD
0x140006730  add     rbx, 2
0x140006734  mov     r8d, 22h ; '"'
0x14000673a  movzx   edx, word ptr [rbx]
0x14000673d  cmp     r8w, dx
0x140006741  jnz     short loc_14000674D
0x140006743  lea     r9d, [r8-21h]
0x140006747  add     rbx, 2
0x14000674b  jmp     short loc_14000678B
0x14000674d  movzx   r8d, r9w
0x140006751  mov     r9d, ebp
0x140006754  jmp     short loc_14000678E
0x140006756  cmp     r8w, dx
0x14000675a  jnz     short loc_140006780
0x14000675c  test    r9d, r9d
0x14000675f  jz      short loc_140006793
0x140006761  cmp     bp, dx
0x140006764  jnz     short loc_14000676D
0x140006766  mov     rdx, rbx
0x140006769  mov     eax, ebp
0x14000676b  jmp     short loc_140006774
0x14000676d  lea     rdx, [rbx+2]
0x140006771  movzx   eax, word ptr [rdx]
0x140006774  cmp     r8w, ax
0x140006778  jnz     short loc_140006793
0x14000677a  mov     rbx, rdx
0x14000677d  movzx   edx, word ptr [rdx]
0x140006780  cmp     bp, dx
0x140006783  lea     rax, [rbx+2]
0x140006787  cmovnz  rbx, rax
0x14000678b  movzx   edx, word ptr [rbx]
0x14000678e  test    dx, dx
0x140006791  jnz     short loc_140006756
0x140006793  cmp     [rbx], bp
0x140006796  jz      short loc_14000679E
0x140006798  cmp     r8w, [rbx]
0x14000679c  jnz     short loc_1400067CD
0x14000679e  test    r9d, r9d
0x1400067a1  jz      short loc_1400067AC
0x1400067a3  cmp     bp, [rbx]
0x1400067a6  jz      short loc_1400067AC
0x1400067a8  add     rbx, 2
0x1400067ac  mov     rsi, rbx
0x1400067af  sub     rsi, [r14]
0x1400067b2  sar     rsi, 1
0x1400067b5  inc     esi
0x1400067b7  cmp     esi, 7FFFFFFFh
0x1400067bd  jbe     short loc_1400067DA
0x1400067bf  xor     edx, edx; unsigned int
0x1400067c1  lea     rcx, aPropertyValueI; "Property value is too long.\r\n"
0x1400067c8  call    ?ReportErrorToDebugOutput@@YAXPEBGK@Z; ReportErrorToDebugOutput(ushort const *,ulong)
0x1400067cd  xor     eax, eax
0x1400067cf  add     rsp, 20h
0x1400067d3  pop     r14
0x1400067d5  pop     rdi
0x1400067d6  pop     rsi
0x1400067d7  pop     rbp
0x1400067d8  pop     rbx
0x1400067d9  retn
0x1400067da  mov     ecx, [rdi+8]
0x1400067dd  cmp     ecx, esi
0x1400067df  jge     short loc_140006825
0x1400067e1  cmp     ecx, [rdi+0Ch]
0x1400067e4  jle     short loc_1400067EE
0x1400067e6  mov     rcx, [rdi]; void *
0x1400067e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400067ee  mov     [rdi+8], esi
0x1400067f1  cmp     esi, [rdi+0Ch]
0x1400067f4  jle     short loc_140006819
0x1400067f6  movsxd  rcx, esi
0x1400067f9  mov     eax, 2
0x1400067fe  mul     rcx
0x140006801  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140006808  cmovb   rax, rcx
0x14000680c  xor     ecx, ecx; uFlags
0x14000680e  mov     rdx, rax; dwBytes
0x140006811  call    cs:__imp_GlobalAlloc
0x140006817  jmp     short loc_14000681D
0x140006819  lea     rax, [rdi+10h]
0x14000681d  mov     [rdi], rax
0x140006820  test    rax, rax
0x140006823  jz      short loc_1400067CD
0x140006825  movsxd  rdx, dword ptr [rdi+8]; unsigned __int64
0x140006829  mov     r8, [r14]; unsigned __int16 *
0x14000682c  mov     rcx, [rdi]; unsigned __int16 *
0x14000682f  movsxd  r9, esi; unsigned __int64
0x140006832  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140006837  cmp     bp, [rbx]
0x14000683a  jz      short loc_140006840
0x14000683c  add     rbx, 2
0x140006840  mov     [r14], rbx
0x140006843  mov     eax, 1
0x140006848  jmp     short loc_1400067CF
```
