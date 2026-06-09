# ProvisioningCommandsMap::`scalar deleting destructor'(uint)

- ea: `0x180006490`
- end: `0x1800064b4`
- name: `??_GProvisioningCommandsMap@@UEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(ProvisioningCommandsMap *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180006490`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000649e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000649e`

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
0x180006490  push    rbx
0x180006492  sub     rsp, 20h
0x180006496  mov     rbx, rcx
0x180006499  test    dl, 1
0x18000649c  jz      short loc_1800064AA
0x18000649e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800064a5  nop     dword ptr [rax+rax+00h]
0x1800064aa  mov     rax, rbx
0x1800064ad  add     rsp, 20h
0x1800064b1  pop     rbx
0x1800064b2  retn
```
