# DeleteOrphan(ushort * *,ulong,_SEARCHCOLUMN * const,_PRUNINGPOLICIES *)

- ea: `0x1800a6e68`
- end: `0x1800a744b`
- name: `?DeleteOrphan@@YAXPEAPEAGKQEAU_SEARCHCOLUMN@@PEAU_PRUNINGPOLICIES@@@Z`
- size: `1507`
- prototype: `void __fastcall(unsigned __int16 **, unsigned int, struct _SEARCHCOLUMN *const, struct _PRUNINGPOLICIES *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x1800a7454`

## callees

- `0x18000edc4`
- `0x180013c90`
- `0x180035ae4`
- `0x180046650`
- `0x180054638`
- `0x1800a5738`
- `0x1800a5f90`
- `0x1800a6a14`
- `0x1800a6c30`
- `0x1800a6e68`
- `0x1800a77a0`
- `0x1800a79e8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a700b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a71d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7374`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a700b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a71d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a725c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a72bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7374`
- `SPOOLSS!DllFreeSplStr` at `0x1800a727b`
- `SPOOLSS!DllFreeSplStr` at `0x1800a727b`
- `SPOOLSS!DllFreeSplMem` at `0x1800a72a3`
- `SPOOLSS!DllFreeSplMem` at `0x1800a740e`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7417`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7422`
- `SPOOLSS!DllFreeSplMem` at `0x1800a72a3`
- `SPOOLSS!DllFreeSplMem` at `0x1800a740e`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7417`
- `SPOOLSS!DllFreeSplMem` at `0x1800a7422`
- `SPOOLSS!DllAllocSplMem` at `0x1800a7185`
- `SPOOLSS!DllAllocSplMem` at `0x1800a7185`
- `SPOOLSS!ClosePrinter` at `0x1800a73c7`
- `SPOOLSS!ClosePrinter` at `0x1800a73c7`
- `SPOOLSS!OpenPrinter2W` at `0x1800a6ffd`
- `SPOOLSS!OpenPrinter2W` at `0x1800a6ffd`
- `SPOOLSS!GetPrinterW` at `0x1800a716c`
- `SPOOLSS!GetPrinterW` at `0x1800a71af`
- `SPOOLSS!GetPrinterW` at `0x1800a716c`
- `SPOOLSS!GetPrinterW` at `0x1800a71af`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7403`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a7403`
- `srvcli!NetServerGetInfo` at `0x1800a7044`
- `srvcli!NetServerGetInfo` at `0x1800a7044`
- `netutils!NetApiBufferFree` at `0x1800a7051`
- `netutils!NetApiBufferFree` at `0x1800a7051`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a70ab`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a710c`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a720c`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a70ab`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a710c`
- `ACTIVEDS!__imp_ADsGetObject` at `0x1800a720c`

## string_xrefs

- `0x1800a73a5`: `DeleteOrphan`
- `0x1800a739b`: `Can't delete %ws.  Error: hr: 0x%x`

## pseudocode

```c
void __fastcall DeleteOrphan(
        unsigned __int16 **a1,
        unsigned int a2,
        struct _SEARCHCOLUMN *const a3,
        struct _PRUNINGPOLICIES *a4)
{
  int v4; // r14d
  const unsigned __int16 *v8; // r15
  __int64 v9; // r9
  unsigned __int16 *v10; // r10
  int v11; // edx
  unsigned int v12; // ebx
  int v13; // ecx
  unsigned __int16 *v14; // r13
  int v15; // edi
  int v16; // eax
  LPCWSTR v17; // rsi
  struct _PRUNINGPOLICIES *v18; // r12
  DWORD v19; // esi
  DWORD Info; // ebx
  unsigned __int16 *EscapedString; // rax
  BYTE *v22; // rax
  BYTE *v23; // rbx
  DWORD v24; // eax
  BYTE *v25; // rax
  BYTE *v26; // r8
  int v27; // ecx
  int v28; // edx
  DWORD v29; // eax
  DWORD LastError; // eax
  int v31; // eax
  signed int v32; // ebx
  DWORD v33; // eax
  DWORD v34; // eax
  LPCWSTR pPrinterName; // [rsp+30h] [rbp-D0h] BYREF
  struct _PRUNINGPOLICIES *v36; // [rsp+38h] [rbp-C8h]
  void *ppObject; // [rsp+40h] [rbp-C0h] BYREF
  LPBYTE bufptr; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE phPrinter; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR servername; // [rsp+58h] [rbp-A8h] BYREF
  void *v41; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszPathName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  _PRINTER_OPTIONSW pOptions; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v45; // [rsp+80h] [rbp-80h]
  unsigned __int16 v46[12]; // [rsp+88h] [rbp-78h] BYREF
  BYTE pPrinter[256]; // [rsp+A0h] [rbp-60h] BYREF

  v4 = 0;
  v36 = a4;
  ppObject = 0;
  v41 = 0;
  lpszPathName = 0;
  v43 = 0;
  phPrinter = 0;
  servername = 0;
  if ( *((int *)a3 + 10) < 0 )
    v8 = 0;
  else
    v8 = *(const unsigned __int16 **)(*((_QWORD *)a3 + 2) + 8LL);
  if ( *((int *)a3 + 22) < 0 )
    pPrinterName = 0;
  else
    pPrinterName = *(LPCWSTR *)(*((_QWORD *)a3 + 8) + 8LL);
  if ( *((int *)a3 + 58) < 0 )
    v9 = 0;
  else
    v9 = *(_QWORD *)(*((_QWORD *)a3 + 26) + 8LL);
  if ( *((int *)a3 + 34) < 0 )
    v10 = 0;
  else
    v10 = *(unsigned __int16 **)(*((_QWORD *)a3 + 14) + 8LL);
  v11 = *((_DWORD *)a3 + 46);
  v45 = v10;
  if ( v11 < 0 )
    v12 = 0;
  else
    v12 = *(_DWORD *)(*((_QWORD *)a3 + 20) + 8LL);
  if ( *((int *)a3 + 70) < 0 )
    LOBYTE(v13) = 0;
  else
    v13 = *(_DWORD *)(*((_QWORD *)a3 + 32) + 8LL);
  if ( !v8 || !v10 )
    return;
  v14 = 0;
  v15 = 0;
  if ( (v13 & 1) != 0 )
  {
    v18 = a4;
    goto LABEL_37;
  }
  if ( !pPrinterName || !v9 || v11 < 0 )
  {
    v4 = 1;
    v15 = 1;
    LastError = GetLastError();
    SplLogEvent(&MSG_PRUNING_NOUNC_PRINTER, LastError, v8, 0);
LABEL_71:
    v18 = v36;
LABEL_37:
    v17 = pPrinterName;
    goto LABEL_38;
  }
  if ( v12 < 4 && !*(_DWORD *)a4 )
  {
    v18 = a4;
    v17 = pPrinterName;
LABEL_38:
    if ( ADsGetObject(v8, &IID_IADs, &ppObject) >= 0 )
    {
      if ( v15 )
      {
        if ( (v4 || (unsigned int)EnoughRetries((struct IADs *)ppObject, *((_DWORD *)v18 + 1)))
          && (*(int (__fastcall **)(void *, LPCWSTR *))(*(_QWORD *)ppObject + 88LL))(ppObject, &lpszPathName) >= 0
          && ADsGetObject(lpszPathName, &IID_IADsContainer, &v41) >= 0 )
        {
          EscapedString = CreateEscapedString(v45, L",=\r\n+<>#;\"\\");
          v14 = EscapedString;
          if ( EscapedString )
          {
            v31 = StrCatAlloc(&v43, L"CN=", EscapedString, 0);
            v32 = v31;
            if ( v31 > 0 )
              v32 = (unsigned __int16)v31 | 0x80070000;
            if ( v32 < 0
              || (v32 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64))(*(_QWORD *)v41 + 120LL))(
                          v41,
                          L"printQueue",
                          v43),
                  v32 < 0) )
            {
              StringCchPrintfW(v46, 0xBu, L"%0x", (unsigned int)v32);
              v34 = GetLastError();
              SplLogEvent(&MSG_CANT_PRUNE_PRINTER, v34, v8, v46, 0);
              LocalSpoolerTelemetry::WriteDbgTraceWarning(
                "DeleteOrphan",
                L"Can't delete %ws.  Error: hr: 0x%x",
                v17,
                (unsigned int)v32);
            }
            else
            {
              v33 = GetLastError();
              SplLogEvent(&MSG_PRUNING_PRINTER, v33, v8, 0);
            }
          }
          else
          {
            GetLastError();
          }
        }
      }
      else
      {
        DeleteRetryEntry((struct IADs *)ppObject);
      }
    }
    goto LABEL_81;
  }
  if ( UNC2Server(pPrinterName, &servername) )
    goto LABEL_71;
  v16 = ServerOnSite(a1, a2, servername);
  v17 = pPrinterName;
  if ( !v16 )
    goto LABEL_69;
  pOptions.cbSize = 8;
  pOptions.dwFlags = 1;
  if ( !OpenPrinter2W(pPrinterName, &phPrinter, 0, &pOptions) )
  {
    v18 = v36;
    v19 = GetLastError();
    if ( v19 != 5 )
    {
      if ( v12 >= 4
        || *(_DWORD *)v36 == 2
        || *(_DWORD *)v36 == 1
        && (bufptr = 0, Info = NetServerGetInfo(servername, 0x64u, &bufptr), NetApiBufferFree(bufptr), !Info) )
      {
        v15 = 1;
        if ( *((_DWORD *)v36 + 2) )
        {
          StringCchPrintfW(v46, 0xBu, L"%0x", v19);
          SplLogEvent(&MSG_PRUNING_ABSENT_PRINTER, v19, v8, v46, 0);
        }
      }
    }
    goto LABEL_37;
  }
  if ( v12 < 4 )
    goto LABEL_69;
  LODWORD(pPrinterName) = 0;
  if ( GetPrinterW(phPrinter, 7u, pPrinter, 0x100u, (LPDWORD)&pPrinterName) )
  {
    v23 = pPrinter;
  }
  else
  {
    if ( GetLastError() != 122 )
    {
      v15 = 1;
LABEL_69:
      v18 = v36;
      goto LABEL_38;
    }
    v22 = (BYTE *)DllAllocSplMem((unsigned int)pPrinterName);
    v23 = v22;
    if ( v22 )
      LOBYTE(v22) = GetPrinterW(phPrinter, 7u, v22, (DWORD)pPrinterName, (LPDWORD)&pPrinterName);
    if ( !(_BYTE)v22 )
    {
LABEL_66:
      if ( v23 != pPrinter )
        DllFreeSplMem(v23);
      v4 = v15;
      goto LABEL_69;
    }
  }
  if ( (v23[8] & 1) == 0 )
  {
    v15 = 1;
    v24 = GetLastError();
    SplLogEvent(&MSG_PRUNING_UNPUBLISHED_PRINTER, v24, v8, 0);
    goto LABEL_66;
  }
  bufptr = 0;
  if ( ADsGetObject(v8, &IID_IADs, &ppObject) >= 0
    && (int)GetGUID((struct IADs *)ppObject, (unsigned __int16 **)&bufptr) >= 0 )
  {
    v25 = *(BYTE **)v23;
    if ( !*(_QWORD *)v23 )
      goto LABEL_64;
    v26 = (BYTE *)(bufptr - v25);
    do
    {
      v27 = *(unsigned __int16 *)&v26[(_QWORD)v25];
      v28 = *(unsigned __int16 *)v25 - v27;
      if ( v28 )
        break;
      v25 += 2;
    }
    while ( v27 );
    if ( v28 )
    {
LABEL_64:
      v15 = 1;
      v29 = GetLastError();
      SplLogEvent(&MSG_PRUNING_DUPLICATE_PRINTER, v29, v8, 0);
    }
    DllFreeSplStr(bufptr);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
    ppObject = 0;
    goto LABEL_66;
  }
LABEL_81:
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( v41 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( lpszPathName )
    SysFreeString((BSTR)lpszPathName);
  DllFreeSplMem(v43);
  DllFreeSplMem(v14);
  DllFreeSplMem(servername);
}

```

## disassembly

```asm
0x1800a6e68  push    rbp
0x1800a6e6a  push    rbx
0x1800a6e6b  push    rsi
0x1800a6e6c  push    rdi
0x1800a6e6d  push    r12
0x1800a6e6f  push    r13
0x1800a6e71  push    r14
0x1800a6e73  push    r15
0x1800a6e75  lea     rbp, [rsp-0B8h]
0x1800a6e7d  sub     rsp, 1B8h
0x1800a6e84  mov     rax, cs:__security_cookie
0x1800a6e8b  xor     rax, rsp
0x1800a6e8e  mov     [rbp+0F0h+var_50], rax
0x1800a6e95  xor     r14d, r14d
0x1800a6e98  mov     [rsp+1F0h+var_1B8], r9
0x1800a6e9d  mov     r11, r9
0x1800a6ea0  mov     esi, edx
0x1800a6ea2  mov     r12, rcx
0x1800a6ea5  mov     [rsp+1F0h+ppObject], r14
0x1800a6eaa  mov     [rsp+1F0h+var_190], r14
0x1800a6eaf  mov     [rsp+1F0h+lpszPathName], r14
0x1800a6eb4  mov     [rsp+1F0h+var_180], r14
0x1800a6eb9  mov     [rsp+1F0h+phPrinter], r14
0x1800a6ebe  mov     [rsp+1F0h+servername], r14
0x1800a6ec3  cmp     [r8+28h], r14d
0x1800a6ec7  jl      short loc_1800A6ED3
0x1800a6ec9  mov     rax, [r8+10h]
0x1800a6ecd  mov     r15, [rax+8]
0x1800a6ed1  jmp     short loc_1800A6ED6
0x1800a6ed3  mov     r15, r14
0x1800a6ed6  cmp     [r8+58h], r14d
0x1800a6eda  jl      short loc_1800A6EEB
0x1800a6edc  mov     rax, [r8+40h]
0x1800a6ee0  mov     rax, [rax+8]
0x1800a6ee4  mov     [rsp+1F0h+pPrinterName], rax
0x1800a6ee9  jmp     short loc_1800A6EF0
0x1800a6eeb  mov     [rsp+1F0h+pPrinterName], r14
0x1800a6ef0  cmp     [r8+0E8h], r14d
0x1800a6ef7  jl      short loc_1800A6F06
0x1800a6ef9  mov     rax, [r8+0D0h]
0x1800a6f00  mov     r9, [rax+8]
0x1800a6f04  jmp     short loc_1800A6F09
0x1800a6f06  mov     r9, r14
0x1800a6f09  cmp     [r8+88h], r14d
0x1800a6f10  jl      short loc_1800A6F1C
0x1800a6f12  mov     rax, [r8+70h]
0x1800a6f16  mov     r10, [rax+8]
0x1800a6f1a  jmp     short loc_1800A6F1F
0x1800a6f1c  mov     r10, r14
0x1800a6f1f  mov     edx, [r8+0B8h]
0x1800a6f26  mov     [rbp+0F0h+var_170], r10
0x1800a6f2a  test    edx, edx
0x1800a6f2c  js      short loc_1800A6F3A
0x1800a6f2e  mov     rax, [r8+0A0h]
0x1800a6f35  mov     ebx, [rax+8]
0x1800a6f38  jmp     short loc_1800A6F3D
0x1800a6f3a  mov     ebx, r14d
0x1800a6f3d  cmp     [r8+118h], r14d
0x1800a6f44  jl      short loc_1800A6F52
0x1800a6f46  mov     rax, [r8+100h]
0x1800a6f4d  mov     ecx, [rax+8]
0x1800a6f50  jmp     short loc_1800A6F55
0x1800a6f52  mov     ecx, r14d
0x1800a6f55  test    r15, r15
0x1800a6f58  jz      loc_1800A7428
0x1800a6f5e  test    r10, r10
0x1800a6f61  jz      loc_1800A7428
0x1800a6f67  mov     r8d, 1
0x1800a6f6d  mov     r13, r14
0x1800a6f70  mov     edi, r14d
0x1800a6f73  test    r8b, cl
0x1800a6f76  jnz     loc_1800A72E0
0x1800a6f7c  mov     rax, [rsp+1F0h+pPrinterName]
0x1800a6f81  test    rax, rax
0x1800a6f84  jz      loc_1800A72B6
0x1800a6f8a  test    r9, r9
0x1800a6f8d  jz      loc_1800A72B6
0x1800a6f93  test    edx, edx
0x1800a6f95  js      loc_1800A72B6
0x1800a6f9b  cmp     ebx, 4
0x1800a6f9e  jnb     short loc_1800A6FA9
0x1800a6fa0  cmp     [r11], r14d
0x1800a6fa3  jz      loc_1800A72E8
0x1800a6fa9  lea     rdx, [rsp+1F0h+servername]; unsigned __int16 **
0x1800a6fae  mov     rcx, rax; unsigned __int16 *
0x1800a6fb1  call    ?UNC2Server@@YAKPEBGPEAPEAG@Z; UNC2Server(ushort const *,ushort * *)
0x1800a6fb6  test    eax, eax
0x1800a6fb8  jnz     loc_1800A72D6
0x1800a6fbe  mov     r8, [rsp+1F0h+servername]; unsigned __int16 *
0x1800a6fc3  mov     edx, esi; unsigned int
0x1800a6fc5  mov     rcx, r12; unsigned __int16 **
0x1800a6fc8  call    ?ServerOnSite@@YAHPEAPEAGKPEAG@Z; ServerOnSite(ushort * *,ulong,ushort *)
0x1800a6fcd  mov     rsi, [rsp+1F0h+pPrinterName]
0x1800a6fd2  test    eax, eax
0x1800a6fd4  jz      loc_1800A72AC
0x1800a6fda  mov     r12d, 1
0x1800a6fe0  mov     [rsp+1F0h+pOptions.cbSize], 8
0x1800a6fe8  lea     r9, [rsp+1F0h+pOptions]; pOptions
0x1800a6fed  mov     [rsp+1F0h+pOptions.dwFlags], r12d
0x1800a6ff2  xor     r8d, r8d; pDefault
0x1800a6ff5  lea     rdx, [rsp+1F0h+phPrinter]; phPrinter
0x1800a6ffa  mov     rcx, rsi; pPrinterName
0x1800a6ffd  call    cs:__imp_OpenPrinter2W
0x1800a7003  test    eax, eax
0x1800a7005  jnz     loc_1800A7141
0x1800a700b  call    cs:__imp_GetLastError
0x1800a7011  mov     r12, [rsp+1F0h+var_1B8]
0x1800a7016  mov     esi, eax
0x1800a7018  cmp     eax, 5
0x1800a701b  jz      short loc_1800A7097
0x1800a701d  cmp     ebx, 4
0x1800a7020  jnb     short loc_1800A705B
0x1800a7022  cmp     dword ptr [r12], 2
0x1800a7027  jz      short loc_1800A705B
0x1800a7029  cmp     dword ptr [r12], 1
0x1800a702e  jnz     short loc_1800A7097
0x1800a7030  mov     rcx, [rsp+1F0h+servername]; servername
0x1800a7035  lea     r8, [rsp+1F0h+bufptr]; bufptr
0x1800a703a  mov     edx, 64h ; 'd'; level
0x1800a703f  mov     [rsp+1F0h+bufptr], rdi
0x1800a7044  call    cs:__imp_NetServerGetInfo
0x1800a704a  mov     rcx, [rsp+1F0h+bufptr]; Buffer
0x1800a704f  mov     ebx, eax
0x1800a7051  call    cs:__imp_NetApiBufferFree
0x1800a7057  test    ebx, ebx
0x1800a7059  jnz     short loc_1800A7097
0x1800a705b  mov     edi, 1
0x1800a7060  cmp     [r12+8], r13d
0x1800a7065  jz      short loc_1800A7097
0x1800a7067  mov     r9d, esi
0x1800a706a  lea     r8, a0x; "%0x"
0x1800a7071  lea     edx, [rdi+0Ah]; unsigned __int64
0x1800a7074  lea     rcx, [rbp+0F0h+var_168]; unsigned __int16 *
0x1800a7078  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a707d  lea     r9, [rbp+0F0h+var_168]
0x1800a7081  mov     [rsp+1F0h+pcbNeeded], r13
0x1800a7086  mov     r8, r15; unsigned __int16 *
0x1800a7089  lea     rcx, MSG_PRUNING_ABSENT_PRINTER; struct _EVENT_DESCRIPTOR *
0x1800a7090  mov     edx, esi; unsigned int
0x1800a7092  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a7097  mov     rsi, [rsp+1F0h+pPrinterName]
0x1800a709c  lea     r8, [rsp+1F0h+ppObject]; ppObject
0x1800a70a1  mov     rcx, r15; lpszPathName
0x1800a70a4  lea     rdx, IID_IADs; riid
0x1800a70ab  call    cs:__imp_ADsGetObject
0x1800a70b1  test    eax, eax
0x1800a70b3  js      loc_1800A73BD
0x1800a70b9  test    edi, edi
0x1800a70bb  jz      loc_1800A73B3
0x1800a70c1  test    r14d, r14d
0x1800a70c4  jnz     short loc_1800A70DD
0x1800a70c6  mov     edx, [r12+4]; unsigned int
0x1800a70cb  mov     rcx, [rsp+1F0h+ppObject]; struct IADs *
0x1800a70d0  call    ?EnoughRetries@@YAHPEAUIADs@@K@Z; EnoughRetries(IADs *,ulong)
0x1800a70d5  test    eax, eax
0x1800a70d7  jz      loc_1800A73BD
0x1800a70dd  mov     rcx, [rsp+1F0h+ppObject]
0x1800a70e2  lea     rdx, [rsp+1F0h+lpszPathName]
0x1800a70e7  mov     rax, [rcx]
0x1800a70ea  mov     rax, [rax+58h]
0x1800a70ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a70f3  test    eax, eax
0x1800a70f5  js      loc_1800A73BD
0x1800a70fb  mov     rcx, [rsp+1F0h+lpszPathName]; lpszPathName
0x1800a7100  lea     r8, [rsp+1F0h+var_190]; ppObject
0x1800a7105  lea     rdx, IID_IADsContainer; riid
0x1800a710c  call    cs:__imp_ADsGetObject
0x1800a7112  test    eax, eax
0x1800a7114  js      loc_1800A73BD
0x1800a711a  mov     rcx, [rbp+0F0h+var_170]; unsigned __int16 *
0x1800a711e  lea     rdx, Str; ",=\r\n+<>#;\"\\"
0x1800a7125  call    ?CreateEscapedString@@YAPEAGPEBG0@Z; CreateEscapedString(ushort const *,ushort const *)
0x1800a712a  mov     r13, rax
0x1800a712d  test    rax, rax
0x1800a7130  jnz     loc_1800A72F3
0x1800a7136  call    cs:__imp_GetLastError
0x1800a713c  jmp     loc_1800A73BD
0x1800a7141  cmp     ebx, 4
0x1800a7144  jb      loc_1800A72AC
0x1800a714a  mov     rcx, [rsp+1F0h+phPrinter]; hPrinter
0x1800a714f  lea     rax, [rsp+1F0h+pPrinterName]
0x1800a7154  mov     r9d, 100h; cbBuf
0x1800a715a  mov     [rsp+1F0h+pcbNeeded], rax; pcbNeeded
0x1800a715f  lea     r8, [rbp+0F0h+pPrinter]; pPrinter
0x1800a7163  mov     dword ptr [rsp+1F0h+pPrinterName], edi
0x1800a7167  mov     edx, 7; Level
0x1800a716c  call    cs:__imp_GetPrinterW
0x1800a7172  test    eax, eax
0x1800a7174  jnz     short loc_1800A71CC
0x1800a7176  call    cs:__imp_GetLastError
0x1800a717c  cmp     eax, 7Ah ; 'z'
0x1800a717f  jnz     short loc_1800A71C4
0x1800a7181  mov     ecx, dword ptr [rsp+1F0h+pPrinterName]
0x1800a7185  call    cs:__imp_DllAllocSplMem
0x1800a718b  mov     rbx, rax
0x1800a718e  test    rax, rax
0x1800a7191  jz      short loc_1800A71BA
0x1800a7193  mov     r9d, dword ptr [rsp+1F0h+pPrinterName]; cbBuf
0x1800a7198  lea     rax, [rsp+1F0h+pPrinterName]
0x1800a719d  mov     rcx, [rsp+1F0h+phPrinter]; hPrinter
0x1800a71a2  mov     r8, rbx; pPrinter
0x1800a71a5  mov     edx, 7; Level
0x1800a71aa  mov     [rsp+1F0h+pcbNeeded], rax; pcbNeeded
0x1800a71af  call    cs:__imp_GetPrinterW
0x1800a71b5  test    eax, eax
0x1800a71b7  setnz   al
0x1800a71ba  test    al, al
0x1800a71bc  jz      loc_1800A7297
0x1800a71c2  jmp     short loc_1800A71D0
0x1800a71c4  mov     edi, r12d
0x1800a71c7  jmp     loc_1800A72AC
0x1800a71cc  lea     rbx, [rbp+0F0h+pPrinter]
0x1800a71d0  test    [rbx+8], r12b
0x1800a71d4  jnz     short loc_1800A71F8
0x1800a71d6  mov     edi, r12d
0x1800a71d9  call    cs:__imp_GetLastError
0x1800a71df  xor     r9d, r9d
0x1800a71e2  lea     rcx, MSG_PRUNING_UNPUBLISHED_PRINTER; struct _EVENT_DESCRIPTOR *
0x1800a71e9  mov     edx, eax; unsigned int
0x1800a71eb  mov     r8, r15; unsigned __int16 *
0x1800a71ee  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a71f3  jmp     loc_1800A7297
0x1800a71f8  lea     r8, [rsp+1F0h+ppObject]; ppObject
0x1800a71fd  mov     [rsp+1F0h+bufptr], rdi
0x1800a7202  lea     rdx, IID_IADs; riid
0x1800a7209  mov     rcx, r15; lpszPathName
0x1800a720c  call    cs:__imp_ADsGetObject
0x1800a7212  test    eax, eax
0x1800a7214  js      loc_1800A73BD
0x1800a721a  mov     rcx, [rsp+1F0h+ppObject]; struct IADs *
0x1800a721f  lea     rdx, [rsp+1F0h+bufptr]; unsigned __int16 **
0x1800a7224  call    ?GetGUID@@YAJPEAUIADs@@PEAPEAG@Z; GetGUID(IADs *,ushort * *)
0x1800a7229  test    eax, eax
0x1800a722b  js      loc_1800A73BD
0x1800a7231  mov     rax, [rbx]
0x1800a7234  test    rax, rax
0x1800a7237  jz      short loc_1800A7259
0x1800a7239  mov     r8, [rsp+1F0h+bufptr]
0x1800a723e  sub     r8, rax
0x1800a7241  movzx   edx, word ptr [rax]
0x1800a7244  movzx   ecx, word ptr [rax+r8]
0x1800a7249  sub     edx, ecx
0x1800a724b  jnz     short loc_1800A7255
0x1800a724d  add     rax, 2
0x1800a7251  test    ecx, ecx
0x1800a7253  jnz     short loc_1800A7241
0x1800a7255  test    edx, edx
0x1800a7257  jz      short loc_1800A7276
0x1800a7259  mov     edi, r12d
0x1800a725c  call    cs:__imp_GetLastError
0x1800a7262  xor     r9d, r9d
0x1800a7265  lea     rcx, MSG_PRUNING_DUPLICATE_PRINTER; struct _EVENT_DESCRIPTOR *
0x1800a726c  mov     edx, eax; unsigned int
0x1800a726e  mov     r8, r15; unsigned __int16 *
0x1800a7271  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a7276  mov     rcx, [rsp+1F0h+bufptr]
0x1800a727b  call    cs:__imp_DllFreeSplStr
0x1800a7281  mov     rcx, [rsp+1F0h+ppObject]
0x1800a7286  mov     rax, [rcx]
0x1800a7289  mov     rax, [rax+10h]
0x1800a728d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7292  mov     [rsp+1F0h+ppObject], r13
0x1800a7297  lea     rax, [rbp+0F0h+pPrinter]
0x1800a729b  cmp     rbx, rax
0x1800a729e  jz      short loc_1800A72A9
0x1800a72a0  mov     rcx, rbx
0x1800a72a3  call    cs:__imp_DllFreeSplMem
0x1800a72a9  mov     r14d, edi
0x1800a72ac  mov     r12, [rsp+1F0h+var_1B8]
0x1800a72b1  jmp     loc_1800A709C
0x1800a72b6  mov     r14d, r8d
0x1800a72b9  mov     edi, r8d
0x1800a72bc  call    cs:__imp_GetLastError
0x1800a72c2  xor     r9d, r9d
0x1800a72c5  lea     rcx, MSG_PRUNING_NOUNC_PRINTER; struct _EVENT_DESCRIPTOR *
0x1800a72cc  mov     edx, eax; unsigned int
0x1800a72ce  mov     r8, r15; unsigned __int16 *
0x1800a72d1  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a72d6  mov     r12, [rsp+1F0h+var_1B8]
0x1800a72db  jmp     loc_1800A7097
0x1800a72e0  mov     r12, r11
0x1800a72e3  jmp     loc_1800A7097
0x1800a72e8  mov     r12, r11
0x1800a72eb  mov     rsi, rax
0x1800a72ee  jmp     loc_1800A709C
0x1800a72f3  xor     r9d, r9d
0x1800a72f6  lea     rdx, aCn_0; "CN="
0x1800a72fd  mov     r8, rax
0x1800a7300  lea     rcx, [rsp+1F0h+var_180]
0x1800a7305  call    StrCatAlloc
0x1800a730a  mov     ebx, eax
0x1800a730c  test    eax, eax
0x1800a730e  jle     short loc_1800A7319
0x1800a7310  movzx   ebx, ax
0x1800a7313  or      ebx, 80070000h
0x1800a7319  test    ebx, ebx
0x1800a731b  js      short loc_1800A735C
0x1800a731d  mov     rcx, [rsp+1F0h+var_190]
0x1800a7322  lea     rdx, aPrintqueue; "printQueue"
0x1800a7329  mov     r8, [rsp+1F0h+var_180]
  ... truncated ...
```
