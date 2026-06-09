# DiagCabGetTempFileName(char *,int,void *)

- ea: `0x18013a210`
- end: `0x18013a377`
- name: `?DiagCabGetTempFileName@@YAHPEADHPEAX@Z`
- size: `359`
- prototype: `_BOOL8 __fastcall(char *pszTempName, int cbTempName, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18013a210`

## import_xrefs

- `msvcrt!rand` at `0x18013a299`
- `msvcrt!rand` at `0x18013a299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a2c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a2bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a2c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a322`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a235`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a25b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a235`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18013a25b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a24d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a350`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a24d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a337`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18013a350`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a35e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a345`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18013a35e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18013a2af`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18013a2af`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a30a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18013a30a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18013a27d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18013a27d`

## pseudocode

```c
_BOOL8 __fastcall DiagCabGetTempFileName(char *pszTempName, int cbTempName, void *pv)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rbp
  signed int v7; // ebx
  HANDLE v8; // rax
  WCHAR *v9; // rsi
  unsigned int TempPath2W; // eax
  UINT v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax

  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v6 )
  {
    v7 = -2147024882;
    return v7 >= 0;
  }
  v8 = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(v8, 0, 0x208u);
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_19;
  }
  TempPath2W = GetTempPath2W(260, v6);
  if ( !TempPath2W )
    goto LABEL_17;
  if ( TempPath2W >= 0x104 )
  {
    v7 = -2147024774;
    goto LABEL_19;
  }
  v11 = rand();
  if ( GetTempFileNameW(v6, L"PLA_", v11, v9) || !GetLastError() )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_19;
  }
  if ( !WideCharToMultiByte(0xFDE9u, 0, v9, -1, pszTempName, cbTempName, 0, 0) )
  {
    if ( !GetLastError() )
    {
      v7 = 0;
      goto LABEL_19;
    }
LABEL_17:
    v13 = GetLastError();
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_19:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v6);
  if ( v9 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v9);
  }
  return v7 >= 0;
}

```

## disassembly

```asm
0x18013a210  push    rbx
0x18013a212  push    rbp
0x18013a213  push    rsi
0x18013a214  push    r14
0x18013a216  push    r15
0x18013a218  sub     rsp, 40h
0x18013a21c  mov     r14d, edx
0x18013a21f  mov     r15, rcx
0x18013a222  call    cs:__imp_GetProcessHeap
0x18013a228  mov     ebx, 208h
0x18013a22d  xor     edx, edx; dwFlags
0x18013a22f  mov     rcx, rax; hHeap
0x18013a232  mov     r8d, ebx; dwBytes
0x18013a235  call    cs:__imp_HeapAlloc
0x18013a23b  mov     rbp, rax
0x18013a23e  test    rax, rax
0x18013a241  jnz     short loc_18013A24D
0x18013a243  mov     ebx, 8007000Eh
0x18013a248  jmp     loc_18013A364
0x18013a24d  call    cs:__imp_GetProcessHeap
0x18013a253  mov     r8, rbx; dwBytes
0x18013a256  xor     edx, edx; dwFlags
0x18013a258  mov     rcx, rax; hHeap
0x18013a25b  call    cs:__imp_HeapAlloc
0x18013a261  mov     rsi, rax
0x18013a264  test    rax, rax
0x18013a267  jnz     short loc_18013A273
0x18013a269  mov     ebx, 8007000Eh
0x18013a26e  jmp     loc_18013A337
0x18013a273  mov     ebx, 104h
0x18013a278  mov     rdx, rbp
0x18013a27b  mov     ecx, ebx
0x18013a27d  call    cs:__imp_GetTempPath2W
0x18013a283  test    eax, eax
0x18013a285  jz      loc_18013A322
0x18013a28b  cmp     eax, ebx
0x18013a28d  jb      short loc_18013A299
0x18013a28f  mov     ebx, 8007007Ah
0x18013a294  jmp     loc_18013A337
0x18013a299  call    cs:__imp_rand
0x18013a29f  mov     r9, rsi; lpTempFileName
0x18013a2a2  lea     rdx, aPla; "PLA_"
0x18013a2a9  mov     r8d, eax; uUnique
0x18013a2ac  mov     rcx, rbp; lpPathName
0x18013a2af  call    cs:__imp_GetTempFileNameW
0x18013a2b5  test    eax, eax
0x18013a2b7  jz      short loc_18013A2BD
0x18013a2b9  xor     ebx, ebx
0x18013a2bb  jmp     short loc_18013A2E0
0x18013a2bd  call    cs:__imp_GetLastError
0x18013a2c3  test    eax, eax
0x18013a2c5  jz      short loc_18013A2B9
0x18013a2c7  call    cs:__imp_GetLastError
0x18013a2cd  mov     ebx, eax
0x18013a2cf  test    eax, eax
0x18013a2d1  jle     short loc_18013A2DC
0x18013a2d3  movzx   ebx, ax
0x18013a2d6  or      ebx, 80070000h
0x18013a2dc  test    ebx, ebx
0x18013a2de  js      short loc_18013A337
0x18013a2e0  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18013a2e9  or      r9d, 0FFFFFFFFh; cchWideChar
0x18013a2ed  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18013a2f6  mov     r8, rsi; lpWideCharStr
0x18013a2f9  mov     [rsp+68h+cbMultiByte], r14d; cbMultiByte
0x18013a2fe  xor     edx, edx; dwFlags
0x18013a300  mov     ecx, 0FDE9h; CodePage
0x18013a305  mov     [rsp+68h+lpMultiByteStr], r15; lpMultiByteStr
0x18013a30a  call    cs:__imp_WideCharToMultiByte
0x18013a310  test    eax, eax
0x18013a312  jnz     short loc_18013A337
0x18013a314  call    cs:__imp_GetLastError
0x18013a31a  test    eax, eax
0x18013a31c  jnz     short loc_18013A322
0x18013a31e  xor     ebx, ebx
0x18013a320  jmp     short loc_18013A337
0x18013a322  call    cs:__imp_GetLastError
0x18013a328  mov     ebx, eax
0x18013a32a  test    eax, eax
0x18013a32c  jle     short loc_18013A337
0x18013a32e  movzx   ebx, ax
0x18013a331  or      ebx, 80070000h
0x18013a337  call    cs:__imp_GetProcessHeap
0x18013a33d  mov     r8, rbp; lpMem
0x18013a340  xor     edx, edx; dwFlags
0x18013a342  mov     rcx, rax; hHeap
0x18013a345  call    cs:__imp_HeapFree
0x18013a34b  test    rsi, rsi
0x18013a34e  jz      short loc_18013A364
0x18013a350  call    cs:__imp_GetProcessHeap
0x18013a356  mov     r8, rsi; lpMem
0x18013a359  xor     edx, edx; dwFlags
0x18013a35b  mov     rcx, rax; hHeap
0x18013a35e  call    cs:__imp_HeapFree
0x18013a364  not     ebx
0x18013a366  shr     ebx, 1Fh
0x18013a369  mov     eax, ebx
0x18013a36b  add     rsp, 40h
0x18013a36f  pop     r15
0x18013a371  pop     r14
0x18013a373  pop     rsi
0x18013a374  pop     rbp
0x18013a375  pop     rbx
0x18013a376  retn
```
