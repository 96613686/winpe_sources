# SspDeleteChallengeTracking

- ea: `0x18004cd84`
- end: `0x18004cdf8`
- name: `SspDeleteChallengeTracking`
- size: `116`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f990`
- `0x180018308`
- `0x18004a1c0`

## callees

- `0x18004cd84`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTable` at `0x18004cdc7`
- `ntdll!RtlDeleteElementGenericTable` at `0x18004cdc7`
- `ntdll!RtlNumberGenericTableElements` at `0x18004cd94`
- `ntdll!RtlNumberGenericTableElements` at `0x18004cd94`
- `ntdll!RtlEnterCriticalSection` at `0x18004cda5`
- `ntdll!RtlEnterCriticalSection` at `0x18004cda5`
- `ntdll!RtlLeaveCriticalSection` at `0x18004cdec`
- `ntdll!RtlLeaveCriticalSection` at `0x18004cdec`
- `ntdll!RtlGetElementGenericTable` at `0x18004cdda`
- `ntdll!RtlGetElementGenericTable` at `0x18004cdda`

## pseudocode

```c
NTSTATUS __fastcall SspDeleteChallengeTracking(unsigned __int64 a1)
{
  NTSTATUS result; // eax
  _QWORD *ElementGenericTable; // rax

  result = RtlNumberGenericTableElements(&NtLmGlobalActiveChallengeTable);
  if ( result )
  {
    RtlEnterCriticalSection(&NtlmGlobalChallengeTrackingLock);
    do
      ElementGenericTable = RtlGetElementGenericTable(&NtLmGlobalActiveChallengeTable, 0);
    while ( ElementGenericTable
         && a1 > ElementGenericTable[3] + 310000LL
         && RtlDeleteElementGenericTable(&NtLmGlobalActiveChallengeTable, ElementGenericTable) );
    return RtlLeaveCriticalSection(&NtlmGlobalChallengeTrackingLock);
  }
  return result;
}

```

## disassembly

```asm
0x18004cd84  push    rbx
0x18004cd86  sub     rsp, 20h
0x18004cd8a  mov     rbx, rcx
0x18004cd8d  lea     rcx, ?NtLmGlobalActiveChallengeTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18004cd94  call    cs:__imp_RtlNumberGenericTableElements
0x18004cd9a  test    eax, eax
0x18004cd9c  jz      short loc_18004CDF2
0x18004cd9e  lea     rcx, ?NtlmGlobalChallengeTrackingLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18004cda5  call    cs:__imp_RtlEnterCriticalSection
0x18004cdab  jmp     short loc_18004CDD1
0x18004cdad  mov     rcx, [rax+18h]
0x18004cdb1  add     rcx, 4BAF0h
0x18004cdb8  cmp     rbx, rcx
0x18004cdbb  jbe     short loc_18004CDE5
0x18004cdbd  mov     rdx, rax; Buffer
0x18004cdc0  lea     rcx, ?NtLmGlobalActiveChallengeTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18004cdc7  call    cs:__imp_RtlDeleteElementGenericTable
0x18004cdcd  test    al, al
0x18004cdcf  jz      short loc_18004CDE5
0x18004cdd1  xor     edx, edx; I
0x18004cdd3  lea     rcx, ?NtLmGlobalActiveChallengeTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18004cdda  call    cs:__imp_RtlGetElementGenericTable
0x18004cde0  test    rax, rax
0x18004cde3  jnz     short loc_18004CDAD
0x18004cde5  lea     rcx, ?NtlmGlobalChallengeTrackingLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18004cdec  call    cs:__imp_RtlLeaveCriticalSection
0x18004cdf2  add     rsp, 20h
0x18004cdf6  pop     rbx
0x18004cdf7  retn
```
