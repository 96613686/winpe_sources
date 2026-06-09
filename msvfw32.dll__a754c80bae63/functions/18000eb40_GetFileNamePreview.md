# GetFileNamePreview

- ea: `0x18000eb40`
- end: `0x18000ed0e`
- name: `GetFileNamePreview`
- size: `462`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000efa0`
- `0x18000efb0`
- `0x18000efd0`
- `0x18000eff0`
- `0x180010c08`

## callees

- `0x1800014b0`
- `0x180002118`
- `0x180002198`
- `0x1800022cc`
- `0x18000eb40`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ecda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec0d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ec52`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000ec52`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ecbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000ecbf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ecb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ecc8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ecb6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000ecc8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ecd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000ecd1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ec49`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000ec49`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000ebf3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000ebf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ebc0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000ebc0`

## string_xrefs

- `0x18000eb86`: `GetOpenFileName`
- `0x18000ebd3`: `\COMDLG32.DLL`

## pseudocode

```c
__int64 __fastcall GetFileNamePreview(__int64 a1, int a2, size_t *a3)
{
  const char *v3; // r9
  int v5; // r14d
  size_t v6; // r10
  const char *v7; // r8
  HMODULE LibraryW; // rax
  HMODULE v9; // rdi
  FARPROC ProcAddress; // rbp
  int v11; // ecx
  HGLOBAL v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rsi
  unsigned int v15; // ebp
  HGLOBAL v16; // rax
  HGLOBAL v17; // rax
  size_t v19; // [rsp+20h] [rbp-288h]
  char pszDest[64]; // [rsp+30h] [rbp-278h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-238h] BYREF

  v3 = "GetSaveFileName";
  v5 = (int)a3;
  if ( !a2 )
    v3 = "GetOpenFileName";
  StringCopyWorkerA(pszDest, 0x3Cu, a3, v3, v19);
  v7 = "W";
  if ( !v5 )
    v7 = "A";
  StringCchCatA(pszDest, v6, v7);
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    return 0;
  if ( StringCchCatW(Buffer, 0x104u, L"\\COMDLG32.DLL") < 0 )
    return 0;
  LibraryW = LoadLibraryW(Buffer);
  v9 = LibraryW;
  if ( !LibraryW )
    return 0;
  ProcAddress = GetProcAddress(LibraryW, pszDest);
  if ( !ProcAddress )
    return 0;
  v11 = *(_DWORD *)(a1 + 96);
  if ( (v11 & 4) == 0 )
  {
    v11 |= 4u;
    *(_DWORD *)(a1 + 96) = v11;
  }
  if ( (v11 & 0x20010) == 0x10 )
    *(_DWORD *)(a1 + 96) = v11 & 0xFFFFFFEF;
  v12 = GlobalAlloc(0x42u, 0x180u);
  v13 = GlobalLock(v12);
  v14 = v13;
  if ( v13 )
  {
    *(_DWORD *)v13 = v5;
    v13[5] = *(_QWORD *)(a1 + 120);
    *((_DWORD *)v13 + 8) = *(_DWORD *)(a1 + 96);
    v13[3] = *(_QWORD *)(a1 + 112);
    *(_DWORD *)(a1 + 96) |= 0x20u;
    *(_QWORD *)(a1 + 120) = GetFileNamePreviewHook;
    *(_QWORD *)(a1 + 112) = v13;
    v15 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
    *(_QWORD *)(a1 + 120) = v14[5];
    *(_DWORD *)(a1 + 96) = *((_DWORD *)v14 + 8);
    v16 = GlobalHandle(v14);
    GlobalUnlock(v16);
    v17 = GlobalHandle(v14);
    GlobalFree(v17);
  }
  else
  {
    v15 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a1);
  }
  FreeLibrary(v9);
  return v15;
}

```

## disassembly

```asm
0x18000eb40  mov     [rsp+arg_8], rbx
0x18000eb45  mov     [rsp+arg_10], rbp
0x18000eb4a  push    rsi
0x18000eb4b  push    rdi
0x18000eb4c  push    r14
0x18000eb4e  sub     rsp, 290h
0x18000eb55  mov     rax, cs:__security_cookie
0x18000eb5c  xor     rax, rsp
0x18000eb5f  mov     [rsp+2A8h+var_28], rax
0x18000eb67  mov     r10d, 3Ch ; '<'
0x18000eb6d  lea     r9, aGetsavefilenam_1; "GetSaveFileName"
0x18000eb74  mov     rbx, rcx
0x18000eb77  test    edx, edx
0x18000eb79  mov     edx, r10d; cchDest
0x18000eb7c  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18000eb81  mov     r14d, r8d
0x18000eb84  jnz     short loc_18000EB8D
0x18000eb86  lea     r9, aGetopenfilenam_2; "GetOpenFileName"
0x18000eb8d  call    StringCopyWorkerA
0x18000eb92  lea     rax, aA; "A"
0x18000eb99  test    r14d, r14d
0x18000eb9c  lea     r8, aW; "W"
0x18000eba3  mov     rdx, r10; cchDest
0x18000eba6  cmovz   r8, rax; pszSrc
0x18000ebaa  lea     rcx, [rsp+2A8h+pszDest]; pszDest
0x18000ebaf  call    StringCchCatA
0x18000ebb4  mov     edi, 104h
0x18000ebb9  lea     rcx, [rsp+2A8h+Buffer]; lpBuffer
0x18000ebbe  mov     edx, edi; uSize
0x18000ebc0  call    cs:__imp_GetSystemDirectoryW
0x18000ebc6  dec     eax
0x18000ebc8  cmp     eax, 102h
0x18000ebcd  ja      loc_18000ECE4
0x18000ebd3  lea     r8, aComdlg32Dll; "\\COMDLG32.DLL"
0x18000ebda  mov     edx, edi; cchDest
0x18000ebdc  lea     rcx, [rsp+2A8h+Buffer]; pszDest
0x18000ebe1  call    StringCchCatW
0x18000ebe6  test    eax, eax
0x18000ebe8  js      loc_18000ECE4
0x18000ebee  lea     rcx, [rsp+2A8h+Buffer]; lpLibFileName
0x18000ebf3  call    cs:__imp_LoadLibraryW
0x18000ebf9  mov     rdi, rax
0x18000ebfc  test    rax, rax
0x18000ebff  jz      loc_18000ECE4
0x18000ec05  lea     rdx, [rsp+2A8h+pszDest]; lpProcName
0x18000ec0a  mov     rcx, rax; hModule
0x18000ec0d  call    cs:__imp_GetProcAddress
0x18000ec13  mov     rbp, rax
0x18000ec16  test    rax, rax
0x18000ec19  jz      loc_18000ECE4
0x18000ec1f  mov     ecx, [rbx+60h]
0x18000ec22  test    cl, 4
0x18000ec25  jnz     short loc_18000EC2D
0x18000ec27  or      ecx, 4
0x18000ec2a  mov     [rbx+60h], ecx
0x18000ec2d  mov     eax, ecx
0x18000ec2f  and     eax, 20010h
0x18000ec34  cmp     eax, 10h
0x18000ec37  jnz     short loc_18000EC3F
0x18000ec39  and     ecx, 0FFFFFFEFh
0x18000ec3c  mov     [rbx+60h], ecx
0x18000ec3f  mov     edx, 180h; dwBytes
0x18000ec44  mov     ecx, 42h ; 'B'; uFlags
0x18000ec49  call    cs:__imp_GlobalAlloc
0x18000ec4f  mov     rcx, rax; hMem
0x18000ec52  call    cs:__imp_GlobalLock
0x18000ec58  mov     rsi, rax
0x18000ec5b  mov     rcx, rbx
0x18000ec5e  test    rax, rax
0x18000ec61  jnz     short loc_18000EC6F
0x18000ec63  mov     rax, rbp
0x18000ec66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec6b  mov     ebp, eax
0x18000ec6d  jmp     short loc_18000ECD7
0x18000ec6f  mov     [rax], r14d
0x18000ec72  mov     rax, [rbx+78h]
0x18000ec76  mov     [rsi+28h], rax
0x18000ec7a  mov     eax, [rbx+60h]
0x18000ec7d  mov     [rsi+20h], eax
0x18000ec80  mov     rax, [rbx+70h]
0x18000ec84  mov     [rsi+18h], rax
0x18000ec88  lea     rax, GetFileNamePreviewHook
0x18000ec8f  or      dword ptr [rbx+60h], 20h
0x18000ec93  mov     [rbx+78h], rax
0x18000ec97  mov     rax, rbp
0x18000ec9a  mov     [rbx+70h], rsi
0x18000ec9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca3  mov     ebp, eax
0x18000eca5  mov     rcx, rsi; pMem
0x18000eca8  mov     rax, [rsi+28h]
0x18000ecac  mov     [rbx+78h], rax
0x18000ecb0  mov     eax, [rsi+20h]
0x18000ecb3  mov     [rbx+60h], eax
0x18000ecb6  call    cs:__imp_GlobalHandle
0x18000ecbc  mov     rcx, rax; hMem
0x18000ecbf  call    cs:__imp_GlobalUnlock
0x18000ecc5  mov     rcx, rsi; pMem
0x18000ecc8  call    cs:__imp_GlobalHandle
0x18000ecce  mov     rcx, rax; hMem
0x18000ecd1  call    cs:__imp_GlobalFree
0x18000ecd7  mov     rcx, rdi; hLibModule
0x18000ecda  call    cs:__imp_FreeLibrary
0x18000ece0  mov     eax, ebp
0x18000ece2  jmp     short loc_18000ECE6
0x18000ece4  xor     eax, eax
0x18000ece6  mov     rcx, [rsp+2A8h+var_28]
0x18000ecee  xor     rcx, rsp; StackCookie
0x18000ecf1  call    __security_check_cookie
0x18000ecf6  lea     r11, [rsp+2A8h+var_18]
0x18000ecfe  mov     rbx, [r11+28h]
0x18000ed02  mov     rbp, [r11+30h]
0x18000ed06  mov     rsp, r11
0x18000ed09  pop     r14
0x18000ed0b  pop     rdi
0x18000ed0c  pop     rsi
0x18000ed0d  retn
```
