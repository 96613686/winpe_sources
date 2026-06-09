# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(wchar_t const *,ulong *,uint)

- ea: `0x180006c00`
- end: `0x180006c22`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEB_WPEAKI@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006c0b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180006c0b`

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
0x180006c00  sub     rsp, 28h
0x180006c04  xor     edx, edx
0x180006c06  mov     ecx, 80004001h
0x180006c0b  call    cs:__imp_RoOriginateError
0x180006c12  nop     dword ptr [rax+rax+00h]
0x180006c17  mov     eax, 80004001h
0x180006c1c  add     rsp, 28h
0x180006c20  retn
```
