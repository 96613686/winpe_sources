# wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(uint)

- ea: `0x180025408`
- end: `0x18002551b`
- name: `?Wil_Staging_AreExternalFeatureDependenciesEnabled@wil@@YA_NI@Z`
- size: `275`
- prototype: `bool __fastcall(wil *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025524`
- `0x1800391f4`
- `0x1800394dc`
- `0x180044ba8`
- `0x180044e90`
- `0x1800621cc`

## callees

- `0x180025408`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025451`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002549f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025451`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002549f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800254b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800254ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002542d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002547b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002542d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18002547b`

## string_xrefs

- `0x180025426`: `kernelbase.dll`
- `0x180025474`: `windowsudk.shellcommon.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall wil::Wil_Staging_AreExternalFeatureDependenciesEnabled(wil *this)
{
  unsigned int v1; // esi
  HMODULE Library; // rax
  HMODULE v3; // rdi
  bool v4; // r14
  FARPROC ProcAddress; // rax
  bool v6; // si
  HMODULE v7; // rax
  HMODULE v8; // rbx
  bool v9; // bp
  FARPROC v10; // rax

  v1 = (unsigned int)this;
  Library = LoadLibraryExA("kernelbase.dll", 0, 0x800u);
  v3 = Library;
  v4 = Library != 0;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "AreExternalFeatureDependenciesEnabled");
    if ( ProcAddress )
    {
      v6 = ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v1) == 2;
      goto LABEL_12;
    }
  }
  v7 = LoadLibraryExA("windowsudk.shellcommon.dll", 0, 0x800u);
  v8 = v7;
  v9 = v7 != 0;
  if ( !v7 )
    goto LABEL_11;
  v10 = GetProcAddress(v7, "AreExternalFeatureDependenciesEnabled");
  if ( !v10 )
  {
    v10 = GetProcAddress(v8, "GetExternalFeatureState");
    if ( !v10 )
    {
      if ( v9 )
        FreeLibrary(v8);
LABEL_11:
      v6 = 0;
      goto LABEL_12;
    }
  }
  v6 = ((unsigned int (__fastcall *)(_QWORD))v10)(v1) == 2;
  if ( v9 )
    FreeLibrary(v8);
LABEL_12:
  if ( v4 )
    FreeLibrary(v3);
  return v6;
}

```

## disassembly

```asm
0x180025408  mov     [rsp+arg_8], rbx
0x18002540d  mov     [rsp+arg_10], rbp
0x180025412  push    rsi
0x180025413  push    rdi
0x180025414  push    r14
0x180025416  sub     rsp, 30h
0x18002541a  mov     esi, ecx
0x18002541c  mov     ebx, 800h
0x180025421  mov     r8d, ebx; dwFlags
0x180025424  xor     edx, edx; hFile
0x180025426  lea     rcx, LibFileName; "kernelbase.dll"
0x18002542d  call    cs:__imp_LoadLibraryExA
0x180025433  mov     rdi, rax
0x180025436  mov     [rsp+48h+var_28], rax
0x18002543b  test    rax, rax
0x18002543e  setnz   r14b
0x180025442  test    rax, rax
0x180025445  jz      short loc_18002546F
0x180025447  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18002544e  mov     rcx, rax; hModule
0x180025451  call    cs:__imp_GetProcAddress
0x180025457  test    rax, rax
0x18002545a  jz      short loc_18002546F
0x18002545c  mov     ecx, esi
0x18002545e  call    _guard_dispatch_icall
0x180025463  cmp     eax, 2
0x180025466  setz    sil
0x18002546a  jmp     loc_1800254F7
0x18002546f  mov     r8d, ebx; dwFlags
0x180025472  xor     edx, edx; hFile
0x180025474  lea     rcx, aWindowsudkShel; "windowsudk.shellcommon.dll"
0x18002547b  call    cs:__imp_LoadLibraryExA
0x180025481  mov     rbx, rax
0x180025484  mov     [rsp+48h+var_20], rax
0x180025489  test    rax, rax
0x18002548c  setnz   bpl
0x180025490  test    rax, rax
0x180025493  jz      short loc_1800254E7
0x180025495  lea     rdx, aAreexternalfea; "AreExternalFeatureDependenciesEnabled"
0x18002549c  mov     rcx, rax; hModule
0x18002549f  call    cs:__imp_GetProcAddress
0x1800254a5  test    rax, rax
0x1800254a8  jnz     short loc_1800254C9
0x1800254aa  lea     rdx, aGetexternalfea; "GetExternalFeatureState"
0x1800254b1  mov     rcx, rbx; hModule
0x1800254b4  call    cs:__imp_GetProcAddress
0x1800254ba  test    rax, rax
0x1800254bd  jnz     short loc_1800254C9
0x1800254bf  test    bpl, bpl
0x1800254c2  jz      short loc_1800254F4
0x1800254c4  mov     rcx, rbx
0x1800254c7  jmp     short loc_1800254EE
0x1800254c9  mov     ecx, esi
0x1800254cb  call    _guard_dispatch_icall
0x1800254d0  cmp     eax, 2
0x1800254d3  setz    sil
0x1800254d7  test    bpl, bpl
0x1800254da  jz      short loc_1800254F7
0x1800254dc  mov     rcx, rbx; hLibModule
0x1800254df  call    cs:__imp_FreeLibrary
0x1800254e5  jmp     short loc_1800254F7
0x1800254e7  test    bpl, bpl
0x1800254ea  jz      short loc_1800254F4
0x1800254ec  xor     ecx, ecx; hLibModule
0x1800254ee  call    cs:__imp_FreeLibrary
0x1800254f4  xor     sil, sil
0x1800254f7  test    r14b, r14b
0x1800254fa  jz      short loc_180025505
0x1800254fc  mov     rcx, rdi; hLibModule
0x1800254ff  call    cs:__imp_FreeLibrary
0x180025505  mov     al, sil
0x180025508  mov     rbx, [rsp+48h+arg_8]
0x18002550d  mov     rbp, [rsp+48h+arg_10]
0x180025512  add     rsp, 30h
0x180025516  pop     r14
0x180025518  pop     rdi
0x180025519  pop     rsi
0x18002551a  retn
```
