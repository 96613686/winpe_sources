# NlpStoreKeyInDS

- ea: `0x18002b738`
- end: `0x18002bbf2`
- name: `NlpStoreKeyInDS`
- size: `1210`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002b5b0`

## callees

- `0x180003220`
- `0x180007278`
- `0x18000e270`
- `0x18002ae5c`
- `0x18002b608`
- `0x18002b738`
- `0x1800393f4`
- `0x18006bc60`
- `0x18006bcb4`
- `0x180089a30`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9a1`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18002b9d4`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18002b9d4`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18002bb5a`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18002bb5a`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsFreeNgcKey` at `0x18002bb4a`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsFreeNgcKey` at `0x18002bb4a`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsWriteNgcKeyW` at `0x18002baf3`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsWriteNgcKeyW` at `0x18002baf3`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsReadNgcKeyW` at `0x18002ba17`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsReadNgcKeyW` at `0x18002ba17`
- `netutils!NetApiBufferFree` at `0x18002bb68`
- `netutils!NetApiBufferFree` at `0x18002bb94`
- `netutils!NetApiBufferFree` at `0x18002bb68`
- `netutils!NetApiBufferFree` at `0x18002bb94`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bbb0`
- `CRYPT32!CertFreeCertificateContext` at `0x18002bbb0`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18002b997`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18002b997`

## string_xrefs

- `0x18002b856`: `%hs: Unable to allocate memory for computer acct name: %d\n`
- `0x18002b88c`: `%hs: Error building computer acct name string: %d\n`
- `0x18002b97f`: `%hs: Allocate buffer for computer DN: %d\n`
- `0x18002b9a9`: `%hs: Unable to get computer DN: %d\n`
- `0x18002ba2e`: `%hs: Error reading NGC Key from DC '%ls': %d\n`
- `0x18002bb30`: `%hs: Key already provisioned in DS, nothing to do\n`
- `0x18002bab8`: `%hs: No machine bound certificate could be created: %d\n`

## pseudocode

```c
__int64 NlpStoreKeyInDS()
{
  WCHAR *p_nSize; // rdi
  struct _CERT_CONTEXT *v1; // r14
  unsigned __int16 *v2; // r15
  int v3; // r13d
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned __int16 *p_Buffer; // rsi
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  unsigned __int16 *v12; // rax
  unsigned int v13; // ebx
  DWORD CurrentDomainDCNoCaching; // eax
  unsigned int v15; // ecx
  unsigned __int16 *v16; // rdx
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  WCHAR *v21; // rax
  DWORD v22; // eax
  unsigned __int16 *v23; // rdx
  unsigned int v24; // eax
  _BYTE v26[32]; // [rsp+0h] [rbp-30h] BYREF
  __int64 BindFlags; // [rsp+20h] [rbp-10h]
  LPVOID Buffer; // [rsp+30h] [rbp+0h] BYREF
  ULONG nSize; // [rsp+38h] [rbp+8h] BYREF
  int v30; // [rsp+3Ch] [rbp+Ch] BYREF
  HANDLE phDS; // [rsp+40h] [rbp+10h] BYREF
  struct _CERT_CONTEXT *v32; // [rsp+48h] [rbp+18h] BYREF
  int v33; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp+28h] BYREF
  __int64 v35; // [rsp+60h] [rbp+30h] BYREF

  p_nSize = 0;
  Buffer = 0;
  v1 = 0;
  v32 = 0;
  v2 = 0;
  v34 = 0;
  phDS = 0;
  v3 = 0;
  v35 = 0;
  v4 = -1;
  v33 = 0;
  nSize = 1024;
  v30 = 1;
  do
    ++v4;
  while ( NlGlobalUnicodeComputerName[v4] );
  v5 = (unsigned int)(v4 + 2);
  p_Buffer = 0;
  v7 = (unsigned int)v5;
  v8 = 2 * v5;
  if ( !(2 * v5)
    || v8 > g_ulMaxStackAllocSize
    || v8 + g_ulAdditionalProbeSize + 8 < v8
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_78;
  }
  v9 = v8 + 23;
  if ( v8 + 23 <= v8 + 8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  v11 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  p_Buffer = (unsigned __int16 *)&Buffer;
  if ( v26 == (_BYTE *)-48LL || (LODWORD(Buffer) = 1801679955, (p_Buffer = (unsigned __int16 *)&nSize) == 0) )
  {
LABEL_78:
    if ( v8 + 8 >= v8 )
    {
      v12 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
      p_Buffer = v12;
      if ( v12 )
      {
        *(_DWORD *)v12 = 1885431112;
        p_Buffer = v12 + 4;
      }
    }
  }
  if ( !p_Buffer )
  {
    v13 = 8;
    NlPrintRoutine(0x800u, L"%hs: Unable to allocate memory for computer acct name: %d\n", "NlpStoreKeyInDS", 8);
    goto LABEL_56;
  }
  CurrentDomainDCNoCaching = RtlStringCchPrintfW(p_Buffer, v7, L"%s$", NlGlobalUnicodeComputerName);
  v13 = CurrentDomainDCNoCaching;
  if ( CurrentDomainDCNoCaching )
  {
    v16 = L"%hs: Error building computer acct name string: %d\n";
LABEL_18:
    NlPrintRoutine(0x800u, v16, "NlpStoreKeyInDS", CurrentDomainDCNoCaching);
    goto LABEL_56;
  }
  CurrentDomainDCNoCaching = NlpLocateCurrentDomainDCNoCaching(
                               v15,
                               p_Buffer,
                               NlGlobalMemberWorkstation != 0 ? 4096 : 0x2000,
                               (struct _DOMAIN_CONTROLLER_INFOW **)&Buffer);
  v13 = CurrentDomainDCNoCaching;
  if ( CurrentDomainDCNoCaching )
  {
    v16 = L"%hs: Unable to contact a threshold or higher level DC: %d\n";
    goto LABEL_18;
  }
  v17 = 2LL * nSize;
  if ( !v17
    || v17 > g_ulMaxStackAllocSize
    || v17 + g_ulAdditionalProbeSize + 8 < v17
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_79;
  }
  v18 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  v20 = alloca(v18 & 0xFFFFFFFFFFFFFFF0uLL);
  p_nSize = (WCHAR *)&Buffer;
  if ( v26 == (_BYTE *)-48LL || (LODWORD(Buffer) = 1801679955, (p_nSize = (WCHAR *)&nSize) == 0) )
  {
LABEL_79:
    if ( v17 + 8 >= v17 )
    {
      v21 = (WCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_nSize = v21;
      if ( v21 )
      {
        *(_DWORD *)v21 = 1885431112;
        p_nSize = v21 + 4;
      }
    }
  }
  if ( !p_nSize )
  {
    v13 = 8;
    NlPrintRoutine(0x800u, L"%hs: Allocate buffer for computer DN: %d\n", "NlpStoreKeyInDS", 8);
    goto LABEL_56;
  }
  if ( !GetComputerObjectNameW(NameFullyQualifiedDN, p_nSize, &nSize) )
  {
    CurrentDomainDCNoCaching = GetLastError();
    v13 = CurrentDomainDCNoCaching;
    v16 = L"%hs: Unable to get computer DN: %d\n";
    goto LABEL_18;
  }
  v22 = DsBindWithSpnExW(*(LPCWSTR *)Buffer, *((LPCWSTR *)Buffer + 5), 0, 0, 0, &phDS);
  v13 = v22;
  if ( v22 )
  {
    v23 = L"%hs: Error binding to DC '%ls': %d\n";
LABEL_38:
    LODWORD(BindFlags) = v22;
    NlPrintRoutine(0x800u, v23, "NlpStoreKeyInDS", *(_QWORD *)Buffer, BindFlags);
    goto LABEL_56;
  }
  v22 = DsReadNgcKeyW(phDS, p_nSize, &v33, &v35);
  v13 = v22;
  if ( v22 )
  {
    if ( v22 != 8202 )
    {
      v23 = L"%hs: Error reading NGC Key from DC '%ls': %d\n";
      goto LABEL_38;
    }
    v24 = NlpGenerateMachineKeyCertificateSubjectName(&v34);
    v13 = v24;
    if ( v24 )
    {
      NlPrintRoutine(0x800u, L"%hs: Error building cert subject string: %d\n", "NlpStoreKeyInDS", v24);
      v2 = v34;
      goto LABEL_56;
    }
    v2 = v34;
    v13 = NlpGenerateIumBoundMachineAuthCert(v34, (const struct _CERT_CONTEXT **)&v32, &v30);
    if ( v13 )
    {
      if ( v30 )
      {
        NlPrintRoutine(
          0x100u,
          L"%hs: Unexpected error generating IUM bound machine auth key: %d\n",
          "NlpStoreKeyInDS",
          v13);
        goto LABEL_50;
      }
      NlPrintRoutine(2u, L"%hs: IUM Provisioning interface not up.\n", "NlpStoreKeyInDS");
    }
    else
    {
      v3 = 1;
      NlPrintRoutine(2u, L"%hs: IUM bound certificate successfully obtained\n", "NlpStoreKeyInDS");
    }
    if ( !v3 )
    {
      NlPrintRoutine(0x800u, L"%hs: No machine bound certificate could be created: %d\n", "NlpStoreKeyInDS", v13);
LABEL_50:
      v1 = v32;
      goto LABEL_56;
    }
    v1 = v32;
    v22 = DsWriteNgcKeyW(
            phDS,
            p_nSize,
            v32->pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
            v32->pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData);
    v13 = v22;
    if ( v22 )
    {
      v23 = L"%hs: Error writing NGC Key to DC '%ls': %d\n";
      goto LABEL_38;
    }
    NlPrintRoutine(2u, L"%hs: Successfully provisioned the machine auth key in DS\n", "NlpStoreKeyInDS");
  }
  else
  {
    NlPrintRoutine(2u, L"%hs: Key already provisioned in DS, nothing to do\n", "NlpStoreKeyInDS");
  }
LABEL_56:
  if ( v35 )
    DsFreeNgcKey();
  if ( phDS )
    DsUnBindW(&phDS);
  if ( v2 )
    NetApiBufferFree(v2);
  if ( p_nSize && *((_DWORD *)p_nSize - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v13 && v3 )
    NlpDeleteIumBoundMachineAuthCert();
  if ( v1 )
    CertFreeCertificateContext(v1);
  if ( p_Buffer && *((_DWORD *)p_Buffer - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v13;
}

```

## disassembly

```asm
0x18002b738  push    rbp
0x18002b73a  push    rbx
0x18002b73b  push    rsi
0x18002b73c  push    rdi
0x18002b73d  push    r12
0x18002b73f  push    r13
0x18002b741  push    r14
0x18002b743  push    r15
0x18002b745  sub     rsp, 88h
0x18002b74c  lea     rbp, [rsp+30h]
0x18002b751  mov     rax, cs:__security_cookie
0x18002b758  xor     rax, rbp
0x18002b75b  mov     [rbp+90h+var_50], rax
0x18002b75f  mov     rcx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18002b766  xor     edx, edx
0x18002b768  mov     edi, edx
0x18002b76a  mov     [rbp+90h+Buffer], rdx
0x18002b76e  mov     r14d, edx
0x18002b771  mov     [rbp+90h+var_78], rdx
0x18002b775  mov     r15d, edx
0x18002b778  mov     [rbp+90h+var_68], rdx
0x18002b77c  mov     [rbp+90h+var_80], rdx
0x18002b780  mov     r13d, edx
0x18002b783  mov     [rbp+90h+var_60], rdx
0x18002b787  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b78b  mov     [rbp+90h+var_70], edx
0x18002b78e  mov     [rbp+90h+nSize], 400h
0x18002b795  mov     [rbp+90h+var_84], 1
0x18002b79c  inc     rax
0x18002b79f  cmp     [rcx+rax*2], dx
0x18002b7a3  jnz     short loc_18002B79C
0x18002b7a5  add     eax, 2
0x18002b7a8  mov     rsi, rdx
0x18002b7ab  mov     r12d, eax
0x18002b7ae  lea     rbx, [rax+rax]
0x18002b7b2  test    rbx, rbx
0x18002b7b5  jz      short loc_18002B818
0x18002b7b7  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002b7be  ja      short loc_18002B818
0x18002b7c0  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b7c7  add     rcx, 8
0x18002b7cb  add     rcx, rbx
0x18002b7ce  cmp     rcx, rbx
0x18002b7d1  jb      short loc_18002B818
0x18002b7d3  call    VerifyStackAvailable
0x18002b7d8  test    eax, eax
0x18002b7da  jz      short loc_18002B818
0x18002b7dc  lea     rax, [rbx+8]
0x18002b7e0  lea     rcx, [rax+0Fh]
0x18002b7e4  cmp     rcx, rax
0x18002b7e7  ja      short loc_18002B7F3
0x18002b7e9  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002b7f3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b7f7  mov     rax, rcx
0x18002b7fa  call    _alloca_probe
0x18002b7ff  sub     rsp, rcx
0x18002b802  lea     rsi, [rsp+0C0h+Buffer]
0x18002b807  test    rsi, rsi
0x18002b80a  jz      short loc_18002B818
0x18002b80c  mov     dword ptr [rsi], 6B637453h
0x18002b812  add     rsi, 8
0x18002b816  jnz     short loc_18002B83F
0x18002b818  lea     rcx, [rbx+8]
0x18002b81c  cmp     rcx, rbx
0x18002b81f  jb      short loc_18002B83F
0x18002b821  mov     rax, cs:g_pfnAllocate
0x18002b828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b82d  mov     rsi, rax
0x18002b830  test    rax, rax
0x18002b833  jz      short loc_18002B83F
0x18002b835  mov     dword ptr [rax], 70616548h
0x18002b83b  add     rsi, 8
0x18002b83f  test    rsi, rsi
0x18002b842  jnz     short loc_18002B86A
0x18002b844  lea     ebx, [rsi+8]
0x18002b847  mov     ecx, 800h; unsigned int
0x18002b84c  mov     r9d, ebx
0x18002b84f  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002b856  lea     rdx, aHsUnableToAllo; "%hs: Unable to allocate memory for comp"...
0x18002b85d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b862  xor     r12d, r12d
0x18002b865  jmp     loc_18002BB41
0x18002b86a  mov     r9, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18002b871  lea     r8, aS; "%s$"
0x18002b878  mov     rdx, r12; unsigned __int64
0x18002b87b  mov     rcx, rsi; unsigned __int16 *
0x18002b87e  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002b883  xor     r12d, r12d
0x18002b886  mov     ebx, eax
0x18002b888  test    eax, eax
0x18002b88a  jz      short loc_18002B8AC
0x18002b88c  lea     rdx, aHsErrorBuildin_0; "%hs: Error building computer acct name "...
0x18002b893  mov     r9d, eax
0x18002b896  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002b89d  mov     ecx, 800h; unsigned int
0x18002b8a2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002b8a7  jmp     loc_18002BB41
0x18002b8ac  mov     eax, cs:?NlGlobalMemberWorkstation@@3HA; int NlGlobalMemberWorkstation
0x18002b8b2  lea     r9, [rbp+90h+Buffer]; struct _DOMAIN_CONTROLLER_INFOW **
0x18002b8b6  neg     eax
0x18002b8b8  mov     rdx, rsi; unsigned __int16 *
0x18002b8bb  sbb     r8d, r8d
0x18002b8be  and     r8d, 0FFFFF000h
0x18002b8c5  add     r8d, 2000h; unsigned int
0x18002b8cc  call    ?NlpLocateCurrentDomainDCNoCaching@@YAKKPEAGKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z; NlpLocateCurrentDomainDCNoCaching(ulong,ushort *,ulong,_DOMAIN_CONTROLLER_INFOW * *)
0x18002b8d1  mov     ebx, eax
0x18002b8d3  test    eax, eax
0x18002b8d5  jz      short loc_18002B8E0
0x18002b8d7  lea     rdx, aHsUnableToCont; "%hs: Unable to contact a threshold or h"...
0x18002b8de  jmp     short loc_18002B893
0x18002b8e0  mov     eax, [rbp+90h+nSize]
0x18002b8e3  lea     rbx, [rax+rax]
0x18002b8e7  test    rbx, rbx
0x18002b8ea  jz      short loc_18002B94D
0x18002b8ec  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002b8f3  ja      short loc_18002B94D
0x18002b8f5  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b8fc  add     rcx, 8
0x18002b900  add     rcx, rbx
0x18002b903  cmp     rcx, rbx
0x18002b906  jb      short loc_18002B94D
0x18002b908  call    VerifyStackAvailable
0x18002b90d  test    eax, eax
0x18002b90f  jz      short loc_18002B94D
0x18002b911  lea     rax, [rbx+8]
0x18002b915  lea     rcx, [rax+0Fh]
0x18002b919  cmp     rcx, rax
0x18002b91c  ja      short loc_18002B928
0x18002b91e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002b928  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b92c  mov     rax, rcx
0x18002b92f  call    _alloca_probe
0x18002b934  sub     rsp, rcx
0x18002b937  lea     rdi, [rsp+0C0h+Buffer]
0x18002b93c  test    rdi, rdi
0x18002b93f  jz      short loc_18002B94D
0x18002b941  mov     dword ptr [rdi], 6B637453h
0x18002b947  add     rdi, 8
0x18002b94b  jnz     short loc_18002B974
0x18002b94d  lea     rcx, [rbx+8]
0x18002b951  cmp     rcx, rbx
0x18002b954  jb      short loc_18002B974
0x18002b956  mov     rax, cs:g_pfnAllocate
0x18002b95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b962  mov     rdi, rax
0x18002b965  test    rax, rax
0x18002b968  jz      short loc_18002B974
0x18002b96a  mov     dword ptr [rax], 70616548h
0x18002b970  add     rdi, 8
0x18002b974  test    rdi, rdi
0x18002b977  jnz     short loc_18002B98B
0x18002b979  lea     ebx, [rdi+8]
0x18002b97c  mov     r9d, ebx
0x18002b97f  lea     rdx, aHsAllocateBuff; "%hs: Allocate buffer for computer DN: %"...
0x18002b986  jmp     loc_18002B896
0x18002b98b  lea     r8, [rbp+90h+nSize]; nSize
0x18002b98f  mov     rdx, rdi; lpNameBuffer
0x18002b992  mov     ecx, 1; NameFormat
0x18002b997  call    cs:__imp_GetComputerObjectNameW
0x18002b99d  test    al, al
0x18002b99f  jnz     short loc_18002B9B5
0x18002b9a1  call    cs:__imp_GetLastError
0x18002b9a7  mov     ebx, eax
0x18002b9a9  lea     rdx, aHsUnableToGetC; "%hs: Unable to get computer DN: %d\n"
0x18002b9b0  jmp     loc_18002B893
0x18002b9b5  mov     rcx, [rbp+90h+Buffer]
0x18002b9b9  lea     rax, [rbp+90h+var_80]
0x18002b9bd  mov     [rsp+0C0h+phDS], rax; phDS
0x18002b9c2  xor     r9d, r9d; ServicePrincipalName
0x18002b9c5  xor     r8d, r8d; AuthIdentity
0x18002b9c8  mov     dword ptr [rsp+0C0h+BindFlags], r12d; BindFlags
0x18002b9cd  mov     rdx, [rcx+28h]; DnsDomainName
0x18002b9d1  mov     rcx, [rcx]; DomainControllerName
0x18002b9d4  call    cs:__imp_DsBindWithSpnExW
0x18002b9da  mov     ebx, eax
0x18002b9dc  test    eax, eax
0x18002b9de  jz      short loc_18002BA08
0x18002b9e0  lea     rdx, aHsErrorBinding; "%hs: Error binding to DC '%ls': %d\n"
0x18002b9e7  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002b9ee  mov     r9, [rbp+90h+Buffer]
0x18002b9f2  mov     ecx, 800h; unsigned int
0x18002b9f7  mov     dword ptr [rsp+0C0h+BindFlags], eax
0x18002b9fb  mov     r9, [r9]
0x18002b9fe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ba03  jmp     loc_18002BB41
0x18002ba08  mov     rcx, [rbp+90h+var_80]
0x18002ba0c  lea     r9, [rbp+90h+var_60]
0x18002ba10  lea     r8, [rbp+90h+var_70]
0x18002ba14  mov     rdx, rdi
0x18002ba17  call    cs:__imp_DsReadNgcKeyW
0x18002ba1d  mov     ebx, eax
0x18002ba1f  test    eax, eax
0x18002ba21  jz      loc_18002BB29
0x18002ba27  cmp     eax, 200Ah
0x18002ba2c  jz      short loc_18002BA37
0x18002ba2e  lea     rdx, aHsErrorReading_0; "%hs: Error reading NGC Key from DC '%ls"...
0x18002ba35  jmp     short loc_18002B9E7
0x18002ba37  lea     rcx, [rbp+90h+var_68]
0x18002ba3b  call    NlpGenerateMachineKeyCertificateSubjectName
0x18002ba40  mov     ebx, eax
0x18002ba42  test    eax, eax
0x18002ba44  jz      short loc_18002BA6A
0x18002ba46  mov     r9d, eax
0x18002ba49  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002ba50  lea     rdx, aHsErrorBuildin; "%hs: Error building cert subject string"...
0x18002ba57  mov     ecx, 800h; unsigned int
0x18002ba5c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ba61  mov     r15, [rbp+90h+var_68]
0x18002ba65  jmp     loc_18002BB41
0x18002ba6a  mov     r15, [rbp+90h+var_68]
0x18002ba6e  lea     r8, [rbp+90h+var_84]; int *
0x18002ba72  mov     rcx, r15; unsigned __int16 *
0x18002ba75  lea     rdx, [rbp+90h+var_78]; struct _CERT_CONTEXT **
0x18002ba79  call    ?NlpGenerateIumBoundMachineAuthCert@@YAKPEBGPEAPEBU_CERT_CONTEXT@@PEAH@Z; NlpGenerateIumBoundMachineAuthCert(ushort const *,_CERT_CONTEXT const * *,int *)
0x18002ba7e  mov     ebx, eax
0x18002ba80  test    eax, eax
0x18002ba82  jnz     short loc_18002BA91
0x18002ba84  lea     r13d, [rax+1]
0x18002ba88  lea     rdx, aHsIumBoundCert; "%hs: IUM bound certificate successfully"...
0x18002ba8f  jmp     short loc_18002BAA2
0x18002ba91  cmp     [rbp+90h+var_84], r12d
0x18002ba95  jnz     loc_18002BB1B
0x18002ba9b  lea     rdx, aHsIumProvision; "%hs: IUM Provisioning interface not up."...
0x18002baa2  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002baa9  mov     ecx, 2; unsigned int
0x18002baae  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002bab3  test    r13d, r13d
0x18002bab6  jnz     short loc_18002BAD9
0x18002bab8  lea     rdx, aHsNoMachineBou; "%hs: No machine bound certificate could"...
0x18002babf  mov     ecx, 800h; unsigned int
0x18002bac4  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002bacb  mov     r9d, ebx
0x18002bace  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002bad3  mov     r14, [rbp+90h+var_78]
0x18002bad7  jmp     short loc_18002BB41
0x18002bad9  mov     r14, [rbp+90h+var_78]
0x18002badd  mov     rdx, rdi
0x18002bae0  mov     rcx, [rbp+90h+var_80]
0x18002bae4  mov     r8, [r14+18h]
0x18002bae8  mov     r9, [r8+80h]
0x18002baef  mov     r8d, [r8+78h]
0x18002baf3  call    cs:__imp_DsWriteNgcKeyW
0x18002baf9  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002bb00  mov     ebx, eax
0x18002bb02  test    eax, eax
0x18002bb04  jz      short loc_18002BB12
0x18002bb06  lea     rdx, aHsErrorWriting; "%hs: Error writing NGC Key to DC '%ls':"...
0x18002bb0d  jmp     loc_18002B9EE
0x18002bb12  lea     rdx, aHsSuccessfully_0; "%hs: Successfully provisioned the machi"...
0x18002bb19  jmp     short loc_18002BB37
0x18002bb1b  lea     rdx, aHsUnexpectedEr; "%hs: Unexpected error generating IUM bo"...
0x18002bb22  mov     ecx, 100h
0x18002bb27  jmp     short loc_18002BAC4
0x18002bb29  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002bb30  lea     rdx, aHsKeyAlreadyPr; "%hs: Key already provisioned in DS, not"...
0x18002bb37  mov     ecx, 2; unsigned int
0x18002bb3c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002bb41  mov     rcx, [rbp+90h+var_60]
0x18002bb45  test    rcx, rcx
0x18002bb48  jz      short loc_18002BB50
0x18002bb4a  call    cs:__imp_DsFreeNgcKey
0x18002bb50  cmp     [rbp+90h+var_80], r12
0x18002bb54  jz      short loc_18002BB60
0x18002bb56  lea     rcx, [rbp+90h+var_80]; phDS
0x18002bb5a  call    cs:__imp_DsUnBindW
0x18002bb60  test    r15, r15
0x18002bb63  jz      short loc_18002BB6E
0x18002bb65  mov     rcx, r15; Buffer
0x18002bb68  call    cs:__imp_NetApiBufferFree
0x18002bb6e  test    rdi, rdi
0x18002bb71  jz      short loc_18002BB8B
0x18002bb73  lea     rcx, [rdi-8]
0x18002bb77  cmp     dword ptr [rcx], 70616548h
0x18002bb7d  jnz     short loc_18002BB8B
0x18002bb7f  mov     rax, cs:g_pfnFree
0x18002bb86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb8b  mov     rcx, [rbp+90h+Buffer]; Buffer
0x18002bb8f  test    rcx, rcx
0x18002bb92  jz      short loc_18002BB9A
0x18002bb94  call    cs:__imp_NetApiBufferFree
0x18002bb9a  test    ebx, ebx
0x18002bb9c  jz      short loc_18002BBA8
0x18002bb9e  test    r13d, r13d
0x18002bba1  jz      short loc_18002BBA8
0x18002bba3  call    ?NlpDeleteIumBoundMachineAuthCert@@YAKXZ; NlpDeleteIumBoundMachineAuthCert(void)
0x18002bba8  test    r14, r14
0x18002bbab  jz      short loc_18002BBB6
0x18002bbad  mov     rcx, r14; pCertContext
0x18002bbb0  call    cs:__imp_CertFreeCertificateContext
0x18002bbb6  test    rsi, rsi
0x18002bbb9  jz      short loc_18002BBD3
0x18002bbbb  lea     rcx, [rsi-8]
0x18002bbbf  cmp     dword ptr [rcx], 70616548h
0x18002bbc5  jnz     short loc_18002BBD3
0x18002bbc7  mov     rax, cs:g_pfnFree
0x18002bbce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbd3  mov     eax, ebx
0x18002bbd5  mov     rcx, [rbp+90h+var_50]
0x18002bbd9  xor     rcx, rbp; StackCookie
0x18002bbdc  call    __security_check_cookie
  ... truncated ...
```
