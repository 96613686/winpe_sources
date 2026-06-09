# AppendComsvcsFileVersion(ushort *,ulong,uint *)

- ea: `0x180014898`
- end: `0x180014b8c`
- name: `?AppendComsvcsFileVersion@@YAXPEAGKPEAI@Z`
- size: `756`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7c0`

## callees

- `0x180008a50`
- `0x180014898`
- `0x180016f3c`
- `0x180025104`
- `0x180089578`
- `0x1800b8420`
- `0x1800b84e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001492b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001492b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001494d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001494d`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800149f6`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800149f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800149e4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800149e4`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800149cf`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800149cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800149af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800149af`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014a57`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014aac`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014a57`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180014aac`

## string_xrefs

- `0x1800148bf`: `\nComsvcs.dll file version info: %s %s %s`
- `0x1800149a8`: `comsvcs.dll`
- `0x180014924`: `comres.dll`

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
  unsigned __int64 v30; // rdx
  unsigned __int16 *v31; // rcx
  unsigned __int16 **v32; // r9
  unsigned int pBlock; // [rsp+40h] [rbp+0h] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp+8h] BYREF
  LPVOID v35; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int16 v36[8]; // [rsp+58h] [rbp+18h] BYREF
  unsigned __int16 v37[12]; // [rsp+68h] [rbp+28h] BYREF
  unsigned __int16 v38[56]; // [rsp+80h] [rbp+40h] BYREF

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
  v35 = 0;
  v13 = v38;
  pBlock = 0;
  v37[0] = 0;
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
  v36[0] = 0;
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
              if ( *(_WORD *)lpBuffer == LOWORD(qword_180119E60[2 * i]) )
              {
                StringCchCopyW(v37, 5u, (const unsigned __int16 *)qword_180119E60[2 * i + 1]);
                break;
              }
            }
          }
          if ( VerQueryValueW(&pBlock, L"\\", &v35, &pBlock) )
          {
            v26 = v35;
            v27 = *((_DWORD *)v35 + 2);
            if ( v27 != -1 )
            {
              StringCchPrintfW(
                v38,
                0x32u,
                L"%u.%u.%u.%u",
                HIWORD(v27),
                (unsigned __int16)v27,
                *((unsigned __int16 *)v35 + 7),
                *((unsigned __int16 *)v35 + 6));
              v26 = v35;
            }
            v28 = (v26[28] & 1) == 0;
            v29 = L"dbg";
            if ( v28 )
              v29 = L"shp";
            StringCchCopyW(v36, 5u, v29);
          }
        }
      }
    }
  }
  StringCchPrintfW(&word_180166D90, 0x400u, &Filename, v37, v38);
  if ( *a3 )
  {
    lpBuffer = 0;
    StringCchCatExW(v31, v30, &word_180166D90, v32, (unsigned __int64 *)&lpBuffer, (unsigned int)v36);
    *a3 = (unsigned int)lpBuffer;
  }
}

```

## disassembly

```asm
0x180014898  push    rbp
0x18001489a  push    rbx
0x18001489b  push    rsi
0x18001489c  push    rdi
0x18001489d  sub     rsp, 108h
0x1800148a4  lea     rbp, [rsp+40h]
0x1800148a9  mov     rax, cs:__security_cookie
0x1800148b0  xor     rax, rbp
0x1800148b3  mov     [rbp+0E0h+var_30], rax
0x1800148ba  mov     ebx, 7FFFFFFEh
0x1800148bf  lea     r9, aComsvcsDllFile; "\r\nComsvcs.dll file version info: %s %"...
0x1800148c6  mov     ecx, ebx
0x1800148c8  lea     rax, Filename
0x1800148cf  mov     rdi, r8
0x1800148d2  mov     edx, 81h
0x1800148d7  xor     esi, esi
0x1800148d9  test    rcx, rcx
0x1800148dc  jz      short loc_1800148FD
0x1800148de  movzx   r8d, word ptr [r9]
0x1800148e2  test    r8w, r8w
0x1800148e6  jz      short loc_1800148FD
0x1800148e8  mov     [rax], r8w
0x1800148ec  add     r9, 2
0x1800148f0  add     rax, 2
0x1800148f4  dec     rcx
0x1800148f7  sub     rdx, 1
0x1800148fb  jnz     short loc_1800148D9
0x1800148fd  test    rdx, rdx
0x180014900  lea     rcx, [rax-2]
0x180014904  cmovnz  rcx, rax
0x180014908  mov     rax, cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModCOMRes
0x18001490f  mov     [rcx], si
0x180014912  mov     cs:Filename, si
0x180014919  test    rax, rax
0x18001491c  jnz     short loc_180014938
0x18001491e  xor     edx, edx; hFile
0x180014920  lea     r8d, [rax+2]; dwFlags
0x180014924  lea     rcx, aComresDll_0; "comres.dll"
0x18001492b  call    cs:__imp_LoadLibraryExW
0x180014931  mov     cs:?g_hModCOMRes@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hModCOMRes
0x180014938  mov     r9d, 80h; cchBufferMax
0x18001493e  lea     r8, Filename; lpBuffer
0x180014945  mov     edx, 3AFh; uID
0x18001494a  mov     rcx, rax; hInstance
0x18001494d  call    cs:__imp_LoadStringW
0x180014953  lea     rcx, aNotLoaded; "not loaded"
0x18001495a  mov     [rbp+0E0h+lpBuffer], rsi
0x18001495e  mov     edx, 32h ; '2'
0x180014963  mov     [rbp+0E0h+var_D0], rsi
0x180014967  lea     rax, [rbp+0E0h+var_A0]
0x18001496b  mov     [rbp+0E0h+pBlock], esi
0x18001496e  mov     [rbp+0E0h+var_B8], si
0x180014972  test    rbx, rbx
0x180014975  jz      short loc_180014996
0x180014977  movzx   r8d, word ptr [rcx]
0x18001497b  test    r8w, r8w
0x18001497f  jz      short loc_180014996
0x180014981  mov     [rax], r8w
0x180014985  add     rcx, 2
0x180014989  add     rax, 2
0x18001498d  dec     rbx
0x180014990  sub     rdx, 1
0x180014994  jnz     short loc_180014972
0x180014996  test    rdx, rdx
0x180014999  mov     [rbp+0E0h+var_C8], si
0x18001499d  lea     rcx, [rax-2]
0x1800149a1  cmovnz  rcx, rax
0x1800149a5  mov     [rcx], si
0x1800149a8  lea     rcx, ModuleName; "comsvcs.dll"
0x1800149af  call    cs:__imp_GetModuleHandleW
0x1800149b5  mov     rbx, rax
0x1800149b8  test    rax, rax
0x1800149bb  jz      loc_180014B21
0x1800149c1  xor     r9d, r9d; wLanguage
0x1800149c4  mov     rcx, rax; hModule
0x1800149c7  lea     edx, [r9+10h]; lpType
0x1800149cb  lea     r8d, [r9+1]; lpName
0x1800149cf  call    cs:__imp_FindResourceExW
0x1800149d5  test    rax, rax
0x1800149d8  jz      loc_180014B21
0x1800149de  mov     rdx, rax; hResInfo
0x1800149e1  mov     rcx, rbx; hModule
0x1800149e4  call    cs:__imp_LoadResource
0x1800149ea  test    rax, rax
0x1800149ed  jz      loc_180014B21
0x1800149f3  mov     rcx, rax; hResData
0x1800149f6  call    cs:__imp_LockResource
0x1800149fc  mov     r9, rax
0x1800149ff  test    rax, rax
0x180014a02  jz      loc_180014B21
0x180014a08  movzx   r8d, word ptr [rax]
0x180014a0c  mov     ecx, r8d
0x180014a0f  shr     ecx, 1
0x180014a11  add     ecx, r8d
0x180014a14  mov     edx, ecx
0x180014a16  lea     rax, [rcx+0Fh]
0x180014a1a  cmp     rax, rdx
0x180014a1d  ja      short loc_180014A29
0x180014a1f  mov     rax, 0FFFFFFFFFFFFFF0h
0x180014a29  and     rax, 0FFFFFFFFFFFFFFF0h
0x180014a2d  call    _alloca_probe
0x180014a32  sub     rsp, rax
0x180014a35  mov     rdx, r9; Src
0x180014a38  lea     rbx, [rsp+120h+pBlock]
0x180014a3d  mov     rcx, rbx; void *
0x180014a40  call    memcpy_0
0x180014a45  lea     r9, [rbp+0E0h+pBlock]; puLen
0x180014a49  mov     rcx, rbx; pBlock
0x180014a4c  lea     r8, [rbp+0E0h+lpBuffer]; lplpBuffer
0x180014a50  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180014a57  call    cs:__imp_VerQueryValueW
0x180014a5d  test    eax, eax
0x180014a5f  jz      short loc_180014A9A
0x180014a61  mov     rdx, [rbp+0E0h+lpBuffer]
0x180014a65  lea     r9, qword_180119E60
0x180014a6c  mov     ecx, esi
0x180014a6e  cmp     ecx, 27h ; '''
0x180014a71  jnb     short loc_180014A9A
0x180014a73  mov     r8d, ecx
0x180014a76  add     r8, r8
0x180014a79  movzx   eax, word ptr [r9+r8*8]
0x180014a7e  cmp     [rdx], ax
0x180014a81  jz      short loc_180014A87
0x180014a83  inc     ecx
0x180014a85  jmp     short loc_180014A6E
0x180014a87  mov     r8, [r9+r8*8+8]; unsigned __int16 *
0x180014a8c  lea     rcx, [rbp+0E0h+var_B8]; unsigned __int16 *
0x180014a90  mov     edx, 5; unsigned __int64
0x180014a95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014a9a  lea     r9, [rbp+0E0h+pBlock]; puLen
0x180014a9e  mov     rcx, rbx; pBlock
0x180014aa1  lea     r8, [rbp+0E0h+var_D0]; lplpBuffer
0x180014aa5  lea     rdx, asc_180135D78; "\\"
0x180014aac  call    cs:__imp_VerQueryValueW
0x180014ab2  test    eax, eax
0x180014ab4  jz      short loc_180014B21
0x180014ab6  mov     r8, [rbp+0E0h+var_D0]
0x180014aba  mov     r9d, [r8+8]
0x180014abe  cmp     r9d, 0FFFFFFFFh
0x180014ac2  jz      short loc_180014AFC
0x180014ac4  movzx   ecx, word ptr [r8+0Eh]
0x180014ac9  mov     edx, 32h ; '2'; unsigned __int64
0x180014ace  movzx   eax, word ptr [r8+0Ch]
0x180014ad3  movzx   r8d, r9w
0x180014ad7  mov     [rsp+120h+var_F0], eax
0x180014adb  mov     [rsp+120h+var_F8], ecx
0x180014adf  lea     rcx, [rbp+0E0h+var_A0]; unsigned __int16 *
0x180014ae3  mov     dword ptr [rsp+120h+var_100], r8d
0x180014ae8  lea     r8, aUUUU; "%u.%u.%u.%u"
0x180014aef  shr     r9d, 10h
0x180014af3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014af8  mov     r8, [rbp+0E0h+var_D0]
0x180014afc  test    byte ptr [r8+1Ch], 1
0x180014b01  lea     rax, aShp; "shp"
0x180014b08  lea     r8, aDbg; "dbg"
0x180014b0f  mov     edx, 5; unsigned __int64
0x180014b14  cmovz   r8, rax; unsigned __int16 *
0x180014b18  lea     rcx, [rbp+0E0h+var_C8]; unsigned __int16 *
0x180014b1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180014b21  lea     rax, [rbp+0E0h+var_C8]
0x180014b25  mov     edx, 400h; unsigned __int64
0x180014b2a  mov     qword ptr [rsp+120h+var_F8], rax; unsigned int
0x180014b2f  lea     r9, [rbp+0E0h+var_B8]
0x180014b33  lea     rax, [rbp+0E0h+var_A0]
0x180014b37  lea     r8, Filename; unsigned __int16 *
0x180014b3e  mov     [rsp+120h+var_100], rax
0x180014b43  lea     rcx, word_180166D90; unsigned __int16 *
0x180014b4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014b4f  cmp     [rdi], esi
0x180014b51  jz      short loc_180014B71
0x180014b53  lea     rax, [rbp+0E0h+lpBuffer]
0x180014b57  mov     [rbp+0E0h+lpBuffer], rsi
0x180014b5b  lea     r8, word_180166D90; unsigned __int16 *
0x180014b62  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x180014b67  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180014b6c  mov     eax, dword ptr [rbp+0E0h+lpBuffer]
0x180014b6f  mov     [rdi], eax
0x180014b71  mov     rcx, [rbp+0E0h+var_30]
0x180014b78  xor     rcx, rbp; StackCookie
0x180014b7b  call    __security_check_cookie
0x180014b80  lea     rsp, [rbp+0C8h]
0x180014b87  pop     rdi
0x180014b88  pop     rsi
0x180014b89  pop     rbx
0x180014b8a  pop     rbp
0x180014b8b  retn
```
