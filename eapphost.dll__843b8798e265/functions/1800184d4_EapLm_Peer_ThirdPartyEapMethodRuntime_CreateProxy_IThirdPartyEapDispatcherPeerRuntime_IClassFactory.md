# EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)

- ea: `0x1800184d4`
- end: `0x18001865b`
- name: `?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z`
- size: `391`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *__hidden this, struct IThirdPartyEapDispatcherPeerRuntime **, struct IClassFactory **)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018250`
- `0x180018990`

## callees

- `0x180004af8`
- `0x180004b24`
- `0x180004d1c`
- `0x18000a21c`
- `0x1800184d4`
- `0x18001e754`
- `0x18001e7c0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018638`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800185f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800185f2`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180018568`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180018568`

## string_xrefs

- `0x180018647`: `COM Error`
- `0x18001864e`: `Create Third Party Proxy`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800184d4  mov     [rsp-18h+arg_8], rbx
0x1800184d9  mov     [rsp-18h+arg_10], rsi
0x1800184de  push    rbp
0x1800184df  push    rdi
0x1800184e0  push    r15
0x1800184e2  mov     rbp, rsp
0x1800184e5  sub     rsp, 60h
0x1800184e9  mov     rdi, r8
0x1800184ec  mov     rsi, rdx
0x1800184ef  mov     rbx, rcx
0x1800184f2  lea     r15, WPP_GLOBAL_Control
0x1800184f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018500  cmp     rcx, r15
0x180018503  jz      short loc_180018520
0x180018505  test    byte ptr [rcx+1Ch], 4
0x180018509  jz      short loc_180018520
0x18001850b  mov     edx, 0Eh
0x180018510  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018517  mov     rcx, [rcx+10h]
0x18001851b  call    WPP_SF_
0x180018520  mov     [rbp+arg_0], 0
0x180018528  lea     rdx, [rbx+138h]
0x18001852f  lea     rcx, [rbp+var_30]
0x180018533  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x180018538  nop
0x180018539  mov     rax, [rbx+130h]
0x180018540  test    rax, rax
0x180018543  jnz     short loc_1800185B8
0x180018545  mov     [rbp+arg_18], rax
0x180018549  lea     rax, [rbp+arg_18]
0x18001854d  mov     [rsp+60h+ppv], rax; ppv
0x180018552  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180018559  xor     r8d, r8d; pvReserved
0x18001855c  mov     edx, 10004h; dwClsContext
0x180018561  lea     rcx, _GUID_87bb326b_e4a0_4de1_94f0_b9f41d0c6059; rclsid
0x180018568  call    cs:__imp_CoGetClassObject
0x18001856f  nop     dword ptr [rax+rax+00h]
0x180018574  test    eax, eax
0x180018576  js      loc_180018638
0x18001857c  mov     rcx, [rbp+arg_18]
0x180018580  mov     rax, [rcx]
0x180018583  lea     r9, [rbp+arg_0]
0x180018587  lea     r8, _GUID_c48ca462_67fb_4c12_a21a_6415460fa8ae
0x18001858e  xor     edx, edx
0x180018590  mov     rax, [rax+18h]
0x180018594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018599  mov     r10d, eax
0x18001859c  test    eax, eax
0x18001859e  js      short loc_18001861E
0x1800185a0  mov     rax, [rbp+arg_0]
0x1800185a4  mov     [rbp+arg_0], 0
0x1800185ac  mov     [rsi], rax
0x1800185af  mov     rax, [rbp+arg_18]
0x1800185b3  mov     [rdi], rax
0x1800185b6  jmp     short loc_1800185C2
0x1800185b8  mov     [rsi], rax
0x1800185bb  mov     qword ptr [rdi], 0
0x1800185c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185c9  cmp     rcx, r15
0x1800185cc  jz      short loc_1800185EA
0x1800185ce  test    byte ptr [rcx+1Ch], 4
0x1800185d2  jz      short loc_1800185EA
0x1800185d4  mov     edx, 0Fh
0x1800185d9  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x1800185e0  mov     rcx, [rcx+10h]
0x1800185e4  call    WPP_SF_
0x1800185e9  nop
0x1800185ea  mov     rcx, [rbp+var_30]
0x1800185ee  add     rcx, 10h; lpCriticalSection
0x1800185f2  call    cs:__imp_LeaveCriticalSection
0x1800185f9  nop     dword ptr [rax+rax+00h]
0x1800185fe  nop
0x1800185ff  lea     rcx, [rbp+arg_0]
0x180018603  call    ?Release@?$ComPointer@UIUnknown@@@@AEAAXXZ; ComPointer<IUnknown>::Release(void)
0x180018608  lea     r11, [rsp+60h+var_s0]
0x18001860d  mov     rbx, [r11+28h]
0x180018611  mov     rsi, [r11+30h]
0x180018615  mov     rsp, r11
0x180018618  pop     r15
0x18001861a  pop     rdi
0x18001861b  pop     rbp
0x18001861c  retn
0x18001861e  lea     rdx, [rbx+10h]; struct _EAP_METHOD_TYPE *
0x180018622  lea     rcx, [rbp+var_28]; this
0x180018626  call    ??0EapMethodType@EapHost@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapHost::EapMethodType::EapMethodType(_EAP_METHOD_TYPE const &)
0x18001862b  nop
0x18001862c  mov     rdx, rax; struct EapHost::EapMethodType *
0x18001862f  mov     ecx, r10d; unsigned int
0x180018632  call    ?Throw@EapException@EapHost@@SAXJAEBVEapMethodType@2@@Z; EapHost::EapException::Throw(long,EapHost::EapMethodType const &)
0x180018638  call    cs:__imp_GetLastError
0x18001863f  nop     dword ptr [rax+rax+00h]
0x180018644  mov     r8d, eax; int
0x180018647  lea     rdx, aComError; "COM Error"
0x18001864e  lea     rcx, aCreateThirdPar; "Create Third Party Proxy"
0x180018655  call    ?Throw@EapException@EapHost@@SAXPEB_W0J@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,long)
```
