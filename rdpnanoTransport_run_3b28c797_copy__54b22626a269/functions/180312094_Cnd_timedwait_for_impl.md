# _Cnd_timedwait_for_impl

- ea: `0x180312094`
- end: `0x18031212b`
- name: `_Cnd_timedwait_for_impl`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18031212c`

## callees

- `0x180312094`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180312104`
- `KERNEL32!GetCurrentThreadId` at `0x180312104`
- `KERNEL32!GetTickCount64` at `0x1803120c1`
- `KERNEL32!GetTickCount64` at `0x1803120f1`
- `KERNEL32!GetTickCount64` at `0x1803120c1`
- `KERNEL32!GetTickCount64` at `0x1803120f1`
- `KERNEL32!SleepConditionVariableSRW` at `0x1803120e2`
- `KERNEL32!SleepConditionVariableSRW` at `0x1803120e2`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // ebx
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
0x180312094  mov     [rsp+arg_0], rbx
0x180312099  mov     [rsp+arg_8], rbp
0x18031209e  mov     [rsp+arg_10], rsi
0x1803120a3  push    rdi
0x1803120a4  push    r14
0x1803120a6  push    r15
0x1803120a8  sub     rsp, 20h
0x1803120ac  xor     ebx, ebx
0x1803120ae  mov     r14d, r8d
0x1803120b1  mov     bpl, r9b
0x1803120b4  mov     rdi, rdx
0x1803120b7  mov     r15, rcx
0x1803120ba  mov     esi, ebx
0x1803120bc  test    r9b, r9b
0x1803120bf  jz      short loc_1803120CA
0x1803120c1  call    cs:__imp_GetTickCount64
0x1803120c7  mov     rsi, rax
0x1803120ca  dec     dword ptr [rdi+4Ch]
0x1803120cd  lea     rdx, [rdi+10h]; SRWLock
0x1803120d1  lea     rcx, [r15+8]; ConditionVariable
0x1803120d5  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1803120dc  xor     r9d, r9d; Flags
0x1803120df  mov     r8d, r14d; dwMilliseconds
0x1803120e2  call    cs:__imp_SleepConditionVariableSRW
0x1803120e8  test    eax, eax
0x1803120ea  jnz     short loc_180312104
0x1803120ec  test    bpl, bpl
0x1803120ef  jz      short loc_1803120FF
0x1803120f1  call    cs:__imp_GetTickCount64
0x1803120f7  sub     rax, rsi
0x1803120fa  cmp     rax, r14
0x1803120fd  jb      short loc_180312104
0x1803120ff  mov     ebx, 2
0x180312104  call    cs:__imp_GetCurrentThreadId
0x18031210a  inc     dword ptr [rdi+4Ch]
0x18031210d  mov     rbp, [rsp+38h+arg_8]
0x180312112  mov     rsi, [rsp+38h+arg_10]
0x180312117  mov     [rdi+48h], eax
0x18031211a  mov     eax, ebx
0x18031211c  mov     rbx, [rsp+38h+arg_0]
0x180312121  add     rsp, 20h
0x180312125  pop     r15
0x180312127  pop     r14
0x180312129  pop     rdi
0x18031212a  retn
```
