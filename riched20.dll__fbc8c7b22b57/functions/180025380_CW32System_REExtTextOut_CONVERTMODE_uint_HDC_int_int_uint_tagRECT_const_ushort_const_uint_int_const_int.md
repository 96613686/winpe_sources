# CW32System::REExtTextOut(CONVERTMODE,uint,HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *,int)

- ea: `0x180025380`
- end: `0x18002593b`
- name: `?REExtTextOut@CW32System@@SAXW4CONVERTMODE@@IPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBHH@Z`
- size: `1467`
- prototype: `static void __high(enum CONVERTMODE, unsigned int, HDC, int, int, unsigned int, const struct tagRECT *, const unsigned __int16 *, unsigned int, const int *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x180024580`
- `0x18002519c`

## callees

- `0x18001c1d4`
- `0x18001e170`
- `0x180025380`
- `0x18002720c`
- `0x180027414`
- `0x18002e7e4`
- `0x18002edbc`
- `0x180041a84`
- `0x1800486b0`
- `0x180090024`
- `0x180090bf4`
- `0x180092ad4`
- `0x180093bca`
- `0x180093c00`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18002553a`
- `KERNEL32!WideCharToMultiByte` at `0x180025812`
- `KERNEL32!WideCharToMultiByte` at `0x18002553a`
- `KERNEL32!WideCharToMultiByte` at `0x180025812`
- `GDI32!ExtTextOutW` at `0x180025452`
- `GDI32!ExtTextOutW` at `0x180025452`
- `GDI32!GetDeviceCaps` at `0x180025741`
- `GDI32!GetDeviceCaps` at `0x180025741`
- `GDI32!DeleteObject` at `0x18002592a`
- `GDI32!DeleteObject` at `0x18002592a`
- `GDI32!GetStockObject` at `0x1800255d4`
- `GDI32!GetStockObject` at `0x1800255d4`
- `GDI32!SelectObject` at `0x1800255e6`
- `GDI32!SelectObject` at `0x180025640`
- `GDI32!SelectObject` at `0x180025919`
- `GDI32!SelectObject` at `0x1800255e6`
- `GDI32!SelectObject` at `0x180025640`
- `GDI32!SelectObject` at `0x180025919`
- `GDI32!ExtTextOutA` at `0x1800256c8`
- `GDI32!ExtTextOutA` at `0x1800256c8`

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
0x180025380  mov     [rsp-8+arg_0], rbx
0x180025385  push    rbp
0x180025386  push    rsi
0x180025387  push    rdi
0x180025388  push    r12
0x18002538a  push    r13
0x18002538c  push    r14
0x18002538e  push    r15
0x180025390  lea     rbp, [rsp-250h]
0x180025398  sub     rsp, 350h
0x18002539f  mov     rax, cs:__security_cookie
0x1800253a6  xor     rax, rsp
0x1800253a9  mov     [rbp+280h+var_40], rax
0x1800253b0  mov     rbx, [rbp+280h+lpWideCharStr]
0x1800253b7  mov     esi, r9d
0x1800253ba  mov     r15d, [rbp+280h+arg_40]
0x1800253c1  mov     r13, r8
0x1800253c4  mov     r14, [rbp+280h+arg_30]
0x1800253cb  mov     edi, ecx
0x1800253cd  mov     r12, [rbp+280h+arg_48]
0x1800253d4  mov     [rsp+380h+CodePage], edx
0x1800253d8  test    rbx, rbx
0x1800253db  jz      loc_180025469
0x1800253e1  xor     r8d, r8d
0x1800253e4  mov     eax, 20ACh
0x1800253e9  mov     [rsp+380h+var_320], r8d
0x1800253ee  mov     [rsp+380h+ho], r8
0x1800253f3  mov     [rsp+380h+h], r8
0x1800253f8  cmp     [rbx], ax
0x1800253fb  jz      loc_180025739
0x180025401  mov     ecx, cs:?_dwPlatformId@CW32System@@0KA; ulong CW32System::_dwPlatformId
0x180025407  cmp     ecx, 1
0x18002540a  jz      loc_180025774
0x180025410  mov     eax, [rbp+280h+arg_50]
0x180025416  test    eax, eax
0x180025418  jz      short loc_180025494
0x18002541a  cmp     ecx, 1
0x18002541d  jz      loc_1800256ED
0x180025423  test    eax, eax
0x180025425  jnz     loc_180025703
0x18002542b  mov     r9d, [rbp+280h+options]; options
0x180025432  mov     edx, esi; x
0x180025434  mov     r8d, [rbp+280h+y]; y
0x18002543b  mov     rcx, r13; hdc
0x18002543e  mov     [rsp+380h+lpDx], r12; lpDx
0x180025443  mov     [rsp+380h+c], r15d; c
0x180025448  mov     [rsp+380h+lpString], rbx; lpString
0x18002544d  mov     [rsp+380h+lprect], r14; lprect
0x180025452  call    cs:__imp_ExtTextOutW
0x180025459  nop     dword ptr [rax+rax+00h]
0x18002545e  cmp     [rsp+380h+var_320], 0
0x180025463  jnz     loc_180025911
0x180025469  mov     rcx, [rbp+280h+var_40]
0x180025470  xor     rcx, rsp; StackCookie
0x180025473  call    __security_check_cookie
0x180025478  mov     rbx, [rsp+380h+arg_0]
0x180025480  add     rsp, 350h
0x180025487  pop     r15
0x180025489  pop     r14
0x18002548b  pop     r13
0x18002548d  pop     r12
0x18002548f  pop     rdi
0x180025490  pop     rsi
0x180025491  pop     rbp
0x180025492  retn
0x180025494  test    edi, edi
0x180025496  jz      short loc_18002541A
0x180025498  cmp     edi, 1
0x18002549b  jnz     short loc_1800254AC
0x18002549d  lea     eax, [rdx-3A4h]
0x1800254a3  cmp     eax, 12h
0x1800254a6  jbe     loc_1800257BA
0x1800254ac  lea     rax, [rbp+280h+var_150]
0x1800254b3  mov     [rbp+280h+var_48], 100h
0x1800254bd  mov     [rbp+280h+var_50], rax
0x1800254c4  mov     ecx, r15d
0x1800254c7  lea     rax, [rbp+280h+var_260]
0x1800254cb  mov     [rbp+280h+var_158], 100h
0x1800254d5  mov     [rbp+280h+lpMem], rax
0x1800254dc  cmp     edi, 2
0x1800254df  lea     eax, [r15+r15]
0x1800254e3  cmovnz  ecx, eax
0x1800254e6  mov     [rsp+380h+cbMultiByte], ecx
0x1800254ea  mov     edx, ecx; int
0x1800254ec  lea     rcx, [rbp+280h+var_150]; this
0x1800254f3  call    ?GetBuf@CTempCharBuf@@QEAAPEADJ@Z; CTempCharBuf::GetBuf(long)
0x1800254f8  mov     [rsp+380h+var_328], rax
0x1800254fd  mov     r8, rax
0x180025500  test    rax, rax
0x180025503  jz      loc_180025689
0x180025509  xor     r10d, r10d
0x18002550c  cmp     edi, 1
0x18002550f  jnz     loc_1800258C1
0x180025515  mov     eax, [rsp+380h+cbMultiByte]
0x180025519  mov     r9d, r15d; cchWideChar
0x18002551c  mov     edi, [rsp+380h+CodePage]
0x180025520  xor     edx, edx; dwFlags
0x180025522  mov     [rsp+380h+lpDx], r10; lpUsedDefaultChar
0x180025527  mov     ecx, edi; CodePage
0x180025529  mov     qword ptr [rsp+380h+c], r10; lpDefaultChar
0x18002552e  mov     dword ptr [rsp+380h+lpString], eax; cbMultiByte
0x180025532  mov     [rsp+380h+lprect], r8; lpMultiByteStr
0x180025537  mov     r8, rbx; lpWideCharStr
0x18002553a  call    cs:__imp_WideCharToMultiByte
0x180025541  nop     dword ptr [rax+rax+00h]
0x180025546  mov     [rsp+380h+CodePage], eax
0x18002554a  mov     edx, eax
0x18002554c  test    eax, eax
0x18002554e  jnz     loc_180025824
0x180025554  xorps   xmm0, xmm0
0x180025557  lea     rdx, [rbp+280h+var_300]; struct tagTEXTMETRICW *
0x18002555b  movups  xmmword ptr [rbp+280h+var_300.tmOverhang], xmm0
0x18002555f  mov     rcx, r13; HDC
0x180025562  movups  xmmword ptr [rbp+280h+var_300.tmFirstChar], xmm0
0x180025566  movups  xmmword ptr [rbp+280h+var_300.tmHeight], xmm0
0x18002556a  movups  xmmword ptr [rbp+280h+var_300.tmExternalLeading], xmm0
0x18002556e  call    ?GetTextMetrics@CW32System@@SAHPEAUHDC__@@PEAUtagTEXTMETRICW@@@Z; CW32System::GetTextMetrics(HDC__ *,tagTEXTMETRICW *)
0x180025573  test    eax, eax
0x180025575  jz      loc_1800257DF
0x18002557b  movzx   ecx, [rbp+280h+var_300.tmCharSet]; unsigned __int8
0x18002557f  cmp     cl, 1
0x180025582  jz      loc_1800257DF
0x180025588  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x18002558d  cmp     eax, edi
0x18002558f  jz      loc_1800257DF
0x180025595  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x18002559a  mov     edi, eax
0x18002559c  jmp     loc_1800257E4
0x1800255a1  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x1800255a6  mov     rcx, [rbp+280h+var_50]; lpMem
0x1800255ad  lea     rax, [rbp+280h+var_150]
0x1800255b4  cmp     rcx, rax
0x1800255b7  jz      loc_18002545E
0x1800255bd  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x1800255c2  jmp     loc_18002545E
0x1800255c7  mov     ecx, 0Ch; i
0x1800255cc  mov     [rsp+380h+var_320], 1
0x1800255d4  call    cs:__imp_GetStockObject
0x1800255db  nop     dword ptr [rax+rax+00h]
0x1800255e0  mov     rdx, rax; h
0x1800255e3  mov     rcx, r13; hdc
0x1800255e6  call    cs:__imp_SelectObject
0x1800255ed  nop     dword ptr [rax+rax+00h]
0x1800255f2  xor     edx, edx; Val
0x1800255f4  lea     rcx, [rbp+280h+var_2C0]; void *
0x1800255f8  mov     r8d, 5Ch ; '\'; Size
0x1800255fe  mov     [rsp+380h+h], rax
0x180025603  call    memset_0
0x180025608  mov     rcx, [rsp+380h+h]; void *
0x18002560d  lea     r8, [rbp+280h+var_2C0]; void *
0x180025611  mov     edx, 5Ch ; '\'; int
0x180025616  call    ?GetObjectW@CW32System@@SAHPEAXH0@Z; CW32System::GetObjectW(void *,int,void *)
0x18002561b  cmp     cs:?_dwPlatformId@CW32System@@0KA, 1; ulong CW32System::_dwPlatformId
0x180025622  jz      loc_18002576B
0x180025628  mov     [rbp+280h+var_2C0.lfOutPrecision], 9
0x18002562c  lea     rcx, [rbp+280h+var_2C0]; struct tagLOGFONTW *
0x180025630  call    ?CreateFontIndirect@CW32System@@SAPEAUHFONT__@@PEBUtagLOGFONTW@@@Z; CW32System::CreateFontIndirect(tagLOGFONTW const *)
0x180025635  mov     rdx, rax; h
0x180025638  mov     [rsp+380h+ho], rax
0x18002563d  mov     rcx, r13; hdc
0x180025640  call    cs:__imp_SelectObject
0x180025647  nop     dword ptr [rax+rax+00h]
0x18002564c  mov     edx, [rsp+380h+CodePage]
0x180025650  xor     r8d, r8d
0x180025653  jmp     loc_180025401
0x180025658  movzx   eax, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x18002565f  and     eax, 3FFh
0x180025664  cmp     eax, 12h
0x180025667  jnz     loc_1800257C8
0x18002566d  cmp     ecx, 1
0x180025670  jnz     loc_1800254AC
0x180025676  call    ?OnWin95@CW32System@@SA_NXZ; CW32System::OnWin95(void)
0x18002567b  test    al, al
0x18002567d  jnz     loc_1800254AC
0x180025683  mov     [rsp+380h+var_340], edx
0x180025687  jmp     short loc_180025708
0x180025689  mov     rcx, [rbp+280h+lpMem]; lpMem
0x180025690  lea     rax, [rbp+280h+var_260]
0x180025694  cmp     rcx, rax
0x180025697  jz      loc_1800255A6
0x18002569d  jmp     loc_1800255A1
0x1800256a2  mov     r9d, [rbp+280h+options]; options
0x1800256a9  mov     rcx, r13; hdc
0x1800256ac  mov     [rsp+380h+lpDx], r10; lpDx
0x1800256b1  mov     [rsp+380h+c], edx; c
0x1800256b5  mov     edx, esi; x
0x1800256b7  mov     [rsp+380h+lpString], r8; lpString
0x1800256bc  mov     r8d, [rbp+280h+y]; y
0x1800256c3  mov     [rsp+380h+lprect], r14; lprect
0x1800256c8  call    cs:__imp_ExtTextOutA
0x1800256cf  nop     dword ptr [rax+rax+00h]
0x1800256d4  mov     rcx, [rbp+280h+lpMem]
0x1800256db  lea     rax, [rbp+280h+var_260]
0x1800256df  cmp     rcx, rax
0x1800256e2  jz      loc_1800255A6
0x1800256e8  jmp     loc_1800255A1
0x1800256ed  movzx   ecx, word ptr cs:?_syslcid@CW32System@@0KA; ulong CW32System::_syslcid
0x1800256f4  and     ecx, 3FFh
0x1800256fa  cmp     ecx, 12h
0x1800256fd  jnz     loc_1800258FA
0x180025703  mov     [rsp+380h+var_340], r8d; unsigned int
0x180025708  mov     r9d, [rbp+280h+options]; unsigned int
0x18002570f  mov     edx, esi; int
0x180025711  mov     r8d, [rbp+280h+y]; int
0x180025718  mov     rcx, r13; HDC
0x18002571b  mov     [rsp+380h+lpDx], r12; int *
0x180025720  mov     [rsp+380h+c], r15d; unsigned int
0x180025725  mov     [rsp+380h+lpString], rbx; unsigned __int16 *
0x18002572a  mov     [rsp+380h+lprect], r14; struct tagRECT *
0x18002572f  call    ?ReExtTextOutW@@YAHPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBHI@Z; ReExtTextOutW(HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *,uint)
0x180025734  jmp     loc_18002545E
0x180025739  mov     edx, 2; index
0x18002573e  mov     rcx, r13; hdc
0x180025741  call    cs:__imp_GetDeviceCaps
0x180025748  nop     dword ptr [rax+rax+00h]
0x18002574d  cmp     eax, 1
0x180025750  jnz     loc_1800255C7
0x180025756  mov     rcx, r13; hdc
0x180025759  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x18002575e  test    eax, eax
0x180025760  jz      loc_18002564C
0x180025766  jmp     loc_1800255C7
0x18002576b  mov     [rbp+280h+var_2C0.lfOutPrecision], 7
0x18002576f  jmp     loc_18002562C
0x180025774  test    r15d, r15d
0x180025777  jz      short loc_1800257A3
0x180025779  mov     eax, r8d
0x18002577c  movzx   r9d, word ptr [rbx+rax*2]
0x180025781  cmp     r9d, 7Fh
0x180025785  jbe     short loc_18002579B
0x180025787  lea     eax, [r9-0A0h]
0x18002578e  cmp     eax, 5Fh ; '_'
0x180025791  ja      short loc_1800257B2
0x180025793  cmp     edx, 4E4h
0x180025799  jnz     short loc_1800257B2
0x18002579b  inc     r8d
0x18002579e  cmp     r8d, r15d
0x1800257a1  jb      short loc_180025779
0x1800257a3  cmp     r8d, r15d
0x1800257a6  jnz     short loc_1800257B2
0x1800257a8  mov     edi, 2
0x1800257ad  jmp     loc_1800254AC
0x1800257b2  xor     r8d, r8d
0x1800257b5  jmp     loc_180025410
0x1800257ba  cmp     ecx, 2
0x1800257bd  jnz     loc_18002566D
0x1800257c3  jmp     loc_180025658
0x1800257c8  cmp     eax, 4
0x1800257cb  jz      loc_18002566D
0x1800257d1  cmp     eax, 11h
0x1800257d4  jnz     loc_180025683
0x1800257da  jmp     loc_18002566D
0x1800257df  mov     edi, 4E4h
0x1800257e4  mov     eax, [rsp+380h+cbMultiByte]
0x1800257e8  mov     r9d, r15d; cchWideChar
0x1800257eb  mov     [rsp+380h+lpDx], 0; lpUsedDefaultChar
0x1800257f4  mov     r8, rbx; lpWideCharStr
0x1800257f7  mov     qword ptr [rsp+380h+c], 0; lpDefaultChar
0x180025800  xor     edx, edx; dwFlags
0x180025802  mov     dword ptr [rsp+380h+lpString], eax; cbMultiByte
0x180025806  mov     ecx, edi; CodePage
0x180025808  mov     rax, [rsp+380h+var_328]
0x18002580d  mov     [rsp+380h+lprect], rax; lpMultiByteStr
0x180025812  call    cs:__imp_WideCharToMultiByte
0x180025819  nop     dword ptr [rax+rax+00h]
0x18002581e  mov     edx, eax
0x180025820  mov     [rsp+380h+CodePage], eax
0x180025824  test    edx, edx
0x180025826  jle     loc_1800258B5
0x18002582c  test    r12, r12
0x18002582f  jz      loc_1800258ED
0x180025835  lea     edx, ds:0[rdx*4]; int
0x18002583c  lea     rcx, [rbp+280h+var_260]; this
0x180025840  call    ?GetBuf@CTempBuf@@QEAAPEAXJ@Z; CTempBuf::GetBuf(long)
0x180025845  mov     r10, rax
0x180025848  test    rax, rax
0x18002584b  jz      loc_1800258DA
0x180025851  mov     r11, [rsp+380h+var_328]
0x180025856  mov     r15, rax
0x180025859  mov     ebx, [rsp+380h+CodePage]
0x18002585d  movzx   ecx, byte ptr [r11]; unsigned __int8
0x180025861  lea     rax, [r12+4]
0x180025866  mov     edx, edi; unsigned int
0x180025868  mov     qword ptr [rsp+380h+cbMultiByte], rax
0x18002586d  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x180025872  mov     ecx, [r12]
0x180025876  mov     [r15], ecx
0x180025879  test    eax, eax
0x18002587b  jz      short loc_180025891
0x18002587d  inc     r11
0x180025880  mov     dword ptr [r15+4], 0
0x180025888  dec     ebx
0x18002588a  mov     eax, 8
0x18002588f  jmp     short loc_180025896
0x180025891  mov     eax, 4
0x180025896  mov     r12, qword ptr [rsp+380h+cbMultiByte]
0x18002589b  dec     ebx
0x18002589d  inc     r11
0x1800258a0  add     r15, rax
0x1800258a3  test    ebx, ebx
  ... truncated ...
```
