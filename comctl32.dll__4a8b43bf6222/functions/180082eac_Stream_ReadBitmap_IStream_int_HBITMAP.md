# Stream_ReadBitmap(IStream *,int,HBITMAP__ * *)

- ea: `0x180082eac`
- end: `0x1800831da`
- name: `?Stream_ReadBitmap@@YAJPEAUIStream@@HPEAPEAUHBITMAP__@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct IStream *, int, HBITMAP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180082280`

## callees

- `0x1800115f0`
- `0x180082eac`
- `0x1800852a0`
- `0x18008ea60`
- `0x180090020`

## import_xrefs

- `GDI32!SetDIBits` at `0x180083151`
- `GDI32!SetDIBits` at `0x180083151`
- `GDI32!CreateDIBSection` at `0x18008303d`
- `GDI32!CreateDIBSection` at `0x18008303d`
- `GDI32!DeleteObject` at `0x180083197`
- `GDI32!DeleteObject` at `0x180083197`
- `GDI32!CreateBitmap` at `0x1800830a4`
- `GDI32!CreateBitmap` at `0x1800830a4`
- `KERNEL32!LocalFree` at `0x180083185`
- `KERNEL32!LocalFree` at `0x180083185`
- `KERNEL32!LocalAlloc` at `0x1800830c7`
- `KERNEL32!LocalAlloc` at `0x1800830c7`
- `USER32!GetDC` at `0x180083007`
- `USER32!GetDC` at `0x180083007`
- `USER32!ReleaseDC` at `0x180083177`
- `USER32!ReleaseDC` at `0x180083177`

## pseudocode

```c
__int64 __fastcall Stream_ReadBitmap(struct IStream *a1, int a2, HBITMAP *a3)
{
  HBITMAP v4; // rdi
  int v5; // ebx
  int v6; // esi
  int biWidth; // ebx
  int biHeight; // r15d
  __int64 v9; // r8
  HLOCAL v10; // r14
  HDC DC; // rax
  HDC v12; // r13
  HBITMAP Bitmap; // rax
  int v14; // r8d
  signed int v15; // esi
  int v16; // edx
  UINT v17; // ecx
  UINT cLines; // [rsp+40h] [rbp-C0h]
  UINT cLinesa; // [rsp+40h] [rbp-C0h]
  void *ppvBits; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h]
  HBITMAP *v23; // [rsp+58h] [rbp-A8h]
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  __int16 v26; // [rsp+6Ch] [rbp-94h]
  BITMAPINFO pbmi; // [rsp+70h] [rbp-90h] BYREF

  v23 = a3;
  v22 = a2;
  memset(&pbmi, 0, 1064);
  v24 = 0;
  v4 = 0;
  v25 = 0;
  v26 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IStream *, __int64 *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, &v24, 14, 0);
  if ( v5 >= 0 )
  {
    if ( (_WORD)v24 != 19778 )
    {
      v5 = -2147024809;
      goto LABEL_37;
    }
    v5 = (*(__int64 (__fastcall **)(struct IStream *, BITMAPINFO *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
           a1,
           &pbmi,
           40,
           0);
    if ( v5 >= 0 )
    {
      v5 = -2147024809;
      if ( pbmi.bmiHeader.biSize == 40 )
      {
        v6 = pbmi.bmiHeader.biBitCount * pbmi.bmiHeader.biPlanes;
        if ( v6 >= 0 )
        {
          biWidth = pbmi.bmiHeader.biWidth;
          biHeight = pbmi.bmiHeader.biHeight;
          cLines = pbmi.bmiHeader.biWidth;
          if ( v6 > 8 )
            v9 = 0;
          else
            v9 = 4 * (unsigned int)(1LL << v6);
          LODWORD(ppvBits) = (pbmi.bmiHeader.biWidth * v6 + 31) / 32;
          pbmi.bmiHeader.biSizeImage = 4 * pbmi.bmiHeader.biHeight * (_DWORD)ppvBits;
          if ( (_DWORD)v9 )
          {
            v5 = (*(__int64 (__fastcall **)(struct IStream *, BYTE *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
                   a1,
                   &pbmi.bmiColors[0].rgbBlue,
                   v9,
                   0);
            if ( v5 < 0 )
              goto LABEL_37;
            biWidth = cLines;
          }
          v10 = 0;
          DC = GetDC(0);
          v12 = DC;
          if ( v6 <= 1 )
          {
            Bitmap = CreateBitmap(biWidth, biHeight, 1u, 1u, 0);
          }
          else
          {
            if ( v22 != 254 )
            {
              ppvBits = 0;
              v4 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
              if ( v4 )
              {
                v5 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                       a1,
                       ppvBits,
                       pbmi.bmiHeader.biSizeImage,
                       0);
                if ( v5 >= 0 )
                {
                  ppvBits = 0;
LABEL_28:
                  v5 = 0;
                }
              }
              else
              {
                v5 = -2147024882;
              }
LABEL_29:
              if ( v12 )
                ReleaseDC(0, v12);
              if ( v10 )
                LocalFree(v10);
              if ( v5 < 0 && v4 )
              {
                DeleteObject(v4);
                v4 = 0;
              }
              goto LABEL_37;
            }
            Bitmap = (HBITMAP)CreateColorBitmap(biWidth, biHeight);
          }
          v4 = Bitmap;
          v5 = -2147024882;
          if ( !Bitmap )
            goto LABEL_29;
          v10 = LocalAlloc(0x40u, 0x1000u);
          if ( !v10 )
            goto LABEL_29;
          v14 = 4 * (_DWORD)ppvBits;
          LODWORD(ppvBits) = v14;
          v15 = 0;
          v16 = 4096 / v14;
          if ( biHeight > 0 )
          {
            while ( 1 )
            {
              v17 = biHeight - v15;
              if ( v16 <= biHeight - v15 )
                v17 = v16;
              cLinesa = v17;
              v5 = (*(__int64 (__fastcall **)(struct IStream *, HLOCAL, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                     a1,
                     v10,
                     v17 * v14,
                     0);
              if ( v5 < 0 )
                goto LABEL_29;
              v5 = -2147024882;
              if ( !SetDIBits(v12, v4, v15, cLinesa, v10, &pbmi, 0) )
                goto LABEL_29;
              v16 = cLinesa;
              v15 += cLinesa;
              v14 = (int)ppvBits;
              if ( v15 >= biHeight )
                goto LABEL_28;
            }
          }
          goto LABEL_28;
        }
      }
    }
  }
LABEL_37:
  *v23 = v4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180082eac  mov     [rsp-8+arg_8], rbx
0x180082eb1  push    rbp
0x180082eb2  push    rsi
0x180082eb3  push    rdi
0x180082eb4  push    r12
0x180082eb6  push    r13
0x180082eb8  push    r14
0x180082eba  push    r15
0x180082ebc  lea     rbp, [rsp-3B0h]
0x180082ec4  sub     rsp, 4B0h
0x180082ecb  mov     rax, cs:__security_cookie
0x180082ed2  xor     rax, rsp
0x180082ed5  mov     [rbp+3E0h+var_40], rax
0x180082edc  mov     [rsp+4E0h+var_488], r8
0x180082ee1  mov     r12, rcx
0x180082ee4  mov     [rsp+4E0h+var_490], edx
0x180082ee8  lea     rcx, [rsp+4E0h+pbmi.bmiHeader.biWidth]; void *
0x180082eed  xor     edx, edx; Val
0x180082eef  mov     [rsp+4E0h+pbmi.bmiHeader.biSize], 0
0x180082ef7  mov     r8d, 424h; Size
0x180082efd  call    memset
0x180082f02  xor     eax, eax
0x180082f04  lea     rdx, [rsp+4E0h+var_480]
0x180082f09  mov     [rsp+4E0h+var_480], rax
0x180082f0e  xor     edi, edi
0x180082f10  mov     [rsp+4E0h+var_478], eax
0x180082f14  xor     r9d, r9d
0x180082f17  mov     [rsp+4E0h+var_474], ax
0x180082f1c  mov     rcx, r12
0x180082f1f  mov     rax, [r12]
0x180082f23  lea     r8d, [rdi+0Eh]
0x180082f27  mov     rax, [rax+18h]
0x180082f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f30  mov     ebx, eax
0x180082f32  test    eax, eax
0x180082f34  js      loc_1800831A6
0x180082f3a  mov     eax, 4D42h
0x180082f3f  cmp     word ptr [rsp+4E0h+var_480], ax
0x180082f44  jnz     loc_1800831A1
0x180082f4a  mov     rax, [r12]
0x180082f4e  lea     r8d, [rdi+28h]
0x180082f52  xor     r9d, r9d
0x180082f55  lea     rdx, [rsp+4E0h+pbmi]
0x180082f5a  mov     rcx, r12
0x180082f5d  mov     rax, [rax+18h]
0x180082f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f66  mov     ebx, eax
0x180082f68  test    eax, eax
0x180082f6a  js      loc_1800831A6
0x180082f70  cmp     [rsp+4E0h+pbmi.bmiHeader.biSize], 28h ; '('
0x180082f75  mov     ebx, 80070057h
0x180082f7a  jnz     loc_1800831A6
0x180082f80  movzx   esi, [rsp+4E0h+pbmi.bmiHeader.biPlanes]
0x180082f85  movzx   eax, [rsp+4E0h+pbmi.bmiHeader.biBitCount]
0x180082f8a  imul    esi, eax
0x180082f8d  test    esi, esi
0x180082f8f  js      loc_1800831A6
0x180082f95  mov     ebx, [rsp+4E0h+pbmi.bmiHeader.biWidth]
0x180082f99  mov     r15d, [rsp+4E0h+pbmi.bmiHeader.biHeight]
0x180082f9e  mov     [rsp+4E0h+cLines], ebx
0x180082fa2  cmp     esi, 8
0x180082fa5  jg      short loc_180082FB6
0x180082fa7  mov     ecx, esi
0x180082fa9  lea     r8d, [rdi+1]
0x180082fad  shl     r8, cl
0x180082fb0  shl     r8d, 2
0x180082fb4  jmp     short loc_180082FB9
0x180082fb6  xor     r8d, r8d
0x180082fb9  mov     eax, esi
0x180082fbb  imul    eax, ebx
0x180082fbe  add     eax, 1Fh
0x180082fc1  cdq
0x180082fc2  and     edx, 1Fh
0x180082fc5  add     eax, edx
0x180082fc7  sar     eax, 5
0x180082fca  mov     dword ptr [rsp+4E0h+ppvBits], eax
0x180082fce  imul    eax, r15d
0x180082fd2  shl     eax, 2
0x180082fd5  mov     [rbp+3E0h+pbmi.bmiHeader.biSizeImage], eax
0x180082fd8  test    r8d, r8d
0x180082fdb  jz      short loc_180083002
0x180082fdd  mov     rax, [r12]
0x180082fe1  lea     rdx, [rbp+3E0h+pbmi.bmiColors]
0x180082fe5  xor     r9d, r9d
0x180082fe8  mov     rcx, r12
0x180082feb  mov     rax, [rax+18h]
0x180082fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ff4  mov     ebx, eax
0x180082ff6  test    eax, eax
0x180082ff8  js      loc_1800831A6
0x180082ffe  mov     ebx, [rsp+4E0h+cLines]
0x180083002  xor     ecx, ecx; hWnd
0x180083004  xor     r14d, r14d
0x180083007  call    cs:__imp_GetDC
0x18008300d  mov     r13, rax
0x180083010  cmp     esi, 1
0x180083013  jle     short loc_180083091
0x180083015  cmp     [rsp+4E0h+var_490], 0FEh
0x18008301d  jz      short loc_180083085
0x18008301f  mov     [rsp+4E0h+offset], edi; offset
0x180083023  lea     r9, [rsp+4E0h+ppvBits]; ppvBits
0x180083028  xor     r8d, r8d; usage
0x18008302b  mov     [rsp+4E0h+hSection], rdi; hSection
0x180083030  lea     rdx, [rsp+4E0h+pbmi]; pbmi
0x180083035  mov     [rsp+4E0h+ppvBits], rdi
0x18008303a  mov     rcx, rax; hdc
0x18008303d  call    cs:__imp_CreateDIBSection
0x180083043  mov     rdi, rax
0x180083046  test    rax, rax
0x180083049  jz      short loc_18008307B
0x18008304b  mov     rdx, [r12]
0x18008304f  xor     r9d, r9d
0x180083052  mov     r8d, [rbp+3E0h+pbmi.bmiHeader.biSizeImage]
0x180083056  mov     rcx, r12
0x180083059  mov     rax, [rdx+18h]
0x18008305d  mov     rdx, [rsp+4E0h+ppvBits]
0x180083062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083067  mov     ebx, eax
0x180083069  test    eax, eax
0x18008306b  js      loc_18008316D
0x180083071  mov     [rsp+4E0h+ppvBits], r14
0x180083076  jmp     loc_18008316B
0x18008307b  mov     ebx, 8007000Eh
0x180083080  jmp     loc_18008316D
0x180083085  mov     edx, r15d; cy
0x180083088  mov     ecx, ebx; cx
0x18008308a  call    CreateColorBitmap
0x18008308f  jmp     short loc_1800830AA
0x180083091  mov     r9d, 1; nBitCount
0x180083097  mov     [rsp+4E0h+hSection], rdi; lpBits
0x18008309c  mov     r8d, r9d; nPlanes
0x18008309f  mov     edx, r15d; nHeight
0x1800830a2  mov     ecx, ebx; nWidth
0x1800830a4  call    cs:__imp_CreateBitmap
0x1800830aa  mov     rdi, rax
0x1800830ad  mov     ebx, 8007000Eh
0x1800830b2  test    rax, rax
0x1800830b5  jz      loc_18008316D
0x1800830bb  mov     esi, 1000h
0x1800830c0  mov     ecx, 40h ; '@'; uFlags
0x1800830c5  mov     edx, esi; uBytes
0x1800830c7  call    cs:__imp_LocalAlloc
0x1800830cd  mov     r14, rax
0x1800830d0  test    rax, rax
0x1800830d3  jz      loc_18008316D
0x1800830d9  mov     eax, dword ptr [rsp+4E0h+ppvBits]
0x1800830dd  lea     r8d, ds:0[rax*4]
0x1800830e5  mov     eax, esi
0x1800830e7  cdq
0x1800830e8  mov     dword ptr [rsp+4E0h+ppvBits], r8d
0x1800830ed  idiv    r8d
0x1800830f0  xor     esi, esi
0x1800830f2  mov     edx, eax
0x1800830f4  test    r15d, r15d
0x1800830f7  jle     short loc_18008316B
0x1800830f9  mov     rax, [r12]
0x1800830fd  mov     ecx, r15d
0x180083100  sub     ecx, esi
0x180083102  cmp     edx, ecx
0x180083104  mov     rax, [rax+18h]
0x180083108  cmovle  ecx, edx
0x18008310b  imul    r8d, ecx
0x18008310f  xor     r9d, r9d
0x180083112  mov     [rsp+4E0h+cLines], ecx
0x180083116  mov     rdx, r14
0x180083119  mov     rcx, r12
0x18008311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083121  mov     ebx, eax
0x180083123  test    eax, eax
0x180083125  js      short loc_18008316D
0x180083127  mov     r9d, [rsp+4E0h+cLines]; cLines
0x18008312c  lea     rax, [rsp+4E0h+pbmi]
0x180083131  mov     [rsp+4E0h+ColorUse], 0; ColorUse
0x180083139  mov     r8d, esi; start
0x18008313c  mov     qword ptr [rsp+4E0h+offset], rax; lpbmi
0x180083141  mov     rdx, rdi; hbm
0x180083144  mov     rcx, r13; hdc
0x180083147  mov     [rsp+4E0h+hSection], r14; lpBits
0x18008314c  mov     ebx, 8007000Eh
0x180083151  call    cs:__imp_SetDIBits
0x180083157  test    eax, eax
0x180083159  jz      short loc_18008316D
0x18008315b  mov     edx, [rsp+4E0h+cLines]
0x18008315f  add     esi, edx
0x180083161  mov     r8d, dword ptr [rsp+4E0h+ppvBits]
0x180083166  cmp     esi, r15d
0x180083169  jl      short loc_1800830F9
0x18008316b  xor     ebx, ebx
0x18008316d  test    r13, r13
0x180083170  jz      short loc_18008317D
0x180083172  mov     rdx, r13; hDC
0x180083175  xor     ecx, ecx; hWnd
0x180083177  call    cs:__imp_ReleaseDC
0x18008317d  test    r14, r14
0x180083180  jz      short loc_18008318B
0x180083182  mov     rcx, r14; hMem
0x180083185  call    cs:__imp_LocalFree
0x18008318b  test    ebx, ebx
0x18008318d  jns     short loc_1800831A6
0x18008318f  test    rdi, rdi
0x180083192  jz      short loc_1800831A6
0x180083194  mov     rcx, rdi; ho
0x180083197  call    cs:__imp_DeleteObject
0x18008319d  xor     edi, edi
0x18008319f  jmp     short loc_1800831A6
0x1800831a1  mov     ebx, 80070057h
0x1800831a6  mov     rax, [rsp+4E0h+var_488]
0x1800831ab  mov     [rax], rdi
0x1800831ae  mov     eax, ebx
0x1800831b0  mov     rcx, [rbp+3E0h+var_40]
0x1800831b7  xor     rcx, rsp; StackCookie
0x1800831ba  call    __security_check_cookie
0x1800831bf  mov     rbx, [rsp+4E0h+arg_8]
0x1800831c7  add     rsp, 4B0h
0x1800831ce  pop     r15
0x1800831d0  pop     r14
0x1800831d2  pop     r13
0x1800831d4  pop     r12
0x1800831d6  pop     rdi
0x1800831d7  pop     rsi
0x1800831d8  pop     rbp
0x1800831d9  retn
```
