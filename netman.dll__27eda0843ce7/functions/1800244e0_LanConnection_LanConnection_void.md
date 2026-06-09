# LanConnection::~LanConnection(void)

- ea: `0x1800244e0`
- end: `0x180024529`
- name: `??1LanConnection@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(LanConnection *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800074b0`
- `0x180007ddc`

## callees

- `0x180008168`
- `0x180008618`
- `0x1800304b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024509`

## pseudocode

```c
void __fastcall LanConnection::~LanConnection(LanConnection *this)
{
  RegSafeCloseKey(*((HKEY *)this + 11));
  SetupDiDestroyDeviceInfoListSafe(*((void **)this + 13));
  _InterlockedDecrement(&g_CountLanConnectionObjects);
  CoTaskMemFree(*((LPVOID *)this + 21));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 18);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((LanConnection *)((char *)this + 40));
}

```

## disassembly

```asm
0x1800244e0  push    rbx
0x1800244e2  sub     rsp, 20h
0x1800244e6  mov     rbx, rcx
0x1800244e9  mov     rcx, [rcx+58h]; HKEY
0x1800244ed  call    ?RegSafeCloseKey@@YAXPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x1800244f2  mov     rcx, [rbx+68h]; void *
0x1800244f6  call    ?SetupDiDestroyDeviceInfoListSafe@@YAXPEAX@Z; SetupDiDestroyDeviceInfoListSafe(void *)
0x1800244fb  lock dec cs:?g_CountLanConnectionObjects@@3JA; long g_CountLanConnectionObjects
0x180024502  mov     rcx, [rbx+0A8h]; pv
0x180024509  call    cs:__imp_CoTaskMemFree
0x18002450f  lea     rcx, [rbx+90h]
0x180024516  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002451b  lea     rcx, [rbx+28h]; this
0x18002451f  add     rsp, 20h
0x180024523  pop     rbx
0x180024524  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
