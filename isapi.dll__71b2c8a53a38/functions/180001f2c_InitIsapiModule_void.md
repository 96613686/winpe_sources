# InitIsapiModule(void)

- ea: `0x180001f2c`
- end: `0x180002142`
- name: `?InitIsapiModule@@YAJXZ`
- size: `534`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c30`

## callees

- `0x180001020`
- `0x180001d8c`
- `0x180001f2c`
- `0x1800055ac`
- `0x180005fc8`
- `0x18000c5e8`
- `0x18000e1bc`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001f62`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000200f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000200f`
- `iisutil!PuDbgPrint` at `0x180001ffb`
- `iisutil!PuDbgPrint` at `0x180001ffb`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001f49`
- `iisutil!PuCreateDebugPrintsObject` at `0x180001f49`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180001f90`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x180001f90`
- `iisutil!InitializeIISUtil` at `0x180001fa2`
- `iisutil!InitializeIISUtil` at `0x180001fa2`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800020a7`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x1800020a7`
- `iisutil!TerminateIISUtil` at `0x180002123`
- `iisutil!TerminateIISUtil` at `0x180002123`
- `iisutil!CreateRefTraceLog` at `0x1800020c7`
- `iisutil!CreateRefTraceLog` at `0x1800020c7`
- `iisutil!IISGetPlatformType` at `0x180001f9c`
- `iisutil!IISGetPlatformType` at `0x180001f9c`

## string_xrefs

- `0x180001f5b`: `Unable to Create Debug Print Object \n`
- `0x180001fef`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\isapi_module.cxx`
- `0x180002086`: `ISAPI_DLL_HASH`
- `0x180001f87`: `System\CurrentControlSet\Services\W3SVC\Parameters\w3isapi`

## pseudocode

```c
__int64 InitIsapiModule(void)
{
  int v0; // edi
  __int64 DebugPrintsObject; // rax
  int v2; // esi
  signed int LastError; // eax
  unsigned int v4; // edx
  signed int v5; // ebx
  const char *v6; // rax
  __int64 v7; // r8
  signed int v8; // eax
  CLKRHashTable *v9; // rax
  W3_RESTRICTION_LIST *v10; // rbx

  v0 = 1;
  DebugPrintsObject = PuCreateDebugPrintsObject("w3isapi", 1);
  g_pDebug = DebugPrintsObject;
  if ( !DebugPrintsObject )
  {
    OutputDebugStringA("Unable to Create Debug Print Object \n");
    DebugPrintsObject = g_pDebug;
    if ( !g_pDebug )
      return 2147500037LL;
  }
  if ( !*(_DWORD *)(DebugPrintsObject + 640) )
    return 2147500037LL;
  v2 = 0;
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\W3SVC\\Parameters\\w3isapi", 0);
  IISGetPlatformType();
  if ( !(unsigned int)InitializeIISUtil() )
  {
    v0 = 0;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      goto LABEL_22;
    v6 = "Error initializing IISUTIL.  hr = %x\n";
    v7 = 531;
    goto LABEL_9;
  }
  if ( (unsigned int)ISAPI_REQUEST::InitClass() )
  {
    v2 = 1;
    v9 = (CLKRHashTable *)operator new(0x48u);
    v10 = v9;
    if ( v9 )
    {
      CLKRHashTable::CLKRHashTable(
        v9,
        "ISAPI_DLL_HASH",
        (unsigned __int64 (*)(const void *))TOKEN_KEY::GetUserNameW,
        (unsigned int (*)(unsigned __int64))CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
        (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,unsigned short const *,CLKRHashTable>::_EqualKeys,
        (void (*)(const void *, int))CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,unsigned short const *,CLKRHashTable>::_AddRefRecord,
        4.0,
        1u,
        0,
        0);
      g_pDllManager = v10;
      if ( (g_dwDebugFlags & 0x80000) != 0 )
        ISAPI_CONTEXT::sm_pTraceLog = (struct _TRACE_LOG *)CreateRefTraceLog(2000, 0);
      v5 = ISAPI_DLL::Initialize();
      if ( v5 >= 0 )
        return 0;
      ISAPI_CONTEXT::Terminate();
    }
    else
    {
      g_pDllManager = 0;
      v5 = -2147024888;
    }
    goto LABEL_22;
  }
  v8 = GetLastError();
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v6 = "Error initializing ISAPI_REQUEST.  hr = %x\n";
    v7 = 548;
LABEL_9:
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\isapi_module.cxx",
      v7,
      "InitIsapiModule",
      v6,
      v5);
  }
LABEL_22:
  if ( g_pDllManager )
  {
    W3_RESTRICTION_LIST::`scalar deleting destructor'(g_pDllManager, v4);
    g_pDllManager = 0;
  }
  if ( v2 )
    ISAPI_REQUEST::CleanupClass();
  if ( v0 )
    TerminateIISUtil();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001f2c  mov     [rsp+arg_0], rbx
0x180001f31  mov     [rsp+arg_8], rsi
0x180001f36  push    rdi
0x180001f37  sub     rsp, 50h
0x180001f3b  mov     edi, 1
0x180001f40  lea     rcx, aW3isapi; "w3isapi"
0x180001f47  mov     edx, edi
0x180001f49  call    cs:__imp_PuCreateDebugPrintsObject
0x180001f4f  mov     cs:g_pDebug, rax
0x180001f56  test    rax, rax
0x180001f59  jnz     short loc_180001F78
0x180001f5b  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x180001f62  call    cs:__imp_OutputDebugStringA
0x180001f68  mov     rax, cs:g_pDebug
0x180001f6f  test    rax, rax
0x180001f72  jz      loc_18000212D
0x180001f78  cmp     dword ptr [rax+280h], 0
0x180001f7f  jz      loc_18000212D
0x180001f85  xor     edx, edx
0x180001f87  lea     rcx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180001f8e  xor     esi, esi
0x180001f90  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x180001f96  mov     cs:g_dwDebugFlags, eax
0x180001f9c  call    cs:__imp_IISGetPlatformType
0x180001fa2  call    cs:__imp_InitializeIISUtil
0x180001fa8  test    eax, eax
0x180001faa  jnz     short loc_180002006
0x180001fac  xor     edi, edi
0x180001fae  call    cs:__imp_GetLastError
0x180001fb4  mov     ebx, eax
0x180001fb6  test    eax, eax
0x180001fb8  jle     short loc_180001FC3
0x180001fba  movzx   ebx, ax
0x180001fbd  or      ebx, 80070000h
0x180001fc3  test    byte ptr cs:g_dwDebugFlags, 3
0x180001fca  jz      loc_1800020FA
0x180001fd0  lea     rax, aErrorInitializ_0; "Error initializing IISUTIL.  hr = %x\n"
0x180001fd7  mov     r8d, 213h
0x180001fdd  mov     rcx, cs:g_pDebug
0x180001fe4  lea     r9, aInitisapimodul; "InitIsapiModule"
0x180001feb  mov     dword ptr [rsp+58h+var_30], ebx
0x180001fef  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001ff6  mov     [rsp+58h+var_38], rax
0x180001ffb  call    cs:__imp_PuDbgPrint
0x180002001  jmp     loc_1800020FA
0x180002006  call    ?InitClass@ISAPI_REQUEST@@SAHXZ; ISAPI_REQUEST::InitClass(void)
0x18000200b  test    eax, eax
0x18000200d  jnz     short loc_180002040
0x18000200f  call    cs:__imp_GetLastError
0x180002015  mov     ebx, eax
0x180002017  test    eax, eax
0x180002019  jle     short loc_180002024
0x18000201b  movzx   ebx, ax
0x18000201e  or      ebx, 80070000h
0x180002024  test    byte ptr cs:g_dwDebugFlags, 3
0x18000202b  jz      loc_1800020FA
0x180002031  lea     rax, aErrorInitializ; "Error initializing ISAPI_REQUEST.  hr ="...
0x180002038  mov     r8d, 224h
0x18000203e  jmp     short loc_180001FDD
0x180002040  mov     ecx, 48h ; 'H'; Size
0x180002045  mov     esi, edi
0x180002047  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000204c  mov     rbx, rax
0x18000204f  test    rax, rax
0x180002052  jz      loc_1800020EA
0x180002058  movsd   xmm0, cs:__real@4010000000000000
0x180002060  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180002067  mov     [rsp+58h+var_10], 0
0x18000206c  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VISAPI_DLL_HASH@@VISAPI_DLL@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<ISAPI_DLL_HASH,ISAPI_DLL,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180002073  mov     [rsp+58h+var_18], 0
0x18000207b  lea     r8, ?GetUserNameW@TOKEN_KEY@@UEBAPEBGXZ; TOKEN_KEY::GetUserNameW(void)
0x180002082  mov     [rsp+58h+var_20], edi
0x180002086  lea     rdx, aIsapiDllHash; "ISAPI_DLL_HASH"
0x18000208d  movsd   [rsp+58h+var_28], xmm0
0x180002093  mov     rcx, rbx
0x180002096  mov     [rsp+58h+var_30], rax
0x18000209b  lea     rax, ?_EqualKeys@?$CTypedHashTable@VW3_RESTRICTION_LIST@@VW3_IMAGE_RECORD@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<W3_RESTRICTION_LIST,W3_IMAGE_RECORD,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x1800020a2  mov     [rsp+58h+var_38], rax
0x1800020a7  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x1800020ad  test    cs:g_dwDebugFlags, 80000h
0x1800020b7  mov     cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA, rbx; ISAPI_DLL_MANAGER * g_pDllManager
0x1800020be  jz      short loc_1800020D4
0x1800020c0  xor     edx, edx
0x1800020c2  mov     ecx, 7D0h
0x1800020c7  call    cs:__imp_CreateRefTraceLog
0x1800020cd  mov     cs:?sm_pTraceLog@ISAPI_CONTEXT@@0PEAU_TRACE_LOG@@EA, rax; _TRACE_LOG * ISAPI_CONTEXT::sm_pTraceLog
0x1800020d4  call    ?Initialize@ISAPI_DLL@@SAJXZ; ISAPI_DLL::Initialize(void)
0x1800020d9  mov     ebx, eax
0x1800020db  test    eax, eax
0x1800020dd  jns     short loc_1800020E6
0x1800020df  call    ?Terminate@ISAPI_CONTEXT@@SAXXZ; ISAPI_CONTEXT::Terminate(void)
0x1800020e4  jmp     short loc_1800020FA
0x1800020e6  xor     eax, eax
0x1800020e8  jmp     short loc_180002132
0x1800020ea  mov     cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA, 0; ISAPI_DLL_MANAGER * g_pDllManager
0x1800020f5  mov     ebx, 80070008h
0x1800020fa  mov     rcx, cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA; this
0x180002101  test    rcx, rcx
0x180002104  jz      short loc_180002116
0x180002106  call    ??_GW3_RESTRICTION_LIST@@QEAAPEAXI@Z; W3_RESTRICTION_LIST::`scalar deleting destructor'(uint)
0x18000210b  mov     cs:?g_pDllManager@@3PEAVISAPI_DLL_MANAGER@@EA, 0; ISAPI_DLL_MANAGER * g_pDllManager
0x180002116  test    esi, esi
0x180002118  jz      short loc_18000211F
0x18000211a  call    ?CleanupClass@ISAPI_REQUEST@@SAXXZ; ISAPI_REQUEST::CleanupClass(void)
0x18000211f  test    edi, edi
0x180002121  jz      short loc_180002129
0x180002123  call    cs:__imp_TerminateIISUtil
0x180002129  mov     eax, ebx
0x18000212b  jmp     short loc_180002132
0x18000212d  mov     eax, 80004005h
0x180002132  mov     rbx, [rsp+58h+arg_0]
0x180002137  mov     rsi, [rsp+58h+arg_8]
0x18000213c  add     rsp, 50h
0x180002140  pop     rdi
0x180002141  retn
```
