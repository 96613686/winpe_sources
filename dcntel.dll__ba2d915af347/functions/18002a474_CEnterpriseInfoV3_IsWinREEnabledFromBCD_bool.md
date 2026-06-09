# CEnterpriseInfoV3::IsWinREEnabledFromBCD(bool *)

- ea: `0x18002a474`
- end: `0x18002a688`
- name: `?IsWinREEnabledFromBCD@CEnterpriseInfoV3@@CAJPEA_N@Z`
- size: `532`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800258b0`
- `0x1800a7030`

## callees

- `0x18001daf0`
- `0x18001dcc8`
- `0x18002a474`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a4b5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a4b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a4e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a4f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a50a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a51e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a532`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a4e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a4f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a50a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a51e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a66e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a66e`
- `ntdll!RtlNtStatusToDosError` at `0x18002a57a`
- `ntdll!RtlNtStatusToDosError` at `0x18002a5ac`
- `ntdll!RtlNtStatusToDosError` at `0x18002a5e0`
- `ntdll!RtlNtStatusToDosError` at `0x18002a57a`
- `ntdll!RtlNtStatusToDosError` at `0x18002a5ac`
- `ntdll!RtlNtStatusToDosError` at `0x18002a5e0`

## string_xrefs

- `0x18002a4ae`: `Bcd.DLL`
- `0x18002a4eb`: `BcdOpenObject`
- `0x18002a4d8`: `BcdOpenStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnterpriseInfoV3::IsWinREEnabledFromBCD(bool *a1)
{
  HMODULE Library; // rax
  void (*v3)(void); // rdi
  void (*v4)(void); // rsi
  FARPROC ProcAddress; // rbx
  FARPROC v6; // r14
  FARPROC v7; // r15
  FARPROC v8; // rax
  NTSTATUS v9; // eax
  signed int v10; // eax
  signed int v11; // ebx
  NTSTATUS v12; // eax
  signed int v13; // eax
  NTSTATUS v14; // eax
  signed int v15; // eax
  signed int LastError; // eax
  int v18; // edx
  unsigned int v19; // r8d
  __int64 v20; // [rsp+30h] [rbp-20h] BYREF
  const int *v21; // [rsp+38h] [rbp-18h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp-10h]
  __int16 v23; // [rsp+98h] [rbp+48h] BYREF
  int v24; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+58h] BYREF

  v20 = 0;
  v25 = 0;
  v23 = 0;
  v24 = 2;
  Library = LoadLibraryExW(L"Bcd.DLL", 0, 0x800u);
  v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = Library;
  if ( !Library )
  {
    v3 = 0;
    v4 = 0;
LABEL_19:
    v11 = -2147467259;
    goto LABEL_20;
  }
  ProcAddress = GetProcAddress(Library, "BcdOpenStore");
  v6 = GetProcAddress(hModule, "BcdOpenObject");
  v7 = GetProcAddress(hModule, "BcdGetElementData");
  v3 = (void (*)(void))GetProcAddress(hModule, "BcdCloseObject");
  v8 = GetProcAddress(hModule, "BcdCloseStore");
  v4 = (void (*)(void))v8;
  if ( !ProcAddress || !v6 || !v7 || !v3 || !v8 )
    goto LABEL_19;
  v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64 *))ProcAddress)(0, 0, &v20);
  v10 = RtlNtStatusToDosError(v9);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 >= 0 )
  {
    v12 = ((__int64 (__fastcall *)(__int64, GUID *, __int64 *))v6)(v20, &GUID_CURRENT_BOOT_ENTRY, &v25);
    v13 = RtlNtStatusToDosError(v12);
    v11 = v13;
    if ( v13 > 0 )
      v11 = (unsigned __int16)v13 | 0x80070000;
    if ( v11 >= 0 )
    {
      v14 = ((__int64 (__fastcall *)(__int64, __int64, __int16 *, int *))v7)(v25, 369098761, &v23, &v24);
      v15 = RtlNtStatusToDosError(v14);
      v11 = v15;
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
      if ( v11 >= 0 )
        *a1 = (_BYTE)v23 != 0;
    }
  }
LABEL_20:
  if ( v25 )
    v3();
  if ( v20 )
    v4();
  v21 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v21) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v18, v19);
    JUMPOUT(0x18002A687LL);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002a474  push    rbp
0x18002a476  push    rbx
0x18002a477  push    rsi
0x18002a478  push    rdi
0x18002a479  push    r12
0x18002a47b  push    r14
0x18002a47d  push    r15
0x18002a47f  mov     rbp, rsp
0x18002a482  sub     rsp, 50h
0x18002a486  mov     r12, rcx
0x18002a489  mov     [rbp+var_20], 0
0x18002a491  mov     [rbp+arg_18], 0
0x18002a499  xor     eax, eax
0x18002a49b  mov     [rbp+arg_8], ax
0x18002a49f  mov     [rbp+arg_10], 2
0x18002a4a6  xor     edx, edx; hFile
0x18002a4a8  mov     r8d, 800h; dwFlags
0x18002a4ae  lea     rcx, aBcdDll; "Bcd.DLL"
0x18002a4b5  call    cs:__imp_LoadLibraryExW
0x18002a4bb  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002a4c2  mov     [rbp+var_18], r14
0x18002a4c6  mov     [rbp+hModule], rax
0x18002a4ca  test    rax, rax
0x18002a4cd  jnz     short loc_18002A4D8
0x18002a4cf  xor     edi, edi
0x18002a4d1  xor     esi, esi
0x18002a4d3  jmp     loc_18002A61D
0x18002a4d8  lea     rdx, aBcdopenstore; "BcdOpenStore"
0x18002a4df  mov     rcx, rax; hModule
0x18002a4e2  call    cs:__imp_GetProcAddress
0x18002a4e8  mov     rbx, rax
0x18002a4eb  lea     rdx, aBcdopenobject; "BcdOpenObject"
0x18002a4f2  mov     rcx, [rbp+hModule]; hModule
0x18002a4f6  call    cs:__imp_GetProcAddress
0x18002a4fc  mov     r14, rax
0x18002a4ff  lea     rdx, aBcdgetelementd; "BcdGetElementData"
0x18002a506  mov     rcx, [rbp+hModule]; hModule
0x18002a50a  call    cs:__imp_GetProcAddress
0x18002a510  mov     r15, rax
0x18002a513  lea     rdx, aBcdcloseobject; "BcdCloseObject"
0x18002a51a  mov     rcx, [rbp+hModule]; hModule
0x18002a51e  call    cs:__imp_GetProcAddress
0x18002a524  mov     rdi, rax
0x18002a527  lea     rdx, aBcdclosestore; "BcdCloseStore"
0x18002a52e  mov     rcx, [rbp+hModule]; hModule
0x18002a532  call    cs:__imp_GetProcAddress
0x18002a538  mov     rsi, rax
0x18002a53b  test    rbx, rbx
0x18002a53e  jz      loc_18002A616
0x18002a544  test    r14, r14
0x18002a547  jz      loc_18002A616
0x18002a54d  test    r15, r15
0x18002a550  jz      loc_18002A616
0x18002a556  test    rdi, rdi
0x18002a559  jz      loc_18002A616
0x18002a55f  test    rax, rax
0x18002a562  jz      loc_18002A616
0x18002a568  lea     r8, [rbp+var_20]
0x18002a56c  xor     edx, edx
0x18002a56e  xor     ecx, ecx
0x18002a570  mov     rax, rbx
0x18002a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a578  mov     ecx, eax; Status
0x18002a57a  call    cs:__imp_RtlNtStatusToDosError
0x18002a580  mov     ebx, eax
0x18002a582  test    eax, eax
0x18002a584  jle     short loc_18002A58F
0x18002a586  movzx   ebx, ax
0x18002a589  or      ebx, 80070000h
0x18002a58f  test    ebx, ebx
0x18002a591  js      short loc_18002A60D
0x18002a593  lea     r8, [rbp+arg_18]
0x18002a597  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18002a59e  mov     rcx, [rbp+var_20]
0x18002a5a2  mov     rax, r14
0x18002a5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5aa  mov     ecx, eax; Status
0x18002a5ac  call    cs:__imp_RtlNtStatusToDosError
0x18002a5b2  mov     ebx, eax
0x18002a5b4  test    eax, eax
0x18002a5b6  jle     short loc_18002A5C1
0x18002a5b8  movzx   ebx, ax
0x18002a5bb  or      ebx, 80070000h
0x18002a5c1  test    ebx, ebx
0x18002a5c3  js      short loc_18002A60D
0x18002a5c5  lea     r9, [rbp+arg_10]
0x18002a5c9  lea     r8, [rbp+arg_8]
0x18002a5cd  mov     edx, 16000009h
0x18002a5d2  mov     rcx, [rbp+arg_18]
0x18002a5d6  mov     rax, r15
0x18002a5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5de  mov     ecx, eax; Status
0x18002a5e0  call    cs:__imp_RtlNtStatusToDosError
0x18002a5e6  mov     ebx, eax
0x18002a5e8  test    eax, eax
0x18002a5ea  jle     short loc_18002A5F5
0x18002a5ec  movzx   ebx, ax
0x18002a5ef  or      ebx, 80070000h
0x18002a5f5  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002a5fc  test    ebx, ebx
0x18002a5fe  js      short loc_18002A622
0x18002a600  cmp     byte ptr [rbp+arg_8], 0
0x18002a604  setnz   al
0x18002a607  mov     [r12], al
0x18002a60b  jmp     short loc_18002A622
0x18002a60d  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002a614  jmp     short loc_18002A622
0x18002a616  lea     r14, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18002a61d  mov     ebx, 80004005h
0x18002a622  mov     rcx, [rbp+arg_18]
0x18002a626  test    rcx, rcx
0x18002a629  jz      short loc_18002A633
0x18002a62b  mov     rax, rdi
0x18002a62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a633  mov     rcx, [rbp+var_20]
0x18002a637  test    rcx, rcx
0x18002a63a  jz      short loc_18002A645
0x18002a63c  mov     rax, rsi
0x18002a63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a644  nop
0x18002a645  mov     [rbp+var_18], r14
0x18002a649  cmp     [rbp+hModule], 0
0x18002a64e  jz      short loc_18002A65D
0x18002a650  lea     rcx, [rbp+var_18]
0x18002a654  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18002a659  test    al, al
0x18002a65b  jz      short loc_18002A66E
0x18002a65d  mov     eax, ebx
0x18002a65f  add     rsp, 50h
0x18002a663  pop     r15
0x18002a665  pop     r14
0x18002a667  pop     r12
0x18002a669  pop     rdi
0x18002a66a  pop     rsi
0x18002a66b  pop     rbx
0x18002a66c  pop     rbp
0x18002a66d  retn
0x18002a66e  call    cs:__imp_GetLastError
0x18002a674  test    eax, eax
0x18002a676  jle     short loc_18002A680
0x18002a678  movzx   eax, ax
0x18002a67b  or      eax, 80070000h
0x18002a680  mov     ecx, eax; this
0x18002a682  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
