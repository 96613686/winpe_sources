# QosNblCadComplete

- ea: `0x140011ae8`
- end: `0x140011b51`
- name: `QosNblCadComplete`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008440`
- `0x1400085c0`

## callees

- `0x140011ae8`
- `0x140011e28`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140011b39`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140011b39`

## pseudocode

```c
void __fastcall QosNblCadComplete(__int64 a1, _QWORD *a2, char a3)
{
  __int64 v3; // r9
  _QWORD *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rbx
  struct _NPAGED_LOOKASIDE_LIST *v7; // rcx

  v3 = *(_QWORD *)(a1 + 16);
  v4 = a2;
  *a2 = 0;
  v5 = *(unsigned __int16 *)(v3 + 10);
  v6 = *(_QWORD *)(v5 + v3 + 32);
  *(_BYTE *)(v5 + v3 + 60) = 1;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 48), 0xFFFFFFFF) == 1 )
  {
    LOBYTE(a2) = a3;
    QosNblCadReassemble(v6, a2);
    v7 = QosgNblCadLookasideList;
    *v4 = *(_QWORD *)(v6 + 24);
    ExFreeToNPagedLookasideList(v7, (PVOID)v6);
  }
}

```

## disassembly

```asm
0x140011ae8  mov     [rsp+arg_0], rbx
0x140011aed  push    rdi
0x140011aee  sub     rsp, 20h
0x140011af2  mov     r9, [rcx+10h]
0x140011af6  mov     rdi, rdx
0x140011af9  mov     qword ptr [rdx], 0
0x140011b00  movzx   eax, word ptr [r9+0Ah]
0x140011b05  mov     rbx, [rax+r9+20h]
0x140011b0a  mov     byte ptr [rax+r9+3Ch], 1
0x140011b10  or      eax, 0FFFFFFFFh
0x140011b13  lock xadd [rbx+30h], eax
0x140011b18  cmp     eax, 1
0x140011b1b  jnz     short loc_140011B45
0x140011b1d  mov     dl, r8b
0x140011b20  mov     rcx, rbx
0x140011b23  call    QosNblCadReassemble
0x140011b28  mov     rax, [rbx+18h]
0x140011b2c  mov     rdx, rbx; Entry
0x140011b2f  mov     rcx, cs:QosgNblCadLookasideList; Lookaside
0x140011b36  mov     [rdi], rax
0x140011b39  call    cs:__imp_ExFreeToNPagedLookasideList
0x140011b40  nop     dword ptr [rax+rax+00h]
0x140011b45  mov     rbx, [rsp+28h+arg_0]
0x140011b4a  add     rsp, 20h
0x140011b4e  pop     rdi
0x140011b4f  retn
```
