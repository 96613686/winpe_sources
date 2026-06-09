# CTVOAgent::AutoFlush(ulong *,int)

- ea: `0x180019584`
- end: `0x1800195ef`
- name: `?AutoFlush@CTVOAgent@@QEAAHPEAKH@Z`
- size: `107`
- prototype: `__int64 __fastcall(CTVOAgent *__hidden this, unsigned int *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180019570`

## callees

- `0x180019584`
- `0x1800195f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800195a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800195a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800195ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800195ca`

## pseudocode

```c
__int64 __fastcall CTVOAgent::AutoFlush(CTVOAgent *this, unsigned int *a2, int a3)
{
  LPCRITICAL_SECTION v3; // rdi
  unsigned int v6; // esi
  unsigned int EntryCount; // ebx
  CTVOCache *v8; // rcx
  __int64 result; // rax

  v3 = g_pProcessTVOAgent;
  v6 = 0;
  EnterCriticalSection(g_pProcessTVOAgent);
  if ( a3 )
  {
    v8 = (CTVOCache *)&v3[1];
    EntryCount = v3[1].DebugInfo[1].EntryCount;
  }
  else
  {
    if ( HIDWORD(v3[1].LockSemaphore) )
    {
      EntryCount = 0;
      goto LABEL_6;
    }
    EntryCount = (unsigned int)v3[1].LockSemaphore;
    v8 = (CTVOCache *)&v3[1];
  }
  if ( EntryCount )
  {
    LODWORD(v3[1].LockSemaphore) = 0;
    v6 = 1;
    CTVOCache::RemoveAllCacheEntries(v8);
  }
LABEL_6:
  LeaveCriticalSection(v3);
  result = v6;
  *a2 = EntryCount;
  return result;
}

```

## disassembly

```asm
0x180019584  push    rbx
0x180019586  push    rsi
0x180019587  push    rdi
0x180019588  push    r14
0x18001958a  sub     rsp, 28h
0x18001958e  mov     rdi, cs:?g_pProcessTVOAgent@@3PEAVCTVOAgent@@EA; CTVOAgent * g_pProcessTVOAgent
0x180019595  mov     ebx, r8d
0x180019598  mov     rcx, rdi; lpCriticalSection
0x18001959b  mov     r14, rdx
0x18001959e  xor     esi, esi
0x1800195a0  call    cs:__imp_EnterCriticalSection
0x1800195a6  test    ebx, ebx
0x1800195a8  jnz     short loc_1800195DF
0x1800195aa  cmp     [rdi+44h], esi
0x1800195ad  jnz     short loc_1800195EB
0x1800195af  mov     ebx, [rdi+40h]
0x1800195b2  lea     rcx, [rdi+28h]; this
0x1800195b6  test    ebx, ebx
0x1800195b8  jz      short loc_1800195C7
0x1800195ba  mov     [rdi+40h], esi
0x1800195bd  mov     esi, 1
0x1800195c2  call    ?RemoveAllCacheEntries@CTVOCache@@QEAAXXZ; CTVOCache::RemoveAllCacheEntries(void)
0x1800195c7  mov     rcx, rdi; lpCriticalSection
0x1800195ca  call    cs:__imp_LeaveCriticalSection
0x1800195d0  mov     eax, esi
0x1800195d2  mov     [r14], ebx
0x1800195d5  add     rsp, 28h
0x1800195d9  pop     r14
0x1800195db  pop     rdi
0x1800195dc  pop     rsi
0x1800195dd  pop     rbx
0x1800195de  retn
0x1800195df  lea     rcx, [rdi+28h]
0x1800195e3  mov     rax, [rcx]
0x1800195e6  mov     ebx, [rax+50h]
0x1800195e9  jmp     short loc_1800195B6
0x1800195eb  xor     ebx, ebx
0x1800195ed  jmp     short loc_1800195C7
```
