# AOMDHandler::CleanupToastsOnExit(void)

- ea: `0x18000a1a8`
- end: `0x18000a487`
- name: `?CleanupToastsOnExit@AOMDHandler@@AEAAJXZ`
- size: `735`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x1800026b0`
- `0x18000a1a8`
- `0x18000f144`
- `0x18000f6d8`
- `0x1800113a4`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a228`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a380`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a26c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a26c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall AOMDHandler::CleanupToastsOnExit(AOMDHandler *this)
{
  const struct _tlgProvider_t *v1; // rax
  int v2; // r8d
  int v3; // r9d
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  __int64 v14; // rcx
  _QWORD *v15; // rcx
  __int64 v16; // rbx
  __int64 (__fastcall *v17)(__int64, HSTRING); // rdi
  unsigned __int64 v18; // rdx
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  int v28; // [rsp+20h] [rbp-58h]
  _QWORD *v29; // [rsp+30h] [rbp-48h] BYREF
  __int64 v30; // [rsp+38h] [rbp-40h] BYREF
  int v31[2]; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = TlgHelper::Provider();
  if ( *(_DWORD *)v1 > 4u && (*((_BYTE *)v1 + 16) & 2) != 0 && (*((_QWORD *)v1 + 3) & 2LL) == *((_QWORD *)v1 + 3) )
  {
    *(_QWORD *)v31 = L"CleanupToastsOnExit_Starting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)v1,
      (unsigned int)&unk_18002AB01,
      v2,
      v3,
      (__int64)v31);
  }
  v29 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.UI.Notifications.ToastNotificationManager",
         0x31u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    goto LABEL_33;
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_7ab93c52_0e48_4750_ba9d_1a4113981847, &v29);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C7,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    v9 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    return v8;
  }
  v30 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v29 + 48LL))(v29, &v30);
  v13 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CA,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v11,
      v28);
    v14 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v15 + 16LL))(v15, *v15);
    }
    return v13;
  }
  v16 = v30;
  v17 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v30 + 96LL);
  string = 0;
  v18 = -1;
  do
    ++v18;
  while ( aWindowsSystemt[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v18, v12);
    JUMPOUT(0x18000A485LL);
  }
  if ( (int)v18 + 1 < (unsigned int)v18 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v18, v12);
    __debugbreak();
  }
  v19 = WindowsCreateStringReference(L"Windows.SystemToast.AOMD.MainToast", v18, &hstringHeader, &string);
  if ( v19 < 0 )
  {
LABEL_33:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  v22 = v17(v16, string);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v26 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4CB,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v22,
      v28);
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v25 + 16LL))(v25, *v25);
    }
    return v23;
  }
}

```

## disassembly

```asm
0x18000a1a8  mov     [rsp+arg_0], rbx
0x18000a1ad  mov     [rsp+arg_8], rsi
0x18000a1b2  push    rdi
0x18000a1b3  sub     rsp, 70h
0x18000a1b7  mov     rax, cs:__security_cookie
0x18000a1be  xor     rax, rsp
0x18000a1c1  mov     [rsp+78h+var_10], rax
0x18000a1c6  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x18000a1cb  cmp     dword ptr [rax], 4
0x18000a1ce  jbe     short loc_18000A208
0x18000a1d0  test    byte ptr [rax+10h], 2
0x18000a1d4  jz      short loc_18000A208
0x18000a1d6  mov     rcx, [rax+18h]
0x18000a1da  and     ecx, 2
0x18000a1dd  cmp     rcx, [rax+18h]
0x18000a1e1  jnz     short loc_18000A208
0x18000a1e3  lea     rcx, aCleanuptoastso; "CleanupToastsOnExit_Starting"
0x18000a1ea  mov     qword ptr [rsp+78h+var_38], rcx
0x18000a1ef  lea     rcx, [rsp+78h+var_38]
0x18000a1f4  mov     qword ptr [rsp+78h+var_58], rcx; int
0x18000a1f9  lea     rdx, byte_18002AB01
0x18000a200  mov     rcx, rax
0x18000a203  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a208  xor     esi, esi
0x18000a20a  mov     [rsp+78h+var_48], rsi
0x18000a20f  mov     [rsp+78h+string], rsi
0x18000a214  lea     r9, [rsp+78h+string]; string
0x18000a219  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18000a21e  lea     edx, [rsi+31h]; length
0x18000a221  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x18000a228  call    cs:__imp_WindowsCreateStringReference
0x18000a22f  nop     dword ptr [rax+rax+00h]
0x18000a234  test    eax, eax
0x18000a236  js      loc_18000A460
0x18000a23c  mov     rbx, [rsp+78h+string]
0x18000a241  mov     rcx, [rsp+78h+var_48]
0x18000a246  test    rcx, rcx
0x18000a249  jz      short loc_18000A25D
0x18000a24b  mov     [rsp+78h+var_48], rsi
0x18000a250  mov     rax, [rcx]
0x18000a253  mov     rax, [rax+10h]
0x18000a257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25c  nop
0x18000a25d  lea     r8, [rsp+78h+var_48]
0x18000a262  lea     rdx, _GUID_7ab93c52_0e48_4750_ba9d_1a4113981847
0x18000a269  mov     rcx, rbx
0x18000a26c  call    cs:__imp_RoGetActivationFactory
0x18000a273  nop     dword ptr [rax+rax+00h]
0x18000a278  mov     ebx, eax
0x18000a27a  test    eax, eax
0x18000a27c  jns     short loc_18000A2BB
0x18000a27e  mov     rcx, [rsp+78h]; this
0x18000a283  mov     r9d, eax; char *
0x18000a286  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a28d  mov     edx, 4C7h; void *
0x18000a292  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a297  nop
0x18000a298  mov     rcx, [rsp+78h+var_48]
0x18000a29d  test    rcx, rcx
0x18000a2a0  jz      short loc_18000A2B4
0x18000a2a2  mov     [rsp+78h+var_48], rsi
0x18000a2a7  mov     rax, [rcx]
0x18000a2aa  mov     rax, [rax+10h]
0x18000a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b3  nop
0x18000a2b4  mov     eax, ebx
0x18000a2b6  jmp     loc_18000A440
0x18000a2bb  mov     [rsp+78h+var_40], rsi
0x18000a2c0  mov     rcx, [rsp+78h+var_48]
0x18000a2c5  mov     rax, [rcx]
0x18000a2c8  lea     rdx, [rsp+78h+var_40]
0x18000a2cd  mov     rax, [rax+30h]
0x18000a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d6  mov     ebx, eax
0x18000a2d8  test    eax, eax
0x18000a2da  jns     short loc_18000A335
0x18000a2dc  mov     rcx, [rsp+78h]; this
0x18000a2e1  mov     r9d, eax; char *
0x18000a2e4  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a2eb  mov     edx, 4CAh; void *
0x18000a2f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2f5  nop
0x18000a2f6  mov     rcx, [rsp+78h+var_40]
0x18000a2fb  test    rcx, rcx
0x18000a2fe  jz      short loc_18000A312
0x18000a300  mov     [rsp+78h+var_40], rsi
0x18000a305  mov     rax, [rcx]
0x18000a308  mov     rax, [rax+10h]
0x18000a30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a311  nop
0x18000a312  mov     rcx, [rsp+78h+var_48]
0x18000a317  test    rcx, rcx
0x18000a31a  jz      short loc_18000A32E
0x18000a31c  mov     [rsp+78h+var_48], rsi
0x18000a321  mov     rdx, [rcx]
0x18000a324  mov     rax, [rdx+10h]
0x18000a328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32d  nop
0x18000a32e  mov     eax, ebx
0x18000a330  jmp     loc_18000A440
0x18000a335  mov     rbx, [rsp+78h+var_40]
0x18000a33a  mov     rax, [rbx]
0x18000a33d  mov     rdi, [rax+60h]
0x18000a341  mov     [rsp+78h+string], rsi
0x18000a346  mov     rcx, cs:sourceString; sourceString
0x18000a34d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a351  inc     rdx; int
0x18000a354  cmp     [rcx+rdx*2], si
0x18000a358  jnz     short loc_18000A351
0x18000a35a  mov     eax, 0FFFFFFFFh
0x18000a35f  cmp     rdx, rax
0x18000a362  ja      loc_18000A47B
0x18000a368  lea     eax, [rdx+1]
0x18000a36b  cmp     eax, edx
0x18000a36d  jb      loc_18000A470
0x18000a373  cmova   edx, edx; length
0x18000a376  lea     r9, [rsp+78h+string]; string
0x18000a37b  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18000a380  call    cs:__imp_WindowsCreateStringReference
0x18000a387  nop     dword ptr [rax+rax+00h]
0x18000a38c  test    eax, eax
0x18000a38e  js      loc_18000A468
0x18000a394  mov     rdx, [rsp+78h+string]
0x18000a399  mov     rcx, rbx
0x18000a39c  mov     rax, rdi
0x18000a39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a4  mov     ebx, eax
0x18000a3a6  test    eax, eax
0x18000a3a8  jns     short loc_18000A400
0x18000a3aa  mov     rcx, [rsp+78h]; this
0x18000a3af  mov     r9d, eax; char *
0x18000a3b2  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a3b9  mov     edx, 4CBh; void *
0x18000a3be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3c3  nop
0x18000a3c4  mov     rcx, [rsp+78h+var_40]
0x18000a3c9  test    rcx, rcx
0x18000a3cc  jz      short loc_18000A3E0
0x18000a3ce  mov     [rsp+78h+var_40], rsi
0x18000a3d3  mov     rax, [rcx]
0x18000a3d6  mov     rax, [rax+10h]
0x18000a3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3df  nop
0x18000a3e0  mov     rcx, [rsp+78h+var_48]
0x18000a3e5  test    rcx, rcx
0x18000a3e8  jz      short loc_18000A3FC
0x18000a3ea  mov     [rsp+78h+var_48], rsi
0x18000a3ef  mov     rdx, [rcx]
0x18000a3f2  mov     rax, [rdx+10h]
0x18000a3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3fb  nop
0x18000a3fc  mov     eax, ebx
0x18000a3fe  jmp     short loc_18000A440
0x18000a400  mov     rcx, [rsp+78h+var_40]
0x18000a405  test    rcx, rcx
0x18000a408  jz      short loc_18000A41C
0x18000a40a  mov     [rsp+78h+var_40], rsi
0x18000a40f  mov     rax, [rcx]
0x18000a412  mov     rax, [rax+10h]
0x18000a416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41b  nop
0x18000a41c  mov     rcx, [rsp+78h+var_48]
0x18000a421  test    rcx, rcx
0x18000a424  jz      short loc_18000A438
0x18000a426  mov     [rsp+78h+var_48], rsi
0x18000a42b  mov     rax, [rcx]
0x18000a42e  mov     rax, [rax+10h]
0x18000a432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a437  nop
0x18000a438  xor     eax, eax
0x18000a43a  jmp     short loc_18000A440
0x18000a43c  mov     eax, dword ptr [rsp+78h+var_48]
0x18000a440  mov     rcx, [rsp+78h+var_10]
0x18000a445  xor     rcx, rsp; StackCookie
0x18000a448  call    __security_check_cookie
0x18000a44d  lea     r11, [rsp+78h+var_8]
0x18000a452  mov     rbx, [r11+10h]
0x18000a456  mov     rsi, [r11+18h]
0x18000a45a  mov     rsp, r11
0x18000a45d  pop     rdi
0x18000a45e  retn
0x18000a460  mov     ecx, eax; this
0x18000a462  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a467  nop
0x18000a468  mov     ecx, eax; this
0x18000a46a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a46f  int     3; Trap to Debugger
0x18000a470  mov     ecx, 80070216h; this
0x18000a475  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a47a  int     3; Trap to Debugger
0x18000a47b  mov     ecx, 80070216h; this
0x18000a480  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
