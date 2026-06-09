# PcpLineDereference

- ea: `0x140003770`
- end: `0x1400037f6`
- name: `PcpLineDereference`
- size: `134`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x140001884`
- `0x1400029d0`
- `0x140002c1c`
- `0x140002d48`
- `0x140002e80`
- `0x140003ab0`
- `0x140005578`
- `0x140005b00`
- `0x140005c10`
- `0x140007f90`
- `0x140008440`
- `0x1400085c0`
- `0x140009050`
- `0x14000b5e0`
- `0x14000cce0`
- `0x14000eca0`
- `0x14000f1fc`
- `0x1400107dc`
- `0x140010c70`
- `0x140011154`
- `0x14001f2a0`

## callees

- `0x140003770`
- `0x1400039a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400037e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400037e8`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400037ae`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400037ae`
- `NDIS!NdisFreeRWLock` at `0x1400037d4`
- `NDIS!NdisFreeRWLock` at `0x1400037d4`

## pseudocode

```c
__int64 __fastcall PcpLineDereference(volatile signed __int32 *P, __int64 a2, __int64 a3)
{
  unsigned __int32 v4; // ebx
  void *v6; // rcx
  __int64 v7; // rcx
  struct _NDIS_RW_LOCK_EX *v8; // rcx

  v4 = _InterlockedDecrement(P + 62);
  if ( !v4 )
  {
    v6 = (void *)*((_QWORD *)P + 40);
    if ( v6 )
      NdisFreeMemoryWithTag(v6, 0x616E6350u);
    v7 = *((_QWORD *)P + 32);
    if ( v7 )
      PcpFilterDecrementDetachCount(v7, a2, a3);
    v8 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 2);
    if ( v8 )
      NdisFreeRWLock(v8);
    ExFreePoolWithTag((PVOID)P, 0x656C6350u);
  }
  return v4;
}

```

## disassembly

```asm
0x140003770  mov     [rsp+arg_0], rbx
0x140003775  push    rdi
0x140003776  sub     rsp, 20h
0x14000377a  mov     rdi, rcx
0x14000377d  mov     ebx, 0FFFFFFFFh
0x140003782  lock xadd [rcx+0F8h], ebx
0x14000378a  sub     ebx, 1
0x14000378d  jz      short loc_14000379D
0x14000378f  mov     eax, ebx
0x140003791  mov     rbx, [rsp+28h+arg_0]
0x140003796  add     rsp, 20h
0x14000379a  pop     rdi
0x14000379b  retn
0x14000379d  mov     rcx, [rcx+140h]; VirtualAddress
0x1400037a4  test    rcx, rcx
0x1400037a7  jz      short loc_1400037BA
0x1400037a9  mov     edx, 616E6350h; Tag
0x1400037ae  call    cs:__imp_NdisFreeMemoryWithTag
0x1400037b5  nop     dword ptr [rax+rax+00h]
0x1400037ba  mov     rcx, [rdi+100h]
0x1400037c1  test    rcx, rcx
0x1400037c4  jz      short loc_1400037CB
0x1400037c6  call    PcpFilterDecrementDetachCount
0x1400037cb  mov     rcx, [rdi+10h]; Lock
0x1400037cf  test    rcx, rcx
0x1400037d2  jz      short loc_1400037E0
0x1400037d4  call    cs:__imp_NdisFreeRWLock
0x1400037db  nop     dword ptr [rax+rax+00h]
0x1400037e0  mov     edx, 656C6350h; Tag
0x1400037e5  mov     rcx, rdi; P
0x1400037e8  call    cs:__imp_ExFreePoolWithTag
0x1400037ef  nop     dword ptr [rax+rax+00h]
0x1400037f4  jmp     short loc_14000378F
```
