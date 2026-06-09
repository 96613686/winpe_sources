# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vector deleting destructor'(uint)

- ea: `0x180001d50`
- end: `0x180001d73`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEASConsentPopup@@UIPopupCommandHandler@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001070`
- `0x180001d50`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEASConsentPopup,IPopupCommandHandler>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001d50  push    rbx
0x180001d52  sub     rsp, 20h
0x180001d56  mov     dword ptr [rcx+14h], 0C0000001h
0x180001d5d  mov     rbx, rcx
0x180001d60  test    dl, 1
0x180001d63  jz      short loc_180001D6A
0x180001d65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d6a  mov     rax, rbx
0x180001d6d  add     rsp, 20h
0x180001d71  pop     rbx
0x180001d72  retn
```
