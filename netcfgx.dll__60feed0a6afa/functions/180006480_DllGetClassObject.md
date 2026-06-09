# DllGetClassObject

- ea: `0x180006480`
- end: `0x1800064b8`
- name: `DllGetClassObject`
- size: `56`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800044cc`
- `0x180006480`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( qword_18001A628 )
    return ATL::CComModule::GetClassObject((ATL::CComModule *)&_Module, rclsid, riid, ppv);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180006480  test    r8, r8
0x180006483  jnz     short loc_18000648C
0x180006485  mov     eax, 80070057h
0x18000648a  jmp     short locret_1800064B7
0x18000648c  mov     qword ptr [r8], 0
0x180006493  cmp     cs:qword_18001A628, 0
0x18000649b  jz      short loc_1800064B2
0x18000649d  mov     r9, r8; void **
0x1800064a0  mov     r8, rdx; struct _GUID *
0x1800064a3  mov     rdx, rcx; struct _GUID *
0x1800064a6  lea     rcx, ?_Module@@3VCComModule@ATL@@A; this
0x1800064ad  jmp     ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x1800064b2  mov     eax, 80004005h
0x1800064b7  retn
```
