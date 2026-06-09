# CuipAlphaBlend(HDC__ *,int,ulong,ulong)

- ea: `0x140006fd0`
- end: `0x14000723f`
- name: `?CuipAlphaBlend@@YAXPEAUHDC__@@HKK@Z`
- size: `623`
- prototype: `void __fastcall(HDC hdcDest)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140006d00`

## callees

- `0x140006fd0`
- `0x14000fbec`
- `0x14001ba28`
- `0x14001e050`

## import_xrefs

- `GDI32!SelectObject` at `0x14000713b`
- `GDI32!SelectObject` at `0x14000713b`
- `GDI32!DeleteDC` at `0x14000720a`
- `GDI32!DeleteDC` at `0x14000720a`
- `GDI32!CreateDIBSection` at `0x1400070dc`
- `GDI32!CreateDIBSection` at `0x1400070dc`
- `GDI32!DeleteObject` at `0x140007201`
- `GDI32!DeleteObject` at `0x140007201`
- `GDI32!CreateCompatibleDC` at `0x14000701c`
- `GDI32!CreateCompatibleDC` at `0x14000701c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000704b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000710b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000704b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000710b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007167`
- `MSIMG32!AlphaBlend` at `0x1400071c6`
- `MSIMG32!AlphaBlend` at `0x1400071c6`

## pseudocode

```c
void __fastcall CuipAlphaBlend(HDC hdcDest)
{
  int v1; // ebp
  int v2; // r14d
  HDC CompatibleDC; // rax
  HDC v5; // rbx
  DWORD v6; // eax
  HBITMAP v7; // rax
  HBITMAP v8; // rdi
  DWORD v9; // eax
  DWORD LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  void *ppvBits; // [rsp+68h] [rbp-70h] BYREF
  BITMAPINFO pbmi; // [rsp+70h] [rbp-68h] BYREF

  v1 = nHeight;
  v2 = nWidth;
  memset(&pbmi, 0, sizeof(pbmi));
  ppvBits = 0;
  CompatibleDC = CreateCompatibleDC(hdcDest);
  v5 = CompatibleDC;
  if ( CompatibleDC )
  {
    pbmi.bmiHeader.biWidth = 1;
    pbmi.bmiHeader.biHeight = 1;
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    v7 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      if ( SelectObject(v5, v7) )
      {
        if ( AlphaBlend(hdcDest, 0, 0, v2, v1, v5, 0, 0, 1, 1, (BLENDFUNCTION)11468800)
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          WPP_SF_Dlld(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v11, v12, (unsigned int)hdcDest, v2, v1);
        }
      }
      else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
      }
      DeleteObject(v8);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v9);
    }
    DeleteDC(v5);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v6 = GetLastError();
    WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v6);
  }
}

```

## disassembly

```asm
0x140006fd0  mov     r11, rsp
0x140006fd3  push    rbx
0x140006fd4  push    rbp
0x140006fd5  push    rsi
0x140006fd6  push    r14
0x140006fd8  push    r15
0x140006fda  sub     rsp, 0B0h
0x140006fe1  mov     rax, cs:__security_cookie
0x140006fe8  xor     rax, rsp
0x140006feb  mov     [rsp+0D8h+var_38], rax
0x140006ff3  mov     ebp, cs:nHeight
0x140006ff9  xorps   xmm0, xmm0
0x140006ffc  mov     r14d, cs:nWidth
0x140007003  xor     r15d, r15d
0x140007006  movups  xmmword ptr [rsp+0D8h+pbmi.bmiHeader.biSize], xmm0
0x14000700b  mov     rsi, rcx
0x14000700e  mov     [r11-70h], r15
0x140007012  movups  xmmword ptr [r11-58h], xmm0
0x140007017  movups  xmmword ptr [r11-4Ch], xmm0
0x14000701c  call    cs:__imp_CreateCompatibleDC
0x140007022  mov     rbx, rax
0x140007025  test    rax, rax
0x140007028  jnz     short loc_140007075
0x14000702a  mov     rcx, cs:WPP_GLOBAL_Control
0x140007031  lea     rax, WPP_GLOBAL_Control
0x140007038  cmp     rcx, rax
0x14000703b  jz      loc_140007220
0x140007041  test    byte ptr [rcx+1Ch], 4
0x140007045  jz      loc_140007220
0x14000704b  call    cs:__imp_GetLastError
0x140007051  mov     rcx, cs:WPP_GLOBAL_Control
0x140007058  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000705f  mov     edx, 19h
0x140007064  mov     r9d, eax
0x140007067  mov     rcx, [rcx+10h]
0x14000706b  call    WPP_SF_D
0x140007070  jmp     loc_140007220
0x140007075  xorps   xmm0, xmm0
0x140007078  mov     [rsp+0D8h+arg_8], rdi
0x140007080  mov     [rsp+0D8h+arg_10], r12
0x140007088  lea     r9, [rsp+0D8h+ppvBits]; ppvBits
0x14000708d  mov     r12d, 1
0x140007093  mov     [rsp+0D8h+offset], r15d; offset
0x140007098  xor     r8d, r8d; usage
0x14000709b  mov     [rsp+0D8h+pbmi.bmiHeader.biWidth], r12d
0x1400070a0  lea     rdx, [rsp+0D8h+pbmi]; pbmi
0x1400070a5  mov     [rsp+0D8h+pbmi.bmiHeader.biHeight], r12d
0x1400070aa  mov     rcx, rbx; hdc
0x1400070ad  mov     dword ptr [rsp+0D8h+pbmi.bmiColors.rgbBlue], r15d
0x1400070b5  movdqu  xmmword ptr [rsp+0D8h+pbmi.bmiHeader.biXPelsPerMeter], xmm0
0x1400070be  mov     [rsp+0D8h+pbmi.bmiHeader.biSize], 28h ; '('
0x1400070c6  mov     qword ptr [rsp+0D8h+pbmi.bmiHeader.biPlanes], 200001h
0x1400070cf  mov     [rsp+0D8h+pbmi.bmiHeader.biSizeImage], r15d
0x1400070d7  mov     [rsp+0D8h+hSection], r15; hSection
0x1400070dc  call    cs:__imp_CreateDIBSection
0x1400070e2  mov     rdi, rax
0x1400070e5  test    rax, rax
0x1400070e8  jnz     short loc_140007135
0x1400070ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400070f1  lea     rax, WPP_GLOBAL_Control
0x1400070f8  cmp     rcx, rax
0x1400070fb  jz      loc_140007207
0x140007101  test    byte ptr [rcx+1Ch], 4
0x140007105  jz      loc_140007207
0x14000710b  call    cs:__imp_GetLastError
0x140007111  mov     rcx, cs:WPP_GLOBAL_Control
0x140007118  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000711f  mov     edx, 1Ah
0x140007124  mov     r9d, eax
0x140007127  mov     rcx, [rcx+10h]
0x14000712b  call    WPP_SF_D
0x140007130  jmp     loc_140007207
0x140007135  mov     rdx, rdi; h
0x140007138  mov     rcx, rbx; hdc
0x14000713b  call    cs:__imp_SelectObject
0x140007141  test    rax, rax
0x140007144  jnz     short loc_14000718E
0x140007146  mov     rcx, cs:WPP_GLOBAL_Control
0x14000714d  lea     rax, WPP_GLOBAL_Control
0x140007154  cmp     rcx, rax
0x140007157  jz      loc_1400071FE
0x14000715d  test    byte ptr [rcx+1Ch], 4
0x140007161  jz      loc_1400071FE
0x140007167  call    cs:__imp_GetLastError
0x14000716d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007174  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x14000717b  mov     edx, 1Bh
0x140007180  mov     r9d, eax
0x140007183  mov     rcx, [rcx+10h]
0x140007187  call    WPP_SF_D
0x14000718c  jmp     short loc_1400071FE
0x14000718e  mov     dword ptr [rsp+0D8h+var_78.BlendOp], 0AF0000h
0x140007196  mov     r9d, r14d; wDest
0x140007199  mov     eax, dword ptr [rsp+0D8h+var_78.BlendOp]
0x14000719d  xor     r8d, r8d; yoriginDest
0x1400071a0  mov     dword ptr [rsp+0D8h+ftn.BlendOp], eax; ftn
0x1400071a4  xor     edx, edx; xoriginDest
0x1400071a6  mov     [rsp+0D8h+hSrc], r12d; hSrc
0x1400071ab  mov     rcx, rsi; hdcDest
0x1400071ae  mov     [rsp+0D8h+wSrc], r12d; wSrc
0x1400071b3  mov     [rsp+0D8h+yoriginSrc], r15d; yoriginSrc
0x1400071b8  mov     [rsp+0D8h+xoriginSrc], r15d; xoriginSrc
0x1400071bd  mov     qword ptr [rsp+0D8h+offset], rbx; hdcSrc
0x1400071c2  mov     dword ptr [rsp+0D8h+hSection], ebp; hDest
0x1400071c6  call    cs:__imp_AlphaBlend
0x1400071cc  test    eax, eax
0x1400071ce  jz      short loc_1400071FE
0x1400071d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400071d7  lea     rax, WPP_GLOBAL_Control
0x1400071de  cmp     rcx, rax
0x1400071e1  jz      short loc_1400071FE
0x1400071e3  test    byte ptr [rcx+1Ch], 4
0x1400071e7  jz      short loc_1400071FE
0x1400071e9  mov     rcx, [rcx+10h]
0x1400071ed  mov     r9d, esi
0x1400071f0  mov     [rsp+0D8h+offset], ebp
0x1400071f4  mov     dword ptr [rsp+0D8h+hSection], r14d
0x1400071f9  call    WPP_SF_Dlld
0x1400071fe  mov     rcx, rdi; ho
0x140007201  call    cs:__imp_DeleteObject
0x140007207  mov     rcx, rbx; hdc
0x14000720a  call    cs:__imp_DeleteDC
0x140007210  mov     r12, [rsp+0D8h+arg_10]
0x140007218  mov     rdi, [rsp+0D8h+arg_8]
0x140007220  mov     rcx, [rsp+0D8h+var_38]
0x140007228  xor     rcx, rsp; StackCookie
0x14000722b  call    __security_check_cookie
0x140007230  add     rsp, 0B0h
0x140007237  pop     r15
0x140007239  pop     r14
0x14000723b  pop     rsi
0x14000723c  pop     rbp
0x14000723d  pop     rbx
0x14000723e  retn
```
