# wil_QueryFeatureState

- ea: `0x18000c428`
- end: `0x18000c58e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800089d0`

## callees

- `0x180003080`
- `0x18000c428`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c4ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c4ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c4c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c4c4`

## string_xrefs

- `0x18000c4a6`: `ntdll.dll`
- `0x18000c4ba`: `RtlQueryFeatureConfiguration`

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
0x18000c428  mov     [rsp+arg_10], rbx
0x18000c42d  mov     [rsp+arg_18], rbp
0x18000c432  push    rsi
0x18000c433  push    rdi
0x18000c434  push    r14
0x18000c436  sub     rsp, 50h
0x18000c43a  mov     rax, cs:__security_cookie
0x18000c441  xor     rax, rsp
0x18000c444  mov     [rsp+68h+var_20], rax
0x18000c449  mov     rdi, [rsp+68h+arg_20]
0x18000c451  mov     r14d, edx
0x18000c454  mov     rax, [rsp+68h+arg_28]
0x18000c45c  mov     rsi, rcx
0x18000c45f  test    rdi, rdi
0x18000c462  jz      short loc_18000C46A
0x18000c464  mov     dword ptr [rdi], 0
0x18000c46a  xor     ebp, ebp
0x18000c46c  mov     [rsp+68h+var_38], 0
0x18000c475  test    r8d, r8d
0x18000c478  mov     ebx, 1
0x18000c47d  mov     [rax], ebx
0x18000c47f  setz    bpl
0x18000c483  xor     eax, eax
0x18000c485  mov     [rsp+68h+var_30], rax
0x18000c48a  mov     [rsp+68h+var_28], eax
0x18000c48e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000c495  test    rax, rax
0x18000c498  jnz     short loc_18000C515
0x18000c49a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c4a1  test    rax, rax
0x18000c4a4  jnz     short loc_18000C4BA
0x18000c4a6  lea     rcx, ModuleName; "ntdll.dll"
0x18000c4ad  call    cs:__imp_GetModuleHandleW
0x18000c4b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c4ba  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000c4c1  mov     rcx, rax; hModule
0x18000c4c4  call    cs:__imp_GetProcAddress
0x18000c4ca  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000c4d1  test    rax, rax
0x18000c4d4  jnz     short loc_18000C515
0x18000c4d6  mov     r8d, 0C0000139h
0x18000c4dc  xor     ebx, ebx
0x18000c4de  test    rdi, rdi
0x18000c4e1  jz      short loc_18000C4F1
0x18000c4e3  xor     ecx, ecx
0x18000c4e5  cmp     r8d, 80000022h
0x18000c4ec  setnz   cl
0x18000c4ef  mov     [rdi], ecx
0x18000c4f1  mov     eax, ebx
0x18000c4f3  mov     rcx, [rsp+68h+var_20]
0x18000c4f8  xor     rcx, rsp; StackCookie
0x18000c4fb  call    __security_check_cookie
0x18000c500  lea     r11, [rsp+68h+var_18]
0x18000c505  mov     rbx, [r11+30h]
0x18000c509  mov     rbp, [r11+38h]
0x18000c50d  mov     rsp, r11
0x18000c510  pop     r14
0x18000c512  pop     rdi
0x18000c513  pop     rsi
0x18000c514  retn
0x18000c515  lea     r9, [rsp+68h+var_30]
0x18000c51a  mov     edx, ebp
0x18000c51c  lea     r8, [rsp+68h+var_38]
0x18000c521  mov     ecx, r14d
0x18000c524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c529  mov     r8d, eax
0x18000c52c  test    eax, eax
0x18000c52e  jnz     short loc_18000C572
0x18000c530  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000c534  mov     ecx, edx
0x18000c536  mov     eax, [rsp+68h+var_28]
0x18000c53a  mov     [rsi+0Ch], eax
0x18000c53d  mov     eax, edx
0x18000c53f  shr     eax, 0Eh
0x18000c542  shr     ecx, 4
0x18000c545  and     eax, 3
0x18000c548  and     ecx, 3
0x18000c54b  mov     [rsi+8], eax
0x18000c54e  mov     [rsi], ecx
0x18000c550  mov     eax, edx
0x18000c552  mov     ecx, edx
0x18000c554  shr     eax, 6
0x18000c557  shr     ecx, 8
0x18000c55a  and     eax, ebx
0x18000c55c  and     cl, 3Fh
0x18000c55f  shr     edx, 7
0x18000c562  and     edx, ebx
0x18000c564  mov     [rsi+4], cl
0x18000c567  mov     [rsi+10h], edx
0x18000c56a  mov     [rsi+14h], eax
0x18000c56d  jmp     loc_18000C4DE
0x18000c572  cmp     eax, 117h
0x18000c577  jnz     loc_18000C4DC
0x18000c57d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000c581  shr     eax, 7
0x18000c584  and     eax, ebx
0x18000c586  mov     [rsi+10h], eax
0x18000c589  jmp     loc_18000C4DE
```
