# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x1800069b0`
- end: `0x1800069cb`
- name: `?UnregisterCOMObject@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800069bb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800069bb`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800069b0  sub     rsp, 28h
0x1800069b4  xor     edx, edx
0x1800069b6  mov     ecx, 80004001h
0x1800069bb  call    cs:__imp_RoOriginateError
0x1800069c1  mov     eax, 80004001h
0x1800069c6  add     rsp, 28h
0x1800069ca  retn
```
