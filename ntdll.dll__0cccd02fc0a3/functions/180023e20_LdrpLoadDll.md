# LdrpLoadDll

- ea: `0x180023e20`
- end: `0x180024892`
- name: `LdrpLoadDll`
- size: `2674`
- prototype: `__int64 __fastcall(char ArgList)`
- caller_count: `8`
- callee_count: `20`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x18001b9b0`
- `0x1800bbb90`
- `0x1800bbda8`
- `0x1800bc9c0`
- `0x1800bd6e0`
- `0x1800fb05c`
- `0x180105288`
- `0x180106c24`

## callees

- `0x18001bcb0`
- `0x18001d490`
- `0x18001eb80`
- `0x18001f154`
- `0x18001f900`
- `0x18001faf0`
- `0x180021fe0`
- `0x180023e20`
- `0x1800248a0`
- `0x1800249a0`
- `0x180024eb0`
- `0x180028020`
- `0x180029b70`
- `0x18004cef8`
- `0x1800526f0`
- `0x18005d660`
- `0x18011fba4`
- `0x180162000`
- `0x180163a80`
- `0x18016f030`

## string_xrefs

- `0x180024251`: `LdrpPreprocessDllName`
- `0x1800244e0`: `LdrpPreprocessDllName`
- `0x180024245`: `LdrpPreprocessDllName for DLL %wZ failed with status 0x%08lx\n`
- `0x180024501`: `DLL %wZ was redirected to %wZ by %s\n`

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
0x180023e20  mov     r11, rsp
0x180023e23  push    rbp
0x180023e24  push    rbx
0x180023e25  push    r15
0x180023e27  lea     rbp, [r11-0F8h]
0x180023e2e  sub     rsp, 1E0h
0x180023e35  mov     rax, cs:__security_cookie
0x180023e3c  xor     rax, rsp
0x180023e3f  mov     [rbp+0F0h+var_50], rax
0x180023e46  mov     [r11-20h], rsi
0x180023e4a  mov     r15, rcx
0x180023e4d  mov     [r11-30h], r12
0x180023e51  lea     rcx, [rbp+0F0h+var_160]; void *
0x180023e55  mov     [r11-38h], r13
0x180023e59  mov     r13d, r8d
0x180023e5c  mov     [rsp+1F0h+var_178], rdx
0x180023e61  mov     r8d, 110h; Size
0x180023e67  xor     edx, edx; Val
0x180023e69  mov     [rsp+1F0h+var_180], r9
0x180023e6e  call    memset$thunk$772440563353939046
0x180023e73  mov     dword ptr [rsp+1F0h+var_1A0+4], 0
0x180023e7b  mov     r12d, 7FFE0384h
0x180023e81  mov     rax, gs:60h
0x180023e8a  mov     rcx, [rax+90h]
0x180023e91  test    rcx, rcx
0x180023e94  jnz     loc_18002455C
0x180023e9a  mov     rcx, r12
0x180023e9d  cmp     byte ptr [rcx], 0
0x180023ea0  jz      short loc_180023EB8
0x180023ea2  mov     rax, gs:60h
0x180023eab  test    byte ptr [rax+378h], 4
0x180023eb2  jnz     loc_1800246F3
0x180023eb8  xor     eax, eax
0x180023eba  mov     [rsp+1F0h+var_20], rdi
0x180023ec2  mov     [rsp+1F0h+var_38], r14
0x180023eca  lea     rsi, [rbp+0F0h+var_150]
0x180023ece  mov     [rbp+0F0h+Src], rsi
0x180023ed2  mov     dword ptr [rbp+0F0h+var_160], 1000000h
0x180023ed9  mov     [rbp+0F0h+var_150], ax
0x180023edd  test    r13d, 800008h
0x180023ee4  jnz     loc_180024881
0x180023eea  xorps   xmm1, xmm1
0x180023eed  mov     byte ptr [rsp+1F0h+var_1A0], al
0x180023ef1  movups  [rbp+0F0h+var_170], xmm1
0x180023ef5  mov     rsi, gs:60h
0x180023efe  xor     r14b, r14b
0x180023f01  mov     rax, gs:60h
0x180023f0a  xorps   xmm0, xmm0
0x180023f0d  movups  xmmword ptr [rsp+1F0h+var_1A0+8], xmm0
0x180023f12  mov     rbx, [rsi+68h]
0x180023f16  mov     rcx, [rax+90h]
0x180023f1d  test    rcx, rcx
0x180023f20  jnz     loc_1800245A6
0x180023f26  mov     rcx, r12
0x180023f29  cmp     [rcx], r14b
0x180023f2c  jz      short loc_180023F44
0x180023f2e  mov     rax, gs:60h
0x180023f37  test    byte ptr [rax+378h], 4
0x180023f3e  jnz     loc_180024792
0x180023f44  cmp     byte ptr [rbx], 7
0x180023f47  jz      short loc_180023F74
0x180023f49  cmp     dword ptr [rbx], 6
0x180023f4c  jnz     loc_180024042
0x180023f52  cmp     dword ptr [rbx+10h], 8
0x180023f56  jbe     loc_180024042
0x180023f5c  cmp     byte ptr [rbx+1Ch], 7
0x180023f60  jnz     loc_180024042
0x180023f66  test    byte ptr [rbx+1Eh], 4
0x180023f6a  jnz     loc_180024042
0x180023f70  add     rbx, 1Ch
0x180023f74  movzx   r8d, word ptr [r15]
0x180023f78  lea     r9, [rsp+1F0h+var_1A0+8]
0x180023f7d  mov     [rsp+1F0h+var_1C0], r9
0x180023f82  lea     rcx, [rsp+1F0h+var_1A0]
0x180023f87  mov     qword ptr [rsp+1F0h+ArgList], rcx
0x180023f8c  xor     eax, eax
0x180023f8e  mov     edx, 8
0x180023f93  shr     r8w, 1
0x180023f97  mov     r10, r15
0x180023f9a  mov     [rsp+1F0h+Format], rax
0x180023f9f  mov     r9b, 1
0x180023fa2  mov     rcx, rbx
0x180023fa5  mov     rdx, [rdx+r15]
0x180023fa9  call    ApiSetpResolveHost
0x180023fae  movzx   edi, byte ptr [rsp+1F0h+var_1A0]
0x180023fb3  mov     ebx, eax
0x180023fb5  test    eax, eax
0x180023fb7  jns     loc_18002408A
0x180023fbd  mov     rax, gs:60h
0x180023fc6  mov     rcx, [rax+90h]
0x180023fcd  test    rcx, rcx
0x180023fd0  jnz     loc_180024648
0x180023fd6  mov     rcx, r12
0x180023fd9  cmp     [rcx], r14b
0x180023fdc  jz      short loc_180023FF4
0x180023fde  mov     rax, gs:60h
0x180023fe7  test    byte ptr [rax+378h], 4
0x180023fee  jnz     loc_180024804
0x180023ff4  test    dil, dil
0x180023ff7  jz      loc_180024111
0x180023ffd  cmp     word ptr [rsp+1F0h+var_1A0+8], 0
0x180024003  jz      loc_180024532
0x180024009  lea     rdx, [rsp+1F0h+var_1A0+8]
0x18002400e  lea     rcx, [rbp+0F0h+var_160]
0x180024012  call    LdrpBuildSystem32FileName
0x180024017  mov     ebx, eax
0x180024019  test    eax, eax
0x18002401b  js      loc_180024126
0x180024021  mov     rax, [rsi+20h]
0x180024025  test    rax, rax
0x180024028  jz      short loc_180024037
0x18002402a  test    dword ptr [rax+8], 1000h
0x180024031  jnz     loc_180024551
0x180024037  xor     al, al
0x180024039  lea     rdx, [rbp+0F0h+var_160]
0x18002403d  jmp     loc_18002411E
0x180024042  movzx   ecx, word ptr [r15]
0x180024046  xor     dil, dil
0x180024049  cmp     ecx, 8
0x18002404c  jb      short loc_180024088
0x18002404e  mov     rdx, [r15+8]
0x180024052  mov     r8, 0FFFFFFDFFFDFFFDFh
0x18002405c  mov     rax, [rdx]
0x18002405f  and     rax, r8
0x180024062  mov     r8, 2D004900500041h
0x18002406c  cmp     rax, r8
0x18002406f  jz      loc_18002445F
0x180024075  mov     r8, 2D005400580045h
0x18002407f  cmp     rax, r8
0x180024082  jz      loc_18002445F
0x180024088  xor     ebx, ebx
0x18002408a  test    dil, dil
0x18002408d  jz      loc_180023FBD
0x180024093  cmp     word ptr [rsp+1F0h+var_1A0+8], 0
0x180024099  jz      loc_1800246A6
0x18002409f  mov     rax, gs:60h
0x1800240a8  mov     rcx, [rax+90h]
0x1800240af  test    rcx, rcx
0x1800240b2  jnz     loc_1800246BB
0x1800240b8  mov     rcx, r12
0x1800240bb  cmp     [rcx], r14b
0x1800240be  jz      loc_180023FF4
0x1800240c4  mov     rax, gs:60h
0x1800240cd  test    byte ptr [rax+378h], 4
0x1800240d4  jz      loc_180023FF4
0x1800240da  call    RtlGetCurrentServiceSessionId
0x1800240df  test    eax, eax
0x1800240e1  jz      loc_180024877
0x1800240e7  mov     rax, gs:60h
0x1800240f0  mov     rcx, [rax+90h]
0x1800240f7  add     rcx, 22Bh
0x1800240fe  test    byte ptr [rcx], 20h
0x180024101  jz      loc_180023FF4
0x180024107  mov     ecx, 14D1h
0x18002410c  jmp     loc_180024832
0x180024111  test    ebx, ebx
0x180024113  js      loc_18002469F
0x180024119  mov     al, 1
0x18002411b  mov     rdx, r15
0x18002411e  test    al, al
0x180024120  jnz     loc_180024382
0x180024126  test    ebx, ebx
0x180024128  js      loc_18002469F
0x18002412e  mov     rsi, [rbp+0F0h+Src]
0x180024132  cmp     [rbp+0F0h+var_160], 0
0x180024137  mov     r9d, 0FFFEh
0x18002413d  jnz     loc_1800244C5
0x180024143  movzx   r8d, word ptr [r15]
0x180024147  mov     r14, r15
0x18002414a  mov     rdx, [r15+8]
0x18002414e  lea     rax, [rdx+r8]
0x180024152  sub     rax, 2
0x180024156  cmp     rax, rdx
0x180024159  jb      short loc_1800241A0
0x18002415b  movzx   ecx, word ptr [rax]
0x18002415e  cmp     cx, 5Ch ; '\'
0x180024162  jz      short loc_18002416A
0x180024164  cmp     cx, 2Fh ; '/'
0x180024168  jnz     short loc_180024152
0x18002416a  mov     rcx, r15
0x18002416d  call    RtlDetermineDosPathNameType_Ustr
0x180024172  cmp     eax, 5
0x180024175  jz      loc_1800246E0
0x18002417b  lea     rdx, [rbp+0F0h+var_160]
0x18002417f  mov     rcx, r15
0x180024182  call    LdrpGetFullPath
0x180024187  mov     ebx, eax
0x180024189  mov     edi, eax
0x18002418b  test    eax, eax
0x18002418d  js      loc_180024241
0x180024193  mov     rsi, [rbp+0F0h+Src]
0x180024197  or      r13d, 600h
0x18002419e  jmp     short loc_1800241F8
0x1800241a0  or      r13d, 20h
0x1800241a4  xor     ebx, ebx
0x1800241a6  test    r8w, r8w
0x1800241aa  jz      short loc_1800241F2
0x1800241ac  movzx   eax, [rbp+0F0h+var_160+2]
0x1800241b0  lea     ecx, [r8+2]
0x1800241b4  cmp     ecx, eax
0x1800241b6  ja      loc_18002460D
0x1800241bc  movzx   ecx, [rbp+0F0h+var_160]
0x1800241c0  xor     ebx, ebx
0x1800241c2  movzx   r8d, word ptr [r15]; Size
0x1800241c6  add     rcx, rsi; void *
0x1800241c9  mov     rdx, [r15+8]; Src
0x1800241cd  call    memmove
0x1800241d2  movzx   eax, [rbp+0F0h+var_160]
0x1800241d6  add     ax, [r15]
0x1800241da  movzx   edx, ax
0x1800241dd  mov     rax, [rbp+0F0h+Src]
0x1800241e1  mov     [rbp+0F0h+var_160], dx
0x1800241e5  shr     rdx, 1
0x1800241e8  xor     ecx, ecx
0x1800241ea  mov     [rax+rdx*2], cx
0x1800241ee  mov     rsi, [rbp+0F0h+Src]
0x1800241f2  mov     edi, ebx
0x1800241f4  test    ebx, ebx
0x1800241f6  js      short loc_180024241
0x1800241f8  mov     rdx, [r14+8]
0x1800241fc  movzx   eax, word ptr [r14]
0x180024200  add     rax, rdx
0x180024203  sub     rax, 2
0x180024207  cmp     rax, rdx
0x18002420a  jb      short loc_180024225
0x18002420c  movzx   ecx, word ptr [rax]
0x18002420f  cmp     cx, 2Eh ; '.'
0x180024213  jz      loc_18002431A
0x180024219  cmp     cx, 2Fh ; '/'
0x18002421d  jz      short loc_180024225
0x18002421f  cmp     cx, 5Ch ; '\'
0x180024223  jnz     short loc_180024203
0x180024225  lea     rdx, LdrpDefaultExtension; "\b\n"
0x18002422c  lea     rcx, [rbp+0F0h+var_160]
0x180024230  call    LdrpAppendUnicodeStringToFilenameBuffer
0x180024235  mov     ebx, eax
0x180024237  mov     edi, eax
0x180024239  test    eax, eax
0x18002423b  jns     loc_18002488B
0x180024241  mov     dword ptr [rsp+1F0h+var_1C0], ebx
0x180024245  lea     rax, aLdrppreprocess_0; "LdrpPreprocessDllName for DLL %wZ faile"...
0x18002424c  mov     qword ptr [rsp+1F0h+ArgList], r15; ArgList
0x180024251  lea     r8, aLdrppreprocess; "LdrpPreprocessDllName"
0x180024258  xor     r9d, r9d; int
0x18002425b  mov     [rsp+1F0h+Format], rax; Format
0x180024260  mov     edx, 0B2Eh; int
0x180024265  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x18002426c  call    LdrpLogInternal
0x180024271  xor     ebx, ebx
0x180024273  mov     dword ptr [rsp+1F0h+var_1A0+4], edi
0x180024277  mov     rcx, [rbp+0F0h+Src]
0x18002427b  lea     rax, [rbp+0F0h+var_150]
0x18002427f  mov     r14, [rsp+1F0h+var_38]
0x180024287  mov     r13, [rsp+1F0h+var_30]
0x18002428f  mov     rdi, [rsp+1F0h+var_20]
0x180024297  mov     rsi, [rsp+1D8h]
0x18002429f  cmp     rax, rcx
0x1800242a2  jz      short loc_1800242A9
0x1800242a4  call    RtlpSysVolFree
0x1800242a9  lea     rax, [rbp+0F0h+var_150]
0x1800242ad  mov     dword ptr [rbp+0F0h+var_160], 1000000h
0x1800242b4  mov     [rbp+0F0h+Src], rax
0x1800242b8  mov     [rbp+0F0h+var_150], bx
0x1800242bc  mov     rax, gs:60h
0x1800242c5  mov     rcx, [rax+90h]
0x1800242cc  test    rcx, rcx
0x1800242cf  jnz     loc_180024581
0x1800242d5  cmp     byte ptr [r12], 0
0x1800242da  mov     r12, [rsp+1F0h+var_28]
0x1800242e2  jz      short loc_1800242FA
0x1800242e4  mov     rax, gs:60h
0x1800242ed  test    byte ptr [rax+378h], 4
0x1800242f4  jnz     loc_180024745
0x1800242fa  mov     eax, dword ptr [rsp+1F0h+var_1A0+4]
0x1800242fe  mov     rcx, [rbp+0F0h+var_50]
0x180024305  xor     rcx, rsp; StackCookie
0x180024308  call    __security_check_cookie
0x18002430d  add     rsp, 1E0h
0x180024314  pop     r15
0x180024316  pop     rbx
0x180024317  pop     rbp
0x180024318  retn
0x18002431a  movzx   ecx, [rbp+0F0h+var_160]
0x18002431e  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180024322  add     rcx, rsi
0x180024325  cmp     rcx, rsi
0x180024328  jb      short loc_180024339
0x18002432a  mov     eax, 0FFFEh
0x18002432f  cmp     word ptr [rcx], 2Eh ; '.'
0x180024333  jz      loc_1800247E4
0x180024339  xor     ebx, ebx
0x18002433b  mov     [rcx+2], bx
0x18002433f  mov     rdx, [rsp+1F0h+var_178]
0x180024344  lea     rax, [rsp+1F0h+var_1A0+4]
0x180024349  mov     [rsp+40h], rbx; __int64
0x18002434e  lea     rcx, [rbp+0F0h+var_160]; ArgList
0x180024352  mov     [rsp+1F0h+var_1B8], rax; __int64
0x180024357  mov     r9d, 4
0x18002435d  mov     rax, [rsp+1F0h+var_180]
0x180024362  mov     r8d, r13d
  ... truncated ...
```
