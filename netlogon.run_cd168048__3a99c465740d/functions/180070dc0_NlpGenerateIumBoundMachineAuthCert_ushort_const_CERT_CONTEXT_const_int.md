# NlpGenerateIumBoundMachineAuthCert(ushort const *,_CERT_CONTEXT const * *,int *)

- ea: `0x180070dc0`
- end: `0x18007116a`
- name: `?NlpGenerateIumBoundMachineAuthCert@@YAKPEBGPEAPEBU_CERT_CONTEXT@@PEAH@Z`
- size: `938`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const struct _CERT_CONTEXT **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002d098`

## callees

- `0x180007518`
- `0x180070dc0`
- `0x18008a45c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007111a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180071130`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007111a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180071130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071081`
- `RPCRT4!RpcStringFreeW` at `0x180070e91`
- `RPCRT4!RpcStringFreeW` at `0x180070e91`
- `RPCRT4!RpcBindingFree` at `0x180071149`
- `RPCRT4!RpcBindingFree` at `0x180071149`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180070e7e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180070e7e`
- `RPCRT4!NdrClientCall3` at `0x180070ee1`
- `RPCRT4!NdrClientCall3` at `0x180070ff6`
- `RPCRT4!NdrClientCall3` at `0x180070ee1`
- `RPCRT4!NdrClientCall3` at `0x180070ff6`
- `RPCRT4!RpcStringBindingComposeW` at `0x180070e42`
- `RPCRT4!RpcStringBindingComposeW` at `0x180070e42`
- `RPCRT4!RpcExceptionFilter` at `0x1800903de`
- `RPCRT4!RpcExceptionFilter` at `0x180090400`
- `RPCRT4!RpcExceptionFilter` at `0x1800903de`
- `RPCRT4!RpcExceptionFilter` at `0x180090400`
- `ntdll!RtlNtStatusToDosError` at `0x180070f16`
- `ntdll!RtlNtStatusToDosError` at `0x18007102e`
- `ntdll!RtlNtStatusToDosError` at `0x1800710c4`
- `ntdll!RtlNtStatusToDosError` at `0x180070f16`
- `ntdll!RtlNtStatusToDosError` at `0x18007102e`
- `ntdll!RtlNtStatusToDosError` at `0x1800710c4`
- `CRYPT32!CertFreeCertificateContext` at `0x180071101`
- `CRYPT32!CertFreeCertificateContext` at `0x180071101`
- `CRYPT32!CertCreateCertificateContext` at `0x18007106d`
- `CRYPT32!CertCreateCertificateContext` at `0x18007106d`

## string_xrefs

- `0x180070e54`: `%hs: Error composing string binding: %d\n`
- `0x180070f03`: `%hs: ProvIumCreateMachineKey returned 0x%x\n`
- `0x18007101b`: `%hs: ProvIumCreateMachineSelfSignedCertificate returned 0x%x\n`

## pseudocode

```c
__int64 __fastcall NlpGenerateIumBoundMachineAuthCert(
        const unsigned __int16 *a1,
        const struct _CERT_CONTEXT **a2,
        int *a3)
{
  PCCERT_CONTEXT CertificateContext; // r14
  DWORD LastError; // eax
  ULONG v8; // edi
  unsigned __int16 *v9; // rdx
  CLIENT_CALL_RETURN v10; // rax
  NTSTATUS Pointer; // ebx
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  NTSTATUS v15; // ebx
  NTSTATUS v16; // eax
  unsigned int v17; // ebx
  RPC_WSTR Options; // [rsp+20h] [rbp-A8h]
  RPC_WSTR Optionsa; // [rsp+20h] [rbp-A8h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-70h] BYREF
  BYTE *pbCertEncoded; // [rsp+60h] [rbp-68h] BYREF
  RPC_WSTR String[2]; // [rsp+68h] [rbp-60h] BYREF
  CLIENT_CALL_RETURN v24; // [rsp+78h] [rbp-50h]
  _OWORD v25[4]; // [rsp+80h] [rbp-48h] BYREF
  DWORD cbCertEncoded; // [rsp+E8h] [rbp+20h] BYREF

  Binding = 0;
  String[0] = 0;
  pbCertEncoded = 0;
  cbCertEncoded = 0;
  CertificateContext = 0;
  String[1] = 0;
  v25[0] = 0;
  *a3 = 1;
  *a2 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, String);
  v8 = LastError;
  if ( LastError )
  {
    v9 = L"%hs: Error composing string binding: %d\n";
LABEL_3:
    NlPrintRoutine(0x800u, v9, "NlpGenerateIumBoundMachineAuthCert", LastError);
    goto LABEL_22;
  }
  v8 = RpcBindingFromStringBindingW(String[0], &Binding);
  RpcStringFreeW(String);
  if ( v8 )
  {
    NlPrintRoutine(0x800u, L"%hs: Error creating RPC binding: %d\n", "NlpGenerateIumBoundMachineAuthCert", v8);
    goto LABEL_22;
  }
  v24.Simple = 0;
  v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&ProvIum_ProxyInfo, 0, 0, Binding, v25, (char *)v25 + 8).Pointer;
  Pointer = (NTSTATUS)v10.Pointer;
  v24.Pointer = v10.Pointer;
  if ( SLODWORD(v10.Simple) < 0 )
  {
    NlPrintRoutine(
      0x800u,
      L"%hs: ProvIumCreateMachineKey returned 0x%x\n",
      "NlpGenerateIumBoundMachineAuthCert",
      LODWORD(v10.Pointer));
    v8 = RtlNtStatusToDosError(Pointer);
  }
  v12 = v8 - 1708;
  if ( (unsigned int)v12 <= 0x2D )
  {
    v13 = 0x200000004201LL;
    if ( _bittest64(&v13, v12) )
    {
      NlPrintRoutine(
        0x800u,
        L"%hs: Provisioning interface not responding; treating as if IUM weren't available: %d\n",
        "NlpGenerateIumBoundMachineAuthCert",
        v8);
      *a3 = 0;
      goto LABEL_22;
    }
  }
  if ( v8 )
    goto LABEL_13;
  LODWORD(Options) = v25[0];
  v14 = (unsigned int)NdrClientCall3(
                        (MIDL_STUBLESS_PROXY_INFO *)&ProvIum_ProxyInfo,
                        1u,
                        0,
                        Binding,
                        Options,
                        *((_QWORD *)&v25[0] + 1),
                        a1,
                        &cbCertEncoded,
                        &pbCertEncoded).Pointer;
  v15 = v14;
  if ( v14 < 0 )
  {
    NlPrintRoutine(
      0x800u,
      L"%hs: ProvIumCreateMachineSelfSignedCertificate returned 0x%x\n",
      "NlpGenerateIumBoundMachineAuthCert",
      (unsigned int)v14);
    v8 = RtlNtStatusToDosError(v15);
  }
  if ( v8 )
  {
LABEL_13:
    NlPrintRoutine(0x800u, L"%hs: Error calling provisioning interface: %d\n", "NlpGenerateIumBoundMachineAuthCert", v8);
    goto LABEL_22;
  }
  CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    v8 = LastError;
    v9 = L"%hs: Error creating certificate context: %d\n";
    goto LABEL_3;
  }
  v16 = LsaSetMachineCertificate(cbCertEncoded, pbCertEncoded, LODWORD(v25[0]), *((_QWORD *)&v25[0] + 1));
  v17 = v16;
  if ( v16 >= 0 )
  {
    *a2 = CertificateContext;
    CertificateContext = 0;
  }
  else
  {
    v8 = RtlNtStatusToDosError(v16);
    LODWORD(Optionsa) = v8;
    NlPrintRoutine(
      0x800u,
      L"%hs: LsaSetMachineCertificate failed with 0x%x (%d)\n.",
      "NlpGenerateIumBoundMachineAuthCert",
      v17,
      Optionsa);
  }
LABEL_22:
  if ( CertificateContext )
    CertFreeCertificateContext(CertificateContext);
  if ( *((_QWORD *)&v25[0] + 1) )
    free(*((void **)&v25[0] + 1));
  if ( pbCertEncoded )
    free(pbCertEncoded);
  if ( Binding )
    RpcBindingFree(&Binding);
  return v8;
}

```

## disassembly

```asm
0x180070dc0  mov     rax, rsp
0x180070dc3  mov     [rax+18h], r8
0x180070dc7  mov     [rax+10h], rdx
0x180070dcb  mov     [rax+8], rcx
0x180070dcf  push    rbx
0x180070dd0  push    rdi
0x180070dd1  push    r12
0x180070dd3  push    r13
0x180070dd5  push    r14
0x180070dd7  push    r15
0x180070dd9  sub     rsp, 98h
0x180070de0  mov     r12, r8
0x180070de3  mov     r15, rdx
0x180070de6  mov     r13, rcx
0x180070de9  mov     qword ptr [rax-70h], 0
0x180070df1  mov     qword ptr [rax-60h], 0
0x180070df9  mov     qword ptr [rax-68h], 0
0x180070e01  mov     dword ptr [rax+20h], 0
0x180070e08  xor     r14d, r14d
0x180070e0b  mov     [rsp+0C8h+var_58], r14
0x180070e10  xorps   xmm0, xmm0
0x180070e13  movups  xmmword ptr [rax-48h], xmm0
0x180070e17  mov     dword ptr [r8], 1
0x180070e1e  mov     [rdx], r14
0x180070e21  lea     rax, [rax-60h]
0x180070e25  mov     [rsp+0C8h+StringBinding], rax; StringBinding
0x180070e2a  mov     [rsp+0C8h+Options], r14; Options
0x180070e2f  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x180070e36  xor     r8d, r8d; NetworkAddr
0x180070e39  lea     rdx, ProtSeq; "ncalrpc"
0x180070e40  xor     ecx, ecx; ObjUuid
0x180070e42  call    cs:__imp_RpcStringBindingComposeW
0x180070e49  nop     dword ptr [rax+rax+00h]
0x180070e4e  mov     edi, eax
0x180070e50  test    eax, eax
0x180070e52  jz      short loc_180070E74
0x180070e54  lea     rdx, aHsErrorComposi; "%hs: Error composing string binding: %d"...
0x180070e5b  mov     r9d, eax
0x180070e5e  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x180070e65  mov     ecx, 800h; unsigned int
0x180070e6a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070e6f  jmp     loc_1800710F9
0x180070e74  lea     rdx, [rsp+0C8h+Binding]; Binding
0x180070e79  mov     rcx, [rsp+0C8h+String]; StringBinding
0x180070e7e  call    cs:__imp_RpcBindingFromStringBindingW
0x180070e85  nop     dword ptr [rax+rax+00h]
0x180070e8a  mov     edi, eax
0x180070e8c  lea     rcx, [rsp+0C8h+String]; String
0x180070e91  call    cs:__imp_RpcStringFreeW
0x180070e98  nop     dword ptr [rax+rax+00h]
0x180070e9d  test    edi, edi
0x180070e9f  jz      short loc_180070EAD
0x180070ea1  mov     r9d, edi
0x180070ea4  lea     rdx, aHsErrorCreatin; "%hs: Error creating RPC binding: %d\n"
0x180070eab  jmp     short loc_180070E5E
0x180070ead  mov     [rsp+0C8h+var_50], 0
0x180070eb6  lea     rax, [rsp+0C8h+Block]
0x180070ebe  mov     [rsp+0C8h+StringBinding], rax
0x180070ec3  lea     rax, [rsp+0C8h+var_48]
0x180070ecb  mov     [rsp+0C8h+Options], rax
0x180070ed0  mov     r9, [rsp+0C8h+Binding]
0x180070ed5  xor     r8d, r8d; pReturnValue
0x180070ed8  xor     edx, edx; nProcNum
0x180070eda  lea     rcx, ?ProvIum_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180070ee1  call    cs:__imp_NdrClientCall3
0x180070ee8  nop     dword ptr [rax+rax+00h]
0x180070eed  mov     rbx, rax
0x180070ef0  mov     [rsp+0C8h+var_50], rax
0x180070ef5  test    eax, eax
0x180070ef7  jns     short loc_180070F28
0x180070ef9  mov     r9d, ebx
0x180070efc  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x180070f03  lea     rdx, aHsProviumcreat; "%hs: ProvIumCreateMachineKey returned 0"...
0x180070f0a  mov     ecx, 800h; unsigned int
0x180070f0f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070f14  mov     ecx, ebx; Status
0x180070f16  call    cs:__imp_RtlNtStatusToDosError
0x180070f1d  nop     dword ptr [rax+rax+00h]
0x180070f22  mov     edi, eax
0x180070f24  mov     [rsp+0C8h+var_78], eax
0x180070f28  jmp     short loc_180070F4D
0x180070f2a  mov     edi, eax
0x180070f2c  mov     [rsp+0C8h+var_78], eax
0x180070f30  mov     r12, [rsp+0C8h+arg_10]
0x180070f38  mov     r15, [rsp+0C8h+arg_8]
0x180070f40  mov     r13, [rsp+0C8h+arg_0]
0x180070f48  mov     r14, [rsp+0C8h+var_58]
0x180070f4d  lea     eax, [rdi-6ACh]
0x180070f53  cmp     eax, 2Dh ; '-'
0x180070f56  ja      short loc_180070F90
0x180070f58  mov     rcx, 200000004201h
0x180070f62  bt      rcx, rax
0x180070f66  jnb     short loc_180070F90
0x180070f68  mov     r9d, edi
0x180070f6b  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x180070f72  lea     rdx, aHsProvisioning; "%hs: Provisioning interface not respond"...
0x180070f79  mov     ecx, 800h; unsigned int
0x180070f7e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180070f83  mov     dword ptr [r12], 0
0x180070f8b  jmp     loc_1800710F9
0x180070f90  test    edi, edi
0x180070f92  jz      short loc_180070FA3
0x180070f94  mov     r9d, edi
0x180070f97  lea     rdx, aHsErrorCalling; "%hs: Error calling provisioning interfa"...
0x180070f9e  jmp     loc_180070E5E
0x180070fa3  mov     rdx, [rsp+0C8h+Block]
0x180070fab  mov     eax, [rsp+0C8h+var_48]
0x180070fb2  mov     [rsp+0C8h+arg_10], 0
0x180070fbe  lea     rcx, [rsp+0C8h+pbCertEncoded]
0x180070fc3  mov     [rsp+0C8h+var_88], rcx
0x180070fc8  lea     rcx, [rsp+0C8h+cbCertEncoded]
0x180070fd0  mov     [rsp+0C8h+var_90], rcx
0x180070fd5  mov     [rsp+0C8h+var_98], r13
0x180070fda  mov     [rsp+0C8h+StringBinding], rdx
0x180070fdf  mov     dword ptr [rsp+0C8h+Options], eax
0x180070fe3  mov     r9, [rsp+0C8h+Binding]
0x180070fe8  xor     r8d, r8d; pReturnValue
0x180070feb  lea     edx, [r8+1]; nProcNum
0x180070fef  lea     rcx, ?ProvIum_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180070ff6  call    cs:__imp_NdrClientCall3
0x180070ffd  nop     dword ptr [rax+rax+00h]
0x180071002  mov     rbx, rax
0x180071005  mov     [rsp+0C8h+arg_10], rax
0x18007100d  test    eax, eax
0x18007100f  jns     short loc_180071040
0x180071011  mov     r9d, ebx
0x180071014  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18007101b  lea     rdx, aHsProviumcreat_0; "%hs: ProvIumCreateMachineSelfSignedCert"...
0x180071022  mov     ecx, 800h; unsigned int
0x180071027  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007102c  mov     ecx, ebx; Status
0x18007102e  call    cs:__imp_RtlNtStatusToDosError
0x180071035  nop     dword ptr [rax+rax+00h]
0x18007103a  mov     edi, eax
0x18007103c  mov     [rsp+0C8h+var_78], eax
0x180071040  jmp     short loc_180071055
0x180071042  mov     edi, eax
0x180071044  mov     [rsp+0C8h+var_78], eax
0x180071048  mov     r15, [rsp+0C8h+arg_8]
0x180071050  mov     r14, [rsp+0C8h+var_58]
0x180071055  test    edi, edi
0x180071057  jnz     loc_180070F94
0x18007105d  mov     r8d, [rsp+0C8h+cbCertEncoded]; cbCertEncoded
0x180071065  mov     rdx, [rsp+0C8h+pbCertEncoded]; pbCertEncoded
0x18007106a  lea     ecx, [rdi+1]; dwCertEncodingType
0x18007106d  call    cs:__imp_CertCreateCertificateContext
0x180071074  nop     dword ptr [rax+rax+00h]
0x180071079  mov     r14, rax
0x18007107c  test    rax, rax
0x18007107f  jnz     short loc_18007109B
0x180071081  call    cs:__imp_GetLastError
0x180071088  nop     dword ptr [rax+rax+00h]
0x18007108d  mov     edi, eax
0x18007108f  lea     rdx, aHsErrorCreatin_0; "%hs: Error creating certificate context"...
0x180071096  jmp     loc_180070E5B
0x18007109b  mov     r9, [rsp+0C8h+Block]
0x1800710a3  mov     r8d, [rsp+0C8h+var_48]
0x1800710ab  mov     rdx, [rsp+0C8h+pbCertEncoded]
0x1800710b0  mov     ecx, [rsp+0C8h+cbCertEncoded]
0x1800710b7  call    LsaSetMachineCertificate
0x1800710bc  mov     ebx, eax
0x1800710be  test    eax, eax
0x1800710c0  jns     short loc_1800710F3
0x1800710c2  mov     ecx, eax; Status
0x1800710c4  call    cs:__imp_RtlNtStatusToDosError
0x1800710cb  nop     dword ptr [rax+rax+00h]
0x1800710d0  mov     edi, eax
0x1800710d2  mov     dword ptr [rsp+0C8h+Options], eax
0x1800710d6  mov     r9d, ebx
0x1800710d9  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x1800710e0  lea     rdx, aHsLsasetmachin; "%hs: LsaSetMachineCertificate failed wi"...
0x1800710e7  mov     ecx, 800h; unsigned int
0x1800710ec  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800710f1  jmp     short loc_1800710F9
0x1800710f3  mov     [r15], r14
0x1800710f6  xor     r14d, r14d
0x1800710f9  test    r14, r14
0x1800710fc  jz      short loc_18007110D
0x1800710fe  mov     rcx, r14; pCertContext
0x180071101  call    cs:__imp_CertFreeCertificateContext
0x180071108  nop     dword ptr [rax+rax+00h]
0x18007110d  mov     rcx, [rsp+0C8h+Block]; Block
0x180071115  test    rcx, rcx
0x180071118  jz      short loc_180071126
0x18007111a  call    cs:__imp_free
0x180071121  nop     dword ptr [rax+rax+00h]
0x180071126  mov     rcx, [rsp+0C8h+pbCertEncoded]; Block
0x18007112b  test    rcx, rcx
0x18007112e  jz      short loc_18007113C
0x180071130  call    cs:__imp_free
0x180071137  nop     dword ptr [rax+rax+00h]
0x18007113c  cmp     [rsp+0C8h+Binding], 0
0x180071142  jz      short loc_180071155
0x180071144  lea     rcx, [rsp+0C8h+Binding]; Binding
0x180071149  call    cs:__imp_RpcBindingFree
0x180071150  nop     dword ptr [rax+rax+00h]
0x180071155  mov     eax, edi
0x180071157  add     rsp, 98h
0x18007115e  pop     r15
0x180071160  pop     r14
0x180071162  pop     r13
0x180071164  pop     r12
0x180071166  pop     rdi
0x180071167  pop     rbx
0x180071168  retn
0x1800903d0  push    rbp
0x1800903d2  sub     rsp, 50h
0x1800903d6  mov     rbp, rdx
0x1800903d9  mov     rcx, [rcx]
0x1800903dc  mov     ecx, [rcx]; ExceptionCode
0x1800903de  call    cs:__imp_RpcExceptionFilter
0x1800903e5  nop     dword ptr [rax+rax+00h]
0x1800903ea  nop
0x1800903eb  add     rsp, 50h
0x1800903ef  pop     rbp
0x1800903f0  retn
0x1800903f2  push    rbp
0x1800903f4  sub     rsp, 50h
0x1800903f8  mov     rbp, rdx
0x1800903fb  mov     rcx, [rcx]
0x1800903fe  mov     ecx, [rcx]; ExceptionCode
0x180090400  call    cs:__imp_RpcExceptionFilter
0x180090407  nop     dword ptr [rax+rax+00h]
0x18009040c  nop
0x18009040d  add     rsp, 50h
0x180090411  pop     rbp
0x180090412  retn
```
