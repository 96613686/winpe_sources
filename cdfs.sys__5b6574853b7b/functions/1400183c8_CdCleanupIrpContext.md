# CdCleanupIrpContext

- ea: `0x1400183c8`
- end: `0x1400184ec`
- name: `CdCleanupIrpContext`
- size: `292`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001160`
- `0x140001240`
- `0x140001474`
- `0x140002250`
- `0x14000c6d8`
- `0x14001a9a0`

## callees

- `0x1400183c8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001844f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001844f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018484`
- `ntoskrnl!ExReleaseFastMutex` at `0x140018484`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001841b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018497`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001841b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018497`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400183f3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400184c0`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400183f3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400184c0`

## pseudocode

```c
void __fastcall CdCleanupIrpContext(_DWORD *P, char a2)
{
  int v2; // eax
  _DWORD *v4; // rax
  void *v5; // rcx
  _DWORD *v6; // rax

  v2 = P[8];
  if ( (v2 & 2) != 0 )
  {
    if ( a2 )
    {
      v6 = (_DWORD *)*((_QWORD *)P + 9);
      if ( v6 )
      {
        *v6 = 0;
        IoSetTopLevelIrp(*(PIRP *)(*((_QWORD *)P + 9) + 8LL));
        *((_QWORD *)P + 9) = 0;
      }
      P[8] &= 0xFFFFFD01;
    }
    else
    {
      P[8] = v2 & 0xFFFFFD7D;
    }
  }
  else
  {
    v4 = (_DWORD *)*((_QWORD *)P + 9);
    if ( v4 )
    {
      *v4 = 0;
      IoSetTopLevelIrp(*(PIRP *)(*((_QWORD *)P + 9) + 8LL));
      *((_QWORD *)P + 9) = 0;
    }
    if ( (P[8] & 0x100) != 0 )
    {
      v5 = (void *)*((_QWORD *)P + 6);
      if ( v5 )
      {
        ExFreePoolWithTag(v5, 0);
        *((_QWORD *)P + 6) = 0;
      }
    }
    if ( (P[8] & 1) == 0 )
    {
      if ( dword_140007300 >= (unsigned int)dword_140007304 )
      {
        ExFreePoolWithTag(P, 0);
      }
      else
      {
        ExAcquireFastMutex(&FastMutex);
        *(_QWORD *)P = qword_140007308;
        ++dword_140007300;
        qword_140007308 = P;
        qword_140007350 = 0;
        ExReleaseFastMutex(&FastMutex);
      }
    }
  }
}

```

## disassembly

```asm
0x1400183c8  push    rbx
0x1400183ca  sub     rsp, 20h
0x1400183ce  mov     eax, [rcx+20h]
0x1400183d1  mov     rbx, rcx
0x1400183d4  test    al, 2
0x1400183d6  jnz     loc_1400184A5
0x1400183dc  mov     rax, [rcx+48h]
0x1400183e0  test    rax, rax
0x1400183e3  jz      short loc_140018407
0x1400183e5  mov     dword ptr [rax], 0
0x1400183eb  mov     rcx, [rcx+48h]
0x1400183ef  mov     rcx, [rcx+8]; Irp
0x1400183f3  call    cs:__imp_IoSetTopLevelIrp
0x1400183fa  nop     dword ptr [rax+rax+00h]
0x1400183ff  mov     qword ptr [rbx+48h], 0
0x140018407  test    dword ptr [rbx+20h], 100h
0x14001840e  jz      short loc_14001842F
0x140018410  mov     rcx, [rbx+30h]; P
0x140018414  test    rcx, rcx
0x140018417  jz      short loc_14001842F
0x140018419  xor     edx, edx; Tag
0x14001841b  call    cs:__imp_ExFreePoolWithTag
0x140018422  nop     dword ptr [rax+rax+00h]
0x140018427  mov     qword ptr [rbx+30h], 0
0x14001842f  mov     eax, [rbx+20h]
0x140018432  test    al, 1
0x140018434  jnz     loc_1400184E5
0x14001843a  mov     eax, cs:dword_140007304
0x140018440  cmp     cs:dword_140007300, eax
0x140018446  jnb     short loc_140018492
0x140018448  lea     rcx, FastMutex; FastMutex
0x14001844f  call    cs:__imp_ExAcquireFastMutex
0x140018456  nop     dword ptr [rax+rax+00h]
0x14001845b  mov     rax, cs:qword_140007308
0x140018462  lea     rcx, FastMutex; FastMutex
0x140018469  mov     [rbx], rax
0x14001846c  inc     cs:dword_140007300
0x140018472  mov     cs:qword_140007308, rbx
0x140018479  mov     cs:qword_140007350, 0
0x140018484  call    cs:__imp_ExReleaseFastMutex
0x14001848b  nop     dword ptr [rax+rax+00h]
0x140018490  jmp     short loc_1400184E5
0x140018492  xor     edx, edx; Tag
0x140018494  mov     rcx, rbx; P
0x140018497  call    cs:__imp_ExFreePoolWithTag
0x14001849e  nop     dword ptr [rax+rax+00h]
0x1400184a3  jmp     short loc_1400184E5
0x1400184a5  test    dl, dl
0x1400184a7  jz      short loc_1400184DD
0x1400184a9  mov     rax, [rcx+48h]
0x1400184ad  test    rax, rax
0x1400184b0  jz      short loc_1400184D4
0x1400184b2  mov     dword ptr [rax], 0
0x1400184b8  mov     rcx, [rcx+48h]
0x1400184bc  mov     rcx, [rcx+8]; Irp
0x1400184c0  call    cs:__imp_IoSetTopLevelIrp
0x1400184c7  nop     dword ptr [rax+rax+00h]
0x1400184cc  mov     qword ptr [rbx+48h], 0
0x1400184d4  and     dword ptr [rbx+20h], 0FFFFFD01h
0x1400184db  jmp     short loc_1400184E5
0x1400184dd  and     eax, 0FFFFFD7Dh
0x1400184e2  mov     [rcx+20h], eax
0x1400184e5  add     rsp, 20h
0x1400184e9  pop     rbx
0x1400184ea  retn
```
