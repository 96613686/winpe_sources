# SPCryptGetProviderProperty

- ea: `0x180003ea0`
- end: `0x18000434a`
- name: `SPCryptGetProviderProperty`
- size: `1194`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ea0`
- `0x180004350`
- `0x18000af80`
- `0x18000b250`
- `0x1800398b0`
- `0x18004bc40`
- `0x18004be4c`
- `0x1800505b4`
- `0x1800622e0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180003f26`
- `ntdll!RtlReleaseResource` at `0x180003f26`
- `ntdll!RtlAcquireResourceShared` at `0x180003ed4`
- `ntdll!RtlAcquireResourceShared` at `0x180003ed4`

## string_xrefs

- `0x180003fcc`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180004047`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800040b2`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x1800040f5`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000419f`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000421c`: `Security Descr Support`

## pseudocode

```c
__int64 __fastcall SPCryptGetProviderProperty(
        __int64 a1,
        const wchar_t *a2,
        _DWORD *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6)
{
  __int64 v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // rbp
  int v13; // edx
  int v14; // r8d
  __int64 v15; // rdi
  unsigned __int64 v16; // rax
  unsigned int v17; // edi
  int v19; // edx
  int v20; // r8d
  int v21; // ebx
  unsigned int v22; // eax
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int VsmIdkSPub; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ebx
  int v33; // ebx
  const void *v34; // rdx
  __int64 v35[11]; // [rsp+40h] [rbp-58h] BYREF

  v9 = KspValidateProvHandle();
  v12 = v9;
  if ( v9 )
  {
    RtlAcquireResourceShared((PRTL_RESOURCE)(v9 + 64), 1u);
    if ( a2 )
    {
      v15 = -1;
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      if ( v16 > 0x40 )
      {
        v17 = -2146893785;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13,
            v14,
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
            131);
        goto LABEL_8;
      }
      if ( a5 )
      {
        if ( (a6 & 0xFFFFFFBF) != 0 )
        {
          v17 = -2146893815;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v13,
              v14,
              (unsigned int)"Status",
              9,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
              145);
          goto LABEL_8;
        }
        if ( !wcscmp_0(a2, L"Impl Type") )
        {
          v21 = 4;
          v22 = 4;
          goto LABEL_14;
        }
        if ( !wcscmp_0(a2, L"Max Name Length") )
        {
          v21 = 14;
LABEL_24:
          v22 = 4;
          goto LABEL_14;
        }
        if ( !wcscmp_0(a2, L"Name") )
        {
          v21 = 9;
          do
            ++v15;
          while ( *(_WORD *)(*(_QWORD *)(v12 + 16) + 2 * v15) );
          v22 = 2 * v15 + 2;
LABEL_14:
          *a5 = v22;
          if ( a3 )
          {
            if ( a4 < v22 )
            {
              v17 = -2146893784;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v19,
                  v20,
                  (unsigned int)"Status",
                  40,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
                  3);
              goto LABEL_8;
            }
            v23 = v21 - 4;
            if ( !v23 )
            {
              *a3 = 2;
              if ( !wcscmp_0(*(const wchar_t **)(v12 + 16), L"Microsoft Software Key Storage Provider") )
                *a3 = 34;
              goto LABEL_19;
            }
            v24 = v23 - 5;
            if ( v24 )
            {
              v25 = v24 - 4;
              if ( !v25 )
              {
                *a3 = 0x10000;
                goto LABEL_19;
              }
              v26 = v25 - 1;
              if ( !v26 )
              {
                *a3 = 260;
                goto LABEL_19;
              }
              v32 = v26 - 6;
              if ( !v32 )
              {
                *a3 = 1;
                goto LABEL_19;
              }
              v33 = v32 - 1;
              if ( v33 )
              {
                if ( v33 != 7 )
                  goto LABEL_19;
                v34 = *(const void **)(v12 + 40);
              }
              else
              {
                v34 = *(const void **)(v12 + 32);
              }
            }
            else
            {
              v34 = *(const void **)(v12 + 16);
            }
            memcpy_0(a3, v34, v22);
          }
LABEL_19:
          v17 = 0;
LABEL_8:
          RtlReleaseResource((PRTL_RESOURCE)(v12 + 64));
          return v17;
        }
        if ( !wcscmp_0(a2, L"Version") )
        {
          v21 = 13;
          goto LABEL_24;
        }
        if ( !wcscmp_0(a2, L"Security Descr Support") )
        {
          v21 = 20;
          goto LABEL_24;
        }
        if ( !wcscmp_0(a2, L"Use Context") )
        {
          v30 = *(_QWORD *)(v12 + 32);
          if ( v30 )
          {
            do
              ++v15;
            while ( *(_WORD *)(v30 + 2 * v15) );
            v22 = 2 * v15 + 2;
            if ( 2 * (_DWORD)v15 != -2 )
            {
              v21 = 21;
              goto LABEL_14;
            }
          }
          v28 = 705;
LABEL_61:
          v17 = -2146893807;
          v29 = 2148073489LL;
          goto LABEL_42;
        }
        if ( !wcscmp_0(a2, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION") )
        {
          v31 = *(_QWORD *)(v12 + 40);
          if ( v31 )
          {
            do
              ++v15;
            while ( *(_WORD *)(v31 + 2 * v15) );
            v22 = 2 * v15 + 2;
            if ( 2 * (_DWORD)v15 != -2 )
            {
              v21 = 28;
              goto LABEL_14;
            }
          }
          v28 = 722;
          goto LABEL_61;
        }
        if ( !wcscmp_0(a2, L"VBS_ROOT_PUB") )
        {
          v35[0] = (unsigned int)Feature_Key_Guard_Attestation__private_featureState;
          if ( (Feature_Key_Guard_Attestation__private_featureState & 0x10) == 0 )
          {
            LODWORD(v35[0]) = Feature_Key_Guard_Attestation__private_featureState | 1;
            wil_details_FeatureReporting_ReportUsageToService(
              Feature_Key_Guard_Attestation__private_descriptor,
              v35[0],
              3);
            wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
              v35[0],
              3,
              Feature_Key_Guard_Attestation__private_descriptor);
          }
          LODWORD(v35[0]) = 0;
          v21 = 31;
          VsmIdkSPub = GetVsmIdkSPub(a4, v35, a3);
          v17 = VsmIdkSPub;
          if ( VsmIdkSPub >= 0 )
          {
            v22 = v35[0];
            goto LABEL_14;
          }
          v28 = 738;
          v29 = (unsigned int)VsmIdkSPub;
        }
        else
        {
          v17 = -2146893783;
          v28 = 752;
          v29 = 2148073513LL;
        }
LABEL_42:
        DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v28);
        goto LABEL_8;
      }
      v28 = 650;
    }
    else
    {
      v28 = 637;
    }
    v17 = -2146893785;
    v29 = 2148073511LL;
    goto LABEL_42;
  }
  v17 = -2146893786;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      118);
  return v17;
}

```

## disassembly

```asm
0x180003ea0  push    rbx
0x180003ea2  push    rbp
0x180003ea3  push    rsi
0x180003ea4  push    rdi
0x180003ea5  push    r12
0x180003ea7  push    r13
0x180003ea9  push    r14
0x180003eab  push    r15
0x180003ead  sub     rsp, 58h
0x180003eb1  mov     r12d, r9d
0x180003eb4  mov     r14, r8
0x180003eb7  mov     rbx, rdx
0x180003eba  call    KspValidateProvHandle
0x180003ebf  xor     r13d, r13d
0x180003ec2  mov     rbp, rax
0x180003ec5  test    rax, rax
0x180003ec8  jz      loc_1800040CB
0x180003ece  mov     dl, 1; Wait
0x180003ed0  lea     rcx, [rax+40h]; Resource
0x180003ed4  call    cs:__imp_RtlAcquireResourceShared
0x180003edb  nop     dword ptr [rax+rax+00h]
0x180003ee0  test    rbx, rbx
0x180003ee3  jz      loc_1800041B7
0x180003ee9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180003eed  mov     rax, rdi
0x180003ef0  inc     rax
0x180003ef3  cmp     [rbx+rax*2], r13w
0x180003ef8  jnz     short loc_180003EF0
0x180003efa  cmp     rax, 40h ; '@'
0x180003efe  jbe     short loc_180003F46
0x180003f00  mov     edi, 80090027h
0x180003f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f0c  lea     rax, WPP_GLOBAL_Control
0x180003f13  cmp     rcx, rax
0x180003f16  jz      short loc_180003F22
0x180003f18  test    byte ptr [rcx+1Ch], 1
0x180003f1c  jnz     loc_180003FC4
0x180003f22  lea     rcx, [rbp+40h]; Resource
0x180003f26  call    cs:__imp_RtlReleaseResource
0x180003f2d  nop     dword ptr [rax+rax+00h]
0x180003f32  mov     eax, edi
0x180003f34  add     rsp, 58h
0x180003f38  pop     r15
0x180003f3a  pop     r14
0x180003f3c  pop     r13
0x180003f3e  pop     r12
0x180003f40  pop     rdi
0x180003f41  pop     rsi
0x180003f42  pop     rbp
0x180003f43  pop     rbx
0x180003f44  retn
0x180003f46  mov     r15, [rsp+98h+arg_20]
0x180003f4e  test    r15, r15
0x180003f51  jz      loc_1800041BF
0x180003f57  test    [rsp+98h+arg_28], 0FFFFFFBFh
0x180003f62  jnz     loc_180004084
0x180003f68  lea     rdx, aImplType; "Impl Type"
0x180003f6f  mov     rcx, rbx; String1
0x180003f72  call    wcscmp_0
0x180003f77  test    eax, eax
0x180003f79  jnz     short loc_180003FF5
0x180003f7b  lea     ebx, [rax+4]
0x180003f7e  mov     eax, ebx
0x180003f80  mov     [r15], eax
0x180003f83  test    r14, r14
0x180003f86  jz      short loc_180003FBC
0x180003f88  cmp     r12d, eax
0x180003f8b  jb      loc_180004019
0x180003f91  sub     ebx, 4
0x180003f94  jnz     loc_18000405D
0x180003f9a  mov     dword ptr [r14], 2
0x180003fa1  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x180003fa8  mov     rcx, [rbp+10h]; String1
0x180003fac  call    wcscmp_0
0x180003fb1  test    eax, eax
0x180003fb3  jnz     short loc_180003FBC
0x180003fb5  mov     dword ptr [r14], 22h ; '"'
0x180003fbc  mov     edi, r13d
0x180003fbf  jmp     loc_180003F22
0x180003fc4  mov     [rsp+98h+var_68], 283h
0x180003fcc  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003fd3  mov     [rsp+98h+var_70], rax
0x180003fd8  mov     [rsp+98h+var_78], 80090027h
0x180003fe0  mov     rcx, [rcx+10h]
0x180003fe4  lea     r9, aStatus; "Status"
0x180003feb  call    WPP_SF_sDsd
0x180003ff0  jmp     loc_180003F22
0x180003ff5  lea     rdx, aMaxNameLength; "Max Name Length"
0x180003ffc  mov     rcx, rbx; String1
0x180003fff  call    wcscmp_0
0x180004004  test    eax, eax
0x180004006  jnz     loc_1800041D1
0x18000400c  lea     ebx, [rax+0Eh]
0x18000400f  mov     eax, 4
0x180004014  jmp     loc_180003F80
0x180004019  mov     edi, 80090028h
0x18000401e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004025  lea     rax, WPP_GLOBAL_Control
0x18000402c  cmp     rcx, rax
0x18000402f  jz      loc_180003F22
0x180004035  test    byte ptr [rcx+1Ch], 1
0x180004039  jz      loc_180003F22
0x18000403f  mov     [rsp+98h+var_68], 303h
0x180004047  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000404e  mov     [rsp+98h+var_70], rax
0x180004053  mov     [rsp+98h+var_78], 80090028h
0x18000405b  jmp     short loc_180003FE0
0x18000405d  sub     ebx, 5
0x180004060  jz      loc_180004318
0x180004066  sub     ebx, 4
0x180004069  jz      loc_18000433E
0x18000406f  sub     ebx, 1
0x180004072  jnz     loc_1800042FF
0x180004078  mov     dword ptr [r14], 104h
0x18000407f  jmp     loc_180003FBC
0x180004084  mov     edi, 80090009h
0x180004089  mov     rcx, cs:WPP_GLOBAL_Control
0x180004090  lea     rax, WPP_GLOBAL_Control
0x180004097  cmp     rcx, rax
0x18000409a  jz      loc_180003F22
0x1800040a0  test    byte ptr [rcx+1Ch], 1
0x1800040a4  jz      loc_180003F22
0x1800040aa  mov     [rsp+98h+var_68], 291h
0x1800040b2  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800040b9  mov     [rsp+98h+var_70], rax
0x1800040be  mov     [rsp+98h+var_78], 80090009h
0x1800040c6  jmp     loc_180003FE0
0x1800040cb  mov     edi, 80090026h
0x1800040d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040d7  lea     rax, WPP_GLOBAL_Control
0x1800040de  cmp     rcx, rax
0x1800040e1  jz      loc_180003F32
0x1800040e7  test    byte ptr [rcx+1Ch], 1
0x1800040eb  jz      loc_180003F32
0x1800040f1  mov     rcx, [rcx+10h]
0x1800040f5  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800040fc  mov     [rsp+98h+var_68], 276h
0x180004104  lea     r9, aStatus; "Status"
0x18000410b  mov     [rsp+98h+var_70], rax
0x180004110  mov     [rsp+98h+var_78], 80090026h
0x180004118  call    WPP_SF_sDsd
0x18000411d  jmp     loc_180003F32
0x180004122  mov     ecx, cs:Feature_Key_Guard_Attestation__private_featureState
0x180004128  mov     [rsp+98h+var_58], r13
0x18000412d  mov     dword ptr [rsp+98h+var_58], ecx
0x180004131  test    cl, 10h
0x180004134  jnz     short loc_180004173
0x180004136  mov     rax, [rsp+98h+var_58]
0x18000413b  or      ecx, 1
0x18000413e  mov     [rsp+98h+var_58], rax
0x180004143  mov     ebx, 3
0x180004148  mov     dword ptr [rsp+98h+var_58], ecx
0x18000414c  mov     r8d, ebx
0x18000414f  mov     rdx, [rsp+98h+var_58]
0x180004154  lea     rcx, Feature_Key_Guard_Attestation__private_descriptor
0x18000415b  call    wil_details_FeatureReporting_ReportUsageToService
0x180004160  mov     rcx, [rsp+98h+var_58]
0x180004165  lea     r8, Feature_Key_Guard_Attestation__private_descriptor
0x18000416c  mov     edx, ebx
0x18000416e  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x180004173  mov     r8, r14
0x180004176  mov     dword ptr [rsp+98h+var_58], r13d
0x18000417b  lea     rdx, [rsp+98h+var_58]
0x180004180  mov     ecx, r12d
0x180004183  mov     ebx, 1Fh
0x180004188  call    GetVsmIdkSPub
0x18000418d  mov     edi, eax
0x18000418f  test    eax, eax
0x180004191  jns     loc_1800042F6
0x180004197  mov     r9d, 2E2h
0x18000419d  mov     ecx, eax
0x18000419f  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800041a6  lea     rdx, aStatus; "Status"
0x1800041ad  call    DebugTraceError
0x1800041b2  jmp     loc_180003F22
0x1800041b7  mov     r9d, 27Dh
0x1800041bd  jmp     short loc_1800041C5
0x1800041bf  mov     r9d, 28Ah
0x1800041c5  mov     edi, 80090027h
0x1800041ca  mov     ecx, 80090027h
0x1800041cf  jmp     short loc_18000419F
0x1800041d1  lea     rdx, aName; "Name"
0x1800041d8  mov     rcx, rbx; String1
0x1800041db  call    wcscmp_0
0x1800041e0  test    eax, eax
0x1800041e2  jnz     short loc_180004201
0x1800041e4  lea     ebx, [rax+9]
0x1800041e7  mov     rax, [rbp+10h]
0x1800041eb  inc     rdi
0x1800041ee  cmp     [rax+rdi*2], r13w
0x1800041f3  jnz     short loc_1800041EB
0x1800041f5  lea     eax, ds:2[rdi*2]
0x1800041fc  jmp     loc_180003F80
0x180004201  lea     rdx, aVersion; "Version"
0x180004208  mov     rcx, rbx; String1
0x18000420b  call    wcscmp_0
0x180004210  test    eax, eax
0x180004212  jnz     short loc_18000421C
0x180004214  lea     ebx, [rax+0Dh]
0x180004217  jmp     loc_18000400F
0x18000421c  lea     rdx, aSecurityDescrS; "Security Descr Support"
0x180004223  mov     rcx, rbx; String1
0x180004226  call    wcscmp_0
0x18000422b  test    eax, eax
0x18000422d  jnz     short loc_180004237
0x18000422f  lea     ebx, [rax+14h]
0x180004232  jmp     loc_18000400F
0x180004237  lea     rdx, aUseContext; "Use Context"
0x18000423e  mov     rcx, rbx; String1
0x180004241  call    wcscmp_0
0x180004246  test    eax, eax
0x180004248  jnz     short loc_18000428F
0x18000424a  mov     rax, [rbp+20h]
0x18000424e  test    rax, rax
0x180004251  jz      short loc_180004272
0x180004253  inc     rdi
0x180004256  cmp     [rax+rdi*2], r13w
0x18000425b  jnz     short loc_180004253
0x18000425d  lea     eax, ds:2[rdi*2]
0x180004264  test    eax, eax
0x180004266  jz      short loc_180004272
0x180004268  mov     ebx, 15h
0x18000426d  jmp     loc_180003F80
0x180004272  mov     r9d, 2C1h
0x180004278  jmp     short loc_180004280
0x18000427a  mov     r9d, 2D2h
0x180004280  mov     edi, 80090011h
0x180004285  mov     ecx, 80090011h
0x18000428a  jmp     loc_18000419F
0x18000428f  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180004296  mov     rcx, rbx; String1
0x180004299  call    wcscmp_0
0x18000429e  test    eax, eax
0x1800042a0  jnz     short loc_1800042CA
0x1800042a2  mov     rax, [rbp+28h]
0x1800042a6  test    rax, rax
0x1800042a9  jz      short loc_18000427A
0x1800042ab  inc     rdi
0x1800042ae  cmp     [rax+rdi*2], r13w
0x1800042b3  jnz     short loc_1800042AB
0x1800042b5  lea     eax, ds:2[rdi*2]
0x1800042bc  test    eax, eax
0x1800042be  jz      short loc_18000427A
0x1800042c0  mov     ebx, 1Ch
0x1800042c5  jmp     loc_180003F80
0x1800042ca  lea     rdx, aVbsRootPub; "VBS_ROOT_PUB"
0x1800042d1  mov     rcx, rbx; String1
0x1800042d4  call    wcscmp_0
0x1800042d9  test    eax, eax
0x1800042db  jz      loc_180004122
0x1800042e1  mov     edi, 80090029h
0x1800042e6  mov     r9d, 2F0h
0x1800042ec  mov     ecx, 80090029h
0x1800042f1  jmp     loc_18000419F
0x1800042f6  mov     eax, dword ptr [rsp+98h+var_58]
0x1800042fa  jmp     loc_180003F80
0x1800042ff  sub     ebx, 6
0x180004302  jz      short loc_180004332
0x180004304  sub     ebx, 1
0x180004307  jz      short loc_18000432C
0x180004309  cmp     ebx, 7
0x18000430c  jnz     loc_180003FBC
0x180004312  mov     rdx, [rbp+28h]
0x180004316  jmp     short loc_18000431C
0x180004318  mov     rdx, [rbp+10h]; Src
0x18000431c  mov     r8d, eax; Size
0x18000431f  mov     rcx, r14; void *
0x180004322  call    memcpy_0
0x180004327  jmp     loc_180003FBC
0x18000432c  mov     rdx, [rbp+20h]
0x180004330  jmp     short loc_18000431C
0x180004332  mov     dword ptr [r14], 1
0x180004339  jmp     loc_180003FBC
0x18000433e  mov     dword ptr [r14], 10000h
0x180004345  jmp     loc_180003FBC
```
