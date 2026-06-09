# QuicWorkerThreadWake

- ea: `0x14002e7a4`
- end: `0x14002e7e9`
- name: `QuicWorkerThreadWake`
- size: `69`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000c5b0`
- `0x140022528`
- `0x1400230c0`
- `0x14002e654`
- `0x1400454e4`

## callees

- `0x14002e7a4`
- `0x1400337e4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14002e7d7`
- `ntoskrnl!KeSetEvent` at `0x14002e7d7`

## pseudocode

```c
LONG __fastcall QuicWorkerThreadWake(__int64 a1)
{
  bool v1; // zf
  LONG result; // eax

  v1 = *(_BYTE *)(a1 + 80) == 0;
  *(_BYTE *)(a1 + 40) = 1;
  if ( v1 )
    return KeSetEvent((PRKEVENT)(a1 + 128), 0, 0);
  result = CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\worker.c", 51, "0");
  __int2c();
  return result;
}

```

## disassembly

```asm
0x14002e7a4  sub     rsp, 28h
0x14002e7a8  cmp     byte ptr [rcx+50h], 0
0x14002e7ac  mov     byte ptr [rcx+28h], 1
0x14002e7b0  jz      short loc_14002E7CE
0x14002e7b2  lea     r8, a0; "0"
0x14002e7b9  mov     edx, 33h ; '3'
0x14002e7be  lea     rcx, aCW1SMsquicSrcC_20; "C:\\__w\\1\\s\\msquic\\src\\core\\worke"...
0x14002e7c5  call    CxPlatLogAssert
0x14002e7ca  int     2Ch; Windows NT - assertion failure
0x14002e7cc  jmp     short loc_14002E7E3
0x14002e7ce  sub     rcx, 0FFFFFFFFFFFFFF80h; Event
0x14002e7d2  xor     r8d, r8d; Wait
0x14002e7d5  xor     edx, edx; Increment
0x14002e7d7  call    cs:__imp_KeSetEvent
0x14002e7de  nop     dword ptr [rax+rax+00h]
0x14002e7e3  add     rsp, 28h
0x14002e7e7  retn
```
