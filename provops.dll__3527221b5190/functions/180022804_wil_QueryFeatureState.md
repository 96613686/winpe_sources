# wil_QueryFeatureState

- ea: `0x180022804`
- end: `0x18002296a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800130b0`

## callees

- `0x180022804`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022889`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022889`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800228a0`

## string_xrefs

- `0x180022882`: `ntdll.dll`
- `0x180022896`: `RtlQueryFeatureConfiguration`

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
0x180022804  mov     [rsp+arg_10], rbx
0x180022809  mov     [rsp+arg_18], rbp
0x18002280e  push    rsi
0x18002280f  push    rdi
0x180022810  push    r14
0x180022812  sub     rsp, 50h
0x180022816  mov     rax, cs:__security_cookie
0x18002281d  xor     rax, rsp
0x180022820  mov     [rsp+68h+var_20], rax
0x180022825  mov     rdi, [rsp+68h+arg_20]
0x18002282d  mov     r14d, edx
0x180022830  mov     rax, [rsp+68h+arg_28]
0x180022838  mov     rsi, rcx
0x18002283b  test    rdi, rdi
0x18002283e  jz      short loc_180022846
0x180022840  mov     dword ptr [rdi], 0
0x180022846  xor     ebp, ebp
0x180022848  mov     [rsp+68h+var_38], 0
0x180022851  test    r8d, r8d
0x180022854  mov     ebx, 1
0x180022859  mov     [rax], ebx
0x18002285b  setz    bpl
0x18002285f  xor     eax, eax
0x180022861  mov     [rsp+68h+var_30], rax
0x180022866  mov     [rsp+68h+var_28], eax
0x18002286a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180022871  test    rax, rax
0x180022874  jnz     short loc_1800228F1
0x180022876  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002287d  test    rax, rax
0x180022880  jnz     short loc_180022896
0x180022882  lea     rcx, ModuleName; "ntdll.dll"
0x180022889  call    cs:__imp_GetModuleHandleW
0x18002288f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022896  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002289d  mov     rcx, rax; hModule
0x1800228a0  call    cs:__imp_GetProcAddress
0x1800228a6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800228ad  test    rax, rax
0x1800228b0  jnz     short loc_1800228F1
0x1800228b2  mov     r8d, 0C0000139h
0x1800228b8  xor     ebx, ebx
0x1800228ba  test    rdi, rdi
0x1800228bd  jz      short loc_1800228CD
0x1800228bf  xor     ecx, ecx
0x1800228c1  cmp     r8d, 80000022h
0x1800228c8  setnz   cl
0x1800228cb  mov     [rdi], ecx
0x1800228cd  mov     eax, ebx
0x1800228cf  mov     rcx, [rsp+68h+var_20]
0x1800228d4  xor     rcx, rsp; StackCookie
0x1800228d7  call    __security_check_cookie
0x1800228dc  lea     r11, [rsp+68h+var_18]
0x1800228e1  mov     rbx, [r11+30h]
0x1800228e5  mov     rbp, [r11+38h]
0x1800228e9  mov     rsp, r11
0x1800228ec  pop     r14
0x1800228ee  pop     rdi
0x1800228ef  pop     rsi
0x1800228f0  retn
0x1800228f1  lea     r9, [rsp+68h+var_30]
0x1800228f6  mov     edx, ebp
0x1800228f8  lea     r8, [rsp+68h+var_38]
0x1800228fd  mov     ecx, r14d
0x180022900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022905  mov     r8d, eax
0x180022908  test    eax, eax
0x18002290a  jnz     short loc_18002294E
0x18002290c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180022910  mov     ecx, edx
0x180022912  mov     eax, [rsp+68h+var_28]
0x180022916  mov     [rsi+0Ch], eax
0x180022919  mov     eax, edx
0x18002291b  shr     eax, 0Eh
0x18002291e  shr     ecx, 4
0x180022921  and     eax, 3
0x180022924  and     ecx, 3
0x180022927  mov     [rsi+8], eax
0x18002292a  mov     [rsi], ecx
0x18002292c  mov     eax, edx
0x18002292e  mov     ecx, edx
0x180022930  shr     eax, 6
0x180022933  shr     ecx, 8
0x180022936  and     eax, ebx
0x180022938  and     cl, 3Fh
0x18002293b  shr     edx, 7
0x18002293e  and     edx, ebx
0x180022940  mov     [rsi+4], cl
0x180022943  mov     [rsi+10h], edx
0x180022946  mov     [rsi+14h], eax
0x180022949  jmp     loc_1800228BA
0x18002294e  cmp     eax, 117h
0x180022953  jnz     loc_1800228B8
0x180022959  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002295d  shr     eax, 7
0x180022960  and     eax, ebx
0x180022962  mov     [rsi+10h], eax
0x180022965  jmp     loc_1800228BA
```
