# FIPfUserOpenDispatchCleanup

- ea: `0x140012fdc`
- end: `0x140013047`
- name: `FIPfUserOpenDispatchCleanup`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140012e50`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14001070c`
- `0x140012fdc`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140012ffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013039`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013039`

## pseudocode

```c
void __fastcall FIPfUserOpenDispatchCleanup(__int64 a1)
{
  __int64 v1; // rbx
  _QWORD *v2; // rdi

  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL);
  FILockExclusiveAcquire(&qword_140009760);
  v2 = *(_QWORD **)(v1 + 32);
  *(_QWORD *)(v1 + 32) = MmBadPointer;
  FILockExclusiveRelease(&qword_140009760);
  if ( v2 )
  {
    FIPfUserOpenCleanup(v2);
    ExFreePoolWithTag(v2, 0);
  }
}

```

## disassembly

```asm
0x140012fdc  mov     [rsp+arg_0], rbx
0x140012fe1  push    rdi
0x140012fe2  sub     rsp, 20h
0x140012fe6  mov     rax, [rcx+0B8h]
0x140012fed  lea     rcx, qword_140009760
0x140012ff4  mov     rbx, [rax+30h]
0x140012ff8  call    FILockExclusiveAcquire
0x140012ffd  mov     rax, cs:MmBadPointer
0x140013004  lea     rcx, qword_140009760
0x14001300b  mov     rdi, [rbx+20h]
0x14001300f  mov     rdx, [rax]
0x140013012  mov     [rbx+20h], rdx
0x140013016  call    FILockExclusiveRelease
0x14001301b  test    rdi, rdi
0x14001301e  jnz     short loc_14001302C
0x140013020  mov     rbx, [rsp+28h+arg_0]
0x140013025  add     rsp, 20h
0x140013029  pop     rdi
0x14001302a  retn
0x14001302c  mov     rcx, rdi
0x14001302f  call    FIPfUserOpenCleanup
0x140013034  xor     edx, edx; Tag
0x140013036  mov     rcx, rdi; P
0x140013039  call    cs:__imp_ExFreePoolWithTag
0x140013040  nop     dword ptr [rax+rax+00h]
0x140013045  jmp     short loc_140013020
```
