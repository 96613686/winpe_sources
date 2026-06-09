# InitializeUserFontsDir(ushort *)

- ea: `0x180013658`
- end: `0x18001387a`
- name: `?InitializeUserFontsDir@@YAJPEAG@Z`
- size: `546`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800135dc`

## callees

- `0x180002ee8`
- `0x180006598`
- `0x180006624`
- `0x1800132e4`
- `0x180013658`
- `0x180031070`

## import_xrefs

- `SHELL32!SHGetFolderPathW` at `0x1800136a3`
- `SHELL32!SHGetFolderPathW` at `0x1800136a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013760`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137ff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800136ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013745`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800136ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013745`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013756`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800137f5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013756`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800137f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001382b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013822`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001382b`

## pseudocode

```c
signed int __fastcall InitializeUserFontsDir(unsigned __int16 *a1)
{
  signed int result; // eax
  __int64 v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  const unsigned __int16 **i; // rbx
  int v9; // eax
  HLOCAL v10; // rsi
  struct _SECURITY_ATTRIBUTES *v11; // rdi
  signed int v12; // ebx
  signed int LastError; // eax
  HLOCAL v14; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B0h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  result = SHGetFolderPathW(0, 28, 0, 0, FileName);
  if ( result >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( FileName[v3] );
    result = StringCchCatW(FileName, 0x104u, L"\\Microsoft\\Windows\\Fonts");
    if ( result >= 0 )
    {
      if ( GetFileAttributesW(FileName) != -1 )
        return StringCchCopyW(a1, 0x104u, FileName);
      v7 = v3;
      if ( v7 >= 260 )
        _report_rangecheckfailure(v5, v4, v6);
      FileName[v7] = 0;
      for ( i = (const unsigned __int16 **)off_180035290; i != (const unsigned __int16 **)&off_1800352A0; ++i )
      {
        result = StringCchCatW(FileName, 0x104u, *i);
        if ( result < 0 )
          return result;
        if ( GetFileAttributesW(FileName) == -1 && !CreateDirectoryW(FileName, 0) )
        {
          result = GetLastError();
          if ( result != 183 )
          {
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
            return result;
          }
        }
      }
      hMem = 0;
      v14 = 0;
      v9 = CreateUserFontsSecurityDescriptor(FileName, (struct _ACL **)&hMem, &v14);
      v10 = v14;
      v17 = 0;
      v11 = 0;
      v16 = 0;
      if ( !v9 )
      {
        LODWORD(v16) = 24;
        v11 = (struct _SECURITY_ATTRIBUTES *)&v16;
        *((_QWORD *)&v16 + 1) = v14;
        LODWORD(v17) = 0;
      }
      v12 = StringCchCatW(FileName, 0x104u, L"\\Fonts");
      if ( v12 >= 0 && !CreateDirectoryW(FileName, v11) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
        {
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          else
            v12 = LastError;
        }
      }
      LocalFree(hMem);
      LocalFree(v10);
      if ( v12 >= 0 )
        return StringCchCopyW(a1, 0x104u, FileName);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013658  mov     [rsp-8+arg_8], rbx
0x18001365d  mov     [rsp-8+arg_10], rsi
0x180013662  push    rbp
0x180013663  push    rdi
0x180013664  push    r12
0x180013666  push    r14
0x180013668  push    r15
0x18001366a  lea     rbp, [rsp-180h]
0x180013672  sub     rsp, 280h
0x180013679  mov     rax, cs:__security_cookie
0x180013680  xor     rax, rsp
0x180013683  mov     [rbp+1A0h+var_30], rax
0x18001368a  xor     r9d, r9d; dwFlags
0x18001368d  lea     rax, [rsp+2A0h+FileName]
0x180013692  mov     r14, rcx
0x180013695  mov     [rsp+2A0h+pszPath], rax; pszPath
0x18001369a  xor     r8d, r8d; hToken
0x18001369d  xor     ecx, ecx; hwnd
0x18001369f  lea     edx, [r9+1Ch]; csidl
0x1800136a3  call    cs:__imp_SHGetFolderPathW
0x1800136a9  xor     r15d, r15d
0x1800136ac  test    eax, eax
0x1800136ae  js      loc_180013849
0x1800136b4  lea     rax, [rsp+2A0h+FileName]
0x1800136b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800136bd  inc     rbx
0x1800136c0  cmp     [rax+rbx*2], r15w
0x1800136c5  jnz     short loc_1800136BD
0x1800136c7  mov     r12d, 104h
0x1800136cd  lea     r8, aMicrosoftWindo; "\\Microsoft\\Windows\\Fonts"
0x1800136d4  mov     edx, r12d; unsigned __int64
0x1800136d7  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x1800136dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800136e1  test    eax, eax
0x1800136e3  js      loc_180013849
0x1800136e9  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x1800136ee  call    cs:__imp_GetFileAttributesW
0x1800136f4  or      edi, 0FFFFFFFFh
0x1800136f7  cmp     eax, edi
0x1800136f9  jnz     loc_180013835
0x1800136ff  add     rbx, rbx
0x180013702  cmp     rbx, 208h
0x180013709  jnb     loc_180013874
0x18001370f  mov     [rsp+rbx+2A0h+FileName], r15w
0x180013715  lea     rbx, off_180035290; "\\Microsoft"
0x18001371c  lea     rax, off_1800352A0
0x180013723  lea     rcx, [rsp+2A0h+FileName]; pObjectName
0x180013728  cmp     rbx, rax
0x18001372b  jz      short loc_180013788
0x18001372d  mov     r8, [rbx]; unsigned __int16 *
0x180013730  mov     rdx, r12; unsigned __int64
0x180013733  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013738  test    eax, eax
0x18001373a  js      loc_180013849
0x180013740  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x180013745  call    cs:__imp_GetFileAttributesW
0x18001374b  cmp     eax, edi
0x18001374d  jnz     short loc_18001376D
0x18001374f  xor     edx, edx; lpSecurityAttributes
0x180013751  lea     rcx, [rsp+2A0h+FileName]; lpPathName
0x180013756  call    cs:__imp_CreateDirectoryW
0x18001375c  test    eax, eax
0x18001375e  jnz     short loc_18001376D
0x180013760  call    cs:__imp_GetLastError
0x180013766  cmp     eax, 0B7h
0x18001376b  jnz     short loc_180013773
0x18001376d  add     rbx, 8
0x180013771  jmp     short loc_18001371C
0x180013773  test    eax, eax
0x180013775  jle     loc_180013849
0x18001377b  movzx   eax, ax
0x18001377e  or      eax, 80070000h
0x180013783  jmp     loc_180013849
0x180013788  lea     r8, [rsp+2A0h+var_270]; void **
0x18001378d  mov     [rsp+2A0h+hMem], r15
0x180013792  lea     rdx, [rsp+2A0h+hMem]; struct _ACL **
0x180013797  mov     [rsp+2A0h+var_270], r15
0x18001379c  call    ?CreateUserFontsSecurityDescriptor@@YAKPEBGPEAPEAU_ACL@@PEAPEAX@Z; CreateUserFontsSecurityDescriptor(ushort const *,_ACL * *,void * *)
0x1800137a1  mov     rsi, [rsp+2A0h+var_270]
0x1800137a6  xor     ecx, ecx
0x1800137a8  mov     [rsp+2A0h+var_250], rcx
0x1800137ad  xorps   xmm0, xmm0
0x1800137b0  mov     rdi, r15
0x1800137b3  movups  [rsp+2A0h+var_260], xmm0
0x1800137b8  test    eax, eax
0x1800137ba  jnz     short loc_1800137D3
0x1800137bc  mov     dword ptr [rsp+2A0h+var_260], 18h
0x1800137c4  lea     rdi, [rsp+2A0h+var_260]
0x1800137c9  mov     qword ptr [rsp+2A0h+var_260+8], rsi
0x1800137ce  mov     dword ptr [rsp+2A0h+var_250], r15d
0x1800137d3  lea     r8, aFonts_0; "\\Fonts"
0x1800137da  mov     rdx, r12; unsigned __int64
0x1800137dd  lea     rcx, [rsp+2A0h+FileName]; unsigned __int16 *
0x1800137e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800137e7  mov     ebx, eax
0x1800137e9  test    eax, eax
0x1800137eb  js      short loc_18001381D
0x1800137ed  mov     rdx, rdi; lpSecurityAttributes
0x1800137f0  lea     rcx, [rsp+2A0h+FileName]; lpPathName
0x1800137f5  call    cs:__imp_CreateDirectoryW
0x1800137fb  test    eax, eax
0x1800137fd  jnz     short loc_18001381D
0x1800137ff  call    cs:__imp_GetLastError
0x180013805  cmp     eax, 0B7h
0x18001380a  jz      short loc_18001381D
0x18001380c  test    eax, eax
0x18001380e  jg      short loc_180013814
0x180013810  mov     ebx, eax
0x180013812  jmp     short loc_18001381D
0x180013814  movzx   ebx, ax
0x180013817  or      ebx, 80070000h
0x18001381d  mov     rcx, [rsp+2A0h+hMem]; hMem
0x180013822  call    cs:__imp_LocalFree
0x180013828  mov     rcx, rsi; hMem
0x18001382b  call    cs:__imp_LocalFree
0x180013831  test    ebx, ebx
0x180013833  js      short loc_180013847
0x180013835  lea     r8, [rsp+2A0h+FileName]; unsigned __int16 *
0x18001383a  mov     rdx, r12; unsigned __int64
0x18001383d  mov     rcx, r14; unsigned __int16 *
0x180013840  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013845  mov     ebx, eax
0x180013847  mov     eax, ebx
0x180013849  mov     rcx, [rbp+1A0h+var_30]
0x180013850  xor     rcx, rsp; StackCookie
0x180013853  call    __security_check_cookie
0x180013858  lea     r11, [rsp+2A0h+var_20]
0x180013860  mov     rbx, [r11+38h]
0x180013864  mov     rsi, [r11+40h]
0x180013868  mov     rsp, r11
0x18001386b  pop     r15
0x18001386d  pop     r14
0x18001386f  pop     r12
0x180013871  pop     rdi
0x180013872  pop     rbp
0x180013873  retn
0x180013874  call    __report_rangecheckfailure
```
