# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vector deleting destructor'(uint)

- ea: `0x180001d80`
- end: `0x180001da3`
- name: `??_E?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPopupCommand@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001070`
- `0x180001d80`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPopupCommand>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180001d80  push    rbx
0x180001d82  sub     rsp, 20h
0x180001d86  mov     dword ptr [rcx+0Ch], 0C0000001h
0x180001d8d  mov     rbx, rcx
0x180001d90  test    dl, 1
0x180001d93  jz      short loc_180001D9A
0x180001d95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d9a  mov     rax, rbx
0x180001d9d  add     rsp, 20h
0x180001da1  pop     rbx
0x180001da2  retn
```
