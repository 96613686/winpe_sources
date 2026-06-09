# CRtfToHtmlConverter::StringRtfToStringHtml(char *,void * *)

- ea: `0x18087bd3c`
- end: `0x18087c100`
- name: `?StringRtfToStringHtml@CRtfToHtmlConverter@@IEAAJPEADPEAPEAX@Z`
- size: `964`
- prototype: `__int64 __fastcall(CRtfToHtmlConverter *__hidden this, char *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180805db4`

## callees

- `0x18040ac58`
- `0x18087af4c`
- `0x18087b30c`
- `0x18087bd3c`
- `0x1810f6516`
- `0x1810f656a`
- `0x1810f65c0`

## import_xrefs

- `msvcrt!strchr` at `0x18087bf99`
- `msvcrt!strchr` at `0x18087bfcd`
- `msvcrt!strchr` at `0x18087bff3`
- `msvcrt!strchr` at `0x18087bf99`
- `msvcrt!strchr` at `0x18087bfcd`
- `msvcrt!strchr` at `0x18087bff3`
- `msvcrt!memcpy_s` at `0x18087c05f`
- `msvcrt!memcpy_s` at `0x18087c05f`
- `KERNEL32!GlobalFree` at `0x18087c0b3`
- `KERNEL32!GlobalFree` at `0x18087c0b3`
- `KERNEL32!GlobalLock` at `0x18087bf27`
- `KERNEL32!GlobalLock` at `0x18087bf27`
- `KERNEL32!GlobalUnlock` at `0x18087c09f`
- `KERNEL32!GlobalUnlock` at `0x18087c09f`
- `KERNEL32!WriteFile` at `0x18087be76`
- `KERNEL32!WriteFile` at `0x18087be76`
- `KERNEL32!ReadFile` at `0x18087bf56`
- `KERNEL32!ReadFile` at `0x18087bf56`
- `KERNEL32!GlobalAlloc` at `0x18087bf10`
- `KERNEL32!GlobalAlloc` at `0x18087bf10`
- `KERNEL32!GetTempPath2W` at `0x18087bdad`
- `KERNEL32!GetTempPath2W` at `0x18087bdad`
- `KERNEL32!GetTempFileNameW` at `0x18087bdd7`
- `KERNEL32!GetTempFileNameW` at `0x18087bdd7`
- `KERNEL32!CreateFileW` at `0x18087be24`
- `KERNEL32!CreateFileW` at `0x18087bed5`
- `KERNEL32!CreateFileW` at `0x18087be24`
- `KERNEL32!CreateFileW` at `0x18087bed5`
- `KERNEL32!GetFileSize` at `0x18087bef2`
- `KERNEL32!GetFileSize` at `0x18087bef2`
- `KERNEL32!DeleteFileW` at `0x18087c0c6`
- `KERNEL32!DeleteFileW` at `0x18087c0c6`
- `KERNEL32!CloseHandle` at `0x18087be87`
- `KERNEL32!CloseHandle` at `0x18087bf67`
- `KERNEL32!CloseHandle` at `0x18087be87`
- `KERNEL32!CloseHandle` at `0x18087bf67`

## pseudocode

```c
__int64 __fastcall CRtfToHtmlConverter::StringRtfToStringHtml(CRtfToHtmlConverter *this, char *a2, void **a3)
{
  void *v5; // r14
  char *v6; // rsi
  __int64 v7; // rdi
  CRtfToHtmlConverter *v8; // rcx
  HANDLE FileW; // r15
  int v10; // eax
  __int64 v11; // r8
  BOOL v12; // ebx
  unsigned int v13; // r8d
  unsigned int v14; // r12d
  HANDLE v15; // rax
  void *v16; // r15
  DWORD FileSize; // eax
  __int64 v18; // r13
  HGLOBAL v19; // rax
  char *v20; // rax
  BOOL v21; // ebx
  const char *v22; // rbx
  const char *v23; // rcx
  char *v24; // rax
  char *v25; // rbx
  char *v26; // r15
  const char *i; // rcx
  char *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  int v31; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  void **v36; // [rsp+58h] [rbp-A8h]
  WCHAR TempFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+270h] [rbp+170h] BYREF

  v36 = a3;
  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  PathName[0] = 0;
  v5 = 0;
  TempFileName[0] = 0;
  lpBuffer = 0;
  v6 = 0;
  if ( !(unsigned int)GetTempPath2W(260, PathName) )
    goto LABEL_28;
  if ( !GetTempFileNameW(PathName, L"r2h", 0, TempFileName) )
    goto LABEL_28;
  StringCchCopyW(PathName, 0x104u, TempFileName);
  v7 = -1;
  FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_28;
  v10 = CRtfToHtmlConverter::AdjustRtfIfNeeded(v8, a2, (char **)&lpBuffer);
  v5 = (void *)lpBuffer;
  if ( v10 )
    goto LABEL_28;
  v11 = -1;
  do
    ++v11;
  while ( *((_BYTE *)lpBuffer + v11) );
  v12 = WriteFile(FileW, lpBuffer, v11, &NumberOfBytesWritten, 0);
  CloseHandle(FileW);
  if ( !v12 )
    goto LABEL_28;
  v14 = CRtfToHtmlConverter::ExternalRtfToInternalHtml(this, TempFileName, v13);
  if ( v14 )
    goto LABEL_28;
  v15 = CreateFileW(TempFileName, 0x80000000, 0, 0, 3u, 0x4000000u, 0);
  v16 = v15;
  if ( v15 == (HANDLE)-1LL )
    goto LABEL_28;
  FileSize = GetFileSize(v15, 0);
  v18 = FileSize;
  if ( FileSize == -1
    || (v19 = GlobalAlloc(0, FileSize + 1), *v36 = v19, v20 = (char *)GlobalLock(v19), (v6 = v20) == 0)
    || (v21 = ReadFile(v16, v20, v18, &NumberOfBytesRead, 0), CloseHandle(v16), !v21) )
  {
LABEL_28:
    v14 = -2147467259;
    if ( !v6 )
      goto LABEL_30;
  }
  else
  {
    v22 = v6;
    v23 = v6;
    v6[NumberOfBytesRead] = 0;
    while ( strncmp_0(v23, "<BODY", 5u) )
    {
      v24 = strchr(v22 + 1, 60);
      v22 = v24;
      if ( !v24 )
        goto LABEL_28;
      v23 = v24;
    }
    v25 = strchr(v22, 62) + 1;
    lpBuffer = v25;
    v26 = v25;
    for ( i = v25; strncmp_0(i, "</BODY", 6u); i = v28 )
    {
      v28 = strchr(v26 + 1, 60);
      v26 = v28;
      if ( !v28 )
        goto LABEL_28;
    }
    v29 = -1;
    do
      ++v29;
    while ( v25[v29] );
    v30 = -1;
    do
      ++v30;
    while ( v6[v30] );
    v31 = v30 - v29;
    do
      ++v7;
    while ( v26[v7] );
    memcpy_s(v6, NumberOfBytesRead + 1, lpBuffer, (unsigned int)(v18 - v31 - v7));
    memset_0(&v6[v18 - v31 - (int)v7], 0, v31 + (int)v7);
  }
  GlobalUnlock(*v36);
LABEL_30:
  if ( v5 )
    GlobalFree(v5);
  DeleteFileW(PathName);
  return v14;
}

```

## disassembly

```asm
0x18087bd3c  mov     [rsp-8+arg_18], rbx
0x18087bd41  push    rbp
0x18087bd42  push    rsi
0x18087bd43  push    rdi
0x18087bd44  push    r12
0x18087bd46  push    r13
0x18087bd48  push    r14
0x18087bd4a  push    r15
0x18087bd4c  lea     rbp, [rsp-390h]
0x18087bd54  sub     rsp, 490h
0x18087bd5b  mov     rax, cs:__security_cookie
0x18087bd62  xor     rax, rsp
0x18087bd65  mov     [rbp+3C0h+var_40], rax
0x18087bd6c  xor     eax, eax
0x18087bd6e  mov     [rsp+4C0h+var_468], r8
0x18087bd73  mov     rbx, rdx
0x18087bd76  mov     [rsp+4C0h+NumberOfBytesRead], 0
0x18087bd7e  mov     r12, rcx
0x18087bd81  mov     [rsp+4C0h+NumberOfBytesWritten], 0
0x18087bd89  mov     edi, 104h
0x18087bd8e  mov     [rbp+3C0h+PathName], ax
0x18087bd95  xor     r14d, r14d
0x18087bd98  mov     [rsp+4C0h+TempFileName], ax
0x18087bd9d  mov     ecx, edi
0x18087bd9f  mov     [rsp+4C0h+lpBuffer], r14
0x18087bda4  lea     rdx, [rbp+3C0h+PathName]
0x18087bdab  xor     esi, esi
0x18087bdad  call    cs:__imp_GetTempPath2W
0x18087bdb4  nop     dword ptr [rax+rax+00h]
0x18087bdb9  test    eax, eax
0x18087bdbb  jz      loc_18087C08C
0x18087bdc1  lea     r9, [rsp+4C0h+TempFileName]; lpTempFileName
0x18087bdc6  xor     r8d, r8d; uUnique
0x18087bdc9  lea     rdx, aR2h; "r2h"
0x18087bdd0  lea     rcx, [rbp+3C0h+PathName]; lpPathName
0x18087bdd7  call    cs:__imp_GetTempFileNameW
0x18087bdde  nop     dword ptr [rax+rax+00h]
0x18087bde3  test    eax, eax
0x18087bde5  jz      loc_18087C08C
0x18087bdeb  lea     r8, [rsp+4C0h+TempFileName]; unsigned __int16 *
0x18087bdf0  mov     edx, edi; unsigned __int64
0x18087bdf2  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x18087bdf9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18087bdfe  mov     [rsp+4C0h+hTemplateFile], rsi; hTemplateFile
0x18087be03  lea     r13d, [r14+3]
0x18087be07  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18087be0f  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x18087be14  xor     r9d, r9d; lpSecurityAttributes
0x18087be17  mov     [rsp+4C0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18087be1c  xor     r8d, r8d; dwShareMode
0x18087be1f  mov     edx, 40000000h; dwDesiredAccess
0x18087be24  call    cs:__imp_CreateFileW
0x18087be2b  nop     dword ptr [rax+rax+00h]
0x18087be30  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18087be34  mov     r15, rax
0x18087be37  cmp     rax, rdi
0x18087be3a  jz      loc_18087C08C
0x18087be40  lea     r8, [rsp+4C0h+lpBuffer]; char **
0x18087be45  mov     rdx, rbx; char *
0x18087be48  call    ?AdjustRtfIfNeeded@CRtfToHtmlConverter@@AEAAJPEADPEAPEAD@Z; CRtfToHtmlConverter::AdjustRtfIfNeeded(char *,char * *)
0x18087be4d  mov     r14, [rsp+4C0h+lpBuffer]
0x18087be52  test    eax, eax
0x18087be54  jnz     loc_18087C08C
0x18087be5a  mov     r8, rdi
0x18087be5d  inc     r8; nNumberOfBytesToWrite
0x18087be60  cmp     [r14+r8], sil
0x18087be64  jnz     short loc_18087BE5D
0x18087be66  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18087be6b  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rsi; lpOverlapped
0x18087be70  mov     rdx, r14; lpBuffer
0x18087be73  mov     rcx, r15; hFile
0x18087be76  call    cs:__imp_WriteFile
0x18087be7d  nop     dword ptr [rax+rax+00h]
0x18087be82  mov     rcx, r15; hObject
0x18087be85  mov     ebx, eax
0x18087be87  call    cs:__imp_CloseHandle
0x18087be8e  nop     dword ptr [rax+rax+00h]
0x18087be93  test    ebx, ebx
0x18087be95  jz      loc_18087C08C
0x18087be9b  lea     rdx, [rsp+4C0h+TempFileName]; unsigned __int16 *
0x18087bea0  mov     rcx, r12; this
0x18087bea3  call    ?ExternalRtfToInternalHtml@CRtfToHtmlConverter@@IEAAJPEAGK@Z; CRtfToHtmlConverter::ExternalRtfToInternalHtml(ushort *,ulong)
0x18087bea8  mov     r12d, eax
0x18087beab  test    eax, eax
0x18087bead  jnz     loc_18087C08C
0x18087beb3  mov     [rsp+4C0h+hTemplateFile], rsi; hTemplateFile
0x18087beb8  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x18087bebd  mov     [rsp+4C0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18087bec5  xor     r9d, r9d; lpSecurityAttributes
0x18087bec8  xor     r8d, r8d; dwShareMode
0x18087becb  mov     [rsp+4C0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18087bed0  mov     edx, 80000000h; dwDesiredAccess
0x18087bed5  call    cs:__imp_CreateFileW
0x18087bedc  nop     dword ptr [rax+rax+00h]
0x18087bee1  mov     r15, rax
0x18087bee4  cmp     rax, rdi
0x18087bee7  jz      loc_18087C08C
0x18087beed  xor     edx, edx; lpFileSizeHigh
0x18087beef  mov     rcx, rax; hFile
0x18087bef2  call    cs:__imp_GetFileSize
0x18087bef9  nop     dword ptr [rax+rax+00h]
0x18087befe  mov     r13d, eax
0x18087bf01  cmp     eax, 0FFFFFFFFh
0x18087bf04  jz      loc_18087C08C
0x18087bf0a  lea     edx, [r13+1]; dwBytes
0x18087bf0e  xor     ecx, ecx; uFlags
0x18087bf10  call    cs:__imp_GlobalAlloc
0x18087bf17  nop     dword ptr [rax+rax+00h]
0x18087bf1c  mov     rcx, [rsp+4C0h+var_468]
0x18087bf21  mov     [rcx], rax
0x18087bf24  mov     rcx, rax; hMem
0x18087bf27  call    cs:__imp_GlobalLock
0x18087bf2e  nop     dword ptr [rax+rax+00h]
0x18087bf33  mov     rsi, rax
0x18087bf36  test    rax, rax
0x18087bf39  jz      loc_18087C08C
0x18087bf3f  lea     r9, [rsp+4C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18087bf44  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x18087bf4d  mov     r8d, r13d; nNumberOfBytesToRead
0x18087bf50  mov     rdx, rax; lpBuffer
0x18087bf53  mov     rcx, r15; hFile
0x18087bf56  call    cs:__imp_ReadFile
0x18087bf5d  nop     dword ptr [rax+rax+00h]
0x18087bf62  mov     rcx, r15; hObject
0x18087bf65  mov     ebx, eax
0x18087bf67  call    cs:__imp_CloseHandle
0x18087bf6e  nop     dword ptr [rax+rax+00h]
0x18087bf73  test    ebx, ebx
0x18087bf75  jz      loc_18087C08C
0x18087bf7b  mov     eax, [rsp+4C0h+NumberOfBytesRead]
0x18087bf7f  lea     r15d, [r12+5]
0x18087bf84  mov     rbx, rsi
0x18087bf87  mov     rcx, rsi
0x18087bf8a  mov     [rax+rsi], r12b
0x18087bf8e  jmp     short loc_18087BFB4
0x18087bf90  lea     rcx, [rbx+1]; Str
0x18087bf94  mov     edx, 3Ch ; '<'; Val
0x18087bf99  call    cs:__imp_strchr
0x18087bfa0  nop     dword ptr [rax+rax+00h]
0x18087bfa5  mov     rbx, rax
0x18087bfa8  test    rax, rax
0x18087bfab  jz      loc_18087C08C
0x18087bfb1  mov     rcx, rax; Str1
0x18087bfb4  mov     r8d, r15d; MaxCount
0x18087bfb7  lea     rdx, Str2; "<BODY"
0x18087bfbe  call    strncmp_0
0x18087bfc3  test    eax, eax
0x18087bfc5  jnz     short loc_18087BF90
0x18087bfc7  lea     edx, [rax+3Eh]; Val
0x18087bfca  mov     rcx, rbx; Str
0x18087bfcd  call    cs:__imp_strchr
0x18087bfd4  nop     dword ptr [rax+rax+00h]
0x18087bfd9  lea     rbx, [rax+1]
0x18087bfdd  mov     [rsp+4C0h+lpBuffer], rbx
0x18087bfe2  mov     r15, rbx
0x18087bfe5  mov     rcx, rbx
0x18087bfe8  jmp     short loc_18087C00E
0x18087bfea  lea     rcx, [r15+1]; Str
0x18087bfee  mov     edx, 3Ch ; '<'; Val
0x18087bff3  call    cs:__imp_strchr
0x18087bffa  nop     dword ptr [rax+rax+00h]
0x18087bfff  mov     r15, rax
0x18087c002  test    rax, rax
0x18087c005  jz      loc_18087C08C
0x18087c00b  mov     rcx, rax; Str1
0x18087c00e  mov     r8d, 6; MaxCount
0x18087c014  lea     rdx, aBody_1; "</BODY"
0x18087c01b  call    strncmp_0
0x18087c020  test    eax, eax
0x18087c022  jnz     short loc_18087BFEA
0x18087c024  mov     rax, rdi
0x18087c027  inc     rax
0x18087c02a  cmp     byte ptr [rbx+rax], 0
0x18087c02e  jnz     short loc_18087C027
0x18087c030  mov     rbx, rdi
0x18087c033  inc     rbx
0x18087c036  cmp     byte ptr [rsi+rbx], 0
0x18087c03a  jnz     short loc_18087C033
0x18087c03c  sub     ebx, eax
0x18087c03e  inc     rdi
0x18087c041  cmp     byte ptr [r15+rdi], 0
0x18087c046  jnz     short loc_18087C03E
0x18087c048  mov     edx, [rsp+4C0h+NumberOfBytesRead]
0x18087c04c  mov     r9d, r13d
0x18087c04f  mov     r8, [rsp+4C0h+lpBuffer]; Source
0x18087c054  sub     r9d, ebx
0x18087c057  sub     r9d, edi; SourceSize
0x18087c05a  mov     rcx, rsi; Destination
0x18087c05d  inc     edx; DestinationSize
0x18087c05f  call    cs:__imp_memcpy_s
0x18087c066  nop     dword ptr [rax+rax+00h]
0x18087c06b  lea     eax, [rbx+rdi]
0x18087c06e  mov     rcx, r13
0x18087c071  movsxd  r8, eax; Size
0x18087c074  xor     edx, edx; Val
0x18087c076  movsxd  rax, ebx
0x18087c079  sub     rcx, rax
0x18087c07c  movsxd  rax, edi
0x18087c07f  sub     rcx, rax
0x18087c082  add     rcx, rsi; void *
0x18087c085  call    memset_0
0x18087c08a  jmp     short loc_18087C097
0x18087c08c  mov     r12d, 80004005h
0x18087c092  test    rsi, rsi
0x18087c095  jz      short loc_18087C0AB
0x18087c097  mov     rax, [rsp+4C0h+var_468]
0x18087c09c  mov     rcx, [rax]; hMem
0x18087c09f  call    cs:__imp_GlobalUnlock
0x18087c0a6  nop     dword ptr [rax+rax+00h]
0x18087c0ab  test    r14, r14
0x18087c0ae  jz      short loc_18087C0BF
0x18087c0b0  mov     rcx, r14; hMem
0x18087c0b3  call    cs:__imp_GlobalFree
0x18087c0ba  nop     dword ptr [rax+rax+00h]
0x18087c0bf  lea     rcx, [rbp+3C0h+PathName]; lpFileName
0x18087c0c6  call    cs:__imp_DeleteFileW
0x18087c0cd  nop     dword ptr [rax+rax+00h]
0x18087c0d2  mov     eax, r12d
0x18087c0d5  mov     rcx, [rbp+3C0h+var_40]
0x18087c0dc  xor     rcx, rsp; StackCookie
0x18087c0df  call    __security_check_cookie
0x18087c0e4  mov     rbx, [rsp+4C0h+arg_18]
0x18087c0ec  add     rsp, 490h
0x18087c0f3  pop     r15
0x18087c0f5  pop     r14
0x18087c0f7  pop     r13
0x18087c0f9  pop     r12
0x18087c0fb  pop     rdi
0x18087c0fc  pop     rsi
0x18087c0fd  pop     rbp
0x18087c0fe  retn
```
