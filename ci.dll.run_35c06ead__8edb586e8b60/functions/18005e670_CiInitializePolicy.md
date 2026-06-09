# CiInitializePolicy

- ea: `0x18005e670`
- end: `0x18005ea2b`
- name: `CiInitializePolicy`
- size: `955`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001db7c`
- `0x18002c0d0`
- `0x18002c1b0`
- `0x18005e670`
- `0x18005ed08`
- `0x18005f0a0`
- `0x18005f9f8`
- `0x18006060c`
- `0x180060768`
- `0x180070274`
- `0x1800735f8`
- `0x18007434c`
- `0x18009257c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005e7ab`
- `ntoskrnl!ZwCreateKey` at `0x18005e811`
- `ntoskrnl!ZwCreateKey` at `0x18005e7ab`
- `ntoskrnl!ZwCreateKey` at `0x18005e811`
- `ntoskrnl!MmProtectDriverSection` at `0x18005e9ec`
- `ntoskrnl!MmProtectDriverSection` at `0x18005e9ec`
- `ntoskrnl!ZwDeleteKey` at `0x18005e7cb`
- `ntoskrnl!ZwDeleteKey` at `0x18005e7cb`
- `ntoskrnl!ZwClose` at `0x18005e7dc`
- `ntoskrnl!ZwClose` at `0x18005e869`
- `ntoskrnl!ZwClose` at `0x18005e7dc`
- `ntoskrnl!ZwClose` at `0x18005e869`
- `ntoskrnl!ZwSetValueKey` at `0x18005e858`
- `ntoskrnl!ZwSetValueKey` at `0x18005e858`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18005e9d3`
- `ntoskrnl!KdDebuggerEnabled` at `0x18005e9c7`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e6dc`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e8e7`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e6dc`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e8e7`

## string_xrefs

- `0x18005e736`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\State`

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
        v10 = (*((__int64 (**)(void))&xmmword_18004A5D0 + 1))();
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
0x18005e670  push    rbp
0x18005e672  push    rbx
0x18005e673  push    rsi
0x18005e674  push    rdi
0x18005e675  push    r12
0x18005e677  push    r14
0x18005e679  push    r15
0x18005e67b  lea     rbp, [rsp-27h]
0x18005e680  sub     rsp, 0F0h
0x18005e687  mov     rax, cs:__security_cookie
0x18005e68e  xor     rax, rsp
0x18005e691  mov     [rbp+57h+var_40], rax
0x18005e695  xorps   xmm0, xmm0
0x18005e698  xor     eax, eax
0x18005e69a  movups  [rbp+57h+SystemInformation], xmm0
0x18005e69e  mov     [rbp+57h+var_68], rax
0x18005e6a2  mov     r12, r8
0x18005e6a5  mov     [rbp+57h+var_D0], eax
0x18005e6a8  mov     r15, rdx
0x18005e6ab  movups  [rbp+57h+var_60], xmm0
0x18005e6af  mov     rbx, rcx
0x18005e6b2  movups  [rbp+57h+var_50], xmm0
0x18005e6b6  call    CipSetRevocationListRegKey
0x18005e6bb  mov     edi, eax
0x18005e6bd  test    eax, eax
0x18005e6bf  js      loc_18005EA0A
0x18005e6c5  mov     rcx, rbx
0x18005e6c8  call    CipCheckLicensing
0x18005e6cd  xor     r9d, r9d; ReturnLength
0x18005e6d0  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18005e6d4  lea     r8d, [r9+18h]; SystemInformationLength
0x18005e6d8  lea     ecx, [r8+77h]; SystemInformationClass
0x18005e6dc  call    cs:__imp_ZwQuerySystemInformation
0x18005e6e3  nop     dword ptr [rax+rax+00h]
0x18005e6e8  mov     esi, eax
0x18005e6ea  mov     eax, 80000000h
0x18005e6ef  lea     ecx, [rsi+rax]
0x18005e6f2  test    eax, ecx
0x18005e6f4  jnz     short loc_18005E705
0x18005e6f6  cmp     esi, 80430006h
0x18005e6fc  jz      short loc_18005E705
0x18005e6fe  mov     edi, esi
0x18005e700  jmp     loc_18005EA0A
0x18005e705  cmp     cs:g_HvciSupported, 0
0x18005e70c  mov     r14d, 1
0x18005e712  jz      loc_18005E89F
0x18005e718  mov     rax, qword ptr cs:xmmword_18004A5D0+8
0x18005e71f  call    _guard_dispatch_icall
0x18005e724  mov     edi, eax
0x18005e726  test    al, 2
0x18005e728  jz      loc_18005E875
0x18005e72e  bts     cs:g_CiOptions, 0Fh
0x18005e736  lea     rax, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005e73d  mov     [rbp+57h+var_C0], rax
0x18005e741  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e745  lea     rax, [rbp+57h+var_C8]
0x18005e749  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e751  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e755  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e75a  lea     rax, [rsp+120h+var_E0]
0x18005e75f  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005e767  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e76c  xorps   xmm0, xmm0
0x18005e76f  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e774  xor     r9d, r9d; TitleIndex
0x18005e777  mov     edx, 20006h; DesiredAccess
0x18005e77c  mov     [rsp+120h+Class], 0; Class
0x18005e785  mov     [rbp+57h+var_C8], 780076h
0x18005e78d  mov     [rsp+120h+KeyHandle], 0
0x18005e796  mov     [rsp+120h+var_E0], 0
0x18005e79e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005e7a6  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e7ab  call    cs:__imp_ZwCreateKey
0x18005e7b2  nop     dword ptr [rax+rax+00h]
0x18005e7b7  test    eax, eax
0x18005e7b9  js      loc_18005E875
0x18005e7bf  cmp     [rsp+120h+var_E0], 2
0x18005e7c4  jnz     short loc_18005E821
0x18005e7c6  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e7cb  call    cs:__imp_ZwDeleteKey
0x18005e7d2  nop     dword ptr [rax+rax+00h]
0x18005e7d7  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e7dc  call    cs:__imp_ZwClose
0x18005e7e3  nop     dword ptr [rax+rax+00h]
0x18005e7e8  lea     rax, [rsp+120h+var_E0]
0x18005e7ed  xor     r9d, r9d; TitleIndex
0x18005e7f0  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e7f5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e7f9  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e7fe  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e803  mov     edx, 20006h; DesiredAccess
0x18005e808  mov     [rsp+120h+Class], 0; Class
0x18005e811  call    cs:__imp_ZwCreateKey
0x18005e818  nop     dword ptr [rax+rax+00h]
0x18005e81d  test    eax, eax
0x18005e81f  js      short loc_18005E875
0x18005e821  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e826  lea     rax, aHvcienabled; "HVCIEnabled"
0x18005e82d  mov     [rbp+57h+ValueName.Buffer], rax
0x18005e831  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005e835  mov     r9d, 4; Type
0x18005e83b  mov     qword ptr [rbp+57h+ValueName.Length], 180016h
0x18005e843  lea     rax, [rbp+57h+Data]
0x18005e847  mov     [rsp+120h+CreateOptions], r9d; DataSize
0x18005e84c  xor     r8d, r8d; TitleIndex
0x18005e84f  mov     [rsp+120h+Class], rax; Data
0x18005e854  mov     [rbp+57h+Data], r14d
0x18005e858  call    cs:__imp_ZwSetValueKey
0x18005e85f  nop     dword ptr [rax+rax+00h]
0x18005e864  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e869  call    cs:__imp_ZwClose
0x18005e870  nop     dword ptr [rax+rax+00h]
0x18005e875  test    dil, 20h
0x18005e879  jz      short loc_18005E883
0x18005e87b  bts     cs:g_CiOptions, 10h
0x18005e883  test    dil, 4
0x18005e887  jz      short loc_18005E891
0x18005e889  bts     cs:g_CiOptions, 0Eh
0x18005e891  test    dil, 40h
0x18005e895  jz      short loc_18005E89F
0x18005e897  bts     cs:g_CiOptions, 15h
0x18005e89f  lea     r8, [rbp+57h+var_D0]
0x18005e8a3  call    CipCheckConfigOptions
0x18005e8a8  mov     edi, eax
0x18005e8aa  test    eax, eax
0x18005e8ac  js      loc_18005EA0A
0x18005e8b2  mov     r14d, [rbp+57h+var_D0]
0x18005e8b6  mov     cs:g_CiTestFlags, r14d
0x18005e8bd  test    rbx, rbx
0x18005e8c0  jz      short loc_18005E8D8
0x18005e8c2  mov     ecx, [rbx+30h]
0x18005e8c5  test    ecx, ecx
0x18005e8c7  jns     short loc_18005E8D8
0x18005e8c9  xor     r8d, r8d
0x18005e8cc  lea     rdx, CipLoadWeakCryptoPoliciesFailed
0x18005e8d3  call    CiLogStatusEventWithCorrelationId
0x18005e8d8  xor     r9d, r9d; ReturnLength
0x18005e8db  lea     rdx, [rbp+57h+var_60]; SystemInformation
0x18005e8df  lea     r8d, [r9+20h]; SystemInformationLength
0x18005e8e3  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18005e8e7  call    cs:__imp_ZwQuerySystemInformation
0x18005e8ee  nop     dword ptr [rax+rax+00h]
0x18005e8f3  mov     edi, eax
0x18005e8f5  test    eax, eax
0x18005e8f7  js      loc_18005EA0A
0x18005e8fd  mov     eax, dword ptr [rbp+57h+var_50]
0x18005e900  shr     esi, 1Fh
0x18005e903  xor     sil, 1
0x18005e907  mov     cs:g_CiFirmwareType, eax
0x18005e90d  cmp     eax, 2
0x18005e910  jnz     short loc_18005E919
0x18005e912  mov     cs:g_SiPolicyIsUefiSystem, 1
0x18005e919  mov     r9d, r14d
0x18005e91c  lea     rdx, [rbp+57h+SystemInformation]
0x18005e920  mov     r8, rbx
0x18005e923  mov     cl, sil
0x18005e926  call    CiInitializePolicyFromPolicies
0x18005e92b  mov     edi, eax
0x18005e92d  test    eax, eax
0x18005e92f  js      loc_18005EA0A
0x18005e935  call    CiInitializeNightsWatchPolicyStateGlobal
0x18005e93a  call    CiSetRuntimeUmciSigningLevel
0x18005e93f  mov     eax, cs:g_CiDeveloperMode
0x18005e945  test    al, 2
0x18005e947  jz      short loc_18005E94E
0x18005e949  call    CipSetUmciExclusionPaths
0x18005e94e  test    rbx, rbx
0x18005e951  jz      short loc_18005E958
0x18005e953  mov     eax, [rbx+44h]
0x18005e956  jmp     short loc_18005E95A
0x18005e958  xor     eax, eax
0x18005e95a  mov     cs:g_CiCurrentBootId, eax
0x18005e960  call    CiBlackBoxInitialize
0x18005e965  mov     edi, eax
0x18005e967  test    eax, eax
0x18005e969  js      loc_18005EA0A
0x18005e96f  test    rbx, rbx
0x18005e972  jz      short loc_18005E9BD
0x18005e974  mov     rax, [rbx+48h]
0x18005e978  mov     cs:qword_180049E40, rax
0x18005e97f  mov     rax, [rbx+50h]
0x18005e983  mov     cs:qword_180049E48, rax
0x18005e98a  mov     rax, [rbx+58h]
0x18005e98e  mov     cs:qword_180049E50, rax
0x18005e995  mov     rax, [rbx+60h]
0x18005e999  mov     cs:qword_180049E58, rax
0x18005e9a0  movsxd  rax, dword ptr [rbx+68h]
0x18005e9a4  mov     rcx, rax
0x18005e9a7  mov     cs:g_CiRevocationListInfo, eax
0x18005e9ad  lea     rax, qword_180049E40
0x18005e9b4  lea     rcx, [rax+rcx*8]
0x18005e9b8  call    CiBlackBoxRevocationListUpdate
0x18005e9bd  mov     eax, cs:g_CiOptions
0x18005e9c3  test    al, 10h
0x18005e9c5  jnz     short loc_18005E9DF
0x18005e9c7  mov     rax, cs:KdDebuggerEnabled
0x18005e9ce  cmp     byte ptr [rax], 1
0x18005e9d1  jnz     short loc_18005E9DF
0x18005e9d3  mov     rax, cs:KdDebuggerNotPresent
0x18005e9da  cmp     byte ptr [rax], 0
0x18005e9dd  jz      short loc_18005E9F8
0x18005e9df  xor     edx, edx
0x18005e9e1  lea     rcx, g_CiOptions
0x18005e9e8  lea     r8d, [rdx+1]
0x18005e9ec  call    cs:__imp_MmProtectDriverSection
0x18005e9f3  nop     dword ptr [rax+rax+00h]
0x18005e9f8  lea     rax, g_CiProtectedContent
0x18005e9ff  mov     [r15], rax
0x18005ea02  mov     dword ptr [r12], 8
0x18005ea0a  mov     eax, edi
0x18005ea0c  mov     rcx, [rbp+57h+var_40]
0x18005ea10  xor     rcx, rsp; StackCookie
0x18005ea13  call    __security_check_cookie
0x18005ea18  add     rsp, 0F0h
0x18005ea1f  pop     r15
0x18005ea21  pop     r14
0x18005ea23  pop     r12
0x18005ea25  pop     rdi
0x18005ea26  pop     rsi
0x18005ea27  pop     rbx
0x18005ea28  pop     rbp
0x18005ea29  retn
```
