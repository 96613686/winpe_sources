# CClipDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x140059390`
- end: `0x140059487`
- name: `?GetData@CClipDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CClipDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140059390`
- `0x14006a0e2`

## import_xrefs

- `USER32!IsClipboardFormatAvailable` at `0x1400593c9`
- `USER32!IsClipboardFormatAvailable` at `0x1400593c9`
- `USER32!CloseClipboard` at `0x140059472`
- `USER32!CloseClipboard` at `0x140059472`
- `USER32!GetClipboardData` at `0x1400593e0`
- `USER32!GetClipboardData` at `0x1400593e0`
- `USER32!OpenClipboard` at `0x1400593b2`
- `USER32!OpenClipboard` at `0x1400593b2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x14005941e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x14005941e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1400593f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140059438`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1400593f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140059438`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140059410`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140059410`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14005945f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14005946c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14005945f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x14005946c`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetData(CClipDataObject *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  unsigned int v5; // ebx
  HANDLE ClipboardData; // rax
  void *v7; // rdi
  const void *v8; // rbx
  SIZE_T v9; // r15
  HBITMAP v10; // rax
  HBITMAP v11; // rbp
  void *v12; // rsi

  *(_OWORD *)&a3->tymed = 0;
  a3->pUnkForRelease = 0;
  if ( OpenClipboard(0) )
  {
    if ( IsClipboardFormatAvailable(a2->cfFormat) )
    {
      ClipboardData = GetClipboardData(a2->cfFormat);
      v7 = ClipboardData;
      if ( ClipboardData )
      {
        v8 = GlobalLock(ClipboardData);
        if ( v8 )
        {
          v9 = GlobalSize(v7);
          v10 = (HBITMAP)GlobalAlloc(0, v9);
          v11 = v10;
          if ( v10 )
          {
            v12 = GlobalLock(v10);
            memcpy_0(v12, v8, v9);
            v5 = 0;
            a3->tymed = 1;
            a3->hBitmap = v11;
          }
          else
          {
            v12 = 0;
            v5 = -2147024882;
          }
          GlobalUnlock(v7);
          if ( v12 )
            GlobalUnlock(0);
        }
        else
        {
          v5 = -2147024882;
        }
      }
      else
      {
        v5 = -2147221037;
      }
    }
    else
    {
      v5 = -2147221404;
    }
    CloseClipboard();
  }
  else
  {
    return (unsigned int)-2147221040;
  }
  return v5;
}

```

## disassembly

```asm
0x140059390  push    rbx
0x140059392  push    rbp
0x140059393  push    rsi
0x140059394  push    rdi
0x140059395  push    r14
0x140059397  push    r15
0x140059399  sub     rsp, 28h
0x14005939d  xorps   xmm0, xmm0
0x1400593a0  xor     eax, eax
0x1400593a2  movups  xmmword ptr [r8], xmm0
0x1400593a6  xor     ecx, ecx; hWndNewOwner
0x1400593a8  mov     [r8+10h], rax
0x1400593ac  mov     r14, r8
0x1400593af  mov     rbx, rdx
0x1400593b2  call    cs:__imp_OpenClipboard
0x1400593b8  test    eax, eax
0x1400593ba  jnz     short loc_1400593C6
0x1400593bc  mov     ebx, 800401D0h
0x1400593c1  jmp     loc_140059478
0x1400593c6  movzx   ecx, word ptr [rbx]; format
0x1400593c9  call    cs:__imp_IsClipboardFormatAvailable
0x1400593cf  test    eax, eax
0x1400593d1  jnz     short loc_1400593DD
0x1400593d3  mov     ebx, 80040064h
0x1400593d8  jmp     loc_140059472
0x1400593dd  movzx   ecx, word ptr [rbx]; uFormat
0x1400593e0  call    cs:__imp_GetClipboardData
0x1400593e6  mov     rdi, rax
0x1400593e9  test    rax, rax
0x1400593ec  jnz     short loc_1400593F5
0x1400593ee  mov     ebx, 800401D3h
0x1400593f3  jmp     short loc_140059472
0x1400593f5  mov     rcx, rdi; hMem
0x1400593f8  call    cs:__imp_GlobalLock
0x1400593fe  mov     rbx, rax
0x140059401  test    rax, rax
0x140059404  jnz     short loc_14005940D
0x140059406  mov     ebx, 8007000Eh
0x14005940b  jmp     short loc_140059472
0x14005940d  mov     rcx, rdi; hMem
0x140059410  call    cs:__imp_GlobalSize
0x140059416  mov     rdx, rax; dwBytes
0x140059419  xor     ecx, ecx; uFlags
0x14005941b  mov     r15, rax
0x14005941e  call    cs:__imp_GlobalAlloc
0x140059424  mov     rbp, rax
0x140059427  test    rax, rax
0x14005942a  jnz     short loc_140059435
0x14005942c  xor     esi, esi
0x14005942e  mov     ebx, 8007000Eh
0x140059433  jmp     short loc_14005945C
0x140059435  mov     rcx, rbp; hMem
0x140059438  call    cs:__imp_GlobalLock
0x14005943e  mov     r8, r15; Size
0x140059441  mov     rdx, rbx; Src
0x140059444  mov     rcx, rax; void *
0x140059447  mov     rsi, rax
0x14005944a  call    memcpy_0
0x14005944f  xor     ebx, ebx
0x140059451  mov     dword ptr [r14], 1
0x140059458  mov     [r14+8], rbp
0x14005945c  mov     rcx, rdi; hMem
0x14005945f  call    cs:__imp_GlobalUnlock
0x140059465  test    rsi, rsi
0x140059468  jz      short loc_140059472
0x14005946a  xor     ecx, ecx; hMem
0x14005946c  call    cs:__imp_GlobalUnlock
0x140059472  call    cs:__imp_CloseClipboard
0x140059478  mov     eax, ebx
0x14005947a  add     rsp, 28h
0x14005947e  pop     r15
0x140059480  pop     r14
0x140059482  pop     rdi
0x140059483  pop     rsi
0x140059484  pop     rbp
0x140059485  pop     rbx
0x140059486  retn
```
