# CCSCShellServiceObject::Stop(void)

- ea: `0x180021cb0`
- end: `0x180021d1a`
- name: `?Stop@CCSCShellServiceObject@@UEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(CCSCShellServiceObject *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180006e30`
- `0x180021cb0`
- `0x18004386c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d04`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021cc2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180021cc2`

## pseudocode

```c
__int64 __fastcall CCSCShellServiceObject::Stop(CCSCShellServiceObject *this)
{
  COfflineFilesEventListener *v2; // rcx
  unsigned int v3; // edx
  void *v4; // rcx

  v2 = (COfflineFilesEventListener *)*((_QWORD *)this - 12);
  if ( v2 )
  {
    CloseServiceHandle((SC_HANDLE)v2);
    *((_QWORD *)this - 12) = 0;
  }
  v3 = *((_DWORD *)this - 59);
  if ( v3 )
  {
    COfflineFilesEventListener::_UnregisterEventSink(v2, v3);
    *((_DWORD *)this - 59) = 0;
    if ( *((_QWORD *)this - 29) )
      SafeRelease<IDataObject>((char *)this - 232);
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 2) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180021cb0  push    rbx
0x180021cb2  sub     rsp, 20h
0x180021cb6  mov     rbx, rcx
0x180021cb9  mov     rcx, [rcx-60h]; hSCObject
0x180021cbd  test    rcx, rcx
0x180021cc0  jz      short loc_180021CD0
0x180021cc2  call    cs:__imp_CloseServiceHandle
0x180021cc8  mov     qword ptr [rbx-60h], 0
0x180021cd0  mov     edx, [rbx-0ECh]; unsigned int
0x180021cd6  test    edx, edx
0x180021cd8  jz      short loc_180021CFB
0x180021cda  call    ?_UnregisterEventSink@COfflineFilesEventListener@@IEAAJK@Z; COfflineFilesEventListener::_UnregisterEventSink(ulong)
0x180021cdf  lea     rcx, [rbx-0E8h]
0x180021ce6  mov     dword ptr [rbx-0ECh], 0
0x180021cf0  cmp     qword ptr [rcx], 0
0x180021cf4  jz      short loc_180021CFB
0x180021cf6  call    ??$SafeRelease@UIDataObject@@@@YAXPEAPEAUIDataObject@@@Z; SafeRelease<IDataObject>(IDataObject * *)
0x180021cfb  mov     rcx, [rbx+10h]; hObject
0x180021cff  test    rcx, rcx
0x180021d02  jz      short loc_180021D12
0x180021d04  call    cs:__imp_CloseHandle
0x180021d0a  mov     qword ptr [rbx+10h], 0
0x180021d12  xor     eax, eax
0x180021d14  add     rsp, 20h
0x180021d18  pop     rbx
0x180021d19  retn
```
