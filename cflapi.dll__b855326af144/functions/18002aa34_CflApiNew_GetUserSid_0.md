# CflApiNew::GetUserSid_0

- ea: `0x18002aa34`
- end: `0x18002ad4e`
- name: `CflApiNew::GetUserSid_0`
- size: `794`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a7cc`

## callees

- `0x1800067a4`
- `0x1800067c4`
- `0x1800071b4`
- `0x180010700`
- `0x18001332c`
- `0x18001f8e4`
- `0x18001f924`
- `0x18002aa34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002abfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002abfb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ac0e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ac06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ad38`
- `ntdll!RtlInitUnicodeString` at `0x18002aad2`
- `ntdll!RtlInitUnicodeString` at `0x18002aad2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002aaa7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ac77`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002aaa7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002ac77`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab65`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab96`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002abad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac55`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac68`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab46`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab65`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ab96`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002abad`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac55`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002ac68`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002aa7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18002aa7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18002ab25`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18002ab25`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002ac24`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002ac24`

## string_xrefs

- `0x18002abcb`: `Unexpected SID type: 0x%x`
- `0x18002aa8b`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002ab76`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002abdf`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002ac32`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002acb0`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002acf9`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
__int64 __fastcall CflApiNew::GetUserSid_0(PCWSTR SourceString, _QWORD *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v7; // ebx
  PVOID v8; // rcx
  PVOID v9; // rcx
  int v10; // eax
  PVOID v11; // rcx
  PVOID v12; // rcx
  bool v13; // zf
  PSID *v14; // rcx
  HLOCAL v15; // rdi
  DWORD LastError; // ebx
  const char *v17; // r9
  PVOID v18; // rcx
  PVOID v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rdi
  int v22; // eax
  PVOID v23; // rbx
  int v24; // eax
  unsigned int v25; // edi
  int ReferencedDomains; // [rsp+20h] [rbp-59h]
  int ReferencedDomainsa; // [rsp+20h] [rbp-59h]
  PLSA_TRANSLATED_SID2 *Sids; // [rsp+28h] [rbp-51h]
  PVOID PolicyHandle; // [rsp+30h] [rbp-49h] BYREF
  PVOID *v30; // [rsp+38h] [rbp-41h]
  PLSA_REFERENCED_DOMAIN_LIST v31; // [rsp+40h] [rbp-39h] BYREF
  char v32; // [rsp+48h] [rbp-31h]
  PVOID *p_Buffer; // [rsp+50h] [rbp-29h]
  PLSA_TRANSLATED_SID2 v34; // [rsp+58h] [rbp-21h] BYREF
  char v35; // [rsp+60h] [rbp-19h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  HLOCAL hMem; // [rsp+E8h] [rbp+6Fh] BYREF
  PVOID Buffer; // [rsp+F0h] [rbp+77h] BYREF
  PVOID v41; // [rsp+F8h] [rbp+7Fh] BYREF

  *a2 = 0;
  hMem = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  v4 = LsaOpenPolicy(0, &ObjectAttributes, 0x801u, &PolicyHandle);
  if ( v4 < 0 )
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x299,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
           (const char *)(unsigned int)v4,
           ReferencedDomains);
LABEL_3:
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
LABEL_5:
    if ( hMem )
      LocalFree(hMem);
    return v5;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v41 = 0;
  Buffer = 0;
  p_Buffer = &Buffer;
  v34 = 0;
  v35 = 1;
  v30 = &v41;
  v31 = 0;
  v32 = 1;
  v7 = LsaLookupNames2(PolicyHandle, 0x80000000, 1u, (PLSA_UNICODE_STRING)&DestinationString, &v31, &v34);
  if ( v32 )
  {
    v8 = *v30;
    *v30 = v31;
    if ( v8 )
      LsaFreeMemory(v8);
  }
  if ( v35 )
  {
    v9 = *p_Buffer;
    *p_Buffer = v34;
    if ( v9 )
      LsaFreeMemory(v9);
  }
  if ( v7 < 0 )
  {
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x2A0,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
            (const char *)(unsigned int)v7,
            ReferencedDomainsa);
LABEL_16:
    v5 = v10;
LABEL_17:
    v11 = Buffer;
    Buffer = 0;
    if ( v11 )
      LsaFreeMemory(v11);
    v12 = v41;
    v13 = v41 == 0;
    v41 = 0;
    if ( !v13 )
      LsaFreeMemory(v12);
    goto LABEL_3;
  }
  v14 = (PSID *)Buffer;
  if ( *(_DWORD *)Buffer != 1 )
  {
    LODWORD(Sids) = *(_DWORD *)Buffer;
    v5 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Unexpected SID type: 0x%x",
      (const char *)Sids);
    goto LABEL_17;
  }
  v15 = hMem;
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(v15);
    SetLastError(LastError);
    v14 = (PSID *)Buffer;
  }
  hMem = 0;
  if ( !ConvertSidToStringSidW(v14[1], (LPWSTR *)&hMem) )
  {
    v10 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2A3,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
            v17);
    goto LABEL_16;
  }
  v18 = Buffer;
  Buffer = 0;
  if ( v18 )
    LsaFreeMemory(v18);
  v19 = v41;
  v41 = 0;
  if ( v19 )
    LsaFreeMemory(v19);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  v20 = -1;
  do
    ++v20;
  while ( *((_WORD *)hMem + v20) );
  v21 = v20 + 1;
  Buffer = 0;
  v22 = CflApiNew::AllocBuffer_unsigned_short_(v20 + 1, &Buffer);
  v5 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v22,
      ReferencedDomainsa);
    if ( Buffer )
      CflFreeBuffer(Buffer);
    goto LABEL_5;
  }
  v23 = Buffer;
  v24 = StringCchCopyW((unsigned __int16 *)Buffer, v21, (const unsigned __int16 *)hMem);
  v25 = v24;
  if ( v24 >= 0 )
  {
    *a2 = v23;
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v24,
      ReferencedDomainsa);
    if ( v23 )
      CflFreeBuffer(v23);
    if ( hMem )
      LocalFree(hMem);
    return v25;
  }
}

```

## disassembly

```asm
0x18002aa34  push    rbp
0x18002aa36  push    rbx
0x18002aa37  push    rsi
0x18002aa38  push    rdi
0x18002aa39  push    r14
0x18002aa3b  lea     rbp, [rsp-37h]
0x18002aa40  sub     rsp, 0B0h
0x18002aa47  mov     rsi, rdx
0x18002aa4a  mov     rbx, rcx
0x18002aa4d  xor     r14d, r14d
0x18002aa50  mov     [rdx], r14
0x18002aa53  mov     [rbp+57h+hMem], r14
0x18002aa57  xorps   xmm0, xmm0
0x18002aa5a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002aa5e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002aa62  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002aa66  mov     [rbp+57h+PolicyHandle], r14
0x18002aa6a  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002aa6e  mov     r8d, 801h; DesiredAccess
0x18002aa74  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002aa78  xor     ecx, ecx; SystemName
0x18002aa7a  call    cs:__imp_LsaOpenPolicy
0x18002aa80  test    eax, eax
0x18002aa82  jns     short loc_18002AAC4
0x18002aa84  mov     rcx, [rbp+5Fh]; this
0x18002aa88  mov     r9d, eax; char *
0x18002aa8b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002aa92  mov     edx, 299h; void *
0x18002aa97  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002aa9c  mov     ebx, eax
0x18002aa9e  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002aaa2  test    rcx, rcx
0x18002aaa5  jz      short loc_18002AAAE
0x18002aaa7  call    cs:__imp_LsaClose
0x18002aaad  nop
0x18002aaae  mov     rcx, [rbp+57h+hMem]; hMem
0x18002aab2  test    rcx, rcx
0x18002aab5  jz      short loc_18002AABD
0x18002aab7  call    cs:__imp_LocalFree
0x18002aabd  mov     eax, ebx
0x18002aabf  jmp     loc_18002AD40
0x18002aac4  xorps   xmm0, xmm0
0x18002aac7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18002aacb  mov     rdx, rbx; SourceString
0x18002aace  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18002aad2  call    cs:__imp_RtlInitUnicodeString
0x18002aad8  mov     [rbp+57h+arg_18], r14
0x18002aadc  mov     [rbp+57h+Buffer], r14
0x18002aae0  lea     rax, [rbp+57h+Buffer]
0x18002aae4  mov     [rbp+57h+var_80], rax
0x18002aae8  mov     [rbp+57h+var_78], r14
0x18002aaec  mov     [rbp+57h+var_70], 1
0x18002aaf0  lea     rax, [rbp+57h+arg_18]
0x18002aaf4  mov     [rbp+57h+var_98], rax
0x18002aaf8  mov     [rbp+57h+var_90], r14
0x18002aafc  mov     [rbp+57h+var_88], 1
0x18002ab00  lea     rax, [rbp+57h+var_78]
0x18002ab04  mov     [rsp+0D0h+Sids], rax; Sids
0x18002ab09  lea     rax, [rbp+57h+var_90]
0x18002ab0d  mov     [rsp+0D0h+ReferencedDomains], rax; int
0x18002ab12  lea     r9, [rbp+57h+DestinationString]; Names
0x18002ab16  mov     edx, 80000000h; Flags
0x18002ab1b  mov     r8d, 1; Count
0x18002ab21  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18002ab25  call    cs:__imp_LsaLookupNames2
0x18002ab2b  mov     ebx, eax
0x18002ab2d  cmp     [rbp+57h+var_88], r14b
0x18002ab31  jz      short loc_18002AB4C
0x18002ab33  mov     r8, [rbp+57h+var_98]
0x18002ab37  mov     rcx, [r8]; Buffer
0x18002ab3a  mov     rdx, [rbp+57h+var_90]
0x18002ab3e  mov     [r8], rdx
0x18002ab41  test    rcx, rcx
0x18002ab44  jz      short loc_18002AB4C
0x18002ab46  call    cs:__imp_LsaFreeMemory
0x18002ab4c  cmp     [rbp+57h+var_70], r14b
0x18002ab50  jz      short loc_18002AB6B
0x18002ab52  mov     rdx, [rbp+57h+var_80]
0x18002ab56  mov     rcx, [rdx]; Buffer
0x18002ab59  mov     rax, [rbp+57h+var_78]
0x18002ab5d  mov     [rdx], rax
0x18002ab60  test    rcx, rcx
0x18002ab63  jz      short loc_18002AB6B
0x18002ab65  call    cs:__imp_LsaFreeMemory
0x18002ab6b  test    ebx, ebx
0x18002ab6d  jns     short loc_18002ABB8
0x18002ab6f  mov     rcx, [rbp+5Fh]; this
0x18002ab73  mov     r9d, ebx; char *
0x18002ab76  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ab7d  mov     edx, 2A0h; void *
0x18002ab82  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002ab87  mov     ebx, eax
0x18002ab89  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18002ab8d  mov     [rbp+57h+Buffer], r14
0x18002ab91  test    rcx, rcx
0x18002ab94  jz      short loc_18002AB9C
0x18002ab96  call    cs:__imp_LsaFreeMemory
0x18002ab9c  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18002aba0  test    rcx, rcx
0x18002aba3  mov     [rbp+57h+arg_18], r14
0x18002aba7  jz      loc_18002AA9E
0x18002abad  call    cs:__imp_LsaFreeMemory
0x18002abb3  jmp     loc_18002AA9E
0x18002abb8  mov     rcx, [rbp+57h+Buffer]
0x18002abbc  mov     eax, [rcx]
0x18002abbe  cmp     eax, 1
0x18002abc1  jz      short loc_18002ABF2
0x18002abc3  mov     rcx, [rbp+5Fh]; this
0x18002abc7  mov     dword ptr [rsp+0D0h+Sids], eax; char *
0x18002abcb  lea     rax, aUnexpectedSidT; "Unexpected SID type: 0x%x"
0x18002abd2  mov     [rsp+0D0h+ReferencedDomains], rax; int
0x18002abd7  mov     ebx, 8000FFFFh
0x18002abdc  mov     r9d, ebx; char *
0x18002abdf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002abe6  mov     edx, 2A1h; void *
0x18002abeb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002abf0  jmp     short loc_18002AB89
0x18002abf2  mov     rdi, [rbp+57h+hMem]
0x18002abf6  test    rdi, rdi
0x18002abf9  jz      short loc_18002AC18
0x18002abfb  call    cs:__imp_GetLastError
0x18002ac01  mov     ebx, eax
0x18002ac03  mov     rcx, rdi; hMem
0x18002ac06  call    cs:__imp_LocalFree
0x18002ac0c  mov     ecx, ebx; dwErrCode
0x18002ac0e  call    cs:__imp_SetLastError
0x18002ac14  mov     rcx, [rbp+57h+Buffer]
0x18002ac18  mov     [rbp+57h+hMem], r14
0x18002ac1c  lea     rdx, [rbp+57h+hMem]; StringSid
0x18002ac20  mov     rcx, [rcx+8]; Sid
0x18002ac24  call    cs:__imp_ConvertSidToStringSidW
0x18002ac2a  test    eax, eax
0x18002ac2c  jnz     short loc_18002AC48
0x18002ac2e  mov     rcx, [rbp+5Fh]; this
0x18002ac32  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ac39  mov     edx, 2A3h; void *
0x18002ac3e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ac43  jmp     loc_18002AB87
0x18002ac48  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18002ac4c  mov     [rbp+57h+Buffer], r14
0x18002ac50  test    rcx, rcx
0x18002ac53  jz      short loc_18002AC5B
0x18002ac55  call    cs:__imp_LsaFreeMemory
0x18002ac5b  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18002ac5f  mov     [rbp+57h+arg_18], r14
0x18002ac63  test    rcx, rcx
0x18002ac66  jz      short loc_18002AC6E
0x18002ac68  call    cs:__imp_LsaFreeMemory
0x18002ac6e  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18002ac72  test    rcx, rcx
0x18002ac75  jz      short loc_18002AC7D
0x18002ac77  call    cs:__imp_LsaClose
0x18002ac7d  mov     rcx, [rbp+57h+hMem]
0x18002ac81  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ac85  inc     rax
0x18002ac88  cmp     [rcx+rax*2], r14w
0x18002ac8d  jnz     short loc_18002AC85
0x18002ac8f  lea     rdi, [rax+1]
0x18002ac93  mov     [rbp+57h+Buffer], r14
0x18002ac97  lea     rdx, [rbp+57h+Buffer]
0x18002ac9b  mov     rcx, rdi
0x18002ac9e  call    CflApiNew__AllocBuffer_unsigned_short_
0x18002aca3  mov     ebx, eax
0x18002aca5  test    eax, eax
0x18002aca7  jns     short loc_18002ACD9
0x18002aca9  mov     rcx, [rbp+5Fh]; this
0x18002acad  mov     r9d, eax; char *
0x18002acb0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002acb7  mov     edx, 2A9h; void *
0x18002acbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acc1  nop
0x18002acc2  mov     rcx, [rbp+57h+Buffer]; hMem
0x18002acc6  test    rcx, rcx
0x18002acc9  jz      loc_18002AAAE
0x18002accf  call    CflFreeBuffer
0x18002acd4  jmp     loc_18002AAAE
0x18002acd9  mov     r8, [rbp+57h+hMem]; unsigned __int16 *
0x18002acdd  mov     rdx, rdi; unsigned __int64
0x18002ace0  mov     rbx, [rbp+57h+Buffer]
0x18002ace4  mov     rcx, rbx; unsigned __int16 *
0x18002ace7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002acec  mov     edi, eax
0x18002acee  test    eax, eax
0x18002acf0  jns     short loc_18002AD2C
0x18002acf2  mov     rcx, [rbp+5Fh]; this
0x18002acf6  mov     r9d, eax; char *
0x18002acf9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ad00  mov     edx, 2AAh; void *
0x18002ad05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ad0a  nop
0x18002ad0b  test    rbx, rbx
0x18002ad0e  jz      short loc_18002AD19
0x18002ad10  mov     rcx, rbx; hMem
0x18002ad13  call    CflFreeBuffer
0x18002ad18  nop
0x18002ad19  mov     rcx, [rbp+57h+hMem]; hMem
0x18002ad1d  test    rcx, rcx
0x18002ad20  jz      short loc_18002AD28
0x18002ad22  call    cs:__imp_LocalFree
0x18002ad28  mov     eax, edi
0x18002ad2a  jmp     short loc_18002AD40
0x18002ad2c  mov     [rsi], rbx
0x18002ad2f  mov     rcx, [rbp+57h+hMem]; hMem
0x18002ad33  test    rcx, rcx
0x18002ad36  jz      short loc_18002AD3E
0x18002ad38  call    cs:__imp_LocalFree
0x18002ad3e  xor     eax, eax
0x18002ad40  add     rsp, 0B0h
0x18002ad47  pop     r14
0x18002ad49  pop     rdi
0x18002ad4a  pop     rsi
0x18002ad4b  pop     rbx
0x18002ad4c  pop     rbp
0x18002ad4d  retn
```
