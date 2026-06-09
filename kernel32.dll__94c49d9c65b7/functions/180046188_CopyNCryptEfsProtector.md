# CopyNCryptEfsProtector

- ea: `0x180046188`
- end: `0x180046370`
- name: `CopyNCryptEfsProtector`
- size: `488`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000db20`

## callees

- `0x180046188`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180046240`
- `ntdll!RtlSetLastWin32Error` at `0x180046240`
- `ntdll!_wcsicmp` at `0x1800462aa`
- `ntdll!_wcsicmp` at `0x1800462aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800461d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800461f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046213`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800462db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800461d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800461f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180046213`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800462db`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004634e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046357`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004634e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046357`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800461bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800462c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800461bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800462c3`

## string_xrefs

- `0x1800462b6`: `advapi32.dll`
- `0x1800461b6`: `feclient.dll`

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
0x180046188  mov     rax, rsp
0x18004618b  push    rbx
0x18004618c  push    rbp
0x18004618d  push    rsi
0x18004618e  push    rdi
0x18004618f  push    r12
0x180046191  push    r13
0x180046193  push    r14
0x180046195  push    r15
0x180046197  sub     rsp, 38h
0x18004619b  mov     r15d, r8d
0x18004619e  mov     r13, rdx
0x1800461a1  mov     r12, rcx
0x1800461a4  xor     esi, esi
0x1800461a6  xor     edx, edx; hFile
0x1800461a8  mov     [rax+20h], rsi
0x1800461ac  mov     r8d, 800h; dwFlags
0x1800461b2  mov     [rax-58h], rsi
0x1800461b6  lea     rcx, FECLIENT_DLL_STRING; "feclient.dll"
0x1800461bd  call    cs:__imp_LoadLibraryExW
0x1800461c3  mov     rdi, rax
0x1800461c6  test    rax, rax
0x1800461c9  jz      loc_18004635D
0x1800461cf  lea     rdx, ENCRYPTFILEEX_NAME; "EfsClientEncryptFileEx"
0x1800461d6  mov     rcx, rax; hModule
0x1800461d9  call    cs:__imp_GetProcAddress
0x1800461df  mov     [rsp+78h+var_50], rax
0x1800461e4  test    rax, rax
0x1800461e7  jz      loc_180046354
0x1800461ed  lea     rdx, QUERYFILEPROTECTORS_NAME; "EfsClientQueryProtectors"
0x1800461f4  mov     rcx, rdi; hModule
0x1800461f7  call    cs:__imp_GetProcAddress
0x1800461fd  mov     rbp, rax
0x180046200  test    rax, rax
0x180046203  jz      loc_180046354
0x180046209  lea     rdx, FREEFILEPROTECTORLIST_NAME; "EfsClientFreeProtectorList"
0x180046210  mov     rcx, rdi; hModule
0x180046213  call    cs:__imp_GetProcAddress
0x180046219  mov     r14, rax
0x18004621c  test    rax, rax
0x18004621f  jz      loc_180046354
0x180046225  lea     rdx, [rsp+78h+arg_18]
0x18004622d  mov     rcx, r12
0x180046230  mov     rax, rbp
0x180046233  xor     ebx, ebx
0x180046235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004623a  test    eax, eax
0x18004623c  jz      short loc_18004624B
0x18004623e  mov     ecx, eax; LastError
0x180046240  call    cs:__imp_RtlSetLastWin32Error
0x180046246  jmp     loc_18004631F
0x18004624b  mov     rax, [rsp+78h+arg_18]
0x180046253  mov     r12d, 1
0x180046259  cmp     [rax], r12d
0x18004625c  jnb     short loc_180046265
0x18004625e  lea     ecx, [r12+0Ch]
0x180046263  jmp     short loc_180046240
0x180046265  test    r15d, r15d
0x180046268  jz      loc_1800462FC
0x18004626e  lea     rdx, [rsp+78h+var_58]
0x180046273  mov     rcx, r13
0x180046276  mov     rax, rbp
0x180046279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004627e  test    eax, eax
0x180046280  jnz     short loc_18004623E
0x180046282  mov     rax, [rsp+78h+var_58]
0x180046287  cmp     [rax], r12d
0x18004628a  jnz     short loc_1800462B4
0x18004628c  mov     rax, [rax+8]
0x180046290  mov     rdx, [rax]
0x180046293  mov     rax, [rsp+78h+arg_18]
0x18004629b  mov     rdx, [rdx+10h]; String2
0x18004629f  mov     rcx, [rax+8]
0x1800462a3  mov     rcx, [rcx]
0x1800462a6  mov     rcx, [rcx+10h]; String1
0x1800462aa  call    cs:__imp__wcsicmp
0x1800462b0  test    eax, eax
0x1800462b2  jz      short loc_18004631C
0x1800462b4  xor     edx, edx; hFile
0x1800462b6  lea     rcx, AdvapiDllString; "advapi32.dll"
0x1800462bd  mov     r8d, 800h; dwFlags
0x1800462c3  call    cs:__imp_LoadLibraryExW
0x1800462c9  mov     rbx, rax
0x1800462cc  test    rax, rax
0x1800462cf  jz      short loc_18004631F
0x1800462d1  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x1800462d8  mov     rcx, rax; hModule
0x1800462db  call    cs:__imp_GetProcAddress
0x1800462e1  test    rax, rax
0x1800462e4  jz      short loc_18004631F
0x1800462e6  xor     edx, edx
0x1800462e8  mov     rcx, r13
0x1800462eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462f0  test    eax, eax
0x1800462f2  jz      short loc_18004631F
0x1800462f4  mov     rax, [rsp+78h+arg_18]
0x1800462fc  mov     rax, [rax+8]
0x180046300  mov     rcx, r13
0x180046303  mov     rdx, [rax]
0x180046306  mov     rax, [rsp+78h+var_50]
0x18004630b  mov     rdx, [rdx+10h]
0x18004630f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046314  test    eax, eax
0x180046316  jnz     loc_18004623E
0x18004631c  mov     esi, r12d
0x18004631f  mov     rcx, [rsp+78h+arg_18]
0x180046327  test    rcx, rcx
0x18004632a  jz      short loc_180046334
0x18004632c  mov     rax, r14
0x18004632f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046334  mov     rcx, [rsp+78h+var_58]
0x180046339  test    rcx, rcx
0x18004633c  jz      short loc_180046346
0x18004633e  mov     rax, r14
0x180046341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046346  test    rbx, rbx
0x180046349  jz      short loc_180046354
0x18004634b  mov     rcx, rbx; hLibModule
0x18004634e  call    cs:__imp_FreeLibrary
0x180046354  mov     rcx, rdi; hLibModule
0x180046357  call    cs:__imp_FreeLibrary
0x18004635d  mov     eax, esi
0x18004635f  add     rsp, 38h
0x180046363  pop     r15
0x180046365  pop     r14
0x180046367  pop     r13
0x180046369  pop     r12
0x18004636b  pop     rdi
0x18004636c  pop     rsi
0x18004636d  pop     rbp
0x18004636e  pop     rbx
0x18004636f  retn
```
