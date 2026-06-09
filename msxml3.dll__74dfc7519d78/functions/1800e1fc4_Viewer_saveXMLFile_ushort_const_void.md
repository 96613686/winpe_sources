# Viewer::saveXMLFile(ushort const *,void *)

- ea: `0x1800e1fc4`
- end: `0x1800e2284`
- name: `?saveXMLFile@Viewer@@AEAAJPEBGPEAX@Z`
- size: `704`
- prototype: `int(Viewer *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800dfee4`

## callees

- `0x18001dde0`
- `0x18001f080`
- `0x1800e1fc4`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e212c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e212c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e2163`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e2163`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e2148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e2148`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e20d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e20d9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e223a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e223a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e21dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e21dc`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800e2174`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800e2174`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e1ffc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800e1ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e2268`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e2268`

## string_xrefs

- `0x1800e2123`: `IEFRAME.DLL`

## pseudocode

```c
__int64 __fastcall Viewer::saveXMLFile(Viewer *this, const unsigned __int16 *a2, void *a3)
{
  OLECHAR *v6; // r15
  HRESULT v7; // ebx
  __int64 FileW; // rsi
  __int64 v9; // rax
  void *v10; // r14
  HMODULE Library; // rax
  HMODULE v12; // rdi
  FARPROC ProcAddress; // rax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-29h] BYREF
  __int64 v16; // [rsp+48h] [rbp-21h] BYREF
  __int64 v17; // [rsp+50h] [rbp-19h] BYREF
  LPBC ppbc; // [rsp+58h] [rbp-11h] BYREF
  __int128 v19; // [rsp+60h] [rbp-9h] BYREF
  __int64 v20; // [rsp+70h] [rbp+7h]
  DWORD nNumberOfBytesToWrite; // [rsp+E8h] [rbp+7Fh] BYREF

  v17 = 0;
  v19 = 0;
  v20 = 0;
  v6 = SysAllocString(a2);
  if ( v6 )
  {
    v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 7))(
           *((_QWORD *)this + 7),
           &IID_IOleCommandTarget,
           &v17);
    if ( v7 >= 0 )
    {
      *((_QWORD *)&v19 + 1) = v6;
      LOWORD(v19) = 8;
      (*(void (__fastcall **)(Viewer *))(*(_QWORD *)this + 8LL))(this);
      v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v17 + 32LL))(
             v17,
             &CGID_MSHTML,
             2370,
             0,
             &v19,
             0);
      (*(void (__fastcall **)(Viewer *))(*(_QWORD *)this + 16LL))(this);
      if ( v7 >= 0 )
        goto LABEL_32;
      if ( *((_QWORD *)this + 10) )
      {
        v16 = 0;
        ppbc = 0;
        FileW = -1;
        v9 = new_array_ne<unsigned char>(0x2000u);
        nNumberOfBytesToWrite = 0;
        v10 = (void *)v9;
        NumberOfBytesWritten = 0;
        if ( v9 )
        {
          v7 = CreateBindCtx(0, &ppbc);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(_QWORD, LPBC, _QWORD, GUID *, __int64 *))(**((_QWORD **)this + 10) + 72LL))(
                   *((_QWORD *)this + 10),
                   ppbc,
                   0,
                   &IID_IStream,
                   &v16);
            if ( v7 >= 0 )
            {
              FileW = (__int64)CreateFileW(a2, 0x40000000u, 0, 0, 2u, 0x80u, 0);
              if ( FileW == -1 )
              {
                v7 = -2147467259;
              }
              else
              {
                while ( (*(int (__fastcall **)(__int64, void *, __int64, DWORD *))(*(_QWORD *)v16 + 24LL))(
                          v16,
                          v10,
                          0x2000,
                          &nNumberOfBytesToWrite) >= 0
                     && nNumberOfBytesToWrite )
                  WriteFile((HANDLE)FileW, v10, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
              }
            }
          }
        }
        else
        {
          v7 = -2147024882;
        }
        MemFreeObject(v10);
        CloseHandle((HANDLE)FileW);
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v16 = 0;
        }
        if ( ppbc )
          ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      if ( v7 >= 0 )
      {
LABEL_32:
        if ( a3 )
        {
          Library = LoadLibraryExW(L"IEFRAME.DLL", 0, 0);
          v12 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "IESaveFile");
            if ( ProcAddress )
              v7 = ((__int64 (__fastcall *)(void *, const unsigned __int16 *))ProcAddress)(a3, a2);
            FreeLibrary(v12);
          }
        }
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v6 )
    SysFreeString(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800e1fc4  push    rbp
0x1800e1fc6  push    rbx
0x1800e1fc7  push    rsi
0x1800e1fc8  push    rdi
0x1800e1fc9  push    r12
0x1800e1fcb  push    r13
0x1800e1fcd  push    r14
0x1800e1fcf  push    r15
0x1800e1fd1  lea     rbp, [rsp-1Fh]
0x1800e1fd6  sub     rsp, 88h
0x1800e1fdd  mov     rdi, rcx
0x1800e1fe0  xorps   xmm0, xmm0
0x1800e1fe3  xor     eax, eax
0x1800e1fe5  xor     esi, esi
0x1800e1fe7  mov     rcx, rdx; psz
0x1800e1fea  mov     [rbp+57h+var_70], rsi
0x1800e1fee  movups  [rbp+57h+var_60], xmm0
0x1800e1ff2  mov     [rbp+57h+var_50], rax
0x1800e1ff6  mov     r13, r8
0x1800e1ff9  mov     r12, rdx
0x1800e1ffc  call    cs:__imp_SysAllocString
0x1800e2002  mov     r15, rax
0x1800e2005  test    rax, rax
0x1800e2008  jz      loc_1800E2242
0x1800e200e  mov     rcx, [rdi+38h]
0x1800e2012  lea     r8, [rbp+57h+var_70]
0x1800e2016  mov     rdx, [rcx]
0x1800e2019  mov     rax, [rdx]
0x1800e201c  lea     rdx, IID_IOleCommandTarget
0x1800e2023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2028  mov     ebx, eax
0x1800e202a  test    eax, eax
0x1800e202c  js      loc_1800E2247
0x1800e2032  lea     eax, [rsi+8]
0x1800e2035  mov     qword ptr [rbp+57h+var_60+8], r15
0x1800e2039  mov     word ptr [rbp+57h+var_60], ax
0x1800e203d  mov     rcx, rdi
0x1800e2040  mov     rax, [rdi]
0x1800e2043  mov     rax, [rax+8]
0x1800e2047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e204c  mov     rcx, [rbp+57h+var_70]
0x1800e2050  lea     rdx, [rbp+57h+var_60]
0x1800e2054  mov     qword ptr [rsp+0C0h+dwFlagsAndAttributes], rsi
0x1800e2059  xor     r9d, r9d
0x1800e205c  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx
0x1800e2061  mov     r8d, 942h
0x1800e2067  lea     rdx, CGID_MSHTML
0x1800e206e  mov     rax, [rcx]
0x1800e2071  mov     rax, [rax+20h]
0x1800e2075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e207a  mov     ebx, eax
0x1800e207c  mov     rcx, rdi
0x1800e207f  mov     rax, [rdi]
0x1800e2082  mov     rax, [rax+10h]
0x1800e2086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e208b  test    ebx, ebx
0x1800e208d  jns     loc_1800E2117
0x1800e2093  cmp     [rdi+50h], rsi
0x1800e2097  jz      short loc_1800E210F
0x1800e2099  mov     [rbp+57h+var_78], rsi
0x1800e209d  mov     ecx, 2000h; unsigned __int64
0x1800e20a2  mov     [rbp+57h+ppbc], rsi
0x1800e20a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800e20aa  call    ??$new_array_ne@E@@YAPEAE_J@Z; new_array_ne<uchar>(__int64)
0x1800e20af  mov     [rbp+57h+nNumberOfBytesToWrite], 0
0x1800e20b6  mov     r14, rax
0x1800e20b9  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1800e20c0  test    rax, rax
0x1800e20c3  jnz     loc_1800E216E
0x1800e20c9  mov     ebx, 8007000Eh
0x1800e20ce  mov     rcx, r14; void *
0x1800e20d1  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800e20d6  mov     rcx, rsi; hObject
0x1800e20d9  call    cs:__imp_CloseHandle
0x1800e20df  mov     rcx, [rbp+57h+var_78]
0x1800e20e3  xor     esi, esi
0x1800e20e5  test    rcx, rcx
0x1800e20e8  jz      short loc_1800E20FA
0x1800e20ea  mov     rax, [rcx]
0x1800e20ed  mov     rax, [rax+10h]
0x1800e20f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e20f6  mov     [rbp+57h+var_78], rsi
0x1800e20fa  mov     rcx, [rbp+57h+ppbc]
0x1800e20fe  test    rcx, rcx
0x1800e2101  jz      short loc_1800E210F
0x1800e2103  mov     rax, [rcx]
0x1800e2106  mov     rax, [rax+10h]
0x1800e210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e210f  test    ebx, ebx
0x1800e2111  js      loc_1800E2247
0x1800e2117  test    r13, r13
0x1800e211a  jz      loc_1800E2247
0x1800e2120  xor     r8d, r8d; dwFlags
0x1800e2123  lea     rcx, LibFileName; "IEFRAME.DLL"
0x1800e212a  xor     edx, edx; hFile
0x1800e212c  call    cs:__imp_LoadLibraryExW
0x1800e2132  mov     rdi, rax
0x1800e2135  test    rax, rax
0x1800e2138  jz      loc_1800E2247
0x1800e213e  lea     rdx, aIesavefile; "IESaveFile"
0x1800e2145  mov     rcx, rax; hModule
0x1800e2148  call    cs:__imp_GetProcAddress
0x1800e214e  test    rax, rax
0x1800e2151  jz      short loc_1800E2160
0x1800e2153  mov     rdx, r12
0x1800e2156  mov     rcx, r13
0x1800e2159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e215e  mov     ebx, eax
0x1800e2160  mov     rcx, rdi; hLibModule
0x1800e2163  call    cs:__imp_FreeLibrary
0x1800e2169  jmp     loc_1800E2247
0x1800e216e  lea     rdx, [rbp+57h+ppbc]; ppbc
0x1800e2172  xor     ecx, ecx; reserved
0x1800e2174  call    cs:__imp_CreateBindCtx
0x1800e217a  mov     ebx, eax
0x1800e217c  test    eax, eax
0x1800e217e  js      loc_1800E20CE
0x1800e2184  mov     rcx, [rdi+50h]
0x1800e2188  lea     rdx, [rbp+57h+var_78]
0x1800e218c  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rdx
0x1800e2191  lea     r9, IID_IStream
0x1800e2198  mov     rdx, [rbp+57h+ppbc]
0x1800e219c  xor     r8d, r8d
0x1800e219f  mov     rax, [rcx]
0x1800e21a2  mov     rax, [rax+48h]
0x1800e21a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e21ab  mov     ebx, eax
0x1800e21ad  test    eax, eax
0x1800e21af  js      loc_1800E20CE
0x1800e21b5  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800e21be  xor     r9d, r9d; lpSecurityAttributes
0x1800e21c1  mov     [rsp+0C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e21c9  xor     r8d, r8d; dwShareMode
0x1800e21cc  mov     edx, 40000000h; dwDesiredAccess
0x1800e21d1  mov     [rsp+0C0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800e21d9  mov     rcx, r12; lpFileName
0x1800e21dc  call    cs:__imp_CreateFileW
0x1800e21e2  mov     rsi, rax
0x1800e21e5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e21e9  jnz     short loc_1800E21F5
0x1800e21eb  mov     ebx, 80004005h
0x1800e21f0  jmp     loc_1800E20CE
0x1800e21f5  mov     rcx, [rbp+57h+var_78]
0x1800e21f9  lea     r9, [rbp+57h+nNumberOfBytesToWrite]
0x1800e21fd  mov     r8d, 2000h
0x1800e2203  mov     rdx, r14
0x1800e2206  mov     rax, [rcx]
0x1800e2209  mov     rax, [rax+18h]
0x1800e220d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2212  test    eax, eax
0x1800e2214  js      loc_1800E20CE
0x1800e221a  mov     r8d, [rbp+57h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800e221e  test    r8d, r8d
0x1800e2221  jz      loc_1800E20CE
0x1800e2227  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800e222b  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x1800e2234  mov     rdx, r14; lpBuffer
0x1800e2237  mov     rcx, rsi; hFile
0x1800e223a  call    cs:__imp_WriteFile
0x1800e2240  jmp     short loc_1800E21F5
0x1800e2242  mov     ebx, 8007000Eh
0x1800e2247  mov     rcx, [rbp+57h+var_70]
0x1800e224b  test    rcx, rcx
0x1800e224e  jz      short loc_1800E2260
0x1800e2250  mov     rax, [rcx]
0x1800e2253  mov     rax, [rax+10h]
0x1800e2257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e225c  mov     [rbp+57h+var_70], rsi
0x1800e2260  test    r15, r15
0x1800e2263  jz      short loc_1800E226E
0x1800e2265  mov     rcx, r15; bstrString
0x1800e2268  call    cs:__imp_SysFreeString
0x1800e226e  mov     eax, ebx
0x1800e2270  add     rsp, 88h
0x1800e2277  pop     r15
0x1800e2279  pop     r14
0x1800e227b  pop     r13
0x1800e227d  pop     r12
0x1800e227f  pop     rdi
0x1800e2280  pop     rsi
0x1800e2281  pop     rbx
0x1800e2282  pop     rbp
0x1800e2283  retn
```
