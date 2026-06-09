# InstallPrinterDriverFromInfPackage

- ea: `0x18000eb10`
- end: `0x18000ed28`
- name: `InstallPrinterDriverFromInfPackage`
- size: `536`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000b7ec`

## callees

- `0x18000eb10`
- `0x180029ff0`
- `0x180034bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec06`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x18000eb50`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x18000eb50`

## string_xrefs

- `0x18000eb6b`: `InstallPrinterDriverFromPackage failed`
- `0x18000eb76`: `InstallPrinterDriverFromInfPackage`
- `0x18000ec1b`: `InstallPrinterDriverFromInfPackage`
- `0x18000ec7c`: `InstallPrinterDriverFromInfPackage`
- `0x18000ecd5`: `InstallPrinterDriverFromInfPackage`

## pseudocode

```c
__int64 __fastcall InstallPrinterDriverFromInfPackage(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4,
        __int16 a5,
        unsigned int a6,
        int *a7)
{
  __int64 v7; // r15
  int v11; // esi
  HRESULT v12; // ebx
  DWORD LastError; // eax
  DWORD v14; // eax

  v7 = a4;
  v11 = 0;
  v12 = InstallPrinterDriverFromPackageW(a1, a2, a3, (LPCWSTR)PlatformEnv[a4], (a6 >> 2) & 1);
  if ( v12 < 0 )
  {
    LastError = GetLastError();
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InstallPrinterDriverFromInfPackage",
      L"InstallPrinterDriverFromPackage failed",
      a1,
      a2,
      a3,
      0,
      (const unsigned __int16 *)PlatformEnv[v7],
      0,
      0,
      LastError,
      v12);
    if ( (a5 & 0x208) == 0 && ((unsigned __int16)v12 == 1930 || (unsigned int)(unsigned __int16)v12 - 3013 <= 1) )
    {
      v12 = InternalPrintUpgUI(a3);
      if ( v12 < 0 )
      {
        v14 = GetLastError();
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"InstallPrinterDriverFromInfPackage",
          L"InternalPrintUpgUI failed",
          a1,
          a2,
          a3,
          0,
          (const unsigned __int16 *)PlatformEnv[v7],
          0,
          0,
          v14,
          v12);
      }
      v11 = 1;
    }
  }
  if ( a7 )
    *a7 = v11;
  if ( v12 >= 0 )
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
      L"InstallPrinterDriverFromInfPackage",
      0,
      a1,
      a2,
      a3,
      0,
      (const unsigned __int16 *)PlatformEnv[v7],
      0,
      0,
      0,
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000eb10  push    rbx
0x18000eb12  push    rbp
0x18000eb13  push    rsi
0x18000eb14  push    rdi
0x18000eb15  push    r12
0x18000eb17  push    r13
0x18000eb19  push    r14
0x18000eb1b  push    r15
0x18000eb1d  sub     rsp, 68h
0x18000eb21  mov     eax, [rsp+0A8h+arg_28]
0x18000eb28  lea     r13, PlatformEnv
0x18000eb2f  movsxd  r15, r9d
0x18000eb32  xor     r12d, r12d
0x18000eb35  shr     eax, 2
0x18000eb38  mov     rdi, r8
0x18000eb3b  and     eax, 1
0x18000eb3e  mov     rbp, rdx
0x18000eb41  mov     [rsp+0A8h+dwFlags], eax; dwFlags
0x18000eb45  mov     r14, rcx
0x18000eb48  mov     r9, [r13+r15*8+0]; pszEnvironment
0x18000eb4d  mov     esi, r12d
0x18000eb50  call    cs:__imp_InstallPrinterDriverFromPackageW
0x18000eb56  mov     ebx, eax
0x18000eb58  test    eax, eax
0x18000eb5a  jns     loc_18000ECBD
0x18000eb60  call    cs:__imp_GetLastError
0x18000eb66  mov     rcx, [r13+r15*8+0]
0x18000eb6b  lea     r8, aInstallprinter_1; "InstallPrinterDriverFromPackage failed"
0x18000eb72  mov     [rsp+0A8h+var_50], ebx; unsigned int
0x18000eb76  lea     rdx, aInstallprinter_2; "InstallPrinterDriverFromInfPackage"
0x18000eb7d  mov     [rsp+0A8h+var_58], eax; unsigned int
0x18000eb81  mov     r9, r14; unsigned __int16 *
0x18000eb84  mov     [rsp+0A8h+var_60], r12; unsigned __int16 *
0x18000eb89  mov     [rsp+0A8h+var_68], r12d; int
0x18000eb8e  mov     [rsp+0A8h+var_70], rcx; unsigned __int16 *
0x18000eb93  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000eb9a  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000eb9f  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18000eba4  mov     qword ptr [rsp+0A8h+dwFlags], rbp; unsigned __int16 *
0x18000eba9  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000ebae  test    dword ptr [rsp+0A8h+arg_20], 208h
0x18000ebb9  jnz     loc_18000ECBD
0x18000ebbf  movzx   ecx, bx
0x18000ebc2  mov     r8d, 78Ah
0x18000ebc8  cmp     ecx, r8d
0x18000ebcb  jz      short loc_18000EBDC
0x18000ebcd  lea     eax, [rcx-0BC5h]
0x18000ebd3  cmp     eax, 1
0x18000ebd6  ja      loc_18000ECBD
0x18000ebdc  cmp     ecx, r8d
0x18000ebdf  mov     [rsp+0A8h+arg_28], 1
0x18000ebea  mov     edx, r12d
0x18000ebed  lea     r8, [rsp+0A8h+arg_28]
0x18000ebf5  setz    dl
0x18000ebf8  mov     rcx, rdi; unsigned __int16 *
0x18000ebfb  call    InternalPrintUpgUI
0x18000ec00  mov     ebx, eax
0x18000ec02  test    eax, eax
0x18000ec04  jns     short loc_18000EC5D
0x18000ec06  call    cs:__imp_GetLastError
0x18000ec0c  mov     [rsp+0A8h+var_50], ebx; unsigned int
0x18000ec10  lea     r8, aInternalprintu; "InternalPrintUpgUI failed"
0x18000ec17  mov     [rsp+0A8h+var_58], eax; unsigned int
0x18000ec1b  lea     rdx, aInstallprinter_2; "InstallPrinterDriverFromInfPackage"
0x18000ec22  mov     rax, [r13+r15*8+0]
0x18000ec27  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000ec2e  mov     [rsp+0A8h+var_60], r12; unsigned __int16 *
0x18000ec33  mov     r9, r14; unsigned __int16 *
0x18000ec36  mov     [rsp+0A8h+var_68], r12d; int
0x18000ec3b  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x18000ec40  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000ec45  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18000ec4a  mov     qword ptr [rsp+0A8h+dwFlags], rbp; unsigned __int16 *
0x18000ec4f  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000ec54  mov     esi, [rsp+0A8h+arg_28]
0x18000ec5b  jmp     short loc_18000ECBD
0x18000ec5d  mov     esi, [rsp+0A8h+arg_28]
0x18000ec64  test    esi, esi
0x18000ec66  jns     short loc_18000ECBD
0x18000ec68  mov     rax, [r13+r15*8+0]
0x18000ec6d  lea     r8, aBspPrinterDriv; "BSP_PRINTER_DRIVER_CANCELLED"
0x18000ec74  mov     [rsp+0A8h+var_50], 800704C7h; unsigned int
0x18000ec7c  lea     rdx, aInstallprinter_2; "InstallPrinterDriverFromInfPackage"
0x18000ec83  mov     [rsp+0A8h+var_58], 4C7h; unsigned int
0x18000ec8b  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000ec92  mov     [rsp+0A8h+var_60], r12; unsigned __int16 *
0x18000ec97  mov     r9, r14; unsigned __int16 *
0x18000ec9a  mov     [rsp+0A8h+var_68], r12d; int
0x18000ec9f  mov     ebx, 800704C7h
0x18000eca4  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x18000eca9  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000ecae  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18000ecb3  mov     qword ptr [rsp+0A8h+dwFlags], rbp; unsigned __int16 *
0x18000ecb8  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000ecbd  mov     rax, [rsp+0A8h+arg_30]
0x18000ecc5  test    rax, rax
0x18000ecc8  jz      short loc_18000ECCC
0x18000ecca  mov     [rax], esi
0x18000eccc  test    ebx, ebx
0x18000ecce  js      short loc_18000ED15
0x18000ecd0  mov     rax, [r13+r15*8+0]
0x18000ecd5  lea     rdx, aInstallprinter_2; "InstallPrinterDriverFromInfPackage"
0x18000ecdc  mov     [rsp+0A8h+var_50], ebx; unsigned int
0x18000ece0  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18000ece7  mov     [rsp+0A8h+var_58], r12d; unsigned int
0x18000ecec  mov     r9, r14; unsigned __int16 *
0x18000ecef  mov     [rsp+0A8h+var_60], r12; unsigned __int16 *
0x18000ecf4  xor     r8d, r8d; unsigned __int16 *
0x18000ecf7  mov     [rsp+0A8h+var_68], r12d; int
0x18000ecfc  mov     [rsp+0A8h+var_70], rax; unsigned __int16 *
0x18000ed01  mov     [rsp+0A8h+var_78], r12; unsigned __int16 *
0x18000ed06  mov     [rsp+0A8h+var_80], rdi; unsigned __int16 *
0x18000ed0b  mov     qword ptr [rsp+0A8h+dwFlags], rbp; unsigned __int16 *
0x18000ed10  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000ed15  mov     eax, ebx
0x18000ed17  add     rsp, 68h
0x18000ed1b  pop     r15
0x18000ed1d  pop     r14
0x18000ed1f  pop     r13
0x18000ed21  pop     r12
0x18000ed23  pop     rdi
0x18000ed24  pop     rsi
0x18000ed25  pop     rbp
0x18000ed26  pop     rbx
0x18000ed27  retn
```
