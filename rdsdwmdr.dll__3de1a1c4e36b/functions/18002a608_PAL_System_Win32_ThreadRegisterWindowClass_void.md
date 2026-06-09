# PAL_System_Win32_ThreadRegisterWindowClass(void)

- ea: `0x18002a608`
- end: `0x18002a881`
- name: `?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ`
- size: `633`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002a33c`

## callees

- `0x180001f98`
- `0x18001d04c`
- `0x18001d114`
- `0x18001ef44`
- `0x18002a608`
- `0x18002b4b8`
- `0x18002b93a`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a6d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002a6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a795`
- `USER32!RegisterClassExW` at `0x18002a78c`
- `USER32!RegisterClassExW` at `0x18002a78c`
- `USER32!GetClassInfoExW` at `0x18002a738`
- `USER32!GetClassInfoExW` at `0x18002a738`

## string_xrefs

- `0x18002a7e8`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18002a7d1`: `PAL_System_Win32_ThreadRegisterWindowClass`

## pseudocode

```c
__int64 PAL_System_Win32_ThreadRegisterWindowClass(void)
{
  const unsigned __int16 *v0; // rcx
  unsigned int v1; // r8d
  signed int ModuleSpecificClassName; // ebx
  unsigned int v3; // eax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  ATOM v6; // bx
  signed int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  signed int v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh] BYREF
  signed int v13; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v15; // [rsp+68h] [rbp-98h] BYREF
  const char *v16; // [rsp+70h] [rbp-90h] BYREF
  const char *v17; // [rsp+78h] [rbp-88h] BYREF
  tagWNDCLASSEXW wcx; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szClass[264]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  phModule = 0;
  memset_0(szClass, 0, 0x208u);
  ModuleSpecificClassName = PAL_System_Win32_GetModuleSpecificClassName(v0, szClass, v1);
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
          19,
          WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
    }
    if ( GetClassInfoExW(0, szClass, &wcx) )
      goto LABEL_19;
    wcx.cbSize = 80;
    wcx.lpfnWndProc = (WNDPROC)PAL_System_Win32_ThreadWndProc;
    wcx.hInstance = phModule;
    wcx.style = 3;
    wcx.lpszClassName = szClass;
    *(_QWORD *)&wcx.cbClsExtra = 0;
    memset(&wcx.hIcon, 0, 32);
    wcx.hIconSm = 0;
    v6 = RegisterClassExW(&wcx);
    v7 = GetLastError();
    if ( v6 || v7 == 1410 )
    {
LABEL_19:
      g_PAL_SYS_fThreadWndClassRegistered = 1;
      return 0;
    }
    else
    {
      if ( v7 > 0 )
        ModuleSpecificClassName = (unsigned __int16)v7 | 0x80070000;
      else
        ModuleSpecificClassName = v7;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v11 = v7;
        v15 = "PAL_System_Win32_ThreadRegisterWindowClass";
        v12 = 538;
        v16 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v17 = "Failed to register window class [Win32err = %d]";
        v13 = ModuleSpecificClassName;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)v7,
          (__int64)word_180040222,
          v8,
          v9,
          (const unsigned __int16 **)&v17,
          (__int64)&v13,
          (const unsigned __int16 **)&v16,
          (__int64)&v12,
          (const unsigned __int16 **)&v15,
          (__int64)&v11);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
      v3,
      (__int64)"Failed to get module specific class name",
      ModuleSpecificClassName);
  }
  return (unsigned int)ModuleSpecificClassName;
}

```

## disassembly

```asm
0x18002a608  mov     [rsp-8+arg_0], rbx
0x18002a60d  mov     [rsp-8+arg_8], rdi
0x18002a612  push    rbp
0x18002a613  lea     rbp, [rsp-1F0h]
0x18002a61b  sub     rsp, 2F0h
0x18002a622  mov     rax, cs:__security_cookie
0x18002a629  xor     rax, rsp
0x18002a62c  mov     [rbp+1F0h+var_10], rax
0x18002a633  xor     edx, edx; Val
0x18002a635  lea     rcx, [rbp+1F0h+wcx]; void *
0x18002a639  lea     r8d, [rdx+50h]; Size
0x18002a63d  call    memset_0
0x18002a642  xor     edi, edi
0x18002a644  lea     rcx, [rbp+1F0h+szClass]; void *
0x18002a648  xor     edx, edx; Val
0x18002a64a  mov     [rsp+2F0h+phModule], rdi
0x18002a64f  mov     r8d, 208h; Size
0x18002a655  call    memset_0
0x18002a65a  lea     rdx, [rbp+1F0h+szClass]; unsigned __int16 *
0x18002a65e  call    ?PAL_System_Win32_GetModuleSpecificClassName@@YAJPEBGPEAGK@Z; PAL_System_Win32_GetModuleSpecificClassName(ushort const *,ushort *,ulong)
0x18002a663  mov     ebx, eax
0x18002a665  test    eax, eax
0x18002a667  jns     short loc_18002A6CB
0x18002a669  mov     rax, cs:WPP_GLOBAL_Control
0x18002a670  lea     rcx, WPP_GLOBAL_Control
0x18002a677  cmp     rax, rcx
0x18002a67a  jz      loc_18002A85B
0x18002a680  test    byte ptr [rax+1Ch], 8
0x18002a684  jz      loc_18002A85B
0x18002a68a  cmp     byte ptr [rax+19h], 2
0x18002a68e  jb      loc_18002A85B
0x18002a694  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a699  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x18002a6a0  mov     dword ptr [rsp+2F0h+var_2C8], ebx
0x18002a6a4  mov     [rsp+2F0h+var_2D0], rcx
0x18002a6a9  lea     edx, [rdi+12h]
0x18002a6ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6b3  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002a6ba  mov     r9d, eax
0x18002a6bd  mov     rcx, [rcx+10h]
0x18002a6c1  call    WPP_SF_DsD
0x18002a6c6  jmp     loc_18002A85B
0x18002a6cb  xor     edx, edx; lpModuleName
0x18002a6cd  lea     r8, [rsp+2F0h+phModule]; phModule
0x18002a6d2  lea     ecx, [rdx+2]; dwFlags
0x18002a6d5  call    cs:__imp_GetModuleHandleExW
0x18002a6db  test    eax, eax
0x18002a6dd  jnz     short loc_18002A72E
0x18002a6df  call    cs:__imp_GetLastError
0x18002a6e5  mov     ebx, eax
0x18002a6e7  mov     rdx, cs:WPP_GLOBAL_Control
0x18002a6ee  lea     rcx, WPP_GLOBAL_Control
0x18002a6f5  cmp     rdx, rcx
0x18002a6f8  jz      short loc_18002A72E
0x18002a6fa  test    byte ptr [rdx+1Ch], 8
0x18002a6fe  jz      short loc_18002A72E
0x18002a700  cmp     byte ptr [rdx+19h], 2
0x18002a704  jb      short loc_18002A72E
0x18002a706  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002a70b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a712  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x18002a719  mov     edx, 13h
0x18002a71e  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x18002a722  mov     r9d, eax
0x18002a725  mov     rcx, [rcx+10h]
0x18002a729  call    WPP_SF_Dd
0x18002a72e  lea     r8, [rbp+1F0h+wcx]; lpwcx
0x18002a732  xor     ecx, ecx; hInstance
0x18002a734  lea     rdx, [rbp+1F0h+szClass]; lpszClass
0x18002a738  call    cs:__imp_GetClassInfoExW
0x18002a73e  test    eax, eax
0x18002a740  jnz     loc_18002A84F
0x18002a746  lea     rax, ?PAL_System_Win32_ThreadWndProc@@YA_JPEAUHWND__@@I_K_J@Z; PAL_System_Win32_ThreadWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002a74d  mov     [rbp+1F0h+wcx.cbSize], 50h ; 'P'
0x18002a754  mov     [rbp+1F0h+wcx.lpfnWndProc], rax
0x18002a758  lea     rcx, [rbp+1F0h+wcx]; WNDCLASSEXW *
0x18002a75c  mov     rax, [rsp+2F0h+phModule]
0x18002a761  xorps   xmm0, xmm0
0x18002a764  mov     [rbp+1F0h+wcx.hInstance], rax
0x18002a768  xorps   xmm1, xmm1
0x18002a76b  lea     rax, [rbp+1F0h+szClass]
0x18002a76f  mov     [rbp+1F0h+wcx.style], 3
0x18002a776  mov     [rbp+1F0h+wcx.lpszClassName], rax
0x18002a77a  mov     qword ptr [rbp+1F0h+wcx.cbClsExtra], rdi
0x18002a77e  movdqa  xmmword ptr [rbp+1F0h+wcx.hIcon], xmm0
0x18002a783  movdqa  xmmword ptr [rbp+1F0h+wcx.hbrBackground], xmm1
0x18002a788  mov     [rbp+1F0h+wcx.hIconSm], rdi
0x18002a78c  call    cs:__imp_RegisterClassExW
0x18002a792  movzx   ebx, ax
0x18002a795  call    cs:__imp_GetLastError
0x18002a79b  mov     ecx, eax
0x18002a79d  test    bx, bx
0x18002a7a0  jnz     loc_18002A84F
0x18002a7a6  cmp     eax, 582h
0x18002a7ab  jz      loc_18002A84F
0x18002a7b1  test    eax, eax
0x18002a7b3  jg      short loc_18002A7B9
0x18002a7b5  mov     ebx, eax
0x18002a7b7  jmp     short loc_18002A7C2
0x18002a7b9  movzx   ebx, cx
0x18002a7bc  or      ebx, 80070000h
0x18002a7c2  mov     eax, cs:dword_180044008
0x18002a7c8  cmp     eax, 2
0x18002a7cb  jbe     loc_18002A85B
0x18002a7d1  lea     rax, aPalSystemWin32; "PAL_System_Win32_ThreadRegisterWindowCl"...
0x18002a7d8  mov     [rsp+2F0h+var_2A0], ecx
0x18002a7dc  mov     [rsp+2F0h+var_288], rax
0x18002a7e1  lea     rdx, word_180040222
0x18002a7e8  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002a7ef  mov     [rsp+2F0h+var_29C], 21Ah
0x18002a7f7  mov     [rsp+2F0h+var_280], rax
0x18002a7fc  lea     rax, aFailedToRegist; "Failed to register window class [Win32e"...
0x18002a803  mov     [rsp+2F0h+var_278], rax
0x18002a808  lea     rax, [rsp+2F0h+var_2A0]
0x18002a80d  mov     [rsp+2F0h+var_2A8], rax
0x18002a812  lea     rax, [rsp+2F0h+var_288]
0x18002a817  mov     [rsp+2F0h+var_2B0], rax
0x18002a81c  lea     rax, [rsp+2F0h+var_29C]
0x18002a821  mov     [rsp+2F0h+var_2B8], rax
0x18002a826  lea     rax, [rsp+2F0h+var_280]
0x18002a82b  mov     [rsp+2F0h+var_2C0], rax
0x18002a830  lea     rax, [rsp+2F0h+var_298]
0x18002a835  mov     [rsp+2F0h+var_2C8], rax
0x18002a83a  lea     rax, [rsp+2F0h+var_278]
0x18002a83f  mov     [rsp+2F0h+var_2D0], rax
0x18002a844  mov     [rsp+2F0h+var_298], ebx
0x18002a848  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002a84d  jmp     short loc_18002A85B
0x18002a84f  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 1; int g_PAL_SYS_fThreadWndClassRegistered
0x18002a859  mov     ebx, edi
0x18002a85b  mov     eax, ebx
0x18002a85d  mov     rcx, [rbp+1F0h+var_10]
0x18002a864  xor     rcx, rsp; StackCookie
0x18002a867  call    __security_check_cookie
0x18002a86c  lea     r11, [rsp+2F0h+var_s0]
0x18002a874  mov     rbx, [r11+10h]
0x18002a878  mov     rdi, [r11+18h]
0x18002a87c  mov     rsp, r11
0x18002a87f  pop     rbp
0x18002a880  retn
```
