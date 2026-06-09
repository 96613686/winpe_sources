# DeviceCert::GetDeviceCertWithRegistryInfo(CertStore &,std::shared_ptr<_CERT_CONTEXT const> &,ILogContext *)

- ea: `0x14002a61c`
- end: `0x14002a722`
- name: `?GetDeviceCertWithRegistryInfo@DeviceCert@@AEAAXAEAVCertStore@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@PEAVILogContext@@@Z`
- size: `262`
- prototype: `LSTATUS __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a520`

## callees

- `0x1400234dc`
- `0x14002a61c`
- `0x14002a728`
- `0x14002b3c8`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a6fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002a6fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a6e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002a6e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002a675`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002a675`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall DeviceCert::GetDeviceCertWithRegistryInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx
  signed __int32 v10; // eax
  bool v11; // cc
  LSTATUS result; // eax
  DWORD LastError; // eax
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-20h] BYREF
  __int64 v16; // [rsp+80h] [rbp+8h] BYREF

  v16 = a1;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeviceRegistration",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0) )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  RegistryKey::GetRegistryString(&hKey, &v16);
  v8 = v16;
  if ( *(_DWORD *)(v16 - 16) )
  {
    DeviceCert::GetDeviceCertWithThumbPrint(v7, a2, a3, v16, a4);
    v8 = v16;
  }
  v9 = (_QWORD *)(v8 - 24);
  v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(v8 - 24 + 16), 0xFFFFFFFF);
  v11 = v10 <= 1;
  result = v10 - 1;
  if ( v11 )
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x14002a61c  mov     r11, rsp
0x14002a61f  mov     [r11+10h], rbx
0x14002a623  mov     [r11+18h], rsi
0x14002a627  mov     [r11+8], rcx
0x14002a62b  push    rdi
0x14002a62c  sub     rsp, 70h
0x14002a630  mov     rbx, r9
0x14002a633  mov     rdi, r8
0x14002a636  mov     rsi, rdx
0x14002a639  mov     qword ptr [r11-38h], 0
0x14002a641  lea     rax, [r11-28h]
0x14002a645  mov     [r11-40h], rax
0x14002a649  mov     qword ptr [r11-48h], 0
0x14002a651  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x14002a659  mov     [rsp+78h+dwOptions], 0; dwOptions
0x14002a661  xor     r9d, r9d; lpClass
0x14002a664  xor     r8d, r8d; Reserved
0x14002a667  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14002a66e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002a675  call    cs:__imp_RegCreateKeyExW
0x14002a67b  test    eax, eax
0x14002a67d  jnz     short loc_14002A6FE
0x14002a67f  lea     rdx, [rsp+78h+arg_0]
0x14002a687  lea     rcx, [rsp+78h+hKey]
0x14002a68c  call    ?GetRegistryString@RegistryKey@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG0@Z; RegistryKey::GetRegistryString(ushort const *,ushort const *)
0x14002a691  nop
0x14002a692  mov     rax, [rsp+78h+arg_0]
0x14002a69a  cmp     dword ptr [rax-10h], 0
0x14002a69e  jz      short loc_14002A6BB
0x14002a6a0  mov     qword ptr [rsp+78h+dwOptions], rbx
0x14002a6a5  mov     r9, rax
0x14002a6a8  mov     r8, rdi
0x14002a6ab  mov     rdx, rsi
0x14002a6ae  call    ?GetDeviceCertWithThumbPrint@DeviceCert@@AEAAXAEAVCertStore@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@PEBGPEAVILogContext@@@Z; DeviceCert::GetDeviceCertWithThumbPrint(CertStore &,std::shared_ptr<_CERT_CONTEXT const> &,ushort const *,ILogContext *)
0x14002a6b3  mov     rax, [rsp+78h+arg_0]
0x14002a6bb  lea     rdx, [rax-18h]
0x14002a6bf  or      eax, 0FFFFFFFFh
0x14002a6c2  lock xadd [rdx+10h], eax
0x14002a6c7  sub     eax, 1
0x14002a6ca  jg      short loc_14002A6DC
0x14002a6cc  mov     rcx, [rdx]
0x14002a6cf  mov     rax, [rcx]
0x14002a6d2  mov     rax, [rax+8]
0x14002a6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a6db  nop
0x14002a6dc  mov     rcx, [rsp+78h+hKey]; hKey
0x14002a6e1  test    rcx, rcx
0x14002a6e4  jz      short loc_14002A6EC
0x14002a6e6  call    cs:__imp_RegCloseKey
0x14002a6ec  lea     r11, [rsp+78h+var_8]
0x14002a6f1  mov     rbx, [r11+18h]
0x14002a6f5  mov     rsi, [r11+20h]
0x14002a6f9  mov     rsp, r11
0x14002a6fc  pop     rdi
0x14002a6fd  retn
0x14002a6fe  call    cs:__imp_GetLastError
0x14002a704  mov     edx, eax; unsigned int
0x14002a706  lea     rcx, [rsp+78h+pExceptionObject]; this
0x14002a70b  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002a710  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002a717  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14002a71c  call    _CxxThrowException_0
```
