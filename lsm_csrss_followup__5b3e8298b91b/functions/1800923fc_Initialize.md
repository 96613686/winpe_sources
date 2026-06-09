# Initialize

- ea: `0x1800923fc`
- end: `0x180092522`
- name: `Initialize`
- size: `294`
- prototype: `HRESULT __cdecl()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800922d0`

## callees

- `0x1800074c0`
- `0x18004b460`
- `0x18004bf44`
- `0x1800923fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800924c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800924c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009248e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009248e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800924d3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009243b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18009243b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009247c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009247c`

## string_xrefs

- `0x180092434`: `%SystemRoot%\System32\Userenv.dll`
- `0x1800924a7`: `LoadLibrary failed: 0x%x in %s`

## pseudocode

```c
HRESULT __cdecl Initialize()
{
  DWORD v0; // eax
  HRESULT LastError; // ebx
  HMODULE LibraryW; // rax
  signed int v3; // eax
  signed int v4; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x20Au);
  v0 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\Userenv.dll", Dst, 0x105u);
  if ( v0 )
  {
    LastError = 0;
    if ( v0 <= 0x105 )
      goto LABEL_8;
    LOWORD(LastError) = 1359;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_6:
  if ( LastError < 0 )
  {
    _DbgPrintMessage(
      8,
      "ExpandEnvironmentStrings failed: 0x%x in %s",
      (unsigned int)LastError,
      "RDSAppXUtils::Initialize");
    return LastError;
  }
LABEL_8:
  LibraryW = LoadLibraryW(Dst);
  g_hUserEnvDll = LibraryW;
  if ( !LibraryW )
  {
    v3 = GetLastError();
    LastError = v3;
    if ( v3 > 0 )
      LastError = (unsigned __int16)v3 | 0x80070000;
    if ( LastError < 0 )
    {
      _DbgPrintMessage(8, "LoadLibrary failed: 0x%x in %s", (unsigned int)LastError, "RDSAppXUtils::Initialize");
      return LastError;
    }
    LibraryW = g_hUserEnvDll;
  }
  pfn_GetProfileType = (int (*)(unsigned int *))GetProcAddress(LibraryW, "GetProfileType");
  if ( !pfn_GetProfileType )
  {
    v4 = GetLastError();
    LastError = v4;
    if ( v4 > 0 )
      LastError = (unsigned __int16)v4 | 0x80070000;
    if ( LastError < 0 )
      _DbgPrintMessage(
        8,
        "GetProcAddress GETPROFILETYPE failed: 0x%x in %s",
        (unsigned int)LastError,
        "RDSAppXUtils::Initialize");
  }
  return LastError;
}

```

## disassembly

```asm
0x1800923fc  push    rbx
0x1800923fe  sub     rsp, 240h
0x180092405  mov     rax, cs:__security_cookie
0x18009240c  xor     rax, rsp
0x18009240f  mov     [rsp+248h+var_18], rax
0x180092417  xor     edx, edx; Val
0x180092419  lea     rcx, [rsp+248h+Dst]; void *
0x18009241e  mov     r8d, 20Ah; Size
0x180092424  call    memset_0
0x180092429  mov     r8d, 105h; nSize
0x18009242f  lea     rdx, [rsp+248h+Dst]; lpDst
0x180092434  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\Userenv.dll"
0x18009243b  call    cs:__imp_ExpandEnvironmentStringsW
0x180092441  test    eax, eax
0x180092443  jz      short loc_180092455
0x180092445  xor     ebx, ebx
0x180092447  cmp     eax, 105h
0x18009244c  jbe     short loc_180092477
0x18009244e  mov     ebx, 54Fh
0x180092453  jmp     short loc_180092461
0x180092455  call    cs:__imp_GetLastError
0x18009245b  mov     ebx, eax
0x18009245d  test    eax, eax
0x18009245f  jle     short loc_18009246A
0x180092461  movzx   ebx, bx
0x180092464  or      ebx, 80070000h
0x18009246a  test    ebx, ebx
0x18009246c  jns     short loc_180092477
0x18009246e  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings failed: 0x%x i"...
0x180092475  jmp     short loc_1800924F3
0x180092477  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x18009247c  call    cs:__imp_LoadLibraryW
0x180092482  mov     cs:?g_hUserEnvDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hUserEnvDll
0x180092489  test    rax, rax
0x18009248c  jnz     short loc_1800924B7
0x18009248e  call    cs:__imp_GetLastError
0x180092494  mov     ebx, eax
0x180092496  test    eax, eax
0x180092498  jle     short loc_1800924A3
0x18009249a  movzx   ebx, ax
0x18009249d  or      ebx, 80070000h
0x1800924a3  test    ebx, ebx
0x1800924a5  jns     short loc_1800924B0
0x1800924a7  lea     rdx, aLoadlibraryFai; "LoadLibrary failed: 0x%x in %s"
0x1800924ae  jmp     short loc_1800924F3
0x1800924b0  mov     rax, cs:?g_hUserEnvDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hUserEnvDll
0x1800924b7  lea     rdx, aGetprofiletype; "GetProfileType"
0x1800924be  mov     rcx, rax; hModule
0x1800924c1  call    cs:__imp_GetProcAddress
0x1800924c7  mov     cs:?pfn_GetProfileType@@3P6AHPEAK@ZEA, rax; int (*pfn_GetProfileType)(ulong *)
0x1800924ce  test    rax, rax
0x1800924d1  jnz     short loc_180092507
0x1800924d3  call    cs:__imp_GetLastError
0x1800924d9  mov     ebx, eax
0x1800924db  test    eax, eax
0x1800924dd  jle     short loc_1800924E8
0x1800924df  movzx   ebx, ax
0x1800924e2  or      ebx, 80070000h
0x1800924e8  test    ebx, ebx
0x1800924ea  jns     short loc_180092507
0x1800924ec  lea     rdx, aGetprocaddress_1; "GetProcAddress GETPROFILETYPE failed: 0"...
0x1800924f3  lea     r9, aRdsappxutilsIn; "RDSAppXUtils::Initialize"
0x1800924fa  mov     r8d, ebx
0x1800924fd  mov     ecx, 8; int
0x180092502  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180092507  mov     eax, ebx
0x180092509  mov     rcx, [rsp+248h+var_18]
0x180092511  xor     rcx, rsp; StackCookie
0x180092514  call    __security_check_cookie
0x180092519  add     rsp, 240h
0x180092520  pop     rbx
0x180092521  retn
```
