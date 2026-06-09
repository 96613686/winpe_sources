# DfscRmValidateLinkIterate

- ea: `0x1400115c0`
- end: `0x1400115fc`
- name: `DfscRmValidateLinkIterate`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140021688`

## pseudocode

```c
__int64 __fastcall DfscRmValidateLinkIterate(__int64 a1)
{
  *(_DWORD *)(a1 + 36) = DfscIterateAndGetReferral(
                           0,
                           *(_QWORD *)a1,
                           2,
                           *(_QWORD *)(a1 + 8),
                           *(_QWORD *)(a1 + 24),
                           a1 + 16);
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1400115c0  push    rbx
0x1400115c2  sub     rsp, 30h
0x1400115c6  mov     r9, [rcx+8]
0x1400115ca  lea     rax, [rcx+10h]
0x1400115ce  mov     rdx, [rcx]
0x1400115d1  mov     rbx, rcx
0x1400115d4  mov     [rsp+38h+var_10], rax
0x1400115d9  mov     r8d, 2
0x1400115df  mov     rax, [rcx+18h]
0x1400115e3  xor     ecx, ecx
0x1400115e5  mov     [rsp+38h+var_18], rax
0x1400115ea  call    DfscIterateAndGetReferral
0x1400115ef  mov     [rbx+24h], eax
0x1400115f2  or      eax, 0FFFFFFFFh
0x1400115f5  add     rsp, 30h
0x1400115f9  pop     rbx
0x1400115fa  retn
```
