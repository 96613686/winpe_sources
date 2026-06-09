# GetExeInformation(ushort const *,ushort *,ulong,uchar *)

- ea: `0x180008250`
- end: `0x1800084cf`
- name: `?GetExeInformation@@YAHPEBGPEAGKPEAE@Z`
- size: `639`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008c38`
- `0x1800096e0`

## callees

- `0x180007ae0`
- `0x180007b54`
- `0x180008250`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180008349`
- `KERNEL32!HeapAlloc` at `0x180008349`
- `KERNEL32!GetProcessHeap` at `0x180008338`
- `KERNEL32!GetProcessHeap` at `0x180008489`
- `KERNEL32!GetProcessHeap` at `0x180008338`
- `KERNEL32!GetProcessHeap` at `0x180008489`
- `KERNEL32!HeapFree` at `0x180008497`
- `KERNEL32!HeapFree` at `0x180008497`
- `SHLWAPI!PathFileExistsW` at `0x1800082c4`
- `SHLWAPI!PathFileExistsW` at `0x1800082c4`
- `SHLWAPI!PathRemoveExtensionW` at `0x18000845d`
- `SHLWAPI!PathRemoveExtensionW` at `0x18000845d`
- `SHLWAPI!PathFindFileNameW` at `0x180008467`
- `SHLWAPI!PathFindFileNameW` at `0x180008467`
- `VERSION!GetFileVersionInfoW` at `0x180008369`
- `VERSION!GetFileVersionInfoW` at `0x180008369`
- `VERSION!VerQueryValueW` at `0x18000838b`
- `VERSION!VerQueryValueW` at `0x1800083db`
- `VERSION!VerQueryValueW` at `0x18000840f`
- `VERSION!VerQueryValueW` at `0x180008443`
- `VERSION!VerQueryValueW` at `0x18000838b`
- `VERSION!VerQueryValueW` at `0x1800083db`
- `VERSION!VerQueryValueW` at `0x18000840f`
- `VERSION!VerQueryValueW` at `0x180008443`
- `VERSION!GetFileVersionInfoSizeW` at `0x180008325`
- `VERSION!GetFileVersionInfoSizeW` at `0x180008325`

## pseudocode

```c
_BOOL8 __fastcall GetExeInformation(LPCWSTR pszPath, unsigned __int16 *a2, __int64 a3, unsigned __int8 *a4)
{
  const WCHAR *v6; // rdi
  void *v7; // rbx
  WCHAR *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  DWORD FileVersionInfoSizeW; // edi
  HANDLE ProcessHeap; // rax
  void *v14; // rax
  void *FileNameW; // r8
  int v16; // edi
  HANDLE v17; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  DWORD dwHandle; // [rsp+34h] [rbp-CCh] BYREF
  LPVOID v22; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubBlock[64]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR tstrFilename[264]; // [rsp+D0h] [rbp-30h] BYREF

  puLen = 0;
  v22 = 0;
  v6 = pszPath;
  dwHandle = 0;
  lpBuffer = 0;
  AslLogCallPrintf(3, "GetExeInformation", 544, "AppName: %ws", pszPath);
  *a4 = 0;
  if ( !PathFileExistsW(v6) )
    return 0;
  v7 = 0;
  v8 = tstrFilename;
  v9 = 2147483646;
  v10 = 260;
  do
  {
    if ( !v9 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v9;
    --v10;
  }
  while ( v10 );
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  if ( v10 )
  {
    FileVersionInfoSizeW = GetFileVersionInfoSizeW(tstrFilename, &dwHandle);
    if ( FileVersionInfoSizeW )
    {
      *a4 = 1;
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 8u, FileVersionInfoSizeW);
      v7 = v14;
      if ( v14 )
      {
        if ( GetFileVersionInfoW(tstrFilename, dwHandle, FileVersionInfoSizeW, v14) )
        {
          if ( !VerQueryValueW(v7, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen)
            || !puLen
            || (LODWORD(v19) = *((unsigned __int16 *)lpBuffer + 1),
                (int)StringCchPrintfW(
                       SubBlock,
                       0x3Cu,
                       L"\\StringFileInfo\\%04X%04X\\FileDescription",
                       *(unsigned __int16 *)lpBuffer,
                       v19) < 0)
            || !VerQueryValueW(v7, SubBlock, &v22, &puLen) )
          {
            if ( ((int)StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\040904E4\\FileDescription") < 0
               || !VerQueryValueW(v7, SubBlock, &v22, &puLen))
              && (int)StringCchPrintfW(SubBlock, 0x3Cu, L"\\StringFileInfo\\04090000\\FileDescription") >= 0 )
            {
              VerQueryValueW(v7, SubBlock, &v22, &puLen);
            }
          }
        }
      }
    }
  }
  FileNameW = v22;
  if ( !v22 || !*(_WORD *)v22 )
  {
    PathRemoveExtensionW(tstrFilename);
    FileNameW = PathFindFileNameW(tstrFilename);
    v22 = FileNameW;
  }
  v16 = StringCchCopyW(a2, 0x100u, (const unsigned __int16 *)FileNameW);
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  return v16 >= 0;
}

```

## disassembly

```asm
0x180008250  mov     [rsp-8+arg_10], rbx
0x180008255  push    rbp
0x180008256  push    rsi
0x180008257  push    rdi
0x180008258  push    r14
0x18000825a  push    r15
0x18000825c  lea     rbp, [rsp-1F0h]
0x180008264  sub     rsp, 2F0h
0x18000826b  mov     rax, cs:__security_cookie
0x180008272  xor     rax, rsp
0x180008275  mov     [rbp+210h+var_30], rax
0x18000827c  xor     r15d, r15d
0x18000827f  mov     [rsp+310h+var_2F0], rcx
0x180008284  mov     rsi, r9
0x180008287  mov     [rsp+310h+puLen], r15d
0x18000828c  mov     r14, rdx
0x18000828f  mov     [rsp+310h+var_2D8], r15
0x180008294  mov     rdi, rcx
0x180008297  mov     [rsp+310h+dwHandle], r15d
0x18000829c  lea     ecx, [r15+3]
0x1800082a0  mov     [rsp+310h+lpBuffer], r15
0x1800082a5  lea     r9, aAppnameWs; "AppName: %ws"
0x1800082ac  mov     r8d, 220h
0x1800082b2  lea     rdx, aGetexeinformat; "GetExeInformation"
0x1800082b9  call    AslLogCallPrintf
0x1800082be  mov     rcx, rdi; pszPath
0x1800082c1  mov     [rsi], r15b
0x1800082c4  call    cs:__imp_PathFileExistsW
0x1800082ca  test    eax, eax
0x1800082cc  jz      loc_1800084A7
0x1800082d2  mov     ebx, r15d
0x1800082d5  lea     rax, [rbp+210h+tstrFilename]
0x1800082d9  mov     ecx, 7FFFFFFEh
0x1800082de  mov     edx, 104h
0x1800082e3  test    rcx, rcx
0x1800082e6  jz      short loc_180008307
0x1800082e8  movzx   r8d, word ptr [rdi]
0x1800082ec  test    r8w, r8w
0x1800082f0  jz      short loc_180008307
0x1800082f2  mov     [rax], r8w
0x1800082f6  add     rdi, 2
0x1800082fa  add     rax, 2
0x1800082fe  dec     rcx
0x180008301  sub     rdx, 1
0x180008305  jnz     short loc_1800082E3
0x180008307  test    rdx, rdx
0x18000830a  lea     rcx, [rax-2]
0x18000830e  cmovnz  rcx, rax
0x180008312  mov     [rcx], r15w
0x180008316  jz      loc_180008449
0x18000831c  lea     rdx, [rsp+310h+dwHandle]; lpdwHandle
0x180008321  lea     rcx, [rbp+210h+tstrFilename]; lptstrFilename
0x180008325  call    cs:__imp_GetFileVersionInfoSizeW
0x18000832b  mov     edi, eax
0x18000832d  test    eax, eax
0x18000832f  jz      loc_180008449
0x180008335  mov     byte ptr [rsi], 1
0x180008338  call    cs:__imp_GetProcessHeap
0x18000833e  mov     r8d, edi; dwBytes
0x180008341  mov     edx, 8; dwFlags
0x180008346  mov     rcx, rax; hHeap
0x180008349  call    cs:__imp_HeapAlloc
0x18000834f  mov     rbx, rax
0x180008352  test    rax, rax
0x180008355  jz      loc_180008449
0x18000835b  mov     edx, [rsp+310h+dwHandle]; dwHandle
0x18000835f  lea     rcx, [rbp+210h+tstrFilename]; lptstrFilename
0x180008363  mov     r9, rax; lpData
0x180008366  mov     r8d, edi; dwLen
0x180008369  call    cs:__imp_GetFileVersionInfoW
0x18000836f  test    eax, eax
0x180008371  jz      loc_180008449
0x180008377  lea     r9, [rsp+310h+puLen]; puLen
0x18000837c  mov     rcx, rbx; pBlock
0x18000837f  lea     r8, [rsp+310h+lpBuffer]; lplpBuffer
0x180008384  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18000838b  call    cs:__imp_VerQueryValueW
0x180008391  mov     edi, 3Ch ; '<'
0x180008396  test    eax, eax
0x180008398  jz      short loc_1800083E5
0x18000839a  cmp     [rsp+310h+puLen], r15d
0x18000839f  jbe     short loc_1800083E5
0x1800083a1  mov     rax, [rsp+310h+lpBuffer]
0x1800083a6  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\FileDescrip"...
0x1800083ad  mov     edx, edi; unsigned __int64
0x1800083af  movzx   ecx, word ptr [rax+2]
0x1800083b3  movzx   r9d, word ptr [rax]
0x1800083b7  mov     dword ptr [rsp+310h+var_2F0], ecx
0x1800083bb  lea     rcx, [rsp+310h+SubBlock]; unsigned __int16 *
0x1800083c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800083c5  test    eax, eax
0x1800083c7  js      short loc_1800083E5
0x1800083c9  lea     r9, [rsp+310h+puLen]; puLen
0x1800083ce  mov     rcx, rbx; pBlock
0x1800083d1  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x1800083d6  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x1800083db  call    cs:__imp_VerQueryValueW
0x1800083e1  test    eax, eax
0x1800083e3  jnz     short loc_180008449
0x1800083e5  lea     r8, aStringfileinfo_8; "\\StringFileInfo\\040904E4\\FileDescrip"...
0x1800083ec  mov     rdx, rdi; unsigned __int64
0x1800083ef  lea     rcx, [rsp+310h+SubBlock]; unsigned __int16 *
0x1800083f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800083f9  test    eax, eax
0x1800083fb  js      short loc_180008419
0x1800083fd  lea     r9, [rsp+310h+puLen]; puLen
0x180008402  mov     rcx, rbx; pBlock
0x180008405  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x18000840a  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x18000840f  call    cs:__imp_VerQueryValueW
0x180008415  test    eax, eax
0x180008417  jnz     short loc_180008449
0x180008419  lea     r8, aStringfileinfo_0; "\\StringFileInfo\\04090000\\FileDescrip"...
0x180008420  mov     rdx, rdi; unsigned __int64
0x180008423  lea     rcx, [rsp+310h+SubBlock]; unsigned __int16 *
0x180008428  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000842d  test    eax, eax
0x18000842f  js      short loc_180008449
0x180008431  lea     r9, [rsp+310h+puLen]; puLen
0x180008436  mov     rcx, rbx; pBlock
0x180008439  lea     r8, [rsp+310h+var_2D8]; lplpBuffer
0x18000843e  lea     rdx, [rsp+310h+SubBlock]; lpSubBlock
0x180008443  call    cs:__imp_VerQueryValueW
0x180008449  mov     r8, [rsp+310h+var_2D8]
0x18000844e  test    r8, r8
0x180008451  jz      short loc_180008459
0x180008453  cmp     r15w, [r8]
0x180008457  jnz     short loc_180008475
0x180008459  lea     rcx, [rbp+210h+tstrFilename]; pszPath
0x18000845d  call    cs:__imp_PathRemoveExtensionW
0x180008463  lea     rcx, [rbp+210h+tstrFilename]; pszPath
0x180008467  call    cs:__imp_PathFindFileNameW
0x18000846d  mov     r8, rax; unsigned __int16 *
0x180008470  mov     [rsp+310h+var_2D8], rax
0x180008475  mov     edx, 100h; unsigned __int64
0x18000847a  mov     rcx, r14; unsigned __int16 *
0x18000847d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008482  mov     edi, eax
0x180008484  test    rbx, rbx
0x180008487  jz      short loc_18000849D
0x180008489  call    cs:__imp_GetProcessHeap
0x18000848f  mov     r8, rbx; lpMem
0x180008492  xor     edx, edx; dwFlags
0x180008494  mov     rcx, rax; hHeap
0x180008497  call    cs:__imp_HeapFree
0x18000849d  test    edi, edi
0x18000849f  mov     eax, r15d
0x1800084a2  setns   al
0x1800084a5  jmp     short loc_1800084A9
0x1800084a7  xor     eax, eax
0x1800084a9  mov     rcx, [rbp+210h+var_30]
0x1800084b0  xor     rcx, rsp; StackCookie
0x1800084b3  call    __security_check_cookie
0x1800084b8  mov     rbx, [rsp+310h+arg_10]
0x1800084c0  add     rsp, 2F0h
0x1800084c7  pop     r15
0x1800084c9  pop     r14
0x1800084cb  pop     rdi
0x1800084cc  pop     rsi
0x1800084cd  pop     rbp
0x1800084ce  retn
```
