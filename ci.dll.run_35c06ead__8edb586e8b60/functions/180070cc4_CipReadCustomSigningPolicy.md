# CipReadCustomSigningPolicy

- ea: `0x180070cc4`
- end: `0x180071281`
- name: `CipReadCustomSigningPolicy`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001db7c`

## callees

- `0x18002c0d0`
- `0x1800703e0`
- `0x180070cc4`
- `0x1800a7fc0`

## import_xrefs

- `ntoskrnl!_ultow_s` at `0x180070dd8`
- `ntoskrnl!_ultow_s` at `0x180070dd8`
- `ntoskrnl!RtlInitUnicodeString` at `0x180070df4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180070df4`
- `ntoskrnl!ExAllocatePool2` at `0x180070d94`
- `ntoskrnl!ExAllocatePool2` at `0x180070d94`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070fa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071252`
- `ntoskrnl!ExFreePoolWithTag` at `0x180070fa8`
- `ntoskrnl!ExFreePoolWithTag` at `0x180071252`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070d66`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070e23`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070eb1`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18007113f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18007119f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x1800711fb`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070d66`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070e23`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x180070eb1`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18007113f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x18007119f`
- `ntoskrnl!SeQuerySecureBootPolicyValue` at `0x1800711fb`

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
  if ( (int)SeQuerySecureBootPolicyValue(&qword_180030920, &qword_180030930, 2, &v30, 4, &v28) < 0 )
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
      g_CipCustomLevelComparisons = xmmword_180035EA0;
      xmmword_18004A4F0 = xmmword_180035EB0;
      xmmword_18004A500 = xmmword_180035EC0;
      xmmword_18004A510 = xmmword_180035ED0;
      while ( v16 < 0x13 )
      {
        v17 = v16;
        v18 = 12LL * v16;
        v19 = 2LL * v16;
        while ( v0 <= v15 )
        {
          v19 = 2LL * v16;
          SecureBootPolicyValue = CipAllocateAndQuerySecureBootPolicyValue(
                                    0x180000000LL + v19 * 8 + 198560,
                                    (unsigned int)&asc_180030950[8 * v0],
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
        v22 = *((unsigned __int8 *)&qword_180035DE0[8] + v16);
        v0 = 0;
        if ( (_BYTE)v22 )
        {
          v23 = SeQuerySecureBootPolicyValue(&qword_1800307A0[v19], &qword_180030900, 2, &v29, 4, &v28);
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
        if ( (int)SeQuerySecureBootPolicyValue(&qword_1800307A0[v19], L"\b\n", 2, &v27, 4, &v28) >= 0 )
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
      v25 = SeQuerySecureBootPolicyValue(&qword_180030790, L"&(", 2, &v29, 4, &v28);
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
           (unsigned int)&qword_1800309A0,
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
0x180070cc4  push    rbp
0x180070cc6  push    rbx
0x180070cc7  push    rsi
0x180070cc8  push    rdi
0x180070cc9  push    r12
0x180070ccb  push    r13
0x180070ccd  push    r14
0x180070ccf  push    r15
0x180070cd1  lea     rbp, [rsp-1Fh]
0x180070cd6  sub     rsp, 0A8h
0x180070cdd  mov     rax, cs:__security_cookie
0x180070ce4  xor     rax, rsp
0x180070ce7  mov     [rbp+57h+var_48], rax
0x180070ceb  movups  xmm1, xmmword ptr cs:aCiSigners; "CI\\Signers\\"
0x180070cf2  xor     r12d, r12d
0x180070cf5  lea     r9, [rbp+57h+var_A4]
0x180070cf9  xor     eax, eax
0x180070cfb  mov     [rbp+57h+P], r12
0x180070cff  xorps   xmm0, xmm0
0x180070d02  mov     [rbp+57h+var_50], rax
0x180070d06  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180070d0a  lea     rax, [rbp+57h+var_AC]
0x180070d0e  mov     [rbp+57h+var_94], r12d
0x180070d12  movsd   xmm0, qword ptr cs:aCiSigners+10h; "rs\\"
0x180070d1a  lea     edi, [r12+2]
0x180070d1f  mov     [rsp+0E0h+var_B8], rax
0x180070d24  lea     rdx, qword_180030930
0x180070d2b  mov     r8d, edi
0x180070d2e  mov     [rbp+57h+var_B0], r12d
0x180070d32  lea     rcx, qword_180030920
0x180070d39  mov     [rbp+57h+var_98], r12d
0x180070d3d  mov     [rbp+57h+var_9C], r12d
0x180070d41  mov     [rbp+57h+var_A8], r12d
0x180070d45  movups  xmmword ptr [rbp+57h+SourceString], xmm1
0x180070d49  mov     [rbp+57h+var_A4], r12d
0x180070d4d  movsd   qword ptr [rbp+57h+DstBuf], xmm0
0x180070d52  mov     [rbp+57h+var_80], r12
0x180070d56  mov     [rbp+57h+var_A0], r12d
0x180070d5a  mov     [rbp+57h+var_AC], r12d
0x180070d5e  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070d66  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070d6d  nop     dword ptr [rax+rax+00h]
0x180070d72  test    eax, eax
0x180070d74  jns     short loc_180070D7E
0x180070d76  mov     ebx, r12d
0x180070d79  jmp     loc_18007125E
0x180070d7e  mov     eax, [rbp+57h+var_A4]
0x180070d81  mov     ecx, 102h
0x180070d86  mov     r8d, 63734943h
0x180070d8c  lea     rdx, [rax+rax*4]
0x180070d90  shl     rdx, 3
0x180070d94  call    cs:__imp_ExAllocatePool2
0x180070d9b  nop     dword ptr [rax+rax+00h]
0x180070da0  mov     [rbp+57h+var_90], rax
0x180070da4  mov     r15, rax
0x180070da7  test    rax, rax
0x180070daa  jnz     short loc_180070DB6
0x180070dac  mov     ebx, 0C0000017h
0x180070db1  jmp     loc_18007125E
0x180070db6  mov     esi, r12d
0x180070db9  mov     r13d, 0C0000034h
0x180070dbf  cmp     esi, [rbp+57h+var_A4]
0x180070dc2  jnb     loc_180070FC9
0x180070dc8  mov     r9d, 0Ah; Radix
0x180070dce  lea     rdx, [rbp+57h+DstBuf+6]; DstBuf
0x180070dd2  mov     ecx, esi; Val
0x180070dd4  lea     r8d, [r9-5]; SizeInWords
0x180070dd8  call    cs:__imp__ultow_s
0x180070ddf  nop     dword ptr [rax+rax+00h]
0x180070de4  test    eax, eax
0x180070de6  jnz     loc_180070FBF
0x180070dec  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180070df0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180070df4  call    cs:__imp_RtlInitUnicodeString
0x180070dfb  nop     dword ptr [rax+rax+00h]
0x180070e00  lea     rax, [rbp+57h+var_AC]
0x180070e04  mov     r8d, edi
0x180070e07  mov     [rsp+0E0h+var_B8], rax
0x180070e0c  lea     r9, [rbp+57h+var_9C]
0x180070e10  lea     rdx, qword_1800308F0
0x180070e17  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070e1f  lea     rcx, [rbp+57h+DestinationString]
0x180070e23  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070e2a  nop     dword ptr [rax+rax+00h]
0x180070e2f  test    eax, eax
0x180070e31  js      short loc_180070E50
0x180070e33  mov     ecx, [rbp+57h+var_9C]
0x180070e36  test    ecx, ecx
0x180070e38  jz      short loc_180070E50
0x180070e3a  mov     r14d, esi
0x180070e3d  lea     rax, [r14+r14*4]
0x180070e41  lea     rdi, [r15+rax*8]
0x180070e45  mov     [rdi], ecx
0x180070e47  mov     [rdi+8], r12d
0x180070e4b  jmp     loc_180070EF5
0x180070e50  mov     r14d, esi
0x180070e53  lea     rdx, qword_1800309A0
0x180070e5a  mov     r8d, 0Ah
0x180070e60  lea     rcx, [rbp+57h+DestinationString]
0x180070e64  lea     rax, [r14+r14*4]
0x180070e68  lea     rdi, [r15+rax*8]
0x180070e6c  mov     [rdi], r12d
0x180070e6f  lea     r9, [rdi+10h]
0x180070e73  lea     r12, [rdi+8]
0x180070e77  mov     [rsp+0E0h+var_C0], r12
0x180070e7c  call    CipAllocateAndQuerySecureBootPolicyValue
0x180070e81  mov     ebx, eax
0x180070e83  test    eax, eax
0x180070e85  js      loc_180070FB6
0x180070e8b  lea     rax, [rbp+57h+var_AC]
0x180070e8f  mov     r8d, 2
0x180070e95  mov     [rsp+0E0h+var_B8], rax
0x180070e9a  lea     r9, [rbp+57h+var_B0]
0x180070e9e  lea     rdx, asc_1800308E0; "\b\n"
0x180070ea5  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180070ead  lea     rcx, [rbp+57h+DestinationString]
0x180070eb1  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180070eb8  nop     dword ptr [rax+rax+00h]
0x180070ebd  test    eax, eax
0x180070ebf  jns     short loc_180070ECB
0x180070ec1  mov     eax, 800Ch
0x180070ec6  mov     [rbp+57h+var_B0], eax
0x180070ec9  jmp     short loc_180070ECE
0x180070ecb  mov     eax, [rbp+57h+var_B0]
0x180070ece  mov     [rdi+4], eax
0x180070ed1  lea     rdx, [rbp+57h+var_98]
0x180070ed5  mov     ecx, [rbp+57h+var_B0]
0x180070ed8  call    HashKGetHashLength
0x180070edd  test    eax, eax
0x180070edf  js      loc_180070FBF
0x180070ee5  mov     eax, [r12]
0x180070ee9  cmp     [rbp+57h+var_98], eax
0x180070eec  jnz     loc_180070FBF
0x180070ef2  xor     r12d, r12d
0x180070ef5  lea     rax, [rbp+57h+var_94]
0x180070ef9  mov     r8d, 0Ah
0x180070eff  lea     r9, [rbp+57h+P]
0x180070f03  mov     [rsp+0E0h+var_C0], rax
0x180070f08  lea     rdx, asc_1800309B0; "\b\n"
0x180070f0f  lea     rcx, [rbp+57h+DestinationString]
0x180070f13  call    CipAllocateAndQuerySecureBootPolicyValue
0x180070f18  mov     ebx, eax
0x180070f1a  test    eax, eax
0x180070f1c  jns     short loc_180070F2C
0x180070f1e  cmp     eax, r13d
0x180070f21  jnz     loc_18007124A
0x180070f27  mov     edx, r12d
0x180070f2a  jmp     short loc_180070F91
0x180070f2c  mov     ebx, [rbp+57h+var_94]
0x180070f2f  mov     ecx, ebx
0x180070f31  mov     r10, [rbp+57h+P]
0x180070f35  test    ebx, ebx
0x180070f37  jz      short loc_180070FA0
0x180070f39  movzx   r11d, byte ptr [r10]
0x180070f3d  mov     r8, r10
0x180070f40  test    r11d, r11d
0x180070f43  jz      short loc_180070FA0
0x180070f45  dec     ecx
0x180070f47  mov     edx, r12d
0x180070f4a  inc     r8
0x180070f4d  test    ecx, ecx
0x180070f4f  jz      short loc_180070F72
0x180070f51  movzx   r9d, byte ptr [r8]
0x180070f55  lea     eax, [r9-1]
0x180070f59  cmp     eax, 7Eh ; '~'
0x180070f5c  ja      short loc_180070FA0
0x180070f5e  dec     ecx
0x180070f60  cmp     r9d, ecx
0x180070f63  ja      short loc_180070FA0
0x180070f65  inc     edx
0x180070f67  sub     ecx, r9d
0x180070f6a  inc     r8
0x180070f6d  add     r8, r9
0x180070f70  jmp     short loc_180070F4D
0x180070f72  cmp     edx, r11d
0x180070f75  jnz     short loc_180070FA0
0x180070f77  test    edx, edx
0x180070f79  jz      short loc_180070FA0
0x180070f7b  lea     rax, [r14+r14*4]
0x180070f7f  lea     rdi, [r15+rax*8]
0x180070f83  lea     eax, [rbx-1]
0x180070f86  mov     [rdi+1Ch], eax
0x180070f89  lea     rax, [r10+1]
0x180070f8d  mov     [rdi+20h], rax
0x180070f91  mov     [rdi+18h], edx
0x180070f94  inc     esi
0x180070f96  mov     edi, 2
0x180070f9b  jmp     loc_180070DBF
0x180070fa0  mov     edx, 63734943h; Tag
0x180070fa5  mov     rcx, r10; P
0x180070fa8  call    cs:__imp_ExFreePoolWithTag
0x180070faf  nop     dword ptr [rax+rax+00h]
0x180070fb4  jmp     short loc_180070FBF
0x180070fb6  cmp     eax, r13d
0x180070fb9  jnz     loc_18007124A
0x180070fbf  mov     ebx, 0C0430003h
0x180070fc4  jmp     loc_18007124A
0x180070fc9  mov     eax, cs:g_CiOptions
0x180070fcf  test    al, 8
0x180070fd1  jz      short loc_180070FDD
0x180070fd3  mov     cs:g_CiSignerTypeMax, edi
0x180070fd9  mov     esi, edi
0x180070fdb  jmp     short loc_180070FF1
0x180070fdd  movzx   esi, byte ptr cs:g_CiDeveloperMode
0x180070fe4  shr     esi, 2
0x180070fe7  and     esi, 1
0x180070fea  mov     cs:g_CiSignerTypeMax, r12d
0x180070ff1  movaps  xmm0, cs:xmmword_180035EA0
0x180070ff8  lea     rbx, cs:180000000h
0x180070fff  movaps  xmm1, cs:xmmword_180035EB0
0x180071006  mov     r13d, r12d
0x180071009  movups  cs:g_CipCustomLevelComparisons, xmm0
0x180071010  movaps  xmm0, cs:xmmword_180035EC0
0x180071017  movups  cs:xmmword_18004A4F0, xmm1
0x18007101e  movaps  xmm1, cs:xmmword_180035ED0
0x180071025  movups  cs:xmmword_18004A500, xmm0
0x18007102c  movups  cs:xmmword_18004A510, xmm1
0x180071033  cmp     r13d, 13h
0x180071037  jnb     loc_1800711D2
0x18007103d  mov     edi, r13d
0x180071040  mov     r15d, r13d
0x180071043  lea     r14, [rdi+rdi*2]
0x180071047  shl     r14, 2
0x18007104b  shl     r15, 4
0x18007104f  cmp     r12d, esi
0x180071052  jg      loc_180071103
0x180071058  lea     rax, asc_180030950; "\"$"
0x18007105f  movsxd  rdx, r12d
0x180071062  shl     rdx, 4
0x180071066  lea     r9, [rbp+57h+var_80]
0x18007106a  add     rdx, rax
0x18007106d  mov     r15, rdi
0x180071070  lea     rax, [rbp+57h+var_A0]
0x180071074  shl     r15, 4
0x180071078  mov     r8d, 4
0x18007107e  mov     [rsp+0E0h+var_C0], rax
0x180071083  lea     rcx, [r15+307A0h]
0x18007108a  add     rcx, rbx
0x18007108d  call    CipAllocateAndQuerySecureBootPolicyValue
0x180071092  mov     ebx, eax
0x180071094  test    eax, eax
0x180071096  js      short loc_1800710D8
0x180071098  mov     edx, [rbp+57h+var_A0]
0x18007109b  lea     rax, [rdi+rdi*2]
0x18007109f  shr     edx, 2
0x1800710a2  lea     rbx, cs:180000000h
0x1800710a9  movsxd  r8, r12d
0x1800710ac  lea     r14, [rdi+rdi*2]
0x1800710b0  mov     [rbp+57h+var_A0], edx
0x1800710b3  shl     r14, 2
0x1800710b7  lea     rcx, [r8+rax*2]
0x1800710bb  mov     rax, [rbp+57h+var_80]
0x1800710bf  mov     rva qword_180049A98[rbx+rcx*8], rax
0x1800710c7  lea     rax, [rdi+rdi*2]
0x1800710cb  lea     rcx, [r8+rax*4]
0x1800710cf  mov     rva dword_180049AB0[rbx+rcx*4], edx
0x1800710d6  jmp     short loc_1800710FB
0x1800710d8  cmp     eax, 0C0000034h
0x1800710dd  jnz     loc_180071246
0x1800710e3  movsxd  rax, r12d
0x1800710e6  lea     rbx, cs:180000000h
0x1800710ed  add     rax, r14
0x1800710f0  mov     rva dword_180049AB0[rbx+rax*4], 0
0x1800710fb  inc     r12d
0x1800710fe  jmp     loc_18007104F
0x180071103  movzx   r14d, byte ptr [rdi+rbx+35E20h]
0x18007110c  xor     r12d, r12d
0x18007110f  test    r14b, r14b
0x180071112  jz      short loc_180071173
0x180071114  lea     rax, [rbp+57h+var_AC]
0x180071118  mov     [rsp+0E0h+var_B8], rax
0x18007111d  lea     rcx, rva qword_1800307A0[rbx]
0x180071124  add     rcx, r15
0x180071127  mov     dword ptr [rsp+0E0h+var_C0], 4
0x18007112f  lea     r9, [rbp+57h+var_A8]
0x180071133  lea     r8d, [r12+2]
0x180071138  lea     rdx, qword_180030900
0x18007113f  call    cs:__imp_SeQuerySecureBootPolicyValue
0x180071146  nop     dword ptr [rax+rax+00h]
0x18007114b  mov     ebx, eax
0x18007114d  test    eax, eax
0x18007114f  js      short loc_180071161
0x180071151  mov     eax, [rbp+57h+var_A8]
0x180071154  lea     rdx, g_CipCustomLevelComparisons
0x18007115b  mov     [rdx+r14*4], eax
0x18007115f  jmp     short loc_18007116C
0x180071161  cmp     eax, 0C0000034h
0x180071166  jnz     loc_180071246
0x18007116c  lea     rbx, cs:180000000h
0x180071173  lea     rax, [rbp+57h+var_AC]
0x180071177  mov     r8d, 2
0x18007117d  mov     [rsp+0E0h+var_B8], rax
0x180071182  lea     rcx, rva qword_1800307A0[rbx]
0x180071189  add     rcx, r15
0x18007118c  mov     dword ptr [rsp+0E0h+var_C0], 4
0x180071194  lea     r9, [rbp+57h+var_B0]
0x180071198  lea     rdx, asc_1800308E0; "\b\n"
0x18007119f  call    cs:__imp_SeQuerySecureBootPolicyValue
0x1800711a6  nop     dword ptr [rax+rax+00h]
0x1800711ab  test    eax, eax
  ... truncated ...
```
