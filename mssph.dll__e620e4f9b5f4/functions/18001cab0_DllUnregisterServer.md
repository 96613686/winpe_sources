# DllUnregisterServer

- ea: `0x18001cab0`
- end: `0x18001cb77`
- name: `DllUnregisterServer`
- size: `199`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007158`
- `0x18000fcd0`
- `0x18001ba7c`
- `0x18001ceb8`
- `0x18001d480`
- `0x18001e9ec`

## string_xrefs

- `0x18001cadc`: `ProtocolHandlers`
- `0x18001cb0c`: `ConfigHelpers`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  const wchar_t *v0; // rdx
  unsigned int v1; // r8d
  int v2; // edx
  ATL::CComModule *v3; // rcx
  const struct _GUID *v4; // r8
  _BYTE v6[192]; // [rsp+20h] [rbp-258h] BYREF
  _BYTE v7[192]; // [rsp+E0h] [rbp-198h] BYREF
  _BYTE v8[192]; // [rsp+1A0h] [rbp-D8h] BYREF

  CSearchRootRegistry::CSearchRootRegistry((CSearchRootRegistry *)v8, v0, v1);
  CRegistry::CRegistry((CRegistry *)v6, (struct CRegistry *)v8, L"ProtocolHandlers", 0xF003Fu);
  CRegistry::DeleteValue((CRegistry *)v6, L"File");
  CRegistry::CRegistry((CRegistry *)v7, (struct CRegistry *)v6, L"ConfigHelpers", 0xF003Fu);
  CRegistry::DeleteValue((CRegistry *)v7, 0);
  ATL::CComModule::UnregisterServer(v3, v2, v4);
  CRegistry::~CRegistry((CRegistry *)v7);
  CRegistry::~CRegistry((CRegistry *)v6);
  CRegistry::~CRegistry((CRegistry *)v8);
  return 0;
}

```

## disassembly

```asm
0x18001cab0  sub     rsp, 278h
0x18001cab7  mov     rax, cs:__security_cookie
0x18001cabe  xor     rax, rsp
0x18001cac1  mov     [rsp+278h+var_18], rax
0x18001cac9  lea     rcx, [rsp+278h+var_D8]; this
0x18001cad1  call    ??0CSearchRootRegistry@@QEAA@PEB_WK@Z; CSearchRootRegistry::CSearchRootRegistry(wchar_t const *,ulong)
0x18001cad6  mov     r9d, 0F003Fh; unsigned int
0x18001cadc  lea     r8, aProtocolhandle; "ProtocolHandlers"
0x18001cae3  lea     rdx, [rsp+278h+var_D8]; struct CRegistry *
0x18001caeb  lea     rcx, [rsp+278h+var_258]; this
0x18001caf0  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x18001caf5  lea     rdx, aFile_0; "File"
0x18001cafc  lea     rcx, [rsp+278h+var_258]; this
0x18001cb01  call    ?DeleteValue@CRegistry@@UEAAHPEB_W@Z; CRegistry::DeleteValue(wchar_t const *)
0x18001cb06  mov     r9d, 0F003Fh; unsigned int
0x18001cb0c  lea     r8, aConfighelpers; "ConfigHelpers"
0x18001cb13  lea     rdx, [rsp+278h+var_258]; struct CRegistry *
0x18001cb18  lea     rcx, [rsp+278h+var_198]; this
0x18001cb20  call    ??0CRegistry@@QEAA@PEAV0@PEB_WK@Z; CRegistry::CRegistry(CRegistry *,wchar_t const *,ulong)
0x18001cb25  xor     edx, edx; wchar_t *
0x18001cb27  lea     rcx, [rsp+278h+var_198]; this
0x18001cb2f  call    ?DeleteValue@CRegistry@@UEAAHPEB_W@Z; CRegistry::DeleteValue(wchar_t const *)
0x18001cb34  call    ?UnregisterServer@CComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CComModule::UnregisterServer(int,_GUID const *)
0x18001cb39  lea     rcx, [rsp+278h+var_198]; this
0x18001cb41  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001cb46  lea     rcx, [rsp+278h+var_258]; this
0x18001cb4b  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001cb50  lea     rcx, [rsp+278h+var_D8]; this
0x18001cb58  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001cb5d  xor     eax, eax
0x18001cb5f  mov     rcx, [rsp+278h+var_18]
0x18001cb67  xor     rcx, rsp; StackCookie
0x18001cb6a  call    __security_check_cookie
0x18001cb6f  add     rsp, 278h
0x18001cb76  retn
```
