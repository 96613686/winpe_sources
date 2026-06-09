# SmbMmFreeSmbBuffer

- ea: `0x140028230`
- end: `0x140028277`
- name: `SmbMmFreeSmbBuffer`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400093a0`
- `0x140011910`
- `0x140022950`
- `0x14003822c`
- `0x14003dc50`

## callees

- `0x140028230`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140028254`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140028254`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028265`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028265`

## pseudocode

```c
void __fastcall SmbMmFreeSmbBuffer(__int64 a1, ULONG a2)
{
  __int64 v3; // rcx
  void *v4; // rax

  v3 = a1 & 7;
  v4 = (void *)(a1 & 0xFFFFFFFFFFFFFFF8uLL);
  if ( (unsigned int)v3 > 4 )
    ExFreePoolWithTag(v4, a2);
  else
    ExFreeToNPagedLookasideList(&SmbBufferLookasideList + v3, v4);
}

```

## disassembly

```asm
0x140028230  sub     rsp, 28h
0x140028234  mov     rax, rcx
0x140028237  and     ecx, 7
0x14002823a  and     rax, 0FFFFFFFFFFFFFFF8h
0x14002823e  cmp     ecx, 4
0x140028241  ja      short loc_140028262
0x140028243  shl     rcx, 7
0x140028247  lea     rdx, SmbBufferLookasideList
0x14002824e  add     rcx, rdx; Lookaside
0x140028251  mov     rdx, rax; Entry
0x140028254  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002825b  nop     dword ptr [rax+rax+00h]
0x140028260  jmp     short loc_140028271
0x140028262  mov     rcx, rax; P
0x140028265  call    cs:__imp_ExFreePoolWithTag
0x14002826c  nop     dword ptr [rax+rax+00h]
0x140028271  add     rsp, 28h
0x140028275  retn
```
