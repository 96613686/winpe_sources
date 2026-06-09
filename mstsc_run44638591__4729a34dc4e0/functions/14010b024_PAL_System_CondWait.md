# PAL_System_CondWait

- ea: `0x14010b024`
- end: `0x14010b329`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140104350`

## callees

- `0x140001940`
- `0x1400019e8`
- `0x14010b024`

## import_xrefs

- `USER32!MsgWaitForMultipleObjectsEx` at `0x14010b116`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x14010b14b`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x14010b116`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x14010b14b`
- `USER32!PeekMessageW` at `0x14010b0dc`
- `USER32!PeekMessageW` at `0x14010b0dc`
- `USER32!DispatchMessageW` at `0x14010b0f7`
- `USER32!DispatchMessageW` at `0x14010b0f7`
- `KERNEL32!WaitForMultipleObjects` at `0x14010b0b5`
- `KERNEL32!WaitForMultipleObjects` at `0x14010b0b5`
- `KERNEL32!GetTickCount` at `0x14010b05b`
- `KERNEL32!GetTickCount` at `0x14010b16e`
- `KERNEL32!GetTickCount` at `0x14010b05b`
- `KERNEL32!GetTickCount` at `0x14010b16e`
- `KERNEL32!GetCurrentThreadId` at `0x14010b064`
- `KERNEL32!GetCurrentThreadId` at `0x14010b064`

## string_xrefs

- `0x14010b1a1`: `Thread: 0x%x got a WM_QUIT`
- `0x14010b1fe`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x14010b245`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x14010b25a`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

## pseudocode

```c
__int64 __fastcall PAL_System_CondWait(
        HANDLE *pHandles,
        DWORD nCount,
        const char *a3,
        DWORD a4,
        BOOL bWaitAll,
        int a6,
        DWORD *a7)
{
  DWORD *v10; // rdi
  unsigned int v11; // ebx
  DWORD v12; // ecx
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // r12d
  unsigned int i; // r15d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  DWORD v20; // eax
  DWORD TickCount; // eax
  DWORD v22; // ecx
  const char *v24; // [rsp+50h] [rbp-31h] BYREF
  const char *v25; // [rsp+58h] [rbp-29h] BYREF
  struct tagMSG Msg; // [rsp+60h] [rbp-21h] BYREF
  const char *v27; // [rsp+D0h] [rbp+4Fh] BYREF
  const char *v28; // [rsp+E0h] [rbp+5Fh] BYREF
  DWORD dwMilliseconds; // [rsp+E8h] [rbp+67h] BYREF

  dwMilliseconds = a4;
  v28 = a3;
  memset(&Msg, 0, sizeof(Msg));
  LODWORD(v28) = GetTickCount();
  LODWORD(v27) = GetCurrentThreadId();
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
            if ( (unsigned int)dword_140152118 > 4 )
            {
              dwMilliseconds = (unsigned int)v27;
              v28 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)&word_1401460CE,
                v18,
                v19,
                (__int64)&v28,
                (__int64)&dwMilliseconds);
            }
            return (unsigned int)-2092629812;
          }
          DispatchMessageW(&Msg);
        }
        v12 = MsgWaitForMultipleObjectsEx(nCount, pHandles, 0, 0, 6u);
        if ( v12 <= nCount - 1 )
          goto LABEL_26;
        if ( v12 != 192 )
        {
          v20 = MsgWaitForMultipleObjectsEx(nCount, pHandles, dwMilliseconds, 0x1CFFu, 6u);
          v12 = v20;
          if ( v20 != 192 )
          {
            if ( v20 != nCount )
              goto LABEL_26;
            if ( v15 != -1 )
              break;
          }
        }
      }
      TickCount = GetTickCount();
      v22 = TickCount - (_DWORD)v28;
      if ( TickCount - (unsigned int)v28 < v15 )
      {
        v15 -= v22;
        LODWORD(v28) = TickCount;
        goto LABEL_9;
      }
      if ( (unsigned int)dword_140152118 > 2 )
      {
        dwMilliseconds = 242;
        v25 = "Timeout processing window messages";
        v27 = "PAL_System_CondWait";
        v24 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v28) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)&word_14014613E,
          v13,
          v14,
          (__int64)&v25,
          (__int64)&v28,
          (__int64)&v24,
          (__int64)&dwMilliseconds,
          (__int64)&v27);
      }
      v12 = 258;
    }
LABEL_26:
    if ( v12 > nCount - 1 )
    {
      if ( v12 < 0x80 || v12 > nCount + 127 )
      {
        if ( v12 == 258 )
        {
          *v10 = 0;
          return (unsigned int)-2092629813;
        }
        else if ( (unsigned int)dword_140152118 > 2 )
        {
          v27 = "PAL_System_CondWait";
          v24 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v28) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_1401460F9,
            v13,
            v14,
            (__int64)&v24,
            (__int64)&v28,
            (__int64)&v25,
            (__int64)&dwMilliseconds,
            (__int64)&v27);
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
0x14010b024  mov     [rsp-8+dwMilliseconds], r9d
0x14010b029  mov     [rsp-8+arg_10], r8
0x14010b02e  push    rbp
0x14010b02f  push    rbx
0x14010b030  push    rsi
0x14010b031  push    rdi
0x14010b032  push    r12
0x14010b034  push    r13
0x14010b036  push    r15
0x14010b038  lea     rbp, [rsp-0Fh]
0x14010b03d  sub     rsp, 90h
0x14010b044  xorps   xmm0, xmm0
0x14010b047  mov     r15d, r9d
0x14010b04a  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x14010b04e  mov     esi, edx
0x14010b050  mov     r13, rcx
0x14010b053  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x14010b057  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x14010b05b  call    cs:__imp_GetTickCount
0x14010b061  mov     dword ptr [rbp+3Fh+arg_10], eax
0x14010b064  call    cs:__imp_GetCurrentThreadId
0x14010b06a  mov     dword ptr [rbp+3Fh+arg_0], eax
0x14010b06d  test    r13, r13
0x14010b070  jz      loc_14010B310
0x14010b076  mov     rdi, [rbp+3Fh+arg_30]
0x14010b07a  test    rdi, rdi
0x14010b07d  jz      loc_14010B310
0x14010b083  test    esi, esi
0x14010b085  jz      loc_14010B310
0x14010b08b  cmp     [rbp+3Fh+bWaitAll], 0
0x14010b08f  jz      short loc_14010B097
0x14010b091  mov     dword ptr [rdi], 0
0x14010b097  cmp     [rbp+3Fh+arg_28], 0
0x14010b09b  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x14010b0a2  mov     ebx, 80004005h
0x14010b0a7  jz      short loc_14010B0C2
0x14010b0a9  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x14010b0ad  mov     r9d, r15d; dwMilliseconds
0x14010b0b0  mov     rdx, r13; lpHandles
0x14010b0b3  mov     ecx, esi; nCount
0x14010b0b5  call    cs:__imp_WaitForMultipleObjects
0x14010b0bb  mov     ecx, eax
0x14010b0bd  jmp     loc_14010B25A
0x14010b0c2  mov     r12d, r15d
0x14010b0c5  xor     r15d, r15d
0x14010b0c8  xor     r9d, r9d; wMsgFilterMax
0x14010b0cb  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x14010b0d3  xor     r8d, r8d; wMsgFilterMin
0x14010b0d6  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x14010b0da  xor     edx, edx; hWnd
0x14010b0dc  call    cs:__imp_PeekMessageW
0x14010b0e2  test    eax, eax
0x14010b0e4  jz      short loc_14010B103
0x14010b0e6  cmp     [rbp+3Fh+Msg.message], 12h
0x14010b0ea  jz      loc_14010B189
0x14010b0f0  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x14010b0f4  inc     r15d
0x14010b0f7  call    cs:__imp_DispatchMessageW
0x14010b0fd  cmp     r15d, 64h ; 'd'
0x14010b101  jb      short loc_14010B0C8
0x14010b103  xor     r9d, r9d; dwWakeMask
0x14010b106  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x14010b10e  xor     r8d, r8d; dwMilliseconds
0x14010b111  mov     rdx, r13; pHandles
0x14010b114  mov     ecx, esi; nCount
0x14010b116  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x14010b11c  mov     ecx, eax
0x14010b11e  lea     eax, [rsi-1]
0x14010b121  cmp     ecx, eax
0x14010b123  jbe     loc_14010B253
0x14010b129  mov     r15d, 0C0h
0x14010b12f  cmp     ecx, r15d
0x14010b132  jz      short loc_14010B0C5
0x14010b134  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x14010b138  mov     r9d, 1CFFh; dwWakeMask
0x14010b13e  mov     rdx, r13; pHandles
0x14010b141  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x14010b149  mov     ecx, esi; nCount
0x14010b14b  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x14010b151  mov     ecx, eax
0x14010b153  cmp     eax, r15d
0x14010b156  jz      loc_14010B0C5
0x14010b15c  cmp     eax, esi
0x14010b15e  jnz     loc_14010B253
0x14010b164  cmp     r12d, 0FFFFFFFFh
0x14010b168  jz      loc_14010B0C5
0x14010b16e  call    cs:__imp_GetTickCount
0x14010b174  mov     ecx, eax
0x14010b176  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x14010b179  cmp     ecx, r12d
0x14010b17c  jnb     short loc_14010B1CD
0x14010b17e  sub     r12d, ecx
0x14010b181  mov     dword ptr [rbp+3Fh+arg_10], eax
0x14010b184  jmp     loc_14010B0C5
0x14010b189  mov     eax, cs:dword_140152118
0x14010b18f  cmp     eax, 4
0x14010b192  jbe     short loc_14010B1C3
0x14010b194  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x14010b197  lea     rdx, word_1401460CE
0x14010b19e  mov     [rbp+3Fh+dwMilliseconds], eax
0x14010b1a1  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x14010b1a8  mov     [rbp+3Fh+arg_10], rax
0x14010b1ac  lea     rax, [rbp+3Fh+dwMilliseconds]
0x14010b1b0  mov     [rsp+0C0h+var_98], rax
0x14010b1b5  lea     rax, [rbp+3Fh+arg_10]
0x14010b1b9  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x14010b1be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14010b1c3  mov     ebx, 834500CCh
0x14010b1c8  jmp     loc_14010B315
0x14010b1cd  mov     eax, cs:dword_140152118
0x14010b1d3  cmp     eax, 2
0x14010b1d6  jbe     short loc_14010B23E
0x14010b1d8  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x14010b1df  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x14010b1e6  mov     [rbp+3Fh+var_68], rax
0x14010b1ea  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x14010b1f1  lea     rax, [rbp+3Fh+arg_0]
0x14010b1f5  mov     [rbp+3Fh+arg_0], r12
0x14010b1f9  mov     [rsp+0C0h+var_80], rax
0x14010b1fe  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010b205  lea     rax, [rbp+3Fh+dwMilliseconds]
0x14010b209  mov     [rbp+3Fh+var_70], r15
0x14010b20d  mov     [rsp+0C0h+var_88], rax
0x14010b212  lea     rdx, word_14014613E
0x14010b219  lea     rax, [rbp+3Fh+var_70]
0x14010b21d  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x14010b220  mov     [rsp+0C0h+var_90], rax
0x14010b225  lea     rax, [rbp+3Fh+arg_10]
0x14010b229  mov     [rsp+0C0h+var_98], rax
0x14010b22e  lea     rax, [rbp+3Fh+var_68]
0x14010b232  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x14010b237  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010b23c  jmp     short loc_14010B24C
0x14010b23e  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x14010b245  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010b24c  mov     ecx, 102h
0x14010b251  jmp     short loc_14010B261
0x14010b253  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x14010b25a  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x14010b261  lea     eax, [rsi-1]
0x14010b264  cmp     ecx, eax
0x14010b266  ja      short loc_14010B277
0x14010b268  cmp     [rbp+3Fh+bWaitAll], 0
0x14010b26c  jnz     short loc_14010B270
0x14010b26e  mov     [rdi], ecx
0x14010b270  xor     ebx, ebx
0x14010b272  jmp     loc_14010B315
0x14010b277  cmp     ecx, 80h
0x14010b27d  jb      short loc_14010B298
0x14010b27f  lea     eax, [rsi+7Fh]
0x14010b282  cmp     ecx, eax
0x14010b284  ja      short loc_14010B298
0x14010b286  cmp     [rbp+3Fh+bWaitAll], 0
0x14010b28a  jnz     short loc_14010B291
0x14010b28c  lea     eax, [rcx-80h]
0x14010b28f  mov     [rdi], eax
0x14010b291  mov     ebx, 834500CAh
0x14010b296  jmp     short loc_14010B315
0x14010b298  cmp     ecx, 102h
0x14010b29e  jnz     short loc_14010B2AD
0x14010b2a0  mov     dword ptr [rdi], 0
0x14010b2a6  mov     ebx, 834500CBh
0x14010b2ab  jmp     short loc_14010B315
0x14010b2ad  mov     eax, cs:dword_140152118
0x14010b2b3  cmp     eax, 2
0x14010b2b6  jbe     short loc_14010B315
0x14010b2b8  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x14010b2bf  mov     [rbp+3Fh+arg_0], r12
0x14010b2c3  mov     [rbp+3Fh+var_70], rax
0x14010b2c7  lea     rdx, byte_1401460F9
0x14010b2ce  lea     rax, [rbp+3Fh+arg_0]
0x14010b2d2  mov     [rbp+3Fh+dwMilliseconds], 127h
0x14010b2d9  mov     [rsp+0C0h+var_80], rax
0x14010b2de  lea     rax, [rbp+3Fh+dwMilliseconds]
0x14010b2e2  mov     [rsp+0C0h+var_88], rax
0x14010b2e7  lea     rax, [rbp+3Fh+var_68]
0x14010b2eb  mov     [rsp+0C0h+var_90], rax
0x14010b2f0  lea     rax, [rbp+3Fh+arg_10]
0x14010b2f4  mov     [rsp+0C0h+var_98], rax
0x14010b2f9  lea     rax, [rbp+3Fh+var_70]
0x14010b2fd  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x14010b302  mov     [rbp+3Fh+var_68], r15
0x14010b306  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x14010b309  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010b30e  jmp     short loc_14010B315
0x14010b310  mov     ebx, 80070057h
0x14010b315  mov     eax, ebx
0x14010b317  add     rsp, 90h
0x14010b31e  pop     r15
0x14010b320  pop     r13
0x14010b322  pop     r12
0x14010b324  pop     rdi
0x14010b325  pop     rsi
0x14010b326  pop     rbx
0x14010b327  pop     rbp
0x14010b328  retn
```
