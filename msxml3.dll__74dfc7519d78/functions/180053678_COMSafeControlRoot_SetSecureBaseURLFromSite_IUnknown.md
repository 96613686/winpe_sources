# COMSafeControlRoot::SetSecureBaseURLFromSite(IUnknown *)

- ea: `0x180053678`
- end: `0x180053ae8`
- name: `?SetSecureBaseURLFromSite@COMSafeControlRoot@@QEAAJPEAUIUnknown@@@Z`
- size: `1136`
- prototype: `__int64 __fastcall(COMSafeControlRoot *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005356c`
- `0x1800687e0`

## callees

- `0x180012000`
- `0x180014214`
- `0x18001ecd0`
- `0x1800222c0`
- `0x180053678`
- `0x18005f9b8`
- `0x180064034`
- `0x180102d20`
- `0x180102db0`
- `0x180107010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800539dc`
- `msvcrt!_resetstkoflw` at `0x1800539dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053a2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180053a2f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800539ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053a5b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800539ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053a5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800537f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800539b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800539b9`

## pseudocode

```c
__int64 __fastcall COMSafeControlRoot::SetSecureBaseURLFromSite(struct IUnknown **this, struct IUnknown *a2)
{
  int v4; // edi
  struct String *v5; // rax
  struct String *v6; // rdx
  struct String *v7; // rax
  struct String *v8; // rax
  BSTR bstrString; // [rsp+38h] [rbp-10B0h] BYREF
  struct IUnknown *v11; // [rsp+40h] [rbp-10A8h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-10A0h] BYREF
  struct IUnknown *v13; // [rsp+50h] [rbp-1098h] BYREF
  struct IUnknown *v14; // [rsp+58h] [rbp-1090h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-1088h] BYREF
  struct IUnknown *v16; // [rsp+68h] [rbp-1080h] BYREF
  struct IUnknown *v17; // [rsp+70h] [rbp-1078h] BYREF
  struct IUnknown *v18; // [rsp+78h] [rbp-1070h] BYREF
  unsigned __int16 Src[2088]; // [rsp+80h] [rbp-1068h] BYREF

  v16 = 0;
  v17 = 0;
  v11 = 0;
  v18 = 0;
  v14 = 0;
  v13 = 0;
  bstrString = 0;
  pv = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IXMLDOMDocument,
         &v13) < 0 )
  {
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IOleClientSite,
           &v16) >= 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, struct IUnknown **))v16->lpVtbl[1].AddRef)(
             v16,
             1,
             1,
             &v17);
      if ( v4 >= 0 )
      {
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, LPVOID *))v17->lpVtbl[6].Release)(
               v17,
               0,
               0,
               &pv);
        if ( v4 >= 0 )
        {
          if ( pv )
          {
            v7 = String::newString((const unsigned __int16 *)pv);
            assign(this + 4, v7);
            CoTaskMemFree(pv);
          }
        }
      }
      goto LABEL_23;
    }
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IServiceProvider,
           &v11);
    if ( v4 < 0 )
      goto LABEL_23;
    if ( ((int (__fastcall *)(struct IUnknown *, __int64 *, GUID *, struct IUnknown **))v11->lpVtbl[1].QueryInterface)(
           v11,
           &UUID_MSXMLSecureBaseUrl,
           &IID_IStream,
           &v18) < 0 )
    {
      v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, GUID *, struct IUnknown **))v11->lpVtbl[1].QueryInterface)(
             v11,
             &IID_IInternetHostSecurityManager,
             &IID_IXMLDOMDocument,
             &v13);
      if ( v4 < 0 )
      {
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, SID *, GUID *, struct IUnknown **))v11->lpVtbl[1].QueryInterface)(
               v11,
               &SID_SContainerDispatch,
               &IID_IHTMLDocument2,
               &v14);
        if ( v4 < 0 )
        {
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, GUID *, struct IUnknown **))v11->lpVtbl[1].QueryInterface)(
                 v11,
                 &IID_IInternetHostSecurityManager,
                 &IID_IHTMLDocument2,
                 &v14);
          if ( v4 < 0 )
            goto LABEL_23;
        }
        if ( !v14 )
          goto LABEL_23;
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v14->lpVtbl[13].AddRef)(v14, &bstrString);
        if ( v4 < 0 )
          goto LABEL_23;
      }
      else
      {
        if ( !v13 )
          goto LABEL_23;
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v13->lpVtbl[20].AddRef)(v13, &bstrString);
        if ( v4 < 0 )
          goto LABEL_23;
      }
      v6 = String::newString(bstrString);
      goto LABEL_22;
    }
    v12 = 0;
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int16 *, __int64, unsigned int *))v18->lpVtbl[1].QueryInterface)(
           v18,
           Src,
           4168,
           &v12);
    if ( v4 >= 0 )
    {
      v8 = String::newString(Src, v12 >> 1);
      assign(this + 4, v8);
    }
  }
  else
  {
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))v13->lpVtbl[20].AddRef)(v13, &bstrString);
    if ( v4 >= 0 )
    {
      v5 = String::newString(bstrString);
      assign(this + 3, v5);
      v6 = (struct String *)this[3];
LABEL_22:
      assign(this + 4, v6);
      SysFreeString(bstrString);
    }
  }
LABEL_23:
  release(&v16);
  release(&v17);
  release(&v11);
  release(&v18);
  release(&v14);
  release(&v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180053678  mov     [rsp+arg_10], rbx
0x18005367d  mov     [rsp+arg_18], rsi
0x180053682  push    rdi
0x180053683  mov     eax, 10E0h
0x180053688  call    _alloca_probe
0x18005368d  sub     rsp, rax
0x180053690  mov     rax, cs:__security_cookie
0x180053697  xor     rax, rsp
0x18005369a  mov     [rsp+10E8h+var_18], rax
0x1800536a2  mov     rbx, rdx
0x1800536a5  mov     rsi, rcx
0x1800536a8  mov     [rsp+10E8h+var_1080], 0
0x1800536b1  mov     [rsp+10E8h+var_1078], 0
0x1800536ba  mov     [rsp+10E8h+var_10A8], 0
0x1800536c3  mov     [rsp+10E8h+var_1070], 0
0x1800536cc  mov     [rsp+10E8h+var_1090], 0
0x1800536d5  mov     [rsp+10E8h+var_1098], 0
0x1800536de  mov     [rsp+10E8h+bstrString], 0
0x1800536e7  mov     [rsp+10E8h+pv], 0
0x1800536f0  mov     rax, [rdx]
0x1800536f3  lea     r8, [rsp+10E8h+var_1098]
0x1800536f8  lea     rdx, IID_IXMLDOMDocument
0x1800536ff  mov     rcx, rbx
0x180053702  mov     rax, [rax]
0x180053705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005370a  test    eax, eax
0x18005370c  js      short loc_180053754
0x18005370e  mov     rcx, [rsp+10E8h+var_1098]
0x180053713  mov     rax, [rcx]
0x180053716  lea     rdx, [rsp+10E8h+bstrString]
0x18005371b  mov     rax, [rax+1E8h]
0x180053722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053727  mov     edi, eax
0x180053729  mov     [rsp+10E8h+var_10B8], eax
0x18005372d  test    eax, eax
0x18005372f  js      loc_180053A85
0x180053735  mov     rcx, [rsp+10E8h+bstrString]; unsigned __int16 *
0x18005373a  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x18005373f  mov     rdx, rax; void *
0x180053742  lea     rcx, [rsi+18h]; struct IUnknown **
0x180053746  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x18005374b  mov     rdx, [rsi+18h]
0x18005374f  jmp     loc_1800539AB
0x180053754  mov     rax, [rbx]
0x180053757  lea     r8, [rsp+10E8h+var_1080]
0x18005375c  lea     rdx, IID_IOleClientSite
0x180053763  mov     rcx, rbx
0x180053766  mov     rax, [rax]
0x180053769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005376e  test    eax, eax
0x180053770  js      loc_1800537FD
0x180053776  mov     rcx, [rsp+10E8h+var_1080]
0x18005377b  mov     rax, [rcx]
0x18005377e  lea     r9, [rsp+10E8h+var_1078]
0x180053783  mov     edx, 1
0x180053788  mov     r8d, edx
0x18005378b  mov     rax, [rax+20h]
0x18005378f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053794  mov     edi, eax
0x180053796  mov     [rsp+10E8h+var_10B8], eax
0x18005379a  test    eax, eax
0x18005379c  js      loc_180053A85
0x1800537a2  mov     rcx, [rsp+10E8h+var_1078]
0x1800537a7  mov     rax, [rcx]
0x1800537aa  lea     r9, [rsp+10E8h+pv]
0x1800537af  xor     r8d, r8d
0x1800537b2  xor     edx, edx
0x1800537b4  mov     rax, [rax+0A0h]
0x1800537bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537c0  mov     edi, eax
0x1800537c2  mov     [rsp+10E8h+var_10B8], eax
0x1800537c6  test    eax, eax
0x1800537c8  js      loc_180053A85
0x1800537ce  mov     rcx, [rsp+10E8h+pv]; unsigned __int16 *
0x1800537d3  test    rcx, rcx
0x1800537d6  jz      loc_1800539BF
0x1800537dc  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800537e1  lea     rcx, [rsi+20h]; struct IUnknown **
0x1800537e5  mov     rdx, rax; void *
0x1800537e8  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800537ed  mov     rcx, [rsp+10E8h+pv]; pv
0x1800537f2  call    cs:__imp_CoTaskMemFree
0x1800537f8  jmp     loc_1800539BF
0x1800537fd  mov     rax, [rbx]
0x180053800  lea     r8, [rsp+10E8h+var_10A8]
0x180053805  lea     rdx, IID_IServiceProvider
0x18005380c  mov     rcx, rbx
0x18005380f  mov     rax, [rax]
0x180053812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053817  mov     edi, eax
0x180053819  mov     [rsp+10E8h+var_10B8], eax
0x18005381d  test    eax, eax
0x18005381f  js      loc_180053A85
0x180053825  mov     rcx, [rsp+10E8h+var_10A8]
0x18005382a  mov     rax, [rcx]
0x18005382d  lea     r9, [rsp+10E8h+var_1070]
0x180053832  lea     r8, IID_IStream
0x180053839  lea     rdx, UUID_MSXMLSecureBaseUrl
0x180053840  mov     rax, [rax+18h]
0x180053844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053849  mov     [rsp+10E8h+var_10B8], eax
0x18005384d  test    eax, eax
0x18005384f  js      short loc_1800538AF
0x180053851  mov     [rsp+10E8h+var_10A0], 0
0x180053859  mov     rcx, [rsp+10E8h+var_1070]
0x18005385e  mov     rax, [rcx]
0x180053861  lea     r9, [rsp+10E8h+var_10A0]
0x180053866  mov     r8d, 1048h
0x18005386c  lea     rdx, [rsp+10E8h+Src]
0x180053874  mov     rax, [rax+18h]
0x180053878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005387d  mov     edi, eax
0x18005387f  mov     [rsp+10E8h+var_10B8], eax
0x180053883  test    eax, eax
0x180053885  js      loc_180053A85
0x18005388b  mov     edx, [rsp+10E8h+var_10A0]
0x18005388f  shr     edx, 1; int
0x180053891  lea     rcx, [rsp+10E8h+Src]; Src
0x180053899  call    ?newString@String@@SAPEAV1@PEBGH@Z; String::newString(ushort const *,int)
0x18005389e  lea     rcx, [rsi+20h]; struct IUnknown **
0x1800538a2  mov     rdx, rax; void *
0x1800538a5  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800538aa  jmp     loc_1800539BF
0x1800538af  mov     rcx, [rsp+10E8h+var_10A8]
0x1800538b4  mov     rax, [rcx]
0x1800538b7  lea     r9, [rsp+10E8h+var_1098]
0x1800538bc  lea     r8, IID_IXMLDOMDocument
0x1800538c3  lea     rdx, IID_IInternetHostSecurityManager
0x1800538ca  mov     rax, [rax+18h]
0x1800538ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538d3  mov     edi, eax
0x1800538d5  mov     [rsp+10E8h+var_10B8], eax
0x1800538d9  test    eax, eax
0x1800538db  js      short loc_180053912
0x1800538dd  mov     rcx, [rsp+10E8h+var_1098]
0x1800538e2  test    rcx, rcx
0x1800538e5  jz      loc_1800539BF
0x1800538eb  mov     rax, [rcx]
0x1800538ee  lea     rdx, [rsp+10E8h+bstrString]
0x1800538f3  mov     rax, [rax+1E8h]
0x1800538fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800538ff  mov     edi, eax
0x180053901  mov     [rsp+10E8h+var_10B8], eax
0x180053905  test    eax, eax
0x180053907  jns     loc_18005399E
0x18005390d  jmp     loc_180053A85
0x180053912  mov     rcx, [rsp+10E8h+var_10A8]
0x180053917  mov     rax, [rcx]
0x18005391a  lea     r9, [rsp+10E8h+var_1090]
0x18005391f  lea     r8, IID_IHTMLDocument2
0x180053926  lea     rdx, SID_SContainerDispatch
0x18005392d  mov     rax, [rax+18h]
0x180053931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053936  mov     edi, eax
0x180053938  mov     [rsp+10E8h+var_10B8], eax
0x18005393c  test    eax, eax
0x18005393e  jns     short loc_180053972
0x180053940  mov     rcx, [rsp+10E8h+var_10A8]
0x180053945  mov     rax, [rcx]
0x180053948  lea     r9, [rsp+10E8h+var_1090]
0x18005394d  lea     r8, IID_IHTMLDocument2
0x180053954  lea     rdx, IID_IInternetHostSecurityManager
0x18005395b  mov     rax, [rax+18h]
0x18005395f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053964  mov     edi, eax
0x180053966  mov     [rsp+10E8h+var_10B8], eax
0x18005396a  test    eax, eax
0x18005396c  js      loc_180053A85
0x180053972  mov     rcx, [rsp+10E8h+var_1090]
0x180053977  test    rcx, rcx
0x18005397a  jz      short loc_1800539BF
0x18005397c  mov     rax, [rcx]
0x18005397f  lea     rdx, [rsp+10E8h+bstrString]
0x180053984  mov     rax, [rax+140h]
0x18005398b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053990  mov     edi, eax
0x180053992  mov     [rsp+10E8h+var_10B8], eax
0x180053996  test    eax, eax
0x180053998  js      loc_180053A85
0x18005399e  mov     rcx, [rsp+10E8h+bstrString]; unsigned __int16 *
0x1800539a3  call    ?newString@String@@SAPEAV1@PEBG@Z; String::newString(ushort const *)
0x1800539a8  mov     rdx, rax; void *
0x1800539ab  lea     rcx, [rsi+20h]; struct IUnknown **
0x1800539af  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1800539b4  mov     rcx, [rsp+10E8h+bstrString]; bstrString
0x1800539b9  call    cs:__imp_SysFreeString
0x1800539bf  jmp     loc_180053A85
0x1800539c4  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x1800539ca  call    cs:__imp_TlsGetValue
0x1800539d0  mov     rbx, rax
0x1800539d3  cmp     dword ptr [rax+54h], 0C00000FDh
0x1800539da  jnz     short loc_180053A55
0x1800539dc  call    cs:__imp__resetstkoflw
0x1800539e2  test    eax, eax
0x1800539e4  jnz     short loc_180053A37
0x1800539e6  mov     rcx, cs:?g_pMutexGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexGC
0x1800539ed  test    rcx, rcx
0x1800539f0  jz      short loc_180053A04
0x1800539f2  cmp     [rcx+50h], rbx
0x1800539f6  jnz     short loc_180053A04
0x1800539f8  mov     rax, [rcx]
0x1800539fb  mov     rax, [rax+20h]
0x1800539ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a04  mov     rcx, cs:?g_pMutexFullGC@@3PEAVCSMutex@@EA; CSMutex * g_pMutexFullGC
0x180053a0b  test    rcx, rcx
0x180053a0e  jz      short loc_180053A22
0x180053a10  cmp     [rcx+50h], rbx
0x180053a14  jnz     short loc_180053A22
0x180053a16  mov     rax, [rcx]
0x180053a19  mov     rax, [rax+20h]
0x180053a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a22  xor     r9d, r9d; lpArguments
0x180053a25  xor     r8d, r8d; nNumberOfArguments
0x180053a28  xor     edx, edx; dwExceptionFlags
0x180053a2a  mov     ecx, 0C00000FDh; dwExceptionCode
0x180053a2f  call    cs:__imp_RaiseException
0x180053a35  jmp     short loc_180053A55
0x180053a37  mov     rax, [rbx+60h]
0x180053a3b  mov     [rbx+68h], rax
0x180053a3f  lea     rax, ?s_cexpOutOfStack@Exception@@2V_CodebaseException@@B; _CodebaseException const Exception::s_cexpOutOfStack
0x180053a46  mov     [rbx+60h], rax
0x180053a4a  mov     dword ptr [rbx+54h], 800703E9h
0x180053a51  mov     byte ptr [rbx+78h], 0
0x180053a55  mov     ecx, cs:?g_dwTlsIndex@@3KA; dwTlsIndex
0x180053a5b  call    cs:__imp_TlsGetValue
0x180053a61  mov     rcx, [rax+60h]; struct Exception *
0x180053a65  call    ?setErrorInfo@_dispatchImpl@@SAPEAVException@@PEAV2@@Z; _dispatchImpl::setErrorInfo(Exception *)
0x180053a6a  mov     rdx, rax
0x180053a6d  mov     rcx, [rax]
0x180053a70  mov     rax, [rcx+80h]
0x180053a77  mov     rcx, rdx
0x180053a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a7f  mov     edi, eax
0x180053a81  mov     [rsp+10E8h+var_10B8], eax
0x180053a85  lea     rcx, [rsp+10E8h+var_1080]; struct IUnknown **
0x180053a8a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053a8f  lea     rcx, [rsp+10E8h+var_1078]; struct IUnknown **
0x180053a94  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053a99  lea     rcx, [rsp+10E8h+var_10A8]; struct IUnknown **
0x180053a9e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053aa3  lea     rcx, [rsp+10E8h+var_1070]; struct IUnknown **
0x180053aa8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053aad  lea     rcx, [rsp+10E8h+var_1090]; struct IUnknown **
0x180053ab2  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053ab7  lea     rcx, [rsp+10E8h+var_1098]; struct IUnknown **
0x180053abc  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180053ac1  mov     eax, edi
0x180053ac3  mov     rcx, [rsp+10E8h+var_18]
0x180053acb  xor     rcx, rsp; StackCookie
0x180053ace  call    __security_check_cookie
0x180053ad3  lea     r11, [rsp+10E8h+var_8]
0x180053adb  mov     rbx, [r11+20h]
0x180053adf  mov     rsi, [r11+28h]
0x180053ae3  mov     rsp, r11
0x180053ae6  pop     rdi
0x180053ae7  retn
0x180103974  push    rbp
0x180103976  sub     rsp, 30h
0x18010397a  mov     rbp, rdx
0x18010397d  xor     edx, edx; bool
0x18010397f  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@_N@Z
0x180103984  nop
0x180103985  add     rsp, 30h
0x180103989  pop     rbp
0x18010398a  retn
```
