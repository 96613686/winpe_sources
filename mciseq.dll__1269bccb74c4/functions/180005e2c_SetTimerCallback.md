# SetTimerCallback

- ea: `0x180005e2c`
- end: `0x180005e73`
- name: `SetTimerCallback`
- size: `71`
- prototype: `__int64 __fastcall(DWORD_PTR dwUser, UINT uDelay)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180005270`
- `0x180005990`
- `0x180005a1c`
- `0x180005cd0`
- `0x180005d4c`

## import_xrefs

- `WINMM!timeSetEvent` at `0x180005e58`
- `WINMM!timeSetEvent` at `0x180005e58`

## pseudocode

```c
__int64 __fastcall SetTimerCallback(DWORD_PTR dwUser, UINT uDelay, int a3)
{
  MMRESULT v4; // eax

  *(_DWORD *)(dwUser + 156) = a3;
  v4 = timeSetEvent(uDelay, MINPERIOD, OneShotTimer, dwUser, 0x100u);
  *(_DWORD *)(dwUser + 160) = v4;
  return v4 == 0 ? 0x6B : 0;
}

```

## disassembly

```asm
0x180005e2c  push    rbx
0x180005e2e  sub     rsp, 30h
0x180005e32  mov     eax, edx
0x180005e34  mov     [rcx+9Ch], r8d
0x180005e3b  mov     edx, cs:MINPERIOD; uResolution
0x180005e41  lea     r8, OneShotTimer; fptc
0x180005e48  mov     rbx, rcx
0x180005e4b  mov     [rsp+38h+fuEvent], 100h; fuEvent
0x180005e53  mov     r9, rcx; dwUser
0x180005e56  mov     ecx, eax; uDelay
0x180005e58  call    cs:__imp_timeSetEvent
0x180005e5e  mov     [rbx+0A0h], eax
0x180005e64  neg     eax
0x180005e66  sbb     eax, eax
0x180005e68  not     eax
0x180005e6a  and     eax, 6Bh
0x180005e6d  add     rsp, 30h
0x180005e71  pop     rbx
0x180005e72  retn
```
