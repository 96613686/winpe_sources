# CflApi::HideTempUserAccountFromLogonUI

- ea: `0x18001eef8`
- end: `0x18001f2d1`
- name: `CflApi::HideTempUserAccountFromLogonUI`
- size: `985`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020a54`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x18001eef8`
- `0x18001f924`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001f0b0`
- `ntdll!RtlInitUnicodeString` at `0x18001f0b0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ef89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001f2a5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001ef89`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001f2a5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001efdb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001f295`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001efdb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001f295`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ef58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18001ef58`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001efaa`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001efaa`
- `SAMLIB!SamSetInformationUser` at `0x18001f220`
- `SAMLIB!SamSetInformationUser` at `0x18001f220`
- `SAMLIB!SamOpenUser` at `0x18001f1ba`
- `SAMLIB!SamOpenUser` at `0x18001f1ba`
- `SAMLIB!SamFreeMemory` at `0x18001f125`
- `SAMLIB!SamFreeMemory` at `0x18001f144`
- `SAMLIB!SamFreeMemory` at `0x18001f17a`
- `SAMLIB!SamFreeMemory` at `0x18001f193`
- `SAMLIB!SamFreeMemory` at `0x18001f250`
- `SAMLIB!SamFreeMemory` at `0x18001f265`
- `SAMLIB!SamFreeMemory` at `0x18001f125`
- `SAMLIB!SamFreeMemory` at `0x18001f144`
- `SAMLIB!SamFreeMemory` at `0x18001f17a`
- `SAMLIB!SamFreeMemory` at `0x18001f193`
- `SAMLIB!SamFreeMemory` at `0x18001f250`
- `SAMLIB!SamFreeMemory` at `0x18001f265`
- `SAMLIB!SamOpenDomain` at `0x18001f069`
- `SAMLIB!SamOpenDomain` at `0x18001f069`
- `SAMLIB!SamLookupNamesInDomain` at `0x18001f101`
- `SAMLIB!SamLookupNamesInDomain` at `0x18001f101`
- `SAMLIB!SamCloseHandle` at `0x18001f044`
- `SAMLIB!SamCloseHandle` at `0x18001f09a`
- `SAMLIB!SamCloseHandle` at `0x18001f1eb`
- `SAMLIB!SamCloseHandle` at `0x18001f23b`
- `SAMLIB!SamCloseHandle` at `0x18001f275`
- `SAMLIB!SamCloseHandle` at `0x18001f285`
- `SAMLIB!SamCloseHandle` at `0x18001f044`
- `SAMLIB!SamCloseHandle` at `0x18001f09a`
- `SAMLIB!SamCloseHandle` at `0x18001f1eb`
- `SAMLIB!SamCloseHandle` at `0x18001f23b`
- `SAMLIB!SamCloseHandle` at `0x18001f275`
- `SAMLIB!SamCloseHandle` at `0x18001f285`
- `SAMLIB!SamConnect` at `0x18001f013`
- `SAMLIB!SamConnect` at `0x18001f013`

## string_xrefs

- `0x18001ef69`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001efbb`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f024`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f07a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f155`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f1d0`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CflApi::HideTempUserAccountFromLogonUI(PCWSTR SourceString)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  NTSTATUS v5; // eax
  int v6; // eax
  int v7; // eax
  int v8; // ebx
  unsigned int *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned int *v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int *v16; // rcx
  int v17; // [rsp+20h] [rbp-E0h]
  unsigned int *v18; // [rsp+30h] [rbp-D0h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  PVOID Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int **v25; // [rsp+68h] [rbp-98h]
  unsigned int *v26; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+78h] [rbp-88h]
  __int64 *v28; // [rsp+80h] [rbp-80h]
  int v29[2]; // [rsp+88h] [rbp-78h] BYREF
  char v30; // [rsp+90h] [rbp-70h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD v33[10]; // [rsp+E0h] [rbp-20h] BYREF
  char v34; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  PolicyHandle = 0;
  v2 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x342,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v2,
           v17);
LABEL_3:
    if ( PolicyHandle )
      LsaClose(PolicyHandle);
    return v3;
  }
  Buffer = 0;
  v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  if ( v5 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x349,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v5,
           v17);
LABEL_8:
    if ( Buffer )
      LsaFreeMemory(Buffer);
    goto LABEL_3;
  }
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  v23 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = SamConnect(0, &v23, 32, &ObjectAttributes);
  if ( v6 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x352,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v6,
           v17);
LABEL_12:
    if ( v23 )
      SamCloseHandle();
    goto LABEL_8;
  }
  v22 = 0;
  v7 = SamOpenDomain(v23, 0x2000000, *((_QWORD *)Buffer + 2), &v22);
  if ( v7 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x35A,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v7,
           v17);
LABEL_16:
    if ( v22 )
      SamCloseHandle();
    goto LABEL_12;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v28 = &v20;
  v18 = 0;
  v25 = &v18;
  v20 = 0;
  *(_QWORD *)v29 = 0;
  v30 = 1;
  v26 = 0;
  v27 = 1;
  v8 = SamLookupNamesInDomain(v22, 1, &DestinationString, &v26);
  if ( v27 )
  {
    v9 = *v25;
    *v25 = v26;
    if ( v9 )
      SamFreeMemory();
  }
  if ( v30 )
  {
    v10 = *v28;
    *v28 = *(_QWORD *)v29;
    if ( v10 )
      SamFreeMemory();
  }
  if ( v8 < 0 )
  {
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x366,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v8,
           (int)v29);
LABEL_26:
    v11 = v20;
    v20 = 0;
    if ( v11 )
      SamFreeMemory();
    v12 = v18;
    v18 = 0;
    if ( v12 )
      SamFreeMemory();
    goto LABEL_16;
  }
  v24 = 0;
  v13 = SamOpenUser(v22, 0x2000000, *v18, &v24);
  if ( v13 < 0 )
  {
    v14 = 878;
    goto LABEL_32;
  }
  memset_0(v33, 0, 0xA8u);
  v33[0] = 0x4000;
  v34 = 1;
  v13 = SamSetInformationUser(v24, 28, v33);
  if ( v13 < 0 )
  {
    v14 = 887;
LABEL_32:
    v3 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v14,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           (const char *)(unsigned int)v13,
           (int)v29);
    if ( v24 )
      SamCloseHandle();
    goto LABEL_26;
  }
  if ( v24 )
    SamCloseHandle();
  v15 = v20;
  v20 = 0;
  if ( v15 )
    SamFreeMemory();
  v16 = v18;
  v18 = 0;
  if ( v16 )
    SamFreeMemory();
  if ( v22 )
    SamCloseHandle();
  if ( v23 )
    SamCloseHandle();
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return 0;
}

```

## disassembly

```asm
0x18001eef8  mov     [rsp-8+arg_8], rbx
0x18001eefd  mov     [rsp-8+arg_10], rdi
0x18001ef02  push    rbp
0x18001ef03  lea     rbp, [rsp-0A0h]
0x18001ef0b  sub     rsp, 1A0h
0x18001ef12  mov     rax, cs:__security_cookie
0x18001ef19  xor     rax, rsp
0x18001ef1c  mov     [rbp+0A0h+var_10], rax
0x18001ef23  xor     edi, edi
0x18001ef25  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18001ef2d  mov     rbx, rcx
0x18001ef30  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], rdi
0x18001ef34  xorps   xmm0, xmm0
0x18001ef37  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rdi
0x18001ef3b  lea     r9, [rsp+1A0h+PolicyHandle]; PolicyHandle
0x18001ef40  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rdi
0x18001ef44  lea     r8d, [rdi+1]; DesiredAccess
0x18001ef48  mov     [rsp+1A0h+PolicyHandle], rdi
0x18001ef4d  lea     rdx, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x18001ef51  xor     ecx, ecx; SystemName
0x18001ef53  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ef58  call    cs:__imp_LsaOpenPolicy
0x18001ef5e  test    eax, eax
0x18001ef60  jns     short loc_18001EF96
0x18001ef62  mov     rcx, [rbp+0A8h]; this
0x18001ef69  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ef70  mov     r9d, eax; char *
0x18001ef73  mov     edx, 342h; void *
0x18001ef78  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001ef7d  mov     ebx, eax
0x18001ef7f  mov     rcx, [rsp+1A0h+PolicyHandle]; ObjectHandle
0x18001ef84  test    rcx, rcx
0x18001ef87  jz      short loc_18001EF8F
0x18001ef89  call    cs:__imp_LsaClose
0x18001ef8f  mov     eax, ebx
0x18001ef91  jmp     loc_18001F2AD
0x18001ef96  mov     rcx, [rsp+1A0h+PolicyHandle]; PolicyHandle
0x18001ef9b  lea     r8, [rsp+1A0h+Buffer]; Buffer
0x18001efa0  mov     edx, 5; InformationClass
0x18001efa5  mov     [rsp+1A0h+Buffer], rdi
0x18001efaa  call    cs:__imp_LsaQueryInformationPolicy
0x18001efb0  test    eax, eax
0x18001efb2  jns     short loc_18001EFE3
0x18001efb4  mov     rcx, [rbp+0A8h]; this
0x18001efbb  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001efc2  mov     r9d, eax; char *
0x18001efc5  mov     edx, 349h; void *
0x18001efca  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001efcf  mov     ebx, eax
0x18001efd1  mov     rcx, [rsp+1A0h+Buffer]; Buffer
0x18001efd6  test    rcx, rcx
0x18001efd9  jz      short loc_18001EF7F
0x18001efdb  call    cs:__imp_LsaFreeMemory
0x18001efe1  jmp     short loc_18001EF7F
0x18001efe3  xorps   xmm0, xmm0
0x18001efe6  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x18001efed  lea     r9, [rbp+0A0h+ObjectAttributes]
0x18001eff1  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rdi
0x18001eff5  mov     r8d, 20h ; ' '
0x18001effb  mov     [rbp+0A0h+ObjectAttributes.Attributes], edi
0x18001effe  lea     rdx, [rsp+1A0h+var_148]
0x18001f003  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rdi
0x18001f007  xor     ecx, ecx
0x18001f009  mov     [rsp+1A0h+var_148], rdi
0x18001f00e  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001f013  call    cs:__imp_SamConnect
0x18001f019  test    eax, eax
0x18001f01b  jns     short loc_18001F04C
0x18001f01d  mov     rcx, [rbp+0A8h]; this
0x18001f024  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f02b  mov     r9d, eax; char *
0x18001f02e  mov     edx, 352h; void *
0x18001f033  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f038  mov     ebx, eax
0x18001f03a  mov     rcx, [rsp+1A0h+var_148]
0x18001f03f  test    rcx, rcx
0x18001f042  jz      short loc_18001EFD1
0x18001f044  call    cs:__imp_SamCloseHandle
0x18001f04a  jmp     short loc_18001EFD1
0x18001f04c  mov     r8, [rsp+1A0h+Buffer]
0x18001f051  lea     r9, [rsp+1A0h+var_150]
0x18001f056  mov     rcx, [rsp+1A0h+var_148]
0x18001f05b  mov     edx, 2000000h
0x18001f060  mov     [rsp+1A0h+var_150], rdi
0x18001f065  mov     r8, [r8+10h]
0x18001f069  call    cs:__imp_SamOpenDomain
0x18001f06f  test    eax, eax
0x18001f071  jns     short loc_18001F0A2
0x18001f073  mov     rcx, [rbp+0A8h]; this
0x18001f07a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f081  mov     r9d, eax; char *
0x18001f084  mov     edx, 35Ah; void *
0x18001f089  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f08e  mov     ebx, eax
0x18001f090  mov     rcx, [rsp+1A0h+var_150]
0x18001f095  test    rcx, rcx
0x18001f098  jz      short loc_18001F03A
0x18001f09a  call    cs:__imp_SamCloseHandle
0x18001f0a0  jmp     short loc_18001F03A
0x18001f0a2  xorps   xmm0, xmm0
0x18001f0a5  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x18001f0a9  mov     rdx, rbx; SourceString
0x18001f0ac  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x18001f0b0  call    cs:__imp_RtlInitUnicodeString
0x18001f0b6  mov     rcx, [rsp+1A0h+var_150]
0x18001f0bb  lea     rax, [rsp+1A0h+var_160]
0x18001f0c0  mov     [rbp+0A0h+var_120], rax
0x18001f0c4  lea     r9, [rsp+1A0h+var_130]
0x18001f0c9  lea     rax, [rsp+1A0h+var_170]
0x18001f0ce  mov     [rsp+1A0h+var_170], rdi
0x18001f0d3  mov     [rsp+1A0h+var_138], rax
0x18001f0d8  lea     r8, [rbp+0A0h+DestinationString]
0x18001f0dc  lea     rax, [rbp+0A0h+var_118]
0x18001f0e0  mov     [rsp+1A0h+var_160], rdi
0x18001f0e5  mov     edx, 1
0x18001f0ea  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18001f0ef  mov     qword ptr [rbp+0A0h+var_118], rdi
0x18001f0f3  mov     [rbp+0A0h+var_110], 1
0x18001f0f7  mov     [rsp+1A0h+var_130], rdi
0x18001f0fc  mov     [rsp+1A0h+var_128], 1
0x18001f101  call    cs:__imp_SamLookupNamesInDomain
0x18001f107  mov     ebx, eax
0x18001f109  cmp     [rsp+1A0h+var_128], dil
0x18001f10e  jz      short loc_18001F12B
0x18001f110  mov     r8, [rsp+1A0h+var_138]
0x18001f115  mov     rdx, [rsp+1A0h+var_130]
0x18001f11a  mov     rcx, [r8]
0x18001f11d  mov     [r8], rdx
0x18001f120  test    rcx, rcx
0x18001f123  jz      short loc_18001F12B
0x18001f125  call    cs:__imp_SamFreeMemory
0x18001f12b  cmp     [rbp+0A0h+var_110], dil
0x18001f12f  jz      short loc_18001F14A
0x18001f131  mov     rdx, [rbp+0A0h+var_120]
0x18001f135  mov     rax, qword ptr [rbp+0A0h+var_118]
0x18001f139  mov     rcx, [rdx]
0x18001f13c  mov     [rdx], rax
0x18001f13f  test    rcx, rcx
0x18001f142  jz      short loc_18001F14A
0x18001f144  call    cs:__imp_SamFreeMemory
0x18001f14a  test    ebx, ebx
0x18001f14c  jns     short loc_18001F19E
0x18001f14e  mov     rcx, [rbp+0A8h]; this
0x18001f155  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f15c  mov     r9d, ebx; char *
0x18001f15f  mov     edx, 366h; void *
0x18001f164  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f169  mov     ebx, eax
0x18001f16b  mov     rcx, [rsp+1A0h+var_160]
0x18001f170  mov     [rsp+1A0h+var_160], rdi
0x18001f175  test    rcx, rcx
0x18001f178  jz      short loc_18001F180
0x18001f17a  call    cs:__imp_SamFreeMemory
0x18001f180  mov     rcx, [rsp+1A0h+var_170]
0x18001f185  mov     [rsp+1A0h+var_170], rdi
0x18001f18a  test    rcx, rcx
0x18001f18d  jz      loc_18001F090
0x18001f193  call    cs:__imp_SamFreeMemory
0x18001f199  jmp     loc_18001F090
0x18001f19e  mov     r8, [rsp+1A0h+var_170]
0x18001f1a3  lea     r9, [rsp+1A0h+var_140]
0x18001f1a8  mov     rcx, [rsp+1A0h+var_150]
0x18001f1ad  mov     edx, 2000000h
0x18001f1b2  mov     [rsp+1A0h+var_140], rdi
0x18001f1b7  mov     r8d, [r8]
0x18001f1ba  call    cs:__imp_SamOpenUser
0x18001f1c0  test    eax, eax
0x18001f1c2  jns     short loc_18001F1F6
0x18001f1c4  mov     edx, 36Eh; void *
0x18001f1c9  mov     rcx, [rbp+0A8h]; this
0x18001f1d0  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f1d7  mov     r9d, eax; char *
0x18001f1da  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001f1df  mov     rcx, [rsp+1A0h+var_140]
0x18001f1e4  mov     ebx, eax
0x18001f1e6  test    rcx, rcx
0x18001f1e9  jz      short loc_18001F16B
0x18001f1eb  call    cs:__imp_SamCloseHandle
0x18001f1f1  jmp     loc_18001F16B
0x18001f1f6  xor     edx, edx; Val
0x18001f1f8  lea     rcx, [rbp+0A0h+var_C0]; void *
0x18001f1fc  mov     r8d, 0A8h; Size
0x18001f202  call    memset_0
0x18001f207  mov     rcx, [rsp+1A0h+var_140]
0x18001f20c  lea     r8, [rbp+0A0h+var_C0]
0x18001f210  mov     edx, 1Ch
0x18001f215  mov     [rbp+0A0h+var_C0], 4000h
0x18001f21c  mov     [rbp+0A0h+var_98], 1
0x18001f220  call    cs:__imp_SamSetInformationUser
0x18001f226  test    eax, eax
0x18001f228  jns     short loc_18001F231
0x18001f22a  mov     edx, 377h
0x18001f22f  jmp     short loc_18001F1C9
0x18001f231  mov     rcx, [rsp+1A0h+var_140]
0x18001f236  test    rcx, rcx
0x18001f239  jz      short loc_18001F241
0x18001f23b  call    cs:__imp_SamCloseHandle
0x18001f241  mov     rcx, [rsp+1A0h+var_160]
0x18001f246  mov     [rsp+1A0h+var_160], rdi
0x18001f24b  test    rcx, rcx
0x18001f24e  jz      short loc_18001F256
0x18001f250  call    cs:__imp_SamFreeMemory
0x18001f256  mov     rcx, [rsp+1A0h+var_170]
0x18001f25b  mov     [rsp+1A0h+var_170], rdi
0x18001f260  test    rcx, rcx
0x18001f263  jz      short loc_18001F26B
0x18001f265  call    cs:__imp_SamFreeMemory
0x18001f26b  mov     rcx, [rsp+1A0h+var_150]
0x18001f270  test    rcx, rcx
0x18001f273  jz      short loc_18001F27B
0x18001f275  call    cs:__imp_SamCloseHandle
0x18001f27b  mov     rcx, [rsp+1A0h+var_148]
0x18001f280  test    rcx, rcx
0x18001f283  jz      short loc_18001F28B
0x18001f285  call    cs:__imp_SamCloseHandle
0x18001f28b  mov     rcx, [rsp+1A0h+Buffer]; Buffer
0x18001f290  test    rcx, rcx
0x18001f293  jz      short loc_18001F29B
0x18001f295  call    cs:__imp_LsaFreeMemory
0x18001f29b  mov     rcx, [rsp+1A0h+PolicyHandle]; ObjectHandle
0x18001f2a0  test    rcx, rcx
0x18001f2a3  jz      short loc_18001F2AB
0x18001f2a5  call    cs:__imp_LsaClose
0x18001f2ab  xor     eax, eax
0x18001f2ad  mov     rcx, [rbp+0A0h+var_10]
0x18001f2b4  xor     rcx, rsp; StackCookie
0x18001f2b7  call    __security_check_cookie
0x18001f2bc  lea     r11, [rsp+1A0h+var_s0]
0x18001f2c4  mov     rbx, [r11+18h]
0x18001f2c8  mov     rdi, [r11+20h]
0x18001f2cc  mov     rsp, r11
0x18001f2cf  pop     rbp
0x18001f2d0  retn
```
