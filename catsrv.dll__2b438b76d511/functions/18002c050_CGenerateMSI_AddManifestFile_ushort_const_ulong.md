# CGenerateMSI::AddManifestFile(ushort const *,ulong)

- ea: `0x18002c050`
- end: `0x18002c2eb`
- name: `?AddManifestFile@CGenerateMSI@@UEAAJPEBGK@Z`
- size: `667`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000a01c`
- `0x18002c050`
- `0x18002dda8`
- `0x18002deac`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c203`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c1c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c1c6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c1f8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c1f8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c102`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002c102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2b6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c11c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c11c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c0cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c0cd`

## string_xrefs

- `0x18002c227`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002c131`: `Manifest_%s`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddManifestFile(CGenerateMSI *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 *v6; // rsi
  __int64 v7; // rax
  unsigned __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r14
  int inserted; // ebx
  CGenerateMSI *v12; // rcx
  int v13; // eax
  CGenerateMSI *v14; // rcx
  HANDLE FileW; // rax
  void *v16; // r12
  signed int LastError; // eax
  DWORD FileSize; // ebx
  LPOLESTR lpsz; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v24[264]; // [rsp+90h] [rbp-70h] BYREF

  pv = 0;
  v21 = 0;
  v6 = 0;
  memset_0(v24, 0, 0x208u);
  lpsz = 0;
  pguid = 0;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v7 + 1));
  v10 = v9;
  if ( v9 )
  {
    inserted = StringCchCopyW(v9, v8, a2);
    if ( inserted >= 0 )
    {
      inserted = CoCreateGuid(&pguid);
      if ( inserted >= 0 )
      {
        inserted = StringFromCLSID(&pguid, &lpsz);
        if ( inserted >= 0 )
        {
          inserted = StringCchPrintfW(v24, 0x104u, L"Manifest_%s", lpsz);
          if ( inserted >= 0 )
          {
            v13 = CGenerateMSI::GenerateIdentifier(v12, &v21, v24);
            v6 = v21;
            inserted = v13;
            if ( v13 >= 0 )
            {
              inserted = CGenerateMSI::_InsertComponent(this, v21, lpsz, *((_DWORD *)this + 162));
              if ( inserted >= 0 )
              {
                inserted = CGenerateMSI::GenerateMSIFileName(v14, v10, (unsigned __int16 **)&pv);
                if ( inserted >= 0 )
                {
                  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
                  v16 = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    LastError = GetLastError();
                    inserted = LastError;
                    if ( LastError > 0 )
                      inserted = (unsigned __int16)LastError | 0x80070000;
                  }
                  else
                  {
                    FileSize = GetFileSize(FileW, 0);
                    CloseHandle(v16);
                    inserted = CGenerateMSI::_InsertRow(
                                 this,
                                 L"File",
                                 L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                                 L"'%s', '%s', '%s', %ld, '%s', %d, %d, %d",
                                 v6,
                                 v6,
                                 pv,
                                 FileSize,
                                 L"1.1.1.1",
                                 2048,
                                 0,
                                 *((_DWORD *)this + 20));
                    if ( inserted >= 0 )
                    {
                      inserted = CGenerateMSI::_GetMakeCab(this, a3);
                      if ( inserted >= 0 )
                        inserted = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned __int16 *))(**((_QWORD **)this + 77) + 32LL))(
                                     *((_QWORD *)this + 77),
                                     a2,
                                     v6);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    inserted = -2147024882;
  }
  CoTaskMemFree(lpsz);
  CoTaskMemFree(v6);
  CoTaskMemFree(pv);
  CoTaskMemFree(v10);
  ++*((_DWORD *)this + 20);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002c050  mov     [rsp-8+arg_18], rbx
0x18002c055  push    rbp
0x18002c056  push    rsi
0x18002c057  push    rdi
0x18002c058  push    r12
0x18002c05a  push    r13
0x18002c05c  push    r14
0x18002c05e  push    r15
0x18002c060  lea     rbp, [rsp-1B0h]
0x18002c068  sub     rsp, 2B0h
0x18002c06f  mov     rax, cs:__security_cookie
0x18002c076  xor     rax, rsp
0x18002c079  mov     [rbp+1E0h+var_40], rax
0x18002c080  xor     r12d, r12d
0x18002c083  mov     r13d, r8d
0x18002c086  mov     r15, rdx
0x18002c089  mov     [rsp+2E0h+pv], r12
0x18002c08e  mov     rdi, rcx
0x18002c091  mov     [rsp+2E0h+var_278], r12
0x18002c096  xor     edx, edx; Val
0x18002c098  lea     rcx, [rbp+1E0h+var_250]; void *
0x18002c09c  mov     r8d, 208h; Size
0x18002c0a2  mov     esi, r12d
0x18002c0a5  call    memset_0
0x18002c0aa  xorps   xmm0, xmm0
0x18002c0ad  mov     [rsp+2E0h+lpsz], r12
0x18002c0b2  movups  xmmword ptr [rsp+2E0h+pguid.Data1], xmm0
0x18002c0b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c0bb  inc     rax
0x18002c0be  cmp     [r15+rax*2], r12w
0x18002c0c3  jnz     short loc_18002C0BB
0x18002c0c5  lea     rbx, [rax+1]
0x18002c0c9  lea     rcx, [rbx+rbx]; cb
0x18002c0cd  call    cs:__imp_CoTaskMemAlloc
0x18002c0d3  mov     r14, rax
0x18002c0d6  test    rax, rax
0x18002c0d9  jnz     short loc_18002C0E5
0x18002c0db  mov     ebx, 8007000Eh
0x18002c0e0  jmp     loc_18002C294
0x18002c0e5  mov     r8, r15; unsigned __int16 *
0x18002c0e8  mov     rdx, rbx; unsigned __int64
0x18002c0eb  mov     rcx, r14; unsigned __int16 *
0x18002c0ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002c0f3  mov     ebx, eax
0x18002c0f5  test    eax, eax
0x18002c0f7  js      loc_18002C294
0x18002c0fd  lea     rcx, [rsp+2E0h+pguid]; pguid
0x18002c102  call    cs:__imp_CoCreateGuid
0x18002c108  mov     ebx, eax
0x18002c10a  test    eax, eax
0x18002c10c  js      loc_18002C294
0x18002c112  lea     rdx, [rsp+2E0h+lpsz]; lplpsz
0x18002c117  lea     rcx, [rsp+2E0h+pguid]; rclsid
0x18002c11c  call    cs:__imp_StringFromCLSID
0x18002c122  mov     ebx, eax
0x18002c124  test    eax, eax
0x18002c126  js      loc_18002C294
0x18002c12c  mov     r9, [rsp+2E0h+lpsz]
0x18002c131  lea     r8, aManifestS; "Manifest_%s"
0x18002c138  mov     edx, 104h; unsigned __int64
0x18002c13d  lea     rcx, [rbp+1E0h+var_250]; unsigned __int16 *
0x18002c141  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c146  mov     ebx, eax
0x18002c148  test    eax, eax
0x18002c14a  js      loc_18002C294
0x18002c150  lea     r8, [rbp+1E0h+var_250]; unsigned __int16 *
0x18002c154  lea     rdx, [rsp+2E0h+var_278]; unsigned __int16 **
0x18002c159  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002c15e  mov     rsi, [rsp+2E0h+var_278]
0x18002c163  mov     ebx, eax
0x18002c165  test    eax, eax
0x18002c167  js      loc_18002C294
0x18002c16d  mov     r9d, [rdi+288h]; unsigned int
0x18002c174  mov     rdx, rsi; unsigned __int16 *
0x18002c177  mov     r8, [rsp+2E0h+lpsz]; unsigned __int16 *
0x18002c17c  mov     rcx, rdi; this
0x18002c17f  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002c184  mov     ebx, eax
0x18002c186  test    eax, eax
0x18002c188  js      loc_18002C294
0x18002c18e  lea     r8, [rsp+2E0h+pv]; unsigned __int16 **
0x18002c193  mov     rdx, r14; unsigned __int16 *
0x18002c196  call    ?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z; CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)
0x18002c19b  mov     ebx, eax
0x18002c19d  test    eax, eax
0x18002c19f  js      loc_18002C294
0x18002c1a5  xor     r9d, r9d; lpSecurityAttributes
0x18002c1a8  mov     [rsp+2E0h+hTemplateFile], r12; hTemplateFile
0x18002c1ad  mov     [rsp+2E0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002c1b2  mov     edx, 80000000h; dwDesiredAccess
0x18002c1b7  mov     rcx, r15; lpFileName
0x18002c1ba  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c1c2  lea     r8d, [r9+1]; dwShareMode
0x18002c1c6  call    cs:__imp_CreateFileW
0x18002c1cc  mov     r12, rax
0x18002c1cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c1d3  jnz     short loc_18002C1F3
0x18002c1d5  call    cs:__imp_GetLastError
0x18002c1db  mov     ebx, eax
0x18002c1dd  test    eax, eax
0x18002c1df  jle     loc_18002C294
0x18002c1e5  movzx   ebx, ax
0x18002c1e8  or      ebx, 80070000h
0x18002c1ee  jmp     loc_18002C294
0x18002c1f3  xor     edx, edx; lpFileSizeHigh
0x18002c1f5  mov     rcx, r12; hFile
0x18002c1f8  call    cs:__imp_GetFileSize
0x18002c1fe  mov     rcx, r12; hObject
0x18002c201  mov     ebx, eax
0x18002c203  call    cs:__imp_CloseHandle
0x18002c209  mov     ecx, [rdi+50h]
0x18002c20c  lea     rax, a1111; "1.1.1.1"
0x18002c213  mov     [rsp+2E0h+var_288], ecx
0x18002c217  lea     r9, aSSSLdSDDD; "'%s', '%s', '%s', %ld, '%s', %d, %d, %d"
0x18002c21e  mov     [rsp+2E0h+var_290], 0
0x18002c227  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002c22e  mov     [rsp+2E0h+var_298], 800h
0x18002c236  lea     rdx, aFile_0; "File"
0x18002c23d  mov     [rsp+2E0h+var_2A0], rax
0x18002c242  mov     rcx, rdi; this
0x18002c245  mov     rax, [rsp+2E0h+pv]
0x18002c24a  mov     [rsp+2E0h+var_2A8], ebx
0x18002c24e  mov     [rsp+2E0h+hTemplateFile], rax
0x18002c253  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rsi
0x18002c258  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rsi
0x18002c25d  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002c262  mov     ebx, eax
0x18002c264  test    eax, eax
0x18002c266  js      short loc_18002C294
0x18002c268  mov     edx, r13d; unsigned int
0x18002c26b  mov     rcx, rdi; this
0x18002c26e  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002c273  mov     ebx, eax
0x18002c275  test    eax, eax
0x18002c277  js      short loc_18002C294
0x18002c279  mov     rcx, [rdi+268h]
0x18002c280  mov     r8, rsi
0x18002c283  mov     rdx, r15
0x18002c286  mov     rax, [rcx]
0x18002c289  mov     rax, [rax+20h]
0x18002c28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c292  mov     ebx, eax
0x18002c294  mov     rcx, [rsp+2E0h+lpsz]; pv
0x18002c299  call    cs:__imp_CoTaskMemFree
0x18002c29f  mov     rcx, rsi; pv
0x18002c2a2  call    cs:__imp_CoTaskMemFree
0x18002c2a8  mov     rcx, [rsp+2E0h+pv]; pv
0x18002c2ad  call    cs:__imp_CoTaskMemFree
0x18002c2b3  mov     rcx, r14; pv
0x18002c2b6  call    cs:__imp_CoTaskMemFree
0x18002c2bc  inc     dword ptr [rdi+50h]
0x18002c2bf  mov     eax, ebx
0x18002c2c1  mov     rcx, [rbp+1E0h+var_40]
0x18002c2c8  xor     rcx, rsp; StackCookie
0x18002c2cb  call    __security_check_cookie
0x18002c2d0  mov     rbx, [rsp+2E0h+arg_18]
0x18002c2d8  add     rsp, 2B0h
0x18002c2df  pop     r15
0x18002c2e1  pop     r14
0x18002c2e3  pop     r13
0x18002c2e5  pop     r12
0x18002c2e7  pop     rdi
0x18002c2e8  pop     rsi
0x18002c2e9  pop     rbp
0x18002c2ea  retn
```
