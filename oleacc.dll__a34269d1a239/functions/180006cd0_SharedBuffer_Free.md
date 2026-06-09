# SharedBuffer_Free

- ea: `0x180006cd0`
- end: `0x180007192`
- name: `SharedBuffer_Free`
- size: `1218`
- prototype: `__int64 __fastcall(int, int, const IID *, LPVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800127b0`

## callees

- `0x180006cd0`
- `0x180007700`
- `0x18001e4c0`
- `0x180047fec`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800070a1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800070a1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006ef1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006f71`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006ef1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006f71`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006f0b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006f95`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006f0b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006f95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000702d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000708d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000702d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000708d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070e3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070d8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800070d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800070b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006f22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007023`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006fa3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006fa3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f47`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f47`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007174`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007187`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007174`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180007187`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006fd8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006fd8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006fb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006fb8`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180006d3b`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180006d3b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180006ebf`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180006ebf`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180007008`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180007008`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180006fee`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180006fee`
- `USER32!EnumWindows` at `0x18000714f`
- `USER32!EnumWindows` at `0x18000714f`

## pseudocode

```c
__int64 __fastcall SharedBuffer_Free(int a1, int a2, const IID *a3, LPVOID *a4)
{
  ATOM v7; // si
  char *v8; // rdx
  DWORD v9; // edi
  int v10; // eax
  int v11; // r8d
  int v12; // edi
  int v13; // edi
  char *v14; // rdx
  HANDLE v15; // rbx
  int v16; // ecx
  int v17; // r8d
  int v18; // ebx
  int v19; // ebx
  __int16 *v20; // rdx
  int i; // ecx
  __int16 v22; // r8
  __int16 *v23; // rdx
  int j; // ecx
  __int16 v25; // r8
  int *v26; // rax
  int v27; // ebx
  int v28; // esi
  SIZE_T v29; // rdi
  size_t v30; // rbx
  HLOCAL v31; // rdi
  char *v32; // rax
  const void *v33; // rsi
  HGLOBAL v34; // rax
  void *v35; // rsi
  void *v36; // rax
  HRESULT v37; // ebx
  HANDLE ProcessHandleFromHwnd; // rsi
  HANDLE CurrentProcess; // rax
  BOOL v41; // ebx
  HANDLE hFileMappingObject; // [rsp+48h] [rbp-69h] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-61h] BYREF
  __int64 v44; // [rsp+58h] [rbp-59h]
  WCHAR Buffer[5]; // [rsp+68h] [rbp-49h] BYREF
  char v46; // [rsp+72h] [rbp-3Fh] BYREF
  __int16 v47; // [rsp+82h] [rbp-2Fh]
  char v48; // [rsp+84h] [rbp-2Dh] BYREF
  __int16 v49; // [rsp+94h] [rbp-1Dh]
  char v50; // [rsp+96h] [rbp-1Bh] BYREF
  __int16 v51; // [rsp+A6h] [rbp-Bh]
  char v52; // [rsp+A8h] [rbp-9h] BYREF
  __int16 v53; // [rsp+B8h] [rbp+7h]
  __int16 v54; // [rsp+BAh] [rbp+9h]

  v7 = a1;
  if ( a1 < 0 )
    return 2147942487LL;
  hFileMappingObject = 0;
  if ( HIWORD(a1)
    || !(_WORD)a1
    || GlobalGetAtomNameW(a1, Buffer, 42) != 41
    || memcmp_0(Buffer, L"MSAA:", 0xAu)
    || v47 != 58
    || v49 != 58
    || v51 != 58
    || v53 != 58
    || v54 )
  {
    return 2147500037LL;
  }
  v8 = &v46;
  v9 = 0;
  v10 = 0;
  while ( v10 < 8 )
  {
    v11 = *(unsigned __int16 *)v8;
    v12 = 16 * v9;
    if ( (unsigned __int16)(v11 - 48) <= 9u )
    {
      v13 = v12 - 48;
      goto LABEL_15;
    }
    if ( (unsigned __int16)(v11 - 65) > 5u )
    {
      if ( (unsigned __int16)(v11 - 97) > 5u )
        return 2147500037LL;
      v13 = v12 - 87;
LABEL_15:
      v9 = v11 + v13;
      ++v10;
      v8 += 2;
    }
    else
    {
      ++v10;
      v9 = v11 + v12 - 55;
      v8 += 2;
    }
  }
  v14 = &v48;
  LODWORD(v15) = 0;
  v16 = 0;
  while ( v16 < 8 )
  {
    v17 = *(unsigned __int16 *)v14;
    v18 = 16 * (_DWORD)v15;
    if ( (unsigned __int16)(v17 - 48) <= 9u )
    {
      v19 = v18 - 48;
      goto LABEL_22;
    }
    if ( (unsigned __int16)(v17 - 65) > 5u )
    {
      if ( (unsigned __int16)(v17 - 97) > 5u )
        return 2147500037LL;
      v19 = v18 - 87;
LABEL_22:
      LODWORD(v15) = v17 + v19;
      ++v16;
      v14 += 2;
    }
    else
    {
      ++v16;
      LODWORD(v15) = v17 + v18 - 55;
      v14 += 2;
    }
  }
  v20 = (__int16 *)&v50;
  for ( i = 0; i < 8; ++i )
  {
    v22 = *v20;
    if ( (unsigned __int16)(*v20 - 48) > 9u && (unsigned __int16)(v22 - 65) > 5u && (unsigned __int16)(v22 - 97) > 5u )
      return 2147500037LL;
    ++v20;
  }
  v23 = (__int16 *)&v52;
  for ( j = 0; j < 8; ++j )
  {
    v25 = *v23;
    if ( (unsigned __int16)(*v23 - 48) > 9u && (unsigned __int16)(v25 - 65) > 5u && (unsigned __int16)(v25 - 97) > 5u )
      return 2147500037LL;
    ++v23;
  }
  GlobalDeleteAtom(v7);
  v15 = (HANDLE)(int)v15;
  if ( v9 == GetCurrentProcessId() )
  {
    hFileMappingObject = (HANDLE)(int)v15;
    goto LABEL_41;
  }
  ProcessHandleFromHwnd = OpenProcess(0x40u, 0, v9);
  if ( !ProcessHandleFromHwnd )
  {
    ppstm = (LPSTREAM)v9;
    v44 = 0;
    EnumWindows(FindWindowFromProcessEnumWindowsProc, (LPARAM)&ppstm);
    if ( !v44 )
      return 2147500037LL;
    ProcessHandleFromHwnd = (HANDLE)GetProcessHandleFromHwnd(v44);
    if ( !ProcessHandleFromHwnd )
      return 2147500037LL;
  }
  CurrentProcess = GetCurrentProcess();
  v41 = DuplicateHandle(ProcessHandleFromHwnd, (HANDLE)(int)v15, CurrentProcess, &hFileMappingObject, 0, 0, 3u);
  CloseHandle(ProcessHandleFromHwnd);
  if ( !v41 )
    return 2147500037LL;
  v15 = hFileMappingObject;
  if ( !hFileMappingObject )
    return 2147500037LL;
LABEL_41:
  v26 = (int *)MapViewOfFile(v15, 0xF001Fu, 0, 0, 0x10u);
  if ( !v26 )
    return 2147500037LL;
  v27 = *v26;
  v28 = v26[2];
  v29 = (unsigned int)v26[3];
  UnmapViewOfFile(v26);
  if ( v27 != -1440944115 || a2 && v28 != GetCurrentProcessId() )
    return 2147500037LL;
  if ( (unsigned int)v29 <= 0x100000 )
  {
    v30 = v29;
    v31 = LocalAlloc(0x40u, v29);
    if ( v31 )
    {
      v32 = (char *)MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, v30 + 16);
      v33 = v32;
      if ( v32 )
      {
        memcpy_0(v31, v32 + 16, v30);
        UnmapViewOfFile(v33);
        v34 = GlobalAlloc(2u, v30);
        v35 = v34;
        if ( !v34 )
        {
          v37 = -2147024882;
          goto LABEL_52;
        }
        v36 = GlobalLock(v34);
        if ( v36 )
        {
          memcpy_0(v36, v31, v30);
          GlobalUnlock(v35);
          ppstm = 0;
          v37 = CreateStreamOnHGlobal(v35, 1, &ppstm);
          if ( v37 < 0 )
          {
            GlobalFree(v35);
          }
          else
          {
            v37 = CoUnmarshalInterface(ppstm, a3, a4);
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          }
LABEL_52:
          LocalFree(v31);
LABEL_53:
          CloseHandle(hFileMappingObject);
          return (unsigned int)v37;
        }
        GlobalFree(v35);
      }
      v37 = -2147467259;
      goto LABEL_52;
    }
    v37 = -2147024882;
    goto LABEL_53;
  }
  CloseHandle(hFileMappingObject);
  return 2147500037LL;
}

```

## disassembly

```asm
0x180006cd0  mov     r11, rsp
0x180006cd3  push    rbp
0x180006cd4  push    rsi
0x180006cd5  push    r12
0x180006cd7  push    r14
0x180006cd9  push    r15
0x180006cdb  lea     rbp, [r11-5Fh]
0x180006cdf  sub     rsp, 0E0h
0x180006ce6  mov     rax, cs:__security_cookie
0x180006ced  xor     rax, rsp
0x180006cf0  mov     [rbp+57h+var_40], rax
0x180006cf4  mov     r12, r9
0x180006cf7  mov     r15, r8
0x180006cfa  mov     r14d, edx
0x180006cfd  mov     esi, ecx
0x180006cff  test    ecx, ecx
0x180006d01  js      loc_180007103
0x180006d07  mov     [r11+10h], rbx
0x180006d0b  mov     eax, ecx
0x180006d0d  mov     [r11-30h], rdi
0x180006d11  mov     [r11-38h], r13
0x180006d15  xor     r13d, r13d
0x180006d18  shr     eax, 10h
0x180006d1b  mov     [rbp+57h+hFileMappingObject], r13
0x180006d1f  test    ax, ax
0x180006d22  jnz     loc_180007044
0x180006d28  test    si, si
0x180006d2b  jz      loc_180007044
0x180006d31  mov     r8d, 2Ah ; '*'; nSize
0x180006d37  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180006d3b  call    cs:__imp_GlobalGetAtomNameW
0x180006d41  cmp     eax, 29h ; ')'
0x180006d44  jnz     loc_180007044
0x180006d4a  mov     r8d, 0Ah; Size
0x180006d50  lea     rdx, aMsaa_0; "MSAA:"
0x180006d57  lea     rcx, [rbp+57h+Buffer]; Buf1
0x180006d5b  call    memcmp_0
0x180006d60  test    eax, eax
0x180006d62  jnz     loc_180007044
0x180006d68  cmp     [rbp+57h+var_86], 3Ah ; ':'
0x180006d6d  jnz     loc_180007044
0x180006d73  cmp     [rbp+57h+var_74], 3Ah ; ':'
0x180006d78  jnz     loc_180007044
0x180006d7e  cmp     [rbp+57h+var_62], 3Ah ; ':'
0x180006d83  jnz     loc_180007044
0x180006d89  cmp     [rbp+57h+var_50], 3Ah ; ':'
0x180006d8e  jnz     loc_180007044
0x180006d94  cmp     [rbp+57h+var_4E], r13w
0x180006d99  jnz     loc_180007044
0x180006d9f  lea     rdx, [rbp+57h+var_96]
0x180006da3  mov     edi, r13d
0x180006da6  mov     eax, r13d
0x180006da9  nop     dword ptr [rax+00000000h]
0x180006db0  cmp     eax, 8
0x180006db3  jge     short loc_180006DF0
0x180006db5  movzx   r8d, word ptr [rdx]
0x180006db9  shl     edi, 4
0x180006dbc  lea     ecx, [r8-30h]
0x180006dc0  cmp     cx, 9
0x180006dc4  ja      short loc_180006DD4
0x180006dc6  add     edi, 0FFFFFFD0h
0x180006dc9  add     edi, r8d
0x180006dcc  inc     eax
0x180006dce  add     rdx, 2
0x180006dd2  jmp     short loc_180006DB0
0x180006dd4  lea     ecx, [r8-41h]
0x180006dd8  cmp     cx, 5
0x180006ddc  ja      loc_18000710D
0x180006de2  add     edi, 0FFFFFFC9h
0x180006de5  inc     eax
0x180006de7  add     edi, r8d
0x180006dea  add     rdx, 2
0x180006dee  jmp     short loc_180006DB0
0x180006df0  lea     rdx, [rbp+57h+var_84]
0x180006df4  mov     ebx, r13d
0x180006df7  mov     ecx, r13d
0x180006dfa  nop     word ptr [rax+rax+00h]
0x180006e00  cmp     ecx, 8
0x180006e03  jge     short loc_180006E40
0x180006e05  movzx   r8d, word ptr [rdx]
0x180006e09  shl     ebx, 4
0x180006e0c  lea     eax, [r8-30h]
0x180006e10  cmp     ax, 9
0x180006e14  ja      short loc_180006E24
0x180006e16  add     ebx, 0FFFFFFD0h
0x180006e19  add     ebx, r8d
0x180006e1c  inc     ecx
0x180006e1e  add     rdx, 2
0x180006e22  jmp     short loc_180006E00
0x180006e24  lea     eax, [r8-41h]
0x180006e28  cmp     ax, 5
0x180006e2c  ja      loc_180007123
0x180006e32  add     ebx, 0FFFFFFC9h
0x180006e35  inc     ecx
0x180006e37  add     ebx, r8d
0x180006e3a  add     rdx, 2
0x180006e3e  jmp     short loc_180006E00
0x180006e40  lea     rdx, [rbp+57h+var_72]
0x180006e44  mov     ecx, r13d
0x180006e47  cmp     ecx, 8
0x180006e4a  jge     short loc_180006E7E
0x180006e4c  movzx   r8d, word ptr [rdx]
0x180006e50  lea     eax, [r8-30h]
0x180006e54  cmp     ax, 9
0x180006e58  ja      short loc_180006E62
0x180006e5a  inc     ecx
0x180006e5c  add     rdx, 2
0x180006e60  jmp     short loc_180006E47
0x180006e62  lea     eax, [r8-41h]
0x180006e66  cmp     ax, 5
0x180006e6a  jbe     short loc_180006E5A
0x180006e6c  sub     r8w, 61h ; 'a'
0x180006e71  cmp     r8w, 5
0x180006e76  ja      loc_180007044
0x180006e7c  jmp     short loc_180006E5A
0x180006e7e  lea     rdx, [rbp+57h+var_60]
0x180006e82  mov     ecx, r13d
0x180006e85  cmp     ecx, 8
0x180006e88  jge     short loc_180006EBC
0x180006e8a  movzx   r8d, word ptr [rdx]
0x180006e8e  lea     eax, [r8-30h]
0x180006e92  cmp     ax, 9
0x180006e96  ja      short loc_180006EA0
0x180006e98  inc     ecx
0x180006e9a  add     rdx, 2
0x180006e9e  jmp     short loc_180006E85
0x180006ea0  lea     eax, [r8-41h]
0x180006ea4  cmp     ax, 5
0x180006ea8  jbe     short loc_180006E98
0x180006eaa  sub     r8w, 61h ; 'a'
0x180006eaf  cmp     r8w, 5
0x180006eb4  ja      loc_180007044
0x180006eba  jmp     short loc_180006E98
0x180006ebc  movzx   ecx, si; nAtom
0x180006ebf  call    cs:__imp_GlobalDeleteAtom
0x180006ec5  movsxd  rbx, ebx
0x180006ec8  call    cs:__imp_GetCurrentProcessId
0x180006ece  cmp     edi, eax
0x180006ed0  jnz     loc_180007097
0x180006ed6  mov     [rbp+57h+hFileMappingObject], rbx
0x180006eda  xor     r9d, r9d; dwFileOffsetLow
0x180006edd  mov     [rsp+100h+dwNumberOfBytesToMap], 10h; dwNumberOfBytesToMap
0x180006ee6  xor     r8d, r8d; dwFileOffsetHigh
0x180006ee9  mov     edx, 0F001Fh; dwDesiredAccess
0x180006eee  mov     rcx, rbx; hFileMappingObject
0x180006ef1  call    cs:__imp_MapViewOfFile
0x180006ef7  test    rax, rax
0x180006efa  jz      loc_180007044
0x180006f00  mov     ebx, [rax]
0x180006f02  mov     rcx, rax; lpBaseAddress
0x180006f05  mov     esi, [rax+8]
0x180006f08  mov     edi, [rax+0Ch]
0x180006f0b  call    cs:__imp_UnmapViewOfFile
0x180006f11  cmp     ebx, 0AA1CF00Dh
0x180006f17  jnz     loc_180007044
0x180006f1d  test    r14d, r14d
0x180006f20  jz      short loc_180006F30
0x180006f22  call    cs:__imp_GetCurrentProcessId
0x180006f28  cmp     esi, eax
0x180006f2a  jnz     loc_180007044
0x180006f30  cmp     edi, 100000h
0x180006f36  ja      loc_180007084
0x180006f3c  mov     rdx, rdi; uBytes
0x180006f3f  mov     ecx, 40h ; '@'; uFlags
0x180006f44  mov     rbx, rdi
0x180006f47  call    cs:__imp_LocalAlloc
0x180006f4d  mov     rdi, rax
0x180006f50  test    rax, rax
0x180006f53  jz      loc_180007167
0x180006f59  mov     rcx, [rbp+57h+hFileMappingObject]; hFileMappingObject
0x180006f5d  lea     rax, [rbx+10h]
0x180006f61  xor     r9d, r9d; dwFileOffsetLow
0x180006f64  mov     [rsp+100h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180006f69  xor     r8d, r8d; dwFileOffsetHigh
0x180006f6c  mov     edx, 0F001Fh; dwDesiredAccess
0x180006f71  call    cs:__imp_MapViewOfFile
0x180006f77  mov     rsi, rax
0x180006f7a  test    rax, rax
0x180006f7d  jz      loc_18000717A
0x180006f83  lea     rdx, [rax+10h]; Src
0x180006f87  mov     r8, rbx; Size
0x180006f8a  mov     rcx, rdi; void *
0x180006f8d  call    memcpy_0
0x180006f92  mov     rcx, rsi; lpBaseAddress
0x180006f95  call    cs:__imp_UnmapViewOfFile
0x180006f9b  mov     rdx, rbx; dwBytes
0x180006f9e  mov     ecx, 2; uFlags
0x180006fa3  call    cs:__imp_GlobalAlloc
0x180006fa9  mov     rsi, rax
0x180006fac  test    rax, rax
0x180006faf  jz      loc_18000707D
0x180006fb5  mov     rcx, rax; hMem
0x180006fb8  call    cs:__imp_GlobalLock
0x180006fbe  test    rax, rax
0x180006fc1  jz      loc_180007171
0x180006fc7  mov     r8, rbx; Size
0x180006fca  mov     rdx, rdi; Src
0x180006fcd  mov     rcx, rax; void *
0x180006fd0  call    memcpy_0
0x180006fd5  mov     rcx, rsi; hMem
0x180006fd8  call    cs:__imp_GlobalUnlock
0x180006fde  lea     r8, [rbp+57h+ppstm]; ppstm
0x180006fe2  mov     [rbp+57h+ppstm], r13
0x180006fe6  mov     edx, 1; fDeleteOnRelease
0x180006feb  mov     rcx, rsi; hGlobal
0x180006fee  call    cs:__imp_CreateStreamOnHGlobal
0x180006ff4  mov     ebx, eax
0x180006ff6  test    eax, eax
0x180006ff8  js      loc_180007184
0x180006ffe  mov     rcx, [rbp+57h+ppstm]; pStm
0x180007002  mov     r8, r12; ppv
0x180007005  mov     rdx, r15; riid
0x180007008  call    cs:__imp_CoUnmarshalInterface
0x18000700e  mov     rcx, [rbp+57h+ppstm]
0x180007012  mov     ebx, eax
0x180007014  mov     rax, [rcx]
0x180007017  mov     rax, [rax+10h]
0x18000701b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007020  mov     rcx, rdi; hMem
0x180007023  call    cs:__imp_LocalFree
0x180007029  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x18000702d  call    cs:__imp_CloseHandle
0x180007033  mov     eax, ebx
0x180007035  jmp     short loc_180007049
0x180007037  call    GetProcessHandleFromHwnd
0x18000703c  mov     rsi, rax
0x18000703f  test    rax, rax
0x180007042  jnz     short loc_1800070B3
0x180007044  mov     eax, 80004005h
0x180007049  mov     rdi, [rsp+0D8h]
0x180007051  mov     rbx, [rsp+100h+arg_8]
0x180007059  mov     r13, [rsp+100h+var_30]
0x180007061  mov     rcx, [rbp+57h+var_40]
0x180007065  xor     rcx, rsp; StackCookie
0x180007068  call    __security_check_cookie
0x18000706d  add     rsp, 0E0h
0x180007074  pop     r15
0x180007076  pop     r14
0x180007078  pop     r12
0x18000707a  pop     rsi
0x18000707b  pop     rbp
0x18000707c  retn
0x18000707d  mov     ebx, 8007000Eh
0x180007082  jmp     short loc_180007020
0x180007084  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x180007088  mov     ebx, 80004005h
0x18000708d  call    cs:__imp_CloseHandle
0x180007093  mov     eax, ebx
0x180007095  jmp     short loc_180007049
0x180007097  mov     r8d, edi; dwProcessId
0x18000709a  xor     edx, edx; bInheritHandle
0x18000709c  mov     ecx, 40h ; '@'; dwDesiredAccess
0x1800070a1  call    cs:__imp_OpenProcess
0x1800070a7  mov     rsi, rax
0x1800070aa  test    rax, rax
0x1800070ad  jz      loc_180007139
0x1800070b3  call    cs:__imp_GetCurrentProcess
0x1800070b9  mov     dword ptr [rsp+30h], 3; dwOptions
0x1800070c1  lea     r9, [rbp+57h+hFileMappingObject]; lpTargetHandle
0x1800070c5  mov     r8, rax; hTargetProcessHandle
0x1800070c8  mov     [rsp+100h+bInheritHandle], r13d; bInheritHandle
0x1800070cd  mov     rdx, rbx; hSourceHandle
0x1800070d0  mov     dword ptr [rsp+100h+dwNumberOfBytesToMap], r13d; dwDesiredAccess
0x1800070d5  mov     rcx, rsi; hSourceProcessHandle
0x1800070d8  call    cs:__imp_DuplicateHandle
0x1800070de  mov     rcx, rsi; hObject
0x1800070e1  mov     ebx, eax
0x1800070e3  call    cs:__imp_CloseHandle
0x1800070e9  test    ebx, ebx
0x1800070eb  jz      loc_180007044
0x1800070f1  mov     rbx, [rbp+57h+hFileMappingObject]
0x1800070f5  test    rbx, rbx
0x1800070f8  jnz     loc_180006EDA
0x1800070fe  jmp     loc_180007044
0x180007103  mov     eax, 80070057h
0x180007108  jmp     loc_180007061
0x18000710d  lea     ecx, [r8-61h]
0x180007111  cmp     cx, 5
0x180007115  ja      loc_180007044
0x18000711b  add     edi, 0FFFFFFA9h
0x18000711e  jmp     loc_180006DC9
0x180007123  lea     eax, [r8-61h]
0x180007127  cmp     ax, 5
0x18000712b  ja      loc_180007044
0x180007131  add     ebx, 0FFFFFFA9h
0x180007134  jmp     loc_180006E19
0x180007139  lea     rdx, [rbp+57h+ppstm]; lParam
0x18000713d  mov     dword ptr [rbp+57h+ppstm+4], r13d
0x180007141  lea     rcx, ?FindWindowFromProcessEnumWindowsProc@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180007148  mov     dword ptr [rbp+57h+ppstm], edi
0x18000714b  mov     [rbp+57h+var_B0], r13
0x18000714f  call    cs:__imp_EnumWindows
0x180007155  mov     rcx, [rbp+57h+var_B0]
0x180007159  test    rcx, rcx
0x18000715c  jz      loc_180007044
0x180007162  jmp     loc_180007037
0x180007167  mov     ebx, 8007000Eh
0x18000716c  jmp     loc_180007029
0x180007171  mov     rcx, rsi; hMem
0x180007174  call    cs:__imp_GlobalFree
  ... truncated ...
```
