# COskNativeHWNDHost::Initialize(ushort const *,ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,HINSTANCE__ *,uint)

- ea: `0x140014f60`
- end: `0x14001518c`
- name: `?Initialize@COskNativeHWNDHost@@AEAAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@I@Z`
- size: `556`
- prototype: `__int64 __usercall@<rax>(COskNativeHWNDHost *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, HWND@<r9>, HICON, int, int, int, int, int, int, HINSTANCE, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400144fc`

## callees

- `0x140002de3`
- `0x14000df20`
- `0x1400144ac`
- `0x140014740`
- `0x140014cb8`
- `0x140014f60`
- `0x140016cf4`
- `0x14001c010`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GlobalAddAtomW` at `0x140015070`
- `KERNEL32!GlobalAddAtomW` at `0x140015070`
- `GDI32!GetStockObject` at `0x140015052`
- `GDI32!GetStockObject` at `0x140015052`
- `USER32!SendMessageW` at `0x140015107`
- `USER32!SendMessageW` at `0x140015107`
- `USER32!SetLayeredWindowAttributes` at `0x140015047`
- `USER32!SetLayeredWindowAttributes` at `0x140015047`
- `USER32!SetClassLongPtrW` at `0x140015063`
- `USER32!SetClassLongPtrW` at `0x140015063`
- `USER32!SetPropW` at `0x14001508d`
- `USER32!SetPropW` at `0x14001508d`
- `ole32!CoCreateInstance` at `0x14001512c`
- `ole32!CoCreateInstance` at `0x14001512c`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140015030`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400150c4`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140015030`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400150c4`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@I@Z` at `0x140015003`
- `DUI70!?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@I@Z` at `0x140015003`

## string_xrefs

- `0x140015069`: `ACCESSIBILITY_TOPMOST`

## pseudocode

```c
__int64 __fastcall COskNativeHWNDHost::Initialize(
        COskNativeHWNDHost *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HWND a4,
        HICON a5)
{
  int inited; // edi
  HWND HWND; // rsi
  HGDIOBJ StockObject; // rax
  ATOM v10; // ax
  __int64 Window; // rax
  HWND v12; // rax
  HWND v13; // rcx
  HRESULT Instance; // eax
  LPARAM lParam[10]; // [rsp+70h] [rbp-78h] BYREF

  *((_DWORD *)this + 16) = 0;
  inited = -2147467259;
  if ( COskNativeHWNDHost::StoreDPI(this) )
  {
    COskNativeHWNDHost::CacheForegroundWindowHandle(this);
    inited = DirectUI::NativeHWNDHost::Initialize(
               this,
               L"OSKMainClass",
               a3,
               0,
               a5,
               100,
               100,
               0,
               0,
               135004168,
               13500416,
               0,
               0x11u);
    if ( inited >= 0 )
    {
      COskNativeHWNDHost::DetermineOSKWindowSizeAndLimits(this);
      inited = COskNativeHWNDHost::InitSettings(this);
      if ( inited >= 0 )
      {
        HWND = DirectUI::NativeHWNDHost::GetHWND(this);
        SetLayeredWindowAttributes(HWND, 0, 0xFFu, 2u);
        StockObject = GetStockObject(5);
        SetClassLongPtrW(HWND, -10, (LONG_PTR)StockObject);
        v10 = GlobalAddAtomW(L"ACCESSIBILITY_TOPMOST");
        *((_WORD *)this + 51) = v10;
        if ( v10 )
          SetPropW(HWND, (LPCWSTR)v10, HANDLE_FLAG_INHERIT);
        Window = SHFusionCreateWindowEx();
        *((_QWORD *)this + 9) = Window;
        if ( Window )
        {
          memset_0(lParam, 0, 0x48u);
          lParam[0] = 0x12200000048LL;
          v12 = DirectUI::NativeHWNDHost::GetHWND(this);
          v13 = (HWND)*((_QWORD *)this + 9);
          lParam[1] = (LPARAM)v12;
          lParam[5] = (LPARAM)g_hInstance;
          lParam[2] = 0;
          lParam[6] = 0;
          SendMessageW(v13, 0x432u, 0, (LPARAM)lParam);
        }
        Instance = CoCreateInstance(
                     &GUID_29ce1d46_b481_4aa0_a08a_d3ebc8aca402,
                     0,
                     1u,
                     &GUID_8849dc22_cedf_4c95_998d_051419dd3f76,
                     (LPVOID *)this + 16);
        if ( Instance < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            WPP_701f9d48580b340774086315e62b6ed1_Traceguids,
            (unsigned int)Instance);
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140014f60  mov     [rsp+arg_8], rbx
0x140014f65  push    rbp
0x140014f66  push    rsi
0x140014f67  push    rdi
0x140014f68  sub     rsp, 0D0h
0x140014f6f  mov     rax, cs:__security_cookie
0x140014f76  xor     rax, rsp
0x140014f79  mov     [rsp+0E8h+var_28], rax
0x140014f81  mov     rbp, [rsp+0E8h+arg_20]
0x140014f89  mov     rsi, r8
0x140014f8c  mov     rbx, rcx
0x140014f8f  mov     dword ptr [rcx+40h], 0
0x140014f96  mov     edi, 80004005h
0x140014f9b  call    ?StoreDPI@COskNativeHWNDHost@@AEAA_NXZ; COskNativeHWNDHost::StoreDPI(void)
0x140014fa0  test    al, al
0x140014fa2  jz      loc_140015167
0x140014fa8  mov     rcx, rbx; this
0x140014fab  call    ?CacheForegroundWindowHandle@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::CacheForegroundWindowHandle(void)
0x140014fb0  mov     [rsp+0E8h+var_88], 11h
0x140014fb8  lea     rdx, ClassName; "OSKMainClass"
0x140014fbf  mov     [rsp+0E8h+var_90], 0
0x140014fc8  mov     eax, 64h ; 'd'
0x140014fcd  mov     [rsp+0E8h+var_98], 0CE0000h
0x140014fd5  xor     r9d, r9d
0x140014fd8  mov     [rsp+0E8h+var_A0], 80C0008h
0x140014fe0  mov     r8, rsi
0x140014fe3  mov     [rsp+0E8h+var_A8], 0
0x140014feb  mov     rcx, rbx
0x140014fee  mov     [rsp+0E8h+var_B0], 0
0x140014ff6  mov     [rsp+0E8h+var_B8], eax
0x140014ffa  mov     [rsp+0E8h+var_C0], eax
0x140014ffe  mov     [rsp+0E8h+ppv], rbp
0x140015003  call    cs:__imp_?Initialize@NativeHWNDHost@DirectUI@@QEAAJPEBG0PEAUHWND__@@PEAUHICON__@@HHHHHHPEAUHINSTANCE__@@I@Z; DirectUI::NativeHWNDHost::Initialize(ushort const *,ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,HINSTANCE__ *,uint)
0x140015009  mov     edi, eax
0x14001500b  test    eax, eax
0x14001500d  js      loc_140015167
0x140015013  mov     rcx, rbx; this
0x140015016  call    ?DetermineOSKWindowSizeAndLimits@COskNativeHWNDHost@@AEAAXXZ; COskNativeHWNDHost::DetermineOSKWindowSizeAndLimits(void)
0x14001501b  mov     rcx, rbx; this
0x14001501e  call    ?InitSettings@COskNativeHWNDHost@@AEAAJXZ; COskNativeHWNDHost::InitSettings(void)
0x140015023  mov     edi, eax
0x140015025  test    eax, eax
0x140015027  js      loc_140015167
0x14001502d  mov     rcx, rbx
0x140015030  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140015036  mov     r9d, 2; dwFlags
0x14001503c  mov     r8b, 0FFh; bAlpha
0x14001503f  mov     rcx, rax; hwnd
0x140015042  xor     edx, edx; crKey
0x140015044  mov     rsi, rax
0x140015047  call    cs:__imp_SetLayeredWindowAttributes
0x14001504d  mov     ecx, 5; i
0x140015052  call    cs:__imp_GetStockObject
0x140015058  mov     edx, 0FFFFFFF6h; nIndex
0x14001505d  mov     rcx, rsi; hWnd
0x140015060  mov     r8, rax; dwNewLong
0x140015063  call    cs:__imp_SetClassLongPtrW
0x140015069  lea     rcx, aAccessibilityT; "ACCESSIBILITY_TOPMOST"
0x140015070  call    cs:__imp_GlobalAddAtomW
0x140015076  xor     ecx, ecx
0x140015078  mov     [rbx+66h], ax
0x14001507c  lea     ebp, [rcx+1]
0x14001507f  cmp     cx, ax
0x140015082  jz      short loc_140015093
0x140015084  movzx   edx, ax; lpString
0x140015087  mov     r8d, ebp; hData
0x14001508a  mov     rcx, rsi; hWnd
0x14001508d  call    cs:__imp_SetPropW
0x140015093  call    SHFusionCreateWindowEx
0x140015098  mov     [rbx+48h], rax
0x14001509c  test    rax, rax
0x14001509f  jz      short loc_14001510D
0x1400150a1  mov     esi, 48h ; 'H'
0x1400150a6  lea     rcx, [rsp+0E8h+lParam]; void *
0x1400150ab  mov     r8d, esi; Size
0x1400150ae  xor     edx, edx; Val
0x1400150b0  call    memset_0
0x1400150b5  mov     rcx, rbx
0x1400150b8  mov     dword ptr [rsp+0E8h+lParam], esi
0x1400150bc  mov     dword ptr [rsp+0E8h+lParam+4], 122h
0x1400150c4  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1400150ca  mov     rcx, [rbx+48h]; hWnd
0x1400150ce  lea     r9, [rsp+0E8h+lParam]; lParam
0x1400150d3  mov     [rsp+0E8h+var_70], rax
0x1400150d8  xor     r8d, r8d; wParam
0x1400150db  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1400150e2  mov     edx, 432h; Msg
0x1400150e7  mov     [rsp+0E8h+var_50], rax
0x1400150ef  mov     [rsp+0E8h+var_68], 0
0x1400150fb  mov     [rsp+0E8h+var_48], 0
0x140015107  call    cs:__imp_SendMessageW
0x14001510d  lea     rax, [rbx+80h]
0x140015114  mov     r8d, ebp; dwClsContext
0x140015117  lea     r9, _GUID_8849dc22_cedf_4c95_998d_051419dd3f76; riid
0x14001511e  mov     [rsp+0E8h+ppv], rax; ppv
0x140015123  xor     edx, edx; pUnkOuter
0x140015125  lea     rcx, _GUID_29ce1d46_b481_4aa0_a08a_d3ebc8aca402; rclsid
0x14001512c  call    cs:__imp_CoCreateInstance
0x140015132  test    eax, eax
0x140015134  jns     short loc_140015167
0x140015136  mov     rcx, cs:WPP_GLOBAL_Control
0x14001513d  lea     rdx, WPP_GLOBAL_Control
0x140015144  cmp     rcx, rdx
0x140015147  jz      short loc_140015167
0x140015149  test    [rcx+1Ch], bpl
0x14001514d  jz      short loc_140015167
0x14001514f  mov     rcx, [rcx+10h]
0x140015153  lea     r8, WPP_701f9d48580b340774086315e62b6ed1_Traceguids
0x14001515a  mov     edx, 0Ah
0x14001515f  mov     r9d, eax
0x140015162  call    WPP_SF_d
0x140015167  mov     eax, edi
0x140015169  mov     rcx, [rsp+0E8h+var_28]
0x140015171  xor     rcx, rsp; StackCookie
0x140015174  call    __security_check_cookie
0x140015179  mov     rbx, [rsp+0E8h+arg_8]
0x140015181  add     rsp, 0D0h
0x140015188  pop     rdi
0x140015189  pop     rsi
0x14001518a  pop     rbp
0x14001518b  retn
```
