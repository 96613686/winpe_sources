# RasmanServiceNotify

- ea: `0x1800149c0`
- end: `0x180014a37`
- name: `RasmanServiceNotify`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800149c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a30`

## pseudocode

```c
void __fastcall RasmanServiceNotify(__int64 a1)
{
  int v1; // ecx
  int v2; // ecx

  if ( !*(_DWORD *)(a1 + 24) )
  {
    v1 = *(_DWORD *)(a1 + 64) - 1;
    if ( v1 && (v2 = v1 - 3) != 0 )
    {
      if ( v2 != 4 )
        return;
      EnterCriticalSection(&g_RasCriticalSection);
      g_fRasmanStarted = 1;
    }
    else
    {
      EnterCriticalSection(&g_RasCriticalSection);
      g_fRasmanStarted = 0;
      g_fRCNInitialized = 0;
      g_fRasReferenced = 0;
    }
    LeaveCriticalSection(&g_RasCriticalSection);
  }
}

```

## disassembly

```asm
0x1800149c0  sub     rsp, 28h
0x1800149c4  cmp     dword ptr [rcx+18h], 0
0x1800149c8  jz      short loc_1800149CF
0x1800149ca  add     rsp, 28h
0x1800149ce  retn
0x1800149cf  mov     ecx, [rcx+40h]
0x1800149d2  sub     ecx, 1
0x1800149d5  jz      short loc_1800149FA
0x1800149d7  sub     ecx, 3
0x1800149da  jz      short loc_1800149FA
0x1800149dc  cmp     ecx, 4
0x1800149df  jnz     short loc_1800149CA
0x1800149e1  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800149e8  call    cs:__imp_EnterCriticalSection
0x1800149ee  mov     cs:g_fRasmanStarted, 1
0x1800149f8  jmp     short loc_180014A25
0x1800149fa  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180014a01  call    cs:__imp_EnterCriticalSection
0x180014a07  mov     cs:g_fRasmanStarted, 0
0x180014a11  mov     cs:g_fRCNInitialized, 0
0x180014a1b  mov     cs:g_fRasReferenced, 0
0x180014a25  lea     rcx, g_RasCriticalSection
0x180014a2c  add     rsp, 28h
0x180014a30  jmp     cs:__imp_LeaveCriticalSection
```
