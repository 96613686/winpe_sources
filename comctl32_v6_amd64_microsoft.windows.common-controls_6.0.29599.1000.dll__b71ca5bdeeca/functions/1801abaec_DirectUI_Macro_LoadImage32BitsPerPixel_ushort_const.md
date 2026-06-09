# DirectUI::Macro::_LoadImage32BitsPerPixel(ushort const *)

- ea: `0x1801abaec`
- end: `0x1801abc18`
- name: `?_LoadImage32BitsPerPixel@Macro@DirectUI@@KAPEAVValue@2@PEBG@Z`
- size: `300`
- prototype: `struct DirectUI::Value *__fastcall(LPCWSTR name)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18010b6f4`

## callees

- `0x180164780`
- `0x1801aba48`
- `0x1801abaec`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801abc06`
- `GDI32!DeleteObject` at `0x1801abc06`
- `GDI32!GetObjectW` at `0x1801abb6a`
- `GDI32!GetObjectW` at `0x1801abb6a`
- `GDI32!SelectObject` at `0x1801abb49`
- `GDI32!SelectObject` at `0x1801abbaf`
- `GDI32!SelectObject` at `0x1801abb49`
- `GDI32!SelectObject` at `0x1801abbaf`
- `GDI32!DeleteDC` at `0x1801abbf3`
- `GDI32!DeleteDC` at `0x1801abbf3`
- `GDI32!CreateCompatibleDC` at `0x1801abafc`
- `GDI32!CreateCompatibleDC` at `0x1801abafc`
- `GDI32!GetDeviceCaps` at `0x1801abb14`
- `GDI32!GetDeviceCaps` at `0x1801abb14`
- `USER32!LoadImageW` at `0x1801abb3a`
- `USER32!LoadImageW` at `0x1801abbc3`
- `USER32!LoadImageW` at `0x1801abb3a`
- `USER32!LoadImageW` at `0x1801abbc3`

## pseudocode

```c
struct DirectUI::Value *__fastcall DirectUI::Macro::_LoadImage32BitsPerPixel(LPCWSTR name)
{
  struct DirectUI::Value *Graphic; // rbx
  HDC CompatibleDC; // rax
  HDC v4; // rsi
  HBITMAP ImageW; // rdi
  HGDIOBJ v6; // rbp
  int v7; // edx
  int v8; // r8d
  HBITMAP v9; // rax
  unsigned __int8 fuLoad; // [rsp+28h] [rbp-70h]
  unsigned __int8 v12; // [rsp+30h] [rbp-68h]
  unsigned __int8 v13; // [rsp+38h] [rbp-60h]
  unsigned __int8 v14; // [rsp+40h] [rbp-58h]
  unsigned int v15; // [rsp+48h] [rbp-50h]
  _OWORD pv[4]; // [rsp+50h] [rbp-48h] BYREF

  Graphic = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v4 = CompatibleDC;
  if ( CompatibleDC )
  {
    if ( GetDeviceCaps(CompatibleDC, 12) == 32 )
    {
      ImageW = (HBITMAP)LoadImageW(0, name, 0, 0, 0, 0x10u);
      memset(pv, 0, 32);
      v6 = SelectObject(v4, ImageW);
      if ( GetObjectW(ImageW, 32, pv) == 32 )
      {
        DirectUI::Macro::_BitAccurateFillRect(v4, v7, v8, SDWORD1(pv[0]), SDWORD2(pv[0]), fuLoad, v12, v13, v14, v15);
        Graphic = DirectUI::Value::CreateGraphic(ImageW, 1u, 0xFFu, 0, 0, 1);
      }
      SelectObject(v4, v6);
    }
    else
    {
      v9 = (HBITMAP)LoadImageW(0, name, 0, 0, 0, 0x2010u);
      ImageW = v9;
      if ( v9 )
        Graphic = DirectUI::Value::CreateGraphic(v9, 1u, 0xFEu, 0, 0, 1);
    }
    DeleteDC(v4);
    if ( !Graphic && ImageW )
      DeleteObject(ImageW);
  }
  return Graphic;
}

```

## disassembly

```asm
0x1801abaec  push    rbx
0x1801abaee  push    rbp
0x1801abaef  push    rsi
0x1801abaf0  push    rdi
0x1801abaf1  sub     rsp, 78h
0x1801abaf5  mov     rdi, rcx
0x1801abaf8  xor     ebx, ebx
0x1801abafa  xor     ecx, ecx; hdc
0x1801abafc  call    cs:__imp_CreateCompatibleDC
0x1801abb02  mov     rsi, rax
0x1801abb05  test    rax, rax
0x1801abb08  jz      loc_1801ABC0C
0x1801abb0e  lea     edx, [rbx+0Ch]; index
0x1801abb11  mov     rcx, rax; hdc
0x1801abb14  call    cs:__imp_GetDeviceCaps
0x1801abb1a  xor     r9d, r9d; cx
0x1801abb1d  xor     r8d, r8d; type
0x1801abb20  xor     ecx, ecx; hInst
0x1801abb22  mov     rdx, rdi; name
0x1801abb25  cmp     eax, 20h ; ' '
0x1801abb28  jnz     loc_1801ABBB7
0x1801abb2e  mov     dword ptr [rsp+98h+fuLoad], 10h; unsigned __int8
0x1801abb36  mov     [rsp+98h+cy], ebx; cy
0x1801abb3a  call    cs:__imp_LoadImageW
0x1801abb40  mov     rdx, rax; h
0x1801abb43  mov     rcx, rsi; hdc
0x1801abb46  mov     rdi, rax
0x1801abb49  call    cs:__imp_SelectObject
0x1801abb4f  xorps   xmm0, xmm0
0x1801abb52  lea     r8, [rsp+98h+pv]; pv
0x1801abb57  lea     edx, [rbx+20h]; c
0x1801abb5a  mov     rcx, rdi; h
0x1801abb5d  movups  [rsp+98h+pv], xmm0
0x1801abb62  mov     rbp, rax
0x1801abb65  movups  [rsp+98h+var_38], xmm0
0x1801abb6a  call    cs:__imp_GetObjectW
0x1801abb70  cmp     eax, 20h ; ' '
0x1801abb73  jnz     short loc_1801ABBA9
0x1801abb75  mov     eax, dword ptr [rsp+98h+pv+8]
0x1801abb79  mov     rcx, rsi; HDC
0x1801abb7c  mov     r9d, dword ptr [rsp+98h+pv+4]; int
0x1801abb81  mov     [rsp+98h+cy], eax; int
0x1801abb85  call    ?_BitAccurateFillRect@Macro@DirectUI@@KAXPEAUHDC__@@HHHHEEEEK@Z; DirectUI::Macro::_BitAccurateFillRect(HDC__ *,int,int,int,int,uchar,uchar,uchar,uchar,ulong)
0x1801abb8a  xor     r9d, r9d; bool
0x1801abb8d  mov     [rsp+98h+fuLoad], 1; bool
0x1801abb92  mov     r8d, 0FFh; unsigned int
0x1801abb98  mov     byte ptr [rsp+98h+cy], bl; bool
0x1801abb9c  mov     dl, 1; unsigned __int8
0x1801abb9e  mov     rcx, rdi; hbm
0x1801abba1  call    ?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1801abba6  mov     rbx, rax
0x1801abba9  mov     rdx, rbp; h
0x1801abbac  mov     rcx, rsi; hdc
0x1801abbaf  call    cs:__imp_SelectObject
0x1801abbb5  jmp     short loc_1801ABBF0
0x1801abbb7  mov     dword ptr [rsp+98h+fuLoad], 2010h; fuLoad
0x1801abbbf  mov     [rsp+98h+cy], ebx; cy
0x1801abbc3  call    cs:__imp_LoadImageW
0x1801abbc9  mov     rdi, rax
0x1801abbcc  test    rax, rax
0x1801abbcf  jz      short loc_1801ABBF0
0x1801abbd1  mov     [rsp+98h+fuLoad], 1; bool
0x1801abbd6  xor     r9d, r9d; bool
0x1801abbd9  mov     r8d, 0FEh; unsigned int
0x1801abbdf  mov     byte ptr [rsp+98h+cy], bl; bool
0x1801abbe3  mov     dl, 1; unsigned __int8
0x1801abbe5  mov     rcx, rax; hbm
0x1801abbe8  call    ?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1801abbed  mov     rbx, rax
0x1801abbf0  mov     rcx, rsi; hdc
0x1801abbf3  call    cs:__imp_DeleteDC
0x1801abbf9  test    rbx, rbx
0x1801abbfc  jnz     short loc_1801ABC0C
0x1801abbfe  test    rdi, rdi
0x1801abc01  jz      short loc_1801ABC0C
0x1801abc03  mov     rcx, rdi; ho
0x1801abc06  call    cs:__imp_DeleteObject
0x1801abc0c  mov     rax, rbx
0x1801abc0f  add     rsp, 78h
0x1801abc13  pop     rdi
0x1801abc14  pop     rsi
0x1801abc15  pop     rbp
0x1801abc16  pop     rbx
0x1801abc17  retn
```
