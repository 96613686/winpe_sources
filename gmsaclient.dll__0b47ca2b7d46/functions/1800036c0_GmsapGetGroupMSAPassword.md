# GmsapGetGroupMSAPassword

- ea: `0x1800036c0`
- end: `0x180003e7c`
- name: `GmsapGetGroupMSAPassword`
- size: `1980`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002114`
- `0x180005ab0`
- `0x180005e70`

## callees

- `0x180002e18`
- `0x180003500`
- `0x180003514`
- `0x1800036c0`
- `0x180003e84`
- `0x18000461c`
- `0x180006280`
- `0x1800062b0`
- `0x1800063cc`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003daf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003e4d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003daf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003e4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003be1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003be1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e69`
- `ntdll!RtlAcquireResourceShared` at `0x1800039e2`
- `ntdll!RtlAcquireResourceShared` at `0x1800039e2`
- `ntdll!RtlReleaseResource` at `0x180003a89`
- `ntdll!RtlReleaseResource` at `0x180003a89`

## pseudocode

```c
__int64 __fastcall GmsapGetGroupMSAPassword(
        int a1,
        struct _tagGMsaListEntry *a2,
        const struct _UNICODE_STRING *a3,
        const struct _UNICODE_STRING *a4,
        int a5,
        FILETIME *lpFileTime1,
        _OWORD *a7,
        _OWORD *a8,
        LPFILETIME lpSystemTimeAsFileTime)
{
  struct _tagGMsaListEntry *v9; // rbx
  const struct _UNICODE_STRING *v10; // r11
  BOOL v11; // edx
  unsigned __int8 *v12; // r13
  _QWORD *v15; // r10
  int DoesCachedDataRequireRefetch; // edi
  __int64 v17; // rdx
  __int64 v18; // r9
  FILETIME *v19; // r15
  _OWORD *v20; // r14
  _OWORD *v21; // r12
  int v22; // ecx
  int v23; // eax
  int v24; // edx
  int v25; // edi
  __int16 v26; // ax
  unsigned int v27; // ebx
  __int64 v28; // rdx
  unsigned __int8 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int8 *v32; // rdx
  void *v33; // rcx
  void *v34; // rcx
  void *v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  __int64 v39; // rdx
  __int64 v40; // r9
  __int16 v41; // ax
  __int16 v42; // ax
  struct _FILETIME *v43; // rdi
  int v44; // [rsp+58h] [rbp-59h]
  int v45; // [rsp+58h] [rbp-59h]
  unsigned __int8 *v46; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v47; // [rsp+68h] [rbp-49h] BYREF
  BOOL v48; // [rsp+6Ch] [rbp-45h]
  unsigned __int8 *v49; // [rsp+70h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-39h] BYREF
  HLOCAL v51; // [rsp+80h] [rbp-31h] BYREF
  int v52; // [rsp+88h] [rbp-29h] BYREF
  int v53; // [rsp+8Ch] [rbp-25h] BYREF
  int v54; // [rsp+90h] [rbp-21h] BYREF
  int v55; // [rsp+94h] [rbp-1Dh] BYREF
  int v56; // [rsp+98h] [rbp-19h] BYREF
  int v57; // [rsp+9Ch] [rbp-15h]
  FILETIME FileTime2; // [rsp+A0h] [rbp-11h] BYREF
  HLOCAL v59; // [rsp+A8h] [rbp-9h] BYREF
  struct _tagGMsaListEntry *v60; // [rsp+100h] [rbp+4Fh] BYREF
  unsigned int v61; // [rsp+108h] [rbp+57h] BYREF
  const struct _UNICODE_STRING *v62; // [rsp+110h] [rbp+5Fh]

  v62 = a4;
  v60 = a2;
  v9 = a2;
  v61 = 0;
  v47 = 0;
  FileTime2 = 0;
  v10 = a4;
  v53 = 0;
  v11 = a2 != 0;
  v52 = 0;
  v12 = 0;
  v48 = v9 != 0;
  v49 = 0;
  hMem = 0;
  v59 = 0;
  v51 = 0;
  v55 = 0;
  v56 = 0;
  v54 = 0;
  v46 = 0;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
    v15 = WPP_GLOBAL_Control;
    v10 = v62;
    v11 = v48;
  }
  if ( (v9 == 0) != (a3 != 0) )
  {
    DoesCachedDataRequireRefetch = -1073741811;
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
    {
      v17 = 81;
LABEL_8:
      v18 = 3221225485LL;
LABEL_9:
      WPP_SF_D(v15[2], v17, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v18);
LABEL_62:
      v15 = WPP_GLOBAL_Control;
      goto LABEL_63;
    }
    goto LABEL_63;
  }
  if ( a5 != 1 || !v11 && !a1 )
  {
    if ( a3 && (!a3->Buffer || !a3->Length) )
    {
      DoesCachedDataRequireRefetch = -1073741811;
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
      {
        v17 = 83;
        goto LABEL_8;
      }
      goto LABEL_63;
    }
    v19 = lpFileTime1;
    if ( lpFileTime1 )
      *lpFileTime1 = 0;
    v20 = a7;
    if ( a7 )
      *a7 = 0;
    v21 = a8;
    if ( a8 )
      *a8 = 0;
    if ( lpSystemTimeAsFileTime )
      *lpSystemTimeAsFileTime = 0;
    v22 = 0;
    if ( !v11 )
      v22 = a1;
    v23 = 0;
    v57 = v22;
    if ( !v11 )
      v23 = a5;
    v24 = 0;
    if ( !v22 )
      v24 = v23;
    v44 = v24;
    DoesCachedDataRequireRefetch = GmsapParseAccountNamesLocally(
                                     v9,
                                     a3,
                                     v10,
                                     (unsigned __int16 **)&hMem,
                                     (unsigned __int16 **)&v59,
                                     (unsigned __int16 **)&v51,
                                     &v53);
    if ( DoesCachedDataRequireRefetch < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_63;
      v17 = 84;
      goto LABEL_40;
    }
    v25 = v44;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (_DWORD)v51,
        (__int64)hMem,
        v44);
    if ( v44 == 1 )
    {
      DoesCachedDataRequireRefetch = ((__int64 (__fastcall *)(__int64, HLOCAL, HLOCAL, unsigned int *, unsigned __int8 **))xmmword_18000B5B0)(
                                       1,
                                       hMem,
                                       v51,
                                       &v61,
                                       &v46);
      if ( DoesCachedDataRequireRefetch >= 0 )
      {
        if ( v20 )
        {
          v26 = v61;
          *((_WORD *)v20 + 1) = v61;
          *(_WORD *)v20 = v26;
          *((_QWORD *)v20 + 1) = v46;
          v46 = 0;
LABEL_71:
          v15 = WPP_GLOBAL_Control;
          goto LABEL_72;
        }
        goto LABEL_62;
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_63;
      v17 = 86;
LABEL_40:
      v18 = (unsigned int)DoesCachedDataRequireRefetch;
      goto LABEL_9;
    }
    v45 = 0;
    if ( !v48 )
    {
      RtlAcquireResourceShared(&Resource, 1u);
      v45 = 1;
    }
    v27 = v57;
    DoesCachedDataRequireRefetch = GmsapDoesCachedDataRequireRefetch(
                                     v57,
                                     v25,
                                     (const unsigned __int16 *)hMem,
                                     (const unsigned __int16 *)v59,
                                     (unsigned __int16 *)v51,
                                     &v54,
                                     &v60,
                                     (struct _FILETIME)&v52,
                                     &v55);
    if ( DoesCachedDataRequireRefetch < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_59;
      v28 = 87;
      goto LABEL_57;
    }
    if ( v27 == 2 )
    {
      v9 = v60;
      DoesCachedDataRequireRefetch = -1073741772;
      if ( v60 )
        DoesCachedDataRequireRefetch = 0;
      goto LABEL_98;
    }
    if ( v52 )
    {
      DoesCachedDataRequireRefetch = GmsapGetPassword(v27, hMem, v51, &v60, &v56);
      if ( DoesCachedDataRequireRefetch < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_59;
        v28 = 89;
LABEL_57:
        WPP_SF_D(
          v15[2],
          v28,
          &WPP_70b8577d707437755865c965214ce19a_Traceguids,
          (unsigned int)DoesCachedDataRequireRefetch);
LABEL_58:
        v15 = WPP_GLOBAL_Control;
LABEL_59:
        v9 = v60;
LABEL_60:
        if ( !v45 )
          goto LABEL_63;
        RtlReleaseResource(&Resource);
        goto LABEL_62;
      }
      if ( v27 == 3 )
        goto LABEL_58;
      v9 = v60;
    }
    else
    {
      v9 = v60;
      if ( !v60 )
      {
        DoesCachedDataRequireRefetch = -1073741637;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_60;
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)v60 + 88),
          &WPP_70b8577d707437755865c965214ce19a_Traceguids,
          3221225659LL);
        goto LABEL_98;
      }
    }
    DoesCachedDataRequireRefetch = GmsapGetDecryptedData(v9, &v61, &v46, &v47, &v49, &FileTime2);
    if ( DoesCachedDataRequireRefetch < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v39 = 90;
        v40 = (unsigned int)DoesCachedDataRequireRefetch;
LABEL_114:
        WPP_SF_D(v15[2], v39, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v40);
        v12 = v49;
LABEL_98:
        v15 = WPP_GLOBAL_Control;
        goto LABEL_60;
      }
      goto LABEL_122;
    }
    if ( v19 )
    {
      if ( (v19->dwLowDateTime || v19->dwHighDateTime) && !CompareFileTime(v19, &FileTime2) )
      {
        DoesCachedDataRequireRefetch = -2147483614;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v39 = 91;
          v40 = 2147483682LL;
          goto LABEL_114;
        }
LABEL_122:
        v12 = v49;
        goto LABEL_60;
      }
      *v19 = FileTime2;
    }
    if ( v20 )
    {
      v41 = v61;
      *((_WORD *)v20 + 1) = v61;
      *(_WORD *)v20 = v41;
      *((_QWORD *)v20 + 1) = v46;
      v46 = 0;
    }
    if ( v21 )
    {
      v42 = v47;
      *((_WORD *)v21 + 1) = v47;
      *(_WORD *)v21 = v42;
      *((_QWORD *)v21 + 1) = v49;
    }
    else
    {
      v12 = v49;
    }
    v43 = lpSystemTimeAsFileTime;
    if ( lpSystemTimeAsFileTime )
    {
      if ( CompareFileTime((const FILETIME *)v9 + 7, (const FILETIME *)v9 + 5) <= 0 )
        GetSystemTimeAsFileTime(v43);
      else
        *v43 = *(struct _FILETIME *)((char *)v9 + 48);
    }
    DoesCachedDataRequireRefetch = 0;
    goto LABEL_98;
  }
  DoesCachedDataRequireRefetch = -1073741811;
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
  {
    v17 = 82;
    goto LABEL_8;
  }
LABEL_63:
  v29 = v46;
  if ( v46 )
  {
    v30 = v61;
    if ( v61 )
    {
      do
      {
        *v29++ = 0;
        --v30;
      }
      while ( v30 );
    }
    (*((void (__fastcall **)(unsigned __int8 *))&xmmword_18000B580 + 1))(v46);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v12 )
  {
    v31 = v47;
    v32 = v12;
    if ( v47 )
    {
      do
      {
        *v32++ = 0;
        --v31;
      }
      while ( v31 );
    }
    (*((void (__fastcall **)(unsigned __int8 *, unsigned __int8 *))&xmmword_18000B580 + 1))(v12, v32);
    goto LABEL_71;
  }
LABEL_72:
  if ( v53 )
  {
    GmsapFreeStringRoutine(hMem);
    GmsapFreeStringRoutine(v59);
    GmsapFreeStringRoutine(v51);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v54 && v9 )
  {
    v33 = (void *)*((_QWORD *)v9 + 2);
    if ( v33 )
    {
      LocalFree(v33);
      *((_QWORD *)v9 + 2) = 0;
    }
    v34 = (void *)*((_QWORD *)v9 + 3);
    if ( v34 )
    {
      LocalFree(v34);
      *((_QWORD *)v9 + 3) = 0;
    }
    v35 = (void *)*((_QWORD *)v9 + 4);
    if ( v35 )
    {
      LocalFree(v35);
      *((_QWORD *)v9 + 4) = 0;
    }
    v36 = (void *)*((_QWORD *)v9 + 8);
    if ( v36 )
    {
      LocalFree(v36);
      *((_QWORD *)v9 + 8) = 0;
      *((_QWORD *)v9 + 9) = 0;
    }
    v37 = (void *)*((_QWORD *)v9 + 10);
    if ( v37 )
    {
      LocalFree(v37);
      *((_QWORD *)v9 + 10) = 0;
      *((_QWORD *)v9 + 11) = 0;
    }
    LocalFree(v9);
    v15 = WPP_GLOBAL_Control;
  }
  if ( !v48 && (v55 || v56) )
  {
    (*((void (**)(void))&xmmword_18000B5A0 + 1))();
    v15 = WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
    WPP_SF_D(v15[2], 92, &WPP_70b8577d707437755865c965214ce19a_Traceguids, (unsigned int)DoesCachedDataRequireRefetch);
  return (unsigned int)DoesCachedDataRequireRefetch;
}

```

## disassembly

```asm
0x1800036c0  mov     rax, rsp
0x1800036c3  mov     [rax+8], rbx
0x1800036c7  mov     [rax+20h], r9
0x1800036cb  mov     [rax+10h], rdx
0x1800036cf  push    rbp
0x1800036d0  push    rsi
0x1800036d1  push    rdi
0x1800036d2  push    r12
0x1800036d4  push    r13
0x1800036d6  push    r14
0x1800036d8  push    r15
0x1800036da  lea     rbp, [rax-3Fh]
0x1800036de  sub     rsp, 0B0h
0x1800036e5  mov     rbx, rdx
0x1800036e8  mov     [rbp+37h+arg_10], 0
0x1800036ef  xor     edx, edx
0x1800036f1  mov     [rbp+37h+var_80], 0
0x1800036f8  test    rbx, rbx
0x1800036fb  mov     qword ptr [rbp+37h+FileTime2.dwLowDateTime], 0
0x180003703  mov     r11, r9
0x180003706  mov     [rbp+37h+var_5C], 0
0x18000370d  setnz   dl
0x180003710  mov     [rbp+37h+var_60], 0
0x180003717  xor     r13d, r13d
0x18000371a  mov     [rbp+37h+var_7C], edx
0x18000371d  mov     [rbp+37h+var_78], r13
0x180003721  mov     rdi, r8
0x180003724  mov     [rbp+37h+hMem], r13
0x180003728  mov     esi, ecx
0x18000372a  mov     [rbp+37h+var_40], r13
0x18000372e  mov     [rbp+37h+var_68], r13
0x180003732  mov     [rbp+37h+var_54], 0
0x180003739  mov     [rbp+37h+var_50], 0
0x180003740  mov     [rbp+37h+var_58], 0
0x180003747  mov     [rbp+37h+var_88], 0
0x18000374f  mov     r10, cs:WPP_GLOBAL_Control
0x180003756  lea     r8, WPP_GLOBAL_Control
0x18000375d  lea     r14, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003764  cmp     r10, r8
0x180003767  jz      short loc_180003795
0x180003769  test    byte ptr [r10+1Ch], 8
0x18000376e  jz      short loc_180003795
0x180003770  mov     rcx, [r10+10h]
0x180003774  lea     edx, [r13+50h]
0x180003778  mov     r8, r14
0x18000377b  call    WPP_SF_
0x180003780  mov     r10, cs:WPP_GLOBAL_Control
0x180003787  lea     r8, WPP_GLOBAL_Control
0x18000378e  mov     r11, [rbp+37h+arg_18]
0x180003792  mov     edx, [rbp+37h+var_7C]
0x180003795  xor     ecx, ecx
0x180003797  test    rdi, rdi
0x18000379a  setnz   cl
0x18000379d  xor     eax, eax
0x18000379f  test    rbx, rbx
0x1800037a2  setz    al
0x1800037a5  cmp     eax, ecx
0x1800037a7  jz      short loc_1800037E0
0x1800037a9  mov     edi, 0C000000Dh
0x1800037ae  cmp     r10, r8
0x1800037b1  jz      loc_180003A9C
0x1800037b7  mov     sil, 4
0x1800037ba  test    [r10+1Ch], sil
0x1800037be  jz      loc_180003A9C
0x1800037c4  mov     edx, 51h ; 'Q'
0x1800037c9  mov     r9d, 0C000000Dh
0x1800037cf  mov     r8, r14
0x1800037d2  mov     rcx, [r10+10h]
0x1800037d6  call    WPP_SF_D
0x1800037db  jmp     loc_180003A95
0x1800037e0  cmp     [rbp+37h+arg_20], 1
0x1800037e4  jnz     short loc_180003810
0x1800037e6  test    edx, edx
0x1800037e8  jnz     short loc_1800037EE
0x1800037ea  test    esi, esi
0x1800037ec  jz      short loc_180003810
0x1800037ee  mov     edi, 0C000000Dh
0x1800037f3  cmp     r10, r8
0x1800037f6  jz      loc_180003A9C
0x1800037fc  mov     sil, 4
0x1800037ff  test    [r10+1Ch], sil
0x180003803  jz      loc_180003A9C
0x180003809  mov     edx, 52h ; 'R'
0x18000380e  jmp     short loc_1800037C9
0x180003810  test    rdi, rdi
0x180003813  jz      short loc_180003844
0x180003815  cmp     [rdi+8], r13
0x180003819  jz      short loc_180003822
0x18000381b  xor     eax, eax
0x18000381d  cmp     ax, [rdi]
0x180003820  jnz     short loc_180003844
0x180003822  mov     edi, 0C000000Dh
0x180003827  cmp     r10, r8
0x18000382a  jz      loc_180003A9C
0x180003830  mov     sil, 4
0x180003833  test    [r10+1Ch], sil
0x180003837  jz      loc_180003A9C
0x18000383d  mov     edx, 53h ; 'S'
0x180003842  jmp     short loc_1800037C9
0x180003844  mov     r15, [rbp+37h+lpFileTime1]
0x180003848  test    r15, r15
0x18000384b  jz      short loc_180003852
0x18000384d  xor     eax, eax
0x18000384f  mov     [r15], rax
0x180003852  mov     r14, [rbp+37h+arg_30]
0x180003856  test    r14, r14
0x180003859  jz      short loc_180003862
0x18000385b  xorps   xmm0, xmm0
0x18000385e  movups  xmmword ptr [r14], xmm0
0x180003862  mov     r12, [rbp+37h+arg_38]
0x180003866  test    r12, r12
0x180003869  jz      short loc_180003873
0x18000386b  xorps   xmm0, xmm0
0x18000386e  movups  xmmword ptr [r12], xmm0
0x180003873  mov     rax, [rbp+37h+lpSystemTimeAsFileTime]
0x18000387a  test    rax, rax
0x18000387d  jz      short loc_180003884
0x18000387f  xor     ecx, ecx
0x180003881  mov     [rax], rcx
0x180003884  xor     ecx, ecx
0x180003886  lea     r9, [rbp+37h+hMem]; unsigned __int16 **
0x18000388a  test    edx, edx
0x18000388c  mov     r8, r11; struct _UNICODE_STRING *
0x18000388f  cmovz   ecx, esi
0x180003892  xor     eax, eax
0x180003894  test    edx, edx
0x180003896  mov     [rbp+37h+var_4C], ecx
0x180003899  cmovz   eax, [rbp+37h+arg_20]
0x18000389d  xor     edx, edx
0x18000389f  test    ecx, ecx
0x1800038a1  mov     rcx, rbx; struct _tagGMsaListEntry *
0x1800038a4  cmovz   edx, eax
0x1800038a7  lea     rax, [rbp+37h+var_5C]
0x1800038ab  mov     [rsp+0E0h+var_B0], rax; int *
0x1800038b0  lea     rax, [rbp+37h+var_68]
0x1800038b4  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 **
0x1800038b9  lea     rax, [rbp+37h+var_40]
0x1800038bd  mov     [rbp+37h+var_90], edx
0x1800038c0  mov     rdx, rdi; struct _UNICODE_STRING *
0x1800038c3  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x1800038c8  call    ?GmsapParseAccountNamesLocally@@YAJPEAU_tagGMsaListEntry@@PEBU_UNICODE_STRING@@1PEAPEAG22PEAH@Z; GmsapParseAccountNamesLocally(_tagGMsaListEntry *,_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *,int *)
0x1800038cd  mov     edi, eax
0x1800038cf  test    eax, eax
0x1800038d1  jns     short loc_18000390B
0x1800038d3  mov     r10, cs:WPP_GLOBAL_Control
0x1800038da  lea     rax, WPP_GLOBAL_Control
0x1800038e1  cmp     r10, rax
0x1800038e4  jz      loc_180003A9C
0x1800038ea  mov     sil, 4
0x1800038ed  test    [r10+1Ch], sil
0x1800038f1  jz      loc_180003A9C
0x1800038f7  mov     edx, 54h ; 'T'
0x1800038fc  mov     r9d, edi
0x1800038ff  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003906  jmp     loc_1800037D2
0x18000390b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003912  lea     rax, WPP_GLOBAL_Control
0x180003919  mov     edi, [rbp+37h+var_90]
0x18000391c  mov     sil, 4
0x18000391f  cmp     rcx, rax
0x180003922  jz      short loc_180003950
0x180003924  test    [rcx+1Ch], sil
0x180003928  jz      short loc_180003950
0x18000392a  mov     rax, [rbp+37h+hMem]
0x18000392e  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003935  mov     r9, [rbp+37h+var_68]
0x180003939  mov     edx, 55h ; 'U'
0x18000393e  mov     rcx, [rcx+10h]
0x180003942  mov     dword ptr [rsp+0E0h+var_B8], edi
0x180003946  mov     [rsp+0E0h+var_C0], rax
0x18000394b  call    WPP_SF_SSD
0x180003950  cmp     edi, 1
0x180003953  jnz     short loc_1800039CF
0x180003955  mov     r8, [rbp+37h+var_68]
0x180003959  lea     rax, [rbp+37h+var_88]
0x18000395d  mov     rdx, [rbp+37h+hMem]
0x180003961  lea     r9, [rbp+37h+arg_10]
0x180003965  mov     [rsp+0E0h+var_C0], rax
0x18000396a  mov     ecx, edi
0x18000396c  mov     rax, qword ptr cs:xmmword_18000B5B0
0x180003973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003978  mov     edi, eax
0x18000397a  test    eax, eax
0x18000397c  jns     short loc_1800039A9
0x18000397e  mov     r10, cs:WPP_GLOBAL_Control
0x180003985  lea     rax, WPP_GLOBAL_Control
0x18000398c  cmp     r10, rax
0x18000398f  jz      loc_180003A9C
0x180003995  test    [r10+1Ch], sil
0x180003999  jz      loc_180003A9C
0x18000399f  mov     edx, 56h ; 'V'
0x1800039a4  jmp     loc_1800038FC
0x1800039a9  test    r14, r14
0x1800039ac  jz      loc_180003A95
0x1800039b2  mov     eax, [rbp+37h+arg_10]
0x1800039b5  mov     [r14+2], ax
0x1800039ba  mov     [r14], ax
0x1800039be  mov     rax, [rbp+37h+var_88]
0x1800039c2  mov     [r14+8], rax
0x1800039c6  mov     [rbp+37h+var_88], r13
0x1800039ca  jmp     loc_180003AFB
0x1800039cf  mov     [rbp+37h+var_90], r13d
0x1800039d3  cmp     [rbp+37h+var_7C], r13d
0x1800039d7  jnz     short loc_1800039F5
0x1800039d9  mov     dl, 1; Wait
0x1800039db  lea     rcx, Resource; Resource
0x1800039e2  call    cs:__imp_RtlAcquireResourceShared
0x1800039e9  nop     dword ptr [rax+rax+00h]
0x1800039ee  mov     [rbp+37h+var_90], 1
0x1800039f5  mov     ebx, [rbp+37h+var_4C]
0x1800039f8  lea     rax, [rbp+37h+var_54]
0x1800039fc  mov     r9, [rbp+37h+var_40]
0x180003a00  mov     edx, edi
0x180003a02  mov     r8, [rbp+37h+hMem]
0x180003a06  mov     ecx, ebx
0x180003a08  mov     [rsp+40h], rax
0x180003a0d  lea     rax, [rbp+37h+var_60]
0x180003a11  mov     [rsp+0E0h+var_A8], rax
0x180003a16  lea     rax, [rbp+37h+arg_8]
0x180003a1a  mov     [rsp+0E0h+var_B0], rax
0x180003a1f  lea     rax, [rbp+37h+var_58]
0x180003a23  mov     [rsp+0E0h+var_B8], rax
0x180003a28  mov     rax, [rbp+37h+var_68]
0x180003a2c  mov     [rsp+0E0h+var_C0], rax
0x180003a31  call    ?GmsapDoesCachedDataRequireRefetch@@YAJW4_tagCredFetchInt@@W4_CRED_FETCH@@PEBG22PEAHPEAPEAU_tagGMsaListEntry@@33@Z; GmsapDoesCachedDataRequireRefetch(_tagCredFetchInt,_CRED_FETCH,ushort const *,ushort const *,ushort const *,int *,_tagGMsaListEntry * *,int *,int *)
0x180003a36  mov     edi, eax
0x180003a38  test    eax, eax
0x180003a3a  jns     loc_180003C62
0x180003a40  mov     r10, cs:WPP_GLOBAL_Control
0x180003a47  lea     rax, WPP_GLOBAL_Control
0x180003a4e  cmp     r10, rax
0x180003a51  jz      short loc_180003A78
0x180003a53  test    [r10+1Ch], sil
0x180003a57  jz      short loc_180003A78
0x180003a59  mov     edx, 57h ; 'W'
0x180003a5e  mov     rcx, [r10+10h]
0x180003a62  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180003a69  mov     r9d, edi
0x180003a6c  call    WPP_SF_D
0x180003a71  mov     r10, cs:WPP_GLOBAL_Control
0x180003a78  mov     rbx, [rbp+37h+arg_8]
0x180003a7c  cmp     [rbp+37h+var_90], 0
0x180003a80  jz      short loc_180003A9C
0x180003a82  lea     rcx, Resource; Resource
0x180003a89  call    cs:__imp_RtlReleaseResource
0x180003a90  nop     dword ptr [rax+rax+00h]
0x180003a95  mov     r10, cs:WPP_GLOBAL_Control
0x180003a9c  mov     rax, [rbp+37h+var_88]
0x180003aa0  test    rax, rax
0x180003aa3  jz      short loc_180003AD0
0x180003aa5  mov     ecx, [rbp+37h+arg_10]
0x180003aa8  test    rcx, rcx
0x180003aab  jz      short loc_180003AB9
0x180003aad  mov     byte ptr [rax], 0
0x180003ab0  inc     rax
0x180003ab3  sub     rcx, 1
0x180003ab7  jnz     short loc_180003AAD
0x180003ab9  mov     rcx, [rbp+37h+var_88]
0x180003abd  mov     rax, qword ptr cs:xmmword_18000B580+8
0x180003ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac9  mov     r10, cs:WPP_GLOBAL_Control
0x180003ad0  test    r13, r13
0x180003ad3  jz      short loc_180003B02
0x180003ad5  mov     eax, [rbp+37h+var_80]
0x180003ad8  mov     rdx, r13
0x180003adb  test    rax, rax
0x180003ade  jz      short loc_180003AEC
0x180003ae0  mov     byte ptr [rdx], 0
0x180003ae3  inc     rdx
0x180003ae6  sub     rax, 1
0x180003aea  jnz     short loc_180003AE0
0x180003aec  mov     rax, qword ptr cs:xmmword_18000B580+8
0x180003af3  mov     rcx, r13
0x180003af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003afb  mov     r10, cs:WPP_GLOBAL_Control
0x180003b02  cmp     [rbp+37h+var_5C], 0
0x180003b06  jz      short loc_180003B2A
0x180003b08  mov     rcx, [rbp+37h+hMem]; hMem
0x180003b0c  call    GmsapFreeStringRoutine
0x180003b11  mov     rcx, [rbp+37h+var_40]; hMem
0x180003b15  call    GmsapFreeStringRoutine
0x180003b1a  mov     rcx, [rbp+37h+var_68]; hMem
0x180003b1e  call    GmsapFreeStringRoutine
0x180003b23  mov     r10, cs:WPP_GLOBAL_Control
0x180003b2a  cmp     [rbp+37h+var_58], 0
0x180003b2e  jz      loc_180003BF4
0x180003b34  test    rbx, rbx
0x180003b37  jz      loc_180003BF4
0x180003b3d  mov     rcx, [rbx+10h]; hMem
0x180003b41  test    rcx, rcx
0x180003b44  jz      short loc_180003B5A
0x180003b46  call    cs:__imp_LocalFree
0x180003b4d  nop     dword ptr [rax+rax+00h]
0x180003b52  mov     qword ptr [rbx+10h], 0
0x180003b5a  mov     rcx, [rbx+18h]; hMem
0x180003b5e  test    rcx, rcx
0x180003b61  jz      short loc_180003B77
0x180003b63  call    cs:__imp_LocalFree
0x180003b6a  nop     dword ptr [rax+rax+00h]
0x180003b6f  mov     qword ptr [rbx+18h], 0
  ... truncated ...
```
