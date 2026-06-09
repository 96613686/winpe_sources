# CImageList::_ReplaceIcon(int,HICON__ *,int *)

- ea: `0x180084b34`
- end: `0x180084cbd`
- name: `?_ReplaceIcon@CImageList@@QEAAJHPEAUHICON__@@PEAH@Z`
- size: `393`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int, HICON, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180082850`

## callees

- `0x1800115f0`
- `0x1800835e8`
- `0x180084b34`
- `0x180090020`

## import_xrefs

- `USER32!DestroyIcon` at `0x180084c9a`
- `USER32!DestroyIcon` at `0x180084c9a`
- `USER32!CopyImage` at `0x180084b93`
- `USER32!CopyImage` at `0x180084b93`
- `USER32!FillRect` at `0x180084c06`
- `USER32!FillRect` at `0x180084c06`
- `USER32!DrawIconEx` at `0x180084c45`
- `USER32!DrawIconEx` at `0x180084c8c`
- `USER32!DrawIconEx` at `0x180084c45`
- `USER32!DrawIconEx` at `0x180084c8c`

## pseudocode

```c
int __fastcall CImageList::_ReplaceIcon(CImageList *this, int a2, HICON a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  int result; // eax
  HICON v9; // rdi
  HDC v10; // rcx
  UINT flags; // [rsp+20h] [rbp-78h]
  int cyWidth; // [rsp+28h] [rbp-70h]
  int v13; // [rsp+50h] [rbp-48h] BYREF
  RECT rc; // [rsp+58h] [rbp-40h] BYREF

  v13 = a2;
  *a4 = -1;
  v6 = a2;
  rc = 0;
  if ( a2 < -1 )
    return -2147024809;
  v9 = (HICON)CopyImage(a3, 1u, *((_DWORD *)this + 17), *((_DWORD *)this + 18), 0x4004u);
  if ( !v9 )
    return -2147024882;
  if ( v6 != -1 || (result = CImageList::_Add(this, 0, 0, 1, flags, cyWidth, &v13), v6 = v13, v13 != -1) )
  {
    result = (*(__int64 (__fastcall **)(char *, _QWORD, RECT *))(*((_QWORD *)this + 2) + 120LL))(
               (char *)this + 16,
               v6,
               &rc);
    if ( result >= 0 )
    {
      FillRect(*((HDC *)this + 15), &rc, *((HBRUSH *)this + 12));
      DrawIconEx(*((HDC *)this + 15), rc.left, rc.top, v9, 0, 0, 0, 0, 3u);
      v10 = (HDC)*((_QWORD *)this + 16);
      if ( v10 )
        DrawIconEx(v10, rc.left, rc.top, v9, 0, 0, 0, 0, 1u);
      if ( v9 != a3 )
        DestroyIcon(v9);
      *a4 = v6;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180084b34  push    rbx
0x180084b36  push    rbp
0x180084b37  push    rsi
0x180084b38  push    rdi
0x180084b39  push    r14
0x180084b3b  sub     rsp, 70h
0x180084b3f  mov     rax, cs:__security_cookie
0x180084b46  xor     rax, rsp
0x180084b49  mov     [rsp+98h+var_30], rax
0x180084b4e  mov     [rsp+98h+var_48], edx
0x180084b52  xorps   xmm0, xmm0
0x180084b55  mov     dword ptr [r9], 0FFFFFFFFh
0x180084b5c  mov     r14, r9
0x180084b5f  mov     rbp, r8
0x180084b62  mov     ebx, edx
0x180084b64  mov     rsi, rcx
0x180084b67  movups  xmmword ptr [rsp+98h+rc.left], xmm0
0x180084b6c  cmp     edx, 0FFFFFFFFh
0x180084b6f  jge     short loc_180084B7B
0x180084b71  mov     eax, 80070057h
0x180084b76  jmp     loc_180084CA5
0x180084b7b  mov     r9d, [rcx+48h]; cy
0x180084b7f  mov     edx, 1; type
0x180084b84  mov     r8d, [rcx+44h]; cx
0x180084b88  mov     rcx, rbp; h
0x180084b8b  mov     [rsp+98h+flags], 4004h; int
0x180084b93  call    cs:__imp_CopyImage
0x180084b99  mov     rdi, rax
0x180084b9c  test    rax, rax
0x180084b9f  jnz     short loc_180084BAB
0x180084ba1  mov     eax, 8007000Eh
0x180084ba6  jmp     loc_180084CA5
0x180084bab  xor     eax, eax
0x180084bad  cmp     ebx, 0FFFFFFFFh
0x180084bb0  jnz     short loc_180084BDA
0x180084bb2  lea     rax, [rsp+98h+var_48]
0x180084bb7  xor     r8d, r8d; HBITMAP
0x180084bba  lea     r9d, [rbx+2]; int
0x180084bbe  mov     qword ptr [rsp+98h+istepIfAniCur], rax; int *
0x180084bc3  xor     edx, edx; HBITMAP
0x180084bc5  mov     rcx, rsi; this
0x180084bc8  call    ?_Add@CImageList@@QEAAJPEAUHBITMAP__@@0HHHPEAH@Z; CImageList::_Add(HBITMAP__ *,HBITMAP__ *,int,int,int,int *)
0x180084bcd  mov     ebx, [rsp+98h+var_48]
0x180084bd1  cmp     ebx, 0FFFFFFFFh
0x180084bd4  jz      loc_180084CA5
0x180084bda  lea     rcx, [rsi+10h]
0x180084bde  mov     edx, ebx
0x180084be0  mov     rax, [rcx]
0x180084be3  lea     r8, [rsp+98h+rc]
0x180084be8  mov     rax, [rax+78h]
0x180084bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bf1  test    eax, eax
0x180084bf3  js      loc_180084CA5
0x180084bf9  mov     r8, [rsi+60h]; hbr
0x180084bfd  lea     rdx, [rsp+98h+rc]; lprc
0x180084c02  mov     rcx, [rsi+78h]; hDC
0x180084c06  call    cs:__imp_FillRect
0x180084c0c  mov     r8d, [rsp+98h+rc.top]; yTop
0x180084c11  mov     r9, rdi; hIcon
0x180084c14  mov     edx, [rsp+98h+rc.left]; xLeft
0x180084c18  mov     rcx, [rsi+78h]; hdc
0x180084c1c  mov     [rsp+98h+diFlags], 3; diFlags
0x180084c24  mov     [rsp+98h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180084c2d  mov     [rsp+98h+istepIfAniCur], 0; istepIfAniCur
0x180084c35  mov     [rsp+98h+cyWidth], 0; cyWidth
0x180084c3d  mov     [rsp+98h+flags], 0; cxWidth
0x180084c45  call    cs:__imp_DrawIconEx
0x180084c4b  mov     rcx, [rsi+80h]; hdc
0x180084c52  test    rcx, rcx
0x180084c55  jz      short loc_180084C92
0x180084c57  mov     r8d, [rsp+98h+rc.top]; yTop
0x180084c5c  mov     r9, rdi; hIcon
0x180084c5f  mov     edx, [rsp+98h+rc.left]; xLeft
0x180084c63  mov     [rsp+98h+diFlags], 1; diFlags
0x180084c6b  mov     [rsp+98h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180084c74  mov     [rsp+98h+istepIfAniCur], 0; istepIfAniCur
0x180084c7c  mov     [rsp+98h+cyWidth], 0; cyWidth
0x180084c84  mov     [rsp+98h+flags], 0; cxWidth
0x180084c8c  call    cs:__imp_DrawIconEx
0x180084c92  cmp     rdi, rbp
0x180084c95  jz      short loc_180084CA0
0x180084c97  mov     rcx, rdi; hIcon
0x180084c9a  call    cs:__imp_DestroyIcon
0x180084ca0  mov     [r14], ebx
0x180084ca3  xor     eax, eax
0x180084ca5  mov     rcx, [rsp+98h+var_30]
0x180084caa  xor     rcx, rsp; StackCookie
0x180084cad  call    __security_check_cookie
0x180084cb2  add     rsp, 70h
0x180084cb6  pop     r14
0x180084cb8  pop     rdi
0x180084cb9  pop     rsi
0x180084cba  pop     rbp
0x180084cbb  pop     rbx
0x180084cbc  retn
```
