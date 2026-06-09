# CNlIsmSiteNameIndexCache::Purge(void)

- ea: `0x18004f0b8`
- end: `0x18004f149`
- name: `?Purge@CNlIsmSiteNameIndexCache@@AEAAXXZ`
- size: `145`
- prototype: `void __fastcall(CNlIsmSiteNameIndexCache *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18004d464`

## callees

- `0x18004e3ac`
- `0x18004f0b8`
- `0x18008b240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004f13d`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f0e7`
- `ntdll!RtlEnumerateGenericTableAvl` at `0x18004f0e7`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004f0d6`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004f117`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004f0d6`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18004f117`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004f101`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18004f101`

## pseudocode

```c
void __fastcall CNlIsmSiteNameIndexCache::Purge(CNlIsmSiteNameIndexCache *this)
{
  struct _NL_ISM_SITENAME_CACHE_ENTRY **v2; // rax
  struct _RTL_AVL_TABLE *v3; // rcx
  struct _NL_ISM_SITENAME_CACHE_ENTRY *v4; // rbx
  CNlIsmSiteNameIndexCache *v5; // rcx

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
}

```

## disassembly

```asm
0x18004f0b8  mov     [rsp+arg_0], rbx
0x18004f0bd  mov     [rsp+arg_8], rsi
0x18004f0c2  push    rdi
0x18004f0c3  sub     rsp, 20h
0x18004f0c7  mov     rdi, rcx
0x18004f0ca  call    ?LockExclusive@NLRefcountableObjectWithLock@@QEAAXXZ; NLRefcountableObjectWithLock::LockExclusive(void)
0x18004f0cf  lea     rsi, [rdi+20h]
0x18004f0d3  mov     rcx, rsi; Table
0x18004f0d6  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18004f0dd  nop     dword ptr [rax+rax+00h]
0x18004f0e2  mov     dl, 1; Restart
0x18004f0e4  mov     rcx, rsi; Table
0x18004f0e7  call    cs:__imp_RtlEnumerateGenericTableAvl
0x18004f0ee  nop     dword ptr [rax+rax+00h]
0x18004f0f3  mov     rcx, rsi; Table
0x18004f0f6  test    rax, rax
0x18004f0f9  jz      short loc_18004F117
0x18004f0fb  mov     rbx, [rax]
0x18004f0fe  mov     rdx, rax; Buffer
0x18004f101  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18004f108  nop     dword ptr [rax+rax+00h]
0x18004f10d  mov     rdx, rbx; struct _NL_ISM_SITENAME_CACHE_ENTRY *
0x18004f110  call    ?FreeCacheEntry@CNlIsmSiteNameIndexCache@@AEAAXPEAU_NL_ISM_SITENAME_CACHE_ENTRY@@@Z; CNlIsmSiteNameIndexCache::FreeCacheEntry(_NL_ISM_SITENAME_CACHE_ENTRY *)
0x18004f115  jmp     short loc_18004F0E2
0x18004f117  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18004f11e  nop     dword ptr [rax+rax+00h]
0x18004f123  lea     rcx, [rdi+10h]
0x18004f127  mov     dword ptr [rdi+18h], 0
0x18004f12e  mov     rbx, [rsp+28h+arg_0]
0x18004f133  mov     rsi, [rsp+28h+arg_8]
0x18004f138  add     rsp, 20h
0x18004f13c  pop     rdi
0x18004f13d  jmp     cs:__imp_ReleaseSRWLockExclusive
```
