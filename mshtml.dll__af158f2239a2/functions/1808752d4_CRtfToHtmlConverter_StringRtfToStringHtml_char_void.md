# CRtfToHtmlConverter::StringRtfToStringHtml(char *,void * *)

- ea: `0x1808752d4`
- end: `0x180875627`
- name: `?StringRtfToStringHtml@CRtfToHtmlConverter@@IEAAJPEADPEAPEAX@Z`
- size: `851`
- prototype: `__int64 __fastcall(CRtfToHtmlConverter *__hidden this, char *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1807fb1b4`

## callees

- `0x1802e5024`
- `0x180874660`
- `0x1808749d0`
- `0x1808752d4`
- `0x1810c2cb6`
- `0x1810c2d0a`
- `0x1810c2d60`

## import_xrefs

- `msvcrt!strchr` at `0x1808754ef`
- `msvcrt!strchr` at `0x18087551d`
- `msvcrt!strchr` at `0x18087553d`
- `msvcrt!strchr` at `0x1808754ef`
- `msvcrt!strchr` at `0x18087551d`
- `msvcrt!strchr` at `0x18087553d`
- `msvcrt!memcpy_s` at `0x18087559f`
- `msvcrt!memcpy_s` at `0x18087559f`
- `KERNEL32!GlobalFree` at `0x1808755e7`
- `KERNEL32!GlobalFree` at `0x1808755e7`
- `KERNEL32!GlobalLock` at `0x18087548f`
- `KERNEL32!GlobalLock` at `0x18087548f`
- `KERNEL32!GlobalUnlock` at `0x1808755d9`
- `KERNEL32!GlobalUnlock` at `0x1808755d9`
- `KERNEL32!WriteFile` at `0x1808753fc`
- `KERNEL32!WriteFile` at `0x1808753fc`
- `KERNEL32!ReadFile` at `0x1808754b8`
- `KERNEL32!ReadFile` at `0x1808754b8`
- `KERNEL32!GlobalAlloc` at `0x18087547e`
- `KERNEL32!GlobalAlloc` at `0x18087547e`
- `KERNEL32!GetTempPath2W` at `0x180875345`
- `KERNEL32!GetTempPath2W` at `0x180875345`
- `KERNEL32!GetTempFileNameW` at `0x180875369`
- `KERNEL32!GetTempFileNameW` at `0x180875369`
- `KERNEL32!CreateFileW` at `0x1808753b0`
- `KERNEL32!CreateFileW` at `0x18087544f`
- `KERNEL32!CreateFileW` at `0x1808753b0`
- `KERNEL32!CreateFileW` at `0x18087544f`
- `KERNEL32!GetFileSize` at `0x180875466`
- `KERNEL32!GetFileSize` at `0x180875466`
- `KERNEL32!DeleteFileW` at `0x1808755f4`
- `KERNEL32!DeleteFileW` at `0x1808755f4`
- `KERNEL32!CloseHandle` at `0x180875407`
- `KERNEL32!CloseHandle` at `0x1808754c3`
- `KERNEL32!CloseHandle` at `0x180875407`
- `KERNEL32!CloseHandle` at `0x1808754c3`

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
  unsigned int v13; // r12d
  HANDLE v14; // rax
  void *v15; // r15
  DWORD FileSize; // eax
  __int64 v17; // r13
  HGLOBAL v18; // rax
  char *v19; // rax
  BOOL v20; // ebx
  const char *v21; // rbx
  const char *v22; // rcx
  char *v23; // rax
  char *v24; // rbx
  char *v25; // r15
  const char *i; // rcx
  char *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  int v30; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  LPCVOID lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  void **v35; // [rsp+58h] [rbp-A8h]
  WCHAR TempFileName[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR PathName[264]; // [rsp+270h] [rbp+170h] BYREF

  v35 = a3;
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
  v13 = CRtfToHtmlConverter::ExternalRtfToInternalHtml(this, TempFileName);
  if ( v13 )
    goto LABEL_28;
  v14 = CreateFileW(TempFileName, 0x80000000, 0, 0, 3u, 0x4000000u, 0);
  v15 = v14;
  if ( v14 == (HANDLE)-1LL )
    goto LABEL_28;
  FileSize = GetFileSize(v14, 0);
  v17 = FileSize;
  if ( FileSize == -1
    || (v18 = GlobalAlloc(0, FileSize + 1), *v35 = v18, v19 = (char *)GlobalLock(v18), (v6 = v19) == 0)
    || (v20 = ReadFile(v15, v19, v17, &NumberOfBytesRead, 0), CloseHandle(v15), !v20) )
  {
LABEL_28:
    v13 = -2147467259;
    if ( !v6 )
      goto LABEL_30;
  }
  else
  {
    v21 = v6;
    v22 = v6;
    v6[NumberOfBytesRead] = 0;
    while ( strncmp_0(v22, "<BODY", 5u) )
    {
      v23 = strchr(v21 + 1, 60);
      v21 = v23;
      if ( !v23 )
        goto LABEL_28;
      v22 = v23;
    }
    v24 = strchr(v21, 62) + 1;
    lpBuffer = v24;
    v25 = v24;
    for ( i = v24; strncmp_0(i, "</BODY", 6u); i = v27 )
    {
      v27 = strchr(v25 + 1, 60);
      v25 = v27;
      if ( !v27 )
        goto LABEL_28;
    }
    v28 = -1;
    do
      ++v28;
    while ( v24[v28] );
    v29 = -1;
    do
      ++v29;
    while ( v6[v29] );
    v30 = v29 - v28;
    do
      ++v7;
    while ( v25[v7] );
    memcpy_s(v6, NumberOfBytesRead + 1, lpBuffer, (unsigned int)(v17 - v30 - v7));
    memset_0(&v6[v17 - v30 - (int)v7], 0, v30 + (int)v7);
  }
  GlobalUnlock(*v35);
LABEL_30:
  if ( v5 )
    GlobalFree(v5);
  DeleteFileW(PathName);
  return v13;
}

```

## disassembly

```asm
0x1808752d4  mov     [rsp-8+arg_18], rbx
0x1808752d9  push    rbp
0x1808752da  push    rsi
0x1808752db  push    rdi
0x1808752dc  push    r12
0x1808752de  push    r13
0x1808752e0  push    r14
0x1808752e2  push    r15
0x1808752e4  lea     rbp, [rsp-390h]
0x1808752ec  sub     rsp, 490h
0x1808752f3  mov     rax, cs:__security_cookie
0x1808752fa  xor     rax, rsp
0x1808752fd  mov     [rbp+3C0h+var_40], rax
0x180875304  xor     eax, eax
0x180875306  mov     [rsp+4C0h+var_468], r8
0x18087530b  mov     rbx, rdx
0x18087530e  mov     [rsp+4C0h+NumberOfBytesRead], 0
0x180875316  mov     r12, rcx
0x180875319  mov     [rsp+4C0h+NumberOfBytesWritten], 0
0x180875321  mov     edi, 104h
0x180875326  mov     [rbp+3C0h+PathName], ax
0x18087532d  xor     r14d, r14d
0x180875330  mov     [rsp+4C0h+TempFileName], ax
0x180875335  mov     ecx, edi
0x180875337  mov     [rsp+4C0h+lpBuffer], r14
0x18087533c  lea     rdx, [rbp+3C0h+PathName]
0x180875343  xor     esi, esi
0x180875345  call    cs:__imp_GetTempPath2W
0x18087534b  test    eax, eax
0x18087534d  jz      loc_1808755C6
0x180875353  lea     r9, [rsp+4C0h+TempFileName]; lpTempFileName
0x180875358  xor     r8d, r8d; uUnique
0x18087535b  lea     rdx, aR2h; "r2h"
0x180875362  lea     rcx, [rbp+3C0h+PathName]; lpPathName
0x180875369  call    cs:__imp_GetTempFileNameW
0x18087536f  test    eax, eax
0x180875371  jz      loc_1808755C6
0x180875377  lea     r8, [rsp+4C0h+TempFileName]; unsigned __int16 *
0x18087537c  mov     edx, edi; unsigned __int64
0x18087537e  lea     rcx, [rbp+3C0h+PathName]; unsigned __int16 *
0x180875385  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18087538a  mov     [rsp+4C0h+hTemplateFile], rsi; hTemplateFile
0x18087538f  lea     r13d, [r14+3]
0x180875393  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18087539b  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x1808753a0  xor     r9d, r9d; lpSecurityAttributes
0x1808753a3  mov     [rsp+4C0h+dwCreationDisposition], r13d; dwCreationDisposition
0x1808753a8  xor     r8d, r8d; dwShareMode
0x1808753ab  mov     edx, 40000000h; dwDesiredAccess
0x1808753b0  call    cs:__imp_CreateFileW
0x1808753b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1808753ba  mov     r15, rax
0x1808753bd  cmp     rax, rdi
0x1808753c0  jz      loc_1808755C6
0x1808753c6  lea     r8, [rsp+4C0h+lpBuffer]; char **
0x1808753cb  mov     rdx, rbx; char *
0x1808753ce  call    ?AdjustRtfIfNeeded@CRtfToHtmlConverter@@AEAAJPEADPEAPEAD@Z; CRtfToHtmlConverter::AdjustRtfIfNeeded(char *,char * *)
0x1808753d3  mov     r14, [rsp+4C0h+lpBuffer]
0x1808753d8  test    eax, eax
0x1808753da  jnz     loc_1808755C6
0x1808753e0  mov     r8, rdi
0x1808753e3  inc     r8; nNumberOfBytesToWrite
0x1808753e6  cmp     [r14+r8], sil
0x1808753ea  jnz     short loc_1808753E3
0x1808753ec  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1808753f1  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rsi; lpOverlapped
0x1808753f6  mov     rdx, r14; lpBuffer
0x1808753f9  mov     rcx, r15; hFile
0x1808753fc  call    cs:__imp_WriteFile
0x180875402  mov     rcx, r15; hObject
0x180875405  mov     ebx, eax
0x180875407  call    cs:__imp_CloseHandle
0x18087540d  test    ebx, ebx
0x18087540f  jz      loc_1808755C6
0x180875415  lea     rdx, [rsp+4C0h+TempFileName]; unsigned __int16 *
0x18087541a  mov     rcx, r12; this
0x18087541d  call    ?ExternalRtfToInternalHtml@CRtfToHtmlConverter@@IEAAJPEAGK@Z; CRtfToHtmlConverter::ExternalRtfToInternalHtml(ushort *,ulong)
0x180875422  mov     r12d, eax
0x180875425  test    eax, eax
0x180875427  jnz     loc_1808755C6
0x18087542d  mov     [rsp+4C0h+hTemplateFile], rsi; hTemplateFile
0x180875432  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x180875437  mov     [rsp+4C0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x18087543f  xor     r9d, r9d; lpSecurityAttributes
0x180875442  xor     r8d, r8d; dwShareMode
0x180875445  mov     [rsp+4C0h+dwCreationDisposition], r13d; dwCreationDisposition
0x18087544a  mov     edx, 80000000h; dwDesiredAccess
0x18087544f  call    cs:__imp_CreateFileW
0x180875455  mov     r15, rax
0x180875458  cmp     rax, rdi
0x18087545b  jz      loc_1808755C6
0x180875461  xor     edx, edx; lpFileSizeHigh
0x180875463  mov     rcx, rax; hFile
0x180875466  call    cs:__imp_GetFileSize
0x18087546c  mov     r13d, eax
0x18087546f  cmp     eax, 0FFFFFFFFh
0x180875472  jz      loc_1808755C6
0x180875478  lea     edx, [r13+1]; dwBytes
0x18087547c  xor     ecx, ecx; uFlags
0x18087547e  call    cs:__imp_GlobalAlloc
0x180875484  mov     rcx, [rsp+4C0h+var_468]
0x180875489  mov     [rcx], rax
0x18087548c  mov     rcx, rax; hMem
0x18087548f  call    cs:__imp_GlobalLock
0x180875495  mov     rsi, rax
0x180875498  test    rax, rax
0x18087549b  jz      loc_1808755C6
0x1808754a1  lea     r9, [rsp+4C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1808754a6  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x1808754af  mov     r8d, r13d; nNumberOfBytesToRead
0x1808754b2  mov     rdx, rax; lpBuffer
0x1808754b5  mov     rcx, r15; hFile
0x1808754b8  call    cs:__imp_ReadFile
0x1808754be  mov     rcx, r15; hObject
0x1808754c1  mov     ebx, eax
0x1808754c3  call    cs:__imp_CloseHandle
0x1808754c9  test    ebx, ebx
0x1808754cb  jz      loc_1808755C6
0x1808754d1  mov     eax, [rsp+4C0h+NumberOfBytesRead]
0x1808754d5  lea     r15d, [r12+5]
0x1808754da  mov     rbx, rsi
0x1808754dd  mov     rcx, rsi
0x1808754e0  mov     [rax+rsi], r12b
0x1808754e4  jmp     short loc_180875504
0x1808754e6  lea     rcx, [rbx+1]; Str
0x1808754ea  mov     edx, 3Ch ; '<'; Val
0x1808754ef  call    cs:__imp_strchr
0x1808754f5  mov     rbx, rax
0x1808754f8  test    rax, rax
0x1808754fb  jz      loc_1808755C6
0x180875501  mov     rcx, rax; Str1
0x180875504  mov     r8d, r15d; MaxCount
0x180875507  lea     rdx, Str2; "<BODY"
0x18087550e  call    strncmp_0
0x180875513  test    eax, eax
0x180875515  jnz     short loc_1808754E6
0x180875517  lea     edx, [rax+3Eh]; Val
0x18087551a  mov     rcx, rbx; Str
0x18087551d  call    cs:__imp_strchr
0x180875523  lea     rbx, [rax+1]
0x180875527  mov     [rsp+4C0h+lpBuffer], rbx
0x18087552c  mov     r15, rbx
0x18087552f  mov     rcx, rbx
0x180875532  jmp     short loc_18087554E
0x180875534  lea     rcx, [r15+1]; Str
0x180875538  mov     edx, 3Ch ; '<'; Val
0x18087553d  call    cs:__imp_strchr
0x180875543  mov     r15, rax
0x180875546  test    rax, rax
0x180875549  jz      short loc_1808755C6
0x18087554b  mov     rcx, rax; Str1
0x18087554e  mov     r8d, 6; MaxCount
0x180875554  lea     rdx, aBody_1; "</BODY"
0x18087555b  call    strncmp_0
0x180875560  test    eax, eax
0x180875562  jnz     short loc_180875534
0x180875564  mov     rax, rdi
0x180875567  inc     rax
0x18087556a  cmp     byte ptr [rbx+rax], 0
0x18087556e  jnz     short loc_180875567
0x180875570  mov     rbx, rdi
0x180875573  inc     rbx
0x180875576  cmp     byte ptr [rsi+rbx], 0
0x18087557a  jnz     short loc_180875573
0x18087557c  sub     ebx, eax
0x18087557e  inc     rdi
0x180875581  cmp     byte ptr [r15+rdi], 0
0x180875586  jnz     short loc_18087557E
0x180875588  mov     edx, [rsp+4C0h+NumberOfBytesRead]
0x18087558c  mov     r9d, r13d
0x18087558f  mov     r8, [rsp+4C0h+lpBuffer]; Source
0x180875594  sub     r9d, ebx
0x180875597  sub     r9d, edi; SourceSize
0x18087559a  mov     rcx, rsi; Destination
0x18087559d  inc     edx; DestinationSize
0x18087559f  call    cs:__imp_memcpy_s
0x1808755a5  lea     eax, [rbx+rdi]
0x1808755a8  mov     rcx, r13
0x1808755ab  movsxd  r8, eax; Size
0x1808755ae  xor     edx, edx; Val
0x1808755b0  movsxd  rax, ebx
0x1808755b3  sub     rcx, rax
0x1808755b6  movsxd  rax, edi
0x1808755b9  sub     rcx, rax
0x1808755bc  add     rcx, rsi; void *
0x1808755bf  call    memset_0
0x1808755c4  jmp     short loc_1808755D1
0x1808755c6  mov     r12d, 80004005h
0x1808755cc  test    rsi, rsi
0x1808755cf  jz      short loc_1808755DF
0x1808755d1  mov     rax, [rsp+4C0h+var_468]
0x1808755d6  mov     rcx, [rax]; hMem
0x1808755d9  call    cs:__imp_GlobalUnlock
0x1808755df  test    r14, r14
0x1808755e2  jz      short loc_1808755ED
0x1808755e4  mov     rcx, r14; hMem
0x1808755e7  call    cs:__imp_GlobalFree
0x1808755ed  lea     rcx, [rbp+3C0h+PathName]; lpFileName
0x1808755f4  call    cs:__imp_DeleteFileW
0x1808755fa  mov     eax, r12d
0x1808755fd  mov     rcx, [rbp+3C0h+var_40]
0x180875604  xor     rcx, rsp; StackCookie
0x180875607  call    __security_check_cookie
0x18087560c  mov     rbx, [rsp+4C0h+arg_18]
0x180875614  add     rsp, 490h
0x18087561b  pop     r15
0x18087561d  pop     r14
0x18087561f  pop     r13
0x180875621  pop     r12
0x180875623  pop     rdi
0x180875624  pop     rsi
0x180875625  pop     rbp
0x180875626  retn
```
