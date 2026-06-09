# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180034344`
- end: `0x180034478`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180034710`

## callees

- `0x1800017a0`
- `0x180012b80`
- `0x180034344`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034411`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034411`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003442e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003442e`

## string_xrefs

- `0x18003440a`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  unsigned int v4; // esi
  __int64 v5; // rax
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+34h] [rbp-54h]
  _BYTE v12[24]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+60h] [rbp-28h]

  v3 = a2;
  v4 = a3;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(v12, &Feature_UDFDOD__private_reporting, a3, HIDWORD(a2));
  v6 = 0;
  v13 = *(_OWORD *)v5;
  v14 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(54591346, v4, 1, &Feature_UDFDOD__private_reporting, &v13);
  if ( (v3 & 0x400) != 0 && v4 != 254 )
  {
    v10 = 54591346;
    v11 = (unsigned __int16)v4;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_11;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_11:
      ((void (__fastcall *)(int *))ProcAddress)(&v10);
  }
  LOBYTE(v6) = (_DWORD)v14 == 0;
  return v6;
}

```

## disassembly

```asm
0x180034344  mov     [rsp+arg_0], rbx
0x180034349  push    rbp
0x18003434a  push    rsi
0x18003434b  push    rdi
0x18003434c  sub     rsp, 70h
0x180034350  mov     rax, cs:__security_cookie
0x180034357  xor     rax, rsp
0x18003435a  mov     [rsp+88h+var_20], rax
0x18003435f  mov     r9, rdx
0x180034362  lea     rcx, [rsp+88h+var_50]
0x180034367  mov     rbx, rdx
0x18003436a  shr     r9, 20h
0x18003436e  mov     rdx, cs:off_180043038
0x180034375  mov     esi, r8d
0x180034378  call    wil_details_FeatureReporting_RecordUsageInCache
0x18003437d  xor     edi, edi
0x18003437f  mov     ebp, 1
0x180034384  movups  xmm1, xmmword ptr [rax]
0x180034387  movups  [rsp+88h+var_38], xmm1
0x18003438c  movsd   xmm0, qword ptr [rax+10h]
0x180034391  mov     rax, cs:g_wil_details_recordFeatureUsage
0x180034398  movsd   [rsp+88h+var_28], xmm0
0x18003439e  test    rax, rax
0x1800343a1  jz      short loc_1800343C3
0x1800343a3  mov     r9, cs:off_180043038
0x1800343aa  lea     rcx, [rsp+88h+var_38]
0x1800343af  mov     [rsp+88h+var_68], rcx
0x1800343b4  mov     r8d, ebp
0x1800343b7  mov     ecx, 340FF72h
0x1800343bc  mov     edx, esi
0x1800343be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343c3  bt      ebx, 0Ah
0x1800343c7  jnb     loc_180034450
0x1800343cd  cmp     esi, 0FEh
0x1800343d3  jz      short loc_180034450
0x1800343d5  mov     [rsp+88h+var_58], rdi
0x1800343da  mov     dword ptr [rsp+88h+var_58], 340FF72h
0x1800343e2  mov     word ptr [rsp+88h+var_58+4], si
0x1800343e7  bt      ebx, 0Bh
0x1800343eb  jnb     short loc_1800343F2
0x1800343ed  or      word ptr [rsp+88h+var_58+6], bp
0x1800343f2  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800343f9  test    rax, rax
0x1800343fc  jnz     short loc_180034446
0x1800343fe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180034405  test    rax, rax
0x180034408  jnz     short loc_180034424
0x18003440a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180034411  call    cs:__imp_GetModuleHandleW
0x180034418  nop     dword ptr [rax+rax+00h]
0x18003441d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180034424  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18003442b  mov     rcx, rax; hModule
0x18003442e  call    cs:__imp_GetProcAddress
0x180034435  nop     dword ptr [rax+rax+00h]
0x18003443a  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180034441  test    rax, rax
0x180034444  jz      short loc_180034450
0x180034446  lea     rcx, [rsp+88h+var_58]
0x18003444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034450  cmp     dword ptr [rsp+88h+var_28], edi
0x180034454  setz    dil
0x180034458  mov     eax, edi
0x18003445a  mov     rcx, [rsp+88h+var_20]
0x18003445f  xor     rcx, rsp; StackCookie
0x180034462  call    __security_check_cookie
0x180034467  mov     rbx, [rsp+88h+arg_0]
0x18003446f  add     rsp, 70h
0x180034473  pop     rdi
0x180034474  pop     rsi
0x180034475  pop     rbp
0x180034476  retn
```
