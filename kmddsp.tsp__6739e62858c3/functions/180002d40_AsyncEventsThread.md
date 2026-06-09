# AsyncEventsThread

- ea: `0x180002d40`
- end: `0x18000316e`
- name: `AsyncEventsThread`
- size: `1070`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001400`
- `0x18000298c`
- `0x180002d40`
- `0x180003ba8`
- `0x180007d9c`
- `0x180007df8`
- `0x180009010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002dde`
- `KERNEL32!GetLastError` at `0x180002e6e`
- `KERNEL32!GetLastError` at `0x180002f7c`
- `KERNEL32!GetLastError` at `0x180002dde`
- `KERNEL32!GetLastError` at `0x180002e6e`
- `KERNEL32!GetLastError` at `0x180002f7c`
- `KERNEL32!Sleep` at `0x180002e98`
- `KERNEL32!Sleep` at `0x180002fa8`
- `KERNEL32!Sleep` at `0x180002e98`
- `KERNEL32!Sleep` at `0x180002fa8`
- `KERNEL32!ExitThread` at `0x180003161`
- `KERNEL32!ExitThread` at `0x180003161`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180002e34`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180002e34`
- `KERNEL32!DeviceIoControl` at `0x180002dc9`
- `KERNEL32!DeviceIoControl` at `0x180002f67`
- `KERNEL32!DeviceIoControl` at `0x180002dc9`
- `KERNEL32!DeviceIoControl` at `0x180002f67`
- `KERNEL32!DeleteCriticalSection` at `0x180003057`
- `KERNEL32!DeleteCriticalSection` at `0x180003057`
- `KERNEL32!LeaveCriticalSection` at `0x180003048`
- `KERNEL32!LeaveCriticalSection` at `0x18000306d`
- `KERNEL32!LeaveCriticalSection` at `0x180003048`
- `KERNEL32!LeaveCriticalSection` at `0x18000306d`
- `KERNEL32!EnterCriticalSection` at `0x180003033`
- `KERNEL32!EnterCriticalSection` at `0x180003033`

## string_xrefs

- `0x180002df4`: `AsyncEventsThread: IoCtl(GetEvent) failed(%d)`
- `0x180002f96`: `AsyncEventsThread: IoCtl(GetEvent) failed(%d)`
- `0x18000312f`: `AsyncEventsThread: Got exit message from TSPI_providerShutdown`
- `0x180002e5d`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x180002e86`: `AsyncEventsThread: GetQueuedCompletionStatus failed(%d)`
- `0x180002ebb`: `AsyncEventsThread: got a line event`
- `0x180002fb9`: `AsyncEventsThread: got a completed req`
- `0x180002fce`: `AsyncEventsThread: got a bogus req`
- `0x180002ffe`: `AsyncEventsThread: req(%p) with reqID(%x) returned lRes(%x)`
- `0x18000307c`: `AsyncEventsThread: call compproc with ReqID(%x), lRes(%x)`
- `0x1800030b5`: `AsyncEventsThread: report back the saved call state`

## pseudocode

```c
__int64 __fastcall AsyncEventsThread(LPVOID lpThreadParameter)
{
  HLOCAL v1; // rdx
  HANDLE v2; // rcx
  DWORD LastError; // eax
  LPOVERLAPPED v4; // rbx
  DWORD v5; // eax
  HLOCAL v6; // r9
  unsigned int v7; // edi
  __int64 v8; // rax
  struct _EVENT_RECORD *v9; // rbx
  HANDLE v10; // rcx
  DWORD v11; // eax
  __int64 InternalHigh_low; // rcx
  unsigned int Internal_high; // r14d
  unsigned int v14; // esi
  void (__fastcall *InternalHigh)(LPOVERLAPPED, _QWORD, const void **); // rax
  bool v16; // zf
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+44h] [rbp-45h] BYREF
  LPOVERLAPPED v21; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp-39h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+58h] [rbp-31h] BYREF
  const void *v24; // [rsp+78h] [rbp-11h] BYREF
  const void *v25; // [rsp+80h] [rbp-9h]
  const void *v26; // [rsp+88h] [rbp-1h]
  const void *v27; // [rsp+90h] [rbp+7h]
  const void *v28; // [rsp+98h] [rbp+Fh]

  v1 = gpAsyncEventsThreadInfo;
  memset(&Overlapped, 0, sizeof(Overlapped));
  BytesReturned = 0;
  **((_DWORD **)gpAsyncEventsThreadInfo + 1) = *((_DWORD *)gpAsyncEventsThreadInfo + 4) - 11;
  v2 = ghDriverAsync;
  *(_DWORD *)(*((_QWORD *)v1 + 1) + 4LL) = 0;
  if ( !DeviceIoControl(
          v2,
          0x8FFF23D0,
          *((LPVOID *)v1 + 1),
          0xCu,
          *((LPVOID *)v1 + 1),
          *((_DWORD *)v1 + 4),
          &BytesReturned,
          &Overlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
      TspLog(1, "AsyncEventsThread: IoCtl(GetEvent) failed(%d)", LastError);
  }
LABEL_4:
  v21 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      NumberOfBytesTransferred = 0;
      CompletionKey = 0;
      if ( GetQueuedCompletionStatus(ghCompletionPort, &NumberOfBytesTransferred, &CompletionKey, &v21, 0xFFFFFFFF) )
        break;
      v5 = GetLastError();
      if ( v5 == 6 )
        ExitThread(0);
      TspLog(1, "AsyncEventsThread: GetQueuedCompletionStatus failed(%d)", v5);
      Sleep(1u);
    }
    v4 = v21;
    if ( &gOverlappedTerminate == v21 )
      return TspLog(2, "AsyncEventsThread: Got exit message from TSPI_providerShutdown");
    if ( v21 )
    {
      if ( v21 == &Overlapped )
      {
        TspLog(4, "AsyncEventsThread: got a line event");
        v6 = gpAsyncEventsThreadInfo;
        v7 = 0;
        v8 = *((_QWORD *)gpAsyncEventsThreadInfo + 1);
        v9 = (struct _EVENT_RECORD *)(v8 + 8);
        if ( *(unsigned int *)(v8 + 4) / 0x30uLL )
        {
          do
          {
            ProcessEvent(v9);
            v6 = gpAsyncEventsThreadInfo;
            ++v7;
            v9 = (struct _EVENT_RECORD *)((char *)v9 + 48);
          }
          while ( v7 < *(unsigned int *)(*((_QWORD *)gpAsyncEventsThreadInfo + 1) + 4LL) / 0x30uLL );
        }
        Overlapped.hEvent = 0;
        **((_DWORD **)v6 + 1) = *((_DWORD *)v6 + 4) - 11;
        v10 = ghDriverAsync;
        *(_DWORD *)(*((_QWORD *)v6 + 1) + 4LL) = 0;
        if ( !DeviceIoControl(
                v10,
                0x8FFF23D0,
                *((LPVOID *)v6 + 1),
                0xCu,
                *((LPVOID *)v6 + 1),
                *((_DWORD *)v6 + 4),
                &BytesReturned,
                &Overlapped) )
        {
          v11 = GetLastError();
          if ( v11 != 997 )
          {
            TspLog(1, "AsyncEventsThread: IoCtl(GetEvent) failed(%d)", v11);
            Sleep(1u);
          }
        }
      }
      else
      {
        TspLog(4, "AsyncEventsThread: got a completed req");
        if ( LODWORD(v4[1].Internal) == 1095915339 )
        {
          InternalHigh_low = LODWORD(v4[3].InternalHigh);
          Internal_high = HIDWORD(v4[1].Internal);
          v4[-1].Offset = 0;
          v14 = TranslateDriverResult(InternalHigh_low);
          TspLog(4, "AsyncEventsThread: req(%p) with reqID(%x) returned lRes(%x)", v4, Internal_high, v14);
          v24 = 0;
          InternalHigh = (void (__fastcall *)(LPOVERLAPPED, _QWORD, const void **))v4[1].InternalHigh;
          if ( InternalHigh )
            InternalHigh(v4, v14, &v24);
          EnterCriticalSection((LPCRITICAL_SECTION)&v4[1].16);
          v16 = LODWORD(v4[2].hEvent)-- == 1;
          v17 = (struct _RTL_CRITICAL_SECTION *)&v4[1].16;
          if ( v16 )
          {
            LeaveCriticalSection(v17);
            DeleteCriticalSection((LPCRITICAL_SECTION)&v4[1].16);
            FreeRequest(v4);
          }
          else
          {
            LeaveCriticalSection(v17);
          }
          TspLog(8, "AsyncEventsThread: call compproc with ReqID(%x), lRes(%x)", Internal_high, v14);
          ((void (__fastcall *)(_QWORD, _QWORD))gpfnCompletionProc)(Internal_high, v14);
          if ( v24 )
          {
            TspLog(4, "AsyncEventsThread: report back the saved call state");
            TspLog(
              4,
              "AET::fnLineEvent(CALLSTATE): htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
              v24,
              v25,
              v26,
              v27,
              v28);
            ((void (__fastcall *)(const void *, const void *, __int64, const void *, const void *, const void *))gpfnLineEvent)(
              v24,
              v25,
              2,
              v26,
              v27,
              v28);
          }
        }
        else
        {
          TspLog(2, "AsyncEventsThread: got a bogus req");
        }
      }
      goto LABEL_4;
    }
    TspLog(2, "AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!");
  }
}

```

## disassembly

```asm
0x180002d40  push    rbp
0x180002d42  push    rbx
0x180002d43  push    rsi
0x180002d44  push    rdi
0x180002d45  push    r12
0x180002d47  push    r14
0x180002d49  push    r15
0x180002d4b  lea     rbp, [rsp-27h]
0x180002d50  sub     rsp, 0B0h
0x180002d57  mov     rax, cs:__security_cookie
0x180002d5e  xor     rax, rsp
0x180002d61  mov     [rbp+57h+var_40], rax
0x180002d65  mov     rdx, cs:gpAsyncEventsThreadInfo
0x180002d6c  xor     r15d, r15d
0x180002d6f  mov     [rbp+57h+Overlapped.Internal], r15
0x180002d73  xorps   xmm0, xmm0
0x180002d76  movdqu  xmmword ptr [rbp+57h+Overlapped.InternalHigh], xmm0
0x180002d7b  mov     [rbp+57h+BytesReturned], r15d
0x180002d7f  mov     ecx, [rdx+10h]
0x180002d82  lea     r9d, [r15+0Ch]; nInBufferSize
0x180002d86  mov     rax, [rdx+8]
0x180002d8a  sub     ecx, 0Bh
0x180002d8d  mov     [rbp+57h+Overlapped.hEvent], r15
0x180002d91  mov     [rax], ecx
0x180002d93  mov     rax, [rdx+8]
0x180002d97  mov     rcx, cs:ghDriverAsync; hDevice
0x180002d9e  mov     [rax+4], r15d
0x180002da2  lea     rax, [rbp+57h+Overlapped]
0x180002da6  mov     r8, [rdx+8]; lpInBuffer
0x180002daa  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x180002daf  lea     rax, [rbp+57h+BytesReturned]
0x180002db3  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x180002db8  mov     eax, [rdx+10h]
0x180002dbb  mov     edx, 8FFF23D0h; dwIoControlCode
0x180002dc0  mov     [rsp+0E0h+nOutBufferSize], eax; nOutBufferSize
0x180002dc4  mov     [rsp+0E0h+lpOutBuffer], r8; lpOutBuffer
0x180002dc9  call    cs:__imp_DeviceIoControl
0x180002dd0  nop     dword ptr [rax+rax+00h]
0x180002dd5  lea     r12d, [r15+1]
0x180002dd9  cmp     eax, r12d
0x180002ddc  jz      short loc_180002E03
0x180002dde  call    cs:__imp_GetLastError
0x180002de5  nop     dword ptr [rax+rax+00h]
0x180002dea  cmp     eax, 3E5h
0x180002def  jz      short loc_180002E03
0x180002df1  mov     r8d, eax
0x180002df4  lea     rdx, aAsynceventsthr_3; "AsyncEventsThread: IoCtl(GetEvent) fail"...
0x180002dfb  mov     ecx, r12d
0x180002dfe  call    TspLog
0x180002e03  mov     rsi, 0AAAAAAAAAAAAAAABh
0x180002e0d  mov     [rbp+57h+var_98], r15
0x180002e11  mov     rcx, cs:ghCompletionPort; CompletionPort
0x180002e18  lea     r9, [rbp+57h+var_98]; lpOverlapped
0x180002e1c  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x180002e20  mov     [rbp+57h+NumberOfBytesTransferred], r15d
0x180002e24  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180002e28  mov     [rbp+57h+CompletionKey], r15
0x180002e2c  mov     dword ptr [rsp+0E0h+lpOutBuffer], 0FFFFFFFFh; dwMilliseconds
0x180002e34  call    cs:__imp_GetQueuedCompletionStatus
0x180002e3b  nop     dword ptr [rax+rax+00h]
0x180002e40  test    eax, eax
0x180002e42  jz      short loc_180002E6E
0x180002e44  mov     rbx, [rbp+57h+var_98]
0x180002e48  lea     rax, gOverlappedTerminate
0x180002e4f  cmp     rax, rbx
0x180002e52  jz      loc_18000312F
0x180002e58  test    rbx, rbx
0x180002e5b  jnz     short loc_180002EA9
0x180002e5d  lea     rdx, aAsynceventsthr_6; "AsyncEventsThread: GetQueuedCompletionS"...
0x180002e64  lea     ecx, [rbx+2]
0x180002e67  call    TspLog
0x180002e6c  jmp     short loc_180002E11
0x180002e6e  call    cs:__imp_GetLastError
0x180002e75  nop     dword ptr [rax+rax+00h]
0x180002e7a  cmp     eax, 6
0x180002e7d  jz      loc_18000315F
0x180002e83  mov     r8d, eax
0x180002e86  lea     rdx, aAsynceventsthr; "AsyncEventsThread: GetQueuedCompletionS"...
0x180002e8d  mov     ecx, r12d
0x180002e90  call    TspLog
0x180002e95  mov     ecx, r12d; dwMilliseconds
0x180002e98  call    cs:__imp_Sleep
0x180002e9f  nop     dword ptr [rax+rax+00h]
0x180002ea4  jmp     loc_180002E11
0x180002ea9  lea     rax, [rbp+57h+Overlapped]
0x180002ead  mov     ecx, 4
0x180002eb2  cmp     rbx, rax
0x180002eb5  jnz     loc_180002FB9
0x180002ebb  lea     rdx, aAsynceventsthr_5; "AsyncEventsThread: got a line event"
0x180002ec2  call    TspLog
0x180002ec7  mov     r9, cs:gpAsyncEventsThreadInfo
0x180002ece  mov     edi, r15d
0x180002ed1  mov     rax, [r9+8]
0x180002ed5  mov     ecx, [rax+4]
0x180002ed8  lea     rbx, [rax+8]
0x180002edc  mov     rax, rsi
0x180002edf  mul     rcx
0x180002ee2  shr     rdx, 5
0x180002ee6  test    rdx, rdx
0x180002ee9  jz      short loc_180002F19
0x180002eeb  mov     rcx, rbx; eventRecord
0x180002eee  call    ProcessEvent
0x180002ef3  mov     r9, cs:gpAsyncEventsThreadInfo
0x180002efa  add     edi, r12d
0x180002efd  add     rbx, 30h ; '0'
0x180002f01  mov     rax, [r9+8]
0x180002f05  mov     ecx, [rax+4]
0x180002f08  mov     rax, rsi
0x180002f0b  mul     rcx
0x180002f0e  mov     eax, edi
0x180002f10  shr     rdx, 5
0x180002f14  cmp     rax, rdx
0x180002f17  jb      short loc_180002EEB
0x180002f19  mov     [rbp+57h+Overlapped.hEvent], r15
0x180002f1d  mov     edx, 8FFF23D0h; dwIoControlCode
0x180002f22  mov     ecx, [r9+10h]
0x180002f26  mov     rax, [r9+8]
0x180002f2a  sub     ecx, 0Bh
0x180002f2d  mov     [rax], ecx
0x180002f2f  mov     rax, [r9+8]
0x180002f33  mov     rcx, cs:ghDriverAsync; hDevice
0x180002f3a  mov     [rax+4], r15d
0x180002f3e  lea     rax, [rbp+57h+Overlapped]
0x180002f42  mov     r8, [r9+8]; lpInBuffer
0x180002f46  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x180002f4b  lea     rax, [rbp+57h+BytesReturned]
0x180002f4f  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x180002f54  mov     eax, [r9+10h]
0x180002f58  mov     r9d, 0Ch; nInBufferSize
0x180002f5e  mov     [rsp+0E0h+nOutBufferSize], eax; nOutBufferSize
0x180002f62  mov     [rsp+0E0h+lpOutBuffer], r8; lpOutBuffer
0x180002f67  call    cs:__imp_DeviceIoControl
0x180002f6e  nop     dword ptr [rax+rax+00h]
0x180002f73  cmp     eax, r12d
0x180002f76  jz      loc_180002E0D
0x180002f7c  call    cs:__imp_GetLastError
0x180002f83  nop     dword ptr [rax+rax+00h]
0x180002f88  cmp     eax, 3E5h
0x180002f8d  jz      loc_180002E0D
0x180002f93  mov     r8d, eax
0x180002f96  lea     rdx, aAsynceventsthr_3; "AsyncEventsThread: IoCtl(GetEvent) fail"...
0x180002f9d  mov     ecx, r12d
0x180002fa0  call    TspLog
0x180002fa5  mov     ecx, r12d; dwMilliseconds
0x180002fa8  call    cs:__imp_Sleep
0x180002faf  nop     dword ptr [rax+rax+00h]
0x180002fb4  jmp     loc_180002E0D
0x180002fb9  lea     rdx, aAsynceventsthr_7; "AsyncEventsThread: got a completed req"
0x180002fc0  call    TspLog
0x180002fc5  cmp     dword ptr [rbx+20h], 4152574Bh
0x180002fcc  jz      short loc_180002FE4
0x180002fce  lea     rdx, aAsynceventsthr_8; "AsyncEventsThread: got a bogus req"
0x180002fd5  mov     ecx, 2
0x180002fda  call    TspLog
0x180002fdf  jmp     loc_180002E0D
0x180002fe4  mov     ecx, [rbx+68h]
0x180002fe7  mov     r14d, [rbx+24h]
0x180002feb  mov     [rbx-10h], r15d
0x180002fef  call    TranslateDriverResult
0x180002ff4  mov     r9d, r14d
0x180002ff7  mov     dword ptr [rsp+0E0h+lpOutBuffer], eax
0x180002ffb  mov     r8, rbx
0x180002ffe  lea     rdx, aAsynceventsthr_2; "AsyncEventsThread: req(%p) with reqID(%"...
0x180003005  mov     ecx, 4
0x18000300a  mov     esi, eax
0x18000300c  call    TspLog
0x180003011  mov     [rbp+57h+var_68], r15
0x180003015  mov     rax, [rbx+28h]
0x180003019  test    rax, rax
0x18000301c  jz      short loc_18000302C
0x18000301e  lea     r8, [rbp+57h+var_68]
0x180003022  mov     edx, esi
0x180003024  mov     rcx, rbx
0x180003027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302c  lea     rdi, [rbx+30h]
0x180003030  mov     rcx, rdi; lpCriticalSection
0x180003033  call    cs:__imp_EnterCriticalSection
0x18000303a  nop     dword ptr [rax+rax+00h]
0x18000303f  add     dword ptr [rbx+58h], 0FFFFFFFFh
0x180003043  mov     rcx, rdi; lpCriticalSection
0x180003046  jnz     short loc_18000306D
0x180003048  call    cs:__imp_LeaveCriticalSection
0x18000304f  nop     dword ptr [rax+rax+00h]
0x180003054  mov     rcx, rdi; lpCriticalSection
0x180003057  call    cs:__imp_DeleteCriticalSection
0x18000305e  nop     dword ptr [rax+rax+00h]
0x180003063  mov     rcx, rbx; void *
0x180003066  call    FreeRequest
0x18000306b  jmp     short loc_180003079
0x18000306d  call    cs:__imp_LeaveCriticalSection
0x180003074  nop     dword ptr [rax+rax+00h]
0x180003079  mov     r9d, esi
0x18000307c  lea     rdx, aAsynceventsthr_1; "AsyncEventsThread: call compproc with R"...
0x180003083  mov     r8d, r14d
0x180003086  mov     ecx, 8
0x18000308b  call    TspLog
0x180003090  mov     rax, cs:gpfnCompletionProc
0x180003097  mov     edx, esi
0x180003099  mov     ecx, r14d
0x18000309c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a1  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800030ab  cmp     [rbp+57h+var_68], r15
0x1800030af  jz      loc_180002E0D
0x1800030b5  lea     rdx, aAsynceventsthr_0; "AsyncEventsThread: report back the save"...
0x1800030bc  mov     ecx, 4
0x1800030c1  call    TspLog
0x1800030c6  mov     rax, [rbp+57h+var_48]
0x1800030ca  lea     rdx, aAetFnlineevent; "AET::fnLineEvent(CALLSTATE): htline(%p)"...
0x1800030d1  mov     r9, [rbp+57h+var_60]
0x1800030d5  mov     ecx, 4
0x1800030da  mov     r8, [rbp+57h+var_68]
0x1800030de  mov     [rsp+0E0h+lpBytesReturned], rax
0x1800030e3  mov     rax, [rbp+57h+var_50]
0x1800030e7  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x1800030ec  mov     rax, [rbp+57h+var_58]
0x1800030f0  mov     [rsp+0E0h+lpOutBuffer], rax
0x1800030f5  call    TspLog
0x1800030fa  mov     rcx, [rbp+57h+var_48]
0x1800030fe  mov     r8d, 2
0x180003104  mov     r9, [rbp+57h+var_58]
0x180003108  mov     rdx, [rbp+57h+var_60]
0x18000310c  mov     rax, cs:gpfnLineEvent
0x180003113  mov     qword ptr [rsp+0E0h+nOutBufferSize], rcx
0x180003118  mov     rcx, [rbp+57h+var_50]
0x18000311c  mov     [rsp+0E0h+lpOutBuffer], rcx
0x180003121  mov     rcx, [rbp+57h+var_68]
0x180003125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000312a  jmp     loc_180002E0D
0x18000312f  lea     rdx, aAsynceventsthr_4; "AsyncEventsThread: Got exit message fro"...
0x180003136  mov     ecx, 2
0x18000313b  call    TspLog
0x180003140  mov     rcx, [rbp+57h+var_40]
0x180003144  xor     rcx, rsp; StackCookie
0x180003147  call    __security_check_cookie
0x18000314c  add     rsp, 0B0h
0x180003153  pop     r15
0x180003155  pop     r14
0x180003157  pop     r12
0x180003159  pop     rdi
0x18000315a  pop     rsi
0x18000315b  pop     rbx
0x18000315c  pop     rbp
0x18000315d  retn
0x18000315f  xor     ecx, ecx; dwExitCode
0x180003161  call    cs:__imp_ExitThread
```
