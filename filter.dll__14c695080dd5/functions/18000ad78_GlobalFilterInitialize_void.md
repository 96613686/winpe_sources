# GlobalFilterInitialize(void)

- ea: `0x18000ad78`
- end: `0x18000ae5c`
- name: `?GlobalFilterInitialize@@YAJXZ`
- size: `228`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009fa0`

## callees

- `0x18000ad78`
- `0x18000ae64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ada9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000ad9f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000ad9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ae4c`
- `iisutil!PuDbgPrint` at `0x18000adf6`
- `iisutil!PuDbgPrint` at `0x18000ae3f`
- `iisutil!PuDbgPrint` at `0x18000adf6`
- `iisutil!PuDbgPrint` at `0x18000ae3f`

## string_xrefs

- `0x18000adef`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x18000ae26`: `servercommon\inetsrv\iis\iisrearc\iis70\isapifilters\filter.cxx`
- `0x18000add2`: `Failed to initialize HTTP_FILTER_DLL globals.  hr = %x\n`

## pseudocode

```c
__int64 GlobalFilterInitialize(void)
{
  signed int LastError; // eax
  unsigned int v1; // ebx
  int v3; // eax

  qword_1800136C8 = (__int64)&HTTP_FILTER_DLL::sm_FilterHead;
  HTTP_FILTER_DLL::sm_FilterHead.Flink = &HTTP_FILTER_DLL::sm_FilterHead;
  if ( !InitializeCriticalSectionAndSpinCount(&HTTP_FILTER_DLL::sm_csFilterDlls, 0xC8u) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( (v1 & 0x80000000) != 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
          5377,
          "GlobalFilterInitialize",
          "Failed to initialize HTTP_FILTER_DLL globals.  hr = %x\n",
          v1);
      return v1;
    }
  }
  v3 = W3_FILTER_CONTEXT::Initialize();
  v1 = v3;
  if ( v3 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapifilters\\filter.cxx",
        5405,
        "GlobalFilterInitialize",
        "Failed to initialize W3_FILTER_CONTEXT globals.  hr = %x\n",
        v3);
    DeleteCriticalSection(&HTTP_FILTER_DLL::sm_csFilterDlls);
    return v1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ad78  push    rbx
0x18000ad7a  sub     rsp, 30h
0x18000ad7e  lea     rax, ?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x18000ad85  mov     edx, 0C8h; dwSpinCount
0x18000ad8a  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ad91  mov     cs:qword_1800136C8, rax
0x18000ad98  mov     cs:?sm_FilterHead@HTTP_FILTER_DLL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY HTTP_FILTER_DLL::sm_FilterHead
0x18000ad9f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000ada5  test    eax, eax
0x18000ada7  jnz     short loc_18000AE00
0x18000ada9  call    cs:__imp_GetLastError
0x18000adaf  mov     ebx, eax
0x18000adb1  test    eax, eax
0x18000adb3  jle     short loc_18000ADBE
0x18000adb5  movzx   ebx, ax
0x18000adb8  or      ebx, 80070000h
0x18000adbe  test    ebx, ebx
0x18000adc0  jns     short loc_18000AE00
0x18000adc2  test    cs:g_dwDebugFlags, 3
0x18000adc9  jz      short loc_18000ADFC
0x18000adcb  mov     rcx, cs:g_pDebug
0x18000add2  lea     rax, aFailedToInitia; "Failed to initialize HTTP_FILTER_DLL gl"...
0x18000add9  mov     [rsp+38h+var_10], ebx
0x18000addd  lea     r9, aGlobalfilterin; "GlobalFilterInitialize"
0x18000ade4  mov     r8d, 1501h
0x18000adea  mov     [rsp+38h+var_18], rax
0x18000adef  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000adf6  call    cs:__imp_PuDbgPrint
0x18000adfc  mov     eax, ebx
0x18000adfe  jmp     short loc_18000AE56
0x18000ae00  call    ?Initialize@W3_FILTER_CONTEXT@@SAJXZ; W3_FILTER_CONTEXT::Initialize(void)
0x18000ae05  mov     ebx, eax
0x18000ae07  test    eax, eax
0x18000ae09  jns     short loc_18000AE54
0x18000ae0b  test    cs:g_dwDebugFlags, 3
0x18000ae12  jz      short loc_18000AE45
0x18000ae14  mov     rcx, cs:g_pDebug
0x18000ae1b  lea     r9, aGlobalfilterin; "GlobalFilterInitialize"
0x18000ae22  mov     [rsp+38h+var_10], eax
0x18000ae26  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ae2d  lea     rax, aFailedToInitia_0; "Failed to initialize W3_FILTER_CONTEXT "...
0x18000ae34  mov     r8d, 151Dh
0x18000ae3a  mov     [rsp+38h+var_18], rax
0x18000ae3f  call    cs:__imp_PuDbgPrint
0x18000ae45  lea     rcx, ?sm_csFilterDlls@HTTP_FILTER_DLL@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000ae4c  call    cs:__imp_DeleteCriticalSection
0x18000ae52  jmp     short loc_18000ADFC
0x18000ae54  xor     eax, eax
0x18000ae56  add     rsp, 30h
0x18000ae5a  pop     rbx
0x18000ae5b  retn
```
