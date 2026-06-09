# KbdHid_CancelAutoRepeatTimer

- ea: `0x140001d30`
- end: `0x140001da0`
- name: `KbdHid_CancelAutoRepeatTimer`
- size: `112`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001300`
- `0x1400053c0`
- `0x140006680`
- `0x14000f930`

## callees

- `0x140001d30`
- `0x140001ed0`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140001d4f`
- `ntoskrnl!KeCancelTimer` at `0x140001d4f`

## pseudocode

```c
char __fastcall KbdHid_CancelAutoRepeatTimer(char *Context, int a2)
{
  BOOLEAN v4; // al

  if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 6) )
    return 0;
  v4 = KeCancelTimer((PKTIMER)(Context + 432));
  if ( a2 == 5 )
  {
    if ( v4 )
      *((_QWORD *)Context + 100) = MEMORY[0xFFFFF78000000014];
  }
  KbdHid_S0IdleStateUpdate(Context, 0, a2);
  return 1;
}

```

## disassembly

```asm
0x140001d30  mov     [rsp+arg_0], rbx
0x140001d35  push    rdi
0x140001d36  sub     rsp, 20h
0x140001d3a  cmp     byte ptr cs:WPP_MAIN_CB.Queue+2Eh, 0
0x140001d41  mov     edi, edx
0x140001d43  mov     rbx, rcx
0x140001d46  jnz     short loc_140001D7B
0x140001d48  add     rcx, 1B0h; PKTIMER
0x140001d4f  call    cs:__imp_KeCancelTimer
0x140001d56  nop     dword ptr [rax+rax+00h]
0x140001d5b  cmp     edi, 5
0x140001d5e  jz      short loc_140001D89
0x140001d60  mov     r8d, edi
0x140001d63  xor     edx, edx
0x140001d65  mov     rcx, rbx; Context
0x140001d68  call    KbdHid_S0IdleStateUpdate
0x140001d6d  mov     al, 1
0x140001d6f  mov     rbx, [rsp+28h+arg_0]
0x140001d74  add     rsp, 20h
0x140001d78  pop     rdi
0x140001d79  retn
0x140001d7b  mov     rbx, [rsp+28h+arg_0]
0x140001d80  xor     al, al
0x140001d82  add     rsp, 20h
0x140001d86  pop     rdi
0x140001d87  retn
0x140001d89  test    al, al
0x140001d8b  jz      short loc_140001D60
0x140001d8d  mov     rax, ds:0FFFFF78000000014h
0x140001d97  mov     [rbx+320h], rax
0x140001d9e  jmp     short loc_140001D60
```
