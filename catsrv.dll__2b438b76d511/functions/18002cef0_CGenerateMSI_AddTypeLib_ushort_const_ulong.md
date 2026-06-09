# CGenerateMSI::AddTypeLib(ushort const *,ulong)

- ea: `0x18002cef0`
- end: `0x18002d31b`
- name: `?AddTypeLib@CGenerateMSI@@UEAAJPEBGK@Z`
- size: `1067`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000a01c`
- `0x18002cef0`
- `0x18002dda8`
- `0x18002deac`
- `0x18002e0c8`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002cf88`
- `msvcrt!wcsrchr` at `0x18002cf88`
- `msvcrt!wcsspn` at `0x18002cfa1`
- `msvcrt!wcsspn` at `0x18002cfa1`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18002cffa`
- `OLEAUT32!__imp_LoadTypeLibEx` at `0x18002cffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d12e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfcf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d10a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d10a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002cfc5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002cfc5`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d122`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002d122`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002d050`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002d050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d29a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d2ac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d03c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d06b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d03c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d06b`

## string_xrefs

- `0x18002d195`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002d23c`: `ComPlusFeature`
- `0x18002d228`: ``LibID`, `Language`, `Version`, `Description`, `Directory_`, `Feature_`, `Component_``

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddTypeLib(CGenerateMSI *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r13
  unsigned __int16 *v7; // r15
  unsigned __int16 *v8; // r12
  int inserted; // ebx
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  signed int LastError; // eax
  CGenerateMSI *v13; // rcx
  int v14; // eax
  HANDLE FileW; // rax
  void *v16; // rbx
  DWORD FileSize; // r14d
  CGenerateMSI *v18; // rcx
  CGenerateMSI *v19; // rcx
  int v20; // eax
  unsigned __int16 *v21; // rdx
  unsigned __int16 *v22; // rax
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  DWORD v26; // [rsp+38h] [rbp-C8h]
  int v27; // [rsp+58h] [rbp-A8h]
  GUID *rguid; // [rsp+60h] [rbp-A0h] BYREF
  ITypeLib *pptlib; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v30; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v31; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v32; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v33; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v34; // [rsp+90h] [rbp-70h] BYREF
  LPWSTR FilePart; // [rsp+98h] [rbp-68h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR v38[40]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t Str[264]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v40[264]; // [rsp+360h] [rbp+260h] BYREF
  WCHAR Buffer[264]; // [rsp+570h] [rbp+470h] BYREF

  v30 = a3;
  pptlib = 0;
  rguid = 0;
  FilePart = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  pguid = 0;
  v5 = 0;
  v33 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  if ( (int)StringCchCopyW(Str, 0x104u, a2) < 0 )
  {
    inserted = -2147024809;
    goto LABEL_29;
  }
  v10 = wcsrchr(Str, 0x5Cu);
  v11 = v10;
  if ( v10 && wcsspn(v10 + 1, L"0123456789") )
    *v11 = 0;
  if ( !GetFullPathNameW(Str, 0x104u, Buffer, &FilePart) )
    goto LABEL_7;
  inserted = LoadTypeLibEx(a2, REGKIND_NONE, &pptlib);
  if ( inserted < 0 )
    goto LABEL_29;
  inserted = ((__int64 (__fastcall *)(ITypeLib *, GUID **))pptlib->lpVtbl->GetLibAttr)(pptlib, &rguid);
  if ( inserted < 0 )
    goto LABEL_29;
  inserted = StringFromGUID2(rguid, sz, 40);
  if ( inserted < 0 )
    goto LABEL_29;
  inserted = CoCreateGuid(&pguid);
  if ( inserted < 0 )
    goto LABEL_29;
  inserted = StringFromGUID2(&pguid, v38, 40);
  if ( inserted < 0 )
    goto LABEL_29;
  inserted = StringCchPrintfW(v40, 0x104u, L"TLB_%sXxX%s", sz, v38);
  if ( inserted < 0 )
    goto LABEL_29;
  v14 = CGenerateMSI::GenerateIdentifier(v13, &v34, v40);
  v5 = v34;
  inserted = v14;
  if ( v14 < 0 )
    goto LABEL_29;
  inserted = CGenerateMSI::_InsertComponent(this, v34, sz, *((_DWORD *)this + 162));
  if ( inserted < 0 )
    goto LABEL_29;
  FileW = CreateFileW(Str, 0x80000000, 1u, 0, 3u, 0, 0);
  v16 = FileW;
  if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, 0), CloseHandle(v16), FileSize == -1) )
  {
LABEL_7:
    LastError = GetLastError();
    inserted = LastError;
    if ( LastError > 0 )
      inserted = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    CGenerateMSI::GenerateMSIFileVerAndLocale(v18, Str, &v32, &v33);
    v20 = CGenerateMSI::GenerateMSIFileName(v19, Str, &v31);
    v8 = v33;
    inserted = v20;
    v7 = v32;
    if ( v20 < 0 )
    {
      v6 = v31;
    }
    else
    {
      v21 = L"0";
      v22 = L"1.1.1.2";
      v6 = v31;
      if ( v33 )
        v21 = v33;
      if ( v32 )
        v22 = v32;
      v26 = FileSize;
      v27 = *((_DWORD *)this + 20);
      inserted = CGenerateMSI::_InsertRow(
                   this,
                   L"File",
                   L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                   L"'%s', '%s', '%s', %ld, '%s', '%s', %d, %d",
                   v5,
                   v5,
                   v31,
                   v26,
                   v22,
                   v21,
                   0,
                   v27);
      if ( inserted >= 0 )
      {
        inserted = CGenerateMSI::_GetMakeCab(this, v30);
        if ( inserted >= 0 )
        {
          inserted = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 77) + 32LL))(
                       *((_QWORD *)this + 77),
                       Str,
                       v5);
          if ( inserted >= 0 )
          {
            LODWORD(hTemplateFile) = *(unsigned __int16 *)&rguid[1].Data4[2]
                                   + (*(unsigned __int16 *)rguid[1].Data4 << 8);
            dwFlagsAndAttributes[0] = rguid[1].Data1;
            inserted = CGenerateMSI::_InsertRow(
                         this,
                         L"`TypeLib`",
                         L"`LibID`, `Language`, `Version`, `Description`, `Directory_`, `Feature_`, `Component_`",
                         L"'%s', %d, %d, '%s', '%s', '%s', '%s'",
                         sz,
                         *(_QWORD *)dwFlagsAndAttributes,
                         hTemplateFile,
                         FilePart,
                         *((_QWORD *)this + 9),
                         L"ComPlusFeature",
                         v5);
          }
        }
      }
    }
  }
LABEL_29:
  CoTaskMemFree(v5);
  CoTaskMemFree(0);
  CoTaskMemFree(v6);
  CoTaskMemFree(v7);
  CoTaskMemFree(v8);
  if ( rguid )
  {
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->ReleaseTLibAttr)(pptlib);
    rguid = 0;
  }
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  ++*((_DWORD *)this + 20);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002cef0  mov     [rsp-8+arg_18], rbx
0x18002cef5  push    rbp
0x18002cef6  push    rsi
0x18002cef7  push    rdi
0x18002cef8  push    r12
0x18002cefa  push    r13
0x18002cefc  push    r14
0x18002cefe  push    r15
0x18002cf00  lea     rbp, [rsp-690h]
0x18002cf08  sub     rsp, 790h
0x18002cf0f  mov     rax, cs:__security_cookie
0x18002cf16  xor     rax, rsp
0x18002cf19  mov     [rbp+6C0h+var_40], rax
0x18002cf20  xor     r11d, r11d
0x18002cf23  mov     [rsp+7C0h+var_750], r8d
0x18002cf28  mov     r8, rdx; unsigned __int16 *
0x18002cf2b  mov     [rsp+7C0h+pptlib], r11
0x18002cf30  mov     r14, rdx
0x18002cf33  mov     [rsp+7C0h+rguid], r11
0x18002cf38  mov     rdi, rcx
0x18002cf3b  mov     [rbp+6C0h+FilePart], r11
0x18002cf3f  xorps   xmm0, xmm0
0x18002cf42  mov     [rbp+6C0h+var_730], r11
0x18002cf46  mov     edx, 104h; unsigned __int64
0x18002cf4b  mov     [rsp+7C0h+var_748], r11
0x18002cf50  lea     rcx, [rbp+6C0h+Str]; unsigned __int16 *
0x18002cf54  mov     [rbp+6C0h+var_740], r11
0x18002cf58  movups  xmmword ptr [rbp+6C0h+pguid.Data1], xmm0
0x18002cf5c  mov     esi, r11d
0x18002cf5f  mov     [rbp+6C0h+var_738], r11
0x18002cf63  mov     r13d, r11d
0x18002cf66  mov     r15d, r11d
0x18002cf69  mov     r12d, r11d
0x18002cf6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cf71  test    eax, eax
0x18002cf73  jns     short loc_18002CF7F
0x18002cf75  mov     ebx, 80070057h
0x18002cf7a  jmp     loc_18002D286
0x18002cf7f  mov     edx, 5Ch ; '\'; Ch
0x18002cf84  lea     rcx, [rbp+6C0h+Str]; Str
0x18002cf88  call    cs:__imp_wcsrchr
0x18002cf8e  mov     rbx, rax
0x18002cf91  test    rax, rax
0x18002cf94  jz      short loc_18002CFB1
0x18002cf96  lea     rcx, [rax+2]; String
0x18002cf9a  lea     rdx, a0123456789; "0123456789"
0x18002cfa1  call    cs:__imp_wcsspn
0x18002cfa7  test    rax, rax
0x18002cfaa  jz      short loc_18002CFB1
0x18002cfac  xor     ecx, ecx
0x18002cfae  mov     [rbx], cx
0x18002cfb1  lea     r9, [rbp+6C0h+FilePart]; lpFilePart
0x18002cfb5  mov     edx, 104h; nBufferLength
0x18002cfba  lea     r8, [rbp+6C0h+Buffer]; lpBuffer
0x18002cfc1  lea     rcx, [rbp+6C0h+Str]; lpFileName
0x18002cfc5  call    cs:__imp_GetFullPathNameW
0x18002cfcb  test    eax, eax
0x18002cfcd  jnz     short loc_18002CFED
0x18002cfcf  call    cs:__imp_GetLastError
0x18002cfd5  mov     ebx, eax
0x18002cfd7  test    eax, eax
0x18002cfd9  jle     loc_18002D286
0x18002cfdf  movzx   ebx, ax
0x18002cfe2  or      ebx, 80070000h
0x18002cfe8  jmp     loc_18002D286
0x18002cfed  lea     r8, [rsp+7C0h+pptlib]; pptlib
0x18002cff2  mov     edx, 2; regkind
0x18002cff7  mov     rcx, r14; szFile
0x18002cffa  call    cs:__imp_LoadTypeLibEx
0x18002d000  mov     ebx, eax
0x18002d002  test    eax, eax
0x18002d004  js      loc_18002D286
0x18002d00a  mov     rcx, [rsp+7C0h+pptlib]
0x18002d00f  lea     rdx, [rsp+7C0h+rguid]
0x18002d014  mov     rax, [rcx]
0x18002d017  mov     rax, [rax+38h]
0x18002d01b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d020  mov     ebx, eax
0x18002d022  test    eax, eax
0x18002d024  js      loc_18002D286
0x18002d02a  mov     rcx, [rsp+7C0h+rguid]; rguid
0x18002d02f  lea     rdx, [rbp+6C0h+sz]; lpsz
0x18002d033  mov     r14d, 28h ; '('
0x18002d039  mov     r8d, r14d; cchMax
0x18002d03c  call    cs:__imp_StringFromGUID2
0x18002d042  mov     ebx, eax
0x18002d044  test    eax, eax
0x18002d046  js      loc_18002D286
0x18002d04c  lea     rcx, [rbp+6C0h+pguid]; pguid
0x18002d050  call    cs:__imp_CoCreateGuid
0x18002d056  mov     ebx, eax
0x18002d058  test    eax, eax
0x18002d05a  js      loc_18002D286
0x18002d060  mov     r8d, r14d; cchMax
0x18002d063  lea     rdx, [rbp+6C0h+var_6C0]; lpsz
0x18002d067  lea     rcx, [rbp+6C0h+pguid]; rguid
0x18002d06b  call    cs:__imp_StringFromGUID2
0x18002d071  mov     ebx, eax
0x18002d073  test    eax, eax
0x18002d075  js      loc_18002D286
0x18002d07b  lea     rax, [rbp+6C0h+var_6C0]
0x18002d07f  mov     edx, 104h; unsigned __int64
0x18002d084  lea     r9, [rbp+6C0h+sz]
0x18002d088  mov     qword ptr [rsp+7C0h+dwCreationDisposition], rax
0x18002d08d  lea     r8, aTlbSxxxS; "TLB_%sXxX%s"
0x18002d094  lea     rcx, [rbp+6C0h+var_460]; unsigned __int16 *
0x18002d09b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d0a0  mov     ebx, eax
0x18002d0a2  test    eax, eax
0x18002d0a4  js      loc_18002D286
0x18002d0aa  lea     r8, [rbp+6C0h+var_460]; unsigned __int16 *
0x18002d0b1  lea     rdx, [rbp+6C0h+var_730]; unsigned __int16 **
0x18002d0b5  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002d0ba  mov     rsi, [rbp+6C0h+var_730]
0x18002d0be  mov     ebx, eax
0x18002d0c0  test    eax, eax
0x18002d0c2  js      loc_18002D286
0x18002d0c8  mov     r9d, [rdi+288h]; unsigned int
0x18002d0cf  lea     r8, [rbp+6C0h+sz]; unsigned __int16 *
0x18002d0d3  mov     rdx, rsi; unsigned __int16 *
0x18002d0d6  mov     rcx, rdi; this
0x18002d0d9  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002d0de  mov     ebx, eax
0x18002d0e0  test    eax, eax
0x18002d0e2  js      loc_18002D286
0x18002d0e8  mov     [rsp+7C0h+hTemplateFile], r12; hTemplateFile
0x18002d0ed  lea     r8d, [r14-27h]; dwShareMode
0x18002d0f1  mov     [rsp+7C0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002d0f6  lea     rcx, [rbp+6C0h+Str]; lpFileName
0x18002d0fa  xor     r9d, r9d; lpSecurityAttributes
0x18002d0fd  mov     [rsp+7C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d105  mov     edx, 80000000h; dwDesiredAccess
0x18002d10a  call    cs:__imp_CreateFileW
0x18002d110  mov     rbx, rax
0x18002d113  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d117  jz      loc_18002CFCF
0x18002d11d  xor     edx, edx; lpFileSizeHigh
0x18002d11f  mov     rcx, rax; hFile
0x18002d122  call    cs:__imp_GetFileSize
0x18002d128  mov     rcx, rbx; hObject
0x18002d12b  mov     r14d, eax
0x18002d12e  call    cs:__imp_CloseHandle
0x18002d134  cmp     r14d, 0FFFFFFFFh
0x18002d138  jz      loc_18002CFCF
0x18002d13e  lea     r9, [rbp+6C0h+var_738]; unsigned __int16 **
0x18002d142  lea     r8, [rbp+6C0h+var_740]; unsigned __int16 **
0x18002d146  lea     rdx, [rbp+6C0h+Str]; unsigned __int16 *
0x18002d14a  call    ?GenerateMSIFileVerAndLocale@CGenerateMSI@@AEAAJPEAGPEAPEAG1@Z; CGenerateMSI::GenerateMSIFileVerAndLocale(ushort *,ushort * *,ushort * *)
0x18002d14f  lea     r8, [rsp+7C0h+var_748]; unsigned __int16 **
0x18002d154  lea     rdx, [rbp+6C0h+Str]; unsigned __int16 *
0x18002d158  call    ?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z; CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)
0x18002d15d  mov     r12, [rbp+6C0h+var_738]
0x18002d161  mov     ebx, eax
0x18002d163  mov     r15, [rbp+6C0h+var_740]
0x18002d167  test    eax, eax
0x18002d169  js      loc_18002D281
0x18002d16f  mov     ecx, [rdi+50h]
0x18002d172  lea     rdx, Default; "0"
0x18002d179  mov     [rsp+7C0h+var_768], ecx
0x18002d17d  lea     rax, a1112; "1.1.1.2"
0x18002d184  mov     [rsp+7C0h+var_770], r13
0x18002d189  lea     r9, aSSSLdSSDD; "'%s', '%s', '%s', %ld, '%s', '%s', %d, "...
0x18002d190  mov     r13, [rsp+7C0h+var_748]
0x18002d195  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002d19c  test    r12, r12
0x18002d19f  mov     rcx, rdi; this
0x18002d1a2  cmovnz  rdx, r12
0x18002d1a6  test    r15, r15
0x18002d1a9  mov     [rsp+7C0h+var_778], rdx
0x18002d1ae  lea     rdx, aFile_0; "File"
0x18002d1b5  cmovnz  rax, r15
0x18002d1b9  mov     [rsp+7C0h+var_780], rax
0x18002d1be  mov     dword ptr [rsp+7C0h+var_788], r14d
0x18002d1c3  mov     [rsp+7C0h+hTemplateFile], r13
0x18002d1c8  mov     qword ptr [rsp+7C0h+dwFlagsAndAttributes], rsi
0x18002d1cd  mov     qword ptr [rsp+7C0h+dwCreationDisposition], rsi
0x18002d1d2  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002d1d7  mov     ebx, eax
0x18002d1d9  test    eax, eax
0x18002d1db  js      loc_18002D286
0x18002d1e1  mov     edx, [rsp+7C0h+var_750]; unsigned int
0x18002d1e5  mov     rcx, rdi; this
0x18002d1e8  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002d1ed  mov     ebx, eax
0x18002d1ef  test    eax, eax
0x18002d1f1  js      loc_18002D286
0x18002d1f7  mov     rcx, [rdi+268h]
0x18002d1fe  lea     rdx, [rbp+6C0h+Str]
0x18002d202  mov     r8, rsi
0x18002d205  mov     rax, [rcx]
0x18002d208  mov     rax, [rax+20h]
0x18002d20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d211  mov     ebx, eax
0x18002d213  test    eax, eax
0x18002d215  js      short loc_18002D286
0x18002d217  mov     rdx, [rsp+7C0h+rguid]
0x18002d21c  lea     r9, aSDDSSSS; "'%s', %d, %d, '%s', '%s', '%s', '%s'"
0x18002d223  mov     [rsp+7C0h+var_770], rsi
0x18002d228  lea     r8, aLibidLanguageV; "`LibID`, `Language`, `Version`, `Descri"...
0x18002d22f  movzx   ecx, word ptr [rdx+18h]
0x18002d233  movzx   eax, word ptr [rdx+1Ah]
0x18002d237  shl     ecx, 8
0x18002d23a  add     ecx, eax
0x18002d23c  lea     rax, aComplusfeature; "ComPlusFeature"
0x18002d243  mov     [rsp+7C0h+var_778], rax
0x18002d248  mov     rax, [rdi+48h]
0x18002d24c  mov     [rsp+7C0h+var_780], rax
0x18002d251  mov     rax, [rbp+6C0h+FilePart]
0x18002d255  mov     [rsp+7C0h+var_788], rax
0x18002d25a  mov     eax, [rdx+10h]
0x18002d25d  lea     rdx, aTypelib; "`TypeLib`"
0x18002d264  mov     dword ptr [rsp+7C0h+hTemplateFile], ecx
0x18002d268  mov     rcx, rdi; this
0x18002d26b  mov     [rsp+7C0h+dwFlagsAndAttributes], eax
0x18002d26f  lea     rax, [rbp+6C0h+sz]
0x18002d273  mov     qword ptr [rsp+7C0h+dwCreationDisposition], rax
0x18002d278  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002d27d  mov     ebx, eax
0x18002d27f  jmp     short loc_18002D286
0x18002d281  mov     r13, [rsp+7C0h+var_748]
0x18002d286  mov     rcx, rsi; pv
0x18002d289  call    cs:__imp_CoTaskMemFree
0x18002d28f  xor     ecx, ecx; pv
0x18002d291  call    cs:__imp_CoTaskMemFree
0x18002d297  mov     rcx, r13; pv
0x18002d29a  call    cs:__imp_CoTaskMemFree
0x18002d2a0  mov     rcx, r15; pv
0x18002d2a3  call    cs:__imp_CoTaskMemFree
0x18002d2a9  mov     rcx, r12; pv
0x18002d2ac  call    cs:__imp_CoTaskMemFree
0x18002d2b2  mov     rdx, [rsp+7C0h+rguid]
0x18002d2b7  test    rdx, rdx
0x18002d2ba  jz      short loc_18002D2D6
0x18002d2bc  mov     rcx, [rsp+7C0h+pptlib]
0x18002d2c1  mov     rax, [rcx]
0x18002d2c4  mov     rax, [rax+60h]
0x18002d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2cd  mov     [rsp+7C0h+rguid], 0
0x18002d2d6  mov     rcx, [rsp+7C0h+pptlib]
0x18002d2db  test    rcx, rcx
0x18002d2de  jz      short loc_18002D2EC
0x18002d2e0  mov     rax, [rcx]
0x18002d2e3  mov     rax, [rax+10h]
0x18002d2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2ec  inc     dword ptr [rdi+50h]
0x18002d2ef  mov     eax, ebx
0x18002d2f1  mov     rcx, [rbp+6C0h+var_40]
0x18002d2f8  xor     rcx, rsp; StackCookie
0x18002d2fb  call    __security_check_cookie
0x18002d300  mov     rbx, [rsp+7C0h+arg_18]
0x18002d308  add     rsp, 790h
0x18002d30f  pop     r15
0x18002d311  pop     r14
0x18002d313  pop     r13
0x18002d315  pop     r12
0x18002d317  pop     rdi
0x18002d318  pop     rsi
0x18002d319  pop     rbp
0x18002d31a  retn
```
