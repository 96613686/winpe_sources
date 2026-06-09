# PAL_System_ThreadSignalPulse(void *)

- ea: `0x18002b0dc`
- end: `0x18002b1a6`
- name: `?PAL_System_ThreadSignalPulse@@YAJPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028f30`

## callees

- `0x180001f98`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b123`
- `USER32!PostMessageW` at `0x18002b105`
- `USER32!PostMessageW` at `0x18002b105`

## string_xrefs

- `0x18002b145`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002b13a`: `PAL_System_ThreadSignalPulse`
- `0x18002b150`: `Failed to post thread message. Error %d`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalPulse(void *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  const char *v8; // [rsp+58h] [rbp-10h] BYREF
  DWORD v9; // [rsp+80h] [rbp+18h] BYREF
  int v10; // [rsp+88h] [rbp+20h] BYREF
  int v11; // [rsp+90h] [rbp+28h] BYREF
  const char *v12; // [rsp+98h] [rbp+30h] BYREF

  if ( a1 )
  {
    if ( PostMessageW(*(HWND *)a1, 0x413u, *((_QWORD *)a1 + 1), *((_QWORD *)a1 + 2)) )
    {
      return 0;
    }
    else
    {
      v1 = -2147467259;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LastError = GetLastError();
        v10 = 683;
        v9 = LastError;
        v12 = "PAL_System_ThreadSignalPulse";
        v7 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        v8 = "Failed to post thread message. Error %d";
        v11 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v3,
          (__int64)&word_180040386,
          v4,
          v5,
          (const unsigned __int16 **)&v8,
          (__int64)&v11,
          (const unsigned __int16 **)&v7,
          (__int64)&v10,
          (const unsigned __int16 **)&v12,
          (__int64)&v9);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v1;
}

```

## disassembly

```asm
0x18002b0dc  push    rbp
0x18002b0de  push    rbx
0x18002b0df  mov     rbp, rsp
0x18002b0e2  sub     rsp, 68h
0x18002b0e6  test    rcx, rcx
0x18002b0e9  jnz     short loc_18002B0F5
0x18002b0eb  mov     ebx, 80070057h
0x18002b0f0  jmp     loc_18002B19D
0x18002b0f5  mov     r9, [rcx+10h]; lParam
0x18002b0f9  mov     edx, 413h; Msg
0x18002b0fe  mov     r8, [rcx+8]; wParam
0x18002b102  mov     rcx, [rcx]; hWnd
0x18002b105  call    cs:__imp_PostMessageW
0x18002b10b  test    eax, eax
0x18002b10d  jnz     loc_18002B19B
0x18002b113  mov     eax, cs:dword_180044008
0x18002b119  mov     ebx, 80004005h
0x18002b11e  cmp     eax, 2
0x18002b121  jbe     short loc_18002B19D
0x18002b123  call    cs:__imp_GetLastError
0x18002b129  lea     rdx, word_180040386
0x18002b130  mov     [rbp+arg_8], 2ABh
0x18002b137  mov     [rbp+arg_0], eax
0x18002b13a  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalPulse"
0x18002b141  mov     [rbp+arg_18], rax
0x18002b145  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b14c  mov     [rbp+var_18], rax
0x18002b150  lea     rax, aFailedToPostTh_0; "Failed to post thread message. Error %d"
0x18002b157  mov     [rbp+var_10], rax
0x18002b15b  lea     rax, [rbp+arg_0]
0x18002b15f  mov     [rsp+68h+var_20], rax
0x18002b164  lea     rax, [rbp+arg_18]
0x18002b168  mov     [rsp+68h+var_28], rax
0x18002b16d  lea     rax, [rbp+arg_8]
0x18002b171  mov     [rsp+68h+var_30], rax
0x18002b176  lea     rax, [rbp+var_18]
0x18002b17a  mov     [rsp+68h+var_38], rax
0x18002b17f  lea     rax, [rbp+arg_10]
0x18002b183  mov     [rsp+68h+var_40], rax
0x18002b188  lea     rax, [rbp+var_10]
0x18002b18c  mov     [rsp+68h+var_48], rax
0x18002b191  mov     [rbp+arg_10], ebx
0x18002b194  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b199  jmp     short loc_18002B19D
0x18002b19b  xor     ebx, ebx
0x18002b19d  mov     eax, ebx
0x18002b19f  add     rsp, 68h
0x18002b1a3  pop     rbx
0x18002b1a4  pop     rbp
0x18002b1a5  retn
```
