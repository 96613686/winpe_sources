# wil_QueryFeatureState

- ea: `0x180025138`
- end: `0x18002529e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180018548`

## callees

- `0x180025138`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800251bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800251bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800251d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800251d4`

## string_xrefs

- `0x1800251b6`: `ntdll.dll`
- `0x1800251ca`: `RtlQueryFeatureConfiguration`

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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180025138  mov     [rsp+arg_10], rbx
0x18002513d  mov     [rsp+arg_18], rbp
0x180025142  push    rsi
0x180025143  push    rdi
0x180025144  push    r14
0x180025146  sub     rsp, 50h
0x18002514a  mov     rax, cs:__security_cookie
0x180025151  xor     rax, rsp
0x180025154  mov     [rsp+68h+var_20], rax
0x180025159  mov     rdi, [rsp+68h+arg_20]
0x180025161  mov     r14d, edx
0x180025164  mov     rax, [rsp+68h+arg_28]
0x18002516c  mov     rsi, rcx
0x18002516f  test    rdi, rdi
0x180025172  jz      short loc_18002517A
0x180025174  mov     dword ptr [rdi], 0
0x18002517a  xor     ebp, ebp
0x18002517c  mov     [rsp+68h+var_38], 0
0x180025185  test    r8d, r8d
0x180025188  mov     ebx, 1
0x18002518d  mov     [rax], ebx
0x18002518f  setz    bpl
0x180025193  xor     eax, eax
0x180025195  mov     [rsp+68h+var_30], rax
0x18002519a  mov     [rsp+68h+var_28], eax
0x18002519e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800251a5  test    rax, rax
0x1800251a8  jnz     short loc_180025225
0x1800251aa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800251b1  test    rax, rax
0x1800251b4  jnz     short loc_1800251CA
0x1800251b6  lea     rcx, ModuleName; "ntdll.dll"
0x1800251bd  call    cs:__imp_GetModuleHandleW
0x1800251c3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800251ca  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800251d1  mov     rcx, rax; hModule
0x1800251d4  call    cs:__imp_GetProcAddress
0x1800251da  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800251e1  test    rax, rax
0x1800251e4  jnz     short loc_180025225
0x1800251e6  mov     r8d, 0C0000139h
0x1800251ec  xor     ebx, ebx
0x1800251ee  test    rdi, rdi
0x1800251f1  jz      short loc_180025201
0x1800251f3  xor     ecx, ecx
0x1800251f5  cmp     r8d, 80000022h
0x1800251fc  setnz   cl
0x1800251ff  mov     [rdi], ecx
0x180025201  mov     eax, ebx
0x180025203  mov     rcx, [rsp+68h+var_20]
0x180025208  xor     rcx, rsp; StackCookie
0x18002520b  call    __security_check_cookie
0x180025210  lea     r11, [rsp+68h+var_18]
0x180025215  mov     rbx, [r11+30h]
0x180025219  mov     rbp, [r11+38h]
0x18002521d  mov     rsp, r11
0x180025220  pop     r14
0x180025222  pop     rdi
0x180025223  pop     rsi
0x180025224  retn
0x180025225  lea     r9, [rsp+68h+var_30]
0x18002522a  mov     edx, ebp
0x18002522c  lea     r8, [rsp+68h+var_38]
0x180025231  mov     ecx, r14d
0x180025234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025239  mov     r8d, eax
0x18002523c  test    eax, eax
0x18002523e  jnz     short loc_180025282
0x180025240  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180025244  mov     ecx, edx
0x180025246  mov     eax, [rsp+68h+var_28]
0x18002524a  mov     [rsi+0Ch], eax
0x18002524d  mov     eax, edx
0x18002524f  shr     eax, 0Eh
0x180025252  shr     ecx, 4
0x180025255  and     eax, 3
0x180025258  and     ecx, 3
0x18002525b  mov     [rsi+8], eax
0x18002525e  mov     [rsi], ecx
0x180025260  mov     eax, edx
0x180025262  mov     ecx, edx
0x180025264  shr     eax, 6
0x180025267  shr     ecx, 8
0x18002526a  and     eax, ebx
0x18002526c  and     cl, 3Fh
0x18002526f  shr     edx, 7
0x180025272  and     edx, ebx
0x180025274  mov     [rsi+4], cl
0x180025277  mov     [rsi+10h], edx
0x18002527a  mov     [rsi+14h], eax
0x18002527d  jmp     loc_1800251EE
0x180025282  cmp     eax, 117h
0x180025287  jnz     loc_1800251EC
0x18002528d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180025291  shr     eax, 7
0x180025294  and     eax, ebx
0x180025296  mov     [rsi+10h], eax
0x180025299  jmp     loc_1800251EE
```
