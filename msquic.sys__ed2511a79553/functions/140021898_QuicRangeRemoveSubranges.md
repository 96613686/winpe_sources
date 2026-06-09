# QuicRangeRemoveSubranges

- ea: `0x140021898`
- end: `0x1400218e4`
- name: `QuicRangeRemoveSubranges`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400123c0`
- `0x140013550`
- `0x140014630`
- `0x14001be88`
- `0x14001c0f4`

## callees

- `0x140021898`
- `0x14003cb00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e568`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e568`
- `ntoskrnl!ExAllocatePool2` at `0x14003e535`
- `ntoskrnl!ExAllocatePool2` at `0x14003e535`

## pseudocode

```c
char __fastcall QuicRangeRemoveSubranges(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rdi
  unsigned int v5; // r8d
  unsigned int v6; // ecx
  unsigned int v7; // edi
  char result; // al
  unsigned int v9; // edi
  void *Pool2; // rsi

  v3 = a3;
  v5 = *(_DWORD *)(a1 + 8);
  if ( a2 + (unsigned int)v3 < v5 )
    memmove(
      (void *)(*(_QWORD *)a1 + 16LL * a2),
      (const void *)(*(_QWORD *)a1 + 16 * (a2 + v3)),
      16LL * (v5 - a2 - (unsigned int)v3));
  v6 = *(_DWORD *)(a1 + 8) - v3;
  v7 = *(_DWORD *)(a1 + 12);
  *(_DWORD *)(a1 + 8) = v6;
  if ( v7 < 0x10 || v6 >= v7 >> 2 )
    return 0;
  v9 = v7 >> 1;
  if ( v9 != 8 )
  {
    Pool2 = (void *)ExAllocatePool2(66, 16LL * v9, 825320273);
    if ( Pool2 )
      goto LABEL_9;
    return 0;
  }
  Pool2 = (void *)(a1 + 24);
LABEL_9:
  memmove(Pool2, *(const void **)a1, 16LL * *(unsigned int *)(a1 + 8));
  ExFreePoolWithTag(*(PVOID *)a1, 0x31316351u);
  result = 1;
  *(_QWORD *)a1 = Pool2;
  *(_DWORD *)(a1 + 12) = v9;
  return result;
}

```

## disassembly

```asm
0x140021898  mov     [rsp+arg_0], rbx
0x14002189d  mov     [rsp+arg_8], rsi
0x1400218a2  push    rdi
0x1400218a3  sub     rsp, 20h
0x1400218a7  mov     edi, r8d
0x1400218aa  mov     rbx, rcx
0x1400218ad  mov     r8d, [rcx+8]
0x1400218b1  lea     eax, [rdx+rdi]
0x1400218b4  cmp     eax, r8d
0x1400218b7  jb      loc_14003E4DE
0x1400218bd  mov     ecx, [rbx+8]
0x1400218c0  sub     ecx, edi
0x1400218c2  mov     edi, [rbx+0Ch]
0x1400218c5  mov     [rbx+8], ecx
0x1400218c8  cmp     edi, 10h
0x1400218cb  jnb     loc_14003E50A
0x1400218d1  xor     al, al
0x1400218d3  mov     rbx, [rsp+28h+arg_0]
0x1400218d8  mov     rsi, [rsp+28h+arg_8]
0x1400218dd  add     rsp, 20h
0x1400218e1  pop     rdi
0x1400218e2  retn
0x14003e4de  mov     rax, [rbx]
0x14003e4e1  sub     r8d, edx
0x14003e4e4  mov     ecx, edx
0x14003e4e6  sub     r8d, edi
0x14003e4e9  shl     r8, 4; Size
0x14003e4ed  lea     rdx, [rcx+rdi]
0x14003e4f1  shl     rcx, 4
0x14003e4f5  shl     rdx, 4
0x14003e4f9  add     rcx, rax; void *
0x14003e4fc  add     rdx, rax; Src
0x14003e4ff  call    memmove
0x14003e504  nop
0x14003e505  jmp     loc_1400218BD
0x14003e50a  mov     eax, edi
0x14003e50c  shr     eax, 2
0x14003e50f  cmp     ecx, eax
0x14003e511  jnb     loc_1400218D1
0x14003e517  shr     edi, 1
0x14003e519  cmp     edi, 8
0x14003e51c  jnz     short loc_14003E524
0x14003e51e  lea     rsi, [rbx+18h]
0x14003e522  jmp     short loc_14003E54D
0x14003e524  mov     edx, edi
0x14003e526  mov     ecx, 42h ; 'B'
0x14003e52b  shl     rdx, 4
0x14003e52f  mov     r8d, 31316351h
0x14003e535  call    cs:__imp_ExAllocatePool2
0x14003e53c  nop     dword ptr [rax+rax+00h]
0x14003e541  mov     rsi, rax
0x14003e544  test    rax, rax
0x14003e547  jz      loc_1400218D1
0x14003e54d  mov     r8d, [rbx+8]
0x14003e551  mov     rcx, rsi; void *
0x14003e554  mov     rdx, [rbx]; Src
0x14003e557  shl     r8, 4; Size
0x14003e55b  call    memmove
0x14003e560  mov     rcx, [rbx]; P
0x14003e563  mov     edx, 31316351h; Tag
0x14003e568  call    cs:__imp_ExFreePoolWithTag
0x14003e56f  nop     dword ptr [rax+rax+00h]
0x14003e574  mov     al, 1
0x14003e576  mov     [rbx], rsi
0x14003e579  mov     [rbx+0Ch], edi
0x14003e57c  jmp     loc_1400218D3
```
