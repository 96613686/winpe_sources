# CreateUplevelBitmap(int,int,int,int,int,HBITMAP__ * *,void * *)

- ea: `0x1800ca600`
- end: `0x1800ca7f2`
- name: `?CreateUplevelBitmap@@YAJHHHHHPEAPEAUHBITMAP__@@PEAPEAX@Z`
- size: `498`
- prototype: `__int64 __usercall@<rax>(int cx@<ecx>, int@<edx>, int@<r8d>, int@<r9d>, int, HBITMAP *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009d868`
- `0x18009d950`

## callees

- `0x18007b714`
- `0x1800ca600`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800ca743`
- `GDI32!DeleteObject` at `0x1800ca743`
- `GDI32!GetObjectW` at `0x1800ca7db`
- `GDI32!GetObjectW` at `0x1800ca7db`
- `GDI32!SelectObject` at `0x1800ca66a`
- `GDI32!SelectObject` at `0x1800ca6d0`
- `GDI32!SelectObject` at `0x1800ca73a`
- `GDI32!SelectObject` at `0x1800ca75d`
- `GDI32!SelectObject` at `0x1800ca66a`
- `GDI32!SelectObject` at `0x1800ca6d0`
- `GDI32!SelectObject` at `0x1800ca73a`
- `GDI32!SelectObject` at `0x1800ca75d`
- `GDI32!DeleteDC` at `0x1800ca74f`
- `GDI32!DeleteDC` at `0x1800ca766`
- `GDI32!DeleteDC` at `0x1800ca74f`
- `GDI32!DeleteDC` at `0x1800ca766`
- `GDI32!CreateCompatibleDC` at `0x1800ca652`
- `GDI32!CreateCompatibleDC` at `0x1800ca677`
- `GDI32!CreateCompatibleDC` at `0x1800ca652`
- `GDI32!CreateCompatibleDC` at `0x1800ca677`
- `GDI32!CreateCompatibleBitmap` at `0x1800ca7b3`
- `GDI32!CreateCompatibleBitmap` at `0x1800ca7b3`
- `GDI32!CreateBitmap` at `0x1800ca6b8`
- `GDI32!CreateBitmap` at `0x1800ca6b8`
- `GDI32!BitBlt` at `0x1800ca720`
- `GDI32!BitBlt` at `0x1800ca720`

## pseudocode

```c
__int64 __fastcall CreateUplevelBitmap(unsigned int cx, int a2, int a3, int a4, int a5, HBITMAP *a6, void **a7)
{
  HGDIOBJ *v7; // r15
  unsigned int v11; // ebp
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HDC v14; // rsi
  unsigned int v15; // ecx
  HBITMAP Bitmap; // rax
  HBITMAP v17; // rbx
  int v18; // ebp
  HGDIOBJ v19; // r12
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ h; // [rsp+60h] [rbp-68h]
  __int128 pv; // [rsp+68h] [rbp-60h] BYREF
  __int128 v25; // [rsp+78h] [rbp-50h]

  v7 = (HGDIOBJ *)a6;
  v11 = -2147024882;
  CompatibleDC = CreateCompatibleDC(0);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    h = SelectObject(CompatibleDC, *a6);
    v14 = CreateCompatibleDC(0);
    if ( !v14 )
    {
LABEL_11:
      SelectObject(hdcSrc, h);
      DeleteDC(hdcSrc);
      return v11;
    }
    v15 = a2 * a3;
    if ( a5 )
    {
      Bitmap = CreateBitmap(cx, v15, 1u, 1u, 0);
    }
    else
    {
      if ( !a4 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(hdcSrc, cx, v15);
        v17 = CompatibleBitmap;
        if ( CompatibleBitmap )
        {
          pv = 0;
          v25 = 0;
          GetObjectW(CompatibleBitmap, 32, &pv);
          *a7 = (void *)*((_QWORD *)&v25 + 1);
          goto LABEL_6;
        }
LABEL_10:
        DeleteDC(v14);
        goto LABEL_11;
      }
      Bitmap = (HBITMAP)CreateDIB(hdcSrc, cx, v15, a7);
    }
    v17 = Bitmap;
    if ( Bitmap )
    {
LABEL_6:
      v18 = 0;
      v19 = SelectObject(v14, v17);
      if ( a3 > 0 )
      {
        do
        {
          BitBlt(v14, 0, v18 * a2, cx, a2, hdcSrc, cx * (v18 & 3), a2 * ((unsigned int)v18 >> 2), 0xCC0020u);
          ++v18;
        }
        while ( v18 < a3 );
        v7 = (HGDIOBJ *)a6;
      }
      v11 = 0;
      SelectObject(v14, v19);
      DeleteObject(*v7);
      *v7 = v17;
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  return v11;
}

```

## disassembly

```asm
0x1800ca600  mov     [rsp+arg_18], rbx
0x1800ca605  push    rbp
0x1800ca606  push    rsi
0x1800ca607  push    rdi
0x1800ca608  push    r12
0x1800ca60a  push    r13
0x1800ca60c  push    r14
0x1800ca60e  push    r15
0x1800ca610  sub     rsp, 90h
0x1800ca617  mov     rax, cs:__security_cookie
0x1800ca61e  xor     rax, rsp
0x1800ca621  mov     [rsp+0C8h+var_40], rax
0x1800ca629  mov     r15, [rsp+0C8h+arg_28]
0x1800ca631  mov     r14d, ecx
0x1800ca634  mov     r12, [rsp+0C8h+arg_30]
0x1800ca63c  xor     ecx, ecx; hdc
0x1800ca63e  mov     [rsp+0C8h+var_70], r15
0x1800ca643  mov     ebx, r9d
0x1800ca646  mov     r13d, r8d
0x1800ca649  mov     [rsp+0C8h+cy], edx
0x1800ca64d  mov     ebp, 8007000Eh
0x1800ca652  call    cs:__imp_CreateCompatibleDC
0x1800ca658  mov     rdi, rax
0x1800ca65b  test    rax, rax
0x1800ca65e  jz      loc_1800CA76C
0x1800ca664  mov     rdx, [r15]; h
0x1800ca667  mov     rcx, rax; hdc
0x1800ca66a  call    cs:__imp_SelectObject
0x1800ca670  xor     ecx, ecx; hdc
0x1800ca672  mov     [rsp+0C8h+h], rax
0x1800ca677  call    cs:__imp_CreateCompatibleDC
0x1800ca67d  mov     rsi, rax
0x1800ca680  test    rax, rax
0x1800ca683  jz      loc_1800CA755
0x1800ca689  mov     ecx, r13d
0x1800ca68c  mov     eax, 1
0x1800ca691  imul    ecx, [rsp+0C8h+cy]
0x1800ca696  cmp     [rsp+0C8h+arg_20], 0
0x1800ca69e  jz      loc_1800CA799
0x1800ca6a4  mov     edx, ecx; nHeight
0x1800ca6a6  mov     [rsp+0C8h+lpBits], 0; lpBits
0x1800ca6af  mov     ecx, r14d; nWidth
0x1800ca6b2  mov     r9d, eax; nBitCount
0x1800ca6b5  mov     r8d, eax; nPlanes
0x1800ca6b8  call    cs:__imp_CreateBitmap
0x1800ca6be  mov     rbx, rax
0x1800ca6c1  test    rax, rax
0x1800ca6c4  jz      loc_1800CA74C
0x1800ca6ca  mov     rdx, rbx; h
0x1800ca6cd  mov     rcx, rsi; hdc
0x1800ca6d0  call    cs:__imp_SelectObject
0x1800ca6d6  xor     ebp, ebp
0x1800ca6d8  mov     r12, rax
0x1800ca6db  test    r13d, r13d
0x1800ca6de  jle     short loc_1800CA732
0x1800ca6e0  mov     r15d, [rsp+0C8h+cy]
0x1800ca6e5  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1800ca6ed  mov     ecx, ebp
0x1800ca6ef  shr     ecx, 2
0x1800ca6f2  mov     eax, ebp
0x1800ca6f4  imul    ecx, r15d
0x1800ca6f8  and     eax, 3
0x1800ca6fb  imul    eax, r14d
0x1800ca6ff  mov     r8d, r15d
0x1800ca702  imul    r8d, ebp; y
0x1800ca706  mov     r9d, r14d; cx
0x1800ca709  xor     edx, edx; x
0x1800ca70b  mov     [rsp+0C8h+y1], ecx; y1
0x1800ca70f  mov     rcx, rsi; hdc
0x1800ca712  mov     [rsp+0C8h+x1], eax; x1
0x1800ca716  mov     [rsp+0C8h+hdcSrc], rdi; hdcSrc
0x1800ca71b  mov     dword ptr [rsp+0C8h+lpBits], r15d; cy
0x1800ca720  call    cs:__imp_BitBlt
0x1800ca726  inc     ebp
0x1800ca728  cmp     ebp, r13d
0x1800ca72b  jl      short loc_1800CA6E5
0x1800ca72d  mov     r15, [rsp+0C8h+var_70]
0x1800ca732  mov     rdx, r12; h
0x1800ca735  mov     rcx, rsi; hdc
0x1800ca738  xor     ebp, ebp
0x1800ca73a  call    cs:__imp_SelectObject
0x1800ca740  mov     rcx, [r15]; ho
0x1800ca743  call    cs:__imp_DeleteObject
0x1800ca749  mov     [r15], rbx
0x1800ca74c  mov     rcx, rsi; hdc
0x1800ca74f  call    cs:__imp_DeleteDC
0x1800ca755  mov     rdx, [rsp+0C8h+h]; h
0x1800ca75a  mov     rcx, rdi; hdc
0x1800ca75d  call    cs:__imp_SelectObject
0x1800ca763  mov     rcx, rdi; hdc
0x1800ca766  call    cs:__imp_DeleteDC
0x1800ca76c  mov     eax, ebp
0x1800ca76e  mov     rcx, [rsp+0C8h+var_40]
0x1800ca776  xor     rcx, rsp; StackCookie
0x1800ca779  call    __security_check_cookie
0x1800ca77e  mov     rbx, [rsp+0C8h+arg_18]
0x1800ca786  add     rsp, 90h
0x1800ca78d  pop     r15
0x1800ca78f  pop     r14
0x1800ca791  pop     r13
0x1800ca793  pop     r12
0x1800ca795  pop     rdi
0x1800ca796  pop     rsi
0x1800ca797  pop     rbp
0x1800ca798  retn
0x1800ca799  mov     r8d, ecx; cy
0x1800ca79c  mov     rcx, rdi; hdc
0x1800ca79f  mov     edx, r14d; cx
0x1800ca7a2  test    ebx, ebx
0x1800ca7a4  jz      short loc_1800CA7B3
0x1800ca7a6  mov     r9, r12
0x1800ca7a9  call    CreateDIB
0x1800ca7ae  jmp     loc_1800CA6BE
0x1800ca7b3  call    cs:__imp_CreateCompatibleBitmap
0x1800ca7b9  mov     rbx, rax
0x1800ca7bc  test    rax, rax
0x1800ca7bf  jz      short loc_1800CA74C
0x1800ca7c1  xorps   xmm0, xmm0
0x1800ca7c4  lea     r8, [rsp+0C8h+pv]; pv
0x1800ca7c9  mov     edx, 20h ; ' '; c
0x1800ca7ce  mov     rcx, rax; h
0x1800ca7d1  movups  [rsp+0C8h+pv], xmm0
0x1800ca7d6  movups  [rsp+0C8h+var_50], xmm0
0x1800ca7db  call    cs:__imp_GetObjectW
0x1800ca7e1  mov     rax, qword ptr [rsp+0C8h+var_50+8]
0x1800ca7e9  mov     [r12], rax
0x1800ca7ed  jmp     loc_1800CA6CA
```
