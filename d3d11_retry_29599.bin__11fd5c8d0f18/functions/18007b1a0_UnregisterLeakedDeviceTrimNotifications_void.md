# UnregisterLeakedDeviceTrimNotifications(void)

- ea: `0x18007b1a0`
- end: `0x18007b1ff`
- name: `?UnregisterLeakedDeviceTrimNotifications@@YAXXZ`
- size: `95`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007ae80`

## callees

- `0x18007b1a0`
- `0x1801cb010`

## import_xrefs

- `ntdll!RtlDllShutdownInProgress` at `0x18007b1bb`
- `ntdll!RtlDllShutdownInProgress` at `0x18007b1bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18007b1ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18007b1ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b1cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007b1cf`

## string_xrefs

- `0x18007b1a6`: `gdi32.dll`

## pseudocode

```c
void UnregisterLeakedDeviceTrimNotifications(void)
{
  HMODULE ModuleHandleA; // rbx
  FARPROC ProcAddress; // rax
  _QWORD v2[3]; // [rsp+20h] [rbp-18h] BYREF

  ModuleHandleA = GetModuleHandleA("gdi32.dll");
  if ( ModuleHandleA && !RtlDllShutdownInProgress() )
  {
    ProcAddress = GetProcAddress(ModuleHandleA, "D3DKMTUnregisterTrimNotification");
    if ( ProcAddress )
    {
      v2[0] = 0;
      v2[1] = NDXGI::CDevice::TrimNotificationCallback;
      ((void (__fastcall *)(_QWORD *))ProcAddress)(v2);
    }
  }
}

```

## disassembly

```asm
0x18007b1a0  push    rbx
0x18007b1a2  sub     rsp, 30h
0x18007b1a6  lea     rcx, aGdi32Dll; "gdi32.dll"
0x18007b1ad  call    cs:__imp_GetModuleHandleA
0x18007b1b3  mov     rbx, rax
0x18007b1b6  test    rax, rax
0x18007b1b9  jz      short loc_18007B1F9
0x18007b1bb  call    cs:__imp_RtlDllShutdownInProgress
0x18007b1c1  test    al, al
0x18007b1c3  jnz     short loc_18007B1F9
0x18007b1c5  lea     rdx, aD3dkmtunregist; "D3DKMTUnregisterTrimNotification"
0x18007b1cc  mov     rcx, rbx; hModule
0x18007b1cf  call    cs:__imp_GetProcAddress
0x18007b1d5  test    rax, rax
0x18007b1d8  jz      short loc_18007B1F9
0x18007b1da  lea     rcx, ?TrimNotificationCallback@CDevice@NDXGI@@SAXPEAU_D3DKMT_TRIMNOTIFICATION@@@Z; NDXGI::CDevice::TrimNotificationCallback(_D3DKMT_TRIMNOTIFICATION *)
0x18007b1e1  mov     [rsp+38h+var_18], 0
0x18007b1ea  mov     [rsp+38h+var_10], rcx
0x18007b1ef  lea     rcx, [rsp+38h+var_18]
0x18007b1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b1f9  add     rsp, 30h
0x18007b1fd  pop     rbx
0x18007b1fe  retn
```
