# myLoadSystem32LibraryEx(ushort const *,void *,ulong)

- ea: `0x18000d9f0`
- end: `0x18000dc60`
- name: `?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z`
- size: `624`
- prototype: `HINSTANCE __fastcall(WCHAR *, void *, DWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007a00`
- `0x180010168`
- `0x1800103fc`
- `0x180012830`
- `0x18001d988`

## callees

- `0x180008610`
- `0x18000a3b0`
- `0x18000d9f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000db9a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000db9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da3f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000da3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000da0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000da57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000da0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000da57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbe3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dbe3`

## pseudocode

```c
HINSTANCE __fastcall myLoadSystem32LibraryEx(WCHAR *a1, void *a2, DWORD a3)
{
  HMODULE Library; // rbp
  UINT SystemDirectoryW; // eax
  UINT v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // rdx
  unsigned __int64 v10; // rsi
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  UINT v13; // eax
  bool v14; // zf
  __int64 v15; // r8
  unsigned __int64 v16; // rcx
  WCHAR *v17; // rax
  unsigned __int64 v18; // r10
  const unsigned __int16 *v19; // r9
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  WCHAR *v22; // r10
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rcx
  WCHAR *v25; // rax
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rsi
  WCHAR *v28; // rdx
  WCHAR *v29; // rcx
  DWORD v30; // ebx
  DWORD LastError; // eax
  DWORD v33; // eax
  int v34; // r9d
  int v35; // r8d
  unsigned int v36; // edx
  const unsigned __int16 *v37; // rcx
  DWORD v38; // eax

  Library = 0;
  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  v7 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    v30 = myHError(LastError);
    CSPrintErrorLineFileData2(0, 0x4E501CAu, v30, 0);
    goto LABEL_41;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = v9 + SystemDirectoryW + 1 + 1LL;
  v11 = (WCHAR *)LocalAlloc(0, 2 * v10);
  v12 = v11;
  if ( !v11 )
  {
    v30 = -2147024882;
    CSPrintErrorLineFileData2(0, 0x4EE01CAu, -2147024882, 0);
    goto LABEL_41;
  }
  v13 = GetSystemDirectoryW(v11, v7);
  if ( v13 > v7 || !v13 )
  {
    v38 = GetLastError();
    v30 = myHError(v38);
    v36 = 83362250;
    if ( !v30 )
      v30 = -2147024785;
    v34 = 0;
    v37 = 0;
    v35 = v30;
    goto LABEL_47;
  }
  do
    v14 = v12[++v8] == 0;
  while ( !v14 );
  if ( v10 )
  {
    v15 = 2147483646;
    if ( v12[v8 - 1] == 92 )
    {
      if ( v10 <= 0x7FFFFFFF )
      {
LABEL_25:
        v24 = v10;
        v25 = v12;
        do
        {
          if ( !*v25 )
            break;
          ++v25;
          --v24;
        }
        while ( v24 );
        v26 = v10 - v24;
        if ( v24 )
        {
          v27 = v24;
          v28 = &v12[v26];
          do
          {
            if ( !v15 )
              break;
            if ( !*a1 )
              break;
            *v28++ = *a1++;
            --v15;
            --v27;
          }
          while ( v27 );
          v29 = v28 - 1;
          if ( v27 )
            v29 = v28;
          *v29 = 0;
        }
      }
    }
    else if ( v10 <= 0x7FFFFFFF )
    {
      v16 = v10;
      v17 = v12;
      while ( *v17 )
      {
        ++v17;
        if ( !--v16 )
        {
          v18 = 0;
          goto LABEL_16;
        }
      }
      v18 = v10 - v16;
LABEL_16:
      if ( v16 )
      {
        v19 = L"\\";
        v20 = v10 - v18;
        v14 = v10 == v18;
        v21 = 2147483646;
        v22 = &v12[v18];
        if ( !v14 )
        {
          do
          {
            if ( !v21 )
              break;
            if ( !*v19 )
              break;
            *v22++ = *v19++;
            --v21;
            --v20;
          }
          while ( v20 );
        }
        v23 = v22 - 1;
        if ( v20 )
          v23 = v22;
        *v23 = 0;
      }
      goto LABEL_25;
    }
  }
  Library = LoadLibraryExW(v12, 0, a3);
  if ( Library )
  {
    v30 = 0;
    goto LABEL_38;
  }
  v33 = GetLastError();
  v30 = myHError(v33);
  v34 = -2147024894;
  v35 = v30;
  v36 = 84541898;
  v37 = v12;
LABEL_47:
  CSPrintErrorLineFileData2(v37, v36, v35, v34);
LABEL_38:
  LocalFree(v12);
  if ( !Library )
LABEL_41:
    SetLastError(v30);
  return Library;
}

```

## disassembly

```asm
0x18000d9f0  push    rbx
0x18000d9f2  push    rbp
0x18000d9f3  push    rsi
0x18000d9f4  push    rdi
0x18000d9f5  push    r12
0x18000d9f7  push    r14
0x18000d9f9  push    r15
0x18000d9fb  sub     rsp, 20h
0x18000d9ff  mov     r14, rcx
0x18000da02  xor     edx, edx; uSize
0x18000da04  xor     ecx, ecx; lpBuffer
0x18000da06  mov     r12d, r8d
0x18000da09  xor     ebp, ebp
0x18000da0b  call    cs:__imp_GetSystemDirectoryW
0x18000da11  mov     r15d, eax
0x18000da14  test    eax, eax
0x18000da16  jz      loc_18000DBEB
0x18000da1c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000da23  mov     rdx, rbx
0x18000da26  inc     rdx
0x18000da29  cmp     [r14+rdx*2], bp
0x18000da2e  jnz     short loc_18000DA26
0x18000da30  lea     esi, [rax+1]
0x18000da33  xor     ecx, ecx; uFlags
0x18000da35  inc     rsi
0x18000da38  add     rsi, rdx
0x18000da3b  lea     rdx, [rsi+rsi]; uBytes
0x18000da3f  call    cs:__imp_LocalAlloc
0x18000da45  mov     rdi, rax
0x18000da48  test    rax, rax
0x18000da4b  jz      loc_18000DBCA
0x18000da51  mov     edx, r15d; uSize
0x18000da54  mov     rcx, rax; lpBuffer
0x18000da57  call    cs:__imp_GetSystemDirectoryW
0x18000da5d  cmp     eax, r15d
0x18000da60  ja      loc_18000DC30
0x18000da66  test    eax, eax
0x18000da68  jz      loc_18000DC30
0x18000da6e  xchg    ax, ax
0x18000da70  cmp     [rdi+rbx*2+2], bp
0x18000da75  lea     rbx, [rbx+1]
0x18000da79  jnz     short loc_18000DA70
0x18000da7b  test    rsi, rsi
0x18000da7e  jz      loc_18000DB92
0x18000da84  mov     eax, 5Ch ; '\'
0x18000da89  mov     r8d, 7FFFFFFEh
0x18000da8f  cmp     ax, [rdi+rbx*2-2]
0x18000da94  jz      loc_18000DB1A
0x18000da9a  cmp     rsi, 7FFFFFFFh
0x18000daa1  ja      loc_18000DB92
0x18000daa7  mov     rcx, rsi
0x18000daaa  mov     rax, rdi
0x18000daad  nop     dword ptr [rax]
0x18000dab0  cmp     [rax], bp
0x18000dab3  jz      short loc_18000DAC4
0x18000dab5  add     rax, 2
0x18000dab9  sub     rcx, 1
0x18000dabd  jnz     short loc_18000DAB0
0x18000dabf  xor     r10d, r10d
0x18000dac2  jmp     short loc_18000DACA
0x18000dac4  mov     r10, rsi
0x18000dac7  sub     r10, rcx
0x18000daca  test    rcx, rcx
0x18000dacd  jz      short loc_18000DB23
0x18000dacf  mov     rdx, rsi
0x18000dad2  lea     r9, asc_180061BD4; "\\"
0x18000dad9  sub     rdx, r10
0x18000dadc  mov     rax, r8
0x18000dadf  lea     r10, [rdi+r10*2]
0x18000dae3  jz      short loc_18000DB08
0x18000dae5  test    rax, rax
0x18000dae8  jz      short loc_18000DB08
0x18000daea  movzx   ecx, word ptr [r9]
0x18000daee  test    cx, cx
0x18000daf1  jz      short loc_18000DB08
0x18000daf3  mov     [r10], cx
0x18000daf7  add     r9, 2
0x18000dafb  add     r10, 2
0x18000daff  dec     rax
0x18000db02  sub     rdx, 1
0x18000db06  jnz     short loc_18000DAE5
0x18000db08  test    rdx, rdx
0x18000db0b  lea     rcx, [r10-2]
0x18000db0f  cmovnz  rcx, r10
0x18000db13  xor     eax, eax
0x18000db15  mov     [rcx], ax
0x18000db18  jmp     short loc_18000DB23
0x18000db1a  cmp     rsi, 7FFFFFFFh
0x18000db21  ja      short loc_18000DB92
0x18000db23  mov     rcx, rsi
0x18000db26  mov     rax, rdi
0x18000db29  nop     dword ptr [rax+00000000h]
0x18000db30  cmp     [rax], bp
0x18000db33  jz      short loc_18000DB3F
0x18000db35  add     rax, 2
0x18000db39  sub     rcx, 1
0x18000db3d  jnz     short loc_18000DB30
0x18000db3f  xor     edx, edx
0x18000db41  mov     rax, rsi
0x18000db44  sub     rax, rcx
0x18000db47  test    rcx, rcx
0x18000db4a  cmovnz  rdx, rax
0x18000db4e  jz      short loc_18000DB92
0x18000db50  sub     rsi, rdx
0x18000db53  lea     rdx, [rdi+rdx*2]
0x18000db57  jz      short loc_18000DB82
0x18000db59  nop     dword ptr [rax+00000000h]
0x18000db60  test    r8, r8
0x18000db63  jz      short loc_18000DB82
0x18000db65  movzx   eax, word ptr [r14]
0x18000db69  test    ax, ax
0x18000db6c  jz      short loc_18000DB82
0x18000db6e  mov     [rdx], ax
0x18000db71  add     r14, 2
0x18000db75  add     rdx, 2
0x18000db79  dec     r8
0x18000db7c  sub     rsi, 1
0x18000db80  jnz     short loc_18000DB60
0x18000db82  test    rsi, rsi
0x18000db85  lea     rcx, [rdx-2]
0x18000db89  cmovnz  rcx, rdx
0x18000db8d  xor     eax, eax
0x18000db8f  mov     [rcx], ax
0x18000db92  mov     r8d, r12d; dwFlags
0x18000db95  xor     edx, edx; hFile
0x18000db97  mov     rcx, rdi; lpLibFileName
0x18000db9a  call    cs:__imp_LoadLibraryExW
0x18000dba0  mov     rbp, rax
0x18000dba3  test    rax, rax
0x18000dba6  jz      short loc_18000DC0E
0x18000dba8  xor     ebx, ebx
0x18000dbaa  mov     rcx, rdi; hMem
0x18000dbad  call    cs:__imp_LocalFree
0x18000dbb3  test    rbp, rbp
0x18000dbb6  jz      short loc_18000DBE1
0x18000dbb8  mov     rax, rbp
0x18000dbbb  add     rsp, 20h
0x18000dbbf  pop     r15
0x18000dbc1  pop     r14
0x18000dbc3  pop     r12
0x18000dbc5  pop     rdi
0x18000dbc6  pop     rsi
0x18000dbc7  pop     rbp
0x18000dbc8  pop     rbx
0x18000dbc9  retn
0x18000dbca  mov     ebx, 8007000Eh
0x18000dbcf  xor     r9d, r9d; int
0x18000dbd2  mov     r8d, ebx; int
0x18000dbd5  mov     edx, 4EE01CAh; unsigned int
0x18000dbda  xor     ecx, ecx; unsigned __int16 *
0x18000dbdc  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000dbe1  mov     ecx, ebx; dwErrCode
0x18000dbe3  call    cs:__imp_SetLastError
0x18000dbe9  jmp     short loc_18000DBB8
0x18000dbeb  call    cs:__imp_GetLastError
0x18000dbf1  mov     ecx, eax; int
0x18000dbf3  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000dbf8  xor     r9d, r9d; int
0x18000dbfb  mov     r8d, eax; int
0x18000dbfe  mov     edx, 4E501CAh; unsigned int
0x18000dc03  xor     ecx, ecx; unsigned __int16 *
0x18000dc05  mov     ebx, eax
0x18000dc07  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000dc0c  jmp     short loc_18000DBE1
0x18000dc0e  call    cs:__imp_GetLastError
0x18000dc14  mov     ecx, eax; int
0x18000dc16  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000dc1b  mov     ebx, eax
0x18000dc1d  mov     r9d, 80070002h
0x18000dc23  mov     r8d, eax
0x18000dc26  mov     edx, 50A01CAh
0x18000dc2b  mov     rcx, rdi
0x18000dc2e  jmp     short loc_18000DC56
0x18000dc30  call    cs:__imp_GetLastError
0x18000dc36  mov     ecx, eax; int
0x18000dc38  call    ?myHError@@YAJJ@Z; myHError(long)
0x18000dc3d  mov     ebx, eax
0x18000dc3f  mov     edx, 4F801CAh; unsigned int
0x18000dc44  test    ebx, ebx
0x18000dc46  mov     eax, 8007006Fh
0x18000dc4b  cmovz   ebx, eax
0x18000dc4e  xor     r9d, r9d; int
0x18000dc51  xor     ecx, ecx; unsigned __int16 *
0x18000dc53  mov     r8d, ebx; int
0x18000dc56  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000dc5b  jmp     loc_18000DBAA
```
