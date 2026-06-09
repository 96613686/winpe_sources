# _LoadDllString(ushort const *,ushort *,uint)

- ea: `0x180083ae8`
- end: `0x180083bb2`
- name: `?_LoadDllString@@YAJPEBGPEAGI@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPWSTR lpBuffer, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002cd94`

## callees

- `0x18002cfd0`
- `0x18002f9e0`
- `0x180053b34`
- `0x18006ed20`
- `0x180083ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083b87`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083b87`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180083b47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180083b47`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180083b2e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathParseIconLocationW` at `0x180083b2e`

## pseudocode

```c
__int64 __fastcall _LoadDllString(const unsigned __int16 *a1, LPWSTR lpBuffer)
{
  int v3; // ebx
  int v4; // eax
  UINT v5; // edi
  HMODULE Library; // rax
  unsigned int v7; // r9d
  HMODULE v8; // rsi
  int String; // eax
  int pszIconFile[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v3 = StringCchCopyW((unsigned __int16 *)pszIconFile, 0x104u, a1);
  if ( v3 >= 0 )
  {
    v3 = -2147467259;
    v4 = PathParseIconLocationW((LPWSTR)pszIconFile);
    v5 = -v4;
    if ( -v4 >= 0 && v4 != 0 )
    {
      Library = LoadLibraryExW((LPCWSTR)pszIconFile, 0, 2u);
      v8 = Library;
      if ( Library )
      {
        String = _SafeLoadString(Library, v5, lpBuffer, v7);
        v3 = String;
        if ( String < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x40,
            (unsigned int)"onecoreuap\\shell\\propsys\\propdesc.cpp",
            (const char *)(unsigned int)String,
            pszIconFile[0]);
        FreeLibrary(v8);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180083ae8  mov     [rsp+arg_10], rbx
0x180083aed  push    rbp
0x180083aee  push    rsi
0x180083aef  push    rdi
0x180083af0  sub     rsp, 240h
0x180083af7  mov     rax, cs:__security_cookie
0x180083afe  xor     rax, rsp
0x180083b01  mov     [rsp+258h+var_28], rax
0x180083b09  mov     rbp, rdx
0x180083b0c  mov     r8, rcx; unsigned __int16 *
0x180083b0f  mov     edx, 104h; unsigned __int64
0x180083b14  lea     rcx, [rsp+258h+pszIconFile]; unsigned __int16 *
0x180083b19  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083b1e  mov     ebx, eax
0x180083b20  test    eax, eax
0x180083b22  js      short loc_180083B8D
0x180083b24  lea     rcx, [rsp+258h+pszIconFile]; pszIconFile
0x180083b29  mov     ebx, 80004005h
0x180083b2e  call    cs:__imp_PathParseIconLocationW
0x180083b34  mov     edi, eax
0x180083b36  neg     edi
0x180083b38  test    edi, edi
0x180083b3a  jle     short loc_180083B8D
0x180083b3c  xor     edx, edx; hFile
0x180083b3e  lea     rcx, [rsp+258h+pszIconFile]; lpLibFileName
0x180083b43  lea     r8d, [rdx+2]; dwFlags
0x180083b47  call    cs:__imp_LoadLibraryExW
0x180083b4d  mov     rsi, rax
0x180083b50  test    rax, rax
0x180083b53  jz      short loc_180083B8D
0x180083b55  mov     r8, rbp; lpBuffer
0x180083b58  mov     edx, edi; uID
0x180083b5a  mov     rcx, rax; hInstance
0x180083b5d  call    ?_SafeLoadString@@YAJPEAUHINSTANCE__@@IPEAGI@Z; _SafeLoadString(HINSTANCE__ *,uint,ushort *,uint)
0x180083b62  mov     ebx, eax
0x180083b64  test    eax, eax
0x180083b66  jns     short loc_180083B84
0x180083b68  mov     rcx, [rsp+258h]; this
0x180083b70  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\propsys\\propdesc.cp"...
0x180083b77  mov     r9d, eax; char *
0x180083b7a  mov     edx, 40h ; '@'; void *
0x180083b7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083b84  mov     rcx, rsi; hLibModule
0x180083b87  call    cs:__imp_FreeLibrary
0x180083b8d  mov     eax, ebx
0x180083b8f  mov     rcx, [rsp+258h+var_28]
0x180083b97  xor     rcx, rsp; StackCookie
0x180083b9a  call    __security_check_cookie
0x180083b9f  mov     rbx, [rsp+258h+arg_10]
0x180083ba7  add     rsp, 240h
0x180083bae  pop     rdi
0x180083baf  pop     rsi
0x180083bb0  pop     rbp
0x180083bb1  retn
```
