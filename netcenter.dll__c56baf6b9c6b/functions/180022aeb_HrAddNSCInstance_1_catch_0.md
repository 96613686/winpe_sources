# _HrAddNSCInstance_::_1_::catch$0

- ea: `0x180022aeb`
- end: `0x180022b1b`
- name: `_HrAddNSCInstance_::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022b03`

## pseudocode

```c
__int64 __fastcall HrAddNSCInstance_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = -2147024882;
  CoTaskMemFree(*(LPVOID *)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x180022aeb  mov     [rsp+arg_8], rdx
0x180022af0  push    rbp
0x180022af1  sub     rsp, 20h
0x180022af5  mov     rbp, rdx
0x180022af8  mov     dword ptr [rbp+30h], 8007000Eh
0x180022aff  mov     rcx, [rbp+40h]; pv
0x180022b03  call    cs:__imp_CoTaskMemFree
0x180022b09  nop
0x180022b0a  mov     rax, 0
0x180022b14  add     rsp, 20h
0x180022b18  pop     rbp
0x180022b19  retn
```
