# Helpers::IsV2PreSP2Helper(void)

- ea: `0x18002c124`
- end: `0x18002c49b`
- name: `?IsV2PreSP2Helper@Helpers@@CA_NXZ`
- size: `887`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180023bcc`

## callees

- `0x180001e8c`
- `0x180001f48`
- `0x1800020f0`
- `0x18002c124`
- `0x180030c50`
- `0x180030d84`
- `0x180032ef4`
- `0x18003303c`
- `0x18003dc30`
- `0x18003f110`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002c28a`
- `KERNEL32!LoadLibraryExW` at `0x18002c336`
- `KERNEL32!LoadLibraryExW` at `0x18002c3b4`
- `KERNEL32!LoadLibraryExW` at `0x18002c28a`
- `KERNEL32!LoadLibraryExW` at `0x18002c336`
- `KERNEL32!LoadLibraryExW` at `0x18002c3b4`
- `KERNEL32!GetProcAddress` at `0x18002c29f`
- `KERNEL32!GetProcAddress` at `0x18002c34b`
- `KERNEL32!GetProcAddress` at `0x18002c3c9`
- `KERNEL32!GetProcAddress` at `0x18002c29f`
- `KERNEL32!GetProcAddress` at `0x18002c34b`
- `KERNEL32!GetProcAddress` at `0x18002c3c9`
- `KERNEL32!HeapFree` at `0x18002c462`
- `KERNEL32!HeapFree` at `0x18002c462`
- `KERNEL32!GetProcessHeap` at `0x18002c44d`
- `KERNEL32!GetProcessHeap` at `0x18002c44d`

## string_xrefs

- `0x18002c283`: `version.dll`
- `0x18002c32f`: `version.dll`
- `0x18002c3ad`: `version.dll`
- `0x18002c244`: `v2.0.50727\mscorwks.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
bool Helpers::IsV2PreSP2Helper(void)
{
  LPVOID v0; // rbx
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  unsigned int v3; // eax
  unsigned __int64 v4; // rbx
  __int64 v5; // rax
  void *v6; // rsp
  LPVOID v7; // rsi
  unsigned int v8; // r14d
  FARPROC v9; // rax
  HMODULE v10; // rax
  FARPROC v11; // rax
  HMODULE v12; // rax
  int v13; // ecx
  bool v14; // bl
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v18; // [rsp+30h] [rbp+0h] BYREF
  int v19; // [rsp+34h] [rbp+4h] BYREF
  char *v20; // [rsp+38h] [rbp+8h] BYREF
  int v21; // [rsp+40h] [rbp+10h]
  __int64 v22; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v23; // [rsp+60h] [rbp+30h] BYREF
  __int64 v24; // [rsp+64h] [rbp+34h]
  LPVOID lpMem; // [rsp+70h] [rbp+40h]
  __int16 v26; // [rsp+78h] [rbp+48h] BYREF

  v24 = 512;
  lpMem = &v26;
  v23 = 2;
  v26 = 0;
  Helpers::GetVersionDirectoryPathFromCurrentModulePath((struct SString *)&v23);
  if ( (~(HIDWORD(v24) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v23) )
    SString::ConvertToUnicode((SString *)&v23);
  if ( (v24 & 0x1000000000LL) != 0 )
    SBuffer::ReallocateBuffer(&v23, (unsigned int)v24, 1);
  if ( (v24 & 0x200000000LL) != 0
    && ((BYTE4(v24) & 7) != 7 || SString::s_IsANSIMultibyte)
    && !(unsigned int)SString::ScanASCII((SString *)&v23) )
  {
    SString::ConvertToUnicode((SString *)&v23);
  }
  v20 = (char *)lpMem + (int)(((v23 >> ((v24 & 0x100000000LL) == 0)) - 1) << ((v24 & 0x100000000LL) == 0));
  v21 = (v24 & 0x100000000LL) == 0;
  SString::FindBack((SString *)&v23, (struct SString::CIterator *)&v20, L"\\");
  v20 += 1 << v21;
  SString::Truncate((SString *)&v23, (const struct SString::Iterator *)&v20);
  SString::Append((SString *)&v23, L"v2.0.50727\\mscorwks.dll");
  v18 = 0;
  SString::ConvertToUnicode((SString *)&v23);
  v0 = lpMem;
  ProcAddress = (FARPROC)qword_18006FFD0;
  if ( !qword_18006FFD0 )
  {
    if ( bGetFileVersionInfoSizeWProbed )
      goto LABEL_37;
    Library = LoadLibraryExW(L"version.dll", 0, 0);
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetFileVersionInfoSizeW");
      qword_18006FFD0 = (__int64)ProcAddress;
    }
    else
    {
      ProcAddress = (FARPROC)qword_18006FFD0;
    }
    bGetFileVersionInfoSizeWProbed = 1;
    if ( !ProcAddress )
      goto LABEL_37;
  }
  v3 = ((__int64 (__fastcall *)(LPVOID, unsigned int *))ProcAddress)(v0, &v18);
  v4 = v3;
  if ( !v3 )
    goto LABEL_37;
  v5 = v3 + 15LL;
  if ( v4 + 15 < v4 )
    v5 = 0xFFFFFFFFFFFFFF0LL;
  v6 = alloca(v5 & 0xFFFFFFFFFFFFFFF0uLL);
  SString::ConvertToUnicode((SString *)&v23);
  v7 = lpMem;
  v8 = v18;
  v9 = (FARPROC)qword_18006FFC8;
  if ( !qword_18006FFC8 )
  {
    if ( bGetFileVersionInfoWProbed )
      goto LABEL_37;
    v10 = LoadLibraryExW(L"version.dll", 0, 0);
    if ( v10 )
    {
      v9 = GetProcAddress(v10, "GetFileVersionInfoW");
      qword_18006FFC8 = (__int64)v9;
    }
    else
    {
      v9 = (FARPROC)qword_18006FFC8;
    }
    bGetFileVersionInfoWProbed = 1;
    if ( !v9 )
      goto LABEL_37;
  }
  if ( ((unsigned int (__fastcall *)(LPVOID, _QWORD, _QWORD, unsigned int *))v9)(v7, v8, (unsigned int)v4, &v18)
    && ((v19 = 0, (v11 = (FARPROC)qword_18006FFD8) != 0)
     || !bVerQueryValueWProbed
     && ((v12 = LoadLibraryExW(L"version.dll", 0, 0)) == 0
       ? (v11 = (FARPROC)qword_18006FFD8)
       : (FARPROC)(v11 = GetProcAddress(v12, "VerQueryValueW"), qword_18006FFD8 = (__int64)v11),
         bVerQueryValueWProbed = 1,
         v11))
    && ((unsigned int (__fastcall *)(unsigned int *, const wchar_t *, __int64 *, int *))v11)(&v18, L"\\", &v22, &v19)
    && *(_DWORD *)(v22 + 8) == 0x20000
    && (v13 = *(_DWORD *)(v22 + 12), (v13 & 0xFFFF0000) == 0xC6270000) )
  {
    v14 = (unsigned __int16)v13 < 0xBEDu;
  }
  else
  {
LABEL_37:
    v14 = 0;
  }
  if ( (v24 & 0x800000000LL) != 0 )
  {
    v15 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v15);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18002c124  push    rbp
0x18002c126  push    r14
0x18002c128  push    r15
0x18002c12a  sub     rsp, 290h
0x18002c131  lea     rbp, [rsp+30h]
0x18002c136  mov     [rbp+270h+arg_0], rbx
0x18002c13d  mov     [rbp+270h+arg_8], rsi
0x18002c144  mov     [rbp+270h+arg_10], rdi
0x18002c14b  mov     rax, cs:__security_cookie
0x18002c152  xor     rax, rbp
0x18002c155  mov     [rbp+270h+var_20], rax
0x18002c15c  xor     r15d, r15d
0x18002c15f  mov     [rbp+270h+var_240], r15
0x18002c163  mov     [rbp+270h+var_240+4], 200h
0x18002c16b  mov     [rbp+270h+lpMem], r15
0x18002c16f  lea     rax, [rbp+270h+var_228]
0x18002c173  mov     [rbp+270h+lpMem], rax
0x18002c177  mov     dword ptr [rbp+270h+var_240], 2
0x18002c17e  mov     rax, [rbp+270h+lpMem]
0x18002c182  mov     [rax], r15w
0x18002c186  lea     rcx, [rbp+270h+var_240]; this
0x18002c18a  call    ?GetVersionDirectoryPathFromCurrentModulePath@Helpers@@SAXAEAVSString@@@Z; Helpers::GetVersionDirectoryPathFromCurrentModulePath(SString &)
0x18002c18f  mov     eax, [rbp+270h+var_238]
0x18002c192  shr     eax, 1
0x18002c194  not     eax
0x18002c196  test    al, 1
0x18002c198  jnz     short loc_18002C1B0
0x18002c19a  lea     rcx, [rbp+270h+var_240]; this
0x18002c19e  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18002c1a3  test    eax, eax
0x18002c1a5  jnz     short loc_18002C1B0
0x18002c1a7  lea     rcx, [rbp+270h+var_240]; this
0x18002c1ab  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002c1b0  test    byte ptr [rbp+270h+var_238], 10h
0x18002c1b4  jz      short loc_18002C1C8
0x18002c1b6  mov     r8d, 1
0x18002c1bc  mov     edx, dword ptr [rbp+270h+var_240+4]
0x18002c1bf  lea     rcx, [rbp+270h+var_240]
0x18002c1c3  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x18002c1c8  mov     eax, [rbp+270h+var_238]
0x18002c1cb  test    al, 2
0x18002c1cd  jz      short loc_18002C1F5
0x18002c1cf  and     eax, 7
0x18002c1d2  cmp     al, 7
0x18002c1d4  jnz     short loc_18002C1DF
0x18002c1d6  cmp     cs:?s_IsANSIMultibyte@SString@@0HA, r15d; int SString::s_IsANSIMultibyte
0x18002c1dd  jz      short loc_18002C1F5
0x18002c1df  lea     rcx, [rbp+270h+var_240]; this
0x18002c1e3  call    ?ScanASCII@SString@@AEBAHXZ; SString::ScanASCII(void)
0x18002c1e8  test    eax, eax
0x18002c1ea  jnz     short loc_18002C1F5
0x18002c1ec  lea     rcx, [rbp+270h+var_240]; this
0x18002c1f0  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002c1f5  mov     ecx, [rbp+270h+var_238]
0x18002c1f8  not     ecx
0x18002c1fa  and     ecx, 1
0x18002c1fd  mov     eax, dword ptr [rbp+270h+var_240]
0x18002c200  shr     eax, cl
0x18002c202  dec     eax
0x18002c204  shl     eax, cl
0x18002c206  cdqe
0x18002c208  add     rax, [rbp+270h+lpMem]
0x18002c20c  mov     [rbp+270h+var_268], rax
0x18002c210  mov     [rbp+270h+var_260], ecx
0x18002c213  lea     r8, asc_180049544; "\\"
0x18002c21a  lea     rdx, [rbp+270h+var_268]; struct SString::CIterator *
0x18002c21e  lea     rcx, [rbp+270h+var_240]; this
0x18002c222  call    ?FindBack@SString@@QEBAHAEAVCIterator@1@PEBG@Z; SString::FindBack(SString::CIterator &,ushort const *)
0x18002c227  mov     ecx, [rbp+270h+var_260]
0x18002c22a  mov     eax, 1
0x18002c22f  shl     eax, cl
0x18002c231  cdqe
0x18002c233  add     [rbp+270h+var_268], rax
0x18002c237  lea     rdx, [rbp+270h+var_268]; struct SString::Iterator *
0x18002c23b  lea     rcx, [rbp+270h+var_240]; this
0x18002c23f  call    ?Truncate@SString@@QEAAXAEBVIterator@1@@Z; SString::Truncate(SString::Iterator const &)
0x18002c244  lea     rdx, aV2050727Mscorw; "v2.0.50727\\mscorwks.dll"
0x18002c24b  lea     rcx, [rbp+270h+var_240]; this
0x18002c24f  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18002c254  mov     [rbp+270h+var_270], r15d
0x18002c258  lea     rcx, [rbp+270h+var_240]; this
0x18002c25c  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002c261  mov     rbx, [rbp+270h+lpMem]
0x18002c265  mov     rax, cs:qword_18006FFD0
0x18002c26c  test    rax, rax
0x18002c26f  jnz     short loc_18002C2C5
0x18002c271  cmp     cs:?bGetFileVersionInfoSizeWProbed@@3_NA, r15b; bool bGetFileVersionInfoSizeWProbed
0x18002c278  jnz     loc_18002C42F
0x18002c27e  xor     r8d, r8d; dwFlags
0x18002c281  xor     edx, edx; hFile
0x18002c283  lea     rcx, aVersionDll; "version.dll"
0x18002c28a  call    cs:__imp_LoadLibraryExW
0x18002c290  test    rax, rax
0x18002c293  jz      short loc_18002C2AE
0x18002c295  lea     rdx, aGetfileversion; "GetFileVersionInfoSizeW"
0x18002c29c  mov     rcx, rax; hModule
0x18002c29f  call    cs:__imp_GetProcAddress
0x18002c2a5  mov     cs:qword_18006FFD0, rax
0x18002c2ac  jmp     short loc_18002C2B5
0x18002c2ae  mov     rax, cs:qword_18006FFD0
0x18002c2b5  mov     cs:?bGetFileVersionInfoSizeWProbed@@3_NA, 1; bool bGetFileVersionInfoSizeWProbed
0x18002c2bc  test    rax, rax
0x18002c2bf  jz      loc_18002C42F
0x18002c2c5  lea     rdx, [rbp+270h+var_270]
0x18002c2c9  mov     rcx, rbx
0x18002c2cc  call    cs:__guard_dispatch_icall_fptr
0x18002c2d2  mov     ebx, eax
0x18002c2d4  test    eax, eax
0x18002c2d6  jz      loc_18002C42F
0x18002c2dc  lea     rax, [rbx+0Fh]
0x18002c2e0  cmp     rax, rbx
0x18002c2e3  ja      short loc_18002C2EF
0x18002c2e5  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002c2ef  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002c2f3  call    _alloca_probe
0x18002c2f8  sub     rsp, rax
0x18002c2fb  lea     rdi, [rsp+2A0h+var_270]
0x18002c300  lea     rcx, [rbp+270h+var_240]; this
0x18002c304  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002c309  mov     rsi, [rbp+270h+lpMem]
0x18002c30d  mov     r14d, [rbp+270h+var_270]
0x18002c311  mov     rax, cs:qword_18006FFC8
0x18002c318  test    rax, rax
0x18002c31b  jnz     short loc_18002C371
0x18002c31d  cmp     cs:?bGetFileVersionInfoWProbed@@3_NA, r15b; bool bGetFileVersionInfoWProbed
0x18002c324  jnz     loc_18002C42F
0x18002c32a  xor     r8d, r8d; dwFlags
0x18002c32d  xor     edx, edx; hFile
0x18002c32f  lea     rcx, aVersionDll; "version.dll"
0x18002c336  call    cs:__imp_LoadLibraryExW
0x18002c33c  test    rax, rax
0x18002c33f  jz      short loc_18002C35A
0x18002c341  lea     rdx, aGetfileversion_0; "GetFileVersionInfoW"
0x18002c348  mov     rcx, rax; hModule
0x18002c34b  call    cs:__imp_GetProcAddress
0x18002c351  mov     cs:qword_18006FFC8, rax
0x18002c358  jmp     short loc_18002C361
0x18002c35a  mov     rax, cs:qword_18006FFC8
0x18002c361  mov     cs:?bGetFileVersionInfoWProbed@@3_NA, 1; bool bGetFileVersionInfoWProbed
0x18002c368  test    rax, rax
0x18002c36b  jz      loc_18002C42F
0x18002c371  mov     r9, rdi
0x18002c374  mov     r8d, ebx
0x18002c377  mov     edx, r14d
0x18002c37a  mov     rcx, rsi
0x18002c37d  call    cs:__guard_dispatch_icall_fptr
0x18002c383  test    eax, eax
0x18002c385  jz      loc_18002C42F
0x18002c38b  mov     [rbp+270h+var_26C], r15d
0x18002c38f  mov     rax, cs:qword_18006FFD8
0x18002c396  test    rax, rax
0x18002c399  jnz     short loc_18002C3EB
0x18002c39b  cmp     cs:?bVerQueryValueWProbed@@3_NA, r15b; bool bVerQueryValueWProbed
0x18002c3a2  jnz     loc_18002C42F
0x18002c3a8  xor     r8d, r8d; dwFlags
0x18002c3ab  xor     edx, edx; hFile
0x18002c3ad  lea     rcx, aVersionDll; "version.dll"
0x18002c3b4  call    cs:__imp_LoadLibraryExW
0x18002c3ba  test    rax, rax
0x18002c3bd  jz      short loc_18002C3D8
0x18002c3bf  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x18002c3c6  mov     rcx, rax; hModule
0x18002c3c9  call    cs:__imp_GetProcAddress
0x18002c3cf  mov     cs:qword_18006FFD8, rax
0x18002c3d6  jmp     short loc_18002C3DF
0x18002c3d8  mov     rax, cs:qword_18006FFD8
0x18002c3df  mov     cs:?bVerQueryValueWProbed@@3_NA, 1; bool bVerQueryValueWProbed
0x18002c3e6  test    rax, rax
0x18002c3e9  jz      short loc_18002C42F
0x18002c3eb  lea     r9, [rbp+270h+var_26C]
0x18002c3ef  lea     r8, [rbp+270h+var_250]
0x18002c3f3  lea     rdx, asc_180049544; "\\"
0x18002c3fa  mov     rcx, rdi
0x18002c3fd  call    cs:__guard_dispatch_icall_fptr
0x18002c403  test    eax, eax
0x18002c405  jz      short loc_18002C42F
0x18002c407  mov     rax, [rbp+270h+var_250]
0x18002c40b  cmp     dword ptr [rax+8], 20000h
0x18002c412  jnz     short loc_18002C42F
0x18002c414  mov     ecx, [rax+0Ch]
0x18002c417  mov     eax, ecx
0x18002c419  and     eax, 0FFFF0000h
0x18002c41e  cmp     eax, 0C6270000h
0x18002c423  jnz     short loc_18002C42F
0x18002c425  cmp     cx, 0BEDh
0x18002c42a  setb    bl
0x18002c42d  jmp     short loc_18002C432
0x18002c42f  mov     bl, r15b
0x18002c432  test    byte ptr [rbp+270h+var_238], 8
0x18002c436  jz      short loc_18002C468
0x18002c438  mov     rdi, [rbp+270h+lpMem]
0x18002c43c  test    rdi, rdi
0x18002c43f  jz      short loc_18002C468
0x18002c441  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002c448  test    rax, rax
0x18002c44b  jnz     short loc_18002C45A
0x18002c44d  call    cs:__imp_GetProcessHeap
0x18002c453  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002c45a  mov     r8, rdi; lpMem
0x18002c45d  xor     edx, edx; dwFlags
0x18002c45f  mov     rcx, rax; hHeap
0x18002c462  call    cs:__imp_HeapFree
0x18002c468  mov     al, bl
0x18002c46a  mov     rcx, [rbp+270h+var_20]
0x18002c471  xor     rcx, rbp; StackCookie
0x18002c474  call    __security_check_cookie
0x18002c479  mov     rbx, [rbp+270h+arg_0]
0x18002c480  mov     rsi, [rbp+270h+arg_8]
0x18002c487  mov     rdi, [rbp+270h+arg_10]
0x18002c48e  lea     rsp, [rbp+260h]
0x18002c495  pop     r15
0x18002c497  pop     r14
0x18002c499  pop     rbp
0x18002c49a  retn
```
