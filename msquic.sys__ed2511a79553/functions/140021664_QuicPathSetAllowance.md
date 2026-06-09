# QuicPathSetAllowance

- ea: `0x140021664`
- end: `0x1400216c4`
- name: `QuicPathSetAllowance`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140015480`
- `0x14002157c`
- `0x140026f1c`

## callees

- `0x14000d638`
- `0x14000f130`
- `0x140021664`
- `0x1400216cc`
- `0x1400217f0`

## pseudocode

```c
void __fastcall QuicPathSetAllowance(__int64 a1, __int64 a2, unsigned int a3)
{
  bool v3; // zf

  v3 = (*(_BYTE *)(a2 + 1) & 0x20) == 0;
  *(_DWORD *)(a2 + 208) = a3;
  if ( v3 )
  {
    if ( a3 < 0x4C )
    {
      QuicConnAddOutFlowBlockedReason(a1, 4);
    }
    else if ( QuicConnRemoveOutFlowBlockedReason(a1, 4) )
    {
      if ( *(_DWORD *)(a1 + 3488) )
        QuicSendQueueFlush(a1 + 3416, 11);
      QuicLossDetectionUpdateTimer(a1 + 2632, 1);
    }
  }
}

```

## disassembly

```asm
0x140021664  push    rbx
0x140021666  sub     rsp, 20h
0x14002166a  test    byte ptr [rdx+1], 20h
0x14002166e  mov     rbx, rcx
0x140021671  mov     [rdx+0D0h], r8d
0x140021678  jnz     short loc_1400216BD
0x14002167a  mov     edx, 4
0x14002167f  cmp     r8d, 4Ch ; 'L'
0x140021683  jb      short loc_1400216B8
0x140021685  call    QuicConnRemoveOutFlowBlockedReason
0x14002168a  test    al, al
0x14002168c  jz      short loc_1400216BD
0x14002168e  cmp     dword ptr [rbx+0DA0h], 0
0x140021695  jz      short loc_1400216A8
0x140021697  lea     rcx, [rbx+0D58h]
0x14002169e  mov     edx, 0Bh
0x1400216a3  call    QuicSendQueueFlush
0x1400216a8  lea     rcx, [rbx+0A48h]
0x1400216af  mov     dl, 1
0x1400216b1  call    QuicLossDetectionUpdateTimer
0x1400216b6  jmp     short loc_1400216BD
0x1400216b8  call    QuicConnAddOutFlowBlockedReason
0x1400216bd  add     rsp, 20h
0x1400216c1  pop     rbx
0x1400216c2  retn
```
