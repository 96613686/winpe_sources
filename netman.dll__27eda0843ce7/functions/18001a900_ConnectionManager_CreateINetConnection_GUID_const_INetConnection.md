# ConnectionManager::CreateINetConnection(_GUID const &,INetConnection * *)

- ea: `0x18001a900`
- end: `0x18001a924`
- name: `?CreateINetConnection@ConnectionManager@@UEAAJAEBU_GUID@@PEAPEAUINetConnection@@@Z`
- size: `36`
- prototype: `HRESULT __fastcall(ConnectionManager *this, const struct _GUID *, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a919`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a919`

## pseudocode

```c
HRESULT __fastcall ConnectionManager::CreateINetConnection(
        ConnectionManager *this,
        const struct _GUID *a2,
        LPVOID *ppv)
{
  return CoCreateInstance(a2, 0, 4u, &GUID_c08956a1_1cd3_11d1_b1c5_00805fc1270e, ppv);
}

```

## disassembly

```asm
0x18001a900  sub     rsp, 38h
0x18001a904  mov     rcx, rdx; rclsid
0x18001a907  mov     [rsp+38h+ppv], r8; ppv
0x18001a90c  xor     edx, edx; pUnkOuter
0x18001a90e  lea     r9, _GUID_c08956a1_1cd3_11d1_b1c5_00805fc1270e; riid
0x18001a915  lea     r8d, [rdx+4]; dwClsContext
0x18001a919  call    cs:__imp_CoCreateInstance
0x18001a91f  add     rsp, 38h
0x18001a923  retn
```
