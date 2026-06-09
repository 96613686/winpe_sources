# CDllCache::_Add(ushort const *,HINSTANCE__ *)

- ea: `0x18000c4f0`
- end: `0x18000c58c`
- name: `?_Add@CDllCache@@AEAAJPEBGPEAUHINSTANCE__@@@Z`
- size: `156`
- prototype: `int __fastcall(CDllCache *this, const unsigned __int16 *, HINSTANCE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000c368`

## callees

- `0x180003398`
- `0x18000c4f0`
- `0x180017d40`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000c554`
- `msvcrt!wcsncpy_s` at `0x18000c554`

## pseudocode

```c
int __fastcall CDllCache::_Add(CDllCache *this, const unsigned __int16 *a2, HINSTANCE a3)
{
  wchar_t *v5; // rax
  struct CLruCacheItem *v6; // rbx

  v5 = (wchar_t *)operator new(0x230u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = (struct CLruCacheItem *)v5;
  if ( !v5 )
    return -2147024882;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_DWORD *)v5 + 6) = 0;
  *(_QWORD *)v5 = &CDllCacheItem::`vftable';
  wcsncpy_s(v5 + 16, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
  *((_QWORD *)v6 + 69) = a3;
  return CLruCache::Add((CLruCache *)&g_DllCache, v6);
}

```

## disassembly

```asm
0x18000c4f0  mov     [rsp+arg_8], rbx
0x18000c4f5  mov     [rsp+arg_10], rsi
0x18000c4fa  push    rdi
0x18000c4fb  sub     rsp, 20h
0x18000c4ff  mov     rsi, rdx
0x18000c502  mov     ecx, 230h; unsigned __int64
0x18000c507  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c50e  mov     rdi, r8
0x18000c511  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c516  mov     [rsp+28h+arg_0], rax
0x18000c51b  mov     rbx, rax
0x18000c51e  test    rax, rax
0x18000c521  jz      short loc_18000C577
0x18000c523  mov     qword ptr [rax+8], 0
0x18000c52b  lea     rcx, [rbx+20h]; Destination
0x18000c52f  mov     qword ptr [rax+10h], 0
0x18000c537  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000c53b  mov     dword ptr [rax+18h], 0
0x18000c542  mov     r8, rsi; Source
0x18000c545  lea     rax, ??_7CDllCacheItem@@6B@; const CDllCacheItem::`vftable'
0x18000c54c  mov     edx, 104h; SizeInWords
0x18000c551  mov     [rbx], rax
0x18000c554  call    cs:__imp_wcsncpy_s
0x18000c55a  mov     [rbx+228h], rdi
0x18000c561  test    rbx, rbx
0x18000c564  jz      short loc_18000C577
0x18000c566  mov     rdx, rbx; struct CLruCacheItem *
0x18000c569  lea     rcx, ?g_DllCache@@3VCDllCache@@A; this
0x18000c570  call    ?Add@CLruCache@@UEAAJPEAVCLruCacheItem@@@Z; CLruCache::Add(CLruCacheItem *)
0x18000c575  jmp     short loc_18000C57C
0x18000c577  mov     eax, 8007000Eh
0x18000c57c  mov     rbx, [rsp+28h+arg_8]
0x18000c581  mov     rsi, [rsp+28h+arg_10]
0x18000c586  add     rsp, 20h
0x18000c58a  pop     rdi
0x18000c58b  retn
```
