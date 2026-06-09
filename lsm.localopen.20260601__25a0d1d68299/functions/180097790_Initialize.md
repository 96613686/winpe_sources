# Initialize

- ea: `0x180097790`
- end: `0x1800978de`
- name: `Initialize`
- size: `334`
- prototype: `HRESULT __cdecl()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180097660`

## callees

- `0x1800077a0`
- `0x18004e850`
- `0x18004f354`
- `0x180097790`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180097870`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180097870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097888`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800977cf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800977cf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009781f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009781f`

## string_xrefs

- `0x1800977c8`: `%SystemRoot%\System32\Userenv.dll`
- `0x180097856`: `LoadLibrary failed: 0x%x in %s`

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
0x180097790  push    rbx
0x180097792  sub     rsp, 240h
0x180097799  mov     rax, cs:__security_cookie
0x1800977a0  xor     rax, rsp
0x1800977a3  mov     [rsp+248h+var_18], rax
0x1800977ab  xor     edx, edx; Val
0x1800977ad  lea     rcx, [rsp+248h+Dst]; void *
0x1800977b2  mov     r8d, 20Ah; Size
0x1800977b8  call    memset_0
0x1800977bd  mov     r8d, 105h; nSize
0x1800977c3  lea     rdx, [rsp+248h+Dst]; lpDst
0x1800977c8  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\Userenv.dll"
0x1800977cf  call    cs:__imp_ExpandEnvironmentStringsW
0x1800977d6  nop     dword ptr [rax+rax+00h]
0x1800977db  test    eax, eax
0x1800977dd  jz      short loc_1800977EF
0x1800977df  xor     ebx, ebx
0x1800977e1  cmp     eax, 105h
0x1800977e6  jbe     short loc_18009781A
0x1800977e8  mov     ebx, 54Fh
0x1800977ed  jmp     short loc_180097801
0x1800977ef  call    cs:__imp_GetLastError
0x1800977f6  nop     dword ptr [rax+rax+00h]
0x1800977fb  mov     ebx, eax
0x1800977fd  test    eax, eax
0x1800977ff  jle     short loc_18009780A
0x180097801  movzx   ebx, bx
0x180097804  or      ebx, 80070000h
0x18009780a  test    ebx, ebx
0x18009780c  jns     short loc_18009781A
0x18009780e  lea     rdx, aExpandenvironm; "ExpandEnvironmentStrings failed: 0x%x i"...
0x180097815  jmp     loc_1800978AE
0x18009781a  lea     rcx, [rsp+248h+Dst]; lpLibFileName
0x18009781f  call    cs:__imp_LoadLibraryW
0x180097826  nop     dword ptr [rax+rax+00h]
0x18009782b  mov     cs:?g_hUserEnvDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hUserEnvDll
0x180097832  test    rax, rax
0x180097835  jnz     short loc_180097866
0x180097837  call    cs:__imp_GetLastError
0x18009783e  nop     dword ptr [rax+rax+00h]
0x180097843  mov     ebx, eax
0x180097845  test    eax, eax
0x180097847  jle     short loc_180097852
0x180097849  movzx   ebx, ax
0x18009784c  or      ebx, 80070000h
0x180097852  test    ebx, ebx
0x180097854  jns     short loc_18009785F
0x180097856  lea     rdx, aLoadlibraryFai; "LoadLibrary failed: 0x%x in %s"
0x18009785d  jmp     short loc_1800978AE
0x18009785f  mov     rax, cs:?g_hUserEnvDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hUserEnvDll
0x180097866  lea     rdx, aGetprofiletype; "GetProfileType"
0x18009786d  mov     rcx, rax; hModule
0x180097870  call    cs:__imp_GetProcAddress
0x180097877  nop     dword ptr [rax+rax+00h]
0x18009787c  mov     cs:?pfn_GetProfileType@@3P6AHPEAK@ZEA, rax; int (*pfn_GetProfileType)(ulong *)
0x180097883  test    rax, rax
0x180097886  jnz     short loc_1800978C2
0x180097888  call    cs:__imp_GetLastError
0x18009788f  nop     dword ptr [rax+rax+00h]
0x180097894  mov     ebx, eax
0x180097896  test    eax, eax
0x180097898  jle     short loc_1800978A3
0x18009789a  movzx   ebx, ax
0x18009789d  or      ebx, 80070000h
0x1800978a3  test    ebx, ebx
0x1800978a5  jns     short loc_1800978C2
0x1800978a7  lea     rdx, aGetprocaddress_1; "GetProcAddress GETPROFILETYPE failed: 0"...
0x1800978ae  lea     r9, aRdsappxutilsIn; "RDSAppXUtils::Initialize"
0x1800978b5  mov     r8d, ebx
0x1800978b8  mov     ecx, 8; int
0x1800978bd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800978c2  mov     eax, ebx
0x1800978c4  mov     rcx, [rsp+248h+var_18]
0x1800978cc  xor     rcx, rsp; StackCookie
0x1800978cf  call    __security_check_cookie
0x1800978d4  add     rsp, 240h
0x1800978db  pop     rbx
0x1800978dc  retn
```
