# Windows::Internal::ServiceModule::DisconnectCallback(void)

- ea: `0x180005200`
- end: `0x18000521f`
- name: `?DisconnectCallback@ServiceModule@Internal@Windows@@UEAAJXZ`
- size: `31`
- prototype: `HRESULT __fastcall(struct Microsoft::WRL::Details::ModuleBase **this, __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007b9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180005218`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::ServiceModule::DisconnectCallback(
        struct Microsoft::WRL::Details::ModuleBase **this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  Microsoft::WRL::Details::UnregisterObjects((Microsoft::WRL::Details *)(this + 5), this[4], a3);
  return CoDisconnectContext(0xFFFFFFFF);
}

```

## disassembly

```asm
0x180005200  sub     rsp, 28h
0x180005204  mov     rdx, [rcx+20h]; struct Microsoft::WRL::Details::ModuleBase *
0x180005208  add     rcx, 28h ; '('; this
0x18000520c  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180005211  or      ecx, 0FFFFFFFFh
0x180005214  add     rsp, 28h
0x180005218  jmp     cs:__imp_CoDisconnectContext
```
