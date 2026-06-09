# CGenerateMSI::AddPSDll(ushort const *,ulong,ulong,_tagPSCLASSINFO *)

- ea: `0x18002c300`
- end: `0x18002c811`
- name: `?AddPSDll@CGenerateMSI@@UEAAJPEBGKKPEAU_tagPSCLASSINFO@@@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CGenerateMSI *this, WCHAR *, unsigned int, unsigned int, IID *rclsid)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18002c300`
- `0x18002dda8`
- `0x18002deac`
- `0x18002e0c8`
- `0x18002e620`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x180055550`
- `0x180055610`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c39d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c464`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c464`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002c393`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002c393`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c47c`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002c47c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c779`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c438`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c749`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c766`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c779`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c7df`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c3c3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c59a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c6a3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c3c3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c59a`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002c6a3`

## string_xrefs

- `0x18002c507`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002c5af`: `CLSID\%s\InprocServer32`
- `0x18002c6b8`: `Interface\%s\ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddPSDll(CGenerateMSI *this, WCHAR *a2, unsigned int a3, unsigned int a4, IID *rclsid)
{
  unsigned __int16 *v8; // rsi
  void *v9; // r12
  signed int LastError; // eax
  int inserted; // ebx
  CGenerateMSI *v12; // rcx
  int Identifier; // eax
  HANDLE FileW; // rax
  void *v15; // rbx
  DWORD FileSize; // r15d
  CGenerateMSI *v17; // rcx
  CGenerateMSI *v18; // rcx
  unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // rax
  unsigned int v21; // r15d
  int v22; // eax
  unsigned int v23; // r14d
  const IID *v24; // r13
  CGenerateMSI *v25; // rcx
  int v26; // eax
  LPOLESTR v27; // rdx
  LPOLESTR i; // rax
  OLECHAR v29; // cx
  DWORD v31; // [rsp+38h] [rbp-C8h]
  LPOLESTR lpsz; // [rsp+60h] [rbp-A0h] BYREF
  LPOLESTR v33; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v35; // [rsp+78h] [rbp-88h]
  unsigned int v36; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v37; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v38; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v39; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR FilePart; // [rsp+98h] [rbp-68h] BYREF
  IID *v41; // [rsp+A0h] [rbp-60h]
  IID v42; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v43[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v44[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v45[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR Buffer[264]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v47[2048]; // [rsp+900h] [rbp+800h] BYREF

  v35 = a4;
  v36 = a3;
  v41 = rclsid;
  v33 = 0;
  lpsz = 0;
  FilePart = 0;
  *(_QWORD *)&v42.Data1 = 0;
  v8 = 0;
  pv = 0;
  v9 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( !GetFullPathNameW(a2, 0x104u, Buffer, &FilePart) )
    goto LABEL_2;
  inserted = StringFromCLSID(rclsid, &lpsz);
  if ( inserted < 0 )
    goto LABEL_41;
  inserted = StringCchPrintfW(v43, 0x104u, L"PS_%s", lpsz);
  if ( inserted < 0 )
    goto LABEL_41;
  Identifier = CGenerateMSI::GenerateIdentifier(v12, (unsigned __int16 **)&v42, v43);
  v8 = *(unsigned __int16 **)&v42.Data1;
  inserted = Identifier;
  if ( Identifier < 0 )
    goto LABEL_41;
  inserted = CGenerateMSI::_InsertComponent(this, *(const unsigned __int16 **)&v42.Data1, lpsz, *((_DWORD *)this + 162));
  if ( inserted < 0 )
    goto LABEL_41;
  CoTaskMemFree(lpsz);
  lpsz = 0;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0, 0);
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, 0), CloseHandle(v15), FileSize == -1) )
  {
LABEL_2:
    LastError = GetLastError();
    inserted = LastError;
    if ( LastError > 0 )
      inserted = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    inserted = CGenerateMSI::GenerateMSIFileName(v17, a2, &v37);
    if ( inserted >= 0 )
    {
      CGenerateMSI::GenerateMSIFileVerAndLocale(v18, a2, &v38, &v39);
      v19 = L"0";
      if ( v39 )
        v19 = v39;
      v20 = L"1.1.1.2";
      if ( v38 )
        v20 = v38;
      v31 = FileSize;
      v21 = 0;
      inserted = CGenerateMSI::_InsertRow(
                   this,
                   L"File",
                   L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                   L"'%s', '%s', '%s', %ld, '%s', '%s', %d, %d",
                   v8,
                   v8,
                   v37,
                   v31,
                   v20,
                   v19,
                   0,
                   *((_DWORD *)this + 20));
      if ( inserted >= 0 )
      {
        inserted = CGenerateMSI::_GetMakeCab(this, a3);
        if ( inserted >= 0 )
        {
          v22 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, unsigned __int16 *))(**((_QWORD **)this + 77) + 32LL))(
                  *((_QWORD *)this + 77),
                  a2,
                  v8);
          v23 = 0;
          inserted = v22;
          if ( v22 >= 0 )
          {
            while ( v21 < v35 )
            {
              v24 = (IID *)((char *)v41 + 40 * v21);
              inserted = StringFromCLSID(v24, &lpsz);
              if ( inserted < 0 )
                goto LABEL_41;
              inserted = StringCchPrintfW(v47, 0x800u, L"CLSID\\%s\\InprocServer32", lpsz);
              if ( inserted < 0 )
                goto LABEL_41;
              inserted = StringCchPrintfW(v45, 0x104u, L"[#%s]", v8);
              if ( inserted < 0 )
                goto LABEL_41;
              inserted = StringCchPrintfW(v44, 0x104u, L"PS_%s", lpsz);
              if ( inserted < 0 )
                goto LABEL_41;
              v26 = CGenerateMSI::GenerateIdentifier(v25, (unsigned __int16 **)&pv, v44);
              v9 = pv;
              inserted = v26;
              if ( v26 < 0 )
                goto LABEL_41;
              inserted = CGenerateMSI::_AddRegKey(this, (const unsigned __int16 *)pv, v47, &word_18005C890, v45, v8);
              if ( inserted < 0 )
                goto LABEL_41;
              if ( (v36 & 0x20) != 0 )
              {
                while ( v23 < *(_DWORD *)v24[1].Data4 )
                {
                  v42 = *(IID *)(*(_QWORD *)&v24[2].Data1 + 24LL * v23);
                  inserted = StringFromCLSID(&v42, &v33);
                  if ( inserted < 0 )
                    goto LABEL_41;
                  inserted = StringCchPrintfW(v47, 0x800u, L"Interface\\%s\\ProxyStubClsid32", v33);
                  if ( inserted < 0 )
                    goto LABEL_41;
                  v27 = v33;
                  for ( i = v33; ; ++i )
                  {
                    v29 = *i;
                    if ( *i == 45 || v29 == 123 || v29 == 125 )
                      v29 = *++i;
                    *v27 = v29;
                    if ( !*i )
                      break;
                    ++v27;
                  }
                  inserted = CGenerateMSI::_AddRegKey(this, v33, v47, &word_18005C890, lpsz, v8);
                  if ( inserted < 0 )
                    goto LABEL_41;
                  CoTaskMemFree(v33);
                  ++v23;
                  v33 = 0;
                }
                v23 = 0;
              }
              CoTaskMemFree(v9);
              v9 = 0;
              pv = 0;
              CoTaskMemFree(lpsz);
              lpsz = 0;
              CoTaskMemFree(v33);
              ++v21;
              v33 = 0;
            }
            ++*((_DWORD *)this + 20);
          }
        }
      }
    }
  }
LABEL_41:
  CoTaskMemFree(v9);
  CoTaskMemFree(lpsz);
  CoTaskMemFree(v33);
  CoTaskMemFree(v8);
  CoTaskMemFree(v37);
  CoTaskMemFree(v38);
  CoTaskMemFree(v39);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002c300  mov     [rsp-8+arg_18], rbx
0x18002c305  push    rbp
0x18002c306  push    rsi
0x18002c307  push    rdi
0x18002c308  push    r12
0x18002c30a  push    r13
0x18002c30c  push    r14
0x18002c30e  push    r15
0x18002c310  lea     rbp, [rsp-1810h]
0x18002c318  mov     eax, 1910h
0x18002c31d  call    _alloca_probe
0x18002c322  sub     rsp, rax
0x18002c325  mov     rax, cs:__security_cookie
0x18002c32c  xor     rax, rsp
0x18002c32f  mov     [rbp+1840h+var_40], rax
0x18002c336  mov     rbx, [rbp+1840h+rclsid]
0x18002c33d  xor     r15d, r15d
0x18002c340  mov     r14, rdx
0x18002c343  mov     [rsp+1940h+var_18C8], r9d
0x18002c348  mov     r13d, r8d
0x18002c34b  mov     [rsp+1940h+var_18C4], r8d
0x18002c350  mov     rdi, rcx
0x18002c353  mov     [rbp+1840h+var_18A0], rbx
0x18002c357  mov     rcx, r14; lpFileName
0x18002c35a  mov     [rsp+1940h+var_18D8], r15
0x18002c35f  lea     r9, [rbp+1840h+FilePart]; lpFilePart
0x18002c363  mov     [rsp+1940h+lpsz], r15
0x18002c368  lea     r8, [rbp+1840h+Buffer]; lpBuffer
0x18002c36f  mov     [rbp+1840h+FilePart], r15
0x18002c373  mov     edx, 104h; nBufferLength
0x18002c378  mov     qword ptr [rbp+1840h+var_1898.Data1], r15
0x18002c37c  mov     esi, r15d
0x18002c37f  mov     [rsp+1940h+pv], r15
0x18002c384  mov     r12d, r15d
0x18002c387  mov     [rbp+1840h+var_18C0], r15
0x18002c38b  mov     [rbp+1840h+var_18B8], r15
0x18002c38f  mov     [rbp+1840h+var_18B0], r15
0x18002c393  call    cs:__imp_GetFullPathNameW
0x18002c399  test    eax, eax
0x18002c39b  jnz     short loc_18002C3BB
0x18002c39d  call    cs:__imp_GetLastError
0x18002c3a3  mov     ebx, eax
0x18002c3a5  test    eax, eax
0x18002c3a7  jle     loc_18002C79F
0x18002c3ad  movzx   ebx, ax
0x18002c3b0  or      ebx, 80070000h
0x18002c3b6  jmp     loc_18002C79F
0x18002c3bb  lea     rdx, [rsp+1940h+lpsz]; lplpsz
0x18002c3c0  mov     rcx, rbx; rclsid
0x18002c3c3  call    cs:__imp_StringFromCLSID
0x18002c3c9  mov     ebx, eax
0x18002c3cb  test    eax, eax
0x18002c3cd  js      loc_18002C79F
0x18002c3d3  mov     r9, [rsp+1940h+lpsz]
0x18002c3d8  lea     r8, aPsS; "PS_%s"
0x18002c3df  mov     edx, 104h; unsigned __int64
0x18002c3e4  lea     rcx, [rbp+1840h+var_1880]; unsigned __int16 *
0x18002c3e8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c3ed  mov     ebx, eax
0x18002c3ef  test    eax, eax
0x18002c3f1  js      loc_18002C79F
0x18002c3f7  lea     r8, [rbp+1840h+var_1880]; unsigned __int16 *
0x18002c3fb  lea     rdx, [rbp+1840h+var_1898]; unsigned __int16 **
0x18002c3ff  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002c404  mov     rsi, qword ptr [rbp+1840h+var_1898.Data1]
0x18002c408  mov     ebx, eax
0x18002c40a  test    eax, eax
0x18002c40c  js      loc_18002C79F
0x18002c412  mov     r9d, [rdi+288h]; unsigned int
0x18002c419  mov     rdx, rsi; unsigned __int16 *
0x18002c41c  mov     r8, [rsp+1940h+lpsz]; unsigned __int16 *
0x18002c421  mov     rcx, rdi; this
0x18002c424  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002c429  mov     ebx, eax
0x18002c42b  test    eax, eax
0x18002c42d  js      loc_18002C79F
0x18002c433  mov     rcx, [rsp+1940h+lpsz]; pv
0x18002c438  call    cs:__imp_CoTaskMemFree
0x18002c43e  xor     r9d, r9d; lpSecurityAttributes
0x18002c441  mov     [rsp+1940h+hTemplateFile], r15; hTemplateFile
0x18002c446  mov     [rsp+1940h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18002c44b  mov     edx, 80000000h; dwDesiredAccess
0x18002c450  mov     rcx, r14; lpFileName
0x18002c453  mov     [rsp+1940h+lpsz], r15
0x18002c458  mov     [rsp+1940h+dwCreationDisposition], 3; dwCreationDisposition
0x18002c460  lea     r8d, [r9+1]; dwShareMode
0x18002c464  call    cs:__imp_CreateFileW
0x18002c46a  mov     rbx, rax
0x18002c46d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c471  jz      loc_18002C39D
0x18002c477  xor     edx, edx; lpFileSizeHigh
0x18002c479  mov     rcx, rax; hFile
0x18002c47c  call    cs:__imp_GetFileSize
0x18002c482  mov     rcx, rbx; hObject
0x18002c485  mov     r15d, eax
0x18002c488  call    cs:__imp_CloseHandle
0x18002c48e  cmp     r15d, 0FFFFFFFFh
0x18002c492  jz      loc_18002C39D
0x18002c498  lea     r8, [rbp+1840h+var_18C0]; unsigned __int16 **
0x18002c49c  mov     rdx, r14; unsigned __int16 *
0x18002c49f  call    ?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z; CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)
0x18002c4a4  mov     ebx, eax
0x18002c4a6  test    eax, eax
0x18002c4a8  js      loc_18002C79F
0x18002c4ae  lea     r9, [rbp+1840h+var_18B0]; unsigned __int16 **
0x18002c4b2  mov     rdx, r14; unsigned __int16 *
0x18002c4b5  lea     r8, [rbp+1840h+var_18B8]; unsigned __int16 **
0x18002c4b9  call    ?GenerateMSIFileVerAndLocale@CGenerateMSI@@AEAAJPEAGPEAPEAG1@Z; CGenerateMSI::GenerateMSIFileVerAndLocale(ushort *,ushort * *,ushort * *)
0x18002c4be  mov     rax, [rbp+1840h+var_18B0]
0x18002c4c2  lea     rdx, Default; "0"
0x18002c4c9  mov     r8, [rbp+1840h+var_18B8]
0x18002c4cd  xor     r9d, r9d
0x18002c4d0  mov     ecx, [rdi+50h]
0x18002c4d3  test    rax, rax
0x18002c4d6  mov     [rsp+1940h+var_18E8], ecx
0x18002c4da  mov     rcx, rdi; this
0x18002c4dd  mov     [rsp+1940h+var_18F0], r9
0x18002c4e2  cmovnz  rdx, rax
0x18002c4e6  mov     [rsp+1940h+var_18F8], rdx
0x18002c4eb  lea     rax, a1112; "1.1.1.2"
0x18002c4f2  test    r8, r8
0x18002c4f5  lea     r9, aSSSLdSSDD; "'%s', '%s', '%s', %ld, '%s', '%s', %d, "...
0x18002c4fc  lea     rdx, aFile_0; "File"
0x18002c503  cmovnz  rax, r8
0x18002c507  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002c50e  mov     [rsp+1940h+var_1900], rax
0x18002c513  mov     rax, [rbp+1840h+var_18C0]
0x18002c517  mov     [rsp+1940h+var_1908], r15d
0x18002c51c  mov     [rsp+1940h+hTemplateFile], rax
0x18002c521  mov     qword ptr [rsp+1940h+dwFlagsAndAttributes], rsi
0x18002c526  mov     qword ptr [rsp+1940h+dwCreationDisposition], rsi
0x18002c52b  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002c530  xor     r15d, r15d
0x18002c533  mov     ebx, eax
0x18002c535  test    eax, eax
0x18002c537  js      loc_18002C79F
0x18002c53d  mov     edx, r13d; unsigned int
0x18002c540  mov     rcx, rdi; this
0x18002c543  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002c548  mov     ebx, eax
0x18002c54a  test    eax, eax
0x18002c54c  js      loc_18002C79F
0x18002c552  mov     rcx, [rdi+268h]
0x18002c559  mov     r8, rsi
0x18002c55c  mov     rdx, r14
0x18002c55f  mov     rax, [rcx]
0x18002c562  mov     rax, [rax+20h]
0x18002c566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c56b  xor     r14d, r14d
0x18002c56e  mov     ebx, eax
0x18002c570  test    eax, eax
0x18002c572  js      loc_18002C79F
0x18002c578  cmp     r15d, [rsp+1940h+var_18C8]
0x18002c57d  jnb     loc_18002C79C
0x18002c583  mov     eax, r15d
0x18002c586  lea     rdx, [rsp+1940h+lpsz]; lplpsz
0x18002c58b  lea     rcx, [rax+rax*4]
0x18002c58f  mov     rax, [rbp+1840h+var_18A0]
0x18002c593  lea     r13, [rax+rcx*8]
0x18002c597  mov     rcx, r13; rclsid
0x18002c59a  call    cs:__imp_StringFromCLSID
0x18002c5a0  mov     ebx, eax
0x18002c5a2  test    eax, eax
0x18002c5a4  js      loc_18002C79F
0x18002c5aa  mov     r9, [rsp+1940h+lpsz]
0x18002c5af  lea     r8, aClsidSInprocse; "CLSID\\%s\\InprocServer32"
0x18002c5b6  mov     edx, 800h; unsigned __int64
0x18002c5bb  lea     rcx, [rbp+1840h+var_1040]; unsigned __int16 *
0x18002c5c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c5c7  mov     ebx, eax
0x18002c5c9  test    eax, eax
0x18002c5cb  js      loc_18002C79F
0x18002c5d1  mov     r9, rsi
0x18002c5d4  lea     r8, aS_0; "[#%s]"
0x18002c5db  mov     edx, 104h; unsigned __int64
0x18002c5e0  lea     rcx, [rbp+1840h+var_1460]; unsigned __int16 *
0x18002c5e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c5ec  mov     ebx, eax
0x18002c5ee  test    eax, eax
0x18002c5f0  js      loc_18002C79F
0x18002c5f6  mov     r9, [rsp+1940h+lpsz]
0x18002c5fb  lea     r8, aPsS; "PS_%s"
0x18002c602  mov     edx, 104h; unsigned __int64
0x18002c607  lea     rcx, [rbp+1840h+var_1670]; unsigned __int16 *
0x18002c60e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c613  mov     ebx, eax
0x18002c615  test    eax, eax
0x18002c617  js      loc_18002C79F
0x18002c61d  lea     r8, [rbp+1840h+var_1670]; unsigned __int16 *
0x18002c624  lea     rdx, [rsp+1940h+pv]; unsigned __int16 **
0x18002c629  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002c62e  mov     r12, [rsp+1940h+pv]
0x18002c633  mov     ebx, eax
0x18002c635  test    eax, eax
0x18002c637  js      loc_18002C79F
0x18002c63d  lea     rax, [rbp+1840h+var_1460]
0x18002c644  mov     qword ptr [rsp+1940h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x18002c649  lea     r9, word_18005C890; unsigned __int16 *
0x18002c650  mov     qword ptr [rsp+1940h+dwCreationDisposition], rax; unsigned __int16 *
0x18002c655  lea     r8, [rbp+1840h+var_1040]; unsigned __int16 *
0x18002c65c  mov     rdx, r12; unsigned __int16 *
0x18002c65f  mov     rcx, rdi; this
0x18002c662  call    ?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z; CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002c667  mov     ebx, eax
0x18002c669  test    eax, eax
0x18002c66b  js      loc_18002C79F
0x18002c671  test    byte ptr [rsp+1940h+var_18C4], 20h
0x18002c676  jz      loc_18002C763
0x18002c67c  cmp     r14d, [r13+18h]
0x18002c680  jnb     loc_18002C760
0x18002c686  mov     eax, r14d
0x18002c689  lea     rdx, [rsp+1940h+var_18D8]; lplpsz
0x18002c68e  lea     rcx, [rax+rax*2]
0x18002c692  mov     rax, [r13+20h]
0x18002c696  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18002c69a  lea     rcx, [rbp+1840h+var_1898]; rclsid
0x18002c69e  movdqu  xmmword ptr [rbp+1840h+var_1898.Data1], xmm0
0x18002c6a3  call    cs:__imp_StringFromCLSID
0x18002c6a9  mov     ebx, eax
0x18002c6ab  test    eax, eax
0x18002c6ad  js      loc_18002C79F
0x18002c6b3  mov     r9, [rsp+1940h+var_18D8]
0x18002c6b8  lea     r8, aInterfaceSProx; "Interface\\%s\\ProxyStubClsid32"
0x18002c6bf  mov     edx, 800h; unsigned __int64
0x18002c6c4  lea     rcx, [rbp+1840h+var_1040]; unsigned __int16 *
0x18002c6cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c6d0  xor     r8d, r8d
0x18002c6d3  mov     ebx, eax
0x18002c6d5  test    eax, eax
0x18002c6d7  js      loc_18002C79F
0x18002c6dd  mov     rdx, [rsp+1940h+var_18D8]
0x18002c6e2  mov     rax, rdx
0x18002c6e5  movzx   ecx, word ptr [rax]
0x18002c6e8  cmp     cx, 2Dh ; '-'
0x18002c6ec  jz      short loc_18002C6FA
0x18002c6ee  cmp     cx, 7Bh ; '{'
0x18002c6f2  jz      short loc_18002C6FA
0x18002c6f4  cmp     cx, 7Dh ; '}'
0x18002c6f8  jnz     short loc_18002C701
0x18002c6fa  add     rax, 2
0x18002c6fe  movzx   ecx, word ptr [rax]
0x18002c701  mov     [rdx], cx
0x18002c704  cmp     [rax], r8w
0x18002c708  jz      short loc_18002C714
0x18002c70a  add     rdx, 2
0x18002c70e  add     rax, 2
0x18002c712  jmp     short loc_18002C6E5
0x18002c714  mov     rax, [rsp+1940h+lpsz]
0x18002c719  lea     r9, word_18005C890; unsigned __int16 *
0x18002c720  mov     rdx, [rsp+1940h+var_18D8]; unsigned __int16 *
0x18002c725  lea     r8, [rbp+1840h+var_1040]; unsigned __int16 *
0x18002c72c  mov     qword ptr [rsp+1940h+dwFlagsAndAttributes], rsi; unsigned __int16 *
0x18002c731  mov     rcx, rdi; this
0x18002c734  mov     qword ptr [rsp+1940h+dwCreationDisposition], rax; unsigned __int16 *
0x18002c739  call    ?_AddRegKey@CGenerateMSI@@QEAAJPEBG0000@Z; CGenerateMSI::_AddRegKey(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002c73e  mov     ebx, eax
0x18002c740  test    eax, eax
0x18002c742  js      short loc_18002C79F
0x18002c744  mov     rcx, [rsp+1940h+var_18D8]; pv
0x18002c749  call    cs:__imp_CoTaskMemFree
0x18002c74f  inc     r14d
0x18002c752  mov     [rsp+1940h+var_18D8], 0
0x18002c75b  jmp     loc_18002C67C
0x18002c760  xor     r14d, r14d
0x18002c763  mov     rcx, r12; pv
0x18002c766  call    cs:__imp_CoTaskMemFree
0x18002c76c  mov     rcx, [rsp+1940h+lpsz]; pv
0x18002c771  mov     r12, r14
0x18002c774  mov     [rsp+1940h+pv], r14
0x18002c779  call    cs:__imp_CoTaskMemFree
0x18002c77f  mov     rcx, [rsp+1940h+var_18D8]; pv
0x18002c784  mov     [rsp+1940h+lpsz], r14
0x18002c789  call    cs:__imp_CoTaskMemFree
0x18002c78f  inc     r15d
0x18002c792  mov     [rsp+1940h+var_18D8], r14
0x18002c797  jmp     loc_18002C578
0x18002c79c  inc     dword ptr [rdi+50h]
0x18002c79f  mov     rcx, r12; pv
0x18002c7a2  call    cs:__imp_CoTaskMemFree
0x18002c7a8  mov     rcx, [rsp+1940h+lpsz]; pv
0x18002c7ad  call    cs:__imp_CoTaskMemFree
0x18002c7b3  mov     rcx, [rsp+1940h+var_18D8]; pv
0x18002c7b8  call    cs:__imp_CoTaskMemFree
0x18002c7be  mov     rcx, rsi; pv
0x18002c7c1  call    cs:__imp_CoTaskMemFree
0x18002c7c7  mov     rcx, [rbp+1840h+var_18C0]; pv
0x18002c7cb  call    cs:__imp_CoTaskMemFree
0x18002c7d1  mov     rcx, [rbp+1840h+var_18B8]; pv
0x18002c7d5  call    cs:__imp_CoTaskMemFree
0x18002c7db  mov     rcx, [rbp+1840h+var_18B0]; pv
0x18002c7df  call    cs:__imp_CoTaskMemFree
0x18002c7e5  mov     eax, ebx
0x18002c7e7  mov     rcx, [rbp+1840h+var_40]
0x18002c7ee  xor     rcx, rsp; StackCookie
0x18002c7f1  call    __security_check_cookie
0x18002c7f6  mov     rbx, [rsp+1940h+arg_18]
0x18002c7fe  add     rsp, 1910h
0x18002c805  pop     r15
0x18002c807  pop     r14
0x18002c809  pop     r13
  ... truncated ...
```
