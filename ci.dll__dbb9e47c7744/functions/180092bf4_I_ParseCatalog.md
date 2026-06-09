# I_ParseCatalog

- ea: `0x180092bf4`
- end: `0x180092ec1`
- name: `I_ParseCatalog`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180092a04`

## callees

- `0x18000cf74`
- `0x180010094`
- `0x18002c8a0`
- `0x18008ed10`
- `0x18008f458`
- `0x18009261c`
- `0x1800928ec`
- `0x180092bf4`
- `0x180092ec8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x180092e63`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180092e63`
- `ntoskrnl!ExAllocatePool2` at `0x180092e28`
- `ntoskrnl!ExAllocatePool2` at `0x180092e28`
- `ntoskrnl!RtlCompareMemory` at `0x180092ca5`
- `ntoskrnl!RtlCompareMemory` at `0x180092ca5`

## pseudocode

```c
__int64 __fastcall I_ParseCatalog(__int64 a1, __int64 a2, int a3, int a4, __int64 a5)
{
  __int64 v7; // rsi
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 *v10; // rax
  int NamedCatalogAttributeValue; // ebx
  __int64 *i; // rbx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // dx
  __int64 Pool2; // rax
  __int64 v19; // [rsp+60h] [rbp-58h] BYREF
  WCHAR *v20; // [rsp+68h] [rbp-50h]
  UNICODE_STRING SourceString; // [rsp+70h] [rbp-48h] BYREF

  v7 = a2 + 32;
  LODWORD(v20) = 0;
  v19 = 0;
  SourceString = 0;
  v8 = a1 + 72;
  v9 = a1 + 120;
  v10 = qword_18002E530;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v10 = (__int64 *)&qword_18002E5B0;
  NamedCatalogAttributeValue = MinCrypK_VerifySignedDataKModeEx(
                                 a3,
                                 a4,
                                 0,
                                 0,
                                 (__int64)v10,
                                 v8,
                                 (void *)(a2 + 32),
                                 a1 + 168,
                                 v9);
  if ( NamedCatalogAttributeValue >= 0 )
  {
    if ( *(_DWORD *)v7 == 9
      && RtlCompareMemory(qword_180034DA0, *(const void **)(v7 + 8), 9u) == 9
      && (int)MinAsn1ParseCTL(v7 + 16, a2 + 112) >= 0 )
    {
      for ( i = &qword_1800304C0; *(_DWORD *)i; i += 4 )
      {
        v13 = *((_DWORD *)i + 4);
        if ( v13 == *(_DWORD *)(a2 + 240) && !memcmp((const void *)i[1], *(const void **)(a2 + 248), v13) )
        {
          *(_QWORD *)(a1 + 176) = i;
          if ( (unsigned __int8)MinAsn1FindExtensionMatchingValue(v15, v14, a2 + 272) )
            *(_DWORD *)(a1 + 64) |= 1u;
          NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_1800304A0, &v19);
          if ( NamedCatalogAttributeValue < 0 )
          {
            if ( NamedCatalogAttributeValue == -1073741275 )
              NamedCatalogAttributeValue = 0;
          }
          else
          {
            NamedCatalogAttributeValue = CipSetPlatformManifestFromPackageName(v8, &v19);
            if ( NamedCatalogAttributeValue < 0 )
              return (unsigned int)NamedCatalogAttributeValue;
          }
          if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
          {
            if ( NamedCatalogAttributeValue < 0 )
              return (unsigned int)NamedCatalogAttributeValue;
            NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_180030490, &v19);
            if ( NamedCatalogAttributeValue < 0 )
            {
              if ( NamedCatalogAttributeValue == -1073741275 )
                NamedCatalogAttributeValue = 0;
            }
            else
            {
              v16 = v19;
              if ( (unsigned int)v19 < 2 )
                return (unsigned int)-1073741275;
              if ( (unsigned int)v19 > 0xFFFF )
                return (unsigned int)-1073741811;
              SourceString.MaximumLength = v19;
              SourceString.Length = v19;
              SourceString.Buffer = v20;
              if ( !v20[((unsigned __int64)(unsigned int)v19 >> 1) - 1] )
              {
                v16 = v19 - 2;
                SourceString.Length = v19 - 2;
              }
              Pool2 = ExAllocatePool2(258, v16, 1668499779);
              *(_QWORD *)(a1 + 264) = Pool2;
              if ( !Pool2 )
                return (unsigned int)-1073741801;
              *(_WORD *)(a1 + 258) = SourceString.Length;
              *(_WORD *)(a1 + 256) = 0;
              RtlCopyUnicodeString((PUNICODE_STRING)(a1 + 256), &SourceString);
            }
            if ( NamedCatalogAttributeValue < 0 )
              return (unsigned int)NamedCatalogAttributeValue;
          }
          if ( (int)MinAsn1ExtractContent(*(_QWORD *)(a2 + 264), *(unsigned int *)(a2 + 256), a5, a5 + 8) >= 0 )
            return (unsigned int)NamedCatalogAttributeValue;
          break;
        }
      }
    }
    return (unsigned int)-1073740760;
  }
  return (unsigned int)NamedCatalogAttributeValue;
}

```

## disassembly

```asm
0x180092bf4  push    rbx
0x180092bf6  push    rsi
0x180092bf7  push    rdi
0x180092bf8  push    r12
0x180092bfa  push    r13
0x180092bfc  push    r14
0x180092bfe  push    r15
0x180092c00  sub     rsp, 80h
0x180092c07  mov     r10d, r9d
0x180092c0a  mov     r11, r8
0x180092c0d  mov     r13, rdx
0x180092c10  mov     rdi, rcx
0x180092c13  lea     rsi, [rdx+20h]
0x180092c17  xor     eax, eax
0x180092c19  mov     [rsp+0B8h+var_58+4], rax
0x180092c1e  mov     [rsp+0B8h+var_58], rax
0x180092c23  xorps   xmm0, xmm0
0x180092c26  movups  xmmword ptr [rsp+0B8h+SourceString.Length], xmm0
0x180092c2b  lea     r12, [rcx+48h]
0x180092c2f  add     rcx, 78h ; 'x'
0x180092c33  lea     rdx, [rdi+0A8h]
0x180092c3a  test    byte ptr cs:g_CiPolicyState+2, 1
0x180092c41  lea     r8, qword_18002E5B0
0x180092c48  lea     rax, qword_18002E530
0x180092c4f  cmovz   rax, r8
0x180092c53  mov     [rsp+0B8h+var_78], rcx; __int64
0x180092c58  mov     [rsp+0B8h+var_80], rdx; __int64
0x180092c5d  mov     [rsp+0B8h+var_88], rsi; void *
0x180092c62  mov     qword ptr [rsp+0B8h+var_90], r12; int
0x180092c67  mov     [rsp+0B8h+var_98], rax; __int64
0x180092c6c  xor     r9d, r9d; int
0x180092c6f  xor     r8d, r8d; int
0x180092c72  mov     edx, r10d; int
0x180092c75  mov     rcx, r11; int
0x180092c78  call    MinCrypK_VerifySignedDataKModeEx
0x180092c7d  mov     ebx, eax
0x180092c7f  mov     [rsp+0B8h+var_68], eax
0x180092c83  test    eax, eax
0x180092c85  js      loc_180092EAB
0x180092c8b  cmp     dword ptr [rsi], 9
0x180092c8e  jnz     loc_180092EA2
0x180092c94  mov     r8d, 9; Length
0x180092c9a  mov     rdx, [rsi+8]; Source2
0x180092c9e  lea     rcx, qword_180034DA0; Source1
0x180092ca5  call    cs:__imp_RtlCompareMemory
0x180092cac  nop     dword ptr [rax+rax+00h]
0x180092cb1  cmp     rax, 9
0x180092cb5  jnz     loc_180092EA2
0x180092cbb  lea     rcx, [rsi+10h]
0x180092cbf  lea     rdx, [r13+70h]
0x180092cc3  call    MinAsn1ParseCTL
0x180092cc8  test    eax, eax
0x180092cca  js      loc_180092EA2
0x180092cd0  lea     rbx, qword_1800304C0
0x180092cd7  mov     [rsp+0B8h+var_60], rbx
0x180092cdc  mov     esi, [rbx]
0x180092cde  test    esi, esi
0x180092ce0  jz      loc_180092EA2
0x180092ce6  mov     eax, [rbx+10h]
0x180092ce9  cmp     eax, [r13+0F0h]
0x180092cf0  jnz     short loc_180092D09
0x180092cf2  mov     r8d, eax; Size
0x180092cf5  mov     rdx, [r13+0F8h]; Buf2
0x180092cfc  mov     rcx, [rbx+8]; Buf1
0x180092d00  call    memcmp
0x180092d05  test    eax, eax
0x180092d07  jz      short loc_180092D0F
0x180092d09  add     rbx, 20h ; ' '
0x180092d0d  jmp     short loc_180092CD7
0x180092d0f  test    esi, esi
0x180092d11  jz      loc_180092EA2
0x180092d17  mov     [rdi+0B0h], rbx
0x180092d1e  lea     r15, [r13+110h]
0x180092d25  mov     r8, r15
0x180092d28  call    MinAsn1FindExtensionMatchingValue
0x180092d2d  test    al, al
0x180092d2f  jz      short loc_180092D35
0x180092d31  or      dword ptr [rdi+40h], 1
0x180092d35  lea     r9, [rsp+0B8h+var_58]
0x180092d3a  lea     r8, qword_1800304A0
0x180092d41  mov     rdx, r15
0x180092d44  mov     rcx, r13
0x180092d47  call    I_GetNamedCatalogAttributeValue
0x180092d4c  mov     ebx, eax
0x180092d4e  mov     [rsp+0B8h+var_68], eax
0x180092d52  test    eax, eax
0x180092d54  js      short loc_180092D7B
0x180092d56  lea     rdx, [rsp+0B8h+var_58]
0x180092d5b  mov     rcx, r12
0x180092d5e  call    CipSetPlatformManifestFromPackageName
0x180092d63  mov     ebx, eax
0x180092d65  mov     [rsp+0B8h+var_68], eax
0x180092d69  xor     r12d, r12d
0x180092d6c  test    eax, eax
0x180092d6e  js      loc_180092EAB
0x180092d74  mov     esi, 0C0000225h
0x180092d79  jmp     short loc_180092D8D
0x180092d7b  xor     r12d, r12d
0x180092d7e  mov     esi, 0C0000225h
0x180092d83  cmp     ebx, esi
0x180092d85  cmovz   ebx, r12d
0x180092d89  mov     [rsp+0B8h+var_68], ebx
0x180092d8d  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x180092d92  test    eax, eax
0x180092d94  jz      loc_180092E7F
0x180092d9a  test    ebx, ebx
0x180092d9c  js      loc_180092EAB
0x180092da2  lea     r9, [rsp+0B8h+var_58]
0x180092da7  lea     r8, qword_180030490
0x180092dae  mov     rdx, r15
0x180092db1  mov     rcx, r13
0x180092db4  call    I_GetNamedCatalogAttributeValue
0x180092db9  mov     ebx, eax
0x180092dbb  mov     [rsp+0B8h+var_68], eax
0x180092dbf  test    eax, eax
0x180092dc1  js      loc_180092E71
0x180092dc7  mov     edx, dword ptr [rsp+0B8h+var_58]
0x180092dcb  mov     r8d, 2
0x180092dd1  cmp     edx, r8d
0x180092dd4  jnb     short loc_180092DDD
0x180092dd6  mov     ebx, esi
0x180092dd8  jmp     loc_180092EA7
0x180092ddd  cmp     edx, 0FFFFh
0x180092de3  jbe     short loc_180092DEF
0x180092de5  mov     ebx, 0C000000Dh
0x180092dea  jmp     loc_180092EA7
0x180092def  mov     [rsp+0B8h+SourceString.MaximumLength], dx
0x180092df4  mov     [rsp+0B8h+SourceString.Length], dx
0x180092df9  mov     rcx, [rsp+0B8h+var_50]
0x180092dfe  mov     [rsp+0B8h+SourceString.Buffer], rcx
0x180092e03  mov     rax, rdx
0x180092e06  shr     rax, 1
0x180092e09  cmp     [rcx+rax*2-2], r12w
0x180092e0f  jnz     short loc_180092E1A
0x180092e11  sub     dx, r8w
0x180092e15  mov     [rsp+0B8h+SourceString.Length], dx
0x180092e1a  movzx   edx, dx
0x180092e1d  mov     ecx, 102h
0x180092e22  mov     r8d, 63734943h
0x180092e28  call    cs:__imp_ExAllocatePool2
0x180092e2f  nop     dword ptr [rax+rax+00h]
0x180092e34  mov     [rdi+108h], rax
0x180092e3b  test    rax, rax
0x180092e3e  jnz     short loc_180092E47
0x180092e40  mov     ebx, 0C0000017h
0x180092e45  jmp     short loc_180092EA7
0x180092e47  movzx   eax, [rsp+0B8h+SourceString.Length]
0x180092e4c  mov     [rdi+102h], ax
0x180092e53  lea     rcx, [rdi+100h]; DestinationString
0x180092e5a  mov     [rcx], r12w
0x180092e5e  lea     rdx, [rsp+0B8h+SourceString]; SourceString
0x180092e63  call    cs:__imp_RtlCopyUnicodeString
0x180092e6a  nop     dword ptr [rax+rax+00h]
0x180092e6f  jmp     short loc_180092E7B
0x180092e71  cmp     ebx, esi
0x180092e73  cmovz   ebx, r12d
0x180092e77  mov     [rsp+0B8h+var_68], ebx
0x180092e7b  test    ebx, ebx
0x180092e7d  js      short loc_180092EAB
0x180092e7f  mov     r8, [rsp+0B8h+arg_20]
0x180092e87  lea     r9, [r8+8]
0x180092e8b  mov     edx, [r13+100h]
0x180092e92  mov     rcx, [r13+108h]
0x180092e99  call    MinAsn1ExtractContent
0x180092e9e  test    eax, eax
0x180092ea0  jns     short loc_180092EAB
0x180092ea2  mov     ebx, 0C0000428h
0x180092ea7  mov     [rsp+0B8h+var_68], ebx
0x180092eab  mov     eax, ebx
0x180092ead  add     rsp, 80h
0x180092eb4  pop     r15
0x180092eb6  pop     r14
0x180092eb8  pop     r13
0x180092eba  pop     r12
0x180092ebc  pop     rdi
0x180092ebd  pop     rsi
0x180092ebe  pop     rbx
0x180092ebf  retn
0x1800e9978  push    rbp
0x1800e997a  sub     rsp, 50h
0x1800e997e  mov     rbp, rdx
0x1800e9981  movzx   eax, cl
0x1800e9984  mov     ecx, [rbp+50h]
0x1800e9987  mov     edx, 0C00000E8h
0x1800e998c  test    eax, eax
0x1800e998e  cmovnz  ecx, edx
0x1800e9991  mov     [rbp+50h], ecx
0x1800e9994  add     rsp, 50h
0x1800e9998  pop     rbp
0x1800e9999  retn
```
