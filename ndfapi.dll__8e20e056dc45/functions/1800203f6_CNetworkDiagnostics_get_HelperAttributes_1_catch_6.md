# _CNetworkDiagnostics::get_HelperAttributes_::_1_::catch$6

- ea: `0x1800203f6`
- end: `0x18002042b`
- name: `_CNetworkDiagnostics::get_HelperAttributes_::_1_::catch$6`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180020413`
- `ole32!CoTaskMemFree` at `0x180020413`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::get_HelperAttributes_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = **(_DWORD **)(a2 + 32);
  CoTaskMemFree(*(LPVOID *)(a2 + 136));
  return 0;
}

```

## disassembly

```asm
0x1800203f6  mov     [rsp+arg_8], rdx
0x1800203fb  push    rbp
0x1800203fc  sub     rsp, 20h
0x180020400  mov     rbp, rdx
0x180020403  mov     rax, [rbp+20h]
0x180020407  mov     ecx, [rax]
0x180020409  mov     [rbp+70h], ecx
0x18002040c  mov     rcx, [rbp+88h]; pv
0x180020413  call    cs:__imp_CoTaskMemFree
0x180020419  nop
0x18002041a  mov     rax, 0
0x180020424  add     rsp, 20h
0x180020428  pop     rbp
0x180020429  retn
```
