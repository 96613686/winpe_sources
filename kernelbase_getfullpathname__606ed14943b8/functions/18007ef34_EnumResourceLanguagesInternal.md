# EnumResourceLanguagesInternal

- ea: `0x18007ef34`
- end: `0x18007fa0b`
- name: `EnumResourceLanguagesInternal`
- size: `2775`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18007fc30`
- `0x18012d9f0`

## callees

- `0x18004b9d0`
- `0x18007ebd0`
- `0x18007ed30`
- `0x18007ed68`
- `0x18007ef34`
- `0x18007fa14`
- `0x18007fb08`
- `0x18007fdc0`
- `0x180080480`
- `0x1800bad80`
- `0x180180538`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18007f384`
- `ntdll!RtlFreeHeap` at `0x18007f968`
- `ntdll!RtlFreeHeap` at `0x18007f98d`
- `ntdll!RtlFreeHeap` at `0x18007f9ad`
- `ntdll!RtlFreeHeap` at `0x1801957cb`
- `ntdll!RtlFreeHeap` at `0x1801957fe`
- `ntdll!RtlFreeHeap` at `0x18019582a`
- `ntdll!RtlFreeHeap` at `0x18007f384`
- `ntdll!RtlFreeHeap` at `0x18007f968`
- `ntdll!RtlFreeHeap` at `0x18007f98d`
- `ntdll!RtlFreeHeap` at `0x18007f9ad`
- `ntdll!RtlFreeHeap` at `0x1801957cb`
- `ntdll!RtlFreeHeap` at `0x1801957fe`
- `ntdll!RtlFreeHeap` at `0x18019582a`
- `ntdll!LdrResGetRCConfig` at `0x18007f3bb`
- `ntdll!LdrResGetRCConfig` at `0x18007f65d`
- `ntdll!LdrResGetRCConfig` at `0x18007f3bb`
- `ntdll!LdrResGetRCConfig` at `0x18007f65d`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007f17f`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007f7bc`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007f17f`
- `ntdll!LdrpResGetResourceDirectory` at `0x18007f7bc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007f5f3`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18007f5f3`
- `ntdll!LdrRscIsTypeExist` at `0x18007f631`
- `ntdll!LdrRscIsTypeExist` at `0x18007f631`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x18007f299`
- `ntdll!LdrLoadAlternateResourceModuleEx` at `0x18007f299`
- `ntdll!LdrpResGetMappingSize` at `0x18007f874`
- `ntdll!LdrpResGetMappingSize` at `0x18007f874`
- `ntdll!RtlAllocateHeap` at `0x18007f6b9`
- `ntdll!RtlAllocateHeap` at `0x18007f6b9`

## pseudocode

```c
__int64 __fastcall EnumResourceLanguagesInternal(
        void *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        unsigned int (__fastcall *a4)(void *, void *, void *, _QWORD, __int64),
        __int64 a5,
        unsigned int a6,
        unsigned __int16 a7,
        char a8)
{
  PVOID ImageBaseAddress; // r13
  unsigned int v10; // r15d
  int v11; // eax
  __int64 v12; // rsi
  signed int RCConfig; // esi
  unsigned int v14; // r14d
  int v15; // ebx
  __int64 v16; // r13
  __int64 v17; // r9
  __int64 v18; // r13
  PVOID v19; // rbx
  int v20; // ebx
  int i; // ebx
  unsigned __int16 v22; // bx
  unsigned int j; // ecx
  unsigned int v24; // ecx
  void *v25; // r8
  void *v26; // rdx
  int v27; // eax
  unsigned __int16 *v28; // rbx
  unsigned int v29; // edx
  __int64 v30; // r9
  unsigned int k; // ecx
  void *v32; // r8
  void *v33; // rdx
  __int64 v34; // rax
  unsigned __int64 v35; // rdx
  LANGID *v36; // rbx
  int v38; // [rsp+38h] [rbp-230h]
  ULONG Size; // [rsp+3Ch] [rbp-22Ch] BYREF
  int v40; // [rsp+40h] [rbp-228h]
  int v41; // [rsp+44h] [rbp-224h]
  int v42; // [rsp+48h] [rbp-220h] BYREF
  unsigned int v43; // [rsp+4Ch] [rbp-21Ch]
  PVOID P[2]; // [rsp+50h] [rbp-218h] BYREF
  int v45; // [rsp+60h] [rbp-208h]
  __int64 v46; // [rsp+68h] [rbp-200h]
  __int64 v47; // [rsp+70h] [rbp-1F8h]
  __int64 v48; // [rsp+78h] [rbp-1F0h]
  PVOID BaseAddress; // [rsp+80h] [rbp-1E8h] BYREF
  PVOID v50; // [rsp+88h] [rbp-1E0h]
  PVOID v51; // [rsp+90h] [rbp-1D8h]
  PVOID Address; // [rsp+98h] [rbp-1D0h] BYREF
  unsigned __int64 v53; // [rsp+A0h] [rbp-1C8h] BYREF
  __int64 v54; // [rsp+A8h] [rbp-1C0h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-1B8h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-1B0h]
  void *v57; // [rsp+C0h] [rbp-1A8h]
  unsigned int (__fastcall *v58)(void *, void *, void *, __int64, __int64); // [rsp+C8h] [rbp-1A0h]
  int v59; // [rsp+D0h] [rbp-198h]
  unsigned int v60; // [rsp+D4h] [rbp-194h]
  unsigned int v61; // [rsp+D8h] [rbp-190h]
  int v62; // [rsp+DCh] [rbp-18Ch]
  PVOID v63; // [rsp+E0h] [rbp-188h] BYREF
  PCWCH v64; // [rsp+E8h] [rbp-180h]
  PCWCH UnicodeString; // [rsp+F0h] [rbp-178h]
  __int64 v66; // [rsp+F8h] [rbp-170h] BYREF
  unsigned int v67; // [rsp+100h] [rbp-168h]
  __int64 v68; // [rsp+108h] [rbp-160h] BYREF
  unsigned __int16 *v69; // [rsp+110h] [rbp-158h]
  int v70; // [rsp+118h] [rbp-150h]
  _WORD v71[128]; // [rsp+120h] [rbp-148h]
  int v72; // [rsp+2A8h] [rbp+40h]

  v58 = a4;
  v64 = a3;
  UnicodeString = a2;
  ImageBaseAddress = a1;
  v57 = a1;
  Size = 0;
  v53 = 0;
  v63 = 0;
  v68 = 0;
  v66 = 0;
  *(_OWORD *)P = 0;
  v55 = 0;
  v50 = 0;
  v59 = 0;
  v51 = 0;
  LODWORD(v56) = 0;
  v54 = 0;
  v42 = 0;
  if ( (a6 & 0xFFFFFFE0) != 0 )
    goto LABEL_138;
  v41 = a6 & 8;
  v10 = a6 | 3;
  if ( (a6 & 0x17) != 0 )
    v10 = a6;
  if ( (a6 & 6) == 6 )
    goto LABEL_142;
  if ( (a6 & 0x10) != 0 )
  {
    if ( (a6 & 7) == 0 )
    {
      v10 = v10 & 0xFFFFFFEE | 1;
      goto LABEL_6;
    }
LABEL_142:
    v11 = 0;
    goto LABEL_7;
  }
LABEL_6:
  v11 = 1;
LABEL_7:
  if ( !v11 )
    goto LABEL_138;
  v12 = BaseDllMapResourceIdW(a2);
  v46 = v12;
  if ( v12 == -1 )
    goto LABEL_138;
  v47 = BaseDllMapResourceIdW(a3);
  if ( v47 == -1 )
  {
    BaseDllFreeResourceId(v12);
LABEL_138:
    BaseSetLastNTError(3221225485LL);
    return 0;
  }
  RCConfig = 0;
  v43 = 0;
  v45 = 0;
  v14 = 1;
  v38 = 0;
  v40 = 0;
  if ( !ImageBaseAddress )
    ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
  Address = ImageBaseAddress;
  BaseAddress = ImageBaseAddress;
  v72 = a8 & 1;
  if ( v72 )
  {
    if ( ((unsigned __int64)UnicodeString & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      RCConfig = ConverStringWithHeapAlloc(UnicodeString);
      if ( RCConfig < 0 )
      {
LABEL_108:
        v14 = 0;
LABEL_109:
        v16 = v46;
        goto LABEL_28;
      }
    }
    else
    {
      v50 = (PVOID)UnicodeString;
    }
    if ( ((unsigned __int64)v64 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      RCConfig = ConverStringWithHeapAlloc(v64);
      if ( RCConfig < 0 )
        goto LABEL_108;
    }
    else
    {
      v51 = (PVOID)v64;
    }
  }
  v15 = v41;
  if ( (a6 & 0x10) != 0 )
    goto LABEL_14;
  if ( v41 )
  {
    RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v54, 0, 1);
    if ( RCConfig == -1073020925 )
      RCConfig = -1073741701;
  }
  else
  {
    RCConfig = LdrResGetRCConfig(ImageBaseAddress, 0, &v54, 0x2000, 1);
  }
  if ( RCConfig >= 0 )
  {
    v16 = v46;
    RCConfig = LdrRscIsTypeExist(v54, v46, 0, &v42);
    if ( RCConfig < 0 )
    {
      v14 = 0;
      goto LABEL_28;
    }
  }
  else if ( RCConfig == -1073741701 )
  {
    goto LABEL_108;
  }
LABEL_14:
  if ( (v10 & 6) == 0 )
    goto LABEL_18;
  if ( !v54 || (*(_BYTE *)(v54 + 16) & 1) == 0 )
  {
    RCConfig = -1073020927;
LABEL_17:
    v40 = 0;
    goto LABEL_18;
  }
  if ( (v42 & 0x20000) != 0 )
  {
    RCConfig = -1073741686;
    goto LABEL_17;
  }
  LODWORD(P[0]) = 0;
  Size = 0;
  if ( !a7 )
  {
    P[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
    if ( P[1] )
    {
      HIDWORD(P[0]) = 32;
      Internal_EnumUILanguages((__int64 (__fastcall *)(PVOID, __int64))EnumUILanguagesProcW, 0, (__int64)P, 1);
      for ( i = v45; ; i = 1 )
      {
        if ( i )
          GetInstalledMUILanguages(Address);
        if ( !LODWORD(P[0]) )
        {
          v36 = (LANGID *)P[1];
          *v36 = GetUserDefaultUILanguage();
LABEL_106:
          LODWORD(P[0]) = 1;
        }
LABEL_36:
        if ( Size < LODWORD(P[0]) )
          break;
        if ( v45 || (v10 & 4) != 0 || a7 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
          P[1] = 0;
          v15 = v41;
          goto LABEL_18;
        }
        v45 = 1;
        v70 = 1;
      }
      if ( a7 )
        v22 = a7;
      else
        v22 = *((_WORD *)P[1] + Size);
      for ( j = 0; ; ++j )
      {
        v60 = j;
        if ( j >= v43 )
          break;
        if ( v71[j] == v22 )
          goto LABEL_45;
      }
      if ( (int)LdrLoadAlternateResourceModuleEx(Address, v22, &v66, 0, 128) < 0 )
      {
        RCConfig = -1073020927;
LABEL_45:
        ++Size;
        goto LABEL_36;
      }
      v48 = v22;
      RCConfig = EnumFindResource(v66, v46, v47, v22, v10, (__int64)&v68);
      if ( RCConfig < 0 )
        goto LABEL_45;
      v40 = 1;
      v24 = v43;
      v71[v43] = v22;
      v43 = v24 + 1;
      v67 = v24 + 1;
      if ( v72 )
      {
        v25 = v51;
        v26 = v50;
      }
      else
      {
        v25 = (void *)v64;
        v26 = (void *)UnicodeString;
      }
      if ( v58(v57, v26, v25, v22, a5) )
        goto LABEL_45;
      RCConfig = -1073020921;
    }
    else
    {
      RCConfig = -1073741801;
    }
    goto LABEL_108;
  }
  if ( (v10 & 4) == 0 || (unsigned int)IsValidInstalledLang(a7) )
    goto LABEL_106;
  RCConfig = -1073020927;
LABEL_18:
  if ( (v10 & 1) == 0 )
    goto LABEL_109;
  v16 = v46;
  GetMunResourceModuleForEnumIfExist((unsigned int)&BaseAddress, v10, v46, (unsigned int)&v54, (__int64)&v42);
  if ( (v42 & 0x40000) != 0 )
  {
    RCConfig = -1073741686;
    v20 = 0;
    goto LABEL_118;
  }
  if ( v15 )
  {
    LOBYTE(v17) = 1;
    if ( (int)LdrpResGetMappingSize(BaseAddress, &v55, 256, v17) < 0 )
      v55 = 0;
  }
  v18 = v55;
  v19 = BaseAddress;
  Address = 0;
  if ( !BaseAddress )
    goto LABEL_104;
  if ( (v10 & 8) == 0 )
  {
    v63 = RtlImageDirectoryEntryToData(BaseAddress, 1u, 2u, &Size);
    RCConfig = v63 == 0 ? 0xC0000089 : 0;
    goto LABEL_26;
  }
  if ( !v55 )
  {
LABEL_104:
    RCConfig = -1073741811;
    goto LABEL_26;
  }
  RCConfig = LdrpResGetResourceDirectory(BaseAddress, v55, 4096, &v63, &Address);
  if ( RCConfig == -1073741686 )
    RCConfig = LdrpResGetResourceDirectory(v19, v18, 0, &v63, &Address);
LABEL_26:
  v16 = v46;
  if ( RCConfig < 0 )
    goto LABEL_28;
  RCConfig = EnumFindResource((_DWORD)BaseAddress, v46, v47, 0, v10 | 0x400, (__int64)&v53);
  if ( RCConfig < 0 )
    goto LABEL_28;
  v27 = v41;
  if ( v41 )
  {
    v35 = v53 + 16;
    if ( v53 + 16 < v53
      || v35 < ((unsigned __int64)BaseAddress & 0xFFFFFFFFFFFFFFFCuLL)
      || v35 > v55 + ((unsigned __int64)BaseAddress & 0xFFFFFFFFFFFFFFFCuLL) )
    {
      goto LABEL_80;
    }
    v27 = v41;
  }
  v28 = (unsigned __int16 *)(v53 + 16);
  v69 = (unsigned __int16 *)(v53 + 16);
  if ( *(_WORD *)(v53 + 12) )
  {
    RCConfig = -1073741701;
    goto LABEL_28;
  }
  if ( !v27
    || !*(_WORD *)(v53 + 14)
    || (v56 = 0, v34 = 8LL * *(unsigned __int16 *)(v53 + 14), is_mul_ok(*(unsigned __int16 *)(v53 + 14), 8u))
    && v34 + v53 >= ((unsigned __int64)BaseAddress & 0xFFFFFFFFFFFFFFFCuLL)
    && v34 + v53 <= v55 + ((unsigned __int64)BaseAddress & 0xFFFFFFFFFFFFFFFCuLL) )
  {
    Size = 0;
    v29 = 0;
    while ( 2 )
    {
      if ( v29 >= *(unsigned __int16 *)(v53 + 14) )
        goto LABEL_28;
      v30 = *v28;
      for ( k = 0; ; ++k )
      {
        v61 = k;
        if ( k >= v43 )
          break;
        if ( v71[k] == (_WORD)v30 )
          goto LABEL_68;
      }
      v38 = 1;
      v62 = 1;
      if ( v72 )
      {
        v32 = v51;
        v33 = v50;
      }
      else
      {
        v32 = (void *)v64;
        v33 = (void *)UnicodeString;
      }
      if ( v58(v57, v33, v32, v30, a5) )
      {
LABEL_68:
        v28 += 4;
        v69 = v28;
        v29 = ++Size;
        continue;
      }
      break;
    }
    RCConfig = -1073020921;
    goto LABEL_73;
  }
LABEL_80:
  BaseSetLastNTError(3221225595LL);
LABEL_73:
  v14 = 0;
LABEL_28:
  v20 = v38;
LABEL_118:
  BaseDllFreeResourceId(v16);
  BaseDllFreeResourceId(v47);
  if ( P[1] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    P[1] = 0;
  }
  if ( ((unsigned __int64)v50 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v50);
  if ( ((unsigned __int64)v51 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v51);
  if ( ((v10 & 1) == 0 || (v10 & 6) == 0 || v40 || v20) && ((v10 & 6) == 0 || (v10 & 1) != 0 || v40) )
  {
    if ( (v10 & 1) != 0 && (v10 & 6) == 0 )
      v14 &= -(v20 != 0);
    if ( v14 )
      RCConfig = 0;
  }
  else
  {
    v14 = 0;
  }
  BaseSetLastNTError((unsigned int)RCConfig);
  return v14;
}

```

## disassembly

```asm
0x18007ef34  mov     r11, rsp
0x18007ef37  push    rbx
0x18007ef38  push    rsi
0x18007ef39  push    rdi
0x18007ef3a  push    r12
0x18007ef3c  push    r13
0x18007ef3e  push    r14
0x18007ef40  push    r15
0x18007ef42  sub     rsp, 230h
0x18007ef49  mov     rax, cs:__security_cookie
0x18007ef50  xor     rax, rsp
0x18007ef53  mov     [rsp+268h+var_48], rax
0x18007ef5b  mov     [rsp+268h+var_1A0], r9
0x18007ef63  mov     r14, r8
0x18007ef66  mov     [rsp+268h+var_180], r8
0x18007ef6e  mov     [rsp+268h+UnicodeString], rdx
0x18007ef76  mov     r13, rcx
0x18007ef79  mov     [rsp+268h+var_1A8], rcx
0x18007ef81  xor     edi, edi
0x18007ef83  mov     [rsp+268h+Size], edi
0x18007ef87  mov     [r11-1C8h], rdi
0x18007ef8e  mov     [r11-188h], rdi
0x18007ef95  mov     [r11-160h], rdi
0x18007ef9c  mov     [r11-170h], rdi
0x18007efa3  xorps   xmm0, xmm0
0x18007efa6  movups  xmmword ptr [rsp+268h+P], xmm0
0x18007efab  mov     [r11-1B8h], rdi
0x18007efb2  mov     [r11-1E0h], rdi
0x18007efb9  mov     [rsp+268h+var_198], edi
0x18007efc0  mov     [r11-1D8h], rdi
0x18007efc7  mov     dword ptr [rsp+268h+var_1B0], edi
0x18007efce  mov     [r11-1C0h], rdi
0x18007efd5  mov     [rsp+268h+var_220], edi
0x18007efd9  mov     ecx, [rsp+268h+arg_28]
0x18007efe0  test    ecx, 0FFFFFFE0h
0x18007efe6  jnz     loc_18007F9D4
0x18007efec  mov     eax, ecx
0x18007efee  and     eax, 8
0x18007eff1  mov     [rsp+268h+var_224], eax
0x18007eff5  mov     ebx, ecx
0x18007eff7  and     ebx, 10h
0x18007effa  mov     r15d, ecx
0x18007effd  or      r15d, 3
0x18007f001  test    cl, 17h
0x18007f004  cmovnz  r15d, ecx
0x18007f008  mov     eax, ecx
0x18007f00a  and     eax, 6
0x18007f00d  lea     r12d, [rdi+1]
0x18007f011  cmp     al, 6
0x18007f013  jz      loc_18007F9F8
0x18007f019  test    ebx, ebx
0x18007f01b  jnz     loc_18007F9F3
0x18007f021  mov     eax, r12d
0x18007f024  mov     [rsp+268h+arg_28], r15d
0x18007f02c  test    eax, eax
0x18007f02e  jz      loc_18007F9D4
0x18007f034  mov     rcx, rdx
0x18007f037  call    BaseDllMapResourceIdW
0x18007f03c  mov     rsi, rax
0x18007f03f  mov     [rsp+268h+var_200], rax
0x18007f044  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007f048  jz      loc_18007F9D4
0x18007f04e  mov     rcx, r14
0x18007f051  call    BaseDllMapResourceIdW
0x18007f056  mov     [rsp+268h+var_1F8], rax
0x18007f05b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007f05f  jz      loc_18007F9CC
0x18007f065  mov     esi, edi
0x18007f067  mov     [rsp+268h+var_21C], edi
0x18007f06b  mov     [rsp+268h+var_208], edi
0x18007f06f  mov     r14d, r12d
0x18007f072  mov     [rsp+268h+var_234], r12d
0x18007f077  mov     eax, edi
0x18007f079  mov     [rsp+268h+var_230], eax
0x18007f07d  mov     [rsp+268h+var_228], edi
0x18007f081  test    r13, r13
0x18007f084  jnz     short loc_18007F093
0x18007f086  mov     rax, gs:60h
0x18007f08f  mov     r13, [rax+10h]
0x18007f093  mov     [rsp+268h+Address], r13
0x18007f09b  mov     [rsp+268h+BaseAddress], r13
0x18007f0a3  and     [rsp+268h+arg_38], r12d
0x18007f0ab  jnz     loc_18007F70F
0x18007f0b1  test    ebx, ebx
0x18007f0b3  mov     ebx, [rsp+268h+var_224]
0x18007f0b7  jz      loc_18007F39E
0x18007f0bd  test    r15b, 6
0x18007f0c1  jz      short loc_18007F0E1
0x18007f0c3  mov     rax, [rsp+268h+var_1C0]
0x18007f0cb  test    rax, rax
0x18007f0ce  jnz     loc_18007F670
0x18007f0d4  mov     esi, 0C00B0001h
0x18007f0d9  mov     [rsp+268h+var_238], esi
0x18007f0dd  mov     [rsp+268h+var_228], edi
0x18007f0e1  test    r12b, r15b
0x18007f0e4  jz      loc_18007F7F9
0x18007f0ea  lea     rax, [rsp+268h+var_220]
0x18007f0ef  mov     [rsp+268h+var_248], rax
0x18007f0f4  lea     r9, [rsp+268h+var_1C0]
0x18007f0fc  mov     r13, [rsp+268h+var_200]
0x18007f101  mov     r8, r13
0x18007f104  mov     edx, r15d
0x18007f107  lea     rcx, [rsp+268h+BaseAddress]
0x18007f10f  call    GetMunResourceModuleForEnumIfExist
0x18007f114  test    [rsp+268h+var_220], 40000h
0x18007f11c  jnz     loc_18007F785
0x18007f122  test    ebx, ebx
0x18007f124  jnz     loc_18007F85B
0x18007f12a  mov     r13, [rsp+268h+var_1B8]
0x18007f132  mov     rbx, [rsp+268h+BaseAddress]
0x18007f13a  mov     [rsp+268h+Address], rdi
0x18007f142  test    rbx, rbx
0x18007f145  jz      loc_18007F7CF
0x18007f14b  test    r15b, 8
0x18007f14f  jz      loc_18007F5E2
0x18007f155  test    r13, r13
0x18007f158  jz      loc_18007F7CF
0x18007f15e  lea     rax, [rsp+268h+Address]
0x18007f166  mov     [rsp+268h+var_248], rax
0x18007f16b  lea     r9, [rsp+268h+var_188]
0x18007f173  mov     r8d, 1000h
0x18007f179  mov     rdx, r13
0x18007f17c  mov     rcx, rbx
0x18007f17f  call    cs:__imp_LdrpResGetResourceDirectory
0x18007f186  nop     dword ptr [rax+rax+00h]
0x18007f18b  mov     esi, eax
0x18007f18d  cmp     eax, 0C000008Ah
0x18007f192  jz      loc_18007F79E
0x18007f198  mov     [rsp+268h+var_238], esi
0x18007f19c  mov     r13, [rsp+268h+var_200]
0x18007f1a1  test    esi, esi
0x18007f1a3  js      short loc_18007F1E3
0x18007f1a5  mov     eax, r15d
0x18007f1a8  bts     eax, 0Ah
0x18007f1ac  xor     r9d, r9d
0x18007f1af  lea     rcx, [rsp+268h+var_1C8]
0x18007f1b7  mov     [rsp+268h+var_240], rcx
0x18007f1bc  mov     dword ptr [rsp+268h+var_248], eax
0x18007f1c0  mov     r8, [rsp+268h+var_1F8]
0x18007f1c5  mov     rdx, r13
0x18007f1c8  mov     rcx, [rsp+268h+BaseAddress]
0x18007f1d0  call    EnumFindResource
0x18007f1d5  mov     esi, eax
0x18007f1d7  mov     [rsp+268h+var_238], eax
0x18007f1db  test    eax, eax
0x18007f1dd  jns     loc_18007F3F1
0x18007f1e3  mov     ebx, [rsp+268h+var_230]
0x18007f1e7  jmp     loc_18007F899
0x18007f1ec  mov     eax, [rsp+268h+var_208]
0x18007f1f0  test    eax, eax
0x18007f1f2  jnz     loc_18007F370
0x18007f1f8  test    r15b, 4
0x18007f1fc  jnz     loc_18007F370
0x18007f202  test    r13w, r13w
0x18007f206  jnz     loc_18007F370
0x18007f20c  mov     ebx, r12d
0x18007f20f  mov     [rsp+268h+var_208], ebx
0x18007f213  mov     [rsp+268h+var_150], ebx
0x18007f21a  test    ebx, ebx
0x18007f21c  jz      short loc_18007F230
0x18007f21e  lea     rdx, [rsp+268h+P]
0x18007f223  mov     rcx, [rsp+268h+Address]; Address
0x18007f22b  call    GetInstalledMUILanguages
0x18007f230  cmp     dword ptr [rsp+268h+P], edi
0x18007f234  jz      loc_18007F842
0x18007f23a  mov     eax, dword ptr [rsp+268h+P]
0x18007f23e  cmp     [rsp+268h+Size], eax
0x18007f242  jnb     short loc_18007F1EC
0x18007f244  test    r13w, r13w
0x18007f248  jnz     loc_18007F795
0x18007f24e  mov     ecx, [rsp+268h+Size]
0x18007f252  mov     rax, [rsp+268h+P+8]
0x18007f257  movzx   ebx, word ptr [rax+rcx*2]
0x18007f25b  mov     ecx, edi
0x18007f25d  mov     [rsp+268h+var_194], ecx
0x18007f264  cmp     ecx, [rsp+268h+var_21C]
0x18007f268  jnb     short loc_18007F27B
0x18007f26a  mov     eax, ecx
0x18007f26c  cmp     [rsp+rax*2+268h+var_148], bx
0x18007f274  jz      short loc_18007F2B6
0x18007f276  add     ecx, r12d
0x18007f279  jmp     short loc_18007F25D
0x18007f27b  mov     dword ptr [rsp+268h+var_248], 80h
0x18007f283  xor     r9d, r9d
0x18007f286  lea     r8, [rsp+268h+var_170]
0x18007f28e  movzx   edx, bx
0x18007f291  mov     rcx, [rsp+268h+Address]
0x18007f299  call    cs:__imp_LdrLoadAlternateResourceModuleEx
0x18007f2a0  nop     dword ptr [rax+rax+00h]
0x18007f2a5  mov     [rsp+268h+var_238], eax
0x18007f2a9  test    eax, eax
0x18007f2ab  jns     short loc_18007F2C0
0x18007f2ad  mov     esi, 0C00B0001h
0x18007f2b2  mov     [rsp+268h+var_238], esi
0x18007f2b6  add     [rsp+268h+Size], r12d
0x18007f2bb  jmp     loc_18007F23A
0x18007f2c0  movzx   r9d, bx
0x18007f2c4  mov     [rsp+268h+var_1F0], r9
0x18007f2c9  lea     rax, [rsp+268h+var_160]
0x18007f2d1  mov     [rsp+268h+var_240], rax
0x18007f2d6  mov     dword ptr [rsp+268h+var_248], r15d
0x18007f2db  mov     r8, [rsp+268h+var_1F8]
0x18007f2e0  mov     rdx, [rsp+268h+var_200]
0x18007f2e5  mov     rcx, [rsp+268h+var_170]
0x18007f2ed  call    EnumFindResource
0x18007f2f2  mov     esi, eax
0x18007f2f4  mov     [rsp+268h+var_238], eax
0x18007f2f8  test    eax, eax
0x18007f2fa  js      short loc_18007F2B6
0x18007f2fc  mov     [rsp+268h+var_228], r12d
0x18007f301  mov     ecx, [rsp+268h+var_21C]
0x18007f305  mov     [rsp+rcx*2+268h+var_148], bx
0x18007f30d  add     ecx, r12d
0x18007f310  mov     [rsp+268h+var_21C], ecx
0x18007f314  mov     [rsp+268h+var_168], ecx
0x18007f31b  mov     rax, [rsp+268h+arg_20]
0x18007f323  movzx   r9d, bx
0x18007f327  mov     rcx, [rsp+268h+var_1A8]
0x18007f32f  mov     [rsp+268h+var_248], rax
0x18007f334  mov     rax, [rsp+268h+var_1A0]
0x18007f33c  cmp     [rsp+268h+arg_38], edi
0x18007f343  jnz     loc_18007F6FA
0x18007f349  mov     r8, [rsp+268h+var_180]
0x18007f351  mov     rdx, [rsp+268h+UnicodeString]
0x18007f359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f35e  test    eax, eax
0x18007f360  jnz     loc_18007F2B6
0x18007f366  mov     esi, 0C00B0007h
0x18007f36b  jmp     loc_18007F7EE
0x18007f370  mov     rcx, gs:60h
0x18007f379  mov     r8, [rsp+268h+P+8]; P
0x18007f37e  xor     edx, edx; Flags
0x18007f380  mov     rcx, [rcx+30h]; HeapHandle
0x18007f384  call    cs:__imp_RtlFreeHeap
0x18007f38b  nop     dword ptr [rax+rax+00h]
0x18007f390  mov     [rsp+268h+P+8], rdi
0x18007f395  mov     ebx, [rsp+268h+var_224]
0x18007f399  jmp     loc_18007F0E1
0x18007f39e  mov     byte ptr [rsp+268h+var_248], r12b
0x18007f3a3  lea     r8, [rsp+268h+var_1C0]
0x18007f3ab  xor     edx, edx
0x18007f3ad  mov     rcx, r13
0x18007f3b0  test    ebx, ebx
0x18007f3b2  jz      loc_18007F657
0x18007f3b8  xor     r9d, r9d
0x18007f3bb  call    cs:__imp_LdrResGetRCConfig
0x18007f3c2  nop     dword ptr [rax+rax+00h]
0x18007f3c7  mov     esi, eax
0x18007f3c9  cmp     eax, 0C00B0003h
0x18007f3ce  jz      loc_18007F81D
0x18007f3d4  mov     [rsp+268h+var_238], esi
0x18007f3d8  test    esi, esi
0x18007f3da  jns     loc_18007F619
0x18007f3e0  cmp     esi, 0C000007Bh
0x18007f3e6  jnz     loc_18007F0BD
0x18007f3ec  jmp     loc_18007F7F2
0x18007f3f1  mov     eax, [rsp+268h+var_224]
0x18007f3f5  test    eax, eax
0x18007f3f7  jnz     loc_18007F552
0x18007f3fd  mov     r8, [rsp+268h+var_1C8]
0x18007f405  lea     rbx, [r8+10h]
0x18007f409  mov     [rsp+268h+var_158], rbx
0x18007f411  cmp     [r8+0Ch], di
0x18007f416  jnz     loc_18007F4F6
0x18007f41c  test    eax, eax
0x18007f41e  jnz     loc_18007F504
0x18007f424  mov     [rsp+268h+Size], edi
0x18007f428  mov     edx, edi
0x18007f42a  mov     rax, [rsp+268h+var_1C8]
0x18007f432  movzx   ecx, word ptr [rax+0Eh]
0x18007f436  cmp     edx, ecx
0x18007f438  jnb     loc_18007F5B1
0x18007f43e  movzx   r9d, word ptr [rbx]
0x18007f442  mov     ecx, edi
0x18007f444  mov     [rsp+268h+var_190], ecx
0x18007f44b  cmp     ecx, [rsp+268h+var_21C]
0x18007f44f  jb      short loc_18007F4BA
0x18007f451  mov     eax, r12d
0x18007f454  mov     [rsp+268h+var_230], eax
0x18007f458  mov     [rsp+268h+var_18C], eax
0x18007f45f  mov     rax, [rsp+268h+arg_20]
0x18007f467  mov     rcx, [rsp+268h+var_1A8]
0x18007f46f  mov     [rsp+268h+var_248], rax
0x18007f474  mov     rax, [rsp+268h+var_1A0]
0x18007f47c  cmp     [rsp+268h+arg_38], edi
0x18007f483  jnz     short loc_18007F4CF
0x18007f485  mov     r8, [rsp+268h+var_180]
0x18007f48d  mov     rdx, [rsp+268h+UnicodeString]
0x18007f495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f49a  test    eax, eax
0x18007f49c  jz      short loc_18007F4E1
0x18007f49e  add     rbx, 8
0x18007f4a2  mov     [rsp+268h+var_158], rbx
0x18007f4aa  mov     edx, [rsp+268h+Size]
0x18007f4ae  add     edx, r12d
0x18007f4b1  mov     [rsp+268h+Size], edx
0x18007f4b5  jmp     loc_18007F42A
0x18007f4ba  mov     eax, ecx
0x18007f4bc  cmp     [rsp+rax*2+268h+var_148], r9w
0x18007f4c5  jz      short loc_18007F49E
  ... truncated ...
```
