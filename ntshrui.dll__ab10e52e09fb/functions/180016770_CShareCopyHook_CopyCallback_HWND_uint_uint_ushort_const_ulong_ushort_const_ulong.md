# CShareCopyHook::CopyCallback(HWND__ *,uint,uint,ushort const *,ulong,ushort const *,ulong)

- ea: `0x180016770`
- end: `0x180016b31`
- name: `?CopyCallback@CShareCopyHook@@UEAAIPEAUHWND__@@IIPEBGK1K@Z`
- size: `961`
- prototype: `unsigned int(CShareCopyHook *__hidden this, HWND, unsigned int, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016770`
- `0x180016b38`
- `0x180016c30`
- `0x180016f8c`
- `0x18001a1a4`
- `0x18001c4a8`
- `0x1800254e0`
- `0x180026394`
- `0x18002b1c4`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001686e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001698d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016ad0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001686e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001698d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016ad0`
- `SHELL32!SHCreateItemFromIDList` at `0x1800168cc`
- `SHELL32!SHCreateItemFromIDList` at `0x1800168cc`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800168e9`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800168e9`
- `SHELL32!__imp_ILFree` at `0x1800168f6`
- `SHELL32!__imp_ILFree` at `0x1800168f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CShareCopyHook::CopyCallback(
        CShareCopyHook *this,
        HWND a2,
        int a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  unsigned int v8; // r14d
  CShareCopyHook *v9; // rcx
  __int64 v10; // r8
  HRESULT v11; // ebx
  CShareCopyHook *v12; // rcx
  void **v13; // rcx
  CShareCopyHook *v15; // rcx
  int v16; // eax
  struct IShellItemArray *v17; // [rsp+30h] [rbp-D0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  IShellItem *psi; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  void *v21; // [rsp+50h] [rbp-B0h] BYREF
  struct IShareManager *ppv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[588]; // [rsp+74h] [rbp-8Ch] BYREF

  v8 = 6;
  if ( (a6 & 0x10) == 0 || ((a3 - 1) & 0xFFFFFFFC) != 0 || a3 == 2 )
    return v8;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_ShareManager, 0, 1u, &GUID_5bb62628_92e7_4f54_81a5_29c579341e13, (LPVOID *)&ppv) >= 0 )
  {
    v20 = 0;
    if ( (*(int (__fastcall **)(struct IShareManager *, unsigned __int16 *, __int64, int *))(*(_QWORD *)ppv + 48LL))(
           ppv,
           a5,
           1,
           &v20) >= 0 )
    {
      if ( v20 )
      {
        pidl = 0;
        v17 = 0;
        if ( CShareCopyHook::_GetItemAndArrayForPath(v9, a5, a6, (struct IShellItem **)&pidl, &v17) >= 0 )
        {
          v16 = CShareCopyHook::_StopSharingSMB(v15, a2, a5, v17, ppv);
          if ( v16 == -2147023673 )
          {
            v8 = 2;
          }
          else if ( v16 >= 0 )
          {
            psi = 0;
            if ( CoCreateInstance(
                   &CLSID_WSDPublisher,
                   0,
                   1u,
                   &GUID_065e74c3_6872_44cb_b894_cfec1284f23f,
                   (LPVOID *)&psi) >= 0 )
            {
              ((void (__fastcall *)(IShellItem *, struct IShellItemArray *))psi->lpVtbl->GetDisplayName)(psi, v17);
              ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
            }
          }
        }
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v17);
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&pidl);
        goto LABEL_25;
      }
      if ( a3 != 4 )
      {
        v17 = 0;
        if ( CoCreateInstance(
               &CLSID_InplaceShareEngine,
               0,
               1u,
               &GUID_559b1911_d3af_486e_b8bc_242b24df0114,
               (LPVOID *)&v17) < 0 )
        {
LABEL_23:
          if ( v17 )
            ((void (__fastcall *)(struct IShellItemArray *))v17->lpVtbl->Release)(v17);
          goto LABEL_25;
        }
        psi = 0;
        v21 = 0;
        pidl = 0;
        memset_0(v26, 0, sizeof(v26));
        v25 = a6;
        if ( (int)SHSimpleIDListFromFindDataAndFlags(a5, &v25, v10, &pidl) < 0 )
          goto LABEL_35;
        v11 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&psi);
        if ( v11 >= 0 )
          v11 = SHCreateShellItemArrayFromShellItem(psi, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, &v21);
        ILFree((LPITEMIDLIST)pidl);
        if ( v11 < 0 )
        {
LABEL_35:
          SafeRelease<IShellItemArray>(&psi);
          v13 = &v21;
        }
        else
        {
          if ( !CShareCopyHook::_IsSharedInplace(v12, (struct IShareEngine *)v17, psi, a5)
            || ((int (__fastcall *)(struct IShellItemArray *, void *))v17->lpVtbl->GetPropertyStore)(v17, v21) < 0 )
          {
            goto LABEL_19;
          }
          v24 = 0;
          v23 = 0;
          ((void (__fastcall *)(struct IShellItemArray *, _QWORD, _QWORD, __int64 *, __int64 *))v17->lpVtbl->GetItemAt)(
            v17,
            0,
            0,
            &v23,
            &v24);
          pidl = 0;
          if ( CoCreateInstance(&CLSID_WSDPublisher, 0, 1u, &GUID_065e74c3_6872_44cb_b894_cfec1284f23f, (LPVOID *)&pidl) >= 0 )
          {
            (*(void (__fastcall **)(LPCITEMIDLIST, void *))(*(_QWORD *)&pidl->mkid.cb + 40LL))(pidl, v21);
            (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
          }
          SafeRelease<IShellItemArray>(&v23);
          v13 = (void **)&v24;
        }
        SafeRelease<IShellItemArray>(v13);
LABEL_19:
        if ( v21 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
        if ( psi )
          ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
        goto LABEL_23;
      }
    }
  }
LABEL_25:
  if ( ppv )
    (*(void (__fastcall **)(struct IShareManager *))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x180016770  push    rbp
0x180016772  push    rbx
0x180016773  push    rsi
0x180016774  push    rdi
0x180016775  push    r12
0x180016777  push    r13
0x180016779  push    r14
0x18001677b  push    r15
0x18001677d  lea     rbp, [rsp-1D8h]
0x180016785  sub     rsp, 2D8h
0x18001678c  mov     rax, cs:__security_cookie
0x180016793  xor     rax, rsp
0x180016796  mov     [rbp+210h+var_50], rax
0x18001679d  mov     ebx, r8d
0x1800167a0  mov     r15, rdx
0x1800167a3  mov     rdi, [rbp+210h+arg_20]
0x1800167aa  mov     r14d, 6
0x1800167b0  mov     esi, [rbp+210h+arg_28]
0x1800167b6  test    sil, 10h
0x1800167ba  jz      loc_180016A2F
0x1800167c0  lea     eax, [r8-1]
0x1800167c4  test    eax, 0FFFFFFFCh
0x1800167c9  jnz     loc_180016A2F
0x1800167cf  cmp     ebx, 2
0x1800167d2  jz      loc_180016A2F
0x1800167d8  xor     r12d, r12d
0x1800167db  mov     [rsp+310h+var_2B8], r12
0x1800167e0  lea     rax, [rsp+310h+var_2B8]
0x1800167e5  mov     [rsp+310h+ppv], rax; ppv
0x1800167ea  lea     r9, _GUID_5bb62628_92e7_4f54_81a5_29c579341e13; riid
0x1800167f1  lea     r13d, [r14-5]
0x1800167f5  mov     r8d, r13d; dwClsContext
0x1800167f8  xor     edx, edx; pUnkOuter
0x1800167fa  lea     rcx, CLSID_ShareManager; rclsid
0x180016801  call    cs:__imp_CoCreateInstance
0x180016807  test    eax, eax
0x180016809  js      loc_180016A18
0x18001680f  mov     [rsp+310h+var_2C8], r12d
0x180016814  mov     rcx, [rsp+310h+var_2B8]
0x180016819  mov     rax, [rcx]
0x18001681c  lea     r9, [rsp+310h+var_2C8]
0x180016821  mov     r8d, r13d
0x180016824  mov     rdx, rdi
0x180016827  mov     rax, [rax+30h]
0x18001682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016830  test    eax, eax
0x180016832  js      loc_180016A18
0x180016838  cmp     [rsp+310h+var_2C8], r12d
0x18001683d  jnz     loc_180016A55
0x180016843  cmp     ebx, 4
0x180016846  jz      loc_180016A18
0x18001684c  mov     [rsp+310h+var_2E0], r12
0x180016851  lea     rax, [rsp+310h+var_2E0]
0x180016856  mov     [rsp+310h+ppv], rax; ppv
0x18001685b  lea     r9, _GUID_559b1911_d3af_486e_b8bc_242b24df0114; riid
0x180016862  mov     r8d, r13d; dwClsContext
0x180016865  xor     edx, edx; pUnkOuter
0x180016867  lea     rcx, CLSID_InplaceShareEngine; rclsid
0x18001686e  call    cs:__imp_CoCreateInstance
0x180016874  test    eax, eax
0x180016876  js      loc_180016A01
0x18001687c  mov     [rsp+310h+psi], r12
0x180016881  mov     [rsp+310h+var_2C0], r12
0x180016886  mov     [rsp+310h+pidl], r12
0x18001688b  xor     edx, edx; Val
0x18001688d  mov     r8d, 24Ch; Size
0x180016893  lea     rcx, [rsp+310h+var_29C]; void *
0x180016898  call    memset_0
0x18001689d  mov     [rsp+310h+var_2A0], esi
0x1800168a1  lea     r9, [rsp+310h+pidl]
0x1800168a6  lea     rdx, [rsp+310h+var_2A0]
0x1800168ab  mov     rcx, rdi
0x1800168ae  call    ?SHSimpleIDListFromFindDataAndFlags@@YAJPEBGPEBU_WIN32_FIND_DATAW@@W4SIMPLE_IDLIST_FLAGS@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; SHSimpleIDListFromFindDataAndFlags(ushort const *,_WIN32_FIND_DATAW const *,SIMPLE_IDLIST_FLAGS,_ITEMIDLIST_ABSOLUTE * *)
0x1800168b3  test    eax, eax
0x1800168b5  js      loc_180016B1C
0x1800168bb  lea     r8, [rsp+310h+psi]; ppv
0x1800168c0  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800168c7  mov     rcx, [rsp+310h+pidl]; pidl
0x1800168cc  call    cs:__imp_SHCreateItemFromIDList
0x1800168d2  mov     ebx, eax
0x1800168d4  test    eax, eax
0x1800168d6  js      short loc_1800168F1
0x1800168d8  lea     r8, [rsp+310h+var_2C0]; ppv
0x1800168dd  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x1800168e4  mov     rcx, [rsp+310h+psi]; psi
0x1800168e9  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x1800168ef  mov     ebx, eax
0x1800168f1  mov     rcx, [rsp+310h+pidl]; pidl
0x1800168f6  call    cs:__imp_ILFree
0x1800168fc  test    ebx, ebx
0x1800168fe  js      loc_180016B1C
0x180016904  mov     r9, rdi; unsigned __int16 *
0x180016907  mov     r8, [rsp+310h+psi]; struct IShellItem *
0x18001690c  mov     rdx, [rsp+310h+var_2E0]; struct IShareEngine *
0x180016911  call    ?_IsSharedInplace@CShareCopyHook@@AEAAHPEAUIShareEngine@@PEAUIShellItem@@PEBG@Z; CShareCopyHook::_IsSharedInplace(IShareEngine *,IShellItem *,ushort const *)
0x180016916  test    eax, eax
0x180016918  jz      loc_1800169D3
0x18001691e  mov     rcx, [rsp+310h+var_2E0]
0x180016923  mov     rax, [rcx]
0x180016926  mov     rdx, [rsp+310h+var_2C0]
0x18001692b  mov     rax, [rax+20h]
0x18001692f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016934  test    eax, eax
0x180016936  js      loc_1800169D3
0x18001693c  mov     [rsp+310h+var_2A8], r12
0x180016941  mov     [rsp+310h+var_2B0], r12
0x180016946  mov     rcx, [rsp+310h+var_2E0]
0x18001694b  mov     rax, [rcx]
0x18001694e  lea     rdx, [rsp+310h+var_2A8]
0x180016953  mov     [rsp+310h+ppv], rdx
0x180016958  lea     r9, [rsp+310h+var_2B0]
0x18001695d  xor     r8d, r8d
0x180016960  xor     edx, edx
0x180016962  mov     rax, [rax+40h]
0x180016966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001696b  mov     [rsp+310h+pidl], r12
0x180016970  lea     rax, [rsp+310h+pidl]
0x180016975  mov     [rsp+310h+ppv], rax; ppv
0x18001697a  lea     r9, _GUID_065e74c3_6872_44cb_b894_cfec1284f23f; riid
0x180016981  mov     r8d, r13d; dwClsContext
0x180016984  xor     edx, edx; pUnkOuter
0x180016986  lea     rcx, CLSID_WSDPublisher; rclsid
0x18001698d  call    cs:__imp_CoCreateInstance
0x180016993  test    eax, eax
0x180016995  js      short loc_1800169BE
0x180016997  mov     rcx, [rsp+310h+pidl]
0x18001699c  mov     rax, [rcx]
0x18001699f  mov     rdx, [rsp+310h+var_2C0]
0x1800169a4  mov     rax, [rax+28h]
0x1800169a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ad  mov     rcx, [rsp+310h+pidl]
0x1800169b2  mov     rax, [rcx]
0x1800169b5  mov     rax, [rax+10h]
0x1800169b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169be  lea     rcx, [rsp+310h+var_2B0]
0x1800169c3  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800169c8  lea     rcx, [rsp+310h+var_2A8]
0x1800169cd  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x1800169d2  nop
0x1800169d3  mov     rcx, [rsp+310h+var_2C0]
0x1800169d8  test    rcx, rcx
0x1800169db  jz      short loc_1800169EA
0x1800169dd  mov     rax, [rcx]
0x1800169e0  mov     rax, [rax+10h]
0x1800169e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e9  nop
0x1800169ea  mov     rcx, [rsp+310h+psi]
0x1800169ef  test    rcx, rcx
0x1800169f2  jz      short loc_180016A01
0x1800169f4  mov     rax, [rcx]
0x1800169f7  mov     rax, [rax+10h]
0x1800169fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a00  nop
0x180016a01  mov     rcx, [rsp+310h+var_2E0]
0x180016a06  test    rcx, rcx
0x180016a09  jz      short loc_180016A18
0x180016a0b  mov     rax, [rcx]
0x180016a0e  mov     rax, [rax+10h]
0x180016a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a17  nop
0x180016a18  mov     rcx, [rsp+310h+var_2B8]
0x180016a1d  test    rcx, rcx
0x180016a20  jz      short loc_180016A2F
0x180016a22  mov     rdx, [rcx]
0x180016a25  mov     rax, [rdx+10h]
0x180016a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a2e  nop
0x180016a2f  mov     eax, r14d
0x180016a32  mov     rcx, [rbp+210h+var_50]
0x180016a39  xor     rcx, rsp; StackCookie
0x180016a3c  call    __security_check_cookie
0x180016a41  add     rsp, 2D8h
0x180016a48  pop     r15
0x180016a4a  pop     r14
0x180016a4c  pop     r13
0x180016a4e  pop     r12
0x180016a50  pop     rdi
0x180016a51  pop     rsi
0x180016a52  pop     rbx
0x180016a53  pop     rbp
0x180016a54  retn
0x180016a55  mov     [rsp+310h+pidl], r12
0x180016a5a  mov     [rsp+310h+var_2E0], r12
0x180016a5f  lea     rax, [rsp+310h+var_2E0]
0x180016a64  mov     [rsp+310h+ppv], rax; struct IShellItemArray **
0x180016a69  lea     r9, [rsp+310h+pidl]; struct IShellItem **
0x180016a6e  mov     r8d, esi; unsigned int
0x180016a71  mov     rdx, rdi; unsigned __int16 *
0x180016a74  call    ?_GetItemAndArrayForPath@CShareCopyHook@@AEAAJPEBGKPEAPEAUIShellItem@@PEAPEAUIShellItemArray@@@Z; CShareCopyHook::_GetItemAndArrayForPath(ushort const *,ulong,IShellItem * *,IShellItemArray * *)
0x180016a79  test    eax, eax
0x180016a7b  js      loc_180016B02
0x180016a81  mov     rax, [rsp+310h+var_2B8]
0x180016a86  mov     [rsp+310h+ppv], rax; struct IShareManager *
0x180016a8b  mov     r9, [rsp+310h+var_2E0]; struct IShellItemArray *
0x180016a90  mov     r8, rdi; unsigned __int16 *
0x180016a93  mov     rdx, r15; HWND
0x180016a96  call    ?_StopSharingSMB@CShareCopyHook@@AEAAJPEAUHWND__@@PEBGPEAUIShellItemArray@@PEAUIShareManager@@@Z; CShareCopyHook::_StopSharingSMB(HWND__ *,ushort const *,IShellItemArray *,IShareManager *)
0x180016a9b  cmp     eax, 800704C7h
0x180016aa0  jnz     short loc_180016AAA
0x180016aa2  mov     r14d, 2
0x180016aa8  jmp     short loc_180016B02
0x180016aaa  test    eax, eax
0x180016aac  js      short loc_180016B02
0x180016aae  mov     [rsp+310h+psi], r12
0x180016ab3  lea     rax, [rsp+310h+psi]
0x180016ab8  mov     [rsp+310h+ppv], rax; ppv
0x180016abd  lea     r9, _GUID_065e74c3_6872_44cb_b894_cfec1284f23f; riid
0x180016ac4  mov     r8d, r13d; dwClsContext
0x180016ac7  xor     edx, edx; pUnkOuter
0x180016ac9  lea     rcx, CLSID_WSDPublisher; rclsid
0x180016ad0  call    cs:__imp_CoCreateInstance
0x180016ad6  test    eax, eax
0x180016ad8  js      short loc_180016B02
0x180016ada  mov     rcx, [rsp+310h+psi]
0x180016adf  mov     rax, [rcx]
0x180016ae2  mov     rdx, [rsp+310h+var_2E0]
0x180016ae7  mov     rax, [rax+28h]
0x180016aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af0  mov     rcx, [rsp+310h+psi]
0x180016af5  mov     rax, [rcx]
0x180016af8  mov     rax, [rax+10h]
0x180016afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b01  nop
0x180016b02  lea     rcx, [rsp+310h+var_2E0]
0x180016b07  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180016b0c  nop
0x180016b0d  lea     rcx, [rsp+310h+pidl]
0x180016b12  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180016b17  jmp     loc_180016A18
0x180016b1c  lea     rcx, [rsp+310h+psi]
0x180016b21  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180016b26  lea     rcx, [rsp+310h+var_2C0]
0x180016b2b  jmp     loc_1800169CD
```
