# EpPaletteMap::UpdateTranslate(HDC__ *,ColorPalette * *)

- ea: `0x180130048`
- end: `0x18013028b`
- name: `?UpdateTranslate@EpPaletteMap@@QEAAXPEAUHDC__@@PEAPEAUColorPalette@@@Z`
- size: `579`
- prototype: `void(EpPaletteMap *__hidden this, HDC, struct ColorPalette **)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18003d790`
- `0x18012fd10`

## callees

- `0x1800067bc`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180130048`

## import_xrefs

- `GDI32!GetNearestPaletteIndex` at `0x1801301f1`
- `GDI32!GetNearestPaletteIndex` at `0x1801301f1`
- `GDI32!GetNearestColor` at `0x1801301e2`
- `GDI32!GetNearestColor` at `0x1801301e2`
- `GDI32!DeleteObject` at `0x18013025b`
- `GDI32!DeleteObject` at `0x18013025b`
- `GDI32!GetDeviceCaps` at `0x1801300b0`
- `GDI32!GetDeviceCaps` at `0x1801300c0`
- `GDI32!GetDeviceCaps` at `0x1801300b0`
- `GDI32!GetDeviceCaps` at `0x1801300c0`
- `GDI32!GetSystemPaletteEntries` at `0x1801300f4`
- `GDI32!GetSystemPaletteEntries` at `0x1801300f4`
- `GDI32!CreatePalette` at `0x1801300ff`
- `GDI32!CreatePalette` at `0x1801300ff`

## pseudocode

```c
void __fastcall EpPaletteMap::UpdateTranslate(EpPaletteMap *this, HDC a2, struct ColorPalette **a3)
{
  char DeviceCaps; // bl
  HPALETTE v7; // r13
  struct ColorPalette *v8; // rcx
  struct ColorPalette *v9; // rax
  int v10; // r8d
  __int64 v11; // rdx
  int v12; // edi
  char *v13; // rsi
  int v14; // r15d
  COLORREF v15; // ebx
  COLORREF NearestColor; // eax
  UINT NearestPaletteIndex; // eax
  LOGPALETTE plpal; // [rsp+30h] [rbp-D0h] BYREF

  *(_DWORD *)this = 1279869254;
  memset_0(&plpal.palNumEntries, 0, 0x406u);
  plpal.palVersion = 768;
  DeviceCaps = GetDeviceCaps(a2, 14);
  plpal.palNumEntries = 1 << (GetDeviceCaps(a2, 12) * DeviceCaps);
  if ( plpal.palNumEntries > 0x100u )
    plpal.palNumEntries = 256;
  GetSystemPaletteEntries(a2, 0, 0x100u, plpal.palPalEntry);
  v7 = CreatePalette(&plpal);
  if ( v7 )
  {
    if ( a3 )
    {
      v8 = *a3;
      if ( !*a3 )
      {
        v9 = (struct ColorPalette *)GpMallocEx(1036, 0);
        *a3 = v9;
        v8 = v9;
        if ( !v9 )
        {
LABEL_20:
          DeleteObject(v7);
          return;
        }
      }
      v10 = 0;
      *((_DWORD *)v8 + 1) = plpal.palNumEntries;
      if ( plpal.palNumEntries )
      {
        do
        {
          v11 = v10++;
          *((_DWORD *)*a3 + v11 + 2) = plpal.palPalEntry[v11].peBlue
                                     | ((plpal.palPalEntry[v11].peGreen
                                       | ((plpal.palPalEntry[v11].peRed | 0xFFFFFF00) << 8)) << 8);
        }
        while ( v10 < plpal.palNumEntries );
      }
    }
    memset_0((char *)this + 8, 0, 0x100u);
    v12 = 0;
    v13 = &byte_180180A54;
    v14 = 0;
    while ( v12 < 256 )
    {
      if ( (unsigned int)(v12 - 8) > 3 )
        v15 = (unsigned __int8)*v13 | ((unsigned __int8)v13[1] << 8) | (((unsigned __int8)v13[2] | 0x200) << 16);
      else
        v15 = dword_1801A4E50[v12] | 0x2000000;
      NearestColor = GetNearestColor(a2, v15);
      NearestPaletteIndex = GetNearestPaletteIndex(v7, NearestColor | 0x2000000);
      if ( NearestPaletteIndex == -1 )
        goto LABEL_20;
      *((_BYTE *)this + v12 + 8) = NearestPaletteIndex;
      if ( v12 >= 40
        && (plpal.palPalEntry[NearestPaletteIndex].peRed
          | (plpal.palPalEntry[NearestPaletteIndex].peGreen << 8)
          | ((plpal.palPalEntry[NearestPaletteIndex].peBlue | 0x200) << 16)) == v15 )
      {
        ++v14;
      }
      ++v12;
      v13 += 4;
    }
    *(_DWORD *)this = 1298223153;
    *((_DWORD *)this + 66) = v14 < 212;
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x180130048  mov     [rsp-8+arg_18], rbx
0x18013004d  push    rbp
0x18013004e  push    rsi
0x18013004f  push    rdi
0x180130050  push    r12
0x180130052  push    r13
0x180130054  push    r14
0x180130056  push    r15
0x180130058  lea     rbp, [rsp-350h]
0x180130060  sub     rsp, 450h
0x180130067  mov     rax, cs:__security_cookie
0x18013006e  xor     rax, rsp
0x180130071  mov     [rbp+380h+var_40], rax
0x180130078  mov     rdi, r8
0x18013007b  mov     [rsp+480h+hdc], rdx
0x180130080  mov     rsi, rdx
0x180130083  mov     dword ptr [rcx], 4C494146h
0x180130089  mov     r12, rcx
0x18013008c  xor     edx, edx; Val
0x18013008e  mov     r8d, 406h; Size
0x180130094  lea     rcx, [rsp+480h+plpal.palNumEntries]; void *
0x180130099  call    memset_0
0x18013009e  mov     eax, 300h
0x1801300a3  mov     edx, 0Eh; index
0x1801300a8  mov     rcx, rsi; hdc
0x1801300ab  mov     [rsp+480h+plpal.palVersion], ax
0x1801300b0  call    cs:__imp_GetDeviceCaps
0x1801300b6  mov     edx, 0Ch; index
0x1801300bb  mov     rcx, rsi; hdc
0x1801300be  mov     ebx, eax
0x1801300c0  call    cs:__imp_GetDeviceCaps
0x1801300c6  imul    ebx, eax
0x1801300c9  mov     edx, 1
0x1801300ce  mov     cl, bl
0x1801300d0  mov     ebx, 100h
0x1801300d5  shl     dx, cl
0x1801300d8  mov     [rsp+480h+plpal.palNumEntries], dx
0x1801300dd  cmp     dx, bx
0x1801300e0  jbe     short loc_1801300E7
0x1801300e2  mov     [rsp+480h+plpal.palNumEntries], bx
0x1801300e7  lea     r9, [rsp+480h+plpal.palPalEntry]; pPalEntries
0x1801300ec  mov     r8d, ebx; cEntries
0x1801300ef  xor     edx, edx; iStart
0x1801300f1  mov     rcx, rsi; hdc
0x1801300f4  call    cs:__imp_GetSystemPaletteEntries
0x1801300fa  lea     rcx, [rsp+480h+plpal]; plpal
0x1801300ff  call    cs:__imp_CreatePalette
0x180130105  mov     r13, rax
0x180130108  test    rax, rax
0x18013010b  jz      loc_180130261
0x180130111  test    rdi, rdi
0x180130114  jz      short loc_180130183
0x180130116  mov     rcx, [rdi]
0x180130119  test    rcx, rcx
0x18013011c  jnz     short loc_180130139
0x18013011e  xor     edx, edx
0x180130120  mov     ecx, 40Ch
0x180130125  call    GpMallocEx
0x18013012a  mov     [rdi], rax
0x18013012d  mov     rcx, rax
0x180130130  test    rax, rax
0x180130133  jz      loc_180130258
0x180130139  movzx   eax, [rsp+480h+plpal.palNumEntries]
0x18013013e  xor     r8d, r8d
0x180130141  mov     [rcx+4], eax
0x180130144  xor     eax, eax
0x180130146  cmp     ax, [rsp+480h+plpal.palNumEntries]
0x18013014b  jnb     short loc_180130183
0x18013014d  movsxd  rdx, r8d
0x180130150  inc     r8d
0x180130153  movzx   eax, [rsp+rdx*4+480h+plpal.palPalEntry.peGreen]
0x180130158  movzx   ecx, [rsp+rdx*4+480h+plpal.palPalEntry.peRed]
0x18013015d  or      ecx, 0FFFFFF00h
0x180130163  shl     ecx, 8
0x180130166  or      ecx, eax
0x180130168  movzx   eax, [rsp+rdx*4+480h+plpal.palPalEntry.peBlue]
0x18013016d  shl     ecx, 8
0x180130170  or      ecx, eax
0x180130172  mov     rax, [rdi]
0x180130175  mov     [rax+rdx*4+8], ecx
0x180130179  movzx   eax, [rsp+480h+plpal.palNumEntries]
0x18013017e  cmp     r8d, eax
0x180130181  jl      short loc_18013014D
0x180130183  lea     rcx, [r12+8]; void *
0x180130188  mov     r8, rbx; Size
0x18013018b  xor     edx, edx; Val
0x18013018d  call    memset_0
0x180130192  xor     edi, edi
0x180130194  lea     rsi, byte_180180A54
0x18013019b  xor     r15d, r15d
0x18013019e  cmp     edi, ebx
0x1801301a0  jge     loc_18013023C
0x1801301a6  lea     eax, [rdi-8]
0x1801301a9  movsxd  r14, edi
0x1801301ac  cmp     eax, 3
0x1801301af  ja      short loc_1801301C2
0x1801301b1  lea     rbx, dword_1801A4E50
0x1801301b8  mov     ebx, [rbx+r14*4]
0x1801301bc  bts     ebx, 19h
0x1801301c0  jmp     short loc_1801301DB
0x1801301c2  movzx   ebx, byte ptr [rsi+2]
0x1801301c6  movzx   eax, byte ptr [rsi+1]
0x1801301ca  bts     ebx, 9
0x1801301ce  shl     eax, 8
0x1801301d1  shl     ebx, 10h
0x1801301d4  or      ebx, eax
0x1801301d6  movzx   eax, byte ptr [rsi]
0x1801301d9  or      ebx, eax
0x1801301db  mov     rcx, [rsp+480h+hdc]; hdc
0x1801301e0  mov     edx, ebx; color
0x1801301e2  call    cs:__imp_GetNearestColor
0x1801301e8  bts     eax, 19h
0x1801301ec  mov     rcx, r13; h
0x1801301ef  mov     edx, eax; color
0x1801301f1  call    cs:__imp_GetNearestPaletteIndex
0x1801301f7  cmp     eax, 0FFFFFFFFh
0x1801301fa  jz      short loc_180130258
0x1801301fc  mov     [r12+r14+8], al
0x180130201  cmp     edi, 28h ; '('
0x180130204  jl      short loc_18013022C
0x180130206  mov     ecx, eax
0x180130208  movzx   edx, [rsp+rcx*4+480h+plpal.palPalEntry.peBlue]
0x18013020d  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peGreen]
0x180130212  bts     edx, 9
0x180130216  shl     edx, 10h
0x180130219  shl     eax, 8
0x18013021c  or      edx, eax
0x18013021e  movzx   eax, [rsp+rcx*4+480h+plpal.palPalEntry.peRed]
0x180130223  or      edx, eax
0x180130225  cmp     edx, ebx
0x180130227  jnz     short loc_18013022C
0x180130229  inc     r15d
0x18013022c  inc     edi
0x18013022e  mov     ebx, 100h
0x180130233  add     rsi, 4
0x180130237  jmp     loc_18013019E
0x18013023c  xor     eax, eax
0x18013023e  mov     dword ptr [r12], 4D615031h
0x180130246  cmp     r15d, 0D4h
0x18013024d  setl    al
0x180130250  mov     [r12+108h], eax
0x180130258  mov     rcx, r13; ho
0x18013025b  call    cs:__imp_DeleteObject
0x180130261  mov     rcx, [rbp+380h+var_40]
0x180130268  xor     rcx, rsp; StackCookie
0x18013026b  call    __security_check_cookie
0x180130270  mov     rbx, [rsp+480h+arg_18]
0x180130278  add     rsp, 450h
0x18013027f  pop     r15
0x180130281  pop     r14
0x180130283  pop     r13
0x180130285  pop     r12
0x180130287  pop     rdi
0x180130288  pop     rsi
0x180130289  pop     rbp
0x18013028a  retn
```
