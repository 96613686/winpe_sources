# RtlGetFileMUIPath

- ea: `0x18005d8e0`
- end: `0x18005e55b`
- name: `RtlGetFileMUIPath`
- size: `3195`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009d60`
- `0x18000aab0`
- `0x18000b730`
- `0x18000d3e0`
- `0x1800159b0`
- `0x18001861c`
- `0x18001b984`
- `0x180054eb0`
- `0x18005c420`
- `0x18005d8e0`
- `0x18005e570`
- `0x18005e604`
- `0x1800fa8f8`
- `0x1800ffee8`
- `0x1801122c4`
- `0x180127d10`
- `0x18012c830`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
__int64 __fastcall RtlGetFileMUIPath(
        unsigned int a1,
        __int64 a2,
        wchar_t *a3,
        int *a4,
        __int64 a5,
        __int64 a6,
        unsigned __int64 *a7)
{
  __int64 v8; // rbx
  unsigned int v9; // eax
  unsigned __int64 v10; // r12
  wchar_t *v11; // rsi
  __int64 result; // rax
  unsigned int v13; // edi
  __int64 Heap_0; // rax
  unsigned __int64 v15; // r13
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int64 k; // rcx
  wchar_t *v19; // r15
  char v20; // r12
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // r14
  bool v23; // r15
  wchar_t *v24; // rdi
  unsigned __int64 v25; // r12
  int *v26; // rdx
  wchar_t *v27; // r15
  unsigned __int64 v28; // rbx
  char v29; // r15
  char v30; // r10
  unsigned __int64 v31; // rax
  __int64 v32; // r10
  __int64 v33; // r9
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rax
  bool v37; // zf
  wchar_t *v38; // rbx
  unsigned int v39; // ebx
  __int64 v40; // rdx
  __int16 v41; // ax
  __int64 v42; // rax
  wchar_t *v43; // rax
  int ThreadPreferredUILanguages; // eax
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rdx
  unsigned __int64 v47; // rax
  wchar_t *i; // rbx
  char v49; // r12
  size_t v50; // rax
  int MUIRedirectedFilePath; // eax
  __int64 v52; // rax
  bool v53; // r14
  int v54; // ecx
  wchar_t *v55; // rax
  __int64 v56; // rax
  wchar_t *v57; // rax
  char v58; // bl
  size_t v59; // rax
  unsigned __int64 v60; // rax
  char v61; // al
  __int64 v62; // rcx
  unsigned __int64 v63; // rcx
  wchar_t *j; // rbx
  __int64 v65; // rax
  char v66; // r12
  size_t v67; // rax
  int v68; // eax
  __int64 v69; // rax
  __int64 v70; // rax
  size_t v71; // rax
  int v72; // eax
  __int64 v73; // rax
  size_t v74; // rax
  size_t v75; // rax
  wchar_t *v76; // rax
  int v77; // [rsp+20h] [rbp-E0h]
  int v78; // [rsp+28h] [rbp-D8h]
  char v79; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v80; // [rsp+48h] [rbp-B8h] BYREF
  bool v81; // [rsp+50h] [rbp-B0h]
  wchar_t *String2[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v83; // [rsp+70h] [rbp-90h]
  unsigned int v84; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v85; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v86; // [rsp+80h] [rbp-80h]
  wchar_t *v87; // [rsp+88h] [rbp-78h]
  int *v88; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  __int128 v90; // [rsp+A0h] [rbp-60h] BYREF
  int v91; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v92; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v93; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *String1; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v95; // [rsp+D0h] [rbp-30h]
  __int64 v96; // [rsp+D8h] [rbp-28h]
  wchar_t *v97; // [rsp+E0h] [rbp-20h]
  __int64 v98; // [rsp+E8h] [rbp-18h]
  __int64 v99; // [rsp+F0h] [rbp-10h]
  wchar_t *v100; // [rsp+F8h] [rbp-8h]
  __int64 v101; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 *v102; // [rsp+108h] [rbp+8h]
  wchar_t String[4]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v104; // [rsp+118h] [rbp+18h]

  v95 = a5;
  v96 = a6;
  *(_QWORD *)String = 0;
  v104 = 0;
  v8 = a1;
  v88 = a4;
  v9 = a1 >> 10;
  v10 = 0;
  LOBYTE(v9) = (a1 & 0x400) != 0;
  v87 = a3;
  v102 = a7;
  v11 = 0;
  v83 = 0;
  v80 = 0;
  v101 = 0;
  *(_QWORD *)&v90 = 0;
  v91 = 0;
  v97 = 0;
  v92 = 0;
  String1 = 0;
  v84 = 0;
  v85 = 0;
  v93 = 0;
  Src = 0;
  v86 = v9;
  *(_OWORD *)String2 = 0;
  if ( !a2 || !a7 )
    return 3221225485LL;
  result = RtlpCreateProcessRegistryInfo(&Src);
  v13 = result;
  if ( (int)result >= 0 )
  {
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 522);
    v15 = Heap_0;
    if ( !Heap_0 )
      return 3221225495LL;
    if ( (unsigned int)RtlGetFullPathName_U(a2, 520, Heap_0, &v93) - 1 > 0x206 || !v93 || v93 <= v15 || v93 >= v15 + 520 )
      goto LABEL_11;
    *(_WORD *)(v93 - 2) = 0;
    v16 = *a7;
    if ( *a7 )
    {
      v22 = 0;
      v80 = 0;
      v29 = 0;
      v98 = 0;
      v30 = v16;
      v31 = v16 >> 4;
      v32 = v30 & 0xF;
      v99 = v32;
      v33 = (unsigned int)v32;
      v34 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            v35 = v31 & 0xFFF;
            v31 >>= 12;
            v33 ^= v35;
            if ( v34 )
              break;
            v29 = v35;
            v98 = v35;
            v34 = 1;
          }
          if ( v34 != 2 )
            break;
          v10 = (unsigned int)v35;
          v83 = v35;
          v34 = 3;
        }
        if ( v34 == 3 )
          break;
        if ( (unsigned __int64)++v34 >= 4 )
          goto LABEL_54;
      }
      v22 = v35;
      v80 = v35;
LABEL_54:
      if ( ((v31 ^ v33) & 0xFFF) != 0 )
      {
        v13 = -1073741776;
        goto LABEL_33;
      }
      if ( v22 > v10 )
      {
        v13 = -2147483642;
        goto LABEL_33;
      }
      if ( (v29 & 0x20) != 0 )
        v39 = 2;
      else
        v39 = (v29 & 0x40 | 0x20u) >> 5;
      v23 = (v29 & 4) == 0;
      v79 = v32 & 1;
      v81 = v23;
      goto LABEL_76;
    }
    if ( (v8 & 0xC) == 0xC
      || (v8 & 0x10) != 0 && (v8 & 0x20) != 0
      || (v40 = v8 & 0x40, (v8 & 0x10) != 0) && (v8 & 0x40) != 0
      || (v8 & 0x20) != 0 && (v8 & 0x40) != 0
      || (v8 & 0x200) != 0 && (v8 & 0x100) != 0
      || (v8 & 0x10) != 0 && (v8 & 0x20) != 0 && (v8 & 0x40) != 0 )
    {
LABEL_11:
      v13 = -1073741811;
LABEL_33:
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v15);
      return v13;
    }
    v99 = 0;
    v41 = v8;
    v98 = v8;
    if ( (v8 & 0x20) != 0 )
      v39 = 2;
    else
      v39 = (unsigned __int64)(v8 & 0x40 | 0x20) >> 5;
    v23 = (v41 & 4) == 0;
    v81 = v23;
    if ( (v41 & 0x200) != 0 )
    {
      v79 = 0;
    }
    else if ( (v41 & 0x100) != 0 || (unsigned __int8)RtlpFileIsWin32WithRCManifest(a2, v40) )
    {
      v79 = 1;
      v99 = 1;
    }
    else
    {
      v79 = 0;
    }
    switch ( v39 )
    {
      case 1u:
        LODWORD(v80) = 0;
        RtlGetThreadPreferredUILanguages(0x30u, &v84, 0, &v80);
        if ( !(_DWORD)v80 )
          goto LABEL_33;
        v42 = LdrpCalcAllocSize((unsigned int)v80, 2);
        if ( !v42 )
        {
          v13 = -1073741675;
          goto LABEL_33;
        }
        v43 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v42);
        v97 = v43;
        v11 = v43;
        v92 = v43;
        if ( !v43 )
        {
          v13 = -1073741801;
          goto LABEL_29;
        }
        ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(0x30u, &v84, v43, &v80);
        if ( ThreadPreferredUILanguages < 0 )
        {
          v13 = ThreadPreferredUILanguages;
          goto LABEL_29;
        }
        v45 = v84;
        break;
      case 2u:
        RtlpMUIGetAllInstalledLang(Src, &v92, &v80);
        v11 = v92;
        v45 = v80;
        v97 = v92;
        break;
      case 3u:
        RtlpMUIEnumerateFolder(v15, &v80, &String1);
        v45 = v80;
        break;
      default:
        goto LABEL_75;
    }
    v83 = v45;
LABEL_75:
    v22 = 0;
    v80 = 0;
LABEL_76:
    v100 = 0;
    if ( v39 == 1 )
    {
      if ( v11 )
      {
        v46 = v83;
      }
      else
      {
        LODWORD(v80) = 0;
        RtlGetThreadPreferredUILanguages(0x30u, &v84, 0, &v80);
        if ( !(_DWORD)v80 )
          goto LABEL_111;
        v56 = LdrpCalcAllocSize((unsigned int)v80, 2);
        if ( !v56 )
        {
          v13 = -1073741675;
LABEL_31:
          if ( String1 )
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, String1);
          goto LABEL_33;
        }
        v57 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, v56);
        v11 = v57;
        if ( v57 && (int)RtlGetThreadPreferredUILanguages(0x30u, &v84, v57, &v80) >= 0 )
        {
          v46 = v83;
        }
        else
        {
LABEL_111:
          v46 = v83;
          v22 = v83;
        }
      }
      v47 = 0;
      for ( i = v11; v47 < v22; i += v62 + 1 )
      {
        if ( !i )
          break;
        if ( !*i )
          break;
        ++v47;
        v62 = -1;
        do
          v37 = i[++v62] == 0;
        while ( !v37 );
      }
      v24 = String2[1];
      v49 = v86;
      while ( v22 < v46 && *i )
      {
        HIDWORD(String2[0]) = 0;
        v24 = i;
        String2[1] = i;
        v50 = 2 * wcslen(i);
        if ( v50 >= 0xFFFE )
          LOWORD(v50) = -4;
        LOWORD(String2[0]) = v50;
        WORD1(String2[0]) = v50 + 2;
        LOBYTE(v78) = v49;
        LOBYTE(v77) = v79;
        v90 = *(_OWORD *)String2;
        MUIRedirectedFilePath = RtlpGetMUIRedirectedFilePath(&v90, v15, v93, v96, v77, v78, v95);
        if ( (int)(MUIRedirectedFilePath + 0x80000000) < 0 || MUIRedirectedFilePath == -1073741789 )
          break;
        ++v22;
        v52 = -1;
        do
          v37 = i[++v52] == 0;
        while ( !v37 );
        v46 = v83;
        i += v52 + 1;
      }
LABEL_16:
      v25 = v83;
      if ( v22 >= v83 )
      {
        v13 = -2147483642;
      }
      else
      {
        v26 = v88;
        if ( !v87 && !v88 )
          goto LABEL_40;
        if ( v23 )
          goto LABEL_19;
        v58 = RtlCultureNameToLCID(String2, &v91);
        if ( v58 )
          v58 = (int)RtlIntegerToUnicode((unsigned __int16)v91, 16, 4294967292LL, String) >= 0;
        v24 = String;
        v59 = wcslen(String);
        v26 = v88;
        v60 = 2 * v59;
        if ( v60 >= 0xFFFE )
          LOWORD(v60) = -4;
        LOWORD(String2[0]) = v60;
        if ( v58 )
        {
LABEL_19:
          v27 = v87;
          if ( v26 )
          {
            if ( v87 )
            {
              if ( *v26 > (unsigned int)(LOWORD(String2[0]) >> 1) )
              {
                v28 = LOWORD(String2[0]);
                memmove(v87, v24, LOWORD(String2[0]));
                v26 = v88;
                v27[v28 >> 1] = 0;
              }
            }
            else
            {
              *v26 = 85;
            }
          }
        }
        else
        {
LABEL_40:
          v27 = v87;
        }
        if ( !v95 || !v27 && v26 )
        {
          v13 = 0;
LABEL_27:
          if ( v100 )
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v100);
          goto LABEL_29;
        }
        v13 = 0;
      }
      *v102 = v99
            | ((v25 ^ v99 ^ v98 ^ (v22 + 1)) << 52) ^ 0xCB7000000CB70000uLL
            | (16 * (v98 | ((v25 | ((v22 + 1) << 12)) << 24) | 0xCB7000));
      goto LABEL_27;
    }
    if ( v39 == 2 )
    {
      if ( !v11 )
      {
        RtlpMUIGetAllInstalledLang(Src, &v92, &v101);
        v11 = v92;
      }
      v63 = 0;
      for ( j = v11; v63 < v22; j += v65 + 1 )
      {
        if ( !j )
          break;
        if ( !*j )
          break;
        ++v63;
        v65 = -1;
        do
          v37 = j[++v65] == 0;
        while ( !v37 );
      }
      v24 = String2[1];
      v66 = v86;
      while ( v22 < v83 && j && *j )
      {
        HIDWORD(String2[0]) = 0;
        v24 = j;
        String2[1] = j;
        v67 = 2 * wcslen(j);
        if ( v67 >= 0xFFFE )
          LOWORD(v67) = -4;
        LOWORD(String2[0]) = v67;
        WORD1(String2[0]) = v67 + 2;
        LOBYTE(v78) = v66;
        LOBYTE(v77) = v79;
        v90 = *(_OWORD *)String2;
        v68 = RtlpGetMUIRedirectedFilePath(&v90, v15, v93, v96, v77, v78, v95);
        if ( (int)(v68 + 0x80000000) < 0 || v68 == -1073741789 )
          break;
        ++v22;
        v69 = -1;
        do
          v37 = j[++v69] == 0;
        while ( !v37 );
        j += v69 + 1;
      }
      goto LABEL_16;
    }
    v38 = String1;
    if ( !String1 )
    {
      v61 = RtlpMUIEnumerateFolder(v15, &v90, &String1);
      v38 = String1;
      if ( !v61 )
        v22 = v83;
      v80 = v22;
    }
    v53 = 0;
    if ( v80 || (v54 = *v88) == 0 || !v87 )
    {
LABEL_12:
      v17 = v80;
      for ( k = 0; k < v80; v38 += v70 + 1 )
      {
        if ( !v38 )
          break;
        if ( !*v38 )
          break;
        ++k;
        v70 = -1;
        do
          v37 = v38[++v70] == 0;
        while ( !v37 );
      }
LABEL_13:
      v19 = String2[1];
      v20 = v86;
      v21 = v83;
      Src = String2[1];
      while ( v17 < v21 )
      {
        if ( v53 && wcsicmp(v38, v19) )
        {
          ++v17;
          v36 = -1;
          do
            v37 = v38[++v36] == 0;
          while ( !v37 );
          v38 += v36 + 1;
        }
        else
        {
          String2[0] = 0;
          v19 = v38;
          String2[1] = v38;
          if ( v38 )
          {
            v71 = 2 * wcslen(v38);
            if ( v71 >= 0xFFFE )
              LOWORD(v71) = -4;
            LOWORD(String2[0]) = v71;
            WORD1(String2[0]) = v71 + 2;
          }
          LOBYTE(v78) = v20;
          LOBYTE(v77) = v79;
          v90 = *(_OWORD *)String2;
          v72 = RtlpGetMUIRedirectedFilePath(&v90, v15, v93, v96, v77, v78, v95);
          if ( (int)(v72 + 0x80000000) < 0 || v72 == -1073741789 )
            break;
          ++v17;
          v73 = -1;
          do
            v37 = v38[++v73] == 0;
          while ( !v37 );
          v38 += v73 + 1;
        }
      }
      v11 = v97;
      v22 = v17;
      Src = v19;
      v23 = v81;
      v24 = (wchar_t *)Src;
      goto LABEL_16;
    }
    v55 = v87;
    while ( *v55 )
    {
      ++v55;
      if ( !--v54 )
      {
        v17 = v80;
        goto LABEL_13;
      }
    }
    if ( v23 )
    {
      String2[1] = v87;
      v74 = 2 * wcslen(v87);
      if ( v74 >= 0xFFFE )
        LOWORD(v74) = -4;
      LOWORD(String2[0]) = v74;
      WORD1(String2[0]) = v74 + 2;
      if ( (unsigned __int8)RtlCultureNameToLCID(String2, &v85) )
      {
        v17 = v80;
        v53 = 1;
        goto LABEL_13;
      }
      goto LABEL_12;
    }
    DWORD1(v90) = 0;
    *((_QWORD *)&v90 + 1) = v87;
    v75 = 2 * wcslen(v87);
    if ( v75 >= 0xFFFE )
      LOWORD(v75) = -4;
    LOWORD(v90) = v75;
    WORD1(v90) = v75 + 2;
    if ( (int)RtlUnicodeStringToInteger(&v90, 16, &v85) < 0 )
    {
LABEL_184:
      v17 = v80;
      goto LABEL_13;
    }
    v76 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8, 170);
    v100 = v76;
    if ( v76 )
    {
      String2[1] = v76;
      LODWORD(String2[0]) = 11141120;
      v53 = (unsigned __int8)RtlLCIDToCultureName(v85, String2) != 0;
      goto LABEL_184;
    }
LABEL_29:
    if ( v11 )
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v11);
    goto LABEL_31;
  }
  return result;
}

```

## disassembly

```asm
0x18005d8e0  push    rbp
0x18005d8e2  push    rbx
0x18005d8e3  push    rsi
0x18005d8e4  push    rdi
0x18005d8e5  push    r12
0x18005d8e7  push    r14
0x18005d8e9  push    r15
0x18005d8eb  lea     rbp, [rsp-30h]
0x18005d8f0  sub     rsp, 130h
0x18005d8f7  mov     rax, cs:__security_cookie
0x18005d8fe  xor     rax, rsp
0x18005d901  mov     [rbp+60h+var_40], rax
0x18005d905  mov     rax, [rbp+60h+arg_20]
0x18005d90c  xorps   xmm0, xmm0
0x18005d90f  mov     r15, [rbp+60h+arg_30]
0x18005d916  mov     r14, rdx
0x18005d919  mov     [rbp+60h+var_90], rax
0x18005d91d  mov     rax, [rbp+60h+arg_28]
0x18005d924  mov     [rbp+60h+var_88], rax
0x18005d928  xor     eax, eax
0x18005d92a  mov     qword ptr [rbp+60h+String], rax
0x18005d92e  mov     [rbp+60h+var_48], ax
0x18005d932  mov     ebx, ecx
0x18005d934  xor     ecx, ecx
0x18005d936  mov     eax, ebx
0x18005d938  mov     [rbp+60h+var_D0], r9
0x18005d93c  shr     eax, 0Ah
0x18005d93f  mov     r12d, ecx
0x18005d942  and     al, 1
0x18005d944  mov     [rbp+60h+var_D8], r8
0x18005d948  mov     [rbp+60h+var_58], r15
0x18005d94c  mov     esi, ecx
0x18005d94e  mov     [rsp+160h+var_F0], rcx
0x18005d953  mov     [rsp+160h+var_118], rcx
0x18005d958  mov     [rbp+60h+var_60], rcx
0x18005d95c  mov     qword ptr [rbp+60h+var_C0], rcx
0x18005d960  mov     [rbp+60h+var_B0], ecx
0x18005d963  mov     [rbp+60h+var_80], rcx
0x18005d967  mov     [rbp+60h+var_A8], rcx
0x18005d96b  mov     [rbp+60h+String1], rcx
0x18005d96f  mov     [rsp+160h+var_E8], ecx
0x18005d973  mov     [rsp+160h+var_E4], ecx
0x18005d977  mov     [rbp+60h+var_A0], rcx
0x18005d97b  mov     [rbp+60h+Src], rcx
0x18005d97f  mov     [rbp+60h+var_E0], eax
0x18005d982  movups  xmmword ptr [rsp+160h+String2], xmm0
0x18005d987  test    rdx, rdx
0x18005d98a  jz      loc_18005DBE3
0x18005d990  test    r15, r15
0x18005d993  jz      loc_18005DBE3
0x18005d999  lea     rcx, [rbp+60h+Src]
0x18005d99d  call    RtlpCreateProcessRegistryInfo
0x18005d9a2  mov     edi, eax
0x18005d9a4  test    eax, eax
0x18005d9a6  js      loc_18005DBC4
0x18005d9ac  mov     rcx, gs:60h
0x18005d9b5  mov     edx, 8
0x18005d9ba  mov     r8d, 20Ah
0x18005d9c0  mov     [rsp+160h+arg_0], r13
0x18005d9c8  mov     rcx, [rcx+30h]
0x18005d9cc  call    RtlAllocateHeap_0
0x18005d9d1  mov     r13, rax
0x18005d9d4  test    rax, rax
0x18005d9d7  jz      loc_18005E515
0x18005d9dd  lea     r9, [rbp+60h+var_A0]
0x18005d9e1  mov     r8, rax
0x18005d9e4  mov     edx, 208h
0x18005d9e9  mov     rcx, r14
0x18005d9ec  call    RtlGetFullPathName_U
0x18005d9f1  dec     eax
0x18005d9f3  cmp     eax, 206h
0x18005d9f8  ja      short loc_18005DA35
0x18005d9fa  mov     rcx, [rbp+60h+var_A0]
0x18005d9fe  test    rcx, rcx
0x18005da01  jz      short loc_18005DA35
0x18005da03  cmp     rcx, r13
0x18005da06  jbe     short loc_18005DA35
0x18005da08  lea     rax, [r13+208h]
0x18005da0f  cmp     rcx, rax
0x18005da12  jnb     short loc_18005DA35
0x18005da14  xor     r10d, r10d
0x18005da17  mov     [rcx-2], r10w
0x18005da1c  mov     rax, [r15]
0x18005da1f  test    rax, rax
0x18005da22  jnz     loc_18005DC16
0x18005da28  mov     eax, ebx
0x18005da2a  and     eax, 0Ch
0x18005da2d  cmp     al, 0Ch
0x18005da2f  jnz     loc_18005DD29
0x18005da35  mov     edi, 0C000000Dh
0x18005da3a  jmp     loc_18005DBA3
0x18005da3f  xor     r10d, r10d
0x18005da42  mov     rdi, [rsp+160h+var_118]
0x18005da47  mov     rcx, r10
0x18005da4a  test    rdi, rdi
0x18005da4d  jnz     loc_18005E2F0
0x18005da53  mov     r15, [rsp+160h+String2+8]
0x18005da58  mov     r12d, [rbp+60h+var_E0]
0x18005da5c  mov     rsi, [rsp+160h+var_F0]
0x18005da61  mov     [rbp+60h+Src], r15
0x18005da65  cmp     rdi, rsi
0x18005da68  jb      loc_18005DC68
0x18005da6e  mov     rsi, [rbp+60h+var_80]
0x18005da72  mov     r14, rdi
0x18005da75  mov     [rbp+60h+Src], r15
0x18005da79  movzx   r15d, [rsp+160h+var_110]
0x18005da7f  mov     rdi, [rbp+60h+Src]
0x18005da83  mov     r12, [rsp+160h+var_F0]
0x18005da88  cmp     r14, r12
0x18005da8b  jnb     loc_18005DBFA
0x18005da91  cmp     [rbp+60h+var_D8], 0
0x18005da96  mov     rdx, [rbp+60h+var_D0]
0x18005da9a  jz      loc_18005DC04
0x18005daa0  test    r15b, r15b
0x18005daa3  jz      loc_18005E0EE
0x18005daa9  mov     r15, [rbp+60h+var_D8]
0x18005daad  test    rdx, rdx
0x18005dab0  jz      short loc_18005DAE6
0x18005dab2  test    r15, r15
0x18005dab5  jz      loc_18005DCA9
0x18005dabb  movzx   ecx, word ptr [rsp+160h+String2]
0x18005dac0  mov     eax, ecx
0x18005dac2  shr     eax, 1
0x18005dac4  cmp     [rdx], eax
0x18005dac6  jbe     short loc_18005DAE6
0x18005dac8  mov     ebx, ecx
0x18005daca  mov     r8d, ecx; Size
0x18005dacd  mov     rcx, r15; void *
0x18005dad0  mov     rdx, rdi; Src
0x18005dad3  call    memmove
0x18005dad8  mov     rdx, [rbp+60h+var_D0]
0x18005dadc  shr     rbx, 1
0x18005dadf  xor     eax, eax
0x18005dae1  mov     [r15+rbx*2], ax
0x18005dae6  cmp     [rbp+60h+var_90], 0
0x18005daeb  jz      loc_18005DBF3
0x18005daf1  test    r15, r15
0x18005daf4  jz      loc_18005DBEA
0x18005dafa  xor     edi, edi
0x18005dafc  lea     rax, [r14+1]
0x18005db00  mov     r8, 0CB7000000CB70000h
0x18005db0a  mov     rcx, rax
0x18005db0d  xor     rax, [rbp+60h+var_78]
0x18005db11  xor     rax, [rbp+60h+var_70]
0x18005db15  shl     rcx, 0Ch
0x18005db19  xor     rax, r12
0x18005db1c  or      rcx, r12
0x18005db1f  shl     rax, 34h
0x18005db23  shl     rcx, 18h
0x18005db27  xor     rax, r8
0x18005db2a  or      rcx, [rbp+60h+var_78]
0x18005db2e  or      rcx, 0CB7000h
0x18005db35  shl     rcx, 4
0x18005db39  or      rcx, rax
0x18005db3c  mov     rax, [rbp+60h+var_58]
0x18005db40  or      rcx, [rbp+60h+var_70]
0x18005db44  mov     [rax], rcx
0x18005db47  mov     rax, [rbp+60h+var_68]
0x18005db4b  test    rax, rax
0x18005db4e  jz      short loc_18005DB67
0x18005db50  mov     rcx, gs:60h
0x18005db59  mov     r8, rax
0x18005db5c  xor     edx, edx
0x18005db5e  mov     rcx, [rcx+30h]
0x18005db62  call    RtlFreeHeap_0
0x18005db67  test    rsi, rsi
0x18005db6a  jz      short loc_18005DB83
0x18005db6c  mov     rcx, gs:60h
0x18005db75  mov     r8, rsi
0x18005db78  xor     edx, edx
0x18005db7a  mov     rcx, [rcx+30h]
0x18005db7e  call    RtlFreeHeap_0
0x18005db83  mov     rax, [rbp+60h+String1]
0x18005db87  test    rax, rax
0x18005db8a  jz      short loc_18005DBA3
0x18005db8c  mov     rcx, gs:60h
0x18005db95  mov     r8, rax
0x18005db98  xor     edx, edx
0x18005db9a  mov     rcx, [rcx+30h]
0x18005db9e  call    RtlFreeHeap_0
0x18005dba3  mov     rcx, gs:60h
0x18005dbac  mov     r8, r13
0x18005dbaf  xor     edx, edx
0x18005dbb1  mov     rcx, [rcx+30h]
0x18005dbb5  call    RtlFreeHeap_0
0x18005dbba  mov     eax, edi
0x18005dbbc  mov     r13, [rsp+160h+arg_0]
0x18005dbc4  mov     rcx, [rbp+60h+var_40]
0x18005dbc8  xor     rcx, rsp; StackCookie
0x18005dbcb  call    __security_check_cookie
0x18005dbd0  add     rsp, 130h
0x18005dbd7  pop     r15
0x18005dbd9  pop     r14
0x18005dbdb  pop     r12
0x18005dbdd  pop     rdi
0x18005dbde  pop     rsi
0x18005dbdf  pop     rbx
0x18005dbe0  pop     rbp
0x18005dbe1  retn
0x18005dbe3  mov     eax, 0C000000Dh
0x18005dbe8  jmp     short loc_18005DBC4
0x18005dbea  test    rdx, rdx
0x18005dbed  jz      loc_18005DAFA
0x18005dbf3  xor     edi, edi
0x18005dbf5  jmp     loc_18005DB47
0x18005dbfa  mov     edi, 80000006h
0x18005dbff  jmp     loc_18005DAFC
0x18005dc04  test    rdx, rdx
0x18005dc07  jnz     loc_18005DAA0
0x18005dc0d  mov     r15, [rbp+60h+var_D8]
0x18005dc11  jmp     loc_18005DAE6
0x18005dc16  mov     r14, r10
0x18005dc19  mov     [rsp+160h+var_118], r10
0x18005dc1e  mov     r15, r10
0x18005dc21  mov     [rbp+60h+var_78], r10
0x18005dc25  mov     r10, rax
0x18005dc28  shr     rax, 4
0x18005dc2c  and     r10d, 0Fh
0x18005dc30  mov     [rbp+60h+var_70], r10
0x18005dc34  mov     r9d, r10d
0x18005dc37  xor     ecx, ecx
0x18005dc39  mov     rdx, rax
0x18005dc3c  mov     r8, rcx
0x18005dc3f  and     edx, 0FFFh
0x18005dc45  shr     rax, 0Ch
0x18005dc49  xor     r9, rdx
0x18005dc4c  test    rcx, rcx
0x18005dc4f  jz      loc_18005E0DF
0x18005dc55  sub     r8, 2
0x18005dc59  jnz     short loc_18005DCB4
0x18005dc5b  mov     r12d, edx
0x18005dc5e  mov     [rsp+160h+var_F0], rdx
0x18005dc63  inc     rcx
0x18005dc66  jmp     short loc_18005DC39
0x18005dc68  test    r14b, r14b
0x18005dc6b  jz      loc_18005E32F
0x18005dc71  mov     rdx, r15; String2
0x18005dc74  mov     rcx, rbx; String1
0x18005dc77  call    _wcsicmp
0x18005dc7c  test    eax, eax
0x18005dc7e  jz      loc_18005E32F
0x18005dc84  inc     rdi
0x18005dc87  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18005dc8e  xchg    ax, ax
0x18005dc90  cmp     word ptr [rbx+rax*2+2], 0
0x18005dc96  lea     rax, [rax+1]
0x18005dc9a  jnz     short loc_18005DC90
0x18005dc9c  lea     rbx, [rbx+rax*2]
0x18005dca0  add     rbx, 2
0x18005dca4  jmp     loc_18005DA65
0x18005dca9  mov     dword ptr [rdx], 55h ; 'U'
0x18005dcaf  jmp     loc_18005DAE6
0x18005dcb4  cmp     r8, 1
0x18005dcb8  jnz     short loc_18005DCC4
0x18005dcba  mov     r14, rdx
0x18005dcbd  mov     [rsp+160h+var_118], rdx
0x18005dcc2  jmp     short loc_18005DCD1
0x18005dcc4  inc     rcx
0x18005dcc7  cmp     rcx, 4
0x18005dccb  jb      loc_18005DC39
0x18005dcd1  xor     r9, rax
0x18005dcd4  test    r9, 0FFFh
0x18005dcdb  jnz     loc_18005E51F
0x18005dce1  cmp     r14, r12
0x18005dce4  ja      loc_18005E529
0x18005dcea  test    r15b, 20h
0x18005dcee  jnz     loc_18005E40D
0x18005dcf4  movzx   ebx, r15b
0x18005dcf8  and     ebx, 40h
0x18005dcfb  or      ebx, 20h
0x18005dcfe  shr     ebx, 5
0x18005dd01  shr     r15b, 2
0x18005dd05  movzx   eax, r10b
0x18005dd09  and     al, 1
0x18005dd0b  not     r15b
0x18005dd0e  and     r15b, 1
0x18005dd12  mov     [rsp+160h+var_120], al
0x18005dd16  mov     [rsp+160h+var_110], r15b
0x18005dd1b  xor     r10d, r10d
0x18005dd1e  mov     r12d, 1
0x18005dd24  jmp     loc_18005DE4E
0x18005dd29  mov     ecx, ebx
0x18005dd2b  mov     eax, ebx
0x18005dd2d  and     ecx, 20h
0x18005dd30  and     eax, 10h
0x18005dd33  jnz     loc_18005DFDD
0x18005dd39  mov     edx, ebx
0x18005dd3b  and     edx, 40h
0x18005dd3e  test    eax, eax
0x18005dd40  jnz     loc_18005E0D2
0x18005dd46  test    ecx, ecx
0x18005dd48  jnz     loc_18005E508
0x18005dd4e  bt      ebx, 9
0x18005dd52  jb      loc_18005E07F
0x18005dd58  test    eax, eax
0x18005dd5a  jnz     loc_18005E08E
0x18005dd60  mov     [rbp+60h+var_70], r10
0x18005dd64  mov     rax, rbx
0x18005dd67  mov     [rbp+60h+var_78], rbx
0x18005dd6b  test    ecx, ecx
  ... truncated ...
```
