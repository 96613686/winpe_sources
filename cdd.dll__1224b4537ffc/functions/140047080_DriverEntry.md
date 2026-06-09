# DriverEntry

- ea: `0x140047080`
- end: `0x1400472e4`
- name: `DriverEntry`
- size: `612`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140047010`

## callees

- `0x140029dd0`
- `0x1400435c4`
- `0x140044ef8`
- `0x140047080`
- `0x1400472ec`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140047255`
- `ntoskrnl!RtlInitUnicodeString` at `0x140047255`
- `ntoskrnl!DbgPrint` at `0x140047127`
- `ntoskrnl!DbgPrint` at `0x14004719c`
- `ntoskrnl!DbgPrint` at `0x140047127`
- `ntoskrnl!DbgPrint` at `0x14004719c`
- `ntoskrnl!KdDebuggerEnabled` at `0x140047114`
- `ntoskrnl!KdDebuggerEnabled` at `0x140047189`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400470ca`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400470ca`
- `ntoskrnl!ExIsProcessorFeaturePresent` at `0x1400470b5`
- `ntoskrnl!ExIsProcessorFeaturePresent` at `0x1400470b5`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140047293`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140047293`
- `watchdog!WdLogSingleEntry1` at `0x14004727d`
- `watchdog!WdLogSingleEntry1` at `0x14004727d`
- `watchdog!WdLogNewEntry5_WdError` at `0x14004714f`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400471c4`
- `watchdog!WdLogNewEntry5_WdError` at `0x14004714f`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400471c4`
- `watchdog!WdLogSingleEntry0` at `0x140047138`
- `watchdog!WdLogSingleEntry0` at `0x1400471ad`
- `watchdog!WdLogSingleEntry0` at `0x140047138`
- `watchdog!WdLogSingleEntry0` at `0x1400471ad`

## string_xrefs

- `0x140047120`: `Cache line size in bytes is not power of 2`
- `0x140047195`: `Cache line size in pixels is not power of 2`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  ULONG v5; // edx
  ULONG v6; // r9d
  NTSTATUS v7; // eax
  NTSTATUS v8; // edi
  _QWORD *v9; // rax
  ULONG v11; // [rsp+20h] [rbp-48h]
  BOOLEAN v12; // [rsp+28h] [rbp-40h]
  const UNICODE_STRING *v13; // [rsp+30h] [rbp-38h]
  const GUID *v14; // [rsp+38h] [rbp-30h]
  PDEVICE_OBJECT *v15; // [rsp+40h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  gCddImageInfo = DriverObject->DriverStart;
  LODWORD(dword_14003E570) = DriverObject->DriverSize;
  if ( !g_IsCPUInfoLoaded )
  {
    g_SSE2InstructionsAvailable = ExIsProcessorFeaturePresent(0xAu);
    g_CPUCacheLineSizeInBytes = KeGetRecommendedSharedDataAlignment();
    g_IsCPUInfoLoaded = 1;
    g_CPUCacheLineSizeInPixels = g_CPUCacheLineSizeInBytes >> 2;
    g_CPUCacheLineMaskPixels = (g_CPUCacheLineSizeInBytes >> 2) - 1;
    g_CPUCacheLineMaskBytes = g_CPUCacheLineSizeInBytes - 1;
  }
  if ( (g_CPUCacheLineMaskBytes & g_CPUCacheLineSizeInBytes) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Cache line size in bytes is not power of 2", RegistryPath);
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 59;
    v3 = (_QWORD *)WdLogNewEntry5_WdError();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 59;
    __debugbreak();
  }
  if ( (g_CPUCacheLineMaskPixels & g_CPUCacheLineSizeInPixels) != 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("Cache line size in pixels is not power of 2", RegistryPath);
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 60;
    v4 = (_QWORD *)WdLogNewEntry5_WdError();
    v4[3] = gCddImageInfo;
    v4[4] = (unsigned int)dword_14003E570;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 60;
    __debugbreak();
  }
  wil_InitializeFeatureStaging();
  if ( _InterlockedIncrement(&g_iTelemetryProviderRef) == 1 )
    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation();
  DriverObject->MajorFunction[0] = CddCreateClose;
  DriverObject->MajorFunction[2] = CddCreateClose;
  DriverObject->MajorFunction[15] = CddInternalDeviceIoctl;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)CddDriverUnload;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Cdd");
  v7 = WdmlibIoCreateDeviceSecure(DriverObject, v5, &DestinationString, v6, v11, v12, v13, v14, v15);
  v8 = v7;
  if ( v7 >= 0 )
    return 0;
  WdLogSingleEntry1(3, v7);
  WdLogGlobalForLineNumber = 87;
  v9 = (_QWORD *)WdLogNewEntry5_WdWarning();
  v9[3] = gCddImageInfo;
  v9[4] = (unsigned int)dword_14003E570;
  v9[5] = 215857758;
  WdLogGlobalForLineNumber = 87;
  CddDriverUnload(DriverObject);
  return v8;
}

```

## disassembly

```asm
0x140047080  mov     [rsp+arg_8], rbx
0x140047085  mov     [rsp+arg_10], rdi
0x14004708a  push    r14
0x14004708c  sub     rsp, 60h
0x140047090  cmp     cs:?g_IsCPUInfoLoaded@@3HA, 0; int g_IsCPUInfoLoaded
0x140047097  mov     rbx, rcx
0x14004709a  mov     rax, [rcx+18h]
0x14004709e  mov     cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A, rax; _CDD_IMAGE_INFO gCddImageInfo
0x1400470a5  mov     eax, [rcx+20h]
0x1400470a8  mov     cs:dword_14003E570, eax
0x1400470ae  jnz     short loc_140047100
0x1400470b0  mov     ecx, 0Ah; ProcessorFeature
0x1400470b5  call    cs:__imp_ExIsProcessorFeaturePresent
0x1400470bc  nop     dword ptr [rax+rax+00h]
0x1400470c1  movzx   eax, al
0x1400470c4  mov     cs:?g_SSE2InstructionsAvailable@@3HA, eax; int g_SSE2InstructionsAvailable
0x1400470ca  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400470d1  nop     dword ptr [rax+rax+00h]
0x1400470d6  mov     cs:?g_CPUCacheLineSizeInBytes@@3IA, eax; uint g_CPUCacheLineSizeInBytes
0x1400470dc  mov     cs:?g_IsCPUInfoLoaded@@3HA, 1; int g_IsCPUInfoLoaded
0x1400470e6  lea     ecx, [rax-1]
0x1400470e9  shr     eax, 2
0x1400470ec  mov     cs:?g_CPUCacheLineSizeInPixels@@3IA, eax; uint g_CPUCacheLineSizeInPixels
0x1400470f2  dec     eax
0x1400470f4  mov     cs:?g_CPUCacheLineMaskPixels@@3IA, eax; uint g_CPUCacheLineMaskPixels
0x1400470fa  mov     cs:?g_CPUCacheLineMaskBytes@@3IA, ecx; uint g_CPUCacheLineMaskBytes
0x140047100  mov     eax, cs:?g_CPUCacheLineMaskBytes@@3IA; uint g_CPUCacheLineMaskBytes
0x140047106  mov     r14d, 0CDDBA5Eh
0x14004710c  test    cs:?g_CPUCacheLineSizeInBytes@@3IA, eax; uint g_CPUCacheLineSizeInBytes
0x140047112  jz      short loc_14004717B
0x140047114  mov     rax, cs:KdDebuggerEnabled
0x14004711b  cmp     byte ptr [rax], 0
0x14004711e  jz      short loc_14004717B
0x140047120  lea     rcx, aCacheLineSizeI; "Cache line size in bytes is not power o"...
0x140047127  call    cs:__imp_DbgPrint
0x14004712e  nop     dword ptr [rax+rax+00h]
0x140047133  mov     ecx, 2
0x140047138  call    cs:__imp_WdLogSingleEntry0
0x14004713f  nop     dword ptr [rax+rax+00h]
0x140047144  mov     edi, 3Bh ; ';'
0x140047149  mov     cs:WdLogGlobalForLineNumber, edi
0x14004714f  call    cs:__imp_WdLogNewEntry5_WdError
0x140047156  nop     dword ptr [rax+rax+00h]
0x14004715b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140047162  mov     [rax+18h], rcx
0x140047166  mov     ecx, cs:dword_14003E570
0x14004716c  mov     [rax+20h], rcx
0x140047170  mov     [rax+28h], r14
0x140047174  mov     cs:WdLogGlobalForLineNumber, edi
0x14004717a  int     3; Trap to Debugger
0x14004717b  mov     eax, cs:?g_CPUCacheLineMaskPixels@@3IA; uint g_CPUCacheLineMaskPixels
0x140047181  test    cs:?g_CPUCacheLineSizeInPixels@@3IA, eax; uint g_CPUCacheLineSizeInPixels
0x140047187  jz      short loc_1400471F0
0x140047189  mov     rax, cs:KdDebuggerEnabled
0x140047190  cmp     byte ptr [rax], 0
0x140047193  jz      short loc_1400471F0
0x140047195  lea     rcx, aCacheLineSizeI_0; "Cache line size in pixels is not power "...
0x14004719c  call    cs:__imp_DbgPrint
0x1400471a3  nop     dword ptr [rax+rax+00h]
0x1400471a8  mov     ecx, 2
0x1400471ad  call    cs:__imp_WdLogSingleEntry0
0x1400471b4  nop     dword ptr [rax+rax+00h]
0x1400471b9  mov     edi, 3Ch ; '<'
0x1400471be  mov     cs:WdLogGlobalForLineNumber, edi
0x1400471c4  call    cs:__imp_WdLogNewEntry5_WdError
0x1400471cb  nop     dword ptr [rax+rax+00h]
0x1400471d0  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400471d7  mov     [rax+18h], rcx
0x1400471db  mov     ecx, cs:dword_14003E570
0x1400471e1  mov     [rax+20h], rcx
0x1400471e5  mov     [rax+28h], r14
0x1400471e9  mov     cs:WdLogGlobalForLineNumber, edi
0x1400471ef  int     3; Trap to Debugger
0x1400471f0  call    wil_InitializeFeatureStaging
0x1400471f5  mov     eax, 1
0x1400471fa  lock xadd cs:?g_iTelemetryProviderRef@@3JA, eax; long g_iTelemetryProviderRef
0x140047202  inc     eax
0x140047204  cmp     eax, 1
0x140047207  jnz     short loc_14004720E
0x140047209  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x14004720e  lea     rax, ?CddCreateClose@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CddCreateClose(_DEVICE_OBJECT *,_IRP *)
0x140047215  mov     [rsp+68h+arg_0], 0
0x14004721d  mov     [rbx+70h], rax
0x140047221  lea     rdx, aDeviceCdd; "\\Device\\Cdd"
0x140047228  mov     [rbx+80h], rax
0x14004722f  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140047234  lea     rax, ?CddInternalDeviceIoctl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CddInternalDeviceIoctl(_DEVICE_OBJECT *,_IRP *)
0x14004723b  xorps   xmm0, xmm0
0x14004723e  mov     [rbx+0E8h], rax
0x140047245  lea     rax, ?CddDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; CddDriverUnload(_DRIVER_OBJECT *)
0x14004724c  mov     [rbx+68h], rax
0x140047250  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140047255  call    cs:__imp_RtlInitUnicodeString
0x14004725c  nop     dword ptr [rax+rax+00h]
0x140047261  lea     r8, [rsp+68h+DestinationString]; DeviceName
0x140047266  mov     rcx, rbx; DriverObject
0x140047269  call    WdmlibIoCreateDeviceSecure
0x14004726e  movsxd  rdi, eax
0x140047271  test    eax, eax
0x140047273  jns     short loc_1400472CE
0x140047275  mov     rdx, rdi
0x140047278  mov     ecx, 3
0x14004727d  call    cs:__imp_WdLogSingleEntry1
0x140047284  nop     dword ptr [rax+rax+00h]
0x140047289  mov     cs:WdLogGlobalForLineNumber, 57h ; 'W'
0x140047293  call    cs:__imp_WdLogNewEntry5_WdWarning
0x14004729a  nop     dword ptr [rax+rax+00h]
0x14004729f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400472a6  mov     [rax+18h], rcx
0x1400472aa  mov     ecx, cs:dword_14003E570
0x1400472b0  mov     [rax+20h], rcx
0x1400472b4  mov     rcx, rbx; struct _DRIVER_OBJECT *
0x1400472b7  mov     [rax+28h], r14
0x1400472bb  mov     cs:WdLogGlobalForLineNumber, 57h ; 'W'
0x1400472c5  call    ?CddDriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z; CddDriverUnload(_DRIVER_OBJECT *)
0x1400472ca  mov     eax, edi
0x1400472cc  jmp     short loc_1400472D0
0x1400472ce  xor     eax, eax
0x1400472d0  lea     r11, [rsp+68h+var_8]
0x1400472d5  mov     rbx, [r11+18h]
0x1400472d9  mov     rdi, [r11+20h]
0x1400472dd  mov     rsp, r11
0x1400472e0  pop     r14
0x1400472e2  retn
```
