# CiInitializePolicy

- ea: `0x18005e6d0`
- end: `0x18005ea8b`
- name: `CiInitializePolicy`
- size: `955`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001daa8`
- `0x18002bf20`
- `0x18002c000`
- `0x18005e6d0`
- `0x18005ed68`
- `0x18005f100`
- `0x18005fa58`
- `0x18006066c`
- `0x1800607c8`
- `0x18006ff94`
- `0x180073318`
- `0x18007406c`
- `0x18008d25c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005e80b`
- `ntoskrnl!ZwCreateKey` at `0x18005e871`
- `ntoskrnl!ZwCreateKey` at `0x18005e80b`
- `ntoskrnl!ZwCreateKey` at `0x18005e871`
- `ntoskrnl!MmProtectDriverSection` at `0x18005ea4c`
- `ntoskrnl!MmProtectDriverSection` at `0x18005ea4c`
- `ntoskrnl!ZwDeleteKey` at `0x18005e82b`
- `ntoskrnl!ZwDeleteKey` at `0x18005e82b`
- `ntoskrnl!ZwClose` at `0x18005e83c`
- `ntoskrnl!ZwClose` at `0x18005e8c9`
- `ntoskrnl!ZwClose` at `0x18005e83c`
- `ntoskrnl!ZwClose` at `0x18005e8c9`
- `ntoskrnl!ZwSetValueKey` at `0x18005e8b8`
- `ntoskrnl!ZwSetValueKey` at `0x18005e8b8`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18005ea33`
- `ntoskrnl!KdDebuggerEnabled` at `0x18005ea27`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e73c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e947`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e73c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e947`

## string_xrefs

- `0x18005e796`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\State`

## pseudocode

```c
__int64 __fastcall CiInitializePolicy(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  NTSTATUS v6; // edi
  __int64 v7; // rdx
  NTSTATUS v8; // esi
  __int64 v9; // rcx
  char v10; // di
  unsigned int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // rcx
  bool v14; // si
  int v15; // eax
  ULONG Disposition; // [rsp+40h] [rbp-89h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-81h] BYREF
  int v19; // [rsp+50h] [rbp-79h] BYREF
  int Data; // [rsp+54h] [rbp-75h] BYREF
  _QWORD v21[2]; // [rsp+58h] [rbp-71h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+68h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-51h] BYREF
  __int128 SystemInformation; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-11h]
  __int128 v26; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v27; // [rsp+D0h] [rbp+7h]

  SystemInformation = 0;
  v25 = 0;
  v19 = 0;
  v26 = 0;
  v27 = 0;
  v6 = CipSetRevocationListRegKey();
  if ( v6 >= 0 )
  {
    CipCheckLicensing(a1);
    v8 = ZwQuerySystemInformation(SystemNonPagedPoolInformation|0x80, &SystemInformation, 0x18u, 0);
    v9 = v8 + 0x80000000;
    if ( (int)v9 < 0 || v8 == -2143092730 )
    {
      if ( g_HvciSupported )
      {
        v10 = (*((__int64 (**)(void))&xmmword_18004A630 + 1))();
        if ( (v10 & 2) != 0 )
        {
          g_CiOptions |= 0x8000u;
          v21[1] = L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\State";
          *(_QWORD *)&ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)v21;
          *(_QWORD *)&ObjectAttributes.Attributes = 576;
          v21[0] = 7864438;
          KeyHandle = 0;
          Disposition = 0;
          ObjectAttributes.RootDirectory = 0;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 1u, &Disposition) >= 0 )
          {
            if ( Disposition != 2
              || (ZwDeleteKey(KeyHandle),
                  ZwClose(KeyHandle),
                  ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 1u, &Disposition) >= 0) )
            {
              ValueName.Buffer = L"HVCIEnabled";
              *(_QWORD *)&ValueName.Length = 1572886;
              Data = 1;
              ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &Data, 4u);
              ZwClose(KeyHandle);
            }
          }
        }
        if ( (v10 & 0x20) != 0 )
          g_CiOptions |= 0x10000u;
        if ( (v10 & 4) != 0 )
          g_CiOptions |= 0x4000u;
        if ( (v10 & 0x40) != 0 )
          g_CiOptions |= 0x200000u;
      }
      v6 = CipCheckConfigOptions(v9, v7, &v19);
      if ( v6 >= 0 )
      {
        v11 = v19;
        g_CiTestFlags = v19;
        if ( a1 )
        {
          v12 = *(unsigned int *)(a1 + 48);
          if ( (int)v12 < 0 )
            CiLogStatusEventWithCorrelationId(v12, CipLoadWeakCryptoPoliciesFailed, 0);
        }
        v6 = ZwQuerySystemInformation(SystemBootEnvironmentInformation, &v26, 0x20u, 0);
        if ( v6 >= 0 )
        {
          v14 = v8 >= 0;
          g_CiFirmwareType = v27;
          if ( (_DWORD)v27 == 2 )
            g_SiPolicyIsUefiSystem = 1;
          LOBYTE(v13) = v14;
          v6 = CiInitializePolicyFromPolicies(v13, &SystemInformation, a1, v11);
          if ( v6 >= 0 )
          {
            CiInitializeNightsWatchPolicyStateGlobal();
            CiSetRuntimeUmciSigningLevel();
            if ( (g_CiDeveloperMode & 2) != 0 )
              CipSetUmciExclusionPaths();
            if ( a1 )
              v15 = *(_DWORD *)(a1 + 68);
            else
              v15 = 0;
            g_CiCurrentBootId = v15;
            v6 = CiBlackBoxInitialize();
            if ( v6 >= 0 )
            {
              if ( a1 )
              {
                qword_180049E40[0] = *(_QWORD *)(a1 + 72);
                qword_180049E48 = *(_QWORD *)(a1 + 80);
                qword_180049E50 = *(_QWORD *)(a1 + 88);
                qword_180049E58 = *(_QWORD *)(a1 + 96);
                g_CiRevocationListInfo = *(_DWORD *)(a1 + 104);
                CiBlackBoxRevocationListUpdate(&qword_180049E40[g_CiRevocationListInfo]);
              }
              if ( (g_CiOptions & 0x10) != 0 || (_BYTE)KdDebuggerEnabled != 1 || (_BYTE)KdDebuggerNotPresent )
                MmProtectDriverSection(&g_CiOptions, 0, 1);
              *a2 = &g_CiProtectedContent;
              *a3 = 8;
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)v8;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005e6d0  push    rbp
0x18005e6d2  push    rbx
0x18005e6d3  push    rsi
0x18005e6d4  push    rdi
0x18005e6d5  push    r12
0x18005e6d7  push    r14
0x18005e6d9  push    r15
0x18005e6db  lea     rbp, [rsp-27h]
0x18005e6e0  sub     rsp, 0F0h
0x18005e6e7  mov     rax, cs:__security_cookie
0x18005e6ee  xor     rax, rsp
0x18005e6f1  mov     [rbp+57h+var_40], rax
0x18005e6f5  xorps   xmm0, xmm0
0x18005e6f8  xor     eax, eax
0x18005e6fa  movups  [rbp+57h+SystemInformation], xmm0
0x18005e6fe  mov     [rbp+57h+var_68], rax
0x18005e702  mov     r12, r8
0x18005e705  mov     [rbp+57h+var_D0], eax
0x18005e708  mov     r15, rdx
0x18005e70b  movups  [rbp+57h+var_60], xmm0
0x18005e70f  mov     rbx, rcx
0x18005e712  movups  [rbp+57h+var_50], xmm0
0x18005e716  call    CipSetRevocationListRegKey
0x18005e71b  mov     edi, eax
0x18005e71d  test    eax, eax
0x18005e71f  js      loc_18005EA6A
0x18005e725  mov     rcx, rbx
0x18005e728  call    CipCheckLicensing
0x18005e72d  xor     r9d, r9d; ReturnLength
0x18005e730  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18005e734  lea     r8d, [r9+18h]; SystemInformationLength
0x18005e738  lea     ecx, [r8+77h]; SystemInformationClass
0x18005e73c  call    cs:__imp_ZwQuerySystemInformation
0x18005e743  nop     dword ptr [rax+rax+00h]
0x18005e748  mov     esi, eax
0x18005e74a  mov     eax, 80000000h
0x18005e74f  lea     ecx, [rsi+rax]
0x18005e752  test    eax, ecx
0x18005e754  jnz     short loc_18005E765
0x18005e756  cmp     esi, 80430006h
0x18005e75c  jz      short loc_18005E765
0x18005e75e  mov     edi, esi
0x18005e760  jmp     loc_18005EA6A
0x18005e765  cmp     cs:g_HvciSupported, 0
0x18005e76c  mov     r14d, 1
0x18005e772  jz      loc_18005E8FF
0x18005e778  mov     rax, qword ptr cs:xmmword_18004A630+8
0x18005e77f  call    _guard_dispatch_icall
0x18005e784  mov     edi, eax
0x18005e786  test    al, 2
0x18005e788  jz      loc_18005E8D5
0x18005e78e  bts     cs:g_CiOptions, 0Fh
0x18005e796  lea     rax, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005e79d  mov     [rbp+57h+var_C0], rax
0x18005e7a1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e7a5  lea     rax, [rbp+57h+var_C8]
0x18005e7a9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e7b1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e7b5  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e7ba  lea     rax, [rsp+120h+var_E0]
0x18005e7bf  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005e7c7  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e7cc  xorps   xmm0, xmm0
0x18005e7cf  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e7d4  xor     r9d, r9d; TitleIndex
0x18005e7d7  mov     edx, 20006h; DesiredAccess
0x18005e7dc  mov     [rsp+120h+Class], 0; Class
0x18005e7e5  mov     [rbp+57h+var_C8], 780076h
0x18005e7ed  mov     [rsp+120h+KeyHandle], 0
0x18005e7f6  mov     [rsp+120h+var_E0], 0
0x18005e7fe  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005e806  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e80b  call    cs:__imp_ZwCreateKey
0x18005e812  nop     dword ptr [rax+rax+00h]
0x18005e817  test    eax, eax
0x18005e819  js      loc_18005E8D5
0x18005e81f  cmp     [rsp+120h+var_E0], 2
0x18005e824  jnz     short loc_18005E881
0x18005e826  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e82b  call    cs:__imp_ZwDeleteKey
0x18005e832  nop     dword ptr [rax+rax+00h]
0x18005e837  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e83c  call    cs:__imp_ZwClose
0x18005e843  nop     dword ptr [rax+rax+00h]
0x18005e848  lea     rax, [rsp+120h+var_E0]
0x18005e84d  xor     r9d, r9d; TitleIndex
0x18005e850  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e855  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e859  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e85e  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e863  mov     edx, 20006h; DesiredAccess
0x18005e868  mov     [rsp+120h+Class], 0; Class
0x18005e871  call    cs:__imp_ZwCreateKey
0x18005e878  nop     dword ptr [rax+rax+00h]
0x18005e87d  test    eax, eax
0x18005e87f  js      short loc_18005E8D5
0x18005e881  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e886  lea     rax, aHvcienabled; "HVCIEnabled"
0x18005e88d  mov     [rbp+57h+ValueName.Buffer], rax
0x18005e891  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005e895  mov     r9d, 4; Type
0x18005e89b  mov     qword ptr [rbp+57h+ValueName.Length], 180016h
0x18005e8a3  lea     rax, [rbp+57h+Data]
0x18005e8a7  mov     [rsp+120h+CreateOptions], r9d; DataSize
0x18005e8ac  xor     r8d, r8d; TitleIndex
0x18005e8af  mov     [rsp+120h+Class], rax; Data
0x18005e8b4  mov     [rbp+57h+Data], r14d
0x18005e8b8  call    cs:__imp_ZwSetValueKey
0x18005e8bf  nop     dword ptr [rax+rax+00h]
0x18005e8c4  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e8c9  call    cs:__imp_ZwClose
0x18005e8d0  nop     dword ptr [rax+rax+00h]
0x18005e8d5  test    dil, 20h
0x18005e8d9  jz      short loc_18005E8E3
0x18005e8db  bts     cs:g_CiOptions, 10h
0x18005e8e3  test    dil, 4
0x18005e8e7  jz      short loc_18005E8F1
0x18005e8e9  bts     cs:g_CiOptions, 0Eh
0x18005e8f1  test    dil, 40h
0x18005e8f5  jz      short loc_18005E8FF
0x18005e8f7  bts     cs:g_CiOptions, 15h
0x18005e8ff  lea     r8, [rbp+57h+var_D0]
0x18005e903  call    CipCheckConfigOptions
0x18005e908  mov     edi, eax
0x18005e90a  test    eax, eax
0x18005e90c  js      loc_18005EA6A
0x18005e912  mov     r14d, [rbp+57h+var_D0]
0x18005e916  mov     cs:g_CiTestFlags, r14d
0x18005e91d  test    rbx, rbx
0x18005e920  jz      short loc_18005E938
0x18005e922  mov     ecx, [rbx+30h]
0x18005e925  test    ecx, ecx
0x18005e927  jns     short loc_18005E938
0x18005e929  xor     r8d, r8d
0x18005e92c  lea     rdx, CipLoadWeakCryptoPoliciesFailed
0x18005e933  call    CiLogStatusEventWithCorrelationId
0x18005e938  xor     r9d, r9d; ReturnLength
0x18005e93b  lea     rdx, [rbp+57h+var_60]; SystemInformation
0x18005e93f  lea     r8d, [r9+20h]; SystemInformationLength
0x18005e943  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18005e947  call    cs:__imp_ZwQuerySystemInformation
0x18005e94e  nop     dword ptr [rax+rax+00h]
0x18005e953  mov     edi, eax
0x18005e955  test    eax, eax
0x18005e957  js      loc_18005EA6A
0x18005e95d  mov     eax, dword ptr [rbp+57h+var_50]
0x18005e960  shr     esi, 1Fh
0x18005e963  xor     sil, 1
0x18005e967  mov     cs:g_CiFirmwareType, eax
0x18005e96d  cmp     eax, 2
0x18005e970  jnz     short loc_18005E979
0x18005e972  mov     cs:g_SiPolicyIsUefiSystem, 1
0x18005e979  mov     r9d, r14d
0x18005e97c  lea     rdx, [rbp+57h+SystemInformation]
0x18005e980  mov     r8, rbx
0x18005e983  mov     cl, sil
0x18005e986  call    CiInitializePolicyFromPolicies
0x18005e98b  mov     edi, eax
0x18005e98d  test    eax, eax
0x18005e98f  js      loc_18005EA6A
0x18005e995  call    CiInitializeNightsWatchPolicyStateGlobal
0x18005e99a  call    CiSetRuntimeUmciSigningLevel
0x18005e99f  mov     eax, cs:g_CiDeveloperMode
0x18005e9a5  test    al, 2
0x18005e9a7  jz      short loc_18005E9AE
0x18005e9a9  call    CipSetUmciExclusionPaths
0x18005e9ae  test    rbx, rbx
0x18005e9b1  jz      short loc_18005E9B8
0x18005e9b3  mov     eax, [rbx+44h]
0x18005e9b6  jmp     short loc_18005E9BA
0x18005e9b8  xor     eax, eax
0x18005e9ba  mov     cs:g_CiCurrentBootId, eax
0x18005e9c0  call    CiBlackBoxInitialize
0x18005e9c5  mov     edi, eax
0x18005e9c7  test    eax, eax
0x18005e9c9  js      loc_18005EA6A
0x18005e9cf  test    rbx, rbx
0x18005e9d2  jz      short loc_18005EA1D
0x18005e9d4  mov     rax, [rbx+48h]
0x18005e9d8  mov     cs:qword_180049E40, rax
0x18005e9df  mov     rax, [rbx+50h]
0x18005e9e3  mov     cs:qword_180049E48, rax
0x18005e9ea  mov     rax, [rbx+58h]
0x18005e9ee  mov     cs:qword_180049E50, rax
0x18005e9f5  mov     rax, [rbx+60h]
0x18005e9f9  mov     cs:qword_180049E58, rax
0x18005ea00  movsxd  rax, dword ptr [rbx+68h]
0x18005ea04  mov     rcx, rax
0x18005ea07  mov     cs:g_CiRevocationListInfo, eax
0x18005ea0d  lea     rax, qword_180049E40
0x18005ea14  lea     rcx, [rax+rcx*8]
0x18005ea18  call    CiBlackBoxRevocationListUpdate
0x18005ea1d  mov     eax, cs:g_CiOptions
0x18005ea23  test    al, 10h
0x18005ea25  jnz     short loc_18005EA3F
0x18005ea27  mov     rax, cs:KdDebuggerEnabled
0x18005ea2e  cmp     byte ptr [rax], 1
0x18005ea31  jnz     short loc_18005EA3F
0x18005ea33  mov     rax, cs:KdDebuggerNotPresent
0x18005ea3a  cmp     byte ptr [rax], 0
0x18005ea3d  jz      short loc_18005EA58
0x18005ea3f  xor     edx, edx
0x18005ea41  lea     rcx, g_CiOptions
0x18005ea48  lea     r8d, [rdx+1]
0x18005ea4c  call    cs:__imp_MmProtectDriverSection
0x18005ea53  nop     dword ptr [rax+rax+00h]
0x18005ea58  lea     rax, g_CiProtectedContent
0x18005ea5f  mov     [r15], rax
0x18005ea62  mov     dword ptr [r12], 8
0x18005ea6a  mov     eax, edi
0x18005ea6c  mov     rcx, [rbp+57h+var_40]
0x18005ea70  xor     rcx, rsp; StackCookie
0x18005ea73  call    __security_check_cookie
0x18005ea78  add     rsp, 0F0h
0x18005ea7f  pop     r15
0x18005ea81  pop     r14
0x18005ea83  pop     r12
0x18005ea85  pop     rdi
0x18005ea86  pop     rsi
0x18005ea87  pop     rbx
0x18005ea88  pop     rbp
0x18005ea89  retn
```
