# _lambda_2ac9aa54c7f3cc855bb3c08927cd909e_::operator()

- ea: `0x18004f67c`
- end: `0x18004fc1e`
- name: `_lambda_2ac9aa54c7f3cc855bb3c08927cd909e_::operator()`
- size: `1442`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004f4b4`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x18000fb8c`
- `0x180011f00`
- `0x180012510`
- `0x180014d9c`
- `0x180014dd4`
- `0x18001683c`
- `0x180017c3c`
- `0x180017e4c`
- `0x18001860c`
- `0x1800187a8`
- `0x18003aad0`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x18004f67c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f7dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004f7dc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004f9b0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004f9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004facd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004facd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fb84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fb52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fb52`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004fb76`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004fb76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f766`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f9ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f766`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f9ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fbc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fbdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fbc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fbdd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004faab`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004fae8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004faab`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004fae8`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004fa7d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18004fa7d`
- `SPOOLSS!RevertToPrinterSelf` at `0x18004f719`
- `SPOOLSS!RevertToPrinterSelf` at `0x18004fafb`
- `SPOOLSS!RevertToPrinterSelf` at `0x18004f719`
- `SPOOLSS!RevertToPrinterSelf` at `0x18004fafb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004fadb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004fbae`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004fadb`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18004fbae`

## string_xrefs

- `0x18004fa0f`: `Unable to create key for queue '%ws', cVersion=%u, pszV4PrinterDriverDirectory='%ws'`
- `0x18004fb21`: `Failed to open client process %u for handle duplication: %d`

## pseudocode

```c
void __fastcall lambda_2ac9aa54c7f3cc855bb3c08927cd909e_::operator()(__int64 a1)
{
  unsigned int SidAsString; // eax
  int v3; // edx
  unsigned int v4; // eax
  int v5; // edx
  HANDLE v6; // rax
  LSTATUS *v7; // rcx
  void *v8; // r13
  BOOL v9; // edi
  _QWORD *v10; // rcx
  _DWORD *v11; // rbx
  _DWORD *v12; // rax
  _DWORD *v13; // rax
  __int64 v14; // rbx
  _QWORD *v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // r14
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // eax
  int v22; // r11d
  unsigned __int64 v23; // rcx
  _DWORD *v24; // r10
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  unsigned int *v28; // r10
  unsigned __int16 *v29; // rdi
  _DWORD *v30; // rbx
  _DWORD *v31; // rax
  const wchar_t *v32; // rcx
  _DWORD *v33; // rax
  LSTATUS *v34; // rbx
  RPC_STATUS *v35; // rax
  _DWORD *v36; // rax
  __int64 v37; // r14
  DWORD v38; // edi
  HANDLE v39; // rax
  HANDLE v40; // rax
  HANDLE v41; // rax
  DWORD *v42; // rbx
  HKEY v43; // rbx
  HANDLE *v44; // rdi
  HANDLE CurrentProcess; // rax
  DWORD *v46; // rbx
  NCoreLibrary::TString *v47; // rcx
  unsigned __int64 v48; // rdx
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v56[56]; // [rsp+88h] [rbp-78h] BYREF
  DWORD dwProcessId; // [rsp+C0h] [rbp-40h]
  _BYTE v58[64]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v59[260]; // [rsp+130h] [rbp+30h] BYREF
  char v60; // [rsp+338h] [rbp+238h] BYREF

  ***(_QWORD ***)a1 = 0;
  NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v58, 0, 1);
  lpSubKey = &NCoreLibrary::TString::gszNullState;
  SidAsString = NSecurityLibrary::TSidUserContext::GetSidAsString(
                  (NSecurityLibrary::TSidUserContext *)v58,
                  (struct TString *)&lpSubKey);
  **(_DWORD **)(a1 + 8) = NCoreLibrary::StatusFromHResult((NCoreLibrary *)SidAsString, v3);
  if ( !**(_DWORD **)(a1 + 8) )
  {
    v4 = NCoreLibrary::TString::Cat(
           (NCoreLibrary::TString *)&lpSubKey,
           L"_Classes\\Local Settings\\Printers\\PropertyBags");
    **(_DWORD **)(a1 + 8) = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v4, v5);
  }
  v6 = RevertToPrinterSelf();
  v7 = *(LSTATUS **)(a1 + 8);
  v8 = v6;
  hKey = 0;
  if ( !*v7 )
    *v7 = RegCreateKeyExW(HKEY_USERS, lpSubKey, 0, 0, 0, 0xCu, 0, &hKey, 0);
  v9 = 0;
  if ( !**(_DWORD **)(a1 + 8) )
  {
    v10 = *(_QWORD **)(a1 + 16);
    v11 = *(_DWORD **)(a1 + 8);
    v49 = 0;
    LODWORD(v50) = 0;
    *v11 = SplGetPrinterData(
             *v10,
             (unsigned int)L"V4_UserPropertyBagScope",
             (unsigned int)&v49,
             (unsigned int)v59,
             8,
             (char)&v50);
    v12 = *(_DWORD **)(a1 + 8);
    if ( *v12 == 2 )
    {
      *v12 = 0;
    }
    else if ( !*v12 && v49 == 1 )
    {
      v9 = _o__wcsicmp(L"Manufacturer", v59) == 0;
    }
  }
  v13 = *(_DWORD **)(a1 + 8);
  phkResult = 0;
  if ( !*v13 )
  {
    v14 = **(_QWORD **)(a1 + 16);
    EnterSplSem(0);
    v15 = *(_QWORD **)(v14 + 64);
    if ( (unsigned int)ValidateSpoolHandle(v14, 16)
      && v15
      && (v16 = v15[11]) != 0
      && (v17 = *(_QWORD *)(v14 + 168)) != 0
      && (*(_BYTE *)(*(_QWORD *)(v14 + 64) + 136LL) & 0x30) == 0 )
    {
      v18 = 0;
      if ( *(_DWORD *)(v16 + 236) >= 4u )
      {
        if ( v9 )
        {
          v19 = StringCchCopyW(v59, 0x104u, L"Manufacturers\\");
          v21 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v19, v20);
          v22 = 0;
          **(_DWORD **)(a1 + 8) = v21;
          v23 = 0;
          v24 = *(_DWORD **)(a1 + 8);
          v54 = 0;
          if ( !*v24 )
          {
            v25 = StringCchLengthW(v59, 0x104u, &v54);
            v27 = NCoreLibrary::StatusFromHResult((NCoreLibrary *)v25, v26);
            v23 = v54;
            *v28 = v27;
          }
          if ( **(_DWORD **)(a1 + 8) == v22 )
          {
            v49 = v22;
            v29 = &v59[v23];
            LODWORD(v50) = v22;
            LeaveSplSem(v23);
            v30 = *(_DWORD **)(a1 + 8);
            *v30 = SplGetPrinterData(
                     **(_QWORD **)(a1 + 16),
                     (unsigned int)L"V4_Manufacturer",
                     (unsigned int)&v49,
                     (_DWORD)v29,
                     2 * (4 - (unsigned __int8)v54),
                     (char)&v50);
            EnterSplSem(0);
            v31 = *(_DWORD **)(a1 + 8);
            if ( !*v31 )
            {
              v18 = v59;
              if ( v29 >= (unsigned __int16 *)&v60 )
              {
LABEL_29:
                if ( v29 == (unsigned __int16 *)&v60 )
                  *v31 = 13;
              }
              else
              {
                while ( *v29 )
                {
                  if ( *v29 == 92 )
                    *v29 = 44;
                  if ( ++v29 >= (unsigned __int16 *)&v60 )
                    goto LABEL_29;
                }
              }
            }
          }
        }
        else if ( (*(_DWORD *)(v17 + 168) & 0x4000000) != 0 )
        {
          v18 = (unsigned __int16 *)v15[3];
        }
        else
        {
          v32 = (const wchar_t *)v15[61];
          if ( v32 )
            v18 = wcsrchr(v32, 0x5Cu) + 1;
        }
      }
      else
      {
        **(_DWORD **)(a1 + 8) = 50;
      }
      v33 = *(_DWORD **)(a1 + 8);
      if ( *v33 || !v18 )
      {
        *v33 = 50;
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SplGetUserPropertyBag::<lambda_2ac9aa54c7f3cc855bb3c08927cd909e>::operator ()",
          L"Unable to create key for queue '%ws', cVersion=%u, pszV4PrinterDriverDirectory='%ws'",
          v15[3],
          *(unsigned int *)(v15[11] + 236LL),
          v15[61]);
      }
      else
      {
        v34 = *(LSTATUS **)(a1 + 8);
        *v34 = RegCreateKeyExW(hKey, v18, 0, 0, 0, 3u, 0, &phkResult, 0);
      }
    }
    else
    {
      **(_DWORD **)(a1 + 8) = 6;
    }
    LeaveSplSem(v16);
  }
  memset_0(v56, 0, 0x68u);
  v35 = *(RPC_STATUS **)(a1 + 8);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  if ( !*v35 )
    *v35 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  v36 = *(_DWORD **)(a1 + 8);
  v37 = -1;
  v50 = -1;
  if ( !*v36 )
  {
    v38 = dwProcessId;
    v39 = OpenProcess(0x40u, 0, dwProcessId);
    NCoreLibrary::TAutoHandleNT::operator=(&v50, v39);
    v37 = v50;
    if ( v50 == -1 )
    {
      if ( !v8
        || GetLastError() != 5
        || (ImpersonatePrinterClient(v8),
            v40 = OpenProcess(0x40u, 0, v38),
            NCoreLibrary::TAutoHandleNT::operator=(&v50, v40),
            v41 = RevertToPrinterSelf(),
            v37 = v50,
            v8 = v41,
            v50 == -1) )
      {
        v42 = *(DWORD **)(a1 + 8);
        *v42 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SplGetUserPropertyBag::<lambda_2ac9aa54c7f3cc855bb3c08927cd909e>::operator ()",
          L"Failed to open client process %u for handle duplication: %d",
          v38,
          **(unsigned int **)(a1 + 8));
      }
    }
  }
  if ( !**(_DWORD **)(a1 + 8) )
  {
    v43 = phkResult;
    if ( v37 == -1 )
      v37 = 0;
    v44 = **(HANDLE ***)a1;
    CurrentProcess = GetCurrentProcess();
    if ( !DuplicateHandle(CurrentProcess, v43, (HANDLE)v37, v44, 0, 0, 2u) )
    {
      v46 = *(DWORD **)(a1 + 8);
      *v46 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "SplGetUserPropertyBag::<lambda_2ac9aa54c7f3cc855bb3c08927cd909e>::operator ()",
        L"Failed to duplicate user property bag handle into process: %d",
        **(unsigned int **)(a1 + 8));
    }
  }
  if ( v8 )
    ImpersonatePrinterClient(v8);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleNT,void *,-1,void * const *>::Reset(&v50);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  v47 = (NCoreLibrary::TString *)hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  NCoreLibrary::TString::vFree(v47, (void *)lpSubKey);
  NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v58, v48);
}

```

## disassembly

```asm
0x18004f67c  push    rbp
0x18004f67e  push    rbx
0x18004f67f  push    rsi
0x18004f680  push    rdi
0x18004f681  push    r12
0x18004f683  push    r13
0x18004f685  push    r14
0x18004f687  push    r15
0x18004f689  lea     rbp, [rsp-258h]
0x18004f691  sub     rsp, 358h
0x18004f698  mov     rax, cs:__security_cookie
0x18004f69f  xor     rax, rsp
0x18004f6a2  mov     [rbp+290h+var_50], rax
0x18004f6a9  mov     rax, [rcx]
0x18004f6ac  xor     r12d, r12d
0x18004f6af  mov     rsi, rcx
0x18004f6b2  lea     rcx, [rbp+290h+var_2A0]; this
0x18004f6b6  mov     rdx, [rax]
0x18004f6b9  lea     r14d, [r12+1]
0x18004f6be  mov     r8d, r14d; int
0x18004f6c1  mov     [rdx], r12
0x18004f6c4  xor     edx, edx; int
0x18004f6c6  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x18004f6cb  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18004f6d2  lea     rdx, [rsp+390h+lpSubKey]; struct TString *
0x18004f6d7  mov     [rsp+390h+lpSubKey], rax
0x18004f6dc  lea     rcx, [rbp+290h+var_2A0]; this
0x18004f6e0  call    ?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z; NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)
0x18004f6e5  mov     ecx, eax; this
0x18004f6e7  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18004f6ec  mov     rcx, [rsi+8]
0x18004f6f0  mov     [rcx], eax
0x18004f6f2  mov     rax, [rsi+8]
0x18004f6f6  cmp     [rax], r12d
0x18004f6f9  jnz     short loc_18004F719
0x18004f6fb  lea     rdx, aClassesLocalSe_0; "_Classes\\Local Settings\\Printers\\Pro"...
0x18004f702  lea     rcx, [rsp+390h+lpSubKey]; this
0x18004f707  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x18004f70c  mov     ecx, eax; this
0x18004f70e  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18004f713  mov     rcx, [rsi+8]
0x18004f717  mov     [rcx], eax
0x18004f719  call    cs:__imp_RevertToPrinterSelf
0x18004f71f  mov     rcx, [rsi+8]
0x18004f723  mov     r13, rax
0x18004f726  mov     [rsp+390h+hKey], r12
0x18004f72b  cmp     [rcx], r12d
0x18004f72e  jnz     short loc_18004F76E
0x18004f730  mov     rdx, [rsp+390h+lpSubKey]; lpSubKey
0x18004f735  lea     rax, [rsp+390h+hKey]
0x18004f73a  mov     [rsp+390h+lpdwDisposition], r12; lpdwDisposition
0x18004f73f  mov     rbx, rcx
0x18004f742  mov     [rsp+390h+phkResult], rax; phkResult
0x18004f747  xor     r9d, r9d; lpClass
0x18004f74a  mov     [rsp+390h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004f74f  xor     r8d, r8d; Reserved
0x18004f752  mov     [rsp+390h+samDesired], 0Ch; samDesired
0x18004f75a  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18004f761  mov     [rsp+390h+dwOptions], r12d; dwOptions
0x18004f766  call    cs:__imp_RegCreateKeyExW
0x18004f76c  mov     [rbx], eax
0x18004f76e  mov     rax, [rsi+8]
0x18004f772  mov     edi, r12d
0x18004f775  cmp     [rax], r12d
0x18004f778  jnz     short loc_18004F7E8
0x18004f77a  mov     rcx, [rsi+10h]
0x18004f77e  lea     r9, [rbp+290h+var_260]
0x18004f782  mov     rbx, rax
0x18004f785  mov     [rsp+390h+var_340], r12d
0x18004f78a  lea     rax, [rsp+390h+var_338]
0x18004f78f  mov     dword ptr [rsp+390h+var_338], r12d
0x18004f794  mov     qword ptr [rsp+390h+samDesired], rax
0x18004f799  lea     r8, [rsp+390h+var_340]
0x18004f79e  mov     rcx, [rcx]
0x18004f7a1  lea     rdx, aV4Userproperty; "V4_UserPropertyBagScope"
0x18004f7a8  mov     [rsp+390h+dwOptions], 208h
0x18004f7b0  call    SplGetPrinterData
0x18004f7b5  mov     [rbx], eax
0x18004f7b7  mov     rax, [rsi+8]
0x18004f7bb  cmp     dword ptr [rax], 2
0x18004f7be  jnz     short loc_18004F7C5
0x18004f7c0  mov     [rax], r12d
0x18004f7c3  jmp     short loc_18004F7E8
0x18004f7c5  cmp     [rax], r12d
0x18004f7c8  jnz     short loc_18004F7E8
0x18004f7ca  cmp     [rsp+390h+var_340], r14d
0x18004f7cf  jnz     short loc_18004F7E8
0x18004f7d1  lea     rdx, [rbp+290h+var_260]
0x18004f7d5  lea     rcx, aManufacturer; "Manufacturer"
0x18004f7dc  call    cs:__imp__o__wcsicmp
0x18004f7e2  test    eax, eax
0x18004f7e4  cmovz   edi, r14d
0x18004f7e8  mov     rax, [rsi+8]
0x18004f7ec  mov     [rsp+390h+var_330], r12
0x18004f7f1  cmp     [rax], r12d
0x18004f7f4  jnz     loc_18004FA4E
0x18004f7fa  mov     rax, [rsi+10h]
0x18004f7fe  xor     ecx, ecx
0x18004f800  mov     rbx, [rax]
0x18004f803  call    EnterSplSem
0x18004f808  mov     r15, [rbx+40h]
0x18004f80c  mov     edx, 10h
0x18004f811  mov     rcx, rbx
0x18004f814  call    ValidateSpoolHandle
0x18004f819  test    eax, eax
0x18004f81b  jz      loc_18004FA3F
0x18004f821  test    r15, r15
0x18004f824  jz      loc_18004FA3F
0x18004f82a  mov     rcx, [r15+58h]
0x18004f82e  test    rcx, rcx
0x18004f831  jz      loc_18004FA3F
0x18004f837  mov     rdx, [rbx+0A8h]
0x18004f83e  test    rdx, rdx
0x18004f841  jz      loc_18004FA3F
0x18004f847  mov     rax, [rbx+40h]
0x18004f84b  test    byte ptr [rax+88h], 30h
0x18004f852  jnz     loc_18004FA3F
0x18004f858  cmp     dword ptr [rcx+0ECh], 4
0x18004f85f  mov     r14, r12
0x18004f862  jnb     short loc_18004F873
0x18004f864  mov     rax, [rsi+8]
0x18004f868  mov     dword ptr [rax], 32h ; '2'
0x18004f86e  jmp     loc_18004F9BF
0x18004f873  test    edi, edi
0x18004f875  jz      loc_18004F98D
0x18004f87b  mov     r12d, 104h
0x18004f881  lea     r8, aManufacturers; "Manufacturers\\"
0x18004f888  mov     edx, r12d; unsigned __int64
0x18004f88b  lea     rcx, [rbp+290h+var_260]; unsigned __int16 *
0x18004f88f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f894  mov     ecx, eax; this
0x18004f896  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18004f89b  mov     rcx, [rsi+8]
0x18004f89f  xor     r11d, r11d
0x18004f8a2  mov     [rcx], eax
0x18004f8a4  mov     ecx, r11d
0x18004f8a7  mov     r10, [rsi+8]
0x18004f8ab  mov     [rsp+390h+var_318], rcx
0x18004f8b0  cmp     [r10], r11d
0x18004f8b3  jnz     short loc_18004F8D5
0x18004f8b5  lea     r8, [rsp+390h+var_318]; unsigned __int64 *
0x18004f8ba  mov     edx, r12d; unsigned __int64
0x18004f8bd  lea     rcx, [rbp+290h+var_260]; unsigned __int16 *
0x18004f8c1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004f8c6  mov     ecx, eax; this
0x18004f8c8  call    ?StatusFromHResult@NCoreLibrary@@YAKJ@Z; NCoreLibrary::StatusFromHResult(long)
0x18004f8cd  mov     rcx, [rsp+390h+var_318]
0x18004f8d2  mov     [r10], eax
0x18004f8d5  mov     rax, [rsi+8]
0x18004f8d9  cmp     [rax], r11d
0x18004f8dc  jnz     loc_18004F9BC
0x18004f8e2  lea     rdi, [rbp+290h+var_260]
0x18004f8e6  mov     [rsp+390h+var_340], r11d
0x18004f8eb  lea     rdi, [rdi+rcx*2]
0x18004f8ef  mov     dword ptr [rsp+390h+var_338], r11d
0x18004f8f4  call    LeaveSplSem
0x18004f8f9  mov     rcx, [rsi+10h]
0x18004f8fd  lea     rax, [rsp+390h+var_338]
0x18004f902  sub     r12d, dword ptr [rsp+390h+var_318]
0x18004f907  lea     r8, [rsp+390h+var_340]
0x18004f90c  mov     rbx, [rsi+8]
0x18004f910  lea     rdx, aV4Manufacturer; "V4_Manufacturer"
0x18004f917  mov     qword ptr [rsp+390h+samDesired], rax
0x18004f91c  add     r12d, r12d
0x18004f91f  mov     rcx, [rcx]
0x18004f922  mov     r9, rdi
0x18004f925  mov     [rsp+390h+dwOptions], r12d
0x18004f92a  call    SplGetPrinterData
0x18004f92f  xor     ecx, ecx
0x18004f931  mov     [rbx], eax
0x18004f933  call    EnterSplSem
0x18004f938  mov     rax, [rsi+8]
0x18004f93c  xor     r12d, r12d
0x18004f93f  cmp     [rax], r12d
0x18004f942  jnz     short loc_18004F9BF
0x18004f944  lea     rcx, [rbp+290h+var_58]
0x18004f94b  lea     r14, [rbp+290h+var_260]
0x18004f94f  cmp     rdi, rcx
0x18004f952  jnb     short loc_18004F979
0x18004f954  lea     edx, [r12+5Ch]
0x18004f959  cmp     [rdi], r12w
0x18004f95d  jz      short loc_18004F9BF
0x18004f95f  cmp     dx, [rdi]
0x18004f962  jnz     short loc_18004F969
0x18004f964  mov     word ptr [rdi], 2Ch ; ','
0x18004f969  add     rdi, 2
0x18004f96d  lea     rcx, [rbp+290h+var_58]
0x18004f974  cmp     rdi, rcx
0x18004f977  jb      short loc_18004F959
0x18004f979  lea     rcx, [rbp+290h+var_58]
0x18004f980  cmp     rdi, rcx
0x18004f983  jnz     short loc_18004F9BF
0x18004f985  mov     dword ptr [rax], 0Dh
0x18004f98b  jmp     short loc_18004F9BF
0x18004f98d  test    dword ptr [rdx+0A8h], 4000000h
0x18004f997  jz      short loc_18004F99F
0x18004f999  mov     r14, [r15+18h]
0x18004f99d  jmp     short loc_18004F9BF
0x18004f99f  mov     rcx, [r15+1E8h]; Str
0x18004f9a6  test    rcx, rcx
0x18004f9a9  jz      short loc_18004F9BF
0x18004f9ab  mov     edx, 5Ch ; '\'; Ch
0x18004f9b0  call    cs:__imp_wcsrchr
0x18004f9b6  lea     r14, [rax+2]
0x18004f9ba  jmp     short loc_18004F9BF
0x18004f9bc  xor     r12d, r12d
0x18004f9bf  mov     rax, [rsi+8]
0x18004f9c3  cmp     [rax], r12d
0x18004f9c6  jnz     short loc_18004FA09
0x18004f9c8  test    r14, r14
0x18004f9cb  jz      short loc_18004FA09
0x18004f9cd  mov     rcx, [rsp+390h+hKey]; hKey
0x18004f9d2  mov     rbx, rax
0x18004f9d5  mov     [rsp+390h+lpdwDisposition], r12; lpdwDisposition
0x18004f9da  lea     rax, [rsp+390h+var_330]
0x18004f9df  mov     [rsp+390h+phkResult], rax; phkResult
0x18004f9e4  xor     r9d, r9d; lpClass
0x18004f9e7  mov     [rsp+390h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004f9ec  xor     r8d, r8d; Reserved
0x18004f9ef  mov     [rsp+390h+samDesired], 3; samDesired
0x18004f9f7  mov     rdx, r14; lpSubKey
0x18004f9fa  mov     [rsp+390h+dwOptions], r12d; dwOptions
0x18004f9ff  call    cs:__imp_RegCreateKeyExW
0x18004fa05  mov     [rbx], eax
0x18004fa07  jmp     short loc_18004FA49
0x18004fa09  mov     dword ptr [rax], 32h ; '2'
0x18004fa0f  lea     rdx, aUnableToCreate; "Unable to create key for queue '%ws', c"...
0x18004fa16  mov     r9, [r15+58h]
0x18004fa1a  lea     rcx, aSplgetuserprop_0; "SplGetUserPropertyBag::<lambda_2ac9aa54"...
0x18004fa21  mov     rax, [r15+1E8h]
0x18004fa28  mov     r8, [r15+18h]
0x18004fa2c  mov     qword ptr [rsp+390h+dwOptions], rax
0x18004fa31  mov     r9d, [r9+0ECh]
0x18004fa38  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18004fa3d  jmp     short loc_18004FA49
0x18004fa3f  mov     rax, [rsi+8]
0x18004fa43  mov     dword ptr [rax], 6
0x18004fa49  call    LeaveSplSem
0x18004fa4e  xor     edx, edx; Val
0x18004fa50  lea     rcx, [rbp+290h+var_308]; void *
0x18004fa54  lea     r8d, [rdx+68h]; Size
0x18004fa58  call    memset_0
0x18004fa5d  mov     rax, [rsi+8]
0x18004fa61  mov     [rbp+290h+RpcCallAttributes], 2
0x18004fa68  mov     [rbp+290h+var_30C], 10h
0x18004fa6f  cmp     [rax], r12d
0x18004fa72  jnz     short loc_18004FA85
0x18004fa74  lea     rdx, [rbp+290h+RpcCallAttributes]; RpcCallAttributes
0x18004fa78  xor     ecx, ecx; ClientBinding
0x18004fa7a  mov     rbx, rax
0x18004fa7d  call    cs:__imp_RpcServerInqCallAttributesW
0x18004fa83  mov     [rbx], eax
0x18004fa85  mov     rax, [rsi+8]
0x18004fa89  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004fa8d  mov     r14, r15
0x18004fa90  mov     [rsp+390h+var_338], r15
0x18004fa95  cmp     [rax], r12d
0x18004fa98  jnz     loc_18004FB37
0x18004fa9e  mov     edi, [rbp+290h+dwProcessId]
0x18004faa1  xor     edx, edx; bInheritHandle
0x18004faa3  mov     r8d, edi; dwProcessId
0x18004faa6  lea     ebx, [rdx+40h]
0x18004faa9  mov     ecx, ebx; dwDesiredAccess
0x18004faab  call    cs:__imp_OpenProcess
0x18004fab1  mov     rdx, rax
0x18004fab4  lea     rcx, [rsp+390h+var_338]
0x18004fab9  call    ??4TAutoHandleNT@NCoreLibrary@@QEAAPEAXPEAX@Z; NCoreLibrary::TAutoHandleNT::operator=(void *)
0x18004fabe  mov     r14, [rsp+390h+var_338]
0x18004fac3  cmp     r14, r15
0x18004fac6  jnz     short loc_18004FB37
0x18004fac8  test    r13, r13
0x18004facb  jz      short loc_18004FB0E
0x18004facd  call    cs:__imp_GetLastError
0x18004fad3  cmp     eax, 5
0x18004fad6  jnz     short loc_18004FB0E
0x18004fad8  mov     rcx, r13; hToken
0x18004fadb  call    cs:__imp_ImpersonatePrinterClient
0x18004fae1  mov     r8d, edi; dwProcessId
0x18004fae4  xor     edx, edx; bInheritHandle
0x18004fae6  mov     ecx, ebx; dwDesiredAccess
0x18004fae8  call    cs:__imp_OpenProcess
0x18004faee  mov     rdx, rax
0x18004faf1  lea     rcx, [rsp+390h+var_338]
0x18004faf6  call    ??4TAutoHandleNT@NCoreLibrary@@QEAAPEAXPEAX@Z; NCoreLibrary::TAutoHandleNT::operator=(void *)
0x18004fafb  call    cs:__imp_RevertToPrinterSelf
0x18004fb01  mov     r14, [rsp+390h+var_338]
0x18004fb06  mov     r13, rax
0x18004fb09  cmp     r14, r15
0x18004fb0c  jnz     short loc_18004FB37
0x18004fb0e  mov     rbx, [rsi+8]
0x18004fb12  call    cs:__imp_GetLastError
0x18004fb18  mov     [rbx], eax
0x18004fb1a  mov     r8d, edi
0x18004fb1d  mov     r9, [rsi+8]
0x18004fb21  lea     rdx, aFailedToOpenCl; "Failed to open client process %u for ha"...
0x18004fb28  lea     rcx, aSplgetuserprop_0; "SplGetUserPropertyBag::<lambda_2ac9aa54"...
0x18004fb2f  mov     r9d, [r9]
0x18004fb32  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18004fb37  mov     rax, [rsi+8]
0x18004fb3b  cmp     [rax], r12d
  ... truncated ...
```
