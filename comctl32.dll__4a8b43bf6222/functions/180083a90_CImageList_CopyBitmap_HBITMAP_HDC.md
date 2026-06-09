# CImageList::_CopyBitmap(HBITMAP__ *,HDC__ *)

- ea: `0x180083a90`
- end: `0x180083b51`
- name: `?_CopyBitmap@CImageList@@QEAAPEAUHBITMAP__@@PEAU2@PEAUHDC__@@@Z`
- size: `193`
- prototype: `HBITMAP(CImageList *__hidden this, HBITMAP, HDC)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007f860`

## callees

- `0x180082a7c`
- `0x180083a90`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x180083ada`
- `GDI32!CreateCompatibleBitmap` at `0x180083ada`
- `GDI32!BitBlt` at `0x180083b26`
- `GDI32!BitBlt` at `0x180083b26`
- `GDI32!GetObjectW` at `0x180083ab6`
- `GDI32!GetObjectW` at `0x180083ab6`
- `KERNEL32!EnterCriticalSection` at `0x180083ac8`
- `KERNEL32!EnterCriticalSection` at `0x180083ac8`
- `KERNEL32!LeaveCriticalSection` at `0x180083b3a`
- `KERNEL32!LeaveCriticalSection` at `0x180083b3a`

## pseudocode

```c
HBITMAP __fastcall CImageList::_CopyBitmap(CImageList *this, HBITMAP a2, HDC a3)
{
  HBITMAP v4; // rbx
  HBITMAP CompatibleBitmap; // rax
  int v7[10]; // [rsp+50h] [rbp-28h] BYREF

  v4 = 0;
  memset(v7, 0, 32);
  if ( GetObjectW(a2, 32, v7) == 32 )
  {
    EnterCriticalSection(&g_csDll);
    CompatibleBitmap = CreateCompatibleBitmap(a3, v7[1], v7[2]);
    v4 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      CImageList::SelectDstBitmap(CompatibleBitmap);
      BitBlt(g_hdcDst, 0, 0, v7[1], v7[2], a3, 0, 0, 0xCC0020u);
      CImageList::SelectDstBitmap(0);
    }
    LeaveCriticalSection(&g_csDll);
  }
  return v4;
}

```

## disassembly

```asm
0x180083a90  mov     rax, rsp
0x180083a93  mov     [rax+8], rbx
0x180083a97  push    rdi
0x180083a98  sub     rsp, 70h
0x180083a9c  xorps   xmm0, xmm0
0x180083a9f  mov     rdi, r8
0x180083aa2  mov     rcx, rdx; h
0x180083aa5  lea     r8, [rax-28h]; pv
0x180083aa9  xor     ebx, ebx
0x180083aab  movups  xmmword ptr [rax-28h], xmm0
0x180083aaf  movups  xmmword ptr [rax-18h], xmm0
0x180083ab3  lea     edx, [rbx+20h]; c
0x180083ab6  call    cs:__imp_GetObjectW
0x180083abc  cmp     eax, 20h ; ' '
0x180083abf  jnz     short loc_180083B40
0x180083ac1  lea     rcx, g_csDll; lpCriticalSection
0x180083ac8  call    cs:__imp_EnterCriticalSection
0x180083ace  mov     r8d, [rsp+78h+cy]; cy
0x180083ad3  mov     rcx, rdi; hdc
0x180083ad6  mov     edx, [rsp+78h+var_24]; cx
0x180083ada  call    cs:__imp_CreateCompatibleBitmap
0x180083ae0  mov     rbx, rax
0x180083ae3  test    rax, rax
0x180083ae6  jz      short loc_180083B33
0x180083ae8  mov     rcx, rax; HBITMAP
0x180083aeb  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180083af0  mov     edx, [rsp+78h+cy]
0x180083af4  xor     r8d, r8d; y
0x180083af7  mov     r9d, [rsp+78h+var_24]; cx
0x180083afc  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180083b03  mov     [rsp+78h+rop], 0CC0020h; rop
0x180083b0b  mov     [rsp+78h+y1], 0; y1
0x180083b13  mov     [rsp+78h+x1], 0; x1
0x180083b1b  mov     [rsp+78h+hdcSrc], rdi; hdcSrc
0x180083b20  mov     [rsp+78h+var_58], edx; cy
0x180083b24  xor     edx, edx; x
0x180083b26  call    cs:__imp_BitBlt
0x180083b2c  xor     ecx, ecx; HBITMAP
0x180083b2e  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x180083b33  lea     rcx, g_csDll; lpCriticalSection
0x180083b3a  call    cs:__imp_LeaveCriticalSection
0x180083b40  mov     rax, rbx
0x180083b43  mov     rbx, [rsp+78h+arg_0]
0x180083b4b  add     rsp, 70h
0x180083b4f  pop     rdi
0x180083b50  retn
```
