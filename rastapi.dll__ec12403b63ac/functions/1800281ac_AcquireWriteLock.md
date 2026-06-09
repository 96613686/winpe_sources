# AcquireWriteLock

- ea: `0x1800281ac`
- end: `0x1800281e9`
- name: `AcquireWriteLock`
- size: `61`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180028078`
- `0x1800281f0`
- `0x1800284fc`
- `0x1800287d8`

## callees

- `0x1800281ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800281ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800281d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800281d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800281c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800281c7`

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
0x1800281ac  push    rbx
0x1800281ae  sub     rsp, 20h
0x1800281b2  mov     rbx, rcx
0x1800281b5  jmp     short loc_1800281D0
0x1800281b7  mov     rcx, rbx; lpCriticalSection
0x1800281ba  call    cs:__imp_LeaveCriticalSection
0x1800281c0  mov     rcx, [rbx+28h]; hHandle
0x1800281c4  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800281c7  call    cs:__imp_WaitForSingleObject
0x1800281cd  mov     rcx, rbx; lpCriticalSection
0x1800281d0  call    cs:__imp_EnterCriticalSection
0x1800281d6  cmp     dword ptr [rbx+30h], 0
0x1800281da  ja      short loc_1800281B7
0x1800281dc  mov     dword ptr [rbx+30h], 1
0x1800281e3  add     rsp, 20h
0x1800281e7  pop     rbx
0x1800281e8  retn
```
