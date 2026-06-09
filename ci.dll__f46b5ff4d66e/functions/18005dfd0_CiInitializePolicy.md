# CiInitializePolicy

- ea: `0x18005dfd0`
- end: `0x18005e38b`
- name: `CiInitializePolicy`
- size: `955`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001db68`
- `0x18002bef0`
- `0x18002bfd0`
- `0x18005dfd0`
- `0x18005e61c`
- `0x18005e9b4`
- `0x18005f308`
- `0x18005feb8`
- `0x180060014`
- `0x18006ece4`
- `0x180072068`
- `0x180072dbc`
- `0x18008bc2c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18005e10b`
- `ntoskrnl!ZwCreateKey` at `0x18005e171`
- `ntoskrnl!ZwCreateKey` at `0x18005e10b`
- `ntoskrnl!ZwCreateKey` at `0x18005e171`
- `ntoskrnl!MmProtectDriverSection` at `0x18005e34c`
- `ntoskrnl!MmProtectDriverSection` at `0x18005e34c`
- `ntoskrnl!ZwDeleteKey` at `0x18005e12b`
- `ntoskrnl!ZwDeleteKey` at `0x18005e12b`
- `ntoskrnl!ZwClose` at `0x18005e13c`
- `ntoskrnl!ZwClose` at `0x18005e1c9`
- `ntoskrnl!ZwClose` at `0x18005e13c`
- `ntoskrnl!ZwClose` at `0x18005e1c9`
- `ntoskrnl!ZwSetValueKey` at `0x18005e1b8`
- `ntoskrnl!ZwSetValueKey` at `0x18005e1b8`
- `ntoskrnl!KdDebuggerNotPresent` at `0x18005e333`
- `ntoskrnl!KdDebuggerEnabled` at `0x18005e327`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e03c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e247`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e03c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x18005e247`

## string_xrefs

- `0x18005e096`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\State`

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
        v10 = (*((__int64 (**)(void))&xmmword_1800495D0 + 1))();
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
                qword_180048E50[0] = *(_QWORD *)(a1 + 72);
                qword_180048E58 = *(_QWORD *)(a1 + 80);
                qword_180048E60 = *(_QWORD *)(a1 + 88);
                qword_180048E68 = *(_QWORD *)(a1 + 96);
                g_CiRevocationListInfo = *(_DWORD *)(a1 + 104);
                CiBlackBoxRevocationListUpdate(&qword_180048E50[g_CiRevocationListInfo]);
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
0x18005dfd0  push    rbp
0x18005dfd2  push    rbx
0x18005dfd3  push    rsi
0x18005dfd4  push    rdi
0x18005dfd5  push    r12
0x18005dfd7  push    r14
0x18005dfd9  push    r15
0x18005dfdb  lea     rbp, [rsp-27h]
0x18005dfe0  sub     rsp, 0F0h
0x18005dfe7  mov     rax, cs:__security_cookie
0x18005dfee  xor     rax, rsp
0x18005dff1  mov     [rbp+57h+var_40], rax
0x18005dff5  xorps   xmm0, xmm0
0x18005dff8  xor     eax, eax
0x18005dffa  movups  [rbp+57h+SystemInformation], xmm0
0x18005dffe  mov     [rbp+57h+var_68], rax
0x18005e002  mov     r12, r8
0x18005e005  mov     [rbp+57h+var_D0], eax
0x18005e008  mov     r15, rdx
0x18005e00b  movups  [rbp+57h+var_60], xmm0
0x18005e00f  mov     rbx, rcx
0x18005e012  movups  [rbp+57h+var_50], xmm0
0x18005e016  call    CipSetRevocationListRegKey
0x18005e01b  mov     edi, eax
0x18005e01d  test    eax, eax
0x18005e01f  js      loc_18005E36A
0x18005e025  mov     rcx, rbx
0x18005e028  call    CipCheckLicensing
0x18005e02d  xor     r9d, r9d; ReturnLength
0x18005e030  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x18005e034  lea     r8d, [r9+18h]; SystemInformationLength
0x18005e038  lea     ecx, [r8+77h]; SystemInformationClass
0x18005e03c  call    cs:__imp_ZwQuerySystemInformation
0x18005e043  nop     dword ptr [rax+rax+00h]
0x18005e048  mov     esi, eax
0x18005e04a  mov     eax, 80000000h
0x18005e04f  lea     ecx, [rsi+rax]
0x18005e052  test    eax, ecx
0x18005e054  jnz     short loc_18005E065
0x18005e056  cmp     esi, 80430006h
0x18005e05c  jz      short loc_18005E065
0x18005e05e  mov     edi, esi
0x18005e060  jmp     loc_18005E36A
0x18005e065  cmp     cs:g_HvciSupported, 0
0x18005e06c  mov     r14d, 1
0x18005e072  jz      loc_18005E1FF
0x18005e078  mov     rax, qword ptr cs:xmmword_1800495D0+8
0x18005e07f  call    _guard_dispatch_icall
0x18005e084  mov     edi, eax
0x18005e086  test    al, 2
0x18005e088  jz      loc_18005E1D5
0x18005e08e  bts     cs:g_CiOptions, 0Fh
0x18005e096  lea     rax, aRegistryMachin_4; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18005e09d  mov     [rbp+57h+var_C0], rax
0x18005e0a1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e0a5  lea     rax, [rbp+57h+var_C8]
0x18005e0a9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18005e0b1  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005e0b5  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e0ba  lea     rax, [rsp+120h+var_E0]
0x18005e0bf  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x18005e0c7  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e0cc  xorps   xmm0, xmm0
0x18005e0cf  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e0d4  xor     r9d, r9d; TitleIndex
0x18005e0d7  mov     edx, 20006h; DesiredAccess
0x18005e0dc  mov     [rsp+120h+Class], 0; Class
0x18005e0e5  mov     [rbp+57h+var_C8], 780076h
0x18005e0ed  mov     [rsp+120h+KeyHandle], 0
0x18005e0f6  mov     [rsp+120h+var_E0], 0
0x18005e0fe  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18005e106  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005e10b  call    cs:__imp_ZwCreateKey
0x18005e112  nop     dword ptr [rax+rax+00h]
0x18005e117  test    eax, eax
0x18005e119  js      loc_18005E1D5
0x18005e11f  cmp     [rsp+120h+var_E0], 2
0x18005e124  jnz     short loc_18005E181
0x18005e126  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e12b  call    cs:__imp_ZwDeleteKey
0x18005e132  nop     dword ptr [rax+rax+00h]
0x18005e137  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e13c  call    cs:__imp_ZwClose
0x18005e143  nop     dword ptr [rax+rax+00h]
0x18005e148  lea     rax, [rsp+120h+var_E0]
0x18005e14d  xor     r9d, r9d; TitleIndex
0x18005e150  mov     [rsp+120h+Disposition], rax; Disposition
0x18005e155  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18005e159  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x18005e15e  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e163  mov     edx, 20006h; DesiredAccess
0x18005e168  mov     [rsp+120h+Class], 0; Class
0x18005e171  call    cs:__imp_ZwCreateKey
0x18005e178  nop     dword ptr [rax+rax+00h]
0x18005e17d  test    eax, eax
0x18005e17f  js      short loc_18005E1D5
0x18005e181  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18005e186  lea     rax, aHvcienabled; "HVCIEnabled"
0x18005e18d  mov     [rbp+57h+ValueName.Buffer], rax
0x18005e191  lea     rdx, [rbp+57h+ValueName]; ValueName
0x18005e195  mov     r9d, 4; Type
0x18005e19b  mov     qword ptr [rbp+57h+ValueName.Length], 180016h
0x18005e1a3  lea     rax, [rbp+57h+Data]
0x18005e1a7  mov     [rsp+120h+CreateOptions], r9d; DataSize
0x18005e1ac  xor     r8d, r8d; TitleIndex
0x18005e1af  mov     [rsp+120h+Class], rax; Data
0x18005e1b4  mov     [rbp+57h+Data], r14d
0x18005e1b8  call    cs:__imp_ZwSetValueKey
0x18005e1bf  nop     dword ptr [rax+rax+00h]
0x18005e1c4  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x18005e1c9  call    cs:__imp_ZwClose
0x18005e1d0  nop     dword ptr [rax+rax+00h]
0x18005e1d5  test    dil, 20h
0x18005e1d9  jz      short loc_18005E1E3
0x18005e1db  bts     cs:g_CiOptions, 10h
0x18005e1e3  test    dil, 4
0x18005e1e7  jz      short loc_18005E1F1
0x18005e1e9  bts     cs:g_CiOptions, 0Eh
0x18005e1f1  test    dil, 40h
0x18005e1f5  jz      short loc_18005E1FF
0x18005e1f7  bts     cs:g_CiOptions, 15h
0x18005e1ff  lea     r8, [rbp+57h+var_D0]
0x18005e203  call    CipCheckConfigOptions
0x18005e208  mov     edi, eax
0x18005e20a  test    eax, eax
0x18005e20c  js      loc_18005E36A
0x18005e212  mov     r14d, [rbp+57h+var_D0]
0x18005e216  mov     cs:g_CiTestFlags, r14d
0x18005e21d  test    rbx, rbx
0x18005e220  jz      short loc_18005E238
0x18005e222  mov     ecx, [rbx+30h]
0x18005e225  test    ecx, ecx
0x18005e227  jns     short loc_18005E238
0x18005e229  xor     r8d, r8d
0x18005e22c  lea     rdx, CipLoadWeakCryptoPoliciesFailed
0x18005e233  call    CiLogStatusEventWithCorrelationId
0x18005e238  xor     r9d, r9d; ReturnLength
0x18005e23b  lea     rdx, [rbp+57h+var_60]; SystemInformation
0x18005e23f  lea     r8d, [r9+20h]; SystemInformationLength
0x18005e243  lea     ecx, [r9+5Ah]; SystemInformationClass
0x18005e247  call    cs:__imp_ZwQuerySystemInformation
0x18005e24e  nop     dword ptr [rax+rax+00h]
0x18005e253  mov     edi, eax
0x18005e255  test    eax, eax
0x18005e257  js      loc_18005E36A
0x18005e25d  mov     eax, dword ptr [rbp+57h+var_50]
0x18005e260  shr     esi, 1Fh
0x18005e263  xor     sil, 1
0x18005e267  mov     cs:g_CiFirmwareType, eax
0x18005e26d  cmp     eax, 2
0x18005e270  jnz     short loc_18005E279
0x18005e272  mov     cs:g_SiPolicyIsUefiSystem, 1
0x18005e279  mov     r9d, r14d
0x18005e27c  lea     rdx, [rbp+57h+SystemInformation]
0x18005e280  mov     r8, rbx
0x18005e283  mov     cl, sil
0x18005e286  call    CiInitializePolicyFromPolicies
0x18005e28b  mov     edi, eax
0x18005e28d  test    eax, eax
0x18005e28f  js      loc_18005E36A
0x18005e295  call    CiInitializeNightsWatchPolicyStateGlobal
0x18005e29a  call    CiSetRuntimeUmciSigningLevel
0x18005e29f  mov     eax, cs:g_CiDeveloperMode
0x18005e2a5  test    al, 2
0x18005e2a7  jz      short loc_18005E2AE
0x18005e2a9  call    CipSetUmciExclusionPaths
0x18005e2ae  test    rbx, rbx
0x18005e2b1  jz      short loc_18005E2B8
0x18005e2b3  mov     eax, [rbx+44h]
0x18005e2b6  jmp     short loc_18005E2BA
0x18005e2b8  xor     eax, eax
0x18005e2ba  mov     cs:g_CiCurrentBootId, eax
0x18005e2c0  call    CiBlackBoxInitialize
0x18005e2c5  mov     edi, eax
0x18005e2c7  test    eax, eax
0x18005e2c9  js      loc_18005E36A
0x18005e2cf  test    rbx, rbx
0x18005e2d2  jz      short loc_18005E31D
0x18005e2d4  mov     rax, [rbx+48h]
0x18005e2d8  mov     cs:qword_180048E50, rax
0x18005e2df  mov     rax, [rbx+50h]
0x18005e2e3  mov     cs:qword_180048E58, rax
0x18005e2ea  mov     rax, [rbx+58h]
0x18005e2ee  mov     cs:qword_180048E60, rax
0x18005e2f5  mov     rax, [rbx+60h]
0x18005e2f9  mov     cs:qword_180048E68, rax
0x18005e300  movsxd  rax, dword ptr [rbx+68h]
0x18005e304  mov     rcx, rax
0x18005e307  mov     cs:g_CiRevocationListInfo, eax
0x18005e30d  lea     rax, qword_180048E50
0x18005e314  lea     rcx, [rax+rcx*8]
0x18005e318  call    CiBlackBoxRevocationListUpdate
0x18005e31d  mov     eax, cs:g_CiOptions
0x18005e323  test    al, 10h
0x18005e325  jnz     short loc_18005E33F
0x18005e327  mov     rax, cs:KdDebuggerEnabled
0x18005e32e  cmp     byte ptr [rax], 1
0x18005e331  jnz     short loc_18005E33F
0x18005e333  mov     rax, cs:KdDebuggerNotPresent
0x18005e33a  cmp     byte ptr [rax], 0
0x18005e33d  jz      short loc_18005E358
0x18005e33f  xor     edx, edx
0x18005e341  lea     rcx, g_CiOptions
0x18005e348  lea     r8d, [rdx+1]
0x18005e34c  call    cs:__imp_MmProtectDriverSection
0x18005e353  nop     dword ptr [rax+rax+00h]
0x18005e358  lea     rax, g_CiProtectedContent
0x18005e35f  mov     [r15], rax
0x18005e362  mov     dword ptr [r12], 8
0x18005e36a  mov     eax, edi
0x18005e36c  mov     rcx, [rbp+57h+var_40]
0x18005e370  xor     rcx, rsp; StackCookie
0x18005e373  call    __security_check_cookie
0x18005e378  add     rsp, 0F0h
0x18005e37f  pop     r15
0x18005e381  pop     r14
0x18005e383  pop     r12
0x18005e385  pop     rdi
0x18005e386  pop     rsi
0x18005e387  pop     rbx
0x18005e388  pop     rbp
0x18005e389  retn
```
