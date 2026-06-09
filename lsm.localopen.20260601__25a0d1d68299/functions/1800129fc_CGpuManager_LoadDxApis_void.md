# CGpuManager::LoadDxApis(void)

- ea: `0x1800129fc`
- end: `0x180012c04`
- name: `?LoadDxApis@CGpuManager@@AEAAJXZ`
- size: `520`
- prototype: `__int64 __fastcall(CGpuManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180012e54`

## callees

- `0x1800077a0`
- `0x1800129fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012a71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ba3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012a71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012b59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012ba3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012a1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012abf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012a1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bbb`

## string_xrefs

- `0x180012a10`: `dxgi.dll`
- `0x180012a57`: `dxgi.dll not found failed: 0x%x in %s`
- `0x180012a6a`: `CreateDXGIFactory1`
- `0x180012aa4`: `GetProcAddress failed to load CreateDXGIFactory1 failed: 0x%x in %s`
- `0x180012ab2`: `gdi32.dll`
- `0x180012af2`: `gdi32.dll not found failed: 0x%x in %s`
- `0x180012b05`: `D3DKMTOpenAdapterFromDeviceName`
- `0x180012b3f`: `GetProcAddress failed to load D3DKMTOpenAdapterFromDeviceName failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CGpuManager::LoadDxApis(CGpuManager *this)
{
  signed int v2; // ebx
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v6; // eax
  HMODULE v7; // rax
  signed int v8; // eax
  FARPROC v9; // rax
  signed int v10; // eax
  FARPROC v11; // rax
  signed int v12; // eax
  FARPROC v13; // rax
  signed int v14; // eax

  v2 = 0;
  Library = LoadLibraryExW(L"dxgi.dll", 0, 0x800u);
  *((_QWORD *)this + 211) = Library;
  if ( Library )
    goto LABEL_6;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_6:
    ProcAddress = GetProcAddress(*((HMODULE *)this + 211), "CreateDXGIFactory1");
    *((_QWORD *)this + 212) = ProcAddress;
    if ( ProcAddress )
      goto LABEL_11;
    v6 = GetLastError();
    v2 = v6;
    if ( v6 > 0 )
      v2 = (unsigned __int16)v6 | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_11:
      v7 = LoadLibraryExW(L"gdi32.dll", 0, 0x800u);
      *((_QWORD *)this + 213) = v7;
      if ( v7 )
        goto LABEL_16;
      v8 = GetLastError();
      v2 = v8;
      if ( v8 > 0 )
        v2 = (unsigned __int16)v8 | 0x80070000;
      if ( v2 >= 0 )
      {
LABEL_16:
        v9 = GetProcAddress(*((HMODULE *)this + 213), "D3DKMTOpenAdapterFromDeviceName");
        *((_QWORD *)this + 214) = v9;
        if ( v9 )
          goto LABEL_21;
        v10 = GetLastError();
        v2 = v10;
        if ( v10 > 0 )
          v2 = (unsigned __int16)v10 | 0x80070000;
        if ( v2 >= 0 )
        {
LABEL_21:
          v11 = GetProcAddress(*((HMODULE *)this + 213), "D3DKMTQueryAdapterInfo");
          *((_QWORD *)this + 215) = v11;
          if ( v11 )
            goto LABEL_26;
          v12 = GetLastError();
          v2 = v12;
          if ( v12 > 0 )
            v2 = (unsigned __int16)v12 | 0x80070000;
          if ( v2 >= 0 )
          {
LABEL_26:
            v13 = GetProcAddress(*((HMODULE *)this + 213), "D3DKMTCloseAdapter");
            *((_QWORD *)this + 216) = v13;
            if ( !v13 )
            {
              v14 = GetLastError();
              v2 = v14;
              if ( v14 > 0 )
                v2 = (unsigned __int16)v14 | 0x80070000;
              if ( v2 < 0 )
                _DbgPrintMessage(
                  8,
                  "GetProcAddress failed to load D3DKMTCloseAdapter failed: 0x%x in %s",
                  (unsigned int)v2,
                  "CGpuManager::LoadDxApis");
            }
          }
          else
          {
            _DbgPrintMessage(
              8,
              "GetProcAddress failed to load D3DKMTQueryAdapterInfo failed: 0x%x in %s",
              (unsigned int)v2,
              "CGpuManager::LoadDxApis");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "GetProcAddress failed to load D3DKMTOpenAdapterFromDeviceName failed: 0x%x in %s",
            (unsigned int)v2,
            "CGpuManager::LoadDxApis");
        }
      }
      else
      {
        _DbgPrintMessage(8, "gdi32.dll not found failed: 0x%x in %s", (unsigned int)v2, "CGpuManager::LoadDxApis");
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "GetProcAddress failed to load CreateDXGIFactory1 failed: 0x%x in %s",
        (unsigned int)v2,
        "CGpuManager::LoadDxApis");
    }
  }
  else
  {
    _DbgPrintMessage(8, "dxgi.dll not found failed: 0x%x in %s", (unsigned int)v2, "CGpuManager::LoadDxApis");
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800129fc  mov     [rsp+arg_0], rbx
0x180012a01  mov     [rsp+arg_8], rsi
0x180012a06  push    rdi
0x180012a07  sub     rsp, 20h
0x180012a0b  mov     rdi, rcx
0x180012a0e  xor     edx, edx; hFile
0x180012a10  lea     rcx, LibFileName; "dxgi.dll"
0x180012a17  mov     r8d, 800h; dwFlags
0x180012a1d  xor     ebx, ebx
0x180012a1f  call    cs:__imp_LoadLibraryExW
0x180012a26  nop     dword ptr [rax+rax+00h]
0x180012a2b  mov     [rdi+698h], rax
0x180012a32  mov     esi, 80070000h
0x180012a37  test    rax, rax
0x180012a3a  jnz     short loc_180012A63
0x180012a3c  call    cs:__imp_GetLastError
0x180012a43  nop     dword ptr [rax+rax+00h]
0x180012a48  mov     ebx, eax
0x180012a4a  test    eax, eax
0x180012a4c  jle     short loc_180012A53
0x180012a4e  movzx   ebx, ax
0x180012a51  or      ebx, esi
0x180012a53  test    ebx, ebx
0x180012a55  jns     short loc_180012A63
0x180012a57  lea     rdx, aDxgiDllNotFoun; "dxgi.dll not found failed: 0x%x in %s"
0x180012a5e  jmp     loc_180012BDD
0x180012a63  mov     rcx, [rdi+698h]; hModule
0x180012a6a  lea     rdx, ProcName; "CreateDXGIFactory1"
0x180012a71  call    cs:__imp_GetProcAddress
0x180012a78  nop     dword ptr [rax+rax+00h]
0x180012a7d  mov     [rdi+6A0h], rax
0x180012a84  test    rax, rax
0x180012a87  jnz     short loc_180012AB0
0x180012a89  call    cs:__imp_GetLastError
0x180012a90  nop     dword ptr [rax+rax+00h]
0x180012a95  mov     ebx, eax
0x180012a97  test    eax, eax
0x180012a99  jle     short loc_180012AA0
0x180012a9b  movzx   ebx, ax
0x180012a9e  or      ebx, esi
0x180012aa0  test    ebx, ebx
0x180012aa2  jns     short loc_180012AB0
0x180012aa4  lea     rdx, aGetprocaddress_3; "GetProcAddress failed to load CreateDXG"...
0x180012aab  jmp     loc_180012BDD
0x180012ab0  xor     edx, edx; hFile
0x180012ab2  lea     rcx, aGdi32Dll; "gdi32.dll"
0x180012ab9  mov     r8d, 800h; dwFlags
0x180012abf  call    cs:__imp_LoadLibraryExW
0x180012ac6  nop     dword ptr [rax+rax+00h]
0x180012acb  mov     [rdi+6A8h], rax
0x180012ad2  test    rax, rax
0x180012ad5  jnz     short loc_180012AFE
0x180012ad7  call    cs:__imp_GetLastError
0x180012ade  nop     dword ptr [rax+rax+00h]
0x180012ae3  mov     ebx, eax
0x180012ae5  test    eax, eax
0x180012ae7  jle     short loc_180012AEE
0x180012ae9  movzx   ebx, ax
0x180012aec  or      ebx, esi
0x180012aee  test    ebx, ebx
0x180012af0  jns     short loc_180012AFE
0x180012af2  lea     rdx, aGdi32DllNotFou; "gdi32.dll not found failed: 0x%x in %s"
0x180012af9  jmp     loc_180012BDD
0x180012afe  mov     rcx, [rdi+6A8h]; hModule
0x180012b05  lea     rdx, aD3dkmtopenadap_0; "D3DKMTOpenAdapterFromDeviceName"
0x180012b0c  call    cs:__imp_GetProcAddress
0x180012b13  nop     dword ptr [rax+rax+00h]
0x180012b18  mov     [rdi+6B0h], rax
0x180012b1f  test    rax, rax
0x180012b22  jnz     short loc_180012B4B
0x180012b24  call    cs:__imp_GetLastError
0x180012b2b  nop     dword ptr [rax+rax+00h]
0x180012b30  mov     ebx, eax
0x180012b32  test    eax, eax
0x180012b34  jle     short loc_180012B3B
0x180012b36  movzx   ebx, ax
0x180012b39  or      ebx, esi
0x180012b3b  test    ebx, ebx
0x180012b3d  jns     short loc_180012B4B
0x180012b3f  lea     rdx, aGetprocaddress; "GetProcAddress failed to load D3DKMTOpe"...
0x180012b46  jmp     loc_180012BDD
0x180012b4b  mov     rcx, [rdi+6A8h]; hModule
0x180012b52  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x180012b59  call    cs:__imp_GetProcAddress
0x180012b60  nop     dword ptr [rax+rax+00h]
0x180012b65  mov     [rdi+6B8h], rax
0x180012b6c  test    rax, rax
0x180012b6f  jnz     short loc_180012B95
0x180012b71  call    cs:__imp_GetLastError
0x180012b78  nop     dword ptr [rax+rax+00h]
0x180012b7d  mov     ebx, eax
0x180012b7f  test    eax, eax
0x180012b81  jle     short loc_180012B88
0x180012b83  movzx   ebx, ax
0x180012b86  or      ebx, esi
0x180012b88  test    ebx, ebx
0x180012b8a  jns     short loc_180012B95
0x180012b8c  lea     rdx, aGetprocaddress_2; "GetProcAddress failed to load D3DKMTQue"...
0x180012b93  jmp     short loc_180012BDD
0x180012b95  mov     rcx, [rdi+6A8h]; hModule
0x180012b9c  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x180012ba3  call    cs:__imp_GetProcAddress
0x180012baa  nop     dword ptr [rax+rax+00h]
0x180012baf  mov     [rdi+6C0h], rax
0x180012bb6  test    rax, rax
0x180012bb9  jnz     short loc_180012BF1
0x180012bbb  call    cs:__imp_GetLastError
0x180012bc2  nop     dword ptr [rax+rax+00h]
0x180012bc7  mov     ebx, eax
0x180012bc9  test    eax, eax
0x180012bcb  jle     short loc_180012BD2
0x180012bcd  movzx   ebx, ax
0x180012bd0  or      ebx, esi
0x180012bd2  test    ebx, ebx
0x180012bd4  jns     short loc_180012BF1
0x180012bd6  lea     rdx, aGetprocaddress_0; "GetProcAddress failed to load D3DKMTClo"...
0x180012bdd  lea     r9, aCgpumanagerLoa_0; "CGpuManager::LoadDxApis"
0x180012be4  mov     r8d, ebx
0x180012be7  mov     ecx, 8; int
0x180012bec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180012bf1  mov     rsi, [rsp+28h+arg_8]
0x180012bf6  mov     eax, ebx
0x180012bf8  mov     rbx, [rsp+28h+arg_0]
0x180012bfd  add     rsp, 20h
0x180012c01  pop     rdi
0x180012c02  retn
```
