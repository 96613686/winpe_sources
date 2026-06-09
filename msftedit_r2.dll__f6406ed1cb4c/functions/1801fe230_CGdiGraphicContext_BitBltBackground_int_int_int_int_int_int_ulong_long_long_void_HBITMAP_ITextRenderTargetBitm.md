# CGdiGraphicContext::BitBltBackground(int,int,int,int,int,int,ulong,long,long,void *,HBITMAP__ * *,ITextRenderTargetBitmap * *)

- ea: `0x1801fe230`
- end: `0x1801fe3c0`
- name: `?BitBltBackground@CGdiGraphicContext@@EEAA_NHHHHHHKJJPEAXPEAPEAUHBITMAP__@@PEAPEAUITextRenderTargetBitmap@@@Z`
- size: `400`
- prototype: `bool(CGdiGraphicContext *__hidden this, int, int, int, int, int, int, unsigned int, int, int, void *, HBITMAP *, struct ITextRenderTargetBitmap **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18013d268`
- `0x1801e11d8`
- `0x1801e8378`
- `0x1801e9924`
- `0x1801fe230`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fe272`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fe272`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fe349`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fe349`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801fe399`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801fe399`

## pseudocode

```c
bool __fastcall CGdiGraphicContext::BitBltBackground(
        HDC *this,
        int a2,
        int a3,
        int a4,
        int cy,
        int x1,
        int y1,
        DWORD rop,
        int a9,
        int a10,
        void *a11,
        HBITMAP *a12)
{
  int v14; // ebx
  HDC *v16; // r14
  HDC CompatibleDC; // rax
  void *v18; // rdx
  CBackgroundImage *v19; // rsi
  int v20; // ebx
  int v21; // eax
  CImage *v22; // rax
  CImage *v23; // rbx
  HBITMAP v24; // rax

  v14 = a2;
  if ( a12 )
  {
    v16 = this + 3;
    if ( this[4] )
      return BitBlt(*v16, v14, a3, a4, cy, this[4], x1, y1, rop);
    CompatibleDC = CreateCompatibleDC(*v16);
    this[4] = CompatibleDC;
    if ( CompatibleDC )
    {
      v18 = *a12;
      if ( *a12 )
      {
LABEL_10:
        this[5] = (HDC)SelectObject(this[4], v18);
        return BitBlt(*v16, v14, a3, a4, cy, this[4], x1, y1, rop);
      }
      v19 = (CBackgroundImage *)operator new(0xE0u);
      v20 = (*((__int64 (__fastcall **)(char *))this[1] + 2))((char *)this + 8);
      v21 = (*((__int64 (__fastcall **)(char *))this[1] + 1))((char *)this + 8);
      v22 = CBackgroundImage::CBackgroundImage(v19, v21, v20);
      v23 = v22;
      if ( v22 )
      {
        if ( !(unsigned int)CImage::LoadFromHglobal(v22, a9, a10, a11) )
        {
          CImage::CheckGdiBitmap(v23, *v16, 0);
          v24 = (HBITMAP)*((_QWORD *)v23 + 16);
          *((_QWORD *)v23 + 16) = 0;
          *a12 = v24;
        }
        (*(void (__fastcall **)(CImage *))(*(_QWORD *)v23 + 16LL))(v23);
        v18 = *a12;
        if ( *a12 )
        {
          v14 = a2;
          goto LABEL_10;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801fe230  mov     [rsp+arg_8], edx
0x1801fe234  push    rbx
0x1801fe235  push    rbp
0x1801fe236  push    rsi
0x1801fe237  push    rdi
0x1801fe238  push    r12
0x1801fe23a  push    r13
0x1801fe23c  push    r14
0x1801fe23e  push    r15
0x1801fe240  sub     rsp, 58h
0x1801fe244  mov     r15, [rsp+98h+arg_58]
0x1801fe24c  mov     r12d, r9d
0x1801fe24f  mov     r13d, r8d
0x1801fe252  mov     ebx, edx
0x1801fe254  mov     rbp, rcx
0x1801fe257  test    r15, r15
0x1801fe25a  jz      loc_1801FE3AC
0x1801fe260  cmp     qword ptr [rcx+20h], 0
0x1801fe265  lea     r14, [rcx+18h]
0x1801fe269  jnz     loc_1801FE359
0x1801fe26f  mov     rcx, [r14]; hdc
0x1801fe272  call    cs:__imp_CreateCompatibleDC
0x1801fe279  nop     dword ptr [rax+rax+00h]
0x1801fe27e  mov     [rbp+20h], rax
0x1801fe282  test    rax, rax
0x1801fe285  jz      loc_1801FE3AC
0x1801fe28b  mov     rdx, [r15]
0x1801fe28e  test    rdx, rdx
0x1801fe291  jnz     loc_1801FE345
0x1801fe297  mov     ecx, 0E0h; Size
0x1801fe29c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801fe2a1  lea     rdi, [rbp+8]
0x1801fe2a5  mov     rsi, rax
0x1801fe2a8  mov     rdx, [rdi]
0x1801fe2ab  mov     rcx, rdi
0x1801fe2ae  mov     rax, [rdx+10h]
0x1801fe2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fe2b7  mov     rdx, [rdi]
0x1801fe2ba  mov     ebx, eax
0x1801fe2bc  mov     rcx, rdi
0x1801fe2bf  mov     rax, [rdx+8]
0x1801fe2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fe2c8  mov     r8d, ebx; int
0x1801fe2cb  mov     edx, eax; int
0x1801fe2cd  mov     rcx, rsi; this
0x1801fe2d0  call    ??0CBackgroundImage@@QEAA@JJ@Z; CBackgroundImage::CBackgroundImage(long,long)
0x1801fe2d5  mov     rbx, rax
0x1801fe2d8  test    rax, rax
0x1801fe2db  jz      loc_1801FE3AC
0x1801fe2e1  mov     r9, [rsp+98h+arg_50]; void *
0x1801fe2e9  mov     rcx, rax; this
0x1801fe2ec  mov     r8d, [rsp+98h+arg_48]; int
0x1801fe2f4  mov     edx, [rsp+98h+arg_40]; int
0x1801fe2fb  call    ?LoadFromHglobal@CImage@@QEAAJJJPEAX@Z; CImage::LoadFromHglobal(long,long,void *)
0x1801fe300  test    eax, eax
0x1801fe302  jnz     short loc_1801FE327
0x1801fe304  mov     rdx, [r14]; HDC
0x1801fe307  xor     r8d, r8d; struct tagRECT *
0x1801fe30a  mov     rcx, rbx; this
0x1801fe30d  call    ?CheckGdiBitmap@CImage@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z; CImage::CheckGdiBitmap(HDC__ *,tagRECT const *)
0x1801fe312  mov     rax, [rbx+80h]
0x1801fe319  mov     qword ptr [rbx+80h], 0
0x1801fe324  mov     [r15], rax
0x1801fe327  mov     rax, [rbx]
0x1801fe32a  mov     rcx, rbx
0x1801fe32d  mov     rax, [rax+10h]
0x1801fe331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fe336  mov     rdx, [r15]; h
0x1801fe339  test    rdx, rdx
0x1801fe33c  jz      short loc_1801FE3AC
0x1801fe33e  mov     ebx, [rsp+98h+arg_8]
0x1801fe345  mov     rcx, [rbp+20h]; hdc
0x1801fe349  call    cs:__imp_SelectObject
0x1801fe350  nop     dword ptr [rax+rax+00h]
0x1801fe355  mov     [rbp+28h], rax
0x1801fe359  mov     eax, [rsp+98h+arg_38]
0x1801fe360  mov     r9d, r12d; cx
0x1801fe363  mov     rcx, [r14]; hdc
0x1801fe366  mov     r8d, r13d; y
0x1801fe369  mov     [rsp+98h+rop], eax; rop
0x1801fe36d  mov     edx, ebx; x
0x1801fe36f  mov     eax, [rsp+98h+arg_30]
0x1801fe376  mov     [rsp+98h+y1], eax; y1
0x1801fe37a  mov     eax, [rsp+98h+arg_28]
0x1801fe381  mov     [rsp+98h+x1], eax; x1
0x1801fe385  mov     rax, [rbp+20h]
0x1801fe389  mov     [rsp+98h+hdcSrc], rax; hdcSrc
0x1801fe38e  mov     eax, [rsp+98h+arg_20]
0x1801fe395  mov     [rsp+98h+cy], eax; cy
0x1801fe399  call    cs:__imp_BitBlt
0x1801fe3a0  nop     dword ptr [rax+rax+00h]
0x1801fe3a5  test    eax, eax
0x1801fe3a7  setnz   al
0x1801fe3aa  jmp     short loc_1801FE3AE
0x1801fe3ac  xor     al, al
0x1801fe3ae  add     rsp, 58h
0x1801fe3b2  pop     r15
0x1801fe3b4  pop     r14
0x1801fe3b6  pop     r13
0x1801fe3b8  pop     r12
0x1801fe3ba  pop     rdi
0x1801fe3bb  pop     rsi
0x1801fe3bc  pop     rbp
0x1801fe3bd  pop     rbx
0x1801fe3be  retn
```
