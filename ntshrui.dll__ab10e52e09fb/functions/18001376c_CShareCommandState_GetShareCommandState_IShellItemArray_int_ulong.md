# CShareCommandState::_GetShareCommandState(IShellItemArray *,int,ulong *)

- ea: `0x18001376c`
- end: `0x18001399c`
- name: `?_GetShareCommandState@CShareCommandState@@AEAAJPEAUIShellItemArray@@HPEAK@Z`
- size: `560`
- prototype: `__int64 __fastcall(CShareCommandState *__hidden this, struct IShellItemArray *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180013c80`

## callees

- `0x18001376c`
- `0x1800139a4`
- `0x180013b3c`
- `0x1800143ec`
- `0x18001c4a8`
- `0x1800254e0`
- `0x180073de0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013913`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013913`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001389e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001389e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800138cd`
- `SHCORE!IUnknown_QueryService` at `0x1800137f2`
- `SHCORE!IUnknown_QueryService` at `0x1800137f2`
- `ADVAPI32!RegEnumKeyW` at `0x1800138b9`
- `ADVAPI32!RegEnumKeyW` at `0x1800138b9`

## string_xrefs

- `0x180013890`: `ShareCommands\shell`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CShareCommandState::_GetShareCommandState(
        IUnknown **this,
        struct IShellItemArray *a2,
        int a3,
        unsigned int *a4)
{
  unsigned int v7; // edx
  HRESULT v8; // ebx
  CShareCommandState *v9; // rcx
  const unsigned __int16 *v10; // rcx
  int v11; // edi
  void *ppvOut; // [rsp+30h] [rbp-99h] BYREF
  struct IShellItemArray *v14; // [rsp+38h] [rbp-91h] BYREF
  struct IShellItemArray *v15[2]; // [rsp+40h] [rbp-89h] BYREF
  WCHAR Name[80]; // [rsp+50h] [rbp-79h] BYREF

  *a4 = 2;
  v14 = 0;
  v15[0] = 0;
  if ( a2 )
  {
    v8 = ((__int64 (__fastcall *)(struct IShellItemArray *, GUID *, struct IShellItemArray **))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
           v15);
  }
  else
  {
    ppvOut = 0;
    v8 = IUnknown_QueryService(this[1], &IID_IFolderView, &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce, &ppvOut);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(void *, GUID *, struct IShellItemArray **))(*(_QWORD *)ppvOut + 40LL))(
             ppvOut,
             &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
             v15);
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppvOut);
  }
  if ( v8 >= 0 )
  {
    v8 = _TruncateShellItemArray(v15[0], v7, &v14);
    if ( v8 >= 0
      && !(unsigned int)CShareCommandState::_IsDesktop(v9, v14)
      && (unsigned int)ShellItemArraySupportsSyncOrShare(v14, a2 == 0) )
    {
      ppvOut = 0;
      if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, L"ShareCommands\\shell", 0, 8u, (PHKEY)&ppvOut) )
        goto LABEL_29;
      v11 = 0;
      if ( !RegEnumKeyW((HKEY)ppvOut, 0, Name, 0x50u) )
      {
        *a4 = 0;
        v11 = 1;
      }
      RegCloseKey((HKEY)ppvOut);
      if ( !v11 )
      {
LABEL_29:
        if ( IsServiceRunningOrStartPending(v10) )
        {
          if ( a3 )
          {
            ppvOut = 0;
            v8 = CoCreateInstance(
                   &CLSID_SharingConfigurationManager,
                   0,
                   1u,
                   &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2,
                   &ppvOut);
            if ( v8 >= 0
              && !(*(unsigned int (__fastcall **)(void *, struct IShellItemArray *))(*(_QWORD *)ppvOut + 24LL))(
                    ppvOut,
                    v14) )
            {
              *a4 = 0;
            }
            if ( ppvOut )
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
          }
          else
          {
            v8 = -2147483638;
          }
        }
      }
    }
  }
  if ( v15[0] )
    ((void (__fastcall *)(struct IShellItemArray *))v15[0]->lpVtbl->Release)(v15[0]);
  if ( v14 )
    ((void (__fastcall *)(struct IShellItemArray *))v14->lpVtbl->Release)(v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001376c  push    rbp
0x18001376e  push    rbx
0x18001376f  push    rsi
0x180013770  push    rdi
0x180013771  push    r14
0x180013773  lea     rbp, [rsp-37h]
0x180013778  sub     rsp, 100h
0x18001377f  mov     rax, cs:__security_cookie
0x180013786  xor     rax, rsp
0x180013789  mov     [rbp+57h+var_30], rax
0x18001378d  mov     rsi, r9
0x180013790  mov     r14d, r8d
0x180013793  mov     rdi, rdx
0x180013796  mov     dword ptr [r9], 2
0x18001379d  mov     [rsp+120h+var_E8], 0
0x1800137a6  mov     [rsp+120h+var_E0], 0
0x1800137af  test    rdx, rdx
0x1800137b2  jz      short loc_1800137D2
0x1800137b4  mov     rax, [rdx]
0x1800137b7  lea     r8, [rsp+120h+var_E0]
0x1800137bc  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x1800137c3  mov     rcx, rdi
0x1800137c6  mov     rax, [rax]
0x1800137c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ce  mov     ebx, eax
0x1800137d0  jmp     short loc_180013827
0x1800137d2  mov     [rsp+120h+ppvOut], 0
0x1800137db  lea     r9, [rsp+120h+ppvOut]; ppvOut
0x1800137e0  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x1800137e7  lea     rdx, IID_IFolderView; guidService
0x1800137ee  mov     rcx, [rcx+8]; punk
0x1800137f2  call    cs:__imp_IUnknown_QueryService
0x1800137f8  mov     ebx, eax
0x1800137fa  test    eax, eax
0x1800137fc  js      short loc_18001381D
0x1800137fe  mov     rcx, [rsp+120h+ppvOut]
0x180013803  mov     rax, [rcx]
0x180013806  lea     r8, [rsp+120h+var_E0]
0x18001380b  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180013812  mov     rax, [rax+28h]
0x180013816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001381b  mov     ebx, eax
0x18001381d  lea     rcx, [rsp+120h+ppvOut]
0x180013822  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180013827  test    ebx, ebx
0x180013829  js      loc_180013952
0x18001382f  lea     r8, [rsp+120h+var_E8]; struct IShellItemArray **
0x180013834  mov     rcx, [rsp+120h+var_E0]; struct IShellItemArray *
0x180013839  call    ?_TruncateShellItemArray@@YAJPEAUIShellItemArray@@KPEAPEAU1@@Z; _TruncateShellItemArray(IShellItemArray *,ulong,IShellItemArray * *)
0x18001383e  mov     ebx, eax
0x180013840  test    eax, eax
0x180013842  js      loc_180013952
0x180013848  mov     rdx, [rsp+120h+var_E8]; struct IShellItemArray *
0x18001384d  call    ?_IsDesktop@CShareCommandState@@AEAAHPEAUIShellItemArray@@@Z; CShareCommandState::_IsDesktop(IShellItemArray *)
0x180013852  test    eax, eax
0x180013854  jnz     loc_180013952
0x18001385a  xor     edx, edx
0x18001385c  test    rdi, rdi
0x18001385f  setz    dl
0x180013862  mov     rcx, [rsp+120h+var_E8]
0x180013867  call    ShellItemArraySupportsSyncOrShare
0x18001386c  test    eax, eax
0x18001386e  jz      loc_180013952
0x180013874  mov     [rsp+120h+ppvOut], 0
0x18001387d  lea     rax, [rsp+120h+ppvOut]
0x180013882  mov     [rsp+120h+phkResult], rax; phkResult
0x180013887  mov     r9d, 8; samDesired
0x18001388d  xor     r8d, r8d; ulOptions
0x180013890  lea     rdx, aSharecommandsS; "ShareCommands\\shell"
0x180013897  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001389e  call    cs:__imp_RegOpenKeyExW
0x1800138a4  test    eax, eax
0x1800138a6  jnz     short loc_1800138D7
0x1800138a8  xor     edi, edi
0x1800138aa  lea     r9d, [rax+50h]; cchName
0x1800138ae  lea     r8, [rbp+57h+Name]; lpName
0x1800138b2  xor     edx, edx; dwIndex
0x1800138b4  mov     rcx, [rsp+120h+ppvOut]; hKey
0x1800138b9  call    cs:__imp_RegEnumKeyW
0x1800138bf  test    eax, eax
0x1800138c1  jnz     short loc_1800138C8
0x1800138c3  mov     [rsi], edi
0x1800138c5  lea     edi, [rax+1]
0x1800138c8  mov     rcx, [rsp+120h+ppvOut]; hKey
0x1800138cd  call    cs:__imp_RegCloseKey
0x1800138d3  test    edi, edi
0x1800138d5  jnz     short loc_180013952
0x1800138d7  call    ?IsServiceRunningOrStartPending@@YA_NPEBG@Z; IsServiceRunningOrStartPending(ushort const *)
0x1800138dc  test    al, al
0x1800138de  jz      short loc_180013952
0x1800138e0  test    r14d, r14d
0x1800138e3  jnz     short loc_1800138EC
0x1800138e5  mov     ebx, 8000000Ah
0x1800138ea  jmp     short loc_180013952
0x1800138ec  mov     [rsp+120h+ppvOut], 0
0x1800138f5  lea     rax, [rsp+120h+ppvOut]
0x1800138fa  mov     [rsp+120h+phkResult], rax; ppv
0x1800138ff  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x180013906  xor     edx, edx; pUnkOuter
0x180013908  lea     r8d, [rdx+1]; dwClsContext
0x18001390c  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x180013913  call    cs:__imp_CoCreateInstance
0x180013919  mov     ebx, eax
0x18001391b  test    eax, eax
0x18001391d  js      short loc_18001393B
0x18001391f  mov     rcx, [rsp+120h+ppvOut]
0x180013924  mov     r8, [rcx]
0x180013927  mov     rdx, [rsp+120h+var_E8]
0x18001392c  mov     rax, [r8+18h]
0x180013930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013935  test    eax, eax
0x180013937  jnz     short loc_18001393B
0x180013939  mov     [rsi], eax
0x18001393b  mov     rcx, [rsp+120h+ppvOut]
0x180013940  test    rcx, rcx
0x180013943  jz      short loc_180013952
0x180013945  mov     rax, [rcx]
0x180013948  mov     rax, [rax+10h]
0x18001394c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013951  nop
0x180013952  mov     rcx, [rsp+120h+var_E0]
0x180013957  test    rcx, rcx
0x18001395a  jz      short loc_180013969
0x18001395c  mov     rax, [rcx]
0x18001395f  mov     rax, [rax+10h]
0x180013963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013968  nop
0x180013969  mov     rcx, [rsp+120h+var_E8]
0x18001396e  test    rcx, rcx
0x180013971  jz      short loc_180013980
0x180013973  mov     rax, [rcx]
0x180013976  mov     rax, [rax+10h]
0x18001397a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001397f  nop
0x180013980  mov     eax, ebx
0x180013982  mov     rcx, [rbp+57h+var_30]
0x180013986  xor     rcx, rsp; StackCookie
0x180013989  call    __security_check_cookie
0x18001398e  add     rsp, 100h
0x180013995  pop     r14
0x180013997  pop     rdi
0x180013998  pop     rsi
0x180013999  pop     rbx
0x18001399a  pop     rbp
0x18001399b  retn
```
