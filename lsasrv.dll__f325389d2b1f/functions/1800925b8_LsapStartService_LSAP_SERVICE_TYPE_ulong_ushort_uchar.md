# LsapStartService(LSAP_SERVICE_TYPE,ulong,ushort * *,uchar)

- ea: `0x1800925b8`
- end: `0x180092ca3`
- name: `?LsapStartService@@YAXW4LSAP_SERVICE_TYPE@@KPEAPEAGE@Z`
- size: `1771`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800b0f40`
- `0x1800f3480`
- `0x1800f34a0`
- `0x1800f34c0`
- `0x1800f3510`
- `0x1800f3530`
- `0x1800f3550`
- `0x1800f35c0`
- `0x1800f35e0`

## callees

- `0x18008e360`
- `0x180090278`
- `0x1800925b8`
- `0x180092cac`
- `0x180097c3c`
- `0x1800b3460`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800b9420`
- `0x1800f37d4`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180092a55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180092c15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180092a55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180092c15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180092880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800929d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180092880`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800929d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800927cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800927cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c28`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800929eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092956`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800929eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092b43`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009293e`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18009293e`
- `ntdll!RtlLeaveCriticalSection` at `0x180092c6c`
- `ntdll!RtlLeaveCriticalSection` at `0x180092c6c`
- `ntdll!RtlEnterCriticalSection` at `0x180092693`
- `ntdll!RtlEnterCriticalSection` at `0x180092693`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180092a86`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180092a86`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180092ae8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180092ae8`

## string_xrefs

- `0x180092740`: `System\CurrentControlSet\Services\%s\Parameters`
- `0x180092767`: `ServiceDll`

## pseudocode

```c
NTSTATUS __fastcall LsapStartService(int a1, unsigned int a2, __int64 a3, char a4)
{
  __int64 v4; // r15
  HMODULE Library; // r14
  struct _LSAP_SERVICE_TABLE *v8; // rdi
  unsigned __int64 v9; // rsi
  NTSTATUS v10; // eax
  int v11; // r12d
  LsaHandleCache *v12; // rcx
  LPCWSTR *v13; // rbx
  HKEY v14; // rcx
  int RegistryString; // eax
  const CHAR *v16; // rdx
  FARPROC v17; // r15
  signed int LastError; // eax
  int v19; // edx
  FARPROC ProcAddress; // r15
  int v21; // edx
  int v22; // r8d
  void (*v23)(void); // rax
  NTSTATUS result; // eax
  SERVICE_STATUS_HANDLE v25; // rcx
  char v26; // al
  int v27; // edx
  struct _RTL_CRITICAL_SECTION *v28; // rcx
  unsigned int v31; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  struct _LSAP_SERVICE_TABLE *v33; // [rsp+50h] [rbp-B0h]
  _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR LibFileName[264]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[264]; // [rsp+290h] [rbp+190h] BYREF

  v4 = a1;
  memset_0(Buffer, 0, 0x208u);
  memset_0(LibFileName, 0, 0x208u);
  v31 = 520;
  Library = 0;
  v8 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v33 = 0;
  v32 = 0;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
      *(&g_LsaServiceTable + 14 * v4 + 2));
  }
  v9 = 112 * v4;
  v10 = RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(&g_LsaServiceTable + 14 * v4 + 9));
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
        *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 16));
    }
    v13 = (LPCWSTR *)&(&off_1801997F0)[v9 / 8];
    swprintf_s(Buffer, 0x104u, L"System\\CurrentControlSet\\Services\\%s\\Parameters", (&off_1801997F0)[v9 / 8]);
    RegistryString = GetRegistryString(v14, Buffer, L"ServiceDll", LibFileName, &v31);
    if ( RegistryString < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
          (unsigned int)*v13,
          RegistryString);
      }
      goto LABEL_47;
    }
    Library = LoadLibraryExW(LibFileName, 0, 0);
    if ( !Library )
    {
      LODWORD(v8) = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
          (unsigned int)LibFileName,
          (char)v8);
      }
      goto LABEL_47;
    }
    if ( *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 24) )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, *v13);
      }
      (*(void (__fastcall **)(HMODULE))((char *)&g_LsaServiceTable + v9 + 24))(Library);
    }
    v16 = *(const CHAR **)((char *)&g_LsaServiceTable + v9 + 8);
    if ( v16 && (v17 = GetProcAddress(Library, v16)) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, *v13);
      }
      LastError = ((__int64 (__fastcall *)(_QWORD, __int64, __int128 *))v17)(a2, a3, &v32);
      if ( LastError < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
        {
          goto LABEL_46;
        }
        v19 = 21;
        goto LABEL_38;
      }
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, *v13);
      }
      v8 = (struct _LSAP_SERVICE_TABLE *)RegisterWaitForSingleObjectEx(
                                           *((_QWORD *)&v32 + 1),
                                           LsapServiceStopCallback,
                                           (char *)&g_LsaServiceTable + v9,
                                           0xFFFFFFFFLL,
                                           24);
      if ( !v8 )
      {
        LastError = GetLastError();
        LODWORD(v8) = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
        {
          goto LABEL_46;
        }
        v19 = 22;
LABEL_38:
        WPP_SF_Sd(
          *((_QWORD *)v12 + 2),
          v19,
          (unsigned int)&WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
          (unsigned int)*v13,
          LastError);
LABEL_46:
        LODWORD(v4) = a1;
LABEL_47:
        v11 = 1;
        goto LABEL_48;
      }
    }
    else
    {
      ProcAddress = GetProcAddress(Library, *(LPCSTR *)((char *)&g_LsaServiceTable + v9));
      if ( !ProcAddress )
      {
        LODWORD(v8) = GetLastError();
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF_sl(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            v22,
            (unsigned int)*(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9),
            (char)v8);
        }
        goto LABEL_46;
      }
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, *v13);
      }
      ((void (__fastcall *)(_QWORD, __int64))ProcAddress)(a2, a3);
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids, *v13);
      }
    }
    if ( a4 )
      FreeLibrary(Library);
    EnterCriticalSection(&ServicesListLock);
    *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 64) = (struct _LSAP_SERVICE_TABLE near *)v32;
    *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 56) = v33;
    *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 40) = (struct _LSAP_SERVICE_TABLE near *)Library;
    *(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 48) = v8;
    LeaveCriticalSection(&ServicesListLock);
    v28 = (struct _RTL_CRITICAL_SECTION *)((char *)&g_LsaServiceTable + v9 + 72);
    return RtlLeaveCriticalSection(v28);
  }
  v11 = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)&WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
      (unsigned int)*(struct _LSAP_SERVICE_TABLE near **)((char *)&g_LsaServiceTable + v9 + 16),
      v10);
  }
  v13 = (LPCWSTR *)((char *)&g_LsaServiceTable + v9 + 16);
LABEL_48:
  v23 = *(void (**)(void))((char *)&g_LsaServiceTable + v9 + 32);
  if ( v23 )
    v23();
  if ( Library )
    FreeLibrary(Library);
  if ( Ntlmless::LocalKdc::IsEnabled(v12) )
  {
    result = LsapSetServiceStopped((unsigned int)v4, (unsigned int)v8);
  }
  else
  {
    v25 = RegisterServiceCtrlHandlerW(*v13, DummyControlHandler);
    if ( v25 )
    {
      ServiceStatus.dwServiceType = 48;
      ServiceStatus.dwCurrentState = 1;
      ServiceStatus.dwControlsAccepted = 3;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      if ( (_DWORD)v8 )
      {
        ServiceStatus.dwServiceSpecificExitCode = (unsigned int)v8;
        ServiceStatus.dwWin32ExitCode = 1066;
        if ( (unsigned int)((_DWORD)v8 - 2100) > 0xED7 )
          ServiceStatus.dwWin32ExitCode = (unsigned int)v8;
      }
      else
      {
        *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
      }
      result = SetServiceStatus(v25, &ServiceStatus);
      if ( result )
        goto LABEL_67;
      result = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
      {
        goto LABEL_67;
      }
      v26 = GetLastError();
      v27 = 26;
    }
    else
    {
      result = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) == 0 )
      {
        goto LABEL_67;
      }
      v26 = GetLastError();
      v27 = 27;
    }
    result = WPP_SF_Sd(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               v27,
               (unsigned int)&WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids,
               (unsigned int)*v13,
               v26);
  }
LABEL_67:
  if ( !v11 )
    return result;
  v28 = (struct _RTL_CRITICAL_SECTION *)&qword_1801997F8[v9 / 8 + 6];
  return RtlLeaveCriticalSection(v28);
}

```

## disassembly

```asm
0x1800925b8  mov     [rsp-8+arg_18], rbx
0x1800925bd  push    rbp
0x1800925be  push    rsi
0x1800925bf  push    rdi
0x1800925c0  push    r12
0x1800925c2  push    r13
0x1800925c4  push    r14
0x1800925c6  push    r15
0x1800925c8  lea     rbp, [rsp-3B0h]
0x1800925d0  sub     rsp, 4B0h
0x1800925d7  mov     rax, cs:__security_cookie
0x1800925de  xor     rax, rsp
0x1800925e1  mov     [rbp+3E0h+var_40], rax
0x1800925e8  movsxd  r15, ecx
0x1800925eb  mov     r13, r8
0x1800925ee  mov     r12d, edx
0x1800925f1  mov     [rsp+4E0h+var_4B0], r9b
0x1800925f6  mov     ebx, 208h
0x1800925fb  mov     [rsp+4E0h+var_4A8], r15d
0x180092600  mov     r8d, ebx; Size
0x180092603  lea     rcx, [rbp+3E0h+Buffer]; void *
0x18009260a  xor     edx, edx; Val
0x18009260c  call    memset_0
0x180092611  mov     r8d, ebx; Size
0x180092614  lea     rcx, [rbp+3E0h+LibFileName]; void *
0x180092618  xor     edx, edx; Val
0x18009261a  call    memset_0
0x18009261f  xorps   xmm0, xmm0
0x180092622  mov     [rsp+4E0h+var_4A4], ebx
0x180092626  xor     r14d, r14d
0x180092629  xor     edi, edi
0x18009262b  xor     eax, eax
0x18009262d  movups  xmmword ptr [rsp+4E0h+ServiceStatus.dwServiceType], xmm0
0x180092632  mov     [rsp+4E0h+var_490], rax
0x180092637  movups  xmmword ptr [rsp+4E0h+ServiceStatus.dwWin32ExitCode], xmm0
0x18009263c  movups  [rsp+4E0h+var_4A0], xmm0
0x180092641  mov     rcx, cs:WPP_GLOBAL_Control
0x180092648  lea     rax, WPP_GLOBAL_Control
0x18009264f  lea     r8, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092656  mov     ebx, 8000000h
0x18009265b  cmp     rcx, rax
0x18009265e  jz      short loc_180092688
0x180092660  test    [rcx+1Ch], ebx
0x180092663  jz      short loc_180092688
0x180092665  mov     rcx, [rcx+10h]
0x180092669  lea     edx, [rdi+0Dh]
0x18009266c  imul    r9, r15, 70h ; 'p'
0x180092670  mov     r9, [r9+r8+10h]
0x180092675  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x18009267c  call    WPP_SF_S
0x180092681  lea     r8, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092688  imul    rsi, r15, 70h ; 'p'
0x18009268c  lea     rcx, [rsi+48h]
0x180092690  add     rcx, r8; CriticalSection
0x180092693  call    cs:__imp_RtlEnterCriticalSection
0x18009269a  nop     dword ptr [rax+rax+00h]
0x18009269f  test    eax, eax
0x1800926a1  jns     short loc_1800926EF
0x1800926a3  xor     r12d, r12d
0x1800926a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800926ad  lea     rdx, WPP_GLOBAL_Control
0x1800926b4  lea     r13, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x1800926bb  cmp     rcx, rdx
0x1800926be  jz      short loc_1800926E3
0x1800926c0  test    [rcx+1Ch], ebx
0x1800926c3  jz      short loc_1800926E3
0x1800926c5  mov     r9, [rsi+r13+10h]
0x1800926ca  lea     edx, [r12+0Eh]
0x1800926cf  mov     rcx, [rcx+10h]
0x1800926d3  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x1800926da  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x1800926de  call    WPP_SF_Sd
0x1800926e3  lea     rbx, [rsi+10h]
0x1800926e7  add     rbx, r13
0x1800926ea  jmp     loc_180092A3E
0x1800926ef  mov     [rsp+4E0h+var_4AC], 1
0x1800926f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800926fe  lea     rax, WPP_GLOBAL_Control
0x180092705  cmp     rcx, rax
0x180092708  jz      short loc_180092730
0x18009270a  test    [rcx+1Ch], ebx
0x18009270d  jz      short loc_180092730
0x18009270f  mov     rcx, [rcx+10h]
0x180092713  lea     rax, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x18009271a  mov     r9, [rsi+rax+10h]
0x18009271f  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x180092726  mov     edx, 0Fh
0x18009272b  call    WPP_SF_S
0x180092730  lea     rbx, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092737  mov     edx, 104h; BufferCount
0x18009273c  add     rbx, 10h
0x180092740  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\%s"...
0x180092747  add     rbx, rsi
0x18009274a  lea     rcx, [rbp+3E0h+Buffer]; Buffer
0x180092751  mov     r9, [rbx]
0x180092754  call    swprintf_s
0x180092759  lea     rax, [rsp+4E0h+var_4A4]
0x18009275e  lea     r9, [rbp+3E0h+LibFileName]; unsigned __int16 *
0x180092762  mov     [rsp+4E0h+var_4C0], rax; unsigned int *
0x180092767  lea     r8, aServicedll; "ServiceDll"
0x18009276e  lea     rdx, [rbp+3E0h+Buffer]; unsigned __int16 *
0x180092775  call    ?GetRegistryString@@YAJPEAUHKEY__@@PEAG11PEAK@Z; GetRegistryString(HKEY__ *,ushort *,ushort *,ushort *,ulong *)
0x18009277a  test    eax, eax
0x18009277c  jns     short loc_1800927C3
0x18009277e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092785  lea     rdx, WPP_GLOBAL_Control
0x18009278c  cmp     rcx, rdx
0x18009278f  jz      loc_180092A32
0x180092795  test    dword ptr [rcx+1Ch], 8000000h
0x18009279c  jz      loc_180092A32
0x1800927a2  mov     r9, [rbx]
0x1800927a5  mov     edx, 10h
0x1800927aa  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x1800927ae  mov     rcx, [rcx+10h]
0x1800927b2  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x1800927b9  call    WPP_SF_Sd
0x1800927be  jmp     loc_180092A32
0x1800927c3  xor     r8d, r8d; dwFlags
0x1800927c6  lea     rcx, [rbp+3E0h+LibFileName]; lpLibFileName
0x1800927ca  xor     edx, edx; hFile
0x1800927cc  call    cs:__imp_LoadLibraryExW
0x1800927d3  nop     dword ptr [rax+rax+00h]
0x1800927d8  mov     r14, rax
0x1800927db  test    rax, rax
0x1800927de  jnz     short loc_180092820
0x1800927e0  call    cs:__imp_GetLastError
0x1800927e7  nop     dword ptr [rax+rax+00h]
0x1800927ec  mov     edi, eax
0x1800927ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800927f5  lea     rax, WPP_GLOBAL_Control
0x1800927fc  cmp     rcx, rax
0x1800927ff  jz      loc_180092A32
0x180092805  test    dword ptr [rcx+1Ch], 8000000h
0x18009280c  jz      loc_180092A32
0x180092812  lea     edx, [r14+11h]
0x180092816  mov     dword ptr [rsp+4E0h+var_4C0], edi
0x18009281a  lea     r9, [rbp+3E0h+LibFileName]
0x18009281e  jmp     short loc_1800927AE
0x180092820  lea     r15, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092827  cmp     [rsi+r15+18h], rdi
0x18009282c  jz      short loc_18009286F
0x18009282e  mov     rcx, cs:WPP_GLOBAL_Control
0x180092835  lea     rax, WPP_GLOBAL_Control
0x18009283c  cmp     rcx, rax
0x18009283f  jz      short loc_180092862
0x180092841  test    dword ptr [rcx+1Ch], 8000000h
0x180092848  jz      short loc_180092862
0x18009284a  mov     r9, [rbx]
0x18009284d  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x180092854  mov     rcx, [rcx+10h]
0x180092858  mov     edx, 12h
0x18009285d  call    WPP_SF_S
0x180092862  mov     rax, [rsi+r15+18h]
0x180092867  mov     rcx, r14
0x18009286a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009286f  mov     rdx, [rsi+r15+8]; lpProcName
0x180092874  test    rdx, rdx
0x180092877  jz      loc_1800929CC
0x18009287d  mov     rcx, r14; hModule
0x180092880  call    cs:__imp_GetProcAddress
0x180092887  nop     dword ptr [rax+rax+00h]
0x18009288c  mov     r15, rax
0x18009288f  test    rax, rax
0x180092892  jz      loc_1800929C5
0x180092898  mov     rcx, cs:WPP_GLOBAL_Control
0x18009289f  lea     rax, WPP_GLOBAL_Control
0x1800928a6  cmp     rcx, rax
0x1800928a9  jz      short loc_1800928CC
0x1800928ab  test    dword ptr [rcx+1Ch], 8000000h
0x1800928b2  jz      short loc_1800928CC
0x1800928b4  mov     r9, [rbx]
0x1800928b7  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x1800928be  mov     rcx, [rcx+10h]
0x1800928c2  mov     edx, 13h
0x1800928c7  call    WPP_SF_S
0x1800928cc  lea     r8, [rsp+4E0h+var_4A0]
0x1800928d1  mov     rdx, r13
0x1800928d4  mov     ecx, r12d
0x1800928d7  mov     rax, r15
0x1800928da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800928df  test    eax, eax
0x1800928e1  js      loc_1800929A2
0x1800928e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800928ee  lea     r12, WPP_GLOBAL_Control
0x1800928f5  cmp     rcx, r12
0x1800928f8  jz      short loc_18009291B
0x1800928fa  test    dword ptr [rcx+1Ch], 8000000h
0x180092901  jz      short loc_18009291B
0x180092903  mov     r9, [rbx]
0x180092906  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x18009290d  mov     rcx, [rcx+10h]
0x180092911  mov     edx, 14h
0x180092916  call    WPP_SF_S
0x18009291b  mov     rcx, qword ptr [rsp+4E0h+var_4A0+8]
0x180092920  lea     r15, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092927  lea     r8, [rsi+r15]
0x18009292b  mov     dword ptr [rsp+4E0h+var_4C0], 18h
0x180092933  or      r9d, 0FFFFFFFFh
0x180092937  lea     rdx, ?LsapServiceStopCallback@@YAXPEAXE@Z; LsapServiceStopCallback(void *,uchar)
0x18009293e  call    cs:__imp_RegisterWaitForSingleObjectEx
0x180092945  nop     dword ptr [rax+rax+00h]
0x18009294a  mov     rdi, rax
0x18009294d  test    rax, rax
0x180092950  jnz     loc_180092C0B
0x180092956  call    cs:__imp_GetLastError
0x18009295d  nop     dword ptr [rax+rax+00h]
0x180092962  mov     edi, eax
0x180092964  mov     rcx, cs:WPP_GLOBAL_Control
0x18009296b  cmp     rcx, r12
0x18009296e  jz      loc_180092A2D
0x180092974  test    dword ptr [rcx+1Ch], 8000000h
0x18009297b  jz      loc_180092A2D
0x180092981  mov     edx, 16h
0x180092986  mov     r9, [rbx]
0x180092989  lea     r8, WPP_78ab6bf705d936786f4c83bd991115a5_Traceguids
0x180092990  mov     rcx, [rcx+10h]
0x180092994  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x180092998  call    WPP_SF_Sd
0x18009299d  jmp     loc_180092A2D
0x1800929a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800929a9  lea     rdx, WPP_GLOBAL_Control
0x1800929b0  cmp     rcx, rdx
0x1800929b3  jz      short loc_180092A2D
0x1800929b5  test    dword ptr [rcx+1Ch], 8000000h
0x1800929bc  jz      short loc_180092A2D
0x1800929be  mov     edx, 15h
0x1800929c3  jmp     short loc_180092986
0x1800929c5  lea     r15, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x1800929cc  mov     rdx, [rsi+r15]; lpProcName
0x1800929d0  mov     rcx, r14; hModule
0x1800929d3  call    cs:__imp_GetProcAddress
0x1800929da  nop     dword ptr [rax+rax+00h]
0x1800929df  mov     r15, rax
0x1800929e2  test    rax, rax
0x1800929e5  jnz     loc_180092B8E
0x1800929eb  call    cs:__imp_GetLastError
0x1800929f2  nop     dword ptr [rax+rax+00h]
0x1800929f7  mov     edi, eax
0x1800929f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180092a00  lea     rax, WPP_GLOBAL_Control
0x180092a07  cmp     rcx, rax
0x180092a0a  jz      short loc_180092A2D
0x180092a0c  test    dword ptr [rcx+1Ch], 8000000h
0x180092a13  jz      short loc_180092A2D
0x180092a15  mov     rcx, [rcx+10h]
0x180092a19  lea     rax, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092a20  mov     r9, [rsi+rax]
0x180092a24  mov     dword ptr [rsp+4E0h+var_4C0], edi
0x180092a28  call    WPP_SF_sl
0x180092a2d  mov     r15d, [rsp+4E0h+var_4A8]
0x180092a32  mov     r12d, [rsp+4E0h+var_4AC]
0x180092a37  lea     r13, ?g_LsaServiceTable@@3PAU_LSAP_SERVICE_TABLE@@A; _LSAP_SERVICE_TABLE near * g_LsaServiceTable
0x180092a3e  mov     rax, [rsi+r13+20h]
0x180092a43  test    rax, rax
0x180092a46  jz      short loc_180092A4D
0x180092a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092a4d  test    r14, r14
0x180092a50  jz      short loc_180092A61
0x180092a52  mov     rcx, r14; hLibModule
0x180092a55  call    cs:__imp_FreeLibrary
0x180092a5c  nop     dword ptr [rax+rax+00h]
0x180092a61  call    ?IsEnabled@LocalKdc@Ntlmless@@YA_NXZ; Ntlmless::LocalKdc::IsEnabled(void)
0x180092a66  xor     r14d, r14d
0x180092a69  test    al, al
0x180092a6b  jz      short loc_180092A7C
0x180092a6d  mov     edx, edi
0x180092a6f  mov     ecx, r15d
0x180092a72  call    ?LsapSetServiceStopped@@YAXW4LSAP_SERVICE_TYPE@@K@Z; LsapSetServiceStopped(LSAP_SERVICE_TYPE,ulong)
0x180092a77  jmp     loc_180092B72
0x180092a7c  mov     rcx, [rbx]; lpServiceName
0x180092a7f  lea     rdx, ?DummyControlHandler@@YAXK@Z; lpHandlerProc
0x180092a86  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180092a8d  nop     dword ptr [rax+rax+00h]
0x180092a92  mov     rcx, rax; hServiceStatus
0x180092a95  test    rax, rax
0x180092a98  jz      loc_180092B27
0x180092a9e  mov     [rsp+4E0h+ServiceStatus.dwServiceType], 30h ; '0'
0x180092aa6  mov     [rsp+4E0h+ServiceStatus.dwCurrentState], 1
0x180092aae  mov     [rsp+4E0h+ServiceStatus.dwControlsAccepted], 3
0x180092ab6  mov     qword ptr [rsp+4E0h+ServiceStatus.dwCheckPoint], r14
0x180092abb  test    edi, edi
0x180092abd  jnz     short loc_180092AC6
0x180092abf  mov     qword ptr [rsp+4E0h+ServiceStatus.dwWin32ExitCode], r14
0x180092ac4  jmp     short loc_180092AE3
0x180092ac6  lea     eax, [rdi-834h]
0x180092acc  mov     [rsp+4E0h+ServiceStatus.dwServiceSpecificExitCode], edi
0x180092ad0  mov     [rsp+4E0h+ServiceStatus.dwWin32ExitCode], 42Ah
0x180092ad8  cmp     eax, 0ED7h
0x180092add  jbe     short loc_180092AE3
0x180092adf  mov     [rsp+4E0h+ServiceStatus.dwWin32ExitCode], edi
0x180092ae3  lea     rdx, [rsp+4E0h+ServiceStatus]; lpServiceStatus
0x180092ae8  call    cs:__imp_SetServiceStatus
0x180092aef  nop     dword ptr [rax+rax+00h]
0x180092af4  test    eax, eax
0x180092af6  jnz     short loc_180092B72
0x180092af8  mov     rax, cs:WPP_GLOBAL_Control
0x180092aff  lea     rcx, WPP_GLOBAL_Control
0x180092b06  cmp     rax, rcx
0x180092b09  jz      short loc_180092B72
0x180092b0b  test    dword ptr [rax+1Ch], 8000000h
  ... truncated ...
```
