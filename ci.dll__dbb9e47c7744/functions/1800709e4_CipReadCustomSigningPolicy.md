# CipReadCustomSigningPolicy

- ea: `0x1800709e4`
- end: `0x180070fa1`
- name: `CipReadCustomSigningPolicy`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001daa8`

## callees

- `0x18002bf20`
- `0x180070100`
- `0x1800709e4`
- `0x1800a89a0`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x180070af8`
- `ntoskrnl!_ultow_s` at `0x180070af8`
- `ntoskrnl!RtlInitUnicodeString` at `0x180070b14`
- `ntoskrnl!RtlInitUnicodeString` at `0x180070b14`
- `ntoskrnl!ExAllocatePool2` at `0x180070ab4`
- `ntoskrnl!ExAllocatePool2` at `0x180070ab4`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070f72`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070cc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070f72`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070a86`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070b43`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070bd1`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070e5f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070ebf`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070f1b`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070a86`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070b43`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070bd1`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070e5f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070ebf`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070f1b`

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
  if ( (int)SeQuerySecureBootPolicyValue(&qword_180030940, &qword_180030950, 2, &v30, 4, &v28) < 0 )
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
      g_CipCustomLevelComparisons = xmmword_180036040;
      xmmword_18004A4D0 = xmmword_180036050;
      xmmword_18004A4E0 = xmmword_180036060;
      xmmword_18004A4F0 = xmmword_180036070;
      while ( v16 < 0x13 )
      {
        v17 = v16;
        v18 = 12LL * v16;
        v19 = 2LL * v16;
        while ( v0 <= v15 )
        {
          v19 = 2LL * v16;
          SecureBootPolicyValue = CipAllocateAndQuerySecureBootPolicyValue(
                                    0x180000000LL + v19 * 8 + 198576,
                                    (unsigned int)&asc_180030970[8 * v0],
                                    4,
                                    (unsigned int)&v37,
                                    (__int64)&v31);
          v1 = SecureBootPolicyValue;
          if ( SecureBootPolicyValue < 0 )
          {
            if ( SecureBootPolicyValue != -1073741772 )
              goto LABEL_59;
            dword_180049AB0[v18 + v0] = 0;
          }
          else
          {
            v31 >>= 2;
            v21 = v31;
            v18 = 12LL * v16;
            qword_180049A98[6 * v16 + v0] = v37;
            dword_180049AB0[v0 + v18] = v21;
          }
          ++v0;
        }
        v22 = *((unsigned __int8 *)&g_MsitTestCodeSignCA3Hash[4] + v16);
        v0 = 0;
        if ( (_BYTE)v22 )
        {
          v23 = SeQuerySecureBootPolicyValue(&qword_1800307B0[v19], &qword_180030920, 2, &v29, 4, &v28);
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
        if ( (int)SeQuerySecureBootPolicyValue(&qword_1800307B0[v19], L"\b\n", 2, &v27, 4, &v28) >= 0 )
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
      v25 = SeQuerySecureBootPolicyValue(&qword_1800308E0, L"&(", 2, &v29, 4, &v28);
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
    if ( (int)SeQuerySecureBootPolicyValue(&DestinationString, &qword_1800308F0, 2, &v32, 4, &v28) >= 0 && v32 )
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
           (unsigned int)&qword_1800309C0,
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
0x1800709e4  push    rbp
0x1800709e6  push    rbx
0x1800709e7  push    rsi
0x1800709e8  push    rdi
0x1800709e9  push    r12
0x1800709eb  push    r13
0x1800709ed  push    r14
0x1800709ef  push    r15
0x1800709f1  lea     rbp, [rsp-1Fh]
0x1800709f6  sub     rsp, 0A8h
0x1800709fd  mov     rax, cs:__security_cookie
0x180070a04  xor     rax, rsp
0x180070a07  mov     [rbp+57h+var_48], rax
0x180070a0b  movups  xmm1, xmmword ptr cs:aCiSigners; "CI\\Signers\\"
0x180070a12  xor     r12d, r12d
0x180070a15  lea     r9, [rbp+57h+var_A4]
0x180070a19  xor     eax, eax
0x180070a1b  mov     [rbp+57h+P], r12
0x180070a1f  xorps   xmm0, xmm0
0x180070a22  mov     [rbp+57h+var_50], rax
0x180070a26  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180070a2a  lea     rax, [rbp+57h+var_AC]
0x180070a2e  mov     [rbp+57h+var_94], r12d
0x180070a32  movsd   xmm0, qword ptr cs:aCiSigners+10h; "rs\\"
0x180070a3a  lea     edi, [r12+2]
0x180070a3f  mov     [rsp+0E0h+var_B8], rax
0x180070a44  lea     rdx, qword_180030950
0x180070a4b  mov     r8d, edi
0x180070a4e  mov     [rbp+57h+var_B0], r12d
0x180070a52  lea     rcx, qword_180030940
0x180070a59  mov     [rbp+57h+var_98], r12d
0x180070a5d  mov     [rbp+57h+var_9C], r12d
0x180070a61  mov     [rbp+57h+var_A8], r12d
0x180070a65  movups  xmmword ptr [rbp+57h+SourceString], xmm1
0x180070a69  mov     [rbp+57h+var_A4], r12d
0x180070a6d  movsd   qword ptr [rbp+57h+DstBuf], xmm0
0x180070a72  mov     [rbp+57h+var_80], r12
0x180070a76  mov     [rbp+57h+var_A0], r12d
0x180070a7a  mov     [rbp+57h+var_AC], r12d
0x180070a7e  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070a86  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070a8d  nop     dword ptr [rax+rax+00h]
0x180070a92  test    eax, eax
0x180070a94  jns     short loc_180070A9E
0x180070a96  mov     ebx, r12d
0x180070a99  jmp     loc_180070F7E
0x180070a9e  mov     eax, [rbp+57h+var_A4]
0x180070aa1  mov     ecx, 102h
0x180070aa6  mov     r8d, 63734943h
0x180070aac  lea     rdx, [rax+rax*4]
0x180070ab0  shl     rdx, 3
0x180070ab4  call    cs:__imp_ExAllocatePool2
0x180070abb  nop     dword ptr [rax+rax+00h]
0x180070ac0  mov     [rbp+57h+var_90], rax
0x180070ac4  mov     r15, rax
0x180070ac7  test    rax, rax
0x180070aca  jnz     short loc_180070AD6
0x180070acc  mov     ebx, 0C0000017h
0x180070ad1  jmp     loc_180070F7E
0x180070ad6  mov     esi, r12d
0x180070ad9  mov     r13d, 0C0000034h
0x180070adf  cmp     esi, [rbp+57h+var_A4]
0x180070ae2  jnb     loc_180070CE9
0x180070ae8  mov     r9d, 0Ah; Radix
0x180070aee  lea     rdx, [rbp+57h+DstBuf+6]; DstBuf
0x180070af2  mov     ecx, esi; Val
0x180070af4  lea     r8d, [r9-5]; SizeInWords
0x180070af8  call    cs:__imp__ultow_s
0x180070aff  nop     dword ptr [rax+rax+00h]
0x180070b04  test    eax, eax
0x180070b06  jnz     loc_180070CDF
0x180070b0c  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180070b10  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180070b14  call    cs:__imp_RtlInitUnicodeString
0x180070b1b  nop     dword ptr [rax+rax+00h]
0x180070b20  lea     rax, [rbp+57h+var_AC]
0x180070b24  mov     r8d, edi
0x180070b27  mov     [rsp+0E0h+var_B8], rax
0x180070b2c  lea     r9, [rbp+57h+var_9C]
0x180070b30  lea     rdx, qword_1800308F0
0x180070b37  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070b3f  lea     rcx, [rbp+57h+DestinationString]
0x180070b43  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070b4a  nop     dword ptr [rax+rax+00h]
0x180070b4f  test    eax, eax
0x180070b51  js      short loc_180070B70
0x180070b53  mov     ecx, [rbp+57h+var_9C]
0x180070b56  test    ecx, ecx
0x180070b58  jz      short loc_180070B70
0x180070b5a  mov     r14d, esi
0x180070b5d  lea     rax, [r14+r14*4]
0x180070b61  lea     rdi, [r15+rax*8]
0x180070b65  mov     [rdi], ecx
0x180070b67  mov     [rdi+8], r12d
0x180070b6b  jmp     loc_180070C15
0x180070b70  mov     r14d, esi
0x180070b73  lea     rdx, qword_1800309C0
0x180070b7a  mov     r8d, 0Ah
0x180070b80  lea     rcx, [rbp+57h+DestinationString]
0x180070b84  lea     rax, [r14+r14*4]
0x180070b88  lea     rdi, [r15+rax*8]
0x180070b8c  mov     [rdi], r12d
0x180070b8f  lea     r9, [rdi+10h]
0x180070b93  lea     r12, [rdi+8]
0x180070b97  mov     [rsp+0E0h+var_C0], r12
0x180070b9c  call    CipAllocateAndQuerySecureBootPolicyValue
0x180070ba1  mov     ebx, eax
0x180070ba3  test    eax, eax
0x180070ba5  js      loc_180070CD6
0x180070bab  lea     rax, [rbp+57h+var_AC]
0x180070baf  mov     r8d, 2
0x180070bb5  mov     [rsp+0E0h+var_B8], rax
0x180070bba  lea     r9, [rbp+57h+var_B0]
0x180070bbe  lea     rdx, asc_180030900; "\b\n"
0x180070bc5  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070bcd  lea     rcx, [rbp+57h+DestinationString]
0x180070bd1  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070bd8  nop     dword ptr [rax+rax+00h]
0x180070bdd  test    eax, eax
0x180070bdf  jns     short loc_180070BEB
0x180070be1  mov     eax, 800Ch
0x180070be6  mov     [rbp+57h+var_B0], eax
0x180070be9  jmp     short loc_180070BEE
0x180070beb  mov     eax, [rbp+57h+var_B0]
0x180070bee  mov     [rdi+4], eax
0x180070bf1  lea     rdx, [rbp+57h+var_98]
0x180070bf5  mov     ecx, [rbp+57h+var_B0]
0x180070bf8  call    HashKGetHashLength
0x180070bfd  test    eax, eax
0x180070bff  js      loc_180070CDF
0x180070c05  mov     eax, [r12]
0x180070c09  cmp     [rbp+57h+var_98], eax
0x180070c0c  jnz     loc_180070CDF
0x180070c12  xor     r12d, r12d
0x180070c15  lea     rax, [rbp+57h+var_94]
0x180070c19  mov     r8d, 0Ah
0x180070c1f  lea     r9, [rbp+57h+P]
0x180070c23  mov     [rsp+0E0h+var_C0], rax
0x180070c28  lea     rdx, asc_1800309D0; "\b\n"
0x180070c2f  lea     rcx, [rbp+57h+DestinationString]
0x180070c33  call    CipAllocateAndQuerySecureBootPolicyValue
0x180070c38  mov     ebx, eax
0x180070c3a  test    eax, eax
0x180070c3c  jns     short loc_180070C4C
0x180070c3e  cmp     eax, r13d
0x180070c41  jnz     loc_180070F6A
0x180070c47  mov     edx, r12d
0x180070c4a  jmp     short loc_180070CB1
0x180070c4c  mov     ebx, [rbp+57h+var_94]
0x180070c4f  mov     ecx, ebx
0x180070c51  mov     r10, [rbp+57h+P]
0x180070c55  test    ebx, ebx
0x180070c57  jz      short loc_180070CC0
0x180070c59  movzx   r11d, byte ptr [r10]
0x180070c5d  mov     r8, r10
0x180070c60  test    r11d, r11d
0x180070c63  jz      short loc_180070CC0
0x180070c65  dec     ecx
0x180070c67  mov     edx, r12d
0x180070c6a  inc     r8
0x180070c6d  test    ecx, ecx
0x180070c6f  jz      short loc_180070C92
0x180070c71  movzx   r9d, byte ptr [r8]
0x180070c75  lea     eax, [r9-1]
0x180070c79  cmp     eax, 7Eh ; '~'
0x180070c7c  ja      short loc_180070CC0
0x180070c7e  dec     ecx
0x180070c80  cmp     r9d, ecx
0x180070c83  ja      short loc_180070CC0
0x180070c85  inc     edx
0x180070c87  sub     ecx, r9d
0x180070c8a  inc     r8
0x180070c8d  add     r8, r9
0x180070c90  jmp     short loc_180070C6D
0x180070c92  cmp     edx, r11d
0x180070c95  jnz     short loc_180070CC0
0x180070c97  test    edx, edx
0x180070c99  jz      short loc_180070CC0
0x180070c9b  lea     rax, [r14+r14*4]
0x180070c9f  lea     rdi, [r15+rax*8]
0x180070ca3  lea     eax, [rbx-1]
0x180070ca6  mov     [rdi+1Ch], eax
0x180070ca9  lea     rax, [r10+1]
0x180070cad  mov     [rdi+20h], rax
0x180070cb1  mov     [rdi+18h], edx
0x180070cb4  inc     esi
0x180070cb6  mov     edi, 2
0x180070cbb  jmp     loc_180070ADF
0x180070cc0  mov     edx, 63734943h; Tag
0x180070cc5  mov     rcx, r10; P
0x180070cc8  call    cs:__imp_ExFreePoolWithTag
0x180070ccf  nop     dword ptr [rax+rax+00h]
0x180070cd4  jmp     short loc_180070CDF
0x180070cd6  cmp     eax, r13d
0x180070cd9  jnz     loc_180070F6A
0x180070cdf  mov     ebx, 0C0430003h
0x180070ce4  jmp     loc_180070F6A
0x180070ce9  mov     eax, cs:g_CiOptions
0x180070cef  test    al, 8
0x180070cf1  jz      short loc_180070CFD
0x180070cf3  mov     cs:g_CiSignerTypeMax, edi
0x180070cf9  mov     esi, edi
0x180070cfb  jmp     short loc_180070D11
0x180070cfd  movzx   esi, byte ptr cs:g_CiDeveloperMode
0x180070d04  shr     esi, 2
0x180070d07  and     esi, 1
0x180070d0a  mov     cs:g_CiSignerTypeMax, r12d
0x180070d11  movaps  xmm0, cs:xmmword_180036040
0x180070d18  lea     rbx, cs:180000000h
0x180070d1f  movaps  xmm1, cs:xmmword_180036050
0x180070d26  mov     r13d, r12d
0x180070d29  movups  cs:g_CipCustomLevelComparisons, xmm0
0x180070d30  movaps  xmm0, cs:xmmword_180036060
0x180070d37  movups  cs:xmmword_18004A4D0, xmm1
0x180070d3e  movaps  xmm1, cs:xmmword_180036070
0x180070d45  movups  cs:xmmword_18004A4E0, xmm0
0x180070d4c  movups  cs:xmmword_18004A4F0, xmm1
0x180070d53  cmp     r13d, 13h
0x180070d57  jnb     loc_180070EF2
0x180070d5d  mov     edi, r13d
0x180070d60  mov     r15d, r13d
0x180070d63  lea     r14, [rdi+rdi*2]
0x180070d67  shl     r14, 2
0x180070d6b  shl     r15, 4
0x180070d6f  cmp     r12d, esi
0x180070d72  jg      loc_180070E23
0x180070d78  lea     rax, asc_180030970; "\"$"
0x180070d7f  movsxd  rdx, r12d
0x180070d82  shl     rdx, 4
0x180070d86  lea     r9, [rbp+57h+var_80]
0x180070d8a  add     rdx, rax
0x180070d8d  mov     r15, rdi
0x180070d90  lea     rax, [rbp+57h+var_A0]
0x180070d94  shl     r15, 4
0x180070d98  mov     r8d, 4
0x180070d9e  mov     [rsp+0E0h+var_C0], rax
0x180070da3  lea     rcx, [r15+307B0h]
0x180070daa  add     rcx, rbx
0x180070dad  call    CipAllocateAndQuerySecureBootPolicyValue
0x180070db2  mov     ebx, eax
0x180070db4  test    eax, eax
0x180070db6  js      short loc_180070DF8
0x180070db8  mov     edx, [rbp+57h+var_A0]
0x180070dbb  lea     rax, [rdi+rdi*2]
0x180070dbf  shr     edx, 2
0x180070dc2  lea     rbx, cs:180000000h
0x180070dc9  movsxd  r8, r12d
0x180070dcc  lea     r14, [rdi+rdi*2]
0x180070dd0  mov     [rbp+57h+var_A0], edx
0x180070dd3  shl     r14, 2
0x180070dd7  lea     rcx, [r8+rax*2]
0x180070ddb  mov     rax, [rbp+57h+var_80]
0x180070ddf  mov     rva qword_180049A98[rbx+rcx*8], rax
0x180070de7  lea     rax, [rdi+rdi*2]
0x180070deb  lea     rcx, [r8+rax*4]
0x180070def  mov     rva dword_180049AB0[rbx+rcx*4], edx
0x180070df6  jmp     short loc_180070E1B
0x180070df8  cmp     eax, 0C0000034h
0x180070dfd  jnz     loc_180070F66
0x180070e03  movsxd  rax, r12d
0x180070e06  lea     rbx, cs:180000000h
0x180070e0d  add     rax, r14
0x180070e10  mov     rva dword_180049AB0[rbx+rax*4], 0
0x180070e1b  inc     r12d
0x180070e1e  jmp     loc_180070D6F
0x180070e23  movzx   r14d, byte ptr [rdi+rbx+35FB0h]
0x180070e2c  xor     r12d, r12d
0x180070e2f  test    r14b, r14b
0x180070e32  jz      short loc_180070E93
0x180070e34  lea     rax, [rbp+57h+var_AC]
0x180070e38  mov     [rsp+0E0h+var_B8], rax
0x180070e3d  lea     rcx, rva qword_1800307B0[rbx]
0x180070e44  add     rcx, r15
0x180070e47  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070e4f  lea     r9, [rbp+57h+var_A8]
0x180070e53  lea     r8d, [r12+2]
0x180070e58  lea     rdx, qword_180030920
0x180070e5f  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070e66  nop     dword ptr [rax+rax+00h]
0x180070e6b  mov     ebx, eax
0x180070e6d  test    eax, eax
0x180070e6f  js      short loc_180070E81
0x180070e71  mov     eax, [rbp+57h+var_A8]
0x180070e74  lea     rdx, g_CipCustomLevelComparisons
0x180070e7b  mov     [rdx+r14*4], eax
0x180070e7f  jmp     short loc_180070E8C
0x180070e81  cmp     eax, 0C0000034h
0x180070e86  jnz     loc_180070F66
0x180070e8c  lea     rbx, cs:180000000h
0x180070e93  lea     rax, [rbp+57h+var_AC]
0x180070e97  mov     r8d, 2
0x180070e9d  mov     [rsp+0E0h+var_B8], rax
0x180070ea2  lea     rcx, rva qword_1800307B0[rbx]
0x180070ea9  add     rcx, r15
0x180070eac  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070eb4  lea     r9, [rbp+57h+var_B0]
0x180070eb8  lea     rdx, asc_180030900; "\b\n"
0x180070ebf  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070ec6  nop     dword ptr [rax+rax+00h]
0x180070ecb  test    eax, eax
  ... truncated ...
```
