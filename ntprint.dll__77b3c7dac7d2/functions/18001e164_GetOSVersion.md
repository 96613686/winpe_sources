# GetOSVersion

- ea: `0x18001e164`
- end: `0x18001e25e`
- name: `GetOSVersion`
- size: `250`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, PRTL_OSVERSIONINFOW lpVersionInformation)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000db80`
- `0x18001c680`
- `0x1800204e0`
- `0x180020660`
- `0x180027e90`
- `0x1800288a0`

## callees

- `0x180002f48`
- `0x18001e164`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x18001e245`
- `ntdll!RtlGetVersion` at `0x18001e245`
- `WINSPOOL!GetPrinterDataW` at `0x18001e208`
- `WINSPOOL!GetPrinterDataW` at `0x18001e208`
- `WINSPOOL!OpenPrinterW` at `0x18001e1db`
- `WINSPOOL!OpenPrinterW` at `0x18001e1db`
- `WINSPOOL!ClosePrinter` at `0x18001e23a`
- `WINSPOOL!ClosePrinter` at `0x18001e23a`

## pseudocode

```c
__int64 __fastcall GetOSVersion(LPWSTR pPrinterName, BYTE *lpVersionInformation)
{
  unsigned int v4; // edi
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-20h] BYREF
  DWORD pcbNeeded; // [rsp+88h] [rbp+38h] BYREF
  DWORD pType; // [rsp+90h] [rbp+40h] BYREF
  HANDLE phPrinter; // [rsp+98h] [rbp+48h] BYREF

  v4 = 0;
  if ( lpVersionInformation )
  {
    memset_0(lpVersionInformation + 4, 0, 0x110u);
    *(_DWORD *)lpVersionInformation = 276;
    if ( pPrinterName && *pPrinterName )
    {
      phPrinter = 0;
      pcbNeeded = 0;
      pType = 3;
      *(_QWORD *)&pDefault.DesiredAccess = 131074;
      *(_OWORD *)&pDefault.pDatatype = 0;
      if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
      {
        if ( GetPrinterDataW(phPrinter, (LPWSTR)L"OSVersion", &pType, lpVersionInformation, 0x114u, &pcbNeeded) )
        {
          memset_0(lpVersionInformation + 12, 0, 0x108u);
          *(_DWORD *)lpVersionInformation = 276;
          *(_QWORD *)(lpVersionInformation + 4) = 4;
        }
        v4 = 1;
        ClosePrinter(phPrinter);
      }
    }
    else
    {
      LOBYTE(v4) = RtlGetVersion((PRTL_OSVERSIONINFOW)lpVersionInformation) >= 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001e164  push    rbp
0x18001e166  push    rbx
0x18001e167  push    rsi
0x18001e168  push    rdi
0x18001e169  push    r14
0x18001e16b  mov     rbp, rsp
0x18001e16e  sub     rsp, 50h
0x18001e172  xor     r14d, r14d
0x18001e175  mov     rbx, rdx
0x18001e178  mov     rsi, rcx
0x18001e17b  mov     edi, r14d
0x18001e17e  test    rdx, rdx
0x18001e181  jz      loc_18001E251
0x18001e187  lea     rcx, [rdx+4]; void *
0x18001e18b  mov     r8d, 110h; Size
0x18001e191  xor     edx, edx; Val
0x18001e193  call    memset_0
0x18001e198  mov     dword ptr [rbx], 114h
0x18001e19e  test    rsi, rsi
0x18001e1a1  jz      loc_18001E242
0x18001e1a7  cmp     [rsi], r14w
0x18001e1ab  jz      loc_18001E242
0x18001e1b1  xorps   xmm0, xmm0
0x18001e1b4  mov     [rbp+phPrinter], r14
0x18001e1b8  lea     r8, [rbp+pDefault]; pDefault
0x18001e1bc  mov     [rbp+arg_8], r14d
0x18001e1c0  lea     rdx, [rbp+phPrinter]; phPrinter
0x18001e1c4  mov     [rbp+pType], 3
0x18001e1cb  mov     rcx, rsi; pPrinterName
0x18001e1ce  mov     qword ptr [rbp+pDefault.DesiredAccess], 20002h
0x18001e1d6  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18001e1db  call    cs:__imp_OpenPrinterW
0x18001e1e1  test    eax, eax
0x18001e1e3  jz      short loc_18001E251
0x18001e1e5  mov     rcx, [rbp+phPrinter]; hPrinter
0x18001e1e9  lea     rax, [rbp+arg_8]
0x18001e1ed  mov     [rsp+50h+pcbNeeded], rax; pcbNeeded
0x18001e1f2  lea     r8, [rbp+pType]; pType
0x18001e1f6  mov     r9, rbx; pData
0x18001e1f9  mov     [rsp+50h+nSize], 114h; nSize
0x18001e201  lea     rdx, aOsversion; "OSVersion"
0x18001e208  call    cs:__imp_GetPrinterDataW
0x18001e20e  test    eax, eax
0x18001e210  jz      short loc_18001E231
0x18001e212  lea     rcx, [rbx+0Ch]; void *
0x18001e216  xor     edx, edx; Val
0x18001e218  mov     r8d, 108h; Size
0x18001e21e  call    memset_0
0x18001e223  mov     dword ptr [rbx], 114h
0x18001e229  mov     qword ptr [rbx+4], 4
0x18001e231  mov     rcx, [rbp+phPrinter]; hPrinter
0x18001e235  mov     edi, 1
0x18001e23a  call    cs:__imp_ClosePrinter
0x18001e240  jmp     short loc_18001E251
0x18001e242  mov     rcx, rbx; lpVersionInformation
0x18001e245  call    cs:__imp_RtlGetVersion
0x18001e24b  test    eax, eax
0x18001e24d  setns   dil
0x18001e251  mov     eax, edi
0x18001e253  add     rsp, 50h
0x18001e257  pop     r14
0x18001e259  pop     rdi
0x18001e25a  pop     rsi
0x18001e25b  pop     rbx
0x18001e25c  pop     rbp
0x18001e25d  retn
```
