# CPnpRebootHandler::Worker(void)

- ea: `0x18000c350`
- end: `0x18000c439`
- name: `?Worker@CPnpRebootHandler@@EEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CPnpRebootHandler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000b868`
- `0x18000c350`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c36f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000c36f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c427`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000c427`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c39c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c39c`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x18000c359`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x18000c359`

## pseudocode

```c
__int64 __fastcall CPnpRebootHandler::Worker(CPnpRebootHandler *this)
{
  int v1; // ebx
  __int64 v3; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  CMP_WaitNoPendingInstallEvents(0xFFFFFFFF);
  v1 = 0;
  ppv = 0;
  v3 = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    v1 = 1;
    if ( CoCreateInstance(
           &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
           0,
           4u,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           &ppv) >= 0
      && (*(int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v3) >= 0 )
    {
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)v3 + 80LL))(
        v3,
        L"NonImmersivePackage",
        L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel",
        0,
        L"DeviceNeedsReboot",
        0);
    }
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v1 )
    CoUninitialize();
  return NotifyDevicesNeedReboot(0);
}

```

## disassembly

```asm
0x18000c350  push    rbx
0x18000c352  sub     rsp, 40h
0x18000c356  or      ecx, 0FFFFFFFFh; dwTimeout
0x18000c359  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x18000c35f  xor     ebx, ebx
0x18000c361  xor     edx, edx; dwCoInit
0x18000c363  xor     ecx, ecx; pvReserved
0x18000c365  mov     [rsp+48h+arg_10], rbx
0x18000c36a  mov     [rsp+48h+arg_8], rbx
0x18000c36f  call    cs:__imp_CoInitializeEx
0x18000c375  test    eax, eax
0x18000c377  js      short loc_18000C3F7
0x18000c379  lea     rax, [rsp+48h+arg_10]
0x18000c37e  mov     ebx, 1
0x18000c383  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18000c38a  mov     [rsp+48h+ppv], rax; ppv
0x18000c38f  xor     edx, edx; pUnkOuter
0x18000c391  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000c398  lea     r8d, [rbx+3]; dwClsContext
0x18000c39c  call    cs:__imp_CoCreateInstance
0x18000c3a2  test    eax, eax
0x18000c3a4  js      short loc_18000C3F7
0x18000c3a6  mov     rcx, [rsp+48h+arg_10]
0x18000c3ab  lea     rdx, [rsp+48h+arg_8]
0x18000c3b0  mov     rax, [rcx]
0x18000c3b3  mov     rax, [rax+18h]
0x18000c3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3bc  test    eax, eax
0x18000c3be  js      short loc_18000C3F7
0x18000c3c0  mov     rcx, [rsp+48h+arg_8]
0x18000c3c5  lea     rdx, aDeviceneedsreb; "DeviceNeedsReboot"
0x18000c3cc  mov     [rsp+48h+var_20], 0
0x18000c3d5  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x18000c3dc  mov     [rsp+48h+ppv], rdx
0x18000c3e1  xor     r9d, r9d
0x18000c3e4  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x18000c3eb  mov     rax, [rcx]
0x18000c3ee  mov     rax, [rax+50h]
0x18000c3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f7  mov     rcx, [rsp+48h+arg_8]
0x18000c3fc  test    rcx, rcx
0x18000c3ff  jz      short loc_18000C40D
0x18000c401  mov     rax, [rcx]
0x18000c404  mov     rax, [rax+10h]
0x18000c408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c40d  mov     rcx, [rsp+48h+arg_10]
0x18000c412  test    rcx, rcx
0x18000c415  jz      short loc_18000C423
0x18000c417  mov     rax, [rcx]
0x18000c41a  mov     rax, [rax+10h]
0x18000c41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c423  test    ebx, ebx
0x18000c425  jz      short loc_18000C42D
0x18000c427  call    cs:__imp_CoUninitialize
0x18000c42d  xor     ecx, ecx; int
0x18000c42f  add     rsp, 40h
0x18000c433  pop     rbx
0x18000c434  jmp     ?NotifyDevicesNeedReboot@@YAJH@Z; NotifyDevicesNeedReboot(int)
```
