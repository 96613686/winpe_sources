# DelayedFreeAddrObj

- ea: `0x14001e4b0`
- end: `0x14001e4fc`
- name: `DelayedFreeAddrObj`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001e4b0`

## import_xrefs

- `ntoskrnl!SeDeassignSecurity` at `0x14001e4cd`
- `ntoskrnl!SeDeassignSecurity` at `0x14001e4cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001e4e4`

## pseudocode

```c
void __fastcall DelayedFreeAddrObj(__int64 a1, __int64 a2)
{
  int v2; // edi

  v2 = *(_DWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 168) )
    SeDeassignSecurity((PSECURITY_DESCRIPTOR *)(a2 + 168));
  *(_DWORD *)(a2 + 16) = v2 + 10;
  ExFreePoolWithTag((PVOID)a2, 0);
}

```

## disassembly

```asm
0x14001e4b0  mov     [rsp+arg_0], rbx
0x14001e4b5  push    rdi
0x14001e4b6  sub     rsp, 20h
0x14001e4ba  mov     edi, [rdx+10h]
0x14001e4bd  lea     rcx, [rdx+0A8h]; SecurityDescriptor
0x14001e4c4  cmp     qword ptr [rcx], 0
0x14001e4c8  mov     rbx, rdx
0x14001e4cb  jz      short loc_14001E4D9
0x14001e4cd  call    cs:__imp_SeDeassignSecurity
0x14001e4d4  nop     dword ptr [rax+rax+00h]
0x14001e4d9  lea     eax, [rdi+0Ah]
0x14001e4dc  xor     edx, edx; Tag
0x14001e4de  mov     rcx, rbx; P
0x14001e4e1  mov     [rbx+10h], eax
0x14001e4e4  call    cs:__imp_ExFreePoolWithTag
0x14001e4eb  nop     dword ptr [rax+rax+00h]
0x14001e4f0  mov     rbx, [rsp+28h+arg_0]
0x14001e4f5  add     rsp, 20h
0x14001e4f9  pop     rdi
0x14001e4fa  retn
```
