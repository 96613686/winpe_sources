# PAL_System_Win32_ThreadCreateWindow(HWND__ * *)

- ea: `0x140041348`
- end: `0x14004168c`
- name: `?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140043768`

## callees

- `0x1400014d4`
- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x140008ce0`
- `0x140041348`
- `0x140041694`
- `0x14006a120`

## import_xrefs

- `USER32!CreateWindowExW` at `0x1400415db`
- `USER32!CreateWindowExW` at `0x1400415db`

## string_xrefs

- `0x1400413b1`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14004144f`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14004160c`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140041396`: `PAL_System_Win32_ThreadCreateWindow`
- `0x140041434`: `PAL_System_Win32_ThreadCreateWindow`
- `0x1400415f1`: `PAL_System_Win32_ThreadCreateWindow`
- `0x14004145f`: `Failed to initialize thread window class`
- `0x1400414b1`: `PAL_SYS_WIN32_THREAD_WNDCLASS`
- `0x140041620`: `Failed to create thread window`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadCreateWindow(HWND *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  PVOID *v9; // rcx
  unsigned int v10; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  HWND Window; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int Y[2]; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v21; // [rsp+68h] [rbp-98h] BYREF
  const char *v22; // [rsp+70h] [rbp-90h] BYREF
  const char *v23; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !a1 )
  {
    v5 = -2147024809;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v19 = 435;
      v21 = "PAL_System_Win32_ThreadCreateWindow";
      v20 = -2147024809;
      v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v23 = "NULL paramater passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)&byte_14008044F,
        a3,
        a4,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v22,
        (__int64)&v19,
        (__int64)&v21);
    }
    return v5;
  }
  memset_0(ClassName, 0, 0x208u);
  v5 = PAL_System_Win32_ThreadRegisterWindowClass();
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v20 = 447;
      v23 = "PAL_System_Win32_ThreadCreateWindow";
      v19 = v5;
      v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v21 = "Failed to initialize thread window class";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1400880C8,
        (unsigned int)&word_1400803BE,
        v6,
        v7,
        (__int64)&v21,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v23);
    }
    return v5;
  }
  ClassName[0] = 0;
  v8 = StringCchPrintfW(ClassName, 0x104u, L"%p-%s", &g_TsSystemPalDllModule, L"PAL_SYS_WIN32_THREAD_WNDCLASS");
  v9 = (PVOID *)WPP_GLOBAL_Control;
  v10 = v8;
  if ( v8 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"Failed StringCchPrintf",
      v10);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v5 = v10;
LABEL_14:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      Y[0] = v10;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
        v12,
        (__int64)"Failed to get module specific class name",
        *(_QWORD *)Y);
    }
    return v5;
  }
  v5 = v8;
  if ( v8 < 0 )
    goto LABEL_14;
  Window = CreateWindowExW(0, ClassName, 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
  if ( Window )
  {
    *a1 = Window;
    return 0;
  }
  else if ( (unsigned int)dword_1400880C8 > 2 )
  {
    v20 = 463;
    v23 = "PAL_System_Win32_ThreadCreateWindow";
    v19 = -2147467259;
    v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
    v21 = "Failed to create thread window";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)&word_14008025E,
      v15,
      v16,
      (__int64)&v21,
      (__int64)&v19,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v23);
  }
  return v5;
}

```

## disassembly

```asm
0x140041348  mov     [rsp-8+arg_8], rbx
0x14004134d  mov     [rsp-8+arg_10], rsi
0x140041352  push    rbp
0x140041353  push    rdi
0x140041354  push    r15
0x140041356  lea     rbp, [rsp-1A0h]
0x14004135e  sub     rsp, 2A0h
0x140041365  mov     rax, cs:__security_cookie
0x14004136c  xor     rax, rsp
0x14004136f  mov     [rbp+1B0h+var_20], rax
0x140041376  mov     rsi, rcx
0x140041379  test    rcx, rcx
0x14004137c  jnz     loc_140041409
0x140041382  mov     eax, cs:dword_1400880C8
0x140041388  mov     ebx, 80070057h
0x14004138d  cmp     eax, 2
0x140041390  jbe     loc_140041663
0x140041396  lea     rax, aPalSystemWin32_4; "PAL_System_Win32_ThreadCreateWindow"
0x14004139d  mov     [rsp+2B0h+var_250], 1B3h
0x1400413a5  mov     [rsp+2B0h+var_248], rax
0x1400413aa  lea     rdx, byte_14008044F
0x1400413b1  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400413b8  mov     [rsp+2B0h+var_24C], ebx
0x1400413bc  mov     [rsp+2B0h+var_240], rax
0x1400413c1  lea     rax, aNullParamaterP; "NULL paramater passed"
0x1400413c8  mov     [rsp+2B0h+var_238], rax
0x1400413cd  lea     rax, [rsp+2B0h+var_248]
0x1400413d2  mov     [rsp+2B0h+hWndParent], rax
0x1400413d7  lea     rax, [rsp+2B0h+var_250]
0x1400413dc  mov     qword ptr [rsp+2B0h+nHeight], rax
0x1400413e1  lea     rax, [rsp+2B0h+var_240]
0x1400413e6  mov     qword ptr [rsp+2B0h+nWidth], rax
0x1400413eb  lea     rax, [rsp+2B0h+var_24C]
0x1400413f0  mov     qword ptr [rsp+2B0h+Y], rax
0x1400413f5  lea     rax, [rsp+2B0h+var_238]
0x1400413fa  mov     qword ptr [rsp+2B0h+X], rax
0x1400413ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140041404  jmp     loc_140041663
0x140041409  xor     edx, edx; Val
0x14004140b  lea     rcx, [rbp+1B0h+ClassName]; void *
0x14004140f  mov     r8d, 208h; Size
0x140041415  call    memset_0
0x14004141a  call    ?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ; PAL_System_Win32_ThreadRegisterWindowClass(void)
0x14004141f  mov     ebx, eax
0x140041421  test    eax, eax
0x140041423  jns     short loc_14004149D
0x140041425  mov     ecx, cs:dword_1400880C8
0x14004142b  cmp     ecx, 2
0x14004142e  jbe     loc_140041663
0x140041434  lea     rax, aPalSystemWin32_4; "PAL_System_Win32_ThreadCreateWindow"
0x14004143b  mov     [rsp+2B0h+var_24C], 1BFh
0x140041443  mov     [rsp+2B0h+var_238], rax
0x140041448  lea     rdx, word_1400803BE
0x14004144f  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041456  mov     [rsp+2B0h+var_250], ebx
0x14004145a  mov     [rsp+2B0h+var_240], rax
0x14004145f  lea     rax, aFailedToInitia_5; "Failed to initialize thread window clas"...
0x140041466  mov     [rsp+2B0h+var_248], rax
0x14004146b  lea     rax, [rsp+2B0h+var_238]
0x140041470  mov     [rsp+2B0h+hWndParent], rax
0x140041475  lea     rax, [rsp+2B0h+var_24C]
0x14004147a  mov     qword ptr [rsp+2B0h+nHeight], rax
0x14004147f  lea     rax, [rsp+2B0h+var_240]
0x140041484  mov     qword ptr [rsp+2B0h+nWidth], rax
0x140041489  lea     rax, [rsp+2B0h+var_250]
0x14004148e  mov     qword ptr [rsp+2B0h+Y], rax
0x140041493  lea     rax, [rsp+2B0h+var_248]
0x140041498  jmp     loc_1400413FA
0x14004149d  xor     eax, eax
0x14004149f  lea     r9, ?g_TsSystemPalDllModule@@3HA; int g_TsSystemPalDllModule
0x1400414a6  mov     [rbp+1B0h+ClassName], ax
0x1400414aa  lea     r8, aPS; "%p-%s"
0x1400414b1  lea     rax, aPalSysWin32Thr; "PAL_SYS_WIN32_THREAD_WNDCLASS"
0x1400414b8  mov     edx, 104h; unsigned __int64
0x1400414bd  lea     rcx, [rbp+1B0h+ClassName]; unsigned __int16 *
0x1400414c1  mov     qword ptr [rsp+2B0h+X], rax
0x1400414c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400414cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400414d2  mov     edi, eax
0x1400414d4  lea     r15, WPP_GLOBAL_Control
0x1400414db  test    eax, eax
0x1400414dd  jns     short loc_14004152F
0x1400414df  cmp     rcx, r15
0x1400414e2  jz      short loc_14004152F
0x1400414e4  test    byte ptr [rcx+1Ch], 8
0x1400414e8  jz      short loc_14004152F
0x1400414ea  cmp     byte ptr [rcx+19h], 2
0x1400414ee  jb      short loc_14004152F
0x1400414f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400414f5  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x1400414fc  mov     [rsp+2B0h+Y], edi
0x140041500  mov     qword ptr [rsp+2B0h+X], rcx
0x140041505  lea     r8, WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids
0x14004150c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041513  mov     edx, 0Ch
0x140041518  mov     r9d, eax
0x14004151b  mov     rcx, [rcx+10h]
0x14004151f  call    WPP_SF_DsD
0x140041524  mov     rcx, cs:WPP_GLOBAL_Control
0x14004152b  mov     ebx, edi
0x14004152d  jmp     short loc_140041535
0x14004152f  mov     ebx, edi
0x140041531  test    edi, edi
0x140041533  jns     short loc_14004158B
0x140041535  cmp     rcx, r15
0x140041538  jz      loc_140041663
0x14004153e  test    byte ptr [rcx+1Ch], 8
0x140041542  jz      loc_140041663
0x140041548  cmp     byte ptr [rcx+19h], 2
0x14004154c  jb      loc_140041663
0x140041552  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041557  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x14004155e  mov     [rsp+2B0h+Y], edi
0x140041562  mov     qword ptr [rsp+2B0h+X], rcx
0x140041567  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x14004156e  mov     rcx, cs:WPP_GLOBAL_Control
0x140041575  mov     edx, 11h
0x14004157a  mov     r9d, eax
0x14004157d  mov     rcx, [rcx+10h]
0x140041581  call    WPP_SF_DsD
0x140041586  jmp     loc_140041663
0x14004158b  mov     [rsp+2B0h+lpParam], 0; lpParam
0x140041594  lea     rdx, [rbp+1B0h+ClassName]; lpClassName
0x140041598  mov     [rsp+2B0h+hInstance], 0; hInstance
0x1400415a1  xor     r9d, r9d; dwStyle
0x1400415a4  mov     [rsp+2B0h+hMenu], 0; hMenu
0x1400415ad  xor     r8d, r8d; lpWindowName
0x1400415b0  mov     [rsp+2B0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x1400415b9  xor     ecx, ecx; dwExStyle
0x1400415bb  mov     [rsp+2B0h+nHeight], 0; nHeight
0x1400415c3  mov     [rsp+2B0h+nWidth], 0; nWidth
0x1400415cb  mov     [rsp+2B0h+Y], 0; Y
0x1400415d3  mov     [rsp+2B0h+X], 0; X
0x1400415db  call    cs:__imp_CreateWindowExW
0x1400415e1  test    rax, rax
0x1400415e4  jnz     short loc_14004165E
0x1400415e6  mov     eax, cs:dword_1400880C8
0x1400415ec  cmp     eax, 2
0x1400415ef  jbe     short loc_140041663
0x1400415f1  lea     rax, aPalSystemWin32_4; "PAL_System_Win32_ThreadCreateWindow"
0x1400415f8  mov     [rsp+2B0h+var_24C], 1CFh
0x140041600  mov     [rsp+2B0h+var_238], rax
0x140041605  lea     rdx, word_14008025E
0x14004160c  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041613  mov     [rsp+2B0h+var_250], 80004005h
0x14004161b  mov     [rsp+2B0h+var_240], rax
0x140041620  lea     rax, aFailedToCreate_23; "Failed to create thread window"
0x140041627  mov     [rsp+2B0h+var_248], rax
0x14004162c  lea     rax, [rsp+2B0h+var_238]
0x140041631  mov     [rsp+2B0h+hWndParent], rax
0x140041636  lea     rax, [rsp+2B0h+var_24C]
0x14004163b  mov     qword ptr [rsp+2B0h+nHeight], rax
0x140041640  lea     rax, [rsp+2B0h+var_240]
0x140041645  mov     qword ptr [rsp+2B0h+nWidth], rax
0x14004164a  lea     rax, [rsp+2B0h+var_250]
0x14004164f  mov     qword ptr [rsp+2B0h+Y], rax
0x140041654  lea     rax, [rsp+2B0h+var_248]
0x140041659  jmp     loc_1400413FA
0x14004165e  mov     [rsi], rax
0x140041661  xor     ebx, ebx
0x140041663  mov     eax, ebx
0x140041665  mov     rcx, [rbp+1B0h+var_20]
0x14004166c  xor     rcx, rsp; StackCookie
0x14004166f  call    __security_check_cookie
0x140041674  lea     r11, [rsp+2B0h+var_10]
0x14004167c  mov     rbx, [r11+28h]
0x140041680  mov     rsi, [r11+30h]
0x140041684  mov     rsp, r11
0x140041687  pop     r15
0x140041689  pop     rdi
0x14004168a  pop     rbp
0x14004168b  retn
```
