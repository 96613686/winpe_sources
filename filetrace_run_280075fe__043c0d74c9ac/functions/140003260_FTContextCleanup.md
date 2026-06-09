# FTContextCleanup

- ea: `0x140003260`
- end: `0x1400032a7`
- name: `FTContextCleanup`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003260`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000327c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000327c`
- `ntoskrnl!ObfDereferenceObject` at `0x140003294`
- `ntoskrnl!ObfDereferenceObject` at `0x140003294`

## pseudocode

```c
void __fastcall FTContextCleanup(__int64 a1, __int16 a2)
{
  void *v3; // rcx
  void *v4; // rcx

  if ( a2 == 1 )
  {
    v3 = *(void **)(a1 + 8);
    if ( v3 )
      ExFreePoolWithTag(v3, 0x72744C46u);
    v4 = *(void **)(a1 + 496);
    if ( v4 )
      ObfDereferenceObject(v4);
  }
}

```

## disassembly

```asm
0x140003260  cmp     dx, 1
0x140003264  jnz     short locret_1400032A5
0x140003266  push    rbx
0x140003267  sub     rsp, 20h
0x14000326b  mov     rbx, rcx
0x14000326e  mov     rcx, [rcx+8]; P
0x140003272  test    rcx, rcx
0x140003275  jz      short loc_140003288
0x140003277  mov     edx, 72744C46h; Tag
0x14000327c  call    cs:__imp_ExFreePoolWithTag
0x140003283  nop     dword ptr [rax+rax+00h]
0x140003288  mov     rcx, [rbx+1F0h]; Object
0x14000328f  test    rcx, rcx
0x140003292  jz      short loc_1400032A0
0x140003294  call    cs:__imp_ObfDereferenceObject
0x14000329b  nop     dword ptr [rax+rax+00h]
0x1400032a0  add     rsp, 20h
0x1400032a4  pop     rbx
0x1400032a5  retn
```
