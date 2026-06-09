# LdrpPreprocessDllName

- ea: `0x18001dc60`
- end: `0x18001e811`
- name: `LdrpPreprocessDllName`
- size: `2993`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x180022aa0`
- `0x18002c970`
- `0x180119f5c`
- `0x1801235d8`
- `0x1801253a0`
- `0x18015d25c`

## callees

- `0x18001bcb0`
- `0x18001d490`
- `0x18001dc60`
- `0x18001eb80`
- `0x18001f154`
- `0x18001f900`
- `0x18001faf0`
- `0x180021fe0`
- `0x1800248a0`
- `0x180028020`
- `0x180028180`
- `0x180029b70`
- `0x18004cef8`
- `0x1800526f0`
- `0x18005d660`
- `0x18011fba4`
- `0x18012c830`
- `0x180163a80`

## string_xrefs

- `0x18001e1fa`: `LdrpPreprocessDllName`
- `0x18001e33e`: `LdrpPreprocessDllName`
- `0x18001e214`: `LdrpPreprocessDllName for DLL %wZ failed with status 0x%08lx\n`
- `0x18001e356`: `DLL %wZ was redirected to %wZ by %s\n`

## pseudocode

```c
__int64 __fastcall LdrpPreprocessDllName(unsigned __int16 *a1, unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  _DWORD *v4; // rsi
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // r9
  __int64 v7; // r14
  struct _PEB *v8; // rax
  __int64 v9; // r15
  _DWORD *ApiSetMap; // rbx
  _DWORD *SharedData; // rcx
  __int64 v12; // rcx
  __int64 v13; // r12
  unsigned __int16 *v14; // r10
  int v15; // r8d
  int v16; // eax
  unsigned __int16 v17; // r14
  int appended; // ebx
  char v19; // si
  _DWORD *v20; // rcx
  __int64 v21; // r15
  _DWORD *v22; // rcx
  __int64 v23; // rsi
  size_t v24; // rax
  unsigned __int16 v25; // bx
  int v26; // ecx
  unsigned int v27; // edx
  int v28; // ecx
  __int64 v29; // rdx
  int v30; // ecx
  unsigned int v31; // edx
  unsigned __int16 v32; // ax
  _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rax
  char v34; // al
  int v35; // edx
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  _DWORD *v38; // rcx
  int v39; // ecx
  _WORD *v40; // rax
  __int64 v41; // rax
  __int64 v42; // r14
  __int64 v43; // rax
  char v44; // r14
  unsigned __int64 v45; // rdx
  unsigned __int16 *v46; // r14
  _WORD *v47; // rax
  __int64 v48; // r9
  int v49; // edx
  unsigned __int64 v50; // rdx
  __int16 *v51; // rax
  __int16 v52; // cx
  unsigned int v53; // ecx
  unsigned __int64 v55; // rcx
  __int64 v56; // rdx
  _WORD *i; // rax
  int v58; // esi
  __int64 FullPathName_Ustr; // rbx
  _WORD *v60; // r14
  unsigned __int16 *v61; // rcx
  unsigned __int16 *v62; // rdx
  unsigned int v63; // ebx
  void *v64; // rsi
  unsigned int v65; // r12d
  unsigned __int16 *v66; // rdx
  unsigned int v67; // r12d
  __int64 v68; // rax
  unsigned __int16 *v69; // rdx
  unsigned int v70; // ebx
  __int64 v71; // rax
  unsigned int v72; // ebx
  unsigned __int16 *v73; // rdx
  unsigned int v74; // ebx
  void *v75; // rsi
  void *Atom; // r15
  void *v77; // rsi
  __int64 v78; // rcx
  unsigned __int16 *v79; // rdx
  unsigned int v80; // ebx
  void *v81; // rsi
  char v82; // [rsp+58h] [rbp-9h] BYREF
  char v83; // [rsp+59h] [rbp-8h]
  struct _PEB *v84; // [rsp+60h] [rbp-1h] BYREF
  void *Src[2]; // [rsp+68h] [rbp+7h] BYREF
  _OWORD v86[4]; // [rsp+78h] [rbp+17h] BYREF

  v4 = a4;
  v5 = a2;
  v6 = a1;
  if ( (*v4 & 0x800008) != 0 )
  {
    appended = 0;
    v44 = 0;
    goto LABEL_69;
  }
  v7 = a3 + 88;
  v82 = 0;
  v86[0] = 0;
  v8 = NtCurrentPeb();
  if ( !a3 )
    v7 = 0;
  v84 = v8;
  *(_OWORD *)Src = 0;
  v9 = 2147353476;
  ApiSetMap = v8->ApiSetMap;
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
    v12 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v12 = 2147353476;
  v13 = 2147353477;
  if ( *(_BYTE *)v12 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v12, a2, a3, v6) )
      v78 = (__int64)NtCurrentPeb()->SharedData + 555;
    else
      v78 = 2147353477;
    if ( (*(_BYTE *)v78 & 0x20) != 0 )
      LdrpLogEtwEvent(5328, 0, 0, 0, (__int64)a1, 0);
    v6 = a1;
  }
  if ( *(_BYTE *)ApiSetMap != 7 )
  {
    if ( *ApiSetMap == 6
      && ApiSetMap[4] > 8u
      && *((_BYTE *)ApiSetMap + 28) == 7
      && (*((_BYTE *)ApiSetMap + 30) & 4) == 0 )
    {
      LODWORD(ApiSetMap) = (_DWORD)ApiSetMap + 28;
      goto LABEL_14;
    }
    v36 = *v6;
    v19 = 0;
    if ( (unsigned int)v36 >= 8 )
    {
      a2 = (unsigned __int16 *)*((_QWORD *)v6 + 1);
      v37 = *(_QWORD *)a2 & 0xFFFFFFDFFFDFFFDFuLL;
      if ( v37 == 0x2D004900500041LL || (a3 = 0x2D005400580045LL, v37 == 0x2D005400580045LL) )
      {
        v40 = (unsigned __int16 *)((char *)a2 + v36);
        a3 = *v6;
        do
        {
          if ( (unsigned int)a3 <= 1 )
            break;
          --v40;
          a3 = (unsigned int)(a3 - 2);
        }
        while ( *v40 != 45 );
        LOWORD(a3) = (unsigned __int16)a3 >> 1;
        if ( (_WORD)a3 )
        {
          v41 = ApiSetpSearchForApiSet(ApiSetMap);
          if ( v41 )
          {
            if ( v7 && *(_DWORD *)(v41 + 20) > 1u )
            {
              v42 = ApiSetpSearchForApiSetHost(v41, *(_QWORD *)(v7 + 8), *(_WORD *)v7 >> 1, ApiSetMap);
LABEL_57:
              v43 = *(unsigned int *)(v42 + 12);
              v19 = 1;
              v17 = *(_WORD *)(v42 + 16);
              Src[1] = (char *)ApiSetMap + v43;
              goto LABEL_39;
            }
            if ( *(_DWORD *)(v41 + 20) )
            {
              v42 = (__int64)ApiSetMap + *(unsigned int *)(v41 + 16);
              goto LABEL_57;
            }
          }
        }
      }
    }
    v17 = (unsigned __int16)Src[0];
LABEL_39:
    appended = 0;
    goto LABEL_40;
  }
LABEL_14:
  v14 = v6;
  v15 = *v6 >> 1;
  LOBYTE(v6) = 1;
  v16 = ApiSetpResolveHost((_DWORD)ApiSetMap, *((_QWORD *)v14 + 1), v15, (_DWORD)v6, v7, (__int64)&v82, (__int64)Src);
  v17 = (unsigned __int16)Src[0];
  appended = v16;
  v19 = v82;
  if ( v16 < 0 )
  {
LABEL_15:
    v20 = NtCurrentPeb()->SharedData;
    if ( v20 && *v20 )
      v9 = (__int64)NtCurrentPeb()->SharedData + 554;
    if ( !*(_BYTE *)v9 || (NtCurrentPeb()->TracingFlags & 4) == 0 )
    {
LABEL_18:
      LODWORD(v21) = (_DWORD)a1;
      goto LABEL_19;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v20, a2, a3, v6) )
      v13 = (__int64)NtCurrentPeb()->SharedData + 555;
    v21 = (__int64)a1;
    if ( (*(_BYTE *)v13 & 0x20) != 0 )
    {
      v39 = 5331;
      goto LABEL_178;
    }
    goto LABEL_19;
  }
LABEL_40:
  if ( !v19 )
    goto LABEL_15;
  if ( !v17 )
  {
    LODWORD(v21) = (_DWORD)a1;
    LdrpLogDllState(0, a1, 5330);
    goto LABEL_19;
  }
  v38 = NtCurrentPeb()->SharedData;
  if ( v38 && *v38 )
    v9 = (__int64)NtCurrentPeb()->SharedData + 554;
  if ( !*(_BYTE *)v9 || (NtCurrentPeb()->TracingFlags & 4) == 0 )
    goto LABEL_18;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v38, a2, a3, v6) )
    v13 = (__int64)NtCurrentPeb()->SharedData + 555;
  v21 = (__int64)a1;
  if ( (*(_BYTE *)v13 & 0x20) != 0 )
  {
    v39 = 5329;
LABEL_178:
    LdrpLogEtwEvent(v39, 0, 0, 0, v21, 0);
  }
LABEL_19:
  if ( v19 )
  {
    if ( !v17 )
    {
      appended = -1073740671;
      v44 = 0;
      goto LABEL_67;
    }
    *v5 = 0;
    v22 = NtCurrentPeb()->SharedData;
    if ( v22 && *v22 )
    {
      v23 = (__int64)NtCurrentPeb()->SharedData + 30;
      if ( !v23 )
        goto LABEL_28;
    }
    else
    {
      v23 = 2147352624;
    }
    v24 = wcslen((const wchar_t *)v23);
    a3 = 65534;
    v25 = 2 * v24;
    if ( 2 * v24 >= 0xFFFE )
      v25 = -4;
    if ( v25 )
    {
      v26 = *v5;
      v27 = v25 + v26 + 2;
      if ( v27 <= v5[1] )
        goto LABEL_27;
      if ( v27 <= 0xFFFE )
      {
        v65 = v27 + 63;
        v66 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
        v67 = v65 & 0xFFFFFFC0;
        if ( v67 > 0xFFFE )
          v67 = 65534;
        if ( v66 == v5 + 8 )
        {
          Atom = (void *)RtlpAllocateAtom(v67);
          if ( !Atom )
            goto LABEL_28;
          if ( *v5 )
            memmove(Atom, *((const void **)v5 + 1), *v5);
          LOWORD(v26) = *v5;
          *((_QWORD *)v5 + 1) = Atom;
          v5[1] = v67;
        }
        else
        {
          v68 = NtdllpReallocateStringRoutine(v67, v66, 65534, v6);
          if ( !v68 )
            goto LABEL_28;
          LOWORD(v26) = *v5;
          *((_QWORD *)v5 + 1) = v68;
          v5[1] = v67;
        }
LABEL_27:
        memmove((void *)(*((_QWORD *)v5 + 1) + (unsigned __int16)v26), (const void *)v23, v25);
        *v5 += v25;
        *(_WORD *)(*((_QWORD *)v5 + 1) + 2 * ((unsigned __int64)*v5 >> 1)) = 0;
LABEL_28:
        a3 = 65534;
      }
    }
    v28 = *v5;
    if ( v28 + 22 <= (unsigned int)v5[1] )
    {
LABEL_30:
      v29 = *((_QWORD *)v5 + 1) + (unsigned __int16)v28;
      *(_OWORD *)v29 = *(_OWORD *)L"\\SYSTEM32\\";
      *(_DWORD *)(v29 + 16) = *(_DWORD *)L"2\\";
      *v5 += 20;
      *(_WORD *)(*((_QWORD *)v5 + 1) + 2 * ((unsigned __int64)*v5 >> 1)) = 0;
      goto LABEL_31;
    }
    if ( (unsigned int)(v28 + 22) <= 0xFFFE )
    {
      v69 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
      v70 = (v28 + 85) & 0xFFFFFFC0;
      if ( v70 > 0xFFFE )
        v70 = 65534;
      if ( v69 == v5 + 8 )
      {
        v77 = (void *)RtlpAllocateAtom(v70);
        if ( v77 )
        {
          if ( *v5 )
            memmove(v77, *((const void **)v5 + 1), *v5);
          LOWORD(v28) = *v5;
          *((_QWORD *)v5 + 1) = v77;
          v5[1] = v70;
          goto LABEL_30;
        }
      }
      else
      {
        v71 = NtdllpReallocateStringRoutine(v70, v69, 65534, v6);
        if ( v71 )
        {
          LOWORD(v28) = *v5;
          *((_QWORD *)v5 + 1) = v71;
          v5[1] = v70;
          goto LABEL_30;
        }
      }
    }
LABEL_31:
    v30 = *v5;
    v31 = v17 + v30 + 2;
    if ( v31 <= v5[1] )
    {
LABEL_32:
      memmove((void *)(*((_QWORD *)v5 + 1) + (unsigned __int16)v30), Src[1], v17);
      v32 = *v5 + v17;
      appended = 0;
      *v5 = v32;
      *(_WORD *)(*((_QWORD *)v5 + 1) + 2 * ((unsigned __int64)v32 >> 1)) = 0;
      ProcessParameters = v84->ProcessParameters;
      if ( ProcessParameters && (ProcessParameters->Flags & 0x1000) != 0 )
      {
        v34 = 1;
        v35 = (int)v5;
      }
      else
      {
        v34 = 0;
        v35 = (int)v5;
      }
      goto LABEL_63;
    }
    if ( v31 > 0xFFFE )
    {
      appended = -1073741562;
      v44 = 0;
      goto LABEL_67;
    }
    v72 = v31 + 63;
    v73 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
    v74 = v72 & 0xFFFFFFC0;
    if ( v74 > 0xFFFE )
      v74 = 65534;
    if ( v73 == v5 + 8 )
    {
      v75 = (void *)RtlpAllocateAtom(v74);
      if ( !v75 )
        goto LABEL_143;
      if ( *v5 )
        memmove(v75, *((const void **)v5 + 1), *v5);
    }
    else
    {
      v75 = (void *)NtdllpReallocateStringRoutine(v74, v73, a3, v6);
      if ( !v75 )
      {
LABEL_143:
        appended = -1073741801;
        v44 = 0;
        goto LABEL_67;
      }
    }
    LOWORD(v30) = *v5;
    *((_QWORD *)v5 + 1) = v75;
    v5[1] = v74;
    goto LABEL_32;
  }
  if ( appended < 0 )
  {
LABEL_64:
    v44 = 0;
    goto LABEL_67;
  }
  v34 = 1;
  v35 = v21;
LABEL_63:
  if ( !v34 || LdrpIsSecureProcess )
    goto LABEL_64;
  v58 = RtlDosApplyFileIsolationRedirection_Ustr(1, v35, (unsigned int)L"\b\n", 0, (__int64)v86, 0, 0, 0, 0);
  if ( v58 >= 0 )
  {
    v83 = 1;
    Src[0] = 0;
    v82 = 0;
    v84 = 0;
    while ( 1 )
    {
      FullPathName_Ustr = (unsigned int)RtlGetFullPathName_Ustr(v86, v5[1], *((_QWORD *)v5 + 1), Src, &v82, &v84);
      if ( v82
        || (unsigned int)(FullPathName_Ustr - 1) > 0xFFFD
        || (_DWORD)v84 == 5 && (HIDWORD(v84) & LdrpIllegalCWDDevices) != 0 )
      {
        break;
      }
      if ( (unsigned int)FullPathName_Ustr < v5[1] )
      {
        *v5 = FullPathName_Ustr;
        break;
      }
      v60 = (_WORD *)RtlpAllocateAtom(FullPathName_Ustr);
      if ( !v60 )
        break;
      v61 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
      if ( v5 + 8 != v61 )
        RtlpSysVolFree(v61);
      v5[8] = 0;
      *((_QWORD *)v5 + 1) = v60;
      *v5 = 0;
      v5[1] = FullPathName_Ustr;
      *v60 = 0;
    }
    if ( *((_QWORD *)&v86[0] + 1) )
      RtlpSysVolFree(*((_QWORD *)&v86[0] + 1));
    v44 = v83;
    goto LABEL_66;
  }
  v44 = 0;
  if ( v58 != -1072365560 )
LABEL_66:
    appended = v58;
LABEL_67:
  if ( appended < 0 )
    goto LABEL_89;
  v6 = a1;
  v4 = a4;
LABEL_69:
  if ( *v5 )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      2801,
      (int)"LdrpPreprocessDllName",
      2,
      "DLL %wZ was redirected to %wZ by %s\n",
      (char)v6);
    *v4 |= 0x200u;
    if ( v44 )
      *v4 |= 4u;
    v46 = v5;
    goto LABEL_80;
  }
  v45 = *((_QWORD *)v6 + 1);
  v46 = v6;
  v47 = (_WORD *)(v45 + *v6);
  do
  {
    if ( (unsigned __int64)--v47 < v45 )
    {
      *v4 |= 0x20u;
      appended = 0;
      v49 = *v6;
      if ( !(_WORD)v49 )
        goto LABEL_80;
      a3 = v49 + (unsigned int)*v5 + 2;
      if ( (unsigned int)a3 <= v5[1] )
        goto LABEL_79;
      if ( (unsigned int)a3 <= 0xFFFE )
      {
        v62 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
        v63 = (a3 + 63) & 0xFFFFFFC0;
        if ( v63 > 0xFFFE )
          v63 = 65534;
        if ( v62 == v5 + 8 )
        {
          v64 = (void *)RtlpAllocateAtom(v63);
          if ( !v64 )
            goto LABEL_125;
          if ( *v5 )
            memmove(v64, *((const void **)v5 + 1), *v5);
        }
        else
        {
          v64 = (void *)NtdllpReallocateStringRoutine(v63, v62, a3, v6);
          if ( !v64 )
          {
LABEL_125:
            appended = -1073741801;
            goto LABEL_80;
          }
        }
        v6 = a1;
        *((_QWORD *)v5 + 1) = v64;
        v5[1] = v63;
        LOWORD(v49) = *a1;
LABEL_79:
        appended = 0;
        memmove((void *)(*((_QWORD *)v5 + 1) + *v5), *((const void **)v6 + 1), (unsigned __int16)v49);
        *v5 += *a1;
        *(_WORD *)(*((_QWORD *)v5 + 1) + 2 * ((unsigned __int64)*v5 >> 1)) = 0;
        goto LABEL_80;
      }
      appended = -1073741562;
LABEL_80:
      if ( appended >= 0 )
        goto LABEL_81;
      goto LABEL_89;
    }
  }
  while ( *v47 != 92 && *v47 != 47 );
  if ( (unsigned int)RtlDetermineDosPathNameType_Ustr(v6, v45, a3, v6) == 5 )
  {
    appended = LdrpAppendUnicodeStringToFilenameBuffer(v5, v48);
    goto LABEL_80;
  }
  appended = LdrpGetFullPath(v48, v5);
  if ( appended < 0 )
    goto LABEL_89;
  *v4 |= 0x600u;
LABEL_81:
  v50 = *((_QWORD *)v46 + 1);
  v51 = (__int16 *)(v50 + *v46);
  do
  {
    if ( (unsigned __int64)--v51 < v50 )
      break;
    v52 = *v51;
    if ( *v51 == 46 )
    {
      v55 = *((_QWORD *)v5 + 1);
      v56 = *v5;
      for ( i = (_WORD *)(v56 + v55 - 2); (unsigned __int64)i >= v55; *v5 = v56 )
      {
        if ( *i != 46 )
          break;
        LOWORD(v56) = v56 - 2;
        --i;
      }
      i[1] = 0;
      return (unsigned int)appended;
    }
  }
  while ( v52 != 47 && v52 != 92 );
  v53 = *v5 + 10;
  if ( v53 > v5[1] )
  {
    if ( v53 > 0xFFFE )
    {
      appended = -1073741562;
      goto LABEL_88;
    }
    v79 = (unsigned __int16 *)*((_QWORD *)v5 + 1);
    v80 = (*v5 + 73) & 0xFFFFFFC0;
    if ( v80 > 0xFFFE )
      v80 = 65534;
    if ( v79 == v5 + 8 )
    {
      v81 = (void *)RtlpAllocateAtom(v80);
      if ( !v81 )
        goto LABEL_186;
      if ( *v5 )
        memmove(v81, *((const void **)v5 + 1), *v5);
    }
    else
    {
      v81 = (void *)NtdllpReallocateStringRoutine(v80, v79, a3, v6);
      if ( !v81 )
      {
LABEL_186:
        appended = -1073741801;
        goto LABEL_88;
      }
    }
    *((_QWORD *)v5 + 1) = v81;
    v5[1] = v80;
  }
  appended = 0;
  *(_QWORD *)(*v5 + *((_QWORD *)v5 + 1)) = *(_QWORD *)L".DLL";
  *v5 += 8;
  *(_WORD *)(*((_QWORD *)v5 + 1) + 2 * ((unsigned __int64)*v5 >> 1)) = 0;
LABEL_88:
  if ( appended >= 0 )
    return (unsigned int)appended;
LABEL_89:
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrutil.c",
    2862,
    (int)"LdrpPreprocessDllName",
    0,
    "LdrpPreprocessDllName for DLL %wZ failed with status 0x%08lx\n",
    (char)a1);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001dc60  mov     rax, rsp
0x18001dc63  mov     [rax+20h], r9
0x18001dc67  mov     [rax+8], rcx
0x18001dc6b  push    rbp
0x18001dc6c  push    rbx
0x18001dc6d  push    rsi
0x18001dc6e  push    rdi
0x18001dc6f  push    r13
0x18001dc71  push    r14
0x18001dc73  lea     rbp, [rax-5Fh]
0x18001dc77  sub     rsp, 88h
0x18001dc7e  mov     rsi, r9
0x18001dc81  xor     r13d, r13d
0x18001dc84  mov     rdi, rdx
0x18001dc87  mov     r9, rcx
0x18001dc8a  mov     r10d, 0FFFEh
0x18001dc90  test    dword ptr [rsi], 800008h
0x18001dc96  jnz     loc_18001E806
0x18001dc9c  mov     [rax+10h], r12
0x18001dca0  lea     r14, [r8+58h]
0x18001dca4  mov     [rax-38h], r15
0x18001dca8  test    r8, r8
0x18001dcab  xorps   xmm1, xmm1
0x18001dcae  mov     [rbp+57h+var_60], r13b
0x18001dcb2  movups  xmmword ptr [rbp+17h], xmm1
0x18001dcb6  mov     rax, gs:60h
0x18001dcbf  cmovz   r14, r13
0x18001dcc3  mov     [rbp+57h+var_58], rax
0x18001dcc7  xorps   xmm0, xmm0
0x18001dcca  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001dcce  mov     r15d, 7FFE0384h
0x18001dcd4  mov     rbx, [rax+68h]
0x18001dcd8  mov     rax, gs:60h
0x18001dce1  mov     rcx, [rax+90h]
0x18001dce8  test    rcx, rcx
0x18001dceb  jnz     loc_18001E3CE
0x18001dcf1  mov     rcx, r15
0x18001dcf4  mov     r12d, 7FFE0385h
0x18001dcfa  cmp     [rcx], r13b
0x18001dcfd  jz      short loc_18001DD15
0x18001dcff  mov     rax, gs:60h
0x18001dd08  test    byte ptr [rax+378h], 4
0x18001dd0f  jnz     loc_18001E6B7
0x18001dd15  cmp     byte ptr [rbx], 7
0x18001dd18  jz      short loc_18001DD45
0x18001dd1a  cmp     dword ptr [rbx], 6
0x18001dd1d  jnz     loc_18001DF1B
0x18001dd23  cmp     dword ptr [rbx+10h], 8
0x18001dd27  jbe     loc_18001DF1B
0x18001dd2d  cmp     byte ptr [rbx+1Ch], 7
0x18001dd31  jnz     loc_18001DF1B
0x18001dd37  test    byte ptr [rbx+1Eh], 4
0x18001dd3b  jnz     loc_18001DF1B
0x18001dd41  add     rbx, 1Ch
0x18001dd45  movzx   r8d, word ptr [r9]
0x18001dd49  lea     rcx, [rbp+57h+Src]
0x18001dd4d  mov     [rsp+0B0h+var_80], rcx
0x18001dd52  lea     rax, [rbp+57h+var_60]
0x18001dd56  mov     r10, r9
0x18001dd59  mov     qword ptr [rsp+0B0h+ArgList], rax
0x18001dd5e  mov     edx, 8
0x18001dd63  shr     r8w, 1
0x18001dd67  mov     r9b, 1
0x18001dd6a  mov     [rsp+0B0h+Format], r14
0x18001dd6f  mov     rcx, rbx
0x18001dd72  mov     rdx, [r10+rdx]
0x18001dd76  call    ApiSetpResolveHost
0x18001dd7b  movzx   r14d, word ptr [rbp+57h+Src]
0x18001dd80  mov     ebx, eax
0x18001dd82  movzx   esi, [rbp+57h+var_60]
0x18001dd86  test    eax, eax
0x18001dd88  jns     loc_18001DF69
0x18001dd8e  mov     rax, gs:60h
0x18001dd97  mov     rcx, [rax+90h]
0x18001dd9e  test    rcx, rcx
0x18001dda1  jnz     loc_18001E55C
0x18001dda7  cmp     [r15], r13b
0x18001ddaa  jz      short loc_18001DDC2
0x18001ddac  mov     rax, gs:60h
0x18001ddb5  test    byte ptr [rax+378h], 4
0x18001ddbc  jnz     loc_18001E72C
0x18001ddc2  mov     r15, qword ptr [rbp+57h+arg_0]
0x18001ddc6  test    sil, sil
0x18001ddc9  jz      loc_18001E07D
0x18001ddcf  test    r14w, r14w
0x18001ddd3  jz      loc_18001E073
0x18001ddd9  mov     [rdi], r13w
0x18001dddd  mov     rax, gs:60h
0x18001dde6  mov     rcx, [rax+90h]
0x18001dded  test    rcx, rcx
0x18001ddf0  jnz     loc_18001E39C
0x18001ddf6  mov     esi, 7FFE0030h
0x18001ddfb  mov     rcx, rsi; String
0x18001ddfe  call    wcslen
0x18001de03  mov     rbx, rax
0x18001de06  mov     r8d, 0FFFEh
0x18001de0c  add     rbx, rbx
0x18001de0f  mov     eax, 0FFFCh
0x18001de14  cmp     rbx, r8
0x18001de17  cmovnb  rbx, rax
0x18001de1b  test    bx, bx
0x18001de1e  jz      short loc_18001DE62
0x18001de20  movzx   ecx, word ptr [rdi]
0x18001de23  movzx   eax, bx
0x18001de26  lea     edx, [rcx+2]
0x18001de29  add     edx, eax
0x18001de2b  movzx   eax, word ptr [rdi+2]
0x18001de2f  cmp     edx, eax
0x18001de31  ja      loc_18001E477
0x18001de37  movzx   ecx, cx
0x18001de3a  mov     rdx, rsi; Src
0x18001de3d  add     rcx, [rdi+8]; void *
0x18001de41  movzx   r8d, bx; Size
0x18001de45  call    memmove
0x18001de4a  add     [rdi], bx
0x18001de4d  movzx   ecx, word ptr [rdi]
0x18001de50  mov     rax, [rdi+8]
0x18001de54  shr     rcx, 1
0x18001de57  mov     [rax+rcx*2], r13w
0x18001de5c  mov     r8d, 0FFFEh
0x18001de62  movzx   ecx, word ptr [rdi]
0x18001de65  movzx   eax, word ptr [rdi+2]
0x18001de69  lea     edx, [rcx+16h]
0x18001de6c  cmp     edx, eax
0x18001de6e  ja      loc_18001E4C5
0x18001de74  mov     rax, cs:off_180170110; "\\SYSTEM32\\"
0x18001de7b  movzx   edx, cx
0x18001de7e  add     rdx, [rdi+8]
0x18001de82  movups  xmm0, xmmword ptr [rax]
0x18001de85  movups  xmmword ptr [rdx], xmm0
0x18001de88  mov     eax, [rax+10h]
0x18001de8b  mov     [rdx+10h], eax
0x18001de8e  add     word ptr [rdi], 14h
0x18001de92  movzx   ecx, word ptr [rdi]
0x18001de95  mov     rax, [rdi+8]
0x18001de99  shr     rcx, 1
0x18001de9c  mov     [rax+rcx*2], r13w
0x18001dea1  mov     ebx, r13d
0x18001dea4  test    r14w, r14w
0x18001dea8  jz      short loc_18001DEF7
0x18001deaa  movzx   ecx, word ptr [rdi]
0x18001dead  movzx   eax, r14w
0x18001deb1  lea     edx, [rcx+2]
0x18001deb4  add     edx, eax
0x18001deb6  movzx   eax, word ptr [rdi+2]
0x18001deba  cmp     edx, eax
0x18001debc  ja      loc_18001E50F
0x18001dec2  mov     rdx, [rbp+57h+Src+8]; Src
0x18001dec6  movzx   ecx, cx
0x18001dec9  add     rcx, [rdi+8]; void *
0x18001decd  movzx   ebx, r14w
0x18001ded1  mov     r8d, ebx; Size
0x18001ded4  call    memmove
0x18001ded9  movzx   ecx, word ptr [rdi]
0x18001dedc  lea     eax, [rcx+rbx]
0x18001dedf  add     bx, cx
0x18001dee2  movzx   ecx, bx
0x18001dee5  mov     ebx, r13d
0x18001dee8  mov     [rdi], ax
0x18001deeb  mov     rax, [rdi+8]
0x18001deef  shr     rcx, 1
0x18001def2  mov     [rax+rcx*2], r13w
0x18001def7  mov     rax, [rbp+57h+var_58]
0x18001defb  mov     rax, [rax+20h]
0x18001deff  test    rax, rax
0x18001df02  jz      short loc_18001DF11
0x18001df04  test    dword ptr [rax+8], 1000h
0x18001df0b  jnz     loc_18001E3C4
0x18001df11  xor     al, al
0x18001df13  mov     rdx, rdi
0x18001df16  jmp     loc_18001E086
0x18001df1b  movzx   ecx, word ptr [r9]
0x18001df1f  xor     sil, sil
0x18001df22  cmp     ecx, 8
0x18001df25  jb      short loc_18001DF61
0x18001df27  mov     rdx, [r9+8]
0x18001df2b  mov     r8, 0FFFFFFDFFFDFFFDFh
0x18001df35  mov     rax, [rdx]
0x18001df38  and     rax, r8
0x18001df3b  mov     r8, 2D004900500041h
0x18001df45  cmp     rax, r8
0x18001df48  jz      loc_18001DFED
0x18001df4e  mov     r8, 2D005400580045h
0x18001df58  cmp     rax, r8
0x18001df5b  jz      loc_18001DFED
0x18001df61  movzx   r14d, word ptr [rbp+57h+Src]
0x18001df66  mov     ebx, r13d
0x18001df69  test    sil, sil
0x18001df6c  jz      loc_18001DD8E
0x18001df72  test    r14w, r14w
0x18001df76  jz      loc_18001E5BE
0x18001df7c  mov     rax, gs:60h
0x18001df85  mov     rcx, [rax+90h]
0x18001df8c  test    rcx, rcx
0x18001df8f  jnz     loc_18001E680
0x18001df95  cmp     [r15], r13b
0x18001df98  jz      loc_18001DDC2
0x18001df9e  mov     rax, gs:60h
0x18001dfa7  test    byte ptr [rax+378h], 4
0x18001dfae  jz      loc_18001DDC2
0x18001dfb4  call    RtlGetCurrentServiceSessionId
0x18001dfb9  test    eax, eax
0x18001dfbb  jz      short loc_18001DFD4
0x18001dfbd  mov     rax, gs:60h
0x18001dfc6  mov     r12, [rax+90h]
0x18001dfcd  add     r12, 22Bh
0x18001dfd4  test    byte ptr [r12], 20h
0x18001dfd9  mov     r15, qword ptr [rbp+57h+arg_0]
0x18001dfdd  jz      loc_18001DDC6
0x18001dfe3  mov     ecx, 14D1h
0x18001dfe8  jmp     loc_18001E760
0x18001dfed  lea     rax, [rdx+rcx]
0x18001dff1  mov     r8d, ecx
0x18001dff4  cmp     r8d, 1
0x18001dff8  jbe     short loc_18001E008
0x18001dffa  sub     rax, 2
0x18001dffe  add     r8d, 0FFFFFFFEh
0x18001e002  cmp     word ptr [rax], 2Dh ; '-'
0x18001e006  jnz     short loc_18001DFF4
0x18001e008  shr     r8w, 1
0x18001e00c  jz      loc_18001DF61
0x18001e012  mov     rcx, rbx
0x18001e015  call    ApiSetpSearchForApiSet
0x18001e01a  test    rax, rax
0x18001e01d  jz      loc_18001DF61
0x18001e023  test    r14, r14
0x18001e026  jz      short loc_18001E060
0x18001e028  cmp     dword ptr [rax+14h], 1
0x18001e02c  jbe     short loc_18001E060
0x18001e02e  movzx   r8d, word ptr [r14]
0x18001e032  mov     r9, rbx
0x18001e035  mov     rdx, [r14+8]
0x18001e039  mov     rcx, rax
0x18001e03c  shr     r8w, 1
0x18001e040  call    ApiSetpSearchForApiSetHost
0x18001e045  mov     r14, rax
0x18001e048  mov     eax, [r14+0Ch]
0x18001e04c  mov     sil, 1
0x18001e04f  movzx   r14d, word ptr [r14+10h]
0x18001e054  add     rax, rbx
0x18001e057  mov     [rbp+57h+Src+8], rax
0x18001e05b  jmp     loc_18001DF66
0x18001e060  cmp     [rax+14h], r13d
0x18001e064  jbe     loc_18001DF61
0x18001e06a  mov     r14d, [rax+10h]
0x18001e06e  add     r14, rbx
0x18001e071  jmp     short loc_18001E048
0x18001e073  mov     ebx, 0C0000481h
0x18001e078  xor     r14b, r14b
0x18001e07b  jmp     short loc_18001E0A0
0x18001e07d  test    ebx, ebx
0x18001e07f  js      short loc_18001E08E
0x18001e081  mov     al, 1
0x18001e083  mov     rdx, r15
0x18001e086  test    al, al
0x18001e088  jnz     loc_18001E261
0x18001e08e  xor     r14b, r14b
0x18001e091  jmp     short loc_18001E0A0
0x18001e093  xor     r14b, r14b
0x18001e096  cmp     esi, 0C0150008h
0x18001e09c  jz      short loc_18001E0A0
0x18001e09e  mov     ebx, esi
0x18001e0a0  mov     r10d, 0FFFEh
0x18001e0a6  mov     r15, [rsp+80h]
0x18001e0ae  mov     r12, [rsp+0B0h+arg_8]
0x18001e0b6  test    ebx, ebx
0x18001e0b8  js      loc_18001E1F6
0x18001e0be  mov     r9, qword ptr [rbp+57h+arg_0]
0x18001e0c2  mov     rsi, [rbp+57h+arg_18]
0x18001e0c6  cmp     word ptr [rdi], 0
0x18001e0ca  jnz     loc_18001E324
0x18001e0d0  mov     rdx, [r9+8]
0x18001e0d4  mov     r14, r9
0x18001e0d7  movzx   eax, word ptr [r9]
0x18001e0db  add     rax, rdx
0x18001e0de  xchg    ax, ax
0x18001e0e0  sub     rax, 2
0x18001e0e4  cmp     rax, rdx
0x18001e0e7  jb      short loc_18001E126
0x18001e0e9  movzx   ecx, word ptr [rax]
0x18001e0ec  cmp     cx, 5Ch ; '\'
0x18001e0f0  jz      short loc_18001E0F8
0x18001e0f2  cmp     cx, 2Fh ; '/'
0x18001e0f6  jnz     short loc_18001E0E0
0x18001e0f8  mov     rcx, r9
0x18001e0fb  call    RtlDetermineDosPathNameType_Ustr
0x18001e100  cmp     eax, 5
0x18001e103  jz      loc_18001E6A5
0x18001e109  mov     rdx, rdi
0x18001e10c  mov     rcx, r9
0x18001e10f  call    LdrpGetFullPath
0x18001e114  mov     ebx, eax
0x18001e116  test    eax, eax
0x18001e118  js      loc_18001E1F6
0x18001e11e  or      dword ptr [rsi], 600h
0x18001e124  jmp     short loc_18001E181
0x18001e126  or      dword ptr [rsi], 20h
0x18001e129  mov     ebx, r13d
0x18001e12c  movzx   edx, word ptr [r9]
0x18001e130  test    dx, dx
  ... truncated ...
```
