# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180002d40`
- end: `0x180002d5b`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002d4b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002d4b`

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
0x180002d40  sub     rsp, 28h
0x180002d44  xor     edx, edx
0x180002d46  mov     ecx, 80004001h
0x180002d4b  call    cs:__imp_RoOriginateError
0x180002d51  mov     eax, 80004001h
0x180002d56  add     rsp, 28h
0x180002d5a  retn
```
