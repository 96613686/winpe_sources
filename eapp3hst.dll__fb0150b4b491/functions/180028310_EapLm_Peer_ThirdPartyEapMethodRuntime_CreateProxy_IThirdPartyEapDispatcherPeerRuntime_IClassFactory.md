# EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)

- ea: `0x180028310`
- end: `0x180028484`
- name: `?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z`
- size: `372`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, struct IThirdPartyEapDispatcherPeerRuntime **, LPVOID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800280d0`
- `0x1800287c0`

## callees

- `0x180004ec0`
- `0x180005994`
- `0x18000d0e8`
- `0x180012d18`
- `0x1800154c8`
- `0x180015534`
- `0x180028310`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028428`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028467`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800283a4`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800283a4`

## string_xrefs

- `0x180028470`: `COM Error`
- `0x180028477`: `Create Third Party Proxy`

## pseudocode

```c
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct IThirdPartyEapDispatcherPeerRuntime **a2,
        LPVOID *a3)
{
  struct IThirdPartyEapDispatcherPeerRuntime *v6; // rax
  struct IThirdPartyEapDispatcherPeerRuntime *v7; // rax
  const struct EapHost::EapMethodType *v8; // rax
  unsigned int v9; // r9d
  DWORD LastError; // eax
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v12[40]; // [rsp+38h] [rbp-28h] BYREF
  struct IThirdPartyEapDispatcherPeerRuntime *v13; // [rsp+80h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0e79d599408d37b150a6010943369b1e_Traceguids);
  v13 = 0;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v11, (char *)this + 312);
  v6 = (struct IThirdPartyEapDispatcherPeerRuntime *)*((_QWORD *)this + 38);
  if ( v6 )
  {
    *a2 = v6;
    *a3 = 0;
  }
  else
  {
    ppv = 0;
    if ( CoGetClassObject(
           &GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059,
           0x10004u,
           0,
           &GUID_00000001_0000_0000_c000_000000000046,
           &ppv) < 0 )
    {
      LastError = GetLastError();
      EapHost::EapException::Throw(L"Create Third Party Proxy", L"COM Error", LastError);
    }
    if ( (*(int (__fastcall **)(LPVOID, _QWORD, GUID *, struct IThirdPartyEapDispatcherPeerRuntime **))(*(_QWORD *)ppv + 24LL))(
           ppv,
           0,
           &GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae,
           &v13) < 0 )
    {
      v8 = (const struct EapHost::EapMethodType *)EapHost::EapMethodType::EapMethodType(
                                                    (EapHost::EapMethodType *)v12,
                                                    (const struct _EAP_METHOD_TYPE *)this + 1);
      EapHost::EapException::Throw(v9, v8);
    }
    v7 = v13;
    v13 = 0;
    *a2 = v7;
    *a3 = ppv;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0e79d599408d37b150a6010943369b1e_Traceguids);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v13);
}

```

## disassembly

```asm
0x180028310  mov     [rsp-18h+arg_8], rbx
0x180028315  mov     [rsp-18h+arg_10], rsi
0x18002831a  push    rbp
0x18002831b  push    rdi
0x18002831c  push    r15
0x18002831e  mov     rbp, rsp
0x180028321  sub     rsp, 60h
0x180028325  mov     rdi, r8
0x180028328  mov     rsi, rdx
0x18002832b  mov     rbx, rcx
0x18002832e  lea     r15, WPP_GLOBAL_Control
0x180028335  mov     rcx, cs:WPP_GLOBAL_Control
0x18002833c  cmp     rcx, r15
0x18002833f  jz      short loc_18002835C
0x180028341  test    byte ptr [rcx+1Ch], 4
0x180028345  jz      short loc_18002835C
0x180028347  mov     edx, 0Eh
0x18002834c  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180028353  mov     rcx, [rcx+10h]
0x180028357  call    WPP_SF_
0x18002835c  mov     [rbp+arg_0], 0
0x180028364  lea     rdx, [rbx+138h]
0x18002836b  lea     rcx, [rbp+var_30]
0x18002836f  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180028374  nop
0x180028375  mov     rax, [rbx+130h]
0x18002837c  test    rax, rax
0x18002837f  jnz     short loc_1800283EE
0x180028381  mov     [rbp+arg_18], rax
0x180028385  lea     rax, [rbp+arg_18]
0x180028389  mov     [rsp+60h+ppv], rax; ppv
0x18002838e  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180028395  xor     r8d, r8d; pvReserved
0x180028398  mov     edx, 10004h; dwClsContext
0x18002839d  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x1800283a4  call    cs:__imp_CoGetClassObject
0x1800283aa  test    eax, eax
0x1800283ac  js      loc_180028467
0x1800283b2  mov     rcx, [rbp+arg_18]
0x1800283b6  mov     rax, [rcx]
0x1800283b9  lea     r9, [rbp+arg_0]
0x1800283bd  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x1800283c4  xor     edx, edx
0x1800283c6  mov     rax, [rax+18h]
0x1800283ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283cf  mov     r9d, eax
0x1800283d2  test    eax, eax
0x1800283d4  js      short loc_18002844D
0x1800283d6  mov     rax, [rbp+arg_0]
0x1800283da  mov     [rbp+arg_0], 0
0x1800283e2  mov     [rsi], rax
0x1800283e5  mov     rax, [rbp+arg_18]
0x1800283e9  mov     [rdi], rax
0x1800283ec  jmp     short loc_1800283F8
0x1800283ee  mov     [rsi], rax
0x1800283f1  mov     qword ptr [rdi], 0
0x1800283f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283ff  cmp     rcx, r15
0x180028402  jz      short loc_180028420
0x180028404  test    byte ptr [rcx+1Ch], 4
0x180028408  jz      short loc_180028420
0x18002840a  mov     edx, 0Fh
0x18002840f  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180028416  mov     rcx, [rcx+10h]
0x18002841a  call    WPP_SF_
0x18002841f  nop
0x180028420  mov     rcx, [rbp+var_30]
0x180028424  add     rcx, 10h; lpCriticalSection
0x180028428  call    cs:__imp_LeaveCriticalSection
0x18002842e  nop
0x18002842f  lea     rcx, [rbp+arg_0]
0x180028433  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180028438  lea     r11, [rsp+60h+var_s0]
0x18002843d  mov     rbx, [r11+28h]
0x180028441  mov     rsi, [r11+30h]
0x180028445  mov     rsp, r11
0x180028448  pop     r15
0x18002844a  pop     rdi
0x18002844b  pop     rbp
0x18002844c  retn
0x18002844d  lea     rdx, [rbx+10h]; struct _EAP_METHOD_TYPE *
0x180028451  lea     rcx, [rbp+var_28]; this
0x180028455  call    ??0EapMethodType@EapHost@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapHost::EapMethodType::EapMethodType(_EAP_METHOD_TYPE const &)
0x18002845a  nop
0x18002845b  mov     rdx, rax; struct EapHost::EapMethodType *
0x18002845e  mov     ecx, r9d; unsigned int
0x180028461  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
0x180028467  call    cs:__imp_GetLastError
0x18002846d  mov     r8d, eax; int
0x180028470  lea     rdx, aComError; "COM Error"
0x180028477  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x18002847e  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
