# lldpDrop

- ea: `0x1400034c0`
- end: `0x1400034f9`
- name: `lldpDrop`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002794`
- `0x140002b20`
- `0x140002fe0`

## callees

- `0x1400034c0`
- `0x140005ef8`

## pseudocode

```c
NTSTATUS __fastcall lldpDrop(__int64 a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax

  if ( SLOBYTE(WPP_MAIN_CB.SecurityDescriptor) < 0 )
    result = McTemplateK0qqq_EtwWriteTransfer(a1, a2, a3, *(_DWORD *)(a1 + 128), *(_DWORD *)(a2 + 88), a3);
  _InterlockedIncrement64((volatile signed __int64 *)(a1 + 888));
  return result;
}

```

## disassembly

```asm
0x1400034c0  push    rbx
0x1400034c2  sub     rsp, 30h
0x1400034c6  cmp     byte ptr cs:WPP_MAIN_CB.SecurityDescriptor, 0
0x1400034cd  mov     rbx, rcx
0x1400034d0  jge     short loc_1400034EA
0x1400034d2  mov     eax, [rdx+58h]
0x1400034d5  mov     r9d, [rcx+80h]
0x1400034dc  mov     [rsp+38h+var_10], r8d
0x1400034e1  mov     [rsp+38h+var_18], eax
0x1400034e5  call    McTemplateK0qqq_EtwWriteTransfer
0x1400034ea  lock inc qword ptr [rbx+378h]
0x1400034f2  add     rsp, 30h
0x1400034f6  pop     rbx
0x1400034f7  retn
```
