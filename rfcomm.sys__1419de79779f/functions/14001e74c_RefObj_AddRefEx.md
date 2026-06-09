# RefObj_AddRefEx

- ea: `0x14001e74c`
- end: `0x14001e780`
- name: `RefObj_AddRefEx`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `49`
- callee_count: `2`
- tags: ``

## callers

- `0x140001958`
- `0x140003330`
- `0x140003970`
- `0x1400060c4`
- `0x140006470`
- `0x140006814`
- `0x140006bc0`
- `0x140006f68`
- `0x1400079c0`
- `0x140007b60`
- `0x140008334`
- `0x14000877c`
- `0x140008cdc`
- `0x140009658`
- `0x140009cc8`
- `0x14000a060`
- `0x14000a5f0`
- `0x14000ab70`
- `0x14000aba8`
- `0x14000b318`
- `0x14000b808`
- `0x14000e700`
- `0x14000e840`
- `0x14000ecd0`
- `0x14000fe48`
- `0x140010150`
- `0x140010260`
- `0x140010810`
- `0x14001190c`
- `0x1400121d4`
- `0x140012590`
- `0x1400135cc`
- `0x140013bf8`
- `0x140014210`
- `0x140014b10`
- `0x140014c64`
- `0x14001513c`
- `0x1400152ec`
- `0x140015688`
- `0x140015904`
- `0x140015b04`
- `0x140015c4c`
- `0x1400162d0`
- `0x14001737c`
- `0x14001812c`
- `0x140018e9c`
- `0x1400195d0`
- `0x140019e5c`
- `0x14001a12c`

## callees

- `0x14001e74c`
- `0x14001e788`

## pseudocode

```c
__int64 __fastcall RefObj_AddRefEx(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  signed __int32 v4; // ebx

  v4 = _InterlockedExchangeAdd((volatile signed __int32 *)a1, 1u);
  if ( *(_QWORD *)(a1 + 16) )
    RefObj_AddTrackingBlock(a1, a3, a4, a2);
  return (unsigned int)(v4 + 1);
}

```

## disassembly

```asm
0x14001e74c  push    rbx
0x14001e74e  sub     rsp, 20h
0x14001e752  mov     rax, r9
0x14001e755  mov     r10d, r8d
0x14001e758  mov     ebx, 1
0x14001e75d  lock xadd [rcx], ebx
0x14001e761  cmp     qword ptr [rcx+10h], 0
0x14001e766  jz      short loc_14001E776
0x14001e768  mov     r9, rdx
0x14001e76b  mov     r8, rax
0x14001e76e  mov     edx, r10d
0x14001e771  call    RefObj_AddTrackingBlock
0x14001e776  lea     eax, [rbx+1]
0x14001e779  add     rsp, 20h
0x14001e77d  pop     rbx
0x14001e77e  retn
```
