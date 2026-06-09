# MouHid_PnPComplete

- ea: `0x140002000`
- end: `0x140002047`
- name: `MouHid_PnPComplete`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140002000`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140002022`
- `ntoskrnl!KeSetEvent` at `0x140002022`

## pseudocode

```c
__int64 __fastcall MouHid_PnPComplete(__int64 a1, __int64 a2, __int64 a3)
{
  _BYTE *v3; // rax

  v3 = *(_BYTE **)(a2 + 184);
  if ( *v3 != 27 || v3[1] )
  {
    if ( *(_BYTE *)(a2 + 65) )
      v3[3] |= 1u;
    return 0;
  }
  else
  {
    KeSetEvent((PRKEVENT)(a3 + 328), 0, 0);
    return 3221225494LL;
  }
}

```

## disassembly

```asm
0x140002000  sub     rsp, 28h
0x140002004  mov     rax, [rdx+0B8h]
0x14000200b  cmp     byte ptr [rax], 1Bh
0x14000200e  jnz     short loc_140002035
0x140002010  cmp     byte ptr [rax+1], 0
0x140002014  jnz     short loc_140002035
0x140002016  lea     rcx, [r8+148h]; Event
0x14000201d  xor     edx, edx; Increment
0x14000201f  xor     r8d, r8d; Wait
0x140002022  call    cs:__imp_KeSetEvent
0x140002029  nop     dword ptr [rax+rax+00h]
0x14000202e  mov     eax, 0C0000016h
0x140002033  jmp     short loc_140002041
0x140002035  cmp     byte ptr [rdx+41h], 0
0x140002039  jz      short loc_14000203F
0x14000203b  or      byte ptr [rax+3], 1
0x14000203f  xor     eax, eax
0x140002041  add     rsp, 28h
0x140002045  retn
```
