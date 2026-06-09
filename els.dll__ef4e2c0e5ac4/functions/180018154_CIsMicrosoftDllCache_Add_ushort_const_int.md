# CIsMicrosoftDllCache::_Add(ushort const *,int)

- ea: `0x180018154`
- end: `0x1800181e8`
- name: `?_Add@CIsMicrosoftDllCache@@AEAAJPEBGH@Z`
- size: `148`
- prototype: `int(CIsMicrosoftDllCache *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017ee4`

## callees

- `0x180002928`
- `0x180017d40`
- `0x180018154`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800181b1`
- `msvcrt!wcsncpy_s` at `0x1800181b1`

## pseudocode

```c
__int64 __fastcall CIsMicrosoftDllCache::_Add(CIsMicrosoftDllCache *this, const unsigned __int16 *a2, int a3)
{
  wchar_t *v5; // rax
  struct CLruCacheItem *v6; // rbx

  v5 = (wchar_t *)operator new(0x230u);
  v6 = (struct CLruCacheItem *)v5;
  if ( !v5 )
    return 2147942414LL;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_DWORD *)v5 + 6) = 0;
  *(_QWORD *)v5 = &CIsMicrosoftDllCacheItem::`vftable';
  wcsncpy_s(v5 + 16, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
  *((_DWORD *)v6 + 138) = a3;
  return CLruCache::Add((CLruCache *)&g_IsMicrosoftDllCache, v6);
}

```

## disassembly

```asm
0x180018154  mov     [rsp+arg_8], rbx
0x180018159  mov     [rsp+arg_10], rsi
0x18001815e  push    rdi
0x18001815f  sub     rsp, 20h
0x180018163  mov     ecx, 230h; Size
0x180018168  mov     edi, r8d
0x18001816b  mov     rsi, rdx
0x18001816e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018173  mov     [rsp+28h+arg_0], rax
0x180018178  mov     rbx, rax
0x18001817b  test    rax, rax
0x18001817e  jz      short loc_1800181D3
0x180018180  mov     qword ptr [rax+8], 0
0x180018188  lea     rcx, [rbx+20h]; Destination
0x18001818c  mov     qword ptr [rax+10h], 0
0x180018194  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180018198  mov     dword ptr [rax+18h], 0
0x18001819f  mov     r8, rsi; Source
0x1800181a2  lea     rax, ??_7CIsMicrosoftDllCacheItem@@6B@; const CIsMicrosoftDllCacheItem::`vftable'
0x1800181a9  mov     edx, 104h; SizeInWords
0x1800181ae  mov     [rbx], rax
0x1800181b1  call    cs:__imp_wcsncpy_s
0x1800181b7  mov     [rbx+228h], edi
0x1800181bd  test    rbx, rbx
0x1800181c0  jz      short loc_1800181D3
0x1800181c2  mov     rdx, rbx; struct CLruCacheItem *
0x1800181c5  lea     rcx, ?g_IsMicrosoftDllCache@@3VCIsMicrosoftDllCache@@A; this
0x1800181cc  call    ?Add@CLruCache@@UEAAJPEAVCLruCacheItem@@@Z; CLruCache::Add(CLruCacheItem *)
0x1800181d1  jmp     short loc_1800181D8
0x1800181d3  mov     eax, 8007000Eh
0x1800181d8  mov     rbx, [rsp+28h+arg_8]
0x1800181dd  mov     rsi, [rsp+28h+arg_10]
0x1800181e2  add     rsp, 20h
0x1800181e6  pop     rdi
0x1800181e7  retn
```
