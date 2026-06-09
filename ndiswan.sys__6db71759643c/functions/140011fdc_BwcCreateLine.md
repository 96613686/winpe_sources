# BwcCreateLine

- ea: `0x140011fdc`
- end: `0x1400120a3`
- name: `BwcCreateLine`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012b38`

## callees

- `0x140011fdc`
- `0x140012d80`
- `0x140013ea0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012004`
- `ntoskrnl!ExAllocatePool2` at `0x140012004`
- `NDIS!NdisAllocateRWLock` at `0x140012066`
- `NDIS!NdisAllocateRWLock` at `0x140012066`

## pseudocode

```c
__int64 __fastcall BwcCreateLine(__int64 a1, __int64 a2)
{
  __int64 Pool2; // rax
  _DWORD *v4; // rdi
  __int64 result; // rax
  NDIS_HANDLE v6; // rcx
  PNDIS_RW_LOCK_EX RWLock; // rax

  BwcVirtualLine = 0;
  Pool2 = ExAllocatePool2(64, 280, 1835235138);
  v4 = (_DWORD *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_DWORD *)(Pool2 + 272) = 1;
  QosLineCreate(Pool2 + 8, a2, -1);
  v6 = BwcMiniportHandle;
  *((_QWORD *)v4 + 30) = 0x28F5C28F5C28F5BLL;
  *((_QWORD *)v4 + 31) = -1;
  v4[56] = 1;
  RWLock = NdisAllocateRWLock(v6);
  *(_QWORD *)v4 = RWLock;
  if ( !RWLock )
  {
    BwcLineDereference(v4);
    return 3221225626LL;
  }
  v4[56] = 2;
  result = 0;
  BwcVirtualLine = v4;
  return result;
}

```

## disassembly

```asm
0x140011fdc  mov     [rsp+arg_0], rbx
0x140011fe1  push    rdi
0x140011fe2  sub     rsp, 30h
0x140011fe6  mov     rbx, rdx
0x140011fe9  mov     cs:BwcVirtualLine, 0
0x140011ff4  mov     edx, 118h
0x140011ff9  mov     ecx, 40h ; '@'
0x140011ffe  mov     r8d, 6D637742h
0x140012004  call    cs:__imp_ExAllocatePool2
0x14001200b  nop     dword ptr [rax+rax+00h]
0x140012010  mov     rdi, rax
0x140012013  test    rax, rax
0x140012016  jnz     short loc_14001201F
0x140012018  mov     eax, 0C000009Ah
0x14001201d  jmp     short loc_140012097
0x14001201f  lea     rcx, [rax+8]
0x140012023  mov     dword ptr [rax+110h], 1
0x14001202d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012031  mov     rdx, rbx
0x140012034  call    QosLineCreate
0x140012039  mov     rcx, cs:BwcMiniportHandle; NdisHandle
0x140012040  mov     rax, 28F5C28F5C28F5Bh
0x14001204a  mov     [rdi+0F0h], rax
0x140012051  mov     qword ptr [rdi+0F8h], 0FFFFFFFFFFFFFFFFh
0x14001205c  mov     dword ptr [rdi+0E0h], 1
0x140012066  call    cs:__imp_NdisAllocateRWLock
0x14001206d  nop     dword ptr [rax+rax+00h]
0x140012072  mov     [rdi], rax
0x140012075  test    rax, rax
0x140012078  jnz     short loc_140012084
0x14001207a  mov     rcx, rdi; P
0x14001207d  call    BwcLineDereference
0x140012082  jmp     short loc_140012018
0x140012084  mov     dword ptr [rdi+0E0h], 2
0x14001208e  xor     eax, eax
0x140012090  mov     cs:BwcVirtualLine, rdi
0x140012097  mov     rbx, [rsp+38h+arg_0]
0x14001209c  add     rsp, 30h
0x1400120a0  pop     rdi
0x1400120a1  retn
```
