# CClients::~CClients(void)

- ea: `0x180009b54`
- end: `0x180009ba7`
- name: `??1CClients@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ae94`

## callees

- `0x180009b24`
- `0x180009b54`
- `0x180009bb0`
- `0x180009c3c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009b81`
- `KERNEL32!DeleteCriticalSection` at `0x180009b81`
- `KERNEL32!CloseHandle` at `0x180009b66`
- `KERNEL32!CloseHandle` at `0x180009b66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009b78`

## pseudocode

```c
void __fastcall CClients::~CClients(CClients *lpCriticalSection)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)lpCriticalSection + 9);
  if ( v2 )
    CloseHandle(v2);
  CClients::DeleteObjects(lpCriticalSection);
  CoTaskMemFree(*((LPVOID *)lpCriticalSection + 6));
  DeleteCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
  ClientNodePtr::~ClientNodePtr((CClients *)((char *)lpCriticalSection + 64));
  ClientNodePtr::~ClientNodePtr((CClients *)((char *)lpCriticalSection + 56));
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((char *)lpCriticalSection + 40);
}

```

## disassembly

```asm
0x180009b54  push    rbx
0x180009b56  sub     rsp, 20h
0x180009b5a  mov     rbx, rcx
0x180009b5d  mov     rcx, [rcx+48h]; hObject
0x180009b61  test    rcx, rcx
0x180009b64  jz      short loc_180009B6C
0x180009b66  call    cs:__imp_CloseHandle
0x180009b6c  mov     rcx, rbx; this
0x180009b6f  call    ?DeleteObjects@CClients@@QEAAXXZ; CClients::DeleteObjects(void)
0x180009b74  mov     rcx, [rbx+30h]; pv
0x180009b78  call    cs:__imp_CoTaskMemFree
0x180009b7e  mov     rcx, rbx; lpCriticalSection
0x180009b81  call    cs:__imp_DeleteCriticalSection
0x180009b87  lea     rcx, [rbx+40h]; this
0x180009b8b  call    ??1ClientNodePtr@@QEAA@XZ; ClientNodePtr::~ClientNodePtr(void)
0x180009b90  lea     rcx, [rbx+38h]; this
0x180009b94  call    ??1ClientNodePtr@@QEAA@XZ; ClientNodePtr::~ClientNodePtr(void)
0x180009b99  lea     rcx, [rbx+28h]
0x180009b9d  add     rsp, 20h
0x180009ba1  pop     rbx
0x180009ba2  jmp     ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
```
