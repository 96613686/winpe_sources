# SafeSchedCancel

- ea: `0x14001a50c`
- end: `0x14001a55d`
- name: `SafeSchedCancel`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400199e0`
- `0x140019dd0`
- `0x140019e5c`

## callees

- `0x14001a50c`
- `0x140020894`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001a53d`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001a53d`

## pseudocode

```c
__int64 __fastcall SafeSchedCancel(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  result = CScheduler::SchedCancel(*(CScheduler **)(*(_QWORD *)(a1 + 64) + 360LL), a2);
  if ( !(_DWORD)result )
  {
    while ( 1 )
    {
      result = a2[36] >> 4;
      if ( (a2[36] & 0x10) != 0 )
        break;
      Interval.QuadPart = -10000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001a50c  push    rbx
0x14001a50e  sub     rsp, 20h
0x14001a512  mov     rcx, [rcx+40h]
0x14001a516  mov     rbx, rdx
0x14001a519  mov     rcx, [rcx+168h]; this
0x14001a520  call    ?SchedCancel@CScheduler@@QEAAHPEAX@Z; CScheduler::SchedCancel(void *)
0x14001a525  test    eax, eax
0x14001a527  jnz     short loc_14001A556
0x14001a529  jmp     short loc_14001A549
0x14001a52b  lea     r8, [rsp+28h+Interval]; Interval
0x14001a530  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFD8F0h
0x14001a539  xor     edx, edx; Alertable
0x14001a53b  xor     ecx, ecx; WaitMode
0x14001a53d  call    cs:__imp_KeDelayExecutionThread
0x14001a544  nop     dword ptr [rax+rax+00h]
0x14001a549  mov     eax, [rbx+90h]
0x14001a54f  shr     eax, 4
0x14001a552  test    al, 1
0x14001a554  jz      short loc_14001A52B
0x14001a556  add     rsp, 20h
0x14001a55a  pop     rbx
0x14001a55b  retn
```
