# Windows::Compat::Inventory::AepicInvCache::Initialize(ushort const *,ulong,ulong)

- ea: `0x1800a11f0`
- end: `0x1800a1298`
- name: `?Initialize@AepicInvCache@Inventory@Compat@Windows@@QEAAJPEBGKK@Z`
- size: `168`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a1638`

## callees

- `0x1800a11f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a1210`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a1210`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a1250`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a1250`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a123d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a123d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a121e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a121e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a1290`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a1290`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x1800a127a`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x1800a127a`

## string_xrefs

- `0x1800a1203`: `aepic.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::Initialize(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rsi
  signed int LastError; // eax
  int v7; // ebx
  int v9; // edi
  char *v10; // rbp

  Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    if ( GetProcAddress(Library, (LPCSTR)0x64) )
    {
      v9 = 4;
      v10 = (char *)this + 8;
      while ( 1 )
      {
        v7 = InvCacheOpenVerProvider(v10, 0, a2, 2);
        if ( v7 >= 0 )
          break;
        if ( !--v9 )
          break;
        Sleep(0x64u);
      }
    }
    else
    {
      v7 = -2147467262;
    }
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a11f0  push    rbx
0x1800a11f2  push    rbp
0x1800a11f3  push    rsi
0x1800a11f4  push    rdi
0x1800a11f5  push    r14
0x1800a11f7  sub     rsp, 20h
0x1800a11fb  mov     r14, rdx
0x1800a11fe  mov     rbx, rcx
0x1800a1201  xor     edx, edx; hFile
0x1800a1203  lea     rcx, LibFileName; "aepic.dll"
0x1800a120a  mov     r8d, 800h; dwFlags
0x1800a1210  call    cs:__imp_LoadLibraryExW
0x1800a1216  mov     rsi, rax
0x1800a1219  test    rax, rax
0x1800a121c  jnz     short loc_1800A1235
0x1800a121e  call    cs:__imp_GetLastError
0x1800a1224  mov     ebx, eax
0x1800a1226  test    eax, eax
0x1800a1228  jle     short loc_1800A1256
0x1800a122a  movzx   ebx, ax
0x1800a122d  or      ebx, 80070000h
0x1800a1233  jmp     short loc_1800A1256
0x1800a1235  mov     edx, 64h ; 'd'; lpProcName
0x1800a123a  mov     rcx, rsi; hModule
0x1800a123d  call    cs:__imp_GetProcAddress
0x1800a1243  test    rax, rax
0x1800a1246  jnz     short loc_1800A1263
0x1800a1248  mov     ebx, 80004002h
0x1800a124d  mov     rcx, rsi; hLibModule
0x1800a1250  call    cs:__imp_FreeLibrary
0x1800a1256  mov     eax, ebx
0x1800a1258  add     rsp, 20h
0x1800a125c  pop     r14
0x1800a125e  pop     rdi
0x1800a125f  pop     rsi
0x1800a1260  pop     rbp
0x1800a1261  pop     rbx
0x1800a1262  retn
0x1800a1263  mov     edi, 4
0x1800a1268  lea     rbp, [rbx+8]
0x1800a126c  mov     r9d, 2
0x1800a1272  mov     r8, r14
0x1800a1275  xor     edx, edx
0x1800a1277  mov     rcx, rbp
0x1800a127a  call    cs:__imp_InvCacheOpenVerProvider
0x1800a1280  mov     ebx, eax
0x1800a1282  test    eax, eax
0x1800a1284  jns     short loc_1800A124D
0x1800a1286  add     edi, 0FFFFFFFFh
0x1800a1289  jz      short loc_1800A124D
0x1800a128b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800a1290  call    cs:__imp_Sleep
0x1800a1296  jmp     short loc_1800A126C
```
