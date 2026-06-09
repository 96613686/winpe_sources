# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18002033c`
- end: `0x180020465`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `297`
- prototype: `_BOOL8 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180020220`

## callees

- `0x180002e50`
- `0x180019970`
- `0x18002033c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002040a`
- `KERNEL32!GetModuleHandleW` at `0x18002040a`
- `KERNEL32!GetProcAddress` at `0x180020421`
- `KERNEL32!GetProcAddress` at `0x180020421`

## string_xrefs

- `0x180020403`: `ntdll.dll`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  __int64 v5; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v9; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v10[24]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v11; // [rsp+50h] [rbp-28h] BYREF
  __int64 v12; // [rsp+60h] [rbp-18h]

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v10,
         (volatile signed __int32 *)&Feature_ShadowAdmin__private_reporting,
         a3,
         SHIDWORD(a2));
  v11 = *(_OWORD *)v5;
  v12 = *(_QWORD *)(v5 + 16);
  if ( g_wil_details_recordFeatureUsage )
    g_wil_details_recordFeatureUsage(60288851, a3, 1, &Feature_ShadowAdmin__private_reporting, &v11);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v9 = 60288851;
    WORD2(v9) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v9) |= 1u;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage )
      goto LABEL_11;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
    g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_11:
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v9);
  }
  return (_DWORD)v12 == 0;
}

```

## disassembly

```asm
0x18002033c  mov     [rsp+arg_0], rbx
0x180020341  mov     [rsp+arg_18], rsi
0x180020346  push    rdi
0x180020347  sub     rsp, 70h
0x18002034b  mov     rax, cs:__security_cookie
0x180020352  xor     rax, rsp
0x180020355  mov     [rsp+78h+var_10], rax
0x18002035a  mov     r9, rdx
0x18002035d  lea     rcx, [rsp+78h+var_40]
0x180020362  mov     rbx, rdx
0x180020365  shr     r9, 20h
0x180020369  mov     rdx, cs:off_18002D188
0x180020370  mov     edi, r8d
0x180020373  call    wil_details_FeatureReporting_RecordUsageInCache
0x180020378  mov     esi, 1
0x18002037d  movups  xmm1, xmmword ptr [rax]
0x180020380  movups  [rsp+78h+var_28], xmm1
0x180020385  movsd   xmm0, qword ptr [rax+10h]
0x18002038a  mov     rax, cs:g_wil_details_recordFeatureUsage
0x180020391  movsd   [rsp+78h+var_18], xmm0
0x180020397  test    rax, rax
0x18002039a  jz      short loc_1800203BC
0x18002039c  mov     r9, cs:off_18002D188
0x1800203a3  lea     rcx, [rsp+78h+var_28]
0x1800203a8  mov     [rsp+78h+var_58], rcx
0x1800203ad  mov     r8d, esi
0x1800203b0  mov     ecx, 397EF53h
0x1800203b5  mov     edx, edi
0x1800203b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203bc  bt      ebx, 0Ah
0x1800203c0  jnb     short loc_18002043D
0x1800203c2  cmp     edi, 0FEh
0x1800203c8  jz      short loc_18002043D
0x1800203ca  mov     [rsp+78h+var_48], 0
0x1800203d3  mov     dword ptr [rsp+78h+var_48], 397EF53h
0x1800203db  mov     word ptr [rsp+78h+var_48+4], di
0x1800203e0  bt      ebx, 0Bh
0x1800203e4  jnb     short loc_1800203EB
0x1800203e6  or      word ptr [rsp+78h+var_48+6], si
0x1800203eb  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800203f2  test    rax, rax
0x1800203f5  jnz     short loc_180020433
0x1800203f7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800203fe  test    rax, rax
0x180020401  jnz     short loc_180020417
0x180020403  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002040a  call    cs:__imp_GetModuleHandleW
0x180020410  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180020417  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002041e  mov     rcx, rax; hModule
0x180020421  call    cs:__imp_GetProcAddress
0x180020427  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002042e  test    rax, rax
0x180020431  jz      short loc_18002043D
0x180020433  lea     rcx, [rsp+78h+var_48]
0x180020438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002043d  xor     eax, eax
0x18002043f  cmp     dword ptr [rsp+78h+var_18], eax
0x180020443  setz    al
0x180020446  mov     rcx, [rsp+78h+var_10]
0x18002044b  xor     rcx, rsp; StackCookie
0x18002044e  call    __security_check_cookie
0x180020453  lea     r11, [rsp+78h+var_8]
0x180020458  mov     rbx, [r11+10h]
0x18002045c  mov     rsi, [r11+28h]
0x180020460  mov     rsp, r11
0x180020463  pop     rdi
0x180020464  retn
```
