# FwPlumber::Filter::AddPackageFamilyNameCondition(ushort const *)

- ea: `0x18001ce88`
- end: `0x18001d0a4`
- name: `?AddPackageFamilyNameCondition@Filter@FwPlumber@@QEAAXPEBG@Z`
- size: `540`
- prototype: `void __fastcall(FwPlumber::Filter *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d34c`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18001a220`
- `0x18001c814`
- `0x18001cab0`
- `0x18001ce88`
- `0x1800729c0`
- `0x180076d96`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001cfb3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001cfb3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001cf68`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001cf68`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001cf49`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x18001cf49`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cf32`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001cf32`
- `fwbase!FwFree` at `0x18001d008`
- `fwbase!FwFree` at `0x18001d008`
- `fwbase!FwCreateSDDLStringFromPackageFamilyName` at `0x18001ceea`
- `fwbase!FwCreateSDDLStringFromPackageFamilyName` at `0x18001ceea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 69, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
  if ( (int)FwCreateSDDLStringFromPackageFamilyName(a2, &StringSecurityDescriptor) < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        12,
        WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids,
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
        WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids,
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
0x18001ce88  mov     [rsp-18h+arg_10], rbx
0x18001ce8d  push    rbp
0x18001ce8e  push    rsi
0x18001ce8f  push    rdi
0x18001ce90  mov     rbp, rsp
0x18001ce93  sub     rsp, 60h
0x18001ce97  mov     rax, cs:__security_cookie
0x18001ce9e  xor     rax, rsp
0x18001cea1  mov     [rbp+var_10], rax
0x18001cea5  mov     rbx, rdx
0x18001cea8  mov     rsi, rcx
0x18001ceab  xor     eax, eax
0x18001cead  mov     [rbp+pControl], ax
0x18001ceb1  mov     [rbp+dwRevision], eax
0x18001ceb4  mov     [rbp+StringSecurityDescriptor], rax
0x18001ceb8  lea     rax, [rbp+StringSecurityDescriptor]
0x18001cebc  mov     [rbp+var_38], rax
0x18001cec0  mov     [rbp+var_30], 1
0x18001cec4  mov     [rbp+SecurityDescriptor], 0
0x18001cecc  lea     rdi, WPP_GLOBAL_Control
0x18001ced3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceda  cmp     rcx, rdi
0x18001cedd  jnz     loc_18001D031
0x18001cee3  lea     rdx, [rbp+StringSecurityDescriptor]
0x18001cee7  mov     rcx, rbx
0x18001ceea  call    cs:__imp_FwCreateSDDLStringFromPackageFamilyName
0x18001cef1  nop     dword ptr [rax+rax+00h]
0x18001cef6  test    eax, eax
0x18001cef8  jns     short loc_18001CF23
0x18001cefa  mov     ebx, 80070057h
0x18001ceff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf06  cmp     rcx, rdi
0x18001cf09  jnz     loc_18001D055
0x18001cf0f  mov     [rbp+pExceptionObject], ebx
0x18001cf12  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001cf19  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001cf1d  call    _CxxThrowException_0
0x18001cf23  xor     r9d, r9d; SecurityDescriptorSize
0x18001cf26  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001cf2a  lea     edx, [r9+1]; StringSDRevision
0x18001cf2e  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18001cf32  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001cf39  nop     dword ptr [rax+rax+00h]
0x18001cf3e  mov     ecx, eax; this
0x18001cf40  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001cf45  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001cf49  call    cs:__imp_IsValidSecurityDescriptor
0x18001cf50  nop     dword ptr [rax+rax+00h]
0x18001cf55  mov     ecx, eax; this
0x18001cf57  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001cf5c  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18001cf60  lea     rdx, [rbp+pControl]; pControl
0x18001cf64  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001cf68  call    cs:__imp_GetSecurityDescriptorControl
0x18001cf6f  nop     dword ptr [rax+rax+00h]
0x18001cf74  mov     ecx, eax; this
0x18001cf76  call    ?ThrowIf32Bool@FwPlumber@@YAXH@Z; FwPlumber::ThrowIf32Bool(int)
0x18001cf7b  mov     eax, 8000h
0x18001cf80  test    [rbp+pControl], ax
0x18001cf84  jnz     short loc_18001CFAF
0x18001cf86  mov     ebx, 80070057h
0x18001cf8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf92  cmp     rcx, rdi
0x18001cf95  jnz     loc_18001D07C
0x18001cf9b  mov     [rbp+pExceptionObject], ebx
0x18001cf9e  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001cfa5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001cfa9  call    _CxxThrowException_0
0x18001cfaf  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18001cfb3  call    cs:__imp_GetSecurityDescriptorLength
0x18001cfba  nop     dword ptr [rax+rax+00h]
0x18001cfbf  mov     edi, eax
0x18001cfc1  mov     rcx, rsi; this
0x18001cfc4  call    ?NextCondition@Filter@FwPlumber@@IEAAAEAUFWPM_FILTER_CONDITION0_@@XZ; FwPlumber::Filter::NextCondition(void)
0x18001cfc9  mov     rbx, rax
0x18001cfcc  movups  xmm0, cs:FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME
0x18001cfd3  movdqu  xmmword ptr [rax], xmm0
0x18001cfd7  mov     dword ptr [rax+10h], 0
0x18001cfde  mov     dword ptr [rax+18h], 0Eh
0x18001cfe5  mov     rcx, rsi
0x18001cfe8  call    ??$Allocate@UFWP_BYTE_BLOB_@@@Filter@FwPlumber@@IEAAPEAUFWP_BYTE_BLOB_@@I@Z; FwPlumber::Filter::Allocate<FWP_BYTE_BLOB_>(uint)
0x18001cfed  mov     [rbx+20h], rax
0x18001cff1  mov     [rax], edi
0x18001cff3  mov     rcx, [rbx+20h]
0x18001cff7  mov     rax, [rbp+SecurityDescriptor]
0x18001cffb  mov     [rcx+8], rax
0x18001cfff  mov     rcx, [rbp+StringSecurityDescriptor]
0x18001d003  test    rcx, rcx
0x18001d006  jz      short loc_18001D014
0x18001d008  call    cs:__imp_FwFree
0x18001d00f  nop     dword ptr [rax+rax+00h]
0x18001d014  mov     rcx, [rbp+var_10]
0x18001d018  xor     rcx, rsp; StackCookie
0x18001d01b  call    __security_check_cookie
0x18001d020  mov     rbx, [rsp+60h+arg_10]
0x18001d028  add     rsp, 60h
0x18001d02c  pop     rdi
0x18001d02d  pop     rsi
0x18001d02e  pop     rbp
0x18001d02f  retn
0x18001d031  test    byte ptr [rcx+1Ch], 8
0x18001d035  jz      loc_18001CEE3
0x18001d03b  mov     edx, 45h ; 'E'
0x18001d040  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001d047  mov     rcx, [rcx+10h]
0x18001d04b  call    WPP_SF_
0x18001d050  jmp     loc_18001CEE3
0x18001d055  test    byte ptr [rcx+1Ch], 1
0x18001d059  jz      loc_18001CF0F
0x18001d05f  mov     edx, 0Ch
0x18001d064  mov     r9d, ebx
0x18001d067  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001d06e  mov     rcx, [rcx+10h]
0x18001d072  call    WPP_SF_d
0x18001d077  jmp     loc_18001CF0F
0x18001d07c  test    byte ptr [rcx+1Ch], 1
0x18001d080  jz      loc_18001CF9B
0x18001d086  mov     edx, 0Ch
0x18001d08b  mov     r9d, ebx
0x18001d08e  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001d095  mov     rcx, [rcx+10h]
0x18001d099  call    WPP_SF_d
0x18001d09e  jmp     loc_18001CF9B
```
