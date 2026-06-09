# NlpGenerateIumBoundMachineAuthCert(ushort const *,_CERT_CONTEXT const * *,int *)

- ea: `0x18006bcb4`
- end: `0x18006c009`
- name: `?NlpGenerateIumBoundMachineAuthCert@@YAKPEBGPEAPEBU_CERT_CONTEXT@@PEAH@Z`
- size: `853`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const struct _CERT_CONTEXT **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b738`

## callees

- `0x180007278`
- `0x18006bcb4`
- `0x180084394`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006bfcc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006bfdc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006bfcc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18006bfdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf45`
- `RPCRT4!RpcStringFreeW` at `0x18006bd79`
- `RPCRT4!RpcStringFreeW` at `0x18006bd79`
- `RPCRT4!RpcBindingFree` at `0x18006bfef`
- `RPCRT4!RpcBindingFree` at `0x18006bfef`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006bd6c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18006bd6c`
- `RPCRT4!NdrClientCall3` at `0x18006bdc3`
- `RPCRT4!NdrClientCall3` at `0x18006becc`
- `RPCRT4!NdrClientCall3` at `0x18006bdc3`
- `RPCRT4!NdrClientCall3` at `0x18006becc`
- `RPCRT4!RpcStringBindingComposeW` at `0x18006bd36`
- `RPCRT4!RpcStringBindingComposeW` at `0x18006bd36`
- `RPCRT4!RpcExceptionFilter` at `0x180089c7e`
- `RPCRT4!RpcExceptionFilter` at `0x180089c9a`
- `RPCRT4!RpcExceptionFilter` at `0x180089c7e`
- `RPCRT4!RpcExceptionFilter` at `0x180089c9a`
- `ntdll!RtlNtStatusToDosError` at `0x18006bdf2`
- `ntdll!RtlNtStatusToDosError` at `0x18006befe`
- `ntdll!RtlNtStatusToDosError` at `0x18006bf82`
- `ntdll!RtlNtStatusToDosError` at `0x18006bdf2`
- `ntdll!RtlNtStatusToDosError` at `0x18006befe`
- `ntdll!RtlNtStatusToDosError` at `0x18006bf82`
- `CRYPT32!CertFreeCertificateContext` at `0x18006bfb9`
- `CRYPT32!CertFreeCertificateContext` at `0x18006bfb9`
- `CRYPT32!CertCreateCertificateContext` at `0x18006bf37`
- `CRYPT32!CertCreateCertificateContext` at `0x18006bf37`

## string_xrefs

- `0x18006bd42`: `%hs: Error composing string binding: %d\n`
- `0x18006bddf`: `%hs: ProvIumCreateMachineKey returned 0x%x\n`
- `0x18006beeb`: `%hs: ProvIumCreateMachineSelfSignedCertificate returned 0x%x\n`

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
0x18006bcb4  mov     rax, rsp
0x18006bcb7  mov     [rax+18h], r8
0x18006bcbb  mov     [rax+10h], rdx
0x18006bcbf  mov     [rax+8], rcx
0x18006bcc3  push    rbx
0x18006bcc4  push    rdi
0x18006bcc5  push    r12
0x18006bcc7  push    r13
0x18006bcc9  push    r14
0x18006bccb  push    r15
0x18006bccd  sub     rsp, 98h
0x18006bcd4  mov     r12, r8
0x18006bcd7  mov     r15, rdx
0x18006bcda  mov     r13, rcx
0x18006bcdd  mov     qword ptr [rax-70h], 0
0x18006bce5  mov     qword ptr [rax-60h], 0
0x18006bced  mov     qword ptr [rax-68h], 0
0x18006bcf5  mov     dword ptr [rax+20h], 0
0x18006bcfc  xor     r14d, r14d
0x18006bcff  mov     [rsp+0C8h+var_58], r14
0x18006bd04  xorps   xmm0, xmm0
0x18006bd07  movups  xmmword ptr [rax-48h], xmm0
0x18006bd0b  mov     dword ptr [r8], 1
0x18006bd12  mov     [rdx], r14
0x18006bd15  lea     rax, [rax-60h]
0x18006bd19  mov     [rsp+0C8h+StringBinding], rax; StringBinding
0x18006bd1e  mov     [rsp+0C8h+Options], r14; Options
0x18006bd23  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x18006bd2a  xor     r8d, r8d; NetworkAddr
0x18006bd2d  lea     rdx, ProtSeq; "ncalrpc"
0x18006bd34  xor     ecx, ecx; ObjUuid
0x18006bd36  call    cs:__imp_RpcStringBindingComposeW
0x18006bd3c  mov     edi, eax
0x18006bd3e  test    eax, eax
0x18006bd40  jz      short loc_18006BD62
0x18006bd42  lea     rdx, aHsErrorComposi; "%hs: Error composing string binding: %d"...
0x18006bd49  mov     r9d, eax
0x18006bd4c  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18006bd53  mov     ecx, 800h; unsigned int
0x18006bd58  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bd5d  jmp     loc_18006BFB1
0x18006bd62  lea     rdx, [rsp+0C8h+Binding]; Binding
0x18006bd67  mov     rcx, [rsp+0C8h+String]; StringBinding
0x18006bd6c  call    cs:__imp_RpcBindingFromStringBindingW
0x18006bd72  mov     edi, eax
0x18006bd74  lea     rcx, [rsp+0C8h+String]; String
0x18006bd79  call    cs:__imp_RpcStringFreeW
0x18006bd7f  test    edi, edi
0x18006bd81  jz      short loc_18006BD8F
0x18006bd83  mov     r9d, edi
0x18006bd86  lea     rdx, aHsErrorCreatin; "%hs: Error creating RPC binding: %d\n"
0x18006bd8d  jmp     short loc_18006BD4C
0x18006bd8f  mov     [rsp+0C8h+var_50], 0
0x18006bd98  lea     rax, [rsp+0C8h+Block]
0x18006bda0  mov     [rsp+0C8h+StringBinding], rax
0x18006bda5  lea     rax, [rsp+0C8h+var_48]
0x18006bdad  mov     [rsp+0C8h+Options], rax
0x18006bdb2  mov     r9, [rsp+0C8h+Binding]
0x18006bdb7  xor     r8d, r8d; pReturnValue
0x18006bdba  xor     edx, edx; nProcNum
0x18006bdbc  lea     rcx, ?ProvIum_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18006bdc3  call    cs:__imp_NdrClientCall3
0x18006bdc9  mov     rbx, rax
0x18006bdcc  mov     [rsp+0C8h+var_50], rax
0x18006bdd1  test    eax, eax
0x18006bdd3  jns     short loc_18006BDFE
0x18006bdd5  mov     r9d, ebx
0x18006bdd8  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18006bddf  lea     rdx, aHsProviumcreat; "%hs: ProvIumCreateMachineKey returned 0"...
0x18006bde6  mov     ecx, 800h; unsigned int
0x18006bdeb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bdf0  mov     ecx, ebx; Status
0x18006bdf2  call    cs:__imp_RtlNtStatusToDosError
0x18006bdf8  mov     edi, eax
0x18006bdfa  mov     [rsp+0C8h+var_78], eax
0x18006bdfe  jmp     short loc_18006BE23
0x18006be00  mov     edi, eax
0x18006be02  mov     [rsp+0C8h+var_78], eax
0x18006be06  mov     r12, [rsp+0C8h+arg_10]
0x18006be0e  mov     r15, [rsp+0C8h+arg_8]
0x18006be16  mov     r13, [rsp+0C8h+arg_0]
0x18006be1e  mov     r14, [rsp+0C8h+var_58]
0x18006be23  lea     eax, [rdi-6ACh]
0x18006be29  cmp     eax, 2Dh ; '-'
0x18006be2c  ja      short loc_18006BE66
0x18006be2e  mov     rcx, 200000004201h
0x18006be38  bt      rcx, rax
0x18006be3c  jnb     short loc_18006BE66
0x18006be3e  mov     r9d, edi
0x18006be41  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18006be48  lea     rdx, aHsProvisioning; "%hs: Provisioning interface not respond"...
0x18006be4f  mov     ecx, 800h; unsigned int
0x18006be54  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006be59  mov     dword ptr [r12], 0
0x18006be61  jmp     loc_18006BFB1
0x18006be66  test    edi, edi
0x18006be68  jz      short loc_18006BE79
0x18006be6a  mov     r9d, edi
0x18006be6d  lea     rdx, aHsErrorCalling; "%hs: Error calling provisioning interfa"...
0x18006be74  jmp     loc_18006BD4C
0x18006be79  mov     rdx, [rsp+0C8h+Block]
0x18006be81  mov     eax, [rsp+0C8h+var_48]
0x18006be88  mov     [rsp+0C8h+arg_10], 0
0x18006be94  lea     rcx, [rsp+0C8h+pbCertEncoded]
0x18006be99  mov     [rsp+0C8h+var_88], rcx
0x18006be9e  lea     rcx, [rsp+0C8h+cbCertEncoded]
0x18006bea6  mov     [rsp+0C8h+var_90], rcx
0x18006beab  mov     [rsp+0C8h+var_98], r13
0x18006beb0  mov     [rsp+0C8h+StringBinding], rdx
0x18006beb5  mov     dword ptr [rsp+0C8h+Options], eax
0x18006beb9  mov     r9, [rsp+0C8h+Binding]
0x18006bebe  xor     r8d, r8d; pReturnValue
0x18006bec1  lea     edx, [r8+1]; nProcNum
0x18006bec5  lea     rcx, ?ProvIum_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18006becc  call    cs:__imp_NdrClientCall3
0x18006bed2  mov     rbx, rax
0x18006bed5  mov     [rsp+0C8h+arg_10], rax
0x18006bedd  test    eax, eax
0x18006bedf  jns     short loc_18006BF0A
0x18006bee1  mov     r9d, ebx
0x18006bee4  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18006beeb  lea     rdx, aHsProviumcreat_0; "%hs: ProvIumCreateMachineSelfSignedCert"...
0x18006bef2  mov     ecx, 800h; unsigned int
0x18006bef7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006befc  mov     ecx, ebx; Status
0x18006befe  call    cs:__imp_RtlNtStatusToDosError
0x18006bf04  mov     edi, eax
0x18006bf06  mov     [rsp+0C8h+var_78], eax
0x18006bf0a  jmp     short loc_18006BF1F
0x18006bf0c  mov     edi, eax
0x18006bf0e  mov     [rsp+0C8h+var_78], eax
0x18006bf12  mov     r15, [rsp+0C8h+arg_8]
0x18006bf1a  mov     r14, [rsp+0C8h+var_58]
0x18006bf1f  test    edi, edi
0x18006bf21  jnz     loc_18006BE6A
0x18006bf27  mov     r8d, [rsp+0C8h+cbCertEncoded]; cbCertEncoded
0x18006bf2f  mov     rdx, [rsp+0C8h+pbCertEncoded]; pbCertEncoded
0x18006bf34  lea     ecx, [rdi+1]; dwCertEncodingType
0x18006bf37  call    cs:__imp_CertCreateCertificateContext
0x18006bf3d  mov     r14, rax
0x18006bf40  test    rax, rax
0x18006bf43  jnz     short loc_18006BF59
0x18006bf45  call    cs:__imp_GetLastError
0x18006bf4b  mov     edi, eax
0x18006bf4d  lea     rdx, aHsErrorCreatin_0; "%hs: Error creating certificate context"...
0x18006bf54  jmp     loc_18006BD49
0x18006bf59  mov     r9, [rsp+0C8h+Block]
0x18006bf61  mov     r8d, [rsp+0C8h+var_48]
0x18006bf69  mov     rdx, [rsp+0C8h+pbCertEncoded]
0x18006bf6e  mov     ecx, [rsp+0C8h+cbCertEncoded]
0x18006bf75  call    LsaSetMachineCertificate
0x18006bf7a  mov     ebx, eax
0x18006bf7c  test    eax, eax
0x18006bf7e  jns     short loc_18006BFAB
0x18006bf80  mov     ecx, eax; Status
0x18006bf82  call    cs:__imp_RtlNtStatusToDosError
0x18006bf88  mov     edi, eax
0x18006bf8a  mov     dword ptr [rsp+0C8h+Options], eax
0x18006bf8e  mov     r9d, ebx
0x18006bf91  lea     r8, aNlpgenerateium; "NlpGenerateIumBoundMachineAuthCert"
0x18006bf98  lea     rdx, aHsLsasetmachin; "%hs: LsaSetMachineCertificate failed wi"...
0x18006bf9f  mov     ecx, 800h; unsigned int
0x18006bfa4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bfa9  jmp     short loc_18006BFB1
0x18006bfab  mov     [r15], r14
0x18006bfae  xor     r14d, r14d
0x18006bfb1  test    r14, r14
0x18006bfb4  jz      short loc_18006BFBF
0x18006bfb6  mov     rcx, r14; pCertContext
0x18006bfb9  call    cs:__imp_CertFreeCertificateContext
0x18006bfbf  mov     rcx, [rsp+0C8h+Block]; Block
0x18006bfc7  test    rcx, rcx
0x18006bfca  jz      short loc_18006BFD2
0x18006bfcc  call    cs:__imp_free
0x18006bfd2  mov     rcx, [rsp+0C8h+pbCertEncoded]; Block
0x18006bfd7  test    rcx, rcx
0x18006bfda  jz      short loc_18006BFE2
0x18006bfdc  call    cs:__imp_free
0x18006bfe2  cmp     [rsp+0C8h+Binding], 0
0x18006bfe8  jz      short loc_18006BFF5
0x18006bfea  lea     rcx, [rsp+0C8h+Binding]; Binding
0x18006bfef  call    cs:__imp_RpcBindingFree
0x18006bff5  mov     eax, edi
0x18006bff7  add     rsp, 98h
0x18006bffe  pop     r15
0x18006c000  pop     r14
0x18006c002  pop     r13
0x18006c004  pop     r12
0x18006c006  pop     rdi
0x18006c007  pop     rbx
0x18006c008  retn
0x180089c70  push    rbp
0x180089c72  sub     rsp, 50h
0x180089c76  mov     rbp, rdx
0x180089c79  mov     rcx, [rcx]
0x180089c7c  mov     ecx, [rcx]; ExceptionCode
0x180089c7e  call    cs:__imp_RpcExceptionFilter
0x180089c84  nop
0x180089c85  add     rsp, 50h
0x180089c89  pop     rbp
0x180089c8a  retn
0x180089c8c  push    rbp
0x180089c8e  sub     rsp, 50h
0x180089c92  mov     rbp, rdx
0x180089c95  mov     rcx, [rcx]
0x180089c98  mov     ecx, [rcx]; ExceptionCode
0x180089c9a  call    cs:__imp_RpcExceptionFilter
0x180089ca0  nop
0x180089ca1  add     rsp, 50h
0x180089ca5  pop     rbp
0x180089ca6  retn
```
