# EnrollEngine::BeginEnroll(MDMEnrollInfoTag *,void * *,_GUID *)

- ea: `0x180036220`
- end: `0x180036658`
- name: `?BeginEnroll@EnrollEngine@@UEAAJPEAUMDMEnrollInfoTag@@PEAPEAXPEAU_GUID@@@Z`
- size: `1080`
- prototype: `__int64 __fastcall(EnrollEngine *__hidden this, struct MDMEnrollInfoTag *, void **, GUID *pguid)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180001058`
- `0x180001140`
- `0x1800071c0`
- `0x18000e0d0`
- `0x18000e508`
- `0x18001ab40`
- `0x18002e1a0`
- `0x180033dc8`
- `0x180036220`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800362d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800362d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036318`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800363b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036318`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800363b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800364d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800364d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036508`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnrollEngine::BeginEnroll(EnrollEngine *this, struct MDMEnrollInfoTag *a2, void **a3, GUID *pguid)
{
  void **v5; // rdi
  int v8; // r14d
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // esi
  LSTATUS v12; // eax
  signed int v13; // ebx
  LSTATUS ValueW; // eax
  LSTATUS v15; // eax
  BOOL v16; // edi
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int pvData; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  int v30; // [rsp+50h] [rbp-29h] BYREF
  __int64 v31; // [rsp+58h] [rbp-21h] BYREF
  HKEY *v32; // [rsp+60h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-9h] BYREF
  DWORD v35; // [rsp+74h] [rbp-5h] BYREF
  HKEY hkey[2]; // [rsp+78h] [rbp-1h] BYREF

  v5 = a3;
  v32 = (HKEY *)a3;
  v8 = 0;
  v29 = 0;
  v31 = 0;
  v9 = ((__int64 (__fastcall *)(void ***, __int64, __int64 *))off_1800AF740[4])(&off_1800AF740, 222306401, &v31);
  v10 = v9;
  v11 = 1;
  if ( v9 >= 0 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 24LL))(v31, &v29);
    if ( v17 != 1 )
    {
      v18 = 63;
      pvData = 63;
      v19 = v29;
      if ( !v17 && v29 )
      {
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v29 + 56LL))(v29, &pvData);
        v19 = v29;
        v18 = pvData;
      }
      *(_OWORD *)hkey = 0;
      if ( v18 != 5 && (*(int (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v19 + 24LL))(v19, hkey) >= 0 )
      {
        if ( (unsigned int)dword_1800AF3E8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800AF3E8, 0x800000000000LL) )
        {
          v32 = hkey;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
            v20,
            (__int64)&dword_18009E474,
            v21,
            v22,
            &v32);
        }
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v10 = -2145910774;
        goto LABEL_29;
      }
    }
  }
  else if ( v9 != -2147024894 )
  {
LABEL_29:
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v31);
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v29);
    return v10;
  }
  hkey[0] = 0;
  pvData = 0;
  pcbData = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hkey,
    0);
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\MDM",
          0,
          0x20119u,
          hkey);
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 >= 0 )
  {
    ValueW = RegGetValueW(hkey[0], 0, L"DisableRegistration", 0x18u, 0, &pvData, &pcbData);
    v13 = ValueW;
    if ( ValueW > 0 )
      v13 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( v13 != -2147024894 && v13 != -2147023267 )
  {
    if ( v13 < 0 )
      goto LABEL_38;
    LOBYTE(v8) = pvData != 0;
  }
  hKey = 0;
  v30 = 0;
  v35 = 4;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v13 = EEDBManager::OpenEnrollmentsHKEY(0x20019u, &hKey);
  if ( v13 >= 0 )
  {
    v15 = RegGetValueW(hKey, 0, L"ExternallyManaged", 0x18u, 0, &v30, &v35);
    v13 = v15;
    if ( v15 > 0 )
      v13 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( v13 == -2147024894 || v13 == -2147023267 )
  {
    v16 = 0;
    v13 = 0;
  }
  else
  {
    v16 = 1;
    if ( v13 >= 0 )
      v16 = v30 != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v13 >= 0 && (v8 || v16) )
    v11 = 0;
  v5 = (void **)v32;
LABEL_38:
  if ( hkey[0] )
    RegCloseKey(hkey[0]);
  if ( v13 >= 0 && v11 )
  {
    if ( !*((_QWORD *)a2 + 7)
      && (unsigned int)dword_1800AF3B0 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800AF3B0, 0x800000000000LL) )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v24,
        (__int64)byte_18009E45D);
    }
    if ( !*((_QWORD *)a2 + 2)
      && (unsigned int)dword_1800AF3B0 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800AF3B0, 0x800000000000LL) )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v25,
        (__int64)byte_18009E443);
    }
    if ( !*((_QWORD *)a2 + 6)
      && (unsigned int)dword_1800AF3B0 > 5
      && (unsigned __int8)tlgKeywordOn(&dword_1800AF3B0, 0x800000000000LL) )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v26,
        (__int64)word_18009E422);
    }
    if ( !*(_QWORD *)a2 && !*((_QWORD *)a2 + 4) && (unsigned int)dword_1800AF3B0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800AF3B0, 0x800000000000LL) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v27,
          (__int64)word_18009E40A);
    }
    *pguid = GUID_NULL;
    v10 = EnrollEngine::BeginEnrollInternal<MDMEnrollInfoTag>((__int64)this, (__int64)a2, 0, v5, pguid);
    goto LABEL_29;
  }
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v31);
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v29);
  return 2149056550LL;
}

```

## disassembly

```asm
0x180036220  push    rbp
0x180036222  push    rbx
0x180036223  push    rsi
0x180036224  push    rdi
0x180036225  push    r12
0x180036227  push    r13
0x180036229  push    r14
0x18003622b  push    r15
0x18003622d  lea     rbp, [rsp-1Fh]
0x180036232  sub     rsp, 98h
0x180036239  mov     rax, cs:__security_cookie
0x180036240  xor     rax, rsp
0x180036243  mov     [rbp+57h+var_48], rax
0x180036247  mov     r12, r9
0x18003624a  mov     rdi, r8
0x18003624d  mov     [rbp+57h+var_70], r8
0x180036251  mov     r15, rdx
0x180036254  mov     r13, rcx
0x180036257  xor     r14d, r14d
0x18003625a  mov     [rbp+57h+var_88], r14
0x18003625e  mov     [rbp+57h+var_78], r14
0x180036262  mov     rax, cs:off_1800AF740
0x180036269  lea     r8, [rbp+57h+var_78]
0x18003626d  mov     edx, 0D402061h
0x180036272  lea     rcx, off_1800AF740
0x180036279  mov     rax, [rax+20h]
0x18003627d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036282  mov     ebx, eax
0x180036284  lea     esi, [r14+1]
0x180036288  test    eax, eax
0x18003628a  jns     loc_1800363F5
0x180036290  cmp     eax, 80070002h
0x180036295  jnz     loc_1800364B1
0x18003629b  mov     [rbp+57h+hkey], r14
0x18003629f  mov     [rbp+57h+var_90], r14d
0x1800362a3  mov     [rbp+57h+var_60], 4
0x1800362aa  xor     edx, edx
0x1800362ac  lea     rcx, [rbp+57h+hkey]
0x1800362b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800362b5  lea     rax, [rbp+57h+hkey]
0x1800362b9  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800362be  mov     r9d, 20119h; samDesired
0x1800362c4  xor     r8d, r8d; ulOptions
0x1800362c7  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800362ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800362d5  call    cs:__imp_RegOpenKeyExW
0x1800362db  mov     ebx, eax
0x1800362dd  test    eax, eax
0x1800362df  jle     short loc_1800362EA
0x1800362e1  movzx   ebx, ax
0x1800362e4  or      ebx, 80070000h
0x1800362ea  test    ebx, ebx
0x1800362ec  js      short loc_18003632D
0x1800362ee  lea     rax, [rbp+57h+var_60]
0x1800362f2  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800362f7  lea     rax, [rbp+57h+var_90]
0x1800362fb  mov     [rsp+0D0h+pvData], rax; pvData
0x180036300  mov     [rsp+0D0h+phkResult], r14; pdwType
0x180036305  mov     r9d, 18h; dwFlags
0x18003630b  lea     r8, aDisableregistr; "DisableRegistration"
0x180036312  xor     edx, edx; lpSubKey
0x180036314  mov     rcx, [rbp+57h+hkey]; hkey
0x180036318  call    cs:__imp_RegGetValueW
0x18003631e  mov     ebx, eax
0x180036320  test    eax, eax
0x180036322  jle     short loc_18003632D
0x180036324  movzx   ebx, ax
0x180036327  or      ebx, 80070000h
0x18003632d  cmp     ebx, 80070002h
0x180036333  jz      short loc_18003634D
0x180036335  cmp     ebx, 8007065Dh
0x18003633b  jz      short loc_18003634D
0x18003633d  test    ebx, ebx
0x18003633f  js      loc_1800364FF
0x180036345  cmp     [rbp+57h+var_90], 0
0x180036349  setnz   r14b
0x18003634d  mov     [rbp+57h+hKey], 0
0x180036355  mov     [rbp+57h+var_80], 0
0x18003635c  mov     [rbp+57h+var_5C], 4
0x180036363  xor     edx, edx
0x180036365  lea     rcx, [rbp+57h+hKey]
0x180036369  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003636e  lea     rdx, [rbp+57h+hKey]; HKEY *
0x180036372  mov     ecx, 20019h; unsigned int
0x180036377  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18003637c  mov     ebx, eax
0x18003637e  test    eax, eax
0x180036380  js      short loc_1800363C5
0x180036382  lea     rax, [rbp+57h+var_5C]
0x180036386  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18003638b  lea     rax, [rbp+57h+var_80]
0x18003638f  mov     [rsp+0D0h+pvData], rax; pvData
0x180036394  mov     [rsp+0D0h+phkResult], 0; pdwType
0x18003639d  mov     r9d, 18h; dwFlags
0x1800363a3  lea     r8, aExternallymana; "ExternallyManaged"
0x1800363aa  xor     edx, edx; lpSubKey
0x1800363ac  mov     rcx, [rbp+57h+hKey]; hkey
0x1800363b0  call    cs:__imp_RegGetValueW
0x1800363b6  mov     ebx, eax
0x1800363b8  test    eax, eax
0x1800363ba  jle     short loc_1800363C5
0x1800363bc  movzx   ebx, ax
0x1800363bf  or      ebx, 80070000h
0x1800363c5  cmp     ebx, 80070002h
0x1800363cb  jz      loc_1800364CB
0x1800363d1  cmp     ebx, 8007065Dh
0x1800363d7  jz      loc_1800364CB
0x1800363dd  mov     edi, esi
0x1800363df  test    ebx, ebx
0x1800363e1  js      loc_1800364CF
0x1800363e7  xor     edi, edi
0x1800363e9  cmp     [rbp+57h+var_80], edi
0x1800363ec  setnz   dil
0x1800363f0  jmp     loc_1800364CF
0x1800363f5  mov     rcx, [rbp+57h+var_78]
0x1800363f9  mov     rax, [rcx]
0x1800363fc  lea     rdx, [rbp+57h+var_88]
0x180036400  mov     rax, [rax+18h]
0x180036404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036409  cmp     eax, esi
0x18003640b  jz      loc_18003629B
0x180036411  mov     edx, 3Fh ; '?'
0x180036416  mov     [rbp+57h+var_90], edx
0x180036419  mov     rcx, [rbp+57h+var_88]
0x18003641d  test    eax, eax
0x18003641f  jnz     short loc_18003643D
0x180036421  test    rcx, rcx
0x180036424  jz      short loc_18003643D
0x180036426  mov     rax, [rcx]
0x180036429  lea     rdx, [rbp+57h+var_90]
0x18003642d  mov     rax, [rax+38h]
0x180036431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036436  mov     rcx, [rbp+57h+var_88]
0x18003643a  mov     edx, [rbp+57h+var_90]
0x18003643d  xorps   xmm0, xmm0
0x180036440  movups  xmmword ptr [rbp+57h+hkey], xmm0
0x180036444  cmp     edx, 5
0x180036447  jz      loc_18003629B
0x18003644d  mov     rax, [rcx]
0x180036450  lea     rdx, [rbp+57h+hkey]
0x180036454  mov     rax, [rax+18h]
0x180036458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003645d  test    eax, eax
0x18003645f  js      loc_18003629B
0x180036465  mov     eax, cs:dword_1800AF3E8
0x18003646b  cmp     eax, 5
0x18003646e  jbe     short loc_1800364A7
0x180036470  mov     rdx, 800000000000h
0x18003647a  lea     rcx, dword_1800AF3E8
0x180036481  call    _tlgKeywordOn
0x180036486  test    al, al
0x180036488  jz      short loc_1800364A7
0x18003648a  lea     rax, [rbp+57h+hkey]
0x18003648e  mov     [rbp+57h+var_70], rax
0x180036492  lea     rax, [rbp+57h+var_70]
0x180036496  mov     [rsp+0D0h+phkResult], rax
0x18003649b  lea     rdx, dword_18009E474
0x1800364a2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x1800364a7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x1800364ac  mov     ebx, 8018000Ah
0x1800364b1  lea     rcx, [rbp+57h+var_78]
0x1800364b5  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800364ba  nop
0x1800364bb  lea     rcx, [rbp+57h+var_88]
0x1800364bf  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800364c4  mov     eax, ebx
0x1800364c6  jmp     loc_180036638
0x1800364cb  xor     edi, edi
0x1800364cd  xor     ebx, ebx
0x1800364cf  mov     rcx, [rbp+57h+hKey]; hKey
0x1800364d3  test    rcx, rcx
0x1800364d6  jz      short loc_1800364DE
0x1800364d8  call    cs:__imp_RegCloseKey
0x1800364de  test    ebx, ebx
0x1800364e0  js      short loc_1800364F8
0x1800364e2  test    r14d, r14d
0x1800364e5  jnz     short loc_1800364F0
0x1800364e7  xor     r14d, r14d
0x1800364ea  test    edi, edi
0x1800364ec  jnz     short loc_1800364F3
0x1800364ee  jmp     short loc_1800364FB
0x1800364f0  xor     r14d, r14d
0x1800364f3  mov     esi, r14d
0x1800364f6  jmp     short loc_1800364FB
0x1800364f8  xor     r14d, r14d
0x1800364fb  mov     rdi, [rbp+57h+var_70]
0x1800364ff  mov     rcx, [rbp+57h+hkey]; hKey
0x180036503  test    rcx, rcx
0x180036506  jz      short loc_18003650E
0x180036508  call    cs:__imp_RegCloseKey
0x18003650e  test    ebx, ebx
0x180036510  js      loc_180036620
0x180036516  test    esi, esi
0x180036518  jz      loc_180036620
0x18003651e  lea     rbx, dword_1800AF3B0
0x180036525  cmp     [r15+38h], r14
0x180036529  jnz     short loc_180036558
0x18003652b  mov     eax, cs:dword_1800AF3B0
0x180036531  cmp     eax, 5
0x180036534  jbe     short loc_180036558
0x180036536  mov     rdx, 800000000000h
0x180036540  mov     rcx, rbx
0x180036543  call    _tlgKeywordOn
0x180036548  test    al, al
0x18003654a  jz      short loc_180036558
0x18003654c  lea     rdx, byte_18009E45D
0x180036553  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180036558  cmp     [r15+10h], r14
0x18003655c  jnz     short loc_18003658B
0x18003655e  mov     eax, cs:dword_1800AF3B0
0x180036564  cmp     eax, 5
0x180036567  jbe     short loc_18003658B
0x180036569  mov     rdx, 800000000000h
0x180036573  mov     rcx, rbx
0x180036576  call    _tlgKeywordOn
0x18003657b  test    al, al
0x18003657d  jz      short loc_18003658B
0x18003657f  lea     rdx, byte_18009E443
0x180036586  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003658b  cmp     [r15+30h], r14
0x18003658f  jnz     short loc_1800365BE
0x180036591  mov     eax, cs:dword_1800AF3B0
0x180036597  cmp     eax, 5
0x18003659a  jbe     short loc_1800365BE
0x18003659c  mov     rdx, 800000000000h
0x1800365a6  mov     rcx, rbx
0x1800365a9  call    _tlgKeywordOn
0x1800365ae  test    al, al
0x1800365b0  jz      short loc_1800365BE
0x1800365b2  lea     rdx, word_18009E422
0x1800365b9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800365be  cmp     [r15], r14
0x1800365c1  jnz     short loc_1800365F6
0x1800365c3  cmp     [r15+20h], r14
0x1800365c7  jnz     short loc_1800365F6
0x1800365c9  mov     eax, cs:dword_1800AF3B0
0x1800365cf  cmp     eax, 5
0x1800365d2  jbe     short loc_1800365F6
0x1800365d4  mov     rdx, 800000000000h
0x1800365de  mov     rcx, rbx
0x1800365e1  call    _tlgKeywordOn
0x1800365e6  test    al, al
0x1800365e8  jz      short loc_1800365F6
0x1800365ea  lea     rdx, word_18009E40A
0x1800365f1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800365f6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800365fd  movdqu  xmmword ptr [r12], xmm0
0x180036603  mov     [rsp+0D0h+phkResult], r12; pguid
0x180036608  mov     r9, rdi; int
0x18003660b  xor     r8d, r8d; int
0x18003660e  mov     rdx, r15; int
0x180036611  mov     rcx, r13; int
0x180036614  call    ??$BeginEnrollInternal@UMDMEnrollInfoTag@@@EnrollEngine@@AEAAJPEAUMDMEnrollInfoTag@@W4EntPlatStateMachine@@PEAPEAXPEAU_GUID@@@Z; EnrollEngine::BeginEnrollInternal<MDMEnrollInfoTag>(MDMEnrollInfoTag *,EntPlatStateMachine,void * *,_GUID *)
0x180036619  mov     ebx, eax
0x18003661b  jmp     loc_1800364B1
0x180036620  lea     rcx, [rbp+57h+var_78]
0x180036624  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180036629  nop
0x18003662a  lea     rcx, [rbp+57h+var_88]
0x18003662e  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180036633  mov     eax, 80180026h
0x180036638  mov     rcx, [rbp+57h+var_48]
0x18003663c  xor     rcx, rsp; StackCookie
0x18003663f  call    __security_check_cookie
0x180036644  add     rsp, 98h
0x18003664b  pop     r15
0x18003664d  pop     r14
0x18003664f  pop     r13
0x180036651  pop     r12
0x180036653  pop     rdi
0x180036654  pop     rsi
0x180036655  pop     rbx
0x180036656  pop     rbp
0x180036657  retn
```
