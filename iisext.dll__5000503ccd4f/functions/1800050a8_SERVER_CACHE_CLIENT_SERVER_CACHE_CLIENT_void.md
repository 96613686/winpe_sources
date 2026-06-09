# SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(void)

- ea: `0x1800050a8`
- end: `0x18000510b`
- name: `??1SERVER_CACHE_CLIENT@@QEAA@XZ`
- size: `99`
- prototype: `void __fastcall(SERVER_CACHE_CLIENT *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004f98`
- `0x1800064a0`
- `0x180007020`
- `0x180007fd0`
- `0x1800085f0`
- `0x180009b20`
- `0x18000a65c`

## callees

- `0x180001048`
- `0x1800047f4`
- `0x1800050a8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800050c1`
- `KERNEL32!EnterCriticalSection` at `0x1800050c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800050fa`
- `KERNEL32!LeaveCriticalSection` at `0x1800050fa`

## pseudocode

```c
void __fastcall SERVER_CACHE_CLIENT::~SERVER_CACHE_CLIENT(SERVER_CACHE_CLIENT *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  SERVER_CACHE *v2; // rdi

  v1 = g_pGlobalLock;
  if ( g_pGlobalLock )
  {
    EnterCriticalSection(g_pGlobalLock);
    if ( !--SERVER_CACHE::sm_cRefs )
    {
      v2 = SERVER_CACHE::sm_pServerCache;
      if ( SERVER_CACHE::sm_pServerCache )
      {
        SERVER_CACHE::~SERVER_CACHE(SERVER_CACHE::sm_pServerCache);
        operator delete(v2);
      }
      SERVER_CACHE::sm_pServerCache = 0;
    }
    LeaveCriticalSection(v1);
  }
}

```

## disassembly

```asm
0x1800050a8  mov     [rsp+arg_0], rbx
0x1800050ad  push    rdi
0x1800050ae  sub     rsp, 20h
0x1800050b2  mov     rbx, cs:?g_pGlobalLock@@3PEAVWIN32_CRITSEC@@EA; WIN32_CRITSEC * g_pGlobalLock
0x1800050b9  test    rbx, rbx
0x1800050bc  jz      short loc_180005100
0x1800050be  mov     rcx, rbx; lpCriticalSection
0x1800050c1  call    cs:__imp_EnterCriticalSection
0x1800050c7  sub     cs:?sm_cRefs@SERVER_CACHE@@1JA, 1; long SERVER_CACHE::sm_cRefs
0x1800050ce  jnz     short loc_1800050F7
0x1800050d0  mov     rdi, cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x1800050d7  test    rdi, rdi
0x1800050da  jz      short loc_1800050EC
0x1800050dc  mov     rcx, rdi; this
0x1800050df  call    ??1SERVER_CACHE@@IEAA@XZ; SERVER_CACHE::~SERVER_CACHE(void)
0x1800050e4  mov     rcx, rdi; Block
0x1800050e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800050ec  mov     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x1800050f7  mov     rcx, rbx; lpCriticalSection
0x1800050fa  call    cs:__imp_LeaveCriticalSection
0x180005100  mov     rbx, [rsp+28h+arg_0]
0x180005105  add     rsp, 20h
0x180005109  pop     rdi
0x18000510a  retn
```
