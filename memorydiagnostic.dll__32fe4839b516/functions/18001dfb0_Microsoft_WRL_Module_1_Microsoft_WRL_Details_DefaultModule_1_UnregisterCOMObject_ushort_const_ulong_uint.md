# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x18001dfb0`
- end: `0x18001dfd2`
- name: `?UnregisterCOMObject@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001dfbb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001dfbb`

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
0x18001dfb0  sub     rsp, 28h
0x18001dfb4  xor     edx, edx
0x18001dfb6  mov     ecx, 80004001h
0x18001dfbb  call    cs:__imp_RoOriginateError
0x18001dfc2  nop     dword ptr [rax+rax+00h]
0x18001dfc7  mov     eax, 80004001h
0x18001dfcc  add     rsp, 28h
0x18001dfd0  retn
```
