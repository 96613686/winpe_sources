# CiHandleDefenderSignals

- ea: `0x18007281c`
- end: `0x180072b81`
- name: `CiHandleDefenderSignals`
- size: `869`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800c6340`
- `0x1800c6c7c`

## callees

- `0x18000ecb4`
- `0x18001d2f8`
- `0x18001d350`
- `0x180059ed0`
- `0x1800724e4`
- `0x18007281c`
- `0x180072b88`
- `0x180073440`
- `0x1800e18f8`

## import_xrefs

- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007294d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x18007294d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072b2d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072b56`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072b2d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x180072b56`

## string_xrefs

- `0x180072ada`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI\Policy`

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
0x18007281c  mov     [rsp-40h+arg_8], edx
0x180072820  push    rbp
0x180072821  push    rbx
0x180072822  push    rsi
0x180072823  push    rdi
0x180072824  push    r12
0x180072826  push    r13
0x180072828  push    r14
0x18007282a  push    r15
0x18007282c  mov     rbp, rsp
0x18007282f  sub     rsp, 78h
0x180072833  xor     edi, edi
0x180072835  mov     [rbp+var_24], 0
0x18007283c  xor     bl, bl
0x18007283e  mov     [rbp+var_30], edi
0x180072841  xor     sil, sil
0x180072844  mov     [rbp+var_38], bl
0x180072847  xor     r12d, r12d
0x18007284a  mov     [rbp+var_34], edi
0x18007284d  mov     [rbp+var_28], 0FFFFFFFFh
0x180072854  mov     r13b, r9b
0x180072857  mov     [rbp+var_2C], edi
0x18007285a  mov     r15, r8
0x18007285d  mov     [rbp+var_20], edi
0x180072860  mov     r14, rcx
0x180072863  mov     [rbp+var_37], sil
0x180072867  test    edx, edx
0x180072869  jz      loc_180072A24
0x18007286f  mov     edi, [rbp+arg_8]
0x180072872  xor     ebx, ebx
0x180072874  mov     esi, 800Ch
0x180072879  lea     rcx, [rbx+rbx*2]
0x18007287d  mov     eax, [r15+rcx*8+4]
0x180072882  cmp     eax, 1
0x180072885  jnz     short loc_1800728FC
0x180072887  mov     rax, [r15+rcx*8+10h]
0x18007288c  xorps   xmm0, xmm0
0x18007288f  cmp     dword ptr [rax+4], 0
0x180072893  lea     rcx, [rax+8]
0x180072897  jnz     short loc_1800728A5
0x180072899  cmp     dword ptr [rcx], 0C8h
0x18007289f  jnz     short loc_1800728A5
0x1800728a1  movups  xmm0, xmmword ptr [rax+0Ch]
0x1800728a5  test    r13b, r13b
0x1800728a8  jz      short loc_1800728D3
0x1800728aa  mov     byte ptr [r14+8C8h], 1
0x1800728b2  mov     eax, [rax+4]
0x1800728b5  mov     [r14+8B0h], eax
0x1800728bc  mov     eax, [rcx]
0x1800728be  mov     [r14+8B4h], eax
0x1800728c5  movdqu  xmmword ptr [r14+8B8h], xmm0
0x1800728ce  jmp     loc_180072A0B
0x1800728d3  mov     byte ptr [r14+888h], 1
0x1800728db  mov     eax, [rax+4]
0x1800728de  mov     [r14+870h], eax
0x1800728e5  mov     eax, [rcx]
0x1800728e7  mov     [r14+874h], eax
0x1800728ee  movdqu  xmmword ptr [r14+878h], xmm0
0x1800728f7  jmp     loc_180072A0B
0x1800728fc  mov     edx, [r15+rcx*8+8]
0x180072901  cmp     eax, 2
0x180072904  jnz     short loc_18007295E
0x180072906  mov     rax, [r15+rcx*8+10h]
0x18007290b  lea     rcx, [rbp+SourceString]; SourceString
0x18007290f  mov     [rbp+SourceString.Length], dx
0x180072913  mov     [rbp+SourceString.MaximumLength], dx
0x180072917  xor     edx, edx; dwFlags
0x180072919  mov     [rbp+SourceString.Buffer], rax
0x18007291d  mov     dword ptr [rbp+SourceString+4], 0
0x180072924  call    RtlUnicodeStringValidateEx
0x180072929  test    eax, eax
0x18007292b  js      loc_180072A0B
0x180072931  lea     rdx, [rbp+SourceString]; StringIn
0x180072935  mov     ecx, 1; Flags
0x18007293a  lea     r8, [r14+8A0h]
0x180072941  test    r13b, r13b
0x180072944  jnz     short loc_18007294D
0x180072946  lea     r8, [r14+860h]; StringOut
0x18007294d  call    cs:__imp_RtlDuplicateUnicodeString
0x180072954  nop     dword ptr [rax+rax+00h]
0x180072959  jmp     loc_180072A0B
0x18007295e  cmp     eax, 3
0x180072961  jnz     short loc_18007298F
0x180072963  cmp     edx, 8
0x180072966  jnz     loc_180072A0B
0x18007296c  mov     rax, [r15+rcx*8+10h]
0x180072971  lea     r9, [rbp+var_30]
0x180072975  lea     r8, [rbp+var_38]
0x180072979  mov     rcx, r14
0x18007297c  movzx   edx, byte ptr [rax]
0x18007297f  lea     rax, [rbp+var_37]
0x180072983  mov     [rsp+78h+ValueData], rax
0x180072988  call    CiHandleFlagsFromDefender
0x18007298d  jmp     short loc_180072A0B
0x18007298f  cmp     eax, 4
0x180072992  jnz     short loc_1800729F3
0x180072994  cmp     edx, 30h ; '0'
0x180072997  jb      short loc_180072A0B
0x180072999  mov     rdx, [r15+rcx*8+10h]
0x18007299e  cmp     dword ptr [rdx], 1
0x1800729a1  jnz     short loc_180072A0B
0x1800729a3  cmp     dword ptr [rdx+4], 0
0x1800729a7  jnz     short loc_180072A0B
0x1800729a9  cmp     [rdx+8], esi
0x1800729ac  jnz     short loc_180072A0B
0x1800729ae  cmp     dword ptr [rdx+0Ch], 20h ; ' '
0x1800729b2  jnz     short loc_180072A0B
0x1800729b4  mov     al, r13b
0x1800729b7  neg     al
0x1800729b9  sbb     rcx, rcx
0x1800729bc  and     rcx, 0FFFFFFFFFFFFFBC0h
0x1800729c3  mov     [rcx+r14+0D0Ch], esi
0x1800729cb  mov     dword ptr [rcx+r14+0D10h], 20h ; ' '
0x1800729d7  movups  xmm0, xmmword ptr [rdx+10h]
0x1800729db  movups  xmmword ptr [rcx+r14+0D14h], xmm0
0x1800729e4  movups  xmm1, xmmword ptr [rdx+20h]
0x1800729e8  movups  xmmword ptr [rcx+r14+0D24h], xmm1
0x1800729f1  jmp     short loc_180072A0B
0x1800729f3  cmp     eax, 5
0x1800729f6  jnz     short loc_180072A0B
0x1800729f8  cmp     edx, 4
0x1800729fb  jnz     short loc_180072A0B
0x1800729fd  mov     rax, [r15+rcx*8+10h]
0x180072a02  mov     ecx, [rax]
0x180072a04  mov     [r14+858h], ecx
0x180072a0b  inc     r12d
0x180072a0e  inc     rbx
0x180072a11  cmp     r12d, edi
0x180072a14  jb      loc_180072879
0x180072a1a  mov     bl, [rbp+var_38]
0x180072a1d  mov     edi, [rbp+var_30]
0x180072a20  mov     sil, [rbp+var_37]
0x180072a24  mov     eax, cs:g_ReceivedSignalFromDefender
0x180072a2a  cmp     eax, 1
0x180072a2d  jnz     short loc_180072A51
0x180072a2f  mov     eax, cs:g_HandledSignalToSwitchNWToEnforcementMode
0x180072a35  test    eax, eax
0x180072a37  jnz     short loc_180072A51
0x180072a39  mov     bl, 1
0x180072a3b  lea     edi, [rax+1]
0x180072a3e  mov     sil, bl
0x180072a41  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180072a46  test    eax, eax
0x180072a48  jz      short loc_180072A51
0x180072a4a  mov     [rbp+var_34], 2
0x180072a51  mov     eax, cs:g_ReceivedSignalFromDefender
0x180072a57  test    eax, eax
0x180072a59  jnz     short loc_180072A7C
0x180072a5b  mov     eax, cs:g_HandledSignalToSwitchNWOff
0x180072a61  test    eax, eax
0x180072a63  jnz     short loc_180072A7C
0x180072a65  xor     edi, edi
0x180072a67  mov     bl, 1
0x180072a69  xor     sil, sil
0x180072a6c  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180072a71  test    eax, eax
0x180072a73  jz      short loc_180072A7C
0x180072a75  mov     [rbp+var_34], 5
0x180072a7c  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x180072a81  test    eax, eax
0x180072a83  jz      short loc_180072AB6
0x180072a85  xor     edx, edx
0x180072a87  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x180072a8e  call    SIPolicyIsPolicyActive
0x180072a93  test    al, al
0x180072a95  jz      short loc_180072AB6
0x180072a97  call    CiSmartAppControlClientSideEnable
0x180072a9c  test    al, al
0x180072a9e  jz      short loc_180072AB6
0x180072aa0  mov     bl, 1
0x180072aa2  mov     edi, 1
0x180072aa7  mov     sil, bl
0x180072aaa  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180072aaf  test    eax, eax
0x180072ab1  jz      short loc_180072ABE
0x180072ab3  mov     [rbp+var_34], edi
0x180072ab6  test    bl, bl
0x180072ab8  jz      loc_180072B6C
0x180072abe  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x180072ac3  test    eax, eax
0x180072ac5  jz      loc_180072B62
0x180072acb  lea     rax, [rbp+var_20]
0x180072acf  mov     r14d, 4
0x180072ad5  mov     [rsp+78h+var_48], rax
0x180072ada  lea     rbx, Path; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180072ae1  lea     rax, [rbp+var_2C]
0x180072ae5  mov     [rsp+78h+ValueLength], r14d
0x180072aea  xor     r9d, r9d
0x180072aed  mov     [rsp+78h+ValueData], rax
0x180072af2  lea     r8, aVerifiedandrep_2; "VerifiedAndReputablePolicyState"
0x180072af9  mov     rdx, rbx
0x180072afc  xor     ecx, ecx
0x180072afe  call    CipGetRegistryValue
0x180072b03  mov     [rbp+var_24], eax
0x180072b06  test    eax, eax
0x180072b08  js      short loc_180072B10
0x180072b0a  mov     ecx, [rbp+var_2C]
0x180072b0d  mov     [rbp+var_28], ecx
0x180072b10  lea     rax, [rbp+var_34]
0x180072b14  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x180072b19  mov     r9d, r14d; ValueType
0x180072b1c  mov     [rsp+78h+ValueData], rax; ValueData
0x180072b21  lea     r8, aSacEnforcement; "SAC_EnforcementReason"
0x180072b28  mov     rdx, rbx; Path
0x180072b2b  xor     ecx, ecx; RelativeTo
0x180072b2d  call    cs:__imp_RtlWriteRegistryValue
0x180072b34  nop     dword ptr [rax+rax+00h]
0x180072b39  lea     rax, [rbp+var_28]
0x180072b3d  mov     [rsp+78h+ValueLength], r14d; ValueLength
0x180072b42  mov     r9d, r14d; ValueType
0x180072b45  mov     [rsp+78h+ValueData], rax; ValueData
0x180072b4a  lea     r8, aSacPrevioussta; "SAC_PreviousState"
0x180072b51  mov     rdx, rbx; Path
0x180072b54  xor     ecx, ecx; RelativeTo
0x180072b56  call    cs:__imp_RtlWriteRegistryValue
0x180072b5d  nop     dword ptr [rax+rax+00h]
0x180072b62  mov     dl, sil
0x180072b65  mov     ecx, edi
0x180072b67  call    CiAsyncRefreshPoliciesOnNightsWatchModeChange
0x180072b6c  mov     eax, [rbp+var_24]
0x180072b6f  add     rsp, 78h
0x180072b73  pop     r15
0x180072b75  pop     r14
0x180072b77  pop     r13
0x180072b79  pop     r12
0x180072b7b  pop     rdi
0x180072b7c  pop     rsi
0x180072b7d  pop     rbx
0x180072b7e  pop     rbp
0x180072b7f  retn
```
