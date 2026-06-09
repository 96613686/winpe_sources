# ClassDispatchUnimplemented

- ea: `0x140028e70`
- end: `0x140028eb8`
- name: `ClassDispatchUnimplemented`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140028e70`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140028ea0`
- `ntoskrnl!IofCompleteRequest` at `0x140028ea0`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140028e88`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140028e88`

## pseudocode

```c
__int64 __fastcall ClassDispatchUnimplemented(__int64 a1, __int64 a2)
{
  if ( **(_BYTE **)(a2 + 184) == 22 )
    PoStartNextPowerIrp((PIRP)a2);
  *(_DWORD *)(a2 + 48) = -1073741808;
  IofCompleteRequest((PIRP)a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x140028e70  push    rbx
0x140028e72  sub     rsp, 20h
0x140028e76  mov     rax, [rdx+0B8h]
0x140028e7d  mov     rbx, rdx
0x140028e80  cmp     byte ptr [rax], 16h
0x140028e83  jnz     short loc_140028E94
0x140028e85  mov     rcx, rdx; Irp
0x140028e88  call    cs:__imp_PoStartNextPowerIrp
0x140028e8f  nop     dword ptr [rax+rax+00h]
0x140028e94  xor     edx, edx; PriorityBoost
0x140028e96  mov     dword ptr [rbx+30h], 0C0000010h
0x140028e9d  mov     rcx, rbx; Irp
0x140028ea0  call    cs:__imp_IofCompleteRequest
0x140028ea7  nop     dword ptr [rax+rax+00h]
0x140028eac  mov     eax, 0C0000010h
0x140028eb1  add     rsp, 20h
0x140028eb5  pop     rbx
0x140028eb6  retn
```
