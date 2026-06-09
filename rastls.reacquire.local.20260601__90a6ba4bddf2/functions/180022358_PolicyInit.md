# PolicyInit

- ea: `0x180022358`
- end: `0x180022469`
- name: `PolicyInit`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800222a0`
- `0x18006853c`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180022358`
- `0x180035b9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022392`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022392`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022421`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800223ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223aa`

## string_xrefs

- `0x180022389`: `policymanager.dll`

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
0x180022358  push    rbx
0x18002235a  sub     rsp, 20h
0x18002235e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022365  lea     rbx, WPP_GLOBAL_Control
0x18002236c  cmp     rcx, rbx
0x18002236f  jz      short loc_180022386
0x180022371  mov     rcx, [rcx+10h]
0x180022375  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18002237c  mov     edx, 0Ch
0x180022381  call    WPP_SF_
0x180022386  xor     r8d, r8d; dwFlags
0x180022389  lea     rcx, LibFileName; "policymanager.dll"
0x180022390  xor     edx, edx; hFile
0x180022392  call    cs:__imp_LoadLibraryExW
0x180022399  nop     dword ptr [rax+rax+00h]
0x18002239e  mov     cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hPolicyExtLib
0x1800223a5  test    rax, rax
0x1800223a8  jnz     short loc_1800223E0
0x1800223aa  call    cs:__imp_GetLastError
0x1800223b1  nop     dword ptr [rax+rax+00h]
0x1800223b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223bd  cmp     rcx, rbx
0x1800223c0  jz      loc_180022451
0x1800223c6  mov     rcx, [rcx+10h]
0x1800223ca  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800223d1  mov     edx, 0Dh
0x1800223d6  mov     r9d, eax
0x1800223d9  call    WPP_SF_d
0x1800223de  jmp     short loc_180022451
0x1800223e0  lea     rdx, aPolicymanagerI; "PolicyManager_IsPolicySetByMobileDevice"...
0x1800223e7  mov     rcx, rax; hModule
0x1800223ea  call    cs:__imp_GetProcAddress
0x1800223f1  nop     dword ptr [rax+rax+00h]
0x1800223f6  test    rax, rax
0x1800223f9  jnz     short loc_18002240C
0x1800223fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022402  cmp     rcx, rbx
0x180022405  jz      short loc_180022451
0x180022407  lea     edx, [rax+0Eh]
0x18002240a  jmp     short loc_180022441
0x18002240c  mov     rcx, cs:?g_hPolicyExtLib@@3PEAUHINSTANCE__@@EA; hModule
0x180022413  lea     rdx, aPolicymanagerG; "PolicyManager_GetPolicyInt"
0x18002241a  mov     qword ptr cs:?g_PolicyExtLibFunctionTable@@3U_POLICYEXTLIB_FUNCTION_TABLE@@A, rax; _POLICYEXTLIB_FUNCTION_TABLE g_PolicyExtLibFunctionTable
0x180022421  call    cs:__imp_GetProcAddress
0x180022428  nop     dword ptr [rax+rax+00h]
0x18002242d  test    rax, rax
0x180022430  jnz     short loc_18002245B
0x180022432  mov     rcx, cs:WPP_GLOBAL_Control
0x180022439  cmp     rcx, rbx
0x18002243c  jz      short loc_180022451
0x18002243e  lea     edx, [rax+0Fh]
0x180022441  mov     rcx, [rcx+10h]
0x180022445  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18002244c  call    WPP_SF_
0x180022451  add     rsp, 20h
0x180022455  pop     rbx
0x180022456  jmp     PolicyDeInit
0x18002245b  mov     qword ptr cs:?g_PolicyExtLibFunctionTable@@3U_POLICYEXTLIB_FUNCTION_TABLE@@A+8, rax; _POLICYEXTLIB_FUNCTION_TABLE g_PolicyExtLibFunctionTable
0x180022462  add     rsp, 20h
0x180022466  pop     rbx
0x180022467  retn
```
