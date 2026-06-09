# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x14004197c`
- end: `0x140041c2c`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `688`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017a08`

## callees

- `0x1400010c0`
- `0x1400015ec`
- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x140008ce0`
- `0x14004197c`
- `0x14006a120`

## import_xrefs

- `USER32!UnregisterClassW` at `0x140041b50`
- `USER32!UnregisterClassW` at `0x140041b50`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140041af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140041af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041aff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041b5e`

## string_xrefs

- `0x140041b9d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x140041a11`: `PAL_SYS_WIN32_THREAD_WNDCLASS`
- `0x1400419c5`: `Thread window class not registered. Skipping unregister.`
- `0x140041b86`: `PAL_System_Win32_ThreadUnRegisterWindowClass`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_ThreadUnRegisterWindowClass(int a1, __int64 a2, int a3, int a4)
{
  unsigned int v4; // ebx
  int v5; // edi
  PVOID *v6; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v8; // eax
  DWORD LastError; // edi
  unsigned int v10; // eax
  signed int v11; // eax
  int v12; // r8d
  int v13; // r9d
  __int64 v15; // [rsp+28h] [rbp-D8h]
  signed int v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+54h] [rbp-ACh] BYREF
  const char *v18; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v20; // [rsp+68h] [rbp-98h] BYREF
  const char *v21; // [rsp+70h] [rbp-90h] BYREF
  const char *v22; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ClassName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[526]; // [rsp+82h] [rbp-7Eh] BYREF

  phModule = 0;
  if ( !g_PAL_SYS_fThreadWndClassRegistered )
  {
    v4 = 0;
    if ( (unsigned int)dword_1400880C8 > 4 )
    {
      v18 = "Thread window class not registered. Skipping unregister.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        a1,
        (unsigned int)&word_140080546,
        a3,
        a4,
        (__int64)&v18);
    }
    return v4;
  }
  memset_0(v24, 0, 0x206u);
  ClassName = 0;
  v5 = StringCchPrintfW(&ClassName, 0x104u, L"%p-%s", &g_TsSystemPalDllModule, L"PAL_SYS_WIN32_THREAD_WNDCLASS");
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( v5 < 0
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
      v5);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v4 = v5;
LABEL_10:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v15) = v5;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
        v8,
        (__int64)"Failed to get module specific class name",
        v15);
    }
    return v4;
  }
  v4 = v5;
  if ( v5 < 0 )
    goto LABEL_10;
  if ( !GetModuleHandleExW(2u, 0, &phModule) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
        v10,
        LastError);
    }
  }
  if ( UnregisterClassW(&ClassName, phModule) )
  {
    g_PAL_SYS_fThreadWndClassRegistered = 0;
  }
  else
  {
    v11 = GetLastError();
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    else
      v4 = v11;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v16 = v11;
      v20 = "PAL_System_Win32_ThreadUnRegisterWindowClass";
      v17 = 599;
      v21 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v22 = "Failed to unregister window class [Win32err = %d]";
      LODWORD(v18) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)qword_140080188,
        v12,
        v13,
        (__int64)&v22,
        (__int64)&v18,
        (__int64)&v21,
        (__int64)&v17,
        (__int64)&v20,
        (__int64)&v16);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14004197c  push    rbp
0x14004197e  push    rbx
0x14004197f  push    rdi
0x140041980  push    r12
0x140041982  lea     rbp, [rsp-1A8h]
0x14004198a  sub     rsp, 2A8h
0x140041991  mov     rax, cs:__security_cookie
0x140041998  xor     rax, rsp
0x14004199b  mov     [rbp+1C0h+var_30], rax
0x1400419a2  cmp     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x1400419a9  mov     [rsp+2C0h+phModule], 0
0x1400419b2  jnz     short loc_1400419EC
0x1400419b4  mov     eax, cs:dword_1400880C8
0x1400419ba  xor     ebx, ebx
0x1400419bc  cmp     eax, 4
0x1400419bf  jbe     loc_140041C0E
0x1400419c5  lea     rax, aThreadWindowCl; "Thread window class not registered. Ski"...
0x1400419cc  mov     [rsp+2C0h+var_268], rax
0x1400419d1  lea     rdx, word_140080546
0x1400419d8  lea     rax, [rsp+2C0h+var_268]
0x1400419dd  mov     [rsp+2C0h+var_2A0], rax
0x1400419e2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400419e7  jmp     loc_140041C0E
0x1400419ec  xor     edx, edx; Val
0x1400419ee  lea     rcx, [rbp+1C0h+var_23E]; void *
0x1400419f2  mov     r8d, 206h; Size
0x1400419f8  call    memset_0
0x1400419fd  xor     eax, eax
0x1400419ff  lea     r9, ?g_TsSystemPalDllModule@@3HA; int g_TsSystemPalDllModule
0x140041a06  mov     [rbp+1C0h+ClassName], ax
0x140041a0a  lea     r8, aPS; "%p-%s"
0x140041a11  lea     rax, aPalSysWin32Thr; "PAL_SYS_WIN32_THREAD_WNDCLASS"
0x140041a18  mov     edx, 104h; unsigned __int64
0x140041a1d  lea     rcx, [rbp+1C0h+ClassName]; unsigned __int16 *
0x140041a21  mov     [rsp+2C0h+var_2A0], rax
0x140041a26  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140041a2b  mov     edi, eax
0x140041a2d  lea     r12, WPP_GLOBAL_Control
0x140041a34  mov     rax, cs:WPP_GLOBAL_Control
0x140041a3b  test    edi, edi
0x140041a3d  jns     short loc_140041A8F
0x140041a3f  cmp     rax, r12
0x140041a42  jz      short loc_140041A8F
0x140041a44  test    byte ptr [rax+1Ch], 8
0x140041a48  jz      short loc_140041A8F
0x140041a4a  cmp     byte ptr [rax+19h], 2
0x140041a4e  jb      short loc_140041A8F
0x140041a50  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041a55  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x140041a5c  mov     dword ptr [rsp+2C0h+var_298], edi
0x140041a60  mov     [rsp+2C0h+var_2A0], rcx
0x140041a65  lea     r8, WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids
0x140041a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140041a73  mov     edx, 0Ch
0x140041a78  mov     r9d, eax
0x140041a7b  mov     rcx, [rcx+10h]
0x140041a7f  call    WPP_SF_DsD
0x140041a84  mov     rax, cs:WPP_GLOBAL_Control
0x140041a8b  mov     ebx, edi
0x140041a8d  jmp     short loc_140041A95
0x140041a8f  mov     ebx, edi
0x140041a91  test    edi, edi
0x140041a93  jns     short loc_140041AEB
0x140041a95  cmp     rax, r12
0x140041a98  jz      loc_140041C0E
0x140041a9e  test    byte ptr [rax+1Ch], 8
0x140041aa2  jz      loc_140041C0E
0x140041aa8  cmp     byte ptr [rax+19h], 2
0x140041aac  jb      loc_140041C0E
0x140041ab2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041ab7  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x140041abe  mov     dword ptr [rsp+2C0h+var_298], edi
0x140041ac2  mov     [rsp+2C0h+var_2A0], rcx
0x140041ac7  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140041ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140041ad5  mov     edx, 14h
0x140041ada  mov     r9d, eax
0x140041add  mov     rcx, [rcx+10h]
0x140041ae1  call    WPP_SF_DsD
0x140041ae6  jmp     loc_140041C0E
0x140041aeb  xor     edx, edx; lpModuleName
0x140041aed  lea     r8, [rsp+2C0h+phModule]; phModule
0x140041af2  lea     ecx, [rdx+2]; dwFlags
0x140041af5  call    cs:__imp_GetModuleHandleExW
0x140041afb  test    eax, eax
0x140041afd  jnz     short loc_140041B47
0x140041aff  call    cs:__imp_GetLastError
0x140041b05  mov     edi, eax
0x140041b07  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b0e  cmp     rcx, r12
0x140041b11  jz      short loc_140041B47
0x140041b13  test    byte ptr [rcx+1Ch], 8
0x140041b17  jz      short loc_140041B47
0x140041b19  cmp     byte ptr [rcx+19h], 2
0x140041b1d  jb      short loc_140041B47
0x140041b1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041b24  mov     rcx, cs:WPP_GLOBAL_Control
0x140041b2b  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140041b32  mov     edx, 15h
0x140041b37  mov     dword ptr [rsp+2C0h+var_2A0], edi
0x140041b3b  mov     r9d, eax
0x140041b3e  mov     rcx, [rcx+10h]
0x140041b42  call    WPP_SF_Dd
0x140041b47  mov     rdx, [rsp+2C0h+phModule]; hInstance
0x140041b4c  lea     rcx, [rbp+1C0h+ClassName]; lpClassName
0x140041b50  call    cs:__imp_UnregisterClassW
0x140041b56  test    eax, eax
0x140041b58  jnz     loc_140041C04
0x140041b5e  call    cs:__imp_GetLastError
0x140041b64  mov     ecx, eax
0x140041b66  test    eax, eax
0x140041b68  jg      short loc_140041B6E
0x140041b6a  mov     ebx, eax
0x140041b6c  jmp     short loc_140041B77
0x140041b6e  movzx   ebx, cx
0x140041b71  or      ebx, 80070000h
0x140041b77  mov     eax, cs:dword_1400880C8
0x140041b7d  cmp     eax, 2
0x140041b80  jbe     loc_140041C0E
0x140041b86  lea     rax, aPalSystemWin32_2; "PAL_System_Win32_ThreadUnRegisterWindow"...
0x140041b8d  mov     [rsp+2C0h+var_270], ecx
0x140041b91  mov     [rsp+2C0h+var_258], rax
0x140041b96  lea     rdx, qword_140080188
0x140041b9d  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140041ba4  mov     [rsp+2C0h+var_26C], 257h
0x140041bac  mov     [rsp+2C0h+var_250], rax
0x140041bb1  lea     rax, aFailedToUnregi_1; "Failed to unregister window class [Win3"...
0x140041bb8  mov     [rsp+2C0h+var_248], rax
0x140041bbd  lea     rax, [rsp+2C0h+var_270]
0x140041bc2  mov     [rsp+2C0h+var_278], rax
0x140041bc7  lea     rax, [rsp+2C0h+var_258]
0x140041bcc  mov     [rsp+2C0h+var_280], rax
0x140041bd1  lea     rax, [rsp+2C0h+var_26C]
0x140041bd6  mov     [rsp+2C0h+var_288], rax
0x140041bdb  lea     rax, [rsp+2C0h+var_250]
0x140041be0  mov     [rsp+2C0h+var_290], rax
0x140041be5  lea     rax, [rsp+2C0h+var_268]
0x140041bea  mov     [rsp+2C0h+var_298], rax
0x140041bef  lea     rax, [rsp+2C0h+var_248]
0x140041bf4  mov     [rsp+2C0h+var_2A0], rax
0x140041bf9  mov     dword ptr [rsp+2C0h+var_268], ebx
0x140041bfd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140041c02  jmp     short loc_140041C0E
0x140041c04  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 0; int g_PAL_SYS_fThreadWndClassRegistered
0x140041c0e  mov     eax, ebx
0x140041c10  mov     rcx, [rbp+1C0h+var_30]
0x140041c17  xor     rcx, rsp; StackCookie
0x140041c1a  call    __security_check_cookie
0x140041c1f  add     rsp, 2A8h
0x140041c26  pop     r12
0x140041c28  pop     rdi
0x140041c29  pop     rbx
0x140041c2a  pop     rbp
0x140041c2b  retn
```
