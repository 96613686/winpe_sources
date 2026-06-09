# sxsisol_SearchActCtxForDllName

- ea: `0x18001ae70`
- end: `0x18001b524`
- name: `sxsisol_SearchActCtxForDllName`
- size: `1716`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, loader_planting`

## callers

- `0x18001bcb0`

## callees

- `0x180019840`
- `0x18001a080`
- `0x18001ae70`
- `0x18001b530`
- `0x18001d490`
- `0x18005f8b0`
- `0x18005fd20`
- `0x180060644`
- `0x180061790`
- `0x1800ce740`
- `0x180162000`
- `0x180163a80`

## string_xrefs

- `0x18001b31e`: `minkernel\ntdll\sxsisol.cpp`
- `0x18001b404`: `sxsisol_SearchActCtxForDllName`

## pseudocode

```c
__int64 __fastcall sxsisol_SearchActCtxForDllName(__int128 *a1, char a2, _QWORD *a3, _DWORD *a4, unsigned __int16 *a5)
{
  __int64 v8; // rdi
  __int128 v9; // xmm0
  int ActivationContextSectionString; // eax
  int v11; // ebx
  __int16 *v12; // rdx
  _DWORD *v14; // r15
  unsigned int v15; // r13d
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  int v18; // eax
  int v19; // edx
  int v20; // ecx
  int AssemblyStorageRoot; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  const void **v26; // rdx
  unsigned __int64 v27; // r8
  _QWORD *v28; // r13
  unsigned __int64 v29; // r8
  __int64 v30; // rcx
  unsigned __int64 v31; // rax
  unsigned __int16 v32; // dx
  _WORD *v33; // rcx
  unsigned __int16 v34; // dx
  __int64 v35; // rbx
  int v36; // eax
  void *v37; // rax
  unsigned __int16 v38; // dx
  size_t v39; // rbx
  bool v40; // cf
  unsigned __int64 v41; // r8
  __int64 v42; // rcx
  void *v43; // rdx
  unsigned __int64 v44; // rax
  unsigned __int16 v45; // bx
  __int64 v46; // rdx
  int CharInUnicodeString; // eax
  const char *v48; // r9
  __int64 v49; // r8
  unsigned __int16 *v50; // rdx
  unsigned __int64 v51; // r8
  unsigned int v52; // eax
  __int64 v53; // rcx
  void *v54; // r8
  const void *v55; // rdx
  unsigned __int64 v56; // rax
  unsigned __int64 v57; // rdx
  unsigned int v58; // r10d
  int v59; // r11d
  __int64 v60; // rcx
  unsigned __int64 v61; // rax
  __int64 v62; // rcx
  unsigned __int64 v63; // rdx
  __int64 v64; // [rsp+20h] [rbp-E0h]
  int v65; // [rsp+30h] [rbp-D0h] BYREF
  _WORD *v66; // [rsp+38h] [rbp-C8h] BYREF
  void *Src; // [rsp+40h] [rbp-C0h]
  __int128 v68; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h]
  __int64 v70; // [rsp+60h] [rbp-A0h]
  int v71; // [rsp+70h] [rbp-90h] BYREF
  __int128 v72; // [rsp+74h] [rbp-8Ch]
  __int128 v73; // [rsp+84h] [rbp-7Ch]
  __int128 v74; // [rsp+94h] [rbp-6Ch]
  __int128 v75; // [rsp+A4h] [rbp-5Ch]
  __int128 v76; // [rsp+B4h] [rbp-4Ch]
  _BYTE v77[28]; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v78; // [rsp+E0h] [rbp-20h] BYREF
  void *v79; // [rsp+E8h] [rbp-18h]
  __int16 *v80; // [rsp+F0h] [rbp-10h]
  __int16 *v81; // [rsp+F8h] [rbp-8h]
  __int64 v82; // [rsp+100h] [rbp+0h]
  __int64 v83; // [rsp+108h] [rbp+8h]
  __int16 v84; // [rsp+110h] [rbp+10h] BYREF
  int v85; // [rsp+112h] [rbp+12h]
  __int16 v86; // [rsp+116h] [rbp+16h]

  v80 = &v84;
  v71 = 112;
  memset(v77, 0, sizeof(v77));
  v78 = 0x20000;
  v81 = &v84;
  v85 = 0;
  v86 = 0;
  v72 = 0;
  v79 = &v84;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v8 = 0;
  v76 = 0;
  v66 = 0;
  v82 = 2;
  v9 = *a1;
  v83 = 2;
  v84 = 0;
  v68 = v9;
  ActivationContextSectionString = RtlFindActivationContextSectionString(3, 0, 2, (unsigned int)&v68, (__int64)&v71);
  v11 = ActivationContextSectionString;
  if ( ActivationContextSectionString < 0 )
  {
    if ( ActivationContextSectionString == -1072365567 )
      v11 = -1072365560;
    goto LABEL_4;
  }
  if ( a2 )
  {
    v11 = 0;
    goto LABEL_4;
  }
  v8 = *(_QWORD *)((char *)&v75 + 4);
  if ( HIDWORD(v72) < 0x14 || (_DWORD)v72 != 1 )
  {
    v11 = -1072365565;
    goto LABEL_4;
  }
  v14 = *(_DWORD **)((char *)&v72 + 4);
  v15 = HIDWORD(v74);
  v16 = *(unsigned int *)(*(_QWORD *)((char *)&v72 + 4) + 16LL);
  if ( (unsigned int)v16 > HIDWORD(v74)
    || (v17 = *(_DWORD *)(*(_QWORD *)((char *)&v72 + 4) + 12LL), v17 > 0x1FFFFFFF)
    || v16 > 0xFFFFFFFF - 8 * (unsigned __int64)v17
    || (unsigned int)v16 + 8 * v17 > HIDWORD(v74) )
  {
LABEL_76:
    v11 = -1072365565;
    goto LABEL_4;
  }
  v18 = *(_DWORD *)(*(_QWORD *)((char *)&v72 + 4) + 4LL);
  if ( (v18 & 2) == 0 )
    goto LABEL_28;
  v65 = 0;
  if ( (v18 & 4) != 0 )
  {
    DbgPrintEx(
      51,
      0,
      "[%x.%x] SXS: %s - Relative redirection plus env var expansion.\n",
      LODWORD(NtCurrentTeb()->ClientId.UniqueProcess),
      LODWORD(NtCurrentTeb()->ClientId.UniqueThread),
      "sxsisol_SearchActCtxForDllName");
    goto LABEL_76;
  }
  v19 = 0;
  if ( (v76 & 1) != 0 )
  {
    if ( (v76 & 2) != 0 )
    {
      v48 = "!(askd.Flags & ACTIVATION_CONTEXT_SECTION_KEYED_DATA_FLAG_FOUND_IN_SYSTEM_DEFAULT)";
      v49 = 1050;
      goto LABEL_64;
    }
    v19 = 1;
  }
  v20 = v19 | 2;
  if ( (v76 & 2) == 0 )
    v20 = v19;
  AssemblyStorageRoot = RtlGetAssemblyStorageRoot(
                          v20,
                          DWORD1(v75),
                          HIDWORD(v75),
                          (unsigned int)&v66,
                          v64,
                          (__int64)&v65);
  v11 = AssemblyStorageRoot;
  if ( AssemblyStorageRoot >= 0 )
  {
LABEL_28:
    v22 = 0;
    v23 = *(_QWORD *)((char *)&v74 + 4) + (unsigned int)v14[4];
    *a3 = 0;
    v24 = 0;
    v25 = (unsigned int)v14[3];
    v70 = v23;
    v69 = v25;
    while ( (unsigned int)v22 != v25 )
    {
      v58 = *(_DWORD *)(v23 + 8 * v22 + 4);
      if ( v58 > v15 )
        goto LABEL_76;
      v59 = *(_DWORD *)(v23 + 8 * v22);
      if ( v58 > ~v59 || v59 + v58 > v15 )
        goto LABEL_76;
      v24 += (unsigned __int16)v59;
      *a3 = v24;
      v22 = (unsigned int)(v22 + 1);
    }
    v26 = (const void **)v66;
    if ( v66 )
    {
      v24 += (unsigned __int16)*v66;
      *a3 = v24;
    }
    v27 = (unsigned __int16)v24 + 2LL;
    if ( v27 > 0xFFFE )
      goto LABEL_62;
    v28 = a5 + 8;
    if ( a5 == (unsigned __int16 *)-16LL || v27 > *((_QWORD *)a5 + 4) )
    {
      if ( (int)RtlpEnsureBufferSize(0, a5 + 8) < 0 )
      {
LABEL_90:
        v11 = -1073741801;
        goto LABEL_4;
      }
      v26 = (const void **)v66;
    }
    *((_QWORD *)a5 + 1) = *v28;
    a5[1] = a5[16];
    if ( v26 )
    {
      *a5 = 0;
      v29 = *(unsigned __int16 *)v26 + 2LL;
      if ( v29 > 0xFFFE )
        goto LABEL_62;
      if ( v29 > *((_QWORD *)a5 + 4) )
      {
        if ( (int)RtlpEnsureBufferSize(0, a5 + 8) < 0 )
        {
          v11 = -1073741801;
          goto LABEL_4;
        }
        v26 = (const void **)v66;
      }
      v30 = *v28;
      v31 = *a5;
      *((_QWORD *)a5 + 1) = *v28;
      memmove((void *)(v30 + 2 * (v31 >> 1)), v26[1], *(unsigned __int16 *)v26);
      v32 = *a5;
      v33 = v66;
      a5[1] = *v66 + *a5 + 2;
      v34 = *v33 + v32;
      v24 = *((_QWORD *)a5 + 1);
      *a5 = v34;
      *(_WORD *)(v24 + 2 * ((unsigned __int64)v34 >> 1)) = 0;
    }
    v35 = 0;
    while ( (unsigned int)v35 != v69 )
    {
      v50 = (unsigned __int16 *)(v70 + 8 * v35);
      v51 = *v50 + *a5 + 2LL;
      Src = (void *)*v50;
      if ( v51 > 0xFFFE )
        goto LABEL_62;
      v52 = *((_DWORD *)v50 + 1);
      v65 = v52;
      if ( v51 > *((_QWORD *)a5 + 4) )
      {
        if ( (int)RtlpEnsureBufferSize(0, a5 + 8) < 0 )
          goto LABEL_90;
        v52 = v65;
      }
      v53 = *((_QWORD *)a5 + 2);
      v54 = Src;
      v55 = (const void *)(*(_QWORD *)((char *)&v74 + 4) + v52);
      v56 = (unsigned __int64)*a5 >> 1;
      *((_QWORD *)a5 + 1) = v53;
      memmove((void *)(v53 + 2 * v56), v55, (size_t)v54);
      v24 = *((_QWORD *)a5 + 1);
      v57 = (unsigned __int16)(*a5 + (_WORD)Src);
      *a5 = v57;
      a5[1] = v57 + 2;
      v35 = (unsigned int)(v35 + 1);
      *(_WORD *)(v24 + 2 * (v57 >> 1)) = 0;
    }
    v36 = v14[1];
    if ( (v36 & 1) != 0 )
    {
LABEL_51:
      if ( (v14[1] & 4) == 0 )
      {
LABEL_52:
        if ( a4 )
          *a4 |= 2u;
        v11 = 0;
        goto LABEL_4;
      }
      v11 = sxsisol_ExpandEnvironmentStrings_UEx(v24, a5, &v78);
      if ( v11 < 0 )
        goto LABEL_4;
      v46 = (unsigned __int16)v78;
      *a5 = 0;
      if ( (unsigned __int64)(v46 + 2) <= 0xFFFE )
      {
        if ( (unsigned __int64)(v46 + 2) > *((_QWORD *)a5 + 4) )
        {
          if ( (int)RtlpEnsureBufferSize(0, a5 + 8) < 0 )
          {
            v11 = -1073741801;
            goto LABEL_4;
          }
          LOWORD(v46) = v78;
        }
        v60 = *((_QWORD *)a5 + 2);
        v61 = (unsigned __int64)*a5 >> 1;
        *((_QWORD *)a5 + 1) = v60;
        memmove((void *)(v60 + 2 * v61), v79, (unsigned __int16)v46);
        v62 = *((_QWORD *)a5 + 1);
        v63 = (unsigned __int16)(*a5 + v78);
        *a5 = v63;
        a5[1] = v63 + 2;
        *(_WORD *)(v62 + 2 * (v63 >> 1)) = 0;
        goto LABEL_52;
      }
LABEL_62:
      v11 = -1073741562;
      goto LABEL_4;
    }
    if ( (v36 & 8) == 0 )
    {
      v37 = (void *)*((_QWORD *)&v68 + 1);
      v38 = v68;
      goto LABEL_46;
    }
    LOWORD(v65) = 0;
    CharInUnicodeString = RtlFindCharInUnicodeString(1, &v68, &RtlDosPathSeperatorsString, &v65);
    v11 = CharInUnicodeString;
    if ( CharInUnicodeString >= 0 )
    {
      v38 = -2 - v65 + v68;
      v37 = (void *)(*((_QWORD *)&v68 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v65 >> 1) + 2);
LABEL_46:
      v39 = v38;
      *a3 += v38;
      v40 = *a3 < 0xFFFFu;
      Src = v37;
      if ( !v40 )
        goto LABEL_62;
      v41 = v38 + *a5 + 2LL;
      if ( v41 > 0xFFFE )
        goto LABEL_62;
      if ( v41 > *((_QWORD *)a5 + 4) && (int)RtlpEnsureBufferSize(0, a5 + 8) < 0 )
      {
        v11 = -1073741801;
        goto LABEL_4;
      }
      v42 = *((_QWORD *)a5 + 2);
      v43 = Src;
      v44 = (unsigned __int64)*a5 >> 1;
      *((_QWORD *)a5 + 1) = v42;
      memmove((void *)(v42 + 2 * v44), v43, v39);
      v45 = *a5 + v39;
      v24 = *((_QWORD *)a5 + 1);
      *a5 = v45;
      a5[1] = v45 + 2;
      *(_WORD *)(v24 + 2 * ((unsigned __int64)v45 >> 1)) = 0;
      goto LABEL_51;
    }
    if ( CharInUnicodeString != -1073741275 )
      goto LABEL_4;
    v48 = "Status != STATUS_NOT_FOUND";
    v49 = 1142;
LABEL_64:
    RtlAssert("Internal error check failed", "minkernel\\ntdll\\sxsisol.cpp", v49, v48);
    v11 = -1073741595;
    goto LABEL_4;
  }
  if ( AssemblyStorageRoot == -1073741536 && v65 < 0 )
    v11 = v65;
LABEL_4:
  v12 = v81;
  if ( v80 )
  {
    if ( v80 != v81 )
    {
      RtlpSysVolFree(v80);
      v12 = v81;
    }
    v82 = v83;
    v80 = v12;
  }
  v79 = v12;
  if ( v12 )
    *v12 = 0;
  WORD1(v78) = v83;
  LOWORD(v78) = 0;
  if ( v8 )
    RtlReleaseActivationContext(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001ae70  mov     [rsp-8+arg_8], rbx
0x18001ae75  push    rbp
0x18001ae76  push    rsi
0x18001ae77  push    rdi
0x18001ae78  push    r12
0x18001ae7a  push    r13
0x18001ae7c  push    r14
0x18001ae7e  push    r15
0x18001ae80  lea     rbp, [rsp-20h]
0x18001ae85  sub     rsp, 120h
0x18001ae8c  mov     rax, cs:__security_cookie
0x18001ae93  xor     rax, rsp
0x18001ae96  mov     [rbp+50h+var_38], rax
0x18001ae9a  mov     rsi, [rbp+50h+arg_20]
0x18001aea1  lea     rax, [rbp+50h+var_40]
0x18001aea5  xorps   xmm0, xmm0
0x18001aea8  mov     [rbp+50h+var_60], rax
0x18001aeac  xor     r13d, r13d
0x18001aeaf  mov     [rsp+150h+var_E0], 70h ; 'p'
0x18001aeb7  movups  xmmword ptr [rbp+50h+var_8C], xmm0
0x18001aebb  lea     rax, [rbp+50h+var_40]
0x18001aebf  mov     [rbp+50h+var_70], 20000h
0x18001aec7  mov     [rbp+50h+var_58], rax
0x18001aecb  mov     r14, r8
0x18001aece  mov     r8d, 2
0x18001aed4  mov     [rbp+50h+var_3E], r13d
0x18001aed8  lea     rax, [rbp+50h+var_40]
0x18001aedc  mov     [rbp+50h+var_3A], r13w
0x18001aee1  movups  [rsp+150h+var_DC], xmm0
0x18001aee6  mov     [rbp+50h+var_68], rax
0x18001aeea  lea     rax, [rsp+150h+var_E0]
0x18001aeef  movups  [rbp+50h+var_CC], xmm0
0x18001aef3  mov     r12, r9
0x18001aef6  movzx   r15d, dl
0x18001aefa  movups  [rbp+50h+var_BC], xmm0
0x18001aefe  lea     r9, [rsp+150h+var_108]
0x18001af03  xor     edx, edx
0x18001af05  movups  [rbp+50h+var_AC], xmm0
0x18001af09  mov     [rsp+150h+var_130], rax
0x18001af0e  mov     edi, r13d
0x18001af11  movups  [rbp+50h+var_9C], xmm0
0x18001af15  mov     [rsp+150h+var_118], r13
0x18001af1a  movups  xmmword ptr [rbp+50h+var_8C+0Ch], xmm0
0x18001af1e  mov     [rbp+50h+var_50], r8
0x18001af22  movups  xmm0, xmmword ptr [rcx]
0x18001af25  mov     ecx, 3
0x18001af2a  mov     [rbp+50h+var_48], r8
0x18001af2e  mov     [rbp+50h+var_40], r13w
0x18001af33  movups  [rsp+150h+var_108], xmm0
0x18001af38  call    RtlFindActivationContextSectionString
0x18001af3d  mov     ebx, eax
0x18001af3f  test    eax, eax
0x18001af41  jns     loc_18001AFCB
0x18001af47  cmp     eax, 0C0150001h
0x18001af4c  jnz     short loc_18001AF53
0x18001af4e  mov     ebx, 0C0150008h
0x18001af53  mov     rcx, [rbp+50h+var_60]
0x18001af57  mov     rdx, [rbp+50h+var_58]
0x18001af5b  test    rcx, rcx
0x18001af5e  jz      short loc_18001AF7A
0x18001af60  cmp     rcx, rdx
0x18001af63  jz      short loc_18001AF6E
0x18001af65  call    RtlpSysVolFree
0x18001af6a  mov     rdx, [rbp+50h+var_58]
0x18001af6e  mov     rax, [rbp+50h+var_48]
0x18001af72  mov     [rbp+50h+var_50], rax
0x18001af76  mov     [rbp+50h+var_60], rdx
0x18001af7a  mov     [rbp+50h+var_68], rdx
0x18001af7e  test    rdx, rdx
0x18001af81  jz      short loc_18001AF87
0x18001af83  mov     [rdx], r13w
0x18001af87  movzx   eax, word ptr [rbp+50h+var_48]
0x18001af8b  mov     word ptr [rbp+50h+var_70+2], ax
0x18001af8f  mov     word ptr [rbp+50h+var_70], r13w
0x18001af94  test    rdi, rdi
0x18001af97  jz      short loc_18001AFA1
0x18001af99  mov     rcx, rdi
0x18001af9c  call    RtlReleaseActivationContext
0x18001afa1  mov     eax, ebx
0x18001afa3  mov     rcx, [rbp+50h+var_38]
0x18001afa7  xor     rcx, rsp; StackCookie
0x18001afaa  call    __security_check_cookie
0x18001afaf  mov     rbx, [rsp+150h+arg_8]
0x18001afb7  add     rsp, 120h
0x18001afbe  pop     r15
0x18001afc0  pop     r14
0x18001afc2  pop     r13
0x18001afc4  pop     r12
0x18001afc6  pop     rdi
0x18001afc7  pop     rsi
0x18001afc8  pop     rbp
0x18001afc9  retn
0x18001afcb  test    r15b, r15b
0x18001afce  jnz     loc_18001B3D2
0x18001afd4  cmp     dword ptr [rbp+50h+var_DC+0Ch], 14h
0x18001afd8  mov     rdi, qword ptr [rbp+50h+var_AC+4]
0x18001afdc  jb      loc_18001B46E
0x18001afe2  cmp     dword ptr [rsp+150h+var_DC], 1
0x18001afe7  jnz     loc_18001B46E
0x18001afed  mov     r15, qword ptr [rsp+150h+var_DC+4]
0x18001aff2  mov     r13d, dword ptr [rbp+50h+var_BC+0Ch]
0x18001aff6  mov     edx, [r15+10h]
0x18001affa  cmp     edx, r13d
0x18001affd  ja      loc_18001B437
0x18001b003  mov     r8d, [r15+0Ch]
0x18001b007  cmp     r8d, 1FFFFFFFh
0x18001b00e  ja      loc_18001B437
0x18001b014  mov     eax, r8d
0x18001b017  mov     ecx, 0FFFFFFFFh
0x18001b01c  shl     rax, 3
0x18001b020  sub     rcx, rax
0x18001b023  cmp     rdx, rcx
0x18001b026  ja      loc_18001B437
0x18001b02c  lea     eax, [rdx+r8*8]
0x18001b030  cmp     eax, r13d
0x18001b033  ja      loc_18001B437
0x18001b039  mov     eax, [r15+4]
0x18001b03d  test    al, 2
0x18001b03f  jz      short loc_18001B098
0x18001b041  mov     [rsp+150h+var_120], 0
0x18001b049  test    al, 4
0x18001b04b  jnz     loc_18001B3FB
0x18001b051  mov     eax, dword ptr [rbp+50h+var_9C]
0x18001b054  xor     edx, edx
0x18001b056  test    al, 1
0x18001b058  jz      short loc_18001B067
0x18001b05a  test    al, 2
0x18001b05c  jnz     loc_18001B311
0x18001b062  mov     edx, 1
0x18001b067  mov     r8d, dword ptr [rbp+50h+var_AC+0Ch]
0x18001b06b  lea     rax, [rsp+150h+var_120]
0x18001b070  mov     ecx, edx
0x18001b072  mov     [rsp+150h+var_128], rax
0x18001b077  or      ecx, 2
0x18001b07a  lea     r9, [rsp+150h+var_118]
0x18001b07f  test    byte ptr [rbp+50h+var_9C], 2
0x18001b083  cmovz   ecx, edx
0x18001b086  mov     rdx, rdi
0x18001b089  call    RtlGetAssemblyStorageRoot
0x18001b08e  mov     ebx, eax
0x18001b090  test    eax, eax
0x18001b092  js      loc_18001B3DA
0x18001b098  mov     r9d, [r15+10h]
0x18001b09c  xor     edx, edx
0x18001b09e  add     r9, qword ptr [rbp+50h+var_BC+4]
0x18001b0a2  mov     qword ptr [r14], 0
0x18001b0a9  xor     ecx, ecx
0x18001b0ab  mov     r8d, [r15+0Ch]
0x18001b0af  mov     [rsp+150h+var_F0], r9
0x18001b0b4  mov     [rsp+150h+var_F8], r8
0x18001b0b9  mov     eax, edx
0x18001b0bb  cmp     rax, r8
0x18001b0be  jnz     loc_18001B478
0x18001b0c4  mov     rdx, [rsp+150h+var_118]
0x18001b0c9  test    rdx, rdx
0x18001b0cc  jz      short loc_18001B0D7
0x18001b0ce  movzx   eax, word ptr [rdx]
0x18001b0d1  add     rcx, rax
0x18001b0d4  mov     [r14], rcx
0x18001b0d7  movzx   r8d, cx
0x18001b0db  add     r8, 2
0x18001b0df  cmp     r8, 0FFFEh
0x18001b0e6  ja      loc_18001B30A
0x18001b0ec  lea     r13, [rsi+10h]
0x18001b0f0  test    r13, r13
0x18001b0f3  jz      short loc_18001B0FB
0x18001b0f5  cmp     r8, [rsi+20h]
0x18001b0f9  jbe     short loc_18001B112
0x18001b0fb  mov     rdx, r13
0x18001b0fe  xor     ecx, ecx
0x18001b100  call    RtlpEnsureBufferSize
0x18001b105  test    eax, eax
0x18001b107  js      loc_18001B51A
0x18001b10d  mov     rdx, [rsp+150h+var_118]
0x18001b112  mov     rax, [r13+0]
0x18001b116  mov     [rsi+8], rax
0x18001b11a  movzx   eax, word ptr [rsi+20h]
0x18001b11e  mov     [rsi+2], ax
0x18001b122  test    rdx, rdx
0x18001b125  jz      short loc_18001B192
0x18001b127  xor     eax, eax
0x18001b129  mov     [rsi], ax
0x18001b12c  movzx   r8d, word ptr [rdx]
0x18001b130  add     r8, 2
0x18001b134  cmp     r8, 0FFFEh
0x18001b13b  ja      loc_18001B30A
0x18001b141  cmp     r8, [rsi+20h]
0x18001b145  ja      loc_18001B4F5
0x18001b14b  mov     rcx, [r13+0]
0x18001b14f  movzx   eax, word ptr [rsi]
0x18001b152  mov     [rsi+8], rcx
0x18001b156  movzx   r8d, word ptr [rdx]; Size
0x18001b15a  mov     rdx, [rdx+8]; Src
0x18001b15e  shr     rax, 1
0x18001b161  lea     rcx, [rcx+rax*2]; void *
0x18001b165  call    memmove
0x18001b16a  movzx   edx, word ptr [rsi]
0x18001b16d  mov     rcx, [rsp+150h+var_118]
0x18001b172  lea     eax, [rdx+2]
0x18001b175  add     ax, [rcx]
0x18001b178  mov     [rsi+2], ax
0x18001b17c  add     dx, [rcx]
0x18001b17f  mov     rcx, [rsi+8]
0x18001b183  movzx   edx, dx
0x18001b186  mov     [rsi], dx
0x18001b189  shr     rdx, 1
0x18001b18c  xor     eax, eax
0x18001b18e  mov     [rcx+rdx*2], ax
0x18001b192  xor     ebx, ebx
0x18001b194  mov     eax, ebx
0x18001b196  cmp     rax, [rsp+150h+var_F8]
0x18001b19b  jnz     loc_18001B33E
0x18001b1a1  mov     eax, [r15+4]
0x18001b1a5  test    al, 1
0x18001b1a7  jnz     loc_18001B243
0x18001b1ad  test    al, 8
0x18001b1af  jnz     loc_18001B2B4
0x18001b1b5  mov     rax, qword ptr [rsp+150h+var_108+8]
0x18001b1ba  movzx   edx, word ptr [rsp+150h+var_108]
0x18001b1bf  movzx   ebx, dx
0x18001b1c2  add     [r14], rbx
0x18001b1c5  cmp     qword ptr [r14], 0FFFFh
0x18001b1cc  mov     [rsp+150h+Src], rax
0x18001b1d1  jnb     loc_18001B30A
0x18001b1d7  movzx   r8d, word ptr [rsi]
0x18001b1db  add     r8, 2
0x18001b1df  add     r8, rbx
0x18001b1e2  cmp     r8, 0FFFEh
0x18001b1e9  ja      loc_18001B30A
0x18001b1ef  cmp     r8, [rsi+20h]
0x18001b1f3  jbe     short loc_18001B207
0x18001b1f5  mov     rdx, r13
0x18001b1f8  xor     ecx, ecx
0x18001b1fa  call    RtlpEnsureBufferSize
0x18001b1ff  test    eax, eax
0x18001b201  js      loc_18001B461
0x18001b207  mov     rcx, [rsi+10h]
0x18001b20b  mov     r8, rbx; Size
0x18001b20e  movzx   eax, word ptr [rsi]
0x18001b211  mov     rdx, [rsp+150h+Src]; Src
0x18001b216  shr     rax, 1
0x18001b219  mov     [rsi+8], rcx
0x18001b21d  lea     rcx, [rcx+rax*2]; void *
0x18001b221  call    memmove
0x18001b226  add     bx, [rsi]
0x18001b229  mov     rcx, [rsi+8]
0x18001b22d  movzx   edx, bx
0x18001b230  mov     [rsi], dx
0x18001b233  lea     eax, [rdx+2]
0x18001b236  shr     rdx, 1
0x18001b239  mov     [rsi+2], ax
0x18001b23d  xor     eax, eax
0x18001b23f  mov     [rcx+rdx*2], ax
0x18001b243  test    byte ptr [r15+4], 4
0x18001b248  jnz     short loc_18001B25F
0x18001b24a  xor     r13d, r13d
0x18001b24d  test    r12, r12
0x18001b250  jz      short loc_18001B257
0x18001b252  or      dword ptr [r12], 2
0x18001b257  mov     ebx, r13d
0x18001b25a  jmp     loc_18001AF53
0x18001b25f  lea     r8, [rbp+50h+var_70]
0x18001b263  mov     rdx, rsi
0x18001b266  call    sxsisol_ExpandEnvironmentStrings_UEx
0x18001b26b  mov     ebx, eax
0x18001b26d  test    eax, eax
0x18001b26f  js      loc_18001B336
0x18001b275  movzx   edx, word ptr [rbp+50h+var_70]
0x18001b279  xor     eax, eax
0x18001b27b  mov     [rsi], ax
0x18001b27e  lea     r8, [rdx+2]
0x18001b282  cmp     r8, 0FFFEh
0x18001b289  ja      short loc_18001B30A
0x18001b28b  cmp     r8, [rsi+20h]
0x18001b28f  jbe     loc_18001B4AE
0x18001b295  mov     rdx, r13
0x18001b298  xor     ecx, ecx
0x18001b29a  call    RtlpEnsureBufferSize
0x18001b29f  test    eax, eax
0x18001b2a1  jns     loc_18001B4AA
0x18001b2a7  mov     ebx, 0C0000017h
0x18001b2ac  xor     r13d, r13d
0x18001b2af  jmp     loc_18001AF53
0x18001b2b4  xor     eax, eax
0x18001b2b6  lea     r9, [rsp+150h+var_120]
0x18001b2bb  lea     r8, RtlDosPathSeperatorsString
0x18001b2c2  mov     word ptr [rsp+150h+var_120], ax
0x18001b2c7  lea     rdx, [rsp+150h+var_108]
0x18001b2cc  mov     ecx, 1
0x18001b2d1  call    RtlFindCharInUnicodeString
0x18001b2d6  mov     ebx, eax
0x18001b2d8  test    eax, eax
0x18001b2da  js      loc_18001B444
0x18001b2e0  movzx   ecx, word ptr [rsp+150h+var_120]
0x18001b2e5  mov     eax, 0FFFEh
0x18001b2ea  movzx   edx, word ptr [rsp+150h+var_108]
0x18001b2ef  sub     ax, cx
0x18001b2f2  add     dx, ax
0x18001b2f5  shr     rcx, 1
0x18001b2f8  mov     rax, qword ptr [rsp+150h+var_108+8]
  ... truncated ...
```
