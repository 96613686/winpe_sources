# ProvisioningCommandsMap::`scalar deleting destructor'(uint)

- ea: `0x1800061a0`
- end: `0x1800061bd`
- name: `??_GProvisioningCommandsMap@@UEAAPEAXI@Z`
- size: `29`
- prototype: `ProvisioningCommandsMap *__fastcall(ProvisioningCommandsMap *this, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800061a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800061ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800061ae`

## pseudocode

```c
ProvisioningCommandsMap *__fastcall ProvisioningCommandsMap::`scalar deleting destructor'(
        ProvisioningCommandsMap *this,
        char a2)
{
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800061a0  push    rbx
0x1800061a2  sub     rsp, 20h
0x1800061a6  mov     rbx, rcx
0x1800061a9  test    dl, 1
0x1800061ac  jz      short loc_1800061B4
0x1800061ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800061b4  mov     rax, rbx
0x1800061b7  add     rsp, 20h
0x1800061bb  pop     rbx
0x1800061bc  retn
```
