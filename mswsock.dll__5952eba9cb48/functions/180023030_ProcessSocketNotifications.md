# ProcessSocketNotifications

- ea: `0x180023030`
- end: `0x1800231ea`
- name: `ProcessSocketNotifications`
- size: `442`
- prototype: `__int64 __usercall@<rax>(HANDLE CompletionPort@<rcx>, ULONG ulCount, LPOVERLAPPED_ENTRY lpCompletionPortEntries, PULONG ulNumEntriesRemoved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800052a0`
- `0x180023030`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x18002314f`
- `ntdll!NtDeviceIoControlFile` at `0x18002314f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800230e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800231cb`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatusEx` at `0x1800230d3`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatusEx` at `0x1800230d3`

## pseudocode

```c
__int64 __fastcall ProcessSocketNotifications(
        HANDLE CompletionPort,
        unsigned int a2,
        void **a3,
        DWORD dwMilliseconds,
        ULONG ulCount,
        LPOVERLAPPED_ENTRY lpCompletionPortEntries,
        PULONG ulNumEntriesRemoved)
{
  DWORD LastError; // edi
  BOOL v11; // edx
  void *v12; // rcx
  unsigned int v13; // eax
  DWORD v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rbx
  int v17; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-31h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int128 v21; // [rsp+70h] [rbp-11h]
  __int128 v22; // [rsp+80h] [rbp-1h]

  InputBuffer = 0;
  v21 = 0;
  v22 = 0;
  IoStatusBlock = 0;
  if ( (a2 == 0) != (a3 == 0)
    || (v11 = lpCompletionPortEntries == 0, (ulCount == 0) != v11)
    || (ulNumEntriesRemoved == 0) != v11
    || dwMilliseconds && !lpCompletionPortEntries )
  {
    LastError = 10022;
    goto LABEL_24;
  }
  if ( !a2 )
  {
    if ( GetQueuedCompletionStatusEx(
           CompletionPort,
           lpCompletionPortEntries,
           ulCount,
           ulNumEntriesRemoved,
           dwMilliseconds,
           0) )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    goto LABEL_24;
  }
  v21 = __PAIR128__((unsigned __int64)ulNumEntriesRemoved, (unsigned __int64)lpCompletionPortEntries);
  v12 = *a3;
  *(_QWORD *)&InputBuffer = CompletionPort;
  *(_QWORD *)&v22 = __PAIR64__(dwMilliseconds, a2);
  *((_QWORD *)&InputBuffer + 1) = a3;
  DWORD2(v22) = ulCount;
  v13 = NtDeviceIoControlFile(v12, 0, 0, 0, &IoStatusBlock, 0x12127u, &InputBuffer, 0x30u, 0, 0);
  switch ( v13 )
  {
    case 0x80u:
      LastError = 735;
LABEL_22:
      v15 = 0;
      do
      {
        v16 = 3LL * v15;
        v17 = NtStatusToSocketError(HIDWORD(a3[3 * v15++ + 2]));
        HIDWORD(a3[v16 + 2]) = v17;
      }
      while ( v15 < a2 );
      goto LABEL_24;
    case 0xC0u:
      LastError = 192;
      goto LABEL_22;
    case 0x102u:
      LastError = 258;
      goto LABEL_22;
  }
  v14 = NtStatusToSocketError(v13);
  LastError = v14;
  if ( !v14 || v14 == 258 || v14 == 735 || v14 == 192 )
    goto LABEL_22;
LABEL_24:
  SetLastError(LastError);
  return LastError;
}

```

## disassembly

```asm
0x180023030  push    rbp
0x180023032  push    rbx
0x180023033  push    rsi
0x180023034  push    rdi
0x180023035  push    r14
0x180023037  push    r15
0x180023039  lea     rbp, [rsp-17h]
0x18002303e  sub     rsp, 98h
0x180023045  xor     ebx, ebx
0x180023047  xorps   xmm0, xmm0
0x18002304a  test    edx, edx
0x18002304c  mov     r10d, ebx
0x18002304f  mov     eax, ebx
0x180023051  mov     r15, r8
0x180023054  setz    r10b
0x180023058  mov     r14d, edx
0x18002305b  test    r8, r8
0x18002305e  mov     r11, rcx
0x180023061  movups  [rbp+3Fh+var_60], xmm0
0x180023065  setz    al
0x180023068  movups  [rbp+3Fh+var_50], xmm0
0x18002306c  movups  [rbp+3Fh+var_40], xmm0
0x180023070  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x180023074  cmp     r10d, eax
0x180023077  jz      short loc_180023083
0x180023079  mov     edi, 2726h
0x18002307e  jmp     loc_1800231C9
0x180023083  mov     rcx, [rbp+3Fh+lpCompletionPortEntries]
0x180023087  mov     edx, ebx
0x180023089  mov     r10d, [rbp+3Fh+ulCount]
0x18002308d  test    rcx, rcx
0x180023090  mov     eax, ebx
0x180023092  setz    dl
0x180023095  test    r10d, r10d
0x180023098  setz    al
0x18002309b  cmp     eax, edx
0x18002309d  jnz     short loc_180023079
0x18002309f  mov     r8, [rbp+3Fh+ulNumEntriesRemoved]
0x1800230a3  mov     eax, ebx
0x1800230a5  test    r8, r8
0x1800230a8  setz    al
0x1800230ab  cmp     eax, edx
0x1800230ad  jnz     short loc_180023079
0x1800230af  test    r9d, r9d
0x1800230b2  jz      short loc_1800230B9
0x1800230b4  test    rcx, rcx
0x1800230b7  jz      short loc_180023079
0x1800230b9  test    r14d, r14d
0x1800230bc  jnz     short loc_1800230FD
0x1800230be  mov     rdx, rcx; lpCompletionPortEntries
0x1800230c1  mov     [rsp+0C0h+fAlertable], ebx; fAlertable
0x1800230c5  mov     [rsp+0C0h+dwMilliseconds], r9d; dwMilliseconds
0x1800230ca  mov     rcx, r11; CompletionPort
0x1800230cd  mov     r9, r8; ulNumEntriesRemoved
0x1800230d0  mov     r8d, r10d; ulCount
0x1800230d3  call    cs:__imp_GetQueuedCompletionStatusEx
0x1800230da  nop     dword ptr [rax+rax+00h]
0x1800230df  test    eax, eax
0x1800230e1  jnz     short loc_1800230F6
0x1800230e3  call    cs:__imp_GetLastError
0x1800230ea  nop     dword ptr [rax+rax+00h]
0x1800230ef  mov     edi, eax
0x1800230f1  jmp     loc_1800231C9
0x1800230f6  mov     edi, ebx
0x1800230f8  jmp     loc_1800231C9
0x1800230fd  mov     [rsp+0C0h+OutputBufferLength], ebx; OutputBufferLength
0x180023101  lea     rax, [rbp+3Fh+var_60]
0x180023105  mov     [rsp+0C0h+OutputBuffer], rbx; OutputBuffer
0x18002310a  xor     edx, edx; Event
0x18002310c  mov     [rsp+0C0h+InputBufferLength], 30h ; '0'; InputBufferLength
0x180023114  mov     [rsp+0C0h+InputBuffer], rax; InputBuffer
0x180023119  lea     rax, [rbp+3Fh+IoStatusBlock]
0x18002311d  mov     dword ptr [rbp+3Fh+var_40+4], r9d
0x180023121  xor     r9d, r9d; ApcContext
0x180023124  mov     qword ptr [rbp+3Fh+var_50], rcx
0x180023128  mov     rcx, [r15]; FileHandle
0x18002312b  mov     qword ptr [rbp+3Fh+var_50+8], r8
0x18002312f  xor     r8d, r8d; ApcRoutine
0x180023132  mov     [rsp+0C0h+fAlertable], 12127h; IoControlCode
0x18002313a  mov     qword ptr [rsp+0C0h+dwMilliseconds], rax; IoStatusBlock
0x18002313f  mov     qword ptr [rbp+3Fh+var_60], r11
0x180023143  mov     dword ptr [rbp+3Fh+var_40], r14d
0x180023147  mov     qword ptr [rbp+3Fh+var_60+8], r15
0x18002314b  mov     dword ptr [rbp+3Fh+var_40+8], r10d
0x18002314f  call    cs:__imp_NtDeviceIoControlFile
0x180023156  nop     dword ptr [rax+rax+00h]
0x18002315b  mov     edx, eax
0x18002315d  sub     edx, 80h
0x180023163  jz      short loc_1800231A1
0x180023165  sub     edx, 40h ; '@'
0x180023168  jz      short loc_18002319A
0x18002316a  cmp     edx, 42h ; 'B'
0x18002316d  jz      short loc_180023193
0x18002316f  mov     ecx, eax
0x180023171  call    NtStatusToSocketError
0x180023176  mov     edi, eax
0x180023178  test    eax, eax
0x18002317a  jz      short loc_1800231A6
0x18002317c  cmp     eax, 102h
0x180023181  jz      short loc_1800231A6
0x180023183  cmp     eax, 2DFh
0x180023188  jz      short loc_1800231A6
0x18002318a  cmp     eax, 0C0h
0x18002318f  jnz     short loc_1800231C9
0x180023191  jmp     short loc_1800231A6
0x180023193  mov     edi, 102h
0x180023198  jmp     short loc_1800231A6
0x18002319a  mov     edi, 0C0h
0x18002319f  jmp     short loc_1800231A6
0x1800231a1  mov     edi, 2DFh
0x1800231a6  mov     esi, ebx
0x1800231a8  test    r14d, r14d
0x1800231ab  jz      short loc_1800231C9
0x1800231ad  mov     eax, esi
0x1800231af  lea     rbx, [rax+rax*2]
0x1800231b3  mov     ecx, [r15+rbx*8+14h]
0x1800231b8  call    NtStatusToSocketError
0x1800231bd  inc     esi
0x1800231bf  mov     [r15+rbx*8+14h], eax
0x1800231c4  cmp     esi, r14d
0x1800231c7  jb      short loc_1800231AD
0x1800231c9  mov     ecx, edi; dwErrCode
0x1800231cb  call    cs:__imp_SetLastError
0x1800231d2  nop     dword ptr [rax+rax+00h]
0x1800231d7  mov     eax, edi
0x1800231d9  add     rsp, 98h
0x1800231e0  pop     r15
0x1800231e2  pop     r14
0x1800231e4  pop     rdi
0x1800231e5  pop     rsi
0x1800231e6  pop     rbx
0x1800231e7  pop     rbp
0x1800231e8  retn
```
