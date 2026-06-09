# EpPaletteMap::UpdateTranslate(HDC__ *,ColorPalette * *)

- ea: `0x180125e98`
- end: `0x180126128`
- name: `?UpdateTranslate@EpPaletteMap@@QEAAXPEAUHDC__@@PEAPEAUColorPalette@@@Z`
- size: `656`
- prototype: `void(EpPaletteMap *__hidden this, HDC, struct ColorPalette **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180018720`
- `0x180125acc`

## callees

- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180125e98`

## import_xrefs

- `GDI32!GetNearestPaletteIndex` at `0x180126081`
- `GDI32!GetNearestPaletteIndex` at `0x180126081`
- `GDI32!GetNearestColor` at `0x18012606a`
- `GDI32!GetNearestColor` at `0x18012606a`
- `GDI32!DeleteObject` at `0x1801260f1`
- `GDI32!DeleteObject` at `0x1801260f1`
- `GDI32!GetDeviceCaps` at `0x180125f00`
- `GDI32!GetDeviceCaps` at `0x180125f16`
- `GDI32!GetDeviceCaps` at `0x180125f00`
- `GDI32!GetDeviceCaps` at `0x180125f16`
- `GDI32!GetSystemPaletteEntries` at `0x180125f53`
- `GDI32!GetSystemPaletteEntries` at `0x180125f53`
- `GDI32!CreatePalette` at `0x180125f64`
- `GDI32!CreatePalette` at `0x180125f64`

## pseudocode

```c
void __fastcall EpPaletteMap::UpdateTranslate(EpPaletteMap *this, HDC a2, struct ColorPalette **a3)
{
  char DeviceCaps; // bl
  int v7; // ebx
  __int64 v8; // rax
  int v9; // r11d
  BYTE *p_peGreen; // r9
  int v11; // r12d
  char *v12; // r15
  __int64 v13; // r14
  int *i; // rsi
  COLORREF v15; // edi
  COLORREF NearestColor; // eax
  UINT NearestPaletteIndex; // eax
  HPALETTE h; // [rsp+20h] [rbp-E0h]
  LOGPALETTE plpal; // [rsp+30h] [rbp-D0h] BYREF

  *(_DWORD *)this = 1279869254;
  memset_0(plpal.palPalEntry, 0, 0x404u);
  plpal.palVersion = 768;
  DeviceCaps = GetDeviceCaps(a2, 14);
  plpal.palNumEntries = 1 << (GetDeviceCaps(a2, 12) * DeviceCaps);
  if ( plpal.palNumEntries > 0x100u )
    plpal.palNumEntries = 256;
  GetSystemPaletteEntries(a2, 0, 0x100u, plpal.palPalEntry);
  v7 = 0;
  h = CreatePalette(&plpal);
  if ( h )
  {
    if ( a3 )
    {
      v8 = (__int64)*a3;
      if ( !*a3 )
      {
        v8 = GpMallocEx(1036, 0);
        *a3 = (struct ColorPalette *)v8;
        if ( !v8 )
        {
LABEL_21:
          DeleteObject(h);
          return;
        }
      }
      v9 = 0;
      *(_DWORD *)(v8 + 4) = plpal.palNumEntries;
      if ( plpal.palNumEntries )
      {
        p_peGreen = &plpal.palPalEntry[0].peGreen;
        do
        {
          ++v9;
          *(_DWORD *)&p_peGreen[(_QWORD)*a3 + 8LL - (_QWORD)&plpal.palPalEntry[0].peGreen] = p_peGreen[1]
                                                                                           | ((*p_peGreen
                                                                                             | ((*(p_peGreen - 1)
                                                                                               | 0xFFFFFF00) << 8)) << 8);
          p_peGreen += 4;
        }
        while ( v9 < plpal.palNumEntries );
      }
    }
    memset_0((char *)this + 8, 0, 0x100u);
    v11 = 0;
    v12 = &byte_18018BAF5;
    v13 = 0;
    for ( i = &dword_1801B34D0; (__int64)i < (__int64)&qword_1801B38D0; ++i )
    {
      if ( (unsigned __int64)(v13 - 8) > 3 )
        v15 = (unsigned __int8)*(v12 - 1) | ((unsigned __int8)*v12 << 8) | (((unsigned __int8)v12[1] | 0x200) << 16);
      else
        v15 = *i | 0x2000000;
      NearestColor = GetNearestColor(a2, v15);
      NearestPaletteIndex = GetNearestPaletteIndex(h, NearestColor | 0x2000000);
      if ( NearestPaletteIndex == -1 )
        goto LABEL_21;
      *((_BYTE *)this + v13 + 8) = NearestPaletteIndex;
      if ( v13 >= 40
        && (plpal.palPalEntry[NearestPaletteIndex].peRed
          | (plpal.palPalEntry[NearestPaletteIndex].peGreen << 8)
          | ((plpal.palPalEntry[NearestPaletteIndex].peBlue | 0x200) << 16)) == v15 )
      {
        ++v11;
      }
      ++v13;
      v12 += 4;
    }
    *(_DWORD *)this = 1298223153;
    LOBYTE(v7) = v11 < 212;
    *((_DWORD *)this + 66) = v7;
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x180125e98  mov     [rsp-8+arg_18], rbx
0x180125e9d  push    rbp
0x180125e9e  push    rsi
0x180125e9f  push    rdi
0x180125ea0  push    r12
0x180125ea2  push    r13
0x180125ea4  push    r14
0x180125ea6  push    r15
0x180125ea8  lea     rbp, [rsp-350h]
0x180125eb0  sub     rsp, 450h
0x180125eb7  mov     rax, cs:__security_cookie
0x180125ebe  xor     rax, rsp
0x180125ec1  mov     [rbp+380h+var_40], rax
0x180125ec8  mov     rdi, r8
0x180125ecb  mov     [rsp+480h+hdc], rdx
0x180125ed0  mov     rsi, rdx
0x180125ed3  mov     dword ptr [rcx], 4C494146h
0x180125ed9  mov     r13, rcx
0x180125edc  xor     edx, edx; Val
0x180125ede  mov     r8d, 404h; Size
0x180125ee4  lea     rcx, [rsp+480h+plpal.palPalEntry]; void *
0x180125ee9  call    memset_0
0x180125eee  mov     eax, 300h
0x180125ef3  mov     edx, 0Eh; index
0x180125ef8  mov     rcx, rsi; hdc
0x180125efb  mov     [rsp+480h+plpal.palVersion], ax
0x180125f00  call    cs:__imp_GetDeviceCaps
0x180125f07  nop     dword ptr [rax+rax+00h]
0x180125f0c  mov     edx, 0Ch; index
0x180125f11  mov     rcx, rsi; hdc
0x180125f14  mov     ebx, eax
0x180125f16  call    cs:__imp_GetDeviceCaps
0x180125f1d  nop     dword ptr [rax+rax+00h]
0x180125f22  imul    ebx, eax
0x180125f25  mov     edx, 1
0x180125f2a  mov     r14d, 100h
0x180125f30  mov     cl, bl
0x180125f32  shl     dx, cl
0x180125f35  mov     [rsp+480h+plpal.palNumEntries], dx
0x180125f3a  cmp     dx, r14w
0x180125f3e  jbe     short loc_180125F46
0x180125f40  mov     [rsp+480h+plpal.palNumEntries], r14w
0x180125f46  lea     r9, [rsp+480h+plpal.palPalEntry]; pPalEntries
0x180125f4b  mov     r8d, r14d; cEntries
0x180125f4e  xor     edx, edx; iStart
0x180125f50  mov     rcx, rsi; hdc
0x180125f53  call    cs:__imp_GetSystemPaletteEntries
0x180125f5a  nop     dword ptr [rax+rax+00h]
0x180125f5f  lea     rcx, [rsp+480h+plpal]; plpal
0x180125f64  call    cs:__imp_CreatePalette
0x180125f6b  nop     dword ptr [rax+rax+00h]
0x180125f70  xor     ebx, ebx
0x180125f72  mov     [rsp+480h+h], rax
0x180125f77  test    rax, rax
0x180125f7a  jz      loc_1801260FD
0x180125f80  test    rdi, rdi
0x180125f83  jz      short loc_180126003
0x180125f85  mov     rax, [rdi]
0x180125f88  test    rax, rax
0x180125f8b  jnz     short loc_180125FA5
0x180125f8d  xor     edx, edx
0x180125f8f  mov     ecx, 40Ch
0x180125f94  call    GpMallocEx
0x180125f99  mov     [rdi], rax
0x180125f9c  test    rax, rax
0x180125f9f  jz      loc_1801260EC
0x180125fa5  movzx   ecx, [rsp+480h+plpal.palNumEntries]
0x180125faa  mov     r11d, ebx
0x180125fad  mov     [rax+4], ecx
0x180125fb0  cmp     bx, [rsp+480h+plpal.palNumEntries]
0x180125fb5  jnb     short loc_180126003
0x180125fb7  lea     rax, [rsp+480h+plpal.palPalEntry.peGreen]
0x180125fbc  mov     r10d, 8
0x180125fc2  sub     r10, rax
0x180125fc5  lea     r9, [rsp+480h+plpal.palPalEntry.peGreen]
0x180125fca  movzx   eax, byte ptr [r9]
0x180125fce  inc     r11d
0x180125fd1  movzx   edx, byte ptr [r9-1]
0x180125fd6  mov     rcx, [rdi]
0x180125fd9  or      edx, 0FFFFFF00h
0x180125fdf  shl     edx, 8
0x180125fe2  add     rcx, r10
0x180125fe5  or      edx, eax
0x180125fe7  movzx   eax, byte ptr [r9+1]
0x180125fec  shl     edx, 8
0x180125fef  or      edx, eax
0x180125ff1  mov     [rcx+r9], edx
0x180125ff5  lea     r9, [r9+4]
0x180125ff9  movzx   eax, [rsp+480h+plpal.palNumEntries]
0x180125ffe  cmp     r11d, eax
0x180126001  jl      short loc_180125FCA
0x180126003  lea     rcx, [r13+8]; void *
0x180126007  mov     r8, r14; Size
0x18012600a  xor     edx, edx; Val
0x18012600c  call    memset_0
0x180126011  mov     r12d, ebx
0x180126014  lea     r15, byte_18018BAF5
0x18012601b  mov     r14, rbx
0x18012601e  lea     rsi, dword_1801B34D0
0x180126025  lea     rax, qword_1801B38D0
0x18012602c  cmp     rsi, rax
0x18012602f  jge     loc_1801260D3
0x180126035  lea     rax, [r14-8]
0x180126039  cmp     rax, 3
0x18012603d  ja      short loc_180126047
0x18012603f  mov     edi, [rsi]
0x180126041  bts     edi, 19h
0x180126045  jmp     short loc_180126063
0x180126047  movzx   edi, byte ptr [r15+1]
0x18012604c  movzx   eax, byte ptr [r15]
0x180126050  bts     edi, 9
0x180126054  shl     eax, 8
0x180126057  shl     edi, 10h
0x18012605a  or      edi, eax
0x18012605c  movzx   eax, byte ptr [r15-1]
0x180126061  or      edi, eax
0x180126063  mov     rcx, [rsp+480h+hdc]; hdc
0x180126068  mov     edx, edi; color
0x18012606a  call    cs:__imp_GetNearestColor
0x180126071  nop     dword ptr [rax+rax+00h]
0x180126076  mov     rcx, [rsp+480h+h]; h
0x18012607b  bts     eax, 19h
0x18012607f  mov     edx, eax; color
0x180126081  call    cs:__imp_GetNearestPaletteIndex
0x180126088  nop     dword ptr [rax+rax+00h]
0x18012608d  cmp     eax, 0FFFFFFFFh
0x180126090  jz      short loc_1801260EC
0x180126092  mov     [r14+r13+8], al
0x180126097  cmp     r14, 28h ; '('
0x18012609b  jl      short loc_1801260C3
0x18012609d  mov     ecx, eax
0x18012609f  movzx   edx, [rsp+rcx*4+480h+plpal.palPalEntry.peBlue]
0x1801260a4  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peGreen]
0x1801260a9  bts     edx, 9
0x1801260ad  shl     edx, 10h
0x1801260b0  shl     eax, 8
0x1801260b3  or      edx, eax
0x1801260b5  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peRed]
0x1801260ba  or      edx, eax
0x1801260bc  cmp     edx, edi
0x1801260be  jnz     short loc_1801260C3
0x1801260c0  inc     r12d
0x1801260c3  inc     r14
0x1801260c6  add     rsi, 4
0x1801260ca  add     r15, 4
0x1801260ce  jmp     loc_180126025
0x1801260d3  cmp     r12d, 0D4h
0x1801260da  mov     dword ptr [r13+0], 4D615031h
0x1801260e2  setl    bl
0x1801260e5  mov     [r13+108h], ebx
0x1801260ec  mov     rcx, [rsp+480h+h]; ho
0x1801260f1  call    cs:__imp_DeleteObject
0x1801260f8  nop     dword ptr [rax+rax+00h]
0x1801260fd  mov     rcx, [rbp+380h+var_40]
0x180126104  xor     rcx, rsp; StackCookie
0x180126107  call    __security_check_cookie
0x18012610c  mov     rbx, [rsp+480h+arg_18]
0x180126114  add     rsp, 450h
0x18012611b  pop     r15
0x18012611d  pop     r14
0x18012611f  pop     r13
0x180126121  pop     r12
0x180126123  pop     rdi
0x180126124  pop     rsi
0x180126125  pop     rbp
0x180126126  retn
```
