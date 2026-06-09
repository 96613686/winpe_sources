# PAL_System_CondWait

- ea: `0x18002b1ac`
- end: `0x18002b4b1`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028f50`

## callees

- `0x180001564`
- `0x18000160c`
- `0x18002b1ac`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b1e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b2f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b1e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002b2f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1ec`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b23d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002b23d`
- `USER32!PeekMessageW` at `0x18002b264`
- `USER32!PeekMessageW` at `0x18002b264`
- `USER32!DispatchMessageW` at `0x18002b27f`
- `USER32!DispatchMessageW` at `0x18002b27f`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18002b29e`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18002b2d3`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18002b29e`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x18002b2d3`

## string_xrefs

- `0x18002b329`: `Thread: 0x%x got a WM_QUIT`
- `0x18002b386`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002b3cd`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x18002b3e2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CondWait(
        HANDLE *pHandles,
        DWORD nCount,
        const unsigned __int16 *a3,
        DWORD a4,
        BOOL bWaitAll,
        int a6,
        _DWORD *a7)
{
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // r12d
  unsigned int i; // r15d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD TickCount; // eax
  __int64 v23; // rcx
  const char *v25; // [rsp+50h] [rbp-31h] BYREF
  const char *v26; // [rsp+58h] [rbp-29h] BYREF
  tagMSG Msg; // [rsp+60h] [rbp-21h] BYREF
  const char *v28; // [rsp+D0h] [rbp+4Fh] BYREF
  const char *v29; // [rsp+E0h] [rbp+5Fh] BYREF
  DWORD dwMilliseconds; // [rsp+E8h] [rbp+67h] BYREF

  dwMilliseconds = a4;
  v29 = (const char *)a3;
  memset(&Msg, 0, sizeof(Msg));
  LODWORD(v29) = GetTickCount();
  LODWORD(v28) = GetCurrentThreadId();
  if ( pHandles && (v10 = a7) != 0 && nCount )
  {
    if ( bWaitAll )
      *a7 = 0;
    v11 = -2147467259;
    if ( a6 )
    {
      v12 = WaitForMultipleObjects(nCount, pHandles, bWaitAll, a4);
    }
    else
    {
      v15 = a4;
      while ( 1 )
      {
LABEL_9:
        for ( i = 0; i < 0x64; ++i )
        {
          if ( !PeekMessageW(&Msg, 0, 0, 0, 1u) )
            break;
          if ( Msg.message == 18 )
          {
            if ( (unsigned int)dword_180044008 > 4 )
            {
              dwMilliseconds = (unsigned int)v28;
              v29 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (__int64)qword_180040420,
                v18,
                v19,
                (const unsigned __int16 **)&v29,
                (__int64)&dwMilliseconds);
            }
            return (unsigned int)-2092629812;
          }
          DispatchMessageW(&Msg);
        }
        v20 = MsgWaitForMultipleObjectsEx(nCount, pHandles, 0, 0, 6u);
        v12 = v20;
        if ( v20 <= nCount - 1 )
          goto LABEL_26;
        if ( v20 != 192 )
        {
          v21 = MsgWaitForMultipleObjectsEx(nCount, pHandles, dwMilliseconds, 0x1CFFu, 6u);
          v12 = v21;
          if ( v21 != 192 )
          {
            if ( v21 != nCount )
              goto LABEL_26;
            if ( v15 != -1 )
              break;
          }
        }
      }
      TickCount = GetTickCount();
      v23 = TickCount - (unsigned int)v29;
      if ( (unsigned int)v23 < v15 )
      {
        v15 -= v23;
        LODWORD(v29) = TickCount;
        goto LABEL_9;
      }
      if ( (unsigned int)dword_180044008 > 2 )
      {
        dwMilliseconds = 242;
        v26 = "Timeout processing window messages";
        v28 = "PAL_System_CondWait";
        v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v29) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v23,
          (__int64)qword_180040490,
          v13,
          v14,
          (const unsigned __int16 **)&v26,
          (__int64)&v29,
          (const unsigned __int16 **)&v25,
          (__int64)&dwMilliseconds,
          (const unsigned __int16 **)&v28);
      }
      v12 = 258;
    }
LABEL_26:
    if ( (unsigned int)v12 > nCount - 1 )
    {
      if ( (unsigned int)v12 < 0x80 || (unsigned int)v12 > nCount + 127 )
      {
        if ( (_DWORD)v12 == 258 )
        {
          *v10 = 0;
          return (unsigned int)-2092629813;
        }
        else if ( (unsigned int)dword_180044008 > 2 )
        {
          v28 = "PAL_System_CondWait";
          v25 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v26 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v29) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (__int64)word_18004051A,
            v13,
            v14,
            (const unsigned __int16 **)&v25,
            (__int64)&v29,
            (const unsigned __int16 **)&v26,
            (__int64)&dwMilliseconds,
            (const unsigned __int16 **)&v28);
        }
      }
      else
      {
        if ( !bWaitAll )
          *v10 = v12 - 128;
        return (unsigned int)-2092629814;
      }
    }
    else
    {
      if ( !bWaitAll )
        *v10 = v12;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x18002b1ac  mov     [rsp-8+dwMilliseconds], r9d
0x18002b1b1  mov     [rsp-8+arg_10], r8
0x18002b1b6  push    rbp
0x18002b1b7  push    rbx
0x18002b1b8  push    rsi
0x18002b1b9  push    rdi
0x18002b1ba  push    r12
0x18002b1bc  push    r13
0x18002b1be  push    r15
0x18002b1c0  lea     rbp, [rsp-0Fh]
0x18002b1c5  sub     rsp, 90h
0x18002b1cc  xorps   xmm0, xmm0
0x18002b1cf  mov     r15d, r9d
0x18002b1d2  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x18002b1d6  mov     esi, edx
0x18002b1d8  mov     r13, rcx
0x18002b1db  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x18002b1df  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x18002b1e3  call    cs:__imp_GetTickCount
0x18002b1e9  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18002b1ec  call    cs:__imp_GetCurrentThreadId
0x18002b1f2  mov     dword ptr [rbp+3Fh+arg_0], eax
0x18002b1f5  test    r13, r13
0x18002b1f8  jz      loc_18002B498
0x18002b1fe  mov     rdi, [rbp+3Fh+arg_30]
0x18002b202  test    rdi, rdi
0x18002b205  jz      loc_18002B498
0x18002b20b  test    esi, esi
0x18002b20d  jz      loc_18002B498
0x18002b213  cmp     [rbp+3Fh+bWaitAll], 0
0x18002b217  jz      short loc_18002B21F
0x18002b219  mov     dword ptr [rdi], 0
0x18002b21f  cmp     [rbp+3Fh+arg_28], 0
0x18002b223  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18002b22a  mov     ebx, 80004005h
0x18002b22f  jz      short loc_18002B24A
0x18002b231  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x18002b235  mov     r9d, r15d; dwMilliseconds
0x18002b238  mov     rdx, r13; lpHandles
0x18002b23b  mov     ecx, esi; nCount
0x18002b23d  call    cs:__imp_WaitForMultipleObjects
0x18002b243  mov     ecx, eax
0x18002b245  jmp     loc_18002B3E2
0x18002b24a  mov     r12d, r15d
0x18002b24d  xor     r15d, r15d
0x18002b250  xor     r9d, r9d; wMsgFilterMax
0x18002b253  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x18002b25b  xor     r8d, r8d; wMsgFilterMin
0x18002b25e  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18002b262  xor     edx, edx; hWnd
0x18002b264  call    cs:__imp_PeekMessageW
0x18002b26a  test    eax, eax
0x18002b26c  jz      short loc_18002B28B
0x18002b26e  cmp     [rbp+3Fh+Msg.message], 12h
0x18002b272  jz      loc_18002B311
0x18002b278  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18002b27c  inc     r15d
0x18002b27f  call    cs:__imp_DispatchMessageW
0x18002b285  cmp     r15d, 64h ; 'd'
0x18002b289  jb      short loc_18002B250
0x18002b28b  xor     r9d, r9d; dwWakeMask
0x18002b28e  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x18002b296  xor     r8d, r8d; dwMilliseconds
0x18002b299  mov     rdx, r13; pHandles
0x18002b29c  mov     ecx, esi; nCount
0x18002b29e  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18002b2a4  mov     ecx, eax
0x18002b2a6  lea     eax, [rsi-1]
0x18002b2a9  cmp     ecx, eax
0x18002b2ab  jbe     loc_18002B3DB
0x18002b2b1  mov     r15d, 0C0h
0x18002b2b7  cmp     ecx, r15d
0x18002b2ba  jz      short loc_18002B24D
0x18002b2bc  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x18002b2c0  mov     r9d, 1CFFh; dwWakeMask
0x18002b2c6  mov     rdx, r13; pHandles
0x18002b2c9  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x18002b2d1  mov     ecx, esi; nCount
0x18002b2d3  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x18002b2d9  mov     ecx, eax
0x18002b2db  cmp     eax, r15d
0x18002b2de  jz      loc_18002B24D
0x18002b2e4  cmp     eax, esi
0x18002b2e6  jnz     loc_18002B3DB
0x18002b2ec  cmp     r12d, 0FFFFFFFFh
0x18002b2f0  jz      loc_18002B24D
0x18002b2f6  call    cs:__imp_GetTickCount
0x18002b2fc  mov     ecx, eax
0x18002b2fe  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x18002b301  cmp     ecx, r12d
0x18002b304  jnb     short loc_18002B355
0x18002b306  sub     r12d, ecx
0x18002b309  mov     dword ptr [rbp+3Fh+arg_10], eax
0x18002b30c  jmp     loc_18002B24D
0x18002b311  mov     eax, cs:dword_180044008
0x18002b317  cmp     eax, 4
0x18002b31a  jbe     short loc_18002B34B
0x18002b31c  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x18002b31f  lea     rdx, qword_180040420
0x18002b326  mov     [rbp+3Fh+dwMilliseconds], eax
0x18002b329  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x18002b330  mov     [rbp+3Fh+arg_10], rax
0x18002b334  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18002b338  mov     [rsp+0C0h+var_98], rax
0x18002b33d  lea     rax, [rbp+3Fh+arg_10]
0x18002b341  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18002b346  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002b34b  mov     ebx, 834500CCh
0x18002b350  jmp     loc_18002B49D
0x18002b355  mov     eax, cs:dword_180044008
0x18002b35b  cmp     eax, 2
0x18002b35e  jbe     short loc_18002B3C6
0x18002b360  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x18002b367  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x18002b36e  mov     [rbp+3Fh+var_68], rax
0x18002b372  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18002b379  lea     rax, [rbp+3Fh+arg_0]
0x18002b37d  mov     [rbp+3Fh+arg_0], r12
0x18002b381  mov     [rsp+0C0h+var_80], rax
0x18002b386  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b38d  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18002b391  mov     [rbp+3Fh+var_70], r15
0x18002b395  mov     [rsp+0C0h+var_88], rax
0x18002b39a  lea     rdx, qword_180040490
0x18002b3a1  lea     rax, [rbp+3Fh+var_70]
0x18002b3a5  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x18002b3a8  mov     [rsp+0C0h+var_90], rax
0x18002b3ad  lea     rax, [rbp+3Fh+arg_10]
0x18002b3b1  mov     [rsp+0C0h+var_98], rax
0x18002b3b6  lea     rax, [rbp+3Fh+var_68]
0x18002b3ba  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18002b3bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b3c4  jmp     short loc_18002B3D4
0x18002b3c6  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18002b3cd  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b3d4  mov     ecx, 102h
0x18002b3d9  jmp     short loc_18002B3E9
0x18002b3db  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x18002b3e2  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002b3e9  lea     eax, [rsi-1]
0x18002b3ec  cmp     ecx, eax
0x18002b3ee  ja      short loc_18002B3FF
0x18002b3f0  cmp     [rbp+3Fh+bWaitAll], 0
0x18002b3f4  jnz     short loc_18002B3F8
0x18002b3f6  mov     [rdi], ecx
0x18002b3f8  xor     ebx, ebx
0x18002b3fa  jmp     loc_18002B49D
0x18002b3ff  cmp     ecx, 80h
0x18002b405  jb      short loc_18002B420
0x18002b407  lea     eax, [rsi+7Fh]
0x18002b40a  cmp     ecx, eax
0x18002b40c  ja      short loc_18002B420
0x18002b40e  cmp     [rbp+3Fh+bWaitAll], 0
0x18002b412  jnz     short loc_18002B419
0x18002b414  lea     eax, [rcx-80h]
0x18002b417  mov     [rdi], eax
0x18002b419  mov     ebx, 834500CAh
0x18002b41e  jmp     short loc_18002B49D
0x18002b420  cmp     ecx, 102h
0x18002b426  jnz     short loc_18002B435
0x18002b428  mov     dword ptr [rdi], 0
0x18002b42e  mov     ebx, 834500CBh
0x18002b433  jmp     short loc_18002B49D
0x18002b435  mov     eax, cs:dword_180044008
0x18002b43b  cmp     eax, 2
0x18002b43e  jbe     short loc_18002B49D
0x18002b440  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x18002b447  mov     [rbp+3Fh+arg_0], r12
0x18002b44b  mov     [rbp+3Fh+var_70], rax
0x18002b44f  lea     rdx, word_18004051A
0x18002b456  lea     rax, [rbp+3Fh+arg_0]
0x18002b45a  mov     [rbp+3Fh+dwMilliseconds], 127h
0x18002b461  mov     [rsp+0C0h+var_80], rax
0x18002b466  lea     rax, [rbp+3Fh+dwMilliseconds]
0x18002b46a  mov     [rsp+0C0h+var_88], rax
0x18002b46f  lea     rax, [rbp+3Fh+var_68]
0x18002b473  mov     [rsp+0C0h+var_90], rax
0x18002b478  lea     rax, [rbp+3Fh+arg_10]
0x18002b47c  mov     [rsp+0C0h+var_98], rax
0x18002b481  lea     rax, [rbp+3Fh+var_70]
0x18002b485  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x18002b48a  mov     [rbp+3Fh+var_68], r15
0x18002b48e  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x18002b491  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002b496  jmp     short loc_18002B49D
0x18002b498  mov     ebx, 80070057h
0x18002b49d  mov     eax, ebx
0x18002b49f  add     rsp, 90h
0x18002b4a6  pop     r15
0x18002b4a8  pop     r13
0x18002b4aa  pop     r12
0x18002b4ac  pop     rdi
0x18002b4ad  pop     rsi
0x18002b4ae  pop     rbx
0x18002b4af  pop     rbp
0x18002b4b0  retn
```
