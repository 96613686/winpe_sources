# I8xDeviceControl

- ea: `0x140020210`
- end: `0x140020289`
- name: `I8xDeviceControl`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d1a8`
- `0x14001d1a8`
- `0x140020210`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140020272`
- `ntoskrnl!IofCompleteRequest` at `0x140020272`

## pseudocode

```c
__int64 __fastcall I8xDeviceControl(__int64 a1, IRP *a2)
{
  __int64 v2; // rcx
  __int64 CurrentStackLocation; // r8

  v2 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(v2 + 565) && *(_BYTE *)(v2 + 566) && (*(_DWORD *)(v2 + 556) & 8) == 0 )
  {
    CurrentStackLocation = (__int64)a2->Tail.Overlay.CurrentStackLocation;
    if ( *(_DWORD *)(CurrentStackLocation + 24) == 2703680 )
      return I8xKeyboardGetSysButtonCaps(v2, (__int64)a2);
    if ( *(_DWORD *)(CurrentStackLocation + 24) == 2703684 )
      return I8xKeyboardGetSysButtonEvent(
               v2,
               (__int64)a2,
               CurrentStackLocation,
               (unsigned int)(*(_DWORD *)(CurrentStackLocation + 24) - 2703680));
  }
  a2->IoStatus.Status = -1073741808;
  IofCompleteRequest(a2, 0);
  return 3221225488LL;
}

```

## disassembly

```asm
0x140020210  sub     rsp, 28h
0x140020214  mov     rcx, [rcx+40h]
0x140020218  mov     rax, rdx
0x14002021b  cmp     byte ptr [rcx+235h], 0
0x140020222  jz      short loc_140020266
0x140020224  cmp     byte ptr [rcx+236h], 0
0x14002022b  jz      short loc_140020266
0x14002022d  mov     edx, [rcx+22Ch]
0x140020233  test    dl, 8
0x140020236  jnz     short loc_140020266
0x140020238  mov     r8, [rax+0B8h]
0x14002023f  mov     r9d, [r8+18h]
0x140020243  sub     r9d, 294140h
0x14002024a  jz      short loc_14002025C
0x14002024c  cmp     r9d, 4
0x140020250  jnz     short loc_140020266
0x140020252  mov     rdx, rax
0x140020255  call    I8xKeyboardGetSysButtonEvent
0x14002025a  jmp     short loc_140020283
0x14002025c  mov     rdx, rax
0x14002025f  call    I8xKeyboardGetSysButtonCaps
0x140020264  jmp     short loc_140020283
0x140020266  xor     edx, edx; PriorityBoost
0x140020268  mov     dword ptr [rax+30h], 0C0000010h
0x14002026f  mov     rcx, rax; Irp
0x140020272  call    cs:__imp_IofCompleteRequest
0x140020279  nop     dword ptr [rax+rax+00h]
0x14002027e  mov     eax, 0C0000010h
0x140020283  add     rsp, 28h
0x140020287  retn
```
