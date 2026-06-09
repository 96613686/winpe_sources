# _Cnd_timedwait_for_impl

- ea: `0x180002a9c`
- end: `0x180002b1c`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b24`

## callees

- `0x180002a9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002abe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002aee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002abe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180002aee`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002adf`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002adf`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // edi
  ULONGLONG v5; // r14
  ULONGLONG TickCount64; // rsi
  DWORD CurrentThreadId; // eax

  v4 = 0;
  v5 = a3;
  TickCount64 = 0;
  if ( a4 )
    TickCount64 = GetTickCount64();
  --*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = -1;
  if ( !SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(a2 + 16), v5, 0) && (!a4 || GetTickCount64() - TickCount64 >= v5) )
    v4 = 2;
  CurrentThreadId = GetCurrentThreadId();
  ++*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = CurrentThreadId;
  return v4;
}

```

## disassembly

```asm
0x180002a9c  push    rbx
0x180002a9e  push    rbp
0x180002a9f  push    rsi
0x180002aa0  push    rdi
0x180002aa1  push    r14
0x180002aa3  push    r15
0x180002aa5  sub     rsp, 28h
0x180002aa9  xor     edi, edi
0x180002aab  mov     r14d, r8d
0x180002aae  xor     esi, esi
0x180002ab0  mov     bpl, r9b
0x180002ab3  mov     rbx, rdx
0x180002ab6  mov     r15, rcx
0x180002ab9  test    r9b, r9b
0x180002abc  jz      short loc_180002AC7
0x180002abe  call    cs:__imp_GetTickCount64
0x180002ac4  mov     rsi, rax
0x180002ac7  dec     dword ptr [rbx+4Ch]
0x180002aca  lea     rdx, [rbx+10h]; SRWLock
0x180002ace  lea     rcx, [r15+8]; ConditionVariable
0x180002ad2  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180002ad9  xor     r9d, r9d; Flags
0x180002adc  mov     r8d, r14d; dwMilliseconds
0x180002adf  call    cs:__imp_SleepConditionVariableSRW
0x180002ae5  test    eax, eax
0x180002ae7  jnz     short loc_180002B01
0x180002ae9  test    bpl, bpl
0x180002aec  jz      short loc_180002AFC
0x180002aee  call    cs:__imp_GetTickCount64
0x180002af4  sub     rax, rsi
0x180002af7  cmp     rax, r14
0x180002afa  jb      short loc_180002B01
0x180002afc  mov     edi, 2
0x180002b01  call    cs:__imp_GetCurrentThreadId
0x180002b07  inc     dword ptr [rbx+4Ch]
0x180002b0a  mov     [rbx+48h], eax
0x180002b0d  mov     eax, edi
0x180002b0f  add     rsp, 28h
0x180002b13  pop     r15
0x180002b15  pop     r14
0x180002b17  pop     rdi
0x180002b18  pop     rsi
0x180002b19  pop     rbp
0x180002b1a  pop     rbx
0x180002b1b  retn
```
