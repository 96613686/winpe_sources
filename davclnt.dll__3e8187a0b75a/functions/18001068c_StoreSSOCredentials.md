# StoreSSOCredentials

- ea: `0x18001068c`
- end: `0x18001099b`
- name: `StoreSSOCredentials`
- size: `783`
- prototype: `__int64 __fastcall(WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180007ad0`

## callees

- `0x180004300`
- `0x180007a00`
- `0x18000edb4`
- `0x18000ef88`
- `0x180010384`
- `0x18001068c`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108dc`
- `KERNEL32!LocalFree` at `0x18001090f`
- `KERNEL32!LocalFree` at `0x18001090f`
- `ADVAPI32!CredWriteW` at `0x1800108b9`
- `ADVAPI32!CredWriteW` at `0x1800108b9`

## pseudocode

```c
__int64 __fastcall StoreSSOCredentials(WCHAR *a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned int v5; // r13d
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r10
  size_t v9; // r14
  size_t v10; // r10
  bool v11; // cf
  __int64 v12; // r14
  _BYTE *v13; // rdi
  __int64 v14; // rbx
  DWORD LastError; // eax
  __int64 v16; // rdx
  _BYTE *v17; // rax
  size_t pcchLength; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v20; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  _CREDENTIALW Credential; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t psz[344]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(psz, 0, 0x2A2u);
  hMem[0] = 0;
  memset_0(&Credential, 0, sizeof(Credential));
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a2 + 2 * v4) );
  v5 = 0;
  v20 = v4 + 1;
  if ( a1 && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 327, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a1);
    LODWORD(pcchLength) = 0;
    if ( (unsigned int)ReadRegistryDword(
                         L"DisableDomainCreds",
                         (LPBYTE)&pcchLength,
                         L"SYSTEM\\CurrentControlSet\\Control\\Lsa") == 1
      && (_DWORD)pcchLength )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
          v6 = WPP_GLOBAL_Control;
        }
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        {
          v7 = 328;
LABEL_38:
          WPP_SF_(v6[2], v7, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
        }
      }
    }
    else if ( (unsigned int)GetSSORealm((LPBYTE)psz) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v7 = 329;
        goto LABEL_38;
      }
    }
    else
    {
      pcchLength = 0;
      if ( StringLengthWorkerW(psz, 0x151u, &pcchLength) >= 0 )
      {
        v9 = pcchLength;
        v11 = v8 == pcchLength;
        v10 = v8 - pcchLength;
        if ( v11 || v10 == 1 || StringCopyWorkerW(&psz[pcchLength], v10, &pcchLength, L"\\*", 0x7FFFFFFEu) < 0 )
        {
          psz[v9] = 0;
        }
        else if ( (unsigned int)EncryptPassword(a2, hMem, &v20) )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            v7 = 331;
            goto LABEL_38;
          }
        }
        else
        {
          memset_0(&Credential, 0, sizeof(Credential));
          v12 = v20;
          v13 = hMem[0];
          Credential.TargetName = psz;
          Credential.Type = 4;
          Credential.Persist = 1;
          Credential.Flags = 0;
          Credential.CredentialBlobSize = v20;
          Credential.UserName = a1;
          Credential.CredentialBlob = (LPBYTE)hMem[0];
          v5 = CredWriteW(&Credential, 0);
          if ( !v5
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_d(v14, 330, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
          }
          v16 = v12;
          v17 = v13;
          if ( (_DWORD)v12 )
          {
            do
            {
              *v17++ = 0;
              --v16;
            }
            while ( v16 );
          }
          LocalFree(v13);
        }
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v7 = 326;
      goto LABEL_38;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001068c  mov     [rsp-8+arg_10], rbx
0x180010691  push    rbp
0x180010692  push    rsi
0x180010693  push    rdi
0x180010694  push    r12
0x180010696  push    r13
0x180010698  push    r14
0x18001069a  push    r15
0x18001069c  lea     rbp, [rsp-260h]
0x1800106a4  sub     rsp, 360h
0x1800106ab  mov     rax, cs:__security_cookie
0x1800106b2  xor     rax, rsp
0x1800106b5  mov     [rbp+290h+var_40], rax
0x1800106bc  mov     r15, rdx
0x1800106bf  mov     r12, rcx
0x1800106c2  xor     edx, edx; Val
0x1800106c4  lea     rcx, [rbp+290h+psz]; void *
0x1800106c8  mov     r8d, 2A2h; Size
0x1800106ce  call    memset_0
0x1800106d3  xor     r14d, r14d
0x1800106d6  lea     rcx, [rsp+390h+Credential]; void *
0x1800106db  xor     edx, edx; Val
0x1800106dd  mov     [rsp+390h+hMem], r14
0x1800106e2  lea     r8d, [r14+50h]; Size
0x1800106e6  call    memset_0
0x1800106eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800106ef  inc     rax
0x1800106f2  cmp     [r15+rax*2], r14w
0x1800106f7  jnz     short loc_1800106EF
0x1800106f9  inc     eax
0x1800106fb  mov     r13d, r14d
0x1800106fe  mov     [rsp+390h+var_358], eax
0x180010702  test    r12, r12
0x180010705  jz      loc_18001093D
0x18001070b  test    r15, r15
0x18001070e  jz      loc_18001093D
0x180010714  mov     rcx, cs:WPP_GLOBAL_Control
0x18001071b  lea     rbx, WPP_GLOBAL_Control
0x180010722  lea     rsi, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010729  mov     dil, 20h ; ' '
0x18001072c  cmp     rcx, rbx
0x18001072f  jz      short loc_18001074B
0x180010731  test    [rcx+1Ch], dil
0x180010735  jz      short loc_18001074B
0x180010737  mov     rcx, [rcx+10h]
0x18001073b  mov     edx, 147h
0x180010740  mov     r9, r12
0x180010743  mov     r8, rsi
0x180010746  call    WPP_SF_S
0x18001074b  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x180010752  mov     dword ptr [rsp+390h+pcchLength], r14d
0x180010757  lea     rdx, [rsp+390h+pcchLength]; lpData
0x18001075c  lea     rcx, aDisabledomainc; "DisableDomainCreds"
0x180010763  call    ReadRegistryDword
0x180010768  cmp     eax, 1
0x18001076b  jnz     short loc_1800107C2
0x18001076d  cmp     dword ptr [rsp+390h+pcchLength], r14d
0x180010772  jz      short loc_1800107C2
0x180010774  mov     rcx, cs:WPP_GLOBAL_Control
0x18001077b  cmp     rcx, rbx
0x18001077e  jz      loc_18001096E
0x180010784  test    [rcx+1Ch], dil
0x180010788  jz      short loc_1800107A2
0x18001078a  mov     rcx, [rcx+10h]
0x18001078e  mov     edx, 12Ch
0x180010793  mov     r8, rsi
0x180010796  call    WPP_SF_
0x18001079b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107a2  cmp     rcx, rbx
0x1800107a5  jz      loc_18001096E
0x1800107ab  test    [rcx+1Ch], dil
0x1800107af  jz      loc_18001096E
0x1800107b5  mov     edx, 148h
0x1800107ba  mov     r8, rsi
0x1800107bd  jmp     loc_180010965
0x1800107c2  lea     rcx, [rbp+290h+psz]; lpData
0x1800107c6  call    GetSSORealm
0x1800107cb  test    eax, eax
0x1800107cd  jz      short loc_1800107F0
0x1800107cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107d6  cmp     rcx, rbx
0x1800107d9  jz      loc_18001096E
0x1800107df  test    [rcx+1Ch], dil
0x1800107e3  jz      loc_18001096E
0x1800107e9  mov     edx, 149h
0x1800107ee  jmp     short loc_1800107BA
0x1800107f0  mov     r10d, 151h
0x1800107f6  mov     [rsp+390h+pcchLength], r14
0x1800107fb  mov     edx, r10d; cchMax
0x1800107fe  lea     r8, [rsp+390h+pcchLength]; pcchLength
0x180010803  lea     rcx, [rbp+290h+psz]; psz
0x180010807  call    StringLengthWorkerW
0x18001080c  test    eax, eax
0x18001080e  js      loc_18001096E
0x180010814  mov     r14, [rsp+390h+pcchLength]
0x180010819  sub     r10, r14
0x18001081c  cmp     r10, 1
0x180010820  jbe     loc_180010933
0x180010826  lea     rcx, [rbp+290h+psz]
0x18001082a  mov     [rsp+390h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180010833  lea     rcx, [rcx+r14*2]; pszDest
0x180010837  mov     rdx, r10; cchDest
0x18001083a  lea     r9, asc_18001639C; "\\*"
0x180010841  lea     r8, [rsp+390h+pcchLength]; pcchNewDestLength
0x180010846  call    StringCopyWorkerW
0x18001084b  test    eax, eax
0x18001084d  js      loc_180010933
0x180010853  lea     r8, [rsp+390h+var_358]
0x180010858  mov     rcx, r15
0x18001085b  lea     rdx, [rsp+390h+hMem]
0x180010860  call    EncryptPassword
0x180010865  test    eax, eax
0x180010867  jnz     loc_180010917
0x18001086d  xor     edx, edx; Val
0x18001086f  lea     r8d, [rax+50h]; Size
0x180010873  lea     rcx, [rsp+390h+Credential]; void *
0x180010878  call    memset_0
0x18001087d  mov     r14d, [rsp+390h+var_358]
0x180010882  lea     rax, [rbp+290h+psz]
0x180010886  mov     rdi, [rsp+390h+hMem]
0x18001088b  lea     rcx, [rsp+390h+Credential]; Credential
0x180010890  xor     edx, edx; Flags
0x180010892  mov     [rsp+390h+Credential.TargetName], rax
0x180010897  mov     [rsp+390h+Credential.Type], 4
0x18001089f  mov     [rbp+290h+Credential.Persist], 1
0x1800108a6  mov     [rsp+390h+Credential.Flags], r13d
0x1800108ab  mov     [rsp+390h+Credential.CredentialBlobSize], r14d
0x1800108b0  mov     [rbp+290h+Credential.UserName], r12
0x1800108b4  mov     [rsp+390h+Credential.CredentialBlob], rdi
0x1800108b9  call    cs:__imp_CredWriteW
0x1800108bf  mov     r13d, eax
0x1800108c2  test    eax, eax
0x1800108c4  jnz     short loc_1800108F5
0x1800108c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108cd  cmp     rcx, rbx
0x1800108d0  jz      short loc_1800108F5
0x1800108d2  test    byte ptr [rcx+1Ch], 1
0x1800108d6  jz      short loc_1800108F5
0x1800108d8  mov     rbx, [rcx+10h]
0x1800108dc  call    cs:__imp_GetLastError
0x1800108e2  mov     edx, 14Ah
0x1800108e7  mov     r8, rsi
0x1800108ea  mov     r9d, eax
0x1800108ed  mov     rcx, rbx
0x1800108f0  call    WPP_SF_d
0x1800108f5  mov     rdx, r14
0x1800108f8  mov     rax, rdi
0x1800108fb  test    r14d, r14d
0x1800108fe  jz      short loc_18001090C
0x180010900  mov     byte ptr [rax], 0
0x180010903  inc     rax
0x180010906  sub     rdx, 1
0x18001090a  jnz     short loc_180010900
0x18001090c  mov     rcx, rdi; hMem
0x18001090f  call    cs:__imp_LocalFree
0x180010915  jmp     short loc_18001096E
0x180010917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001091e  cmp     rcx, rbx
0x180010921  jz      short loc_18001096E
0x180010923  test    [rcx+1Ch], dil
0x180010927  jz      short loc_18001096E
0x180010929  mov     edx, 14Bh
0x18001092e  jmp     loc_1800107BA
0x180010933  xor     eax, eax
0x180010935  mov     [rbp+r14*2+290h+psz], ax
0x18001093b  jmp     short loc_18001096E
0x18001093d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010944  lea     rbx, WPP_GLOBAL_Control
0x18001094b  cmp     rcx, rbx
0x18001094e  jz      short loc_18001096E
0x180010950  mov     dil, 20h ; ' '
0x180010953  test    [rcx+1Ch], dil
0x180010957  jz      short loc_18001096E
0x180010959  mov     edx, 146h
0x18001095e  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180010965  mov     rcx, [rcx+10h]
0x180010969  call    WPP_SF_
0x18001096e  mov     eax, r13d
0x180010971  mov     rcx, [rbp+290h+var_40]
0x180010978  xor     rcx, rsp; StackCookie
0x18001097b  call    __security_check_cookie
0x180010980  mov     rbx, [rsp+390h+arg_10]
0x180010988  add     rsp, 360h
0x18001098f  pop     r15
0x180010991  pop     r14
0x180010993  pop     r13
0x180010995  pop     r12
0x180010997  pop     rdi
0x180010998  pop     rsi
0x180010999  pop     rbp
0x18001099a  retn
```
