# DestroyTimer

- ea: `0x18000583c`
- end: `0x1800058b3`
- name: `DestroyTimer`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ff8`
- `0x180005270`
- `0x180005cd0`

## callees

- `0x18000583c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000587e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000587e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005852`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005852`
- `WINMM!timeKillEvent` at `0x180005886`
- `WINMM!timeKillEvent` at `0x180005886`

## pseudocode

```c
void __fastcall DestroyTimer(_DWORD *a1, int a2)
{
  UINT v4; // ebx

  EnterCriticalSection(&CritSec);
  if ( a2 )
    a1[2] = 0;
  v4 = a1[40];
  if ( v4 )
  {
    a1[242] = 1;
    LeaveCriticalSection(&CritSec);
    timeKillEvent(v4);
    a1[242] = 0;
    a1[40] = 0;
  }
  else
  {
    LeaveCriticalSection(&CritSec);
  }
}

```

## disassembly

```asm
0x18000583c  mov     [rsp+arg_0], rbx
0x180005841  push    rdi
0x180005842  sub     rsp, 20h
0x180005846  mov     rdi, rcx
0x180005849  mov     ebx, edx
0x18000584b  lea     rcx, CritSec; lpCriticalSection
0x180005852  call    cs:__imp_EnterCriticalSection
0x180005858  test    ebx, ebx
0x18000585a  jz      short loc_180005863
0x18000585c  mov     dword ptr [rdi+8], 0
0x180005863  mov     ebx, [rdi+0A0h]
0x180005869  lea     rcx, CritSec; lpCriticalSection
0x180005870  test    ebx, ebx
0x180005872  jz      short loc_1800058A2
0x180005874  mov     dword ptr [rdi+3C8h], 1
0x18000587e  call    cs:__imp_LeaveCriticalSection
0x180005884  mov     ecx, ebx; uTimerID
0x180005886  call    cs:__imp_timeKillEvent
0x18000588c  mov     dword ptr [rdi+3C8h], 0
0x180005896  mov     dword ptr [rdi+0A0h], 0
0x1800058a0  jmp     short loc_1800058A8
0x1800058a2  call    cs:__imp_LeaveCriticalSection
0x1800058a8  mov     rbx, [rsp+28h+arg_0]
0x1800058ad  add     rsp, 20h
0x1800058b1  pop     rdi
0x1800058b2  retn
```
