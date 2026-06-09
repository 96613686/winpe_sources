# PAL_System_ThreadSignalPulse(void *)

- ea: `0x140042b9c`
- end: `0x140042c66`
- name: `?PAL_System_ThreadSignalPulse@@YAJPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140020220`

## callees

- `0x1400015ec`
- `0x140042b9c`

## import_xrefs

- `USER32!PostMessageW` at `0x140042bc5`
- `USER32!PostMessageW` at `0x140042bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042be3`

## string_xrefs

- `0x140042c05`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042bfa`: `PAL_System_ThreadSignalPulse`
- `0x140042c10`: `Failed to post thread message. Error %d`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadSignalPulse(void *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
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
      if ( (unsigned int)dword_1400880C8 > 2 )
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
          (unsigned int)byte_1400805F1,
          v4,
          v5,
          (__int64)&v8,
          (__int64)&v11,
          (__int64)&v7,
          (__int64)&v10,
          (__int64)&v12,
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
0x140042b9c  push    rbp
0x140042b9e  push    rbx
0x140042b9f  mov     rbp, rsp
0x140042ba2  sub     rsp, 68h
0x140042ba6  test    rcx, rcx
0x140042ba9  jnz     short loc_140042BB5
0x140042bab  mov     ebx, 80070057h
0x140042bb0  jmp     loc_140042C5D
0x140042bb5  mov     r9, [rcx+10h]; lParam
0x140042bb9  mov     edx, 413h; Msg
0x140042bbe  mov     r8, [rcx+8]; wParam
0x140042bc2  mov     rcx, [rcx]; hWnd
0x140042bc5  call    cs:__imp_PostMessageW
0x140042bcb  test    eax, eax
0x140042bcd  jnz     loc_140042C5B
0x140042bd3  mov     eax, cs:dword_1400880C8
0x140042bd9  mov     ebx, 80004005h
0x140042bde  cmp     eax, 2
0x140042be1  jbe     short loc_140042C5D
0x140042be3  call    cs:__imp_GetLastError
0x140042be9  lea     rdx, byte_1400805F1
0x140042bf0  mov     [rbp+arg_8], 2ABh
0x140042bf7  mov     [rbp+arg_0], eax
0x140042bfa  lea     rax, aPalSystemThrea_1; "PAL_System_ThreadSignalPulse"
0x140042c01  mov     [rbp+arg_18], rax
0x140042c05  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042c0c  mov     [rbp+var_18], rax
0x140042c10  lea     rax, aFailedToPostTh_0; "Failed to post thread message. Error %d"
0x140042c17  mov     [rbp+var_10], rax
0x140042c1b  lea     rax, [rbp+arg_0]
0x140042c1f  mov     [rsp+68h+var_20], rax
0x140042c24  lea     rax, [rbp+arg_18]
0x140042c28  mov     [rsp+68h+var_28], rax
0x140042c2d  lea     rax, [rbp+arg_8]
0x140042c31  mov     [rsp+68h+var_30], rax
0x140042c36  lea     rax, [rbp+var_18]
0x140042c3a  mov     [rsp+68h+var_38], rax
0x140042c3f  lea     rax, [rbp+arg_10]
0x140042c43  mov     [rsp+68h+var_40], rax
0x140042c48  lea     rax, [rbp+var_10]
0x140042c4c  mov     [rsp+68h+var_48], rax
0x140042c51  mov     [rbp+arg_10], ebx
0x140042c54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140042c59  jmp     short loc_140042C5D
0x140042c5b  xor     ebx, ebx
0x140042c5d  mov     eax, ebx
0x140042c5f  add     rsp, 68h
0x140042c63  pop     rbx
0x140042c64  pop     rbp
0x140042c65  retn
```
