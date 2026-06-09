# CDevInventory::GetMemoryInfo(_SYSTEMSPECMEMORYINFO *)

- ea: `0x18003af48`
- end: `0x18003b559`
- name: `?GetMemoryInfo@CDevInventory@@SAJPEAU_SYSTEMSPECMEMORYINFO@@@Z`
- size: `1553`
- prototype: `__int64 __fastcall(struct _SYSTEMSPECMEMORYINFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180029efc`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180006ec4`
- `0x180006fb4`
- `0x180007014`
- `0x18000dcec`
- `0x180039d44`
- `0x18003af48`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b036`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b036`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b448`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003b448`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b05d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b05d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b1c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b1c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003afe6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003afe6`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18003b1b4`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18003b1b4`
- `OLEAUT32!__imp_VariantInit` at `0x18003b391`
- `OLEAUT32!__imp_VariantInit` at `0x18003b391`
- `OLEAUT32!__imp_VariantClear` at `0x18003b3fc`
- `OLEAUT32!__imp_VariantClear` at `0x18003b3fc`

## string_xrefs

- `0x18003b458`: `Failed getting path to system directory [%#x]`
- `0x18003affd`: `%ls\kernel32.dll`
- `0x18003b018`: `Failed getting path to system binary kernel32.dll [%#x]`
- `0x18003b044`: `Kernel32.dll could not be loaded; falling back to GlobalMemoryStatusEx.`
- `0x18003b053`: `GetPhysicallyInstalledSystemMemory`
- `0x18003b06c`: `GetPhysicallyInstalledSystemMemory API is not available; falling back to GlobalMemoryStatusEx.`
- `0x18003b127`: `GetPhysicallyInstalledSystemMemory failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDevInventory::GetMemoryInfo(struct _SYSTEMSPECMEMORYINFO *a1)
{
  int v2; // ebx
  const char *v3; // r14
  __int64 v4; // r15
  HMODULE Library; // rax
  HMODULE v6; // r15
  const char *v7; // rbx
  __int64 v8; // r13
  FARPROC ProcAddress; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  DWORDLONG ullTotalPhys; // rax
  DWORDLONG ullTotalVirtual; // rcx
  const char *v21; // r14
  __int64 v22; // r13
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  FILE *v28; // rax
  __int64 v30; // [rsp+20h] [rbp-E0h]
  __int64 v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  struct IEnumWbemClassObject *v35; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  _MEMORYSTATUSEX v39; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR LibFileName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v33 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  v34 = 0;
  memset_0(&v39, 0, sizeof(v39));
  v36 = 0;
  v35 = 0;
  v39.dwLength = 64;
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 4) = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    v2 = -2147467259;
    v3 = "Failed getting path to system directory [%#x]";
    v4 = 343;
    goto LABEL_51;
  }
  v2 = StringCchPrintfW(LibFileName, 0x104u, L"%ls\\kernel32.dll", Buffer);
  if ( v2 < 0 )
  {
    v3 = "Failed getting path to system binary kernel32.dll [%#x]";
    v4 = 350;
LABEL_51:
    AslLogCallPrintf(2, "CDevInventory::GetMemoryInfo", v4, v3, v2);
    if ( EnableDevInvStdErrLog )
    {
      v26 = o___acrt_iob_func_0(2u);
      fprintf(v26, "Error: %s, %u: ", "CDevInventory::GetMemoryInfo", v4);
      v27 = o___acrt_iob_func_0(2u);
      fprintf(v27, v3, (unsigned int)v2);
      v28 = o___acrt_iob_func_0(2u);
      fprintf(v28, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v3, (unsigned int)v2);
    LODWORD(v32) = v2;
    AslLogCallPrintf(1, "CDevInventory::GetMemoryInfo", v4, v3, v32);
    goto LABEL_56;
  }
  Library = LoadLibraryExW(LibFileName, 0, 0);
  v6 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetPhysicallyInstalledSystemMemory");
    if ( ProcAddress )
    {
      if ( !((unsigned int (__fastcall *)(__int64 *))ProcAddress)(&v34) )
      {
        v34 = 0;
        AslLogCallPrintf(2, "CDevInventory::GetMemoryInfo", 373, "GetPhysicallyInstalledSystemMemory failed.");
        if ( EnableDevInvStdErrLog )
        {
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "Warning: %s, %u: ", "CDevInventory::GetMemoryInfo", 373);
          v14 = o___acrt_iob_func_0(2u);
          fprintf(v14, "GetPhysicallyInstalledSystemMemory failed.");
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(50331648, "GetPhysicallyInstalledSystemMemory failed.");
      }
      *((_QWORD *)a1 + 3) = v34;
      goto LABEL_18;
    }
    v7 = "GetPhysicallyInstalledSystemMemory API is not available; falling back to GlobalMemoryStatusEx.";
    v8 = 366;
  }
  else
  {
    v7 = "Kernel32.dll could not be loaded; falling back to GlobalMemoryStatusEx.";
    v8 = 357;
  }
  AslLogCallPrintf(3, "CDevInventory::GetMemoryInfo", v8, v7);
  if ( EnableDevInvStdErrLog )
  {
    v10 = o___acrt_iob_func_0(2u);
    fprintf(v10, "Info: %s, %u: ", "CDevInventory::GetMemoryInfo", v8);
    v11 = o___acrt_iob_func_0(2u);
    fprintf(v11, v7);
    v12 = o___acrt_iob_func_0(2u);
    fprintf(v12, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, v7);
LABEL_18:
  if ( GlobalMemoryStatusEx(&v39) )
  {
    *(_QWORD *)a1 = v39.ullTotalPageFile;
    ullTotalPhys = *((_QWORD *)a1 + 1);
    if ( !ullTotalPhys )
    {
      ullTotalPhys = v39.ullTotalPhys;
      *((_QWORD *)a1 + 1) = v39.ullTotalPhys;
    }
    ullTotalVirtual = v39.ullTotalVirtual;
    *((_QWORD *)a1 + 2) = v39.ullTotalVirtual;
    if ( !*((_QWORD *)a1 + 3) )
      *((_QWORD *)a1 + 3) = ullTotalPhys >> 10;
    *((_QWORD *)a1 + 4) = ullTotalVirtual >> 10;
  }
  else
  {
    GetLastError();
    AslLogCallPrintf(2, "CDevInventory::GetMemoryInfo", 387, "GlobalMemoryStatusEx failed.");
    if ( EnableDevInvStdErrLog )
    {
      v16 = o___acrt_iob_func_0(2u);
      fprintf(v16, "Warning: %s, %u: ", "CDevInventory::GetMemoryInfo", 387);
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "GlobalMemoryStatusEx failed.");
      v18 = o___acrt_iob_func_0(2u);
      fprintf(v18, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(50331648, "GlobalMemoryStatusEx failed.");
  }
  if ( *((_QWORD *)a1 + 3) )
  {
LABEL_47:
    v2 = 0;
  }
  else
  {
    v2 = CDevInventory::ExecWmiQuery(&v35, L"select Capacity from Win32_PhysicalMemory");
    if ( v2 >= 0 )
    {
      do
      {
        v2 = ((__int64 (__fastcall *)(struct IEnumWbemClassObject *, __int64, __int64, __int64 *, int *))v35->lpVtbl->Next)(
               v35,
               3000,
               1,
               &v36,
               &v33);
        if ( v2 < 0 )
        {
          v21 = "[0x%08x] Failed to get Win32_PhysicalMemory";
          v22 = 430;
          goto LABEL_31;
        }
        if ( v33 )
        {
          v37 = 0;
          VariantInit(&pvarg);
          v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v36 + 32LL))(
                 v36,
                 L"Capacity",
                 0,
                 &pvarg,
                 0,
                 0);
          if ( v2 >= 0 && pvarg.vt == 8 && swscanf_s(pvarg.bstrVal, L"%I64u", &v37) > 0 )
            *((_QWORD *)a1 + 1) += v37;
          VariantClear(&pvarg);
        }
      }
      while ( !v2 );
      *((_QWORD *)a1 + 3) = *((_QWORD *)a1 + 1) >> 10;
      if ( *((_QWORD *)a1 + 1) >= 0x400u )
        goto LABEL_47;
      v2 = -2147467259;
    }
    else
    {
      v21 = "[0x%08x] ExecWmiQuery failed";
      v22 = 415;
LABEL_31:
      LODWORD(v30) = v2;
      AslLogCallPrintf(2, "CDevInventory::GetMemoryInfo", v22, v21, v30);
      if ( EnableDevInvStdErrLog )
      {
        v23 = o___acrt_iob_func_0(2u);
        fprintf(v23, "Error: %s, %u: ", "CDevInventory::GetMemoryInfo", v22);
        v24 = o___acrt_iob_func_0(2u);
        fprintf(v24, v21, (unsigned int)v2);
        v25 = o___acrt_iob_func_0(2u);
        fprintf(v25, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, v21, (unsigned int)v2);
      LODWORD(v31) = v2;
      AslLogCallPrintf(1, "CDevInventory::GetMemoryInfo", v22, v21, v31);
    }
  }
  if ( v6 )
    FreeLibrary(v6);
LABEL_56:
  if ( v35 )
    ((void (__fastcall *)(struct IEnumWbemClassObject *))v35->lpVtbl->Release)(v35);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003af48  push    rbp
0x18003af4a  push    rbx
0x18003af4b  push    rsi
0x18003af4c  push    rdi
0x18003af4d  push    r12
0x18003af4f  push    r13
0x18003af51  push    r14
0x18003af53  push    r15
0x18003af55  lea     rbp, [rsp-3F8h]
0x18003af5d  sub     rsp, 4F8h
0x18003af64  mov     rax, cs:__security_cookie
0x18003af6b  xor     rax, rsp
0x18003af6e  mov     [rbp+430h+var_50], rax
0x18003af75  mov     r14, rcx
0x18003af78  xor     r12d, r12d
0x18003af7b  mov     [rsp+530h+var_4F0], r12d
0x18003af80  mov     ebx, 208h
0x18003af85  mov     r8d, ebx; Size
0x18003af88  xor     edx, edx; Val
0x18003af8a  lea     rcx, [rbp+430h+Buffer]; void *
0x18003af8e  call    memset_0
0x18003af93  mov     r8d, ebx; Size
0x18003af96  xor     edx, edx; Val
0x18003af98  lea     rcx, [rbp+430h+LibFileName]; void *
0x18003af9f  call    memset_0
0x18003afa4  mov     [rsp+530h+var_4E8], r12
0x18003afa9  lea     ebx, [r12+40h]
0x18003afae  mov     r8d, ebx; Size
0x18003afb1  xor     edx, edx; Val
0x18003afb3  lea     rcx, [rbp+430h+var_4B0]; void *
0x18003afb7  call    memset_0
0x18003afbc  mov     [rsp+530h+var_4D8], r12
0x18003afc1  mov     [rsp+530h+var_4E0], r12
0x18003afc6  mov     [rbp+430h+var_4B0.dwLength], ebx
0x18003afc9  xorps   xmm0, xmm0
0x18003afcc  xor     eax, eax
0x18003afce  movups  xmmword ptr [r14], xmm0
0x18003afd2  movups  xmmword ptr [r14+10h], xmm0
0x18003afd7  mov     [r14+20h], rax
0x18003afdb  mov     ebx, 104h
0x18003afe0  mov     edx, ebx; uSize
0x18003afe2  lea     rcx, [rbp+430h+Buffer]; lpBuffer
0x18003afe6  call    cs:__imp_GetSystemDirectoryW
0x18003afec  dec     eax
0x18003afee  cmp     eax, 102h
0x18003aff3  ja      loc_18003B453
0x18003aff9  lea     r9, [rbp+430h+Buffer]
0x18003affd  lea     r8, aLsKernel32Dll; "%ls\\kernel32.dll"
0x18003b004  mov     edx, ebx; unsigned __int64
0x18003b006  lea     rcx, [rbp+430h+LibFileName]; unsigned __int16 *
0x18003b00d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b012  mov     ebx, eax
0x18003b014  test    eax, eax
0x18003b016  jns     short loc_18003B02A
0x18003b018  lea     r14, aFailedGettingP; "Failed getting path to system binary ke"...
0x18003b01f  mov     r15d, 15Eh
0x18003b025  jmp     loc_18003B465
0x18003b02a  xor     r8d, r8d; dwFlags
0x18003b02d  xor     edx, edx; hFile
0x18003b02f  lea     rcx, [rbp+430h+LibFileName]; lpLibFileName
0x18003b036  call    cs:__imp_LoadLibraryExW
0x18003b03c  mov     r15, rax
0x18003b03f  test    rax, rax
0x18003b042  jnz     short loc_18003B053
0x18003b044  lea     rbx, aKernel32DllCou; "Kernel32.dll could not be loaded; falli"...
0x18003b04b  mov     r13d, 165h
0x18003b051  jmp     short loc_18003B079
0x18003b053  lea     rdx, aGetphysicallyi; "GetPhysicallyInstalledSystemMemory"
0x18003b05a  mov     rcx, r15; hModule
0x18003b05d  call    cs:__imp_GetProcAddress
0x18003b063  test    rax, rax
0x18003b066  jnz     loc_18003B104
0x18003b06c  lea     rbx, aGetphysicallyi_0; "GetPhysicallyInstalledSystemMemory API "...
0x18003b073  mov     r13d, 16Eh
0x18003b079  lea     rdi, aCdevinventoryG; "CDevInventory::GetMemoryInfo"
0x18003b080  mov     r9, rbx
0x18003b083  mov     r8, r13
0x18003b086  mov     rdx, rdi
0x18003b089  mov     ecx, 3
0x18003b08e  call    AslLogCallPrintf
0x18003b093  cmp     cs:EnableDevInvStdErrLog, r12d
0x18003b09a  mov     esi, 2
0x18003b09f  jz      short loc_18003B0E5
0x18003b0a1  mov     ecx, esi; Ix
0x18003b0a3  call    _o___acrt_iob_func_0
0x18003b0a8  mov     rcx, rax; Stream
0x18003b0ab  mov     r9d, r13d
0x18003b0ae  mov     r8, rdi
0x18003b0b1  lea     rdx, aInfoSU; "Info: %s, %u: "
0x18003b0b8  call    fprintf
0x18003b0bd  mov     ecx, esi; Ix
0x18003b0bf  call    _o___acrt_iob_func_0
0x18003b0c4  mov     rcx, rax; Stream
0x18003b0c7  mov     rdx, rbx; Format
0x18003b0ca  call    fprintf
0x18003b0cf  mov     ecx, esi; Ix
0x18003b0d1  call    _o___acrt_iob_func_0
0x18003b0d6  mov     rcx, rax; Stream
0x18003b0d9  lea     rdx, asc_18011EAD8; "\n"
0x18003b0e0  call    fprintf
0x18003b0e5  cmp     cs:g_DeviceMapLogFunction, r12
0x18003b0ec  jz      loc_18003B1B0
0x18003b0f2  mov     rdx, rbx
0x18003b0f5  mov     ecx, 4000000h
0x18003b0fa  call    TraceMessageCallback
0x18003b0ff  jmp     loc_18003B1B0
0x18003b104  lea     rcx, [rsp+530h+var_4E8]
0x18003b109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b10e  lea     rdi, aCdevinventoryG; "CDevInventory::GetMemoryInfo"
0x18003b115  mov     esi, 2
0x18003b11a  test    eax, eax
0x18003b11c  jnz     loc_18003B1A7
0x18003b122  mov     [rsp+530h+var_4E8], r12
0x18003b127  lea     rbx, aGetphysicallyi_1; "GetPhysicallyInstalledSystemMemory fail"...
0x18003b12e  mov     r9, rbx
0x18003b131  mov     r13d, 175h
0x18003b137  mov     r8d, r13d
0x18003b13a  mov     rdx, rdi
0x18003b13d  mov     ecx, esi
0x18003b13f  call    AslLogCallPrintf
0x18003b144  cmp     cs:EnableDevInvStdErrLog, r12d
0x18003b14b  jz      short loc_18003B191
0x18003b14d  mov     ecx, esi; Ix
0x18003b14f  call    _o___acrt_iob_func_0
0x18003b154  mov     rcx, rax; Stream
0x18003b157  mov     r9d, r13d
0x18003b15a  mov     r8, rdi
0x18003b15d  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x18003b164  call    fprintf
0x18003b169  mov     ecx, esi; Ix
0x18003b16b  call    _o___acrt_iob_func_0
0x18003b170  mov     rcx, rax; Stream
0x18003b173  mov     rdx, rbx; Format
0x18003b176  call    fprintf
0x18003b17b  mov     ecx, esi; Ix
0x18003b17d  call    _o___acrt_iob_func_0
0x18003b182  mov     rcx, rax; Stream
0x18003b185  lea     rdx, asc_18011EAD8; "\n"
0x18003b18c  call    fprintf
0x18003b191  cmp     cs:g_DeviceMapLogFunction, r12
0x18003b198  jz      short loc_18003B1A7
0x18003b19a  mov     rdx, rbx
0x18003b19d  mov     ecx, 3000000h
0x18003b1a2  call    TraceMessageCallback
0x18003b1a7  mov     rax, [rsp+530h+var_4E8]
0x18003b1ac  mov     [r14+18h], rax
0x18003b1b0  lea     rcx, [rbp+430h+var_4B0]; lpBuffer
0x18003b1b4  call    cs:__imp_GlobalMemoryStatusEx
0x18003b1ba  test    eax, eax
0x18003b1bc  jnz     loc_18003B24A
0x18003b1c2  call    cs:__imp_GetLastError
0x18003b1c8  lea     rbx, aGlobalmemoryst; "GlobalMemoryStatusEx failed."
0x18003b1cf  mov     r9, rbx
0x18003b1d2  mov     r13d, 183h
0x18003b1d8  mov     r8d, r13d
0x18003b1db  mov     rdx, rdi
0x18003b1de  mov     ecx, esi
0x18003b1e0  call    AslLogCallPrintf
0x18003b1e5  cmp     cs:EnableDevInvStdErrLog, r12d
0x18003b1ec  jz      short loc_18003B232
0x18003b1ee  mov     ecx, esi; Ix
0x18003b1f0  call    _o___acrt_iob_func_0
0x18003b1f5  mov     rcx, rax; Stream
0x18003b1f8  mov     r9d, r13d
0x18003b1fb  mov     r8, rdi
0x18003b1fe  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x18003b205  call    fprintf
0x18003b20a  mov     ecx, esi; Ix
0x18003b20c  call    _o___acrt_iob_func_0
0x18003b211  mov     rcx, rax; Stream
0x18003b214  mov     rdx, rbx; Format
0x18003b217  call    fprintf
0x18003b21c  mov     ecx, esi; Ix
0x18003b21e  call    _o___acrt_iob_func_0
0x18003b223  mov     rcx, rax; Stream
0x18003b226  lea     rdx, asc_18011EAD8; "\n"
0x18003b22d  call    fprintf
0x18003b232  cmp     cs:g_DeviceMapLogFunction, r12
0x18003b239  jz      short loc_18003B280
0x18003b23b  mov     rdx, rbx
0x18003b23e  mov     ecx, 3000000h
0x18003b243  call    TraceMessageCallback
0x18003b248  jmp     short loc_18003B280
0x18003b24a  mov     rax, [rbp+430h+var_4B0.ullTotalPageFile]
0x18003b24e  mov     [r14], rax
0x18003b251  mov     rax, [r14+8]
0x18003b255  test    rax, rax
0x18003b258  jnz     short loc_18003B262
0x18003b25a  mov     rax, [rbp+430h+var_4B0.ullTotalPhys]
0x18003b25e  mov     [r14+8], rax
0x18003b262  mov     rcx, [rbp+430h+var_4B0.ullTotalVirtual]
0x18003b266  mov     [r14+10h], rcx
0x18003b26a  cmp     [r14+18h], r12
0x18003b26e  jnz     short loc_18003B278
0x18003b270  shr     rax, 0Ah
0x18003b274  mov     [r14+18h], rax
0x18003b278  shr     rcx, 0Ah
0x18003b27c  mov     [r14+20h], rcx
0x18003b280  cmp     [r14+18h], r12
0x18003b284  jnz     loc_18003B439
0x18003b28a  lea     rdx, aSelectCapacity; "select Capacity from Win32_PhysicalMemo"...
0x18003b291  lea     rcx, [rsp+530h+var_4E0]; struct IEnumWbemClassObject **
0x18003b296  call    ?ExecWmiQuery@CDevInventory@@SAJPEAPEAUIEnumWbemClassObject@@PEBG@Z; CDevInventory::ExecWmiQuery(IEnumWbemClassObject * *,ushort const *)
0x18003b29b  mov     ebx, eax
0x18003b29d  test    eax, eax
0x18003b29f  jns     loc_18003B34B
0x18003b2a5  lea     r14, a0x08xExecwmiqu; "[0x%08x] ExecWmiQuery failed"
0x18003b2ac  mov     r13d, 19Fh
0x18003b2b2  mov     dword ptr [rsp+530h+var_510], ebx
0x18003b2b6  mov     r9, r14
0x18003b2b9  mov     r8, r13
0x18003b2bc  mov     rdx, rdi
0x18003b2bf  mov     ecx, esi
0x18003b2c1  call    AslLogCallPrintf
0x18003b2c6  cmp     cs:EnableDevInvStdErrLog, r12d
0x18003b2cd  jz      short loc_18003B316
0x18003b2cf  mov     ecx, esi; Ix
0x18003b2d1  call    _o___acrt_iob_func_0
0x18003b2d6  mov     r9d, r13d
0x18003b2d9  mov     r8, rdi
0x18003b2dc  lea     rdx, Format; "Error: %s, %u: "
0x18003b2e3  mov     rcx, rax; Stream
0x18003b2e6  call    fprintf
0x18003b2eb  mov     ecx, esi; Ix
0x18003b2ed  call    _o___acrt_iob_func_0
0x18003b2f2  mov     r8d, ebx
0x18003b2f5  mov     rdx, r14; Format
0x18003b2f8  mov     rcx, rax; Stream
0x18003b2fb  call    fprintf
0x18003b300  mov     ecx, esi; Ix
0x18003b302  call    _o___acrt_iob_func_0
0x18003b307  lea     rdx, asc_18011EAD8; "\n"
0x18003b30e  mov     rcx, rax; Stream
0x18003b311  call    fprintf
0x18003b316  cmp     cs:g_DeviceMapLogFunction, r12
0x18003b31d  jz      short loc_18003B32F
0x18003b31f  mov     r8d, ebx
0x18003b322  mov     rdx, r14
0x18003b325  mov     ecx, 2000000h
0x18003b32a  call    TraceMessageCallback
0x18003b32f  mov     dword ptr [rsp+530h+var_510], ebx
0x18003b333  mov     r9, r14
0x18003b336  mov     r8, r13
0x18003b339  mov     rdx, rdi
0x18003b33c  mov     ecx, 1
0x18003b341  call    AslLogCallPrintf
0x18003b346  jmp     loc_18003B43C
0x18003b34b  mov     rcx, [rsp+530h+var_4E0]
0x18003b350  mov     rax, [rcx]
0x18003b353  lea     rdx, [rsp+530h+var_4F0]
0x18003b358  mov     [rsp+530h+var_510], rdx
0x18003b35d  lea     r9, [rsp+530h+var_4D8]
0x18003b362  mov     edx, 0BB8h
0x18003b367  mov     r8d, 1
0x18003b36d  mov     rax, [rax+20h]
0x18003b371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b376  mov     ebx, eax
0x18003b378  test    eax, eax
0x18003b37a  js      loc_18003B427
0x18003b380  cmp     [rsp+530h+var_4F0], r12d
0x18003b385  jbe     short loc_18003B402
0x18003b387  mov     [rsp+530h+var_4D0], r12
0x18003b38c  lea     rcx, [rsp+530h+pvarg]; pvarg
0x18003b391  call    cs:__imp_VariantInit
0x18003b397  nop
0x18003b398  mov     rcx, [rsp+530h+var_4D8]
0x18003b39d  mov     rax, [rcx]
0x18003b3a0  mov     [rsp+530h+var_508], r12
0x18003b3a5  mov     [rsp+530h+var_510], r12
0x18003b3aa  lea     r9, [rsp+530h+pvarg]
0x18003b3af  xor     r8d, r8d
0x18003b3b2  lea     rdx, aCapacity; "Capacity"
0x18003b3b9  mov     rax, [rax+20h]
0x18003b3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3c2  mov     ebx, eax
0x18003b3c4  test    eax, eax
0x18003b3c6  js      short loc_18003B3F7
0x18003b3c8  mov     eax, 8
0x18003b3cd  cmp     ax, word ptr [rsp+530h+pvarg]
0x18003b3d2  jnz     short loc_18003B3F7
0x18003b3d4  lea     r8, [rsp+530h+var_4D0]
0x18003b3d9  lea     rdx, aI64u; "%I64u"
0x18003b3e0  mov     rcx, qword ptr [rsp+530h+pvarg+8]; Buffer
0x18003b3e5  call    swscanf_s
0x18003b3ea  test    eax, eax
0x18003b3ec  jle     short loc_18003B3F7
0x18003b3ee  mov     rax, [rsp+530h+var_4D0]
0x18003b3f3  add     [r14+8], rax
0x18003b3f7  lea     rcx, [rsp+530h+pvarg]; pvarg
0x18003b3fc  call    cs:__imp_VariantClear
0x18003b402  test    ebx, ebx
0x18003b404  jz      loc_18003B34B
0x18003b40a  mov     rax, [r14+8]
0x18003b40e  shr     rax, 0Ah
0x18003b412  mov     [r14+18h], rax
0x18003b416  cmp     qword ptr [r14+8], 400h
0x18003b41e  jnb     short loc_18003B439
0x18003b420  mov     ebx, 80004005h
0x18003b425  jmp     short loc_18003B43C
0x18003b427  lea     r14, a0x08xFailedToG_0; "[0x%08x] Failed to get Win32_PhysicalMe"...
  ... truncated ...
```
