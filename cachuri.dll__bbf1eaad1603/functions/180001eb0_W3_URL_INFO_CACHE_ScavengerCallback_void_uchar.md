# W3_URL_INFO_CACHE::ScavengerCallback(void *,uchar)

- ea: `0x180001eb0`
- end: `0x180001f20`
- name: `?ScavengerCallback@W3_URL_INFO_CACHE@@CAXPEAXE@Z`
- size: `112`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001eb0`
- `0x180003010`

## import_xrefs

- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180001f05`
- `iisutil!?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z` at `0x180001f05`

## pseudocode

```c
void __fastcall W3_URL_INFO_CACHE::ScavengerCallback(TREE_HASH_TABLE *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64, __int64); // rax

  if ( !_InterlockedCompareExchange(&W3_URL_INFO_CACHE::sm_fScavengerFired, 1, 0) )
  {
    v2 = (void (__fastcall ***)(_QWORD, __int64, __int64))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 96LL))(g_pGlobalInfo);
    (**v2)(v2, 10, 1);
    TREE_HASH_TABLE::DeleteIf(a1, (int (*)(void *, void *))W3_URL_INFO_CACHE::CacheFlushByTTL, 0);
    W3_URL_INFO_CACHE::sm_fScavengerFired = 0;
  }
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp+arg_0], rbx
0x180001eb5  push    rdi
0x180001eb6  sub     rsp, 20h
0x180001eba  mov     rbx, rcx
0x180001ebd  mov     edi, 1
0x180001ec2  xor     eax, eax
0x180001ec4  lock cmpxchg cs:?sm_fScavengerFired@W3_URL_INFO_CACHE@@0HA, edi; int W3_URL_INFO_CACHE::sm_fScavengerFired
0x180001ecc  jnz     short loc_180001F15
0x180001ece  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001ed5  mov     rax, [rcx]
0x180001ed8  mov     rax, [rax+60h]
0x180001edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee1  mov     r9, rax
0x180001ee4  lea     edx, [rdi+9]
0x180001ee7  mov     r8d, edi
0x180001eea  mov     rcx, [rax]
0x180001eed  mov     rax, [rcx]
0x180001ef0  mov     rcx, r9
0x180001ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ef8  xor     r8d, r8d
0x180001efb  lea     rdx, ?CacheFlushByTTL@W3_URL_INFO_CACHE@@CAHPEAX0@Z; W3_URL_INFO_CACHE::CacheFlushByTTL(void *,void *)
0x180001f02  mov     rcx, rbx
0x180001f05  call    cs:__imp_?DeleteIf@TREE_HASH_TABLE@@QEAAXP6AHPEAX0@Z0@Z; TREE_HASH_TABLE::DeleteIf(int (*)(void *,void *),void *)
0x180001f0b  mov     cs:?sm_fScavengerFired@W3_URL_INFO_CACHE@@0HA, 0; int W3_URL_INFO_CACHE::sm_fScavengerFired
0x180001f15  mov     rbx, [rsp+28h+arg_0]
0x180001f1a  add     rsp, 20h
0x180001f1e  pop     rdi
0x180001f1f  retn
```
