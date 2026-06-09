# ReadFilePtr(char const *,char *)

- ea: `0x1801963ec`
- end: `0x18019656e`
- name: `?ReadFilePtr@@YAHPEBDPEAD@Z`
- size: `386`
- prototype: `__int64 __fastcall(const char *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18019a960`

## callees

- `0x1800086a0`
- `0x180014958`
- `0x180015010`
- `0x180027430`
- `0x1801963ec`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801964f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801964f4`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1801964a0`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1801964a0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801964ba`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1801964ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019653f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019653f`

## pseudocode

```c
__int64 __fastcall ReadFilePtr(const char *a1, char *a2)
{
  unsigned int FileAttributes; // eax
  HANDLE FileA; // rax
  void *v6; // rbx
  unsigned int v7; // esi
  DWORD FileSize; // edi
  char *i; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-468h] BYREF
  char Buffer[272]; // [rsp+50h] [rbp-458h] BYREF
  CHAR FileName[272]; // [rsp+160h] [rbp-348h] BYREF
  WCHAR WideCharStr[264]; // [rsp+270h] [rbp-238h] BYREF

  NumberOfBytesRead = 0;
  if ( !a1 )
    return 0;
  if ( !*a1 )
    return 0;
  ansi2wcs(a1, WideCharStr, 0x105u);
  strcpy_s_ex(FileName, 0x104u, a1);
  FileAttributes = afnGetFileAttributes(FileName);
  if ( FileAttributes == -1 )
    return 0;
  if ( (FileAttributes & 0x10) != 0 )
    return 0;
  FileA = CreateFileA(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v6 = FileA;
  if ( FileA == (HANDLE)-1LL )
    return 0;
  v7 = 0;
  FileSize = GetFileSize(FileA, 0);
  if ( FileSize - 1 <= 0x103 )
  {
    memset_0(Buffer, 0, 0x104u);
    if ( ReadFile(v6, Buffer, FileSize, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead == FileSize )
      {
        v7 = 1;
        for ( i = Buffer; *i; ++i )
        {
          if ( *i == 10 || *i == 13 )
          {
            *i = 0;
            break;
          }
        }
        strcpy_s_ex(a2, 0x105u, Buffer);
      }
    }
  }
  if ( v6 )
    CloseHandle(v6);
  return v7;
}

```

## disassembly

```asm
0x1801963ec  mov     [rsp+arg_10], rbx
0x1801963f1  push    rbp
0x1801963f2  push    rsi
0x1801963f3  push    rdi
0x1801963f4  sub     rsp, 490h
0x1801963fb  mov     rax, cs:__security_cookie
0x180196402  xor     rax, rsp
0x180196405  mov     [rsp+4A8h+var_28], rax
0x18019640d  mov     [rsp+4A8h+NumberOfBytesRead], 0
0x180196415  mov     rbp, rdx
0x180196418  mov     rbx, rcx
0x18019641b  test    rcx, rcx
0x18019641e  jz      loc_180196549
0x180196424  cmp     byte ptr [rcx], 0
0x180196427  jz      loc_180196549
0x18019642d  mov     r8d, 105h; cchWideChar
0x180196433  lea     rdx, [rsp+4A8h+WideCharStr]; lpWideCharStr
0x18019643b  call    ?ansi2wcs@@YAHPEBDPEAGK@Z; ansi2wcs(char const *,ushort *,ulong)
0x180196440  mov     r8, rbx; char *
0x180196443  lea     rcx, [rsp+4A8h+FileName]; char *
0x18019644b  mov     edx, 104h; unsigned __int64
0x180196450  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x180196455  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x18019645d  call    ?afnGetFileAttributes@@YAKPEBD@Z; afnGetFileAttributes(char const *)
0x180196462  cmp     eax, 0FFFFFFFFh
0x180196465  jz      loc_180196549
0x18019646b  test    al, 10h
0x18019646d  jnz     loc_180196549
0x180196473  xor     r9d, r9d; lpSecurityAttributes
0x180196476  mov     [rsp+4A8h+hTemplateFile], 0; hTemplateFile
0x18019647f  mov     [rsp+4A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180196487  lea     rcx, [rsp+4A8h+FileName]; lpFileName
0x18019648f  mov     edx, 80000000h; dwDesiredAccess
0x180196494  mov     [rsp+4A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18019649c  lea     r8d, [r9+1]; dwShareMode
0x1801964a0  call    cs:__imp_CreateFileA
0x1801964a6  mov     rbx, rax
0x1801964a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801964ad  jz      loc_180196549
0x1801964b3  xor     edx, edx; lpFileSizeHigh
0x1801964b5  mov     rcx, rax; hFile
0x1801964b8  xor     esi, esi
0x1801964ba  call    cs:__imp_GetFileSize
0x1801964c0  mov     edi, eax
0x1801964c2  lea     ecx, [rax-1]
0x1801964c5  cmp     ecx, 103h
0x1801964cb  ja      short loc_180196537
0x1801964cd  xor     edx, edx; Val
0x1801964cf  lea     rcx, [rsp+4A8h+Buffer]; void *
0x1801964d4  mov     r8d, 104h; Size
0x1801964da  call    memset_0
0x1801964df  lea     r9, [rsp+4A8h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801964e4  mov     qword ptr [rsp+4A8h+dwCreationDisposition], rsi; lpOverlapped
0x1801964e9  mov     r8d, edi; nNumberOfBytesToRead
0x1801964ec  lea     rdx, [rsp+4A8h+Buffer]; lpBuffer
0x1801964f1  mov     rcx, rbx; hFile
0x1801964f4  call    cs:__imp_ReadFile
0x1801964fa  test    eax, eax
0x1801964fc  jz      short loc_180196537
0x1801964fe  cmp     [rsp+4A8h+NumberOfBytesRead], edi
0x180196502  jnz     short loc_180196537
0x180196504  mov     esi, 1
0x180196509  lea     rax, [rsp+4A8h+Buffer]
0x18019650e  cmp     byte ptr [rax], 0
0x180196511  jz      short loc_180196525
0x180196513  cmp     byte ptr [rax], 0Ah
0x180196516  jz      short loc_180196522
0x180196518  cmp     byte ptr [rax], 0Dh
0x18019651b  jz      short loc_180196522
0x18019651d  inc     rax
0x180196520  jmp     short loc_18019650E
0x180196522  mov     byte ptr [rax], 0
0x180196525  lea     r8, [rsp+4A8h+Buffer]; char *
0x18019652a  mov     edx, 105h; unsigned __int64
0x18019652f  mov     rcx, rbp; char *
0x180196532  call    ?strcpy_s_ex@@YAHPEAD_KPEBD@Z; strcpy_s_ex(char *,unsigned __int64,char const *)
0x180196537  test    rbx, rbx
0x18019653a  jz      short loc_180196545
0x18019653c  mov     rcx, rbx; hObject
0x18019653f  call    cs:__imp_CloseHandle
0x180196545  mov     eax, esi
0x180196547  jmp     short loc_18019654B
0x180196549  xor     eax, eax
0x18019654b  mov     rcx, [rsp+4A8h+var_28]
0x180196553  xor     rcx, rsp; StackCookie
0x180196556  call    __security_check_cookie
0x18019655b  mov     rbx, [rsp+4A8h+arg_10]
0x180196563  add     rsp, 490h
0x18019656a  pop     rdi
0x18019656b  pop     rsi
0x18019656c  pop     rbp
0x18019656d  retn
```
