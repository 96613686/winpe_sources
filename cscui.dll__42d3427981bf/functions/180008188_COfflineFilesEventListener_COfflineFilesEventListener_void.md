# COfflineFilesEventListener::~COfflineFilesEventListener(void)

- ea: `0x180008188`
- end: `0x1800081f0`
- name: `??1COfflineFilesEventListener@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(COfflineFilesEventListener *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180008130`
- `0x1800435e0`

## callees

- `0x180006500`
- `0x180008188`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800081da`
- `ntdll!RtlDeleteResource` at `0x1800081da`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800081b2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800081b2`

## pseudocode

```c
void __fastcall COfflineFilesEventListener::~COfflineFilesEventListener(COfflineFilesEventListener *this)
{
  SC_HANDLE v2; // rcx
  CRefCounted *v3; // rcx

  *(_QWORD *)this = &COfflineFilesEventListener::`vftable'{for `IOfflineFilesEvents'};
  *((_QWORD *)this + 1) = &COfflineFilesEventListener::`vftable'{for `IOfflineFilesEventsFilter'};
  v2 = (SC_HANDLE)*((_QWORD *)this + 20);
  if ( v2 )
    CloseServiceHandle(v2);
  v3 = (CRefCounted *)*((_QWORD *)this + 4);
  if ( v3 )
    CRefCounted::ReleaseReference(v3);
  _InterlockedDecrement(&g_cRefCount);
  if ( *((_DWORD *)this + 34) )
  {
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 40));
    *((_DWORD *)this + 34) = 0;
  }
}

```

## disassembly

```asm
0x180008188  push    rbx
0x18000818a  sub     rsp, 20h
0x18000818e  lea     rax, ??_7COfflineFilesEventListener@@6BIOfflineFilesEvents@@@; const COfflineFilesEventListener::`vftable'{for `IOfflineFilesEvents'}
0x180008195  mov     rbx, rcx
0x180008198  mov     [rcx], rax
0x18000819b  lea     rax, ??_7COfflineFilesEventListener@@6BIOfflineFilesEventsFilter@@@; const COfflineFilesEventListener::`vftable'{for `IOfflineFilesEventsFilter'}
0x1800081a2  mov     [rcx+8], rax
0x1800081a6  mov     rcx, [rcx+0A0h]; hSCObject
0x1800081ad  test    rcx, rcx
0x1800081b0  jz      short loc_1800081B8
0x1800081b2  call    cs:__imp_CloseServiceHandle
0x1800081b8  mov     rcx, [rbx+20h]; this
0x1800081bc  test    rcx, rcx
0x1800081bf  jz      short loc_1800081C6
0x1800081c1  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x1800081c6  lock dec cs:?g_cRefCount@@3JA; long g_cRefCount
0x1800081cd  cmp     dword ptr [rbx+88h], 0
0x1800081d4  jz      short loc_1800081EA
0x1800081d6  lea     rcx, [rbx+28h]; Resource
0x1800081da  call    cs:__imp_RtlDeleteResource
0x1800081e0  mov     dword ptr [rbx+88h], 0
0x1800081ea  add     rsp, 20h
0x1800081ee  pop     rbx
0x1800081ef  retn
```
