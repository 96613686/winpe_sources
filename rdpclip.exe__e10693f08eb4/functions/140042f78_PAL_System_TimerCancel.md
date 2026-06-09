# PAL_System_TimerCancel

- ea: `0x140042f78`
- end: `0x1400431ca`
- name: `PAL_System_TimerCancel`
- size: `594`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140020874`
- `0x140020d00`

## callees

- `0x1400014d4`
- `0x140004b1c`
- `0x140005750`
- `0x140018404`
- `0x1400184d4`
- `0x14001866c`
- `0x1400412f4`
- `0x140042f78`

## import_xrefs

- `USER32!KillTimer` at `0x140043173`
- `USER32!KillTimer` at `0x140043173`

## string_xrefs

- `0x140042fb2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140043123`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1400431a6`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1400430dc`: `Failed to remove timer to timer list`

## pseudocode

```c
__int64 __fastcall PAL_System_TimerCancel(HWND *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // ebx
  int v6; // esi
  struct tagPAL_SYS_WIN32_SimpleList *v7; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  HWND v13; // rcx
  __int16 *v14; // rdx
  const char *v15; // rax
  _QWORD v17[3]; // [rsp+50h] [rbp-18h] BYREF
  int v18; // [rsp+90h] [rbp+28h] BYREF
  int v19; // [rsp+98h] [rbp+30h] BYREF
  const char *v20; // [rsp+A0h] [rbp+38h] BYREF
  const char *v21; // [rsp+A8h] [rbp+40h] BYREF

  if ( a1 )
  {
    v6 = PAL_System_AtomicCompareAndExchange(a1 + 2, 0);
    v5 = PAL_System_CritSecEnter(g_PAL_SYS_timerListLock);
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v5;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 14;
      v10 = "Failed to grab timer list lock";
      goto LABEL_10;
    }
    v5 = PAL_System_Win32_SimpleListRemove(v7, a1);
    PAL_System_CritSecLeave(g_PAL_SYS_timerListLock);
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return v5;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 15;
      v10 = "Failed to remove timer to timer list";
LABEL_10:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_176310856fb831edac28f3250bf8064f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v10,
        v5);
      return v5;
    }
    if ( v6 )
    {
      v13 = a1[3];
      if ( !v13 )
      {
        v5 = -2147467259;
        if ( (unsigned int)dword_1400880C8 <= 2 )
          return v5;
        v18 = 533;
        v20 = "PAL_System_TimerCancel";
        v14 = word_1400807CA;
        v21 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        v15 = "No timer was ever allocated";
LABEL_20:
        v17[0] = v15;
        v19 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v13,
          (_DWORD)v14,
          v11,
          v12,
          (__int64)v17,
          (__int64)&v19,
          (__int64)&v21,
          (__int64)&v18,
          (__int64)&v20);
        return v5;
      }
      if ( !KillTimer(v13, (UINT_PTR)a1) )
      {
        v5 = -2147467259;
        if ( (unsigned int)dword_1400880C8 <= 2 )
          return v5;
        v18 = 540;
        v20 = "PAL_System_TimerCancel";
        v14 = word_14008075A;
        v21 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        v15 = "Failed to kill timer";
        goto LABEL_20;
      }
    }
    return 0;
  }
  if ( (unsigned int)dword_1400880C8 > 2 )
  {
    v18 = 494;
    v20 = "PAL_System_TimerCancel";
    v19 = -2147467259;
    v21 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
    v17[0] = "NULL parameter passed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      0,
      (unsigned int)&dword_140080854,
      a3,
      a4,
      (__int64)v17,
      (__int64)&v19,
      (__int64)&v21,
      (__int64)&v18,
      (__int64)&v20);
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x140042f78  mov     r11, rsp
0x140042f7b  push    rbp
0x140042f7c  push    rbx
0x140042f7d  push    rsi
0x140042f7e  push    rdi
0x140042f7f  mov     rbp, rsp
0x140042f82  sub     rsp, 68h
0x140042f86  mov     rdi, rcx
0x140042f89  test    rcx, rcx
0x140042f8c  jnz     short loc_140043006
0x140042f8e  mov     eax, cs:dword_1400880C8
0x140042f94  cmp     eax, 2
0x140042f97  jbe     short loc_140042FFC
0x140042f99  lea     rax, aPalSystemTimer_1; "PAL_System_TimerCancel"
0x140042fa0  mov     [rbp+arg_0], 1EEh
0x140042fa7  mov     [rbp+arg_10], rax
0x140042fab  lea     rdx, dword_140080854
0x140042fb2  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042fb9  mov     [rbp+arg_8], 80004005h
0x140042fc0  mov     [rbp+arg_18], rax
0x140042fc4  lea     rax, aNullParameterP; "NULL parameter passed"
0x140042fcb  mov     [rbp+var_18], rax
0x140042fcf  lea     rax, [rbp+arg_10]
0x140042fd3  mov     [r11-48h], rax
0x140042fd7  lea     rax, [rbp+arg_0]
0x140042fdb  mov     [r11-50h], rax
0x140042fdf  lea     rax, [rbp+arg_18]
0x140042fe3  mov     [r11-58h], rax
0x140042fe7  lea     rax, [rbp+arg_8]
0x140042feb  mov     [r11-60h], rax
0x140042fef  lea     rax, [rbp+var_18]
0x140042ff3  mov     [r11-68h], rax
0x140042ff7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042ffc  mov     ebx, 80070057h
0x140043001  jmp     loc_1400431BF
0x140043006  xor     edx, edx
0x140043008  add     rcx, 10h
0x14004300c  lea     r8d, [rdx+1]
0x140043010  call    PAL_System_AtomicCompareAndExchange
0x140043015  mov     rcx, cs:?g_PAL_SYS_timerListLock@@3PEAXEA; void * g_PAL_SYS_timerListLock
0x14004301c  mov     esi, eax
0x14004301e  call    PAL_System_CritSecEnter
0x140043023  mov     ebx, eax
0x140043025  test    eax, eax
0x140043027  jns     short loc_14004308D
0x140043029  mov     rcx, cs:WPP_GLOBAL_Control
0x140043030  lea     rdx, WPP_GLOBAL_Control
0x140043037  cmp     rcx, rdx
0x14004303a  jz      loc_1400431BF
0x140043040  test    byte ptr [rcx+1Ch], 8
0x140043044  jz      loc_1400431BF
0x14004304a  cmp     byte ptr [rcx+19h], 2
0x14004304e  jb      loc_1400431BF
0x140043054  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140043059  mov     edx, 0Eh
0x14004305e  lea     rcx, aFailedToGrabTi; "Failed to grab timer list lock"
0x140043065  mov     dword ptr [rsp+68h+var_40], ebx
0x140043069  lea     r8, WPP_176310856fb831edac28f3250bf8064f_Traceguids
0x140043070  mov     [rsp+68h+var_48], rcx
0x140043075  mov     r9d, eax
0x140043078  mov     rcx, cs:WPP_GLOBAL_Control
0x14004307f  mov     rcx, [rcx+10h]
0x140043083  call    WPP_SF_DsD
0x140043088  jmp     loc_1400431BF
0x14004308d  mov     rdx, rdi; void *
0x140043090  call    ?PAL_System_Win32_SimpleListRemove@@YAJPEAUtagPAL_SYS_WIN32_SimpleList@@PEAX@Z; PAL_System_Win32_SimpleListRemove(tagPAL_SYS_WIN32_SimpleList *,void *)
0x140043095  mov     rcx, cs:?g_PAL_SYS_timerListLock@@3PEAXEA; void * g_PAL_SYS_timerListLock
0x14004309c  mov     ebx, eax
0x14004309e  call    PAL_System_CritSecLeave
0x1400430a3  test    ebx, ebx
0x1400430a5  jns     short loc_1400430E5
0x1400430a7  mov     rax, cs:WPP_GLOBAL_Control
0x1400430ae  lea     rdx, WPP_GLOBAL_Control
0x1400430b5  cmp     rax, rdx
0x1400430b8  jz      loc_1400431BF
0x1400430be  test    byte ptr [rax+1Ch], 8
0x1400430c2  jz      loc_1400431BF
0x1400430c8  cmp     byte ptr [rax+19h], 2
0x1400430cc  jb      loc_1400431BF
0x1400430d2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400430d7  mov     edx, 0Fh
0x1400430dc  lea     rcx, aFailedToRemove_7; "Failed to remove timer to timer list"
0x1400430e3  jmp     short loc_140043065
0x1400430e5  test    esi, esi
0x1400430e7  jz      loc_1400431BD
0x1400430ed  mov     rcx, [rdi+18h]; hWnd
0x1400430f1  test    rcx, rcx
0x1400430f4  jnz     short loc_140043170
0x1400430f6  mov     eax, cs:dword_1400880C8
0x1400430fc  mov     ebx, 80004005h
0x140043101  cmp     eax, 2
0x140043104  jbe     loc_1400431BF
0x14004310a  lea     rax, aPalSystemTimer_1; "PAL_System_TimerCancel"
0x140043111  mov     [rbp+arg_0], 215h
0x140043118  mov     [rbp+arg_10], rax
0x14004311c  lea     rdx, word_1400807CA
0x140043123  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14004312a  mov     [rbp+arg_18], rax
0x14004312e  lea     rax, aNoTimerWasEver; "No timer was ever allocated"
0x140043135  mov     [rbp+var_18], rax
0x140043139  lea     rax, [rbp+arg_10]
0x14004313d  mov     [rsp+68h+var_28], rax
0x140043142  lea     rax, [rbp+arg_0]
0x140043146  mov     [rsp+68h+var_30], rax
0x14004314b  lea     rax, [rbp+arg_18]
0x14004314f  mov     [rsp+68h+var_38], rax
0x140043154  lea     rax, [rbp+arg_8]
0x140043158  mov     [rsp+68h+var_40], rax
0x14004315d  lea     rax, [rbp+var_18]
0x140043161  mov     [rsp+68h+var_48], rax
0x140043166  mov     [rbp+arg_8], ebx
0x140043169  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14004316e  jmp     short loc_1400431BF
0x140043170  mov     rdx, rdi; uIDEvent
0x140043173  call    cs:__imp_KillTimer
0x140043179  test    eax, eax
0x14004317b  jnz     short loc_1400431BD
0x14004317d  mov     eax, cs:dword_1400880C8
0x140043183  mov     ebx, 80004005h
0x140043188  cmp     eax, 2
0x14004318b  jbe     short loc_1400431BF
0x14004318d  lea     rax, aPalSystemTimer_1; "PAL_System_TimerCancel"
0x140043194  mov     [rbp+arg_0], 21Ch
0x14004319b  mov     [rbp+arg_10], rax
0x14004319f  lea     rdx, word_14008075A
0x1400431a6  lea     rax, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1400431ad  mov     [rbp+arg_18], rax
0x1400431b1  lea     rax, aFailedToKillTi; "Failed to kill timer"
0x1400431b8  jmp     loc_140043135
0x1400431bd  xor     ebx, ebx
0x1400431bf  mov     eax, ebx
0x1400431c1  add     rsp, 68h
0x1400431c5  pop     rdi
0x1400431c6  pop     rsi
0x1400431c7  pop     rbx
0x1400431c8  pop     rbp
0x1400431c9  retn
```
