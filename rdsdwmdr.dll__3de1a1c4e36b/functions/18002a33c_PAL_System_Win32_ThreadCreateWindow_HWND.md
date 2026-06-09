# PAL_System_Win32_ThreadCreateWindow(HWND__ * *)

- ea: `0x18002a33c`
- end: `0x18002a5ff`
- name: `?PAL_System_Win32_ThreadCreateWindow@@YAJPEAPEAUHWND__@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002b590`

## callees

- `0x18000160c`
- `0x18001d114`
- `0x18001ef44`
- `0x18002a33c`
- `0x18002a608`
- `0x18002b4b8`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `USER32!CreateWindowExW` at `0x18002a551`
- `USER32!CreateWindowExW` at `0x18002a551`

## string_xrefs

- `0x18002a3a2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18002a440`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18002a582`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18002a387`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18002a425`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18002a567`: `PAL_System_Win32_ThreadCreateWindow`
- `0x18002a450`: `Failed to initialize thread window class`
- `0x18002a596`: `Failed to create thread window`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadCreateWindow(HWND *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+64h] [rbp-9Ch] BYREF
  const char *v17; // [rsp+68h] [rbp-98h] BYREF
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( a1 )
  {
    memset_0(ClassName, 0, 0x208u);
    ModuleSpecificClassName = PAL_System_Win32_ThreadRegisterWindowClass();
    if ( ModuleSpecificClassName >= 0 )
    {
      ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v6, ClassName, v7);
      if ( ModuleSpecificClassName >= 0 )
      {
        Window = CreateWindowExW(0, ClassName, 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, 0, 0);
        if ( Window )
        {
          *a1 = Window;
          return 0;
        }
        else if ( (unsigned int)dword_180044008 > 2 )
        {
          v16 = 463;
          v19 = "PAL_System_Win32_ThreadCreateWindow";
          v15 = -2147467259;
          v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v17 = "Failed to create thread window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v11,
            (__int64)qword_180040198,
            v12,
            v13,
            (const unsigned __int16 **)&v17,
            (__int64)&v15,
            (const unsigned __int16 **)&v18,
            (__int64)&v16,
            (const unsigned __int16 **)&v19);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Failed to get module specific class name",
          ModuleSpecificClassName);
      }
    }
    else if ( (unsigned int)dword_180044008 > 2 )
    {
      v16 = 447;
      v19 = "PAL_System_Win32_ThreadCreateWindow";
      v15 = ModuleSpecificClassName;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v17 = "Failed to initialize thread window class";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)byte_1800401DD,
        v7,
        v8,
        (const unsigned __int16 **)&v17,
        (__int64)&v15,
        (const unsigned __int16 **)&v18,
        (__int64)&v16,
        (const unsigned __int16 **)&v19);
    }
  }
  else
  {
    ModuleSpecificClassName = -2147024809;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v15 = 435;
      v17 = "PAL_System_Win32_ThreadCreateWindow";
      v16 = -2147024809;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v19 = "NULL paramater passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (__int64)&word_18004026E,
        a3,
        a4,
        (const unsigned __int16 **)&v19,
        (__int64)&v16,
        (const unsigned __int16 **)&v18,
        (__int64)&v15,
        (const unsigned __int16 **)&v17);
    }
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x18002a33c  mov     [rsp-8+arg_8], rbx
0x18002a341  mov     [rsp-8+arg_10], rdi
0x18002a346  push    rbp
0x18002a347  lea     rbp, [rsp-1A0h]
0x18002a34f  sub     rsp, 2A0h
0x18002a356  mov     rax, cs:__security_cookie
0x18002a35d  xor     rax, rsp
0x18002a360  mov     [rbp+1A0h+var_10], rax
0x18002a367  mov     rdi, rcx
0x18002a36a  test    rcx, rcx
0x18002a36d  jnz     loc_18002A3FA
0x18002a373  mov     eax, cs:dword_180044008
0x18002a379  mov     ebx, 80070057h
0x18002a37e  cmp     eax, 2
0x18002a381  jbe     loc_18002A5D9
0x18002a387  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18002a38e  mov     [rsp+2A0h+var_240], 1B3h
0x18002a396  mov     [rsp+2A0h+var_238], rax
0x18002a39b  lea     rdx, word_18004026E
0x18002a3a2  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a3a9  mov     [rsp+2A0h+var_23C], ebx
0x18002a3ad  mov     [rsp+2A0h+var_230], rax
0x18002a3b2  lea     rax, aNullParamaterP; "NULL paramater passed"
0x18002a3b9  mov     [rsp+2A0h+var_228], rax
0x18002a3be  lea     rax, [rsp+2A0h+var_238]
0x18002a3c3  mov     [rsp+2A0h+hWndParent], rax
0x18002a3c8  lea     rax, [rsp+2A0h+var_240]
0x18002a3cd  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18002a3d2  lea     rax, [rsp+2A0h+var_230]
0x18002a3d7  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18002a3dc  lea     rax, [rsp+2A0h+var_23C]
0x18002a3e1  mov     qword ptr [rsp+2A0h+Y], rax
0x18002a3e6  lea     rax, [rsp+2A0h+var_228]
0x18002a3eb  mov     qword ptr [rsp+2A0h+X], rax
0x18002a3f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002a3f5  jmp     loc_18002A5D9
0x18002a3fa  xor     edx, edx; Val
0x18002a3fc  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18002a400  mov     r8d, 208h; Size
0x18002a406  call    memset_0
0x18002a40b  call    ?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ; PAL_System_Win32_ThreadRegisterWindowClass(void)
0x18002a410  mov     ebx, eax
0x18002a412  test    eax, eax
0x18002a414  jns     short loc_18002A48E
0x18002a416  mov     ecx, cs:dword_180044008
0x18002a41c  cmp     ecx, 2
0x18002a41f  jbe     loc_18002A5D9
0x18002a425  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18002a42c  mov     [rsp+2A0h+var_23C], 1BFh
0x18002a434  mov     [rsp+2A0h+var_228], rax
0x18002a439  lea     rdx, byte_1800401DD
0x18002a440  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a447  mov     [rsp+2A0h+var_240], ebx
0x18002a44b  mov     [rsp+2A0h+var_230], rax
0x18002a450  lea     rax, aFailedToInitia_1; "Failed to initialize thread window clas"...
0x18002a457  mov     [rsp+2A0h+var_238], rax
0x18002a45c  lea     rax, [rsp+2A0h+var_228]
0x18002a461  mov     [rsp+2A0h+hWndParent], rax
0x18002a466  lea     rax, [rsp+2A0h+var_23C]
0x18002a46b  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18002a470  lea     rax, [rsp+2A0h+var_230]
0x18002a475  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18002a47a  lea     rax, [rsp+2A0h+var_240]
0x18002a47f  mov     qword ptr [rsp+2A0h+Y], rax
0x18002a484  lea     rax, [rsp+2A0h+var_238]
0x18002a489  jmp     loc_18002A3EB
0x18002a48e  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x18002a492  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x18002a497  mov     ebx, eax
0x18002a499  test    eax, eax
0x18002a49b  jns     short loc_18002A501
0x18002a49d  mov     rax, cs:WPP_GLOBAL_Control
0x18002a4a4  lea     rcx, WPP_GLOBAL_Control
0x18002a4ab  cmp     rax, rcx
0x18002a4ae  jz      loc_18002A5D9
0x18002a4b4  test    byte ptr [rax+1Ch], 8
0x18002a4b8  jz      loc_18002A5D9
0x18002a4be  cmp     byte ptr [rax+19h], 2
0x18002a4c2  jb      loc_18002A5D9
0x18002a4c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a4cd  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x18002a4d4  mov     [rsp+2A0h+Y], ebx
0x18002a4d8  mov     qword ptr [rsp+2A0h+X], rcx
0x18002a4dd  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002a4e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4eb  mov     edx, 11h
0x18002a4f0  mov     r9d, eax
0x18002a4f3  mov     rcx, [rcx+10h]
0x18002a4f7  call    WPP_SF_DsD
0x18002a4fc  jmp     loc_18002A5D9
0x18002a501  mov     [rsp+2A0h+lpParam], 0; lpParam
0x18002a50a  lea     rdx, [rbp+1A0h+ClassName]; lpClassName
0x18002a50e  mov     [rsp+2A0h+hInstance], 0; hInstance
0x18002a517  xor     r9d, r9d; dwStyle
0x18002a51a  mov     [rsp+2A0h+hMenu], 0; hMenu
0x18002a523  xor     r8d, r8d; lpWindowName
0x18002a526  mov     [rsp+2A0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18002a52f  xor     ecx, ecx; dwExStyle
0x18002a531  mov     [rsp+2A0h+nHeight], 0; nHeight
0x18002a539  mov     [rsp+2A0h+nWidth], 0; nWidth
0x18002a541  mov     [rsp+2A0h+Y], 0; Y
0x18002a549  mov     [rsp+2A0h+X], 0; X
0x18002a551  call    cs:__imp_CreateWindowExW
0x18002a557  test    rax, rax
0x18002a55a  jnz     short loc_18002A5D4
0x18002a55c  mov     eax, cs:dword_180044008
0x18002a562  cmp     eax, 2
0x18002a565  jbe     short loc_18002A5D9
0x18002a567  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadCreateWindow"
0x18002a56e  mov     [rsp+2A0h+var_23C], 1CFh
0x18002a576  mov     [rsp+2A0h+var_228], rax
0x18002a57b  lea     rdx, qword_180040198
0x18002a582  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a589  mov     [rsp+2A0h+var_240], 80004005h
0x18002a591  mov     [rsp+2A0h+var_230], rax
0x18002a596  lea     rax, aFailedToCreate_12; "Failed to create thread window"
0x18002a59d  mov     [rsp+2A0h+var_238], rax
0x18002a5a2  lea     rax, [rsp+2A0h+var_228]
0x18002a5a7  mov     [rsp+2A0h+hWndParent], rax
0x18002a5ac  lea     rax, [rsp+2A0h+var_23C]
0x18002a5b1  mov     qword ptr [rsp+2A0h+nHeight], rax
0x18002a5b6  lea     rax, [rsp+2A0h+var_230]
0x18002a5bb  mov     qword ptr [rsp+2A0h+nWidth], rax
0x18002a5c0  lea     rax, [rsp+2A0h+var_240]
0x18002a5c5  mov     qword ptr [rsp+2A0h+Y], rax
0x18002a5ca  lea     rax, [rsp+2A0h+var_238]
0x18002a5cf  jmp     loc_18002A3EB
0x18002a5d4  mov     [rdi], rax
0x18002a5d7  xor     ebx, ebx
0x18002a5d9  mov     eax, ebx
0x18002a5db  mov     rcx, [rbp+1A0h+var_10]
0x18002a5e2  xor     rcx, rsp; StackCookie
0x18002a5e5  call    __security_check_cookie
0x18002a5ea  lea     r11, [rsp+2A0h+var_s0]
0x18002a5f2  mov     rbx, [r11+18h]
0x18002a5f6  mov     rdi, [r11+20h]
0x18002a5fa  mov     rsp, r11
0x18002a5fd  pop     rbp
0x18002a5fe  retn
```
