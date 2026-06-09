# CImage::Draw(HDC__ *,int,tagRECT const *)

- ea: `0x1801e7e70`
- end: `0x1801e80a7`
- name: `?Draw@CImage@@UEAAJPEAUHDC__@@HPEBUtagRECT@@@Z`
- size: `567`
- prototype: `int(CImage *__hidden this, HDC, int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000f430`
- `0x1801e7e70`
- `0x1801e9924`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e8084`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801e8084`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e7eb7`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801e7eb7`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801e7f25`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1801e7f25`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e7ed9`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e8075`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e7ed9`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801e8075`
- `ext-ms-win-gdi-draw-l1-1-1!GdiAlphaBlend` at `0x1801e8015`
- `ext-ms-win-gdi-draw-l1-1-1!GdiAlphaBlend` at `0x1801e8015`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801e805c`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1801e805c`

## pseudocode

```c
__int64 __fastcall CImage::Draw(CImage *this, HDC a2, int a3, const struct tagRECT *a4)
{
  unsigned int v8; // edi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  HGDIOBJ v11; // r15
  void *v12; // rcx
  LONG left; // eax
  LONG top; // r13d
  int v15; // eax
  int v16; // eax
  int yoriginSrc; // eax
  float v18; // xmm1_4
  BLENDFUNCTION ftn; // [rsp+60h] [rbp-78h]
  int x1; // [rsp+64h] [rbp-74h]
  int xoriginDest; // [rsp+68h] [rbp-70h]
  _OWORD pv[6]; // [rsp+70h] [rbp-68h] BYREF

  v8 = CImage::CheckGdiBitmap(this, a2, a4);
  if ( !v8 )
  {
    if ( *((_QWORD *)this + 16) )
    {
      v8 = -2147467259;
      CompatibleDC = CreateCompatibleDC(0);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        v11 = SelectObject(CompatibleDC, *((HGDIOBJ *)this + 16));
        if ( v11 )
        {
          v12 = (void *)*((_QWORD *)this + 16);
          memset(pv, 0, 32);
          if ( GetObjectW(v12, 32, pv) == 32 )
          {
            left = a4->left;
            top = a4->top;
            xoriginDest = left;
            v15 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 104LL))(this);
            x1 = CW32System::MulDivFunc(*((_DWORD *)this + 44), v15, 2540);
            v16 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 112LL))(this);
            yoriginSrc = CW32System::MulDivFunc(*((_DWORD *)this + 45), v16, 2540);
            v18 = *((float *)this + 51);
            if ( (v18 >= 1.0 || a3) && !*((_BYTE *)this + 211) )
            {
              if ( BitBlt(
                     a2,
                     xoriginDest,
                     top,
                     *((_DWORD *)this + 48),
                     *((_DWORD *)this + 49),
                     hdcSrc,
                     x1,
                     yoriginSrc,
                     a3 != 0 ? 3342344 : 13369376) )
              {
                v8 = 0;
              }
            }
            else
            {
              ftn.AlphaFormat = *((_BYTE *)this + 211) != 0;
              *(_WORD *)&ftn.BlendOp = 0;
              ftn.SourceConstantAlpha = (int)(float)(v18 * 255.0);
              v8 = !GdiAlphaBlend(
                      a2,
                      xoriginDest,
                      top,
                      *((_DWORD *)this + 48),
                      *((_DWORD *)this + 49),
                      hdcSrc,
                      x1,
                      yoriginSrc,
                      *((_DWORD *)this + 48),
                      *((_DWORD *)this + 49),
                      ftn)
                 ? 0x80004005
                 : 0;
            }
            SelectObject(hdcSrc, v11);
          }
        }
        DeleteDC(hdcSrc);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1801e7e70  push    rbx
0x1801e7e72  push    rbp
0x1801e7e73  push    rsi
0x1801e7e74  push    rdi
0x1801e7e75  push    r12
0x1801e7e77  push    r13
0x1801e7e79  push    r14
0x1801e7e7b  push    r15
0x1801e7e7d  sub     rsp, 98h
0x1801e7e84  mov     r12d, r8d
0x1801e7e87  mov     r13, r9
0x1801e7e8a  mov     r8, r9; struct tagRECT *
0x1801e7e8d  mov     r14, rdx
0x1801e7e90  mov     rbx, rcx
0x1801e7e93  call    ?CheckGdiBitmap@CImage@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z; CImage::CheckGdiBitmap(HDC__ *,tagRECT const *)
0x1801e7e98  mov     edi, eax
0x1801e7e9a  test    eax, eax
0x1801e7e9c  jnz     loc_1801E8090
0x1801e7ea2  cmp     qword ptr [rbx+80h], 0
0x1801e7eaa  jz      loc_1801E8090
0x1801e7eb0  xor     ecx, ecx; hdc
0x1801e7eb2  mov     edi, 80004005h
0x1801e7eb7  call    cs:__imp_CreateCompatibleDC
0x1801e7ebe  nop     dword ptr [rax+rax+00h]
0x1801e7ec3  mov     rsi, rax
0x1801e7ec6  test    rax, rax
0x1801e7ec9  jz      loc_1801E8090
0x1801e7ecf  mov     rdx, [rbx+80h]; h
0x1801e7ed6  mov     rcx, rax; hdc
0x1801e7ed9  call    cs:__imp_SelectObject
0x1801e7ee0  nop     dword ptr [rax+rax+00h]
0x1801e7ee5  mov     r15, rax
0x1801e7ee8  test    rax, rax
0x1801e7eeb  jz      loc_1801E8081
0x1801e7ef1  xorps   xmm0, xmm0
0x1801e7ef4  lea     r8, [rsp+0D8h+pv]; pv
0x1801e7ef9  mov     ecx, r12d
0x1801e7efc  mov     edx, 20h ; ' '; c
0x1801e7f01  neg     ecx
0x1801e7f03  mov     rcx, [rbx+80h]; h
0x1801e7f0a  sbb     ebp, ebp
0x1801e7f0c  and     ebp, 0FF66FFE8h
0x1801e7f12  add     ebp, 0CC0020h
0x1801e7f18  movups  [rsp+0D8h+pv], xmm0
0x1801e7f1d  movups  [rsp+0D8h+var_58], xmm0
0x1801e7f25  call    cs:__imp_GetObjectW
0x1801e7f2c  nop     dword ptr [rax+rax+00h]
0x1801e7f31  cmp     eax, 20h ; ' '
0x1801e7f34  jnz     loc_1801E8081
0x1801e7f3a  mov     eax, [r13+0]
0x1801e7f3e  mov     rcx, rbx
0x1801e7f41  mov     r13d, [r13+4]
0x1801e7f45  mov     [rsp+0D8h+xoriginDest], eax
0x1801e7f49  mov     rax, [rbx]
0x1801e7f4c  mov     rax, [rax+68h]
0x1801e7f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7f55  mov     ecx, [rbx+0B0h]; int
0x1801e7f5b  mov     r8d, 9ECh; int
0x1801e7f61  mov     edx, eax; int
0x1801e7f63  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x1801e7f68  mov     rcx, [rbx]
0x1801e7f6b  mov     [rsp+0D8h+x1], eax
0x1801e7f6f  mov     rax, [rcx+70h]
0x1801e7f73  mov     rcx, rbx
0x1801e7f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e7f7b  mov     ecx, [rbx+0B4h]; int
0x1801e7f81  mov     r8d, 9ECh; int
0x1801e7f87  mov     edx, eax; int
0x1801e7f89  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x1801e7f8e  movss   xmm1, dword ptr [rbx+0CCh]
0x1801e7f96  mov     r11d, eax
0x1801e7f99  movss   xmm0, cs:__real@3f800000
0x1801e7fa1  comiss  xmm0, xmm1
0x1801e7fa4  jbe     short loc_1801E7FAB
0x1801e7fa6  test    r12d, r12d
0x1801e7fa9  jz      short loc_1801E7FB4
0x1801e7fab  cmp     byte ptr [rbx+0D3h], 0
0x1801e7fb2  jz      short loc_1801E802B
0x1801e7fb4  mov     ecx, [rbx+0C4h]
0x1801e7fba  mov     r8d, r13d; yoriginDest
0x1801e7fbd  mulss   xmm1, cs:__real@437f0000
0x1801e7fc5  cmp     byte ptr [rbx+0D3h], 0
0x1801e7fcc  mov     r9d, [rbx+0C0h]; wDest
0x1801e7fd3  mov     edx, [rsp+0D8h+xoriginDest]; xoriginDest
0x1801e7fd7  setnz   [rsp+0D8h+var_78.AlphaFormat]
0x1801e7fdc  cvttss2si eax, xmm1
0x1801e7fe0  mov     word ptr [rsp+0D8h+var_78.BlendOp], 0
0x1801e7fe7  mov     [rsp+0D8h+var_78.SourceConstantAlpha], al
0x1801e7feb  mov     eax, dword ptr [rsp+0D8h+var_78.BlendOp]
0x1801e7fef  mov     dword ptr [rsp+0D8h+ftn.BlendOp], eax; ftn
0x1801e7ff3  mov     eax, [rsp+0D8h+x1]
0x1801e7ff7  mov     [rsp+0D8h+hSrc], ecx; hSrc
0x1801e7ffb  mov     [rsp+0D8h+wSrc], r9d; wSrc
0x1801e8000  mov     [rsp+0D8h+yoriginSrc], r11d; yoriginSrc
0x1801e8005  mov     [rsp+0D8h+xoriginSrc], eax; xoriginSrc
0x1801e8009  mov     [rsp+0D8h+hdcSrc], rsi; hdcSrc
0x1801e800e  mov     [rsp+0D8h+hDest], ecx; hDest
0x1801e8012  mov     rcx, r14; hdcDest
0x1801e8015  call    cs:__imp_GdiAlphaBlend
0x1801e801c  nop     dword ptr [rax+rax+00h]
0x1801e8021  neg     eax
0x1801e8023  sbb     ecx, ecx
0x1801e8025  not     ecx
0x1801e8027  and     edi, ecx
0x1801e8029  jmp     short loc_1801E806F
0x1801e802b  mov     eax, [rsp+0D8h+x1]
0x1801e802f  mov     r8d, r13d; y
0x1801e8032  mov     r9d, [rbx+0C0h]; cx
0x1801e8039  mov     rcx, r14; hdc
0x1801e803c  mov     edx, [rsp+0D8h+xoriginDest]; x
0x1801e8040  mov     [rsp+0D8h+wSrc], ebp; rop
0x1801e8044  mov     [rsp+0D8h+yoriginSrc], r11d; y1
0x1801e8049  mov     [rsp+0D8h+xoriginSrc], eax; x1
0x1801e804d  mov     eax, [rbx+0C4h]
0x1801e8053  mov     [rsp+0D8h+hdcSrc], rsi; hdcSrc
0x1801e8058  mov     [rsp+0D8h+hDest], eax; cy
0x1801e805c  call    cs:__imp_BitBlt
0x1801e8063  nop     dword ptr [rax+rax+00h]
0x1801e8068  xor     ecx, ecx
0x1801e806a  test    eax, eax
0x1801e806c  cmovnz  edi, ecx
0x1801e806f  mov     rdx, r15; h
0x1801e8072  mov     rcx, rsi; hdc
0x1801e8075  call    cs:__imp_SelectObject
0x1801e807c  nop     dword ptr [rax+rax+00h]
0x1801e8081  mov     rcx, rsi; hdc
0x1801e8084  call    cs:__imp_DeleteDC
0x1801e808b  nop     dword ptr [rax+rax+00h]
0x1801e8090  mov     eax, edi
0x1801e8092  add     rsp, 98h
0x1801e8099  pop     r15
0x1801e809b  pop     r14
0x1801e809d  pop     r13
0x1801e809f  pop     r12
0x1801e80a1  pop     rdi
0x1801e80a2  pop     rsi
0x1801e80a3  pop     rbp
0x1801e80a4  pop     rbx
0x1801e80a5  retn
```
