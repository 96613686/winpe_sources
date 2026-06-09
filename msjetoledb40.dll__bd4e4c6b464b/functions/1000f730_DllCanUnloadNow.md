# DllCanUnloadNow()

- ea: `0x1000f730`
- end: `0x1000f775`
- name: `_DllCanUnloadNow@0`
- size: `69`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1000f730`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000f757`
- `KERNEL32!LeaveCriticalSection` at `0x1000f76b`
- `KERNEL32!LeaveCriticalSection` at `0x1000f757`
- `KERNEL32!LeaveCriticalSection` at `0x1000f76b`
- `KERNEL32!EnterCriticalSection` at `0x1000f738`
- `KERNEL32!EnterCriticalSection` at `0x1000f738`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  EnterCriticalSection(&g_CriticalSection);
  if ( g_cObj || g_cLock )
  {
    LeaveCriticalSection(&g_CriticalSection);
    return 1;
  }
  else
  {
    LeaveCriticalSection(&g_CriticalSection);
    return 0;
  }
}

```

## disassembly

```asm
0x1000f730  mov     edi, edi
0x1000f732  push    esi
0x1000f733  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f738  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000f73e  cmp     ?g_cObj@@3JA, 0; long g_cObj
0x1000f745  jnz     short loc_1000F761
0x1000f747  cmp     ?g_cLock@@3JA, 0; long g_cLock
0x1000f74e  jnz     short loc_1000F761
0x1000f750  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f755  xor     esi, esi
0x1000f757  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f75d  mov     eax, esi
0x1000f75f  pop     esi
0x1000f760  retn
0x1000f761  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x1000f766  mov     esi, 1
0x1000f76b  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000f771  mov     eax, esi
0x1000f773  pop     esi
0x1000f774  retn
```
