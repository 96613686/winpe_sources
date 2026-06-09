# FILE_LISTENER::ChangeNotificationThread(void *)

- ea: `0x180003eb0`
- end: `0x180004014`
- name: `?ChangeNotificationThread@FILE_LISTENER@@CAKPEAX@Z`
- size: `356`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x180003e1c`
- `0x180003eb0`
- `0x18000401c`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f71`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180003f14`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180003f14`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180003f98`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180003f98`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003fb2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003fb2`

## pseudocode

```c
__int64 __fastcall FILE_LISTENER::ChangeNotificationThread(PVOID Parameter)
{
  DWORD LastError; // eax
  volatile signed __int32 *v2; // rbx
  struct _LIST_ENTRY *i; // rdi
  const FILETIME *v4; // rbx
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 CompletionKey; // [rsp+38h] [rbp-48h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+40h] [rbp-40h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  FILETIME FileTime2[2]; // [rsp+58h] [rbp-28h] BYREF
  int v11; // [rsp+68h] [rbp-18h]

  FileInformation = 0;
  v11 = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  NumberOfBytesTransferred = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      Overlapped = 0;
      CompletionKey = 0;
      if ( GetQueuedCompletionStatus(
             FILE_LISTENER::sm_hCompletionPort,
             &NumberOfBytesTransferred,
             &CompletionKey,
             &Overlapped,
             0x1388u) )
      {
        LastError = 0;
        break;
      }
      LastError = GetLastError();
      if ( LastError != 258 )
        break;
      for ( i = FILE_LISTENER::sm_UncListenersList.Flink; i != &FILE_LISTENER::sm_UncListenersList; i = i->Flink )
      {
        v4 = (const FILETIME *)&i[-12];
        if ( GetFileAttributesExW((LPCWSTR)i[-9].Flink, GetFileExInfoStandard, &FileInformation) )
        {
          if ( CompareFileTime(v4 + 9, (const FILETIME *)&FileTime2[0].dwHighDateTime) )
          {
            _InterlockedIncrement((volatile signed __int32 *)&v4->dwHighDateTime);
            FILE_LISTENER::HandleChangeNotification((FILE_LISTENER *)&i[-12], 0, 1u);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)&v4->dwHighDateTime, 0xFFFFFFFF) == 1 )
            {
              FILE_LISTENER::~FILE_LISTENER((FILE_LISTENER *)&i[-12]);
              operator delete(&i[-12]);
            }
          }
        }
        else
        {
          v4[9] = 0;
        }
      }
    }
    if ( CompletionKey == -1 )
      return 0;
    if ( Overlapped )
    {
      v2 = (volatile signed __int32 *)&Overlapped[-3];
      _InterlockedIncrement((volatile signed __int32 *)&Overlapped[-3].Internal + 1);
      FILE_LISTENER::HandleChangeNotification((FILE_LISTENER *)v2, LastError, NumberOfBytesTransferred);
      if ( _InterlockedExchangeAdd(v2 + 1, 0xFFFFFFFF) == 1 )
      {
        if ( v2 )
        {
          FILE_LISTENER::~FILE_LISTENER((FILE_LISTENER *)v2);
          operator delete((void *)v2);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180003eb0  push    rbp
0x180003eb2  push    rbx
0x180003eb3  push    rsi
0x180003eb4  push    rdi
0x180003eb5  push    r15
0x180003eb7  mov     rbp, rsp
0x180003eba  sub     rsp, 80h
0x180003ec1  mov     rax, cs:__security_cookie
0x180003ec8  xor     rax, rsp
0x180003ecb  mov     [rbp+var_10], rax
0x180003ecf  xorps   xmm0, xmm0
0x180003ed2  lea     r15, ?sm_UncListenersList@FILE_LISTENER@@0U_LIST_ENTRY@@A; _LIST_ENTRY FILE_LISTENER::sm_UncListenersList
0x180003ed9  xor     eax, eax
0x180003edb  movups  [rbp+FileInformation], xmm0
0x180003edf  mov     [rbp+var_18], eax
0x180003ee2  movups  xmmword ptr [rbp+FileTime2.dwLowDateTime], xmm0
0x180003ee6  mov     [rbp+NumberOfBytesTransferred], eax
0x180003ee9  mov     rcx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; CompletionPort
0x180003ef0  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180003ef4  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180003ef8  mov     [rbp+Overlapped], 0
0x180003f00  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180003f04  mov     [rbp+CompletionKey], 0
0x180003f0c  mov     [rsp+80h+dwMilliseconds], 1388h; dwMilliseconds
0x180003f14  call    cs:__imp_GetQueuedCompletionStatus
0x180003f1a  test    eax, eax
0x180003f1c  jz      short loc_180003F71
0x180003f1e  xor     eax, eax
0x180003f20  cmp     [rbp+CompletionKey], 0FFFFFFFFFFFFFFFFh
0x180003f25  jz      loc_180003FF8
0x180003f2b  mov     rbx, [rbp+Overlapped]
0x180003f2f  test    rbx, rbx
0x180003f32  jz      short loc_180003EE9
0x180003f34  add     rbx, 0FFFFFFFFFFFFFFA0h
0x180003f38  lock inc dword ptr [rbx+4]
0x180003f3c  mov     r8d, [rbp+NumberOfBytesTransferred]; unsigned int
0x180003f40  mov     edx, eax; unsigned int
0x180003f42  mov     rcx, rbx; this
0x180003f45  call    ?HandleChangeNotification@FILE_LISTENER@@AEAAXKK@Z; FILE_LISTENER::HandleChangeNotification(ulong,ulong)
0x180003f4a  or      eax, 0FFFFFFFFh
0x180003f4d  lock xadd [rbx+4], eax
0x180003f52  cmp     eax, 1
0x180003f55  jnz     short loc_180003EE9
0x180003f57  test    rbx, rbx
0x180003f5a  jz      short loc_180003EE9
0x180003f5c  mov     rcx, rbx; this
0x180003f5f  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x180003f64  mov     rcx, rbx; Block
0x180003f67  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003f6c  jmp     loc_180003EE9
0x180003f71  call    cs:__imp_GetLastError
0x180003f77  cmp     eax, 102h
0x180003f7c  jnz     short loc_180003F20
0x180003f7e  mov     rdi, cs:?sm_UncListenersList@FILE_LISTENER@@0U_LIST_ENTRY@@A; _LIST_ENTRY FILE_LISTENER::sm_UncListenersList
0x180003f85  jmp     short loc_180003FEE
0x180003f87  lea     rbx, [rdi-0C0h]
0x180003f8e  xor     edx, edx; fInfoLevelId
0x180003f90  mov     rcx, [rbx+30h]; lpFileName
0x180003f94  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180003f98  call    cs:__imp_GetFileAttributesExW
0x180003f9e  test    eax, eax
0x180003fa0  jnz     short loc_180003FAA
0x180003fa2  xor     eax, eax
0x180003fa4  mov     [rbx+48h], rax
0x180003fa8  jmp     short loc_180003FEB
0x180003faa  lea     rdx, [rbp+FileTime2.dwHighDateTime]; lpFileTime2
0x180003fae  lea     rcx, [rbx+48h]; lpFileTime1
0x180003fb2  call    cs:__imp_CompareFileTime
0x180003fb8  test    eax, eax
0x180003fba  jz      short loc_180003FEB
0x180003fbc  lock inc dword ptr [rbx+4]
0x180003fc0  xor     edx, edx; unsigned int
0x180003fc2  mov     rcx, rbx; this
0x180003fc5  lea     r8d, [rdx+1]; unsigned int
0x180003fc9  call    ?HandleChangeNotification@FILE_LISTENER@@AEAAXKK@Z; FILE_LISTENER::HandleChangeNotification(ulong,ulong)
0x180003fce  or      eax, 0FFFFFFFFh
0x180003fd1  lock xadd [rbx+4], eax
0x180003fd6  cmp     eax, 1
0x180003fd9  jnz     short loc_180003FEB
0x180003fdb  mov     rcx, rbx; this
0x180003fde  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x180003fe3  mov     rcx, rbx; Block
0x180003fe6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003feb  mov     rdi, [rdi]
0x180003fee  cmp     rdi, r15
0x180003ff1  jnz     short loc_180003F87
0x180003ff3  jmp     loc_180003EE9
0x180003ff8  xor     eax, eax
0x180003ffa  mov     rcx, [rbp+var_10]
0x180003ffe  xor     rcx, rsp; StackCookie
0x180004001  call    __security_check_cookie
0x180004006  add     rsp, 80h
0x18000400d  pop     r15
0x18000400f  pop     rdi
0x180004010  pop     rsi
0x180004011  pop     rbx
0x180004012  pop     rbp
0x180004013  retn
```
