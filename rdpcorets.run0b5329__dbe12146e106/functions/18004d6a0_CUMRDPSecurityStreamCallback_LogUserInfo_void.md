# CUMRDPSecurityStreamCallback::LogUserInfo(void *)

- ea: `0x18004d6a0`
- end: `0x18004dd8c`
- name: `?LogUserInfo@CUMRDPSecurityStreamCallback@@AEBAXPEAX@Z`
- size: `1772`
- prototype: `void(CUMRDPSecurityStreamCallback *__hidden this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180046180`

## callees

- `0x1800014d8`
- `0x18000222c`
- `0x180002338`
- `0x18003394c`
- `0x180033958`
- `0x180033da0`
- `0x18004d6a0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d92d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004db54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004dbe9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004dd4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004dd4b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004d9ba`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004da81`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004d9ba`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004da81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004dd2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004dd3c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004dd2d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004dd3c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d720`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d85e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d720`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d85e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004db1a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004dbb3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004db1a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004dbb3`
- `OLEAUT32!__imp_SysAllocString` at `0x18004dc9e`
- `OLEAUT32!__imp_SysAllocString` at `0x18004dc9e`
- `OLEAUT32!__imp_VariantInit` at `0x18004d704`
- `OLEAUT32!__imp_VariantInit` at `0x18004d704`
- `OLEAUT32!__imp_VariantClear` at `0x18004dd62`
- `OLEAUT32!__imp_VariantClear` at `0x18004dd62`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d8f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004d8f3`

## string_xrefs

- `0x18004dd11`: `ActualUserSid`
- `0x18004d782`: `GetTokenInformation failed!`
- `0x18004d8b4`: `GetTokenInformation failed!`
- `0x18004d949`: `ConvertSidToStringSid failed!`
- `0x18004da10`: `AllocateAndInitializeSid(RDU) failed!`
- `0x18004dad7`: `AllocateAndInitializeSid(Administrators) failed!`
- `0x18004db70`: `CheckTokenMembership(RDU) failed!`
- `0x18004dc05`: `CheckTokenMembership(Administrators) failed!`
- `0x18004dcb8`: `SysAllocString(pwszUserSid) failed!`

## pseudocode

```c
void __fastcall CUMRDPSecurityStreamCallback::LogUserInfo(CUMRDPSecurityStreamCallback *this, void *a2)
{
  signed int v4; // eax
  int v5; // r8d
  int v6; // r9d
  PSID *v7; // rbx
  int v8; // r8d
  int v9; // r9d
  signed int v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  signed int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  signed int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  signed int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  signed int v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  signed int LastError; // eax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  WINBOOL v39; // [rsp+60h] [rbp-29h] BYREF
  WINBOOL v40; // [rsp+64h] [rbp-25h] BYREF
  const char *v41; // [rsp+68h] [rbp-21h] BYREF
  const char *v42; // [rsp+70h] [rbp-19h] BYREF
  const char *v43; // [rsp+78h] [rbp-11h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp-9h] BYREF
  WINBOOL v45; // [rsp+84h] [rbp-5h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp-1h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp+7h] BYREF
  PSID pSid; // [rsp+98h] [rbp+Fh] BYREF
  PSID SidToCheck; // [rsp+A0h] [rbp+17h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp+37h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  TokenInformationLength = 0;
  StringSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  pSid = 0;
  IsMember = 0;
  v45 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &TokenInformationLength) || (v4 = GetLastError(), v4 == 122) )
  {
    v7 = (PSID *)operator new[](TokenInformationLength);
    if ( v7 )
    {
      if ( GetTokenInformation(a2, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v7, &StringSid) )
        {
          if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Bu, 0, 0, 0, 0, 0, 0, &SidToCheck) )
          {
            if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pSid) )
            {
              if ( CheckTokenMembership(a2, SidToCheck, &IsMember) )
              {
                if ( CheckTokenMembership(a2, pSid, &v45) )
                {
                  if ( (unsigned int)dword_1801B76C8 > 4 )
                  {
                    v40 = v45;
                    v39 = IsMember;
                    v42 = (const char *)StringSid;
                    v41 = "Connected user information";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                      v30,
                      (unsigned int)byte_180191B1B,
                      v31,
                      v32,
                      (__int64)&v41,
                      (__int64)&v42,
                      (__int64)&v39,
                      (__int64)&v40);
                  }
                  pvarg.vt = 8;
                  pvarg.llVal = (LONGLONG)SysAllocString(StringSid);
                  if ( pvarg.llVal )
                    goto LABEL_47;
                  if ( (unsigned int)dword_1801B76C8 > 3 )
                  {
                    v41 = "SysAllocString(pwszUserSid) failed!";
                    v42 = "LogUserInfo";
                    v43 = "Condition failed but continue";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      (unsigned int)"LogUserInfo",
                      (unsigned int)&dword_180191AE4,
                      v37,
                      v38,
                      (__int64)&v43,
                      (__int64)&v41,
                      (__int64)&v42);
                  }
                  if ( pvarg.llVal )
LABEL_47:
                    (*(void (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 12) + 56LL))(
                      *((_QWORD *)this + 12),
                      L"ActualUserSid",
                      &pvarg);
                }
                else if ( (unsigned int)dword_1801B76C8 > 2 )
                {
                  v40 = 7930;
                  v42 = "LogUserInfo";
                  v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                  LastError = GetLastError();
                  if ( LastError > 0 )
                    LastError = (unsigned __int16)LastError | 0x80070000;
                  v39 = LastError;
                  v43 = "CheckTokenMembership(Administrators) failed!";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v34,
                    (unsigned int)&byte_180191B5F,
                    v35,
                    v36,
                    (__int64)&v43,
                    (__int64)&v39,
                    (__int64)&v41,
                    (__int64)&v40,
                    (__int64)&v42);
                }
              }
              else if ( (unsigned int)dword_1801B76C8 > 2 )
              {
                v40 = 7920;
                v42 = "LogUserInfo";
                v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
                v26 = GetLastError();
                if ( v26 > 0 )
                  v26 = (unsigned __int16)v26 | 0x80070000;
                v39 = v26;
                v43 = "CheckTokenMembership(RDU) failed!";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v27,
                  (unsigned int)qword_180191BA8,
                  v28,
                  v29,
                  (__int64)&v43,
                  (__int64)&v39,
                  (__int64)&v41,
                  (__int64)&v40,
                  (__int64)&v42);
              }
            }
            else if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              v40 = 7910;
              v42 = "LogUserInfo";
              v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
              v22 = GetLastError();
              if ( v22 > 0 )
                v22 = (unsigned __int16)v22 | 0x80070000;
              v39 = v22;
              v43 = "AllocateAndInitializeSid(Administrators) failed!";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v23,
                (unsigned int)byte_180191BF1,
                v24,
                v25,
                (__int64)&v43,
                (__int64)&v39,
                (__int64)&v41,
                (__int64)&v40,
                (__int64)&v42);
            }
          }
          else if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v40 = 7897;
            v42 = "LogUserInfo";
            v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
            v18 = GetLastError();
            if ( v18 > 0 )
              v18 = (unsigned __int16)v18 | 0x80070000;
            v39 = v18;
            v43 = "AllocateAndInitializeSid(RDU) failed!";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v19,
              (unsigned int)word_180191C3A,
              v20,
              v21,
              (__int64)&v43,
              (__int64)&v39,
              (__int64)&v41,
              (__int64)&v40,
              (__int64)&v42);
          }
        }
        else if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v40 = 7884;
          v42 = "LogUserInfo";
          v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
          v14 = GetLastError();
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v39 = v14;
          v43 = "ConvertSidToStringSid failed!";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)byte_180191C83,
            v16,
            v17,
            (__int64)&v43,
            (__int64)&v39,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v42);
        }
      }
      else if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v40 = 7878;
        v42 = "LogUserInfo";
        v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
        v10 = GetLastError();
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v39 = v10;
        v43 = "GetTokenInformation failed!";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&dword_180191CCC,
          v12,
          v13,
          (__int64)&v43,
          (__int64)&v39,
          (__int64)&v41,
          (__int64)&v40,
          (__int64)&v42);
      }
    }
    else if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v40 = 7866;
      v43 = "memory allocation failed!";
      v42 = "LogUserInfo";
      v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      v39 = -2147024882;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp",
        (unsigned int)byte_180191D15,
        v8,
        v9,
        (__int64)&v43,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v42);
    }
  }
  else
  {
    v7 = 0;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v39 = 7858;
      v43 = "LogUserInfo";
      v41 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v40 = v4;
      v42 = "GetTokenInformation failed!";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)"clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp",
        (unsigned int)&word_180191D5E,
        v5,
        v6,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)&v43);
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v7 )
    operator delete(v7);
  VariantClear(&pvarg);
}

```

## disassembly

```asm
0x18004d6a0  mov     [rsp-8+arg_10], rbx
0x18004d6a5  mov     [rsp-8+arg_18], rsi
0x18004d6aa  push    rbp
0x18004d6ab  push    rdi
0x18004d6ac  push    r14
0x18004d6ae  lea     rbp, [rsp-47h]
0x18004d6b3  sub     rsp, 0D0h
0x18004d6ba  mov     rax, cs:__security_cookie
0x18004d6c1  xor     rax, rsp
0x18004d6c4  mov     [rbp+57h+var_18], rax
0x18004d6c8  xor     r14d, r14d
0x18004d6cb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18004d6d1  mov     rsi, rcx
0x18004d6d4  mov     [rbp+57h+TokenInformationLength], r14d
0x18004d6d8  xorps   xmm0, xmm0
0x18004d6db  mov     [rbp+57h+StringSid], r14
0x18004d6df  xor     eax, eax
0x18004d6e1  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18004d6e5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18004d6e9  mov     [rbp+57h+SidToCheck], r14
0x18004d6ed  mov     [rbp+57h+var_48], r14
0x18004d6f1  mov     rdi, rdx
0x18004d6f4  mov     [rbp+57h+IsMember], r14d
0x18004d6f8  mov     [rbp+57h+var_5C], r14d
0x18004d6fc  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18004d700  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18004d704  call    cs:__imp_VariantInit
0x18004d70a  lea     rax, [rbp+57h+TokenInformationLength]
0x18004d70e  xor     r9d, r9d; TokenInformationLength
0x18004d711  xor     r8d, r8d; TokenInformation
0x18004d714  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18004d719  lea     edx, [r14+1]; TokenInformationClass
0x18004d71d  mov     rcx, rdi; TokenHandle
0x18004d720  call    cs:__imp_GetTokenInformation
0x18004d726  test    eax, eax
0x18004d728  jnz     loc_18004D7C4
0x18004d72e  call    cs:__imp_GetLastError
0x18004d734  cmp     eax, 7Ah ; 'z'
0x18004d737  jz      loc_18004D7C4
0x18004d73d  mov     ecx, cs:dword_1801B76C8
0x18004d743  mov     ebx, r14d
0x18004d746  cmp     ecx, 2
0x18004d749  jbe     loc_18004DD24
0x18004d74f  mov     [rbp+57h+var_80], 1EB2h
0x18004d756  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004d75d  mov     [rbp+57h+var_68], rcx
0x18004d761  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004d768  mov     [rbp+57h+var_78], rcx
0x18004d76c  test    eax, eax
0x18004d76e  jle     short loc_18004D778
0x18004d770  movzx   eax, ax
0x18004d773  or      eax, 80070000h
0x18004d778  mov     [rbp+57h+var_7C], eax
0x18004d77b  lea     rdx, word_180191D5E
0x18004d782  lea     rax, aGettokeninform_0; "GetTokenInformation failed!"
0x18004d789  mov     [rbp+57h+var_70], rax
0x18004d78d  lea     rax, [rbp+57h+var_68]
0x18004d791  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004d796  lea     rax, [rbp+57h+var_80]
0x18004d79a  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004d79f  lea     rax, [rbp+57h+var_78]
0x18004d7a3  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004d7a8  lea     rax, [rbp+57h+var_7C]
0x18004d7ac  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004d7b1  lea     rax, [rbp+57h+var_70]
0x18004d7b5  mov     [rsp+0E0h+ReturnLength], rax
0x18004d7ba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18004d7bf  jmp     loc_18004DD24
0x18004d7c4  mov     ecx, [rbp+57h+TokenInformationLength]; unsigned __int64
0x18004d7c7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004d7cc  mov     rbx, rax
0x18004d7cf  test    rax, rax
0x18004d7d2  jnz     short loc_18004D846
0x18004d7d4  mov     eax, cs:dword_1801B76C8
0x18004d7da  cmp     eax, 2
0x18004d7dd  jbe     loc_18004DD24
0x18004d7e3  lea     rax, aMemoryAllocati_0; "memory allocation failed!"
0x18004d7ea  mov     [rbp+57h+var_7C], 1EBAh
0x18004d7f1  mov     [rbp+57h+var_68], rax
0x18004d7f5  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004d7fc  lea     rax, [rbp+57h+var_70]
0x18004d800  mov     [rbp+57h+var_70], rcx
0x18004d804  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004d809  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004d810  lea     rax, [rbp+57h+var_7C]
0x18004d814  mov     [rbp+57h+var_78], rcx
0x18004d818  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004d81d  lea     rdx, byte_180191D15
0x18004d824  lea     rax, [rbp+57h+var_78]
0x18004d828  mov     [rbp+57h+var_80], 8007000Eh
0x18004d82f  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004d834  lea     rax, [rbp+57h+var_80]
0x18004d838  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004d83d  lea     rax, [rbp+57h+var_68]
0x18004d841  jmp     loc_18004D7B5
0x18004d846  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18004d84a  lea     rax, [rbp+57h+TokenInformationLength]
0x18004d84e  mov     r8, rbx; TokenInformation
0x18004d851  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x18004d856  mov     edx, 1; TokenInformationClass
0x18004d85b  mov     rcx, rdi; TokenHandle
0x18004d85e  call    cs:__imp_GetTokenInformation
0x18004d864  test    eax, eax
0x18004d866  jnz     loc_18004D8EC
0x18004d86c  mov     eax, cs:dword_1801B76C8
0x18004d872  cmp     eax, 2
0x18004d875  jbe     loc_18004DD24
0x18004d87b  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004d882  mov     [rbp+57h+var_7C], 1EC6h
0x18004d889  mov     [rbp+57h+var_70], rcx
0x18004d88d  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004d894  mov     [rbp+57h+var_78], rcx
0x18004d898  call    cs:__imp_GetLastError
0x18004d89e  test    eax, eax
0x18004d8a0  jle     short loc_18004D8AA
0x18004d8a2  movzx   eax, ax
0x18004d8a5  or      eax, 80070000h
0x18004d8aa  mov     [rbp+57h+var_80], eax
0x18004d8ad  lea     rdx, dword_180191CCC
0x18004d8b4  lea     rax, aGettokeninform_0; "GetTokenInformation failed!"
0x18004d8bb  mov     [rbp+57h+var_68], rax
0x18004d8bf  lea     rax, [rbp+57h+var_70]
0x18004d8c3  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004d8c8  lea     rax, [rbp+57h+var_7C]
0x18004d8cc  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004d8d1  lea     rax, [rbp+57h+var_78]
0x18004d8d5  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004d8da  lea     rax, [rbp+57h+var_80]
0x18004d8de  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004d8e3  lea     rax, [rbp+57h+var_68]
0x18004d8e7  jmp     loc_18004D7B5
0x18004d8ec  mov     rcx, [rbx]; Sid
0x18004d8ef  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18004d8f3  call    cs:__imp_ConvertSidToStringSidW
0x18004d8f9  test    eax, eax
0x18004d8fb  jnz     loc_18004D981
0x18004d901  mov     eax, cs:dword_1801B76C8
0x18004d907  cmp     eax, 2
0x18004d90a  jbe     loc_18004DD24
0x18004d910  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004d917  mov     [rbp+57h+var_7C], 1ECCh
0x18004d91e  mov     [rbp+57h+var_70], rcx
0x18004d922  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004d929  mov     [rbp+57h+var_78], rcx
0x18004d92d  call    cs:__imp_GetLastError
0x18004d933  test    eax, eax
0x18004d935  jle     short loc_18004D93F
0x18004d937  movzx   eax, ax
0x18004d93a  or      eax, 80070000h
0x18004d93f  mov     [rbp+57h+var_80], eax
0x18004d942  lea     rdx, byte_180191C83
0x18004d949  lea     rax, aConvertsidtost_0; "ConvertSidToStringSid failed!"
0x18004d950  mov     [rbp+57h+var_68], rax
0x18004d954  lea     rax, [rbp+57h+var_70]
0x18004d958  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004d95d  lea     rax, [rbp+57h+var_7C]
0x18004d961  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004d966  lea     rax, [rbp+57h+var_78]
0x18004d96a  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004d96f  lea     rax, [rbp+57h+var_80]
0x18004d973  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004d978  lea     rax, [rbp+57h+var_68]
0x18004d97c  jmp     loc_18004D7B5
0x18004d981  lea     rax, [rbp+57h+SidToCheck]
0x18004d985  mov     r9d, 22Bh; nSubAuthority1
0x18004d98b  mov     [rsp+0E0h+pSid], rax; pSid
0x18004d990  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004d994  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18004d999  mov     r8d, 20h ; ' '; nSubAuthority0
0x18004d99f  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18004d9a4  mov     dl, 2; nSubAuthorityCount
0x18004d9a6  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18004d9ab  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18004d9b0  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18004d9b5  mov     dword ptr [rsp+0E0h+ReturnLength], r14d; nSubAuthority2
0x18004d9ba  call    cs:__imp_AllocateAndInitializeSid
0x18004d9c0  test    eax, eax
0x18004d9c2  jnz     loc_18004DA48
0x18004d9c8  mov     eax, cs:dword_1801B76C8
0x18004d9ce  cmp     eax, 2
0x18004d9d1  jbe     loc_18004DD24
0x18004d9d7  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004d9de  mov     [rbp+57h+var_7C], 1ED9h
0x18004d9e5  mov     [rbp+57h+var_70], rcx
0x18004d9e9  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004d9f0  mov     [rbp+57h+var_78], rcx
0x18004d9f4  call    cs:__imp_GetLastError
0x18004d9fa  test    eax, eax
0x18004d9fc  jle     short loc_18004DA06
0x18004d9fe  movzx   eax, ax
0x18004da01  or      eax, 80070000h
0x18004da06  mov     [rbp+57h+var_80], eax
0x18004da09  lea     rdx, word_180191C3A
0x18004da10  lea     rax, aAllocateandini_1; "AllocateAndInitializeSid(RDU) failed!"
0x18004da17  mov     [rbp+57h+var_68], rax
0x18004da1b  lea     rax, [rbp+57h+var_70]
0x18004da1f  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004da24  lea     rax, [rbp+57h+var_7C]
0x18004da28  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004da2d  lea     rax, [rbp+57h+var_78]
0x18004da31  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004da36  lea     rax, [rbp+57h+var_80]
0x18004da3a  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004da3f  lea     rax, [rbp+57h+var_68]
0x18004da43  jmp     loc_18004D7B5
0x18004da48  lea     rax, [rbp+57h+var_48]
0x18004da4c  mov     r9d, 220h; nSubAuthority1
0x18004da52  mov     [rsp+0E0h+pSid], rax; pSid
0x18004da57  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004da5b  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18004da60  mov     r8d, 20h ; ' '; nSubAuthority0
0x18004da66  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18004da6b  mov     dl, 2; nSubAuthorityCount
0x18004da6d  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18004da72  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18004da77  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18004da7c  mov     dword ptr [rsp+0E0h+ReturnLength], r14d; nSubAuthority2
0x18004da81  call    cs:__imp_AllocateAndInitializeSid
0x18004da87  test    eax, eax
0x18004da89  jnz     loc_18004DB0F
0x18004da8f  mov     eax, cs:dword_1801B76C8
0x18004da95  cmp     eax, 2
0x18004da98  jbe     loc_18004DD24
0x18004da9e  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004daa5  mov     [rbp+57h+var_7C], 1EE6h
0x18004daac  mov     [rbp+57h+var_70], rcx
0x18004dab0  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004dab7  mov     [rbp+57h+var_78], rcx
0x18004dabb  call    cs:__imp_GetLastError
0x18004dac1  test    eax, eax
0x18004dac3  jle     short loc_18004DACD
0x18004dac5  movzx   eax, ax
0x18004dac8  or      eax, 80070000h
0x18004dacd  mov     [rbp+57h+var_80], eax
0x18004dad0  lea     rdx, byte_180191BF1
0x18004dad7  lea     rax, aAllocateandini; "AllocateAndInitializeSid(Administrators"...
0x18004dade  mov     [rbp+57h+var_68], rax
0x18004dae2  lea     rax, [rbp+57h+var_70]
0x18004dae6  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004daeb  lea     rax, [rbp+57h+var_7C]
0x18004daef  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004daf4  lea     rax, [rbp+57h+var_78]
0x18004daf8  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004dafd  lea     rax, [rbp+57h+var_80]
0x18004db01  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004db06  lea     rax, [rbp+57h+var_68]
0x18004db0a  jmp     loc_18004D7B5
0x18004db0f  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18004db13  lea     r8, [rbp+57h+IsMember]; IsMember
0x18004db17  mov     rcx, rdi; TokenHandle
0x18004db1a  call    cs:__imp_CheckTokenMembership
0x18004db20  test    eax, eax
0x18004db22  jnz     loc_18004DBA8
0x18004db28  mov     eax, cs:dword_1801B76C8
0x18004db2e  cmp     eax, 2
0x18004db31  jbe     loc_18004DD24
0x18004db37  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004db3e  mov     [rbp+57h+var_7C], 1EF0h
0x18004db45  mov     [rbp+57h+var_70], rcx
0x18004db49  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004db50  mov     [rbp+57h+var_78], rcx
0x18004db54  call    cs:__imp_GetLastError
0x18004db5a  test    eax, eax
0x18004db5c  jle     short loc_18004DB66
0x18004db5e  movzx   eax, ax
0x18004db61  or      eax, 80070000h
0x18004db66  mov     [rbp+57h+var_80], eax
0x18004db69  lea     rdx, qword_180191BA8
0x18004db70  lea     rax, aChecktokenmemb; "CheckTokenMembership(RDU) failed!"
0x18004db77  mov     [rbp+57h+var_68], rax
0x18004db7b  lea     rax, [rbp+57h+var_70]
0x18004db7f  mov     qword ptr [rsp+0E0h+nSubAuthority6], rax
0x18004db84  lea     rax, [rbp+57h+var_7C]
0x18004db88  mov     qword ptr [rsp+0E0h+nSubAuthority5], rax
0x18004db8d  lea     rax, [rbp+57h+var_78]
0x18004db91  mov     qword ptr [rsp+0E0h+nSubAuthority4], rax
0x18004db96  lea     rax, [rbp+57h+var_80]
0x18004db9a  mov     qword ptr [rsp+0E0h+nSubAuthority3], rax
0x18004db9f  lea     rax, [rbp+57h+var_68]
0x18004dba3  jmp     loc_18004D7B5
0x18004dba8  mov     rdx, [rbp+57h+var_48]; SidToCheck
0x18004dbac  lea     r8, [rbp+57h+var_5C]; IsMember
0x18004dbb0  mov     rcx, rdi; TokenHandle
0x18004dbb3  call    cs:__imp_CheckTokenMembership
0x18004dbb9  test    eax, eax
0x18004dbbb  mov     eax, cs:dword_1801B76C8
0x18004dbc1  jnz     short loc_18004DC3D
0x18004dbc3  cmp     eax, 2
0x18004dbc6  jbe     loc_18004DD24
0x18004dbcc  lea     rcx, aLoguserinfo; "LogUserInfo"
0x18004dbd3  mov     [rbp+57h+var_7C], 1EFAh
0x18004dbda  mov     [rbp+57h+var_70], rcx
0x18004dbde  lea     rcx, aClientcoreTerm_12; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18004dbe5  mov     [rbp+57h+var_78], rcx
0x18004dbe9  call    cs:__imp_GetLastError
0x18004dbef  test    eax, eax
0x18004dbf1  jle     short loc_18004DBFB
0x18004dbf3  movzx   eax, ax
0x18004dbf6  or      eax, 80070000h
0x18004dbfb  mov     [rbp+57h+var_80], eax
  ... truncated ...
```
