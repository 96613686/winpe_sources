# CIISGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180001220`
- end: `0x1800013e5`
- name: `?OnGlobalCacheOperation@CIISGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `453`
- prototype: `enum GLOBAL_NOTIFICATION_STATUS __high(struct ICacheProvider *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001220`
- `0x1800013f0`
- `0x180004010`

## import_xrefs

- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800013d5`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x1800013d5`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800012f0`
- `iisutil!?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z` at `0x1800012f0`

## pseudocode

```c
__int64 __fastcall CIISGlobalModule::OnGlobalCacheOperation(__int64 a1, struct ICacheProvider *a2)
{
  TREE_HASH_TABLE *v2; // rdi
  unsigned int v3; // ebx
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // rdx
  int v11; // ecx
  __int64 v12; // rax
  const unsigned __int16 *v13; // rax
  void *v14; // rdi
  void (__fastcall ***v15)(_QWORD, __int64, __int64); // rax
  int v16; // ecx
  __int64 v17; // rax
  const unsigned __int16 *v18; // rax
  void *v19; // [rsp+40h] [rbp+18h] BYREF

  v2 = (TREE_HASH_TABLE *)g_pFileCache;
  v3 = 0;
  if ( !g_pFileCache )
    return v3;
  v19 = 0;
  if ( !*((_BYTE *)g_pFileCache + 64) )
    return v3;
  v5 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v7 = 0;
  do
  {
    v8 = *(unsigned __int16 *)(v6 + 2 * v7++);
    v9 = v8 - (unsigned int)aFile[v7 - 1];
  }
  while ( !(_DWORD)v9 && v7 != 5 );
  if ( (_DWORD)v9 )
    return v3;
  v11 = (*(__int64 (__fastcall **)(struct ICacheProvider *, __int64, __int64, const wchar_t *))(*(_QWORD *)a2 + 8LL))(
          a2,
          v9,
          v6,
          L"FILE");
  if ( v11 )
  {
    v16 = v11 - 1;
    if ( v16 )
    {
      if ( (unsigned int)(v16 - 1) <= 1 )
      {
        v17 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
        v18 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17);
        TREE_HASH_TABLE::DeletePath(v2, v18);
        return 1;
      }
      return v3;
    }
    CACHED_FILE_INFO::CacheFile(a2);
    return 1;
  }
  else
  {
    v12 = (*(__int64 (__fastcall **)(struct ICacheProvider *))(*(_QWORD *)a2 + 16LL))(a2);
    v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
    TREE_HASH_TABLE::FindRecord(v2, v13, &v19);
    v14 = v19;
    v15 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    if ( !v14 )
    {
      (**v15)(v15, 1, 1);
      return v3;
    }
    (**v15)(v15, 0, 1);
    (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 24LL))(v14);
    (*(void (__fastcall **)(struct ICacheProvider *, void *))(*(_QWORD *)a2 + 32LL))(a2, v14);
    return 1;
  }
}

```

## disassembly

```asm
0x180001220  mov     [rsp+arg_0], rbx
0x180001225  mov     [rsp+arg_8], rsi
0x18000122a  push    rdi
0x18000122b  sub     rsp, 20h
0x18000122f  mov     rdi, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180001236  xor     ebx, ebx
0x180001238  mov     rsi, rdx
0x18000123b  test    rdi, rdi
0x18000123e  jz      short loc_18000129C
0x180001240  mov     [rsp+28h+arg_10], rbx
0x180001245  cmp     [rdi+40h], bl
0x180001248  jz      short loc_18000129C
0x18000124a  mov     rax, [rdx]
0x18000124d  mov     rcx, rdx
0x180001250  mov     rax, [rax+10h]
0x180001254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001259  mov     rcx, rax
0x18000125c  mov     rax, [rax]
0x18000125f  mov     rax, [rax+8]
0x180001263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001268  mov     r8, rax
0x18000126b  lea     r9, aFile; "FILE"
0x180001272  mov     eax, ebx
0x180001274  nop     dword ptr [rax+00h]
0x180001278  nop     dword ptr [rax+rax+00000000h]
0x180001280  movzx   edx, word ptr [r8+rax*2]
0x180001285  inc     rax
0x180001288  movzx   ecx, word ptr [r9+rax*2-2]
0x18000128e  sub     edx, ecx
0x180001290  jnz     short loc_180001298
0x180001292  cmp     rax, 5
0x180001296  jnz     short loc_180001280
0x180001298  test    edx, edx
0x18000129a  jz      short loc_1800012AE
0x18000129c  mov     eax, ebx
0x18000129e  mov     rbx, [rsp+28h+arg_0]
0x1800012a3  mov     rsi, [rsp+28h+arg_8]
0x1800012a8  add     rsp, 20h
0x1800012ac  pop     rdi
0x1800012ad  retn
0x1800012ae  mov     rax, [rsi]
0x1800012b1  mov     rcx, rsi
0x1800012b4  mov     rax, [rax+8]
0x1800012b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012bd  mov     ecx, eax
0x1800012bf  test    eax, eax
0x1800012c1  jnz     loc_18000137F
0x1800012c7  mov     rax, [rsi]
0x1800012ca  mov     rcx, rsi
0x1800012cd  mov     rax, [rax+10h]
0x1800012d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012d6  mov     rcx, rax
0x1800012d9  mov     rax, [rax]
0x1800012dc  mov     rax, [rax+28h]
0x1800012e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012e5  mov     rdx, rax
0x1800012e8  lea     r8, [rsp+28h+arg_10]
0x1800012ed  mov     rcx, rdi
0x1800012f0  call    cs:__imp_?FindRecord@TREE_HASH_TABLE@@QEAAXPEBGPEAPEAX@Z; TREE_HASH_TABLE::FindRecord(ushort const *,void * *)
0x1800012f6  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800012fd  mov     rdi, [rsp+28h+arg_10]
0x180001302  mov     rax, [rcx]
0x180001305  mov     rax, [rax+60h]
0x180001309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000130e  test    rdi, rdi
0x180001311  jnz     short loc_180001331
0x180001313  mov     rcx, [rax]
0x180001316  mov     r9, rax
0x180001319  mov     edx, 1
0x18000131e  mov     r8d, edx
0x180001321  mov     rax, [rcx]
0x180001324  mov     rcx, r9
0x180001327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000132c  jmp     loc_18000129C
0x180001331  mov     rcx, rax
0x180001334  xor     edx, edx
0x180001336  mov     rax, [rax]
0x180001339  mov     r8d, 1
0x18000133f  mov     rax, [rax]
0x180001342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001347  mov     rax, [rdi]
0x18000134a  mov     rcx, rdi
0x18000134d  mov     rax, [rax+18h]
0x180001351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001356  mov     rax, [rsi]
0x180001359  mov     rdx, rdi
0x18000135c  mov     rcx, rsi
0x18000135f  mov     rax, [rax+20h]
0x180001363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001368  mov     ebx, 1
0x18000136d  mov     eax, ebx
0x18000136f  mov     rbx, [rsp+28h+arg_0]
0x180001374  mov     rsi, [rsp+28h+arg_8]
0x180001379  add     rsp, 20h
0x18000137d  pop     rdi
0x18000137e  retn
0x18000137f  sub     ecx, 1
0x180001382  jnz     short loc_1800013A3
0x180001384  mov     rcx, rsi; struct ICacheProvider *
0x180001387  call    ?CacheFile@CACHED_FILE_INFO@@SAXPEAVICacheProvider@@@Z; CACHED_FILE_INFO::CacheFile(ICacheProvider *)
0x18000138c  mov     rsi, [rsp+28h+arg_8]
0x180001391  mov     ebx, 1
0x180001396  mov     eax, ebx
0x180001398  mov     rbx, [rsp+28h+arg_0]
0x18000139d  add     rsp, 20h
0x1800013a1  pop     rdi
0x1800013a2  retn
0x1800013a3  sub     ecx, 1
0x1800013a6  jz      short loc_1800013B1
0x1800013a8  cmp     ecx, 1
0x1800013ab  jnz     loc_18000129C
0x1800013b1  mov     rax, [rsi]
0x1800013b4  mov     rcx, rsi
0x1800013b7  mov     rax, [rax+10h]
0x1800013bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013c0  mov     rcx, rax
0x1800013c3  mov     rax, [rax]
0x1800013c6  mov     rax, [rax+28h]
0x1800013ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013cf  mov     rdx, rax
0x1800013d2  mov     rcx, rdi
0x1800013d5  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x1800013db  mov     ebx, 1
0x1800013e0  jmp     loc_18000129C
```
