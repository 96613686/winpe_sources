# ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval(void)

- ea: `0x180020f90`
- end: `0x18002106b`
- name: `?SetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `219`
- prototype: `_BOOL8(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18001fbd0`

## callees

- `0x180020d04`
- `0x180020f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180020fc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180020fc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002100f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002100f`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180021048`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x180021048`

## string_xrefs

- `0x180020fd9`: `LookasideCleanupInterval`
- `0x180020ff0`: `AcacheHonorPageheap`
- `0x180020fb2`: `System\CurrentControlSet\Services\InetInfo\Parameters`

## pseudocode

```c
_BOOL8 ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval(void)
{
  int RegDword; // ebx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, g_PSZ_ACACHE_CONFIG_PARAMS_REG_KEY, 0, 0x20019u, &hKey) )
    return 1;
  RegDword = I_AtqReadRegDword(hKey, "LookasideCleanupInterval", 900);
  ALLOC_CACHE_HANDLER::sm_fHonorPageHeap = I_AtqReadRegDword(hKey, "AcacheHonorPageheap", 1);
  RegCloseKey(hKey);
  return !RegDword
      || CreateTimerQueueTimer(
           &ALLOC_CACHE_HANDLER::sm_hTimer,
           0,
           ALLOC_CACHE_HANDLER::CleanupAllLookasides,
           0,
           1000 * RegDword,
           1000 * RegDword,
           0x10u);
}

```

## disassembly

```asm
0x180020f90  push    rbx
0x180020f92  sub     rsp, 40h
0x180020f96  lea     rax, [rsp+48h+hKey]
0x180020f9b  mov     [rsp+48h+hKey], 0
0x180020fa4  mov     r9d, 20019h; samDesired
0x180020faa  mov     [rsp+48h+phkResult], rax; phkResult
0x180020faf  xor     r8d, r8d; ulOptions
0x180020fb2  lea     rdx, ?g_PSZ_ACACHE_CONFIG_PARAMS_REG_KEY@@3PADA; "System\\CurrentControlSet\\Services\\In"...
0x180020fb9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020fc0  call    cs:__imp_RegOpenKeyExA
0x180020fc7  nop     dword ptr [rax+rax+00h]
0x180020fcc  test    eax, eax
0x180020fce  jnz     loc_18002105F
0x180020fd4  mov     rcx, [rsp+48h+hKey]
0x180020fd9  lea     rdx, aLookasideclean; "LookasideCleanupInterval"
0x180020fe0  mov     r8d, 384h
0x180020fe6  call    I_AtqReadRegDword
0x180020feb  mov     rcx, [rsp+48h+hKey]
0x180020ff0  lea     rdx, aAcachehonorpag; "AcacheHonorPageheap"
0x180020ff7  mov     r8d, 1
0x180020ffd  mov     ebx, eax
0x180020fff  call    I_AtqReadRegDword
0x180021004  mov     rcx, [rsp+48h+hKey]; hKey
0x180021009  mov     cs:?sm_fHonorPageHeap@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fHonorPageHeap
0x18002100f  call    cs:__imp_RegCloseKey
0x180021016  nop     dword ptr [rax+rax+00h]
0x18002101b  test    ebx, ebx
0x18002101d  jz      short loc_18002105F
0x18002101f  imul    eax, ebx, 3E8h
0x180021025  lea     r8, ?CleanupAllLookasides@ALLOC_CACHE_HANDLER@@SAXPEAXE@Z; Callback
0x18002102c  mov     [rsp+48h+Flags], 10h; Flags
0x180021034  lea     rcx, ?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; phNewTimer
0x18002103b  xor     r9d, r9d; Parameter
0x18002103e  xor     edx, edx; TimerQueue
0x180021040  mov     [rsp+48h+Period], eax; Period
0x180021044  mov     dword ptr [rsp+48h+phkResult], eax; DueTime
0x180021048  call    cs:__imp_CreateTimerQueueTimer
0x18002104f  nop     dword ptr [rax+rax+00h]
0x180021054  xor     ecx, ecx
0x180021056  test    eax, eax
0x180021058  setnz   cl
0x18002105b  mov     eax, ecx
0x18002105d  jmp     short loc_180021064
0x18002105f  mov     eax, 1
0x180021064  add     rsp, 40h
0x180021068  pop     rbx
0x180021069  retn
```
