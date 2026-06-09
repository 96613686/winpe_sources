# cdp::Devicelet::DeviceHandler::DeviceHandler(ICDPComDevice *)

- ea: `0x180173a50`
- end: `0x180173bef`
- name: `??0DeviceHandler@Devicelet@cdp@@QEAA@PEAUICDPComDevice@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(cdp::Devicelet::DeviceHandler *__hidden this, struct ICDPComDevice *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180173978`

## callees

- `0x18001ce80`
- `0x18002bbe8`
- `0x1800624cc`
- `0x18008539c`
- `0x180114c58`
- `0x180173a50`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180173bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180173bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180173bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180173bc8`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180173afe`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180173afe`

## string_xrefs

- `0x180173b1a`: `Failed to store ICDPComDevice in global interface table`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
cdp::Devicelet::DeviceHandler *__fastcall cdp::Devicelet::DeviceHandler::DeviceHandler(
        cdp::Devicelet::DeviceHandler *this,
        struct ICDPComDevice *a2,
        __int64 a3)
{
  char *v5; // r14
  char *v6; // r15
  cdp::Devicelet::DeviceHandler **v7; // rax
  cdp::Devicelet::DeviceHandler **v8; // rsi
  int AgileReference; // eax
  __int64 v10; // rax
  const char *v12; // [rsp+28h] [rbp-50h] BYREF
  int v13; // [rsp+30h] [rbp-48h]
  _BYTE v14[64]; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+40h] BYREF
  LPVOID v16; // [rsp+C0h] [rbp+48h] BYREF
  cdp::Devicelet::DeviceHandler *v17; // [rsp+C8h] [rbp+50h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = (char *)this + 24;
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 15;
  *((_BYTE *)this + 24) = 0;
  v6 = (char *)this + 56;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 15;
  *((_BYTE *)this + 56) = 0;
  if ( a2 )
    (*(void (__fastcall **)(struct ICDPComDevice *))(*(_QWORD *)a2 + 8LL))(a2);
  v17 = this;
  v7 = (cdp::Devicelet::DeviceHandler **)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(
                                           &v17,
                                           a2,
                                           a3);
  v8 = v7;
  if ( a2 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v7);
    AgileReference = RoGetAgileReference(0, &GUID_4389de91_3314_4fe7_bff1_73fbc7ef1f32, a2, v8);
    if ( AgileReference < 0 )
    {
      v12 = "onecoreuap\\windows\\cdp\\core\\private\\onecore\\Devicelet.h";
      v13 = 70;
      v10 = cdp::MakeException<cdp::hresult_exception,>(
              v14,
              &v12,
              (unsigned int)AgileReference,
              "Failed to store ICDPComDevice in global interface table");
      cdp::CdpThrow<cdp::hresult_exception>(&v12, v10);
    }
  }
  else
  {
    v17 = *v7;
    *v7 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  }
  v16 = 0;
  if ( (*(int (__fastcall **)(struct ICDPComDevice *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, &v16) >= 0 )
    std::string::assign(v5, v16);
  pv = 0;
  if ( (*(int (__fastcall **)(struct ICDPComDevice *, LPVOID *))(*(_QWORD *)a2 + 104LL))(a2, &pv) >= 0 )
    std::string::assign(v6, pv);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v16 )
    CoTaskMemFree(v16);
  (*(void (__fastcall **)(struct ICDPComDevice *))(*(_QWORD *)a2 + 16LL))(a2);
  return this;
}

```

## disassembly

```asm
0x180173a50  mov     [rsp-30h+arg_0], rcx
0x180173a55  push    rbp
0x180173a56  push    rbx
0x180173a57  push    rsi
0x180173a58  push    rdi
0x180173a59  push    r14
0x180173a5b  push    r15
0x180173a5d  mov     rbp, rsp
0x180173a60  sub     rsp, 78h
0x180173a64  mov     rbx, rdx
0x180173a67  mov     rdi, rcx
0x180173a6a  mov     qword ptr [rcx], 0
0x180173a71  mov     qword ptr [rcx+8], 0
0x180173a79  mov     qword ptr [rcx+10h], 0
0x180173a81  lea     r14, [rcx+18h]
0x180173a85  xorps   xmm0, xmm0
0x180173a88  movups  xmmword ptr [r14], xmm0
0x180173a8c  mov     qword ptr [r14+10h], 0
0x180173a94  mov     eax, 0Fh
0x180173a99  mov     [r14+18h], rax
0x180173a9d  mov     byte ptr [r14], 0
0x180173aa1  lea     r15, [rcx+38h]
0x180173aa5  movups  xmmword ptr [r15], xmm0
0x180173aa9  mov     qword ptr [r15+10h], 0
0x180173ab1  mov     [r15+18h], rax
0x180173ab5  mov     byte ptr [r15], 0
0x180173ab9  mov     [rbp+var_58], rdx
0x180173abd  test    rdx, rdx
0x180173ac0  jz      short loc_180173AD2
0x180173ac2  mov     rax, [rdx]
0x180173ac5  mov     rcx, rdx
0x180173ac8  mov     rax, [rax+8]
0x180173acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173ad1  nop
0x180173ad2  mov     [rbp+arg_18], rdi
0x180173ad6  lea     rcx, [rbp+arg_18]
0x180173ada  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x180173adf  mov     rsi, rax
0x180173ae2  test    rbx, rbx
0x180173ae5  jz      short loc_180173B3F
0x180173ae7  mov     rcx, rax
0x180173aea  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180173aef  mov     r9, rsi
0x180173af2  mov     r8, rbx
0x180173af5  lea     rdx, _GUID_4389de91_3314_4fe7_bff1_73fbc7ef1f32
0x180173afc  xor     ecx, ecx
0x180173afe  call    cs:__imp_RoGetAgileReference
0x180173b04  test    eax, eax
0x180173b06  jns     short loc_180173B57
0x180173b08  lea     rcx, aOnecoreuapWind_61; "onecoreuap\\windows\\cdp\\core\\private"...
0x180173b0f  mov     [rbp+var_50], rcx
0x180173b13  mov     [rbp+var_48], 46h ; 'F'
0x180173b1a  lea     r9, aFailedToStoreI_0; "Failed to store ICDPComDevice in global"...
0x180173b21  mov     r8d, eax
0x180173b24  lea     rdx, [rbp+var_50]
0x180173b28  lea     rcx, [rbp+var_40]
0x180173b2c  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x180173b31  nop
0x180173b32  mov     rdx, rax
0x180173b35  lea     rcx, [rbp+var_50]
0x180173b39  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x180173b3f  mov     rax, [rax]
0x180173b42  mov     [rbp+arg_18], rax
0x180173b46  mov     qword ptr [rsi], 0
0x180173b4d  lea     rcx, [rbp+arg_18]
0x180173b51  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180173b56  nop
0x180173b57  mov     [rbp+arg_10], 0
0x180173b5f  mov     rax, [rbx]
0x180173b62  lea     rdx, [rbp+arg_10]
0x180173b66  mov     rcx, rbx
0x180173b69  mov     rax, [rax+18h]
0x180173b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173b72  test    eax, eax
0x180173b74  js      short loc_180173B83
0x180173b76  mov     rdx, [rbp+arg_10]
0x180173b7a  mov     rcx, r14
0x180173b7d  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180173b82  nop
0x180173b83  mov     [rbp+pv], 0
0x180173b8b  mov     rax, [rbx]
0x180173b8e  lea     rdx, [rbp+pv]
0x180173b92  mov     rcx, rbx
0x180173b95  mov     rax, [rax+68h]
0x180173b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173b9e  test    eax, eax
0x180173ba0  js      short loc_180173BAF
0x180173ba2  mov     rdx, [rbp+pv]
0x180173ba6  mov     rcx, r15
0x180173ba9  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180173bae  nop
0x180173baf  mov     rcx, [rbp+pv]; pv
0x180173bb3  test    rcx, rcx
0x180173bb6  jz      short loc_180173BBF
0x180173bb8  call    cs:__imp_CoTaskMemFree
0x180173bbe  nop
0x180173bbf  mov     rcx, [rbp+arg_10]; pv
0x180173bc3  test    rcx, rcx
0x180173bc6  jz      short loc_180173BCF
0x180173bc8  call    cs:__imp_CoTaskMemFree
0x180173bce  nop
0x180173bcf  mov     rax, [rbx]
0x180173bd2  mov     rcx, rbx
0x180173bd5  mov     rax, [rax+10h]
0x180173bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180173bde  nop
0x180173bdf  mov     rax, rdi
0x180173be2  add     rsp, 78h
0x180173be6  pop     r15
0x180173be8  pop     r14
0x180173bea  pop     rdi
0x180173beb  pop     rsi
0x180173bec  pop     rbx
0x180173bed  pop     rbp
0x180173bee  retn
```
