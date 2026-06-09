# CdSetThreadContext

- ea: `0x14000c010`
- end: `0x14000c0a4`
- name: `CdSetThreadContext`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001240`
- `0x140002250`
- `0x14000c374`

## callees

- `0x14000c010`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c020`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000c020`
- `ntoskrnl!IoWithinStackLimits` at `0x14000c049`
- `ntoskrnl!IoWithinStackLimits` at `0x14000c049`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c07f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000c07f`

## pseudocode

```c
__int64 __fastcall CdSetThreadContext(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rbx
  ULONG_PTR TopLevelIrp; // rdi
  __int64 result; // rax

  v4 = (_DWORD *)(a1 + 32);
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( !TopLevelIrp )
    *v4 |= 0x10u;
  if ( (*v4 & 0x10) != 0
    || !IoWithinStackLimits(TopLevelIrp, 0x18u)
    || (TopLevelIrp & 3) != 0
    || *(_DWORD *)TopLevelIrp != 1397113923 )
  {
    *(_DWORD *)a2 = 1397113923;
    *(_QWORD *)(a2 + 8) = TopLevelIrp;
    *(_QWORD *)(a2 + 16) = a1;
    IoSetTopLevelIrp((PIRP)a2);
    *v4 |= 0x20u;
    result = a1;
    *(_QWORD *)(a1 + 72) = a2;
  }
  else
  {
    result = *(_QWORD *)(TopLevelIrp + 16);
  }
  *(_QWORD *)(a1 + 56) = result;
  return result;
}

```

## disassembly

```asm
0x14000c010  push    rbx
0x14000c012  push    rsi
0x14000c013  push    rdi
0x14000c014  push    r14
0x14000c016  sub     rsp, 28h
0x14000c01a  mov     r14, rdx
0x14000c01d  mov     rsi, rcx
0x14000c020  call    cs:__imp_IoGetTopLevelIrp
0x14000c027  nop     dword ptr [rax+rax+00h]
0x14000c02c  lea     rbx, [rsi+20h]
0x14000c030  mov     rdi, rax
0x14000c033  test    rax, rax
0x14000c036  jnz     short loc_14000C03B
0x14000c038  or      dword ptr [rbx], 10h
0x14000c03b  mov     eax, [rbx]
0x14000c03d  test    al, 10h
0x14000c03f  jnz     short loc_14000C06D
0x14000c041  mov     edx, 18h; RegionSize
0x14000c046  mov     rcx, rdi; RegionStart
0x14000c049  call    cs:__imp_IoWithinStackLimits
0x14000c050  nop     dword ptr [rax+rax+00h]
0x14000c055  test    eax, eax
0x14000c057  jz      short loc_14000C06D
0x14000c059  test    dil, 3
0x14000c05d  jnz     short loc_14000C06D
0x14000c05f  cmp     dword ptr [rdi], 53464443h
0x14000c065  jnz     short loc_14000C06D
0x14000c067  mov     rax, [rdi+10h]
0x14000c06b  jmp     short loc_14000C095
0x14000c06d  mov     rcx, r14; Irp
0x14000c070  mov     dword ptr [r14], 53464443h
0x14000c077  mov     [r14+8], rdi
0x14000c07b  mov     [r14+10h], rsi
0x14000c07f  call    cs:__imp_IoSetTopLevelIrp
0x14000c086  nop     dword ptr [rax+rax+00h]
0x14000c08b  or      dword ptr [rbx], 20h
0x14000c08e  mov     rax, rsi
0x14000c091  mov     [rsi+48h], r14
0x14000c095  mov     [rsi+38h], rax
0x14000c099  add     rsp, 28h
0x14000c09d  pop     r14
0x14000c09f  pop     rdi
0x14000c0a0  pop     rsi
0x14000c0a1  pop     rbx
0x14000c0a2  retn
```
