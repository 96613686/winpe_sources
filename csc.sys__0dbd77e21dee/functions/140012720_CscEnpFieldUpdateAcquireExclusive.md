# CscEnpFieldUpdateAcquireExclusive

- ea: `0x140012720`
- end: `0x140012782`
- name: `CscEnpFieldUpdateAcquireExclusive`
- size: `98`
- prototype: `BOOLEAN __fastcall(__int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002a61c`
- `0x14002b1a8`
- `0x140048148`
- `0x14005f150`
- `0x14005f944`
- `0x1400691f8`
- `0x14006999c`
- `0x140072310`
- `0x140073330`
- `0x140073aa0`
- `0x14007dc34`
- `0x140089a40`

## callees

- `0x140012720`
- `0x14001b568`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001274b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001274b`

## pseudocode

```c
BOOLEAN __fastcall CscEnpFieldUpdateAcquireExclusive(__int64 a1)
{
  void *retaddr; // [rsp+38h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1, retaddr);
  return ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 120), 1u);
}

```

## disassembly

```asm
0x140012720  push    rbx
0x140012722  sub     rsp, 30h
0x140012726  mov     rbx, rcx
0x140012729  mov     rcx, cs:WPP_GLOBAL_Control
0x140012730  lea     rax, WPP_GLOBAL_Control
0x140012737  cmp     rcx, rax
0x14001273a  jz      short loc_140012745
0x14001273c  test    dword ptr [rcx+2Ch], 40000h
0x140012743  jnz     short loc_14001275E
0x140012745  mov     rcx, [rbx+78h]; Resource
0x140012749  mov     dl, 1; Wait
0x14001274b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012752  nop     dword ptr [rax+rax+00h]
0x140012757  add     rsp, 30h
0x14001275b  pop     rbx
0x14001275c  retn
0x14001275e  mov     rax, [rsp+38h]
0x140012763  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14001276a  mov     rcx, [rcx+18h]
0x14001276e  mov     edx, 0Ah
0x140012773  mov     r9, rbx
0x140012776  mov     [rsp+38h+var_18], rax
0x14001277b  call    WPP_SF_qq
0x140012780  jmp     short loc_140012745
```
