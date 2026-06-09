# _GetShareStateFromSite(IUnknown *,IShellItemArray *,SHARING_MENU_SHARE_STATE *,SHARING_MENU_PRESENTATION_STATE *,SHARE_MODE *,int *)

- ea: `0x1800509c8`
- end: `0x180050d89`
- name: `?_GetShareStateFromSite@@YAJPEAUIUnknown@@PEAUIShellItemArray@@PEAW4SHARING_MENU_SHARE_STATE@@PEAW4SHARING_MENU_PRESENTATION_STATE@@PEAW4SHARE_MODE@@PEAH@Z`
- size: `961`
- prototype: `__int64 __usercall@<rax>(struct IUnknown *@<rcx>, struct IShellItemArray *@<rdx>, enum SHARING_MENU_SHARE_STATE *@<r8>, enum SHARING_MENU_PRESENTATION_STATE *@<r9>, enum SHARE_MODE *, int *)`
- caller_count: `8`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180013c80`
- `0x18003e780`
- `0x180044090`
- `0x180045a20`
- `0x180045a80`
- `0x180046520`
- `0x180046710`
- `0x1800487f0`

## callees

- `0x180012340`
- `0x1800139a4`
- `0x18001b8c0`
- `0x18001c084`
- `0x18001c4a8`
- `0x1800254e0`
- `0x1800509c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050b28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050bd2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050b28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050cf6`
- `SHCORE!IUnknown_QueryService` at `0x180050a46`
- `SHCORE!IUnknown_QueryService` at `0x180050a46`
- `SHELL32!SHGetFolderPathEx` at `0x180050c94`
- `SHELL32!SHGetFolderPathEx` at `0x180050c94`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180050cc3`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180050cc3`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050b93`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050baa`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050c15`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050b93`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050baa`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x180050c15`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x180050ab2`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x180050ab2`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a61`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a7c`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a97`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a61`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a7c`
- `PROPSYS!PSPropertyBag_ReadDWORD` at `0x180050a97`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x180050ceb`
- `PROPSYS!PSPropertyBag_WriteBOOL` at `0x180050ceb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _GetShareStateFromSite(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        enum SHARING_MENU_SHARE_STATE *a3,
        enum SHARING_MENU_PRESENTATION_STATE *a4,
        enum SHARE_MODE *a5,
        int *a6)
{
  HRESULT ImpliedSelection; // ebx
  unsigned int v11; // edx
  BOOL v12; // edi
  void *ppvOut; // [rsp+30h] [rbp-D0h] BYREF
  DWORD value; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v16; // [rsp+3Ch] [rbp-C4h] BYREF
  DWORD v17; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v18; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID v19; // [rsp+48h] [rbp-B8h] BYREF
  struct IShellItemArray *v20; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  struct IShellItemArray *v24[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[528]; // [rsp+80h] [rbp-80h] BYREF

  value = 0;
  v16 = 0;
  v17 = 3;
  v18 = 0;
  ppvOut = 0;
  if ( !a1
    || IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_CommandsPropertyBag,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) < 0
    || PSPropertyBag_ReadDWORD((IPropertyBag *)ppvOut, L"WindowsShareState", &value) < 0
    || PSPropertyBag_ReadDWORD((IPropertyBag *)ppvOut, L"WindowsSharePresentationState", &v16) < 0
    || PSPropertyBag_ReadDWORD((IPropertyBag *)ppvOut, L"WindowsShareMode", &v17) < 0
    || (ImpliedSelection = PSPropertyBag_ReadBOOL((IPropertyBag *)ppvOut, L"WindowsShareIsUnderPublicState", &v18),
        ImpliedSelection < 0) )
  {
    v20 = 0;
    v24[0] = 0;
    ImpliedSelection = _GetImpliedSelection(a2, a1, v24);
    if ( ImpliedSelection >= 0 )
    {
      ImpliedSelection = _TruncateShellItemArray(v24[0], v11, &v20);
      if ( ImpliedSelection >= 0 )
      {
        ppv = 0;
        v12 = 1;
        ImpliedSelection = CoCreateInstance(
                             &CLSID_SharingConfigurationManager,
                             0,
                             1u,
                             &GUID_1861a62c_d24c_480c_8200_ccde25fd58bb,
                             &ppv);
        if ( ImpliedSelection >= 0 )
        {
          ImpliedSelection = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *, DWORD *))(*(_QWORD *)ppv + 32LL))(
                               ppv,
                               v20,
                               &value);
          if ( ImpliedSelection >= 0 )
          {
            ImpliedSelection = (*(__int64 (__fastcall **)(LPVOID, DWORD *))(*(_QWORD *)ppv + 24LL))(ppv, &v16);
            if ( ImpliedSelection >= 0 )
            {
              if ( ppvOut )
              {
                PSPropertyBag_WriteDWORD((IPropertyBag *)ppvOut, L"WindowsShareState", value);
                PSPropertyBag_WriteDWORD((IPropertyBag *)ppvOut, L"WindowsSharePresentationState", v16);
              }
              v19 = 0;
              ImpliedSelection = CoCreateInstance(
                                   &CLSID_SharingConfigurationManager,
                                   0,
                                   1u,
                                   &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2,
                                   &v19);
              if ( ImpliedSelection >= 0 )
              {
                ImpliedSelection = (*(__int64 (__fastcall **)(LPVOID, struct IShellItemArray *, DWORD *))(*(_QWORD *)v19 + 88LL))(
                                     v19,
                                     v20,
                                     &v17);
                if ( ImpliedSelection >= 0 )
                {
                  if ( ppvOut )
                    PSPropertyBag_WriteDWORD((IPropertyBag *)ppvOut, L"WindowsShareMode", v17);
                }
              }
              ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v19);
              if ( ImpliedSelection >= 0 )
              {
                LODWORD(v19) = 0;
                ImpliedSelection = IShellItemArray_GetEstimatedCount(v20, (unsigned int *)&v19);
                if ( ImpliedSelection >= 0 )
                {
                  if ( (_DWORD)v19 )
                  {
                    v23 = 0;
                    ImpliedSelection = ((__int64 (__fastcall *)(struct IShellItemArray *, _QWORD, __int64 *))v20->lpVtbl->GetItemAt)(
                                         v20,
                                         0,
                                         &v23);
                    if ( ImpliedSelection >= 0 )
                    {
                      ImpliedSelection = SHGetFolderPathEx(&FOLDERID_Public, 0, 0, v25, 260);
                      if ( ImpliedSelection >= 0 )
                      {
                        pv = 0;
                        ImpliedSelection = GetLocalPathForItemIfPossible(v23, &pv);
                        if ( ImpliedSelection >= 0 )
                        {
                          if ( (unsigned int)PathIsEqualOrSubFolder(v25, pv) )
                            v18 = 1;
                          else
                            v12 = v18;
                          if ( ppvOut )
                            PSPropertyBag_WriteBOOL((IPropertyBag *)ppvOut, L"WindowsShareIsUnderPublicState", v12);
                          CoTaskMemFree(pv);
                        }
                      }
                    }
                    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v23);
                  }
                }
              }
            }
          }
        }
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppv);
      }
    }
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(v24);
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v20);
  }
  if ( a3 )
    *(_DWORD *)a3 = value;
  if ( a4 )
    *(_DWORD *)a4 = v16;
  if ( a5 )
    *(_DWORD *)a5 = v17;
  if ( a6 )
    *a6 = v18;
  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppvOut);
  return (unsigned int)ImpliedSelection;
}

```

## disassembly

```asm
0x1800509c8  push    rbp
0x1800509ca  push    rbx
0x1800509cb  push    rsi
0x1800509cc  push    rdi
0x1800509cd  push    r12
0x1800509cf  push    r13
0x1800509d1  push    r14
0x1800509d3  push    r15
0x1800509d5  lea     rbp, [rsp-1A8h]
0x1800509dd  sub     rsp, 2A8h
0x1800509e4  mov     rax, cs:__security_cookie
0x1800509eb  xor     rax, rsp
0x1800509ee  mov     [rbp+1E0h+var_50], rax
0x1800509f5  mov     r12, r9
0x1800509f8  mov     r13, r8
0x1800509fb  mov     rsi, rdx
0x1800509fe  mov     rdi, rcx
0x180050a01  mov     r15, [rbp+1E0h+arg_20]
0x180050a08  mov     r14, [rbp+1E0h+arg_28]
0x180050a0f  xor     ebx, ebx
0x180050a11  mov     [rsp+2E0h+value], ebx
0x180050a15  mov     [rsp+2E0h+var_2A4], ebx
0x180050a19  mov     [rsp+2E0h+var_2A0], 3
0x180050a21  mov     [rsp+2E0h+var_29C], ebx
0x180050a25  mov     [rsp+2E0h+ppvOut], rbx
0x180050a2a  test    rcx, rcx
0x180050a2d  jz      loc_180050AC4
0x180050a33  lea     r9, [rsp+2E0h+ppvOut]; ppvOut
0x180050a38  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180050a3f  lea     rdx, SID_CommandsPropertyBag; guidService
0x180050a46  call    cs:__imp_IUnknown_QueryService
0x180050a4c  test    eax, eax
0x180050a4e  js      short loc_180050AC4
0x180050a50  lea     r8, [rsp+2E0h+value]; value
0x180050a55  lea     rdx, aWindowssharest; "WindowsShareState"
0x180050a5c  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050a61  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180050a67  test    eax, eax
0x180050a69  js      short loc_180050AC4
0x180050a6b  lea     r8, [rsp+2E0h+var_2A4]; value
0x180050a70  lea     rdx, aWindowssharepr; "WindowsSharePresentationState"
0x180050a77  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050a7c  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180050a82  test    eax, eax
0x180050a84  js      short loc_180050AC4
0x180050a86  lea     r8, [rsp+2E0h+var_2A0]; value
0x180050a8b  lea     rdx, aWindowssharemo; "WindowsShareMode"
0x180050a92  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050a97  call    cs:__imp_PSPropertyBag_ReadDWORD
0x180050a9d  test    eax, eax
0x180050a9f  js      short loc_180050AC4
0x180050aa1  lea     r8, [rsp+2E0h+var_29C]; value
0x180050aa6  lea     rdx, aWindowsshareis; "WindowsShareIsUnderPublicState"
0x180050aad  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050ab2  call    cs:__imp_PSPropertyBag_ReadBOOL
0x180050ab8  mov     ebx, eax
0x180050aba  test    eax, eax
0x180050abc  jns     loc_180050D28
0x180050ac2  xor     ebx, ebx
0x180050ac4  mov     [rsp+2E0h+var_290], rbx
0x180050ac9  mov     [rsp+2E0h+var_270], rbx
0x180050ace  lea     r8, [rsp+2E0h+var_270]; struct IShellItemArray **
0x180050ad3  mov     rdx, rdi; struct IUnknown *
0x180050ad6  mov     rcx, rsi; struct IShellItemArray *
0x180050ad9  call    ?_GetImpliedSelection@@YAJPEAUIShellItemArray@@PEAUIUnknown@@PEAPEAU1@@Z; _GetImpliedSelection(IShellItemArray *,IUnknown *,IShellItemArray * *)
0x180050ade  mov     ebx, eax
0x180050ae0  xor     esi, esi
0x180050ae2  test    eax, eax
0x180050ae4  js      loc_180050D13
0x180050aea  lea     r8, [rsp+2E0h+var_290]; struct IShellItemArray **
0x180050aef  mov     rcx, [rsp+2E0h+var_270]; struct IShellItemArray *
0x180050af4  call    ?_TruncateShellItemArray@@YAJPEAUIShellItemArray@@KPEAPEAU1@@Z; _TruncateShellItemArray(IShellItemArray *,ulong,IShellItemArray * *)
0x180050af9  mov     ebx, eax
0x180050afb  test    eax, eax
0x180050afd  js      loc_180050D13
0x180050b03  mov     [rsp+2E0h+var_288], rsi
0x180050b08  lea     rax, [rsp+2E0h+var_288]
0x180050b0d  mov     [rsp+2E0h+ppv], rax; ppv
0x180050b12  lea     r9, _GUID_1861a62c_d24c_480c_8200_ccde25fd58bb; riid
0x180050b19  lea     edi, [rsi+1]
0x180050b1c  mov     r8d, edi; dwClsContext
0x180050b1f  xor     edx, edx; pUnkOuter
0x180050b21  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180050b28  call    cs:__imp_CoCreateInstance
0x180050b2e  mov     ebx, eax
0x180050b30  test    eax, eax
0x180050b32  js      loc_180050D08
0x180050b38  mov     rcx, [rsp+2E0h+var_288]
0x180050b3d  mov     rax, [rcx]
0x180050b40  lea     r8, [rsp+2E0h+value]
0x180050b45  mov     rdx, [rsp+2E0h+var_290]
0x180050b4a  mov     rax, [rax+20h]
0x180050b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b53  mov     ebx, eax
0x180050b55  test    eax, eax
0x180050b57  js      loc_180050D08
0x180050b5d  mov     rcx, [rsp+2E0h+var_288]
0x180050b62  mov     rax, [rcx]
0x180050b65  lea     rdx, [rsp+2E0h+var_2A4]
0x180050b6a  mov     rax, [rax+18h]
0x180050b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b73  mov     ebx, eax
0x180050b75  test    eax, eax
0x180050b77  js      loc_180050D08
0x180050b7d  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050b82  test    rcx, rcx
0x180050b85  jz      short loc_180050BB0
0x180050b87  mov     r8d, [rsp+2E0h+value]; value
0x180050b8c  lea     rdx, aWindowssharest; "WindowsShareState"
0x180050b93  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180050b99  mov     r8d, [rsp+2E0h+var_2A4]; value
0x180050b9e  lea     rdx, aWindowssharepr; "WindowsSharePresentationState"
0x180050ba5  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050baa  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180050bb0  mov     [rsp+2E0h+var_298], rsi
0x180050bb5  lea     rax, [rsp+2E0h+var_298]
0x180050bba  mov     [rsp+2E0h+ppv], rax; ppv
0x180050bbf  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x180050bc6  mov     r8d, edi; dwClsContext
0x180050bc9  xor     edx, edx; pUnkOuter
0x180050bcb  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180050bd2  call    cs:__imp_CoCreateInstance
0x180050bd8  mov     ebx, eax
0x180050bda  test    eax, eax
0x180050bdc  js      short loc_180050C1C
0x180050bde  mov     rcx, [rsp+2E0h+var_298]
0x180050be3  mov     rax, [rcx]
0x180050be6  lea     r8, [rsp+2E0h+var_2A0]
0x180050beb  mov     rdx, [rsp+2E0h+var_290]
0x180050bf0  mov     rax, [rax+58h]
0x180050bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bf9  mov     ebx, eax
0x180050bfb  test    eax, eax
0x180050bfd  js      short loc_180050C1C
0x180050bff  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050c04  test    rcx, rcx
0x180050c07  jz      short loc_180050C1C
0x180050c09  mov     r8d, [rsp+2E0h+var_2A0]; value
0x180050c0e  lea     rdx, aWindowssharemo; "WindowsShareMode"
0x180050c15  call    cs:__imp_PSPropertyBag_WriteDWORD
0x180050c1b  nop
0x180050c1c  lea     rcx, [rsp+2E0h+var_298]
0x180050c21  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050c26  test    ebx, ebx
0x180050c28  js      loc_180050D08
0x180050c2e  mov     dword ptr [rsp+2E0h+var_298], esi
0x180050c32  lea     rdx, [rsp+2E0h+var_298]; unsigned int *
0x180050c37  mov     rcx, [rsp+2E0h+var_290]; struct IShellItemArray *
0x180050c3c  call    ?IShellItemArray_GetEstimatedCount@@YAJPEAUIShellItemArray@@PEAK@Z; IShellItemArray_GetEstimatedCount(IShellItemArray *,ulong *)
0x180050c41  mov     ebx, eax
0x180050c43  test    eax, eax
0x180050c45  js      loc_180050D08
0x180050c4b  cmp     dword ptr [rsp+2E0h+var_298], esi
0x180050c4f  jbe     loc_180050D08
0x180050c55  mov     [rsp+2E0h+var_278], rsi
0x180050c5a  mov     rcx, [rsp+2E0h+var_290]
0x180050c5f  mov     rax, [rcx]
0x180050c62  lea     r8, [rsp+2E0h+var_278]
0x180050c67  xor     edx, edx
0x180050c69  mov     rax, [rax+40h]
0x180050c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c72  mov     ebx, eax
0x180050c74  test    eax, eax
0x180050c76  js      loc_180050CFD
0x180050c7c  mov     dword ptr [rsp+2E0h+ppv], 104h
0x180050c84  lea     r9, [rbp+1E0h+var_260]
0x180050c88  xor     r8d, r8d
0x180050c8b  xor     edx, edx
0x180050c8d  lea     rcx, FOLDERID_Public
0x180050c94  call    cs:__imp_SHGetFolderPathEx
0x180050c9a  mov     ebx, eax
0x180050c9c  test    eax, eax
0x180050c9e  js      short loc_180050CFD
0x180050ca0  mov     [rsp+2E0h+pv], rsi
0x180050ca5  lea     rdx, [rsp+2E0h+pv]
0x180050caa  mov     rcx, [rsp+2E0h+var_278]
0x180050caf  call    GetLocalPathForItemIfPossible
0x180050cb4  mov     ebx, eax
0x180050cb6  test    eax, eax
0x180050cb8  js      short loc_180050CFD
0x180050cba  mov     rdx, [rsp+2E0h+pv]
0x180050cbf  lea     rcx, [rbp+1E0h+var_260]
0x180050cc3  call    cs:__imp_PathIsEqualOrSubFolder
0x180050cc9  test    eax, eax
0x180050ccb  jz      short loc_180050CD3
0x180050ccd  mov     [rsp+2E0h+var_29C], edi
0x180050cd1  jmp     short loc_180050CD7
0x180050cd3  mov     edi, [rsp+2E0h+var_29C]
0x180050cd7  mov     rcx, [rsp+2E0h+ppvOut]; propBag
0x180050cdc  test    rcx, rcx
0x180050cdf  jz      short loc_180050CF1
0x180050ce1  mov     r8d, edi; value
0x180050ce4  lea     rdx, aWindowsshareis; "WindowsShareIsUnderPublicState"
0x180050ceb  call    cs:__imp_PSPropertyBag_WriteBOOL
0x180050cf1  mov     rcx, [rsp+2E0h+pv]; pv
0x180050cf6  call    cs:__imp_CoTaskMemFree
0x180050cfc  nop
0x180050cfd  lea     rcx, [rsp+2E0h+var_278]
0x180050d02  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050d07  nop
0x180050d08  lea     rcx, [rsp+2E0h+var_288]
0x180050d0d  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050d12  nop
0x180050d13  lea     rcx, [rsp+2E0h+var_270]
0x180050d18  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050d1d  nop
0x180050d1e  lea     rcx, [rsp+2E0h+var_290]
0x180050d23  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050d28  test    r13, r13
0x180050d2b  jz      short loc_180050D35
0x180050d2d  mov     eax, [rsp+2E0h+value]
0x180050d31  mov     [r13+0], eax
0x180050d35  test    r12, r12
0x180050d38  jz      short loc_180050D42
0x180050d3a  mov     eax, [rsp+2E0h+var_2A4]
0x180050d3e  mov     [r12], eax
0x180050d42  test    r15, r15
0x180050d45  jz      short loc_180050D4E
0x180050d47  mov     eax, [rsp+2E0h+var_2A0]
0x180050d4b  mov     [r15], eax
0x180050d4e  test    r14, r14
0x180050d51  jz      short loc_180050D5A
0x180050d53  mov     eax, [rsp+2E0h+var_29C]
0x180050d57  mov     [r14], eax
0x180050d5a  lea     rcx, [rsp+2E0h+ppvOut]
0x180050d5f  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180050d64  mov     eax, ebx
0x180050d66  mov     rcx, [rbp+1E0h+var_50]
0x180050d6d  xor     rcx, rsp; StackCookie
0x180050d70  call    __security_check_cookie
0x180050d75  add     rsp, 2A8h
0x180050d7c  pop     r15
0x180050d7e  pop     r14
0x180050d80  pop     r13
0x180050d82  pop     r12
0x180050d84  pop     rdi
0x180050d85  pop     rsi
0x180050d86  pop     rbx
0x180050d87  pop     rbp
0x180050d88  retn
```
