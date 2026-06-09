# OpenExtObjectLibrary(EXT_OBJECT *)

- ea: `0x1800136b0`
- end: `0x180014033`
- name: `?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z`
- size: `2435`
- prototype: `__int64 __fastcall(struct EXT_OBJECT *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011d10`

## callees

- `0x180007740`
- `0x18000a0d4`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000ab64`
- `0x18000b0e8`
- `0x18000b264`
- `0x18000b6d4`
- `0x18000c134`
- `0x18000c2b0`
- `0x18000c424`
- `0x18000c774`
- `0x1800119b4`
- `0x1800119fc`
- `0x180011ad4`
- `0x180012df0`
- `0x1800136b0`
- `0x18001403c`
- `0x1800141e0`
- `0x18001422c`
- `0x1800142ac`
- `0x1800143b0`
- `0x18001444c`
- `0x180014508`
- `0x18001458c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001391f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001391f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013aed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e8d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013882`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013f7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013882`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180013f7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013d30`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800138b7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800138b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013a24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ada`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013a24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ada`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013b83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013e6b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013e6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013915`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180013915`

## pseudocode

```c
__int64 __fastcall OpenExtObjectLibrary(struct EXT_OBJECT *a1, __int64 a2, unsigned int *a3)
{
  int *v4; // r13
  DWORD LastError; // edi
  const unsigned __int16 near *const *v6; // r15
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int IsRelative; // eax
  HMODULE Library; // rax
  int v12; // edx
  int v13; // r8d
  int v14; // r12d
  __int64 v15; // rcx
  FARPROC ProcAddress; // rax
  DWORD v17; // eax
  int v18; // r8d
  int v19; // ecx
  FARPROC v20; // rax
  DWORD v21; // eax
  int v22; // ecx
  FARPROC v23; // rax
  DWORD v24; // eax
  int v25; // r8d
  int v26; // ecx
  BOOL v27; // ecx
  int v28; // ecx
  HMODULE *v29; // rdi
  DWORD v30; // eax
  int v31; // edx
  int v32; // r8d
  int v33; // eax
  unsigned int v34; // r15d
  unsigned int v35; // r12d
  __int64 v36; // rcx
  __int64 *v37; // rdx
  unsigned int v39; // [rsp+40h] [rbp-2D8h] BYREF
  int v40; // [rsp+44h] [rbp-2D4h]
  _QWORD *v41; // [rsp+48h] [rbp-2D0h]
  UINT uMode; // [rsp+50h] [rbp-2C8h] BYREF
  unsigned __int8 v43[4]; // [rsp+54h] [rbp-2C4h] BYREF
  HMODULE *v44; // [rsp+58h] [rbp-2C0h]
  HKEY *v45; // [rsp+60h] [rbp-2B8h]
  int v46; // [rsp+68h] [rbp-2B0h]
  int v47; // [rsp+6Ch] [rbp-2ACh]
  void *Block; // [rsp+70h] [rbp-2A8h]
  const unsigned __int16 near *const *v49; // [rsp+78h] [rbp-2A0h]
  struct EXT_OBJECT *v50; // [rsp+80h] [rbp-298h]
  __int64 (__fastcall **v51)(_QWORD); // [rsp+88h] [rbp-290h]
  char *v52; // [rsp+90h] [rbp-288h]
  __int128 v53; // [rsp+98h] [rbp-280h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-270h]
  struct EXT_OBJECT *v55; // [rsp+B8h] [rbp-260h]
  __int128 v56; // [rsp+C0h] [rbp-258h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-248h] BYREF

  v50 = a1;
  *(_DWORD *)v43 = 0;
  v56 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
      *((_QWORD *)a1 + 49));
  v4 = (int *)((char *)a1 + 380);
  v52 = (char *)a1 + 380;
  if ( (*((_BYTE *)a1 + 380) & 0x10) != 0 )
  {
    LastError = 1058;
LABEL_122:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, LastError);
    return LastError;
  }
  v40 = 0;
  v47 = 0;
  v44 = (HMODULE *)((char *)a1 + 88);
  if ( *((_QWORD *)a1 + 11) )
  {
    LastError = 0;
    *((_QWORD *)a1 + 50) = GetTimeAsLongLong();
    goto LABEL_118;
  }
  v6 = &NULL_STRING;
  if ( *((_QWORD *)a1 + 49) )
    v6 = (const unsigned __int16 near *const *)*((_QWORD *)a1 + 49);
  v49 = v6;
  uMode = 0;
  v39 = 4;
  *(_DWORD *)v43 = 0;
  v45 = (HKEY *)((char *)a1 + 104);
  LastError = PrivateRegQueryValueExT(*((HKEY *)a1 + 13), L"Disable Performance Counters", a3, &uMode, v43, &v39, 1);
  v39 = LastError;
  if ( LastError || uMode != 4 )
  {
    LastError = 0;
    v39 = 0;
    *v4 &= ~0x10u;
  }
  else
  {
    *v4 &= ~0x10u;
    v7 = *v4;
    if ( *(_DWORD *)v43 == 1 )
    {
      *v4 = v7 | 0x10;
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = 14;
        goto LABEL_19;
      }
    }
    else if ( *(_DWORD *)v43 == 4 )
    {
      v40 = 1;
      v47 = 1;
      *v4 = v7 | 0x10;
      v8 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = LastError + 16;
LABEL_19:
        WPP_SF_S(v8[2], v9, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
      }
    }
  }
  if ( (*(_BYTE *)v4 & 0x10) == 0 )
  {
    uMode = SetErrorMode(1u);
    v41 = (_QWORD *)((char *)a1 + 96);
    IsRelative = PerflibciPathIsRelative(*((_QWORD *)a1 + 12));
    Library = LoadLibraryExW(*((LPCWSTR *)a1 + 12), 0, IsRelative != 0 ? 4096 : 2304);
    *v44 = Library;
    if ( Library )
    {
      v14 = 0;
      Block = 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v13, *v41, (char)Library);
      if ( !GetModuleFileNameW(*v44, Filename, 0x104u) )
      {
        LastError = GetLastError();
        v39 = LastError;
      }
      if ( !LastError && *((__int64 *)a1 + 52) > 0 )
      {
        if ( (unsigned int)ServiceIsTrustedByDefault(v6) )
          goto LABEL_33;
        v56 = 0;
        LastError = GetPerfDllFileInfo(Filename, (struct DLL_VALIDATION_DATA *)&v56);
        v39 = LastError;
        if ( LastError )
          goto LABEL_40;
        if ( *(_OWORD *)((char *)a1 + 408) == v56 )
        {
LABEL_33:
          *v4 |= 0x20u;
        }
        else
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
          if ( PerfpThrottleError(0x7D3u, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
          {
            McTemplateU0zz_EtwEventWriteTransfer(v15, PERFLIB_NOT_TRUSTED_FILE, *v41, v6);
          }
        }
      }
LABEL_40:
      ProcAddress = GetProcAddress(*v44, *((LPCSTR *)a1 + 3));
      v51 = (__int64 (__fastcall **)(_QWORD))((char *)a1 + 16);
      *((_QWORD *)a1 + 2) = ProcAddress;
      if ( !ProcAddress )
      {
        v17 = GetLastError();
        LastError = v17;
        v39 = v17;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v18, (_DWORD)v6, *((_QWORD *)a1 + 3), v17);
        if ( PerfpThrottleError(0x3EDu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
        {
          McTemplateU0szzq_EtwEventWriteTransfer(
            v19,
            (unsigned int)PERFLIB_OPEN_PROC_NOT_FOUND,
            *((_QWORD *)a1 + 3),
            *v41,
            (__int64)v6,
            LastError);
        }
      }
      if ( !LastError )
      {
        v20 = GetProcAddress(*v44, *((LPCSTR *)a1 + 6));
        *((_QWORD *)a1 + 5) = v20;
        if ( !v20 )
        {
          v21 = GetLastError();
          LastError = v21;
          v39 = v21;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              (unsigned int)WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
              (_DWORD)v6,
              v21);
          if ( PerfpThrottleError(0x3EEu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
            && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
          {
            McTemplateU0szzq_EtwEventWriteTransfer(
              v22,
              (unsigned int)PERFLIB_COLLECT_PROC_NOT_FOUND,
              *((_QWORD *)a1 + 6),
              *v41,
              (__int64)v6,
              LastError);
          }
        }
        if ( !LastError )
        {
          v23 = GetProcAddress(*v44, *((LPCSTR *)a1 + 9));
          *((_QWORD *)a1 + 8) = v23;
          if ( !v23 )
          {
            v24 = GetLastError();
            LastError = v24;
            v39 = v24;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v25, (_DWORD)v6, *((_QWORD *)a1 + 9), v24);
            if ( PerfpThrottleError(0x3EFu, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
              && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
            {
              McTemplateU0szzq_EtwEventWriteTransfer(
                v26,
                (unsigned int)PERFLIB_CLOSE_PROC_NOT_FOUND,
                *((_QWORD *)a1 + 9),
                *v41,
                (__int64)v6,
                LastError);
            }
          }
        }
      }
      v27 = (lPerflibConfigFlags & 4) == 0 && (*v4 & 0x20) == 0;
      if ( !LastError )
      {
        *(_QWORD *)&v53 = 0;
        *((_QWORD *)&v53 + 1) = *v41;
        *(_QWORD *)&v54 = v6;
        DWORD2(v54) = *((_DWORD *)a1 + 15);
        HIDWORD(v54) = 2002;
        v55 = a1;
        if ( v27 )
        {
          Block = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)&v53);
          if ( !Block && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids);
        }
        else
        {
          Block = 0;
        }
        if ( *v51 )
        {
          v14 = (*v51)(*((_QWORD *)a1 + 4));
          v46 = v14;
        }
        else
        {
          v14 = 127;
          v46 = 127;
        }
        if ( v14 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              (unsigned int)WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids,
              (_DWORD)v6,
              v14);
          if ( v14 == 5 )
          {
            *((_DWORD *)a1 + 130) = GetCurrentThreadId();
            *((_DWORD *)a1 + 121) = 0;
          }
          else
          {
            ++*((_DWORD *)a1 + 121);
          }
        }
        else
        {
          *((_DWORD *)a1 + 130) = 0;
          _InterlockedIncrement((volatile signed __int32 *)a1 + 113);
        }
        if ( Block )
          LastError = KillPerflibFunctionTimer(Block);
        if ( !v14 )
          goto LABEL_97;
        if ( PerfpThrottleError(0x3F0u, *v45, (struct ERROR_LOG *)((char *)a1 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
        {
          McTemplateU0zzq_EtwEventWriteTransfer(v28, (unsigned int)PERFLIB_OPEN_PROC_FAILURE, (_DWORD)v6, *v41, v14);
        }
      }
      if ( v14 )
      {
        *v51 = 0;
        *((_QWORD *)a1 + 5) = 0;
        *((_QWORD *)a1 + 8) = 0;
        v29 = v44;
        if ( *v44 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids, v6);
          FreeLibrary(*v29);
          *v29 = 0;
        }
        LastError = v14;
        goto LABEL_116;
      }
LABEL_97:
      *((_QWORD *)a1 + 50) = GetTimeAsLongLong();
LABEL_116:
      SetErrorMode(uMode);
      goto LABEL_118;
    }
    v30 = GetLastError();
    LastError = v30;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, (_DWORD)v6, *((_QWORD *)a1 + 12), v30);
    v33 = v40;
    if ( LastError == 193 )
      v33 = 1;
    v40 = v33;
    v34 = 1021;
    if ( LastError != 193 )
      v34 = 1023;
    v35 = 4;
    if ( LastError != 193 )
      v35 = 0;
    if ( PerfpThrottleError(v34, *v45, (struct ERROR_LOG *)((char *)a1 + 488)) )
    {
      if ( v34 == 1021 )
      {
        if ( (Microsoft_Windows_PerflibEnableBits & 2) == 0 )
          goto LABEL_114;
        v37 = PERFLIB_INVALID_WOW32_PERF_DLL;
      }
      else
      {
        if ( (Microsoft_Windows_PerflibEnableBits & 2) == 0 )
          goto LABEL_114;
        v37 = PERFLIB_CANNOT_LOAD_PERF_DLL;
      }
      McTemplateU0zq_EtwEventWriteTransfer(v36, v37, *v41, LastError);
    }
LABEL_114:
    if ( LastError == 193 )
      DisablePerfLibrary(a1, v35, v34, 0xC1u, 0);
    goto LABEL_116;
  }
LABEL_118:
  if ( v40 )
  {
    LastError = OpenRemoteExtObjectLibrary(a1);
    if ( !LastError )
      *v4 &= ~0x10u;
  }
  if ( LastError )
    goto LABEL_122;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids);
  return LastError;
}

```

## disassembly

```asm
0x1800136b0  mov     [rsp+arg_8], rbx
0x1800136b5  mov     [rsp+arg_10], rsi
0x1800136ba  push    rdi
0x1800136bb  push    r12
0x1800136bd  push    r13
0x1800136bf  push    r14
0x1800136c1  push    r15
0x1800136c3  sub     rsp, 2F0h
0x1800136ca  mov     rax, cs:__security_cookie
0x1800136d1  xor     rax, rsp
0x1800136d4  mov     [rsp+318h+var_38], rax
0x1800136dc  mov     rsi, rcx
0x1800136df  mov     [rsp+318h+var_298], rcx
0x1800136e7  xor     ebx, ebx
0x1800136e9  mov     dword ptr [rsp+318h+var_2C4], ebx
0x1800136ed  xorps   xmm0, xmm0
0x1800136f0  movups  [rsp+318h+var_258], xmm0
0x1800136f8  xorps   xmm1, xmm1
0x1800136fb  xor     eax, eax
0x1800136fd  movups  [rsp+318h+var_280], xmm1
0x180013705  movups  [rsp+318h+var_270], xmm1
0x18001370d  mov     [rsp+318h+var_260], rax
0x180013715  mov     rcx, cs:WPP_GLOBAL_Control
0x18001371c  lea     r14d, [rbx+4]
0x180013720  test    [rcx+1Ch], r14b
0x180013724  jz      short loc_180013746
0x180013726  cmp     [rcx+19h], r14b
0x18001372a  jb      short loc_180013746
0x18001372c  lea     edx, [rbx+0Dh]
0x18001372f  mov     r9, [rsi+188h]
0x180013736  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18001373d  mov     rcx, [rcx+10h]
0x180013741  call    WPP_SF_S
0x180013746  lea     r13, [rsi+17Ch]
0x18001374d  mov     [rsp+318h+var_288], r13
0x180013755  test    byte ptr [r13+0], 10h
0x18001375a  jz      short loc_180013766
0x18001375c  mov     edi, 422h
0x180013761  jmp     loc_180013FAF
0x180013766  mov     [rsp+318h+var_2D4], ebx
0x18001376a  mov     [rsp+318h+var_2AC], ebx
0x18001376e  lea     rax, [rsi+58h]
0x180013772  mov     [rsp+318h+var_2C0], rax
0x180013777  cmp     [rax], rbx
0x18001377a  jnz     loc_180013F84
0x180013780  mov     rax, [rsi+188h]
0x180013787  lea     r15, ?NULL_STRING@@3QBGB; ushort const near * const NULL_STRING
0x18001378e  test    rax, rax
0x180013791  cmovnz  r15, rax
0x180013795  mov     [rsp+318h+var_2A0], r15
0x18001379a  mov     [rsp+318h+uMode], ebx
0x18001379e  mov     [rsp+318h+var_2D8], r14d
0x1800137a3  mov     dword ptr [rsp+318h+var_2C4], ebx
0x1800137a7  lea     rax, [rsi+68h]
0x1800137ab  mov     [rsp+318h+var_2B8], rax
0x1800137b0  mov     r12d, 1
0x1800137b6  mov     [rsp+318h+var_2E8], r12d; int
0x1800137bb  lea     rcx, [rsp+318h+var_2D8]
0x1800137c0  mov     [rsp+318h+var_2F0], rcx; unsigned int *
0x1800137c5  lea     rcx, [rsp+318h+var_2C4]
0x1800137ca  mov     [rsp+318h+var_2F8], rcx; unsigned __int8 *
0x1800137cf  lea     r9, [rsp+318h+uMode]; unsigned int *
0x1800137d4  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x1800137db  mov     rcx, [rax]; KeyHandle
0x1800137de  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x1800137e3  mov     edi, eax
0x1800137e5  mov     [rsp+318h+var_2D8], eax
0x1800137e9  test    eax, eax
0x1800137eb  jnz     short loc_180013869
0x1800137ed  cmp     [rsp+318h+uMode], r14d
0x1800137f2  jnz     short loc_180013869
0x1800137f4  and     dword ptr [r13+0], 0FFFFFFEFh
0x1800137f9  mov     eax, [r13+0]
0x1800137fd  mov     ecx, dword ptr [rsp+318h+var_2C4]
0x180013801  sub     ecx, r12d
0x180013804  jz      short loc_180013835
0x180013806  cmp     ecx, 3
0x180013809  jnz     short loc_180013874
0x18001380b  mov     ecx, r12d
0x18001380e  mov     [rsp+318h+var_2D4], ecx
0x180013812  mov     [rsp+318h+var_2AC], ecx
0x180013816  or      eax, 10h
0x180013819  mov     [r13+0], eax
0x18001381d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013824  test    [rcx+1Ch], r14b
0x180013828  jz      short loc_180013874
0x18001382a  cmp     byte ptr [rcx+19h], 3
0x18001382e  jb      short loc_180013874
0x180013830  lea     edx, [rdi+10h]
0x180013833  jmp     short loc_180013854
0x180013835  or      eax, 10h
0x180013838  mov     [r13+0], eax
0x18001383c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013843  test    [rcx+1Ch], r14b
0x180013847  jz      short loc_180013874
0x180013849  cmp     byte ptr [rcx+19h], 3
0x18001384d  jb      short loc_180013874
0x18001384f  mov     edx, 0Eh
0x180013854  mov     r9, r15
0x180013857  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x18001385e  mov     rcx, [rcx+10h]
0x180013862  call    WPP_SF_S
0x180013867  jmp     short loc_180013874
0x180013869  mov     edi, ebx
0x18001386b  mov     [rsp+318h+var_2D8], ebx
0x18001386f  and     dword ptr [r13+0], 0FFFFFFEFh
0x180013874  test    byte ptr [r13+0], 10h
0x180013879  jnz     loc_180013F92
0x18001387f  mov     ecx, r12d; uMode
0x180013882  call    cs:__imp_SetErrorMode
0x180013888  mov     [rsp+318h+uMode], eax
0x18001388c  lea     r12, [rsi+60h]
0x180013890  mov     [rsp+318h+var_2D0], r12
0x180013895  mov     rcx, [r12]
0x180013899  call    PerflibciPathIsRelative
0x18001389e  neg     eax
0x1800138a0  sbb     r8d, r8d
0x1800138a3  and     r8d, 700h
0x1800138aa  add     r8d, 900h; dwFlags
0x1800138b1  xor     edx, edx; hFile
0x1800138b3  mov     rcx, [r12]; lpLibFileName
0x1800138b7  call    cs:__imp_LoadLibraryExW
0x1800138bd  mov     rcx, [rsp+318h+var_2C0]
0x1800138c2  mov     [rcx], rax
0x1800138c5  test    rax, rax
0x1800138c8  jz      loc_180013E8D
0x1800138ce  mov     r12d, ebx
0x1800138d1  mov     [rsp+318h+Block], rbx
0x1800138d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138dd  test    [rcx+1Ch], r14b
0x1800138e1  jz      short loc_1800138FF
0x1800138e3  cmp     [rcx+19h], r14b
0x1800138e7  jb      short loc_1800138FF
0x1800138e9  mov     [rsp+318h+var_2F8], rax
0x1800138ee  mov     r9, [rsp+318h+var_2D0]
0x1800138f3  mov     r9, [r9]
0x1800138f6  mov     rcx, [rcx+10h]
0x1800138fa  call    WPP_SF_Sq
0x1800138ff  mov     r8d, 104h; nSize
0x180013905  lea     rdx, [rsp+318h+Filename]; lpFilename
0x18001390d  mov     rax, [rsp+318h+var_2C0]
0x180013912  mov     rcx, [rax]; hModule
0x180013915  call    cs:__imp_GetModuleFileNameW
0x18001391b  test    eax, eax
0x18001391d  jnz     short loc_18001392B
0x18001391f  call    cs:__imp_GetLastError
0x180013925  mov     edi, eax
0x180013927  mov     [rsp+318h+var_2D8], eax
0x18001392b  test    edi, edi
0x18001392d  jnz     loc_180013A18
0x180013933  cmp     [rsi+1A0h], rbx
0x18001393a  jle     loc_180013A18
0x180013940  mov     rcx, r15
0x180013943  call    ServiceIsTrustedByDefault
0x180013948  test    eax, eax
0x18001394a  jnz     short loc_1800139A9
0x18001394c  xorps   xmm0, xmm0
0x18001394f  movups  [rsp+318h+var_258], xmm0
0x180013957  lea     rdx, [rsp+318h+var_258]; struct DLL_VALIDATION_DATA *
0x18001395f  lea     rcx, [rsp+318h+Filename]; unsigned __int16 *
0x180013967  call    ?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z; GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)
0x18001396c  mov     edi, eax
0x18001396e  mov     [rsp+318h+var_2D8], eax
0x180013972  test    eax, eax
0x180013974  jnz     loc_180013A18
0x18001397a  mov     eax, dword ptr [rsp+318h+var_258+4]
0x180013981  cmp     [rsi+19Ch], eax
0x180013987  jnz     short loc_1800139B0
0x180013989  mov     eax, dword ptr [rsp+318h+var_258]
0x180013990  cmp     [rsi+198h], eax
0x180013996  jnz     short loc_1800139B0
0x180013998  mov     rax, qword ptr [rsp+318h+var_258+8]
0x1800139a0  cmp     [rsi+1A0h], rax
0x1800139a7  jnz     short loc_1800139B0
0x1800139a9  or      dword ptr [r13+0], 20h
0x1800139ae  jmp     short loc_180013A18
0x1800139b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139b7  test    [rcx+1Ch], r14b
0x1800139bb  jz      short loc_1800139DB
0x1800139bd  cmp     byte ptr [rcx+19h], 2
0x1800139c1  jb      short loc_1800139DB
0x1800139c3  mov     edx, 12h
0x1800139c8  mov     r9, r15
0x1800139cb  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x1800139d2  mov     rcx, [rcx+10h]
0x1800139d6  call    WPP_SF_S
0x1800139db  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x1800139e2  mov     rdx, [rsp+318h+var_2B8]
0x1800139e7  mov     rdx, [rdx]; HKEY
0x1800139ea  mov     ecx, 7D3h; unsigned int
0x1800139ef  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x1800139f4  test    eax, eax
0x1800139f6  jz      short loc_180013A18
0x1800139f8  test    cs:Microsoft_Windows_PerflibEnableBits, r14b
0x1800139ff  jz      short loc_180013A18
0x180013a01  mov     r9, r15
0x180013a04  mov     rax, [rsp+318h+var_2D0]
0x180013a09  mov     r8, [rax]
0x180013a0c  lea     rdx, PERFLIB_NOT_TRUSTED_FILE
0x180013a13  call    McTemplateU0zz_EtwEventWriteTransfer
0x180013a18  mov     rdx, [rsi+18h]; lpProcName
0x180013a1c  mov     rax, [rsp+318h+var_2C0]
0x180013a21  mov     rcx, [rax]; hModule
0x180013a24  call    cs:__imp_GetProcAddress
0x180013a2a  lea     rcx, [rsi+10h]
0x180013a2e  mov     [rsp+318h+var_290], rcx
0x180013a36  mov     [rcx], rax
0x180013a39  test    rax, rax
0x180013a3c  jnz     loc_180013AC6
0x180013a42  call    cs:__imp_GetLastError
0x180013a48  mov     edi, eax
0x180013a4a  mov     [rsp+318h+var_2D8], eax
0x180013a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a55  test    [rcx+1Ch], r14b
0x180013a59  jz      short loc_180013A7F
0x180013a5b  cmp     byte ptr [rcx+19h], 2
0x180013a5f  jb      short loc_180013A7F
0x180013a61  mov     edx, 13h
0x180013a66  mov     dword ptr [rsp+318h+var_2F0], eax
0x180013a6a  mov     rax, [rsi+18h]
0x180013a6e  mov     [rsp+318h+var_2F8], rax
0x180013a73  mov     r9, r15
0x180013a76  mov     rcx, [rcx+10h]
0x180013a7a  call    WPP_SF_Ssd
0x180013a7f  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x180013a86  mov     rax, [rsp+318h+var_2B8]
0x180013a8b  mov     rdx, [rax]; HKEY
0x180013a8e  mov     ecx, 3EDh; unsigned int
0x180013a93  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180013a98  test    eax, eax
0x180013a9a  jz      short loc_180013AC6
0x180013a9c  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180013aa3  jz      short loc_180013AC6
0x180013aa5  mov     dword ptr [rsp+318h+var_2F0], edi
0x180013aa9  mov     [rsp+318h+var_2F8], r15
0x180013aae  mov     rax, [rsp+318h+var_2D0]
0x180013ab3  mov     r9, [rax]
0x180013ab6  mov     r8, [rsi+18h]
0x180013aba  lea     rdx, PERFLIB_OPEN_PROC_NOT_FOUND
0x180013ac1  call    McTemplateU0szzq_EtwEventWriteTransfer
0x180013ac6  test    edi, edi
0x180013ac8  jnz     loc_180013C1A
0x180013ace  mov     rdx, [rsi+30h]; lpProcName
0x180013ad2  mov     rax, [rsp+318h+var_2C0]
0x180013ad7  mov     rcx, [rax]; hModule
0x180013ada  call    cs:__imp_GetProcAddress
0x180013ae0  mov     [rsi+28h], rax
0x180013ae4  test    rax, rax
0x180013ae7  jnz     loc_180013B6F
0x180013aed  call    cs:__imp_GetLastError
0x180013af3  mov     edi, eax
0x180013af5  mov     [rsp+318h+var_2D8], eax
0x180013af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b00  test    [rcx+1Ch], r14b
0x180013b04  jz      short loc_180013B28
0x180013b06  cmp     byte ptr [rcx+19h], 2
0x180013b0a  jb      short loc_180013B28
0x180013b0c  mov     edx, 14h
0x180013b11  mov     dword ptr [rsp+318h+var_2F8], eax
0x180013b15  mov     r9, r15
0x180013b18  lea     r8, WPP_87c7810662dc3a996ea6084ec2e5f776_Traceguids
0x180013b1f  mov     rcx, [rcx+10h]
0x180013b23  call    WPP_SF_Sd
0x180013b28  lea     r8, [rsi+1E8h]; struct ERROR_LOG *
0x180013b2f  mov     rax, [rsp+318h+var_2B8]
0x180013b34  mov     rdx, [rax]; HKEY
0x180013b37  mov     ecx, 3EEh; unsigned int
0x180013b3c  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180013b41  test    eax, eax
0x180013b43  jz      short loc_180013B6F
0x180013b45  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180013b4c  jz      short loc_180013B6F
0x180013b4e  mov     dword ptr [rsp+318h+var_2F0], edi
0x180013b52  mov     [rsp+318h+var_2F8], r15
0x180013b57  mov     rax, [rsp+318h+var_2D0]
0x180013b5c  mov     r9, [rax]
0x180013b5f  mov     r8, [rsi+30h]
0x180013b63  lea     rdx, PERFLIB_COLLECT_PROC_NOT_FOUND
0x180013b6a  call    McTemplateU0szzq_EtwEventWriteTransfer
0x180013b6f  test    edi, edi
0x180013b71  jnz     loc_180013C1A
0x180013b77  mov     rdx, [rsi+48h]; lpProcName
0x180013b7b  mov     rax, [rsp+318h+var_2C0]
0x180013b80  mov     rcx, [rax]; hModule
0x180013b83  call    cs:__imp_GetProcAddress
0x180013b89  mov     [rsi+40h], rax
0x180013b8d  test    rax, rax
0x180013b90  jnz     loc_180013C1A
0x180013b96  call    cs:__imp_GetLastError
0x180013b9c  mov     edi, eax
0x180013b9e  mov     [rsp+318h+var_2D8], eax
0x180013ba2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ba9  test    [rcx+1Ch], r14b
0x180013bad  jz      short loc_180013BD3
0x180013baf  cmp     byte ptr [rcx+19h], 2
0x180013bb3  jb      short loc_180013BD3
0x180013bb5  mov     edx, 15h
0x180013bba  mov     dword ptr [rsp+318h+var_2F0], eax
0x180013bbe  mov     rax, [rsi+48h]
0x180013bc2  mov     [rsp+318h+var_2F8], rax
  ... truncated ...
```
