# CleanupTempDirs(void)

- ea: `0x140008c74`
- end: `0x140008f72`
- name: `?CleanupTempDirs@@YAJXZ`
- size: `766`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000ca10`

## callees

- `0x140001af3`
- `0x140008c74`
- `0x14000abd4`
- `0x14000b654`
- `0x14000b700`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!SetFileAttributesA` at `0x140008ed4`
- `KERNEL32!SetFileAttributesA` at `0x140008ed4`
- `KERNEL32!FindFirstFileA` at `0x140008d75`
- `KERNEL32!FindFirstFileA` at `0x140008d75`
- `KERNEL32!FindNextFileA` at `0x140008efa`
- `KERNEL32!FindNextFileA` at `0x140008efa`
- `KERNEL32!FindClose` at `0x140008f3d`
- `KERNEL32!FindClose` at `0x140008f3d`
- `KERNEL32!lstrcmpA` at `0x140008d9a`
- `KERNEL32!lstrcmpA` at `0x140008dba`
- `KERNEL32!lstrcmpA` at `0x140008d9a`
- `KERNEL32!lstrcmpA` at `0x140008dba`
- `KERNEL32!GetTempPath2A` at `0x140008cbc`
- `KERNEL32!GetTempPath2A` at `0x140008cbc`
- `KERNEL32!GetLastError` at `0x140008ccc`
- `KERNEL32!GetLastError` at `0x140008f0e`
- `KERNEL32!GetLastError` at `0x140008f1f`
- `KERNEL32!GetLastError` at `0x140008ccc`
- `KERNEL32!GetLastError` at `0x140008f0e`
- `KERNEL32!GetLastError` at `0x140008f1f`

## pseudocode

```c
__int64 CleanupTempDirs(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  __int64 v2; // rax
  char *v3; // r8
  __int64 v4; // rcx
  CHAR *v5; // rdx
  CHAR *v6; // rax
  HANDLE FirstFileA; // rdi
  size_t v8; // rcx
  char *v9; // rdx
  __int64 v10; // rax
  CHAR *cFileName; // r8
  char *v12; // rax
  signed int v13; // eax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  char *v16; // [rsp+38h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  CHAR FileName[272]; // [rsp+180h] [rbp+80h] BYREF
  char v19[272]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !(unsigned int)GetTempPath2A(260, v19) )
  {
LABEL_2:
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)v1;
  }
  v2 = 2147483646;
  v3 = v19;
  v4 = 260;
  v5 = FileName;
  do
  {
    if ( !v2 )
      break;
    if ( !*v3 )
      break;
    *v5++ = *v3++;
    --v2;
    --v4;
  }
  while ( v4 );
  v6 = v5 - 1;
  v1 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v6 = v5;
  *v6 = 0;
  if ( v4 )
  {
    v1 = StringCchCatA(FileName, 0x104u, "IDC*");
    if ( v1 >= 0 )
    {
      FirstFileA = FindFirstFileA(FileName, &FindFileData);
      if ( FirstFileA == (HANDLE)-1LL )
        goto LABEL_2;
      do
      {
        if ( lstrcmpA(FindFileData.cFileName, ".") && lstrcmpA(FindFileData.cFileName, "..") )
        {
          v16 = FileName;
          Size = 260;
          v1 = StringCchCopyExA(FileName, 0x104u, v19, &v16, &Size, 0);
          if ( v1 < 0 )
            goto LABEL_34;
          v1 = StringCchCopyExA(v16, Size, "\\", &v16, &Size, 0);
          if ( v1 < 0 )
            goto LABEL_34;
          v8 = Size;
          v9 = v16;
          if ( Size )
          {
            if ( Size > 0x7FFFFFFF )
            {
              *v16 = 0;
              v1 = -2147024809;
              goto LABEL_34;
            }
            v10 = 2147483646;
            cFileName = FindFileData.cFileName;
            do
            {
              if ( !v10 )
                break;
              if ( !*cFileName )
                break;
              *v9++ = *cFileName++;
              --v10;
              --v8;
            }
            while ( v8 );
            v12 = v9 - 1;
            if ( v8 )
              v12 = v9;
            v1 = v8 == 0 ? 0x8007007A : 0;
            *v12 = 0;
          }
          else
          {
            v1 = -2147024809;
          }
          if ( v1 < 0 )
            goto LABEL_34;
          if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
          {
            SetFileAttributesA(FileName, 0x90u);
            v1 = RemoveDirectoryAndChildren(FileName);
            if ( v1 < 0 )
              goto LABEL_34;
          }
        }
      }
      while ( FindNextFileA(FirstFileA, &FindFileData) );
      if ( GetLastError() != 18 )
      {
        v13 = GetLastError();
        v1 = v13;
        if ( v13 > 0 )
          v1 = (unsigned __int16)v13 | 0x80070000;
      }
LABEL_34:
      FindClose(FirstFileA);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140008c74  push    rbp
0x140008c76  push    rbx
0x140008c77  push    rdi
0x140008c78  push    r14
0x140008c7a  lea     rbp, [rsp-2B8h]
0x140008c82  sub     rsp, 3B8h
0x140008c89  mov     rax, cs:__security_cookie
0x140008c90  xor     rax, rsp
0x140008c93  mov     [rbp+2D0h+var_30], rax
0x140008c9a  xor     edx, edx; Val
0x140008c9c  lea     rcx, [rsp+3D0h+FindFileData]; void *
0x140008ca1  mov     r8d, 140h; Size
0x140008ca7  call    memset_0
0x140008cac  mov     r14d, 104h
0x140008cb2  lea     rdx, [rbp+2D0h+var_140]
0x140008cb9  mov     ecx, r14d
0x140008cbc  call    cs:__imp_GetTempPath2A
0x140008cc3  nop     dword ptr [rax+rax+00h]
0x140008cc8  test    eax, eax
0x140008cca  jnz     short loc_140008CF0
0x140008ccc  call    cs:__imp_GetLastError
0x140008cd3  nop     dword ptr [rax+rax+00h]
0x140008cd8  mov     ebx, eax
0x140008cda  test    eax, eax
0x140008cdc  jle     loc_140008F49
0x140008ce2  movzx   ebx, ax
0x140008ce5  or      ebx, 80070000h
0x140008ceb  jmp     loc_140008F49
0x140008cf0  mov     eax, 7FFFFFFEh
0x140008cf5  lea     r8, [rbp+2D0h+var_140]
0x140008cfc  mov     rcx, r14
0x140008cff  lea     rdx, [rbp+2D0h+FileName]
0x140008d06  test    rax, rax
0x140008d09  jz      short loc_140008D25
0x140008d0b  mov     r9b, [r8]
0x140008d0e  test    r9b, r9b
0x140008d11  jz      short loc_140008D25
0x140008d13  mov     [rdx], r9b
0x140008d16  inc     r8
0x140008d19  inc     rdx
0x140008d1c  dec     rax
0x140008d1f  sub     rcx, 1
0x140008d23  jnz     short loc_140008D06
0x140008d25  mov     rax, rcx
0x140008d28  neg     rax
0x140008d2b  lea     rax, [rdx-1]
0x140008d2f  sbb     ebx, ebx
0x140008d31  not     ebx
0x140008d33  and     ebx, 8007007Ah
0x140008d39  test    rcx, rcx
0x140008d3c  cmovnz  rax, rdx
0x140008d40  mov     byte ptr [rax], 0
0x140008d43  jz      loc_140008F49
0x140008d49  lea     r8, aIdc; "IDC*"
0x140008d50  mov     rdx, r14; unsigned __int64
0x140008d53  lea     rcx, [rbp+2D0h+FileName]; char *
0x140008d5a  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x140008d5f  mov     ebx, eax
0x140008d61  test    eax, eax
0x140008d63  js      loc_140008F49
0x140008d69  lea     rdx, [rsp+3D0h+FindFileData]; lpFindFileData
0x140008d6e  lea     rcx, [rbp+2D0h+FileName]; lpFileName
0x140008d75  call    cs:__imp_FindFirstFileA
0x140008d7c  nop     dword ptr [rax+rax+00h]
0x140008d81  mov     rdi, rax
0x140008d84  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140008d88  jz      loc_140008CCC
0x140008d8e  lea     rdx, String2; "."
0x140008d95  lea     rcx, [rsp+3D0h+FindFileData.cFileName]; lpString1
0x140008d9a  call    cs:__imp_lstrcmpA
0x140008da1  nop     dword ptr [rax+rax+00h]
0x140008da6  test    eax, eax
0x140008da8  jz      loc_140008EF2
0x140008dae  lea     rdx, asc_14001330C; ".."
0x140008db5  lea     rcx, [rsp+3D0h+FindFileData.cFileName]; lpString1
0x140008dba  call    cs:__imp_lstrcmpA
0x140008dc1  nop     dword ptr [rax+rax+00h]
0x140008dc6  test    eax, eax
0x140008dc8  jz      loc_140008EF2
0x140008dce  lea     rax, [rbp+2D0h+FileName]
0x140008dd5  mov     [rsp+3D0h+var_3A8], 0; unsigned int
0x140008ddd  mov     [rsp+3D0h+var_398], rax
0x140008de2  lea     r9, [rsp+3D0h+var_398]; char **
0x140008de7  lea     rax, [rsp+3D0h+Size]
0x140008dec  mov     [rsp+3D0h+Size], r14
0x140008df1  lea     r8, [rbp+2D0h+var_140]; char *
0x140008df8  mov     [rsp+3D0h+var_3B0], rax; unsigned __int64 *
0x140008dfd  mov     rdx, r14; Size
0x140008e00  lea     rcx, [rbp+2D0h+FileName]; char *
0x140008e07  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x140008e0c  mov     ebx, eax
0x140008e0e  test    eax, eax
0x140008e10  js      loc_140008F3A
0x140008e16  mov     rdx, [rsp+3D0h+Size]; Size
0x140008e1b  lea     rax, [rsp+3D0h+Size]
0x140008e20  mov     rcx, [rsp+3D0h+var_398]; char *
0x140008e25  lea     r9, [rsp+3D0h+var_398]; char **
0x140008e2a  mov     [rsp+3D0h+var_3A8], 0; unsigned int
0x140008e32  lea     r8, asc_14001337C; "\\"
0x140008e39  mov     [rsp+3D0h+var_3B0], rax; unsigned __int64 *
0x140008e3e  call    ?StringCchCopyExA@@YAJPEAD_KPEBDPEAPEADPEA_KK@Z; StringCchCopyExA(char *,unsigned __int64,char const *,char * *,unsigned __int64 *,ulong)
0x140008e43  mov     ebx, eax
0x140008e45  test    eax, eax
0x140008e47  js      loc_140008F3A
0x140008e4d  mov     rcx, [rsp+3D0h+Size]
0x140008e52  mov     rdx, [rsp+3D0h+var_398]
0x140008e57  test    rcx, rcx
0x140008e5a  jz      short loc_140008EAF
0x140008e5c  cmp     rcx, 7FFFFFFFh
0x140008e63  ja      loc_140008F68
0x140008e69  mov     eax, 7FFFFFFEh
0x140008e6e  lea     r8, [rsp+3D0h+FindFileData.cFileName]
0x140008e73  test    rax, rax
0x140008e76  jz      short loc_140008E92
0x140008e78  mov     r9b, [r8]
0x140008e7b  test    r9b, r9b
0x140008e7e  jz      short loc_140008E92
0x140008e80  mov     [rdx], r9b
0x140008e83  inc     r8
0x140008e86  inc     rdx
0x140008e89  dec     rax
0x140008e8c  sub     rcx, 1
0x140008e90  jnz     short loc_140008E73
0x140008e92  test    rcx, rcx
0x140008e95  lea     rax, [rdx-1]
0x140008e99  cmovnz  rax, rdx
0x140008e9d  neg     rcx
0x140008ea0  sbb     ebx, ebx
0x140008ea2  not     ebx
0x140008ea4  and     ebx, 8007007Ah
0x140008eaa  mov     byte ptr [rax], 0
0x140008ead  jmp     short loc_140008EBD
0x140008eaf  mov     ebx, 80070057h
0x140008eb4  test    rcx, rcx
0x140008eb7  jnz     loc_140008F68
0x140008ebd  test    ebx, ebx
0x140008ebf  js      short loc_140008F3A
0x140008ec1  test    byte ptr [rsp+3D0h+FindFileData.dwFileAttributes], 10h
0x140008ec6  jz      short loc_140008EF2
0x140008ec8  mov     edx, 90h; dwFileAttributes
0x140008ecd  lea     rcx, [rbp+2D0h+FileName]; lpFileName
0x140008ed4  call    cs:__imp_SetFileAttributesA
0x140008edb  nop     dword ptr [rax+rax+00h]
0x140008ee0  lea     rcx, [rbp+2D0h+FileName]; char *
0x140008ee7  call    ?RemoveDirectoryAndChildren@@YAJPEBD@Z; RemoveDirectoryAndChildren(char const *)
0x140008eec  mov     ebx, eax
0x140008eee  test    eax, eax
0x140008ef0  js      short loc_140008F3A
0x140008ef2  lea     rdx, [rsp+3D0h+FindFileData]; lpFindFileData
0x140008ef7  mov     rcx, rdi; hFindFile
0x140008efa  call    cs:__imp_FindNextFileA
0x140008f01  nop     dword ptr [rax+rax+00h]
0x140008f06  test    eax, eax
0x140008f08  jnz     loc_140008D8E
0x140008f0e  call    cs:__imp_GetLastError
0x140008f15  nop     dword ptr [rax+rax+00h]
0x140008f1a  cmp     eax, 12h
0x140008f1d  jz      short loc_140008F3A
0x140008f1f  call    cs:__imp_GetLastError
0x140008f26  nop     dword ptr [rax+rax+00h]
0x140008f2b  mov     ebx, eax
0x140008f2d  test    eax, eax
0x140008f2f  jle     short loc_140008F3A
0x140008f31  movzx   ebx, ax
0x140008f34  or      ebx, 80070000h
0x140008f3a  mov     rcx, rdi; hFindFile
0x140008f3d  call    cs:__imp_FindClose
0x140008f44  nop     dword ptr [rax+rax+00h]
0x140008f49  mov     eax, ebx
0x140008f4b  mov     rcx, [rbp+2D0h+var_30]
0x140008f52  xor     rcx, rsp; StackCookie
0x140008f55  call    __security_check_cookie
0x140008f5a  add     rsp, 3B8h
0x140008f61  pop     r14
0x140008f63  pop     rdi
0x140008f64  pop     rbx
0x140008f65  pop     rbp
0x140008f66  retn
0x140008f68  mov     byte ptr [rdx], 0
0x140008f6b  mov     ebx, 80070057h
0x140008f70  jmp     short loc_140008F3A
```
