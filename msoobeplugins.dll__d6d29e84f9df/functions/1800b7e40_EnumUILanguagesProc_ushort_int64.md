# EnumUILanguagesProc(ushort *,__int64)

- ea: `0x1800b7e40`
- end: `0x1800b8042`
- name: `?EnumUILanguagesProc@@YAHPEAG_J@Z`
- size: `514`
- prototype: `__int64 __fastcall(__int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003470`
- `0x180003ffc`
- `0x180008b54`
- `0x1800b7bd0`
- `0x1800b7e40`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7f3c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7f0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b7f0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f4e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f4e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b7f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7eef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7fe2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7f88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b7f88`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800b7ee5`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x1800b7ee5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b7f24`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b7f24`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800b7ff1`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800b7ff1`

## string_xrefs

- `0x1800b7f02`: `kernel32.dll`
- `0x1800b7f1a`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnumUILanguagesProc(__int16 *a1, unsigned __int16 *a2)
{
  unsigned __int16 i; // r8
  __int16 v5; // dx
  __int16 v6; // dx
  LANGID v7; // bp
  int v8; // edi
  HMODULE ModuleHandleW; // rbx
  FARPROC ProcAddress; // rax
  DWORD v11; // ecx
  WCHAR Name[88]; // [rsp+40h] [rbp-E8h] BYREF

  memset_0(Name, 0, 0xAEu);
  for ( i = 0; ; i = v5 + 16 * i )
  {
    v6 = *a1;
    if ( !*a1 )
      break;
    if ( (unsigned __int16)(v6 - 65) > 5u )
    {
      if ( (unsigned __int16)(v6 - 48) > 9u )
      {
        if ( (unsigned __int16)(v6 - 97) > 5u )
          break;
        v5 = v6 - 87;
      }
      else
      {
        v5 = v6 - 48;
      }
    }
    else
    {
      v5 = v6 - 55;
    }
    ++a1;
  }
  v7 = i;
  if ( LCIDToLocaleName(i, Name, 85, 0x8000000u) <= 0 )
  {
    if ( !GetLastError() )
    {
LABEL_21:
      v11 = 87;
LABEL_22:
      SetLastError(v11);
    }
    return 0;
  }
  v8 = 0;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  if ( !ModuleHandleW )
  {
    v8 = 1;
    ModuleHandleW = LoadLibraryW(L"kernel32.dll");
    if ( !ModuleHandleW )
      return 0;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "GetUILanguageInfo");
  if ( !ProcAddress )
  {
    if ( v8 )
      FreeLibrary(ModuleHandleW);
    return 0;
  }
  if ( !((unsigned int (__fastcall *)(__int64, WCHAR *, _QWORD))ProcAddress)(8, Name, 0) )
  {
    if ( v8 )
      FreeLibrary(ModuleHandleW);
    goto LABEL_21;
  }
  if ( v8 )
    FreeLibrary(ModuleHandleW);
  if ( a2 && g_uNumLangIdx == g_LangNumber )
  {
    if ( StringCchCopyW(a2, (unsigned int)g_BufferSize, Name) >= 0 )
    {
      g_uNumLangIdx = (GetSystemDefaultUILanguage() == v7) | 0x10000002;
      return 0;
    }
    if ( !GetLastError() )
    {
      v11 = 122;
      goto LABEL_22;
    }
    return 0;
  }
  ++g_uNumLangIdx;
  return 1;
}

```

## disassembly

```asm
0x1800b7e40  mov     [rsp+arg_10], rbx
0x1800b7e45  push    rbp
0x1800b7e46  push    rsi
0x1800b7e47  push    rdi
0x1800b7e48  push    r12
0x1800b7e4a  push    r14
0x1800b7e4c  sub     rsp, 100h
0x1800b7e53  mov     rax, cs:__security_cookie
0x1800b7e5a  xor     rax, rsp
0x1800b7e5d  mov     [rsp+128h+var_38], rax
0x1800b7e65  mov     rsi, rdx
0x1800b7e68  mov     rbx, rcx
0x1800b7e6b  xor     r14d, r14d
0x1800b7e6e  lea     rcx, [rsp+128h+Name]; void *
0x1800b7e73  xor     edx, edx; Val
0x1800b7e75  mov     [rsp+128h+var_F8], r14d
0x1800b7e7a  mov     r8d, 0AEh; Size
0x1800b7e80  call    memset_0
0x1800b7e85  mov     r8d, r14d
0x1800b7e88  lea     r12d, [r14+57h]
0x1800b7e8c  jmp     short loc_1800B7EC6
0x1800b7e8e  lea     eax, [rdx-41h]
0x1800b7e91  cmp     ax, 5
0x1800b7e95  ja      short loc_1800B7E9D
0x1800b7e97  sub     dx, 37h ; '7'
0x1800b7e9b  jmp     short loc_1800B7EB8
0x1800b7e9d  lea     eax, [rdx-30h]
0x1800b7ea0  cmp     ax, 9
0x1800b7ea4  ja      short loc_1800B7EAB
0x1800b7ea6  movzx   edx, ax
0x1800b7ea9  jmp     short loc_1800B7EB8
0x1800b7eab  lea     eax, [rdx-61h]
0x1800b7eae  cmp     ax, 5
0x1800b7eb2  ja      short loc_1800B7ECE
0x1800b7eb4  sub     dx, r12w
0x1800b7eb8  add     rbx, 2
0x1800b7ebc  shl     r8d, 4
0x1800b7ec0  movzx   eax, dx
0x1800b7ec3  add     r8d, eax
0x1800b7ec6  movzx   edx, word ptr [rbx]
0x1800b7ec9  test    dx, dx
0x1800b7ecc  jnz     short loc_1800B7E8E
0x1800b7ece  movzx   ebp, r8w
0x1800b7ed2  lea     rdx, [rsp+128h+Name]; lpName
0x1800b7ed7  mov     ecx, ebp; Locale
0x1800b7ed9  mov     r9d, 8000000h; dwFlags
0x1800b7edf  mov     r8d, 55h ; 'U'; cchName
0x1800b7ee5  call    cs:__imp_LCIDToLocaleName
0x1800b7eeb  test    eax, eax
0x1800b7eed  jg      short loc_1800B7F02
0x1800b7eef  call    cs:__imp_GetLastError
0x1800b7ef5  test    eax, eax
0x1800b7ef7  jnz     loc_1800B7F8E
0x1800b7efd  jmp     loc_1800B7F85
0x1800b7f02  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800b7f09  mov     edi, r14d
0x1800b7f0c  call    cs:__imp_GetModuleHandleW
0x1800b7f12  mov     rbx, rax
0x1800b7f15  test    rax, rax
0x1800b7f18  jnz     short loc_1800B7F32
0x1800b7f1a  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x1800b7f21  lea     edi, [rax+1]
0x1800b7f24  call    cs:__imp_LoadLibraryW
0x1800b7f2a  mov     rbx, rax
0x1800b7f2d  test    rax, rax
0x1800b7f30  jz      short loc_1800B7F8E
0x1800b7f32  lea     rdx, aGetuilanguagei; "GetUILanguageInfo"
0x1800b7f39  mov     rcx, rbx; hModule
0x1800b7f3c  call    cs:__imp_GetProcAddress
0x1800b7f42  test    rax, rax
0x1800b7f45  jnz     short loc_1800B7F56
0x1800b7f47  test    edi, edi
0x1800b7f49  jz      short loc_1800B7F8E
0x1800b7f4b  mov     rcx, rbx; hLibModule
0x1800b7f4e  call    cs:__imp_FreeLibrary
0x1800b7f54  jmp     short loc_1800B7F8E
0x1800b7f56  lea     rcx, [rsp+128h+var_F8]
0x1800b7f5b  xor     r9d, r9d
0x1800b7f5e  mov     [rsp+128h+var_108], rcx
0x1800b7f63  lea     rdx, [rsp+128h+Name]
0x1800b7f68  xor     r8d, r8d
0x1800b7f6b  lea     ecx, [r9+8]
0x1800b7f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f74  test    eax, eax
0x1800b7f76  jnz     short loc_1800B7F95
0x1800b7f78  test    edi, edi
0x1800b7f7a  jz      short loc_1800B7F85
0x1800b7f7c  mov     rcx, rbx; hLibModule
0x1800b7f7f  call    cs:__imp_FreeLibrary
0x1800b7f85  mov     ecx, r12d; dwErrCode
0x1800b7f88  call    cs:__imp_SetLastError
0x1800b7f8e  xor     eax, eax
0x1800b7f90  jmp     loc_1800B801B
0x1800b7f95  test    edi, edi
0x1800b7f97  jz      short loc_1800B7FA2
0x1800b7f99  mov     rcx, rbx; hLibModule
0x1800b7f9c  call    cs:__imp_FreeLibrary
0x1800b7fa2  test    byte ptr [rsp+128h+var_F8], 4
0x1800b7fa7  jz      short loc_1800B7FB8
0x1800b7fa9  mov     rdx, rsi; unsigned __int16 *
0x1800b7fac  lea     rcx, [rsp+128h+Name]; unsigned __int16 *
0x1800b7fb1  call    ?EnumUILIPHelper@@YAHPEBGPEAGK@Z; EnumUILIPHelper(ushort const *,ushort *,ulong)
0x1800b7fb6  jmp     short loc_1800B801B
0x1800b7fb8  mov     eax, cs:?g_uNumLangIdx@@3IA; uint g_uNumLangIdx
0x1800b7fbe  test    rsi, rsi
0x1800b7fc1  jz      short loc_1800B800E
0x1800b7fc3  cmp     eax, cs:?g_LangNumber@@3IA; uint g_LangNumber
0x1800b7fc9  jnz     short loc_1800B800E
0x1800b7fcb  mov     edx, cs:?g_BufferSize@@3IA; unsigned __int64
0x1800b7fd1  lea     r8, [rsp+128h+Name]; unsigned __int16 *
0x1800b7fd6  mov     rcx, rsi; unsigned __int16 *
0x1800b7fd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b7fde  test    eax, eax
0x1800b7fe0  jns     short loc_1800B7FF1
0x1800b7fe2  call    cs:__imp_GetLastError
0x1800b7fe8  test    eax, eax
0x1800b7fea  jnz     short loc_1800B7F8E
0x1800b7fec  lea     ecx, [rax+7Ah]
0x1800b7fef  jmp     short loc_1800B7F88
0x1800b7ff1  call    cs:__imp_GetSystemDefaultUILanguage
0x1800b7ff7  cmp     ax, bp
0x1800b7ffa  mov     ecx, r14d
0x1800b7ffd  setz    cl
0x1800b8000  or      ecx, 10000002h
0x1800b8006  mov     cs:?g_uNumLangIdx@@3IA, ecx; uint g_uNumLangIdx
0x1800b800c  jmp     short loc_1800B7F8E
0x1800b800e  inc     eax
0x1800b8010  mov     cs:?g_uNumLangIdx@@3IA, eax; uint g_uNumLangIdx
0x1800b8016  mov     eax, 1
0x1800b801b  mov     rcx, [rsp+128h+var_38]
0x1800b8023  xor     rcx, rsp; StackCookie
0x1800b8026  call    __security_check_cookie
0x1800b802b  mov     rbx, [rsp+128h+arg_10]
0x1800b8033  add     rsp, 100h
0x1800b803a  pop     r14
0x1800b803c  pop     r12
0x1800b803e  pop     rdi
0x1800b803f  pop     rsi
0x1800b8040  pop     rbp
0x1800b8041  retn
```
