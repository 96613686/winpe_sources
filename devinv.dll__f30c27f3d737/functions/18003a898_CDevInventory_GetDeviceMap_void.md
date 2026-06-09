# CDevInventory::GetDeviceMap(void * *)

- ea: `0x18003a898`
- end: `0x18003aec6`
- name: `?GetDeviceMap@CDevInventory@@AEAAJPEAPEAX@Z`
- size: `1582`
- prototype: `__int64 __fastcall(CDevInventory *__hidden this, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180039b88`

## callees

- `0x180005e40`
- `0x180006210`
- `0x1800066f0`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x18003a898`
- `0x18003c678`
- `0x18006041c`
- `0x18006154c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003aa40`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003aa40`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a959`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003a959`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ae93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003ae93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ab24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003ab24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ae71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ae71`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003a8eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003a8eb`

## string_xrefs

- `0x18003aa67`: `[0x%08x] CreateThread failed for printer enumeration`

## pseudocode

```c
__int64 __fastcall CDevInventory::GetDeviceMap(CDevInventory *this, void **a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rbp
  int v6; // edx
  int v7; // ebx
  signed int v8; // eax
  signed int v9; // ebx
  char *v10; // rax
  char *v11; // rdi
  _OWORD *v12; // rax
  _OWORD *v13; // rcx
  __int128 v14; // xmm1
  void *v15; // rax
  void *v16; // r12
  signed int v17; // eax
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  DWORD v21; // eax
  CDevInventory *v22; // rcx
  signed int LastError; // eax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  FILE *v28; // rax
  FILE *v29; // rax
  FILE *v30; // rax
  FILE *v31; // rax
  FILE *v32; // rax
  FILE *v33; // rax
  FILE *v34; // rax
  FILE *v35; // rax
  HMODULE phModule; // [rsp+30h] [rbp-188h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-178h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  phModule = 0;
  if ( !GetVersionExW(&VersionInformation)
    || VersionInformation.dwMajorVersion < 6
    || VersionInformation.dwMajorVersion == 6 && !VersionInformation.dwMinorVersion )
  {
    return 2147500033LL;
  }
  v4 = *((_DWORD *)this + 3);
  v5 = 4;
  v6 = (v4 >> 3) & 0x80000 | 0x100000;
  if ( (v4 & 0x1000000) == 0 )
    v6 = (*((_DWORD *)this + 3) >> 3) & 0x80000;
  v7 = v6 | 0x200000;
  if ( (v4 & 0x800000) == 0 )
    v7 = v6;
  GetModuleHandleExW(4u, (LPCWSTR)CreateDeviceInventory, &phModule);
  if ( phModule )
  {
    v10 = (char *)operator new(0x228u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 2) = 0;
      *(_QWORD *)v10 = 0;
      *((_DWORD *)v10 + 4) = -2147467263;
      *((_DWORD *)v10 + 3) = v7;
      *((_QWORD *)v10 + 3) = phModule;
      if ( (v7 & 0x200000) != 0 )
      {
        v12 = (_OWORD *)*((_QWORD *)this + 2);
        if ( v12 )
        {
          v13 = v11 + 32;
          do
          {
            *v13 = *v12;
            v13[1] = v12[1];
            v13[2] = v12[2];
            v13[3] = v12[3];
            v13[4] = v12[4];
            v13[5] = v12[5];
            v13[6] = v12[6];
            v14 = v12[7];
            v12 += 8;
            v13[7] = v14;
            v13 += 8;
            --v5;
          }
          while ( v5 );
          *(_QWORD *)v13 = *(_QWORD *)v12;
        }
      }
      v15 = (void *)_o__beginthreadex(0, 0, GetDeviceMapWorker, v11, 0, 0);
      v16 = v15;
      if ( v15 )
      {
        phModule = 0;
        v21 = WaitForSingleObject(v15, 0x124F80u);
        if ( v21 )
        {
          v22 = (CDevInventory *)(unsigned int)_InterlockedExchange((volatile __int32 *)v11 + 2, 1);
          if ( v21 == 258 )
          {
            v9 = -2147024638;
            v11 = 0;
            if ( !(unsigned int)CDevInventory::ReportWatsonEvent(v22) )
            {
              AslLogCallPrintf(
                2,
                "CDevInventory::GetDeviceMap",
                1273,
                "Failed to send Watson report [%#x]",
                -2147467259);
              if ( EnableDevInvStdErrLog )
              {
                v27 = o___acrt_iob_func_0(2u);
                fprintf(v27, "Error: %s, %u: ", "CDevInventory::GetDeviceMap", 1273);
                v28 = o___acrt_iob_func_0(2u);
                fprintf(v28, "Failed to send Watson report [%#x]", -2147467259);
                v29 = o___acrt_iob_func_0(2u);
                fprintf(v29, "\n");
              }
              if ( g_DeviceMapLogFunction )
                TraceMessageCallback(0x2000000, "Failed to send Watson report [%#x]", -2147467259);
              AslLogCallPrintf(
                1,
                "CDevInventory::GetDeviceMap",
                1273,
                "Failed to send Watson report [%#x]",
                -2147467259);
            }
            AslLogCallPrintf(
              2,
              "CDevInventory::GetDeviceMap",
              1275,
              "[0x%08x] Failed to generate device map",
              -2147024638);
            if ( EnableDevInvStdErrLog )
            {
              v30 = o___acrt_iob_func_0(2u);
              fprintf(v30, "Error: %s, %u: ", "CDevInventory::GetDeviceMap", 1275);
              v31 = o___acrt_iob_func_0(2u);
              fprintf(v31, "[0x%08x] Failed to generate device map", -2147024638);
              v32 = o___acrt_iob_func_0(2u);
              fprintf(v32, "\n");
            }
            if ( g_DeviceMapLogFunction )
              TraceMessageCallback(0x2000000, "[0x%08x] Failed to generate device map", -2147024638);
            AslLogCallPrintf(
              1,
              "CDevInventory::GetDeviceMap",
              1275,
              "[0x%08x] Failed to generate device map",
              -2147024638);
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          else
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            v11 = 0;
            AslLogCallPrintf(2, "CDevInventory::GetDeviceMap", 1285, "[0x%08x] Failed to generate device map", v9);
            if ( EnableDevInvStdErrLog )
            {
              v24 = o___acrt_iob_func_0(2u);
              fprintf(v24, "Error: %s, %u: ", "CDevInventory::GetDeviceMap", 1285);
              v25 = o___acrt_iob_func_0(2u);
              fprintf(v25, "[0x%08x] Failed to generate device map", v9);
              v26 = o___acrt_iob_func_0(2u);
              fprintf(v26, "\n");
            }
            if ( g_DeviceMapLogFunction )
              TraceMessageCallback(0x2000000, "[0x%08x] Failed to generate device map", v9);
            AslLogCallPrintf(1, "CDevInventory::GetDeviceMap", 1285, "[0x%08x] Failed to generate device map", v9);
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
        else if ( _InterlockedExchange((volatile __int32 *)v11 + 2, 1) )
        {
          v9 = *((_DWORD *)v11 + 4);
          if ( v9 >= 0 )
            *a2 = *(void **)v11;
        }
        else
        {
          v9 = -2147467259;
          v11 = 0;
          AslLogCallPrintf(
            2,
            "CDevInventory::GetDeviceMap",
            1254,
            "[0x%08x] Failed to generate device map",
            -2147467259);
          if ( EnableDevInvStdErrLog )
          {
            v33 = o___acrt_iob_func_0(2u);
            fprintf(v33, "Error: %s, %u: ", "CDevInventory::GetDeviceMap", 1254);
            v34 = o___acrt_iob_func_0(2u);
            fprintf(v34, "[0x%08x] Failed to generate device map", -2147467259);
            v35 = o___acrt_iob_func_0(2u);
            fprintf(v35, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "[0x%08x] Failed to generate device map", -2147467259);
          AslLogCallPrintf(
            1,
            "CDevInventory::GetDeviceMap",
            1254,
            "[0x%08x] Failed to generate device map",
            -2147467259);
        }
        CloseHandle(v16);
        if ( !v11 )
          goto LABEL_57;
      }
      else
      {
        v17 = GetLastError();
        v9 = v17;
        if ( v17 > 0 )
          v9 = (unsigned __int16)v17 | 0x80070000;
        AslLogCallPrintf(
          2,
          "CDevInventory::GetDeviceMap",
          1222,
          "[0x%08x] CreateThread failed for printer enumeration",
          v9);
        if ( EnableDevInvStdErrLog )
        {
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "Error: %s, %u: ", "CDevInventory::GetDeviceMap", 1222);
          v19 = o___acrt_iob_func_0(2u);
          fprintf(v19, "[0x%08x] CreateThread failed for printer enumeration", v9);
          v20 = o___acrt_iob_func_0(2u);
          fprintf(v20, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "[0x%08x] CreateThread failed for printer enumeration", v9);
        AslLogCallPrintf(
          1,
          "CDevInventory::GetDeviceMap",
          1222,
          "[0x%08x] CreateThread failed for printer enumeration",
          v9);
      }
      operator delete(v11);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
LABEL_57:
  if ( phModule )
    FreeLibrary(phModule);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003a898  push    rbx
0x18003a89a  push    rbp
0x18003a89b  push    rsi
0x18003a89c  push    rdi
0x18003a89d  push    r12
0x18003a89f  push    r13
0x18003a8a1  push    r14
0x18003a8a3  push    r15
0x18003a8a5  sub     rsp, 178h
0x18003a8ac  mov     rax, cs:__security_cookie
0x18003a8b3  xor     rax, rsp
0x18003a8b6  mov     [rsp+1B8h+var_58], rax
0x18003a8be  mov     r14, rdx
0x18003a8c1  mov     rsi, rcx
0x18003a8c4  xor     edx, edx; Val
0x18003a8c6  lea     rcx, [rsp+1B8h+VersionInformation.dwMajorVersion]; void *
0x18003a8cb  mov     r8d, 110h; Size
0x18003a8d1  call    memset_0
0x18003a8d6  xor     r13d, r13d
0x18003a8d9  mov     [rsp+1B8h+VersionInformation.dwOSVersionInfoSize], 114h
0x18003a8e1  lea     rcx, [rsp+1B8h+VersionInformation]; lpVersionInformation
0x18003a8e6  mov     [rsp+1B8h+phModule], r13
0x18003a8eb  call    cs:__imp_GetVersionExW
0x18003a8f1  test    eax, eax
0x18003a8f3  jz      loc_18003AE9D
0x18003a8f9  cmp     [rsp+1B8h+VersionInformation.dwMajorVersion], 6
0x18003a8fe  jb      loc_18003AE9D
0x18003a904  lea     r15d, [r13+1]
0x18003a908  jnz     short loc_18003A915
0x18003a90a  cmp     [rsp+1B8h+VersionInformation.dwMinorVersion], r15d
0x18003a90f  jb      loc_18003AE9D
0x18003a915  mov     r8d, [rsi+0Ch]
0x18003a919  mov     r12d, 200000h
0x18003a91f  mov     ecx, r8d
0x18003a922  mov     ebp, 4
0x18003a927  shr     ecx, 3
0x18003a92a  and     ecx, 80000h
0x18003a930  mov     edx, ecx
0x18003a932  bts     edx, 14h
0x18003a936  bt      r8d, 18h
0x18003a93b  cmovnb  edx, ecx
0x18003a93e  mov     ecx, ebp; dwFlags
0x18003a940  mov     ebx, edx
0x18003a942  or      ebx, r12d
0x18003a945  bt      r8d, 17h
0x18003a94a  lea     r8, [rsp+1B8h+phModule]; phModule
0x18003a94f  cmovnb  ebx, edx
0x18003a952  lea     rdx, CreateDeviceInventory; lpModuleName
0x18003a959  call    cs:__imp_GetModuleHandleExW
0x18003a95f  cmp     [rsp+1B8h+phModule], r13
0x18003a964  jnz     short loc_18003A984
0x18003a966  call    cs:__imp_GetLastError
0x18003a96c  mov     ebx, eax
0x18003a96e  test    eax, eax
0x18003a970  jle     loc_18003AE89
0x18003a976  movzx   ebx, ax
0x18003a979  or      ebx, 80070000h
0x18003a97f  jmp     loc_18003AE89
0x18003a984  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a98b  mov     ecx, 228h; unsigned __int64
0x18003a990  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a995  mov     rdi, rax
0x18003a998  test    rax, rax
0x18003a99b  jnz     short loc_18003A9A7
0x18003a99d  mov     ebx, 8007000Eh
0x18003a9a2  jmp     loc_18003AE89
0x18003a9a7  mov     [rax+8], r13d
0x18003a9ab  mov     [rax], r13
0x18003a9ae  mov     dword ptr [rax+10h], 80004001h
0x18003a9b5  mov     [rax+0Ch], ebx
0x18003a9b8  mov     rax, [rsp+1B8h+phModule]
0x18003a9bd  mov     [rdi+18h], rax
0x18003a9c1  test    r12d, ebx
0x18003a9c4  jz      short loc_18003AA28
0x18003a9c6  mov     rax, [rsi+10h]
0x18003a9ca  test    rax, rax
0x18003a9cd  jz      short loc_18003AA28
0x18003a9cf  lea     rcx, [rdi+20h]
0x18003a9d3  mov     edx, 80h
0x18003a9d8  movups  xmm0, xmmword ptr [rax]
0x18003a9db  movups  xmmword ptr [rcx], xmm0
0x18003a9de  movups  xmm1, xmmword ptr [rax+10h]
0x18003a9e2  movups  xmmword ptr [rcx+10h], xmm1
0x18003a9e6  movups  xmm0, xmmword ptr [rax+20h]
0x18003a9ea  movups  xmmword ptr [rcx+20h], xmm0
0x18003a9ee  movups  xmm1, xmmword ptr [rax+30h]
0x18003a9f2  movups  xmmword ptr [rcx+30h], xmm1
0x18003a9f6  movups  xmm0, xmmword ptr [rax+40h]
0x18003a9fa  movups  xmmword ptr [rcx+40h], xmm0
0x18003a9fe  movups  xmm1, xmmword ptr [rax+50h]
0x18003aa02  movups  xmmword ptr [rcx+50h], xmm1
0x18003aa06  movups  xmm0, xmmword ptr [rax+60h]
0x18003aa0a  movups  xmmword ptr [rcx+60h], xmm0
0x18003aa0e  movups  xmm1, xmmword ptr [rax+70h]
0x18003aa12  add     rax, rdx
0x18003aa15  movups  xmmword ptr [rcx+70h], xmm1
0x18003aa19  add     rcx, rdx
0x18003aa1c  sub     rbp, 1
0x18003aa20  jnz     short loc_18003A9D8
0x18003aa22  mov     rax, [rax]
0x18003aa25  mov     [rcx], rax
0x18003aa28  mov     [rsp+1B8h+var_190], r13
0x18003aa2d  lea     r8, ?GetDeviceMapWorker@@YAIPEAX@Z; GetDeviceMapWorker(void *)
0x18003aa34  mov     r9, rdi
0x18003aa37  mov     [rsp+1B8h+var_198], r13d
0x18003aa3c  xor     edx, edx
0x18003aa3e  xor     ecx, ecx
0x18003aa40  call    cs:__imp__o__beginthreadex
0x18003aa46  mov     r12, rax
0x18003aa49  test    rax, rax
0x18003aa4c  jnz     loc_18003AB17
0x18003aa52  call    cs:__imp_GetLastError
0x18003aa58  mov     ebx, eax
0x18003aa5a  test    eax, eax
0x18003aa5c  jle     short loc_18003AA67
0x18003aa5e  movzx   ebx, ax
0x18003aa61  or      ebx, 80070000h
0x18003aa67  lea     r14, a0x08xCreatethr; "[0x%08x] CreateThread failed for printe"...
0x18003aa6e  mov     [rsp+1B8h+var_198], ebx
0x18003aa72  mov     r12d, 4C6h
0x18003aa78  lea     rsi, aCdevinventoryG_0; "CDevInventory::GetDeviceMap"
0x18003aa7f  mov     ebp, 2
0x18003aa84  mov     r9, r14
0x18003aa87  mov     r8d, r12d
0x18003aa8a  mov     rdx, rsi
0x18003aa8d  mov     ecx, ebp
0x18003aa8f  call    AslLogCallPrintf
0x18003aa94  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003aa9b  jz      short loc_18003AAE4
0x18003aa9d  mov     ecx, ebp; Ix
0x18003aa9f  call    _o___acrt_iob_func_0
0x18003aaa4  mov     rcx, rax; Stream
0x18003aaa7  lea     rdx, Format; "Error: %s, %u: "
0x18003aaae  mov     r9d, r12d
0x18003aab1  mov     r8, rsi
0x18003aab4  call    fprintf
0x18003aab9  mov     ecx, ebp; Ix
0x18003aabb  call    _o___acrt_iob_func_0
0x18003aac0  mov     rcx, rax; Stream
0x18003aac3  mov     r8d, ebx
0x18003aac6  mov     rdx, r14; Format
0x18003aac9  call    fprintf
0x18003aace  mov     ecx, ebp; Ix
0x18003aad0  call    _o___acrt_iob_func_0
0x18003aad5  mov     rcx, rax; Stream
0x18003aad8  lea     rdx, asc_18011EAD8; "\n"
0x18003aadf  call    fprintf
0x18003aae4  cmp     cs:g_DeviceMapLogFunction, r13
0x18003aaeb  jz      short loc_18003AAFD
0x18003aaed  mov     r8d, ebx
0x18003aaf0  mov     rdx, r14
0x18003aaf3  mov     ecx, 2000000h
0x18003aaf8  call    TraceMessageCallback
0x18003aafd  mov     r9, r14
0x18003ab00  mov     [rsp+1B8h+var_198], ebx
0x18003ab04  mov     r8, r12
0x18003ab07  mov     rdx, rsi
0x18003ab0a  mov     ecx, r15d
0x18003ab0d  call    AslLogCallPrintf
0x18003ab12  jmp     loc_18003AE7C
0x18003ab17  mov     edx, 124F80h; dwMilliseconds
0x18003ab1c  mov     [rsp+1B8h+phModule], r13
0x18003ab21  mov     rcx, r12; hHandle
0x18003ab24  call    cs:__imp_WaitForSingleObject
0x18003ab2a  test    eax, eax
0x18003ab2c  jz      loc_18003AD90
0x18003ab32  mov     ecx, r15d
0x18003ab35  xchg    ecx, [rdi+8]; this
0x18003ab38  cmp     eax, 102h
0x18003ab3d  jz      loc_18003AC13
0x18003ab43  call    cs:__imp_GetLastError
0x18003ab49  mov     ebx, eax
0x18003ab4b  test    eax, eax
0x18003ab4d  jle     short loc_18003AB58
0x18003ab4f  movzx   ebx, ax
0x18003ab52  or      ebx, 80070000h
0x18003ab58  lea     r14, a0x08xFailedToG_1; "[0x%08x] Failed to generate device map"
0x18003ab5f  mov     [rsp+1B8h+var_198], ebx
0x18003ab63  lea     rsi, aCdevinventoryG_0; "CDevInventory::GetDeviceMap"
0x18003ab6a  mov     ebp, 2
0x18003ab6f  mov     r9, r14
0x18003ab72  mov     rdx, rsi
0x18003ab75  mov     ecx, ebp
0x18003ab77  mov     r8d, 505h
0x18003ab7d  mov     rdi, r13
0x18003ab80  call    AslLogCallPrintf
0x18003ab85  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003ab8c  jz      short loc_18003ABD8
0x18003ab8e  mov     ecx, ebp; Ix
0x18003ab90  call    _o___acrt_iob_func_0
0x18003ab95  mov     rcx, rax; Stream
0x18003ab98  lea     rdx, Format; "Error: %s, %u: "
0x18003ab9f  mov     r9d, 505h
0x18003aba5  mov     r8, rsi
0x18003aba8  call    fprintf
0x18003abad  mov     ecx, ebp; Ix
0x18003abaf  call    _o___acrt_iob_func_0
0x18003abb4  mov     rcx, rax; Stream
0x18003abb7  mov     r8d, ebx
0x18003abba  mov     rdx, r14; Format
0x18003abbd  call    fprintf
0x18003abc2  mov     ecx, ebp; Ix
0x18003abc4  call    _o___acrt_iob_func_0
0x18003abc9  mov     rcx, rax; Stream
0x18003abcc  lea     rdx, asc_18011EAD8; "\n"
0x18003abd3  call    fprintf
0x18003abd8  cmp     cs:g_DeviceMapLogFunction, r13
0x18003abdf  jz      short loc_18003ABF1
0x18003abe1  mov     r8d, ebx
0x18003abe4  mov     rdx, r14
0x18003abe7  mov     ecx, 2000000h
0x18003abec  call    TraceMessageCallback
0x18003abf1  mov     r9, r14
0x18003abf4  mov     [rsp+1B8h+var_198], ebx
0x18003abf8  mov     r8d, 505h
0x18003abfe  mov     rdx, rsi
0x18003ac01  mov     ecx, r15d
0x18003ac04  call    AslLogCallPrintf
0x18003ac09  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ac0e  jmp     loc_18003AE6E
0x18003ac13  mov     ebx, 80070102h
0x18003ac18  mov     rdi, r13
0x18003ac1b  call    ?ReportWatsonEvent@CDevInventory@@QEAAHXZ; CDevInventory::ReportWatsonEvent(void)
0x18003ac20  lea     rsi, aCdevinventoryG_0; "CDevInventory::GetDeviceMap"
0x18003ac27  mov     ebp, 2
0x18003ac2c  test    eax, eax
0x18003ac2e  jnz     loc_18003ACE4
0x18003ac34  lea     r14, aFailedToSendWa; "Failed to send Watson report [%#x]"
0x18003ac3b  mov     r15d, 80004005h
0x18003ac41  mov     r9, r14
0x18003ac44  mov     [rsp+1B8h+var_198], r15d
0x18003ac49  mov     r8d, 4F9h
0x18003ac4f  mov     rdx, rsi
0x18003ac52  mov     ecx, ebp
0x18003ac54  call    AslLogCallPrintf
0x18003ac59  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003ac60  jz      short loc_18003ACAC
0x18003ac62  mov     ecx, ebp; Ix
0x18003ac64  call    _o___acrt_iob_func_0
0x18003ac69  mov     rcx, rax; Stream
0x18003ac6c  lea     rdx, Format; "Error: %s, %u: "
0x18003ac73  mov     r9d, 4F9h
0x18003ac79  mov     r8, rsi
0x18003ac7c  call    fprintf
0x18003ac81  mov     ecx, ebp; Ix
0x18003ac83  call    _o___acrt_iob_func_0
0x18003ac88  mov     rcx, rax; Stream
0x18003ac8b  mov     r8d, r15d
0x18003ac8e  mov     rdx, r14; Format
0x18003ac91  call    fprintf
0x18003ac96  mov     ecx, ebp; Ix
0x18003ac98  call    _o___acrt_iob_func_0
0x18003ac9d  mov     rcx, rax; Stream
0x18003aca0  lea     rdx, asc_18011EAD8; "\n"
0x18003aca7  call    fprintf
0x18003acac  cmp     cs:g_DeviceMapLogFunction, r13
0x18003acb3  jz      short loc_18003ACC5
0x18003acb5  mov     r8d, r15d
0x18003acb8  mov     rdx, r14
0x18003acbb  mov     ecx, 2000000h
0x18003acc0  call    TraceMessageCallback
0x18003acc5  mov     [rsp+1B8h+var_198], r15d
0x18003acca  mov     r9, r14
0x18003accd  mov     r15d, 1
0x18003acd3  mov     r8d, 4F9h
0x18003acd9  mov     ecx, r15d
0x18003acdc  mov     rdx, rsi
0x18003acdf  call    AslLogCallPrintf
0x18003ace4  lea     r14, a0x08xFailedToG_1; "[0x%08x] Failed to generate device map"
0x18003aceb  mov     [rsp+1B8h+var_198], ebx
0x18003acef  mov     r9, r14
0x18003acf2  mov     r8d, 4FBh
0x18003acf8  mov     rdx, rsi
0x18003acfb  mov     ecx, ebp
0x18003acfd  call    AslLogCallPrintf
0x18003ad02  cmp     cs:EnableDevInvStdErrLog, r13d
0x18003ad09  jz      short loc_18003AD55
0x18003ad0b  mov     ecx, ebp; Ix
0x18003ad0d  call    _o___acrt_iob_func_0
0x18003ad12  mov     rcx, rax; Stream
0x18003ad15  lea     rdx, Format; "Error: %s, %u: "
0x18003ad1c  mov     r9d, 4FBh
0x18003ad22  mov     r8, rsi
0x18003ad25  call    fprintf
0x18003ad2a  mov     ecx, ebp; Ix
0x18003ad2c  call    _o___acrt_iob_func_0
0x18003ad31  mov     rcx, rax; Stream
0x18003ad34  mov     r8d, ebx
0x18003ad37  mov     rdx, r14; Format
0x18003ad3a  call    fprintf
0x18003ad3f  mov     ecx, ebp; Ix
0x18003ad41  call    _o___acrt_iob_func_0
0x18003ad46  mov     rcx, rax; Stream
0x18003ad49  lea     rdx, asc_18011EAD8; "\n"
0x18003ad50  call    fprintf
0x18003ad55  cmp     cs:g_DeviceMapLogFunction, r13
0x18003ad5c  jz      short loc_18003AD6E
0x18003ad5e  mov     r8d, ebx
0x18003ad61  mov     rdx, r14
0x18003ad64  mov     ecx, 2000000h
  ... truncated ...
```
