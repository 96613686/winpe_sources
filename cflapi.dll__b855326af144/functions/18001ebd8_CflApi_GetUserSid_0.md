# CflApi::GetUserSid_0

- ea: `0x18001ebd8`
- end: `0x18001eef2`
- name: `CflApi::GetUserSid_0`
- size: `794`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e970`

## callees

- `0x1800067a4`
- `0x1800067c4`
- `0x1800071b4`
- `0x180010700`
- `0x18001332c`
- `0x18001ebd8`
- `0x18001f8e4`
- `0x18001f924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001edb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001edb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eedc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ec5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001eedc`
- `ntdll!RtlInitUnicodeString` at `0x18001ec76`
- `ntdll!RtlInitUnicodeString` at `0x18001ec76`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ec4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ee1b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ec4b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ee1b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ecea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed09`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed3a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001edf9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ee0c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ecea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed09`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed3a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ed51`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001edf9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001ee0c`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ec1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ec1e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18001ecc9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x18001ecc9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001edc8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001edc8`

## string_xrefs

- `0x18001ec2f`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ed1a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ed83`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001edd6`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ee54`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ee9d`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ed6f`: `Unexpected SID type: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CflApi::GetUserSid_0(PCWSTR SourceString, _QWORD *a2)
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
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
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
           (void *)0x514,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
            (void *)0x51B,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      (void *)0x51C,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
            (void *)0x51E,
            (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      (void *)0x524,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
      (void *)0x525,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
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
0x18001ebd8  push    rbp
0x18001ebda  push    rbx
0x18001ebdb  push    rsi
0x18001ebdc  push    rdi
0x18001ebdd  push    r14
0x18001ebdf  lea     rbp, [rsp-37h]
0x18001ebe4  sub     rsp, 0B0h
0x18001ebeb  mov     rsi, rdx
0x18001ebee  mov     rbx, rcx
0x18001ebf1  xor     r14d, r14d
0x18001ebf4  mov     [rdx], r14
0x18001ebf7  mov     [rbp+57h+hMem], r14
0x18001ebfb  xorps   xmm0, xmm0
0x18001ebfe  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001ec02  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001ec06  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ec0a  mov     [rbp+57h+PolicyHandle], r14
0x18001ec0e  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18001ec12  mov     r8d, 801h; DesiredAccess
0x18001ec18  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001ec1c  xor     ecx, ecx; SystemName
0x18001ec1e  call    cs:__imp_LsaOpenPolicy
0x18001ec24  test    eax, eax
0x18001ec26  jns     short loc_18001EC68
0x18001ec28  mov     rcx, [rbp+5Fh]; this
0x18001ec2c  mov     r9d, eax; char *
0x18001ec2f  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ec36  mov     edx, 514h; void *
0x18001ec3b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ec40  mov     ebx, eax
0x18001ec42  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18001ec46  test    rcx, rcx
0x18001ec49  jz      short loc_18001EC52
0x18001ec4b  call    cs:__imp_LsaClose
0x18001ec51  nop
0x18001ec52  mov     rcx, [rbp+57h+hMem]; hMem
0x18001ec56  test    rcx, rcx
0x18001ec59  jz      short loc_18001EC61
0x18001ec5b  call    cs:__imp_LocalFree
0x18001ec61  mov     eax, ebx
0x18001ec63  jmp     loc_18001EEE4
0x18001ec68  xorps   xmm0, xmm0
0x18001ec6b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001ec6f  mov     rdx, rbx; SourceString
0x18001ec72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001ec76  call    cs:__imp_RtlInitUnicodeString
0x18001ec7c  mov     [rbp+57h+arg_18], r14
0x18001ec80  mov     [rbp+57h+Buffer], r14
0x18001ec84  lea     rax, [rbp+57h+Buffer]
0x18001ec88  mov     [rbp+57h+var_80], rax
0x18001ec8c  mov     [rbp+57h+var_78], r14
0x18001ec90  mov     [rbp+57h+var_70], 1
0x18001ec94  lea     rax, [rbp+57h+arg_18]
0x18001ec98  mov     [rbp+57h+var_98], rax
0x18001ec9c  mov     [rbp+57h+var_90], r14
0x18001eca0  mov     [rbp+57h+var_88], 1
0x18001eca4  lea     rax, [rbp+57h+var_78]
0x18001eca8  mov     [rsp+0D0h+Sids], rax; Sids
0x18001ecad  lea     rax, [rbp+57h+var_90]
0x18001ecb1  mov     [rsp+0D0h+ReferencedDomains], rax; int
0x18001ecb6  lea     r9, [rbp+57h+DestinationString]; Names
0x18001ecba  mov     edx, 80000000h; Flags
0x18001ecbf  mov     r8d, 1; Count
0x18001ecc5  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18001ecc9  call    cs:__imp_LsaLookupNames2
0x18001eccf  mov     ebx, eax
0x18001ecd1  cmp     [rbp+57h+var_88], r14b
0x18001ecd5  jz      short loc_18001ECF0
0x18001ecd7  mov     r8, [rbp+57h+var_98]
0x18001ecdb  mov     rcx, [r8]; Buffer
0x18001ecde  mov     rdx, [rbp+57h+var_90]
0x18001ece2  mov     [r8], rdx
0x18001ece5  test    rcx, rcx
0x18001ece8  jz      short loc_18001ECF0
0x18001ecea  call    cs:__imp_LsaFreeMemory
0x18001ecf0  cmp     [rbp+57h+var_70], r14b
0x18001ecf4  jz      short loc_18001ED0F
0x18001ecf6  mov     rdx, [rbp+57h+var_80]
0x18001ecfa  mov     rcx, [rdx]; Buffer
0x18001ecfd  mov     rax, [rbp+57h+var_78]
0x18001ed01  mov     [rdx], rax
0x18001ed04  test    rcx, rcx
0x18001ed07  jz      short loc_18001ED0F
0x18001ed09  call    cs:__imp_LsaFreeMemory
0x18001ed0f  test    ebx, ebx
0x18001ed11  jns     short loc_18001ED5C
0x18001ed13  mov     rcx, [rbp+5Fh]; this
0x18001ed17  mov     r9d, ebx; char *
0x18001ed1a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ed21  mov     edx, 51Bh; void *
0x18001ed26  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ed2b  mov     ebx, eax
0x18001ed2d  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18001ed31  mov     [rbp+57h+Buffer], r14
0x18001ed35  test    rcx, rcx
0x18001ed38  jz      short loc_18001ED40
0x18001ed3a  call    cs:__imp_LsaFreeMemory
0x18001ed40  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18001ed44  test    rcx, rcx
0x18001ed47  mov     [rbp+57h+arg_18], r14
0x18001ed4b  jz      loc_18001EC42
0x18001ed51  call    cs:__imp_LsaFreeMemory
0x18001ed57  jmp     loc_18001EC42
0x18001ed5c  mov     rcx, [rbp+57h+Buffer]
0x18001ed60  mov     eax, [rcx]
0x18001ed62  cmp     eax, 1
0x18001ed65  jz      short loc_18001ED96
0x18001ed67  mov     rcx, [rbp+5Fh]; this
0x18001ed6b  mov     dword ptr [rsp+0D0h+Sids], eax; char *
0x18001ed6f  lea     rax, aUnexpectedSidT; "Unexpected SID type: 0x%x"
0x18001ed76  mov     [rsp+0D0h+ReferencedDomains], rax; int
0x18001ed7b  mov     ebx, 8000FFFFh
0x18001ed80  mov     r9d, ebx; char *
0x18001ed83  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ed8a  mov     edx, 51Ch; void *
0x18001ed8f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001ed94  jmp     short loc_18001ED2D
0x18001ed96  mov     rdi, [rbp+57h+hMem]
0x18001ed9a  test    rdi, rdi
0x18001ed9d  jz      short loc_18001EDBC
0x18001ed9f  call    cs:__imp_GetLastError
0x18001eda5  mov     ebx, eax
0x18001eda7  mov     rcx, rdi; hMem
0x18001edaa  call    cs:__imp_LocalFree
0x18001edb0  mov     ecx, ebx; dwErrCode
0x18001edb2  call    cs:__imp_SetLastError
0x18001edb8  mov     rcx, [rbp+57h+Buffer]
0x18001edbc  mov     [rbp+57h+hMem], r14
0x18001edc0  lea     rdx, [rbp+57h+hMem]; StringSid
0x18001edc4  mov     rcx, [rcx+8]; Sid
0x18001edc8  call    cs:__imp_ConvertSidToStringSidW
0x18001edce  test    eax, eax
0x18001edd0  jnz     short loc_18001EDEC
0x18001edd2  mov     rcx, [rbp+5Fh]; this
0x18001edd6  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001eddd  mov     edx, 51Eh; void *
0x18001ede2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ede7  jmp     loc_18001ED2B
0x18001edec  mov     rcx, [rbp+57h+Buffer]; Buffer
0x18001edf0  mov     [rbp+57h+Buffer], r14
0x18001edf4  test    rcx, rcx
0x18001edf7  jz      short loc_18001EDFF
0x18001edf9  call    cs:__imp_LsaFreeMemory
0x18001edff  mov     rcx, [rbp+57h+arg_18]; Buffer
0x18001ee03  mov     [rbp+57h+arg_18], r14
0x18001ee07  test    rcx, rcx
0x18001ee0a  jz      short loc_18001EE12
0x18001ee0c  call    cs:__imp_LsaFreeMemory
0x18001ee12  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18001ee16  test    rcx, rcx
0x18001ee19  jz      short loc_18001EE21
0x18001ee1b  call    cs:__imp_LsaClose
0x18001ee21  mov     rcx, [rbp+57h+hMem]
0x18001ee25  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee29  inc     rax
0x18001ee2c  cmp     [rcx+rax*2], r14w
0x18001ee31  jnz     short loc_18001EE29
0x18001ee33  lea     rdi, [rax+1]
0x18001ee37  mov     [rbp+57h+Buffer], r14
0x18001ee3b  lea     rdx, [rbp+57h+Buffer]
0x18001ee3f  mov     rcx, rdi
0x18001ee42  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001ee47  mov     ebx, eax
0x18001ee49  test    eax, eax
0x18001ee4b  jns     short loc_18001EE7D
0x18001ee4d  mov     rcx, [rbp+5Fh]; this
0x18001ee51  mov     r9d, eax; char *
0x18001ee54  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ee5b  mov     edx, 524h; void *
0x18001ee60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee65  nop
0x18001ee66  mov     rcx, [rbp+57h+Buffer]; hMem
0x18001ee6a  test    rcx, rcx
0x18001ee6d  jz      loc_18001EC52
0x18001ee73  call    CflFreeBuffer
0x18001ee78  jmp     loc_18001EC52
0x18001ee7d  mov     r8, [rbp+57h+hMem]; unsigned __int16 *
0x18001ee81  mov     rdx, rdi; unsigned __int64
0x18001ee84  mov     rbx, [rbp+57h+Buffer]
0x18001ee88  mov     rcx, rbx; unsigned __int16 *
0x18001ee8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ee90  mov     edi, eax
0x18001ee92  test    eax, eax
0x18001ee94  jns     short loc_18001EED0
0x18001ee96  mov     rcx, [rbp+5Fh]; this
0x18001ee9a  mov     r9d, eax; char *
0x18001ee9d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001eea4  mov     edx, 525h; void *
0x18001eea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eeae  nop
0x18001eeaf  test    rbx, rbx
0x18001eeb2  jz      short loc_18001EEBD
0x18001eeb4  mov     rcx, rbx; hMem
0x18001eeb7  call    CflFreeBuffer
0x18001eebc  nop
0x18001eebd  mov     rcx, [rbp+57h+hMem]; hMem
0x18001eec1  test    rcx, rcx
0x18001eec4  jz      short loc_18001EECC
0x18001eec6  call    cs:__imp_LocalFree
0x18001eecc  mov     eax, edi
0x18001eece  jmp     short loc_18001EEE4
0x18001eed0  mov     [rsi], rbx
0x18001eed3  mov     rcx, [rbp+57h+hMem]; hMem
0x18001eed7  test    rcx, rcx
0x18001eeda  jz      short loc_18001EEE2
0x18001eedc  call    cs:__imp_LocalFree
0x18001eee2  xor     eax, eax
0x18001eee4  add     rsp, 0B0h
0x18001eeeb  pop     r14
0x18001eeed  pop     rdi
0x18001eeee  pop     rsi
0x18001eeef  pop     rbx
0x18001eef0  pop     rbp
0x18001eef1  retn
```
