# RtlGetFileMUIPath

- ea: `0x18007a2c0`
- end: `0x18007af3b`
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
- `0x180071890`
- `0x180078e00`
- `0x18007a2c0`
- `0x18007af50`
- `0x18007afe4`
- `0x1800fb630`
- `0x180100508`
- `0x1801136b4`
- `0x180128800`
- `0x18012d320`
- `0x180162810`
- `0x180164280`

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
0x18007a2c0  push    rbp
0x18007a2c2  push    rbx
0x18007a2c3  push    rsi
0x18007a2c4  push    rdi
0x18007a2c5  push    r12
0x18007a2c7  push    r14
0x18007a2c9  push    r15
0x18007a2cb  lea     rbp, [rsp-30h]
0x18007a2d0  sub     rsp, 130h
0x18007a2d7  mov     rax, cs:__security_cookie
0x18007a2de  xor     rax, rsp
0x18007a2e1  mov     [rbp+60h+var_40], rax
0x18007a2e5  mov     rax, [rbp+60h+arg_20]
0x18007a2ec  xorps   xmm0, xmm0
0x18007a2ef  mov     r15, [rbp+60h+arg_30]
0x18007a2f6  mov     r14, rdx
0x18007a2f9  mov     [rbp+60h+var_90], rax
0x18007a2fd  mov     rax, [rbp+60h+arg_28]
0x18007a304  mov     [rbp+60h+var_88], rax
0x18007a308  xor     eax, eax
0x18007a30a  mov     qword ptr [rbp+60h+String], rax
0x18007a30e  mov     [rbp+60h+var_48], ax
0x18007a312  mov     ebx, ecx
0x18007a314  xor     ecx, ecx
0x18007a316  mov     eax, ebx
0x18007a318  mov     [rbp+60h+var_D0], r9
0x18007a31c  shr     eax, 0Ah
0x18007a31f  mov     r12d, ecx
0x18007a322  and     al, 1
0x18007a324  mov     [rbp+60h+var_D8], r8
0x18007a328  mov     [rbp+60h+var_58], r15
0x18007a32c  mov     esi, ecx
0x18007a32e  mov     [rsp+160h+var_F0], rcx
0x18007a333  mov     [rsp+160h+var_118], rcx
0x18007a338  mov     [rbp+60h+var_60], rcx
0x18007a33c  mov     qword ptr [rbp+60h+var_C0], rcx
0x18007a340  mov     [rbp+60h+var_B0], ecx
0x18007a343  mov     [rbp+60h+var_80], rcx
0x18007a347  mov     [rbp+60h+var_A8], rcx
0x18007a34b  mov     [rbp+60h+String1], rcx
0x18007a34f  mov     [rsp+160h+var_E8], ecx
0x18007a353  mov     [rsp+160h+var_E4], ecx
0x18007a357  mov     [rbp+60h+var_A0], rcx
0x18007a35b  mov     [rbp+60h+Src], rcx
0x18007a35f  mov     [rbp+60h+var_E0], eax
0x18007a362  movups  xmmword ptr [rsp+160h+String2], xmm0
0x18007a367  test    rdx, rdx
0x18007a36a  jz      loc_18007A5C3
0x18007a370  test    r15, r15
0x18007a373  jz      loc_18007A5C3
0x18007a379  lea     rcx, [rbp+60h+Src]
0x18007a37d  call    RtlpCreateProcessRegistryInfo
0x18007a382  mov     edi, eax
0x18007a384  test    eax, eax
0x18007a386  js      loc_18007A5A4
0x18007a38c  mov     rcx, gs:60h
0x18007a395  mov     edx, 8
0x18007a39a  mov     r8d, 20Ah
0x18007a3a0  mov     [rsp+160h+arg_0], r13
0x18007a3a8  mov     rcx, [rcx+30h]
0x18007a3ac  call    RtlAllocateHeap_0
0x18007a3b1  mov     r13, rax
0x18007a3b4  test    rax, rax
0x18007a3b7  jz      loc_18007AEF5
0x18007a3bd  lea     r9, [rbp+60h+var_A0]
0x18007a3c1  mov     r8, rax
0x18007a3c4  mov     edx, 208h
0x18007a3c9  mov     rcx, r14
0x18007a3cc  call    RtlGetFullPathName_U
0x18007a3d1  dec     eax
0x18007a3d3  cmp     eax, 206h
0x18007a3d8  ja      short loc_18007A415
0x18007a3da  mov     rcx, [rbp+60h+var_A0]
0x18007a3de  test    rcx, rcx
0x18007a3e1  jz      short loc_18007A415
0x18007a3e3  cmp     rcx, r13
0x18007a3e6  jbe     short loc_18007A415
0x18007a3e8  lea     rax, [r13+208h]
0x18007a3ef  cmp     rcx, rax
0x18007a3f2  jnb     short loc_18007A415
0x18007a3f4  xor     r10d, r10d
0x18007a3f7  mov     [rcx-2], r10w
0x18007a3fc  mov     rax, [r15]
0x18007a3ff  test    rax, rax
0x18007a402  jnz     loc_18007A5F6
0x18007a408  mov     eax, ebx
0x18007a40a  and     eax, 0Ch
0x18007a40d  cmp     al, 0Ch
0x18007a40f  jnz     loc_18007A709
0x18007a415  mov     edi, 0C000000Dh
0x18007a41a  jmp     loc_18007A583
0x18007a41f  xor     r10d, r10d
0x18007a422  mov     rdi, [rsp+160h+var_118]
0x18007a427  mov     rcx, r10
0x18007a42a  test    rdi, rdi
0x18007a42d  jnz     loc_18007ACD0
0x18007a433  mov     r15, [rsp+160h+String2+8]
0x18007a438  mov     r12d, [rbp+60h+var_E0]
0x18007a43c  mov     rsi, [rsp+160h+var_F0]
0x18007a441  mov     [rbp+60h+Src], r15
0x18007a445  cmp     rdi, rsi
0x18007a448  jb      loc_18007A648
0x18007a44e  mov     rsi, [rbp+60h+var_80]
0x18007a452  mov     r14, rdi
0x18007a455  mov     [rbp+60h+Src], r15
0x18007a459  movzx   r15d, [rsp+160h+var_110]
0x18007a45f  mov     rdi, [rbp+60h+Src]
0x18007a463  mov     r12, [rsp+160h+var_F0]
0x18007a468  cmp     r14, r12
0x18007a46b  jnb     loc_18007A5DA
0x18007a471  cmp     [rbp+60h+var_D8], 0
0x18007a476  mov     rdx, [rbp+60h+var_D0]
0x18007a47a  jz      loc_18007A5E4
0x18007a480  test    r15b, r15b
0x18007a483  jz      loc_18007AACE
0x18007a489  mov     r15, [rbp+60h+var_D8]
0x18007a48d  test    rdx, rdx
0x18007a490  jz      short loc_18007A4C6
0x18007a492  test    r15, r15
0x18007a495  jz      loc_18007A689
0x18007a49b  movzx   ecx, word ptr [rsp+160h+String2]
0x18007a4a0  mov     eax, ecx
0x18007a4a2  shr     eax, 1
0x18007a4a4  cmp     [rdx], eax
0x18007a4a6  jbe     short loc_18007A4C6
0x18007a4a8  mov     ebx, ecx
0x18007a4aa  mov     r8d, ecx; Size
0x18007a4ad  mov     rcx, r15; void *
0x18007a4b0  mov     rdx, rdi; Src
0x18007a4b3  call    memmove
0x18007a4b8  mov     rdx, [rbp+60h+var_D0]
0x18007a4bc  shr     rbx, 1
0x18007a4bf  xor     eax, eax
0x18007a4c1  mov     [r15+rbx*2], ax
0x18007a4c6  cmp     [rbp+60h+var_90], 0
0x18007a4cb  jz      loc_18007A5D3
0x18007a4d1  test    r15, r15
0x18007a4d4  jz      loc_18007A5CA
0x18007a4da  xor     edi, edi
0x18007a4dc  lea     rax, [r14+1]
0x18007a4e0  mov     r8, 0CB7000000CB70000h
0x18007a4ea  mov     rcx, rax
0x18007a4ed  xor     rax, [rbp+60h+var_78]
0x18007a4f1  xor     rax, [rbp+60h+var_70]
0x18007a4f5  shl     rcx, 0Ch
0x18007a4f9  xor     rax, r12
0x18007a4fc  or      rcx, r12
0x18007a4ff  shl     rax, 34h
0x18007a503  shl     rcx, 18h
0x18007a507  xor     rax, r8
0x18007a50a  or      rcx, [rbp+60h+var_78]
0x18007a50e  or      rcx, 0CB7000h
0x18007a515  shl     rcx, 4
0x18007a519  or      rcx, rax
0x18007a51c  mov     rax, [rbp+60h+var_58]
0x18007a520  or      rcx, [rbp+60h+var_70]
0x18007a524  mov     [rax], rcx
0x18007a527  mov     rax, [rbp+60h+var_68]
0x18007a52b  test    rax, rax
0x18007a52e  jz      short loc_18007A547
0x18007a530  mov     rcx, gs:60h
0x18007a539  mov     r8, rax
0x18007a53c  xor     edx, edx
0x18007a53e  mov     rcx, [rcx+30h]
0x18007a542  call    RtlFreeHeap_0
0x18007a547  test    rsi, rsi
0x18007a54a  jz      short loc_18007A563
0x18007a54c  mov     rcx, gs:60h
0x18007a555  mov     r8, rsi
0x18007a558  xor     edx, edx
0x18007a55a  mov     rcx, [rcx+30h]
0x18007a55e  call    RtlFreeHeap_0
0x18007a563  mov     rax, [rbp+60h+String1]
0x18007a567  test    rax, rax
0x18007a56a  jz      short loc_18007A583
0x18007a56c  mov     rcx, gs:60h
0x18007a575  mov     r8, rax
0x18007a578  xor     edx, edx
0x18007a57a  mov     rcx, [rcx+30h]
0x18007a57e  call    RtlFreeHeap_0
0x18007a583  mov     rcx, gs:60h
0x18007a58c  mov     r8, r13
0x18007a58f  xor     edx, edx
0x18007a591  mov     rcx, [rcx+30h]
0x18007a595  call    RtlFreeHeap_0
0x18007a59a  mov     eax, edi
0x18007a59c  mov     r13, [rsp+160h+arg_0]
0x18007a5a4  mov     rcx, [rbp+60h+var_40]
0x18007a5a8  xor     rcx, rsp; StackCookie
0x18007a5ab  call    __security_check_cookie
0x18007a5b0  add     rsp, 130h
0x18007a5b7  pop     r15
0x18007a5b9  pop     r14
0x18007a5bb  pop     r12
0x18007a5bd  pop     rdi
0x18007a5be  pop     rsi
0x18007a5bf  pop     rbx
0x18007a5c0  pop     rbp
0x18007a5c1  retn
0x18007a5c3  mov     eax, 0C000000Dh
0x18007a5c8  jmp     short loc_18007A5A4
0x18007a5ca  test    rdx, rdx
0x18007a5cd  jz      loc_18007A4DA
0x18007a5d3  xor     edi, edi
0x18007a5d5  jmp     loc_18007A527
0x18007a5da  mov     edi, 80000006h
0x18007a5df  jmp     loc_18007A4DC
0x18007a5e4  test    rdx, rdx
0x18007a5e7  jnz     loc_18007A480
0x18007a5ed  mov     r15, [rbp+60h+var_D8]
0x18007a5f1  jmp     loc_18007A4C6
0x18007a5f6  mov     r14, r10
0x18007a5f9  mov     [rsp+160h+var_118], r10
0x18007a5fe  mov     r15, r10
0x18007a601  mov     [rbp+60h+var_78], r10
0x18007a605  mov     r10, rax
0x18007a608  shr     rax, 4
0x18007a60c  and     r10d, 0Fh
0x18007a610  mov     [rbp+60h+var_70], r10
0x18007a614  mov     r9d, r10d
0x18007a617  xor     ecx, ecx
0x18007a619  mov     rdx, rax
0x18007a61c  mov     r8, rcx
0x18007a61f  and     edx, 0FFFh
0x18007a625  shr     rax, 0Ch
0x18007a629  xor     r9, rdx
0x18007a62c  test    rcx, rcx
0x18007a62f  jz      loc_18007AABF
0x18007a635  sub     r8, 2
0x18007a639  jnz     short loc_18007A694
0x18007a63b  mov     r12d, edx
0x18007a63e  mov     [rsp+160h+var_F0], rdx
0x18007a643  inc     rcx
0x18007a646  jmp     short loc_18007A619
0x18007a648  test    r14b, r14b
0x18007a64b  jz      loc_18007AD0F
0x18007a651  mov     rdx, r15; String2
0x18007a654  mov     rcx, rbx; String1
0x18007a657  call    _wcsicmp
0x18007a65c  test    eax, eax
0x18007a65e  jz      loc_18007AD0F
0x18007a664  inc     rdi
0x18007a667  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007a66e  xchg    ax, ax
0x18007a670  cmp     word ptr [rbx+rax*2+2], 0
0x18007a676  lea     rax, [rax+1]
0x18007a67a  jnz     short loc_18007A670
0x18007a67c  lea     rbx, [rbx+rax*2]
0x18007a680  add     rbx, 2
0x18007a684  jmp     loc_18007A445
0x18007a689  mov     dword ptr [rdx], 55h ; 'U'
0x18007a68f  jmp     loc_18007A4C6
0x18007a694  cmp     r8, 1
0x18007a698  jnz     short loc_18007A6A4
0x18007a69a  mov     r14, rdx
0x18007a69d  mov     [rsp+160h+var_118], rdx
0x18007a6a2  jmp     short loc_18007A6B1
0x18007a6a4  inc     rcx
0x18007a6a7  cmp     rcx, 4
0x18007a6ab  jb      loc_18007A619
0x18007a6b1  xor     r9, rax
0x18007a6b4  test    r9, 0FFFh
0x18007a6bb  jnz     loc_18007AEFF
0x18007a6c1  cmp     r14, r12
0x18007a6c4  ja      loc_18007AF09
0x18007a6ca  test    r15b, 20h
0x18007a6ce  jnz     loc_18007ADED
0x18007a6d4  movzx   ebx, r15b
0x18007a6d8  and     ebx, 40h
0x18007a6db  or      ebx, 20h
0x18007a6de  shr     ebx, 5
0x18007a6e1  shr     r15b, 2
0x18007a6e5  movzx   eax, r10b
0x18007a6e9  and     al, 1
0x18007a6eb  not     r15b
0x18007a6ee  and     r15b, 1
0x18007a6f2  mov     [rsp+160h+var_120], al
0x18007a6f6  mov     [rsp+160h+var_110], r15b
0x18007a6fb  xor     r10d, r10d
0x18007a6fe  mov     r12d, 1
0x18007a704  jmp     loc_18007A82E
0x18007a709  mov     ecx, ebx
0x18007a70b  mov     eax, ebx
0x18007a70d  and     ecx, 20h
0x18007a710  and     eax, 10h
0x18007a713  jnz     loc_18007A9BD
0x18007a719  mov     edx, ebx
0x18007a71b  and     edx, 40h
0x18007a71e  test    eax, eax
0x18007a720  jnz     loc_18007AAB2
0x18007a726  test    ecx, ecx
0x18007a728  jnz     loc_18007AEE8
0x18007a72e  bt      ebx, 9
0x18007a732  jb      loc_18007AA5F
0x18007a738  test    eax, eax
0x18007a73a  jnz     loc_18007AA6E
0x18007a740  mov     [rbp+60h+var_70], r10
0x18007a744  mov     rax, rbx
0x18007a747  mov     [rbp+60h+var_78], rbx
0x18007a74b  test    ecx, ecx
  ... truncated ...
```
