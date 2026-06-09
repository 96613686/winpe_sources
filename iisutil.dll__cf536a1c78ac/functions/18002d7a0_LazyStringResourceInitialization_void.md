# LazyStringResourceInitialization(void)

- ea: `0x18002d7a0`
- end: `0x18002d8b3`
- name: `?LazyStringResourceInitialization@@YAJXZ`
- size: `275`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18002d8c0`

## callees

- `0x180019230`
- `0x180019270`
- `0x18002c4f0`
- `0x18002d7a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d7b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d7b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d893`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d893`

## string_xrefs

- `0x18002d7a9`: `iisres.dll`

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
0x18002d7a0  push    rbx
0x18002d7a2  sub     rsp, 20h
0x18002d7a6  xor     r8d, r8d; dwFlags
0x18002d7a9  lea     rcx, LibFileName; "iisres.dll"
0x18002d7b0  xor     edx, edx; hFile
0x18002d7b2  call    cs:__imp_LoadLibraryExW
0x18002d7b9  nop     dword ptr [rax+rax+00h]
0x18002d7be  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hLocalizedResourceDll
0x18002d7c5  test    rax, rax
0x18002d7c8  jnz     short loc_18002D7F6
0x18002d7ca  call    cs:__imp_GetLastError
0x18002d7d1  nop     dword ptr [rax+rax+00h]
0x18002d7d6  mov     ebx, eax
0x18002d7d8  test    eax, eax
0x18002d7da  jle     short loc_18002D7E5
0x18002d7dc  movzx   ebx, ax
0x18002d7df  or      ebx, 80070000h
0x18002d7e5  test    ebx, ebx
0x18002d7e7  jns     loc_18002D8AA
0x18002d7ed  mov     rcx, cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLocalizedLangString
0x18002d7f4  jmp     short loc_18002D872
0x18002d7f6  mov     ecx, 58h ; 'X'; Size
0x18002d7fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d800  test    rax, rax
0x18002d803  jz      short loc_18002D864
0x18002d805  mov     rdx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18002d80c  mov     r8d, 5; unsigned int
0x18002d812  mov     rcx, rax; this
0x18002d815  mov     dword ptr [rax], 0
0x18002d81b  mov     qword ptr [rax+8], 0
0x18002d823  mov     dword ptr [rax+10h], 0
0x18002d82a  mov     qword ptr [rax+18h], 0
0x18002d832  mov     qword ptr [rax+20h], 0
0x18002d83a  mov     dword ptr [rax+28h], 0
0x18002d841  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, rax; LANG_STRING * g_pLocalizedLangString
0x18002d848  call    ?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x18002d84d  mov     ebx, eax
0x18002d84f  test    eax, eax
0x18002d851  js      short loc_18002D7ED
0x18002d853  lock or [rsp+28h+var_28], 0
0x18002d858  mov     cs:?g_fInitialized@@3HA, 1; int g_fInitialized
0x18002d862  jmp     short loc_18002D8AA
0x18002d864  xor     ecx, ecx; Block
0x18002d866  mov     ebx, 80070008h
0x18002d86b  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, rcx; LANG_STRING * g_pLocalizedLangString
0x18002d872  test    rcx, rcx
0x18002d875  jz      short loc_18002D887
0x18002d877  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d87c  mov     cs:?g_pLocalizedLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLocalizedLangString
0x18002d887  mov     rcx, cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002d88e  test    rcx, rcx
0x18002d891  jz      short loc_18002D8AA
0x18002d893  call    cs:__imp_FreeLibrary
0x18002d89a  nop     dword ptr [rax+rax+00h]
0x18002d89f  mov     cs:?g_hLocalizedResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hLocalizedResourceDll
0x18002d8aa  mov     eax, ebx
0x18002d8ac  add     rsp, 20h
0x18002d8b0  pop     rbx
0x18002d8b1  retn
```
