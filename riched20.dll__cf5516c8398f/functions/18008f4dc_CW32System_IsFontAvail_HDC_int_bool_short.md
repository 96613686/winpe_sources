# CW32System::IsFontAvail(HDC__ *,int,bool,short *)

- ea: `0x18008f4dc`
- end: `0x18008f698`
- name: `?IsFontAvail@CW32System@@SA_NPEAUHDC__@@H_NPEAF@Z`
- size: `444`
- prototype: `bool __fastcall(HDC hdc, int, bool, __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18008d3a0`
- `0x18008de60`

## callees

- `0x180029d38`
- `0x180031ff0`
- `0x18003dc58`
- `0x18008d830`
- `0x18008e1f8`
- `0x18008e358`
- `0x18008f4dc`
- `0x180090ff0`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18008f593`
- `msvcrt!wcscpy_s` at `0x18008f593`
- `GDI32!DeleteObject` at `0x18008f64d`
- `GDI32!DeleteObject` at `0x18008f64d`
- `GDI32!SelectObject` at `0x18008f5d1`
- `GDI32!SelectObject` at `0x18008f644`
- `GDI32!SelectObject` at `0x18008f5d1`
- `GDI32!SelectObject` at `0x18008f644`

## pseudocode

```c
char __fastcall CW32System::IsFontAvail(HDC hdc, int a2, char a3, __int16 *a4)
{
  BYTE CharSet; // si
  BYTE v9; // al
  int v10; // ecx
  const wchar_t *FontName; // rax
  char v12; // di
  HFONT v13; // rax
  HFONT v14; // rbx
  HGDIOBJ v15; // r12
  int v16; // edx
  const unsigned __int16 *v17; // rsi
  int v19[4]; // [rsp+20h] [rbp-E0h] BYREF
  struct tagLOGFONTW v20; // [rsp+30h] [rbp-D0h] BYREF
  struct tagTEXTMETRICW v21; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 Src[32]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&v20, 0, sizeof(v20));
  v19[0] = 0;
  CharSet = CW32System::GetCharSet(a2, v19);
  if ( CharSet && v19[0] == -1 )
    return 0;
  v20.lfCharSet = CharSet;
  if ( a3 )
  {
    v20.lfHeight = *((unsigned __int8 *)&g_pfinfo + 8 * v19[0] + 1);
    v9 = *((_BYTE *)&g_pfinfo + 8 * v19[0]);
    v10 = *((__int16 *)&g_pfinfo + 4 * v19[0] + 1);
  }
  else
  {
    v20.lfHeight = *((unsigned __int8 *)&g_pfinfo + 8 * v19[0] + 5);
    v9 = *((_BYTE *)&g_pfinfo + 8 * v19[0] + 4);
    v10 = *((__int16 *)&g_pfinfo + 4 * v19[0] + 3);
  }
  v20.lfPitchAndFamily = v9;
  FontName = GetFontName(v10);
  if ( !FontName )
    return 0;
  wcscpy_s(v20.lfFaceName, 0x20u, FontName);
  v20.lfHeight &= ~0x80u;
  v12 = 0;
  v13 = CW32System::CreateFontIndirect(&v20);
  v14 = v13;
  if ( v13 )
  {
    memset(&v21, 0, sizeof(v21));
    v15 = SelectObject(hdc, v13);
    if ( (unsigned int)CW32System::GetTextMetrics(hdc, &v21) )
    {
      if ( v21.tmCharSet == CharSet )
      {
        v12 = 1;
        if ( a4 )
        {
          v17 = GetFontName(*a4);
          if ( v17 )
          {
            Src[0] = 0;
            CW32System::GetTextFace(hdc, v16, Src);
            if ( Src[0] )
            {
              if ( (unsigned int)CW32System::wcsicmp(v17, Src) )
                *a4 = GetFontNameIndex(Src);
            }
          }
        }
      }
    }
    SelectObject(hdc, v15);
    DeleteObject(v14);
  }
  return v12;
}

```

## disassembly

```asm
0x18008f4dc  mov     [rsp-8+arg_10], rbx
0x18008f4e1  push    rbp
0x18008f4e2  push    rsi
0x18008f4e3  push    rdi
0x18008f4e4  push    r12
0x18008f4e6  push    r13
0x18008f4e8  push    r14
0x18008f4ea  push    r15
0x18008f4ec  lea     rbp, [rsp-20h]
0x18008f4f1  sub     rsp, 120h
0x18008f4f8  mov     rax, cs:__security_cookie
0x18008f4ff  xor     rax, rsp
0x18008f502  mov     [rbp+50h+var_40], rax
0x18008f506  mov     ebx, edx
0x18008f508  mov     dil, r8b
0x18008f50b  xor     edx, edx; Val
0x18008f50d  mov     r14, rcx
0x18008f510  lea     rcx, [rsp+150h+var_120]; void *
0x18008f515  mov     r15, r9
0x18008f518  lea     r8d, [rdx+5Ch]; Size
0x18008f51c  call    memset_0
0x18008f521  xor     r13d, r13d
0x18008f524  lea     rdx, [rsp+150h+var_130]; int *
0x18008f529  mov     ecx, ebx; int
0x18008f52b  mov     [rsp+150h+var_130], r13d
0x18008f530  call    ?GetCharSet@CW32System@@SAEHPEAH@Z; CW32System::GetCharSet(int,int *)
0x18008f535  mov     sil, al
0x18008f538  movsxd  rax, [rsp+150h+var_130]
0x18008f53d  test    sil, sil
0x18008f540  jz      short loc_18008F54B
0x18008f542  cmp     eax, 0FFFFFFFFh
0x18008f545  jz      loc_18008F694
0x18008f54b  mov     [rsp+150h+var_120.lfCharSet], sil
0x18008f550  mov     rcx, rax
0x18008f553  lea     rdx, ?g_pfinfo@@3PAUPreferredFontInfo@@A; PreferredFontInfo near * g_pfinfo
0x18008f55a  test    dil, dil
0x18008f55d  jz      loc_18008F67D
0x18008f563  movzx   eax, byte ptr [rdx+rax*8+1]
0x18008f568  mov     [rsp+150h+var_120.lfHeight], eax
0x18008f56c  mov     al, [rdx+rcx*8]
0x18008f56f  movsx   ecx, word ptr [rdx+rcx*8+2]; int
0x18008f574  mov     [rsp+150h+var_120.lfPitchAndFamily], al
0x18008f578  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x18008f57d  test    rax, rax
0x18008f580  jz      loc_18008F694
0x18008f586  mov     r8, rax; Source
0x18008f589  lea     rcx, [rsp+150h+var_120.lfFaceName]; Destination
0x18008f58e  mov     edx, 20h ; ' '; SizeInWords
0x18008f593  call    cs:__imp_wcscpy_s
0x18008f599  btr     [rsp+150h+var_120.lfHeight], 7
0x18008f59f  lea     rcx, [rsp+150h+var_120]; struct tagLOGFONTW *
0x18008f5a4  mov     dil, r13b
0x18008f5a7  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18008f5ac  mov     rbx, rax
0x18008f5af  test    rax, rax
0x18008f5b2  jz      loc_18008F653
0x18008f5b8  xorps   xmm0, xmm0
0x18008f5bb  mov     rdx, rax; h
0x18008f5be  movups  xmmword ptr [rbp+50h+var_C0.tmOverhang], xmm0
0x18008f5c2  mov     rcx, r14; hdc
0x18008f5c5  movups  xmmword ptr [rbp+50h+var_C0.tmFirstChar], xmm0
0x18008f5c9  movups  xmmword ptr [rbp+50h+var_C0.tmHeight], xmm0
0x18008f5cd  movups  xmmword ptr [rbp+50h+var_C0.tmExternalLeading], xmm0
0x18008f5d1  call    cs:__imp_SelectObject
0x18008f5d7  lea     rdx, [rbp+50h+var_C0]; struct tagTEXTMETRICW *
0x18008f5db  mov     rcx, r14; HDC
0x18008f5de  mov     r12, rax
0x18008f5e1  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x18008f5e6  test    eax, eax
0x18008f5e8  jz      short loc_18008F63E
0x18008f5ea  cmp     [rbp+50h+var_C0.tmCharSet], sil
0x18008f5ee  jnz     short loc_18008F63E
0x18008f5f0  mov     dil, 1
0x18008f5f3  test    r15, r15
0x18008f5f6  jz      short loc_18008F63E
0x18008f5f8  movsx   ecx, word ptr [r15]; int
0x18008f5fc  call    ?GetFontName@@YAPEBGJ@Z; GetFontName(long)
0x18008f601  mov     rsi, rax
0x18008f604  test    rax, rax
0x18008f607  jz      short loc_18008F63E
0x18008f609  lea     r8, [rbp+50h+Src]; unsigned __int16 *
0x18008f60d  mov     [rbp+50h+Src], r13w
0x18008f612  mov     rcx, r14; hdc
0x18008f615  call    ?GetTextFace@CW32System@@SAHPEAUHDC__@@HPEAG@Z; CW32System::GetTextFace(HDC__ *,int,ushort *)
0x18008f61a  cmp     [rbp+50h+Src], r13w
0x18008f61f  jz      short loc_18008F63E
0x18008f621  lea     rdx, [rbp+50h+Src]; unsigned __int16 *
0x18008f625  mov     rcx, rsi; unsigned __int16 *
0x18008f628  call    ?wcsicmp@CW32System@@SAHPEBG0@Z; CW32System::wcsicmp(ushort const *,ushort const *)
0x18008f62d  test    eax, eax
0x18008f62f  jz      short loc_18008F63E
0x18008f631  lea     rcx, [rbp+50h+Src]; Src
0x18008f635  call    ?GetFontNameIndex@@YAFPEBG@Z; GetFontNameIndex(ushort const *)
0x18008f63a  mov     [r15], ax
0x18008f63e  mov     rdx, r12; h
0x18008f641  mov     rcx, r14; hdc
0x18008f644  call    cs:__imp_SelectObject
0x18008f64a  mov     rcx, rbx; ho
0x18008f64d  call    cs:__imp_DeleteObject
0x18008f653  mov     al, dil
0x18008f656  mov     rcx, [rbp+50h+var_40]
0x18008f65a  xor     rcx, rsp; StackCookie
0x18008f65d  call    __security_check_cookie
0x18008f662  mov     rbx, [rsp+150h+arg_10]
0x18008f66a  add     rsp, 120h
0x18008f671  pop     r15
0x18008f673  pop     r14
0x18008f675  pop     r13
0x18008f677  pop     r12
0x18008f679  pop     rdi
0x18008f67a  pop     rsi
0x18008f67b  pop     rbp
0x18008f67c  retn
0x18008f67d  movzx   eax, byte ptr [rdx+rax*8+5]
0x18008f682  mov     [rsp+150h+var_120.lfHeight], eax
0x18008f686  mov     al, [rdx+rcx*8+4]
0x18008f68a  movsx   ecx, word ptr [rdx+rcx*8+6]
0x18008f68f  jmp     loc_18008F574
0x18008f694  xor     al, al
0x18008f696  jmp     short loc_18008F656
```
