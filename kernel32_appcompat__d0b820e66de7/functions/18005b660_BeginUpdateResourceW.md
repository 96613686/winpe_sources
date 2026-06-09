# BeginUpdateResourceW

- ea: `0x18005b660`
- end: `0x18005b8bc`
- name: `BeginUpdateResourceW`
- size: `604`
- prototype: `HANDLE __stdcall(LPCWSTR pFileName, BOOL bDeleteExistingResources)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180069d30`

## callees

- `0x180017530`
- `0x18005b660`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18005b89c`
- `ntdll!RtlSetLastWin32Error` at `0x18005b89c`
- `KERNELBASE!GlobalFree` at `0x18005b84e`
- `KERNELBASE!GlobalFree` at `0x18005b887`
- `KERNELBASE!GlobalFree` at `0x18005b84e`
- `KERNELBASE!GlobalFree` at `0x18005b887`
- `KERNELBASE!GlobalAlloc` at `0x18005b697`
- `KERNELBASE!GlobalAlloc` at `0x18005b739`
- `KERNELBASE!GlobalAlloc` at `0x18005b697`
- `KERNELBASE!GlobalAlloc` at `0x18005b739`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b7a7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b7a7`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceTypesExW` at `0x18005b829`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceTypesExW` at `0x18005b829`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b838`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b838`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b7e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b7e3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18005b6b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18005b759`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18005b6b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18005b759`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b78a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b85f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b878`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b78a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b85f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18005b878`

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
0x18005b660  push    rbx
0x18005b662  push    rbp
0x18005b663  push    rsi
0x18005b664  push    rdi
0x18005b665  push    r12
0x18005b667  push    r13
0x18005b669  push    r14
0x18005b66b  push    r15
0x18005b66d  sub     rsp, 38h
0x18005b671  xor     r12d, r12d
0x18005b674  mov     r15d, edx
0x18005b677  mov     rbx, rcx
0x18005b67a  test    rcx, rcx
0x18005b67d  jz      loc_18005B895
0x18005b683  cmp     [rcx], r12w
0x18005b687  jz      loc_18005B895
0x18005b68d  lea     edx, [r12+38h]; dwBytes
0x18005b692  lea     ebp, [rdx+0Ah]
0x18005b695  mov     ecx, ebp; uFlags
0x18005b697  call    cs:__imp_GlobalAlloc
0x18005b69e  nop     dword ptr [rax+rax+00h]
0x18005b6a3  mov     rdi, rax
0x18005b6a6  test    rax, rax
0x18005b6a9  jnz     short loc_18005B6B3
0x18005b6ab  lea     ebx, [rbp-3Ah]
0x18005b6ae  jmp     loc_18005B89A
0x18005b6b3  mov     rcx, rdi; hMem
0x18005b6b6  call    cs:__imp_GlobalLock
0x18005b6bd  nop     dword ptr [rax+rax+00h]
0x18005b6c2  mov     rsi, rax
0x18005b6c5  test    rax, rax
0x18005b6c8  jnz     short loc_18005B6D2
0x18005b6ca  lea     ebx, [rax+8]
0x18005b6cd  jmp     loc_18005B884
0x18005b6d2  mov     r8d, 7FFFFFFFh
0x18005b6d8  mov     rax, rbx
0x18005b6db  mov     ecx, r8d
0x18005b6de  cmp     [rax], r12w
0x18005b6e2  jz      short loc_18005B6EE
0x18005b6e4  add     rax, 2
0x18005b6e8  sub     rcx, 1
0x18005b6ec  jnz     short loc_18005B6DE
0x18005b6ee  sub     r8, rcx
0x18005b6f1  mov     rax, rcx
0x18005b6f4  neg     rax
0x18005b6f7  sbb     rdx, rdx
0x18005b6fa  and     rdx, r8
0x18005b6fd  test    rcx, rcx
0x18005b700  jnz     short loc_18005B711
0x18005b702  neg     rcx
0x18005b705  sbb     ebx, ebx
0x18005b707  not     ebx
0x18005b709  and     ebx, 57h
0x18005b70c  jmp     loc_18005B875
0x18005b711  lea     eax, [rdx+1]
0x18005b714  mov     [rsi+28h], r12d
0x18005b718  cmp     eax, edx
0x18005b71a  jb      loc_18005B870
0x18005b720  mov     r14d, eax
0x18005b723  mov     r13d, 0FFFFFFFFh
0x18005b729  add     rax, rax
0x18005b72c  cmp     rax, r13
0x18005b72f  ja      loc_18005B870
0x18005b735  mov     edx, eax; dwBytes
0x18005b737  mov     ecx, ebp; uFlags
0x18005b739  call    cs:__imp_GlobalAlloc
0x18005b740  nop     dword ptr [rax+rax+00h]
0x18005b745  mov     [rsi+30h], rax
0x18005b749  test    rax, rax
0x18005b74c  jnz     short loc_18005B756
0x18005b74e  lea     ebx, [rax+8]
0x18005b751  jmp     loc_18005B875
0x18005b756  mov     rcx, rax; hMem
0x18005b759  call    cs:__imp_GlobalLock
0x18005b760  nop     dword ptr [rax+rax+00h]
0x18005b765  mov     rbp, rax
0x18005b768  test    rax, rax
0x18005b76b  jnz     short loc_18005B775
0x18005b76d  lea     ebx, [rax+8]
0x18005b770  jmp     loc_18005B84A
0x18005b775  mov     r8, rbx; pszSrc
0x18005b778  mov     rdx, r14; cchDest
0x18005b77b  mov     rcx, rbp; pszDest
0x18005b77e  call    StringCchCopyW
0x18005b783  mov     rcx, [rsi+30h]; hMem
0x18005b787  mov     r14d, eax
0x18005b78a  call    cs:__imp_GlobalUnlock
0x18005b791  nop     dword ptr [rax+rax+00h]
0x18005b796  test    r14d, r14d
0x18005b799  jns     short loc_18005B7A4
0x18005b79b  movzx   ebx, r14w
0x18005b79f  jmp     loc_18005B84A
0x18005b7a4  mov     rcx, rbp; lpFileName
0x18005b7a7  call    cs:__imp_GetFileAttributesW
0x18005b7ae  nop     dword ptr [rax+rax+00h]
0x18005b7b3  cmp     eax, r13d
0x18005b7b6  jnz     short loc_18005B7CF
0x18005b7b8  mov     ebx, gs:68h
0x18005b7c0  test    ebx, ebx
0x18005b7c2  jnz     loc_18005B84A
0x18005b7c8  mov     ebx, 2
0x18005b7cd  jmp     short loc_18005B84A
0x18005b7cf  test    al, 17h
0x18005b7d1  jz      short loc_18005B7DA
0x18005b7d3  mov     ebx, 13h
0x18005b7d8  jmp     short loc_18005B84A
0x18005b7da  xor     edx, edx; hFile
0x18005b7dc  mov     rcx, rbx; lpLibFileName
0x18005b7df  lea     r8d, [rdx+3]; dwFlags
0x18005b7e3  call    cs:__imp_LoadLibraryExW
0x18005b7ea  nop     dword ptr [rax+rax+00h]
0x18005b7ef  mov     rbp, rax
0x18005b7f2  test    rax, rax
0x18005b7f5  jnz     short loc_18005B80A
0x18005b7f7  mov     ebx, gs:68h
0x18005b7ff  test    ebx, ebx
0x18005b801  jnz     short loc_18005B84A
0x18005b803  mov     ebx, 0C1h
0x18005b808  jmp     short loc_18005B84A
0x18005b80a  mov     ebx, r12d
0x18005b80d  test    r15d, r15d
0x18005b810  jnz     short loc_18005B835
0x18005b812  lea     r9d, [r15+10h]; dwFlags
0x18005b816  mov     [rsp+78h+LangId], r12w; LangId
0x18005b81c  mov     r8, rsi; lParam
0x18005b81f  lea     rdx, ?EnumTypesFunc@@YAHPEAUHINSTANCE__@@PEBG_J@Z; lpEnumFunc
0x18005b826  mov     rcx, rbp; hModule
0x18005b829  call    cs:__imp_EnumResourceTypesExW
0x18005b830  nop     dword ptr [rax+rax+00h]
0x18005b835  mov     rcx, rbp; hLibModule
0x18005b838  call    cs:__imp_FreeLibrary
0x18005b83f  nop     dword ptr [rax+rax+00h]
0x18005b844  cmp     [rsi+28h], r12d
0x18005b848  jz      short loc_18005B85C
0x18005b84a  mov     rcx, [rsi+30h]; hMem
0x18005b84e  call    cs:__imp_GlobalFree
0x18005b855  nop     dword ptr [rax+rax+00h]
0x18005b85a  jmp     short loc_18005B875
0x18005b85c  mov     rcx, rdi; hMem
0x18005b85f  call    cs:__imp_GlobalUnlock
0x18005b866  nop     dword ptr [rax+rax+00h]
0x18005b86b  mov     rax, rdi
0x18005b86e  jmp     short loc_18005B8AA
0x18005b870  mov     ebx, 216h
0x18005b875  mov     rcx, rdi; hMem
0x18005b878  call    cs:__imp_GlobalUnlock
0x18005b87f  nop     dword ptr [rax+rax+00h]
0x18005b884  mov     rcx, rdi; hMem
0x18005b887  call    cs:__imp_GlobalFree
0x18005b88e  nop     dword ptr [rax+rax+00h]
0x18005b893  jmp     short loc_18005B89A
0x18005b895  mov     ebx, 57h ; 'W'
0x18005b89a  mov     ecx, ebx; LastError
0x18005b89c  call    cs:__imp_RtlSetLastWin32Error
0x18005b8a3  nop     dword ptr [rax+rax+00h]
0x18005b8a8  xor     eax, eax
0x18005b8aa  add     rsp, 38h
0x18005b8ae  pop     r15
0x18005b8b0  pop     r14
0x18005b8b2  pop     r13
0x18005b8b4  pop     r12
0x18005b8b6  pop     rdi
0x18005b8b7  pop     rsi
0x18005b8b8  pop     rbp
0x18005b8b9  pop     rbx
0x18005b8ba  retn
```
