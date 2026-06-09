# JsonHttpRequest::Send(ushort const *)

- ea: `0x1800ba4c8`
- end: `0x1800ba6bc`
- name: `?Send@JsonHttpRequest@@QEAAJPEBG@Z`
- size: `500`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800276fc`
- `0x180028440`
- `0x1800b237c`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x18003334c`
- `0x18003d72c`
- `0x180043ef8`
- `0x180078720`
- `0x18007bfb4`
- `0x1800ba4c8`
- `0x1800ba6c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba51e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba51e`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ba50c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800ba50c`

## string_xrefs

- `0x1800ba67e`: `Logger::WriteJsonRequestFailureEvent`
- `0x1800ba4db`: `JsonHttpRequest::Send`
- `0x1800ba559`: `CreateCompleteEvent`
- `0x1800ba574`: `JsonHttpRequest::SendAsync`
- `0x1800ba626`: `GetCopyOfResponseBuffer`
- `0x1800ba5d1`: `WaitForCompleteEvent`
- `0x1800ba52e`: `%s: CreateEventEx failed with error code: 0x%08x`
- `0x1800ba527`: `JsonHttpRequest::CreateCompleteEvent`

## pseudocode

```c
__int64 __fastcall JsonHttpRequest::Send(DWORD_PTR dwContext, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  HANDLE Event; // rax
  __int64 LastError; // rbx
  __int64 v7; // r9
  const wchar_t *v8; // r8
  __int64 v9; // r8
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebp
  int CopyOfResponseBuffer; // eax
  int v14; // ecx
  int v15; // eax
  unsigned int v17; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int16 *v18; // [rsp+60h] [rbp+18h] BYREF

  v18 = 0;
  v4 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started", L"JsonHttpRequest::Send");
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  *(_QWORD *)(dwContext + 184) = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CreateEventEx failed with error code: 0x%08x",
      L"JsonHttpRequest::CreateCompleteEvent",
      LastError);
    if ( (_DWORD)LastError )
    {
      if ( (int)LastError <= 0 )
      {
LABEL_6:
        v7 = (unsigned int)LastError;
        v8 = L"CreateCompleteEvent";
        goto LABEL_7;
      }
    }
    else
    {
      LOWORD(LastError) = 1359;
    }
    LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_6;
  }
  Logger::TraceInformation(L"%s: Sending the http request.", L"JsonHttpRequest::SendAsync");
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = WinHttpRequest::SendRequest(dwContext, a2, v9, 0);
  LODWORD(LastError) = v10;
  if ( v10 >= 0 )
  {
    v11 = JsonHttpRequest::WaitForCompleteEvent((JsonHttpRequest *)dwContext);
    LODWORD(LastError) = v11;
    if ( v11 >= 0 )
    {
      LODWORD(LastError) = *(_DWORD *)(dwContext + 176);
      if ( (int)LastError >= 0 )
      {
        v12 = *(_DWORD *)(dwContext + 140);
        Logger::TraceVerbose((wchar_t *)L"%s: Http response code: %d", L"JsonHttpRequest::Send", v12);
        CopyOfResponseBuffer = WinHttpRequest::GetCopyOfResponseBuffer((WinHttpRequest *)dwContext, &v18, &v17);
        LODWORD(LastError) = CopyOfResponseBuffer;
        if ( CopyOfResponseBuffer < 0 )
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"JsonHttpRequest::Send",
            L"GetCopyOfResponseBuffer",
            (unsigned int)CopyOfResponseBuffer);
          v4 = v18;
          goto LABEL_27;
        }
        v4 = v18;
        if ( !v18 )
        {
          LODWORD(LastError) = -2147024882;
          Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"JsonHttpRequest::Send");
          goto LABEL_27;
        }
        if ( v12 == 200 )
          goto LABEL_27;
        v15 = Logger::WriteJsonRequestFailureEvent(v14, v12, v18);
        LODWORD(LastError) = v15;
        if ( v15 >= 0 )
        {
          LODWORD(LastError) = -2145648595;
          goto LABEL_27;
        }
        v7 = (unsigned int)v15;
        v8 = L"Logger::WriteJsonRequestFailureEvent";
      }
      else
      {
        v7 = (unsigned int)LastError;
        v8 = L"RequestCallback";
      }
    }
    else
    {
      v7 = (unsigned int)v11;
      v8 = L"WaitForCompleteEvent";
    }
  }
  else
  {
    v7 = (unsigned int)v10;
    v8 = L"SendAsync";
  }
LABEL_7:
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"JsonHttpRequest::Send", v8, v7);
LABEL_27:
  operator delete(v4);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"JsonHttpRequest::Send", (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800ba4c8  mov     [rsp+arg_8], rbx
0x1800ba4cd  push    rbp
0x1800ba4ce  push    rsi
0x1800ba4cf  push    rdi
0x1800ba4d0  push    r14
0x1800ba4d2  push    r15
0x1800ba4d4  sub     rsp, 20h
0x1800ba4d8  mov     rbp, rdx
0x1800ba4db  lea     r15, aJsonhttpreques_1; "JsonHttpRequest::Send"
0x1800ba4e2  mov     rsi, rcx
0x1800ba4e5  xor     r14d, r14d
0x1800ba4e8  mov     rdx, r15
0x1800ba4eb  mov     [rsp+48h+arg_10], r14
0x1800ba4f0  lea     rcx, aSStarted; "%s started"
0x1800ba4f7  mov     edi, r14d
0x1800ba4fa  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ba4ff  mov     r9d, 1F0003h; dwDesiredAccess
0x1800ba505  xor     r8d, r8d; dwFlags
0x1800ba508  xor     edx, edx; lpName
0x1800ba50a  xor     ecx, ecx; lpEventAttributes
0x1800ba50c  call    cs:__imp_CreateEventExW
0x1800ba512  mov     [rsi+0B8h], rax
0x1800ba519  test    rax, rax
0x1800ba51c  jnz     short loc_1800BA574
0x1800ba51e  call    cs:__imp_GetLastError
0x1800ba524  mov     r8d, eax
0x1800ba527  lea     rdx, aJsonhttpreques_4; "JsonHttpRequest::CreateCompleteEvent"
0x1800ba52e  lea     rcx, aSCreateeventex_0; "%s: CreateEventEx failed with error cod"...
0x1800ba535  mov     ebx, eax
0x1800ba537  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ba53c  test    ebx, ebx
0x1800ba53e  jnz     short loc_1800BA547
0x1800ba540  mov     ebx, 54Fh
0x1800ba545  jmp     short loc_1800BA549
0x1800ba547  jle     short loc_1800BA552
0x1800ba549  movzx   ebx, bx
0x1800ba54c  or      ebx, 80070000h
0x1800ba552  test    ebx, ebx
0x1800ba554  jns     short loc_1800BA574
0x1800ba556  mov     r9d, ebx
0x1800ba559  lea     r8, aCreatecomplete; "CreateCompleteEvent"
0x1800ba560  mov     rdx, r15
0x1800ba563  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800ba56a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ba56f  jmp     loc_1800BA68F
0x1800ba574  lea     rdx, aJsonhttpreques_0; "JsonHttpRequest::SendAsync"
0x1800ba57b  lea     rcx, aSSendingTheHtt; "%s: Sending the http request."
0x1800ba582  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800ba587  test    rbp, rbp
0x1800ba58a  jz      short loc_1800BA59D
0x1800ba58c  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ba590  inc     r8
0x1800ba593  cmp     [rbp+r8*2+0], r14w
0x1800ba599  jnz     short loc_1800BA590
0x1800ba59b  jmp     short loc_1800BA5A0
0x1800ba59d  mov     r8d, r14d; unsigned int
0x1800ba5a0  xor     r9d, r9d; unsigned __int16 *
0x1800ba5a3  mov     rdx, rbp; unsigned __int16 *
0x1800ba5a6  mov     rcx, rsi; dwContext
0x1800ba5a9  call    ?SendRequest@WinHttpRequest@@IEAAJPEBGK0@Z; WinHttpRequest::SendRequest(ushort const *,ulong,ushort const *)
0x1800ba5ae  mov     ebx, eax
0x1800ba5b0  test    eax, eax
0x1800ba5b2  jns     short loc_1800BA5C0
0x1800ba5b4  mov     r9d, eax
0x1800ba5b7  lea     r8, aSendasync; "SendAsync"
0x1800ba5be  jmp     short loc_1800BA560
0x1800ba5c0  mov     rcx, rsi; this
0x1800ba5c3  call    ?WaitForCompleteEvent@JsonHttpRequest@@AEAAJXZ; JsonHttpRequest::WaitForCompleteEvent(void)
0x1800ba5c8  mov     ebx, eax
0x1800ba5ca  test    eax, eax
0x1800ba5cc  jns     short loc_1800BA5DA
0x1800ba5ce  mov     r9d, eax
0x1800ba5d1  lea     r8, aWaitforcomplet_0; "WaitForCompleteEvent"
0x1800ba5d8  jmp     short loc_1800BA560
0x1800ba5da  mov     ebx, [rsi+0B0h]
0x1800ba5e0  mov     rdx, r15
0x1800ba5e3  test    ebx, ebx
0x1800ba5e5  jns     short loc_1800BA5F6
0x1800ba5e7  mov     r9d, ebx
0x1800ba5ea  lea     r8, aRequestcallbac; "RequestCallback"
0x1800ba5f1  jmp     loc_1800BA563
0x1800ba5f6  mov     ebp, [rsi+8Ch]
0x1800ba5fc  lea     rcx, aSHttpResponseC; "%s: Http response code: %d"
0x1800ba603  mov     r8d, ebp
0x1800ba606  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ba60b  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x1800ba610  mov     rcx, rsi; this
0x1800ba613  lea     rdx, [rsp+48h+arg_10]; unsigned __int16 **
0x1800ba618  call    ?GetCopyOfResponseBuffer@WinHttpRequest@@QEAAJPEAPEAGPEAK@Z; WinHttpRequest::GetCopyOfResponseBuffer(ushort * *,ulong *)
0x1800ba61d  mov     ebx, eax
0x1800ba61f  test    eax, eax
0x1800ba621  jns     short loc_1800BA643
0x1800ba623  mov     r9d, eax
0x1800ba626  lea     r8, aGetcopyofrespo; "GetCopyOfResponseBuffer"
0x1800ba62d  mov     rdx, r15
0x1800ba630  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800ba637  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ba63c  mov     rdi, [rsp+48h+arg_10]
0x1800ba641  jmp     short loc_1800BA68F
0x1800ba643  mov     rdi, [rsp+48h+arg_10]
0x1800ba648  test    rdi, rdi
0x1800ba64b  jnz     short loc_1800BA663
0x1800ba64d  mov     rdx, r15
0x1800ba650  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x1800ba657  mov     ebx, 8007000Eh
0x1800ba65c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x1800ba661  jmp     short loc_1800BA68F
0x1800ba663  cmp     ebp, 0C8h
0x1800ba669  jz      short loc_1800BA68F
0x1800ba66b  mov     r8, rdi; unsigned __int16 *
0x1800ba66e  mov     edx, ebp; unsigned int
0x1800ba670  call    ?WriteJsonRequestFailureEvent@Logger@@SAJJKPEBG@Z; Logger::WriteJsonRequestFailureEvent(long,ulong,ushort const *)
0x1800ba675  mov     ebx, eax
0x1800ba677  test    eax, eax
0x1800ba679  jns     short loc_1800BA68A
0x1800ba67b  mov     r9d, eax
0x1800ba67e  lea     r8, aLoggerWritejso; "Logger::WriteJsonRequestFailureEvent"
0x1800ba685  jmp     loc_1800BA560
0x1800ba68a  mov     ebx, 801C002Dh
0x1800ba68f  mov     rcx, rdi; Block
0x1800ba692  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ba697  mov     r8d, ebx
0x1800ba69a  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800ba6a1  mov     rdx, r15
0x1800ba6a4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ba6a9  mov     eax, ebx
0x1800ba6ab  mov     rbx, [rsp+48h+arg_8]
0x1800ba6b0  add     rsp, 20h
0x1800ba6b4  pop     r15
0x1800ba6b6  pop     r14
0x1800ba6b8  pop     rdi
0x1800ba6b9  pop     rsi
0x1800ba6ba  pop     rbp
0x1800ba6bb  retn
```
