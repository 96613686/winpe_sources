# DiscpGetInitiatorsSupportingSecurity

- ea: `0x18000f4a8`
- end: `0x18000f4fc`
- name: `DiscpGetInitiatorsSupportingSecurity`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800100f8`
- `0x18001048c`
- `0x180010b5c`

## callees

- `0x180006998`
- `0x18000f4a8`

## import_xrefs

- `WMICLNT!WmiCloseBlock` at `0x18000f4eb`
- `WMICLNT!WmiCloseBlock` at `0x18000f4eb`
- `WMICLNT!WmiOpenBlock` at `0x18000f4c9`
- `WMICLNT!WmiOpenBlock` at `0x18000f4c9`

## pseudocode

```c
__int64 __fastcall DiscpGetInitiatorsSupportingSecurity(_QWORD *a1, _DWORD *a2, __int64 *a3)
{
  unsigned int InitiatorInstanceList; // ebx

  InitiatorInstanceList = WmiOpenBlock(MSiSCSI_SecurityConfigOperations_GUID, 2684354560LL, a1);
  if ( !InitiatorInstanceList )
  {
    InitiatorInstanceList = DiscpGetInitiatorInstanceList(0, a2, a3);
    if ( InitiatorInstanceList )
      WmiCloseBlock(*a1);
  }
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x18000f4a8  push    rbx
0x18000f4aa  push    rbp
0x18000f4ab  push    rsi
0x18000f4ac  push    rdi
0x18000f4ad  sub     rsp, 28h
0x18000f4b1  mov     rsi, r8
0x18000f4b4  mov     rbp, rdx
0x18000f4b7  mov     r8, rcx
0x18000f4ba  mov     rdi, rcx
0x18000f4bd  lea     rcx, MSiSCSI_SecurityConfigOperations_GUID
0x18000f4c4  mov     edx, 0A0000000h
0x18000f4c9  call    cs:__imp_WmiOpenBlock
0x18000f4cf  mov     ebx, eax
0x18000f4d1  test    eax, eax
0x18000f4d3  jnz     short loc_18000F4F1
0x18000f4d5  mov     r8, rsi
0x18000f4d8  mov     rdx, rbp
0x18000f4db  xor     ecx, ecx
0x18000f4dd  call    DiscpGetInitiatorInstanceList
0x18000f4e2  mov     ebx, eax
0x18000f4e4  test    eax, eax
0x18000f4e6  jz      short loc_18000F4F1
0x18000f4e8  mov     rcx, [rdi]
0x18000f4eb  call    cs:__imp_WmiCloseBlock
0x18000f4f1  mov     eax, ebx
0x18000f4f3  add     rsp, 28h
0x18000f4f7  pop     rdi
0x18000f4f8  pop     rsi
0x18000f4f9  pop     rbp
0x18000f4fa  pop     rbx
0x18000f4fb  retn
```
