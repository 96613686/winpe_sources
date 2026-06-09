# PsBootPhaseComplete

- ea: `0x1407af3d4`
- end: `0x1407af75d`
- name: `PsBootPhaseComplete`
- size: `905`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1407f96fc`
- `0x140aeb590`

## callees

- `0x1403726d0`
- `0x1404920b0`
- `0x1404d1004`
- `0x1406dc8c0`
- `0x1406dd620`
- `0x1406dd6c0`
- `0x1407af3d4`
- `0x1407af9c4`
- `0x1407b1db4`
- `0x1407b92d0`
- `0x14094b0a0`

## string_xrefs

- `0x1407af3ff`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\LsaInformation`
- `0x1407af50b`: `NoRemoteThreadBeforeProcessInit`
- `0x1407af418`: `UACInstalled`
- `0x1407af43c`: `\Registry\Machine\Software\Microsoft\Windows\CurrentVersion\Policies\System`
- `0x1407af4f8`: `MaxLoaderThreads`
- `0x1407af481`: `EnableInstallerDetection`

## pseudocode

```c
__int64 __fastcall PsBootPhaseComplete(__int64 a1, __int64 a2, __int64 a3)
{
  _BOOL8 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rcx
  __int64 v6; // r8
  bool v7; // bl
  NTSTATUS v8; // edi
  __int64 i; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v11; // rax
  __int64 ServerSiloGlobals; // rbx
  __int64 result; // rax
  HANDLE KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v18[2]; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING ValueName; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v20[2]; // [rsp+A0h] [rbp-60h] BYREF
  UNICODE_STRING v21; // [rsp+B0h] [rbp-50h] BYREF
  __int128 KeyValueInformation; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v23[2]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v24; // [rsp+D8h] [rbp-28h]
  _DWORD v25[4]; // [rsp+E0h] [rbp-20h]
  const wchar_t *v26; // [rsp+F0h] [rbp-10h]
  int v27; // [rsp+F8h] [rbp-8h]
  int v28; // [rsp+100h] [rbp+0h]
  const wchar_t *v29; // [rsp+108h] [rbp+8h]
  int v30; // [rsp+110h] [rbp+10h]

  v16 = 0;
  KeyHandle = 0;
  v18[1] = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\LsaInformation";
  v18[0] = 8650882;
  ValueName.Buffer = L"UACInstalled";
  *(_QWORD *)&ValueName.Length = 1703960;
  v20[0] = 9961622;
  v20[1] = L"\\Registry\\Machine\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System";
  *(_QWORD *)&v21.Length = 3145774;
  v21.Buffer = L"TypeOfAdminApprovalMode";
  v24 = L"EnableLUA";
  v26 = L"EnableVirtualization";
  v23[0] = 1310738;
  v29 = L"EnableInstallerDetection";
  KeyValueInformation = 0;
  v25[0] = 1;
  memset(&ObjectAttributes, 0, 44);
  v25[2] = 2752552;
  v27 = 2;
  v28 = 3276848;
  v30 = 3;
  ResultLength = 0;
  if ( (int)RtlQueryImageFileExecutionOptions(a1, L"DevOverrideEnable", a3, &v16) >= 0 )
  {
    v3 = v16 != 0;
    PspGlobalFlags = v3 | PspGlobalFlags & 0xFFFFFFFE;
  }
  RtlQueryImageFileExecutionOptions(v3, L"MaxLoaderThreads", v4, &PsDefaultLoaderThreads);
  RtlQueryImageFileExecutionOptions(v5, L"NoRemoteThreadBeforeProcessInit", v6, &PsNoRemoteThreadBeforeProcessInit);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v18;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes) >= 0 )
  {
    v7 = 0;
    if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength) >= 0
      && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL )
    {
      v7 = HIDWORD(KeyValueInformation) != 0;
    }
    ObCloseHandle(KeyHandle, 0);
    KeyHandle = 0;
    if ( v7 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v20;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
      if ( v8 < 0 )
        KeyHandle = 0;
      for ( i = 0; i != 3; ++i )
      {
        if ( KeyHandle )
          v8 = ZwQueryValueKey(
                 KeyHandle,
                 (PUNICODE_STRING)&v23[6 * i],
                 KeyValuePartialInformation,
                 &KeyValueInformation,
                 0x10u,
                 &ResultLength);
        if ( v8 < 0 || *(_QWORD *)((char *)&KeyValueInformation + 4) != 0x400000004LL || HIDWORD(KeyValueInformation) )
          _interlockedbittestandset((volatile signed __int32 *)(MmWriteableSharedUserData + 752), v25[6 * i]);
      }
      if ( (Feature_ShadowAdmin__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_ShadowAdmin__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        if ( KeyHandle )
          v8 = ZwQueryValueKey(KeyHandle, &v21, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength);
        if ( v8 >= 0
          && *(_QWORD *)((char *)&KeyValueInformation + 4) == 0x400000004LL
          && HIDWORD(KeyValueInformation) == 2 )
        {
          _interlockedbittestandset((volatile signed __int32 *)(MmWriteableSharedUserData + 752), 0xCu);
        }
        else
        {
          _interlockedbittestandset((volatile signed __int32 *)(MmWriteableSharedUserData + 752), 0xBu);
        }
      }
      if ( KeyHandle )
        ObCloseHandle(KeyHandle, 0);
    }
  }
  PsCpuFairShareEnabled = PspIsDfssEnabled();
  v11 = HalSystemVectorDispatchEntry();
  ServerSiloGlobals = PsGetServerSiloGlobals(v11);
  *(_BYTE *)(ServerSiloGlobals + 1000) = PspQueryForwardersEnabled();
  result = PspGlobalFlags & 0xFFFFFFF3 | 4;
  PspGlobalFlags = PspGlobalFlags & 0xFFFFFFF3 | 4;
  return result;
}

```

## disassembly

```asm
0x1407af3d4  push    rbp
0x1407af3d6  push    rbx
0x1407af3d7  push    rdi
0x1407af3d8  push    r15
0x1407af3da  lea     rbp, [rsp-38h]
0x1407af3df  sub     rsp, 138h
0x1407af3e6  mov     rax, cs:__security_cookie
0x1407af3ed  xor     rax, rsp
0x1407af3f0  mov     [rbp+50h+var_30], rax
0x1407af3f4  xorps   xmm0, xmm0
0x1407af3f7  mov     [rsp+150h+var_104], 0
0x1407af3ff  lea     rax, aRegistryMachin_89; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1407af406  mov     [rsp+150h+KeyHandle], 0
0x1407af40f  mov     [rbp+50h+var_C8], rax
0x1407af413  lea     r9, [rsp+150h+var_104]
0x1407af418  lea     rax, aUacinstalled; "UACInstalled"
0x1407af41f  mov     [rbp+50h+var_D0], 840082h
0x1407af427  mov     [rbp+50h+ValueName.Buffer], rax
0x1407af42b  lea     rdx, aDevoverrideena; "DevOverrideEnable"
0x1407af432  xor     eax, eax
0x1407af434  mov     qword ptr [rbp+50h+ValueName.Length], 1A0018h
0x1407af43c  lea     rax, aRegistryMachin_95; "\\Registry\\Machine\\Software\\Microsof"...
0x1407af443  mov     [rbp+50h+var_B0], 980096h
0x1407af44b  mov     [rbp+50h+var_A8], rax
0x1407af44f  mov     ebx, 30h ; '0'
0x1407af454  lea     rax, aTypeofadminapp; "TypeOfAdminApprovalMode"
0x1407af45b  mov     qword ptr [rbp+50h+var_A0.Length], 30002Eh
0x1407af463  mov     [rbp+50h+var_A0.Buffer], rax
0x1407af467  lea     rax, aEnablelua; "EnableLUA"
0x1407af46e  mov     [rbp+50h+var_78], rax
0x1407af472  lea     rax, aEnablevirtuali; "EnableVirtualization"
0x1407af479  mov     [rbp+50h+var_60], rax
0x1407af47d  lea     r15d, [rbx-2Fh]
0x1407af481  lea     rax, aEnableinstalle; "EnableInstallerDetection"
0x1407af488  mov     [rbp+50h+var_80], 140012h
0x1407af48f  movups  xmmword ptr [rsp+150h+ObjectAttributes.ObjectName], xmm0
0x1407af494  mov     [rbp+50h+var_48], rax
0x1407af498  movups  [rbp+50h+KeyValueInformation], xmm0
0x1407af49c  mov     [rbp+50h+var_70], r15d
0x1407af4a0  movups  xmmword ptr [rsp+150h+ObjectAttributes.Length], xmm0
0x1407af4a5  mov     [rbp+50h+var_68], 2A0028h
0x1407af4ac  movups  xmmword ptr [rsp+150h+ObjectAttributes+1Ch], xmm0
0x1407af4b1  mov     [rbp+50h+var_58], 2
0x1407af4b8  mov     [rbp+50h+var_50], 320030h
0x1407af4bf  mov     [rbp+50h+var_40], 3
0x1407af4c6  mov     [rsp+150h+var_108], 0
0x1407af4ce  call    RtlQueryImageFileExecutionOptions
0x1407af4d3  test    eax, eax
0x1407af4d5  js      short loc_1407AF4F1
0x1407af4d7  mov     eax, cs:PspGlobalFlags
0x1407af4dd  xor     ecx, ecx
0x1407af4df  cmp     [rsp+150h+var_104], ecx
0x1407af4e3  setnz   cl
0x1407af4e6  and     eax, 0FFFFFFFEh
0x1407af4e9  or      eax, ecx
0x1407af4eb  mov     cs:PspGlobalFlags, eax
0x1407af4f1  lea     r9, PsDefaultLoaderThreads
0x1407af4f8  lea     rdx, aMaxloaderthrea; "MaxLoaderThreads"
0x1407af4ff  call    RtlQueryImageFileExecutionOptions
0x1407af504  lea     r9, PsNoRemoteThreadBeforeProcessInit
0x1407af50b  lea     rdx, aNoremotethread; "NoRemoteThreadBeforeProcessInit"
0x1407af512  call    RtlQueryImageFileExecutionOptions
0x1407af517  lea     rax, [rbp+50h+var_D0]
0x1407af51b  mov     [rsp+150h+ObjectAttributes.Length], ebx
0x1407af51f  xorps   xmm0, xmm0
0x1407af522  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1407af527  mov     edi, 240h
0x1407af52c  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1407af535  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1407af53a  mov     [rsp+150h+ObjectAttributes.Attributes], edi
0x1407af53e  mov     edx, r15d; DesiredAccess
0x1407af541  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x1407af546  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407af54c  call    ZwOpenKey
0x1407af551  test    eax, eax
0x1407af553  js      loc_1407AF70B
0x1407af559  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x1407af55e  lea     rax, [rsp+150h+var_108]
0x1407af563  mov     [rsp+150h+ResultLength], rax; ResultLength
0x1407af568  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x1407af56c  mov     r8d, 2; KeyValueInformationClass
0x1407af572  mov     [rsp+150h+Length], 10h; Length
0x1407af57a  lea     rdx, [rbp+50h+ValueName]; ValueName
0x1407af57e  xor     bl, bl
0x1407af580  call    ZwQueryValueKey
0x1407af585  test    eax, eax
0x1407af587  js      short loc_1407AF5A0
0x1407af589  cmp     dword ptr [rbp+50h+KeyValueInformation+4], 4
0x1407af58d  jnz     short loc_1407AF5A0
0x1407af58f  cmp     dword ptr [rbp+50h+KeyValueInformation+8], 4
0x1407af593  jnz     short loc_1407AF5A0
0x1407af595  cmp     dword ptr [rbp+50h+KeyValueInformation+0Ch], 0
0x1407af599  movzx   ebx, bl
0x1407af59c  cmovnz  ebx, r15d
0x1407af5a0  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x1407af5a5  xor     edx, edx; PreviousMode
0x1407af5a7  call    ObCloseHandle
0x1407af5ac  mov     [rsp+150h+KeyHandle], 0
0x1407af5b5  test    bl, bl
0x1407af5b7  jz      loc_1407AF70B
0x1407af5bd  lea     rax, [rbp+50h+var_B0]
0x1407af5c1  mov     [rsp+150h+ObjectAttributes.Length], 30h ; '0'
0x1407af5c9  xorps   xmm0, xmm0
0x1407af5cc  mov     [rsp+150h+ObjectAttributes.ObjectName], rax
0x1407af5d1  lea     r8, [rsp+150h+ObjectAttributes]; ObjectAttributes
0x1407af5d6  mov     [rsp+150h+ObjectAttributes.RootDirectory], 0
0x1407af5df  mov     edx, r15d; DesiredAccess
0x1407af5e2  mov     [rsp+150h+ObjectAttributes.Attributes], edi
0x1407af5e6  lea     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x1407af5eb  movdqu  xmmword ptr [rsp+150h+ObjectAttributes.SecurityDescriptor], xmm0
0x1407af5f1  call    ZwOpenKey
0x1407af5f6  mov     edi, eax
0x1407af5f8  test    eax, eax
0x1407af5fa  jns     short loc_1407AF605
0x1407af5fc  mov     [rsp+150h+KeyHandle], 0
0x1407af605  xor     ebx, ebx
0x1407af607  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x1407af60c  test    rcx, rcx
0x1407af60f  jz      short loc_1407AF640
0x1407af611  lea     rax, [rbx+rbx*2]
0x1407af615  mov     r8d, 2; KeyValueInformationClass
0x1407af61b  lea     rdx, [rbp+50h+var_80]
0x1407af61f  lea     rdx, [rdx+rax*8]; ValueName
0x1407af623  lea     rax, [rsp+150h+var_108]
0x1407af628  mov     [rsp+150h+ResultLength], rax; ResultLength
0x1407af62d  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x1407af631  mov     [rsp+150h+Length], 10h; Length
0x1407af639  call    ZwQueryValueKey
0x1407af63e  mov     edi, eax
0x1407af640  mov     rax, rbx
0x1407af643  test    edi, edi
0x1407af645  js      short loc_1407AF659
0x1407af647  cmp     dword ptr [rbp+50h+KeyValueInformation+4], 4
0x1407af64b  jnz     short loc_1407AF659
0x1407af64d  cmp     dword ptr [rbp+50h+KeyValueInformation+8], 4
0x1407af651  jnz     short loc_1407AF659
0x1407af653  cmp     dword ptr [rbp+50h+KeyValueInformation+0Ch], 0
0x1407af657  jz      short loc_1407AF670
0x1407af659  mov     rdx, cs:MmWriteableSharedUserData
0x1407af660  lea     rax, [rax+rax*2]
0x1407af664  mov     ecx, [rbp+rax*8+50h+var_70]
0x1407af668  lock bts [rdx+2F0h], ecx
0x1407af670  add     rbx, r15
0x1407af673  cmp     rbx, 3
0x1407af677  jnz     short loc_1407AF607
0x1407af679  mov     eax, cs:Feature_ShadowAdmin__private_featureState
0x1407af67f  test    al, 10h
0x1407af681  jz      short loc_1407AF688
0x1407af683  and     eax, r15d
0x1407af686  jmp     short loc_1407AF68D
0x1407af688  call    Feature_ShadowAdmin__private_IsEnabledDeviceUsageNoInline
0x1407af68d  test    eax, eax
0x1407af68f  jz      short loc_1407AF6FA
0x1407af691  mov     rcx, [rsp+150h+KeyHandle]; KeyHandle
0x1407af696  test    rcx, rcx
0x1407af699  jz      short loc_1407AF6C2
0x1407af69b  lea     rax, [rsp+150h+var_108]
0x1407af6a0  mov     r8d, 2; KeyValueInformationClass
0x1407af6a6  mov     [rsp+150h+ResultLength], rax; ResultLength
0x1407af6ab  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x1407af6af  lea     rdx, [rbp+50h+var_A0]; ValueName
0x1407af6b3  mov     [rsp+150h+Length], 10h; Length
0x1407af6bb  call    ZwQueryValueKey
0x1407af6c0  mov     edi, eax
0x1407af6c2  test    edi, edi
0x1407af6c4  js      short loc_1407AF6EA
0x1407af6c6  cmp     dword ptr [rbp+50h+KeyValueInformation+4], 4
0x1407af6ca  jnz     short loc_1407AF6EA
0x1407af6cc  cmp     dword ptr [rbp+50h+KeyValueInformation+8], 4
0x1407af6d0  jnz     short loc_1407AF6EA
0x1407af6d2  cmp     dword ptr [rbp+50h+KeyValueInformation+0Ch], 2
0x1407af6d6  jnz     short loc_1407AF6EA
0x1407af6d8  mov     rax, cs:MmWriteableSharedUserData
0x1407af6df  lock bts dword ptr [rax+2F0h], 0Ch
0x1407af6e8  jmp     short loc_1407AF6FA
0x1407af6ea  mov     rax, cs:MmWriteableSharedUserData
0x1407af6f1  lock bts dword ptr [rax+2F0h], 0Bh
0x1407af6fa  mov     rcx, [rsp+150h+KeyHandle]; Handle
0x1407af6ff  test    rcx, rcx
0x1407af702  jz      short loc_1407AF70B
0x1407af704  xor     edx, edx; PreviousMode
0x1407af706  call    ObCloseHandle
0x1407af70b  call    PspIsDfssEnabled
0x1407af710  mov     cs:PsCpuFairShareEnabled, al
0x1407af716  call    HalSystemVectorDispatchEntry
0x1407af71b  mov     rcx, rax
0x1407af71e  call    PsGetServerSiloGlobals
0x1407af723  mov     rbx, rax
0x1407af726  call    PspQueryForwardersEnabled
0x1407af72b  mov     [rbx+3E8h], al
0x1407af731  mov     eax, cs:PspGlobalFlags
0x1407af737  and     eax, 0FFFFFFF7h
0x1407af73a  or      eax, 4
0x1407af73d  mov     cs:PspGlobalFlags, eax
0x1407af743  mov     rcx, [rbp+50h+var_30]
0x1407af747  xor     rcx, rsp; StackCookie
0x1407af74a  call    __security_check_cookie
0x1407af74f  add     rsp, 138h
0x1407af756  pop     r15
0x1407af758  pop     rdi
0x1407af759  pop     rbx
0x1407af75a  pop     rbp
0x1407af75b  retn
```
