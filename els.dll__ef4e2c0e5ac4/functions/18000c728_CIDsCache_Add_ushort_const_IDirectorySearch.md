# CIDsCache::Add(ushort const *,IDirectorySearch *)

- ea: `0x18000c728`
- end: `0x18000c7e2`
- name: `?Add@CIDsCache@@QEAAJPEBGPEAUIDirectorySearch@@@Z`
- size: `186`
- prototype: `int(CIDsCache *__hidden this, const unsigned __int16 *, struct IDirectorySearch *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e208`

## callees

- `0x180002928`
- `0x18000c728`
- `0x180017d40`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000c7a6`
- `msvcrt!wcsncpy_s` at `0x18000c7a6`
- `KERNEL32!EnterCriticalSection` at `0x18000c74f`
- `KERNEL32!EnterCriticalSection` at `0x18000c74f`
- `KERNEL32!LeaveCriticalSection` at `0x18000c7cc`
- `KERNEL32!LeaveCriticalSection` at `0x18000c7cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIDsCache::Add(CIDsCache *this, const unsigned __int16 *a2, struct IDirectorySearch *a3)
{
  wchar_t *v5; // rax
  struct CLruCacheItem *v6; // rbx
  unsigned int v7; // ebx

  EnterCriticalSection(&stru_18002F0B8);
  v5 = (wchar_t *)operator new(0x230u);
  v6 = (struct CLruCacheItem *)v5;
  if ( v5 )
  {
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 6) = 0;
    *(_QWORD *)v5 = &CIDsCacheItem::`vftable';
    *((_QWORD *)v5 + 69) = a3;
    wcsncpy_s(v5 + 16, 0x104u, a2, 0x103u);
    v7 = CLruCache::Add((CLruCache *)&g_DirSearchCache, v6);
  }
  else
  {
    v7 = -2147024882;
  }
  LeaveCriticalSection(&stru_18002F0B8);
  return v7;
}

```

## disassembly

```asm
0x18000c728  mov     [rsp+arg_8], rbx
0x18000c72d  mov     [rsp+arg_0], rcx
0x18000c732  push    rsi
0x18000c733  push    rdi
0x18000c734  push    r14
0x18000c736  sub     rsp, 20h
0x18000c73a  mov     rdi, r8
0x18000c73d  mov     rsi, rdx
0x18000c740  lea     r14, stru_18002F0B8
0x18000c747  mov     [rsp+38h+arg_0], r14
0x18000c74c  mov     rcx, r14; lpCriticalSection
0x18000c74f  call    cs:__imp_EnterCriticalSection
0x18000c755  nop
0x18000c756  mov     ecx, 230h; Size
0x18000c75b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c760  mov     rbx, rax
0x18000c763  mov     [rsp+38h+arg_18], rax
0x18000c768  test    rax, rax
0x18000c76b  jz      short loc_18000C7C4
0x18000c76d  mov     qword ptr [rax+8], 0
0x18000c775  mov     qword ptr [rax+10h], 0
0x18000c77d  mov     dword ptr [rax+18h], 0
0x18000c784  lea     rax, ??_7CIDsCacheItem@@6B@; const CIDsCacheItem::`vftable'
0x18000c78b  mov     [rbx], rax
0x18000c78e  mov     [rbx+228h], rdi
0x18000c795  lea     rcx, [rbx+20h]; Destination
0x18000c799  mov     r9d, 103h; MaxCount
0x18000c79f  mov     r8, rsi; Source
0x18000c7a2  lea     edx, [r9+1]; SizeInWords
0x18000c7a6  call    cs:__imp_wcsncpy_s
0x18000c7ac  test    rbx, rbx
0x18000c7af  jz      short loc_18000C7C4
0x18000c7b1  mov     rdx, rbx; struct CLruCacheItem *
0x18000c7b4  lea     rcx, ?g_DirSearchCache@@3VCIDsCache@@A; this
0x18000c7bb  call    ?Add@CLruCache@@UEAAJPEAVCLruCacheItem@@@Z; CLruCache::Add(CLruCacheItem *)
0x18000c7c0  mov     ebx, eax
0x18000c7c2  jmp     short loc_18000C7C9
0x18000c7c4  mov     ebx, 8007000Eh
0x18000c7c9  mov     rcx, r14; lpCriticalSection
0x18000c7cc  call    cs:__imp_LeaveCriticalSection
0x18000c7d2  mov     eax, ebx
0x18000c7d4  mov     rbx, [rsp+38h+arg_8]
0x18000c7d9  add     rsp, 20h
0x18000c7dd  pop     r14
0x18000c7df  pop     rdi
0x18000c7e0  pop     rsi
0x18000c7e1  retn
```
