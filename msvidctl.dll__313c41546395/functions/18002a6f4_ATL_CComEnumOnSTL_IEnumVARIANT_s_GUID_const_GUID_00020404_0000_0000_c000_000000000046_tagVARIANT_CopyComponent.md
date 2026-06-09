# ATL::CComEnumOnSTL<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046,tagVARIANT,CopyComponentToVARIANT,std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>,std::allocator<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>>,ATL::CComMultiThreadModel>::~CComEnumOnSTL<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046,tagVARIANT,CopyComponentToVARIANT,std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>,std::allocator<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>>,ATL::CComMultiThreadModel>(void)

- ea: `0x18002a6f4`
- end: `0x18002a71f`
- name: `??1?$CComEnumOnSTL@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@BUtagVARIANT@@VCopyComponentToVARIANT@@V?$vector@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@V?$allocator@V?$CComQIPtr@UIComponent@@$1?_GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980@@3U__s_GUID@@B@ATL@@@std@@@std@@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002a728`
- `0x18002a74c`
- `0x180032b84`
- `0x180032ba8`
- `0x180038bdc`
- `0x180038c00`
- `0x180085b38`

## callees

- `0x180006b38`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002a701`
- `KERNEL32!DeleteCriticalSection` at `0x18002a70b`
- `KERNEL32!DeleteCriticalSection` at `0x18002a701`
- `KERNEL32!DeleteCriticalSection` at `0x18002a70b`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumOnSTL<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046,tagVARIANT,CopyComponentToVARIANT,std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>,ATL::CComMultiThreadModel>::~CComEnumOnSTL<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046,tagVARIANT,CopyComponentToVARIANT,std::vector<ATL::CComQIPtr<IComponent,&__s_GUID const _GUID_1a5576fc_0e19_11d3_9d8e_00c04f72d980>>,ATL::CComMultiThreadModel>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  DeleteCriticalSection(a1 + 2);
  DeleteCriticalSection(a1 + 1);
  return ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&a1->LockCount);
}

```

## disassembly

```asm
0x18002a6f4  push    rbx
0x18002a6f6  sub     rsp, 20h
0x18002a6fa  mov     rbx, rcx
0x18002a6fd  add     rcx, 50h ; 'P'; lpCriticalSection
0x18002a701  call    cs:__imp_DeleteCriticalSection
0x18002a707  lea     rcx, [rbx+28h]; lpCriticalSection
0x18002a70b  call    cs:__imp_DeleteCriticalSection
0x18002a711  lea     rcx, [rbx+8]
0x18002a715  add     rsp, 20h
0x18002a719  pop     rbx
0x18002a71a  jmp     ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
```
