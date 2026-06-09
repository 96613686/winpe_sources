# I8xSendResetCommand

- ea: `0x14000bb00`
- end: `0x14000bb74`
- name: `I8xSendResetCommand`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007c20`
- `0x14000b8a8`

## callees

- `0x1400059c0`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x14000bb28`
- `ntoskrnl!KeSetTimer` at `0x14000bb28`

## pseudocode

```c
__int64 __fastcall I8xSendResetCommand(__int64 a1)
{
  __int64 v2; // r9
  __int64 v3; // r8

  *(_DWORD *)(a1 + 928) = 0;
  KeSetTimer((PKTIMER)(a1 + 864), (LARGE_INTEGER)-15000000LL, (PKDPC)(a1 + 800));
  *(_BYTE *)(a1 + 1015) = 0;
  LOBYTE(v2) = -1;
  *(_QWORD *)(a1 + 1000) = 5;
  LOBYTE(v3) = 2;
  *(_BYTE *)(a1 + 1104) = 0;
  *(_QWORD *)(a1 + 1016) = MEMORY[0xFFFFF78000000320];
  return I8xPutBytePolled(0, 0, v3, v2);
}

```

## disassembly

```asm
0x14000bb00  push    rbx
0x14000bb02  sub     rsp, 20h
0x14000bb06  mov     rbx, rcx
0x14000bb09  mov     dword ptr [rcx+3A0h], 0
0x14000bb13  lea     r8, [rcx+320h]; Dpc
0x14000bb1a  mov     rdx, 0FFFFFFFFFF1B1E40h; DueTime
0x14000bb21  add     rcx, 360h; Timer
0x14000bb28  call    cs:__imp_KeSetTimer
0x14000bb2f  nop     dword ptr [rax+rax+00h]
0x14000bb34  mov     byte ptr [rbx+3F7h], 0
0x14000bb3b  mov     r9b, 0FFh
0x14000bb3e  mov     qword ptr [rbx+3E8h], 5
0x14000bb49  mov     r8b, 2
0x14000bb4c  mov     byte ptr [rbx+450h], 0
0x14000bb53  xor     edx, edx
0x14000bb55  mov     rax, ds:0FFFFF78000000320h
0x14000bb5f  xor     ecx, ecx
0x14000bb61  mov     [rbx+3F8h], rax
0x14000bb68  call    I8xPutBytePolled
0x14000bb6d  add     rsp, 20h
0x14000bb71  pop     rbx
0x14000bb72  retn
```
