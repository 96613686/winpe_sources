# AOMDHandler::CleanupToastsOnExit(void)

- ea: `0x180009fc0`
- end: `0x18000a28d`
- name: `?CleanupToastsOnExit@AOMDHandler@@AEAAJXZ`
- size: `717`
- prototype: `__int64 __fastcall(AOMDHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007944`

## callees

- `0x180001008`
- `0x180002e50`
- `0x180009fc0`
- `0x18000e7ec`
- `0x18000ee30`
- `0x1800109d4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a18c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a085`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a085`

## pseudocode

```c
__int64 __fastcall AOMDHandler::CleanupToastsOnExit(AOMDHandler *this)
{
  const struct _tlgProvider_t *v1; // rax
  __int64 v2; // r8
  __int64 v3; // r9
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // rbx
  __int64 v17; // rdi
  unsigned __int64 v18; // rdx
  HRESULT v19; // eax
  int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  unsigned int v23; // ebx
  _QWORD *v24; // rcx
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-58h]
  __int64 v29; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v30; // [rsp+38h] [rbp-40h] BYREF
  int v31[2]; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = TlgHelper::Provider();
  if ( *(_DWORD *)v1 > 4u && (*((_QWORD *)v1 + 2) & 2) != 0 && (*((_QWORD *)v1 + 3) & 2LL) == *((_QWORD *)v1 + 3) )
  {
    *(_QWORD *)v31 = L"CleanupToastsOnExit_Starting";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v1,
      (__int64)&word_180029B1E,
      v2,
      v3,
      (int **)v31);
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
      (void *)0x468,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    v9 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v30 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v29 + 48LL))(v29, &v30);
  v13 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46B,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v11,
      v28);
    v14 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    v15 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v13;
  }
  v16 = v30;
  v17 = *v30;
  string = 0;
  v18 = -1;
  do
    ++v18;
  while ( aWindowsSystemt[v18] );
  if ( v18 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v18, v12);
    JUMPOUT(0x18000A28BLL);
  }
  if ( (int)v18 + 1 < (unsigned int)v18 )
  {
LABEL_33:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v18, v12);
    __debugbreak();
  }
  v19 = WindowsCreateStringReference(L"Windows.SystemToast.AOMD.MainToast", v18, &hstringHeader, &string);
  if ( v19 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v19, v20, v21);
    __debugbreak();
  }
  v22 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING))(v17 + 96))(v16, string);
  v23 = v22;
  if ( v22 >= 0 )
  {
    v26 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
    }
    v27 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
      (const char *)(unsigned int)v22,
      v28);
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v24 + 16LL))(v24);
    }
    v25 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return v23;
  }
}

```

## disassembly

```asm
0x180009fc0  mov     [rsp+arg_0], rbx
0x180009fc5  mov     [rsp+arg_8], rsi
0x180009fca  push    rdi
0x180009fcb  sub     rsp, 70h
0x180009fcf  mov     rax, cs:__security_cookie
0x180009fd6  xor     rax, rsp
0x180009fd9  mov     [rsp+78h+var_10], rax
0x180009fde  call    ?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ; TlgHelper::Provider(void)
0x180009fe3  mov     ecx, [rax]
0x180009fe5  cmp     ecx, 4
0x180009fe8  jbe     short loc_18000A027
0x180009fea  mov     rdx, [rax+18h]
0x180009fee  mov     rcx, [rax+10h]
0x180009ff2  test    cl, 2
0x180009ff5  jz      short loc_18000A027
0x180009ff7  mov     rcx, rdx
0x180009ffa  and     ecx, 2
0x180009ffd  cmp     rcx, rdx
0x18000a000  jnz     short loc_18000A027
0x18000a002  lea     rcx, aCleanuptoastso; "CleanupToastsOnExit_Starting"
0x18000a009  mov     qword ptr [rsp+78h+var_38], rcx
0x18000a00e  lea     rcx, [rsp+78h+var_38]
0x18000a013  mov     qword ptr [rsp+78h+var_58], rcx; int
0x18000a018  lea     rdx, word_180029B1E
0x18000a01f  mov     rcx, rax
0x18000a022  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a027  xor     esi, esi
0x18000a029  mov     [rsp+78h+var_48], rsi
0x18000a02e  mov     [rsp+78h+string], rsi
0x18000a033  lea     r9, [rsp+78h+string]; string
0x18000a038  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18000a03d  lea     edx, [rsi+31h]; length
0x18000a040  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x18000a047  call    cs:__imp_WindowsCreateStringReference
0x18000a04d  test    eax, eax
0x18000a04f  js      loc_18000A266
0x18000a055  mov     rbx, [rsp+78h+string]
0x18000a05a  mov     rcx, [rsp+78h+var_48]
0x18000a05f  test    rcx, rcx
0x18000a062  jz      short loc_18000A076
0x18000a064  mov     [rsp+78h+var_48], rsi
0x18000a069  mov     rax, [rcx]
0x18000a06c  mov     rax, [rax+10h]
0x18000a070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a075  nop
0x18000a076  lea     r8, [rsp+78h+var_48]
0x18000a07b  lea     rdx, _GUID_7ab93c52_0e48_4750_ba9d_1a4113981847
0x18000a082  mov     rcx, rbx
0x18000a085  call    cs:__imp_RoGetActivationFactory
0x18000a08b  mov     ebx, eax
0x18000a08d  test    eax, eax
0x18000a08f  jns     short loc_18000A0CE
0x18000a091  mov     rcx, [rsp+78h]; this
0x18000a096  mov     r9d, eax; char *
0x18000a099  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a0a0  mov     edx, 468h; void *
0x18000a0a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0aa  nop
0x18000a0ab  mov     rcx, [rsp+78h+var_48]
0x18000a0b0  test    rcx, rcx
0x18000a0b3  jz      short loc_18000A0C7
0x18000a0b5  mov     [rsp+78h+var_48], rsi
0x18000a0ba  mov     rax, [rcx]
0x18000a0bd  mov     rax, [rax+10h]
0x18000a0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c6  nop
0x18000a0c7  mov     eax, ebx
0x18000a0c9  jmp     loc_18000A247
0x18000a0ce  mov     [rsp+78h+var_40], rsi
0x18000a0d3  mov     rcx, [rsp+78h+var_48]
0x18000a0d8  mov     rax, [rcx]
0x18000a0db  lea     rdx, [rsp+78h+var_40]
0x18000a0e0  mov     rax, [rax+30h]
0x18000a0e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e9  mov     ebx, eax
0x18000a0eb  test    eax, eax
0x18000a0ed  jns     short loc_18000A148
0x18000a0ef  mov     rcx, [rsp+78h]; this
0x18000a0f4  mov     r9d, eax; char *
0x18000a0f7  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a0fe  mov     edx, 46Bh; void *
0x18000a103  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a108  nop
0x18000a109  mov     rcx, [rsp+78h+var_40]
0x18000a10e  test    rcx, rcx
0x18000a111  jz      short loc_18000A125
0x18000a113  mov     [rsp+78h+var_40], rsi
0x18000a118  mov     rax, [rcx]
0x18000a11b  mov     rax, [rax+10h]
0x18000a11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a124  nop
0x18000a125  mov     rcx, [rsp+78h+var_48]
0x18000a12a  test    rcx, rcx
0x18000a12d  jz      short loc_18000A141
0x18000a12f  mov     [rsp+78h+var_48], rsi
0x18000a134  mov     rax, [rcx]
0x18000a137  mov     rax, [rax+10h]
0x18000a13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a140  nop
0x18000a141  mov     eax, ebx
0x18000a143  jmp     loc_18000A247
0x18000a148  mov     rbx, [rsp+78h+var_40]
0x18000a14d  mov     rdi, [rbx]
0x18000a150  mov     [rsp+78h+string], rsi
0x18000a155  mov     rcx, cs:sourceString; sourceString
0x18000a15c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a160  inc     rdx; int
0x18000a163  cmp     [rcx+rdx*2], si
0x18000a167  jnz     short loc_18000A160
0x18000a169  mov     eax, 0FFFFFFFFh
0x18000a16e  cmp     rdx, rax
0x18000a171  ja      loc_18000A281
0x18000a177  lea     eax, [rdx+1]
0x18000a17a  cmp     eax, edx
0x18000a17c  jb      loc_18000A26E
0x18000a182  lea     r9, [rsp+78h+string]; string
0x18000a187  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18000a18c  call    cs:__imp_WindowsCreateStringReference
0x18000a192  test    eax, eax
0x18000a194  js      loc_18000A279
0x18000a19a  mov     rdx, [rsp+78h+string]
0x18000a19f  mov     rcx, rbx
0x18000a1a2  mov     rax, [rdi+60h]
0x18000a1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ab  mov     ebx, eax
0x18000a1ad  test    eax, eax
0x18000a1af  jns     short loc_18000A207
0x18000a1b1  mov     rcx, [rsp+78h]; this
0x18000a1b6  mov     r9d, eax; char *
0x18000a1b9  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18000a1c0  mov     edx, 46Ch; void *
0x18000a1c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1ca  nop
0x18000a1cb  mov     rcx, [rsp+78h+var_40]
0x18000a1d0  test    rcx, rcx
0x18000a1d3  jz      short loc_18000A1E7
0x18000a1d5  mov     [rsp+78h+var_40], rsi
0x18000a1da  mov     rax, [rcx]
0x18000a1dd  mov     rax, [rax+10h]
0x18000a1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e6  nop
0x18000a1e7  mov     rcx, [rsp+78h+var_48]
0x18000a1ec  test    rcx, rcx
0x18000a1ef  jz      short loc_18000A203
0x18000a1f1  mov     [rsp+78h+var_48], rsi
0x18000a1f6  mov     rax, [rcx]
0x18000a1f9  mov     rax, [rax+10h]
0x18000a1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a202  nop
0x18000a203  mov     eax, ebx
0x18000a205  jmp     short loc_18000A247
0x18000a207  mov     rcx, [rsp+78h+var_40]
0x18000a20c  test    rcx, rcx
0x18000a20f  jz      short loc_18000A223
0x18000a211  mov     [rsp+78h+var_40], rsi
0x18000a216  mov     rax, [rcx]
0x18000a219  mov     rax, [rax+10h]
0x18000a21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a222  nop
0x18000a223  mov     rcx, [rsp+78h+var_48]
0x18000a228  test    rcx, rcx
0x18000a22b  jz      short loc_18000A23F
0x18000a22d  mov     [rsp+78h+var_48], rsi
0x18000a232  mov     rax, [rcx]
0x18000a235  mov     rax, [rax+10h]
0x18000a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23e  nop
0x18000a23f  xor     eax, eax
0x18000a241  jmp     short loc_18000A247
0x18000a243  mov     eax, dword ptr [rsp+78h+var_48]
0x18000a247  mov     rcx, [rsp+78h+var_10]
0x18000a24c  xor     rcx, rsp; StackCookie
0x18000a24f  call    __security_check_cookie
0x18000a254  lea     r11, [rsp+78h+var_8]
0x18000a259  mov     rbx, [r11+10h]
0x18000a25d  mov     rsi, [r11+18h]
0x18000a261  mov     rsp, r11
0x18000a264  pop     rdi
0x18000a265  retn
0x18000a266  mov     ecx, eax; this
0x18000a268  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a26d  nop
0x18000a26e  mov     ecx, 80070216h; this
0x18000a273  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a278  int     3; Trap to Debugger
0x18000a279  mov     ecx, eax; this
0x18000a27b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000a280  int     3; Trap to Debugger
0x18000a281  mov     ecx, 80070216h; this
0x18000a286  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
