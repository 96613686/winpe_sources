# ALLOC_CACHE_HANDLER::SetLookasideCleanupInterval(void)

- ea: `0x18001fc60`
- end: `0x18001fd24`
- name: `?SetLookasideCleanupInterval@ALLOC_CACHE_HANDLER@@SAHXZ`
- size: `196`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18001ea00`

## callees

- `0x18001f9e8`
- `0x18001fc60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001fc90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001fc90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcd5`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x18001fd08`
- `api-ms-win-core-threadpool-l1-1-0!CreateTimerQueueTimer` at `0x18001fd08`

## string_xrefs

- `0x18001fc9f`: `LookasideCleanupInterval`
- `0x18001fcb6`: `AcacheHonorPageheap`
- `0x18001fc82`: `System\CurrentControlSet\Services\InetInfo\Parameters`

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
0x18001fc60  push    rbx
0x18001fc62  sub     rsp, 40h
0x18001fc66  lea     rax, [rsp+48h+hKey]
0x18001fc6b  mov     [rsp+48h+hKey], 0
0x18001fc74  mov     r9d, 20019h; samDesired
0x18001fc7a  mov     [rsp+48h+phkResult], rax; phkResult
0x18001fc7f  xor     r8d, r8d; ulOptions
0x18001fc82  lea     rdx, ?g_PSZ_ACACHE_CONFIG_PARAMS_REG_KEY@@3PADA; "System\\CurrentControlSet\\Services\\In"...
0x18001fc89  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001fc90  call    cs:__imp_RegOpenKeyExA
0x18001fc96  test    eax, eax
0x18001fc98  jnz     short loc_18001FD19
0x18001fc9a  mov     rcx, [rsp+48h+hKey]
0x18001fc9f  lea     rdx, aLookasideclean; "LookasideCleanupInterval"
0x18001fca6  mov     r8d, 384h
0x18001fcac  call    I_AtqReadRegDword
0x18001fcb1  mov     rcx, [rsp+48h+hKey]
0x18001fcb6  lea     rdx, aAcachehonorpag; "AcacheHonorPageheap"
0x18001fcbd  mov     r8d, 1
0x18001fcc3  mov     ebx, eax
0x18001fcc5  call    I_AtqReadRegDword
0x18001fcca  mov     rcx, [rsp+48h+hKey]; hKey
0x18001fccf  mov     cs:?sm_fHonorPageHeap@ALLOC_CACHE_HANDLER@@0HA, eax; int ALLOC_CACHE_HANDLER::sm_fHonorPageHeap
0x18001fcd5  call    cs:__imp_RegCloseKey
0x18001fcdb  test    ebx, ebx
0x18001fcdd  jz      short loc_18001FD19
0x18001fcdf  imul    eax, ebx, 3E8h
0x18001fce5  lea     r8, ?CleanupAllLookasides@ALLOC_CACHE_HANDLER@@SAXPEAXE@Z; Callback
0x18001fcec  mov     [rsp+48h+Flags], 10h; Flags
0x18001fcf4  lea     rcx, ?sm_hTimer@ALLOC_CACHE_HANDLER@@0PEAXEA; phNewTimer
0x18001fcfb  xor     r9d, r9d; Parameter
0x18001fcfe  xor     edx, edx; TimerQueue
0x18001fd00  mov     [rsp+48h+Period], eax; Period
0x18001fd04  mov     dword ptr [rsp+48h+phkResult], eax; DueTime
0x18001fd08  call    cs:__imp_CreateTimerQueueTimer
0x18001fd0e  xor     ecx, ecx
0x18001fd10  test    eax, eax
0x18001fd12  setnz   cl
0x18001fd15  mov     eax, ecx
0x18001fd17  jmp     short loc_18001FD1E
0x18001fd19  mov     eax, 1
0x18001fd1e  add     rsp, 40h
0x18001fd22  pop     rbx
0x18001fd23  retn
```
