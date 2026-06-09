# I_CryptGetLowIntegrityUserPath

- ea: `0x180006710`
- end: `0x180006c8c`
- name: `I_CryptGetLowIntegrityUserPath`
- size: `1404`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001798`
- `0x180006290`
- `0x1800063b0`
- `0x180006420`

## callees

- `0x1800059b8`
- `0x180006710`
- `0x180006c94`
- `0x18000a990`
- `0x180017500`
- `0x180026364`
- `0x1800263d0`
- `0x180026552`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ad9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006b90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006c5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ac6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c47`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800068df`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800068df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ad1`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180006bd6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180006bd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000692d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800068b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000692d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006a63`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006959`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180006959`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006979`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180006979`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800069ab`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800069ab`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006a28`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006a28`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006a55`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180006a55`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006776`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006776`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006a0d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180006a0d`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800067c5`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800067c5`

## pseudocode

```c
__int64 __fastcall I_CryptGetLowIntegrityUserPath(void *a1, void *a2)
{
  DWORD v2; // r12d
  _WORD *v3; // r14
  void *v4; // rdi
  BOOL v5; // esi
  __int64 v6; // r15
  int BasicProfileFolderPath; // ebx
  __int64 v8; // rdx
  _WORD *v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rcx
  _WORD *v12; // r8
  const wchar_t *v13; // r9
  _WORD *v14; // rcx
  int v15; // r9d
  __int64 v16; // rbx
  __int64 v17; // rdi
  WCHAR *v18; // rax
  WCHAR *v19; // rsi
  DWORD FileAttributesW; // eax
  DWORD v21; // r13d
  HLOCAL v22; // r15
  struct _ACL *v23; // rcx
  DWORD AceCount; // r14d
  LPVOID i; // rax
  BOOL v26; // r14d
  bool v27; // zf
  DWORD LastError; // ebx
  __int64 Token; // rax
  _WORD *v31; // rax
  _WORD *v32; // rdx
  const wchar_t *v33; // rcx
  _WORD *v34; // rcx
  DWORD v35; // ecx
  HLOCAL v36; // rax
  DWORD nLengthNeeded; // [rsp+60h] [rbp-A0h] BYREF
  WINBOOL TokenInformation; // [rsp+64h] [rbp-9Ch] BYREF
  LPVOID pAce; // [rsp+68h] [rbp-98h] BYREF
  WINBOOL bSaclPresent; // [rsp+70h] [rbp-90h] BYREF
  PACL pSacl; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid1; // [rsp+80h] [rbp-80h] BYREF
  void *v43; // [rsp+88h] [rbp-78h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-70h] BYREF
  _WORD Src[260]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v46[8]; // [rsp+2A8h] [rbp+1A8h] BYREF

  v2 = 0;
  v43 = a2;
  TokenInformation = 0;
  v3 = a2;
  nLengthNeeded = 0;
  if ( a1 )
  {
    v4 = 0;
  }
  else
  {
    Token = I_CryptGetToken();
    v4 = (void *)Token;
    if ( !Token )
      goto LABEL_9;
    a1 = (void *)Token;
  }
  v5 = 0;
  if ( GetTokenInformation(a1, TokenIsAppContainer, &TokenInformation, 4u, &nLengthNeeded) && TokenInformation )
    v5 = nLengthNeeded == 4;
  if ( v4 )
  {
    LastError = GetLastError();
    CloseHandle(v4);
    SetLastError(LastError);
  }
  if ( !v5 )
  {
LABEL_9:
    v6 = 260;
    Src[0] = 0;
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, Src, 260);
    if ( BasicProfileFolderPath >= 0 )
    {
      v8 = 260;
      v9 = Src;
      do
      {
        if ( !*v9 )
          break;
        ++v9;
        --v8;
      }
      while ( v8 );
      BasicProfileFolderPath = -2147024809;
      if ( v8 )
      {
        v10 = 2147483646;
        v11 = 2147483646;
        v12 = &v46[-2 * v8];
        v13 = L"Low";
        do
        {
          if ( !v11 )
            break;
          if ( !*v13 )
            break;
          *v12++ = *v13++;
          --v11;
          --v8;
        }
        while ( v8 );
        v14 = v12 - 1;
        BasicProfileFolderPath = -2147024774;
        if ( v8 )
          v14 = v12;
        v15 = -2147024774;
        if ( v8 )
          v15 = 0;
        *v14 = 0;
        if ( v8 )
        {
          if ( Src[0] == 37 )
            ExpandUserAppDataPathW(Src);
          if ( !v3 || *v3 == 92 )
            goto LABEL_26;
          v31 = Src;
          do
          {
            if ( !*v31 )
              break;
            ++v31;
            --v6;
          }
          while ( v6 );
          if ( v6 )
          {
            v32 = &v46[-2 * v6];
            v33 = L"\\";
            do
            {
              if ( !v10 )
                break;
              if ( !*v33 )
                break;
              *v32++ = *v33++;
              --v10;
              --v6;
            }
            while ( v6 );
            v34 = v32 - 1;
            if ( v6 )
            {
              v34 = v32;
              BasicProfileFolderPath = 0;
            }
            *v34 = 0;
            if ( !v6 )
              goto LABEL_68;
LABEL_26:
            v16 = -1;
            v17 = -1;
            do
              ++v17;
            while ( Src[v17] );
            if ( v3 )
            {
              do
                ++v16;
              while ( v3[v16] );
            }
            else
            {
              LODWORD(v16) = 0;
            }
            v18 = (WCHAR *)LocalAlloc(0, 2LL * (unsigned int)(v17 + v16 + 1));
            v19 = v18;
            if ( !v18 )
            {
              v35 = -2147024882;
              goto LABEL_69;
            }
            memcpy_0(v18, Src, 2LL * (unsigned int)(v17 + 1));
            FileAttributesW = GetFileAttributesW(v19);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
            {
              if ( !(unsigned int)I_RecursiveCreateDirectory(v19) )
                goto LABEL_71;
            }
            else
            {
              *(_DWORD *)pIdentifierAuthority.Value = 0;
              *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
              v21 = 0;
              pSid1 = 0;
              pSacl = 0;
              pAce = 0;
              bSaclPresent = 0;
              TokenInformation = 0;
              nLengthNeeded = 1024;
              v22 = LocalAlloc(0x40u, 0x400u);
              if ( !v22 )
                goto LABEL_83;
              while ( !GetFileSecurityW(v19, 0x10u, v22, nLengthNeeded, &nLengthNeeded) )
              {
                v21 = GetLastError();
                if ( v21 != 122 )
                  goto LABEL_83;
                v36 = LocalReAlloc(v22, nLengthNeeded, 0x40u);
                if ( !v36 )
                  goto LABEL_83;
                v22 = v36;
              }
              if ( GetSecurityDescriptorSacl(v22, &bSaclPresent, &pSacl, &TokenInformation) )
              {
                v23 = pSacl;
                AceCount = 0;
                if ( pSacl )
                  AceCount = pSacl->AceCount;
                for ( i = pAce; v2 < AceCount; i = 0 )
                {
                  if ( !GetAce(v23, v2, &pAce) )
                  {
                    v2 = 0;
                    goto LABEL_83;
                  }
                  i = pAce;
                  if ( *(_BYTE *)pAce == 17 )
                    break;
                  v23 = pSacl;
                  pAce = 0;
                  ++v2;
                }
                v26 = 1;
                if ( i )
                {
                  v2 = 0;
                  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x1000u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
                    goto LABEL_83;
                  if ( EqualSid(pSid1, (char *)pAce + 8) )
                    v26 = (*((_BYTE *)pAce + 1) & 3) != 3;
                }
                v2 = 1;
              }
              else
              {
LABEL_83:
                v21 = GetLastError();
                v26 = 1;
              }
              if ( pSid1 )
                FreeSid(pSid1);
              if ( v22 )
                LocalFree(v22);
              if ( !v2 )
              {
                SetLastError(v21);
                goto LABEL_71;
              }
              v27 = !v26;
              v3 = v43;
              if ( v27 )
              {
LABEL_53:
                memcpy_0(&v19[(unsigned int)v17], v3, 2LL * (unsigned int)(v16 + 1));
                return (__int64)v19;
              }
            }
            if ( (unsigned int)SetLowIntegrityFile(v19) )
              goto LABEL_53;
LABEL_71:
            operator delete(v19);
            return 0;
          }
          BasicProfileFolderPath = -2147024809;
        }
        else
        {
          BasicProfileFolderPath = v15;
        }
      }
    }
LABEL_68:
    v19 = 0;
    v35 = BasicProfileFolderPath;
LABEL_69:
    SetLastError(v35);
    return (__int64)v19;
  }
  return CryptGetAppContainerUserPath(v3);
}

```

## disassembly

```asm
0x180006710  push    rbp
0x180006712  push    rbx
0x180006713  push    rsi
0x180006714  push    rdi
0x180006715  push    r12
0x180006717  push    r14
0x180006719  lea     rbp, [rsp-1C8h]
0x180006721  sub     rsp, 2C8h
0x180006728  mov     rax, cs:__security_cookie
0x18000672f  xor     rax, rsp
0x180006732  mov     [rbp+1F0h+var_40], rax
0x180006739  xor     r12d, r12d
0x18000673c  mov     [rbp+1F0h+var_268], rdx
0x180006740  mov     [rsp+2F0h+TokenInformation], r12d
0x180006745  mov     r14, rdx
0x180006748  mov     [rsp+2F0h+nLengthNeeded], r12d
0x18000674d  test    rcx, rcx
0x180006750  jz      loc_180006AF9
0x180006756  mov     edi, r12d
0x180006759  lea     rax, [rsp+2F0h+nLengthNeeded]
0x18000675e  mov     r9d, 4; TokenInformationLength
0x180006764  lea     r8, [rsp+2F0h+TokenInformation]; TokenInformation
0x180006769  mov     [rsp+2F0h+ReturnLength], rax; ReturnLength
0x18000676e  mov     edx, 1Dh; TokenInformationClass
0x180006773  mov     esi, r12d
0x180006776  call    cs:__imp_GetTokenInformation
0x18000677c  test    eax, eax
0x18000677e  jz      short loc_18000678B
0x180006780  cmp     [rsp+2F0h+TokenInformation], r12d
0x180006785  jnz     loc_180006AE4
0x18000678b  test    rdi, rdi
0x18000678e  jnz     loc_180006AC6
0x180006794  test    esi, esi
0x180006796  jnz     loc_180006BE9
0x18000679c  mov     [rsp+2F0h+arg_10], r13
0x1800067a4  lea     r8, [rbp+1F0h+Src]
0x1800067a8  mov     [rsp+2F0h+var_30], r15
0x1800067b0  xor     edx, edx
0x1800067b2  mov     r15d, 104h
0x1800067b8  mov     [rbp+1F0h+Src], r12w
0x1800067bd  mov     r9d, r15d
0x1800067c0  mov     ecx, 6
0x1800067c5  call    cs:__imp_GetBasicProfileFolderPath
0x1800067cb  mov     ebx, eax
0x1800067cd  test    eax, eax
0x1800067cf  js      loc_180006B8B
0x1800067d5  mov     edx, r15d
0x1800067d8  lea     rax, [rbp+1F0h+Src]
0x1800067dc  nop     dword ptr [rax+00h]
0x1800067e0  cmp     [rax], r12w
0x1800067e4  jz      short loc_1800067F0
0x1800067e6  add     rax, 2
0x1800067ea  sub     rdx, 1
0x1800067ee  jnz     short loc_1800067E0
0x1800067f0  mov     edi, 80070057h
0x1800067f5  test    rdx, rdx
0x1800067f8  mov     ebx, edi
0x1800067fa  cmovnz  ebx, r12d
0x1800067fe  jz      loc_180006B8B
0x180006804  mov     esi, 7FFFFFFEh
0x180006809  lea     rax, [rdx+rdx]
0x18000680d  lea     r8, [rbp+1F0h+var_48]
0x180006814  mov     ecx, esi
0x180006816  sub     r8, rax
0x180006819  lea     r9, aLow; "Low"
0x180006820  test    rcx, rcx
0x180006823  jz      short loc_180006843
0x180006825  movzx   eax, word ptr [r9]
0x180006829  test    ax, ax
0x18000682c  jz      short loc_180006843
0x18000682e  mov     [r8], ax
0x180006832  add     r9, 2
0x180006836  add     r8, 2
0x18000683a  dec     rcx
0x18000683d  sub     rdx, 1
0x180006841  jnz     short loc_180006820
0x180006843  test    rdx, rdx
0x180006846  lea     rcx, [r8-2]
0x18000684a  mov     ebx, 8007007Ah
0x18000684f  cmovnz  rcx, r8
0x180006853  mov     r9d, ebx
0x180006856  cmovnz  r9d, r12d
0x18000685a  mov     [rcx], r12w
0x18000685e  jz      loc_180006C84
0x180006864  mov     eax, 25h ; '%'
0x180006869  cmp     ax, [rbp+1F0h+Src]
0x18000686d  jz      loc_180006C1D
0x180006873  test    r14, r14
0x180006876  jnz     loc_180006B12
0x18000687c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180006883  lea     rax, [rbp+1F0h+Src]
0x180006887  mov     rdi, rbx
0x18000688a  nop     word ptr [rax+rax+00h]
0x180006890  inc     rdi
0x180006893  cmp     [rax+rdi*2], r12w
0x180006898  jnz     short loc_180006890
0x18000689a  test    r14, r14
0x18000689d  jz      loc_180006C32
0x1800068a3  inc     rbx
0x1800068a6  cmp     [r14+rbx*2], r12w
0x1800068ab  jnz     short loc_1800068A3
0x1800068ad  lea     edx, [rbx+1]
0x1800068b0  xor     ecx, ecx; uFlags
0x1800068b2  add     edx, edi
0x1800068b4  add     rdx, rdx; uBytes
0x1800068b7  call    cs:__imp_LocalAlloc
0x1800068bd  mov     rsi, rax
0x1800068c0  test    rax, rax
0x1800068c3  jz      loc_180006C3A
0x1800068c9  lea     r8d, [rdi+1]
0x1800068cd  mov     rcx, rax; void *
0x1800068d0  add     r8, r8; Size
0x1800068d3  lea     rdx, [rbp+1F0h+Src]; Src
0x1800068d7  call    memcpy_0
0x1800068dc  mov     rcx, rsi; lpFileName
0x1800068df  call    cs:__imp_GetFileAttributesW
0x1800068e5  cmp     eax, 0FFFFFFFFh
0x1800068e8  jz      loc_180006B9B
0x1800068ee  test    al, 10h
0x1800068f0  jz      loc_180006B9B
0x1800068f6  mov     edx, 400h; uBytes
0x1800068fb  mov     dword ptr [rbp+1F0h+pIdentifierAuthority.Value], r12d
0x1800068ff  mov     ecx, 40h ; '@'; uFlags
0x180006904  mov     word ptr [rbp+1F0h+pIdentifierAuthority.Value+4], 1000h
0x18000690a  mov     r13d, r12d
0x18000690d  mov     [rbp+1F0h+pSid1], r12
0x180006911  mov     [rsp+2F0h+pSacl], r12
0x180006916  mov     [rsp+2F0h+pAce], r12
0x18000691b  mov     [rsp+2F0h+bSaclPresent], r12d
0x180006920  mov     [rsp+2F0h+TokenInformation], r12d
0x180006925  mov     [rsp+2F0h+nLengthNeeded], 400h
0x18000692d  call    cs:__imp_LocalAlloc
0x180006933  mov     r15, rax
0x180006936  test    rax, rax
0x180006939  jz      loc_180006C47
0x18000693f  mov     r9d, [rsp+2F0h+nLengthNeeded]; nLength
0x180006944  lea     rax, [rsp+2F0h+nLengthNeeded]
0x180006949  mov     r8, r15; pSecurityDescriptor
0x18000694c  mov     [rsp+2F0h+ReturnLength], rax; lpnLengthNeeded
0x180006951  mov     edx, 10h; RequestedInformation
0x180006956  mov     rcx, rsi; lpFileName
0x180006959  call    cs:__imp_GetFileSecurityW
0x18000695f  test    eax, eax
0x180006961  jz      loc_180006BBB
0x180006967  lea     r9, [rsp+2F0h+TokenInformation]; lpbSaclDefaulted
0x18000696c  mov     rcx, r15; pSecurityDescriptor
0x18000696f  lea     r8, [rsp+2F0h+pSacl]; pSacl
0x180006974  lea     rdx, [rsp+2F0h+bSaclPresent]; lpbSaclPresent
0x180006979  call    cs:__imp_GetSecurityDescriptorSacl
0x18000697f  test    eax, eax
0x180006981  jz      loc_180006C47
0x180006987  mov     rcx, [rsp+2F0h+pSacl]; pAcl
0x18000698c  mov     r14d, r12d
0x18000698f  test    rcx, rcx
0x180006992  jz      short loc_180006999
0x180006994  movzx   r14d, word ptr [rcx+4]
0x180006999  mov     rax, [rsp+2F0h+pAce]
0x18000699e  cmp     r12d, r14d
0x1800069a1  jnb     short loc_1800069C7
0x1800069a3  lea     r8, [rsp+2F0h+pAce]; pAce
0x1800069a8  mov     edx, r12d; dwAceIndex
0x1800069ab  call    cs:__imp_GetAce
0x1800069b1  test    eax, eax
0x1800069b3  jz      loc_180006C44
0x1800069b9  mov     rax, [rsp+2F0h+pAce]
0x1800069be  cmp     byte ptr [rax], 11h
0x1800069c1  jnz     loc_180006BF6
0x1800069c7  mov     r14d, 1
0x1800069cd  test    rax, rax
0x1800069d0  jz      short loc_180006A46
0x1800069d2  xor     r12d, r12d
0x1800069d5  lea     rax, [rbp+1F0h+pSid1]
0x1800069d9  mov     [rsp+2F0h+pSid], rax; pSid
0x1800069de  lea     rcx, [rbp+1F0h+pIdentifierAuthority]; pIdentifierAuthority
0x1800069e2  mov     [rsp+2F0h+nSubAuthority7], r12d; nSubAuthority7
0x1800069e7  xor     r9d, r9d; nSubAuthority1
0x1800069ea  mov     [rsp+2F0h+nSubAuthority6], r12d; nSubAuthority6
0x1800069ef  mov     r8d, 1000h; nSubAuthority0
0x1800069f5  mov     [rsp+2F0h+nSubAuthority5], r12d; nSubAuthority5
0x1800069fa  movzx   edx, r14b; nSubAuthorityCount
0x1800069fe  mov     [rsp+2F0h+nSubAuthority4], r12d; nSubAuthority4
0x180006a03  mov     [rsp+2F0h+nSubAuthority3], r12d; nSubAuthority3
0x180006a08  mov     dword ptr [rsp+2F0h+ReturnLength], r12d; nSubAuthority2
0x180006a0d  call    cs:__imp_AllocateAndInitializeSid
0x180006a13  test    eax, eax
0x180006a15  jz      loc_180006C47
0x180006a1b  mov     rdx, [rsp+2F0h+pAce]
0x180006a20  mov     rcx, [rbp+1F0h+pSid1]; pSid1
0x180006a24  add     rdx, 8; pSid2
0x180006a28  call    cs:__imp_EqualSid
0x180006a2e  test    eax, eax
0x180006a30  jz      short loc_180006A46
0x180006a32  mov     rax, [rsp+2F0h+pAce]
0x180006a37  movzx   ecx, byte ptr [rax+1]
0x180006a3b  and     cl, 3
0x180006a3e  cmp     cl, 3
0x180006a41  jnz     short loc_180006A46
0x180006a43  mov     r14d, r12d
0x180006a46  mov     r12d, 1
0x180006a4c  mov     rcx, [rbp+1F0h+pSid1]; pSid
0x180006a50  test    rcx, rcx
0x180006a53  jz      short loc_180006A5B
0x180006a55  call    cs:__imp_FreeSid
0x180006a5b  test    r15, r15
0x180006a5e  jz      short loc_180006A69
0x180006a60  mov     rcx, r15; hMem
0x180006a63  call    cs:__imp_LocalFree
0x180006a69  test    r12d, r12d
0x180006a6c  jz      loc_180006C5B
0x180006a72  test    r14d, r14d
0x180006a75  mov     r14, [rbp+1F0h+var_268]
0x180006a79  jnz     loc_180006C6C
0x180006a7f  mov     eax, edi
0x180006a81  lea     r8d, [rbx+1]
0x180006a85  add     r8, r8; Size
0x180006a88  mov     rdx, r14; Src
0x180006a8b  lea     rcx, [rsi+rax*2]; void *
0x180006a8f  call    memcpy_0
0x180006a94  mov     r15, [rsp+2F0h+var_30]
0x180006a9c  mov     rax, rsi
0x180006a9f  mov     r13, [rsp+2F0h+arg_10]
0x180006aa7  mov     rcx, [rbp+1F0h+var_40]
0x180006aae  xor     rcx, rsp; StackCookie
0x180006ab1  call    __security_check_cookie
0x180006ab6  add     rsp, 2C8h
0x180006abd  pop     r14
0x180006abf  pop     r12
0x180006ac1  pop     rdi
0x180006ac2  pop     rsi
0x180006ac3  pop     rbx
0x180006ac4  pop     rbp
0x180006ac5  retn
0x180006ac6  call    cs:__imp_GetLastError
0x180006acc  mov     rcx, rdi; hObject
0x180006acf  mov     ebx, eax
0x180006ad1  call    cs:__imp_CloseHandle
0x180006ad7  mov     ecx, ebx; dwErrCode
0x180006ad9  call    cs:__imp_SetLastError
0x180006adf  jmp     loc_180006794
0x180006ae4  cmp     [rsp+2F0h+nLengthNeeded], 4
0x180006ae9  jnz     loc_18000678B
0x180006aef  mov     esi, 1
0x180006af4  jmp     loc_18000678B
0x180006af9  call    I_CryptGetToken
0x180006afe  mov     rdi, rax
0x180006b01  test    rax, rax
0x180006b04  jz      loc_18000679C
0x180006b0a  mov     rcx, rax
0x180006b0d  jmp     loc_180006759
0x180006b12  mov     eax, 5Ch ; '\'
0x180006b17  cmp     ax, [r14]
0x180006b1b  jz      loc_18000687C
0x180006b21  lea     rax, [rbp+1F0h+Src]
0x180006b25  cmp     [rax], r12w
0x180006b29  jnz     loc_180006C0A
0x180006b2f  test    r15, r15
0x180006b32  cmovnz  edi, r12d
0x180006b36  jz      loc_180006C2B
0x180006b3c  lea     rax, [r15+r15]
0x180006b40  lea     rdx, [rbp+1F0h+var_48]
0x180006b47  sub     rdx, rax
0x180006b4a  lea     rcx, asc_180029BAC; "\\"
0x180006b51  test    rsi, rsi
0x180006b54  jz      short loc_180006B72
0x180006b56  movzx   eax, word ptr [rcx]
0x180006b59  test    ax, ax
0x180006b5c  jz      short loc_180006B72
0x180006b5e  mov     [rdx], ax
0x180006b61  add     rcx, 2
0x180006b65  add     rdx, 2
0x180006b69  dec     rsi
0x180006b6c  sub     r15, 1
0x180006b70  jnz     short loc_180006B51
0x180006b72  test    r15, r15
0x180006b75  lea     rcx, [rdx-2]
0x180006b79  cmovnz  rcx, rdx
0x180006b7d  cmovnz  ebx, r12d
0x180006b81  mov     [rcx], r12w
0x180006b85  jnz     loc_18000687C
0x180006b8b  mov     rsi, r12
0x180006b8e  mov     ecx, ebx; dwErrCode
0x180006b90  call    cs:__imp_SetLastError
0x180006b96  jmp     loc_180006A94
0x180006b9b  mov     rcx, rsi; lpFileName
0x180006b9e  call    I_RecursiveCreateDirectory
0x180006ba3  test    eax, eax
0x180006ba5  jnz     loc_180006C6F
0x180006bab  mov     rcx, rsi; hMem
0x180006bae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006bb3  mov     rsi, r12
0x180006bb6  jmp     loc_180006A94
0x180006bbb  call    cs:__imp_GetLastError
0x180006bc1  mov     r13d, eax
0x180006bc4  cmp     eax, 7Ah ; 'z'
0x180006bc7  jnz     short loc_180006C47
0x180006bc9  mov     edx, [rsp+2F0h+nLengthNeeded]; uBytes
0x180006bcd  mov     r8d, 40h ; '@'; uFlags
0x180006bd3  mov     rcx, r15; hMem
0x180006bd6  call    cs:__imp_LocalReAlloc
0x180006bdc  test    rax, rax
  ... truncated ...
```
