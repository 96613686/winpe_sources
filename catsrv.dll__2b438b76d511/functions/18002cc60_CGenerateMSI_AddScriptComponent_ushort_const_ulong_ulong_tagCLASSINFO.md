# CGenerateMSI::AddScriptComponent(ushort const *,ulong,ulong,_tagCLASSINFO *)

- ea: `0x18002cc60`
- end: `0x18002cee7`
- name: `?AddScriptComponent@CGenerateMSI@@UEAAJPEBGKKPEAU_tagCLASSINFO@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(CGenerateMSI *this, const unsigned __int16 *, unsigned int, __int64, IID *rclsid)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000be28`
- `0x18002cc60`
- `0x18002dda8`
- `0x18002deac`
- `0x18002e708`
- `0x18002e888`
- `0x18002e91c`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cde2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002cde2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cdbe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002cdbe`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002cce6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002cce6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002cdd6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002cdd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ceb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cebb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cd90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ce9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cea7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ceb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002cebb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002cd16`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002cd16`

## string_xrefs

- `0x18002ce19`: `File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence`
- `0x18002cd2e`: `Dll_%s`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::AddScriptComponent(
        CGenerateMSI *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        IID *rclsid)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r12
  int inserted; // ebx
  signed int LastError; // eax
  CGenerateMSI *v11; // rcx
  int v12; // eax
  HANDLE FileW; // rax
  void *v14; // rbx
  DWORD FileSize; // r15d
  CGenerateMSI *v16; // rcx
  LPOLESTR lpsz; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v20; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v21; // [rsp+78h] [rbp-88h] BYREF
  LPWSTR FilePart; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  lpFileName = 0;
  FilePart = 0;
  v6 = 0;
  lpsz = 0;
  v7 = 0;
  v21 = 0;
  v20 = 0;
  inserted = IsLocalPath(a2, (unsigned __int16 **)&lpFileName);
  if ( !inserted )
  {
    if ( !GetFullPathNameW(lpFileName, 0x104u, Buffer, &FilePart) )
      goto LABEL_3;
    inserted = StringFromCLSID(rclsid, &lpsz);
    if ( inserted < 0 )
      goto LABEL_16;
    inserted = StringCchPrintfW(v23, 0x104u, L"Dll_%s", lpsz);
    if ( inserted < 0 )
      goto LABEL_16;
    v12 = CGenerateMSI::GenerateIdentifier(v11, &v21, v23);
    v6 = v21;
    inserted = v12;
    if ( v12 < 0 )
      goto LABEL_16;
    inserted = CGenerateMSI::_InsertComponent(this, v21, lpsz, *((_DWORD *)this + 162));
    if ( inserted < 0 )
      goto LABEL_16;
    CoTaskMemFree(lpsz);
    lpsz = 0;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
    v14 = FileW;
    if ( FileW == (HANDLE)-1LL || (FileSize = GetFileSize(FileW, 0), CloseHandle(v14), FileSize == -1) )
    {
LABEL_3:
      LastError = GetLastError();
      inserted = LastError;
      if ( LastError > 0 )
        inserted = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      inserted = CGenerateMSI::GenerateMSIFileName(v16, (unsigned __int16 *)lpFileName, &v20);
      if ( inserted < 0 )
      {
        v7 = v20;
      }
      else
      {
        v7 = v20;
        inserted = CGenerateMSI::_InsertRow(
                     this,
                     L"File",
                     L"File, Component_, FileName, FileSize, Version, Language, Attributes, Sequence",
                     L"'%s', '%s', '%s', %ld, '%s', %d, %d, %d",
                     v6,
                     v6,
                     v20,
                     FileSize,
                     L"1.1.1.1",
                     0,
                     0,
                     *((_DWORD *)this + 20));
        if ( inserted >= 0 )
        {
          inserted = CGenerateMSI::_GetMakeCab(this, a3);
          if ( inserted >= 0 )
            inserted = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, unsigned __int16 *))(**((_QWORD **)this + 77) + 32LL))(
                         *((_QWORD *)this + 77),
                         lpFileName,
                         v6);
        }
      }
    }
  }
LABEL_16:
  CoTaskMemFree(lpsz);
  CoTaskMemFree(v6);
  CoTaskMemFree((LPVOID)lpFileName);
  CoTaskMemFree(v7);
  ++*((_DWORD *)this + 20);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18002cc60  push    rbp
0x18002cc62  push    rbx
0x18002cc63  push    rsi
0x18002cc64  push    rdi
0x18002cc65  push    r12
0x18002cc67  push    r13
0x18002cc69  push    r15
0x18002cc6b  lea     rbp, [rsp-3C0h]
0x18002cc73  sub     rsp, 4C0h
0x18002cc7a  mov     rax, cs:__security_cookie
0x18002cc81  xor     rax, rsp
0x18002cc84  mov     [rbp+3F0h+var_40], rax
0x18002cc8b  mov     r15, [rbp+3F0h+rclsid]
0x18002cc92  mov     rdi, rcx
0x18002cc95  xor     ecx, ecx
0x18002cc97  mov     rax, rdx
0x18002cc9a  mov     [rsp+4F0h+lpFileName], rcx
0x18002cc9f  lea     rdx, [rsp+4F0h+lpFileName]; unsigned __int16 **
0x18002cca4  mov     [rbp+3F0h+FilePart], rcx
0x18002cca8  mov     esi, ecx
0x18002ccaa  mov     [rsp+4F0h+lpsz], rcx
0x18002ccaf  mov     r12d, ecx
0x18002ccb2  mov     [rsp+4F0h+var_478], rcx
0x18002ccb7  mov     r13d, r8d
0x18002ccba  mov     [rsp+4F0h+var_480], rcx
0x18002ccbf  mov     rcx, rax; unsigned __int16 *
0x18002ccc2  call    ?IsLocalPath@@YAJPEBGPEAPEAG@Z; IsLocalPath(ushort const *,ushort * *)
0x18002ccc7  mov     ebx, eax
0x18002ccc9  test    eax, eax
0x18002cccb  jnz     loc_18002CE99
0x18002ccd1  mov     rcx, [rsp+4F0h+lpFileName]; lpFileName
0x18002ccd6  lea     r9, [rbp+3F0h+FilePart]; lpFilePart
0x18002ccda  lea     r8, [rbp+3F0h+Buffer]; lpBuffer
0x18002cce1  mov     edx, 104h; nBufferLength
0x18002cce6  call    cs:__imp_GetFullPathNameW
0x18002ccec  test    eax, eax
0x18002ccee  jnz     short loc_18002CD0E
0x18002ccf0  call    cs:__imp_GetLastError
0x18002ccf6  mov     ebx, eax
0x18002ccf8  test    eax, eax
0x18002ccfa  jle     loc_18002CE99
0x18002cd00  movzx   ebx, ax
0x18002cd03  or      ebx, 80070000h
0x18002cd09  jmp     loc_18002CE99
0x18002cd0e  lea     rdx, [rsp+4F0h+lpsz]; lplpsz
0x18002cd13  mov     rcx, r15; rclsid
0x18002cd16  call    cs:__imp_StringFromCLSID
0x18002cd1c  xor     r15d, r15d
0x18002cd1f  mov     ebx, eax
0x18002cd21  test    eax, eax
0x18002cd23  js      loc_18002CE99
0x18002cd29  mov     r9, [rsp+4F0h+lpsz]
0x18002cd2e  lea     r8, aDllS; "Dll_%s"
0x18002cd35  mov     edx, 104h; unsigned __int64
0x18002cd3a  lea     rcx, [rbp+3F0h+var_460]; unsigned __int16 *
0x18002cd3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002cd43  mov     ebx, eax
0x18002cd45  test    eax, eax
0x18002cd47  js      loc_18002CE99
0x18002cd4d  lea     r8, [rbp+3F0h+var_460]; unsigned __int16 *
0x18002cd51  lea     rdx, [rsp+4F0h+var_478]; unsigned __int16 **
0x18002cd56  call    ?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z; CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)
0x18002cd5b  mov     rsi, [rsp+4F0h+var_478]
0x18002cd60  mov     ebx, eax
0x18002cd62  test    eax, eax
0x18002cd64  js      loc_18002CE99
0x18002cd6a  mov     r9d, [rdi+288h]; unsigned int
0x18002cd71  mov     rdx, rsi; unsigned __int16 *
0x18002cd74  mov     r8, [rsp+4F0h+lpsz]; unsigned __int16 *
0x18002cd79  mov     rcx, rdi; this
0x18002cd7c  call    ?_InsertComponent@CGenerateMSI@@QEAAJPEBG0K@Z; CGenerateMSI::_InsertComponent(ushort const *,ushort const *,ulong)
0x18002cd81  mov     ebx, eax
0x18002cd83  test    eax, eax
0x18002cd85  js      loc_18002CE99
0x18002cd8b  mov     rcx, [rsp+4F0h+lpsz]; pv
0x18002cd90  call    cs:__imp_CoTaskMemFree
0x18002cd96  mov     rcx, [rsp+4F0h+lpFileName]; lpFileName
0x18002cd9b  lea     r8d, [r15+1]; dwShareMode
0x18002cd9f  mov     [rsp+4F0h+hTemplateFile], r15; hTemplateFile
0x18002cda4  xor     r9d, r9d; lpSecurityAttributes
0x18002cda7  mov     [rsp+4F0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18002cdac  mov     edx, 80000000h; dwDesiredAccess
0x18002cdb1  mov     [rsp+4F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002cdb9  mov     [rsp+4F0h+lpsz], r15
0x18002cdbe  call    cs:__imp_CreateFileW
0x18002cdc4  mov     rbx, rax
0x18002cdc7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002cdcb  jz      loc_18002CCF0
0x18002cdd1  xor     edx, edx; lpFileSizeHigh
0x18002cdd3  mov     rcx, rax; hFile
0x18002cdd6  call    cs:__imp_GetFileSize
0x18002cddc  mov     rcx, rbx; hObject
0x18002cddf  mov     r15d, eax
0x18002cde2  call    cs:__imp_CloseHandle
0x18002cde8  cmp     r15d, 0FFFFFFFFh
0x18002cdec  jz      loc_18002CCF0
0x18002cdf2  mov     rdx, [rsp+4F0h+lpFileName]; unsigned __int16 *
0x18002cdf7  lea     r8, [rsp+4F0h+var_480]; unsigned __int16 **
0x18002cdfc  call    ?GenerateMSIFileName@CGenerateMSI@@AEAAJPEAGPEAPEAG@Z; CGenerateMSI::GenerateMSIFileName(ushort *,ushort * *)
0x18002ce01  mov     ebx, eax
0x18002ce03  test    eax, eax
0x18002ce05  js      loc_18002CE94
0x18002ce0b  mov     eax, [rdi+50h]
0x18002ce0e  lea     r9, aSSSLdSDDD; "'%s', '%s', '%s', %ld, '%s', %d, %d, %d"
0x18002ce15  mov     [rsp+4F0h+var_498], eax
0x18002ce19  lea     r8, aFileComponentF; "File, Component_, FileName, FileSize, V"...
0x18002ce20  mov     [rsp+4F0h+var_4A0], r12
0x18002ce25  lea     rax, a1111; "1.1.1.1"
0x18002ce2c  mov     [rsp+4F0h+var_4A8], r12
0x18002ce31  lea     rdx, aFile_0; "File"
0x18002ce38  mov     r12, [rsp+4F0h+var_480]
0x18002ce3d  mov     rcx, rdi; this
0x18002ce40  mov     [rsp+4F0h+var_4B0], rax
0x18002ce45  mov     [rsp+4F0h+var_4B8], r15d
0x18002ce4a  mov     [rsp+4F0h+hTemplateFile], r12
0x18002ce4f  mov     qword ptr [rsp+4F0h+dwFlagsAndAttributes], rsi
0x18002ce54  mov     qword ptr [rsp+4F0h+dwCreationDisposition], rsi
0x18002ce59  call    ?_InsertRow@CGenerateMSI@@QEAAJPEBG00ZZ; CGenerateMSI::_InsertRow(ushort const *,ushort const *,ushort const *,...)
0x18002ce5e  mov     ebx, eax
0x18002ce60  test    eax, eax
0x18002ce62  js      short loc_18002CE99
0x18002ce64  mov     edx, r13d; unsigned int
0x18002ce67  mov     rcx, rdi; this
0x18002ce6a  call    ?_GetMakeCab@CGenerateMSI@@QEAAJK@Z; CGenerateMSI::_GetMakeCab(ulong)
0x18002ce6f  mov     ebx, eax
0x18002ce71  test    eax, eax
0x18002ce73  js      short loc_18002CE99
0x18002ce75  mov     rcx, [rdi+268h]
0x18002ce7c  mov     r8, rsi
0x18002ce7f  mov     rdx, [rsp+4F0h+lpFileName]
0x18002ce84  mov     rax, [rcx]
0x18002ce87  mov     rax, [rax+20h]
0x18002ce8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce90  mov     ebx, eax
0x18002ce92  jmp     short loc_18002CE99
0x18002ce94  mov     r12, [rsp+4F0h+var_480]
0x18002ce99  mov     rcx, [rsp+4F0h+lpsz]; pv
0x18002ce9e  call    cs:__imp_CoTaskMemFree
0x18002cea4  mov     rcx, rsi; pv
0x18002cea7  call    cs:__imp_CoTaskMemFree
0x18002cead  mov     rcx, [rsp+4F0h+lpFileName]; pv
0x18002ceb2  call    cs:__imp_CoTaskMemFree
0x18002ceb8  mov     rcx, r12; pv
0x18002cebb  call    cs:__imp_CoTaskMemFree
0x18002cec1  inc     dword ptr [rdi+50h]
0x18002cec4  mov     eax, ebx
0x18002cec6  mov     rcx, [rbp+3F0h+var_40]
0x18002cecd  xor     rcx, rsp; StackCookie
0x18002ced0  call    __security_check_cookie
0x18002ced5  add     rsp, 4C0h
0x18002cedc  pop     r15
0x18002cede  pop     r13
0x18002cee0  pop     r12
0x18002cee2  pop     rdi
0x18002cee3  pop     rsi
0x18002cee4  pop     rbx
0x18002cee5  pop     rbp
0x18002cee6  retn
```
