# DumpSIDString(void *)

- ea: `0x140010e70`
- end: `0x140011249`
- name: `?DumpSIDString@@YAXPEAX@Z`
- size: `985`
- prototype: `void __fastcall(int *TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001150c`
- `0x140011928`

## callees

- `0x14000182c`
- `0x140001a84`
- `0x140001b9c`
- `0x140010e70`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010ef6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010f34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010ef6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140010f34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010ee6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010ee6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010f24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400111d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400111e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400111f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011126`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400111f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010ec5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010f71`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010ec5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140010f71`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140011069`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140011069`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140010f86`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140010f86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011110`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011110`

## string_xrefs

- `0x14001100b`: `Got SID.`
- `0x140011137`: `Failed to get SID.`
- `0x14001117a`: `Failed to get buffer for TokenUser and Account Name.`
- `0x140011208`: `Failed required length for TokenUser.`

## pseudocode

```c
void __fastcall DumpSIDString(int *TokenHandle)
{
  DWORD v2; // ebx
  HANDLE ProcessHeap; // rax
  PSID *v4; // rdi
  SIZE_T v5; // rbx
  HANDLE v6; // rax
  int *v7; // rsi
  SIZE_T v8; // rbx
  HANDLE v9; // rax
  int *v10; // rax
  int *v11; // rbx
  DWORD LastError; // eax
  LPWSTR v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  HANDLE v28; // rax
  HANDLE v29; // rax
  HANDLE v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned __int32 v34; // [rsp+40h] [rbp-89h] BYREF
  DWORD TokenInformationLength; // [rsp+44h] [rbp-85h] BYREF
  const char *v36; // [rsp+48h] [rbp-81h] BYREF
  DWORD cchReferencedDomainName; // [rsp+50h] [rbp-79h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-75h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+58h] [rbp-71h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-69h] BYREF
  int *v41; // [rsp+68h] [rbp-61h] BYREF
  int *v42; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v43[32]; // [rsp+80h] [rbp-49h] BYREF
  const char *v44; // [rsp+A0h] [rbp-29h]
  __int64 v45; // [rsp+A8h] [rbp-21h]
  int **v46; // [rsp+B0h] [rbp-19h]
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
    v7 = (int *)HeapAlloc(v6, 8u, v5);
    v8 = 2LL * cchReferencedDomainName;
    v9 = GetProcessHeap();
    v10 = (int *)HeapAlloc(v9, 8u, v8);
    v11 = v10;
    if ( v4 && v7 && v10 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength)
        && ConvertSidToStringSidW(*v4, &StringSid) )
      {
        if ( (unsigned int)dword_140027000 > 5 )
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
            v13 = (LPWSTR)&dword_14001C5D4;
            v15 = 2;
          }
          v49 = v15;
          v48 = v13;
          v46 = &v41;
          v50 = 0;
          v44 = "Got SID.";
          v47 = 8;
          v45 = 9;
          tlgWriteTransfer_EventWriteTransfer(&dword_140027000, byte_14002237B, 0, 0, 6, v43);
        }
        if ( LookupAccountSidW(0, *v4, (LPWSTR)v7, &cchName, (LPWSTR)v11, &cchReferencedDomainName, &peUse) )
        {
          if ( (unsigned int)dword_140027000 > 5 )
          {
            v34 = peUse;
            v36 = "Account info";
            v41 = v11;
            v42 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v16,
              (__int64)&dword_1400222BC,
              v17,
              v18,
              (const unsigned __int16 **)&v36,
              &v42,
              &v41,
              (__int64)&v34);
          }
        }
        else if ( (unsigned int)dword_140027000 > 5 )
        {
          v34 = GetLastError();
          v36 = "Failed to look up account";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v19,
            (__int64)&dword_140022424,
            v20,
            v21,
            (const unsigned __int16 **)&v36,
            (__int64)&v34);
        }
        LocalFree(StringSid);
        goto LABEL_26;
      }
      if ( (unsigned int)dword_140027000 > 5 )
      {
        v34 = GetLastError();
        v36 = "Failed to get SID.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v22,
          (__int64)byte_1400221C5,
          v23,
          v24,
          (const unsigned __int16 **)&v36,
          (__int64)&v34);
        goto LABEL_26;
      }
    }
    else if ( (unsigned int)dword_140027000 > 5 )
    {
      v34 = GetLastError();
      v36 = "Failed to get buffer for TokenUser and Account Name.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v25,
        (__int64)&word_140022296,
        v26,
        v27,
        (const unsigned __int16 **)&v36,
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
  if ( (unsigned int)dword_140027000 > 5 )
  {
    v34 = GetLastError();
    v36 = "Failed required length for TokenUser.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v31,
      (__int64)qword_140022508,
      v32,
      v33,
      (const unsigned __int16 **)&v36,
      (__int64)&v34);
  }
}

```

## disassembly

```asm
0x140010e70  push    rbp
0x140010e72  push    rbx
0x140010e73  push    rsi
0x140010e74  push    rdi
0x140010e75  push    r14
0x140010e77  push    r15
0x140010e79  lea     rbp, [rsp-2Fh]
0x140010e7e  sub     rsp, 0F8h
0x140010e85  mov     rax, cs:__security_cookie
0x140010e8c  xor     rax, rsp
0x140010e8f  mov     [rbp+57h+var_40], rax
0x140010e93  xor     r15d, r15d
0x140010e96  mov     eax, 100h
0x140010e9b  mov     [rbp+57h+cchName], eax
0x140010e9e  xor     r9d, r9d; TokenInformationLength
0x140010ea1  mov     [rbp+57h+var_D0], eax
0x140010ea4  xor     r8d, r8d; TokenInformation
0x140010ea7  lea     rax, [rsp+120h+TokenInformationLength]
0x140010eac  mov     [rsp+120h+TokenInformationLength], r15d
0x140010eb1  lea     edx, [r15+1]; TokenInformationClass
0x140010eb5  mov     [rbp+57h+StringSid], r15
0x140010eb9  mov     r14, rcx
0x140010ebc  mov     [rbp+57h+var_C8], r15d
0x140010ec0  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x140010ec5  call    cs:__imp_GetTokenInformation
0x140010ecb  test    eax, eax
0x140010ecd  jnz     loc_1400111EC
0x140010ed3  call    cs:__imp_GetLastError
0x140010ed9  cmp     eax, 7Ah ; 'z'
0x140010edc  jnz     loc_1400111EC
0x140010ee2  mov     ebx, [rsp+120h+TokenInformationLength]
0x140010ee6  call    cs:__imp_GetProcessHeap
0x140010eec  mov     r8d, ebx; dwBytes
0x140010eef  lea     edx, [r15+8]; dwFlags
0x140010ef3  mov     rcx, rax; hHeap
0x140010ef6  call    cs:__imp_HeapAlloc
0x140010efc  mov     ebx, [rbp+57h+cchName]
0x140010eff  mov     rdi, rax
0x140010f02  add     rbx, rbx
0x140010f05  call    cs:__imp_GetProcessHeap
0x140010f0b  mov     r8, rbx; dwBytes
0x140010f0e  lea     edx, [r15+8]; dwFlags
0x140010f12  mov     rcx, rax; hHeap
0x140010f15  call    cs:__imp_HeapAlloc
0x140010f1b  mov     ebx, [rbp+57h+var_D0]
0x140010f1e  mov     rsi, rax
0x140010f21  add     rbx, rbx
0x140010f24  call    cs:__imp_GetProcessHeap
0x140010f2a  mov     r8, rbx; dwBytes
0x140010f2d  lea     edx, [r15+8]; dwFlags
0x140010f31  mov     rcx, rax; hHeap
0x140010f34  call    cs:__imp_HeapAlloc
0x140010f3a  mov     rbx, rax
0x140010f3d  test    rdi, rdi
0x140010f40  jz      loc_14001115E
0x140010f46  test    rsi, rsi
0x140010f49  jz      loc_14001115E
0x140010f4f  test    rax, rax
0x140010f52  jz      loc_14001115E
0x140010f58  mov     r9d, [rsp+120h+TokenInformationLength]; TokenInformationLength
0x140010f5d  lea     rax, [rsp+120h+TokenInformationLength]
0x140010f62  mov     r8, rdi; TokenInformation
0x140010f65  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x140010f6a  lea     edx, [r15+1]; TokenInformationClass
0x140010f6e  mov     rcx, r14; TokenHandle
0x140010f71  call    cs:__imp_GetTokenInformation
0x140010f77  test    eax, eax
0x140010f79  jz      loc_14001111B
0x140010f7f  mov     rcx, [rdi]; Sid
0x140010f82  lea     rdx, [rbp+57h+StringSid]; StringSid
0x140010f86  call    cs:__imp_ConvertSidToStringSidW
0x140010f8c  test    eax, eax
0x140010f8e  jz      loc_14001111B
0x140010f94  mov     eax, cs:dword_140027000
0x140010f9a  cmp     eax, 5
0x140010f9d  jbe     loc_140011046
0x140010fa3  call    cs:__imp_GetLastError
0x140010fa9  mov     rcx, [rbp+57h+StringSid]
0x140010fad  mov     [rsp+120h+var_E0], eax
0x140010fb1  lea     rax, [rsp+120h+var_E0]
0x140010fb6  mov     [rbp+57h+var_50], rax
0x140010fba  mov     [rbp+57h+var_B8], r14
0x140010fbe  mov     [rbp+57h+var_48], 4
0x140010fc6  test    rcx, rcx
0x140010fc9  jz      short loc_140010FE2
0x140010fcb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010fcf  inc     rax
0x140010fd2  cmp     [rcx+rax*2], r15w
0x140010fd7  jnz     short loc_140010FCF
0x140010fd9  lea     eax, ds:2[rax*2]
0x140010fe0  jmp     short loc_140010FEE
0x140010fe2  lea     rcx, dword_14001C5D4
0x140010fe9  mov     eax, 2
0x140010fee  mov     [rbp+57h+var_58], eax
0x140010ff1  lea     rdx, byte_14002237B
0x140010ff8  lea     rax, [rbp+57h+var_B8]
0x140010ffc  mov     [rbp+57h+var_60], rcx
0x140011000  mov     [rbp+57h+var_70], rax
0x140011004  lea     rcx, dword_140027000
0x14001100b  lea     rax, aGotSid; "Got SID."
0x140011012  mov     [rbp+57h+var_54], r15d
0x140011016  mov     [rbp+57h+var_80], rax
0x14001101a  xor     r9d, r9d
0x14001101d  lea     rax, [rbp+57h+var_A0]
0x140011021  mov     [rbp+57h+var_68], 8
0x140011029  mov     [rsp+120h+cchReferencedDomainName], rax
0x14001102e  xor     r8d, r8d
0x140011031  mov     dword ptr [rsp+120h+ReturnLength], 6
0x140011039  mov     [rbp+57h+var_78], 9
0x140011041  call    _tlgWriteTransfer_EventWriteTransfer
0x140011046  mov     rdx, [rdi]; Sid
0x140011049  lea     rax, [rbp+57h+var_C8]
0x14001104d  mov     [rsp+120h+peUse], rax; peUse
0x140011052  lea     r9, [rbp+57h+cchName]; cchName
0x140011056  lea     rax, [rbp+57h+var_D0]
0x14001105a  mov     r8, rsi; Name
0x14001105d  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x140011062  xor     ecx, ecx; lpSystemName
0x140011064  mov     [rsp+120h+ReturnLength], rbx; ReferencedDomainName
0x140011069  call    cs:__imp_LookupAccountSidW
0x14001106f  test    eax, eax
0x140011071  mov     eax, cs:dword_140027000
0x140011077  jz      short loc_1400110D1
0x140011079  cmp     eax, 5
0x14001107c  jbe     loc_14001110C
0x140011082  mov     eax, [rbp+57h+var_C8]
0x140011085  lea     rdx, dword_1400222BC
0x14001108c  mov     [rsp+120h+var_E0], eax
0x140011090  lea     rax, aAccountInfo; "Account info"
0x140011097  mov     [rsp+120h+var_D8], rax
0x14001109c  lea     rax, [rsp+120h+var_E0]
0x1400110a1  mov     [rsp+120h+var_E8], rax
0x1400110a6  lea     rax, [rbp+57h+var_B8]
0x1400110aa  mov     [rsp+120h+peUse], rax
0x1400110af  lea     rax, [rbp+57h+var_B0]
0x1400110b3  mov     [rsp+120h+cchReferencedDomainName], rax
0x1400110b8  lea     rax, [rsp+120h+var_D8]
0x1400110bd  mov     [rsp+120h+ReturnLength], rax
0x1400110c2  mov     [rbp+57h+var_B8], rbx
0x1400110c6  mov     [rbp+57h+var_B0], rsi
0x1400110ca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400110cf  jmp     short loc_14001110C
0x1400110d1  cmp     eax, 5
0x1400110d4  jbe     short loc_14001110C
0x1400110d6  call    cs:__imp_GetLastError
0x1400110dc  mov     [rsp+120h+var_E0], eax
0x1400110e0  lea     rdx, dword_140022424
0x1400110e7  lea     rax, aFailedToLookUp; "Failed to look up account"
0x1400110ee  mov     [rsp+120h+var_D8], rax
0x1400110f3  lea     rax, [rsp+120h+var_E0]
0x1400110f8  mov     [rsp+120h+cchReferencedDomainName], rax
0x1400110fd  lea     rax, [rsp+120h+var_D8]
0x140011102  mov     [rsp+120h+ReturnLength], rax
0x140011107  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001110c  mov     rcx, [rbp+57h+StringSid]; hMem
0x140011110  call    cs:__imp_LocalFree
0x140011116  jmp     loc_1400111A4
0x14001111b  mov     eax, cs:dword_140027000
0x140011121  cmp     eax, 5
0x140011124  jbe     short loc_14001119F
0x140011126  call    cs:__imp_GetLastError
0x14001112c  mov     [rsp+120h+var_E0], eax
0x140011130  lea     rdx, byte_1400221C5
0x140011137  lea     rax, aFailedToGetSid; "Failed to get SID."
0x14001113e  mov     [rsp+120h+var_D8], rax
0x140011143  lea     rax, [rsp+120h+var_E0]
0x140011148  mov     [rsp+120h+cchReferencedDomainName], rax
0x14001114d  lea     rax, [rsp+120h+var_D8]
0x140011152  mov     [rsp+120h+ReturnLength], rax
0x140011157  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001115c  jmp     short loc_1400111A4
0x14001115e  mov     eax, cs:dword_140027000
0x140011164  cmp     eax, 5
0x140011167  jbe     short loc_14001119F
0x140011169  call    cs:__imp_GetLastError
0x14001116f  mov     [rsp+120h+var_E0], eax
0x140011173  lea     rdx, word_140022296
0x14001117a  lea     rax, aFailedToGetBuf; "Failed to get buffer for TokenUser and "...
0x140011181  mov     [rsp+120h+var_D8], rax
0x140011186  lea     rax, [rsp+120h+var_E0]
0x14001118b  mov     [rsp+120h+cchReferencedDomainName], rax
0x140011190  lea     rax, [rsp+120h+var_D8]
0x140011195  mov     [rsp+120h+ReturnLength], rax
0x14001119a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001119f  test    rsi, rsi
0x1400111a2  jz      short loc_1400111B8
0x1400111a4  call    cs:__imp_GetProcessHeap
0x1400111aa  mov     r8, rsi; lpMem
0x1400111ad  xor     edx, edx; dwFlags
0x1400111af  mov     rcx, rax; hHeap
0x1400111b2  call    cs:__imp_HeapFree
0x1400111b8  test    rbx, rbx
0x1400111bb  jz      short loc_1400111D1
0x1400111bd  call    cs:__imp_GetProcessHeap
0x1400111c3  mov     r8, rbx; lpMem
0x1400111c6  xor     edx, edx; dwFlags
0x1400111c8  mov     rcx, rax; hHeap
0x1400111cb  call    cs:__imp_HeapFree
0x1400111d1  test    rdi, rdi
0x1400111d4  jz      short loc_14001122D
0x1400111d6  call    cs:__imp_GetProcessHeap
0x1400111dc  mov     r8, rdi; lpMem
0x1400111df  xor     edx, edx; dwFlags
0x1400111e1  mov     rcx, rax; hHeap
0x1400111e4  call    cs:__imp_HeapFree
0x1400111ea  jmp     short loc_14001122D
0x1400111ec  mov     eax, cs:dword_140027000
0x1400111f2  cmp     eax, 5
0x1400111f5  jbe     short loc_14001122D
0x1400111f7  call    cs:__imp_GetLastError
0x1400111fd  mov     [rsp+120h+var_E0], eax
0x140011201  lea     rdx, qword_140022508
0x140011208  lea     rax, aFailedRequired; "Failed required length for TokenUser."
0x14001120f  mov     [rsp+120h+var_D8], rax
0x140011214  lea     rax, [rsp+120h+var_E0]
0x140011219  mov     [rsp+120h+cchReferencedDomainName], rax
0x14001121e  lea     rax, [rsp+120h+var_D8]
0x140011223  mov     [rsp+120h+ReturnLength], rax
0x140011228  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001122d  mov     rcx, [rbp+57h+var_40]
0x140011231  xor     rcx, rsp; StackCookie
0x140011234  call    __security_check_cookie
0x140011239  add     rsp, 0F8h
0x140011240  pop     r15
0x140011242  pop     r14
0x140011244  pop     rdi
0x140011245  pop     rsi
0x140011246  pop     rbx
0x140011247  pop     rbp
0x140011248  retn
```
