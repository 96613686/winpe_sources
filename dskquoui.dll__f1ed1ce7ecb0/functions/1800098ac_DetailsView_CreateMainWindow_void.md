# DetailsView::CreateMainWindow(void)

- ea: `0x1800098ac`
- end: `0x180009b2c`
- name: `?CreateMainWindow@DetailsView@@AEAAJXZ`
- size: `640`
- prototype: `__int64 __fastcall(DetailsView *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180010390`

## callees

- `0x1800022b4`
- `0x1800098ac`
- `0x18000f450`
- `0x180019d24`
- `0x180019ee0`
- `0x18001c134`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180009a0f`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180009a40`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180009a0f`
- `api-ms-win-core-localization-l1-2-0!GetUserPreferredUILanguages` at `0x180009a40`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180009a5d`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180009a5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a24`
- `GDI32!GetDeviceCaps` at `0x1800099a8`
- `GDI32!GetDeviceCaps` at `0x1800099c1`
- `GDI32!GetDeviceCaps` at `0x1800099a8`
- `GDI32!GetDeviceCaps` at `0x1800099c1`
- `USER32!RegisterClassExW` at `0x180009952`
- `USER32!RegisterClassExW` at `0x180009952`
- `USER32!GetDC` at `0x180009997`
- `USER32!GetDC` at `0x180009997`
- `USER32!ReleaseDC` at `0x1800099f9`
- `USER32!ReleaseDC` at `0x1800099f9`
- `USER32!LoadCursorW` at `0x180009924`
- `USER32!LoadCursorW` at `0x180009924`
- `USER32!LoadIconW` at `0x180009913`
- `USER32!LoadIconW` at `0x180009913`
- `USER32!GetDesktopWindow` at `0x18000998b`
- `USER32!GetDesktopWindow` at `0x18000998b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DetailsView::CreateMainWindow(DetailsView *this)
{
  HWND DesktopWindow; // r15
  HDC DC; // rdi
  int *v4; // r14
  DWORD v5; // edi
  WCHAR *v6; // rax
  WCHAR *v7; // rsi
  int v8; // r9d
  int v9; // eax
  HWND Window; // rax
  unsigned int v11; // edi
  _QWORD v13[2]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v14[8]; // [rsp+70h] [rbp-29h] BYREF
  LPCWSTR *v15; // [rsp+78h] [rbp-21h]
  WNDCLASSEXW v16; // [rsp+80h] [rbp-19h] BYREF
  ULONG pcchLanguagesBuffer; // [rsp+100h] [rbp+67h] BYREF
  ULONG pulNumLanguages; // [rsp+108h] [rbp+6Fh] BYREF
  int LCData; // [rsp+110h] [rbp+77h] BYREF

  memset_0(&v16, 0, sizeof(v16));
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  v16.cbSize = 80;
  v16.style = 128;
  v16.lpfnWndProc = (WNDPROC)DetailsView::WndProc;
  *(_QWORD *)&v16.cbClsExtra = 0;
  v16.hInstance = g_hInstDll;
  v16.hIcon = LoadIconW(g_hInstDll, (LPCWSTR)0x75);
  v16.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  *(__m128i *)&v16.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  v16.lpszClassName = c_szWndClassDetailsView;
  v16.hIconSm = 0;
  RegisterClassExW(&v16);
  v13[0] = 16;
  v13[1] = this;
  CString::CString((CString *)v14, g_hInstDll, 40556, **((_QWORD **)this + 39));
  DesktopWindow = GetDesktopWindow();
  DC = GetDC(DesktopWindow);
  if ( *((_DWORD *)this + 143) == (unsigned __int16)GetDeviceCaps(DC, 8)
    && *((_DWORD *)this + 144) == (unsigned __int16)GetDeviceCaps(DC, 10) )
  {
    v4 = (int *)((char *)this + 580);
  }
  else
  {
    v4 = (int *)((char *)this + 580);
    *((_DWORD *)this + 145) = 0;
    *((_DWORD *)this + 146) = 0;
  }
  ReleaseDC(DesktopWindow, DC);
  v5 = 0;
  GetUserPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer);
  if ( pcchLanguagesBuffer )
  {
    v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * pcchLanguagesBuffer);
    v7 = v6;
    if ( v6 )
    {
      if ( GetUserPreferredUILanguages(8u, &pulNumLanguages, v6, &pcchLanguagesBuffer) )
      {
        LCData = 0;
        if ( GetLocaleInfoEx(v7, 0x20000070u, (LPWSTR)&LCData, 2) )
        {
          if ( LCData == 1 )
            v5 = 0x400000;
        }
      }
      LocalFree(v7);
    }
  }
  v8 = 0x80000000;
  if ( *((_DWORD *)this + 146) )
    v8 = *((_DWORD *)this + 146);
  v9 = 0x80000000;
  if ( *v4 )
    v9 = *v4;
  Window = SHFusionCreateWindowEx(
             v5,
             c_szWndClassDetailsView,
             *v15,
             0xCF0000u,
             0x80000000,
             0x80000000,
             v9,
             v8,
             DesktopWindow,
             0,
             g_hInstDll,
             v13);
  *((_QWORD *)this + 12) = Window;
  if ( Window )
  {
    v11 = 0;
    DetailsView::RegisterAsDropTarget(this, 1);
  }
  else
  {
    v11 = -2147467259;
  }
  CString::~CString((CString *)v14);
  return v11;
}

```

## disassembly

```asm
0x1800098ac  mov     [rsp-8+arg_18], rbx
0x1800098b1  push    rbp
0x1800098b2  push    rsi
0x1800098b3  push    rdi
0x1800098b4  push    r14
0x1800098b6  push    r15
0x1800098b8  lea     rbp, [rsp-37h]
0x1800098bd  sub     rsp, 0D0h
0x1800098c4  mov     rbx, rcx
0x1800098c7  mov     edi, 50h ; 'P'
0x1800098cc  mov     r8d, edi; Size
0x1800098cf  xor     edx, edx; Val
0x1800098d1  lea     rcx, [rbp+57h+var_70]; void *
0x1800098d5  call    memset_0
0x1800098da  mov     [rbp+57h+pulNumLanguages], 0
0x1800098e1  mov     [rbp+57h+pcchLanguagesBuffer], 0
0x1800098e8  mov     [rbp+57h+var_70.cbSize], edi
0x1800098eb  mov     [rbp+57h+var_70.style], 80h
0x1800098f2  lea     rax, ?WndProc@DetailsView@@CA_JPEAUHWND__@@I_K_J@Z; DetailsView::WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800098f9  mov     [rbp+57h+var_70.lpfnWndProc], rax
0x1800098fd  mov     qword ptr [rbp+57h+var_70.cbClsExtra], 0
0x180009905  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000990c  mov     [rbp+57h+var_70.hInstance], rcx
0x180009910  lea     edx, [rdi+25h]; lpIconName
0x180009913  call    cs:__imp_LoadIconW
0x180009919  mov     [rbp+57h+var_70.hIcon], rax
0x18000991d  mov     edx, 7F00h; lpCursorName
0x180009922  xor     ecx, ecx; hInstance
0x180009924  call    cs:__imp_LoadCursorW
0x18000992a  mov     [rbp+57h+var_70.hCursor], rax
0x18000992e  movdqa  xmm0, cs:__xmm@00000000000000690000000000000000
0x180009936  movdqa  xmmword ptr [rbp+57h+var_70.hbrBackground], xmm0
0x18000993b  lea     rax, ?c_szWndClassDetailsView@@3PAGA; "DetailsView"
0x180009942  mov     [rbp+57h+var_70.lpszClassName], rax
0x180009946  mov     [rbp+57h+var_70.hIconSm], 0
0x18000994e  lea     rcx, [rbp+57h+var_70]; WNDCLASSEXW *
0x180009952  call    cs:__imp_RegisterClassExW
0x180009958  xorps   xmm0, xmm0
0x18000995b  movups  [rbp+57h+var_90], xmm0
0x18000995f  lea     eax, [rdi-40h]
0x180009962  mov     word ptr [rbp+57h+var_90], ax
0x180009966  mov     qword ptr [rbp+57h+var_90+8], rbx
0x18000996a  mov     r9, [rbx+138h]
0x180009971  mov     r9, [r9]
0x180009974  mov     r8d, 9E6Ch; int
0x18000997a  mov     rdx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180009981  lea     rcx, [rbp+57h+var_80]; this
0x180009985  call    ??0CString@@QEAA@PEAUHINSTANCE__@@HZZ; CString::CString(HINSTANCE__ *,int,...)
0x18000998a  nop
0x18000998b  call    cs:__imp_GetDesktopWindow
0x180009991  mov     r15, rax
0x180009994  mov     rcx, rax; hWnd
0x180009997  call    cs:__imp_GetDC
0x18000999d  mov     rdi, rax
0x1800099a0  mov     edx, 8; index
0x1800099a5  mov     rcx, rax; hdc
0x1800099a8  call    cs:__imp_GetDeviceCaps
0x1800099ae  movzx   ecx, ax
0x1800099b1  cmp     [rbx+23Ch], ecx
0x1800099b7  jnz     short loc_1800099DB
0x1800099b9  mov     edx, 0Ah; index
0x1800099be  mov     rcx, rdi; hdc
0x1800099c1  call    cs:__imp_GetDeviceCaps
0x1800099c7  movzx   ecx, ax
0x1800099ca  cmp     [rbx+240h], ecx
0x1800099d0  jnz     short loc_1800099DB
0x1800099d2  lea     r14, [rbx+244h]
0x1800099d9  jmp     short loc_1800099F3
0x1800099db  lea     r14, [rbx+244h]
0x1800099e2  mov     dword ptr [r14], 0
0x1800099e9  mov     dword ptr [rbx+248h], 0
0x1800099f3  mov     rdx, rdi; hDC
0x1800099f6  mov     rcx, r15; hWnd
0x1800099f9  call    cs:__imp_ReleaseDC
0x1800099ff  xor     edi, edi
0x180009a01  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180009a05  xor     r8d, r8d; pwszLanguagesBuffer
0x180009a08  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x180009a0c  lea     ecx, [rdi+8]; dwFlags
0x180009a0f  call    cs:__imp_GetUserPreferredUILanguages
0x180009a15  mov     eax, [rbp+57h+pcchLanguagesBuffer]
0x180009a18  test    eax, eax
0x180009a1a  jz      short loc_180009A7C
0x180009a1c  mov     edx, eax
0x180009a1e  add     rdx, rdx; uBytes
0x180009a21  lea     ecx, [rdi+40h]; uFlags
0x180009a24  call    cs:__imp_LocalAlloc
0x180009a2a  mov     rsi, rax
0x180009a2d  test    rax, rax
0x180009a30  jz      short loc_180009A7C
0x180009a32  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180009a36  mov     r8, rax; pwszLanguagesBuffer
0x180009a39  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x180009a3d  lea     ecx, [rdi+8]; dwFlags
0x180009a40  call    cs:__imp_GetUserPreferredUILanguages
0x180009a46  test    eax, eax
0x180009a48  jz      short loc_180009A73
0x180009a4a  mov     [rbp+57h+LCData], edi
0x180009a4d  lea     r9d, [rdi+2]; cchData
0x180009a51  lea     r8, [rbp+57h+LCData]; lpLCData
0x180009a55  mov     edx, 20000070h; LCType
0x180009a5a  mov     rcx, rsi; lpLocaleName
0x180009a5d  call    cs:__imp_GetLocaleInfoEx
0x180009a63  test    eax, eax
0x180009a65  jz      short loc_180009A73
0x180009a67  mov     eax, 400000h
0x180009a6c  cmp     [rbp+57h+LCData], 1
0x180009a70  cmovz   edi, eax
0x180009a73  mov     rcx, rsi; hMem
0x180009a76  call    cs:__imp_LocalFree
0x180009a7c  mov     r8, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstDll
0x180009a83  mov     eax, [rbx+248h]
0x180009a89  mov     r10d, 80000000h
0x180009a8f  mov     r9d, r10d
0x180009a92  test    eax, eax
0x180009a94  cmovnz  r9d, eax
0x180009a98  mov     eax, r10d
0x180009a9b  cmp     dword ptr [r14], 0
0x180009a9f  cmovnz  eax, [r14]
0x180009aa3  lea     rcx, [rbp+57h+var_90]
0x180009aa7  mov     [rsp+0F0h+var_98], rcx; LPVOID
0x180009aac  mov     [rsp+0F0h+var_A0], r8; HINSTANCE
0x180009ab1  mov     [rsp+0F0h+var_A8], 0; HMENU
0x180009aba  mov     [rsp+0F0h+var_B0], r15; HWND
0x180009abf  mov     [rsp+0F0h+var_B8], r9d; int
0x180009ac4  mov     [rsp+0F0h+var_C0], eax; int
0x180009ac8  mov     [rsp+0F0h+var_C8], r10d; int
0x180009acd  mov     [rsp+0F0h+var_D0], r10d; int
0x180009ad2  mov     r9d, 0CF0000h; dwStyle
0x180009ad8  mov     r8, [rbp+57h+var_78]
0x180009adc  mov     r8, [r8]; lpWindowName
0x180009adf  lea     rdx, ?c_szWndClassDetailsView@@3PAGA; "DetailsView"
0x180009ae6  mov     ecx, edi; dwExStyle
0x180009ae8  call    SHFusionCreateWindowEx
0x180009aed  mov     [rbx+60h], rax
0x180009af1  test    rax, rax
0x180009af4  jz      short loc_180009B05
0x180009af6  xor     edi, edi
0x180009af8  lea     edx, [rdi+1]; int
0x180009afb  mov     rcx, rbx; this
0x180009afe  call    ?RegisterAsDropTarget@DetailsView@@AEAAXH@Z; DetailsView::RegisterAsDropTarget(int)
0x180009b03  jmp     short loc_180009B0A
0x180009b05  mov     edi, 80004005h
0x180009b0a  lea     rcx, [rbp+57h+var_80]; this
0x180009b0e  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180009b13  mov     eax, edi
0x180009b15  mov     rbx, [rsp+0F0h+arg_18]
0x180009b1d  add     rsp, 0D0h
0x180009b24  pop     r15
0x180009b26  pop     r14
0x180009b28  pop     rdi
0x180009b29  pop     rsi
0x180009b2a  pop     rbp
0x180009b2b  retn
```
