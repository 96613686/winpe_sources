# FindItemInProfileAndStartOutlook(CMapiUrl &,int,ATL::CComBSTR &,ATL::CComPtr<Outlook::_Application> &,ATL::CComPtr<Outlook::_NameSpace> &,ATL::CComBSTR &,ATL::CComBSTR &,int)

- ea: `0x180019a20`
- end: `0x180019d36`
- name: `?FindItemInProfileAndStartOutlook@@YAJAEAVCMapiUrl@@HAEAVCComBSTR@ATL@@AEAV?$CComPtr@U_Application@Outlook@@@3@AEAV?$CComPtr@U_NameSpace@Outlook@@@3@11H@Z`
- size: `790`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c020`

## callees

- `0x18000419c`
- `0x1800048c0`
- `0x180005210`
- `0x180006270`
- `0x180018c14`
- `0x180018d88`
- `0x1800199b8`
- `0x180019a20`
- `0x18001dff8`
- `0x180020864`
- `0x18002fcdc`
- `0x18003d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180019ccb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ccb`
- `OLEAUT32!__imp_VariantClear` at `0x180019b8d`
- `OLEAUT32!__imp_VariantClear` at `0x180019cb5`
- `OLEAUT32!__imp_VariantClear` at `0x180019cc1`
- `OLEAUT32!__imp_VariantClear` at `0x180019b8d`
- `OLEAUT32!__imp_VariantClear` at `0x180019cb5`
- `OLEAUT32!__imp_VariantClear` at `0x180019cc1`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019c12`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180019c12`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180019c1d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180019c1d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180019a7a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180019a7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019aaa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019a92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019a92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ae8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019b4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019ae8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180019b4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FindItemInProfileAndStartOutlook(
        __int64 a1,
        int a2,
        __int64 a3,
        LPVOID *a4,
        __int64 *a5,
        BSTR *a6,
        BSTR *a7)
{
  HANDLE v10; // rax
  void *v11; // rbx
  int v12; // r14d
  int OutlookCLSID; // ebx
  bool v14; // al
  BSTR *v15; // r13
  BSTR v16; // rax
  LPVOID v17; // rsi
  __int64 (__fastcall *v18)(LPVOID, _QWORD, __int64, _QWORD, BSTR *, BSTR *); // rdi
  __int64 v19; // rbx
  _QWORD *v20; // rax
  UINT v21; // eax
  __int64 v22; // rcx
  int v23; // edx
  const char *v24; // rcx
  wchar_t *v25; // rax
  LPVOID v27; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v31; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG v32; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v33; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v34; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v35; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v36; // [rsp+100h] [rbp+0h] BYREF
  IID rclsid; // [rsp+120h] [rbp+20h] BYREF

  v10 = OpenMutexW(0x1F0001u, 0, L"MSSPHTB_Alive");
  v11 = v10;
  v31 = v10;
  if ( !v10 )
    goto LABEL_5;
  if ( WaitForSingleObject(v10, 0) != 258 )
  {
    ReleaseMutex(v11);
LABEL_5:
    v12 = 0;
    goto LABEL_6;
  }
  v12 = 1;
LABEL_6:
  rclsid = GUID_NULL;
  OutlookCLSID = CMapiSupport::GetOutlookCLSID(&rclsid);
  if ( OutlookCLSID < 0 )
    goto LABEL_22;
  OutlookCLSID = CoCreateInstance(&rclsid, 0, 4u, &IID__Application, a4);
  if ( OutlookCLSID < 0 )
    goto LABEL_22;
  OutlookCLSID = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)*a4 + 72LL))(*a4, a5);
  if ( OutlookCLSID < 0 )
    goto LABEL_22;
  v27 = 0;
  v14 = IsMapiDLL64Bit();
  OutlookCLSID = CoCreateInstance(
                   &GUID_1af81e4e_fc45_48ee_b236_a2a663494390,
                   0,
                   v14 ? 524292 : 4,
                   &GUID_38004ea6_ecfd_4da2_a68f_d76ff85da38f,
                   &v27);
  if ( OutlookCLSID >= 0 )
  {
    if ( !a2 )
    {
      v17 = v27;
      v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD, BSTR *, BSTR *))(*(_QWORD *)v27 + 56LL);
      v19 = *(_QWORD *)CMapiUrl::EntryId(a1, &v30);
      v20 = (_QWORD *)CMapiUrl::StoreHash(a1, &v29);
      v15 = a7;
      OutlookCLSID = v18(v17, *v20, v19, 0, a6, a7);
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v29);
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v30);
      goto LABEL_13;
    }
    OutlookCLSID = -2147467263;
  }
  v15 = a7;
LABEL_13:
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&v27);
  if ( OutlookCLSID >= 0 && !v12 )
  {
    pvarg.vt = 0;
    VariantClear(&pvarg);
    pvarg.vt = 8;
    if ( *a6 )
    {
      v21 = SysStringByteLen(*a6);
      v16 = SysAllocStringByteLen((LPCSTR)*a6, v21);
    }
    else
    {
      v16 = 0;
    }
    pvarg.llVal = (LONGLONG)v16;
    if ( !v16 && *a6 )
    {
      pvarg.vt = 10;
      pvarg.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v32.vt = 10;
    v32.lVal = -2147352572;
    v22 = *a5;
    v33 = v32;
    v34 = v32;
    v35 = v32;
    v36 = pvarg;
    (*(void (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v22 + 176LL))(
      v22,
      &v36,
      &v35,
      &v34,
      &v33);
    VariantClear(&v32);
    VariantClear(&pvarg);
    SysFreeString(*v15);
    v25 = A2WBSTR(v24, v23);
    *v15 = v25;
    if ( !v25 )
      ATL::AtlThrowImpl(-2147024882);
  }
LABEL_22:
  OutlookSync::~OutlookSync((OutlookSync *)&v31);
  return (unsigned int)OutlookCLSID;
}

```

## disassembly

```asm
0x180019a20  mov     [rsp-8+arg_8], rbx
0x180019a25  push    rbp
0x180019a26  push    rsi
0x180019a27  push    rdi
0x180019a28  push    r12
0x180019a2a  push    r13
0x180019a2c  push    r14
0x180019a2e  push    r15
0x180019a30  lea     rbp, [rsp-40h]
0x180019a35  sub     rsp, 140h
0x180019a3c  mov     rax, cs:__security_cookie
0x180019a43  xor     rax, rsp
0x180019a46  mov     [rbp+70h+var_40], rax
0x180019a4a  mov     rdi, r9
0x180019a4d  mov     esi, edx
0x180019a4f  mov     r13, rcx
0x180019a52  mov     rax, [rbp+70h+arg_30]
0x180019a59  mov     [rsp+170h+var_130], rax
0x180019a5e  mov     r15, [rbp+70h+arg_28]
0x180019a65  mov     r12, [rbp+70h+arg_20]
0x180019a6c  lea     r8, Name; "MSSPHTB_Alive"
0x180019a73  xor     edx, edx; bInheritHandle
0x180019a75  mov     ecx, 1F0001h; dwDesiredAccess
0x180019a7a  call    cs:__imp_OpenMutexW
0x180019a80  mov     rbx, rax
0x180019a83  mov     [rsp+170h+var_F8], rax
0x180019a88  test    rax, rax
0x180019a8b  jz      short loc_180019AB0
0x180019a8d  xor     edx, edx; dwMilliseconds
0x180019a8f  mov     rcx, rax; hHandle
0x180019a92  call    cs:__imp_WaitForSingleObject
0x180019a98  cmp     eax, 102h
0x180019a9d  jnz     short loc_180019AA7
0x180019a9f  mov     r14d, 1
0x180019aa5  jmp     short loc_180019AB3
0x180019aa7  mov     rcx, rbx; hMutex
0x180019aaa  call    cs:__imp_ReleaseMutex
0x180019ab0  xor     r14d, r14d
0x180019ab3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180019aba  movdqu  xmmword ptr [rbp+70h+rclsid.Data1], xmm0
0x180019abf  lea     rcx, [rbp+70h+rclsid]; lpclsid
0x180019ac3  call    ?GetOutlookCLSID@CMapiSupport@@SAJPEAU_GUID@@@Z; CMapiSupport::GetOutlookCLSID(_GUID *)
0x180019ac8  mov     ebx, eax
0x180019aca  test    eax, eax
0x180019acc  js      loc_180019CDF
0x180019ad2  mov     [rsp+170h+ppv], rdi; ppv
0x180019ad7  lea     r9, IID__Application; riid
0x180019ade  xor     edx, edx; pUnkOuter
0x180019ae0  lea     r8d, [rdx+4]; dwClsContext
0x180019ae4  lea     rcx, [rbp+70h+rclsid]; rclsid
0x180019ae8  call    cs:__imp_CoCreateInstance
0x180019aee  mov     ebx, eax
0x180019af0  test    eax, eax
0x180019af2  js      loc_180019CDF
0x180019af8  mov     rcx, [rdi]
0x180019afb  mov     rax, [rcx]
0x180019afe  mov     rdx, r12
0x180019b01  mov     rax, [rax+48h]
0x180019b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b0a  mov     ebx, eax
0x180019b0c  test    eax, eax
0x180019b0e  js      loc_180019CDF
0x180019b14  mov     [rsp+170h+var_128], 0
0x180019b1d  call    ?IsMapiDLL64Bit@@YA_NXZ; IsMapiDLL64Bit(void)
0x180019b22  neg     al
0x180019b24  sbb     r8d, r8d
0x180019b27  and     r8d, 80000h
0x180019b2e  add     r8d, 4; dwClsContext
0x180019b32  lea     rax, [rsp+170h+var_128]
0x180019b37  mov     [rsp+170h+ppv], rax; ppv
0x180019b3c  lea     r9, _GUID_38004ea6_ecfd_4da2_a68f_d76ff85da38f; riid
0x180019b43  xor     edx, edx; pUnkOuter
0x180019b45  lea     rcx, _GUID_1af81e4e_fc45_48ee_b236_a2a663494390; rclsid
0x180019b4c  call    cs:__imp_CoCreateInstance
0x180019b52  mov     ebx, eax
0x180019b54  test    eax, eax
0x180019b56  js      short loc_180019B61
0x180019b58  test    esi, esi
0x180019b5a  jz      short loc_180019BA8
0x180019b5c  mov     ebx, 80004001h
0x180019b61  mov     r13, [rsp+170h+var_130]
0x180019b66  lea     rcx, [rsp+170h+var_128]
0x180019b6b  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180019b70  test    ebx, ebx
0x180019b72  js      loc_180019CDF
0x180019b78  test    r14d, r14d
0x180019b7b  jnz     loc_180019CDF
0x180019b81  xor     eax, eax
0x180019b83  mov     word ptr [rsp+170h+pvarg], ax
0x180019b88  lea     rcx, [rsp+170h+pvarg]; pvarg
0x180019b8d  call    cs:__imp_VariantClear
0x180019b93  lea     eax, [r14+8]
0x180019b97  mov     word ptr [rsp+170h+pvarg], ax
0x180019b9c  mov     rcx, [r15]; bstr
0x180019b9f  test    rcx, rcx
0x180019ba2  jnz     short loc_180019C12
0x180019ba4  xor     eax, eax
0x180019ba6  jmp     short loc_180019C23
0x180019ba8  mov     rsi, [rsp+170h+var_128]
0x180019bad  mov     rax, [rsi]
0x180019bb0  mov     rdi, [rax+38h]
0x180019bb4  lea     rdx, [rsp+170h+var_100]
0x180019bb9  mov     rcx, r13
0x180019bbc  call    ?EntryId@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::EntryId(void)
0x180019bc1  nop
0x180019bc2  mov     rbx, [rax]
0x180019bc5  lea     rdx, [rsp+170h+var_108]
0x180019bca  mov     rcx, r13
0x180019bcd  call    ?StoreHash@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::StoreHash(void)
0x180019bd2  nop
0x180019bd3  mov     r13, [rsp+170h+var_130]
0x180019bd8  mov     [rsp+170h+var_148], r13
0x180019bdd  mov     [rsp+170h+ppv], r15
0x180019be2  xor     r9d, r9d
0x180019be5  mov     r8, rbx
0x180019be8  mov     rdx, [rax]
0x180019beb  mov     rcx, rsi
0x180019bee  mov     rax, rdi
0x180019bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bf6  mov     ebx, eax
0x180019bf8  lea     rcx, [rsp+170h+var_108]
0x180019bfd  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180019c02  nop
0x180019c03  lea     rcx, [rsp+170h+var_100]
0x180019c08  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180019c0d  jmp     loc_180019B66
0x180019c12  call    cs:__imp_SysStringByteLen
0x180019c18  mov     edx, eax; len
0x180019c1a  mov     rcx, [r15]; psz
0x180019c1d  call    cs:__imp_SysAllocStringByteLen
0x180019c23  mov     dword ptr [rsp+170h+pvarg+8], eax
0x180019c27  mov     rcx, rax
0x180019c2a  sar     rcx, 20h
0x180019c2e  mov     dword ptr [rsp+170h+pvarg+0Ch], ecx
0x180019c32  test    rax, rax
0x180019c35  jnz     short loc_180019C40
0x180019c37  cmp     [r15], rax
0x180019c3a  jnz     loc_180019D1D
0x180019c40  mov     eax, 0Ah
0x180019c45  mov     word ptr [rbp+70h+var_F0], ax
0x180019c49  mov     dword ptr [rbp+70h+var_F0+8], 80020004h
0x180019c50  mov     rcx, [r12]
0x180019c54  movups  xmm1, xmmword ptr [rbp+70h+var_F0]
0x180019c58  movaps  [rbp+70h+var_D0], xmm1
0x180019c5c  movsd   xmm0, qword ptr [rbp+70h+var_F0+10h]
0x180019c61  movsd   [rbp+70h+var_C0], xmm0
0x180019c66  movaps  [rbp+70h+var_B0], xmm1
0x180019c6a  movsd   [rbp+70h+var_A0], xmm0
0x180019c6f  movaps  [rbp+70h+var_90], xmm1
0x180019c73  movsd   [rbp+70h+var_80], xmm0
0x180019c78  movups  xmm0, xmmword ptr [rsp+170h+pvarg]
0x180019c7d  movaps  [rbp+70h+var_70], xmm0
0x180019c81  movsd   xmm1, qword ptr [rsp+170h+pvarg+10h]
0x180019c87  movsd   [rbp+70h+var_60], xmm1
0x180019c8c  mov     rax, [rcx]
0x180019c8f  lea     rdx, [rbp+70h+var_D0]
0x180019c93  mov     [rsp+170h+ppv], rdx
0x180019c98  lea     r9, [rbp+70h+var_B0]
0x180019c9c  lea     r8, [rbp+70h+var_90]
0x180019ca0  lea     rdx, [rbp+70h+var_70]
0x180019ca4  mov     rax, [rax+0B0h]
0x180019cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cb0  nop
0x180019cb1  lea     rcx, [rbp+70h+var_F0]; pvarg
0x180019cb5  call    cs:__imp_VariantClear
0x180019cbb  nop
0x180019cbc  lea     rcx, [rsp+170h+pvarg]; pvarg
0x180019cc1  call    cs:__imp_VariantClear
0x180019cc7  mov     rcx, [r13+0]; bstrString
0x180019ccb  call    cs:__imp_SysFreeString
0x180019cd1  call    ?A2WBSTR@@YAPEA_WPEBDH@Z; A2WBSTR(char const *,int)
0x180019cd6  mov     [r13+0], rax
0x180019cda  test    rax, rax
0x180019cdd  jz      short loc_180019D12
0x180019cdf  lea     rcx, [rsp+170h+var_F8]; this
0x180019ce4  call    ??1OutlookSync@@QEAA@XZ; OutlookSync::~OutlookSync(void)
0x180019ce9  mov     eax, ebx
0x180019ceb  mov     rcx, [rbp+70h+var_40]
0x180019cef  xor     rcx, rsp; StackCookie
0x180019cf2  call    __security_check_cookie
0x180019cf7  mov     rbx, [rsp+170h+arg_8]
0x180019cff  add     rsp, 140h
0x180019d06  pop     r15
0x180019d08  pop     r14
0x180019d0a  pop     r13
0x180019d0c  pop     r12
0x180019d0e  pop     rdi
0x180019d0f  pop     rsi
0x180019d10  pop     rbp
0x180019d11  retn
0x180019d12  mov     ecx, 8007000Eh; int
0x180019d17  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019d1d  mov     eax, 0Ah
0x180019d22  mov     word ptr [rsp+170h+pvarg], ax
0x180019d27  mov     ecx, 8007000Eh; int
0x180019d2c  mov     dword ptr [rsp+170h+pvarg+8], ecx
0x180019d30  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
