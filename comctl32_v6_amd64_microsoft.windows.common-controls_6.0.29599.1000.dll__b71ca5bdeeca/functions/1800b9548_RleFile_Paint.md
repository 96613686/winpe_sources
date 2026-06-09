# RleFile_Paint

- ea: `0x1800b9548`
- end: `0x1800b96b2`
- name: `RleFile_Paint`
- size: `362`
- prototype: `__int64 __usercall@<rax>(struct _RLEFILE *@<rcx>, HDC hdcDest@<rdx>, int y, int wDest, int hDest, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b8bdc`
- `0x1800b9430`

## callees

- `0x1800b9548`
- `0x1800b96b8`
- `0x1800b979c`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800b9638`
- `GDI32!DeleteObject` at `0x1800b9638`
- `GDI32!SelectObject` at `0x1800b95c3`
- `GDI32!SelectObject` at `0x1800b962f`
- `GDI32!SelectObject` at `0x1800b95c3`
- `GDI32!SelectObject` at `0x1800b962f`
- `GDI32!DeleteDC` at `0x1800b9641`
- `GDI32!DeleteDC` at `0x1800b9641`
- `GDI32!CreateCompatibleDC` at `0x1800b958f`
- `GDI32!CreateCompatibleDC` at `0x1800b958f`
- `GDI32!CreateCompatibleBitmap` at `0x1800b95ab`
- `GDI32!CreateCompatibleBitmap` at `0x1800b95ab`
- `GDI32!BitBlt` at `0x1800b961e`
- `GDI32!BitBlt` at `0x1800b961e`
- `GDI32!GdiTransparentBlt` at `0x1800b96a7`
- `GDI32!GdiTransparentBlt` at `0x1800b96a7`

## pseudocode

```c
__int64 __fastcall RleFile_Paint(
        struct _RLEFILE *a1,
        HDC hdcDest,
        __int64 a3,
        int a4,
        int y,
        int wDest,
        int hDest,
        int a8)
{
  unsigned int v11; // r14d
  HDC hdcSrc; // rdi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v14; // r15
  HGDIOBJ v15; // rax
  int v16; // r12d
  int v17; // ebp
  HGDIOBJ h; // [rsp+B0h] [rbp+8h]

  if ( !a1 || !*((_QWORD *)a1 + 146) )
    return 0;
  v11 = RleFile_Seek(a1);
  if ( v11 )
  {
    hdcSrc = CreateCompatibleDC(hdcDest);
    if ( hdcSrc )
    {
      CompatibleBitmap = CreateCompatibleBitmap(hdcDest, *((_DWORD *)a1 + 1), *((_DWORD *)a1 + 2));
      v14 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v15 = SelectObject(hdcSrc, CompatibleBitmap);
        v16 = *((_DWORD *)a1 + 10);
        v17 = *((_DWORD *)a1 + 11);
        h = v15;
        while ( v17 <= v16 )
        {
          RleFile_Draw(a1, hdcSrc);
          ++v17;
        }
        if ( a8 )
          GdiTransparentBlt(
            hdcDest,
            a4,
            y,
            wDest,
            hDest,
            hdcSrc,
            0,
            0,
            *((_DWORD *)a1 + 1),
            *((_DWORD *)a1 + 2),
            *((_DWORD *)a1 + 296));
        else
          BitBlt(hdcDest, a4, y, wDest, hDest, hdcSrc, 0, 0, 0xCC0020u);
        SelectObject(hdcSrc, h);
        DeleteObject(v14);
      }
      DeleteDC(hdcSrc);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800b9548  push    rbx
0x1800b954a  push    rbp
0x1800b954b  push    rsi
0x1800b954c  push    rdi
0x1800b954d  push    r12
0x1800b954f  push    r13
0x1800b9551  push    r14
0x1800b9553  push    r15
0x1800b9555  sub     rsp, 68h
0x1800b9559  mov     r13d, r9d
0x1800b955c  mov     rsi, rdx
0x1800b955f  mov     rbx, rcx
0x1800b9562  test    rcx, rcx
0x1800b9565  jz      loc_1800B9670
0x1800b956b  cmp     qword ptr [rcx+490h], 0
0x1800b9573  jz      loc_1800B9670
0x1800b9579  mov     edx, r8d
0x1800b957c  call    RleFile_Seek
0x1800b9581  mov     r14d, eax
0x1800b9584  test    eax, eax
0x1800b9586  jz      loc_1800B9647
0x1800b958c  mov     rcx, rsi; hdc
0x1800b958f  call    cs:__imp_CreateCompatibleDC
0x1800b9595  mov     rdi, rax
0x1800b9598  test    rax, rax
0x1800b959b  jz      loc_1800B9647
0x1800b95a1  mov     r8d, [rbx+8]; cy
0x1800b95a5  mov     rcx, rsi; hdc
0x1800b95a8  mov     edx, [rbx+4]; cx
0x1800b95ab  call    cs:__imp_CreateCompatibleBitmap
0x1800b95b1  mov     r15, rax
0x1800b95b4  test    rax, rax
0x1800b95b7  jz      loc_1800B963E
0x1800b95bd  mov     rdx, rax; h
0x1800b95c0  mov     rcx, rdi; hdc
0x1800b95c3  call    cs:__imp_SelectObject
0x1800b95c9  mov     r12d, [rbx+28h]
0x1800b95cd  mov     ebp, [rbx+2Ch]
0x1800b95d0  mov     [rsp+0A8h+h], rax
0x1800b95d8  cmp     ebp, r12d
0x1800b95db  jle     short loc_1800B965B
0x1800b95dd  mov     r9d, [rsp+0A8h+wDest]; wDest
0x1800b95e5  xor     ecx, ecx
0x1800b95e7  mov     edx, r13d; xoriginDest
0x1800b95ea  mov     r8d, [rsp+0A8h+y]; yoriginDest
0x1800b95f2  cmp     [rsp+0A8h+arg_38], ecx
0x1800b95f9  jnz     short loc_1800B9674
0x1800b95fb  mov     eax, [rsp+0A8h+hDest]
0x1800b9602  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1800b960a  mov     [rsp+0A8h+y1], ecx; y1
0x1800b960e  mov     [rsp+0A8h+x1], ecx; x1
0x1800b9612  mov     rcx, rsi; hdc
0x1800b9615  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x1800b961a  mov     [rsp+0A8h+cy], eax; cy
0x1800b961e  call    cs:__imp_BitBlt
0x1800b9624  mov     rdx, [rsp+0A8h+h]; h
0x1800b962c  mov     rcx, rdi; hdc
0x1800b962f  call    cs:__imp_SelectObject
0x1800b9635  mov     rcx, r15; ho
0x1800b9638  call    cs:__imp_DeleteObject
0x1800b963e  mov     rcx, rdi; hdc
0x1800b9641  call    cs:__imp_DeleteDC
0x1800b9647  mov     eax, r14d
0x1800b964a  add     rsp, 68h
0x1800b964e  pop     r15
0x1800b9650  pop     r14
0x1800b9652  pop     r13
0x1800b9654  pop     r12
0x1800b9656  pop     rdi
0x1800b9657  pop     rsi
0x1800b9658  pop     rbp
0x1800b9659  pop     rbx
0x1800b965a  retn
0x1800b965b  mov     r8d, ebp
0x1800b965e  mov     rdx, rdi; hdc
0x1800b9661  mov     rcx, rbx; struct _RLEFILE *
0x1800b9664  call    RleFile_Draw
0x1800b9669  inc     ebp
0x1800b966b  jmp     loc_1800B95D8
0x1800b9670  xor     eax, eax
0x1800b9672  jmp     short loc_1800B964A
0x1800b9674  mov     eax, [rbx+4A0h]
0x1800b967a  mov     [rsp+0A8h+crTransparent], eax; crTransparent
0x1800b967e  mov     eax, [rbx+8]
0x1800b9681  mov     [rsp+0A8h+hSrc], eax; hSrc
0x1800b9685  mov     eax, [rbx+4]
0x1800b9688  mov     [rsp+0A8h+rop], eax; wSrc
0x1800b968c  mov     eax, [rsp+0A8h+hDest]
0x1800b9693  mov     [rsp+0A8h+y1], ecx; yoriginSrc
0x1800b9697  mov     [rsp+0A8h+x1], ecx; xoriginSrc
0x1800b969b  mov     rcx, rsi; hdcDest
0x1800b969e  mov     [rsp+0A8h+hdcSrc], rdi; hdcSrc
0x1800b96a3  mov     [rsp+0A8h+cy], eax; hDest
0x1800b96a7  call    cs:__imp_GdiTransparentBlt
0x1800b96ad  jmp     loc_1800B9624
```
