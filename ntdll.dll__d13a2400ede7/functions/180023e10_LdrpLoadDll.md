# LdrpLoadDll

- ea: `0x180023e10`
- end: `0x180024882`
- name: `LdrpLoadDll`
- size: `2674`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `8`
- callee_count: `20`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x18001b9b0`
- `0x1800bfe70`
- `0x1800c0088`
- `0x1800c0ca0`
- `0x1800c19c0`
- `0x1800fbd9c`
- `0x1801060b8`
- `0x180107a54`

## callees

- `0x18001bcb0`
- `0x18001d490`
- `0x18001eb80`
- `0x18001f154`
- `0x18001f8f0`
- `0x18001fae0`
- `0x180021fd0`
- `0x180023e10`
- `0x180024890`
- `0x180024990`
- `0x180024ea0`
- `0x180027f10`
- `0x180029a60`
- `0x180069af8`
- `0x18006f0d0`
- `0x18007a040`
- `0x180120694`
- `0x180162810`
- `0x180164280`
- `0x18016f030`

## string_xrefs

- `0x180024241`: `LdrpPreprocessDllName`
- `0x1800244d0`: `LdrpPreprocessDllName`
- `0x180024235`: `LdrpPreprocessDllName for DLL %wZ failed with status 0x%08lx\n`
- `0x1800244f1`: `DLL %wZ was redirected to %wZ by %s\n`

## pseudocode

```c
__int64 __fastcall LdrpLoadDll(unsigned __int16 *ArgList, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v6; // r12
  _DWORD *SharedData; // rcx
  __int64 v8; // rcx
  _WORD *v9; // rsi
  struct _PEB *v10; // rsi
  char v11; // r14
  _DWORD *ApiSetMap; // rbx
  _DWORD *v13; // rcx
  __int64 v14; // rcx
  __int64 *v15; // r9
  int v16; // eax
  char v17; // di
  int appended; // ebx
  _DWORD *v19; // rcx
  __int64 v20; // rcx
  _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rax
  char v22; // al
  char *v23; // rdx
  __int64 v24; // rcx
  _QWORD *v25; // rdx
  unsigned __int64 v26; // rax
  _DWORD *v27; // rcx
  __int64 v28; // rcx
  char *v29; // rcx
  int v30; // ecx
  __int64 v31; // r8
  char *v32; // r14
  unsigned __int64 v33; // rdx
  _WORD *v34; // rax
  int FullPath; // edi
  unsigned __int64 v36; // rdx
  __int16 *v37; // rax
  __int16 v38; // cx
  _DWORD *v39; // rcx
  _WORD *i; // rcx
  int v42; // edi
  __int64 FullPathName_Ustr; // rbx
  _WORD *v44; // rax
  unsigned int v45; // r8d
  __int64 v46; // rax
  __int64 v47; // rcx
  bool v48; // zf
  _WORD *Atom; // rsi
  unsigned int v50; // ebx
  char *v51; // rcx
  __int64 v52; // rax
  char *v53; // rcx
  char *v54; // rcx
  char v55; // [rsp+50h] [rbp-B8h]
  _BYTE v56[4]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v57; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v58[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v59; // [rsp+70h] [rbp-98h] BYREF
  __int64 v60; // [rsp+78h] [rbp-90h]
  __int64 v61; // [rsp+80h] [rbp-88h]
  __int128 v62; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int16 v63[4]; // [rsp+98h] [rbp-70h] BYREF
  void *Src; // [rsp+A0h] [rbp-68h]
  _WORD v65[128]; // [rsp+A8h] [rbp-60h] BYREF

  v61 = a2;
  v60 = a4;
  memset_thunk_772440563353939046(v63, 0, 0x110u);
  v57 = 0;
  v6 = 2147353476;
  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
    v8 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v8 = 2147353476;
  if ( *(_BYTE *)v8 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    v51 = (unsigned int)RtlGetCurrentServiceSessionId() ? (char *)NtCurrentPeb()->SharedData + 555 : (char *)2147353477;
    if ( (*v51 & 0x20) != 0 )
      LdrpLogEtwEvent(5288, 0, 0, 0, (__int64)ArgList, 0);
  }
  v9 = v65;
  Src = v65;
  *(_DWORD *)v63 = 0x1000000;
  v65[0] = 0;
  if ( (a3 & 0x800008) != 0 )
  {
    appended = 0;
    v11 = 0;
    goto LABEL_46;
  }
  v56[0] = 0;
  v62 = 0;
  v10 = NtCurrentPeb();
  v11 = 0;
  *(_OWORD *)v58 = 0;
  ApiSetMap = v10->ApiSetMap;
  v13 = v10->SharedData;
  if ( v13 && *v13 )
    v14 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v14 = 2147353476;
  if ( *(_BYTE *)v14 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    v53 = (unsigned int)RtlGetCurrentServiceSessionId() ? (char *)NtCurrentPeb()->SharedData + 555 : (char *)2147353477;
    if ( (*v53 & 0x20) != 0 )
      LdrpLogEtwEvent(5328, 0, 0, 0, (__int64)ArgList, 0);
  }
  if ( *(_BYTE *)ApiSetMap != 7 )
  {
    if ( *ApiSetMap != 6
      || ApiSetMap[4] <= 8u
      || *((_BYTE *)ApiSetMap + 28) != 7
      || (*((_BYTE *)ApiSetMap + 30) & 4) != 0 )
    {
      v24 = *ArgList;
      v17 = 0;
      if ( (unsigned int)v24 >= 8 )
      {
        v25 = (_QWORD *)*((_QWORD *)ArgList + 1);
        v26 = *v25 & 0xFFFFFFDFFFDFFFDFuLL;
        if ( v26 == 0x2D004900500041LL || v26 == 0x2D005400580045LL )
        {
          v44 = (_WORD *)((char *)v25 + v24);
          v45 = *ArgList;
          do
          {
            if ( v45 <= 1 )
              break;
            --v44;
            v45 -= 2;
          }
          while ( *v44 != 45 );
          if ( (unsigned __int16)v45 >> 1 )
          {
            v46 = ApiSetpSearchForApiSet(ApiSetMap);
            if ( v46 )
            {
              if ( *(_DWORD *)(v46 + 20) )
              {
                v47 = *(unsigned int *)(v46 + 16);
                v17 = 1;
                v58[1] = (__int64)ApiSetMap + *(unsigned int *)((char *)ApiSetMap + v47 + 12);
                WORD1(v58[0]) = *(_WORD *)((char *)ApiSetMap + v47 + 16);
                LOWORD(v58[0]) = WORD1(v58[0]);
              }
            }
          }
        }
      }
      appended = 0;
      goto LABEL_31;
    }
    LODWORD(ApiSetMap) = (_DWORD)ApiSetMap + 28;
  }
  v15 = v58;
  LOBYTE(v15) = 1;
  v16 = ApiSetpResolveHost(
          (_DWORD)ApiSetMap,
          *((_QWORD *)ArgList + 1),
          *ArgList >> 1,
          (_DWORD)v15,
          0,
          (__int64)v56,
          (__int64)v58);
  v17 = v56[0];
  appended = v16;
  if ( v16 < 0 )
  {
LABEL_17:
    v19 = NtCurrentPeb()->SharedData;
    if ( v19 && *v19 )
      v20 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v20 = 2147353476;
    if ( *(_BYTE *)v20 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v54 = (unsigned int)RtlGetCurrentServiceSessionId()
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v54 & 0x20) != 0 )
      {
        v30 = 5331;
        goto LABEL_148;
      }
    }
    goto LABEL_21;
  }
LABEL_31:
  if ( !v17 )
    goto LABEL_17;
  if ( !LOWORD(v58[0]) )
  {
    LdrpLogDllState(0, ArgList, 5330);
    goto LABEL_21;
  }
  v27 = NtCurrentPeb()->SharedData;
  if ( v27 && *v27 )
    v28 = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    v28 = 2147353476;
  if ( *(_BYTE *)v28 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    v29 = (unsigned int)RtlGetCurrentServiceSessionId() ? (char *)NtCurrentPeb()->SharedData + 555 : (char *)2147353477;
    if ( (*v29 & 0x20) != 0 )
    {
      v30 = 5329;
LABEL_148:
      LdrpLogEtwEvent(v30, 0, 0, 0, (__int64)ArgList, 0);
    }
  }
LABEL_21:
  if ( v17 )
  {
    if ( !LOWORD(v58[0]) )
    {
      appended = -1073740671;
      goto LABEL_44;
    }
    appended = LdrpBuildSystem32FileName(v63, v58);
    if ( appended < 0 )
      goto LABEL_44;
    ProcessParameters = v10->ProcessParameters;
    if ( ProcessParameters && (ProcessParameters->Flags & 0x1000) != 0 )
    {
      v22 = 1;
      v23 = (char *)v63;
    }
    else
    {
      v22 = 0;
      v23 = (char *)v63;
    }
  }
  else
  {
    if ( appended < 0 )
    {
LABEL_124:
      FullPath = appended;
LABEL_65:
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrutil.c",
        2862,
        (int)"LdrpPreprocessDllName",
        0,
        "LdrpPreprocessDllName for DLL %wZ failed with status 0x%08lx\n",
        (char)ArgList);
      v57 = FullPath;
      goto LABEL_66;
    }
    v22 = 1;
    LODWORD(v23) = (_DWORD)ArgList;
  }
  if ( v22 && !LdrpIsSecureProcess )
  {
    v42 = RtlDosApplyFileIsolationRedirection_Ustr(1, (_DWORD)v23, (unsigned int)L"\b\n", 0, (__int64)&v62, 0, 0, 0, 0);
    if ( v42 < 0 )
    {
      if ( v42 == -1072365560 )
        goto LABEL_44;
    }
    else
    {
      v11 = 1;
      v58[0] = 0;
      v56[0] = 0;
      v59 = 0;
      while ( 1 )
      {
        FullPathName_Ustr = (unsigned int)RtlGetFullPathName_Ustr(&v62, v63[1], Src, v58, v56, &v59);
        if ( v56[0]
          || (unsigned int)(FullPathName_Ustr - 1) > 0xFFFD
          || (_DWORD)v59 == 5 && (HIDWORD(v59) & LdrpIllegalCWDDevices) != 0 )
        {
          break;
        }
        if ( (unsigned int)FullPathName_Ustr < v63[1] )
        {
          v63[0] = FullPathName_Ustr;
          break;
        }
        Atom = (_WORD *)RtlpAllocateAtom(FullPathName_Ustr);
        if ( !Atom )
          break;
        if ( v65 != Src )
          RtlpSysVolFree(Src);
        Src = Atom;
        v65[0] = 0;
        v63[0] = 0;
        v63[1] = FullPathName_Ustr;
        *Atom = 0;
      }
      if ( *((_QWORD *)&v62 + 1) )
      {
        RtlpSysVolFree(*((_QWORD *)&v62 + 1));
        appended = v42;
        goto LABEL_44;
      }
    }
    appended = v42;
  }
LABEL_44:
  if ( appended < 0 )
    goto LABEL_124;
  v9 = Src;
LABEL_46:
  if ( v63[0] )
  {
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      2801,
      (int)"LdrpPreprocessDllName",
      2,
      "DLL %wZ was redirected to %wZ by %s\n",
      (char)ArgList);
    a3 |= 0x200u;
    v48 = v11 == 0;
    v32 = (char *)v63;
    if ( !v48 )
      a3 |= 4u;
    goto LABEL_57;
  }
  v31 = *ArgList;
  v32 = (char *)ArgList;
  v33 = *((_QWORD *)ArgList + 1);
  v34 = (_WORD *)(v33 + v31);
  do
  {
    if ( (unsigned __int64)--v34 < v33 )
    {
      a3 |= 0x20u;
      appended = 0;
      if ( !(_WORD)v31 )
        goto LABEL_58;
      if ( (int)v31 + 2 <= (unsigned int)v63[1] )
        goto LABEL_56;
      if ( (unsigned int)(v31 + 2) > 0xFFFE )
      {
        appended = -1073741562;
LABEL_58:
        FullPath = appended;
        if ( appended >= 0 )
          goto LABEL_59;
        goto LABEL_65;
      }
      v50 = (v31 + 65) & 0xFFFFFFC0;
      if ( v50 > 0xFFFE )
        v50 = 65534;
      if ( v9 == v65 )
      {
        v9 = (_WORD *)RtlpAllocateAtom(v50);
        if ( !v9 )
          goto LABEL_117;
        if ( v63[0] )
          memmove(v9, Src, v63[0]);
      }
      else
      {
        v9 = (_WORD *)NtdllpReallocateStringRoutine(v50, v9, v31, 65534);
        if ( !v9 )
        {
LABEL_117:
          appended = -1073741801;
LABEL_57:
          v9 = Src;
          goto LABEL_58;
        }
      }
      Src = v9;
      v63[1] = v50;
LABEL_56:
      appended = 0;
      memmove((char *)v9 + v63[0], *((const void **)ArgList + 1), *ArgList);
      v63[0] += *ArgList;
      *((_WORD *)Src + ((unsigned __int64)v63[0] >> 1)) = 0;
      goto LABEL_57;
    }
  }
  while ( *v34 != 92 && *v34 != 47 );
  if ( (unsigned int)RtlDetermineDosPathNameType_Ustr(ArgList, v33, v31, 65534) == 5 )
  {
    appended = LdrpAppendUnicodeStringToFilenameBuffer(v63, ArgList);
    goto LABEL_57;
  }
  FullPath = LdrpGetFullPath(ArgList, v63);
  if ( FullPath < 0 )
    goto LABEL_65;
  v9 = Src;
  a3 |= 0x600u;
LABEL_59:
  v36 = *((_QWORD *)v32 + 1);
  v37 = (__int16 *)(v36 + *(unsigned __int16 *)v32);
  do
  {
    if ( (unsigned __int64)--v37 < v36 )
      break;
    v38 = *v37;
    if ( *v37 == 46 )
    {
      for ( i = (_WORD *)((char *)v9 + v63[0] - 2); i >= v9; --i )
      {
        if ( *i != 46 )
          break;
        v63[0] -= 2;
      }
      i[1] = 0;
      goto LABEL_75;
    }
  }
  while ( v38 != 47 && v38 != 92 );
  FullPath = LdrpAppendUnicodeStringToFilenameBuffer(v63, L"\b\n");
  if ( FullPath < 0 )
    goto LABEL_65;
LABEL_75:
  v57 = FullPath;
  LdrpLoadDllInternal((__int64)v63, v61, a3, 4, 0, 0, (__int64 *)v60, (int *)&v57, 0, v55);
LABEL_66:
  if ( v65 != Src )
    RtlpSysVolFree(Src);
  *(_DWORD *)v63 = 0x1000000;
  Src = v65;
  v65[0] = 0;
  v39 = NtCurrentPeb()->SharedData;
  if ( v39 && *v39 )
    v6 = (__int64)NtCurrentPeb()->SharedData + 554;
  if ( *(_BYTE *)v6 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId() )
      v52 = (__int64)NtCurrentPeb()->SharedData + 555;
    else
      v52 = 2147353477;
    if ( (*(_BYTE *)v52 & 0x20) != 0 )
      LdrpLogEtwEvent(5289, 0, 0, 0, (__int64)ArgList, 0);
  }
  return v57;
}

```

## disassembly

```asm
0x180023e10  mov     r11, rsp
0x180023e13  push    rbp
0x180023e14  push    rbx
0x180023e15  push    r15
0x180023e17  lea     rbp, [r11-0F8h]
0x180023e1e  sub     rsp, 1E0h
0x180023e25  mov     rax, cs:__security_cookie
0x180023e2c  xor     rax, rsp
0x180023e2f  mov     [rbp+0F0h+var_50], rax
0x180023e36  mov     [r11-20h], rsi
0x180023e3a  mov     r15, rcx
0x180023e3d  mov     [r11-30h], r12
0x180023e41  lea     rcx, [rbp+0F0h+var_160]; void *
0x180023e45  mov     [r11-38h], r13
0x180023e49  mov     r13d, r8d
0x180023e4c  mov     [rsp+1F0h+var_178], rdx
0x180023e51  mov     r8d, 110h; Size
0x180023e57  xor     edx, edx; Val
0x180023e59  mov     [rsp+1F0h+var_180], r9
0x180023e5e  call    memset$thunk$772440563353939046
0x180023e63  mov     dword ptr [rsp+1F0h+var_1A0+4], 0
0x180023e6b  mov     r12d, 7FFE0384h
0x180023e71  mov     rax, gs:60h
0x180023e7a  mov     rcx, [rax+90h]
0x180023e81  test    rcx, rcx
0x180023e84  jnz     loc_18002454C
0x180023e8a  mov     rcx, r12
0x180023e8d  cmp     byte ptr [rcx], 0
0x180023e90  jz      short loc_180023EA8
0x180023e92  mov     rax, gs:60h
0x180023e9b  test    byte ptr [rax+378h], 4
0x180023ea2  jnz     loc_1800246E3
0x180023ea8  xor     eax, eax
0x180023eaa  mov     [rsp+1F0h+var_20], rdi
0x180023eb2  mov     [rsp+1F0h+var_38], r14
0x180023eba  lea     rsi, [rbp+0F0h+var_150]
0x180023ebe  mov     [rbp+0F0h+Src], rsi
0x180023ec2  mov     dword ptr [rbp+0F0h+var_160], 1000000h
0x180023ec9  mov     [rbp+0F0h+var_150], ax
0x180023ecd  test    r13d, 800008h
0x180023ed4  jnz     loc_180024871
0x180023eda  xorps   xmm1, xmm1
0x180023edd  mov     byte ptr [rsp+1F0h+var_1A0], al
0x180023ee1  movups  [rbp+0F0h+var_170], xmm1
0x180023ee5  mov     rsi, gs:60h
0x180023eee  xor     r14b, r14b
0x180023ef1  mov     rax, gs:60h
0x180023efa  xorps   xmm0, xmm0
0x180023efd  movups  xmmword ptr [rsp+1F0h+var_1A0+8], xmm0
0x180023f02  mov     rbx, [rsi+68h]
0x180023f06  mov     rcx, [rax+90h]
0x180023f0d  test    rcx, rcx
0x180023f10  jnz     loc_180024596
0x180023f16  mov     rcx, r12
0x180023f19  cmp     [rcx], r14b
0x180023f1c  jz      short loc_180023F34
0x180023f1e  mov     rax, gs:60h
0x180023f27  test    byte ptr [rax+378h], 4
0x180023f2e  jnz     loc_180024782
0x180023f34  cmp     byte ptr [rbx], 7
0x180023f37  jz      short loc_180023F64
0x180023f39  cmp     dword ptr [rbx], 6
0x180023f3c  jnz     loc_180024032
0x180023f42  cmp     dword ptr [rbx+10h], 8
0x180023f46  jbe     loc_180024032
0x180023f4c  cmp     byte ptr [rbx+1Ch], 7
0x180023f50  jnz     loc_180024032
0x180023f56  test    byte ptr [rbx+1Eh], 4
0x180023f5a  jnz     loc_180024032
0x180023f60  add     rbx, 1Ch
0x180023f64  movzx   r8d, word ptr [r15]
0x180023f68  lea     r9, [rsp+1F0h+var_1A0+8]
0x180023f6d  mov     [rsp+1F0h+var_1C0], r9
0x180023f72  lea     rcx, [rsp+1F0h+var_1A0]
0x180023f77  mov     qword ptr [rsp+1F0h+ArgList], rcx
0x180023f7c  xor     eax, eax
0x180023f7e  mov     edx, 8
0x180023f83  shr     r8w, 1
0x180023f87  mov     r10, r15
0x180023f8a  mov     [rsp+1F0h+Format], rax
0x180023f8f  mov     r9b, 1
0x180023f92  mov     rcx, rbx
0x180023f95  mov     rdx, [rdx+r15]
0x180023f99  call    ApiSetpResolveHost
0x180023f9e  movzx   edi, byte ptr [rsp+1F0h+var_1A0]
0x180023fa3  mov     ebx, eax
0x180023fa5  test    eax, eax
0x180023fa7  jns     loc_18002407A
0x180023fad  mov     rax, gs:60h
0x180023fb6  mov     rcx, [rax+90h]
0x180023fbd  test    rcx, rcx
0x180023fc0  jnz     loc_180024638
0x180023fc6  mov     rcx, r12
0x180023fc9  cmp     [rcx], r14b
0x180023fcc  jz      short loc_180023FE4
0x180023fce  mov     rax, gs:60h
0x180023fd7  test    byte ptr [rax+378h], 4
0x180023fde  jnz     loc_1800247F4
0x180023fe4  test    dil, dil
0x180023fe7  jz      loc_180024101
0x180023fed  cmp     word ptr [rsp+1F0h+var_1A0+8], 0
0x180023ff3  jz      loc_180024522
0x180023ff9  lea     rdx, [rsp+1F0h+var_1A0+8]
0x180023ffe  lea     rcx, [rbp+0F0h+var_160]
0x180024002  call    LdrpBuildSystem32FileName
0x180024007  mov     ebx, eax
0x180024009  test    eax, eax
0x18002400b  js      loc_180024116
0x180024011  mov     rax, [rsi+20h]
0x180024015  test    rax, rax
0x180024018  jz      short loc_180024027
0x18002401a  test    dword ptr [rax+8], 1000h
0x180024021  jnz     loc_180024541
0x180024027  xor     al, al
0x180024029  lea     rdx, [rbp+0F0h+var_160]
0x18002402d  jmp     loc_18002410E
0x180024032  movzx   ecx, word ptr [r15]
0x180024036  xor     dil, dil
0x180024039  cmp     ecx, 8
0x18002403c  jb      short loc_180024078
0x18002403e  mov     rdx, [r15+8]
0x180024042  mov     r8, 0FFFFFFDFFFDFFFDFh
0x18002404c  mov     rax, [rdx]
0x18002404f  and     rax, r8
0x180024052  mov     r8, 2D004900500041h
0x18002405c  cmp     rax, r8
0x18002405f  jz      loc_18002444F
0x180024065  mov     r8, 2D005400580045h
0x18002406f  cmp     rax, r8
0x180024072  jz      loc_18002444F
0x180024078  xor     ebx, ebx
0x18002407a  test    dil, dil
0x18002407d  jz      loc_180023FAD
0x180024083  cmp     word ptr [rsp+1F0h+var_1A0+8], 0
0x180024089  jz      loc_180024696
0x18002408f  mov     rax, gs:60h
0x180024098  mov     rcx, [rax+90h]
0x18002409f  test    rcx, rcx
0x1800240a2  jnz     loc_1800246AB
0x1800240a8  mov     rcx, r12
0x1800240ab  cmp     [rcx], r14b
0x1800240ae  jz      loc_180023FE4
0x1800240b4  mov     rax, gs:60h
0x1800240bd  test    byte ptr [rax+378h], 4
0x1800240c4  jz      loc_180023FE4
0x1800240ca  call    RtlGetCurrentServiceSessionId
0x1800240cf  test    eax, eax
0x1800240d1  jz      loc_180024867
0x1800240d7  mov     rax, gs:60h
0x1800240e0  mov     rcx, [rax+90h]
0x1800240e7  add     rcx, 22Bh
0x1800240ee  test    byte ptr [rcx], 20h
0x1800240f1  jz      loc_180023FE4
0x1800240f7  mov     ecx, 14D1h
0x1800240fc  jmp     loc_180024822
0x180024101  test    ebx, ebx
0x180024103  js      loc_18002468F
0x180024109  mov     al, 1
0x18002410b  mov     rdx, r15
0x18002410e  test    al, al
0x180024110  jnz     loc_180024372
0x180024116  test    ebx, ebx
0x180024118  js      loc_18002468F
0x18002411e  mov     rsi, [rbp+0F0h+Src]
0x180024122  cmp     [rbp+0F0h+var_160], 0
0x180024127  mov     r9d, 0FFFEh
0x18002412d  jnz     loc_1800244B5
0x180024133  movzx   r8d, word ptr [r15]
0x180024137  mov     r14, r15
0x18002413a  mov     rdx, [r15+8]
0x18002413e  lea     rax, [rdx+r8]
0x180024142  sub     rax, 2
0x180024146  cmp     rax, rdx
0x180024149  jb      short loc_180024190
0x18002414b  movzx   ecx, word ptr [rax]
0x18002414e  cmp     cx, 5Ch ; '\'
0x180024152  jz      short loc_18002415A
0x180024154  cmp     cx, 2Fh ; '/'
0x180024158  jnz     short loc_180024142
0x18002415a  mov     rcx, r15
0x18002415d  call    RtlDetermineDosPathNameType_Ustr
0x180024162  cmp     eax, 5
0x180024165  jz      loc_1800246D0
0x18002416b  lea     rdx, [rbp+0F0h+var_160]
0x18002416f  mov     rcx, r15
0x180024172  call    LdrpGetFullPath
0x180024177  mov     ebx, eax
0x180024179  mov     edi, eax
0x18002417b  test    eax, eax
0x18002417d  js      loc_180024231
0x180024183  mov     rsi, [rbp+0F0h+Src]
0x180024187  or      r13d, 600h
0x18002418e  jmp     short loc_1800241E8
0x180024190  or      r13d, 20h
0x180024194  xor     ebx, ebx
0x180024196  test    r8w, r8w
0x18002419a  jz      short loc_1800241E2
0x18002419c  movzx   eax, [rbp+0F0h+var_160+2]
0x1800241a0  lea     ecx, [r8+2]
0x1800241a4  cmp     ecx, eax
0x1800241a6  ja      loc_1800245FD
0x1800241ac  movzx   ecx, [rbp+0F0h+var_160]
0x1800241b0  xor     ebx, ebx
0x1800241b2  movzx   r8d, word ptr [r15]; Size
0x1800241b6  add     rcx, rsi; void *
0x1800241b9  mov     rdx, [r15+8]; Src
0x1800241bd  call    memmove
0x1800241c2  movzx   eax, [rbp+0F0h+var_160]
0x1800241c6  add     ax, [r15]
0x1800241ca  movzx   edx, ax
0x1800241cd  mov     rax, [rbp+0F0h+Src]
0x1800241d1  mov     [rbp+0F0h+var_160], dx
0x1800241d5  shr     rdx, 1
0x1800241d8  xor     ecx, ecx
0x1800241da  mov     [rax+rdx*2], cx
0x1800241de  mov     rsi, [rbp+0F0h+Src]
0x1800241e2  mov     edi, ebx
0x1800241e4  test    ebx, ebx
0x1800241e6  js      short loc_180024231
0x1800241e8  mov     rdx, [r14+8]
0x1800241ec  movzx   eax, word ptr [r14]
0x1800241f0  add     rax, rdx
0x1800241f3  sub     rax, 2
0x1800241f7  cmp     rax, rdx
0x1800241fa  jb      short loc_180024215
0x1800241fc  movzx   ecx, word ptr [rax]
0x1800241ff  cmp     cx, 2Eh ; '.'
0x180024203  jz      loc_18002430A
0x180024209  cmp     cx, 2Fh ; '/'
0x18002420d  jz      short loc_180024215
0x18002420f  cmp     cx, 5Ch ; '\'
0x180024213  jnz     short loc_1800241F3
0x180024215  lea     rdx, LdrpDefaultExtension; "\b\n"
0x18002421c  lea     rcx, [rbp+0F0h+var_160]
0x180024220  call    LdrpAppendUnicodeStringToFilenameBuffer
0x180024225  mov     ebx, eax
0x180024227  mov     edi, eax
0x180024229  test    eax, eax
0x18002422b  jns     loc_18002487B
0x180024231  mov     dword ptr [rsp+1F0h+var_1C0], ebx
0x180024235  lea     rax, aLdrppreprocess_0; "LdrpPreprocessDllName for DLL %wZ faile"...
0x18002423c  mov     qword ptr [rsp+1F0h+ArgList], r15; ArgList
0x180024241  lea     r8, aLdrppreprocess; "LdrpPreprocessDllName"
0x180024248  xor     r9d, r9d; int
0x18002424b  mov     [rsp+1F0h+Format], rax; Format
0x180024250  mov     edx, 0B2Eh; int
0x180024255  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002425c  call    LdrpLogInternal
0x180024261  xor     ebx, ebx
0x180024263  mov     dword ptr [rsp+1F0h+var_1A0+4], edi
0x180024267  mov     rcx, [rbp+0F0h+Src]
0x18002426b  lea     rax, [rbp+0F0h+var_150]
0x18002426f  mov     r14, [rsp+1F0h+var_38]
0x180024277  mov     r13, [rsp+1F0h+var_30]
0x18002427f  mov     rdi, [rsp+1F0h+var_20]
0x180024287  mov     rsi, [rsp+1D8h]
0x18002428f  cmp     rax, rcx
0x180024292  jz      short loc_180024299
0x180024294  call    RtlpSysVolFree
0x180024299  lea     rax, [rbp+0F0h+var_150]
0x18002429d  mov     dword ptr [rbp+0F0h+var_160], 1000000h
0x1800242a4  mov     [rbp+0F0h+Src], rax
0x1800242a8  mov     [rbp+0F0h+var_150], bx
0x1800242ac  mov     rax, gs:60h
0x1800242b5  mov     rcx, [rax+90h]
0x1800242bc  test    rcx, rcx
0x1800242bf  jnz     loc_180024571
0x1800242c5  cmp     byte ptr [r12], 0
0x1800242ca  mov     r12, [rsp+1F0h+var_28]
0x1800242d2  jz      short loc_1800242EA
0x1800242d4  mov     rax, gs:60h
0x1800242dd  test    byte ptr [rax+378h], 4
0x1800242e4  jnz     loc_180024735
0x1800242ea  mov     eax, dword ptr [rsp+1F0h+var_1A0+4]
0x1800242ee  mov     rcx, [rbp+0F0h+var_50]
0x1800242f5  xor     rcx, rsp; StackCookie
0x1800242f8  call    __security_check_cookie
0x1800242fd  add     rsp, 1E0h
0x180024304  pop     r15
0x180024306  pop     rbx
0x180024307  pop     rbp
0x180024308  retn
0x18002430a  movzx   ecx, [rbp+0F0h+var_160]
0x18002430e  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180024312  add     rcx, rsi
0x180024315  cmp     rcx, rsi
0x180024318  jb      short loc_180024329
0x18002431a  mov     eax, 0FFFEh
0x18002431f  cmp     word ptr [rcx], 2Eh ; '.'
0x180024323  jz      loc_1800247D4
0x180024329  xor     ebx, ebx
0x18002432b  mov     [rcx+2], bx
0x18002432f  mov     rdx, [rsp+1F0h+var_178]
0x180024334  lea     rax, [rsp+1F0h+var_1A0+4]
0x180024339  mov     [rsp+40h], rbx; __int64
0x18002433e  lea     rcx, [rbp+0F0h+var_160]; ArgList
0x180024342  mov     [rsp+1F0h+var_1B8], rax; __int64
0x180024347  mov     r9d, 4
0x18002434d  mov     rax, [rsp+1F0h+var_180]
0x180024352  mov     r8d, r13d
  ... truncated ...
```
