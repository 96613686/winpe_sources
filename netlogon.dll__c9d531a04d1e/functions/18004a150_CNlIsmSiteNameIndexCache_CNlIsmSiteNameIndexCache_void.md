# CNlIsmSiteNameIndexCache::~CNlIsmSiteNameIndexCache(void)

- ea: `0x18004a150`
- end: `0x18004a1df`
- name: `??1CNlIsmSiteNameIndexCache@@EEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CNlIsmSiteNameIndexCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18004a480`

## callees

- `0x18004a150`
- `0x18004b1b0`
- `0x18008504c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a1b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a1b8`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004a183`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004a183`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004a178`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004a1a7`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004a178`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004a1a7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004a197`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004a197`

## pseudocode

```c
void __fastcall CNlIsmSiteNameIndexCache::~CNlIsmSiteNameIndexCache(CNlIsmSiteNameIndexCache *this)
{
  struct _NL_ISM_SITENAME_CACHE_ENTRY **v2; // rax
  struct _RTL_AVL_TABLE *v3; // rcx
  struct _NL_ISM_SITENAME_CACHE_ENTRY *v4; // rbx
  CNlIsmSiteNameIndexCache *v5; // rcx

  *(_QWORD *)this = &CNlIsmSiteNameIndexCache::`vftable';
  NLRefcountableObjectWithLock::LockExclusive(this);
  RtlNumberGenericTableElementsAvl((PRTL_AVL_TABLE)((char *)this + 32));
  while ( 1 )
  {
    v2 = (struct _NL_ISM_SITENAME_CACHE_ENTRY **)RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)((char *)this + 32), 1u);
    v3 = (struct _RTL_AVL_TABLE *)((char *)this + 32);
    if ( !v2 )
      break;
    v4 = *v2;
    RtlDeleteElementGenericTableAvl(v3, v2);
    CNlIsmSiteNameIndexCache::FreeCacheEntry(v5, v4);
  }
  RtlNumberGenericTableElementsAvl(v3);
  *((_DWORD *)this + 6) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 2);
  _InterlockedDecrement((volatile signed __int32 *)&CNlIsmSiteNameIndexCache::s_ObjectCount);
  *(_QWORD *)this = &NLRefcountableObject::`vftable';
}

```

## disassembly

```asm
0x18004a150  mov     [rsp+arg_0], rbx
0x18004a155  mov     [rsp+arg_8], rsi
0x18004a15a  push    rdi
0x18004a15b  sub     rsp, 20h
0x18004a15f  lea     rax, ??_7CNlIsmSiteNameIndexCache@@6B@; const CNlIsmSiteNameIndexCache::`vftable'
0x18004a166  mov     rdi, rcx
0x18004a169  mov     [rcx], rax
0x18004a16c  call    ?LockExclusive@NLRefcountableObjectWithLock@@QEAAXXZ; NLRefcountableObjectWithLock::LockExclusive(void)
0x18004a171  lea     rsi, [rdi+20h]
0x18004a175  mov     rcx, rsi; Table
0x18004a178  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18004a17e  mov     dl, 1; Restart
0x18004a180  mov     rcx, rsi; Table
0x18004a183  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18004a189  mov     rcx, rsi; Table
0x18004a18c  test    rax, rax
0x18004a18f  jz      short loc_18004A1A7
0x18004a191  mov     rbx, [rax]
0x18004a194  mov     rdx, rax; Buffer
0x18004a197  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18004a19d  mov     rdx, rbx; struct _NL_ISM_SITENAME_CACHE_ENTRY *
0x18004a1a0  call    ?FreeCacheEntry@CNlIsmSiteNameIndexCache@@AEAAXPEAU_NL_ISM_SITENAME_CACHE_ENTRY@@@Z; CNlIsmSiteNameIndexCache::FreeCacheEntry(_NL_ISM_SITENAME_CACHE_ENTRY *)
0x18004a1a5  jmp     short loc_18004A17E
0x18004a1a7  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18004a1ad  lea     rcx, [rdi+10h]; SRWLock
0x18004a1b1  mov     dword ptr [rdi+18h], 0
0x18004a1b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a1be  lock dec cs:?s_ObjectCount@CNlIsmSiteNameIndexCache@@0KA; ulong CNlIsmSiteNameIndexCache::s_ObjectCount
0x18004a1c5  lea     rax, ??_7NLRefcountableObject@@6B@; const NLRefcountableObject::`vftable'
0x18004a1cc  mov     rbx, [rsp+28h+arg_0]
0x18004a1d1  mov     rsi, [rsp+28h+arg_8]
0x18004a1d6  mov     [rdi], rax
0x18004a1d9  add     rsp, 20h
0x18004a1dd  pop     rdi
0x18004a1de  retn
```
