# myIsDirWriteable(ushort const *,int)

- ea: `0x18001673c`
- end: `0x180016819`
- name: `?myIsDirWriteable@@YAJPEBGH@Z`
- size: `221`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016364`

## callees

- `0x180008610`
- `0x180012450`
- `0x18001673c`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167cd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800167cd`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800167a4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800167a4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180016774`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180016774`

## pseudocode

```c
__int64 __fastcall myIsDirWriteable(WCHAR *a1)
{
  unsigned int v1; // ebx
  int v3; // eax
  unsigned int v4; // edx
  WCHAR *v5; // rcx
  int v6; // r9d
  LPWSTR FilePart; // [rsp+20h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR TempFileName[264]; // [rsp+240h] [rbp-228h] BYREF

  v1 = 0;
  FilePart = 0;
  if ( !GetFullPathNameW(a1, 0x104u, Buffer, &FilePart) )
  {
    v3 = myHLastError();
    v4 = 43778450;
    v5 = a1;
LABEL_7:
    v6 = 0;
    goto LABEL_8;
  }
  if ( !GetTempFileNameW(Buffer, L"cert", 0, TempFileName) )
  {
    v3 = myHLastError();
    v6 = -2147024891;
    v5 = Buffer;
    v4 = 45810066;
LABEL_8:
    v1 = v3;
    CSPrintErrorLineFileData2(v5, v4, v3, v6);
    return v1;
  }
  if ( !DeleteFileW(TempFileName) )
  {
    v3 = myHLastError();
    v4 = 46203282;
    v5 = TempFileName;
    goto LABEL_7;
  }
  return v1;
}

```

## disassembly

```asm
0x18001673c  mov     [rsp+arg_8], rbx
0x180016741  push    rdi
0x180016742  sub     rsp, 460h
0x180016749  mov     rax, cs:__security_cookie
0x180016750  xor     rax, rsp
0x180016753  mov     [rsp+468h+var_18], rax
0x18001675b  xor     ebx, ebx
0x18001675d  lea     r9, [rsp+468h+FilePart]; lpFilePart
0x180016762  lea     r8, [rsp+468h+Buffer]; lpBuffer
0x180016767  mov     [rsp+468h+FilePart], rbx
0x18001676c  mov     edx, 104h; nBufferLength
0x180016771  mov     rdi, rcx
0x180016774  call    cs:__imp_GetFullPathNameW
0x18001677a  test    eax, eax
0x18001677c  jnz     short loc_18001678D
0x18001677e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180016783  mov     edx, 29C0192h
0x180016788  mov     rcx, rdi
0x18001678b  jmp     short loc_1800167E9
0x18001678d  lea     r9, [rsp+468h+TempFileName]; lpTempFileName
0x180016795  xor     r8d, r8d; uUnique
0x180016798  lea     rdx, PrefixString; "cert"
0x18001679f  lea     rcx, [rsp+468h+Buffer]; lpPathName
0x1800167a4  call    cs:__imp_GetTempFileNameW
0x1800167aa  test    eax, eax
0x1800167ac  jnz     short loc_1800167C5
0x1800167ae  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800167b3  mov     r9d, 80070005h
0x1800167b9  lea     rcx, [rsp+468h+Buffer]
0x1800167be  mov     edx, 2BB0192h
0x1800167c3  jmp     short loc_1800167EC
0x1800167c5  lea     rcx, [rsp+468h+TempFileName]; lpFileName
0x1800167cd  call    cs:__imp_DeleteFileW
0x1800167d3  test    eax, eax
0x1800167d5  jnz     short loc_1800167F6
0x1800167d7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800167dc  mov     edx, 2C10192h; unsigned int
0x1800167e1  lea     rcx, [rsp+468h+TempFileName]; unsigned __int16 *
0x1800167e9  xor     r9d, r9d; int
0x1800167ec  mov     r8d, eax; int
0x1800167ef  mov     ebx, eax
0x1800167f1  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800167f6  mov     eax, ebx
0x1800167f8  mov     rcx, [rsp+468h+var_18]
0x180016800  xor     rcx, rsp; StackCookie
0x180016803  call    __security_check_cookie
0x180016808  mov     rbx, [rsp+468h+arg_8]
0x180016810  add     rsp, 460h
0x180016817  pop     rdi
0x180016818  retn
```
