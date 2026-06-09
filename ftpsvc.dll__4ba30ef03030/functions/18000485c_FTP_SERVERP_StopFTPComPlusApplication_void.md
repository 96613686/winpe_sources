# FTP_SERVERP::StopFTPComPlusApplication(void)

- ea: `0x18000485c`
- end: `0x180004978`
- name: `?StopFTPComPlusApplication@FTP_SERVERP@@AEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(FTP_SERVERP *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a18`

## callees

- `0x18000485c`
- `0x180049010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004890`
- `ole32!CoCreateInstance` at `0x180004890`
- `OLEAUT32!__imp_SysAllocString` at `0x1800048e3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800048e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000494f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000494f`
- `iisutil!PuDbgPrintError` at `0x1800048d4`
- `iisutil!PuDbgPrintError` at `0x180004946`
- `iisutil!PuDbgPrintError` at `0x1800048d4`
- `iisutil!PuDbgPrintError` at `0x180004946`

## string_xrefs

- `0x1800048b0`: `Failed to CoCreateInstance of Catalog Object.`
- `0x1800048bc`: `FTP_SERVERP::StopFTPComPlusApplication`
- `0x18000492e`: `FTP_SERVERP::StopFTPComPlusApplication`

## pseudocode

```c
__int64 __fastcall FTP_SERVERP::StopFTPComPlusApplication(FTP_SERVERP *this)
{
  HRESULT v1; // ebx
  BSTR v2; // rax
  OLECHAR *v3; // rdi
  LPVOID v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v1 = CoCreateInstance(&CLSID_COMAdminCatalog, 0, 0x15u, &IID_ICOMAdminCatalog, &v5);
  if ( v1 >= 0 )
  {
    v2 = SysAllocString(L"{5268ca1b-44ff-4fe6-9d5f-9cf63f69c4e3}");
    v3 = v2;
    if ( v2 )
    {
      v1 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v5 + 112LL))(v5, v2);
      if ( v1 < 0 && (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
          1669,
          "FTP_SERVERP::StopFTPComPlusApplication",
          v1,
          "m_pCatalog->ShutdownApplication() failed.");
      SysFreeString(v3);
    }
    else
    {
      v1 = -2147024888;
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_serverp.cxx",
      1647,
      "FTP_SERVERP::StopFTPComPlusApplication",
      v1,
      "Failed to CoCreateInstance of Catalog Object.");
  }
  if ( v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000485c  mov     r11, rsp
0x18000485f  mov     [r11+10h], rbx
0x180004863  mov     [r11+8], rcx
0x180004867  push    rdi
0x180004868  sub     rsp, 30h
0x18000486c  xor     edx, edx; pUnkOuter
0x18000486e  mov     qword ptr [r11+8], 0
0x180004876  lea     rax, [r11+8]
0x18000487a  lea     r9, IID_ICOMAdminCatalog; riid
0x180004881  mov     [r11-18h], rax
0x180004885  lea     rcx, CLSID_COMAdminCatalog; rclsid
0x18000488c  lea     r8d, [rdx+15h]; dwClsContext
0x180004890  call    cs:__imp_CoCreateInstance
0x180004896  mov     ebx, eax
0x180004898  test    eax, eax
0x18000489a  jns     short loc_1800048DC
0x18000489c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800048a3  jz      loc_180004955
0x1800048a9  mov     rcx, cs:g_pDebug
0x1800048b0  lea     rax, aFailedToCocrea; "Failed to CoCreateInstance of Catalog O"...
0x1800048b7  mov     [rsp+38h+var_10], rax
0x1800048bc  lea     r9, aFtpServerpStop; "FTP_SERVERP::StopFTPComPlusApplication"
0x1800048c3  mov     r8d, 66Fh
0x1800048c9  mov     [rsp+38h+var_18], ebx
0x1800048cd  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x1800048d4  call    cs:__imp_PuDbgPrintError
0x1800048da  jmp     short loc_180004955
0x1800048dc  lea     rcx, a5268ca1b44ff4f; "{5268ca1b-44ff-4fe6-9d5f-9cf63f69c4e3}"
0x1800048e3  call    cs:__imp_SysAllocString
0x1800048e9  mov     rdi, rax
0x1800048ec  test    rax, rax
0x1800048ef  jnz     short loc_1800048F8
0x1800048f1  mov     ebx, 80070008h
0x1800048f6  jmp     short loc_180004955
0x1800048f8  mov     rcx, [rsp+38h+arg_0]
0x1800048fd  mov     rdx, rdi
0x180004900  mov     rax, [rcx]
0x180004903  mov     rax, [rax+70h]
0x180004907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490c  mov     ebx, eax
0x18000490e  test    eax, eax
0x180004910  jns     short loc_18000494C
0x180004912  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004919  jz      short loc_18000494C
0x18000491b  mov     rcx, cs:g_pDebug
0x180004922  lea     rax, aMPcatalogShutd; "m_pCatalog->ShutdownApplication() faile"...
0x180004929  mov     [rsp+38h+var_10], rax
0x18000492e  lea     r9, aFtpServerpStop; "FTP_SERVERP::StopFTPComPlusApplication"
0x180004935  mov     r8d, 685h
0x18000493b  mov     [rsp+38h+var_18], ebx
0x18000493f  lea     rdx, aInetsrvIisIisr_23; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180004946  call    cs:__imp_PuDbgPrintError
0x18000494c  mov     rcx, rdi; bstrString
0x18000494f  call    cs:__imp_SysFreeString
0x180004955  mov     rcx, [rsp+38h+arg_0]
0x18000495a  test    rcx, rcx
0x18000495d  jz      short loc_18000496B
0x18000495f  mov     rax, [rcx]
0x180004962  mov     rax, [rax+10h]
0x180004966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496b  mov     eax, ebx
0x18000496d  mov     rbx, [rsp+38h+arg_8]
0x180004972  add     rsp, 30h
0x180004976  pop     rdi
0x180004977  retn
```
