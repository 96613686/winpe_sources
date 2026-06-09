# NlpInternalCacheInitialize(void)

- ea: `0x1800425d0`
- end: `0x18004265e`
- name: `?NlpInternalCacheInitialize@@YAJXZ`
- size: `142`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180043e64`

## callees

- `0x180040cf8`
- `0x180040e74`
- `0x180040fec`
- `0x1800415a4`
- `0x180042168`
- `0x1800425d0`
- `0x180042c48`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x180042625`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileIntW` at `0x180042625`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800425df`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800425df`
- `ntdll!RtlReleaseResource` at `0x180042650`
- `ntdll!RtlReleaseResource` at `0x180042650`

## string_xrefs

- `0x180042617`: `CachedLogonsCount`

## pseudocode

```c
__int64 NlpInternalCacheInitialize(void)
{
  NTSTATUS CacheControlInfo; // ebx
  UINT ProfileIntW; // eax

  RtlAcquireResourceExclusive(&NlpLogonCacheCritSec, 1u);
  CacheControlInfo = NlpOpenCache();
  if ( CacheControlInfo < 0 )
  {
    HIDWORD(NlpCacheControl) = 0;
  }
  else
  {
    CacheControlInfo = NlpGetCacheControlInfo();
    if ( CacheControlInfo < 0
      || (CacheControlInfo = NlpCacheKeyInitialize(), CacheControlInfo < 0)
      || (CacheControlInfo = NlpBuildCteTable(), CacheControlInfo < 0)
      || (ProfileIntW = GetProfileIntW(L"Winlogon", L"CachedLogonsCount", 10),
          CacheControlInfo = NlpChangeCacheSizeIfNecessary(ProfileIntW),
          CacheControlInfo < 0) )
    {
      NlpCloseCache();
    }
  }
  RtlReleaseResource(&NlpLogonCacheCritSec);
  return (unsigned int)CacheControlInfo;
}

```

## disassembly

```asm
0x1800425d0  push    rbx
0x1800425d2  sub     rsp, 20h
0x1800425d6  mov     dl, 1; Wait
0x1800425d8  lea     rcx, NlpLogonCacheCritSec; Resource
0x1800425df  call    cs:__imp_RtlAcquireResourceExclusive
0x1800425e5  call    ?NlpOpenCache@@YAJXZ; NlpOpenCache(void)
0x1800425ea  mov     ebx, eax
0x1800425ec  test    eax, eax
0x1800425ee  js      short loc_18004263F
0x1800425f0  call    ?NlpGetCacheControlInfo@@YAJXZ; NlpGetCacheControlInfo(void)
0x1800425f5  mov     ebx, eax
0x1800425f7  test    eax, eax
0x1800425f9  js      short loc_180042638
0x1800425fb  call    ?NlpCacheKeyInitialize@@YAJXZ; NlpCacheKeyInitialize(void)
0x180042600  mov     ebx, eax
0x180042602  test    eax, eax
0x180042604  js      short loc_180042638
0x180042606  call    ?NlpBuildCteTable@@YAJXZ; NlpBuildCteTable(void)
0x18004260b  mov     ebx, eax
0x18004260d  test    eax, eax
0x18004260f  js      short loc_180042638
0x180042611  mov     r8d, 0Ah; nDefault
0x180042617  lea     rdx, KeyName; "CachedLogonsCount"
0x18004261e  lea     rcx, AppName; "Winlogon"
0x180042625  call    cs:__imp_GetProfileIntW
0x18004262b  mov     ecx, eax; unsigned int
0x18004262d  call    ?NlpChangeCacheSizeIfNecessary@@YAJI@Z; NlpChangeCacheSizeIfNecessary(uint)
0x180042632  mov     ebx, eax
0x180042634  test    eax, eax
0x180042636  jns     short loc_180042649
0x180042638  call    ?NlpCloseCache@@YAXXZ; NlpCloseCache(void)
0x18004263d  jmp     short loc_180042649
0x18004263f  mov     dword ptr cs:NlpCacheControl+4, 0
0x180042649  lea     rcx, NlpLogonCacheCritSec; Resource
0x180042650  call    cs:__imp_RtlReleaseResource
0x180042656  mov     eax, ebx
0x180042658  add     rsp, 20h
0x18004265c  pop     rbx
0x18004265d  retn
```
