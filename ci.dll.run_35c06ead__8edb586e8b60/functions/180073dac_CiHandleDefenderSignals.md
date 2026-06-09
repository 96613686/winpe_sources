# CiHandleDefenderSignals

- ea: `0x180073dac`
- end: `0x180074111`
- name: `CiHandleDefenderSignals`
- size: `869`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c77d0`
- `0x1800c810c`

## callees

- `0x18000ecc4`
- `0x18001d348`
- `0x18001d3a0`
- `0x18005ab10`
- `0x180073a74`
- `0x180073dac`
- `0x180074118`
- `0x1800749d0`
- `0x1800e27f8`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180073edd`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x180073edd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800740bd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800740e6`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800740bd`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1800740e6`

## string_xrefs

- `0x18007406a`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
                v20 = -(__int64)(a4 != 0) & 0xFFFFFFFFFFFFFBB0uLL;
                *(_DWORD *)(v20 + a1 + 3356) = 32780;
                *(_DWORD *)(v20 + a1 + 3360) = 32;
                *(_OWORD *)(v20 + a1 + 3364) = *(_OWORD *)(v19 + 16);
                *(_OWORD *)(v20 + a1 + 3380) = *(_OWORD *)(v19 + 32);
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
0x180073dac  mov     [rsp-40h+arg_8], edx
0x180073db0  push    rbp
0x180073db1  push    rbx
0x180073db2  push    rsi
0x180073db3  push    rdi
0x180073db4  push    r12
0x180073db6  push    r13
0x180073db8  push    r14
0x180073dba  push    r15
0x180073dbc  mov     rbp, rsp
0x180073dbf  sub     rsp, 78h
0x180073dc3  xor     edi, edi
0x180073dc5  mov     [rbp+var_24], 0
0x180073dcc  xor     bl, bl
0x180073dce  mov     [rbp+var_30], edi
0x180073dd1  xor     sil, sil
0x180073dd4  mov     [rbp+var_38], bl
0x180073dd7  xor     r12d, r12d
0x180073dda  mov     [rbp+var_34], edi
0x180073ddd  mov     [rbp+var_28], 0FFFFFFFFh
0x180073de4  mov     r13b, r9b
0x180073de7  mov     [rbp+var_2C], edi
0x180073dea  mov     r15, r8
0x180073ded  mov     [rbp+var_20], edi
0x180073df0  mov     r14, rcx
0x180073df3  mov     [rbp+var_37], sil
0x180073df7  test    edx, edx
0x180073df9  jz      loc_180073FB4
0x180073dff  mov     edi, [rbp+arg_8]
0x180073e02  xor     ebx, ebx
0x180073e04  mov     esi, 800Ch
0x180073e09  lea     rcx, [rbx+rbx*2]
0x180073e0d  mov     eax, [r15+rcx*8+4]
0x180073e12  cmp     eax, 1
0x180073e15  jnz     short loc_180073E8C
0x180073e17  mov     rax, [r15+rcx*8+10h]
0x180073e1c  xorps   xmm0, xmm0
0x180073e1f  cmp     dword ptr [rax+4], 0
0x180073e23  lea     rcx, [rax+8]
0x180073e27  jnz     short loc_180073E35
0x180073e29  cmp     dword ptr [rcx], 0C8h
0x180073e2f  jnz     short loc_180073E35
0x180073e31  movups  xmm0, xmmword ptr [rax+0Ch]
0x180073e35  test    r13b, r13b
0x180073e38  jz      short loc_180073E63
0x180073e3a  mov     byte ptr [r14+8C8h], 1
0x180073e42  mov     eax, [rax+4]
0x180073e45  mov     [r14+8B0h], eax
0x180073e4c  mov     eax, [rcx]
0x180073e4e  mov     [r14+8B4h], eax
0x180073e55  movdqu  xmmword ptr [r14+8B8h], xmm0
0x180073e5e  jmp     loc_180073F9B
0x180073e63  mov     byte ptr [r14+888h], 1
0x180073e6b  mov     eax, [rax+4]
0x180073e6e  mov     [r14+870h], eax
0x180073e75  mov     eax, [rcx]
0x180073e77  mov     [r14+874h], eax
0x180073e7e  movdqu  xmmword ptr [r14+878h], xmm0
0x180073e87  jmp     loc_180073F9B
0x180073e8c  mov     edx, [r15+rcx*8+8]
0x180073e91  cmp     eax, 2
0x180073e94  jnz     short loc_180073EEE
0x180073e96  mov     rax, [r15+rcx*8+10h]
0x180073e9b  lea     rcx, [rbp+SourceString]; SourceString
0x180073e9f  mov     [rbp+SourceString.Length], dx
0x180073ea3  mov     [rbp+SourceString.MaximumLength], dx
0x180073ea7  xor     edx, edx; dwFlags
0x180073ea9  mov     [rbp+SourceString.Buffer], rax
0x180073ead  mov     dword ptr [rbp+SourceString+4], 0
0x180073eb4  call    RtlUnicodeStringValidateEx
0x180073eb9  test    eax, eax
0x180073ebb  js      loc_180073F9B
0x180073ec1  lea     rdx, [rbp+SourceString]; StringIn
0x180073ec5  mov     ecx, 1; Flags
0x180073eca  lea     r8, [r14+8A0h]
0x180073ed1  test    r13b, r13b
0x180073ed4  jnz     short loc_180073EDD
0x180073ed6  lea     r8, [r14+860h]; StringOut
0x180073edd  call    cs:__imp_RtlDuplicateUnicodeString
0x180073ee4  nop     dword ptr [rax+rax+00h]
0x180073ee9  jmp     loc_180073F9B
0x180073eee  cmp     eax, 3
0x180073ef1  jnz     short loc_180073F1F
0x180073ef3  cmp     edx, 8
0x180073ef6  jnz     loc_180073F9B
0x180073efc  mov     rax, [r15+rcx*8+10h]
0x180073f01  lea     r9, [rbp+var_30]
0x180073f05  lea     r8, [rbp+var_38]
0x180073f09  mov     rcx, r14
0x180073f0c  movzx   edx, byte ptr [rax]
0x180073f0f  lea     rax, [rbp+var_37]
0x180073f13  mov     [rsp+78h+ValueData], rax
0x180073f18  call    CiHandleFlagsFromDefender
0x180073f1d  jmp     short loc_180073F9B
0x180073f1f  cmp     eax, 4
0x180073f22  jnz     short loc_180073F83
0x180073f24  cmp     edx, 30h ; '0'
0x180073f27  jb      short loc_180073F9B
0x180073f29  mov     rdx, [r15+rcx*8+10h]
0x180073f2e  cmp     dword ptr [rdx], 1
0x180073f31  jnz     short loc_180073F9B
0x180073f33  cmp     dword ptr [rdx+4], 0
0x180073f37  jnz     short loc_180073F9B
0x180073f39  cmp     [rdx+8], esi
0x180073f3c  jnz     short loc_180073F9B
0x180073f3e  cmp     dword ptr [rdx+0Ch], 20h ; ' '
0x180073f42  jnz     short loc_180073F9B
0x180073f44  mov     al, r13b
0x180073f47  neg     al
0x180073f49  sbb     rcx, rcx
0x180073f4c  and     rcx, 0FFFFFFFFFFFFFBB0h
0x180073f53  mov     [rcx+r14+0D1Ch], esi
0x180073f5b  mov     dword ptr [rcx+r14+0D20h], 20h ; ' '
0x180073f67  movups  xmm0, xmmword ptr [rdx+10h]
0x180073f6b  movups  xmmword ptr [rcx+r14+0D24h], xmm0
0x180073f74  movups  xmm1, xmmword ptr [rdx+20h]
0x180073f78  movups  xmmword ptr [rcx+r14+0D34h], xmm1
0x180073f81  jmp     short loc_180073F9B
0x180073f83  cmp     eax, 5
0x180073f86  jnz     short loc_180073F9B
0x180073f88  cmp     edx, 4
0x180073f8b  jnz     short loc_180073F9B
0x180073f8d  mov     rax, [r15+rcx*8+10h]
0x180073f92  mov     ecx, [rax]
0x180073f94  mov     [r14+858h], ecx
0x180073f9b  inc     r12d
0x180073f9e  inc     rbx
0x180073fa1  cmp     r12d, edi
0x180073fa4  jb      loc_180073E09
0x180073faa  mov     bl, [rbp+var_38]
0x180073fad  mov     edi, [rbp+var_30]
0x180073fb0  mov     sil, [rbp+var_37]
0x180073fb4  mov     eax, cs:g_ReceivedSignalFromDefender
0x180073fba  cmp     eax, 1
0x180073fbd  jnz     short loc_180073FE1
0x180073fbf  mov     eax, cs:g_HandledSignalToSwitchNWToEnforcementMode
0x180073fc5  test    eax, eax
0x180073fc7  jnz     short loc_180073FE1
0x180073fc9  mov     bl, 1
0x180073fcb  lea     edi, [rax+1]
0x180073fce  mov     sil, bl
0x180073fd1  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180073fd6  test    eax, eax
0x180073fd8  jz      short loc_180073FE1
0x180073fda  mov     [rbp+var_34], 2
0x180073fe1  mov     eax, cs:g_ReceivedSignalFromDefender
0x180073fe7  test    eax, eax
0x180073fe9  jnz     short loc_18007400C
0x180073feb  mov     eax, cs:g_HandledSignalToSwitchNWOff
0x180073ff1  test    eax, eax
0x180073ff3  jnz     short loc_18007400C
0x180073ff5  xor     edi, edi
0x180073ff7  mov     bl, 1
0x180073ff9  xor     sil, sil
0x180073ffc  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180074001  test    eax, eax
0x180074003  jz      short loc_18007400C
0x180074005  mov     [rbp+var_34], 5
0x18007400c  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x180074011  test    eax, eax
0x180074013  jz      short loc_180074046
0x180074015  xor     edx, edx
0x180074017  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x18007401e  call    SIPolicyIsPolicyActive
0x180074023  test    al, al
0x180074025  jz      short loc_180074046
0x180074027  call    CiSmartAppControlClientSideEnable
0x18007402c  test    al, al
0x18007402e  jz      short loc_180074046
0x180074030  mov     bl, 1
0x180074032  mov     edi, 1
0x180074037  mov     sil, bl
0x18007403a  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x18007403f  test    eax, eax
0x180074041  jz      short loc_18007404E
0x180074043  mov     [rbp+var_34], edi
0x180074046  test    bl, bl
0x180074048  jz      loc_1800740FC
0x18007404e  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180074053  test    eax, eax
0x180074055  jz      loc_1800740F2
0x18007405b  lea     rax, [rbp+var_20]
0x18007405f  mov     r14d, 4
0x180074065  mov     [rsp+78h+var_48], rax
0x18007406a  lea     rbx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180074071  lea     rax, [rbp+var_2C]
0x180074075  mov     [rsp+78h+ValueLength], r14d
0x18007407a  xor     r9d, r9d
0x18007407d  mov     [rsp+78h+ValueData], rax
0x180074082  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180074089  mov     rdx, rbx
0x18007408c  xor     ecx, ecx
0x18007408e  call    CipGetRegistryValue
0x180074093  mov     [rbp+var_24], eax
0x180074096  test    eax, eax
0x180074098  js      short loc_1800740A0
0x18007409a  mov     ecx, [rbp+var_2C]
0x18007409d  mov     [rbp+var_28], ecx
0x1800740a0  lea     rax, [rbp+var_34]
0x1800740a4  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x1800740a9  mov     r9d, r14d; ValueType
0x1800740ac  mov     [rsp+78h+ValueData], rax; ValueData
0x1800740b1  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x1800740b8  mov     rdx, rbx; Path
0x1800740bb  xor     ecx, ecx; RelativeTo
0x1800740bd  call    cs:__imp_RtlWriteRegistryValue
0x1800740c4  nop     dword ptr [rax+rax+00h]
0x1800740c9  lea     rax, [rbp+var_28]
0x1800740cd  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x1800740d2  mov     r9d, r14d; ValueType
0x1800740d5  mov     [rsp+78h+ValueData], rax; ValueData
0x1800740da  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x1800740e1  mov     rdx, rbx; Path
0x1800740e4  xor     ecx, ecx; RelativeTo
0x1800740e6  call    cs:__imp_RtlWriteRegistryValue
0x1800740ed  nop     dword ptr [rax+rax+00h]
0x1800740f2  mov     dl, sil
0x1800740f5  mov     ecx, edi
0x1800740f7  call    CiAsyncRefreshPoliciesOnNightsWatchModeChange
0x1800740fc  mov     eax, [rbp+var_24]
0x1800740ff  add     rsp, 78h
0x180074103  pop     r15
0x180074105  pop     r14
0x180074107  pop     r13
0x180074109  pop     r12
0x18007410b  pop     rdi
0x18007410c  pop     rsi
0x18007410d  pop     rbx
0x18007410e  pop     rbp
0x18007410f  retn
```
