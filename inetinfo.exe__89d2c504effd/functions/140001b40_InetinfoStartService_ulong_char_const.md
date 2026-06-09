# InetinfoStartService(ulong,char * * const)

- ea: `0x140001b40`
- end: `0x140001f4e`
- name: `?InetinfoStartService@@YAXKQEAPEAD@Z`
- size: `1038`
- prototype: `void __fastcall(unsigned int, LPCSTR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x140001808`
- `0x14000193c`
- `0x140001b40`
- `0x140002826`
- `0x140002850`
- `0x140003010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140001bd6`
- `KERNEL32!SetLastError` at `0x140001bd6`
- `KERNEL32!EnterCriticalSection` at `0x140001c5a`
- `KERNEL32!EnterCriticalSection` at `0x140001c5a`
- `KERNEL32!LoadLibraryExA` at `0x140001d0a`
- `KERNEL32!LoadLibraryExA` at `0x140001d0a`
- `KERNEL32!LeaveCriticalSection` at `0x140001d99`
- `KERNEL32!LeaveCriticalSection` at `0x140001e50`
- `KERNEL32!LeaveCriticalSection` at `0x140001d99`
- `KERNEL32!LeaveCriticalSection` at `0x140001e50`
- `KERNEL32!Sleep` at `0x140001e5b`
- `KERNEL32!Sleep` at `0x140001e5b`
- `KERNEL32!GetLastError` at `0x140001d1c`
- `KERNEL32!GetLastError` at `0x140001db9`
- `KERNEL32!GetLastError` at `0x140001e72`
- `KERNEL32!GetLastError` at `0x140001d1c`
- `KERNEL32!GetLastError` at `0x140001db9`
- `KERNEL32!GetLastError` at `0x140001e72`
- `KERNEL32!GetProcAddress` at `0x140001dae`
- `KERNEL32!GetProcAddress` at `0x140001dae`
- `KERNEL32!FreeLibrary` at `0x140001e64`
- `KERNEL32!FreeLibrary` at `0x140001e64`
- `KERNEL32!lstrcmpiA` at `0x140001bbb`
- `KERNEL32!lstrcmpiA` at `0x140001bbb`
- `msvcrt!sprintf_s` at `0x140001c10`
- `msvcrt!sprintf_s` at `0x140001cbe`
- `msvcrt!sprintf_s` at `0x140001d3d`
- `msvcrt!sprintf_s` at `0x140001de3`
- `msvcrt!sprintf_s` at `0x140001e90`
- `msvcrt!sprintf_s` at `0x140001ee8`
- `msvcrt!sprintf_s` at `0x140001c10`
- `msvcrt!sprintf_s` at `0x140001cbe`
- `msvcrt!sprintf_s` at `0x140001d3d`
- `msvcrt!sprintf_s` at `0x140001de3`
- `msvcrt!sprintf_s` at `0x140001e90`
- `msvcrt!sprintf_s` at `0x140001ee8`
- `msvcrt!strcat_s` at `0x140001c9d`
- `msvcrt!strcat_s` at `0x140001c9d`
- `msvcrt!strcpy_s` at `0x140001c8a`
- `msvcrt!strcpy_s` at `0x140001c8a`
- `iisutil!PuDbgPrint` at `0x140001cea`
- `iisutil!PuDbgPrint` at `0x140001d71`
- `iisutil!PuDbgPrint` at `0x140001e17`
- `iisutil!PuDbgPrint` at `0x140001ec8`
- `iisutil!PuDbgPrint` at `0x140001f14`
- `iisutil!PuDbgPrint` at `0x140001cea`
- `iisutil!PuDbgPrint` at `0x140001d71`
- `iisutil!PuDbgPrint` at `0x140001e17`
- `iisutil!PuDbgPrint` at `0x140001ec8`
- `iisutil!PuDbgPrint` at `0x140001f14`

## string_xrefs

- `0x140001bff`: `Service %s has path set in registry.  Assuming %s\n`
- `0x140001b8f`: `InetinfoStartService`
- `0x140001d58`: `InetinfoStartService`
- `0x140001dfe`: `InetinfoStartService`
- `0x140001eaf`: `InetinfoStartService`
- `0x140001caa`: `Service %s not on primary list.  Assuming %s\n`
- `0x140001ed5`: `Inetinfo: Failed To Find Dll For %s : %ld\n`
- `0x140001d25`: `Inetinfo: Failed to load DLL %s: %ld\n`
- `0x140001da4`: `ServiceEntry`
- `0x140001dc3`: `ServiceEntry`
- `0x140001dd4`: `Inetinfo: Can't find entry %s in DLL %s: %ld\n`
- `0x140001e7b`: `INETSVCS: Can't unload DLL %s: %ld\n`

## pseudocode

```c
void __fastcall InetinfoStartService(unsigned int a1, LPCSTR *a2)
{
  const CHAR *v3; // rax
  const CHAR *v4; // rdi
  const CHAR **v5; // rbx
  unsigned int v6; // r8d
  __int64 v7; // rbx
  int DLLNameForDispatchEntryService; // eax
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // r15
  __int64 v12; // r12
  char *v13; // rdi
  unsigned __int64 v14; // rax
  HMODULE Library; // rax
  HMODULE v16; // r13
  DWORD v17; // r12d
  FARPROC ProcAddress; // rax
  DWORD LastError; // r15d
  DWORD v20; // eax
  char Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF
  char Destination[272]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(Destination, 0, 0x105u);
  v3 = InetServiceDispatchTable;
  if ( InetServiceDispatchTable )
  {
    v4 = *a2;
    v5 = &InetServiceDispatchTable;
    while ( lstrcmpiA(v3, v4) )
    {
      v5 += 2;
      v3 = *v5;
      if ( !*v5 )
        goto LABEL_5;
    }
    v7 = ((char *)v5 - (char *)&InetServiceDispatchTable) >> 4;
    if ( (_DWORD)v7 != -1 )
    {
      v11 = (unsigned int)v7;
      v12 = 7LL * (unsigned int)v7;
      v13 = *(char **)((char *)&InetServiceDllTable + v12 * 8 + 8);
      EnterCriticalSection((LPCRITICAL_SECTION)&qword_140006050[v12]);
      goto LABEL_18;
    }
  }
  else
  {
LABEL_5:
    SetLastError(0x57u);
    LODWORD(v7) = -1;
  }
  DLLNameForDispatchEntryService = GetDLLNameForDispatchEntryService(*a2, (LPBYTE)Destination, v6);
  v9 = *a2;
  if ( DLLNameForDispatchEntryService )
  {
    sprintf_s(Buffer, 0x100u, "Service %s has path set in registry.  Assuming %s\n", v9, Destination);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v10 = 490;
LABEL_16:
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx", v10, "InetinfoStartService", Buffer);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  v14 = -1;
  do
    ++v14;
  while ( v9[v14] );
  if ( v14 < 0x100 )
  {
    strcpy_s(Destination, 0x105u, *a2);
    strcat_s(Destination, 0x105u, ".dll");
    sprintf_s(Buffer, 0x100u, "Service %s not on primary list.  Assuming %s\n", *a2, Destination);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v10 = 499;
      goto LABEL_16;
    }
LABEL_17:
    v13 = Destination;
    v11 = 0xFFFFFFFFLL;
    v12 = 0x6FFFFFFF9LL;
LABEL_18:
    Library = LoadLibraryExA(v13, 0, 8u);
    v16 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "ServiceEntry");
      if ( ProcAddress )
      {
        ((void (__fastcall *)(_QWORD, LPCSTR *, void *))ProcAddress)(a1, a2, &InetinfoGlobalData);
      }
      else
      {
        LastError = GetLastError();
        sprintf_s(Buffer, 0x100u, "Inetinfo: Can't find entry %s in DLL %s: %ld\n", "ServiceEntry", v13, LastError);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
            558,
            "InetinfoStartService",
            Buffer);
        AbortService((char *)*a2, LastError);
      }
      if ( (_DWORD)v7 != -1 )
        LeaveCriticalSection((LPCRITICAL_SECTION)&qword_140006050[v12]);
      Sleep(0x1F4u);
      if ( !FreeLibrary(v16) )
      {
        v20 = GetLastError();
        sprintf_s(Buffer, 0x100u, "INETSVCS: Can't unload DLL %s: %ld\n", v13, v20);
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
            592,
            "InetinfoStartService",
            Buffer);
      }
    }
    else
    {
      v17 = GetLastError();
      sprintf_s(Buffer, 0x100u, "Inetinfo: Failed to load DLL %s: %ld\n", v13, v17);
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx", 532, "InetinfoStartService", Buffer);
      AbortService((char *)*a2, v17);
      if ( (_DWORD)v7 != -1 )
        LeaveCriticalSection((LPCRITICAL_SECTION)&qword_140006050[7 * v11]);
    }
    return;
  }
  sprintf_s(Buffer, 0x100u, "Inetinfo: Failed To Find Dll For %s : %ld\n", v9, 122);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx", 507, "InetinfoStartService", Buffer);
  AbortService((char *)*a2, 0x7Au);
}

```

## disassembly

```asm
0x140001b40  mov     [rsp-8+arg_10], rbx
0x140001b45  push    rbp
0x140001b46  push    rsi
0x140001b47  push    rdi
0x140001b48  push    r12
0x140001b4a  push    r13
0x140001b4c  push    r14
0x140001b4e  push    r15
0x140001b50  lea     rbp, [rsp-160h]
0x140001b58  sub     rsp, 260h
0x140001b5f  mov     rax, cs:__security_cookie
0x140001b66  xor     rax, rsp
0x140001b69  mov     [rbp+190h+var_40], rax
0x140001b70  mov     rsi, rdx
0x140001b73  mov     [rsp+290h+var_260], ecx
0x140001b77  xor     edx, edx; Val
0x140001b79  lea     rcx, [rbp+190h+Destination]; void *
0x140001b7d  mov     r8d, 105h; Size
0x140001b83  call    memset_0
0x140001b88  mov     rax, cs:?InetServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYA@@A; _SERVICE_TABLE_ENTRYA near * InetServiceDispatchTable
0x140001b8f  lea     r15, aInetinfostarts; "InetinfoStartService"
0x140001b96  lea     r12, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001b9d  mov     r13d, 100h
0x140001ba3  test    rax, rax
0x140001ba6  jz      short loc_140001BD1
0x140001ba8  mov     rdi, [rsi]
0x140001bab  lea     r14, ?InetServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYA@@A; _SERVICE_TABLE_ENTRYA near * InetServiceDispatchTable
0x140001bb2  mov     rbx, r14
0x140001bb5  mov     rdx, rdi; lpString2
0x140001bb8  mov     rcx, rax; lpString1
0x140001bbb  call    cs:__imp_lstrcmpiA
0x140001bc1  test    eax, eax
0x140001bc3  jz      short loc_140001C2E
0x140001bc5  add     rbx, 10h
0x140001bc9  mov     rax, [rbx]
0x140001bcc  test    rax, rax
0x140001bcf  jnz     short loc_140001BB5
0x140001bd1  mov     ecx, 57h ; 'W'; dwErrCode
0x140001bd6  call    cs:__imp_SetLastError
0x140001bdc  mov     r14d, 0FFFFFFFFh
0x140001be2  mov     ebx, r14d
0x140001be5  mov     rcx, [rsi]; lpSubKey
0x140001be8  lea     rdx, [rbp+190h+Destination]; lpData
0x140001bec  call    ?GetDLLNameForDispatchEntryService@@YAHPEAD0K@Z; GetDLLNameForDispatchEntryService(char *,char *,ulong)
0x140001bf1  mov     r9, [rsi]
0x140001bf4  test    eax, eax
0x140001bf6  jz      short loc_140001C65
0x140001bf8  lea     rax, [rbp+190h+Destination]
0x140001bfc  mov     rdx, r13; BufferCount
0x140001bff  lea     r8, aServiceSHasPat; "Service %s has path set in registry.  A"...
0x140001c06  mov     [rsp+290h+var_270], rax
0x140001c0b  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001c10  call    cs:__imp_sprintf_s
0x140001c16  test    cs:g_dwDebugFlags, 3
0x140001c1d  jz      loc_140001CF0
0x140001c23  mov     r8d, 1EAh
0x140001c29  jmp     loc_140001CD3
0x140001c2e  sub     rbx, r14
0x140001c31  mov     r14d, 0FFFFFFFFh
0x140001c37  sar     rbx, 4
0x140001c3b  cmp     ebx, r14d
0x140001c3e  jz      short loc_140001BE5
0x140001c40  lea     rax, ?InetServiceDllTable@@3PAUSERVICE_DLL_TABLE_ENTRY@@A; SERVICE_DLL_TABLE_ENTRY near * InetServiceDllTable
0x140001c47  mov     r15d, ebx
0x140001c4a  imul    r12, r15, 38h ; '8'
0x140001c4e  lea     rcx, [rax+10h]
0x140001c52  add     rcx, r12; lpCriticalSection
0x140001c55  mov     rdi, [r12+rax+8]
0x140001c5a  call    cs:__imp_EnterCriticalSection
0x140001c60  jmp     loc_140001D01
0x140001c65  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001c69  inc     rax
0x140001c6c  cmp     byte ptr [r9+rax], 0
0x140001c71  jnz     short loc_140001C69
0x140001c73  cmp     rax, r13
0x140001c76  jnb     loc_140001ED0
0x140001c7c  mov     edi, 105h
0x140001c81  lea     rcx, [rbp+190h+Destination]; Destination
0x140001c85  mov     edx, edi; SizeInBytes
0x140001c87  mov     r8, r9; Source
0x140001c8a  call    cs:__imp_strcpy_s
0x140001c90  lea     r8, Source; ".dll"
0x140001c97  mov     edx, edi; SizeInBytes
0x140001c99  lea     rcx, [rbp+190h+Destination]; Destination
0x140001c9d  call    cs:__imp_strcat_s
0x140001ca3  mov     r9, [rsi]
0x140001ca6  lea     rax, [rbp+190h+Destination]
0x140001caa  lea     r8, aServiceSNotOnP; "Service %s not on primary list.  Assumi"...
0x140001cb1  mov     [rsp+290h+var_270], rax
0x140001cb6  mov     rdx, r13; BufferCount
0x140001cb9  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001cbe  call    cs:__imp_sprintf_s
0x140001cc4  test    cs:g_dwDebugFlags, 3
0x140001ccb  jz      short loc_140001CF0
0x140001ccd  mov     r8d, 1F3h
0x140001cd3  mov     rcx, cs:g_pDebug
0x140001cda  lea     rax, [rsp+290h+Buffer]
0x140001cdf  mov     r9, r15
0x140001ce2  mov     [rsp+290h+var_270], rax
0x140001ce7  mov     rdx, r12
0x140001cea  call    cs:__imp_PuDbgPrint
0x140001cf0  lea     rdi, [rbp+190h+Destination]
0x140001cf4  mov     r15, r14
0x140001cf7  mov     r12, 37FFFFFFC8h
0x140001d01  xor     edx, edx; hFile
0x140001d03  mov     rcx, rdi; lpLibFileName
0x140001d06  lea     r8d, [rdx+8]; dwFlags
0x140001d0a  call    cs:__imp_LoadLibraryExA
0x140001d10  mov     r13, rax
0x140001d13  test    rax, rax
0x140001d16  jnz     loc_140001DA4
0x140001d1c  call    cs:__imp_GetLastError
0x140001d22  mov     r9, rdi
0x140001d25  lea     r8, aInetinfoFailed_1; "Inetinfo: Failed to load DLL %s: %ld\n"
0x140001d2c  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001d31  mov     dword ptr [rsp+290h+var_270], eax
0x140001d35  mov     edx, 100h; BufferCount
0x140001d3a  mov     r12d, eax
0x140001d3d  call    cs:__imp_sprintf_s
0x140001d43  test    cs:g_dwDebugFlags, 3
0x140001d4a  jz      short loc_140001D77
0x140001d4c  mov     rcx, cs:g_pDebug
0x140001d53  lea     rax, [rsp+290h+Buffer]
0x140001d58  lea     r9, aInetinfostarts; "InetinfoStartService"
0x140001d5f  mov     [rsp+290h+var_270], rax
0x140001d64  mov     r8d, 214h
0x140001d6a  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001d71  call    cs:__imp_PuDbgPrint
0x140001d77  mov     rcx, [rsi]; char *
0x140001d7a  mov     edx, r12d; unsigned int
0x140001d7d  call    ?AbortService@@YAXPEADK@Z; AbortService(char *,ulong)
0x140001d82  cmp     ebx, r14d
0x140001d85  jz      loc_140001F24
0x140001d8b  imul    rcx, r15, 38h ; '8'
0x140001d8f  lea     rax, qword_140006050
0x140001d96  add     rcx, rax; lpCriticalSection
0x140001d99  call    cs:__imp_LeaveCriticalSection
0x140001d9f  jmp     loc_140001F24
0x140001da4  lea     rdx, ProcName; "ServiceEntry"
0x140001dab  mov     rcx, r13; hModule
0x140001dae  call    cs:__imp_GetProcAddress
0x140001db4  test    rax, rax
0x140001db7  jnz     short loc_140001E2A
0x140001db9  call    cs:__imp_GetLastError
0x140001dbf  mov     [rsp+290h+var_268], eax
0x140001dc3  lea     r9, ProcName; "ServiceEntry"
0x140001dca  mov     edx, 100h; BufferCount
0x140001dcf  mov     [rsp+290h+var_270], rdi
0x140001dd4  lea     r8, aInetinfoCanTFi; "Inetinfo: Can't find entry %s in DLL %s"...
0x140001ddb  mov     r15d, eax
0x140001dde  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001de3  call    cs:__imp_sprintf_s
0x140001de9  test    cs:g_dwDebugFlags, 3
0x140001df0  jz      short loc_140001E1D
0x140001df2  mov     rcx, cs:g_pDebug
0x140001df9  lea     rax, [rsp+290h+Buffer]
0x140001dfe  lea     r9, aInetinfostarts; "InetinfoStartService"
0x140001e05  mov     [rsp+290h+var_270], rax
0x140001e0a  mov     r8d, 22Eh
0x140001e10  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001e17  call    cs:__imp_PuDbgPrint
0x140001e1d  mov     rcx, [rsi]; char *
0x140001e20  mov     edx, r15d; unsigned int
0x140001e23  call    ?AbortService@@YAXPEADK@Z; AbortService(char *,ulong)
0x140001e28  jmp     short loc_140001E3D
0x140001e2a  mov     ecx, [rsp+290h+var_260]
0x140001e2e  lea     r8, ?InetinfoGlobalData@@3U_TCPSVCS_GLOBAL_DATA@@A; _TCPSVCS_GLOBAL_DATA InetinfoGlobalData
0x140001e35  mov     rdx, rsi
0x140001e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e3d  cmp     ebx, r14d
0x140001e40  jz      short loc_140001E56
0x140001e42  lea     rcx, ?InetServiceDllTable@@3PAUSERVICE_DLL_TABLE_ENTRY@@A; SERVICE_DLL_TABLE_ENTRY near * InetServiceDllTable
0x140001e49  add     rcx, 10h
0x140001e4d  add     rcx, r12; lpCriticalSection
0x140001e50  call    cs:__imp_LeaveCriticalSection
0x140001e56  mov     ecx, 1F4h; dwMilliseconds
0x140001e5b  call    cs:__imp_Sleep
0x140001e61  mov     rcx, r13; hLibModule
0x140001e64  call    cs:__imp_FreeLibrary
0x140001e6a  test    eax, eax
0x140001e6c  jnz     loc_140001F24
0x140001e72  call    cs:__imp_GetLastError
0x140001e78  mov     r9, rdi
0x140001e7b  lea     r8, aInetsvcsCanTUn; "INETSVCS: Can't unload DLL %s: %ld\n"
0x140001e82  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001e87  mov     dword ptr [rsp+290h+var_270], eax
0x140001e8b  mov     edx, 100h; BufferCount
0x140001e90  call    cs:__imp_sprintf_s
0x140001e96  test    cs:g_dwDebugFlags, 3
0x140001e9d  jz      loc_140001F24
0x140001ea3  mov     rcx, cs:g_pDebug
0x140001eaa  lea     rax, [rsp+290h+Buffer]
0x140001eaf  lea     r9, aInetinfostarts; "InetinfoStartService"
0x140001eb6  mov     [rsp+290h+var_270], rax
0x140001ebb  mov     r8d, 250h
0x140001ec1  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140001ec8  call    cs:__imp_PuDbgPrint
0x140001ece  jmp     short loc_140001F24
0x140001ed0  mov     ebx, 7Ah ; 'z'
0x140001ed5  lea     r8, aInetinfoFailed_3; "Inetinfo: Failed To Find Dll For %s : %"...
0x140001edc  mov     rdx, r13; BufferCount
0x140001edf  mov     dword ptr [rsp+290h+var_270], ebx
0x140001ee3  lea     rcx, [rsp+290h+Buffer]; Buffer
0x140001ee8  call    cs:__imp_sprintf_s
0x140001eee  test    cs:g_dwDebugFlags, 3
0x140001ef5  jz      short loc_140001F1A
0x140001ef7  mov     rcx, cs:g_pDebug
0x140001efe  lea     rax, [rsp+290h+Buffer]
0x140001f03  mov     r9, r15
0x140001f06  mov     [rsp+290h+var_270], rax
0x140001f0b  mov     r8d, 1FBh
0x140001f11  mov     rdx, r12
0x140001f14  call    cs:__imp_PuDbgPrint
0x140001f1a  mov     rcx, [rsi]; char *
0x140001f1d  mov     edx, ebx; unsigned int
0x140001f1f  call    ?AbortService@@YAXPEADK@Z; AbortService(char *,ulong)
0x140001f24  mov     rcx, [rbp+190h+var_40]
0x140001f2b  xor     rcx, rsp; StackCookie
0x140001f2e  call    __security_check_cookie
0x140001f33  mov     rbx, [rsp+290h+arg_10]
0x140001f3b  add     rsp, 260h
0x140001f42  pop     r15
0x140001f44  pop     r14
0x140001f46  pop     r13
0x140001f48  pop     r12
0x140001f4a  pop     rdi
0x140001f4b  pop     rsi
0x140001f4c  pop     rbp
0x140001f4d  retn
```
