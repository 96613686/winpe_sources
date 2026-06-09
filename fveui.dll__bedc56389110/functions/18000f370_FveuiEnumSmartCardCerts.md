# FveuiEnumSmartCardCerts

- ea: `0x18000f370`
- end: `0x18000f76b`
- name: `FveuiEnumSmartCardCerts`
- size: `1019`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005850`
- `0x180007e20`

## callees

- `0x18000ee54`
- `0x18000f370`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f468`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f4fb`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f468`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f4fb`
- `KERNEL32!HeapFree` at `0x18000f707`
- `KERNEL32!HeapFree` at `0x18000f707`
- `KERNEL32!HeapAlloc` at `0x18000f49a`
- `KERNEL32!HeapAlloc` at `0x18000f49a`
- `KERNEL32!GetProcessHeap` at `0x18000f489`
- `KERNEL32!GetProcessHeap` at `0x18000f6f9`
- `KERNEL32!GetProcessHeap` at `0x18000f489`
- `KERNEL32!GetProcessHeap` at `0x18000f6f9`
- `KERNEL32!GetLastError` at `0x18000f3e8`
- `KERNEL32!GetLastError` at `0x18000f602`
- `KERNEL32!GetLastError` at `0x18000f3e8`
- `KERNEL32!GetLastError` at `0x18000f602`
- `FVECERTS!FveCertFilterForValidCertificates` at `0x18000f633`
- `FVECERTS!FveCertFilterForValidCertificates` at `0x18000f633`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f5dd`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f5dd`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f6d0`
- `CRYPT32!CertFreeCertificateContext` at `0x18000f6d0`
- `CRYPT32!CertOpenStore` at `0x18000f3d6`
- `CRYPT32!CertOpenStore` at `0x18000f3d6`
- `CRYPT32!CertAddCertificateLinkToStore` at `0x18000f5f8`
- `CRYPT32!CertAddCertificateLinkToStore` at `0x18000f5f8`
- `CRYPT32!CertCloseStore` at `0x18000f671`
- `CRYPT32!CertCloseStore` at `0x18000f72e`
- `CRYPT32!CertCloseStore` at `0x18000f73f`
- `CRYPT32!CertCloseStore` at `0x18000f671`
- `CRYPT32!CertCloseStore` at `0x18000f72e`
- `CRYPT32!CertCloseStore` at `0x18000f73f`
- `WinSCard!SCardFreeMemory` at `0x18000f5b6`
- `WinSCard!SCardFreeMemory` at `0x18000f654`
- `WinSCard!SCardFreeMemory` at `0x18000f6ea`
- `WinSCard!SCardFreeMemory` at `0x18000f71a`
- `WinSCard!SCardFreeMemory` at `0x18000f5b6`
- `WinSCard!SCardFreeMemory` at `0x18000f654`
- `WinSCard!SCardFreeMemory` at `0x18000f6ea`
- `WinSCard!SCardFreeMemory` at `0x18000f71a`
- `WinSCard!SCardListCardsW` at `0x18000f579`
- `WinSCard!SCardListCardsW` at `0x18000f579`
- `WinSCard!SCardGetStatusChangeW` at `0x18000f516`
- `WinSCard!SCardGetStatusChangeW` at `0x18000f516`
- `WinSCard!SCardListReadersW` at `0x18000f42b`
- `WinSCard!SCardListReadersW` at `0x18000f42b`
- `WinSCard!SCardReleaseContext` at `0x18000f752`
- `WinSCard!SCardReleaseContext` at `0x18000f752`
- `WinSCard!SCardEstablishContext` at `0x18000f411`
- `WinSCard!SCardEstablishContext` at `0x18000f411`

## pseudocode

```c
__int64 __fastcall FveuiEnumSmartCardCerts(int a1, _QWORD *a2, _DWORD *a3)
{
  DWORD v3; // r13d
  signed int valid; // ebx
  struct $B80B7D01E79FADDB4AAC58DE22BC823F *v5; // r12
  HCERTSTORE v6; // r14
  signed int LastError; // eax
  bool v8; // cc
  DWORD v9; // edx
  DWORD v10; // r15d
  DWORD v11; // ebx
  const wchar_t *v12; // rcx
  int v13; // eax
  HANDLE ProcessHeap; // rax
  DWORD v15; // edi
  DWORD i; // ebx
  const WCHAR *v17; // rdx
  __int64 v18; // rax
  const wchar_t *v19; // rcx
  int v20; // eax
  const CERT_CONTEXT *v21; // rdi
  int v22; // esi
  unsigned __int64 v23; // r14
  LONG v24; // eax
  const CERT_CONTEXT *v25; // rax
  signed int v26; // eax
  HANDLE v27; // rax
  int v29; // [rsp+30h] [rbp-48h]
  DWORD pcchCards; // [rsp+34h] [rbp-44h] BYREF
  int v31; // [rsp+38h] [rbp-40h] BYREF
  SCARDCONTEXT phContext; // [rsp+40h] [rbp-38h] BYREF
  WCHAR mszCards[4]; // [rsp+48h] [rbp-30h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-28h] BYREF
  HCERTSTORE v35; // [rsp+58h] [rbp-20h]
  WCHAR mszReaders[4]; // [rsp+60h] [rbp-18h] BYREF
  DWORD pcchReaders; // [rsp+D8h] [rbp+60h] BYREF

  v3 = 0;
  phContext = 0;
  *(_QWORD *)mszReaders = 0;
  pcchReaders = -1;
  v31 = 0;
  hCertStore = 0;
  *(_QWORD *)mszCards = 0;
  pcchCards = -1;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = 0;
  v35 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, 0);
  v6 = v35;
  if ( !v35 )
  {
    LastError = GetLastError();
    valid = LastError;
    v8 = LastError <= 0;
    goto LABEL_5;
  }
  LastError = SCardEstablishContext(0, 0, 0, &phContext);
  valid = LastError;
  v8 = LastError <= 0;
  if ( LastError )
    goto LABEL_5;
  LastError = SCardListReadersW(phContext, 0, mszReaders, &pcchReaders);
  valid = LastError;
  if ( LastError == -2146435026 )
  {
LABEL_56:
    valid = -2146435060;
    goto LABEL_57;
  }
  v8 = LastError <= 0;
  if ( LastError )
  {
LABEL_5:
    if ( !v8 )
      valid = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_57;
  }
  v9 = pcchReaders;
  v10 = 0;
  v11 = 0;
  if ( !pcchReaders )
    goto LABEL_56;
  do
  {
    v12 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * v11);
    if ( !*v12 )
      break;
    ++v10;
    v13 = wcsnlen(v12, v9 - v11);
    v9 = pcchReaders;
    v11 += v13 + 1;
  }
  while ( v11 < pcchReaders );
  if ( !v10 )
    goto LABEL_56;
  ProcessHeap = GetProcessHeap();
  v5 = (struct $B80B7D01E79FADDB4AAC58DE22BC823F *)HeapAlloc(ProcessHeap, 8u, (unsigned __int64)v10 << 6);
  if ( !v5 )
  {
    valid = -2147024882;
    goto LABEL_57;
  }
  v15 = 0;
  for ( i = 0; i < pcchReaders; i += v20 + 1 )
  {
    v17 = (const WCHAR *)(*(_QWORD *)mszReaders + 2LL * i);
    if ( !*v17 || v15 >= v10 )
      break;
    v18 = v15++;
    v18 <<= 6;
    *(LPCWSTR *)((char *)&v5->szReader + v18) = v17;
    *(DWORD *)((char *)&v5->dwCurrentState + v18) = 0;
    v19 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * i);
    v20 = v19 ? wcsnlen(v19, pcchReaders - i) : 0;
  }
  LastError = SCardGetStatusChangeW(phContext, 0, v5, v10);
  valid = LastError;
  v8 = LastError <= 0;
  if ( LastError )
    goto LABEL_5;
  v21 = 0;
  v29 = 0;
  valid = 0;
  v22 = 0;
  while ( v3 < v10 )
  {
    v23 = (unsigned __int64)v3 << 6;
    if ( (*(DWORD *)((_BYTE *)&v5->dwEventState + v23) & 0xA0) != 0x20 )
      goto LABEL_31;
    pcchCards = -1;
    v24 = SCardListCardsW(phContext, &v5->rgbAtr[v23], 0, 0, mszCards, &pcchCards);
    valid = v24;
    if ( v24 )
    {
      if ( v24 > 0 )
        valid = (unsigned __int16)v24 | 0x80070000;
      v6 = v35;
      goto LABEL_57;
    }
    ++v29;
    valid = FveuiAcquireSmartCardCertStore(
              phContext,
              *(PBYTE *)((char *)&v5->szReader + v23),
              *(LPCWSTR *)mszCards,
              &hCertStore);
    if ( valid < 0 )
    {
      valid = 0;
      if ( *(_QWORD *)mszCards )
      {
        SCardFreeMemory(phContext, *(LPCVOID *)mszCards);
        *(_QWORD *)mszCards = 0;
      }
LABEL_31:
      v6 = v35;
      goto LABEL_32;
    }
    v6 = v35;
    if ( a1 )
    {
      while ( 1 )
      {
        v25 = CertEnumCertificatesInStore(hCertStore, v21);
        v21 = v25;
        if ( !v25 )
          break;
        if ( !CertAddCertificateLinkToStore(v6, v25, 2u, 0) )
        {
          v26 = GetLastError();
          valid = v26;
          if ( v26 > 0 )
            valid = (unsigned __int16)v26 | 0x80070000;
          goto LABEL_55;
        }
      }
    }
    else
    {
      valid = FveCertFilterForValidCertificates(16, hCertStore, v35, &v31);
      if ( valid < 0 )
        goto LABEL_57;
      if ( !v31 )
        goto LABEL_41;
    }
    ++v22;
LABEL_41:
    if ( *(_QWORD *)mszCards )
    {
      SCardFreeMemory(phContext, *(LPCVOID *)mszCards);
      *(_QWORD *)mszCards = 0;
    }
    if ( hCertStore )
    {
      CertCloseStore(hCertStore, 0);
      hCertStore = 0;
    }
LABEL_32:
    ++v3;
  }
  if ( !v29 )
    goto LABEL_56;
  if ( v22 )
  {
    if ( a3 )
      *a3 = v22;
    *a2 = v6;
    v6 = 0;
    if ( v21 )
LABEL_55:
      CertFreeCertificateContext(v21);
  }
  else
  {
    valid = -2146885628;
  }
LABEL_57:
  if ( *(_QWORD *)mszCards )
  {
    SCardFreeMemory(phContext, *(LPCVOID *)mszCards);
    *(_QWORD *)mszCards = 0;
  }
  if ( v5 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v5);
  }
  if ( *(_QWORD *)mszReaders )
  {
    SCardFreeMemory(phContext, *(LPCVOID *)mszReaders);
    *(_QWORD *)mszReaders = 0;
  }
  if ( v6 )
    CertCloseStore(v6, 0);
  if ( hCertStore )
  {
    CertCloseStore(hCertStore, 0);
    hCertStore = 0;
  }
  if ( phContext )
    SCardReleaseContext(phContext);
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18000f370  mov     [rsp-40h+arg_10], r8
0x18000f375  mov     [rsp-40h+arg_8], rdx
0x18000f37a  mov     [rsp-40h+arg_0], ecx
0x18000f37e  push    rbp
0x18000f37f  push    rbx
0x18000f380  push    rsi
0x18000f381  push    rdi
0x18000f382  push    r12
0x18000f384  push    r13
0x18000f386  push    r14
0x18000f388  push    r15
0x18000f38a  mov     rbp, rsp
0x18000f38d  sub     rsp, 78h
0x18000f391  xor     r13d, r13d
0x18000f394  or      ecx, 0FFFFFFFFh
0x18000f397  mov     [rbp+phContext], r13
0x18000f39b  mov     qword ptr [rbp+mszReaders], r13
0x18000f39f  mov     [rbp+pcchReaders], ecx
0x18000f3a2  mov     [rbp+var_40], r13d
0x18000f3a6  mov     [rbp+hCertStore], r13
0x18000f3aa  mov     qword ptr [rbp+mszCards], r13
0x18000f3ae  mov     [rbp+var_44], ecx
0x18000f3b1  test    rdx, rdx
0x18000f3b4  jnz     short loc_18000F3C0
0x18000f3b6  mov     ebx, 80070057h
0x18000f3bb  jmp     loc_18000F758
0x18000f3c0  xor     edx, edx; dwEncodingType
0x18000f3c2  mov     [rsp+78h+pvPara], r13; pvPara
0x18000f3c7  mov     r9d, 2000h; dwFlags
0x18000f3cd  xor     r8d, r8d; hCryptProv
0x18000f3d0  mov     r12, r13
0x18000f3d3  lea     ecx, [rdx+2]; lpszStoreProvider
0x18000f3d6  call    cs:__imp_CertOpenStore
0x18000f3dc  mov     [rbp+var_20], rax
0x18000f3e0  mov     r14, rax
0x18000f3e3  test    rax, rax
0x18000f3e6  jnz     short loc_18000F406
0x18000f3e8  call    cs:__imp_GetLastError
0x18000f3ee  mov     ebx, eax
0x18000f3f0  test    eax, eax
0x18000f3f2  jle     loc_18000F6DD
0x18000f3f8  movzx   ebx, ax
0x18000f3fb  or      ebx, 80070000h
0x18000f401  jmp     loc_18000F6DD
0x18000f406  lea     r9, [rbp+phContext]; phContext
0x18000f40a  xor     r8d, r8d; pvReserved2
0x18000f40d  xor     edx, edx; pvReserved1
0x18000f40f  xor     ecx, ecx; dwScope
0x18000f411  call    cs:__imp_SCardEstablishContext
0x18000f417  mov     ebx, eax
0x18000f419  test    eax, eax
0x18000f41b  jnz     short loc_18000F3F2
0x18000f41d  mov     rcx, [rbp+phContext]; hContext
0x18000f421  lea     r9, [rbp+pcchReaders]; pcchReaders
0x18000f425  lea     r8, [rbp+mszReaders]; mszReaders
0x18000f429  xor     edx, edx; mszGroups
0x18000f42b  call    cs:__imp_SCardListReadersW
0x18000f431  mov     ebx, eax
0x18000f433  cmp     eax, 8010002Eh
0x18000f438  jz      loc_18000F6D8
0x18000f43e  test    eax, eax
0x18000f440  jnz     short loc_18000F3F2
0x18000f442  mov     edx, [rbp+pcchReaders]
0x18000f445  mov     r15d, r13d
0x18000f448  mov     ebx, r13d
0x18000f44b  test    edx, edx
0x18000f44d  jz      loc_18000F6D8
0x18000f453  mov     rax, qword ptr [rbp+mszReaders]
0x18000f457  mov     ecx, ebx
0x18000f459  lea     rcx, [rax+rcx*2]; Source
0x18000f45d  cmp     r13w, [rcx]
0x18000f461  jz      short loc_18000F479
0x18000f463  sub     edx, ebx; MaxCount
0x18000f465  inc     r15d
0x18000f468  call    cs:__imp_wcsnlen
0x18000f46e  mov     edx, [rbp+pcchReaders]
0x18000f471  inc     ebx
0x18000f473  add     ebx, eax
0x18000f475  cmp     ebx, edx
0x18000f477  jb      short loc_18000F453
0x18000f479  test    r15d, r15d
0x18000f47c  jz      loc_18000F6D8
0x18000f482  mov     ebx, r15d
0x18000f485  shl     rbx, 6
0x18000f489  call    cs:__imp_GetProcessHeap
0x18000f48f  mov     r8, rbx; dwBytes
0x18000f492  mov     edx, 8; dwFlags
0x18000f497  mov     rcx, rax; hHeap
0x18000f49a  call    cs:__imp_HeapAlloc
0x18000f4a0  mov     r12, rax
0x18000f4a3  test    rax, rax
0x18000f4a6  jnz     short loc_18000F4B2
0x18000f4a8  mov     ebx, 8007000Eh
0x18000f4ad  jmp     loc_18000F6DD
0x18000f4b2  mov     edi, r13d
0x18000f4b5  mov     ebx, r13d
0x18000f4b8  cmp     [rbp+pcchReaders], r13d
0x18000f4bc  jbe     short loc_18000F50A
0x18000f4be  mov     rax, qword ptr [rbp+mszReaders]
0x18000f4c2  mov     ecx, ebx
0x18000f4c4  lea     rdx, [rax+rcx*2]
0x18000f4c8  cmp     r13w, [rdx]
0x18000f4cc  jz      short loc_18000F50A
0x18000f4ce  cmp     edi, r15d
0x18000f4d1  jnb     short loc_18000F50A
0x18000f4d3  mov     eax, edi
0x18000f4d5  inc     edi
0x18000f4d7  shl     rax, 6
0x18000f4db  mov     [rax+r12], rdx
0x18000f4df  mov     [rax+r12+10h], r13d
0x18000f4e4  mov     rax, qword ptr [rbp+mszReaders]
0x18000f4e8  lea     rcx, [rax+rcx*2]; Source
0x18000f4ec  test    rcx, rcx
0x18000f4ef  jnz     short loc_18000F4F6
0x18000f4f1  mov     rax, r13
0x18000f4f4  jmp     short loc_18000F501
0x18000f4f6  mov     edx, [rbp+pcchReaders]
0x18000f4f9  sub     edx, ebx; MaxCount
0x18000f4fb  call    cs:__imp_wcsnlen
0x18000f501  inc     ebx
0x18000f503  add     ebx, eax
0x18000f505  cmp     ebx, [rbp+pcchReaders]
0x18000f508  jb      short loc_18000F4BE
0x18000f50a  mov     rcx, [rbp+phContext]; hContext
0x18000f50e  mov     r9d, r15d; cReaders
0x18000f511  mov     r8, r12; rgReaderStates
0x18000f514  xor     edx, edx; dwTimeout
0x18000f516  call    cs:__imp_SCardGetStatusChangeW
0x18000f51c  mov     ebx, eax
0x18000f51e  test    eax, eax
0x18000f520  jnz     loc_18000F3F2
0x18000f526  mov     rdi, r13
0x18000f529  mov     [rbp+var_48], r13d
0x18000f52d  mov     ebx, r13d
0x18000f530  mov     esi, r13d
0x18000f533  cmp     r13d, r15d
0x18000f536  jnb     loc_18000F69F
0x18000f53c  mov     r14d, r13d
0x18000f53f  shl     r14, 6
0x18000f543  mov     eax, [r14+r12+14h]
0x18000f548  and     al, 0A0h
0x18000f54a  cmp     al, 20h ; ' '
0x18000f54c  jnz     short loc_18000F5C0
0x18000f54e  mov     rcx, [rbp+phContext]; hContext
0x18000f552  lea     rax, [rbp+var_44]
0x18000f556  mov     [rsp+78h+pcchCards], rax; pcchCards
0x18000f55b  lea     rdx, [r12+1Ch]
0x18000f560  lea     rax, [rbp+mszCards]
0x18000f564  mov     [rbp+var_44], 0FFFFFFFFh
0x18000f56b  add     rdx, r14; pbAtr
0x18000f56e  mov     [rsp+78h+pvPara], rax; mszCards
0x18000f573  xor     r9d, r9d; cguidInterfaceCount
0x18000f576  xor     r8d, r8d; rgquidInterfaces
0x18000f579  call    cs:__imp_SCardListCardsW
0x18000f57f  mov     ebx, eax
0x18000f581  test    eax, eax
0x18000f583  jnz     loc_18000F689
0x18000f589  mov     r8, qword ptr [rbp+mszCards]; szCardName
0x18000f58d  lea     r9, [rbp+hCertStore]; void **
0x18000f591  mov     rdx, [r14+r12]; pbInput
0x18000f595  mov     rcx, [rbp+phContext]; hContext
0x18000f599  inc     [rbp+var_48]
0x18000f59c  call    ?FveuiAcquireSmartCardCertStore@@YAJ_KPEBG1PEAPEAX@Z; FveuiAcquireSmartCardCertStore(unsigned __int64,ushort const *,ushort const *,void * *)
0x18000f5a1  mov     ebx, eax
0x18000f5a3  test    eax, eax
0x18000f5a5  jns     short loc_18000F5CC
0x18000f5a7  mov     rdx, qword ptr [rbp+mszCards]; pvMem
0x18000f5ab  xor     ebx, ebx
0x18000f5ad  test    rdx, rdx
0x18000f5b0  jz      short loc_18000F5C0
0x18000f5b2  mov     rcx, [rbp+phContext]; hContext
0x18000f5b6  call    cs:__imp_SCardFreeMemory
0x18000f5bc  mov     qword ptr [rbp+mszCards], rbx
0x18000f5c0  mov     r14, [rbp+var_20]
0x18000f5c4  inc     r13d
0x18000f5c7  jmp     loc_18000F533
0x18000f5cc  cmp     [rbp+arg_0], 0
0x18000f5d0  mov     r14, [rbp+var_20]
0x18000f5d4  jz      short loc_18000F623
0x18000f5d6  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000f5da  mov     rdx, rdi; pPrevCertContext
0x18000f5dd  call    cs:__imp_CertEnumCertificatesInStore
0x18000f5e3  mov     rdi, rax
0x18000f5e6  test    rax, rax
0x18000f5e9  jz      short loc_18000F645
0x18000f5eb  xor     r9d, r9d; ppStoreContext
0x18000f5ee  mov     rdx, rax; pCertContext
0x18000f5f1  mov     rcx, r14; hCertStore
0x18000f5f4  lea     r8d, [r9+2]; dwAddDisposition
0x18000f5f8  call    cs:__imp_CertAddCertificateLinkToStore
0x18000f5fe  test    eax, eax
0x18000f600  jnz     short loc_18000F5D6
0x18000f602  call    cs:__imp_GetLastError
0x18000f608  xor     r13d, r13d
0x18000f60b  mov     ebx, eax
0x18000f60d  test    eax, eax
0x18000f60f  jle     loc_18000F6CD
0x18000f615  movzx   ebx, ax
0x18000f618  or      ebx, 80070000h
0x18000f61e  jmp     loc_18000F6CD
0x18000f623  mov     rdx, [rbp+hCertStore]
0x18000f627  lea     r9, [rbp+var_40]
0x18000f62b  mov     r8, r14
0x18000f62e  mov     ecx, 10h
0x18000f633  call    cs:__imp_FveCertFilterForValidCertificates
0x18000f639  mov     ebx, eax
0x18000f63b  test    eax, eax
0x18000f63d  js      short loc_18000F684
0x18000f63f  cmp     [rbp+var_40], 0
0x18000f643  jbe     short loc_18000F647
0x18000f645  inc     esi
0x18000f647  mov     rdx, qword ptr [rbp+mszCards]; pvMem
0x18000f64b  test    rdx, rdx
0x18000f64e  jz      short loc_18000F662
0x18000f650  mov     rcx, [rbp+phContext]; hContext
0x18000f654  call    cs:__imp_SCardFreeMemory
0x18000f65a  mov     qword ptr [rbp+mszCards], 0
0x18000f662  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000f666  test    rcx, rcx
0x18000f669  jz      loc_18000F5C4
0x18000f66f  xor     edx, edx; dwFlags
0x18000f671  call    cs:__imp_CertCloseStore
0x18000f677  mov     [rbp+hCertStore], 0
0x18000f67f  jmp     loc_18000F5C4
0x18000f684  xor     r13d, r13d
0x18000f687  jmp     short loc_18000F6DD
0x18000f689  xor     r13d, r13d
0x18000f68c  test    eax, eax
0x18000f68e  jle     short loc_18000F699
0x18000f690  movzx   ebx, ax
0x18000f693  or      ebx, 80070000h
0x18000f699  mov     r14, [rbp+var_20]
0x18000f69d  jmp     short loc_18000F6DD
0x18000f69f  xor     r13d, r13d
0x18000f6a2  cmp     [rbp+var_48], r13d
0x18000f6a6  jz      short loc_18000F6D8
0x18000f6a8  test    esi, esi
0x18000f6aa  jnz     short loc_18000F6B3
0x18000f6ac  mov     ebx, 80092004h
0x18000f6b1  jmp     short loc_18000F6DD
0x18000f6b3  mov     rax, [rbp+arg_10]
0x18000f6b7  test    rax, rax
0x18000f6ba  jz      short loc_18000F6BE
0x18000f6bc  mov     [rax], esi
0x18000f6be  mov     rax, [rbp+arg_8]
0x18000f6c2  mov     [rax], r14
0x18000f6c5  mov     r14, r13
0x18000f6c8  test    rdi, rdi
0x18000f6cb  jz      short loc_18000F6DD
0x18000f6cd  mov     rcx, rdi; pCertContext
0x18000f6d0  call    cs:__imp_CertFreeCertificateContext
0x18000f6d6  jmp     short loc_18000F6DD
0x18000f6d8  mov     ebx, 8010000Ch
0x18000f6dd  mov     rdx, qword ptr [rbp+mszCards]; pvMem
0x18000f6e1  test    rdx, rdx
0x18000f6e4  jz      short loc_18000F6F4
0x18000f6e6  mov     rcx, [rbp+phContext]; hContext
0x18000f6ea  call    cs:__imp_SCardFreeMemory
0x18000f6f0  mov     qword ptr [rbp+mszCards], r13
0x18000f6f4  test    r12, r12
0x18000f6f7  jz      short loc_18000F70D
0x18000f6f9  call    cs:__imp_GetProcessHeap
0x18000f6ff  mov     r8, r12; lpMem
0x18000f702  xor     edx, edx; dwFlags
0x18000f704  mov     rcx, rax; hHeap
0x18000f707  call    cs:__imp_HeapFree
0x18000f70d  mov     rdx, qword ptr [rbp+mszReaders]; pvMem
0x18000f711  test    rdx, rdx
0x18000f714  jz      short loc_18000F724
0x18000f716  mov     rcx, [rbp+phContext]; hContext
0x18000f71a  call    cs:__imp_SCardFreeMemory
0x18000f720  mov     qword ptr [rbp+mszReaders], r13
0x18000f724  test    r14, r14
0x18000f727  jz      short loc_18000F734
0x18000f729  xor     edx, edx; dwFlags
0x18000f72b  mov     rcx, r14; hCertStore
0x18000f72e  call    cs:__imp_CertCloseStore
0x18000f734  mov     rcx, [rbp+hCertStore]; hCertStore
0x18000f738  test    rcx, rcx
0x18000f73b  jz      short loc_18000F749
0x18000f73d  xor     edx, edx; dwFlags
0x18000f73f  call    cs:__imp_CertCloseStore
0x18000f745  mov     [rbp+hCertStore], r13
0x18000f749  mov     rcx, [rbp+phContext]; hContext
0x18000f74d  test    rcx, rcx
0x18000f750  jz      short loc_18000F758
0x18000f752  call    cs:__imp_SCardReleaseContext
0x18000f758  mov     eax, ebx
0x18000f75a  add     rsp, 78h
0x18000f75e  pop     r15
0x18000f760  pop     r14
0x18000f762  pop     r13
0x18000f764  pop     r12
0x18000f766  pop     rdi
0x18000f767  pop     rsi
0x18000f768  pop     rbx
0x18000f769  pop     rbp
0x18000f76a  retn
```
