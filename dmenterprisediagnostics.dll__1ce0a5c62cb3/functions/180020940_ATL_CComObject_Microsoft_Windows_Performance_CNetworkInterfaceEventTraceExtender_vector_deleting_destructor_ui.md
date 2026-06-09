# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180020940`
- end: `0x180020974`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall(Microsoft::Windows::Performance::CEventTraceExtenderBase *, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001804`
- `0x1800208f8`
- `0x180020940`

## pseudocode

```c
Microsoft::Windows::Performance::CEventTraceExtenderBase *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CEventTraceExtenderBase *a1,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180020940  mov     [rsp+arg_0], rbx
0x180020945  push    rdi
0x180020946  sub     rsp, 20h
0x18002094a  mov     ebx, edx
0x18002094c  mov     rdi, rcx
0x18002094f  call    ??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)
0x180020954  test    bl, 1
0x180020957  jz      short loc_180020966
0x180020959  mov     edx, 20h ; ' '; unsigned __int64
0x18002095e  mov     rcx, rdi; void *
0x180020961  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020966  mov     rbx, [rsp+28h+arg_0]
0x18002096b  mov     rax, rdi
0x18002096e  add     rsp, 20h
0x180020972  pop     rdi
0x180020973  retn
```
