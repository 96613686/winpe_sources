# Microsoft::InformationProtection::CIrmProtectorWrapper::CIrmProtectorWrapper(ATL::CComPtr<IUnknown> &,ATL::CComBSTR &,ATL::CComPtr<ILockBytes> &,_IPC_PROMPT_CTX const *,ulong,ulong)

- ea: `0x180057d98`
- end: `0x180058166`
- name: `??0CIrmProtectorWrapper@InformationProtection@Microsoft@@QEAA@AEAV?$CComPtr@UIUnknown@@@ATL@@AEAVCComBSTR@4@AEAV?$CComPtr@UILockBytes@@@4@PEBU_IPC_PROMPT_CTX@@KK@Z`
- size: `974`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800537e0`

## callees

- `0x180001244`
- `0x1800030a0`
- `0x180003128`
- `0x180003198`
- `0x18000343a`
- `0x180043330`
- `0x1800516b8`
- `0x180053344`
- `0x180057c48`
- `0x180057cf0`
- `0x180057d98`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005806d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005806d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057f2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180058079`
- `OLEAUT32!__imp_SysFreeString` at `0x180058085`
- `OLEAUT32!__imp_SysFreeString` at `0x180058079`
- `OLEAUT32!__imp_SysFreeString` at `0x180058085`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180057e10`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180057e10`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180057e1b`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180057e1b`

## string_xrefs

- `0x18005810f`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058143`: `ds\security\rm\src\client\promethium\clientsdk\fileapi\irmprotectorwrapper\cirmprotectorwrapper.cpp`
- `0x180058136`: `m_pIrmProtector->HrInit(&bstrProduct, &dwVersion, &bstrExtensions, &bUseRMS)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::InformationProtection::CIrmProtectorWrapper::CIrmProtectorWrapper(
        __int64 a1,
        _QWORD *a2,
        BSTR *a3,
        __int64 *a4,
        __int64 a5,
        int a6,
        int a7)
{
  _QWORD *v11; // r14
  BSTR v12; // rax
  UINT v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rax
  volatile signed __int32 *v18; // rbx
  _QWORD *v19; // rax
  volatile signed __int32 *v20; // rbx
  __int128 v22; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B8h] BYREF
  BSTR v25[4]; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[1216]; // [rsp+78h] [rbp-90h] BYREF

  v25[1] = (BSTR)-2LL;
  v25[2] = (BSTR)a1;
  *(_QWORD *)a1 = &Microsoft::InformationProtection::CIrmProtectorWrapper::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v11 = (_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  if ( *a3 )
  {
    v13 = SysStringByteLen(*a3);
    v12 = SysAllocStringByteLen((LPCSTR)*a3, v13);
  }
  else
  {
    v12 = 0;
  }
  *(_QWORD *)(a1 + 32) = v12;
  if ( *a3 && !v12 )
    ATL::AtlThrowImpl(-2147024882);
  v14 = *a4;
  *(_QWORD *)(a1 + 40) = *a4;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  *(_QWORD *)(a1 + 48) = a5;
  v23 = 1;
  v25[0] = 0;
  bstrString = 0;
  *(_DWORD *)(a1 + 56) = a6;
  *(_DWORD *)(a1 + 60) = a7;
  v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*a2)(*a2, &IID_I_IrmProtector, v11);
  if ( v15 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0x35u,
      L"pIUnknownProtector->QueryInterface(IID_I_IrmProtector, (void **)&m_pIrmProtector)",
      v15);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, BSTR *, char *, BSTR *, __int64 *))(*(_QWORD *)*v11 + 24LL))(
          *v11,
          v25,
          (char *)&v23 + 4,
          &bstrString,
          &v23);
  if ( v16 < 0 )
  {
    Microsoft::FoundationServices::Common::FsException::FsException(
      (Microsoft::FoundationServices::Common::FsException *)pExceptionObject,
      L"ds\\security\\rm\\src\\client\\promethium\\clientsdk\\fileapi\\irmprotectorwrapper\\cirmprotectorwrapper.cpp",
      0x37u,
      L"m_pIrmProtector->HrInit(&bstrProduct, &dwVersion, &bstrExtensions, &bUseRMS)",
      v16);
    throw (Microsoft::FoundationServices::Common::FsException *)pExceptionObject;
  }
  if ( dword_180087498 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180087498);
    if ( dword_180087498 == -1 )
    {
      Microsoft::FoundationServices::Common::FastMutex::FastMutex((Microsoft::FoundationServices::Common::FastMutex *)&stru_180087470);
      atexit(Microsoft::InformationProtection::CIrmProtectorWrapper::CIrmProtectorWrapper_::_2_::_dynamic_atexit_destructor_for__mutex__);
      Init_thread_footer(&dword_180087498);
    }
  }
  if ( !(_QWORD)Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
    || !(_QWORD)Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory )
  {
    v25[3] = (BSTR)&stru_180087470;
    EnterCriticalSection(&stru_180087470);
    if ( !(_QWORD)Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory )
    {
      v17 = operator new(8u);
      *(_QWORD *)&v22 = v17;
      if ( v17 )
        *v17 = &Microsoft::InformationProtection::CIrmClientFactory::`vftable';
      v22 = 0;
      std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory>::_Resetp<Microsoft::InformationProtection::CIrmClientFactory>(
        &v22,
        v17);
      v18 = (volatile signed __int32 *)*((_QWORD *)&Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
                                       + 1);
      Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory = v22;
      if ( v18 )
      {
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
    }
    if ( !(_QWORD)Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory )
    {
      v19 = operator new(8u);
      *(_QWORD *)&v22 = v19;
      if ( v19 )
        *v19 = &Microsoft::InformationProtection::CIrmDocumentFactory::`vftable';
      v22 = 0;
      std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory>::_Resetp<Microsoft::InformationProtection::CIrmDocumentFactory>(
        &v22,
        v19);
      v20 = (volatile signed __int32 *)*((_QWORD *)&Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
                                       + 1);
      Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory = v22;
      if ( v20 )
      {
        if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
    }
    LeaveCriticalSection(&stru_180087470);
  }
  SysFreeString(bstrString);
  SysFreeString(v25[0]);
  return a1;
}

```

## disassembly

```asm
0x180057d98  mov     rax, rsp
0x180057d9b  push    rbp
0x180057d9c  push    rsi
0x180057d9d  push    rdi
0x180057d9e  push    r14
0x180057da0  push    r15
0x180057da2  lea     rbp, [rax-468h]
0x180057da9  sub     rsp, 540h
0x180057db0  mov     [rsp+560h+var_508], 0FFFFFFFFFFFFFFFEh
0x180057db9  mov     [rax+20h], rbx
0x180057dbd  mov     rax, cs:__security_cookie
0x180057dc4  xor     rax, rsp
0x180057dc7  mov     [rbp+460h+var_30], rax
0x180057dce  mov     rsi, r9
0x180057dd1  mov     rbx, r8
0x180057dd4  mov     r15, rdx
0x180057dd7  mov     rdi, rcx
0x180057dda  mov     [rsp+560h+var_500], rcx
0x180057ddf  lea     rax, ??_7CIrmProtectorWrapper@InformationProtection@Microsoft@@6B@; const Microsoft::InformationProtection::CIrmProtectorWrapper::`vftable'
0x180057de6  mov     [rcx], rax
0x180057de9  mov     qword ptr [rcx+8], 0
0x180057df1  mov     qword ptr [rcx+10h], 0
0x180057df9  lea     r14, [rcx+18h]
0x180057dfd  mov     qword ptr [r14], 0
0x180057e04  mov     rcx, [r8]; bstr
0x180057e07  test    rcx, rcx
0x180057e0a  jnz     short loc_180057E10
0x180057e0c  xor     eax, eax
0x180057e0e  jmp     short loc_180057E21
0x180057e10  call    cs:__imp_SysStringByteLen
0x180057e16  mov     edx, eax; len
0x180057e18  mov     rcx, [rbx]; psz
0x180057e1b  call    cs:__imp_SysAllocStringByteLen
0x180057e21  mov     [rdi+20h], rax
0x180057e25  cmp     qword ptr [rbx], 0
0x180057e29  jz      short loc_180057E34
0x180057e2b  test    rax, rax
0x180057e2e  jz      loc_1800580F3
0x180057e34  mov     rcx, [rsi]
0x180057e37  mov     [rdi+28h], rcx
0x180057e3b  test    rcx, rcx
0x180057e3e  jz      short loc_180057E4D
0x180057e40  mov     rax, [rcx]
0x180057e43  mov     rax, [rax+8]
0x180057e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057e4c  nop
0x180057e4d  mov     rax, [rbp+460h+arg_20]
0x180057e54  mov     [rdi+30h], rax
0x180057e58  mov     dword ptr [rsp+560h+var_520], 1
0x180057e60  mov     [rsp+560h+var_510], 0
0x180057e69  mov     [rsp+560h+bstrString], 0
0x180057e72  mov     dword ptr [rsp+560h+var_520+4], 0
0x180057e7a  mov     eax, [rbp+460h+arg_28]
0x180057e80  mov     [rdi+38h], eax
0x180057e83  mov     eax, [rbp+460h+arg_30]
0x180057e89  mov     [rdi+3Ch], eax
0x180057e8c  mov     rcx, [r15]
0x180057e8f  mov     rax, [rcx]
0x180057e92  mov     r8, r14
0x180057e95  lea     rdx, IID_I_IrmProtector
0x180057e9c  mov     rax, [rax]
0x180057e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ea4  test    eax, eax
0x180057ea6  js      loc_1800580FE
0x180057eac  mov     rcx, [r14]
0x180057eaf  mov     rax, [rcx]
0x180057eb2  lea     rdx, [rsp+560h+var_520]
0x180057eb7  mov     [rsp+20h], rdx
0x180057ebc  lea     r9, [rsp+560h+bstrString]
0x180057ec1  lea     r8, [rsp+560h+var_520+4]
0x180057ec6  lea     rdx, [rsp+560h+var_510]
0x180057ecb  mov     rax, [rax+18h]
0x180057ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ed4  test    eax, eax
0x180057ed6  js      loc_180058132
0x180057edc  mov     ecx, cs:_tls_index
0x180057ee2  mov     rax, gs:58h
0x180057eeb  mov     edx, 4
0x180057ef0  mov     rax, [rax+rcx*8]
0x180057ef4  or      esi, 0FFFFFFFFh
0x180057ef7  lea     r14, stru_180087470
0x180057efe  mov     eax, [rdx+rax]
0x180057f01  cmp     cs:dword_180087498, eax
0x180057f07  jg      loc_1800580B5
0x180057f0d  cmp     qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A, 0; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x180057f15  jz      short loc_180057F25
0x180057f17  cmp     qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A, 0; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x180057f1f  jnz     loc_180058074
0x180057f25  mov     qword ptr [rsp+560h+var_4F8], r14
0x180057f2a  mov     rcx, r14; lpCriticalSection
0x180057f2d  call    cs:__imp_EnterCriticalSection
0x180057f33  nop
0x180057f34  mov     r15d, 8
0x180057f3a  cmp     qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A, 0; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x180057f42  jnz     loc_180057FD2
0x180057f48  mov     ecx, r15d; Size
0x180057f4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057f50  mov     qword ptr [rsp+560h+var_538+8], rax
0x180057f55  test    rax, rax
0x180057f58  jz      short loc_180057F64
0x180057f5a  lea     rcx, ??_7CIrmClientFactory@InformationProtection@Microsoft@@6B@; const Microsoft::InformationProtection::CIrmClientFactory::`vftable'
0x180057f61  mov     [rax], rcx
0x180057f64  xorps   xmm0, xmm0
0x180057f67  movdqu  [rsp+560h+var_538+8], xmm0
0x180057f6d  mov     rdx, rax
0x180057f70  lea     rcx, [rsp+560h+var_538+8]
0x180057f75  call    ??$_Resetp@VCIrmClientFactory@InformationProtection@Microsoft@@@?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@AEAAXPEAVCIrmClientFactory@InformationProtection@Microsoft@@@Z; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory>::_Resetp<Microsoft::InformationProtection::CIrmClientFactory>(Microsoft::InformationProtection::CIrmClientFactory *)
0x180057f7a  mov     rbx, qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A+8; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x180057f81  mov     rax, qword ptr [rsp+560h+var_528]
0x180057f86  mov     qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A+8, rax; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x180057f8d  mov     rax, qword ptr [rsp+560h+var_538+8]
0x180057f92  mov     qword ptr cs:?s_IrmClientFactory@IIrmClientFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmClientFactory@InformationProtection@Microsoft@@@tr1@std@@A, rax; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmClientFactory> Microsoft::InformationProtection::IIrmClientFactory::s_IrmClientFactory
0x180057f99  test    rbx, rbx
0x180057f9c  jz      short loc_180057FD2
0x180057f9e  mov     eax, esi
0x180057fa0  lock xadd [rbx+8], eax
0x180057fa5  add     eax, esi
0x180057fa7  jnz     short loc_180057FD2
0x180057fa9  mov     rax, [rbx]
0x180057fac  mov     rcx, rbx
0x180057faf  mov     rax, [rax]
0x180057fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fb7  mov     eax, esi
0x180057fb9  lock xadd [rbx+0Ch], eax
0x180057fbe  add     eax, esi
0x180057fc0  jnz     short loc_180057FD2
0x180057fc2  mov     rax, [rbx]
0x180057fc5  mov     rcx, rbx
0x180057fc8  mov     rax, [rax+8]
0x180057fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fd1  nop
0x180057fd2  cmp     qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A, 0; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x180057fda  jnz     loc_18005806A
0x180057fe0  mov     rcx, r15; Size
0x180057fe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180057fe8  mov     qword ptr [rsp+560h+var_538+8], rax
0x180057fed  test    rax, rax
0x180057ff0  jz      short loc_180057FFC
0x180057ff2  lea     rcx, ??_7CIrmDocumentFactory@InformationProtection@Microsoft@@6B@; const Microsoft::InformationProtection::CIrmDocumentFactory::`vftable'
0x180057ff9  mov     [rax], rcx
0x180057ffc  xorps   xmm0, xmm0
0x180057fff  movdqu  [rsp+560h+var_538+8], xmm0
0x180058005  mov     rdx, rax
0x180058008  lea     rcx, [rsp+560h+var_538+8]
0x18005800d  call    ??$_Resetp@VCIrmDocumentFactory@InformationProtection@Microsoft@@@?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@AEAAXPEAVCIrmDocumentFactory@InformationProtection@Microsoft@@@Z; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory>::_Resetp<Microsoft::InformationProtection::CIrmDocumentFactory>(Microsoft::InformationProtection::CIrmDocumentFactory *)
0x180058012  mov     rbx, qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A+8; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x180058019  mov     rax, qword ptr [rsp+560h+var_528]
0x18005801e  mov     qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A+8, rax; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x180058025  mov     rax, qword ptr [rsp+560h+var_538+8]
0x18005802a  mov     qword ptr cs:?s_IrmDocumentFactory@IIrmDocumentFactory@InformationProtection@Microsoft@@2V?$shared_ptr@VIIrmDocumentFactory@InformationProtection@Microsoft@@@tr1@std@@A, rax; std::tr1::shared_ptr<Microsoft::InformationProtection::IIrmDocumentFactory> Microsoft::InformationProtection::IIrmDocumentFactory::s_IrmDocumentFactory
0x180058031  test    rbx, rbx
0x180058034  jz      short loc_18005806A
0x180058036  mov     eax, esi
0x180058038  lock xadd [rbx+8], eax
0x18005803d  add     eax, esi
0x18005803f  jnz     short loc_18005806A
0x180058041  mov     rax, [rbx]
0x180058044  mov     rcx, rbx
0x180058047  mov     rax, [rax]
0x18005804a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005804f  mov     eax, esi
0x180058051  lock xadd [rbx+0Ch], eax
0x180058056  add     eax, esi
0x180058058  jnz     short loc_18005806A
0x18005805a  mov     rax, [rbx]
0x18005805d  mov     rcx, rbx
0x180058060  mov     rax, [rax+8]
0x180058064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058069  nop
0x18005806a  mov     rcx, r14; lpCriticalSection
0x18005806d  call    cs:__imp_LeaveCriticalSection
0x180058073  nop
0x180058074  mov     rcx, [rsp+560h+bstrString]; bstrString
0x180058079  call    cs:__imp_SysFreeString
0x18005807f  nop
0x180058080  mov     rcx, [rsp+560h+var_510]; bstrString
0x180058085  call    cs:__imp_SysFreeString
0x18005808b  nop
0x18005808c  mov     rax, rdi
0x18005808f  mov     rcx, [rbp+460h+var_30]
0x180058096  xor     rcx, rsp; StackCookie
0x180058099  call    __security_check_cookie
0x18005809e  mov     rbx, [rsp+560h+arg_18]
0x1800580a6  add     rsp, 540h
0x1800580ad  pop     r15
0x1800580af  pop     r14
0x1800580b1  pop     rdi
0x1800580b2  pop     rsi
0x1800580b3  pop     rbp
0x1800580b4  retn
0x1800580b5  lea     rcx, dword_180087498
0x1800580bc  call    _Init_thread_header
0x1800580c1  cmp     cs:dword_180087498, esi
0x1800580c7  jnz     loc_180057F0D
0x1800580cd  mov     rcx, r14; this
0x1800580d0  call    ??0FastMutex@Common@FoundationServices@Microsoft@@QEAA@XZ; Microsoft::FoundationServices::Common::FastMutex::FastMutex(void)
0x1800580d5  lea     rcx, _Microsoft__InformationProtection__CIrmProtectorWrapper__CIrmProtectorWrapper____2____dynamic_atexit_destructor_for__mutex__; void (__cdecl *)()
0x1800580dc  call    atexit
0x1800580e1  nop
0x1800580e2  lea     rcx, dword_180087498
0x1800580e9  call    _Init_thread_footer
0x1800580ee  jmp     loc_180057F0D
0x1800580f3  mov     ecx, 8007000Eh; int
0x1800580f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800580fe  mov     [rsp+20h], eax; int
0x180058102  lea     r9, aPiunknownprote_0; "pIUnknownProtector->QueryInterface(IID_"...
0x180058109  mov     r8d, 35h ; '5'; unsigned int
0x18005810f  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x180058116  lea     rcx, [rsp+560h+pExceptionObject]; this
0x18005811b  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058120  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x180058127  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18005812c  call    _CxxThrowException_0
0x180058132  mov     [rsp+20h], eax; int
0x180058136  lea     r9, aMPirmprotector_1; "m_pIrmProtector->HrInit(&bstrProduct, &"...
0x18005813d  mov     r8d, 37h ; '7'; unsigned int
0x180058143  lea     rdx, aDsSecurityRmSr_3; "ds\\security\\rm\\src\\client\\promethi"...
0x18005814a  lea     rcx, [rsp+560h+pExceptionObject]; this
0x18005814f  call    ??0FsException@Common@FoundationServices@Microsoft@@QEAA@PEBGK0J@Z; Microsoft::FoundationServices::Common::FsException::FsException(ushort const *,ulong,ushort const *,long)
0x180058154  lea     rdx, _TI4?AVFsException@Common@FoundationServices@Microsoft@@; pThrowInfo
0x18005815b  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x180058160  call    _CxxThrowException_0
```
