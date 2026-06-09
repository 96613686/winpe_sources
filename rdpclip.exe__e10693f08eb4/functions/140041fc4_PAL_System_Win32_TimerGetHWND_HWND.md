# PAL_System_Win32_TimerGetHWND(HWND__ * *)

- ea: `0x140041fc4`
- end: `0x140042134`
- name: `?PAL_System_Win32_TimerGetHWND@@YAJPEAPEAUHWND__@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140043268`
- `0x1400434bc`

## callees

- `0x1400014d4`
- `0x140041c78`
- `0x140041fc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400420d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400420d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14004205a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x14004205a`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400420cb`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400420cb`

## string_xrefs

- `0x140042004`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1400420a7`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x14004210e`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x1400420b2`: `Failed to create timer window`

## pseudocode

```c
__int64 __fastcall PAL_System_Win32_TimerGetHWND(HWND *a1, __int64 a2, int a3, int a4)
{
  HWND *v4; // rdi
  int Window; // ebx
  __int64 *v6; // rdx
  const char *v7; // rax
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // r9d
  HWND v11; // rbx
  signed int LastError; // eax
  const char *v14; // [rsp+50h] [rbp-10h] BYREF
  LPVOID lpTlsValue; // [rsp+80h] [rbp+20h] BYREF
  int v16; // [rsp+88h] [rbp+28h] BYREF
  const char *v17; // [rsp+90h] [rbp+30h] BYREF
  const char *v18; // [rsp+98h] [rbp+38h] BYREF

  v4 = a1;
  if ( a1 )
  {
    lpTlsValue = TlsGetValue(g_PAL_SYS_timerWndIndex);
    v11 = (HWND)lpTlsValue;
    if ( lpTlsValue )
      goto LABEL_14;
    Window = PAL_System_Win32_TimerCreateWindow((HWND *)&lpTlsValue, v8, v9, v10);
    if ( Window < 0 )
    {
      LODWORD(a1) = dword_1400880C8;
      if ( (unsigned int)dword_1400880C8 <= 2 )
        return (unsigned int)Window;
      LODWORD(lpTlsValue) = 93;
      v17 = "PAL_System_Win32_TimerGetHWND";
      v6 = (__int64 *)byte_14008032D;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v7 = "Failed to create timer window";
      goto LABEL_4;
    }
    v11 = (HWND)lpTlsValue;
    if ( TlsSetValue(g_PAL_SYS_timerWndIndex, lpTlsValue) )
    {
LABEL_14:
      *v4 = v11;
      return 0;
    }
    LastError = GetLastError();
    Window = LastError;
    if ( LastError > 0 )
      Window = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(lpTlsValue) = 100;
      v17 = "PAL_System_Win32_TimerGetHWND";
      v6 = (__int64 *)&dword_1400801D4;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v7 = "Failed to set timer window TLS value";
      goto LABEL_4;
    }
  }
  else
  {
    Window = -2147024809;
    if ( (unsigned int)dword_1400880C8 > 2 )
    {
      LODWORD(lpTlsValue) = 79;
      v17 = "PAL_System_Win32_TimerGetHWND";
      v6 = qword_1400802E8;
      v18 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32int.cpp";
      v7 = "Invalid parameter passed";
LABEL_4:
      v14 = v7;
      v16 = Window;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (_DWORD)v6,
        a3,
        a4,
        (__int64)&v14,
        (__int64)&v16,
        (__int64)&v18,
        (__int64)&lpTlsValue,
        (__int64)&v17);
    }
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x140041fc4  push    rbp
0x140041fc6  push    rbx
0x140041fc7  push    rdi
0x140041fc8  mov     rbp, rsp
0x140041fcb  sub     rsp, 60h
0x140041fcf  mov     rdi, rcx
0x140041fd2  test    rcx, rcx
0x140041fd5  jnz     short loc_140042054
0x140041fd7  mov     eax, cs:dword_1400880C8
0x140041fdd  mov     ebx, 80070057h
0x140041fe2  cmp     eax, 2
0x140041fe5  jbe     loc_14004212A
0x140041feb  lea     rax, aPalSystemWin32_1; "PAL_System_Win32_TimerGetHWND"
0x140041ff2  mov     dword ptr [rbp+lpTlsValue], 4Fh ; 'O'
0x140041ff9  mov     [rbp+arg_10], rax
0x140041ffd  lea     rdx, qword_1400802E8
0x140042004  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14004200b  mov     [rbp+arg_18], rax
0x14004200f  lea     rax, aInvalidParamet; "Invalid parameter passed"
0x140042016  mov     [rbp+var_10], rax
0x14004201a  lea     rax, [rbp+arg_10]
0x14004201e  mov     [rsp+60h+var_20], rax
0x140042023  lea     rax, [rbp+lpTlsValue]
0x140042027  mov     [rsp+60h+var_28], rax
0x14004202c  lea     rax, [rbp+arg_18]
0x140042030  mov     [rsp+60h+var_30], rax
0x140042035  lea     rax, [rbp+arg_8]
0x140042039  mov     [rsp+60h+var_38], rax
0x14004203e  lea     rax, [rbp+var_10]
0x140042042  mov     [rsp+60h+var_40], rax
0x140042047  mov     [rbp+arg_8], ebx
0x14004204a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004204f  jmp     loc_14004212A
0x140042054  mov     ecx, cs:?g_PAL_SYS_timerWndIndex@@3KA; dwTlsIndex
0x14004205a  call    cs:__imp_TlsGetValue
0x140042060  mov     [rbp+lpTlsValue], rax
0x140042064  mov     rbx, rax
0x140042067  test    rax, rax
0x14004206a  jnz     loc_140042125
0x140042070  lea     rcx, [rbp+lpTlsValue]; HWND *
0x140042074  call    ?PAL_System_Win32_TimerCreateWindow@@YAJPEAPEAUHWND__@@@Z; PAL_System_Win32_TimerCreateWindow(HWND__ * *)
0x140042079  mov     ebx, eax
0x14004207b  test    eax, eax
0x14004207d  jns     short loc_1400420BE
0x14004207f  mov     ecx, cs:dword_1400880C8
0x140042085  cmp     ecx, 2
0x140042088  jbe     loc_14004212A
0x14004208e  lea     rax, aPalSystemWin32_1; "PAL_System_Win32_TimerGetHWND"
0x140042095  mov     dword ptr [rbp+lpTlsValue], 5Dh ; ']'
0x14004209c  mov     [rbp+arg_10], rax
0x1400420a0  lea     rdx, byte_14008032D
0x1400420a7  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400420ae  mov     [rbp+arg_18], rax
0x1400420b2  lea     rax, aFailedToCreate_21; "Failed to create timer window"
0x1400420b9  jmp     loc_140042016
0x1400420be  mov     rbx, [rbp+lpTlsValue]
0x1400420c2  mov     ecx, cs:?g_PAL_SYS_timerWndIndex@@3KA; dwTlsIndex
0x1400420c8  mov     rdx, rbx; lpTlsValue
0x1400420cb  call    cs:__imp_TlsSetValue
0x1400420d1  test    eax, eax
0x1400420d3  jnz     short loc_140042125
0x1400420d5  call    cs:__imp_GetLastError
0x1400420db  mov     ebx, eax
0x1400420dd  test    eax, eax
0x1400420df  jle     short loc_1400420EA
0x1400420e1  movzx   ebx, ax
0x1400420e4  or      ebx, 80070000h
0x1400420ea  mov     eax, cs:dword_1400880C8
0x1400420f0  cmp     eax, 2
0x1400420f3  jbe     short loc_14004212A
0x1400420f5  lea     rax, aPalSystemWin32_1; "PAL_System_Win32_TimerGetHWND"
0x1400420fc  mov     dword ptr [rbp+lpTlsValue], 64h ; 'd'
0x140042103  mov     [rbp+arg_10], rax
0x140042107  lea     rdx, dword_1400801D4
0x14004210e  lea     rax, aOnecoreTermsrv_9; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042115  mov     [rbp+arg_18], rax
0x140042119  lea     rax, aFailedToSetTim; "Failed to set timer window TLS value"
0x140042120  jmp     loc_140042016
0x140042125  mov     [rdi], rbx
0x140042128  xor     ebx, ebx
0x14004212a  mov     eax, ebx
0x14004212c  add     rsp, 60h
0x140042130  pop     rdi
0x140042131  pop     rbx
0x140042132  pop     rbp
0x140042133  retn
```
