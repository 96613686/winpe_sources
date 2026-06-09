# CRASMapi::get_Reload(long *)

- ea: `0x1800140c4`
- end: `0x18001424c`
- name: `?get_Reload@CRASMapi@@IEAAJPEAJ@Z`
- size: `392`
- prototype: `__int64 __fastcall(CRASMapi *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180013b00`

## callees

- `0x180006a20`
- `0x1800140c4`
- `0x180014660`
- `0x18001a5a2`
- `0x18001a5e0`
- `0x18001c010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800141ea`
- `KERNEL32!LoadLibraryW` at `0x1800141ea`
- `KERNEL32!FreeLibrary` at `0x180014165`
- `KERNEL32!FreeLibrary` at `0x180014165`
- `KERNEL32!GetProcAddress` at `0x180014210`
- `KERNEL32!GetProcAddress` at `0x180014210`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180014191`
- `SHELL32!SHGetSpecialFolderPathW` at `0x180014191`

## string_xrefs

- `0x1800141c8`: `\mapi32.dll`

## pseudocode

```c
__int64 __fastcall CRASMapi::get_Reload(CRASMapi *this, int *a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  unsigned int v6; // edi
  bool v7; // zf
  HMODULE v8; // rcx
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  HMODULE LibraryW; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  HMODULE v15; // rsi
  WCHAR pszPath[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(pszPath, 0, 0x208u);
  if ( !a2 )
  {
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
      0xBAu,
      L"CRASMapi::get_Reload",
      0x80004003);
    return (unsigned int)-2147467261;
  }
  *a2 = 0;
  v7 = *((_DWORD *)this + 271) == 0;
  *((_DWORD *)this + 270) = 0;
  if ( !v7 )
    (*(void (__fastcall **)(CRASMapi *))(*(_QWORD *)this + 112LL))(this);
  v8 = (HMODULE)*((_QWORD *)this + 2);
  if ( v8 )
  {
    FreeLibrary(v8);
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 2) = 0;
  }
  if ( !SHGetSpecialFolderPathW(0, pszPath, 37, 0) )
  {
    v11 = 218;
LABEL_9:
    CEventLogger::LogError(
      v10,
      v9,
      L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
      v11,
      L"CRASMapi::get_Reload",
      0x80004005);
    return (unsigned int)-2147467259;
  }
  if ( StringCchCatW(pszPath, (unsigned __int64)v9, L"\\mapi32.dll") < 0 )
  {
    v11 = 226;
    goto LABEL_9;
  }
  LibraryW = LoadLibraryW(pszPath);
  v15 = LibraryW;
  if ( !LibraryW )
  {
    CEventLogger::LogError(
      v14,
      v13,
      L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp",
      0xEDu,
      L"CRASMapi::get_Reload",
      0);
    return (unsigned int)-2147467259;
  }
  v6 = 0;
  if ( GetProcAddress(LibraryW, "MAPILogon") )
    *((_QWORD *)this + 2) = v15;
  *a2 = 1;
  return v6;
}

```

## disassembly

```asm
0x1800140c4  mov     [rsp+arg_10], rbx
0x1800140c9  push    rsi
0x1800140ca  push    rdi
0x1800140cb  push    r14
0x1800140cd  sub     rsp, 250h
0x1800140d4  mov     rax, cs:__security_cookie
0x1800140db  xor     rax, rsp
0x1800140de  mov     [rsp+268h+var_28], rax
0x1800140e6  mov     r14, rdx
0x1800140e9  mov     rbx, rcx
0x1800140ec  xor     edx, edx; Val
0x1800140ee  lea     rcx, [rsp+268h+pszPath]; void *
0x1800140f3  mov     r8d, 208h; Size
0x1800140f9  call    memset_0
0x1800140fe  test    r14, r14
0x180014101  jnz     short loc_180014133
0x180014103  lea     rax, aCrasmapiGetRel; "CRASMapi::get_Reload"
0x18001410a  mov     [rsp+268h+var_240], 80004003h; unsigned int
0x180014112  mov     r9d, 0BAh; unsigned int
0x180014118  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x18001411d  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x180014124  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014129  mov     edi, 80004003h
0x18001412e  jmp     loc_180014226
0x180014133  mov     dword ptr [r14], 0
0x18001413a  cmp     dword ptr [rbx+43Ch], 0
0x180014141  mov     dword ptr [rbx+438h], 0
0x18001414b  jz      short loc_18001415C
0x18001414d  mov     rax, [rbx]
0x180014150  mov     rcx, rbx
0x180014153  mov     rax, [rax+70h]
0x180014157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001415c  mov     rcx, [rbx+10h]; hLibModule
0x180014160  test    rcx, rcx
0x180014163  jz      short loc_180014183
0x180014165  call    cs:__imp_FreeLibrary
0x18001416b  mov     qword ptr [rbx+18h], 0
0x180014173  mov     qword ptr [rbx+20h], 0
0x18001417b  mov     qword ptr [rbx+10h], 0
0x180014183  xor     r9d, r9d; fCreate
0x180014186  lea     rdx, [rsp+268h+pszPath]; pszPath
0x18001418b  xor     ecx, ecx; hwnd
0x18001418d  lea     r8d, [r9+25h]; csidl
0x180014191  call    cs:__imp_SHGetSpecialFolderPathW
0x180014197  test    eax, eax
0x180014199  jnz     short loc_1800141C8
0x18001419b  mov     r9d, 0DAh; unsigned int
0x1800141a1  mov     [rsp+268h+var_240], 80004005h; unsigned int
0x1800141a9  lea     rax, aCrasmapiGetRel; "CRASMapi::get_Reload"
0x1800141b0  lea     r8, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x1800141b7  mov     [rsp+268h+var_248], rax; unsigned __int16 *
0x1800141bc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800141c1  mov     edi, 80004005h
0x1800141c6  jmp     short loc_180014226
0x1800141c8  lea     r8, aMapi32Dll; "\\mapi32.dll"
0x1800141cf  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x1800141d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800141d9  test    eax, eax
0x1800141db  jns     short loc_1800141E5
0x1800141dd  mov     r9d, 0E2h
0x1800141e3  jmp     short loc_1800141A1
0x1800141e5  lea     rcx, [rsp+268h+pszPath]; lpLibFileName
0x1800141ea  call    cs:__imp_LoadLibraryW
0x1800141f0  mov     rsi, rax
0x1800141f3  test    rax, rax
0x1800141f6  jnz     short loc_180014204
0x1800141f8  mov     [rsp+268h+var_240], eax
0x1800141fc  mov     r9d, 0EDh
0x180014202  jmp     short loc_1800141A9
0x180014204  lea     rdx, aMapilogon; "MAPILogon"
0x18001420b  mov     rcx, rsi; hModule
0x18001420e  xor     edi, edi
0x180014210  call    cs:__imp_GetProcAddress
0x180014216  test    rax, rax
0x180014219  jz      short loc_18001421F
0x18001421b  mov     [rbx+10h], rsi
0x18001421f  mov     dword ptr [r14], 1
0x180014226  mov     eax, edi
0x180014228  mov     rcx, [rsp+268h+var_28]
0x180014230  xor     rcx, rsp; StackCookie
0x180014233  call    __security_check_cookie
0x180014238  mov     rbx, [rsp+268h+arg_10]
0x180014240  add     rsp, 250h
0x180014247  pop     r14
0x180014249  pop     rdi
0x18001424a  pop     rsi
0x18001424b  retn
```
