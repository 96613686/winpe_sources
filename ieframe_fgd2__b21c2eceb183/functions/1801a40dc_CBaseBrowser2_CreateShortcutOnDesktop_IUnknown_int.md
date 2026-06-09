# CBaseBrowser2::_CreateShortcutOnDesktop(IUnknown *,int)

- ea: `0x1801a40dc`
- end: `0x1801a4569`
- name: `?_CreateShortcutOnDesktop@CBaseBrowser2@@IEAAXPEAUIUnknown@@H@Z`
- size: `1165`
- prototype: `void __fastcall(CBaseBrowser2 *__hidden this, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e8b0`

## callees

- `0x180011230`
- `0x180012140`
- `0x180012310`
- `0x18002320c`
- `0x1800c5d04`
- `0x1800c5df0`
- `0x1800c6168`
- `0x1800f60c4`
- `0x1800f6730`
- `0x1801a29a4`
- `0x1801a40dc`
- `0x180247ba0`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801a420d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801a430a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801a420d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1801a430a`
- `USER32!EnableWindow` at `0x1801a43f6`
- `USER32!EnableWindow` at `0x1801a445d`
- `USER32!EnableWindow` at `0x1801a43f6`
- `USER32!EnableWindow` at `0x1801a445d`
- `USER32!GetAncestor` at `0x1801a43e3`
- `USER32!GetAncestor` at `0x1801a43e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a44e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a44ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a44e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1801a44ee`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a41e6`
- `OLEAUT32!__imp_SysStringLen` at `0x1801a41e6`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1801a449e`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1801a449e`
- `SHELL32!__imp_ILFree` at `0x1801a44f7`
- `SHELL32!__imp_ILFree` at `0x1801a44f7`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801a439d`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1801a439d`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801a44c7`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1801a44c7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801a416f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801a416f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801a44d8`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x1801a44d8`

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
0x1801a40dc  mov     [rsp-8+arg_10], rbx
0x1801a40e1  mov     [rsp-8+arg_18], rsi
0x1801a40e6  push    rbp
0x1801a40e7  push    rdi
0x1801a40e8  push    r14
0x1801a40ea  lea     rbp, [rsp-1680h]
0x1801a40f2  mov     eax, 1780h
0x1801a40f7  call    _alloca_probe
0x1801a40fc  sub     rsp, rax
0x1801a40ff  mov     rax, cs:__security_cookie
0x1801a4106  xor     rax, rsp
0x1801a4109  mov     [rbp+1690h+var_20], rax
0x1801a4110  mov     rbx, rdx
0x1801a4113  mov     r14d, r8d
0x1801a4116  xor     edx, edx; Val
0x1801a4118  mov     rsi, rcx
0x1801a411b  lea     rcx, [rsp+1790h+var_1730]; void *
0x1801a4120  lea     r8d, [rdx+48h]; Size
0x1801a4124  call    memset_0
0x1801a4129  xor     edi, edi
0x1801a412b  mov     [rsp+1790h+ppvOut], 0
0x1801a4134  mov     [rsp+1790h+var_1738], 0
0x1801a413d  lea     r9, [rsp+1790h+ppvOut]; ppvOut
0x1801a4142  mov     [rsp+1790h+var_1758], 0
0x1801a414b  lea     r8, _GUID_eab22ac1_30c1_11cf_a7eb_0000c05bae0b; riid
0x1801a4152  mov     [rsp+1790h+pbstr], rdi
0x1801a4157  lea     rdx, IID_IHlinkFrame; guidService
0x1801a415e  mov     [rsp+1790h+bstrString], rdi
0x1801a4163  test    rbx, rbx
0x1801a4166  jz      loc_1801A424B
0x1801a416c  mov     rcx, rbx; punk
0x1801a416f  call    cs:__imp_IUnknown_QueryService
0x1801a4175  test    eax, eax
0x1801a4177  js      loc_1801A44DE
0x1801a417d  mov     rax, [rbx]
0x1801a4180  lea     r8, [rsp+1790h+var_1758]
0x1801a4185  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801a418c  mov     rcx, rbx
0x1801a418f  mov     rax, [rax]
0x1801a4192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4197  test    eax, eax
0x1801a4199  js      loc_1801A44DE
0x1801a419f  mov     rcx, [rsp+1790h+var_1758]
0x1801a41a4  lea     rdx, [rsp+1790h+bstrString]
0x1801a41a9  mov     rax, [rcx]
0x1801a41ac  mov     rax, [rax+140h]
0x1801a41b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a41b8  test    eax, eax
0x1801a41ba  js      loc_1801A44DE
0x1801a41c0  mov     rcx, [rsp+1790h+var_1758]
0x1801a41c5  lea     rdx, [rsp+1790h+pbstr]
0x1801a41ca  mov     rax, [rcx]
0x1801a41cd  mov     rax, [rax+88h]
0x1801a41d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a41d9  test    eax, eax
0x1801a41db  js      loc_1801A44DE
0x1801a41e1  mov     rcx, [rsp+1790h+pbstr]; pbstr
0x1801a41e6  call    cs:__imp_SysStringLen
0x1801a41ec  mov     edx, 824h; unsigned __int64
0x1801a41f1  lea     rcx, [rbp+1690h+pszPath]; unsigned __int16 *
0x1801a41f8  test    eax, eax
0x1801a41fa  jnz     short loc_1801A4215
0x1801a41fc  mov     r8, [rsp+1790h+bstrString]; unsigned __int16 *
0x1801a4201  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801a4206  lea     rcx, [rbp+1690h+pszPath]; pszPath
0x1801a420d  call    cs:__imp_PathFindFileNameW
0x1801a4213  jmp     short loc_1801A4226
0x1801a4215  mov     r8, [rsp+1790h+pbstr]; unsigned __int16 *
0x1801a421a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801a421f  lea     rax, [rbp+1690h+pszPath]
0x1801a4226  mov     rcx, [rsp+1790h+bstrString]; unsigned __int16 *
0x1801a422b  mov     [rsp+1790h+var_1728], rax
0x1801a4230  call    ?PidlFromUrl@CBaseBrowser2@@SAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; CBaseBrowser2::PidlFromUrl(ushort const *,int)
0x1801a4235  mov     rdi, rax
0x1801a4238  test    rax, rax
0x1801a423b  jz      loc_1801A44DE
0x1801a4241  mov     [rsp+1790h+var_1730], rax
0x1801a4246  jmp     loc_1801A4315
0x1801a424b  lea     rcx, [rsi+20h]
0x1801a424f  mov     rax, [rcx]
0x1801a4252  mov     rax, [rax+18h]
0x1801a4256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a425b  test    eax, eax
0x1801a425d  js      loc_1801A44DE
0x1801a4263  mov     rcx, [rsp+1790h+ppvOut]
0x1801a4268  lea     rdx, [rsp+1790h+var_1738]
0x1801a426d  mov     rax, [rcx]
0x1801a4270  mov     rax, [rax+90h]
0x1801a4277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a427c  test    eax, eax
0x1801a427e  js      loc_1801A44DE
0x1801a4284  mov     rcx, [rsp+1790h+var_1738]
0x1801a4289  test    rcx, rcx
0x1801a428c  jz      loc_1801A44DE
0x1801a4292  mov     rax, [rcx]
0x1801a4295  lea     r8, [rsp+1790h+var_1758]
0x1801a429a  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801a42a1  mov     rax, [rax]
0x1801a42a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a42a9  test    eax, eax
0x1801a42ab  js      loc_1801A44DE
0x1801a42b1  mov     r8, [rsi+1B8h]; unsigned __int16 *
0x1801a42b8  mov     rcx, [rsi+198h]; int
0x1801a42bf  mov     [rsp+1790h+var_1730], rcx
0x1801a42c4  test    r8, r8
0x1801a42c7  jz      short loc_1801A42E3
0x1801a42c9  mov     edx, 824h; unsigned __int64
0x1801a42ce  lea     rcx, [rbp+1690h+pszPath]; unsigned __int16 *
0x1801a42d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801a42da  lea     rax, [rbp+1690h+pszPath]
0x1801a42e1  jmp     short loc_1801A4310
0x1801a42e3  xor     r8d, r8d; int
0x1801a42e6  mov     [rsp+1790h+var_1768], rdi; __int64
0x1801a42eb  lea     r9, [rbp+1690h+pszPath]; int
0x1801a42f2  mov     [rsp+1790h+cchBuf], 824h; cchBuf
0x1801a42fa  lea     edx, [r8+1]; int
0x1801a42fe  call    IEGetNameAndFlagsEx
0x1801a4303  lea     rcx, [rbp+1690h+pszPath]; pszPath
0x1801a430a  call    cs:__imp_PathFindFileNameW
0x1801a4310  mov     [rsp+1790h+var_1728], rax
0x1801a4315  xor     eax, eax
0x1801a4317  lea     rcx, [rbp+1690h+var_169E]; void *
0x1801a431b  xor     edx, edx; Val
0x1801a431d  mov     [rbp+1690h+var_16A0], ax
0x1801a4321  mov     r8d, 206h; Size
0x1801a4327  call    memset_0
0x1801a432c  mov     rcx, [rsp+1790h+ppvOut]
0x1801a4331  lea     rax, [rbp+1690h+var_16A0]
0x1801a4335  movdqa  xmm0, cs:__xmm@00000001000000010000000000000104
0x1801a433d  lea     r8, [rbp+1690h+var_1700]
0x1801a4341  mov     [rsp+1790h+var_1718], rax
0x1801a4346  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x1801a434d  movdqa  [rbp+1690h+var_1710], xmm0
0x1801a4352  mov     rax, [rcx]
0x1801a4355  mov     rax, [rax]
0x1801a4358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a435d  test    eax, eax
0x1801a435f  js      loc_1801A44DE
0x1801a4365  mov     rcx, [rsp+1790h+var_1758]
0x1801a436a  mov     [rbp+1690h+var_16F8], rcx
0x1801a436e  mov     rax, [rcx]
0x1801a4371  mov     rax, [rax+8]
0x1801a4375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a437a  mov     rax, [rsi+158h]
0x1801a4381  lea     rcx, [rsp+1790h+hwnd]; HWND *
0x1801a4386  mov     edx, 1; unsigned int
0x1801a438b  mov     [rsp+1790h+hwnd], rax
0x1801a4390  call    ?SuppressDialog@@YAJPEAPEAUHWND__@@K@Z; SuppressDialog(HWND__ * *,ulong)
0x1801a4395  test    eax, eax
0x1801a4397  js      loc_1801A44DE
0x1801a439d  call    cs:__imp_?IsProtectedModeProcess@@YAJXZ; IsProtectedModeProcess(void)
0x1801a43a3  test    eax, eax
0x1801a43a5  jnz     loc_1801A446E
0x1801a43ab  xorps   xmm0, xmm0
0x1801a43ae  mov     [rbp+1690h+var_16C0], eax
0x1801a43b1  xorps   xmm1, xmm1
0x1801a43b4  mov     [rbp+1690h+var_16B8], 0
0x1801a43bc  lea     rcx, [rbp+1690h+var_16E0]
0x1801a43c0  movdqu  [rbp+1690h+var_16E0], xmm0
0x1801a43c5  movdqu  [rbp+1690h+var_16D0], xmm1
0x1801a43ca  call    ?Init@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJXZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::Init(void)
0x1801a43cf  mov     r8, [rsp+1790h+hwnd]
0x1801a43d4  xor     ebx, ebx
0x1801a43d6  mov     esi, eax
0x1801a43d8  test    r8, r8
0x1801a43db  jz      short loc_1801A4401
0x1801a43dd  lea     edx, [rbx+2]; gaFlags
0x1801a43e0  mov     rcx, r8; hwnd
0x1801a43e3  call    cs:__imp_GetAncestor
0x1801a43e9  mov     rbx, rax
0x1801a43ec  test    rax, rax
0x1801a43ef  jz      short loc_1801A43FC
0x1801a43f1  xor     edx, edx; bEnable
0x1801a43f3  mov     rcx, rax; hWnd
0x1801a43f6  call    cs:__imp_EnableWindow
0x1801a43fc  mov     r8, [rsp+1790h+hwnd]
0x1801a4401  test    esi, esi
0x1801a4403  js      short loc_1801A4450
0x1801a4405  mov     rcx, qword ptr [rbp+1690h+var_16D0+8]
0x1801a4409  lea     rdx, [rsp+1790h+var_1730]
0x1801a440e  mov     r9d, 104h
0x1801a4414  mov     rax, [rcx]
0x1801a4417  mov     rax, [rax+208h]
0x1801a441e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4423  test    eax, eax
0x1801a4425  js      short loc_1801A4450
0x1801a4427  xor     edx, edx
0x1801a4429  lea     rcx, [rbp+1690h+var_16E0]
0x1801a442d  call    ?WaitForCallComplete@?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBroker@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAAJPEAUHWND__@@I@Z; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBroker,&_GUID const IID_AsyncIShdocvwBroker>::WaitForCallComplete(HWND__ *,uint)
0x1801a4432  test    eax, eax
0x1801a4434  js      short loc_1801A4450
0x1801a4436  mov     rcx, qword ptr [rbp+1690h+var_16D0+8]
0x1801a443a  lea     rdx, [rbp+1690h+var_1280]
0x1801a4441  mov     rax, [rcx]
0x1801a4444  mov     rax, [rax+210h]
0x1801a444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a4450  test    rbx, rbx
0x1801a4453  jz      short loc_1801A4463
0x1801a4455  mov     edx, 1; bEnable
0x1801a445a  mov     rcx, rbx; hWnd
0x1801a445d  call    cs:__imp_EnableWindow
0x1801a4463  lea     rcx, [rbp+1690h+var_16E0]
0x1801a4467  call    ??1?$CBrokerObjectCall@UAsyncIShdocvwBroker@@$1?CLSID_CShdocvwBrokerNoFrameAffinity@@3U_GUID@@B$1?IID_AsyncIShdocvwBroker@@3U3@B@@QEAA@XZ; CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>::~CBrokerObjectCall<AsyncIShdocvwBroker,&_GUID const CLSID_CShdocvwBrokerNoFrameAffinity,&_GUID const IID_AsyncIShdocvwBroker>(void)
0x1801a446c  jmp     short loc_1801A44DE
0x1801a446e  cmp     eax, 1
0x1801a4471  jnz     short loc_1801A44DE
0x1801a4473  test    r14d, r14d
0x1801a4476  jz      short loc_1801A448B
0x1801a4478  mov     r8, [rsp+1790h+var_1730]; struct _ITEMIDLIST_ABSOLUTE *
0x1801a447d  mov     rdx, [rsp+1790h+hwnd]; HWND
0x1801a4482  call    ?ShowCreateShortcutOnDesktopDlg@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@@Z; ShowCreateShortcutOnDesktopDlg(HINSTANCE__ *,HWND__ *,_ITEMIDLIST_ABSOLUTE const *)
0x1801a4487  test    eax, eax
0x1801a4489  jnz     short loc_1801A44DE
0x1801a448b  mov     r9d, 1; fCreate
0x1801a4491  lea     rdx, [rbp+1690h+var_1490]; pszPath
0x1801a4498  xor     ecx, ecx; hwnd
0x1801a449a  lea     r8d, [r9+0Fh]; csidl
0x1801a449e  call    cs:__imp_SHGetSpecialFolderPathW
0x1801a44a4  test    eax, eax
0x1801a44a6  jz      short loc_1801A44DE
0x1801a44a8  lea     rax, [rbp+1690h+var_1490]
0x1801a44af  lea     rcx, [rsp+1790h+var_1730]
0x1801a44b4  mov     [rsp+1790h+var_1720], rax
0x1801a44b9  call    CreateShortcutInDirEx
0x1801a44be  test    eax, eax
0x1801a44c0  js      short loc_1801A44DE
0x1801a44c2  mov     ecx, 20000011h
0x1801a44c7  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1801a44cd  test    eax, eax
0x1801a44cf  jz      short loc_1801A44DE
0x1801a44d1  mov     rcx, [rsp+1790h+var_1718]
0x1801a44d6  xor     edx, edx
0x1801a44d8  call    cs:__imp_EfsClientDecryptFile
0x1801a44de  mov     rcx, [rsp+1790h+pbstr]; bstrString
0x1801a44e3  call    cs:__imp_SysFreeString
0x1801a44e9  mov     rcx, [rsp+1790h+bstrString]; bstrString
0x1801a44ee  call    cs:__imp_SysFreeString
0x1801a44f4  mov     rcx, rdi; pidl
0x1801a44f7  call    cs:__imp_ILFree
0x1801a44fd  lea     rcx, [rbp+1690h+var_16F8]
0x1801a4501  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x1801a4506  lea     rcx, [rbp+1690h+var_1700]
0x1801a450a  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x1801a450f  mov     rcx, [rsp+1790h+ppvOut]
0x1801a4514  test    rcx, rcx
0x1801a4517  jz      short loc_1801A452E
0x1801a4519  mov     [rsp+1790h+ppvOut], 0
0x1801a4522  mov     rax, [rcx]
0x1801a4525  mov     rax, [rax+10h]
0x1801a4529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a452e  lea     rcx, [rsp+1790h+var_1738]
0x1801a4533  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1801a4538  lea     rcx, [rsp+1790h+var_1758]
0x1801a453d  call    ?Release@?$CComPtr@UIPrivacIEDatabase@@@ATL@@QEAAXXZ; ATL::CComPtr<IPrivacIEDatabase>::Release(void)
0x1801a4542  mov     rcx, [rbp+1690h+var_20]
0x1801a4549  xor     rcx, rsp; StackCookie
0x1801a454c  call    __security_check_cookie
0x1801a4551  lea     r11, [rsp+1790h+var_10]
0x1801a4559  mov     rbx, [r11+30h]
0x1801a455d  mov     rsi, [r11+38h]
0x1801a4561  mov     rsp, r11
0x1801a4564  pop     r14
0x1801a4566  pop     rdi
0x1801a4567  pop     rbp
0x1801a4568  retn
```
