# SyncProviderTelemetryHelpers::GetFilePath(IShellItem *,ushort * *)

- ea: `0x180043dd4`
- end: `0x180043fdd`
- name: `?GetFilePath@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAG@Z`
- size: `521`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180045e80`

## callees

- `0x180008900`
- `0x180019670`
- `0x180019f78`
- `0x1800214cc`
- `0x18003a4cc`
- `0x180043dd4`
- `0x180052cc4`
- `0x180053c14`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043ea9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043f9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043ea9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180043f9a`
- `SHELL32!SHCreateItemFromIDList` at `0x180043f32`
- `SHELL32!SHCreateItemFromIDList` at `0x180043f32`

## string_xrefs

- `0x180043e11`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180043e93`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180043ef3`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180043f45`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SyncProviderTelemetryHelpers::GetFilePath(struct IShellItem *a1, unsigned __int16 **a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  HRESULT v7; // eax
  int v9; // eax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-40h] BYREF
  int v11; // [rsp+30h] [rbp-30h]
  LPCITEMIDLIST *p_pidl; // [rsp+40h] [rbp-20h] BYREF
  struct _ITEMIDLIST_ABSOLUTE *v13; // [rsp+48h] [rbp-18h] BYREF
  char v14; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  void *ppv; // [rsp+88h] [rbp+28h] BYREF
  LPCITEMIDLIST pidl; // [rsp+90h] [rbp+30h] BYREF
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  v18 = 0;
  v4 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v18, a1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    LODWORD(ppv) = 0;
    *(_OWORD *)pvar = PKEY_Home_GraphFileType;
    v11 = 19;
    if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v18, pvar, &ppv) >= 0
      && (_DWORD)ppv )
    {
      LOWORD(pvar[0]) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v18 + 40LL))(
             v18,
             PKEY_DelegateIDList,
             pvar);
      v5 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEA,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v6,
          (int)pvar[0]);
LABEL_7:
        PropVariantClear(pvar);
        goto LABEL_17;
      }
      pidl = 0;
      p_pidl = &pidl;
      v13 = 0;
      v14 = 1;
      v5 = PropVariantToIDList((unsigned __int16 *)pvar, &v13);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v5,
          (int)pvar[0]);
LABEL_10:
        wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &pidl,
          0);
        goto LABEL_7;
      }
      ppv = 0;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      v7 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v5 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v7,
          (int)pvar[0]);
LABEL_13:
        Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
        goto LABEL_10;
      }
      v5 = (*(__int64 (__fastcall **)(void *, __int64, unsigned __int16 **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             2147844096LL,
             a2);
      if ( v5 < 0 )
        goto LABEL_13;
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&ppv);
      wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &pidl,
        0);
      PropVariantClear(pvar);
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned __int16 **))a1->lpVtbl->GetDisplayName)(
             a1,
             2147844096LL,
             a2);
      if ( v9 < 0 )
      {
        v5 = v9;
        goto LABEL_17;
      }
    }
    v5 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE1,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
    (const char *)(unsigned int)v4,
    (int)pvar[0]);
LABEL_17:
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043dd4  mov     [rsp-18h+arg_0], rbx
0x180043dd9  push    rbp
0x180043dda  push    rsi
0x180043ddb  push    rdi
0x180043ddc  mov     rbp, rsp
0x180043ddf  sub     rsp, 60h
0x180043de3  mov     rsi, rdx
0x180043de6  mov     rdi, rcx
0x180043de9  mov     qword ptr [rdx], 0
0x180043df0  mov     [rbp+arg_18], 0
0x180043df8  mov     rdx, rcx
0x180043dfb  lea     rcx, [rbp+arg_18]
0x180043dff  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180043e04  mov     ebx, eax
0x180043e06  test    eax, eax
0x180043e08  jns     short loc_180043E27
0x180043e0a  mov     rcx, [rbp+18h]; this
0x180043e0e  mov     r9d, eax; char *
0x180043e11  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180043e18  mov     edx, 0E1h; void *
0x180043e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043e22  jmp     loc_180043FA2
0x180043e27  mov     dword ptr [rbp+ppv], 0
0x180043e2e  movups  xmm0, cs:PKEY_Home_GraphFileType
0x180043e35  movaps  xmmword ptr [rbp+pvar], xmm0
0x180043e39  mov     eax, cs:dword_18007E7D8
0x180043e3f  mov     [rbp+var_30], eax
0x180043e42  lea     r8, [rbp+ppv]
0x180043e46  lea     rdx, [rbp+pvar]
0x180043e4a  lea     rcx, [rbp+arg_18]
0x180043e4e  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180043e53  test    eax, eax
0x180043e55  js      loc_180043FBD
0x180043e5b  cmp     dword ptr [rbp+ppv], 0
0x180043e5f  jz      loc_180043FBD
0x180043e65  xor     eax, eax
0x180043e67  mov     word ptr [rbp+pvar], ax
0x180043e6b  mov     rcx, [rbp+arg_18]
0x180043e6f  mov     rax, [rcx]
0x180043e72  lea     r8, [rbp+pvar]
0x180043e76  lea     rdx, PKEY_DelegateIDList
0x180043e7d  mov     rax, [rax+28h]
0x180043e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e86  mov     ebx, eax
0x180043e88  test    eax, eax
0x180043e8a  jns     short loc_180043EB4
0x180043e8c  mov     rcx, [rbp+18h]; this
0x180043e90  mov     r9d, eax; char *
0x180043e93  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180043e9a  mov     edx, 0EAh; void *
0x180043e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043ea4  nop
0x180043ea5  lea     rcx, [rbp+pvar]; pvar
0x180043ea9  call    cs:__imp_PropVariantClear
0x180043eaf  jmp     loc_180043FA2
0x180043eb4  mov     [rbp+pidl], 0
0x180043ebc  lea     rax, [rbp+pidl]
0x180043ec0  mov     [rbp+var_20], rax
0x180043ec4  mov     [rbp+var_18], 0
0x180043ecc  mov     [rbp+var_10], 1
0x180043ed0  lea     rdx, [rbp+var_18]
0x180043ed4  lea     rcx, [rbp+pvar]
0x180043ed8  call    PropVariantToIDList
0x180043edd  mov     ebx, eax
0x180043edf  lea     rcx, [rbp+var_20]
0x180043ee3  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180043ee8  test    ebx, ebx
0x180043eea  jns     short loc_180043F12
0x180043eec  mov     rcx, [rbp+18h]; this
0x180043ef0  mov     r9d, ebx; char *
0x180043ef3  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180043efa  mov     edx, 0ECh; void *
0x180043eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043f04  nop
0x180043f05  xor     edx, edx
0x180043f07  lea     rcx, [rbp+pidl]
0x180043f0b  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180043f10  jmp     short loc_180043EA5
0x180043f12  mov     [rbp+ppv], 0
0x180043f1a  lea     rcx, [rbp+ppv]
0x180043f1e  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043f23  lea     r8, [rbp+ppv]; ppv
0x180043f27  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180043f2e  mov     rcx, [rbp+pidl]; pidl
0x180043f32  call    cs:__imp_SHCreateItemFromIDList
0x180043f38  mov     ebx, eax
0x180043f3a  test    eax, eax
0x180043f3c  jns     short loc_180043F62
0x180043f3e  mov     rcx, [rbp+18h]; this
0x180043f42  mov     r9d, eax; char *
0x180043f45  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180043f4c  mov     edx, 0EEh; void *
0x180043f51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043f56  nop
0x180043f57  lea     rcx, [rbp+ppv]
0x180043f5b  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043f60  jmp     short loc_180043F05
0x180043f62  mov     rcx, [rbp+ppv]
0x180043f66  mov     rax, [rcx]
0x180043f69  mov     r8, rsi
0x180043f6c  mov     edx, 80058000h
0x180043f71  mov     rax, [rax+28h]
0x180043f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f7a  mov     ebx, eax
0x180043f7c  lea     rcx, [rbp+ppv]
0x180043f80  test    eax, eax
0x180043f82  js      short loc_180043F5B
0x180043f84  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043f89  nop
0x180043f8a  xor     edx, edx
0x180043f8c  lea     rcx, [rbp+pidl]
0x180043f90  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x180043f95  nop
0x180043f96  lea     rcx, [rbp+pvar]; pvar
0x180043f9a  call    cs:__imp_PropVariantClear
0x180043fa0  xor     ebx, ebx
0x180043fa2  lea     rcx, [rbp+arg_18]
0x180043fa6  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180043fab  mov     eax, ebx
0x180043fad  mov     rbx, [rsp+60h+arg_0]
0x180043fb5  add     rsp, 60h
0x180043fb9  pop     rdi
0x180043fba  pop     rsi
0x180043fbb  pop     rbp
0x180043fbc  retn
0x180043fbd  mov     rax, [rdi]
0x180043fc0  mov     r8, rsi
0x180043fc3  mov     edx, 80058000h
0x180043fc8  mov     rcx, rdi
0x180043fcb  mov     rax, [rax+28h]
0x180043fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fd4  test    eax, eax
0x180043fd6  jns     short loc_180043FA0
0x180043fd8  mov     ebx, eax
0x180043fda  jmp     short loc_180043FA2
```
