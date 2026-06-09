# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180015f58`
- end: `0x18001603f`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180015e1c`

## callees

- `0x180015b44`
- `0x180015f58`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015fe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015ffd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015ffd`

## string_xrefs

- `0x180015fdf`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v4; // edi
  int v5; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  _BYTE v9[24]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+48h] [rbp-20h] BYREF

  v3 = a2;
  v4 = a3;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     v9,
                     &Feature_VPN_BugFixes_25C_RasmansDependency__private_reporting,
                     a3,
                     HIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v10 = 59485045;
    WORD2(v10) = v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v10) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_9;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_9:
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v10);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180015f58  mov     [rsp+arg_0], rbx
0x180015f5d  mov     [rsp+arg_18], rsi
0x180015f62  push    rdi
0x180015f63  sub     rsp, 60h
0x180015f67  mov     rax, cs:__security_cookie
0x180015f6e  xor     rax, rsp
0x180015f71  mov     [rsp+68h+var_18], rax
0x180015f76  mov     r9, rdx
0x180015f79  lea     rcx, [rsp+68h+var_38]
0x180015f7e  mov     rbx, rdx
0x180015f81  shr     r9, 20h
0x180015f85  mov     rdx, cs:off_18003C048
0x180015f8c  mov     edi, r8d
0x180015f8f  call    wil_details_FeatureReporting_RecordUsageInCache
0x180015f94  mov     esi, [rax+10h]
0x180015f97  bt      ebx, 0Ah
0x180015f9b  jnb     short loc_180016019
0x180015f9d  cmp     edi, 0FEh
0x180015fa3  jz      short loc_180016019
0x180015fa5  mov     [rsp+68h+var_20], 0
0x180015fae  mov     dword ptr [rsp+68h+var_20], 38BAB75h
0x180015fb6  mov     word ptr [rsp+68h+var_20+4], di
0x180015fbb  bt      ebx, 0Bh
0x180015fbf  jnb     short loc_180015FC7
0x180015fc1  or      word ptr [rsp+68h+var_20+6], 1
0x180015fc7  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180015fce  test    rax, rax
0x180015fd1  jnz     short loc_18001600F
0x180015fd3  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180015fda  test    rax, rax
0x180015fdd  jnz     short loc_180015FF3
0x180015fdf  lea     rcx, ModuleName; "ntdll.dll"
0x180015fe6  call    cs:__imp_GetModuleHandleW
0x180015fec  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180015ff3  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180015ffa  mov     rcx, rax; hModule
0x180015ffd  call    cs:__imp_GetProcAddress
0x180016003  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001600a  test    rax, rax
0x18001600d  jz      short loc_180016019
0x18001600f  lea     rcx, [rsp+68h+var_20]
0x180016014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016019  xor     eax, eax
0x18001601b  test    esi, esi
0x18001601d  setz    al
0x180016020  mov     rcx, [rsp+68h+var_18]
0x180016025  xor     rcx, rsp; StackCookie
0x180016028  call    __security_check_cookie
0x18001602d  lea     r11, [rsp+68h+var_8]
0x180016032  mov     rbx, [r11+10h]
0x180016036  mov     rsi, [r11+28h]
0x18001603a  mov     rsp, r11
0x18001603d  pop     rdi
0x18001603e  retn
```
