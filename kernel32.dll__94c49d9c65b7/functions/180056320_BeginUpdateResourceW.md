# BeginUpdateResourceW

- ea: `0x180056320`
- end: `0x180056523`
- name: `BeginUpdateResourceW`
- size: `515`
- prototype: `HANDLE __stdcall(LPCWSTR pFileName, BOOL bDeleteExistingResources)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800631e0`

## callees

- `0x180019b00`
- `0x180056320`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005650a`
- `ntdll!RtlSetLastWin32Error` at `0x18005650a`
- `KERNELBASE!GlobalFree` at `0x1800564d4`
- `KERNELBASE!GlobalFree` at `0x1800564fb`
- `KERNELBASE!GlobalFree` at `0x1800564d4`
- `KERNELBASE!GlobalFree` at `0x1800564fb`
- `KERNELBASE!GlobalAlloc` at `0x180056357`
- `KERNELBASE!GlobalAlloc` at `0x1800563ed`
- `KERNELBASE!GlobalAlloc` at `0x180056357`
- `KERNELBASE!GlobalAlloc` at `0x1800563ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180056449`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180056449`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceTypesExW` at `0x1800564bb`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceTypesExW` at `0x1800564bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800564c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800564c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005647b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005647b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056370`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056407`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056370`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180056407`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180056432`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800564df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800564f2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180056432`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800564df`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800564f2`

## pseudocode

```c
HANDLE __stdcall BeginUpdateResourceW(LPCWSTR pFileName, BOOL bDeleteExistingResources)
{
  HGLOBAL v4; // rax
  void *v5; // rdi
  ULONG LastErrorValue; // ebx
  LPVOID v7; // rsi
  LPCWSTR v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  size_t v12; // r14
  unsigned __int64 v13; // rax
  HGLOBAL v14; // rax
  wchar_t *v15; // rax
  const WCHAR *v16; // rbp
  HRESULT v17; // r14d
  DWORD FileAttributesW; // eax
  HMODULE Library; // rax
  HMODULE v20; // rbp

  if ( pFileName && *pFileName )
  {
    v4 = GlobalAlloc(0x42u, 0x38u);
    v5 = v4;
    if ( v4 )
    {
      v7 = GlobalLock(v4);
      if ( v7 )
      {
        v8 = pFileName;
        v9 = 0x7FFFFFFF;
        do
        {
          if ( !*v8 )
            break;
          ++v8;
          --v9;
        }
        while ( v9 );
        v10 = (0x7FFFFFFF - v9) & ((unsigned __int128)-(__int128)(unsigned __int64)v9 >> 64);
        if ( v9 )
        {
          v11 = (unsigned int)(v10 + 1);
          *((_DWORD *)v7 + 10) = 0;
          if ( (unsigned int)v11 < (unsigned int)v10 || (v12 = (unsigned int)v11, v13 = 2 * v11, v13 > 0xFFFFFFFF) )
          {
            LastErrorValue = 534;
          }
          else
          {
            v14 = GlobalAlloc(0x42u, (unsigned int)v13);
            *((_QWORD *)v7 + 6) = v14;
            if ( v14 )
            {
              v15 = (wchar_t *)GlobalLock(v14);
              v16 = v15;
              if ( v15 )
              {
                v17 = StringCchCopyW(v15, v12, pFileName);
                GlobalUnlock(*((HGLOBAL *)v7 + 6));
                if ( v17 >= 0 )
                {
                  FileAttributesW = GetFileAttributesW(v16);
                  if ( FileAttributesW == -1 )
                  {
                    LastErrorValue = NtCurrentTeb()->LastErrorValue;
                    if ( !LastErrorValue )
                      LastErrorValue = 2;
                  }
                  else if ( (FileAttributesW & 0x17) != 0 )
                  {
                    LastErrorValue = 19;
                  }
                  else
                  {
                    Library = LoadLibraryExW(pFileName, 0, 3u);
                    v20 = Library;
                    if ( Library )
                    {
                      LastErrorValue = 0;
                      if ( !bDeleteExistingResources )
                        EnumResourceTypesExW(Library, EnumTypesFunc, (LONG_PTR)v7, 0x10u, 0);
                      FreeLibrary(v20);
                      if ( !*((_DWORD *)v7 + 10) )
                      {
                        GlobalUnlock(v5);
                        return v5;
                      }
                    }
                    else
                    {
                      LastErrorValue = NtCurrentTeb()->LastErrorValue;
                      if ( !LastErrorValue )
                        LastErrorValue = 193;
                    }
                  }
                }
                else
                {
                  LastErrorValue = (unsigned __int16)v17;
                }
              }
              else
              {
                LastErrorValue = 8;
              }
              GlobalFree(*((HGLOBAL *)v7 + 6));
            }
            else
            {
              LastErrorValue = 8;
            }
          }
        }
        else
        {
          LastErrorValue = 87;
        }
        GlobalUnlock(v5);
      }
      else
      {
        LastErrorValue = 8;
      }
      GlobalFree(v5);
    }
    else
    {
      LastErrorValue = 8;
    }
  }
  else
  {
    LastErrorValue = 87;
  }
  RtlSetLastWin32Error(LastErrorValue);
  return 0;
}

```

## disassembly

```asm
0x180056320  push    rbx
0x180056322  push    rbp
0x180056323  push    rsi
0x180056324  push    rdi
0x180056325  push    r12
0x180056327  push    r13
0x180056329  push    r14
0x18005632b  push    r15
0x18005632d  sub     rsp, 38h
0x180056331  xor     r12d, r12d
0x180056334  mov     r15d, edx
0x180056337  mov     rbx, rcx
0x18005633a  test    rcx, rcx
0x18005633d  jz      loc_180056503
0x180056343  cmp     [rcx], r12w
0x180056347  jz      loc_180056503
0x18005634d  lea     edx, [r12+38h]; dwBytes
0x180056352  lea     ebp, [rdx+0Ah]
0x180056355  mov     ecx, ebp; uFlags
0x180056357  call    cs:__imp_GlobalAlloc
0x18005635d  mov     rdi, rax
0x180056360  test    rax, rax
0x180056363  jnz     short loc_18005636D
0x180056365  lea     ebx, [rbp-3Ah]
0x180056368  jmp     loc_180056508
0x18005636d  mov     rcx, rdi; hMem
0x180056370  call    cs:__imp_GlobalLock
0x180056376  mov     rsi, rax
0x180056379  test    rax, rax
0x18005637c  jnz     short loc_180056386
0x18005637e  lea     ebx, [rax+8]
0x180056381  jmp     loc_1800564F8
0x180056386  mov     r8d, 7FFFFFFFh
0x18005638c  mov     rax, rbx
0x18005638f  mov     ecx, r8d
0x180056392  cmp     [rax], r12w
0x180056396  jz      short loc_1800563A2
0x180056398  add     rax, 2
0x18005639c  sub     rcx, 1
0x1800563a0  jnz     short loc_180056392
0x1800563a2  sub     r8, rcx
0x1800563a5  mov     rax, rcx
0x1800563a8  neg     rax
0x1800563ab  sbb     rdx, rdx
0x1800563ae  and     rdx, r8
0x1800563b1  test    rcx, rcx
0x1800563b4  jnz     short loc_1800563C5
0x1800563b6  neg     rcx
0x1800563b9  sbb     ebx, ebx
0x1800563bb  not     ebx
0x1800563bd  and     ebx, 57h
0x1800563c0  jmp     loc_1800564EF
0x1800563c5  lea     eax, [rdx+1]
0x1800563c8  mov     [rsi+28h], r12d
0x1800563cc  cmp     eax, edx
0x1800563ce  jb      loc_1800564EA
0x1800563d4  mov     r14d, eax
0x1800563d7  mov     r13d, 0FFFFFFFFh
0x1800563dd  add     rax, rax
0x1800563e0  cmp     rax, r13
0x1800563e3  ja      loc_1800564EA
0x1800563e9  mov     edx, eax; dwBytes
0x1800563eb  mov     ecx, ebp; uFlags
0x1800563ed  call    cs:__imp_GlobalAlloc
0x1800563f3  mov     [rsi+30h], rax
0x1800563f7  test    rax, rax
0x1800563fa  jnz     short loc_180056404
0x1800563fc  lea     ebx, [rax+8]
0x1800563ff  jmp     loc_1800564EF
0x180056404  mov     rcx, rax; hMem
0x180056407  call    cs:__imp_GlobalLock
0x18005640d  mov     rbp, rax
0x180056410  test    rax, rax
0x180056413  jnz     short loc_18005641D
0x180056415  lea     ebx, [rax+8]
0x180056418  jmp     loc_1800564D0
0x18005641d  mov     r8, rbx; pszSrc
0x180056420  mov     rdx, r14; cchDest
0x180056423  mov     rcx, rbp; pszDest
0x180056426  call    StringCchCopyW
0x18005642b  mov     rcx, [rsi+30h]; hMem
0x18005642f  mov     r14d, eax
0x180056432  call    cs:__imp_GlobalUnlock
0x180056438  test    r14d, r14d
0x18005643b  jns     short loc_180056446
0x18005643d  movzx   ebx, r14w
0x180056441  jmp     loc_1800564D0
0x180056446  mov     rcx, rbp; lpFileName
0x180056449  call    cs:__imp_GetFileAttributesW
0x18005644f  cmp     eax, r13d
0x180056452  jnz     short loc_180056467
0x180056454  mov     ebx, gs:68h
0x18005645c  test    ebx, ebx
0x18005645e  jnz     short loc_1800564D0
0x180056460  mov     ebx, 2
0x180056465  jmp     short loc_1800564D0
0x180056467  test    al, 17h
0x180056469  jz      short loc_180056472
0x18005646b  mov     ebx, 13h
0x180056470  jmp     short loc_1800564D0
0x180056472  xor     edx, edx; hFile
0x180056474  mov     rcx, rbx; lpLibFileName
0x180056477  lea     r8d, [rdx+3]; dwFlags
0x18005647b  call    cs:__imp_LoadLibraryExW
0x180056481  mov     rbp, rax
0x180056484  test    rax, rax
0x180056487  jnz     short loc_18005649C
0x180056489  mov     ebx, gs:68h
0x180056491  test    ebx, ebx
0x180056493  jnz     short loc_1800564D0
0x180056495  mov     ebx, 0C1h
0x18005649a  jmp     short loc_1800564D0
0x18005649c  mov     ebx, r12d
0x18005649f  test    r15d, r15d
0x1800564a2  jnz     short loc_1800564C1
0x1800564a4  lea     r9d, [r15+10h]; dwFlags
0x1800564a8  mov     [rsp+78h+LangId], r12w; LangId
0x1800564ae  mov     r8, rsi; lParam
0x1800564b1  lea     rdx, ?EnumTypesFunc@@YAHPEAUHINSTANCE__@@PEBG_J@Z; lpEnumFunc
0x1800564b8  mov     rcx, rbp; hModule
0x1800564bb  call    cs:__imp_EnumResourceTypesExW
0x1800564c1  mov     rcx, rbp; hLibModule
0x1800564c4  call    cs:__imp_FreeLibrary
0x1800564ca  cmp     [rsi+28h], r12d
0x1800564ce  jz      short loc_1800564DC
0x1800564d0  mov     rcx, [rsi+30h]; hMem
0x1800564d4  call    cs:__imp_GlobalFree
0x1800564da  jmp     short loc_1800564EF
0x1800564dc  mov     rcx, rdi; hMem
0x1800564df  call    cs:__imp_GlobalUnlock
0x1800564e5  mov     rax, rdi
0x1800564e8  jmp     short loc_180056512
0x1800564ea  mov     ebx, 216h
0x1800564ef  mov     rcx, rdi; hMem
0x1800564f2  call    cs:__imp_GlobalUnlock
0x1800564f8  mov     rcx, rdi; hMem
0x1800564fb  call    cs:__imp_GlobalFree
0x180056501  jmp     short loc_180056508
0x180056503  mov     ebx, 57h ; 'W'
0x180056508  mov     ecx, ebx; LastError
0x18005650a  call    cs:__imp_RtlSetLastWin32Error
0x180056510  xor     eax, eax
0x180056512  add     rsp, 38h
0x180056516  pop     r15
0x180056518  pop     r14
0x18005651a  pop     r13
0x18005651c  pop     r12
0x18005651e  pop     rdi
0x18005651f  pop     rsi
0x180056520  pop     rbp
0x180056521  pop     rbx
0x180056522  retn
```
