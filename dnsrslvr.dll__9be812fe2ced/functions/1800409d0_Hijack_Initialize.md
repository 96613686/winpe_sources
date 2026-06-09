# Hijack_Initialize

- ea: `0x1800409d0`
- end: `0x180040a5a`
- name: `Hijack_Initialize`
- size: `138`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800495c0`

## callees

- `0x18003fe3c`
- `0x1800409d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040a0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800409fc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800409fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040a4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040a4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409e5`

## pseudocode

```c
__int64 Hijack_Initialize()
{
  DWORD LastError; // ebx

  LastError = 0;
  g_HijackSystemState = 0;
  EnterCriticalSection(&g_HijackCS);
  g_HijackNumPendingProbes = 0;
  g_HijackPendingProbeCompleteEvent = CreateEventW(0, 1, 1, 0);
  if ( g_HijackPendingProbeCompleteEvent )
  {
    qword_1800AC698 = (__int64)&g_HijackList;
    g_HijackList = &g_HijackList;
    hijackStoreLoad();
    if ( g_HijackSystemState < 1 )
      g_HijackSystemState = 1;
  }
  else
  {
    LastError = GetLastError();
  }
  LeaveCriticalSection(&g_HijackCS);
  return LastError;
}

```

## disassembly

```asm
0x1800409d0  push    rbx
0x1800409d2  sub     rsp, 20h
0x1800409d6  xor     ebx, ebx
0x1800409d8  lea     rcx, g_HijackCS; lpCriticalSection
0x1800409df  mov     cs:g_HijackSystemState, ebx
0x1800409e5  call    cs:__imp_EnterCriticalSection
0x1800409eb  lea     edx, [rbx+1]; bManualReset
0x1800409ee  mov     cs:g_HijackNumPendingProbes, ebx
0x1800409f4  mov     r8d, edx; bInitialState
0x1800409f7  xor     r9d, r9d; lpName
0x1800409fa  xor     ecx, ecx; lpEventAttributes
0x1800409fc  call    cs:__imp_CreateEventW
0x180040a02  mov     cs:g_HijackPendingProbeCompleteEvent, rax
0x180040a09  test    rax, rax
0x180040a0c  jnz     short loc_180040A18
0x180040a0e  call    cs:__imp_GetLastError
0x180040a14  mov     ebx, eax
0x180040a16  jmp     short loc_180040A45
0x180040a18  lea     rax, g_HijackList
0x180040a1f  mov     cs:qword_1800AC698, rax
0x180040a26  mov     cs:g_HijackList, rax
0x180040a2d  call    hijackStoreLoad
0x180040a32  cmp     cs:g_HijackSystemState, 1
0x180040a39  jge     short loc_180040A45
0x180040a3b  mov     cs:g_HijackSystemState, 1
0x180040a45  lea     rcx, g_HijackCS; lpCriticalSection
0x180040a4c  call    cs:__imp_LeaveCriticalSection
0x180040a52  mov     eax, ebx
0x180040a54  add     rsp, 20h
0x180040a58  pop     rbx
0x180040a59  retn
```
