# CSrApiViewerAxHost::s_LaunchViewer(HINSTANCE__ *,HINSTANCE__ *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,ushort const *,CSrApiViewerAxHost::EPromptForCredsDisposition,ushort const *,ulong,CSrApiViewerAxHost * *)

- ea: `0x1400b2d10`
- end: `0x1400b30bd`
- name: `?s_LaunchViewer@CSrApiViewerAxHost@@SAJPEAUHINSTANCE__@@0W4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEBGW4EPromptForCredsDisposition@1@3KPEAPEAV1@@Z`
- size: `941`
- prototype: `static int __high(HINSTANCE, HINSTANCE, enum SHADOW_CONTROL_REQUEST, enum SHADOW_PERMISSION_REQUEST, const unsigned __int16 *, enum CSrApiViewerAxHost::EPromptForCredsDisposition, const unsigned __int16 *, unsigned int, struct CSrApiViewerAxHost **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140064090`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x1400adcec`
- `0x1400aec40`
- `0x1400aeca8`
- `0x1400b0128`
- `0x1400b2d10`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400b300b`
- `USER32!LoadStringW` at `0x1400b3055`
- `USER32!LoadStringW` at `0x1400b300b`
- `USER32!LoadStringW` at `0x1400b3055`
- `USER32!MessageBoxW` at `0x1400b3078`
- `USER32!MessageBoxW` at `0x1400b3078`
- `KERNEL32!LocalFree` at `0x1400b3088`
- `KERNEL32!LocalFree` at `0x1400b3088`
- `KERNEL32!CreateThread` at `0x1400b2ef9`
- `KERNEL32!CreateThread` at `0x1400b2ef9`
- `KERNEL32!CloseHandle` at `0x1400b2f8b`
- `KERNEL32!CloseHandle` at `0x1400b2f8b`
- `KERNEL32!GetLastError` at `0x1400b2f19`
- `KERNEL32!GetLastError` at `0x1400b2f19`
- `KERNEL32!FormatMessageW` at `0x1400b3039`
- `KERNEL32!FormatMessageW` at `0x1400b3039`

## string_xrefs

- `0x1400b2ec9`: `spViewerAxHost->CreateHostWindow failed`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::s_LaunchViewer(
        __int64 a1,
        HINSTANCE a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        CSrApiViewerAxHost **a9)
{
  CSrApiViewerAxHost *v13; // rax
  CSrApiViewerAxHost *v14; // rdi
  __int64 v15; // rcx
  signed int HostWindow; // ebx
  unsigned int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  HANDLE Thread; // rsi
  unsigned int v21; // eax
  void *v22; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  DWORD v24; // eax
  WCHAR *v25; // rdx
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  CSrApiViewerAxHost *v28; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v29[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[64]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v32[512]; // [rsp+F0h] [rbp-10h] BYREF

  v30 = a7;
  v28 = 0;
  memset_0(v32, 0, sizeof(v32));
  memset_0(Buffer, 0, sizeof(Buffer));
  *(_QWORD *)v29 = 0;
  v13 = (CSrApiViewerAxHost *)operator new(0x108u);
  if ( !v13 || (v14 = CSrApiViewerAxHost::CSrApiViewerAxHost(v13)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024882);
    }
    HostWindow = -2147024882;
    goto LABEL_32;
  }
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
  v15 = *(_QWORD *)v14;
  v28 = v14;
  (*(void (__fastcall **)(CSrApiViewerAxHost *))(v15 + 8))(v14);
  HostWindow = CSrApiViewerAxHost::Initialize(v14, a1, a2, a3, a4, a5, v30, a8, a6);
  if ( HostWindow < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 11;
    v19 = "spViewerAxHost->Initialize failed";
LABEL_8:
    LODWORD(lpThreadId) = HostWindow;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v17,
      (__int64)v19,
      lpThreadId);
LABEL_32:
    LoadStringW(a2, 0x34BCu, Buffer, 64);
    v24 = ConvertHRESULT2WIN32(HostWindow);
    if ( !FormatMessageW(0x1100u, 0, v24, 0, v29, 0, 0) )
      LoadStringW(a2, 0x34BDu, v32, 512);
    v25 = v32;
    if ( *(_QWORD *)v29 )
      v25 = *(WCHAR **)v29;
    MessageBoxW(0, v25, Buffer, 0x10u);
    if ( *(_QWORD *)v29 )
      LocalFree(*(HLOCAL *)v29);
    goto LABEL_38;
  }
  HostWindow = CSrApiViewerAxHost::CreateHostWindow(v14);
  if ( HostWindow < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 12;
    v19 = "spViewerAxHost->CreateHostWindow failed";
    goto LABEL_8;
  }
  (*(void (__fastcall **)(CSrApiViewerAxHost *))(*(_QWORD *)v14 + 8LL))(v14);
  Thread = CreateThread(0, 0, CSrApiViewerAxHost::s_RpcShadowClientThreadProc, v14, 0, 0);
  if ( !Thread )
  {
    (*(void (__fastcall **)(CSrApiViewerAxHost *))(*(_QWORD *)v14 + 16LL))(v14);
    HostWindow = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v21,
        HostWindow);
    }
    if ( HostWindow > 0 )
      HostWindow = (unsigned __int16)HostWindow | 0x80070000;
    if ( HostWindow >= 0 )
      HostWindow = -2147467259;
    goto LABEL_32;
  }
  v22 = (void *)*((_QWORD *)v14 + 29);
  if ( v22 )
    CloseHandle(v22);
  *((_QWORD *)v14 + 29) = Thread;
  *a9 = v14;
  v28 = 0;
LABEL_38:
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v28);
  return (unsigned int)HostWindow;
}

```

## disassembly

```asm
0x1400b2d10  push    rbp
0x1400b2d12  push    rbx
0x1400b2d13  push    rsi
0x1400b2d14  push    rdi
0x1400b2d15  push    r12
0x1400b2d17  push    r13
0x1400b2d19  push    r14
0x1400b2d1b  push    r15
0x1400b2d1d  lea     rbp, [rsp-408h]
0x1400b2d25  sub     rsp, 508h
0x1400b2d2c  mov     rax, cs:__security_cookie
0x1400b2d33  xor     rax, rsp
0x1400b2d36  mov     [rbp+440h+var_50], rax
0x1400b2d3d  mov     rax, [rbp+440h+arg_30]
0x1400b2d44  mov     esi, r8d
0x1400b2d47  mov     r13, [rbp+440h+arg_20]
0x1400b2d4e  mov     r14, rdx
0x1400b2d51  mov     r15, [rbp+440h+arg_40]
0x1400b2d58  mov     rbx, rcx
0x1400b2d5b  xor     edx, edx; Val
0x1400b2d5d  mov     [rsp+540h+var_4E0], rax
0x1400b2d62  mov     r8d, 400h; Size
0x1400b2d68  mov     [rsp+540h+var_4F0], 0
0x1400b2d71  lea     rcx, [rbp+440h+var_450]; void *
0x1400b2d75  mov     r12d, r9d
0x1400b2d78  call    memset_0
0x1400b2d7d  xor     edx, edx; Val
0x1400b2d7f  lea     rcx, [rsp+540h+Buffer]; void *
0x1400b2d84  mov     r8d, 80h; Size
0x1400b2d8a  call    memset_0
0x1400b2d8f  mov     ecx, 108h; Size
0x1400b2d94  mov     qword ptr [rsp+540h+var_4E8], 0
0x1400b2d9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b2da2  test    rax, rax
0x1400b2da5  jz      loc_1400B2FA5
0x1400b2dab  mov     rcx, rax; this
0x1400b2dae  call    ??0CSrApiViewerAxHost@@AEAA@XZ; CSrApiViewerAxHost::CSrApiViewerAxHost(void)
0x1400b2db3  mov     rdi, rax
0x1400b2db6  test    rax, rax
0x1400b2db9  jz      loc_1400B2FA5
0x1400b2dbf  lea     rcx, [rsp+540h+var_4F0]
0x1400b2dc4  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400b2dc9  mov     rcx, [rdi]
0x1400b2dcc  mov     [rsp+540h+var_4F0], rdi
0x1400b2dd1  mov     rax, [rcx+8]
0x1400b2dd5  mov     rcx, rdi
0x1400b2dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2ddd  mov     eax, [rbp+440h+arg_28]
0x1400b2de3  mov     r9d, esi
0x1400b2de6  mov     ecx, [rdi+40h]
0x1400b2de9  mov     r8, r14
0x1400b2dec  mov     [rsp+540h+var_500], eax
0x1400b2df0  mov     rdx, rbx
0x1400b2df3  mov     eax, [rbp+440h+arg_38]
0x1400b2df9  mov     rcx, rdi
0x1400b2dfc  mov     [rsp+540h+var_508], eax
0x1400b2e00  mov     rax, [rsp+540h+var_4E0]
0x1400b2e05  mov     [rsp+540h+Arguments], rax
0x1400b2e0a  mov     [rsp+540h+lpThreadId], r13
0x1400b2e0f  mov     [rsp+540h+dwCreationFlags], r12d
0x1400b2e14  call    ?Initialize@CSrApiViewerAxHost@@AEAAJPEAUHINSTANCE__@@0W4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEBG3KW4EPromptForCredsDisposition@1@@Z; CSrApiViewerAxHost::Initialize(HINSTANCE__ *,HINSTANCE__ *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,ushort const *,ushort const *,ulong,CSrApiViewerAxHost::EPromptForCredsDisposition)
0x1400b2e19  xor     r12d, r12d
0x1400b2e1c  mov     ebx, eax
0x1400b2e1e  test    eax, eax
0x1400b2e20  jns     short loc_1400B2E86
0x1400b2e22  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2e29  lea     rax, WPP_GLOBAL_Control
0x1400b2e30  cmp     rcx, rax
0x1400b2e33  jz      loc_1400B2FF8
0x1400b2e39  test    byte ptr [rcx+1Ch], 8
0x1400b2e3d  jz      loc_1400B2FF8
0x1400b2e43  cmp     byte ptr [rcx+19h], 2
0x1400b2e47  jb      loc_1400B2FF8
0x1400b2e4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2e52  lea     edx, [r12+0Bh]
0x1400b2e57  lea     rcx, aSpvieweraxhost_0; "spViewerAxHost->Initialize failed"
0x1400b2e5e  mov     dword ptr [rsp+540h+lpThreadId], ebx
0x1400b2e62  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b2e69  mov     qword ptr [rsp+540h+dwCreationFlags], rcx
0x1400b2e6e  mov     r9d, eax
0x1400b2e71  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2e78  mov     rcx, [rcx+10h]
0x1400b2e7c  call    WPP_SF_DsD
0x1400b2e81  jmp     loc_1400B2FF8
0x1400b2e86  mov     rcx, rdi; this
0x1400b2e89  call    ?CreateHostWindow@CSrApiViewerAxHost@@AEAAJXZ; CSrApiViewerAxHost::CreateHostWindow(void)
0x1400b2e8e  mov     ebx, eax
0x1400b2e90  test    eax, eax
0x1400b2e92  jns     short loc_1400B2ED2
0x1400b2e94  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2e9b  lea     rax, WPP_GLOBAL_Control
0x1400b2ea2  cmp     rcx, rax
0x1400b2ea5  jz      loc_1400B2FF8
0x1400b2eab  test    byte ptr [rcx+1Ch], 8
0x1400b2eaf  jz      loc_1400B2FF8
0x1400b2eb5  cmp     byte ptr [rcx+19h], 2
0x1400b2eb9  jb      loc_1400B2FF8
0x1400b2ebf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2ec4  mov     edx, 0Ch
0x1400b2ec9  lea     rcx, aSpvieweraxhost; "spViewerAxHost->CreateHostWindow failed"
0x1400b2ed0  jmp     short loc_1400B2E5E
0x1400b2ed2  mov     rax, [rdi]
0x1400b2ed5  mov     rcx, rdi
0x1400b2ed8  mov     rax, [rax+8]
0x1400b2edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2ee1  mov     r9, rdi; lpParameter
0x1400b2ee4  mov     [rsp+540h+lpThreadId], r12; lpThreadId
0x1400b2ee9  lea     r8, ?s_RpcShadowClientThreadProc@CSrApiViewerAxHost@@CAKPEAV1@@Z; lpStartAddress
0x1400b2ef0  mov     [rsp+540h+dwCreationFlags], r12d; dwCreationFlags
0x1400b2ef5  xor     edx, edx; dwStackSize
0x1400b2ef7  xor     ecx, ecx; lpThreadAttributes
0x1400b2ef9  call    cs:__imp_CreateThread
0x1400b2eff  mov     rsi, rax
0x1400b2f02  test    rax, rax
0x1400b2f05  jnz     short loc_1400B2F7F
0x1400b2f07  mov     eax, [rdi+40h]
0x1400b2f0a  mov     rcx, rdi
0x1400b2f0d  mov     rax, [rdi]
0x1400b2f10  mov     rax, [rax+10h]
0x1400b2f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b2f19  call    cs:__imp_GetLastError
0x1400b2f1f  mov     ebx, eax
0x1400b2f21  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2f28  lea     rax, WPP_GLOBAL_Control
0x1400b2f2f  cmp     rcx, rax
0x1400b2f32  jz      short loc_1400B2F66
0x1400b2f34  test    byte ptr [rcx+1Ch], 8
0x1400b2f38  jz      short loc_1400B2F66
0x1400b2f3a  cmp     byte ptr [rcx+19h], 2
0x1400b2f3e  jb      short loc_1400B2F66
0x1400b2f40  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2f45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2f4c  lea     edx, [rsi+0Dh]
0x1400b2f4f  mov     r9d, eax
0x1400b2f52  mov     [rsp+540h+dwCreationFlags], ebx
0x1400b2f56  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b2f5d  mov     rcx, [rcx+10h]
0x1400b2f61  call    WPP_SF_Dd
0x1400b2f66  test    ebx, ebx
0x1400b2f68  jle     short loc_1400B2F73
0x1400b2f6a  movzx   ebx, bx
0x1400b2f6d  or      ebx, 80070000h
0x1400b2f73  test    ebx, ebx
0x1400b2f75  mov     eax, 80004005h
0x1400b2f7a  cmovns  ebx, eax
0x1400b2f7d  jmp     short loc_1400B2FF8
0x1400b2f7f  mov     rcx, [rdi+0E8h]; hObject
0x1400b2f86  test    rcx, rcx
0x1400b2f89  jz      short loc_1400B2F91
0x1400b2f8b  call    cs:__imp_CloseHandle
0x1400b2f91  mov     [rdi+0E8h], rsi
0x1400b2f98  mov     [r15], rdi
0x1400b2f9b  mov     [rsp+540h+var_4F0], r12
0x1400b2fa0  jmp     loc_1400B308E
0x1400b2fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2fac  lea     rax, WPP_GLOBAL_Control
0x1400b2fb3  cmp     rcx, rax
0x1400b2fb6  jz      short loc_1400B2FF0
0x1400b2fb8  test    byte ptr [rcx+1Ch], 8
0x1400b2fbc  jz      short loc_1400B2FF0
0x1400b2fbe  cmp     byte ptr [rcx+19h], 2
0x1400b2fc2  jb      short loc_1400B2FF0
0x1400b2fc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b2fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2fd0  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b2fd7  mov     edx, 0Ah
0x1400b2fdc  mov     [rsp+540h+dwCreationFlags], 8007000Eh
0x1400b2fe4  mov     r9d, eax
0x1400b2fe7  mov     rcx, [rcx+10h]
0x1400b2feb  call    WPP_SF_Dd
0x1400b2ff0  mov     ebx, 8007000Eh
0x1400b2ff5  xor     r12d, r12d
0x1400b2ff8  mov     r9d, 40h ; '@'; cchBufferMax
0x1400b2ffe  lea     r8, [rsp+540h+Buffer]; lpBuffer
0x1400b3003  mov     edx, 34BCh; uID
0x1400b3008  mov     rcx, r14; hInstance
0x1400b300b  call    cs:__imp_LoadStringW
0x1400b3011  mov     ecx, ebx; int
0x1400b3013  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1400b3018  mov     r8d, eax; dwMessageId
0x1400b301b  mov     [rsp+540h+Arguments], r12; Arguments
0x1400b3020  lea     rax, [rsp+540h+var_4E8]
0x1400b3025  mov     dword ptr [rsp+540h+lpThreadId], r12d; nSize
0x1400b302a  xor     r9d, r9d; dwLanguageId
0x1400b302d  mov     qword ptr [rsp+540h+dwCreationFlags], rax; lpBuffer
0x1400b3032  xor     edx, edx; lpSource
0x1400b3034  mov     ecx, 1100h; dwFlags
0x1400b3039  call    cs:__imp_FormatMessageW
0x1400b303f  test    eax, eax
0x1400b3041  jnz     short loc_1400B305B
0x1400b3043  mov     r9d, 200h; cchBufferMax
0x1400b3049  lea     r8, [rbp+440h+var_450]; lpBuffer
0x1400b304d  mov     edx, 34BDh; uID
0x1400b3052  mov     rcx, r14; hInstance
0x1400b3055  call    cs:__imp_LoadStringW
0x1400b305b  mov     rax, qword ptr [rsp+540h+var_4E8]
0x1400b3060  lea     rdx, [rbp+440h+var_450]
0x1400b3064  test    rax, rax
0x1400b3067  lea     r8, [rsp+540h+Buffer]; lpCaption
0x1400b306c  mov     r9d, 10h; uType
0x1400b3072  cmovnz  rdx, rax; lpText
0x1400b3076  xor     ecx, ecx; hWnd
0x1400b3078  call    cs:__imp_MessageBoxW
0x1400b307e  mov     rcx, qword ptr [rsp+540h+var_4E8]; hMem
0x1400b3083  test    rcx, rcx
0x1400b3086  jz      short loc_1400B308E
0x1400b3088  call    cs:__imp_LocalFree
0x1400b308e  lea     rcx, [rsp+540h+var_4F0]
0x1400b3093  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400b3098  mov     eax, ebx
0x1400b309a  mov     rcx, [rbp+440h+var_50]
0x1400b30a1  xor     rcx, rsp; StackCookie
0x1400b30a4  call    __security_check_cookie
0x1400b30a9  add     rsp, 508h
0x1400b30b0  pop     r15
0x1400b30b2  pop     r14
0x1400b30b4  pop     r13
0x1400b30b6  pop     r12
0x1400b30b8  pop     rdi
0x1400b30b9  pop     rsi
0x1400b30ba  pop     rbx
0x1400b30bb  pop     rbp
0x1400b30bc  retn
```
