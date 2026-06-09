# CShdocvwBroker::ShowSaveBrowseFile(HWND__ *,ushort const *,ushort const *,int,int,ushort * *,ulong *,ulong *)

- ea: `0x180138fd0`
- end: `0x180139491`
- name: `?ShowSaveBrowseFile@CShdocvwBroker@@UEAAJPEAUHWND__@@PEBG1HHPEAPEAGPEAK3@Z`
- size: `1217`
- prototype: `int(CShdocvwBroker *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, int, int, unsigned __int16 **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005b3c`
- `0x180007010`
- `0x1800144d0`
- `0x1800423a4`
- `0x180078b9c`
- `0x1800b9fd4`
- `0x180135370`
- `0x180138fd0`
- `0x18013f7e0`
- `0x180591f80`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180139384`
- `KERNEL32!DeleteFileW` at `0x180139384`
- `KERNEL32!GetTempPath2W` at `0x180139282`
- `KERNEL32!GetTempPath2W` at `0x180139282`
- `KERNEL32!GetTempFileNameW` at `0x18013936f`
- `KERNEL32!GetTempFileNameW` at `0x18013936f`
- `KERNEL32!GetLastError` at `0x180139333`
- `KERNEL32!GetLastError` at `0x180139333`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1801392b9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFileExistsW` at `0x1801392b9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18013917e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x18013917e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180139397`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180139397`
- `OLEAUT32!__imp_SysFreeString` at `0x18013907d`
- `OLEAUT32!__imp_SysFreeString` at `0x18013907d`
- `SHELL32!SHGetFolderPathW` at `0x18013924f`
- `SHELL32!SHGetFolderPathW` at `0x18013924f`
- `SHELL32!SHGetKnownFolderPath` at `0x1801392e3`
- `SHELL32!SHGetKnownFolderPath` at `0x1801392e3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRevertToSelf` at `0x18013925d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoRevertToSelf` at `0x18013925d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoImpersonateClient` at `0x180139227`
- `api-ms-win-downlevel-ole32-l1-1-0!CoImpersonateClient` at `0x180139227`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18013942f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18013942f`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x180139208`
- `msIso!__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z` at `0x180139208`

## string_xrefs

- `0x180139364`: `lrietemp`
- `0x180139443`: `CShdocvwBroker::SaveAsComplete,CShdocvwBroker::SaveAsFile`

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
0x180138fd0  mov     [rsp-8+arg_18], rbx
0x180138fd5  push    rbp
0x180138fd6  push    rsi
0x180138fd7  push    rdi
0x180138fd8  push    r12
0x180138fda  push    r13
0x180138fdc  push    r14
0x180138fde  push    r15
0x180138fe0  lea     rbp, [rsp-810h]
0x180138fe8  sub     rsp, 910h
0x180138fef  mov     rax, cs:__security_cookie
0x180138ff6  xor     rax, rsp
0x180138ff9  mov     [rbp+840h+var_40], rax
0x180139000  mov     rax, [rbp+840h+arg_30]
0x180139007  mov     rdi, rcx
0x18013900a  mov     r13, [rbp+840h+arg_38]
0x180139011  mov     rcx, rdx
0x180139014  mov     [rsp+940h+ppwsz], rax
0x180139019  mov     rbx, r9
0x18013901c  mov     rax, [rbp+840h+arg_40]
0x180139023  mov     r14, r8
0x180139026  mov     [rsp+940h+ppszPath], rax
0x18013902b  mov     r15, rdx
0x18013902e  call    _VerifyHwndIsIE
0x180139033  xor     esi, esi
0x180139035  mov     [rsp+940h+var_910], eax
0x180139039  test    eax, eax
0x18013903b  js      loc_180139466
0x180139041  mov     rcx, [rdi+1B08h]
0x180139048  mov     [rbp+840h+PathName], si
0x18013904c  mov     [rsp+940h+var_8F8], rsi
0x180139051  mov     [rsp+940h+var_8F0], rbx
0x180139056  mov     [rsp+940h+var_90C], 3
0x18013905e  test    rcx, rcx
0x180139061  jnz     short loc_180139074
0x180139063  lea     ecx, [rsi+10h]; dwBytes
0x180139066  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18013906b  mov     [rdi+1B08h], rax
0x180139072  jmp     short loc_180139089
0x180139074  mov     rcx, [rcx+8]; bstrString
0x180139078  test    rcx, rcx
0x18013907b  jz      short loc_180139089
0x18013907d  call    cs:__imp_SysFreeString
0x180139084  nop     dword ptr [rax+rax+00h]
0x180139089  mov     rax, [rdi+1B08h]
0x180139090  lea     r12, [rdi+20h]
0x180139094  mov     [rsp+940h+var_8D8], r12
0x180139099  mov     [rax+4], esi
0x18013909c  mov     rax, [rdi+1B08h]
0x1801390a3  mov     [rax], esi
0x1801390a5  mov     rax, [rdi+1B08h]
0x1801390ac  mov     [rax+8], rsi
0x1801390b0  lea     rax, [rsp+940h+var_910]
0x1801390b5  mov     [rsp+940h+var_8E0], rax
0x1801390ba  cmp     [r12], rsi
0x1801390be  jz      short loc_1801390D4
0x1801390c0  lea     rcx, [rsp+940h+var_8E0]; this
0x1801390c5  call    ??1CBrokerCallStateReset@@QEAA@XZ; CBrokerCallStateReset::~CBrokerCallStateReset(void)
0x1801390ca  mov     eax, 8007139Fh
0x1801390cf  jmp     loc_180139466
0x1801390d4  lea     rsi, [rdi+2A0h]
0x1801390db  mov     r8, r14; unsigned __int16 *
0x1801390de  mov     rcx, rsi; unsigned __int16 *
0x1801390e1  mov     edx, 104h; unsigned __int64
0x1801390e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801390eb  xor     r14d, r14d
0x1801390ee  mov     [rsp+940h+var_910], eax
0x1801390f2  test    eax, eax
0x1801390f4  js      short loc_18013916D
0x1801390f6  cmp     [rbp+840h+arg_20], r14d
0x1801390fd  lea     rax, [rsp+940h+var_8F8]
0x180139102  mov     [rbp+840h+var_8B8], rax
0x180139106  lea     rcx, [rbp+840h+Parameter]; lpParameter
0x18013910a  lea     rax, [rsp+940h+var_90C]
0x18013910f  mov     [rsp+940h+var_8D0], r15
0x180139114  mov     [rbp+840h+var_8B0], rax
0x180139118  setnz   [rbp+840h+var_8A8]
0x18013911c  mov     rax, [rdi+1B08h]
0x180139123  mov     r15d, 104h
0x180139129  cmp     [rbp+840h+arg_28], r14d
0x180139130  mov     [rbp+840h+var_8A0], rax
0x180139134  lea     rax, ??_7CShowSaveBrowseFile@CShdocvwBroker@@6B@; const CShdocvwBroker::CShowSaveBrowseFile::`vftable'
0x18013913b  mov     [rbp+840h+Parameter], rax
0x18013913f  setnz   [rbp+840h+var_8A7]
0x180139143  lea     rax, [rsp+940h+var_8D0]
0x180139148  mov     [rbp+840h+var_8C0], 104h
0x180139150  mov     [rbp+840h+var_890], rax
0x180139154  mov     [rbp+840h+var_8A6], r14d
0x180139158  mov     [rbp+840h+var_8A2], r14w
0x18013915d  mov     [rsp+940h+var_8C8], rsi
0x180139162  call    ?Run@?$CSTAWorkItem@U_internet_options_params@CShdocvwBroker@@@CShdocvwBroker@@QEAAJXZ; CShdocvwBroker::CSTAWorkItem<CShdocvwBroker::_internet_options_params>::Run(void)
0x180139167  mov     [rsp+940h+var_910], eax
0x18013916b  jmp     short loc_180139173
0x18013916d  mov     r15d, 104h
0x180139173  test    eax, eax
0x180139175  jnz     loc_180139458
0x18013917b  mov     rcx, rsi; pszPath
0x18013917e  call    cs:__imp_PathFindFileNameW
0x180139185  nop     dword ptr [rax+rax+00h]
0x18013918a  mov     rdx, r15; unsigned __int64
0x18013918d  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x180139194  mov     r8, rax; unsigned __int16 *
0x180139197  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18013919c  mov     [rsp+940h+var_910], eax
0x1801391a0  test    eax, eax
0x1801391a2  js      loc_180139458
0x1801391a8  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801391ac  lea     rcx, [rbp+840h+pszMore]
0x1801391b3  mov     rax, r9
0x1801391b6  inc     rax
0x1801391b9  cmp     [rcx+rax*2], r14w
0x1801391be  jnz     short loc_1801391B6
0x1801391c0  inc     r9
0x1801391c3  cmp     [rsi+r9*2], r14w
0x1801391c8  jnz     short loc_1801391C0
0x1801391ca  sub     r9, rax; unsigned __int64
0x1801391cd  lea     rcx, [rbp+840h+var_250]; unsigned __int16 *
0x1801391d4  mov     r8, rsi; unsigned __int16 *
0x1801391d7  mov     rdx, r15; unsigned __int64
0x1801391da  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1801391df  mov     [rsp+940h+var_910], eax
0x1801391e3  test    eax, eax
0x1801391e5  js      loc_180139458
0x1801391eb  mov     eax, dword ptr [rsp+940h+var_8F8+4]
0x1801391ef  mov     rcx, [rsp+940h+ppszPath]
0x1801391f4  mov     [r13+0], eax
0x1801391f8  mov     eax, [rsp+940h+var_90C]
0x1801391fc  mov     [rsp+940h+var_908], r14d
0x180139201  mov     [rcx], eax
0x180139203  lea     rcx, [rsp+940h+var_908]
0x180139208  call    cs:__imp_?IEGetCOMCallerIntegrity@@YAJPEAW4_IsoIntegrity@@@Z; IEGetCOMCallerIntegrity(_IsoIntegrity *)
0x18013920f  nop     dword ptr [rax+rax+00h]
0x180139214  mov     [rsp+940h+var_910], eax
0x180139218  test    eax, eax
0x18013921a  js      loc_18013934F
0x180139220  cmp     [rsp+940h+var_908], 7Bh ; '{'
0x180139225  jge     short loc_18013927B
0x180139227  call    cs:__imp_CoImpersonateClient
0x18013922e  nop     dword ptr [rax+rax+00h]
0x180139233  mov     ebx, eax
0x180139235  test    eax, eax
0x180139237  js      short loc_180139272
0x180139239  lea     rax, [rbp+840h+PathName]
0x18013923d  xor     r9d, r9d; dwFlags
0x180139240  xor     r8d, r8d; hToken
0x180139243  mov     [rsp+940h+pszPath], rax; pszPath
0x180139248  mov     edx, 801Ch; csidl
0x18013924d  xor     ecx, ecx; hwnd
0x18013924f  call    cs:__imp_SHGetFolderPathW
0x180139256  nop     dword ptr [rax+rax+00h]
0x18013925b  mov     ebx, eax
0x18013925d  call    cs:__imp_CoRevertToSelf
0x180139264  nop     dword ptr [rax+rax+00h]
0x180139269  test    ebx, ebx
0x18013926b  js      short loc_180139272
0x18013926d  test    eax, eax
0x18013926f  cmovs   ebx, eax
0x180139272  mov     [rsp+940h+var_910], ebx
0x180139276  jmp     loc_18013934F
0x18013927b  lea     rdx, [rbp+840h+PathName]
0x18013927f  mov     ecx, r15d
0x180139282  call    cs:__imp_GetTempPath2W
0x180139289  nop     dword ptr [rax+rax+00h]
0x18013928e  test    eax, eax
0x180139290  jz      loc_180139333
0x180139296  lea     r8, aLow; "Low"
0x18013929d  mov     rdx, r15; cchPath
0x1801392a0  lea     rcx, [rbp+840h+PathName]; pszPath
0x1801392a4  call    PathCchAppendEx
0x1801392a9  mov     [rsp+940h+var_910], eax
0x1801392ad  test    eax, eax
0x1801392af  js      loc_18013934F
0x1801392b5  lea     rcx, [rbp+840h+PathName]; pszPath
0x1801392b9  call    cs:__imp_PathFileExistsW
0x1801392c0  nop     dword ptr [rax+rax+00h]
0x1801392c5  test    eax, eax
0x1801392c7  jnz     loc_18013934F
0x1801392cd  lea     r9, [rsp+940h+ppszPath]; ppszPath
0x1801392d2  mov     [rsp+940h+ppszPath], r14
0x1801392d7  xor     r8d, r8d; hToken
0x1801392da  lea     rcx, FOLDERID_LocalAppDataLow; rfid
0x1801392e1  xor     edx, edx; dwFlags
0x1801392e3  call    cs:__imp_SHGetKnownFolderPath
0x1801392ea  nop     dword ptr [rax+rax+00h]
0x1801392ef  mov     [rsp+940h+var_910], eax
0x1801392f3  test    eax, eax
0x1801392f5  js      short loc_180139327
0x1801392f7  mov     r8, [rsp+940h+ppszPath]; unsigned __int16 *
0x1801392fc  lea     rcx, [rbp+840h+PathName]; unsigned __int16 *
0x180139300  mov     rdx, r15; unsigned __int64
0x180139303  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180139308  mov     [rsp+940h+var_910], eax
0x18013930c  test    eax, eax
0x18013930e  js      short loc_180139327
0x180139310  lea     r8, aMicrosoftInter_10; "Microsoft\\Internet Explorer"
0x180139317  mov     rdx, r15; cchPath
0x18013931a  lea     rcx, [rbp+840h+PathName]; pszPath
0x18013931e  call    PathCchAppendEx
0x180139323  mov     [rsp+940h+var_910], eax
0x180139327  lea     rcx, [rsp+940h+ppszPath]
0x18013932c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180139331  jmp     short loc_18013934F
0x180139333  call    cs:__imp_GetLastError
0x18013933a  nop     dword ptr [rax+rax+00h]
0x18013933f  test    eax, eax
0x180139341  jle     short loc_18013934B
0x180139343  movzx   eax, ax
0x180139346  or      eax, 80070000h
0x18013934b  mov     [rsp+940h+var_910], eax
0x18013934f  cmp     [rsp+940h+var_910], r14d
0x180139354  jl      loc_180139458
0x18013935a  lea     r9, [rbp+840h+TempFileName]; lpTempFileName
0x180139361  xor     r8d, r8d; uUnique
0x180139364  lea     rdx, aLrietemp; "lrietemp"
0x18013936b  lea     rcx, [rbp+840h+PathName]; lpPathName
0x18013936f  call    cs:__imp_GetTempFileNameW
0x180139376  nop     dword ptr [rax+rax+00h]
0x18013937b  lea     rcx, [rbp+840h+TempFileName]; lpFileName
0x180139382  mov     ebx, eax
0x180139384  call    cs:__imp_DeleteFileW
0x18013938b  nop     dword ptr [rax+rax+00h]
0x180139390  lea     rcx, [rbp+840h+TempFileName]; pszPath
0x180139397  call    cs:__imp_PathRemoveExtensionW
0x18013939e  nop     dword ptr [rax+rax+00h]
0x1801393a3  test    ebx, ebx
0x1801393a5  jz      loc_180139450
0x1801393ab  lea     r8, [rbp+840h+pszMore]; unsigned __int16 *
0x1801393b2  mov     rdx, r15; unsigned __int64
0x1801393b5  mov     rcx, rsi; unsigned __int16 *
0x1801393b8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801393bd  mov     [rsp+940h+var_910], eax
0x1801393c1  test    eax, eax
0x1801393c3  js      loc_180139458
0x1801393c9  lea     rcx, [rdi+6B0h]; unsigned __int16 *
0x1801393d0  mov     rdx, r15; unsigned __int64
0x1801393d3  lea     r8, [rbp+840h+var_250]; unsigned __int16 *
0x1801393da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801393df  mov     [rsp+940h+var_910], eax
0x1801393e3  test    eax, eax
0x1801393e5  js      short loc_180139458
0x1801393e7  lea     rcx, [rdi+8B8h]; unsigned __int16 *
0x1801393ee  mov     rdx, r15; unsigned __int64
0x1801393f1  lea     r8, [rbp+840h+TempFileName]; unsigned __int16 *
0x1801393f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801393fd  mov     [rsp+940h+var_910], eax
0x180139401  test    eax, eax
0x180139403  js      short loc_180139458
0x180139405  lea     r8, [rbp+840h+pszMore]; pszMore
0x18013940c  mov     rdx, r15; cchPath
0x18013940f  lea     rcx, [rbp+840h+TempFileName]; pszPath
0x180139416  call    PathCchAppendEx
0x18013941b  mov     [rsp+940h+var_910], eax
0x18013941f  test    eax, eax
0x180139421  js      short loc_180139458
0x180139423  mov     rdx, [rsp+940h+ppwsz]; ppwsz
0x180139428  lea     rcx, [rbp+840h+TempFileName]; psz
0x18013942f  call    cs:__imp_SHStrDupW
0x180139436  nop     dword ptr [rax+rax+00h]
0x18013943b  mov     [rsp+940h+var_910], eax
0x18013943f  test    eax, eax
0x180139441  jnz     short loc_180139458
0x180139443  lea     rax, aCshdocvwbroker_7; "CShdocvwBroker::SaveAsComplete,CShdocvw"...
0x18013944a  mov     [r12], rax
0x18013944e  jmp     short loc_180139458
0x180139450  mov     [rsp+940h+var_910], 80004005h
0x180139458  lea     rcx, [rsp+940h+var_8E0]; this
0x18013945d  call    ??1CBrokerCallStateReset@@QEAA@XZ; CBrokerCallStateReset::~CBrokerCallStateReset(void)
0x180139462  mov     eax, [rsp+940h+var_910]
0x180139466  mov     rcx, [rbp+840h+var_40]
0x18013946d  xor     rcx, rsp; StackCookie
0x180139470  call    __security_check_cookie
0x180139475  mov     rbx, [rsp+940h+arg_18]
0x18013947d  add     rsp, 910h
0x180139484  pop     r15
0x180139486  pop     r14
0x180139488  pop     r13
0x18013948a  pop     r12
0x18013948c  pop     rdi
0x18013948d  pop     rsi
0x18013948e  pop     rbp
0x18013948f  retn
```
