# StartTracking(ulong)

- ea: `0x1400565a0`
- end: `0x14005667d`
- name: `?StartTracking@@YA_NK@Z`
- size: `221`
- prototype: `bool __fastcall(DWORD Period)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140056080`

## callees

- `0x140007ce0`
- `0x1400086f8`
- `0x1400565a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140056644`
- `KERNEL32!GetLastError` at `0x140056644`
- `KERNEL32!CreateTimerQueueTimer` at `0x140056621`
- `KERNEL32!CreateTimerQueueTimer` at `0x140056621`

## pseudocode

```c
bool __fastcall StartTracking(DWORD Period)
{
  DWORD LastError; // eax
  bool result; // al

  if ( dword_140081218 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dad65cf913563a822a96282680d83d20_Traceguids);
    return 0;
  }
  if ( Period < 0x2710 )
    Period = dword_1400809B8;
  else
    dword_1400809B8 = Period;
  if ( !CreateTimerQueueTimer(&phNewTimer, 0, ModuleTrackingTimerRoutine, 0, Period, Period, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dad65cf913563a822a96282680d83d20_Traceguids, LastError);
    }
    return 0;
  }
  result = 1;
  dword_140081218 = 1;
  return result;
}

```

## disassembly

```asm
0x1400565a0  sub     rsp, 48h
0x1400565a4  cmp     cs:dword_140081218, 0
0x1400565ab  jz      short loc_1400565E8
0x1400565ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400565b4  lea     rax, WPP_GLOBAL_Control
0x1400565bb  cmp     rcx, rax
0x1400565be  jz      loc_140056669
0x1400565c4  test    byte ptr [rcx+1Ch], 2
0x1400565c8  jz      loc_140056669
0x1400565ce  mov     rcx, [rcx+10h]
0x1400565d2  lea     r8, WPP_dad65cf913563a822a96282680d83d20_Traceguids
0x1400565d9  mov     edx, 0Ah
0x1400565de  call    WPP_SF_
0x1400565e3  jmp     loc_140056669
0x1400565e8  cmp     ecx, 2710h
0x1400565ee  jb      short loc_1400565F8
0x1400565f0  mov     cs:dword_1400809B8, ecx
0x1400565f6  jmp     short loc_1400565FE
0x1400565f8  mov     ecx, cs:dword_1400809B8
0x1400565fe  mov     [rsp+48h+Flags], 0; Flags
0x140056606  lea     r8, ?ModuleTrackingTimerRoutine@@YAXPEAXH@Z; Callback
0x14005660d  mov     [rsp+48h+Period], ecx; Period
0x140056611  xor     r9d, r9d; Parameter
0x140056614  mov     [rsp+48h+DueTime], ecx; DueTime
0x140056618  xor     edx, edx; TimerQueue
0x14005661a  lea     rcx, phNewTimer; phNewTimer
0x140056621  call    cs:__imp_CreateTimerQueueTimer
0x140056627  test    eax, eax
0x140056629  jnz     short loc_14005666D
0x14005662b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056632  lea     rax, WPP_GLOBAL_Control
0x140056639  cmp     rcx, rax
0x14005663c  jz      short loc_140056669
0x14005663e  test    byte ptr [rcx+1Ch], 2
0x140056642  jz      short loc_140056669
0x140056644  call    cs:__imp_GetLastError
0x14005664a  mov     rcx, cs:WPP_GLOBAL_Control
0x140056651  lea     r8, WPP_dad65cf913563a822a96282680d83d20_Traceguids
0x140056658  mov     edx, 0Bh
0x14005665d  mov     r9d, eax
0x140056660  mov     rcx, [rcx+10h]
0x140056664  call    WPP_SF_d
0x140056669  xor     al, al
0x14005666b  jmp     short loc_140056678
0x14005666d  mov     eax, 1
0x140056672  mov     cs:dword_140081218, eax
0x140056678  add     rsp, 48h
0x14005667c  retn
```
