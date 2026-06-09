# PingInit

- ea: `0x180034a30`
- end: `0x180034d92`
- name: `PingInit`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180055758`

## callees

- `0x180034a30`

## import_xrefs

- `IPHLPAPI!IcmpCreateFile` at `0x180034b2c`
- `IPHLPAPI!IcmpCreateFile` at `0x180034b2c`
- `KERNEL32!CreateEventW` at `0x180034b72`
- `KERNEL32!CreateEventW` at `0x180034bd6`
- `KERNEL32!CreateEventW` at `0x180034c4a`
- `KERNEL32!CreateEventW` at `0x180034b72`
- `KERNEL32!CreateEventW` at `0x180034bd6`
- `KERNEL32!CreateEventW` at `0x180034c4a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034aae`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034adb`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034b08`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034aae`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034adb`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180034b08`
- `KERNEL32!DeleteCriticalSection` at `0x180034aee`
- `KERNEL32!DeleteCriticalSection` at `0x180034b1b`
- `KERNEL32!DeleteCriticalSection` at `0x180034b48`
- `KERNEL32!DeleteCriticalSection` at `0x180034b57`
- `KERNEL32!DeleteCriticalSection` at `0x180034b9b`
- `KERNEL32!DeleteCriticalSection` at `0x180034baa`
- `KERNEL32!DeleteCriticalSection` at `0x180034bb9`
- `KERNEL32!DeleteCriticalSection` at `0x180034bff`
- `KERNEL32!DeleteCriticalSection` at `0x180034c0e`
- `KERNEL32!DeleteCriticalSection` at `0x180034c1d`
- `KERNEL32!DeleteCriticalSection` at `0x180034c73`
- `KERNEL32!DeleteCriticalSection` at `0x180034c82`
- `KERNEL32!DeleteCriticalSection` at `0x180034c91`
- `KERNEL32!DeleteCriticalSection` at `0x180034d05`
- `KERNEL32!DeleteCriticalSection` at `0x180034d14`
- `KERNEL32!DeleteCriticalSection` at `0x180034d23`
- `KERNEL32!DeleteCriticalSection` at `0x180034aee`
- `KERNEL32!DeleteCriticalSection` at `0x180034b1b`
- `KERNEL32!DeleteCriticalSection` at `0x180034b48`
- `KERNEL32!DeleteCriticalSection` at `0x180034b57`
- `KERNEL32!DeleteCriticalSection` at `0x180034b9b`
- `KERNEL32!DeleteCriticalSection` at `0x180034baa`
- `KERNEL32!DeleteCriticalSection` at `0x180034bb9`
- `KERNEL32!DeleteCriticalSection` at `0x180034bff`
- `KERNEL32!DeleteCriticalSection` at `0x180034c0e`
- `KERNEL32!DeleteCriticalSection` at `0x180034c1d`
- `KERNEL32!DeleteCriticalSection` at `0x180034c73`
- `KERNEL32!DeleteCriticalSection` at `0x180034c82`
- `KERNEL32!DeleteCriticalSection` at `0x180034c91`
- `KERNEL32!DeleteCriticalSection` at `0x180034d05`
- `KERNEL32!DeleteCriticalSection` at `0x180034d14`
- `KERNEL32!DeleteCriticalSection` at `0x180034d23`
- `KERNEL32!CreateThread` at `0x180034cd8`
- `KERNEL32!CreateThread` at `0x180034cd8`
- `KERNEL32!GetLastError` at `0x180034abe`
- `KERNEL32!GetLastError` at `0x180034b8a`
- `KERNEL32!GetLastError` at `0x180034bee`
- `KERNEL32!GetLastError` at `0x180034c62`
- `KERNEL32!GetLastError` at `0x180034cf4`
- `KERNEL32!GetLastError` at `0x180034abe`
- `KERNEL32!GetLastError` at `0x180034b8a`
- `KERNEL32!GetLastError` at `0x180034bee`
- `KERNEL32!GetLastError` at `0x180034c62`
- `KERNEL32!GetLastError` at `0x180034cf4`
- `KERNEL32!CloseHandle` at `0x180034c30`
- `KERNEL32!CloseHandle` at `0x180034ca4`
- `KERNEL32!CloseHandle` at `0x180034d36`
- `KERNEL32!CloseHandle` at `0x180034d49`
- `KERNEL32!CloseHandle` at `0x180034d5c`
- `KERNEL32!CloseHandle` at `0x180034c30`
- `KERNEL32!CloseHandle` at `0x180034ca4`
- `KERNEL32!CloseHandle` at `0x180034d36`
- `KERNEL32!CloseHandle` at `0x180034d49`
- `KERNEL32!CloseHandle` at `0x180034d5c`

## pseudocode

```c
DWORD PingInit()
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx
  DWORD LastError; // ebx
  HANDLE v3; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = 0;
  TerminateEvent = 0;
  qword_1801507D8 = (__int64)&IcmpRepliesList;
  IcmpRepliesList = &IcmpRepliesList;
  IcmpRequestsEvent = 0;
  qword_180150818 = (__int64)&IcmpRequestsList;
  IcmpRequestsList = (__int64)&IcmpRequestsList;
  IcmpRepliesEvent = 0;
  RequestsThreadHandle = 0;
  RepliesThreadHandle = 0;
  IcmpHandle = 0;
  if ( !InitializeCriticalSectionAndSpinCount(&IcmpRepliesCritSect, 0x400u) )
    return GetLastError();
  if ( !InitializeCriticalSectionAndSpinCount(&IcmpRequestsCritSect, 0x400u) )
  {
    v1 = &IcmpRepliesCritSect;
LABEL_5:
    DeleteCriticalSection(v1);
    return GetLastError();
  }
  if ( !InitializeCriticalSectionAndSpinCount(&OutputCritSect, 0x400u) )
  {
    DeleteCriticalSection(&IcmpRepliesCritSect);
    v1 = &IcmpRequestsCritSect;
    goto LABEL_5;
  }
  IcmpHandle = IcmpCreateFile();
  if ( IcmpHandle == (HANDLE)-1LL )
  {
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    v1 = &OutputCritSect;
    goto LABEL_5;
  }
  IcmpRepliesEvent = CreateEventW(0, 0, 0, 0);
  if ( !IcmpRepliesEvent )
  {
    LastError = GetLastError();
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    DeleteCriticalSection(&OutputCritSect);
    return LastError;
  }
  IcmpRequestsEvent = CreateEventW(0, 0, 0, 0);
  if ( !IcmpRequestsEvent )
  {
    LastError = GetLastError();
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    DeleteCriticalSection(&OutputCritSect);
    v3 = IcmpRepliesEvent;
LABEL_15:
    CloseHandle(v3);
    return LastError;
  }
  TerminateEvent = CreateEventW(0, 1, 0, 0);
  if ( !TerminateEvent )
  {
    LastError = GetLastError();
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    DeleteCriticalSection(&OutputCritSect);
    CloseHandle(IcmpRepliesEvent);
    v3 = IcmpRequestsEvent;
    goto LABEL_15;
  }
  RequestsThreadHandle = CreateThread(0, 0, LoopOnIcmpRequests, 0, 0, &ThreadId);
  if ( !RequestsThreadHandle )
  {
    LastError = GetLastError();
    DeleteCriticalSection(&IcmpRepliesCritSect);
    DeleteCriticalSection(&IcmpRequestsCritSect);
    DeleteCriticalSection(&OutputCritSect);
    CloseHandle(IcmpRepliesEvent);
    CloseHandle(IcmpRequestsEvent);
    CloseHandle(TerminateEvent);
    v3 = (HANDLE)RepliesThreadHandle;
    goto LABEL_15;
  }
  ++PingInitLevel;
  return 0;
}

```

## disassembly

```asm
0x180034a30  mov     rax, rsp
0x180034a33  mov     [rax+10h], rbx
0x180034a37  mov     [rax+18h], rbp
0x180034a3b  mov     [rax+20h], rsi
0x180034a3f  push    rdi
0x180034a40  sub     rsp, 30h
0x180034a44  xor     ebx, ebx
0x180034a46  lea     rdi, IcmpRepliesCritSect
0x180034a4d  mov     [rax+8], ebx
0x180034a50  mov     ebp, 400h
0x180034a55  lea     rax, IcmpRepliesList
0x180034a5c  mov     cs:TerminateEvent, rbx
0x180034a63  mov     cs:qword_1801507D8, rax
0x180034a6a  mov     edx, ebp; dwSpinCount
0x180034a6c  mov     cs:IcmpRepliesList, rax
0x180034a73  mov     rcx, rdi; lpCriticalSection
0x180034a76  lea     rax, IcmpRequestsList
0x180034a7d  mov     cs:IcmpRequestsEvent, rbx
0x180034a84  mov     cs:qword_180150818, rax
0x180034a8b  mov     cs:IcmpRequestsList, rax
0x180034a92  mov     cs:IcmpRepliesEvent, rbx
0x180034a99  mov     cs:RequestsThreadHandle, rbx
0x180034aa0  mov     cs:RepliesThreadHandle, rbx
0x180034aa7  mov     cs:IcmpHandle, rbx
0x180034aae  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180034ab5  nop     dword ptr [rax+rax+00h]
0x180034aba  test    eax, eax
0x180034abc  jnz     short loc_180034ACF
0x180034abe  call    cs:__imp_GetLastError
0x180034ac5  nop     dword ptr [rax+rax+00h]
0x180034aca  jmp     loc_180034D7C
0x180034acf  lea     rsi, IcmpRequestsCritSect
0x180034ad6  mov     edx, ebp; dwSpinCount
0x180034ad8  mov     rcx, rsi; lpCriticalSection
0x180034adb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180034ae2  nop     dword ptr [rax+rax+00h]
0x180034ae7  test    eax, eax
0x180034ae9  jnz     short loc_180034AFC
0x180034aeb  mov     rcx, rdi; lpCriticalSection
0x180034aee  call    cs:__imp_DeleteCriticalSection
0x180034af5  nop     dword ptr [rax+rax+00h]
0x180034afa  jmp     short loc_180034ABE
0x180034afc  mov     edx, ebp; dwSpinCount
0x180034afe  lea     rbp, OutputCritSect
0x180034b05  mov     rcx, rbp; lpCriticalSection
0x180034b08  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180034b0f  nop     dword ptr [rax+rax+00h]
0x180034b14  test    eax, eax
0x180034b16  jnz     short loc_180034B2C
0x180034b18  mov     rcx, rdi; lpCriticalSection
0x180034b1b  call    cs:__imp_DeleteCriticalSection
0x180034b22  nop     dword ptr [rax+rax+00h]
0x180034b27  mov     rcx, rsi
0x180034b2a  jmp     short loc_180034AEE
0x180034b2c  call    cs:__imp_IcmpCreateFile
0x180034b33  nop     dword ptr [rax+rax+00h]
0x180034b38  mov     cs:IcmpHandle, rax
0x180034b3f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034b43  jnz     short loc_180034B68
0x180034b45  mov     rcx, rdi; lpCriticalSection
0x180034b48  call    cs:__imp_DeleteCriticalSection
0x180034b4f  nop     dword ptr [rax+rax+00h]
0x180034b54  mov     rcx, rsi; lpCriticalSection
0x180034b57  call    cs:__imp_DeleteCriticalSection
0x180034b5e  nop     dword ptr [rax+rax+00h]
0x180034b63  mov     rcx, rbp
0x180034b66  jmp     short loc_180034AEE
0x180034b68  xor     r9d, r9d; lpName
0x180034b6b  xor     r8d, r8d; bInitialState
0x180034b6e  xor     edx, edx; bManualReset
0x180034b70  xor     ecx, ecx; lpEventAttributes
0x180034b72  call    cs:__imp_CreateEventW
0x180034b79  nop     dword ptr [rax+rax+00h]
0x180034b7e  mov     cs:IcmpRepliesEvent, rax
0x180034b85  test    rax, rax
0x180034b88  jnz     short loc_180034BCC
0x180034b8a  call    cs:__imp_GetLastError
0x180034b91  nop     dword ptr [rax+rax+00h]
0x180034b96  mov     rcx, rdi; lpCriticalSection
0x180034b99  mov     ebx, eax
0x180034b9b  call    cs:__imp_DeleteCriticalSection
0x180034ba2  nop     dword ptr [rax+rax+00h]
0x180034ba7  mov     rcx, rsi; lpCriticalSection
0x180034baa  call    cs:__imp_DeleteCriticalSection
0x180034bb1  nop     dword ptr [rax+rax+00h]
0x180034bb6  mov     rcx, rbp; lpCriticalSection
0x180034bb9  call    cs:__imp_DeleteCriticalSection
0x180034bc0  nop     dword ptr [rax+rax+00h]
0x180034bc5  mov     eax, ebx
0x180034bc7  jmp     loc_180034D7C
0x180034bcc  xor     r9d, r9d; lpName
0x180034bcf  xor     r8d, r8d; bInitialState
0x180034bd2  xor     edx, edx; bManualReset
0x180034bd4  xor     ecx, ecx; lpEventAttributes
0x180034bd6  call    cs:__imp_CreateEventW
0x180034bdd  nop     dword ptr [rax+rax+00h]
0x180034be2  mov     cs:IcmpRequestsEvent, rax
0x180034be9  test    rax, rax
0x180034bec  jnz     short loc_180034C3E
0x180034bee  call    cs:__imp_GetLastError
0x180034bf5  nop     dword ptr [rax+rax+00h]
0x180034bfa  mov     rcx, rdi; lpCriticalSection
0x180034bfd  mov     ebx, eax
0x180034bff  call    cs:__imp_DeleteCriticalSection
0x180034c06  nop     dword ptr [rax+rax+00h]
0x180034c0b  mov     rcx, rsi; lpCriticalSection
0x180034c0e  call    cs:__imp_DeleteCriticalSection
0x180034c15  nop     dword ptr [rax+rax+00h]
0x180034c1a  mov     rcx, rbp; lpCriticalSection
0x180034c1d  call    cs:__imp_DeleteCriticalSection
0x180034c24  nop     dword ptr [rax+rax+00h]
0x180034c29  mov     rcx, cs:IcmpRepliesEvent; hObject
0x180034c30  call    cs:__imp_CloseHandle
0x180034c37  nop     dword ptr [rax+rax+00h]
0x180034c3c  jmp     short loc_180034BC5
0x180034c3e  xor     r9d, r9d; lpName
0x180034c41  xor     r8d, r8d; bInitialState
0x180034c44  xor     ecx, ecx; lpEventAttributes
0x180034c46  lea     edx, [r9+1]; bManualReset
0x180034c4a  call    cs:__imp_CreateEventW
0x180034c51  nop     dword ptr [rax+rax+00h]
0x180034c56  mov     cs:TerminateEvent, rax
0x180034c5d  test    rax, rax
0x180034c60  jnz     short loc_180034CBC
0x180034c62  call    cs:__imp_GetLastError
0x180034c69  nop     dword ptr [rax+rax+00h]
0x180034c6e  mov     rcx, rdi; lpCriticalSection
0x180034c71  mov     ebx, eax
0x180034c73  call    cs:__imp_DeleteCriticalSection
0x180034c7a  nop     dword ptr [rax+rax+00h]
0x180034c7f  mov     rcx, rsi; lpCriticalSection
0x180034c82  call    cs:__imp_DeleteCriticalSection
0x180034c89  nop     dword ptr [rax+rax+00h]
0x180034c8e  mov     rcx, rbp; lpCriticalSection
0x180034c91  call    cs:__imp_DeleteCriticalSection
0x180034c98  nop     dword ptr [rax+rax+00h]
0x180034c9d  mov     rcx, cs:IcmpRepliesEvent; hObject
0x180034ca4  call    cs:__imp_CloseHandle
0x180034cab  nop     dword ptr [rax+rax+00h]
0x180034cb0  mov     rcx, cs:IcmpRequestsEvent
0x180034cb7  jmp     loc_180034C30
0x180034cbc  lea     rax, [rsp+38h+ThreadId]
0x180034cc1  xor     r9d, r9d; lpParameter
0x180034cc4  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180034cc9  lea     r8, LoopOnIcmpRequests; lpStartAddress
0x180034cd0  xor     edx, edx; dwStackSize
0x180034cd2  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x180034cd6  xor     ecx, ecx; lpThreadAttributes
0x180034cd8  call    cs:__imp_CreateThread
0x180034cdf  nop     dword ptr [rax+rax+00h]
0x180034ce4  mov     cs:RequestsThreadHandle, rax
0x180034ceb  test    rax, rax
0x180034cee  jnz     loc_180034D74
0x180034cf4  call    cs:__imp_GetLastError
0x180034cfb  nop     dword ptr [rax+rax+00h]
0x180034d00  mov     rcx, rdi; lpCriticalSection
0x180034d03  mov     ebx, eax
0x180034d05  call    cs:__imp_DeleteCriticalSection
0x180034d0c  nop     dword ptr [rax+rax+00h]
0x180034d11  mov     rcx, rsi; lpCriticalSection
0x180034d14  call    cs:__imp_DeleteCriticalSection
0x180034d1b  nop     dword ptr [rax+rax+00h]
0x180034d20  mov     rcx, rbp; lpCriticalSection
0x180034d23  call    cs:__imp_DeleteCriticalSection
0x180034d2a  nop     dword ptr [rax+rax+00h]
0x180034d2f  mov     rcx, cs:IcmpRepliesEvent; hObject
0x180034d36  call    cs:__imp_CloseHandle
0x180034d3d  nop     dword ptr [rax+rax+00h]
0x180034d42  mov     rcx, cs:IcmpRequestsEvent; hObject
0x180034d49  call    cs:__imp_CloseHandle
0x180034d50  nop     dword ptr [rax+rax+00h]
0x180034d55  mov     rcx, cs:TerminateEvent; hObject
0x180034d5c  call    cs:__imp_CloseHandle
0x180034d63  nop     dword ptr [rax+rax+00h]
0x180034d68  mov     rcx, cs:RepliesThreadHandle
0x180034d6f  jmp     loc_180034C30
0x180034d74  inc     cs:PingInitLevel
0x180034d7a  xor     eax, eax
0x180034d7c  mov     rbx, [rsp+38h+arg_8]
0x180034d81  mov     rbp, [rsp+38h+arg_10]
0x180034d86  mov     rsi, [rsp+38h+arg_18]
0x180034d8b  add     rsp, 30h
0x180034d8f  pop     rdi
0x180034d90  retn
```
