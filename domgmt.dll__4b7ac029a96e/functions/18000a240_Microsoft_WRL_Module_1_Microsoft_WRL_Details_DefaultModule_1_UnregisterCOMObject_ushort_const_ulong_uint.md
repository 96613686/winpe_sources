# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x18000a240`
- end: `0x18000a25b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a24b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a24b`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000a240  sub     rsp, 28h
0x18000a244  xor     edx, edx
0x18000a246  mov     ecx, 80004001h
0x18000a24b  call    cs:__imp_RoOriginateError
0x18000a251  mov     eax, 80004001h
0x18000a256  add     rsp, 28h
0x18000a25a  retn
```
