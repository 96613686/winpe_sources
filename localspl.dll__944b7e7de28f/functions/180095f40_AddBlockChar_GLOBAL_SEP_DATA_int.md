# AddBlockChar(GLOBAL_SEP_DATA *,int)

- ea: `0x180095f40`
- end: `0x18009626a`
- name: `?AddBlockChar@@YAHPEAUGLOBAL_SEP_DATA@@H@Z`
- size: `810`
- prototype: `__int64 __fastcall(struct GLOBAL_SEP_DATA *, BYTE)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009646c`

## callees

- `0x180046650`
- `0x180047330`
- `0x180095f40`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x180095f7c`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByte` at `0x180095f7c`
- `SPOOLSS!DllAllocSplMem` at `0x180095ff9`
- `SPOOLSS!DllAllocSplMem` at `0x180095ff9`
- `GDI32!PatBlt` at `0x180096126`
- `GDI32!PatBlt` at `0x180096126`
- `GDI32!CreateFontIndirectW` at `0x180096059`
- `GDI32!CreateFontIndirectW` at `0x180096059`
- `GDI32!GetBitmapBits` at `0x18009616d`
- `GDI32!GetBitmapBits` at `0x18009616d`
- `GDI32!TextOutA` at `0x180096149`
- `GDI32!TextOutA` at `0x180096149`
- `GDI32!CreateCompatibleDC` at `0x180095fa5`
- `GDI32!CreateCompatibleDC` at `0x180095fa5`
- `GDI32!SelectObject` at `0x180096079`
- `GDI32!SelectObject` at `0x180096095`
- `GDI32!SelectObject` at `0x1800960ad`
- `GDI32!SelectObject` at `0x18009617f`
- `GDI32!SelectObject` at `0x18009618f`
- `GDI32!SelectObject` at `0x180096079`
- `GDI32!SelectObject` at `0x180096095`
- `GDI32!SelectObject` at `0x1800960ad`
- `GDI32!SelectObject` at `0x18009617f`
- `GDI32!SelectObject` at `0x18009618f`
- `GDI32!CreateCompatibleBitmap` at `0x180095fd4`
- `GDI32!CreateCompatibleBitmap` at `0x180095fd4`

## pseudocode

```c
__int64 __fastcall AddBlockChar(struct GLOBAL_SEP_DATA *a1, BYTE a2)
{
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  __int64 v7; // rax
  bool v8; // zf
  LONG v9; // eax
  HFONT v10; // rax
  HGDIOBJ v11; // rbp
  HGDIOBJ v12; // r15
  char v13; // bl
  HDC v14; // rcx
  int v15; // r14d
  LONG BitmapBits; // ebx
  unsigned int v17; // ecx
  unsigned int v18; // edx
  char *v19; // r9
  int i; // r8d
  char v21; // r10
  char *v22; // rbx
  int v23; // esi
  _BYTE *v24; // rdx
  int v25; // r11d
  _BYTE *v26; // rbp
  char v27; // al
  int v28; // eax
  CHAR String[16]; // [rsp+30h] [rbp-A8h] BYREF
  LOGFONTW lf; // [rsp+40h] [rbp-98h] BYREF

  if ( !*((_BYTE *)a1 + 610) && IsDBCSLeadByte(a2) )
  {
    *((_BYTE *)a1 + 610) = a2;
    return 1;
  }
  CompatibleDC = (HDC)*((_QWORD *)a1 + 77);
  if ( CompatibleDC || (CompatibleDC = CreateCompatibleDC(0), (*((_QWORD *)a1 + 77) = CompatibleDC) != 0) )
  {
    if ( *((_QWORD *)a1 + 79)
      || (CompatibleBitmap = CreateCompatibleBitmap(CompatibleDC, 16, 16), (*((_QWORD *)a1 + 79) = CompatibleBitmap) != 0) )
    {
      if ( *((_QWORD *)a1 + 80) || (v7 = DllAllocSplMem(32), (*((_QWORD *)a1 + 80) = v7) != 0) )
      {
        if ( *((_QWORD *)a1 + 78) )
          goto LABEL_15;
        memset_0(&lf, 0, sizeof(lf));
        v8 = *((_BYTE *)a1 + 608) == 77;
        v9 = 8;
        lf.lfHeight = 16;
        if ( v8 )
          v9 = 16;
        lf.lfWeight = 400;
        lf.lfWidth = v9;
        lf.lfPitchAndFamily = 49;
        lf.lfCharSet = 1;
        v10 = CreateFontIndirectW(&lf);
        *((_QWORD *)a1 + 78) = v10;
        if ( v10 )
        {
LABEL_15:
          v11 = SelectObject(*((HDC *)a1 + 77), *((HGDIOBJ *)a1 + 79));
          if ( v11 )
          {
            v12 = SelectObject(*((HDC *)a1 + 77), *((HGDIOBJ *)a1 + 78));
            if ( v12 )
            {
              v13 = *((_BYTE *)a1 + 610);
              if ( v13 )
                String[0] = *((_BYTE *)a1 + 610);
              v14 = (HDC)*((_QWORD *)a1 + 77);
              v15 = v13 != 0 ? 16 : 8;
              String[v13 != 0] = a2;
              PatBlt(v14, 0, 0, 16, 16, 0xFF0062u);
              TextOutA(*((HDC *)a1 + 77), 0, 0, String, (v13 != 0) + 1);
              BitmapBits = GetBitmapBits(
                             *((HBITMAP *)a1 + 79),
                             16 * (((unsigned int)(v13 != 0 ? 31 : 23) >> 3) & 0x1FFFFFFE),
                             *((LPVOID *)a1 + 80));
              SelectObject(*((HDC *)a1 + 77), v11);
              SelectObject(*((HDC *)a1 + 77), v12);
              if ( BitmapBits )
              {
                v17 = 2 * v15;
                if ( *((_BYTE *)a1 + 608) != 77 )
                  v17 = v15;
                v18 = v17 + *((_DWORD *)a1 + 141);
                if ( v18 >= v17 )
                {
                  if ( v18 <= *((_DWORD *)a1 + 142) )
                  {
                    v19 = (char *)*((_QWORD *)a1 + 80);
                    for ( i = 0; i != 4128; i += 258 )
                    {
                      v21 = *v19;
                      v22 = v19;
                      v23 = v15;
                      v24 = (_BYTE *)(*((_QWORD *)a1 + 73) + i);
                      v25 = 0;
                      do
                      {
                        --v23;
                        v26 = v24;
                        v27 = ((v21 >> 7) & 0xFD) + 35;
                        if ( *((_BYTE *)a1 + 608) == 77 )
                        {
                          v24[1] = v27;
                          v24 += 2;
                        }
                        else
                        {
                          ++v24;
                        }
                        *v26 = v27;
                        if ( v25 == 7 )
                          v21 = *++v22;
                        else
                          v21 *= 2;
                        v28 = 0;
                        if ( v25 != 7 )
                          v28 = v25 + 1;
                        v25 = v28;
                      }
                      while ( v23 );
                      v19 += 2;
                    }
                    *((_DWORD *)a1 + 141) += v17;
                    *((_QWORD *)a1 + 73) += v17;
                    *((_DWORD *)a1 + 140) += v17;
                    *((_BYTE *)a1 + 610) = 0;
                  }
                  return 1;
                }
              }
            }
            else
            {
              SelectObject(*((HDC *)a1 + 77), v11);
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180095f40  mov     [rsp+arg_10], rbx
0x180095f45  mov     [rsp+arg_18], rbp
0x180095f4a  push    rsi
0x180095f4b  push    rdi
0x180095f4c  push    r13
0x180095f4e  push    r14
0x180095f50  push    r15
0x180095f52  sub     rsp, 0B0h
0x180095f59  mov     rax, cs:__security_cookie
0x180095f60  xor     rax, rsp
0x180095f63  mov     [rsp+0D8h+var_38], rax
0x180095f6b  cmp     byte ptr [rcx+262h], 0
0x180095f72  mov     esi, edx
0x180095f74  mov     rdi, rcx
0x180095f77  jnz     short loc_180095F97
0x180095f79  mov     cl, sil; TestChar
0x180095f7c  call    cs:__imp_IsDBCSLeadByte
0x180095f82  test    eax, eax
0x180095f84  jz      short loc_180095F97
0x180095f86  mov     [rdi+262h], sil
0x180095f8d  mov     eax, 1
0x180095f92  jmp     loc_1800960B5
0x180095f97  mov     rax, [rdi+268h]
0x180095f9e  test    rax, rax
0x180095fa1  jnz     short loc_180095FBB
0x180095fa3  xor     ecx, ecx; hdc
0x180095fa5  call    cs:__imp_CreateCompatibleDC
0x180095fab  mov     [rdi+268h], rax
0x180095fb2  test    rax, rax
0x180095fb5  jz      loc_1800960B3
0x180095fbb  cmp     qword ptr [rdi+278h], 0
0x180095fc3  mov     r13d, 10h
0x180095fc9  jnz     short loc_180095FEA
0x180095fcb  mov     r8d, r13d; cy
0x180095fce  mov     edx, r13d; cx
0x180095fd1  mov     rcx, rax; hdc
0x180095fd4  call    cs:__imp_CreateCompatibleBitmap
0x180095fda  mov     [rdi+278h], rax
0x180095fe1  test    rax, rax
0x180095fe4  jz      loc_1800960B3
0x180095fea  cmp     qword ptr [rdi+280h], 0
0x180095ff2  jnz     short loc_18009600F
0x180095ff4  mov     ecx, 20h ; ' '
0x180095ff9  call    cs:__imp_DllAllocSplMem
0x180095fff  mov     [rdi+280h], rax
0x180096006  test    rax, rax
0x180096009  jz      loc_1800960B3
0x18009600f  cmp     qword ptr [rdi+270h], 0
0x180096017  jnz     short loc_18009606B
0x180096019  xor     edx, edx; Val
0x18009601b  lea     rcx, [rsp+0D8h+lf]; void *
0x180096020  lea     r8d, [rdx+5Ch]; Size
0x180096024  call    memset_0
0x180096029  cmp     byte ptr [rdi+260h], 4Dh ; 'M'
0x180096030  lea     rcx, [rsp+0D8h+lf]; lplf
0x180096035  mov     eax, 8
0x18009603a  mov     [rsp+0D8h+lf.lfHeight], r13d
0x18009603f  cmovz   eax, r13d
0x180096043  mov     [rsp+0D8h+lf.lfWeight], 190h
0x18009604b  mov     [rsp+0D8h+lf.lfWidth], eax
0x18009604f  mov     [rsp+0D8h+lf.lfPitchAndFamily], 31h ; '1'
0x180096054  mov     [rsp+0D8h+lf.lfCharSet], 1
0x180096059  call    cs:__imp_CreateFontIndirectW
0x18009605f  mov     [rdi+270h], rax
0x180096066  test    rax, rax
0x180096069  jz      short loc_1800960B3
0x18009606b  mov     rdx, [rdi+278h]; h
0x180096072  mov     rcx, [rdi+268h]; hdc
0x180096079  call    cs:__imp_SelectObject
0x18009607f  mov     rbp, rax
0x180096082  test    rax, rax
0x180096085  jz      short loc_1800960B3
0x180096087  mov     rdx, [rdi+270h]; h
0x18009608e  mov     rcx, [rdi+268h]; hdc
0x180096095  call    cs:__imp_SelectObject
0x18009609b  mov     r15, rax
0x18009609e  test    rax, rax
0x1800960a1  jnz     short loc_1800960E1
0x1800960a3  mov     rcx, [rdi+268h]; hdc
0x1800960aa  mov     rdx, rbp; h
0x1800960ad  call    cs:__imp_SelectObject
0x1800960b3  xor     eax, eax
0x1800960b5  mov     rcx, [rsp+0D8h+var_38]
0x1800960bd  xor     rcx, rsp; StackCookie
0x1800960c0  call    __security_check_cookie
0x1800960c5  lea     r11, [rsp+0D8h+var_28]
0x1800960cd  mov     rbx, [r11+40h]
0x1800960d1  mov     rbp, [r11+48h]
0x1800960d5  mov     rsp, r11
0x1800960d8  pop     r15
0x1800960da  pop     r14
0x1800960dc  pop     r13
0x1800960de  pop     rdi
0x1800960df  pop     rsi
0x1800960e0  retn
0x1800960e1  mov     bl, [rdi+262h]
0x1800960e7  test    bl, bl
0x1800960e9  jz      short loc_1800960EF
0x1800960eb  mov     [rsp+0D8h+String], bl
0x1800960ef  mov     rcx, [rdi+268h]; hdc
0x1800960f6  mov     al, bl
0x1800960f8  neg     al
0x1800960fa  mov     [rsp+0D8h+rop], 0FF0062h; rop
0x180096102  mov     r9d, r13d; w
0x180096105  mov     [rsp+0D8h+h], r13d; h
0x18009610a  sbb     r14d, r14d
0x18009610d  xor     eax, eax
0x18009610f  and     r14d, 8
0x180096113  add     r14d, 8
0x180096117  test    bl, bl
0x180096119  setnz   al
0x18009611c  xor     r8d, r8d; y
0x18009611f  xor     edx, edx; x
0x180096121  mov     [rsp+rax+0D8h+String], sil
0x180096126  call    cs:__imp_PatBlt
0x18009612c  mov     rcx, [rdi+268h]; hdc
0x180096133  lea     r9, [rsp+0D8h+String]; lpString
0x180096138  neg     bl
0x18009613a  sbb     eax, eax
0x18009613c  xor     r8d, r8d; y
0x18009613f  neg     eax
0x180096141  xor     edx, edx; x
0x180096143  inc     eax
0x180096145  mov     [rsp+0D8h+h], eax; c
0x180096149  call    cs:__imp_TextOutA
0x18009614f  mov     r8, [rdi+280h]; lpvBits
0x180096156  lea     edx, [r14+0Fh]
0x18009615a  mov     rcx, [rdi+278h]; hbit
0x180096161  shr     edx, 3
0x180096164  and     edx, 1FFFFFFEh
0x18009616a  shl     edx, 4; cb
0x18009616d  call    cs:__imp_GetBitmapBits
0x180096173  mov     rcx, [rdi+268h]; hdc
0x18009617a  mov     rdx, rbp; h
0x18009617d  mov     ebx, eax
0x18009617f  call    cs:__imp_SelectObject
0x180096185  mov     rcx, [rdi+268h]; hdc
0x18009618c  mov     rdx, r15; h
0x18009618f  call    cs:__imp_SelectObject
0x180096195  test    ebx, ebx
0x180096197  jz      loc_1800960B3
0x18009619d  cmp     byte ptr [rdi+260h], 4Dh ; 'M'
0x1800961a4  lea     ecx, [r14+r14]
0x1800961a8  jz      short loc_1800961AD
0x1800961aa  mov     ecx, r14d
0x1800961ad  mov     edx, [rdi+234h]
0x1800961b3  add     edx, ecx
0x1800961b5  cmp     edx, ecx
0x1800961b7  jb      loc_1800960B3
0x1800961bd  cmp     edx, [rdi+238h]
0x1800961c3  ja      loc_180095F8D
0x1800961c9  mov     r9, [rdi+280h]
0x1800961d0  xor     r8d, r8d
0x1800961d3  mov     r10b, [r9]
0x1800961d6  mov     rbx, r9
0x1800961d9  movsxd  rdx, r8d
0x1800961dc  mov     esi, r14d
0x1800961df  add     rdx, [rdi+248h]
0x1800961e6  xor     r11d, r11d
0x1800961e9  mov     al, r10b
0x1800961ec  dec     esi
0x1800961ee  sar     al, 7
0x1800961f1  mov     rbp, rdx
0x1800961f4  and     al, 0FDh
0x1800961f6  add     al, 23h ; '#'
0x1800961f8  cmp     byte ptr [rdi+260h], 4Dh ; 'M'
0x1800961ff  jnz     short loc_18009620A
0x180096201  mov     [rdx+1], al
0x180096204  add     rdx, 2
0x180096208  jmp     short loc_18009620D
0x18009620a  inc     rdx
0x18009620d  mov     [rbp+0], al
0x180096210  lea     ebp, [r11+1]
0x180096214  cmp     r11d, 7
0x180096218  jnz     short loc_180096222
0x18009621a  inc     rbx
0x18009621d  mov     r10b, [rbx]
0x180096220  jmp     short loc_180096225
0x180096222  add     r10b, r10b
0x180096225  xor     eax, eax
0x180096227  cmp     r11d, 7
0x18009622b  cmovnz  eax, ebp
0x18009622e  mov     r11d, eax
0x180096231  test    esi, esi
0x180096233  jnz     short loc_1800961E9
0x180096235  add     r9, 2
0x180096239  add     r8d, 102h
0x180096240  cmp     r8d, 1020h
0x180096247  jnz     short loc_1800961D3
0x180096249  add     [rdi+234h], ecx
0x18009624f  mov     eax, ecx
0x180096251  add     [rdi+248h], rax
0x180096258  add     [rdi+230h], ecx
0x18009625e  mov     [rdi+262h], sil
0x180096265  jmp     loc_180095F8D
```
