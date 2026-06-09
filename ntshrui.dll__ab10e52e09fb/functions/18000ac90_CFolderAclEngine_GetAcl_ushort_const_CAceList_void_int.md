# CFolderAclEngine::_GetAcl(ushort const *,CAceList * *,void * *,int)

- ea: `0x18000ac90`
- end: `0x18000b231`
- name: `?_GetAcl@CFolderAclEngine@@IEAAJPEBGPEAPEAVCAceList@@PEAPEAXH@Z`
- size: `1441`
- prototype: `int(CFolderAclEngine *__hidden this, const unsigned __int16 *, struct CAceList **, void **, int)`
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800093d0`
- `0x180059214`
- `0x18005a044`
- `0x18005a9ec`
- `0x18005b5e4`
- `0x18005b8b8`
- `0x18005bcac`
- `0x18005c1d0`
- `0x18005c398`
- `0x18005dd50`

## callees

- `0x1800096a0`
- `0x1800098dc`
- `0x18000a5f8`
- `0x18000ac90`
- `0x18000bc00`
- `0x18000d1f0`
- `0x18000f4b0`
- `0x18000f7f0`
- `0x1800254e0`
- `0x1800259bc`
- `0x18005e1c8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b153`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000aebc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000aebc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ae2b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ae2b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b018`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18000b018`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000adf9`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000adf9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000aef9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000aef9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000aecd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b186`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000aecd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000b186`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aee2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aee2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b118`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ad65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b118`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b148`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b16d`
- `ntdll!RtlMapGenericMask` at `0x18000af33`
- `ntdll!RtlMapGenericMask` at `0x18000af33`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18000b0ca`
- `SHELL32!__imp_SHGetCorrectOwnerSid` at `0x18000b0ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b138`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b138`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000acff`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18000acff`

## pseudocode

```c
__int64 __fastcall CFolderAclEngine::_GetAcl(
        CFolderAclEngine *this,
        const unsigned __int16 *a2,
        struct CAceList **a3,
        void **a4,
        int a5)
{
  const unsigned __int16 *v5; // rsi
  PSID *v6; // r12
  signed int NamedSecurityInfoW; // eax
  int v9; // r8d
  signed int Error; // ebx
  struct _ACL *v11; // r14
  PSECURITY_DESCRIPTOR v12; // r15
  CAceList *v13; // rdi
  unsigned int v15; // edx
  DWORD v16; // r12d
  char *v17; // r14
  DWORD *v18; // rax
  DWORD *v19; // rsi
  char *v20; // r15
  DWORD v21; // r12d
  HLOCAL v22; // rax
  void *v23; // r14
  unsigned __int8 v24; // al
  char v25; // cl
  unsigned int v26; // eax
  DWORD v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 (__fastcall *v30)(__int64, __int64, DWORD *); // rax
  __int64 v31; // rbx
  int v32; // eax
  signed int v33; // eax
  unsigned int v34; // edx
  signed int LastError; // eax
  DWORD LengthSid; // eax
  WORD pControl[2]; // [rsp+40h] [rbp-61h] BYREF
  unsigned __int8 v38; // [rsp+44h] [rbp-5Dh]
  DWORD dwRevision[2]; // [rsp+48h] [rbp-59h] BYREF
  __int16 v40; // [rsp+50h] [rbp-51h]
  DWORD v41; // [rsp+54h] [rbp-4Dh]
  PACL v42; // [rsp+58h] [rbp-49h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+60h] [rbp-41h] BYREF
  LPVOID pAce; // [rsp+68h] [rbp-39h] BYREF
  PACL pAcl; // [rsp+70h] [rbp-31h] BYREF
  const unsigned __int16 *v46; // [rsp+78h] [rbp-29h]
  PSECURITY_DESCRIPTOR v47; // [rsp+80h] [rbp-21h]
  void **v48; // [rsp+88h] [rbp-19h]
  PSID ppsidOwner; // [rsp+98h] [rbp-9h] BYREF
  __int64 pAclInformation; // [rsp+A0h] [rbp-1h] BYREF
  int v51; // [rsp+A8h] [rbp+7h]

  v48 = a4;
  v5 = a2;
  v46 = a2;
  hMem = 0;
  v6 = a4;
  pAcl = 0;
  ppsidOwner = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 5u, &ppsidOwner, 0, &pAcl, 0, &hMem);
  Error = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    Error = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( Error >= 0 )
  {
    v11 = pAcl;
    v12 = hMem;
    v47 = hMem;
    v42 = pAcl;
    pAce = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    v13 = (CAceList *)pAce;
    if ( !pAce )
    {
      Error = -2147024882;
      goto LABEL_6;
    }
    *(_QWORD *)pAce = 0;
    *((_QWORD *)v13 + 1) = 0;
    *((_QWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 3) = 1;
    Error = CAceList::_Init(v13);
    if ( Error >= 0 && v11 )
    {
      pAclInformation = 0;
      v51 = 0;
      GetAclInformation(v11, &pAclInformation, 0xCu, AclSizeInformation);
      v16 = 0;
      v41 = 0;
      while ( 1 )
      {
        if ( v16 >= (unsigned int)pAclInformation )
        {
LABEL_40:
          v6 = v48;
          v12 = v47;
          v5 = v46;
          goto LABEL_41;
        }
        pAce = 0;
        if ( !GetAce(v11, v16, &pAce) )
        {
          Error = ResultFromKnownLastError();
          goto LABEL_39;
        }
        v17 = (char *)pAce;
        Error = -2147024882;
        v18 = (DWORD *)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)dwRevision = v18;
        v19 = v18;
        if ( !v18 )
          goto LABEL_38;
        *(_QWORD *)v18 = 0x80000;
        *((_QWORD *)v18 + 1) = 0;
        *((_QWORD *)v18 + 2) = 0;
        *((_QWORD *)v18 + 3) = 0;
        if ( !v17 )
        {
          Error = -2147024809;
LABEL_53:
          CAce::`scalar deleting destructor'((CAce *)v19, v15);
          goto LABEL_38;
        }
        v20 = v17 + 8;
        v38 = *v17;
        if ( v38 != 9 )
          break;
        LengthSid = GetLengthSid(v17 + 8);
        Error = CAce::_Init(
                  (CAce *)v19,
                  v17 + 8,
                  *((_DWORD *)v17 + 1),
                  v17[1],
                  *v17,
                  *((_WORD *)v17 + 1),
                  &v20[LengthSid]);
LABEL_26:
        if ( Error < 0 )
          goto LABEL_53;
        v27 = v19[7];
        v28 = v27 & 0x20;
        if ( (v27 & 0x20) != 0 )
        {
          v29 = v27 & 1;
        }
        else
        {
          v29 = v27 & 1;
          if ( !v29 )
          {
            Error = CAceList::_AddExplicitAceToDpa(v28, v13, v19);
            goto LABEL_37;
          }
        }
        if ( !(_DWORD)v28 && v29 )
        {
          Error = CAceList::_AddExplicitAceToDpa(v28, (char *)v13 + 8, v19);
        }
        else
        {
          v30 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
          v31 = *((_QWORD *)v13 + 2);
          if ( qword_1800959F8 == -1 )
          {
            GetProcFromComCtl32(&qword_1800959F8, 334);
            v30 = (__int64 (__fastcall *)(__int64, __int64, DWORD *))qword_1800959F8;
          }
          if ( v30 )
            v32 = v30(v31, 0x7FFFFFFF, v19);
          else
            v32 = -1;
          Error = 0;
          if ( v32 == -1 )
            Error = -2147024882;
        }
LABEL_37:
        if ( Error )
          goto LABEL_53;
LABEL_38:
        v11 = v42;
LABEL_39:
        v41 = ++v16;
        if ( Error < 0 )
          goto LABEL_40;
      }
      Error = -2147024809;
      if ( v17 == (char *)-8LL )
        goto LABEL_26;
      v40 = *((_WORD *)v17 + 1);
      LOBYTE(pControl[0]) = v17[1];
      dwRevision[0] = *((_DWORD *)v17 + 1);
      if ( IsValidSid(v17 + 8) )
      {
        v21 = GetLengthSid(v17 + 8);
        Error = -2147024882;
        v22 = LocalAlloc(0x40u, v21);
        v23 = v22;
        if ( v22 )
        {
          if ( CopySid(v21, v22, v20) )
          {
            Error = 0;
            goto LABEL_21;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
          {
LABEL_21:
            v24 = v38;
            *((_QWORD *)v19 + 1) = v23;
            *(_BYTE *)v19 = v24;
            *((_BYTE *)v19 + 1) = pControl[0];
            *((_WORD *)v19 + 1) = v40;
            v19[1] = dwRevision[0];
            RtlMapGenericMask(v19 + 1, (PGENERIC_MAPPING)&GenericMapping);
            v25 = *(_BYTE *)v19;
            v19[7] = 0x80000000;
            if ( !v25 || (v26 = 0x80000000, v25 == 9) )
            {
              v19[7] = -2147483647;
              v26 = -2147483647;
            }
            if ( (*((_BYTE *)v19 + 1) & 0x10) != 0 )
              v19[7] = v26 | 0x20;
            goto LABEL_25;
          }
          LocalFree(v23);
        }
      }
LABEL_25:
      v16 = v41;
      goto LABEL_26;
    }
LABEL_41:
    if ( Error >= 0 )
    {
      if ( v12 )
      {
        pControl[0] = 0;
        dwRevision[0] = 0;
        if ( GetSecurityDescriptorControl(v12, pControl, dwRevision) )
        {
          if ( (pControl[0] & 0x1000) != 0 )
            *((_DWORD *)v13 + 6) = 0;
          *((_DWORD *)v13 + 7) = a5;
LABEL_57:
          *a3 = v13;
          if ( !v6 )
            goto LABEL_6;
          *(_QWORD *)dwRevision = 0;
          Error = SHGetCorrectOwnerSid(v5, ppsidOwner, dwRevision);
          if ( Error >= 0 )
          {
            if ( ConvertStringSidToSidW(*(LPCWSTR *)dwRevision, v6) )
            {
              Error = 0;
              LocalFree(*(HLOCAL *)dwRevision);
              goto LABEL_6;
            }
            LastError = GetLastError();
            Error = LastError;
            if ( LastError > 0 )
              Error = (unsigned __int16)LastError | 0x80070000;
            if ( Error >= 0 )
              Error = -2147467259;
            LocalFree(*(HLOCAL *)dwRevision);
          }
          if ( *a3 )
            CAceList::`scalar deleting destructor'(*a3, v34);
LABEL_6:
          LocalFree(hMem);
          if ( Error >= 0 )
            return (unsigned int)Error;
          goto LABEL_74;
        }
        v33 = GetLastError();
        Error = v33;
        if ( v33 > 0 )
          Error = (unsigned __int16)v33 | 0x80070000;
      }
      if ( Error >= 0 )
        goto LABEL_57;
    }
    CAceList::`scalar deleting destructor'(v13, v15);
    goto LABEL_6;
  }
LABEL_74:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v9, (_DWORD)v5, Error);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000ac90  push    rbp
0x18000ac92  push    rbx
0x18000ac93  push    rsi
0x18000ac94  push    r12
0x18000ac96  push    r13
0x18000ac98  lea     rbp, [rsp-2Fh]
0x18000ac9d  sub     rsp, 0D0h
0x18000aca4  mov     rax, cs:__security_cookie
0x18000acab  xor     rax, rsp
0x18000acae  mov     [rbp+4Fh+var_40], rax
0x18000acb2  xor     ecx, ecx
0x18000acb4  mov     [rbp+4Fh+var_68], r9
0x18000acb8  mov     rsi, rdx
0x18000acbb  mov     [rbp+4Fh+var_78], rdx
0x18000acbf  lea     rax, [rbp+4Fh+hMem]
0x18000acc3  mov     [rbp+4Fh+hMem], rcx
0x18000acc7  mov     [rsp+0F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18000accc  mov     r12, r9
0x18000accf  mov     [rsp+0F0h+ppSacl], rcx; ppSacl
0x18000acd4  lea     rax, [rbp+4Fh+pAcl]
0x18000acd8  mov     [rsp+0F0h+ppDacl], rax; ppDacl
0x18000acdd  lea     r9, [rbp+4Fh+ppsidOwner]; ppsidOwner
0x18000ace1  mov     [rsp+0F0h+ppsidGroup], rcx; ppsidGroup
0x18000ace6  mov     r13, r8
0x18000ace9  mov     [rbp+4Fh+pAcl], rcx
0x18000aced  mov     edx, 1; ObjectType
0x18000acf2  mov     [rbp+4Fh+ppsidOwner], rcx
0x18000acf6  mov     r8d, 5; SecurityInfo
0x18000acfc  mov     rcx, rsi; pObjectName
0x18000acff  call    cs:__imp_GetNamedSecurityInfoW
0x18000ad05  mov     ebx, eax
0x18000ad07  test    eax, eax
0x18000ad09  jg      loc_18000B04C
0x18000ad0f  test    ebx, ebx
0x18000ad11  js      loc_18000B1F6
0x18000ad17  mov     [rsp+0F0h+arg_0], rdi
0x18000ad1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad26  mov     [rsp+0F0h+var_28], r14
0x18000ad2e  mov     ecx, 20h ; ' '; unsigned __int64
0x18000ad33  mov     r14, [rbp+4Fh+pAcl]
0x18000ad37  mov     [rsp+0F0h+var_30], r15
0x18000ad3f  mov     r15, [rbp+4Fh+hMem]
0x18000ad43  mov     [rbp+4Fh+var_70], r15
0x18000ad47  mov     [rbp+4Fh+var_98], r14
0x18000ad4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad50  mov     [rbp+4Fh+pAce], rax
0x18000ad54  mov     rdi, rax
0x18000ad57  test    rax, rax
0x18000ad5a  jnz     short loc_18000ADA8
0x18000ad5c  mov     ebx, 8007000Eh
0x18000ad61  mov     rcx, [rbp+4Fh+hMem]; hMem
0x18000ad65  call    cs:__imp_LocalFree
0x18000ad6b  mov     r15, [rsp+0F0h+var_30]
0x18000ad73  mov     r14, [rsp+0F0h+var_28]
0x18000ad7b  mov     rdi, [rsp+0F0h+arg_0]
0x18000ad83  test    ebx, ebx
0x18000ad85  js      loc_18000B1F6
0x18000ad8b  mov     eax, ebx
0x18000ad8d  mov     rcx, [rbp+4Fh+var_40]
0x18000ad91  xor     rcx, rsp; StackCookie
0x18000ad94  call    __security_check_cookie
0x18000ad99  add     rsp, 0D0h
0x18000ada0  pop     r13
0x18000ada2  pop     r12
0x18000ada4  pop     rsi
0x18000ada5  pop     rbx
0x18000ada6  pop     rbp
0x18000ada7  retn
0x18000ada8  xor     eax, eax
0x18000adaa  mov     [rdi], rax
0x18000adad  mov     [rdi+8], rax
0x18000adb1  mov     [rdi+10h], rax
0x18000adb5  mov     qword ptr [rdi+18h], 1
0x18000adbd  test    rdi, rdi
0x18000adc0  jz      short loc_18000AD5C
0x18000adc2  mov     rcx, rdi; this
0x18000adc5  call    ?_Init@CAceList@@AEAAJXZ; CAceList::_Init(void)
0x18000adca  mov     ebx, eax
0x18000adcc  test    eax, eax
0x18000adce  js      loc_18000AFF3
0x18000add4  test    r14, r14
0x18000add7  jz      loc_18000AFF3
0x18000addd  xor     eax, eax
0x18000addf  lea     rdx, [rbp+4Fh+pAclInformation]; pAclInformation
0x18000ade3  mov     r9d, 2; dwAclInformationClass
0x18000ade9  mov     [rbp+4Fh+pAclInformation], rax
0x18000aded  mov     r8d, 0Ch; nAclInformationLength
0x18000adf3  mov     [rbp+4Fh+var_48], eax
0x18000adf6  mov     rcx, r14; pAcl
0x18000adf9  call    cs:__imp_GetAclInformation
0x18000adff  xor     r15d, r15d
0x18000ae02  mov     esi, 8007000Eh
0x18000ae07  mov     r12d, r15d
0x18000ae0a  mov     [rbp+4Fh+var_9C], r15d
0x18000ae0e  jmp     short loc_18000AE13
0x18000ae10  xor     r15d, r15d
0x18000ae13  cmp     r12d, dword ptr [rbp+4Fh+pAclInformation]
0x18000ae17  jnb     loc_18000AFE7
0x18000ae1d  lea     r8, [rbp+4Fh+pAce]; pAce
0x18000ae21  mov     [rbp+4Fh+pAce], r15
0x18000ae25  mov     edx, r12d; dwAceIndex
0x18000ae28  mov     rcx, r14; pAcl
0x18000ae2b  call    cs:__imp_GetAce
0x18000ae31  test    eax, eax
0x18000ae33  jz      loc_18000B0FA
0x18000ae39  mov     r14, [rbp+4Fh+pAce]
0x18000ae3d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ae44  mov     ecx, 20h ; ' '; unsigned __int64
0x18000ae49  mov     ebx, esi
0x18000ae4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ae50  mov     qword ptr [rbp+4Fh+dwRevision], rax
0x18000ae54  mov     rsi, rax
0x18000ae57  test    rax, rax
0x18000ae5a  jz      loc_18000AFCF
0x18000ae60  mov     qword ptr [rax], 80000h
0x18000ae67  mov     [rax+8], r15
0x18000ae6b  mov     [rax+10h], r15
0x18000ae6f  mov     qword ptr [rax+18h], 0
0x18000ae77  test    r14, r14
0x18000ae7a  jz      loc_18000B088
0x18000ae80  movzx   eax, byte ptr [r14]
0x18000ae84  lea     r15, [r14+8]
0x18000ae88  mov     [rbp+4Fh+var_AC], al
0x18000ae8b  cmp     al, 9
0x18000ae8d  jz      loc_18000B183
0x18000ae93  mov     ebx, 80070057h
0x18000ae98  test    r15, r15
0x18000ae9b  jz      loc_18000AF67
0x18000aea1  movzx   eax, word ptr [r14+2]
0x18000aea6  mov     rcx, r15; pSid
0x18000aea9  mov     [rbp+4Fh+var_A0], ax
0x18000aead  movzx   eax, byte ptr [r14+1]
0x18000aeb2  mov     byte ptr [rbp+4Fh+pControl], al
0x18000aeb5  mov     eax, [r14+4]
0x18000aeb9  mov     [rbp+4Fh+dwRevision], eax
0x18000aebc  call    cs:__imp_IsValidSid
0x18000aec2  test    eax, eax
0x18000aec4  jz      loc_18000AF63
0x18000aeca  mov     rcx, r15; pSid
0x18000aecd  call    cs:__imp_GetLengthSid
0x18000aed3  mov     edx, eax; uBytes
0x18000aed5  mov     ecx, 40h ; '@'; uFlags
0x18000aeda  mov     r12d, eax
0x18000aedd  mov     ebx, 8007000Eh
0x18000aee2  call    cs:__imp_LocalAlloc
0x18000aee8  mov     r14, rax
0x18000aeeb  test    rax, rax
0x18000aeee  jz      short loc_18000AF63
0x18000aef0  mov     r8, r15; pSourceSid
0x18000aef3  mov     rdx, rax; pDestinationSid
0x18000aef6  mov     ecx, r12d; nDestinationSidLength
0x18000aef9  call    cs:__imp_CopySid
0x18000aeff  test    eax, eax
0x18000af01  jz      loc_18000B106
0x18000af07  xor     ebx, ebx
0x18000af09  movzx   eax, [rbp+4Fh+var_AC]
0x18000af0d  lea     rdx, GenericMapping; GenericMapping
0x18000af14  mov     [rsi+8], r14
0x18000af18  lea     rcx, [rsi+4]; AccessMask
0x18000af1c  mov     [rsi], al
0x18000af1e  movzx   eax, byte ptr [rbp+4Fh+pControl]
0x18000af22  mov     [rsi+1], al
0x18000af25  movzx   eax, [rbp+4Fh+var_A0]
0x18000af29  mov     [rsi+2], ax
0x18000af2d  mov     eax, [rbp+4Fh+dwRevision]
0x18000af30  mov     [rsi+4], eax
0x18000af33  call    cs:__imp_RtlMapGenericMask
0x18000af39  movzx   ecx, byte ptr [rsi]
0x18000af3c  mov     dword ptr [rsi+1Ch], 80000000h
0x18000af43  test    cl, cl
0x18000af45  jnz     loc_18000B039
0x18000af4b  mov     dword ptr [rsi+1Ch], 80000001h
0x18000af52  mov     eax, 80000001h
0x18000af57  test    byte ptr [rsi+1], 10h
0x18000af5b  jz      short loc_18000AF63
0x18000af5d  or      eax, 20h
0x18000af60  mov     [rsi+1Ch], eax
0x18000af63  mov     r12d, [rbp+4Fh+var_9C]
0x18000af67  test    ebx, ebx
0x18000af69  js      loc_18000B08D
0x18000af6f  mov     eax, [rsi+1Ch]
0x18000af72  mov     ecx, eax
0x18000af74  and     ecx, 20h
0x18000af77  jz      loc_18000B05A
0x18000af7d  and     eax, 1
0x18000af80  test    ecx, ecx
0x18000af82  jnz     short loc_18000AF8C
0x18000af84  test    eax, eax
0x18000af86  jnz     loc_18000B075
0x18000af8c  mov     rax, cs:qword_1800959F8
0x18000af93  mov     rbx, [rdi+10h]
0x18000af97  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000af9b  jz      loc_18000B1C3
0x18000afa1  test    rax, rax
0x18000afa4  jz      loc_18000B1E0
0x18000afaa  mov     r8, rsi
0x18000afad  mov     edx, 7FFFFFFFh
0x18000afb2  mov     rcx, rbx
0x18000afb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afba  xor     ebx, ebx
0x18000afbc  cmp     eax, 0FFFFFFFFh
0x18000afbf  mov     eax, 8007000Eh
0x18000afc4  cmovz   ebx, eax
0x18000afc7  test    ebx, ebx
0x18000afc9  jnz     loc_18000B08D
0x18000afcf  mov     r14, [rbp+4Fh+var_98]
0x18000afd3  mov     esi, 8007000Eh
0x18000afd8  inc     r12d
0x18000afdb  mov     [rbp+4Fh+var_9C], r12d
0x18000afdf  test    ebx, ebx
0x18000afe1  jns     loc_18000AE10
0x18000afe7  mov     r12, [rbp+4Fh+var_68]
0x18000afeb  mov     r15, [rbp+4Fh+var_70]
0x18000afef  mov     rsi, [rbp+4Fh+var_78]
0x18000aff3  test    ebx, ebx
0x18000aff5  js      loc_18000B0ED
0x18000affb  test    r15, r15
0x18000affe  jz      loc_18000B0A6
0x18000b004  xor     eax, eax
0x18000b006  lea     r8, [rbp+4Fh+dwRevision]; lpdwRevision
0x18000b00a  lea     rdx, [rbp+4Fh+pControl]; pControl
0x18000b00e  mov     [rbp+4Fh+pControl], ax
0x18000b012  mov     rcx, r15; pSecurityDescriptor
0x18000b015  mov     [rbp+4Fh+dwRevision], eax
0x18000b018  call    cs:__imp_GetSecurityDescriptorControl
0x18000b01e  test    eax, eax
0x18000b020  jz      short loc_18000B09A
0x18000b022  mov     eax, 1000h
0x18000b027  test    [rbp+4Fh+pControl], ax
0x18000b02b  jnz     loc_18000B1EA
0x18000b031  mov     eax, [rbp+4Fh+arg_20]
0x18000b034  mov     [rdi+1Ch], eax
0x18000b037  jmp     short loc_18000B0AA
0x18000b039  mov     eax, 80000000h
0x18000b03e  cmp     cl, 9
0x18000b041  jnz     loc_18000AF57
0x18000b047  jmp     loc_18000AF4B
0x18000b04c  movzx   ebx, ax
0x18000b04f  or      ebx, 80070000h
0x18000b055  jmp     loc_18000AD0F
0x18000b05a  and     eax, 1
0x18000b05d  jnz     loc_18000AF80
0x18000b063  mov     r8, rsi
0x18000b066  mov     rdx, rdi
0x18000b069  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000b06e  mov     ebx, eax
0x18000b070  jmp     loc_18000AFC7
0x18000b075  lea     rdx, [rdi+8]
0x18000b079  mov     r8, rsi
0x18000b07c  call    ?_AddExplicitAceToDpa@CAceList@@AEAAJAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAVCAce@@@Z; CAceList::_AddExplicitAceToDpa(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,CAce *)
0x18000b081  mov     ebx, eax
0x18000b083  jmp     loc_18000AFC7
0x18000b088  mov     ebx, 80070057h
0x18000b08d  mov     rcx, rsi; this
0x18000b090  call    ??_GCAce@@QEAAPEAXI@Z; CAce::`scalar deleting destructor'(uint)
0x18000b095  jmp     loc_18000AFCF
0x18000b09a  call    cs:__imp_GetLastError
0x18000b0a0  mov     ebx, eax
0x18000b0a2  test    eax, eax
0x18000b0a4  jg      short loc_18000B123
0x18000b0a6  test    ebx, ebx
0x18000b0a8  js      short loc_18000B0ED
0x18000b0aa  mov     [r13+0], rdi
0x18000b0ae  test    r12, r12
0x18000b0b1  jz      loc_18000AD61
0x18000b0b7  mov     rdx, [rbp+4Fh+ppsidOwner]
0x18000b0bb  lea     r8, [rbp+4Fh+dwRevision]
0x18000b0bf  mov     rcx, rsi
0x18000b0c2  mov     qword ptr [rbp+4Fh+dwRevision], 0
0x18000b0ca  call    cs:__imp_SHGetCorrectOwnerSid
0x18000b0d0  mov     ebx, eax
0x18000b0d2  test    eax, eax
0x18000b0d4  jns     short loc_18000B131
0x18000b0d6  mov     rcx, [r13+0]; this
0x18000b0da  test    rcx, rcx
0x18000b0dd  jz      loc_18000AD61
0x18000b0e3  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000b0e8  jmp     loc_18000AD61
0x18000b0ed  mov     rcx, rdi; this
0x18000b0f0  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18000b0f5  jmp     loc_18000AD61
0x18000b0fa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b0ff  mov     ebx, eax
0x18000b101  jmp     loc_18000AFD8
0x18000b106  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000b10b  mov     ebx, eax
0x18000b10d  test    eax, eax
0x18000b10f  jns     loc_18000AF09
0x18000b115  mov     rcx, r14; hMem
0x18000b118  call    cs:__imp_LocalFree
0x18000b11e  jmp     loc_18000AF63
0x18000b123  movzx   ebx, ax
0x18000b126  or      ebx, 80070000h
0x18000b12c  jmp     loc_18000B0A6
0x18000b131  mov     rcx, qword ptr [rbp+4Fh+dwRevision]; StringSid
0x18000b135  mov     rdx, r12; Sid
0x18000b138  call    cs:__imp_ConvertStringSidToSidW
0x18000b13e  test    eax, eax
0x18000b140  jz      short loc_18000B153
0x18000b142  mov     rcx, qword ptr [rbp+4Fh+dwRevision]; hMem
  ... truncated ...
```
