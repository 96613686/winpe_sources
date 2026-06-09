# CClients::CallbackRoutine(IAS_CALLBACK *)

- ea: `0x180009c10`
- end: `0x180009c34`
- name: `?CallbackRoutine@CClients@@CAXPEAUIAS_CALLBACK@@@Z`
- size: `36`
- prototype: `void __fastcall(struct IAS_CALLBACK *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009f58`

## callees

- `0x180009e44`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c2d`

## pseudocode

```c
void __fastcall CClients::CallbackRoutine(struct IAS_CALLBACK *a1)
{
  CClients::Resolve(*((CClients **)a1 + 1), *((_DWORD *)a1 + 4));
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180009c10  push    rbx
0x180009c12  sub     rsp, 20h
0x180009c16  mov     edx, [rcx+10h]; unsigned int
0x180009c19  mov     rbx, rcx
0x180009c1c  mov     rcx, [rcx+8]; this
0x180009c20  call    ?Resolve@CClients@@AEAAXK@Z; CClients::Resolve(ulong)
0x180009c25  mov     rcx, rbx
0x180009c28  add     rsp, 20h
0x180009c2c  pop     rbx
0x180009c2d  jmp     cs:__imp_CoTaskMemFree
```
