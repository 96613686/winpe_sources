# CCommunityRatings::AddMVPImage(HDC__ *,int *,int)

- ea: `0x180082198`
- end: `0x180082328`
- name: `?AddMVPImage@CCommunityRatings@@QEAAJPEAUHDC__@@PEAHH@Z`
- size: `400`
- prototype: `int(CCommunityRatings *__hidden this, HDC, int *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006d958`
- `0x18007b108`

## callees

- `0x1800247c8`
- `0x180082198`
- `0x1800cca00`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18008221d`
- `GDI32!CreateCompatibleDC` at `0x18008221d`
- `GDI32!SelectObject` at `0x180082235`
- `GDI32!SelectObject` at `0x180082235`
- `GDI32!DeleteDC` at `0x1800822d7`
- `GDI32!DeleteDC` at `0x1800822d7`
- `GDI32!GetDIBits` at `0x180082280`
- `GDI32!GetDIBits` at `0x180082280`
- `GDI32!DeleteObject` at `0x1800822e9`
- `GDI32!DeleteObject` at `0x1800822e9`
- `USER32!LoadImageA` at `0x180082208`
- `USER32!LoadImageA` at `0x180082208`
- `MSIMG32!TransparentBlt` at `0x1800822bf`
- `MSIMG32!TransparentBlt` at `0x1800822bf`

## pseudocode

```c
__int64 __fastcall CCommunityRatings::AddMVPImage(CCommunityRatings *this, HDC a2, int *a3, int a4)
{
  HBITMAP ImageA; // rbp
  HDC CompatibleDC; // rax
  HDC v10; // rdi
  unsigned int LastError; // ebx
  struct tagBITMAPINFO bmi; // [rsp+60h] [rbp-68h] BYREF

  if ( !a2 || !a3 )
    return 2147942487LL;
  if ( !g_hLocRes )
    return 2147549183LL;
  ImageA = (HBITMAP)LoadImageA(g_hLocRes, (LPCSTR)6, 0, 0, 0, 0x40u);
  if ( ImageA )
  {
    CompatibleDC = CreateCompatibleDC(a2);
    v10 = CompatibleDC;
    if ( CompatibleDC )
    {
      SelectObject(CompatibleDC, ImageA);
      bmi.bmiHeader.biSize = 40;
      memset(&bmi.bmiHeader.biWidth, 0, 40);
      if ( GetDIBits(v10, ImageA, 0, 1u, 0, &bmi, 0) )
      {
        LastError = 0;
        TransparentBlt(
          a2,
          *a3,
          a4,
          bmi.bmiHeader.biWidth,
          bmi.bmiHeader.biHeight,
          v10,
          0,
          0,
          bmi.bmiHeader.biWidth,
          bmi.bmiHeader.biHeight,
          0xFF00FFu);
        *a3 += bmi.bmiHeader.biWidth;
      }
      else
      {
        LastError = HrGetLastError();
      }
      DeleteDC(v10);
    }
    else
    {
      LastError = HrGetLastError();
    }
    DeleteObject(ImageA);
  }
  else
  {
    return (unsigned int)HrGetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x180082198  mov     [rsp+arg_0], rbx
0x18008219d  push    rbp
0x18008219e  push    rsi
0x18008219f  push    rdi
0x1800821a0  push    r14
0x1800821a2  push    r15
0x1800821a4  sub     rsp, 0A0h
0x1800821ab  mov     rax, cs:__security_cookie
0x1800821b2  xor     rax, rsp
0x1800821b5  mov     [rsp+0C8h+var_38], rax
0x1800821bd  mov     r15d, r9d
0x1800821c0  mov     rsi, r8
0x1800821c3  mov     r14, rdx
0x1800821c6  test    rdx, rdx
0x1800821c9  jz      loc_1800822FC
0x1800821cf  test    r8, r8
0x1800821d2  jz      loc_1800822FC
0x1800821d8  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInst
0x1800821df  test    rcx, rcx
0x1800821e2  jnz     short loc_1800821EE
0x1800821e4  mov     eax, 8000FFFFh
0x1800821e9  jmp     loc_180082301
0x1800821ee  xor     r9d, r9d; cx
0x1800821f1  mov     [rsp+0C8h+fuLoad], 40h ; '@'; fuLoad
0x1800821f9  xor     r8d, r8d; type
0x1800821fc  mov     [rsp+0C8h+cy], 0; cy
0x180082204  lea     edx, [r9+6]; name
0x180082208  call    cs:__imp_LoadImageA
0x18008220e  mov     rbp, rax
0x180082211  test    rax, rax
0x180082214  jz      loc_1800822F1
0x18008221a  mov     rcx, r14; hdc
0x18008221d  call    cs:__imp_CreateCompatibleDC
0x180082223  mov     rdi, rax
0x180082226  test    rax, rax
0x180082229  jz      loc_1800822DF
0x18008222f  mov     rdx, rbp; h
0x180082232  mov     rcx, rax; hdc
0x180082235  call    cs:__imp_SelectObject
0x18008223b  xor     eax, eax
0x18008223d  mov     [rsp+0C8h+bmi.bmiHeader.biSize], 28h ; '('
0x180082245  mov     [rsp+0C8h+usage], eax; usage
0x180082249  xorps   xmm0, xmm0
0x18008224c  mov     qword ptr [rsp+0C8h+bmi.bmiHeader.biClrImportant], rax
0x180082254  mov     r9d, 1; cLines
0x18008225a  lea     rax, [rsp+0C8h+bmi]
0x18008225f  xor     r8d, r8d; start
0x180082262  mov     qword ptr [rsp+0C8h+fuLoad], rax; lpbmi
0x180082267  mov     rdx, rbp; hbm
0x18008226a  mov     rcx, rdi; hdc
0x18008226d  mov     qword ptr [rsp+0C8h+cy], 0; lpvBits
0x180082276  movups  xmmword ptr [rsp+0C8h+bmi.bmiHeader.biWidth], xmm0
0x18008227b  movups  xmmword ptr [rsp+0C8h+bmi.bmiHeader.biSizeImage], xmm0
0x180082280  call    cs:__imp_GetDIBits
0x180082286  test    eax, eax
0x180082288  jz      short loc_1800822CD
0x18008228a  mov     eax, [rsp+0C8h+bmi.bmiHeader.biHeight]
0x18008228e  xor     ebx, ebx
0x180082290  mov     r9d, [rsp+0C8h+bmi.bmiHeader.biWidth]; wDest
0x180082295  mov     r8d, r15d; yoriginDest
0x180082298  mov     edx, [rsi]; xoriginDest
0x18008229a  mov     rcx, r14; hdcDest
0x18008229d  mov     [rsp+0C8h+crTransparent], 0FF00FFh; crTransparent
0x1800822a5  mov     [rsp+0C8h+hSrc], eax; hSrc
0x1800822a9  mov     [rsp+0C8h+wSrc], r9d; wSrc
0x1800822ae  mov     [rsp+0C8h+yoriginSrc], ebx; yoriginSrc
0x1800822b2  mov     [rsp+0C8h+usage], ebx; xoriginSrc
0x1800822b6  mov     qword ptr [rsp+0C8h+fuLoad], rdi; hdcSrc
0x1800822bb  mov     [rsp+0C8h+cy], eax; hDest
0x1800822bf  call    cs:__imp_TransparentBlt
0x1800822c5  mov     eax, [rsp+0C8h+bmi.bmiHeader.biWidth]
0x1800822c9  add     [rsi], eax
0x1800822cb  jmp     short loc_1800822D4
0x1800822cd  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800822d2  mov     ebx, eax
0x1800822d4  mov     rcx, rdi; hdc
0x1800822d7  call    cs:__imp_DeleteDC
0x1800822dd  jmp     short loc_1800822E6
0x1800822df  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800822e4  mov     ebx, eax
0x1800822e6  mov     rcx, rbp; ho
0x1800822e9  call    cs:__imp_DeleteObject
0x1800822ef  jmp     short loc_1800822F8
0x1800822f1  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800822f6  mov     ebx, eax
0x1800822f8  mov     eax, ebx
0x1800822fa  jmp     short loc_180082301
0x1800822fc  mov     eax, 80070057h
0x180082301  mov     rcx, [rsp+0C8h+var_38]
0x180082309  xor     rcx, rsp; StackCookie
0x18008230c  call    __security_check_cookie
0x180082311  mov     rbx, [rsp+0C8h+arg_0]
0x180082319  add     rsp, 0A0h
0x180082320  pop     r15
0x180082322  pop     r14
0x180082324  pop     rdi
0x180082325  pop     rsi
0x180082326  pop     rbp
0x180082327  retn
```
