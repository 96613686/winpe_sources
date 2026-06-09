# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800045d4`
- end: `0x180004781`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `429`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800045d4`
- `0x180004ae4`

## callees

- `0x180004570`
- `0x1800045d4`
- `0x180008580`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004740`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004704`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004704`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800046c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000463a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000463a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004752`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004695`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004695`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800046ef`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800046ef`

## string_xrefs

- `0x1800046c0`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800046d2`: `RegDeleteKeyExW`
- `0x1800046e8`: `advapi32.dll`
- `0x1800046fa`: `RegDeleteKeyW`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2, __int64 a3, unsigned int a4)
{
  int v6; // eax
  HKEY v7; // rcx
  unsigned int v8; // edi
  unsigned int v10; // eax
  HMODULE ModuleHandleW; // rax
  HMODULE LibraryW; // rax
  __int64 (__fastcall *v13)(_QWORD, _QWORD, _QWORD, _QWORD); // rax
  DWORD LastError; // eax
  __int64 (__fastcall *v15)(HKEY, const unsigned __int16 *); // rax
  DWORD v16; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v6 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, a4);
  v7 = hKey[0];
  v8 = v6;
  if ( v6 )
  {
LABEL_2:
    if ( v7 )
      RegCloseKey(v7);
    return v8;
  }
  else
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v7, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v10 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v7 = hKey[0];
      v8 = v10;
      if ( v10 )
        goto LABEL_2;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    if ( !this[1] && !this[2] )
    {
      ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
      if ( ModuleHandleW )
      {
        this[1] = (HKEY)GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
      }
      else
      {
        LibraryW = LoadLibraryW(L"advapi32.dll");
        if ( LibraryW )
          this[2] = (HKEY)GetProcAddress(LibraryW, "RegDeleteKeyW");
      }
    }
    v13 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))this[1];
    if ( v13 )
    {
      LastError = v13(*this, a2, 0, 0);
    }
    else
    {
      v15 = (__int64 (__fastcall *)(HKEY, const unsigned __int16 *))this[2];
      if ( v15 )
        LastError = v15(*this, a2);
      else
        LastError = GetLastError();
    }
    v16 = LastError;
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return v16;
  }
}

```

## disassembly

```asm
0x1800045d4  mov     [rsp-8+arg_10], rbx
0x1800045d9  mov     [rsp-8+arg_18], rsi
0x1800045de  push    rbp
0x1800045df  push    rdi
0x1800045e0  push    r14
0x1800045e2  lea     rbp, [rsp-180h]
0x1800045ea  sub     rsp, 280h
0x1800045f1  mov     rax, cs:__security_cookie
0x1800045f8  xor     rax, rsp
0x1800045fb  mov     [rbp+190h+var_20], rax
0x180004602  xor     r14d, r14d
0x180004605  mov     rsi, rdx
0x180004608  mov     r8, rdx; unsigned __int16 *
0x18000460b  mov     [rsp+290h+hKey], r14
0x180004610  mov     rdx, [rcx]; HKEY
0x180004613  mov     rbx, rcx
0x180004616  lea     rcx, [rsp+290h+hKey]; this
0x18000461b  mov     [rsp+290h+var_240], r14
0x180004620  mov     [rsp+290h+var_238], r14
0x180004625  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000462a  mov     rcx, [rsp+290h+hKey]; hKey
0x18000462f  mov     edi, eax
0x180004631  test    eax, eax
0x180004633  jz      short loc_180004647
0x180004635  test    rcx, rcx
0x180004638  jz      short loc_180004640
0x18000463a  call    cs:__imp_RegCloseKey
0x180004640  mov     eax, edi
0x180004642  jmp     loc_18000475A
0x180004647  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000464c  jmp     short loc_180004668
0x18000464e  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004653  lea     rcx, [rsp+290h+hKey]; this
0x180004658  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000465d  mov     rcx, [rsp+290h+hKey]; hKey
0x180004662  mov     edi, eax
0x180004664  test    eax, eax
0x180004666  jnz     short loc_180004635
0x180004668  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000466d  mov     [rsp+290h+cchName], 100h
0x180004675  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000467a  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000467f  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004684  lea     r8, [rsp+290h+Name]; lpName
0x180004689  mov     [rsp+290h+lpClass], r14; lpClass
0x18000468e  xor     edx, edx; dwIndex
0x180004690  mov     [rsp+290h+lpReserved], r14; lpReserved
0x180004695  call    cs:__imp_RegEnumKeyExW
0x18000469b  test    eax, eax
0x18000469d  jz      short loc_18000464E
0x18000469f  mov     rcx, [rsp+290h+hKey]; hKey
0x1800046a4  test    rcx, rcx
0x1800046a7  jz      short loc_1800046B4
0x1800046a9  call    cs:__imp_RegCloseKey
0x1800046af  mov     [rsp+290h+hKey], r14
0x1800046b4  cmp     [rbx+8], r14
0x1800046b8  jnz     short loc_18000470E
0x1800046ba  cmp     [rbx+10h], r14
0x1800046be  jnz     short loc_18000470E
0x1800046c0  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800046c7  call    cs:__imp_GetModuleHandleW
0x1800046cd  test    rax, rax
0x1800046d0  jz      short loc_1800046E8
0x1800046d2  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800046d9  mov     rcx, rax; hModule
0x1800046dc  call    cs:__imp_GetProcAddress
0x1800046e2  mov     [rbx+8], rax
0x1800046e6  jmp     short loc_18000470E
0x1800046e8  lea     rcx, LibFileName; "advapi32.dll"
0x1800046ef  call    cs:__imp_LoadLibraryW
0x1800046f5  test    rax, rax
0x1800046f8  jz      short loc_18000470E
0x1800046fa  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004701  mov     rcx, rax; hModule
0x180004704  call    cs:__imp_GetProcAddress
0x18000470a  mov     [rbx+10h], rax
0x18000470e  mov     rax, [rbx+8]
0x180004712  test    rax, rax
0x180004715  jz      short loc_18000472A
0x180004717  mov     rcx, [rbx]
0x18000471a  xor     r9d, r9d
0x18000471d  xor     r8d, r8d
0x180004720  mov     rdx, rsi
0x180004723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004728  jmp     short loc_180004746
0x18000472a  mov     rax, [rbx+10h]
0x18000472e  test    rax, rax
0x180004731  jz      short loc_180004740
0x180004733  mov     rcx, [rbx]
0x180004736  mov     rdx, rsi
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  jmp     short loc_180004746
0x180004740  call    cs:__imp_GetLastError
0x180004746  mov     rcx, [rsp+290h+hKey]; hKey
0x18000474b  mov     ebx, eax
0x18000474d  test    rcx, rcx
0x180004750  jz      short loc_180004758
0x180004752  call    cs:__imp_RegCloseKey
0x180004758  mov     eax, ebx
0x18000475a  mov     rcx, [rbp+190h+var_20]
0x180004761  xor     rcx, rsp; StackCookie
0x180004764  call    __security_check_cookie
0x180004769  lea     r11, [rsp+290h+var_10]
0x180004771  mov     rbx, [r11+30h]
0x180004775  mov     rsi, [r11+38h]
0x180004779  mov     rsp, r11
0x18000477c  pop     r14
0x18000477e  pop     rdi
0x18000477f  pop     rbp
0x180004780  retn
```
