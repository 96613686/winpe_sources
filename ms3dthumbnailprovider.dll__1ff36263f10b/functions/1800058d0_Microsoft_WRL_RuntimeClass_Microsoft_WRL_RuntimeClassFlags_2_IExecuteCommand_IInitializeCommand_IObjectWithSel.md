# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`scalar deleting destructor'(uint)

- ea: `0x1800058d0`
- end: `0x1800058f8`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001f44`
- `0x1800058d0`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[7] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800058d0  push    rbx
0x1800058d2  sub     rsp, 20h
0x1800058d6  mov     dword ptr [rcx+1Ch], 0C0000001h
0x1800058dd  mov     rbx, rcx
0x1800058e0  test    dl, 1
0x1800058e3  jz      short loc_1800058EF
0x1800058e5  mov     edx, 20h ; ' '
0x1800058ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800058ef  mov     rax, rbx
0x1800058f2  add     rsp, 20h
0x1800058f6  pop     rbx
0x1800058f7  retn
```
