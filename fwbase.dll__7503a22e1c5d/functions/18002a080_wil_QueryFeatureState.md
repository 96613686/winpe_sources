# wil_QueryFeatureState

- ea: `0x18002a080`
- end: `0x18002a1e6`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025030`

## callees

- `0x18001e1d0`
- `0x18002a080`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a105`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a105`

## string_xrefs

- `0x18002a0fe`: `ntdll.dll`
- `0x18002a112`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  __int64 result; // rax
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+38h] [rbp-30h]
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF

  if ( a5 )
    *a5 = 0;
  v19 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v17 = 0;
  v18 = 0;
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
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v19, &v17);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v17);
    v16 = HIDWORD(v17);
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v16 >> 14;
    *(_DWORD *)a1 = (v16 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
  }
LABEL_9:
  result = v8;
  if ( a5 )
    *a5 = v12 != -2147483614;
  return result;
}

```

## disassembly

```asm
0x18002a080  mov     [rsp+arg_10], rbx
0x18002a085  mov     [rsp+arg_18], rbp
0x18002a08a  push    rsi
0x18002a08b  push    rdi
0x18002a08c  push    r14
0x18002a08e  sub     rsp, 50h
0x18002a092  mov     rax, cs:__security_cookie
0x18002a099  xor     rax, rsp
0x18002a09c  mov     [rsp+68h+var_20], rax
0x18002a0a1  mov     rdi, [rsp+68h+arg_20]
0x18002a0a9  mov     r14d, edx
0x18002a0ac  mov     rax, [rsp+68h+arg_28]
0x18002a0b4  mov     rsi, rcx
0x18002a0b7  test    rdi, rdi
0x18002a0ba  jz      short loc_18002A0C2
0x18002a0bc  mov     dword ptr [rdi], 0
0x18002a0c2  xor     ebp, ebp
0x18002a0c4  mov     [rsp+68h+var_28], 0
0x18002a0cd  test    r8d, r8d
0x18002a0d0  mov     ebx, 1
0x18002a0d5  mov     [rax], ebx
0x18002a0d7  setz    bpl
0x18002a0db  xor     eax, eax
0x18002a0dd  mov     [rsp+68h+var_38], rax
0x18002a0e2  mov     [rsp+68h+var_30], eax
0x18002a0e6  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002a0ed  test    rax, rax
0x18002a0f0  jnz     short loc_18002A16D
0x18002a0f2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a0f9  test    rax, rax
0x18002a0fc  jnz     short loc_18002A112
0x18002a0fe  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002a105  call    cs:__imp_GetModuleHandleW
0x18002a10b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002a112  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002a119  mov     rcx, rax; hModule
0x18002a11c  call    cs:__imp_GetProcAddress
0x18002a122  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002a129  test    rax, rax
0x18002a12c  jnz     short loc_18002A16D
0x18002a12e  mov     r8d, 0C0000139h
0x18002a134  xor     ebx, ebx
0x18002a136  mov     eax, ebx
0x18002a138  test    rdi, rdi
0x18002a13b  jz      short loc_18002A14B
0x18002a13d  xor     ecx, ecx
0x18002a13f  cmp     r8d, 80000022h
0x18002a146  setnz   cl
0x18002a149  mov     [rdi], ecx
0x18002a14b  mov     rcx, [rsp+68h+var_20]
0x18002a150  xor     rcx, rsp; StackCookie
0x18002a153  call    __security_check_cookie
0x18002a158  lea     r11, [rsp+68h+var_18]
0x18002a15d  mov     rbx, [r11+30h]
0x18002a161  mov     rbp, [r11+38h]
0x18002a165  mov     rsp, r11
0x18002a168  pop     r14
0x18002a16a  pop     rdi
0x18002a16b  pop     rsi
0x18002a16c  retn
0x18002a16d  lea     r9, [rsp+68h+var_38]
0x18002a172  mov     edx, ebp
0x18002a174  lea     r8, [rsp+68h+var_28]
0x18002a179  mov     ecx, r14d
0x18002a17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a181  mov     r8d, eax
0x18002a184  test    eax, eax
0x18002a186  jnz     short loc_18002A1CA
0x18002a188  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18002a18c  mov     ecx, edx
0x18002a18e  mov     eax, [rsp+68h+var_30]
0x18002a192  mov     [rsi+0Ch], eax
0x18002a195  mov     eax, edx
0x18002a197  shr     eax, 0Eh
0x18002a19a  shr     ecx, 4
0x18002a19d  and     eax, 3
0x18002a1a0  and     ecx, 3
0x18002a1a3  mov     [rsi+8], eax
0x18002a1a6  mov     [rsi], ecx
0x18002a1a8  mov     eax, edx
0x18002a1aa  mov     ecx, edx
0x18002a1ac  shr     eax, 6
0x18002a1af  shr     ecx, 8
0x18002a1b2  and     eax, ebx
0x18002a1b4  and     cl, 3Fh
0x18002a1b7  shr     edx, 7
0x18002a1ba  and     edx, ebx
0x18002a1bc  mov     [rsi+4], cl
0x18002a1bf  mov     [rsi+10h], edx
0x18002a1c2  mov     [rsi+14h], eax
0x18002a1c5  jmp     loc_18002A136
0x18002a1ca  cmp     eax, 117h
0x18002a1cf  jnz     loc_18002A134
0x18002a1d5  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18002a1d9  shr     eax, 7
0x18002a1dc  and     eax, ebx
0x18002a1de  mov     [rsi+10h], eax
0x18002a1e1  jmp     loc_18002A136
```
