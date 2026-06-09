# NlpStoreKeyInDS

- ea: `0x18002d098`
- end: `0x18002d58f`
- name: `NlpStoreKeyInDS`
- size: `1271`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002cf00`

## callees

- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x18002c758`
- `0x18002cf5c`
- `0x18002d098`
- `0x18003b6c4`
- `0x180070d64`
- `0x180070dc0`
- `0x180090180`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d307`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18002d340`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsBindWithSpnExW` at `0x18002d340`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18002d4de`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsUnBindW` at `0x18002d4de`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsFreeNgcKey` at `0x18002d4c8`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsFreeNgcKey` at `0x18002d4c8`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsWriteNgcKeyW` at `0x18002d46b`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsWriteNgcKeyW` at `0x18002d46b`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsReadNgcKeyW` at `0x18002d389`
- `api-ms-win-security-activedirectoryclient-l1-1-1!DsReadNgcKeyW` at `0x18002d389`
- `netutils!NetApiBufferFree` at `0x18002d4f2`
- `netutils!NetApiBufferFree` at `0x18002d524`
- `netutils!NetApiBufferFree` at `0x18002d4f2`
- `netutils!NetApiBufferFree` at `0x18002d524`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d546`
- `CRYPT32!CertFreeCertificateContext` at `0x18002d546`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18002d2f7`
- `ext-ms-win-secur32-translatename-l1-1-0!GetComputerObjectNameW` at `0x18002d2f7`

## string_xrefs

- `0x18002d1b6`: `%hs: Unable to allocate memory for computer acct name: %d\n`
- `0x18002d1ec`: `%hs: Error building computer acct name string: %d\n`
- `0x18002d2df`: `%hs: Allocate buffer for computer DN: %d\n`
- `0x18002d315`: `%hs: Unable to get computer DN: %d\n`
- `0x18002d3a6`: `%hs: Error reading NGC Key from DC '%ls': %d\n`
- `0x18002d4ae`: `%hs: Key already provisioned in DS, nothing to do\n`
- `0x18002d430`: `%hs: No machine bound certificate could be created: %d\n`

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
0x18002d098  push    rbp
0x18002d09a  push    rbx
0x18002d09b  push    rsi
0x18002d09c  push    rdi
0x18002d09d  push    r12
0x18002d09f  push    r13
0x18002d0a1  push    r14
0x18002d0a3  push    r15
0x18002d0a5  sub     rsp, 88h
0x18002d0ac  lea     rbp, [rsp+30h]
0x18002d0b1  mov     rax, cs:__security_cookie
0x18002d0b8  xor     rax, rbp
0x18002d0bb  mov     [rbp+90h+var_50], rax
0x18002d0bf  mov     rcx, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18002d0c6  xor     edx, edx
0x18002d0c8  mov     edi, edx
0x18002d0ca  mov     [rbp+90h+Buffer], rdx
0x18002d0ce  mov     r14d, edx
0x18002d0d1  mov     [rbp+90h+var_78], rdx
0x18002d0d5  mov     r15d, edx
0x18002d0d8  mov     [rbp+90h+var_68], rdx
0x18002d0dc  mov     [rbp+90h+var_80], rdx
0x18002d0e0  mov     r13d, edx
0x18002d0e3  mov     [rbp+90h+var_60], rdx
0x18002d0e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d0eb  mov     [rbp+90h+var_70], edx
0x18002d0ee  mov     [rbp+90h+nSize], 400h
0x18002d0f5  mov     [rbp+90h+var_84], 1
0x18002d0fc  inc     rax
0x18002d0ff  cmp     [rcx+rax*2], dx
0x18002d103  jnz     short loc_18002D0FC
0x18002d105  add     eax, 2
0x18002d108  mov     rsi, rdx
0x18002d10b  mov     r12d, eax
0x18002d10e  lea     rbx, [rax+rax]
0x18002d112  test    rbx, rbx
0x18002d115  jz      short loc_18002D178
0x18002d117  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002d11e  ja      short loc_18002D178
0x18002d120  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002d127  add     rcx, 8
0x18002d12b  add     rcx, rbx
0x18002d12e  cmp     rcx, rbx
0x18002d131  jb      short loc_18002D178
0x18002d133  call    VerifyStackAvailable
0x18002d138  test    eax, eax
0x18002d13a  jz      short loc_18002D178
0x18002d13c  lea     rax, [rbx+8]
0x18002d140  lea     rcx, [rax+0Fh]
0x18002d144  cmp     rcx, rax
0x18002d147  ja      short loc_18002D153
0x18002d149  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002d153  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002d157  mov     rax, rcx
0x18002d15a  call    _alloca_probe
0x18002d15f  sub     rsp, rcx
0x18002d162  lea     rsi, [rsp+0C0h+Buffer]
0x18002d167  test    rsi, rsi
0x18002d16a  jz      short loc_18002D178
0x18002d16c  mov     dword ptr [rsi], 6B637453h
0x18002d172  add     rsi, 8
0x18002d176  jnz     short loc_18002D19F
0x18002d178  lea     rcx, [rbx+8]
0x18002d17c  cmp     rcx, rbx
0x18002d17f  jb      short loc_18002D19F
0x18002d181  mov     rax, cs:g_pfnAllocate
0x18002d188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d18d  mov     rsi, rax
0x18002d190  test    rax, rax
0x18002d193  jz      short loc_18002D19F
0x18002d195  mov     dword ptr [rax], 70616548h
0x18002d19b  add     rsi, 8
0x18002d19f  test    rsi, rsi
0x18002d1a2  jnz     short loc_18002D1CA
0x18002d1a4  lea     ebx, [rsi+8]
0x18002d1a7  mov     ecx, 800h; unsigned int
0x18002d1ac  mov     r9d, ebx
0x18002d1af  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d1b6  lea     rdx, aHsUnableToAllo; "%hs: Unable to allocate memory for comp"...
0x18002d1bd  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d1c2  xor     r12d, r12d
0x18002d1c5  jmp     loc_18002D4BF
0x18002d1ca  mov     r9, cs:?NlGlobalUnicodeComputerName@@3PEAGEA; ushort * NlGlobalUnicodeComputerName
0x18002d1d1  lea     r8, aS; "%s$"
0x18002d1d8  mov     rdx, r12; unsigned __int64
0x18002d1db  mov     rcx, rsi; unsigned __int16 *
0x18002d1de  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d1e3  xor     r12d, r12d
0x18002d1e6  mov     ebx, eax
0x18002d1e8  test    eax, eax
0x18002d1ea  jz      short loc_18002D20C
0x18002d1ec  lea     rdx, aHsErrorBuildin_0; "%hs: Error building computer acct name "...
0x18002d1f3  mov     r9d, eax
0x18002d1f6  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d1fd  mov     ecx, 800h; unsigned int
0x18002d202  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d207  jmp     loc_18002D4BF
0x18002d20c  mov     eax, cs:?NlGlobalMemberWorkstation@@3HA; int NlGlobalMemberWorkstation
0x18002d212  lea     r9, [rbp+90h+Buffer]; struct _DOMAIN_CONTROLLER_INFOW **
0x18002d216  neg     eax
0x18002d218  mov     rdx, rsi; unsigned __int16 *
0x18002d21b  sbb     r8d, r8d
0x18002d21e  and     r8d, 0FFFFF000h
0x18002d225  add     r8d, 2000h; unsigned int
0x18002d22c  call    ?NlpLocateCurrentDomainDCNoCaching@@YAKKPEAGKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z; NlpLocateCurrentDomainDCNoCaching(ulong,ushort *,ulong,_DOMAIN_CONTROLLER_INFOW * *)
0x18002d231  mov     ebx, eax
0x18002d233  test    eax, eax
0x18002d235  jz      short loc_18002D240
0x18002d237  lea     rdx, aHsUnableToCont; "%hs: Unable to contact a threshold or h"...
0x18002d23e  jmp     short loc_18002D1F3
0x18002d240  mov     eax, [rbp+90h+nSize]
0x18002d243  lea     rbx, [rax+rax]
0x18002d247  test    rbx, rbx
0x18002d24a  jz      short loc_18002D2AD
0x18002d24c  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002d253  ja      short loc_18002D2AD
0x18002d255  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002d25c  add     rcx, 8
0x18002d260  add     rcx, rbx
0x18002d263  cmp     rcx, rbx
0x18002d266  jb      short loc_18002D2AD
0x18002d268  call    VerifyStackAvailable
0x18002d26d  test    eax, eax
0x18002d26f  jz      short loc_18002D2AD
0x18002d271  lea     rax, [rbx+8]
0x18002d275  lea     rcx, [rax+0Fh]
0x18002d279  cmp     rcx, rax
0x18002d27c  ja      short loc_18002D288
0x18002d27e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002d288  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002d28c  mov     rax, rcx
0x18002d28f  call    _alloca_probe
0x18002d294  sub     rsp, rcx
0x18002d297  lea     rdi, [rsp+0C0h+Buffer]
0x18002d29c  test    rdi, rdi
0x18002d29f  jz      short loc_18002D2AD
0x18002d2a1  mov     dword ptr [rdi], 6B637453h
0x18002d2a7  add     rdi, 8
0x18002d2ab  jnz     short loc_18002D2D4
0x18002d2ad  lea     rcx, [rbx+8]
0x18002d2b1  cmp     rcx, rbx
0x18002d2b4  jb      short loc_18002D2D4
0x18002d2b6  mov     rax, cs:g_pfnAllocate
0x18002d2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2c2  mov     rdi, rax
0x18002d2c5  test    rax, rax
0x18002d2c8  jz      short loc_18002D2D4
0x18002d2ca  mov     dword ptr [rax], 70616548h
0x18002d2d0  add     rdi, 8
0x18002d2d4  test    rdi, rdi
0x18002d2d7  jnz     short loc_18002D2EB
0x18002d2d9  lea     ebx, [rdi+8]
0x18002d2dc  mov     r9d, ebx
0x18002d2df  lea     rdx, aHsAllocateBuff; "%hs: Allocate buffer for computer DN: %"...
0x18002d2e6  jmp     loc_18002D1F6
0x18002d2eb  lea     r8, [rbp+90h+nSize]; nSize
0x18002d2ef  mov     rdx, rdi; lpNameBuffer
0x18002d2f2  mov     ecx, 1; NameFormat
0x18002d2f7  call    cs:__imp_GetComputerObjectNameW
0x18002d2fe  nop     dword ptr [rax+rax+00h]
0x18002d303  test    al, al
0x18002d305  jnz     short loc_18002D321
0x18002d307  call    cs:__imp_GetLastError
0x18002d30e  nop     dword ptr [rax+rax+00h]
0x18002d313  mov     ebx, eax
0x18002d315  lea     rdx, aHsUnableToGetC; "%hs: Unable to get computer DN: %d\n"
0x18002d31c  jmp     loc_18002D1F3
0x18002d321  mov     rcx, [rbp+90h+Buffer]
0x18002d325  lea     rax, [rbp+90h+var_80]
0x18002d329  mov     [rsp+0C0h+phDS], rax; phDS
0x18002d32e  xor     r9d, r9d; ServicePrincipalName
0x18002d331  xor     r8d, r8d; AuthIdentity
0x18002d334  mov     dword ptr [rsp+0C0h+BindFlags], r12d; BindFlags
0x18002d339  mov     rdx, [rcx+28h]; DnsDomainName
0x18002d33d  mov     rcx, [rcx]; DomainControllerName
0x18002d340  call    cs:__imp_DsBindWithSpnExW
0x18002d347  nop     dword ptr [rax+rax+00h]
0x18002d34c  mov     ebx, eax
0x18002d34e  test    eax, eax
0x18002d350  jz      short loc_18002D37A
0x18002d352  lea     rdx, aHsErrorBinding; "%hs: Error binding to DC '%ls': %d\n"
0x18002d359  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d360  mov     r9, [rbp+90h+Buffer]
0x18002d364  mov     ecx, 800h; unsigned int
0x18002d369  mov     dword ptr [rsp+0C0h+BindFlags], eax
0x18002d36d  mov     r9, [r9]
0x18002d370  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d375  jmp     loc_18002D4BF
0x18002d37a  mov     rcx, [rbp+90h+var_80]
0x18002d37e  lea     r9, [rbp+90h+var_60]
0x18002d382  lea     r8, [rbp+90h+var_70]
0x18002d386  mov     rdx, rdi
0x18002d389  call    cs:__imp_DsReadNgcKeyW
0x18002d390  nop     dword ptr [rax+rax+00h]
0x18002d395  mov     ebx, eax
0x18002d397  test    eax, eax
0x18002d399  jz      loc_18002D4A7
0x18002d39f  cmp     eax, 200Ah
0x18002d3a4  jz      short loc_18002D3AF
0x18002d3a6  lea     rdx, aHsErrorReading_0; "%hs: Error reading NGC Key from DC '%ls"...
0x18002d3ad  jmp     short loc_18002D359
0x18002d3af  lea     rcx, [rbp+90h+var_68]
0x18002d3b3  call    NlpGenerateMachineKeyCertificateSubjectName
0x18002d3b8  mov     ebx, eax
0x18002d3ba  test    eax, eax
0x18002d3bc  jz      short loc_18002D3E2
0x18002d3be  mov     r9d, eax
0x18002d3c1  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d3c8  lea     rdx, aHsErrorBuildin; "%hs: Error building cert subject string"...
0x18002d3cf  mov     ecx, 800h; unsigned int
0x18002d3d4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d3d9  mov     r15, [rbp+90h+var_68]
0x18002d3dd  jmp     loc_18002D4BF
0x18002d3e2  mov     r15, [rbp+90h+var_68]
0x18002d3e6  lea     r8, [rbp+90h+var_84]; int *
0x18002d3ea  mov     rcx, r15; unsigned __int16 *
0x18002d3ed  lea     rdx, [rbp+90h+var_78]; struct _CERT_CONTEXT **
0x18002d3f1  call    ?NlpGenerateIumBoundMachineAuthCert@@YAKPEBGPEAPEBU_CERT_CONTEXT@@PEAH@Z; NlpGenerateIumBoundMachineAuthCert(ushort const *,_CERT_CONTEXT const * *,int *)
0x18002d3f6  mov     ebx, eax
0x18002d3f8  test    eax, eax
0x18002d3fa  jnz     short loc_18002D409
0x18002d3fc  lea     r13d, [rax+1]
0x18002d400  lea     rdx, aHsIumBoundCert; "%hs: IUM bound certificate successfully"...
0x18002d407  jmp     short loc_18002D41A
0x18002d409  cmp     [rbp+90h+var_84], r12d
0x18002d40d  jnz     loc_18002D499
0x18002d413  lea     rdx, aHsIumProvision; "%hs: IUM Provisioning interface not up."...
0x18002d41a  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d421  mov     ecx, 2; unsigned int
0x18002d426  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d42b  test    r13d, r13d
0x18002d42e  jnz     short loc_18002D451
0x18002d430  lea     rdx, aHsNoMachineBou; "%hs: No machine bound certificate could"...
0x18002d437  mov     ecx, 800h; unsigned int
0x18002d43c  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d443  mov     r9d, ebx
0x18002d446  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d44b  mov     r14, [rbp+90h+var_78]
0x18002d44f  jmp     short loc_18002D4BF
0x18002d451  mov     r14, [rbp+90h+var_78]
0x18002d455  mov     rdx, rdi
0x18002d458  mov     rcx, [rbp+90h+var_80]
0x18002d45c  mov     r8, [r14+18h]
0x18002d460  mov     r9, [r8+80h]
0x18002d467  mov     r8d, [r8+78h]
0x18002d46b  call    cs:__imp_DsWriteNgcKeyW
0x18002d472  nop     dword ptr [rax+rax+00h]
0x18002d477  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d47e  mov     ebx, eax
0x18002d480  test    eax, eax
0x18002d482  jz      short loc_18002D490
0x18002d484  lea     rdx, aHsErrorWriting; "%hs: Error writing NGC Key to DC '%ls':"...
0x18002d48b  jmp     loc_18002D360
0x18002d490  lea     rdx, aHsSuccessfully_0; "%hs: Successfully provisioned the machi"...
0x18002d497  jmp     short loc_18002D4B5
0x18002d499  lea     rdx, aHsUnexpectedEr; "%hs: Unexpected error generating IUM bo"...
0x18002d4a0  mov     ecx, 100h
0x18002d4a5  jmp     short loc_18002D43C
0x18002d4a7  lea     r8, aNlpstorekeyind; "NlpStoreKeyInDS"
0x18002d4ae  lea     rdx, aHsKeyAlreadyPr; "%hs: Key already provisioned in DS, not"...
0x18002d4b5  mov     ecx, 2; unsigned int
0x18002d4ba  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002d4bf  mov     rcx, [rbp+90h+var_60]
0x18002d4c3  test    rcx, rcx
0x18002d4c6  jz      short loc_18002D4D4
0x18002d4c8  call    cs:__imp_DsFreeNgcKey
0x18002d4cf  nop     dword ptr [rax+rax+00h]
0x18002d4d4  cmp     [rbp+90h+var_80], r12
0x18002d4d8  jz      short loc_18002D4EA
0x18002d4da  lea     rcx, [rbp+90h+var_80]; phDS
0x18002d4de  call    cs:__imp_DsUnBindW
0x18002d4e5  nop     dword ptr [rax+rax+00h]
0x18002d4ea  test    r15, r15
0x18002d4ed  jz      short loc_18002D4FE
0x18002d4ef  mov     rcx, r15; Buffer
0x18002d4f2  call    cs:__imp_NetApiBufferFree
0x18002d4f9  nop     dword ptr [rax+rax+00h]
0x18002d4fe  test    rdi, rdi
0x18002d501  jz      short loc_18002D51B
0x18002d503  lea     rcx, [rdi-8]
0x18002d507  cmp     dword ptr [rcx], 70616548h
0x18002d50d  jnz     short loc_18002D51B
0x18002d50f  mov     rax, cs:g_pfnFree
0x18002d516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d51b  mov     rcx, [rbp+90h+Buffer]; Buffer
0x18002d51f  test    rcx, rcx
0x18002d522  jz      short loc_18002D530
0x18002d524  call    cs:__imp_NetApiBufferFree
0x18002d52b  nop     dword ptr [rax+rax+00h]
0x18002d530  test    ebx, ebx
0x18002d532  jz      short loc_18002D53E
0x18002d534  test    r13d, r13d
0x18002d537  jz      short loc_18002D53E
0x18002d539  call    ?NlpDeleteIumBoundMachineAuthCert@@YAKXZ; NlpDeleteIumBoundMachineAuthCert(void)
0x18002d53e  test    r14, r14
0x18002d541  jz      short loc_18002D552
0x18002d543  mov     rcx, r14; pCertContext
0x18002d546  call    cs:__imp_CertFreeCertificateContext
0x18002d54d  nop     dword ptr [rax+rax+00h]
0x18002d552  test    rsi, rsi
  ... truncated ...
```
