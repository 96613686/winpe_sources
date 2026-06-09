# CopyNCryptEfsProtector

- ea: `0x18000a4b8`
- end: `0x18000a6dd`
- name: `CopyNCryptEfsProtector`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000acc0`

## callees

- `0x18000a4b8`
- `0x180084010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18000a588`
- `ntdll!RtlSetLastWin32Error` at `0x18000a588`
- `ntdll!_wcsicmp` at `0x18000a5f8`
- `ntdll!_wcsicmp` at `0x18000a5f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a533`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a555`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a50f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a533`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a555`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a635`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6bd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6ae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a6bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a4ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a617`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a4ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a617`

## string_xrefs

- `0x18000a4e6`: `feclient.dll`
- `0x18000a60a`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall CopyNCryptEfsProtector(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // esi
  HMODULE Library; // rax
  HMODULE v8; // rdi
  FARPROC v9; // rbp
  void (*v10)(void); // r14
  HMODULE v11; // rbx
  ULONG v12; // eax
  ULONG v13; // ecx
  __int64 v14; // rax
  HMODULE v15; // rax
  FARPROC v16; // rax
  __int64 v18; // [rsp+20h] [rbp-58h] BYREF
  FARPROC ProcAddress; // [rsp+28h] [rbp-50h]
  __int64 v20; // [rsp+98h] [rbp+20h] BYREF

  v6 = 0;
  v20 = 0;
  v18 = 0;
  Library = LoadLibraryExW(L"feclient.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "EfsClientEncryptFileEx");
    if ( !ProcAddress
      || (v9 = GetProcAddress(v8, "EfsClientQueryProtectors")) == 0
      || (v10 = (void (*)(void))GetProcAddress(v8, "EfsClientFreeProtectorList")) == 0 )
    {
LABEL_26:
      FreeLibrary(v8);
      return v6;
    }
    v11 = 0;
    v12 = ((__int64 (__fastcall *)(__int64, __int64 *))v9)(a1, &v20);
    if ( v12 )
      goto LABEL_6;
    v14 = v20;
    if ( !*(_DWORD *)v20 )
    {
      v13 = 13;
      goto LABEL_7;
    }
    if ( a3 )
    {
      v12 = ((__int64 (__fastcall *)(__int64, __int64 *))v9)(a2, &v18);
      if ( v12 )
        goto LABEL_6;
      if ( *(_DWORD *)v18 == 1
        && !_wcsicmp(
              *(const wchar_t **)(**(_QWORD **)(v20 + 8) + 16LL),
              *(const wchar_t **)(**(_QWORD **)(v18 + 8) + 16LL)) )
      {
        goto LABEL_19;
      }
      v15 = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
      v11 = v15;
      if ( !v15 )
        goto LABEL_20;
      v16 = GetProcAddress(v15, "DecryptFileW");
      if ( !v16 || !((unsigned int (__fastcall *)(__int64, _QWORD))v16)(a2, 0) )
        goto LABEL_20;
      v14 = v20;
    }
    v12 = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(a2, *(_QWORD *)(**(_QWORD **)(v14 + 8) + 16LL));
    if ( !v12 )
    {
LABEL_19:
      v6 = 1;
      goto LABEL_20;
    }
LABEL_6:
    v13 = v12;
LABEL_7:
    RtlSetLastWin32Error(v13);
LABEL_20:
    if ( v20 )
      v10();
    if ( v18 )
      v10();
    if ( v11 )
      FreeLibrary(v11);
    goto LABEL_26;
  }
  return v6;
}

```

## disassembly

```asm
0x18000a4b8  mov     rax, rsp
0x18000a4bb  push    rbx
0x18000a4bc  push    rbp
0x18000a4bd  push    rsi
0x18000a4be  push    rdi
0x18000a4bf  push    r12
0x18000a4c1  push    r13
0x18000a4c3  push    r14
0x18000a4c5  push    r15
0x18000a4c7  sub     rsp, 38h
0x18000a4cb  mov     r15d, r8d
0x18000a4ce  mov     r13, rdx
0x18000a4d1  mov     r12, rcx
0x18000a4d4  xor     esi, esi
0x18000a4d6  xor     edx, edx; hFile
0x18000a4d8  mov     [rax+20h], rsi
0x18000a4dc  mov     r8d, 800h; dwFlags
0x18000a4e2  mov     [rax-58h], rsi
0x18000a4e6  lea     rcx, FECLIENT_DLL_STRING; "feclient.dll"
0x18000a4ed  call    cs:__imp_LoadLibraryExW
0x18000a4f4  nop     dword ptr [rax+rax+00h]
0x18000a4f9  mov     rdi, rax
0x18000a4fc  test    rax, rax
0x18000a4ff  jz      loc_18000A6C9
0x18000a505  lea     rdx, ENCRYPTFILEEX_NAME; "EfsClientEncryptFileEx"
0x18000a50c  mov     rcx, rax; hModule
0x18000a50f  call    cs:__imp_GetProcAddress
0x18000a516  nop     dword ptr [rax+rax+00h]
0x18000a51b  mov     [rsp+78h+var_50], rax
0x18000a520  test    rax, rax
0x18000a523  jz      loc_18000A6BA
0x18000a529  lea     rdx, QUERYFILEPROTECTORS_NAME; "EfsClientQueryProtectors"
0x18000a530  mov     rcx, rdi; hModule
0x18000a533  call    cs:__imp_GetProcAddress
0x18000a53a  nop     dword ptr [rax+rax+00h]
0x18000a53f  mov     rbp, rax
0x18000a542  test    rax, rax
0x18000a545  jz      loc_18000A6BA
0x18000a54b  lea     rdx, FREEFILEPROTECTORLIST_NAME; "EfsClientFreeProtectorList"
0x18000a552  mov     rcx, rdi; hModule
0x18000a555  call    cs:__imp_GetProcAddress
0x18000a55c  nop     dword ptr [rax+rax+00h]
0x18000a561  mov     r14, rax
0x18000a564  test    rax, rax
0x18000a567  jz      loc_18000A6BA
0x18000a56d  lea     rdx, [rsp+78h+arg_18]
0x18000a575  mov     rcx, r12
0x18000a578  mov     rax, rbp
0x18000a57b  xor     ebx, ebx
0x18000a57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a582  test    eax, eax
0x18000a584  jz      short loc_18000A599
0x18000a586  mov     ecx, eax; LastError
0x18000a588  call    cs:__imp_RtlSetLastWin32Error
0x18000a58f  nop     dword ptr [rax+rax+00h]
0x18000a594  jmp     loc_18000A67F
0x18000a599  mov     rax, [rsp+78h+arg_18]
0x18000a5a1  mov     r12d, 1
0x18000a5a7  cmp     [rax], r12d
0x18000a5aa  jnb     short loc_18000A5B3
0x18000a5ac  lea     ecx, [r12+0Ch]
0x18000a5b1  jmp     short loc_18000A588
0x18000a5b3  test    r15d, r15d
0x18000a5b6  jz      loc_18000A65C
0x18000a5bc  lea     rdx, [rsp+78h+var_58]
0x18000a5c1  mov     rcx, r13
0x18000a5c4  mov     rax, rbp
0x18000a5c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5cc  test    eax, eax
0x18000a5ce  jnz     short loc_18000A586
0x18000a5d0  mov     rax, [rsp+78h+var_58]
0x18000a5d5  cmp     [rax], r12d
0x18000a5d8  jnz     short loc_18000A608
0x18000a5da  mov     rax, [rax+8]
0x18000a5de  mov     rdx, [rax]
0x18000a5e1  mov     rax, [rsp+78h+arg_18]
0x18000a5e9  mov     rdx, [rdx+10h]; String2
0x18000a5ed  mov     rcx, [rax+8]
0x18000a5f1  mov     rcx, [rcx]
0x18000a5f4  mov     rcx, [rcx+10h]; String1
0x18000a5f8  call    cs:__imp__wcsicmp
0x18000a5ff  nop     dword ptr [rax+rax+00h]
0x18000a604  test    eax, eax
0x18000a606  jz      short loc_18000A67C
0x18000a608  xor     edx, edx; hFile
0x18000a60a  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18000a611  mov     r8d, 800h; dwFlags
0x18000a617  call    cs:__imp_LoadLibraryExW
0x18000a61e  nop     dword ptr [rax+rax+00h]
0x18000a623  mov     rbx, rax
0x18000a626  test    rax, rax
0x18000a629  jz      short loc_18000A67F
0x18000a62b  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x18000a632  mov     rcx, rax; hModule
0x18000a635  call    cs:__imp_GetProcAddress
0x18000a63c  nop     dword ptr [rax+rax+00h]
0x18000a641  test    rax, rax
0x18000a644  jz      short loc_18000A67F
0x18000a646  xor     edx, edx
0x18000a648  mov     rcx, r13
0x18000a64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a650  test    eax, eax
0x18000a652  jz      short loc_18000A67F
0x18000a654  mov     rax, [rsp+78h+arg_18]
0x18000a65c  mov     rax, [rax+8]
0x18000a660  mov     rcx, r13
0x18000a663  mov     rdx, [rax]
0x18000a666  mov     rax, [rsp+78h+var_50]
0x18000a66b  mov     rdx, [rdx+10h]
0x18000a66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a674  test    eax, eax
0x18000a676  jnz     loc_18000A586
0x18000a67c  mov     esi, r12d
0x18000a67f  mov     rcx, [rsp+78h+arg_18]
0x18000a687  test    rcx, rcx
0x18000a68a  jz      short loc_18000A694
0x18000a68c  mov     rax, r14
0x18000a68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a694  mov     rcx, [rsp+78h+var_58]
0x18000a699  test    rcx, rcx
0x18000a69c  jz      short loc_18000A6A6
0x18000a69e  mov     rax, r14
0x18000a6a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a6  test    rbx, rbx
0x18000a6a9  jz      short loc_18000A6BA
0x18000a6ab  mov     rcx, rbx; hLibModule
0x18000a6ae  call    cs:__imp_FreeLibrary
0x18000a6b5  nop     dword ptr [rax+rax+00h]
0x18000a6ba  mov     rcx, rdi; hLibModule
0x18000a6bd  call    cs:__imp_FreeLibrary
0x18000a6c4  nop     dword ptr [rax+rax+00h]
0x18000a6c9  mov     eax, esi
0x18000a6cb  add     rsp, 38h
0x18000a6cf  pop     r15
0x18000a6d1  pop     r14
0x18000a6d3  pop     r13
0x18000a6d5  pop     r12
0x18000a6d7  pop     rdi
0x18000a6d8  pop     rsi
0x18000a6d9  pop     rbp
0x18000a6da  pop     rbx
0x18000a6db  retn
```
