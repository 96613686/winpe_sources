# RdsDWMDirectSharedMemory::AddTermsrvACEToSectionObject(void *)

- ea: `0x180007b44`
- end: `0x180008051`
- name: `?AddTermsrvACEToSectionObject@RdsDWMDirectSharedMemory@@AEAAJPEAX@Z`
- size: `1293`
- prototype: `__int64 __fastcall(RdsDWMDirectSharedMemory *this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800088c0`

## callees

- `0x180001724`
- `0x180007b44`
- `0x18002b922`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007f5a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e31`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007d73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008012`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ff5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008004`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008012`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007d55`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180007d55`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007e8c`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180007e8c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007bd3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007bd3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008021`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180008021`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180007ee7`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180007ee7`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180007f4c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180007f4c`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180007cac`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180007cac`

## string_xrefs

- `0x180007c05`: `Failed to create the termsrv SID`
- `0x180007cde`: `Failed to get the old DACL.`
- `0x180007d9b`: `Failed to allocate a new ACL`
- `0x180007eba`: `Failed to copy the termsrv SID`
- `0x180007f7a`: `Failed to set the new DACL.`

## pseudocode

```c
__int64 __fastcall RdsDWMDirectSharedMemory::AddTermsrvACEToSectionObject(RdsDWMDirectSharedMemory *this, void *a2)
{
  void *v3; // rdi
  signed int LastError; // eax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // ebx
  signed int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  DWORD LengthSid; // r14d
  WORD v14; // bx
  struct _ACL *v15; // rax
  int v16; // r8d
  int v17; // r9d
  struct _ACL *v18; // rsi
  char *v19; // rax
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  const char *v23; // rax
  char *v24; // rdx
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  int v29; // [rsp+60h] [rbp-19h] BYREF
  int v30; // [rsp+64h] [rbp-15h] BYREF
  const char *v31; // [rsp+68h] [rbp-11h] BYREF
  const char *v32; // [rsp+70h] [rbp-9h] BYREF
  const char *v33; // [rsp+78h] [rbp-1h] BYREF
  const char *v34; // [rsp+80h] [rbp+7h] BYREF
  PSID pSourceSid; // [rsp+88h] [rbp+Fh] BYREF
  PACL ppDacl; // [rsp+90h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+98h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  ppDacl = 0;
  v3 = 0;
  ppSecurityDescriptor = 0;
  pSourceSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( !AllocateAndInitializeSid(
          &pIdentifierAuthority,
          6u,
          0x50u,
          0x1A963466u,
          0x5CF1AAB9u,
          0xF8123019,
          0x7448CE95u,
          0x304EFDA0u,
          0,
          0,
          &pSourceSid) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v29 = 186;
      v31 = "Failed to create the termsrv SID";
      v30 = v8;
      v32 = "AddTermsrvACEToSectionObject";
      v33 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      v34 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&dword_180038ABC,
        v6,
        v7,
        (__int64)&v34,
        (__int64)&v30,
        (__int64)&v33,
        (__int64)&v29,
        (__int64)&v32,
        (__int64)&v31);
    }
    goto LABEL_36;
  }
  if ( GetSecurityInfo(a2, SE_KERNEL_OBJECT, 4u, 0, 0, &ppDacl, 0, &ppSecurityDescriptor) )
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v30 = 198;
      v34 = "Failed to get the old DACL.";
      v29 = v8;
      v33 = "AddTermsrvACEToSectionObject";
      v32 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
      v31 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (unsigned int)&byte_180038A67,
        v11,
        v12,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v33,
        (__int64)&v34);
    }
    goto LABEL_36;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v14 = ppDacl->AclSize + LengthSid + 8;
  v15 = (struct _ACL *)LocalAlloc(0x40u, v14);
  v18 = v15;
  if ( v15 )
  {
    memcpy_0(v15, ppDacl, ppDacl->AclSize);
    v18->AclSize = v14;
    v19 = (char *)LocalAlloc(0x40u, (unsigned __int16)(LengthSid + 8));
    v3 = v19;
    if ( v19 )
    {
      *(_WORD *)v19 = 0;
      *((_WORD *)v19 + 1) = LengthSid + 8;
      *((_DWORD *)v19 + 1) = 6;
      if ( CopySid(LengthSid, v19 + 8, pSourceSid) )
      {
        if ( AddAce(v18, 2u, 0xFFFFFFFF, v3, (unsigned __int16)(LengthSid + 8)) )
        {
          v8 = 0;
          if ( !SetSecurityInfo(a2, SE_KERNEL_OBJECT, 4u, 0, 0, v18, 0) )
            goto LABEL_35;
          v27 = GetLastError();
          v8 = v27;
          if ( v27 > 0 )
            v8 = (unsigned __int16)v27 | 0x80070000;
          if ( (unsigned int)dword_180044008 <= 2 )
            goto LABEL_35;
          v23 = "Failed to set the new DACL.";
          v30 = 242;
          v24 = (char *)&word_1800388BE;
        }
        else
        {
          v26 = GetLastError();
          v8 = v26;
          if ( v26 > 0 )
            v8 = (unsigned __int16)v26 | 0x80070000;
          if ( (unsigned int)dword_180044008 <= 2 )
            goto LABEL_35;
          v23 = "Failed to add the termsrv ACE.";
          v30 = 233;
          v24 = byte_180038913;
        }
      }
      else
      {
        v25 = GetLastError();
        v8 = v25;
        if ( v25 > 0 )
          v8 = (unsigned __int16)v25 | 0x80070000;
        if ( (unsigned int)dword_180044008 <= 2 )
          goto LABEL_35;
        v23 = "Failed to copy the termsrv SID";
        v30 = 230;
        v24 = (char *)&unk_180038968;
      }
      v29 = v8;
    }
    else
    {
      v22 = -2147024882;
      v8 = -2147024882;
      if ( (unsigned int)dword_180044008 <= 2 )
      {
LABEL_35:
        LocalFree(v18);
        goto LABEL_36;
      }
      v23 = "Failed to allocate a new allow ACE.";
      v30 = 221;
      v29 = -2147024882;
      v24 = byte_1800389BD;
    }
    v34 = v23;
    v33 = "AddTermsrvACEToSectionObject";
    v32 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    v31 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v22,
      (_DWORD)v24,
      v20,
      v21,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v34);
    goto LABEL_35;
  }
  v8 = -2147024882;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    v30 = 210;
    v34 = "Failed to allocate a new ACL";
    v29 = -2147024882;
    v33 = "AddTermsrvACEToSectionObject";
    v32 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdrdriverio.cpp";
    v31 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024882,
      (unsigned int)word_180038A12,
      v16,
      v17,
      (__int64)&v31,
      (__int64)&v29,
      (__int64)&v32,
      (__int64)&v30,
      (__int64)&v33,
      (__int64)&v34);
  }
LABEL_36:
  if ( ppSecurityDescriptor )
    LocalFree(ppSecurityDescriptor);
  if ( v3 )
    LocalFree(v3);
  if ( pSourceSid )
    FreeSid(pSourceSid);
  return v8;
}

```

## disassembly

```asm
0x180007b44  mov     [rsp-8+arg_0], rbx
0x180007b49  mov     [rsp-8+arg_10], rsi
0x180007b4e  push    rbp
0x180007b4f  push    rdi
0x180007b50  push    r12
0x180007b52  push    r14
0x180007b54  push    r15
0x180007b56  lea     rbp, [rsp-37h]
0x180007b5b  sub     rsp, 0B0h
0x180007b62  mov     rax, cs:__security_cookie
0x180007b69  xor     rax, rsp
0x180007b6c  mov     [rbp+57h+var_28], rax
0x180007b70  xor     r12d, r12d
0x180007b73  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180007b79  lea     rax, [rbp+57h+pSourceSid]
0x180007b7d  mov     [rbp+57h+ppDacl], r12
0x180007b81  mov     [rsp+0D0h+pSid], rax; pSid
0x180007b86  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180007b8a  mov     [rsp+0D0h+nSubAuthority7], r12d; nSubAuthority7
0x180007b8f  mov     r15, rdx
0x180007b92  mov     [rsp+0D0h+nSubAuthority6], r12d; nSubAuthority6
0x180007b97  lea     r8d, [r12+50h]; nSubAuthority0
0x180007b9c  mov     [rsp+0D0h+nSubAuthority5], 304EFDA0h; nSubAuthority5
0x180007ba4  mov     r9d, 1A963466h; nSubAuthority1
0x180007baa  mov     [rsp+0D0h+nSubAuthority4], 7448CE95h; nSubAuthority4
0x180007bb2  mov     dl, 6; nSubAuthorityCount
0x180007bb4  mov     [rsp+0D0h+nSubAuthority3], 0F8123019h; nSubAuthority3
0x180007bbc  mov     edi, r12d
0x180007bbf  mov     [rsp+0D0h+nSubAuthority2], 5CF1AAB9h; nSubAuthority2
0x180007bc7  mov     [rbp+57h+ppSecurityDescriptor], r12
0x180007bcb  mov     [rbp+57h+pSourceSid], r12
0x180007bcf  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x180007bd3  call    cs:__imp_AllocateAndInitializeSid
0x180007bd9  test    eax, eax
0x180007bdb  jnz     loc_180007C82
0x180007be1  call    cs:__imp_GetLastError
0x180007be7  mov     ebx, eax
0x180007be9  test    eax, eax
0x180007beb  jle     short loc_180007BF6
0x180007bed  movzx   ebx, ax
0x180007bf0  or      ebx, 80070000h
0x180007bf6  mov     eax, cs:dword_180044008
0x180007bfc  cmp     eax, 2
0x180007bff  jbe     loc_180007FFB
0x180007c05  lea     rax, aFailedToCreate_9; "Failed to create the termsrv SID"
0x180007c0c  mov     [rbp+57h+var_70], 0BAh
0x180007c13  mov     [rbp+57h+var_68], rax
0x180007c17  lea     rdx, dword_180038ABC
0x180007c1e  lea     rax, aAddtermsrvacet; "AddTermsrvACEToSectionObject"
0x180007c25  mov     [rbp+57h+var_6C], ebx
0x180007c28  mov     [rbp+57h+var_60], rax
0x180007c2c  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180007c33  mov     [rbp+57h+var_58], rax
0x180007c37  lea     rax, aErrorCondition; "Error condition failed"
0x180007c3e  mov     [rbp+57h+var_50], rax
0x180007c42  lea     rax, [rbp+57h+var_68]
0x180007c46  mov     qword ptr [rsp+0D0h+nSubAuthority7], rax
0x180007c4b  lea     rax, [rbp+57h+var_60]
0x180007c4f  mov     qword ptr [rsp+0D0h+nSubAuthority6], rax
0x180007c54  lea     rax, [rbp+57h+var_70]
0x180007c58  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax
0x180007c5d  lea     rax, [rbp+57h+var_58]
0x180007c61  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180007c66  lea     rax, [rbp+57h+var_6C]
0x180007c6a  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180007c6f  lea     rax, [rbp+57h+var_50]
0x180007c73  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x180007c78  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180007c7d  jmp     loc_180007FFB
0x180007c82  xor     r9d, r9d; ppsidOwner
0x180007c85  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x180007c89  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax; ppSecurityDescriptor
0x180007c8e  mov     rcx, r15; handle
0x180007c91  lea     rax, [rbp+57h+ppDacl]
0x180007c95  mov     qword ptr [rsp+0D0h+nSubAuthority4], r12; ppSacl
0x180007c9a  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax; ppDacl
0x180007c9f  lea     edx, [r9+6]; ObjectType
0x180007ca3  mov     qword ptr [rsp+0D0h+nSubAuthority2], r12; ppsidGroup
0x180007ca8  lea     r8d, [r9+4]; SecurityInfo
0x180007cac  call    cs:__imp_GetSecurityInfo
0x180007cb2  test    eax, eax
0x180007cb4  jz      loc_180007D51
0x180007cba  call    cs:__imp_GetLastError
0x180007cc0  mov     ebx, eax
0x180007cc2  test    eax, eax
0x180007cc4  jle     short loc_180007CCF
0x180007cc6  movzx   ebx, ax
0x180007cc9  or      ebx, 80070000h
0x180007ccf  mov     eax, cs:dword_180044008
0x180007cd5  cmp     eax, 2
0x180007cd8  jbe     loc_180007FFB
0x180007cde  lea     rax, aFailedToGetThe; "Failed to get the old DACL."
0x180007ce5  mov     [rbp+57h+var_6C], 0C6h
0x180007cec  mov     [rbp+57h+var_50], rax
0x180007cf0  lea     rdx, byte_180038A67
0x180007cf7  lea     rax, aAddtermsrvacet; "AddTermsrvACEToSectionObject"
0x180007cfe  mov     [rbp+57h+var_70], ebx
0x180007d01  mov     [rbp+57h+var_58], rax
0x180007d05  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180007d0c  mov     [rbp+57h+var_60], rax
0x180007d10  lea     rax, aErrorCondition; "Error condition failed"
0x180007d17  mov     [rbp+57h+var_68], rax
0x180007d1b  lea     rax, [rbp+57h+var_50]
0x180007d1f  mov     qword ptr [rsp+0D0h+nSubAuthority7], rax
0x180007d24  lea     rax, [rbp+57h+var_58]
0x180007d28  mov     qword ptr [rsp+0D0h+nSubAuthority6], rax
0x180007d2d  lea     rax, [rbp+57h+var_6C]
0x180007d31  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax
0x180007d36  lea     rax, [rbp+57h+var_60]
0x180007d3a  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180007d3f  lea     rax, [rbp+57h+var_70]
0x180007d43  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180007d48  lea     rax, [rbp+57h+var_68]
0x180007d4c  jmp     loc_180007C73
0x180007d51  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x180007d55  call    cs:__imp_GetLengthSid
0x180007d5b  mov     rcx, [rbp+57h+ppDacl]
0x180007d5f  mov     r14d, eax
0x180007d62  lea     edx, [rax+8]
0x180007d65  add     dx, [rcx+2]
0x180007d69  mov     ecx, 40h ; '@'; uFlags
0x180007d6e  movzx   ebx, dx
0x180007d71  mov     edx, ebx; uBytes
0x180007d73  call    cs:__imp_LocalAlloc
0x180007d79  mov     rsi, rax
0x180007d7c  test    rax, rax
0x180007d7f  jnz     loc_180007E0E
0x180007d85  mov     eax, cs:dword_180044008
0x180007d8b  mov     ecx, 8007000Eh
0x180007d90  mov     ebx, ecx
0x180007d92  cmp     eax, 2
0x180007d95  jbe     loc_180007FFB
0x180007d9b  lea     rax, aFailedToAlloca; "Failed to allocate a new ACL"
0x180007da2  mov     [rbp+57h+var_6C], 0D2h
0x180007da9  mov     [rbp+57h+var_50], rax
0x180007dad  lea     rdx, word_180038A12
0x180007db4  lea     rax, aAddtermsrvacet; "AddTermsrvACEToSectionObject"
0x180007dbb  mov     [rbp+57h+var_70], ecx
0x180007dbe  mov     [rbp+57h+var_58], rax
0x180007dc2  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180007dc9  mov     [rbp+57h+var_60], rax
0x180007dcd  lea     rax, aErrorCondition; "Error condition failed"
0x180007dd4  mov     [rbp+57h+var_68], rax
0x180007dd8  lea     rax, [rbp+57h+var_50]
0x180007ddc  mov     qword ptr [rsp+0D0h+nSubAuthority7], rax
0x180007de1  lea     rax, [rbp+57h+var_58]
0x180007de5  mov     qword ptr [rsp+0D0h+nSubAuthority6], rax
0x180007dea  lea     rax, [rbp+57h+var_6C]
0x180007dee  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax
0x180007df3  lea     rax, [rbp+57h+var_60]
0x180007df7  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180007dfc  lea     rax, [rbp+57h+var_70]
0x180007e00  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180007e05  lea     rax, [rbp+57h+var_68]
0x180007e09  jmp     loc_180007C73
0x180007e0e  mov     rdx, [rbp+57h+ppDacl]; Src
0x180007e12  mov     rcx, rsi; void *
0x180007e15  movzx   r8d, word ptr [rdx+2]; Size
0x180007e1a  call    memcpy_0
0x180007e1f  lea     eax, [r14+8]
0x180007e23  mov     [rsi+2], bx
0x180007e27  movzx   ebx, ax
0x180007e2a  mov     ecx, 40h ; '@'; uFlags
0x180007e2f  mov     edx, ebx; uBytes
0x180007e31  call    cs:__imp_LocalAlloc
0x180007e37  mov     rdi, rax
0x180007e3a  test    rax, rax
0x180007e3d  jnz     short loc_180007E72
0x180007e3f  mov     eax, cs:dword_180044008
0x180007e45  mov     ecx, 8007000Eh
0x180007e4a  mov     ebx, ecx
0x180007e4c  cmp     eax, 2
0x180007e4f  jbe     loc_180007FF2
0x180007e55  lea     rax, aFailedToAlloca_1; "Failed to allocate a new allow ACE."
0x180007e5c  mov     [rbp+57h+var_6C], 0DDh
0x180007e63  mov     [rbp+57h+var_70], ecx
0x180007e66  lea     rdx, byte_1800389BD
0x180007e6d  jmp     loc_180007F92
0x180007e72  mov     [rax], r12w
0x180007e76  lea     rdx, [rax+8]; pDestinationSid
0x180007e7a  mov     [rax+2], bx
0x180007e7e  mov     ecx, r14d; nDestinationSidLength
0x180007e81  mov     dword ptr [rax+4], 6
0x180007e88  mov     r8, [rbp+57h+pSourceSid]; pSourceSid
0x180007e8c  call    cs:__imp_CopySid
0x180007e92  test    eax, eax
0x180007e94  jnz     short loc_180007ED4
0x180007e96  call    cs:__imp_GetLastError
0x180007e9c  mov     ebx, eax
0x180007e9e  test    eax, eax
0x180007ea0  jle     short loc_180007EAB
0x180007ea2  movzx   ebx, ax
0x180007ea5  or      ebx, 80070000h
0x180007eab  mov     eax, cs:dword_180044008
0x180007eb1  cmp     eax, 2
0x180007eb4  jbe     loc_180007FF2
0x180007eba  lea     rax, aFailedToCopyTh; "Failed to copy the termsrv SID"
0x180007ec1  mov     [rbp+57h+var_6C], 0E6h
0x180007ec8  lea     rdx, unk_180038968
0x180007ecf  jmp     loc_180007F8F
0x180007ed4  mov     r9, rdi; pAceList
0x180007ed7  mov     [rsp+0D0h+nSubAuthority2], ebx; nAceListLength
0x180007edb  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180007edf  mov     edx, 2; dwAceRevision
0x180007ee4  mov     rcx, rsi; pAcl
0x180007ee7  call    cs:__imp_AddAce
0x180007eed  test    eax, eax
0x180007eef  jnz     short loc_180007F2C
0x180007ef1  call    cs:__imp_GetLastError
0x180007ef7  mov     ebx, eax
0x180007ef9  test    eax, eax
0x180007efb  jle     short loc_180007F06
0x180007efd  movzx   ebx, ax
0x180007f00  or      ebx, 80070000h
0x180007f06  mov     eax, cs:dword_180044008
0x180007f0c  cmp     eax, 2
0x180007f0f  jbe     loc_180007FF2
0x180007f15  lea     rax, aFailedToAddThe_0; "Failed to add the termsrv ACE."
0x180007f1c  mov     [rbp+57h+var_6C], 0E9h
0x180007f23  lea     rdx, byte_180038913
0x180007f2a  jmp     short loc_180007F8F
0x180007f2c  xor     r9d, r9d; psidOwner
0x180007f2f  mov     qword ptr [rsp+0D0h+nSubAuthority4], r12; pSacl
0x180007f34  mov     qword ptr [rsp+0D0h+nSubAuthority3], rsi; pDacl
0x180007f39  mov     rcx, r15; handle
0x180007f3c  mov     ebx, r12d
0x180007f3f  mov     qword ptr [rsp+0D0h+nSubAuthority2], r12; psidGroup
0x180007f44  lea     edx, [r9+6]; ObjectType
0x180007f48  lea     r8d, [r9+4]; SecurityInfo
0x180007f4c  call    cs:__imp_SetSecurityInfo
0x180007f52  test    eax, eax
0x180007f54  jz      loc_180007FF2
0x180007f5a  call    cs:__imp_GetLastError
0x180007f60  mov     ebx, eax
0x180007f62  test    eax, eax
0x180007f64  jle     short loc_180007F6F
0x180007f66  movzx   ebx, ax
0x180007f69  or      ebx, 80070000h
0x180007f6f  mov     eax, cs:dword_180044008
0x180007f75  cmp     eax, 2
0x180007f78  jbe     short loc_180007FF2
0x180007f7a  lea     rax, aFailedToSetThe; "Failed to set the new DACL."
0x180007f81  mov     [rbp+57h+var_6C], 0F2h
0x180007f88  lea     rdx, word_1800388BE
0x180007f8f  mov     [rbp+57h+var_70], ebx
0x180007f92  mov     [rbp+57h+var_50], rax
0x180007f96  lea     rax, aAddtermsrvacet; "AddTermsrvACEToSectionObject"
0x180007f9d  mov     [rbp+57h+var_58], rax
0x180007fa1  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180007fa8  mov     [rbp+57h+var_60], rax
0x180007fac  lea     rax, aErrorCondition; "Error condition failed"
0x180007fb3  mov     [rbp+57h+var_68], rax
0x180007fb7  lea     rax, [rbp+57h+var_50]
0x180007fbb  mov     qword ptr [rsp+0D0h+nSubAuthority7], rax
0x180007fc0  lea     rax, [rbp+57h+var_58]
0x180007fc4  mov     qword ptr [rsp+0D0h+nSubAuthority6], rax
0x180007fc9  lea     rax, [rbp+57h+var_6C]
0x180007fcd  mov     qword ptr [rsp+0D0h+nSubAuthority5], rax
0x180007fd2  lea     rax, [rbp+57h+var_60]
0x180007fd6  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax
0x180007fdb  lea     rax, [rbp+57h+var_70]
0x180007fdf  mov     qword ptr [rsp+0D0h+nSubAuthority3], rax
0x180007fe4  lea     rax, [rbp+57h+var_68]
0x180007fe8  mov     qword ptr [rsp+0D0h+nSubAuthority2], rax
0x180007fed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180007ff2  mov     rcx, rsi; hMem
0x180007ff5  call    cs:__imp_LocalFree
0x180007ffb  mov     rcx, [rbp+57h+ppSecurityDescriptor]; hMem
0x180007fff  test    rcx, rcx
0x180008002  jz      short loc_18000800A
0x180008004  call    cs:__imp_LocalFree
0x18000800a  test    rdi, rdi
0x18000800d  jz      short loc_180008018
0x18000800f  mov     rcx, rdi; hMem
0x180008012  call    cs:__imp_LocalFree
0x180008018  mov     rcx, [rbp+57h+pSourceSid]; pSid
0x18000801c  test    rcx, rcx
0x18000801f  jz      short loc_180008027
0x180008021  call    cs:__imp_FreeSid
0x180008027  mov     eax, ebx
0x180008029  mov     rcx, [rbp+57h+var_28]
0x18000802d  xor     rcx, rsp; StackCookie
0x180008030  call    __security_check_cookie
0x180008035  lea     r11, [rsp+0D0h+var_20]
0x18000803d  mov     rbx, [r11+30h]
0x180008041  mov     rsi, [r11+40h]
0x180008045  mov     rsp, r11
0x180008048  pop     r15
0x18000804a  pop     r14
0x18000804c  pop     r12
0x18000804e  pop     rdi
0x18000804f  pop     rbp
0x180008050  retn
```
