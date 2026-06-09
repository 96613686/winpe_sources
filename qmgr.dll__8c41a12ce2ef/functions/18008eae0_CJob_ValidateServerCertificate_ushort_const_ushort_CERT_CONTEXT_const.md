# CJob::ValidateServerCertificate(ushort const *,ushort,_CERT_CONTEXT const *)

- ea: `0x18008eae0`
- end: `0x18008f161`
- name: `?ValidateServerCertificate@CJob@@UEAAJPEBGGPEBU_CERT_CONTEXT@@@Z`
- size: `1665`
- prototype: `__int64 __fastcall(CJob *this, unsigned __int16 *, unsigned __int16, const struct _CERT_CONTEXT *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002c6ac`
- `0x18002c6e0`
- `0x180031d74`
- `0x180060058`
- `0x18008ddc8`
- `0x18008e258`
- `0x18008eae0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a3420`
- `0x1800ab7fc`
- `0x1800cbd48`
- `0x1800cc130`
- `0x1800d0ef0`
- `0x1800f227c`
- `0x1800f23c8`
- `0x1800f2674`
- `0x1800f9948`
- `0x1800f9960`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ed78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ee7c`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18008ebf2`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18008ebf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f09e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f09e`
- `CRYPT32!CertSaveStore` at `0x18008ed5c`
- `CRYPT32!CertSaveStore` at `0x18008ee60`
- `CRYPT32!CertSaveStore` at `0x18008ed5c`
- `CRYPT32!CertSaveStore` at `0x18008ee60`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall CJob::ValidateServerCertificate(
        CJob *this,
        unsigned __int16 *a2,
        unsigned __int16 a3,
        const struct _CERT_CONTEXT *a4)
{
  EVENT_LOG *v8; // rcx
  ServerCertCache *v9; // r13
  const struct ServerCertCache::CertHash *v10; // rsi
  const struct ServerCertCache::ServerEndpoint *v11; // rax
  int v13; // eax
  int ServerCertificateValidationInterface; // eax
  void *v15; // rsi
  unsigned int LastError; // eax
  void *v17; // r15
  unsigned int v18; // eax
  int v19; // eax
  int v20; // edi
  EVENT_LOG *v21; // rcx
  const struct ServerCertCache::CertHash *v22; // rbx
  const struct ServerCertCache::ServerEndpoint *v23; // rax
  __int64 v24; // rcx
  struct IBackgroundCopyServerCertificateValidationCallback *v26; // [rsp+58h] [rbp-3E0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-3D8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-3D0h] BYREF
  __int64 v29; // [rsp+70h] [rbp-3C8h] BYREF
  __int128 pvSaveToPara; // [rsp+78h] [rbp-3C0h] BYREF
  void *v31; // [rsp+90h] [rbp-3A8h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-3A0h] BYREF
  unsigned __int16 *v33; // [rsp+A0h] [rbp-398h]
  void **pExceptionObject; // [rsp+B0h] [rbp-388h] BYREF
  __int128 v35; // [rsp+B8h] [rbp-380h]
  int v36; // [rsp+C8h] [rbp-370h]
  int v37; // [rsp+CCh] [rbp-36Ch]
  int v38; // [rsp+D0h] [rbp-368h]
  void **v39; // [rsp+110h] [rbp-328h] BYREF
  __int128 v40; // [rsp+118h] [rbp-320h]
  int v41; // [rsp+128h] [rbp-310h]
  int v42; // [rsp+12Ch] [rbp-30Ch]
  int v43; // [rsp+130h] [rbp-308h]
  void **v44; // [rsp+170h] [rbp-2C8h] BYREF
  __int128 v45; // [rsp+178h] [rbp-2C0h]
  int v46; // [rsp+188h] [rbp-2B0h]
  int v47; // [rsp+18Ch] [rbp-2ACh]
  int v48; // [rsp+190h] [rbp-2A8h]
  void **v49; // [rsp+1D0h] [rbp-268h] BYREF
  __int128 v50; // [rsp+1D8h] [rbp-260h]
  unsigned int v51; // [rsp+1E8h] [rbp-250h]
  int v52; // [rsp+1ECh] [rbp-24Ch]
  int v53; // [rsp+1F0h] [rbp-248h]
  void **v54; // [rsp+230h] [rbp-208h] BYREF
  __int128 v55; // [rsp+238h] [rbp-200h]
  int v56; // [rsp+248h] [rbp-1F0h]
  int v57; // [rsp+24Ch] [rbp-1ECh]
  int v58; // [rsp+250h] [rbp-1E8h]
  void **v59; // [rsp+290h] [rbp-1A8h] BYREF
  __int128 v60; // [rsp+298h] [rbp-1A0h]
  unsigned int v61; // [rsp+2A8h] [rbp-190h]
  int v62; // [rsp+2ACh] [rbp-18Ch]
  int v63; // [rsp+2B0h] [rbp-188h]
  void **v64; // [rsp+2F0h] [rbp-148h] BYREF
  __int128 v65; // [rsp+2F8h] [rbp-140h]
  int v66; // [rsp+308h] [rbp-130h]
  int v67; // [rsp+30Ch] [rbp-12Ch]
  int v68; // [rsp+310h] [rbp-128h]
  void **v69; // [rsp+350h] [rbp-E8h] BYREF
  __int128 v70; // [rsp+358h] [rbp-E0h]
  int v71; // [rsp+368h] [rbp-D0h]
  int v72; // [rsp+36Ch] [rbp-CCh]
  int v73; // [rsp+370h] [rbp-C8h]
  _BYTE v74[32]; // [rsp+3B0h] [rbp-88h] BYREF
  _BYTE v75[32]; // [rsp+3D0h] [rbp-68h] BYREF

  v33 = a2;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
      (char *)this - 616);
  v9 = (CJob *)((char *)this + 896);
  v10 = (const struct ServerCertCache::CertHash *)ServerCertCache::ComputeCertHash(v8, &pvSaveToPara, a4);
  v11 = (const struct ServerCertCache::ServerEndpoint *)ServerCertCache::ServerEndpoint::ServerEndpoint(
                                                          (ServerCertCache::ServerEndpoint *)v74,
                                                          a2,
                                                          a3);
  LOBYTE(v10) = ServerCertCache::Contains((CJob *)((char *)this + 896), v11, v10);
  std::wstring::~wstring(v74);
  std::vector<unsigned char>::_Tidy(&pvSaveToPara);
  if ( (_BYTE)v10 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
    return 0;
  }
  else
  {
    v29 = 0;
    v13 = CoIncrementMTAUsage(&v29);
    if ( v13 < 0 )
    {
      v35 = 0;
      pExceptionObject = &ComError::`vftable';
      v36 = v13;
      v37 = 1014;
      v38 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v26 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    ServerCertificateValidationInterface = CJob::GetServerCertificateValidationInterface(
                                             (CJob *)((char *)this - 616),
                                             &v26);
    if ( ServerCertificateValidationInterface < 0 )
    {
      v40 = 0;
      v39 = &ComError::`vftable';
      v41 = ServerCertificateValidationInterface;
      v42 = 1017;
      v43 = 1;
      throw (ComError *)&v39;
    }
    if ( !v26 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
      v70 = 0;
      v69 = &ComError::`vftable';
      v71 = -2145386380;
      v72 = 1088;
      v73 = 1;
      throw (ComError *)&v69;
    }
    wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&v31, a4->cbCertEncoded);
    v15 = v31;
    if ( !v31 )
    {
      v45 = 0;
      v44 = &ComError::`vftable';
      v46 = -2147024882;
      v47 = 1025;
      v48 = 1;
      throw (ComError *)&v44;
    }
    memcpy_0(v31, a4->pbCertEncoded, a4->cbCertEncoded);
    pvSaveToPara = 0;
    if ( !CertSaveStore(a4->hCertStore, 0, 1u, 2u, &pvSaveToPara, 0) )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0x80070000;
      else
        LastError = GetLastError();
      v50 = 0;
      v49 = &ComError::`vftable';
      v51 = LastError;
      v52 = 1040;
      v53 = 1;
      throw (ComError *)&v49;
    }
    wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pv, (unsigned int)pvSaveToPara);
    v17 = pv;
    if ( !pv )
    {
      v55 = 0;
      v54 = &ComError::`vftable';
      v56 = -2147024882;
      v57 = 1047;
      v58 = 1;
      throw (ComError *)&v54;
    }
    *((_QWORD *)&pvSaveToPara + 1) = pv;
    if ( !CertSaveStore(a4->hCertStore, 0, 1u, 2u, &pvSaveToPara, 0) )
    {
      if ( (int)GetLastError() > 0 )
        v18 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v18 = GetLastError();
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v18;
      v62 = 1059;
      v63 = 1;
      throw (ComError *)&v59;
    }
    CJob::GetJobExternal((__int64)this - 616, &v27);
    CFile::GetFileExternal(*(_QWORD *)(*((_QWORD *)this + 29) + 8LL * *((unsigned int *)this + 56)), &v28);
    v19 = (*(__int64 (__fastcall **)(struct IBackgroundCopyServerCertificateValidationCallback *, __int64, __int64, _QWORD, void *, DWORD, _DWORD, _QWORD))(*(_QWORD *)v26 + 24LL))(
            v26,
            v27,
            v28,
            a4->cbCertEncoded,
            v15,
            a4->dwCertEncodingType,
            pvSaveToPara,
            *((_QWORD *)&pvSaveToPara + 1));
    v20 = v19;
    if ( v19 == -2147417848 || v19 == -2147023174 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids);
        v21 = WPP_GLOBAL_Control;
      }
      v20 = -2145386380;
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
    }
    if ( v21 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v21 + 2), 53, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, (unsigned int)v20);
    if ( v20 < 0 )
    {
      v65 = 0;
      v64 = &ComError::`vftable';
      v66 = v20;
      v67 = 1082;
      v68 = 1;
      throw (ComError *)&v64;
    }
    v22 = (const struct ServerCertCache::CertHash *)ServerCertCache::ComputeCertHash(v21, v74, a4);
    v23 = (const struct ServerCertCache::ServerEndpoint *)ServerCertCache::ServerEndpoint::ServerEndpoint(
                                                            (ServerCertCache::ServerEndpoint *)v75,
                                                            v33,
                                                            a3);
    ServerCertCache::Insert(v9, v23, v22);
    std::wstring::~wstring(v75);
    std::vector<unsigned char>::_Tidy(v74);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v24 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    if ( v17 )
      CoTaskMemFree(v17);
    if ( v15 )
      CoTaskMemFree(v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>(&v29);
    return 0;
  }
}

```

## disassembly

```asm
0x18008eae0  push    rbx
0x18008eae2  push    rsi
0x18008eae3  push    rdi
0x18008eae4  push    r12
0x18008eae6  push    r13
0x18008eae8  push    r14
0x18008eaea  push    r15
0x18008eaec  sub     rsp, 400h
0x18008eaf3  mov     rax, cs:__security_cookie
0x18008eafa  xor     rax, rsp
0x18008eafd  mov     [rsp+438h+var_48], rax
0x18008eb05  mov     r14, r9
0x18008eb08  movzx   r12d, r8w
0x18008eb0c  mov     word ptr [rsp+438h+var_3E8], r8w
0x18008eb12  mov     r15, rdx
0x18008eb15  mov     [rsp+438h+var_398], rdx
0x18008eb1d  mov     rdi, rcx
0x18008eb20  lea     rax, WPP_GLOBAL_Control
0x18008eb27  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb2e  mov     ebx, 1
0x18008eb33  cmp     rcx, rax
0x18008eb36  jz      short loc_18008EB58
0x18008eb38  test    [rcx+1Ch], bl
0x18008eb3b  jz      short loc_18008EB58
0x18008eb3d  lea     r9, [rdi-268h]
0x18008eb44  lea     edx, [rbx+31h]
0x18008eb47  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18008eb4e  mov     rcx, [rcx+10h]
0x18008eb52  call    WPP_SF_q
0x18008eb57  nop
0x18008eb58  lea     r13, [rdi+380h]
0x18008eb5f  mov     r8, r14
0x18008eb62  lea     rdx, [rsp+438h+var_3C0]
0x18008eb67  call    ?ComputeCertHash@ServerCertCache@@AEAA?AVCertHash@1@PEBU_CERT_CONTEXT@@@Z; ServerCertCache::ComputeCertHash(_CERT_CONTEXT const *)
0x18008eb6c  mov     rsi, rax
0x18008eb6f  movzx   r8d, r12w; unsigned __int16
0x18008eb73  mov     rdx, r15; unsigned __int16 *
0x18008eb76  lea     rcx, [rsp+438h+var_88]; this
0x18008eb7e  call    ??0ServerEndpoint@ServerCertCache@@QEAA@PEBGG@Z; ServerCertCache::ServerEndpoint::ServerEndpoint(ushort const *,ushort)
0x18008eb83  nop
0x18008eb84  mov     r8, rsi; struct ServerCertCache::CertHash *
0x18008eb87  mov     rdx, rax; struct ServerCertCache::ServerEndpoint *
0x18008eb8a  mov     rcx, r13; this
0x18008eb8d  call    ?Contains@ServerCertCache@@AEAA_NAEBVServerEndpoint@1@AEBVCertHash@1@@Z; ServerCertCache::Contains(ServerCertCache::ServerEndpoint const &,ServerCertCache::CertHash const &)
0x18008eb92  mov     sil, al
0x18008eb95  lea     rcx, [rsp+438h+var_88]
0x18008eb9d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008eba2  nop
0x18008eba3  lea     rcx, [rsp+438h+var_3C0]
0x18008eba8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008ebad  xor     r15d, r15d
0x18008ebb0  test    sil, sil
0x18008ebb3  jz      short loc_18008EBE8
0x18008ebb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ebbc  lea     r12, WPP_GLOBAL_Control
0x18008ebc3  cmp     rcx, r12
0x18008ebc6  jz      short loc_18008EBE1
0x18008ebc8  test    [rcx+1Ch], bl
0x18008ebcb  jz      short loc_18008EBE1
0x18008ebcd  lea     edx, [r15+33h]
0x18008ebd1  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18008ebd8  mov     rcx, [rcx+10h]
0x18008ebdc  call    WPP_SF_
0x18008ebe1  xor     eax, eax
0x18008ebe3  jmp     loc_18008F13D
0x18008ebe8  mov     [rsp+438h+var_3C8], r15
0x18008ebed  lea     rcx, [rsp+438h+var_3C8]
0x18008ebf2  call    cs:__imp_CoIncrementMTAUsage
0x18008ebf8  test    eax, eax
0x18008ebfa  jns     short loc_18008EC43
0x18008ebfc  xorps   xmm0, xmm0
0x18008ebff  movups  [rsp+438h+var_380], xmm0
0x18008ec07  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008ec0e  mov     [rsp+438h+pExceptionObject], rcx
0x18008ec16  mov     [rsp+438h+var_370], eax
0x18008ec1d  mov     [rsp+438h+var_36C], 3F6h
0x18008ec28  mov     [rsp+438h+var_368], ebx
0x18008ec2f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008ec36  lea     rcx, [rsp+438h+pExceptionObject]; pExceptionObject
0x18008ec3e  call    _CxxThrowException_0
0x18008ec43  mov     [rsp+438h+var_3E0], r15
0x18008ec48  lea     r12, [rdi-268h]
0x18008ec4f  lea     rcx, [rsp+438h+var_3E0]
0x18008ec54  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008ec59  lea     rdx, [rsp+438h+var_3E0]; struct IBackgroundCopyServerCertificateValidationCallback **
0x18008ec5e  mov     rcx, r12; this
0x18008ec61  call    ?GetServerCertificateValidationInterface@CJob@@QEBAJPEAPEAUIBackgroundCopyServerCertificateValidationCallback@@@Z; CJob::GetServerCertificateValidationInterface(IBackgroundCopyServerCertificateValidationCallback * *)
0x18008ec66  test    eax, eax
0x18008ec68  jns     short loc_18008ECB1
0x18008ec6a  xorps   xmm0, xmm0
0x18008ec6d  movups  [rsp+438h+var_320], xmm0
0x18008ec75  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008ec7c  mov     [rsp+438h+var_328], rcx
0x18008ec84  mov     [rsp+438h+var_310], eax
0x18008ec8b  mov     [rsp+438h+var_30C], 3F9h
0x18008ec96  mov     [rsp+438h+var_308], ebx
0x18008ec9d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008eca4  lea     rcx, [rsp+438h+var_328]; pExceptionObject
0x18008ecac  call    _CxxThrowException_0
0x18008ecb1  cmp     [rsp+438h+var_3E0], r15
0x18008ecb6  jz      loc_18008F0BE
0x18008ecbc  mov     edx, [r14+10h]
0x18008ecc0  lea     rcx, [rsp+438h+var_3A8]
0x18008ecc8  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x18008eccd  nop
0x18008ecce  mov     rsi, [rsp+438h+var_3A8]
0x18008ecd6  test    rsi, rsi
0x18008ecd9  jnz     short loc_18008ED26
0x18008ecdb  xorps   xmm0, xmm0
0x18008ecde  movups  [rsp+438h+var_2C0], xmm0
0x18008ece6  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008eced  mov     [rsp+438h+var_2C8], rcx
0x18008ecf5  mov     [rsp+438h+var_2B0], 8007000Eh
0x18008ed00  mov     [rsp+438h+var_2AC], 401h
0x18008ed0b  mov     [rsp+438h+var_2A8], ebx
0x18008ed12  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008ed19  lea     rcx, [rsp+438h+var_2C8]; pExceptionObject
0x18008ed21  call    _CxxThrowException_0
0x18008ed26  mov     r8d, [r14+10h]; Size
0x18008ed2a  mov     rdx, [r14+8]; Src
0x18008ed2e  mov     rcx, rsi; void *
0x18008ed31  call    memcpy_0
0x18008ed36  xorps   xmm0, xmm0
0x18008ed39  movups  [rsp+438h+var_3C0], xmm0
0x18008ed3e  mov     [rsp+438h+dwFlags], r15d; dwFlags
0x18008ed43  lea     rax, [rsp+438h+var_3C0]
0x18008ed48  mov     [rsp+438h+pvSaveToPara], rax; pvSaveToPara
0x18008ed4d  mov     r9d, 2; dwSaveTo
0x18008ed53  mov     r8d, ebx; dwSaveAs
0x18008ed56  xor     edx, edx; dwEncodingType
0x18008ed58  mov     rcx, [r14+20h]; hCertStore
0x18008ed5c  call    cs:__imp_CertSaveStore
0x18008ed62  test    eax, eax
0x18008ed64  jnz     short loc_18008EDCD
0x18008ed66  call    cs:__imp_GetLastError
0x18008ed6c  test    eax, eax
0x18008ed6e  jg      short loc_18008ED78
0x18008ed70  call    cs:__imp_GetLastError
0x18008ed76  jmp     short loc_18008ED86
0x18008ed78  call    cs:__imp_GetLastError
0x18008ed7e  movzx   eax, ax
0x18008ed81  or      eax, 80070000h
0x18008ed86  xorps   xmm0, xmm0
0x18008ed89  movups  [rsp+438h+var_260], xmm0
0x18008ed91  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008ed98  mov     [rsp+438h+var_268], rcx
0x18008eda0  mov     [rsp+438h+var_250], eax
0x18008eda7  mov     [rsp+438h+var_24C], 410h
0x18008edb2  mov     [rsp+438h+var_248], ebx
0x18008edb9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008edc0  lea     rcx, [rsp+438h+var_268]; pExceptionObject
0x18008edc8  call    _CxxThrowException_0
0x18008edcd  mov     edx, dword ptr [rsp+438h+var_3C0]
0x18008edd1  lea     rcx, [rsp+438h+pv]
0x18008edd9  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x18008edde  nop
0x18008eddf  mov     r15, [rsp+438h+pv]
0x18008ede7  test    r15, r15
0x18008edea  jnz     short loc_18008EE37
0x18008edec  xorps   xmm0, xmm0
0x18008edef  movups  [rsp+438h+var_200], xmm0
0x18008edf7  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008edfe  mov     [rsp+438h+var_208], rcx
0x18008ee06  mov     [rsp+438h+var_1F0], 8007000Eh
0x18008ee11  mov     [rsp+438h+var_1EC], 417h
0x18008ee1c  mov     [rsp+438h+var_1E8], ebx
0x18008ee23  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008ee2a  lea     rcx, [rsp+438h+var_208]; pExceptionObject
0x18008ee32  call    _CxxThrowException_0
0x18008ee37  mov     qword ptr [rsp+438h+var_3C0+8], r15
0x18008ee3f  mov     [rsp+438h+dwFlags], 0; dwFlags
0x18008ee47  lea     rax, [rsp+438h+var_3C0]
0x18008ee4c  mov     [rsp+438h+pvSaveToPara], rax; pvSaveToPara
0x18008ee51  mov     r9d, 2; dwSaveTo
0x18008ee57  mov     r8d, ebx; dwSaveAs
0x18008ee5a  xor     edx, edx; dwEncodingType
0x18008ee5c  mov     rcx, [r14+20h]; hCertStore
0x18008ee60  call    cs:__imp_CertSaveStore
0x18008ee66  test    eax, eax
0x18008ee68  jnz     short loc_18008EED1
0x18008ee6a  call    cs:__imp_GetLastError
0x18008ee70  test    eax, eax
0x18008ee72  jg      short loc_18008EE7C
0x18008ee74  call    cs:__imp_GetLastError
0x18008ee7a  jmp     short loc_18008EE8A
0x18008ee7c  call    cs:__imp_GetLastError
0x18008ee82  movzx   eax, ax
0x18008ee85  or      eax, 80070000h
0x18008ee8a  xorps   xmm0, xmm0
0x18008ee8d  movups  [rsp+438h+var_1A0], xmm0
0x18008ee95  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008ee9c  mov     [rsp+438h+var_1A8], rcx
0x18008eea4  mov     [rsp+438h+var_190], eax
0x18008eeab  mov     [rsp+438h+var_18C], 423h
0x18008eeb6  mov     [rsp+438h+var_188], ebx
0x18008eebd  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008eec4  lea     rcx, [rsp+438h+var_1A8]; pExceptionObject
0x18008eecc  call    _CxxThrowException_0
0x18008eed1  lea     rdx, [rsp+438h+var_3D8]
0x18008eed6  mov     rcx, r12
0x18008eed9  call    ?GetJobExternal@CJob@@QEAA?AV?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@XZ; CJob::GetJobExternal(void)
0x18008eede  nop
0x18008eedf  mov     eax, [rdi+0E0h]
0x18008eee5  mov     rcx, [rdi+0E8h]
0x18008eeec  lea     rdx, [rsp+438h+var_3D0]
0x18008eef1  mov     rcx, [rcx+rax*8]
0x18008eef5  call    ?GetFileExternal@CFile@@QEAA?AV?$ComPtr@UIBackgroundCopyFile@@@WRL@Microsoft@@XZ; CFile::GetFileExternal(void)
0x18008eefa  nop
0x18008eefb  mov     rcx, [rsp+438h+var_3E0]
0x18008ef00  mov     rax, [rcx]
0x18008ef03  mov     rdx, qword ptr [rsp+438h+var_3C0+8]
0x18008ef0b  mov     [rsp+438h+var_400], rdx
0x18008ef10  mov     edx, dword ptr [rsp+438h+var_3C0]
0x18008ef14  mov     [rsp+438h+var_408], edx
0x18008ef18  mov     edx, [r14]
0x18008ef1b  mov     [rsp+438h+dwFlags], edx
0x18008ef1f  mov     [rsp+438h+pvSaveToPara], rsi
0x18008ef24  mov     r9d, [r14+10h]
0x18008ef28  mov     r8, [rsp+438h+var_3D0]
0x18008ef2d  mov     rdx, [rsp+438h+var_3D8]
0x18008ef32  mov     rax, [rax+18h]
0x18008ef36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef3b  mov     edi, eax
0x18008ef3d  cmp     eax, 80010108h
0x18008ef42  jz      short loc_18008EF5B
0x18008ef44  cmp     eax, 800706BAh
0x18008ef49  jz      short loc_18008EF5B
0x18008ef4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ef52  lea     r12, WPP_GLOBAL_Control
0x18008ef59  jmp     short loc_18008EF95
0x18008ef5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ef62  lea     r12, WPP_GLOBAL_Control
0x18008ef69  cmp     rcx, r12
0x18008ef6c  jz      short loc_18008EF90
0x18008ef6e  test    byte ptr [rcx+1Ch], 2
0x18008ef72  jz      short loc_18008EF90
0x18008ef74  mov     edx, 34h ; '4'
0x18008ef79  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18008ef80  mov     rcx, [rcx+10h]
0x18008ef84  call    WPP_SF_
0x18008ef89  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ef90  mov     edi, 80200074h
0x18008ef95  cmp     rcx, r12
0x18008ef98  jz      short loc_18008EFB7
0x18008ef9a  test    [rcx+1Ch], bl
0x18008ef9d  jz      short loc_18008EFB7
0x18008ef9f  mov     edx, 35h ; '5'
0x18008efa4  mov     r9d, edi
0x18008efa7  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x18008efae  mov     rcx, [rcx+10h]
0x18008efb2  call    WPP_SF_d
0x18008efb7  test    edi, edi
0x18008efb9  jns     short loc_18008F002
0x18008efbb  xorps   xmm0, xmm0
0x18008efbe  movups  [rsp+438h+var_140], xmm0
0x18008efc6  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18008efcd  mov     [rsp+438h+var_148], rcx
0x18008efd5  mov     [rsp+438h+var_130], edi
0x18008efdc  mov     [rsp+438h+var_12C], 43Ah
0x18008efe7  mov     [rsp+438h+var_128], ebx
0x18008efee  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18008eff5  lea     rcx, [rsp+438h+var_148]; pExceptionObject
0x18008effd  call    _CxxThrowException_0
0x18008f002  mov     r8, r14
0x18008f005  lea     rdx, [rsp+438h+var_88]
0x18008f00d  call    ?ComputeCertHash@ServerCertCache@@AEAA?AVCertHash@1@PEBU_CERT_CONTEXT@@@Z; ServerCertCache::ComputeCertHash(_CERT_CONTEXT const *)
0x18008f012  mov     rbx, rax
0x18008f015  movzx   r8d, word ptr [rsp+438h+var_3E8]; unsigned __int16
0x18008f01b  mov     rdx, [rsp+438h+var_398]; unsigned __int16 *
0x18008f023  lea     rcx, [rsp+438h+var_68]; this
0x18008f02b  call    ??0ServerEndpoint@ServerCertCache@@QEAA@PEBGG@Z; ServerCertCache::ServerEndpoint::ServerEndpoint(ushort const *,ushort)
0x18008f030  nop
0x18008f031  mov     r8, rbx; struct ServerCertCache::CertHash *
0x18008f034  mov     rdx, rax; struct ServerCertCache::ServerEndpoint *
0x18008f037  mov     rcx, r13; this
0x18008f03a  call    ?Insert@ServerCertCache@@AEAAXAEBVServerEndpoint@1@AEBVCertHash@1@@Z; ServerCertCache::Insert(ServerCertCache::ServerEndpoint const &,ServerCertCache::CertHash const &)
0x18008f03f  nop
0x18008f040  lea     rcx, [rsp+438h+var_68]
0x18008f048  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008f04d  nop
0x18008f04e  lea     rcx, [rsp+438h+var_88]
0x18008f056  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008f05b  nop
0x18008f05c  lea     rcx, [rsp+438h+var_3D0]
0x18008f061  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18008f066  nop
0x18008f067  mov     rcx, [rsp+438h+var_3D8]
0x18008f06c  test    rcx, rcx
0x18008f06f  jz      short loc_18008F087
0x18008f071  mov     [rsp+438h+var_3D8], 0
0x18008f07a  mov     rax, [rcx]
0x18008f07d  mov     rax, [rax+10h]
0x18008f081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f086  nop
0x18008f087  test    r15, r15
0x18008f08a  jz      short loc_18008F096
0x18008f08c  mov     rcx, r15; pv
0x18008f08f  call    cs:__imp_CoTaskMemFree
0x18008f095  nop
0x18008f096  test    rsi, rsi
  ... truncated ...
```
