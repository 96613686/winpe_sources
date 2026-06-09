# CHtmlHelpControl::OnDraw(ulong,HDC__ *,_RECTL const *,_RECTL const *,HDC__ *,int)

- ea: `0x1800325e0`
- end: `0x180032858`
- name: `?OnDraw@CHtmlHelpControl@@EEAAJKPEAUHDC__@@PEBU_RECTL@@10H@Z`
- size: `632`
- prototype: `__int64 __usercall@<rax>(CHtmlHelpControl *__hidden this@<rcx>, unsigned int@<edx>, HDC@<r8>, const struct _RECTL *@<r9>, const struct _RECTL *, HDC, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005a4c`
- `0x18002396c`
- `0x180024270`
- `0x1800325e0`
- `0x180048fe8`
- `0x180064b88`
- `0x1800661d0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180032710`
- `KERNEL32!lstrlenW` at `0x180032710`
- `USER32!FillRect` at `0x18003266c`
- `USER32!FillRect` at `0x18003266c`
- `USER32!LoadBitmapA` at `0x1800327bb`
- `USER32!LoadBitmapA` at `0x1800327bb`
- `GDI32!DPtoLP` at `0x180032806`
- `GDI32!DPtoLP` at `0x180032806`
- `GDI32!DeleteObject` at `0x18003283c`
- `GDI32!DeleteObject` at `0x18003283c`
- `GDI32!GetObjectA` at `0x1800327ea`
- `GDI32!GetObjectA` at `0x1800327ea`
- `GDI32!GetStockObject` at `0x18003265d`
- `GDI32!GetStockObject` at `0x18003265d`
- `GDI32!DeleteDC` at `0x180032833`
- `GDI32!DeleteDC` at `0x180032833`
- `GDI32!CreateCompatibleDC` at `0x18003279c`
- `GDI32!CreateCompatibleDC` at `0x18003279c`
- `GDI32!SelectObject` at `0x180032700`
- `GDI32!SelectObject` at `0x180032743`
- `GDI32!SelectObject` at `0x1800327ca`
- `GDI32!SelectObject` at `0x18003282a`
- `GDI32!SelectObject` at `0x180032700`
- `GDI32!SelectObject` at `0x180032743`
- `GDI32!SelectObject` at `0x1800327ca`
- `GDI32!SelectObject` at `0x18003282a`
- `GDI32!GetDeviceCaps` at `0x18003268c`
- `GDI32!GetDeviceCaps` at `0x18003268c`

## pseudocode

```c
__int64 __fastcall CHtmlHelpControl::OnDraw(
        CHtmlHelpControl *this,
        __int64 a2,
        HDC a3,
        const RECT *a4,
        const struct _RECTL *a5)
{
  int v6; // ecx
  HBRUSH StockObject; // rax
  int DeviceCaps; // eax
  int v11; // ecx
  _WORD *v12; // rax
  char *v13; // rcx
  HFONT UserFont; // rsi
  HGDIOBJ v15; // rbx
  UINT v16; // eax
  void *v17; // rcx
  int v18; // ecx
  int v19; // ecx
  HDC CompatibleDC; // rsi
  HINSTANCE ResourceInstance; // rax
  HBITMAP BitmapA; // rdi
  HGDIOBJ v23; // rbx
  const int *v25; // [rsp+38h] [rbp-49h]
  unsigned int *v26; // [rsp+40h] [rbp-41h]
  struct tagSIZE v27; // [rsp+50h] [rbp-31h] BYREF
  _OWORD pv[6]; // [rsp+58h] [rbp-29h] BYREF
  struct tagPOINT pt; // [rsp+D0h] [rbp+4Fh] BYREF

  v6 = *((_DWORD *)this + 69);
  if ( (v6 & 1) == 0 )
  {
    LOWORD(pt.x) = 1;
    *((_DWORD *)this + 69) = v6 | 1;
    COleControl::GetAmbientProperty(this, -709, 0xBu, &pt);
    v6 = *((_DWORD *)this + 69)
       ^ ((unsigned __int8)*((_DWORD *)this + 69)
        ^ (unsigned __int8)(32 * LOBYTE(pt.x)))
       & 0x20;
    *((_DWORD *)this + 69) = v6;
  }
  if ( (v6 & 0x20) == 0 )
  {
    StockObject = (HBRUSH)GetStockObject(4);
    FillRect(a3, a4, StockObject);
    return 0;
  }
  if ( a5 )
    return 0;
  DeviceCaps = GetDeviceCaps(a3, 2);
  v11 = *((_DWORD *)this + 91);
  if ( DeviceCaps == 2 )
  {
    if ( v11 )
    {
      v12 = (_WORD *)*((_QWORD *)this + 72);
      if ( v12 )
      {
        if ( *v12 )
        {
          v13 = (char *)this + 944;
          if ( *((_BYTE *)this + 944) )
          {
            UserFont = CreateUserFont(v13, 0, a3, *((_DWORD *)this + 302));
          }
          else
          {
            pt = 0;
            CResourceCache::InitDefaultUIFont((CResourceCache *)v13, a3, (HFONT *)&pt);
            UserFont = (HFONT)pt;
          }
          v15 = SelectObject(a3, UserFont);
          v16 = lstrlenW(*((LPCWSTR *)this + 72));
          IntlExtTextOutW(a3, a4->left, a4->top, 0, 0, *((LPCWSTR *)this + 72), v16, v25, v26);
          SelectObject(a3, v15);
          v17 = UserFont;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v18 = v11 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 2 )
        {
          if ( (unsigned int)(*((_DWORD *)this + 94) + 1) <= 1 && !*((_QWORD *)this + 48) )
          {
            pt = 0;
            COleControl::SetControlSize(this, (struct tagSIZE *)&pt);
            return 0;
          }
          CompatibleDC = CreateCompatibleDC(a3);
          ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
          BitmapA = LoadBitmapA(ResourceInstance, "shortcut");
          memset(pv, 0, 32);
          v23 = SelectObject(CompatibleDC, BitmapA);
          GetObjectA(BitmapA, 32, pv);
          pt = *(struct tagPOINT *)((char *)pv + 4);
          DPtoLP(CompatibleDC, &pt, 1);
          v27 = *(struct tagSIZE *)((char *)pv + 4);
          COleControl::SetControlSize(this, &v27);
          SelectObject(CompatibleDC, v23);
          DeleteDC(CompatibleDC);
          v17 = BitmapA;
LABEL_21:
          DeleteObject(v17);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800325e0  push    rbp
0x1800325e2  push    rbx
0x1800325e3  push    rsi
0x1800325e4  push    rdi
0x1800325e5  push    r12
0x1800325e7  push    r13
0x1800325e9  push    r14
0x1800325eb  push    r15
0x1800325ed  lea     rbp, [rsp-7]
0x1800325f2  sub     rsp, 88h
0x1800325f9  mov     r14, rcx
0x1800325fc  mov     r13d, 1
0x180032602  mov     ecx, [rcx+114h]
0x180032608  mov     r15, r9
0x18003260b  mov     rdi, r8
0x18003260e  test    r13b, cl
0x180032611  jnz     short loc_180032653
0x180032613  or      ecx, r13d
0x180032616  mov     word ptr [rbp+3Fh+pt.x], r13w
0x18003261b  mov     [r14+114h], ecx
0x180032622  lea     r8d, [r13+0Ah]; unsigned __int16
0x180032626  mov     rcx, r14; this
0x180032629  lea     r9, [rbp+3Fh+pt]; void *
0x18003262d  mov     edx, 0FFFFFD3Bh; int
0x180032632  call    ?GetAmbientProperty@COleControl@@IEAAHJGPEAX@Z; COleControl::GetAmbientProperty(long,ushort,void *)
0x180032637  mov     eax, [r14+114h]
0x18003263e  movsx   ecx, word ptr [rbp+3Fh+pt.x]
0x180032642  shl     ecx, 5
0x180032645  xor     ecx, eax
0x180032647  and     ecx, 20h
0x18003264a  xor     ecx, eax
0x18003264c  mov     [r14+114h], ecx
0x180032653  test    cl, 20h
0x180032656  jnz     short loc_180032677
0x180032658  mov     ecx, 4; i
0x18003265d  call    cs:__imp_GetStockObject
0x180032663  mov     rdx, r15; lprc
0x180032666  mov     rcx, rdi; hDC
0x180032669  mov     r8, rax; hbr
0x18003266c  call    cs:__imp_FillRect
0x180032672  jmp     loc_180032842
0x180032677  xor     r12d, r12d
0x18003267a  cmp     [rbp+3Fh+arg_20], r12
0x18003267e  jnz     loc_180032842
0x180032684  lea     edx, [r12+2]; index
0x180032689  mov     rcx, rdi; hdc
0x18003268c  call    cs:__imp_GetDeviceCaps
0x180032692  mov     ecx, [r14+16Ch]
0x180032699  cmp     eax, 2
0x18003269c  jnz     loc_180032751
0x1800326a2  test    ecx, ecx
0x1800326a4  jz      loc_180032842
0x1800326aa  mov     rax, [r14+240h]
0x1800326b1  test    rax, rax
0x1800326b4  jz      loc_180032842
0x1800326ba  cmp     [rax], r12w
0x1800326be  jz      loc_180032842
0x1800326c4  lea     rcx, [r14+3B0h]; this
0x1800326cb  cmp     [rcx], r12b
0x1800326ce  jz      short loc_1800326E6
0x1800326d0  mov     r9d, [r14+4B8h]; int
0x1800326d7  mov     r8, rdi; HDC
0x1800326da  xor     edx, edx; unsigned int *
0x1800326dc  call    ?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z; CreateUserFont(char const *,ulong *,HDC__ *,int)
0x1800326e1  mov     rsi, rax
0x1800326e4  jmp     short loc_1800326FA
0x1800326e6  lea     r8, [rbp+3Fh+pt]; HFONT *
0x1800326ea  mov     qword ptr [rbp+3Fh+pt.x], r12
0x1800326ee  mov     rdx, rdi; HDC
0x1800326f1  call    ?InitDefaultUIFont@CResourceCache@@AEAAXPEAUHDC__@@PEAPEAUHFONT__@@@Z; CResourceCache::InitDefaultUIFont(HDC__ *,HFONT__ * *)
0x1800326f6  mov     rsi, qword ptr [rbp+3Fh+pt.x]
0x1800326fa  mov     rdx, rsi; h
0x1800326fd  mov     rcx, rdi; hdc
0x180032700  call    cs:__imp_SelectObject
0x180032706  mov     rcx, [r14+240h]; lpString
0x18003270d  mov     rbx, rax
0x180032710  call    cs:__imp_lstrlenW
0x180032716  mov     rcx, [r14+240h]
0x18003271d  xor     r9d, r9d; options
0x180032720  mov     r8d, [r15+4]; y
0x180032724  mov     edx, [r15]; x
0x180032727  mov     [rsp+0C0h+var_90], eax; UINT
0x18003272b  mov     [rsp+0C0h+var_98], rcx; LPCWSTR
0x180032730  mov     rcx, rdi; HDC
0x180032733  mov     [rsp+0C0h+var_A0], r12; RECT *
0x180032738  call    ?IntlExtTextOutW@@YAHPEAUHDC__@@HHIPEBUtagRECT@@PEBGIPEBHPEAI@Z; IntlExtTextOutW(HDC__ *,int,int,uint,tagRECT const *,ushort const *,uint,int const *,uint *)
0x18003273d  mov     rdx, rbx; h
0x180032740  mov     rcx, rdi; hdc
0x180032743  call    cs:__imp_SelectObject
0x180032749  mov     rcx, rsi
0x18003274c  jmp     loc_18003283C
0x180032751  sub     ecx, r13d
0x180032754  jz      loc_180032842
0x18003275a  sub     ecx, r13d
0x18003275d  jz      loc_180032842
0x180032763  cmp     ecx, 2
0x180032766  jz      loc_180032842
0x18003276c  mov     eax, [r14+178h]
0x180032773  add     eax, r13d
0x180032776  cmp     eax, r13d
0x180032779  ja      short loc_180032799
0x18003277b  cmp     [r14+180h], r12
0x180032782  jnz     short loc_180032799
0x180032784  lea     rdx, [rbp+3Fh+pt]; struct tagSIZE *
0x180032788  mov     qword ptr [rbp+3Fh+pt.x], r12
0x18003278c  mov     rcx, r14; this
0x18003278f  call    ?SetControlSize@COleControl@@IEAAHPEAUtagSIZE@@@Z; COleControl::SetControlSize(tagSIZE *)
0x180032794  jmp     loc_180032842
0x180032799  mov     rcx, rdi; hdc
0x18003279c  call    cs:__imp_CreateCompatibleDC
0x1800327a2  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x1800327a9  mov     rsi, rax
0x1800327ac  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x1800327b1  mov     rcx, rax; hInstance
0x1800327b4  lea     rdx, BitmapName; "shortcut"
0x1800327bb  call    cs:__imp_LoadBitmapA
0x1800327c1  mov     rdx, rax; h
0x1800327c4  mov     rcx, rsi; hdc
0x1800327c7  mov     rdi, rax
0x1800327ca  call    cs:__imp_SelectObject
0x1800327d0  xorps   xmm0, xmm0
0x1800327d3  lea     r8, [rbp+3Fh+pv]; pv
0x1800327d7  mov     edx, 20h ; ' '; c
0x1800327dc  mov     rcx, rdi; h
0x1800327df  movups  [rbp+3Fh+pv], xmm0
0x1800327e3  mov     rbx, rax
0x1800327e6  movups  [rbp+3Fh+var_58], xmm0
0x1800327ea  call    cs:__imp_GetObjectA
0x1800327f0  mov     ecx, dword ptr [rbp+3Fh+pv+4]
0x1800327f3  lea     rdx, [rbp+3Fh+pt]; lppt
0x1800327f7  mov     [rbp+3Fh+pt.x], ecx
0x1800327fa  mov     r8d, r13d; c
0x1800327fd  mov     ecx, dword ptr [rbp+3Fh+pv+8]
0x180032800  mov     [rbp+3Fh+pt.y], ecx
0x180032803  mov     rcx, rsi; hdc
0x180032806  call    cs:__imp_DPtoLP
0x18003280c  mov     eax, dword ptr [rbp+3Fh+pv+4]
0x18003280f  lea     rdx, [rbp+3Fh+var_70]; struct tagSIZE *
0x180032813  mov     [rbp+3Fh+var_70.cx], eax
0x180032816  mov     rcx, r14; this
0x180032819  mov     eax, dword ptr [rbp+3Fh+pv+8]
0x18003281c  mov     [rbp+3Fh+var_70.cy], eax
0x18003281f  call    ?SetControlSize@COleControl@@IEAAHPEAUtagSIZE@@@Z; COleControl::SetControlSize(tagSIZE *)
0x180032824  mov     rdx, rbx; h
0x180032827  mov     rcx, rsi; hdc
0x18003282a  call    cs:__imp_SelectObject
0x180032830  mov     rcx, rsi; hdc
0x180032833  call    cs:__imp_DeleteDC
0x180032839  mov     rcx, rdi; ho
0x18003283c  call    cs:__imp_DeleteObject
0x180032842  xor     eax, eax
0x180032844  add     rsp, 88h
0x18003284b  pop     r15
0x18003284d  pop     r14
0x18003284f  pop     r13
0x180032851  pop     r12
0x180032853  pop     rdi
0x180032854  pop     rsi
0x180032855  pop     rbx
0x180032856  pop     rbp
0x180032857  retn
```
