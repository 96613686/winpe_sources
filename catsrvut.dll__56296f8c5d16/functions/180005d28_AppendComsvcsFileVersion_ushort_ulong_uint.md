# AppendComsvcsFileVersion(ushort *,ulong,uint *)

- ea: `0x180005d28`
- end: `0x180006032`
- name: `?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z`
- size: `778`
- prototype: `void __fastcall(unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005944`

## callees

- `0x180001e60`
- `0x180005d28`
- `0x18000717c`
- `0x18000e3b8`
- `0x18005582e`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005e5f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005e5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005ddd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005ddd`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180005e86`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180005e86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005e3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005e3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005e74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005e74`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005dbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005dbb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180005ee7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180005f3c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180005ee7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180005f3c`

## string_xrefs

- `0x180005d4f`: `\nComsvcs.dll file version info: %s %s %s`
- `0x180005e38`: `comsvcs.dll`
- `0x180005db4`: `comres.dll`

## pseudocode

```c
void __fastcall AppendComsvcsFileVersion(unsigned __int16 *a1, __int64 a2, unsigned int *a3)
{
  __int64 v3; // rbx
  const wchar_t *v4; // r9
  __int64 v5; // rcx
  WCHAR *v6; // rax
  __int64 v8; // rdx
  WCHAR *v9; // rcx
  HMODULE Library; // rax
  const wchar_t *v11; // rcx
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rcx
  HMODULE ModuleHandleW; // rax
  HMODULE v16; // rbx
  HRSRC Resource; // rax
  HGLOBAL v18; // rax
  unsigned __int16 *v19; // rax
  const void *v20; // r9
  size_t v21; // r8
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  void *v24; // rsp
  unsigned int i; // ecx
  _BYTE *v26; // r8
  unsigned int v27; // r9d
  bool v28; // zf
  const unsigned __int16 *v29; // r8
  unsigned int pBlock; // [rsp+40h] [rbp+0h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp+8h] BYREF
  LPVOID v32; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int16 v33[8]; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int16 v34[12]; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int16 v35[56]; // [rsp+80h] [rbp+40h] BYREF

  v3 = 2147483646;
  v4 = L"\r\nComsvcs.dll file version info: %s %s %s";
  v5 = 2147483646;
  v6 = &Filename;
  v8 = 129;
  do
  {
    if ( !v5 )
      break;
    if ( !*v4 )
      break;
    *v6++ = *v4++;
    --v5;
    --v8;
  }
  while ( v8 );
  v9 = v6 - 1;
  if ( v8 )
    v9 = v6;
  Library = g_hModCOMRes;
  *v9 = 0;
  Filename = 0;
  if ( !Library )
  {
    Library = LoadLibraryExW(L"comres.dll", 0, 2u);
    g_hModCOMRes = Library;
  }
  LoadStringW(Library, 0x3AFu, &Filename, 128);
  v11 = L"not loaded";
  lpBuffer = 0;
  v12 = 50;
  v32 = 0;
  v13 = v35;
  pBlock = 0;
  v34[0] = 0;
  do
  {
    if ( !v3 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v3;
    --v12;
  }
  while ( v12 );
  v33[0] = 0;
  v14 = v13 - 1;
  if ( v12 )
    v14 = v13;
  *v14 = 0;
  ModuleHandleW = GetModuleHandleW(L"comsvcs.dll");
  v16 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    Resource = FindResourceExW(ModuleHandleW, (LPCWSTR)0x10, (LPCWSTR)1, 0);
    if ( Resource )
    {
      v18 = LoadResource(v16, Resource);
      if ( v18 )
      {
        v19 = (unsigned __int16 *)LockResource(v18);
        v20 = v19;
        if ( v19 )
        {
          v21 = *v19;
          v22 = (unsigned int)v21 + (*v19 >> 1);
          v23 = v22 + 15;
          if ( v22 + 15 <= v22 )
            v23 = 0xFFFFFFFFFFFFFF0LL;
          v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
          memcpy_0(&pBlock, v20, v21);
          if ( VerQueryValueW(&pBlock, L"\\VarFileInfo\\Translation", &lpBuffer, &pBlock) )
          {
            for ( i = 0; i < 0x27; ++i )
            {
              if ( *(_WORD *)lpBuffer == LOWORD(qword_18005F060[2 * i]) )
              {
                StringCchCopyW(v34, 5u, (const unsigned __int16 *)qword_18005F060[2 * i + 1]);
                break;
              }
            }
          }
          if ( VerQueryValueW(&pBlock, L"\\", &v32, &pBlock) )
          {
            v26 = v32;
            v27 = *((_DWORD *)v32 + 2);
            if ( v27 != -1 )
            {
              StringCchPrintfW(
                v35,
                0x32u,
                L"%u.%u.%u.%u",
                HIWORD(v27),
                (unsigned __int16)v27,
                *((unsigned __int16 *)v32 + 7),
                *((unsigned __int16 *)v32 + 6));
              v26 = v32;
            }
            v28 = (v26[28] & 1) == 0;
            v29 = L"dbg";
            if ( v28 )
              v29 = L"shp";
            StringCchCopyW(v33, 5u, v29);
          }
        }
      }
    }
  }
  StringCchPrintfW(&word_180074070, 0x400u, &Filename, v34, v35, v33);
  if ( *a3 )
  {
    lpBuffer = 0;
    StringCchCatExW(&word_180073860, 0x400u, &word_180074070, 0, (unsigned __int64 *)&lpBuffer, 0x1000u);
    *a3 = (unsigned int)lpBuffer;
  }
}

```

## disassembly

```asm
0x180005d28  push    rbp
0x180005d2a  push    rbx
0x180005d2b  push    rsi
0x180005d2c  push    rdi
0x180005d2d  sub     rsp, 108h
0x180005d34  lea     rbp, [rsp+40h]
0x180005d39  mov     rax, cs:__security_cookie
0x180005d40  xor     rax, rbp
0x180005d43  mov     [rbp+0E0h+var_30], rax
0x180005d4a  mov     ebx, 7FFFFFFEh
0x180005d4f  lea     r9, aComsvcsDllFile; "\r\nComsvcs.dll file version info: %s %"...
0x180005d56  mov     ecx, ebx
0x180005d58  lea     rax, Filename
0x180005d5f  mov     rdi, r8
0x180005d62  mov     edx, 81h
0x180005d67  xor     esi, esi
0x180005d69  test    rcx, rcx
0x180005d6c  jz      short loc_180005D8D
0x180005d6e  movzx   r8d, word ptr [r9]
0x180005d72  test    r8w, r8w
0x180005d76  jz      short loc_180005D8D
0x180005d78  mov     [rax], r8w
0x180005d7c  add     r9, 2
0x180005d80  add     rax, 2
0x180005d84  dec     rcx
0x180005d87  sub     rdx, 1
0x180005d8b  jnz     short loc_180005D69
0x180005d8d  test    rdx, rdx
0x180005d90  lea     rcx, [rax-2]
0x180005d94  cmovnz  rcx, rax
0x180005d98  mov     rax, cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModCOMRes
0x180005d9f  mov     [rcx], si
0x180005da2  mov     cs:Filename, si
0x180005da9  test    rax, rax
0x180005dac  jnz     short loc_180005DC8
0x180005dae  xor     edx, edx; hFile
0x180005db0  lea     r8d, [rax+2]; dwFlags
0x180005db4  lea     rcx, LibFileName; "comres.dll"
0x180005dbb  call    cs:__imp_LoadLibraryExW
0x180005dc1  mov     cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModCOMRes
0x180005dc8  mov     r9d, 80h; cchBufferMax
0x180005dce  lea     r8, Filename; lpBuffer
0x180005dd5  mov     edx, 3AFh; uID
0x180005dda  mov     rcx, rax; hInstance
0x180005ddd  call    cs:__imp_LoadStringW
0x180005de3  lea     rcx, aNotLoaded; "not loaded"
0x180005dea  mov     [rbp+0E0h+lpBuffer], rsi
0x180005dee  mov     edx, 32h ; '2'
0x180005df3  mov     [rbp+0E0h+var_D0], rsi
0x180005df7  lea     rax, [rbp+0E0h+var_A0]
0x180005dfb  mov     [rbp+0E0h+pBlock], esi
0x180005dfe  mov     [rbp+0E0h+var_B8], si
0x180005e02  test    rbx, rbx
0x180005e05  jz      short loc_180005E26
0x180005e07  movzx   r8d, word ptr [rcx]
0x180005e0b  test    r8w, r8w
0x180005e0f  jz      short loc_180005E26
0x180005e11  mov     [rax], r8w
0x180005e15  add     rcx, 2
0x180005e19  add     rax, 2
0x180005e1d  dec     rbx
0x180005e20  sub     rdx, 1
0x180005e24  jnz     short loc_180005E02
0x180005e26  test    rdx, rdx
0x180005e29  mov     [rbp+0E0h+var_C8], si
0x180005e2d  lea     rcx, [rax-2]
0x180005e31  cmovnz  rcx, rax
0x180005e35  mov     [rcx], si
0x180005e38  lea     rcx, ModuleName; "comsvcs.dll"
0x180005e3f  call    cs:__imp_GetModuleHandleW
0x180005e45  mov     rbx, rax
0x180005e48  test    rax, rax
0x180005e4b  jz      loc_180005FB1
0x180005e51  xor     r9d, r9d; wLanguage
0x180005e54  mov     rcx, rax; hModule
0x180005e57  lea     edx, [r9+10h]; lpType
0x180005e5b  lea     r8d, [r9+1]; lpName
0x180005e5f  call    cs:__imp_FindResourceExW
0x180005e65  test    rax, rax
0x180005e68  jz      loc_180005FB1
0x180005e6e  mov     rdx, rax; hResInfo
0x180005e71  mov     rcx, rbx; hModule
0x180005e74  call    cs:__imp_LoadResource
0x180005e7a  test    rax, rax
0x180005e7d  jz      loc_180005FB1
0x180005e83  mov     rcx, rax; hResData
0x180005e86  call    cs:__imp_LockResource
0x180005e8c  mov     r9, rax
0x180005e8f  test    rax, rax
0x180005e92  jz      loc_180005FB1
0x180005e98  movzx   r8d, word ptr [rax]
0x180005e9c  mov     ecx, r8d
0x180005e9f  shr     ecx, 1
0x180005ea1  add     ecx, r8d
0x180005ea4  mov     edx, ecx
0x180005ea6  lea     rax, [rcx+0Fh]
0x180005eaa  cmp     rax, rdx
0x180005ead  ja      short loc_180005EB9
0x180005eaf  mov     rax, 0FFFFFFFFFFFFFF0h
0x180005eb9  and     rax, 0FFFFFFFFFFFFFFF0h
0x180005ebd  call    _alloca_probe
0x180005ec2  sub     rsp, rax
0x180005ec5  mov     rdx, r9; Src
0x180005ec8  lea     rbx, [rsp+120h+pBlock]
0x180005ecd  mov     rcx, rbx; void *
0x180005ed0  call    memcpy_0
0x180005ed5  lea     r9, [rbp+0E0h+pBlock]; puLen
0x180005ed9  mov     rcx, rbx; pBlock
0x180005edc  lea     r8, [rbp+0E0h+lpBuffer]; lplpBuffer
0x180005ee0  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180005ee7  call    cs:__imp_VerQueryValueW
0x180005eed  test    eax, eax
0x180005eef  jz      short loc_180005F2A
0x180005ef1  mov     rdx, [rbp+0E0h+lpBuffer]
0x180005ef5  lea     r9, qword_18005F060
0x180005efc  mov     ecx, esi
0x180005efe  cmp     ecx, 27h ; '''
0x180005f01  jnb     short loc_180005F2A
0x180005f03  mov     r8d, ecx
0x180005f06  add     r8, r8
0x180005f09  movzx   eax, word ptr [r9+r8*8]
0x180005f0e  cmp     [rdx], ax
0x180005f11  jz      short loc_180005F17
0x180005f13  inc     ecx
0x180005f15  jmp     short loc_180005EFE
0x180005f17  mov     r8, [r9+r8*8+8]; unsigned __int16 *
0x180005f1c  lea     rcx, [rbp+0E0h+var_B8]; unsigned __int16 *
0x180005f20  mov     edx, 5; unsigned __int64
0x180005f25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005f2a  lea     r9, [rbp+0E0h+pBlock]; puLen
0x180005f2e  mov     rcx, rbx; pBlock
0x180005f31  lea     r8, [rbp+0E0h+var_D0]; lplpBuffer
0x180005f35  lea     rdx, asc_180061B34; "\\"
0x180005f3c  call    cs:__imp_VerQueryValueW
0x180005f42  test    eax, eax
0x180005f44  jz      short loc_180005FB1
0x180005f46  mov     r8, [rbp+0E0h+var_D0]
0x180005f4a  mov     r9d, [r8+8]
0x180005f4e  cmp     r9d, 0FFFFFFFFh
0x180005f52  jz      short loc_180005F8C
0x180005f54  movzx   ecx, word ptr [r8+0Eh]
0x180005f59  mov     edx, 32h ; '2'; unsigned __int64
0x180005f5e  movzx   eax, word ptr [r8+0Ch]
0x180005f63  movzx   r8d, r9w
0x180005f67  mov     [rsp+120h+var_F0], eax
0x180005f6b  mov     [rsp+120h+var_F8], ecx
0x180005f6f  lea     rcx, [rbp+0E0h+var_A0]; unsigned __int16 *
0x180005f73  mov     dword ptr [rsp+120h+var_100], r8d
0x180005f78  lea     r8, aUUUU; "%u.%u.%u.%u"
0x180005f7f  shr     r9d, 10h
0x180005f83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005f88  mov     r8, [rbp+0E0h+var_D0]
0x180005f8c  test    byte ptr [r8+1Ch], 1
0x180005f91  lea     rax, aShp; "shp"
0x180005f98  lea     r8, aDbg; "dbg"
0x180005f9f  mov     edx, 5; unsigned __int64
0x180005fa4  cmovz   r8, rax; unsigned __int16 *
0x180005fa8  lea     rcx, [rbp+0E0h+var_C8]; unsigned __int16 *
0x180005fac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005fb1  lea     rax, [rbp+0E0h+var_C8]
0x180005fb5  mov     ebx, 400h
0x180005fba  mov     qword ptr [rsp+120h+var_F8], rax
0x180005fbf  lea     r9, [rbp+0E0h+var_B8]
0x180005fc3  lea     rax, [rbp+0E0h+var_A0]
0x180005fc7  mov     edx, ebx; unsigned __int64
0x180005fc9  lea     r8, Filename; unsigned __int16 *
0x180005fd0  mov     [rsp+120h+var_100], rax
0x180005fd5  lea     rcx, word_180074070; unsigned __int16 *
0x180005fdc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005fe1  cmp     [rdi], esi
0x180005fe3  jz      short loc_180006017
0x180005fe5  lea     rax, [rbp+0E0h+lpBuffer]
0x180005fe9  mov     [rsp+120h+var_F8], 1000h; unsigned int
0x180005ff1  xor     r9d, r9d; unsigned __int16 **
0x180005ff4  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x180005ff9  lea     r8, word_180074070; unsigned __int16 *
0x180006000  mov     [rbp+0E0h+lpBuffer], rsi
0x180006004  mov     edx, ebx; unsigned __int64
0x180006006  lea     rcx, word_180073860; psz
0x18000600d  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180006012  mov     eax, dword ptr [rbp+0E0h+lpBuffer]
0x180006015  mov     [rdi], eax
0x180006017  mov     rcx, [rbp+0E0h+var_30]
0x18000601e  xor     rcx, rbp; StackCookie
0x180006021  call    __security_check_cookie
0x180006026  lea     rsp, [rbp+0C8h]
0x18000602d  pop     rdi
0x18000602e  pop     rsi
0x18000602f  pop     rbx
0x180006030  pop     rbp
0x180006031  retn
```
