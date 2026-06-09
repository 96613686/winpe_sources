# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x18002a888`
- end: `0x18002aad1`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `585`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001e550`

## callees

- `0x1800010f8`
- `0x180001f98`
- `0x18001d04c`
- `0x18001d114`
- `0x18001ef44`
- `0x18002a888`
- `0x18002b4b8`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a98b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a98b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9fb`
- `USER32!UnregisterClassW` at `0x18002a9ed`
- `USER32!UnregisterClassW` at `0x18002a9ed`

## string_xrefs

- `0x18002aa3a`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18002a8d6`: `Thread window class not registered. Skipping unregister.`
- `0x18002aa23`: `PAL_System_Win32_ThreadUnRegisterWindowClass`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadUnRegisterWindowClass(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // r8d
  unsigned int v7; // eax
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  signed int v14; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+54h] [rbp-ACh] BYREF
  const char *v16; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v18; // [rsp+68h] [rbp-98h] BYREF
  const char *v19; // [rsp+70h] [rbp-90h] BYREF
  const char *v20; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName[264]; // [rsp+80h] [rbp-80h] BYREF

  phModule = 0;
  if ( g_PAL_SYS_fThreadWndClassRegistered )
  {
    memset_0(ClassName, 0, 0x208u);
    ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v5, ClassName, v6);
    if ( ModuleSpecificClassName >= 0 )
    {
      if ( !GetModuleHandleExW(2u, 0, &phModule) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
      }
      if ( UnregisterClassW(ClassName, phModule) )
      {
        g_PAL_SYS_fThreadWndClassRegistered = 0;
      }
      else
      {
        v10 = GetLastError();
        if ( v10 > 0 )
          ModuleSpecificClassName = (unsigned __int16)v10 | 0x80070000;
        else
          ModuleSpecificClassName = v10;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v14 = v10;
          v18 = "PAL_System_Win32_ThreadUnRegisterWindowClass";
          v15 = 599;
          v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v20 = "Failed to unregister window class [Win32err = %d]";
          LODWORD(v16) = ModuleSpecificClassName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)v10,
            (__int64)&dword_18004014C,
            v11,
            v12,
            (const unsigned __int16 **)&v20,
            (__int64)&v16,
            (const unsigned __int16 **)&v19,
            (__int64)&v15,
            (const unsigned __int16 **)&v18,
            (__int64)&v14);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
        v7,
        (__int64)"Failed to get module specific class name",
        ModuleSpecificClassName);
    }
  }
  else
  {
    ModuleSpecificClassName = 0;
    if ( (unsigned int)dword_180044008 > 4 )
    {
      v16 = "Thread window class not registered. Skipping unregister.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (__int64)qword_180040320,
        a3,
        a4,
        (const unsigned __int16 **)&v16);
    }
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x18002a888  mov     [rsp-8+arg_0], rbx
0x18002a88d  mov     [rsp-8+arg_8], rdi
0x18002a892  push    rbp
0x18002a893  lea     rbp, [rsp-1A0h]
0x18002a89b  sub     rsp, 2A0h
0x18002a8a2  mov     rax, cs:__security_cookie
0x18002a8a9  xor     rax, rsp
0x18002a8ac  mov     [rbp+1A0h+var_10], rax
0x18002a8b3  cmp     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x18002a8ba  mov     [rsp+2A0h+phModule], 0
0x18002a8c3  jnz     short loc_18002A8FD
0x18002a8c5  mov     eax, cs:dword_180044008
0x18002a8cb  xor     ebx, ebx
0x18002a8cd  cmp     eax, 4
0x18002a8d0  jbe     loc_18002AAAB
0x18002a8d6  lea     rax, aThreadWindowCl; "Thread window class not registered. Ski"...
0x18002a8dd  mov     [rsp+2A0h+var_248], rax
0x18002a8e2  lea     rdx, qword_180040320
0x18002a8e9  lea     rax, [rsp+2A0h+var_248]
0x18002a8ee  mov     [rsp+2A0h+var_280], rax
0x18002a8f3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002a8f8  jmp     loc_18002AAAB
0x18002a8fd  xor     edx, edx; Val
0x18002a8ff  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18002a903  mov     r8d, 208h; Size
0x18002a909  call    memset_0
0x18002a90e  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x18002a912  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x18002a917  mov     ebx, eax
0x18002a919  test    eax, eax
0x18002a91b  jns     short loc_18002A981
0x18002a91d  mov     rax, cs:WPP_GLOBAL_Control
0x18002a924  lea     rcx, WPP_GLOBAL_Control
0x18002a92b  cmp     rax, rcx
0x18002a92e  jz      loc_18002AAAB
0x18002a934  test    byte ptr [rax+1Ch], 8
0x18002a938  jz      loc_18002AAAB
0x18002a93e  cmp     byte ptr [rax+19h], 2
0x18002a942  jb      loc_18002AAAB
0x18002a948  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a94d  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x18002a954  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18002a958  mov     [rsp+2A0h+var_280], rcx
0x18002a95d  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002a964  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a96b  mov     edx, 14h
0x18002a970  mov     r9d, eax
0x18002a973  mov     rcx, [rcx+10h]
0x18002a977  call    WPP_SF_DsD
0x18002a97c  jmp     loc_18002AAAB
0x18002a981  xor     edx, edx; lpModuleName
0x18002a983  lea     r8, [rsp+2A0h+phModule]; phModule
0x18002a988  lea     ecx, [rdx+2]; dwFlags
0x18002a98b  call    cs:__imp_GetModuleHandleExW
0x18002a991  test    eax, eax
0x18002a993  jnz     short loc_18002A9E4
0x18002a995  call    cs:__imp_GetLastError
0x18002a99b  mov     edi, eax
0x18002a99d  mov     rdx, cs:WPP_GLOBAL_Control
0x18002a9a4  lea     rcx, WPP_GLOBAL_Control
0x18002a9ab  cmp     rdx, rcx
0x18002a9ae  jz      short loc_18002A9E4
0x18002a9b0  test    byte ptr [rdx+1Ch], 8
0x18002a9b4  jz      short loc_18002A9E4
0x18002a9b6  cmp     byte ptr [rdx+19h], 2
0x18002a9ba  jb      short loc_18002A9E4
0x18002a9bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9c8  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002a9cf  mov     edx, 15h
0x18002a9d4  mov     dword ptr [rsp+2A0h+var_280], edi
0x18002a9d8  mov     r9d, eax
0x18002a9db  mov     rcx, [rcx+10h]
0x18002a9df  call    WPP_SF_Dd
0x18002a9e4  mov     rdx, [rsp+2A0h+phModule]; hInstance
0x18002a9e9  lea     rcx, [rbp+1A0h+ClassName]; lpClassName
0x18002a9ed  call    cs:__imp_UnregisterClassW
0x18002a9f3  test    eax, eax
0x18002a9f5  jnz     loc_18002AAA1
0x18002a9fb  call    cs:__imp_GetLastError
0x18002aa01  mov     ecx, eax
0x18002aa03  test    eax, eax
0x18002aa05  jg      short loc_18002AA0B
0x18002aa07  mov     ebx, eax
0x18002aa09  jmp     short loc_18002AA14
0x18002aa0b  movzx   ebx, cx
0x18002aa0e  or      ebx, 80070000h
0x18002aa14  mov     eax, cs:dword_180044008
0x18002aa1a  cmp     eax, 2
0x18002aa1d  jbe     loc_18002AAAB
0x18002aa23  lea     rax, aPalSystemWin32_0; "PAL_System_Win32_ThreadUnRegisterWindow"...
0x18002aa2a  mov     [rsp+2A0h+var_250], ecx
0x18002aa2e  mov     [rsp+2A0h+var_238], rax
0x18002aa33  lea     rdx, dword_18004014C
0x18002aa3a  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002aa41  mov     [rsp+2A0h+var_24C], 257h
0x18002aa49  mov     [rsp+2A0h+var_230], rax
0x18002aa4e  lea     rax, aFailedToUnregi_1; "Failed to unregister window class [Win3"...
0x18002aa55  mov     [rsp+2A0h+var_228], rax
0x18002aa5a  lea     rax, [rsp+2A0h+var_250]
0x18002aa5f  mov     [rsp+2A0h+var_258], rax
0x18002aa64  lea     rax, [rsp+2A0h+var_238]
0x18002aa69  mov     [rsp+2A0h+var_260], rax
0x18002aa6e  lea     rax, [rsp+2A0h+var_24C]
0x18002aa73  mov     [rsp+2A0h+var_268], rax
0x18002aa78  lea     rax, [rsp+2A0h+var_230]
0x18002aa7d  mov     [rsp+2A0h+var_270], rax
0x18002aa82  lea     rax, [rsp+2A0h+var_248]
0x18002aa87  mov     [rsp+2A0h+var_278], rax
0x18002aa8c  lea     rax, [rsp+2A0h+var_228]
0x18002aa91  mov     [rsp+2A0h+var_280], rax
0x18002aa96  mov     dword ptr [rsp+2A0h+var_248], ebx
0x18002aa9a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002aa9f  jmp     short loc_18002AAAB
0x18002aaa1  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x18002aaab  mov     eax, ebx
0x18002aaad  mov     rcx, [rbp+1A0h+var_10]
0x18002aab4  xor     rcx, rsp; StackCookie
0x18002aab7  call    __security_check_cookie
0x18002aabc  lea     r11, [rsp+2A0h+var_s0]
0x18002aac4  mov     rbx, [r11+10h]
0x18002aac8  mov     rdi, [r11+18h]
0x18002aacc  mov     rsp, r11
0x18002aacf  pop     rbp
0x18002aad0  retn
```
