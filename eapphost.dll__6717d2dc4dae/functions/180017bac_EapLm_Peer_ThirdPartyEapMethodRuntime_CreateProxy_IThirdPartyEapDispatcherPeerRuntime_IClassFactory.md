# EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)

- ea: `0x180017bac`
- end: `0x180017d20`
- name: `?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z`
- size: `372`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, struct IThirdPartyEapDispatcherPeerRuntime **, LPVOID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017930`
- `0x180018020`

## callees

- `0x180004988`
- `0x1800049b0`
- `0x180004b98`
- `0x180009dc4`
- `0x180017bac`
- `0x18001dc50`
- `0x18001dcbc`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017cc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017cc4`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180017c40`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180017c40`

## string_xrefs

- `0x180017d0c`: `COM Error`
- `0x180017d13`: `Create Third Party Proxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        struct IThirdPartyEapDispatcherPeerRuntime **a2,
        LPVOID *a3)
{
  struct IThirdPartyEapDispatcherPeerRuntime *v6; // rax
  struct IThirdPartyEapDispatcherPeerRuntime *v7; // rax
  const struct EapHost::EapMethodType *v8; // rax
  unsigned int v9; // r10d
  DWORD LastError; // eax
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v12[40]; // [rsp+38h] [rbp-28h] BYREF
  struct IThirdPartyEapDispatcherPeerRuntime *v13; // [rsp+80h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0e79d599408d37b150a6010943369b1e_Traceguids);
  }
  v13 = 0;
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v11, (__int64)this + 312);
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
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0e79d599408d37b150a6010943369b1e_Traceguids);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
  ComPointer<IUnknown>::Release(&v13);
}

```

## disassembly

```asm
0x180017bac  mov     [rsp-18h+arg_8], rbx
0x180017bb1  mov     [rsp-18h+arg_10], rsi
0x180017bb6  push    rbp
0x180017bb7  push    rdi
0x180017bb8  push    r15
0x180017bba  mov     rbp, rsp
0x180017bbd  sub     rsp, 60h
0x180017bc1  mov     rdi, r8
0x180017bc4  mov     rsi, rdx
0x180017bc7  mov     rbx, rcx
0x180017bca  lea     r15, WPP_GLOBAL_Control
0x180017bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bd8  cmp     rcx, r15
0x180017bdb  jz      short loc_180017BF8
0x180017bdd  test    byte ptr [rcx+1Ch], 4
0x180017be1  jz      short loc_180017BF8
0x180017be3  mov     edx, 0Eh
0x180017be8  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180017bef  mov     rcx, [rcx+10h]
0x180017bf3  call    WPP_SF_
0x180017bf8  mov     [rbp+arg_0], 0
0x180017c00  lea     rdx, [rbx+138h]
0x180017c07  lea     rcx, [rbp+var_30]
0x180017c0b  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180017c10  nop
0x180017c11  mov     rax, [rbx+130h]
0x180017c18  test    rax, rax
0x180017c1b  jnz     short loc_180017C8A
0x180017c1d  mov     [rbp+arg_18], rax
0x180017c21  lea     rax, [rbp+arg_18]
0x180017c25  mov     [rsp+60h+ppv], rax; ppv
0x180017c2a  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180017c31  xor     r8d, r8d; pvReserved
0x180017c34  mov     edx, 10004h; dwClsContext
0x180017c39  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180017c40  call    cs:__imp_CoGetClassObject
0x180017c46  test    eax, eax
0x180017c48  js      loc_180017D03
0x180017c4e  mov     rcx, [rbp+arg_18]
0x180017c52  mov     rax, [rcx]
0x180017c55  lea     r9, [rbp+arg_0]
0x180017c59  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x180017c60  xor     edx, edx
0x180017c62  mov     rax, [rax+18h]
0x180017c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c6b  mov     r10d, eax
0x180017c6e  test    eax, eax
0x180017c70  js      short loc_180017CE9
0x180017c72  mov     rax, [rbp+arg_0]
0x180017c76  mov     [rbp+arg_0], 0
0x180017c7e  mov     [rsi], rax
0x180017c81  mov     rax, [rbp+arg_18]
0x180017c85  mov     [rdi], rax
0x180017c88  jmp     short loc_180017C94
0x180017c8a  mov     [rsi], rax
0x180017c8d  mov     qword ptr [rdi], 0
0x180017c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c9b  cmp     rcx, r15
0x180017c9e  jz      short loc_180017CBC
0x180017ca0  test    byte ptr [rcx+1Ch], 4
0x180017ca4  jz      short loc_180017CBC
0x180017ca6  mov     edx, 0Fh
0x180017cab  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180017cb2  mov     rcx, [rcx+10h]
0x180017cb6  call    WPP_SF_
0x180017cbb  nop
0x180017cbc  mov     rcx, [rbp+var_30]
0x180017cc0  add     rcx, 10h; lpCriticalSection
0x180017cc4  call    cs:__imp_LeaveCriticalSection
0x180017cca  nop
0x180017ccb  lea     rcx, [rbp+arg_0]
0x180017ccf  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180017cd4  lea     r11, [rsp+60h+var_s0]
0x180017cd9  mov     rbx, [r11+28h]
0x180017cdd  mov     rsi, [r11+30h]
0x180017ce1  mov     rsp, r11
0x180017ce4  pop     r15
0x180017ce6  pop     rdi
0x180017ce7  pop     rbp
0x180017ce8  retn
0x180017ce9  lea     rdx, [rbx+10h]; struct _EAP_METHOD_TYPE *
0x180017ced  lea     rcx, [rbp+var_28]; this
0x180017cf1  call    ??0EapMethodType@EapHost@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapHost::EapMethodType::EapMethodType(_EAP_METHOD_TYPE const &)
0x180017cf6  nop
0x180017cf7  mov     rdx, rax; struct EapHost::EapMethodType *
0x180017cfa  mov     ecx, r10d; unsigned int
0x180017cfd  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
0x180017d03  call    cs:__imp_GetLastError
0x180017d09  mov     r8d, eax; int
0x180017d0c  lea     rdx, aComError; "COM Error"
0x180017d13  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180017d1a  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
