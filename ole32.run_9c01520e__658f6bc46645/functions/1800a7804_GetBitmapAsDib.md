# GetBitmapAsDib

- ea: `0x1800a7804`
- end: `0x1800a79c5`
- name: `GetBitmapAsDib`
- size: `449`
- prototype: `HRESULT __fastcall(_OLESTREAM *pos, CData *pdata)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a7df8`

## callees

- `0x18000a574`
- `0x1800430a4`
- `0x1800a7804`
- `0x1800a84f4`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x1800a7893`
- `KERNELBASE!GlobalAlloc` at `0x1800a7893`
- `KERNELBASE!GlobalFree` at `0x1800a797b`
- `KERNELBASE!GlobalFree` at `0x1800a797b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800a7956`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x1800a7956`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a796c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800a796c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a78ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a7937`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a78ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800a7937`
- `GDI32!DeleteObject` at `0x1800a798f`
- `GDI32!DeleteObject` at `0x1800a798f`
- `GDI32!CreateBitmap` at `0x1800a7907`
- `GDI32!CreateBitmap` at `0x1800a7907`

## pseudocode

```c
HRESULT __fastcall GetBitmapAsDib(_OLESTREAM *pos, CData *pdata)
{
  HBITMAP v4; // rdi
  HRESULT result; // eax
  HRESULT v6; // ebx
  unsigned int v7; // r12d
  unsigned __int64 v8; // rsi
  HGLOBAL v9; // rax
  void *v10; // rbp
  const void *v11; // rax
  const void *lpBits; // rsi
  HBITMAP Bitmap; // rax
  void *v14; // rax
  void *v15; // rsi
  void *v16; // rax
  tagWIN16BITMAP bm; // [rsp+30h] [rbp-48h] BYREF
  unsigned int ul; // [rsp+90h] [rbp+18h] BYREF

  ul = 0;
  memset(&bm, 0, sizeof(bm));
  v4 = 0;
  result = OLE1StreamToUL(pos, &ul);
  v6 = result;
  if ( result >= 0 )
  {
    if ( ((__int64 (__fastcall *)(_OLESTREAM *, tagWIN16BITMAP *, __int64))pos->lpstbl->Get)(pos, &bm, 18) < 0x12
      || ul < 0x12 )
    {
      return -2147221056;
    }
    else
    {
      v7 = ul - 18;
      v8 = ul - 18;
      if ( v8 >= GetSafeAllocSize() )
        return -2147024882;
      v9 = GlobalAlloc(2u, (unsigned int)v8);
      v10 = v9;
      if ( !v9 )
        return -2147024882;
      v11 = GlobalLock(v9);
      lpBits = v11;
      if ( v11 )
      {
        if ( ((__int64 (__fastcall *)(_OLESTREAM *, const void *, _QWORD))pos->lpstbl->Get)(pos, v11, v7) >= v7 )
        {
          Bitmap = CreateBitmap(bm.bmWidth, bm.bmHeight, bm.bmPlanes, bm.bmBitsPixel, lpBits);
          v4 = Bitmap;
          if ( Bitmap && (v14 = UtConvertBitmapToDib(Bitmap, 0), (v15 = v14) != 0) )
          {
            v16 = GlobalLock(v14);
            pdata->m_pv = v16;
            if ( v16 )
            {
              pdata->m_cbSize = GlobalSize(v15);
              pdata->m_h = v15;
            }
            else
            {
              v6 = -2147024882;
            }
          }
          else
          {
            v6 = -2147221053;
          }
        }
        else
        {
          v6 = -2147221056;
        }
        GlobalUnlock(v10);
      }
      else
      {
        v6 = -2147024882;
      }
      GlobalFree(v10);
      if ( v4 )
        DeleteObject(v4);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800a7804  mov     r11, rsp
0x1800a7807  mov     [r11+8], rbx
0x1800a780b  mov     [r11+10h], rbp
0x1800a780f  push    rsi
0x1800a7810  push    rdi
0x1800a7811  push    r12
0x1800a7813  push    r14
0x1800a7815  push    r15
0x1800a7817  sub     rsp, 50h
0x1800a781b  xor     eax, eax
0x1800a781d  mov     r14, pdata
0x1800a7820  and     [r11+18h], eax
0x1800a7824  lea     pdata, [r11+18h]; pul
0x1800a7828  xorps   xmm0, xmm0
0x1800a782b  mov     word ptr [rsp+78h+bm.bmBits+6], ax
0x1800a7830  movups  xmmword ptr [rsp+78h+bm.bmType], xmm0
0x1800a7835  mov     r15, pos
0x1800a7838  xor     edi, edi
0x1800a783a  call    OLE1StreamToUL
0x1800a783f  mov     ebx, eax
0x1800a7841  test    eax, eax
0x1800a7843  js      loc_1800A79AB
0x1800a7849  mov     rax, [r15]
0x1800a784c  lea     r8d, [rdi+12h]
0x1800a7850  lea     pdata, [rsp+78h+bm]
0x1800a7855  mov     pos, r15
0x1800a7858  mov     rax, [rax]
0x1800a785b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7860  cmp     eax, 12h
0x1800a7863  jb      loc_1800A79A6
0x1800a7869  mov     eax, [rsp+78h+ul]
0x1800a7870  cmp     eax, 12h
0x1800a7873  jb      loc_1800A79A6
0x1800a7879  lea     r12d, [rax-12h]
0x1800a787d  mov     esi, r12d
0x1800a7880  call    GetSafeAllocSize
0x1800a7885  cmp     rsi, rax
0x1800a7888  jnb     loc_1800A799D
0x1800a788e  mov     edx, esi; dwBytes
0x1800a7890  lea     ecx, [rdi+2]; uFlags
0x1800a7893  call    cs:__imp_GlobalAlloc
0x1800a789a  nop     dword ptr [rax+rax+00h]
0x1800a789f  mov     rbp, rax
0x1800a78a2  test    rax, rax
0x1800a78a5  jz      loc_1800A799D
0x1800a78ab  mov     pos, rax; hMem
0x1800a78ae  call    cs:__imp_GlobalLock
0x1800a78b5  nop     dword ptr [rax+rax+00h]
0x1800a78ba  mov     rsi, rax
0x1800a78bd  test    rax, rax
0x1800a78c0  jnz     short loc_1800A78CC
0x1800a78c2  mov     ebx, 8007000Eh
0x1800a78c7  jmp     loc_1800A7978
0x1800a78cc  mov     rax, [r15]
0x1800a78cf  mov     r8d, r12d
0x1800a78d2  mov     pdata, rsi
0x1800a78d5  mov     pos, r15
0x1800a78d8  mov     rax, [rax]
0x1800a78db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a78e0  cmp     eax, r12d
0x1800a78e3  jnb     short loc_1800A78EC
0x1800a78e5  mov     ebx, 800401C0h
0x1800a78ea  jmp     short $errRtn_164
0x1800a78ec  movzx   r9d, [rsp+78h+bm.bmBitsPixel]; nBitCount
0x1800a78f2  movzx   r8d, [rsp+78h+bm.bmPlanes]; nPlanes
0x1800a78f8  movsx   edx, [rsp+78h+bm.bmHeight]; nHeight
0x1800a78fd  movsx   ecx, [rsp+78h+bm.bmWidth]; nWidth
0x1800a7902  mov     [rsp+78h+lpBits], rsi; lpBits
0x1800a7907  call    cs:__imp_CreateBitmap
0x1800a790e  nop     dword ptr [rax+rax+00h]
0x1800a7913  mov     rdi, rax
0x1800a7916  test    rax, rax
0x1800a7919  jnz     short loc_1800A7922
0x1800a791b  mov     ebx, 800401C3h
0x1800a7920  jmp     short $errRtn_164
0x1800a7922  xor     edx, edx; hpal
0x1800a7924  mov     pos, rax; hBitmap
0x1800a7927  call    ?UtConvertBitmapToDib@@YAPEAXPEAUHBITMAP__@@PEAUHPALETTE__@@@Z; UtConvertBitmapToDib(HBITMAP__ *,HPALETTE__ *)
0x1800a792c  mov     rsi, rax
0x1800a792f  test    rax, rax
0x1800a7932  jz      short loc_1800A791B
0x1800a7934  mov     pos, rax; hMem
0x1800a7937  call    cs:__imp_GlobalLock
0x1800a793e  nop     dword ptr [rax+rax+00h]
0x1800a7943  mov     [r14+8], rax
0x1800a7947  test    rax, rax
0x1800a794a  jnz     short loc_1800A7953
0x1800a794c  mov     ebx, 8007000Eh
0x1800a7951  jmp     short $errRtn_164
0x1800a7953  mov     pos, rsi; hMem
0x1800a7956  call    cs:__imp_GlobalSize
0x1800a795d  nop     dword ptr [rax+rax+00h]
0x1800a7962  mov     [r14], eax
0x1800a7965  mov     [r14+10h], rsi
0x1800a7969  mov     pos, rbp; hMem
0x1800a796c  call    cs:__imp_GlobalUnlock
0x1800a7973  nop     dword ptr [rax+rax+00h]
0x1800a7978  mov     pos, rbp; hMem
0x1800a797b  call    cs:__imp_GlobalFree
0x1800a7982  nop     dword ptr [rax+rax+00h]
0x1800a7987  test    rdi, rdi
0x1800a798a  jz      short loc_1800A79A2
0x1800a798c  mov     pos, rdi; ho
0x1800a798f  call    cs:__imp_DeleteObject
0x1800a7996  nop     dword ptr [rax+rax+00h]
0x1800a799b  jmp     short loc_1800A79A2
0x1800a799d  mov     ebx, 8007000Eh
0x1800a79a2  mov     eax, ebx
0x1800a79a4  jmp     short loc_1800A79AB
0x1800a79a6  mov     eax, 800401C0h
0x1800a79ab  lea     r11, [rsp+78h+var_28]
0x1800a79b0  mov     rbx, [r11+30h]
0x1800a79b4  mov     rbp, [r11+38h]
0x1800a79b8  mov     rsp, r11
0x1800a79bb  pop     r15
0x1800a79bd  pop     r14
0x1800a79bf  pop     r12
0x1800a79c1  pop     rdi
0x1800a79c2  pop     rsi
0x1800a79c3  retn
```
