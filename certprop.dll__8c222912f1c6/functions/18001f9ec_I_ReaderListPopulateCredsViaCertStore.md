# I_ReaderListPopulateCredsViaCertStore

- ea: `0x18001f9ec`
- end: `0x18001fdf6`
- name: `I_ReaderListPopulateCredsViaCertStore`
- size: `1034`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001e4bc`

## callees

- `0x180002aa0`
- `0x180004600`
- `0x18000a980`
- `0x18000cce0`
- `0x18000e33c`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001f9ec`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fce3`
- `CRYPT32!CertCloseStore` at `0x18001fd57`
- `CRYPT32!CertCloseStore` at `0x18001fd57`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001fb06`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18001fb06`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fd65`
- `CRYPT32!CertFreeCertificateContext` at `0x18001fd65`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001fb26`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001fbf9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001fb26`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18001fbf9`
- `ADVAPI32!CryptGetProvParam` at `0x18001fa92`
- `ADVAPI32!CryptGetProvParam` at `0x18001fa92`

## pseudocode

```c
__int64 __fastcall I_ReaderListPopulateCredsViaCertStore(__int64 a1, __int64 a2, _DWORD *a3)
{
  const CERT_CONTEXT *v4; // r15
  unsigned int *p_pdwDataLen; // rbx
  void *v6; // r12
  HCRYPTPROV v9; // rcx
  DWORD LastError; // esi
  __int64 v11; // rcx
  STRSAFE_LPSTR v12; // rcx
  int v13; // edx
  const CERT_CONTEXT *v14; // rax
  unsigned __int64 v15; // rdi
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  unsigned int *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  DWORD v23; // edi
  unsigned int *v24; // rcx
  __int64 v26; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  BYTE pbData[8]; // [rsp+38h] [rbp+8h] BYREF
  void *v29; // [rsp+40h] [rbp+10h] BYREF
  _DWORD *v30; // [rsp+48h] [rbp+18h]

  v30 = a3;
  *(_QWORD *)pbData = 0;
  pdwDataLen = 0;
  v4 = 0;
  v29 = 0;
  p_pdwDataLen = 0;
  v6 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v9 = *(_QWORD *)(a2 + 128);
  *a3 = 0;
  LastError = 8;
  pdwDataLen = 8;
  if ( CryptGetProvParam(v9, 0x2Au, pbData, &pdwDataLen, 0) )
  {
    while ( 1 )
    {
      v14 = CertEnumCertificatesInStore(*(HCERTSTORE *)pbData, v4);
      v4 = v14;
      if ( !v14 )
      {
        LastError = 0;
        *(_QWORD *)(a2 + 168) = *(_QWORD *)pbData;
        *(_DWORD *)(a2 + 148) = 1;
        *(_QWORD *)pbData = 0;
        goto LABEL_45;
      }
      if ( !CertGetCertificateContextProperty(v14, 2u, 0, &pdwDataLen) )
        break;
      if ( p_pdwDataLen && *(p_pdwDataLen - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      v15 = pdwDataLen;
      p_pdwDataLen = 0;
      if ( !pdwDataLen
        || pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize
        || (unsigned __int64)pdwDataLen + g_ulAdditionalProbeSize + 8 < pdwDataLen
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_24;
      }
      v16 = v15 + 23;
      if ( v15 + 23 <= v15 + 8 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
      v18 = alloca(v17);
      v19 = alloca(v17);
      p_pdwDataLen = &pdwDataLen;
      if ( &v26 == (__int64 *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = (unsigned int *)pbData) == 0) )
      {
LABEL_24:
        v17 = v15 + 8;
        if ( v15 + 8 >= v15 )
        {
          v20 = (unsigned int *)((__int64 (*)(void))g_pfnAllocate)();
          p_pdwDataLen = v20;
          if ( v20 )
          {
            *v20 = 1885431112;
            p_pdwDataLen = v20 + 2;
          }
        }
      }
      if ( !p_pdwDataLen )
      {
        WppTraceIndent(v17, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
            WPP_pszIndent);
        }
        goto LABEL_45;
      }
      if ( !CertGetCertificateContextProperty(v4, 2u, p_pdwDataLen, &pdwDataLen) )
      {
        LastError = GetLastError();
        WppTraceIndent(v21, 2);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          v13 = 103;
          goto LABEL_10;
        }
        goto LABEL_45;
      }
      if ( (unsigned int)I_ReaderListBuildCredFromCertContext(a1, v4, *(_QWORD *)p_pdwDataLen, p_pdwDataLen[10], &v29) )
      {
        v6 = v29;
      }
      else
      {
        I_ReaderListAddCredToList(v29, *(_QWORD *)(a2 + 96), a2 + 232);
        ++*v30;
        v6 = 0;
        v29 = 0;
      }
    }
    LastError = GetLastError();
    WppTraceIndent(v22, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v13 = 101;
      goto LABEL_10;
    }
  }
  else
  {
    LastError = GetLastError();
    WppTraceIndent(v11, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v13 = 100;
LABEL_10:
      WPP_SF_sD(
        *((_QWORD *)v12 + 2),
        v13,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
    }
  }
LABEL_45:
  v23 = 0;
  v24 = *(unsigned int **)pbData;
  if ( !*v30 )
    v23 = LastError;
  if ( *(_QWORD *)pbData )
    CertCloseStore(*(HCERTSTORE *)pbData, 0);
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v6 )
    I_FreeCredListItem(v6);
  if ( p_pdwDataLen )
  {
    v24 = p_pdwDataLen - 2;
    if ( *(p_pdwDataLen - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  WppTraceIndent(v24, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v23);
  }
  return v23;
}

```

## disassembly

```asm
0x18001f9ec  push    rbp
0x18001f9ee  push    rbx
0x18001f9ef  push    rsi
0x18001f9f0  push    rdi
0x18001f9f1  push    r12
0x18001f9f3  push    r13
0x18001f9f5  push    r14
0x18001f9f7  push    r15
0x18001f9f9  sub     rsp, 68h
0x18001f9fd  lea     rbp, [rsp+30h]
0x18001fa02  mov     rax, cs:__security_cookie
0x18001fa09  xor     rax, rbp
0x18001fa0c  mov     [rbp+70h+var_48], rax
0x18001fa10  xor     esi, esi
0x18001fa12  mov     [rbp+70h+var_58], r8
0x18001fa16  mov     r14, rdx
0x18001fa19  mov     qword ptr [rbp+70h+pbData], rsi
0x18001fa1d  xor     edx, edx
0x18001fa1f  mov     [rbp+70h+pdwDataLen], esi
0x18001fa22  mov     r15d, esi
0x18001fa25  mov     [rbp+70h+var_60], rsi
0x18001fa29  mov     ebx, esi
0x18001fa2b  mov     r12d, esi
0x18001fa2e  mov     rdi, r8
0x18001fa31  mov     r13, rcx
0x18001fa34  call    WppTraceIndent
0x18001fa39  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa40  lea     rax, WPP_GLOBAL_Control
0x18001fa47  cmp     rcx, rax
0x18001fa4a  jz      short loc_18001FA72
0x18001fa4c  test    byte ptr [rcx+1Ch], 2
0x18001fa50  jz      short loc_18001FA72
0x18001fa52  cmp     byte ptr [rcx+19h], 5
0x18001fa56  jb      short loc_18001FA72
0x18001fa58  mov     r9, cs:WPP_pszIndent
0x18001fa5f  lea     edx, [rsi+63h]
0x18001fa62  mov     rcx, [rcx+10h]
0x18001fa66  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001fa6d  call    WPP_SF_s
0x18001fa72  mov     rcx, [r14+80h]; hProv
0x18001fa79  lea     r9, [rbp+70h+pdwDataLen]; pdwDataLen
0x18001fa7d  mov     [rdi], esi
0x18001fa7f  lea     r8, [rbp+70h+pbData]; pbData
0x18001fa83  mov     esi, 8
0x18001fa88  mov     [rsp+0A0h+dwFlags], ebx; dwFlags
0x18001fa8c  mov     [rbp+70h+pdwDataLen], esi
0x18001fa8f  lea     edx, [rsi+22h]; dwParam
0x18001fa92  call    cs:__imp_CryptGetProvParam
0x18001fa98  cmp     eax, 1
0x18001fa9b  jz      short loc_18001FAFF
0x18001fa9d  call    cs:__imp_GetLastError
0x18001faa3  mov     edx, 2
0x18001faa8  mov     esi, eax
0x18001faaa  call    WppTraceIndent
0x18001faaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fab6  lea     r14, WPP_GLOBAL_Control
0x18001fabd  cmp     rcx, r14
0x18001fac0  jz      loc_18001FD41
0x18001fac6  test    byte ptr [rcx+1Ch], 1
0x18001faca  jz      loc_18001FD41
0x18001fad0  cmp     byte ptr [rcx+19h], 2
0x18001fad4  jb      loc_18001FD41
0x18001fada  mov     edx, 64h ; 'd'
0x18001fadf  mov     r9, cs:WPP_pszIndent
0x18001fae6  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001faed  mov     rcx, [rcx+10h]
0x18001faf1  mov     [rsp+0A0h+dwFlags], esi
0x18001faf5  call    WPP_SF_sD
0x18001fafa  jmp     loc_18001FD41
0x18001faff  mov     rcx, qword ptr [rbp+70h+pbData]; hCertStore
0x18001fb03  mov     rdx, r15; pPrevCertContext
0x18001fb06  call    cs:__imp_CertEnumCertificatesInStore
0x18001fb0c  mov     r15, rax
0x18001fb0f  test    rax, rax
0x18001fb12  jz      loc_18001FD1E
0x18001fb18  xor     r8d, r8d; pvData
0x18001fb1b  lea     r9, [rbp+70h+pdwDataLen]; pcbData
0x18001fb1f  mov     rcx, rax; pCertContext
0x18001fb22  lea     edx, [r8+2]; dwPropId
0x18001fb26  call    cs:__imp_CertGetCertificateContextProperty
0x18001fb2c  cmp     eax, 1
0x18001fb2f  jnz     loc_18001FCE3
0x18001fb35  test    rbx, rbx
0x18001fb38  jz      short loc_18001FB52
0x18001fb3a  lea     rcx, [rbx-8]
0x18001fb3e  cmp     dword ptr [rcx], 70616548h
0x18001fb44  jnz     short loc_18001FB52
0x18001fb46  mov     rax, cs:g_pfnFree
0x18001fb4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb52  mov     edi, [rbp+70h+pdwDataLen]
0x18001fb55  xor     ebx, ebx
0x18001fb57  test    rdi, rdi
0x18001fb5a  jz      short loc_18001FBBB
0x18001fb5c  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001fb63  ja      short loc_18001FBBB
0x18001fb65  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001fb6c  add     rcx, rsi
0x18001fb6f  add     rcx, rdi
0x18001fb72  cmp     rcx, rdi
0x18001fb75  jb      short loc_18001FBBB
0x18001fb77  call    VerifyStackAvailable
0x18001fb7c  test    eax, eax
0x18001fb7e  jz      short loc_18001FBBB
0x18001fb80  lea     rax, [rdi+8]
0x18001fb84  lea     rcx, [rax+0Fh]
0x18001fb88  cmp     rcx, rax
0x18001fb8b  ja      short loc_18001FB97
0x18001fb8d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001fb97  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001fb9b  mov     rax, rcx
0x18001fb9e  call    _alloca_probe
0x18001fba3  sub     rsp, rcx
0x18001fba6  lea     rbx, [rsp+0A0h+pdwDataLen]
0x18001fbab  test    rbx, rbx
0x18001fbae  jz      short loc_18001FBBB
0x18001fbb0  mov     dword ptr [rbx], 6B637453h
0x18001fbb6  add     rbx, rsi
0x18001fbb9  jnz     short loc_18001FBE1
0x18001fbbb  lea     rcx, [rdi+8]
0x18001fbbf  cmp     rcx, rdi
0x18001fbc2  jb      short loc_18001FBE1
0x18001fbc4  mov     rax, cs:g_pfnAllocate
0x18001fbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd0  mov     rbx, rax
0x18001fbd3  test    rax, rax
0x18001fbd6  jz      short loc_18001FBE1
0x18001fbd8  mov     dword ptr [rax], 70616548h
0x18001fbde  add     rbx, rsi
0x18001fbe1  mov     edx, 2; dwPropId
0x18001fbe6  test    rbx, rbx
0x18001fbe9  jz      loc_18001FC99
0x18001fbef  lea     r9, [rbp+70h+pdwDataLen]; pcbData
0x18001fbf3  mov     r8, rbx; pvData
0x18001fbf6  mov     rcx, r15; pCertContext
0x18001fbf9  call    cs:__imp_CertGetCertificateContextProperty
0x18001fbff  cmp     eax, 1
0x18001fc02  jnz     short loc_18001FC52
0x18001fc04  mov     r9d, [rbx+28h]
0x18001fc08  lea     rax, [rbp+70h+var_60]
0x18001fc0c  mov     r8, [rbx]
0x18001fc0f  mov     rdx, r15
0x18001fc12  mov     rcx, r13
0x18001fc15  mov     qword ptr [rsp+0A0h+dwFlags], rax
0x18001fc1a  call    I_ReaderListBuildCredFromCertContext
0x18001fc1f  test    eax, eax
0x18001fc21  jz      short loc_18001FC2C
0x18001fc23  mov     r12, [rbp+70h+var_60]
0x18001fc27  jmp     loc_18001FAFF
0x18001fc2c  mov     rdx, [r14+60h]
0x18001fc30  lea     r8, [r14+0E8h]
0x18001fc37  mov     rcx, [rbp+70h+var_60]
0x18001fc3b  call    I_ReaderListAddCredToList
0x18001fc40  mov     rdi, [rbp+70h+var_58]
0x18001fc44  inc     dword ptr [rdi]
0x18001fc46  xor     r12d, r12d
0x18001fc49  mov     [rbp+70h+var_60], r12
0x18001fc4d  jmp     loc_18001FAFF
0x18001fc52  call    cs:__imp_GetLastError
0x18001fc58  mov     edx, 2
0x18001fc5d  mov     esi, eax
0x18001fc5f  call    WppTraceIndent
0x18001fc64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc6b  lea     r14, WPP_GLOBAL_Control
0x18001fc72  cmp     rcx, r14
0x18001fc75  jz      loc_18001FD41
0x18001fc7b  test    byte ptr [rcx+1Ch], 1
0x18001fc7f  jz      loc_18001FD41
0x18001fc85  cmp     byte ptr [rcx+19h], 2
0x18001fc89  jb      loc_18001FD41
0x18001fc8f  mov     edx, 67h ; 'g'
0x18001fc94  jmp     loc_18001FADF
0x18001fc99  call    WppTraceIndent
0x18001fc9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fca5  lea     r14, WPP_GLOBAL_Control
0x18001fcac  cmp     rcx, r14
0x18001fcaf  jz      loc_18001FD41
0x18001fcb5  test    byte ptr [rcx+1Ch], 1
0x18001fcb9  jz      loc_18001FD41
0x18001fcbf  cmp     byte ptr [rcx+19h], 2
0x18001fcc3  jb      short loc_18001FD41
0x18001fcc5  mov     r9, cs:WPP_pszIndent
0x18001fccc  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001fcd3  mov     rcx, [rcx+10h]
0x18001fcd7  mov     edx, 66h ; 'f'
0x18001fcdc  call    WPP_SF_s
0x18001fce1  jmp     short loc_18001FD41
0x18001fce3  call    cs:__imp_GetLastError
0x18001fce9  mov     edx, 2
0x18001fcee  mov     esi, eax
0x18001fcf0  call    WppTraceIndent
0x18001fcf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcfc  lea     r14, WPP_GLOBAL_Control
0x18001fd03  cmp     rcx, r14
0x18001fd06  jz      short loc_18001FD41
0x18001fd08  test    byte ptr [rcx+1Ch], 1
0x18001fd0c  jz      short loc_18001FD41
0x18001fd0e  cmp     byte ptr [rcx+19h], 2
0x18001fd12  jb      short loc_18001FD41
0x18001fd14  mov     edx, 65h ; 'e'
0x18001fd19  jmp     loc_18001FADF
0x18001fd1e  mov     rax, qword ptr [rbp+70h+pbData]
0x18001fd22  xor     esi, esi
0x18001fd24  mov     [r14+0A8h], rax
0x18001fd2b  mov     dword ptr [r14+94h], 1
0x18001fd36  lea     r14, WPP_GLOBAL_Control
0x18001fd3d  mov     qword ptr [rbp+70h+pbData], rsi
0x18001fd41  mov     rax, [rbp+70h+var_58]
0x18001fd45  xor     edi, edi
0x18001fd47  mov     rcx, qword ptr [rbp+70h+pbData]; hCertStore
0x18001fd4b  cmp     [rax], edi
0x18001fd4d  cmovbe  edi, esi
0x18001fd50  test    rcx, rcx
0x18001fd53  jz      short loc_18001FD5D
0x18001fd55  xor     edx, edx; dwFlags
0x18001fd57  call    cs:__imp_CertCloseStore
0x18001fd5d  test    r15, r15
0x18001fd60  jz      short loc_18001FD6B
0x18001fd62  mov     rcx, r15; pCertContext
0x18001fd65  call    cs:__imp_CertFreeCertificateContext
0x18001fd6b  test    r12, r12
0x18001fd6e  jz      short loc_18001FD78
0x18001fd70  mov     rcx, r12; lpMem
0x18001fd73  call    I_FreeCredListItem
0x18001fd78  test    rbx, rbx
0x18001fd7b  jz      short loc_18001FD95
0x18001fd7d  lea     rcx, [rbx-8]
0x18001fd81  cmp     dword ptr [rcx], 70616548h
0x18001fd87  jnz     short loc_18001FD95
0x18001fd89  mov     rax, cs:g_pfnFree
0x18001fd90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd95  mov     edx, 1
0x18001fd9a  call    WppTraceIndent
0x18001fd9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fda6  cmp     rcx, r14
0x18001fda9  jz      short loc_18001FDD7
0x18001fdab  test    byte ptr [rcx+1Ch], 2
0x18001fdaf  jz      short loc_18001FDD7
0x18001fdb1  cmp     byte ptr [rcx+19h], 5
0x18001fdb5  jb      short loc_18001FDD7
0x18001fdb7  mov     r9, cs:WPP_pszIndent
0x18001fdbe  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001fdc5  mov     rcx, [rcx+10h]
0x18001fdc9  mov     edx, 68h ; 'h'
0x18001fdce  mov     [rsp+0A0h+dwFlags], edi
0x18001fdd2  call    WPP_SF_sD
0x18001fdd7  mov     eax, edi
0x18001fdd9  mov     rcx, [rbp+70h+var_48]
0x18001fddd  xor     rcx, rbp; StackCookie
0x18001fde0  call    __security_check_cookie
0x18001fde5  lea     rsp, [rbp+38h]
0x18001fde9  pop     r15
0x18001fdeb  pop     r14
0x18001fded  pop     r13
0x18001fdef  pop     r12
0x18001fdf1  pop     rdi
0x18001fdf2  pop     rsi
0x18001fdf3  pop     rbx
0x18001fdf4  pop     rbp
0x18001fdf5  retn
```
