# AslFileAllocAndGetAttributes

- ea: `0x18000d258`
- end: `0x18000d77f`
- name: `AslFileAllocAndGetAttributes`
- size: `1319`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1800039c8`
- `0x18000d824`

## callees

- `0x18000d258`
- `0x18000dcf4`
- `0x18000e240`
- `0x18000f980`
- `0x18000fd14`
- `0x1800101d4`
- `0x180010354`
- `0x1800103dc`
- `0x18001057c`
- `0x180010c48`
- `0x180010d10`
- `0x180011d78`
- `0x180011f2c`
- `0x18001378c`

## pseudocode

```c
__int64 __fastcall AslFileAllocAndGetAttributes(__int64 a1, __int64 a2, unsigned __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  int v6; // ecx
  __int64 i; // r8
  __int64 v8; // rax
  int v9; // edx
  unsigned int v10; // ebx
  bool v12; // zf
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  bool v16; // zf
  int v17; // ecx
  int ChecksumAttributes; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  const char *v21; // r9
  __int64 v22; // r8
  int v23; // ebp
  int VersionAttributes; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  int IsArm64XBinary; // eax
  __int64 v28; // rax
  __int64 v29; // [rsp+20h] [rbp-38h]
  unsigned __int64 v30; // [rsp+70h] [rbp+18h] BYREF

  v30 = a3;
  v4 = a2;
  if ( *(_DWORD *)(a2 + 56) == 1 )
  {
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      v8 = 32 * i;
      if ( !v6 || v6 == 17 )
        break;
      v9 = *(_DWORD *)(v8 + a1 + 24);
      if ( v6 == 28 )
      {
        *(_QWORD *)(v8 + a1 + 16) = 1;
        *(_DWORD *)(v8 + a1 + 24) = v9 | 1;
LABEL_9:
        *(_DWORD *)(v8 + a1) = 2;
        *(_QWORD *)(v8 + a1 + 8) = 4;
        goto LABEL_10;
      }
      *(_DWORD *)(v8 + a1 + 24) = v9 | 2;
LABEL_10:
      if ( ++v6 >= 36 )
        return 0;
    }
    *(_DWORD *)(v8 + a1 + 24) |= 1u;
    *(_QWORD *)(v8 + a1 + 16) = 0;
    goto LABEL_9;
  }
  if ( *(_DWORD *)(a2 + 72) )
  {
    LODWORD(a2) = 0;
    do
    {
      if ( (unsigned int)a2 > 0x10 )
      {
        if ( (unsigned int)a2 > 0x1C )
        {
          if ( (_DWORD)a2 != 29 && (_DWORD)a2 != 30 && (_DWORD)a2 != 31 )
          {
            v17 = a2 - 33;
            v16 = (_DWORD)a2 == 33;
            goto LABEL_36;
          }
        }
        else if ( (_DWORD)a2 != 28 && (_DWORD)a2 != 17 && (_DWORD)a2 != 18 && (_DWORD)a2 != 19 )
        {
          v17 = a2 - 22;
          v16 = (_DWORD)a2 == 22;
          goto LABEL_36;
        }
      }
      else if ( (_DWORD)a2 != 16 )
      {
        if ( (unsigned int)a2 > 9 )
        {
          v12 = (_DWORD)a2 == 10;
          v13 = a2 - 10;
        }
        else
        {
          if ( (_DWORD)a2 == 9 || (_DWORD)a2 == 1 )
            goto LABEL_39;
          v13 = a2 - 3;
          v12 = (_DWORD)a2 == 3;
        }
        if ( !v12 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v17 = v15 - 1;
              v16 = v17 == 0;
LABEL_36:
              if ( !v16 && (unsigned int)(v17 - 1) >= 2 )
                *(_DWORD *)(32LL * (unsigned int)a2 + a1 + 24) |= 2u;
            }
          }
        }
      }
LABEL_39:
      a2 = (unsigned int)(a2 + 1);
    }
    while ( (int)a2 < 36 );
  }
  ChecksumAttributes = AslFileMappingEnsure(v4, a2, a3, a4);
  v10 = ChecksumAttributes;
  if ( ChecksumAttributes == -1073741801 )
  {
    if ( !*(_DWORD *)(v4 + 72) )
    {
      ChecksumAttributes = AslpFileLargeEnsureLargeFileMapping(a1, v4);
      v10 = ChecksumAttributes;
      if ( ChecksumAttributes < 0 )
      {
        v21 = "AslpFileLargeEnsureLargeFileMapping failed [%x]";
        v22 = 599;
        goto LABEL_44;
      }
      goto LABEL_47;
    }
LABEL_46:
    v21 = "AslFileMappingEnsure failed [%x]";
    v22 = 603;
    goto LABEL_44;
  }
  if ( ChecksumAttributes < 0 )
    goto LABEL_46;
LABEL_47:
  v23 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( ((v30 >> v23) & 1) == 0 || (*(_BYTE *)(32LL * v23 + a1 + 24) & 3) != 0 )
          goto LABEL_110;
        if ( v23 > 18 )
          break;
        if ( v23 == 18 )
          goto LABEL_107;
        if ( v23 <= 9 )
        {
          if ( v23 == 9 )
            goto LABEL_62;
          if ( !v23 )
          {
LABEL_106:
            v26 = *(_QWORD *)(v4 + 24);
            *(_DWORD *)(a1 + 1048) |= 1u;
            *(_DWORD *)(a1 + 24) |= 1u;
            *(_QWORD *)(a1 + 16) = (unsigned int)v26;
            *(_DWORD *)(a1 + 1024) = 3;
            *(_QWORD *)(a1 + 1032) = 8;
            *(_QWORD *)(a1 + 1040) = v26;
            *(_DWORD *)a1 = 2;
            *(_QWORD *)(a1 + 8) = 4;
            goto LABEL_110;
          }
          if ( v23 != 1 )
          {
            if ( v23 != 2 )
            {
              if ( v23 != 3 && v23 != 4 && v23 != 5 && v23 != 6 && (unsigned int)(v23 - 7) > 1 )
                return (unsigned int)-1073741595;
LABEL_62:
              VersionAttributes = AslpFileGetVersionAttributes(a1, v4);
              if ( VersionAttributes <= -1073741688 || (unsigned int)(VersionAttributes + 1073741684) <= 0x3FFFFF73 )
                AslLogCallPrintf(
                  1,
                  "AslFileAllocAndGetAttributes",
                  666,
                  "AslpFileGetVersionAttributes failed [%x]",
                  VersionAttributes);
              goto LABEL_110;
            }
LABEL_104:
            ChecksumAttributes = AslpFileGetChecksumAttributes(a1, v4);
            v10 = ChecksumAttributes;
            if ( ChecksumAttributes < 0 )
            {
              v21 = "AslpFileGetChecksumAttributes failed [%x]";
              v22 = 786;
              goto LABEL_44;
            }
            goto LABEL_110;
          }
          goto LABEL_107;
        }
        if ( v23 == 10 || v23 == 11 || v23 == 12 || v23 == 13 || v23 == 14 || v23 == 15 || v23 == 16 )
          goto LABEL_62;
        switch ( *(_DWORD *)(v4 + 56) )
        {
          case 4:
            v25 = 1;
            break;
          case 5:
            v25 = 2;
            break;
          case 6:
            v25 = 3;
            break;
          default:
            v25 = 0;
            break;
        }
        *(_DWORD *)(a1 + 568) |= 1u;
        ++v23;
        *(_DWORD *)(a1 + 544) = 2;
        *(_QWORD *)(a1 + 552) = 4;
        *(_QWORD *)(a1 + 560) = v25;
      }
      if ( v23 > 27 )
        break;
      switch ( v23 )
      {
        case 27:
          ChecksumAttributes = AslpFileGetClrVersionAttribute(a1, v4);
          v10 = ChecksumAttributes;
          if ( ChecksumAttributes < 0 )
          {
            v21 = "AslpFileGetClrVersionAttribute failed [%x]";
            v22 = 765;
            goto LABEL_44;
          }
          break;
        case 19:
          goto LABEL_107;
        case 20:
        case 21:
          ChecksumAttributes = AslpFileGetHeaderAttributesNE(a1, v4, v19, v20);
          v10 = ChecksumAttributes;
          if ( ChecksumAttributes < 0 )
          {
            v21 = "AslpFileGetHeaderAttributesNE failed [%x]";
            v22 = 775;
            goto LABEL_44;
          }
          goto LABEL_110;
        case 22:
          goto LABEL_107;
        case 23:
          ChecksumAttributes = AslpFileGetPeExportNameAttribute(a1, v4, v19, v20);
          v10 = ChecksumAttributes;
          if ( ChecksumAttributes < 0 )
          {
            v21 = "AslpFileGetPeExportNameAttribute failed [%x]";
            v22 = 756;
            goto LABEL_44;
          }
          break;
        case 24:
          goto LABEL_62;
        case 25:
          ChecksumAttributes = AslpFileGetExeWrapperAttribute(a1, v4);
          v10 = ChecksumAttributes;
          if ( ChecksumAttributes < 0 )
          {
            v21 = "AslpFileGetExeWrapperAttribute failed [%x]";
            v22 = 747;
            goto LABEL_44;
          }
          break;
        default:
          goto LABEL_104;
      }
      ++v23;
    }
    if ( v23 == 28 )
      break;
    if ( v23 != 29 && v23 != 30 && v23 != 31 )
    {
      if ( v23 == 32 )
        goto LABEL_106;
      if ( v23 != 33 )
      {
        if ( v23 != 34 )
        {
          if ( v23 != 35 )
            return (unsigned int)-1073741595;
          if ( (unsigned int)Feature_Arm64XMatching__private_IsEnabledDeviceUsageNoInline() )
          {
            LOBYTE(v30) = 0;
            IsArm64XBinary = AslpFileIsArm64XBinary((bool *)&v30, v4);
            if ( IsArm64XBinary >= 0 )
            {
              v28 = (unsigned __int8)v30;
              *(_DWORD *)(a1 + 1144) |= 1u;
              *(_QWORD *)(a1 + 1136) = v28;
              *(_DWORD *)(a1 + 1120) = 0;
              *(_QWORD *)(a1 + 1128) = 1;
              return 0;
            }
            if ( IsArm64XBinary != -2147483614 )
              AslLogCallPrintf(
                1,
                "AslFileAllocAndGetAttributes",
                730,
                "AslpFileIsArm64XBinary failed [%x]",
                IsArm64XBinary);
          }
          *(_DWORD *)(a1 + 1144) |= 2u;
          return 0;
        }
        goto LABEL_104;
      }
    }
LABEL_107:
    ChecksumAttributes = AslpFileGetHeaderAttributesPE(a1, v4);
    v10 = ChecksumAttributes;
    if ( ChecksumAttributes < 0 )
    {
      v21 = "AslpFileGetHeaderAttributesPE failed [%x]";
      v22 = 710;
      goto LABEL_44;
    }
LABEL_110:
    if ( ++v23 >= 36 )
      return 0;
  }
  ChecksumAttributes = AslpFileGetFileKindDetailAttribute(a1, v4);
  v10 = ChecksumAttributes;
  if ( ChecksumAttributes >= 0 )
    goto LABEL_110;
  v21 = "AslpFileGetFileKindDetailAttribute failed [%x]";
  v22 = 694;
LABEL_44:
  LODWORD(v29) = ChecksumAttributes;
  AslLogCallPrintf(1, "AslFileAllocAndGetAttributes", v22, v21, v29);
  return v10;
}

```

## disassembly

```asm
0x18000d258  mov     [rsp+arg_0], rbx
0x18000d25d  mov     [rsp+arg_8], rbp
0x18000d262  mov     [rsp+arg_10], r8
0x18000d267  push    rdi
0x18000d268  push    r12
0x18000d26a  push    r13
0x18000d26c  push    r14
0x18000d26e  push    r15
0x18000d270  sub     rsp, 30h
0x18000d274  mov     ebp, 1
0x18000d279  mov     r15, rdx
0x18000d27c  mov     rdi, rcx
0x18000d27f  lea     r13d, [rbp+1]
0x18000d283  cmp     [rdx+38h], ebp
0x18000d286  jnz     short loc_18000D2FC
0x18000d288  xor     ecx, ecx
0x18000d28a  lea     r12d, [rbp+3]
0x18000d28e  xor     r8d, r8d
0x18000d291  mov     rax, r8
0x18000d294  shl     rax, 5
0x18000d298  test    ecx, ecx
0x18000d29a  jz      short loc_18000D2C0
0x18000d29c  cmp     ecx, 11h
0x18000d29f  jz      short loc_18000D2C0
0x18000d2a1  mov     edx, [rax+rdi+18h]
0x18000d2a5  cmp     ecx, 1Ch
0x18000d2a8  jz      short loc_18000D2B3
0x18000d2aa  or      edx, r13d
0x18000d2ad  mov     [rax+rdi+18h], edx
0x18000d2b1  jmp     short loc_18000D2D6
0x18000d2b3  or      edx, ebp
0x18000d2b5  mov     [rax+rdi+10h], rbp
0x18000d2ba  mov     [rax+rdi+18h], edx
0x18000d2be  jmp     short loc_18000D2CD
0x18000d2c0  or      [rax+rdi+18h], ebp
0x18000d2c4  mov     qword ptr [rax+rdi+10h], 0
0x18000d2cd  mov     [rax+rdi], r13d
0x18000d2d1  mov     [rax+rdi+8], r12
0x18000d2d6  add     ecx, ebp
0x18000d2d8  add     r8, rbp
0x18000d2db  cmp     ecx, 24h ; '$'
0x18000d2de  jl      short loc_18000D291
0x18000d2e0  xor     ebx, ebx
0x18000d2e2  mov     rbp, [rsp+58h+arg_8]
0x18000d2e7  mov     eax, ebx
0x18000d2e9  mov     rbx, [rsp+58h+arg_0]
0x18000d2ee  add     rsp, 30h
0x18000d2f2  pop     r15
0x18000d2f4  pop     r14
0x18000d2f6  pop     r13
0x18000d2f8  pop     r12
0x18000d2fa  pop     rdi
0x18000d2fb  retn
0x18000d2fc  cmp     dword ptr [rdx+48h], 0
0x18000d300  jz      short loc_18000D379
0x18000d302  xor     edx, edx
0x18000d304  cmp     edx, 10h
0x18000d307  ja      short loc_18000D330
0x18000d309  jz      short loc_18000D372
0x18000d30b  cmp     edx, 9
0x18000d30e  ja      short loc_18000D329
0x18000d310  jz      short loc_18000D372
0x18000d312  mov     ecx, edx
0x18000d314  sub     ecx, ebp
0x18000d316  jz      short loc_18000D372
0x18000d318  sub     ecx, r13d
0x18000d31b  jz      short loc_18000D372
0x18000d31d  sub     ecx, ebp
0x18000d31f  jz      short loc_18000D372
0x18000d321  sub     ecx, ebp
0x18000d323  jz      short loc_18000D372
0x18000d325  sub     ecx, ebp
0x18000d327  jmp     short loc_18000D35D
0x18000d329  mov     ecx, edx
0x18000d32b  sub     ecx, 0Ah
0x18000d32e  jmp     short loc_18000D31B
0x18000d330  cmp     edx, 1Ch
0x18000d333  ja      short loc_18000D34B
0x18000d335  jz      short loc_18000D372
0x18000d337  mov     ecx, edx
0x18000d339  sub     ecx, 11h
0x18000d33c  jz      short loc_18000D372
0x18000d33e  sub     ecx, ebp
0x18000d340  jz      short loc_18000D372
0x18000d342  sub     ecx, ebp
0x18000d344  jz      short loc_18000D372
0x18000d346  sub     ecx, 3
0x18000d349  jmp     short loc_18000D35D
0x18000d34b  mov     ecx, edx
0x18000d34d  sub     ecx, 1Dh
0x18000d350  jz      short loc_18000D372
0x18000d352  sub     ecx, ebp
0x18000d354  jz      short loc_18000D372
0x18000d356  sub     ecx, ebp
0x18000d358  jz      short loc_18000D372
0x18000d35a  sub     ecx, r13d
0x18000d35d  jz      short loc_18000D372
0x18000d35f  sub     ecx, ebp
0x18000d361  jz      short loc_18000D372
0x18000d363  cmp     ecx, ebp
0x18000d365  jz      short loc_18000D372
0x18000d367  mov     eax, edx
0x18000d369  shl     rax, 5
0x18000d36d  or      [rax+rdi+18h], r13d
0x18000d372  add     edx, ebp
0x18000d374  cmp     edx, 24h ; '$'
0x18000d377  jl      short loc_18000D304
0x18000d379  mov     rcx, r15
0x18000d37c  call    AslFileMappingEnsure
0x18000d381  mov     ebx, eax
0x18000d383  cmp     eax, 0C0000017h
0x18000d388  jnz     short loc_18000D3C6
0x18000d38a  cmp     dword ptr [r15+48h], 0
0x18000d38f  jnz     short loc_18000D3CA
0x18000d391  mov     rdx, r15
0x18000d394  mov     rcx, rdi
0x18000d397  call    AslpFileLargeEnsureLargeFileMapping
0x18000d39c  mov     ebx, eax
0x18000d39e  test    eax, eax
0x18000d3a0  jns     short loc_18000D3D9
0x18000d3a2  lea     r9, aAslpfilelargee_0; "AslpFileLargeEnsureLargeFileMapping fai"...
0x18000d3a9  mov     r8d, 257h
0x18000d3af  lea     rdx, aAslfileallocan; "AslFileAllocAndGetAttributes"
0x18000d3b6  mov     ecx, ebp
0x18000d3b8  mov     dword ptr [rsp+58h+var_38], eax
0x18000d3bc  call    AslLogCallPrintf
0x18000d3c1  jmp     loc_18000D2E2
0x18000d3c6  test    eax, eax
0x18000d3c8  jns     short loc_18000D3D9
0x18000d3ca  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x18000d3d1  mov     r8d, 25Bh
0x18000d3d7  jmp     short loc_18000D3AF
0x18000d3d9  xor     ebp, ebp
0x18000d3db  lea     r14, aAslfileallocan; "AslFileAllocAndGetAttributes"
0x18000d3e2  lea     r12d, [rbp+4]
0x18000d3e6  mov     rax, [rsp+58h+arg_10]
0x18000d3eb  mov     ecx, ebp
0x18000d3ed  shr     rax, cl
0x18000d3f0  test    al, 1
0x18000d3f2  jz      loc_18000D6B7
0x18000d3f8  movsxd  rax, ebp
0x18000d3fb  shl     rax, 5
0x18000d3ff  test    byte ptr [rax+rdi+18h], 3
0x18000d404  jnz     loc_18000D6B7
0x18000d40a  cmp     ebp, 12h
0x18000d40d  jg      loc_18000D51E
0x18000d413  jz      loc_18000D67F
0x18000d419  cmp     ebp, 9
0x18000d41c  jg      loc_18000D4A7
0x18000d422  jz      short loc_18000D460
0x18000d424  test    ebp, ebp
0x18000d426  jz      loc_18000D645
0x18000d42c  sub     ecx, 1
0x18000d42f  jz      loc_18000D67F
0x18000d435  sub     ecx, 1
0x18000d438  jz      loc_18000D61E
0x18000d43e  sub     ecx, 1
0x18000d441  jz      short loc_18000D460
0x18000d443  sub     ecx, 1
0x18000d446  jz      short loc_18000D460
0x18000d448  sub     ecx, 1
0x18000d44b  jz      short loc_18000D460
0x18000d44d  sub     ecx, 1
0x18000d450  jz      short loc_18000D460
0x18000d452  sub     ecx, 1
0x18000d455  jz      short loc_18000D460
0x18000d457  cmp     ecx, 1
0x18000d45a  jnz     loc_18000D6DE
0x18000d460  mov     rdx, r15
0x18000d463  mov     rcx, rdi
0x18000d466  call    AslpFileGetVersionAttributes
0x18000d46b  cmp     eax, 0C0000088h
0x18000d470  jle     short loc_18000D484
0x18000d472  lea     ecx, [rax+3FFFFF74h]
0x18000d478  cmp     ecx, 3FFFFF73h
0x18000d47e  ja      loc_18000D6B7
0x18000d484  lea     r9, aAslpfilegetver_5; "AslpFileGetVersionAttributes failed [%x"...
0x18000d48b  mov     dword ptr [rsp+58h+var_38], eax
0x18000d48f  mov     r8d, 29Ah
0x18000d495  mov     rdx, r14
0x18000d498  mov     ecx, 1
0x18000d49d  call    AslLogCallPrintf
0x18000d4a2  jmp     loc_18000D6B7
0x18000d4a7  sub     ecx, 0Ah
0x18000d4aa  jz      short loc_18000D460
0x18000d4ac  sub     ecx, 1
0x18000d4af  jz      short loc_18000D460
0x18000d4b1  sub     ecx, 1
0x18000d4b4  jz      short loc_18000D460
0x18000d4b6  sub     ecx, 1
0x18000d4b9  jz      short loc_18000D460
0x18000d4bb  sub     ecx, 1
0x18000d4be  jz      short loc_18000D460
0x18000d4c0  sub     ecx, 1
0x18000d4c3  jz      short loc_18000D460
0x18000d4c5  sub     ecx, 1
0x18000d4c8  jz      short loc_18000D460
0x18000d4ca  cmp     ecx, 1
0x18000d4cd  jnz     loc_18000D6DE
0x18000d4d3  mov     ecx, [r15+38h]
0x18000d4d7  sub     ecx, r12d
0x18000d4da  jz      short loc_18000D4F6
0x18000d4dc  sub     ecx, 1
0x18000d4df  jz      short loc_18000D4F1
0x18000d4e1  cmp     ecx, 1
0x18000d4e4  jz      short loc_18000D4EA
0x18000d4e6  xor     eax, eax
0x18000d4e8  jmp     short loc_18000D4FB
0x18000d4ea  mov     eax, 3
0x18000d4ef  jmp     short loc_18000D4FB
0x18000d4f1  mov     rax, r13
0x18000d4f4  jmp     short loc_18000D4FB
0x18000d4f6  mov     eax, 1
0x18000d4fb  or      dword ptr [rdi+238h], 1
0x18000d502  inc     ebp
0x18000d504  mov     [rdi+220h], r13d
0x18000d50b  mov     [rdi+228h], r12
0x18000d512  mov     [rdi+230h], rax
0x18000d519  jmp     loc_18000D3E6
0x18000d51e  cmp     ebp, 1Bh
0x18000d521  jg      loc_18000D5F3
0x18000d527  jz      loc_18000D5D0
0x18000d52d  sub     ecx, 13h
0x18000d530  jz      loc_18000D67F
0x18000d536  sub     ecx, 1
0x18000d539  jz      short loc_18000D5A9
0x18000d53b  sub     ecx, 1
0x18000d53e  jz      short loc_18000D5A9
0x18000d540  sub     ecx, 1
0x18000d543  jz      loc_18000D67F
0x18000d549  sub     ecx, 1
0x18000d54c  jz      short loc_18000D586
0x18000d54e  sub     ecx, 1
0x18000d551  jz      loc_18000D460
0x18000d557  sub     ecx, 1
0x18000d55a  jz      short loc_18000D56A
0x18000d55c  cmp     ecx, 1
0x18000d55f  jnz     loc_18000D6DE
0x18000d565  jmp     loc_18000D61E
0x18000d56a  mov     rdx, r15
0x18000d56d  mov     rcx, rdi
0x18000d570  call    AslpFileGetExeWrapperAttribute
0x18000d575  mov     ebx, eax
0x18000d577  test    eax, eax
0x18000d579  js      loc_18000D6C7
0x18000d57f  inc     ebp
0x18000d581  jmp     loc_18000D3E6
0x18000d586  mov     rdx, r15
0x18000d589  mov     rcx, rdi
0x18000d58c  call    AslpFileGetPeExportNameAttribute
0x18000d591  mov     ebx, eax
0x18000d593  test    eax, eax
0x18000d595  jns     short loc_18000D57F
0x18000d597  lea     r9, aAslpfilegetpee_0; "AslpFileGetPeExportNameAttribute failed"...
0x18000d59e  mov     r8d, 2F4h
0x18000d5a4  jmp     loc_18000D772
0x18000d5a9  mov     rdx, r15
0x18000d5ac  mov     rcx, rdi
0x18000d5af  call    AslpFileGetHeaderAttributesNE
0x18000d5b4  mov     ebx, eax
0x18000d5b6  test    eax, eax
0x18000d5b8  jns     loc_18000D6B7
0x18000d5be  lea     r9, aAslpfilegethea; "AslpFileGetHeaderAttributesNE failed [%"...
0x18000d5c5  mov     r8d, 307h
0x18000d5cb  jmp     loc_18000D772
0x18000d5d0  mov     rdx, r15
0x18000d5d3  mov     rcx, rdi
0x18000d5d6  call    AslpFileGetClrVersionAttribute
0x18000d5db  mov     ebx, eax
0x18000d5dd  test    eax, eax
0x18000d5df  jns     short loc_18000D57F
0x18000d5e1  lea     r9, aAslpfilegetclr_0; "AslpFileGetClrVersionAttribute failed ["...
0x18000d5e8  mov     r8d, 2FDh
0x18000d5ee  jmp     loc_18000D772
0x18000d5f3  sub     ecx, 1Ch
0x18000d5f6  jz      loc_18000D6A2
0x18000d5fc  sub     ecx, 1
0x18000d5ff  jz      short loc_18000D67F
0x18000d601  sub     ecx, 1
0x18000d604  jz      short loc_18000D67F
0x18000d606  sub     ecx, 1
0x18000d609  jz      short loc_18000D67F
0x18000d60b  sub     ecx, 1
0x18000d60e  jz      short loc_18000D645
0x18000d610  sub     ecx, 1
0x18000d613  jz      short loc_18000D67F
0x18000d615  sub     ecx, 1
0x18000d618  jnz     loc_18000D6D9
0x18000d61e  mov     rdx, r15
0x18000d621  mov     rcx, rdi
0x18000d624  call    AslpFileGetChecksumAttributes
0x18000d629  mov     ebx, eax
0x18000d62b  test    eax, eax
0x18000d62d  jns     loc_18000D6B7
0x18000d633  lea     r9, aAslpfilegetche_2; "AslpFileGetChecksumAttributes failed [%"...
0x18000d63a  mov     r8d, 312h
0x18000d640  jmp     loc_18000D772
0x18000d645  mov     rax, [r15+18h]
0x18000d649  or      dword ptr [rdi+418h], 1
0x18000d650  or      dword ptr [rdi+18h], 1
  ... truncated ...
```
