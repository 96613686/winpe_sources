# PrinterPnPDataSame(ushort *,ushort *)

- ea: `0x180015a7c`
- end: `0x180015b7e`
- name: `?PrinterPnPDataSame@@YAHPEAG0@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, LPWSTR pPrinterName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800156c4`

## callees

- `0x180002300`
- `0x180015a7c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180015b42`
- `KERNEL32!lstrcmpiW` at `0x180015b42`
- `WINSPOOL!GetPrinterDataExW` at `0x180015b25`
- `WINSPOOL!GetPrinterDataExW` at `0x180015b25`
- `WINSPOOL!OpenPrinterW` at `0x180015ae7`
- `WINSPOOL!OpenPrinterW` at `0x180015ae7`
- `WINSPOOL!ClosePrinter` at `0x180015b53`
- `WINSPOOL!ClosePrinter` at `0x180015b53`

## pseudocode

```c
_BOOL8 __fastcall PrinterPnPDataSame(LPCWSTR lpString2, LPWSTR pPrinterName)
{
  BOOL v2; // ebx
  DWORD pType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbNeeded; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pData[200]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  phPrinter = 0;
  pcbNeeded = 0;
  pType = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  if ( pPrinterName && lpString2 && OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
  {
    if ( !GetPrinterDataExW(phPrinter, L"PnPData", L"DeviceInstanceId", &pType, (LPBYTE)pData, 0x190u, &pcbNeeded)
      && pType == 1 )
    {
      v2 = lstrcmpiW(pData, lpString2) == 0;
    }
    ClosePrinter(phPrinter);
  }
  return v2;
}

```

## disassembly

```asm
0x180015a7c  mov     [rsp-8+arg_10], rbx
0x180015a81  push    rbp
0x180015a82  push    rdi
0x180015a83  push    r14
0x180015a85  lea     rbp, [rsp-110h]
0x180015a8d  sub     rsp, 210h
0x180015a94  mov     rax, cs:__security_cookie
0x180015a9b  xor     rax, rsp
0x180015a9e  mov     [rbp+120h+var_20], rax
0x180015aa5  xor     ebx, ebx
0x180015aa7  mov     qword ptr [rsp+220h+pDefault.DesiredAccess], 0F000Ch
0x180015ab0  mov     [rsp+220h+phPrinter], rbx
0x180015ab5  xorps   xmm0, xmm0
0x180015ab8  mov     [rsp+220h+var_1DC], ebx
0x180015abc  mov     rax, rdx
0x180015abf  mov     [rsp+220h+pType], ebx
0x180015ac3  mov     rdi, rcx
0x180015ac6  movdqu  xmmword ptr [rsp+220h+pDefault.pDatatype], xmm0
0x180015acc  test    rdx, rdx
0x180015acf  jz      loc_180015B59
0x180015ad5  test    rcx, rcx
0x180015ad8  jz      short loc_180015B59
0x180015ada  lea     r8, [rsp+220h+pDefault]; pDefault
0x180015adf  mov     rcx, rax; pPrinterName
0x180015ae2  lea     rdx, [rsp+220h+phPrinter]; phPrinter
0x180015ae7  call    cs:__imp_OpenPrinterW
0x180015aed  test    eax, eax
0x180015aef  jz      short loc_180015B59
0x180015af1  mov     rcx, [rsp+220h+phPrinter]; hPrinter
0x180015af6  lea     rax, [rsp+220h+var_1DC]
0x180015afb  mov     [rsp+220h+pcbNeeded], rax; pcbNeeded
0x180015b00  lea     r9, [rsp+220h+pType]; pType
0x180015b05  lea     rax, [rsp+220h+var_1B0]
0x180015b0a  mov     [rsp+220h+nSize], 190h; nSize
0x180015b12  lea     r8, pValueName; "DeviceInstanceId"
0x180015b19  mov     [rsp+220h+pData], rax; pData
0x180015b1e  lea     rdx, pKeyName; "PnPData"
0x180015b25  call    cs:__imp_GetPrinterDataExW
0x180015b2b  test    eax, eax
0x180015b2d  jnz     short loc_180015B4E
0x180015b2f  lea     r14d, [rbx+1]
0x180015b33  cmp     [rsp+220h+pType], r14d
0x180015b38  jnz     short loc_180015B4E
0x180015b3a  mov     rdx, rdi; lpString2
0x180015b3d  lea     rcx, [rsp+220h+var_1B0]; lpString1
0x180015b42  call    cs:__imp_lstrcmpiW
0x180015b48  test    eax, eax
0x180015b4a  cmovz   ebx, r14d
0x180015b4e  mov     rcx, [rsp+220h+phPrinter]; hPrinter
0x180015b53  call    cs:__imp_ClosePrinter
0x180015b59  mov     eax, ebx
0x180015b5b  mov     rcx, [rbp+120h+var_20]
0x180015b62  xor     rcx, rsp; StackCookie
0x180015b65  call    __security_check_cookie
0x180015b6a  mov     rbx, [rsp+220h+arg_10]
0x180015b72  add     rsp, 210h
0x180015b79  pop     r14
0x180015b7b  pop     rdi
0x180015b7c  pop     rbp
0x180015b7d  retn
```
