# AcquireWriteLock

- ea: `0x180001de8`
- end: `0x180001e38`
- name: `AcquireWriteLock`
- size: `80`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d2c`
- `0x180001e40`
- `0x180001fe4`
- `0x1800021ac`

## callees

- `0x180001de8`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180001e09`
- `KERNEL32!WaitForSingleObject` at `0x180001e09`
- `KERNEL32!LeaveCriticalSection` at `0x180001df6`
- `KERNEL32!LeaveCriticalSection` at `0x180001df6`
- `KERNEL32!EnterCriticalSection` at `0x180001e18`
- `KERNEL32!EnterCriticalSection` at `0x180001e18`

## pseudocode

```c
void __fastcall AcquireWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  LPCRITICAL_SECTION i; // rbx

  for ( i = lpCriticalSection; ; lpCriticalSection = i )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( !i[1].LockCount )
      break;
    LeaveCriticalSection(i);
    WaitForSingleObject(i[1].DebugInfo, 0xFFFFFFFF);
  }
  i[1].LockCount = 1;
}

```

## disassembly

```asm
0x180001de8  push    rbx
0x180001dea  sub     rsp, 20h
0x180001dee  mov     rbx, rcx
0x180001df1  jmp     short loc_180001E18
0x180001df3  mov     rcx, rbx; lpCriticalSection
0x180001df6  call    cs:__imp_LeaveCriticalSection
0x180001dfd  nop     dword ptr [rax+rax+00h]
0x180001e02  mov     rcx, [rbx+28h]; hHandle
0x180001e06  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180001e09  call    cs:__imp_WaitForSingleObject
0x180001e10  nop     dword ptr [rax+rax+00h]
0x180001e15  mov     rcx, rbx; lpCriticalSection
0x180001e18  call    cs:__imp_EnterCriticalSection
0x180001e1f  nop     dword ptr [rax+rax+00h]
0x180001e24  cmp     dword ptr [rbx+30h], 0
0x180001e28  ja      short loc_180001DF3
0x180001e2a  mov     dword ptr [rbx+30h], 1
0x180001e31  add     rsp, 20h
0x180001e35  pop     rbx
0x180001e36  retn
```
