# BluetoothConnection::~BluetoothConnection(void)

- ea: `0x180027288`
- end: `0x1800272dc`
- name: `??1BluetoothConnection@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(BluetoothConnection *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800071f4`
- `0x180007a80`

## callees

- `0x180008168`
- `0x180008618`
- `0x180027288`
- `0x1800304b0`
- `0x18003104c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800272af`
- `KERNEL32!CloseHandle` at `0x1800272af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272bc`

## pseudocode

```c
void __fastcall BluetoothConnection::~BluetoothConnection(BluetoothConnection *this)
{
  void *v2; // rcx

  RegSafeCloseKey(*((HKEY *)this + 12));
  SetupDiDestroyDeviceInfoListSafe(*((void **)this + 14));
  v2 = (void *)*((_QWORD *)this + 19);
  if ( v2 )
    CloseHandle(v2);
  CoTaskMemFree(*((LPVOID *)this + 24));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 21);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((BluetoothConnection *)((char *)this + 48));
}

```

## disassembly

```asm
0x180027288  push    rbx
0x18002728a  sub     rsp, 20h
0x18002728e  mov     rbx, rcx
0x180027291  mov     rcx, [rcx+60h]; HKEY
0x180027295  call    ?RegSafeCloseKey@@YAXPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x18002729a  mov     rcx, [rbx+70h]; void *
0x18002729e  call    ?SetupDiDestroyDeviceInfoListSafe@@YAXPEAX@Z; SetupDiDestroyDeviceInfoListSafe(void *)
0x1800272a3  mov     rcx, [rbx+98h]; hObject
0x1800272aa  test    rcx, rcx
0x1800272ad  jz      short loc_1800272B5
0x1800272af  call    cs:__imp_CloseHandle
0x1800272b5  mov     rcx, [rbx+0C0h]; pv
0x1800272bc  call    cs:__imp_CoTaskMemFree
0x1800272c2  lea     rcx, [rbx+0A8h]
0x1800272c9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800272ce  lea     rcx, [rbx+30h]; this
0x1800272d2  add     rsp, 20h
0x1800272d6  pop     rbx
0x1800272d7  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
