# UtHEMFToEMFStm(HENHMETAFILE__ *,ulong,IStream *,tagEMFWRITETYPE)

- ea: `0x1800a14a8`
- end: `0x1800a1629`
- name: `?UtHEMFToEMFStm@@YAJPEAUHENHMETAFILE__@@KPEAUIStream@@W4tagEMFWRITETYPE@@@Z`
- size: `385`
- prototype: `HRESULT __fastcall(HENHMETAFILE__ *hEMF, unsigned int dwSize, IStream *lpstream, tagEMFWRITETYPE emfwType)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800a0830`
- `0x1800a0c10`

## callees

- `0x18000a574`
- `0x1800a14a8`
- `0x1800ab940`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a15b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a15b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a14f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a14f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a15ed`
- `GDI32!DeleteDC` at `0x1800a1574`
- `GDI32!DeleteDC` at `0x1800a1585`
- `GDI32!DeleteDC` at `0x1800a1574`
- `GDI32!DeleteDC` at `0x1800a1585`
- `GDI32!CreateCompatibleDC` at `0x1800a1518`
- `GDI32!CreateCompatibleDC` at `0x1800a1518`
- `GDI32!GetEnhMetaFileBits` at `0x1800a15dd`
- `GDI32!GetEnhMetaFileBits` at `0x1800a15dd`
- `GDI32!GetWinMetaFileBits` at `0x1800a1546`
- `GDI32!GetWinMetaFileBits` at `0x1800a1546`

## pseudocode

```c
__int64 __fastcall UtHEMFToEMFStm(HENHMETAFILE hEMF, unsigned int dwSize, IStream *lpstream, tagEMFWRITETYPE emfwType)
{
  SIZE_T v4; // rbx
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rsi
  HDC hdcRef; // rax
  HDC v12; // rdi
  signed int v13; // ebx
  signed int v14; // eax
  unsigned int v15; // edx
  int v16; // r8d
  signed int LastError; // eax

  v4 = dwSize;
  if ( !hEMF )
    return 2147745799LL;
  if ( dwSize >= GetSafeAllocSize() )
    return 2147942414LL;
  v9 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, v4);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  if ( emfwType != WRITE_AS_WMF )
  {
    if ( !GetEnhMetaFileBits(hEMF, v4, v9) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      goto $errRtn_136;
    }
LABEL_13:
    v13 = ((__int64 (__fastcall *)(IStream *, unsigned __int8 *, _QWORD, _QWORD))lpstream->lpVtbl->Write)(
            lpstream,
            v10,
            (unsigned int)v4,
            0);
    goto $errRtn_136;
  }
  hdcRef = CreateCompatibleDC(0);
  v12 = hdcRef;
  if ( hdcRef )
  {
    if ( !GetWinMetaFileBits(hEMF, v4, v10, 8, hdcRef) )
    {
      v14 = GetLastError();
      v13 = v14;
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      DeleteDC(v12);
      goto $errRtn_136;
    }
    DeleteDC(v12);
    goto LABEL_13;
  }
  v13 = -2147467259;
$errRtn_136:
  HeapFree(g_hHeap, 0, v10);
  if ( v13 >= 0 )
    return (unsigned int)StSetSize(lpstream, v15, v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a14a8  mov     [rsp+arg_0], rbx
0x1800a14ad  mov     [rsp+arg_8], rbp
0x1800a14b2  mov     [rsp+arg_10], rsi
0x1800a14b7  push    rdi
0x1800a14b8  push    r14
0x1800a14ba  push    r15
0x1800a14bc  sub     rsp, 30h
0x1800a14c0  mov     ebx, dwSize
0x1800a14c2  mov     r14d, emfwType
0x1800a14c5  mov     r15, lpstream
0x1800a14c8  mov     rbp, hEMF
0x1800a14cb  test    hEMF, hEMF
0x1800a14ce  jnz     short loc_1800A14DA
0x1800a14d0  mov     eax, 80040007h
0x1800a14d5  jmp     loc_1800A160F
0x1800a14da  call    GetSafeAllocSize
0x1800a14df  cmp     rbx, rax
0x1800a14e2  jnb     loc_1800A160A
0x1800a14e8  mov     hEMF, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a14ef  mov     lpstream, rbx; dwBytes
0x1800a14f2  xor     dwSize, dwSize; dwFlags
0x1800a14f4  call    cs:__imp_HeapAlloc
0x1800a14fb  nop     dword ptr [rax+rax+00h]
0x1800a1500  mov     rsi, rax
0x1800a1503  test    rax, rax
0x1800a1506  jz      loc_1800A160A
0x1800a150c  cmp     r14d, 0Dh
0x1800a1510  jnz     loc_1800A15D5
0x1800a1516  xor     ecx, ecx; hdc
0x1800a1518  call    cs:__imp_CreateCompatibleDC
0x1800a151f  nop     dword ptr [rax+rax+00h]
0x1800a1524  mov     rdi, rax
0x1800a1527  test    rax, rax
0x1800a152a  jnz     short loc_1800A1533
0x1800a152c  mov     ebx, 80004005h
0x1800a1531  jmp     short $errRtn_136
0x1800a1533  mov     emfwType, 8; iMapMode
0x1800a1539  mov     [rsp+48h+hdcRef], rdi; hdcRef
0x1800a153e  mov     lpstream, rsi; pData16
0x1800a1541  mov     dwSize, ebx; cbData16
0x1800a1543  mov     hEMF, rbp; hemf
0x1800a1546  call    cs:__imp_GetWinMetaFileBits
0x1800a154d  nop     dword ptr [rax+rax+00h]
0x1800a1552  test    eax, eax
0x1800a1554  jnz     short loc_1800A1582
0x1800a1556  call    cs:__imp_GetLastError
0x1800a155d  nop     dword ptr [rax+rax+00h]
0x1800a1562  mov     ebx, eax
0x1800a1564  test    eax, eax
0x1800a1566  jle     short loc_1800A1571
0x1800a1568  movzx   ebx, ax
0x1800a156b  or      ebx, 80070000h
0x1800a1571  mov     hEMF, rdi; hdc
0x1800a1574  call    cs:__imp_DeleteDC
0x1800a157b  nop     dword ptr [rax+rax+00h]
0x1800a1580  jmp     short $errRtn_136
0x1800a1582  mov     hEMF, rdi; hdc
0x1800a1585  call    cs:__imp_DeleteDC
0x1800a158c  nop     dword ptr [rax+rax+00h]
0x1800a1591  mov     rax, [r15]
0x1800a1594  xor     emfwType, emfwType
0x1800a1597  mov     r8d, ebx
0x1800a159a  mov     rdx, rsi
0x1800a159d  mov     hEMF, r15
0x1800a15a0  mov     rax, [rax+20h]
0x1800a15a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a15a9  mov     ebx, eax
0x1800a15ab  mov     hEMF, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800a15b2  mov     lpstream, rsi; lpMem
0x1800a15b5  xor     dwSize, dwSize; dwFlags
0x1800a15b7  call    cs:__imp_HeapFree
0x1800a15be  nop     dword ptr [rax+rax+00h]
0x1800a15c3  test    ebx, ebx
0x1800a15c5  js      short loc_1800A15D1
0x1800a15c7  mov     hEMF, r15; pstm
0x1800a15ca  call    ?StSetSize@@YAJPEAUIStream@@KH@Z; StSetSize(IStream *,ulong,int)
0x1800a15cf  mov     ebx, eax
0x1800a15d1  mov     eax, ebx
0x1800a15d3  jmp     short loc_1800A160F
0x1800a15d5  mov     lpstream, rsi; lpData
0x1800a15d8  mov     dwSize, ebx; nSize
0x1800a15da  mov     hEMF, rbp; hEMF
0x1800a15dd  call    cs:__imp_GetEnhMetaFileBits
0x1800a15e4  nop     dword ptr [rax+rax+00h]
0x1800a15e9  test    eax, eax
0x1800a15eb  jnz     short loc_1800A1591
0x1800a15ed  call    cs:__imp_GetLastError
0x1800a15f4  nop     dword ptr [rax+rax+00h]
0x1800a15f9  mov     ebx, eax
0x1800a15fb  test    eax, eax
0x1800a15fd  jle     short $errRtn_136
0x1800a15ff  movzx   ebx, ax
0x1800a1602  or      ebx, 80070000h
0x1800a1608  jmp     short $errRtn_136
0x1800a160a  mov     eax, 8007000Eh
0x1800a160f  mov     rbx, [rsp+48h+arg_0]
0x1800a1614  mov     rbp, [rsp+48h+arg_8]
0x1800a1619  mov     rsi, [rsp+48h+arg_10]
0x1800a161e  add     rsp, 30h
0x1800a1622  pop     r15
0x1800a1624  pop     r14
0x1800a1626  pop     rdi
0x1800a1627  retn
```
