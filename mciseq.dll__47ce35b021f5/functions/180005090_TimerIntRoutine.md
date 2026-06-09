# TimerIntRoutine

- ea: `0x180005090`
- end: `0x180005267`
- name: `TimerIntRoutine`
- size: `471`
- prototype: `__int64 __fastcall(DWORD_PTR dwUser)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005cb0`

## callees

- `0x1800033d8`
- `0x1800048fc`
- `0x180004ff8`
- `0x180005090`
- `0x180007010`

## import_xrefs

- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800050c8`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180005126`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800050c8`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180005126`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180005116`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180005116`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000524f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000524f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800050ab`
- `WINMM!midiOutLongMsg` at `0x18000522f`
- `WINMM!midiOutLongMsg` at `0x18000522f`
- `WINMM!timeSetEvent` at `0x18000515c`
- `WINMM!timeSetEvent` at `0x18000515c`

## pseudocode

```c
__int64 __fastcall TimerIntRoutine(DWORD_PTR dwUser, int a2)
{
  signed int v4; // edi
  int v5; // eax
  int v6; // eax
  int v7; // edi
  DWORD Time; // eax
  UINT v9; // edx
  MMRESULT v10; // eax
  int v11; // eax
  __int64 v12; // r8
  void (__fastcall *v13)(_QWORD, __int64, _QWORD); // rax
  unsigned int v14; // ebx
  __int64 v15; // r8
  void (__fastcall *v16)(_QWORD, __int64, _QWORD); // rax

  EnterCriticalSection(&CritSec);
  if ( !*(_DWORD *)(dwUser + 968) )
  {
    *(_DWORD *)(dwUser + 968) = 1;
    v4 = *(_DWORD *)(dwUser + 28) - timeGetTime();
    if ( *(_DWORD *)(dwUser + 8) )
    {
      while ( 1 )
      {
        v5 = SendAllEventsB4(dwUser, a2, (unsigned int)(v4 <= -100) + 2);
        if ( v5 != 256 )
          break;
        a2 = *(_DWORD *)(*(_QWORD *)(dwUser + 80) + 4LL);
        if ( a2 )
          v6 = MulDiv(a2, *(_DWORD *)(dwUser + 40), 1000);
        else
          v6 = 0;
        *(_DWORD *)(dwUser + 28) += v6;
        v7 = *(_DWORD *)(dwUser + 28);
        Time = timeGetTime();
        v9 = MINPERIOD;
        v4 = v7 - Time;
        if ( v4 <= (int)MINPERIOD )
        {
          v11 = 1;
        }
        else
        {
          *(_DWORD *)(dwUser + 968) = 0;
          *(_DWORD *)(dwUser + 156) = a2;
          v10 = timeSetEvent(v4, v9, OneShotTimer, dwUser, 0x100u);
          *(_DWORD *)(dwUser + 160) = v10;
          if ( !v10 )
          {
            Stop(dwUser);
            v12 = *(_QWORD *)(dwUser + 88);
            v13 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(v12 + 64);
            if ( v13 )
              v13(0, 2, *(_QWORD *)(v12 + 72));
            v14 = 107;
            goto LABEL_25;
          }
          v11 = 0;
        }
        if ( !v11 )
          goto LABEL_21;
      }
      if ( ((v5 - 258) & 0xFFFFFFFD) == 0 )
      {
        if ( *(_DWORD *)(dwUser + 184) == 3 )
          Notify(*(_QWORD *)(dwUser + 176), 1);
        Stop(dwUser);
        v15 = *(_QWORD *)(dwUser + 88);
        v16 = *(void (__fastcall **)(_QWORD, __int64, _QWORD))(v15 + 64);
        if ( v16 )
          v16(0, 2, *(_QWORD *)(v15 + 72));
      }
    }
LABEL_21:
    if ( *(_DWORD *)(dwUser + 1732) )
    {
      midiOutLongMsg(*(HMIDIOUT *)(dwUser + 168), (LPMIDIHDR)(dwUser + 1724), 0x70u);
      *(_DWORD *)(dwUser + 1732) = 0;
    }
    *(_DWORD *)(dwUser + 968) = 0;
  }
  v14 = 0;
LABEL_25:
  LeaveCriticalSection(&CritSec);
  return v14;
}

```

## disassembly

```asm
0x180005090  mov     [rsp+arg_0], rbx
0x180005095  mov     [rsp+arg_8], rsi
0x18000509a  push    rdi
0x18000509b  sub     rsp, 30h
0x18000509f  mov     rbx, rcx
0x1800050a2  mov     esi, edx
0x1800050a4  lea     rcx, CritSec; lpCriticalSection
0x1800050ab  call    cs:__imp_EnterCriticalSection
0x1800050b1  cmp     dword ptr [rbx+3C8h], 0
0x1800050b8  jnz     loc_180005246
0x1800050be  mov     dword ptr [rbx+3C8h], 1
0x1800050c8  call    cs:__imp_timeGetTime
0x1800050ce  mov     edi, [rbx+1Ch]
0x1800050d1  sub     edi, eax
0x1800050d3  cmp     dword ptr [rbx+8], 0
0x1800050d7  jz      loc_180005212
0x1800050dd  xor     r8d, r8d
0x1800050e0  mov     edx, esi
0x1800050e2  cmp     edi, 0FFFFFF9Ch
0x1800050e5  mov     rcx, rbx
0x1800050e8  setle   r8b
0x1800050ec  add     r8d, 2
0x1800050f0  call    SendAllEventsB4
0x1800050f5  cmp     eax, 100h
0x1800050fa  jnz     loc_1800051BC
0x180005100  mov     rax, [rbx+50h]
0x180005104  mov     esi, [rax+4]
0x180005107  test    esi, esi
0x180005109  jz      short loc_18000511E
0x18000510b  mov     edx, [rbx+28h]; nNumerator
0x18000510e  mov     r8d, 3E8h; nDenominator
0x180005114  mov     ecx, esi; nNumber
0x180005116  call    cs:__imp_MulDiv
0x18000511c  jmp     short loc_180005120
0x18000511e  xor     eax, eax
0x180005120  add     [rbx+1Ch], eax
0x180005123  mov     edi, [rbx+1Ch]
0x180005126  call    cs:__imp_timeGetTime
0x18000512c  mov     edx, cs:MINPERIOD; uResolution
0x180005132  sub     edi, eax
0x180005134  cmp     edi, edx
0x180005136  jle     short loc_180005170
0x180005138  mov     r9, rbx; dwUser
0x18000513b  mov     dword ptr [rbx+3C8h], 0
0x180005145  lea     r8, OneShotTimer; fptc
0x18000514c  mov     [rbx+9Ch], esi
0x180005152  mov     ecx, edi; uDelay
0x180005154  mov     [rsp+38h+fuEvent], 100h; fuEvent
0x18000515c  call    cs:__imp_timeSetEvent
0x180005162  mov     [rbx+0A0h], eax
0x180005168  test    eax, eax
0x18000516a  jz      short loc_180005182
0x18000516c  xor     eax, eax
0x18000516e  jmp     short loc_180005175
0x180005170  mov     eax, 1
0x180005175  test    eax, eax
0x180005177  jnz     loc_1800050DD
0x18000517d  jmp     loc_180005212
0x180005182  mov     rcx, rbx
0x180005185  call    Stop
0x18000518a  mov     r8, [rbx+58h]
0x18000518e  mov     rax, [r8+40h]
0x180005192  test    rax, rax
0x180005195  jz      short loc_1800051B2
0x180005197  mov     r8, [r8+48h]
0x18000519b  xor     r9d, r9d
0x18000519e  xor     ecx, ecx
0x1800051a0  mov     qword ptr [rsp+38h+fuEvent], 0
0x1800051a9  lea     edx, [r9+2]
0x1800051ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b2  mov     ebx, 6Bh ; 'k'
0x1800051b7  jmp     loc_180005248
0x1800051bc  add     eax, 0FFFFFEFEh
0x1800051c1  test    eax, 0FFFFFFFDh
0x1800051c6  jnz     short loc_180005212
0x1800051c8  cmp     dword ptr [rbx+0B8h], 3
0x1800051cf  jnz     short loc_1800051E2
0x1800051d1  mov     rcx, [rbx+0B0h]
0x1800051d8  mov     edx, 1
0x1800051dd  call    Notify
0x1800051e2  mov     rcx, rbx
0x1800051e5  call    Stop
0x1800051ea  mov     r8, [rbx+58h]
0x1800051ee  mov     rax, [r8+40h]
0x1800051f2  test    rax, rax
0x1800051f5  jz      short loc_180005212
0x1800051f7  mov     r8, [r8+48h]
0x1800051fb  xor     r9d, r9d
0x1800051fe  xor     ecx, ecx
0x180005200  mov     qword ptr [rsp+38h+fuEvent], 0
0x180005209  lea     edx, [r9+2]
0x18000520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005212  lea     rdi, [rbx+6BCh]
0x180005219  cmp     dword ptr [rdi+8], 0
0x18000521d  jz      short loc_18000523C
0x18000521f  mov     rcx, [rbx+0A8h]; hmo
0x180005226  mov     r8d, 70h ; 'p'; cbmh
0x18000522c  mov     rdx, rdi; pmh
0x18000522f  call    cs:__imp_midiOutLongMsg
0x180005235  mov     dword ptr [rdi+8], 0
0x18000523c  mov     dword ptr [rbx+3C8h], 0
0x180005246  xor     ebx, ebx
0x180005248  lea     rcx, CritSec; lpCriticalSection
0x18000524f  call    cs:__imp_LeaveCriticalSection
0x180005255  mov     rsi, [rsp+38h+arg_8]
0x18000525a  mov     eax, ebx
0x18000525c  mov     rbx, [rsp+38h+arg_0]
0x180005261  add     rsp, 30h
0x180005265  pop     rdi
0x180005266  retn
```
