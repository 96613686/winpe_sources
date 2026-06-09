# LoadDllString(ushort const *,ushort *,uint,ushort const *)

- ea: `0x180026984`
- end: `0x180026b47`
- name: `?LoadDllString@@YAJPEBGPEAGI0@Z`
- size: `451`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800267c0`

## callees

- `0x180026984`
- `0x18009c9a0`
- `0x18009eaea`
- `0x18009ed2c`
- `0x180106a60`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180026af1`
- `msvcrt!_wcsnicmp` at `0x180026af1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180026aba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180026aba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026acb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180026acb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026a9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026b39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026a9c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180026b39`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180026b25`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180026b25`

## string_xrefs

- `0x180026ae7`: `%SystemRoot%\System32\input.dll`
- `0x180026b1e`: `%SystemRoot%\System32\minglobinputhost.dll`

## pseudocode

```c
__int64 __fastcall LoadDllString(WCHAR *a1, unsigned __int16 *a2, int a3, const unsigned __int16 *a4)
{
  __int64 v8; // rax
  WCHAR *v9; // r8
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  unsigned int v12; // ebx
  WCHAR *i; // rcx
  UINT v15; // esi
  HMODULE Library; // rdi
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-468h] BYREF
  WCHAR Dst[264]; // [rsp+230h] [rbp-258h] BYREF

  memset_0(LibFileName, 0, 0x208u);
  v8 = 2147483646;
  v9 = LibFileName;
  v10 = 260;
  do
  {
    if ( !v8 )
      break;
    if ( !*a1 )
      break;
    *v9++ = *a1++;
    --v8;
    --v10;
  }
  while ( v10 );
  v11 = v9 - 1;
  v12 = v10 == 0 ? 0x8007007A : 0;
  if ( v10 )
    v11 = v9;
  *v11 = 0;
  if ( v10 )
  {
    for ( i = LibFileName; ; ++i )
    {
      if ( !*i )
        return 2147500037LL;
      if ( *i == 44 )
        break;
    }
    if ( !i )
      return 2147500037LL;
    *i = 0;
    do
    {
      if ( !*++i )
        return 2147500037LL;
    }
    while ( *i != 45 );
    if ( !i )
      return 2147500037LL;
    v12 = -2147467259;
    v15 = wcstoul_0(i + 1, 0, 10);
    Library = LoadLibraryExW(LibFileName, 0, 2u);
    if ( Library )
    {
LABEL_19:
      if ( Library )
      {
        v12 = LoadStringW(Library, v15, a2, a3) == 0 ? 0x80004005 : 0;
        FreeLibrary(Library);
      }
      return v12;
    }
    if ( !(unsigned __int8)IsInstallLayoutOrTipPresent() && !_wcsnicmp(a4, L"%SystemRoot%\\System32\\input.dll", 0x1Fu) )
    {
      memset_0(Dst, 0, 0x20Au);
      ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\minglobinputhost.dll", Dst, 0x105u);
      Library = LoadLibraryExW(Dst, 0, 2u);
      goto LABEL_19;
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180026984  push    rbx
0x180026986  push    rbp
0x180026987  push    rsi
0x180026988  push    rdi
0x180026989  push    r12
0x18002698b  push    r14
0x18002698d  push    r15
0x18002698f  sub     rsp, 450h
0x180026996  mov     rax, cs:__security_cookie
0x18002699d  xor     rax, rsp
0x1800269a0  mov     [rsp+488h+var_48], rax
0x1800269a8  mov     r15d, r8d
0x1800269ab  mov     r14, rdx
0x1800269ae  mov     rbx, rcx
0x1800269b1  xor     edx, edx; Val
0x1800269b3  mov     r8d, 208h; Size
0x1800269b9  lea     rcx, [rsp+488h+LibFileName]; void *
0x1800269be  mov     rbp, r9
0x1800269c1  call    memset_0
0x1800269c6  mov     eax, 7FFFFFFEh
0x1800269cb  lea     r8, [rsp+488h+LibFileName]
0x1800269d0  mov     edx, 104h
0x1800269d5  xor     r12d, r12d
0x1800269d8  test    rax, rax
0x1800269db  jz      short loc_1800269FA
0x1800269dd  movzx   ecx, word ptr [rbx]
0x1800269e0  test    cx, cx
0x1800269e3  jz      short loc_1800269FA
0x1800269e5  mov     [r8], cx
0x1800269e9  add     rbx, 2
0x1800269ed  add     r8, 2
0x1800269f1  dec     rax
0x1800269f4  sub     rdx, 1
0x1800269f8  jnz     short loc_1800269D8
0x1800269fa  mov     rax, rdx
0x1800269fd  lea     rcx, [r8-2]
0x180026a01  neg     rax
0x180026a04  sbb     ebx, ebx
0x180026a06  not     ebx
0x180026a08  and     ebx, 8007007Ah
0x180026a0e  test    rdx, rdx
0x180026a11  cmovnz  rcx, r8
0x180026a15  mov     [rcx], r12w
0x180026a19  jz      loc_180026AD1
0x180026a1f  lea     rcx, [rsp+488h+LibFileName]
0x180026a24  cmp     [rcx], r12w
0x180026a28  jz      short loc_180026A36
0x180026a2a  cmp     word ptr [rcx], 2Ch ; ','
0x180026a2e  jz      short loc_180026A5D
0x180026a30  add     rcx, 2
0x180026a34  jmp     short loc_180026A24
0x180026a36  mov     eax, 80004005h
0x180026a3b  mov     rcx, [rsp+488h+var_48]
0x180026a43  xor     rcx, rsp; StackCookie
0x180026a46  call    __security_check_cookie
0x180026a4b  add     rsp, 450h
0x180026a52  pop     r15
0x180026a54  pop     r14
0x180026a56  pop     r12
0x180026a58  pop     rdi
0x180026a59  pop     rsi
0x180026a5a  pop     rbp
0x180026a5b  pop     rbx
0x180026a5c  retn
0x180026a5d  test    rcx, rcx
0x180026a60  jz      short loc_180026A36
0x180026a62  mov     [rcx], r12w
0x180026a66  add     rcx, 2
0x180026a6a  cmp     [rcx], r12w
0x180026a6e  jz      short loc_180026A36
0x180026a70  cmp     word ptr [rcx], 2Dh ; '-'
0x180026a74  jnz     short loc_180026A66
0x180026a76  test    rcx, rcx
0x180026a79  jz      short loc_180026A36
0x180026a7b  xor     edx, edx; EndPtr
0x180026a7d  add     rcx, 2; String
0x180026a81  mov     ebx, 80004005h
0x180026a86  lea     r8d, [rdx+0Ah]; Radix
0x180026a8a  call    wcstoul_0
0x180026a8f  xor     edx, edx; hFile
0x180026a91  lea     rcx, [rsp+488h+LibFileName]; lpLibFileName
0x180026a96  mov     esi, eax
0x180026a98  lea     r8d, [rdx+2]; dwFlags
0x180026a9c  call    cs:__imp_LoadLibraryExW
0x180026aa2  mov     rdi, rax
0x180026aa5  test    rax, rax
0x180026aa8  jz      short loc_180026AD8
0x180026aaa  test    rdi, rdi
0x180026aad  jz      short loc_180026AD1
0x180026aaf  mov     r9d, r15d; cchBufferMax
0x180026ab2  mov     r8, r14; lpBuffer
0x180026ab5  mov     edx, esi; uID
0x180026ab7  mov     rcx, rdi; hInstance
0x180026aba  call    cs:__imp_LoadStringW
0x180026ac0  neg     eax
0x180026ac2  sbb     ecx, ecx
0x180026ac4  not     ecx
0x180026ac6  and     ebx, ecx
0x180026ac8  mov     rcx, rdi; hLibModule
0x180026acb  call    cs:__imp_FreeLibrary
0x180026ad1  mov     eax, ebx
0x180026ad3  jmp     loc_180026A3B
0x180026ad8  call    IsInstallLayoutOrTipPresent
0x180026add  test    al, al
0x180026adf  jnz     short loc_180026AD1
0x180026ae1  mov     r8d, 1Fh; MaxCount
0x180026ae7  lea     rdx, aSystemrootSyst; "%SystemRoot%\\System32\\input.dll"
0x180026aee  mov     rcx, rbp; String1
0x180026af1  call    cs:__imp__wcsnicmp
0x180026af7  test    eax, eax
0x180026af9  jnz     short loc_180026AD1
0x180026afb  xor     edx, edx; Val
0x180026afd  lea     rcx, [rsp+488h+Dst]; void *
0x180026b05  mov     r8d, 20Ah; Size
0x180026b0b  call    memset_0
0x180026b10  mov     r8d, 105h; nSize
0x180026b16  lea     rdx, [rsp+488h+Dst]; lpDst
0x180026b1e  lea     rcx, Src; "%SystemRoot%\\System32\\minglobinputhos"...
0x180026b25  call    cs:__imp_ExpandEnvironmentStringsW
0x180026b2b  xor     edx, edx; hFile
0x180026b2d  lea     rcx, [rsp+488h+Dst]; lpLibFileName
0x180026b35  lea     r8d, [rdx+2]; dwFlags
0x180026b39  call    cs:__imp_LoadLibraryExW
0x180026b3f  mov     rdi, rax
0x180026b42  jmp     loc_180026AAA
```
