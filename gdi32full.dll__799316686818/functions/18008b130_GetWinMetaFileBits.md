# GetWinMetaFileBits

- ea: `0x18008b130`
- end: `0x18008b30b`
- name: `GetWinMetaFileBits`
- size: `475`
- prototype: `UINT __stdcall(HENHMETAFILE hemf, UINT cbData16, LPBYTE pData16, INT iMapMode, HDC hdcRef)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180070c44`

## callees

- `0x180023650`
- `0x180024fb8`
- `0x180047cbc`
- `0x18004ca5c`
- `0x18005e1ec`
- `0x18008b130`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008b293`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008b293`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008b2a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008b2a3`
- `GDI32!GdiSetLastError` at `0x18008b256`
- `GDI32!GdiSetLastError` at `0x18008b301`
- `GDI32!GdiSetLastError` at `0x18008b256`
- `GDI32!GdiSetLastError` at `0x18008b301`

## string_xrefs

- `0x18008b28a`: `mf3216.dll`

## pseudocode

```c
UINT __stdcall GetWinMetaFileBits(HENHMETAFILE hemf, UINT cbData16, LPBYTE pData16, INT iMapMode, HDC hdcRef)
{
  UINT v5; // ebp
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // r8
  unsigned int *v13; // rdi
  void *v14; // rdx
  MF *v15; // rcx
  unsigned int v16; // eax
  _DWORD *v17; // rbx
  unsigned int *v18; // rdx
  size_t v19; // r8
  int v20; // ebx
  __int64 (__fastcall *v21)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int); // r10
  HMODULE Library; // rax

  v5 = 0;
  if ( gbDisableMetaFiles )
    return v5;
  if ( (unsigned int)(iMapMode - 1) <= 7 && ((unsigned int)hemf & 0x7F0000) == 0x460000 )
  {
    v10 = pvClientObjGet(hemf, 4587520);
    v11 = v10;
    if ( !v10 )
      return v5;
    v12 = *(_QWORD *)(v10 + 48);
    if ( !v12 )
      return v5;
    v13 = (unsigned int *)EMFContainer::ObtainPtr((EMFContainer *)(v10 + 40), 0, *(_DWORD *)(v12 + 48));
    if ( !v13 )
      return v5;
    **(_QWORD **)(v11 + 688) = hemf;
    if ( (unsigned int)MF::bValidBoundedSize((MF *)v11, v13, v13[1]) )
    {
      v16 = v13[1];
      if ( v16 + 36 >= v16 )
      {
        if ( (unsigned int)MF::bValidBoundedSize(v15, v14, v16 + 36) )
        {
          v17 = (unsigned int *)((char *)v13 + v13[1]);
          if ( (unsigned int)bIsEMRPublicComment(v17) && v17[4] == -2147483647 )
          {
            if ( iMapMode == 8 && ((v17[5] - 256) & 0xFFFFFDFF) == 0 && !v17[7] && !GetDWordCheckSum(v13[12], v18) )
            {
              v19 = (unsigned int)v17[8];
              if ( (unsigned __int64)v13 + *(_QWORD *)(v11 + 56) - (_QWORD)v17 - 36 >= v19 )
              {
                if ( pData16 )
                {
                  if ( cbData16 < (unsigned int)v19 )
                  {
                    GdiSetLastError(122);
                    goto LABEL_27;
                  }
                  memcpy_0(pData16, v17 + 9, v19);
                }
                v5 = v17[8];
                goto LABEL_27;
              }
            }
            v20 = 0;
          }
          else
          {
            v20 = 1;
          }
          v21 = (__int64 (__fastcall *)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int))qword_1800FB6F0;
          if ( qword_1800FB6F0
            || (Library = LoadLibraryExW(L"mf3216.dll", 0, 0),
                qword_1800FB6F0 = (__int64)GetProcAddress(Library, "ConvertEmfToWmf"),
                (v21 = (__int64 (__fastcall *)(_QWORD, unsigned int *, _QWORD, LPBYTE, INT, HDC, int))qword_1800FB6F0) != 0) )
          {
            v5 = v21(*(_QWORD *)(v11 + 688), v13, cbData16, pData16, iMapMode, hdcRef, v20);
          }
        }
      }
    }
LABEL_27:
    --*(_DWORD *)(v11 + 40);
    return v5;
  }
  GdiSetLastError(87);
  return 0;
}

```

## disassembly

```asm
0x18008b130  push    rbx
0x18008b132  push    rbp
0x18008b133  push    rsi
0x18008b134  push    rdi
0x18008b135  push    r12
0x18008b137  push    r14
0x18008b139  push    r15
0x18008b13b  sub     rsp, 40h
0x18008b13f  xor     ebp, ebp
0x18008b141  mov     r14d, r9d
0x18008b144  cmp     cs:gbDisableMetaFiles, ebp
0x18008b14a  mov     r15, r8
0x18008b14d  mov     r12d, edx
0x18008b150  mov     rbx, rcx
0x18008b153  jnz     loc_18008B2EB
0x18008b159  lea     eax, [r9-1]
0x18008b15d  cmp     eax, 7
0x18008b160  ja      loc_18008B2FC
0x18008b166  mov     eax, ebx
0x18008b168  mov     edx, 460000h
0x18008b16d  and     eax, 7F0000h
0x18008b172  cmp     eax, edx
0x18008b174  jnz     loc_18008B2FC
0x18008b17a  call    pvClientObjGet
0x18008b17f  mov     rsi, rax
0x18008b182  test    rax, rax
0x18008b185  jz      loc_18008B2EB
0x18008b18b  lea     rcx, [rax+28h]; this
0x18008b18f  mov     r8, [rcx+8]
0x18008b193  test    r8, r8
0x18008b196  jz      loc_18008B2EB
0x18008b19c  mov     r8d, [r8+30h]; unsigned int
0x18008b1a0  xor     edx, edx; unsigned int
0x18008b1a2  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18008b1a7  mov     rdi, rax
0x18008b1aa  test    rax, rax
0x18008b1ad  jz      loc_18008B2EB
0x18008b1b3  mov     rax, [rsi+2B0h]
0x18008b1ba  mov     rdx, rdi; void *
0x18008b1bd  mov     rcx, rsi; this
0x18008b1c0  mov     [rax], rbx
0x18008b1c3  mov     r8d, [rdi+4]; unsigned int
0x18008b1c7  call    ?bValidBoundedSize@MF@@QEAAHPEAXK@Z; MF::bValidBoundedSize(void *,ulong)
0x18008b1cc  test    eax, eax
0x18008b1ce  jz      loc_18008B2E8
0x18008b1d4  mov     eax, [rdi+4]
0x18008b1d7  lea     r8d, [rax+24h]; unsigned int
0x18008b1db  cmp     r8d, eax
0x18008b1de  jb      loc_18008B2E8
0x18008b1e4  call    ?bValidBoundedSize@MF@@QEAAHPEAXK@Z; MF::bValidBoundedSize(void *,ulong)
0x18008b1e9  test    eax, eax
0x18008b1eb  jz      loc_18008B2E8
0x18008b1f1  mov     ebx, [rdi+4]
0x18008b1f4  add     rbx, rdi
0x18008b1f7  mov     rcx, rbx
0x18008b1fa  call    bIsEMRPublicComment
0x18008b1ff  test    eax, eax
0x18008b201  jz      short loc_18008B276
0x18008b203  cmp     dword ptr [rbx+10h], 80000001h
0x18008b20a  jnz     short loc_18008B276
0x18008b20c  cmp     r14d, 8
0x18008b210  jnz     short loc_18008B272
0x18008b212  mov     eax, [rbx+14h]
0x18008b215  sub     eax, 100h
0x18008b21a  test    eax, 0FFFFFDFFh
0x18008b21f  jnz     short loc_18008B272
0x18008b221  cmp     [rbx+1Ch], ebp
0x18008b224  jnz     short loc_18008B272
0x18008b226  mov     ecx, [rdi+30h]; unsigned int
0x18008b229  call    ?GetDWordCheckSum@@YAKIPEAK@Z; GetDWordCheckSum(uint,ulong *)
0x18008b22e  test    eax, eax
0x18008b230  jnz     short loc_18008B272
0x18008b232  mov     rax, [rsi+38h]
0x18008b236  mov     r8d, [rbx+20h]; Size
0x18008b23a  sub     rax, rbx
0x18008b23d  add     rax, 0FFFFFFFFFFFFFFDCh
0x18008b241  add     rax, rdi
0x18008b244  cmp     rax, r8
0x18008b247  jb      short loc_18008B272
0x18008b249  test    r15, r15
0x18008b24c  jz      short loc_18008B26D
0x18008b24e  cmp     r12d, r8d
0x18008b251  jnb     short loc_18008B261
0x18008b253  lea     ecx, [rbp+7Ah]
0x18008b256  call    cs:__imp_GdiSetLastError
0x18008b25c  jmp     loc_18008B2E8
0x18008b261  lea     rdx, [rbx+24h]; Src
0x18008b265  mov     rcx, r15; void *
0x18008b268  call    memcpy_0
0x18008b26d  mov     ebp, [rbx+20h]
0x18008b270  jmp     short loc_18008B2E8
0x18008b272  xor     ebx, ebx
0x18008b274  jmp     short loc_18008B27B
0x18008b276  mov     ebx, 1
0x18008b27b  mov     r10, cs:qword_1800FB6F0
0x18008b282  test    r10, r10
0x18008b285  jnz     short loc_18008B2B8
0x18008b287  xor     r8d, r8d; dwFlags
0x18008b28a  lea     rcx, aMf3216Dll; "mf3216.dll"
0x18008b291  xor     edx, edx; hFile
0x18008b293  call    cs:__imp_LoadLibraryExW
0x18008b299  mov     rcx, rax; hModule
0x18008b29c  lea     rdx, aConvertemftowm; "ConvertEmfToWmf"
0x18008b2a3  call    cs:__imp_GetProcAddress
0x18008b2a9  mov     cs:qword_1800FB6F0, rax
0x18008b2b0  mov     r10, rax
0x18008b2b3  test    rax, rax
0x18008b2b6  jz      short loc_18008B2E8
0x18008b2b8  mov     rax, [rsp+78h+hdcRef]
0x18008b2c0  mov     r9, r15
0x18008b2c3  mov     rcx, [rsi+2B0h]
0x18008b2ca  mov     r8d, r12d
0x18008b2cd  mov     [rsp+78h+var_48], ebx
0x18008b2d1  mov     rdx, rdi
0x18008b2d4  mov     [rsp+78h+var_50], rax
0x18008b2d9  mov     rax, r10
0x18008b2dc  mov     [rsp+78h+var_58], r14d
0x18008b2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b2e6  mov     ebp, eax
0x18008b2e8  dec     dword ptr [rsi+28h]
0x18008b2eb  mov     eax, ebp
0x18008b2ed  add     rsp, 40h
0x18008b2f1  pop     r15
0x18008b2f3  pop     r14
0x18008b2f5  pop     r12
0x18008b2f7  pop     rdi
0x18008b2f8  pop     rsi
0x18008b2f9  pop     rbp
0x18008b2fa  pop     rbx
0x18008b2fb  retn
0x18008b2fc  mov     ecx, 57h ; 'W'
0x18008b301  call    cs:__imp_GdiSetLastError
0x18008b307  xor     eax, eax
0x18008b309  jmp     short loc_18008B2ED
```
