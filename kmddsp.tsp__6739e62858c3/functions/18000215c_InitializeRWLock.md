# InitializeRWLock

- ea: `0x18000215c`
- end: `0x1800021a6`
- name: `InitializeRWLock`
- size: `74`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002080`
- `0x1800021ac`

## callees

- `0x18000215c`

## import_xrefs

- `KERNEL32!CreateEventA` at `0x18000216f`
- `KERNEL32!CreateEventA` at `0x18000216f`
- `KERNEL32!InitializeCriticalSection` at `0x180002187`
- `KERNEL32!InitializeCriticalSection` at `0x180002187`

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
0x18000215c  push    rbx
0x18000215e  sub     rsp, 20h
0x180002162  mov     rbx, rcx
0x180002165  xor     r9d, r9d; lpName
0x180002168  xor     ecx, ecx; lpEventAttributes
0x18000216a  xor     r8d, r8d; bInitialState
0x18000216d  xor     edx, edx; bManualReset
0x18000216f  call    cs:__imp_CreateEventA
0x180002176  nop     dword ptr [rax+rax+00h]
0x18000217b  mov     [rbx+28h], rax
0x18000217f  test    rax, rax
0x180002182  jz      short loc_18000219F
0x180002184  mov     rcx, rbx; lpCriticalSection
0x180002187  call    cs:__imp_InitializeCriticalSection
0x18000218e  nop     dword ptr [rax+rax+00h]
0x180002193  mov     eax, 1
0x180002198  mov     dword ptr [rbx+30h], 0
0x18000219f  add     rsp, 20h
0x1800021a3  pop     rbx
0x1800021a4  retn
```
