# CheckServicesRegistryEntry

- ea: `0x180061e38`
- end: `0x180061f46`
- name: `CheckServicesRegistryEntry`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180029228`

## callees

- `0x18002b42c`
- `0x18002bccc`
- `0x180061e38`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180061edc`
- `ADVAPI32!RegQueryValueExW` at `0x180061f17`
- `ADVAPI32!RegQueryValueExW` at `0x180061edc`
- `ADVAPI32!RegQueryValueExW` at `0x180061f17`
- `ole32!CoTaskMemFree` at `0x180061f2c`
- `ole32!CoTaskMemFree` at `0x180061f2c`
- `ole32!StringFromCLSID` at `0x180061e70`
- `ole32!StringFromCLSID` at `0x180061e70`

## string_xrefs

- `0x180061e7e`: `CLSID`
- `0x180061ebd`: `OLEDB_SERVICES`

## pseudocode

```c
char __fastcall CheckServicesRegistryEntry(const IID *a1, BYTE *a2, DWORD *a3)
{
  char v5; // bl
  unsigned int v6; // r9d
  unsigned int v7; // r9d
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  DWORD v10; // [rsp+34h] [rbp-34h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-30h] BYREF
  HKEY hKey[5]; // [rsp+40h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+40h] BYREF

  lpsz = 0;
  memset(hKey, 0, 24);
  v5 = 0;
  if ( StringFromCLSID(a1, &lpsz) >= 0
    && !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID", v6)
    && !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, hKey[0], lpsz, v7) )
  {
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"OLEDB_SERVICES", 0, &Type, a2, &cbData) )
    {
      cbData = 0;
      v10 = 0;
      Type = 4;
      if ( !RegQueryValueExW(hKey[0], L"SPTimeOut", 0, &v10, (LPBYTE)&cbData, &Type) )
        *a3 = cbData;
      v5 = 1;
    }
  }
  CoTaskMemFree(lpsz);
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v5;
}

```

## disassembly

```asm
0x180061e38  push    rbp
0x180061e3a  push    rbx
0x180061e3b  push    rsi
0x180061e3c  push    rdi
0x180061e3d  mov     rbp, rsp
0x180061e40  sub     rsp, 68h
0x180061e44  mov     rsi, rdx
0x180061e47  mov     [rbp+lpsz], 0
0x180061e4f  lea     rdx, [rbp+lpsz]; lplpsz
0x180061e53  mov     [rbp+hKey], 0
0x180061e5b  mov     rdi, r8
0x180061e5e  mov     [rbp+var_20], 0
0x180061e66  xor     bl, bl
0x180061e68  mov     [rbp+var_18], 0
0x180061e70  call    cs:__imp_StringFromCLSID
0x180061e76  test    eax, eax
0x180061e78  js      loc_180061F28
0x180061e7e  lea     r8, aClsid_0; "CLSID"
0x180061e85  mov     rdx, 0FFFFFFFF80000000h; hKey
0x180061e8c  lea     rcx, [rbp+hKey]; this
0x180061e90  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180061e95  test    eax, eax
0x180061e97  jnz     loc_180061F28
0x180061e9d  mov     r8, [rbp+lpsz]; lpSubKey
0x180061ea1  lea     rcx, [rbp+hKey]; this
0x180061ea5  mov     rdx, [rbp+hKey]; hKey
0x180061ea9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180061eae  test    eax, eax
0x180061eb0  jnz     short loc_180061F28
0x180061eb2  mov     rcx, [rbp+hKey]; hKey
0x180061eb6  lea     r9, [rbp+Type]; lpType
0x180061eba  mov     [rbp+Type], eax
0x180061ebd  lea     rdx, aOledbServices; "OLEDB_SERVICES"
0x180061ec4  lea     rax, [rbp+cbData]
0x180061ec8  mov     [rbp+cbData], 4
0x180061ecf  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180061ed4  xor     r8d, r8d; lpReserved
0x180061ed7  mov     [rsp+68h+lpData], rsi; lpData
0x180061edc  call    cs:__imp_RegQueryValueExW
0x180061ee2  test    eax, eax
0x180061ee4  jnz     short loc_180061F28
0x180061ee6  mov     rcx, [rbp+hKey]; hKey
0x180061eea  lea     r9, [rbp+var_34]; lpType
0x180061eee  mov     [rbp+cbData], eax
0x180061ef1  lea     rdx, aSptimeout; "SPTimeOut"
0x180061ef8  mov     [rbp+var_34], eax
0x180061efb  xor     r8d, r8d; lpReserved
0x180061efe  lea     rax, [rbp+Type]
0x180061f02  mov     [rbp+Type], 4
0x180061f09  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180061f0e  lea     rax, [rbp+cbData]
0x180061f12  mov     [rsp+68h+lpData], rax; lpData
0x180061f17  call    cs:__imp_RegQueryValueExW
0x180061f1d  test    eax, eax
0x180061f1f  jnz     short loc_180061F26
0x180061f21  mov     eax, [rbp+cbData]
0x180061f24  mov     [rdi], eax
0x180061f26  mov     bl, 1
0x180061f28  mov     rcx, [rbp+lpsz]; pv
0x180061f2c  call    cs:__imp_CoTaskMemFree
0x180061f32  lea     rcx, [rbp+hKey]; this
0x180061f36  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180061f3b  mov     al, bl
0x180061f3d  add     rsp, 68h
0x180061f41  pop     rdi
0x180061f42  pop     rsi
0x180061f43  pop     rbx
0x180061f44  pop     rbp
0x180061f45  retn
```
