# PAL_System_ThreadSignalDestroy(void *)

- ea: `0x140042a70`
- end: `0x140042b93`
- name: `?PAL_System_ThreadSignalDestroy@@YAJPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140020210`

## callees

- `0x1400014d4`
- `0x140042a70`

## import_xrefs

- `USER32!DestroyWindow` at `0x140042b04`
- `USER32!DestroyWindow` at `0x140042b04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140042b84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140042b84`

## string_xrefs

- `0x140042aa8`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042b32`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042a8f`: `PAL_System_ThreadSignalDestroy`
- `0x140042b19`: `PAL_System_ThreadSignalDestroy`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalDestroy(HWND *hMem, __int64 a2, int a3, int a4)
{
  HWND v6; // rcx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  _QWORD v10[3]; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  int v12; // [rsp+88h] [rbp+20h] BYREF
  const char *v13; // [rsp+90h] [rbp+28h] BYREF
  const char *v14; // [rsp+98h] [rbp+30h] BYREF

  if ( hMem )
  {
    v6 = *hMem;
    if ( v6 && !DestroyWindow(v6) && (unsigned int)dword_1400880C8 > 2 )
    {
      v11 = 735;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = "Failed to destroy window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&byte_14008080F,
        v8,
        v9,
        (__int64)v10,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v13);
    }
    LocalFree(hMem);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      v11 = 724;
      v13 = "PAL_System_ThreadSignalDestroy";
      v12 = -2147467259;
      v14 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
      v10[0] = "NULL parameter passed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)&byte_140080567,
        a3,
        a4,
        (__int64)v10,
        (__int64)&v12,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v13);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140042a70  mov     r11, rsp
0x140042a73  push    rbp
0x140042a74  push    rbx
0x140042a75  mov     rbp, rsp
0x140042a78  sub     rsp, 68h
0x140042a7c  mov     rbx, rcx
0x140042a7f  test    rcx, rcx
0x140042a82  jnz     short loc_140042AFC
0x140042a84  mov     eax, cs:dword_1400880C8
0x140042a8a  cmp     eax, 2
0x140042a8d  jbe     short loc_140042AF2
0x140042a8f  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x140042a96  mov     [rbp+arg_0], 2D4h
0x140042a9d  mov     [rbp+arg_10], rax
0x140042aa1  lea     rdx, byte_140080567
0x140042aa8  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042aaf  mov     [rbp+arg_8], 80004005h
0x140042ab6  mov     [rbp+arg_18], rax
0x140042aba  lea     rax, aNullParameterP; "NULL parameter passed"
0x140042ac1  mov     [rbp+var_18], rax
0x140042ac5  lea     rax, [rbp+arg_10]
0x140042ac9  mov     [r11-38h], rax
0x140042acd  lea     rax, [rbp+arg_0]
0x140042ad1  mov     [r11-40h], rax
0x140042ad5  lea     rax, [rbp+arg_18]
0x140042ad9  mov     [r11-48h], rax
0x140042add  lea     rax, [rbp+arg_8]
0x140042ae1  mov     [r11-50h], rax
0x140042ae5  lea     rax, [rbp+var_18]
0x140042ae9  mov     [r11-58h], rax
0x140042aed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042af2  mov     eax, 80070057h
0x140042af7  jmp     loc_140042B8C
0x140042afc  mov     rcx, [rcx]; hWnd
0x140042aff  test    rcx, rcx
0x140042b02  jz      short loc_140042B81
0x140042b04  call    cs:__imp_DestroyWindow
0x140042b0a  test    eax, eax
0x140042b0c  jnz     short loc_140042B81
0x140042b0e  mov     eax, cs:dword_1400880C8
0x140042b14  cmp     eax, 2
0x140042b17  jbe     short loc_140042B81
0x140042b19  lea     rax, aPalSystemThrea_7; "PAL_System_ThreadSignalDestroy"
0x140042b20  mov     [rbp+arg_0], 2DFh
0x140042b27  mov     [rbp+arg_10], rax
0x140042b2b  lea     rdx, byte_14008080F
0x140042b32  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042b39  mov     [rbp+arg_8], 80004005h
0x140042b40  mov     [rbp+arg_18], rax
0x140042b44  lea     rax, aFailedToDestro_0; "Failed to destroy window"
0x140042b4b  mov     [rbp+var_18], rax
0x140042b4f  lea     rax, [rbp+arg_10]
0x140042b53  mov     [rsp+68h+var_28], rax
0x140042b58  lea     rax, [rbp+arg_0]
0x140042b5c  mov     [rsp+68h+var_30], rax
0x140042b61  lea     rax, [rbp+arg_18]
0x140042b65  mov     [rsp+68h+var_38], rax
0x140042b6a  lea     rax, [rbp+arg_8]
0x140042b6e  mov     [rsp+68h+var_40], rax
0x140042b73  lea     rax, [rbp+var_18]
0x140042b77  mov     [rsp+68h+var_48], rax
0x140042b7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042b81  mov     rcx, rbx; hMem
0x140042b84  call    cs:__imp_LocalFree
0x140042b8a  xor     eax, eax
0x140042b8c  add     rsp, 68h
0x140042b90  pop     rbx
0x140042b91  pop     rbp
0x140042b92  retn
```
