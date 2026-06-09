# DeviceCert::GetDeviceCert(CertStore &,std::shared_ptr<_CERT_CONTEXT const> &,ILogContext *)

- ea: `0x14002a520`
- end: `0x14002a613`
- name: `?GetDeviceCert@DeviceCert@@AEAAXAEAVCertStore@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@PEAVILogContext@@@Z`
- size: `243`
- prototype: `void __fastcall(_QWORD *, __int64, _QWORD *, const struct ILogContext *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140029d48`
- `0x14002aa18`

## callees

- `0x14000c7d8`
- `0x14000e000`
- `0x14002a520`
- `0x14002a61c`
- `0x14002a728`
- `0x14002b1f4`
- `0x14002c3e8`

## string_xrefs

- `0x14002a54f`: `Work place join device certificate info is not found with registry info.`

## pseudocode

```c
void __fastcall DeviceCert::GetDeviceCert(_QWORD *a1, __int64 a2, _QWORD *a3, const struct ILogContext *a4)
{
  __int64 v8; // rcx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  if ( !*(_DWORD *)(*a1 - 16LL) )
    DeviceCert::GetDeviceCertWithRegistryInfo();
  if ( !*a3 )
  {
    Log::Verbose(a4, L"Work place join device certificate info is not found with registry info.");
    if ( *(_DWORD *)(*a1 - 16LL) )
    {
      Log::Verbose(a4, L"Device certificate thumbprint is not empty %s");
      DeviceCert::GetDeviceCertWithThumbPrint(v8, a2, a3, *a1, a4);
      if ( !*a3 )
      {
        Log::Verbose(a4, L"Work place join device certificate is not found with thumbprint %s", *a1);
        if ( *(_DWORD *)(a1[1] - 16LL) )
        {
          Log::Verbose(a4, L"Device certificate thumbprint is not empty %s", *a1);
          if ( !*(_DWORD *)(a1[1] - 16LL) )
          {
            Log::Verbose(a4, L"GetDeviceCertWithIssuer: Issuer is not set.");
            InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418262);
            throw (InvalidCallException *)pExceptionObject;
          }
          CertStore::FindCertificateWithIssuer(a2, a1 + 1, a3);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002a520  push    rbx
0x14002a522  push    rbp
0x14002a523  push    rsi
0x14002a524  push    rdi
0x14002a525  push    r14
0x14002a527  sub     rsp, 40h
0x14002a52b  mov     rax, [rcx]
0x14002a52e  mov     rbx, r9
0x14002a531  mov     rsi, r8
0x14002a534  mov     rbp, rdx
0x14002a537  mov     rdi, rcx
0x14002a53a  cmp     dword ptr [rax-10h], 0
0x14002a53e  jnz     short loc_14002A545
0x14002a540  call    ?GetDeviceCertWithRegistryInfo@DeviceCert@@AEAAXAEAVCertStore@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@PEAVILogContext@@@Z; DeviceCert::GetDeviceCertWithRegistryInfo(CertStore &,std::shared_ptr<_CERT_CONTEXT const> &,ILogContext *)
0x14002a545  cmp     qword ptr [rsi], 0
0x14002a549  jnz     loc_14002A5D8
0x14002a54f  lea     rdx, aWorkPlaceJoinD_0; "Work place join device certificate info"...
0x14002a556  mov     rcx, rbx; struct ILogContext *
0x14002a559  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002a55e  mov     r8, [rdi]
0x14002a561  cmp     dword ptr [r8-10h], 0
0x14002a566  jz      short loc_14002A5D8
0x14002a568  lea     rdx, aDeviceCertific; "Device certificate thumbprint is not em"...
0x14002a56f  mov     rcx, rbx; struct ILogContext *
0x14002a572  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002a577  mov     r9, [rdi]
0x14002a57a  mov     r8, rsi
0x14002a57d  mov     rdx, rbp
0x14002a580  mov     [rsp+68h+var_48], rbx
0x14002a585  call    ?GetDeviceCertWithThumbPrint@DeviceCert@@AEAAXAEAVCertStore@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@PEBGPEAVILogContext@@@Z; DeviceCert::GetDeviceCertWithThumbPrint(CertStore &,std::shared_ptr<_CERT_CONTEXT const> &,ushort const *,ILogContext *)
0x14002a58a  cmp     qword ptr [rsi], 0
0x14002a58e  jnz     short loc_14002A5D8
0x14002a590  mov     r8, [rdi]
0x14002a593  lea     rdx, aWorkPlaceJoinD; "Work place join device certificate is n"...
0x14002a59a  mov     rcx, rbx; struct ILogContext *
0x14002a59d  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002a5a2  lea     r14, [rdi+8]
0x14002a5a6  mov     rax, [r14]
0x14002a5a9  cmp     dword ptr [rax-10h], 0
0x14002a5ad  jz      short loc_14002A5D8
0x14002a5af  mov     r8, [rdi]
0x14002a5b2  lea     rdx, aDeviceCertific; "Device certificate thumbprint is not em"...
0x14002a5b9  mov     rcx, rbx; struct ILogContext *
0x14002a5bc  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002a5c1  mov     rax, [r14]
0x14002a5c4  cmp     dword ptr [rax-10h], 0
0x14002a5c8  jz      short loc_14002A5E3
0x14002a5ca  mov     r8, rsi
0x14002a5cd  mov     rdx, r14
0x14002a5d0  mov     rcx, rbp
0x14002a5d3  call    ?FindCertificateWithIssuer@CertStore@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$shared_ptr@$$CBU_CERT_CONTEXT@@@std@@@Z; CertStore::FindCertificateWithIssuer(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::shared_ptr<_CERT_CONTEXT const> &)
0x14002a5d8  add     rsp, 40h
0x14002a5dc  pop     r14
0x14002a5de  pop     rdi
0x14002a5df  pop     rsi
0x14002a5e0  pop     rbp
0x14002a5e1  pop     rbx
0x14002a5e2  retn
0x14002a5e3  lea     rdx, aGetdevicecertw; "GetDeviceCertWithIssuer: Issuer is not "...
0x14002a5ea  mov     rcx, rbx; struct ILogContext *
0x14002a5ed  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002a5f2  mov     edx, 0CAA1006Ah; unsigned int
0x14002a5f7  lea     rcx, [rsp+68h+pExceptionObject]; this
0x14002a5fc  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x14002a601  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x14002a608  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14002a60d  call    _CxxThrowException_0
```
