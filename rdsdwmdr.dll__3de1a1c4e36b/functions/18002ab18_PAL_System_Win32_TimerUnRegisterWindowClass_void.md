# PAL_System_Win32_TimerUnRegisterWindowClass(void)

- ea: `0x18002ab18`
- end: `0x18002ad61`
- name: `?PAL_System_Win32_TimerUnRegisterWindowClass@@YAJXZ`
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
- `0x18002ab18`
- `0x18002b4b8`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ac1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ac1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac8b`
- `USER32!UnregisterClassW` at `0x18002ac7d`
- `USER32!UnregisterClassW` at `0x18002ac7d`

## string_xrefs

- `0x18002acca`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_TimerUnRegisterWindowClass(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int ModuleSpecificClassName; // ebx
  const unsigned __int16 *v5; // rcx
  unsigned int v6; // r8d
  int v7; // eax
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
  if ( g_PAL_SYS_fTimerWndClassRegistered )
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
            16,
            WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
      }
      if ( UnregisterClassW(ClassName, phModule) )
      {
        g_PAL_SYS_fTimerWndClassRegistered = 0;
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
          v18 = "PAL_System_Win32_TimerUnRegisterWindowClass";
          v15 = 396;
          v19 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
          v20 = "Failed to unregister window class [Win32err = %d]";
          LODWORD(v16) = ModuleSpecificClassName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)v10,
            (__int64)&dword_1800402D4,
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
        15,
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
      v16 = "Timer window class not registered. Skipping unregister.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (__int64)byte_1800402B3,
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
0x18002ab18  mov     [rsp-8+arg_0], rbx
0x18002ab1d  mov     [rsp-8+arg_8], rdi
0x18002ab22  push    rbp
0x18002ab23  lea     rbp, [rsp-1A0h]
0x18002ab2b  sub     rsp, 2A0h
0x18002ab32  mov     rax, cs:__security_cookie
0x18002ab39  xor     rax, rsp
0x18002ab3c  mov     [rbp+1A0h+var_10], rax
0x18002ab43  cmp     cs:?g_PAL_SYS_fTimerWndClassRegistered@@3HA, 0; int g_PAL_SYS_fTimerWndClassRegistered
0x18002ab4a  mov     [rsp+2A0h+phModule], 0
0x18002ab53  jnz     short loc_18002AB8D
0x18002ab55  mov     eax, cs:dword_180044008
0x18002ab5b  xor     ebx, ebx
0x18002ab5d  cmp     eax, 4
0x18002ab60  jbe     loc_18002AD3B
0x18002ab66  lea     rax, aTimerWindowCla; "Timer window class not registered. Skip"...
0x18002ab6d  mov     [rsp+2A0h+var_248], rax
0x18002ab72  lea     rdx, byte_1800402B3
0x18002ab79  lea     rax, [rsp+2A0h+var_248]
0x18002ab7e  mov     [rsp+2A0h+var_280], rax
0x18002ab83  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002ab88  jmp     loc_18002AD3B
0x18002ab8d  xor     edx, edx; Val
0x18002ab8f  lea     rcx, [rbp+1A0h+ClassName]; void *
0x18002ab93  mov     r8d, 208h; Size
0x18002ab99  call    memset_0
0x18002ab9e  lea     rdx, [rbp+1A0h+ClassName]; unsigned __int16 *
0x18002aba2  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x18002aba7  mov     ebx, eax
0x18002aba9  test    eax, eax
0x18002abab  jns     short loc_18002AC11
0x18002abad  mov     rax, cs:WPP_GLOBAL_Control
0x18002abb4  lea     rcx, WPP_GLOBAL_Control
0x18002abbb  cmp     rax, rcx
0x18002abbe  jz      loc_18002AD3B
0x18002abc4  test    byte ptr [rax+1Ch], 8
0x18002abc8  jz      loc_18002AD3B
0x18002abce  cmp     byte ptr [rax+19h], 2
0x18002abd2  jb      loc_18002AD3B
0x18002abd8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002abdd  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x18002abe4  mov     dword ptr [rsp+2A0h+var_278], ebx
0x18002abe8  mov     [rsp+2A0h+var_280], rcx
0x18002abed  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002abf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abfb  mov     edx, 0Fh
0x18002ac00  mov     r9d, eax
0x18002ac03  mov     rcx, [rcx+10h]
0x18002ac07  call    WPP_SF_DsD
0x18002ac0c  jmp     loc_18002AD3B
0x18002ac11  xor     edx, edx; lpModuleName
0x18002ac13  lea     r8, [rsp+2A0h+phModule]; phModule
0x18002ac18  lea     ecx, [rdx+2]; dwFlags
0x18002ac1b  call    cs:__imp_GetModuleHandleExW
0x18002ac21  test    eax, eax
0x18002ac23  jnz     short loc_18002AC74
0x18002ac25  call    cs:__imp_GetLastError
0x18002ac2b  mov     edi, eax
0x18002ac2d  mov     rdx, cs:WPP_GLOBAL_Control
0x18002ac34  lea     rcx, WPP_GLOBAL_Control
0x18002ac3b  cmp     rdx, rcx
0x18002ac3e  jz      short loc_18002AC74
0x18002ac40  test    byte ptr [rdx+1Ch], 8
0x18002ac44  jz      short loc_18002AC74
0x18002ac46  cmp     byte ptr [rdx+19h], 2
0x18002ac4a  jb      short loc_18002AC74
0x18002ac4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002ac51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac58  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002ac5f  mov     edx, 10h
0x18002ac64  mov     dword ptr [rsp+2A0h+var_280], edi
0x18002ac68  mov     r9d, eax
0x18002ac6b  mov     rcx, [rcx+10h]
0x18002ac6f  call    WPP_SF_Dd
0x18002ac74  mov     rdx, [rsp+2A0h+phModule]; hInstance
0x18002ac79  lea     rcx, [rbp+1A0h+ClassName]; lpClassName
0x18002ac7d  call    cs:__imp_UnregisterClassW
0x18002ac83  test    eax, eax
0x18002ac85  jnz     loc_18002AD31
0x18002ac8b  call    cs:__imp_GetLastError
0x18002ac91  mov     ecx, eax
0x18002ac93  test    eax, eax
0x18002ac95  jg      short loc_18002AC9B
0x18002ac97  mov     ebx, eax
0x18002ac99  jmp     short loc_18002ACA4
0x18002ac9b  movzx   ebx, cx
0x18002ac9e  or      ebx, 80070000h
0x18002aca4  mov     eax, cs:dword_180044008
0x18002acaa  cmp     eax, 2
0x18002acad  jbe     loc_18002AD3B
0x18002acb3  lea     rax, aPalSystemWin32_3; "PAL_System_Win32_TimerUnRegisterWindowC"...
0x18002acba  mov     [rsp+2A0h+var_250], ecx
0x18002acbe  mov     [rsp+2A0h+var_238], rax
0x18002acc3  lea     rdx, dword_1800402D4
0x18002acca  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002acd1  mov     [rsp+2A0h+var_24C], 18Ch
0x18002acd9  mov     [rsp+2A0h+var_230], rax
0x18002acde  lea     rax, aFailedToUnregi_1; "Failed to unregister window class [Win3"...
0x18002ace5  mov     [rsp+2A0h+var_228], rax
0x18002acea  lea     rax, [rsp+2A0h+var_250]
0x18002acef  mov     [rsp+2A0h+var_258], rax
0x18002acf4  lea     rax, [rsp+2A0h+var_238]
0x18002acf9  mov     [rsp+2A0h+var_260], rax
0x18002acfe  lea     rax, [rsp+2A0h+var_24C]
0x18002ad03  mov     [rsp+2A0h+var_268], rax
0x18002ad08  lea     rax, [rsp+2A0h+var_230]
0x18002ad0d  mov     [rsp+2A0h+var_270], rax
0x18002ad12  lea     rax, [rsp+2A0h+var_248]
0x18002ad17  mov     [rsp+2A0h+var_278], rax
0x18002ad1c  lea     rax, [rsp+2A0h+var_228]
0x18002ad21  mov     [rsp+2A0h+var_280], rax
0x18002ad26  mov     dword ptr [rsp+2A0h+var_248], ebx
0x18002ad2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002ad2f  jmp     short loc_18002AD3B
0x18002ad31  mov     cs:?g_PAL_SYS_fTimerWndClassRegistered@@3HA, 0; int g_PAL_SYS_fTimerWndClassRegistered
0x18002ad3b  mov     eax, ebx
0x18002ad3d  mov     rcx, [rbp+1A0h+var_10]
0x18002ad44  xor     rcx, rsp; StackCookie
0x18002ad47  call    __security_check_cookie
0x18002ad4c  lea     r11, [rsp+2A0h+var_s0]
0x18002ad54  mov     rbx, [r11+10h]
0x18002ad58  mov     rdi, [r11+18h]
0x18002ad5c  mov     rsp, r11
0x18002ad5f  pop     rbp
0x18002ad60  retn
```
