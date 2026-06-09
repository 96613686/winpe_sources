# COMPRESSION_SCHEME::Initialize(INativeConfigurationElement *)

- ea: `0x180003cc0`
- end: `0x180003fa2`
- name: `?Initialize@COMPRESSION_SCHEME@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `738`
- prototype: `signed int __fastcall(COMPRESSION_SCHEME *this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800012b0`

## callees

- `0x180003cc0`
- `0x180008010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003e21`
- `msvcrt!_wcsicmp` at `0x180003e44`
- `msvcrt!_wcsicmp` at `0x180003e21`
- `msvcrt!_wcsicmp` at `0x180003e44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e71`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003d28`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003d28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d11`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f25`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003e9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003eef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f25`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180003e5f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180003e5f`

## string_xrefs

- `0x180003da0`: `doStaticCompression`
- `0x180003d73`: `doDynamicCompression`
- `0x180003dcd`: `dynamicCompressionLevel`
- `0x180003dfa`: `staticCompressionLevel`
- `0x180003e94`: `InitCompression`
- `0x180003eab`: `DeInitCompression`
- `0x180003ec6`: `CreateCompression`
- `0x180003ee1`: `Compress`
- `0x180003efc`: `Compress2`
- `0x180003f17`: `DestroyCompression`

## pseudocode

```c
signed int __fastcall COMPRESSION_SCHEME::Initialize(COMPRESSION_SCHEME *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  signed int result; // eax
  int v6; // eax
  int v7; // ecx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  HMODULE v10; // rcx
  FARPROC v11; // rax
  HMODULE v12; // rcx
  FARPROC v13; // rax
  HMODULE v14; // rcx
  FARPROC v15; // rax
  HMODULE v16; // rcx
  FARPROC v17; // rax
  HMODULE v18; // rcx
  FARPROC v19; // rax
  __int64 (*v20)(void); // rcx
  wchar_t *String1; // [rsp+58h] [rbp+10h] BYREF
  LPCWSTR lpLibFileName; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(_QWORD *)a2;
  String1 = 0;
  lpLibFileName = 0;
  result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(v2 + 64))(
             a2,
             L"name",
             &String1,
             0,
             0);
  if ( result >= 0 )
  {
    result = STRU::Copy(this, String1);
    if ( result >= 0 )
    {
      result = STRA::CopyW((COMPRESSION_SCHEME *)((char *)this + 56), String1);
      if ( result >= 0 )
      {
        result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, LPCWSTR *, _QWORD, _QWORD))(*(_QWORD *)a2 + 64LL))(
                   a2,
                   L"dll",
                   &lpLibFileName,
                   0,
                   0);
        if ( result >= 0 )
        {
          result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                     a2,
                     L"doDynamicCompression",
                     (char *)this + 236,
                     0,
                     0);
          if ( result >= 0 )
          {
            result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 72LL))(
                       a2,
                       L"doStaticCompression",
                       (char *)this + 240,
                       0,
                       0);
            if ( result >= 0 )
            {
              result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
                         a2,
                         L"dynamicCompressionLevel",
                         (char *)this + 224,
                         0,
                         0);
              if ( result >= 0 )
              {
                result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 48LL))(
                           a2,
                           L"staticCompressionLevel",
                           (char *)this + 228,
                           0,
                           0);
                if ( result >= 0 )
                {
                  if ( _wcsicmp(String1, L"deflate") )
                  {
                    v6 = _wcsicmp(String1, L"gzip");
                    v7 = -1;
                    if ( !v6 )
                      v7 = 1;
                    *((_DWORD *)this + 58) = v7;
                  }
                  else
                  {
                    *((_DWORD *)this + 58) = 0;
                  }
                  LibraryW = LoadLibraryW(lpLibFileName);
                  *((_QWORD *)this + 21) = LibraryW;
                  if ( LibraryW )
                  {
                    ProcAddress = GetProcAddress(LibraryW, "InitCompression");
                    v10 = (HMODULE)*((_QWORD *)this + 21);
                    *((_QWORD *)this + 22) = ProcAddress;
                    v11 = GetProcAddress(v10, "DeInitCompression");
                    v12 = (HMODULE)*((_QWORD *)this + 21);
                    *((_QWORD *)this + 23) = v11;
                    v13 = GetProcAddress(v12, "CreateCompression");
                    v14 = (HMODULE)*((_QWORD *)this + 21);
                    *((_QWORD *)this + 24) = v13;
                    v15 = GetProcAddress(v14, "Compress");
                    v16 = (HMODULE)*((_QWORD *)this + 21);
                    *((_QWORD *)this + 25) = v15;
                    v17 = GetProcAddress(v16, "Compress2");
                    v18 = (HMODULE)*((_QWORD *)this + 21);
                    *((_QWORD *)this + 26) = v17;
                    v19 = GetProcAddress(v18, "DestroyCompression");
                    v20 = (__int64 (*)(void))*((_QWORD *)this + 22);
                    *((_QWORD *)this + 27) = v19;
                    if ( v20
                      && *((_QWORD *)this + 23)
                      && *((_QWORD *)this + 24)
                      && (*((_QWORD *)this + 25) || *((_QWORD *)this + 26))
                      && v19 )
                    {
                      result = v20();
                      if ( result >= 0 )
                      {
                        if ( *((_DWORD *)this + 59) )
                          HTTP_COMPRESSION::sm_fDoDynamicCompression = 1;
                        return 0;
                      }
                    }
                    else
                    {
                      return -2147024769;
                    }
                  }
                  else
                  {
                    result = GetLastError();
                    if ( result > 0 )
                      return (unsigned __int16)result | 0x80070000;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003cc0  mov     [rsp+arg_0], rbx
0x180003cc5  push    rbp
0x180003cc6  push    rsi
0x180003cc7  push    rdi
0x180003cc8  sub     rsp, 30h
0x180003ccc  mov     rax, [rdx]
0x180003ccf  lea     r8, [rsp+48h+String1]
0x180003cd4  mov     rdi, rdx
0x180003cd7  xor     ebp, ebp
0x180003cd9  mov     rbx, rcx
0x180003cdc  mov     [rsp+48h+String1], rbp
0x180003ce1  xor     r9d, r9d
0x180003ce4  mov     [rsp+48h+lpLibFileName], rbp
0x180003ce9  mov     rax, [rax+40h]
0x180003ced  lea     rdx, aName; "name"
0x180003cf4  mov     rcx, rdi
0x180003cf7  mov     [rsp+48h+var_28], rbp
0x180003cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d01  test    eax, eax
0x180003d03  js      loc_180003F95
0x180003d09  mov     rdx, [rsp+48h+String1]
0x180003d0e  mov     rcx, rbx
0x180003d11  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003d17  test    eax, eax
0x180003d19  js      loc_180003F95
0x180003d1f  mov     rdx, [rsp+48h+String1]
0x180003d24  lea     rcx, [rbx+38h]
0x180003d28  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180003d2e  test    eax, eax
0x180003d30  js      loc_180003F95
0x180003d36  mov     rax, [rdi]
0x180003d39  lea     r8, [rsp+48h+lpLibFileName]
0x180003d3e  xor     r9d, r9d
0x180003d41  mov     [rsp+48h+var_28], rbp
0x180003d46  lea     rdx, aDll; "dll"
0x180003d4d  mov     rcx, rdi
0x180003d50  mov     rax, [rax+40h]
0x180003d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d59  test    eax, eax
0x180003d5b  js      loc_180003F95
0x180003d61  mov     rax, [rdi]
0x180003d64  lea     r8, [rbx+0ECh]
0x180003d6b  xor     r9d, r9d
0x180003d6e  mov     [rsp+48h+var_28], rbp
0x180003d73  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x180003d7a  mov     rcx, rdi
0x180003d7d  mov     rax, [rax+48h]
0x180003d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d86  test    eax, eax
0x180003d88  js      loc_180003F95
0x180003d8e  mov     rax, [rdi]
0x180003d91  lea     r8, [rbx+0F0h]
0x180003d98  xor     r9d, r9d
0x180003d9b  mov     [rsp+48h+var_28], rbp
0x180003da0  lea     rdx, aDostaticcompre; "doStaticCompression"
0x180003da7  mov     rcx, rdi
0x180003daa  mov     rax, [rax+48h]
0x180003dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db3  test    eax, eax
0x180003db5  js      loc_180003F95
0x180003dbb  mov     rax, [rdi]
0x180003dbe  lea     r8, [rbx+0E0h]
0x180003dc5  xor     r9d, r9d
0x180003dc8  mov     [rsp+48h+var_28], rbp
0x180003dcd  lea     rdx, aDynamiccompres_1; "dynamicCompressionLevel"
0x180003dd4  mov     rcx, rdi
0x180003dd7  mov     rax, [rax+30h]
0x180003ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de0  test    eax, eax
0x180003de2  js      loc_180003F95
0x180003de8  mov     rax, [rdi]
0x180003deb  lea     r8, [rbx+0E4h]
0x180003df2  xor     r9d, r9d
0x180003df5  mov     [rsp+48h+var_28], rbp
0x180003dfa  lea     rdx, aStaticcompress; "staticCompressionLevel"
0x180003e01  mov     rcx, rdi
0x180003e04  mov     rax, [rax+30h]
0x180003e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e0d  test    eax, eax
0x180003e0f  js      loc_180003F95
0x180003e15  mov     rcx, [rsp+48h+String1]; String1
0x180003e1a  lea     rdx, aDeflate; "deflate"
0x180003e21  call    cs:__imp__wcsicmp
0x180003e27  mov     edi, 1
0x180003e2c  test    eax, eax
0x180003e2e  jnz     short loc_180003E38
0x180003e30  mov     [rbx+0E8h], ebp
0x180003e36  jmp     short loc_180003E5A
0x180003e38  mov     rcx, [rsp+48h+String1]; String1
0x180003e3d  lea     rdx, aGzip; "gzip"
0x180003e44  call    cs:__imp__wcsicmp
0x180003e4a  test    eax, eax
0x180003e4c  mov     ecx, 0FFFFFFFFh
0x180003e51  cmovz   ecx, edi
0x180003e54  mov     [rbx+0E8h], ecx
0x180003e5a  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x180003e5f  call    cs:__imp_LoadLibraryW
0x180003e65  mov     [rbx+0A8h], rax
0x180003e6c  test    rax, rax
0x180003e6f  jnz     short loc_180003E94
0x180003e71  call    cs:__imp_GetLastError
0x180003e77  test    eax, eax
0x180003e79  jle     loc_180003F95
0x180003e7f  movzx   eax, ax
0x180003e82  or      eax, 80070000h
0x180003e87  mov     rbx, [rsp+48h+arg_0]
0x180003e8c  add     rsp, 30h
0x180003e90  pop     rdi
0x180003e91  pop     rsi
0x180003e92  pop     rbp
0x180003e93  retn
0x180003e94  lea     rdx, ProcName; "InitCompression"
0x180003e9b  mov     rcx, rax; hModule
0x180003e9e  call    cs:__imp_GetProcAddress
0x180003ea4  mov     rcx, [rbx+0A8h]; hModule
0x180003eab  lea     rdx, aDeinitcompress; "DeInitCompression"
0x180003eb2  mov     [rbx+0B0h], rax
0x180003eb9  call    cs:__imp_GetProcAddress
0x180003ebf  mov     rcx, [rbx+0A8h]; hModule
0x180003ec6  lea     rdx, aCreatecompress; "CreateCompression"
0x180003ecd  mov     [rbx+0B8h], rax
0x180003ed4  call    cs:__imp_GetProcAddress
0x180003eda  mov     rcx, [rbx+0A8h]; hModule
0x180003ee1  lea     rdx, aCompress; "Compress"
0x180003ee8  mov     [rbx+0C0h], rax
0x180003eef  call    cs:__imp_GetProcAddress
0x180003ef5  mov     rcx, [rbx+0A8h]; hModule
0x180003efc  lea     rdx, aCompress2; "Compress2"
0x180003f03  mov     [rbx+0C8h], rax
0x180003f0a  call    cs:__imp_GetProcAddress
0x180003f10  mov     rcx, [rbx+0A8h]; hModule
0x180003f17  lea     rdx, aDestroycompres; "DestroyCompression"
0x180003f1e  mov     [rbx+0D0h], rax
0x180003f25  call    cs:__imp_GetProcAddress
0x180003f2b  mov     rcx, [rbx+0B0h]
0x180003f32  mov     [rbx+0D8h], rax
0x180003f39  test    rcx, rcx
0x180003f3c  jz      short loc_180003F90
0x180003f3e  cmp     [rbx+0B8h], rbp
0x180003f45  jz      short loc_180003F90
0x180003f47  cmp     [rbx+0C0h], rbp
0x180003f4e  jz      short loc_180003F90
0x180003f50  cmp     [rbx+0C8h], rbp
0x180003f57  jnz     short loc_180003F62
0x180003f59  cmp     [rbx+0D0h], rbp
0x180003f60  jz      short loc_180003F90
0x180003f62  test    rax, rax
0x180003f65  jz      short loc_180003F90
0x180003f67  mov     rax, rcx
0x180003f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6f  test    eax, eax
0x180003f71  js      short loc_180003F95
0x180003f73  cmp     [rbx+0ECh], ebp
0x180003f79  jz      short loc_180003F81
0x180003f7b  mov     cs:?sm_fDoDynamicCompression@HTTP_COMPRESSION@@2HA, edi; int HTTP_COMPRESSION::sm_fDoDynamicCompression
0x180003f81  xor     eax, eax
0x180003f83  mov     rbx, [rsp+48h+arg_0]
0x180003f88  add     rsp, 30h
0x180003f8c  pop     rdi
0x180003f8d  pop     rsi
0x180003f8e  pop     rbp
0x180003f8f  retn
0x180003f90  mov     eax, 8007007Fh
0x180003f95  mov     rbx, [rsp+48h+arg_0]
0x180003f9a  add     rsp, 30h
0x180003f9e  pop     rdi
0x180003f9f  pop     rsi
0x180003fa0  pop     rbp
0x180003fa1  retn
```
