# CiHandleDefenderSignals

- ea: `0x180073acc`
- end: `0x180073e31`
- name: `CiHandleDefenderSignals`
- size: `869`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c77c0`
- `0x1800c80fc`

## callees

- `0x18000ecb4`
- `0x18001d290`
- `0x18001d2e8`
- `0x18005abe8`
- `0x180073794`
- `0x180073acc`
- `0x180073e38`
- `0x1800746f0`
- `0x1800e28e8`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180073bfd`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180073bfd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073ddd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073e06`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073ddd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180073e06`

## string_xrefs

- `0x180073d8a`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

## pseudocode

```c
__int64 __fastcall CiHandleDefenderSignals(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  unsigned int v4; // edi
  char v5; // bl
  char v6; // si
  unsigned int v7; // r12d
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rax
  __int128 v14; // xmm0
  _DWORD *v15; // rcx
  unsigned int v16; // edx
  WCHAR *v17; // rax
  struct _UNICODE_STRING *v18; // r8
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  __int64 v21; // rdx
  char v23; // [rsp+40h] [rbp-38h] BYREF
  char v24[3]; // [rsp+41h] [rbp-37h] BYREF
  int ValueData; // [rsp+44h] [rbp-34h] BYREF
  unsigned int v26; // [rsp+48h] [rbp-30h] BYREF
  int v27; // [rsp+4Ch] [rbp-2Ch] BYREF
  int v28; // [rsp+50h] [rbp-28h] BYREF
  int RegistryValue; // [rsp+54h] [rbp-24h]
  int v30; // [rsp+58h] [rbp-20h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-18h] BYREF

  v4 = 0;
  RegistryValue = 0;
  v5 = 0;
  v26 = 0;
  v6 = 0;
  v23 = 0;
  v7 = 0;
  ValueData = 0;
  v28 = -1;
  v27 = 0;
  v30 = 0;
  v24[0] = 0;
  if ( a2 )
  {
    v11 = 0;
    do
    {
      v12 = *(_DWORD *)(a3 + 24 * v11 + 4);
      if ( v12 == 1 )
      {
        v13 = *(_QWORD *)(a3 + 24 * v11 + 16);
        v14 = 0;
        v15 = (_DWORD *)(v13 + 8);
        if ( !*(_DWORD *)(v13 + 4) && *v15 == 200 )
          v14 = *(_OWORD *)(v13 + 12);
        if ( a4 )
        {
          *(_BYTE *)(a1 + 2248) = 1;
          *(_DWORD *)(a1 + 2224) = *(_DWORD *)(v13 + 4);
          *(_DWORD *)(a1 + 2228) = *v15;
          *(_OWORD *)(a1 + 2232) = v14;
        }
        else
        {
          *(_BYTE *)(a1 + 2184) = 1;
          *(_DWORD *)(a1 + 2160) = *(_DWORD *)(v13 + 4);
          *(_DWORD *)(a1 + 2164) = *v15;
          *(_OWORD *)(a1 + 2168) = v14;
        }
      }
      else
      {
        v16 = *(_DWORD *)(a3 + 24 * v11 + 8);
        switch ( v12 )
        {
          case 2:
            v17 = *(WCHAR **)(a3 + 24 * v11 + 16);
            SourceString.Length = *(_DWORD *)(a3 + 24 * v11 + 8);
            SourceString.MaximumLength = v16;
            SourceString.Buffer = v17;
            *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
            if ( RtlUnicodeStringValidateEx(&SourceString, 0) >= 0 )
            {
              v18 = (struct _UNICODE_STRING *)(a1 + 2208);
              if ( !a4 )
                v18 = (struct _UNICODE_STRING *)(a1 + 2144);
              RtlDuplicateUnicodeString(1u, &SourceString, v18);
            }
            break;
          case 3:
            if ( v16 == 8 )
              CiHandleFlagsFromDefender(
                a1,
                **(unsigned __int8 **)(a3 + 24 * v11 + 16),
                (unsigned int)&v23,
                (unsigned int)&v26,
                (__int64)v24);
            break;
          case 4:
            if ( v16 >= 0x30 )
            {
              v19 = *(_QWORD *)(a3 + 24 * v11 + 16);
              if ( *(_DWORD *)v19 == 1
                && !*(_DWORD *)(v19 + 4)
                && *(_DWORD *)(v19 + 8) == 32780
                && *(_DWORD *)(v19 + 12) == 32 )
              {
                v20 = -(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFBC0uLL;
                *(_DWORD *)(v20 + a1 + 3340) = 32780;
                *(_DWORD *)(v20 + a1 + 3344) = 32;
                *(_OWORD *)(v20 + a1 + 3348) = *(_OWORD *)(v19 + 16);
                *(_OWORD *)(v20 + a1 + 3364) = *(_OWORD *)(v19 + 32);
              }
            }
            break;
          default:
            if ( v12 == 5 && v16 == 4 )
              *(_DWORD *)(a1 + 2136) = **(_DWORD **)(a3 + 24 * v11 + 16);
            break;
        }
      }
      ++v7;
      ++v11;
    }
    while ( v7 < a2 );
    v5 = v23;
    v4 = v26;
    v6 = v24[0];
  }
  if ( g_ReceivedSignalFromDefender == 1 && !g_HandledSignalToSwitchNWToEnforcementMode )
  {
    v5 = 1;
    v4 = 1;
    v6 = 1;
    if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
      ValueData = 2;
  }
  if ( !g_ReceivedSignalFromDefender && !g_HandledSignalToSwitchNWOff )
  {
    v4 = 0;
    v5 = 1;
    v6 = 0;
    if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
      ValueData = 5;
  }
  if ( !(unsigned int)Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline()
    || !(unsigned __int8)SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktopEval, 0)
    || !(unsigned __int8)CiSmartAppControlClientSideEnable() )
  {
LABEL_43:
    if ( !v5 )
      return (unsigned int)RegistryValue;
    goto LABEL_44;
  }
  v5 = 1;
  v4 = 1;
  v6 = 1;
  if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
  {
    ValueData = 1;
    goto LABEL_43;
  }
LABEL_44:
  if ( (unsigned int)Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline() )
  {
    RegistryValue = CipGetRegistryValue(
                      0,
                      (unsigned int)L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
                      (unsigned int)L"VerifiedAndReputablePolicyState",
                      0,
                      (__int64)&v27,
                      4,
                      (__int64)&v30);
    if ( RegistryValue >= 0 )
      v28 = v27;
    RtlWriteRegistryValue(
      0,
      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
      L"SAC_EnforcementReason",
      4u,
      &ValueData,
      4u);
    RtlWriteRegistryValue(
      0,
      L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI\\Policy",
      L"SAC_PreviousState",
      4u,
      &v28,
      4u);
  }
  LOBYTE(v21) = v6;
  CiAsyncRefreshPoliciesOnNightsWatchModeChange(v4, v21);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x180073acc  mov     [rsp-40h+arg_8], edx
0x180073ad0  push    rbp
0x180073ad1  push    rbx
0x180073ad2  push    rsi
0x180073ad3  push    rdi
0x180073ad4  push    r12
0x180073ad6  push    r13
0x180073ad8  push    r14
0x180073ada  push    r15
0x180073adc  mov     rbp, rsp
0x180073adf  sub     rsp, 78h
0x180073ae3  xor     edi, edi
0x180073ae5  mov     [rbp+var_24], 0
0x180073aec  xor     bl, bl
0x180073aee  mov     [rbp+var_30], edi
0x180073af1  xor     sil, sil
0x180073af4  mov     [rbp+var_38], bl
0x180073af7  xor     r12d, r12d
0x180073afa  mov     [rbp+var_34], edi
0x180073afd  mov     [rbp+var_28], 0FFFFFFFFh
0x180073b04  mov     r13b, r9b
0x180073b07  mov     [rbp+var_2C], edi
0x180073b0a  mov     r15, r8
0x180073b0d  mov     [rbp+var_20], edi
0x180073b10  mov     r14, rcx
0x180073b13  mov     [rbp+var_37], sil
0x180073b17  test    edx, edx
0x180073b19  jz      loc_180073CD4
0x180073b1f  mov     edi, [rbp+arg_8]
0x180073b22  xor     ebx, ebx
0x180073b24  mov     esi, 800Ch
0x180073b29  lea     rcx, [rbx+rbx*2]
0x180073b2d  mov     eax, [r15+rcx*8+4]
0x180073b32  cmp     eax, 1
0x180073b35  jnz     short loc_180073BAC
0x180073b37  mov     rax, [r15+rcx*8+10h]
0x180073b3c  xorps   xmm0, xmm0
0x180073b3f  cmp     dword ptr [rax+4], 0
0x180073b43  lea     rcx, [rax+8]
0x180073b47  jnz     short loc_180073B55
0x180073b49  cmp     dword ptr [rcx], 0C8h
0x180073b4f  jnz     short loc_180073B55
0x180073b51  movups  xmm0, xmmword ptr [rax+0Ch]
0x180073b55  test    r13b, r13b
0x180073b58  jz      short loc_180073B83
0x180073b5a  mov     byte ptr [r14+8C8h], 1
0x180073b62  mov     eax, [rax+4]
0x180073b65  mov     [r14+8B0h], eax
0x180073b6c  mov     eax, [rcx]
0x180073b6e  mov     [r14+8B4h], eax
0x180073b75  movdqu  xmmword ptr [r14+8B8h], xmm0
0x180073b7e  jmp     loc_180073CBB
0x180073b83  mov     byte ptr [r14+888h], 1
0x180073b8b  mov     eax, [rax+4]
0x180073b8e  mov     [r14+870h], eax
0x180073b95  mov     eax, [rcx]
0x180073b97  mov     [r14+874h], eax
0x180073b9e  movdqu  xmmword ptr [r14+878h], xmm0
0x180073ba7  jmp     loc_180073CBB
0x180073bac  mov     edx, [r15+rcx*8+8]
0x180073bb1  cmp     eax, 2
0x180073bb4  jnz     short loc_180073C0E
0x180073bb6  mov     rax, [r15+rcx*8+10h]
0x180073bbb  lea     rcx, [rbp+SourceString]; SourceString
0x180073bbf  mov     [rbp+SourceString.Length], dx
0x180073bc3  mov     [rbp+SourceString.MaximumLength], dx
0x180073bc7  xor     edx, edx; dwFlags
0x180073bc9  mov     [rbp+SourceString.Buffer], rax
0x180073bcd  mov     dword ptr [rbp+SourceString+4], 0
0x180073bd4  call    RtlUnicodeStringValidateEx
0x180073bd9  test    eax, eax
0x180073bdb  js      loc_180073CBB
0x180073be1  lea     rdx, [rbp+SourceString]; StringIn
0x180073be5  mov     ecx, 1; Flags
0x180073bea  lea     r8, [r14+8A0h]
0x180073bf1  test    r13b, r13b
0x180073bf4  jnz     short loc_180073BFD
0x180073bf6  lea     r8, [r14+860h]; StringOut
0x180073bfd  call    cs:__imp_RtlDuplicateUnicodeString
0x180073c04  nop     dword ptr [rax+rax+00h]
0x180073c09  jmp     loc_180073CBB
0x180073c0e  cmp     eax, 3
0x180073c11  jnz     short loc_180073C3F
0x180073c13  cmp     edx, 8
0x180073c16  jnz     loc_180073CBB
0x180073c1c  mov     rax, [r15+rcx*8+10h]
0x180073c21  lea     r9, [rbp+var_30]
0x180073c25  lea     r8, [rbp+var_38]
0x180073c29  mov     rcx, r14
0x180073c2c  movzx   edx, byte ptr [rax]
0x180073c2f  lea     rax, [rbp+var_37]
0x180073c33  mov     [rsp+78h+ValueData], rax
0x180073c38  call    CiHandleFlagsFromDefender
0x180073c3d  jmp     short loc_180073CBB
0x180073c3f  cmp     eax, 4
0x180073c42  jnz     short loc_180073CA3
0x180073c44  cmp     edx, 30h ; '0'
0x180073c47  jb      short loc_180073CBB
0x180073c49  mov     rdx, [r15+rcx*8+10h]
0x180073c4e  cmp     dword ptr [rdx], 1
0x180073c51  jnz     short loc_180073CBB
0x180073c53  cmp     dword ptr [rdx+4], 0
0x180073c57  jnz     short loc_180073CBB
0x180073c59  cmp     [rdx+8], esi
0x180073c5c  jnz     short loc_180073CBB
0x180073c5e  cmp     dword ptr [rdx+0Ch], 20h ; ' '
0x180073c62  jnz     short loc_180073CBB
0x180073c64  mov     al, r13b
0x180073c67  neg     al
0x180073c69  sbb     rcx, rcx
0x180073c6c  and     rcx, 0FFFFFFFFFFFFFBC0h
0x180073c73  mov     [rcx+r14+0D0Ch], esi
0x180073c7b  mov     dword ptr [rcx+r14+0D10h], 20h ; ' '
0x180073c87  movups  xmm0, xmmword ptr [rdx+10h]
0x180073c8b  movups  xmmword ptr [rcx+r14+0D14h], xmm0
0x180073c94  movups  xmm1, xmmword ptr [rdx+20h]
0x180073c98  movups  xmmword ptr [rcx+r14+0D24h], xmm1
0x180073ca1  jmp     short loc_180073CBB
0x180073ca3  cmp     eax, 5
0x180073ca6  jnz     short loc_180073CBB
0x180073ca8  cmp     edx, 4
0x180073cab  jnz     short loc_180073CBB
0x180073cad  mov     rax, [r15+rcx*8+10h]
0x180073cb2  mov     ecx, [rax]
0x180073cb4  mov     [r14+858h], ecx
0x180073cbb  inc     r12d
0x180073cbe  inc     rbx
0x180073cc1  cmp     r12d, edi
0x180073cc4  jb      loc_180073B29
0x180073cca  mov     bl, [rbp+var_38]
0x180073ccd  mov     edi, [rbp+var_30]
0x180073cd0  mov     sil, [rbp+var_37]
0x180073cd4  mov     eax, cs:g_ReceivedSignalFromDefender
0x180073cda  cmp     eax, 1
0x180073cdd  jnz     short loc_180073D01
0x180073cdf  mov     eax, cs:g_HandledSignalToSwitchNWToEnforcementMode
0x180073ce5  test    eax, eax
0x180073ce7  jnz     short loc_180073D01
0x180073ce9  mov     bl, 1
0x180073ceb  lea     edi, [rax+1]
0x180073cee  mov     sil, bl
0x180073cf1  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073cf6  test    eax, eax
0x180073cf8  jz      short loc_180073D01
0x180073cfa  mov     [rbp+var_34], 2
0x180073d01  mov     eax, cs:g_ReceivedSignalFromDefender
0x180073d07  test    eax, eax
0x180073d09  jnz     short loc_180073D2C
0x180073d0b  mov     eax, cs:g_HandledSignalToSwitchNWOff
0x180073d11  test    eax, eax
0x180073d13  jnz     short loc_180073D2C
0x180073d15  xor     edi, edi
0x180073d17  mov     bl, 1
0x180073d19  xor     sil, sil
0x180073d1c  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073d21  test    eax, eax
0x180073d23  jz      short loc_180073D2C
0x180073d25  mov     [rbp+var_34], 5
0x180073d2c  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x180073d31  test    eax, eax
0x180073d33  jz      short loc_180073D66
0x180073d35  xor     edx, edx
0x180073d37  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x180073d3e  call    SIPolicyIsPolicyActive
0x180073d43  test    al, al
0x180073d45  jz      short loc_180073D66
0x180073d47  call    CiSmartAppControlClientSideEnable
0x180073d4c  test    al, al
0x180073d4e  jz      short loc_180073D66
0x180073d50  mov     bl, 1
0x180073d52  mov     edi, 1
0x180073d57  mov     sil, bl
0x180073d5a  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073d5f  test    eax, eax
0x180073d61  jz      short loc_180073D6E
0x180073d63  mov     [rbp+var_34], edi
0x180073d66  test    bl, bl
0x180073d68  jz      loc_180073E1C
0x180073d6e  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073d73  test    eax, eax
0x180073d75  jz      loc_180073E12
0x180073d7b  lea     rax, [rbp+var_20]
0x180073d7f  mov     r14d, 4
0x180073d85  mov     [rsp+78h+var_48], rax
0x180073d8a  lea     rbx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180073d91  lea     rax, [rbp+var_2C]
0x180073d95  mov     [rsp+78h+ValueLength], r14d
0x180073d9a  xor     r9d, r9d
0x180073d9d  mov     [rsp+78h+ValueData], rax
0x180073da2  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180073da9  mov     rdx, rbx
0x180073dac  xor     ecx, ecx
0x180073dae  call    CipGetRegistryValue
0x180073db3  mov     [rbp+var_24], eax
0x180073db6  test    eax, eax
0x180073db8  js      short loc_180073DC0
0x180073dba  mov     ecx, [rbp+var_2C]
0x180073dbd  mov     [rbp+var_28], ecx
0x180073dc0  lea     rax, [rbp+var_34]
0x180073dc4  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x180073dc9  mov     r9d, r14d; ValueType
0x180073dcc  mov     [rsp+78h+ValueData], rax; ValueData
0x180073dd1  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180073dd8  mov     rdx, rbx; Path
0x180073ddb  xor     ecx, ecx; RelativeTo
0x180073ddd  call    cs:__imp_RtlWriteRegistryValue
0x180073de4  nop     dword ptr [rax+rax+00h]
0x180073de9  lea     rax, [rbp+var_28]
0x180073ded  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x180073df2  mov     r9d, r14d; ValueType
0x180073df5  mov     [rsp+78h+ValueData], rax; ValueData
0x180073dfa  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x180073e01  mov     rdx, rbx; Path
0x180073e04  xor     ecx, ecx; RelativeTo
0x180073e06  call    cs:__imp_RtlWriteRegistryValue
0x180073e0d  nop     dword ptr [rax+rax+00h]
0x180073e12  mov     dl, sil
0x180073e15  mov     ecx, edi
0x180073e17  call    CiAsyncRefreshPoliciesOnNightsWatchModeChange
0x180073e1c  mov     eax, [rbp+var_24]
0x180073e1f  add     rsp, 78h
0x180073e23  pop     r15
0x180073e25  pop     r14
0x180073e27  pop     r13
0x180073e29  pop     r12
0x180073e2b  pop     rdi
0x180073e2c  pop     rsi
0x180073e2d  pop     rbx
0x180073e2e  pop     rbp
0x180073e2f  retn
```
