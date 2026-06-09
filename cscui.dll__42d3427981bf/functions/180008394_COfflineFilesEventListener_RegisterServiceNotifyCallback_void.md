# COfflineFilesEventListener::_RegisterServiceNotifyCallback(void)

- ea: `0x180008394`
- end: `0x180008422`
- name: `?_RegisterServiceNotifyCallback@COfflineFilesEventListener@@IEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(COfflineFilesEventListener *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005e80`
- `0x180006e60`

## callees

- `0x180008394`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800083f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800083f2`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800083d8`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800083d8`

## pseudocode

```c
__int64 __fastcall COfflineFilesEventListener::_RegisterServiceNotifyCallback(COfflineFilesEventListener *this)
{
  DWORD v1; // edx
  SERVICE_NOTIFY_2W *v2; // r8
  SC_HANDLE v4; // rcx
  unsigned int v5; // ebx
  signed int v6; // eax
  unsigned __int16 v7; // di

  v1 = *((_DWORD *)this + 62);
  v2 = (SERVICE_NOTIFY_2W *)((char *)this + 168);
  *((_QWORD *)this + 23) = this;
  *((_QWORD *)this + 22) = COfflineFilesEventListener::_ServiceNotifyCallback;
  v4 = (SC_HANDLE)*((_QWORD *)this + 20);
  v5 = 0;
  v2->dwVersion = 2;
  v6 = NotifyServiceStatusChangeW(v4, v1, v2);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 == 1072 )
    {
      CloseServiceHandle(*((SC_HANDLE *)this + 20));
      *((_QWORD *)this + 20) = 0;
    }
    else if ( v6 <= 0 )
    {
      return (unsigned int)v6;
    }
    return v7 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180008394  mov     [rsp+arg_0], rbx
0x180008399  mov     [rsp+arg_8], rsi
0x18000839e  push    rdi
0x18000839f  sub     rsp, 20h
0x1800083a3  mov     edx, [rcx+0F8h]; dwNotifyMask
0x1800083a9  lea     r8, [rcx+0A8h]; pNotifyBuffer
0x1800083b0  lea     rax, ?_ServiceNotifyCallback@COfflineFilesEventListener@@CAXPEAX@Z; COfflineFilesEventListener::_ServiceNotifyCallback(void *)
0x1800083b7  mov     [rcx+0B8h], rcx
0x1800083be  mov     [rcx+0B0h], rax
0x1800083c5  mov     rsi, rcx
0x1800083c8  mov     rcx, [rcx+0A0h]; hService
0x1800083cf  xor     ebx, ebx
0x1800083d1  mov     dword ptr [r8], 2
0x1800083d8  call    cs:__imp_NotifyServiceStatusChangeW
0x1800083de  mov     edi, eax
0x1800083e0  test    eax, eax
0x1800083e2  jz      short loc_180008408
0x1800083e4  cmp     eax, 430h
0x1800083e9  jnz     short loc_18000841A
0x1800083eb  mov     rcx, [rsi+0A0h]; hSCObject
0x1800083f2  call    cs:__imp_CloseServiceHandle
0x1800083f8  mov     [rsi+0A0h], rbx
0x1800083ff  movzx   ebx, di
0x180008402  or      ebx, 80070000h
0x180008408  mov     rsi, [rsp+28h+arg_8]
0x18000840d  mov     eax, ebx
0x18000840f  mov     rbx, [rsp+28h+arg_0]
0x180008414  add     rsp, 20h
0x180008418  pop     rdi
0x180008419  retn
0x18000841a  test    edi, edi
0x18000841c  jg      short loc_1800083FF
0x18000841e  mov     ebx, edi
0x180008420  jmp     short loc_180008408
```
