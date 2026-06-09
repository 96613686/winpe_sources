# InitializeRWLock

- ea: `0x1800902f4`
- end: `0x18009033b`
- name: `InitializeRWLock`
- size: `71`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18009018c`
- `0x180090344`

## callees

- `0x1800902f4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18009031f`
- `KERNEL32!InitializeCriticalSection` at `0x18009031f`
- `KERNEL32!CreateEventA` at `0x180090307`
- `KERNEL32!CreateEventA` at `0x180090307`

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
    lpCriticalSection[1].LockCount = 0;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800902f4  push    rbx
0x1800902f6  sub     rsp, 20h
0x1800902fa  mov     rbx, rcx
0x1800902fd  xor     r9d, r9d; lpName
0x180090300  xor     ecx, ecx; lpEventAttributes
0x180090302  xor     r8d, r8d; bInitialState
0x180090305  xor     edx, edx; bManualReset
0x180090307  call    cs:__imp_CreateEventA
0x18009030e  nop     dword ptr [rax+rax+00h]
0x180090313  mov     [rbx+28h], rax
0x180090317  test    rax, rax
0x18009031a  jz      short loc_180090334
0x18009031c  mov     rcx, rbx; lpCriticalSection
0x18009031f  call    cs:__imp_InitializeCriticalSection
0x180090326  nop     dword ptr [rax+rax+00h]
0x18009032b  and     dword ptr [rbx+30h], 0
0x18009032f  mov     eax, 1
0x180090334  add     rsp, 20h
0x180090338  pop     rbx
0x180090339  retn
```
