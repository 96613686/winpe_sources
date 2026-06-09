# ClassGetPdoId

- ea: `0x1400569e4`
- end: `0x140056a37`
- name: `ClassGetPdoId`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14005fe50`

## callees

- `0x14003e470`

## import_xrefs

- `ntoskrnl!IoGetDriverObjectExtension` at `0x140056a06`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x140056a06`

## pseudocode

```c
__int64 __fastcall ClassGetPdoId(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 (__fastcall **DriverObjectExtension)(__int64, _QWORD, __int64); // rax

  DriverObjectExtension = (__int64 (__fastcall **)(__int64, _QWORD, __int64))IoGetDriverObjectExtension(
                                                                               *(PDRIVER_OBJECT *)(a1 + 8),
                                                                               ClassInitialize);
  return DriverObjectExtension[47](a1, a2, a3);
}

```

## disassembly

```asm
0x1400569e4  mov     [rsp+arg_0], rbx
0x1400569e9  mov     [rsp+arg_8], rsi
0x1400569ee  push    rdi
0x1400569ef  sub     rsp, 20h
0x1400569f3  mov     edi, edx
0x1400569f5  mov     rsi, rcx
0x1400569f8  mov     rcx, [rcx+8]; DriverObject
0x1400569fc  lea     rdx, ClassInitialize; ClientIdentificationAddress
0x140056a03  mov     rbx, r8
0x140056a06  call    cs:__imp_IoGetDriverObjectExtension
0x140056a0d  nop     dword ptr [rax+rax+00h]
0x140056a12  mov     r8, rbx
0x140056a15  mov     edx, edi
0x140056a17  mov     rcx, rsi
0x140056a1a  mov     rax, [rax+178h]
0x140056a21  call    _guard_dispatch_icall
0x140056a26  mov     rbx, [rsp+28h+arg_0]
0x140056a2b  mov     rsi, [rsp+28h+arg_8]
0x140056a30  add     rsp, 20h
0x140056a34  pop     rdi
0x140056a35  retn
```
