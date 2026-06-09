# CipValidateImageHash

- ea: `0x18009eef4`
- end: `0x18009f36a`
- name: `CipValidateImageHash`
- size: `1142`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180099688`
- `0x18009eef4`
- `0x1800e55e0`

## callees

- `0x18001003c`
- `0x18002bef0`
- `0x18002bfd0`
- `0x180059b3c`
- `0x1800642e8`
- `0x18007573c`
- `0x1800758fc`
- `0x1800759d4`
- `0x180091d2c`
- `0x18009222c`
- `0x180099bd0`
- `0x18009eef4`
- `0x1800a00e8`
- `0x1800a0154`
- `0x1800aae2c`
- `0x1800e2208`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009f0df`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x18009f0df`

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
0x18009eef4  mov     r11, rsp
0x18009eef7  push    rbx
0x18009eef8  push    rbp
0x18009eef9  push    rsi
0x18009eefa  push    rdi
0x18009eefb  push    r12
0x18009eefd  push    r13
0x18009eeff  push    r14
0x18009ef01  push    r15
0x18009ef03  sub     rsp, 0B8h
0x18009ef0a  mov     rax, cs:__security_cookie
0x18009ef11  xor     rax, rsp
0x18009ef14  mov     [rsp+0F8h+var_58], rax
0x18009ef1c  mov     rax, [rsp+0F8h+arg_20]
0x18009ef24  mov     r10, r9
0x18009ef27  mov     ebx, [rsp+0F8h+arg_30]
0x18009ef2e  mov     rbp, r8
0x18009ef31  mov     r13, [rsp+0F8h+arg_50]
0x18009ef39  mov     rdi, rdx
0x18009ef3c  mov     [rsp+0F8h+var_80], rax
0x18009ef41  mov     rdx, r10
0x18009ef44  mov     rax, [rsp+0F8h+arg_48]
0x18009ef4c  xor     r15b, r15b
0x18009ef4f  mov     [rsp+0F8h+var_88], rax
0x18009ef54  mov     [rsp+0F8h+var_70], rcx
0x18009ef5c  xor     ecx, ecx
0x18009ef5e  mov     [rsp+0F8h+var_78], r9
0x18009ef66  mov     rax, [rax]
0x18009ef69  mov     r9b, [rsp+0F8h+arg_38]
0x18009ef71  mov     [rsp+0F8h+var_68], rax
0x18009ef79  mov     al, [rsp+0F8h+arg_40]
0x18009ef80  mov     [rsp+0F8h+var_90], r8
0x18009ef85  mov     r8d, ebx
0x18009ef88  mov     [r11-60h], ecx
0x18009ef8c  mov     [r11-5Ch], cx
0x18009ef91  mov     [r11-5Ah], cl
0x18009ef95  mov     [rsp+0F8h+var_98], cl
0x18009ef99  lea     rcx, [r11-60h]
0x18009ef9d  mov     byte ptr [rsp+0F8h+var_D8], al
0x18009efa1  call    CipInitializeSigningLevelOrder
0x18009efa6  mov     eax, cs:g_CiPolicyState
0x18009efac  mov     esi, ebx
0x18009efae  bts     esi, 1Bh
0x18009efb2  shr     eax, 2
0x18009efb5  test    al, 1
0x18009efb7  cmovz   esi, ebx
0x18009efba  mov     edx, esi
0x18009efbc  mov     rcx, rdi
0x18009efbf  call    CiReinitializeValidationContext
0x18009efc4  movzx   eax, r15b
0x18009efc8  movzx   r12d, [rsp+rax+0F8h+var_5F]
0x18009efd1  lea     r14, [rdi+0BD8h]
0x18009efd8  mov     rax, [rsp+0F8h+var_88]
0x18009efdd  mov     rdx, rbp
0x18009efe0  mov     r9, [rsp+0F8h+var_80]
0x18009efe5  mov     rcx, rdi
0x18009efe8  mov     r8, [rsp+0F8h+var_78]
0x18009eff0  mov     [rsp+0F8h+var_B8], r13
0x18009eff5  mov     [rsp+0F8h+var_C0], rax
0x18009effa  mov     eax, [rsp+0F8h+arg_28]
0x18009f001  mov     byte ptr [rsp+0F8h+var_C8], r12b
0x18009f006  mov     dword ptr [rsp+0F8h+var_D0], esi
0x18009f00a  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18009f00e  mov     rax, [rsp+0F8h+var_70]
0x18009f016  call    _guard_dispatch_icall
0x18009f01b  mov     ebx, eax
0x18009f01d  test    eax, eax
0x18009f01f  js      loc_18009F0D8
0x18009f025  lea     rax, off_18002EE80
0x18009f02c  cmp     [rdi+0BD8h], rax
0x18009f033  jnz     loc_18009F145
0x18009f039  cmp     [rsp+0F8h+var_68], 0
0x18009f042  jnz     loc_18009F145
0x18009f048  test    cs:g_CiOptions, 200000h
0x18009f052  jnz     short loc_18009F08C
0x18009f054  cmp     byte ptr [rdi+0CE8h], 0
0x18009f05b  jz      loc_18009F145
0x18009f061  mov     rbp, [r13+0]
0x18009f065  mov     rcx, rbp
0x18009f068  call    CiIsSignatureTrustedForVsmEnclaves
0x18009f06d  test    al, al
0x18009f06f  jnz     short loc_18009F087
0x18009f071  mov     rcx, rbp
0x18009f074  call    CiIsSignatureTrustedForIum
0x18009f079  mov     rbp, [rsp+0F8h+var_90]
0x18009f07e  test    al, al
0x18009f080  jnz     short loc_18009F08C
0x18009f082  jmp     loc_18009F145
0x18009f087  mov     rbp, [rsp+0F8h+var_90]
0x18009f08c  mov     rbx, [rsp+0F8h+var_88]
0x18009f091  mov     rcx, [rbx]
0x18009f094  test    rcx, rcx
0x18009f097  jz      short loc_18009F0A5
0x18009f099  call    CiReleaseContext
0x18009f09e  mov     qword ptr [rbx], 0
0x18009f0a5  mov     r9d, [rsp+0F8h+arg_28]
0x18009f0ad  mov     edx, esi
0x18009f0af  mov     r8, [rsp+0F8h+var_80]
0x18009f0b4  mov     rcx, rdi
0x18009f0b7  mov     qword ptr [r13+0], 0
0x18009f0bf  call    CiHvciResetValidationContextForHvci
0x18009f0c4  mov     ebx, eax
0x18009f0c6  test    eax, eax
0x18009f0c8  js      loc_18009F25D
0x18009f0ce  mov     [rsp+0F8h+var_98], 1
0x18009f0d3  jmp     loc_18009EFD1
0x18009f0d8  cmp     [rsp+0F8h+var_98], 0
0x18009f0dd  jz      short loc_18009F122
0x18009f0df  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x18009f0e6  nop     dword ptr [rax+rax+00h]
0x18009f0eb  test    al, al
0x18009f0ed  jz      short loc_18009F122
0x18009f0ef  xor     edx, edx
0x18009f0f1  mov     rcx, rdi
0x18009f0f4  call    CiHvciIsVbsPolicyFailure
0x18009f0f9  test    al, al
0x18009f0fb  jz      short loc_18009F122
0x18009f0fd  call    CiHvciReleaseHvciOnlyResourcesInValidationContext
0x18009f102  lea     rax, off_18002EE80
0x18009f109  mov     edx, esi
0x18009f10b  mov     rcx, rdi
0x18009f10e  mov     [r14], rax
0x18009f111  call    CiReinitializeValidationContext
0x18009f116  mov     byte ptr [rdi+0CE8h], 0
0x18009f11d  jmp     loc_18009EFD8
0x18009f122  cmp     ebx, 0C0E90002h
0x18009f128  jz      short loc_18009F167
0x18009f12a  cmp     ebx, 0C0000428h
0x18009f130  jz      short loc_18009F167
0x18009f132  cmp     ebx, 0C000007Bh
0x18009f138  jz      short loc_18009F167
0x18009f13a  lea     eax, [rbx+3F16FFF9h]
0x18009f140  cmp     eax, 6
0x18009f143  jbe     short loc_18009F167
0x18009f145  mov     rdx, [rsp+0F8h+var_78]
0x18009f14d  mov     r9b, r12b
0x18009f150  mov     r8d, esi
0x18009f153  mov     dword ptr [rsp+0F8h+var_D8], ebx
0x18009f157  mov     rcx, rbp
0x18009f15a  call    CipAllowPolicyEngineToEvaluateObjectWithExpiredAndRevokedCert
0x18009f15f  test    al, al
0x18009f161  jz      loc_18009F207
0x18009f167  test    esi, 0E41FFF87h
0x18009f16d  jnz     loc_18009F207
0x18009f173  mov     rax, cs:g_CipWhichLevelComparisons
0x18009f17a  mov     rcx, r12
0x18009f17d  and     ecx, 0Fh
0x18009f180  mov     ecx, [rax+rcx*4]
0x18009f183  test    cl, 4
0x18009f186  jz      short loc_18009F207
0x18009f188  lea     rax, CipValidateFileHash
0x18009f18f  cmp     [rsp+0F8h+var_70], rax
0x18009f197  jnz     short loc_18009F207
0x18009f199  cmp     dword ptr [rdi+18h], 1Ah
0x18009f19d  jz      short loc_18009F207
0x18009f19f  call    Feature_TrustedLaunchHosts__private_IsEnabledDeviceUsageNoInline
0x18009f1a4  test    eax, eax
0x18009f1a6  jz      short loc_18009F1B2
0x18009f1a8  cmp     qword ptr [rdi+0E10h], 0
0x18009f1b0  jnz     short loc_18009F207
0x18009f1b2  mov     [rsp+0F8h+var_D0], r13
0x18009f1b7  mov     r9b, r12b
0x18009f1ba  mov     r8d, esi
0x18009f1bd  mov     [rsp+0F8h+var_D8], rbp
0x18009f1c2  mov     edx, ebx
0x18009f1c4  mov     rcx, rdi
0x18009f1c7  call    CipApplySIPolicyUMCI
0x18009f1cc  mov     ebx, eax
0x18009f1ce  test    eax, eax
0x18009f1d0  jns     loc_18009F338
0x18009f1d6  cmp     dword ptr [rdi+18h], 1Ah
0x18009f1da  jz      short loc_18009F20F
0x18009f1dc  test    dword ptr [rdi+0BE8h], 100h
0x18009f1e6  jnz     short loc_18009F20F
0x18009f1e8  and     dword ptr [rdi+938h], 0FFFFFFFDh
0x18009f1ef  mov     r9b, r12b
0x18009f1f2  mov     r8d, esi
0x18009f1f5  mov     [rsp+0F8h+var_D8], r13
0x18009f1fa  mov     rdx, rbp
0x18009f1fd  mov     rcx, rdi
0x18009f200  call    CipValidateFileObjectWithContext
0x18009f205  mov     ebx, eax
0x18009f207  test    ebx, ebx
0x18009f209  jns     loc_18009F338
0x18009f20f  cmp     ebx, 0C0E90002h
0x18009f215  jz      short loc_18009F23A
0x18009f217  cmp     ebx, 0C0000603h
0x18009f21d  jz      short loc_18009F23A
0x18009f21f  cmp     ebx, 0C0000428h
0x18009f225  jz      short loc_18009F23A
0x18009f227  cmp     ebx, 0C000007Bh
0x18009f22d  jz      short loc_18009F23A
0x18009f22f  lea     eax, [rbx+3F16FFF9h]
0x18009f235  cmp     eax, 6
0x18009f238  ja      short loc_18009F265
0x18009f23a  inc     r15b
0x18009f23d  cmp     r15b, [rsp+0F8h+var_60]
0x18009f245  jb      loc_18009EFBA
0x18009f24b  bt      esi, 1Bh
0x18009f24f  jnb     short loc_18009F25D
0x18009f251  xor     r15b, r15b
0x18009f254  btr     esi, 1Bh
0x18009f258  jmp     loc_18009EFBA
0x18009f25d  cmp     ebx, 0C0000428h
0x18009f263  jz      short loc_18009F29C
0x18009f265  lea     eax, [rbx+3F16FFF9h]
0x18009f26b  cmp     eax, 6
0x18009f26e  jbe     short loc_18009F29C
0x18009f270  cmp     ebx, 0C0E90002h
0x18009f276  jz      short loc_18009F29C
0x18009f278  cmp     ebx, 0C0000605h
0x18009f27e  jz      short loc_18009F29C
0x18009f280  cmp     ebx, 0C0000603h
0x18009f286  jz      short loc_18009F29C
0x18009f288  cmp     ebx, 0C000010Eh
0x18009f28e  jz      short loc_18009F29C
0x18009f290  cmp     ebx, 0C0EB0003h
0x18009f296  jnz     loc_18009F338
0x18009f29c  mov     edx, [rdi+938h]
0x18009f2a2  mov     eax, edx
0x18009f2a4  and     eax, 0C0000h
0x18009f2a9  cmp     eax, 80000h
0x18009f2ae  jnz     loc_18009F338
0x18009f2b4  mov     eax, [rdi+18h]
0x18009f2b7  cmp     eax, 15h
0x18009f2ba  jz      short loc_18009F2C0
0x18009f2bc  test    eax, eax
0x18009f2be  jnz     short loc_18009F338
0x18009f2c0  mov     rax, [rsp+0F8h+var_88]
0x18009f2c5  btr     edx, 13h
0x18009f2c9  mov     r9, [rsp+0F8h+var_78]
0x18009f2d1  bts     edx, 12h
0x18009f2d5  mov     rcx, [rsp+0F8h+var_70]
0x18009f2dd  btr     esi, 1Bh
0x18009f2e1  mov     [rsp+0F8h+var_A8], r13
0x18009f2e6  mov     r8, rbp
0x18009f2e9  mov     [rsp+0F8h+var_B0], rax
0x18009f2ee  mov     al, [rsp+0F8h+arg_40]
0x18009f2f5  mov     byte ptr [rsp+0F8h+var_B8], al
0x18009f2f9  mov     al, [rsp+0F8h+arg_38]
0x18009f300  mov     byte ptr [rsp+0F8h+var_C0], al
0x18009f304  mov     eax, [rsp+0F8h+arg_28]
0x18009f30b  mov     [rsp+0F8h+var_C8], esi
0x18009f30f  mov     dword ptr [rsp+0F8h+var_D0], eax
0x18009f313  mov     rax, [rsp+0F8h+var_80]
0x18009f318  mov     [rdi+938h], edx
0x18009f31e  mov     rdx, rdi
0x18009f321  mov     [rsp+0F8h+var_D8], rax
0x18009f326  call    CipValidateImageHash
0x18009f32b  test    eax, eax
0x18009f32d  cmovns  ebx, eax
0x18009f330  btr     dword ptr [rdi+938h], 12h
0x18009f338  lea     rdx, [rdi+18h]
0x18009f33c  mov     ecx, ebx
0x18009f33e  call    CipSetRevocationRuleAppliedIfRequired
0x18009f343  mov     eax, ebx
0x18009f345  mov     rcx, [rsp+0F8h+var_58]
0x18009f34d  xor     rcx, rsp; StackCookie
0x18009f350  call    __security_check_cookie
0x18009f355  add     rsp, 0B8h
0x18009f35c  pop     r15
0x18009f35e  pop     r14
0x18009f360  pop     r13
0x18009f362  pop     r12
0x18009f364  pop     rdi
0x18009f365  pop     rsi
0x18009f366  pop     rbp
0x18009f367  pop     rbx
0x18009f368  retn
```
