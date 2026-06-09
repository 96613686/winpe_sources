# CipValidateImageHash

- ea: `0x18009ed54`
- end: `0x18009f1ca`
- name: `CipValidateImageHash`
- size: `1142`
- prototype: `__int64 __fastcall(__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, unsigned int, int, __int64 *, _QWORD *), __int64, __int64, __int64, __int64, unsigned int, unsigned int, char, char, __int64 *, _QWORD *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009ed54`
- `0x18009fff8`
- `0x1800e5fd0`

## callees

- `0x18001004c`
- `0x18002c0d0`
- `0x18002c1b0`
- `0x18005a77c`
- `0x180064d70`
- `0x180076fcc`
- `0x18007718c`
- `0x180077264`
- `0x180098cbc`
- `0x1800991bc`
- `0x18009ed54`
- `0x18009f1d0`
- `0x18009f23c`
- `0x1800a0540`
- `0x1800ab5fc`
- `0x1800e72e4`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009ef3f`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009ef3f`

## pseudocode

```c
__int64 __fastcall CipValidateImageHash(
        __int64 (__fastcall *a1)(__int64, __int64, __int64, __int64, __int64, unsigned int, int, __int64 *, _QWORD *),
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7,
        char a8,
        char a9,
        __int64 *a10,
        _QWORD *a11)
{
  __int64 v11; // rbp
  int v13; // edx
  unsigned __int8 v14; // r15
  unsigned int v15; // esi
  char v16; // r12
  int v17; // ebx
  int v18; // r9d
  __int64 v19; // rbp
  char IsSignatureTrustedForIum; // al
  int v21; // r9d
  __int64 v22; // r9
  int v23; // eax
  int v24; // eax
  __int64 v26; // [rsp+20h] [rbp-D8h]
  int v27; // [rsp+30h] [rbp-C8h]
  char v28; // [rsp+60h] [rbp-98h]
  __int64 v30; // [rsp+80h] [rbp-78h]
  __int64 v32; // [rsp+90h] [rbp-68h]
  int v33; // [rsp+98h] [rbp-60h] BYREF
  __int16 v34; // [rsp+9Ch] [rbp-5Ch]
  char v35; // [rsp+9Eh] [rbp-5Ah]

  v11 = a3;
  v13 = a4;
  v14 = 0;
  v30 = a4;
  LOBYTE(a4) = a8;
  v32 = *a10;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v28 = 0;
  CipInitializeSigningLevelOrder((unsigned int)&v33, v13, a7, a4, a9);
  v15 = a7 | 0x8000000;
  if ( (g_CiPolicyState & 4) == 0 )
    v15 = a7;
  while ( 2 )
  {
    while ( 2 )
    {
      CiReinitializeValidationContext(a2, v15);
      v16 = *((_BYTE *)&v33 + v14 + 1);
      while ( 1 )
      {
        while ( 1 )
        {
          LOBYTE(v27) = v16;
          LODWORD(v26) = a6;
          v17 = a1(a2, v11, v30, a5, v26, v15, v27, a10, a11);
          if ( v17 < 0 )
            break;
          if ( *(__int64 (__fastcall ***)())(a2 + 3040) != &off_18002EEF0 || v32 )
            goto LABEL_25;
          if ( (g_CiOptions & 0x200000) == 0 )
          {
            if ( !*(_BYTE *)(a2 + 3320) )
              goto LABEL_25;
            v19 = *a11;
            if ( (unsigned __int8)CiIsSignatureTrustedForVsmEnclaves(*a11) )
            {
              v11 = a3;
            }
            else
            {
              IsSignatureTrustedForIum = CiIsSignatureTrustedForIum(v19);
              v11 = a3;
              if ( !IsSignatureTrustedForIum )
                goto LABEL_25;
            }
          }
          if ( *a10 )
          {
            CiReleaseContext();
            *a10 = 0;
          }
          *a11 = 0;
          v17 = CiHvciResetValidationContextForHvci(a2, v15, a5, a6);
          if ( v17 < 0 )
            goto LABEL_45;
          v28 = 1;
        }
        if ( !v28
          || !(unsigned __int8)PsIsCurrentThreadInServerSilo()
          || !(unsigned __int8)CiHvciIsVbsPolicyFailure(a2, 0) )
        {
          break;
        }
        CiHvciReleaseHvciOnlyResourcesInValidationContext();
        *(_QWORD *)(a2 + 3040) = &off_18002EEF0;
        CiReinitializeValidationContext(a2, v15);
        *(_BYTE *)(a2 + 3320) = 0;
      }
      if ( v17 == -1058471934 || v17 == -1073740760 || v17 == -1073741701 || (unsigned int)(v17 + 1058471929) <= 6 )
        goto LABEL_26;
LABEL_25:
      LOBYTE(v18) = v16;
      if ( !(unsigned __int8)CipAllowPolicyEngineToEvaluateObjectWithExpiredAndRevokedCert(v11, v30, v15, v18, v17) )
        goto LABEL_36;
LABEL_26:
      if ( (v15 & 0xE41FFF87) == 0
        && (*((_DWORD *)g_CipWhichLevelComparisons + (v16 & 0xF)) & 4) != 0
        && (char *)a1 == (char *)&CipValidateFileHash
        && *(_DWORD *)(a2 + 24) != 26
        && (!(unsigned int)Feature_TrustedLaunchHosts__private_IsEnabledDeviceUsageNoInline() || !*(_QWORD *)(a2 + 3616)) )
      {
        LOBYTE(v21) = v16;
        v17 = CipApplySIPolicyUMCI(a2, v17, v15, v21, v11, (__int64)a11);
        if ( v17 >= 0 )
          goto LABEL_58;
        if ( *(_DWORD *)(a2 + 24) == 26 || (*(_DWORD *)(a2 + 3056) & 0x100) != 0 )
          goto LABEL_37;
        *(_DWORD *)(a2 + 2368) &= ~2u;
        LOBYTE(v22) = v16;
        v17 = CipValidateFileObjectWithContext(a2, v11, v15, v22, a11);
      }
LABEL_36:
      if ( v17 >= 0 )
        goto LABEL_58;
LABEL_37:
      if ( v17 != -1058471934
        && v17 != -1073740285
        && v17 != -1073740760
        && v17 != -1073741701
        && (unsigned int)(v17 + 1058471929) > 6 )
      {
        goto LABEL_46;
      }
      if ( ++v14 < (unsigned __int8)v33 )
        continue;
      break;
    }
    if ( (v15 & 0x8000000) != 0 )
    {
      v14 = 0;
      v15 &= ~0x8000000u;
      continue;
    }
    break;
  }
LABEL_45:
  if ( v17 == -1073740760 )
    goto LABEL_52;
LABEL_46:
  if ( (unsigned int)(v17 + 1058471929) > 6
    && v17 != -1058471934
    && v17 != -1073740283
    && v17 != -1073740285
    && v17 != -1073741554
    && v17 != -1058340861 )
  {
    goto LABEL_58;
  }
LABEL_52:
  if ( (*(_DWORD *)(a2 + 2368) & 0xC0000) == 0x80000 )
  {
    v23 = *(_DWORD *)(a2 + 24);
    if ( v23 == 21 || !v23 )
    {
      *(_DWORD *)(a2 + 2368) = *(_DWORD *)(a2 + 2368) & 0xFFF3FFFF | 0x40000;
      v24 = CipValidateImageHash((_DWORD)a1, a2, v11, v30, a5, a6, v15 & 0xF7FFFFFF, a8, a9, (__int64)a10, (__int64)a11);
      if ( v24 >= 0 )
        v17 = v24;
      *(_DWORD *)(a2 + 2368) &= ~0x40000u;
    }
  }
LABEL_58:
  CipSetRevocationRuleAppliedIfRequired((unsigned int)v17, a2 + 24);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18009ed54  mov     r11, rsp
0x18009ed57  push    rbx
0x18009ed58  push    rbp
0x18009ed59  push    rsi
0x18009ed5a  push    rdi
0x18009ed5b  push    r12
0x18009ed5d  push    r13
0x18009ed5f  push    r14
0x18009ed61  push    r15
0x18009ed63  sub     rsp, 0B8h
0x18009ed6a  mov     rax, cs:__security_cookie
0x18009ed71  xor     rax, rsp
0x18009ed74  mov     [rsp+0F8h+var_58], rax
0x18009ed7c  mov     rax, [rsp+0F8h+arg_20]
0x18009ed84  mov     r10, r9
0x18009ed87  mov     ebx, [rsp+0F8h+arg_30]
0x18009ed8e  mov     rbp, r8
0x18009ed91  mov     r13, [rsp+0F8h+arg_50]
0x18009ed99  mov     rdi, rdx
0x18009ed9c  mov     [rsp+0F8h+var_80], rax
0x18009eda1  mov     rdx, r10
0x18009eda4  mov     rax, [rsp+0F8h+arg_48]
0x18009edac  xor     r15b, r15b
0x18009edaf  mov     [rsp+0F8h+var_88], rax
0x18009edb4  mov     [rsp+0F8h+var_70], rcx
0x18009edbc  xor     ecx, ecx
0x18009edbe  mov     [rsp+0F8h+var_78], r9
0x18009edc6  mov     rax, [rax]
0x18009edc9  mov     r9b, [rsp+0F8h+arg_38]
0x18009edd1  mov     [rsp+0F8h+var_68], rax
0x18009edd9  mov     al, [rsp+0F8h+arg_40]
0x18009ede0  mov     [rsp+0F8h+var_90], r8
0x18009ede5  mov     r8d, ebx
0x18009ede8  mov     [r11-60h], ecx
0x18009edec  mov     [r11-5Ch], cx
0x18009edf1  mov     [r11-5Ah], cl
0x18009edf5  mov     [rsp+0F8h+var_98], cl
0x18009edf9  lea     rcx, [r11-60h]
0x18009edfd  mov     byte ptr [rsp+0F8h+var_D8], al
0x18009ee01  call    CipInitializeSigningLevelOrder
0x18009ee06  mov     eax, cs:g_CiPolicyState
0x18009ee0c  mov     esi, ebx
0x18009ee0e  bts     esi, 1Bh
0x18009ee12  shr     eax, 2
0x18009ee15  test    al, 1
0x18009ee17  cmovz   esi, ebx
0x18009ee1a  mov     edx, esi
0x18009ee1c  mov     rcx, rdi
0x18009ee1f  call    CiReinitializeValidationContext
0x18009ee24  movzx   eax, r15b
0x18009ee28  movzx   r12d, [rsp+rax+0F8h+var_5F]
0x18009ee31  lea     r14, [rdi+0BE0h]
0x18009ee38  mov     rax, [rsp+0F8h+var_88]
0x18009ee3d  mov     rdx, rbp
0x18009ee40  mov     r9, [rsp+0F8h+var_80]
0x18009ee45  mov     rcx, rdi
0x18009ee48  mov     r8, [rsp+0F8h+var_78]
0x18009ee50  mov     [rsp+0F8h+var_B8], r13
0x18009ee55  mov     [rsp+0F8h+var_C0], rax
0x18009ee5a  mov     eax, [rsp+0F8h+arg_28]
0x18009ee61  mov     byte ptr [rsp+0F8h+var_C8], r12b
0x18009ee66  mov     dword ptr [rsp+0F8h+var_D0], esi
0x18009ee6a  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18009ee6e  mov     rax, [rsp+0F8h+var_70]
0x18009ee76  call    _guard_dispatch_icall
0x18009ee7b  mov     ebx, eax
0x18009ee7d  test    eax, eax
0x18009ee7f  js      loc_18009EF38
0x18009ee85  lea     rax, off_18002EEF0
0x18009ee8c  cmp     [rdi+0BE0h], rax
0x18009ee93  jnz     loc_18009EFA5
0x18009ee99  cmp     [rsp+0F8h+var_68], 0
0x18009eea2  jnz     loc_18009EFA5
0x18009eea8  test    cs:g_CiOptions, 200000h
0x18009eeb2  jnz     short loc_18009EEEC
0x18009eeb4  cmp     byte ptr [rdi+0CF8h], 0
0x18009eebb  jz      loc_18009EFA5
0x18009eec1  mov     rbp, [r13+0]
0x18009eec5  mov     rcx, rbp
0x18009eec8  call    CiIsSignatureTrustedForVsmEnclaves
0x18009eecd  test    al, al
0x18009eecf  jnz     short loc_18009EEE7
0x18009eed1  mov     rcx, rbp
0x18009eed4  call    CiIsSignatureTrustedForIum
0x18009eed9  mov     rbp, [rsp+0F8h+var_90]
0x18009eede  test    al, al
0x18009eee0  jnz     short loc_18009EEEC
0x18009eee2  jmp     loc_18009EFA5
0x18009eee7  mov     rbp, [rsp+0F8h+var_90]
0x18009eeec  mov     rbx, [rsp+0F8h+var_88]
0x18009eef1  mov     rcx, [rbx]
0x18009eef4  test    rcx, rcx
0x18009eef7  jz      short loc_18009EF05
0x18009eef9  call    CiReleaseContext
0x18009eefe  mov     qword ptr [rbx], 0
0x18009ef05  mov     r9d, [rsp+0F8h+arg_28]
0x18009ef0d  mov     edx, esi
0x18009ef0f  mov     r8, [rsp+0F8h+var_80]
0x18009ef14  mov     rcx, rdi
0x18009ef17  mov     qword ptr [r13+0], 0
0x18009ef1f  call    CiHvciResetValidationContextForHvci
0x18009ef24  mov     ebx, eax
0x18009ef26  test    eax, eax
0x18009ef28  js      loc_18009F0BD
0x18009ef2e  mov     [rsp+0F8h+var_98], 1
0x18009ef33  jmp     loc_18009EE31
0x18009ef38  cmp     [rsp+0F8h+var_98], 0
0x18009ef3d  jz      short loc_18009EF82
0x18009ef3f  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18009ef46  nop     dword ptr [rax+rax+00h]
0x18009ef4b  test    al, al
0x18009ef4d  jz      short loc_18009EF82
0x18009ef4f  xor     edx, edx
0x18009ef51  mov     rcx, rdi
0x18009ef54  call    CiHvciIsVbsPolicyFailure
0x18009ef59  test    al, al
0x18009ef5b  jz      short loc_18009EF82
0x18009ef5d  call    CiHvciReleaseHvciOnlyResourcesInValidationContext
0x18009ef62  lea     rax, off_18002EEF0
0x18009ef69  mov     edx, esi
0x18009ef6b  mov     rcx, rdi
0x18009ef6e  mov     [r14], rax
0x18009ef71  call    CiReinitializeValidationContext
0x18009ef76  mov     byte ptr [rdi+0CF8h], 0
0x18009ef7d  jmp     loc_18009EE38
0x18009ef82  cmp     ebx, 0C0E90002h
0x18009ef88  jz      short loc_18009EFC7
0x18009ef8a  cmp     ebx, 0C0000428h
0x18009ef90  jz      short loc_18009EFC7
0x18009ef92  cmp     ebx, 0C000007Bh
0x18009ef98  jz      short loc_18009EFC7
0x18009ef9a  lea     eax, [rbx+3F16FFF9h]
0x18009efa0  cmp     eax, 6
0x18009efa3  jbe     short loc_18009EFC7
0x18009efa5  mov     rdx, [rsp+0F8h+var_78]
0x18009efad  mov     r9b, r12b
0x18009efb0  mov     r8d, esi
0x18009efb3  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x18009efb7  mov     rcx, rbp
0x18009efba  call    CipAllowPolicyEngineToEvaluateObjectWithExpiredAndRevokedCert
0x18009efbf  test    al, al
0x18009efc1  jz      loc_18009F067
0x18009efc7  test    esi, 0E41FFF87h
0x18009efcd  jnz     loc_18009F067
0x18009efd3  mov     rax, cs:g_CipWhichLevelComparisons
0x18009efda  mov     rcx, r12
0x18009efdd  and     ecx, 0Fh
0x18009efe0  mov     ecx, [rax+rcx*4]
0x18009efe3  test    cl, 4
0x18009efe6  jz      short loc_18009F067
0x18009efe8  lea     rax, CipValidateFileHash
0x18009efef  cmp     [rsp+0F8h+var_70], rax
0x18009eff7  jnz     short loc_18009F067
0x18009eff9  cmp     dword ptr [rdi+18h], 1Ah
0x18009effd  jz      short loc_18009F067
0x18009efff  call    Feature_TrustedLaunchHosts__private_IsEnabledDeviceUsageNoInline
0x18009f004  test    eax, eax
0x18009f006  jz      short loc_18009F012
0x18009f008  cmp     qword ptr [rdi+0E20h], 0
0x18009f010  jnz     short loc_18009F067
0x18009f012  mov     [rsp+0F8h+var_D0], r13
0x18009f017  mov     r9b, r12b
0x18009f01a  mov     r8d, esi
0x18009f01d  mov     [rsp+0F8h+var_D8], rbp
0x18009f022  mov     edx, ebx
0x18009f024  mov     rcx, rdi
0x18009f027  call    CipApplySIPolicyUMCI
0x18009f02c  mov     ebx, eax
0x18009f02e  test    eax, eax
0x18009f030  jns     loc_18009F198
0x18009f036  cmp     dword ptr [rdi+18h], 1Ah
0x18009f03a  jz      short loc_18009F06F
0x18009f03c  test    dword ptr [rdi+0BF0h], 100h
0x18009f046  jnz     short loc_18009F06F
0x18009f048  and     dword ptr [rdi+940h], 0FFFFFFFDh
0x18009f04f  mov     r9b, r12b
0x18009f052  mov     r8d, esi
0x18009f055  mov     [rsp+0F8h+var_D8], r13
0x18009f05a  mov     rdx, rbp
0x18009f05d  mov     rcx, rdi
0x18009f060  call    CipValidateFileObjectWithContext
0x18009f065  mov     ebx, eax
0x18009f067  test    ebx, ebx
0x18009f069  jns     loc_18009F198
0x18009f06f  cmp     ebx, 0C0E90002h
0x18009f075  jz      short loc_18009F09A
0x18009f077  cmp     ebx, 0C0000603h
0x18009f07d  jz      short loc_18009F09A
0x18009f07f  cmp     ebx, 0C0000428h
0x18009f085  jz      short loc_18009F09A
0x18009f087  cmp     ebx, 0C000007Bh
0x18009f08d  jz      short loc_18009F09A
0x18009f08f  lea     eax, [rbx+3F16FFF9h]
0x18009f095  cmp     eax, 6
0x18009f098  ja      short loc_18009F0C5
0x18009f09a  inc     r15b
0x18009f09d  cmp     r15b, [rsp+0F8h+var_60]
0x18009f0a5  jb      loc_18009EE1A
0x18009f0ab  bt      esi, 1Bh
0x18009f0af  jnb     short loc_18009F0BD
0x18009f0b1  xor     r15b, r15b
0x18009f0b4  btr     esi, 1Bh
0x18009f0b8  jmp     loc_18009EE1A
0x18009f0bd  cmp     ebx, 0C0000428h
0x18009f0c3  jz      short loc_18009F0FC
0x18009f0c5  lea     eax, [rbx+3F16FFF9h]
0x18009f0cb  cmp     eax, 6
0x18009f0ce  jbe     short loc_18009F0FC
0x18009f0d0  cmp     ebx, 0C0E90002h
0x18009f0d6  jz      short loc_18009F0FC
0x18009f0d8  cmp     ebx, 0C0000605h
0x18009f0de  jz      short loc_18009F0FC
0x18009f0e0  cmp     ebx, 0C0000603h
0x18009f0e6  jz      short loc_18009F0FC
0x18009f0e8  cmp     ebx, 0C000010Eh
0x18009f0ee  jz      short loc_18009F0FC
0x18009f0f0  cmp     ebx, 0C0EB0003h
0x18009f0f6  jnz     loc_18009F198
0x18009f0fc  mov     edx, [rdi+940h]
0x18009f102  mov     eax, edx
0x18009f104  and     eax, 0C0000h
0x18009f109  cmp     eax, 80000h
0x18009f10e  jnz     loc_18009F198
0x18009f114  mov     eax, [rdi+18h]
0x18009f117  cmp     eax, 15h
0x18009f11a  jz      short loc_18009F120
0x18009f11c  test    eax, eax
0x18009f11e  jnz     short loc_18009F198
0x18009f120  mov     rax, [rsp+0F8h+var_88]
0x18009f125  btr     edx, 13h
0x18009f129  mov     r9, [rsp+0F8h+var_78]
0x18009f131  bts     edx, 12h
0x18009f135  mov     rcx, [rsp+0F8h+var_70]
0x18009f13d  btr     esi, 1Bh
0x18009f141  mov     [rsp+0F8h+var_A8], r13
0x18009f146  mov     r8, rbp
0x18009f149  mov     [rsp+0F8h+var_B0], rax
0x18009f14e  mov     al, [rsp+0F8h+arg_40]
0x18009f155  mov     byte ptr [rsp+0F8h+var_B8], al
0x18009f159  mov     al, [rsp+0F8h+arg_38]
0x18009f160  mov     byte ptr [rsp+0F8h+var_C0], al
0x18009f164  mov     eax, [rsp+0F8h+arg_28]
0x18009f16b  mov     [rsp+0F8h+var_C8], esi
0x18009f16f  mov     dword ptr [rsp+0F8h+var_D0], eax
0x18009f173  mov     rax, [rsp+0F8h+var_80]
0x18009f178  mov     [rdi+940h], edx
0x18009f17e  mov     rdx, rdi
0x18009f181  mov     [rsp+0F8h+var_D8], rax
0x18009f186  call    CipValidateImageHash
0x18009f18b  test    eax, eax
0x18009f18d  cmovns  ebx, eax
0x18009f190  btr     dword ptr [rdi+940h], 12h
0x18009f198  lea     rdx, [rdi+18h]
0x18009f19c  mov     ecx, ebx
0x18009f19e  call    CipSetRevocationRuleAppliedIfRequired
0x18009f1a3  mov     eax, ebx
0x18009f1a5  mov     rcx, [rsp+0F8h+var_58]
0x18009f1ad  xor     rcx, rsp; StackCookie
0x18009f1b0  call    __security_check_cookie
0x18009f1b5  add     rsp, 0B8h
0x18009f1bc  pop     r15
0x18009f1be  pop     r14
0x18009f1c0  pop     r13
0x18009f1c2  pop     r12
0x18009f1c4  pop     rdi
0x18009f1c5  pop     rsi
0x18009f1c6  pop     rbp
0x18009f1c7  pop     rbx
0x18009f1c8  retn
```
