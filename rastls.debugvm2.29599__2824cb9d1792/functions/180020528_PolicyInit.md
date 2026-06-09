# PolicyInit

- ea: `0x180020528`
- end: `0x18002061c`
- name: `PolicyInit`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180020470`
- `0x1800649f8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180020528`
- `0x180033284`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020562`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020562`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800205db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020574`

## string_xrefs

- `0x180020559`: `policymanager.dll`

## pseudocode

```c
FARPROC PolicyInit()
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  FARPROC ProcAddress; // rax
  struct _EAPTLS_CONTROL_BLOCK *v3; // rcx
  __int64 v4; // rdx
  FARPROC result; // rax

  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
  Library = LoadLibraryExW(L"policymanager.dll", 0, 0);
  g_hPolicyExtLib = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
    return (FARPROC)PolicyDeInit();
  }
  ProcAddress = GetProcAddress(Library, "PolicyManager_IsPolicySetByMobileDeviceManager");
  if ( !ProcAddress )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v4 = 14;
LABEL_12:
      WPP_SF_(*((_QWORD *)v3 + 2), v4, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
      return (FARPROC)PolicyDeInit();
    }
    return (FARPROC)PolicyDeInit();
  }
  g_PolicyExtLibFunctionTable = ProcAddress;
  result = GetProcAddress(g_hPolicyExtLib, "PolicyManager_GetPolicyInt");
  if ( !result )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v4 = 15;
      goto LABEL_12;
    }
    return (FARPROC)PolicyDeInit();
  }
  *(&g_PolicyExtLibFunctionTable + 1) = result;
  return result;
}

```

## disassembly

```asm
0x180020528  push    rbx
0x18002052a  sub     rsp, 20h
0x18002052e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020535  lea     rbx, WPP_GLOBAL_Control
0x18002053c  cmp     rcx, rbx
0x18002053f  jz      short loc_180020556
0x180020541  mov     rcx, [rcx+10h]
0x180020545  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18002054c  mov     edx, 0Ch
0x180020551  call    WPP_SF_
0x180020556  xor     r8d, r8d; dwFlags
0x180020559  lea     rcx, LibFileName; "policymanager.dll"
0x180020560  xor     edx, edx; hFile
0x180020562  call    cs:__imp_LoadLibraryExW
0x180020568  mov     cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hPolicyExtLib
0x18002056f  test    rax, rax
0x180020572  jnz     short loc_1800205A0
0x180020574  call    cs:__imp_GetLastError
0x18002057a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020581  cmp     rcx, rbx
0x180020584  jz      short loc_180020605
0x180020586  mov     rcx, [rcx+10h]
0x18002058a  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180020591  mov     edx, 0Dh
0x180020596  mov     r9d, eax
0x180020599  call    WPP_SF_d
0x18002059e  jmp     short loc_180020605
0x1800205a0  lea     rdx, aPolicymanagerI; "PolicyManager_IsPolicySetByMobileDevice"...
0x1800205a7  mov     rcx, rax; hModule
0x1800205aa  call    cs:__imp_GetProcAddress
0x1800205b0  test    rax, rax
0x1800205b3  jnz     short loc_1800205C6
0x1800205b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205bc  cmp     rcx, rbx
0x1800205bf  jz      short loc_180020605
0x1800205c1  lea     edx, [rax+0Eh]
0x1800205c4  jmp     short loc_1800205F5
0x1800205c6  mov     rcx, cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA; hModule
0x1800205cd  lea     rdx, aPolicymanagerG; "PolicyManager_GetPolicyInt"
0x1800205d4  mov     qword ptr cs:?g_PolicyExtLibFunctionTable@@3U_POLICYEXTLIB_FUNCTION_TABLE@@A, rax; _POLICYEXTLIB_FUNCTION_TABLE g_PolicyExtLibFunctionTable
0x1800205db  call    cs:__imp_GetProcAddress
0x1800205e1  test    rax, rax
0x1800205e4  jnz     short loc_18002060F
0x1800205e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205ed  cmp     rcx, rbx
0x1800205f0  jz      short loc_180020605
0x1800205f2  lea     edx, [rax+0Fh]
0x1800205f5  mov     rcx, [rcx+10h]
0x1800205f9  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180020600  call    WPP_SF_
0x180020605  add     rsp, 20h
0x180020609  pop     rbx
0x18002060a  jmp     PolicyDeInit
0x18002060f  mov     qword ptr cs:?g_PolicyExtLibFunctionTable@@3U_POLICYEXTLIB_FUNCTION_TABLE@@A+8, rax; _POLICYEXTLIB_FUNCTION_TABLE g_PolicyExtLibFunctionTable
0x180020616  add     rsp, 20h
0x18002061a  pop     rbx
0x18002061b  retn
```
