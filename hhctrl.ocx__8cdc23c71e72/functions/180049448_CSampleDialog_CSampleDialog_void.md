# CSampleDialog::CSampleDialog(void)

- ea: `0x180049448`
- end: `0x180049636`
- name: `??0CSampleDialog@@QEAA@XZ`
- size: `494`
- prototype: `CSampleDialog *__fastcall(CSampleDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004ad98`

## callees

- `0x180005a4c`
- `0x1800095c8`
- `0x180049448`
- `0x18004cd14`
- `0x18004ce00`
- `0x18004d0bc`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetSystemDefaultLangID` at `0x180049574`
- `KERNEL32!GetSystemDefaultLangID` at `0x180049574`
- `KERNEL32!MulDiv` at `0x1800495c5`
- `KERNEL32!MulDiv` at `0x1800495c5`
- `USER32!ReleaseDC` at `0x1800494fa`
- `USER32!ReleaseDC` at `0x1800494fa`
- `USER32!GetDC` at `0x1800494d6`
- `USER32!GetDC` at `0x18004958e`
- `USER32!GetDC` at `0x1800494d6`
- `USER32!GetDC` at `0x18004958e`
- `USER32!LoadBitmapA` at `0x18004952a`
- `USER32!LoadBitmapA` at `0x180049547`
- `USER32!LoadBitmapA` at `0x18004952a`
- `USER32!LoadBitmapA` at `0x180049547`
- `GDI32!DeleteObject` at `0x180049565`
- `GDI32!DeleteObject` at `0x18004956e`
- `GDI32!DeleteObject` at `0x180049565`
- `GDI32!DeleteObject` at `0x18004956e`
- `GDI32!GetDeviceCaps` at `0x1800495b4`
- `GDI32!GetDeviceCaps` at `0x1800495b4`
- `GDI32!GetTextMetricsA` at `0x1800494e6`
- `GDI32!GetTextMetricsA` at `0x1800494e6`
- `GDI32!CreateFontIndirectA` at `0x180049602`
- `GDI32!CreateFontIndirectA` at `0x180049602`

## pseudocode

```c
CSampleDialog *__fastcall CSampleDialog::CSampleDialog(CSampleDialog *this)
{
  HDC DC; // rbx
  __int64 v3; // rax
  HINSTANCE ResourceInstance; // rax
  HBITMAP BitmapA; // rdi
  HINSTANCE v6; // rax
  HBITMAP v7; // rbx
  HDC v8; // rax
  int DeviceCaps; // eax
  LOGFONTA lf; // [rsp+30h] [rbp-39h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+70h] [rbp+7h] BYREF

  *((_DWORD *)this + 551) = 1;
  *((_BYTE *)this + 1688) = 0;
  *((_BYTE *)this + 2208) = 0;
  *((_BYTE *)this + 4292) = 0;
  *((_BYTE *)this + 1164) = 0;
  *((_BYTE *)this + 620) = 0;
  *((_QWORD *)this + 614) = 0;
  *((_QWORD *)this + 210) = 0;
  *((_DWORD *)this + 550) = 0;
  *((_DWORD *)this + 419) = 0;
  memset(&tm, 0, sizeof(tm));
  DC = GetDC(0);
  GetTextMetricsA(DC, &tm);
  *((_DWORD *)this + 290) = tm.tmMaxCharWidth;
  ReleaseDC(0, DC);
  IsolationAwareInitCommonControls();
  v3 = IsolationAwareImageList_Create();
  *((_QWORD *)this + 613) = v3;
  if ( v3 )
  {
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    BitmapA = LoadBitmapA(ResourceInstance, (LPCSTR)0x138);
    v6 = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    v7 = LoadBitmapA(v6, (LPCSTR)0x139);
    IsolationAwareImageList_Add(*((_QWORD *)this + 613), BitmapA, v7);
    DeleteObject(BitmapA);
    DeleteObject(v7);
  }
  if ( (GetSystemDefaultLangID() & 0x3FF) == 0x11 )
  {
    v8 = GetDC(0);
    if ( v8 )
    {
      memset(&lf.lfWeight, 0, 44);
      DeviceCaps = GetDeviceCaps(v8, 90);
      lf.lfHeight = MulDiv(-9, DeviceCaps, 72);
      *(_DWORD *)&lf.lfItalic = 0x80000000;
      *(__m128i *)&lf.lfWidth = _mm_load_si128((const __m128i *)&_xmm);
      *(_DWORD *)&lf.lfOutPrecision = 838926849;
      StringCchCopyA(lf.lfFaceName, 0x1Fu, qword_18007F550);
      *((_QWORD *)this + 614) = CreateFontIndirectA(&lf);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180049448  mov     [rsp-8+arg_8], rbx
0x18004944d  mov     [rsp-8+arg_10], rsi
0x180049452  push    rbp
0x180049453  push    rdi
0x180049454  push    r14
0x180049456  lea     rbp, [rsp-47h]
0x18004945b  sub     rsp, 0B0h
0x180049462  mov     rax, cs:__security_cookie
0x180049469  xor     rax, rsp
0x18004946c  mov     [rbp+57h+var_18], rax
0x180049470  xor     r14d, r14d
0x180049473  mov     dword ptr [rcx+89Ch], 1
0x18004947d  xorps   xmm0, xmm0
0x180049480  mov     [rcx+698h], r14b
0x180049487  mov     [rcx+8A0h], r14b
0x18004948e  mov     rsi, rcx
0x180049491  mov     [rcx+10C4h], r14b
0x180049498  xor     eax, eax
0x18004949a  mov     [rcx+48Ch], r14b
0x1800494a1  mov     [rcx+26Ch], r14b
0x1800494a8  mov     [rcx+1330h], r14
0x1800494af  mov     [rcx+690h], r14
0x1800494b6  mov     [rcx+898h], r14d
0x1800494bd  mov     [rcx+68Ch], r14d
0x1800494c4  xor     ecx, ecx; hWnd
0x1800494c6  movups  xmmword ptr [rbp+57h+tm.tmHeight], xmm0
0x1800494ca  mov     qword ptr [rbp+57h+tm.tmItalic], rax
0x1800494ce  movups  xmmword ptr [rbp+57h+tm.tmExternalLeading], xmm0
0x1800494d2  movups  xmmword ptr [rbp+57h+tm.tmOverhang], xmm0
0x1800494d6  call    cs:__imp_GetDC
0x1800494dc  mov     rcx, rax; hdc
0x1800494df  lea     rdx, [rbp+57h+tm]; lptm
0x1800494e3  mov     rbx, rax
0x1800494e6  call    cs:__imp_GetTextMetricsA
0x1800494ec  mov     eax, [rbp+57h+tm.tmMaxCharWidth]
0x1800494ef  mov     rdx, rbx; hDC
0x1800494f2  xor     ecx, ecx; hWnd
0x1800494f4  mov     [rsi+488h], eax
0x1800494fa  call    cs:__imp_ReleaseDC
0x180049500  call    IsolationAwareInitCommonControls
0x180049505  call    IsolationAwareImageList_Create
0x18004950a  mov     [rsi+1328h], rax
0x180049511  test    rax, rax
0x180049514  jz      short loc_180049574
0x180049516  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x18004951d  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x180049522  mov     rcx, rax; hInstance
0x180049525  mov     edx, 138h; lpBitmapName
0x18004952a  call    cs:__imp_LoadBitmapA
0x180049530  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x180049537  mov     rdi, rax
0x18004953a  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x18004953f  mov     rcx, rax; hInstance
0x180049542  mov     edx, 139h; lpBitmapName
0x180049547  call    cs:__imp_LoadBitmapA
0x18004954d  mov     rcx, [rsi+1328h]
0x180049554  mov     rdx, rdi
0x180049557  mov     r8, rax
0x18004955a  mov     rbx, rax
0x18004955d  call    IsolationAwareImageList_Add
0x180049562  mov     rcx, rdi; ho
0x180049565  call    cs:__imp_DeleteObject
0x18004956b  mov     rcx, rbx; ho
0x18004956e  call    cs:__imp_DeleteObject
0x180049574  call    cs:__imp_GetSystemDefaultLangID
0x18004957a  mov     ecx, 3FFh
0x18004957f  and     ax, cx
0x180049582  cmp     ax, 11h
0x180049586  jnz     loc_18004960F
0x18004958c  xor     ecx, ecx; hWnd
0x18004958e  call    cs:__imp_GetDC
0x180049594  test    rax, rax
0x180049597  jz      short loc_18004960F
0x180049599  xorps   xmm0, xmm0
0x18004959c  mov     edx, 5Ah ; 'Z'; index
0x1800495a1  movups  xmmword ptr [rbp+57h+lf.lfFaceName+4], xmm0
0x1800495a5  mov     rcx, rax; hdc
0x1800495a8  movups  xmmword ptr [rbp+57h+lf.lfFaceName+10h], xmm0
0x1800495ac  movups  xmmword ptr [rbp+57h+lf.lfHeight], xmm0
0x1800495b0  movups  xmmword ptr [rbp+57h+lf.lfWeight], xmm0
0x1800495b4  call    cs:__imp_GetDeviceCaps
0x1800495ba  mov     ecx, 0FFFFFFF7h; nNumber
0x1800495bf  mov     edx, eax; nNumerator
0x1800495c1  lea     r8d, [rcx+51h]; nDenominator
0x1800495c5  call    cs:__imp_MulDiv
0x1800495cb  movdqa  xmm0, cs:__xmm@00000190000000000000000000000000
0x1800495d3  lea     r8, qword_18007F550; char *
0x1800495da  mov     edx, 1Fh; unsigned __int64
0x1800495df  mov     [rbp+57h+lf.lfHeight], eax
0x1800495e2  lea     rcx, [rbp+57h+lf.lfFaceName]; char *
0x1800495e6  mov     dword ptr [rbp+57h+lf.lfItalic], 80000000h
0x1800495ed  movdqu  xmmword ptr [rbp+57h+lf.lfWidth], xmm0
0x1800495f2  mov     dword ptr [rbp+57h+lf.lfOutPrecision], 32010201h
0x1800495f9  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800495fe  lea     rcx, [rbp+57h+lf]; lplf
0x180049602  call    cs:__imp_CreateFontIndirectA
0x180049608  mov     [rsi+1330h], rax
0x18004960f  mov     rax, rsi
0x180049612  mov     rcx, [rbp+57h+var_18]
0x180049616  xor     rcx, rsp; StackCookie
0x180049619  call    __security_check_cookie
0x18004961e  lea     r11, [rsp+0C0h+var_10]
0x180049626  mov     rbx, [r11+28h]
0x18004962a  mov     rsi, [r11+30h]
0x18004962e  mov     rsp, r11
0x180049631  pop     r14
0x180049633  pop     rdi
0x180049634  pop     rbp
0x180049635  retn
```
