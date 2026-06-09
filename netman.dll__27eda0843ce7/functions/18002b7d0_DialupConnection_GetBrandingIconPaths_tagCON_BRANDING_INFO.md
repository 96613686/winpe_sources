# DialupConnection::GetBrandingIconPaths(tagCON_BRANDING_INFO * *)

- ea: `0x18002b7d0`
- end: `0x18002bc12`
- name: `?GetBrandingIconPaths@DialupConnection@@UEAAJPEAPEAUtagCON_BRANDING_INFO@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(DialupConnection *__hidden this, struct tagCON_BRANDING_INFO **)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x1800084fc`
- `0x18002ac94`
- `0x18002b7a0`
- `0x18002b7d0`
- `0x18002c4e8`
- `0x18002cedc`
- `0x18002cf50`
- `0x18002cf80`
- `0x18002d2e4`
- `0x18002d69c`
- `0x1800304e8`
- `0x180030514`
- `0x180032c3c`
- `0x180034d90`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002ba95`
- `KERNEL32!FreeLibrary` at `0x18002ba95`
- `KERNEL32!LoadLibraryExW` at `0x18002b9a5`
- `KERNEL32!LoadLibraryExW` at `0x18002b9a5`
- `KERNEL32!EnterCriticalSection` at `0x18002b818`
- `KERNEL32!EnterCriticalSection` at `0x18002b818`
- `KERNEL32!GetProcAddress` at `0x18002b9dd`
- `KERNEL32!GetProcAddress` at `0x18002b9dd`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002b8eb`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002baec`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002b8eb`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002baec`
- `USER32!DestroyIcon` at `0x18002ba6d`
- `USER32!DestroyIcon` at `0x18002bb6e`
- `USER32!DestroyIcon` at `0x18002ba6d`
- `USER32!DestroyIcon` at `0x18002bb6e`
- `USER32!LoadImageW` at `0x18002ba5f`
- `USER32!LoadImageW` at `0x18002bb60`
- `USER32!LoadImageW` at `0x18002ba5f`
- `USER32!LoadImageW` at `0x18002bb60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bba1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bba1`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002b98b`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x18002b98b`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18002b922`
- `RASAPI32!RasGetEntryPropertiesW` at `0x18002b922`
- `rasman!RasIsTrustedCustomDll` at `0x18002b95c`
- `rasman!RasIsTrustedCustomDll` at `0x18002b95c`

## string_xrefs

- `0x18002b8e1`: `CustomRasDialDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DialupConnection::GetBrandingIconPaths(DialupConnection *this, unsigned __int16 ***a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v4; // edi
  unsigned __int16 **v5; // rsi
  const WCHAR *lpFileName; // rbx
  const WCHAR *v7; // rax
  const WCHAR *v8; // rbx
  const WCHAR *v9; // rax
  __int64 v10; // rax
  HMODULE Library; // r13
  BOOL v12; // r12d
  const unsigned __int16 *v13; // rbx
  const unsigned __int16 *v14; // rax
  HICON ImageW; // rax
  const WCHAR *v16; // rax
  __int64 v17; // rcx
  const unsigned __int16 *v18; // r8
  unsigned __int64 v19; // rdx
  HICON v20; // rax
  FARPROC ProcAddress; // [rsp+30h] [rbp-D0h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR *v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v28[4]; // [rsp+60h] [rbp-A0h] BYREF
  tagRASENTRYW v29; // [rsp+70h] [rbp-90h] BYREF
  WCHAR name[264]; // [rsp+1AC0h] [rbp+19C0h] BYREF
  WCHAR v31[264]; // [rsp+1CD0h] [rbp+1BD0h] BYREF
  WCHAR Dest[264]; // [rsp+1EE0h] [rbp+1DE0h] BYREF
  WCHAR ReturnedString[264]; // [rsp+20F0h] [rbp+1FF0h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 296);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  v24 = v3;
  v4 = RasConnectionBase::HrEnsureEntryPropertiesCached((DialupConnection *)((char *)this + 80));
  pv = 0;
  if ( v4 >= 0 )
  {
    if ( !(unsigned int)RasConnectionBase::FIsBranded((DialupConnection *)((char *)this + 80)) )
    {
      v4 = -2147467263;
      goto LABEL_31;
    }
    v4 = HrCoTaskMemAlloc(0x10u, &pv);
    v5 = (unsigned __int16 **)pv;
    if ( v4 >= 0 )
    {
      *(_OWORD *)pv = 0;
      memset_0(Dest, 0, 0x20Au);
      v26 = 0;
      memset_0(&v29.dwfOptions, 0, 0x1A40u);
      v28[0] = 6724;
      v29.dwSize = 6724;
      lpFileName = RasConnectionBase::PszwPbkFile((DialupConnection *)((char *)this + 80));
      v7 = RasConnectionBase::PszwEntryName((DialupConnection *)((char *)this + 80));
      if ( !GetPrivateProfileStringW(v7, L"CustomRasDialDll", &Default, v29.szCustomDialDll, 0x103u, lpFileName) )
      {
        v8 = RasConnectionBase::PszwEntryName((DialupConnection *)((char *)this + 80));
        v9 = RasConnectionBase::PszwPbkFile((DialupConnection *)((char *)this + 80));
        if ( RasGetEntryPropertiesW(v9, v8, &v29, v28, 0, 0) )
          goto LABEL_19;
      }
      v10 = -1;
      do
        ++v10;
      while ( v29.szCustomDialDll[v10] );
      if ( !v10 )
        goto LABEL_19;
      if ( (unsigned int)RasIsTrustedCustomDll(0, v29.szCustomDialDll, &v26) )
        goto LABEL_19;
      if ( !v26 )
        goto LABEL_19;
      if ( !ExpandEnvironmentStringsForUserW(0, v29.szCustomDialDll, Dest, 0x104u) )
        goto LABEL_19;
      Library = LoadLibraryExW(Dest, 0, 0);
      if ( !Library )
        goto LABEL_19;
      v12 = 1;
      memset_0(name, 0, 0x208u);
      ProcAddress = GetProcAddress(Library, "GetCustomProperty");
      if ( ProcAddress )
      {
        v25 = name;
        LODWORD(pv) = 520;
        v13 = RasConnectionBase::PszwEntryName((DialupConnection *)((char *)this + 80));
        v14 = RasConnectionBase::PszwPbkFile((DialupConnection *)((char *)this + 80));
        if ( ((unsigned int (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, const WCHAR *, WCHAR **, LPVOID *))ProcAddress)(
               v14,
               v13,
               L"Icon",
               &v25,
               &pv) )
        {
          ImageW = (HICON)LoadImageW(0, name, 1u, 32, 32, 0x10u);
          if ( ImageW )
          {
            DestroyIcon(ImageW);
            v4 = HrCoTaskMemAllocAndDupSz(name, v5, 0x104u);
            v12 = v4 < 0;
          }
        }
      }
      FreeLibrary(Library);
      if ( v12 )
      {
LABEL_19:
        v4 = DialupConnection::HrEnsureCmStringsLoaded((DialupConnection *)((char *)this - 24));
        if ( v4 < 0 )
          goto LABEL_29;
        v16 = DialupConnection::PszwCmsFile((DialupConnection *)((char *)this - 24));
        if ( !GetPrivateProfileStringW(L"Connection Manager", L"Icon", &Default, ReturnedString, 0x105u, v16) )
          goto LABEL_28;
        if ( !*((_QWORD *)this + 56) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v17);
        v18 = (const unsigned __int16 *)((char *)this + 432);
        if ( *((_QWORD *)this + 57) > 7u )
          v18 = *(const unsigned __int16 **)v18;
        StringCbCopyW(v31, 0x20Au, v18);
        StringCbCatW(v31, v19, ReturnedString);
        v20 = (HICON)LoadImageW(0, v31, 1u, 32, 32, 0x10u);
        if ( !v20 )
          goto LABEL_28;
        DestroyIcon(v20);
        v4 = HrCoTaskMemAllocAndDupSz(v31, v5, 0x104u);
      }
      if ( v4 >= 0 )
      {
LABEL_28:
        *a2 = v5;
        goto LABEL_34;
      }
    }
LABEL_29:
    if ( v5 )
      CoTaskMemFree(v5);
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
      (unsigned int)v4);
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v24);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002b7d0  mov     [rsp-8+arg_10], rbx
0x18002b7d5  push    rbp
0x18002b7d6  push    rsi
0x18002b7d7  push    rdi
0x18002b7d8  push    r12
0x18002b7da  push    r13
0x18002b7dc  push    r14
0x18002b7de  push    r15
0x18002b7e0  lea     rbp, [rsp-2210h]
0x18002b7e8  mov     eax, 2310h
0x18002b7ed  call    _alloca_probe
0x18002b7f2  sub     rsp, rax
0x18002b7f5  mov     rax, cs:__security_cookie
0x18002b7fc  xor     rax, rsp
0x18002b7ff  mov     [rbp+2240h+var_40], rax
0x18002b806  mov     [rsp+2340h+var_2308], rdx
0x18002b80b  mov     r14, rcx
0x18002b80e  lea     rbx, [rcx+128h]
0x18002b815  mov     rcx, rbx; lpCriticalSection
0x18002b818  call    cs:__imp_EnterCriticalSection
0x18002b81e  mov     [rsp+2340h+var_2300], rbx
0x18002b823  lea     r15, [r14+50h]
0x18002b827  mov     rcx, r15; this
0x18002b82a  call    ?HrEnsureEntryPropertiesCached@RasConnectionBase@@IEAAJXZ; RasConnectionBase::HrEnsureEntryPropertiesCached(void)
0x18002b82f  mov     edi, eax
0x18002b831  xor     r12d, r12d
0x18002b834  mov     [rsp+2340h+pv], r12
0x18002b839  test    eax, eax
0x18002b83b  js      loc_18002BBAB
0x18002b841  mov     rcx, r15; this
0x18002b844  call    ?FIsBranded@RasConnectionBase@@IEBAHXZ; RasConnectionBase::FIsBranded(void)
0x18002b849  test    eax, eax
0x18002b84b  jnz     short loc_18002B857
0x18002b84d  mov     edi, 80004001h
0x18002b852  jmp     loc_18002BBAB
0x18002b857  lea     rdx, [rsp+2340h+pv]; void **
0x18002b85c  mov     ecx, 10h; cb
0x18002b861  call    ?HrCoTaskMemAlloc@@YAJKPEAPEAX@Z; HrCoTaskMemAlloc(ulong,void * *)
0x18002b866  mov     edi, eax
0x18002b868  mov     rsi, [rsp+2340h+pv]
0x18002b86d  test    eax, eax
0x18002b86f  js      loc_18002BB99
0x18002b875  xorps   xmm0, xmm0
0x18002b878  movups  xmmword ptr [rsi], xmm0
0x18002b87b  xor     edx, edx; Val
0x18002b87d  mov     r8d, 20Ah; Size
0x18002b883  lea     rcx, [rbp+2240h+Dest]; void *
0x18002b88a  call    memset_0
0x18002b88f  mov     [rsp+2340h+var_22F0], r12d
0x18002b894  xor     edx, edx; Val
0x18002b896  mov     r8d, 1A40h; Size
0x18002b89c  lea     rcx, [rsp+2340h+var_22D0.dwfOptions]; void *
0x18002b8a1  call    memset_0
0x18002b8a6  mov     eax, 1A44h
0x18002b8ab  mov     [rsp+2340h+var_22E0], eax
0x18002b8af  mov     [rsp+2340h+var_22D0.dwSize], eax
0x18002b8b3  mov     rcx, r15; this
0x18002b8b6  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b8bb  mov     rbx, rax
0x18002b8be  mov     rcx, r15; this
0x18002b8c1  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002b8c6  mov     [rsp+2340h+lpFileName], rbx; lpFileName
0x18002b8cb  mov     [rsp+2340h+nSize], 103h; nSize
0x18002b8d3  lea     r9, [rbp+2240h+var_22D0.szCustomDialDll]; lpReturnedString
0x18002b8da  lea     r8, Default; lpDefault
0x18002b8e1  lea     rdx, KeyName; "CustomRasDialDll"
0x18002b8e8  mov     rcx, rax; lpAppName
0x18002b8eb  call    cs:__imp_GetPrivateProfileStringW
0x18002b8f1  test    eax, eax
0x18002b8f3  jnz     short loc_18002B930
0x18002b8f5  mov     rcx, r15; this
0x18002b8f8  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002b8fd  mov     rbx, rax
0x18002b900  mov     rcx, r15; this
0x18002b903  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002b908  mov     [rsp+2340h+lpFileName], r12; LPDWORD
0x18002b90d  mov     qword ptr [rsp+2340h+nSize], r12; LPBYTE
0x18002b912  lea     r9, [rsp+2340h+var_22E0]; LPDWORD
0x18002b917  lea     r8, [rsp+2340h+var_22D0]; struct tagRASENTRYW *
0x18002b91c  mov     rdx, rbx; LPCWSTR
0x18002b91f  mov     rcx, rax; LPCWSTR
0x18002b922  call    cs:__imp_RasGetEntryPropertiesW
0x18002b928  test    eax, eax
0x18002b92a  jnz     loc_18002BAA7
0x18002b930  lea     rcx, [rbp+2240h+var_22D0.szCustomDialDll]
0x18002b937  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b93b  inc     rax
0x18002b93e  cmp     [rcx+rax*2], r12w
0x18002b943  jnz     short loc_18002B93B
0x18002b945  test    rax, rax
0x18002b948  jz      loc_18002BAA7
0x18002b94e  lea     r8, [rsp+2340h+var_22F0]
0x18002b953  lea     rdx, [rbp+2240h+var_22D0.szCustomDialDll]
0x18002b95a  xor     ecx, ecx
0x18002b95c  call    cs:__imp_RasIsTrustedCustomDll
0x18002b962  test    eax, eax
0x18002b964  jnz     loc_18002BAA7
0x18002b96a  cmp     [rsp+2340h+var_22F0], r12d
0x18002b96f  jz      loc_18002BAA7
0x18002b975  mov     r9d, 104h; dwSize
0x18002b97b  lea     r8, [rbp+2240h+Dest]; lpDest
0x18002b982  lea     rdx, [rbp+2240h+var_22D0.szCustomDialDll]; lpSrc
0x18002b989  xor     ecx, ecx; hToken
0x18002b98b  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18002b991  test    eax, eax
0x18002b993  jz      loc_18002BAA7
0x18002b999  xor     r8d, r8d; dwFlags
0x18002b99c  xor     edx, edx; hFile
0x18002b99e  lea     rcx, [rbp+2240h+Dest]; lpLibFileName
0x18002b9a5  call    cs:__imp_LoadLibraryExW
0x18002b9ab  mov     r13, rax
0x18002b9ae  test    rax, rax
0x18002b9b1  jz      loc_18002BAA7
0x18002b9b7  mov     ebx, 208h
0x18002b9bc  mov     r12d, 1
0x18002b9c2  mov     r8d, ebx; Size
0x18002b9c5  xor     edx, edx; Val
0x18002b9c7  lea     rcx, [rbp+2240h+name]; void *
0x18002b9ce  call    memset_0
0x18002b9d3  lea     rdx, aGetcustomprope; "GetCustomProperty"
0x18002b9da  mov     rcx, r13; hModule
0x18002b9dd  call    cs:__imp_GetProcAddress
0x18002b9e3  mov     [rsp+2340h+var_2310], rax
0x18002b9e8  test    rax, rax
0x18002b9eb  jz      loc_18002BA92
0x18002b9f1  lea     rax, [rbp+2240h+name]
0x18002b9f8  mov     [rsp+2340h+var_22F8], rax
0x18002b9fd  mov     dword ptr [rsp+2340h+pv], ebx
0x18002ba01  mov     rcx, r15; this
0x18002ba04  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002ba09  mov     rbx, rax
0x18002ba0c  mov     rcx, r15; this
0x18002ba0f  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002ba14  lea     rcx, [rsp+2340h+pv]
0x18002ba19  mov     qword ptr [rsp+2340h+nSize], rcx
0x18002ba1e  lea     r9, [rsp+2340h+var_22F8]
0x18002ba23  lea     r8, aIcon; "Icon"
0x18002ba2a  mov     rdx, rbx
0x18002ba2d  mov     rcx, rax
0x18002ba30  mov     rax, [rsp+2340h+var_2310]
0x18002ba35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba3a  test    eax, eax
0x18002ba3c  jz      short loc_18002BA92
0x18002ba3e  mov     dword ptr [rsp+2340h+lpFileName], 10h; fuLoad
0x18002ba46  mov     [rsp+2340h+nSize], 20h ; ' '; cy
0x18002ba4e  lea     r9d, [r12+1Fh]; cx
0x18002ba53  mov     r8d, r12d; type
0x18002ba56  lea     rdx, [rbp+2240h+name]; name
0x18002ba5d  xor     ecx, ecx; hInst
0x18002ba5f  call    cs:__imp_LoadImageW
0x18002ba65  test    rax, rax
0x18002ba68  jz      short loc_18002BA92
0x18002ba6a  mov     rcx, rax; hIcon
0x18002ba6d  call    cs:__imp_DestroyIcon
0x18002ba73  mov     r8d, 104h; unsigned int
0x18002ba79  mov     rdx, rsi; unsigned __int16 **
0x18002ba7c  lea     rcx, [rbp+2240h+name]; unsigned __int16 *
0x18002ba83  call    ?HrCoTaskMemAllocAndDupSz@@YAJPEBGPEAPEAGK@Z; HrCoTaskMemAllocAndDupSz(ushort const *,ushort * *,ulong)
0x18002ba88  mov     edi, eax
0x18002ba8a  xor     eax, eax
0x18002ba8c  test    edi, edi
0x18002ba8e  cmovns  r12d, eax
0x18002ba92  mov     rcx, r13; hLibModule
0x18002ba95  call    cs:__imp_FreeLibrary
0x18002ba9b  test    r12d, r12d
0x18002ba9e  jz      loc_18002BB8B
0x18002baa4  xor     r12d, r12d
0x18002baa7  lea     rcx, [r14-18h]; this
0x18002baab  call    ?HrEnsureCmStringsLoaded@DialupConnection@@AEAAJXZ; DialupConnection::HrEnsureCmStringsLoaded(void)
0x18002bab0  mov     edi, eax
0x18002bab2  test    eax, eax
0x18002bab4  js      loc_18002BB99
0x18002baba  lea     rcx, [r14-18h]; this
0x18002babe  call    ?PszwCmsFile@DialupConnection@@AEAAPEBGXZ; DialupConnection::PszwCmsFile(void)
0x18002bac3  mov     [rsp+2340h+lpFileName], rax; lpFileName
0x18002bac8  mov     [rsp+2340h+nSize], 105h; nSize
0x18002bad0  lea     r9, [rbp+2240h+ReturnedString]; lpReturnedString
0x18002bad7  lea     r8, Default; lpDefault
0x18002bade  lea     rdx, aIcon; "Icon"
0x18002bae5  lea     rcx, AppName; "Connection Manager"
0x18002baec  call    cs:__imp_GetPrivateProfileStringW
0x18002baf2  test    eax, eax
0x18002baf4  jz      loc_18002BB8F
0x18002bafa  cmp     [r14+1C0h], r12
0x18002bb01  jnz     short loc_18002BB08
0x18002bb03  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002bb08  lea     r8, [r14+1B0h]
0x18002bb0f  cmp     qword ptr [r8+18h], 7
0x18002bb14  jbe     short loc_18002BB19
0x18002bb16  mov     r8, [r8]; unsigned __int16 *
0x18002bb19  mov     edx, 20Ah; unsigned __int64
0x18002bb1e  lea     rcx, [rbp+2240h+var_670]; unsigned __int16 *
0x18002bb25  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bb2a  lea     r8, [rbp+2240h+ReturnedString]; unsigned __int16 *
0x18002bb31  lea     rcx, [rbp+2240h+var_670]; unsigned __int16 *
0x18002bb38  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002bb3d  mov     dword ptr [rsp+2340h+lpFileName], 10h; fuLoad
0x18002bb45  mov     [rsp+2340h+nSize], 20h ; ' '; cy
0x18002bb4d  mov     r9d, 20h ; ' '; cx
0x18002bb53  lea     r8d, [r9-1Fh]; type
0x18002bb57  lea     rdx, [rbp+2240h+var_670]; name
0x18002bb5e  xor     ecx, ecx; hInst
0x18002bb60  call    cs:__imp_LoadImageW
0x18002bb66  test    rax, rax
0x18002bb69  jz      short loc_18002BB8F
0x18002bb6b  mov     rcx, rax; hIcon
0x18002bb6e  call    cs:__imp_DestroyIcon
0x18002bb74  mov     r8d, 104h; unsigned int
0x18002bb7a  mov     rdx, rsi; unsigned __int16 **
0x18002bb7d  lea     rcx, [rbp+2240h+var_670]; unsigned __int16 *
0x18002bb84  call    ?HrCoTaskMemAllocAndDupSz@@YAJPEBGPEAPEAGK@Z; HrCoTaskMemAllocAndDupSz(ushort const *,ushort * *,ulong)
0x18002bb89  mov     edi, eax
0x18002bb8b  test    edi, edi
0x18002bb8d  js      short loc_18002BB99
0x18002bb8f  mov     rax, [rsp+2340h+var_2308]
0x18002bb94  mov     [rax], rsi
0x18002bb97  jmp     short loc_18002BBDC
0x18002bb99  test    rsi, rsi
0x18002bb9c  jz      short loc_18002BBA7
0x18002bb9e  mov     rcx, rsi; pv
0x18002bba1  call    cs:__imp_CoTaskMemFree
0x18002bba7  test    edi, edi
0x18002bba9  jns     short loc_18002BBDC
0x18002bbab  lea     rax, WPP_GLOBAL_Control
0x18002bbb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbb9  cmp     rcx, rax
0x18002bbbc  jz      short loc_18002BBDC
0x18002bbbe  test    byte ptr [rcx+1Ch], 1
0x18002bbc2  jz      short loc_18002BBDC
0x18002bbc4  mov     edx, 20h ; ' '
0x18002bbc9  mov     r9d, edi
0x18002bbcc  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002bbd3  mov     rcx, [rcx+10h]
0x18002bbd7  call    WPP_SF_d
0x18002bbdc  lea     rcx, [rsp+2340h+var_2300]
0x18002bbe1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002bbe6  mov     eax, edi
0x18002bbe8  mov     rcx, [rbp+2240h+var_40]
0x18002bbef  xor     rcx, rsp; StackCookie
0x18002bbf2  call    __security_check_cookie
0x18002bbf7  mov     rbx, [rsp+2340h+arg_10]
0x18002bbff  add     rsp, 2310h
0x18002bc06  pop     r15
0x18002bc08  pop     r14
0x18002bc0a  pop     r13
0x18002bc0c  pop     r12
0x18002bc0e  pop     rdi
0x18002bc0f  pop     rsi
0x18002bc10  pop     rbp
0x18002bc11  retn
```
