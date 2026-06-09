# PAL_System_CondWait

- ea: `0x140042c6c`
- end: `0x140042f71`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140020240`

## callees

- `0x14000142c`
- `0x1400014d4`
- `0x140042c6c`

## import_xrefs

- `USER32!MsgWaitForMultipleObjectsEx` at `0x140042d5e`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140042d93`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140042d5e`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140042d93`
- `USER32!PeekMessageW` at `0x140042d24`
- `USER32!PeekMessageW` at `0x140042d24`
- `USER32!DispatchMessageW` at `0x140042d3f`
- `USER32!DispatchMessageW` at `0x140042d3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042cac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140042ca3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140042db6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140042ca3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140042db6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140042cfd`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140042cfd`

## string_xrefs

- `0x140042de9`: `Thread: 0x%x got a WM_QUIT`
- `0x140042e46`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042e8d`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x140042ea2`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

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
  tagMSG Msg; // [rsp+60h] [rbp-21h] BYREF
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
            if ( (unsigned int)dword_1400880C8 > 4 )
            {
              dwMilliseconds = (unsigned int)v27;
              v28 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)&byte_14008079F,
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
      if ( (unsigned int)dword_1400880C8 > 2 )
      {
        dwMilliseconds = 242;
        v25 = "Timeout processing window messages";
        v27 = "PAL_System_CondWait";
        v24 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v28) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_140080923,
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
        else if ( (unsigned int)dword_1400880C8 > 2 )
        {
          v27 = "PAL_System_CondWait";
          v24 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v28) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_1400809AD,
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
0x140042c6c  mov     [rsp-8+dwMilliseconds], r9d
0x140042c71  mov     [rsp-8+arg_10], r8
0x140042c76  push    rbp
0x140042c77  push    rbx
0x140042c78  push    rsi
0x140042c79  push    rdi
0x140042c7a  push    r12
0x140042c7c  push    r13
0x140042c7e  push    r15
0x140042c80  lea     rbp, [rsp-0Fh]
0x140042c85  sub     rsp, 90h
0x140042c8c  xorps   xmm0, xmm0
0x140042c8f  mov     r15d, r9d
0x140042c92  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x140042c96  mov     esi, edx
0x140042c98  mov     r13, rcx
0x140042c9b  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x140042c9f  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x140042ca3  call    cs:__imp_GetTickCount
0x140042ca9  mov     dword ptr [rbp+3Fh+arg_10], eax
0x140042cac  call    cs:__imp_GetCurrentThreadId
0x140042cb2  mov     dword ptr [rbp+3Fh+arg_0], eax
0x140042cb5  test    r13, r13
0x140042cb8  jz      loc_140042F58
0x140042cbe  mov     rdi, [rbp+3Fh+arg_30]
0x140042cc2  test    rdi, rdi
0x140042cc5  jz      loc_140042F58
0x140042ccb  test    esi, esi
0x140042ccd  jz      loc_140042F58
0x140042cd3  cmp     [rbp+3Fh+bWaitAll], 0
0x140042cd7  jz      short loc_140042CDF
0x140042cd9  mov     dword ptr [rdi], 0
0x140042cdf  cmp     [rbp+3Fh+arg_28], 0
0x140042ce3  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140042cea  mov     ebx, 80004005h
0x140042cef  jz      short loc_140042D0A
0x140042cf1  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x140042cf5  mov     r9d, r15d; dwMilliseconds
0x140042cf8  mov     rdx, r13; lpHandles
0x140042cfb  mov     ecx, esi; nCount
0x140042cfd  call    cs:__imp_WaitForMultipleObjects
0x140042d03  mov     ecx, eax
0x140042d05  jmp     loc_140042EA2
0x140042d0a  mov     r12d, r15d
0x140042d0d  xor     r15d, r15d
0x140042d10  xor     r9d, r9d; wMsgFilterMax
0x140042d13  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x140042d1b  xor     r8d, r8d; wMsgFilterMin
0x140042d1e  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x140042d22  xor     edx, edx; hWnd
0x140042d24  call    cs:__imp_PeekMessageW
0x140042d2a  test    eax, eax
0x140042d2c  jz      short loc_140042D4B
0x140042d2e  cmp     [rbp+3Fh+Msg.message], 12h
0x140042d32  jz      loc_140042DD1
0x140042d38  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x140042d3c  inc     r15d
0x140042d3f  call    cs:__imp_DispatchMessageW
0x140042d45  cmp     r15d, 64h ; 'd'
0x140042d49  jb      short loc_140042D10
0x140042d4b  xor     r9d, r9d; dwWakeMask
0x140042d4e  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x140042d56  xor     r8d, r8d; dwMilliseconds
0x140042d59  mov     rdx, r13; pHandles
0x140042d5c  mov     ecx, esi; nCount
0x140042d5e  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x140042d64  mov     ecx, eax
0x140042d66  lea     eax, [rsi-1]
0x140042d69  cmp     ecx, eax
0x140042d6b  jbe     loc_140042E9B
0x140042d71  mov     r15d, 0C0h
0x140042d77  cmp     ecx, r15d
0x140042d7a  jz      short loc_140042D0D
0x140042d7c  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x140042d80  mov     r9d, 1CFFh; dwWakeMask
0x140042d86  mov     rdx, r13; pHandles
0x140042d89  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x140042d91  mov     ecx, esi; nCount
0x140042d93  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x140042d99  mov     ecx, eax
0x140042d9b  cmp     eax, r15d
0x140042d9e  jz      loc_140042D0D
0x140042da4  cmp     eax, esi
0x140042da6  jnz     loc_140042E9B
0x140042dac  cmp     r12d, 0FFFFFFFFh
0x140042db0  jz      loc_140042D0D
0x140042db6  call    cs:__imp_GetTickCount
0x140042dbc  mov     ecx, eax
0x140042dbe  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x140042dc1  cmp     ecx, r12d
0x140042dc4  jnb     short loc_140042E15
0x140042dc6  sub     r12d, ecx
0x140042dc9  mov     dword ptr [rbp+3Fh+arg_10], eax
0x140042dcc  jmp     loc_140042D0D
0x140042dd1  mov     eax, cs:dword_1400880C8
0x140042dd7  cmp     eax, 4
0x140042dda  jbe     short loc_140042E0B
0x140042ddc  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x140042ddf  lea     rdx, byte_14008079F
0x140042de6  mov     [rbp+3Fh+dwMilliseconds], eax
0x140042de9  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x140042df0  mov     [rbp+3Fh+arg_10], rax
0x140042df4  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140042df8  mov     [rsp+0C0h+var_98], rax
0x140042dfd  lea     rax, [rbp+3Fh+arg_10]
0x140042e01  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x140042e06  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140042e0b  mov     ebx, 834500CCh
0x140042e10  jmp     loc_140042F5D
0x140042e15  mov     eax, cs:dword_1400880C8
0x140042e1b  cmp     eax, 2
0x140042e1e  jbe     short loc_140042E86
0x140042e20  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x140042e27  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x140042e2e  mov     [rbp+3Fh+var_68], rax
0x140042e32  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140042e39  lea     rax, [rbp+3Fh+arg_0]
0x140042e3d  mov     [rbp+3Fh+arg_0], r12
0x140042e41  mov     [rsp+0C0h+var_80], rax
0x140042e46  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042e4d  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140042e51  mov     [rbp+3Fh+var_70], r15
0x140042e55  mov     [rsp+0C0h+var_88], rax
0x140042e5a  lea     rdx, byte_140080923
0x140042e61  lea     rax, [rbp+3Fh+var_70]
0x140042e65  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x140042e68  mov     [rsp+0C0h+var_90], rax
0x140042e6d  lea     rax, [rbp+3Fh+arg_10]
0x140042e71  mov     [rsp+0C0h+var_98], rax
0x140042e76  lea     rax, [rbp+3Fh+var_68]
0x140042e7a  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x140042e7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042e84  jmp     short loc_140042E94
0x140042e86  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140042e8d  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042e94  mov     ecx, 102h
0x140042e99  jmp     short loc_140042EA9
0x140042e9b  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140042ea2  lea     r15, aOnecoreTermsrv_4; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140042ea9  lea     eax, [rsi-1]
0x140042eac  cmp     ecx, eax
0x140042eae  ja      short loc_140042EBF
0x140042eb0  cmp     [rbp+3Fh+bWaitAll], 0
0x140042eb4  jnz     short loc_140042EB8
0x140042eb6  mov     [rdi], ecx
0x140042eb8  xor     ebx, ebx
0x140042eba  jmp     loc_140042F5D
0x140042ebf  cmp     ecx, 80h
0x140042ec5  jb      short loc_140042EE0
0x140042ec7  lea     eax, [rsi+7Fh]
0x140042eca  cmp     ecx, eax
0x140042ecc  ja      short loc_140042EE0
0x140042ece  cmp     [rbp+3Fh+bWaitAll], 0
0x140042ed2  jnz     short loc_140042ED9
0x140042ed4  lea     eax, [rcx-80h]
0x140042ed7  mov     [rdi], eax
0x140042ed9  mov     ebx, 834500CAh
0x140042ede  jmp     short loc_140042F5D
0x140042ee0  cmp     ecx, 102h
0x140042ee6  jnz     short loc_140042EF5
0x140042ee8  mov     dword ptr [rdi], 0
0x140042eee  mov     ebx, 834500CBh
0x140042ef3  jmp     short loc_140042F5D
0x140042ef5  mov     eax, cs:dword_1400880C8
0x140042efb  cmp     eax, 2
0x140042efe  jbe     short loc_140042F5D
0x140042f00  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x140042f07  mov     [rbp+3Fh+arg_0], r12
0x140042f0b  mov     [rbp+3Fh+var_70], rax
0x140042f0f  lea     rdx, byte_1400809AD
0x140042f16  lea     rax, [rbp+3Fh+arg_0]
0x140042f1a  mov     [rbp+3Fh+dwMilliseconds], 127h
0x140042f21  mov     [rsp+0C0h+var_80], rax
0x140042f26  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140042f2a  mov     [rsp+0C0h+var_88], rax
0x140042f2f  lea     rax, [rbp+3Fh+var_68]
0x140042f33  mov     [rsp+0C0h+var_90], rax
0x140042f38  lea     rax, [rbp+3Fh+arg_10]
0x140042f3c  mov     [rsp+0C0h+var_98], rax
0x140042f41  lea     rax, [rbp+3Fh+var_70]
0x140042f45  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x140042f4a  mov     [rbp+3Fh+var_68], r15
0x140042f4e  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x140042f51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140042f56  jmp     short loc_140042F5D
0x140042f58  mov     ebx, 80070057h
0x140042f5d  mov     eax, ebx
0x140042f5f  add     rsp, 90h
0x140042f66  pop     r15
0x140042f68  pop     r13
0x140042f6a  pop     r12
0x140042f6c  pop     rdi
0x140042f6d  pop     rsi
0x140042f6e  pop     rbx
0x140042f6f  pop     rbp
0x140042f70  retn
```
