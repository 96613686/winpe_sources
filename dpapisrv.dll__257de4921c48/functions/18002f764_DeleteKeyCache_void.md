# DeleteKeyCache(void)

- ea: `0x18002f764`
- end: `0x18002f807`
- name: `?DeleteKeyCache@@YAXXZ`
- size: `163`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800283c4`

## callees

- `0x18002f764`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f7c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f7c8`
- `ntdll!RtlEnterCriticalSection` at `0x18002f779`
- `ntdll!RtlEnterCriticalSection` at `0x18002f779`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f7e4`
- `ntdll!RtlLeaveCriticalSection` at `0x18002f7e4`
- `ntdll!RtlDeleteCriticalSection` at `0x18002f7fb`

## pseudocode

```c
void DeleteKeyCache(void)
{
  _BYTE *v0; // rax
  _QWORD *v1; // rcx
  HLOCAL *v2; // rdx
  __int64 v3; // rdx
  _BYTE *v4; // rcx

  fKeyCacheInitialized = 0;
  RtlEnterCriticalSection(&g_MasterKeyCacheCritSect);
  while ( 1 )
  {
    v0 = g_MasterKeyCacheList;
    if ( g_MasterKeyCacheList == &g_MasterKeyCacheList )
      break;
    v1 = *(_QWORD **)g_MasterKeyCacheList;
    if ( *(HLOCAL *)(*(_QWORD *)g_MasterKeyCacheList + 8LL) != g_MasterKeyCacheList
      || (v2 = (HLOCAL *)*((_QWORD *)g_MasterKeyCacheList + 1), *v2 != g_MasterKeyCacheList) )
    {
      __fastfail(3u);
    }
    *v2 = v1;
    v1[1] = v2;
    v3 = 128;
    v4 = v0;
    do
    {
      *v4++ = 0;
      --v3;
    }
    while ( v3 );
    LocalFree(v0);
  }
  RtlLeaveCriticalSection(&g_MasterKeyCacheCritSect);
  RtlDeleteCriticalSection(&g_MasterKeyCacheCritSect);
}

```

## disassembly

```asm
0x18002f764  sub     rsp, 28h
0x18002f768  lea     rcx, ?g_MasterKeyCacheCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002f76f  mov     cs:?fKeyCacheInitialized@@3HA, 0; int fKeyCacheInitialized
0x18002f779  call    cs:__imp_RtlEnterCriticalSection
0x18002f780  nop     dword ptr [rax+rax+00h]
0x18002f785  mov     rax, cs:?g_MasterKeyCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MasterKeyCacheList
0x18002f78c  lea     rcx, ?g_MasterKeyCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MasterKeyCacheList
0x18002f793  cmp     rax, rcx
0x18002f796  jz      short loc_18002F7DD
0x18002f798  mov     rcx, [rax]
0x18002f79b  cmp     [rcx+8], rax
0x18002f79f  jnz     short loc_18002F7D6
0x18002f7a1  mov     rdx, [rax+8]
0x18002f7a5  cmp     [rdx], rax
0x18002f7a8  jnz     short loc_18002F7D6
0x18002f7aa  mov     [rdx], rcx
0x18002f7ad  mov     [rcx+8], rdx
0x18002f7b1  mov     edx, 80h
0x18002f7b6  mov     rcx, rax
0x18002f7b9  mov     byte ptr [rcx], 0
0x18002f7bc  inc     rcx
0x18002f7bf  sub     rdx, 1
0x18002f7c3  jnz     short loc_18002F7B9
0x18002f7c5  mov     rcx, rax; hMem
0x18002f7c8  call    cs:__imp_LocalFree
0x18002f7cf  nop     dword ptr [rax+rax+00h]
0x18002f7d4  jmp     short loc_18002F785
0x18002f7d6  mov     ecx, 3
0x18002f7db  int     29h; Win8: RtlFailFast(ecx)
0x18002f7dd  lea     rcx, ?g_MasterKeyCacheCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002f7e4  call    cs:__imp_RtlLeaveCriticalSection
0x18002f7eb  nop     dword ptr [rax+rax+00h]
0x18002f7f0  lea     rcx, ?g_MasterKeyCacheCritSect@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_MasterKeyCacheCritSect
0x18002f7f7  add     rsp, 28h
0x18002f7fb  jmp     cs:__imp_RtlDeleteCriticalSection
```
