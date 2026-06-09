# UtGetHEMFFromEMFStm(IStream *,ulong *,HENHMETAFILE__ * *)

- ea: `0x1800a1354`
- end: `0x1800a14a0`
- name: `?UtGetHEMFFromEMFStm@@YAJPEAUIStream@@PEAKPEAPEAUHENHMETAFILE__@@@Z`
- size: `332`
- prototype: `HRESULT __fastcall(IStream *lpstream, unsigned int *pdwSize, HENHMETAFILE__ **lphPres)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a0a70`

## callees

- `0x18000a574`
- `0x180043eec`
- `0x1800a1354`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a138e`
- `KERNELBASE!GlobalAlloc` at `0x1800a138e`
- `KERNELBASE!GlobalFree` at `0x1800a13d8`
- `KERNELBASE!GlobalFree` at `0x1800a1417`
- `KERNELBASE!GlobalFree` at `0x1800a13d8`
- `KERNELBASE!GlobalFree` at `0x1800a1417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a142e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a145f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a142e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a145f`
- `GDI32!DeleteDC` at `0x1800a1408`
- `GDI32!DeleteDC` at `0x1800a1408`
- `GDI32!CreateCompatibleDC` at `0x1800a13bc`
- `GDI32!CreateCompatibleDC` at `0x1800a13bc`
- `GDI32!GetEnhMetaFileBits` at `0x1800a144d`
- `GDI32!GetEnhMetaFileBits` at `0x1800a144d`
- `GDI32!SetWinMetaFileBits` at `0x1800a13f6`
- `GDI32!SetWinMetaFileBits` at `0x1800a13f6`

## pseudocode

```c
__int64 __fastcall UtGetHEMFFromEMFStm(IStream *lpstream, unsigned int *pdwSize, HENHMETAFILE__ **lphPres)
{
  unsigned __int64 v4; // rbx
  BYTE *v7; // rax
  BYTE *v8; // rdi
  unsigned int v9; // ebx
  HDC CompatibleDC; // rax
  HDC v11; // rbp
  signed int LastError; // eax
  UINT EnhMetaFileBits; // eax
  signed int v15; // eax

  *lphPres = 0;
  v4 = *pdwSize;
  if ( v4 < GetSafeAllocSize() )
  {
    v7 = (BYTE *)GlobalAlloc(0, (unsigned int)v4);
    v8 = v7;
    if ( v7 )
    {
      v9 = StRead(lpstream, v7, *pdwSize);
      if ( (v9 & 0x80000000) == 0 )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v11 = CompatibleDC;
        if ( CompatibleDC )
        {
          *lphPres = SetWinMetaFileBits(*pdwSize, v8, CompatibleDC, 0);
          DeleteDC(v11);
          GlobalFree(v8);
          if ( !*lphPres )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
          EnhMetaFileBits = GetEnhMetaFileBits(*lphPres, 0, 0);
          *pdwSize = EnhMetaFileBits;
          if ( !EnhMetaFileBits )
          {
            v15 = GetLastError();
            v9 = v15;
            if ( v15 > 0 )
              return (unsigned __int16)v15 | 0x80070000;
          }
          return v9;
        }
        v9 = -2147467259;
      }
      GlobalFree(v8);
      return v9;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800a1354  mov     rax, rsp
0x1800a1357  mov     [rax+8], rbx
0x1800a135b  mov     [rax+10h], rbp
0x1800a135f  mov     [rax+18h], rsi
0x1800a1363  mov     [rax+20h], rdi
0x1800a1367  push    r14
0x1800a1369  sub     rsp, 20h
0x1800a136d  and     qword ptr [lphPres], 0
0x1800a1371  mov     r14, lphPres
0x1800a1374  mov     ebx, [pdwSize]
0x1800a1376  mov     rsi, pdwSize
0x1800a1379  mov     rbp, lpstream
0x1800a137c  call    GetSafeAllocSize
0x1800a1381  cmp     rbx, rax
0x1800a1384  jnb     loc_1800A147F
0x1800a138a  mov     edx, ebx; dwBytes
0x1800a138c  xor     ecx, ecx; uFlags
0x1800a138e  call    cs:__imp_GlobalAlloc
0x1800a1395  nop     dword ptr [rax+rax+00h]
0x1800a139a  mov     rdi, rax
0x1800a139d  test    rax, rax
0x1800a13a0  jz      loc_1800A147F
0x1800a13a6  mov     r8d, [rsi]; requestedByteCount
0x1800a13a9  mov     pdwSize, rax; buffer
0x1800a13ac  mov     lpstream, rbp; stream
0x1800a13af  call    ?StRead@@YAJPEAUIStream@@PEAXK@Z; StRead(IStream *,void *,ulong)
0x1800a13b4  mov     ebx, eax
0x1800a13b6  test    eax, eax
0x1800a13b8  js      short loc_1800A13D5
0x1800a13ba  xor     ecx, ecx; hdc
0x1800a13bc  call    cs:__imp_CreateCompatibleDC
0x1800a13c3  nop     dword ptr [rax+rax+00h]
0x1800a13c8  mov     rbp, rax
0x1800a13cb  test    rax, rax
0x1800a13ce  jnz     short loc_1800A13EB
0x1800a13d0  mov     ebx, 80004005h
0x1800a13d5  mov     lpstream, rdi; hMem
0x1800a13d8  call    cs:__imp_GlobalFree
0x1800a13df  nop     dword ptr [rax+rax+00h]
0x1800a13e4  mov     eax, ebx
0x1800a13e6  jmp     loc_1800A1484
0x1800a13eb  mov     ecx, [rsi]; nSize
0x1800a13ed  xor     r9d, r9d; lpMFP
0x1800a13f0  mov     lphPres, rbp; hdcRef
0x1800a13f3  mov     pdwSize, rdi; lpMeta16Data
0x1800a13f6  call    cs:__imp_SetWinMetaFileBits
0x1800a13fd  nop     dword ptr [rax+rax+00h]
0x1800a1402  mov     lpstream, rbp; hdc
0x1800a1405  mov     [r14], rax
0x1800a1408  call    cs:__imp_DeleteDC
0x1800a140f  nop     dword ptr [rax+rax+00h]
0x1800a1414  mov     lpstream, rdi; hMem
0x1800a1417  call    cs:__imp_GlobalFree
0x1800a141e  nop     dword ptr [rax+rax+00h]
0x1800a1423  cmp     qword ptr [r14], 0
0x1800a1427  mov     edi, 80070000h
0x1800a142c  jnz     short loc_1800A1445
0x1800a142e  call    cs:__imp_GetLastError
0x1800a1435  nop     dword ptr [rax+rax+00h]
0x1800a143a  mov     ebx, eax
0x1800a143c  test    eax, eax
0x1800a143e  jle     short loc_1800A1445
0x1800a1440  movzx   ebx, ax
0x1800a1443  or      ebx, edi
0x1800a1445  mov     lpstream, [r14]; hEMF
0x1800a1448  xor     r8d, r8d; lpData
0x1800a144b  xor     edx, edx; nSize
0x1800a144d  call    cs:__imp_GetEnhMetaFileBits
0x1800a1454  nop     dword ptr [rax+rax+00h]
0x1800a1459  mov     [rsi], eax
0x1800a145b  test    eax, eax
0x1800a145d  jnz     short loc_1800A13E4
0x1800a145f  call    cs:__imp_GetLastError
0x1800a1466  nop     dword ptr [rax+rax+00h]
0x1800a146b  mov     ebx, eax
0x1800a146d  test    eax, eax
0x1800a146f  jle     loc_1800A13E4
0x1800a1475  movzx   ebx, ax
0x1800a1478  or      ebx, edi
0x1800a147a  jmp     loc_1800A13E4
0x1800a147f  mov     eax, 8007000Eh
0x1800a1484  mov     rbx, [rsp+28h+arg_0]
0x1800a1489  mov     rbp, [rsp+28h+arg_8]
0x1800a148e  mov     rsi, [rsp+28h+arg_10]
0x1800a1493  mov     rdi, [rsp+28h+arg_18]
0x1800a1498  add     rsp, 20h
0x1800a149c  pop     r14
0x1800a149e  retn
```
