# KbdHid_PnPComplete

- ea: `0x140005170`
- end: `0x1400051b2`
- name: `KbdHid_PnPComplete`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005170`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000519b`
- `ntoskrnl!KeSetEvent` at `0x14000519b`

## pseudocode

```c
__int64 __fastcall KbdHid_PnPComplete(__int64 a1, __int64 a2, struct _KEVENT *a3)
{
  __int64 v3; // rax

  v3 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)(v3 + 1) )
  {
    if ( *(_BYTE *)(a2 + 65) )
      *(_BYTE *)(v3 + 3) |= 1u;
    return 0;
  }
  else
  {
    KeSetEvent(a3 + 10, 0, 0);
    return 3221225494LL;
  }
}

```

## disassembly

```asm
0x140005170  sub     rsp, 28h
0x140005174  mov     rax, [rdx+0B8h]
0x14000517b  cmp     byte ptr [rax+1], 0
0x14000517f  jz      short loc_14000518F
0x140005181  cmp     byte ptr [rdx+41h], 0
0x140005185  jz      short loc_14000518B
0x140005187  or      byte ptr [rax+3], 1
0x14000518b  xor     eax, eax
0x14000518d  jmp     short loc_1400051AC
0x14000518f  lea     rcx, [r8+0F0h]; Event
0x140005196  xor     edx, edx; Increment
0x140005198  xor     r8d, r8d; Wait
0x14000519b  call    cs:__imp_KeSetEvent
0x1400051a2  nop     dword ptr [rax+rax+00h]
0x1400051a7  mov     eax, 0C0000016h
0x1400051ac  add     rsp, 28h
0x1400051b0  retn
```
