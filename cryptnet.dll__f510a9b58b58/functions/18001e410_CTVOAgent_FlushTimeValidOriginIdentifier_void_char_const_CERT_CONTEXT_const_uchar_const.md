# CTVOAgent::FlushTimeValidOriginIdentifier(void *,char const *,_CERT_CONTEXT const *,uchar * const)

- ea: `0x18001e410`
- end: `0x18001e51c`
- name: `?FlushTimeValidOriginIdentifier@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@QEAE@Z`
- size: `268`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, CERT_CONTEXT *, const char *, const struct _CERT_CONTEXT *, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e1b8`

## callees

- `0x180012e1c`
- `0x180012f0c`
- `0x180017000`
- `0x18001e410`
- `0x18001e524`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e503`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e430`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e463`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e463`

## pseudocode

```c
__int64 __fastcall CTVOAgent::FlushTimeValidOriginIdentifier(
        LPCRITICAL_SECTION lpCriticalSection,
        CERT_CONTEXT *a2,
        const char *a3,
        const struct _CERT_CONTEXT *a4,
        unsigned __int8 *const a5)
{
  unsigned int v9; // edi
  struct _TVO_CACHE_ENTRY *CacheEntry; // rax
  CTVOCache *v11; // rcx
  struct _TVO_CACHE_ENTRY *v12; // rbx
  __int64 v13; // rax
  DWORD LastError; // esi
  __int64 v15; // rbp
  __int64 v16; // rdx
  __int64 v17; // rbp
  unsigned __int16 *v19; // [rsp+20h] [rbp-48h]

  v9 = 1;
  EnterCriticalSection(lpCriticalSection);
  CacheEntry = CTVOCache::FindCacheEntry((CTVOCache *)&lpCriticalSection[1], a5, a3, a2);
  v12 = CacheEntry;
  if ( CacheEntry )
    CTVOCache::RemoveCacheEntry(v11, CacheEntry, 1);
  LeaveCriticalSection(lpCriticalSection);
  if ( v12 )
  {
    v13 = *((_QWORD *)v12 + 7);
    LastError = 0;
    if ( v13 && *(_DWORD *)v13 )
    {
      v15 = 0;
      do
      {
        v19 = *(unsigned __int16 **)(*(_QWORD *)(v13 + 8) + 8 * v15);
        if ( !CTVOAgent::FlushTimeValidUrlCacheEntry((CTVOAgent *)v19, a2, a3, a4, v19) )
          LastError = GetLastError();
        v13 = *((_QWORD *)v12 + 7);
        v15 = (unsigned int)(v15 + 1);
      }
      while ( (unsigned int)v15 < *(_DWORD *)v13 );
    }
    v16 = *((_QWORD *)v12 + 9);
    if ( v16 && *(_DWORD *)v16 )
    {
      v17 = 0;
      do
      {
        if ( !CTVOAgent::FlushTimeValidUrlCacheEntry(
                *(CTVOAgent **)(*(_QWORD *)(v16 + 8) + 8 * v17),
                a2,
                a3,
                a4,
                *(const unsigned __int16 **)(*(_QWORD *)(v16 + 8) + 8 * v17)) )
          LastError = GetLastError();
        v16 = *((_QWORD *)v12 + 9);
        v17 = (unsigned int)(v17 + 1);
      }
      while ( (unsigned int)v17 < *(_DWORD *)v16 );
    }
    ObjectContextFreeTVOCacheEntry(v12);
    if ( LastError )
    {
      SetLastError(LastError);
      return 0;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x18001e410  push    rbx
0x18001e412  push    rbp
0x18001e413  push    rsi
0x18001e414  push    rdi
0x18001e415  push    r12
0x18001e417  push    r14
0x18001e419  push    r15
0x18001e41b  sub     rsp, 30h
0x18001e41f  mov     r12, r9
0x18001e422  mov     r14, r8
0x18001e425  mov     r15, rdx
0x18001e428  mov     rsi, rcx
0x18001e42b  mov     edi, 1
0x18001e430  call    cs:__imp_EnterCriticalSection
0x18001e436  mov     rdx, [rsp+68h+arg_20]; unsigned __int8 *
0x18001e43e  lea     rcx, [rsi+28h]; this
0x18001e442  mov     r9, r15; void *
0x18001e445  mov     r8, r14; char *
0x18001e448  call    ?FindCacheEntry@CTVOCache@@QEAAPEAU_TVO_CACHE_ENTRY@@QEAEPEBDPEAX@Z; CTVOCache::FindCacheEntry(uchar * const,char const *,void *)
0x18001e44d  mov     rbx, rax
0x18001e450  test    rax, rax
0x18001e453  jz      short loc_18001E460
0x18001e455  mov     r8d, edi; int
0x18001e458  mov     rdx, rax; struct _TVO_CACHE_ENTRY *
0x18001e45b  call    ?RemoveCacheEntry@CTVOCache@@QEAAXPEAU_TVO_CACHE_ENTRY@@H@Z; CTVOCache::RemoveCacheEntry(_TVO_CACHE_ENTRY *,int)
0x18001e460  mov     rcx, rsi; lpCriticalSection
0x18001e463  call    cs:__imp_LeaveCriticalSection
0x18001e469  test    rbx, rbx
0x18001e46c  jz      loc_18001E50B
0x18001e472  mov     rax, [rbx+38h]
0x18001e476  xor     esi, esi
0x18001e478  test    rax, rax
0x18001e47b  jz      short loc_18001E4B4
0x18001e47d  cmp     [rax], esi
0x18001e47f  jbe     short loc_18001E4B4
0x18001e481  xor     ebp, ebp
0x18001e483  mov     rax, [rax+8]
0x18001e487  mov     r9, r12; struct _CERT_CONTEXT *
0x18001e48a  mov     r8, r14; char *
0x18001e48d  mov     rdx, r15; void *
0x18001e490  mov     rcx, [rax+rbp*8]; this
0x18001e494  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18001e499  call    ?FlushTimeValidUrlCacheEntry@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@PEBG@Z; CTVOAgent::FlushTimeValidUrlCacheEntry(void *,char const *,_CERT_CONTEXT const *,ushort const *)
0x18001e49e  test    eax, eax
0x18001e4a0  jnz     short loc_18001E4AA
0x18001e4a2  call    cs:__imp_GetLastError
0x18001e4a8  mov     esi, eax
0x18001e4aa  mov     rax, [rbx+38h]
0x18001e4ae  add     ebp, edi
0x18001e4b0  cmp     ebp, [rax]
0x18001e4b2  jb      short loc_18001E483
0x18001e4b4  mov     rdx, [rbx+48h]
0x18001e4b8  test    rdx, rdx
0x18001e4bb  jz      short loc_18001E4F5
0x18001e4bd  cmp     dword ptr [rdx], 0
0x18001e4c0  jbe     short loc_18001E4F5
0x18001e4c2  xor     ebp, ebp
0x18001e4c4  mov     rax, [rdx+8]
0x18001e4c8  mov     r9, r12; struct _CERT_CONTEXT *
0x18001e4cb  mov     r8, r14; char *
0x18001e4ce  mov     rdx, r15; void *
0x18001e4d1  mov     rcx, [rax+rbp*8]; this
0x18001e4d5  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18001e4da  call    ?FlushTimeValidUrlCacheEntry@CTVOAgent@@QEAAHPEAXPEBDPEBU_CERT_CONTEXT@@PEBG@Z; CTVOAgent::FlushTimeValidUrlCacheEntry(void *,char const *,_CERT_CONTEXT const *,ushort const *)
0x18001e4df  test    eax, eax
0x18001e4e1  jnz     short loc_18001E4EB
0x18001e4e3  call    cs:__imp_GetLastError
0x18001e4e9  mov     esi, eax
0x18001e4eb  mov     rdx, [rbx+48h]
0x18001e4ef  add     ebp, edi
0x18001e4f1  cmp     ebp, [rdx]
0x18001e4f3  jb      short loc_18001E4C4
0x18001e4f5  mov     rcx, rbx; hMem
0x18001e4f8  call    ?ObjectContextFreeTVOCacheEntry@@YAXPEAU_TVO_CACHE_ENTRY@@@Z; ObjectContextFreeTVOCacheEntry(_TVO_CACHE_ENTRY *)
0x18001e4fd  test    esi, esi
0x18001e4ff  jz      short loc_18001E50B
0x18001e501  mov     ecx, esi; dwErrCode
0x18001e503  call    cs:__imp_SetLastError
0x18001e509  xor     edi, edi
0x18001e50b  mov     eax, edi
0x18001e50d  add     rsp, 30h
0x18001e511  pop     r15
0x18001e513  pop     r14
0x18001e515  pop     r12
0x18001e517  pop     rdi
0x18001e518  pop     rsi
0x18001e519  pop     rbp
0x18001e51a  pop     rbx
0x18001e51b  retn
```
