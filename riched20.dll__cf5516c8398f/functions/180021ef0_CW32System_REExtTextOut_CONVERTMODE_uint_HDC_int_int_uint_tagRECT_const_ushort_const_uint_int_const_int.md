# CW32System::REExtTextOut(CONVERTMODE,uint,HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *,int)

- ea: `0x180021ef0`
- end: `0x18002246e`
- name: `?REExtTextOut@CW32System@@SAXW4CONVERTMODE@@IPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBHH@Z`
- size: `1406`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180021160`
- `0x180021d18`

## callees

- `0x180021ef0`
- `0x180022b04`
- `0x180023010`
- `0x180029bd0`
- `0x18002a144`
- `0x180033af0`
- `0x18003df20`
- `0x180041128`
- `0x1800475c4`
- `0x18008d830`
- `0x18008e358`
- `0x180090148`
- `0x18009110a`
- `0x180091140`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800220a3`
- `KERNEL32!WideCharToMultiByte` at `0x180022357`
- `KERNEL32!WideCharToMultiByte` at `0x1800220a3`
- `KERNEL32!WideCharToMultiByte` at `0x180022357`
- `GDI32!ExtTextOutW` at `0x180021fc2`
- `GDI32!ExtTextOutW` at `0x180021fc2`
- `GDI32!GetDeviceCaps` at `0x18002228c`
- `GDI32!GetDeviceCaps` at `0x18002228c`
- `GDI32!DeleteObject` at `0x180022463`
- `GDI32!DeleteObject` at `0x180022463`
- `GDI32!GetStockObject` at `0x180022137`
- `GDI32!GetStockObject` at `0x180022137`
- `GDI32!SelectObject` at `0x180022143`
- `GDI32!SelectObject` at `0x180022197`
- `GDI32!SelectObject` at `0x180022458`
- `GDI32!SelectObject` at `0x180022143`
- `GDI32!SelectObject` at `0x180022197`
- `GDI32!SelectObject` at `0x180022458`
- `GDI32!ExtTextOutA` at `0x180022219`
- `GDI32!ExtTextOutA` at `0x180022219`

## pseudocode

```c
void __fastcall CW32System::REExtTextOut(
        int a1,
        unsigned int a2,
        HDC a3,
        int a4,
        int y,
        UINT options,
        RECT *lprect,
        LPCWSTR lpWideCharStr,
        UINT c,
        INT *lpDx,
        int a11)
{
  __int64 v12; // r15
  INT *v15; // r12
  int v16; // r8d
  int v17; // ecx
  const CHAR *lpString; // r8
  UINT v19; // edi
  signed int v20; // edx
  unsigned __int8 v21; // cl
  HGDIOBJ StockObject; // rax
  unsigned int v23; // eax
  void *v24; // rcx
  unsigned int v25; // ecx
  unsigned int v26; // r9d
  INT *v27; // rax
  unsigned __int8 *v28; // r11
  INT *v29; // r15
  int v30; // ebx
  int TrailBytesCount; // eax
  const INT *v32; // r10
  __int64 v33; // r11
  __int64 v34; // rax
  bool v35; // zf
  UINT CodePage; // [rsp+50h] [rbp-B0h]
  UINT CodePagea; // [rsp+50h] [rbp-B0h]
  CHAR *Buf; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+60h] [rbp-A0h]
  int cbMultiByte; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+70h] [rbp-90h]
  HFONT ho; // [rsp+78h] [rbp-88h]
  struct tagTEXTMETRICW v43; // [rsp+80h] [rbp-80h] BYREF
  struct tagLOGFONTW v44; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v45[256]; // [rsp+120h] [rbp+20h] BYREF
  void *lpMem; // [rsp+220h] [rbp+120h]
  int v47; // [rsp+228h] [rbp+128h]
  _BYTE v48[256]; // [rsp+230h] [rbp+130h] BYREF
  void *v49; // [rsp+330h] [rbp+230h]
  int v50; // [rsp+338h] [rbp+238h]

  LODWORD(v12) = c;
  v15 = lpDx;
  CodePage = a2;
  if ( lpWideCharStr )
  {
    v16 = 0;
    v39 = 0;
    ho = 0;
    h = 0;
    if ( *lpWideCharStr == 8364 )
    {
      if ( GetDeviceCaps(a3, 2) != 1 || (unsigned int)CW32System::IsEnhancedMetafileDC(a3) )
      {
        v39 = 1;
        StockObject = GetStockObject(12);
        h = SelectObject(a3, StockObject);
        memset_0(&v44, 0, sizeof(v44));
        CW32System::GetObjectW(h, 92, &v44);
        if ( CW32System::_dwPlatformId == 1 )
          v44.lfOutPrecision = 7;
        else
          v44.lfOutPrecision = 9;
        ho = CW32System::CreateFontIndirect(&v44);
        SelectObject(a3, ho);
      }
      a2 = CodePage;
      v16 = 0;
    }
    if ( CW32System::_dwPlatformId == 1 )
    {
      if ( c )
      {
        while ( 1 )
        {
          v26 = lpWideCharStr[v16];
          if ( v26 > 0x7F && (v26 - 160 > 0x5F || a2 != 1252) )
            break;
          if ( ++v16 >= c )
            goto LABEL_48;
        }
      }
      else
      {
LABEL_48:
        if ( v16 == c )
        {
          a1 = 2;
          goto LABEL_13;
        }
      }
    }
    if ( a11 || !a1 )
    {
      if ( CW32System::_dwPlatformId == 1 && ((v25 = CW32System::_syslcid & 0x3FF, v25 == 18) || v25 == 4 || v25 == 17)
        || a11 )
      {
        ReExtTextOutW(a3, a4, y, options, lprect, lpWideCharStr, c, lpDx, 0);
      }
      else
      {
        ExtTextOutW(a3, a4, y, options, lprect, lpWideCharStr, c, lpDx);
      }
      goto LABEL_8;
    }
    if ( a1 == 1 && a2 - 932 <= 0x12 )
    {
      if ( CW32System::_dwPlatformId == 2 && (v23 = CW32System::_syslcid & 0x3FF, v23 != 18) && v23 != 4 && v23 != 17
        || CW32System::_dwPlatformId == 1 && !CW32System::OnWin95() )
      {
        ReExtTextOutW(a3, a4, y, options, lprect, lpWideCharStr, c, lpDx, a2);
LABEL_8:
        if ( v39 )
        {
          SelectObject(a3, h);
          DeleteObject(ho);
        }
        return;
      }
    }
LABEL_13:
    v50 = 256;
    v49 = v48;
    v17 = c;
    v47 = 256;
    lpMem = v45;
    if ( a1 != 2 )
      v17 = 2 * c;
    cbMultiByte = v17;
    Buf = CTempCharBuf::GetBuf((CTempCharBuf *)v48, v17);
    lpString = Buf;
    if ( !Buf )
    {
      v24 = lpMem;
      if ( lpMem != v45 )
LABEL_22:
        CW32System::FreePv(v24);
LABEL_23:
      if ( v49 != v48 )
        CW32System::FreePv(v49);
      goto LABEL_8;
    }
    if ( a1 == 1 )
    {
      v19 = CodePage;
      CodePagea = WideCharToMultiByte(CodePage, 0, lpWideCharStr, c, Buf, cbMultiByte, 0, 0);
      v20 = CodePagea;
      if ( !CodePagea )
      {
        memset(&v43, 0, sizeof(v43));
        if ( !(unsigned int)CW32System::GetTextMetrics(a3, &v43)
          || v43.tmCharSet == 1
          || (unsigned int)CW32System::GetCodePage(v43.tmCharSet) == v19 )
        {
          v19 = 1252;
        }
        else
        {
          v19 = CW32System::GetCodePage(v21);
        }
        v20 = WideCharToMultiByte(v19, 0, lpWideCharStr, c, Buf, cbMultiByte, 0, 0);
        CodePagea = v20;
      }
      if ( v20 > 0 )
      {
        if ( lpDx )
        {
          v27 = (INT *)CTempBuf::GetBuf((CTempBuf *)v45, 4 * v20);
          if ( v27 )
          {
            v28 = (unsigned __int8 *)Buf;
            v29 = v27;
            v30 = CodePagea;
            do
            {
              TrailBytesCount = CW32System::GetTrailBytesCount(*v28, v19);
              *v29 = *v15;
              if ( TrailBytesCount )
              {
                ++v33;
                v29[1] = 0;
                --v30;
                v34 = 8;
              }
              else
              {
                v34 = 4;
              }
              ++v15;
              --v30;
              v28 = (unsigned __int8 *)(v33 + 1);
              v29 = (INT *)((char *)v29 + v34);
            }
            while ( v30 > 0 );
            v20 = CodePagea;
            lpString = Buf;
LABEL_35:
            ExtTextOutA(a3, a4, y, options, lprect, lpString, v20, v32);
            v24 = lpMem;
            if ( lpMem != v45 )
              goto LABEL_22;
            goto LABEL_23;
          }
          v20 = CodePagea;
          lpString = Buf;
        }
        else
        {
          lpString = Buf;
        }
LABEL_73:
        v32 = lpDx;
        goto LABEL_35;
      }
      lpString = Buf;
      if ( v20 )
        goto LABEL_73;
    }
    v20 = c;
    if ( c )
    {
      do
      {
        v35 = (_DWORD)v12 == 1;
        v12 = (unsigned int)(v12 - 1);
        lpString[v12] = lpWideCharStr[v12];
      }
      while ( !v35 );
    }
    goto LABEL_73;
  }
}

```

## disassembly

```asm
0x180021ef0  mov     [rsp-8+arg_0], rbx
0x180021ef5  push    rbp
0x180021ef6  push    rsi
0x180021ef7  push    rdi
0x180021ef8  push    r12
0x180021efa  push    r13
0x180021efc  push    r14
0x180021efe  push    r15
0x180021f00  lea     rbp, [rsp-250h]
0x180021f08  sub     rsp, 350h
0x180021f0f  mov     rax, cs:__security_cookie
0x180021f16  xor     rax, rsp
0x180021f19  mov     [rbp+280h+var_40], rax
0x180021f20  mov     rbx, [rbp+280h+lpWideCharStr]
0x180021f27  mov     esi, r9d
0x180021f2a  mov     r15d, [rbp+280h+arg_40]
0x180021f31  mov     r13, r8
0x180021f34  mov     r14, [rbp+280h+arg_30]
0x180021f3b  mov     edi, ecx
0x180021f3d  mov     r12, [rbp+280h+arg_48]
0x180021f44  mov     [rsp+380h+CodePage], edx
0x180021f48  test    rbx, rbx
0x180021f4b  jz      loc_180021FD3
0x180021f51  xor     r8d, r8d
0x180021f54  mov     eax, 20ACh
0x180021f59  mov     [rsp+380h+var_320], r8d
0x180021f5e  mov     [rsp+380h+ho], r8
0x180021f63  mov     [rsp+380h+h], r8
0x180021f68  cmp     [rbx], ax
0x180021f6b  jz      loc_180022284
0x180021f71  mov     ecx, cs:?_dwPlatformId@CW32System@@0KA; ulong CW32System::_dwPlatformId
0x180021f77  cmp     ecx, 1
0x180021f7a  jz      loc_1800222B9
0x180021f80  mov     eax, [rbp+280h+arg_50]
0x180021f86  test    eax, eax
0x180021f88  jz      short loc_180021FFD
0x180021f8a  cmp     ecx, 1
0x180021f8d  jz      loc_180022238
0x180021f93  test    eax, eax
0x180021f95  jnz     loc_18002224E
0x180021f9b  mov     r9d, [rbp+280h+options]; options
0x180021fa2  mov     edx, esi; x
0x180021fa4  mov     r8d, [rbp+280h+y]; y
0x180021fab  mov     rcx, r13; hdc
0x180021fae  mov     [rsp+380h+lpDx], r12; lpDx
0x180021fb3  mov     [rsp+380h+c], r15d; c
0x180021fb8  mov     [rsp+380h+lpString], rbx; lpString
0x180021fbd  mov     [rsp+380h+lprect], r14; lprect
0x180021fc2  call    cs:__imp_ExtTextOutW
0x180021fc8  cmp     [rsp+380h+var_320], 0
0x180021fcd  jnz     loc_180022450
0x180021fd3  mov     rcx, [rbp+280h+var_40]
0x180021fda  xor     rcx, rsp; StackCookie
0x180021fdd  call    __security_check_cookie
0x180021fe2  mov     rbx, [rsp+380h+arg_0]
0x180021fea  add     rsp, 350h
0x180021ff1  pop     r15
0x180021ff3  pop     r14
0x180021ff5  pop     r13
0x180021ff7  pop     r12
0x180021ff9  pop     rdi
0x180021ffa  pop     rsi
0x180021ffb  pop     rbp
0x180021ffc  retn
0x180021ffd  test    edi, edi
0x180021fff  jz      short loc_180021F8A
0x180022001  cmp     edi, 1
0x180022004  jnz     short loc_180022015
0x180022006  lea     eax, [rdx-3A4h]
0x18002200c  cmp     eax, 12h
0x18002200f  jbe     loc_1800222FF
0x180022015  lea     rax, [rbp+280h+var_150]
0x18002201c  mov     [rbp+280h+var_48], 100h
0x180022026  mov     [rbp+280h+var_50], rax
0x18002202d  mov     ecx, r15d
0x180022030  lea     rax, [rbp+280h+var_260]
0x180022034  mov     [rbp+280h+var_158], 100h
0x18002203e  mov     [rbp+280h+lpMem], rax
0x180022045  cmp     edi, 2
0x180022048  lea     eax, [r15+r15]
0x18002204c  cmovnz  ecx, eax
0x18002204f  mov     [rsp+380h+cbMultiByte], ecx
0x180022053  mov     edx, ecx; int
0x180022055  lea     rcx, [rbp+280h+var_150]; this
0x18002205c  call    ?GetBuf@CTempCharBuf@@QEAAPEADJ@Z; CTempCharBuf::GetBuf(long)
0x180022061  mov     [rsp+380h+var_328], rax
0x180022066  mov     r8, rax
0x180022069  test    rax, rax
0x18002206c  jz      loc_1800221DA
0x180022072  xor     r10d, r10d
0x180022075  cmp     edi, 1
0x180022078  jnz     loc_180022400
0x18002207e  mov     eax, [rsp+380h+cbMultiByte]
0x180022082  mov     r9d, r15d; cchWideChar
0x180022085  mov     edi, [rsp+380h+CodePage]
0x180022089  xor     edx, edx; dwFlags
0x18002208b  mov     [rsp+380h+lpDx], r10; lpUsedDefaultChar
0x180022090  mov     ecx, edi; CodePage
0x180022092  mov     qword ptr [rsp+380h+c], r10; lpDefaultChar
0x180022097  mov     dword ptr [rsp+380h+lpString], eax; cbMultiByte
0x18002209b  mov     [rsp+380h+lprect], r8; lpMultiByteStr
0x1800220a0  mov     r8, rbx; lpWideCharStr
0x1800220a3  call    cs:__imp_WideCharToMultiByte
0x1800220a9  mov     [rsp+380h+CodePage], eax
0x1800220ad  mov     edx, eax
0x1800220af  test    eax, eax
0x1800220b1  jnz     loc_180022363
0x1800220b7  xorps   xmm0, xmm0
0x1800220ba  lea     rdx, [rbp+280h+var_300]; struct tagTEXTMETRICW *
0x1800220be  movups  xmmword ptr [rbp+280h+var_300.tmOverhang], xmm0
0x1800220c2  mov     rcx, r13; HDC
0x1800220c5  movups  xmmword ptr [rbp+280h+var_300.tmFirstChar], xmm0
0x1800220c9  movups  xmmword ptr [rbp+280h+var_300.tmHeight], xmm0
0x1800220cd  movups  xmmword ptr [rbp+280h+var_300.tmExternalLeading], xmm0
0x1800220d1  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x1800220d6  test    eax, eax
0x1800220d8  jz      loc_180022324
0x1800220de  movzx   ecx, [rbp+280h+var_300.tmCharSet]; unsigned __int8
0x1800220e2  cmp     cl, 1
0x1800220e5  jz      loc_180022324
0x1800220eb  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800220f0  cmp     eax, edi
0x1800220f2  jz      loc_180022324
0x1800220f8  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800220fd  mov     edi, eax
0x1800220ff  jmp     loc_180022329
0x180022104  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180022109  mov     rcx, [rbp+280h+var_50]; lpMem
0x180022110  lea     rax, [rbp+280h+var_150]
0x180022117  cmp     rcx, rax
0x18002211a  jz      loc_180021FC8
0x180022120  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x180022125  jmp     loc_180021FC8
0x18002212a  mov     ecx, 0Ch; i
0x18002212f  mov     [rsp+380h+var_320], 1
0x180022137  call    cs:__imp_GetStockObject
0x18002213d  mov     rdx, rax; h
0x180022140  mov     rcx, r13; hdc
0x180022143  call    cs:__imp_SelectObject
0x180022149  xor     edx, edx; Val
0x18002214b  lea     rcx, [rbp+280h+var_2C0]; void *
0x18002214f  mov     r8d, 5Ch ; '\'; Size
0x180022155  mov     [rsp+380h+h], rax
0x18002215a  call    memset_0
0x18002215f  mov     rcx, [rsp+380h+h]; void *
0x180022164  lea     r8, [rbp+280h+var_2C0]; void *
0x180022168  mov     edx, 5Ch ; '\'; int
0x18002216d  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x180022172  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180022179  jz      loc_1800222B0
0x18002217f  mov     [rbp+280h+var_2C0.lfOutPrecision], 9
0x180022183  lea     rcx, [rbp+280h+var_2C0]; struct tagLOGFONTW *
0x180022187  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x18002218c  mov     rdx, rax; h
0x18002218f  mov     [rsp+380h+ho], rax
0x180022194  mov     rcx, r13; hdc
0x180022197  call    cs:__imp_SelectObject
0x18002219d  mov     edx, [rsp+380h+CodePage]
0x1800221a1  xor     r8d, r8d
0x1800221a4  jmp     loc_180021F71
0x1800221a9  movzx   eax, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x1800221b0  and     eax, 3FFh
0x1800221b5  cmp     eax, 12h
0x1800221b8  jnz     loc_18002230D
0x1800221be  cmp     ecx, 1
0x1800221c1  jnz     loc_180022015
0x1800221c7  call    ?OnWin95@CW32System@@SA_NXZ; CW32System::OnWin95(void)
0x1800221cc  test    al, al
0x1800221ce  jnz     loc_180022015
0x1800221d4  mov     [rsp+380h+var_340], edx
0x1800221d8  jmp     short loc_180022253
0x1800221da  mov     rcx, [rbp+280h+lpMem]; lpMem
0x1800221e1  lea     rax, [rbp+280h+var_260]
0x1800221e5  cmp     rcx, rax
0x1800221e8  jz      loc_180022109
0x1800221ee  jmp     loc_180022104
0x1800221f3  mov     r9d, [rbp+280h+options]; options
0x1800221fa  mov     rcx, r13; hdc
0x1800221fd  mov     [rsp+380h+lpDx], r10; lpDx
0x180022202  mov     [rsp+380h+c], edx; c
0x180022206  mov     edx, esi; x
0x180022208  mov     [rsp+380h+lpString], r8; lpString
0x18002220d  mov     r8d, [rbp+280h+y]; y
0x180022214  mov     [rsp+380h+lprect], r14; lprect
0x180022219  call    cs:__imp_ExtTextOutA
0x18002221f  mov     rcx, [rbp+280h+lpMem]
0x180022226  lea     rax, [rbp+280h+var_260]
0x18002222a  cmp     rcx, rax
0x18002222d  jz      loc_180022109
0x180022233  jmp     loc_180022104
0x180022238  movzx   ecx, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x18002223f  and     ecx, 3FFh
0x180022245  cmp     ecx, 12h
0x180022248  jnz     loc_180022439
0x18002224e  mov     [rsp+380h+var_340], r8d; unsigned int
0x180022253  mov     r9d, [rbp+280h+options]; unsigned int
0x18002225a  mov     edx, esi; int
0x18002225c  mov     r8d, [rbp+280h+y]; int
0x180022263  mov     rcx, r13; HDC
0x180022266  mov     [rsp+380h+lpDx], r12; int *
0x18002226b  mov     [rsp+380h+c], r15d; unsigned int
0x180022270  mov     [rsp+380h+lpString], rbx; unsigned __int16 *
0x180022275  mov     [rsp+380h+lprect], r14; struct tagRECT *
0x18002227a  call    ?ReExtTextOutW@@YAHPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBHI@Z; ReExtTextOutW(HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *,uint)
0x18002227f  jmp     loc_180021FC8
0x180022284  mov     edx, 2; index
0x180022289  mov     rcx, r13; hdc
0x18002228c  call    cs:__imp_GetDeviceCaps
0x180022292  cmp     eax, 1
0x180022295  jnz     loc_18002212A
0x18002229b  mov     rcx, r13; hdc
0x18002229e  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x1800222a3  test    eax, eax
0x1800222a5  jz      loc_18002219D
0x1800222ab  jmp     loc_18002212A
0x1800222b0  mov     [rbp+280h+var_2C0.lfOutPrecision], 7
0x1800222b4  jmp     loc_180022183
0x1800222b9  test    r15d, r15d
0x1800222bc  jz      short loc_1800222E8
0x1800222be  mov     eax, r8d
0x1800222c1  movzx   r9d, word ptr [rbx+rax*2]
0x1800222c6  cmp     r9d, 7Fh
0x1800222ca  jbe     short loc_1800222E0
0x1800222cc  lea     eax, [r9-0A0h]
0x1800222d3  cmp     eax, 5Fh ; '_'
0x1800222d6  ja      short loc_1800222F7
0x1800222d8  cmp     edx, 4E4h
0x1800222de  jnz     short loc_1800222F7
0x1800222e0  inc     r8d
0x1800222e3  cmp     r8d, r15d
0x1800222e6  jb      short loc_1800222BE
0x1800222e8  cmp     r8d, r15d
0x1800222eb  jnz     short loc_1800222F7
0x1800222ed  mov     edi, 2
0x1800222f2  jmp     loc_180022015
0x1800222f7  xor     r8d, r8d
0x1800222fa  jmp     loc_180021F80
0x1800222ff  cmp     ecx, 2
0x180022302  jnz     loc_1800221BE
0x180022308  jmp     loc_1800221A9
0x18002230d  cmp     eax, 4
0x180022310  jz      loc_1800221BE
0x180022316  cmp     eax, 11h
0x180022319  jnz     loc_1800221D4
0x18002231f  jmp     loc_1800221BE
0x180022324  mov     edi, 4E4h
0x180022329  mov     eax, [rsp+380h+cbMultiByte]
0x18002232d  mov     r9d, r15d; cchWideChar
0x180022330  mov     [rsp+380h+lpDx], 0; lpUsedDefaultChar
0x180022339  mov     r8, rbx; lpWideCharStr
0x18002233c  mov     qword ptr [rsp+380h+c], 0; lpDefaultChar
0x180022345  xor     edx, edx; dwFlags
0x180022347  mov     dword ptr [rsp+380h+lpString], eax; cbMultiByte
0x18002234b  mov     ecx, edi; CodePage
0x18002234d  mov     rax, [rsp+380h+var_328]
0x180022352  mov     [rsp+380h+lprect], rax; lpMultiByteStr
0x180022357  call    cs:__imp_WideCharToMultiByte
0x18002235d  mov     edx, eax
0x18002235f  mov     [rsp+380h+CodePage], eax
0x180022363  test    edx, edx
0x180022365  jle     loc_1800223F4
0x18002236b  test    r12, r12
0x18002236e  jz      loc_18002242C
0x180022374  lea     edx, ds:0[rdx*4]; int
0x18002237b  lea     rcx, [rbp+280h+var_260]; this
0x18002237f  call    ?GetBuf@CTempBuf@@QEAAPEAXJ@Z; CTempBuf::GetBuf(long)
0x180022384  mov     r10, rax
0x180022387  test    rax, rax
0x18002238a  jz      loc_180022419
0x180022390  mov     r11, [rsp+380h+var_328]
0x180022395  mov     r15, rax
0x180022398  mov     ebx, [rsp+380h+CodePage]
0x18002239c  movzx   ecx, byte ptr [r11]; unsigned __int8
0x1800223a0  lea     rax, [r12+4]
0x1800223a5  mov     edx, edi; unsigned int
0x1800223a7  mov     qword ptr [rsp+380h+cbMultiByte], rax
0x1800223ac  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x1800223b1  mov     ecx, [r12]
0x1800223b5  mov     [r15], ecx
0x1800223b8  test    eax, eax
0x1800223ba  jz      short loc_1800223D0
0x1800223bc  inc     r11
0x1800223bf  mov     dword ptr [r15+4], 0
0x1800223c7  dec     ebx
0x1800223c9  mov     eax, 8
0x1800223ce  jmp     short loc_1800223D5
0x1800223d0  mov     eax, 4
0x1800223d5  mov     r12, qword ptr [rsp+380h+cbMultiByte]
0x1800223da  dec     ebx
0x1800223dc  inc     r11
0x1800223df  add     r15, rax
0x1800223e2  test    ebx, ebx
0x1800223e4  jg      short loc_18002239C
0x1800223e6  mov     edx, [rsp+380h+CodePage]
0x1800223ea  mov     r8, [rsp+380h+var_328]
0x1800223ef  jmp     loc_1800221F3
0x1800223f4  mov     r8, [rsp+380h+var_328]
0x1800223f9  xor     r10d, r10d
0x1800223fc  test    edx, edx
0x1800223fe  jnz     short loc_180022431
  ... truncated ...
```
