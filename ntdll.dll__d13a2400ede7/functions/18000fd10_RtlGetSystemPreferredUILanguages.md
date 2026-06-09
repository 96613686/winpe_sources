# RtlGetSystemPreferredUILanguages

- ea: `0x18000fd10`
- end: `0x180010274`
- name: `RtlGetSystemPreferredUILanguages`
- size: `1380`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800c4750`

## callees

- `0x180009060`
- `0x18000c7b0`
- `0x18000e650`
- `0x18000ee60`
- `0x18000f760`
- `0x18000fd10`
- `0x180010280`
- `0x1800145b0`
- `0x180071890`
- `0x1800c4da0`
- `0x1800c4f40`
- `0x18012d320`

## pseudocode

```c
__int64 __fastcall RtlGetSystemPreferredUILanguages(
        unsigned int a1,
        wchar_t *a2,
        _DWORD *a3,
        _WORD *a4,
        unsigned int *a5)
{
  _WORD *v5; // r13
  __int64 v8; // rdi
  __int64 v9; // r14
  unsigned int v10; // ebx
  bool v11; // r15
  unsigned int v12; // eax
  int v13; // eax
  __int64 result; // rax
  __int64 v15; // r13
  __int64 v16; // rdx
  __int64 v17; // r9
  int v18; // esi
  int v19; // eax
  unsigned int v20; // ebx
  __int64 v21; // r9
  int LangFallbackList; // eax
  _WORD *v23; // rdx
  char v24; // r15
  char v25; // r15
  __int64 v26; // r9
  __int64 v27; // rax
  __int16 v28; // dx
  int v29; // [rsp+20h] [rbp-60h]
  unsigned __int16 v30[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v31; // [rsp+54h] [rbp-2Ch]
  int v32; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v33; // [rsp+5Ch] [rbp-24h]
  int v34; // [rsp+60h] [rbp-20h]
  __int64 LanguageList; // [rsp+68h] [rbp-18h] BYREF
  int v36[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v37; // [rsp+78h] [rbp-8h] BYREF

  v34 = -1;
  v32 = 0;
  v5 = a4;
  LanguageList = 0;
  *(_QWORD *)v36 = 0;
  v30[0] = -1;
  v8 = 0;
  v37 = 0;
  v9 = 0;
  if ( a2 )
  {
    v11 = (a1 & 0x80) != 0;
    v20 = *a5;
    wcslen(a2);
    if ( !(unsigned __int8)RtlIsValidLocaleName(a2) )
    {
      v18 = -1073741772;
      goto LABEL_66;
    }
    v10 = 4104;
  }
  else
  {
    if ( (a1 & 0xFFFF6373) != 0 )
      return 3221225485LL;
    v10 = a1 | 0x80;
    if ( (a1 & 0x9880) != 0 )
      v10 = a1;
    v11 = 0;
    if ( (v10 & 8) != 0 )
    {
      if ( (v10 & 4) != 0 )
        return 3221225485LL;
    }
    else if ( (v10 & 4) == 0 )
    {
      v10 |= 8u;
    }
  }
  v12 = v10 >> 10;
  LOBYTE(v12) = (v10 & 0x400) == 0;
  v31 = v12;
  v13 = v10 & 0x9880;
  if ( (v10 & 0x9880) != 0 )
  {
    if ( v13 != 128 && v13 != 2048 && v13 != 4096 && v13 != 0x8000 )
      return 3221225485LL;
  }
  else
  {
    v10 |= 0x8000u;
  }
  if ( !a5 )
    return 3221225485LL;
  v33 = *a5;
  if ( v33 )
  {
    if ( !v5 )
      return 3221225485LL;
  }
  result = RtlpCreateProcessRegistryInfo(&v37);
  if ( (int)result < 0 )
    return result;
  v15 = v37;
  if ( a2 )
  {
    if ( (int)RtlpMuiRegGetInstalledLanguageIndexByName(v37, a2, 0, v30) < 0 )
    {
      v18 = -1073741772;
LABEL_81:
      v20 = v33;
      v5 = a4;
LABEL_66:
      if ( v5 )
      {
        if ( v20 )
          *v5 = 0;
        if ( v20 > 1 )
          v5[1] = 0;
      }
      return (unsigned int)v18;
    }
    v34 = v30[0];
  }
  result = RtlpSetProcUserMachineLangList(v15, 0);
  if ( (int)result < 0 )
    return result;
  if ( (v10 & 0x800) == 0 )
  {
    if ( (v10 & 0x8080) != 0 )
    {
      if ( v15 )
      {
        LOBYTE(v16) = 1;
        LanguageList = RtlpMuiRegCreateLanguageList(25, v16, v15);
        if ( !LanguageList )
        {
          v18 = -1073741801;
          goto LABEL_24;
        }
        v19 = LdrpMergeLangFallbackLists(v10 | 0x30, v15, &LanguageList, 0, 0, 0, *(_QWORD *)(v15 + 56), 0, 1);
        v8 = LanguageList;
        v18 = v19;
        if ( v19 >= 0 )
          v18 = LdrpConvertLangFallbackListToMultiSz(LanguageList, v15, (_DWORD)a4, (_DWORD)a5, v10, v31, (__int64)&v32);
      }
      else
      {
        v18 = -1073741811;
      }
LABEL_22:
      if ( v8 )
        RtlpMuiRegFreeLanguageList(v8);
LABEL_24:
      if ( v9 )
        RtlpMuiRegFreeLanguageList(v9);
      if ( v18 >= 0 )
        goto LABEL_27;
      goto LABEL_81;
    }
    LOBYTE(v17) = 1;
    v18 = LdrpCreateLangFallbackList(&LanguageList, v15, 25, v17);
    if ( v18 >= 0 )
    {
      v18 = LdrpMergeLangFallbackLists(v10 | 0x30, v15, &LanguageList, 0, 0, 0, *(_QWORD *)(v15 + 56), 0, 0);
      if ( v18 >= 0 )
      {
        LOBYTE(v21) = 1;
        LangFallbackList = LdrpCreateLangFallbackList(v36, v15, 25, v21);
        v8 = LanguageList;
        v18 = LangFallbackList;
        if ( LangFallbackList < 0 )
        {
LABEL_60:
          v9 = *(_QWORD *)v36;
          goto LABEL_22;
        }
        if ( a2 )
        {
          if ( (_WORD)v34 != 0xFFFF )
          {
            v23 = (_WORD *)(28LL * (__int16)v34 + *(_QWORD *)(*(_QWORD *)(v15 + 24) + 16LL));
            if ( v23 )
            {
              if ( (*v23 & 2) != 0 || v11 && (*v23 & 4) != 0 )
                v24 = 0;
              else
                v24 = v31;
              v18 = LdrpMergeParentBaseLanguagesToList((int)v36, v29);
LABEL_59:
              if ( v18 < 0 )
                goto LABEL_60;
LABEL_54:
              v9 = *(_QWORD *)v36;
              v18 = LdrpConvertLangFallbackListToMultiSz(v36[0], v15, (_DWORD)a4, (_DWORD)a5, v10, v24, (__int64)&v32);
              goto LABEL_22;
            }
          }
        }
        else if ( *(_WORD *)(LanguageList + 4) )
        {
          v24 = v31;
          while ( 1 )
          {
            v27 = *(_QWORD *)(v8 + 24);
            if ( *(_WORD *)(v27 + 6 * v9) == 2 )
            {
              v28 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)(v15 + 24) + 16LL) + 28LL * *(__int16 *)(v27 + 6 * v9 + 4));
              if ( (v28 & 2) != 0 )
                v24 = 0;
              if ( (v28 & 6) != 0 )
              {
                v18 = LdrpMergeParentBaseLanguagesToList((int)v36, v29);
                if ( v18 >= 0 )
                  goto LABEL_54;
              }
            }
            v9 = (unsigned int)(v9 + 1);
            if ( (unsigned int)v9 >= *(unsigned __int16 *)(v8 + 4) )
              goto LABEL_59;
          }
        }
        v24 = v31;
        goto LABEL_54;
      }
    }
LABEL_71:
    v8 = LanguageList;
    goto LABEL_22;
  }
  v25 = v31;
  *a5 = v33;
  v18 = LdrpConvertLangFallbackListToMultiSz(
          *(_QWORD *)(v15 + 56),
          v15,
          (_DWORD)a4,
          (_DWORD)a5,
          v10,
          v25,
          (__int64)&v32);
  if ( v18 < 0 || !v32 )
  {
    LOBYTE(v26) = 1;
    v18 = LdrpCreateLangFallbackList(&LanguageList, v15, 25, v26);
    if ( v18 >= 0 )
    {
      v18 = LdrpMergeLangFallbackLists(v10 | 0x30, v15, &LanguageList, 0, 0, 0, 0, 0, 0);
      if ( v18 >= 0 )
      {
        *a5 = v33;
        v8 = LanguageList;
        v18 = LdrpConvertLangFallbackListToMultiSz(LanguageList, v15, (_DWORD)a4, (_DWORD)a5, v10, v25, (__int64)&v32);
        goto LABEL_22;
      }
    }
    goto LABEL_71;
  }
LABEL_27:
  *a3 = v32;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000fd10  mov     [rsp-38h+arg_0], rbx
0x18000fd15  mov     [rsp-38h+arg_18], r9
0x18000fd1a  mov     [rsp-38h+arg_8], rdx
0x18000fd1f  push    rbp
0x18000fd20  push    rsi
0x18000fd21  push    rdi
0x18000fd22  push    r12
0x18000fd24  push    r13
0x18000fd26  push    r14
0x18000fd28  push    r15
0x18000fd2a  mov     rbp, rsp
0x18000fd2d  sub     rsp, 80h
0x18000fd34  mov     eax, 0FFFFFFFFh
0x18000fd39  mov     r15d, ecx
0x18000fd3c  xor     ecx, ecx
0x18000fd3e  mov     [rbp+var_20], eax
0x18000fd41  mov     [rbp+var_28], ecx
0x18000fd44  mov     r13, r9
0x18000fd47  mov     [rbp+var_18], rcx
0x18000fd4b  mov     r12, r8
0x18000fd4e  mov     qword ptr [rbp+var_10], rcx
0x18000fd52  mov     rsi, rdx
0x18000fd55  mov     [rbp+var_30], ax
0x18000fd59  mov     edi, ecx
0x18000fd5b  mov     [rbp+var_8], rcx
0x18000fd5f  mov     r14d, ecx
0x18000fd62  test    rdx, rdx
0x18000fd65  jnz     loc_18000FF55
0x18000fd6b  test    r15d, 0FFFF6373h
0x18000fd72  jnz     loc_18000FF28
0x18000fd78  mov     ebx, r15d
0x18000fd7b  bts     ebx, 7
0x18000fd7f  test    r15d, 9880h
0x18000fd86  cmovnz  ebx, r15d
0x18000fd8a  xor     r15b, r15b
0x18000fd8d  mov     eax, ebx
0x18000fd8f  and     eax, 4
0x18000fd92  test    bl, 8
0x18000fd95  jz      loc_18001024A
0x18000fd9b  test    eax, eax
0x18000fd9d  jnz     loc_18000FF28
0x18000fda3  mov     eax, ebx
0x18000fda5  shr     eax, 0Ah
0x18000fda8  not     al
0x18000fdaa  and     al, 1
0x18000fdac  mov     [rbp+var_2C], eax
0x18000fdaf  mov     eax, ebx
0x18000fdb1  and     eax, 9880h
0x18000fdb6  jz      loc_18001025A
0x18000fdbc  cmp     eax, 80h
0x18000fdc1  jnz     loc_18000FF07
0x18000fdc7  mov     rax, [rbp+arg_20]
0x18000fdcb  test    rax, rax
0x18000fdce  jz      loc_18000FF28
0x18000fdd4  mov     eax, [rax]
0x18000fdd6  mov     [rbp+var_24], eax
0x18000fdd9  test    eax, eax
0x18000fddb  jz      short loc_18000FDE6
0x18000fddd  test    r13, r13
0x18000fde0  jz      loc_18000FF28
0x18000fde6  lea     rcx, [rbp+var_8]
0x18000fdea  call    RtlpCreateProcessRegistryInfo
0x18000fdef  test    eax, eax
0x18000fdf1  js      loc_18000FEEB
0x18000fdf7  mov     r13, [rbp+var_8]
0x18000fdfb  test    rsi, rsi
0x18000fdfe  jnz     loc_18000FF2F
0x18000fe04  xor     edx, edx
0x18000fe06  mov     rcx, r13
0x18000fe09  call    RtlpSetProcUserMachineLangList
0x18000fe0e  test    eax, eax
0x18000fe10  js      loc_18000FEEB
0x18000fe16  bt      ebx, 0Bh
0x18000fe1a  jb      loc_180010056
0x18000fe20  test    ebx, 8080h
0x18000fe26  jz      loc_18000FF8B
0x18000fe2c  test    r13, r13
0x18000fe2f  jz      loc_18001004C
0x18000fe35  mov     r8, r13
0x18000fe38  mov     dl, 1
0x18000fe3a  mov     ecx, 19h
0x18000fe3f  call    RtlpMuiRegCreateLanguageList
0x18000fe44  mov     rdi, rax
0x18000fe47  mov     [rbp+var_18], rax
0x18000fe4b  xor     esi, esi
0x18000fe4d  mov     eax, 0C0000017h
0x18000fe52  test    rdi, rdi
0x18000fe55  cmovz   esi, eax
0x18000fe58  jz      short loc_18000FECD
0x18000fe5a  mov     rax, [r13+38h]
0x18000fe5e  lea     r8, [rbp+var_18]
0x18000fe62  mov     [rsp+80h+var_40], 1
0x18000fe67  mov     ecx, ebx
0x18000fe69  mov     [rsp+80h+var_48], r14
0x18000fe6e  or      ecx, 30h
0x18000fe71  mov     [rsp+80h+var_50], rax
0x18000fe76  xor     r9d, r9d
0x18000fe79  mov     [rsp+80h+var_58], r14
0x18000fe7e  mov     rdx, r13
0x18000fe81  mov     qword ptr [rsp+80h+var_60], r14
0x18000fe86  call    LdrpMergeLangFallbackLists
0x18000fe8b  mov     rdi, [rbp+var_18]
0x18000fe8f  mov     esi, eax
0x18000fe91  test    eax, eax
0x18000fe93  js      short loc_18000FEC0
0x18000fe95  mov     r15d, [rbp+var_2C]
0x18000fe99  lea     rax, [rbp+var_28]
0x18000fe9d  mov     r9, [rbp+arg_20]
0x18000fea1  mov     rdx, r13
0x18000fea4  mov     r8, [rbp+arg_18]
0x18000fea8  mov     rcx, rdi
0x18000feab  mov     [rsp+80h+var_50], rax
0x18000feb0  mov     byte ptr [rsp+80h+var_58], r15b
0x18000feb5  mov     [rsp+80h+var_60], ebx
0x18000feb9  call    LdrpConvertLangFallbackListToMultiSz
0x18000febe  mov     esi, eax
0x18000fec0  test    rdi, rdi
0x18000fec3  jz      short loc_18000FECD
0x18000fec5  mov     rcx, rdi
0x18000fec8  call    RtlpMuiRegFreeLanguageList
0x18000fecd  test    r14, r14
0x18000fed0  jz      short loc_18000FEDA
0x18000fed2  mov     rcx, r14
0x18000fed5  call    RtlpMuiRegFreeLanguageList
0x18000feda  test    esi, esi
0x18000fedc  js      loc_180010268
0x18000fee2  mov     eax, [rbp+var_28]
0x18000fee5  mov     [r12], eax
0x18000fee9  mov     eax, esi
0x18000feeb  mov     rbx, [rsp+80h+arg_0]
0x18000fef3  add     rsp, 80h
0x18000fefa  pop     r15
0x18000fefc  pop     r14
0x18000fefe  pop     r13
0x18000ff00  pop     r12
0x18000ff02  pop     rdi
0x18000ff03  pop     rsi
0x18000ff04  pop     rbp
0x18000ff05  retn
0x18000ff07  cmp     eax, 800h
0x18000ff0c  jz      loc_18000FDC7
0x18000ff12  cmp     eax, 1000h
0x18000ff17  jz      loc_18000FDC7
0x18000ff1d  cmp     eax, 8000h
0x18000ff22  jz      loc_18000FDC7
0x18000ff28  mov     eax, 0C000000Dh
0x18000ff2d  jmp     short loc_18000FEEB
0x18000ff2f  lea     r9, [rbp+var_30]
0x18000ff33  xor     r8d, r8d
0x18000ff36  mov     rdx, rsi
0x18000ff39  mov     rcx, r13
0x18000ff3c  call    RtlpMuiRegGetInstalledLanguageIndexByName
0x18000ff41  test    eax, eax
0x18000ff43  js      loc_180010263
0x18000ff49  movzx   eax, [rbp+var_30]
0x18000ff4d  mov     [rbp+var_20], eax
0x18000ff50  jmp     loc_18000FE04
0x18000ff55  mov     r9, [rbp+arg_20]
0x18000ff59  mov     rcx, rsi; String
0x18000ff5c  shr     r15d, 7
0x18000ff60  and     r15b, 1
0x18000ff64  mov     ebx, [r9]
0x18000ff67  call    wcslen
0x18000ff6c  mov     edx, 2
0x18000ff71  mov     rcx, rsi; String
0x18000ff74  call    RtlIsValidLocaleName
0x18000ff79  test    al, al
0x18000ff7b  jz      loc_1800101BB
0x18000ff81  mov     ebx, 1008h
0x18000ff86  jmp     loc_18000FDA3
0x18000ff8b  mov     r9b, 1
0x18000ff8e  lea     rcx, [rbp+var_18]
0x18000ff92  mov     r8d, 19h
0x18000ff98  mov     rdx, r13
0x18000ff9b  call    LdrpCreateLangFallbackList
0x18000ffa0  mov     esi, eax
0x18000ffa2  test    eax, eax
0x18000ffa4  js      loc_1800101E9
0x18000ffaa  mov     rax, [r13+38h]
0x18000ffae  lea     r8, [rbp+var_18]
0x18000ffb2  mov     [rsp+80h+var_40], dil
0x18000ffb7  mov     ecx, ebx
0x18000ffb9  mov     [rsp+80h+var_48], rdi
0x18000ffbe  or      ecx, 30h
0x18000ffc1  mov     [rsp+80h+var_50], rax
0x18000ffc6  xor     r9d, r9d
0x18000ffc9  mov     [rsp+80h+var_58], rdi
0x18000ffce  mov     rdx, r13
0x18000ffd1  mov     qword ptr [rsp+80h+var_60], rdi; int
0x18000ffd6  call    LdrpMergeLangFallbackLists
0x18000ffdb  mov     esi, eax
0x18000ffdd  test    eax, eax
0x18000ffdf  js      loc_1800101E9
0x18000ffe5  mov     r9b, 1
0x18000ffe8  lea     rcx, [rbp+var_10]
0x18000ffec  mov     r8d, 19h
0x18000fff2  mov     rdx, r13
0x18000fff5  call    LdrpCreateLangFallbackList
0x18000fffa  mov     rdi, [rbp+var_18]
0x18000fffe  mov     esi, eax
0x180010000  test    eax, eax
0x180010002  js      loc_18001018B
0x180010008  cmp     [rbp+arg_8], r14
0x18001000c  jz      loc_180010122
0x180010012  movsxd  rax, [rbp+var_20]
0x180010016  cmp     ax, 0FFFFh
0x18001001a  jz      loc_18001012A
0x180010020  mov     rdx, [r13+18h]
0x180010024  movsx   rax, ax
0x180010028  imul    rcx, rax, 1Ch
0x18001002c  mov     rdx, [rdx+10h]
0x180010030  add     rdx, rcx
0x180010033  jz      loc_18001012A
0x180010039  movzx   eax, word ptr [rdx]
0x18001003c  test    al, 2
0x18001003e  jz      loc_18001015E
0x180010044  xor     r15b, r15b
0x180010047  jmp     loc_18001016F
0x18001004c  mov     esi, 0C000000Dh
0x180010051  jmp     loc_18000FEC0
0x180010056  mov     rdi, [rbp+arg_20]
0x18001005a  mov     rdx, r13
0x18001005d  mov     eax, [rbp+var_24]
0x180010060  mov     r9, rdi
0x180010063  mov     r15d, [rbp+var_2C]
0x180010067  mov     r8, [rbp+arg_18]
0x18001006b  mov     [rdi], eax
0x18001006d  lea     rax, [rbp+var_28]
0x180010071  mov     rcx, [r13+38h]
0x180010075  mov     [rsp+80h+var_50], rax
0x18001007a  mov     byte ptr [rsp+80h+var_58], r15b
0x18001007f  mov     [rsp+80h+var_60], ebx
0x180010083  call    LdrpConvertLangFallbackListToMultiSz
0x180010088  mov     esi, eax
0x18001008a  test    eax, eax
0x18001008c  js      short loc_180010098
0x18001008e  cmp     [rbp+var_28], r14d
0x180010092  jnz     loc_18000FEE2
0x180010098  mov     r9b, 1
0x18001009b  lea     rcx, [rbp+var_18]
0x18001009f  mov     r8d, 19h
0x1800100a5  mov     rdx, r13
0x1800100a8  call    LdrpCreateLangFallbackList
0x1800100ad  mov     esi, eax
0x1800100af  test    eax, eax
0x1800100b1  js      loc_1800101E9
0x1800100b7  mov     [rsp+80h+var_40], r14b
0x1800100bc  lea     r8, [rbp+var_18]
0x1800100c0  mov     [rsp+80h+var_48], r14
0x1800100c5  mov     ecx, ebx
0x1800100c7  mov     [rsp+80h+var_50], r14
0x1800100cc  or      ecx, 30h
0x1800100cf  mov     [rsp+80h+var_58], r14
0x1800100d4  xor     r9d, r9d
0x1800100d7  mov     rdx, r13
0x1800100da  mov     qword ptr [rsp+80h+var_60], r14
0x1800100df  call    LdrpMergeLangFallbackLists
0x1800100e4  mov     esi, eax
0x1800100e6  test    eax, eax
0x1800100e8  js      loc_1800101E9
0x1800100ee  mov     eax, [rbp+var_24]
0x1800100f1  mov     r9, rdi
0x1800100f4  mov     r8, [rbp+arg_18]
0x1800100f8  mov     rdx, r13
0x1800100fb  mov     [rdi], eax
0x1800100fd  lea     rax, [rbp+var_28]
0x180010101  mov     rdi, [rbp+var_18]
0x180010105  mov     [rsp+80h+var_50], rax
0x18001010a  mov     rcx, rdi
0x18001010d  mov     byte ptr [rsp+80h+var_58], r15b
0x180010112  mov     [rsp+80h+var_60], ebx
0x180010116  call    LdrpConvertLangFallbackListToMultiSz
0x18001011b  mov     esi, eax
0x18001011d  jmp     loc_18000FEC0
0x180010122  xor     eax, eax
0x180010124  cmp     ax, [rdi+4]
0x180010128  jb      short loc_18001019A
0x18001012a  mov     r15d, [rbp+var_2C]
0x18001012e  mov     r14, qword ptr [rbp+var_10]
0x180010132  lea     rax, [rbp+var_28]
0x180010136  mov     r9, [rbp+arg_20]
0x18001013a  mov     rdx, r13
0x18001013d  mov     r8, [rbp+arg_18]
0x180010141  mov     rcx, r14
0x180010144  mov     [rsp+80h+var_50], rax
0x180010149  mov     byte ptr [rsp+80h+var_58], r15b
0x18001014e  mov     [rsp+80h+var_60], ebx
0x180010152  call    LdrpConvertLangFallbackListToMultiSz
0x180010157  mov     esi, eax
0x180010159  jmp     loc_18000FEC0
0x18001015e  test    r15b, r15b
0x180010161  jz      short loc_18001016B
0x180010163  test    al, 4
0x180010165  jnz     loc_180010044
0x18001016b  mov     r15d, [rbp+var_2C]
0x18001016f  cmp     [rdi+8], r14b
0x180010173  jz      short loc_180010194
0x180010175  mov     r9, [r13+28h]
0x180010179  mov     r8, r13
0x18001017c  lea     rcx, [rbp+var_10]; int
  ... truncated ...
```
