# DllRegisterServer

- ea: `0x180020c00`
- end: `0x180021065`
- name: `DllRegisterServer`
- size: `1125`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000aef4`
- `0x180011204`
- `0x180014130`
- `0x18001fa9c`
- `0x180020c00`
- `0x18002107c`
- `0x180022d54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020d5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020d7a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020daa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020dc9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020df5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020ea8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020d5b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020d7a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020daa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020dc9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020df5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020e89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180020ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020c31`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020c31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020d10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3c`

## string_xrefs

- `0x180020c27`: `nlhtml.dll`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  HMODULE Library; // rbx
  HINSTANCE MUILibraryW; // rax
  WCHAR *v3; // rsi
  HINSTANCE v4; // rdi
  int v5; // r14d
  int StringW; // ecx
  WCHAR *v7; // rsi
  int v8; // r14d
  int v9; // ecx
  WCHAR *v10; // rsi
  int v11; // r14d
  int v12; // ecx
  WCHAR *v13; // rsi
  int v14; // r14d
  int v15; // ecx
  WCHAR *v16; // rsi
  int v17; // r14d
  int v18; // ecx
  HRESULT v19; // ebx
  __int128 v20; // [rsp+20h] [rbp-E0h] BYREF
  void **v21; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v22; // [rsp+38h] [rbp-C8h]
  int v23[2]; // [rsp+40h] [rbp-C0h]
  __int16 v24; // [rsp+48h] [rbp-B8h] BYREF
  void **v25; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR v26; // [rsp+98h] [rbp-68h]
  int v27[2]; // [rsp+A0h] [rbp-60h]
  __int16 v28; // [rsp+A8h] [rbp-58h] BYREF
  void **v29; // [rsp+F0h] [rbp-10h] BYREF
  LPWSTR v30; // [rsp+F8h] [rbp-8h]
  int v31[2]; // [rsp+100h] [rbp+0h]
  __int16 v32; // [rsp+108h] [rbp+8h] BYREF
  void **v33; // [rsp+150h] [rbp+50h] BYREF
  LPWSTR v34; // [rsp+158h] [rbp+58h]
  int v35[2]; // [rsp+160h] [rbp+60h]
  __int16 v36; // [rsp+168h] [rbp+68h] BYREF
  void **v37; // [rsp+1B0h] [rbp+B0h] BYREF
  LPWSTR lpBuffer; // [rsp+1B8h] [rbp+B8h]
  int cchBufferMax[2]; // [rsp+1C0h] [rbp+C0h]
  __int16 v40; // [rsp+1C8h] [rbp+C8h] BYREF

  if ( GetModuleHandleW(L"nlhtml.dll") )
  {
    *(_QWORD *)cchBufferMax = 33;
    v37 = &TLMString<32,32,1024>::`vftable';
    lpBuffer = (LPWSTR)&v40;
    v21 = &TLMString<32,32,1024>::`vftable';
    v40 = 0;
    v22 = (LPWSTR)&v24;
    v24 = 0;
    v34 = (LPWSTR)&v36;
    v36 = 0;
    v30 = (LPWSTR)&v32;
    v32 = 0;
    v26 = (LPWSTR)&v28;
    v33 = &TLMString<32,32,1024>::`vftable';
    v29 = &TLMString<32,32,1024>::`vftable';
    v25 = &TLMString<32,32,1024>::`vftable';
    v28 = 0;
    *(_QWORD *)v23 = 33;
    *(_QWORD *)v35 = 33;
    *(_QWORD *)v31 = 33;
    *(_QWORD *)v27 = 33;
    v20 = 0;
    CResourceLibrary::FreeLibs((CResourceLibrary *)&v20);
    Library = LoadLibraryExW(L"nlhtml.dll", 0, 2u);
    *(_QWORD *)&v20 = Library;
    MUILibraryW = LoadMUILibraryW(L"nlhtml.dll", 8u, 0);
    v3 = lpBuffer;
    v4 = MUILibraryW;
    v5 = cchBufferMax[0];
    StringW = 0;
    *((_QWORD *)&v20 + 1) = MUILibraryW;
    *lpBuffer = 0;
    if ( !MUILibraryW || (StringW = LoadStringW(MUILibraryW, 1u, v3, v5)) == 0 )
    {
      if ( Library )
        StringW = LoadStringW(Library, 1u, v3, v5);
    }
    v7 = v22;
    v8 = v23[0];
    cchBufferMax[1] = StringW;
    v9 = 0;
    *v22 = 0;
    if ( !v4 || (v9 = LoadStringW(v4, 2u, v7, v8)) == 0 )
    {
      if ( Library )
        v9 = LoadStringW(Library, 2u, v7, v8);
    }
    v10 = v34;
    v11 = v35[0];
    v23[1] = v9;
    v12 = 0;
    *v34 = 0;
    if ( !v4 || (v12 = LoadStringW(v4, 3u, v10, v11)) == 0 )
    {
      if ( Library )
        v12 = LoadStringW(Library, 3u, v10, v11);
    }
    v13 = v30;
    v14 = v31[0];
    v35[1] = v12;
    v15 = 0;
    *v30 = 0;
    if ( !v4 || (v15 = LoadStringW(v4, 4u, v13, v14)) == 0 )
    {
      if ( Library )
        v15 = LoadStringW(Library, 4u, v13, v14);
    }
    v16 = v26;
    v17 = v27[0];
    v31[1] = v15;
    v18 = 0;
    *v26 = 0;
    if ( !v4 || (v18 = LoadStringW(v4, 5u, v16, v17)) == 0 )
    {
      if ( Library )
        v18 = LoadStringW(Library, 5u, v16, v17);
    }
    v27[1] = v18;
    off_180039080[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039070 = (__int64 (*)[2])off_180039080[0];
    off_1800390A8[0] = CLMString::GetBuffer((CLMString *)&v37, 0);
    off_180039098 = (__int64 (*)[2])off_1800390A8[0];
    off_1800390D0[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_1800390C0 = (__int64 (*)[2])off_1800390D0[0];
    off_1800390F8[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_1800390E8 = (__int64 (*)[2])off_1800390F8[0];
    off_180039120[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039110 = (__int64 (*)[2])off_180039120[0];
    off_180039148[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039138 = (__int64 (*)[2])off_180039148[0];
    off_180039170[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039160 = (__int64 (*)[2])off_180039170[0];
    off_180039198[0] = CLMString::GetBuffer((CLMString *)&v33, 0);
    off_180039188 = (__int64 (*)[2])off_180039198[0];
    off_1800391C0[0] = CLMString::GetBuffer((CLMString *)&v29, 0);
    off_1800391B0 = (__int64 (*)[2])off_1800391C0[0];
    off_1800391E8[0] = CLMString::GetBuffer((CLMString *)&v25, 0);
    off_1800391D8 = (__int64 (*)[2])off_1800391E8[0];
    off_180039210[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039200 = (__int64 (*)[2])off_180039210[0];
    off_180039238[0] = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039228 = (__int64 (*)[2])off_180039238[0];
    off_180039260 = CLMString::GetBuffer((CLMString *)&v21, 0);
    off_180039250 = (__int64 (*)[2])off_180039260;
    v19 = HTMLRegisterServer();
    CResourceLibrary::FreeLibs((CResourceLibrary *)&v20);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v25);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v29);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v33);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v21);
    TLMString<32,32,1024>::~TLMString<32,32,1024>(&v37);
    return v19;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180020c00  push    rbp
0x180020c02  push    rbx
0x180020c03  push    rsi
0x180020c04  push    rdi
0x180020c05  push    r14
0x180020c07  lea     rbp, [rsp-120h]
0x180020c0f  sub     rsp, 220h
0x180020c16  mov     rax, cs:__security_cookie
0x180020c1d  xor     rax, rsp
0x180020c20  mov     [rbp+140h+var_30], rax
0x180020c27  lea     rdi, FileName; "nlhtml.dll"
0x180020c2e  mov     rcx, rdi; lpModuleName
0x180020c31  call    cs:__imp_GetModuleHandleW
0x180020c37  test    rax, rax
0x180020c3a  jnz     short loc_180020C57
0x180020c3c  call    cs:__imp_GetLastError
0x180020c42  test    eax, eax
0x180020c44  jle     loc_180021048
0x180020c4a  movzx   eax, ax
0x180020c4d  or      eax, 80070000h
0x180020c52  jmp     loc_180021048
0x180020c57  lea     rcx, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x180020c5e  mov     qword ptr [rbp+140h+cchBufferMax], 21h ; '!'
0x180020c69  lea     rax, [rbp+140h+var_78]
0x180020c70  mov     [rbp+140h+var_90], rcx
0x180020c77  mov     [rbp+140h+lpBuffer], rax
0x180020c7e  xorps   xmm0, xmm0
0x180020c81  xor     eax, eax
0x180020c83  mov     [rsp+240h+var_210], rcx
0x180020c88  mov     [rbp+140h+var_78], ax
0x180020c8f  lea     rax, [rsp+240h+var_1F8]
0x180020c94  mov     [rsp+240h+var_208], rax
0x180020c99  xor     eax, eax
0x180020c9b  mov     [rsp+240h+var_1F8], ax
0x180020ca0  lea     rax, [rbp+140h+var_D8]
0x180020ca4  mov     [rbp+140h+var_E8], rax
0x180020ca8  xor     eax, eax
0x180020caa  mov     [rbp+140h+var_D8], ax
0x180020cae  lea     rax, [rbp+140h+var_138]
0x180020cb2  mov     [rbp+140h+var_148], rax
0x180020cb6  xor     eax, eax
0x180020cb8  mov     [rbp+140h+var_138], ax
0x180020cbc  lea     rax, [rbp+140h+var_198]
0x180020cc0  mov     [rbp+140h+var_1A8], rax
0x180020cc4  xor     eax, eax
0x180020cc6  mov     [rbp+140h+var_F0], rcx
0x180020cca  mov     [rbp+140h+var_150], rcx
0x180020cce  mov     [rbp+140h+var_1B0], rcx
0x180020cd2  lea     rcx, [rsp+240h+var_220]; this
0x180020cd7  mov     [rbp+140h+var_198], ax
0x180020cdb  mov     qword ptr [rsp+240h+var_200], 21h ; '!'
0x180020ce4  mov     qword ptr [rbp+140h+var_E0], 21h ; '!'
0x180020cec  mov     qword ptr [rbp+140h+var_140], 21h ; '!'
0x180020cf4  mov     qword ptr [rbp+140h+var_1A0], 21h ; '!'
0x180020cfc  movdqu  [rsp+240h+var_220], xmm0
0x180020d02  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x180020d07  xor     edx, edx; hFile
0x180020d09  mov     rcx, rdi; lpLibFileName
0x180020d0c  lea     r8d, [rdx+2]; dwFlags
0x180020d10  call    cs:__imp_LoadLibraryExW
0x180020d16  xor     r8d, r8d; LangID
0x180020d19  mov     rcx, rdi; pszFullModuleName
0x180020d1c  mov     rbx, rax
0x180020d1f  mov     qword ptr [rsp+240h+var_220], rax
0x180020d24  lea     edx, [r8+8]; dwLangConvention
0x180020d28  call    LoadMUILibraryW
0x180020d2d  mov     rsi, [rbp+140h+lpBuffer]
0x180020d34  mov     rdi, rax
0x180020d37  mov     r14d, [rbp+140h+cchBufferMax]
0x180020d3e  xor     ecx, ecx
0x180020d40  mov     qword ptr [rsp+240h+var_220+8], rax
0x180020d45  xor     eax, eax
0x180020d47  mov     [rsi], ax
0x180020d4a  test    rdi, rdi
0x180020d4d  jz      short loc_180020D67
0x180020d4f  lea     edx, [rcx+1]; uID
0x180020d52  mov     r9d, r14d; cchBufferMax
0x180020d55  mov     rcx, rdi; hInstance
0x180020d58  mov     r8, rsi; lpBuffer
0x180020d5b  call    cs:__imp_LoadStringW
0x180020d61  mov     ecx, eax
0x180020d63  test    eax, eax
0x180020d65  jnz     short loc_180020D82
0x180020d67  test    rbx, rbx
0x180020d6a  jz      short loc_180020D82
0x180020d6c  mov     r9d, r14d; cchBufferMax
0x180020d6f  mov     r8, rsi; lpBuffer
0x180020d72  mov     edx, 1; uID
0x180020d77  mov     rcx, rbx; hInstance
0x180020d7a  call    cs:__imp_LoadStringW
0x180020d80  mov     ecx, eax
0x180020d82  mov     rsi, [rsp+240h+var_208]
0x180020d87  xor     eax, eax
0x180020d89  mov     r14d, [rsp+240h+var_200]
0x180020d8e  mov     [rbp+140h+cchBufferMax+4], ecx
0x180020d94  xor     ecx, ecx
0x180020d96  mov     [rsi], ax
0x180020d99  test    rdi, rdi
0x180020d9c  jz      short loc_180020DB6
0x180020d9e  lea     edx, [rcx+2]; uID
0x180020da1  mov     r9d, r14d; cchBufferMax
0x180020da4  mov     rcx, rdi; hInstance
0x180020da7  mov     r8, rsi; lpBuffer
0x180020daa  call    cs:__imp_LoadStringW
0x180020db0  mov     ecx, eax
0x180020db2  test    eax, eax
0x180020db4  jnz     short loc_180020DD1
0x180020db6  test    rbx, rbx
0x180020db9  jz      short loc_180020DD1
0x180020dbb  mov     r9d, r14d; cchBufferMax
0x180020dbe  mov     r8, rsi; lpBuffer
0x180020dc1  mov     edx, 2; uID
0x180020dc6  mov     rcx, rbx; hInstance
0x180020dc9  call    cs:__imp_LoadStringW
0x180020dcf  mov     ecx, eax
0x180020dd1  mov     rsi, [rbp+140h+var_E8]
0x180020dd5  xor     eax, eax
0x180020dd7  mov     r14d, [rbp+140h+var_E0]
0x180020ddb  mov     [rsp+240h+var_200+4], ecx
0x180020ddf  xor     ecx, ecx
0x180020de1  mov     [rsi], ax
0x180020de4  test    rdi, rdi
0x180020de7  jz      short loc_180020E01
0x180020de9  lea     edx, [rcx+3]; uID
0x180020dec  mov     r9d, r14d; cchBufferMax
0x180020def  mov     rcx, rdi; hInstance
0x180020df2  mov     r8, rsi; lpBuffer
0x180020df5  call    cs:__imp_LoadStringW
0x180020dfb  mov     ecx, eax
0x180020dfd  test    eax, eax
0x180020dff  jnz     short loc_180020E1C
0x180020e01  test    rbx, rbx
0x180020e04  jz      short loc_180020E1C
0x180020e06  mov     r9d, r14d; cchBufferMax
0x180020e09  mov     r8, rsi; lpBuffer
0x180020e0c  mov     edx, 3; uID
0x180020e11  mov     rcx, rbx; hInstance
0x180020e14  call    cs:__imp_LoadStringW
0x180020e1a  mov     ecx, eax
0x180020e1c  mov     rsi, [rbp+140h+var_148]
0x180020e20  xor     eax, eax
0x180020e22  mov     r14d, [rbp+140h+var_140]
0x180020e26  mov     [rbp+140h+var_E0+4], ecx
0x180020e29  xor     ecx, ecx
0x180020e2b  mov     [rsi], ax
0x180020e2e  test    rdi, rdi
0x180020e31  jz      short loc_180020E4B
0x180020e33  lea     edx, [rcx+4]; uID
0x180020e36  mov     r9d, r14d; cchBufferMax
0x180020e39  mov     rcx, rdi; hInstance
0x180020e3c  mov     r8, rsi; lpBuffer
0x180020e3f  call    cs:__imp_LoadStringW
0x180020e45  mov     ecx, eax
0x180020e47  test    eax, eax
0x180020e49  jnz     short loc_180020E66
0x180020e4b  test    rbx, rbx
0x180020e4e  jz      short loc_180020E66
0x180020e50  mov     r9d, r14d; cchBufferMax
0x180020e53  mov     r8, rsi; lpBuffer
0x180020e56  mov     edx, 4; uID
0x180020e5b  mov     rcx, rbx; hInstance
0x180020e5e  call    cs:__imp_LoadStringW
0x180020e64  mov     ecx, eax
0x180020e66  mov     rsi, [rbp+140h+var_1A8]
0x180020e6a  xor     eax, eax
0x180020e6c  mov     r14d, [rbp+140h+var_1A0]
0x180020e70  mov     [rbp+140h+var_140+4], ecx
0x180020e73  xor     ecx, ecx
0x180020e75  mov     [rsi], ax
0x180020e78  test    rdi, rdi
0x180020e7b  jz      short loc_180020E95
0x180020e7d  lea     edx, [rcx+5]; uID
0x180020e80  mov     r9d, r14d; cchBufferMax
0x180020e83  mov     rcx, rdi; hInstance
0x180020e86  mov     r8, rsi; lpBuffer
0x180020e89  call    cs:__imp_LoadStringW
0x180020e8f  mov     ecx, eax
0x180020e91  test    eax, eax
0x180020e93  jnz     short loc_180020EB0
0x180020e95  test    rbx, rbx
0x180020e98  jz      short loc_180020EB0
0x180020e9a  mov     r9d, r14d; cchBufferMax
0x180020e9d  mov     r8, rsi; lpBuffer
0x180020ea0  mov     edx, 5; uID
0x180020ea5  mov     rcx, rbx; hInstance
0x180020ea8  call    cs:__imp_LoadStringW
0x180020eae  mov     ecx, eax
0x180020eb0  mov     [rbp+140h+var_1A0+4], ecx
0x180020eb3  xor     edx, edx; int
0x180020eb5  lea     rcx, [rsp+240h+var_210]; this
0x180020eba  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020ebf  xor     edx, edx; int
0x180020ec1  mov     cs:off_180039080, rax; "ODC file"
0x180020ec8  lea     rcx, [rbp+140h+var_90]; this
0x180020ecf  mov     cs:off_180039070, rax
0x180020ed6  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020edb  xor     edx, edx; int
0x180020edd  mov     cs:off_1800390A8, rax; "HHC file"
0x180020ee4  lea     rcx, [rsp+240h+var_210]; this
0x180020ee9  mov     cs:off_180039098, rax
0x180020ef0  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020ef5  xor     edx, edx; int
0x180020ef7  mov     cs:off_1800390D0, rax; "HTML file"
0x180020efe  lea     rcx, [rsp+240h+var_210]; this
0x180020f03  mov     cs:off_1800390C0, rax
0x180020f0a  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f0f  xor     edx, edx; int
0x180020f11  mov     cs:off_1800390F8, rax; "HTML file"
0x180020f18  lea     rcx, [rsp+240h+var_210]; this
0x180020f1d  mov     cs:off_1800390E8, rax
0x180020f24  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f29  xor     edx, edx; int
0x180020f2b  mov     cs:off_180039120, rax; "HTML file"
0x180020f32  lea     rcx, [rsp+240h+var_210]; this
0x180020f37  mov     cs:off_180039110, rax
0x180020f3e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f43  xor     edx, edx; int
0x180020f45  mov     cs:off_180039148, rax; "HTML file"
0x180020f4c  lea     rcx, [rsp+240h+var_210]; this
0x180020f51  mov     cs:off_180039138, rax
0x180020f58  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f5d  xor     edx, edx; int
0x180020f5f  mov     cs:off_180039170, rax; "HTML file"
0x180020f66  lea     rcx, [rbp+140h+var_F0]; this
0x180020f6a  mov     cs:off_180039160, rax
0x180020f71  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f76  xor     edx, edx; int
0x180020f78  mov     cs:off_180039198, rax; "ASP auto file"
0x180020f7f  lea     rcx, [rbp+140h+var_150]; this
0x180020f83  mov     cs:off_180039188, rax
0x180020f8a  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020f8f  xor     edx, edx; int
0x180020f91  mov     cs:off_1800391C0, rax; "Active Server Page Plus"
0x180020f98  lea     rcx, [rbp+140h+var_1B0]; this
0x180020f9c  mov     cs:off_1800391B0, rax
0x180020fa3  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020fa8  xor     edx, edx; int
0x180020faa  mov     cs:off_1800391E8, rax; "ASP.NET User Controls"
0x180020fb1  lea     rcx, [rsp+240h+var_210]; this
0x180020fb6  mov     cs:off_1800391D8, rax
0x180020fbd  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020fc2  xor     edx, edx; int
0x180020fc4  mov     cs:off_180039210, rax; "HTML file"
0x180020fcb  lea     rcx, [rsp+240h+var_210]; this
0x180020fd0  mov     cs:off_180039200, rax
0x180020fd7  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020fdc  xor     edx, edx; int
0x180020fde  mov     cs:off_180039238, rax; "HTML file"
0x180020fe5  lea     rcx, [rsp+240h+var_210]; this
0x180020fea  mov     cs:off_180039228, rax
0x180020ff1  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180020ff6  mov     cs:off_180039260, rax; "HTML file"
0x180020ffd  mov     cs:off_180039250, rax
0x180021004  call    HTMLRegisterServer
0x180021009  lea     rcx, [rsp+240h+var_220]; this
0x18002100e  mov     ebx, eax
0x180021010  call    ?FreeLibs@CResourceLibrary@@AEAAXXZ; CResourceLibrary::FreeLibs(void)
0x180021015  lea     rcx, [rbp+140h+var_1B0]
0x180021019  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18002101e  lea     rcx, [rbp+140h+var_150]
0x180021022  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x180021027  lea     rcx, [rbp+140h+var_F0]
0x18002102b  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x180021030  lea     rcx, [rsp+240h+var_210]
0x180021035  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18002103a  lea     rcx, [rbp+140h+var_90]
0x180021041  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x180021046  mov     eax, ebx
0x180021048  mov     rcx, [rbp+140h+var_30]
0x18002104f  xor     rcx, rsp; StackCookie
0x180021052  call    __security_check_cookie
0x180021057  add     rsp, 220h
0x18002105e  pop     r14
0x180021060  pop     rdi
0x180021061  pop     rsi
0x180021062  pop     rbx
0x180021063  pop     rbp
0x180021064  retn
```
