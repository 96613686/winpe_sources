# CGpuManager::LoadDxApis(void)

- ea: `0x18000eea4`
- end: `0x18000f060`
- name: `?LoadDxApis@CGpuManager@@AEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(CGpuManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f2b0`

## callees

- `0x1800074c0`
- `0x18000eea4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f00c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ef90`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000efce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f00c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000eec7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ef4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000eec7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ef4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f01e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000efe0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f01e`

## string_xrefs

- `0x18000eeb8`: `dxgi.dll`
- `0x18000eef3`: `dxgi.dll not found failed: 0x%x in %s`
- `0x18000ef06`: `CreateDXGIFactory1`
- `0x18000ef34`: `GetProcAddress failed to load CreateDXGIFactory1 failed: 0x%x in %s`
- `0x18000ef42`: `gdi32.dll`
- `0x18000ef76`: `gdi32.dll not found failed: 0x%x in %s`
- `0x18000ef89`: `D3DKMTOpenAdapterFromDeviceName`
- `0x18000efb7`: `GetProcAddress failed to load D3DKMTOpenAdapterFromDeviceName failed: 0x%x in %s`

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
0x18000eea4  mov     [rsp+arg_0], rbx
0x18000eea9  mov     [rsp+arg_8], rsi
0x18000eeae  push    rdi
0x18000eeaf  sub     rsp, 20h
0x18000eeb3  mov     rdi, rcx
0x18000eeb6  xor     edx, edx; hFile
0x18000eeb8  lea     rcx, LibFileName; "dxgi.dll"
0x18000eebf  mov     r8d, 800h; dwFlags
0x18000eec5  xor     ebx, ebx
0x18000eec7  call    cs:__imp_LoadLibraryExW
0x18000eecd  mov     [rdi+698h], rax
0x18000eed4  mov     esi, 80070000h
0x18000eed9  test    rax, rax
0x18000eedc  jnz     short loc_18000EEFF
0x18000eede  call    cs:__imp_GetLastError
0x18000eee4  mov     ebx, eax
0x18000eee6  test    eax, eax
0x18000eee8  jle     short loc_18000EEEF
0x18000eeea  movzx   ebx, ax
0x18000eeed  or      ebx, esi
0x18000eeef  test    ebx, ebx
0x18000eef1  jns     short loc_18000EEFF
0x18000eef3  lea     rdx, aDxgiDllNotFoun; "dxgi.dll not found failed: 0x%x in %s"
0x18000eefa  jmp     loc_18000F03A
0x18000eeff  mov     rcx, [rdi+698h]; hModule
0x18000ef06  lea     rdx, ProcName; "CreateDXGIFactory1"
0x18000ef0d  call    cs:__imp_GetProcAddress
0x18000ef13  mov     [rdi+6A0h], rax
0x18000ef1a  test    rax, rax
0x18000ef1d  jnz     short loc_18000EF40
0x18000ef1f  call    cs:__imp_GetLastError
0x18000ef25  mov     ebx, eax
0x18000ef27  test    eax, eax
0x18000ef29  jle     short loc_18000EF30
0x18000ef2b  movzx   ebx, ax
0x18000ef2e  or      ebx, esi
0x18000ef30  test    ebx, ebx
0x18000ef32  jns     short loc_18000EF40
0x18000ef34  lea     rdx, aGetprocaddress_3; "GetProcAddress failed to load CreateDXG"...
0x18000ef3b  jmp     loc_18000F03A
0x18000ef40  xor     edx, edx; hFile
0x18000ef42  lea     rcx, aGdi32Dll; "gdi32.dll"
0x18000ef49  mov     r8d, 800h; dwFlags
0x18000ef4f  call    cs:__imp_LoadLibraryExW
0x18000ef55  mov     [rdi+6A8h], rax
0x18000ef5c  test    rax, rax
0x18000ef5f  jnz     short loc_18000EF82
0x18000ef61  call    cs:__imp_GetLastError
0x18000ef67  mov     ebx, eax
0x18000ef69  test    eax, eax
0x18000ef6b  jle     short loc_18000EF72
0x18000ef6d  movzx   ebx, ax
0x18000ef70  or      ebx, esi
0x18000ef72  test    ebx, ebx
0x18000ef74  jns     short loc_18000EF82
0x18000ef76  lea     rdx, aGdi32DllNotFou; "gdi32.dll not found failed: 0x%x in %s"
0x18000ef7d  jmp     loc_18000F03A
0x18000ef82  mov     rcx, [rdi+6A8h]; hModule
0x18000ef89  lea     rdx, aD3dkmtopenadap_0; "D3DKMTOpenAdapterFromDeviceName"
0x18000ef90  call    cs:__imp_GetProcAddress
0x18000ef96  mov     [rdi+6B0h], rax
0x18000ef9d  test    rax, rax
0x18000efa0  jnz     short loc_18000EFC0
0x18000efa2  call    cs:__imp_GetLastError
0x18000efa8  mov     ebx, eax
0x18000efaa  test    eax, eax
0x18000efac  jle     short loc_18000EFB3
0x18000efae  movzx   ebx, ax
0x18000efb1  or      ebx, esi
0x18000efb3  test    ebx, ebx
0x18000efb5  jns     short loc_18000EFC0
0x18000efb7  lea     rdx, aGetprocaddress; "GetProcAddress failed to load D3DKMTOpe"...
0x18000efbe  jmp     short loc_18000F03A
0x18000efc0  mov     rcx, [rdi+6A8h]; hModule
0x18000efc7  lea     rdx, aD3dkmtqueryada; "D3DKMTQueryAdapterInfo"
0x18000efce  call    cs:__imp_GetProcAddress
0x18000efd4  mov     [rdi+6B8h], rax
0x18000efdb  test    rax, rax
0x18000efde  jnz     short loc_18000EFFE
0x18000efe0  call    cs:__imp_GetLastError
0x18000efe6  mov     ebx, eax
0x18000efe8  test    eax, eax
0x18000efea  jle     short loc_18000EFF1
0x18000efec  movzx   ebx, ax
0x18000efef  or      ebx, esi
0x18000eff1  test    ebx, ebx
0x18000eff3  jns     short loc_18000EFFE
0x18000eff5  lea     rdx, aGetprocaddress_2; "GetProcAddress failed to load D3DKMTQue"...
0x18000effc  jmp     short loc_18000F03A
0x18000effe  mov     rcx, [rdi+6A8h]; hModule
0x18000f005  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x18000f00c  call    cs:__imp_GetProcAddress
0x18000f012  mov     [rdi+6C0h], rax
0x18000f019  test    rax, rax
0x18000f01c  jnz     short loc_18000F04E
0x18000f01e  call    cs:__imp_GetLastError
0x18000f024  mov     ebx, eax
0x18000f026  test    eax, eax
0x18000f028  jle     short loc_18000F02F
0x18000f02a  movzx   ebx, ax
0x18000f02d  or      ebx, esi
0x18000f02f  test    ebx, ebx
0x18000f031  jns     short loc_18000F04E
0x18000f033  lea     rdx, aGetprocaddress_0; "GetProcAddress failed to load D3DKMTClo"...
0x18000f03a  lea     r9, aCgpumanagerLoa_0; "CGpuManager::LoadDxApis"
0x18000f041  mov     r8d, ebx
0x18000f044  mov     ecx, 8; int
0x18000f049  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f04e  mov     rsi, [rsp+28h+arg_8]
0x18000f053  mov     eax, ebx
0x18000f055  mov     rbx, [rsp+28h+arg_0]
0x18000f05a  add     rsp, 20h
0x18000f05e  pop     rdi
0x18000f05f  retn
```
