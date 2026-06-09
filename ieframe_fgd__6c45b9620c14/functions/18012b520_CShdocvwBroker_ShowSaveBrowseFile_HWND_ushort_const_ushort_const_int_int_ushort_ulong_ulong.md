# CShdocvwBroker::ShowSaveBrowseFile(HWND__ *,ushort const *,ushort const *,int,int,ushort * *,ulong *,ulong *)

- ea: `0x18012b520`
- end: `0x18012b988`
- name: `?ShowSaveBrowseFile@CShdocvwBroker@@UEAAJPEAUHWND__@@PEBG1HHPEAPEAGPEAK3@Z`
- size: `1128`
- prototype: `int(CShdocvwBroker *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned __int16 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180011230`
- `0x18001132c`
- `0x180018eb0`
- `0x18002acc0`
- `0x180073910`
- `0x1800b36b8`
- `0x180127bb0`
- `0x18012b520`
- `0x180131730`
- `0x18054e310`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18012b88e`
- `KERNEL32!DeleteFileW` at `0x18012b88e`
- `KERNEL32!GetTempPath2W` at `0x18012b7ae`
- `KERNEL32!GetTempPath2W` at `0x18012b7ae`
- `KERNEL32!GetTempFileNameW` at `0x18012b87f`
- `KERNEL32!GetTempFileNameW` at `0x18012b87f`
- `KERNEL32!GetLastError` at `0x18012b849`
- `KERNEL32!GetLastError` at `0x18012b849`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18012b7df`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x18012b7df`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18012b6c8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18012b6c8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18012b89b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18012b89b`
- `OLEAUT32!__imp_SysFreeString` at `0x18012b5cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18012b5cd`
- `SHELL32!SHGetFolderPathW` at `0x18012b787`
- `SHELL32!SHGetFolderPathW` at `0x18012b787`
- `SHELL32!SHGetKnownFolderPath` at `0x18012b7ff`
- `SHELL32!SHGetKnownFolderPath` at `0x18012b7ff`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRevertToSelf` at `0x18012b78f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRevertToSelf` at `0x18012b78f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoImpersonateClient` at `0x18012b765`
- `api-ms-win-downlevel-ole32-l1-1-0!CoImpersonateClient` at `0x18012b765`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18012b92d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18012b92d`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x18012b74c`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x18012b74c`

## string_xrefs

- `0x18012b874`: `lrietemp`
- `0x18012b93b`: `CShdocvwBroker::SaveAsComplete,CShdocvwBroker::SaveAsFile`

## pseudocode

```c
__int64 __fastcall CShdocvwBroker::ShowSaveBrowseFile(
        CShdocvwBroker *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        unsigned __int16 **a7,
        unsigned int *a8,
        unsigned int *a9)
{
  __int64 result; // rax
  __int64 v14; // rcx
  OLECHAR *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  const unsigned __int16 *FileNameW; // rax
  __int64 v19; // r9
  __int64 v20; // rax
  PWSTR v21; // rcx
  HRESULT v22; // ebx
  HRESULT v23; // eax
  ULONG v24; // r9d
  ULONG v25; // r9d
  signed int LastError; // eax
  UINT TempFileNameW; // ebx
  ULONG v28; // r9d
  HRESULT v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v33[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR *ppwsz; // [rsp+58h] [rbp-A8h]
  _QWORD v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v36[5]; // [rsp+70h] [rbp-90h] BYREF
  bool v37; // [rsp+98h] [rbp-68h]
  bool v38; // [rsp+99h] [rbp-67h]
  int v39; // [rsp+9Ah] [rbp-66h]
  __int16 v40; // [rsp+9Eh] [rbp-62h]
  __int64 v41; // [rsp+A0h] [rbp-60h]
  _QWORD Parameter[3]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR PathName[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR TempFileName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pszMore[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v46[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  ppwsz = a7;
  ppszPath = (PWSTR)a9;
  result = VerifyHwndIsIE(a2);
  v29 = result;
  if ( (int)result >= 0 )
  {
    v14 = *((_QWORD *)this + 865);
    PathName[0] = 0;
    v33[0] = 0;
    v33[1] = a4;
    v30 = 3;
    if ( v14 )
    {
      v15 = *(OLECHAR **)(v14 + 8);
      if ( v15 )
        SysFreeString(v15);
    }
    else
    {
      *((_QWORD *)this + 865) = operator new(0x10u);
    }
    v16 = *((_QWORD *)this + 865);
    v35[1] = (char *)this + 32;
    *(_DWORD *)(v16 + 4) = 0;
    **((_DWORD **)this + 865) = 0;
    *(_QWORD *)(*((_QWORD *)this + 865) + 8LL) = 0;
    v35[0] = &v29;
    if ( *((_QWORD *)this + 4) )
    {
      CBrokerCallStateReset::~CBrokerCallStateReset((CBrokerCallStateReset *)v35);
      return 2147947423LL;
    }
    else
    {
      v17 = StringCchCopyW((unsigned __int16 *)this + 336, 0x104u, a3);
      v29 = v17;
      if ( v17 >= 0 )
      {
        v36[3] = v33;
        v36[0] = a2;
        v36[4] = &v30;
        v37 = a5 != 0;
        v41 = *((_QWORD *)this + 865);
        Parameter[0] = &CShdocvwBroker::CShowSaveBrowseFile::`vftable';
        v38 = a6 != 0;
        v36[2] = 260;
        Parameter[1] = v36;
        v39 = 0;
        v40 = 0;
        v36[1] = (char *)this + 672;
        v17 = CShdocvwBroker::CSTAWorkItem<CShdocvwBroker::_internet_options_params>::Run(Parameter);
        v29 = v17;
      }
      if ( !v17 )
      {
        FileNameW = PathFindFileNameW((LPCWSTR)this + 336);
        v29 = StringCchCopyW(pszMore, 0x104u, FileNameW);
        if ( v29 >= 0 )
        {
          v19 = -1;
          v20 = -1;
          do
            ++v20;
          while ( pszMore[v20] );
          do
            ++v19;
          while ( *((_WORD *)this + v19 + 336) );
          v29 = StringCchCopyNW(v46, 0x104u, (const unsigned __int16 *)this + 336, v19 - v20);
          if ( v29 >= 0 )
          {
            v21 = ppszPath;
            *a8 = HIDWORD(v33[0]);
            v31 = 0;
            *(_DWORD *)v21 = v30;
            v29 = IEGetCOMCallerIntegrity((enum _IsoIntegrity *)&v31);
            if ( v29 >= 0 )
            {
              if ( v31 >= 123 )
              {
                if ( (unsigned int)GetTempPath2W(260, PathName) )
                {
                  v29 = PathCchAppendEx(PathName, 0x104u, L"Low", v24);
                  if ( v29 >= 0 && !PathFileExistsW(PathName) )
                  {
                    ppszPath = 0;
                    v29 = SHGetKnownFolderPath(&FOLDERID_LocalAppDataLow, 0, 0, &ppszPath);
                    if ( v29 >= 0 )
                    {
                      v29 = StringCchCopyW(PathName, 0x104u, ppszPath);
                      if ( v29 >= 0 )
                        v29 = PathCchAppendEx(PathName, 0x104u, L"Microsoft\\Internet Explorer", v25);
                    }
                    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszPath);
                  }
                }
                else
                {
                  LastError = GetLastError();
                  if ( LastError > 0 )
                    LastError = (unsigned __int16)LastError | 0x80070000;
                  v29 = LastError;
                }
              }
              else
              {
                v22 = CoImpersonateClient();
                if ( v22 >= 0 )
                {
                  v22 = SHGetFolderPathW(0, 32796, 0, 0, PathName);
                  v23 = CoRevertToSelf();
                  if ( v22 >= 0 && v23 < 0 )
                    v22 = v23;
                }
                v29 = v22;
              }
            }
            if ( v29 >= 0 )
            {
              TempFileNameW = GetTempFileNameW(PathName, L"lrietemp", 0, TempFileName);
              DeleteFileW(TempFileName);
              PathRemoveExtensionW(TempFileName);
              if ( TempFileNameW )
              {
                v29 = StringCchCopyW((unsigned __int16 *)this + 336, 0x104u, pszMore);
                if ( v29 >= 0 )
                {
                  v29 = StringCchCopyW((unsigned __int16 *)this + 856, 0x104u, v46);
                  if ( v29 >= 0 )
                  {
                    v29 = StringCchCopyW((unsigned __int16 *)this + 1116, 0x104u, TempFileName);
                    if ( v29 >= 0 )
                    {
                      v29 = PathCchAppendEx(TempFileName, 0x104u, pszMore, v28);
                      if ( v29 >= 0 )
                      {
                        v29 = SHStrDupW(TempFileName, ppwsz);
                        if ( !v29 )
                          *((_QWORD *)this + 4) = "CShdocvwBroker::SaveAsComplete,CShdocvwBroker::SaveAsFile";
                      }
                    }
                  }
                }
              }
              else
              {
                v29 = -2147467259;
              }
            }
          }
        }
      }
      CBrokerCallStateReset::~CBrokerCallStateReset((CBrokerCallStateReset *)v35);
      return (unsigned int)v29;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18012b520  mov     [rsp-8+arg_18], rbx
0x18012b525  push    rbp
0x18012b526  push    rsi
0x18012b527  push    rdi
0x18012b528  push    r12
0x18012b52a  push    r13
0x18012b52c  push    r14
0x18012b52e  push    r15
0x18012b530  lea     rbp, [rsp-810h]
0x18012b538  sub     rsp, 910h
0x18012b53f  mov     rax, cs:__security_cookie
0x18012b546  xor     rax, rsp
0x18012b549  mov     [rbp+840h+var_40], rax
0x18012b550  mov     rax, [rbp+840h+arg_30]
0x18012b557  mov     rdi, rcx
0x18012b55a  mov     r13, [rbp+840h+arg_38]
0x18012b561  mov     rcx, rdx
0x18012b564  mov     [rsp+940h+ppwsz], rax
0x18012b569  mov     rbx, r9
0x18012b56c  mov     rax, [rbp+840h+arg_40]
0x18012b573  mov     r14, r8
0x18012b576  mov     [rsp+940h+ppszPath], rax
0x18012b57b  mov     r15, rdx
0x18012b57e  call    _VerifyHwndIsIE
0x18012b583  xor     esi, esi
0x18012b585  mov     [rsp+940h+var_910], eax
0x18012b589  test    eax, eax
0x18012b58b  js      loc_18012B95E
0x18012b591  mov     rcx, [rdi+1B08h]
0x18012b598  mov     [rbp+840h+PathName], si
0x18012b59c  mov     [rsp+940h+var_8F8], rsi
0x18012b5a1  mov     [rsp+940h+var_8F0], rbx
0x18012b5a6  mov     [rsp+940h+var_90C], 3
0x18012b5ae  test    rcx, rcx
0x18012b5b1  jnz     short loc_18012B5C4
0x18012b5b3  lea     ecx, [rsi+10h]; dwBytes
0x18012b5b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012b5bb  mov     [rdi+1B08h], rax
0x18012b5c2  jmp     short loc_18012B5D3
0x18012b5c4  mov     rcx, [rcx+8]; bstrString
0x18012b5c8  test    rcx, rcx
0x18012b5cb  jz      short loc_18012B5D3
0x18012b5cd  call    cs:__imp_SysFreeString
0x18012b5d3  mov     rax, [rdi+1B08h]
0x18012b5da  lea     r12, [rdi+20h]
0x18012b5de  mov     [rsp+940h+var_8D8], r12
0x18012b5e3  mov     [rax+4], esi
0x18012b5e6  mov     rax, [rdi+1B08h]
0x18012b5ed  mov     [rax], esi
0x18012b5ef  mov     rax, [rdi+1B08h]
0x18012b5f6  mov     [rax+8], rsi
0x18012b5fa  lea     rax, [rsp+940h+var_910]
0x18012b5ff  mov     [rsp+940h+var_8E0], rax
0x18012b604  cmp     [r12], rsi
0x18012b608  jz      short loc_18012B61E
0x18012b60a  lea     rcx, [rsp+940h+var_8E0]; this
0x18012b60f  call    ??1CBrokerCallStateReset@@QEAA@XZ; CBrokerCallStateReset::~CBrokerCallStateReset(void)
0x18012b614  mov     eax, 8007139Fh
0x18012b619  jmp     loc_18012B95E
0x18012b61e  lea     rsi, [rdi+2A0h]
0x18012b625  mov     r8, r14; unsigned __int16 *
0x18012b628  mov     rcx, rsi; unsigned __int16 *
0x18012b62b  mov     edx, 104h; unsigned __int64
0x18012b630  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b635  xor     r14d, r14d
0x18012b638  mov     [rsp+940h+var_910], eax
0x18012b63c  test    eax, eax
0x18012b63e  js      short loc_18012B6B7
0x18012b640  cmp     [rbp+840h+arg_20], r14d
0x18012b647  lea     rax, [rsp+940h+var_8F8]
0x18012b64c  mov     [rbp+840h+var_8B8], rax
0x18012b650  lea     rcx, [rbp+840h+Parameter]; lpParameter
0x18012b654  lea     rax, [rsp+940h+var_90C]
0x18012b659  mov     [rsp+940h+var_8D0], r15
0x18012b65e  mov     [rbp+840h+var_8B0], rax
0x18012b662  setnz   [rbp+840h+var_8A8]
0x18012b666  mov     rax, [rdi+1B08h]
0x18012b66d  mov     r15d, 104h
0x18012b673  cmp     [rbp+840h+arg_28], r14d
0x18012b67a  mov     [rbp+840h+var_8A0], rax
0x18012b67e  lea     rax, ??_7CShowSaveBrowseFile@CShdocvwBroker@@6B@; const CShdocvwBroker::CShowSaveBrowseFile::`vftable'
0x18012b685  mov     [rbp+840h+Parameter], rax
0x18012b689  setnz   [rbp+840h+var_8A7]
0x18012b68d  lea     rax, [rsp+940h+var_8D0]
0x18012b692  mov     [rbp+840h+var_8C0], 104h
0x18012b69a  mov     [rbp+840h+var_890], rax
0x18012b69e  mov     [rbp+840h+var_8A6], r14d
0x18012b6a2  mov     [rbp+840h+var_8A2], r14w
0x18012b6a7  mov     [rsp+940h+var_8C8], rsi
0x18012b6ac  call    ?Run@?$CSTAWorkItem@U_internet_options_params@CShdocvwBroker@@@CShdocvwBroker@@QEAAJXZ; CShdocvwBroker::CSTAWorkItem<CShdocvwBroker::_internet_options_params>::Run(void)
0x18012b6b1  mov     [rsp+940h+var_910], eax
0x18012b6b5  jmp     short loc_18012B6BD
0x18012b6b7  mov     r15d, 104h
0x18012b6bd  test    eax, eax
0x18012b6bf  jnz     loc_18012B950
0x18012b6c5  mov     rcx, rsi; pszPath
0x18012b6c8  call    cs:__imp_PathFindFileNameW
0x18012b6ce  mov     rdx, r15; unsigned __int64
0x18012b6d1  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x18012b6d8  mov     r8, rax; unsigned __int16 *
0x18012b6db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b6e0  mov     [rsp+940h+var_910], eax
0x18012b6e4  test    eax, eax
0x18012b6e6  js      loc_18012B950
0x18012b6ec  or      r9, 0FFFFFFFFFFFFFFFFh
0x18012b6f0  lea     rcx, [rbp+840h+pszMore]
0x18012b6f7  mov     rax, r9
0x18012b6fa  inc     rax
0x18012b6fd  cmp     [rcx+rax*2], r14w
0x18012b702  jnz     short loc_18012B6FA
0x18012b704  inc     r9
0x18012b707  cmp     [rsi+r9*2], r14w
0x18012b70c  jnz     short loc_18012B704
0x18012b70e  sub     r9, rax; unsigned __int64
0x18012b711  lea     rcx, [rbp+840h+var_250]; unsigned __int16 *
0x18012b718  mov     r8, rsi; unsigned __int16 *
0x18012b71b  mov     rdx, r15; unsigned __int64
0x18012b71e  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18012b723  mov     [rsp+940h+var_910], eax
0x18012b727  test    eax, eax
0x18012b729  js      loc_18012B950
0x18012b72f  mov     eax, dword ptr [rsp+940h+var_8F8+4]
0x18012b733  mov     rcx, [rsp+940h+ppszPath]
0x18012b738  mov     [r13+0], eax
0x18012b73c  mov     eax, [rsp+940h+var_90C]
0x18012b740  mov     [rsp+940h+var_908], r14d
0x18012b745  mov     [rcx], eax
0x18012b747  lea     rcx, [rsp+940h+var_908]
0x18012b74c  call    cs:__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z; IEGetCOMCallerIntegrity(_IsoIntegrity *)
0x18012b752  mov     [rsp+940h+var_910], eax
0x18012b756  test    eax, eax
0x18012b758  js      loc_18012B85F
0x18012b75e  cmp     [rsp+940h+var_908], 7Bh ; '{'
0x18012b763  jge     short loc_18012B7A7
0x18012b765  call    cs:__imp_CoImpersonateClient
0x18012b76b  mov     ebx, eax
0x18012b76d  test    eax, eax
0x18012b76f  js      short loc_18012B79E
0x18012b771  lea     rax, [rbp+840h+PathName]
0x18012b775  xor     r9d, r9d; dwFlags
0x18012b778  xor     r8d, r8d; hToken
0x18012b77b  mov     [rsp+940h+pszPath], rax; pszPath
0x18012b780  mov     edx, 801Ch; csidl
0x18012b785  xor     ecx, ecx; hwnd
0x18012b787  call    cs:__imp_SHGetFolderPathW
0x18012b78d  mov     ebx, eax
0x18012b78f  call    cs:__imp_CoRevertToSelf
0x18012b795  test    ebx, ebx
0x18012b797  js      short loc_18012B79E
0x18012b799  test    eax, eax
0x18012b79b  cmovs   ebx, eax
0x18012b79e  mov     [rsp+940h+var_910], ebx
0x18012b7a2  jmp     loc_18012B85F
0x18012b7a7  lea     rdx, [rbp+840h+PathName]
0x18012b7ab  mov     ecx, r15d
0x18012b7ae  call    cs:__imp_GetTempPath2W
0x18012b7b4  test    eax, eax
0x18012b7b6  jz      loc_18012B849
0x18012b7bc  lea     r8, aLow; "Low"
0x18012b7c3  mov     rdx, r15; cchPath
0x18012b7c6  lea     rcx, [rbp+840h+PathName]; pszPath
0x18012b7ca  call    PathCchAppendEx
0x18012b7cf  mov     [rsp+940h+var_910], eax
0x18012b7d3  test    eax, eax
0x18012b7d5  js      loc_18012B85F
0x18012b7db  lea     rcx, [rbp+840h+PathName]; pszPath
0x18012b7df  call    cs:__imp_PathFileExistsW
0x18012b7e5  test    eax, eax
0x18012b7e7  jnz     short loc_18012B85F
0x18012b7e9  lea     r9, [rsp+940h+ppszPath]; ppszPath
0x18012b7ee  mov     [rsp+940h+ppszPath], r14
0x18012b7f3  xor     r8d, r8d; hToken
0x18012b7f6  lea     rcx, FOLDERID_LocalAppDataLow; rfid
0x18012b7fd  xor     edx, edx; dwFlags
0x18012b7ff  call    cs:__imp_SHGetKnownFolderPath
0x18012b805  mov     [rsp+940h+var_910], eax
0x18012b809  test    eax, eax
0x18012b80b  js      short loc_18012B83D
0x18012b80d  mov     r8, [rsp+940h+ppszPath]; unsigned __int16 *
0x18012b812  lea     rcx, [rbp+840h+PathName]; unsigned __int16 *
0x18012b816  mov     rdx, r15; unsigned __int64
0x18012b819  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b81e  mov     [rsp+940h+var_910], eax
0x18012b822  test    eax, eax
0x18012b824  js      short loc_18012B83D
0x18012b826  lea     r8, aMicrosoftInter_10; "Microsoft\\Internet Explorer"
0x18012b82d  mov     rdx, r15; cchPath
0x18012b830  lea     rcx, [rbp+840h+PathName]; pszPath
0x18012b834  call    PathCchAppendEx
0x18012b839  mov     [rsp+940h+var_910], eax
0x18012b83d  lea     rcx, [rsp+940h+ppszPath]
0x18012b842  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18012b847  jmp     short loc_18012B85F
0x18012b849  call    cs:__imp_GetLastError
0x18012b84f  test    eax, eax
0x18012b851  jle     short loc_18012B85B
0x18012b853  movzx   eax, ax
0x18012b856  or      eax, 80070000h
0x18012b85b  mov     [rsp+940h+var_910], eax
0x18012b85f  cmp     [rsp+940h+var_910], r14d
0x18012b864  jl      loc_18012B950
0x18012b86a  lea     r9, [rbp+840h+TempFileName]; lpTempFileName
0x18012b871  xor     r8d, r8d; uUnique
0x18012b874  lea     rdx, aLrietemp; "lrietemp"
0x18012b87b  lea     rcx, [rbp+840h+PathName]; lpPathName
0x18012b87f  call    cs:__imp_GetTempFileNameW
0x18012b885  lea     rcx, [rbp+840h+TempFileName]; lpFileName
0x18012b88c  mov     ebx, eax
0x18012b88e  call    cs:__imp_DeleteFileW
0x18012b894  lea     rcx, [rbp+840h+TempFileName]; pszPath
0x18012b89b  call    cs:__imp_PathRemoveExtensionW
0x18012b8a1  test    ebx, ebx
0x18012b8a3  jz      loc_18012B948
0x18012b8a9  lea     r8, [rbp+840h+pszMore]; unsigned __int16 *
0x18012b8b0  mov     rdx, r15; unsigned __int64
0x18012b8b3  mov     rcx, rsi; unsigned __int16 *
0x18012b8b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b8bb  mov     [rsp+940h+var_910], eax
0x18012b8bf  test    eax, eax
0x18012b8c1  js      loc_18012B950
0x18012b8c7  lea     rcx, [rdi+6B0h]; unsigned __int16 *
0x18012b8ce  mov     rdx, r15; unsigned __int64
0x18012b8d1  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x18012b8d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b8dd  mov     [rsp+940h+var_910], eax
0x18012b8e1  test    eax, eax
0x18012b8e3  js      short loc_18012B950
0x18012b8e5  lea     rcx, [rdi+8B8h]; unsigned __int16 *
0x18012b8ec  mov     rdx, r15; unsigned __int64
0x18012b8ef  lea     r8, [rbp+840h+TempFileName]; unsigned __int16 *
0x18012b8f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012b8fb  mov     [rsp+940h+var_910], eax
0x18012b8ff  test    eax, eax
0x18012b901  js      short loc_18012B950
0x18012b903  lea     r8, [rbp+840h+pszMore]; pszMore
0x18012b90a  mov     rdx, r15; cchPath
0x18012b90d  lea     rcx, [rbp+840h+TempFileName]; pszPath
0x18012b914  call    PathCchAppendEx
0x18012b919  mov     [rsp+940h+var_910], eax
0x18012b91d  test    eax, eax
0x18012b91f  js      short loc_18012B950
0x18012b921  mov     rdx, [rsp+940h+ppwsz]; ppwsz
0x18012b926  lea     rcx, [rbp+840h+TempFileName]; psz
0x18012b92d  call    cs:__imp_SHStrDupW
0x18012b933  mov     [rsp+940h+var_910], eax
0x18012b937  test    eax, eax
0x18012b939  jnz     short loc_18012B950
0x18012b93b  lea     rax, aCshdocvwbroker_7; "CShdocvwBroker::SaveAsComplete,CShdocvw"...
0x18012b942  mov     [r12], rax
0x18012b946  jmp     short loc_18012B950
0x18012b948  mov     [rsp+940h+var_910], 80004005h
0x18012b950  lea     rcx, [rsp+940h+var_8E0]; this
0x18012b955  call    ??1CBrokerCallStateReset@@QEAA@XZ; CBrokerCallStateReset::~CBrokerCallStateReset(void)
0x18012b95a  mov     eax, [rsp+940h+var_910]
0x18012b95e  mov     rcx, [rbp+840h+var_40]
0x18012b965  xor     rcx, rsp; StackCookie
0x18012b968  call    __security_check_cookie
0x18012b96d  mov     rbx, [rsp+940h+arg_18]
0x18012b975  add     rsp, 910h
0x18012b97c  pop     r15
0x18012b97e  pop     r14
0x18012b980  pop     r13
0x18012b982  pop     r12
0x18012b984  pop     rdi
0x18012b985  pop     rsi
0x18012b986  pop     rbp
0x18012b987  retn
```
