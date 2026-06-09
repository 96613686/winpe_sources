# CipReadCustomSigningPolicy

- ea: `0x18006f734`
- end: `0x18006fcf1`
- name: `CipReadCustomSigningPolicy`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001db68`

## callees

- `0x18002bef0`
- `0x18006ee50`
- `0x18006f734`
- `0x1800a7520`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x18006f848`
- `ntoskrnl!_ultow_s` at `0x18006f848`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006f864`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006f864`
- `ntoskrnl!ExAllocatePool2` at `0x18006f804`
- `ntoskrnl!ExAllocatePool2` at `0x18006f804`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006fa18`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006fcc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006fa18`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006fcc2`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f7d6`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f893`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f921`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fbaf`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fc0f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fc6b`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f7d6`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f893`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006f921`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fbaf`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fc0f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18006fc6b`

## pseudocode

```c
__int64 CipReadCustomSigningPolicy()
{
  int v0; // r12d
  unsigned int v1; // ebx
  char *v2; // r15
  unsigned int i; // esi
  __int64 v4; // r14
  char *v5; // rdi
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // edx
  char *v10; // r10
  int v11; // ecx
  unsigned __int8 *v12; // r8
  __int64 v13; // r9
  unsigned int v14; // ecx
  int v15; // esi
  unsigned int v16; // r13d
  __int64 v17; // rdi
  __int64 v18; // r14
  __int64 v19; // r15
  int SecureBootPolicyValue; // eax
  int v21; // edx
  __int64 v22; // r14
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  unsigned int v27; // [rsp+30h] [rbp-59h] BYREF
  int v28; // [rsp+34h] [rbp-55h] BYREF
  int v29; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+3Ch] [rbp-4Dh] BYREF
  unsigned int v31; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+44h] [rbp-45h] BYREF
  int v33; // [rsp+48h] [rbp-41h] BYREF
  int v34; // [rsp+4Ch] [rbp-3Dh] BYREF
  __int64 Pool2; // [rsp+50h] [rbp-39h]
  PVOID P; // [rsp+58h] [rbp-31h] BYREF
  __int64 v37; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  WCHAR SourceString[12]; // [rsp+78h] [rbp-11h] BYREF
  __int64 v40; // [rsp+90h] [rbp+7h]

  v0 = 0;
  P = 0;
  v40 = 0;
  DestinationString = 0;
  v34 = 0;
  v27 = 0;
  v33 = 0;
  v32 = 0;
  v29 = 0;
  wcscpy(SourceString, L"CI\\Signers\\");
  v30 = 0;
  v37 = 0;
  v31 = 0;
  v28 = 0;
  if ( (int)SeQuerySecureBootPolicyValue(&qword_1800308A0, &qword_1800308B0, 2, &v30, 4, &v28) < 0 )
    return 0;
  Pool2 = ExAllocatePool2(258, 40LL * v30, 1668499779);
  v2 = (char *)Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741801;
  for ( i = 0; ; ++i )
  {
    if ( i >= v30 )
    {
      if ( (g_CiOptions & 8) != 0 )
      {
        g_CiSignerTypeMax = 2;
        v15 = 2;
      }
      else
      {
        v15 = ((unsigned __int8)g_CiDeveloperMode >> 2) & 1;
        g_CiSignerTypeMax = 0;
      }
      v16 = 0;
      g_CipCustomLevelComparisons = xmmword_180035F80;
      xmmword_1800494F0 = xmmword_180035F90;
      xmmword_180049500 = xmmword_180035FA0;
      xmmword_180049510 = xmmword_180035FB0;
      while ( v16 < 0x13 )
      {
        v17 = v16;
        v18 = 12LL * v16;
        v19 = 2LL * v16;
        while ( v0 <= v15 )
        {
          v19 = 2LL * v16;
          SecureBootPolicyValue = CipAllocateAndQuerySecureBootPolicyValue(
                                    0x180000000LL + v19 * 8 + 198432,
                                    (unsigned int)&asc_1800308D0[8 * v0],
                                    4,
                                    (unsigned int)&v37,
                                    (__int64)&v31);
          v1 = SecureBootPolicyValue;
          if ( SecureBootPolicyValue < 0 )
          {
            if ( SecureBootPolicyValue != -1073741772 )
              goto LABEL_59;
            dword_180048AC0[v18 + v0] = 0;
          }
          else
          {
            v31 >>= 2;
            v21 = v31;
            v18 = 12LL * v16;
            qword_180048AA8[6 * v16 + v0] = v37;
            dword_180048AC0[v0 + v18] = v21;
          }
          ++v0;
        }
        v22 = *((unsigned __int8 *)&qword_180035EB0[8] + v16);
        v0 = 0;
        if ( (_BYTE)v22 )
        {
          v23 = SeQuerySecureBootPolicyValue(&qword_180030720[v19], &qword_180030880, 2, &v29, 4, &v28);
          v1 = v23;
          if ( v23 < 0 )
          {
            if ( v23 != -1073741772 )
              goto LABEL_59;
          }
          else
          {
            *((_DWORD *)&g_CipCustomLevelComparisons + v22) = v29;
          }
        }
        if ( (int)SeQuerySecureBootPolicyValue(&qword_180030720[v19], L"\b\n", 2, &v27, 4, &v28) >= 0 )
        {
          v24 = v27;
        }
        else
        {
          v24 = 32780;
          v27 = 32780;
        }
        ++v16;
        g_CiScenarios[12 * v17] = v24;
      }
      v25 = SeQuerySecureBootPolicyValue(&qword_180030710, L"&(", 2, &v29, 4, &v28);
      v1 = v25;
      if ( v25 < 0 )
      {
        if ( v25 != -1073741772 )
        {
LABEL_59:
          v2 = (char *)Pool2;
          goto LABEL_60;
        }
      }
      else
      {
        g_CipCustomRuntimeCustomizableLevels = v29;
      }
      v1 = 0;
      g_CipWhichLevelComparisons = &g_CipCustomLevelComparisons;
      g_CiSignersCount = v30;
      g_CiSigners = Pool2;
      return v1;
    }
    if ( _ultow_s(i, &SourceString[11], 5u, 10) )
      goto LABEL_34;
    RtlInitUnicodeString(&DestinationString, SourceString);
    if ( (int)SeQuerySecureBootPolicyValue(&DestinationString, &qword_180030850, 2, &v32, 4, &v28) >= 0 && v32 )
    {
      v4 = i;
      v5 = &v2[40 * i];
      *(_DWORD *)v5 = v32;
      *((_DWORD *)v5 + 2) = 0;
      goto LABEL_18;
    }
    v4 = i;
    v5 = &v2[40 * i];
    *(_DWORD *)v5 = 0;
    v6 = CipAllocateAndQuerySecureBootPolicyValue(
           (unsigned int)&DestinationString,
           (unsigned int)&qword_180030920,
           10,
           (int)v5 + 16,
           (__int64)(v5 + 8));
    v1 = v6;
    if ( v6 < 0 )
      break;
    if ( (int)SeQuerySecureBootPolicyValue(&DestinationString, L"\b\n", 2, &v27, 4, &v28) >= 0 )
    {
      v7 = v27;
    }
    else
    {
      v7 = 32780;
      v27 = 32780;
    }
    *((_DWORD *)v5 + 1) = v7;
    if ( (int)HashKGetHashLength(v27, &v33) < 0 || v33 != *((_DWORD *)v5 + 2) )
      goto LABEL_34;
    v0 = 0;
LABEL_18:
    v8 = CipAllocateAndQuerySecureBootPolicyValue(
           (unsigned int)&DestinationString,
           (unsigned int)L"\b\n",
           10,
           (unsigned int)&P,
           (__int64)&v34);
    v1 = v8;
    if ( v8 >= 0 )
    {
      v10 = (char *)P;
      if ( !v34 || !*(_BYTE *)P )
        goto LABEL_32;
      v11 = v34 - 1;
      v9 = 0;
      v12 = (unsigned __int8 *)P + 1;
      while ( v11 )
      {
        v13 = *v12;
        if ( (unsigned int)(v13 - 1) > 0x7E )
          goto LABEL_32;
        v14 = v11 - 1;
        if ( (unsigned int)v13 > v14 )
          goto LABEL_32;
        ++v9;
        v11 = v14 - v13;
        v12 += v13 + 1;
      }
      if ( v9 != *(unsigned __int8 *)P || !v9 )
      {
LABEL_32:
        ExFreePoolWithTag(P, 0x63734943u);
        goto LABEL_34;
      }
      v5 = &v2[40 * v4];
      *((_DWORD *)v5 + 7) = v34 - 1;
      *((_QWORD *)v5 + 4) = v10 + 1;
    }
    else
    {
      if ( v8 != -1073741772 )
        goto LABEL_60;
      v9 = 0;
    }
    *((_DWORD *)v5 + 6) = v9;
  }
  if ( v6 == -1073741772 )
LABEL_34:
    v1 = -1069350909;
LABEL_60:
  ExFreePoolWithTag(v2, 0x63734943u);
  return v1;
}

```

## disassembly

```asm
0x18006f734  push    rbp
0x18006f736  push    rbx
0x18006f737  push    rsi
0x18006f738  push    rdi
0x18006f739  push    r12
0x18006f73b  push    r13
0x18006f73d  push    r14
0x18006f73f  push    r15
0x18006f741  lea     rbp, [rsp-1Fh]
0x18006f746  sub     rsp, 0A8h
0x18006f74d  mov     rax, cs:__security_cookie
0x18006f754  xor     rax, rsp
0x18006f757  mov     [rbp+57h+var_48], rax
0x18006f75b  movups  xmm1, xmmword ptr cs:aCiSigners; "CI\\Signers\\"
0x18006f762  xor     r12d, r12d
0x18006f765  lea     r9, [rbp+57h+var_A4]
0x18006f769  xor     eax, eax
0x18006f76b  mov     [rbp+57h+P], r12
0x18006f76f  xorps   xmm0, xmm0
0x18006f772  mov     [rbp+57h+var_50], rax
0x18006f776  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18006f77a  lea     rax, [rbp+57h+var_AC]
0x18006f77e  mov     [rbp+57h+var_94], r12d
0x18006f782  movsd   xmm0, qword ptr cs:aCiSigners+10h; "rs\\"
0x18006f78a  lea     edi, [r12+2]
0x18006f78f  mov     [rsp+0E0h+var_B8], rax
0x18006f794  lea     rdx, qword_1800308B0
0x18006f79b  mov     r8d, edi
0x18006f79e  mov     [rbp+57h+var_B0], r12d
0x18006f7a2  lea     rcx, qword_1800308A0
0x18006f7a9  mov     [rbp+57h+var_98], r12d
0x18006f7ad  mov     [rbp+57h+var_9C], r12d
0x18006f7b1  mov     [rbp+57h+var_A8], r12d
0x18006f7b5  movups  xmmword ptr [rbp+57h+SourceString], xmm1
0x18006f7b9  mov     [rbp+57h+var_A4], r12d
0x18006f7bd  movsd   qword ptr [rbp+57h+DstBuf], xmm0
0x18006f7c2  mov     [rbp+57h+var_80], r12
0x18006f7c6  mov     [rbp+57h+var_A0], r12d
0x18006f7ca  mov     [rbp+57h+var_AC], r12d
0x18006f7ce  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18006f7d6  call    cs:__imp_SeQuerySecureBootPolicyValue
0x18006f7dd  nop     dword ptr [rax+rax+00h]
0x18006f7e2  test    eax, eax
0x18006f7e4  jns     short loc_18006F7EE
0x18006f7e6  mov     ebx, r12d
0x18006f7e9  jmp     loc_18006FCCE
0x18006f7ee  mov     eax, [rbp+57h+var_A4]
0x18006f7f1  mov     ecx, 102h
0x18006f7f6  mov     r8d, 63734943h
0x18006f7fc  lea     rdx, [rax+rax*4]
0x18006f800  shl     rdx, 3
0x18006f804  call    cs:__imp_ExAllocatePool2
0x18006f80b  nop     dword ptr [rax+rax+00h]
0x18006f810  mov     [rbp+57h+var_90], rax
0x18006f814  mov     r15, rax
0x18006f817  test    rax, rax
0x18006f81a  jnz     short loc_18006F826
0x18006f81c  mov     ebx, 0C0000017h
0x18006f821  jmp     loc_18006FCCE
0x18006f826  mov     esi, r12d
0x18006f829  mov     r13d, 0C0000034h
0x18006f82f  cmp     esi, [rbp+57h+var_A4]
0x18006f832  jnb     loc_18006FA39
0x18006f838  mov     r9d, 0Ah; Radix
0x18006f83e  lea     rdx, [rbp+57h+DstBuf+6]; DstBuf
0x18006f842  mov     ecx, esi; Val
0x18006f844  lea     r8d, [r9-5]; SizeInWords
0x18006f848  call    cs:__imp__ultow_s
0x18006f84f  nop     dword ptr [rax+rax+00h]
0x18006f854  test    eax, eax
0x18006f856  jnz     loc_18006FA2F
0x18006f85c  lea     rdx, [rbp+57h+SourceString]; SourceString
0x18006f860  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18006f864  call    cs:__imp_RtlInitUnicodeString
0x18006f86b  nop     dword ptr [rax+rax+00h]
0x18006f870  lea     rax, [rbp+57h+var_AC]
0x18006f874  mov     r8d, edi
0x18006f877  mov     [rsp+0E0h+var_B8], rax
0x18006f87c  lea     r9, [rbp+57h+var_9C]
0x18006f880  lea     rdx, qword_180030850
0x18006f887  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18006f88f  lea     rcx, [rbp+57h+DestinationString]
0x18006f893  call    cs:__imp_SeQuerySecureBootPolicyValue
0x18006f89a  nop     dword ptr [rax+rax+00h]
0x18006f89f  test    eax, eax
0x18006f8a1  js      short loc_18006F8C0
0x18006f8a3  mov     ecx, [rbp+57h+var_9C]
0x18006f8a6  test    ecx, ecx
0x18006f8a8  jz      short loc_18006F8C0
0x18006f8aa  mov     r14d, esi
0x18006f8ad  lea     rax, [r14+r14*4]
0x18006f8b1  lea     rdi, [r15+rax*8]
0x18006f8b5  mov     [rdi], ecx
0x18006f8b7  mov     [rdi+8], r12d
0x18006f8bb  jmp     loc_18006F965
0x18006f8c0  mov     r14d, esi
0x18006f8c3  lea     rdx, qword_180030920
0x18006f8ca  mov     r8d, 0Ah
0x18006f8d0  lea     rcx, [rbp+57h+DestinationString]
0x18006f8d4  lea     rax, [r14+r14*4]
0x18006f8d8  lea     rdi, [r15+rax*8]
0x18006f8dc  mov     [rdi], r12d
0x18006f8df  lea     r9, [rdi+10h]
0x18006f8e3  lea     r12, [rdi+8]
0x18006f8e7  mov     [rsp+0E0h+var_C0], r12
0x18006f8ec  call    CipAllocateAndQuerySecureBootPolicyValue
0x18006f8f1  mov     ebx, eax
0x18006f8f3  test    eax, eax
0x18006f8f5  js      loc_18006FA26
0x18006f8fb  lea     rax, [rbp+57h+var_AC]
0x18006f8ff  mov     r8d, 2
0x18006f905  mov     [rsp+0E0h+var_B8], rax
0x18006f90a  lea     r9, [rbp+57h+var_B0]
0x18006f90e  lea     rdx, asc_180030860; "\b\n"
0x18006f915  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18006f91d  lea     rcx, [rbp+57h+DestinationString]
0x18006f921  call    cs:__imp_SeQuerySecureBootPolicyValue
0x18006f928  nop     dword ptr [rax+rax+00h]
0x18006f92d  test    eax, eax
0x18006f92f  jns     short loc_18006F93B
0x18006f931  mov     eax, 800Ch
0x18006f936  mov     [rbp+57h+var_B0], eax
0x18006f939  jmp     short loc_18006F93E
0x18006f93b  mov     eax, [rbp+57h+var_B0]
0x18006f93e  mov     [rdi+4], eax
0x18006f941  lea     rdx, [rbp+57h+var_98]
0x18006f945  mov     ecx, [rbp+57h+var_B0]
0x18006f948  call    HashKGetHashLength
0x18006f94d  test    eax, eax
0x18006f94f  js      loc_18006FA2F
0x18006f955  mov     eax, [r12]
0x18006f959  cmp     [rbp+57h+var_98], eax
0x18006f95c  jnz     loc_18006FA2F
0x18006f962  xor     r12d, r12d
0x18006f965  lea     rax, [rbp+57h+var_94]
0x18006f969  mov     r8d, 0Ah
0x18006f96f  lea     r9, [rbp+57h+P]
0x18006f973  mov     [rsp+0E0h+var_C0], rax
0x18006f978  lea     rdx, asc_180030930; "\b\n"
0x18006f97f  lea     rcx, [rbp+57h+DestinationString]
0x18006f983  call    CipAllocateAndQuerySecureBootPolicyValue
0x18006f988  mov     ebx, eax
0x18006f98a  test    eax, eax
0x18006f98c  jns     short loc_18006F99C
0x18006f98e  cmp     eax, r13d
0x18006f991  jnz     loc_18006FCBA
0x18006f997  mov     edx, r12d
0x18006f99a  jmp     short loc_18006FA01
0x18006f99c  mov     ebx, [rbp+57h+var_94]
0x18006f99f  mov     ecx, ebx
0x18006f9a1  mov     r10, [rbp+57h+P]
0x18006f9a5  test    ebx, ebx
0x18006f9a7  jz      short loc_18006FA10
0x18006f9a9  movzx   r11d, byte ptr [r10]
0x18006f9ad  mov     r8, r10
0x18006f9b0  test    r11d, r11d
0x18006f9b3  jz      short loc_18006FA10
0x18006f9b5  dec     ecx
0x18006f9b7  mov     edx, r12d
0x18006f9ba  inc     r8
0x18006f9bd  test    ecx, ecx
0x18006f9bf  jz      short loc_18006F9E2
0x18006f9c1  movzx   r9d, byte ptr [r8]
0x18006f9c5  lea     eax, [r9-1]
0x18006f9c9  cmp     eax, 7Eh ; '~'
0x18006f9cc  ja      short loc_18006FA10
0x18006f9ce  dec     ecx
0x18006f9d0  cmp     r9d, ecx
0x18006f9d3  ja      short loc_18006FA10
0x18006f9d5  inc     edx
0x18006f9d7  sub     ecx, r9d
0x18006f9da  inc     r8
0x18006f9dd  add     r8, r9
0x18006f9e0  jmp     short loc_18006F9BD
0x18006f9e2  cmp     edx, r11d
0x18006f9e5  jnz     short loc_18006FA10
0x18006f9e7  test    edx, edx
0x18006f9e9  jz      short loc_18006FA10
0x18006f9eb  lea     rax, [r14+r14*4]
0x18006f9ef  lea     rdi, [r15+rax*8]
0x18006f9f3  lea     eax, [rbx-1]
0x18006f9f6  mov     [rdi+1Ch], eax
0x18006f9f9  lea     rax, [r10+1]
0x18006f9fd  mov     [rdi+20h], rax
0x18006fa01  mov     [rdi+18h], edx
0x18006fa04  inc     esi
0x18006fa06  mov     edi, 2
0x18006fa0b  jmp     loc_18006F82F
0x18006fa10  mov     edx, 63734943h; Tag
0x18006fa15  mov     rcx, r10; P
0x18006fa18  call    cs:__imp_ExFreePoolWithTag
0x18006fa1f  nop     dword ptr [rax+rax+00h]
0x18006fa24  jmp     short loc_18006FA2F
0x18006fa26  cmp     eax, r13d
0x18006fa29  jnz     loc_18006FCBA
0x18006fa2f  mov     ebx, 0C0430003h
0x18006fa34  jmp     loc_18006FCBA
0x18006fa39  mov     eax, cs:g_CiOptions
0x18006fa3f  test    al, 8
0x18006fa41  jz      short loc_18006FA4D
0x18006fa43  mov     cs:g_CiSignerTypeMax, edi
0x18006fa49  mov     esi, edi
0x18006fa4b  jmp     short loc_18006FA61
0x18006fa4d  movzx   esi, byte ptr cs:g_CiDeveloperMode
0x18006fa54  shr     esi, 2
0x18006fa57  and     esi, 1
0x18006fa5a  mov     cs:g_CiSignerTypeMax, r12d
0x18006fa61  movaps  xmm0, cs:xmmword_180035F80
0x18006fa68  lea     rbx, cs:180000000h
0x18006fa6f  movaps  xmm1, cs:xmmword_180035F90
0x18006fa76  mov     r13d, r12d
0x18006fa79  movups  cs:g_CipCustomLevelComparisons, xmm0
0x18006fa80  movaps  xmm0, cs:xmmword_180035FA0
0x18006fa87  movups  cs:xmmword_1800494F0, xmm1
0x18006fa8e  movaps  xmm1, cs:xmmword_180035FB0
0x18006fa95  movups  cs:xmmword_180049500, xmm0
0x18006fa9c  movups  cs:xmmword_180049510, xmm1
0x18006faa3  cmp     r13d, 13h
0x18006faa7  jnb     loc_18006FC42
0x18006faad  mov     edi, r13d
0x18006fab0  mov     r15d, r13d
0x18006fab3  lea     r14, [rdi+rdi*2]
0x18006fab7  shl     r14, 2
0x18006fabb  shl     r15, 4
0x18006fabf  cmp     r12d, esi
0x18006fac2  jg      loc_18006FB73
0x18006fac8  lea     rax, asc_1800308D0; "\"$"
0x18006facf  movsxd  rdx, r12d
0x18006fad2  shl     rdx, 4
0x18006fad6  lea     r9, [rbp+57h+var_80]
0x18006fada  add     rdx, rax
0x18006fadd  mov     r15, rdi
0x18006fae0  lea     rax, [rbp+57h+var_A0]
0x18006fae4  shl     r15, 4
0x18006fae8  mov     r8d, 4
0x18006faee  mov     [rsp+0E0h+var_C0], rax
0x18006faf3  lea     rcx, [r15+30720h]
0x18006fafa  add     rcx, rbx
0x18006fafd  call    CipAllocateAndQuerySecureBootPolicyValue
0x18006fb02  mov     ebx, eax
0x18006fb04  test    eax, eax
0x18006fb06  js      short loc_18006FB48
0x18006fb08  mov     edx, [rbp+57h+var_A0]
0x18006fb0b  lea     rax, [rdi+rdi*2]
0x18006fb0f  shr     edx, 2
0x18006fb12  lea     rbx, cs:180000000h
0x18006fb19  movsxd  r8, r12d
0x18006fb1c  lea     r14, [rdi+rdi*2]
0x18006fb20  mov     [rbp+57h+var_A0], edx
0x18006fb23  shl     r14, 2
0x18006fb27  lea     rcx, [r8+rax*2]
0x18006fb2b  mov     rax, [rbp+57h+var_80]
0x18006fb2f  mov     rva qword_180048AA8[rbx+rcx*8], rax
0x18006fb37  lea     rax, [rdi+rdi*2]
0x18006fb3b  lea     rcx, [r8+rax*4]
0x18006fb3f  mov     rva dword_180048AC0[rbx+rcx*4], edx
0x18006fb46  jmp     short loc_18006FB6B
0x18006fb48  cmp     eax, 0C0000034h
0x18006fb4d  jnz     loc_18006FCB6
0x18006fb53  movsxd  rax, r12d
0x18006fb56  lea     rbx, cs:180000000h
0x18006fb5d  add     rax, r14
0x18006fb60  mov     rva dword_180048AC0[rbx+rax*4], 0
0x18006fb6b  inc     r12d
0x18006fb6e  jmp     loc_18006FABF
0x18006fb73  movzx   r14d, byte ptr [rdi+rbx+35EF0h]
0x18006fb7c  xor     r12d, r12d
0x18006fb7f  test    r14b, r14b
0x18006fb82  jz      short loc_18006FBE3
0x18006fb84  lea     rax, [rbp+57h+var_AC]
0x18006fb88  mov     [rsp+0E0h+var_B8], rax
0x18006fb8d  lea     rcx, rva qword_180030720[rbx]
0x18006fb94  add     rcx, r15
0x18006fb97  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18006fb9f  lea     r9, [rbp+57h+var_A8]
0x18006fba3  lea     r8d, [r12+2]
0x18006fba8  lea     rdx, qword_180030880
0x18006fbaf  call    cs:__imp_SeQuerySecureBootPolicyValue
0x18006fbb6  nop     dword ptr [rax+rax+00h]
0x18006fbbb  mov     ebx, eax
0x18006fbbd  test    eax, eax
0x18006fbbf  js      short loc_18006FBD1
0x18006fbc1  mov     eax, [rbp+57h+var_A8]
0x18006fbc4  lea     rdx, g_CipCustomLevelComparisons
0x18006fbcb  mov     [rdx+r14*4], eax
0x18006fbcf  jmp     short loc_18006FBDC
0x18006fbd1  cmp     eax, 0C0000034h
0x18006fbd6  jnz     loc_18006FCB6
0x18006fbdc  lea     rbx, cs:180000000h
0x18006fbe3  lea     rax, [rbp+57h+var_AC]
0x18006fbe7  mov     r8d, 2
0x18006fbed  mov     [rsp+0E0h+var_B8], rax
0x18006fbf2  lea     rcx, rva qword_180030720[rbx]
0x18006fbf9  add     rcx, r15
0x18006fbfc  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18006fc04  lea     r9, [rbp+57h+var_B0]
0x18006fc08  lea     rdx, asc_180030860; "\b\n"
0x18006fc0f  call    cs:__imp_SeQuerySecureBootPolicyValue
0x18006fc16  nop     dword ptr [rax+rax+00h]
0x18006fc1b  test    eax, eax
  ... truncated ...
```
