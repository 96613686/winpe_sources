# CertOpenServerOcspResponse

- ea: `0x1800ab390`
- end: `0x1800ab4c0`
- name: `CertOpenServerOcspResponse`
- size: `304`
- prototype: `HCERT_SERVER_OCSP_RESPONSE __stdcall(PCCERT_CHAIN_CONTEXT pChainContext, DWORD dwFlags, PCERT_SERVER_OCSP_RESPONSE_OPEN_PARA pOpenPara)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800449d4`
- `0x180046e10`
- `0x1800ab390`
- `0x1800ab4c8`
- `0x1800b7300`
- `0x1800be40c`
- `0x1800c6470`
- `0x1800c6558`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011de54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011de54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ab437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011ddb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011de60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ab437`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011ddb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011de60`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011ddf7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18011ddf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011dde1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18011dde1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011de3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18011de3d`

## pseudocode

```c
HCERT_SERVER_OCSP_RESPONSE __stdcall CertOpenServerOcspResponse(
        PCCERT_CHAIN_CONTEXT pChainContext,
        DWORD dwFlags,
        PCERT_SERVER_OCSP_RESPONSE_OPEN_PARA pOpenPara)
{
  __int64 v4; // rdi
  char v5; // r14
  size_t v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  PCERT_SIMPLE_CHAIN v10; // rdx
  PCERT_CHAIN_ELEMENT *rgpElement; // r8
  DWORD v13; // ecx
  PCCERT_CONTEXT pCertContext; // rax
  PWSTR pwszOcspDirectory; // rcx
  __int64 v16; // rax
  DWORD *pcbUsedSize; // rax
  HANDLE CurrentThread; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  v5 = dwFlags;
  InitSrvOcspRespPara();
  if ( !pChainContext )
    goto LABEL_9;
  v7 = 0;
  if ( pOpenPara )
  {
    if ( pOpenPara->cbSize >= 0x28 )
    {
      v13 = pOpenPara->dwFlags & 2;
      if ( (pOpenPara->dwFlags & 1) != 0 )
      {
        if ( v13 )
          goto LABEL_27;
      }
      else if ( !v13 )
      {
        goto LABEL_25;
      }
      pwszOcspDirectory = pOpenPara->pwszOcspDirectory;
      if ( pwszOcspDirectory )
      {
        v16 = -1;
        do
          ++v16;
        while ( pwszOcspDirectory[v16] );
        v7 = 2LL * ((int)v16 + 1);
LABEL_25:
        pcbUsedSize = pOpenPara->pcbUsedSize;
        if ( pcbUsedSize )
          *pcbUsedSize = 40;
        goto LABEL_3;
      }
    }
LABEL_27:
    SetLastError(0x57u);
    return (HCERT_SERVER_OCSP_RESPONSE)v4;
  }
LABEL_3:
  v4 = PkiZeroAlloc(v7 + 160);
  if ( !v4 )
    goto LABEL_10;
  if ( pOpenPara )
  {
    *(_DWORD *)(v4 + 128) = pOpenPara->dwFlags;
    if ( v7 )
    {
      *(_QWORD *)(v4 + 136) = v4 + 160;
      memcpy_0((void *)(v4 + 160), pOpenPara->pwszOcspDirectory, v7);
    }
    *(_QWORD *)(v4 + 144) = pOpenPara->pfnUpdateCallback;
    *(_QWORD *)(v4 + 152) = pOpenPara->pvUpdateCallbackArg;
  }
  if ( !(unsigned int)Pki_InitializeCriticalSection(v4 + 16, v8, v9) )
    goto LABEL_6;
  *(_DWORD *)(v4 + 56) = 1;
  _InterlockedIncrement((volatile signed __int32 *)&pChainContext[1]);
  *(_QWORD *)(v4 + 80) = pChainContext;
  v10 = *pChainContext->rgpChain;
  rgpElement = v10->rgpElement;
  *(_QWORD *)(v4 + 88) = (*rgpElement)->pCertContext;
  if ( v10->cElement >= 2 )
  {
    pCertContext = rgpElement[1]->pCertContext;
  }
  else
  {
    if ( ((*rgpElement)->TrustStatus.dwInfoStatus & 8) == 0 )
    {
LABEL_9:
      SetLastError(0x57u);
      goto LABEL_10;
    }
    pCertContext = (*rgpElement)->pCertContext;
  }
  *(_QWORD *)(v4 + 96) = pCertContext;
  CurrentThread = GetCurrentThread();
  OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)(v4 + 104));
  if ( (v5 & 1) != 0 )
  {
    if ( (unsigned int)HasOcspAIAUrl(*(PCCERT_CONTEXT *)(v4 + 88)) )
      goto LABEL_31;
  }
  else
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( (unsigned int)UpdateSrvOcspResp((struct _SRV_OCSP_RESP *)v4, &SystemTimeAsFileTime)
      || GetLastError() != -2146885612 )
    {
LABEL_31:
      if ( (unsigned int)AddSrvOcspResp((struct _SRV_OCSP_RESP *)v4) )
      {
        *(_DWORD *)(v4 + 60) = 1;
        return (HCERT_SERVER_OCSP_RESPONSE)v4;
      }
LABEL_10:
      if ( !v4 )
        return (HCERT_SERVER_OCSP_RESPONSE)v4;
      goto LABEL_6;
    }
  }
  SetLastError(0x80092014);
LABEL_6:
  FreeSrvOcspResp((HLOCAL)v4);
  return 0;
}

```

## disassembly

```asm
0x1800ab390  push    rbx
0x1800ab392  push    rbp
0x1800ab393  push    rsi
0x1800ab394  push    rdi
0x1800ab395  push    r14
0x1800ab397  push    r15
0x1800ab399  sub     rsp, 28h
0x1800ab39d  xor     r15d, r15d
0x1800ab3a0  mov     rbx, r8
0x1800ab3a3  mov     edi, r15d
0x1800ab3a6  mov     r14d, edx
0x1800ab3a9  mov     rbp, rcx
0x1800ab3ac  call    ?InitSrvOcspRespPara@@YAXXZ; InitSrvOcspRespPara(void)
0x1800ab3b1  test    rbp, rbp
0x1800ab3b4  jz      short loc_1800AB432
0x1800ab3b6  mov     esi, r15d
0x1800ab3b9  test    rbx, rbx
0x1800ab3bc  jnz     loc_1800AB452
0x1800ab3c2  lea     rcx, [rsi+0A0h]; uBytes
0x1800ab3c9  call    PkiZeroAlloc
0x1800ab3ce  mov     rdi, rax
0x1800ab3d1  test    rax, rax
0x1800ab3d4  jz      short loc_1800AB43D
0x1800ab3d6  test    rbx, rbx
0x1800ab3d9  jnz     loc_1800AB478
0x1800ab3df  lea     rcx, [rdi+10h]
0x1800ab3e3  call    Pki_InitializeCriticalSection
0x1800ab3e8  test    eax, eax
0x1800ab3ea  jnz     short loc_1800AB3F9
0x1800ab3ec  mov     rcx, rdi; hMem
0x1800ab3ef  call    ?FreeSrvOcspResp@@YAXPEAU_SRV_OCSP_RESP@@@Z; FreeSrvOcspResp(_SRV_OCSP_RESP *)
0x1800ab3f4  mov     rdi, r15
0x1800ab3f7  jmp     short loc_1800AB442
0x1800ab3f9  mov     dword ptr [rdi+38h], 1
0x1800ab400  lock inc dword ptr [rbp+48h]
0x1800ab404  mov     [rdi+50h], rbp
0x1800ab408  mov     rax, [rbp+10h]
0x1800ab40c  mov     rdx, [rax]
0x1800ab40f  mov     r8, [rdx+10h]
0x1800ab413  mov     rax, [r8]
0x1800ab416  mov     rcx, [rax+8]
0x1800ab41a  mov     [rdi+58h], rcx
0x1800ab41e  cmp     dword ptr [rdx+0Ch], 2
0x1800ab422  jnb     loc_1800AB4B3
0x1800ab428  mov     rcx, [r8]
0x1800ab42b  mov     eax, [rcx+14h]
0x1800ab42e  test    al, 8
0x1800ab430  jnz     short loc_1800AB4AA
0x1800ab432  mov     ecx, 57h ; 'W'; dwErrCode
0x1800ab437  call    cs:__imp_SetLastError
0x1800ab43d  test    rdi, rdi
0x1800ab440  jnz     short loc_1800AB3EC
0x1800ab442  mov     rax, rdi
0x1800ab445  add     rsp, 28h
0x1800ab449  pop     r15
0x1800ab44b  pop     r14
0x1800ab44d  pop     rdi
0x1800ab44e  pop     rsi
0x1800ab44f  pop     rbp
0x1800ab450  pop     rbx
0x1800ab451  retn
0x1800ab452  cmp     dword ptr [rbx], 28h ; '('
0x1800ab455  jb      loc_18011DDB1
0x1800ab45b  mov     eax, [rbx+4]
0x1800ab45e  mov     ecx, eax
0x1800ab460  and     ecx, 2
0x1800ab463  test    al, 1
0x1800ab465  jnz     loc_18011DD76
0x1800ab46b  test    ecx, ecx
0x1800ab46d  jnz     loc_18011DD7A
0x1800ab473  jmp     loc_18011DD99
0x1800ab478  mov     eax, [rbx+4]
0x1800ab47b  mov     [rdi+80h], eax
0x1800ab481  test    rsi, rsi
0x1800ab484  jz      loc_18011DDC2
0x1800ab48a  lea     rcx, [rdi+0A0h]; void *
0x1800ab491  mov     r8, rsi; Size
0x1800ab494  mov     [rdi+88h], rcx
0x1800ab49b  mov     rdx, [rbx+10h]; Src
0x1800ab49f  call    memcpy_0
0x1800ab4a4  nop
0x1800ab4a5  jmp     loc_18011DDC2
0x1800ab4aa  mov     rax, [rcx+8]
0x1800ab4ae  jmp     loc_18011DDDD
0x1800ab4b3  mov     rax, [r8+8]
0x1800ab4b7  mov     rax, [rax+8]
0x1800ab4bb  jmp     loc_18011DDDD
0x18011dd76  test    ecx, ecx
0x18011dd78  jnz     short loc_18011DDB1
0x18011dd7a  mov     rcx, [rbx+10h]
0x18011dd7e  test    rcx, rcx
0x18011dd81  jz      short loc_18011DDB1
0x18011dd83  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011dd87  inc     rax
0x18011dd8a  cmp     [rcx+rax*2], r15w
0x18011dd8f  jnz     short loc_18011DD87
0x18011dd91  inc     eax
0x18011dd93  movsxd  rsi, eax
0x18011dd96  add     rsi, rsi
0x18011dd99  mov     rax, [rbx+8]
0x18011dd9d  test    rax, rax
0x18011dda0  jz      loc_1800AB3C2
0x18011dda6  mov     dword ptr [rax], 28h ; '('
0x18011ddac  jmp     loc_1800AB3C2
0x18011ddb1  mov     ecx, 57h ; 'W'; dwErrCode
0x18011ddb6  call    cs:__imp_SetLastError
0x18011ddbc  nop
0x18011ddbd  jmp     loc_1800AB442
0x18011ddc2  mov     rax, [rbx+18h]
0x18011ddc6  mov     [rdi+90h], rax
0x18011ddcd  mov     rax, [rbx+20h]
0x18011ddd1  mov     [rdi+98h], rax
0x18011ddd8  jmp     loc_1800AB3DF
0x18011dddd  mov     [rdi+60h], rax
0x18011dde1  call    cs:__imp_GetCurrentThread
0x18011dde7  mov     edx, 0Ch; DesiredAccess
0x18011ddec  lea     r9, [rdi+68h]; TokenHandle
0x18011ddf0  mov     rcx, rax; ThreadHandle
0x18011ddf3  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18011ddf7  call    cs:__imp_OpenThreadToken
0x18011ddfd  mov     ebx, 80092014h
0x18011de02  test    r14b, 1
0x18011de06  jz      short loc_18011DE33
0x18011de08  mov     rcx, [rdi+58h]; pCertContext
0x18011de0c  xor     edx, edx
0x18011de0e  call    _HasOcspAIAUrl
0x18011de13  test    eax, eax
0x18011de15  jz      short loc_18011DE5E
0x18011de17  mov     rcx, rdi; struct _SRV_OCSP_RESP *
0x18011de1a  call    ?AddSrvOcspResp@@YAHPEAU_SRV_OCSP_RESP@@@Z; AddSrvOcspResp(_SRV_OCSP_RESP *)
0x18011de1f  test    eax, eax
0x18011de21  jz      loc_1800AB43D
0x18011de27  mov     dword ptr [rdi+3Ch], 1
0x18011de2e  jmp     loc_1800AB442
0x18011de33  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18011de38  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18011de3d  call    cs:__imp_GetSystemTimeAsFileTime
0x18011de43  lea     rdx, [rsp+58h+SystemTimeAsFileTime]; struct _FILETIME *
0x18011de48  mov     rcx, rdi; struct _SRV_OCSP_RESP *
0x18011de4b  call    ?UpdateSrvOcspResp@@YAHPEAU_SRV_OCSP_RESP@@PEAU_FILETIME@@@Z; UpdateSrvOcspResp(_SRV_OCSP_RESP *,_FILETIME *)
0x18011de50  test    eax, eax
0x18011de52  jnz     short loc_18011DE17
0x18011de54  call    cs:__imp_GetLastError
0x18011de5a  cmp     eax, ebx
0x18011de5c  jnz     short loc_18011DE17
0x18011de5e  mov     ecx, ebx; dwErrCode
0x18011de60  call    cs:__imp_SetLastError
0x18011de66  nop
0x18011de67  jmp     loc_1800AB3EC
```
