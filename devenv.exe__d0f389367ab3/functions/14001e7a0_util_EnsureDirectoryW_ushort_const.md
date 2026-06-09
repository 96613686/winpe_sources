# util_EnsureDirectoryW(ushort const *)

- ea: `0x14001e7a0`
- end: `0x14001e9e0`
- name: `?util_EnsureDirectoryW@@YAHPEBG@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001e650`
- `0x140064640`

## callees

- `0x140001020`
- `0x140001040`
- `0x14001e7a0`
- `0x14001e9e0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14001e873`
- `KERNEL32!GetFileAttributesW` at `0x14001e8eb`
- `KERNEL32!GetFileAttributesW` at `0x14001e981`
- `KERNEL32!GetFileAttributesW` at `0x14001e873`
- `KERNEL32!GetFileAttributesW` at `0x14001e8eb`
- `KERNEL32!GetFileAttributesW` at `0x14001e981`
- `KERNEL32!CreateDirectoryW` at `0x14001e995`
- `KERNEL32!CreateDirectoryW` at `0x14001e995`
- `KERNEL32!MoveFileW` at `0x14001e910`
- `KERNEL32!MoveFileW` at `0x14001e910`
- `SHLWAPI!PathRemoveBackslashW` at `0x14001e868`
- `SHLWAPI!PathRemoveBackslashW` at `0x14001e868`

## pseudocode

```c
__int64 __fastcall util_EnsureDirectoryW(char *a1)
{
  signed __int64 v2; // rbx
  WCHAR *p_pszPath; // rcx
  bool v4; // si
  int v5; // r14d
  __int64 v6; // rdx
  WCHAR v7; // ax
  WCHAR *v8; // rax
  DWORD FileAttributesW; // eax
  int v10; // ebx
  int v11; // eax
  WCHAR v12; // ax
  WCHAR *v13; // rbx
  WCHAR *p_PathName; // rdi
  WCHAR v15; // ax
  WCHAR v16; // cx
  __int64 v18; // [rsp+28h] [rbp-E0h]
  WCHAR pszPath; // [rsp+38h] [rbp-D0h] BYREF
  _WORD v20[263]; // [rsp+3Ah] [rbp-CEh] BYREF
  WCHAR FileName; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v22[526]; // [rsp+24Ah] [rbp+142h] BYREF
  WCHAR PathName; // [rsp+458h] [rbp+350h] BYREF
  _BYTE v24[526]; // [rsp+45Ah] [rbp+352h] BYREF

  pszPath = 0;
  memset_0(v20, 0, 0x206u);
  PathName = 0;
  memset_0(v24, 0, 0x206u);
  v2 = a1 - (char *)&pszPath;
  p_pszPath = &pszPath;
  v4 = 1;
  v5 = 0;
  v6 = 260;
  do
  {
    if ( v6 == -2147483386 )
      break;
    v7 = *(WCHAR *)((char *)p_pszPath + v2);
    if ( !v7 )
      break;
    *p_pszPath++ = v7;
    --v6;
  }
  while ( v6 );
  v8 = p_pszPath - 1;
  if ( v6 )
    v8 = p_pszPath;
  *v8 = 0;
  if ( v6 )
  {
    PathRemoveBackslashW(&pszPath);
    FileAttributesW = GetFileAttributesW(&pszPath);
    if ( FileAttributesW == -1 )
    {
LABEL_19:
      v12 = pszPath;
      v13 = &pszPath;
      if ( pszPath == 92 )
        v4 = v20[0] != 92;
      p_PathName = &PathName;
      while ( v12 )
      {
        v15 = *v13;
        v16 = *v13;
        do
        {
          *p_PathName = v16;
          ++v13;
          ++p_PathName;
          if ( v15 == 92 )
          {
            if ( v4 )
              break;
            v4 = ++v5 == 3;
          }
          v15 = *v13;
          v16 = *v13;
        }
        while ( *v13 );
        *p_PathName = 0;
        if ( GetFileAttributesW(&PathName) == -1 && !CreateDirectoryW(&PathName, 0) )
          return 0;
        v12 = *v13;
      }
    }
    else if ( (FileAttributesW & 0x10) == 0 )
    {
      FileName = 0;
      memset_0(v22, 0, 0x206u);
      v10 = 0;
      while ( 1 )
      {
        if ( v10 )
        {
          LODWORD(v18) = v10;
          v11 = StringCchPrintfW(&FileName, 0x104u, L"%s.bak-%d", &pszPath, v18);
        }
        else
        {
          v11 = StringCchPrintfW(&FileName, 0x104u, L"%s.bak", &pszPath);
        }
        if ( v11 < 0 )
          return 0;
        if ( GetFileAttributesW(&FileName) != -1 && ++v10 < 1024 )
          continue;
        if ( v10 == 1024 || !MoveFileW(&pszPath, &FileName) )
          return 0;
        goto LABEL_19;
      }
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e7a0  mov     rax, rsp
0x14001e7a3  mov     [rax+8], rbx
0x14001e7a7  mov     [rax+10h], rsi
0x14001e7ab  mov     [rax+18h], rdi
0x14001e7af  mov     [rax+20h], r13
0x14001e7b3  push    rbp
0x14001e7b4  push    r14
0x14001e7b6  push    r15
0x14001e7b8  lea     rbp, [rax-588h]
0x14001e7bf  sub     rsp, 670h
0x14001e7c6  mov     rax, cs:__security_cookie
0x14001e7cd  xor     rax, rsp
0x14001e7d0  mov     [rbp+580h+var_20], rax
0x14001e7d7  mov     rbx, rcx
0x14001e7da  mov     edi, 206h
0x14001e7df  xor     r15d, r15d
0x14001e7e2  lea     rcx, [rsp+680h+var_64E]; void *
0x14001e7e7  mov     r8d, edi; Size
0x14001e7ea  mov     [rsp+680h+pszPath], r15w
0x14001e7f0  xor     edx, edx; Val
0x14001e7f2  call    memset_0
0x14001e7f7  mov     r8d, edi; Size
0x14001e7fa  mov     [rbp+580h+PathName], r15w
0x14001e802  xor     edx, edx; Val
0x14001e804  lea     rcx, [rbp+580h+var_22E]; void *
0x14001e80b  call    memset_0
0x14001e810  lea     rax, [rsp+680h+pszPath]
0x14001e815  mov     r13d, 104h
0x14001e81b  sub     rbx, rax
0x14001e81e  lea     rcx, [rsp+680h+pszPath]
0x14001e823  mov     sil, 1
0x14001e826  mov     r14d, r15d
0x14001e829  mov     edx, r13d
0x14001e82c  lea     rax, [rdx+7FFFFEFAh]
0x14001e833  test    rax, rax
0x14001e836  jz      short loc_14001E84E
0x14001e838  movzx   eax, word ptr [rbx+rcx]
0x14001e83c  test    ax, ax
0x14001e83f  jz      short loc_14001E84E
0x14001e841  mov     [rcx], ax
0x14001e844  add     rcx, 2
0x14001e848  sub     rdx, 1
0x14001e84c  jnz     short loc_14001E82C
0x14001e84e  test    rdx, rdx
0x14001e851  lea     rax, [rcx-2]
0x14001e855  cmovnz  rax, rcx
0x14001e859  mov     [rax], r15w
0x14001e85d  jz      loc_14001E9AE
0x14001e863  lea     rcx, [rsp+680h+pszPath]; pszPath
0x14001e868  call    cs:__imp_PathRemoveBackslashW
0x14001e86e  lea     rcx, [rsp+680h+pszPath]; lpFileName
0x14001e873  call    cs:__imp_GetFileAttributesW
0x14001e879  cmp     eax, 0FFFFFFFFh
0x14001e87c  jz      loc_14001E91E
0x14001e882  test    al, 10h
0x14001e884  jnz     loc_14001E9A7
0x14001e88a  mov     r8, rdi; Size
0x14001e88d  mov     [rbp+580h+FileName], r15w
0x14001e895  xor     edx, edx; Val
0x14001e897  lea     rcx, [rbp+580h+var_43E]; void *
0x14001e89e  call    memset_0
0x14001e8a3  mov     ebx, r15d
0x14001e8a6  mov     edi, 400h
0x14001e8ab  lea     r9, [rsp+680h+pszPath]
0x14001e8b0  mov     rdx, r13; unsigned __int64
0x14001e8b3  lea     rcx, [rbp+580h+FileName]; Buffer
0x14001e8ba  test    ebx, ebx
0x14001e8bc  jnz     short loc_14001E8CC
0x14001e8be  lea     r8, aSBak; "%s.bak"
0x14001e8c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001e8ca  jmp     short loc_14001E8DC
0x14001e8cc  lea     r8, aSBakD; "%s.bak-%d"
0x14001e8d3  mov     [rsp+680h+var_660], ebx
0x14001e8d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001e8dc  test    eax, eax
0x14001e8de  js      loc_14001E9AE
0x14001e8e4  lea     rcx, [rbp+580h+FileName]; lpFileName
0x14001e8eb  call    cs:__imp_GetFileAttributesW
0x14001e8f1  cmp     eax, 0FFFFFFFFh
0x14001e8f4  jz      short loc_14001E8FC
0x14001e8f6  inc     ebx
0x14001e8f8  cmp     ebx, edi
0x14001e8fa  jl      short loc_14001E8AB
0x14001e8fc  cmp     ebx, edi
0x14001e8fe  jz      loc_14001E9AE
0x14001e904  lea     rdx, [rbp+580h+FileName]; lpNewFileName
0x14001e90b  lea     rcx, [rsp+680h+pszPath]; lpExistingFileName
0x14001e910  call    cs:__imp_MoveFileW
0x14001e916  test    eax, eax
0x14001e918  jz      loc_14001E9AE
0x14001e91e  movzx   eax, [rsp+680h+pszPath]
0x14001e923  lea     rbx, [rsp+680h+pszPath]
0x14001e928  cmp     ax, 5Ch ; '\'
0x14001e92c  jnz     short loc_14001E93B
0x14001e92e  cmp     [rsp+680h+var_64E], ax
0x14001e933  movzx   esi, sil
0x14001e937  cmovz   esi, r15d
0x14001e93b  lea     rdi, [rbp+580h+PathName]
0x14001e942  jmp     short loc_14001E9A2
0x14001e944  movzx   eax, word ptr [rbx]
0x14001e947  movzx   ecx, ax
0x14001e94a  mov     [rdi], cx
0x14001e94d  add     rbx, 2
0x14001e951  add     rdi, 2
0x14001e955  cmp     ax, 5Ch ; '\'
0x14001e959  jnz     short loc_14001E96B
0x14001e95b  test    sil, sil
0x14001e95e  jnz     short loc_14001E976
0x14001e960  inc     r14d
0x14001e963  cmp     r14d, 3
0x14001e967  setz    sil
0x14001e96b  movzx   eax, word ptr [rbx]
0x14001e96e  movzx   ecx, ax
0x14001e971  test    ax, ax
0x14001e974  jnz     short loc_14001E94A
0x14001e976  lea     rcx, [rbp+580h+PathName]; lpFileName
0x14001e97d  mov     [rdi], r15w
0x14001e981  call    cs:__imp_GetFileAttributesW
0x14001e987  cmp     eax, 0FFFFFFFFh
0x14001e98a  jnz     short loc_14001E99F
0x14001e98c  xor     edx, edx; lpSecurityAttributes
0x14001e98e  lea     rcx, [rbp+580h+PathName]; lpPathName
0x14001e995  call    cs:__imp_CreateDirectoryW
0x14001e99b  test    eax, eax
0x14001e99d  jz      short loc_14001E9AE
0x14001e99f  movzx   eax, word ptr [rbx]
0x14001e9a2  test    ax, ax
0x14001e9a5  jnz     short loc_14001E944
0x14001e9a7  mov     eax, 1
0x14001e9ac  jmp     short loc_14001E9B0
0x14001e9ae  xor     eax, eax
0x14001e9b0  mov     rcx, [rbp+580h+var_20]
0x14001e9b7  xor     rcx, rsp; StackCookie
0x14001e9ba  call    __security_check_cookie
0x14001e9bf  lea     r11, [rsp+680h+var_10]
0x14001e9c7  mov     rbx, [r11+20h]
0x14001e9cb  mov     rsi, [r11+28h]
0x14001e9cf  mov     rdi, [r11+30h]
0x14001e9d3  mov     r13, [r11+38h]
0x14001e9d7  mov     rsp, r11
0x14001e9da  pop     r15
0x14001e9dc  pop     r14
0x14001e9de  pop     rbp
0x14001e9df  retn
```
