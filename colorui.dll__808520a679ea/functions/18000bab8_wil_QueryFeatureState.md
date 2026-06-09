# wil_QueryFeatureState

- ea: `0x18000bab8`
- end: `0x18000bc1e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006798`

## callees

- `0x18000bab8`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000bb54`
- `KERNEL32!GetProcAddress` at `0x18000bb54`
- `KERNEL32!GetModuleHandleW` at `0x18000bb3d`
- `KERNEL32!GetModuleHandleW` at `0x18000bb3d`

## string_xrefs

- `0x18000bb36`: `ntdll.dll`
- `0x18000bb4a`: `RtlQueryFeatureConfiguration`

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
0x18000bab8  mov     [rsp+arg_10], rbx
0x18000babd  mov     [rsp+arg_18], rbp
0x18000bac2  push    rsi
0x18000bac3  push    rdi
0x18000bac4  push    r14
0x18000bac6  sub     rsp, 50h
0x18000baca  mov     rax, cs:__security_cookie
0x18000bad1  xor     rax, rsp
0x18000bad4  mov     [rsp+68h+var_20], rax
0x18000bad9  mov     rdi, [rsp+68h+arg_20]
0x18000bae1  mov     r14d, edx
0x18000bae4  mov     rax, [rsp+68h+arg_28]
0x18000baec  mov     rsi, rcx
0x18000baef  test    rdi, rdi
0x18000baf2  jz      short loc_18000BAFA
0x18000baf4  mov     dword ptr [rdi], 0
0x18000bafa  xor     ebp, ebp
0x18000bafc  mov     [rsp+68h+var_38], 0
0x18000bb05  test    r8d, r8d
0x18000bb08  mov     ebx, 1
0x18000bb0d  mov     [rax], ebx
0x18000bb0f  setz    bpl
0x18000bb13  xor     eax, eax
0x18000bb15  mov     [rsp+68h+var_30], rax
0x18000bb1a  mov     [rsp+68h+var_28], eax
0x18000bb1e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000bb25  test    rax, rax
0x18000bb28  jnz     short loc_18000BBA5
0x18000bb2a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb31  test    rax, rax
0x18000bb34  jnz     short loc_18000BB4A
0x18000bb36  lea     rcx, ModuleName; "ntdll.dll"
0x18000bb3d  call    cs:__imp_GetModuleHandleW
0x18000bb43  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000bb4a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000bb51  mov     rcx, rax; hModule
0x18000bb54  call    cs:__imp_GetProcAddress
0x18000bb5a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000bb61  test    rax, rax
0x18000bb64  jnz     short loc_18000BBA5
0x18000bb66  mov     r8d, 0C0000139h
0x18000bb6c  xor     ebx, ebx
0x18000bb6e  test    rdi, rdi
0x18000bb71  jz      short loc_18000BB81
0x18000bb73  xor     ecx, ecx
0x18000bb75  cmp     r8d, 80000022h
0x18000bb7c  setnz   cl
0x18000bb7f  mov     [rdi], ecx
0x18000bb81  mov     eax, ebx
0x18000bb83  mov     rcx, [rsp+68h+var_20]
0x18000bb88  xor     rcx, rsp; StackCookie
0x18000bb8b  call    __security_check_cookie
0x18000bb90  lea     r11, [rsp+68h+var_18]
0x18000bb95  mov     rbx, [r11+30h]
0x18000bb99  mov     rbp, [r11+38h]
0x18000bb9d  mov     rsp, r11
0x18000bba0  pop     r14
0x18000bba2  pop     rdi
0x18000bba3  pop     rsi
0x18000bba4  retn
0x18000bba5  lea     r9, [rsp+68h+var_30]
0x18000bbaa  mov     edx, ebp
0x18000bbac  lea     r8, [rsp+68h+var_38]
0x18000bbb1  mov     ecx, r14d
0x18000bbb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb9  mov     r8d, eax
0x18000bbbc  test    eax, eax
0x18000bbbe  jnz     short loc_18000BC02
0x18000bbc0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000bbc4  mov     ecx, edx
0x18000bbc6  mov     eax, [rsp+68h+var_28]
0x18000bbca  mov     [rsi+0Ch], eax
0x18000bbcd  mov     eax, edx
0x18000bbcf  shr     eax, 0Eh
0x18000bbd2  shr     ecx, 4
0x18000bbd5  and     eax, 3
0x18000bbd8  and     ecx, 3
0x18000bbdb  mov     [rsi+8], eax
0x18000bbde  mov     [rsi], ecx
0x18000bbe0  mov     eax, edx
0x18000bbe2  mov     ecx, edx
0x18000bbe4  shr     eax, 6
0x18000bbe7  shr     ecx, 8
0x18000bbea  and     eax, ebx
0x18000bbec  and     cl, 3Fh
0x18000bbef  shr     edx, 7
0x18000bbf2  and     edx, ebx
0x18000bbf4  mov     [rsi+4], cl
0x18000bbf7  mov     [rsi+10h], edx
0x18000bbfa  mov     [rsi+14h], eax
0x18000bbfd  jmp     loc_18000BB6E
0x18000bc02  cmp     eax, 117h
0x18000bc07  jnz     loc_18000BB6C
0x18000bc0d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000bc11  shr     eax, 7
0x18000bc14  and     eax, ebx
0x18000bc16  mov     [rsi+10h], eax
0x18000bc19  jmp     loc_18000BB6E
```
