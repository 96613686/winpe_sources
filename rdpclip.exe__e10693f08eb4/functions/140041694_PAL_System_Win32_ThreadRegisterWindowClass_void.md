# PAL_System_Win32_ThreadRegisterWindowClass(void)

- ea: `0x140041694`
- end: `0x140041975`
- name: `?PAL_System_Win32_ThreadRegisterWindowClass@@YAJXZ`
- size: `737`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140041348`

## callees

- `0x1400015ec`
- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x140008ce0`
- `0x140041694`
- `0x14006a120`

## import_xrefs

- `USER32!RegisterClassExW` at `0x140041889`
- `USER32!RegisterClassExW` at `0x140041889`
- `USER32!GetClassInfoExW` at `0x140041835`
- `USER32!GetClassInfoExW` at `0x140041835`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400417d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1400417d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400417dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400417dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041892`

## string_xrefs

- `0x1400418e5`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1400416e0`: `PAL_SYS_WIN32_THREAD_WNDCLASS`
- `0x1400418ce`: `PAL_System_Win32_ThreadRegisterWindowClass`

## pseudocode

```c
__int64 PAL_System_Win32_ThreadRegisterWindowClass(void)
{
  signed int v0; // ebx
  PVOID *v1; // rax
  unsigned int v2; // eax
  unsigned int v3; // eax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  ATOM v6; // bx
  signed int v7; // eax
  int v8; // r8d
  int v9; // r9d
  __int64 v11; // [rsp+28h] [rbp-D8h]
  signed int v12; // [rsp+50h] [rbp-B0h] BYREF
  int v13; // [rsp+54h] [rbp-ACh] BYREF
  signed int v14; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  const char *v16; // [rsp+68h] [rbp-98h] BYREF
  const char *v17; // [rsp+70h] [rbp-90h] BYREF
  const char *v18; // [rsp+78h] [rbp-88h] BYREF
  struct tagWNDCLASSEXW wcx; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szClass; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v21[526]; // [rsp+D2h] [rbp-2Eh] BYREF

  memset_0(&wcx, 0, sizeof(wcx));
  phModule = 0;
  memset_0(v21, 0, 0x206u);
  szClass = 0;
  v0 = StringCchPrintfW(&szClass, 0x104u, L"%p-%s", &g_TsSystemPalDllModule, L"PAL_SYS_WIN32_THREAD_WNDCLASS");
  if ( v0 >= 0 )
  {
    if ( !GetModuleHandleExW(2u, 0, &phModule) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
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
    if ( GetClassInfoExW(0, &szClass, &wcx) )
      goto LABEL_23;
    wcx.cbSize = 80;
    wcx.lpfnWndProc = (WNDPROC)PAL_System_Win32_ThreadWndProc;
    wcx.hInstance = phModule;
    wcx.style = 3;
    wcx.lpszClassName = &szClass;
    *(_QWORD *)&wcx.cbClsExtra = 0;
    memset(&wcx.hIcon, 0, 32);
    wcx.hIconSm = 0;
    v6 = RegisterClassExW(&wcx);
    v7 = GetLastError();
    if ( v6 || v7 == 1410 )
    {
LABEL_23:
      g_PAL_SYS_fThreadWndClassRegistered = 1;
      return 0;
    }
    else
    {
      if ( v7 > 0 )
        v0 = (unsigned __int16)v7 | 0x80070000;
      else
        v0 = v7;
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        v12 = v7;
        v16 = "PAL_System_Win32_ThreadRegisterWindowClass";
        v13 = 538;
        v17 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
        v18 = "Failed to register window class [Win32err = %d]";
        v14 = v0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)byte_140080403,
          v8,
          v9,
          (__int64)&v18,
          (__int64)&v14,
          (__int64)&v17,
          (__int64)&v13,
          (__int64)&v16,
          (__int64)&v12);
      }
    }
  }
  else
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v2 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids,
          v2,
          (__int64)"Failed StringCchPrintf",
          v0);
        v1 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 && *((_BYTE *)v1 + 25) >= 2u )
      {
        v3 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v11) = v0;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_c585fe5194613b5687849eb156704f7c_Traceguids,
          v3,
          (__int64)"Failed to get module specific class name",
          v11);
      }
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140041694  push    rbp
0x140041696  push    rbx
0x140041697  push    rsi
0x140041698  push    rdi
0x140041699  lea     rbp, [rsp-1F8h]
0x1400416a1  sub     rsp, 2F8h
0x1400416a8  mov     rax, cs:__security_cookie
0x1400416af  xor     rax, rsp
0x1400416b2  mov     [rbp+210h+var_30], rax
0x1400416b9  xor     edx, edx; Val
0x1400416bb  lea     rcx, [rbp+210h+wcx]; void *
0x1400416bf  lea     r8d, [rdx+50h]; Size
0x1400416c3  call    memset_0
0x1400416c8  xor     esi, esi
0x1400416ca  lea     rcx, [rbp+210h+var_23E]; void *
0x1400416ce  xor     edx, edx; Val
0x1400416d0  mov     [rsp+310h+phModule], rsi
0x1400416d5  mov     r8d, 206h; Size
0x1400416db  call    memset_0
0x1400416e0  lea     rax, aPalSysWin32Thr; "PAL_SYS_WIN32_THREAD_WNDCLASS"
0x1400416e7  mov     [rbp+210h+szClass], si
0x1400416eb  lea     r9, ?g_TsSystemPalDllModule@@3HA; int g_TsSystemPalDllModule
0x1400416f2  mov     [rsp+310h+var_2F0], rax
0x1400416f7  lea     r8, aPS; "%p-%s"
0x1400416fe  mov     edx, 104h; unsigned __int64
0x140041703  lea     rcx, [rbp+210h+szClass]; unsigned __int16 *
0x140041707  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004170c  mov     ebx, eax
0x14004170e  test    eax, eax
0x140041710  jns     loc_1400417C8
0x140041716  mov     rax, cs:WPP_GLOBAL_Control
0x14004171d  lea     rdi, WPP_GLOBAL_Control
0x140041724  cmp     rax, rdi
0x140041727  jz      loc_140041958
0x14004172d  test    byte ptr [rax+1Ch], 8
0x140041731  jz      short loc_140041772
0x140041733  cmp     byte ptr [rax+19h], 2
0x140041737  jb      short loc_140041772
0x140041739  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004173e  lea     rcx, aFailedStringcc; "Failed StringCchPrintf"
0x140041745  mov     dword ptr [rsp+310h+var_2E8], ebx
0x140041749  mov     [rsp+310h+var_2F0], rcx
0x14004174e  lea     edx, [rsi+0Ch]
0x140041751  mov     rcx, cs:WPP_GLOBAL_Control
0x140041758  lea     r8, WPP_9e2d2381f4b936a6413120d345f767e7_Traceguids
0x14004175f  mov     r9d, eax
0x140041762  mov     rcx, [rcx+10h]
0x140041766  call    WPP_SF_DsD
0x14004176b  mov     rax, cs:WPP_GLOBAL_Control
0x140041772  cmp     rax, rdi
0x140041775  jz      loc_140041958
0x14004177b  test    byte ptr [rax+1Ch], 8
0x14004177f  jz      loc_140041958
0x140041785  cmp     byte ptr [rax+19h], 2
0x140041789  jb      loc_140041958
0x14004178f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041794  lea     rcx, aFailedToGetMod; "Failed to get module specific class nam"...
0x14004179b  mov     dword ptr [rsp+310h+var_2E8], ebx
0x14004179f  mov     [rsp+310h+var_2F0], rcx
0x1400417a4  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x1400417ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400417b2  mov     edx, 12h
0x1400417b7  mov     r9d, eax
0x1400417ba  mov     rcx, [rcx+10h]
0x1400417be  call    WPP_SF_DsD
0x1400417c3  jmp     loc_140041958
0x1400417c8  xor     edx, edx; lpModuleName
0x1400417ca  lea     r8, [rsp+310h+phModule]; phModule
0x1400417cf  lea     ecx, [rdx+2]; dwFlags
0x1400417d2  call    cs:__imp_GetModuleHandleExW
0x1400417d8  test    eax, eax
0x1400417da  jnz     short loc_14004182B
0x1400417dc  call    cs:__imp_GetLastError
0x1400417e2  mov     ebx, eax
0x1400417e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400417eb  lea     rdi, WPP_GLOBAL_Control
0x1400417f2  cmp     rcx, rdi
0x1400417f5  jz      short loc_14004182B
0x1400417f7  test    byte ptr [rcx+1Ch], 8
0x1400417fb  jz      short loc_14004182B
0x1400417fd  cmp     byte ptr [rcx+19h], 2
0x140041801  jb      short loc_14004182B
0x140041803  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140041808  mov     rcx, cs:WPP_GLOBAL_Control
0x14004180f  lea     r8, WPP_c585fe5194613b5687849eb156704f7c_Traceguids
0x140041816  mov     edx, 13h
0x14004181b  mov     dword ptr [rsp+310h+var_2F0], ebx
0x14004181f  mov     r9d, eax
0x140041822  mov     rcx, [rcx+10h]
0x140041826  call    WPP_SF_Dd
0x14004182b  lea     r8, [rbp+210h+wcx]; lpwcx
0x14004182f  xor     ecx, ecx; hInstance
0x140041831  lea     rdx, [rbp+210h+szClass]; lpszClass
0x140041835  call    cs:__imp_GetClassInfoExW
0x14004183b  test    eax, eax
0x14004183d  jnz     loc_14004194C
0x140041843  lea     rax, ?PAL_System_Win32_ThreadWndProc@@YA_JPEAUHWND__@@I_K_J@Z; PAL_System_Win32_ThreadWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14004184a  mov     [rbp+210h+wcx.cbSize], 50h ; 'P'
0x140041851  mov     [rbp+210h+wcx.lpfnWndProc], rax
0x140041855  lea     rcx, [rbp+210h+wcx]; WNDCLASSEXW *
0x140041859  mov     rax, [rsp+310h+phModule]
0x14004185e  xorps   xmm0, xmm0
0x140041861  mov     [rbp+210h+wcx.hInstance], rax
0x140041865  xorps   xmm1, xmm1
0x140041868  lea     rax, [rbp+210h+szClass]
0x14004186c  mov     [rbp+210h+wcx.style], 3
0x140041873  mov     [rbp+210h+wcx.lpszClassName], rax
0x140041877  mov     qword ptr [rbp+210h+wcx.cbClsExtra], rsi
0x14004187b  movdqa  xmmword ptr [rbp+210h+wcx.hIcon], xmm0
0x140041880  movdqa  xmmword ptr [rbp+210h+wcx.hbrBackground], xmm1
0x140041885  mov     [rbp+210h+wcx.hIconSm], rsi
0x140041889  call    cs:__imp_RegisterClassExW
0x14004188f  movzx   ebx, ax
0x140041892  call    cs:__imp_GetLastError
0x140041898  mov     ecx, eax
0x14004189a  test    bx, bx
0x14004189d  jnz     loc_14004194C
0x1400418a3  cmp     eax, 582h
0x1400418a8  jz      loc_14004194C
0x1400418ae  test    eax, eax
0x1400418b0  jg      short loc_1400418B6
0x1400418b2  mov     ebx, eax
0x1400418b4  jmp     short loc_1400418BF
0x1400418b6  movzx   ebx, cx
0x1400418b9  or      ebx, 80070000h
0x1400418bf  mov     eax, cs:dword_1400880C8
0x1400418c5  cmp     eax, 2
0x1400418c8  jbe     loc_140041958
0x1400418ce  lea     rax, aPalSystemWin32; "PAL_System_Win32_ThreadRegisterWindowCl"...
0x1400418d5  mov     [rsp+310h+var_2C0], ecx
0x1400418d9  mov     [rsp+310h+var_2A8], rax
0x1400418de  lea     rdx, byte_140080403
0x1400418e5  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400418ec  mov     [rsp+310h+var_2BC], 21Ah
0x1400418f4  mov     [rsp+310h+var_2A0], rax
0x1400418f9  lea     rax, aFailedToRegist; "Failed to register window class [Win32e"...
0x140041900  mov     [rsp+310h+var_298], rax
0x140041905  lea     rax, [rsp+310h+var_2C0]
0x14004190a  mov     [rsp+310h+var_2C8], rax
0x14004190f  lea     rax, [rsp+310h+var_2A8]
0x140041914  mov     [rsp+310h+var_2D0], rax
0x140041919  lea     rax, [rsp+310h+var_2BC]
0x14004191e  mov     [rsp+310h+var_2D8], rax
0x140041923  lea     rax, [rsp+310h+var_2A0]
0x140041928  mov     [rsp+310h+var_2E0], rax
0x14004192d  lea     rax, [rsp+310h+var_2B8]
0x140041932  mov     [rsp+310h+var_2E8], rax
0x140041937  lea     rax, [rsp+310h+var_298]
0x14004193c  mov     [rsp+310h+var_2F0], rax
0x140041941  mov     [rsp+310h+var_2B8], ebx
0x140041945  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14004194a  jmp     short loc_140041958
0x14004194c  mov     cs:?g_PAL_SYS_fThreadWndClassRegistered@@3HA, 1; int g_PAL_SYS_fThreadWndClassRegistered
0x140041956  mov     ebx, esi
0x140041958  mov     eax, ebx
0x14004195a  mov     rcx, [rbp+210h+var_30]
0x140041961  xor     rcx, rsp; StackCookie
0x140041964  call    __security_check_cookie
0x140041969  add     rsp, 2F8h
0x140041970  pop     rdi
0x140041971  pop     rsi
0x140041972  pop     rbx
0x140041973  pop     rbp
0x140041974  retn
```
