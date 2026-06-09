# wil_QueryFeatureState

- ea: `0x18000ac98`
- end: `0x18000adfe`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006d28`

## callees

- `0x1800024a0`
- `0x18000ac98`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ad34`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ad1d`

## string_xrefs

- `0x18000ad16`: `ntdll.dll`
- `0x18000ad2a`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v17 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v18 = 0;
  v19 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v12 = -1073741511;
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v17, &v18);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v18) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v18);
    v16 = HIDWORD(v18);
    *(_DWORD *)(a1 + 12) = v19;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v16 >> 14;
    *(_DWORD *)a1 = (v16 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
  }
LABEL_9:
  if ( a5 )
    *a5 = v12 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x18000ac98  mov     [rsp+arg_10], rbx
0x18000ac9d  mov     [rsp+arg_18], rbp
0x18000aca2  push    rsi
0x18000aca3  push    rdi
0x18000aca4  push    r14
0x18000aca6  sub     rsp, 50h
0x18000acaa  mov     rax, cs:__security_cookie
0x18000acb1  xor     rax, rsp
0x18000acb4  mov     [rsp+68h+var_20], rax
0x18000acb9  mov     rdi, [rsp+68h+arg_20]
0x18000acc1  mov     r14d, edx
0x18000acc4  mov     rax, [rsp+68h+arg_28]
0x18000accc  mov     rsi, rcx
0x18000accf  test    rdi, rdi
0x18000acd2  jz      short loc_18000ACDA
0x18000acd4  mov     dword ptr [rdi], 0
0x18000acda  xor     ebp, ebp
0x18000acdc  mov     [rsp+68h+var_38], 0
0x18000ace5  test    r8d, r8d
0x18000ace8  mov     ebx, 1
0x18000aced  mov     [rax], ebx
0x18000acef  setz    bpl
0x18000acf3  xor     eax, eax
0x18000acf5  mov     [rsp+68h+var_30], rax
0x18000acfa  mov     [rsp+68h+var_28], eax
0x18000acfe  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ad05  test    rax, rax
0x18000ad08  jnz     short loc_18000AD85
0x18000ad0a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ad11  test    rax, rax
0x18000ad14  jnz     short loc_18000AD2A
0x18000ad16  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000ad1d  call    cs:__imp_GetModuleHandleW
0x18000ad23  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ad2a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ad31  mov     rcx, rax; hModule
0x18000ad34  call    cs:__imp_GetProcAddress
0x18000ad3a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ad41  test    rax, rax
0x18000ad44  jnz     short loc_18000AD85
0x18000ad46  mov     r8d, 0C0000139h
0x18000ad4c  xor     ebx, ebx
0x18000ad4e  test    rdi, rdi
0x18000ad51  jz      short loc_18000AD61
0x18000ad53  xor     ecx, ecx
0x18000ad55  cmp     r8d, 80000022h
0x18000ad5c  setnz   cl
0x18000ad5f  mov     [rdi], ecx
0x18000ad61  mov     eax, ebx
0x18000ad63  mov     rcx, [rsp+68h+var_20]
0x18000ad68  xor     rcx, rsp; StackCookie
0x18000ad6b  call    __security_check_cookie
0x18000ad70  lea     r11, [rsp+68h+var_18]
0x18000ad75  mov     rbx, [r11+30h]
0x18000ad79  mov     rbp, [r11+38h]
0x18000ad7d  mov     rsp, r11
0x18000ad80  pop     r14
0x18000ad82  pop     rdi
0x18000ad83  pop     rsi
0x18000ad84  retn
0x18000ad85  lea     r9, [rsp+68h+var_30]
0x18000ad8a  mov     edx, ebp
0x18000ad8c  lea     r8, [rsp+68h+var_38]
0x18000ad91  mov     ecx, r14d
0x18000ad94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad99  mov     r8d, eax
0x18000ad9c  test    eax, eax
0x18000ad9e  jnz     short loc_18000ADE2
0x18000ada0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000ada4  mov     ecx, edx
0x18000ada6  mov     eax, [rsp+68h+var_28]
0x18000adaa  mov     [rsi+0Ch], eax
0x18000adad  mov     eax, edx
0x18000adaf  shr     eax, 0Eh
0x18000adb2  shr     ecx, 4
0x18000adb5  and     eax, 3
0x18000adb8  and     ecx, 3
0x18000adbb  mov     [rsi+8], eax
0x18000adbe  mov     [rsi], ecx
0x18000adc0  mov     eax, edx
0x18000adc2  mov     ecx, edx
0x18000adc4  shr     eax, 6
0x18000adc7  shr     ecx, 8
0x18000adca  and     eax, ebx
0x18000adcc  and     cl, 3Fh
0x18000adcf  shr     edx, 7
0x18000add2  and     edx, ebx
0x18000add4  mov     [rsi+4], cl
0x18000add7  mov     [rsi+10h], edx
0x18000adda  mov     [rsi+14h], eax
0x18000addd  jmp     loc_18000AD4E
0x18000ade2  cmp     eax, 117h
0x18000ade7  jnz     loc_18000AD4C
0x18000aded  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000adf1  shr     eax, 7
0x18000adf4  and     eax, ebx
0x18000adf6  mov     [rsi+10h], eax
0x18000adf9  jmp     loc_18000AD4E
```
