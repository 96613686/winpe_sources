# LazyStringResourceInitialization(void)

- ea: `0x18002b7f8`
- end: `0x18002b8f8`
- name: `?LazyStringResourceInitialization@@YAJXZ`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002b900`

## callees

- `0x1800183f8`
- `0x180018438`
- `0x18002a610`
- `0x18002b7f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b81c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b81c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b80a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002b80a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b8df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002b8df`

## string_xrefs

- `0x18002b801`: `iisres.dll`

## pseudocode

```c
__int64 LazyStringResourceInitialization(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  LANG_STRING *v2; // rcx
  _QWORD *v3; // rax
  HINSTANCE v4; // rdx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  g_hLocalizedResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
  if ( g_hLocalizedResourceDll )
  {
    v3 = operator new(0x58u);
    if ( !v3 )
    {
      v2 = 0;
      v1 = -2147024888;
      g_pLocalizedLangString = 0;
      goto LABEL_10;
    }
    v4 = g_hLocalizedResourceDll;
    *(_DWORD *)v3 = 0;
    v3[1] = 0;
    *((_DWORD *)v3 + 4) = 0;
    v3[3] = 0;
    v3[4] = 0;
    *((_DWORD *)v3 + 10) = 0;
    g_pLocalizedLangString = (LANG_STRING *)v3;
    v1 = LANG_STRING::Initialize((LANG_STRING *)v3, v4, 5u);
    if ( v1 >= 0 )
    {
      _InterlockedOr(v6, 0);
      g_fInitialized = 1;
      return (unsigned int)v1;
    }
LABEL_5:
    v2 = g_pLocalizedLangString;
LABEL_10:
    if ( v2 )
    {
      operator delete(v2);
      g_pLocalizedLangString = 0;
    }
    if ( g_hLocalizedResourceDll )
    {
      FreeLibrary(g_hLocalizedResourceDll);
      g_hLocalizedResourceDll = 0;
    }
    return (unsigned int)v1;
  }
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 < 0 )
    goto LABEL_5;
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002b7f8  push    rbx
0x18002b7fa  sub     rsp, 20h
0x18002b7fe  xor     r8d, r8d; dwFlags
0x18002b801  lea     rcx, LibFileName; "iisres.dll"
0x18002b808  xor     edx, edx; hFile
0x18002b80a  call    cs:__imp_LoadLibraryExW
0x18002b810  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hLocalizedResourceDll
0x18002b817  test    rax, rax
0x18002b81a  jnz     short loc_18002B842
0x18002b81c  call    cs:__imp_GetLastError
0x18002b822  mov     ebx, eax
0x18002b824  test    eax, eax
0x18002b826  jle     short loc_18002B831
0x18002b828  movzx   ebx, ax
0x18002b82b  or      ebx, 80070000h
0x18002b831  test    ebx, ebx
0x18002b833  jns     loc_18002B8F0
0x18002b839  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLocalizedLangString
0x18002b840  jmp     short loc_18002B8BE
0x18002b842  mov     ecx, 58h ; 'X'; Size
0x18002b847  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b84c  test    rax, rax
0x18002b84f  jz      short loc_18002B8B0
0x18002b851  mov     rdx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18002b858  mov     r8d, 5; unsigned int
0x18002b85e  mov     rcx, rax; this
0x18002b861  mov     dword ptr [rax], 0
0x18002b867  mov     qword ptr [rax+8], 0
0x18002b86f  mov     dword ptr [rax+10h], 0
0x18002b876  mov     qword ptr [rax+18h], 0
0x18002b87e  mov     qword ptr [rax+20h], 0
0x18002b886  mov     dword ptr [rax+28h], 0
0x18002b88d  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, rax; LANG_STRING * g_pLocalizedLangString
0x18002b894  call    ?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x18002b899  mov     ebx, eax
0x18002b89b  test    eax, eax
0x18002b89d  js      short loc_18002B839
0x18002b89f  lock or [rsp+28h+var_28], 0
0x18002b8a4  mov     cs:?g_fInitialized@@3HA, 1; int g_fInitialized
0x18002b8ae  jmp     short loc_18002B8F0
0x18002b8b0  xor     ecx, ecx; Block
0x18002b8b2  mov     ebx, 80070008h
0x18002b8b7  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, rcx; LANG_STRING * g_pLocalizedLangString
0x18002b8be  test    rcx, rcx
0x18002b8c1  jz      short loc_18002B8D3
0x18002b8c3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002b8c8  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLocalizedLangString
0x18002b8d3  mov     rcx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002b8da  test    rcx, rcx
0x18002b8dd  jz      short loc_18002B8F0
0x18002b8df  call    cs:__imp_FreeLibrary
0x18002b8e5  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hLocalizedResourceDll
0x18002b8f0  mov     eax, ebx
0x18002b8f2  add     rsp, 20h
0x18002b8f6  pop     rbx
0x18002b8f7  retn
```
