# CFtpFolder::_IsProxyBlockingSite(_ITEMIDLIST const *)

- ea: `0x180018b4c`
- end: `0x180018d20`
- name: `?_IsProxyBlockingSite@CFtpFolder@@IEAAHPEFBU_ITEMIDLIST@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018dc0`

## callees

- `0x180002240`
- `0x18000cfcc`
- `0x18001168c`
- `0x180016b9c`
- `0x180018b4c`
- `0x18001cdb8`
- `0x18001d6bc`
- `0x180022bb0`
- `0x180022dc0`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180018c6f`
- `SHLWAPI!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180018c6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018cb0`
- `WININET!InternetCloseHandle` at `0x180018ccd`
- `WININET!InternetCloseHandle` at `0x180018cd8`
- `WININET!InternetCloseHandle` at `0x180018ccd`
- `WININET!InternetCloseHandle` at `0x180018cd8`
- `WININET!InternetOpenUrlW` at `0x180018ca2`
- `WININET!InternetOpenUrlW` at `0x180018ca2`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_IsProxyBlockingSite(CFtpFolder *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v5; // ebx
  CFtpDir *FtpDirFromPidl; // rax
  CFtpDir *v7; // rsi
  int v8; // eax
  int v9; // edx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r9
  BOOL BoolValueFromHKCUHKLM; // eax
  void *v15; // rbp
  signed int LastError; // eax
  bool v17; // sf
  unsigned int dwFlags; // [rsp+20h] [rbp-10A8h]
  HINTERNET hInternet[2]; // [rsp+40h] [rbp-1088h] BYREF
  WCHAR szUrl[2088]; // [rsp+50h] [rbp-1078h] BYREF

  LODWORD(hInternet[0]) = 0;
  if ( (unsigned int)ProxyCache_IsProxyBlocking(a2, (int *)hInternet) )
    return LODWORD(hInternet[0]);
  v5 = 1;
  FtpDirFromPidl = CFtpFolder::GetFtpDirFromPidl(this, a2);
  v7 = FtpDirFromPidl;
  if ( FtpDirFromPidl )
  {
    v8 = CFtpDir::WithHint(FtpDirFromPidl, 0, 0, 0, 0, 0, this);
    if ( (unsigned int)(v8 + 2147012889) <= 0x18 && (v9 = 20971521, _bittest(&v9, v8 + 2147012889))
      || v8 == -2147012894 && !(unsigned int)FtpPidl_IsDNSServerName(a2) )
    {
      if ( (int)UrlCreateFromPidl(a2, 0x8000u, szUrl, 0x824u, 0xC0000000, 0) >= 0 )
      {
        hInternet[0] = 0;
        if ( (int)InternetOpenWrap(v11, v10, v12, v13, dwFlags, hInternet) >= 0 )
        {
          BoolValueFromHKCUHKLM = SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Ftp", L"Use PASV");
          v15 = InternetOpenUrlW(hInternet[0], szUrl, 0, 0, BoolValueFromHKCUHKLM ? 134218240 : 512, 0);
          if ( v15 )
            goto LABEL_15;
          LastError = GetLastError();
          v17 = LastError < 0;
          if ( LastError > 0 )
            v17 = 1;
          if ( !v17 )
LABEL_15:
            InternetCloseHandle(v15);
          else
            v5 = 0;
          InternetCloseHandle(hInternet[0]);
        }
      }
    }
    else
    {
      v5 = 0;
    }
    ProxyCache_SetProxyBlocking(a2, v5);
    (*(void (__fastcall **)(CFtpDir *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180018b4c  mov     [rsp+arg_10], rbx
0x180018b51  push    rbp
0x180018b52  push    rsi
0x180018b53  push    rdi
0x180018b54  mov     eax, 10B0h
0x180018b59  call    _alloca_probe
0x180018b5e  sub     rsp, rax
0x180018b61  mov     rax, cs:__security_cookie
0x180018b68  xor     rax, rsp
0x180018b6b  mov     [rsp+10C8h+var_28], rax
0x180018b73  mov     rdi, rdx
0x180018b76  mov     dword ptr [rsp+10C8h+hInternet], 0
0x180018b7e  mov     rbp, rcx
0x180018b81  lea     rdx, [rsp+10C8h+hInternet]; int *
0x180018b86  mov     rcx, rdi; struct _ITEMIDLIST *
0x180018b89  call    ?ProxyCache_IsProxyBlocking@@YAHPEFBU_ITEMIDLIST@@PEAH@Z; ProxyCache_IsProxyBlocking(_ITEMIDLIST const *,int *)
0x180018b8e  test    eax, eax
0x180018b90  jz      short loc_180018B9B
0x180018b92  mov     eax, dword ptr [rsp+10C8h+hInternet]
0x180018b96  jmp     loc_180018CFD
0x180018b9b  mov     rdx, rdi; struct _ITEMIDLIST *
0x180018b9e  mov     rcx, rbp; this
0x180018ba1  mov     ebx, 1
0x180018ba6  call    ?GetFtpDirFromPidl@CFtpFolder@@QEAAPEAVCFtpDir@@PEFBU_ITEMIDLIST@@@Z; CFtpFolder::GetFtpDirFromPidl(_ITEMIDLIST const *)
0x180018bab  mov     rsi, rax
0x180018bae  test    rax, rax
0x180018bb1  jz      loc_180018CFB
0x180018bb7  mov     [rsp+10C8h+var_1098], rbp; struct CFtpFolder *
0x180018bbc  xor     r9d, r9d; int (*)(void *, struct HINTPROCINFO *, void *, int *)
0x180018bbf  mov     [rsp+10C8h+dwContext], 0; struct IUnknown *
0x180018bc8  xor     r8d, r8d; HWND
0x180018bcb  xor     edx, edx; struct CStatusBar *
0x180018bcd  mov     qword ptr [rsp+10C8h+dwFlags], 0; void *
0x180018bd6  mov     rcx, rax; this
0x180018bd9  call    ?WithHint@CFtpDir@@QEAAJPEAVCStatusBar@@PEAUHWND__@@P6AJPEAXPEAUHINTPROCINFO@@2PEAH@ZPEBXPEAUIUnknown@@PEAVCFtpFolder@@@Z; CFtpDir::WithHint(CStatusBar *,HWND__ *,long (*)(void *,HINTPROCINFO *,void *,int *),void const *,IUnknown *,CFtpFolder *)
0x180018bde  lea     ecx, [rax+7FF8D119h]
0x180018be4  cmp     ecx, 18h
0x180018be7  ja      short loc_180018BF3
0x180018be9  mov     edx, 1400001h
0x180018bee  bt      edx, ecx
0x180018bf1  jb      short loc_180018C0E
0x180018bf3  cmp     eax, 80072EE2h
0x180018bf8  jnz     loc_180018CE0
0x180018bfe  mov     rcx, rdi; struct _ITEMIDLIST *
0x180018c01  call    ?FtpPidl_IsDNSServerName@@YAHPEFBU_ITEMIDLIST@@@Z; FtpPidl_IsDNSServerName(_ITEMIDLIST const *)
0x180018c06  test    eax, eax
0x180018c08  jnz     loc_180018CE0
0x180018c0e  mov     dword ptr [rsp+10C8h+dwContext], 0; int
0x180018c16  lea     r8, [rsp+10C8h+szUrl]; unsigned __int16 *
0x180018c1b  mov     r9d, 824h; unsigned int
0x180018c21  mov     [rsp+10C8h+dwFlags], 0C0000000h; unsigned int
0x180018c29  mov     edx, 8000h; unsigned int
0x180018c2e  mov     rcx, rdi; struct _ITEMIDLIST *
0x180018c31  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x180018c36  test    eax, eax
0x180018c38  js      loc_180018CE2
0x180018c3e  lea     rax, [rsp+10C8h+hInternet]
0x180018c43  mov     [rsp+10C8h+hInternet], 0
0x180018c4c  mov     [rsp+10C8h+dwContext], rax; void **
0x180018c51  call    ?InternetOpenWrap@@YAJPEBGK00KPEAPEAX@Z; InternetOpenWrap(ushort const *,ulong,ushort const *,ushort const *,ulong,void * *)
0x180018c56  test    eax, eax
0x180018c58  js      loc_180018CE2
0x180018c5e  mov     r8d, ebx
0x180018c61  lea     rdx, aUsePasv; "Use PASV"
0x180018c68  lea     rcx, pszPrefix; "Software\\Microsoft\\Ftp"
0x180018c6f  call    cs:__imp_SHRegGetBoolValueFromHKCUHKLM
0x180018c75  mov     [rsp+10C8h+dwContext], 0; dwContext
0x180018c7e  lea     rdx, [rsp+10C8h+szUrl]; lpszUrl
0x180018c83  neg     eax
0x180018c85  sbb     ecx, ecx
0x180018c87  xor     r9d, r9d; dwHeadersLength
0x180018c8a  and     ecx, 8000000h
0x180018c90  xor     r8d, r8d; lpszHeaders
0x180018c93  add     ecx, 200h
0x180018c99  mov     [rsp+10C8h+dwFlags], ecx; dwFlags
0x180018c9d  mov     rcx, [rsp+10C8h+hInternet]; hInternet
0x180018ca2  call    cs:__imp_InternetOpenUrlW
0x180018ca8  mov     rbp, rax
0x180018cab  test    rax, rax
0x180018cae  jnz     short loc_180018CCA
0x180018cb0  call    cs:__imp_GetLastError
0x180018cb6  test    eax, eax
0x180018cb8  jle     short loc_180018CC4
0x180018cba  movzx   eax, ax
0x180018cbd  or      eax, 80070000h
0x180018cc2  test    eax, eax
0x180018cc4  jns     short loc_180018CCA
0x180018cc6  xor     ebx, ebx
0x180018cc8  jmp     short loc_180018CD3
0x180018cca  mov     rcx, rbp; hInternet
0x180018ccd  call    cs:__imp_InternetCloseHandle
0x180018cd3  mov     rcx, [rsp+10C8h+hInternet]; hInternet
0x180018cd8  call    cs:__imp_InternetCloseHandle
0x180018cde  jmp     short loc_180018CE2
0x180018ce0  xor     ebx, ebx
0x180018ce2  mov     edx, ebx; int
0x180018ce4  mov     rcx, rdi; struct _ITEMIDLIST *
0x180018ce7  call    ?ProxyCache_SetProxyBlocking@@YAXPEFBU_ITEMIDLIST@@H@Z; ProxyCache_SetProxyBlocking(_ITEMIDLIST const *,int)
0x180018cec  mov     rcx, [rsi]
0x180018cef  mov     rax, [rcx+10h]
0x180018cf3  mov     rcx, rsi
0x180018cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cfb  mov     eax, ebx
0x180018cfd  mov     rcx, [rsp+10C8h+var_28]
0x180018d05  xor     rcx, rsp; StackCookie
0x180018d08  call    __security_check_cookie
0x180018d0d  mov     rbx, [rsp+10C8h+arg_10]
0x180018d15  add     rsp, 10B0h
0x180018d1c  pop     rdi
0x180018d1d  pop     rsi
0x180018d1e  pop     rbp
0x180018d1f  retn
```
