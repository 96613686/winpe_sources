# I_ParseCatalog

- ea: `0x180098554`
- end: `0x180098821`
- name: `I_ParseCatalog`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180098364`

## callees

- `0x18000cf84`
- `0x1800100a4`
- `0x18002ca20`
- `0x180094670`
- `0x180094db8`
- `0x180097f7c`
- `0x18009824c`
- `0x180098554`
- `0x180098828`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800987c3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800987c3`
- `ntoskrnl!ExAllocatePool2` at `0x180098788`
- `ntoskrnl!ExAllocatePool2` at `0x180098788`
- `ntoskrnl!RtlCompareMemory` at `0x180098605`
- `ntoskrnl!RtlCompareMemory` at `0x180098605`

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
  v10 = qword_18002E4E0;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v10 = (__int64 *)&qword_18002E560;
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
      && RtlCompareMemory(qword_180034C10, *(const void **)(v7 + 8), 9u) == 9
      && (int)MinAsn1ParseCTL(v7 + 16, a2 + 112) >= 0 )
    {
      for ( i = &qword_180030490; *(_DWORD *)i; i += 4 )
      {
        v13 = *((_DWORD *)i + 4);
        if ( v13 == *(_DWORD *)(a2 + 240) && !memcmp((const void *)i[1], *(const void **)(a2 + 248), v13) )
        {
          *(_QWORD *)(a1 + 176) = i;
          if ( (unsigned __int8)MinAsn1FindExtensionMatchingValue(v15, v14, a2 + 272) )
            *(_DWORD *)(a1 + 64) |= 1u;
          NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_180030470, &v19);
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
            NamedCatalogAttributeValue = I_GetNamedCatalogAttributeValue(a2, a2 + 272, &qword_180030460, &v19);
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
0x180098554  push    rbx
0x180098556  push    rsi
0x180098557  push    rdi
0x180098558  push    r12
0x18009855a  push    r13
0x18009855c  push    r14
0x18009855e  push    r15
0x180098560  sub     rsp, 80h
0x180098567  mov     r10d, r9d
0x18009856a  mov     r11, r8
0x18009856d  mov     r13, rdx
0x180098570  mov     rdi, rcx
0x180098573  lea     rsi, [rdx+20h]
0x180098577  xor     eax, eax
0x180098579  mov     [rsp+0B8h+var_58+4], rax
0x18009857e  mov     [rsp+0B8h+var_58], rax
0x180098583  xorps   xmm0, xmm0
0x180098586  movups  xmmword ptr [rsp+0B8h+SourceString.Length], xmm0
0x18009858b  lea     r12, [rcx+48h]
0x18009858f  add     rcx, 78h ; 'x'
0x180098593  lea     rdx, [rdi+0A8h]
0x18009859a  test    byte ptr cs:g_CiPolicyState+2, 1
0x1800985a1  lea     r8, qword_18002E560
0x1800985a8  lea     rax, qword_18002E4E0
0x1800985af  cmovz   rax, r8
0x1800985b3  mov     [rsp+0B8h+var_78], rcx; __int64
0x1800985b8  mov     [rsp+0B8h+var_80], rdx; __int64
0x1800985bd  mov     [rsp+0B8h+var_88], rsi; void *
0x1800985c2  mov     qword ptr [rsp+0B8h+var_90], r12; int
0x1800985c7  mov     [rsp+0B8h+var_98], rax; __int64
0x1800985cc  xor     r9d, r9d; int
0x1800985cf  xor     r8d, r8d; int
0x1800985d2  mov     edx, r10d; int
0x1800985d5  mov     rcx, r11; int
0x1800985d8  call    MinCrypK_VerifySignedDataKModeEx
0x1800985dd  mov     ebx, eax
0x1800985df  mov     [rsp+0B8h+var_68], eax
0x1800985e3  test    eax, eax
0x1800985e5  js      loc_18009880B
0x1800985eb  cmp     dword ptr [rsi], 9
0x1800985ee  jnz     loc_180098802
0x1800985f4  mov     r8d, 9; Length
0x1800985fa  mov     rdx, [rsi+8]; Source2
0x1800985fe  lea     rcx, qword_180034C10; Source1
0x180098605  call    cs:__imp_RtlCompareMemory
0x18009860c  nop     dword ptr [rax+rax+00h]
0x180098611  cmp     rax, 9
0x180098615  jnz     loc_180098802
0x18009861b  lea     rcx, [rsi+10h]
0x18009861f  lea     rdx, [r13+70h]
0x180098623  call    MinAsn1ParseCTL
0x180098628  test    eax, eax
0x18009862a  js      loc_180098802
0x180098630  lea     rbx, qword_180030490
0x180098637  mov     [rsp+0B8h+var_60], rbx
0x18009863c  mov     esi, [rbx]
0x18009863e  test    esi, esi
0x180098640  jz      loc_180098802
0x180098646  mov     eax, [rbx+10h]
0x180098649  cmp     eax, [r13+0F0h]
0x180098650  jnz     short loc_180098669
0x180098652  mov     r8d, eax; Size
0x180098655  mov     rdx, [r13+0F8h]; Buf2
0x18009865c  mov     rcx, [rbx+8]; Buf1
0x180098660  call    memcmp
0x180098665  test    eax, eax
0x180098667  jz      short loc_18009866F
0x180098669  add     rbx, 20h ; ' '
0x18009866d  jmp     short loc_180098637
0x18009866f  test    esi, esi
0x180098671  jz      loc_180098802
0x180098677  mov     [rdi+0B0h], rbx
0x18009867e  lea     r15, [r13+110h]
0x180098685  mov     r8, r15
0x180098688  call    MinAsn1FindExtensionMatchingValue
0x18009868d  test    al, al
0x18009868f  jz      short loc_180098695
0x180098691  or      dword ptr [rdi+40h], 1
0x180098695  lea     r9, [rsp+0B8h+var_58]
0x18009869a  lea     r8, qword_180030470
0x1800986a1  mov     rdx, r15
0x1800986a4  mov     rcx, r13
0x1800986a7  call    I_GetNamedCatalogAttributeValue
0x1800986ac  mov     ebx, eax
0x1800986ae  mov     [rsp+0B8h+var_68], eax
0x1800986b2  test    eax, eax
0x1800986b4  js      short loc_1800986DB
0x1800986b6  lea     rdx, [rsp+0B8h+var_58]
0x1800986bb  mov     rcx, r12
0x1800986be  call    CipSetPlatformManifestFromPackageName
0x1800986c3  mov     ebx, eax
0x1800986c5  mov     [rsp+0B8h+var_68], eax
0x1800986c9  xor     r12d, r12d
0x1800986cc  test    eax, eax
0x1800986ce  js      loc_18009880B
0x1800986d4  mov     esi, 0C0000225h
0x1800986d9  jmp     short loc_1800986ED
0x1800986db  xor     r12d, r12d
0x1800986de  mov     esi, 0C0000225h
0x1800986e3  cmp     ebx, esi
0x1800986e5  cmovz   ebx, r12d
0x1800986e9  mov     [rsp+0B8h+var_68], ebx
0x1800986ed  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800986f2  test    eax, eax
0x1800986f4  jz      loc_1800987DF
0x1800986fa  test    ebx, ebx
0x1800986fc  js      loc_18009880B
0x180098702  lea     r9, [rsp+0B8h+var_58]
0x180098707  lea     r8, qword_180030460
0x18009870e  mov     rdx, r15
0x180098711  mov     rcx, r13
0x180098714  call    I_GetNamedCatalogAttributeValue
0x180098719  mov     ebx, eax
0x18009871b  mov     [rsp+0B8h+var_68], eax
0x18009871f  test    eax, eax
0x180098721  js      loc_1800987D1
0x180098727  mov     edx, dword ptr [rsp+0B8h+var_58]
0x18009872b  mov     r8d, 2
0x180098731  cmp     edx, r8d
0x180098734  jnb     short loc_18009873D
0x180098736  mov     ebx, esi
0x180098738  jmp     loc_180098807
0x18009873d  cmp     edx, 0FFFFh
0x180098743  jbe     short loc_18009874F
0x180098745  mov     ebx, 0C000000Dh
0x18009874a  jmp     loc_180098807
0x18009874f  mov     [rsp+0B8h+SourceString.MaximumLength], dx
0x180098754  mov     [rsp+0B8h+SourceString.Length], dx
0x180098759  mov     rcx, [rsp+0B8h+var_50]
0x18009875e  mov     [rsp+0B8h+SourceString.Buffer], rcx
0x180098763  mov     rax, rdx
0x180098766  shr     rax, 1
0x180098769  cmp     [rcx+rax*2-2], r12w
0x18009876f  jnz     short loc_18009877A
0x180098771  sub     dx, r8w
0x180098775  mov     [rsp+0B8h+SourceString.Length], dx
0x18009877a  movzx   edx, dx
0x18009877d  mov     ecx, 102h
0x180098782  mov     r8d, 63734943h
0x180098788  call    cs:__imp_ExAllocatePool2
0x18009878f  nop     dword ptr [rax+rax+00h]
0x180098794  mov     [rdi+108h], rax
0x18009879b  test    rax, rax
0x18009879e  jnz     short loc_1800987A7
0x1800987a0  mov     ebx, 0C0000017h
0x1800987a5  jmp     short loc_180098807
0x1800987a7  movzx   eax, [rsp+0B8h+SourceString.Length]
0x1800987ac  mov     [rdi+102h], ax
0x1800987b3  lea     rcx, [rdi+100h]; DestinationString
0x1800987ba  mov     [rcx], r12w
0x1800987be  lea     rdx, [rsp+0B8h+SourceString]; SourceString
0x1800987c3  call    cs:__imp_RtlCopyUnicodeString
0x1800987ca  nop     dword ptr [rax+rax+00h]
0x1800987cf  jmp     short loc_1800987DB
0x1800987d1  cmp     ebx, esi
0x1800987d3  cmovz   ebx, r12d
0x1800987d7  mov     [rsp+0B8h+var_68], ebx
0x1800987db  test    ebx, ebx
0x1800987dd  js      short loc_18009880B
0x1800987df  mov     r8, [rsp+0B8h+arg_20]
0x1800987e7  lea     r9, [r8+8]
0x1800987eb  mov     edx, [r13+100h]
0x1800987f2  mov     rcx, [r13+108h]
0x1800987f9  call    MinAsn1ExtractContent
0x1800987fe  test    eax, eax
0x180098800  jns     short loc_18009880B
0x180098802  mov     ebx, 0C0000428h
0x180098807  mov     [rsp+0B8h+var_68], ebx
0x18009880b  mov     eax, ebx
0x18009880d  add     rsp, 80h
0x180098814  pop     r15
0x180098816  pop     r14
0x180098818  pop     r13
0x18009881a  pop     r12
0x18009881c  pop     rdi
0x18009881d  pop     rsi
0x18009881e  pop     rbx
0x18009881f  retn
0x1800ea168  push    rbp
0x1800ea16a  sub     rsp, 50h
0x1800ea16e  mov     rbp, rdx
0x1800ea171  movzx   eax, cl
0x1800ea174  mov     ecx, [rbp+50h]
0x1800ea177  mov     edx, 0C00000E8h
0x1800ea17c  test    eax, eax
0x1800ea17e  cmovnz  ecx, edx
0x1800ea181  mov     [rbp+50h], ecx
0x1800ea184  add     rsp, 50h
0x1800ea188  pop     rbp
0x1800ea189  retn
```
