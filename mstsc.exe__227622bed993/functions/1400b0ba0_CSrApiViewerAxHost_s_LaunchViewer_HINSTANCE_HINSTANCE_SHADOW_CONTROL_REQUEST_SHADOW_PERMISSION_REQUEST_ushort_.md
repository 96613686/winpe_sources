# CSrApiViewerAxHost::s_LaunchViewer(HINSTANCE__ *,HINSTANCE__ *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,ushort const *,CSrApiViewerAxHost::EPromptForCredsDisposition,ushort const *,ulong,CSrApiViewerAxHost * *)

- ea: `0x1400b0ba0`
- end: `0x1400b0f4d`
- name: `?s_LaunchViewer@CSrApiViewerAxHost@@SAJPEAUHINSTANCE__@@0W4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEBGW4EPromptForCredsDisposition@1@3KPEAPEAV1@@Z`
- size: `941`
- prototype: `static int __high(HINSTANCE, HINSTANCE, enum SHADOW_CONTROL_REQUEST, enum SHADOW_PERMISSION_REQUEST, const unsigned __int16 *, enum CSrApiViewerAxHost::EPromptForCredsDisposition, const unsigned __int16 *, unsigned int, struct CSrApiViewerAxHost **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140061f20`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x1400abb7c`
- `0x1400acad0`
- `0x1400acb38`
- `0x1400adfb8`
- `0x1400b0ba0`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400b0e9b`
- `USER32!LoadStringW` at `0x1400b0ee5`
- `USER32!LoadStringW` at `0x1400b0e9b`
- `USER32!LoadStringW` at `0x1400b0ee5`
- `USER32!MessageBoxW` at `0x1400b0f08`
- `USER32!MessageBoxW` at `0x1400b0f08`
- `KERNEL32!LocalFree` at `0x1400b0f18`
- `KERNEL32!LocalFree` at `0x1400b0f18`
- `KERNEL32!CreateThread` at `0x1400b0d89`
- `KERNEL32!CreateThread` at `0x1400b0d89`
- `KERNEL32!CloseHandle` at `0x1400b0e1b`
- `KERNEL32!CloseHandle` at `0x1400b0e1b`
- `KERNEL32!GetLastError` at `0x1400b0da9`
- `KERNEL32!GetLastError` at `0x1400b0da9`
- `KERNEL32!FormatMessageW` at `0x1400b0ec9`
- `KERNEL32!FormatMessageW` at `0x1400b0ec9`

## string_xrefs

- `0x1400b0d59`: `spViewerAxHost->CreateHostWindow failed`

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
0x1400b0ba0  push    rbp
0x1400b0ba2  push    rbx
0x1400b0ba3  push    rsi
0x1400b0ba4  push    rdi
0x1400b0ba5  push    r12
0x1400b0ba7  push    r13
0x1400b0ba9  push    r14
0x1400b0bab  push    r15
0x1400b0bad  lea     rbp, [rsp-408h]
0x1400b0bb5  sub     rsp, 508h
0x1400b0bbc  mov     rax, cs:__security_cookie
0x1400b0bc3  xor     rax, rsp
0x1400b0bc6  mov     [rbp+440h+var_50], rax
0x1400b0bcd  mov     rax, [rbp+440h+arg_30]
0x1400b0bd4  mov     esi, r8d
0x1400b0bd7  mov     r13, [rbp+440h+arg_20]
0x1400b0bde  mov     r14, rdx
0x1400b0be1  mov     r15, [rbp+440h+arg_40]
0x1400b0be8  mov     rbx, rcx
0x1400b0beb  xor     edx, edx; Val
0x1400b0bed  mov     [rsp+540h+var_4E0], rax
0x1400b0bf2  mov     r8d, 400h; Size
0x1400b0bf8  mov     [rsp+540h+var_4F0], 0
0x1400b0c01  lea     rcx, [rbp+440h+var_450]; void *
0x1400b0c05  mov     r12d, r9d
0x1400b0c08  call    memset_0
0x1400b0c0d  xor     edx, edx; Val
0x1400b0c0f  lea     rcx, [rsp+540h+Buffer]; void *
0x1400b0c14  mov     r8d, 80h; Size
0x1400b0c1a  call    memset_0
0x1400b0c1f  mov     ecx, 108h; Size
0x1400b0c24  mov     qword ptr [rsp+540h+var_4E8], 0
0x1400b0c2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400b0c32  test    rax, rax
0x1400b0c35  jz      loc_1400B0E35
0x1400b0c3b  mov     rcx, rax; this
0x1400b0c3e  call    ??0CSrApiViewerAxHost@@AEAA@XZ; CSrApiViewerAxHost::CSrApiViewerAxHost(void)
0x1400b0c43  mov     rdi, rax
0x1400b0c46  test    rax, rax
0x1400b0c49  jz      loc_1400B0E35
0x1400b0c4f  lea     rcx, [rsp+540h+var_4F0]
0x1400b0c54  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400b0c59  mov     rcx, [rdi]
0x1400b0c5c  mov     [rsp+540h+var_4F0], rdi
0x1400b0c61  mov     rax, [rcx+8]
0x1400b0c65  mov     rcx, rdi
0x1400b0c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b0c6d  mov     eax, [rbp+440h+arg_28]
0x1400b0c73  mov     r9d, esi
0x1400b0c76  mov     ecx, [rdi+40h]
0x1400b0c79  mov     r8, r14
0x1400b0c7c  mov     [rsp+540h+var_500], eax
0x1400b0c80  mov     rdx, rbx
0x1400b0c83  mov     eax, [rbp+440h+arg_38]
0x1400b0c89  mov     rcx, rdi
0x1400b0c8c  mov     [rsp+540h+var_508], eax
0x1400b0c90  mov     rax, [rsp+540h+var_4E0]
0x1400b0c95  mov     [rsp+540h+Arguments], rax
0x1400b0c9a  mov     [rsp+540h+lpThreadId], r13
0x1400b0c9f  mov     [rsp+540h+dwCreationFlags], r12d
0x1400b0ca4  call    ?Initialize@CSrApiViewerAxHost@@AEAAJPEAUHINSTANCE__@@0W4SHADOW_CONTROL_REQUEST@@W4SHADOW_PERMISSION_REQUEST@@PEBG3KW4EPromptForCredsDisposition@1@@Z; CSrApiViewerAxHost::Initialize(HINSTANCE__ *,HINSTANCE__ *,SHADOW_CONTROL_REQUEST,SHADOW_PERMISSION_REQUEST,ushort const *,ushort const *,ulong,CSrApiViewerAxHost::EPromptForCredsDisposition)
0x1400b0ca9  xor     r12d, r12d
0x1400b0cac  mov     ebx, eax
0x1400b0cae  test    eax, eax
0x1400b0cb0  jns     short loc_1400B0D16
0x1400b0cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0cb9  lea     rax, WPP_GLOBAL_Control
0x1400b0cc0  cmp     rcx, rax
0x1400b0cc3  jz      loc_1400B0E88
0x1400b0cc9  test    byte ptr [rcx+1Ch], 8
0x1400b0ccd  jz      loc_1400B0E88
0x1400b0cd3  cmp     byte ptr [rcx+19h], 2
0x1400b0cd7  jb      loc_1400B0E88
0x1400b0cdd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0ce2  lea     edx, [r12+0Bh]
0x1400b0ce7  lea     rcx, aSpvieweraxhost_0; "spViewerAxHost->Initialize failed"
0x1400b0cee  mov     dword ptr [rsp+540h+lpThreadId], ebx
0x1400b0cf2  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0cf9  mov     qword ptr [rsp+540h+dwCreationFlags], rcx
0x1400b0cfe  mov     r9d, eax
0x1400b0d01  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0d08  mov     rcx, [rcx+10h]
0x1400b0d0c  call    WPP_SF_DsD
0x1400b0d11  jmp     loc_1400B0E88
0x1400b0d16  mov     rcx, rdi; this
0x1400b0d19  call    ?CreateHostWindow@CSrApiViewerAxHost@@AEAAJXZ; CSrApiViewerAxHost::CreateHostWindow(void)
0x1400b0d1e  mov     ebx, eax
0x1400b0d20  test    eax, eax
0x1400b0d22  jns     short loc_1400B0D62
0x1400b0d24  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0d2b  lea     rax, WPP_GLOBAL_Control
0x1400b0d32  cmp     rcx, rax
0x1400b0d35  jz      loc_1400B0E88
0x1400b0d3b  test    byte ptr [rcx+1Ch], 8
0x1400b0d3f  jz      loc_1400B0E88
0x1400b0d45  cmp     byte ptr [rcx+19h], 2
0x1400b0d49  jb      loc_1400B0E88
0x1400b0d4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0d54  mov     edx, 0Ch
0x1400b0d59  lea     rcx, aSpvieweraxhost; "spViewerAxHost->CreateHostWindow failed"
0x1400b0d60  jmp     short loc_1400B0CEE
0x1400b0d62  mov     rax, [rdi]
0x1400b0d65  mov     rcx, rdi
0x1400b0d68  mov     rax, [rax+8]
0x1400b0d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b0d71  mov     r9, rdi; lpParameter
0x1400b0d74  mov     [rsp+540h+lpThreadId], r12; lpThreadId
0x1400b0d79  lea     r8, ?s_RpcShadowClientThreadProc@CSrApiViewerAxHost@@CAKPEAV1@@Z; lpStartAddress
0x1400b0d80  mov     [rsp+540h+dwCreationFlags], r12d; dwCreationFlags
0x1400b0d85  xor     edx, edx; dwStackSize
0x1400b0d87  xor     ecx, ecx; lpThreadAttributes
0x1400b0d89  call    cs:__imp_CreateThread
0x1400b0d8f  mov     rsi, rax
0x1400b0d92  test    rax, rax
0x1400b0d95  jnz     short loc_1400B0E0F
0x1400b0d97  mov     eax, [rdi+40h]
0x1400b0d9a  mov     rcx, rdi
0x1400b0d9d  mov     rax, [rdi]
0x1400b0da0  mov     rax, [rax+10h]
0x1400b0da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b0da9  call    cs:__imp_GetLastError
0x1400b0daf  mov     ebx, eax
0x1400b0db1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0db8  lea     rax, WPP_GLOBAL_Control
0x1400b0dbf  cmp     rcx, rax
0x1400b0dc2  jz      short loc_1400B0DF6
0x1400b0dc4  test    byte ptr [rcx+1Ch], 8
0x1400b0dc8  jz      short loc_1400B0DF6
0x1400b0dca  cmp     byte ptr [rcx+19h], 2
0x1400b0dce  jb      short loc_1400B0DF6
0x1400b0dd0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0ddc  lea     edx, [rsi+0Dh]
0x1400b0ddf  mov     r9d, eax
0x1400b0de2  mov     [rsp+540h+dwCreationFlags], ebx
0x1400b0de6  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0ded  mov     rcx, [rcx+10h]
0x1400b0df1  call    WPP_SF_Dd
0x1400b0df6  test    ebx, ebx
0x1400b0df8  jle     short loc_1400B0E03
0x1400b0dfa  movzx   ebx, bx
0x1400b0dfd  or      ebx, 80070000h
0x1400b0e03  test    ebx, ebx
0x1400b0e05  mov     eax, 80004005h
0x1400b0e0a  cmovns  ebx, eax
0x1400b0e0d  jmp     short loc_1400B0E88
0x1400b0e0f  mov     rcx, [rdi+0E8h]; hObject
0x1400b0e16  test    rcx, rcx
0x1400b0e19  jz      short loc_1400B0E21
0x1400b0e1b  call    cs:__imp_CloseHandle
0x1400b0e21  mov     [rdi+0E8h], rsi
0x1400b0e28  mov     [r15], rdi
0x1400b0e2b  mov     [rsp+540h+var_4F0], r12
0x1400b0e30  jmp     loc_1400B0F1E
0x1400b0e35  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0e3c  lea     rax, WPP_GLOBAL_Control
0x1400b0e43  cmp     rcx, rax
0x1400b0e46  jz      short loc_1400B0E80
0x1400b0e48  test    byte ptr [rcx+1Ch], 8
0x1400b0e4c  jz      short loc_1400B0E80
0x1400b0e4e  cmp     byte ptr [rcx+19h], 2
0x1400b0e52  jb      short loc_1400B0E80
0x1400b0e54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b0e59  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0e60  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b0e67  mov     edx, 0Ah
0x1400b0e6c  mov     [rsp+540h+dwCreationFlags], 8007000Eh
0x1400b0e74  mov     r9d, eax
0x1400b0e77  mov     rcx, [rcx+10h]
0x1400b0e7b  call    WPP_SF_Dd
0x1400b0e80  mov     ebx, 8007000Eh
0x1400b0e85  xor     r12d, r12d
0x1400b0e88  mov     r9d, 40h ; '@'; cchBufferMax
0x1400b0e8e  lea     r8, [rsp+540h+Buffer]; lpBuffer
0x1400b0e93  mov     edx, 34BCh; uID
0x1400b0e98  mov     rcx, r14; hInstance
0x1400b0e9b  call    cs:__imp_LoadStringW
0x1400b0ea1  mov     ecx, ebx; int
0x1400b0ea3  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1400b0ea8  mov     r8d, eax; dwMessageId
0x1400b0eab  mov     [rsp+540h+Arguments], r12; Arguments
0x1400b0eb0  lea     rax, [rsp+540h+var_4E8]
0x1400b0eb5  mov     dword ptr [rsp+540h+lpThreadId], r12d; nSize
0x1400b0eba  xor     r9d, r9d; dwLanguageId
0x1400b0ebd  mov     qword ptr [rsp+540h+dwCreationFlags], rax; lpBuffer
0x1400b0ec2  xor     edx, edx; lpSource
0x1400b0ec4  mov     ecx, 1100h; dwFlags
0x1400b0ec9  call    cs:__imp_FormatMessageW
0x1400b0ecf  test    eax, eax
0x1400b0ed1  jnz     short loc_1400B0EEB
0x1400b0ed3  mov     r9d, 200h; cchBufferMax
0x1400b0ed9  lea     r8, [rbp+440h+var_450]; lpBuffer
0x1400b0edd  mov     edx, 34BDh; uID
0x1400b0ee2  mov     rcx, r14; hInstance
0x1400b0ee5  call    cs:__imp_LoadStringW
0x1400b0eeb  mov     rax, qword ptr [rsp+540h+var_4E8]
0x1400b0ef0  lea     rdx, [rbp+440h+var_450]
0x1400b0ef4  test    rax, rax
0x1400b0ef7  lea     r8, [rsp+540h+Buffer]; lpCaption
0x1400b0efc  mov     r9d, 10h; uType
0x1400b0f02  cmovnz  rdx, rax; lpText
0x1400b0f06  xor     ecx, ecx; hWnd
0x1400b0f08  call    cs:__imp_MessageBoxW
0x1400b0f0e  mov     rcx, qword ptr [rsp+540h+var_4E8]; hMem
0x1400b0f13  test    rcx, rcx
0x1400b0f16  jz      short loc_1400B0F1E
0x1400b0f18  call    cs:__imp_LocalFree
0x1400b0f1e  lea     rcx, [rsp+540h+var_4F0]
0x1400b0f23  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1400b0f28  mov     eax, ebx
0x1400b0f2a  mov     rcx, [rbp+440h+var_50]
0x1400b0f31  xor     rcx, rsp; StackCookie
0x1400b0f34  call    __security_check_cookie
0x1400b0f39  add     rsp, 508h
0x1400b0f40  pop     r15
0x1400b0f42  pop     r14
0x1400b0f44  pop     r13
0x1400b0f46  pop     r12
0x1400b0f48  pop     rdi
0x1400b0f49  pop     rsi
0x1400b0f4a  pop     rbx
0x1400b0f4b  pop     rbp
0x1400b0f4c  retn
```
