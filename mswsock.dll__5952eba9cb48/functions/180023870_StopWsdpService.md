# StopWsdpService

- ea: `0x180023870`
- end: `0x1800238c4`
- name: `StopWsdpService`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x180023870`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800238a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800238a5`
- `WS2_32!__imp_WSACleanup` at `0x1800238b1`
- `WS2_32!__imp_WSACleanup` at `0x1800238b1`

## pseudocode

```c
int StopWsdpService()
{
  HANDLE v0; // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int result; // eax

  SockAcquireRwLockExclusive();
  v0 = SockSanProviderChangeHandle;
  SockSanProviderChangeHandle = 0;
  SockSanServiceHelper = 0;
  result = SockReleaseRwLockExclusive(v2, v1, v3, v4);
  if ( v0 )
  {
    CloseHandle(v0);
    return WSACleanup();
  }
  return result;
}

```

## disassembly

```asm
0x180023870  push    rbx
0x180023872  sub     rsp, 20h
0x180023876  call    SockAcquireRwLockExclusive
0x18002387b  mov     rbx, cs:SockSanProviderChangeHandle
0x180023882  mov     cs:SockSanProviderChangeHandle, 0
0x18002388d  mov     cs:SockSanServiceHelper, 0
0x180023898  call    SockReleaseRwLockExclusive
0x18002389d  test    rbx, rbx
0x1800238a0  jz      short loc_1800238BD
0x1800238a2  mov     rcx, rbx; hObject
0x1800238a5  call    cs:__imp_CloseHandle
0x1800238ac  nop     dword ptr [rax+rax+00h]
0x1800238b1  call    cs:__imp_WSACleanup
0x1800238b8  nop     dword ptr [rax+rax+00h]
0x1800238bd  add     rsp, 20h
0x1800238c1  pop     rbx
0x1800238c2  retn
```
