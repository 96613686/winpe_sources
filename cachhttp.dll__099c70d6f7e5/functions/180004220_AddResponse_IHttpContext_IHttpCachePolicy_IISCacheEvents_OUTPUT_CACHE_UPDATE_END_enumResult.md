# AddResponse(IHttpContext *,IHttpCachePolicy *,IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult *)

- ea: `0x180004220`
- end: `0x18000473c`
- name: `?AddResponse@@YAJPEAVIHttpContext@@PEAVIHttpCachePolicy@@PEAW4enumResult@OUTPUT_CACHE_UPDATE_END@IISCacheEvents@@@Z`
- size: `1308`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IHttpCachePolicy *, enum IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180001280`

## callees

- `0x180004220`
- `0x180004744`
- `0x180004778`
- `0x180004bfc`
- `0x180004d18`
- `0x180005a0c`
- `0x18000657c`
- `0x1800065c8`
- `0x180006628`
- `0x180007218`
- `0x18000770c`
- `0x1800084bc`
- `0x18000852c`
- `0x1800089f0`
- `0x180008bbe`
- `0x180009010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180004356`
- `msvcrt!_stricmp` at `0x180004385`
- `msvcrt!_stricmp` at `0x180004428`
- `msvcrt!_stricmp` at `0x180004457`
- `msvcrt!_stricmp` at `0x180004356`
- `msvcrt!_stricmp` at `0x180004385`
- `msvcrt!_stricmp` at `0x180004428`
- `msvcrt!_stricmp` at `0x180004457`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800045d9`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x1800045d9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000431c`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000431c`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000434a`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180004379`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000441c`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000444b`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000434a`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180004379`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000441c`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x18000444b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004396`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180004396`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800043a7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800043a7`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043cf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043f6`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043cf`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x1800043f6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000446b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000446b`

## pseudocode

```c
__int64 __fastcall AddResponse(
        struct IHttpContext *a1,
        struct IHttpCachePolicy *a2,
        enum IISCacheEvents::OUTPUT_CACHE_UPDATE_END::enumResult *a3)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // esi
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rcx
  int v13; // r9d
  int v14; // edi
  __int64 result; // rax
  VARY_BY_CACHE_ENTRY *v16; // r14
  CReaderWriterLock3 *v17; // rdi
  int v18; // ebx
  const char *v19; // rbx
  const char *Str; // rax
  const char *v21; // rbx
  const char *v22; // rax
  int v23; // eax
  __int64 (__fastcall *v24)(struct IHttpCachePolicy *); // rax
  const char *v25; // rax
  const char *v26; // rax
  const char *v27; // rbx
  const char *v28; // rax
  const char *v29; // rbx
  const char *v30; // rax
  int v31; // eax
  OUTPUT_ENTRY *v32; // rax
  OUTPUT_ENTRY *v33; // rax
  OUTPUT_ENTRY *v34; // rbx
  _QWORD *v35; // rsi
  __int64 v36; // rcx
  OUTPUT_ENTRY *v37; // rbp
  __int64 v38; // rax
  __int64 v39; // rax
  const char *v40; // rax
  bool v41; // zf
  PVOID v42; // rcx
  void (__fastcall ***v43)(_QWORD, __int64, __int64); // rbx
  OUTPUT_ENTRY *v44; // [rsp+20h] [rbp-48h] BYREF
  unsigned int v45; // [rsp+70h] [rbp+8h]
  VARY_BY_CACHE_ENTRY *v46; // [rsp+88h] [rbp+20h] BYREF

  v46 = 0;
  v4 = 0;
  v44 = 0;
  v45 = 0;
  v7 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  v9 = 1;
  if ( *(_WORD *)(v8 + 536) )
  {
    v10 = *(_QWORD *)(v8 + 544);
    v11 = 0;
    do
    {
      v12 = 32LL * v11;
      v13 = *(_DWORD *)(v12 + v10);
      if ( v13 )
      {
        if ( v13 == 1 )
          v4 += *(_QWORD *)(v12 + v10 + 16);
      }
      else
      {
        v4 += *(unsigned int *)(v12 + v10 + 16);
      }
      ++v11;
    }
    while ( v11 < *(unsigned __int16 *)(v8 + 536) );
    v45 = v4;
  }
  if ( !*((_DWORD *)g_pOutputCache + 21) || v4 <= *((unsigned int *)g_pOutputCache + 21) )
  {
    if ( v4 + *((_QWORD *)g_pOutputCache + 13) > *((_QWORD *)g_pOutputCache + 11) )
    {
      *(_DWORD *)a3 = 9;
      return (unsigned int)-2147024888;
    }
    result = VARY_BY_CACHE_ENTRY::RetrieveEntry(a1, 1, &v46);
    if ( (int)result < 0 )
      return result;
    v16 = v46;
    v17 = (VARY_BY_CACHE_ENTRY *)((char *)v46 + 1320);
    CReaderWriterLock3::ReadLock((VARY_BY_CACHE_ENTRY *)((char *)v46 + 1320));
    if ( *((_DWORD *)v16 + 172) )
    {
      v19 = (const char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 32LL))(a2);
      Str = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v16 + 696));
      if ( _stricmp(Str, v19)
        || (v21 = (const char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 48LL))(a2),
            v22 = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v16 + 1008)),
            v23 = _stricmp(v22, v21),
            v18 = 1,
            v23) )
      {
        v18 = 0;
      }
    }
    else
    {
      v18 = 1;
      v9 = 0;
    }
    CReaderWriterLock3::ReadUnlock(v17);
    if ( v9 )
    {
LABEL_30:
      if ( !v18 )
      {
        *(_DWORD *)a3 = 10;
        v14 = -2147024809;
LABEL_61:
        VARY_BY_CACHE_ENTRY::DereferenceCacheData(v16);
        return (unsigned int)v14;
      }
      if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 208LL))(a1)
        && *(_DWORD *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 16LL))(a2) == 1 )
      {
        v14 = VARY_BY_CACHE_ENTRY::SetFileMonitor(v16, a1);
        if ( v14 < 0 )
          goto LABEL_61;
      }
      else
      {
        VARY_BY_CACHE_ENTRY::CalculateFileAttributes(v16, a1);
      }
      v32 = (OUTPUT_ENTRY *)operator new(0x3B8u);
      if ( !v32 || (v33 = OUTPUT_ENTRY::OUTPUT_ENTRY(v32), (v34 = v33) == 0) )
      {
        v14 = -2147024888;
        goto LABEL_61;
      }
      v35 = 0;
      v14 = OUTPUT_ENTRY::Initialize(v33, a1, a2);
      if ( v14 < 0 )
      {
        v37 = v34;
      }
      else
      {
        CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(v36, (char *)v34 + 8, &v44);
        v37 = v44;
        if ( v44 )
        {
          OUTPUT_ENTRY::DereferenceOutputEntry(v34);
        }
        else
        {
          v37 = v34;
          if ( (unsigned int)CLKRHashTable::InsertRecord(g_pOutputCache, v34, 0) )
          {
            *(_DWORD *)a3 = 11;
            v14 = -2147467259;
            goto LABEL_58;
          }
        }
        v38 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 32LL))(a1);
        v46 = (VARY_BY_CACHE_ENTRY *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v38 + 64LL))(v38, 13);
        if ( v46 )
        {
          v41 = *((_QWORD *)v37 + 104) == 0;
        }
        else
        {
          v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 24LL))(a1);
          v40 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 16LL))(v39, 22);
          if ( v40 && !*((_QWORD *)v37 + 104) )
            OUTPUT_ENTRY::UpdateEncodingsRejectedIfNeeded(v37, v40);
          v41 = *((_QWORD *)v37 + 103) == 0;
        }
        if ( !v41 )
          goto LABEL_48;
        v35 = operator new(0x258u);
        if ( v35 )
        {
          v35[1] = 1;
          *v35 = &RESPONSE_ENTRY::`vftable';
          *((_DWORD *)v35 + 147) = 0;
          *((_DWORD *)v35 + 148) = -1;
          memset_0(v35 + 2, 0, 0x238u);
          v14 = RESPONSE_ENTRY::Initialize((RESPONSE_ENTRY *)v35, a1, a2, v45);
          if ( v14 >= 0 )
          {
            v14 = OUTPUT_ENTRY::SetResponseEntry(v37, (struct RESPONSE_ENTRY *)v35, (const char *)v46);
            if ( v14 < 0 )
            {
LABEL_48:
              *(_DWORD *)a3 = 11;
              goto LABEL_58;
            }
            v42 = g_pOutputCache;
            v35 = 0;
            *(_DWORD *)a3 = 0;
            _InterlockedAdd((volatile signed __int32 *)v42 + 29, 1u);
            _InterlockedAdd64((volatile signed __int64 *)v42 + 13, v45);
            v43 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
            (**v43)(v43, 18, 1);
            (**v43)(v43, 19, v45);
            g_fAnyResponseCached = 1;
          }
        }
        else
        {
          v14 = -2147024888;
          v35 = 0;
        }
      }
LABEL_58:
      OUTPUT_ENTRY::DereferenceOutputEntry(v37);
      if ( v35 )
        RESPONSE_ENTRY::DereferenceResponseEntry((RESPONSE_ENTRY *)v35);
      goto LABEL_61;
    }
    CReaderWriterLock3::WriteLock(v17);
    v24 = *(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 32LL);
    if ( *((_DWORD *)v16 + 172) )
    {
      v27 = (const char *)v24(a2);
      v28 = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v16 + 696));
      if ( !_stricmp(v28, v27) )
      {
        v29 = (const char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 48LL))(a2);
        v30 = STRA::QueryStr((VARY_BY_CACHE_ENTRY *)((char *)v16 + 1008));
        v31 = _stricmp(v30, v29);
        v18 = 1;
        if ( !v31 )
          goto LABEL_29;
      }
    }
    else
    {
      v25 = (const char *)v24(a2);
      if ( (int)STRA::Copy((VARY_BY_CACHE_ENTRY *)((char *)v16 + 696), v25) >= 0 )
      {
        v26 = (const char *)(*(__int64 (__fastcall **)(struct IHttpCachePolicy *))(*(_QWORD *)a2 + 48LL))(a2);
        if ( (int)STRA::Copy((VARY_BY_CACHE_ENTRY *)((char *)v16 + 1008), v26) >= 0 )
        {
          *((_DWORD *)v16 + 172) = 1;
LABEL_29:
          CReaderWriterLock3::WriteUnlock(v17);
          goto LABEL_30;
        }
      }
    }
    v18 = 0;
    goto LABEL_29;
  }
  *(_DWORD *)a3 = 8;
  return (unsigned int)-2147024888;
}

```

## disassembly

```asm
0x180004220  mov     rax, rsp
0x180004223  mov     [rax+10h], rbx
0x180004227  push    rbp
0x180004228  push    rsi
0x180004229  push    rdi
0x18000422a  push    r12
0x18000422c  push    r13
0x18000422e  push    r14
0x180004230  push    r15
0x180004232  sub     rsp, 30h
0x180004236  xor     ebp, ebp
0x180004238  mov     r13, r8
0x18000423b  mov     [rax+20h], rbp
0x18000423f  mov     ebx, ebp
0x180004241  mov     [rax-48h], rbp
0x180004245  mov     r15, rdx
0x180004248  mov     rax, [rcx]
0x18000424b  mov     r12, rcx
0x18000424e  mov     qword ptr [rsp+68h+arg_0], rbx
0x180004253  mov     rax, [rax+20h]
0x180004257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000425c  mov     rcx, rax
0x18000425f  mov     r8, [rax]
0x180004262  mov     rax, [r8+8]
0x180004266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426b  lea     esi, [rbp+1]
0x18000426e  movzx   r10d, word ptr [rax+218h]
0x180004276  test    r10d, r10d
0x180004279  jz      short loc_1800042B3
0x18000427b  mov     r8, [rax+220h]
0x180004282  mov     edx, ebp
0x180004284  mov     ecx, edx
0x180004286  shl     rcx, 5
0x18000428a  mov     r9d, [rcx+r8]
0x18000428e  test    r9d, r9d
0x180004291  jz      short loc_18000429F
0x180004293  cmp     r9d, esi
0x180004296  jnz     short loc_1800042A7
0x180004298  add     rbx, [rcx+r8+10h]
0x18000429d  jmp     short loc_1800042A7
0x18000429f  mov     eax, [rcx+r8+10h]
0x1800042a4  add     rbx, rax
0x1800042a7  add     edx, esi
0x1800042a9  cmp     edx, r10d
0x1800042ac  jb      short loc_180004284
0x1800042ae  mov     qword ptr [rsp+68h+arg_0], rbx
0x1800042b3  mov     rdx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x1800042ba  cmp     [rdx+54h], ebp
0x1800042bd  jz      short loc_1800042D9
0x1800042bf  mov     eax, [rdx+54h]
0x1800042c2  cmp     rbx, rax
0x1800042c5  jbe     short loc_1800042D9
0x1800042c7  mov     dword ptr [r13+0], 8
0x1800042cf  mov     edi, 80070008h
0x1800042d4  jmp     loc_180004725
0x1800042d9  mov     rcx, [rdx+68h]
0x1800042dd  add     rcx, rbx
0x1800042e0  cmp     rcx, [rdx+58h]
0x1800042e4  jbe     short loc_1800042F0
0x1800042e6  mov     dword ptr [r13+0], 9
0x1800042ee  jmp     short loc_1800042CF
0x1800042f0  lea     r8, [rsp+68h+arg_18]; struct VARY_BY_CACHE_ENTRY **
0x1800042f8  mov     edx, esi; int
0x1800042fa  mov     rcx, r12; struct IHttpContext *
0x1800042fd  call    ?RetrieveEntry@VARY_BY_CACHE_ENTRY@@SAJPEAVIHttpContext@@HPEAPEAV1@@Z; VARY_BY_CACHE_ENTRY::RetrieveEntry(IHttpContext *,int,VARY_BY_CACHE_ENTRY * *)
0x180004302  test    eax, eax
0x180004304  js      loc_180004727
0x18000430a  mov     r14, [rsp+68h+arg_18]
0x180004312  lea     rdi, [r14+528h]
0x180004319  mov     rcx, rdi
0x18000431c  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180004322  cmp     [r14+2B0h], ebp
0x180004329  jnz     short loc_180004331
0x18000432b  mov     ebx, esi
0x18000432d  mov     esi, ebp
0x18000432f  jmp     short loc_180004393
0x180004331  mov     rax, [r15]
0x180004334  mov     rcx, r15
0x180004337  mov     rax, [rax+20h]
0x18000433b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004340  lea     rcx, [r14+2B8h]
0x180004347  mov     rbx, rax
0x18000434a  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180004350  mov     rcx, rax; String1
0x180004353  mov     rdx, rbx; String2
0x180004356  call    cs:__imp__stricmp
0x18000435c  test    eax, eax
0x18000435e  jnz     short loc_180004391
0x180004360  mov     rax, [r15]
0x180004363  mov     rcx, r15
0x180004366  mov     rax, [rax+30h]
0x18000436a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436f  lea     rcx, [r14+3F0h]
0x180004376  mov     rbx, rax
0x180004379  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x18000437f  mov     rcx, rax; String1
0x180004382  mov     rdx, rbx; String2
0x180004385  call    cs:__imp__stricmp
0x18000438b  mov     ebx, esi
0x18000438d  test    eax, eax
0x18000438f  jz      short loc_180004393
0x180004391  mov     ebx, ebp
0x180004393  mov     rcx, rdi
0x180004396  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000439c  test    esi, esi
0x18000439e  jnz     loc_180004471
0x1800043a4  mov     rcx, rdi
0x1800043a7  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800043ad  mov     rcx, r15
0x1800043b0  mov     rax, [r15]
0x1800043b3  mov     rax, [rax+20h]
0x1800043b7  cmp     [r14+2B0h], ebp
0x1800043be  jnz     short loc_18000440D
0x1800043c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c5  lea     rcx, [r14+2B8h]
0x1800043cc  mov     rdx, rax
0x1800043cf  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800043d5  test    eax, eax
0x1800043d7  js      loc_180004466
0x1800043dd  mov     rax, [r15]
0x1800043e0  mov     rcx, r15
0x1800043e3  mov     rax, [rax+30h]
0x1800043e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ec  lea     rcx, [r14+3F0h]
0x1800043f3  mov     rdx, rax
0x1800043f6  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x1800043fc  test    eax, eax
0x1800043fe  js      short loc_180004466
0x180004400  mov     dword ptr [r14+2B0h], 1
0x18000440b  jmp     short loc_180004468
0x18000440d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004412  lea     rcx, [r14+2B8h]
0x180004419  mov     rbx, rax
0x18000441c  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180004422  mov     rcx, rax; String1
0x180004425  mov     rdx, rbx; String2
0x180004428  call    cs:__imp__stricmp
0x18000442e  test    eax, eax
0x180004430  jnz     short loc_180004466
0x180004432  mov     rax, [r15]
0x180004435  mov     rcx, r15
0x180004438  mov     rax, [rax+30h]
0x18000443c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004441  lea     rcx, [r14+3F0h]
0x180004448  mov     rbx, rax
0x18000444b  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180004451  mov     rcx, rax; String1
0x180004454  mov     rdx, rbx; String2
0x180004457  call    cs:__imp__stricmp
0x18000445d  mov     ebx, 1
0x180004462  test    eax, eax
0x180004464  jz      short loc_180004468
0x180004466  mov     ebx, ebp
0x180004468  mov     rcx, rdi
0x18000446b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180004471  test    ebx, ebx
0x180004473  jnz     short loc_180004487
0x180004475  mov     dword ptr [r13+0], 0Ah
0x18000447d  mov     edi, 80070057h
0x180004482  jmp     loc_18000471D
0x180004487  mov     rax, [r12]
0x18000448b  mov     rcx, r12
0x18000448e  mov     rax, [rax+0D0h]
0x180004495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000449a  test    rax, rax
0x18000449d  jz      short loc_1800044C9
0x18000449f  mov     rax, [r15]
0x1800044a2  mov     rcx, r15
0x1800044a5  mov     rax, [rax+10h]
0x1800044a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ae  cmp     dword ptr [rax], 1
0x1800044b1  jnz     short loc_1800044C9
0x1800044b3  mov     rdx, r12; struct IHttpContext *
0x1800044b6  mov     rcx, r14; this
0x1800044b9  call    ?SetFileMonitor@VARY_BY_CACHE_ENTRY@@QEAAJPEAVIHttpContext@@@Z; VARY_BY_CACHE_ENTRY::SetFileMonitor(IHttpContext *)
0x1800044be  mov     edi, eax
0x1800044c0  test    eax, eax
0x1800044c2  jns     short loc_1800044D4
0x1800044c4  jmp     loc_18000471D
0x1800044c9  mov     rdx, r12; struct IHttpContext *
0x1800044cc  mov     rcx, r14; this
0x1800044cf  call    ?CalculateFileAttributes@VARY_BY_CACHE_ENTRY@@QEAAXPEAVIHttpContext@@@Z; VARY_BY_CACHE_ENTRY::CalculateFileAttributes(IHttpContext *)
0x1800044d4  mov     ecx, 3B8h; Size
0x1800044d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044de  test    rax, rax
0x1800044e1  jz      loc_180004718
0x1800044e7  mov     rcx, rax; this
0x1800044ea  call    ??0OUTPUT_ENTRY@@QEAA@XZ; OUTPUT_ENTRY::OUTPUT_ENTRY(void)
0x1800044ef  mov     rbx, rax
0x1800044f2  test    rax, rax
0x1800044f5  jz      loc_180004718
0x1800044fb  mov     r8, r15; struct IHttpCachePolicy *
0x1800044fe  mov     rdx, r12; struct IHttpContext *
0x180004501  mov     rcx, rax; this
0x180004504  mov     rsi, rbp
0x180004507  call    ?Initialize@OUTPUT_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIHttpCachePolicy@@@Z; OUTPUT_ENTRY::Initialize(IHttpContext *,IHttpCachePolicy *)
0x18000450c  mov     edi, eax
0x18000450e  test    eax, eax
0x180004510  js      loc_1800046FE
0x180004516  lea     rdx, [rbx+8]
0x18000451a  lea     r8, [rsp+68h+var_48]
0x18000451f  call    ?FindKey@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEAVOUTPUT_KEY@@PEAPEAVOUTPUT_ENTRY@@@Z; CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::FindKey(OUTPUT_KEY * const,OUTPUT_ENTRY * *)
0x180004524  mov     rbp, [rsp+68h+var_48]
0x180004529  test    rbp, rbp
0x18000452c  jz      loc_1800045CC
0x180004532  mov     rcx, rbx; this
0x180004535  call    ?DereferenceOutputEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::DereferenceOutputEntry(void)
0x18000453a  mov     rax, [r12]
0x18000453e  mov     rcx, r12
0x180004541  mov     rax, [rax+20h]
0x180004545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000454a  mov     r9, rax
0x18000454d  xor     r8d, r8d
0x180004550  mov     rcx, [rax]
0x180004553  lea     edx, [r8+0Dh]
0x180004557  mov     rax, [rcx+40h]
0x18000455b  mov     rcx, r9
0x18000455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004563  mov     [rsp+68h+arg_18], rax
0x18000456b  test    rax, rax
0x18000456e  jnz     loc_1800045FC
0x180004574  mov     rcx, [r12]
0x180004578  mov     rax, [rcx+18h]
0x18000457c  mov     rcx, r12
0x18000457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004584  mov     r9, rax
0x180004587  xor     r8d, r8d
0x18000458a  mov     rcx, [rax]
0x18000458d  lea     edx, [r8+16h]
0x180004591  mov     rax, [rcx+10h]
0x180004595  mov     rcx, r9
0x180004598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459d  test    rax, rax
0x1800045a0  jz      short loc_1800045B6
0x1800045a2  cmp     [rbp+340h], rsi
0x1800045a9  jnz     short loc_1800045B6
0x1800045ab  mov     rdx, rax; char *
0x1800045ae  mov     rcx, rbp; this
0x1800045b1  call    ?UpdateEncodingsRejectedIfNeeded@OUTPUT_ENTRY@@QEAAXPEBD@Z; OUTPUT_ENTRY::UpdateEncodingsRejectedIfNeeded(char const *)
0x1800045b6  cmp     [rbp+338h], rsi
0x1800045bd  jz      short loc_180004605
0x1800045bf  mov     dword ptr [r13+0], 0Bh
0x1800045c7  jmp     loc_180004701
0x1800045cc  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x1800045d3  xor     r8d, r8d
0x1800045d6  mov     rdx, rbx
0x1800045d9  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x1800045df  mov     rbp, rbx
0x1800045e2  test    eax, eax
0x1800045e4  jz      loc_18000453A
0x1800045ea  mov     dword ptr [r13+0], 0Bh
0x1800045f2  mov     edi, 80004005h
0x1800045f7  jmp     loc_180004701
0x1800045fc  cmp     [rbp+340h], rsi
0x180004603  jmp     short loc_1800045BD
0x180004605  mov     ecx, 258h; Size
0x18000460a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000460f  mov     rsi, rax
0x180004612  test    rax, rax
0x180004615  jz      loc_1800046F5
0x18000461b  lea     rax, ??_7RESPONSE_ENTRY@@6B@; const RESPONSE_ENTRY::`vftable'
0x180004622  mov     qword ptr [rsi+8], 1
0x18000462a  lea     rcx, [rsi+10h]; void *
0x18000462e  mov     [rsi], rax
0x180004631  xor     edx, edx; Val
0x180004633  mov     dword ptr [rsi+24Ch], 0
0x18000463d  mov     r8d, 238h; Size
0x180004643  mov     dword ptr [rsi+250h], 0FFFFFFFFh
0x18000464d  call    memset_0
0x180004652  mov     rbx, qword ptr [rsp+68h+arg_0]
0x180004657  mov     r8, r15; struct IHttpCachePolicy *
0x18000465a  mov     r9d, ebx; unsigned int
0x18000465d  mov     rdx, r12; struct IHttpContext *
0x180004660  mov     rcx, rsi; this
0x180004663  call    ?Initialize@RESPONSE_ENTRY@@QEAAJPEAVIHttpContext@@PEAVIHttpCachePolicy@@K@Z; RESPONSE_ENTRY::Initialize(IHttpContext *,IHttpCachePolicy *,ulong)
0x180004668  mov     edi, eax
0x18000466a  test    eax, eax
0x18000466c  js      loc_180004701
0x180004672  mov     r8, [rsp+68h+arg_18]; char *
0x18000467a  mov     rdx, rsi; struct RESPONSE_ENTRY *
0x18000467d  mov     rcx, rbp; this
0x180004680  call    ?SetResponseEntry@OUTPUT_ENTRY@@QEAAJPEAVRESPONSE_ENTRY@@PEBD@Z; OUTPUT_ENTRY::SetResponseEntry(RESPONSE_ENTRY *,char const *)
0x180004685  mov     edi, eax
0x180004687  test    eax, eax
0x180004689  js      loc_1800045BF
0x18000468f  mov     rcx, cs:?g_pOutputCache@@3PEAVOUTPUT_CACHE@@EA; OUTPUT_CACHE * g_pOutputCache
0x180004696  xor     esi, esi
0x180004698  mov     [r13+0], esi
0x18000469c  lea     r15d, [rsi+1]
0x1800046a0  lock add [rcx+74h], r15d
0x1800046a5  mov     eax, ebx
0x1800046a7  lock add [rcx+68h], rax
0x1800046ac  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800046b3  mov     rax, [rcx]
0x1800046b6  mov     rax, [rax+60h]
0x1800046ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046bf  mov     rbx, rax
0x1800046c2  lea     edx, [rsi+12h]
0x1800046c5  mov     r8d, r15d
0x1800046c8  mov     rcx, [rax]
  ... truncated ...
```
