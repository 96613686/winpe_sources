# CBaseBrowser2::_CreateShortcutOnDesktop(IUnknown *,int)

- ea: `0x1801b8cd4`
- end: `0x1801b91b9`
- name: `?_CreateShortcutOnDesktop@CBaseBrowser2@@IEAAXPEAUIUnknown@@H@Z`
- size: `1253`
- prototype: `void __fastcall(CBaseBrowser2 *__hidden this, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002b300`

## callees

- `0x1800144d0`
- `0x18001546c`
- `0x180015644`
- `0x180024bc4`
- `0x1800cd150`
- `0x1800cd2a4`
- `0x1800cd638`
- `0x180100d8c`
- `0x180101460`
- `0x1801b7524`
- `0x1801b8cd4`
- `0x180266190`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801b8e11`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801b8f14`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801b8e11`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801b8f14`
- `USER32!EnableWindow` at `0x1801b9012`
- `USER32!EnableWindow` at `0x1801b907f`
- `USER32!EnableWindow` at `0x1801b9012`
- `USER32!EnableWindow` at `0x1801b907f`
- `USER32!GetAncestor` at `0x1801b8ff9`
- `USER32!GetAncestor` at `0x1801b8ff9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b9120`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b9131`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b9120`
- `OLEAUT32!__imp_SysFreeString` at `0x1801b9131`
- `OLEAUT32!__imp_SysStringLen` at `0x1801b8de4`
- `OLEAUT32!__imp_SysStringLen` at `0x1801b8de4`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1801b90c9`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1801b90c9`
- `SHELL32!__imp_ILFree` at `0x1801b9140`
- `SHELL32!__imp_ILFree` at `0x1801b9140`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801b8fad`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801b8fad`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801b90f8`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801b90f8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801b8d67`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801b8d67`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801b910f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801b910f`

## pseudocode

```c
void __fastcall CBaseBrowser2::_CreateShortcutOnDesktop(CBaseBrowser2 *this, struct IUnknown *a2, int a3)
{
  ITEMIDLIST *v6; // rdi
  WCHAR *FileNameW; // rax
  int v8; // edx
  struct _ITEMIDLIST_ABSOLUTE *v9; // rax
  const unsigned __int16 *v10; // r8
  struct _ITEMIDLIST_ABSOLUTE *v11; // rcx
  WCHAR *v12; // rax
  int v13; // eax
  HINSTANCE v14; // rcx
  int v15; // eax
  HWND v16; // r8
  HWND v17; // rbx
  int v18; // esi
  HWND Ancestor; // rax
  void *v20; // rcx
  void *ppvOut; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  HWND hwnd; // [rsp+40h] [rbp-C0h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  int (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v27; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v28; // [rsp+68h] [rbp-98h]
  WCHAR *v29; // [rsp+70h] [rbp-90h]
  __int16 *v30; // [rsp+78h] [rbp-88h]
  __m128i si128; // [rsp+80h] [rbp-80h]
  _BYTE v32[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v33[3]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v34; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v35; // [rsp+C0h] [rbp-40h]
  int v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  __int16 v38; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v39[526]; // [rsp+F2h] [rbp-Eh] BYREF
  WCHAR v40[264]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v41[528]; // [rsp+510h] [rbp+410h] BYREF
  WCHAR pszPath[2088]; // [rsp+720h] [rbp+620h] BYREF

  memset_0(&v27, 0, 0x48u);
  v6 = 0;
  ppvOut = 0;
  v26 = 0;
  v22 = 0;
  pbstr = 0;
  bstrString = 0;
  if ( a2 )
  {
    if ( IUnknown_QueryService(a2, &IID_IHlinkFrame, &GUID_eab22ac1_30c1_11cf_a7eb_0000c05bae0b, &ppvOut) < 0
      || ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_332c4425_26cb_11d0_b483_00c04fd90119,
           &v22) < 0
      || (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 320LL))(v22, &bstrString) < 0
      || (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 136LL))(v22, &pbstr) < 0 )
    {
      goto LABEL_40;
    }
    if ( SysStringLen(pbstr) )
    {
      StringCchCopyW(pszPath, 0x824u, pbstr);
      FileNameW = pszPath;
    }
    else
    {
      StringCchCopyW(pszPath, 0x824u, bstrString);
      FileNameW = PathFindFileNameW(pszPath);
    }
    v28 = FileNameW;
    v9 = CBaseBrowser2::PidlFromUrl(bstrString, v8);
    v6 = (ITEMIDLIST *)v9;
    if ( !v9 )
      goto LABEL_40;
    v27 = v9;
  }
  else
  {
    if ( (*(int (__fastcall **)(char *, GUID *, GUID *, void **))(*((_QWORD *)this + 4) + 24LL))(
           (char *)this + 32,
           &IID_IHlinkFrame,
           &GUID_eab22ac1_30c1_11cf_a7eb_0000c05bae0b,
           &ppvOut) < 0
      || (*(int (__fastcall **)(void *, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)ppvOut + 144LL))(
           ppvOut,
           &v26) < 0
      || !v26
      || (**v26)(v26, &GUID_332c4425_26cb_11d0_b483_00c04fd90119, &v22) < 0 )
    {
      goto LABEL_40;
    }
    v10 = (const unsigned __int16 *)*((_QWORD *)this + 55);
    v11 = (struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)this + 51);
    v27 = v11;
    if ( v10 )
    {
      StringCchCopyW(pszPath, 0x824u, v10);
      v12 = pszPath;
    }
    else
    {
      IEGetNameAndFlagsEx((unsigned __int16 *)v11, 1u, 0, pszPath, 0x824u, 0);
      v12 = PathFindFileNameW(pszPath);
    }
    v28 = v12;
  }
  v38 = 0;
  memset_0(v39, 0, 0x206u);
  v30 = &v38;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( (**(int (__fastcall ***)(void *, GUID *, _BYTE *))ppvOut)(
         ppvOut,
         &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
         v32) >= 0 )
  {
    v33[0] = v22;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    hwnd = (HWND)*((_QWORD *)this + 43);
    if ( (int)SuppressDialog(&hwnd, 1u) >= 0 )
    {
      v13 = IsProtectedModeProcess();
      if ( v13 )
      {
        if ( v13 == 1 && (!a3 || !(unsigned int)ShowCreateShortcutOnDesktopDlg(v14, hwnd, v27)) )
        {
          if ( SHGetSpecialFolderPathW(0, v40, 16, 1) )
          {
            v29 = v40;
            if ( (int)CreateShortcutInDirEx(&v27) >= 0 )
            {
              if ( (unsigned int)IEConfiguration_GetDWORD(536870929) )
                EfsClientDecryptFile(v30, 0);
            }
          }
        }
      }
      else
      {
        v36 = 0;
        v37 = 0;
        v34 = 0;
        v35 = 0;
        v15 = CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(&v34);
        v16 = hwnd;
        v17 = 0;
        v18 = v15;
        if ( hwnd )
        {
          Ancestor = GetAncestor(hwnd, 2u);
          v17 = Ancestor;
          if ( Ancestor )
            EnableWindow(Ancestor, 0);
          v16 = hwnd;
        }
        if ( v18 >= 0
          && (*(int (__fastcall **)(_QWORD, struct _ITEMIDLIST_ABSOLUTE **, HWND, __int64))(**((_QWORD **)&v35 + 1)
                                                                                          + 520LL))(
               *((_QWORD *)&v35 + 1),
               &v27,
               v16,
               260) >= 0
          && (int)CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(
                    &v34,
                    0) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)&v35 + 1) + 528LL))(*((_QWORD *)&v35 + 1), v41);
        }
        if ( v17 )
          EnableWindow(v17, 1);
        CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(&v34);
      }
    }
  }
LABEL_40:
  SysFreeString(pbstr);
  SysFreeString(bstrString);
  ILFree(v6);
  IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(v33);
  IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(v32);
  v20 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
  }
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v26);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v22);
}

```

## disassembly

```asm
0x1801b8cd4  mov     [rsp-8+arg_10], rbx
0x1801b8cd9  mov     [rsp-8+arg_18], rsi
0x1801b8cde  push    rbp
0x1801b8cdf  push    rdi
0x1801b8ce0  push    r14
0x1801b8ce2  lea     rbp, [rsp-1680h]
0x1801b8cea  mov     eax, 1780h
0x1801b8cef  call    _alloca_probe
0x1801b8cf4  sub     rsp, rax
0x1801b8cf7  mov     rax, cs:__security_cookie
0x1801b8cfe  xor     rax, rsp
0x1801b8d01  mov     [rbp+1690h+var_20], rax
0x1801b8d08  mov     rbx, rdx
0x1801b8d0b  mov     r14d, r8d
0x1801b8d0e  xor     edx, edx; Val
0x1801b8d10  mov     rsi, rcx
0x1801b8d13  lea     rcx, [rsp+1790h+var_1730]; void *
0x1801b8d18  lea     r8d, [rdx+48h]; Size
0x1801b8d1c  call    memset_0
0x1801b8d21  xor     edi, edi
0x1801b8d23  mov     [rsp+1790h+ppvOut], 0
0x1801b8d2c  mov     [rsp+1790h+var_1738], 0
0x1801b8d35  lea     r9, [rsp+1790h+ppvOut]; ppvOut
0x1801b8d3a  mov     [rsp+1790h+var_1758], 0
0x1801b8d43  lea     r8, _GUID_eab22ac1_30c1_11cf_a7eb_0000c05bae0b; riid
0x1801b8d4a  mov     [rsp+1790h+pbstr], rdi
0x1801b8d4f  lea     rdx, IID_IHlinkFrame; guidService
0x1801b8d56  mov     [rsp+1790h+bstrString], rdi
0x1801b8d5b  test    rbx, rbx
0x1801b8d5e  jz      loc_1801B8E55
0x1801b8d64  mov     rcx, rbx; punk
0x1801b8d67  call    cs:__imp_IUnknown_QueryService
0x1801b8d6e  nop     dword ptr [rax+rax+00h]
0x1801b8d73  test    eax, eax
0x1801b8d75  js      loc_1801B911B
0x1801b8d7b  mov     rax, [rbx]
0x1801b8d7e  lea     r8, [rsp+1790h+var_1758]
0x1801b8d83  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801b8d8a  mov     rcx, rbx
0x1801b8d8d  mov     rax, [rax]
0x1801b8d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8d95  test    eax, eax
0x1801b8d97  js      loc_1801B911B
0x1801b8d9d  mov     rcx, [rsp+1790h+var_1758]
0x1801b8da2  lea     rdx, [rsp+1790h+bstrString]
0x1801b8da7  mov     rax, [rcx]
0x1801b8daa  mov     rax, [rax+140h]
0x1801b8db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8db6  test    eax, eax
0x1801b8db8  js      loc_1801B911B
0x1801b8dbe  mov     rcx, [rsp+1790h+var_1758]
0x1801b8dc3  lea     rdx, [rsp+1790h+pbstr]
0x1801b8dc8  mov     rax, [rcx]
0x1801b8dcb  mov     rax, [rax+88h]
0x1801b8dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8dd7  test    eax, eax
0x1801b8dd9  js      loc_1801B911B
0x1801b8ddf  mov     rcx, [rsp+1790h+pbstr]; pbstr
0x1801b8de4  call    cs:__imp_SysStringLen
0x1801b8deb  nop     dword ptr [rax+rax+00h]
0x1801b8df0  mov     edx, 824h; unsigned __int64
0x1801b8df5  lea     rcx, [rbp+1690h+pszPath]; unsigned __int16 *
0x1801b8dfc  test    eax, eax
0x1801b8dfe  jnz     short loc_1801B8E1F
0x1801b8e00  mov     r8, [rsp+1790h+bstrString]; unsigned __int16 *
0x1801b8e05  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b8e0a  lea     rcx, [rbp+1690h+pszPath]; pszPath
0x1801b8e11  call    cs:__imp_PathFindFileNameW
0x1801b8e18  nop     dword ptr [rax+rax+00h]
0x1801b8e1d  jmp     short loc_1801B8E30
0x1801b8e1f  mov     r8, [rsp+1790h+pbstr]; unsigned __int16 *
0x1801b8e24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b8e29  lea     rax, [rbp+1690h+pszPath]
0x1801b8e30  mov     rcx, [rsp+1790h+bstrString]; unsigned __int16 *
0x1801b8e35  mov     [rsp+1790h+var_1728], rax
0x1801b8e3a  call    ?PidlFromUrl@CBaseBrowser2@@SAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; CBaseBrowser2::PidlFromUrl(ushort const *,int)
0x1801b8e3f  mov     rdi, rax
0x1801b8e42  test    rax, rax
0x1801b8e45  jz      loc_1801B911B
0x1801b8e4b  mov     [rsp+1790h+var_1730], rax
0x1801b8e50  jmp     loc_1801B8F25
0x1801b8e55  lea     rcx, [rsi+20h]
0x1801b8e59  mov     rax, [rcx]
0x1801b8e5c  mov     rax, [rax+18h]
0x1801b8e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8e65  test    eax, eax
0x1801b8e67  js      loc_1801B911B
0x1801b8e6d  mov     rcx, [rsp+1790h+ppvOut]
0x1801b8e72  lea     rdx, [rsp+1790h+var_1738]
0x1801b8e77  mov     rax, [rcx]
0x1801b8e7a  mov     rax, [rax+90h]
0x1801b8e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8e86  test    eax, eax
0x1801b8e88  js      loc_1801B911B
0x1801b8e8e  mov     rcx, [rsp+1790h+var_1738]
0x1801b8e93  test    rcx, rcx
0x1801b8e96  jz      loc_1801B911B
0x1801b8e9c  mov     rax, [rcx]
0x1801b8e9f  lea     r8, [rsp+1790h+var_1758]
0x1801b8ea4  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801b8eab  mov     rax, [rax]
0x1801b8eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8eb3  test    eax, eax
0x1801b8eb5  js      loc_1801B911B
0x1801b8ebb  mov     r8, [rsi+1B8h]; unsigned __int16 *
0x1801b8ec2  mov     rcx, [rsi+198h]; int
0x1801b8ec9  mov     [rsp+1790h+var_1730], rcx
0x1801b8ece  test    r8, r8
0x1801b8ed1  jz      short loc_1801B8EED
0x1801b8ed3  mov     edx, 824h; unsigned __int64
0x1801b8ed8  lea     rcx, [rbp+1690h+pszPath]; unsigned __int16 *
0x1801b8edf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b8ee4  lea     rax, [rbp+1690h+pszPath]
0x1801b8eeb  jmp     short loc_1801B8F20
0x1801b8eed  xor     r8d, r8d; int
0x1801b8ef0  mov     [rsp+1790h+var_1768], rdi; __int64
0x1801b8ef5  lea     r9, [rbp+1690h+pszPath]; int
0x1801b8efc  mov     [rsp+1790h+cchBuf], 824h; cchBuf
0x1801b8f04  lea     edx, [r8+1]; int
0x1801b8f08  call    IEGetNameAndFlagsEx
0x1801b8f0d  lea     rcx, [rbp+1690h+pszPath]; pszPath
0x1801b8f14  call    cs:__imp_PathFindFileNameW
0x1801b8f1b  nop     dword ptr [rax+rax+00h]
0x1801b8f20  mov     [rsp+1790h+var_1728], rax
0x1801b8f25  xor     eax, eax
0x1801b8f27  lea     rcx, [rbp+1690h+var_169E]; void *
0x1801b8f2b  xor     edx, edx; Val
0x1801b8f2d  mov     [rbp+1690h+var_16A0], ax
0x1801b8f31  mov     r8d, 206h; Size
0x1801b8f37  call    memset_0
0x1801b8f3c  mov     rcx, [rsp+1790h+ppvOut]
0x1801b8f41  lea     rax, [rbp+1690h+var_16A0]
0x1801b8f45  movdqa  xmm0, cs:__xmm@00000001000000010000000000000104
0x1801b8f4d  lea     r8, [rbp+1690h+var_1700]
0x1801b8f51  mov     [rsp+1790h+var_1718], rax
0x1801b8f56  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x1801b8f5d  movdqa  [rbp+1690h+var_1710], xmm0
0x1801b8f62  mov     rax, [rcx]
0x1801b8f65  mov     rax, [rax]
0x1801b8f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8f6d  test    eax, eax
0x1801b8f6f  js      loc_1801B911B
0x1801b8f75  mov     rcx, [rsp+1790h+var_1758]
0x1801b8f7a  mov     [rbp+1690h+var_16F8], rcx
0x1801b8f7e  mov     rax, [rcx]
0x1801b8f81  mov     rax, [rax+8]
0x1801b8f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b8f8a  mov     rax, [rsi+158h]
0x1801b8f91  lea     rcx, [rsp+1790h+hwnd]; HWND *
0x1801b8f96  mov     edx, 1; unsigned int
0x1801b8f9b  mov     [rsp+1790h+hwnd], rax
0x1801b8fa0  call    ?SuppressDialog@@YAJPEAPEAUHWND__@@K@Z; SuppressDialog(HWND__ * *,ulong)
0x1801b8fa5  test    eax, eax
0x1801b8fa7  js      loc_1801B911B
0x1801b8fad  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801b8fb4  nop     dword ptr [rax+rax+00h]
0x1801b8fb9  test    eax, eax
0x1801b8fbb  jnz     loc_1801B9099
0x1801b8fc1  xorps   xmm0, xmm0
0x1801b8fc4  mov     [rbp+1690h+var_16C0], eax
0x1801b8fc7  xorps   xmm1, xmm1
0x1801b8fca  mov     [rbp+1690h+var_16B8], 0
0x1801b8fd2  lea     rcx, [rbp+1690h+var_16E0]
0x1801b8fd6  movdqu  [rbp+1690h+var_16E0], xmm0
0x1801b8fdb  movdqu  [rbp+1690h+var_16D0], xmm1
0x1801b8fe0  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1801b8fe5  mov     r8, [rsp+1790h+hwnd]
0x1801b8fea  xor     ebx, ebx
0x1801b8fec  mov     esi, eax
0x1801b8fee  test    r8, r8
0x1801b8ff1  jz      short loc_1801B9023
0x1801b8ff3  lea     edx, [rbx+2]; gaFlags
0x1801b8ff6  mov     rcx, r8; hwnd
0x1801b8ff9  call    cs:__imp_GetAncestor
0x1801b9000  nop     dword ptr [rax+rax+00h]
0x1801b9005  mov     rbx, rax
0x1801b9008  test    rax, rax
0x1801b900b  jz      short loc_1801B901E
0x1801b900d  xor     edx, edx; bEnable
0x1801b900f  mov     rcx, rax; hWnd
0x1801b9012  call    cs:__imp_EnableWindow
0x1801b9019  nop     dword ptr [rax+rax+00h]
0x1801b901e  mov     r8, [rsp+1790h+hwnd]
0x1801b9023  test    esi, esi
0x1801b9025  js      short loc_1801B9072
0x1801b9027  mov     rcx, qword ptr [rbp+1690h+var_16D0+8]
0x1801b902b  lea     rdx, [rsp+1790h+var_1730]
0x1801b9030  mov     r9d, 104h
0x1801b9036  mov     rax, [rcx]
0x1801b9039  mov     rax, [rax+208h]
0x1801b9040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9045  test    eax, eax
0x1801b9047  js      short loc_1801B9072
0x1801b9049  xor     edx, edx
0x1801b904b  lea     rcx, [rbp+1690h+var_16E0]
0x1801b904f  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1801b9054  test    eax, eax
0x1801b9056  js      short loc_1801B9072
0x1801b9058  mov     rcx, qword ptr [rbp+1690h+var_16D0+8]
0x1801b905c  lea     rdx, [rbp+1690h+var_1280]
0x1801b9063  mov     rax, [rcx]
0x1801b9066  mov     rax, [rax+210h]
0x1801b906d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b9072  test    rbx, rbx
0x1801b9075  jz      short loc_1801B908B
0x1801b9077  mov     edx, 1; bEnable
0x1801b907c  mov     rcx, rbx; hWnd
0x1801b907f  call    cs:__imp_EnableWindow
0x1801b9086  nop     dword ptr [rax+rax+00h]
0x1801b908b  lea     rcx, [rbp+1690h+var_16E0]
0x1801b908f  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x1801b9094  jmp     loc_1801B911B
0x1801b9099  cmp     eax, 1
0x1801b909c  jnz     short loc_1801B911B
0x1801b909e  test    r14d, r14d
0x1801b90a1  jz      short loc_1801B90B6
0x1801b90a3  mov     r8, [rsp+1790h+var_1730]; struct _ITEMIDLIST_ABSOLUTE *
0x1801b90a8  mov     rdx, [rsp+1790h+hwnd]; HWND
0x1801b90ad  call    ?ShowCreateShortcutOnDesktopDlg@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z; ShowCreateShortcutOnDesktopDlg(HINSTANCE__ *,HWND__ *,_ITEMIDLIST_ABSOLUTE const *)
0x1801b90b2  test    eax, eax
0x1801b90b4  jnz     short loc_1801B911B
0x1801b90b6  mov     r9d, 1; fCreate
0x1801b90bc  lea     rdx, [rbp+1690h+var_1490]; pszPath
0x1801b90c3  xor     ecx, ecx; hwnd
0x1801b90c5  lea     r8d, [r9+0Fh]; csidl
0x1801b90c9  call    cs:__imp_SHGetSpecialFolderPathW
0x1801b90d0  nop     dword ptr [rax+rax+00h]
0x1801b90d5  test    eax, eax
0x1801b90d7  jz      short loc_1801B911B
0x1801b90d9  lea     rax, [rbp+1690h+var_1490]
0x1801b90e0  lea     rcx, [rsp+1790h+var_1730]
0x1801b90e5  mov     [rsp+1790h+var_1720], rax
0x1801b90ea  call    CreateShortcutInDirEx
0x1801b90ef  test    eax, eax
0x1801b90f1  js      short loc_1801B911B
0x1801b90f3  mov     ecx, 20000011h
0x1801b90f8  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801b90ff  nop     dword ptr [rax+rax+00h]
0x1801b9104  test    eax, eax
0x1801b9106  jz      short loc_1801B911B
0x1801b9108  mov     rcx, [rsp+1790h+var_1718]
0x1801b910d  xor     edx, edx
0x1801b910f  call    cs:__imp_EfsClientDecryptFile
0x1801b9116  nop     dword ptr [rax+rax+00h]
0x1801b911b  mov     rcx, [rsp+1790h+pbstr]; bstrString
0x1801b9120  call    cs:__imp_SysFreeString
0x1801b9127  nop     dword ptr [rax+rax+00h]
0x1801b912c  mov     rcx, [rsp+1790h+bstrString]; bstrString
0x1801b9131  call    cs:__imp_SysFreeString
0x1801b9138  nop     dword ptr [rax+rax+00h]
0x1801b913d  mov     rcx, rdi; pidl
0x1801b9140  call    cs:__imp_ILFree
0x1801b9147  nop     dword ptr [rax+rax+00h]
0x1801b914c  lea     rcx, [rbp+1690h+var_16F8]
0x1801b9150  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x1801b9155  lea     rcx, [rbp+1690h+var_1700]
0x1801b9159  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x1801b915e  mov     rcx, [rsp+1790h+ppvOut]
0x1801b9163  test    rcx, rcx
0x1801b9166  jz      short loc_1801B917D
0x1801b9168  mov     [rsp+1790h+ppvOut], 0
0x1801b9171  mov     rax, [rcx]
0x1801b9174  mov     rax, [rax+10h]
0x1801b9178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b917d  lea     rcx, [rsp+1790h+var_1738]
0x1801b9182  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1801b9187  lea     rcx, [rsp+1790h+var_1758]
0x1801b918c  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1801b9191  mov     rcx, [rbp+1690h+var_20]
0x1801b9198  xor     rcx, rsp; StackCookie
0x1801b919b  call    __security_check_cookie
0x1801b91a0  lea     r11, [rsp+1790h+var_10]
0x1801b91a8  mov     rbx, [r11+30h]
0x1801b91ac  mov     rsi, [r11+38h]
0x1801b91b0  mov     rsp, r11
0x1801b91b3  pop     r14
0x1801b91b5  pop     rdi
0x1801b91b6  pop     rbp
0x1801b91b7  retn
```
