# CMapiManager::SendShutdownNotification(void)

- ea: `0x18003250c`
- end: `0x180032681`
- name: `?SendShutdownNotification@CMapiManager@@AEAAXXZ`
- size: `373`
- prototype: `void __fastcall(CMapiManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800320e8`

## callees

- `0x1800031c0`
- `0x1800048c0`
- `0x180005210`
- `0x1800187cc`
- `0x1800188a8`
- `0x180018b34`
- `0x180024504`
- `0x18002925c`
- `0x18002e65c`
- `0x18003250c`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800325ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800325b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180032646`
- `OLEAUT32!__imp_SysFreeString` at `0x1800325ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1800325b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180032646`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032550`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032550`

## string_xrefs

- `0x1800325c0`: `CMapiManager::SendShutdownNotification failed to create gather notify`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CMapiManager::SendShutdownNotification(CMapiManager *this)
{
  HRESULT v1; // eax
  int v2; // ebx
  const wchar_t *v3; // rdx
  const wchar_t **URL; // rax
  OLECHAR *v5; // rbx
  __int128 v6; // [rsp+30h] [rbp-29h] BYREF
  __int64 v7; // [rsp+40h] [rbp-19h]
  _BYTE v8[40]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v9[56]; // [rsp+78h] [rbp+1Fh] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+67h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp+6Fh] BYREF
  BSTR v12; // [rsp+D0h] [rbp+77h] BYREF

  if ( *((_DWORD *)this + 42) )
  {
    ppv = 0;
    v1 = CoCreateInstance(
           &GUID_9e175b6d_f52a_11d8_b9a5_505054503030,
           0,
           0x15u,
           &GUID_b05651f9_9b10_425e_b616_1fcd828db3b1,
           &ppv);
    v2 = v1;
    if ( v1 < 0 )
    {
      CLogger::Error(v1, L"CMapiManager::SendShutdownNotification failed to create gather notify");
    }
    else
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v12, L"Windows");
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"SystemIndex");
      v6 = 0;
      v7 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, __int128 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             v12,
             bstrString,
             &v6);
      SysFreeString(bstrString);
      SysFreeString(v12);
    }
    if ( v2 < 0 )
    {
      CLogger::Error(v2, L"CMapiManager::SendShutdownNotification failed to initialize gather notify");
    }
    else
    {
      CMapiUrl::CMapiUrl((CMapiUrl *)v8);
      ATL::CSimpleStringT<wchar_t,0>::SetString(v9, L"private", 7);
      CMapiUrl::SetStore((CMapiUrl *)v8, v3);
      URL = (const wchar_t **)CMapiUrl::GetURL(v8, &bstrString);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v12, *URL);
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&bstrString);
      v5 = v12;
      (*(void (__fastcall **)(LPVOID, __int64, BSTR, BSTR))(*(_QWORD *)ppv + 80LL))(ppv, 8388610, v12, v12);
      SysFreeString(v5);
      CMapiUrl::~CMapiUrl((CMapiUrl *)v8);
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppv);
  }
}

```

## disassembly

```asm
0x18003250c  mov     [rsp-8+arg_18], rbx
0x180032511  push    rbp
0x180032512  lea     rbp, [rsp-57h]
0x180032517  sub     rsp, 0B0h
0x18003251e  cmp     dword ptr [rcx+0A8h], 0
0x180032525  jz      loc_180032670
0x18003252b  mov     [rbp+57h+arg_0], 0
0x180032533  lea     rax, [rbp+57h+arg_0]
0x180032537  mov     [rsp+0B0h+ppv], rax; ppv
0x18003253c  lea     r9, _GUID_b05651f9_9b10_425e_b616_1fcd828db3b1; riid
0x180032543  xor     edx, edx; pUnkOuter
0x180032545  lea     r8d, [rdx+15h]; dwClsContext
0x180032549  lea     rcx, _GUID_9e175b6d_f52a_11d8_b9a5_505054503030; rclsid
0x180032550  call    cs:__imp_CoCreateInstance
0x180032556  mov     ebx, eax
0x180032558  test    eax, eax
0x18003255a  js      short loc_1800325C0
0x18003255c  lea     rdx, aWindows; "Windows"
0x180032563  lea     rcx, [rbp+57h+arg_10]; this
0x180032567  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x18003256c  nop
0x18003256d  lea     rdx, aSystemindex; "SystemIndex"
0x180032574  lea     rcx, [rbp+57h+bstrString]; this
0x180032578  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x18003257d  nop
0x18003257e  xorps   xmm0, xmm0
0x180032581  xor     eax, eax
0x180032583  mov     rcx, [rbp+57h+arg_0]
0x180032587  movaps  [rbp+57h+var_80], xmm0
0x18003258b  mov     [rbp+57h+var_70], rax
0x18003258f  mov     rax, [rcx]
0x180032592  lea     r9, [rbp+57h+var_80]
0x180032596  mov     r8, [rbp+57h+bstrString]
0x18003259a  mov     rdx, [rbp+57h+arg_10]
0x18003259e  mov     rax, [rax+38h]
0x1800325a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a7  mov     ebx, eax
0x1800325a9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1800325ad  call    cs:__imp_SysFreeString
0x1800325b3  nop
0x1800325b4  mov     rcx, [rbp+57h+arg_10]; bstrString
0x1800325b8  call    cs:__imp_SysFreeString
0x1800325be  jmp     short loc_1800325CE
0x1800325c0  lea     rdx, aCmapimanagerSe; "CMapiManager::SendShutdownNotification "...
0x1800325c7  mov     ecx, eax; int
0x1800325c9  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x1800325ce  test    ebx, ebx
0x1800325d0  js      loc_180032658
0x1800325d6  lea     rcx, [rbp+57h+var_60]; this
0x1800325da  call    ??0CMapiUrl@@QEAA@XZ; CMapiUrl::CMapiUrl(void)
0x1800325df  nop
0x1800325e0  mov     r8d, 7
0x1800325e6  lea     rdx, aPrivate; "private"
0x1800325ed  lea     rcx, [rbp+57h+var_38]
0x1800325f1  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800325f6  lea     rcx, [rbp+57h+var_60]; this
0x1800325fa  call    ?SetStore@CMapiUrl@@QEAAXPEB_W@Z; CMapiUrl::SetStore(wchar_t const *)
0x1800325ff  lea     rdx, [rbp+57h+bstrString]
0x180032603  lea     rcx, [rbp+57h+var_60]
0x180032607  call    ?GetURL@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::GetURL(void)
0x18003260c  nop
0x18003260d  mov     rdx, [rax]; wchar_t *
0x180032610  lea     rcx, [rbp+57h+arg_10]; this
0x180032614  call    ??0CComBSTR@ATL@@QEAA@PEB_W@Z; ATL::CComBSTR::CComBSTR(wchar_t const *)
0x180032619  nop
0x18003261a  lea     rcx, [rbp+57h+bstrString]
0x18003261e  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180032623  mov     rcx, [rbp+57h+arg_0]
0x180032627  mov     rax, [rcx]
0x18003262a  mov     rbx, [rbp+57h+arg_10]
0x18003262e  mov     r9, rbx
0x180032631  mov     r8, rbx
0x180032634  mov     edx, 800002h
0x180032639  mov     rax, [rax+50h]
0x18003263d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032642  nop
0x180032643  mov     rcx, rbx; bstrString
0x180032646  call    cs:__imp_SysFreeString
0x18003264c  nop
0x18003264d  lea     rcx, [rbp+57h+var_60]; this
0x180032651  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x180032656  jmp     short loc_180032667
0x180032658  lea     rdx, aCmapimanagerSe_0; "CMapiManager::SendShutdownNotification "...
0x18003265f  mov     ecx, ebx; int
0x180032661  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x180032666  nop
0x180032667  lea     rcx, [rbp+57h+arg_0]
0x18003266b  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180032670  mov     rbx, [rsp+0B0h+arg_18]
0x180032678  add     rsp, 0B0h
0x18003267f  pop     rbp
0x180032680  retn
```
