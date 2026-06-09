# wil_QueryFeatureState

- ea: `0x140014458`
- end: `0x1400145be`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140010754`

## callees

- `0x140002f60`
- `0x140014458`
- `0x14003e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400144f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400144f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400144dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400144dd`

## string_xrefs

- `0x1400144d6`: `ntdll.dll`
- `0x1400144ea`: `RtlQueryFeatureConfiguration`

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
0x140014458  mov     [rsp+arg_10], rbx
0x14001445d  mov     [rsp+arg_18], rbp
0x140014462  push    rsi
0x140014463  push    rdi
0x140014464  push    r14
0x140014466  sub     rsp, 50h
0x14001446a  mov     rax, cs:__security_cookie
0x140014471  xor     rax, rsp
0x140014474  mov     [rsp+68h+var_20], rax
0x140014479  mov     rdi, [rsp+68h+arg_20]
0x140014481  mov     r14d, edx
0x140014484  mov     rax, [rsp+68h+arg_28]
0x14001448c  mov     rsi, rcx
0x14001448f  test    rdi, rdi
0x140014492  jz      short loc_14001449A
0x140014494  mov     dword ptr [rdi], 0
0x14001449a  xor     ebp, ebp
0x14001449c  mov     [rsp+68h+var_38], 0
0x1400144a5  test    r8d, r8d
0x1400144a8  mov     ebx, 1
0x1400144ad  mov     [rax], ebx
0x1400144af  setz    bpl
0x1400144b3  xor     eax, eax
0x1400144b5  mov     [rsp+68h+var_30], rax
0x1400144ba  mov     [rsp+68h+var_28], eax
0x1400144be  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1400144c5  test    rax, rax
0x1400144c8  jnz     short loc_140014545
0x1400144ca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400144d1  test    rax, rax
0x1400144d4  jnz     short loc_1400144EA
0x1400144d6  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400144dd  call    cs:__imp_GetModuleHandleW
0x1400144e3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400144ea  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1400144f1  mov     rcx, rax; hModule
0x1400144f4  call    cs:__imp_GetProcAddress
0x1400144fa  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140014501  test    rax, rax
0x140014504  jnz     short loc_140014545
0x140014506  mov     r8d, 0C0000139h
0x14001450c  xor     ebx, ebx
0x14001450e  test    rdi, rdi
0x140014511  jz      short loc_140014521
0x140014513  xor     ecx, ecx
0x140014515  cmp     r8d, 80000022h
0x14001451c  setnz   cl
0x14001451f  mov     [rdi], ecx
0x140014521  mov     eax, ebx
0x140014523  mov     rcx, [rsp+68h+var_20]
0x140014528  xor     rcx, rsp; StackCookie
0x14001452b  call    __security_check_cookie
0x140014530  lea     r11, [rsp+68h+var_18]
0x140014535  mov     rbx, [r11+30h]
0x140014539  mov     rbp, [r11+38h]
0x14001453d  mov     rsp, r11
0x140014540  pop     r14
0x140014542  pop     rdi
0x140014543  pop     rsi
0x140014544  retn
0x140014545  lea     r9, [rsp+68h+var_30]
0x14001454a  mov     edx, ebp
0x14001454c  lea     r8, [rsp+68h+var_38]
0x140014551  mov     ecx, r14d
0x140014554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014559  mov     r8d, eax
0x14001455c  test    eax, eax
0x14001455e  jnz     short loc_1400145A2
0x140014560  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140014564  mov     ecx, edx
0x140014566  mov     eax, [rsp+68h+var_28]
0x14001456a  mov     [rsi+0Ch], eax
0x14001456d  mov     eax, edx
0x14001456f  shr     eax, 0Eh
0x140014572  shr     ecx, 4
0x140014575  and     eax, 3
0x140014578  and     ecx, 3
0x14001457b  mov     [rsi+8], eax
0x14001457e  mov     [rsi], ecx
0x140014580  mov     eax, edx
0x140014582  mov     ecx, edx
0x140014584  shr     eax, 6
0x140014587  shr     ecx, 8
0x14001458a  and     eax, ebx
0x14001458c  and     cl, 3Fh
0x14001458f  shr     edx, 7
0x140014592  and     edx, ebx
0x140014594  mov     [rsi+4], cl
0x140014597  mov     [rsi+10h], edx
0x14001459a  mov     [rsi+14h], eax
0x14001459d  jmp     loc_14001450E
0x1400145a2  cmp     eax, 117h
0x1400145a7  jnz     loc_14001450C
0x1400145ad  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1400145b1  shr     eax, 7
0x1400145b4  and     eax, ebx
0x1400145b6  mov     [rsi+10h], eax
0x1400145b9  jmp     loc_14001450E
```
