# CCorSvcMgr::InferPackageInformation(ushort const *)

- ea: `0x180021810`
- end: `0x1800221fa`
- name: `?InferPackageInformation@CCorSvcMgr@@AEAAJPEBG@Z`
- size: `2538`
- prototype: `__int64 __fastcall(CCorSvcMgr *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002142c`

## callees

- `0x180001ce8`
- `0x180005ed0`
- `0x18000a9cc`
- `0x180021810`
- `0x18002220c`
- `0x18002a02c`
- `0x18002a054`
- `0x18002c4fc`
- `0x18002d624`
- `0x180030530`
- `0x180030568`
- `0x1800354e0`
- `0x180035a64`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180021955`
- `ADVAPI32!OpenProcessToken` at `0x180021955`
- `ADVAPI32!GetTokenInformation` at `0x1800219be`
- `ADVAPI32!GetTokenInformation` at `0x180021a23`
- `ADVAPI32!GetTokenInformation` at `0x1800219be`
- `ADVAPI32!GetTokenInformation` at `0x180021a23`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180021a86`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180021ebb`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180021a86`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180021ebb`
- `KERNEL32!GetCurrentProcess` at `0x180021943`
- `KERNEL32!GetCurrentProcess` at `0x180021943`
- `KERNEL32!LoadLibraryExW` at `0x180021896`
- `KERNEL32!LoadLibraryExW` at `0x180021896`
- `KERNEL32!RaiseException` at `0x180021b9e`
- `KERNEL32!RaiseException` at `0x180021b9e`
- `KERNEL32!GetLastError` at `0x1800218ec`
- `KERNEL32!GetLastError` at `0x18002197c`
- `KERNEL32!GetLastError` at `0x180021a2d`
- `KERNEL32!GetLastError` at `0x180021aaa`
- `KERNEL32!GetLastError` at `0x1800218ec`
- `KERNEL32!GetLastError` at `0x18002197c`
- `KERNEL32!GetLastError` at `0x180021a2d`
- `KERNEL32!GetLastError` at `0x180021aaa`
- `KERNEL32!GetProcAddress` at `0x1800218c5`
- `KERNEL32!GetProcAddress` at `0x1800218de`
- `KERNEL32!GetProcAddress` at `0x1800218c5`
- `KERNEL32!GetProcAddress` at `0x1800218de`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180021f72`
- `ucrtbase_clr0400!_wcsnicmp` at `0x180021f72`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220e5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220e5`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002205d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002205d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021bef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180021bef`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180021916`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180021916`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180021b42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021b86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021b5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022186`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800221ab`

## string_xrefs

- `0x1800218d3`: `GetAppContainerFolderPath`
- `0x1800218be`: `DeriveAppContainerSidFromAppContainerName`
- `0x18002188f`: `userenv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=403
__int64 __fastcall CCorSvcMgr::InferPackageInformation(CCorSvcMgr *this, wchar_t *a2)
{
  int v2; // eax
  int v3; // eax
  signed int v4; // eax
  signed int ActivationFactory; // edi
  HANDLE CurrentProcess; // rax
  bool v7; // cl
  int v8; // eax
  signed int LastError; // eax
  const struct NoThrow *v10; // rdx
  void **v11; // r15
  DWORD v12; // ebx
  signed int v13; // eax
  void *v14; // rcx
  bool v15; // cl
  int v16; // eax
  signed int v17; // eax
  HSTRING v18; // rbx
  const WCHAR *v19; // rcx
  __int64 v20; // rdx
  const WCHAR *v21; // rax
  __int64 v22; // r9
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  _BYTE v29[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-C8h] BYREF
  PSID Sid; // [rsp+40h] [rbp-C0h]
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  int v36; // [rsp+B8h] [rbp-48h]
  HANDLE TokenHandle; // [rsp+C0h] [rbp-40h] BYREF
  int v38; // [rsp+C8h] [rbp-38h]
  __int64 v39; // [rsp+D0h] [rbp-30h] BYREF
  int v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E0h] [rbp-20h] BYREF
  int v42; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+F0h] [rbp-10h] BYREF
  int v44; // [rsp+F8h] [rbp-8h]
  LPWSTR StringSid; // [rsp+100h] [rbp+0h] BYREF
  int v46; // [rsp+108h] [rbp+8h]
  BOOL v47; // [rsp+110h] [rbp+10h]
  wchar_t *String1; // [rsp+118h] [rbp+18h]
  CCorSvcMgr *v49; // [rsp+120h] [rbp+20h]
  HMODULE hModule; // [rsp+138h] [rbp+38h] BYREF
  BOOL v51; // [rsp+140h] [rbp+40h]
  HSTRING v52; // [rsp+148h] [rbp+48h]
  void **v53; // [rsp+150h] [rbp+50h]
  BOOL v54; // [rsp+158h] [rbp+58h]
  HSTRING v55; // [rsp+180h] [rbp+80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+188h] [rbp+88h] BYREF

  String1 = a2;
  v49 = this;
  v2 = gRunningOnStatus;
  if ( !gRunningOnStatus )
  {
    InitRunningOnVersionStatus();
    v2 = gRunningOnStatus;
  }
  if ( v2 < 6 )
    return 1;
  v3 = gWinRTStatus;
  if ( !gWinRTStatus )
  {
    InitWinRTStatus();
    v3 = gWinRTStatus;
  }
  if ( v3 != 2 )
    return 1;
  hModule = LoadLibraryExW(L"userenv.dll", 0, 0);
  v51 = hModule != 0;
  if ( hModule
    && GetProcAddress(hModule, "DeriveAppContainerSidFromAppContainerName")
    && GetProcAddress(hModule, "GetAppContainerFolderPath") )
  {
    ActivationFactory = RoInitialize(1);
    if ( ActivationFactory >= 0 )
    {
      v38 = 0;
      Sid = &TokenHandle;
      TokenHandle = (HANDLE)-1LL;
      CurrentProcess = GetCurrentProcess();
      v7 = !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle);
      v8 = v38;
      if ( TokenHandle != (HANDLE)-1LL )
        v8 = 1;
      v38 = v8;
      if ( v7 )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          ActivationFactory = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            ActivationFactory = LastError;
        }
        else
        {
          ActivationFactory = -2147467259;
        }
      }
      else
      {
        TokenInformationLength = 0;
        GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
        if ( TokenInformationLength )
        {
          v11 = (void **)operator new(TokenInformationLength, v10);
          v53 = v11;
          v47 = v11 != 0;
          v54 = v47;
          v12 = TokenInformationLength;
          if ( v11 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v11, TokenInformationLength, &TokenInformationLength) )
            {
              if ( TokenInformationLength == v12 )
              {
                v14 = *v11;
                v46 = 0;
                Sid = &StringSid;
                StringSid = 0;
                v15 = !ConvertSidToStringSidW(v14, &StringSid);
                v16 = v46;
                if ( StringSid )
                  v16 = 1;
                v46 = v16;
                if ( v15 )
                {
                  v17 = GetLastError();
                  if ( v17 )
                  {
                    ActivationFactory = (unsigned __int16)v17 | 0x80070000;
                    if ( v17 <= 0 )
                      ActivationFactory = v17;
                  }
                  else
                  {
                    ActivationFactory = -2147467259;
                  }
                }
                else
                {
                  v18 = 0;
                  v52 = 0;
                  v19 = &psz;
                  if ( StringSid )
                    v19 = StringSid;
                  v20 = 0x7FFFFFFF;
                  v21 = v19;
                  do
                  {
                    if ( !*v21 )
                      break;
                    ++v21;
                    --v20;
                  }
                  while ( v20 );
                  ActivationFactory = v20 == 0 ? 0x80070057 : 0;
                  v22 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
                  if ( !v20 )
                    LODWORD(v22) = 0;
                  string = 0;
                  if ( v20 )
                  {
                    ActivationFactory = WindowsCreateString(v19, v22, &string);
                    if ( ActivationFactory >= 0 )
                    {
                      v18 = string;
                      v52 = string;
                      WindowsDeleteString(0);
                      v33 = 0;
                      v34 = 0;
                      if ( WindowsCreateStringReference(
                             L"Windows.Management.Deployment.PackageManager",
                             0x2Cu,
                             &hstringHeader,
                             &v55) < 0 )
                        RaiseException(0xC000000D, 1u, 0, 0);
                      Sid = &v33;
                      if ( v34 )
                      {
                        if ( v33 )
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                        v34 = 0;
                      }
                      v33 = 0;
                      ActivationFactory = RoGetActivationFactory(v55, &GUID_00000035_0000_0000_c000_000000000046, &v33);
                      v23 = v34;
                      if ( v33 )
                        v23 = 1;
                      v34 = v23;
                      if ( ActivationFactory >= 0 )
                      {
                        v44 = 0;
                        Sid = &v43;
                        v43 = 0;
                        ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v33 + 48LL))(
                                              v33,
                                              &v43);
                        v24 = v44;
                        if ( v43 )
                          v24 = 1;
                        v44 = v24;
                        if ( ActivationFactory >= 0 )
                        {
                          v42 = 0;
                          Sid = &v41;
                          v41 = 0;
                          ActivationFactory = (**v43)(v43, &GUID_9a7d4b65_5e8f_4fc7_a2e5_7f6925cb8b53, &v41);
                          v25 = v42;
                          if ( v41 )
                            v25 = 1;
                          v42 = v25;
                          if ( ActivationFactory >= 0 )
                          {
                            v40 = 0;
                            Sid = &v39;
                            v39 = 0;
                            ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v41 + 96LL))(
                                                  v41,
                                                  v18,
                                                  &v39);
                            v26 = v40;
                            if ( v39 )
                              v26 = 1;
                            v40 = v26;
                            if ( ActivationFactory >= 0 )
                            {
                              v36 = 0;
                              Sid = &v35;
                              v35 = 0;
                              ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL))(
                                                    v39,
                                                    &v35);
                              v27 = v36;
                              if ( v35 )
                                v27 = 1;
                              v36 = v27;
                              if ( ActivationFactory >= 0 )
                              {
                                v29[0] = 0;
                                (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v35 + 56LL))(v35, v29);
                                Logger::Printf(
                                  (CCorSvcMgr *)((char *)v49 + 208),
                                  L"No matching package found for NI '%s'.\n",
                                  String1);
                                ActivationFactory = 1;
                              }
                              Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>::~Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>(&v35);
                            }
                            Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>::~Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>(&v39);
                          }
                          Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>::~Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>(&v41);
                        }
                        Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>::~Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>((__int64 *)&v43);
                      }
                      Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>::~Wrapper<NodeFactory *,&void DoNothing<NodeFactory *>(NodeFactory *),&void DoTheRelease<NodeFactory>(NodeFactory *),0,&int CompareDefault<NodeFactory *>(NodeFactory *,NodeFactory *),2,1>(&v33);
                    }
                  }
                  if ( v18 )
                    WindowsDeleteString(v18);
                }
                Wrapper<unsigned short * *,&void DoNothing<unsigned short * *>(unsigned short * *),&void DoLocalFree<unsigned short *>(unsigned short * *),0,&int CompareDefault<unsigned short * *>(unsigned short * *,unsigned short * *),2,1>::~Wrapper<unsigned short * *,&void DoNothing<unsigned short * *>(unsigned short * *),&void DoLocalFree<unsigned short *>(unsigned short * *),0,&int CompareDefault<unsigned short * *>(unsigned short * *,unsigned short * *),2,1>((__int64)&StringSid);
              }
              else
              {
                ActivationFactory = -2147418113;
              }
            }
            else
            {
              v13 = GetLastError();
              if ( v13 )
              {
                ActivationFactory = (unsigned __int16)v13 | 0x80070000;
                if ( v13 <= 0 )
                  ActivationFactory = v13;
              }
              else
              {
                ActivationFactory = -2147467259;
              }
            }
          }
          else
          {
            ActivationFactory = -2147024882;
          }
          if ( v47 )
          {
            operator delete(v11);
            v54 = 0;
          }
        }
        else
        {
          ActivationFactory = -2147418113;
        }
      }
      Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2,1>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2,1>((__int64)&TokenHandle);
      RoUninitialize();
    }
  }
  else
  {
    v4 = GetLastError();
    if ( v4 )
    {
      ActivationFactory = (unsigned __int16)v4 | 0x80070000;
      if ( v4 <= 0 )
        ActivationFactory = v4;
    }
    else
    {
      ActivationFactory = -2147467259;
    }
  }
  Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2,1>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2,1>((__int64)&hModule);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180021810  mov     [rsp-8+arg_10], rbx
0x180021815  push    rbp
0x180021816  push    rsi
0x180021817  push    rdi
0x180021818  push    r12
0x18002181a  push    r13
0x18002181c  push    r14
0x18002181e  push    r15
0x180021820  lea     rbp, [rsp-0B0h]
0x180021828  sub     rsp, 1B0h
0x18002182f  mov     rax, cs:__security_cookie
0x180021836  xor     rax, rsp
0x180021839  mov     [rbp+0E0h+var_38], rax
0x180021840  mov     [rbp+0E0h+String1], rdx
0x180021844  mov     [rbp+0E0h+var_C0], rcx
0x180021848  xor     ebx, ebx
0x18002184a  mov     [rsp+1E0h+var_1B0], ebx
0x18002184e  mov     eax, cs:?gRunningOnStatus@@3W4RunningOnStatusEnum@@A; RunningOnStatusEnum gRunningOnStatus
0x180021854  test    eax, eax
0x180021856  jnz     short loc_180021863
0x180021858  call    ?InitRunningOnVersionStatus@@YAXXZ; InitRunningOnVersionStatus(void)
0x18002185d  mov     eax, cs:?gRunningOnStatus@@3W4RunningOnStatusEnum@@A; RunningOnStatusEnum gRunningOnStatus
0x180021863  cmp     eax, 6
0x180021866  jl      loc_1800221CB
0x18002186c  mov     eax, cs:?gWinRTStatus@@3W4WinRTStatusEnum@@A; WinRTStatusEnum gWinRTStatus
0x180021872  test    eax, eax
0x180021874  jnz     short loc_180021881
0x180021876  call    ?InitWinRTStatus@@YAXXZ; InitWinRTStatus(void)
0x18002187b  mov     eax, cs:?gWinRTStatus@@3W4WinRTStatusEnum@@A; WinRTStatusEnum gWinRTStatus
0x180021881  cmp     eax, 2
0x180021884  jnz     loc_1800221CB
0x18002188a  xor     r8d, r8d; dwFlags
0x18002188d  xor     edx, edx; hFile
0x18002188f  lea     rcx, aUserenvDll; "userenv.dll"
0x180021896  call    cs:__imp_LoadLibraryExW
0x18002189c  mov     [rbp+0E0h+hModule], rax
0x1800218a0  mov     [rbp+0E0h+var_A0], ebx
0x1800218a3  mov     ecx, ebx
0x1800218a5  mov     r14d, 1
0x1800218ab  test    rax, rax
0x1800218ae  cmovnz  ecx, r14d
0x1800218b2  mov     [rbp+0E0h+var_A0], ecx
0x1800218b5  mov     rcx, [rbp+0E0h+hModule]; hModule
0x1800218b9  test    rcx, rcx
0x1800218bc  jz      short loc_1800218EC
0x1800218be  lea     rdx, aDeriveappconta; "DeriveAppContainerSidFromAppContainerNa"...
0x1800218c5  call    cs:__imp_GetProcAddress
0x1800218cb  mov     r12, rax
0x1800218ce  test    rax, rax
0x1800218d1  jz      short loc_1800218EC
0x1800218d3  lea     rdx, aGetappcontaine; "GetAppContainerFolderPath"
0x1800218da  mov     rcx, [rbp+0E0h+hModule]; hModule
0x1800218de  call    cs:__imp_GetProcAddress
0x1800218e4  mov     r13, rax
0x1800218e7  test    rax, rax
0x1800218ea  jnz     short loc_180021913
0x1800218ec  call    cs:__imp_GetLastError
0x1800218f2  test    eax, eax
0x1800218f4  jnz     short loc_180021900
0x1800218f6  mov     edi, 80004005h
0x1800218fb  jmp     loc_180022064
0x180021900  movzx   edi, ax
0x180021903  or      edi, 80070000h
0x180021909  test    eax, eax
0x18002190b  cmovle  edi, eax
0x18002190e  jmp     loc_180022064
0x180021913  mov     ecx, r14d
0x180021916  call    cs:__imp_RoInitialize
0x18002191c  mov     edi, eax
0x18002191e  test    eax, eax
0x180021920  js      loc_180022064
0x180021926  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002192a  mov     [rbp+0E0h+TokenHandle], rdi
0x18002192e  mov     [rbp+0E0h+var_118], ebx
0x180021931  lea     rax, [rbp+0E0h+TokenHandle]
0x180021935  mov     [rsp+1E0h+Sid], rax
0x18002193a  mov     [rbp+0E0h+TokenHandle], rdi
0x18002193e  mov     [rsp+1E0h+var_1B0], r14d
0x180021943  call    cs:__imp_GetCurrentProcess
0x180021949  mov     rcx, rax; ProcessHandle
0x18002194c  lea     r8, [rbp+0E0h+TokenHandle]; TokenHandle
0x180021950  mov     edx, 20008h; DesiredAccess
0x180021955  call    cs:__imp_OpenProcessToken
0x18002195b  test    eax, eax
0x18002195d  setz    cl
0x180021960  mov     esi, r14d
0x180021963  and     esi, 0FFFFFFFEh
0x180021966  mov     [rsp+1E0h+var_1B0], esi
0x18002196a  mov     eax, [rbp+0E0h+var_118]
0x18002196d  cmp     [rbp+0E0h+TokenHandle], rdi
0x180021971  cmovnz  eax, r14d
0x180021975  mov     [rbp+0E0h+var_118], eax
0x180021978  test    cl, cl
0x18002197a  jz      short loc_1800219A3
0x18002197c  call    cs:__imp_GetLastError
0x180021982  test    eax, eax
0x180021984  jnz     short loc_180021990
0x180021986  mov     edi, 80004005h
0x18002198b  jmp     loc_180022053
0x180021990  movzx   edi, ax
0x180021993  or      edi, 80070000h
0x180021999  test    eax, eax
0x18002199b  cmovle  edi, eax
0x18002199e  jmp     loc_180022053
0x1800219a3  mov     [rsp+1E0h+TokenInformationLength], ebx
0x1800219a7  lea     rax, [rsp+1E0h+TokenInformationLength]
0x1800219ac  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x1800219b1  xor     r9d, r9d; TokenInformationLength
0x1800219b4  xor     r8d, r8d; TokenInformation
0x1800219b7  mov     edx, r14d; TokenInformationClass
0x1800219ba  mov     rcx, [rbp+0E0h+TokenHandle]; TokenHandle
0x1800219be  call    cs:__imp_GetTokenInformation
0x1800219c4  mov     eax, [rsp+1E0h+TokenInformationLength]
0x1800219c8  test    eax, eax
0x1800219ca  jnz     short loc_1800219D6
0x1800219cc  mov     edi, 8000FFFFh
0x1800219d1  jmp     loc_180022053
0x1800219d6  mov     rcx, rax; dwBytes
0x1800219d9  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800219de  mov     r15, rax
0x1800219e1  mov     [rbp+0E0h+var_90], rax
0x1800219e5  mov     [rbp+0E0h+var_88], ebx
0x1800219e8  mov     eax, ebx
0x1800219ea  test    r15, r15
0x1800219ed  cmovnz  eax, r14d
0x1800219f1  mov     [rbp+0E0h+var_D0], eax
0x1800219f4  mov     [rbp+0E0h+var_88], eax
0x1800219f7  mov     ebx, [rsp+1E0h+TokenInformationLength]
0x1800219fb  xor     edi, edi
0x1800219fd  test    r15, r15
0x180021a00  jnz     short loc_180021A0C
0x180021a02  mov     edi, 8007000Eh
0x180021a07  jmp     loc_180022041
0x180021a0c  lea     rax, [rsp+1E0h+TokenInformationLength]
0x180021a11  mov     [rsp+1E0h+ReturnLength], rax; ReturnLength
0x180021a16  mov     r9d, ebx; TokenInformationLength
0x180021a19  mov     r8, r15; TokenInformation
0x180021a1c  mov     edx, r14d; TokenInformationClass
0x180021a1f  mov     rcx, [rbp+0E0h+TokenHandle]; TokenHandle
0x180021a23  call    cs:__imp_GetTokenInformation
0x180021a29  test    eax, eax
0x180021a2b  jnz     short loc_180021A54
0x180021a2d  call    cs:__imp_GetLastError
0x180021a33  test    eax, eax
0x180021a35  jnz     short loc_180021A41
0x180021a37  mov     edi, 80004005h
0x180021a3c  jmp     loc_180022041
0x180021a41  movzx   edi, ax
0x180021a44  or      edi, 80070000h
0x180021a4a  test    eax, eax
0x180021a4c  cmovle  edi, eax
0x180021a4f  jmp     loc_180022041
0x180021a54  cmp     [rsp+1E0h+TokenInformationLength], ebx
0x180021a58  jz      short loc_180021A64
0x180021a5a  mov     edi, 8000FFFFh
0x180021a5f  jmp     loc_180022041
0x180021a64  mov     rcx, [r15]; Sid
0x180021a67  mov     [rbp+0E0h+StringSid], rdi
0x180021a6b  mov     [rbp+0E0h+var_D8], edi
0x180021a6e  lea     rax, [rbp+0E0h+StringSid]
0x180021a72  mov     [rsp+1E0h+Sid], rax
0x180021a77  mov     [rbp+0E0h+StringSid], rdi
0x180021a7b  or      esi, 2
0x180021a7e  mov     [rsp+1E0h+var_1B0], esi
0x180021a82  lea     rdx, [rbp+0E0h+StringSid]; StringSid
0x180021a86  call    cs:__imp_ConvertSidToStringSidW
0x180021a8c  test    eax, eax
0x180021a8e  setz    cl
0x180021a91  and     esi, 0FFFFFFFDh
0x180021a94  mov     [rsp+1E0h+var_1B0], esi
0x180021a98  mov     eax, [rbp+0E0h+var_D8]
0x180021a9b  cmp     [rbp+0E0h+StringSid], rdi
0x180021a9f  cmovnz  eax, r14d
0x180021aa3  mov     [rbp+0E0h+var_D8], eax
0x180021aa6  test    cl, cl
0x180021aa8  jz      short loc_180021AD1
0x180021aaa  call    cs:__imp_GetLastError
0x180021ab0  test    eax, eax
0x180021ab2  jnz     short loc_180021ABE
0x180021ab4  mov     edi, 80004005h
0x180021ab9  jmp     loc_180022037
0x180021abe  movzx   edi, ax
0x180021ac1  or      edi, 80070000h
0x180021ac7  test    eax, eax
0x180021ac9  cmovle  edi, eax
0x180021acc  jmp     loc_180022037
0x180021ad1  mov     rbx, rdi
0x180021ad4  mov     [rbp+0E0h+var_98], rbx
0x180021ad8  mov     rax, [rbp+0E0h+StringSid]
0x180021adc  lea     rcx, psz
0x180021ae3  test    rax, rax
0x180021ae6  cmovnz  rcx, rax; sourceString
0x180021aea  mov     r8d, 7FFFFFFFh
0x180021af0  mov     edx, r8d
0x180021af3  mov     rax, rcx
0x180021af6  cmp     [rax], di
0x180021af9  jz      short loc_180021B04
0x180021afb  add     rax, 2
0x180021aff  sub     rdx, r14
0x180021b02  jnz     short loc_180021AF6
0x180021b04  mov     rax, rdx
0x180021b07  neg     rax
0x180021b0a  sbb     edi, edi
0x180021b0c  not     edi
0x180021b0e  and     edi, 80070057h
0x180021b14  mov     rax, rdx
0x180021b17  sub     r8, rdx
0x180021b1a  neg     rax
0x180021b1d  sbb     r9, r9
0x180021b20  and     r9, r8
0x180021b23  xor     eax, eax
0x180021b25  test    rdx, rdx
0x180021b28  jnz     short loc_180021B2D
0x180021b2a  mov     r9d, eax
0x180021b2d  mov     [rsp+1E0h+string], rax
0x180021b32  test    edi, edi
0x180021b34  js      loc_180022028
0x180021b3a  lea     r8, [rsp+1E0h+string]; string
0x180021b3f  mov     edx, r9d; length
0x180021b42  call    cs:__imp_WindowsCreateString
0x180021b48  mov     edi, eax
0x180021b4a  test    eax, eax
0x180021b4c  js      loc_180022028
0x180021b52  mov     rbx, [rsp+1E0h+string]
0x180021b57  mov     [rbp+0E0h+var_98], rbx
0x180021b5b  xor     ecx, ecx; string
0x180021b5d  call    cs:__imp_WindowsDeleteString
0x180021b63  xor     edi, edi
0x180021b65  mov     [rsp+1E0h+var_178], rdi
0x180021b6a  mov     [rsp+1E0h+var_170], edi
0x180021b6e  lea     r9, [rbp+0E0h+var_60]; string
0x180021b75  lea     r8, [rbp+0E0h+hstringHeader]; hstringHeader
0x180021b7c  lea     edx, [rdi+2Ch]; length
0x180021b7f  lea     rcx, RuntimeClass_Windows_Management_Deployment_PackageManager; "Windows.Management.Deployment.PackageMa"...
0x180021b86  call    cs:__imp_WindowsCreateStringReference
0x180021b8c  test    eax, eax
0x180021b8e  jns     short loc_180021BA5
0x180021b90  xor     r9d, r9d; lpArguments
0x180021b93  xor     r8d, r8d; nNumberOfArguments
0x180021b96  mov     edx, r14d; dwExceptionFlags
0x180021b99  mov     ecx, 0C000000Dh; dwExceptionCode
0x180021b9e  call    cs:__imp_RaiseException
0x180021ba4  nop
0x180021ba5  lea     rax, [rsp+1E0h+var_178]
0x180021baa  mov     [rsp+1E0h+Sid], rax
0x180021baf  cmp     [rsp+1E0h+var_170], edi
0x180021bb3  jz      short loc_180021BD0
0x180021bb5  mov     rcx, [rsp+1E0h+var_178]
0x180021bba  test    rcx, rcx
0x180021bbd  jz      short loc_180021BCC
0x180021bbf  mov     rax, [rcx]
0x180021bc2  mov     rax, [rax+10h]
0x180021bc6  call    cs:__guard_dispatch_icall_fptr
0x180021bcc  mov     [rsp+1E0h+var_170], edi
0x180021bd0  mov     [rsp+1E0h+var_178], rdi
0x180021bd5  or      esi, 4
0x180021bd8  mov     [rsp+1E0h+var_1B0], esi
0x180021bdc  lea     r8, [rsp+1E0h+var_178]
0x180021be1  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180021be8  mov     rcx, [rbp+0E0h+var_60]
0x180021bef  call    cs:__imp_RoGetActivationFactory
0x180021bf5  mov     edi, eax
0x180021bf7  and     esi, 0FFFFFFFBh
0x180021bfa  mov     [rsp+1E0h+var_1B0], esi
0x180021bfe  mov     eax, [rsp+1E0h+var_170]
0x180021c02  xor     edx, edx
0x180021c04  cmp     [rsp+1E0h+var_178], rdx
0x180021c09  cmovnz  eax, r14d
0x180021c0d  mov     [rsp+1E0h+var_170], eax
0x180021c11  test    edi, edi
0x180021c13  js      loc_18002201D
0x180021c19  mov     [rbp+0E0h+var_F0], rdx
0x180021c1d  mov     [rbp+0E0h+var_E8], edx
0x180021c20  mov     rcx, [rsp+1E0h+var_178]
0x180021c25  lea     rax, [rbp+0E0h+var_F0]
0x180021c29  mov     [rsp+1E0h+Sid], rax
0x180021c2e  mov     [rbp+0E0h+var_F0], rdx
0x180021c32  or      esi, 8
0x180021c35  mov     [rsp+1E0h+var_1B0], esi
0x180021c39  mov     rax, [rcx]
0x180021c3c  lea     rdx, [rbp+0E0h+var_F0]
0x180021c40  mov     rax, [rax+30h]
0x180021c44  call    cs:__guard_dispatch_icall_fptr
0x180021c4a  mov     edi, eax
0x180021c4c  and     esi, 0FFFFFFF7h
0x180021c4f  mov     [rsp+1E0h+var_1B0], esi
0x180021c53  mov     eax, [rbp+0E0h+var_E8]
0x180021c56  xor     edx, edx
0x180021c58  cmp     [rbp+0E0h+var_F0], rdx
0x180021c5c  cmovnz  eax, r14d
0x180021c60  mov     [rbp+0E0h+var_E8], eax
0x180021c63  test    edi, edi
0x180021c65  js      loc_180022013
0x180021c6b  mov     [rbp+0E0h+var_100], rdx
0x180021c6f  mov     [rbp+0E0h+var_F8], edx
0x180021c72  mov     rcx, [rbp+0E0h+var_F0]
0x180021c76  lea     rax, [rbp+0E0h+var_100]
0x180021c7a  mov     [rsp+1E0h+Sid], rax
0x180021c7f  mov     [rbp+0E0h+var_100], rdx
0x180021c83  or      esi, 10h
  ... truncated ...
```
