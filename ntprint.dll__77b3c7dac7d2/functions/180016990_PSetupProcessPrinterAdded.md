# PSetupProcessPrinterAdded

- ea: `0x180016990`
- end: `0x180016cdd`
- name: `PSetupProcessPrinterAdded`
- size: `845`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000c368`
- `0x180013050`
- `0x180016730`
- `0x180016990`
- `0x180016ce4`
- `0x18001da88`
- `0x1800204e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016bb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016bb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800169f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016b32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016c35`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ab5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016b47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ab5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016b47`
- `WINSPOOL!GetPrinterW` at `0x180016a8f`
- `WINSPOOL!GetPrinterW` at `0x180016ae8`
- `WINSPOOL!GetPrinterW` at `0x180016a8f`
- `WINSPOOL!GetPrinterW` at `0x180016ae8`
- `WINSPOOL!EnumPrinterDriversW` at `0x180016b24`
- `WINSPOOL!EnumPrinterDriversW` at `0x180016b82`
- `WINSPOOL!EnumPrinterDriversW` at `0x180016b24`
- `WINSPOOL!EnumPrinterDriversW` at `0x180016b82`
- `WINSPOOL!OpenPrinterW` at `0x180016a15`
- `WINSPOOL!OpenPrinterW` at `0x180016a15`
- `WINSPOOL!ClosePrinter` at `0x180016c27`
- `WINSPOOL!ClosePrinter` at `0x180016c27`

## pseudocode

```c
__int64 __fastcall PSetupProcessPrinterAdded(__int64 a1, _QWORD *a2, WCHAR *a3, const WCHAR *a4, __int64 a5, int a6)
{
  WCHAR *v6; // r12
  BYTE *v10; // rdi
  const unsigned __int16 *v11; // r15
  unsigned int PrinterW; // ebx
  BYTE *v13; // r13
  BYTE *v14; // r12
  BYTE *v15; // rax
  unsigned int v16; // r14d
  __int64 v17; // rsi
  BYTE *v18; // r14
  BYTE *v19; // rbx
  unsigned __int16 *v20; // rcx
  DWORD cbBuf; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-BCh] BYREF
  VIRTUAL_PROCESSOR_ARCH Architecture; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbNeeded; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE phPrinter; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR pDeviceName; // [rsp+60h] [rbp-A0h]
  LPBYTE v27; // [rsp+68h] [rbp-98h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+70h] [rbp-90h] BYREF
  WCHAR VpId[264]; // [rsp+90h] [rbp-70h] BYREF

  pDeviceName = a4;
  *(_OWORD *)&pDefault.pDatatype = 0;
  v6 = (WCHAR *)a4;
  phPrinter = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
  {
    SetLastError(0x4ECu);
    return 0;
  }
  v10 = 0;
  v11 = 0;
  PrinterW = OpenPrinterW(v6, &phPrinter, &pDefault);
  if ( PrinterW )
  {
    if ( !(unsigned int)IsLonghornOrAbove(a3) )
    {
      v20 = (unsigned __int16 *)a2[24];
      v19 = (BYTE *)a2[6];
      v11 = (const unsigned __int16 *)a2[27];
      v14 = (BYTE *)a2[4];
      v18 = (BYTE *)a2[5];
      if ( v20 )
        PSetupAssociateICMProfiles(v20, pDeviceName);
      goto LABEL_20;
    }
    pcbNeeded = 0;
    cbBuf = 0;
    pcReturned = 0;
    memset_0(VpId, 0, 0x208u);
    Architecture = 260;
    PrinterW = GetArchitecture(a3, (UINT32)VpId, &Architecture);
    if ( !PrinterW )
      goto LABEL_22;
    if ( !GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) && GetLastError() == 122 )
    {
      v13 = (BYTE *)LocalAlloc(0x40u, cbBuf);
      if ( v13 )
      {
        v14 = 0;
        v27 = 0;
        PrinterW = GetPrinterW(phPrinter, 2u, v13, cbBuf, &pcbNeeded);
        if ( PrinterW )
        {
          cbBuf = 0;
          if ( !EnumPrinterDriversW(a3, VpId, 8u, 0, 0, &cbBuf, &pcReturned)
            && GetLastError() == 122
            && (v15 = (BYTE *)LocalAlloc(0x40u, cbBuf), (v10 = v15) != 0) )
          {
            PrinterW = EnumPrinterDriversW(a3, VpId, 8u, v15, cbBuf, &pcbNeeded, &pcReturned);
            if ( !PrinterW )
            {
              v18 = 0;
              goto LABEL_18;
            }
            PrinterW = 0;
            v16 = 0;
            if ( pcReturned )
            {
              while ( 1 )
              {
                v17 = 200LL * v16;
                if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)&v10[v17 + 8], *((_QWORD *)v13 + 4)) )
                  break;
                if ( ++v16 >= pcReturned )
                  goto LABEL_17;
              }
              PrinterW = 1;
              v11 = *(const unsigned __int16 **)&v10[v17 + 144];
              v14 = *(BYTE **)&v10[v17 + 120];
              v18 = *(BYTE **)&v10[v17 + 104];
              v27 = *(LPBYTE *)&v10[v17 + 112];
              goto LABEL_18;
            }
          }
          else
          {
            PrinterW = 0;
          }
LABEL_17:
          v18 = 0;
        }
        else
        {
          v18 = 0;
        }
LABEL_18:
        LocalFree(v13);
        if ( !PrinterW )
        {
LABEL_21:
          v6 = (WCHAR *)pDeviceName;
          goto LABEL_22;
        }
        v19 = v27;
LABEL_20:
        PrinterW = SetPnPInfoForPrinter(phPrinter, 0, v14, v18, v19, 0);
        goto LABEL_21;
      }
    }
    PrinterW = 0;
  }
LABEL_22:
  if ( !a6 && v11 )
    CallVendorDll(v11, v6);
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( v10 )
    LocalFree(v10);
  return PrinterW;
}

```

## disassembly

```asm
0x180016990  mov     [rsp-8+arg_0], rbx
0x180016995  push    rbp
0x180016996  push    rsi
0x180016997  push    rdi
0x180016998  push    r12
0x18001699a  push    r13
0x18001699c  push    r14
0x18001699e  push    r15
0x1800169a0  lea     rbp, [rsp-1B0h]
0x1800169a8  sub     rsp, 2B0h
0x1800169af  mov     rax, cs:__security_cookie
0x1800169b6  xor     rax, rsp
0x1800169b9  mov     [rbp+1E0h+var_40], rax
0x1800169c0  xorps   xmm0, xmm0
0x1800169c3  mov     [rsp+2E0h+pDeviceName], r9
0x1800169c8  movdqu  xmmword ptr [rsp+2E0h+pDefault.pDatatype], xmm0
0x1800169ce  mov     r12, r9
0x1800169d1  mov     [rsp+2E0h+phPrinter], 0
0x1800169da  mov     r14, r8
0x1800169dd  mov     qword ptr [rbp+1E0h+pDefault.DesiredAccess], 0F000Ch
0x1800169e5  mov     rsi, rdx
0x1800169e8  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x1800169ed  test    al, al
0x1800169ef  jz      short loc_180016A03
0x1800169f1  mov     ecx, 4ECh; dwErrCode
0x1800169f6  call    cs:__imp_SetLastError
0x1800169fc  xor     eax, eax
0x1800169fe  jmp     loc_180016C3D
0x180016a03  lea     r8, [rsp+2E0h+pDefault]; pDefault
0x180016a08  mov     rcx, r12; pPrinterName
0x180016a0b  lea     rdx, [rsp+2E0h+phPrinter]; phPrinter
0x180016a10  xor     edi, edi
0x180016a12  xor     r15d, r15d
0x180016a15  call    cs:__imp_OpenPrinterW
0x180016a1b  mov     ebx, eax
0x180016a1d  test    eax, eax
0x180016a1f  jz      loc_180016C04
0x180016a25  mov     rcx, r14; pPrinterName
0x180016a28  call    IsLonghornOrAbove
0x180016a2d  test    eax, eax
0x180016a2f  jz      loc_180016CAB
0x180016a35  xor     edx, edx; Val
0x180016a37  mov     [rsp+2E0h+var_290], edi
0x180016a3b  mov     r8d, 208h; Size
0x180016a41  mov     [rsp+2E0h+cbBuf], edi
0x180016a45  lea     rcx, [rbp+1E0h+VpId]; void *
0x180016a49  mov     [rsp+2E0h+var_29C], edi
0x180016a4d  call    memset_0
0x180016a52  lea     r8, [rsp+2E0h+Architecture]; Architecture
0x180016a57  mov     [rsp+2E0h+Architecture], 104h
0x180016a5f  lea     rdx, [rbp+1E0h+VpId]; VpId
0x180016a63  mov     rcx, r14; VmSavedStateDumpHandle
0x180016a66  call    GetArchitecture
0x180016a6b  mov     ebx, eax
0x180016a6d  test    eax, eax
0x180016a6f  jz      loc_180016C04
0x180016a75  mov     rcx, [rsp+2E0h+phPrinter]; hPrinter
0x180016a7a  lea     rax, [rsp+2E0h+cbBuf]
0x180016a7f  lea     ebx, [rdi+2]
0x180016a82  mov     [rsp+2E0h+pcbNeeded], rax; pcbNeeded
0x180016a87  mov     edx, ebx; Level
0x180016a89  xor     r9d, r9d; cbBuf
0x180016a8c  xor     r8d, r8d; pPrinter
0x180016a8f  call    cs:__imp_GetPrinterW
0x180016a95  test    eax, eax
0x180016a97  jnz     loc_180016CA4
0x180016a9d  call    cs:__imp_GetLastError
0x180016aa3  cmp     eax, 7Ah ; 'z'
0x180016aa6  jnz     loc_180016CA4
0x180016aac  mov     edx, [rsp+2E0h+cbBuf]; uBytes
0x180016ab0  lea     esi, [rdi+40h]
0x180016ab3  mov     ecx, esi; uFlags
0x180016ab5  call    cs:__imp_LocalAlloc
0x180016abb  mov     r13, rax
0x180016abe  test    rax, rax
0x180016ac1  jz      loc_180016CA4
0x180016ac7  mov     r9d, [rsp+2E0h+cbBuf]; cbBuf
0x180016acc  lea     rax, [rsp+2E0h+var_290]
0x180016ad1  mov     rcx, [rsp+2E0h+phPrinter]; hPrinter
0x180016ad6  mov     r8, r13; pPrinter
0x180016ad9  mov     edx, ebx; Level
0x180016adb  mov     [rsp+2E0h+pcbNeeded], rax; pcbNeeded
0x180016ae0  xor     r12d, r12d
0x180016ae3  mov     [rsp+2E0h+var_278], rdi
0x180016ae8  call    cs:__imp_GetPrinterW
0x180016aee  mov     ebx, eax
0x180016af0  test    eax, eax
0x180016af2  jz      loc_180016C94
0x180016af8  lea     rax, [rsp+2E0h+var_29C]
0x180016afd  mov     [rsp+2E0h+cbBuf], edi
0x180016b01  mov     [rsp+2E0h+pcReturned], rax; pcReturned
0x180016b06  lea     ebx, [rdi+8]
0x180016b09  lea     rax, [rsp+2E0h+cbBuf]
0x180016b0e  xor     r9d, r9d; pDriverInfo
0x180016b11  mov     [rsp+2E0h+var_2B8], rax; pcbNeeded
0x180016b16  lea     rdx, [rbp+1E0h+VpId]; pEnvironment
0x180016b1a  mov     r8d, ebx; Level
0x180016b1d  mov     dword ptr [rsp+2E0h+pcbNeeded], edi; cbBuf
0x180016b21  mov     rcx, r14; pName
0x180016b24  call    cs:__imp_EnumPrinterDriversW
0x180016b2a  test    eax, eax
0x180016b2c  jnz     loc_180016C8D
0x180016b32  call    cs:__imp_GetLastError
0x180016b38  cmp     eax, 7Ah ; 'z'
0x180016b3b  jnz     loc_180016C8D
0x180016b41  mov     edx, [rsp+2E0h+cbBuf]; uBytes
0x180016b45  mov     ecx, esi; uFlags
0x180016b47  call    cs:__imp_LocalAlloc
0x180016b4d  mov     rdi, rax
0x180016b50  test    rax, rax
0x180016b53  jz      loc_180016C8D
0x180016b59  mov     edx, [rsp+2E0h+cbBuf]
0x180016b5d  lea     rax, [rsp+2E0h+var_29C]
0x180016b62  mov     [rsp+2E0h+pcReturned], rax; pcReturned
0x180016b67  mov     r9, rdi; pDriverInfo
0x180016b6a  lea     rax, [rsp+2E0h+var_290]
0x180016b6f  mov     r8d, ebx; Level
0x180016b72  mov     [rsp+2E0h+var_2B8], rax; pcbNeeded
0x180016b77  mov     rcx, r14; pName
0x180016b7a  mov     dword ptr [rsp+2E0h+pcbNeeded], edx; cbBuf
0x180016b7e  lea     rdx, [rbp+1E0h+VpId]; pEnvironment
0x180016b82  call    cs:__imp_EnumPrinterDriversW
0x180016b88  mov     ebx, eax
0x180016b8a  test    eax, eax
0x180016b8c  jz      loc_180016C9C
0x180016b92  xor     ebx, ebx
0x180016b94  xor     r14d, r14d
0x180016b97  cmp     [rsp+2E0h+var_29C], ebx
0x180016b9b  jbe     short loc_180016BC8
0x180016b9d  mov     rdx, [r13+20h]
0x180016ba1  mov     eax, r14d
0x180016ba4  imul    rsi, rax, 0C8h
0x180016bab  mov     rcx, [rsi+rdi+8]
0x180016bb0  call    cs:__imp__o__wcsicmp
0x180016bb6  test    eax, eax
0x180016bb8  jz      loc_180016C67
0x180016bbe  inc     r14d
0x180016bc1  cmp     r14d, [rsp+2E0h+var_29C]
0x180016bc6  jb      short loc_180016B9D
0x180016bc8  mov     r14, rbx
0x180016bcb  mov     rcx, r13; hMem
0x180016bce  call    cs:__imp_LocalFree
0x180016bd4  test    ebx, ebx
0x180016bd6  jz      short loc_180016BFF
0x180016bd8  mov     rbx, [rsp+2E0h+var_278]
0x180016bdd  mov     rcx, [rsp+2E0h+phPrinter]; hPrinter
0x180016be2  mov     r9, r14; LPBYTE
0x180016be5  mov     [rsp+2E0h+var_2B8], 0; LPBYTE
0x180016bee  mov     r8, r12; LPBYTE
0x180016bf1  xor     edx, edx; pData
0x180016bf3  mov     [rsp+2E0h+pcbNeeded], rbx; LPBYTE
0x180016bf8  call    SetPnPInfoForPrinter
0x180016bfd  mov     ebx, eax
0x180016bff  mov     r12, [rsp+2E0h+pDeviceName]
0x180016c04  cmp     [rbp+1E0h+arg_28], 0
0x180016c0b  jnz     short loc_180016C1D
0x180016c0d  test    r15, r15
0x180016c10  jz      short loc_180016C1D
0x180016c12  mov     rdx, r12; unsigned __int16 *
0x180016c15  mov     rcx, r15; unsigned __int16 *
0x180016c18  call    ?CallVendorDll@@YAXPEBG0@Z; CallVendorDll(ushort const *,ushort const *)
0x180016c1d  mov     rcx, [rsp+2E0h+phPrinter]; hPrinter
0x180016c22  test    rcx, rcx
0x180016c25  jz      short loc_180016C2D
0x180016c27  call    cs:__imp_ClosePrinter
0x180016c2d  test    rdi, rdi
0x180016c30  jz      short loc_180016C3B
0x180016c32  mov     rcx, rdi; hMem
0x180016c35  call    cs:__imp_LocalFree
0x180016c3b  mov     eax, ebx
0x180016c3d  mov     rcx, [rbp+1E0h+var_40]
0x180016c44  xor     rcx, rsp; StackCookie
0x180016c47  call    __security_check_cookie
0x180016c4c  mov     rbx, [rsp+2E0h+arg_0]
0x180016c54  add     rsp, 2B0h
0x180016c5b  pop     r15
0x180016c5d  pop     r14
0x180016c5f  pop     r13
0x180016c61  pop     r12
0x180016c63  pop     rdi
0x180016c64  pop     rsi
0x180016c65  pop     rbp
0x180016c66  retn
0x180016c67  mov     rax, [rsi+rdi+70h]
0x180016c6c  mov     ebx, 1
0x180016c71  mov     r15, [rsi+rdi+90h]
0x180016c79  mov     r12, [rsi+rdi+78h]
0x180016c7e  mov     r14, [rsi+rdi+68h]
0x180016c83  mov     [rsp+2E0h+var_278], rax
0x180016c88  jmp     loc_180016BCB
0x180016c8d  xor     ebx, ebx
0x180016c8f  jmp     loc_180016BC8
0x180016c94  mov     r14, rdi
0x180016c97  jmp     loc_180016BCB
0x180016c9c  mov     r14, r12
0x180016c9f  jmp     loc_180016BCB
0x180016ca4  xor     ebx, ebx
0x180016ca6  jmp     loc_180016C04
0x180016cab  mov     rcx, [rsi+0C0h]; unsigned __int16 *
0x180016cb2  mov     rbx, [rsi+30h]
0x180016cb6  mov     r15, [rsi+0D8h]
0x180016cbd  mov     r12, [rsi+20h]
0x180016cc1  mov     r14, [rsi+28h]
0x180016cc5  test    rcx, rcx
0x180016cc8  jz      loc_180016BDD
0x180016cce  mov     rdx, [rsp+2E0h+pDeviceName]; pDeviceName
0x180016cd3  call    PSetupAssociateICMProfiles
0x180016cd8  jmp     loc_180016BDD
```
