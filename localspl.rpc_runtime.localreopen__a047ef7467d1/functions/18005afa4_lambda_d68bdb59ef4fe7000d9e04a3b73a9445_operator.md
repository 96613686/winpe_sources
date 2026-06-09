# _lambda_d68bdb59ef4fe7000d9e04a3b73a9445_::operator()

- ea: `0x18005afa4`
- end: `0x18005b696`
- name: `_lambda_d68bdb59ef4fe7000d9e04a3b73a9445_::operator()`
- size: `1778`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18005bef0`

## callees

- `0x1800051f0`
- `0x180005290`
- `0x180007e94`
- `0x180008520`
- `0x180008560`
- `0x18000a8f0`
- `0x18000ea40`
- `0x180014dd4`
- `0x180022264`
- `0x180038434`
- `0x180038550`
- `0x180038698`
- `0x18003e984`
- `0x18003ea2c`
- `0x1800430b8`
- `0x180046650`
- `0x18005afa4`
- `0x1800ca63c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b2ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b622`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b1b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b375`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b673`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b1b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b375`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005b673`
- `SPOOLSS!DllFreeSplMem` at `0x18005b36a`
- `SPOOLSS!DllFreeSplMem` at `0x18005b4e0`
- `SPOOLSS!DllFreeSplMem` at `0x18005b52d`
- `SPOOLSS!DllFreeSplMem` at `0x18005b551`
- `SPOOLSS!DllFreeSplMem` at `0x18005b5aa`
- `SPOOLSS!DllFreeSplMem` at `0x18005b36a`
- `SPOOLSS!DllFreeSplMem` at `0x18005b4e0`
- `SPOOLSS!DllFreeSplMem` at `0x18005b52d`
- `SPOOLSS!DllFreeSplMem` at `0x18005b551`
- `SPOOLSS!DllFreeSplMem` at `0x18005b5aa`
- `SPOOLSS!CheckLocalCall` at `0x18005b233`
- `SPOOLSS!CheckLocalCall` at `0x18005b233`
- `SPOOLSS!PackStrings` at `0x18005b21b`
- `SPOOLSS!PackStrings` at `0x18005b21b`

## string_xrefs

- `0x18005b565`: `Failed to copy iniPrinter data during enumeration.  Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_d68bdb59ef4fe7000d9e04a3b73a9445_::operator()(unsigned __int8 ***a1)
{
  unsigned __int8 *v2; // rsi
  __int64 v3; // r15
  unsigned int v4; // r12d
  void *v5; // rdi
  int v6; // r14d
  const char *v7; // r9
  void *v8; // rcx
  const WCHAR *v9; // rcx
  unsigned __int16 *v10; // r13
  const WCHAR *v11; // rcx
  const char *v12; // r9
  const char *v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  struct _INISPOOLER *v16; // r8
  __int64 v17; // rcx
  unsigned __int8 **v18; // rcx
  _DWORD *v19; // rcx
  __int64 v20; // rsi
  int v21; // edx
  unsigned int PrinterSize; // edi
  __int64 v23; // rcx
  __int64 v24; // rsi
  unsigned __int8 *v25; // r15
  int v26; // edx
  void *v28; // rcx
  DWORD v29; // eax
  void *v30; // rcx
  const char *v31; // r9
  DWORD LastError; // eax
  const char *v33; // r9
  const char *v34; // r9
  int v35; // [rsp+60h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-31h] BYREF
  int v37; // [rsp+70h] [rbp-29h]
  void *v38; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v39[2]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v40; // [rsp+88h] [rbp-11h] BYREF
  __int128 v41; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = **a1;
  v3 = (__int64)*a1[1];
  v4 = 0;
  v5 = 0;
  v38 = 0;
  v39[1] = 0;
  v6 = 0;
  v35 = 0;
  v39[0] = 0;
  *(_DWORD *)*a1[2] = 0;
  *(_DWORD *)*a1[3] = 0;
  TokenHandle = (void *)-1LL;
  if ( !(unsigned int)GetTokenHandle(&TokenHandle) )
  {
    *(_DWORD *)a1[4] = 0;
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7CC,
      (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
      v7);
  }
  v8 = TokenHandle;
  if ( TokenHandle == (void *)-1LL )
    v8 = 0;
  if ( (unsigned int)ValidateObjectAccessWithToken(v8, 0, 1u, 0, 0, v3, 1, 0) )
  {
    v37 = 1;
  }
  else
  {
    v37 = 0;
    if ( !(unsigned int)ValidateObjectAccess(0, 2, 0, 0, v3, 1) )
    {
      *(_DWORD *)a1[4] = 0;
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x7D6,
        (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
        v13);
    }
  }
  if ( (*(_BYTE *)a1[5] & 8) != 0 )
  {
    v9 = (const WCHAR *)*a1[6];
    if ( v9 )
    {
      if ( *v9 )
      {
        if ( (unsigned int)FastStrcmpi(v9) && !(unsigned int)MyName((LPCWSTR)*a1[6]) )
        {
          LastError = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "SplEnumPrinters::<lambda_d68bdb59ef4fe7000d9e04a3b73a9445>::operator ()",
            L"Name is neither the local print provider nor the local server.  Failing call.  Error %d",
            LastError);
          *(_DWORD *)a1[4] = 0;
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x7E2,
            (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
            v33);
        }
        *(_DWORD *)a1[5] |= 2u;
        *(_DWORD *)a1[5] &= ~0x10u;
      }
    }
  }
  if ( (*(_BYTE *)a1[5] & 0x10) != 0 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplEnumPrinters::<lambda_d68bdb59ef4fe7000d9e04a3b73a9445>::operator ()",
      L"Cannot enumerate remote printers via the local print provider.  Failing call.  Error ERROR_INVALID_NAME");
    SetLastError(0x7Bu);
    *(_DWORD *)a1[4] = 0;
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7F7,
      (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
      v34);
  }
  v10 = 0;
  v11 = (const WCHAR *)*a1[6];
  if ( v11 && *v11 && (unsigned int)MyName(v11) )
    v10 = (unsigned __int16 *)*a1[6];
  if ( *(_DWORD *)a1[7] == 1 && (*(_BYTE *)a1[5] & 0x40) != 0 )
  {
    *(_DWORD *)a1[4] = EnumerateNetworkPrinters(
                         **a1,
                         *(_DWORD *)a1[8],
                         (unsigned int *)*a1[2],
                         (unsigned int *)*a1[3],
                         (struct _INISPOOLER *)v3);
    if ( !*(_DWORD *)a1[4] )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x80E,
        (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
        v12);
    return NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  }
  EnterSplSem(1);
  if ( *(_DWORD *)a1[7] == 1 && (*(_BYTE *)a1[5] & 8) != 0 && !*a1[6] )
  {
    v40 = 0;
    v41 = 0;
    *(_DWORD *)*a1[2] = 202;
    if ( *(_DWORD *)a1[8] < 0xCAu )
    {
LABEL_27:
      SetLastError(0x7Au);
      LeaveSplSem(v17);
      goto LABEL_28;
    }
    *(_DWORD *)*a1[3] = 1;
    *(_DWORD *)v2 = 98304;
    *(_QWORD *)&v40 = L"Windows NT Local Printers";
    *((_QWORD *)&v40 + 1) = L"Windows NT Local Print Providor";
    *(_QWORD *)&v41 = L"Locally connected Printers";
    PackStrings(&v40, **a1, L"\b", &(**a1)[*(unsigned int *)a1[8]]);
    goto LABEL_72;
  }
  if ( (*(_BYTE *)a1[5] & 0xA) != 0 )
  {
    if ( (unsigned int)CheckLocalCall(v15, v14) == 1 )
    {
      v19 = a1[5];
      if ( (*v19 & 0x20) == 0 && !v37 )
        *v19 |= 0x20u;
    }
    v20 = *(_QWORD *)(v3 + 40);
    if ( v20 )
    {
      do
      {
        if ( (unsigned int)EnumThisPrinter(*(_DWORD *)a1[5], (struct _INIPRINTER *)v20, v16) )
        {
          v21 = (int)TokenHandle;
          if ( TokenHandle == (void *)-1LL )
            v21 = 0;
          if ( (unsigned int)ShowThisPrinter(v20, v21, v37, *(_DWORD *)a1[5], &v38, &v39[1], &v35, (__int64)v39) )
          {
            PrinterSize = GetPrinterSize(
                            (struct _INIPRINTER *)v20,
                            *(_DWORD *)a1[7],
                            *(_DWORD *)a1[5],
                            v10,
                            *(struct _devicemodeW **)(v20 + 104),
                            0,
                            1,
                            *(_DWORD *)(v20 + 152) & 0x400000);
            if ( GetLastError() == 534 || PrinterSize + v4 < v4 )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "SplEnumPrinters::<lambda_d68bdb59ef4fe7000d9e04a3b73a9445>::operator ()",
                L"Returning from SplEnumPrinters(), because of Integer Overflow.");
              SetLastError(0x216u);
              v30 = v38;
              if ( v38 && v35 )
                DllFreeSplMem(v38);
              LeaveSplSem(v30);
              *(_DWORD *)a1[4] = 0;
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x862,
                (unsigned int)"printscan\\print\\spooler\\localspl\\getprn.c",
                v31);
            }
            v4 += PrinterSize;
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "SplEnumPrinters::<lambda_d68bdb59ef4fe7000d9e04a3b73a9445>::operator ()",
              L"In SplEnumPrinters, cb size required  = %d");
          }
        }
        v20 = *(_QWORD *)(v20 + 8);
      }
      while ( v20 );
      v5 = v38;
      v6 = v35;
    }
  }
  *(_DWORD *)*a1[2] = v4;
  v18 = (unsigned __int8 **)*(unsigned int *)a1[8];
  if ( v4 > (unsigned int)v18 )
  {
    if ( v5 && v6 )
      DllFreeSplMem(v5);
    SetLastError(0x7Au);
    LeaveSplSem(v23);
    *(_DWORD *)a1[4] = 0;
    return NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  }
  if ( (*(_BYTE *)a1[5] & 0xA) == 0 || (v24 = *(_QWORD *)(v3 + 40), v25 = (unsigned __int8 *)v18 + (_QWORD)**a1, !v24) )
  {
LABEL_69:
    if ( v5 && v6 )
      DllFreeSplMem(v5);
LABEL_72:
    LeaveSplSem(v18);
    *(_DWORD *)a1[4] = 1;
    return NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
  }
  while ( 1 )
  {
    if ( !(unsigned int)EnumThisPrinter(*(_DWORD *)a1[5], (struct _INIPRINTER *)v24, v16) )
      goto LABEL_67;
    v26 = (int)TokenHandle;
    if ( TokenHandle == (void *)-1LL )
      v26 = 0;
    if ( !(unsigned int)ShowThisPrinter(v24, v26, v37, *(_DWORD *)a1[5], &v38, &v39[1], &v35, (__int64)v39) )
      goto LABEL_67;
    v25 = CopyIniPrinterToPrinter(
            (struct _INIPRINTER *)v24,
            *(_DWORD *)a1[7],
            **a1,
            v25,
            0,
            v10,
            0,
            0,
            *(struct _devicemodeW **)(v24 + 104),
            1,
            *(_DWORD *)(v24 + 152) & 0x400000);
    if ( !v25 )
      break;
    ++*(_DWORD *)*a1[3];
    v18 = a1[7];
    switch ( *(_DWORD *)v18 )
    {
      case 0:
        goto LABEL_64;
      case 1:
        goto LABEL_62;
      case 2:
LABEL_64:
        **a1 += 136;
        break;
      case 4:
        **a1 += 24;
        break;
      case 5:
LABEL_62:
        **a1 += 32;
        break;
    }
    if ( **a1 && **a1 > v25 )
    {
      if ( v38 && v35 )
        DllFreeSplMem(v38);
      *(_DWORD *)*a1[3] = 0;
      goto LABEL_27;
    }
LABEL_67:
    v24 = *(_QWORD *)(v24 + 8);
    if ( !v24 )
    {
      v5 = v38;
      v6 = v35;
      goto LABEL_69;
    }
  }
  v28 = v38;
  if ( v38 && v35 )
    DllFreeSplMem(v38);
  LeaveSplSem(v28);
  v29 = GetLastError();
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "SplEnumPrinters::<lambda_d68bdb59ef4fe7000d9e04a3b73a9445>::operator ()",
    L"Failed to copy iniPrinter data during enumeration.  Error %d",
    v29);
LABEL_28:
  *(_DWORD *)a1[4] = 0;
  return NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&TokenHandle);
}

```

## disassembly

```asm
0x18005afa4  push    rbp
0x18005afa6  push    rbx
0x18005afa7  push    rsi
0x18005afa8  push    rdi
0x18005afa9  push    r12
0x18005afab  push    r13
0x18005afad  push    r14
0x18005afaf  push    r15
0x18005afb1  lea     rbp, [rsp-1Fh]
0x18005afb6  sub     rsp, 0B8h
0x18005afbd  mov     rax, cs:__security_cookie
0x18005afc4  xor     rax, rsp
0x18005afc7  mov     [rbp+57h+var_48], rax
0x18005afcb  mov     rbx, rcx
0x18005afce  mov     rax, [rcx]
0x18005afd1  mov     rsi, [rax]
0x18005afd4  mov     rax, [rcx+8]
0x18005afd8  mov     r15, [rax]
0x18005afdb  xor     r12d, r12d
0x18005afde  mov     edi, r12d
0x18005afe1  mov     [rbp+57h+var_78], r12
0x18005afe5  mov     [rbp+57h+var_70+4], r12d
0x18005afe9  mov     r14d, r12d
0x18005afec  mov     [rbp+57h+var_90], r12d
0x18005aff0  mov     [rbp+57h+var_70], r12d
0x18005aff4  mov     rax, [rcx+10h]
0x18005aff8  mov     rcx, [rax]
0x18005affb  mov     [rcx], r12d
0x18005affe  mov     rax, [rbx+18h]
0x18005b002  mov     rcx, [rax]
0x18005b005  mov     [rcx], r12d
0x18005b008  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18005b010  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18005b014  call    GetTokenHandle
0x18005b019  test    eax, eax
0x18005b01b  jz      loc_18005B605
0x18005b021  mov     rcx, [rbp+57h+TokenHandle]
0x18005b025  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005b029  cmovz   rcx, r12; TokenHandle
0x18005b02d  mov     [rsp+0F0h+var_B8], r12d; int
0x18005b032  lea     r13d, [r12+1]
0x18005b037  mov     dword ptr [rsp+0F0h+var_C0], r13d; int
0x18005b03c  mov     [rsp+0F0h+var_C8], r15; __int64
0x18005b041  mov     [rsp+0F0h+var_D0], r12; __int64
0x18005b046  xor     r9d, r9d
0x18005b049  mov     r8d, r13d
0x18005b04c  xor     edx, edx
0x18005b04e  call    ValidateObjectAccessWithToken
0x18005b053  test    eax, eax
0x18005b055  jz      loc_18005B132
0x18005b05b  mov     [rbp+57h+var_80], r13d
0x18005b05f  mov     rax, [rbx+28h]
0x18005b063  test    byte ptr [rax], 8
0x18005b066  jz      short loc_18005B0AF
0x18005b068  mov     rax, [rbx+30h]
0x18005b06c  mov     rcx, [rax]; lpString1
0x18005b06f  test    rcx, rcx
0x18005b072  jz      short loc_18005B0AF
0x18005b074  cmp     [rcx], r12w
0x18005b078  jz      short loc_18005B0AF
0x18005b07a  lea     rdx, aWindowsNtLocal; "Windows NT Local Print Providor"
0x18005b081  call    FastStrcmpi
0x18005b086  test    eax, eax
0x18005b088  jz      short loc_18005B0A1
0x18005b08a  mov     rcx, [rbx+30h]
0x18005b08e  mov     rdx, r15
0x18005b091  mov     rcx, [rcx]; lpString1
0x18005b094  call    MyName
0x18005b099  test    eax, eax
0x18005b09b  jz      loc_18005B622
0x18005b0a1  mov     rax, [rbx+28h]
0x18005b0a5  or      dword ptr [rax], 2
0x18005b0a8  mov     rax, [rbx+28h]
0x18005b0ac  and     dword ptr [rax], 0FFFFFFEFh
0x18005b0af  mov     rax, [rbx+28h]
0x18005b0b3  test    byte ptr [rax], 10h
0x18005b0b6  jnz     loc_18005B65B
0x18005b0bc  mov     r13, r12
0x18005b0bf  mov     rax, [rbx+30h]
0x18005b0c3  mov     rcx, [rax]; lpString1
0x18005b0c6  test    rcx, rcx
0x18005b0c9  jz      short loc_18005B0E4
0x18005b0cb  cmp     [rcx], r12w
0x18005b0cf  jz      short loc_18005B0E4
0x18005b0d1  mov     rdx, r15
0x18005b0d4  call    MyName
0x18005b0d9  test    eax, eax
0x18005b0db  jz      short loc_18005B0E4
0x18005b0dd  mov     rax, [rbx+30h]
0x18005b0e1  mov     r13, [rax]
0x18005b0e4  mov     rax, [rbx+38h]
0x18005b0e8  cmp     dword ptr [rax], 1
0x18005b0eb  jnz     short loc_18005B15E
0x18005b0ed  mov     rax, [rbx+28h]
0x18005b0f1  test    byte ptr [rax], 40h
0x18005b0f4  jz      short loc_18005B15E
0x18005b0f6  mov     r9, [rbx+18h]
0x18005b0fa  mov     r8, [rbx+10h]
0x18005b0fe  mov     rdx, [rbx+40h]
0x18005b102  mov     rcx, [rbx]
0x18005b105  mov     [rsp+0F0h+var_D0], r15; struct _INISPOOLER *
0x18005b10a  mov     r9, [r9]; unsigned int *
0x18005b10d  mov     r8, [r8]; unsigned int *
0x18005b110  mov     edx, [rdx]; unsigned int
0x18005b112  mov     rcx, [rcx]; unsigned __int8 *
0x18005b115  call    ?EnumerateNetworkPrinters@@YAHPEAEKPEAK1PEAU_INISPOOLER@@@Z; EnumerateNetworkPrinters(uchar *,ulong,ulong *,ulong *,_INISPOOLER *)
0x18005b11a  mov     rcx, [rbx+20h]
0x18005b11e  mov     [rcx], eax
0x18005b120  mov     rax, [rbx+20h]
0x18005b124  cmp     [rax], r12d
0x18005b127  jz      loc_18005B5D2
0x18005b12d  jmp     loc_18005B4F5
0x18005b132  mov     [rbp+57h+var_80], r12d
0x18005b136  mov     dword ptr [rsp+0F0h+var_C8], r13d
0x18005b13b  mov     [rsp+0F0h+var_D0], r15
0x18005b140  xor     r9d, r9d
0x18005b143  xor     r8d, r8d
0x18005b146  lea     edx, [r9+2]
0x18005b14a  xor     ecx, ecx
0x18005b14c  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x18005b151  test    eax, eax
0x18005b153  jz      loc_18005B5E8
0x18005b159  jmp     loc_18005B05F
0x18005b15e  mov     ecx, 1
0x18005b163  call    EnterSplSem
0x18005b168  mov     rax, [rbx+38h]
0x18005b16c  cmp     dword ptr [rax], 1
0x18005b16f  jnz     loc_18005B226
0x18005b175  mov     rax, [rbx+28h]
0x18005b179  test    byte ptr [rax], 8
0x18005b17c  jz      loc_18005B226
0x18005b182  mov     rax, [rbx+30h]
0x18005b186  cmp     [rax], r12
0x18005b189  jnz     loc_18005B226
0x18005b18f  xorps   xmm0, xmm0
0x18005b192  movups  [rbp+57h+var_68], xmm0
0x18005b196  movups  [rbp+57h+var_58], xmm0
0x18005b19a  mov     rax, [rbx+10h]
0x18005b19e  mov     rcx, [rax]
0x18005b1a1  mov     edx, 0CAh
0x18005b1a6  mov     [rcx], edx
0x18005b1a8  mov     rax, [rbx+40h]
0x18005b1ac  cmp     [rax], edx
0x18005b1ae  jnb     short loc_18005B1CC
0x18005b1b0  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18005b1b5  call    cs:__imp_SetLastError
0x18005b1bb  call    LeaveSplSem
0x18005b1c0  mov     rax, [rbx+20h]
0x18005b1c4  mov     [rax], r12d
0x18005b1c7  jmp     loc_18005B4F5
0x18005b1cc  mov     rax, [rbx+18h]
0x18005b1d0  mov     rcx, [rax]
0x18005b1d3  mov     dword ptr [rcx], 1
0x18005b1d9  mov     dword ptr [rsi], 18000h
0x18005b1df  lea     rax, aWindowsNtLocal_0; "Windows NT Local Printers"
0x18005b1e6  mov     qword ptr [rbp+57h+var_68], rax
0x18005b1ea  lea     rax, aWindowsNtLocal; "Windows NT Local Print Providor"
0x18005b1f1  mov     qword ptr [rbp+57h+var_68+8], rax
0x18005b1f5  lea     rax, aLocallyConnect; "Locally connected Printers"
0x18005b1fc  mov     qword ptr [rbp+57h+var_58], rax
0x18005b200  mov     rax, [rbx]
0x18005b203  mov     rdx, [rax]
0x18005b206  mov     rax, [rbx+40h]
0x18005b20a  mov     r9d, [rax]
0x18005b20d  add     r9, rdx
0x18005b210  lea     r8, ?PrinterInfo1Strings@@3QBKB; "\b"
0x18005b217  lea     rcx, [rbp+57h+var_68]
0x18005b21b  call    cs:__imp_PackStrings
0x18005b221  jmp     loc_18005B4E6
0x18005b226  mov     rax, [rbx+28h]
0x18005b22a  test    byte ptr [rax], 0Ah
0x18005b22d  jz      loc_18005B348
0x18005b233  call    cs:__imp_CheckLocalCall
0x18005b239  cmp     eax, 1
0x18005b23c  jnz     short loc_18005B253
0x18005b23e  mov     rcx, [rbx+28h]
0x18005b242  mov     eax, [rcx]
0x18005b244  test    al, 20h
0x18005b246  jnz     short loc_18005B253
0x18005b248  cmp     [rbp+57h+var_80], 0
0x18005b24c  jnz     short loc_18005B253
0x18005b24e  or      eax, 20h
0x18005b251  mov     [rcx], eax
0x18005b253  mov     rsi, [r15+28h]
0x18005b257  test    rsi, rsi
0x18005b25a  jz      loc_18005B348
0x18005b260  xor     r14d, r14d
0x18005b263  mov     rcx, [rbx+28h]
0x18005b267  mov     rdx, rsi; struct _INIPRINTER *
0x18005b26a  mov     ecx, [rcx]; unsigned int
0x18005b26c  call    ?EnumThisPrinter@@YAHKPEAU_INIPRINTER@@PEAU_INISPOOLER@@@Z; EnumThisPrinter(ulong,_INIPRINTER *,_INISPOOLER *)
0x18005b271  test    eax, eax
0x18005b273  jz      loc_18005B333
0x18005b279  mov     rax, [rbx+28h]
0x18005b27d  mov     r9d, [rax]; int
0x18005b280  mov     rdx, [rbp+57h+TokenHandle]
0x18005b284  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005b288  cmovz   rdx, r14; int
0x18005b28c  lea     rax, [rbp+57h+var_70]
0x18005b290  mov     qword ptr [rsp+0F0h+var_B8], rax; __int64
0x18005b295  lea     rax, [rbp+57h+var_90]
0x18005b299  mov     [rsp+0F0h+var_C0], rax; int *
0x18005b29e  lea     rax, [rbp+57h+var_70+4]
0x18005b2a2  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18005b2a7  lea     rax, [rbp+57h+var_78]
0x18005b2ab  mov     [rsp+0F0h+var_D0], rax; void **
0x18005b2b0  mov     r8d, [rbp+57h+var_80]; int
0x18005b2b4  mov     rcx, rsi; int
0x18005b2b7  call    ShowThisPrinter
0x18005b2bc  test    eax, eax
0x18005b2be  jz      short loc_18005B333
0x18005b2c0  mov     eax, [rsi+98h]
0x18005b2c6  and     eax, 400000h
0x18005b2cb  mov     r8, [rbx+28h]
0x18005b2cf  mov     rdx, [rbx+38h]
0x18005b2d3  mov     [rsp+0F0h+var_B8], eax; int
0x18005b2d7  mov     dword ptr [rsp+0F0h+var_C0], 1; int
0x18005b2df  mov     [rsp+0F0h+var_C8], r14; struct _PRINTER_INFO_2W *
0x18005b2e4  mov     rax, [rsi+68h]
0x18005b2e8  mov     [rsp+0F0h+var_D0], rax; struct _devicemodeW *
0x18005b2ed  mov     r9, r13; unsigned __int16 *
0x18005b2f0  mov     r8d, [r8]; unsigned int
0x18005b2f3  mov     edx, [rdx]; unsigned int
0x18005b2f5  mov     rcx, rsi; struct _INIPRINTER *
0x18005b2f8  call    ?GetPrinterSize@@YAKPEAU_INIPRINTER@@KKPEAGPEAU_devicemodeW@@PEAU_PRINTER_INFO_2W@@HH@Z; GetPrinterSize(_INIPRINTER *,ulong,ulong,ushort *,_devicemodeW *,_PRINTER_INFO_2W *,int,int)
0x18005b2fd  mov     edi, eax
0x18005b2ff  call    cs:__imp_GetLastError
0x18005b305  cmp     eax, 216h
0x18005b30a  jz      loc_18005B57D
0x18005b310  lea     r8d, [rdi+r12]
0x18005b314  cmp     r8d, r12d
0x18005b317  jb      loc_18005B57D
0x18005b31d  mov     r12d, r8d
0x18005b320  lea     rdx, aInSplenumprint; "In SplEnumPrinters, cb size required  ="...
0x18005b327  lea     rcx, aSplenumprinter_10; "SplEnumPrinters::<lambda_d68bdb59ef4fe7"...
0x18005b32e  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18005b333  mov     rsi, [rsi+8]
0x18005b337  test    rsi, rsi
0x18005b33a  jnz     loc_18005B263
0x18005b340  mov     rdi, [rbp+57h+var_78]
0x18005b344  mov     r14d, [rbp+57h+var_90]
0x18005b348  mov     rax, [rbx+10h]
0x18005b34c  mov     rdx, [rax]
0x18005b34f  mov     [rdx], r12d
0x18005b352  mov     rax, [rbx+40h]
0x18005b356  mov     ecx, [rax]
0x18005b358  cmp     r12d, ecx
0x18005b35b  jbe     short loc_18005B38F
0x18005b35d  test    rdi, rdi
0x18005b360  jz      short loc_18005B370
0x18005b362  test    r14d, r14d
0x18005b365  jz      short loc_18005B370
0x18005b367  mov     rcx, rdi
0x18005b36a  call    cs:__imp_DllFreeSplMem
0x18005b370  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18005b375  call    cs:__imp_SetLastError
0x18005b37b  call    LeaveSplSem
0x18005b380  mov     rax, [rbx+20h]
0x18005b384  mov     dword ptr [rax], 0
0x18005b38a  jmp     loc_18005B4F5
0x18005b38f  mov     rax, [rbx+28h]
0x18005b393  test    byte ptr [rax], 0Ah
0x18005b396  jz      loc_18005B4D3
0x18005b39c  mov     rsi, [r15+28h]
0x18005b3a0  mov     r15, rcx
0x18005b3a3  mov     rax, [rbx]
0x18005b3a6  add     r15, [rax]
0x18005b3a9  xor     r12d, r12d
0x18005b3ac  test    rsi, rsi
0x18005b3af  jz      loc_18005B4D3
0x18005b3b5  mov     edi, 88h
0x18005b3ba  mov     rcx, [rbx+28h]
0x18005b3be  mov     rdx, rsi; struct _INIPRINTER *
0x18005b3c1  mov     ecx, [rcx]; unsigned int
0x18005b3c3  call    ?EnumThisPrinter@@YAHKPEAU_INIPRINTER@@PEAU_INISPOOLER@@@Z; EnumThisPrinter(ulong,_INIPRINTER *,_INISPOOLER *)
0x18005b3c8  test    eax, eax
0x18005b3ca  jz      loc_18005B4BE
0x18005b3d0  mov     rax, [rbx+28h]
0x18005b3d4  mov     r9d, [rax]; int
0x18005b3d7  mov     rdx, [rbp+57h+TokenHandle]
0x18005b3db  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005b3df  cmovz   rdx, r12; int
0x18005b3e3  lea     rax, [rbp+57h+var_70]
0x18005b3e7  mov     qword ptr [rsp+0F0h+var_B8], rax; __int64
0x18005b3ec  lea     rax, [rbp+57h+var_90]
0x18005b3f0  mov     [rsp+0F0h+var_C0], rax; int *
0x18005b3f5  lea     rax, [rbp+57h+var_70+4]
0x18005b3f9  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x18005b3fe  lea     rax, [rbp+57h+var_78]
0x18005b402  mov     [rsp+0F0h+var_D0], rax; void **
0x18005b407  mov     r8d, [rbp+57h+var_80]; int
0x18005b40b  mov     rcx, rsi; int
0x18005b40e  call    ShowThisPrinter
0x18005b413  test    eax, eax
0x18005b415  jz      loc_18005B4BE
0x18005b41b  mov     eax, [rsi+98h]
0x18005b421  and     eax, 400000h
0x18005b426  mov     r8, [rbx]
0x18005b429  mov     rdx, [rbx+38h]
0x18005b42d  mov     [rsp+0F0h+var_A0], eax; int
  ... truncated ...
```
