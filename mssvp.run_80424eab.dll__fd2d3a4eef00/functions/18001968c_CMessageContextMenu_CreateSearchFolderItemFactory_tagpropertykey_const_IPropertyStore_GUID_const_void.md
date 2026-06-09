# CMessageContextMenu::CreateSearchFolderItemFactory(_tagpropertykey const &,IPropertyStore *,_GUID const &,void * *)

- ea: `0x18001968c`
- end: `0x180019836`
- name: `?CreateSearchFolderItemFactory@CMessageContextMenu@@IEAAJAEBU_tagpropertykey@@PEAUIPropertyStore@@AEBU_GUID@@PEAPEAX@Z`
- size: `426`
- prototype: `int(CMessageContextMenu *__hidden this, const struct _tagpropertykey *, struct IPropertyStore *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001dac4`

## callees

- `0x180005210`
- `0x180006270`
- `0x180019188`
- `0x18001968c`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800197ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800196de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800196de`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001970a`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18001970a`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x180019731`
- `api-ms-win-shell-namespace-l1-1-1!SHCreateShellItemArrayFromShellItem` at `0x180019731`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMessageContextMenu::CreateSearchFolderItemFactory(
        CMessageContextMenu *this,
        const struct _tagpropertykey *a2,
        struct IPropertyStore *a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT DisplayNameForPropertySearch; // ebx
  CMessageContextMenu *v8; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  void *v12; // [rsp+40h] [rbp-30h] BYREF
  IShellItem *psi; // [rsp+48h] [rbp-28h] BYREF
  PROPERTYKEY v14; // [rsp+50h] [rbp-20h] BYREF
  int v15; // [rsp+64h] [rbp-Ch]

  ppv = 0;
  DisplayNameForPropertySearch = CoCreateInstance(
                                   &CLSID_SearchFolderItemFactory,
                                   0,
                                   0x17u,
                                   &GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2,
                                   &ppv);
  if ( DisplayNameForPropertySearch >= 0 )
  {
    psi = 0;
    DisplayNameForPropertySearch = SHCreateItemFromParsingName(
                                     L"mapi://",
                                     0,
                                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                     (void **)&psi);
    if ( DisplayNameForPropertySearch >= 0 )
    {
      v12 = 0;
      DisplayNameForPropertySearch = SHCreateShellItemArrayFromShellItem(
                                       psi,
                                       &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                                       &v12);
      if ( DisplayNameForPropertySearch >= 0 )
      {
        DisplayNameForPropertySearch = (*(__int64 (__fastcall **)(LPVOID, void *))(*(_QWORD *)ppv + 88LL))(ppv, v12);
        if ( DisplayNameForPropertySearch >= 0 )
        {
          v14 = PKEY_Message_DateReceived;
          v15 = -1;
          DisplayNameForPropertySearch = (*(__int64 (__fastcall **)(LPVOID, __int64, PROPERTYKEY *))(*(_QWORD *)ppv + 64LL))(
                                           ppv,
                                           1,
                                           &v14);
          if ( DisplayNameForPropertySearch >= 0 )
          {
            pv = 0;
            DisplayNameForPropertySearch = CMessageContextMenu::CreateDisplayNameForPropertySearch(
                                             v8,
                                             a2,
                                             a3,
                                             (wchar_t **)&pv);
            if ( DisplayNameForPropertySearch >= 0 )
            {
              DisplayNameForPropertySearch = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)ppv + 24LL))(
                                               ppv,
                                               pv);
              if ( DisplayNameForPropertySearch >= 0 )
                DisplayNameForPropertySearch = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))ppv)(
                                                 ppv,
                                                 &GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2,
                                                 a5);
              CoTaskMemFree(pv);
            }
          }
        }
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&v12);
    }
    ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&psi);
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
  return (unsigned int)DisplayNameForPropertySearch;
}

```

## disassembly

```asm
0x18001968c  mov     [rsp-18h+arg_0], rbx
0x180019691  mov     [rsp-18h+arg_18], rsi
0x180019696  push    rbp
0x180019697  push    rdi
0x180019698  push    r14
0x18001969a  mov     rbp, rsp
0x18001969d  sub     rsp, 70h
0x1800196a1  mov     rax, cs:__security_cookie
0x1800196a8  xor     rax, rsp
0x1800196ab  mov     [rbp+var_8], rax
0x1800196af  mov     rsi, r8
0x1800196b2  mov     rdi, rdx
0x1800196b5  mov     r14, [rbp+arg_20]
0x1800196b9  mov     [rbp+var_40], 0
0x1800196c1  lea     rax, [rbp+var_40]
0x1800196c5  mov     [rsp+70h+ppv], rax; ppv
0x1800196ca  lea     r9, _GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2; riid
0x1800196d1  xor     edx, edx; pUnkOuter
0x1800196d3  lea     r8d, [rdx+17h]; dwClsContext
0x1800196d7  lea     rcx, CLSID_SearchFolderItemFactory; rclsid
0x1800196de  call    cs:__imp_CoCreateInstance
0x1800196e4  mov     ebx, eax
0x1800196e6  test    eax, eax
0x1800196e8  js      loc_18001980A
0x1800196ee  mov     [rbp+psi], 0
0x1800196f6  lea     r9, [rbp+psi]; ppv
0x1800196fa  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180019701  xor     edx, edx; pbc
0x180019703  lea     rcx, pszPath; "mapi://"
0x18001970a  call    cs:__imp_SHCreateItemFromParsingName
0x180019710  mov     ebx, eax
0x180019712  test    eax, eax
0x180019714  js      loc_180019800
0x18001971a  mov     [rbp+var_30], 0
0x180019722  lea     r8, [rbp+var_30]; ppv
0x180019726  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x18001972d  mov     rcx, [rbp+psi]; psi
0x180019731  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x180019737  mov     ebx, eax
0x180019739  test    eax, eax
0x18001973b  js      loc_1800197F6
0x180019741  mov     rcx, [rbp+var_40]
0x180019745  mov     rax, [rcx]
0x180019748  mov     rdx, [rbp+var_30]
0x18001974c  mov     rax, [rax+58h]
0x180019750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019755  mov     ebx, eax
0x180019757  test    eax, eax
0x180019759  js      loc_1800197F6
0x18001975f  movups  xmm0, xmmword ptr cs:PKEY_Message_DateReceived.fmtid.Data1
0x180019766  movups  [rbp+var_20], xmm0
0x18001976a  mov     eax, cs:PKEY_Message_DateReceived.pid
0x180019770  mov     [rbp+var_10], eax
0x180019773  mov     [rbp+var_C], 0FFFFFFFFh
0x18001977a  mov     rcx, [rbp+var_40]
0x18001977e  mov     rax, [rcx]
0x180019781  lea     r8, [rbp+var_20]
0x180019785  mov     edx, 1
0x18001978a  mov     rax, [rax+40h]
0x18001978e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019793  mov     ebx, eax
0x180019795  test    eax, eax
0x180019797  js      short loc_1800197F6
0x180019799  mov     [rbp+pv], 0
0x1800197a1  lea     r9, [rbp+pv]; wchar_t **
0x1800197a5  mov     r8, rsi; struct IPropertyStore *
0x1800197a8  mov     rdx, rdi; struct _tagpropertykey *
0x1800197ab  call    ?CreateDisplayNameForPropertySearch@CMessageContextMenu@@IEAAJAEBU_tagpropertykey@@PEAUIPropertyStore@@PEAPEA_W@Z; CMessageContextMenu::CreateDisplayNameForPropertySearch(_tagpropertykey const &,IPropertyStore *,wchar_t * *)
0x1800197b0  mov     ebx, eax
0x1800197b2  test    eax, eax
0x1800197b4  js      short loc_1800197F6
0x1800197b6  mov     rcx, [rbp+var_40]
0x1800197ba  mov     rax, [rcx]
0x1800197bd  mov     rdx, [rbp+pv]
0x1800197c1  mov     rax, [rax+18h]
0x1800197c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197ca  mov     ebx, eax
0x1800197cc  test    eax, eax
0x1800197ce  js      short loc_1800197EB
0x1800197d0  mov     rcx, [rbp+var_40]
0x1800197d4  mov     rax, [rcx]
0x1800197d7  mov     r8, r14
0x1800197da  lea     rdx, _GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2
0x1800197e1  mov     rax, [rax]
0x1800197e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197e9  mov     ebx, eax
0x1800197eb  mov     rcx, [rbp+pv]; pv
0x1800197ef  call    cs:__imp_CoTaskMemFree
0x1800197f5  nop
0x1800197f6  lea     rcx, [rbp+var_30]
0x1800197fa  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800197ff  nop
0x180019800  lea     rcx, [rbp+psi]
0x180019804  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180019809  nop
0x18001980a  lea     rcx, [rbp+var_40]
0x18001980e  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180019813  mov     eax, ebx
0x180019815  mov     rcx, [rbp+var_8]
0x180019819  xor     rcx, rsp; StackCookie
0x18001981c  call    __security_check_cookie
0x180019821  lea     r11, [rsp+70h+var_s0]
0x180019826  mov     rbx, [r11+20h]
0x18001982a  mov     rsi, [r11+38h]
0x18001982e  mov     rsp, r11
0x180019831  pop     r14
0x180019833  pop     rdi
0x180019834  pop     rbp
0x180019835  retn
```
