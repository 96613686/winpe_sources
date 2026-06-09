# CACHED_FILE_INFO::CacheFile(ICacheProvider *)

- ea: `0x1800013f0`
- end: `0x180001547`
- name: `?CacheFile@CACHED_FILE_INFO@@SAXPEAVICacheProvider@@@Z`
- size: `343`
- prototype: `void __fastcall(struct ICacheProvider *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001010`
- `0x180001220`

## callees

- `0x1800013f0`
- `0x180001550`
- `0x180001630`
- `0x1800028e0`
- `0x180004010`

## import_xrefs

- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800014ac`
- `iisutil!?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z` at `0x1800014ac`

## pseudocode

```c
void __fastcall CACHED_FILE_INFO::CacheFile(struct ICacheProvider *a1)
{
  const struct IHttpFileInfo *v2; // rdi
  unsigned int v3; // ecx
  CACHED_FILE_INFO *v4; // rax
  CACHED_FILE_INFO *v5; // rax
  CACHED_FILE_INFO *v6; // rbx
  void (__fastcall ***v7)(_QWORD, __int64, __int64); // rdi
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = (const struct IHttpFileInfo *)(*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a1 + 24LL))(a1);
  v8 = 0;
  (*(void (__fastcall **)(const struct IHttpFileInfo *, unsigned __int64 *))(*(_QWORD *)v2 + 64LL))(v2, &v8);
  if ( (*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)v2 + 80LL))(v2) != -1 )
  {
    v3 = *((_DWORD *)g_pFileCache + 14);
    if ( (!v3 || v3 > *((_DWORD *)g_pFileCache + 15)) && v8 <= *((_QWORD *)g_pFileCache + 5) )
    {
      v4 = (CACHED_FILE_INFO *)operator new(0x340u);
      if ( v4 )
      {
        v5 = CACHED_FILE_INFO::CACHED_FILE_INFO(v4);
        v6 = v5;
        if ( v5 )
        {
          if ( (int)CACHED_FILE_INFO::Initialize(v5, v2) < 0
            || (int)TREE_HASH_TABLE::InsertRecord((TREE_HASH_TABLE *)g_pFileCache, v6) < 0 )
          {
            (*(void (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)v6 + 16LL))(v6);
          }
          else
          {
            _InterlockedIncrement((volatile signed __int32 *)g_pFileCache + 15);
            v7 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
            (**v7)(v7, 26, 1);
            (**v7)(v7, 27, 1);
            (*(void (__fastcall **)(struct ICacheProvider *, CACHED_FILE_INFO *))(*(_QWORD *)a1 + 32LL))(a1, v6);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800013f0  mov     [rsp+arg_10], rsi
0x1800013f5  push    rdi
0x1800013f6  sub     rsp, 20h
0x1800013fa  mov     rax, [rcx]
0x1800013fd  mov     rsi, rcx
0x180001400  mov     rax, [rax+18h]
0x180001404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001409  mov     rdi, rax
0x18000140c  mov     [rsp+28h+arg_0], 0
0x180001415  mov     rcx, rdi
0x180001418  mov     rdx, [rax]
0x18000141b  mov     rax, [rdx+40h]
0x18000141f  lea     rdx, [rsp+28h+arg_0]
0x180001424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001429  mov     rcx, [rdi]
0x18000142c  mov     rax, [rcx+50h]
0x180001430  mov     rcx, rdi
0x180001433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001438  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000143c  jz      loc_180001520
0x180001442  mov     rax, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180001449  mov     ecx, [rax+38h]
0x18000144c  test    ecx, ecx
0x18000144e  jnz     loc_18000153C
0x180001454  mov     rax, [rax+28h]
0x180001458  cmp     [rsp+28h+arg_0], rax
0x18000145d  ja      loc_180001520
0x180001463  mov     ecx, 340h; Size
0x180001468  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000146d  test    rax, rax
0x180001470  jz      loc_180001520
0x180001476  mov     rcx, rax; this
0x180001479  mov     [rsp+28h+arg_8], rbx
0x18000147e  call    ??0CACHED_FILE_INFO@@QEAA@XZ; CACHED_FILE_INFO::CACHED_FILE_INFO(void)
0x180001483  mov     rbx, rax
0x180001486  test    rax, rax
0x180001489  jz      loc_18000151B
0x18000148f  mov     rdx, rdi; struct IHttpFileInfo *
0x180001492  mov     rcx, rax; this
0x180001495  call    ?Initialize@CACHED_FILE_INFO@@QEAAJPEBVIHttpFileInfo@@@Z; CACHED_FILE_INFO::Initialize(IHttpFileInfo const *)
0x18000149a  test    eax, eax
0x18000149c  js      loc_18000152B
0x1800014a2  mov     rcx, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800014a9  mov     rdx, rbx
0x1800014ac  call    cs:__imp_?InsertRecord@TREE_HASH_TABLE@@QEAAJPEAX@Z; TREE_HASH_TABLE::InsertRecord(void *)
0x1800014b2  test    eax, eax
0x1800014b4  js      short loc_18000152B
0x1800014b6  mov     rax, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x1800014bd  lock inc dword ptr [rax+3Ch]
0x1800014c1  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800014c8  mov     rax, [rcx]
0x1800014cb  mov     rax, [rax+60h]
0x1800014cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d4  mov     rdi, rax
0x1800014d7  mov     edx, 1Ah
0x1800014dc  mov     r8d, 1
0x1800014e2  mov     rcx, [rax]
0x1800014e5  mov     rax, [rcx]
0x1800014e8  mov     rcx, rdi
0x1800014eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014f0  mov     rcx, [rdi]
0x1800014f3  mov     edx, 1Bh
0x1800014f8  mov     r8d, 1
0x1800014fe  mov     rax, [rcx]
0x180001501  mov     rcx, rdi
0x180001504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001509  mov     rax, [rsi]
0x18000150c  mov     rdx, rbx
0x18000150f  mov     rcx, rsi
0x180001512  mov     rax, [rax+20h]
0x180001516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151b  mov     rbx, [rsp+28h+arg_8]
0x180001520  mov     rsi, [rsp+28h+arg_10]
0x180001525  add     rsp, 20h
0x180001529  pop     rdi
0x18000152a  retn
0x18000152b  mov     rax, [rbx]
0x18000152e  mov     rcx, rbx
0x180001531  mov     rax, [rax+10h]
0x180001535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000153a  jmp     short loc_18000151B
0x18000153c  cmp     ecx, [rax+3Ch]
0x18000153f  ja      loc_180001454
0x180001545  jmp     short loc_180001520
```
