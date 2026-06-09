# PAL_System_Win32_TimerCreateWindow(HWND__ * *)

- ea: `0x140041c78`
- end: `0x140041fbc`
- name: `?PAL_System_Win32_TimerCreateWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140041fc4`

## callees

- `0x1400014d4`
- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x140008ce0`
- `0x140041c78`
- `0x140042288`
- `0x14006a120`

## import_xrefs

- `USER32!CreateWindowExW` at `0x140041f0b`
- `USER32!CreateWindowExW` at `0x140041f0b`

## string_xrefs

- `0x140041ce1`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140041d6e`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140041f3c`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140041f50`: `Failed to create timer window`
- `0x140041cc6`: `PAL_System_Win32_TimerCreateWindow`
- `0x140041d53`: `PAL_System_Win32_TimerCreateWindow`
- `0x140041f21`: `PAL_System_Win32_TimerCreateWindow`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_TimerCreateWindow(HWND *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  PVOID *v9; // rcx
  unsigned int v10; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  HWND v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int Y[2]; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v21; // [rsp+68h] [rbp-98h] BYREF
  const char *v22; // [rsp+70h] [rbp-90h] BYREF
  const char *v23; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[526]; // [rsp+82h] [rbp-7Eh] BYREF

  if ( !a1 )
  {
    v5 = -2147024809;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v19 = 232;
      v21 = "PAL_System_Win32_TimerCreateWindow";
      v20 = -2147024809;
      v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v23 = "NULL paramater passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)byte_1400800DD,
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
  v5 = PAL_System_Win32_TimerRegisterWindowClass();
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v20 = 242;
      v23 = "PAL_System_Win32_TimerCreateWindow";
      v19 = v5;
      v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v21 = "Failed to initialize timer window class";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1400880C8,
        (unsigned int)byte_140080143,
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
  memset_0(v25, 0, 0x206u);
  ClassName = 0;
  v8 = StringCchPrintfW(&ClassName, 0x104u, L"%p-%s", &g_TsSystemPalDllModule, L"PAL_SYS_WIN32_TIMER_WNDCLASS");
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
        12,
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
  v13 = CreateWindowExW(0, &ClassName, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0);
  if ( v13 )
  {
    *a1 = v13;
    return 0;
  }
  else if ( (unsigned int)dword_1400880C8 > 2 )
  {
    v20 = 260;
    v23 = "PAL_System_Win32_TimerCreateWindow";
    v19 = -2147467259;
    v22 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
    v21 = "Failed to create timer window";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)byte_140080219,
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
0x140041c78  mov     [rsp-8+arg_8], rbx
0x140041c7d  mov     [rsp-8+arg_10], rsi
0x140041c82  push    rbp
0x140041c83  push    rdi
0x140041c84  push    r15
0x140041c86  lea     rbp, [rsp-1A0h]
0x140041c8e  sub     rsp, 2A0h
0x140041c95  mov     rax, cs:__security_cookie
0x140041c9c  xor     rax, rsp
0x140041c9f  mov     [rbp+1B0h+var_20], rax
0x140041ca6  mov     rsi, rcx
0x140041ca9  test    rcx, rcx
0x140041cac  jnz     loc_140041D39
0x140041cb2  mov     eax, cs:dword_1400880C8
0x140041cb8  mov     ebx, 80070057h
0x140041cbd  cmp     eax, 2
0x140041cc0  jbe     loc_140041F93
0x140041cc6  lea     rax, aPalSystemWin32_7; "PAL_System_Win32_TimerCreateWindow"
0x140041ccd  mov     [rsp+2B0h+var_250], 0E8h
0x140041cd5  mov     [rsp+2B0h+var_248], rax
0x140041cda  lea     rdx, byte_1400800DD
0x140041ce1  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041ce8  mov     [rsp+2B0h+var_24C], ebx
0x140041cec  mov     [rsp+2B0h+var_240], rax
0x140041cf1  lea     rax, aNullParamaterP; "NULL paramater passed"
0x140041cf8  mov     [rsp+2B0h+var_238], rax
0x140041cfd  lea     rax, [rsp+2B0h+var_248]
0x140041d02  mov     [rsp+2B0h+hWndParent], rax
0x140041d07  lea     rax, [rsp+2B0h+var_250]
0x140041d0c  mov     qword ptr [rsp+2B0h+nHeight], rax
0x140041d11  lea     rax, [rsp+2B0h+var_240]
0x140041d16  mov     qword ptr [rsp+2B0h+nWidth], rax
0x140041d1b  lea     rax, [rsp+2B0h+var_24C]
0x140041d20  mov     qword ptr [rsp+2B0h+Y], rax
0x140041d25  lea     rax, [rsp+2B0h+var_238]
0x140041d2a  mov     qword ptr [rsp+2B0h+X], rax
0x140041d2f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140041d34  jmp     loc_140041F93
0x140041d39  call    ?PAL_System_Win32_TimerRegisterWindowClass@@YAJXZ; PAL_System_Win32_TimerRegisterWindowClass(void)
0x140041d3e  mov     ebx, eax
0x140041d40  test    eax, eax
0x140041d42  jns     short loc_140041DBC
0x140041d44  mov     ecx, cs:dword_1400880C8
0x140041d4a  cmp     ecx, 2
0x140041d4d  jbe     loc_140041F93
0x140041d53  lea     rax, aPalSystemWin32_7; "PAL_System_Win32_TimerCreateWindow"
0x140041d5a  mov     [rsp+2B0h+var_24C], 0F2h
0x140041d62  mov     [rsp+2B0h+var_238], rax
0x140041d67  lea     rdx, byte_140080143
0x140041d6e  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041d75  mov     [rsp+2B0h+var_250], ebx
0x140041d79  mov     [rsp+2B0h+var_240], rax
0x140041d7e  lea     rax, aFailedToInitia_8; "Failed to initialize timer window class"
0x140041d85  mov     [rsp+2B0h+var_248], rax
0x140041d8a  lea     rax, [rsp+2B0h+var_238]
0x140041d8f  mov     [rsp+2B0h+hWndParent], rax
0x140041d94  lea     rax, [rsp+2B0h+var_24C]
0x140041d99  mov     qword ptr [rsp+2B0h+nHeight], rax
0x140041d9e  lea     rax, [rsp+2B0h+var_240]
0x140041da3  mov     qword ptr [rsp+2B0h+nWidth], rax
0x140041da8  lea     rax, [rsp+2B0h+var_250]
0x140041dad  mov     qword ptr [rsp+2B0h+Y], rax
0x140041db2  lea     rax, [rsp+2B0h+var_248]
0x140041db7  jmp     loc_140041D2A
0x140041dbc  xor     edx, edx; Val
0x140041dbe  lea     rcx, [rbp+1B0h+var_22E]; void *
0x140041dc2  mov     r8d, 206h; Size
0x140041dc8  call    memset_0
0x140041dcd  xor     eax, eax
0x140041dcf  lea     r9, ?g_TsSystemPalDllModule@@3HA; int g_TsSystemPalDllModule
0x140041dd6  mov     [rbp+1B0h+ClassName], ax
0x140041dda  lea     r8, aPS; "%p-%s"
0x140041de1  lea     rax, aPalSysWin32Tim; "PAL_SYS_WIN32_TIMER_WNDCLASS"
0x140041de8  mov     edx, 104h; unsigned __int64
0x140041ded  lea     rcx, [rbp+1B0h+ClassName]; unsigned __int16 *
0x140041df1  mov     qword ptr [rsp+2B0h+X], rax
0x140041df6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140041dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140041e02  mov     edi, eax
0x140041e04  lea     r15, WPP_GLOBAL_Control
0x140041e0b  test    eax, eax
0x140041e0d  jns     short loc_140041E5F
0x140041e0f  cmp     rcx, r15
0x140041e12  jz      short loc_140041E5F
0x140041e14  test    byte ptr [rcx+1Ch], 8
0x140041e18  jz      short loc_140041E5F
0x140041e1a  cmp     byte ptr [rcx+19h], 2
0x140041e1e  jb      short loc_140041E5F
0x140041e20  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041e25  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x140041e2c  mov     [rsp+2B0h+Y], edi
0x140041e30  mov     qword ptr [rsp+2B0h+X], rcx
0x140041e35  lea     r8, WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids
0x140041e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041e43  mov     edx, 0Ch
0x140041e48  mov     r9d, eax
0x140041e4b  mov     rcx, [rcx+10h]
0x140041e4f  call    WPP_SF_DsD
0x140041e54  mov     rcx, cs:WPP_GLOBAL_Control
0x140041e5b  mov     ebx, edi
0x140041e5d  jmp     short loc_140041E65
0x140041e5f  mov     ebx, edi
0x140041e61  test    edi, edi
0x140041e63  jns     short loc_140041EBB
0x140041e65  cmp     rcx, r15
0x140041e68  jz      loc_140041F93
0x140041e6e  test    byte ptr [rcx+1Ch], 8
0x140041e72  jz      loc_140041F93
0x140041e78  cmp     byte ptr [rcx+19h], 2
0x140041e7c  jb      loc_140041F93
0x140041e82  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041e87  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x140041e8e  mov     [rsp+2B0h+Y], edi
0x140041e92  mov     qword ptr [rsp+2B0h+X], rcx
0x140041e97  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140041e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ea5  mov     edx, 0Ch
0x140041eaa  mov     r9d, eax
0x140041ead  mov     rcx, [rcx+10h]
0x140041eb1  call    WPP_SF_DsD
0x140041eb6  jmp     loc_140041F93
0x140041ebb  mov     [rsp+2B0h+lpParam], 0; lpParam
0x140041ec4  lea     rdx, [rbp+1B0h+ClassName]; lpClassName
0x140041ec8  mov     [rsp+2B0h+hInstance], 0; hInstance
0x140041ed1  xor     r9d, r9d; dwStyle
0x140041ed4  mov     [rsp+2B0h+hMenu], 0; hMenu
0x140041edd  xor     r8d, r8d; lpWindowName
0x140041ee0  mov     [rsp+2B0h+hWndParent], 0; hWndParent
0x140041ee9  xor     ecx, ecx; dwExStyle
0x140041eeb  mov     [rsp+2B0h+nHeight], 0; nHeight
0x140041ef3  mov     [rsp+2B0h+nWidth], 0; nWidth
0x140041efb  mov     [rsp+2B0h+Y], 0; Y
0x140041f03  mov     [rsp+2B0h+X], 0; X
0x140041f0b  call    cs:__imp_CreateWindowExW
0x140041f11  test    rax, rax
0x140041f14  jnz     short loc_140041F8E
0x140041f16  mov     eax, cs:dword_1400880C8
0x140041f1c  cmp     eax, 2
0x140041f1f  jbe     short loc_140041F93
0x140041f21  lea     rax, aPalSystemWin32_7; "PAL_System_Win32_TimerCreateWindow"
0x140041f28  mov     [rsp+2B0h+var_24C], 104h
0x140041f30  mov     [rsp+2B0h+var_238], rax
0x140041f35  lea     rdx, byte_140080219
0x140041f3c  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041f43  mov     [rsp+2B0h+var_250], 80004005h
0x140041f4b  mov     [rsp+2B0h+var_240], rax
0x140041f50  lea     rax, aFailedToCreate_21; "Failed to create timer window"
0x140041f57  mov     [rsp+2B0h+var_248], rax
0x140041f5c  lea     rax, [rsp+2B0h+var_238]
0x140041f61  mov     [rsp+2B0h+hWndParent], rax
0x140041f66  lea     rax, [rsp+2B0h+var_24C]
0x140041f6b  mov     qword ptr [rsp+2B0h+nHeight], rax
0x140041f70  lea     rax, [rsp+2B0h+var_240]
0x140041f75  mov     qword ptr [rsp+2B0h+nWidth], rax
0x140041f7a  lea     rax, [rsp+2B0h+var_250]
0x140041f7f  mov     qword ptr [rsp+2B0h+Y], rax
0x140041f84  lea     rax, [rsp+2B0h+var_248]
0x140041f89  jmp     loc_140041D2A
0x140041f8e  mov     [rsi], rax
0x140041f91  xor     ebx, ebx
0x140041f93  mov     eax, ebx
0x140041f95  mov     rcx, [rbp+1B0h+var_20]
0x140041f9c  xor     rcx, rsp; StackCookie
0x140041f9f  call    __security_check_cookie
0x140041fa4  lea     r11, [rsp+2B0h+var_10]
0x140041fac  mov     rbx, [r11+28h]
0x140041fb0  mov     rsi, [r11+30h]
0x140041fb4  mov     rsp, r11
0x140041fb7  pop     r15
0x140041fb9  pop     rdi
0x140041fba  pop     rbp
0x140041fbb  retn
```
