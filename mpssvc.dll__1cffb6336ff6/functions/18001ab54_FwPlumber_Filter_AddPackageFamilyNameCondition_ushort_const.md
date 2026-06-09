# FwPlumber::Filter::AddPackageFamilyNameCondition(ushort const *)

- ea: `0x18001ab54`
- end: `0x18001ad4b`
- name: `?AddPackageFamilyNameCondition@Filter@FwPlumber@@QEAAXPEBG@Z`
- size: `503`
- prototype: `void __fastcall(FwPlumber::Filter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000da60`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x180018050`
- `0x18001a4e4`
- `0x18001a780`
- `0x18001ab54`
- `0x18006f520`
- `0x1800738d6`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001ac67`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001ac67`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001ac22`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001ac22`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001ac09`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001ac09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001abf8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001abf8`
- `fwbase!FwFree` at `0x18001acb6`
- `fwbase!FwFree` at `0x18001acb6`
- `fwbase!FwCreateSDDLStringFromPackageFamilyName` at `0x18001abb6`
- `fwbase!FwCreateSDDLStringFromPackageFamilyName` at `0x18001abb6`

## pseudocode

```c
void __fastcall FwPlumber::Filter::AddPackageFamilyNameCondition(FwPlumber::Filter *this, const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  int v5; // edx
  unsigned int valid; // eax
  int v7; // edx
  unsigned int SecurityDescriptorControl; // eax
  int v9; // edx
  DWORD SecurityDescriptorLength; // edi
  struct FWPM_FILTER_CONDITION0_ *Condition; // rbx
  DWORD *v12; // rax
  int pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  LPCWSTR *p_StringSecurityDescriptor; // [rsp+28h] [rbp-38h]
  char v15; // [rsp+30h] [rbp-30h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-28h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+40h] [rbp-20h] BYREF
  WORD pControl[2]; // [rsp+48h] [rbp-18h] BYREF
  DWORD dwRevision; // [rsp+4Ch] [rbp-14h] BYREF

  pControl[0] = 0;
  dwRevision = 0;
  StringSecurityDescriptor = 0;
  p_StringSecurityDescriptor = &StringSecurityDescriptor;
  v15 = 1;
  SecurityDescriptor = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 69, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  if ( (int)FwCreateSDDLStringFromPackageFamilyName(a2, &StringSecurityDescriptor) < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_489b48d90f353cde71bd342750f78ef2_Traceguids,
        2147942487LL);
    pExceptionObject = -2147024809;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0);
  FwPlumber::ThrowIf32Bool((FwPlumber *)v4, v5);
  valid = IsValidSecurityDescriptor(SecurityDescriptor);
  FwPlumber::ThrowIf32Bool((FwPlumber *)valid, v7);
  SecurityDescriptorControl = GetSecurityDescriptorControl(SecurityDescriptor, pControl, &dwRevision);
  FwPlumber::ThrowIf32Bool((FwPlumber *)SecurityDescriptorControl, v9);
  if ( (pControl[0] & 0x8000u) == 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_489b48d90f353cde71bd342750f78ef2_Traceguids,
        2147942487LL);
    pExceptionObject = -2147024809;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
  Condition = FwPlumber::Filter::NextCondition(this);
  Condition->fieldKey = (GUID)FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME;
  Condition->matchType = FWP_MATCH_EQUAL;
  Condition->conditionValue.type = FWP_SECURITY_DESCRIPTOR_TYPE;
  v12 = (DWORD *)FwPlumber::Filter::Allocate<FWP_BYTE_BLOB_>(this);
  Condition->conditionValue.uint64 = (UINT64 *)v12;
  *v12 = SecurityDescriptorLength;
  Condition->conditionValue.uint64[1] = (UINT64)SecurityDescriptor;
  if ( StringSecurityDescriptor )
    FwFree(StringSecurityDescriptor);
}

```

## disassembly

```asm
0x18001ab54  mov     [rsp-18h+arg_10], rbx
0x18001ab59  push    rbp
0x18001ab5a  push    rsi
0x18001ab5b  push    rdi
0x18001ab5c  mov     rbp, rsp
0x18001ab5f  sub     rsp, 60h
0x18001ab63  mov     rax, cs:__security_cookie
0x18001ab6a  xor     rax, rsp
0x18001ab6d  mov     [rbp+var_10], rax
0x18001ab71  mov     rbx, rdx
0x18001ab74  mov     rsi, rcx
0x18001ab77  xor     eax, eax
0x18001ab79  mov     [rbp+pControl], ax
0x18001ab7d  mov     [rbp+dwRevision], eax
0x18001ab80  mov     [rbp+StringSecurityDescriptor], rax
0x18001ab84  lea     rax, [rbp+StringSecurityDescriptor]
0x18001ab88  mov     [rbp+var_38], rax
0x18001ab8c  mov     [rbp+var_30], 1
0x18001ab90  mov     [rbp+SecurityDescriptor], 0
0x18001ab98  lea     rdi, WPP_GLOBAL_Control
0x18001ab9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aba6  cmp     rcx, rdi
0x18001aba9  jnz     loc_18001ACD8
0x18001abaf  lea     rdx, [rbp+StringSecurityDescriptor]
0x18001abb3  mov     rcx, rbx
0x18001abb6  call    cs:__imp_FwCreateSDDLStringFromPackageFamilyName
0x18001abbc  test    eax, eax
0x18001abbe  jns     short loc_18001ABE9
0x18001abc0  mov     ebx, 80070057h
0x18001abc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abcc  cmp     rcx, rdi
0x18001abcf  jnz     loc_18001ACFC
0x18001abd5  mov     [rbp+pExceptionObject], ebx
0x18001abd8  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001abdf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001abe3  call    _CxxThrowException_0
0x18001abe9  xor     r9d, r9d; SecurityDescriptorSize
0x18001abec  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001abf0  lea     edx, [r9+1]; StringSDRevision
0x18001abf4  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001abf8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001abfe  mov     ecx, eax; this
0x18001ac00  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001ac05  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001ac09  call    cs:__imp_IsValidSecurityDescriptor
0x18001ac0f  mov     ecx, eax; this
0x18001ac11  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001ac16  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18001ac1a  lea     rdx, [rbp+pControl]; pControl
0x18001ac1e  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001ac22  call    cs:__imp_GetSecurityDescriptorControl
0x18001ac28  mov     ecx, eax; this
0x18001ac2a  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001ac2f  mov     eax, 8000h
0x18001ac34  test    [rbp+pControl], ax
0x18001ac38  jnz     short loc_18001AC63
0x18001ac3a  mov     ebx, 80070057h
0x18001ac3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac46  cmp     rcx, rdi
0x18001ac49  jnz     loc_18001AD23
0x18001ac4f  mov     [rbp+pExceptionObject], ebx
0x18001ac52  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001ac59  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ac5d  call    _CxxThrowException_0
0x18001ac63  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001ac67  call    cs:__imp_GetSecurityDescriptorLength
0x18001ac6d  mov     edi, eax
0x18001ac6f  mov     rcx, rsi; this
0x18001ac72  call    ?NextCondition@Filter@FwPlumber@@IEAAAEAUFWPM_FILTER_CONDITION0_@@XZ; FwPlumber::Filter::NextCondition(void)
0x18001ac77  mov     rbx, rax
0x18001ac7a  movups  xmm0, cs:FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME
0x18001ac81  movdqu  xmmword ptr [rax], xmm0
0x18001ac85  mov     dword ptr [rax+10h], 0
0x18001ac8c  mov     dword ptr [rax+18h], 0Eh
0x18001ac93  mov     rcx, rsi
0x18001ac96  call    ??$Allocate@UFWP_BYTE_BLOB_@@@Filter@FwPlumber@@IEAAPEAUFWP_BYTE_BLOB_@@I@Z; FwPlumber::Filter::Allocate<FWP_BYTE_BLOB_>(uint)
0x18001ac9b  mov     [rbx+20h], rax
0x18001ac9f  mov     [rax], edi
0x18001aca1  mov     rcx, [rbx+20h]
0x18001aca5  mov     rax, [rbp+SecurityDescriptor]
0x18001aca9  mov     [rcx+8], rax
0x18001acad  mov     rcx, [rbp+StringSecurityDescriptor]
0x18001acb1  test    rcx, rcx
0x18001acb4  jz      short loc_18001ACBC
0x18001acb6  call    cs:__imp_FwFree
0x18001acbc  mov     rcx, [rbp+var_10]
0x18001acc0  xor     rcx, rsp; StackCookie
0x18001acc3  call    __security_check_cookie
0x18001acc8  mov     rbx, [rsp+60h+arg_10]
0x18001acd0  add     rsp, 60h
0x18001acd4  pop     rdi
0x18001acd5  pop     rsi
0x18001acd6  pop     rbp
0x18001acd7  retn
0x18001acd8  test    byte ptr [rcx+1Ch], 8
0x18001acdc  jz      loc_18001ABAF
0x18001ace2  mov     edx, 45h ; 'E'
0x18001ace7  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18001acee  mov     rcx, [rcx+10h]
0x18001acf2  call    WPP_SF_
0x18001acf7  jmp     loc_18001ABAF
0x18001acfc  test    byte ptr [rcx+1Ch], 1
0x18001ad00  jz      loc_18001ABD5
0x18001ad06  mov     edx, 0Ch
0x18001ad0b  mov     r9d, ebx
0x18001ad0e  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18001ad15  mov     rcx, [rcx+10h]
0x18001ad19  call    WPP_SF_d
0x18001ad1e  jmp     loc_18001ABD5
0x18001ad23  test    byte ptr [rcx+1Ch], 1
0x18001ad27  jz      loc_18001AC4F
0x18001ad2d  mov     edx, 0Ch
0x18001ad32  mov     r9d, ebx
0x18001ad35  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18001ad3c  mov     rcx, [rcx+10h]
0x18001ad40  call    WPP_SF_d
0x18001ad45  jmp     loc_18001AC4F
```
