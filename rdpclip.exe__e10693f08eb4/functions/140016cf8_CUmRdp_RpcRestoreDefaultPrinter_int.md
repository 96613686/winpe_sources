# CUmRdp::RpcRestoreDefaultPrinter(int)

- ea: `0x140016cf8`
- end: `0x140016e6d`
- name: `?RpcRestoreDefaultPrinter@CUmRdp@@QEAAIH@Z`
- size: `373`
- prototype: `unsigned int __fastcall(CUmRdp *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400177b0`

## callees

- `0x140016c5c`
- `0x140016cf8`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016e0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016e4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d95`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016d95`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016dd8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140016dd8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016e3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140016e3a`
- `ext-ms-win-printer-winspool-l1-1-4!SetDefaultPrinterW` at `0x140016e24`
- `ext-ms-win-printer-winspool-l1-1-4!SetDefaultPrinterW` at `0x140016e24`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x140016e1b`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x140016e1b`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetDefaultPrinterW` at `0x140016d53`
- `ext-ms-win-printer-winspool-core-l1-1-0!GetDefaultPrinterW` at `0x140016d53`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x140016e02`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x140016e02`

## pseudocode

```c
__int64 __fastcall CUmRdp::RpcRestoreDefaultPrinter(CUmRdp *this, int a2)
{
  DWORD ValueW; // ebx
  WCHAR *v3; // rdi
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcchBuffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-B0h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pvData[528]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszBuffer[264]; // [rsp+280h] [rbp+180h] BYREF

  *(_QWORD *)&pDefault.DesiredAccess = 8;
  hkey = 0;
  phPrinter = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( !a2 )
  {
    pcchBuffer = 261;
    if ( GetDefaultPrinterW(pszBuffer, &pcchBuffer) )
    {
      if ( (unsigned int)PrinterIsServerSide(pszBuffer) )
      {
        ValueW = 0;
        goto LABEL_15;
      }
    }
  }
  ValueW = RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Terminal Server Client\\DefaultPrinter",
             0,
             0x2001Fu,
             &hkey);
  if ( !ValueW )
  {
    pcbData = 520;
    v3 = (WCHAR *)pvData;
    ValueW = RegGetValueW(hkey, 0, L"DefaultPrinterStore", 2u, 0, pvData, &pcbData);
    if ( ValueW )
      v3 = 0;
    if ( v3 && *v3 )
    {
      if ( !OpenPrinterW(v3, &phPrinter, &pDefault) )
      {
        ValueW = GetLastError();
        goto LABEL_15;
      }
      ClosePrinter(phPrinter);
      SetDefaultPrinterW(v3);
    }
    if ( !ValueW )
      RegDeleteValueW(hkey, L"Software\\Microsoft\\Terminal Server Client\\DefaultPrinter");
  }
LABEL_15:
  if ( hkey )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x140016cf8  push    rbp
0x140016cfa  push    rbx
0x140016cfb  push    rsi
0x140016cfc  push    rdi
0x140016cfd  lea     rbp, [rsp-3A8h]
0x140016d05  sub     rsp, 4A8h
0x140016d0c  mov     rax, cs:__security_cookie
0x140016d13  xor     rax, rsp
0x140016d16  mov     [rbp+3C0h+var_30], rax
0x140016d1d  xor     esi, esi
0x140016d1f  mov     qword ptr [rsp+4C0h+pDefault.DesiredAccess], 8
0x140016d28  mov     [rsp+4C0h+hkey], rsi
0x140016d2d  xorps   xmm0, xmm0
0x140016d30  mov     [rsp+4C0h+phPrinter], rsi
0x140016d35  movdqu  xmmword ptr [rsp+4C0h+pDefault.pDatatype], xmm0
0x140016d3b  test    edx, edx
0x140016d3d  jnz     short loc_140016D74
0x140016d3f  lea     rdx, [rsp+4C0h+pcchBuffer]; pcchBuffer
0x140016d44  mov     [rsp+4C0h+pcchBuffer], 105h
0x140016d4c  lea     rcx, [rbp+3C0h+pszBuffer]; pszBuffer
0x140016d53  call    cs:__imp_GetDefaultPrinterW
0x140016d59  test    eax, eax
0x140016d5b  jz      short loc_140016D74
0x140016d5d  lea     rcx, [rbp+3C0h+pszBuffer]; unsigned __int16 *
0x140016d64  call    ?PrinterIsServerSide@@YAHPEAG@Z; PrinterIsServerSide(ushort *)
0x140016d69  test    eax, eax
0x140016d6b  jz      short loc_140016D74
0x140016d6d  mov     ebx, esi
0x140016d6f  jmp     loc_140016E40
0x140016d74  lea     rax, [rsp+4C0h+hkey]
0x140016d79  mov     r9d, 2001Fh; samDesired
0x140016d7f  xor     r8d, r8d; ulOptions
0x140016d82  mov     [rsp+4C0h+phkResult], rax; phkResult
0x140016d87  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Terminal Server Cl"...
0x140016d8e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140016d95  call    cs:__imp_RegOpenKeyExW
0x140016d9b  mov     ebx, eax
0x140016d9d  test    eax, eax
0x140016d9f  jnz     loc_140016E40
0x140016da5  mov     rcx, [rsp+4C0h+hkey]; hkey
0x140016daa  lea     rax, [rsp+4C0h+var_474]
0x140016daf  mov     [rsp+4C0h+pcbData], rax; pcbData
0x140016db4  lea     r9d, [rbx+2]; dwFlags
0x140016db8  lea     rax, [rsp+4C0h+var_450]
0x140016dbd  mov     [rsp+4C0h+var_474], 208h
0x140016dc5  mov     [rsp+4C0h+pvData], rax; pvData
0x140016dca  lea     r8, aDefaultprinter; "DefaultPrinterStore"
0x140016dd1  xor     edx, edx; lpSubKey
0x140016dd3  mov     [rsp+4C0h+phkResult], rsi; pdwType
0x140016dd8  call    cs:__imp_RegGetValueW
0x140016dde  test    eax, eax
0x140016de0  lea     rdi, [rsp+4C0h+var_450]
0x140016de5  mov     ebx, eax
0x140016de7  cmovnz  rdi, rsi
0x140016deb  test    rdi, rdi
0x140016dee  jz      short loc_140016E2A
0x140016df0  cmp     [rdi], si
0x140016df3  jz      short loc_140016E2A
0x140016df5  lea     r8, [rsp+4C0h+pDefault]; pDefault
0x140016dfa  mov     rcx, rdi; pPrinterName
0x140016dfd  lea     rdx, [rsp+4C0h+phPrinter]; phPrinter
0x140016e02  call    cs:__imp_OpenPrinterW
0x140016e08  test    eax, eax
0x140016e0a  jnz     short loc_140016E16
0x140016e0c  call    cs:__imp_GetLastError
0x140016e12  mov     ebx, eax
0x140016e14  jmp     short loc_140016E40
0x140016e16  mov     rcx, [rsp+4C0h+phPrinter]; hPrinter
0x140016e1b  call    cs:__imp_ClosePrinter
0x140016e21  mov     rcx, rdi; pszPrinter
0x140016e24  call    cs:__imp_SetDefaultPrinterW
0x140016e2a  test    ebx, ebx
0x140016e2c  jnz     short loc_140016E40
0x140016e2e  mov     rcx, [rsp+4C0h+hkey]; hKey
0x140016e33  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Terminal Server Cl"...
0x140016e3a  call    cs:__imp_RegDeleteValueW
0x140016e40  mov     rcx, [rsp+4C0h+hkey]; hKey
0x140016e45  test    rcx, rcx
0x140016e48  jz      short loc_140016E50
0x140016e4a  call    cs:__imp_RegCloseKey
0x140016e50  mov     eax, ebx
0x140016e52  mov     rcx, [rbp+3C0h+var_30]
0x140016e59  xor     rcx, rsp; StackCookie
0x140016e5c  call    __security_check_cookie
0x140016e61  add     rsp, 4A8h
0x140016e68  pop     rdi
0x140016e69  pop     rsi
0x140016e6a  pop     rbx
0x140016e6b  pop     rbp
0x140016e6c  retn
```
