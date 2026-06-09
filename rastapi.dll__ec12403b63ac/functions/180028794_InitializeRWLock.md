# InitializeRWLock

- ea: `0x180028794`
- end: `0x1800287d1`
- name: `InitializeRWLock`
- size: `61`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180028648`
- `0x1800287d8`

## callees

- `0x180028794`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800287b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800287b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800287a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800287a7`

## pseudocode

```c
__int64 __fastcall InitializeRWLock(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 result; // rax

  result = (__int64)CreateEventA(0, 0, 0, 0);
  lpCriticalSection[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)result;
  if ( result )
  {
    InitializeCriticalSection(lpCriticalSection);
    result = 1;
    lpCriticalSection[1].LockCount = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180028794  push    rbx
0x180028796  sub     rsp, 20h
0x18002879a  mov     rbx, rcx
0x18002879d  xor     r9d, r9d; lpName
0x1800287a0  xor     ecx, ecx; lpEventAttributes
0x1800287a2  xor     r8d, r8d; bInitialState
0x1800287a5  xor     edx, edx; bManualReset
0x1800287a7  call    cs:__imp_CreateEventA
0x1800287ad  mov     [rbx+28h], rax
0x1800287b1  test    rax, rax
0x1800287b4  jz      short loc_1800287CB
0x1800287b6  mov     rcx, rbx; lpCriticalSection
0x1800287b9  call    cs:__imp_InitializeCriticalSection
0x1800287bf  mov     eax, 1
0x1800287c4  mov     dword ptr [rbx+30h], 0
0x1800287cb  add     rsp, 20h
0x1800287cf  pop     rbx
0x1800287d0  retn
```
