# GlobalDoWork(ulong,IHttpEventProvider *)

- ea: `0x180001010`
- end: `0x18000120d`
- name: `?GlobalDoWork@@YA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(int, struct ICacheProvider *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800036d0`

## callees

- `0x180001010`
- `0x1800013f0`
- `0x180004010`

## import_xrefs

- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800011aa`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800011fd`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800011aa`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800011fd`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x1800011c3`
- `iisutil!?Clear@TREE_HASH_TABLE@@QEAAXXZ` at `0x1800011c3`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800010e5`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800010e5`

## pseudocode

```c
__int64 __fastcall GlobalDoWork(int a1, struct ICacheProvider *a2)
{
  TREE_HASH_TABLE *v3; // rbx
  bool v4; // zf
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v13; // eax
  __int64 v14; // rax
  const unsigned __int16 *v15; // rax
  void *v16; // rsi
  void (__fastcall ***v17)(_QWORD, __int64, __int64); // r9
  void (__fastcall *v18)(_QWORD, __int64, __int64); // rax
  int v19; // eax
  int v20; // ecx
  const unsigned __int16 *v21; // rax
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  void *v24; // [rsp+40h] [rbp+18h] BYREF

  if ( a1 == 16 )
  {
    v3 = (TREE_HASH_TABLE *)g_pFileCache;
    if ( g_pFileCache )
    {
      v4 = *((_BYTE *)g_pFileCache + 64) == 0;
      v24 = 0;
      if ( v4 )
        return 0;
      v5 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
      v7 = 0;
      do
      {
        v8 = *(unsigned __int16 *)(v6 + 2 * v7++);
        v9 = aFile[v7 - 1];
        v10 = (unsigned int)(v8 - v9);
      }
      while ( !(_DWORD)v10 && v7 != 5 );
      if ( (_DWORD)v10 )
      {
        return 0;
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(struct ICacheProvider *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 8LL))(
                a2,
                v9,
                v10,
                L"FILE");
        if ( v13 )
        {
          v19 = v13 - 1;
          if ( !v19 )
          {
            CACHED_FILE_INFO::CacheFile(a2);
            return 1;
          }
          if ( (unsigned int)(v19 - 1) <= 1 )
          {
            v22 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
            v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 40LL))(v22);
            TREE_HASH_TABLE::DeletePath(v3, v23);
            return 1;
          }
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
          v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
          TREE_HASH_TABLE::FindRecord(v3, v15, &v24);
          v16 = v24;
          v17 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
          v11 = 1;
          v18 = **v17;
          if ( v16 )
          {
            v18(v17, 0, 1);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v16 + 24LL))(v16);
            (*(void (__fastcall **)(struct ICacheProvider *, void *))(*(_QWORD *)a2 + 32LL))(a2, v16);
            return v11;
          }
          v18(v17, 1, 1);
        }
        return 0;
      }
    }
  }
  else
  {
    v20 = a1 - 4;
    if ( v20 )
    {
      if ( g_pFileCache && v20 == 124 )
      {
        v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 8LL))(a2);
        TREE_HASH_TABLE::DeletePath((TREE_HASH_TABLE *)g_pFileCache, v21);
      }
    }
    else if ( g_pFileCache )
    {
      TREE_HASH_TABLE::Clear((TREE_HASH_TABLE *)g_pFileCache);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_8], rbx
0x180001015  push    rdi
0x180001016  sub     rsp, 20h
0x18000101a  mov     rdi, rdx
0x18000101d  cmp     ecx, 10h
0x180001020  jnz     loc_18000117D
0x180001026  mov     rbx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x18000102d  test    rbx, rbx
0x180001030  jz      loc_1800011B0
0x180001036  cmp     byte ptr [rbx+40h], 0
0x18000103a  mov     [rsp+28h+arg_10], 0
0x180001043  jz      short loc_18000108E
0x180001045  mov     rax, [rdx]
0x180001048  mov     rcx, rdx
0x18000104b  mov     rax, [rax+10h]
0x18000104f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001054  mov     rdx, rax
0x180001057  mov     rcx, [rax]
0x18000105a  mov     rax, [rcx+8]
0x18000105e  mov     rcx, rdx
0x180001061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001066  xor     ecx, ecx
0x180001068  lea     r9, aFile; "FILE"
0x18000106f  nop
0x180001070  movzx   r8d, word ptr [rax+rcx*2]
0x180001075  inc     rcx
0x180001078  movzx   edx, word ptr [r9+rcx*2-2]
0x18000107e  sub     r8d, edx
0x180001081  jnz     short loc_180001089
0x180001083  cmp     rcx, 5
0x180001087  jnz     short loc_180001070
0x180001089  test    r8d, r8d
0x18000108c  jz      short loc_18000109D
0x18000108e  xor     ebx, ebx
0x180001090  mov     eax, ebx
0x180001092  mov     rbx, [rsp+28h+arg_8]
0x180001097  add     rsp, 20h
0x18000109b  pop     rdi
0x18000109c  retn
0x18000109d  mov     rax, [rdi]
0x1800010a0  mov     rcx, rdi
0x1800010a3  mov     [rsp+28h+arg_0], rsi
0x1800010a8  mov     rax, [rax+8]
0x1800010ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010b1  test    eax, eax
0x1800010b3  jnz     loc_180001161
0x1800010b9  mov     rax, [rdi]
0x1800010bc  mov     rcx, rdi
0x1800010bf  mov     rax, [rax+10h]
0x1800010c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010c8  mov     rdx, rax
0x1800010cb  mov     rcx, [rax]
0x1800010ce  mov     rax, [rcx+28h]
0x1800010d2  mov     rcx, rdx
0x1800010d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010da  mov     rdx, rax
0x1800010dd  lea     r8, [rsp+28h+arg_10]
0x1800010e2  mov     rcx, rbx
0x1800010e5  call    cs:__imp_?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z; TREE_HASH_TABLE::FindRecord(ushort const *,void * *)
0x1800010eb  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800010f2  mov     rsi, [rsp+28h+arg_10]
0x1800010f7  mov     rax, [rcx]
0x1800010fa  mov     rax, [rax+60h]
0x1800010fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001103  mov     r9, rax
0x180001106  mov     ebx, 1
0x18000110b  mov     r8d, ebx
0x18000110e  mov     rcx, [rax]
0x180001111  mov     rax, [rcx]
0x180001114  mov     rcx, r9
0x180001117  test    rsi, rsi
0x18000111a  jnz     short loc_18000112F
0x18000111c  mov     edx, ebx
0x18000111e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001123  xor     ebx, ebx
0x180001125  mov     rsi, [rsp+28h+arg_0]
0x18000112a  jmp     loc_180001090
0x18000112f  xor     edx, edx
0x180001131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001136  mov     rax, [rsi]
0x180001139  mov     rcx, rsi
0x18000113c  mov     rax, [rax+18h]
0x180001140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001145  mov     rax, [rdi]
0x180001148  mov     rdx, rsi
0x18000114b  mov     rcx, rdi
0x18000114e  mov     rax, [rax+20h]
0x180001152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001157  mov     rsi, [rsp+28h+arg_0]
0x18000115c  jmp     loc_180001090
0x180001161  sub     eax, 1
0x180001164  jnz     short loc_1800011CB
0x180001166  mov     rcx, rdi; struct ICacheProvider *
0x180001169  call    ?CacheFile@CACHED_FILE_INFO@@SAXPEAVICacheProvider@@@Z; CACHED_FILE_INFO::CacheFile(ICacheProvider *)
0x18000116e  mov     rsi, [rsp+28h+arg_0]
0x180001173  mov     ebx, 1
0x180001178  jmp     loc_180001090
0x18000117d  sub     ecx, 4
0x180001180  jz      short loc_1800011B7
0x180001182  cmp     cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA, 0; FILE_CACHE * g_pFileCache
0x18000118a  jz      short loc_1800011B0
0x18000118c  cmp     ecx, 7Ch ; '|'
0x18000118f  jnz     short loc_1800011B0
0x180001191  mov     rax, [rdx]
0x180001194  mov     rcx, rdi
0x180001197  mov     rax, [rax+8]
0x18000119b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011a0  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800011a7  mov     rdx, rax
0x1800011aa  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x1800011b0  xor     eax, eax
0x1800011b2  jmp     loc_180001092
0x1800011b7  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800011be  test    rcx, rcx
0x1800011c1  jz      short loc_1800011B0
0x1800011c3  call    cs:__imp_?Clear@TREE_HASH_TABLE@@QEAAXXZ; TREE_HASH_TABLE::Clear(void)
0x1800011c9  jmp     short loc_1800011B0
0x1800011cb  sub     eax, 1
0x1800011ce  jz      short loc_1800011D9
0x1800011d0  cmp     eax, 1
0x1800011d3  jnz     loc_180001123
0x1800011d9  mov     rax, [rdi]
0x1800011dc  mov     rcx, rdi
0x1800011df  mov     rax, [rax+10h]
0x1800011e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e8  mov     rcx, rax
0x1800011eb  mov     rdx, [rax]
0x1800011ee  mov     rax, [rdx+28h]
0x1800011f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011f7  mov     rdx, rax
0x1800011fa  mov     rcx, rbx
0x1800011fd  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x180001203  mov     ebx, 1
0x180001208  jmp     loc_180001125
```
