# I_ReaderListCngPopulateCredsViaCertStore

- ea: `0x18001f548`
- end: `0x18001f99a`
- name: `I_ReaderListCngPopulateCredsViaCertStore`
- size: `1106`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180010d90`

## callees

- `0x180002aa0`
- `0x180004600`
- `0x180006010`
- `0x18000a980`
- `0x18000e33c`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001f548`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f893`
- `CRYPT32!CertCloseStore` at `0x18001f908`
- `CRYPT32!CertCloseStore` at `0x18001f908`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001f6b2`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001f6b2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f6d0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f7a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f6d0`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001f7a8`
- `ncrypt!NCryptGetProperty` at `0x18001f661`
- `ncrypt!NCryptGetProperty` at `0x18001f661`

## pseudocode

```c
__int64 __fastcall I_ReaderListCngPopulateCredsViaCertStore(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int *p_pcbData; // rdi
  __int64 v7; // rcx
  DWORD LastError; // ebx
  unsigned int Property; // r12d
  STRSAFE_LPSTR v10; // rcx
  int v11; // edx
  NCRYPT_HANDLE v12; // rcx
  __int64 v13; // rcx
  const CERT_CONTEXT *v14; // r14
  const CERT_CONTEXT *v15; // rax
  unsigned __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  unsigned int *v21; // rax
  __int64 v22; // rcx
  STRSAFE_LPSTR v23; // rcx
  int v24; // edx
  __int64 v25; // rcx
  unsigned int *v26; // rcx
  char v27; // al
  __int64 v29; // [rsp+0h] [rbp-30h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-10h]
  DWORD pcbData; // [rsp+30h] [rbp+0h] BYREF
  BYTE pbOutput[8]; // [rsp+38h] [rbp+8h] BYREF
  __int64 v33; // [rsp+40h] [rbp+10h] BYREF
  __int64 v34; // [rsp+48h] [rbp+18h]
  __int64 v35; // [rsp+50h] [rbp+20h]

  p_pcbData = 0;
  v35 = a2;
  pcbData = 0;
  v33 = 0;
  v34 = a1;
  *(_QWORD *)pbOutput = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  LastError = I_SetupNCryptStorageProvider(a3);
  if ( LastError )
  {
    Property = 0;
    WppTraceIndent(v7, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_51;
    }
    v11 = 149;
    LODWORD(pcbResult) = LastError;
    goto LABEL_10;
  }
  v12 = *(_QWORD *)(a3 + 136);
  pcbData = 8;
  Property = NCryptGetProperty(v12, L"SmartCardUserCertStore", pbOutput, 8u, &pcbData, 0x40u);
  if ( Property )
  {
    WppTraceIndent(v13, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_51;
    }
    v11 = 150;
    LODWORD(pcbResult) = Property;
LABEL_10:
    WPP_SF_sD(
      *((_QWORD *)v10 + 2),
      v11,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      (char)pcbResult);
    goto LABEL_51;
  }
  v14 = 0;
  while ( 1 )
  {
    v15 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbOutput, v14);
    v14 = v15;
    if ( !v15 )
    {
      *(_QWORD *)(a3 + 168) = *(_QWORD *)pbOutput;
      *(_QWORD *)pbOutput = 0;
      goto LABEL_51;
    }
    if ( !CertGetCertificateContextProperty(v15, 2u, 0, &pcbData) )
    {
      LastError = GetLastError();
      WppTraceIndent(v25, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_51;
      }
      v24 = 151;
LABEL_49:
      WPP_SF_sD(
        *((_QWORD *)v23 + 2),
        v24,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
      goto LABEL_51;
    }
    if ( p_pcbData && *(p_pcbData - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    v16 = pcbData;
    p_pcbData = 0;
    if ( !pcbData
      || pcbData > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)pcbData + g_ulAdditionalProbeSize + 8 < pcbData
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_30;
    }
    v17 = v16 + 23;
    if ( v16 + 23 <= v16 + 8 )
      v17 = 0xFFFFFFFFFFFFFF0LL;
    v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
    v19 = alloca(v18);
    v20 = alloca(v18);
    p_pcbData = &pcbData;
    if ( &v29 == (__int64 *)-48LL || (pcbData = 1801679955, (p_pcbData = (unsigned int *)pbOutput) == 0) )
    {
LABEL_30:
      v18 = v16 + 8;
      if ( v16 + 8 >= v16 )
      {
        v21 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
        p_pcbData = v21;
        if ( v21 )
        {
          *v21 = 1885431112;
          p_pcbData = v21 + 2;
        }
      }
    }
    if ( !p_pcbData )
      break;
    if ( !CertGetCertificateContextProperty(v14, 2u, p_pcbData, &pcbData) )
    {
      LastError = GetLastError();
      WppTraceIndent(v22, 2);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_51;
      }
      v24 = 153;
      goto LABEL_49;
    }
    if ( !(unsigned int)I_ReaderListBuildCredFromCertContext(v34, v14, *(_QWORD *)p_pcbData, p_pcbData[10], &v33) )
    {
      I_ReaderListAddCredToList(v33, v35, a3 + 232);
      ++*a4;
      v33 = 0;
    }
  }
  WppTraceIndent(v18, 2);
  LastError = 8;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
LABEL_51:
  v26 = *(unsigned int **)pbOutput;
  if ( *(_QWORD *)pbOutput )
    CertCloseStore(*(HCERTSTORE *)pbOutput, 0);
  if ( p_pcbData )
  {
    v26 = p_pcbData - 2;
    if ( *(p_pcbData - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  WppTraceIndent(v26, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    v27 = LastError;
    if ( !LastError )
      v27 = Property;
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      154,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v27);
  }
  if ( !LastError )
    return Property;
  return LastError;
}

```

## disassembly

```asm
0x18001f548  push    rbp
0x18001f54a  push    rbx
0x18001f54b  push    rsi
0x18001f54c  push    rdi
0x18001f54d  push    r12
0x18001f54f  push    r13
0x18001f551  push    r14
0x18001f553  push    r15
0x18001f555  sub     rsp, 78h
0x18001f559  lea     rbp, [rsp+30h]
0x18001f55e  mov     rax, cs:__security_cookie
0x18001f565  xor     rax, rbp
0x18001f568  mov     [rbp+80h+var_50], rax
0x18001f56c  xor     edi, edi
0x18001f56e  mov     [rbp+80h+var_60], rdx
0x18001f572  xor     edx, edx
0x18001f574  mov     [rbp+80h+pcbData], edi
0x18001f577  mov     [rbp+80h+var_70], rdi
0x18001f57b  mov     r13, r9
0x18001f57e  mov     r15, r8
0x18001f581  mov     [rbp+80h+var_68], rcx
0x18001f585  mov     qword ptr [rbp+80h+pbOutput], 0
0x18001f58d  call    WppTraceIndent
0x18001f592  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f599  lea     r14, WPP_GLOBAL_Control
0x18001f5a0  lea     esi, [rdi+2]
0x18001f5a3  cmp     rcx, r14
0x18001f5a6  jz      short loc_18001F5D0
0x18001f5a8  test    [rcx+1Ch], sil
0x18001f5ac  jz      short loc_18001F5D0
0x18001f5ae  cmp     byte ptr [rcx+19h], 5
0x18001f5b2  jb      short loc_18001F5D0
0x18001f5b4  mov     r9, cs:WPP_pszIndent
0x18001f5bb  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f5c2  mov     rcx, [rcx+10h]
0x18001f5c6  mov     edx, 94h
0x18001f5cb  call    WPP_SF_s
0x18001f5d0  mov     rcx, r15
0x18001f5d3  call    I_SetupNCryptStorageProvider
0x18001f5d8  mov     ebx, eax
0x18001f5da  test    eax, eax
0x18001f5dc  jz      short loc_18001F631
0x18001f5de  xor     r12d, r12d
0x18001f5e1  mov     edx, esi
0x18001f5e3  call    WppTraceIndent
0x18001f5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5ef  cmp     rcx, r14
0x18001f5f2  jz      loc_18001F8F6
0x18001f5f8  test    byte ptr [rcx+1Ch], 1
0x18001f5fc  jz      loc_18001F8F6
0x18001f602  cmp     [rcx+19h], sil
0x18001f606  jb      loc_18001F8F6
0x18001f60c  mov     edx, 95h
0x18001f611  mov     dword ptr [rsp+0B0h+pcbResult], ebx
0x18001f615  mov     r9, cs:WPP_pszIndent
0x18001f61c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f623  mov     rcx, [rcx+10h]
0x18001f627  call    WPP_SF_sD
0x18001f62c  jmp     loc_18001F8F6
0x18001f631  mov     rcx, [r15+88h]; hObject
0x18001f638  lea     rax, [rbp+80h+pcbData]
0x18001f63c  mov     [rsp+0B0h+dwFlags], 40h ; '@'; dwFlags
0x18001f644  lea     r8, [rbp+80h+pbOutput]; pbOutput
0x18001f648  mov     r9d, 8; cbOutput
0x18001f64e  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18001f653  lea     rdx, aSmartcarduserc; "SmartCardUserCertStore"
0x18001f65a  mov     [rbp+80h+pcbData], 8
0x18001f661  call    cs:__imp_NCryptGetProperty
0x18001f667  mov     r12d, eax
0x18001f66a  test    eax, eax
0x18001f66c  jz      short loc_18001F6A8
0x18001f66e  mov     edx, esi
0x18001f670  call    WppTraceIndent
0x18001f675  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f67c  cmp     rcx, r14
0x18001f67f  jz      loc_18001F8F6
0x18001f685  test    byte ptr [rcx+1Ch], 1
0x18001f689  jz      loc_18001F8F6
0x18001f68f  cmp     [rcx+19h], sil
0x18001f693  jb      loc_18001F8F6
0x18001f699  mov     edx, 96h
0x18001f69e  mov     dword ptr [rsp+0B0h+pcbResult], r12d
0x18001f6a3  jmp     loc_18001F615
0x18001f6a8  xor     r14d, r14d
0x18001f6ab  mov     rcx, qword ptr [rbp+80h+pbOutput]; hCertStore
0x18001f6af  mov     rdx, r14; pPrevCertContext
0x18001f6b2  call    cs:__imp_CertEnumCertificatesInStore
0x18001f6b8  mov     r14, rax
0x18001f6bb  test    rax, rax
0x18001f6be  jz      loc_18001F8E3
0x18001f6c4  lea     r9, [rbp+80h+pcbData]; pcbData
0x18001f6c8  xor     r8d, r8d; pvData
0x18001f6cb  mov     edx, esi; dwPropId
0x18001f6cd  mov     rcx, rax; pCertContext
0x18001f6d0  call    cs:__imp_CertGetCertificateContextProperty
0x18001f6d6  cmp     eax, 1
0x18001f6d9  jnz     loc_18001F893
0x18001f6df  test    rdi, rdi
0x18001f6e2  jz      short loc_18001F6FC
0x18001f6e4  lea     rcx, [rdi-8]
0x18001f6e8  cmp     dword ptr [rcx], 70616548h
0x18001f6ee  jnz     short loc_18001F6FC
0x18001f6f0  mov     rax, cs:g_pfnFree
0x18001f6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6fc  mov     esi, [rbp+80h+pcbData]
0x18001f6ff  xor     edi, edi
0x18001f701  test    rsi, rsi
0x18001f704  jz      short loc_18001F767
0x18001f706  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001f70d  ja      short loc_18001F767
0x18001f70f  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001f716  add     rcx, 8
0x18001f71a  add     rcx, rsi
0x18001f71d  cmp     rcx, rsi
0x18001f720  jb      short loc_18001F767
0x18001f722  call    VerifyStackAvailable
0x18001f727  test    eax, eax
0x18001f729  jz      short loc_18001F767
0x18001f72b  lea     rax, [rsi+8]
0x18001f72f  lea     rcx, [rax+0Fh]
0x18001f733  cmp     rcx, rax
0x18001f736  ja      short loc_18001F742
0x18001f738  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001f742  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001f746  mov     rax, rcx
0x18001f749  call    _alloca_probe
0x18001f74e  sub     rsp, rcx
0x18001f751  lea     rdi, [rsp+0B0h+pcbData]
0x18001f756  test    rdi, rdi
0x18001f759  jz      short loc_18001F767
0x18001f75b  mov     dword ptr [rdi], 6B637453h
0x18001f761  add     rdi, 8
0x18001f765  jnz     short loc_18001F78E
0x18001f767  lea     rcx, [rsi+8]
0x18001f76b  cmp     rcx, rsi
0x18001f76e  jb      short loc_18001F78E
0x18001f770  mov     rax, cs:g_pfnAllocate
0x18001f777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f77c  mov     rdi, rax
0x18001f77f  test    rax, rax
0x18001f782  jz      short loc_18001F78E
0x18001f784  mov     dword ptr [rax], 70616548h
0x18001f78a  add     rdi, 8
0x18001f78e  mov     esi, 2
0x18001f793  mov     edx, esi; dwPropId
0x18001f795  test    rdi, rdi
0x18001f798  jz      loc_18001F840
0x18001f79e  lea     r9, [rbp+80h+pcbData]; pcbData
0x18001f7a2  mov     r8, rdi; pvData
0x18001f7a5  mov     rcx, r14; pCertContext
0x18001f7a8  call    cs:__imp_CertGetCertificateContextProperty
0x18001f7ae  cmp     eax, 1
0x18001f7b1  jnz     short loc_18001F7FC
0x18001f7b3  mov     r9d, [rdi+28h]
0x18001f7b7  lea     rax, [rbp+80h+var_70]
0x18001f7bb  mov     r8, [rdi]
0x18001f7be  mov     rdx, r14
0x18001f7c1  mov     rcx, [rbp+80h+var_68]
0x18001f7c5  mov     [rsp+0B0h+pcbResult], rax
0x18001f7ca  call    I_ReaderListBuildCredFromCertContext
0x18001f7cf  test    eax, eax
0x18001f7d1  jnz     loc_18001F6AB
0x18001f7d7  mov     rdx, [rbp+80h+var_60]
0x18001f7db  lea     r8, [r15+0E8h]
0x18001f7e2  mov     rcx, [rbp+80h+var_70]
0x18001f7e6  call    I_ReaderListAddCredToList
0x18001f7eb  inc     dword ptr [r13+0]
0x18001f7ef  mov     [rbp+80h+var_70], 0
0x18001f7f7  jmp     loc_18001F6AB
0x18001f7fc  call    cs:__imp_GetLastError
0x18001f802  mov     edx, esi
0x18001f804  mov     ebx, eax
0x18001f806  call    WppTraceIndent
0x18001f80b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f812  lea     r14, WPP_GLOBAL_Control
0x18001f819  cmp     rcx, r14
0x18001f81c  jz      loc_18001F8FD
0x18001f822  test    byte ptr [rcx+1Ch], 1
0x18001f826  jz      loc_18001F8FD
0x18001f82c  cmp     [rcx+19h], sil
0x18001f830  jb      loc_18001F8FD
0x18001f836  mov     edx, 99h
0x18001f83b  jmp     loc_18001F8C6
0x18001f840  call    WppTraceIndent
0x18001f845  mov     ebx, 8
0x18001f84a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f851  lea     r14, WPP_GLOBAL_Control
0x18001f858  cmp     rcx, r14
0x18001f85b  jz      loc_18001F8FD
0x18001f861  test    byte ptr [rcx+1Ch], 1
0x18001f865  jz      loc_18001F8FD
0x18001f86b  cmp     [rcx+19h], sil
0x18001f86f  jb      loc_18001F8FD
0x18001f875  mov     r9, cs:WPP_pszIndent
0x18001f87c  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f883  mov     rcx, [rcx+10h]
0x18001f887  mov     edx, 98h
0x18001f88c  call    WPP_SF_s
0x18001f891  jmp     short loc_18001F8FD
0x18001f893  call    cs:__imp_GetLastError
0x18001f899  mov     edx, esi
0x18001f89b  mov     ebx, eax
0x18001f89d  call    WppTraceIndent
0x18001f8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8a9  lea     r14, WPP_GLOBAL_Control
0x18001f8b0  cmp     rcx, r14
0x18001f8b3  jz      short loc_18001F8FD
0x18001f8b5  test    byte ptr [rcx+1Ch], 1
0x18001f8b9  jz      short loc_18001F8FD
0x18001f8bb  cmp     [rcx+19h], sil
0x18001f8bf  jb      short loc_18001F8FD
0x18001f8c1  mov     edx, 97h
0x18001f8c6  mov     r9, cs:WPP_pszIndent
0x18001f8cd  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f8d4  mov     rcx, [rcx+10h]
0x18001f8d8  mov     dword ptr [rsp+0B0h+pcbResult], ebx
0x18001f8dc  call    WPP_SF_sD
0x18001f8e1  jmp     short loc_18001F8FD
0x18001f8e3  mov     rax, qword ptr [rbp+80h+pbOutput]
0x18001f8e7  mov     [r15+0A8h], rax
0x18001f8ee  mov     qword ptr [rbp+80h+pbOutput], 0
0x18001f8f6  lea     r14, WPP_GLOBAL_Control
0x18001f8fd  mov     rcx, qword ptr [rbp+80h+pbOutput]; hCertStore
0x18001f901  test    rcx, rcx
0x18001f904  jz      short loc_18001F90E
0x18001f906  xor     edx, edx; dwFlags
0x18001f908  call    cs:__imp_CertCloseStore
0x18001f90e  test    rdi, rdi
0x18001f911  jz      short loc_18001F92B
0x18001f913  lea     rcx, [rdi-8]
0x18001f917  cmp     dword ptr [rcx], 70616548h
0x18001f91d  jnz     short loc_18001F92B
0x18001f91f  mov     rax, cs:g_pfnFree
0x18001f926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f92b  mov     edx, 1
0x18001f930  call    WppTraceIndent
0x18001f935  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f93c  cmp     rcx, r14
0x18001f93f  jz      short loc_18001F975
0x18001f941  test    [rcx+1Ch], sil
0x18001f945  jz      short loc_18001F975
0x18001f947  cmp     byte ptr [rcx+19h], 5
0x18001f94b  jb      short loc_18001F975
0x18001f94d  mov     r9, cs:WPP_pszIndent
0x18001f954  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f95b  mov     rcx, [rcx+10h]
0x18001f95f  test    ebx, ebx
0x18001f961  mov     eax, ebx
0x18001f963  mov     edx, 9Ah
0x18001f968  cmovz   eax, r12d
0x18001f96c  mov     dword ptr [rsp+0B0h+pcbResult], eax
0x18001f970  call    WPP_SF_sD
0x18001f975  test    ebx, ebx
0x18001f977  cmovz   ebx, r12d
0x18001f97b  mov     eax, ebx
0x18001f97d  mov     rcx, [rbp+80h+var_50]
0x18001f981  xor     rcx, rbp; StackCookie
0x18001f984  call    __security_check_cookie
0x18001f989  lea     rsp, [rbp+48h]
0x18001f98d  pop     r15
0x18001f98f  pop     r14
0x18001f991  pop     r13
0x18001f993  pop     r12
0x18001f995  pop     rdi
0x18001f996  pop     rsi
0x18001f997  pop     rbx
0x18001f998  pop     rbp
0x18001f999  retn
```
