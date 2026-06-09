# FveuiUserSelectSmartCard

- ea: `0x18000f830`
- end: `0x18000fbba`
- name: `FveuiUserSelectSmartCard`
- size: `906`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005850`

## callees

- `0x180001bb0`
- `0x180001bd4`
- `0x180002774`
- `0x18000b978`
- `0x18000ee54`
- `0x18000f830`
- `0x18001114c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000fae5`
- `KERNEL32!GetLastError` at `0x18000fae5`
- `FVECERTS!FveCertFilterForValidCertificates` at `0x18000fb02`
- `FVECERTS!FveCertFilterForValidCertificates` at `0x18000fb02`
- `CRYPT32!CertOpenStore` at `0x18000fad7`
- `CRYPT32!CertOpenStore` at `0x18000fad7`
- `CRYPT32!CertCloseStore` at `0x18000fb3a`
- `CRYPT32!CertCloseStore` at `0x18000fb4c`
- `CRYPT32!CertCloseStore` at `0x18000fb3a`
- `CRYPT32!CertCloseStore` at `0x18000fb4c`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18000f97f`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x18000f97f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb7b`
- `WinSCard!SCardReleaseContext` at `0x18000fb25`
- `WinSCard!SCardReleaseContext` at `0x18000fb25`
- `WinSCard!SCardEstablishContext` at `0x18000fa80`
- `WinSCard!SCardEstablishContext` at `0x18000fa80`

## pseudocode

```c
__int64 __fastcall FveuiUserSelectSmartCard(HWND a1, int a2, HCERTSTORE *a3)
{
  unsigned int v6; // edx
  signed int valid; // ebx
  void *v8; // rdi
  int v9; // eax
  unsigned __int16 *v10; // r14
  signed int LastError; // eax
  bool v12; // cc
  unsigned int *v13; // r11
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // r10
  __int64 v17; // r11
  HCERTSTORE v18; // rax
  _BYTE *v19; // rax
  __int64 v20; // rdx
  ULONG pulOutAuthBufferSize; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp-A8h] BYREF
  SCARDCONTEXT phContext; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-90h] BYREF
  ULONG pulAuthPackage; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 *v28; // [rsp+78h] [rbp-88h] BYREF
  _BYTE pvInAuthBuffer[36]; // [rsp+80h] [rbp-80h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR szCardName; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[526]; // [rsp+D2h] [rbp-2Eh] BYREF
  BYTE pbInput[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v34[526]; // [rsp+2E2h] [rbp+1E2h] BYREF

  phContext = 0;
  *(_WORD *)pbInput = 0;
  memset_0(v34, 0, 0x206u);
  szCardName = 0;
  memset_0(v32, 0, 0x206u);
  hCertStore = 0;
  pulAuthPackage = -629;
  pv = 0;
  pulOutAuthBufferSize = 0;
  v28 = 0;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  memset(pvInAuthBuffer, 0, sizeof(pvInAuthBuffer));
  if ( !a3 )
    return (unsigned int)-2147024809;
  v26 = 0;
  v8 = 0;
  v9 = LoadResourceStringAndLength(fveuig_hInstance, v6, &v28, &v26);
  v10 = v28;
  valid = v9;
  if ( v9 >= 0 )
  {
    pUiInfo.hwndParent = a1;
    *(_QWORD *)&pvInAuthBuffer[4] = 0x300000003LL;
    pUiInfo.cbSize = 40;
    pUiInfo.pszCaptionText = v28;
    memset(&pvInAuthBuffer[12], 0, 24);
    *(_DWORD *)pvInAuthBuffer = 2;
    LastError = CredUIPromptForWindowsCredentialsW(
                  &pUiInfo,
                  0,
                  &pulAuthPackage,
                  pvInAuthBuffer,
                  0x24u,
                  &pv,
                  &pulOutAuthBufferSize,
                  0,
                  0x10u);
    valid = LastError;
    if ( LastError == 1223 )
    {
      valid = -2146434962;
      goto LABEL_27;
    }
    v12 = LastError <= 0;
    if ( !LastError )
    {
      if ( pulOutAuthBufferSize < 0x10
        || (v13 = (unsigned int *)pv, v14 = *((unsigned int *)pv + 1), !(_DWORD)v14)
        || !*((_DWORD *)pv + 3)
        || (v15 = *(unsigned int *)pv, pulOutAuthBufferSize < (unsigned __int64)(v15 + 2 * v14))
        || (v16 = *((unsigned int *)pv + 3), pulOutAuthBufferSize < (unsigned __int64)*((unsigned int *)pv + 2)
                                                                  + 2 * v16)
        || pulOutAuthBufferSize < (unsigned __int64)(2 * (v14 + v16) + 16) )
      {
        valid = -2147024883;
        goto LABEL_27;
      }
      *(_WORD *)((char *)pv + 2 * (unsigned int)(v14 - 1) + v15) = 0;
      *(_WORD *)((char *)v13 + 2 * v13[3] + v13[2] - 2) = 0;
      valid = StringCchCopyW((unsigned __int16 *)pbInput, 0x104u, (const unsigned __int16 *)((char *)v13 + *v13));
      if ( valid < 0 )
        goto LABEL_27;
      valid = StringCchCopyW(&szCardName, 0x104u, (const unsigned __int16 *)(v17 + *(unsigned int *)(v17 + 8)));
      if ( valid < 0 )
        goto LABEL_27;
      LastError = SCardEstablishContext(0, 0, 0, &phContext);
      valid = LastError;
      v12 = LastError <= 0;
      if ( !LastError )
      {
        valid = FveuiAcquireSmartCardCertStore(phContext, pbInput, &szCardName, &hCertStore);
        if ( valid < 0 )
          goto LABEL_27;
        if ( a2 )
        {
          *a3 = hCertStore;
          hCertStore = 0;
          goto LABEL_25;
        }
        v18 = CertOpenStore((LPCSTR)2, 0, 0, 0x2000u, 0);
        v8 = v18;
        if ( v18 )
        {
          valid = FveCertFilterForValidCertificates(16, hCertStore, v18, 0);
          if ( valid < 0 )
            goto LABEL_27;
          *a3 = v8;
LABEL_25:
          v8 = 0;
          goto LABEL_27;
        }
        LastError = GetLastError();
        valid = LastError;
        v12 = LastError <= 0;
      }
    }
    if ( !v12 )
      valid = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_27:
  if ( phContext )
  {
    SCardReleaseContext(phContext);
    phContext = 0;
  }
  if ( v8 )
    CertCloseStore(v8, 0);
  if ( hCertStore )
  {
    CertCloseStore(hCertStore, 0);
    hCertStore = 0;
  }
  v19 = pv;
  if ( pv )
  {
    v20 = pulOutAuthBufferSize;
    if ( pulOutAuthBufferSize )
    {
      do
      {
        *v19++ = 0;
        --v20;
      }
      while ( v20 );
    }
    CoTaskMemFree(pv);
  }
  if ( v10 )
    operator delete(v10);
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18000f830  mov     [rsp-8+arg_8], rbx
0x18000f835  push    rbp
0x18000f836  push    rsi
0x18000f837  push    rdi
0x18000f838  push    r12
0x18000f83a  push    r13
0x18000f83c  push    r14
0x18000f83e  push    r15
0x18000f840  lea     rbp, [rsp-400h]
0x18000f848  sub     rsp, 500h
0x18000f84f  mov     rax, cs:__security_cookie
0x18000f856  xor     rax, rsp
0x18000f859  mov     [rbp+430h+var_40], rax
0x18000f860  mov     rsi, r8
0x18000f863  mov     r12d, edx
0x18000f866  mov     r15, rcx
0x18000f869  xor     r13d, r13d
0x18000f86c  mov     ebx, 206h
0x18000f871  mov     [rsp+530h+phContext], r13
0x18000f876  mov     r8d, ebx; Size
0x18000f879  mov     word ptr [rbp+430h+pbInput], r13w
0x18000f881  xor     edx, edx; Val
0x18000f883  lea     rcx, [rbp+430h+var_24E]; void *
0x18000f88a  call    memset_0
0x18000f88f  mov     r8d, ebx; Size
0x18000f892  mov     [rbp+430h+szCardName], r13w
0x18000f897  xor     edx, edx; Val
0x18000f899  lea     rcx, [rbp+430h+var_45E]; void *
0x18000f89d  call    memset_0
0x18000f8a2  xor     eax, eax
0x18000f8a4  mov     [rsp+530h+hCertStore], r13
0x18000f8a9  mov     [rbp+430h+pUiInfo.hbmBanner], rax
0x18000f8ad  xorps   xmm0, xmm0
0x18000f8b0  mov     [rbp+430h+var_490], eax
0x18000f8b3  xorps   xmm1, xmm1
0x18000f8b6  mov     [rsp+530h+pulAuthPackage], 0FFFFFD8Bh
0x18000f8be  mov     [rsp+530h+pv], r13
0x18000f8c3  mov     [rsp+530h+var_4E0], r13d
0x18000f8c8  mov     [rsp+530h+var_4B8], r13
0x18000f8cd  movups  xmmword ptr [rbp+430h+pUiInfo.cbSize], xmm0
0x18000f8d1  movups  xmmword ptr [rbp+430h+pUiInfo.pszMessageText], xmm0
0x18000f8d5  movups  [rbp+430h+pvInAuthBuffer], xmm1
0x18000f8d9  movups  [rbp+430h+var_4A0], xmm1
0x18000f8dd  test    rsi, rsi
0x18000f8e0  jnz     short loc_18000F8EC
0x18000f8e2  mov     ebx, 80070057h
0x18000f8e7  jmp     loc_18000FB8E
0x18000f8ec  mov     rcx, cs:?fveuig_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18000f8f3  lea     r9, [rsp+530h+var_4C0]; unsigned int *
0x18000f8f8  lea     r8, [rsp+530h+var_4B8]; unsigned __int16 **
0x18000f8fd  mov     [rsp+530h+var_4C0], r13d
0x18000f902  mov     rdi, r13
0x18000f905  call    ?LoadResourceStringAndLength@@YAJPEAUHINSTANCE__@@IPEAPEAGPEAI@Z; LoadResourceStringAndLength(HINSTANCE__ *,uint,ushort * *,uint *)
0x18000f90a  mov     r14, [rsp+530h+var_4B8]
0x18000f90f  mov     ebx, eax
0x18000f911  test    eax, eax
0x18000f913  js      loc_18000FB1B
0x18000f919  mov     eax, 3
0x18000f91e  mov     [rbp+430h+pUiInfo.hwndParent], r15
0x18000f922  mov     dword ptr [rbp+430h+pvInAuthBuffer+8], eax
0x18000f925  lea     r9, [rbp+430h+pvInAuthBuffer]; pvInAuthBuffer
0x18000f929  mov     dword ptr [rbp+430h+pvInAuthBuffer+4], eax
0x18000f92c  lea     r8, [rsp+530h+pulAuthPackage]; pulAuthPackage
0x18000f931  xorps   xmm0, xmm0
0x18000f934  mov     [rbp+430h+pUiInfo.cbSize], 28h ; '('
0x18000f93b  lea     r15d, [rax+0Dh]
0x18000f93f  mov     [rbp+430h+pUiInfo.pszCaptionText], r14
0x18000f943  mov     [rsp+530h+dwFlags], r15d; dwFlags
0x18000f948  lea     rax, [rsp+530h+var_4E0]
0x18000f94d  mov     [rsp+530h+pfSave], r13; pfSave
0x18000f952  lea     rcx, [rbp+430h+pUiInfo]; pUiInfo
0x18000f956  mov     [rsp+530h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x18000f95b  xor     edx, edx; dwAuthError
0x18000f95d  lea     rax, [rsp+530h+pv]
0x18000f962  mov     qword ptr [rbp+430h+var_4A0+0Ch], r13
0x18000f966  mov     [rsp+530h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x18000f96b  mov     [rsp+530h+ulInAuthBufferSize], 24h ; '$'; ulInAuthBufferSize
0x18000f973  movdqu  [rbp+430h+pvInAuthBuffer+0Ch], xmm0
0x18000f978  mov     dword ptr [rbp+430h+pvInAuthBuffer], 2
0x18000f97f  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x18000f985  mov     ebx, eax
0x18000f987  cmp     eax, 4C7h
0x18000f98c  jnz     short loc_18000F998
0x18000f98e  mov     ebx, 8010006Eh
0x18000f993  jmp     loc_18000FB1B
0x18000f998  test    eax, eax
0x18000f99a  jz      short loc_18000F9B0
0x18000f99c  jle     loc_18000FB1B
0x18000f9a2  movzx   ebx, ax
0x18000f9a5  or      ebx, 80070000h
0x18000f9ab  jmp     loc_18000FB1B
0x18000f9b0  cmp     [rsp+530h+var_4E0], r15d
0x18000f9b5  jb      loc_18000FB16
0x18000f9bb  mov     r11, [rsp+530h+pv]
0x18000f9c0  mov     r8d, [r11+4]
0x18000f9c4  test    r8d, r8d
0x18000f9c7  jz      loc_18000FB16
0x18000f9cd  cmp     [r11+0Ch], r13d
0x18000f9d1  jz      loc_18000FB16
0x18000f9d7  mov     ebx, [r11]
0x18000f9da  mov     edx, [rsp+530h+var_4E0]
0x18000f9de  lea     rax, [rbx+r8*2]
0x18000f9e2  cmp     rdx, rax
0x18000f9e5  jb      loc_18000FB16
0x18000f9eb  mov     r10d, [r11+0Ch]
0x18000f9ef  mov     eax, [r11+8]
0x18000f9f3  lea     rcx, [rax+r10*2]
0x18000f9f7  cmp     rdx, rcx
0x18000f9fa  jb      loc_18000FB16
0x18000fa00  lea     rax, [r8+r10]
0x18000fa04  lea     rax, ds:10h[rax*2]
0x18000fa0c  cmp     rdx, rax
0x18000fa0f  jb      loc_18000FB16
0x18000fa15  lea     eax, [r8-1]
0x18000fa19  lea     rdx, [rbx+rax*2]
0x18000fa1d  mov     [rdx+r11], r13w
0x18000fa22  mov     edx, 104h; unsigned __int64
0x18000fa27  mov     eax, [r11+0Ch]
0x18000fa2b  mov     ecx, [r11+8]
0x18000fa2f  dec     eax
0x18000fa31  add     rcx, r11
0x18000fa34  mov     [rcx+rax*2], r13w
0x18000fa39  lea     rcx, [rbp+430h+pbInput]; unsigned __int16 *
0x18000fa40  mov     r8d, [r11]
0x18000fa43  add     r8, r11; unsigned __int16 *
0x18000fa46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa4b  mov     ebx, eax
0x18000fa4d  test    eax, eax
0x18000fa4f  js      loc_18000FB1B
0x18000fa55  mov     r8d, [r11+8]
0x18000fa59  lea     rcx, [rbp+430h+szCardName]; unsigned __int16 *
0x18000fa5d  add     r8, r11; unsigned __int16 *
0x18000fa60  mov     edx, 104h; unsigned __int64
0x18000fa65  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa6a  mov     ebx, eax
0x18000fa6c  test    eax, eax
0x18000fa6e  js      loc_18000FB1B
0x18000fa74  lea     r9, [rsp+530h+phContext]; phContext
0x18000fa79  xor     r8d, r8d; pvReserved2
0x18000fa7c  xor     edx, edx; pvReserved1
0x18000fa7e  xor     ecx, ecx; dwScope
0x18000fa80  call    cs:__imp_SCardEstablishContext
0x18000fa86  mov     ebx, eax
0x18000fa88  test    eax, eax
0x18000fa8a  jnz     loc_18000F99C
0x18000fa90  mov     rcx, [rsp+530h+phContext]; hContext
0x18000fa95  lea     r9, [rsp+530h+hCertStore]; void **
0x18000fa9a  lea     r8, [rbp+430h+szCardName]; szCardName
0x18000fa9e  lea     rdx, [rbp+430h+pbInput]; pbInput
0x18000faa5  call    ?FveuiAcquireSmartCardCertStore@@YAJ_KPEBG1PEAPEAX@Z; FveuiAcquireSmartCardCertStore(unsigned __int64,ushort const *,ushort const *,void * *)
0x18000faaa  mov     ebx, eax
0x18000faac  test    eax, eax
0x18000faae  js      short loc_18000FB1B
0x18000fab0  test    r12d, r12d
0x18000fab3  jz      short loc_18000FAC4
0x18000fab5  mov     rax, [rsp+530h+hCertStore]
0x18000faba  mov     [rsi], rax
0x18000fabd  mov     [rsp+530h+hCertStore], r13
0x18000fac2  jmp     short loc_18000FB11
0x18000fac4  xor     edx, edx; dwEncodingType
0x18000fac6  mov     qword ptr [rsp+530h+ulInAuthBufferSize], r13; pvPara
0x18000facb  mov     r9d, 2000h; dwFlags
0x18000fad1  xor     r8d, r8d; hCryptProv
0x18000fad4  lea     ecx, [rdx+2]; lpszStoreProvider
0x18000fad7  call    cs:__imp_CertOpenStore
0x18000fadd  mov     rdi, rax
0x18000fae0  test    rax, rax
0x18000fae3  jnz     short loc_18000FAF4
0x18000fae5  call    cs:__imp_GetLastError
0x18000faeb  mov     ebx, eax
0x18000faed  test    eax, eax
0x18000faef  jmp     loc_18000F99C
0x18000faf4  mov     rdx, [rsp+530h+hCertStore]
0x18000faf9  xor     r9d, r9d
0x18000fafc  mov     r8, rdi
0x18000faff  mov     ecx, r15d
0x18000fb02  call    cs:__imp_FveCertFilterForValidCertificates
0x18000fb08  mov     ebx, eax
0x18000fb0a  test    eax, eax
0x18000fb0c  js      short loc_18000FB1B
0x18000fb0e  mov     [rsi], rdi
0x18000fb11  mov     rdi, r13
0x18000fb14  jmp     short loc_18000FB1B
0x18000fb16  mov     ebx, 8007000Dh
0x18000fb1b  mov     rcx, [rsp+530h+phContext]; hContext
0x18000fb20  test    rcx, rcx
0x18000fb23  jz      short loc_18000FB30
0x18000fb25  call    cs:__imp_SCardReleaseContext
0x18000fb2b  mov     [rsp+530h+phContext], r13
0x18000fb30  test    rdi, rdi
0x18000fb33  jz      short loc_18000FB40
0x18000fb35  xor     edx, edx; dwFlags
0x18000fb37  mov     rcx, rdi; hCertStore
0x18000fb3a  call    cs:__imp_CertCloseStore
0x18000fb40  mov     rcx, [rsp+530h+hCertStore]; hCertStore
0x18000fb45  test    rcx, rcx
0x18000fb48  jz      short loc_18000FB57
0x18000fb4a  xor     edx, edx; dwFlags
0x18000fb4c  call    cs:__imp_CertCloseStore
0x18000fb52  mov     [rsp+530h+hCertStore], r13
0x18000fb57  mov     rax, [rsp+530h+pv]
0x18000fb5c  test    rax, rax
0x18000fb5f  jz      short loc_18000FB81
0x18000fb61  mov     edx, [rsp+530h+var_4E0]
0x18000fb65  test    rdx, rdx
0x18000fb68  jz      short loc_18000FB76
0x18000fb6a  mov     [rax], r13b
0x18000fb6d  inc     rax
0x18000fb70  sub     rdx, 1
0x18000fb74  jnz     short loc_18000FB6A
0x18000fb76  mov     rcx, [rsp+530h+pv]; pv
0x18000fb7b  call    cs:__imp_CoTaskMemFree
0x18000fb81  test    r14, r14
0x18000fb84  jz      short loc_18000FB8E
0x18000fb86  mov     rcx, r14; void *
0x18000fb89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fb8e  mov     eax, ebx
0x18000fb90  mov     rcx, [rbp+430h+var_40]
0x18000fb97  xor     rcx, rsp; StackCookie
0x18000fb9a  call    __security_check_cookie
0x18000fb9f  mov     rbx, [rsp+530h+arg_8]
0x18000fba7  add     rsp, 500h
0x18000fbae  pop     r15
0x18000fbb0  pop     r14
0x18000fbb2  pop     r13
0x18000fbb4  pop     r12
0x18000fbb6  pop     rdi
0x18000fbb7  pop     rsi
0x18000fbb8  pop     rbp
0x18000fbb9  retn
```
