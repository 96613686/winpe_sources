# I_ParseCatalog

- ea: `0x1800915c4`
- end: `0x180091891`
- name: `I_ParseCatalog`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800913d4`

## callees

- `0x18000cf74`
- `0x180010128`
- `0x18002c860`
- `0x18008d6e0`
- `0x18008de28`
- `0x180090fec`
- `0x1800912bc`
- `0x1800915c4`
- `0x180091898`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x180091833`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180091833`
- `ntoskrnl!ExAllocatePool2` at `0x1800917f8`
- `ntoskrnl!ExAllocatePool2` at `0x1800917f8`
- `ntoskrnl!RtlCompareMemory` at `0x180091675`
- `ntoskrnl!RtlCompareMemory` at `0x180091675`

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
      && RtlCompareMemory(qword_180034BD0, *(const void **)(v7 + 8), 9u) == 9
      && (int)MinAsn1ParseCTL(v7 + 16, a2 + 112) >= 0 )
    {
      for ( i = &qword_180030420; *(_DWORD *)i; i += 4 )
      {
        v13 = *((_DWORD *)i + 4);
        if ( v13 == *(_DWORD *)(a2 + 240) && !memcmp((const void *)i[1], *(const void **)(a2 + 248), v13) )
        {
          *(_QWORD *)(a1 + 176) = i;
          if ( (unsigned __int8)MinAsn1FindExtensionMatchingValue(v15, v14, a2 + 272) )
            *(_DWORD *)(a1 + 64) |= 1u;
          NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_180030400, &v19);
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
            NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_1800303F0, &v19);
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
0x1800915c4  push    rbx
0x1800915c6  push    rsi
0x1800915c7  push    rdi
0x1800915c8  push    r12
0x1800915ca  push    r13
0x1800915cc  push    r14
0x1800915ce  push    r15
0x1800915d0  sub     rsp, 80h
0x1800915d7  mov     r10d, r9d
0x1800915da  mov     r11, r8
0x1800915dd  mov     r13, rdx
0x1800915e0  mov     rdi, rcx
0x1800915e3  lea     rsi, [rdx+20h]
0x1800915e7  xor     eax, eax
0x1800915e9  mov     [rsp+0B8h+var_58+4], rax
0x1800915ee  mov     [rsp+0B8h+var_58], rax
0x1800915f3  xorps   xmm0, xmm0
0x1800915f6  movups  xmmword ptr [rsp+0B8h+SourceString.Length], xmm0
0x1800915fb  lea     r12, [rcx+48h]
0x1800915ff  add     rcx, 78h ; 'x'
0x180091603  lea     rdx, [rdi+0A8h]
0x18009160a  test    byte ptr cs:g_CiPolicyState+2, 1
0x180091611  lea     r8, qword_18002E5B0
0x180091618  lea     rax, qword_18002E530
0x18009161f  cmovz   rax, r8
0x180091623  mov     [rsp+0B8h+var_78], rcx; __int64
0x180091628  mov     [rsp+0B8h+var_80], rdx; __int64
0x18009162d  mov     [rsp+0B8h+var_88], rsi; void *
0x180091632  mov     qword ptr [rsp+0B8h+var_90], r12; int
0x180091637  mov     [rsp+0B8h+var_98], rax; __int64
0x18009163c  xor     r9d, r9d; int
0x18009163f  xor     r8d, r8d; int
0x180091642  mov     edx, r10d; int
0x180091645  mov     rcx, r11; int
0x180091648  call    MinCrypK_VerifySignedDataKModeEx
0x18009164d  mov     ebx, eax
0x18009164f  mov     [rsp+0B8h+var_68], eax
0x180091653  test    eax, eax
0x180091655  js      loc_18009187B
0x18009165b  cmp     dword ptr [rsi], 9
0x18009165e  jnz     loc_180091872
0x180091664  mov     r8d, 9; Length
0x18009166a  mov     rdx, [rsi+8]; Source2
0x18009166e  lea     rcx, qword_180034BD0; Source1
0x180091675  call    cs:__imp_RtlCompareMemory
0x18009167c  nop     dword ptr [rax+rax+00h]
0x180091681  cmp     rax, 9
0x180091685  jnz     loc_180091872
0x18009168b  lea     rcx, [rsi+10h]
0x18009168f  lea     rdx, [r13+70h]
0x180091693  call    MinAsn1ParseCTL
0x180091698  test    eax, eax
0x18009169a  js      loc_180091872
0x1800916a0  lea     rbx, qword_180030420
0x1800916a7  mov     [rsp+0B8h+var_60], rbx
0x1800916ac  mov     esi, [rbx]
0x1800916ae  test    esi, esi
0x1800916b0  jz      loc_180091872
0x1800916b6  mov     eax, [rbx+10h]
0x1800916b9  cmp     eax, [r13+0F0h]
0x1800916c0  jnz     short loc_1800916D9
0x1800916c2  mov     r8d, eax; Size
0x1800916c5  mov     rdx, [r13+0F8h]; Buf2
0x1800916cc  mov     rcx, [rbx+8]; Buf1
0x1800916d0  call    memcmp
0x1800916d5  test    eax, eax
0x1800916d7  jz      short loc_1800916DF
0x1800916d9  add     rbx, 20h ; ' '
0x1800916dd  jmp     short loc_1800916A7
0x1800916df  test    esi, esi
0x1800916e1  jz      loc_180091872
0x1800916e7  mov     [rdi+0B0h], rbx
0x1800916ee  lea     r15, [r13+110h]
0x1800916f5  mov     r8, r15
0x1800916f8  call    MinAsn1FindExtensionMatchingValue
0x1800916fd  test    al, al
0x1800916ff  jz      short loc_180091705
0x180091701  or      dword ptr [rdi+40h], 1
0x180091705  lea     r9, [rsp+0B8h+var_58]
0x18009170a  lea     r8, qword_180030400
0x180091711  mov     rdx, r15
0x180091714  mov     rcx, r13
0x180091717  call    I_GetNamedCatalogAttributeValue
0x18009171c  mov     ebx, eax
0x18009171e  mov     [rsp+0B8h+var_68], eax
0x180091722  test    eax, eax
0x180091724  js      short loc_18009174B
0x180091726  lea     rdx, [rsp+0B8h+var_58]
0x18009172b  mov     rcx, r12
0x18009172e  call    CipSetPlatformManifestFromPackageName
0x180091733  mov     ebx, eax
0x180091735  mov     [rsp+0B8h+var_68], eax
0x180091739  xor     r12d, r12d
0x18009173c  test    eax, eax
0x18009173e  js      loc_18009187B
0x180091744  mov     esi, 0C0000225h
0x180091749  jmp     short loc_18009175D
0x18009174b  xor     r12d, r12d
0x18009174e  mov     esi, 0C0000225h
0x180091753  cmp     ebx, esi
0x180091755  cmovz   ebx, r12d
0x180091759  mov     [rsp+0B8h+var_68], ebx
0x18009175d  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x180091762  test    eax, eax
0x180091764  jz      loc_18009184F
0x18009176a  test    ebx, ebx
0x18009176c  js      loc_18009187B
0x180091772  lea     r9, [rsp+0B8h+var_58]
0x180091777  lea     r8, qword_1800303F0
0x18009177e  mov     rdx, r15
0x180091781  mov     rcx, r13
0x180091784  call    I_GetNamedCatalogAttributeValue
0x180091789  mov     ebx, eax
0x18009178b  mov     [rsp+0B8h+var_68], eax
0x18009178f  test    eax, eax
0x180091791  js      loc_180091841
0x180091797  mov     edx, dword ptr [rsp+0B8h+var_58]
0x18009179b  mov     r8d, 2
0x1800917a1  cmp     edx, r8d
0x1800917a4  jnb     short loc_1800917AD
0x1800917a6  mov     ebx, esi
0x1800917a8  jmp     loc_180091877
0x1800917ad  cmp     edx, 0FFFFh
0x1800917b3  jbe     short loc_1800917BF
0x1800917b5  mov     ebx, 0C000000Dh
0x1800917ba  jmp     loc_180091877
0x1800917bf  mov     [rsp+0B8h+SourceString.MaximumLength], dx
0x1800917c4  mov     [rsp+0B8h+SourceString.Length], dx
0x1800917c9  mov     rcx, [rsp+0B8h+var_50]
0x1800917ce  mov     [rsp+0B8h+SourceString.Buffer], rcx
0x1800917d3  mov     rax, rdx
0x1800917d6  shr     rax, 1
0x1800917d9  cmp     [rcx+rax*2-2], r12w
0x1800917df  jnz     short loc_1800917EA
0x1800917e1  sub     dx, r8w
0x1800917e5  mov     [rsp+0B8h+SourceString.Length], dx
0x1800917ea  movzx   edx, dx
0x1800917ed  mov     ecx, 102h
0x1800917f2  mov     r8d, 63734943h
0x1800917f8  call    cs:__imp_ExAllocatePool2
0x1800917ff  nop     dword ptr [rax+rax+00h]
0x180091804  mov     [rdi+108h], rax
0x18009180b  test    rax, rax
0x18009180e  jnz     short loc_180091817
0x180091810  mov     ebx, 0C0000017h
0x180091815  jmp     short loc_180091877
0x180091817  movzx   eax, [rsp+0B8h+SourceString.Length]
0x18009181c  mov     [rdi+102h], ax
0x180091823  lea     rcx, [rdi+100h]; DestinationString
0x18009182a  mov     [rcx], r12w
0x18009182e  lea     rdx, [rsp+0B8h+SourceString]; SourceString
0x180091833  call    cs:__imp_RtlCopyUnicodeString
0x18009183a  nop     dword ptr [rax+rax+00h]
0x18009183f  jmp     short loc_18009184B
0x180091841  cmp     ebx, esi
0x180091843  cmovz   ebx, r12d
0x180091847  mov     [rsp+0B8h+var_68], ebx
0x18009184b  test    ebx, ebx
0x18009184d  js      short loc_18009187B
0x18009184f  mov     r8, [rsp+0B8h+arg_20]
0x180091857  lea     r9, [r8+8]
0x18009185b  mov     edx, [r13+100h]
0x180091862  mov     rcx, [r13+108h]
0x180091869  call    MinAsn1ExtractContent
0x18009186e  test    eax, eax
0x180091870  jns     short loc_18009187B
0x180091872  mov     ebx, 0C0000428h
0x180091877  mov     [rsp+0B8h+var_68], ebx
0x18009187b  mov     eax, ebx
0x18009187d  add     rsp, 80h
0x180091884  pop     r15
0x180091886  pop     r14
0x180091888  pop     r13
0x18009188a  pop     r12
0x18009188c  pop     rdi
0x18009188d  pop     rsi
0x18009188e  pop     rbx
0x18009188f  retn
0x1800e81d8  push    rbp
0x1800e81da  sub     rsp, 50h
0x1800e81de  mov     rbp, rdx
0x1800e81e1  movzx   eax, cl
0x1800e81e4  mov     ecx, [rbp+50h]
0x1800e81e7  mov     edx, 0C00000E8h
0x1800e81ec  test    eax, eax
0x1800e81ee  cmovnz  ecx, edx
0x1800e81f1  mov     [rbp+50h], ecx
0x1800e81f4  add     rsp, 50h
0x1800e81f8  pop     rbp
0x1800e81f9  retn
```
