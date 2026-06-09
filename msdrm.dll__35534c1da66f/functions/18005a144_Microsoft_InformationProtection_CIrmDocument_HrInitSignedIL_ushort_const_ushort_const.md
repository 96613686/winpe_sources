# Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL(ushort const *,ushort const *)

- ea: `0x18005a144`
- end: `0x18005a4ea`
- name: `?HrInitSignedIL@CIrmDocument@InformationProtection@Microsoft@@AEAAJPEBG0@Z`
- size: `934`
- prototype: `__int64 __fastcall(Microsoft::InformationProtection::CIrmDocument *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059920`

## callees

- `0x180001284`
- `0x180004930`
- `0x180004970`
- `0x1800050d0`
- `0x180005fc0`
- `0x1800075b0`
- `0x180056e20`
- `0x1800590cc`
- `0x18005a144`
- `0x18005a9cc`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a470`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005a470`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a3d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a3d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a363`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a363`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005a333`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005a333`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005a30a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005a30a`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL(
        Microsoft::InformationProtection::CIrmDocument *this,
        unsigned __int16 *a2,
        WCHAR *a3)
{
  int v4; // edi
  DRMPUBHANDLE v5; // r15d
  DRMPUBHANDLE hOwner; // r12d
  __int64 v7; // rcx
  int v9; // esi
  DRMENVHANDLE v10; // r13d
  WCHAR *v11; // rax
  HRESULT v12; // eax
  void *v13; // rsi
  HRESULT v14; // eax
  HRESULT v15; // eax
  __int64 v16; // r8
  void *v17; // rcx
  HANDLE EventW; // rax
  DRMPUBHANDLE phUser; // [rsp+50h] [rbp-98h] BYREF
  DRMPUBHANDLE phIssuanceLicense; // [rsp+54h] [rbp-94h] BYREF
  DRMENVHANDLE hEnv; // [rsp+58h] [rbp-90h]
  __int128 pvContext; // [rsp+60h] [rbp-88h] BYREF
  __int64 v23; // [rsp+70h] [rbp-78h]
  unsigned __int16 *v24; // [rsp+78h] [rbp-70h]
  PWSTR wszUserName; // [rsp+80h] [rbp-68h]
  PWSTR wszClientLicensorCertificate; // [rsp+88h] [rbp-60h]
  __int64 v27; // [rsp+90h] [rbp-58h]
  GUID pguid; // [rsp+98h] [rbp-50h] BYREF

  v27 = -2;
  wszUserName = a3;
  v24 = a2;
  v4 = 0;
  v5 = 0;
  phIssuanceLicense = 0;
  hOwner = 0;
  phUser = 0;
  pvContext = 0;
  v23 = 0;
  v7 = *((_QWORD *)this + 17);
  if ( !v7 )
  {
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL",
      2147549183LL);
    return 2147549183LL;
  }
  try
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 48LL))(*((_QWORD *)this + 17));
    hEnv = v10;
    v11 = (WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 64LL))(*((_QWORD *)this + 17));
    wszClientLicensorCertificate = v11;
    if ( !v9 || !v10 || !v11 || *((_QWORD *)this + 13) )
      v4 = -2147418113;
    Microsoft::InformationProtection::IppUtil::DuplicateString((unsigned __int16 **)this + 16, v24);
    if ( wszUserName && v4 >= 0 )
    {
      v12 = DRMCreateUser(wszUserName, 0, (PWSTR)L"Unspecified", &phUser);
      v4 = v12;
      if ( v12 < 0 )
      {
        Microsoft::InformationProtection::DebugLog(
          (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
          "Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL",
          611,
          (unsigned int)v12);
        v13 = 0;
        hOwner = phUser;
        goto LABEL_17;
      }
      hOwner = phUser;
    }
    v13 = 0;
    if ( v4 >= 0 )
    {
      v14 = DRMCreateIssuanceLicense(0, 0, 0, 0, hOwner, *((PWSTR *)this + 16), 0, &phIssuanceLicense);
      v4 = v14;
      if ( v14 < 0 )
        Microsoft::InformationProtection::DebugLog(
          (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
          "Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL",
          620,
          (unsigned int)v14);
      v5 = phIssuanceLicense;
    }
LABEL_17:
    pguid = 0;
    if ( v4 < 0 )
      goto LABEL_22;
    v15 = CoCreateGuid(&pguid);
    v4 = v15;
    if ( v15 >= 0 )
    {
      if ( StringFromGUID2(&pguid, (LPOLESTR)this + 12, 39) != 39 )
      {
        v4 = -2147418113;
        goto LABEL_22;
      }
      v15 = DRMSetMetaData(v5, (PWSTR)this + 12, (PWSTR)L"MS-GUID", 0, 0, (PWSTR)L"RMS Bulk Protected Document", 0);
      v4 = v15;
      if ( v15 >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        v13 = EventW;
        if ( EventW )
        {
          *(_QWORD *)&pvContext = this;
          *((_QWORD *)&pvContext + 1) = EventW;
          LODWORD(v23) = 0;
          v15 = DRMGetSignedIssuanceLicense(
                  hEnv,
                  v5,
                  0x32u,
                  0,
                  0,
                  (PWSTR)L"AES",
                  wszClientLicensorCertificate,
                  Microsoft::InformationProtection::CIrmDocument::OnStatus,
                  0,
                  &pvContext);
          v4 = v15;
          if ( v15 < 0 )
          {
            v16 = 665;
            goto LABEL_37;
          }
          if ( !WaitForSingleObject(v13, 0xEA60u) )
          {
            if ( (int)v23 >= 0 )
            {
              Microsoft::InformationProtection::CIrmDocument::HrFetchOwnerLicense(this, v5);
LABEL_25:
              if ( v13 != (void *)-1LL )
                CloseHandle(v13);
LABEL_27:
              if ( hOwner )
                DRMClosePubHandle(hOwner);
              if ( v5 )
                DRMClosePubHandle(v5);
              goto LABEL_48;
            }
            v4 = v23;
LABEL_22:
            v17 = (void *)*((_QWORD *)this + 13);
            if ( v17 )
            {
              operator delete(v17);
              *((_QWORD *)this + 13) = 0;
            }
            if ( !v13 )
              goto LABEL_27;
            goto LABEL_25;
          }
        }
        v4 = -2147467259;
        goto LABEL_22;
      }
      v16 = 639;
    }
    else
    {
      v16 = 626;
    }
LABEL_37:
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL",
      v16,
      (unsigned int)v15);
    goto LABEL_22;
  }
  catch ( ... )
  {
    Microsoft::InformationProtection::HandleException((Microsoft::InformationProtection *)v17);
  }
LABEL_48:
  if ( v4 < 0 )
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitSignedIL",
      700,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005a144  mov     r11, rsp
0x18005a147  push    rbx
0x18005a148  push    rsi
0x18005a149  push    rdi
0x18005a14a  push    r12
0x18005a14c  push    r13
0x18005a14e  push    r14
0x18005a150  push    r15
0x18005a152  sub     rsp, 0B0h
0x18005a159  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x18005a161  mov     rax, cs:__security_cookie
0x18005a168  xor     rax, rsp
0x18005a16b  mov     [rsp+0E8h+var_40], rax
0x18005a173  mov     [rsp+0E8h+wszUserName], r8
0x18005a17b  mov     [rsp+0E8h+var_70], rdx
0x18005a180  mov     r14, rcx
0x18005a183  xor     ebx, ebx
0x18005a185  mov     edi, ebx
0x18005a187  mov     r15d, ebx
0x18005a18a  mov     [rsp+0E8h+var_94], ebx
0x18005a18e  mov     r12d, ebx
0x18005a191  mov     [rsp+0E8h+phUser], ebx
0x18005a195  xorps   xmm0, xmm0
0x18005a198  xor     eax, eax
0x18005a19a  movups  [rsp+0E8h+var_88], xmm0
0x18005a19f  mov     [r11-78h], rax
0x18005a1a3  mov     rcx, [rcx+88h]
0x18005a1aa  test    rcx, rcx
0x18005a1ad  jnz     short loc_18005A1D2
0x18005a1af  mov     r8d, 8000FFFFh
0x18005a1b5  lea     rdx, aMicrosoftInfor_14; "Microsoft::InformationProtection::CIrmD"...
0x18005a1bc  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x18005a1c3  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005a1c8  mov     eax, 8000FFFFh
0x18005a1cd  jmp     loc_18005A4C6
0x18005a1d2  mov     rax, [rcx]
0x18005a1d5  mov     rax, [rax+20h]
0x18005a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1de  mov     esi, eax
0x18005a1e0  mov     rcx, [r14+88h]
0x18005a1e7  mov     rax, [rcx]
0x18005a1ea  mov     rax, [rax+30h]
0x18005a1ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a1f3  mov     r13d, eax
0x18005a1f6  mov     [rsp+0E8h+hEnv], eax
0x18005a1fa  mov     rcx, [r14+88h]
0x18005a201  mov     rax, [rcx]
0x18005a204  mov     rax, [rax+40h]
0x18005a208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a20d  mov     [rsp+0E8h+wszClientLicensorCertificate], rax
0x18005a215  test    esi, esi
0x18005a217  jz      short loc_18005A229
0x18005a219  test    r13d, r13d
0x18005a21c  jz      short loc_18005A229
0x18005a21e  test    rax, rax
0x18005a221  jz      short loc_18005A229
0x18005a223  cmp     [r14+68h], rbx
0x18005a227  jz      short loc_18005A22E
0x18005a229  mov     edi, 8000FFFFh
0x18005a22e  lea     r13, [r14+80h]
0x18005a235  mov     rdx, [rsp+0E8h+var_70]; unsigned __int16 *
0x18005a23a  mov     rcx, r13; unsigned __int16 **
0x18005a23d  call    ?DuplicateString@IppUtil@InformationProtection@Microsoft@@SAXPEAPEAGPEBG@Z; Microsoft::InformationProtection::IppUtil::DuplicateString(ushort * *,ushort const *)
0x18005a242  mov     rax, [rsp+0E8h+wszUserName]
0x18005a24a  test    rax, rax
0x18005a24d  jz      short loc_18005A29A
0x18005a24f  test    edi, edi
0x18005a251  js      short loc_18005A29A
0x18005a253  lea     r9, [rsp+0E8h+phUser]; phUser
0x18005a258  lea     r8, aUnspecified; "Unspecified"
0x18005a25f  xor     edx, edx; wszUserId
0x18005a261  mov     rcx, rax; wszUserName
0x18005a264  call    DRMCreateUser
0x18005a269  mov     edi, eax
0x18005a26b  test    eax, eax
0x18005a26d  jns     short loc_18005A295
0x18005a26f  mov     r9d, eax
0x18005a272  mov     r8d, 263h
0x18005a278  lea     rdx, aMicrosoftInfor_14; "Microsoft::InformationProtection::CIrmD"...
0x18005a27f  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005a286  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005a28b  mov     rsi, rbx
0x18005a28e  mov     r12d, [rsp+0E8h+phUser]
0x18005a293  jmp     short loc_18005A2F3
0x18005a295  mov     r12d, [rsp+0E8h+phUser]
0x18005a29a  mov     rsi, rbx
0x18005a29d  test    edi, edi
0x18005a29f  js      short loc_18005A2F3
0x18005a2a1  lea     rax, [rsp+0E8h+var_94]
0x18005a2a6  mov     [rsp+0E8h+phIssuanceLicense], rax; phIssuanceLicense
0x18005a2ab  mov     [rsp+0E8h+hBoundLicense], ebx; hBoundLicense
0x18005a2af  mov     rax, [r13+0]
0x18005a2b3  mov     [rsp+0E8h+wszIssuanceLicense], rax; wszIssuanceLicense
0x18005a2b8  mov     [rsp+0E8h+hOwner], r12d; hOwner
0x18005a2bd  xor     r9d, r9d; wszReferralInfoURL
0x18005a2c0  xor     r8d, r8d; wszReferralInfoName
0x18005a2c3  xor     edx, edx; pstTimeUntil
0x18005a2c5  xor     ecx, ecx; pstTimeFrom
0x18005a2c7  call    DRMCreateIssuanceLicense
0x18005a2cc  mov     edi, eax
0x18005a2ce  test    eax, eax
0x18005a2d0  jns     short loc_18005A2EE
0x18005a2d2  mov     r9d, eax
0x18005a2d5  mov     r8d, 26Ch
0x18005a2db  lea     rdx, aMicrosoftInfor_14; "Microsoft::InformationProtection::CIrmD"...
0x18005a2e2  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005a2e9  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005a2ee  mov     r15d, [rsp+0E8h+var_94]
0x18005a2f3  xorps   xmm0, xmm0
0x18005a2f6  movups  xmmword ptr [rsp+0E8h+pguid.Data1], xmm0
0x18005a2fe  test    edi, edi
0x18005a300  js      short loc_18005A343
0x18005a302  lea     rcx, [rsp+0E8h+pguid]; pguid
0x18005a30a  call    cs:__imp_CoCreateGuid
0x18005a310  mov     edi, eax
0x18005a312  test    eax, eax
0x18005a314  jns     short loc_18005A321
0x18005a316  mov     r8d, 272h
0x18005a31c  jmp     loc_18005A44D
0x18005a321  mov     r8d, 27h ; '''; cchMax
0x18005a327  lea     rdx, [r14+18h]; lpsz
0x18005a32b  lea     rcx, [rsp+0E8h+pguid]; rguid
0x18005a333  call    cs:__imp_StringFromGUID2
0x18005a339  cmp     eax, 27h ; '''
0x18005a33c  jz      short loc_18005A389
0x18005a33e  mov     edi, 8000FFFFh
0x18005a343  mov     rcx, [r14+68h]; Block
0x18005a347  test    rcx, rcx
0x18005a34a  jz      short loc_18005A355
0x18005a34c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005a351  mov     [r14+68h], rbx
0x18005a355  test    rsi, rsi
0x18005a358  jz      short loc_18005A369
0x18005a35a  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005a35e  jz      short loc_18005A369
0x18005a360  mov     rcx, rsi; hObject
0x18005a363  call    cs:__imp_CloseHandle
0x18005a369  test    r12d, r12d
0x18005a36c  jz      short loc_18005A376
0x18005a36e  mov     ecx, r12d; hPub
0x18005a371  call    DRMClosePubHandle
0x18005a376  test    r15d, r15d
0x18005a379  jz      short loc_18005A384
0x18005a37b  mov     ecx, r15d; hPub
0x18005a37e  call    DRMClosePubHandle
0x18005a383  nop
0x18005a384  jmp     loc_18005A4A4
0x18005a389  mov     qword ptr [rsp+0E8h+hBoundLicense], rbx; wszContentName
0x18005a38e  lea     rax, wszContentType; "RMS Bulk Protected Document"
0x18005a395  mov     [rsp+0E8h+wszIssuanceLicense], rax; wszContentType
0x18005a39a  mov     qword ptr [rsp+0E8h+hOwner], rbx; wszSKUIdType
0x18005a39f  xor     r9d, r9d; wszSKUId
0x18005a3a2  lea     r8, wszContentIdType; "MS-GUID"
0x18005a3a9  lea     rdx, [r14+18h]; wszContentId
0x18005a3ad  mov     ecx, r15d; hIssuanceLicense
0x18005a3b0  call    DRMSetMetaData
0x18005a3b5  mov     edi, eax
0x18005a3b7  test    eax, eax
0x18005a3b9  jns     short loc_18005A3C6
0x18005a3bb  mov     r8d, 27Fh
0x18005a3c1  jmp     loc_18005A44D
0x18005a3c6  xor     r9d, r9d; lpName
0x18005a3c9  xor     r8d, r8d; bInitialState
0x18005a3cc  xor     edx, edx; bManualReset
0x18005a3ce  xor     ecx, ecx; lpEventAttributes
0x18005a3d0  call    cs:__imp_CreateEventW
0x18005a3d6  mov     rsi, rax
0x18005a3d9  test    rax, rax
0x18005a3dc  jnz     short loc_18005A3E8
0x18005a3de  mov     edi, 80004005h
0x18005a3e3  jmp     loc_18005A343
0x18005a3e8  mov     qword ptr [rsp+0E8h+var_88], r14
0x18005a3ed  mov     qword ptr [rsp+0E8h+var_88+8], rsi
0x18005a3f2  mov     dword ptr [rsp+0E8h+var_78], ebx
0x18005a3f6  lea     rax, [rsp+0E8h+var_88]
0x18005a3fb  mov     [rsp+0E8h+pvContext], rax; pvContext
0x18005a400  mov     [rsp+0E8h+wszURL], rbx; wszURL
0x18005a405  lea     rax, ?OnStatus@CIrmDocument@InformationProtection@Microsoft@@CAJW4_DRM_STATUS_MSG@@JPEAX1@Z; Microsoft::InformationProtection::CIrmDocument::OnStatus(_DRM_STATUS_MSG,long,void *,void *)
0x18005a40c  mov     [rsp+0E8h+phIssuanceLicense], rax; pfnCallback
0x18005a411  mov     rax, [rsp+0E8h+wszClientLicensorCertificate]
0x18005a419  mov     qword ptr [rsp+0E8h+hBoundLicense], rax; wszClientLicensorCertificate
0x18005a41e  lea     rax, wszSymKeyType; "AES"
0x18005a425  mov     [rsp+0E8h+wszIssuanceLicense], rax; wszSymKeyType
0x18005a42a  mov     [rsp+0E8h+hOwner], ebx; cbSymKey
0x18005a42e  xor     r9d, r9d; pbSymKey
0x18005a431  lea     r8d, [r9+32h]; uFlags
0x18005a435  mov     edx, r15d; hIssuanceLicense
0x18005a438  mov     ecx, [rsp+0E8h+hEnv]; hEnv
0x18005a43c  call    DRMGetSignedIssuanceLicense
0x18005a441  mov     edi, eax
0x18005a443  test    eax, eax
0x18005a445  jns     short loc_18005A468
0x18005a447  mov     r8d, 299h
0x18005a44d  mov     r9d, eax
0x18005a450  lea     rdx, aMicrosoftInfor_14; "Microsoft::InformationProtection::CIrmD"...
0x18005a457  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005a45e  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005a463  jmp     loc_18005A343
0x18005a468  mov     edx, 0EA60h; dwMilliseconds
0x18005a46d  mov     rcx, rsi; hHandle
0x18005a470  call    cs:__imp_WaitForSingleObject
0x18005a476  test    eax, eax
0x18005a478  jnz     loc_18005A3DE
0x18005a47e  cmp     dword ptr [rsp+0E8h+var_78], ebx
0x18005a482  jge     short loc_18005A490
0x18005a484  mov     edi, dword ptr [rsp+0E8h+var_78]
0x18005a488  test    edi, edi
0x18005a48a  js      loc_18005A343
0x18005a490  mov     edx, r15d; unsigned int
0x18005a493  mov     rcx, r14; this
0x18005a496  call    ?HrFetchOwnerLicense@CIrmDocument@InformationProtection@Microsoft@@AEAAJK@Z; Microsoft::InformationProtection::CIrmDocument::HrFetchOwnerLicense(ulong)
0x18005a49b  jmp     loc_18005A35A
0x18005a4a0  mov     edi, [rsp+0E8h+hEnv]
0x18005a4a4  test    edi, edi
0x18005a4a6  jns     short loc_18005A4C4
0x18005a4a8  mov     r9d, edi
0x18005a4ab  mov     r8d, 2BCh
0x18005a4b1  lea     rdx, aMicrosoftInfor_14; "Microsoft::InformationProtection::CIrmD"...
0x18005a4b8  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x18005a4bf  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x18005a4c4  mov     eax, edi
0x18005a4c6  mov     rcx, [rsp+0E8h+var_40]
0x18005a4ce  xor     rcx, rsp; StackCookie
0x18005a4d1  call    __security_check_cookie
0x18005a4d6  add     rsp, 0B0h
0x18005a4dd  pop     r15
0x18005a4df  pop     r14
0x18005a4e1  pop     r13
0x18005a4e3  pop     r12
0x18005a4e5  pop     rdi
0x18005a4e6  pop     rsi
0x18005a4e7  pop     rbx
0x18005a4e8  retn
```
