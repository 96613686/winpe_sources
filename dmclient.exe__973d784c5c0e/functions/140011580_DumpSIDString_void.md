# DumpSIDString(void *)

- ea: `0x140011580`
- end: `0x1400119e8`
- name: `?DumpSIDString@@YAXPEAX@Z`
- size: `1128`
- prototype: `void __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011cd0`
- `0x140012120`

## callees

- `0x140001840`
- `0x140001a9c`
- `0x140001bb4`
- `0x140011580`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011618`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011643`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001166e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011618`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140011643`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001166e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001162d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011658`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001193d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001162d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011658`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011918`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001193d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001192c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011976`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001192c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011976`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001182e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001188e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400118d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001198f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400115e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400116ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001182e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001188e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400118d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001198f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400115d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400116b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400115d5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400116b1`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400117bb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1400117bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400116cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1400116cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001186e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001186e`

## string_xrefs

- `0x14001175d`: `Got SID.`
- `0x1400118a5`: `Failed to get SID.`
- `0x1400118ee`: `Failed to get buffer for TokenUser and Account Name.`
- `0x1400119a6`: `Failed required length for TokenUser.`

## pseudocode

```c
void __fastcall DumpSIDString(WCHAR *TokenHandle)
{
  DWORD v2; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v4; // rdi
  SIZE_T v5; // rbx
  HANDLE v6; // rax
  WCHAR *v7; // rsi
  SIZE_T v8; // rbx
  HANDLE v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rbx
  DWORD LastError; // eax
  LPWSTR v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  HANDLE v28; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned __int32 v34; // [rsp+40h] [rbp-89h] BYREF
  DWORD TokenInformationLength; // [rsp+44h] [rbp-85h] BYREF
  const char *v36; // [rsp+48h] [rbp-81h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-79h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-75h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-69h] BYREF
  WCHAR *v41; // [rsp+68h] [rbp-61h] BYREF
  WCHAR *v42; // [rsp+70h] [rbp-59h] BYREF
  char v43[32]; // [rsp+80h] [rbp-49h] BYREF
  const char *v44; // [rsp+A0h] [rbp-29h]
  __int64 v45; // [rsp+A8h] [rbp-21h]
  HANDLE *v46; // [rsp+B0h] [rbp-19h]
  __int64 v47; // [rsp+B8h] [rbp-11h]
  LPWSTR v48; // [rsp+C0h] [rbp-9h]
  int v49; // [rsp+C8h] [rbp-1h]
  int v50; // [rsp+CCh] [rbp+3h]
  unsigned __int32 *v51; // [rsp+D0h] [rbp+7h]
  __int64 v52; // [rsp+D8h] [rbp+Fh]

  cchName = 256;
  cchReferencedDomainName = 256;
  TokenInformationLength = 0;
  StringSid = 0;
  peUse = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v2 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v4 = (PSID *)HeapAlloc(ProcessHeap, 8u, v2);
    v5 = 2LL * cchName;
    v6 = GetProcessHeap();
    v7 = (WCHAR *)HeapAlloc(v6, 8u, v5);
    v8 = 2LL * cchReferencedDomainName;
    v9 = GetProcessHeap();
    v10 = (WCHAR *)HeapAlloc(v9, 8u, v8);
    v11 = v10;
    if ( v4 && v7 && v10 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength)
        && ConvertSidToStringSidW(*v4, &StringSid) )
      {
        if ( (unsigned int)dword_140028000 > 5 )
        {
          LastError = GetLastError();
          v13 = StringSid;
          v34 = LastError;
          v51 = &v34;
          v41 = TokenHandle;
          v52 = 4;
          if ( StringSid )
          {
            v14 = -1;
            do
              ++v14;
            while ( StringSid[v14] );
            v15 = 2 * v14 + 2;
          }
          else
          {
            v13 = (LPWSTR)&dword_14001D5D4;
            v15 = 2;
          }
          v49 = v15;
          v48 = v13;
          v46 = (HANDLE *)&v41;
          v50 = 0;
          v44 = "Got SID.";
          v47 = 8;
          v45 = 9;
          tlgWriteTransfer_EventWriteTransfer(&dword_140028000, byte_140023383, 0, 0, 6, v43);
        }
        if ( LookupAccountSidW(0, *v4, v7, &cchName, v11, &cchReferencedDomainName, &peUse) )
        {
          if ( (unsigned int)dword_140028000 > 5 )
          {
            v34 = peUse;
            v36 = "Account info";
            v41 = v11;
            v42 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v16,
              (unsigned int)&dword_1400232C4,
              v17,
              v18,
              (__int64)&v36,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&v34);
          }
        }
        else if ( (unsigned int)dword_140028000 > 5 )
        {
          v34 = GetLastError();
          v36 = "Failed to look up account";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (unsigned int)&dword_14002342C,
            v20,
            v21,
            (__int64)&v36,
            (__int64)&v34);
        }
        LocalFree(StringSid);
        goto LABEL_26;
      }
      if ( (unsigned int)dword_140028000 > 5 )
      {
        v34 = GetLastError();
        v36 = "Failed to get SID.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v22,
          (unsigned int)byte_1400231CD,
          v23,
          v24,
          (__int64)&v36,
          (__int64)&v34);
        goto LABEL_26;
      }
    }
    else if ( (unsigned int)dword_140028000 > 5 )
    {
      v34 = GetLastError();
      v36 = "Failed to get buffer for TokenUser and Account Name.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v25,
        (unsigned int)&word_14002329E,
        v26,
        v27,
        (__int64)&v36,
        (__int64)&v34);
    }
    if ( !v7 )
    {
LABEL_27:
      if ( v11 )
      {
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v11);
      }
      if ( v4 )
      {
        v30 = GetProcessHeap();
        HeapFree(v30, 0, v4);
      }
      return;
    }
LABEL_26:
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v7);
    goto LABEL_27;
  }
  if ( (unsigned int)dword_140028000 > 5 )
  {
    v34 = GetLastError();
    v36 = "Failed required length for TokenUser.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (unsigned int)qword_140023510,
      v32,
      v33,
      (__int64)&v36,
      (__int64)&v34);
  }
}

```

## disassembly

```asm
0x140011580  push    rbp
0x140011582  push    rbx
0x140011583  push    rsi
0x140011584  push    rdi
0x140011585  push    r14
0x140011587  push    r15
0x140011589  lea     rbp, [rsp-2Fh]
0x14001158e  sub     rsp, 0F8h
0x140011595  mov     rax, cs:__security_cookie
0x14001159c  xor     rax, rsp
0x14001159f  mov     [rbp+57h+var_40], rax
0x1400115a3  xor     r15d, r15d
0x1400115a6  mov     eax, 100h
0x1400115ab  mov     [rbp+57h+cchName], eax
0x1400115ae  xor     r9d, r9d; TokenInformationLength
0x1400115b1  mov     [rbp+57h+var_D0], eax
0x1400115b4  xor     r8d, r8d; TokenInformation
0x1400115b7  lea     rax, [rsp+120h+TokenInformationLength]
0x1400115bc  mov     [rsp+120h+TokenInformationLength], r15d
0x1400115c1  lea     edx, [r15+1]; TokenInformationClass
0x1400115c5  mov     [rbp+57h+StringSid], r15
0x1400115c9  mov     r14, rcx
0x1400115cc  mov     [rbp+57h+var_C8], r15d
0x1400115d0  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1400115d5  call    cs:__imp_GetTokenInformation
0x1400115dc  nop     dword ptr [rax+rax+00h]
0x1400115e1  test    eax, eax
0x1400115e3  jnz     loc_140011984
0x1400115e9  call    cs:__imp_GetLastError
0x1400115f0  nop     dword ptr [rax+rax+00h]
0x1400115f5  cmp     eax, 7Ah ; 'z'
0x1400115f8  jnz     loc_140011984
0x1400115fe  mov     ebx, [rsp+120h+TokenInformationLength]
0x140011602  call    cs:__imp_GetProcessHeap
0x140011609  nop     dword ptr [rax+rax+00h]
0x14001160e  mov     r8d, ebx; dwBytes
0x140011611  lea     edx, [r15+8]; dwFlags
0x140011615  mov     rcx, rax; hHeap
0x140011618  call    cs:__imp_HeapAlloc
0x14001161f  nop     dword ptr [rax+rax+00h]
0x140011624  mov     ebx, [rbp+57h+cchName]
0x140011627  mov     rdi, rax
0x14001162a  add     rbx, rbx
0x14001162d  call    cs:__imp_GetProcessHeap
0x140011634  nop     dword ptr [rax+rax+00h]
0x140011639  mov     r8, rbx; dwBytes
0x14001163c  lea     edx, [r15+8]; dwFlags
0x140011640  mov     rcx, rax; hHeap
0x140011643  call    cs:__imp_HeapAlloc
0x14001164a  nop     dword ptr [rax+rax+00h]
0x14001164f  mov     ebx, [rbp+57h+var_D0]
0x140011652  mov     rsi, rax
0x140011655  add     rbx, rbx
0x140011658  call    cs:__imp_GetProcessHeap
0x14001165f  nop     dword ptr [rax+rax+00h]
0x140011664  mov     r8, rbx; dwBytes
0x140011667  lea     edx, [r15+8]; dwFlags
0x14001166b  mov     rcx, rax; hHeap
0x14001166e  call    cs:__imp_HeapAlloc
0x140011675  nop     dword ptr [rax+rax+00h]
0x14001167a  mov     rbx, rax
0x14001167d  test    rdi, rdi
0x140011680  jz      loc_1400118CC
0x140011686  test    rsi, rsi
0x140011689  jz      loc_1400118CC
0x14001168f  test    rax, rax
0x140011692  jz      loc_1400118CC
0x140011698  mov     r9d, [rsp+120h+TokenInformationLength]; TokenInformationLength
0x14001169d  lea     rax, [rsp+120h+TokenInformationLength]
0x1400116a2  mov     r8, rdi; TokenInformation
0x1400116a5  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1400116aa  lea     edx, [r15+1]; TokenInformationClass
0x1400116ae  mov     rcx, r14; TokenHandle
0x1400116b1  call    cs:__imp_GetTokenInformation
0x1400116b8  nop     dword ptr [rax+rax+00h]
0x1400116bd  test    eax, eax
0x1400116bf  jz      loc_14001187F
0x1400116c5  mov     rcx, [rdi]; Sid
0x1400116c8  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1400116cc  call    cs:__imp_ConvertSidToStringSidW
0x1400116d3  nop     dword ptr [rax+rax+00h]
0x1400116d8  test    eax, eax
0x1400116da  jz      loc_14001187F
0x1400116e0  mov     eax, cs:dword_140028000
0x1400116e6  cmp     eax, 5
0x1400116e9  jbe     loc_140011798
0x1400116ef  call    cs:__imp_GetLastError
0x1400116f6  nop     dword ptr [rax+rax+00h]
0x1400116fb  mov     rcx, [rbp+57h+StringSid]
0x1400116ff  mov     [rsp+120h+var_E0], eax
0x140011703  lea     rax, [rsp+120h+var_E0]
0x140011708  mov     [rbp+57h+var_50], rax
0x14001170c  mov     [rbp+57h+var_B8], r14
0x140011710  mov     [rbp+57h+var_48], 4
0x140011718  test    rcx, rcx
0x14001171b  jz      short loc_140011734
0x14001171d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011721  inc     rax
0x140011724  cmp     [rcx+rax*2], r15w
0x140011729  jnz     short loc_140011721
0x14001172b  lea     eax, ds:2[rax*2]
0x140011732  jmp     short loc_140011740
0x140011734  lea     rcx, dword_14001D5D4
0x14001173b  mov     eax, 2
0x140011740  mov     [rbp+57h+var_58], eax
0x140011743  lea     rdx, byte_140023383
0x14001174a  lea     rax, [rbp+57h+var_B8]
0x14001174e  mov     [rbp+57h+var_60], rcx
0x140011752  mov     [rbp+57h+var_70], rax
0x140011756  lea     rcx, dword_140028000
0x14001175d  lea     rax, aGotSid; "Got SID."
0x140011764  mov     [rbp+57h+var_54], r15d
0x140011768  mov     [rbp+57h+var_80], rax
0x14001176c  xor     r9d, r9d
0x14001176f  lea     rax, [rbp+57h+var_A0]
0x140011773  mov     [rbp+57h+var_68], 8
0x14001177b  mov     [rsp+120h+cchReferencedDomainName], rax
0x140011780  xor     r8d, r8d
0x140011783  mov     dword ptr [rsp+120h+ReturnLength], 6
0x14001178b  mov     [rbp+57h+var_78], 9
0x140011793  call    _tlgWriteTransfer_EventWriteTransfer
0x140011798  mov     rdx, [rdi]; Sid
0x14001179b  lea     rax, [rbp+57h+var_C8]
0x14001179f  mov     [rsp+120h+peUse], rax; peUse
0x1400117a4  lea     r9, [rbp+57h+cchName]; cchName
0x1400117a8  lea     rax, [rbp+57h+var_D0]
0x1400117ac  mov     r8, rsi; Name
0x1400117af  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1400117b4  xor     ecx, ecx; lpSystemName
0x1400117b6  mov     [rsp+120h+ReturnLength], rbx; ReferencedDomainName
0x1400117bb  call    cs:__imp_LookupAccountSidW
0x1400117c2  nop     dword ptr [rax+rax+00h]
0x1400117c7  test    eax, eax
0x1400117c9  mov     eax, cs:dword_140028000
0x1400117cf  jz      short loc_140011829
0x1400117d1  cmp     eax, 5
0x1400117d4  jbe     loc_14001186A
0x1400117da  mov     eax, [rbp+57h+var_C8]
0x1400117dd  lea     rdx, dword_1400232C4
0x1400117e4  mov     [rsp+120h+var_E0], eax
0x1400117e8  lea     rax, aAccountInfo; "Account info"
0x1400117ef  mov     [rsp+120h+var_D8], rax
0x1400117f4  lea     rax, [rsp+120h+var_E0]
0x1400117f9  mov     [rsp+120h+var_E8], rax
0x1400117fe  lea     rax, [rbp+57h+var_B8]
0x140011802  mov     [rsp+120h+peUse], rax
0x140011807  lea     rax, [rbp+57h+var_B0]
0x14001180b  mov     [rsp+120h+cchReferencedDomainName], rax
0x140011810  lea     rax, [rsp+120h+var_D8]
0x140011815  mov     [rsp+120h+ReturnLength], rax
0x14001181a  mov     [rbp+57h+var_B8], rbx
0x14001181e  mov     [rbp+57h+var_B0], rsi
0x140011822  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x140011827  jmp     short loc_14001186A
0x140011829  cmp     eax, 5
0x14001182c  jbe     short loc_14001186A
0x14001182e  call    cs:__imp_GetLastError
0x140011835  nop     dword ptr [rax+rax+00h]
0x14001183a  mov     [rsp+120h+var_E0], eax
0x14001183e  lea     rdx, dword_14002342C
0x140011845  lea     rax, aFailedToLookUp; "Failed to look up account"
0x14001184c  mov     [rsp+120h+var_D8], rax
0x140011851  lea     rax, [rsp+120h+var_E0]
0x140011856  mov     [rsp+120h+cchReferencedDomainName], rax
0x14001185b  lea     rax, [rsp+120h+var_D8]
0x140011860  mov     [rsp+120h+ReturnLength], rax
0x140011865  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001186a  mov     rcx, [rbp+57h+StringSid]; hMem
0x14001186e  call    cs:__imp_LocalFree
0x140011875  nop     dword ptr [rax+rax+00h]
0x14001187a  jmp     loc_140011918
0x14001187f  mov     eax, cs:dword_140028000
0x140011885  cmp     eax, 5
0x140011888  jbe     loc_140011913
0x14001188e  call    cs:__imp_GetLastError
0x140011895  nop     dword ptr [rax+rax+00h]
0x14001189a  mov     [rsp+120h+var_E0], eax
0x14001189e  lea     rdx, byte_1400231CD
0x1400118a5  lea     rax, aFailedToGetSid; "Failed to get SID."
0x1400118ac  mov     [rsp+120h+var_D8], rax
0x1400118b1  lea     rax, [rsp+120h+var_E0]
0x1400118b6  mov     [rsp+120h+cchReferencedDomainName], rax
0x1400118bb  lea     rax, [rsp+120h+var_D8]
0x1400118c0  mov     [rsp+120h+ReturnLength], rax
0x1400118c5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400118ca  jmp     short loc_140011918
0x1400118cc  mov     eax, cs:dword_140028000
0x1400118d2  cmp     eax, 5
0x1400118d5  jbe     short loc_140011913
0x1400118d7  call    cs:__imp_GetLastError
0x1400118de  nop     dword ptr [rax+rax+00h]
0x1400118e3  mov     [rsp+120h+var_E0], eax
0x1400118e7  lea     rdx, word_14002329E
0x1400118ee  lea     rax, aFailedToGetBuf; "Failed to get buffer for TokenUser and "...
0x1400118f5  mov     [rsp+120h+var_D8], rax
0x1400118fa  lea     rax, [rsp+120h+var_E0]
0x1400118ff  mov     [rsp+120h+cchReferencedDomainName], rax
0x140011904  lea     rax, [rsp+120h+var_D8]
0x140011909  mov     [rsp+120h+ReturnLength], rax
0x14001190e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140011913  test    rsi, rsi
0x140011916  jz      short loc_140011938
0x140011918  call    cs:__imp_GetProcessHeap
0x14001191f  nop     dword ptr [rax+rax+00h]
0x140011924  mov     r8, rsi; lpMem
0x140011927  xor     edx, edx; dwFlags
0x140011929  mov     rcx, rax; hHeap
0x14001192c  call    cs:__imp_HeapFree
0x140011933  nop     dword ptr [rax+rax+00h]
0x140011938  test    rbx, rbx
0x14001193b  jz      short loc_14001195D
0x14001193d  call    cs:__imp_GetProcessHeap
0x140011944  nop     dword ptr [rax+rax+00h]
0x140011949  mov     r8, rbx; lpMem
0x14001194c  xor     edx, edx; dwFlags
0x14001194e  mov     rcx, rax; hHeap
0x140011951  call    cs:__imp_HeapFree
0x140011958  nop     dword ptr [rax+rax+00h]
0x14001195d  test    rdi, rdi
0x140011960  jz      short loc_1400119CB
0x140011962  call    cs:__imp_GetProcessHeap
0x140011969  nop     dword ptr [rax+rax+00h]
0x14001196e  mov     r8, rdi; lpMem
0x140011971  xor     edx, edx; dwFlags
0x140011973  mov     rcx, rax; hHeap
0x140011976  call    cs:__imp_HeapFree
0x14001197d  nop     dword ptr [rax+rax+00h]
0x140011982  jmp     short loc_1400119CB
0x140011984  mov     eax, cs:dword_140028000
0x14001198a  cmp     eax, 5
0x14001198d  jbe     short loc_1400119CB
0x14001198f  call    cs:__imp_GetLastError
0x140011996  nop     dword ptr [rax+rax+00h]
0x14001199b  mov     [rsp+120h+var_E0], eax
0x14001199f  lea     rdx, qword_140023510
0x1400119a6  lea     rax, aFailedRequired; "Failed required length for TokenUser."
0x1400119ad  mov     [rsp+120h+var_D8], rax
0x1400119b2  lea     rax, [rsp+120h+var_E0]
0x1400119b7  mov     [rsp+120h+cchReferencedDomainName], rax
0x1400119bc  lea     rax, [rsp+120h+var_D8]
0x1400119c1  mov     [rsp+120h+ReturnLength], rax
0x1400119c6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400119cb  mov     rcx, [rbp+57h+var_40]
0x1400119cf  xor     rcx, rsp; StackCookie
0x1400119d2  call    __security_check_cookie
0x1400119d7  add     rsp, 0F8h
0x1400119de  pop     r15
0x1400119e0  pop     r14
0x1400119e2  pop     rdi
0x1400119e3  pop     rsi
0x1400119e4  pop     rbx
0x1400119e5  pop     rbp
0x1400119e6  retn
```
