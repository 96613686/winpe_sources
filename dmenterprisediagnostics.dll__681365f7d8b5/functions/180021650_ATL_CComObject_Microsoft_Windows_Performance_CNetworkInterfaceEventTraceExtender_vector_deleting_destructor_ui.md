# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180021650`
- end: `0x180021685`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001824`
- `0x180021608`
- `0x180021650`

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
0x180021650  mov     [rsp+arg_0], rbx
0x180021655  push    rdi
0x180021656  sub     rsp, 20h
0x18002165a  mov     ebx, edx
0x18002165c  mov     rdi, rcx
0x18002165f  call    ??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)
0x180021664  test    bl, 1
0x180021667  jz      short loc_180021676
0x180021669  mov     edx, 20h ; ' '; unsigned __int64
0x18002166e  mov     rcx, rdi; void *
0x180021671  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021676  mov     rbx, [rsp+28h+arg_0]
0x18002167b  mov     rax, rdi
0x18002167e  add     rsp, 20h
0x180021682  pop     rdi
0x180021683  retn
```
