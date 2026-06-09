# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x1800149c4`
- end: `0x180014a89`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180014898`

## callees

- `0x1800145c0`
- `0x1800149c4`
- `0x18001a010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014a56`
- `KERNEL32!GetProcAddress` at `0x180014a56`
- `KERNEL32!GetModuleHandleW` at `0x180014a3f`
- `KERNEL32!GetModuleHandleW` at `0x180014a3f`

## string_xrefs

- `0x180014a38`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v5; // edi
  int v6; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h]
  _BYTE v12[48]; // [rsp+38h] [rbp-30h] BYREF

  v3 = a2;
  v5 = a3;
  v6 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(v12, *(_QWORD *)(a1 + 8), a3, HIDWORD(a2)) + 16);
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
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
      ((void (__fastcall *)(int *))ProcAddress)(&v10);
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x1800149c4  mov     [rsp+arg_18], rbx
0x1800149c9  push    rbp
0x1800149ca  push    rsi
0x1800149cb  push    rdi
0x1800149cc  sub     rsp, 50h
0x1800149d0  mov     r9, rdx
0x1800149d3  mov     rbx, rdx
0x1800149d6  mov     rdx, [rcx+8]
0x1800149da  mov     rsi, rcx
0x1800149dd  shr     r9, 20h
0x1800149e1  lea     rcx, [rsp+68h+var_30]
0x1800149e6  mov     edi, r8d
0x1800149e9  call    wil_details_FeatureReporting_RecordUsageInCache
0x1800149ee  mov     ebp, [rax+10h]
0x1800149f1  bt      ebx, 0Ah
0x1800149f5  jnb     short loc_180014A72
0x1800149f7  cmp     edi, 0FEh
0x1800149fd  jz      short loc_180014A72
0x1800149ff  mov     eax, [rsi+18h]
0x180014a02  mov     [rsp+68h+var_38], 0
0x180014a0b  mov     dword ptr [rsp+68h+var_38], eax
0x180014a0f  mov     word ptr [rsp+68h+var_38+4], di
0x180014a14  bt      ebx, 0Bh
0x180014a18  jnb     short loc_180014A20
0x180014a1a  or      word ptr [rsp+68h+var_38+6], 1
0x180014a20  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180014a27  test    rax, rax
0x180014a2a  jnz     short loc_180014A68
0x180014a2c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180014a33  test    rax, rax
0x180014a36  jnz     short loc_180014A4C
0x180014a38  lea     rcx, LibFileName; "ntdll.dll"
0x180014a3f  call    cs:__imp_GetModuleHandleW
0x180014a45  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180014a4c  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180014a53  mov     rcx, rax; hModule
0x180014a56  call    cs:__imp_GetProcAddress
0x180014a5c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180014a63  test    rax, rax
0x180014a66  jz      short loc_180014A72
0x180014a68  lea     rcx, [rsp+68h+var_38]
0x180014a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a72  mov     rbx, [rsp+68h+arg_18]
0x180014a7a  xor     eax, eax
0x180014a7c  test    ebp, ebp
0x180014a7e  setz    al
0x180014a81  add     rsp, 50h
0x180014a85  pop     rdi
0x180014a86  pop     rsi
0x180014a87  pop     rbp
0x180014a88  retn
```
