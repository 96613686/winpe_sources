# PAL_System_CondWait

- ea: `0x140108eb4`
- end: `0x1401091b9`
- name: `PAL_System_CondWait`
- size: `773`
- prototype: `__int64 __usercall@<rax>(HANDLE *pHandles@<rcx>, DWORD nCount@<edx>, BOOL bWaitAll, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401021e0`

## callees

- `0x140001940`
- `0x1400019e8`
- `0x140108eb4`

## import_xrefs

- `USER32!MsgWaitForMultipleObjectsEx` at `0x140108fa6`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140108fdb`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140108fa6`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140108fdb`
- `USER32!PeekMessageW` at `0x140108f6c`
- `USER32!PeekMessageW` at `0x140108f6c`
- `USER32!DispatchMessageW` at `0x140108f87`
- `USER32!DispatchMessageW` at `0x140108f87`
- `KERNEL32!WaitForMultipleObjects` at `0x140108f45`
- `KERNEL32!WaitForMultipleObjects` at `0x140108f45`
- `KERNEL32!GetTickCount` at `0x140108eeb`
- `KERNEL32!GetTickCount` at `0x140108ffe`
- `KERNEL32!GetTickCount` at `0x140108eeb`
- `KERNEL32!GetTickCount` at `0x140108ffe`
- `KERNEL32!GetCurrentThreadId` at `0x140108ef4`
- `KERNEL32!GetCurrentThreadId` at `0x140108ef4`

## string_xrefs

- `0x140109031`: `Thread: 0x%x got a WM_QUIT`
- `0x14010908e`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1401090d5`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`
- `0x1401090ea`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32.cpp`

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
            if ( (unsigned int)dword_140150118 > 4 )
            {
              dwMilliseconds = (unsigned int)v27;
              v28 = "Thread: 0x%x got a WM_QUIT";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v17,
                (unsigned int)byte_140143F51,
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
      if ( (unsigned int)dword_140150118 > 2 )
      {
        dwMilliseconds = 242;
        v25 = "Timeout processing window messages";
        v27 = "PAL_System_CondWait";
        v24 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
        LODWORD(v28) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_140143FC1,
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
        else if ( (unsigned int)dword_140150118 > 2 )
        {
          v27 = "PAL_System_CondWait";
          v24 = "Wait Failed with unknown error";
          dwMilliseconds = 295;
          v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\win32\\system\\tssystempalwin32.cpp";
          LODWORD(v28) = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v12,
            (unsigned int)byte_14014404B,
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
0x140108eb4  mov     [rsp-8+dwMilliseconds], r9d
0x140108eb9  mov     [rsp-8+arg_10], r8
0x140108ebe  push    rbp
0x140108ebf  push    rbx
0x140108ec0  push    rsi
0x140108ec1  push    rdi
0x140108ec2  push    r12
0x140108ec4  push    r13
0x140108ec6  push    r15
0x140108ec8  lea     rbp, [rsp-0Fh]
0x140108ecd  sub     rsp, 90h
0x140108ed4  xorps   xmm0, xmm0
0x140108ed7  mov     r15d, r9d
0x140108eda  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x140108ede  mov     esi, edx
0x140108ee0  mov     r13, rcx
0x140108ee3  movups  xmmword ptr [rbp+3Fh+Msg.wParam], xmm0
0x140108ee7  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x140108eeb  call    cs:__imp_GetTickCount
0x140108ef1  mov     dword ptr [rbp+3Fh+arg_10], eax
0x140108ef4  call    cs:__imp_GetCurrentThreadId
0x140108efa  mov     dword ptr [rbp+3Fh+arg_0], eax
0x140108efd  test    r13, r13
0x140108f00  jz      loc_1401091A0
0x140108f06  mov     rdi, [rbp+3Fh+arg_30]
0x140108f0a  test    rdi, rdi
0x140108f0d  jz      loc_1401091A0
0x140108f13  test    esi, esi
0x140108f15  jz      loc_1401091A0
0x140108f1b  cmp     [rbp+3Fh+bWaitAll], 0
0x140108f1f  jz      short loc_140108F27
0x140108f21  mov     dword ptr [rdi], 0
0x140108f27  cmp     [rbp+3Fh+arg_28], 0
0x140108f2b  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140108f32  mov     ebx, 80004005h
0x140108f37  jz      short loc_140108F52
0x140108f39  mov     r8d, [rbp+3Fh+bWaitAll]; bWaitAll
0x140108f3d  mov     r9d, r15d; dwMilliseconds
0x140108f40  mov     rdx, r13; lpHandles
0x140108f43  mov     ecx, esi; nCount
0x140108f45  call    cs:__imp_WaitForMultipleObjects
0x140108f4b  mov     ecx, eax
0x140108f4d  jmp     loc_1401090EA
0x140108f52  mov     r12d, r15d
0x140108f55  xor     r15d, r15d
0x140108f58  xor     r9d, r9d; wMsgFilterMax
0x140108f5b  mov     [rsp+0C0h+wRemoveMsg], 1; wRemoveMsg
0x140108f63  xor     r8d, r8d; wMsgFilterMin
0x140108f66  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x140108f6a  xor     edx, edx; hWnd
0x140108f6c  call    cs:__imp_PeekMessageW
0x140108f72  test    eax, eax
0x140108f74  jz      short loc_140108F93
0x140108f76  cmp     [rbp+3Fh+Msg.message], 12h
0x140108f7a  jz      loc_140109019
0x140108f80  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x140108f84  inc     r15d
0x140108f87  call    cs:__imp_DispatchMessageW
0x140108f8d  cmp     r15d, 64h ; 'd'
0x140108f91  jb      short loc_140108F58
0x140108f93  xor     r9d, r9d; dwWakeMask
0x140108f96  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x140108f9e  xor     r8d, r8d; dwMilliseconds
0x140108fa1  mov     rdx, r13; pHandles
0x140108fa4  mov     ecx, esi; nCount
0x140108fa6  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x140108fac  mov     ecx, eax
0x140108fae  lea     eax, [rsi-1]
0x140108fb1  cmp     ecx, eax
0x140108fb3  jbe     loc_1401090E3
0x140108fb9  mov     r15d, 0C0h
0x140108fbf  cmp     ecx, r15d
0x140108fc2  jz      short loc_140108F55
0x140108fc4  mov     r8d, [rbp+3Fh+dwMilliseconds]; dwMilliseconds
0x140108fc8  mov     r9d, 1CFFh; dwWakeMask
0x140108fce  mov     rdx, r13; pHandles
0x140108fd1  mov     [rsp+0C0h+wRemoveMsg], 6; dwFlags
0x140108fd9  mov     ecx, esi; nCount
0x140108fdb  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x140108fe1  mov     ecx, eax
0x140108fe3  cmp     eax, r15d
0x140108fe6  jz      loc_140108F55
0x140108fec  cmp     eax, esi
0x140108fee  jnz     loc_1401090E3
0x140108ff4  cmp     r12d, 0FFFFFFFFh
0x140108ff8  jz      loc_140108F55
0x140108ffe  call    cs:__imp_GetTickCount
0x140109004  mov     ecx, eax
0x140109006  sub     ecx, dword ptr [rbp+3Fh+arg_10]
0x140109009  cmp     ecx, r12d
0x14010900c  jnb     short loc_14010905D
0x14010900e  sub     r12d, ecx
0x140109011  mov     dword ptr [rbp+3Fh+arg_10], eax
0x140109014  jmp     loc_140108F55
0x140109019  mov     eax, cs:dword_140150118
0x14010901f  cmp     eax, 4
0x140109022  jbe     short loc_140109053
0x140109024  mov     eax, dword ptr [rbp+3Fh+arg_0]
0x140109027  lea     rdx, byte_140143F51
0x14010902e  mov     [rbp+3Fh+dwMilliseconds], eax
0x140109031  lea     rax, aThread0xXGotAW; "Thread: 0x%x got a WM_QUIT"
0x140109038  mov     [rbp+3Fh+arg_10], rax
0x14010903c  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140109040  mov     [rsp+0C0h+var_98], rax
0x140109045  lea     rax, [rbp+3Fh+arg_10]
0x140109049  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x14010904e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140109053  mov     ebx, 834500CCh
0x140109058  jmp     loc_1401091A5
0x14010905d  mov     eax, cs:dword_140150118
0x140109063  cmp     eax, 2
0x140109066  jbe     short loc_1401090CE
0x140109068  lea     rax, aTimeoutProcess; "Timeout processing window messages"
0x14010906f  mov     [rbp+3Fh+dwMilliseconds], 0F2h
0x140109076  mov     [rbp+3Fh+var_68], rax
0x14010907a  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x140109081  lea     rax, [rbp+3Fh+arg_0]
0x140109085  mov     [rbp+3Fh+arg_0], r12
0x140109089  mov     [rsp+0C0h+var_80], rax
0x14010908e  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x140109095  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140109099  mov     [rbp+3Fh+var_70], r15
0x14010909d  mov     [rsp+0C0h+var_88], rax
0x1401090a2  lea     rdx, byte_140143FC1
0x1401090a9  lea     rax, [rbp+3Fh+var_70]
0x1401090ad  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x1401090b0  mov     [rsp+0C0h+var_90], rax
0x1401090b5  lea     rax, [rbp+3Fh+arg_10]
0x1401090b9  mov     [rsp+0C0h+var_98], rax
0x1401090be  lea     rax, [rbp+3Fh+var_68]
0x1401090c2  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x1401090c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1401090cc  jmp     short loc_1401090DC
0x1401090ce  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x1401090d5  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1401090dc  mov     ecx, 102h
0x1401090e1  jmp     short loc_1401090F1
0x1401090e3  lea     r12, aPalSystemCondw; "PAL_System_CondWait"
0x1401090ea  lea     r15, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1401090f1  lea     eax, [rsi-1]
0x1401090f4  cmp     ecx, eax
0x1401090f6  ja      short loc_140109107
0x1401090f8  cmp     [rbp+3Fh+bWaitAll], 0
0x1401090fc  jnz     short loc_140109100
0x1401090fe  mov     [rdi], ecx
0x140109100  xor     ebx, ebx
0x140109102  jmp     loc_1401091A5
0x140109107  cmp     ecx, 80h
0x14010910d  jb      short loc_140109128
0x14010910f  lea     eax, [rsi+7Fh]
0x140109112  cmp     ecx, eax
0x140109114  ja      short loc_140109128
0x140109116  cmp     [rbp+3Fh+bWaitAll], 0
0x14010911a  jnz     short loc_140109121
0x14010911c  lea     eax, [rcx-80h]
0x14010911f  mov     [rdi], eax
0x140109121  mov     ebx, 834500CAh
0x140109126  jmp     short loc_1401091A5
0x140109128  cmp     ecx, 102h
0x14010912e  jnz     short loc_14010913D
0x140109130  mov     dword ptr [rdi], 0
0x140109136  mov     ebx, 834500CBh
0x14010913b  jmp     short loc_1401091A5
0x14010913d  mov     eax, cs:dword_140150118
0x140109143  cmp     eax, 2
0x140109146  jbe     short loc_1401091A5
0x140109148  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x14010914f  mov     [rbp+3Fh+arg_0], r12
0x140109153  mov     [rbp+3Fh+var_70], rax
0x140109157  lea     rdx, byte_14014404B
0x14010915e  lea     rax, [rbp+3Fh+arg_0]
0x140109162  mov     [rbp+3Fh+dwMilliseconds], 127h
0x140109169  mov     [rsp+0C0h+var_80], rax
0x14010916e  lea     rax, [rbp+3Fh+dwMilliseconds]
0x140109172  mov     [rsp+0C0h+var_88], rax
0x140109177  lea     rax, [rbp+3Fh+var_68]
0x14010917b  mov     [rsp+0C0h+var_90], rax
0x140109180  lea     rax, [rbp+3Fh+arg_10]
0x140109184  mov     [rsp+0C0h+var_98], rax
0x140109189  lea     rax, [rbp+3Fh+var_70]
0x14010918d  mov     qword ptr [rsp+0C0h+wRemoveMsg], rax
0x140109192  mov     [rbp+3Fh+var_68], r15
0x140109196  mov     dword ptr [rbp+3Fh+arg_10], ebx
0x140109199  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14010919e  jmp     short loc_1401091A5
0x1401091a0  mov     ebx, 80070057h
0x1401091a5  mov     eax, ebx
0x1401091a7  add     rsp, 90h
0x1401091ae  pop     r15
0x1401091b0  pop     r13
0x1401091b2  pop     r12
0x1401091b4  pop     rdi
0x1401091b5  pop     rsi
0x1401091b6  pop     rbx
0x1401091b7  pop     rbp
0x1401091b8  retn
```
