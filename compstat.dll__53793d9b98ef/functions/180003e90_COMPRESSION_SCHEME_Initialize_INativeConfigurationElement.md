# COMPRESSION_SCHEME::Initialize(INativeConfigurationElement *)

- ea: `0x180003e90`
- end: `0x180004172`
- name: `?Initialize@COMPRESSION_SCHEME@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `738`
- prototype: `__int64 __fastcall(COMPRESSION_SCHEME *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002e00`

## callees

- `0x180003e90`
- `0x180009010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003ff1`
- `msvcrt!_wcsicmp` at `0x180004014`
- `msvcrt!_wcsicmp` at `0x180003ff1`
- `msvcrt!_wcsicmp` at `0x180004014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004041`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003ef8`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180003ef8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ee1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000406e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004089`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000406e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004089`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800040f5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000402f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000402f`

## string_xrefs

- `0x180003f70`: `doStaticCompression`
- `0x180003f43`: `doDynamicCompression`
- `0x180003f9d`: `dynamicCompressionLevel`
- `0x180003fca`: `staticCompressionLevel`
- `0x180004064`: `InitCompression`
- `0x18000407b`: `DeInitCompression`
- `0x180004096`: `CreateCompression`
- `0x1800040b1`: `Compress`
- `0x1800040cc`: `Compress2`
- `0x1800040e7`: `DestroyCompression`

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
                        if ( *((_DWORD *)this + 60) )
                          HTTP_COMPRESSION::sm_fDoStaticCompression = 1;
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
0x180003e90  mov     [rsp+arg_0], rbx
0x180003e95  push    rbp
0x180003e96  push    rsi
0x180003e97  push    rdi
0x180003e98  sub     rsp, 30h
0x180003e9c  mov     rax, [rdx]
0x180003e9f  lea     r8, [rsp+48h+String1]
0x180003ea4  mov     rdi, rdx
0x180003ea7  xor     ebp, ebp
0x180003ea9  mov     rbx, rcx
0x180003eac  mov     [rsp+48h+String1], rbp
0x180003eb1  xor     r9d, r9d
0x180003eb4  mov     [rsp+48h+lpLibFileName], rbp
0x180003eb9  mov     rax, [rax+40h]
0x180003ebd  lea     rdx, aName; "name"
0x180003ec4  mov     rcx, rdi
0x180003ec7  mov     [rsp+48h+var_28], rbp
0x180003ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ed1  test    eax, eax
0x180003ed3  js      loc_180004165
0x180003ed9  mov     rdx, [rsp+48h+String1]
0x180003ede  mov     rcx, rbx
0x180003ee1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003ee7  test    eax, eax
0x180003ee9  js      loc_180004165
0x180003eef  mov     rdx, [rsp+48h+String1]
0x180003ef4  lea     rcx, [rbx+38h]
0x180003ef8  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180003efe  test    eax, eax
0x180003f00  js      loc_180004165
0x180003f06  mov     rax, [rdi]
0x180003f09  lea     r8, [rsp+48h+lpLibFileName]
0x180003f0e  xor     r9d, r9d
0x180003f11  mov     [rsp+48h+var_28], rbp
0x180003f16  lea     rdx, aDll; "dll"
0x180003f1d  mov     rcx, rdi
0x180003f20  mov     rax, [rax+40h]
0x180003f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f29  test    eax, eax
0x180003f2b  js      loc_180004165
0x180003f31  mov     rax, [rdi]
0x180003f34  lea     r8, [rbx+0ECh]
0x180003f3b  xor     r9d, r9d
0x180003f3e  mov     [rsp+48h+var_28], rbp
0x180003f43  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x180003f4a  mov     rcx, rdi
0x180003f4d  mov     rax, [rax+48h]
0x180003f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f56  test    eax, eax
0x180003f58  js      loc_180004165
0x180003f5e  mov     rax, [rdi]
0x180003f61  lea     r8, [rbx+0F0h]
0x180003f68  xor     r9d, r9d
0x180003f6b  mov     [rsp+48h+var_28], rbp
0x180003f70  lea     rdx, aDostaticcompre; "doStaticCompression"
0x180003f77  mov     rcx, rdi
0x180003f7a  mov     rax, [rax+48h]
0x180003f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f83  test    eax, eax
0x180003f85  js      loc_180004165
0x180003f8b  mov     rax, [rdi]
0x180003f8e  lea     r8, [rbx+0E0h]
0x180003f95  xor     r9d, r9d
0x180003f98  mov     [rsp+48h+var_28], rbp
0x180003f9d  lea     rdx, aDynamiccompres_1; "dynamicCompressionLevel"
0x180003fa4  mov     rcx, rdi
0x180003fa7  mov     rax, [rax+30h]
0x180003fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb0  test    eax, eax
0x180003fb2  js      loc_180004165
0x180003fb8  mov     rax, [rdi]
0x180003fbb  lea     r8, [rbx+0E4h]
0x180003fc2  xor     r9d, r9d
0x180003fc5  mov     [rsp+48h+var_28], rbp
0x180003fca  lea     rdx, aStaticcompress; "staticCompressionLevel"
0x180003fd1  mov     rcx, rdi
0x180003fd4  mov     rax, [rax+30h]
0x180003fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fdd  test    eax, eax
0x180003fdf  js      loc_180004165
0x180003fe5  mov     rcx, [rsp+48h+String1]; String1
0x180003fea  lea     rdx, aDeflate; "deflate"
0x180003ff1  call    cs:__imp__wcsicmp
0x180003ff7  mov     edi, 1
0x180003ffc  test    eax, eax
0x180003ffe  jnz     short loc_180004008
0x180004000  mov     [rbx+0E8h], ebp
0x180004006  jmp     short loc_18000402A
0x180004008  mov     rcx, [rsp+48h+String1]; String1
0x18000400d  lea     rdx, aGzip; "gzip"
0x180004014  call    cs:__imp__wcsicmp
0x18000401a  test    eax, eax
0x18000401c  mov     ecx, 0FFFFFFFFh
0x180004021  cmovz   ecx, edi
0x180004024  mov     [rbx+0E8h], ecx
0x18000402a  mov     rcx, [rsp+48h+lpLibFileName]; lpLibFileName
0x18000402f  call    cs:__imp_LoadLibraryW
0x180004035  mov     [rbx+0A8h], rax
0x18000403c  test    rax, rax
0x18000403f  jnz     short loc_180004064
0x180004041  call    cs:__imp_GetLastError
0x180004047  test    eax, eax
0x180004049  jle     loc_180004165
0x18000404f  movzx   eax, ax
0x180004052  or      eax, 80070000h
0x180004057  mov     rbx, [rsp+48h+arg_0]
0x18000405c  add     rsp, 30h
0x180004060  pop     rdi
0x180004061  pop     rsi
0x180004062  pop     rbp
0x180004063  retn
0x180004064  lea     rdx, ProcName; "InitCompression"
0x18000406b  mov     rcx, rax; hModule
0x18000406e  call    cs:__imp_GetProcAddress
0x180004074  mov     rcx, [rbx+0A8h]; hModule
0x18000407b  lea     rdx, aDeinitcompress; "DeInitCompression"
0x180004082  mov     [rbx+0B0h], rax
0x180004089  call    cs:__imp_GetProcAddress
0x18000408f  mov     rcx, [rbx+0A8h]; hModule
0x180004096  lea     rdx, aCreatecompress; "CreateCompression"
0x18000409d  mov     [rbx+0B8h], rax
0x1800040a4  call    cs:__imp_GetProcAddress
0x1800040aa  mov     rcx, [rbx+0A8h]; hModule
0x1800040b1  lea     rdx, aCompress; "Compress"
0x1800040b8  mov     [rbx+0C0h], rax
0x1800040bf  call    cs:__imp_GetProcAddress
0x1800040c5  mov     rcx, [rbx+0A8h]; hModule
0x1800040cc  lea     rdx, aCompress2; "Compress2"
0x1800040d3  mov     [rbx+0C8h], rax
0x1800040da  call    cs:__imp_GetProcAddress
0x1800040e0  mov     rcx, [rbx+0A8h]; hModule
0x1800040e7  lea     rdx, aDestroycompres; "DestroyCompression"
0x1800040ee  mov     [rbx+0D0h], rax
0x1800040f5  call    cs:__imp_GetProcAddress
0x1800040fb  mov     rcx, [rbx+0B0h]
0x180004102  mov     [rbx+0D8h], rax
0x180004109  test    rcx, rcx
0x18000410c  jz      short loc_180004160
0x18000410e  cmp     [rbx+0B8h], rbp
0x180004115  jz      short loc_180004160
0x180004117  cmp     [rbx+0C0h], rbp
0x18000411e  jz      short loc_180004160
0x180004120  cmp     [rbx+0C8h], rbp
0x180004127  jnz     short loc_180004132
0x180004129  cmp     [rbx+0D0h], rbp
0x180004130  jz      short loc_180004160
0x180004132  test    rax, rax
0x180004135  jz      short loc_180004160
0x180004137  mov     rax, rcx
0x18000413a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413f  test    eax, eax
0x180004141  js      short loc_180004165
0x180004143  cmp     [rbx+0F0h], ebp
0x180004149  jz      short loc_180004151
0x18000414b  mov     cs:?sm_fDoStaticCompression@HTTP_COMPRESSION@@2HA, edi; int HTTP_COMPRESSION::sm_fDoStaticCompression
0x180004151  xor     eax, eax
0x180004153  mov     rbx, [rsp+48h+arg_0]
0x180004158  add     rsp, 30h
0x18000415c  pop     rdi
0x18000415d  pop     rsi
0x18000415e  pop     rbp
0x18000415f  retn
0x180004160  mov     eax, 8007007Fh
0x180004165  mov     rbx, [rsp+48h+arg_0]
0x18000416a  add     rsp, 30h
0x18000416e  pop     rdi
0x18000416f  pop     rsi
0x180004170  pop     rbp
0x180004171  retn
```
