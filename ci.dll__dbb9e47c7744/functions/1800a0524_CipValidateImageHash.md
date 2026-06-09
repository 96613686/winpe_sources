# CipValidateImageHash

- ea: `0x1800a0524`
- end: `0x1800a099a`
- name: `CipValidateImageHash`
- size: `1142`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009acb8`
- `0x1800a0524`
- `0x1800e5a50`

## callees

- `0x18001003c`
- `0x18002bf20`
- `0x18002c000`
- `0x18005a854`
- `0x180064c00`
- `0x180076cec`
- `0x180076eac`
- `0x180076f84`
- `0x18009335c`
- `0x18009385c`
- `0x18009b200`
- `0x1800a0524`
- `0x1800a1718`
- `0x1800a1784`
- `0x1800ac2ac`
- `0x1800e6d64`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a070f`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x1800a070f`

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
          if ( *(__int64 (__fastcall ***)())(a2 + 3032) != &off_18002EE80 || v32 )
            goto LABEL_25;
          if ( (g_CiOptions & 0x200000) == 0 )
          {
            if ( !*(_BYTE *)(a2 + 3304) )
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
        *(_QWORD *)(a2 + 3032) = &off_18002EE80;
        CiReinitializeValidationContext(a2, v15);
        *(_BYTE *)(a2 + 3304) = 0;
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
        && (!(unsigned int)Feature_TrustedLaunchHosts__private_IsEnabledDeviceUsageNoInline() || !*(_QWORD *)(a2 + 3600)) )
      {
        LOBYTE(v21) = v16;
        v17 = CipApplySIPolicyUMCI(a2, v17, v15, v21, v11, (__int64)a11);
        if ( v17 >= 0 )
          goto LABEL_58;
        if ( *(_DWORD *)(a2 + 24) == 26 || (*(_DWORD *)(a2 + 3048) & 0x100) != 0 )
          goto LABEL_37;
        *(_DWORD *)(a2 + 2360) &= ~2u;
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
  if ( (*(_DWORD *)(a2 + 2360) & 0xC0000) == 0x80000 )
  {
    v23 = *(_DWORD *)(a2 + 24);
    if ( v23 == 21 || !v23 )
    {
      *(_DWORD *)(a2 + 2360) = *(_DWORD *)(a2 + 2360) & 0xFFF3FFFF | 0x40000;
      v24 = CipValidateImageHash((_DWORD)a1, a2, v11, v30, a5, a6, v15 & 0xF7FFFFFF, a8, a9, (__int64)a10, (__int64)a11);
      if ( v24 >= 0 )
        v17 = v24;
      *(_DWORD *)(a2 + 2360) &= ~0x40000u;
    }
  }
LABEL_58:
  CipSetRevocationRuleAppliedIfRequired((unsigned int)v17, a2 + 24);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800a0524  mov     r11, rsp
0x1800a0527  push    rbx
0x1800a0528  push    rbp
0x1800a0529  push    rsi
0x1800a052a  push    rdi
0x1800a052b  push    r12
0x1800a052d  push    r13
0x1800a052f  push    r14
0x1800a0531  push    r15
0x1800a0533  sub     rsp, 0B8h
0x1800a053a  mov     rax, cs:__security_cookie
0x1800a0541  xor     rax, rsp
0x1800a0544  mov     [rsp+0F8h+var_58], rax
0x1800a054c  mov     rax, [rsp+0F8h+arg_20]
0x1800a0554  mov     r10, r9
0x1800a0557  mov     ebx, [rsp+0F8h+arg_30]
0x1800a055e  mov     rbp, r8
0x1800a0561  mov     r13, [rsp+0F8h+arg_50]
0x1800a0569  mov     rdi, rdx
0x1800a056c  mov     [rsp+0F8h+var_80], rax
0x1800a0571  mov     rdx, r10
0x1800a0574  mov     rax, [rsp+0F8h+arg_48]
0x1800a057c  xor     r15b, r15b
0x1800a057f  mov     [rsp+0F8h+var_88], rax
0x1800a0584  mov     [rsp+0F8h+var_70], rcx
0x1800a058c  xor     ecx, ecx
0x1800a058e  mov     [rsp+0F8h+var_78], r9
0x1800a0596  mov     rax, [rax]
0x1800a0599  mov     r9b, [rsp+0F8h+arg_38]
0x1800a05a1  mov     [rsp+0F8h+var_68], rax
0x1800a05a9  mov     al, [rsp+0F8h+arg_40]
0x1800a05b0  mov     [rsp+0F8h+var_90], r8
0x1800a05b5  mov     r8d, ebx
0x1800a05b8  mov     [r11-60h], ecx
0x1800a05bc  mov     [r11-5Ch], cx
0x1800a05c1  mov     [r11-5Ah], cl
0x1800a05c5  mov     [rsp+0F8h+var_98], cl
0x1800a05c9  lea     rcx, [r11-60h]
0x1800a05cd  mov     byte ptr [rsp+0F8h+var_D8], al
0x1800a05d1  call    CipInitializeSigningLevelOrder
0x1800a05d6  mov     eax, cs:g_CiPolicyState
0x1800a05dc  mov     esi, ebx
0x1800a05de  bts     esi, 1Bh
0x1800a05e2  shr     eax, 2
0x1800a05e5  test    al, 1
0x1800a05e7  cmovz   esi, ebx
0x1800a05ea  mov     edx, esi
0x1800a05ec  mov     rcx, rdi
0x1800a05ef  call    CiReinitializeValidationContext
0x1800a05f4  movzx   eax, r15b
0x1800a05f8  movzx   r12d, [rsp+rax+0F8h+var_5F]
0x1800a0601  lea     r14, [rdi+0BD8h]
0x1800a0608  mov     rax, [rsp+0F8h+var_88]
0x1800a060d  mov     rdx, rbp
0x1800a0610  mov     r9, [rsp+0F8h+var_80]
0x1800a0615  mov     rcx, rdi
0x1800a0618  mov     r8, [rsp+0F8h+var_78]
0x1800a0620  mov     [rsp+0F8h+var_B8], r13
0x1800a0625  mov     [rsp+0F8h+var_C0], rax
0x1800a062a  mov     eax, [rsp+0F8h+arg_28]
0x1800a0631  mov     byte ptr [rsp+0F8h+var_C8], r12b
0x1800a0636  mov     dword ptr [rsp+0F8h+var_D0], esi
0x1800a063a  mov     dword ptr [rsp+0F8h+var_D8], eax
0x1800a063e  mov     rax, [rsp+0F8h+var_70]
0x1800a0646  call    _guard_dispatch_icall
0x1800a064b  mov     ebx, eax
0x1800a064d  test    eax, eax
0x1800a064f  js      loc_1800A0708
0x1800a0655  lea     rax, off_18002EE80
0x1800a065c  cmp     [rdi+0BD8h], rax
0x1800a0663  jnz     loc_1800A0775
0x1800a0669  cmp     [rsp+0F8h+var_68], 0
0x1800a0672  jnz     loc_1800A0775
0x1800a0678  test    cs:g_CiOptions, 200000h
0x1800a0682  jnz     short loc_1800A06BC
0x1800a0684  cmp     byte ptr [rdi+0CE8h], 0
0x1800a068b  jz      loc_1800A0775
0x1800a0691  mov     rbp, [r13+0]
0x1800a0695  mov     rcx, rbp
0x1800a0698  call    CiIsSignatureTrustedForVsmEnclaves
0x1800a069d  test    al, al
0x1800a069f  jnz     short loc_1800A06B7
0x1800a06a1  mov     rcx, rbp
0x1800a06a4  call    CiIsSignatureTrustedForIum
0x1800a06a9  mov     rbp, [rsp+0F8h+var_90]
0x1800a06ae  test    al, al
0x1800a06b0  jnz     short loc_1800A06BC
0x1800a06b2  jmp     loc_1800A0775
0x1800a06b7  mov     rbp, [rsp+0F8h+var_90]
0x1800a06bc  mov     rbx, [rsp+0F8h+var_88]
0x1800a06c1  mov     rcx, [rbx]
0x1800a06c4  test    rcx, rcx
0x1800a06c7  jz      short loc_1800A06D5
0x1800a06c9  call    CiReleaseContext
0x1800a06ce  mov     qword ptr [rbx], 0
0x1800a06d5  mov     r9d, [rsp+0F8h+arg_28]
0x1800a06dd  mov     edx, esi
0x1800a06df  mov     r8, [rsp+0F8h+var_80]
0x1800a06e4  mov     rcx, rdi
0x1800a06e7  mov     qword ptr [r13+0], 0
0x1800a06ef  call    CiHvciResetValidationContextForHvci
0x1800a06f4  mov     ebx, eax
0x1800a06f6  test    eax, eax
0x1800a06f8  js      loc_1800A088D
0x1800a06fe  mov     [rsp+0F8h+var_98], 1
0x1800a0703  jmp     loc_1800A0601
0x1800a0708  cmp     [rsp+0F8h+var_98], 0
0x1800a070d  jz      short loc_1800A0752
0x1800a070f  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x1800a0716  nop     dword ptr [rax+rax+00h]
0x1800a071b  test    al, al
0x1800a071d  jz      short loc_1800A0752
0x1800a071f  xor     edx, edx
0x1800a0721  mov     rcx, rdi
0x1800a0724  call    CiHvciIsVbsPolicyFailure
0x1800a0729  test    al, al
0x1800a072b  jz      short loc_1800A0752
0x1800a072d  call    CiHvciReleaseHvciOnlyResourcesInValidationContext
0x1800a0732  lea     rax, off_18002EE80
0x1800a0739  mov     edx, esi
0x1800a073b  mov     rcx, rdi
0x1800a073e  mov     [r14], rax
0x1800a0741  call    CiReinitializeValidationContext
0x1800a0746  mov     byte ptr [rdi+0CE8h], 0
0x1800a074d  jmp     loc_1800A0608
0x1800a0752  cmp     ebx, 0C0E90002h
0x1800a0758  jz      short loc_1800A0797
0x1800a075a  cmp     ebx, 0C0000428h
0x1800a0760  jz      short loc_1800A0797
0x1800a0762  cmp     ebx, 0C000007Bh
0x1800a0768  jz      short loc_1800A0797
0x1800a076a  lea     eax, [rbx+3F16FFF9h]
0x1800a0770  cmp     eax, 6
0x1800a0773  jbe     short loc_1800A0797
0x1800a0775  mov     rdx, [rsp+0F8h+var_78]
0x1800a077d  mov     r9b, r12b
0x1800a0780  mov     r8d, esi
0x1800a0783  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x1800a0787  mov     rcx, rbp
0x1800a078a  call    CipAllowPolicyEngineToEvaluateObjectWithExpiredAndRevokedCert
0x1800a078f  test    al, al
0x1800a0791  jz      loc_1800A0837
0x1800a0797  test    esi, 0E41FFF87h
0x1800a079d  jnz     loc_1800A0837
0x1800a07a3  mov     rax, cs:g_CipWhichLevelComparisons
0x1800a07aa  mov     rcx, r12
0x1800a07ad  and     ecx, 0Fh
0x1800a07b0  mov     ecx, [rax+rcx*4]
0x1800a07b3  test    cl, 4
0x1800a07b6  jz      short loc_1800A0837
0x1800a07b8  lea     rax, CipValidateFileHash
0x1800a07bf  cmp     [rsp+0F8h+var_70], rax
0x1800a07c7  jnz     short loc_1800A0837
0x1800a07c9  cmp     dword ptr [rdi+18h], 1Ah
0x1800a07cd  jz      short loc_1800A0837
0x1800a07cf  call    Feature_TrustedLaunchHosts__private_IsEnabledDeviceUsageNoInline
0x1800a07d4  test    eax, eax
0x1800a07d6  jz      short loc_1800A07E2
0x1800a07d8  cmp     qword ptr [rdi+0E10h], 0
0x1800a07e0  jnz     short loc_1800A0837
0x1800a07e2  mov     [rsp+0F8h+var_D0], r13
0x1800a07e7  mov     r9b, r12b
0x1800a07ea  mov     r8d, esi
0x1800a07ed  mov     [rsp+0F8h+var_D8], rbp
0x1800a07f2  mov     edx, ebx
0x1800a07f4  mov     rcx, rdi
0x1800a07f7  call    CipApplySIPolicyUMCI
0x1800a07fc  mov     ebx, eax
0x1800a07fe  test    eax, eax
0x1800a0800  jns     loc_1800A0968
0x1800a0806  cmp     dword ptr [rdi+18h], 1Ah
0x1800a080a  jz      short loc_1800A083F
0x1800a080c  test    dword ptr [rdi+0BE8h], 100h
0x1800a0816  jnz     short loc_1800A083F
0x1800a0818  and     dword ptr [rdi+938h], 0FFFFFFFDh
0x1800a081f  mov     r9b, r12b
0x1800a0822  mov     r8d, esi
0x1800a0825  mov     [rsp+0F8h+var_D8], r13
0x1800a082a  mov     rdx, rbp
0x1800a082d  mov     rcx, rdi
0x1800a0830  call    CipValidateFileObjectWithContext
0x1800a0835  mov     ebx, eax
0x1800a0837  test    ebx, ebx
0x1800a0839  jns     loc_1800A0968
0x1800a083f  cmp     ebx, 0C0E90002h
0x1800a0845  jz      short loc_1800A086A
0x1800a0847  cmp     ebx, 0C0000603h
0x1800a084d  jz      short loc_1800A086A
0x1800a084f  cmp     ebx, 0C0000428h
0x1800a0855  jz      short loc_1800A086A
0x1800a0857  cmp     ebx, 0C000007Bh
0x1800a085d  jz      short loc_1800A086A
0x1800a085f  lea     eax, [rbx+3F16FFF9h]
0x1800a0865  cmp     eax, 6
0x1800a0868  ja      short loc_1800A0895
0x1800a086a  inc     r15b
0x1800a086d  cmp     r15b, [rsp+0F8h+var_60]
0x1800a0875  jb      loc_1800A05EA
0x1800a087b  bt      esi, 1Bh
0x1800a087f  jnb     short loc_1800A088D
0x1800a0881  xor     r15b, r15b
0x1800a0884  btr     esi, 1Bh
0x1800a0888  jmp     loc_1800A05EA
0x1800a088d  cmp     ebx, 0C0000428h
0x1800a0893  jz      short loc_1800A08CC
0x1800a0895  lea     eax, [rbx+3F16FFF9h]
0x1800a089b  cmp     eax, 6
0x1800a089e  jbe     short loc_1800A08CC
0x1800a08a0  cmp     ebx, 0C0E90002h
0x1800a08a6  jz      short loc_1800A08CC
0x1800a08a8  cmp     ebx, 0C0000605h
0x1800a08ae  jz      short loc_1800A08CC
0x1800a08b0  cmp     ebx, 0C0000603h
0x1800a08b6  jz      short loc_1800A08CC
0x1800a08b8  cmp     ebx, 0C000010Eh
0x1800a08be  jz      short loc_1800A08CC
0x1800a08c0  cmp     ebx, 0C0EB0003h
0x1800a08c6  jnz     loc_1800A0968
0x1800a08cc  mov     edx, [rdi+938h]
0x1800a08d2  mov     eax, edx
0x1800a08d4  and     eax, 0C0000h
0x1800a08d9  cmp     eax, 80000h
0x1800a08de  jnz     loc_1800A0968
0x1800a08e4  mov     eax, [rdi+18h]
0x1800a08e7  cmp     eax, 15h
0x1800a08ea  jz      short loc_1800A08F0
0x1800a08ec  test    eax, eax
0x1800a08ee  jnz     short loc_1800A0968
0x1800a08f0  mov     rax, [rsp+0F8h+var_88]
0x1800a08f5  btr     edx, 13h
0x1800a08f9  mov     r9, [rsp+0F8h+var_78]
0x1800a0901  bts     edx, 12h
0x1800a0905  mov     rcx, [rsp+0F8h+var_70]
0x1800a090d  btr     esi, 1Bh
0x1800a0911  mov     [rsp+0F8h+var_A8], r13
0x1800a0916  mov     r8, rbp
0x1800a0919  mov     [rsp+0F8h+var_B0], rax
0x1800a091e  mov     al, [rsp+0F8h+arg_40]
0x1800a0925  mov     byte ptr [rsp+0F8h+var_B8], al
0x1800a0929  mov     al, [rsp+0F8h+arg_38]
0x1800a0930  mov     byte ptr [rsp+0F8h+var_C0], al
0x1800a0934  mov     eax, [rsp+0F8h+arg_28]
0x1800a093b  mov     [rsp+0F8h+var_C8], esi
0x1800a093f  mov     dword ptr [rsp+0F8h+var_D0], eax
0x1800a0943  mov     rax, [rsp+0F8h+var_80]
0x1800a0948  mov     [rdi+938h], edx
0x1800a094e  mov     rdx, rdi
0x1800a0951  mov     [rsp+0F8h+var_D8], rax
0x1800a0956  call    CipValidateImageHash
0x1800a095b  test    eax, eax
0x1800a095d  cmovns  ebx, eax
0x1800a0960  btr     dword ptr [rdi+938h], 12h
0x1800a0968  lea     rdx, [rdi+18h]
0x1800a096c  mov     ecx, ebx
0x1800a096e  call    CipSetRevocationRuleAppliedIfRequired
0x1800a0973  mov     eax, ebx
0x1800a0975  mov     rcx, [rsp+0F8h+var_58]
0x1800a097d  xor     rcx, rsp; StackCookie
0x1800a0980  call    __security_check_cookie
0x1800a0985  add     rsp, 0B8h
0x1800a098c  pop     r15
0x1800a098e  pop     r14
0x1800a0990  pop     r13
0x1800a0992  pop     r12
0x1800a0994  pop     rdi
0x1800a0995  pop     rsi
0x1800a0996  pop     rbp
0x1800a0997  pop     rbx
0x1800a0998  retn
```
