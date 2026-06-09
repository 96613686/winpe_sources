# FILE_CACHE::ReleaseFromMemoryCache(void *,unsigned __int64)

- ea: `0x1800023f0`
- end: `0x18000248f`
- name: `?ReleaseFromMemoryCache@FILE_CACHE@@QEAAJPEAX_K@Z`
- size: `159`
- prototype: `int(FILE_CACHE *__hidden this, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002300`

## callees

- `0x1800023f0`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002432`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002432`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002419`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002419`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000240f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000240f`

## pseudocode

```c
__int64 __fastcall FILE_CACHE::ReleaseFromMemoryCache(FILE_CACHE *this, void *a2, unsigned __int64 a3)
{
  char *v3; // rsi
  __int64 i; // rdi
  void (__fastcall *v6)(__int64, __int64, __int64); // rax
  __int64 v7; // rax

  v3 = (char *)g_pFileCache;
  HeapFree(*((HANDLE *)g_pFileCache + 16), 0, a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 72));
  *((_QWORD *)v3 + 15) -= a3;
  --*((_DWORD *)v3 + 36);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 72));
  for ( i = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo); a3; a3 -= v7 )
  {
    v6 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)i + 8LL);
    if ( a3 > 0xFFFFFFFF )
    {
      v6(i, 25, 0xFFFFFFFFLL);
      v7 = 0xFFFFFFFFLL;
    }
    else
    {
      v6(i, 25, (unsigned int)a3);
      v7 = a3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800023f0  push    rbx
0x1800023f2  push    rbp
0x1800023f3  push    rsi
0x1800023f4  push    rdi
0x1800023f5  sub     rsp, 28h
0x1800023f9  mov     rsi, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180002400  mov     rbx, r8
0x180002403  mov     r8, rdx; lpMem
0x180002406  xor     edx, edx; dwFlags
0x180002408  mov     rcx, [rsi+80h]; hHeap
0x18000240f  call    cs:__imp_HeapFree
0x180002415  lea     rcx, [rsi+48h]; lpCriticalSection
0x180002419  call    cs:__imp_EnterCriticalSection
0x18000241f  sub     [rsi+78h], rbx
0x180002423  lea     rcx, [rsi+48h]; lpCriticalSection
0x180002427  mov     ebp, 0FFFFFFFFh
0x18000242c  add     [rsi+90h], ebp
0x180002432  call    cs:__imp_LeaveCriticalSection
0x180002438  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000243f  mov     rax, [rcx]
0x180002442  mov     rax, [rax+60h]
0x180002446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244b  mov     rdi, rax
0x18000244e  test    rbx, rbx
0x180002451  jz      short loc_180002477
0x180002453  mov     rcx, [rdi]
0x180002456  mov     edx, 19h
0x18000245b  mov     rax, [rcx+8]
0x18000245f  mov     rcx, rdi
0x180002462  cmp     rbx, rbp
0x180002465  ja      short loc_180002482
0x180002467  mov     r8d, ebx
0x18000246a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000246f  mov     rax, rbx
0x180002472  sub     rbx, rax
0x180002475  jnz     short loc_180002453
0x180002477  xor     eax, eax
0x180002479  add     rsp, 28h
0x18000247d  pop     rdi
0x18000247e  pop     rsi
0x18000247f  pop     rbp
0x180002480  pop     rbx
0x180002481  retn
0x180002482  mov     r8d, ebp
0x180002485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000248a  mov     rax, rbp
0x18000248d  jmp     short loc_180002472
```
