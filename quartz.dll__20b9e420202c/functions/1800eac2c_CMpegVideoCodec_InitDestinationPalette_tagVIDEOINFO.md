# CMpegVideoCodec::InitDestinationPalette(tagVIDEOINFO *)

- ea: `0x1800eac2c`
- end: `0x1800eae1b`
- name: `?InitDestinationPalette@CMpegVideoCodec@@AEAAHPEAUtagVIDEOINFO@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(CMpegVideoCodec *__hidden this, struct tagVIDEOINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002dbe0`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x1800eac2c`

## import_xrefs

- `GDI32!GetSystemPaletteEntries` at `0x1800ead57`
- `GDI32!GetSystemPaletteEntries` at `0x1800ead9c`
- `GDI32!GetSystemPaletteEntries` at `0x1800ead57`
- `GDI32!GetSystemPaletteEntries` at `0x1800ead9c`
- `GDI32!GetDeviceCaps` at `0x1800ead01`
- `GDI32!GetDeviceCaps` at `0x1800ead17`
- `GDI32!GetDeviceCaps` at `0x1800ead01`
- `GDI32!GetDeviceCaps` at `0x1800ead17`
- `USER32!ReleaseDC` at `0x1800eadda`
- `USER32!ReleaseDC` at `0x1800eadda`
- `USER32!GetDC` at `0x1800eace1`
- `USER32!GetDC` at `0x1800eace1`

## pseudocode

```c
HDC __fastcall CMpegVideoCodec::InitDestinationPalette(CMpegVideoCodec *this, struct tagVIDEOINFO *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  BYTE v6; // al
  __int64 v7; // rdx
  HDC result; // rax
  HDC v9; // rsi
  int DeviceCaps; // edi
  signed int v11; // eax
  signed int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r8
  BYTE peRed; // al
  BYTE peBlue; // cl
  struct tagPALETTEENTRY pPalEntries[128]; // [rsp+20h] [rbp-228h] BYREF

  if ( *((_DWORD *)this + 110) )
  {
    a2->bmiHeader.biClrUsed = 144;
    memset_0(a2->bmiColors, 0, sizeof(a2->bmiColors));
    v7 = 0;
    do
    {
      a2->bmiColors[v7 + 16].rgbRed = 2 * v7;
      a2->bmiColors[v7 + 16].rgbBlue = 2 * v7;
      a2->bmiColors[v7 + 16].rgbGreen = 2 * v7;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (int)v7 < 128 );
  }
  else
  {
    v4 = 0;
    a2->bmiHeader.biClrUsed = 256;
    v5 = 0;
    do
    {
      v6 = *((_BYTE *)qword_18017CF00 + v5);
      v5 += 3;
      a2->bmiColors[v4].rgbRed = v6;
      a2->bmiColors[v4].rgbBlue = *((_BYTE *)qword_18017CF00 + v5 - 1);
      a2->bmiColors[v4].rgbGreen = *((_BYTE *)qword_18017CF00 + v5 - 2);
      a2->bmiColors[v4++].rgbReserved = 0;
    }
    while ( v4 != 256 );
  }
  result = GetDC(0);
  v9 = result;
  if ( result )
  {
    DeviceCaps = GetDeviceCaps(result, 106);
    if ( (GetDeviceCaps(v9, 38) & 0x100) != 0 )
    {
      v11 = DeviceCaps / 2;
      v12 = v11;
      if ( v11 > 0 && (unsigned int)v11 <= 0x80 )
      {
        GetSystemPaletteEntries(v9, 0, v11, pPalEntries);
        v13 = 0;
        do
        {
          a2->bmiColors[v13].rgbRed = pPalEntries[v13].peRed;
          a2->bmiColors[v13].rgbGreen = pPalEntries[v13].peGreen;
          a2->bmiColors[v13].rgbBlue = pPalEntries[v13].peBlue;
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (int)v13 < v12 );
        if ( !*((_DWORD *)this + 110) )
        {
          GetSystemPaletteEntries(v9, 256 - v12, v12, pPalEntries);
          v14 = 0;
          do
          {
            v15 = (unsigned int)(v14 + 256 - v12);
            peRed = pPalEntries[v14].peRed;
            a2->bmiColors[v15].rgbGreen = pPalEntries[v14].peGreen;
            peBlue = pPalEntries[v14].peBlue;
            v14 = (unsigned int)(v14 + 1);
            a2->bmiColors[v15].rgbRed = peRed;
            a2->bmiColors[v15].rgbBlue = peBlue;
          }
          while ( (int)v14 < v12 );
        }
      }
    }
    ReleaseDC(0, v9);
    result = (HDC)1;
    a2->bmiHeader.biClrImportant = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800eac2c  mov     [rsp+arg_0], rbx
0x1800eac31  mov     [rsp+arg_10], rbp
0x1800eac36  push    rsi
0x1800eac37  push    rdi
0x1800eac38  push    r14
0x1800eac3a  sub     rsp, 230h
0x1800eac41  mov     rax, cs:__security_cookie
0x1800eac48  xor     rax, rsp
0x1800eac4b  mov     [rsp+248h+var_28], rax
0x1800eac53  cmp     dword ptr [rcx+1B8h], 0
0x1800eac5a  mov     rbx, rdx
0x1800eac5d  mov     r14, rcx
0x1800eac60  mov     ebp, 100h
0x1800eac65  jnz     short loc_1800EACA2
0x1800eac67  xor     ecx, ecx
0x1800eac69  mov     [rdx+50h], ebp
0x1800eac6c  xor     edx, edx
0x1800eac6e  lea     r8, qword_18017CF00
0x1800eac75  mov     al, [rdx+r8]
0x1800eac79  lea     rdx, [rdx+3]
0x1800eac7d  mov     [rbx+rcx*4+5Ah], al
0x1800eac81  mov     al, [rdx+r8-1]
0x1800eac86  mov     [rbx+rcx*4+58h], al
0x1800eac8a  mov     al, [rdx+r8-2]
0x1800eac8f  mov     [rbx+rcx*4+59h], al
0x1800eac93  mov     byte ptr [rbx+rcx*4+5Bh], 0
0x1800eac98  inc     rcx
0x1800eac9b  cmp     rcx, rbp
0x1800eac9e  jnz     short loc_1800EAC75
0x1800eaca0  jmp     short loc_1800EACDF
0x1800eaca2  mov     dword ptr [rdx+50h], 90h
0x1800eaca9  lea     rcx, [rdx+58h]; void *
0x1800eacad  xor     edx, edx; Val
0x1800eacaf  mov     r8d, 400h; Size
0x1800eacb5  call    memset_0
0x1800eacba  xor     edx, edx
0x1800eacbc  mov     cl, dl
0x1800eacbe  add     cl, cl
0x1800eacc0  mov     [rbx+rdx*4+9Ah], cl
0x1800eacc7  mov     [rbx+rdx*4+98h], cl
0x1800eacce  mov     [rbx+rdx*4+99h], cl
0x1800eacd5  inc     edx
0x1800eacd7  cmp     edx, 80h
0x1800eacdd  jl      short loc_1800EACBC
0x1800eacdf  xor     ecx, ecx; hWnd
0x1800eace1  call    cs:__imp_GetDC
0x1800eace8  nop     dword ptr [rax+rax+00h]
0x1800eaced  mov     rsi, rax
0x1800eacf0  test    rax, rax
0x1800eacf3  jz      loc_1800EADF2
0x1800eacf9  mov     edx, 6Ah ; 'j'; index
0x1800eacfe  mov     rcx, rsi; hdc
0x1800ead01  call    cs:__imp_GetDeviceCaps
0x1800ead08  nop     dword ptr [rax+rax+00h]
0x1800ead0d  mov     edx, 26h ; '&'; index
0x1800ead12  mov     rcx, rsi; hdc
0x1800ead15  mov     edi, eax
0x1800ead17  call    cs:__imp_GetDeviceCaps
0x1800ead1e  nop     dword ptr [rax+rax+00h]
0x1800ead23  test    ebp, eax
0x1800ead25  jz      loc_1800EADD5
0x1800ead2b  mov     eax, edi
0x1800ead2d  mov     ecx, 2
0x1800ead32  cdq
0x1800ead33  idiv    ecx
0x1800ead35  mov     edi, eax
0x1800ead37  test    eax, eax
0x1800ead39  jle     loc_1800EADD5
0x1800ead3f  cmp     eax, 80h
0x1800ead44  ja      loc_1800EADD5
0x1800ead4a  lea     r9, [rsp+248h+pPalEntries]; pPalEntries
0x1800ead4f  mov     r8d, eax; cEntries
0x1800ead52  xor     edx, edx; iStart
0x1800ead54  mov     rcx, rsi; hdc
0x1800ead57  call    cs:__imp_GetSystemPaletteEntries
0x1800ead5e  nop     dword ptr [rax+rax+00h]
0x1800ead63  xor     edx, edx
0x1800ead65  mov     al, [rsp+rdx*4+248h+pPalEntries.peRed]
0x1800ead69  mov     [rbx+rdx*4+5Ah], al
0x1800ead6d  mov     al, [rsp+rdx*4+248h+pPalEntries.peGreen]
0x1800ead71  mov     [rbx+rdx*4+59h], al
0x1800ead75  mov     al, [rsp+rdx*4+248h+pPalEntries.peBlue]
0x1800ead79  mov     [rbx+rdx*4+58h], al
0x1800ead7d  inc     edx
0x1800ead7f  cmp     edx, edi
0x1800ead81  jl      short loc_1800EAD65
0x1800ead83  cmp     dword ptr [r14+1B8h], 0
0x1800ead8b  jnz     short loc_1800EADD5
0x1800ead8d  sub     ebp, edi
0x1800ead8f  lea     r9, [rsp+248h+pPalEntries]; pPalEntries
0x1800ead94  mov     edx, ebp; iStart
0x1800ead96  mov     r8d, edi; cEntries
0x1800ead99  mov     rcx, rsi; hdc
0x1800ead9c  call    cs:__imp_GetSystemPaletteEntries
0x1800eada3  nop     dword ptr [rax+rax+00h]
0x1800eada8  xor     r9d, r9d
0x1800eadab  mov     cl, [rsp+r9*4+248h+pPalEntries.peGreen]
0x1800eadb0  lea     r8d, [r9+rbp]
0x1800eadb4  mov     al, [rsp+r9*4+248h+pPalEntries.peRed]
0x1800eadb9  mov     [rbx+r8*4+59h], cl
0x1800eadbe  mov     cl, [rsp+r9*4+248h+pPalEntries.peBlue]
0x1800eadc3  inc     r9d
0x1800eadc6  mov     [rbx+r8*4+5Ah], al
0x1800eadcb  mov     [rbx+r8*4+58h], cl
0x1800eadd0  cmp     r9d, edi
0x1800eadd3  jl      short loc_1800EADAB
0x1800eadd5  mov     rdx, rsi; hDC
0x1800eadd8  xor     ecx, ecx; hWnd
0x1800eadda  call    cs:__imp_ReleaseDC
0x1800eade1  nop     dword ptr [rax+rax+00h]
0x1800eade6  mov     eax, 1
0x1800eadeb  mov     dword ptr [rbx+54h], 0
0x1800eadf2  mov     rcx, [rsp+248h+var_28]
0x1800eadfa  xor     rcx, rsp; StackCookie
0x1800eadfd  call    __security_check_cookie
0x1800eae02  lea     r11, [rsp+248h+var_18]
0x1800eae0a  mov     rbx, [r11+20h]
0x1800eae0e  mov     rbp, [r11+30h]
0x1800eae12  mov     rsp, r11
0x1800eae15  pop     r14
0x1800eae17  pop     rdi
0x1800eae18  pop     rsi
0x1800eae19  retn
```
