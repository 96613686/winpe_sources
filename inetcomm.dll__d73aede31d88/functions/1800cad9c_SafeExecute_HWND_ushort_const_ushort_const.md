# SafeExecute(HWND__ *,ushort const *,ushort const *)

- ea: `0x1800cad9c`
- end: `0x1800cafc0`
- name: `?SafeExecute@@YAJPEAUHWND__@@PEBG1@Z`
- size: `548`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180066748`
- `0x180081724`

## callees

- `0x180002098`
- `0x1800247c8`
- `0x1800c85d8`
- `0x1800cacb8`
- `0x1800cad9c`
- `0x1800cafc8`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cca90`
- `0x1800cd010`

## import_xrefs

- `SHLWAPI!UrlCanonicalizeW` at `0x1800cae01`
- `SHLWAPI!UrlCanonicalizeW` at `0x1800cae01`
- `SHLWAPI!UrlIsW` at `0x1800cae1d`
- `SHLWAPI!UrlIsW` at `0x1800cae1d`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800cae91`
- `SHLWAPI!PathCreateFromUrlW` at `0x1800cae91`
- `SHLWAPI!PathIsDirectoryW` at `0x1800caea5`
- `SHLWAPI!PathIsDirectoryW` at `0x1800caea5`
- `SHLWAPI!__imp_StrCmpNICW` at `0x1800cae39`
- `SHLWAPI!__imp_StrCmpNICW` at `0x1800cae39`
- `SHELL32!ShellExecuteExW` at `0x1800caf8b`
- `SHELL32!ShellExecuteExW` at `0x1800caf8b`

## pseudocode

```c
__int64 __fastcall SafeExecute(HWND a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HRESULT v6; // ebx
  BOOL IsW; // ebx
  void *v10; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchCanonicalized; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchPath; // [rsp+3Ch] [rbp-C4h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszCanonicalized[2088]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(pszCanonicalized, 0, 0x1048u);
  pcchCanonicalized = 2084;
  v6 = UrlCanonicalizeW(a3, pszCanonicalized, &pcchCanonicalized, 0);
  if ( v6 >= 0 )
  {
    IsW = UrlIsW(pszCanonicalized, URLIS_FILEURL);
    if ( !StrCmpNICW(L"mshelp://", pszCanonicalized, 9) )
      return (unsigned int)ShowHelp(pszCanonicalized);
    if ( IsW )
    {
      v10 = 0;
      memset_0(pszPath, 0, 0x208u);
      pcchPath = 260;
      v6 = PathCreateFromUrlW(pszCanonicalized, pszPath, &pcchPath, 0);
      if ( v6 >= 0 )
      {
        if ( PathIsDirectoryW(pszPath) )
        {
          v6 = SafeExecuteDirectory(pszPath);
        }
        else
        {
          v6 = CreateAttachmentServices(a2, &GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57, &v10);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(void *, WCHAR *))(*(_QWORD *)v10 + 40LL))(v10, pszPath);
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v10 + 72LL))(v10);
              if ( !v6 )
              {
                v6 = (*(__int64 (__fastcall **)(void *, HWND, const wchar_t *, _QWORD))(*(_QWORD *)v10 + 96LL))(
                       v10,
                       a1,
                       L"open",
                       0);
                if ( v6 >= 0 )
                  v6 = 0;
              }
            }
          }
        }
      }
      OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
    }
    else
    {
      pExecInfo.cbSize = 112;
      v6 = 0;
      *(_OWORD *)&pExecInfo.lpParameters = 0;
      pExecInfo.hwnd = 0;
      pExecInfo.lpVerb = 0;
      pExecInfo.lpFile = pszCanonicalized;
      memset(&pExecInfo.hInstApp, 0, 56);
      *(_QWORD *)&pExecInfo.nShow = 1;
      pExecInfo.fMask = 0x100000;
      if ( !ShellExecuteExW(&pExecInfo) )
        return (unsigned int)HrGetLastError();
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800cad9c  mov     [rsp-8+arg_18], rbx
0x1800cada1  push    rbp
0x1800cada2  push    rsi
0x1800cada3  push    rdi
0x1800cada4  lea     rbp, [rsp-1220h]
0x1800cadac  mov     eax, 1320h
0x1800cadb1  call    _alloca_probe
0x1800cadb6  sub     rsp, rax
0x1800cadb9  mov     rax, cs:__security_cookie
0x1800cadc0  xor     rax, rsp
0x1800cadc3  mov     [rbp+1230h+var_20], rax
0x1800cadca  mov     rbx, r8
0x1800cadcd  mov     rdi, rdx
0x1800cadd0  mov     rsi, rcx
0x1800cadd3  xor     edx, edx; Val
0x1800cadd5  mov     r8d, 1048h; Size
0x1800caddb  lea     rcx, [rbp+1230h+pszCanonicalized]; void *
0x1800cade2  call    memset_0
0x1800cade7  xor     r9d, r9d; dwFlags
0x1800cadea  mov     [rsp+1330h+pcchCanonicalized], 824h
0x1800cadf2  lea     r8, [rsp+1330h+pcchCanonicalized]; pcchCanonicalized
0x1800cadf7  mov     rcx, rbx; pszUrl
0x1800cadfa  lea     rdx, [rbp+1230h+pszCanonicalized]; pszCanonicalized
0x1800cae01  call    cs:__imp_UrlCanonicalizeW
0x1800cae07  mov     ebx, eax
0x1800cae09  test    eax, eax
0x1800cae0b  js      loc_1800CAF9C
0x1800cae11  mov     edx, 3; UrlIs
0x1800cae16  lea     rcx, [rbp+1230h+pszCanonicalized]; pszUrl
0x1800cae1d  call    cs:__imp_UrlIsW
0x1800cae23  mov     r8d, 9; nChar
0x1800cae29  lea     rdx, [rbp+1230h+pszCanonicalized]; pszStr2
0x1800cae30  lea     rcx, aMshelp; "mshelp://"
0x1800cae37  mov     ebx, eax
0x1800cae39  call    cs:__imp_StrCmpNICW
0x1800cae3f  test    eax, eax
0x1800cae41  jnz     short loc_1800CAE54
0x1800cae43  lea     rcx, [rbp+1230h+pszCanonicalized]
0x1800cae4a  call    ShowHelp
0x1800cae4f  jmp     loc_1800CAF9A
0x1800cae54  test    ebx, ebx
0x1800cae56  jz      loc_1800CAF3B
0x1800cae5c  xor     edx, edx; Val
0x1800cae5e  mov     [rsp+1330h+var_1300], 0
0x1800cae67  mov     r8d, 208h; Size
0x1800cae6d  lea     rcx, [rbp+1230h+pszPath]; void *
0x1800cae71  call    memset_0
0x1800cae76  xor     r9d, r9d; dwFlags
0x1800cae79  mov     [rsp+1330h+pcchPath], 104h
0x1800cae81  lea     r8, [rsp+1330h+pcchPath]; pcchPath
0x1800cae86  lea     rdx, [rbp+1230h+pszPath]; pszPath
0x1800cae8a  lea     rcx, [rbp+1230h+pszCanonicalized]; pszUrl
0x1800cae91  call    cs:__imp_PathCreateFromUrlW
0x1800cae97  mov     ebx, eax
0x1800cae99  test    eax, eax
0x1800cae9b  js      loc_1800CAF2F
0x1800caea1  lea     rcx, [rbp+1230h+pszPath]; pszPath
0x1800caea5  call    cs:__imp_PathIsDirectoryW
0x1800caeab  test    eax, eax
0x1800caead  jz      short loc_1800CAEBC
0x1800caeaf  lea     rcx, [rbp+1230h+pszPath]
0x1800caeb3  call    _SafeExecuteDirectory
0x1800caeb8  mov     ebx, eax
0x1800caeba  jmp     short loc_1800CAF2F
0x1800caebc  lea     r8, [rsp+1330h+var_1300]; void **
0x1800caec1  mov     rcx, rdi; unsigned __int16 *
0x1800caec4  lea     rdx, _GUID_73db1241_1e85_4581_8e4f_a81e1d0f8c57; struct _GUID *
0x1800caecb  call    ?CreateAttachmentServices@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateAttachmentServices(ushort const *,_GUID const &,void * *)
0x1800caed0  mov     ebx, eax
0x1800caed2  test    eax, eax
0x1800caed4  js      short loc_1800CAF2F
0x1800caed6  mov     rcx, [rsp+1330h+var_1300]
0x1800caedb  lea     rdx, [rbp+1230h+pszPath]
0x1800caedf  mov     rax, [rcx]
0x1800caee2  mov     rax, [rax+28h]
0x1800caee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caeeb  mov     ebx, eax
0x1800caeed  test    eax, eax
0x1800caeef  js      short loc_1800CAF2F
0x1800caef1  mov     rcx, [rsp+1330h+var_1300]
0x1800caef6  mov     rax, [rcx]
0x1800caef9  mov     rax, [rax+48h]
0x1800caefd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf02  mov     ebx, eax
0x1800caf04  test    eax, eax
0x1800caf06  jnz     short loc_1800CAF2F
0x1800caf08  mov     rcx, [rsp+1330h+var_1300]
0x1800caf0d  lea     r8, aOpen; "open"
0x1800caf14  xor     r9d, r9d
0x1800caf17  mov     rdx, rsi
0x1800caf1a  mov     rax, [rcx]
0x1800caf1d  mov     rax, [rax+60h]
0x1800caf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf26  mov     ebx, eax
0x1800caf28  xor     eax, eax
0x1800caf2a  test    ebx, ebx
0x1800caf2c  cmovns  ebx, eax
0x1800caf2f  lea     rcx, [rsp+1330h+var_1300]
0x1800caf34  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800caf39  jmp     short loc_1800CAF9C
0x1800caf3b  xorps   xmm0, xmm0
0x1800caf3e  mov     [rsp+1330h+pExecInfo.cbSize], 70h ; 'p'
0x1800caf46  xor     ebx, ebx
0x1800caf48  movdqa  xmmword ptr [rsp+1330h+pExecInfo.lpParameters], xmm0
0x1800caf4e  lea     rax, [rbp+1230h+pszCanonicalized]
0x1800caf55  mov     [rsp+1330h+pExecInfo.hwnd], rbx
0x1800caf5a  lea     rcx, [rsp+1330h+pExecInfo]; pExecInfo
0x1800caf5f  mov     [rsp+1330h+pExecInfo.lpVerb], rbx
0x1800caf64  mov     [rsp+1330h+pExecInfo.lpFile], rax
0x1800caf69  mov     [rsp+1330h+pExecInfo.hInstApp], rbx
0x1800caf6e  movups  xmmword ptr [rbp+1230h+pExecInfo.lpIDList], xmm0
0x1800caf72  mov     qword ptr [rsp+1330h+pExecInfo.nShow], 1
0x1800caf7b  movups  xmmword ptr [rbp+1230h+pExecInfo.hkeyClass], xmm0
0x1800caf7f  mov     [rsp+1330h+pExecInfo.fMask], 100000h
0x1800caf87  movups  xmmword ptr [rbp+1230h+pExecInfo.60h], xmm0
0x1800caf8b  call    cs:__imp_ShellExecuteExW
0x1800caf91  test    eax, eax
0x1800caf93  jnz     short loc_1800CAF9C
0x1800caf95  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800caf9a  mov     ebx, eax
0x1800caf9c  mov     eax, ebx
0x1800caf9e  mov     rcx, [rbp+1230h+var_20]
0x1800cafa5  xor     rcx, rsp; StackCookie
0x1800cafa8  call    __security_check_cookie
0x1800cafad  mov     rbx, [rsp+1330h+arg_18]
0x1800cafb5  add     rsp, 1320h
0x1800cafbc  pop     rdi
0x1800cafbd  pop     rsi
0x1800cafbe  pop     rbp
0x1800cafbf  retn
```
