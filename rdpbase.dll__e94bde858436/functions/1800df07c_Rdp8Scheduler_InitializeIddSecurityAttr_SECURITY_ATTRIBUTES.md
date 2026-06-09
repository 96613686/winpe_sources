# Rdp8Scheduler::InitializeIddSecurityAttr(_SECURITY_ATTRIBUTES *)

- ea: `0x1800df07c`
- end: `0x1800df593`
- name: `?InitializeIddSecurityAttr@Rdp8Scheduler@@AEAAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1303`
- prototype: `int(Rdp8Scheduler *__hidden this, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800deca0`

## callees

- `0x1800018a4`
- `0x180078c20`
- `0x1800df07c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df26a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df1da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df26a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df2f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df423`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df4ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800df25c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800df407`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800df25c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800df407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df563`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df543`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800df563`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800df2e7`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800df2e7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800df101`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800df101`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800df534`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800df534`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800df375`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800df375`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800df3fa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800df3fa`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800df4a3`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800df4a3`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800df1d0`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800df1d0`

## string_xrefs

- `0x1800df145`: `InitializeIddSecurityAttr`
- `0x1800df210`: `InitializeIddSecurityAttr`
- `0x1800df2a0`: `InitializeIddSecurityAttr`
- `0x1800df327`: `InitializeIddSecurityAttr`
- `0x1800df3b5`: `InitializeIddSecurityAttr`
- `0x1800df40d`: `InitializeIddSecurityAttr`
- `0x1800df1fe`: `SetEntriesInAcl`
- `0x1800df133`: `Failed to allocate LOCAL SERVICE sid`
- `0x1800df315`: `InitializeSecurityDescriptor`
- `0x1800df28e`: `Failed to allocate security descriptor`
- `0x1800df3a3`: `SetSecurityDescriptorDacl`

## pseudocode

```c
__int64 __fastcall Rdp8Scheduler::InitializeIddSecurityAttr(Rdp8Scheduler *this, struct _SECURITY_ATTRIBUTES *a2)
{
  void *v3; // r14
  HLOCAL v4; // r15
  signed int v5; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  signed int v9; // ebx
  __int16 *v10; // rdx
  const char **v11; // rax
  signed int LastError; // eax
  HLOCAL v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ecx
  signed int v21; // eax
  int *nSubAuthority3; // [rsp+28h] [rbp-81h]
  int *nSubAuthority5; // [rsp+38h] [rbp-71h]
  const char **nSubAuthority6; // [rsp+40h] [rbp-69h]
  int v26; // [rsp+60h] [rbp-49h] BYREF
  int v27; // [rsp+64h] [rbp-45h] BYREF
  const char *v28; // [rsp+68h] [rbp-41h] BYREF
  const char *v29; // [rsp+70h] [rbp-39h] BYREF
  const char *v30; // [rsp+78h] [rbp-31h] BYREF
  DWORD dwBufferLength; // [rsp+80h] [rbp-29h] BYREF
  PSID pSid; // [rsp+88h] [rbp-21h] BYREF
  PACL NewAcl; // [rsp+90h] [rbp-19h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+98h] [rbp-11h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  pSid = 0;
  v3 = 0;
  NewAcl = 0;
  v4 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
    pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
    *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    if ( SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl) )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v27 = 1045;
        v28 = "SetEntriesInAcl";
        v30 = "InitializeIddSecurityAttr";
        nSubAuthority6 = &v30;
        v10 = word_1801BCA62;
        v26 = v9;
        nSubAuthority5 = &v27;
        nSubAuthority3 = &v26;
        v11 = &v28;
        goto LABEL_6;
      }
    }
    else
    {
      v13 = LocalAlloc(0x40u, 0x28u);
      v3 = v13;
      if ( v13 )
      {
        if ( InitializeSecurityDescriptor(v13, 1u) )
        {
          if ( SetSecurityDescriptorDacl(v3, 1, NewAcl, 0) )
          {
            dwBufferLength = GetSecurityDescriptorLength(v3);
            v4 = LocalAlloc(0x40u, dwBufferLength);
            if ( !v4 )
            {
              v17 = GetLastError();
              v20 = v17;
              if ( v17 > 0 )
                v20 = (unsigned __int16)v17 | 0x80070000;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v30 = "InitializeIddSecurityAttr";
                v28 = "Failed to allocate memory for self-relative SD";
                v27 = 1091;
                v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
                v26 = v20;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v20,
                  (unsigned int)word_1801BC942,
                  v18,
                  v19,
                  (__int64)&v28,
                  (__int64)&v26,
                  (__int64)&v29,
                  (__int64)&v27,
                  (__int64)&v30);
              }
            }
            if ( MakeSelfRelativeSD(v3, v4, &dwBufferLength) )
            {
              a2->nLength = 24;
              a2->lpSecurityDescriptor = v4;
              a2->bInheritHandle = 0;
              v9 = 0;
            }
            else
            {
              v21 = GetLastError();
              v9 = v21;
              if ( v21 > 0 )
                v9 = (unsigned __int16)v21 | 0x80070000;
              if ( (unsigned int)CallbackContext > 2 )
              {
                v30 = "InitializeIddSecurityAttr";
                v28 = "MakeSelfRelativeSD";
                v10 = word_1801BC8FA;
                v27 = 1097;
                nSubAuthority6 = &v30;
                nSubAuthority5 = &v27;
                nSubAuthority3 = &v26;
                v11 = &v28;
                v26 = v9;
                goto LABEL_6;
              }
            }
          }
          else
          {
            v16 = GetLastError();
            v9 = v16;
            if ( v16 > 0 )
              v9 = (unsigned __int16)v16 | 0x80070000;
            if ( (unsigned int)CallbackContext > 2 )
            {
              v27 = 1078;
              v28 = "SetSecurityDescriptorDacl";
              v30 = "InitializeIddSecurityAttr";
              nSubAuthority6 = &v30;
              v10 = word_1801BC98A;
              v26 = v9;
              nSubAuthority5 = &v27;
              nSubAuthority3 = &v26;
              v11 = &v28;
              goto LABEL_6;
            }
          }
        }
        else
        {
          v15 = GetLastError();
          v9 = v15;
          if ( v15 > 0 )
            v9 = (unsigned __int16)v15 | 0x80070000;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v27 = 1065;
            v28 = "InitializeSecurityDescriptor";
            v30 = "InitializeIddSecurityAttr";
            nSubAuthority6 = &v30;
            v10 = word_1801BC9D2;
            v26 = v9;
            nSubAuthority5 = &v27;
            nSubAuthority3 = &v26;
            v11 = &v28;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v14 = GetLastError();
        v9 = v14;
        if ( v14 > 0 )
          v9 = (unsigned __int16)v14 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v27 = 1057;
          v28 = "Failed to allocate security descriptor";
          v30 = "InitializeIddSecurityAttr";
          nSubAuthority6 = &v30;
          v10 = word_1801BCA1A;
          v26 = v9;
          nSubAuthority5 = &v27;
          nSubAuthority3 = &v26;
          v11 = &v28;
          goto LABEL_6;
        }
      }
    }
  }
  else
  {
    v5 = GetLastError();
    v9 = v5;
    if ( v5 > 0 )
      v9 = (unsigned __int16)v5 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v26 = 1021;
      v30 = "Failed to allocate LOCAL SERVICE sid";
      v28 = "InitializeIddSecurityAttr";
      nSubAuthority6 = &v28;
      v10 = word_1801BCAAA;
      v27 = v9;
      nSubAuthority5 = &v26;
      nSubAuthority3 = &v27;
      v11 = &v30;
LABEL_6:
      v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (_DWORD)v10,
        v7,
        v8,
        (__int64)v11,
        (__int64)nSubAuthority3,
        (__int64)&v29,
        (__int64)nSubAuthority5,
        (__int64)nSubAuthority6);
    }
  }
  if ( pSid )
    FreeSid(pSid);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v3 )
    LocalFree(v3);
  if ( v9 < 0 && v4 )
    LocalFree(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800df07c  mov     [rsp-8+arg_0], rbx
0x1800df081  mov     [rsp-8+arg_10], rsi
0x1800df086  push    rbp
0x1800df087  push    rdi
0x1800df088  push    r12
0x1800df08a  push    r14
0x1800df08c  push    r15
0x1800df08e  lea     rbp, [rsp-37h]
0x1800df093  sub     rsp, 0E0h
0x1800df09a  mov     rax, cs:__security_cookie
0x1800df0a1  xor     rax, rsp
0x1800df0a4  mov     [rbp+57h+var_30], rax
0x1800df0a8  xor     r12d, r12d
0x1800df0ab  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800df0b1  lea     rax, [rbp+57h+var_78]
0x1800df0b5  mov     [rbp+57h+var_78], r12
0x1800df0b9  mov     [rsp+100h+pSid], rax; pSid
0x1800df0be  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1800df0c2  mov     [rsp+100h+nSubAuthority7], r12d; nSubAuthority7
0x1800df0c7  mov     rbx, rdx
0x1800df0ca  mov     [rsp+100h+nSubAuthority6], r12d; nSubAuthority6
0x1800df0cf  lea     edi, [r12+1]
0x1800df0d4  mov     [rsp+100h+nSubAuthority5], r12d; nSubAuthority5
0x1800df0d9  lea     r8d, [r12+13h]; nSubAuthority0
0x1800df0de  mov     [rsp+100h+nSubAuthority4], r12d; nSubAuthority4
0x1800df0e3  mov     dl, dil; nSubAuthorityCount
0x1800df0e6  mov     [rsp+100h+nSubAuthority3], r12d; nSubAuthority3
0x1800df0eb  xor     r9d, r9d; nSubAuthority1
0x1800df0ee  mov     [rsp+100h+nSubAuthority2], r12d; nSubAuthority2
0x1800df0f3  mov     r14d, r12d
0x1800df0f6  mov     [rbp+57h+NewAcl], r12
0x1800df0fa  mov     r15d, r12d
0x1800df0fd  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r12d
0x1800df101  call    cs:__imp_AllocateAndInitializeSid
0x1800df107  test    eax, eax
0x1800df109  jnz     loc_1800DF19C
0x1800df10f  call    cs:__imp_GetLastError
0x1800df115  mov     ebx, eax
0x1800df117  test    eax, eax
0x1800df119  jle     short loc_1800DF124
0x1800df11b  movzx   ebx, ax
0x1800df11e  or      ebx, 80070000h
0x1800df124  mov     eax, cs:CallbackContext
0x1800df12a  cmp     eax, 2
0x1800df12d  jbe     loc_1800DF52B
0x1800df133  lea     rax, aFailedToAlloca_12; "Failed to allocate LOCAL SERVICE sid"
0x1800df13a  mov     [rbp+57h+var_A0], 3FDh
0x1800df141  mov     [rbp+57h+var_88], rax
0x1800df145  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df14c  lea     rax, [rbp+57h+var_98]
0x1800df150  mov     [rbp+57h+var_98], rdi
0x1800df154  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df159  lea     rdx, word_1801BCAAA
0x1800df160  lea     rax, [rbp+57h+var_A0]
0x1800df164  mov     [rbp+57h+var_9C], ebx
0x1800df167  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df16c  lea     rax, [rbp+57h+var_90]
0x1800df170  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df175  lea     rax, [rbp+57h+var_9C]
0x1800df179  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df17e  lea     rax, [rbp+57h+var_88]
0x1800df182  lea     rsi, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800df189  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x1800df18e  mov     [rbp+57h+var_90], rsi
0x1800df192  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800df197  jmp     loc_1800DF52B
0x1800df19c  mov     rax, [rbp+57h+var_78]
0x1800df1a0  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1800df1a4  xorps   xmm0, xmm0
0x1800df1a7  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800df1ab  xor     r8d, r8d; OldAcl
0x1800df1ae  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], rdi
0x1800df1b2  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800df1b6  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x1800df1bd  mov     ecx, edi; cCountOfExplicitEntries
0x1800df1bf  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], 2
0x1800df1c7  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x1800df1cc  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x1800df1d0  call    cs:__imp_SetEntriesInAclW
0x1800df1d6  test    eax, eax
0x1800df1d8  jz      short loc_1800DF252
0x1800df1da  call    cs:__imp_GetLastError
0x1800df1e0  mov     ebx, eax
0x1800df1e2  test    eax, eax
0x1800df1e4  jle     short loc_1800DF1EF
0x1800df1e6  movzx   ebx, ax
0x1800df1e9  or      ebx, 80070000h
0x1800df1ef  mov     eax, cs:CallbackContext
0x1800df1f5  cmp     eax, 2
0x1800df1f8  jbe     loc_1800DF52B
0x1800df1fe  lea     rax, aSetentriesinac_0; "SetEntriesInAcl"
0x1800df205  mov     [rbp+57h+var_9C], 415h
0x1800df20c  mov     [rbp+57h+var_98], rax
0x1800df210  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df217  lea     rax, [rbp+57h+var_88]
0x1800df21b  mov     [rbp+57h+var_88], rdi
0x1800df21f  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df224  lea     rdx, word_1801BCA62
0x1800df22b  lea     rax, [rbp+57h+var_9C]
0x1800df22f  mov     [rbp+57h+var_A0], ebx
0x1800df232  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df237  lea     rax, [rbp+57h+var_90]
0x1800df23b  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df240  lea     rax, [rbp+57h+var_A0]
0x1800df244  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df249  lea     rax, [rbp+57h+var_98]
0x1800df24d  jmp     loc_1800DF182
0x1800df252  mov     edx, 28h ; '('; uBytes
0x1800df257  lea     esi, [rdx+18h]
0x1800df25a  mov     ecx, esi; uFlags
0x1800df25c  call    cs:__imp_LocalAlloc
0x1800df262  mov     r14, rax
0x1800df265  test    rax, rax
0x1800df268  jnz     short loc_1800DF2E2
0x1800df26a  call    cs:__imp_GetLastError
0x1800df270  mov     ebx, eax
0x1800df272  test    eax, eax
0x1800df274  jle     short loc_1800DF27F
0x1800df276  movzx   ebx, ax
0x1800df279  or      ebx, 80070000h
0x1800df27f  mov     eax, cs:CallbackContext
0x1800df285  cmp     eax, 2
0x1800df288  jbe     loc_1800DF52B
0x1800df28e  lea     rax, aFailedToAlloca_5; "Failed to allocate security descriptor"
0x1800df295  mov     [rbp+57h+var_9C], 421h
0x1800df29c  mov     [rbp+57h+var_98], rax
0x1800df2a0  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df2a7  lea     rax, [rbp+57h+var_88]
0x1800df2ab  mov     [rbp+57h+var_88], rdi
0x1800df2af  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df2b4  lea     rdx, word_1801BCA1A
0x1800df2bb  lea     rax, [rbp+57h+var_9C]
0x1800df2bf  mov     [rbp+57h+var_A0], ebx
0x1800df2c2  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df2c7  lea     rax, [rbp+57h+var_90]
0x1800df2cb  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df2d0  lea     rax, [rbp+57h+var_A0]
0x1800df2d4  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df2d9  lea     rax, [rbp+57h+var_98]
0x1800df2dd  jmp     loc_1800DF182
0x1800df2e2  mov     edx, edi; dwRevision
0x1800df2e4  mov     rcx, r14; pSecurityDescriptor
0x1800df2e7  call    cs:__imp_InitializeSecurityDescriptor
0x1800df2ed  test    eax, eax
0x1800df2ef  jnz     short loc_1800DF369
0x1800df2f1  call    cs:__imp_GetLastError
0x1800df2f7  mov     ebx, eax
0x1800df2f9  test    eax, eax
0x1800df2fb  jle     short loc_1800DF306
0x1800df2fd  movzx   ebx, ax
0x1800df300  or      ebx, 80070000h
0x1800df306  mov     eax, cs:CallbackContext
0x1800df30c  cmp     eax, 2
0x1800df30f  jbe     loc_1800DF52B
0x1800df315  lea     rax, aInitializesecu_0; "InitializeSecurityDescriptor"
0x1800df31c  mov     [rbp+57h+var_9C], 429h
0x1800df323  mov     [rbp+57h+var_98], rax
0x1800df327  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df32e  lea     rax, [rbp+57h+var_88]
0x1800df332  mov     [rbp+57h+var_88], rdi
0x1800df336  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df33b  lea     rdx, word_1801BC9D2
0x1800df342  lea     rax, [rbp+57h+var_9C]
0x1800df346  mov     [rbp+57h+var_A0], ebx
0x1800df349  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df34e  lea     rax, [rbp+57h+var_90]
0x1800df352  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df357  lea     rax, [rbp+57h+var_A0]
0x1800df35b  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df360  lea     rax, [rbp+57h+var_98]
0x1800df364  jmp     loc_1800DF182
0x1800df369  mov     r8, [rbp+57h+NewAcl]; pDacl
0x1800df36d  xor     r9d, r9d; bDaclDefaulted
0x1800df370  mov     edx, edi; bDaclPresent
0x1800df372  mov     rcx, r14; pSecurityDescriptor
0x1800df375  call    cs:__imp_SetSecurityDescriptorDacl
0x1800df37b  test    eax, eax
0x1800df37d  jnz     short loc_1800DF3F7
0x1800df37f  call    cs:__imp_GetLastError
0x1800df385  mov     ebx, eax
0x1800df387  test    eax, eax
0x1800df389  jle     short loc_1800DF394
0x1800df38b  movzx   ebx, ax
0x1800df38e  or      ebx, 80070000h
0x1800df394  mov     eax, cs:CallbackContext
0x1800df39a  cmp     eax, 2
0x1800df39d  jbe     loc_1800DF52B
0x1800df3a3  lea     rax, aSetsecuritydes; "SetSecurityDescriptorDacl"
0x1800df3aa  mov     [rbp+57h+var_9C], 436h
0x1800df3b1  mov     [rbp+57h+var_98], rax
0x1800df3b5  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df3bc  lea     rax, [rbp+57h+var_88]
0x1800df3c0  mov     [rbp+57h+var_88], rdi
0x1800df3c4  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df3c9  lea     rdx, word_1801BC98A
0x1800df3d0  lea     rax, [rbp+57h+var_9C]
0x1800df3d4  mov     [rbp+57h+var_A0], ebx
0x1800df3d7  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df3dc  lea     rax, [rbp+57h+var_90]
0x1800df3e0  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df3e5  lea     rax, [rbp+57h+var_A0]
0x1800df3e9  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df3ee  lea     rax, [rbp+57h+var_98]
0x1800df3f2  jmp     loc_1800DF182
0x1800df3f7  mov     rcx, r14; pSecurityDescriptor
0x1800df3fa  call    cs:__imp_GetSecurityDescriptorLength
0x1800df400  mov     edx, eax; uBytes
0x1800df402  mov     ecx, esi; uFlags
0x1800df404  mov     [rbp+57h+dwBufferLength], edx
0x1800df407  call    cs:__imp_LocalAlloc
0x1800df40d  lea     rdi, aInitializeidds; "InitializeIddSecurityAttr"
0x1800df414  mov     r15, rax
0x1800df417  lea     rsi, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800df41e  test    rax, rax
0x1800df421  jnz     short loc_1800DF499
0x1800df423  call    cs:__imp_GetLastError
0x1800df429  mov     ecx, eax
0x1800df42b  test    eax, eax
0x1800df42d  jle     short loc_1800DF438
0x1800df42f  movzx   ecx, ax
0x1800df432  or      ecx, 80070000h
0x1800df438  mov     eax, cs:CallbackContext
0x1800df43e  cmp     eax, 2
0x1800df441  jbe     short loc_1800DF499
0x1800df443  lea     rax, aFailedToAlloca_1; "Failed to allocate memory for self-rela"...
0x1800df44a  mov     [rbp+57h+var_88], rdi
0x1800df44e  mov     [rbp+57h+var_98], rax
0x1800df452  lea     rdx, word_1801BC942
0x1800df459  lea     rax, [rbp+57h+var_88]
0x1800df45d  mov     [rbp+57h+var_9C], 443h
0x1800df464  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df469  lea     rax, [rbp+57h+var_9C]
0x1800df46d  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df472  lea     rax, [rbp+57h+var_90]
0x1800df476  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df47b  lea     rax, [rbp+57h+var_A0]
0x1800df47f  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df484  lea     rax, [rbp+57h+var_98]
0x1800df488  mov     qword ptr [rsp+100h+nSubAuthority2], rax
0x1800df48d  mov     [rbp+57h+var_90], rsi
0x1800df491  mov     [rbp+57h+var_A0], ecx
0x1800df494  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800df499  lea     r8, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800df49d  mov     rdx, r15; pSelfRelativeSecurityDescriptor
0x1800df4a0  mov     rcx, r14; pAbsoluteSecurityDescriptor
0x1800df4a3  call    cs:__imp_MakeSelfRelativeSD
0x1800df4a9  test    eax, eax
0x1800df4ab  jnz     short loc_1800DF51A
0x1800df4ad  call    cs:__imp_GetLastError
0x1800df4b3  mov     ebx, eax
0x1800df4b5  test    eax, eax
0x1800df4b7  jle     short loc_1800DF4C2
0x1800df4b9  movzx   ebx, ax
0x1800df4bc  or      ebx, 80070000h
0x1800df4c2  mov     eax, cs:CallbackContext
0x1800df4c8  cmp     eax, 2
0x1800df4cb  jbe     short loc_1800DF52B
0x1800df4cd  lea     rax, aMakeselfrelati; "MakeSelfRelativeSD"
0x1800df4d4  mov     [rbp+57h+var_88], rdi
0x1800df4d8  mov     [rbp+57h+var_98], rax
0x1800df4dc  lea     rdx, word_1801BC8FA
0x1800df4e3  lea     rax, [rbp+57h+var_88]
0x1800df4e7  mov     [rbp+57h+var_9C], 449h
0x1800df4ee  mov     qword ptr [rsp+100h+nSubAuthority6], rax
0x1800df4f3  lea     rax, [rbp+57h+var_9C]
0x1800df4f7  mov     qword ptr [rsp+100h+nSubAuthority5], rax
0x1800df4fc  lea     rax, [rbp+57h+var_90]
0x1800df500  mov     qword ptr [rsp+100h+nSubAuthority4], rax
0x1800df505  lea     rax, [rbp+57h+var_A0]
0x1800df509  mov     qword ptr [rsp+100h+nSubAuthority3], rax
0x1800df50e  lea     rax, [rbp+57h+var_98]
0x1800df512  mov     [rbp+57h+var_A0], ebx
0x1800df515  jmp     loc_1800DF189
0x1800df51a  mov     dword ptr [rbx], 18h
0x1800df520  mov     [rbx+8], r15
0x1800df524  mov     [rbx+10h], r12d
0x1800df528  mov     ebx, r12d
0x1800df52b  mov     rcx, [rbp+57h+var_78]; pSid
0x1800df52f  test    rcx, rcx
0x1800df532  jz      short loc_1800DF53A
0x1800df534  call    cs:__imp_FreeSid
0x1800df53a  mov     rcx, [rbp+57h+NewAcl]; hMem
0x1800df53e  test    rcx, rcx
0x1800df541  jz      short loc_1800DF549
0x1800df543  call    cs:__imp_LocalFree
0x1800df549  test    r14, r14
0x1800df54c  jz      short loc_1800DF557
0x1800df54e  mov     rcx, r14; hMem
0x1800df551  call    cs:__imp_LocalFree
0x1800df557  test    ebx, ebx
0x1800df559  jns     short loc_1800DF569
0x1800df55b  test    r15, r15
0x1800df55e  jz      short loc_1800DF569
0x1800df560  mov     rcx, r15; hMem
0x1800df563  call    cs:__imp_LocalFree
0x1800df569  mov     eax, ebx
0x1800df56b  mov     rcx, [rbp+57h+var_30]
0x1800df56f  xor     rcx, rsp; StackCookie
0x1800df572  call    __security_check_cookie
0x1800df577  lea     r11, [rsp+100h+var_20]
  ... truncated ...
```
